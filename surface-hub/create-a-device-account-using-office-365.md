---
title: Créer un compte d’appareil à l’aide de l’interface utilisateur (Surface Hub v1)
description: Pour utiliser une IU graphique, créez un compte pour votre Surface Hub avec l’interface utilisateur Office365 ou le Centre d’administration Exchange.
ms.assetid: D11BCDC4-DABA-4B9A-9ECB-58E02CC8218C
ms.reviewer: ''
manager: laurawi
keywords: créer un compte d’appareil, interface utilisateur Office 365, Centre d’administration Exchange, Centre d’administration Microsoft 365, Skype Entreprise, stratégie de boîte aux lettres d’appareil mobile
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 05/04/2018
ms.localizationpriority: medium
ms.openlocfilehash: dd19e2fd2417acd29e71c7555e94ee849fbc1bec
ms.sourcegitcommit: 32b6c25698479fa289f642c5b5761ff3be15b686
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/08/2021
ms.locfileid: "11318008"
---
# <span data-ttu-id="f6956-104">Créer un compte d’appareil à l’aide de l’interface utilisateur (Surface Hub v1)</span><span class="sxs-lookup"><span data-stu-id="f6956-104">Create a device account using UI (Surface Hub v1)</span></span>

 > [!NOTE]
 ><span data-ttu-id="f6956-105">Cette page contient des informations sur le Surface Hub d’origine (v1).</span><span class="sxs-lookup"><span data-stu-id="f6956-105">This page includes information about the original Surface Hub (v1).</span></span> <span data-ttu-id="f6956-106">Pour Surface Hub 2S, voir [Créer un compte d’appareil Surface Hub 2S.](surface-hub-2s-account.md)</span><span class="sxs-lookup"><span data-stu-id="f6956-106">For Surface Hub 2S, see [Create Surface Hub 2S device account](surface-hub-2s-account.md).</span></span>

<span data-ttu-id="f6956-107">Pour utiliser une IU graphique, créez un compte pour votre MicrosoftSurfaceHub avec l’[interface utilisateur Office365](#create-device-acct-o365) ou le [Centre d’administration Exchange](#create-device-acct-eac).</span><span class="sxs-lookup"><span data-stu-id="f6956-107">If you prefer to use a graphical user interface, you can create a device account for your Microsoft Surface Hub with either the [Office 365 UI](#create-device-acct-o365) or the [Exchange Admin Center](#create-device-acct-eac).</span></span>

## <a href="" id="create-device-acct-o365"></a><span data-ttu-id="f6956-108">Créer un compte d’appareil à l’aide d’Office 365</span><span class="sxs-lookup"><span data-stu-id="f6956-108">Create a device account using Office 365</span></span>


1.  <span data-ttu-id="f6956-109">[Créez le compte dans le Centre d’administration Microsoft 365.](#create-device-acct-o365-admin-ctr)</span><span class="sxs-lookup"><span data-stu-id="f6956-109">[Create the account in the Microsoft 365 Admin Center](#create-device-acct-o365-admin-ctr).</span></span>
2.  <span data-ttu-id="f6956-110">[Créez une stratégie de boîte aux lettres d’appareil mobile (ActiveSync) à partir du Centre d’administration Exchange](#create-device-acct-o365-mbx-policy).</span><span class="sxs-lookup"><span data-stu-id="f6956-110">[Create a mobile device mailbox (ActiveSync) policy from the Microsoft Exchange Admin Center](#create-device-acct-o365-mbx-policy).</span></span>
3.  <span data-ttu-id="f6956-111">[Utiliser Windows PowerShell pour terminer la création du compte d’appareil](#create-device-acct-o365-complete-acct).</span><span class="sxs-lookup"><span data-stu-id="f6956-111">[Use PowerShell to complete device account creation](#create-device-acct-o365-complete-acct).</span></span>
4.  <span data-ttu-id="f6956-112">[Utilisez PowerShell pour configurer les propriétés Exchange du compte](#create-device-acct-o365-configure-exch-prop).</span><span class="sxs-lookup"><span data-stu-id="f6956-112">[Use PowerShell to configure Exchange properties of the account](#create-device-acct-o365-configure-exch-prop).</span></span>
5.  <span data-ttu-id="f6956-113">[Activez le compte d’appareil avec SkypeEntreprise.](#create-device-acct-o365-skype-for-business).</span><span class="sxs-lookup"><span data-stu-id="f6956-113">[Enable the account with Skype for Business](#create-device-acct-o365-skype-for-business).</span></span>

### <a href="" id="create-device-acct-o365-admin-ctr"></a><span data-ttu-id="f6956-114">Créer le compte dans le Centre d’administration</span><span class="sxs-lookup"><span data-stu-id="f6956-114">Create the account in the admin center</span></span>

1.  <span data-ttu-id="f6956-115">Connectez-vous à Office 365 en visitant [https://portal.office.com](https://portal.office.com) .</span><span class="sxs-lookup"><span data-stu-id="f6956-115">Sign in to Office 365 by visiting [https://portal.office.com](https://portal.office.com).</span></span>

2.  <span data-ttu-id="f6956-116">Fournissez les informations d’identification d’administration de votre client Office365.</span><span class="sxs-lookup"><span data-stu-id="f6956-116">Provide the admin credentials for your Office 365 tenant.</span></span> <span data-ttu-id="f6956-117">Cela vous permettra d’aller dans votre Centre d’administration Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f6956-117">This will take you to your Microsoft 365 Admin Center.</span></span>

    > [!div class="mx-imgBorder"]
    > ![Centre d’administration Microsoft 365.](images/setupdeviceaccto365-02.png)

3. <span data-ttu-id="f6956-119">Dans le Centre d’administration, accédez à **Ressources** dans le panneau gauche, puis cliquez sur **Salles & équipement.**</span><span class="sxs-lookup"><span data-stu-id="f6956-119">In the admin center, navigate to **Resources** in the left panel, and then click **Rooms & equipment**.</span></span>

    > [!div class="mx-imgBorder"]
    > ![Option Salles &'équipement dans le Centre d’administration](images/room-equipment.png)

4. <span data-ttu-id="f6956-121">Cliquez sur **Ajouter** pour créer un nouveau compte de salle.</span><span class="sxs-lookup"><span data-stu-id="f6956-121">Click **Add** to create a new Room account.</span></span> <span data-ttu-id="f6956-122">Entrez un nom d'affichage et une adresse e-mail pour le compte, puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="f6956-122">Enter a display name and email address for the account, and then click **Add**.</span></span>

    > [!div class="mx-imgBorder"]
    > ![Créer une nouvelle fenêtre de compte de salle](images/room-add.png)

5. <span data-ttu-id="f6956-124">Sélectionnez le compte de salle que vous venez de créer dans la liste Utilisateurs actifs.</span><span class="sxs-lookup"><span data-stu-id="f6956-124">Select the Room account you just created in the Active Users list.</span></span> <span data-ttu-id="f6956-125">Dans le volet droit, vous pouvez voir les propriétés du compte et plusieurs actions facultatives.</span><span class="sxs-lookup"><span data-stu-id="f6956-125">In the right panel, you can see the account properties and several optional actions.</span></span> <span data-ttu-id="f6956-126">Cliquez sur **Réinitialiser le mot de passe** pour modifier le mot de passe, décochez la case demandant aux **utilisateurs de modifier leur mot de passe lors de leur première connexion**, car il n’est pas possible de modifier le mot de passe à partir du flux de connexion Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="f6956-126">Click **Reset password** to change the password, and unselect **Make this user change their password when they first sign in**, because it is not possible to change the password from the Surface Hub sign-in flow.</span></span>

6. <span data-ttu-id="f6956-127">Cliquez sur **Modifier** dans la section **Licence attribuée**, puis sur la flèche déroulante en regard de la licence appropriée pour développer les détails.</span><span class="sxs-lookup"><span data-stu-id="f6956-127">In the **Assigned license** section, click **Edit**, and then click the dropdown arrow next to the appropriate license to expand the details.</span></span> <span data-ttu-id="f6956-128">Sélectionnez un emplacement d’utilisateur, puis dans la liste des licences, activez **Skype Entreprise Online (Plan 2)**, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="f6956-128">Select a user location, and in the list of licenses, toggle on **Skype for Business Online (Plan 2)**, and then click **Save**.</span></span> <span data-ttu-id="f6956-129">La licence peut varier en fonction de votre organisation (par exemple, vous disposez peut-être du plan2 ou du plan3).</span><span class="sxs-lookup"><span data-stu-id="f6956-129">The license may vary depending on your organization (for example, you might have Plan 2 or Plan 3).</span></span>

### <a href="" id="create-device-acct-o365-mbx-policy"></a><span data-ttu-id="f6956-130">Créer une stratégie de boîte aux lettres d’appareil mobile (ActiveSync) à partir du Centre d’administration Exchange</span><span class="sxs-lookup"><span data-stu-id="f6956-130">Create a mobile device mailbox (ActiveSync) policy from the Exchange Admin Center</span></span>

1.  <span data-ttu-id="f6956-131">Dans le panneau gauche du Centre d’administration, cliquez sur **ADMIN,** puis sur **Exchange**.</span><span class="sxs-lookup"><span data-stu-id="f6956-131">In the admin center’s left panel, click **ADMIN**, and then click **Exchange**.</span></span>

    > [!div class="mx-imgBorder"]
    > ![centre d’administration, affichant les utilisateurs exchange actifs.](images/setupdeviceaccto365-08.png)

2.  <span data-ttu-id="f6956-133">Un autre onglet s’ouvre sur votre navigateur pour accéder au Centre d’administration Exchange, où vous pouvez créer et définir le paramètre de boîte aux lettres du Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="f6956-133">This will open another tab on your browser to take you to the Exchange Admin Center, where you can create and set the Mailbox Setting for Surface Hub.</span></span>

    > [!div class="mx-imgBorder"]
    > ![Centre d’administration Exchange.](images/setupdeviceaccto365-09.png)

3.  <span data-ttu-id="f6956-135">Pour créer une stratégie de boîte aux lettres d’appareil mobile, cliquez sur **Mobile** dans le volet gauche, puis sur **Stratégies de boîte aux lettres de périphérique mobile**.</span><span class="sxs-lookup"><span data-stu-id="f6956-135">To create a Mobile Device Mailbox Policy, click **Mobile** from the left panel and then click **Mobile device mailbox policies**.</span></span> <span data-ttu-id="f6956-136">Les Surfaces Hub requièrent un compte doté d’une stratégie de boîte aux lettres d’appareil mobile qui ne nécessite pas de mot de passe. Ainsi, si vous avez déjà une stratégie existante qui correspond à cette exigence, vous pouvez l’appliquer au compte.</span><span class="sxs-lookup"><span data-stu-id="f6956-136">Surface Hubs require an account with a mobile device mailbox policy that does not require a password, so if you already have an existing policy that matches this requirement, you can apply that policy to the account.</span></span> <span data-ttu-id="f6956-137">Dans le cas contraire, procédez comme suit pour en créer une nouvelle à utiliser uniquement pour les comptes d’appareil Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="f6956-137">Otherwise use the following steps to create a new one to be used only for Surface Hub device accounts.</span></span>

    > [!div class="mx-imgBorder"]
    > ![Centre d’administration Exchange - création d’une stratégie de boîte aux lettres d’appareil mobile.](images/setupdeviceaccto365-10.png)

4.  <span data-ttu-id="f6956-139">Pour créer une nouvelle stratégie de boîte aux lettres d’appareil mobile Surface Hub, cliquez sur le bouton **+** dans les commandes situées au-dessus de la liste des stratégies pour en ajouter une nouvelle.</span><span class="sxs-lookup"><span data-stu-id="f6956-139">To create a New Surface Hub mobile device mailbox policy, click the **+** button from the controls above the list of policies to add a new policy.</span></span> <span data-ttu-id="f6956-140">Indiquez un nom qui vous aidera à distinguer cette stratégie des autres comptes d’appareil (par exemple, *SurfaceHubDeviceMobilePolicy*).</span><span class="sxs-lookup"><span data-stu-id="f6956-140">For the name, provide a name that will help you distinguish this policy from other device accounts (for example, *SurfaceHubDeviceMobilePolicy*).</span></span> <span data-ttu-id="f6956-141">Assurez-vous que la stratégie ne nécessite pas de mot de passe pour les appareils affectés à celle-ci. Par conséquent, veillez à ce que la case **Exiger un mot de passe** soit décochée, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="f6956-141">Make sure the policy does not require a password for the devices assigned to, so make sure **Require a Password** remains unchecked, then click **Save**.</span></span>

    ![Image montrant une nouvelle stratégie d’appareil mobile.](images/setupdeviceaccto365-11.png)

5.  <span data-ttu-id="f6956-143">Après avoir créé la stratégie de boîte aux lettres d’appareil mobile, revenez au **Centre d’administration Exchange** dans lequel s’affiche la nouvelle stratégie.</span><span class="sxs-lookup"><span data-stu-id="f6956-143">After you have created the new mobile device mailbox policy, go back to the **Exchange Admin Center** and you will see the new policy listed.</span></span>

    > [!div class="mx-imgBorder"]
    > ![Image montrant une nouvelle stratégie de boîte aux lettres d’appareil mobile dans le Centre d’administration Exchange.](images/setupdeviceaccto365-12.png)



### <a href="" id="create-device-acct-o365-complete-acct"></a><span data-ttu-id="f6956-145">Utiliser Windows PowerShell pour terminer la création du compte d’appareil</span><span class="sxs-lookup"><span data-stu-id="f6956-145">Use PowerShell to complete device account creation</span></span>

<span data-ttu-id="f6956-146">À partir de là, vous devrez terminer le processus de création de compte à l’aide de PowerShell pour définir une configuration.</span><span class="sxs-lookup"><span data-stu-id="f6956-146">From here on, you'll need to finish the account creation process using PowerShell to set up some configuration.</span></span>

<span data-ttu-id="f6956-147">Pour exécuter les applets de commande utilisées par ces scripts PowerShell, les éléments suivants doivent être installés pour la console d’administration PowerShell:</span><span class="sxs-lookup"><span data-stu-id="f6956-147">In order to run cmdlets used by these PowerShell scripts, the following must be installed for the admin PowerShell console:</span></span>

-   [<span data-ttu-id="f6956-148">assistant Microsoft Online Services Sign-In pour les professionnels de l’informatique RTW</span><span class="sxs-lookup"><span data-stu-id="f6956-148">Microsoft Online Services Sign-In Assistant for IT Professionals RTW</span></span>](https://www.microsoft.com/download/details.aspx?id=41950)
-   [<span data-ttu-id="f6956-149">Module Windows Active Directory pour Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f6956-149">Windows Azure Active Directory Module for Windows PowerShell</span></span>](https://www.microsoft.com/web/handlers/webpi.ashx/getinstaller/WindowsAzurePowershellGet.3f.3f.3fnew.appids)
-   [<span data-ttu-id="f6956-150">Skype Entreprise Online, module Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f6956-150">Skype for Business Online, Windows PowerShell Module</span></span>](https://www.microsoft.com/download/details.aspx?id=39366)

<span data-ttu-id="f6956-151">Installez le module suivant dans PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f6956-151">Install the following module in PowerShell.</span></span>

```powershell
install-module AzureAD
Install-module MsOnline
```

### <span data-ttu-id="f6956-152">Connexion aux services en ligne</span><span class="sxs-lookup"><span data-stu-id="f6956-152">Connecting to online services</span></span>

1.  <span data-ttu-id="f6956-153">Exécutez Windows PowerShell en tant qu’administrateur.</span><span class="sxs-lookup"><span data-stu-id="f6956-153">Run Windows PowerShell as Administrator.</span></span>

    > [!div class="mx-imgBorder"]
    > ![Image montrant comment démarrer Windows PowerShell et l’exécuter en tant qu’administrateur.](images/setupdeviceaccto365-17.png)

2.  <span data-ttu-id="f6956-155">Créez un objet Informations d’identification, puis créez une nouvelle session qui se connecte à Skype Entreprise Online. Indiquez ensuite le compte d’administrateur du client global, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f6956-155">Create a Credentials object, then create a new session that connects to Skype for Business Online, and provide the global tenant administrator account, then click **OK**.</span></span>

    ![Image relative à la demande d’informations d’identification Windows PowerShell.](images/setupdeviceaccto365-18.png)

3.  <span data-ttu-id="f6956-157">Pour se connecter à Microsoft Online Services, exécutez la commande suivante:</span><span class="sxs-lookup"><span data-stu-id="f6956-157">To connect to Microsoft Online Services, run:</span></span>

    ```powershell
    Connect-MsolService -Credential $Cred
    ```

    ![Image montrant une applet de commande PowerShell.](images/setupdeviceaccto365-19.png)

4.  <span data-ttu-id="f6956-159">À présent pour vous connecter à Skype Entreprise Online, exécutez la commande suivante:</span><span class="sxs-lookup"><span data-stu-id="f6956-159">Now to connect to Skype for Business Online Services, run:</span></span>

    ```powershell
    $sfbsession = New-CsOnlineSession -Credential $cred
    ```

    ![Image montrant une applet de commande PowerShell.](images/setupdeviceaccto365-20.png)

5.  <span data-ttu-id="f6956-161">Enfin, pour vous connecter aux services Exchange Online, exécutez la commande suivante:</span><span class="sxs-lookup"><span data-stu-id="f6956-161">Finally, to connect to Exchange Online Services, run:</span></span>

    ```powershell
    $exchangeSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://outlook.office365.com/powershell-liveid/" -Credential $cred -Authentication "Basic" –AllowRedirection
    ```

    ![Image montrant une applet de commande PowerShell.](images/setupdeviceaccto365-21.png)

6.  <span data-ttu-id="f6956-163">Maintenant, vous devez importer les sessions Skype Entreprise Online et Exchange Online que vous venez de créer pour importer les commandes Exchange et Skype afin de les utiliser localement.</span><span class="sxs-lookup"><span data-stu-id="f6956-163">Now you have to import the Skype for Business Online Session and the Exchange Online session you have just created, which will import the Exchange and Skype Commands so you can use them locally.</span></span>

    ```powershell
    Import-PSSession $exchangesession -AllowClobber -WarningAction SilentlyContinue
    Import-PSSession $sfbsession -AllowClobber -WarningAction SilentlyContinue
    ```

    <span data-ttu-id="f6956-164">Notez que cette opération peut prendre un certain temps.</span><span class="sxs-lookup"><span data-stu-id="f6956-164">Note that this could take a while to complete.</span></span>

    ![Image montrant une applet de commande PowerShell.](images/setupdeviceaccto365-22.png)

7.  <span data-ttu-id="f6956-166">Une fois que vous êtes connecté aux services en ligne, vous devez encore exécuter quelques applets de commande pour configurer ce compte comme compte d’appareil Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="f6956-166">Once you’re connected to the online services you need to run a few more cmdlets to configure this account as a Surface Hub device account.</span></span>

### <a href="" id="create-device-acct-o365-configure-exch-prop"></a><span data-ttu-id="f6956-167">Utiliser PowerShell pour configurer les propriétés Exchange du compte</span><span class="sxs-lookup"><span data-stu-id="f6956-167">Use PowerShell to configure Exchange properties of the account</span></span>

<span data-ttu-id="f6956-168">Maintenant que vous êtes connecté aux services en ligne, vous pouvez terminer la configuration du compte d’appareil.</span><span class="sxs-lookup"><span data-stu-id="f6956-168">Now that you're connected to the online services, you can finish setting up the device account.</span></span> <span data-ttu-id="f6956-169">Vous allez utiliser l’adresse électronique du compte d’appareil pour effectuer les actions suivantes:</span><span class="sxs-lookup"><span data-stu-id="f6956-169">You'll use the device account email address to:</span></span>

-   <span data-ttu-id="f6956-170">Modifier le type de boîte aux lettres pour le convertir de «standard» à «de salle».</span><span class="sxs-lookup"><span data-stu-id="f6956-170">Change the mailbox type from regular to room.</span></span>
-   <span data-ttu-id="f6956-171">Définir le mot de passe et activer le compte de boîte aux lettres de salle</span><span class="sxs-lookup"><span data-stu-id="f6956-171">Set the password and enable the room mailbox account</span></span>
-   <span data-ttu-id="f6956-172">Modifier les différentes propriétés d’Exchange</span><span class="sxs-lookup"><span data-stu-id="f6956-172">Change various Exchange properties</span></span>
-   <span data-ttu-id="f6956-173">Définir le mot de passe du compte d’utilisateur de sorte qu’il n’expire jamais.</span><span class="sxs-lookup"><span data-stu-id="f6956-173">Set the user account password to never expire.</span></span>

1.  <span data-ttu-id="f6956-174">Vous devez entrer l’adresse de messagerie du compte et créer une variable avec la valeur suivante:</span><span class="sxs-lookup"><span data-stu-id="f6956-174">You’ll need to enter the account’s mail address and create a variable with that value:</span></span>

    ```powershell
    $mailbox = (Get-Mailbox <your device account’s alias>)
    ```

    <span data-ttu-id="f6956-175">Pour stocker la valeur, obtenez-la à partir de la boîte aux lettres à l’aide de la commande suivante:</span><span class="sxs-lookup"><span data-stu-id="f6956-175">To store the value get it from the mailbox:</span></span>

    ```powershell
    $strEmail = $mailbox.WindowsEmailAddress
    ```

    <span data-ttu-id="f6956-176">Imprimez la valeur à l’aide de la commande suivante:</span><span class="sxs-lookup"><span data-stu-id="f6956-176">Print the value:</span></span>

    ```powershell
    $strEmail
    ```

    <span data-ttu-id="f6956-177">L’adresse de messagerie appropriée s’affiche.</span><span class="sxs-lookup"><span data-stu-id="f6956-177">You will see the correct email address.</span></span>

    ![Image montrant une applet de commande PowerShell.](images/setupdeviceaccto365-23.png)

2. <span data-ttu-id="f6956-179">Exécutez l’cmdlet suivante :</span><span class="sxs-lookup"><span data-stu-id="f6956-179">Run the following cmdlet:</span></span>

    ```powershell
    Set-CASMailbox $strEmail  -ActiveSyncMailboxPolicy "SurfaceHubDeviceMobilePolicy"
    ```

4.  <span data-ttu-id="f6956-180">Diverses propriétés Exchange peuvent être définies sur le compte d’appareil pour améliorer l’expérience de réunion.</span><span class="sxs-lookup"><span data-stu-id="f6956-180">Various Exchange properties can be set on the device account to improve the meeting experience.</span></span> <span data-ttu-id="f6956-181">Vous pouvez voir les propriétés à définir dans la section [Propriétés Exchange](exchange-properties-for-surface-hub-device-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="f6956-181">You can see which properties need to be set in the [Exchange properties](exchange-properties-for-surface-hub-device-accounts.md) section.</span></span>

    ```powershell
    Set-CalendarProcessing -Identity $strEmail -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts   $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
    Set-CalendarProcessing -Identity $strEmail -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
    ```

    ![Image montrant une applet de commande PowerShell.](images/setupdeviceaccto365-26.png)

5.  <span data-ttu-id="f6956-183">Si vous décidez que le mot de passe n’expire pas, vous pouvez également définir cette option avec des applets de commande PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f6956-183">If you decide to have the password not expire, you can set that with PowerShell cmdlets too.</span></span> <span data-ttu-id="f6956-184">Consultez [Gestion des mots de passe](password-management-for-surface-hub-device-accounts.md) pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="f6956-184">See [Password management](password-management-for-surface-hub-device-accounts.md) for more information.</span></span>

    ```powershell
    Set-MsolUser -UserPrincipalName $strEmail -PasswordNeverExpires $True
    ```

### <a href="" id="create-device-acct-o365-skype-for-business"></a><span data-ttu-id="f6956-185">Activer le compte avec SkypeEntreprise</span><span class="sxs-lookup"><span data-stu-id="f6956-185">Enable the account with Skype for Business</span></span>

<span data-ttu-id="f6956-186">Activez le compte d’appareil avec SkypeEntreprise.</span><span class="sxs-lookup"><span data-stu-id="f6956-186">Enable the device account with Skype for Business.</span></span>

<span data-ttu-id="f6956-187">Pour activer SkypeEntreprise, votre environnement doit respecter la configuration suivante:</span><span class="sxs-lookup"><span data-stu-id="f6956-187">In order to enable Skype for Business, your environment will need to meet the following prerequisites:</span></span>

-   <span data-ttu-id="f6956-188">Vous devez avoir Skype Entreprise Online Plan autonome 2 ou supérieur dans votre plan O365.</span><span class="sxs-lookup"><span data-stu-id="f6956-188">You'll need to have Skype for Business Online Standalone Plan 2 or higher in your O365 plan.</span></span> <span data-ttu-id="f6956-189">L’abonnement doit prendre en charge la fonctionnalité Conférence.</span><span class="sxs-lookup"><span data-stu-id="f6956-189">The plan needs to support conferencing capability.</span></span>
-   <span data-ttu-id="f6956-190">Si vous avez besoin Voix Entreprise (téléphonie PSTN) à l’aide de fournisseurs de services de téléphonie pour le Surface Hub, vous avez besoin de Skype Entreprise Online Plan autonome 3.</span><span class="sxs-lookup"><span data-stu-id="f6956-190">If you need Enterprise Voice (PSTN telephony) using telephony service providers for the Surface Hub, you need Skype for Business Online Standalone Plan 3.</span></span>
-   <span data-ttu-id="f6956-191">Vos utilisateurs clients doivent disposer de boîtes aux lettres Exchange.</span><span class="sxs-lookup"><span data-stu-id="f6956-191">Your tenant users must have Exchange mailboxes.</span></span>
-   <span data-ttu-id="f6956-192">Votre compte Surface Hub nécessite une licence Skype Entreprise Online Plan autonome 2 ou Skype Entreprise Online Plan autonome 3, mais il ne nécessite pas de licence Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="f6956-192">Your Surface Hub account does require a Skype for Business Online Standalone Plan 2 or Skype for Business Online Standalone Plan 3 license, but it does not require an Exchange Online license.</span></span>

1.  <span data-ttu-id="f6956-193">Commencez par créer une session PowerShell à distance à partir d’un PC.</span><span class="sxs-lookup"><span data-stu-id="f6956-193">Start by creating a remote PowerShell session from a PC.</span></span>

    ```PowerShell
    Import-Module SkypeOnlineConnector
    $cssess=New-CsOnlineSession -Credential $cred
    Import-PSSession $cssess -AllowClobber
    ```

2.  <span data-ttu-id="f6956-194">Pour activer votre compte SurfaceHub pour Skype Entreprise Server, exécutez l’applet de commande suivante:</span><span class="sxs-lookup"><span data-stu-id="f6956-194">To enable your Surface Hub account for Skype for Business Server, run this cmdlet:</span></span>

    ```powershell
    Enable-CsMeetingRoom -Identity $strEmail -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
    ```

     <span data-ttu-id="f6956-195">Si vous n’êtes pas certain de la valeur à utiliser pour le paramètre`RegistrarPool` dans votre environnement, vous pouvez obtenir cette valeur à partir d’un utilisateur Skype Entreprise existant en utilisant l’applet de commande suivante:</span><span class="sxs-lookup"><span data-stu-id="f6956-195">If you aren't sure what value to use for the `RegistrarPool` parameter in your environment, you can get the value from an existing Skype for Business user using this cmdlet:</span></span>

    ```powershell
    Get-CsOnlineUser -Identity ‘alice@contoso.microsoft.com’| fl *registrarpool*
    ```

## <a href="" id="create-device-acct-eac"></a><span data-ttu-id="f6956-196">Créer un compte d’appareil à l’aide du Centre d’administration Exchange</span><span class="sxs-lookup"><span data-stu-id="f6956-196">Create a device account using the Exchange Admin Center</span></span>

>[!NOTE]
><span data-ttu-id="f6956-197">Cette méthode ne fonctionne que si vous synchronisez à partir d’un annuaire Active Directory local.</span><span class="sxs-lookup"><span data-stu-id="f6956-197">This method will only work if you are syncing from an on-premises Active Directory.</span></span>

<span data-ttu-id="f6956-198">Vous pouvez utiliser le Centre d’administration Exchange pour créer un compte d’appareil:</span><span class="sxs-lookup"><span data-stu-id="f6956-198">You can use the Exchange Admin Center to create a device account:</span></span>

1.  <span data-ttu-id="f6956-199">[Créez un compte et une boîte aux lettres à l’aide du Centre d’administration Exchange](#create-device-acct-exch-admin-ctr).</span><span class="sxs-lookup"><span data-stu-id="f6956-199">[Create an account and mailbox with the Exchange Admin Center](#create-device-acct-exch-admin-ctr).</span></span>
2.  <span data-ttu-id="f6956-200">[Créez une stratégie de boîte aux lettres d’appareil mobile à partir du Centre d’administration Exchange](#create-device-acct-exch-mbx-policy).</span><span class="sxs-lookup"><span data-stu-id="f6956-200">[Create a mobile device mailbox policy from the Exchange Admin Center](#create-device-acct-exch-mbx-policy).</span></span>
3.  <span data-ttu-id="f6956-201">[Utilisez PowerShell pour configurer le compte](#create-device-acct-exch-powershell-conf).</span><span class="sxs-lookup"><span data-stu-id="f6956-201">[Use PowerShell to configure the account](#create-device-acct-exch-powershell-conf).</span></span>
4.  <span data-ttu-id="f6956-202">[Activez le compte avec SkypeEntreprise](#create-device-acct-exch-skype-for-business).</span><span class="sxs-lookup"><span data-stu-id="f6956-202">[Enable the account with Skype for Business](#create-device-acct-exch-skype-for-business).</span></span>

### <a href="" id="create-device-acct-exch-admin-ctr"></a><span data-ttu-id="f6956-203">Créer un compte et une boîte aux lettres à l’aide du Centre d’administration Exchange</span><span class="sxs-lookup"><span data-stu-id="f6956-203">Create an account and mailbox with the Exchange Admin Center</span></span>

1.  <span data-ttu-id="f6956-204">Connectez-vous à votre Centre d’administration Exchange à l’aide des informations d’identification d’administration Exchange.</span><span class="sxs-lookup"><span data-stu-id="f6956-204">Sign in to your Exchange Admin Center using Exchange admin credentials.</span></span>
2.  <span data-ttu-id="f6956-205">Une fois dans le Centre d’administration Exchange, accédez à **Destinataires** dans le volet gauche.</span><span class="sxs-lookup"><span data-stu-id="f6956-205">Once you are at the Exchange Admin Center (EAC), navigate to **Recipients** in the left panel.</span></span>

    ![Image montrant des boîtes aux lettres du Centre d’administration Exchange.](images/setupdeviceacctexch-01.png)

3.  <span data-ttu-id="f6956-207">Dans les commandes situées au-dessus de la liste des boîtes aux lettres, choisissez **+** pour en créer une, et indiquez un **Nom complet**, un **Nom**, et un **Nom d’ouverture de session de l’utilisateur**, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="f6956-207">On the controls above the list of mailboxess, choose **+** to create a new one, and provide a **Display name**, **Name**, and **User logon name**, and then click **Save**.</span></span>

    ![Image illustrant la création d’une nouvelle boîte aux lettres.](images/setupdeviceacctexch-02.png)

### <a href="" id="create-device-acct-exch-mbx-policy"></a><span data-ttu-id="f6956-209">Créer une stratégie de boîte aux lettres d’appareil mobile à partir du Centre d’administration Exchange</span><span class="sxs-lookup"><span data-stu-id="f6956-209">Create a mobile device mailbox policy from the Exchange Admin Center</span></span>

>[!NOTE]
><span data-ttu-id="f6956-210">Si vous souhaitez créer et affecter une stratégie au compte que vous avez créé et que vous utilisez Exchange 2010, recherchez les informations correspondantes concernant la création et l’attribution de stratégie lors de l’utilisation de la console de gestion Exchange (EMC).</span><span class="sxs-lookup"><span data-stu-id="f6956-210">If you want to create and assign a policy to the account you created, and are using Exchange 2010, look up the corresponding information regarding policy creation and policy assignment when using the EMC (Exchange management console).</span></span>

 

1.  <span data-ttu-id="f6956-211">Accédez au Centre d’administration Exchange.</span><span class="sxs-lookup"><span data-stu-id="f6956-211">Go to the Exchange Admin Center.</span></span>

    ![Image illustrant le Centre d’administration Exchange.](images/setupdeviceacctexch-03.png)

2.  <span data-ttu-id="f6956-213">Pour créer une stratégie de boîte aux lettres d’appareil mobile, cliquez sur **Mobile** dans le volet gauche, puis sur **Stratégies de boîte aux lettres de périphérique mobile**.</span><span class="sxs-lookup"><span data-stu-id="f6956-213">To create a mobile device mailbox policy, click **Mobile** from the left panel, then **Mobile device mailbox policies**.</span></span> <span data-ttu-id="f6956-214">Les Surfaces Hub requièrent un compte doté d’une stratégie de boîte aux lettres d’appareil mobile qui ne nécessite pas de mot de passe. Ainsi, si vous avez déjà une stratégie existante qui correspond à cette exigence, vous pouvez l’appliquer au compte.</span><span class="sxs-lookup"><span data-stu-id="f6956-214">Surface Hubs require an account with a mobile device mailbox policy that does not require a password, so if you already have an existing policy that matches this requirement, you can apply that policy to the account.</span></span> <span data-ttu-id="f6956-215">Dans le cas contraire, procédez comme suit pour en créer une nouvelle à utiliser uniquement pour les comptes d’appareil Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="f6956-215">Otherwise use the following steps to create a new one to be used only for Surface Hub device accounts.</span></span>

    ![Image illustrant la création d’une stratégie de boîte aux lettres d’appareil mobile à partir du Centre d’administration Exchange.](images/setupdeviceacctexch-05.png)

3.  <span data-ttu-id="f6956-217">Pour créer une nouvelle stratégie de boîte aux lettres de compte d’appareil mobile, cliquez sur le bouton **+** dans les commandes situées au-dessus de la liste des stratégies pour ajouter une nouvelle stratégie.</span><span class="sxs-lookup"><span data-stu-id="f6956-217">To create a new mobile device account mailbox policy, click the **+** button from the controls above the list of policies to add a new policy.</span></span> <span data-ttu-id="f6956-218">Indiquez un nom qui vous aidera à distinguer cette stratégie des autres comptes d’appareil (par exemple, *SurfaceHubDeviceMobilePolicy*).</span><span class="sxs-lookup"><span data-stu-id="f6956-218">For the name provide a name that will help you distinguish this policy from other device accounts (for example, *SurfaceHubDeviceMobilePolicy*).</span></span> <span data-ttu-id="f6956-219">La stratégie ne doit pas être protégée par mot de passe. Veillez donc à ce que la case **Exiger un mot de passe** reste décochée, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="f6956-219">The policy must not be password-protected, so make sure **Require a Password** remains unchecked, then click **Save**.</span></span>

    ![Image montrant une nouvelle stratégie de boîte aux lettres d’appareil mobile.](images/setupdeviceacctexch-06.png)

4.  <span data-ttu-id="f6956-221">Après avoir créé la stratégie de boîte aux lettres d’appareil mobile, revenez au Centre d’administration Exchange, dans lequel s’affiche la nouvelle stratégie.</span><span class="sxs-lookup"><span data-stu-id="f6956-221">After you have created the new mobile device mailbox policy, go back to the Exchange Admin Center and you will see the new policy listed.</span></span>

    ![Image montrant une nouvelle stratégie de boîte aux lettres d’appareil mobile dans le Centre d’administration Exchange.](images/setupdeviceacctexch-07.png)

5.  <span data-ttu-id="f6956-223">Pour appliquer la stratégie ActiveSync sans l’aide de PowerShell, vous pouvez procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="f6956-223">To apply the ActiveSync policy without using PowerShell, you can do the following:</span></span>

    -   <span data-ttu-id="f6956-224">Dans le Centre d’administration Exchange, cliquez sur **Destinataires** &gt; **Boîtes aux lettres**, puis sélectionnez une boîte aux lettres.</span><span class="sxs-lookup"><span data-stu-id="f6956-224">In the EAC, click **Recipients** &gt; **Mailboxes** and select a mailbox.</span></span>

        ![Image illustrant le Centre d’administration Exchange.](images/setupdeviceacctexch-08.png)

    -   <span data-ttu-id="f6956-226">Dans le volet **Détails**, faites défiler jusqu’à **Fonctionnalités téléphoniques et vocales** et cliquez sur **Afficher les détails** pour afficher l’écran **Paramètres du périphérique mobile**.</span><span class="sxs-lookup"><span data-stu-id="f6956-226">In the **Details** pane, scroll to **Phone and Voice Features** and click **View details** to display the **Mobile Device Details** screen.</span></span>

        ![Image montrant les informations de boîte aux lettres.](images/setupdeviceacctexch-09.png)

    -   <span data-ttu-id="f6956-228">La stratégie de boîte aux lettres d’appareil mobile actuellement affectée est affichée.</span><span class="sxs-lookup"><span data-stu-id="f6956-228">The mobile device mailbox policy that’s currently assigned is displayed.</span></span> <span data-ttu-id="f6956-229">Pour modifier la stratégie de boîte aux lettres d’appareil mobile, cliquez sur **Parcourir**.</span><span class="sxs-lookup"><span data-stu-id="f6956-229">To change the mobile device mailbox policy, click **Browse**.</span></span>

        ![Image montrant la stratégie de boîte aux lettres d’appareil mobile actuellement affectée.](images/setupdeviceacctexch-10.png)

    -   <span data-ttu-id="f6956-231">Choisissez la stratégie de boîte aux lettres d’appareil mobile appropriée dans la liste, cliquez sur **OK**, puis sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="f6956-231">Choose the appropriate mobile device mailbox policy from the list, click **OK** and then click **Save**.</span></span>

        ![Image montrant une liste des stratégies de boîte aux lettres d’appareil mobile. ](images/setupdeviceacctexch-11.png)

### <a href="" id="create-device-acct-exch-powershell-conf"></a><span data-ttu-id="f6956-233">Utiliser PowerShell pour configurer le compte</span><span class="sxs-lookup"><span data-stu-id="f6956-233">Use PowerShell to configure the account</span></span>

<span data-ttu-id="f6956-234">Maintenant que vous êtes connecté aux services en ligne, vous pouvez terminer la configuration du compte d’appareil.</span><span class="sxs-lookup"><span data-stu-id="f6956-234">Now that you're connected to the online services, you can finish setting up the device account.</span></span> <span data-ttu-id="f6956-235">Vous allez utiliser l’adresse électronique du compte d’appareil pour effectuer les actions suivantes:</span><span class="sxs-lookup"><span data-stu-id="f6956-235">You'll use the device account email address to:</span></span>

-   <span data-ttu-id="f6956-236">Modifier le type de boîte aux lettres pour le convertir de «standard» à «de salle».</span><span class="sxs-lookup"><span data-stu-id="f6956-236">Change the mailbox type from regular to room.</span></span>
-   <span data-ttu-id="f6956-237">Modifier les différentes propriétés d’Exchange</span><span class="sxs-lookup"><span data-stu-id="f6956-237">Change various Exchange properties</span></span>
-   <span data-ttu-id="f6956-238">Définir le mot de passe du compte d’utilisateur de sorte qu’il n’expire jamais.</span><span class="sxs-lookup"><span data-stu-id="f6956-238">Set the user account password to never expire.</span></span>

1.  <span data-ttu-id="f6956-239">Vous devez entrer l’adresse de messagerie du compte et créer une variable avec la valeur suivante:</span><span class="sxs-lookup"><span data-stu-id="f6956-239">You’ll need to enter the account’s mail address and create a variable with that value:</span></span>

    ```powershell
    $mailbox = (Get-Mailbox <your device account’s alias>)
    ```

    <span data-ttu-id="f6956-240">Pour stocker la valeur, obtenez-la à partir de la boîte aux lettres à l’aide de la commande suivante:</span><span class="sxs-lookup"><span data-stu-id="f6956-240">To store the value got it from the mailbox:</span></span>

    ```powershell
    $strEmail = $mailbox.WindowsEmailAddress
    ```

    <span data-ttu-id="f6956-241">Imprimez la valeur en exécutant la commande suivante:</span><span class="sxs-lookup"><span data-stu-id="f6956-241">Print the value by running:</span></span>

    ```powershell
    $strEmail
    ```

    <span data-ttu-id="f6956-242">L’adresse de messagerie appropriée s’affiche.</span><span class="sxs-lookup"><span data-stu-id="f6956-242">You will see the correct email address.</span></span>

2.  <span data-ttu-id="f6956-243">Vous devez convertir le compte en boîte aux lettres de salle. Exécutez donc :</span><span class="sxs-lookup"><span data-stu-id="f6956-243">You need to convert the account into a room mailbox, so run:</span></span>

    ```powershell
    Set-Mailbox $strEmail -Type Room
    ```

3.  <span data-ttu-id="f6956-244">Pour que le compte d’appareil puisse être authentifié sur une Surface Hub, vous devez activer le compte de boîte aux lettres de salle et définir un mot de passe, afin que le compte puisse être utilisé par l’appareil pour obtenir des informations de réunion à l’aide d’ActiveSync et se connecter à Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="f6956-244">In order for the device account to be authenticated on a Surface Hub, you need to enable the room mailbox account and set a password, so the account can be used by the device to get meeting information using ActiveSync and log in to Skype for Business.</span></span>

    ```powershell
    Set-Mailbox $strEmail -RoomMailboxPassword (ConvertTo-SecureString  -String "<your password>" -AsPlainText -Force) -EnableRoomMailboxAccount $true
    ```

4.  <span data-ttu-id="f6956-245">Diverses propriétés Exchange peuvent être définies sur le compte d’appareil pour améliorer l’expérience de réunion.</span><span class="sxs-lookup"><span data-stu-id="f6956-245">Various Exchange properties can be set on the device account to improve the meeting experience.</span></span> <span data-ttu-id="f6956-246">Vous pouvez voir les propriétés à définir dans la section [Propriétés Exchange](exchange-properties-for-surface-hub-device-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="f6956-246">You can see which properties need to be set in the [Exchange properties](exchange-properties-for-surface-hub-device-accounts.md) section.</span></span>

    ```powershell
    Set-CalendarProcessing -Identity $strEmail -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts   $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
    Set-CalendarProcessing -Identity $strEmail -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
    ```

5.  <span data-ttu-id="f6956-247">Nous devons maintenant définir quelques propriétés dans AD.</span><span class="sxs-lookup"><span data-stu-id="f6956-247">Now we have to set some properties in AD.</span></span> <span data-ttu-id="f6956-248">Pour ce faire, vous avez besoin de l’alias du compte (partie du nom d’utilisateur principal qui se transforme avant le «@»).</span><span class="sxs-lookup"><span data-stu-id="f6956-248">To do that, you need the alias of the account (this is the part of the UPN that becomes before the “@”).</span></span>

    ```powershell
    $strAlias = “<your device account’s alias>”
    ```

6.  <span data-ttu-id="f6956-249">L’utilisateur doit être activé dans AD avant de pouvoir s’authentifier avec un Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="f6956-249">The user needs to be enabled in AD before it can authenticate with a Surface Hub.</span></span> <span data-ttu-id="f6956-250">Exécutez la commande suivante:</span><span class="sxs-lookup"><span data-stu-id="f6956-250">Run:</span></span>

    ```powershell
    Set-ADUser $strAlias -Enabled $True
    ```

7.  <span data-ttu-id="f6956-251">Si vous décidez que le mot de passe n’expire pas, vous pouvez également définir cette option avec des applets de commande PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f6956-251">If you decide to have the password not expire, you can set that with PowerShell cmdlets too.</span></span> <span data-ttu-id="f6956-252">Consultez [Gestion des mots de passe](password-management-for-surface-hub-device-accounts.md) pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="f6956-252">See [Password management](password-management-for-surface-hub-device-accounts.md) for more information.</span></span>

    ```powershell
    Set-ADUser $strAlias -PasswordNeverExpires $True
    ```

### <a href="" id="create-device-acct-exch-skype-for-business"></a><span data-ttu-id="f6956-253">Activer le compte avec SkypeEntreprise</span><span class="sxs-lookup"><span data-stu-id="f6956-253">Enable the account with Skype for Business</span></span>

<span data-ttu-id="f6956-254">Activez le compte d’appareil avec SkypeEntreprise.</span><span class="sxs-lookup"><span data-stu-id="f6956-254">Enable the device account with Skype for Business.</span></span>

<span data-ttu-id="f6956-255">Pour activer SkypeEntreprise, votre environnement doit respecter la configuration suivante:</span><span class="sxs-lookup"><span data-stu-id="f6956-255">In order to enable Skype for Business, your environment will need to meet the following prerequisites:</span></span>

- <span data-ttu-id="f6956-256">Vous devez avoir Skype Entreprise Online Plan autonome 2 ou supérieur dans votre plan O365.</span><span class="sxs-lookup"><span data-stu-id="f6956-256">You'll need to have Skype for Business Online Standalone Plan 2 or higher in your O365 plan.</span></span> <span data-ttu-id="f6956-257">L’abonnement doit prendre en charge la fonctionnalité Conférence.</span><span class="sxs-lookup"><span data-stu-id="f6956-257">The plan needs to support conferencing capability.</span></span>
- <span data-ttu-id="f6956-258">Si vous avez besoin Voix Entreprise (téléphonie PSTN) à l’aide de fournisseurs de services de téléphonie pour le Surface Hub, vous avez besoin de Skype Entreprise Online Plan autonome 3.</span><span class="sxs-lookup"><span data-stu-id="f6956-258">If you need Enterprise Voice (PSTN telephony) using telephony service providers for the Surface Hub, you need Skype for Business Online Standalone Plan 3.</span></span>
- <span data-ttu-id="f6956-259">Vos utilisateurs clients doivent disposer de boîtes aux lettres Exchange.</span><span class="sxs-lookup"><span data-stu-id="f6956-259">Your tenant users must have Exchange mailboxes.</span></span>
- <span data-ttu-id="f6956-260">Votre compte Surface Hub nécessite une licence Skype Entreprise Online Plan autonome 2 ou Skype Entreprise Online Plan autonome 3, mais il ne nécessite pas de licence Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="f6956-260">Your Surface Hub account does require a Skype for Business Online Standalone Plan 2 or Skype for Business Online Standalone Plan 3 license, but it does not require an Exchange Online license.</span></span>

1. <span data-ttu-id="f6956-261">Commencez par créer une session PowerShell à distance à partir d’un PC.</span><span class="sxs-lookup"><span data-stu-id="f6956-261">Start by creating a remote PowerShell session from a PC.</span></span>

    ```PowerShell
    Import-Module SkypeOnlineConnector
    $cssess=New-CsOnlineSession -Credential $cred
    Import-PSSession $cssess -AllowClobber
    ```

2. <span data-ttu-id="f6956-262">Récupérez votre pool de bureaux d’enregistrement de comptes Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="f6956-262">Retrieve your Surface Hub account Registrar Pool.</span></span>

   <span data-ttu-id="f6956-263">Si vous n’êtes pas certain de la valeur à utiliser pour le paramètre `RegistrarPool` dans votre environnement, vous pouvez obtenir cette valeur à partir d’un utilisateur Skype Entreprise existant en utilisant l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="f6956-263">If you aren't sure what value to use for the `RegistrarPool` parameter in your environment, you can get the value from an existing Skype for Business user using this cmdlet:</span></span>

   ```PowerShell
   Get-CsOnlineUser -Identity ‘alice@contoso.microsoft.com’| fl *registrarpool*
   ```

3. <span data-ttu-id="f6956-264">Pour activer votre compte Surface Hub pour Skype Entreprise Server, exécutez l’applet de commande suivante:</span><span class="sxs-lookup"><span data-stu-id="f6956-264">To enable your Surface Hub account for Skype for Business Server, run this cmdlet:</span></span>

   ```PowerShell
   Enable-CsMeetingRoom -Identity $strEmail -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```