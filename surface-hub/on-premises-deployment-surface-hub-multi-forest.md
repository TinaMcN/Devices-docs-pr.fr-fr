---
title: Déploiement sur site à forêts multiples (SurfaceHub)
description: Cette rubrique explique comment ajouter un compte d’appareil pour votre Microsoft SurfaceHub lorsque vous disposez d’un déploiement sur site à forêts multiples.
keywords: déploiement à forêts multiples, déploiement sur site, compte d’appareil, SurfaceHub
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.date: 08/28/2018
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: 48fe874175a2c55b7e95ba0974cefe29f710c134
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10833618"
---
# Déploiement sur site pour SurfaceHub dans un environnement à forêts multiples


Cette rubrique explique comment ajouter un compte d’appareil pour votre Microsoft SurfaceHub lorsque vous disposez d’un déploiement sur site à forêts multiples.

Si vous disposez d’un déploiement sur site à forêts multiples avec MicrosoftExchange2013 ou une version ultérieure et SkypeEntreprise2013 ou une version ultérieure, vous pouvez [utiliser les scripts PowerShell fournis](appendix-a-powershell-scripts-for-surface-hub.md#create-on-premises-ps-scripts) pour créer des comptes d’appareil. Si vous utilisez un déploiement à forêt unique, consultez [Déploiement sur site pour SurfaceHub dans un environnement à forêt unique](on-premises-deployment-surface-hub-device-accounts.md).

1.  Démarrez une session PowerShell à distance à partir d’un PC et connectez-vous à Exchange.

    Assurez-vous de disposer de l’ensemble approprié d’autorisations pour exécuter les applets de commande associées.

    Notez ici que `$strExchangeServer` est le nom de domaine complet de votre serveur Exchange, et que `$strLyncFQDN` est le nom de domaine complet de votre serveur Skype Entreprise.

    ```PowerShell
    Set-ExecutionPolicy Unrestricted
    $org='contoso.microsoft.com'
    $cred=Get-Credential $admin@$org
    $sessExchange = New-PSSession -ConfigurationName microsoft.exchange -Credential $cred -AllowRedirection -Authentication Kerberos -ConnectionUri "http://$strExchangeServer/powershell" -WarningAction SilentlyContinue
    $sessLync = New-PSSession -Credential $cred -ConnectionURI "https://$strLyncFQDN/OcsPowershell" -AllowRedirection -WarningAction SilentlyContinue
    Import-PSSession $sessExchange
    Import-PSSession $sessLync
    ```

2.  Après avoir établi une session, créez une nouvelle boîte aux lettres dans la forêt de ressources. Cela permettra au compte de s’authentifier sur le SurfaceHub.

    Si vous modifiez une boîte aux lettres de ressources existante:

    ```PowerShell
    New-Mailbox -UserPrincipalName HUB01@contoso.com -Alias HUB01 -Name "Hub-01"
    ```

3.  Après avoir configuré la boîte aux lettres, vous devez créer une stratégie ExchangeActiveSync ou utiliser une stratégie existante compatible.

    Les Surface Hub sont uniquement compatibles avec les comptes d’appareil dotés d’une stratégie ActiveSync, où la propriété **PasswordEnabled** est définie sur **False**. Si la propriété n’est pas définie correctement, les services Exchange sur le SurfaceHub (courrier, calendrier et accès aux réunions) ne seront pas activés.

    Si vous n’avez pas encore créé de stratégie compatible, utilisez l’applet de commande suivante: celle-ci crée une stratégie appelée SurfaceHub. Une fois qu’elle est créée, vous pouvez appliquer la même stratégie à d’autres comptes d’appareil.

    ```PowerShell
    $easPolicy = New-MobileDeviceMailboxPolicy -Name “SurfaceHubs” -PasswordEnabled $false
    ```

    Une fois que vous disposez d’une stratégie compatible, vous devez l’appliquer au compte d’appareil. 

    ```PowerShell
    Set-CASMailbox $acctUpn -ActiveSyncMailboxPolicy $easPolicy -ActiveSyncEnabled $true
    Set-Mailbox $acctUpn -Type Room
    ```

4.  Diverses propriétés Exchange peuvent être définies sur le compte d’appareil afin d'améliorer l’expérience de réunion pour les utilisateurs. Vous pouvez voir les propriétés qui doivent être définies dans la section [Propriétés Exchange](exchange-properties-for-surface-hub-device-accounts.md).

    ```PowerShell
    Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
    Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
    ```

5.  Si vous décidez que le mot de passe n’expire pas, vous pouvez également définir cette option avec des applets de commande PowerShell. Consultez [Gestion des mots de passe](password-management-for-surface-hub-device-accounts.md) pour plus d’informations. Cela doit être défini dans la forêt d’utilisateurs.

    ```PowerShell
    Set-AdUser $acctUpn -PasswordNeverExpires $true
    ```

6.  Activez le compte dans Active Directory de sorte qu’il s’authentifie auprès du SurfaceHub. Cela doit être défini dans la forêt d’utilisateurs.

    ```PowerShell
    Set-AdUser $acctUpn -Enabled $true
    ```

6. Vous devez maintenant changer la boîte aux lettres de salle en boîte aux lettres liée:

    ```PowerShell
    $cred=Get-Credential AuthForest\ADAdmin
    Set-mailbox -Alias LinkedRoomTest1 -LinkedMasterAccount AuthForest\LinkedRoomTest1 -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -Name LinkedRoomTest1 -LinkedCredential $cred -Identity LinkedRoomTest1
    ```

7.  Activez le compte d’appareil avec Skype Entreprise en activant votre compte AD Surface Hub sur un pool Skype Entreprise Server:

    ```PowerShell
    Enable-CsMeetingRoom -SipAddress "sip:HUB01@contoso.com"
     -DomainController DC-ND-001.contoso.com -RegistrarPool LYNCPool15.contoso.com
     -Identity HUB01
    ```

    Vous devrez utiliser l’adresse et le contrôleur de domaine du protocole SIP (Session Initiation Protocol) du Surface Hub, ainsi que vos propres identificateur de pool et identité d’utilisateur Skype Entreprise Server.


## Désactiver la messagerie instantanée et la messagerie instantanée



Surface Hub utilise un compte d’appareil pour fournir des services de messagerie et de collaboration (messagerie instantanée, vidéo, voix). Ce compte d’appareil est utilisé comme identité d’origine (la partie «de») lors de l’envoi d’e-mails, de messages instantanés et de la mise des appels. Étant donné que ce compte ne provient pas d’un utilisateur identifiable individuel, il est considéré comme «anonyme», car il provient du compte de l’appareil de surface Hub.  

Supposez qu’une stratégie de client par utilisateur est affectée à chaque appareil de salle de réunion ayant une identité de **SurfaceHubPolicy**. Pour désactiver la messagerie instantanée et la messagerie électronique anonyme, vous devez ajouter un clientPolicyEntry à cette stratégie client en utilisant les commandes suivantes.

```
$policyEntry = New-CsClientPolicyEntry -Name AllowResourceAccountSendMessage -value $false
$clientPolicy = Get-CsClientPolicy -Identity SurfaceHubPolicy
$clientPolicy.PolicyEntry.Add($policyEntry)
Set-CsClientPolicy -Instance $clientPolicy
```

Pour vérifier que la stratégie a été définie:

```
Select-Object -InputObject $clientPolicy -Property PolicyEntry
```

La sortie doit être:

```
PolicyEntry
-----------
{Name=AllowResourceAccountSendMessage;Value=False}
```
    
    
Pour modifier l’entrée de stratégie:

```
$policyEntry =  New-CsClientPolicyEntry -Name AllowResourceAccountSendMessage -value $true
$clientPolicy | Set-CsClientPolicy -PolicyEntry @{Replace = $policyEntry}
``` 
    
Pour supprimer l’entrée de stratégie:

```
$policyEntry = New-CsClientPolicyEntry -Name AllowResourceAccountSendMessage -value $true
$clientPolicy | Set-CsClientPolicy -PolicyEntry @{Remove = $policyEntry}
```
 





