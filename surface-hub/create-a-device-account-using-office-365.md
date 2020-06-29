---
title: Créer un compte d’appareil à l’aide de l’IU (SurfaceHub)
description: Pour utiliser une IU graphique, créez un compte pour votre Surface Hub avec l’interface utilisateur Office365 ou le Centre d’administration Exchange.
ms.assetid: D11BCDC4-DABA-4B9A-9ECB-58E02CC8218C
ms.reviewer: ''
manager: laurawi
keywords: créer le compte de l’appareil, l’interface utilisateur d’Office 365, le centre d’administration Exchange, le centre d’administration Microsoft 365, Skype entreprise, stratégie de messagerie d’appareil mobile
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 05/04/2018
ms.localizationpriority: medium
ms.openlocfilehash: e1f82f084103d4eef942e812c5e4f0e8bf425def
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10834074"
---
# <span data-ttu-id="58b09-104">Créer un compte d’appareil à l’aide de l’IU (SurfaceHub)</span><span class="sxs-lookup"><span data-stu-id="58b09-104">Create a device account using UI (Surface Hub)</span></span>


<span data-ttu-id="58b09-105">Pour utiliser une IU graphique, créez un compte pour votre MicrosoftSurfaceHub avec l’[interface utilisateur Office365](#create-device-acct-o365) ou le [Centre d’administration Exchange](#create-device-acct-eac).</span><span class="sxs-lookup"><span data-stu-id="58b09-105">If you prefer to use a graphical user interface, you can create a device account for your Microsoft Surface Hub with either the [Office 365 UI](#create-device-acct-o365) or the [Exchange Admin Center](#create-device-acct-eac).</span></span>

## <a href="" id="create-device-acct-o365"></a><span data-ttu-id="58b09-106">Créer un compte d’appareil à l’aide d’Office 365</span><span class="sxs-lookup"><span data-stu-id="58b09-106">Create a device account using Office 365</span></span>


1.  <span data-ttu-id="58b09-107">[Créez le compte dans le centre d’administration 365 Microsoft](#create-device-acct-o365-admin-ctr).</span><span class="sxs-lookup"><span data-stu-id="58b09-107">[Create the account in the Microsoft 365 Admin Center](#create-device-acct-o365-admin-ctr).</span></span>
2.  <span data-ttu-id="58b09-108">[Créez une stratégie de boîte aux lettres d’appareil mobile (ActiveSync) à partir du Centre d’administration Exchange](#create-device-acct-o365-mbx-policy).</span><span class="sxs-lookup"><span data-stu-id="58b09-108">[Create a mobile device mailbox (ActiveSync) policy from the Microsoft Exchange Admin Center](#create-device-acct-o365-mbx-policy).</span></span>
3.  <span data-ttu-id="58b09-109">[Utiliser Windows PowerShell pour terminer la création du compte d’appareil](#create-device-acct-o365-complete-acct).</span><span class="sxs-lookup"><span data-stu-id="58b09-109">[Use PowerShell to complete device account creation](#create-device-acct-o365-complete-acct).</span></span>
4.  <span data-ttu-id="58b09-110">[Utilisez PowerShell pour configurer les propriétés Exchange du compte](#create-device-acct-o365-configure-exch-prop).</span><span class="sxs-lookup"><span data-stu-id="58b09-110">[Use PowerShell to configure Exchange properties of the account](#create-device-acct-o365-configure-exch-prop).</span></span>
5.  <span data-ttu-id="58b09-111">[Activez le compte d’appareil avec SkypeEntreprise.](#create-device-acct-o365-skype-for-business).</span><span class="sxs-lookup"><span data-stu-id="58b09-111">[Enable the account with Skype for Business](#create-device-acct-o365-skype-for-business).</span></span>

### <a href="" id="create-device-acct-o365-admin-ctr"></a><span data-ttu-id="58b09-112">Créer le compte dans le centre d’administration</span><span class="sxs-lookup"><span data-stu-id="58b09-112">Create the account in the admin center</span></span>

1.  <span data-ttu-id="58b09-113">Connectez-vous à Office 365 en visitanthttps://portal.office.com</span><span class="sxs-lookup"><span data-stu-id="58b09-113">Sign in to Office 365 by visiting https://portal.office.com</span></span>
2.  <span data-ttu-id="58b09-114">Fournissez les informations d’identification d’administration de votre client Office365.</span><span class="sxs-lookup"><span data-stu-id="58b09-114">Provide the admin credentials for your Office 365 tenant.</span></span> <span data-ttu-id="58b09-115">Vous serez ainsi dirigé vers le centre d’administration Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="58b09-115">This will take you to your Microsoft 365 Admin Center.</span></span>

    ![Centre d’administration Microsoft 365.](images/setupdeviceaccto365-02.png)

3. <span data-ttu-id="58b09-117">Dans le centre d’administration, accédez à **ressources** dans le volet gauche, puis cliquez sur **salles & Equipement**.</span><span class="sxs-lookup"><span data-stu-id="58b09-117">In the admin center, navigate to **Resources** in the left panel, and then click **Rooms & equipment**.</span></span>

    ![Option salles & équipements dans le centre d’administration](images/room-equipment.png)

4. <span data-ttu-id="58b09-119">Cliquez sur **Ajouter** pour créer un nouveau compte de salle.</span><span class="sxs-lookup"><span data-stu-id="58b09-119">Click **Add** to create a new Room account.</span></span> <span data-ttu-id="58b09-120">Entrez un nom d'affichage et une adresse e-mail pour le compte, puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="58b09-120">Enter a display name and email address for the account, and then click **Add**.</span></span>

    ![Créer une nouvelle fenêtre de compte de salle](images/room-add.png)

5. <span data-ttu-id="58b09-122">Sélectionnez le compte de salle que vous venez de créer dans la liste Utilisateurs actifs.</span><span class="sxs-lookup"><span data-stu-id="58b09-122">Select the Room account you just created in the Active Users list.</span></span> <span data-ttu-id="58b09-123">Dans le volet droit, vous pouvez voir les propriétés du compte et plusieurs actions facultatives.</span><span class="sxs-lookup"><span data-stu-id="58b09-123">In the right panel, you can see the account properties and several optional actions.</span></span> <span data-ttu-id="58b09-124">Cliquez sur **Réinitialiser le mot de passe** pour modifier le mot de passe, décochez la case demandant aux **utilisateurs de modifier leur mot de passe lors de leur première connexion**, car il n’est pas possible de modifier le mot de passe à partir du flux de connexion Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="58b09-124">Click **Reset password** to change the password, and unselect **Make this user change their password when they first sign in**, because it is not possible to change the password from the Surface Hub sign-in flow.</span></span>

6. <span data-ttu-id="58b09-125">Cliquez sur **Modifier** dans la section **Licence attribuée**, puis sur la flèche déroulante en regard de la licence appropriée pour développer les détails.</span><span class="sxs-lookup"><span data-stu-id="58b09-125">In the **Assigned license** section, click **Edit**, and then click the dropdown arrow next to the appropriate license to expand the details.</span></span> <span data-ttu-id="58b09-126">Sélectionnez un emplacement d’utilisateur, puis dans la liste des licences, activez **Skype Entreprise Online (Plan 2)**, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="58b09-126">Select a user location, and in the list of licenses, toggle on **Skype for Business Online (Plan 2)**, and then click **Save**.</span></span> <span data-ttu-id="58b09-127">La licence peut varier en fonction de votre organisation (par exemple, vous disposez peut-être du plan2 ou du plan3).</span><span class="sxs-lookup"><span data-stu-id="58b09-127">The license may vary depending on your organization (for example, you might have Plan 2 or Plan 3).</span></span>

### <a href="" id="create-device-acct-o365-mbx-policy"></a><span data-ttu-id="58b09-128">Créer une stratégie de boîte aux lettres d’appareil mobile (ActiveSync) à partir du Centre d’administration Exchange</span><span class="sxs-lookup"><span data-stu-id="58b09-128">Create a mobile device mailbox (ActiveSync) policy from the Exchange Admin Center</span></span>

1.  <span data-ttu-id="58b09-129">Dans le volet gauche du centre d’administration, cliquez sur **administrateur**, puis sur **Exchange**.</span><span class="sxs-lookup"><span data-stu-id="58b09-129">In the admin center’s left panel, click **ADMIN**, and then click **Exchange**.</span></span>

    ![Centre d’administration affichant les utilisateurs Exchange actifs.](images/setupdeviceaccto365-08.png)

2.  <span data-ttu-id="58b09-131">Un autre onglet s’ouvre sur votre navigateur pour accéder au Centre d’administration Exchange, où vous pouvez créer et définir le paramètre de boîte aux lettres du Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="58b09-131">This will open another tab on your browser to take you to the Exchange Admin Center, where you can create and set the Mailbox Setting for Surface Hub.</span></span>

    ![Centre d’administration Exchange.](images/setupdeviceaccto365-09.png)

3.  <span data-ttu-id="58b09-133">Pour créer une stratégie de boîte aux lettres d’appareil mobile, cliquez sur **Mobile** dans le volet gauche, puis sur **Stratégies de boîte aux lettres de périphérique mobile**.</span><span class="sxs-lookup"><span data-stu-id="58b09-133">To create a Mobile Device Mailbox Policy, click **Mobile** from the left panel and then click **Mobile device mailbox policies**.</span></span> <span data-ttu-id="58b09-134">Les Surfaces Hub requièrent un compte doté d’une stratégie de boîte aux lettres d’appareil mobile qui ne nécessite pas de mot de passe. Ainsi, si vous avez déjà une stratégie existante qui correspond à cette exigence, vous pouvez l’appliquer au compte.</span><span class="sxs-lookup"><span data-stu-id="58b09-134">Surface Hubs require an account with a mobile device mailbox policy that does not require a password, so if you already have an existing policy that matches this requirement, you can apply that policy to the account.</span></span> <span data-ttu-id="58b09-135">Dans le cas contraire, procédez comme suit pour en créer une nouvelle à utiliser uniquement pour les comptes d’appareil Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="58b09-135">Otherwise use the following steps to create a new one to be used only for Surface Hub device accounts.</span></span>

    ![Centre d’administration Exchange - création d’une stratégie de boîte aux lettres d’appareil mobile.](images/setupdeviceaccto365-10.png)

4.  <span data-ttu-id="58b09-137">Pour créer une nouvelle stratégie de boîte aux lettres d’appareil mobile Surface Hub, cliquez sur le bouton **+** dans les commandes situées au-dessus de la liste des stratégies pour en ajouter une nouvelle.</span><span class="sxs-lookup"><span data-stu-id="58b09-137">To create a New Surface Hub mobile device mailbox policy, click the **+** button from the controls above the list of policies to add a new policy.</span></span> <span data-ttu-id="58b09-138">Indiquez un nom qui vous aidera à distinguer cette stratégie des autres comptes d’appareil (par exemple, *SurfaceHubDeviceMobilePolicy*).</span><span class="sxs-lookup"><span data-stu-id="58b09-138">For the name, provide a name that will help you distinguish this policy from other device accounts (for example, *SurfaceHubDeviceMobilePolicy*).</span></span> <span data-ttu-id="58b09-139">Assurez-vous que la stratégie ne nécessite pas de mot de passe pour les appareils affectés à celle-ci. Par conséquent, veillez à ce que la case **Exiger un mot de passe** soit décochée, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="58b09-139">Make sure the policy does not require a password for the devices assigned to, so make sure **Require a Password** remains unchecked, then click **Save**.</span></span>

    ![Image montrant une nouvelle stratégie d’appareil mobile.](images/setupdeviceaccto365-11.png)

5.  <span data-ttu-id="58b09-141">Après avoir créé la stratégie de boîte aux lettres d’appareil mobile, revenez au **Centre d’administration Exchange** dans lequel s’affiche la nouvelle stratégie.</span><span class="sxs-lookup"><span data-stu-id="58b09-141">After you have created the new mobile device mailbox policy, go back to the **Exchange Admin Center** and you will see the new policy listed.</span></span>

    ![Image montrant une nouvelle stratégie de boîte aux lettres d’appareil mobile dans le Centre d’administration Exchange.](images/setupdeviceaccto365-12.png)



### <a href="" id="create-device-acct-o365-complete-acct"></a><span data-ttu-id="58b09-143">Utiliser Windows PowerShell pour terminer la création du compte d’appareil</span><span class="sxs-lookup"><span data-stu-id="58b09-143">Use PowerShell to complete device account creation</span></span>

<span data-ttu-id="58b09-144">À partir de là, vous devrez terminer le processus de création de compte à l’aide de PowerShell pour définir une configuration.</span><span class="sxs-lookup"><span data-stu-id="58b09-144">From here on, you'll need to finish the account creation process using PowerShell to set up some configuration.</span></span>

<span data-ttu-id="58b09-145">Pour exécuter les applets de commande utilisées par ces scripts PowerShell, les éléments suivants doivent être installés pour la console d’administration PowerShell:</span><span class="sxs-lookup"><span data-stu-id="58b09-145">In order to run cmdlets used by these PowerShell scripts, the following must be installed for the admin PowerShell console:</span></span>

-   [<span data-ttu-id="58b09-146">Assistant de connexion de Microsoft Online Services pour les informaticiens RTW</span><span class="sxs-lookup"><span data-stu-id="58b09-146">Microsoft Online Services Sign-In Assistant for IT Professionals RTW</span></span>](https://www.microsoft.com/download/details.aspx?id=41950)
-   [<span data-ttu-id="58b09-147">Module Windows Active Directory pour Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="58b09-147">Windows Azure Active Directory Module for Windows PowerShell</span></span>](https://www.microsoft.com/web/handlers/webpi.ashx/getinstaller/WindowsAzurePowershellGet.3f.3f.3fnew.appids)
-   [<span data-ttu-id="58b09-148">Skype Entreprise Online, module Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="58b09-148">Skype for Business Online, Windows PowerShell Module</span></span>](https://www.microsoft.com/download/details.aspx?id=39366)

<span data-ttu-id="58b09-149">Installez le module suivant dans PowerShell.</span><span class="sxs-lookup"><span data-stu-id="58b09-149">Install the following module in Powershell</span></span>
``` syntax
    install-module AzureAD
    Install-module MsOnline
```

### <span data-ttu-id="58b09-150">Connexion aux services en ligne</span><span class="sxs-lookup"><span data-stu-id="58b09-150">Connecting to online services</span></span>

1.  <span data-ttu-id="58b09-151">Exécutez Windows PowerShell en tant qu’administrateur.</span><span class="sxs-lookup"><span data-stu-id="58b09-151">Run Windows PowerShell as Administrator.</span></span>

    ![Image montrant comment démarrer Windows PowerShell et l’exécuter en tant qu’administrateur.](images/setupdeviceaccto365-17.png)

2.  <span data-ttu-id="58b09-153">Créez un objet Informations d’identification, puis créez une nouvelle session qui se connecte à Skype Entreprise Online. Indiquez ensuite le compte d’administrateur du client global, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="58b09-153">Create a Credentials object, then create a new session that connects to Skype for Business Online, and provide the global tenant administrator account, then click **OK**.</span></span>

    ![Image relative à la demande d’informations d’identification Windows PowerShell.](images/setupdeviceaccto365-18.png)

3.  <span data-ttu-id="58b09-155">Pour se connecter à Microsoft Online Services, exécutez la commande suivante:</span><span class="sxs-lookup"><span data-stu-id="58b09-155">To connect to Microsoft Online Services, run:</span></span>

    ``` syntax
    Connect-MsolService -Credential $Cred
    ```

    ![Image montrant une applet de commande PowerShell.](images/setupdeviceaccto365-19.png)

4.  <span data-ttu-id="58b09-157">À présent pour vous connecter à Skype Entreprise Online, exécutez la commande suivante:</span><span class="sxs-lookup"><span data-stu-id="58b09-157">Now to connect to Skype for Business Online Services, run:</span></span>

    ``` syntax
    $sfbsession = New-CsOnlineSession -Credential $cred
    ```

    ![Image montrant une applet de commande PowerShell.](images/setupdeviceaccto365-20.png)

5.  <span data-ttu-id="58b09-159">Enfin, pour vous connecter aux services Exchange Online, exécutez la commande suivante:</span><span class="sxs-lookup"><span data-stu-id="58b09-159">Finally, to connect to Exchange Online Services, run:</span></span>

    ``` syntax
    $exchangeSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://outlook.office365.com/powershell-liveid/" -Credential $cred -Authentication "Basic" –AllowRedirection
    ```

    ![Image montrant une applet de commande PowerShell.](images/setupdeviceaccto365-21.png)

6.  <span data-ttu-id="58b09-161">Maintenant, vous devez importer les sessions Skype Entreprise Online et Exchange Online que vous venez de créer pour importer les commandes Exchange et Skype afin de les utiliser localement.</span><span class="sxs-lookup"><span data-stu-id="58b09-161">Now you have to import the Skype for Business Online Session and the Exchange Online session you have just created, which will import the Exchange and Skype Commands so you can use them locally.</span></span>

    ``` syntax
    Import-PSSession $exchangesession -AllowClobber -WarningAction SilentlyContinue
    Import-PSSession $sfbsession -AllowClobber -WarningAction SilentlyContinue
    ```

    <span data-ttu-id="58b09-162">Notez que cette opération peut prendre un certain temps.</span><span class="sxs-lookup"><span data-stu-id="58b09-162">Note that this could take a while to complete.</span></span>

    ![Image montrant une applet de commande PowerShell.](images/setupdeviceaccto365-22.png)

7.  <span data-ttu-id="58b09-164">Une fois que vous êtes connecté aux services en ligne, vous devez encore exécuter quelques applets de commande pour configurer ce compte comme compte d’appareil Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="58b09-164">Once you’re connected to the online services you need to run a few more cmdlets to configure this account as a Surface Hub device account.</span></span>

### <a href="" id="create-device-acct-o365-configure-exch-prop"></a><span data-ttu-id="58b09-165">Utiliser PowerShell pour configurer les propriétés Exchange du compte</span><span class="sxs-lookup"><span data-stu-id="58b09-165">Use PowerShell to configure Exchange properties of the account</span></span>

<span data-ttu-id="58b09-166">Maintenant que vous êtes connecté aux services en ligne, vous pouvez terminer la configuration du compte d’appareil.</span><span class="sxs-lookup"><span data-stu-id="58b09-166">Now that you're connected to the online services, you can finish setting up the device account.</span></span> <span data-ttu-id="58b09-167">Vous allez utiliser l’adresse électronique du compte d’appareil pour effectuer les actions suivantes:</span><span class="sxs-lookup"><span data-stu-id="58b09-167">You'll use the device account email address to:</span></span>

-   <span data-ttu-id="58b09-168">Modifier le type de boîte aux lettres pour le convertir de «standard» à «de salle».</span><span class="sxs-lookup"><span data-stu-id="58b09-168">Change the mailbox type from regular to room.</span></span>
-   <span data-ttu-id="58b09-169">Définir le mot de passe et activer le compte de boîte aux lettres de salle</span><span class="sxs-lookup"><span data-stu-id="58b09-169">Set the password and enable the room mailbox account</span></span>
-   <span data-ttu-id="58b09-170">Modifier les différentes propriétés d’Exchange</span><span class="sxs-lookup"><span data-stu-id="58b09-170">Change various Exchange properties</span></span>
-   <span data-ttu-id="58b09-171">Définir le mot de passe du compte d’utilisateur de sorte qu’il n’expire jamais.</span><span class="sxs-lookup"><span data-stu-id="58b09-171">Set the user account password to never expire.</span></span>

1.  <span data-ttu-id="58b09-172">Vous devez entrer l’adresse de messagerie du compte et créer une variable avec la valeur suivante:</span><span class="sxs-lookup"><span data-stu-id="58b09-172">You’ll need to enter the account’s mail address and create a variable with that value:</span></span>

    ```powershell
    $mailbox = (Get-Mailbox <your device account’s alias>)
    ```

    <span data-ttu-id="58b09-173">Pour stocker la valeur, obtenez-la à partir de la boîte aux lettres à l’aide de la commande suivante:</span><span class="sxs-lookup"><span data-stu-id="58b09-173">To store the value get it from the mailbox:</span></span>

    ```powershell
    $strEmail = $mailbox.WindowsEmailAddress
    ```

    <span data-ttu-id="58b09-174">Imprimez la valeur à l’aide de la commande suivante:</span><span class="sxs-lookup"><span data-stu-id="58b09-174">Print the value:</span></span>

    ```powershell
    $strEmail
    ```

    <span data-ttu-id="58b09-175">L’adresse de messagerie appropriée s’affiche.</span><span class="sxs-lookup"><span data-stu-id="58b09-175">You will see the correct email address.</span></span>

    ![Image montrant une applet de commande PowerShell.](images/setupdeviceaccto365-23.png)

2. <span data-ttu-id="58b09-177">Exécutez l’applet de commande suivante:</span><span class="sxs-lookup"><span data-stu-id="58b09-177">Run the following cmdlet:</span></span>

    ```powershell
    Set-CASMailbox $strEmail  -ActiveSyncMailboxPolicy "SurfaceHubDeviceMobilePolicy"
    ```

4.  <span data-ttu-id="58b09-178">Diverses propriétés Exchange peuvent être définies sur le compte d’appareil pour améliorer l’expérience de réunion.</span><span class="sxs-lookup"><span data-stu-id="58b09-178">Various Exchange properties can be set on the device account to improve the meeting experience.</span></span> <span data-ttu-id="58b09-179">Vous pouvez voir les propriétés à définir dans la section [Propriétés Exchange](exchange-properties-for-surface-hub-device-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="58b09-179">You can see which properties need to be set in the [Exchange properties](exchange-properties-for-surface-hub-device-accounts.md) section.</span></span>

    ``` syntax
    Set-CalendarProcessing -Identity $strEmail -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts   $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
    Set-CalendarProcessing -Identity $strEmail -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
    ```

    ![Image montrant une applet de commande PowerShell.](images/setupdeviceaccto365-26.png)

5.  <span data-ttu-id="58b09-181">Si vous décidez que le mot de passe n’expire pas, vous pouvez également définir cette option avec des applets de commande PowerShell.</span><span class="sxs-lookup"><span data-stu-id="58b09-181">If you decide to have the password not expire, you can set that with PowerShell cmdlets too.</span></span> <span data-ttu-id="58b09-182">Consultez [Gestion des mots de passe](password-management-for-surface-hub-device-accounts.md) pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="58b09-182">See [Password management](password-management-for-surface-hub-device-accounts.md) for more information.</span></span>

    ``` syntax
    Set-MsolUser -UserPrincipalName $strEmail -PasswordNeverExpires $True
    ```

### <a href="" id="create-device-acct-o365-skype-for-business"></a><span data-ttu-id="58b09-183">Activer le compte avec SkypeEntreprise</span><span class="sxs-lookup"><span data-stu-id="58b09-183">Enable the account with Skype for Business</span></span>

<span data-ttu-id="58b09-184">Activez le compte d’appareil avec SkypeEntreprise.</span><span class="sxs-lookup"><span data-stu-id="58b09-184">Enable the device account with Skype for Business.</span></span>

<span data-ttu-id="58b09-185">Pour activer SkypeEntreprise, votre environnement doit respecter la configuration suivante:</span><span class="sxs-lookup"><span data-stu-id="58b09-185">In order to enable Skype for Business, your environment will need to meet the following prerequisites:</span></span>

-   <span data-ttu-id="58b09-186">Vous devez avoir un plan autonome 2 ou une version ultérieure de Skype entreprise Online dans votre offre Office 365.</span><span class="sxs-lookup"><span data-stu-id="58b09-186">You'll need to have Skype for Business Online Standalone Plan 2 or higher in your O365 plan.</span></span> <span data-ttu-id="58b09-187">L’abonnement doit prendre en charge la fonctionnalité Conférence.</span><span class="sxs-lookup"><span data-stu-id="58b09-187">The plan needs to support conferencing capability.</span></span>
-   <span data-ttu-id="58b09-188">Si vous avez besoin d’une voix entreprise (RTC) avec des fournisseurs de service de téléphonie pour le surface Hub, vous devez disposer d’un plan autonome 3 de Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="58b09-188">If you need Enterprise Voice (PSTN telephony) using telephony service providers for the Surface Hub, you need Skype for Business Online Standalone Plan 3.</span></span>
-   <span data-ttu-id="58b09-189">Vos utilisateurs clients doivent disposer de boîtes aux lettres Exchange.</span><span class="sxs-lookup"><span data-stu-id="58b09-189">Your tenant users must have Exchange mailboxes.</span></span>
-   <span data-ttu-id="58b09-190">Votre compte surface Hub nécessite une licence de plan autonome 2 de Skype entreprise Online ou une licence de plan autonome 3 de Skype entreprise Online, mais elle ne nécessite pas de licence Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="58b09-190">Your Surface Hub account does require a Skype for Business Online Standalone Plan 2 or Skype for Business Online Standalone Plan 3 license, but it does not require an Exchange Online license.</span></span>

1.  <span data-ttu-id="58b09-191">Commencez par créer une session PowerShell à distance à partir d’un PC.</span><span class="sxs-lookup"><span data-stu-id="58b09-191">Start by creating a remote PowerShell session from a PC.</span></span>

    ```PowerShell
    Import-Module SkypeOnlineConnector
    $cssess=New-CsOnlineSession -Credential $cred
    Import-PSSession $cssess -AllowClobber
    ```

2.  <span data-ttu-id="58b09-192">Pour activer votre compte SurfaceHub pour Skype Entreprise Server, exécutez l’applet de commande suivante:</span><span class="sxs-lookup"><span data-stu-id="58b09-192">To enable your Surface Hub account for Skype for Business Server, run this cmdlet:</span></span>

    ```PowerShell
    Enable-CsMeetingRoom -Identity $strEmail -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
    ```

    <span data-ttu-id="58b09-193">Si vous n’êtes pas certain de la valeur à utiliser pour le paramètre`RegistrarPool` dans votre environnement, vous pouvez obtenir cette valeur à partir d’un utilisateur Skype Entreprise existant en utilisant l’applet de commande suivante:</span><span class="sxs-lookup"><span data-stu-id="58b09-193">If you aren't sure what value to use for the `RegistrarPool` parameter in your environment, you can get the value from an existing Skype for Business user using this cmdlet:</span></span>

    ```PowerShell
    Get-CsOnlineUser -Identity ‘alice@contoso.microsoft.com’| fl *registrarpool*
    ```

## <a href="" id="create-device-acct-eac"></a><span data-ttu-id="58b09-194">Créer un compte d’appareil à l’aide du Centre d’administration Exchange</span><span class="sxs-lookup"><span data-stu-id="58b09-194">Create a device account using the Exchange Admin Center</span></span>

>[!NOTE]
><span data-ttu-id="58b09-195">Cette méthode ne fonctionnera que si vous effectuez une synchronisation depuis un Active Directory local.</span><span class="sxs-lookup"><span data-stu-id="58b09-195">This method will only work if you are syncing from an on-premises Active Directory.</span></span>

<span data-ttu-id="58b09-196">Vous pouvez utiliser le Centre d’administration Exchange pour créer un compte d’appareil:</span><span class="sxs-lookup"><span data-stu-id="58b09-196">You can use the Exchange Admin Center to create a device account:</span></span>

1.  <span data-ttu-id="58b09-197">[Créez un compte et une boîte aux lettres à l’aide du Centre d’administration Exchange](#create-device-acct-exch-admin-ctr).</span><span class="sxs-lookup"><span data-stu-id="58b09-197">[Create an account and mailbox with the Exchange Admin Center](#create-device-acct-exch-admin-ctr).</span></span>
2.  <span data-ttu-id="58b09-198">[Créez une stratégie de boîte aux lettres d’appareil mobile à partir du Centre d’administration Exchange](#create-device-acct-exch-mbx-policy).</span><span class="sxs-lookup"><span data-stu-id="58b09-198">[Create a mobile device mailbox policy from the Exchange Admin Center](#create-device-acct-exch-mbx-policy).</span></span>
3.  <span data-ttu-id="58b09-199">[Utilisez PowerShell pour configurer le compte](#create-device-acct-exch-powershell-conf).</span><span class="sxs-lookup"><span data-stu-id="58b09-199">[Use PowerShell to configure the account](#create-device-acct-exch-powershell-conf).</span></span>
4.  <span data-ttu-id="58b09-200">[Activez le compte avec SkypeEntreprise](#create-device-acct-exch-skype-for-business).</span><span class="sxs-lookup"><span data-stu-id="58b09-200">[Enable the account with Skype for Business](#create-device-acct-exch-skype-for-business).</span></span>

### <a href="" id="create-device-acct-exch-admin-ctr"></a><span data-ttu-id="58b09-201">Créer un compte et une boîte aux lettres à l’aide du Centre d’administration Exchange</span><span class="sxs-lookup"><span data-stu-id="58b09-201">Create an account and mailbox with the Exchange Admin Center</span></span>

1.  <span data-ttu-id="58b09-202">Connectez-vous à votre Centre d’administration Exchange à l’aide des informations d’identification d’administration Exchange.</span><span class="sxs-lookup"><span data-stu-id="58b09-202">Sign in to your Exchange Admin Center using Exchange admin credentials.</span></span>
2.  <span data-ttu-id="58b09-203">Une fois dans le Centre d’administration Exchange, accédez à **Destinataires** dans le volet gauche.</span><span class="sxs-lookup"><span data-stu-id="58b09-203">Once you are at the Exchange Admin Center (EAC), navigate to **Recipients** in the left panel.</span></span>

    ![Image montrant des boîtes aux lettres du Centre d’administration Exchange.](images/setupdeviceacctexch-01.png)

3.  <span data-ttu-id="58b09-205">Dans les commandes situées au-dessus de la liste des boîtes aux lettres, choisissez **+** pour en créer une, et indiquez un **Nom complet**, un **Nom**, et un **Nom d’ouverture de session de l’utilisateur**, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="58b09-205">On the controls above the list of mailboxess, choose **+** to create a new one, and provide a **Display name**, **Name**, and **User logon name**, and then click **Save**.</span></span>

    ![Image illustrant la création d’une nouvelle boîte aux lettres.](images/setupdeviceacctexch-02.png)

### <a href="" id="create-device-acct-exch-mbx-policy"></a><span data-ttu-id="58b09-207">Créer une stratégie de boîte aux lettres d’appareil mobile à partir du Centre d’administration Exchange</span><span class="sxs-lookup"><span data-stu-id="58b09-207">Create a mobile device mailbox policy from the Exchange Admin Center</span></span>

>[!NOTE]
><span data-ttu-id="58b09-208">Si vous souhaitez créer et affecter une stratégie au compte que vous avez créé et utiliser Exchange 2010, recherchez les informations correspondantes relatives à la création de stratégies et à l’affectation de stratégie lors de l’utilisation d’EMC (Exchange Management Console).</span><span class="sxs-lookup"><span data-stu-id="58b09-208">If you want to create and assign a policy to the account you created, and are using Exchange 2010, look up the corresponding information regarding policy creation and policy assignment when using the EMC (Exchange management console).</span></span>

 

1.  <span data-ttu-id="58b09-209">Accédez au Centre d’administration Exchange.</span><span class="sxs-lookup"><span data-stu-id="58b09-209">Go to the Exchange Admin Center.</span></span>

    ![Image illustrant le Centre d’administration Exchange.](images/setupdeviceacctexch-03.png)

2.  <span data-ttu-id="58b09-211">Pour créer une stratégie de boîte aux lettres d’appareil mobile, cliquez sur **Mobile** dans le volet gauche, puis sur **Stratégies de boîte aux lettres de périphérique mobile**.</span><span class="sxs-lookup"><span data-stu-id="58b09-211">To create a mobile device mailbox policy, click **Mobile** from the left panel, then **Mobile device mailbox policies**.</span></span> <span data-ttu-id="58b09-212">Les Surfaces Hub requièrent un compte doté d’une stratégie de boîte aux lettres d’appareil mobile qui ne nécessite pas de mot de passe. Ainsi, si vous avez déjà une stratégie existante qui correspond à cette exigence, vous pouvez l’appliquer au compte.</span><span class="sxs-lookup"><span data-stu-id="58b09-212">Surface Hubs require an account with a mobile device mailbox policy that does not require a password, so if you already have an existing policy that matches this requirement, you can apply that policy to the account.</span></span> <span data-ttu-id="58b09-213">Dans le cas contraire, procédez comme suit pour en créer une nouvelle à utiliser uniquement pour les comptes d’appareil Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="58b09-213">Otherwise use the following steps to create a new one to be used only for Surface Hub device accounts.</span></span>

    ![Image illustrant la création d’une stratégie de boîte aux lettres d’appareil mobile à partir du Centre d’administration Exchange.](images/setupdeviceacctexch-05.png)

3.  <span data-ttu-id="58b09-215">Pour créer une nouvelle stratégie de boîte aux lettres de compte d’appareil mobile, cliquez sur le bouton **+** dans les commandes situées au-dessus de la liste des stratégies pour ajouter une nouvelle stratégie.</span><span class="sxs-lookup"><span data-stu-id="58b09-215">To create a new mobile device account mailbox policy, click the **+** button from the controls above the list of policies to add a new policy.</span></span> <span data-ttu-id="58b09-216">Indiquez un nom qui vous aidera à distinguer cette stratégie des autres comptes d’appareil (par exemple, *SurfaceHubDeviceMobilePolicy*).</span><span class="sxs-lookup"><span data-stu-id="58b09-216">For the name provide a name that will help you distinguish this policy from other device accounts (for example, *SurfaceHubDeviceMobilePolicy*).</span></span> <span data-ttu-id="58b09-217">La stratégie ne doit pas être protégée par mot de passe. Veillez donc à ce que la case **Exiger un mot de passe** reste décochée, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="58b09-217">The policy must not be password-protected, so make sure **Require a Password** remains unchecked, then click **Save**.</span></span>

    ![Image montrant une nouvelle stratégie de boîte aux lettres d’appareil mobile.](images/setupdeviceacctexch-06.png)

4.  <span data-ttu-id="58b09-219">Après avoir créé la stratégie de boîte aux lettres d’appareil mobile, revenez au Centre d’administration Exchange, dans lequel s’affiche la nouvelle stratégie.</span><span class="sxs-lookup"><span data-stu-id="58b09-219">After you have created the new mobile device mailbox policy, go back to the Exchange Admin Center and you will see the new policy listed.</span></span>

    ![Image montrant une nouvelle stratégie de boîte aux lettres d’appareil mobile dans le Centre d’administration Exchange.](images/setupdeviceacctexch-07.png)

5.  <span data-ttu-id="58b09-221">Pour appliquer la stratégie ActiveSync sans l’aide de PowerShell, vous pouvez procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="58b09-221">To apply the ActiveSync policy without using PowerShell, you can do the following:</span></span>

    -   <span data-ttu-id="58b09-222">Dans le Centre d’administration Exchange, cliquez sur **Destinataires** &gt; **Boîtes aux lettres**, puis sélectionnez une boîte aux lettres.</span><span class="sxs-lookup"><span data-stu-id="58b09-222">In the EAC, click **Recipients** &gt; **Mailboxes** and select a mailbox.</span></span>

        ![Image illustrant le Centre d’administration Exchange.](images/setupdeviceacctexch-08.png)

    -   <span data-ttu-id="58b09-224">Dans le volet **Détails**, faites défiler jusqu’à **Fonctionnalités téléphoniques et vocales** et cliquez sur **Afficher les détails** pour afficher l’écran **Paramètres du périphérique mobile**.</span><span class="sxs-lookup"><span data-stu-id="58b09-224">In the **Details** pane, scroll to **Phone and Voice Features** and click **View details** to display the **Mobile Device Details** screen.</span></span>

        ![Image montrant les informations de boîte aux lettres.](images/setupdeviceacctexch-09.png)

    -   <span data-ttu-id="58b09-226">La stratégie de boîte aux lettres d’appareil mobile actuellement affectée est affichée.</span><span class="sxs-lookup"><span data-stu-id="58b09-226">The mobile device mailbox policy that’s currently assigned is displayed.</span></span> <span data-ttu-id="58b09-227">Pour modifier la stratégie de boîte aux lettres d’appareil mobile, cliquez sur **Parcourir**.</span><span class="sxs-lookup"><span data-stu-id="58b09-227">To change the mobile device mailbox policy, click **Browse**.</span></span>

        ![Image montrant la stratégie de boîte aux lettres d’appareil mobile actuellement affectée.](images/setupdeviceacctexch-10.png)

    -   <span data-ttu-id="58b09-229">Choisissez la stratégie de boîte aux lettres d’appareil mobile appropriée dans la liste, cliquez sur **OK**, puis sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="58b09-229">Choose the appropriate mobile device mailbox policy from the list, click **OK** and then click **Save**.</span></span>

        ![Image montrant une liste des stratégies de boîte aux lettres d’appareil mobile. ](images/setupdeviceacctexch-11.png)

### <a href="" id="create-device-acct-exch-powershell-conf"></a><span data-ttu-id="58b09-231">Utiliser PowerShell pour configurer le compte</span><span class="sxs-lookup"><span data-stu-id="58b09-231">Use PowerShell to configure the account</span></span>

<span data-ttu-id="58b09-232">Maintenant que vous êtes connecté aux services en ligne, vous pouvez terminer la configuration du compte d’appareil.</span><span class="sxs-lookup"><span data-stu-id="58b09-232">Now that you're connected to the online services, you can finish setting up the device account.</span></span> <span data-ttu-id="58b09-233">Vous allez utiliser l’adresse électronique du compte d’appareil pour effectuer les actions suivantes:</span><span class="sxs-lookup"><span data-stu-id="58b09-233">You'll use the device account email address to:</span></span>

-   <span data-ttu-id="58b09-234">Modifier le type de boîte aux lettres pour le convertir de «standard» à «de salle».</span><span class="sxs-lookup"><span data-stu-id="58b09-234">Change the mailbox type from regular to room.</span></span>
-   <span data-ttu-id="58b09-235">Modifier les différentes propriétés d’Exchange</span><span class="sxs-lookup"><span data-stu-id="58b09-235">Change various Exchange properties</span></span>
-   <span data-ttu-id="58b09-236">Définir le mot de passe du compte d’utilisateur de sorte qu’il n’expire jamais.</span><span class="sxs-lookup"><span data-stu-id="58b09-236">Set the user account password to never expire.</span></span>

1.  <span data-ttu-id="58b09-237">Vous devez entrer l’adresse de messagerie du compte et créer une variable avec la valeur suivante:</span><span class="sxs-lookup"><span data-stu-id="58b09-237">You’ll need to enter the account’s mail address and create a variable with that value:</span></span>

    ``` syntax
    $mailbox = (Get-Mailbox <your device account’s alias>)
    ```

    <span data-ttu-id="58b09-238">Pour stocker la valeur, obtenez-la à partir de la boîte aux lettres à l’aide de la commande suivante:</span><span class="sxs-lookup"><span data-stu-id="58b09-238">To store the value got it from the mailbox:</span></span>

    ``` syntax
    $strEmail = $mailbox.WindowsEmailAddress
    ```

    <span data-ttu-id="58b09-239">Imprimez la valeur en exécutant la commande suivante:</span><span class="sxs-lookup"><span data-stu-id="58b09-239">Print the value by running:</span></span>

    ``` syntax
    $strEmail
    ```

    <span data-ttu-id="58b09-240">L’adresse de messagerie appropriée s’affiche.</span><span class="sxs-lookup"><span data-stu-id="58b09-240">You will see the correct email address.</span></span>

2.  <span data-ttu-id="58b09-241">Vous devez convertir le compte en boîte aux lettres de salle, et donc exécuter:</span><span class="sxs-lookup"><span data-stu-id="58b09-241">You need to convert the account into a room mailbox, so run:</span></span>

    ``` syntax
    Set-Mailbox $strEmail -Type Room
    ```

3.  <span data-ttu-id="58b09-242">Pour que le compte d’appareil puisse être authentifié sur une Surface Hub, vous devez activer le compte de boîte aux lettres de salle et définir un mot de passe, afin que le compte puisse être utilisé par l’appareil pour obtenir des informations de réunion à l’aide d’ActiveSync et se connecter à Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="58b09-242">In order for the device account to be authenticated on a Surface Hub, you need to enable the room mailbox account and set a password, so the account can be used by the device to get meeting information using ActiveSync and log in to Skype for Business.</span></span>

    ``` syntax
    Set-Mailbox $strEmail -RoomMailboxPassword (ConvertTo-SecureString  -String "<your password>" -AsPlainText -Force) -EnableRoomMailboxAccount $true
    ```

4.  <span data-ttu-id="58b09-243">Diverses propriétés Exchange peuvent être définies sur le compte d’appareil pour améliorer l’expérience de réunion.</span><span class="sxs-lookup"><span data-stu-id="58b09-243">Various Exchange properties can be set on the device account to improve the meeting experience.</span></span> <span data-ttu-id="58b09-244">Vous pouvez voir les propriétés à définir dans la section [Propriétés Exchange](exchange-properties-for-surface-hub-device-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="58b09-244">You can see which properties need to be set in the [Exchange properties](exchange-properties-for-surface-hub-device-accounts.md) section.</span></span>

    ``` syntax
    Set-CalendarProcessing -Identity $strEmail -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts   $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
    Set-CalendarProcessing -Identity $strEmail -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
    ```

5.  <span data-ttu-id="58b09-245">Nous devons maintenant définir quelques propriétés dans AD.</span><span class="sxs-lookup"><span data-stu-id="58b09-245">Now we have to set some properties in AD.</span></span> <span data-ttu-id="58b09-246">Pour ce faire, vous avez besoin de l’alias du compte (partie du nom d’utilisateur principal qui se transforme avant le «@»).</span><span class="sxs-lookup"><span data-stu-id="58b09-246">To do that, you need the alias of the account (this is the part of the UPN that becomes before the “@”).</span></span>

    ``` syntax
    $strAlias = “<your device account’s alias>”
    ```

6.  <span data-ttu-id="58b09-247">L’utilisateur doit être activé dans AD avant de pouvoir s’authentifier avec un Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="58b09-247">The user needs to be enabled in AD before it can authenticate with a Surface Hub.</span></span> <span data-ttu-id="58b09-248">Exécutez la commande suivante:</span><span class="sxs-lookup"><span data-stu-id="58b09-248">Run:</span></span>

    ``` syntax
    Set-ADUser $strAlias -Enabled $True
    ```

7.  <span data-ttu-id="58b09-249">Si vous décidez que le mot de passe n’expire pas, vous pouvez également définir cette option avec des applets de commande PowerShell.</span><span class="sxs-lookup"><span data-stu-id="58b09-249">If you decide to have the password not expire, you can set that with PowerShell cmdlets too.</span></span> <span data-ttu-id="58b09-250">Consultez [Gestion des mots de passe](password-management-for-surface-hub-device-accounts.md) pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="58b09-250">See [Password management](password-management-for-surface-hub-device-accounts.md) for more information.</span></span>

    ``` syntax
    Set-ADUser $strAlias -PasswordNeverExpires $True
    ```

### <a href="" id="create-device-acct-exch-skype-for-business"></a><span data-ttu-id="58b09-251">Activer le compte avec SkypeEntreprise</span><span class="sxs-lookup"><span data-stu-id="58b09-251">Enable the account with Skype for Business</span></span>

<span data-ttu-id="58b09-252">Activez le compte d’appareil avec SkypeEntreprise.</span><span class="sxs-lookup"><span data-stu-id="58b09-252">Enable the device account with Skype for Business.</span></span>

<span data-ttu-id="58b09-253">Pour activer SkypeEntreprise, votre environnement doit respecter la configuration suivante:</span><span class="sxs-lookup"><span data-stu-id="58b09-253">In order to enable Skype for Business, your environment will need to meet the following prerequisites:</span></span>

-   <span data-ttu-id="58b09-254">Vous devez avoir un plan autonome 2 ou une version ultérieure de Skype entreprise Online dans votre offre Office 365.</span><span class="sxs-lookup"><span data-stu-id="58b09-254">You'll need to have Skype for Business Online Standalone Plan 2 or higher in your O365 plan.</span></span> <span data-ttu-id="58b09-255">L’abonnement doit prendre en charge la fonctionnalité Conférence.</span><span class="sxs-lookup"><span data-stu-id="58b09-255">The plan needs to support conferencing capability.</span></span>
-   <span data-ttu-id="58b09-256">Si vous avez besoin d’une voix entreprise (RTC) avec des fournisseurs de service de téléphonie pour le surface Hub, vous devez disposer d’un plan autonome 3 de Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="58b09-256">If you need Enterprise Voice (PSTN telephony) using telephony service providers for the Surface Hub, you need Skype for Business Online Standalone Plan 3.</span></span>
-   <span data-ttu-id="58b09-257">Vos utilisateurs clients doivent disposer de boîtes aux lettres Exchange.</span><span class="sxs-lookup"><span data-stu-id="58b09-257">Your tenant users must have Exchange mailboxes.</span></span>
-   <span data-ttu-id="58b09-258">Votre compte surface Hub nécessite une licence de plan autonome 2 de Skype entreprise Online ou une licence de plan autonome 3 de Skype entreprise Online, mais elle ne nécessite pas de licence Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="58b09-258">Your Surface Hub account does require a Skype for Business Online Standalone Plan 2 or Skype for Business Online Standalone Plan 3 license, but it does not require an Exchange Online license.</span></span>

1.  <span data-ttu-id="58b09-259">Commencez par créer une session PowerShell à distance à partir d’un PC.</span><span class="sxs-lookup"><span data-stu-id="58b09-259">Start by creating a remote PowerShell session from a PC.</span></span>

    ```PowerShell
    Import-Module SkypeOnlineConnector
    $cssess=New-CsOnlineSession -Credential $cred
    Import-PSSession $cssess -AllowClobber
    ```

2. <span data-ttu-id="58b09-260">Récupérer votre pool d’bureaux d’enregistrement de compte surface Hub</span><span class="sxs-lookup"><span data-stu-id="58b09-260">Retrieve your Surface Hub account Registrar Pool</span></span>

<span data-ttu-id="58b09-261">Si vous n’êtes pas certain de la valeur à utiliser pour le paramètre `RegistrarPool` dans votre environnement, vous pouvez obtenir cette valeur à partir d’un utilisateur Skype Entreprise existant en utilisant l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="58b09-261">If you aren't sure what value to use for the `RegistrarPool` parameter in your environment, you can get the value from an existing Skype for Business user using this cmdlet:</span></span>

    ```PowerShell
    Get-CsOnlineUser -Identity ‘alice@contoso.microsoft.com’| fl *registrarpool*
    ```
    
3. <span data-ttu-id="58b09-262">Pour activer votre compte Surface Hub pour Skype Entreprise Server, exécutez l’applet de commande suivante:</span><span class="sxs-lookup"><span data-stu-id="58b09-262">To enable your Surface Hub account for Skype for Business Server, run this cmdlet:</span></span>

   ```PowerShell
   Enable-CsMeetingRoom -Identity $strEmail -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    





