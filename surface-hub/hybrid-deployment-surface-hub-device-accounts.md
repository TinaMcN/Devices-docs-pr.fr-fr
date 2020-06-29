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
# <span data-ttu-id="ce157-104">Déploiement hybride (Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="ce157-104">Hybrid deployment (Surface Hub)</span></span>

<span data-ttu-id="ce157-105">Un déploiement hybride nécessite un traitement spécial afin de configurer un compte d’appareil pour votre MicrosoftSurfaceHub.</span><span class="sxs-lookup"><span data-stu-id="ce157-105">A hybrid deployment requires special processing to set up a device account for your Microsoft Surface Hub.</span></span> <span data-ttu-id="ce157-106">Si vous utilisez un déploiement hybride, dans lequel votre organisation comporte un mélange de services: certains sont hébergés sur site et certains sont hébergés en ligne. Votre configuration dépend donc de l’emplacement où chaque service est hébergé.</span><span class="sxs-lookup"><span data-stu-id="ce157-106">If you’re using a hybrid deployment, in which your organization has a mix of services, with some hosted on-premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="ce157-107">Cette rubrique traite des déploiements hybrides pour [Exchange hébergé en local](#exchange-on-premises), [Exchange hébergé en ligne](#exchange-online), Skype Entreprise en local, Skype Entreprise Online et Skype Entreprise hybride.</span><span class="sxs-lookup"><span data-stu-id="ce157-107">This topic covers hybrid deployments for [Exchange hosted on-premises](#exchange-on-premises), [Exchange hosted online](#exchange-online), Skype for Business on-premises, Skype for Business online, and Skype for Business hybrid.</span></span> <span data-ttu-id="ce157-108">Étant donné qu’il existe de nombreuses variantes différentes dans ce type de déploiement, il n’est pas possible de fournir des instructions détaillées pour l’ensemble d’entre elles.</span><span class="sxs-lookup"><span data-stu-id="ce157-108">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="ce157-109">Le processus suivant fonctionne pour de nombreuses configurations.</span><span class="sxs-lookup"><span data-stu-id="ce157-109">The following process will work for many configurations.</span></span> <span data-ttu-id="ce157-110">Si le processus n’est pas adapté à votre configuration, nous vous recommandons d’utiliser Windows PowerShell (voir [Annexe: PowerShell](appendix-a-powershell-scripts-for-surface-hub.md)) afin d’obtenir le même résultat final que celui documenté ici, et pour d’autres options de déploiement.</span><span class="sxs-lookup"><span data-stu-id="ce157-110">If the process isn't right for your setup, we recommend that you use PowerShell (see [Appendix: PowerShell](appendix-a-powershell-scripts-for-surface-hub.md)) to achieve the same end result as documented here, and for other deployment options.</span></span> <span data-ttu-id="ce157-111">Vous devez ensuite utiliser le script PowerShell fourni pour vérifier la configuration de votre Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="ce157-111">You should then use the provided Powershell script to verify your Surface Hub setup.</span></span> <span data-ttu-id="ce157-112">(Consultez [Script de vérification de compte](appendix-a-powershell-scripts-for-surface-hub.md#acct-verification-ps-scripts).)</span><span class="sxs-lookup"><span data-stu-id="ce157-112">(See [Account Verification Script](appendix-a-powershell-scripts-for-surface-hub.md#acct-verification-ps-scripts).)</span></span>

> [!NOTE]
> <span data-ttu-id="ce157-113">Dans un environnement Exchange hybride, procédez comme suit pour [Exchange local](#exchange-on-premises).</span><span class="sxs-lookup"><span data-stu-id="ce157-113">In an Exchange hybrid environment, follow the steps for [Exchange on-premises](#exchange-on-premises).</span></span> <span data-ttu-id="ce157-114">Pour déplacer des objets Exchange vers Office 365, utilisez l’applet [de nouvelle applet de nouveau-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/new-moverequest?view=exchange-ps) .</span><span class="sxs-lookup"><span data-stu-id="ce157-114">To move Exchange objects to Office 365, use the [New-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/new-moverequest?view=exchange-ps) cmdlet.</span></span>

## <span data-ttu-id="ce157-115">Exchange en local</span><span class="sxs-lookup"><span data-stu-id="ce157-115">Exchange on-premises</span></span>

<span data-ttu-id="ce157-116">Utilisez cette procédure si vous utilisez Exchange en local.</span><span class="sxs-lookup"><span data-stu-id="ce157-116">Use this procedure if you use Exchange on-premises.</span></span>

1. <span data-ttu-id="ce157-117">Pour cette procédure, vous allez utiliser les outils d’administration AD pour ajouter une adresse e-mail pour votre compte de domaine local.</span><span class="sxs-lookup"><span data-stu-id="ce157-117">For this procedure, you'll be using AD admin tools to add an email address for your on-premises domain account.</span></span> <span data-ttu-id="ce157-118">Ce compte sera synchronisé avec Office 365.</span><span class="sxs-lookup"><span data-stu-id="ce157-118">This account will be synced to Office 365.</span></span>

- <span data-ttu-id="ce157-119">Dans l’outil AD **Utilisateurs et ordinateurs Active Directory** , cliquez avec le bouton droit sur le dossier ou sur l’unité d’organisation dans lesquels vos comptes Surface Hub seront créés, cliquez sur **Nouveau**, puis sur **Utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="ce157-119">In **Active Directory Users and Computers** AD tool, right-click on the folder or Organizational Unit that your Surface Hub accounts will be created in, click **New**, and **User**.</span></span>
- <span data-ttu-id="ce157-120">Saisissez le nom d’affichage à partir de l’applet de commande précédente dans le champ **Nom complet** , et l’alias dans le champ **Nom d’ouverture de session de l’utilisateur** .</span><span class="sxs-lookup"><span data-stu-id="ce157-120">Type the display name from the previous cmdlet into the **Full name** box, and the alias into the **User logon name** box.</span></span> <span data-ttu-id="ce157-121">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="ce157-121">Click **Next**.</span></span><p>

![Nouveau champ d’objet pour la création d’un utilisateur dans Active Directory.](images/hybriddeployment-01a.png)

- <span data-ttu-id="ce157-123">Saisissez le mot de passe de ce compte.</span><span class="sxs-lookup"><span data-stu-id="ce157-123">Type the password for this account.</span></span> <span data-ttu-id="ce157-124">Vous devez le saisir à nouveau pour la vérification.</span><span class="sxs-lookup"><span data-stu-id="ce157-124">You'll need to retype it for verification.</span></span> <span data-ttu-id="ce157-125">Assurez-vous que la case **Le mot de passe n’expire jamais** est la seule option sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="ce157-125">Make sure the **Password never expires** checkbox is the only option selected.</span></span>

> <span data-ttu-id="ce157-126">**Important** La sélection de la case **Le mot de passe n’expire jamais** est une condition requise pour Skype Entreprise sur le SurfaceHub.</span><span class="sxs-lookup"><span data-stu-id="ce157-126">**Important** Selecting **Password never expires** is a requirement for Skype for Business on the Surface Hub.</span></span> <span data-ttu-id="ce157-127">Vos règles de domaine risquent d’interdire les mots de passe qui n’expirent pas.</span><span class="sxs-lookup"><span data-stu-id="ce157-127">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="ce157-128">Si tel est le cas, vous devez créer une exception pour chaque compte d’appareil Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="ce157-128">If so, you'll need to create an exception for each Surface Hub device account.</span></span>

![Image illustrant la boîte de dialogue pour le mot de passe.](images/hybriddeployment-02a.png)

-   <span data-ttu-id="ce157-130">Cliquez sur **Terminer** pour créer le compte.</span><span class="sxs-lookup"><span data-stu-id="ce157-130">Click **Finish** to create the account.</span></span>

![Image illustrant le nom du compte, le nom d’ouverture de session et les options de mot de passe pour un nouvel utilisateur.](images/hybriddeployment-03a.png)

2. <span data-ttu-id="ce157-132">Activez la boîte aux lettres distante.</span><span class="sxs-lookup"><span data-stu-id="ce157-132">Enable the remote mailbox.</span></span>

<span data-ttu-id="ce157-133">Ouvrez votre environnement de ligne de commande Exchange Management Shell local avec les autorisations d’administrateur et exécutez cette applet de commande.</span><span class="sxs-lookup"><span data-stu-id="ce157-133">Open your on-premises Exchange Management Shell with administrator permissions, and run this cmdlet.</span></span>

```PowerShell
Enable-RemoteMailbox 'HUB01@contoso.com' -RemoteRoutingAddress 'HUB01@contoso.com' -Room
```

> [!NOTE]
> <span data-ttu-id="ce157-134">Si vous n’avez pas d'environnement Exchange local pour exécuter cette applet de commande, vous pouvez apporter les mêmes modifications directement à l’objet ActiveDirectory pour le compte.</span><span class="sxs-lookup"><span data-stu-id="ce157-134">If you don't have an on-premises Exchange environment to run this cmdlet, you can make the same changes directly to the Active Directory object for the account.</span></span>
>
> <span data-ttu-id="ce157-135">msExchRemoteRecipientType = 33</span><span class="sxs-lookup"><span data-stu-id="ce157-135">msExchRemoteRecipientType = 33</span></span>
>
> <span data-ttu-id="ce157-136">msExchRecipientDisplayType =-2147481850</span><span class="sxs-lookup"><span data-stu-id="ce157-136">msExchRecipientDisplayType = -2147481850</span></span>
>
> <span data-ttu-id="ce157-137">msExchRecipientTypeDetails = 8589934592</span><span class="sxs-lookup"><span data-stu-id="ce157-137">msExchRecipientTypeDetails = 8589934592</span></span>

3. <span data-ttu-id="ce157-138">Une fois que vous avez créé le compte, exécutez une synchronisation de répertoires.</span><span class="sxs-lookup"><span data-stu-id="ce157-138">After you've created the account, run a directory synchronization.</span></span> <span data-ttu-id="ce157-139">Lorsque vous avez terminé, accédez à la page utilisateurs du centre d’administration Microsoft 365 et vérifiez que le compte créé lors des étapes précédentes a été fusionné en ligne.</span><span class="sxs-lookup"><span data-stu-id="ce157-139">When it's complete, go to the users page in your Microsoft 365 admin center and verify that the account created in the previous steps has merged to online.</span></span>

4. <span data-ttu-id="ce157-140">Connectez-vous à Microsoft Exchange Online et définissez certaines propriétés du compte dans Office365.</span><span class="sxs-lookup"><span data-stu-id="ce157-140">Connect to Microsoft Exchange Online and set some properties for the account in Office 365.</span></span>

<span data-ttu-id="ce157-141">Démarrez une session PowerShell à distance sur un PC et connectez-vous à Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="ce157-141">Start a remote PowerShell session on a PC and connect to Microsoft Exchange.</span></span> <span data-ttu-id="ce157-142">Assurez-vous de disposer de l’ensemble approprié d’autorisations pour exécuter les applets de commande associées.</span><span class="sxs-lookup"><span data-stu-id="ce157-142">Be sure you have the right permissions set to run the associated cmdlets.</span></span>

<span data-ttu-id="ce157-143">Les étapes suivantes seront exécutées sur votre client Office 365.</span><span class="sxs-lookup"><span data-stu-id="ce157-143">The next steps will be run on your Office 365 tenant.</span></span>

```PowerShell
Set-ExecutionPolicy RemoteSigned
$cred=Get-Credential -Message "Please use your Office 365 admin credentials"
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri 'https://ps.outlook.com/powershell' -Credential $cred -Authentication Basic -AllowRedirection
Import-PSSession $sess
```

5. <span data-ttu-id="ce157-144">Créez une stratégie Exchange ActiveSync ou utilisez une stratégie existante compatible.</span><span class="sxs-lookup"><span data-stu-id="ce157-144">Create a new Exchange ActiveSync policy, or use a compatible existing policy.</span></span>

<span data-ttu-id="ce157-145">Après avoir configuré la boîte aux lettres, vous devez créer une stratégie Exchange ActiveSync ou utiliser une stratégie existante compatible.</span><span class="sxs-lookup"><span data-stu-id="ce157-145">After setting up the mailbox, you will need to either create a new Exchange ActiveSync policy or use a compatible existing policy.</span></span>

<span data-ttu-id="ce157-146">Les Surface Hub sont uniquement compatibles avec les comptes d’appareil dotés d’une stratégie ActiveSync, où la propriété **PasswordEnabled** est définie sur False.</span><span class="sxs-lookup"><span data-stu-id="ce157-146">Surface Hubs are only compatible with device accounts that have an ActiveSync policy where the **PasswordEnabled** property is set to False.</span></span> <span data-ttu-id="ce157-147">Si la propriété n’est pas définie correctement, les services Exchange sur le SurfaceHub (courrier, calendrier et accès aux réunions) ne seront pas activés.</span><span class="sxs-lookup"><span data-stu-id="ce157-147">If this isn’t set properly, then Exchange services on the Surface Hub (mail, calendar, and joining meetings), will not be enabled.</span></span>

<span data-ttu-id="ce157-148">Si vous n’avez pas encore créé de stratégie compatible, utilisez l’applet de commande suivante: celle-ci crée une stratégie appelée SurfaceHub.</span><span class="sxs-lookup"><span data-stu-id="ce157-148">If you haven’t created a compatible policy yet, use the following cmdlet—this one creates a policy called "Surface Hubs".</span></span> <span data-ttu-id="ce157-149">Une fois qu’elle est créée, vous pouvez appliquer la même stratégie à d’autres comptes d’appareil.</span><span class="sxs-lookup"><span data-stu-id="ce157-149">Once it’s created, you can apply the same policy to other device accounts.</span></span>

```PowerShell
$easPolicy = New-MobileDeviceMailboxPolicy -Name “SurfaceHubs” -PasswordEnabled $false
```

<span data-ttu-id="ce157-150">Une fois que vous disposez d’une stratégie compatible, vous devrez l’appliquer au compte de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="ce157-150">Once you have a compatible policy, you will need to apply the policy to the device account.</span></span> 

```PowerShell
Set-CASMailbox 'HUB01@contoso.com' -ActiveSyncMailboxPolicy $easPolicy.id
```

6. <span data-ttu-id="ce157-151">Définissez les propriétés d’Exchange.</span><span class="sxs-lookup"><span data-stu-id="ce157-151">Set Exchange properties.</span></span>

<span data-ttu-id="ce157-152">La définition de propriétés Exchange sur le compte d’appareil permet d’améliorer l’expérience de réunions.</span><span class="sxs-lookup"><span data-stu-id="ce157-152">Setting Exchange properties on the device account to improve the meeting experience.</span></span> <span data-ttu-id="ce157-153">Vous pouvez voir les propriétés qui doivent être définies dans la section [Propriétés Exchange](exchange-properties-for-surface-hub-device-accounts.md) .</span><span class="sxs-lookup"><span data-stu-id="ce157-153">You can see which properties need to be set in the [Exchange properties](exchange-properties-for-surface-hub-device-accounts.md) section.</span></span>

```PowerShell
Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse 'This is a Surface Hub room!'
```

7. <span data-ttu-id="ce157-154">Connectez-vous à AzureAD.</span><span class="sxs-lookup"><span data-stu-id="ce157-154">Connect to Azure AD.</span></span>

<span data-ttu-id="ce157-155">Vous devez d’abord installer le module Azure AD pour PowerShell version2.</span><span class="sxs-lookup"><span data-stu-id="ce157-155">You first need to install Azure AD module for PowerShell version 2.</span></span> <span data-ttu-id="ce157-156">Dans une invite PowerShell avec élévation de privilèges, exécutez la commande suivante:</span><span class="sxs-lookup"><span data-stu-id="ce157-156">In an elevated PowerShell prompt, run the following command:</span></span>

```PowerShell
Install-Module -Name AzureAD
```

<span data-ttu-id="ce157-157">Vous devez vous connecter à AzureAD pour appliquer certains paramètres du compte.</span><span class="sxs-lookup"><span data-stu-id="ce157-157">You need to connect to Azure AD to apply some account settings.</span></span> <span data-ttu-id="ce157-158">Vous pouvez exécuter cette applet de commande pour vous connecter.</span><span class="sxs-lookup"><span data-stu-id="ce157-158">You can run this cmdlet to connect.</span></span>

```PowerShell
Import-Module AzureAD
Connect-AzureAD -Credential $cred
```

8. <span data-ttu-id="ce157-159">Affectez une licence Office 365.</span><span class="sxs-lookup"><span data-stu-id="ce157-159">Assign an Office 365 license.</span></span>

<span data-ttu-id="ce157-160">Le compte d’appareil doit disposer d’une licence valide Office 365 (O365). Dans le cas contraire, Exchange et Skype Entreprise ne fonctionneront pas.</span><span class="sxs-lookup"><span data-stu-id="ce157-160">The device account needs to have a valid Office 365 (O365) license, or Exchange and Skype for Business will not work.</span></span> <span data-ttu-id="ce157-161">Si vous disposez de la licence, vous devez affecter un emplacement d’utilisation à votre compte d’appareil ; ce paramètre détermine les références de licence qui sont disponibles pour votre compte.</span><span class="sxs-lookup"><span data-stu-id="ce157-161">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span>

<span data-ttu-id="ce157-162">Vous pouvez utiliser `Get-AzureADSubscribedSku` pour récupérer la liste des références (SKU) disponibles pour votre clientO365.</span><span class="sxs-lookup"><span data-stu-id="ce157-162">You can use `Get-AzureADSubscribedSku` to retrieve a list of available SKUs for your O365 tenant.</span></span>

<span data-ttu-id="ce157-163">Une fois que vous avez répertorié les références, vous devez attribuer le SkuId que vous souhaitez à la variable `$License.SkuId`.</span><span class="sxs-lookup"><span data-stu-id="ce157-163">Once you list out the SKUs, you'll need to assign the SkuId you want to the `$License.SkuId` variable.</span></span>

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

<span data-ttu-id="ce157-164">Ensuite, vous activez le compte de l’appareil avec [Skype Entreprise Online](#skype-for-business-online), [Skype Entreprise local](#skype-for-business-on-premises) ou [Skype Entreprise hybride](#skype-for-business-hybrid).</span><span class="sxs-lookup"><span data-stu-id="ce157-164">Next, you enable the device account with [Skype for Business Online](#skype-for-business-online), [Skype for Business on-premises](#skype-for-business-on-premises), or [Skype for Business hybrid](#skype-for-business-hybrid).</span></span>

### <span data-ttu-id="ce157-165">SkypeEntrepriseOnline</span><span class="sxs-lookup"><span data-stu-id="ce157-165">Skype for Business Online</span></span>

<span data-ttu-id="ce157-166">Pour activer SkypeEntrepriseOnline, vos utilisateurs clients doivent disposer de boîtes aux lettres Exchange (au moins une boîte aux lettres Exchange pour le client est nécessaire).</span><span class="sxs-lookup"><span data-stu-id="ce157-166">To enable Skype for Business online, your tenant users must have Exchange mailboxes (at least one Exchange mailbox in the tenant is required).</span></span> <span data-ttu-id="ce157-167">Le tableau suivant explique les plans ou les services supplémentaires dont vous avez besoin.</span><span class="sxs-lookup"><span data-stu-id="ce157-167">The following table explains which plans or additional services you need.</span></span>

| <span data-ttu-id="ce157-168">Scénario de système de salle Skype</span><span class="sxs-lookup"><span data-stu-id="ce157-168">Skype room system scenario</span></span> | <span data-ttu-id="ce157-169">Si vous avez Office 365 Premium, Microsoft 365 applications pour les entreprises ou plan autonome 2 de Skype entreprise, vous avez besoin des éléments suivants:</span><span class="sxs-lookup"><span data-stu-id="ce157-169">If you have Office 365 Premium, Microsoft 365 Apps for enterprise, or Skype for Business Standalone Plan 2, you need:</span></span> | <span data-ttu-id="ce157-170">Si vous disposez d’un plan d’entreprise, vous devez:</span><span class="sxs-lookup"><span data-stu-id="ce157-170">If you have an Enterprise-based plan, you need:</span></span> | <span data-ttu-id="ce157-171">Si vous possédez Skype entreprise Server 2015 (local ou hybride), vous avez besoin des éléments suivants:</span><span class="sxs-lookup"><span data-stu-id="ce157-171">If you have Skype for Business Server 2015 (on-premises or hybrid), you need:</span></span> |
| --- | --- | --- | --- |
| <span data-ttu-id="ce157-172">Rejoindre une réunion programmée</span><span class="sxs-lookup"><span data-stu-id="ce157-172">Join a scheduled meeting</span></span> | <span data-ttu-id="ce157-173">Skype Entreprise autonome Plan1</span><span class="sxs-lookup"><span data-stu-id="ce157-173">Skype for Business Standalone Plan 1</span></span> | <span data-ttu-id="ce157-174">E1, 3, 4, ou 5</span><span class="sxs-lookup"><span data-stu-id="ce157-174">E1, 3, 4, or 5</span></span> | <span data-ttu-id="ce157-175">Licence d'accès client SkypeEntrepriseServer Standard</span><span class="sxs-lookup"><span data-stu-id="ce157-175">Skype for Business Server Standard CAL</span></span> |
| <span data-ttu-id="ce157-176">Lancer une réunion ponctuelle</span><span class="sxs-lookup"><span data-stu-id="ce157-176">Initiate an ad-hoc meeting</span></span> | <span data-ttu-id="ce157-177">Skype Entreprise autonome Plan2</span><span class="sxs-lookup"><span data-stu-id="ce157-177">Skype for Business Standalone Plan 2</span></span> | <span data-ttu-id="ce157-178">E1, 3, 4 ou 5</span><span class="sxs-lookup"><span data-stu-id="ce157-178">E 1, 3, 4, or 5</span></span> | <span data-ttu-id="ce157-179">Licence d’accès client Skype Entreprise Server ou licence d'accès client Entreprise</span><span class="sxs-lookup"><span data-stu-id="ce157-179">Skype for Business Server Standard CAL or Enterprise CAL</span></span> |
| <span data-ttu-id="ce157-180">Lancer une réunion ponctuelle et établir une connexion avec numéros de téléphone depuis une réunion</span><span class="sxs-lookup"><span data-stu-id="ce157-180">Initiate an ad-hoc meeting and dial out from a meeting to phone numbers</span></span> | <span data-ttu-id="ce157-181">Plan autonome 2 de Skype entreprise avec audioconférence</span><span class="sxs-lookup"><span data-stu-id="ce157-181">Skype for Business Standalone Plan 2 with Audio Conferencing</span></span></br></br><span data-ttu-id="ce157-182">**Remarque** la facturation et de la consommation RTC est facultative</span><span class="sxs-lookup"><span data-stu-id="ce157-182">**Note** PSTN consumption billing is optional</span></span> | <span data-ttu-id="ce157-183">E1 ou E3 avec audioconférence ou E5</span><span class="sxs-lookup"><span data-stu-id="ce157-183">E1 or E3 with Audio Conferencing, or E5</span></span>| <span data-ttu-id="ce157-184">Licence d’accès client Skype Entreprise Server ou licence d'accès client Entreprise</span><span class="sxs-lookup"><span data-stu-id="ce157-184">Skype for Business Server Standard CAL or Enterprise CAL</span></span> |
| <span data-ttu-id="ce157-185">Affecter à la salle un numéro de téléphone et passer ou recevoir des appels à partir de la salle, ou participer à une conférence téléphonique à l’aide d’un numéro de téléphone</span><span class="sxs-lookup"><span data-stu-id="ce157-185">Give the room a phone number and make or receive calls from the room or join a dial-in conference using a phone number</span></span> | <span data-ttu-id="ce157-186">Plan autonome 2 de Skype entreprise avec un système téléphonique et un plan d’appels vocaux RTC</span><span class="sxs-lookup"><span data-stu-id="ce157-186">Skype for Business Standalone Plan 2 with Phone System and a PSTN Voice Calling plan</span></span> | <span data-ttu-id="ce157-187">E1 ou E3 avec système téléphonique et un plan d’appels vocaux PSTN ou E5</span><span class="sxs-lookup"><span data-stu-id="ce157-187">E1 or E3 with Phone System and a PSTN Voice Calling plan, or E5</span></span> | <span data-ttu-id="ce157-188">Licence d’accès client Skype Entreprise Server ou licence d'accès client Plus</span><span class="sxs-lookup"><span data-stu-id="ce157-188">Skype for Business Server Standard CAL or Plus CAL</span></span> |

<span data-ttu-id="ce157-189">Le tableau suivant répertorie les plans Office 365 et les options Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="ce157-189">The following table lists the Office 365 plans and Skype for Business options.</span></span>

| <span data-ttu-id="ce157-190">Plan O365</span><span class="sxs-lookup"><span data-stu-id="ce157-190">O365 Plan</span></span> | <span data-ttu-id="ce157-191">SkypeEntreprise</span><span class="sxs-lookup"><span data-stu-id="ce157-191">Skype for Business</span></span> | <span data-ttu-id="ce157-192">Système téléphonique</span><span class="sxs-lookup"><span data-stu-id="ce157-192">Phone System</span></span> | <span data-ttu-id="ce157-193">Audioconférence</span><span class="sxs-lookup"><span data-stu-id="ce157-193">Audio Conferencing</span></span> | <span data-ttu-id="ce157-194">Offres d’appels</span><span class="sxs-lookup"><span data-stu-id="ce157-194">Calling Plans</span></span> |
| --- | --- | --- | --- | --- |
| <span data-ttu-id="ce157-195">O365 Business Essentials</span><span class="sxs-lookup"><span data-stu-id="ce157-195">O365 Business Essentials</span></span> | <span data-ttu-id="ce157-196">Inclus</span><span class="sxs-lookup"><span data-stu-id="ce157-196">Included</span></span> |  |  |  |
| <span data-ttu-id="ce157-197">O365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="ce157-197">O365 Business Premium</span></span> | <span data-ttu-id="ce157-198">Inclus</span><span class="sxs-lookup"><span data-stu-id="ce157-198">Included</span></span> |  |  |  |
| <span data-ttu-id="ce157-199">E1</span><span class="sxs-lookup"><span data-stu-id="ce157-199">E1</span></span> | <span data-ttu-id="ce157-200">Inclus</span><span class="sxs-lookup"><span data-stu-id="ce157-200">Included</span></span> | <span data-ttu-id="ce157-201">Extension</span><span class="sxs-lookup"><span data-stu-id="ce157-201">Add-on</span></span> | <span data-ttu-id="ce157-202">Extension</span><span class="sxs-lookup"><span data-stu-id="ce157-202">Add-on</span></span> | <span data-ttu-id="ce157-203">Module complémentaire (nécessite une extension du système téléphonique)</span><span class="sxs-lookup"><span data-stu-id="ce157-203">Add-on (requires Phone System add-on)</span></span> |
| <span data-ttu-id="ce157-204">E3</span><span class="sxs-lookup"><span data-stu-id="ce157-204">E3</span></span> | <span data-ttu-id="ce157-205">Inclus</span><span class="sxs-lookup"><span data-stu-id="ce157-205">Included</span></span> | <span data-ttu-id="ce157-206">Extension</span><span class="sxs-lookup"><span data-stu-id="ce157-206">Add-on</span></span> | <span data-ttu-id="ce157-207">Extension</span><span class="sxs-lookup"><span data-stu-id="ce157-207">Add-on</span></span> | <span data-ttu-id="ce157-208">Module complémentaire (nécessite une extension du système téléphonique)</span><span class="sxs-lookup"><span data-stu-id="ce157-208">Add-on (requires Phone System add-on)</span></span> |
| <span data-ttu-id="ce157-209">E5</span><span class="sxs-lookup"><span data-stu-id="ce157-209">E5</span></span> | <span data-ttu-id="ce157-210">Inclus</span><span class="sxs-lookup"><span data-stu-id="ce157-210">Included</span></span> | <span data-ttu-id="ce157-211">Inclus</span><span class="sxs-lookup"><span data-stu-id="ce157-211">Included</span></span> | <span data-ttu-id="ce157-212">Inclus</span><span class="sxs-lookup"><span data-stu-id="ce157-212">Included</span></span> | <span data-ttu-id="ce157-213">Extension</span><span class="sxs-lookup"><span data-stu-id="ce157-213">Add-on</span></span>  |

1. <span data-ttu-id="ce157-214">Commencez par créer une session PowerShell à distance à partir d’un PC dans l’environnement Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="ce157-214">Start by creating a remote PowerShell session from a PC to the Skype for Business online environment.</span></span>

```PowerShell
Import-Module SkypeOnlineConnector  
$cssess=New-CsOnlineSession -Credential $cred  
Import-PSSession $cssess -AllowClobber
```

2. <span data-ttu-id="ce157-215">Pour activer votre compte Surface Hub pour Skype Entreprise Server, exécutez l’applet de commande suivante:</span><span class="sxs-lookup"><span data-stu-id="ce157-215">To enable your Surface Hub account for Skype for Business Server, run this cmdlet:</span></span>

```PowerShell
Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType UserPrincipalName
```

<span data-ttu-id="ce157-216">Si vous n’êtes pas certain de la valeur à utiliser pour le paramètre `RegistrarPool` dans votre environnement, vous pouvez obtenir cette valeur à partir d’un utilisateur Skype Entreprise existant en utilisant l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="ce157-216">If you aren't sure what value to use for the `RegistrarPool` parameter in your environment, you can get the value from an existing Skype for Business user using this cmdlet:</span></span>

```PowerShell
Get-CsOnlineUser -Identity ‘HUB01@contoso.com’| fl *registrarpool*
```

3. <span data-ttu-id="ce157-217">Affectez une licence Skype Entreprise à votre compte Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="ce157-217">Assign Skype for Business license to your Surface Hub account.</span></span>

 <span data-ttu-id="ce157-218">Une fois que vous avez effectué les étapes précédentes pour activer votre compte Surface Hub dans Skype Entreprise Online, vous devez affecter une licence au Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="ce157-218">Once you've completed the preceding steps to enable your Surface Hub account in Skype for Business Online, you need to assign a license to the Surface Hub.</span></span> <span data-ttu-id="ce157-219">À l’aide du portail d’administration Office 365, vous devez attribuer une licence Skype entreprise Online (plan 2) ou Skype entreprise Online (plan 3) à l’appareil.</span><span class="sxs-lookup"><span data-stu-id="ce157-219">Using the O365 administrative portal, assign either a Skype for Business Online (Plan 2) or a Skype for Business Online (Plan 3) license to the device.</span></span>

- <span data-ttu-id="ce157-220">Connectez-vous en tant qu’administrateur client, ouvrez le portail d’administration O365 et cliquez sur l’application Administration.</span><span class="sxs-lookup"><span data-stu-id="ce157-220">Login as a tenant administrator, open the O365 Administrative Portal, and click on the Admin app.</span></span>

- <span data-ttu-id="ce157-221">Cliquez sur **Utilisateurs et groupes** , puis sur **Ajouter des utilisateurs, réinitialiser des mots de passe, et plus encore**.</span><span class="sxs-lookup"><span data-stu-id="ce157-221">Click on **Users and Groups** and then **Add users, reset passwords, and more**.</span></span>

- <span data-ttu-id="ce157-222">Cliquez sur le compte Surface Hub, puis cliquez sur l’icône en forme de stylet pour modifier les informations de compte.</span><span class="sxs-lookup"><span data-stu-id="ce157-222">Click the Surface Hub account, and then click the pen icon to edit the account information.</span></span>

- <span data-ttu-id="ce157-223">Cliquez sur **Licences**.</span><span class="sxs-lookup"><span data-stu-id="ce157-223">Click **Licenses**.</span></span>

- <span data-ttu-id="ce157-224">Dans **attribution de licences**, sélectionnez Skype entreprise (plan 1) ou Skype entreprise (plan 2), en fonction de vos besoins en matière de gestion des licences et de voix de votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="ce157-224">In **Assign licenses**, select Skype for Business (Plan 1) or Skype for Business (Plan 2), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="ce157-225">Vous devez utiliser une licence plan 2 Si vous souhaitez utiliser Enterprise Voice sur votre surface Hub.</span><span class="sxs-lookup"><span data-stu-id="ce157-225">You'll have to use a Plan 2 license if you want to use Enterprise Voice on your Surface Hub.</span></span>

- <span data-ttu-id="ce157-226">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="ce157-226">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="ce157-227">Vous pouvez également utiliser le Module Windows Azure Active Directory pour Windows PowerShell pour exécuter les applets de commande nécessaires pour affecter l’une de ces licences, mais cette procédure n’est pas abordée ici.</span><span class="sxs-lookup"><span data-stu-id="ce157-227">You can also use the Windows Azure Active Directory Module for Windows Powershell to run the cmdlets needed to assign one of these licenses, but that's not covered here.</span></span>

<span data-ttu-id="ce157-228">Pour la validation, vous devez être en mesure d’utiliser n’importe quel client Skype Entreprise (PC, Android, etc.) pour vous connecter à ce compte.</span><span class="sxs-lookup"><span data-stu-id="ce157-228">For validation, you should be able to use any Skype for Business client (PC, Android, etc.) to sign in to this account.</span></span>

### <span data-ttu-id="ce157-229">SkypeEntreprise local</span><span class="sxs-lookup"><span data-stu-id="ce157-229">Skype for Business on-premises</span></span>

<span data-ttu-id="ce157-230">Pour exécuter cette applet de commande, vous devez vous connecter à l’un des serveurs frontaux de Skype.</span><span class="sxs-lookup"><span data-stu-id="ce157-230">To run this cmdlet, you will need to connect to one of the Skype front-ends.</span></span> <span data-ttu-id="ce157-231">Ouvrez Skype PowerShell et exécutez:</span><span class="sxs-lookup"><span data-stu-id="ce157-231">Open the Skype PowerShell and run:</span></span>

```PowerShell
Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool registrarpoolfqdn -SipAddressType UserPrincipalName 
```

### <span data-ttu-id="ce157-232">Skype Entreprise hybride</span><span class="sxs-lookup"><span data-stu-id="ce157-232">Skype for Business hybrid</span></span>

<span data-ttu-id="ce157-233">Si votre organisation a configuré la [connectivité hybride entre Skype Entreprise Server et Skype Entreprise Online](https://technet.microsoft.com/library/jj205403.aspx), les instructions concernant la création de comptes différent d’un déploiement standard du Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="ce157-233">If your organization has set up [hybrid connectivity between Skype for Business Server and Skype for Business Online](https://technet.microsoft.com/library/jj205403.aspx), the guidance for creating accounts differs from a standard Surface Hub deployment.</span></span>

<span data-ttu-id="ce157-234">Le Surface Hub nécessite un compte Skype de type `meetingroom`, tandis qu’un utilisateur normal utiliserait un compte de type utilisateur dans Skype.</span><span class="sxs-lookup"><span data-stu-id="ce157-234">The Surface Hub requires a Skype account of the type `meetingroom`, while a normal user would use a user type account in Skype.</span></span> <span data-ttu-id="ce157-235">Si votre serveur Skype est configuré pour un environnement hybride dans lequel vous pouvez disposer d’utilisateurs sur le serveur local de Skype et d’autres hébergés dans Office365, vous pourrez rencontrer quelques problèmes si vous essayez de créer un compte Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="ce157-235">If your Skype server is set up for hybrid where you might have users on the local Skype server as well as users hosted in Office 365, you might run into a few issues when trying to create a Surface Hub account.</span></span>

<span data-ttu-id="ce157-236">Dans l’environnement hybride Skype entreprise Server 2015, chaque utilisateur souhaité dans Skype entreprise Online doit d’abord être créé dans le déploiement local, de sorte que le compte d’utilisateur est créé dans les services de domaine Active Directory (AD FS).</span><span class="sxs-lookup"><span data-stu-id="ce157-236">In Skype for Business Server 2015 hybrid environment, any user that you want in Skype for Business Online must first be created in the on-premises deployment, so that the user account is created in Active Directory Domain Services.</span></span> <span data-ttu-id="ce157-237">Vous pouvez ensuite déplacer l’utilisateur vers Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="ce157-237">You can then move the user to Skype for Business Online.</span></span> <span data-ttu-id="ce157-238">Le déplacement d’un compte d’utilisateur de local à en ligne est réalisé via l’applet de [passe Move-Csuser](https://technet.microsoft.com/library/gg398528.aspx) .</span><span class="sxs-lookup"><span data-stu-id="ce157-238">The move of a user account from on-premises to online is done via the [Move-CsUser](https://technet.microsoft.com/library/gg398528.aspx) cmdlet.</span></span> <span data-ttu-id="ce157-239">Pour déplacer un objet Csmeetingroom, utilisez l’applet de [passe Move-Csmeetingroom](https://technet.microsoft.com/library/jj204889.aspx?f=255&mspperror=-2147217396) .</span><span class="sxs-lookup"><span data-stu-id="ce157-239">To move a Csmeetingroom object, use the [Move-CsMeetingRoom](https://technet.microsoft.com/library/jj204889.aspx?f=255&mspperror=-2147217396) cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="ce157-240">Pour utiliser l’applet de passe Move-CsMeetingRoom, vous devez avoir installé [la mise à jour cumulative 2017 de Skype entreprise server 2015](https://support.microsoft.com/help/4020991/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p) ou [la mise à jour cumulative 2017 5.0.8308.992 pour Lync Server 2013](https://support.microsoft.com/help/4034279/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p).</span><span class="sxs-lookup"><span data-stu-id="ce157-240">To use the Move-CsMeetingRoom cmdlet, you must have installed [the May 2017 cumulative update 6.0.9319.281 for Skype for Business Server 2015](https://support.microsoft.com/help/4020991/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p) or [the July 2017 cumulative update 5.0.8308.992 for Lync Server 2013](https://support.microsoft.com/help/4034279/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p).</span></span>


## <span data-ttu-id="ce157-241">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="ce157-241">Exchange online</span></span>

<span data-ttu-id="ce157-242">Utilisez cette procédure si vous utilisez Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="ce157-242">Use this procedure if you use Exchange online.</span></span>

1. <span data-ttu-id="ce157-243">Créez un compte de messagerie dans Office 365.</span><span class="sxs-lookup"><span data-stu-id="ce157-243">Create an email account in Office 365.</span></span>

<span data-ttu-id="ce157-244">Démarrez une session PowerShell à distance sur un PC et connectez-vous à Exchange.</span><span class="sxs-lookup"><span data-stu-id="ce157-244">Start a remote PowerShell session on a PC and connect to Exchange.</span></span> <span data-ttu-id="ce157-245">Assurez-vous de disposer de l’ensemble approprié d’autorisations pour exécuter les applets de commande associées.</span><span class="sxs-lookup"><span data-stu-id="ce157-245">Be sure you have the right permissions set to run the associated cmdlets.</span></span>

```PowerShell
Set-ExecutionPolicy RemoteSigned
$cred=Get-Credential -Message "Please use your Office 365 admin credentials"
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/PowerShell-liveid/ -Credential $cred -Authentication Basic -AllowRedirection
Import-PSSession $sess
```

2. <span data-ttu-id="ce157-246">Configurer une boîte aux lettres.</span><span class="sxs-lookup"><span data-stu-id="ce157-246">Set up a mailbox.</span></span>

<span data-ttu-id="ce157-247">Une fois une session établie, vous allez créer une boîte aux lettres et l’activer en tant que RoomMailboxAccount, ou vous allez modifier les paramètres d’une boîte aux lettres de salle existante.</span><span class="sxs-lookup"><span data-stu-id="ce157-247">After establishing a session, you’ll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="ce157-248">Cela permettra au compte de s’authentifier sur le SurfaceHub.</span><span class="sxs-lookup"><span data-stu-id="ce157-248">This will allow the account to authenticate into the Surface Hub.</span></span>

<span data-ttu-id="ce157-249">Si vous modifiez une boîte aux lettres de ressources existante:</span><span class="sxs-lookup"><span data-stu-id="ce157-249">If you're changing an existing resource mailbox:</span></span>

```PowerShell
Set-Mailbox -Identity 'HUB01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

<span data-ttu-id="ce157-250">Si vous créez une boîte aux lettres de ressources :</span><span class="sxs-lookup"><span data-stu-id="ce157-250">If you’re creating a new resource mailbox:</span></span>

```PowerShell
New-Mailbox -MicrosoftOnlineServicesID 'HUB01@contoso.com' -Alias HUB01 -Name "Hub-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

3. <span data-ttu-id="ce157-251">Créez une stratégie Exchange ActiveSync.</span><span class="sxs-lookup"><span data-stu-id="ce157-251">Create Exchange ActiveSync policy.</span></span>

<span data-ttu-id="ce157-252">Après avoir configuré la boîte aux lettres, vous devez créer une stratégie Exchange ActiveSync ou utiliser une stratégie existante compatible.</span><span class="sxs-lookup"><span data-stu-id="ce157-252">After setting up the mailbox, you will need to either create a new Exchange ActiveSync policy, or use a compatible existing policy.</span></span>

<span data-ttu-id="ce157-253">Les Surface Hub sont uniquement compatibles avec les comptes d’appareil dotés d’une stratégie ActiveSync, où la propriété **PasswordEnabled** est définie sur False.</span><span class="sxs-lookup"><span data-stu-id="ce157-253">Surface Hubs are only compatible with device accounts that have an ActiveSync policy where the **PasswordEnabled** property is set to False.</span></span> <span data-ttu-id="ce157-254">Si ce n’est pas le cas, les services Exchange sur surface Hub (courrier, calendrier et réunions de participation) ne seront pas activés.</span><span class="sxs-lookup"><span data-stu-id="ce157-254">If this isn’t set properly, Exchange services on the Surface Hub (mail, calendar, and joining meetings) will not be enabled.</span></span>

<span data-ttu-id="ce157-255">Si vous n’avez pas encore créé de stratégie compatible, utilisez l’applet de commande suivante: celle-ci crée une stratégie appelée SurfaceHub.</span><span class="sxs-lookup"><span data-stu-id="ce157-255">If you haven’t created a compatible policy yet, use the following cmdlet—this one creates a policy called "Surface Hubs".</span></span> <span data-ttu-id="ce157-256">Une fois qu’elle est créée, vous pouvez appliquer la même stratégie à d’autres comptes d’appareil.</span><span class="sxs-lookup"><span data-stu-id="ce157-256">Once it’s created, you can apply the same policy to other device accounts.</span></span>

```PowerShell
$easPolicy = New-MobileDeviceMailboxPolicy -Name “SurfaceHubs” -PasswordEnabled $false
```

<span data-ttu-id="ce157-257">Une fois que vous disposez d’une stratégie compatible, vous devrez l’appliquer au compte de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="ce157-257">Once you have a compatible policy, you will need to apply the policy to the device account.</span></span> <span data-ttu-id="ce157-258">Toutefois, les stratégies peuvent uniquement être appliquées aux comptes d’utilisateurs et non aux boîtes aux lettres de ressources.</span><span class="sxs-lookup"><span data-stu-id="ce157-258">However, policies can only be applied to user accounts and not resource mailboxes.</span></span> <span data-ttu-id="ce157-259">Vous devez convertir la boîte aux lettres en un type d’utilisateur, appliquer la stratégie, puis effectuer une nouvelle conversion en boîte aux lettres. Vous devrez peut-être la réactiver et également redéfinir le mot de passe.</span><span class="sxs-lookup"><span data-stu-id="ce157-259">You need to convert the mailbox into a user type, apply the policy, and then convert it back into a mailbox—you may need to re-enable it and set the password again too.</span></span>

```PowerShell
Set-Mailbox 'HUB01@contoso.com' -Type Regular
Set-CASMailbox 'HUB01@contoso.com' -ActiveSyncMailboxPolicy $easPolicy.id
Set-Mailbox 'HUB01@contoso.com' -Type Room
$credNewAccount = Get-Credential -Message "Please provide the Surface Hub username and password"
Set-Mailbox 'HUB01@contoso.com' -RoomMailboxPassword $credNewAccount.Password -EnableRoomMailboxAccount $true
```

4. <span data-ttu-id="ce157-260">Définissez les propriétés d’Exchange.</span><span class="sxs-lookup"><span data-stu-id="ce157-260">Set Exchange properties.</span></span>

<span data-ttu-id="ce157-261">Diverses propriétés Exchange doivent être définies sur le compte d’appareil pour améliorer l’expérience de réunions.</span><span class="sxs-lookup"><span data-stu-id="ce157-261">Various Exchange properties must be set on the device account to improve the meeting experience.</span></span> <span data-ttu-id="ce157-262">Vous pouvez voir les propriétés qui doivent être définies dans la section [Propriétés Exchange](exchange-properties-for-surface-hub-device-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="ce157-262">You can see which properties need to be set in the [Exchange properties](exchange-properties-for-surface-hub-device-accounts.md) section.</span></span>

```PowerShell
Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
```

5. <span data-ttu-id="ce157-263">Ajoutez une adresse de messagerie pour votre compte de domaine local.</span><span class="sxs-lookup"><span data-stu-id="ce157-263">Add an email address for your on-premises domain account.</span></span>

<span data-ttu-id="ce157-264">Pour cette procédure, vous allez utiliser les outils d’administration AD pour ajouter une adresse e-mail pour votre compte de domaine local.</span><span class="sxs-lookup"><span data-stu-id="ce157-264">For this procedure, you'll be using AD admin tools to add an email address for your on-premises domain account.</span></span>

- <span data-ttu-id="ce157-265">Dans l’outil AD **Utilisateurs et ordinateurs Active Directory** , cliquez avec le bouton droit sur le dossier ou sur l’unité d’organisation dans lesquels vos comptes Surface Hub seront créés, cliquez sur **Nouveau**, puis sur **Utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="ce157-265">In **Active Directory Users and Computers** AD tool, right-click on the folder or Organizational Unit that your Surface Hub accounts will be created in, click **New**, and **User**.</span></span>
- <span data-ttu-id="ce157-266">Saisissez le nom d’affichage à partir de l’applet de commande précédente dans le champ **Nom complet** , et l’alias dans le champ **Nom d’ouverture de session de l’utilisateur** .</span><span class="sxs-lookup"><span data-stu-id="ce157-266">Type the display name from the previous cmdlet into the **Full name** box, and the alias into the **User logon name** box.</span></span> <span data-ttu-id="ce157-267">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="ce157-267">Click **Next**.</span></span>

![Nouveau champ d’objet pour la création d’un utilisateur dans Active Directory.](images/hybriddeployment-01a.png)

- <span data-ttu-id="ce157-269">Saisissez le mot de passe de ce compte.</span><span class="sxs-lookup"><span data-stu-id="ce157-269">Type the password for this account.</span></span> <span data-ttu-id="ce157-270">Vous devez le saisir à nouveau pour la vérification.</span><span class="sxs-lookup"><span data-stu-id="ce157-270">You'll need to retype it for verification.</span></span> <span data-ttu-id="ce157-271">Assurez-vous que la case **Le mot de passe n’expire jamais** est la seule option sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="ce157-271">Make sure the **Password never expires** checkbox is the only option selected.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ce157-272">La sélection du **mot de passe n’expire jamais** est requise pour Skype entreprise sur surface Hub.</span><span class="sxs-lookup"><span data-stu-id="ce157-272">Selecting **Password never expires** is a requirement for Skype for Business on the Surface Hub.</span></span> <span data-ttu-id="ce157-273">Vos règles de domaine risquent d’interdire les mots de passe qui n’expirent pas.</span><span class="sxs-lookup"><span data-stu-id="ce157-273">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="ce157-274">Si tel est le cas, vous devez créer une exception pour chaque compte d’appareil Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="ce157-274">If so, you'll need to create an exception for each Surface Hub device account.</span></span>

![Image illustrant la boîte de dialogue pour le mot de passe.](images/hybriddeployment-02a.png)

- <span data-ttu-id="ce157-276">Cliquez sur **Terminer** pour créer le compte.</span><span class="sxs-lookup"><span data-stu-id="ce157-276">Click **Finish** to create the account.</span></span>

![Image illustrant le nom du compte, le nom d’ouverture de session et les options de mot de passe pour un nouvel utilisateur.](images/hybriddeployment-03a.png)

6. <span data-ttu-id="ce157-278">Exécutez la synchronisation de répertoires.</span><span class="sxs-lookup"><span data-stu-id="ce157-278">Run directory synchronization.</span></span>

<span data-ttu-id="ce157-279">Une fois que vous avez créé le compte, exécutez une synchronisation de répertoires.</span><span class="sxs-lookup"><span data-stu-id="ce157-279">After you've created the account, run a directory synchronization.</span></span> <span data-ttu-id="ce157-280">Lorsqu’elle est terminée, accédez à la page Utilisateurs et vérifiez que les deux comptes créés lors des étapes précédentes ont fusionné.</span><span class="sxs-lookup"><span data-stu-id="ce157-280">When it's complete, go to the users page and verify that the two accounts created in the previous steps have merged.</span></span>

7. <span data-ttu-id="ce157-281">Connectez-vous à Azure AD.</span><span class="sxs-lookup"><span data-stu-id="ce157-281">Connect to Azure AD.</span></span>

<span data-ttu-id="ce157-282">Vous devez d’abord installer le module Azure AD pour PowerShell version2.</span><span class="sxs-lookup"><span data-stu-id="ce157-282">You first need to install Azure AD module for PowerShell version 2.</span></span> <span data-ttu-id="ce157-283">Dans une invite PowerShell avec élévation de privilèges, exécutez la commande suivante:</span><span class="sxs-lookup"><span data-stu-id="ce157-283">In an elevated PowerShell prompt, run the following command:</span></span>

```PowerShell
Install-Module -Name AzureAD
```

<span data-ttu-id="ce157-284">Vous devez vous connecter à AzureAD pour appliquer certains paramètres du compte.</span><span class="sxs-lookup"><span data-stu-id="ce157-284">You need to connect to Azure AD to apply some account settings.</span></span> <span data-ttu-id="ce157-285">Vous pouvez exécuter cette cmdlet pour vous connecter:</span><span class="sxs-lookup"><span data-stu-id="ce157-285">You can run this cmdlet to connect:</span></span>

```PowerShell
Import-Module AzureAD
Connect-AzureAD -Credential $cred
```

8. <span data-ttu-id="ce157-286">Affectez une licence Office 365.</span><span class="sxs-lookup"><span data-stu-id="ce157-286">Assign an Office 365 license.</span></span>

<span data-ttu-id="ce157-287">Le compte d’appareil doit disposer d’une licence valide Office 365 (O365). Dans le cas contraire, Exchange et Skype Entreprise ne fonctionneront pas.</span><span class="sxs-lookup"><span data-stu-id="ce157-287">The device account needs to have a valid Office 365 (O365) license, or Exchange and Skype for Business will not work.</span></span> <span data-ttu-id="ce157-288">Si vous disposez de la licence, vous devez affecter un emplacement d’utilisation à votre compte d’appareil ; ce paramètre détermine les références de licence qui sont disponibles pour votre compte.</span><span class="sxs-lookup"><span data-stu-id="ce157-288">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span>

<span data-ttu-id="ce157-289">Ensuite, vous pouvez utiliser `Get-AzureADSubscribedSku` pour récupérer la liste des références (SKU) disponibles pour votre clientO365.</span><span class="sxs-lookup"><span data-stu-id="ce157-289">Next, you can use `Get-AzureADSubscribedSku` to retrieve a list of available SKUs for your O365 tenant.</span></span>

<span data-ttu-id="ce157-290">Une fois que vous avez répertorié les références, vous devez attribuer le SkuId que vous souhaitez à la variable `$License.SkuId`.</span><span class="sxs-lookup"><span data-stu-id="ce157-290">Once you list out the SKUs, you'll need to assign the SkuId you want to the `$License.SkuId` variable.</span></span>

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

<span data-ttu-id="ce157-291">Ensuite, vous activez le compte de l’appareil avec [Skype Entreprise Online](#skype-for-business-online), [Skype Entreprise local](#skype-for-business-on-premises) ou [Skype Entreprise hybride](#skype-for-business-hybrid).</span><span class="sxs-lookup"><span data-stu-id="ce157-291">Next, you enable the device account with [Skype for Business Online](#skype-for-business-online), [Skype for Business on-premises](#skype-for-business-on-premises), or [Skype for Business hybrid](#skype-for-business-hybrid).</span></span>

### <span data-ttu-id="ce157-292">SkypeEntrepriseOnline</span><span class="sxs-lookup"><span data-stu-id="ce157-292">Skype for Business Online</span></span>

<span data-ttu-id="ce157-293">Pour activer SkypeEntreprise, votre environnement doit respecter les [conditions préalables pour Skype Entreprise Online](#skype-for-business-online).</span><span class="sxs-lookup"><span data-stu-id="ce157-293">In order to enable Skype for Business, your environment will need to meet the [prerequisites for Skype for Business online](#skype-for-business-online).</span></span>

1. <span data-ttu-id="ce157-294">Commencez par créer une session PowerShell à distance dans l’environnement Skype Entreprise Online à partir d’un PC.</span><span class="sxs-lookup"><span data-stu-id="ce157-294">Start by creating a remote PowerShell session to the Skype for Business online environment from a PC.</span></span>

```PowerShell
Import-Module SkypeOnlineConnector  
$cssess=New-CsOnlineSession -Credential $cred  
Import-PSSession $cssess -AllowClobber
```

2. <span data-ttu-id="ce157-295">Pour activer votre compte Surface Hub pour Skype Entreprise Server, exécutez l’applet de commande suivante:</span><span class="sxs-lookup"><span data-stu-id="ce157-295">To enable your Surface Hub account for Skype for Business Server, run this cmdlet:</span></span>

```PowerShell
Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool  
'sippoolbl20a04.infra.lync.com' -SipAddressType UserPrincipalName
```

   <span data-ttu-id="ce157-296">Si vous n’êtes pas certain de la valeur à utiliser pour le paramètre `RegistrarPool` dans votre environnement, vous pouvez obtenir cette valeur à partir d’un utilisateur Skype Entreprise existant en utilisant l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="ce157-296">If you aren't sure what value to use for the `RegistrarPool` parameter in your environment, you can get the value from an existing Skype for Business user using this cmdlet:</span></span>

```PowerShell
Get-CsOnlineUser -Identity 'HUB01@contoso.com'| fl *registrarpool*
```

10. <span data-ttu-id="ce157-297">Affectez une licence Skype Entreprise à votre compte Surface Hub</span><span class="sxs-lookup"><span data-stu-id="ce157-297">Assign Skype for Business license to your Surface Hub account</span></span>

<span data-ttu-id="ce157-298">Une fois que vous avez effectué les étapes précédentes pour activer votre compte Surface Hub dans Skype Entreprise Online, vous devez affecter une licence au Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="ce157-298">Once you've completed the preceding steps to enable your Surface Hub account in Skype for Business Online, you need to assign a license to the Surface Hub.</span></span> <span data-ttu-id="ce157-299">À l’aide du portail d’administration Office 365, vous devez attribuer une licence Skype entreprise Online (plan 2) ou Skype entreprise Online (plan 3) à l’appareil.</span><span class="sxs-lookup"><span data-stu-id="ce157-299">Using the O365 administrative portal, assign either a Skype for Business Online (Plan 2) or a Skype for Business Online (Plan 3) license to the device.</span></span>

- <span data-ttu-id="ce157-300">Connectez-vous en tant qu’administrateur client, ouvrez le portail d’administration O365 et cliquez sur l’application Administration.</span><span class="sxs-lookup"><span data-stu-id="ce157-300">Sign in as a tenant administrator, open the O365 Administrative Portal, and click on the Admin app.</span></span>

- <span data-ttu-id="ce157-301">Cliquez sur **Utilisateurs et groupes** , puis sur **Ajouter des utilisateurs, réinitialiser des mots de passe, et plus encore**.</span><span class="sxs-lookup"><span data-stu-id="ce157-301">Click on **Users and Groups** and then **Add users, reset passwords, and more**.</span></span>

- <span data-ttu-id="ce157-302">Cliquez sur le compte Surface Hub, puis cliquez sur l’icône en forme de stylet pour modifier les informations de compte.</span><span class="sxs-lookup"><span data-stu-id="ce157-302">Click the Surface Hub account, and then click the pen icon to edit the account information.</span></span>

- <span data-ttu-id="ce157-303">Cliquez sur **Licences**.</span><span class="sxs-lookup"><span data-stu-id="ce157-303">Click **Licenses**.</span></span>

- <span data-ttu-id="ce157-304">Dans **Affecter des licences**, sélectionnez Skype Entreprise (Plan 2) ou Skype Entreprise (Plan 3), en fonction de vos besoins en matière de licences et de Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="ce157-304">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="ce157-305">Vous devez utiliser une licence Plan 3 si vous souhaitez utiliser Voix Entreprise sur votre Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="ce157-305">You'll have to use a Plan 3 license if you want to use Enterprise Voice on your Surface Hub.</span></span>

- <span data-ttu-id="ce157-306">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="ce157-306">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="ce157-307">Vous pouvez également utiliser le Module Microsoft Azure Active Directory pour Windows PowerShell pour exécuter les applets de commande nécessaires pour affecter l’une de ces licences, mais cette procédure n’est pas abordée ici.</span><span class="sxs-lookup"><span data-stu-id="ce157-307">You can also use the Windows Azure Active Directory Module for Windows PowerShell to run the cmdlets needed to assign one of these licenses, but that's not covered here.</span></span>

<span data-ttu-id="ce157-308">Pour la validation, vous devez être en mesure d’utiliser n’importe quel client Skype Entreprise (PC, Android, etc.) pour vous connecter à ce compte.</span><span class="sxs-lookup"><span data-stu-id="ce157-308">For validation, you should be able to use any Skype for Business client (PC, Android, etc) to sign in to this account.</span></span>

### <span data-ttu-id="ce157-309">SkypeEntreprise local</span><span class="sxs-lookup"><span data-stu-id="ce157-309">Skype for Business on-premises</span></span>

<span data-ttu-id="ce157-310">Pour exécuter cette applet de commande, vous devez vous connecter à l’un des serveurs frontaux de Skype.</span><span class="sxs-lookup"><span data-stu-id="ce157-310">To run this cmdlet, you will need to connect to one of the Skype front-ends.</span></span> <span data-ttu-id="ce157-311">Ouvrez Skype PowerShell et exécutez:</span><span class="sxs-lookup"><span data-stu-id="ce157-311">Open the Skype PowerShell and run:</span></span>

```PowerShell
Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool registrarpoolfqdn -SipAddressType UserPrincipalName 
```

### <span data-ttu-id="ce157-312">Skype Entreprise hybride</span><span class="sxs-lookup"><span data-stu-id="ce157-312">Skype for Business hybrid</span></span>

<span data-ttu-id="ce157-313">Si votre organisation a configuré la [connectivité hybride entre Skype Entreprise Server et Skype Entreprise Online](https://technet.microsoft.com/library/jj205403.aspx), les instructions concernant la création de comptes différent d’un déploiement standard du Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="ce157-313">If your organization has set up [hybrid connectivity between Skype for Business Server and Skype for Business Online](https://technet.microsoft.com/library/jj205403.aspx), the guidance for creating accounts differs from a standard Surface Hub deployment.</span></span>

<span data-ttu-id="ce157-314">Le Surface Hub nécessite un compte Skype de type *meetingroom*, tandis qu’un utilisateur normal utiliserait un compte de type *utilisateur* dans Skype.</span><span class="sxs-lookup"><span data-stu-id="ce157-314">The Surface Hub requires a Skype account of the type *meetingroom*, while a normal user would use a *user* type account in Skype.</span></span> <span data-ttu-id="ce157-315">Si votre serveur Skype est configuré pour un environnement hybride dans lequel vous pouvez disposer d’utilisateurs sur le serveur local de Skype et d’autres hébergés dans Office365, vous pourrez rencontrer quelques problèmes si vous essayez de créer un compte Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="ce157-315">If your Skype server is set up for hybrid where you might have users on the local Skype server as well as users hosted in Office 365, you might run into a few issues when trying to create a Surface Hub account.</span></span>

<span data-ttu-id="ce157-316">Dans l’environnement hybride Skype entreprise Server 2015, chaque utilisateur souhaité dans Skype entreprise Online doit d’abord être créé dans le déploiement local, de sorte que le compte d’utilisateur est créé dans les services de domaine Active Directory (AD FS).</span><span class="sxs-lookup"><span data-stu-id="ce157-316">In Skype for Business Server 2015 hybrid environment, any user that you want in Skype for Business Online must first be created in the on-premises deployment, so that the user account is created in Active Directory Domain Services.</span></span> <span data-ttu-id="ce157-317">Vous pouvez ensuite déplacer l’utilisateur vers Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="ce157-317">You can then move the user to Skype for Business Online.</span></span> <span data-ttu-id="ce157-318">Le déplacement d’un compte d’utilisateur de local à en ligne est réalisé via l’applet de [passe Move-Csuser](https://technet.microsoft.com/library/gg398528.aspx) .</span><span class="sxs-lookup"><span data-stu-id="ce157-318">The move of a user account from on-premises to online is done via the [Move-CsUser](https://technet.microsoft.com/library/gg398528.aspx) cmdlet.</span></span> <span data-ttu-id="ce157-319">Pour déplacer un objet Csmeetingroom, utilisez l’applet de [passe Move-Csmeetingroom](https://technet.microsoft.com/library/jj204889.aspx?f=255&mspperror=-2147217396) .</span><span class="sxs-lookup"><span data-stu-id="ce157-319">To move a Csmeetingroom object, use the [Move-CsMeetingRoom](https://technet.microsoft.com/library/jj204889.aspx?f=255&mspperror=-2147217396) cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="ce157-320">Pour utiliser l’applet de passe Move-CsMeetingRoom, vous devez avoir installé [la mise à jour cumulative 2017 de Skype entreprise server 2015](https://support.microsoft.com/help/4020991/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p) ou [la mise à jour cumulative 2017 5.0.8308.992 pour Lync Server 2013](https://support.microsoft.com/help/4034279/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p).</span><span class="sxs-lookup"><span data-stu-id="ce157-320">To use the Move-CsMeetingRoom cmdlet, you must have installed [the May 2017 cumulative update 6.0.9319.281 for Skype for Business Server 2015](https://support.microsoft.com/help/4020991/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p) or [the July 2017 cumulative update 5.0.8308.992 for Lync Server 2013](https://support.microsoft.com/help/4034279/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p).</span></span>
