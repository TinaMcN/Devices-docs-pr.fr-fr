---
title: Déploiement en ligne avec Office365 (SurfaceHub)
description: Cette rubrique contient des instructions concernant l’ajout d’un compte d’appareil pour votre Microsoft SurfaceHub lorsque vous disposez d’un déploiement pur, en ligne.
ms.assetid: D325CA68-A03F-43DF-8520-EACF7C3EDEC1
ms.reviewer: ''
manager: laurawi
keywords: compte d’appareil du SurfaceHub, déploiement en ligne
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 02/21/2018
ms.localizationpriority: medium
ms.openlocfilehash: b38b8eb0ef13c2e945d63821e6e246ac7a59b2d7
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10833617"
---
# Déploiement en ligne avec Office365 (SurfaceHub)


Cette rubrique contient des instructions concernant l’ajout d’un compte d’appareil pour votre Microsoft SurfaceHub lorsque vous disposez d’un déploiement pur, en ligne.

Si vous disposez d’un déploiement pur, en ligne (O365), vous pouvez [utiliser les scripts PowerShell fournis](appendix-a-powershell-scripts-for-surface-hub.md#create-os356-ps-scripts) pour créer des comptes d’appareil. 

1. Démarrez une session PowerShell à distance sur unPC et connectez-vous à Exchange.

   Assurez-vous de disposer de l’ensemble approprié d’autorisations pour exécuter les applets de commande associées.

   ```PowerShell
   Set-ExecutionPolicy RemoteSigned
   $org='contoso.microsoft.com'
   $cred=Get-Credential admin@$org
   $sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic -AllowRedirection
   Import-PSSession $sess
   ```

2. Une fois une session établie, vous allez créer une boîte aux lettres et l’activer en tant que RoomMailboxAccount, ou vous allez modifier les paramètres d’une boîte aux lettres de salle existante. Cela permettra au compte de s’authentifier sur le SurfaceHub.

   Si vous modifiez une boîte aux lettres de ressources existante:

   ```PowerShell
   Set-Mailbox -Identity 'HUB01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

   Si vous créez une boîte aux lettres de ressources:

   ```PowerShell
   New-Mailbox -MicrosoftOnlineServicesID HUB01@contoso.com -Alias HUB01 -Name "Hub-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. Après avoir configuré la boîte aux lettres, vous devez créer une stratégie ExchangeActiveSync ou utiliser une stratégie existante compatible.

   Les Surface Hub sont uniquement compatibles avec les comptes d’appareil dotés d’une stratégie ActiveSync, où la propriété **PasswordEnabled** est définie sur False. Si la propriété n’est pas définie correctement, les services Exchange sur le SurfaceHub (courrier, calendrier et accès aux réunions) ne seront pas activés.

   Si vous n’avez pas encore créé de stratégie compatible, utilisez l’applet de commande suivante: celle-ci crée une stratégie appelée SurfaceHub. Une fois qu’elle est créée, vous pouvez appliquer la même stratégie à d’autres comptes d’appareil.

   ```PowerShell
   $easPolicy = New-MobileDeviceMailboxPolicy -Name "SurfaceHubs" -PasswordEnabled $false -AllowNonProvisionableDevices $True
   ```

   Une fois que vous disposez d’une stratégie compatible, vous devez l’appliquer au compte d’appareil.

   ```PowerShell
   Set-CASMailbox 'HUB01@contoso.com' -ActiveSyncMailboxPolicy $easPolicy.Id
   ```

4. Diverses propriétés Exchange doivent être définies sur le compte d’appareil pour améliorer l’expérience de réunions. Vous pouvez voir les propriétés qui doivent être définies dans la section [Propriétés Exchange](exchange-properties-for-surface-hub-device-accounts.md).

   ```PowerShell
   Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
   ```

5. Connectez-vous à AzureAD.
    
   Vous devez d’abord installer le module Azure AD pour PowerShell version2. Dans une invite de commandes avec élévation de privilèges, exécutez la commande suivante:
    
   ```PowerShell
   Install-Module -Name AzureAD
   ```
   Vous devez vous connecter à AzureAD pour appliquer certains paramètres du compte. Vous pouvez exécuter cette applet de commande pour vous connecter.

   ```PowerShell
   Import-Module AzureAD
   Connect-AzureAD -Credential $cred
   ```

6. Si vous décidez que le mot de passe n’expire pas, vous pouvez également définir cette option avec des applets de commande PowerShell. Consultez [Gestion des mots de passe](password-management-for-surface-hub-device-accounts.md) pour plus d’informations.

   ```PowerShell
   Set-AzureADUser -ObjectId "HUB01@contoso.com" -PasswordPolicies "DisablePasswordExpiration"
   ```

7. Surface Hub nécessite une licence pour les fonctionnalités de Skype Entreprise. Pour activer SkypeEntreprise, votre environnement doit respecter les [conditions préalables pour Skype Entreprise Online](hybrid-deployment-surface-hub-device-accounts.md#skype-for-business-online).
   
   Ensuite, vous pouvez utiliser `Get-AzureADSubscribedSku` pour récupérer la liste des références (SKU) disponibles pour votre clientO365.

   Une fois que vous avez répertorié les références, vous devez attribuer le SkuId que vous souhaitez à la variable `$License.SkuId`.

   ```PowerShell
   Set-AzureADUser -ObjectId "HUB01@contoso.com" -UsageLocation "US"
    
   Get-AzureADSubscribedSku | Select Sku*,*Units
   $License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
   $License.SkuId = SkuId You selected 
    
   $AssignedLicenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
   $AssignedLicenses.AddLicenses = $License
   $AssignedLicenses.RemoveLicenses = @()
    
   Set-AzureADUserLicense -ObjectId "HUB01@contoso.com"  -AssignedLicenses $AssignedLicenses
   ```

8. Activez le compte d’appareil avec SkypeEntreprise.
   Si le module PowerShell de Skype Entreprise n’est pas installé, [téléchargez le module Windows PowerShell de Skype Entreprise Online](https://www.microsoft.com/download/details.aspx?id=39366). 

   - Commencez par créer une session PowerShell à distance à partir d’un PC.

     ```PowerShell
     Import-Module SkypeOnlineConnector  
     $cssess=New-CsOnlineSession -Credential $cred  
     Import-PSSession $cssess -AllowClobber
     ```

   - Ensuite, si vous n’êtes pas certain de la valeur à utiliser pour le paramètre `RegistrarPool` dans votre environnement, vous pouvez obtenir cette valeur à partir d’un utilisateur Skype Entreprise existant en utilisant l'applet de commande suivante (par exemple, <em>alice@contoso.com</em>):

       ```PowerShell
       Get-CsOnlineUser -Identity 'alice@contoso.com' | fl registrarpool
       ```
       OU en définissant une variable
        
       ```PowerShell
    $strRegistrarPool = Get-CsOnlineUser -Identity 'alice@contoso.com' | fl registrarpool | out-string
    $strRegistrarPool = $strRegistrarPool.Substring($strRegistrarPool.IndexOf(':') + 2)
       ```
        
   - Activez le compte Surface Hub à l’aide de l’applet de commande suivante:
      
       ```PowerShell
       Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool yourRegistrarPool -SipAddressType EmailAddress
       ```
        
       OU en utilisant la variable $strRegistarPool ci-dessus
        
       ```PowerShell
       Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool $strRegistrarPool -SipAddressType EmailAddress
       ```

Pour la validation, vous devez être en mesure d’utiliser n’importe quel client Skype Entreprise (PC, Android, etc.) pour vous connecter à ce compte.





