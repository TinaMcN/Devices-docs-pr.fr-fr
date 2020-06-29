---
title: Déploiement hybride (Surface Hub)
description: Un déploiement hybride nécessite un traitement spécial afin de configurer un compte d’appareil pour votre MicrosoftSurfaceHub.
ms.assetid: 7BFBB7BE-F587-422E-9CE4-C9DDF829E4F1
ms.reviewer: ''
manager: laurawi
keywords: déploiement hybride, compte d’appareil du SurfaceHub, Exchange hébergé sur site, Exchange hébergé en ligne
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 08/30/2018
ms.localizationpriority: medium
ms.openlocfilehash: 7444c3f31f7a144200a0b8b89cfa509ef7a7afc4
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10833671"
---
# Déploiement hybride (Surface Hub)

Un déploiement hybride nécessite un traitement spécial afin de configurer un compte d’appareil pour votre MicrosoftSurfaceHub. Si vous utilisez un déploiement hybride, dans lequel votre organisation comporte un mélange de services: certains sont hébergés sur site et certains sont hébergés en ligne. Votre configuration dépend donc de l’emplacement où chaque service est hébergé. Cette rubrique traite des déploiements hybrides pour [Exchange hébergé en local](#exchange-on-premises), [Exchange hébergé en ligne](#exchange-online), Skype Entreprise en local, Skype Entreprise Online et Skype Entreprise hybride. Étant donné qu’il existe de nombreuses variantes différentes dans ce type de déploiement, il n’est pas possible de fournir des instructions détaillées pour l’ensemble d’entre elles. Le processus suivant fonctionne pour de nombreuses configurations. Si le processus n’est pas adapté à votre configuration, nous vous recommandons d’utiliser Windows PowerShell (voir [Annexe: PowerShell](appendix-a-powershell-scripts-for-surface-hub.md)) afin d’obtenir le même résultat final que celui documenté ici, et pour d’autres options de déploiement. Vous devez ensuite utiliser le script PowerShell fourni pour vérifier la configuration de votre Surface Hub. (Consultez [Script de vérification de compte](appendix-a-powershell-scripts-for-surface-hub.md#acct-verification-ps-scripts).)

> [!NOTE]
> Dans un environnement Exchange hybride, procédez comme suit pour [Exchange local](#exchange-on-premises). Pour déplacer des objets Exchange vers Office 365, utilisez l’applet [de nouvelle applet de nouveau-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/new-moverequest?view=exchange-ps) .

## Exchange en local

Utilisez cette procédure si vous utilisez Exchange en local.

1. Pour cette procédure, vous allez utiliser les outils d’administration AD pour ajouter une adresse e-mail pour votre compte de domaine local. Ce compte sera synchronisé avec Office 365.

- Dans l’outil AD **Utilisateurs et ordinateurs Active Directory** , cliquez avec le bouton droit sur le dossier ou sur l’unité d’organisation dans lesquels vos comptes Surface Hub seront créés, cliquez sur **Nouveau**, puis sur **Utilisateur**.
- Saisissez le nom d’affichage à partir de l’applet de commande précédente dans le champ **Nom complet** , et l’alias dans le champ **Nom d’ouverture de session de l’utilisateur** . Cliquez sur **Suivant**.<p>

![Nouveau champ d’objet pour la création d’un utilisateur dans Active Directory.](images/hybriddeployment-01a.png)

- Saisissez le mot de passe de ce compte. Vous devez le saisir à nouveau pour la vérification. Assurez-vous que la case **Le mot de passe n’expire jamais** est la seule option sélectionnée.

> **Important** La sélection de la case **Le mot de passe n’expire jamais** est une condition requise pour Skype Entreprise sur le SurfaceHub. Vos règles de domaine risquent d’interdire les mots de passe qui n’expirent pas. Si tel est le cas, vous devez créer une exception pour chaque compte d’appareil Surface Hub.

![Image illustrant la boîte de dialogue pour le mot de passe.](images/hybriddeployment-02a.png)

-   Cliquez sur **Terminer** pour créer le compte.

![Image illustrant le nom du compte, le nom d’ouverture de session et les options de mot de passe pour un nouvel utilisateur.](images/hybriddeployment-03a.png)

2. Activez la boîte aux lettres distante.

Ouvrez votre environnement de ligne de commande Exchange Management Shell local avec les autorisations d’administrateur et exécutez cette applet de commande.

```PowerShell
Enable-RemoteMailbox 'HUB01@contoso.com' -RemoteRoutingAddress 'HUB01@contoso.com' -Room
```

> [!NOTE]
> Si vous n’avez pas d'environnement Exchange local pour exécuter cette applet de commande, vous pouvez apporter les mêmes modifications directement à l’objet ActiveDirectory pour le compte.
>
> msExchRemoteRecipientType = 33
>
> msExchRecipientDisplayType =-2147481850
>
> msExchRecipientTypeDetails = 8589934592

3. Une fois que vous avez créé le compte, exécutez une synchronisation de répertoires. Lorsque vous avez terminé, accédez à la page utilisateurs du centre d’administration Microsoft 365 et vérifiez que le compte créé lors des étapes précédentes a été fusionné en ligne.

4. Connectez-vous à Microsoft Exchange Online et définissez certaines propriétés du compte dans Office365.

Démarrez une session PowerShell à distance sur un PC et connectez-vous à Microsoft Exchange. Assurez-vous de disposer de l’ensemble approprié d’autorisations pour exécuter les applets de commande associées.

Les étapes suivantes seront exécutées sur votre client Office 365.

```PowerShell
Set-ExecutionPolicy RemoteSigned
$cred=Get-Credential -Message "Please use your Office 365 admin credentials"
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri 'https://ps.outlook.com/powershell' -Credential $cred -Authentication Basic -AllowRedirection
Import-PSSession $sess
```

5. Créez une stratégie Exchange ActiveSync ou utilisez une stratégie existante compatible.

Après avoir configuré la boîte aux lettres, vous devez créer une stratégie Exchange ActiveSync ou utiliser une stratégie existante compatible.

Les Surface Hub sont uniquement compatibles avec les comptes d’appareil dotés d’une stratégie ActiveSync, où la propriété **PasswordEnabled** est définie sur False. Si la propriété n’est pas définie correctement, les services Exchange sur le SurfaceHub (courrier, calendrier et accès aux réunions) ne seront pas activés.

Si vous n’avez pas encore créé de stratégie compatible, utilisez l’applet de commande suivante: celle-ci crée une stratégie appelée SurfaceHub. Une fois qu’elle est créée, vous pouvez appliquer la même stratégie à d’autres comptes d’appareil.

```PowerShell
$easPolicy = New-MobileDeviceMailboxPolicy -Name “SurfaceHubs” -PasswordEnabled $false
```

Une fois que vous disposez d’une stratégie compatible, vous devrez l’appliquer au compte de l’appareil. 

```PowerShell
Set-CASMailbox 'HUB01@contoso.com' -ActiveSyncMailboxPolicy $easPolicy.id
```

6. Définissez les propriétés d’Exchange.

La définition de propriétés Exchange sur le compte d’appareil permet d’améliorer l’expérience de réunions. Vous pouvez voir les propriétés qui doivent être définies dans la section [Propriétés Exchange](exchange-properties-for-surface-hub-device-accounts.md) .

```PowerShell
Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse 'This is a Surface Hub room!'
```

7. Connectez-vous à AzureAD.

Vous devez d’abord installer le module Azure AD pour PowerShell version2. Dans une invite PowerShell avec élévation de privilèges, exécutez la commande suivante:

```PowerShell
Install-Module -Name AzureAD
```

Vous devez vous connecter à AzureAD pour appliquer certains paramètres du compte. Vous pouvez exécuter cette applet de commande pour vous connecter.

```PowerShell
Import-Module AzureAD
Connect-AzureAD -Credential $cred
```

8. Affectez une licence Office 365.

Le compte d’appareil doit disposer d’une licence valide Office 365 (O365). Dans le cas contraire, Exchange et Skype Entreprise ne fonctionneront pas. Si vous disposez de la licence, vous devez affecter un emplacement d’utilisation à votre compte d’appareil ; ce paramètre détermine les références de licence qui sont disponibles pour votre compte.

Vous pouvez utiliser `Get-AzureADSubscribedSku` pour récupérer la liste des références (SKU) disponibles pour votre clientO365.

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

Ensuite, vous activez le compte de l’appareil avec [Skype Entreprise Online](#skype-for-business-online), [Skype Entreprise local](#skype-for-business-on-premises) ou [Skype Entreprise hybride](#skype-for-business-hybrid).

### SkypeEntrepriseOnline

Pour activer SkypeEntrepriseOnline, vos utilisateurs clients doivent disposer de boîtes aux lettres Exchange (au moins une boîte aux lettres Exchange pour le client est nécessaire). Le tableau suivant explique les plans ou les services supplémentaires dont vous avez besoin.

| Scénario de système de salle Skype | Si vous avez Office 365 Premium, Microsoft 365 applications pour les entreprises ou plan autonome 2 de Skype entreprise, vous avez besoin des éléments suivants: | Si vous disposez d’un plan d’entreprise, vous devez: | Si vous possédez Skype entreprise Server 2015 (local ou hybride), vous avez besoin des éléments suivants: |
| --- | --- | --- | --- |
| Rejoindre une réunion programmée | Skype Entreprise autonome Plan1 | E1, 3, 4, ou 5 | Licence d'accès client SkypeEntrepriseServer Standard |
| Lancer une réunion ponctuelle | Skype Entreprise autonome Plan2 | E1, 3, 4 ou 5 | Licence d’accès client Skype Entreprise Server ou licence d'accès client Entreprise |
| Lancer une réunion ponctuelle et établir une connexion avec numéros de téléphone depuis une réunion | Plan autonome 2 de Skype entreprise avec audioconférence</br></br>**Remarque** la facturation et de la consommation RTC est facultative | E1 ou E3 avec audioconférence ou E5| Licence d’accès client Skype Entreprise Server ou licence d'accès client Entreprise |
| Affecter à la salle un numéro de téléphone et passer ou recevoir des appels à partir de la salle, ou participer à une conférence téléphonique à l’aide d’un numéro de téléphone | Plan autonome 2 de Skype entreprise avec un système téléphonique et un plan d’appels vocaux RTC | E1 ou E3 avec système téléphonique et un plan d’appels vocaux PSTN ou E5 | Licence d’accès client Skype Entreprise Server ou licence d'accès client Plus |

Le tableau suivant répertorie les plans Office 365 et les options Skype Entreprise.

| Plan O365 | SkypeEntreprise | Système téléphonique | Audioconférence | Offres d’appels |
| --- | --- | --- | --- | --- |
| O365 Business Essentials | Inclus |  |  |  |
| O365 Business Premium | Inclus |  |  |  |
| E1 | Inclus | Extension | Extension | Module complémentaire (nécessite une extension du système téléphonique) |
| E3 | Inclus | Extension | Extension | Module complémentaire (nécessite une extension du système téléphonique) |
| E5 | Inclus | Inclus | Inclus | Extension  |

1. Commencez par créer une session PowerShell à distance à partir d’un PC dans l’environnement Skype Entreprise Online.

```PowerShell
Import-Module SkypeOnlineConnector  
$cssess=New-CsOnlineSession -Credential $cred  
Import-PSSession $cssess -AllowClobber
```

2. Pour activer votre compte Surface Hub pour Skype Entreprise Server, exécutez l’applet de commande suivante:

```PowerShell
Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType UserPrincipalName
```

Si vous n’êtes pas certain de la valeur à utiliser pour le paramètre `RegistrarPool` dans votre environnement, vous pouvez obtenir cette valeur à partir d’un utilisateur Skype Entreprise existant en utilisant l’applet de commande suivante :

```PowerShell
Get-CsOnlineUser -Identity ‘HUB01@contoso.com’| fl *registrarpool*
```

3. Affectez une licence Skype Entreprise à votre compte Surface Hub.

 Une fois que vous avez effectué les étapes précédentes pour activer votre compte Surface Hub dans Skype Entreprise Online, vous devez affecter une licence au Surface Hub. À l’aide du portail d’administration Office 365, vous devez attribuer une licence Skype entreprise Online (plan 2) ou Skype entreprise Online (plan 3) à l’appareil.

- Connectez-vous en tant qu’administrateur client, ouvrez le portail d’administration O365 et cliquez sur l’application Administration.

- Cliquez sur **Utilisateurs et groupes** , puis sur **Ajouter des utilisateurs, réinitialiser des mots de passe, et plus encore**.

- Cliquez sur le compte Surface Hub, puis cliquez sur l’icône en forme de stylet pour modifier les informations de compte.

- Cliquez sur **Licences**.

- Dans **attribution de licences**, sélectionnez Skype entreprise (plan 1) ou Skype entreprise (plan 2), en fonction de vos besoins en matière de gestion des licences et de voix de votre entreprise. Vous devez utiliser une licence plan 2 Si vous souhaitez utiliser Enterprise Voice sur votre surface Hub.

- Cliquez sur **Enregistrer**.

> [!NOTE]
> Vous pouvez également utiliser le Module Windows Azure Active Directory pour Windows PowerShell pour exécuter les applets de commande nécessaires pour affecter l’une de ces licences, mais cette procédure n’est pas abordée ici.

Pour la validation, vous devez être en mesure d’utiliser n’importe quel client Skype Entreprise (PC, Android, etc.) pour vous connecter à ce compte.

### SkypeEntreprise local

Pour exécuter cette applet de commande, vous devez vous connecter à l’un des serveurs frontaux de Skype. Ouvrez Skype PowerShell et exécutez:

```PowerShell
Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool registrarpoolfqdn -SipAddressType UserPrincipalName 
```

### Skype Entreprise hybride

Si votre organisation a configuré la [connectivité hybride entre Skype Entreprise Server et Skype Entreprise Online](https://technet.microsoft.com/library/jj205403.aspx), les instructions concernant la création de comptes différent d’un déploiement standard du Surface Hub.

Le Surface Hub nécessite un compte Skype de type `meetingroom`, tandis qu’un utilisateur normal utiliserait un compte de type utilisateur dans Skype. Si votre serveur Skype est configuré pour un environnement hybride dans lequel vous pouvez disposer d’utilisateurs sur le serveur local de Skype et d’autres hébergés dans Office365, vous pourrez rencontrer quelques problèmes si vous essayez de créer un compte Surface Hub.

Dans l’environnement hybride Skype entreprise Server 2015, chaque utilisateur souhaité dans Skype entreprise Online doit d’abord être créé dans le déploiement local, de sorte que le compte d’utilisateur est créé dans les services de domaine Active Directory (AD FS). Vous pouvez ensuite déplacer l’utilisateur vers Skype entreprise online. Le déplacement d’un compte d’utilisateur de local à en ligne est réalisé via l’applet de [passe Move-Csuser](https://technet.microsoft.com/library/gg398528.aspx) . Pour déplacer un objet Csmeetingroom, utilisez l’applet de [passe Move-Csmeetingroom](https://technet.microsoft.com/library/jj204889.aspx?f=255&mspperror=-2147217396) .

> [!NOTE]
> Pour utiliser l’applet de passe Move-CsMeetingRoom, vous devez avoir installé [la mise à jour cumulative 2017 de Skype entreprise server 2015](https://support.microsoft.com/help/4020991/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p) ou [la mise à jour cumulative 2017 5.0.8308.992 pour Lync Server 2013](https://support.microsoft.com/help/4034279/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p).


## Exchange Online

Utilisez cette procédure si vous utilisez Exchange Online.

1. Créez un compte de messagerie dans Office 365.

Démarrez une session PowerShell à distance sur un PC et connectez-vous à Exchange. Assurez-vous de disposer de l’ensemble approprié d’autorisations pour exécuter les applets de commande associées.

```PowerShell
Set-ExecutionPolicy RemoteSigned
$cred=Get-Credential -Message "Please use your Office 365 admin credentials"
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/PowerShell-liveid/ -Credential $cred -Authentication Basic -AllowRedirection
Import-PSSession $sess
```

2. Configurer une boîte aux lettres.

Une fois une session établie, vous allez créer une boîte aux lettres et l’activer en tant que RoomMailboxAccount, ou vous allez modifier les paramètres d’une boîte aux lettres de salle existante. Cela permettra au compte de s’authentifier sur le SurfaceHub.

Si vous modifiez une boîte aux lettres de ressources existante:

```PowerShell
Set-Mailbox -Identity 'HUB01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

Si vous créez une boîte aux lettres de ressources :

```PowerShell
New-Mailbox -MicrosoftOnlineServicesID 'HUB01@contoso.com' -Alias HUB01 -Name "Hub-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

3. Créez une stratégie Exchange ActiveSync.

Après avoir configuré la boîte aux lettres, vous devez créer une stratégie Exchange ActiveSync ou utiliser une stratégie existante compatible.

Les Surface Hub sont uniquement compatibles avec les comptes d’appareil dotés d’une stratégie ActiveSync, où la propriété **PasswordEnabled** est définie sur False. Si ce n’est pas le cas, les services Exchange sur surface Hub (courrier, calendrier et réunions de participation) ne seront pas activés.

Si vous n’avez pas encore créé de stratégie compatible, utilisez l’applet de commande suivante: celle-ci crée une stratégie appelée SurfaceHub. Une fois qu’elle est créée, vous pouvez appliquer la même stratégie à d’autres comptes d’appareil.

```PowerShell
$easPolicy = New-MobileDeviceMailboxPolicy -Name “SurfaceHubs” -PasswordEnabled $false
```

Une fois que vous disposez d’une stratégie compatible, vous devrez l’appliquer au compte de l’appareil. Toutefois, les stratégies peuvent uniquement être appliquées aux comptes d’utilisateurs et non aux boîtes aux lettres de ressources. Vous devez convertir la boîte aux lettres en un type d’utilisateur, appliquer la stratégie, puis effectuer une nouvelle conversion en boîte aux lettres. Vous devrez peut-être la réactiver et également redéfinir le mot de passe.

```PowerShell
Set-Mailbox 'HUB01@contoso.com' -Type Regular
Set-CASMailbox 'HUB01@contoso.com' -ActiveSyncMailboxPolicy $easPolicy.id
Set-Mailbox 'HUB01@contoso.com' -Type Room
$credNewAccount = Get-Credential -Message "Please provide the Surface Hub username and password"
Set-Mailbox 'HUB01@contoso.com' -RoomMailboxPassword $credNewAccount.Password -EnableRoomMailboxAccount $true
```

4. Définissez les propriétés d’Exchange.

Diverses propriétés Exchange doivent être définies sur le compte d’appareil pour améliorer l’expérience de réunions. Vous pouvez voir les propriétés qui doivent être définies dans la section [Propriétés Exchange](exchange-properties-for-surface-hub-device-accounts.md).

```PowerShell
Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
```

5. Ajoutez une adresse de messagerie pour votre compte de domaine local.

Pour cette procédure, vous allez utiliser les outils d’administration AD pour ajouter une adresse e-mail pour votre compte de domaine local.

- Dans l’outil AD **Utilisateurs et ordinateurs Active Directory** , cliquez avec le bouton droit sur le dossier ou sur l’unité d’organisation dans lesquels vos comptes Surface Hub seront créés, cliquez sur **Nouveau**, puis sur **Utilisateur**.
- Saisissez le nom d’affichage à partir de l’applet de commande précédente dans le champ **Nom complet** , et l’alias dans le champ **Nom d’ouverture de session de l’utilisateur** . Cliquez sur **Suivant**.

![Nouveau champ d’objet pour la création d’un utilisateur dans Active Directory.](images/hybriddeployment-01a.png)

- Saisissez le mot de passe de ce compte. Vous devez le saisir à nouveau pour la vérification. Assurez-vous que la case **Le mot de passe n’expire jamais** est la seule option sélectionnée.

> [!IMPORTANT]
> La sélection du **mot de passe n’expire jamais** est requise pour Skype entreprise sur surface Hub. Vos règles de domaine risquent d’interdire les mots de passe qui n’expirent pas. Si tel est le cas, vous devez créer une exception pour chaque compte d’appareil Surface Hub.

![Image illustrant la boîte de dialogue pour le mot de passe.](images/hybriddeployment-02a.png)

- Cliquez sur **Terminer** pour créer le compte.

![Image illustrant le nom du compte, le nom d’ouverture de session et les options de mot de passe pour un nouvel utilisateur.](images/hybriddeployment-03a.png)

6. Exécutez la synchronisation de répertoires.

Une fois que vous avez créé le compte, exécutez une synchronisation de répertoires. Lorsqu’elle est terminée, accédez à la page Utilisateurs et vérifiez que les deux comptes créés lors des étapes précédentes ont fusionné.

7. Connectez-vous à Azure AD.

Vous devez d’abord installer le module Azure AD pour PowerShell version2. Dans une invite PowerShell avec élévation de privilèges, exécutez la commande suivante:

```PowerShell
Install-Module -Name AzureAD
```

Vous devez vous connecter à AzureAD pour appliquer certains paramètres du compte. Vous pouvez exécuter cette cmdlet pour vous connecter:

```PowerShell
Import-Module AzureAD
Connect-AzureAD -Credential $cred
```

8. Affectez une licence Office 365.

Le compte d’appareil doit disposer d’une licence valide Office 365 (O365). Dans le cas contraire, Exchange et Skype Entreprise ne fonctionneront pas. Si vous disposez de la licence, vous devez affecter un emplacement d’utilisation à votre compte d’appareil ; ce paramètre détermine les références de licence qui sont disponibles pour votre compte.

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

Ensuite, vous activez le compte de l’appareil avec [Skype Entreprise Online](#skype-for-business-online), [Skype Entreprise local](#skype-for-business-on-premises) ou [Skype Entreprise hybride](#skype-for-business-hybrid).

### SkypeEntrepriseOnline

Pour activer SkypeEntreprise, votre environnement doit respecter les [conditions préalables pour Skype Entreprise Online](#skype-for-business-online).

1. Commencez par créer une session PowerShell à distance dans l’environnement Skype Entreprise Online à partir d’un PC.

```PowerShell
Import-Module SkypeOnlineConnector  
$cssess=New-CsOnlineSession -Credential $cred  
Import-PSSession $cssess -AllowClobber
```

2. Pour activer votre compte Surface Hub pour Skype Entreprise Server, exécutez l’applet de commande suivante:

```PowerShell
Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool  
'sippoolbl20a04.infra.lync.com' -SipAddressType UserPrincipalName
```

   Si vous n’êtes pas certain de la valeur à utiliser pour le paramètre `RegistrarPool` dans votre environnement, vous pouvez obtenir cette valeur à partir d’un utilisateur Skype Entreprise existant en utilisant l’applet de commande suivante :

```PowerShell
Get-CsOnlineUser -Identity 'HUB01@contoso.com'| fl *registrarpool*
```

10. Affectez une licence Skype Entreprise à votre compte Surface Hub

Une fois que vous avez effectué les étapes précédentes pour activer votre compte Surface Hub dans Skype Entreprise Online, vous devez affecter une licence au Surface Hub. À l’aide du portail d’administration Office 365, vous devez attribuer une licence Skype entreprise Online (plan 2) ou Skype entreprise Online (plan 3) à l’appareil.

- Connectez-vous en tant qu’administrateur client, ouvrez le portail d’administration O365 et cliquez sur l’application Administration.

- Cliquez sur **Utilisateurs et groupes** , puis sur **Ajouter des utilisateurs, réinitialiser des mots de passe, et plus encore**.

- Cliquez sur le compte Surface Hub, puis cliquez sur l’icône en forme de stylet pour modifier les informations de compte.

- Cliquez sur **Licences**.

- Dans **Affecter des licences**, sélectionnez Skype Entreprise (Plan 2) ou Skype Entreprise (Plan 3), en fonction de vos besoins en matière de licences et de Voix Entreprise. Vous devez utiliser une licence Plan 3 si vous souhaitez utiliser Voix Entreprise sur votre Surface Hub.

- Cliquez sur **Enregistrer**.

> [!NOTE]
> Vous pouvez également utiliser le Module Microsoft Azure Active Directory pour Windows PowerShell pour exécuter les applets de commande nécessaires pour affecter l’une de ces licences, mais cette procédure n’est pas abordée ici.

Pour la validation, vous devez être en mesure d’utiliser n’importe quel client Skype Entreprise (PC, Android, etc.) pour vous connecter à ce compte.

### SkypeEntreprise local

Pour exécuter cette applet de commande, vous devez vous connecter à l’un des serveurs frontaux de Skype. Ouvrez Skype PowerShell et exécutez:

```PowerShell
Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool registrarpoolfqdn -SipAddressType UserPrincipalName 
```

### Skype Entreprise hybride

Si votre organisation a configuré la [connectivité hybride entre Skype Entreprise Server et Skype Entreprise Online](https://technet.microsoft.com/library/jj205403.aspx), les instructions concernant la création de comptes différent d’un déploiement standard du Surface Hub.

Le Surface Hub nécessite un compte Skype de type *meetingroom*, tandis qu’un utilisateur normal utiliserait un compte de type *utilisateur* dans Skype. Si votre serveur Skype est configuré pour un environnement hybride dans lequel vous pouvez disposer d’utilisateurs sur le serveur local de Skype et d’autres hébergés dans Office365, vous pourrez rencontrer quelques problèmes si vous essayez de créer un compte Surface Hub.

Dans l’environnement hybride Skype entreprise Server 2015, chaque utilisateur souhaité dans Skype entreprise Online doit d’abord être créé dans le déploiement local, de sorte que le compte d’utilisateur est créé dans les services de domaine Active Directory (AD FS). Vous pouvez ensuite déplacer l’utilisateur vers Skype entreprise online. Le déplacement d’un compte d’utilisateur de local à en ligne est réalisé via l’applet de [passe Move-Csuser](https://technet.microsoft.com/library/gg398528.aspx) . Pour déplacer un objet Csmeetingroom, utilisez l’applet de [passe Move-Csmeetingroom](https://technet.microsoft.com/library/jj204889.aspx?f=255&mspperror=-2147217396) .

> [!NOTE]
> Pour utiliser l’applet de passe Move-CsMeetingRoom, vous devez avoir installé [la mise à jour cumulative 2017 de Skype entreprise server 2015](https://support.microsoft.com/help/4020991/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p) ou [la mise à jour cumulative 2017 5.0.8308.992 pour Lync Server 2013](https://support.microsoft.com/help/4034279/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p).
