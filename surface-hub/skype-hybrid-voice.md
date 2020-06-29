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
# <span data-ttu-id="69483-104">Déploiement en ligne ou hybride à l’aide de l’environnement SkypeHybridVoice (SurfaceHub)</span><span class="sxs-lookup"><span data-stu-id="69483-104">Online or hybrid deployment using Skype Hybrid Voice environment  (Surface Hub)</span></span>

<span data-ttu-id="69483-105">Cette rubrique explique comment activer le CloudPBX de SkypeEntreprise avec une connectivitéPSTN (réseau téléphonique commuté) locale via le pool CloudConnectorEdition ou SkypeEntreprise2015.</span><span class="sxs-lookup"><span data-stu-id="69483-105">This topic explains how to enable Skype for Business Cloud PBX with on-premises Public Switched Telephone Network (PSTN) connectivity via Cloud Connector Edition or Skype for Business 2015 pool.</span></span> <span data-ttu-id="69483-106">Dans cette option.</span><span class="sxs-lookup"><span data-stu-id="69483-106">In this option.</span></span> <span data-ttu-id="69483-107">vos pools d’accueil SkypeEntreprise et les serveurs Exchange se trouvent dans le cloud et sont connectés par PSTN via un pool local exécutant SkypeEntreprise2015 ou CloudConnectorEdition.</span><span class="sxs-lookup"><span data-stu-id="69483-107">your Skype for Business home pools and Exchange servers are in the cloud, and are connected by PSTN via an on-premises pool running Skype for Business 2015 or Cloud Connector edition.</span></span> <span data-ttu-id="69483-108">[En savoir plus sur les différentes options du CloudPBX](https://technet.microsoft.com/library/mt612869.aspx).</span><span class="sxs-lookup"><span data-stu-id="69483-108">[Learn more about different Cloud PBX options](https://technet.microsoft.com/library/mt612869.aspx).</span></span>  

<span data-ttu-id="69483-109">Si vous avez déployé le CloudPBX de SkypeEntreprise avec l’une des options Hybrid Voice, suivez les étapes ci-dessous pour activer le compte de salle pour SurfaceHub.</span><span class="sxs-lookup"><span data-stu-id="69483-109">If you deployed Skype for Business Cloud PBX with one of the hybrid voice options, follow the steps below to enable the room account for Surface Hub.</span></span> <span data-ttu-id="69483-110">Il est important de créer tout d’abord un compte d’utilisateur standard, d’affecter toutes les options voix hybride et numéros de téléphone, puis de convertir le compte en un compte de salle.</span><span class="sxs-lookup"><span data-stu-id="69483-110">It is important to create a regular user account first, assign all hybrid voice options and phone numbers, and then convert the account to a room account.</span></span> <span data-ttu-id="69483-111">Si vous ne suivez pas cette instruction, vous ne serez pas en mesure d’attribuer un numéro de téléphone hybride.</span><span class="sxs-lookup"><span data-stu-id="69483-111">If you do not follow this order, you will not be able to assign a hybrid phone number.</span></span>  

>[!WARNING]
><span data-ttu-id="69483-112">Si vous créez un compte avant de configurer HybridVoice (en exécutant la commande Enable-CSMeetingRoom), vous ne serez pas en mesure de configurer les paramètres HybridVoice requis.</span><span class="sxs-lookup"><span data-stu-id="69483-112">If you create an account before configuration of Hybrid voice (you run Enable-CSMeetingRoom command), you will not be able to configure required hybrid voice parameters.</span></span> <span data-ttu-id="69483-113">Afin de configurer les paramètres HybridVoice pour un compte précédemment configuré ou de reconfigurer un numéro de téléphone, supprimez les licences E5 ou E3 et le complément CloudPBX, puis suivez les étapes suivantes en commençant par l’étape3.</span><span class="sxs-lookup"><span data-stu-id="69483-113">In order to configure hybrid voice parameters for a previously configured account or to reconfigure a phone number, delete the E5 or E3  + Cloud PBX add-on license, and then follow the steps below, starting at step 3.</span></span>

1. <span data-ttu-id="69483-114">Créez un compte d’utilisateur pour SurfaceHub.</span><span class="sxs-lookup"><span data-stu-id="69483-114">Create a new user account for Surface Hub.</span></span> <span data-ttu-id="69483-115">Cet exemple utilise <strong> surfacehub2@adatum.com </strong> .</span><span class="sxs-lookup"><span data-stu-id="69483-115">This example uses <strong>surfacehub2@adatum.com</strong>.</span></span> <span data-ttu-id="69483-116">Le compte peut être créé dans Active Directory local et synchronisé avec le Cloud, ou créé directement dans le Cloud.</span><span class="sxs-lookup"><span data-stu-id="69483-116">The account can be created in local Active Directory and synchronized to the cloud, or created directly in the cloud.</span></span> 

    ![nouvel objet utilisateur](images/new-user-hybrid-voice.png)

2. <span data-ttu-id="69483-118">Sélectionnez **Le mot de passe n’expire jamais**.</span><span class="sxs-lookup"><span data-stu-id="69483-118">Select **Password Never Expires**.</span></span> <span data-ttu-id="69483-119">Cela est important pour un appareil SurfaceHub.</span><span class="sxs-lookup"><span data-stu-id="69483-119">This is important for a Surface Hub device.</span></span>

   ![Le mot de passe n’expire jamais](images/new-user-password-hybrid-voice.png)

3. <span data-ttu-id="69483-121">Dans Office365, ajoutez une licence **E5** ou **E3 et le complément CloudPBX** au compte d’utilisateur créé pour la salle.</span><span class="sxs-lookup"><span data-stu-id="69483-121">In Office 365, add **E5** license or **E3 and Cloud PBX** add-on to the user account created for the room.</span></span> <span data-ttu-id="69483-122">Cela est nécessaire pour exécuter HybridVoice.</span><span class="sxs-lookup"><span data-stu-id="69483-122">This is required for Hybrid Voice to work.</span></span>

   ![Ajouter la licence du produit](images/product-license-hybrid-voice.png)

4. <span data-ttu-id="69483-124">Attendez environ 15minutes jusqu’à ce que le compte d’utilisateur pour la salle s’affiche dans SkypeEntrepriseOnline.</span><span class="sxs-lookup"><span data-stu-id="69483-124">Wait approximately 15 minutes until the user account for the room appears in Skype for Business Online.</span></span>

5. <span data-ttu-id="69483-125">Une fois que le compte d’utilisateur pour la salle est créé dans SkypeEntrepriseOnline, activez-le pour HybridVoice dans RemotePowerShell de SkypeEntreprise en exécutant l’applet de commande suivante:</span><span class="sxs-lookup"><span data-stu-id="69483-125">After the user account for room is created in Skype for Business Online, enable it for Hybrid Voice in Skype for Business Remote PowerShell by running the following cmdlet:</span></span>

   ```
   Set-csuser surfacehub2@adatum.com EnterpriseVoiceEnabled $true -HostedVoiceMail $true -onpremlineuri tel:+15005000102
   ```
    
6. <span data-ttu-id="69483-126">Valider le flux d’appels HybridVoice en plaçant les appels tests à partir de votre SurfaceHub.</span><span class="sxs-lookup"><span data-stu-id="69483-126">Validate Hybrid Voice call flow by placing test calls from the Surface Hub.</span></span>

7. <span data-ttu-id="69483-127">Démarrez une session PowerShell distante sur un PC et connectez-vous à Exchange en exécutant les applets de commande suivantes.</span><span class="sxs-lookup"><span data-stu-id="69483-127">Start a remote PowerShell session on a PC and connect to Exchange by running the following cmdlets.</span></span>

   ```
   Set-ExecutionPolicy Unrestricted
   $cred=Get-Credential -Message "Please use your Office 365 admin credentials"
   $sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/ps1-liveid/ -Credential $cred -Authentication Basic -AllowRedirection
   Import-PSSession $sess
   ```
    
8. <span data-ttu-id="69483-128">Après avoir établi une session, modifiez le compte d’utilisateur pour la salle afin de l’activer en tant que **RoomMailboxAccount** en exécutant les applets de commande suivantes.</span><span class="sxs-lookup"><span data-stu-id="69483-128">After establishing a session, modify the user account for the room to enable it as a **RoomMailboxAccount** by running the following cmdlets.</span></span> <span data-ttu-id="69483-129">Cela permettra au compte de s’authentifier sur le SurfaceHub.</span><span class="sxs-lookup"><span data-stu-id="69483-129">This allows the account to authenticate with Surface Hub.</span></span>

   ```
   Set-Mailbox surfacehub2@adatum.com -Type Room
   Set-Mailbox surfacehub2@adatum.com -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```
    
9. <span data-ttu-id="69483-130">Après avoir configuré la boîte aux lettres, vous devez créer une stratégie ExchangeActiveSync ou utiliser une stratégie existante compatible.</span><span class="sxs-lookup"><span data-stu-id="69483-130">After setting up the mailbox, you will need to either create a new Exchange ActiveSync policy, or use a compatible existing policy.</span></span>

   <span data-ttu-id="69483-131">Les Surface Hub sont uniquement compatibles avec les comptes d’appareil dotés d’une stratégie ActiveSync, où la propriété **PasswordEnabled** est définie sur **False**.</span><span class="sxs-lookup"><span data-stu-id="69483-131">Surface Hubs are only compatible with device accounts that have an ActiveSync policy where the **PasswordEnabled** property is set to **False**.</span></span> <span data-ttu-id="69483-132">Si la propriété n’est pas définie correctement, les services Exchange sur le SurfaceHub (courrier, calendrier et accès aux réunions) ne seront pas activés.</span><span class="sxs-lookup"><span data-stu-id="69483-132">If this isn’t set properly, then Exchange services on the Surface Hub (mail, calendar, and joining meetings), will not be enabled.</span></span>
    
   <span data-ttu-id="69483-133">Si vous n’avez pas encore créé de stratégie compatible, utilisez l’applet de commande suivante (celle-ci crée une stratégie appelée SurfaceHub).</span><span class="sxs-lookup"><span data-stu-id="69483-133">If you haven’t created a compatible policy yet, use the following cmdlet (this one creates a policy called "Surface Hubs").</span></span> <span data-ttu-id="69483-134">Une fois la stratégie créée, vous pouvez appliquer la même stratégie à d’autres comptes d’appareil.</span><span class="sxs-lookup"><span data-stu-id="69483-134">After it’s created, you can apply the same policy to other device accounts.</span></span>

   ```
   $easPolicy = New-MobileDeviceMailboxPolicy -Name "SurfaceHubs" -PasswordEnabled $false
   ```
    
   <span data-ttu-id="69483-135">Une fois que vous disposez d’une stratégie compatible, vous devez l’appliquer au compte d’appareil.</span><span class="sxs-lookup"><span data-stu-id="69483-135">After you have a compatible policy, then you will need to apply the policy to the device account.</span></span> <span data-ttu-id="69483-136">Toutefois, les stratégies peuvent uniquement être appliquées aux comptes d’utilisateurs et non aux boîtes aux lettres de ressources.</span><span class="sxs-lookup"><span data-stu-id="69483-136">However, policies can only be applied to user accounts and not resource mailboxes.</span></span> <span data-ttu-id="69483-137">Exécutez les applets de commande suivantes pour convertir la boîte aux lettres en un type d’utilisateur, appliquer la stratégie, puis effectuer une nouvelle conversion en boîte aux lettres (vous devrez peut-être réactiver le compte et également redéfinir le mot de passe).</span><span class="sxs-lookup"><span data-stu-id="69483-137">Run the following cmdlets to convert the mailbox into a user type, apply the policy, and then convert it back into a mailbox (you may need to re-enable the account and set the password again).</span></span>
    
   ```
   Set-Mailbox surfacehub2@adatum.com -Type Regular
   Set-CASMailbox surfacehub2@adatum.com -ActiveSyncMailboxPolicy $easPolicy.id
   Set-Mailbox surfacehub2@adatum.com -Type Room
   $credNewAccount = Get-Credential -Message "Please provide the Surface Hub username and password"
   Set-Mailbox surfacehub2@adatum.com -RoomMailboxPassword $credNewAccount.Password -EnableRoomMailboxAccount $true
   ```
    
10. <span data-ttu-id="69483-138">Diverses propriétés Exchange doivent être définies sur le compte d’appareil pour améliorer l’expérience de réunions.</span><span class="sxs-lookup"><span data-stu-id="69483-138">Various Exchange properties must be set on the device account to improve the meeting experience.</span></span> <span data-ttu-id="69483-139">Vous pouvez voir les propriétés qui peuvent être définies dans les [propriétés Exchange](exchange-properties-for-surface-hub-device-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="69483-139">You can see which properties can be set in [Exchange properties](exchange-properties-for-surface-hub-device-accounts.md).</span></span> <span data-ttu-id="69483-140">Les applets de commande suivantes fournissent un exemple de définition des propriétés Exchange.</span><span class="sxs-lookup"><span data-stu-id="69483-140">The following cmdlets provide an example of setting Exchange properties.</span></span>

    ```
    Set-CalendarProcessing surfacehub2@adatum.com -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
    Set-CalendarProcessing surfacehub2@adatum.com -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
    ```

11. <span data-ttu-id="69483-141">Activez la boîte aux lettres en tant qu’appareil de réunion dans SkypeEntrepriseOnline.</span><span class="sxs-lookup"><span data-stu-id="69483-141">Enable the mailbox as a meeting device in Skype for Business Online.</span></span> <span data-ttu-id="69483-142">Exécutez l’applet de commande suivante qui active le compte en tant qu’appareil de réunion.</span><span class="sxs-lookup"><span data-stu-id="69483-142">Run the following cmdlet which enables the account as a meeting device.</span></span> 

    ```
    Get-CsTenant | select registrarpool
    Enable-CsMeetingRoom surfacehub2@adatum.com -RegistrarPool  'sippoolbl20a04.infra.lync.com' -SipAddressType UserPrincipalName
    ```
    
    <span data-ttu-id="69483-143">En conséquence de l’exécution de cette applet de commande, il sera demandé aux utilisateurs s’ils se trouvent dans une salle de réunion, comme illustré dans l’image suivante.</span><span class="sxs-lookup"><span data-stu-id="69483-143">As a result of running this cmdlet, users will be asked if they are in a meeting room, as shown in the following image.</span></span> <span data-ttu-id="69483-144">**Oui** désactivera le microphone et le haut-parleur.</span><span class="sxs-lookup"><span data-stu-id="69483-144">**Yes** will mute the microphone and speaker.</span></span>

    ![](images/adjust-room-audio.png)


    
<span data-ttu-id="69483-145">Le compte de salle est désormais entièrement configuré, y compris HybridVoice.</span><span class="sxs-lookup"><span data-stu-id="69483-145">At this moment the room account is fully configured, including Hybrid Voice.</span></span> <span data-ttu-id="69483-146">Si vous utilisez Skype en local, vous pouvez configurer des attributs supplémentaires, comme la description ou l’emplacement, en local.</span><span class="sxs-lookup"><span data-stu-id="69483-146">If you use Skype on-premises, you can configure additional attributes, like description, location, etc., on-premises.</span></span> <span data-ttu-id="69483-147">Si vous créez une salle dans SkypeOnline, ces paramètres peuvent être définis en ligne.</span><span class="sxs-lookup"><span data-stu-id="69483-147">If you create a room in Skype Online, these parameters can be set online.</span></span> 

<span data-ttu-id="69483-148">Dans l’image suivante, vous pouvez voir comment l’appareil apparaît aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="69483-148">In the following image, you can see how the device appears to users.</span></span>


![](images/select-room-hybrid-voice.png)
