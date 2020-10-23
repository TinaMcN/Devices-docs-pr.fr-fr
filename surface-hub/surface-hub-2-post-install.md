---
title: Configurer Windows 10 Professionnel ou Entreprise sur Surface Hub 2
description: Cet article inclut des recommandations pour garantir une meilleure utilisation lors de l’utilisation d’un ordinateur de stylet et d’un grand écran personnalisés.
keywords: Surface Hub, Windows 10, ordinateur de bureau, installer, configuration
ms.prod: surface-hub
ms.mktglfcycl: deploy
ms.localizationpriority: low
ms.sitesec: library
ms.pagetype: deploy
audience: admin
manager: laurawi
ms.audience: itpro
author: greg-lindsay
ms.author: greglin
ms.collection: M365-modern-desktop
ms.topic: article
ms.date: 10/21/2020
appliesto:
- Surface Hub 2S
ms.openlocfilehash: a17d4b05e6ee5f7415fed62d96b9e0a62a6dc123
ms.sourcegitcommit: cbf237e59c97311bd8add3aae2a17738fe271ddc
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/23/2020
ms.locfileid: "11134402"
---
# <span data-ttu-id="65de7-104">Configurer Windows 10 Professionnel ou Entreprise sur Surface Hub 2</span><span class="sxs-lookup"><span data-stu-id="65de7-104">Configure Windows 10 Pro or Enterprise on Surface Hub 2</span></span>

<span data-ttu-id="65de7-105">Après avoir terminé le processus d’installation de la migration vers Windows 10 professionnel ou entreprise, vous pouvez effectuer les étapes suivantes pour configurer les applications et les paramètres sur votre surface Hub 2.</span><span class="sxs-lookup"><span data-stu-id="65de7-105">After you have completed the installation process of migrating to Windows 10 Pro or Enterprise, you can perform the following steps to configure apps and settings on your Surface Hub 2.</span></span> <span data-ttu-id="65de7-106">Ces étapes sont recommandées pour garantir la meilleure utilisation de cette fonction d’affichage du stylo et de l’écran grand écran.</span><span class="sxs-lookup"><span data-stu-id="65de7-106">These steps are recommended to ensure the best experience when using this personalized large screen touch and pen computer.</span></span>

<span data-ttu-id="65de7-107">Lors de cette procédure, il peut s’avérer utile d’utiliser un clavier et une souris sans fil.</span><span class="sxs-lookup"><span data-stu-id="65de7-107">When performing these steps, you might find it useful to use a wired or wireless keyboard and mouse.</span></span>

## <span data-ttu-id="65de7-108">Configurer les paramètres système</span><span class="sxs-lookup"><span data-stu-id="65de7-108">Configure system settings</span></span>

1. <span data-ttu-id="65de7-109">Connectez-vous à l’aide d’un compte disposant de privilèges d’administrateur local sur l’appareil.</span><span class="sxs-lookup"><span data-stu-id="65de7-109">Sign in with an account that has local administrator privileges on the device.</span></span>  

    - <span data-ttu-id="65de7-110">Sur les appareils disposant d’Azure AD, l’utilisateur qui exécute la jointure Azure AD est automatiquement ajouté au groupe d’administrateurs local.</span><span class="sxs-lookup"><span data-stu-id="65de7-110">On Azure AD joined devices, the user that performs the Azure AD join is automatically added to the local administrator group.</span></span> <span data-ttu-id="65de7-111">Les administrateurs généraux d’Azure AD et d’Azure AD sont [également administrateurs locaux](https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin).</span><span class="sxs-lookup"><span data-stu-id="65de7-111">Azure AD global administrators and Azure AD devices administrators are [also local administrators](https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin).</span></span> 
    
    - <span data-ttu-id="65de7-112">Vous pouvez taper **administrateurs .net localgroup** à une invite de commandes pour répertorier les comptes disposant de droits d’administrateur local.</span><span class="sxs-lookup"><span data-stu-id="65de7-112">You can type **net localgroup administrators** at a command prompt to list the accounts that have local administrator rights.</span></span>
    
2. <span data-ttu-id="65de7-113">Renommez l’appareil en utilisant un nom convivial, par exemple: **nom_utilisateur-SHub-Desktop**.</span><span class="sxs-lookup"><span data-stu-id="65de7-113">Rename the device using a friendly name, for example: **username-SHub-Desktop**.</span></span>

3. <span data-ttu-id="65de7-114">Sélectionnez **Démarrer**  >  les**paramètres**des  >  **comptes**pour  >  **synchroniser vos paramètres** et désactiver les **paramètres de synchronisation** .</span><span class="sxs-lookup"><span data-stu-id="65de7-114">Select **Start** > **Settings** > **Accounts** > **Sync your settings** and turn **Sync settings** off.</span></span> 

    - <span data-ttu-id="65de7-115">Les paramètres utilisés ici sont destinés à permettre une meilleure utilisation de l’affichage des fonctions visuelles de grande taille et, par conséquent, vous ne souhaitez pas synchroniser d’autres appareils.</span><span class="sxs-lookup"><span data-stu-id="65de7-115">The settings used here are intended to enable the best large-screen touch experience, and therefore you may not want to sync other devices.</span></span>
    
4. <span data-ttu-id="65de7-116">Redémarrez l’appareil.</span><span class="sxs-lookup"><span data-stu-id="65de7-116">Restart the device.</span></span>

## <span data-ttu-id="65de7-117">Activez le clavier tactile et le pavé tactile.</span><span class="sxs-lookup"><span data-stu-id="65de7-117">Enable the touch keyboard and touchpad</span></span>

1. <span data-ttu-id="65de7-118">Appuyez de façon prolongée ou cliquez avec le bouton droit sur la barre des tâches, puis sélectionnez **afficher le bouton du clavier tactile** et **afficher le bouton du pavé**tactile.</span><span class="sxs-lookup"><span data-stu-id="65de7-118">Tap and hold or right-click the taskbar and then select **Show touch keyboard button** and **Show touchpad button**.</span></span> 

    - <span data-ttu-id="65de7-119">Le clavier tactile est utile pour la saisie directe de l’utilisateur, et le pavé tactile virtuel permet d’effectuer des sélections précises, de pointage sur les info-bulles ou d’appuyer longuement sur un clic avec le bouton droit.</span><span class="sxs-lookup"><span data-stu-id="65de7-119">The touch keyboard is helpful for direct user input, and the virtual touchpad helps with precise selections, hovering screen tips, or as an alternative to tap and hold for right-click.</span></span> 
    
    - <span data-ttu-id="65de7-120">Consultez l’exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="65de7-120">See the following example.</span></span>

      ![Paramètres d’interaction](images/touch.png)

2. <span data-ttu-id="65de7-122">Configurez le clavier visuel sur azerty et flottez.</span><span class="sxs-lookup"><span data-stu-id="65de7-122">Configure the touch keyboard to QWERTY and floating.</span></span>

    1. <span data-ttu-id="65de7-123">Cliquez sur l’icône de **clavier** dans la barre des tâches pour afficher le clavier visuel.</span><span class="sxs-lookup"><span data-stu-id="65de7-123">Select the **Keyboard** icon on the taskbar to show the touch keyboard.</span></span>
    
    2. <span data-ttu-id="65de7-124">Sur le clavier visuel, sélectionnez l’icône de clavier dans le coin supérieur gauche pour ouvrir les paramètres du clavier.</span><span class="sxs-lookup"><span data-stu-id="65de7-124">On the touch keyboard, select the keyboard icon in the upper left corner to open keyboard settings.</span></span>
    
    3. <span data-ttu-id="65de7-125">Activez la case à cocher en regard de dernier type de clavier dans la ligne du haut pour activer AZERTY, et la dernière option pour activer le mode flottant, ce qui est très utile sur ce grand écran.</span><span class="sxs-lookup"><span data-stu-id="65de7-125">Select the next to last keyboard type on the top row to enable QWERTY, and the last option on the second row to enable floating, which is very helpful on this large screen.</span></span> <span data-ttu-id="65de7-126">Consultez les exemples suivants.</span><span class="sxs-lookup"><span data-stu-id="65de7-126">See the following examples.</span></span>

       ![Paramètres du clavier](images/kbd.png)
 
3. <span data-ttu-id="65de7-128">Configurez les paramètres de clavier logiciels.</span><span class="sxs-lookup"><span data-stu-id="65de7-128">Configure the soft keyboard settings.</span></span>

    1. <span data-ttu-id="65de7-129">Sélectionnez l’icône **paramètres** sur le clavier ou recherchez et ouvrez les **paramètres de saisie**.</span><span class="sxs-lookup"><span data-stu-id="65de7-129">Select the **Settings** icon on the touch keyboard or search for and open **Typing settings**.</span></span>
    
       ![paramètres de clavier logiciels](images/sh2-softkeyboard.png)

    1. <span data-ttu-id="65de7-131">Activez toutes les options sous orthographe, saisie et clavier vocal.</span><span class="sxs-lookup"><span data-stu-id="65de7-131">Enable all the options under Spelling, Typing, and Touch keyboard.</span></span>


<span data-ttu-id="65de7-132">L’exemple suivant illustre pavé tactile, qui est utile pour naviguer et sélectionner des options.</span><span class="sxs-lookup"><span data-stu-id="65de7-132">The following example shows the trackpad, which is useful to navigate and select options.</span></span> <span data-ttu-id="65de7-133">Le clavier à l’écran est utilisé pour effectuer une recherche sur le Microsoft Store:</span><span class="sxs-lookup"><span data-stu-id="65de7-133">The onscreen keyboard is being used to search the Microsoft Store:</span></span>

![Utiliser le pavé tactile](images/store.png)

## <span data-ttu-id="65de7-135">Configurer le clavier et la souris Bluetooth (facultatif)</span><span class="sxs-lookup"><span data-stu-id="65de7-135">Configure bluetooth keyboard and mouse (optional)</span></span>

<span data-ttu-id="65de7-136">Connectez un clavier et une souris si vous utilisez le périphérique en tant qu’appareil Windows principal, ou si vous utilisez souvent cette fonctionnalité pour la saisie ou la précision du fonctionnement.</span><span class="sxs-lookup"><span data-stu-id="65de7-136">Connect a keyboard and mouse if you are using the device as your primary Windows device, or you use it often for typing or precision work.</span></span>

<span data-ttu-id="65de7-137">Si votre périphérique surface Hub est proche d’un PC, vous pouvez utiliser [la souris sans bordure](https://aka.ms/mm) pour vous déplacer en douceur entre le centre de surface et le PC.</span><span class="sxs-lookup"><span data-stu-id="65de7-137">If your Surface Hub device is near to a PC, you can use [Mouse without Borders](https://aka.ms/mm) to move seamlessly between the Surface Hub and the PC.</span></span> <span data-ttu-id="65de7-138">Pour plus d’informations, reportez-vous [à la rubrique téléchargement de Microsoft à partir du garage: souris sans bordure](https://blogs.microsoft.com/ai/microsoft-download-from-the-garage-mouse-without-borders/).</span><span class="sxs-lookup"><span data-stu-id="65de7-138">For more information, see [Microsoft download from The Garage: Mouse without Borders](https://blogs.microsoft.com/ai/microsoft-download-from-the-garage-mouse-without-borders/).</span></span>

## <span data-ttu-id="65de7-139">OneDriveEntreprise</span><span class="sxs-lookup"><span data-stu-id="65de7-139">OneDrive for Business</span></span>

<span data-ttu-id="65de7-140">Utilisez [OneDrive entreprise](https://docs.microsoft.com/onedrive/onedrive) pour partager facilement des outils, des journaux et d’autres fichiers entre tous vos périphériques de travail.</span><span class="sxs-lookup"><span data-stu-id="65de7-140">Use [OneDrive for Business](https://docs.microsoft.com/onedrive/onedrive) to easily share tools, logs, and other files between all your work devices.</span></span>

- <span data-ttu-id="65de7-141">OneDrive vous permet de partager vos fichiers de travail entre votre ordinateur portable, votre bureau surface Hub et vos appareils mobiles gérés par Intune.</span><span class="sxs-lookup"><span data-stu-id="65de7-141">OneDrive enables you to share your work files between your laptops, Surface Hub Desktop, and your Intune-managed mobile devices.</span></span> <span data-ttu-id="65de7-142">Les fichiers peuvent être modifiés sur n’importe quel appareil, et tous les appareils connectés réseau sont mis à jour avec les modifications.</span><span class="sxs-lookup"><span data-stu-id="65de7-142">Files can be edited on any device, and all network connected devices will be updated with the changes.</span></span>

- <span data-ttu-id="65de7-143">Si vous considérez la taille de la fonction SSD de surface Hub (128 Go), si vous configurez OneDrive sur votre appareil de bureau surface Hub, assurez-vous que la configuration par défaut est de conserver les fichiers en ligne et de télécharger des fichiers lorsque vous les utilisez.</span><span class="sxs-lookup"><span data-stu-id="65de7-143">Considering the size of the Surface Hub SSD (128GB), if you configure OneDrive on your Surface Hub Desktop device, make sure the default configuration is to keep the files online and download files as you use them.</span></span>

<span data-ttu-id="65de7-144">Pour configurer OneDrive pour télécharger les fichiers uniquement lorsque cela est nécessaire, définissez le paramètre **fichiers à la demande** pour **économiser de l’espace et télécharger les fichiers lorsque vous les utilisez**.</span><span class="sxs-lookup"><span data-stu-id="65de7-144">To configure OneDrive to download files only when needed, set the **Files On-Demand** setting to **Save space and download files as you use them**.</span></span> <span data-ttu-id="65de7-145">Pour plus d’informations, reportez-vous à [la rubrique interroger et définir des fichiers à la demande dans Windows](https://docs.microsoft.com/onedrive/files-on-demand-windows).</span><span class="sxs-lookup"><span data-stu-id="65de7-145">For more information, see [Query and set Files On-Demand states in Windows](https://docs.microsoft.com/onedrive/files-on-demand-windows).</span></span>

![Paramètres de OneDrive](images/onedrive.png)

> [!NOTE]
> <span data-ttu-id="65de7-147">Vous pouvez également répéter ces étapes pour configurer votre espace OneDrive personnel, mais n’êtes pas sûr de ménager de l’espace disque et de télécharger uniquement les fichiers dont vous avez besoin.</span><span class="sxs-lookup"><span data-stu-id="65de7-147">You can also repeat these steps to configure a personal OneDrive but be sure to conserve drive space and only download files as you need them.</span></span>

## <span data-ttu-id="65de7-148">SharePoint et Teams</span><span class="sxs-lookup"><span data-stu-id="65de7-148">SharePoint and Teams</span></span>

<span data-ttu-id="65de7-149">Les fichiers de canal SharePoint et teams peuvent également être synchronisés localement sur vos appareils de bureau, tels que les ordinateurs portables et les hubs de surface, à l’aide du moteur de synchronisation OneDrive.</span><span class="sxs-lookup"><span data-stu-id="65de7-149">SharePoint and Teams Channel files can also sync locally to your desktop devices, such as laptops and Surface Hubs, using the OneDrive sync engine.</span></span>

<span data-ttu-id="65de7-150">Pour synchroniser des fichiers d’entreprise internes sur votre disque local à l’aide de l’application de synchronisation OneDrive:</span><span class="sxs-lookup"><span data-stu-id="65de7-150">To sync internal corporate files to your local drive with the OneDrive sync app:</span></span>

1. <span data-ttu-id="65de7-151">Accédez à un site SharePoint et naviguez jusqu’au répertoire de documents de niveau supérieur correspondant aux fichiers que vous souhaitez afficher ou modifier à partir de votre appareil local.</span><span class="sxs-lookup"><span data-stu-id="65de7-151">Go to a SharePoint site and navigate to the top-level document directory for files that you are interested in viewing or editing from your local device.</span></span>

2. <span data-ttu-id="65de7-152">Cliquez sur le bouton **synchroniser** situé en haut du ruban SharePoint.</span><span class="sxs-lookup"><span data-stu-id="65de7-152">Select on the **Sync** button on the top of the SharePoint ribbon.</span></span>

3. <span data-ttu-id="65de7-153">Sélectionner sur **ouvrir** dans le menu contextuel **ce site tente d’ouvrir Microsoft OneDrive**.</span><span class="sxs-lookup"><span data-stu-id="65de7-153">Select on **Open** on the popup **This site is trying to open Microsoft OneDrive**.</span></span>

4. <span data-ttu-id="65de7-154">Vérifiez que les fichiers SharePoint sont synchronisés avec votre lecteur local en sélectionnant l’icône OneDrive située en bas à droite de la barre des tâches.</span><span class="sxs-lookup"><span data-stu-id="65de7-154">Verify that the SharePoint files are synchronizing to your local drive by selecting on the OneDrive icon at the bottom right of the taskbar.</span></span>

5. <span data-ttu-id="65de7-155">Vérifiez que la configuration est définie pour conserver les fichiers en ligne et télécharger les fichiers uniquement lors de leur utilisation:</span><span class="sxs-lookup"><span data-stu-id="65de7-155">Verify the configuration is set to keep the files online and download the files only as you use them:</span></span>

    1. <span data-ttu-id="65de7-156">Ouvrez l’Explorateur de fichiers.</span><span class="sxs-lookup"><span data-stu-id="65de7-156">Open file explorer.</span></span>
    
    2. <span data-ttu-id="65de7-157">Accédez et cliquez avec le bouton droit sur votre nom SharePoint; par exemple, \*\*contoso \ \<SharePoint Document Folder Name\> \*\*.</span><span class="sxs-lookup"><span data-stu-id="65de7-157">Navigate to and right click your SharePoint name; for example, **Contoso \ \<SharePoint Document Folder Name\>**.</span></span>
    
    3. <span data-ttu-id="65de7-158">Sélectionnez **libérer**de l’espace.</span><span class="sxs-lookup"><span data-stu-id="65de7-158">Select **Free up space**.</span></span>
    
    4. <span data-ttu-id="65de7-159">La colonne État affiche l’état des fichiers et des dossiers.</span><span class="sxs-lookup"><span data-stu-id="65de7-159">The Status column will display the status of files and folders.</span></span> <span data-ttu-id="65de7-160">Pour plus d’informations, voir [synchroniser des fichiers SharePoint avec le client de synchronisation OneDrive](https://support.microsoft.com/office/sync-sharepoint-files-with-the-onedrive-sync-client-groove-exe-59b1de2b-519e-4d3a-8f45-51647cf291cd).</span><span class="sxs-lookup"><span data-stu-id="65de7-160">For more information, see [Sync SharePoint files with the OneDrive sync client](https://support.microsoft.com/office/sync-sharepoint-files-with-the-onedrive-sync-client-groove-exe-59b1de2b-519e-4d3a-8f45-51647cf291cd).</span></span>
    
6. <span data-ttu-id="65de7-161">Les fichiers de canal teams sont stockés sur des sites SharePoint, avec toutes les mêmes fonctionnalités de documents SharePoint, y compris l’historique des versions et la synchronisation avec les appareils de bureau locaux.</span><span class="sxs-lookup"><span data-stu-id="65de7-161">Teams Channel files are stored in SharePoint sites, with all of the same SharePoint document functionality, including version history and synchronizing to your local desktop devices.</span></span> <span data-ttu-id="65de7-162">Pour synchroniser des fichiers de canal d’équipe:</span><span class="sxs-lookup"><span data-stu-id="65de7-162">To sync Teams Channel files:</span></span>

    1. <span data-ttu-id="65de7-163">Accédez au canal d’intérêt de l’équipe et sélectionnez l’onglet **fichiers** en haut.</span><span class="sxs-lookup"><span data-stu-id="65de7-163">Navigate to the Teams Channel of interest and select the **Files** tab at the top.</span></span> <span data-ttu-id="65de7-164">Sélectionnez **synchroniser**. Les fichiers commenceront à se synchroniser et sont visibles dans l’Explorateur de fichiers sur le \*\*Bureau \ contoso \ \<name of the Teams Channel\> \*\*.</span><span class="sxs-lookup"><span data-stu-id="65de7-164">Then select **Sync**. The files will start synchronizing and will be visible in File Explorer at **Desktop \ Contoso \ \<name of the Teams Channel\>**.</span></span>
    
    2. <span data-ttu-id="65de7-165">Utilisez la même procédure que celle que vous avez utilisée pour synchroniser des sites SharePoint afin de conserver les fichiers dans le Cloud et de les télécharger uniquement lorsque vous les utilisez, appuyez longuement ou cliquez avec le bouton droit dans l’Explorateur de fichiers sur le nom du canal Teams, puis sélectionnez libérer de l' **espace**.</span><span class="sxs-lookup"><span data-stu-id="65de7-165">Use the same procedure that you used for synchronizing SharePoint sites to keep the files in the cloud and only download them when you use them, by tap and hold or right-click in File Explorer on the Teams Channel name, and then selecting **Free up space**.</span></span>

## <span data-ttu-id="65de7-166">Paramètres de stylet surface Hub</span><span class="sxs-lookup"><span data-stu-id="65de7-166">Surface Hub pen settings</span></span>

**<span data-ttu-id="65de7-167">Couplez le stylo Bluetooth surface Hub</span><span class="sxs-lookup"><span data-stu-id="65de7-167">Pair the Bluetooth Surface Hub Pen</span></span>**

<span data-ttu-id="65de7-168">Couplez le stylet pour maintenir à jour le microprogramme du stylo et obtenir des informations de charge de la batterie dans la page Paramètres de l’appareil Bluetooth ou dans l’application surface:</span><span class="sxs-lookup"><span data-stu-id="65de7-168">Pair the pen to keep the pen firmware up to date and get battery charge information on the Bluetooth device settings page, or in the Surface app:</span></span>

1. <span data-ttu-id="65de7-169">Sélectionnez Paramètres de **démarrage**de l'  >  **Settings**  >  **appareil**.</span><span class="sxs-lookup"><span data-stu-id="65de7-169">Select **Start** > **Settings** > **Devices**.</span></span>

2. <span data-ttu-id="65de7-170">Sélectionnez **Ajouter un appareil Bluetooth ou un autre appareil**.</span><span class="sxs-lookup"><span data-stu-id="65de7-170">Select **Add Bluetooth or other device**.</span></span>

3. <span data-ttu-id="65de7-171">Sélectionnez **Bluetooth**.</span><span class="sxs-lookup"><span data-stu-id="65de7-171">Choose **Bluetooth**.</span></span>

4. <span data-ttu-id="65de7-172">Supprimez le bouton de queue du stylo et secouez la connexion à la batterie.</span><span class="sxs-lookup"><span data-stu-id="65de7-172">Remove the pen tail button and shake to disconnect the battery connection.</span></span>

5. <span data-ttu-id="65de7-173">Placez le capuchon en retour, puis appuyez de façon prolongée sur le capuchon jusqu’à ce que le voyant du jumelage clignote.</span><span class="sxs-lookup"><span data-stu-id="65de7-173">Put the cap back on and press and hold the cap until the pairing LED flashes.</span></span>

6. <span data-ttu-id="65de7-174">Dans les paramètres Bluetooth surface Hub, sélectionnez **surface Hub 2 PEN**.</span><span class="sxs-lookup"><span data-stu-id="65de7-174">On the Surface Hub Bluetooth settings, choose **Surface Hub 2 Pen**.</span></span>

7. <span data-ttu-id="65de7-175">Terminez l’opération de jumelage.</span><span class="sxs-lookup"><span data-stu-id="65de7-175">Complete the pairing operation.</span></span> 

8. <span data-ttu-id="65de7-176">Si le jumelage ne fonctionne pas, vous pouvez essayer de jumeler de nouveau le stylet.</span><span class="sxs-lookup"><span data-stu-id="65de7-176">If the pairing is not successful, you can attempt to pair the pen again.</span></span> <span data-ttu-id="65de7-177">Si cela ne fonctionne pas, vous pouvez effectuer des tests pour savoir si la batterie est débitée en vérifiant que le stylet fonctionne dans l’application tableau blanc.</span><span class="sxs-lookup"><span data-stu-id="65de7-177">If that doesn't work, you can test to see if the battery is charged by verifying the pen works in the Whiteboard application.</span></span> <span data-ttu-id="65de7-178">Si ce n’est pas le cas, remplacez la batterie, puis essayez à nouveau de jumeler le stylet.</span><span class="sxs-lookup"><span data-stu-id="65de7-178">If not, then replace the battery and then try to pair the pen again.</span></span> <span data-ttu-id="65de7-179">Le cas échéant, redémarrez l’appareil, puis réessayez.</span><span class="sxs-lookup"><span data-stu-id="65de7-179">If necessary, restart the device and then try again.</span></span>

<span data-ttu-id="65de7-180">**Définir des raccourcis de stylet** Le stylet surface Hub est parfois désigné par un bouton de raccourci.</span><span class="sxs-lookup"><span data-stu-id="65de7-180">**Set pen shortcuts** The Surface Hub pen has a shortcut button sometimes referred to as a "tail click".</span></span> <span data-ttu-id="65de7-181">Pour configurer des raccourcis, vous devez d’abord coupler le stylet, comme décrit précédemment.</span><span class="sxs-lookup"><span data-stu-id="65de7-181">Configuring shortcuts requires you to first pair the pen, as described earlier.</span></span>

1. <span data-ttu-id="65de7-182">Recherchez stylo et sélectionnez **stylo & paramètres Windows Ink**.</span><span class="sxs-lookup"><span data-stu-id="65de7-182">Search for Pen and select **Pen & Windows Ink settings**.</span></span>

2. <span data-ttu-id="65de7-183">Dans la partie inférieure de la page, sélectionnez raccourcis clavier permettant d’ouvrir la boîte de dialogue, comme suit:</span><span class="sxs-lookup"><span data-stu-id="65de7-183">Near the bottom of the page, select Pen shortcuts which opens the dialog box, shown here:</span></span>

   ![Raccourcis clavier](images/sh2-pen-shortcuts.png)

## <span data-ttu-id="65de7-185">Configuration de la caméra</span><span class="sxs-lookup"><span data-stu-id="65de7-185">Camera configuration</span></span>

<span data-ttu-id="65de7-186">Vous pouvez monter la caméra sur le dessus ou sur l’un ou l’autre extrémité de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="65de7-186">You can mount the camera on the top or on either side of the device.</span></span> <span data-ttu-id="65de7-187">Montez l’appareil photo en position pour optimiser l’angle de la caméra si vous utilisez le concentrateur avec un socle de bureau plutôt qu’un panier, ou que vous êtes en proximité du Hub.</span><span class="sxs-lookup"><span data-stu-id="65de7-187">Mount the camera in a position to optimize the camera angle if you are using the Hub with a desktop stand instead of a cart, or are in close proximity to the Hub.</span></span> <span data-ttu-id="65de7-188">Comme la caméra ne pivote pas automatiquement, vous devez disposer d’une touche hexadécimale 2mm pour faire pivoter manuellement la caméra.</span><span class="sxs-lookup"><span data-stu-id="65de7-188">The camera does not auto-rotate, so you need to have a 2mm hex key to manually rotate the camera.</span></span> 

<span data-ttu-id="65de7-189">Pour plus d’informations sur la façon de monter la caméra et de la faire pivoter manuellement, voir orientation de l’objectif de la caméra [surface Hub](https://support.microsoft.com/help/4509729/surface-hub-2s-camera-lens-orientation).</span><span class="sxs-lookup"><span data-stu-id="65de7-189">For more information on how to side-mount the camera and rotate the camera manually, see [Surface Hub 2S camera lens orientation](https://support.microsoft.com/help/4509729/surface-hub-2s-camera-lens-orientation).</span></span>

## <span data-ttu-id="65de7-190">Configuration de Windows Hello</span><span class="sxs-lookup"><span data-stu-id="65de7-190">Windows Hello configuration</span></span>

<span data-ttu-id="65de7-191">Surface Hub 2-xxxxx xxx XXXXXXX XXXXXXX xxxx xxx xxxxxxx xxx XXXXXXX XXXXXXX XXXXXXX XXXXXXX XXXXXXX XXXXXXX XXXXXXX XXXXXXX xxxx.</span><span class="sxs-lookup"><span data-stu-id="65de7-191">Surface Hub 2S running Windows 10 Enterprise allows the full suite of Win32 desktop applications as well as biometric Windows Hello options.</span></span> <span data-ttu-id="65de7-192">Les accessoires du lecteur d’empreintes digitales de surface Hub 2 peuvent être branchés dans n’importe quel port USB-C de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="65de7-192">The Surface Hub 2 Fingerprint Reader accessory can be plugged into any USB-C port on the device.</span></span> 

<span data-ttu-id="65de7-193">Pour commander un lecteur d’empreintes digitales surface Hub 2 ou afficher des spécifications techniques, voir composants additionnels [pour Windows 10 professionnel et entreprise sur surface Hub 2](surface-hub-2-essential-add-ons.md).</span><span class="sxs-lookup"><span data-stu-id="65de7-193">To order a Surface Hub 2 Fingerprint Reader or view technical specs, see [Essential add-ons for Windows 10 Pro and Enterprise on Surface Hub 2](surface-hub-2-essential-add-ons.md).</span></span> 

<span data-ttu-id="65de7-194">Après avoir inséré le lecteur d’empreintes digitales **, sélectionnez**  >  **paramètres**  >  **Accounts**  >  **de connexion comptes options de connexion dans**  >  votre**empreinte digitale Windows Hello** pour inscrire votre empreinte digitale.</span><span class="sxs-lookup"><span data-stu-id="65de7-194">After inserting the fingerprint reader, select **Start** > **Settings** > **Accounts** > **Sign-in options** > **Windows Hello Fingerprint** to enroll your fingerprint.</span></span>

<span data-ttu-id="65de7-195">Utilisez un appareil certifié Windows Hello pour la reconnaissance faciale.</span><span class="sxs-lookup"><span data-stu-id="65de7-195">Use a Windows Hello certified device for face recognition.</span></span> <span data-ttu-id="65de7-196">La caméra surface Hub 2 ne prend pas en charge la reconnaissance faciale Windows Hello.</span><span class="sxs-lookup"><span data-stu-id="65de7-196">The Surface Hub 2S camera does not support Windows Hello face recognition.</span></span>

## <span data-ttu-id="65de7-197">Activer un raccourci de l’écran de verrouillage dans la barre des tâches</span><span class="sxs-lookup"><span data-stu-id="65de7-197">Enable a Lock Screen shortcut icon on the taskbar</span></span>

<span data-ttu-id="65de7-198">Pour ajouter une icône à la barre des tâches qui permet le verrouillage de l’écran à une seule touche, comme le raccourci clavier Windows-L:</span><span class="sxs-lookup"><span data-stu-id="65de7-198">To add an icon to the taskbar that enables one-touch screen lock similar to the Windows-L keyboard shortcut:</span></span> 

1.  <span data-ttu-id="65de7-199">Appuyez de façon prolongée ou cliquez avec le bouton droit sur le bureau, sélectionnez **nouveau**  >  **raccourci**  >  **Parcourir**le  >  **Bureau**  >  **OK**  >  **suivant**.</span><span class="sxs-lookup"><span data-stu-id="65de7-199">Tap and hold or right-click on the desktop, select **New** > **Shortcut** > **Browse** > **Desktop** > **OK** > **Next**.</span></span>

1.  <span data-ttu-id="65de7-200">Indiquez un nom pour le raccourci tel que **verrouiller mon PC**, puis cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="65de7-200">Provide a name for the shortcut such as **Lock my PC**, and then select **Finish**.</span></span>

1.  <span data-ttu-id="65de7-201">Cliquez avec le bouton droit ou appuyez longuement sur le raccourci qui vient d’être créé sur le bureau, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="65de7-201">Right-click or tap and hold the newly created shortcut on the desktop, and select **Properties**.</span></span> <span data-ttu-id="65de7-202">Dans l’onglet **raccourci** , entrez les informations suivantes dans le champ **cible** : **Rundll32.exe User32.dll LockWorkStation**</span><span class="sxs-lookup"><span data-stu-id="65de7-202">On the **Shortcut** tab, enter the following in the **Target** field: **Rundll32.exe User32.dll,LockWorkStation**</span></span>

1.  <span data-ttu-id="65de7-203">Cliquez sur le bouton **modifier l’icône** et recherchez **C:\Windows\System32\imageres.dll** et sélectionnez une icône à utiliser.</span><span class="sxs-lookup"><span data-stu-id="65de7-203">Select the **Change Icon** button and browse to **C:\Windows\System32\imageres.dll** and select an icon to use.</span></span> 

    <span data-ttu-id="65de7-204">Consultez l’exemple suivant:</span><span class="sxs-lookup"><span data-stu-id="65de7-204">See the following example:</span></span>

    ![Choisir une icône](images/lock.png)
    
1.  <span data-ttu-id="65de7-206">Cliquez sur **OK** pour enregistrer le raccourci.</span><span class="sxs-lookup"><span data-stu-id="65de7-206">Select **OK** to save the shortcut.</span></span>

1.  <span data-ttu-id="65de7-207">Cliquez avec le bouton droit ou appuyez longuement sur le raccourci et sélectionnez **Épingler à la barre des tâches**.</span><span class="sxs-lookup"><span data-stu-id="65de7-207">Right-click or tap and hold the shortcut and select **Pin to taskbar**.</span></span>

1. <span data-ttu-id="65de7-208">Après avoir épinglé le raccourci de verrouillage dans la barre des tâches, vous pouvez le supprimer de votre ordinateur de bureau.</span><span class="sxs-lookup"><span data-stu-id="65de7-208">After you have pinned the lock shortcut to the taskbar, you can delete it from the desktop.</span></span>

## <span data-ttu-id="65de7-209">Applications</span><span class="sxs-lookup"><span data-stu-id="65de7-209">Applications</span></span>

### <span data-ttu-id="65de7-210">Mettre à jour les applications installées</span><span class="sxs-lookup"><span data-stu-id="65de7-210">Update installed apps</span></span>

<span data-ttu-id="65de7-211">Pour mettre à jour toutes les applications du Windows Store installées:</span><span class="sxs-lookup"><span data-stu-id="65de7-211">To update all installed Store apps:</span></span>

1. <span data-ttu-id="65de7-212">Ouvrez l’application Microsoft Store et sélectionnez les points de suspension **voir plus** dans le coin supérieur droit.</span><span class="sxs-lookup"><span data-stu-id="65de7-212">Open Microsoft Store app and select the **See more** ellipsis in the top-right corner.</span></span>

2. <span data-ttu-id="65de7-213">Sélectionnez **Téléchargements et mises à jour**.</span><span class="sxs-lookup"><span data-stu-id="65de7-213">Select **Downloads and updates**.</span></span>

2. <span data-ttu-id="65de7-214">Sélectionnez **Obtenir les mises à jour**.</span><span class="sxs-lookup"><span data-stu-id="65de7-214">Select **Get updates**.</span></span>

### <span data-ttu-id="65de7-215">Tableau blanc collaboratif Microsoft</span><span class="sxs-lookup"><span data-stu-id="65de7-215">Microsoft Whiteboard</span></span>

<span data-ttu-id="65de7-216">Pour installer le tableau blanc Microsoft, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="65de7-216">To install the Microsoft Whiteboard:</span></span>

 - <span data-ttu-id="65de7-217">Cliquez sur l’icône de l' **espace de travail Windows Ink** dans le coin inférieur droit de la barre des tâches et téléchargez le **tableau blanc**.</span><span class="sxs-lookup"><span data-stu-id="65de7-217">Select the **Windows Ink Workspace** icon on the lower right of the taskbar and download **Whiteboard**.</span></span>
 
   ![Espace de travail Ink](images/ink.png) 

<span data-ttu-id="65de7-219">Vous pouvez également installer le tableau blanc à partir du Microsoft Store:</span><span class="sxs-lookup"><span data-stu-id="65de7-219">Alternatively, you can install Whiteboard from the Microsoft Store:</span></span>

1. <span data-ttu-id="65de7-220">Ouvrez l’application Microsoft Store et recherchez le **tableau blanc**.</span><span class="sxs-lookup"><span data-stu-id="65de7-220">Open Microsoft Store app and search for **Whiteboard**.</span></span>

2. <span data-ttu-id="65de7-221">Choisissez **non merci** pour vous connecter et utiliser les différents appareils.</span><span class="sxs-lookup"><span data-stu-id="65de7-221">Choose **No thanks** to sign in and use across devices.</span></span>

3. <span data-ttu-id="65de7-222">Épingler le tableau blanc dans la barre des tâches.</span><span class="sxs-lookup"><span data-stu-id="65de7-222">Pin Whiteboard to the taskbar.</span></span>

### <span data-ttu-id="65de7-223">Application surface</span><span class="sxs-lookup"><span data-stu-id="65de7-223">Surface app</span></span>

1. <span data-ttu-id="65de7-224">Dans la boutique Microsoft, recherchez **surface**.</span><span class="sxs-lookup"><span data-stu-id="65de7-224">In the Microsoft Store, search for **Surface**.</span></span>

2. <span data-ttu-id="65de7-225">Définissez le **niveau de filtrage disponible sur** **tous les appareils**.</span><span class="sxs-lookup"><span data-stu-id="65de7-225">Set the **Available on** filter to **All devices**.</span></span>

3. <span data-ttu-id="65de7-226">Installez l’application **surface** .</span><span class="sxs-lookup"><span data-stu-id="65de7-226">Install the **Surface** app.</span></span> <span data-ttu-id="65de7-227">Il s’agit de la première application répertoriée.</span><span class="sxs-lookup"><span data-stu-id="65de7-227">This should be the first app listed.</span></span> <span data-ttu-id="65de7-228">Vous devrez peut-être associer votre MSA au Windows Store pour pouvoir installer l’application.</span><span class="sxs-lookup"><span data-stu-id="65de7-228">You might need to associate your MSA to the Store in order to install the app.</span></span>

4. <span data-ttu-id="65de7-229">Épingler l’application **surface** à la barre des tâches.</span><span class="sxs-lookup"><span data-stu-id="65de7-229">Pin the **Surface** app to taskbar.</span></span>

### <span data-ttu-id="65de7-230">Capture d'écran et Croquis</span><span class="sxs-lookup"><span data-stu-id="65de7-230">Snip & Sketch</span></span>

1. <span data-ttu-id="65de7-231">Ouvrez l’application de **capture & esquisse** et épinglez-la à la barre des tâches.</span><span class="sxs-lookup"><span data-stu-id="65de7-231">Open the **Snip & Sketch** app and pin it to the taskbar.</span></span>

2. <span data-ttu-id="65de7-232">Sélectionnez les points de suspension dans le coin supérieur droit, puis sélectionnez **paramètres**.</span><span class="sxs-lookup"><span data-stu-id="65de7-232">Select the ellipsis in the upper right corner and then select **Settings**.</span></span>

3. <span data-ttu-id="65de7-233">Dans **paramètres**, activez la fonction de **copie automatique dans le presse-papiers**, **Enregistrez les captures**et les **fenêtres multiples** (facultatif).</span><span class="sxs-lookup"><span data-stu-id="65de7-233">In **Settings**, turn on **Auto copy to clipboard**, **Save snips**, and **Multiple windows** (optional).</span></span>

### <span data-ttu-id="65de7-234">MicrosoftOffice</span><span class="sxs-lookup"><span data-stu-id="65de7-234">Microsoft Office</span></span>

1. <span data-ttu-id="65de7-235">Ouvrez le [portail Office](https://portal.office.com/account#installs) et installez les applications souhaitées.</span><span class="sxs-lookup"><span data-stu-id="65de7-235">Open the [Office Portal](https://portal.office.com/account#installs) and install your desired applications.</span></span>

2. <span data-ttu-id="65de7-236">Épinglez les applications Office souhaitées dans la barre des tâches.</span><span class="sxs-lookup"><span data-stu-id="65de7-236">Pin desired Office applications to the taskbar.</span></span>

3. <span data-ttu-id="65de7-237">Si Outlook est installé, assurez-vous de définir le cache OST Outlook de façon à ce qu’il enregistre uniquement le cache des deux dernières semaines.</span><span class="sxs-lookup"><span data-stu-id="65de7-237">If Outlook is installed, be sure to set the Outlook OST to only save last two weeks cache.</span></span> <span data-ttu-id="65de7-238">Le temps d’utilisation et de configuration du disque sera considérablement réduit.</span><span class="sxs-lookup"><span data-stu-id="65de7-238">This will vastly reduce disk usage and setup time.</span></span>

    - <span data-ttu-id="65de7-239">Sélectionnez **File**  >  **paramètres du compte** de fichier, puis sélectionnez votre compte.</span><span class="sxs-lookup"><span data-stu-id="65de7-239">Select **File** > **Account Settings** and select your account.</span></span>
    
    - <span data-ttu-id="65de7-240">Sélectionnez **modifier** , puis positionnez le curseur pour **utiliser le mode Exchange mis en cache** à 14 jours.</span><span class="sxs-lookup"><span data-stu-id="65de7-240">Select **Change** and set the slider for **Use Cached Exchange Mode** to 14 days.</span></span>

### <span data-ttu-id="65de7-241">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="65de7-241">Microsoft Teams</span></span>

1. <span data-ttu-id="65de7-242">Télécharger et installer [Microsoft teams](https://teams.microsoft.com/downloads).</span><span class="sxs-lookup"><span data-stu-id="65de7-242">Download and install [Microsoft Teams](https://teams.microsoft.com/downloads).</span></span>

2. <span data-ttu-id="65de7-243">Configurez les paramètres de démarrage automatique de l’application (facultatif).</span><span class="sxs-lookup"><span data-stu-id="65de7-243">Configure settings to Auto-start application (optional).</span></span>

3. <span data-ttu-id="65de7-244">Épingler des équipes dans la barre des tâches.</span><span class="sxs-lookup"><span data-stu-id="65de7-244">Pin Teams to the taskbar.</span></span>

4. <span data-ttu-id="65de7-245">Envisagez de réduire les notifications d’équipe sur l’appareil pour éviter toute distraction (facultatif).</span><span class="sxs-lookup"><span data-stu-id="65de7-245">Consider reducing Teams notifications on the device to avoid distractions (optional).</span></span>

   ![Notifications teams](images/teams.png)

### <span data-ttu-id="65de7-247">Connecter l’application</span><span class="sxs-lookup"><span data-stu-id="65de7-247">Connect app</span></span>

> [!IMPORTANT]
> <span data-ttu-id="65de7-248">Dans Windows 10, version 2004 et ultérieure, l’application connexion pour la projection sans fil à l’aide de Miracast n’est pas installée par défaut, mais est disponible sous la forme d’une fonctionnalité facultative.</span><span class="sxs-lookup"><span data-stu-id="65de7-248">In Windows 10, version 2004 and later, the Connect app for wireless projection using Miracast is not installed by default, but is available as an optional feature.</span></span> <span data-ttu-id="65de7-249">Si vous avez installé (ou mis à jour vers) Windows version 2004 ou une version ultérieure, il est possible que vous voyiez ce qui suit sur l’écran de projet vers ce PC dans les paramètres:</span><span class="sxs-lookup"><span data-stu-id="65de7-249">If you have installed (or updated to) Windows version 2004 or later, you may see the following on the Projecting to this PC screen in settings:</span></span>

![Projetez sur ce PC](images/sh2-project.png) 


1. <span data-ttu-id="65de7-251">Pour installer l’application à partir de la page de paramètres «projection vers ce PC», sélectionnez **fonctionnalités facultatives**  >  **Ajouter une fonctionnalité** , puis installez l’application d' **affichage sans fil** .</span><span class="sxs-lookup"><span data-stu-id="65de7-251">To install the app from the “Projecting to this PC” settings page, select **Optional features** > **Add a feature** and then install the **Wireless Display** app.</span></span>

2. <span data-ttu-id="65de7-252">Sous **certains appareils Windows et Android peuvent projeter sur ce PC lorsque vous prononcez la mention OK**, choisissez:</span><span class="sxs-lookup"><span data-stu-id="65de7-252">Under **Some Windows and Android devices can project to this PC when you say it's OK**, choose:</span></span>

    - <span data-ttu-id="65de7-253">**Disponible partout** si l’appareil n’est pas sur un réseau d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="65de7-253">**Available everywhere** if the device is not on a corporate network.</span></span>
    - <span data-ttu-id="65de7-254">Dans le cas contraire, choisissez **disponible partout sur des réseaux sécurisés**.</span><span class="sxs-lookup"><span data-stu-id="65de7-254">Otherwise, choose **Available everywhere on secure networks**.</span></span>
    
3. <span data-ttu-id="65de7-255">Sous **demander à Project pour ce PC**, choisissez **première fois uniquement**.</span><span class="sxs-lookup"><span data-stu-id="65de7-255">Under **Ask to project to this PC**, choose **First time only**.</span></span>

4. <span data-ttu-id="65de7-256">Sous **exiger le code confidentiel pour le jumelage**, sélectionnez **jamais**.</span><span class="sxs-lookup"><span data-stu-id="65de7-256">Under **Require PIN for pairing**, choose **Never**.</span></span>

5. <span data-ttu-id="65de7-257">Pour lancer l’application et l’épingler à la barre des tâches, recherchez **connexion**.</span><span class="sxs-lookup"><span data-stu-id="65de7-257">To then launch the app and pin it to the taskbar, search for **Connect**.</span></span>

6. <span data-ttu-id="65de7-258">Ouvrez l’application.</span><span class="sxs-lookup"><span data-stu-id="65de7-258">Open the app.</span></span> <span data-ttu-id="65de7-259">Lorsque l’application est ouverte, cliquez avec le bouton droit sur l’icône de l’application connectée dans la barre des tâches, puis sélectionnez **Épingler à la barre des tâches**.</span><span class="sxs-lookup"><span data-stu-id="65de7-259">While the app is open, right-click on the Connect app icon on the taskbar, and select **pin to taskbar**.</span></span>

7. <span data-ttu-id="65de7-260">Fermez ensuite l’application connexion.</span><span class="sxs-lookup"><span data-stu-id="65de7-260">Then close the Connect app.</span></span> <span data-ttu-id="65de7-261">Le **projet sur ce PC** peut ne pas fonctionner tant que l’application n’a pas été exécutée au moins une fois.</span><span class="sxs-lookup"><span data-stu-id="65de7-261">**Project to this PC** might not work unless the app has been run at least once.</span></span>

<span data-ttu-id="65de7-262">Configuration recommandée hors du réseau d’entreprise:</span><span class="sxs-lookup"><span data-stu-id="65de7-262">Recommended configuration when not on the corporate network:</span></span>

![Paramètres à la maison](images/project1.png)

<span data-ttu-id="65de7-264">Configuration recommandée sur le réseau d’entreprise:</span><span class="sxs-lookup"><span data-stu-id="65de7-264">Recommended configuration on the corporate network:</span></span>

![Paramètres au bureau](images/project2.png)

### <span data-ttu-id="65de7-266">Votre Téléphone</span><span class="sxs-lookup"><span data-stu-id="65de7-266">Your Phone</span></span>

<span data-ttu-id="65de7-267">L’application **votre téléphone** est installée par défaut sur Windows 10.</span><span class="sxs-lookup"><span data-stu-id="65de7-267">The **Your Phone** app is installed by default on Windows 10.</span></span> <span data-ttu-id="65de7-268">Si ce n’est pas le cas, vous pouvez également l’installer à partir du Windows Store.</span><span class="sxs-lookup"><span data-stu-id="65de7-268">If it is not present, you can also install it from the Windows Store.</span></span>

<span data-ttu-id="65de7-269">Pour plus d’informations sur la configuration de l’application, reportez-vous à la rubrique Configuration de [votre téléphone sur Windows 10 et synchronisation des données entre votre ordinateur et votre téléphone](https://www.windowscentral.com/how-set-your-phone-windows-10).</span><span class="sxs-lookup"><span data-stu-id="65de7-269">For information about setting up the app, see [How to set up Your Phone on Windows 10 and sync data between your PC and phone](https://www.windowscentral.com/how-set-your-phone-windows-10).</span></span> <span data-ttu-id="65de7-270">Consultez également [la rubrique Comment résoudre les problèmes courants liés à votre application de téléphone sur Windows 10](https://www.windowscentral.com/how-fix-common-problems-your-phone-app-windows-10).</span><span class="sxs-lookup"><span data-stu-id="65de7-270">Also see [How to fix common problems with Your Phone app on Windows 10](https://www.windowscentral.com/how-fix-common-problems-your-phone-app-windows-10).</span></span>

### <span data-ttu-id="65de7-271">Zones super fantaisie</span><span class="sxs-lookup"><span data-stu-id="65de7-271">Super Fancy Zones</span></span>

<span data-ttu-id="65de7-272">Les **zones super fantaisie** permettent aux utilisateurs de réorganiser les fenêtres afin de maximiser l’espace disponible à l’écran.</span><span class="sxs-lookup"><span data-stu-id="65de7-272">**Super Fancy Zones** helps users arrange windows to maximize screen real estate.</span></span> <span data-ttu-id="65de7-273">Elle est désormais incluse dans [PowerToys](https://github.com/microsoft/PowerToys/releases) sur GitHub.</span><span class="sxs-lookup"><span data-stu-id="65de7-273">It is now included in [PowerToys](https://github.com/microsoft/PowerToys/releases) on GitHub.</span></span>

### <span data-ttu-id="65de7-274">Navigateur Microsoft Edge chrome</span><span class="sxs-lookup"><span data-stu-id="65de7-274">Edge Chromium browser</span></span>

<span data-ttu-id="65de7-275">Téléchargez et installez le nouveau [navigateur Microsoft Edge chrome](https://www.microsoft.com/en-us/edge?form=MY01BL&OCID=MY01BL).</span><span class="sxs-lookup"><span data-stu-id="65de7-275">Download and install the new [Edge Chromium browser](https://www.microsoft.com/en-us/edge?form=MY01BL&OCID=MY01BL).</span></span>


### <span data-ttu-id="65de7-276">Outil de diagnostic du matériel surface Hub</span><span class="sxs-lookup"><span data-stu-id="65de7-276">Surface Hub Hardware Diagnostic tool</span></span>

<span data-ttu-id="65de7-277">[Outil de diagnostic du matériel surface Hub](https://www.microsoft.com/p/surface-hub-hardware-diagnostic/9nblggh51f2g) disponible gratuitement sur le Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="65de7-277">The [Surface Hub Hardware Diagnostic tool](https://www.microsoft.com/p/surface-hub-hardware-diagnostic/9nblggh51f2g) available for free from the Microsoft Store.</span></span> <span data-ttu-id="65de7-278">L’outil est conçu pour vous aider à veiller à ce que votre surface Hub fonctionne de façon optimale.</span><span class="sxs-lookup"><span data-stu-id="65de7-278">The tool is designed to help you make sure your Surface Hub is performing at its best.</span></span> <span data-ttu-id="65de7-279">Il contient des tests permettant de déterminer si le microprogramme est à jour et s’il est configuré correctement.</span><span class="sxs-lookup"><span data-stu-id="65de7-279">It contains tests to determine if your firmware is up to date and configured correctly.</span></span> <span data-ttu-id="65de7-280">Les tests interactifs vous permettent de vérifier que les fonctionnalités essentielles fonctionnent comme prévu.</span><span class="sxs-lookup"><span data-stu-id="65de7-280">Interactive tests allow you to confirm essential functionality is working as expected.</span></span> <span data-ttu-id="65de7-281">Si des problèmes surviennent, les résultats peuvent être enregistrés et partagés avec l’équipe du Support Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="65de7-281">If problems are encountered, results can be saved and shared with the Surface Hub Support Team.</span></span> <span data-ttu-id="65de7-282">Cliquez sur le lien pour l’installer à partir du Microsoft Store, puis épinglez l’application à votre barre des tâches.</span><span class="sxs-lookup"><span data-stu-id="65de7-282">Click on the link to install it from the Microsoft Store, and then pin the application to your taskbar.</span></span>

## <span data-ttu-id="65de7-283">Paramètres supplémentaires</span><span class="sxs-lookup"><span data-stu-id="65de7-283">Additional settings</span></span>

### <span data-ttu-id="65de7-284">Stylo d’aileron sélectionner pour lancer le tableau blanc</span><span class="sxs-lookup"><span data-stu-id="65de7-284">Pen tail select to launch Whiteboard</span></span>

1. <span data-ttu-id="65de7-285">Recherchez **stylo** et sélectionnez **stylo & paramètres Windows Ink**.</span><span class="sxs-lookup"><span data-stu-id="65de7-285">Search for **Pen** and select **Pen & Windows Ink settings**.</span></span>

2. <span data-ttu-id="65de7-286">Dans la partie inférieure de la page, sous **raccourcis clavier** , définissez l' **option Sélectionner une fois** sur le **tableau blanc collaboratif Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="65de7-286">Near the bottom of the page, under **Pen shortcuts** set **Select once** to **Microsoft Whiteboard**.</span></span> 

### <span data-ttu-id="65de7-287">Gestion de l’alimentation</span><span class="sxs-lookup"><span data-stu-id="65de7-287">Power management</span></span>

<span data-ttu-id="65de7-288">Plusieurs paramètres d’alimentation sont disponibles pour tirer le meilleur parti de Windows 10 professionnel ou Enterprise sur surface Hub 2.</span><span class="sxs-lookup"><span data-stu-id="65de7-288">There are several power settings available to get the best experience using Windows 10 Pro or Enterprise on Surface Hub 2.</span></span> <span data-ttu-id="65de7-289">Cela inclut les délais d’expiration de l’écran et du PC, la façon dont ils interagissent avec le système de détection humaine intégré (Doppler), l’économiseur d’écran et la protection par mot de passe, puis, le cas échéant, les paramètres d’alimentation de la stratégie de groupe pour les utilisateurs de l’ordinateur portable ou du bureau.</span><span class="sxs-lookup"><span data-stu-id="65de7-289">This includes screen and pc timeouts and how they interact with the built-in human presence detection (Doppler), the screen saver and password protection, and then if appropriate how to by-pass group policy power settings intended for laptop / desktop users.</span></span>

<span data-ttu-id="65de7-290">Windows 10 professionnel ou entreprise sur surface Hub 2 vous permet d’accéder à l’écran par le biais de la fonction d’effleurement, de la souris et du clavier, ainsi que de la détection d’occupation humaine intégrée (Doppler).</span><span class="sxs-lookup"><span data-stu-id="65de7-290">Windows 10 Pro or Enterprise on Surface Hub 2 keeps the screen from going to sleep by touch, mouse, and keyboard actions, as well as the built-in human occupancy detection (Doppler).</span></span> <span data-ttu-id="65de7-291">La détection d’occupation humaine est activée par défaut, mais si vous le souhaitez, elle peut être désactivée dans UEFI en faisant basculer l’option d’appareil dans l’outil de Configurateur surface UEFI dans le cadre de la migration initiale, ou en construisant et en appliquant un package de configuration UEFI ultérieur.</span><span class="sxs-lookup"><span data-stu-id="65de7-291">Human occupancy detection is enabled by default, but if desired it can be disabled in UEFI by toggling the device option in the Surface UEFI Configurator tool either as part of the initial migration, or by building and applying a later UEFI configuration package.</span></span> 

**<span data-ttu-id="65de7-292">Gestion de l’alimentation: paramètres de veille de l’écran et du PC</span><span class="sxs-lookup"><span data-stu-id="65de7-292">Power Management: Screen and PC sleep settings</span></span>**

1. <span data-ttu-id="65de7-293">Sélectionnez **Démarrer**les  >  **paramètres**  >  **système**  >  **d’alimentation & Sleep**.</span><span class="sxs-lookup"><span data-stu-id="65de7-293">Select **Start** > **Settings** > **System** > **Power & sleep**.</span></span>

2. <span data-ttu-id="65de7-294">Positionnez le curseur mode d’alimentation sur **meilleures performances**.</span><span class="sxs-lookup"><span data-stu-id="65de7-294">Set the power mode slider to **Best performance**.</span></span>

3. <span data-ttu-id="65de7-295">Configurez les valeurs de l’écran et de la mise en veille de votre choix en tenant compte de la détection de présence Doppler qui met l’appareil en éveil lorsque le mouvement est détecté.</span><span class="sxs-lookup"><span data-stu-id="65de7-295">Configure screen and sleep values to your preference while also accounting for Doppler presence detection that wakes up the device when movement is detected.</span></span> <span data-ttu-id="65de7-296">Par conséquent, il est recommandé de configurer l’écran pour qu’il soit **désactivé au bout de 2 heures** et du PC pour le désactiver **après 4 heures.**</span><span class="sxs-lookup"><span data-stu-id="65de7-296">Accordingly, as a best practice, it's recommended to set Screen to **Turn off after 2 hours** and the PC to **Turn off after 4 hours.**</span></span>

**<span data-ttu-id="65de7-297">Gestion de l’alimentation: économiseur d’écran</span><span class="sxs-lookup"><span data-stu-id="65de7-297">Power Management: Screen saver</span></span>**

1. <span data-ttu-id="65de7-298">Recherchez l' **écran de verrouillage** et ouvrez les paramètres de l' **écran de verrouillage**.</span><span class="sxs-lookup"><span data-stu-id="65de7-298">Search for **Lock Screen** and open **Lock screen settings**.</span></span>

2. <span data-ttu-id="65de7-299">Configurez vos préférences en matière de **paramètres de délai d’écran** et de paramètres d' **écran de veille** .</span><span class="sxs-lookup"><span data-stu-id="65de7-299">Configure **Screen timeout settings** and **Screen saver settings** to your preference.</span></span> <span data-ttu-id="65de7-300">Les valeurs par défaut recommandées sont les suivantes:</span><span class="sxs-lookup"><span data-stu-id="65de7-300">Recommended default values are:</span></span>

   - <span data-ttu-id="65de7-301">Écran de veille (aucun) ou écran de votre choix.</span><span class="sxs-lookup"><span data-stu-id="65de7-301">Screen saver to (None) or a screen saver of your choice.</span></span>
   - <span data-ttu-id="65de7-302">Temps d’attente de 15 minutes.</span><span class="sxs-lookup"><span data-stu-id="65de7-302">Wait time to 15 minutes.</span></span>
   - <span data-ttu-id="65de7-303">En sortie, affichez l’écran de connexion.</span><span class="sxs-lookup"><span data-stu-id="65de7-303">On resume, display logon screen.</span></span>


**<span data-ttu-id="65de7-304">Gestion de l’alimentation: stratégie de groupe</span><span class="sxs-lookup"><span data-stu-id="65de7-304">Power Management: Group Policy</span></span>**

<span data-ttu-id="65de7-305">Avant d’effectuer la procédure suivante, contactez votre service informatique pour obtenir de l’aide afin d’exclure un périphérique surface Hub 2 de la stratégie de gestion de l’alimentation globale.</span><span class="sxs-lookup"><span data-stu-id="65de7-305">Before performing the following procedure, check with your IT department for approval to exclude a Surface Hub 2S device from global power management policy.</span></span> <span data-ttu-id="65de7-306">Certains paramètres de gestion de l’alimentation peuvent désactiver la fonction de détection de présence.</span><span class="sxs-lookup"><span data-stu-id="65de7-306">Some power management settings can disable the presence detection function.</span></span>

1. <span data-ttu-id="65de7-307">Recherchez le **Centre de logiciels** et ouvrez-le.</span><span class="sxs-lookup"><span data-stu-id="65de7-307">Search for **Software Center** and open it.</span></span>

2. <span data-ttu-id="65de7-308">Sélectionnez **options**.</span><span class="sxs-lookup"><span data-stu-id="65de7-308">Select **Options**.</span></span>

3. <span data-ttu-id="65de7-309">Développez la gestion de l' **alimentation**  et sélectionnez **ne pas appliquer les paramètres d’alimentation du service informatique à cet ordinateur**.</span><span class="sxs-lookup"><span data-stu-id="65de7-309">Expand the **Power management**  and select **Do not apply power settings from my IT department to this computer**.</span></span>

   ![Paramètres logiciels](images/soft-cntr.png)

### <span data-ttu-id="65de7-311">Assistant Stockage</span><span class="sxs-lookup"><span data-stu-id="65de7-311">Storage Sense</span></span>

<span data-ttu-id="65de7-312">Surface Hub 2 étant doté d’un appareil compact de 128 Go pour le stockage local, il est nécessaire de tenir compte de l’utilisation des mesures d’enregistrement de stockage en cas d’utilisation normale.</span><span class="sxs-lookup"><span data-stu-id="65de7-312">The Surface Hub 2 has a 128GB SSD for local storage, so it is necessary to consider the use of storage saving measures during normal usage.</span></span>  <span data-ttu-id="65de7-313">Pour configurer le sens de stockage:</span><span class="sxs-lookup"><span data-stu-id="65de7-313">To configure Storage Sense:</span></span>

1.  <span data-ttu-id="65de7-314">Recherchez **paramètres de stockage**dans les **paramètres système**.</span><span class="sxs-lookup"><span data-stu-id="65de7-314">Search for **storage settings**, which is found under **System settings**.</span></span>

2.  <span data-ttu-id="65de7-315">Sous **paramètres**, sélectionnez l’option **activer le stockage** pour ouvrir la page Paramètres de **stockage** .</span><span class="sxs-lookup"><span data-stu-id="65de7-315">Under **Settings**, select **Turn on storage sense** to open the **Storage** settings page.</span></span>

3.  <span data-ttu-id="65de7-316">Activez **le stockage sur activé**.</span><span class="sxs-lookup"><span data-stu-id="65de7-316">Turn Storage Sense to **On**.</span></span>

4.  <span data-ttu-id="65de7-317">Sélectionnez **configurer un sens de stockage ou exécutez-le maintenant** et configurez les paramètres permettant de conserver les fichiers en ligne le plus possible (en raison de l’espace disque limité).</span><span class="sxs-lookup"><span data-stu-id="65de7-317">Select **Configure Storage Sense or run it now** and configure settings to keep files online as much as possible (due to limited drive space).</span></span>

<span data-ttu-id="65de7-318">Paramètres recommandés:</span><span class="sxs-lookup"><span data-stu-id="65de7-318">Recommended settings:</span></span>

- <span data-ttu-id="65de7-319">Utilisez l’outil de stockage = quotidiennement.</span><span class="sxs-lookup"><span data-stu-id="65de7-319">Run Storage Sense = Every Day.</span></span>
- <span data-ttu-id="65de7-320">Supprimez les fichiers temporaires que mes applications n’utilisent pas = tous les 14 jours (au moins).</span><span class="sxs-lookup"><span data-stu-id="65de7-320">Delete temporary files that my apps aren't using = Every 14 days (at least).</span></span>
- <span data-ttu-id="65de7-321">Supprimer les fichiers du dossier téléchargements s’ils y étaient depuis plus de 30 jours.</span><span class="sxs-lookup"><span data-stu-id="65de7-321">Delete files in my Downloads folder if they have been there for over = 30 days.</span></span>
- <span data-ttu-id="65de7-322">OneDrive: le contenu devient en ligne uniquement s’il n’est pas ouvert pendant plus de 30 jours.</span><span class="sxs-lookup"><span data-stu-id="65de7-322">OneDrive: Content will become online-only if not opened for more than = 30 days.</span></span>

### <span data-ttu-id="65de7-323">Mode tablette</span><span class="sxs-lookup"><span data-stu-id="65de7-323">Tablet mode</span></span>

<span data-ttu-id="65de7-324">Activez le mode tablette si vous le souhaitez, pour les besoins en matière d’accessibilité.</span><span class="sxs-lookup"><span data-stu-id="65de7-324">Turn on Tablet mode if desired for accessibility needs.</span></span>


### <span data-ttu-id="65de7-325">Paramètres du son</span><span class="sxs-lookup"><span data-stu-id="65de7-325">Sound settings</span></span>

1. <span data-ttu-id="65de7-326">Recherchez les **paramètres audio** et ouvrez cette page.</span><span class="sxs-lookup"><span data-stu-id="65de7-326">Search for **Sounds settings** and open this page.</span></span>

2. <span data-ttu-id="65de7-327">Sélectionnez **son panneau de configuration** sur la droite, puis sélectionnez l’onglet **sons** .</span><span class="sxs-lookup"><span data-stu-id="65de7-327">Select **Sound Control Panel** on the right and select the **Sounds** tab.</span></span>

3. <span data-ttu-id="65de7-328">Sous **événements** , définissez l’option **connexion** de l’appareil et **Débranchez l’appareil** à **aucun**.</span><span class="sxs-lookup"><span data-stu-id="65de7-328">Under **Program Events** set **Device Connect** and **Device Disconnect** to **None**.</span></span>

### <span data-ttu-id="65de7-329">Notifications de silence</span><span class="sxs-lookup"><span data-stu-id="65de7-329">Silence notifications</span></span>

1. <span data-ttu-id="65de7-330">Recherchez **assistance au focus** et ouvrez cette page.</span><span class="sxs-lookup"><span data-stu-id="65de7-330">Search for **Focus assist** and open this page.</span></span>

2. <span data-ttu-id="65de7-331">Sélectionner **alarmes uniquement**.</span><span class="sxs-lookup"><span data-stu-id="65de7-331">Select **Alarms Only**.</span></span> <span data-ttu-id="65de7-332">Cela évite les menus volants de notifications constantes.</span><span class="sxs-lookup"><span data-stu-id="65de7-332">This will avoid constant notification flyouts.</span></span>

### <span data-ttu-id="65de7-333">Nettoyage de disque</span><span class="sxs-lookup"><span data-stu-id="65de7-333">Disk Cleanup</span></span>

1. <span data-ttu-id="65de7-334">Recherchez **Disk Cleanup** et ouvrez cette application.</span><span class="sxs-lookup"><span data-stu-id="65de7-334">Search for **Disk Cleanup** and open this app.</span></span>

2. <span data-ttu-id="65de7-335">Sous **fichiers à supprimer**, sélectionnez les fichiers que vous souhaitez supprimer.</span><span class="sxs-lookup"><span data-stu-id="65de7-335">Under **Files to delete**, select the files you wish to delete.</span></span> 

3. <span data-ttu-id="65de7-336">Sélectionnez également **nettoyer les fichiers système**.</span><span class="sxs-lookup"><span data-stu-id="65de7-336">Also select **Clean up system files**.</span></span>

## <span data-ttu-id="65de7-337">Achever et vérifier</span><span class="sxs-lookup"><span data-stu-id="65de7-337">Complete and verify</span></span>

1. <span data-ttu-id="65de7-338">Recherchez et installez toutes les mises à jour Windows.</span><span class="sxs-lookup"><span data-stu-id="65de7-338">Scan for and install all Windows Updates.</span></span>

2. <span data-ttu-id="65de7-339">Mise à jour de la stratégie de groupe</span><span class="sxs-lookup"><span data-stu-id="65de7-339">Update Group Policy</span></span>

   1. <span data-ttu-id="65de7-340">À l’invite de commandes avec élévation de privilèges, entrez **gpupdate/force/Boot/Wait: 0**.</span><span class="sxs-lookup"><span data-stu-id="65de7-340">At an elevated command prompt, enter **gpupdate /force /boot /wait:0**.</span></span>
   
3. <span data-ttu-id="65de7-341">Redémarrez l’appareil.</span><span class="sxs-lookup"><span data-stu-id="65de7-341">Restart the device.</span></span>

4. <span data-ttu-id="65de7-342">Vérifiez les applications de la barre des tâches.</span><span class="sxs-lookup"><span data-stu-id="65de7-342">Verify taskbar apps.</span></span>

   - <span data-ttu-id="65de7-343">Connecter l’application</span><span class="sxs-lookup"><span data-stu-id="65de7-343">Connect App</span></span>
   - <span data-ttu-id="65de7-344">Icône de verrouillage</span><span class="sxs-lookup"><span data-stu-id="65de7-344">Lock Icon</span></span>
   - <span data-ttu-id="65de7-345">Capture d'écran et Croquis</span><span class="sxs-lookup"><span data-stu-id="65de7-345">Snip & Sketch</span></span>
   - <span data-ttu-id="65de7-346">Teams (le cas échéant)</span><span class="sxs-lookup"><span data-stu-id="65de7-346">Teams (if applicable)</span></span>
   - <span data-ttu-id="65de7-347">Applications Office (le cas échéant)</span><span class="sxs-lookup"><span data-stu-id="65de7-347">Office Apps (if applicable)</span></span>
   - <span data-ttu-id="65de7-348">Application surface</span><span class="sxs-lookup"><span data-stu-id="65de7-348">Surface App</span></span>
   - <span data-ttu-id="65de7-349">Tableau blanc</span><span class="sxs-lookup"><span data-stu-id="65de7-349">Whiteboard</span></span>
    
5. <span data-ttu-id="65de7-350">Vérifier la détection de présence.</span><span class="sxs-lookup"><span data-stu-id="65de7-350">Verify presence detection.</span></span>

   - <span data-ttu-id="65de7-351">La détection de présence sera une icône verte dans la barre d’état système.</span><span class="sxs-lookup"><span data-stu-id="65de7-351">Presence detection will be a green icon in the system tray.</span></span>
    
6. <span data-ttu-id="65de7-352">Vérifiez que l’option de projection vers ce PC est activée avec l’application connexion.</span><span class="sxs-lookup"><span data-stu-id="65de7-352">Verify projecting to this PC is enabled with the Connect App.</span></span> <span data-ttu-id="65de7-353">Après la configuration  **de Project avec ce paramètre de PC** , exécutez l’application de connexion au moins une fois.</span><span class="sxs-lookup"><span data-stu-id="65de7-353">After configuring  **Project to this PC** settings, run the Connect App at least once.</span></span> <span data-ttu-id="65de7-354">(Par la suite, l’application connexion n’a pas besoin d’être en cours d’exécution pour projeter sur surface Hub.)</span><span class="sxs-lookup"><span data-stu-id="65de7-354">(Subsequently, the Connect App does not need to be running in order to project to Surface Hub.)</span></span>

7. <span data-ttu-id="65de7-355">Vérifiez les paramètres d’alimentation et de veille.</span><span class="sxs-lookup"><span data-stu-id="65de7-355">Verify power and sleep settings.</span></span>

    - <span data-ttu-id="65de7-356">Écran de veille: 15 minutes, définie sur (aucune), mystification ou Blank; Vérifiez que la case à cocher demander un mot de passe est activée.</span><span class="sxs-lookup"><span data-stu-id="65de7-356">Screen Saver: 15 minutes, set to (none), Mystify or Blank; ensure the check box for requiring password is selected.</span></span>
    - <span data-ttu-id="65de7-357">Écran: **désactiver après 2 heures**.</span><span class="sxs-lookup"><span data-stu-id="65de7-357">Screen: **Turn off after 2 hours**.</span></span>
    - <span data-ttu-id="65de7-358">PC:  **désactivez après 4 heures**.</span><span class="sxs-lookup"><span data-stu-id="65de7-358">PC:  **Turn off after 4 hours**.</span></span>
    
8. <span data-ttu-id="65de7-359">Vérifiez que Windows Hello fonctionne.</span><span class="sxs-lookup"><span data-stu-id="65de7-359">Verify Windows Hello is working.</span></span>

9. <span data-ttu-id="65de7-360">Vérifier la synchronisation vos paramètres sont désactivés.</span><span class="sxs-lookup"><span data-stu-id="65de7-360">Verify sync your settings is disabled.</span></span>

10. <span data-ttu-id="65de7-361">Vérifiez les applications de démarrage.</span><span class="sxs-lookup"><span data-stu-id="65de7-361">Verify startup apps.</span></span>

> [!TIP]
> <span data-ttu-id="65de7-362">Après l’installation et la configuration de Windows 10, les applications de surface Hub 2 peuvent être gérées comme n’importe quel autre appareil Windows 10.</span><span class="sxs-lookup"><span data-stu-id="65de7-362">After installing and configuring Windows 10, the Surface Hub 2S can be managed just like any other Windows 10 device.</span></span>

## <span data-ttu-id="65de7-363">Rubriques associées</span><span class="sxs-lookup"><span data-stu-id="65de7-363">Related topics</span></span>

[<span data-ttu-id="65de7-364">Migrer vers Windows 10 Professionnel ou Entreprise sur Surface Hub 2</span><span class="sxs-lookup"><span data-stu-id="65de7-364">Migrate to Windows 10 Pro or Enterprise on Surface Hub 2</span></span>](surface-hub-2s-migrate-os.md)
