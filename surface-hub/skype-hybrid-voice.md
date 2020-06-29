---
title: Déploiement en ligne ou hybride à l’aide de l’environnement SkypeHybridVoice (SurfaceHub)
description: Cette rubrique explique comment activer le CloudPBX de SkypeEntreprise avec une connectivitéPSTN locale via le pool CloudConnectorEdition ou SkypeEntreprise2015.
keywords: déploiement hybride, SkypeHybridVoice
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: 08349a7d2decb4d4b053cb03fc95808b49d4f2f0
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10833840"
---
# Déploiement en ligne ou hybride à l’aide de l’environnement SkypeHybridVoice (SurfaceHub)

Cette rubrique explique comment activer le CloudPBX de SkypeEntreprise avec une connectivitéPSTN (réseau téléphonique commuté) locale via le pool CloudConnectorEdition ou SkypeEntreprise2015. Dans cette option. vos pools d’accueil SkypeEntreprise et les serveurs Exchange se trouvent dans le cloud et sont connectés par PSTN via un pool local exécutant SkypeEntreprise2015 ou CloudConnectorEdition. [En savoir plus sur les différentes options du CloudPBX](https://technet.microsoft.com/library/mt612869.aspx).  

Si vous avez déployé le CloudPBX de SkypeEntreprise avec l’une des options Hybrid Voice, suivez les étapes ci-dessous pour activer le compte de salle pour SurfaceHub. Il est important de créer tout d’abord un compte d’utilisateur standard, d’affecter toutes les options voix hybride et numéros de téléphone, puis de convertir le compte en un compte de salle. Si vous ne suivez pas cette instruction, vous ne serez pas en mesure d’attribuer un numéro de téléphone hybride.  

>[!WARNING]
>Si vous créez un compte avant de configurer HybridVoice (en exécutant la commande Enable-CSMeetingRoom), vous ne serez pas en mesure de configurer les paramètres HybridVoice requis. Afin de configurer les paramètres HybridVoice pour un compte précédemment configuré ou de reconfigurer un numéro de téléphone, supprimez les licences E5 ou E3 et le complément CloudPBX, puis suivez les étapes suivantes en commençant par l’étape3.

1. Créez un compte d’utilisateur pour SurfaceHub. Cet exemple utilise <strong> surfacehub2@adatum.com </strong> . Le compte peut être créé dans Active Directory local et synchronisé avec le Cloud, ou créé directement dans le Cloud. 

    ![nouvel objet utilisateur](images/new-user-hybrid-voice.png)

2. Sélectionnez **Le mot de passe n’expire jamais**. Cela est important pour un appareil SurfaceHub.

   ![Le mot de passe n’expire jamais](images/new-user-password-hybrid-voice.png)

3. Dans Office365, ajoutez une licence **E5** ou **E3 et le complément CloudPBX** au compte d’utilisateur créé pour la salle. Cela est nécessaire pour exécuter HybridVoice.

   ![Ajouter la licence du produit](images/product-license-hybrid-voice.png)

4. Attendez environ 15minutes jusqu’à ce que le compte d’utilisateur pour la salle s’affiche dans SkypeEntrepriseOnline.

5. Une fois que le compte d’utilisateur pour la salle est créé dans SkypeEntrepriseOnline, activez-le pour HybridVoice dans RemotePowerShell de SkypeEntreprise en exécutant l’applet de commande suivante:

   ```
   Set-csuser surfacehub2@adatum.com EnterpriseVoiceEnabled $true -HostedVoiceMail $true -onpremlineuri tel:+15005000102
   ```
    
6. Valider le flux d’appels HybridVoice en plaçant les appels tests à partir de votre SurfaceHub.

7. Démarrez une session PowerShell distante sur un PC et connectez-vous à Exchange en exécutant les applets de commande suivantes.

   ```
   Set-ExecutionPolicy Unrestricted
   $cred=Get-Credential -Message "Please use your Office 365 admin credentials"
   $sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/ps1-liveid/ -Credential $cred -Authentication Basic -AllowRedirection
   Import-PSSession $sess
   ```
    
8. Après avoir établi une session, modifiez le compte d’utilisateur pour la salle afin de l’activer en tant que **RoomMailboxAccount** en exécutant les applets de commande suivantes. Cela permettra au compte de s’authentifier sur le SurfaceHub.

   ```
   Set-Mailbox surfacehub2@adatum.com -Type Room
   Set-Mailbox surfacehub2@adatum.com -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```
    
9. Après avoir configuré la boîte aux lettres, vous devez créer une stratégie ExchangeActiveSync ou utiliser une stratégie existante compatible.

   Les Surface Hub sont uniquement compatibles avec les comptes d’appareil dotés d’une stratégie ActiveSync, où la propriété **PasswordEnabled** est définie sur **False**. Si la propriété n’est pas définie correctement, les services Exchange sur le SurfaceHub (courrier, calendrier et accès aux réunions) ne seront pas activés.
    
   Si vous n’avez pas encore créé de stratégie compatible, utilisez l’applet de commande suivante (celle-ci crée une stratégie appelée SurfaceHub). Une fois la stratégie créée, vous pouvez appliquer la même stratégie à d’autres comptes d’appareil.

   ```
   $easPolicy = New-MobileDeviceMailboxPolicy -Name "SurfaceHubs" -PasswordEnabled $false
   ```
    
   Une fois que vous disposez d’une stratégie compatible, vous devez l’appliquer au compte d’appareil. Toutefois, les stratégies peuvent uniquement être appliquées aux comptes d’utilisateurs et non aux boîtes aux lettres de ressources. Exécutez les applets de commande suivantes pour convertir la boîte aux lettres en un type d’utilisateur, appliquer la stratégie, puis effectuer une nouvelle conversion en boîte aux lettres (vous devrez peut-être réactiver le compte et également redéfinir le mot de passe).
    
   ```
   Set-Mailbox surfacehub2@adatum.com -Type Regular
   Set-CASMailbox surfacehub2@adatum.com -ActiveSyncMailboxPolicy $easPolicy.id
   Set-Mailbox surfacehub2@adatum.com -Type Room
   $credNewAccount = Get-Credential -Message "Please provide the Surface Hub username and password"
   Set-Mailbox surfacehub2@adatum.com -RoomMailboxPassword $credNewAccount.Password -EnableRoomMailboxAccount $true
   ```
    
10. Diverses propriétés Exchange doivent être définies sur le compte d’appareil pour améliorer l’expérience de réunions. Vous pouvez voir les propriétés qui peuvent être définies dans les [propriétés Exchange](exchange-properties-for-surface-hub-device-accounts.md). Les applets de commande suivantes fournissent un exemple de définition des propriétés Exchange.

    ```
    Set-CalendarProcessing surfacehub2@adatum.com -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
    Set-CalendarProcessing surfacehub2@adatum.com -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
    ```

11. Activez la boîte aux lettres en tant qu’appareil de réunion dans SkypeEntrepriseOnline. Exécutez l’applet de commande suivante qui active le compte en tant qu’appareil de réunion. 

    ```
    Get-CsTenant | select registrarpool
    Enable-CsMeetingRoom surfacehub2@adatum.com -RegistrarPool  'sippoolbl20a04.infra.lync.com' -SipAddressType UserPrincipalName
    ```
    
    En conséquence de l’exécution de cette applet de commande, il sera demandé aux utilisateurs s’ils se trouvent dans une salle de réunion, comme illustré dans l’image suivante. **Oui** désactivera le microphone et le haut-parleur.

    ![](images/adjust-room-audio.png)


    
Le compte de salle est désormais entièrement configuré, y compris HybridVoice. Si vous utilisez Skype en local, vous pouvez configurer des attributs supplémentaires, comme la description ou l’emplacement, en local. Si vous créez une salle dans SkypeOnline, ces paramètres peuvent être définis en ligne. 

Dans l’image suivante, vous pouvez voir comment l’appareil apparaît aux utilisateurs.


![](images/select-room-hybrid-voice.png)
