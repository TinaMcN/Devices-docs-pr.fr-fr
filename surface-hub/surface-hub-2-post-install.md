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
ms.date: 12/08/2020
appliesto:
- Surface Hub 2S
ms.openlocfilehash: 7accbe3d905af3b295f92c002eecd5d77356672d
ms.sourcegitcommit: e126b8ac66a781ebe42cdd677af3fe6a2eb5e72c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/09/2020
ms.locfileid: "11203553"
---
# <span data-ttu-id="6c180-104">Configurer Windows 10 Professionnel ou Entreprise sur Surface Hub 2</span><span class="sxs-lookup"><span data-stu-id="6c180-104">Configure Windows 10 Pro or Enterprise on Surface Hub 2</span></span>

<span data-ttu-id="6c180-105">Après avoir terminé le processus d’installation de la migration vers Windows 10 professionnel ou entreprise, vous pouvez effectuer les étapes suivantes pour configurer les applications et les paramètres sur votre surface Hub 2.</span><span class="sxs-lookup"><span data-stu-id="6c180-105">After you have completed the installation process of migrating to Windows 10 Pro or Enterprise, you can perform the following steps to configure apps and settings on your Surface Hub 2.</span></span> <span data-ttu-id="6c180-106">Ces étapes sont recommandées pour garantir la meilleure utilisation de cette fonction d’affichage du stylo et de l’écran grand écran.</span><span class="sxs-lookup"><span data-stu-id="6c180-106">These steps are recommended to ensure the best experience when using this personalized large screen touch and pen computer.</span></span>

<span data-ttu-id="6c180-107">Lors de cette procédure, il peut s’avérer utile d’utiliser un clavier et une souris sans fil.</span><span class="sxs-lookup"><span data-stu-id="6c180-107">When performing these steps, you might find it useful to use a wired or wireless keyboard and mouse.</span></span>

## <span data-ttu-id="6c180-108">Configurer les paramètres système</span><span class="sxs-lookup"><span data-stu-id="6c180-108">Configure system settings</span></span>

1. <span data-ttu-id="6c180-109">Connectez-vous à l’aide d’un compte disposant de privilèges d’administrateur local sur l’appareil.</span><span class="sxs-lookup"><span data-stu-id="6c180-109">Sign in with an account that has local administrator privileges on the device.</span></span>  

    - <span data-ttu-id="6c180-110">Sur les appareils disposant d’Azure AD, l’utilisateur qui exécute la jointure Azure AD est automatiquement ajouté au groupe d’administrateurs local.</span><span class="sxs-lookup"><span data-stu-id="6c180-110">On Azure AD joined devices, the user that performs the Azure AD join is automatically added to the local administrator group.</span></span> <span data-ttu-id="6c180-111">Les administrateurs généraux d’Azure AD et d’Azure AD sont <a href="https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin" target="_blank"> également administrateurs locaux </a> .</span><span class="sxs-lookup"><span data-stu-id="6c180-111">Azure AD global administrators and Azure AD devices administrators are <a href="https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin" target="_blank">also local administrators</a>.</span></span> 
    
    - <span data-ttu-id="6c180-112">Vous pouvez taper **administrateurs .net localgroup** à une invite de commandes pour répertorier les comptes disposant de droits d’administrateur local.</span><span class="sxs-lookup"><span data-stu-id="6c180-112">You can type **net localgroup administrators** at a command prompt to list the accounts that have local administrator rights.</span></span>
    
2. <span data-ttu-id="6c180-113">Renommez l’appareil en utilisant un nom convivial, par exemple: **nom_utilisateur-SHub-Desktop**.</span><span class="sxs-lookup"><span data-stu-id="6c180-113">Rename the device using a friendly name, for example: **username-SHub-Desktop**.</span></span>

3. <span data-ttu-id="6c180-114">Sélectionnez **Démarrer**  >  les**paramètres**des  >  **comptes**pour  >  **synchroniser vos paramètres** et désactiver les **paramètres de synchronisation** .</span><span class="sxs-lookup"><span data-stu-id="6c180-114">Select **Start** > **Settings** > **Accounts** > **Sync your settings** and turn **Sync settings** off.</span></span> 

    - <span data-ttu-id="6c180-115">Les paramètres utilisés ici sont destinés à permettre une meilleure utilisation de l’affichage des fonctions visuelles de grande taille et, par conséquent, vous ne souhaitez pas synchroniser d’autres appareils.</span><span class="sxs-lookup"><span data-stu-id="6c180-115">The settings used here are intended to enable the best large-screen touch experience, and therefore you may not want to sync other devices.</span></span>
    
4. <span data-ttu-id="6c180-116">Redémarrez l’appareil.</span><span class="sxs-lookup"><span data-stu-id="6c180-116">Restart the device.</span></span>

## <span data-ttu-id="6c180-117">Activez le clavier tactile et le pavé tactile.</span><span class="sxs-lookup"><span data-stu-id="6c180-117">Enable the touch keyboard and touchpad</span></span>

1. <span data-ttu-id="6c180-118">Appuyez de façon prolongée ou cliquez avec le bouton droit sur la barre des tâches, puis sélectionnez **afficher le bouton du clavier tactile** et **afficher le bouton du pavé**tactile.</span><span class="sxs-lookup"><span data-stu-id="6c180-118">Tap and hold or right-click the taskbar and then select **Show touch keyboard button** and **Show touchpad button**.</span></span> 

    - <span data-ttu-id="6c180-119">Le clavier tactile est utile pour la saisie directe de l’utilisateur, et le pavé tactile virtuel permet d’effectuer des sélections précises, de pointage sur les info-bulles ou d’appuyer longuement sur un clic avec le bouton droit.</span><span class="sxs-lookup"><span data-stu-id="6c180-119">The touch keyboard is helpful for direct user input, and the virtual touchpad helps with precise selections, hovering screen tips, or as an alternative to tap and hold for right-click.</span></span> 
    
    - <span data-ttu-id="6c180-120">Consultez l’exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="6c180-120">See the following example.</span></span>

      ![Paramètres d’interaction](images/touch.png)

2. <span data-ttu-id="6c180-122">Configurez le clavier visuel sur azerty et flottez.</span><span class="sxs-lookup"><span data-stu-id="6c180-122">Configure the touch keyboard to QWERTY and floating.</span></span>

    1. <span data-ttu-id="6c180-123">Cliquez sur l’icône de **clavier** dans la barre des tâches pour afficher le clavier visuel.</span><span class="sxs-lookup"><span data-stu-id="6c180-123">Select the **Keyboard** icon on the taskbar to show the touch keyboard.</span></span>
    
    2. <span data-ttu-id="6c180-124">Sur le clavier visuel, sélectionnez l’icône de clavier dans le coin supérieur gauche pour ouvrir les paramètres du clavier.</span><span class="sxs-lookup"><span data-stu-id="6c180-124">On the touch keyboard, select the keyboard icon in the upper left corner to open keyboard settings.</span></span>
    
    3. <span data-ttu-id="6c180-125">Activez la case à cocher en regard de dernier type de clavier dans la ligne du haut pour activer AZERTY, et la dernière option pour activer le mode flottant, ce qui est très utile sur ce grand écran.</span><span class="sxs-lookup"><span data-stu-id="6c180-125">Select the next to last keyboard type on the top row to enable QWERTY, and the last option on the second row to enable floating, which is very helpful on this large screen.</span></span> <span data-ttu-id="6c180-126">Consultez les exemples suivants.</span><span class="sxs-lookup"><span data-stu-id="6c180-126">See the following examples.</span></span>

       ![Paramètres du clavier](images/kbd.png)
 
3. <span data-ttu-id="6c180-128">Configurez les paramètres de clavier logiciels.</span><span class="sxs-lookup"><span data-stu-id="6c180-128">Configure the soft keyboard settings.</span></span>

    1. <span data-ttu-id="6c180-129">Sélectionnez l’icône **paramètres** sur le clavier ou recherchez et ouvrez les **paramètres de saisie**.</span><span class="sxs-lookup"><span data-stu-id="6c180-129">Select the **Settings** icon on the touch keyboard or search for and open **Typing settings**.</span></span>
    
       ![paramètres de clavier logiciels](images/sh2-softkeyboard.png)

    1. <span data-ttu-id="6c180-131">Activez toutes les options sous orthographe, saisie et clavier vocal.</span><span class="sxs-lookup"><span data-stu-id="6c180-131">Enable all the options under Spelling, Typing, and Touch keyboard.</span></span>


<span data-ttu-id="6c180-132">L’exemple suivant illustre pavé tactile, qui est utile pour naviguer et sélectionner des options.</span><span class="sxs-lookup"><span data-stu-id="6c180-132">The following example shows the trackpad, which is useful to navigate and select options.</span></span> <span data-ttu-id="6c180-133">Le clavier à l’écran est utilisé pour effectuer une recherche sur le Microsoft Store:</span><span class="sxs-lookup"><span data-stu-id="6c180-133">The onscreen keyboard is being used to search the Microsoft Store:</span></span>

![Utiliser le pavé tactile](images/store.png)

## <span data-ttu-id="6c180-135">Configurer le clavier et la souris Bluetooth (facultatif)</span><span class="sxs-lookup"><span data-stu-id="6c180-135">Configure Bluetooth keyboard and mouse (optional)</span></span>

<span data-ttu-id="6c180-136">Connectez un clavier et une souris si vous utilisez le périphérique en tant qu’appareil Windows principal, ou si vous utilisez souvent cette fonctionnalité pour la saisie ou la précision du fonctionnement.</span><span class="sxs-lookup"><span data-stu-id="6c180-136">Connect a keyboard and mouse if you are using the device as your primary Windows device, or you use it often for typing or precision work.</span></span>

<span data-ttu-id="6c180-137">Si votre périphérique surface Hub est proche d’un PC, vous pouvez utiliser <a href="https://aka.ms/mm" target="_blank"> la souris sans bordure </a> pour vous déplacer en douceur entre le centre de surface et le PC.</span><span class="sxs-lookup"><span data-stu-id="6c180-137">If your Surface Hub device is near to a PC, you can use <a href="https://aka.ms/mm" target="_blank"> Mouse without Borders</a> to move seamlessly between the Surface Hub and the PC.</span></span> <span data-ttu-id="6c180-138">Pour plus d’informations, reportez-vous <a href="https://blogs.microsoft.com/ai/microsoft-download-from-the-garage-mouse-without-borders/" target="_blank"> à la rubrique téléchargement de Microsoft à partir du garage: souris sans bordure.</span><span class="sxs-lookup"><span data-stu-id="6c180-138">For more information, see <a href="https://blogs.microsoft.com/ai/microsoft-download-from-the-garage-mouse-without-borders/" target="_blank"> Microsoft download from The Garage: Mouse without Borders.</span></span> </a>

## <span data-ttu-id="6c180-139">Exemple de disposition de barre des tâches</span><span class="sxs-lookup"><span data-stu-id="6c180-139">Example of Taskbar layout</span></span>

<span data-ttu-id="6c180-140">Après avoir suivi les étapes ci-dessous pour configurer et configurer votre surface Hub 2 pour Windows 10 professionnel ou entreprise, nous vous recommandons d’utiliser la fonction épingler les applications les plus utilisées à la barre des tâches pour un lancement rapide d’une touche unique de chaque application.</span><span class="sxs-lookup"><span data-stu-id="6c180-140">After completing the below steps to setup/configure your Surface Hub 2 for Windows 10 Professional or Enterprise, we recommend you utilize pinning your most used applications to the Taskbar for a quick one-touch launch of each application.</span></span> <span data-ttu-id="6c180-141">Vous trouverez ci-dessous un exemple d’aspect de la barre des tâches:</span><span class="sxs-lookup"><span data-stu-id="6c180-141">Below is an example of what your taskbar could look like:</span></span>

 ![Disposition de la barre des tâches](images/taskblyt.png)
### <span data-ttu-id="6c180-143">Mettre à jour les applications installées</span><span class="sxs-lookup"><span data-stu-id="6c180-143">Update installed apps</span></span>

<span data-ttu-id="6c180-144">Pour mettre à jour toutes les applications du Windows Store installées:</span><span class="sxs-lookup"><span data-stu-id="6c180-144">To update all installed Store apps:</span></span>

1. <span data-ttu-id="6c180-145">Ouvrez l’application Microsoft Store et sélectionnez les points de suspension **voir plus** dans le coin supérieur droit.</span><span class="sxs-lookup"><span data-stu-id="6c180-145">Open Microsoft Store app and select the **See more** ellipsis in the top-right corner.</span></span>
2. <span data-ttu-id="6c180-146">Sélectionnez **téléchargements et mises à jour.**</span><span class="sxs-lookup"><span data-stu-id="6c180-146">Select **Downloads and updates.**</span></span>
3. <span data-ttu-id="6c180-147">Sélectionnez **obtenir les mises à jour**</span><span class="sxs-lookup"><span data-stu-id="6c180-147">Select **Get updates**</span></span>

### <span data-ttu-id="6c180-148">Recherchez et installez toutes les mises à jour Windows.</span><span class="sxs-lookup"><span data-stu-id="6c180-148">Scan for and install all Windows Updates</span></span>
<span data-ttu-id="6c180-149">Après la migration vers Windows 10 professionnel ou Windows 10 entreprise, des mises à jour de maintenance et de fonctionnalités peuvent être disponibles pour que vous puissiez les installer.</span><span class="sxs-lookup"><span data-stu-id="6c180-149">After migrating to Windows 10 Professional or Windows 10 Enterprise, there may be servicing and feature updates available for you to install.</span></span> 

- <span data-ttu-id="6c180-150">Accédez à **Settings**  >  **mise à jour** des paramètres & > de sécurité, puis sélectionnez **Rechercher les mises à jour**.</span><span class="sxs-lookup"><span data-stu-id="6c180-150">Go to **Settings** > **Update & Security** > and then select **Check for updates**.</span></span>
- <span data-ttu-id="6c180-151">S’il existe des mises à jour, installez-les, redémarrez, puis répétez la procédure jusqu’à ce que le message suivant s’affiche:</span><span class="sxs-lookup"><span data-stu-id="6c180-151">If there are any updates, install them, reboot, and then repeat the process until you see the following notification:</span></span>

> [!div class="mx-imgBorder"]
> ![Notification de la mise à jour de Windows Update](images/wustatus.png)


## <span data-ttu-id="6c180-153">OneDriveEntreprise</span><span class="sxs-lookup"><span data-stu-id="6c180-153">OneDrive for Business</span></span>

<span data-ttu-id="6c180-154">Utilisez <a href="https://docs.microsoft.com/onedrive/onedrive" target="_blank"> OneDrive entreprise </a> pour partager facilement des outils, des journaux et d’autres fichiers entre tous vos périphériques de travail.</span><span class="sxs-lookup"><span data-stu-id="6c180-154">Use <a href="https://docs.microsoft.com/onedrive/onedrive" target="_blank"> OneDrive for Business</a> to easily share tools, logs, and other files between all your work devices.</span></span>

- <span data-ttu-id="6c180-155">OneDrive vous permet de partager vos fichiers de travail entre votre ordinateur portable, votre bureau surface Hub et vos appareils mobiles gérés par Intune.</span><span class="sxs-lookup"><span data-stu-id="6c180-155">OneDrive enables you to share your work files between your laptops, Surface Hub Desktop, and your Intune-managed mobile devices.</span></span> <span data-ttu-id="6c180-156">Les fichiers peuvent être modifiés sur n’importe quel appareil, et tous les appareils connectés réseau sont mis à jour avec les modifications.</span><span class="sxs-lookup"><span data-stu-id="6c180-156">Files can be edited on any device, and all network connected devices will be updated with the changes.</span></span>

- <span data-ttu-id="6c180-157">Si vous considérez la taille de la fonction SSD de surface Hub (128 Go), si vous configurez OneDrive sur votre appareil de bureau surface Hub, assurez-vous que la configuration par défaut est de conserver les fichiers en ligne et de télécharger des fichiers lorsque vous les utilisez.</span><span class="sxs-lookup"><span data-stu-id="6c180-157">Considering the size of the Surface Hub SSD (128GB), if you configure OneDrive on your Surface Hub Desktop device, make sure the default configuration is to keep the files online and download files as you use them.</span></span>

<span data-ttu-id="6c180-158">Pour configurer OneDrive pour télécharger les fichiers uniquement lorsque cela est nécessaire, définissez le paramètre **fichiers à la demande** pour **économiser de l’espace et télécharger les fichiers lorsque vous les utilisez**.</span><span class="sxs-lookup"><span data-stu-id="6c180-158">To configure OneDrive to download files only when needed, set the **Files On-Demand** setting to **Save space and download files as you use them**.</span></span> <span data-ttu-id="6c180-159">Pour plus d’informations, reportez-vous à <a href="https://docs.microsoft.com/onedrive/files-on-demand-windows" target="_blank"> la rubrique interroger et définir des fichiers à la demande dans Windows </a> .</span><span class="sxs-lookup"><span data-stu-id="6c180-159">For more information, see <a href="https://docs.microsoft.com/onedrive/files-on-demand-windows" target="_blank"> Query and set Files On-Demand states in Windows</a>.</span></span>

![Paramètres de OneDrive](images/onedrive.png)

> [!NOTE]
> <span data-ttu-id="6c180-161">Vous pouvez également répéter ces étapes pour configurer votre espace OneDrive personnel, mais n’êtes pas sûr de ménager de l’espace disque et de télécharger uniquement les fichiers dont vous avez besoin.</span><span class="sxs-lookup"><span data-stu-id="6c180-161">You can also repeat these steps to configure a personal OneDrive but be sure to conserve drive space and only download files as you need them.</span></span>

## <span data-ttu-id="6c180-162">SharePoint et Teams</span><span class="sxs-lookup"><span data-stu-id="6c180-162">SharePoint and Teams</span></span>

<span data-ttu-id="6c180-163">Les fichiers de canal SharePoint et teams peuvent également être synchronisés localement sur vos appareils de bureau, tels que les ordinateurs portables et les hubs de surface, à l’aide du moteur de synchronisation OneDrive.</span><span class="sxs-lookup"><span data-stu-id="6c180-163">SharePoint and Teams Channel files can also sync locally to your desktop devices, such as laptops and Surface Hubs, using the OneDrive sync engine.</span></span>

<span data-ttu-id="6c180-164">Pour synchroniser des fichiers d’entreprise internes sur votre disque local à l’aide de l’application de synchronisation OneDrive:</span><span class="sxs-lookup"><span data-stu-id="6c180-164">To sync internal corporate files to your local drive with the OneDrive sync app:</span></span>

1. <span data-ttu-id="6c180-165">Accédez à un site SharePoint et naviguez jusqu’au répertoire de documents de niveau supérieur correspondant aux fichiers que vous souhaitez afficher ou modifier à partir de votre appareil local.</span><span class="sxs-lookup"><span data-stu-id="6c180-165">Go to a SharePoint site and navigate to the top-level document directory for files that you are interested in viewing or editing from your local device.</span></span>

2. <span data-ttu-id="6c180-166">Cliquez sur le bouton **synchroniser** situé en haut du ruban SharePoint.</span><span class="sxs-lookup"><span data-stu-id="6c180-166">Select on the **Sync** button on the top of the SharePoint ribbon.</span></span>

3. <span data-ttu-id="6c180-167">Sélectionner sur **ouvrir** dans le menu contextuel **ce site tente d’ouvrir Microsoft OneDrive**.</span><span class="sxs-lookup"><span data-stu-id="6c180-167">Select on **Open** on the popup **This site is trying to open Microsoft OneDrive**.</span></span>

4. <span data-ttu-id="6c180-168">Vérifiez que les fichiers SharePoint sont synchronisés avec votre lecteur local en sélectionnant l’icône OneDrive située en bas à droite de la barre des tâches.</span><span class="sxs-lookup"><span data-stu-id="6c180-168">Verify that the SharePoint files are synchronizing to your local drive by selecting on the OneDrive icon at the bottom right of the taskbar.</span></span>

5. <span data-ttu-id="6c180-169">Vérifiez que la configuration est définie pour conserver les fichiers en ligne et télécharger les fichiers uniquement lors de leur utilisation:</span><span class="sxs-lookup"><span data-stu-id="6c180-169">Verify the configuration is set to keep the files online and download the files only as you use them:</span></span>

    1. <span data-ttu-id="6c180-170">Ouvrez l’Explorateur de fichiers.</span><span class="sxs-lookup"><span data-stu-id="6c180-170">Open file explorer.</span></span>
    
    2. <span data-ttu-id="6c180-171">Accédez et cliquez avec le bouton droit sur votre nom SharePoint; par exemple, \*\*contoso \ \<SharePoint Document Folder Name\> \*\*.</span><span class="sxs-lookup"><span data-stu-id="6c180-171">Navigate to and right click your SharePoint name; for example, **Contoso \ \<SharePoint Document Folder Name\>**.</span></span>
    
    3. <span data-ttu-id="6c180-172">Sélectionnez **libérer**de l’espace.</span><span class="sxs-lookup"><span data-stu-id="6c180-172">Select **Free up space**.</span></span>
    
    4. <span data-ttu-id="6c180-173">La colonne État affiche l’état des fichiers et des dossiers.</span><span class="sxs-lookup"><span data-stu-id="6c180-173">The Status column will display the status of files and folders.</span></span> <span data-ttu-id="6c180-174">Pour plus d’informations, voir <a href="https://support.microsoft.com/office/sync-sharepoint-files-with-the-onedrive-sync-client-groove-exe-59b1de2b-519e-4d3a-8f45-51647cf291cd" target="_blank"> synchroniser des fichiers SharePoint avec le client de synchronisation OneDrive </a> .</span><span class="sxs-lookup"><span data-stu-id="6c180-174">For more information, see <a href="https://support.microsoft.com/office/sync-sharepoint-files-with-the-onedrive-sync-client-groove-exe-59b1de2b-519e-4d3a-8f45-51647cf291cd" target="_blank"> Sync SharePoint files with the OneDrive sync client</a>.</span></span>
    
6. <span data-ttu-id="6c180-175">Les fichiers de canal teams sont stockés sur des sites SharePoint, avec toutes les mêmes fonctionnalités de documents SharePoint, y compris l’historique des versions et la synchronisation avec les appareils de bureau locaux.</span><span class="sxs-lookup"><span data-stu-id="6c180-175">Teams Channel files are stored in SharePoint sites, with all of the same SharePoint document functionality, including version history and synchronizing to your local desktop devices.</span></span> <span data-ttu-id="6c180-176">Pour synchroniser des fichiers de canal d’équipe:</span><span class="sxs-lookup"><span data-stu-id="6c180-176">To sync Teams Channel files:</span></span>

    1. <span data-ttu-id="6c180-177">Accédez au canal d’intérêt de l’équipe et sélectionnez l’onglet **fichiers** en haut.</span><span class="sxs-lookup"><span data-stu-id="6c180-177">Navigate to the Teams Channel of interest and select the **Files** tab at the top.</span></span> <span data-ttu-id="6c180-178">Sélectionnez **synchroniser**. Les fichiers commenceront à se synchroniser et sont visibles dans l’Explorateur de fichiers sur le \*\*Bureau \ contoso \ \<name of the Teams Channel\> \*\*.</span><span class="sxs-lookup"><span data-stu-id="6c180-178">Then select **Sync**. The files will start synchronizing and will be visible in File Explorer at **Desktop \ Contoso \ \<name of the Teams Channel\>**.</span></span>
    
    2. <span data-ttu-id="6c180-179">Utilisez la même procédure que celle que vous avez utilisée pour synchroniser des sites SharePoint afin de conserver les fichiers dans le Cloud et de les télécharger uniquement lorsque vous les utilisez, appuyez longuement ou cliquez avec le bouton droit dans l’Explorateur de fichiers sur le nom du canal Teams, puis sélectionnez libérer de l' **espace**.</span><span class="sxs-lookup"><span data-stu-id="6c180-179">Use the same procedure that you used for synchronizing SharePoint sites to keep the files in the cloud and only download them when you use them, by tap and hold or right-click in File Explorer on the Teams Channel name, and then selecting **Free up space**.</span></span>

## <span data-ttu-id="6c180-180">Paramètres de stylet surface Hub</span><span class="sxs-lookup"><span data-stu-id="6c180-180">Surface Hub pen settings</span></span>

**<span data-ttu-id="6c180-181">Couplez le stylo Bluetooth surface Hub</span><span class="sxs-lookup"><span data-stu-id="6c180-181">Pair the Bluetooth Surface Hub Pen</span></span>**

<span data-ttu-id="6c180-182">Couplez le stylet pour garder le microprogramme du stylo à jour, définissez les raccourcis clavier et obtenez des informations sur la charge de la batterie dans la page Paramètres de l’appareil Bluetooth ou dans l’application surface:</span><span class="sxs-lookup"><span data-stu-id="6c180-182">Pair the pen to keep the pen firmware up to date, set the pen shortcuts, and get battery charge information on the Bluetooth device settings page, or in the Surface app:</span></span>

1. <span data-ttu-id="6c180-183">Sélectionnez Paramètres de **démarrage**de l'  >  **Settings**  >  **appareil**.</span><span class="sxs-lookup"><span data-stu-id="6c180-183">Select **Start** > **Settings** > **Devices**.</span></span>

2. <span data-ttu-id="6c180-184">Sélectionnez **Ajouter un appareil Bluetooth ou un autre appareil**.</span><span class="sxs-lookup"><span data-stu-id="6c180-184">Select **Add Bluetooth or other device**.</span></span>

3. <span data-ttu-id="6c180-185">Sélectionnez **Bluetooth**.</span><span class="sxs-lookup"><span data-stu-id="6c180-185">Choose **Bluetooth**.</span></span>

4. <span data-ttu-id="6c180-186">Supprimez le bouton de queue du stylo et secouez la connexion à la batterie.</span><span class="sxs-lookup"><span data-stu-id="6c180-186">Remove the pen tail button and shake to disconnect the battery connection.</span></span>

5. <span data-ttu-id="6c180-187">Placez le capuchon en retour, puis appuyez de façon prolongée sur le capuchon jusqu’à ce que le voyant du jumelage clignote.</span><span class="sxs-lookup"><span data-stu-id="6c180-187">Put the cap back on and press and hold the cap until the pairing LED flashes.</span></span>

6. <span data-ttu-id="6c180-188">Dans les paramètres Bluetooth surface Hub, sélectionnez **surface Hub 2 PEN**.</span><span class="sxs-lookup"><span data-stu-id="6c180-188">On the Surface Hub Bluetooth settings, choose **Surface Hub 2 Pen**.</span></span>

7. <span data-ttu-id="6c180-189">Terminez l’opération de jumelage.</span><span class="sxs-lookup"><span data-stu-id="6c180-189">Complete the pairing operation.</span></span> 

8. <span data-ttu-id="6c180-190">Si le jumelage ne fonctionne pas, vous pouvez essayer de jumeler de nouveau le stylet.</span><span class="sxs-lookup"><span data-stu-id="6c180-190">If the pairing is not successful, you can attempt to pair the pen again.</span></span> <span data-ttu-id="6c180-191">Si cela ne fonctionne pas, vous pouvez effectuer des tests pour savoir si la batterie est débitée en vérifiant que le stylet fonctionne dans l’application tableau blanc.</span><span class="sxs-lookup"><span data-stu-id="6c180-191">If that doesn't work, you can test to see if the battery is charged by verifying the pen works in the Whiteboard application.</span></span> <span data-ttu-id="6c180-192">Si ce n’est pas le cas, remplacez la batterie, puis essayez à nouveau de jumeler le stylet.</span><span class="sxs-lookup"><span data-stu-id="6c180-192">If not, then replace the battery and then try to pair the pen again.</span></span> <span data-ttu-id="6c180-193">Le cas échéant, redémarrez l’appareil, puis réessayez.</span><span class="sxs-lookup"><span data-stu-id="6c180-193">If necessary, restart the device and then try again.</span></span>

<span data-ttu-id="6c180-194">**Définir des raccourcis de stylet** Le stylet surface Hub est parfois désigné par un bouton de raccourci.</span><span class="sxs-lookup"><span data-stu-id="6c180-194">**Set pen shortcuts** The Surface Hub pen has a shortcut button sometimes referred to as a "tail click".</span></span> <span data-ttu-id="6c180-195">Pour configurer des raccourcis, vous devez d’abord coupler le stylet, comme décrit précédemment.</span><span class="sxs-lookup"><span data-stu-id="6c180-195">Configuring shortcuts requires you to first pair the pen, as described earlier.</span></span>

1. <span data-ttu-id="6c180-196">Recherchez stylo et sélectionnez **stylo & paramètres Windows Ink**.</span><span class="sxs-lookup"><span data-stu-id="6c180-196">Search for Pen and select **Pen & Windows Ink settings**.</span></span>

2. <span data-ttu-id="6c180-197">Dans la partie inférieure de la page, sélectionnez raccourcis clavier permettant d’ouvrir la boîte de dialogue, comme suit:</span><span class="sxs-lookup"><span data-stu-id="6c180-197">Near the bottom of the page, select Pen shortcuts which opens the dialog box, shown here:</span></span>

   ![Raccourcis clavier](images/sh2-pen-shortcuts.png)

## <span data-ttu-id="6c180-199">Configuration de la caméra</span><span class="sxs-lookup"><span data-stu-id="6c180-199">Camera configuration</span></span>

<span data-ttu-id="6c180-200">Vous pouvez monter la caméra sur le dessus ou sur l’un ou l’autre extrémité de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="6c180-200">You can mount the camera on the top or on either side of the device.</span></span> <span data-ttu-id="6c180-201">Montez l’appareil photo en position pour optimiser l’angle de la caméra si vous utilisez le concentrateur avec un socle de bureau plutôt qu’un panier, ou que vous êtes en proximité du Hub.</span><span class="sxs-lookup"><span data-stu-id="6c180-201">Mount the camera in a position to optimize the camera angle if you are using the Hub with a desktop stand instead of a cart, or are in close proximity to the Hub.</span></span> <span data-ttu-id="6c180-202">Comme la caméra ne pivote pas automatiquement, vous devez disposer d’une touche hexadécimale 2mm pour faire pivoter manuellement la caméra.</span><span class="sxs-lookup"><span data-stu-id="6c180-202">The camera does not auto-rotate, so you need to have a 2mm hex key to manually rotate the camera.</span></span> 

<span data-ttu-id="6c180-203">Pour plus d’informations sur la façon de monter la caméra et de la faire pivoter manuellement, voir orientation de l’objectif de la caméra <a href="https://support.microsoft.com/help/4509729/surface-hub-2s-camera-lens-orientation" target="_blank"> surface Hub </a> .</span><span class="sxs-lookup"><span data-stu-id="6c180-203">For more information on how to side-mount the camera and rotate the camera manually, see <a href="https://support.microsoft.com/help/4509729/surface-hub-2s-camera-lens-orientation" target="_blank"> Surface Hub 2S camera lens orientation</a>.</span></span>

## <span data-ttu-id="6c180-204">Configuration de Windows Hello</span><span class="sxs-lookup"><span data-stu-id="6c180-204">Windows Hello configuration</span></span>

<span data-ttu-id="6c180-205">Surface Hub 2-xxxxx xxx XXXXXXX XXXXXXX xxxx xxx xxxxxxx xxx XXXXXXX XXXXXXX XXXXXXX XXXXXXX XXXXXXX XXXXXXX XXXXXXX XXXXXXX xxxx.</span><span class="sxs-lookup"><span data-stu-id="6c180-205">Surface Hub 2S running Windows 10 Enterprise allows the full suite of Win32 desktop applications as well as biometric Windows Hello options.</span></span> <span data-ttu-id="6c180-206">Les accessoires du lecteur d’empreintes digitales de surface Hub 2 peuvent être branchés dans n’importe quel port USB-C de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="6c180-206">The Surface Hub 2 Fingerprint Reader accessory can be plugged into any USB-C port on the device.</span></span> 

<span data-ttu-id="6c180-207">Pour commander un lecteur d’empreintes digitales de surface Hub 2 ou afficher des spécifications techniques, voir (surface-hub-2-essential-add-ons.md "target =" _blank ">composants additionnels essentiels pour Windows 10 professionnel et entreprise sur surface Hub 2) </a> .</span><span class="sxs-lookup"><span data-stu-id="6c180-207">To order a Surface Hub 2 Fingerprint Reader or view technical specs, see (surface-hub-2-essential-add-ons.md" target="_blank">Essential add-ons for Windows 10 Pro and Enterprise on Surface Hub 2 </a>.</span></span> 

<span data-ttu-id="6c180-208">Après avoir inséré le lecteur d’empreintes digitales **, sélectionnez**  >  **paramètres**  >  **Accounts**  >  **de connexion comptes options de connexion dans**  >  votre**empreinte digitale Windows Hello** pour inscrire votre empreinte digitale.</span><span class="sxs-lookup"><span data-stu-id="6c180-208">After inserting the fingerprint reader, select **Start** > **Settings** > **Accounts** > **Sign-in options** > **Windows Hello Fingerprint** to enroll your fingerprint.</span></span>

<span data-ttu-id="6c180-209">Utilisez un appareil certifié Windows Hello pour la reconnaissance faciale.</span><span class="sxs-lookup"><span data-stu-id="6c180-209">Use a Windows Hello certified device for face recognition.</span></span> <span data-ttu-id="6c180-210">La caméra surface Hub 2 ne prend pas en charge la reconnaissance faciale Windows Hello.</span><span class="sxs-lookup"><span data-stu-id="6c180-210">The Surface Hub 2S camera does not support Windows Hello face recognition.</span></span>

## <span data-ttu-id="6c180-211">Activer un raccourci de l’écran de verrouillage dans la barre des tâches</span><span class="sxs-lookup"><span data-stu-id="6c180-211">Enable a Lock Screen shortcut icon on the taskbar</span></span>

<span data-ttu-id="6c180-212">Pour ajouter une icône à la barre des tâches qui permet le verrouillage de l’écran à une seule touche, comme le raccourci clavier Windows-L:</span><span class="sxs-lookup"><span data-stu-id="6c180-212">To add an icon to the taskbar that enables one-touch screen lock similar to the Windows-L keyboard shortcut:</span></span> 

1.  <span data-ttu-id="6c180-213">Appuyez de façon prolongée ou cliquez avec le bouton droit sur le bureau, sélectionnez **nouveau**  >  **raccourci**  >  **Parcourir**le  >  **Bureau**  >  **OK**  >  **suivant**.</span><span class="sxs-lookup"><span data-stu-id="6c180-213">Tap and hold or right-click on the desktop, select **New** > **Shortcut** > **Browse** > **Desktop** > **OK** > **Next**.</span></span>

1.  <span data-ttu-id="6c180-214">Indiquez un nom pour le raccourci tel que **verrouiller mon PC**, puis cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="6c180-214">Provide a name for the shortcut such as **Lock my PC**, and then select **Finish**.</span></span>

1.  <span data-ttu-id="6c180-215">Cliquez avec le bouton droit ou appuyez longuement sur le raccourci qui vient d’être créé sur le bureau, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="6c180-215">Right-click or tap and hold the newly created shortcut on the desktop, and select **Properties**.</span></span> <span data-ttu-id="6c180-216">Dans l’onglet **raccourci** , entrez les informations suivantes dans le champ **cible** : **Rundll32.exe User32.dll LockWorkStation**</span><span class="sxs-lookup"><span data-stu-id="6c180-216">On the **Shortcut** tab, enter the following in the **Target** field: **Rundll32.exe User32.dll,LockWorkStation**</span></span>

1.  <span data-ttu-id="6c180-217">Cliquez sur le bouton **modifier l’icône** et recherchez **C:\Windows\System32\imageres.dll** et sélectionnez une icône à utiliser.</span><span class="sxs-lookup"><span data-stu-id="6c180-217">Select the **Change Icon** button and browse to **C:\Windows\System32\imageres.dll** and select an icon to use.</span></span> 

    <span data-ttu-id="6c180-218">Consultez l’exemple suivant:</span><span class="sxs-lookup"><span data-stu-id="6c180-218">See the following example:</span></span>

    ![Choisir une icône](images/lock.png)
    
1.  <span data-ttu-id="6c180-220">Cliquez sur **OK** pour enregistrer le raccourci.</span><span class="sxs-lookup"><span data-stu-id="6c180-220">Select **OK** to save the shortcut.</span></span>

1.  <span data-ttu-id="6c180-221">Cliquez avec le bouton droit ou appuyez longuement sur le raccourci et sélectionnez **Épingler à la barre des tâches**.</span><span class="sxs-lookup"><span data-stu-id="6c180-221">Right-click or tap and hold the shortcut and select **Pin to taskbar**.</span></span>

1. <span data-ttu-id="6c180-222">Après avoir épinglé le raccourci de verrouillage dans la barre des tâches, vous pouvez le supprimer de votre ordinateur de bureau.</span><span class="sxs-lookup"><span data-stu-id="6c180-222">After you have pinned the lock shortcut to the taskbar, you can delete it from the desktop.</span></span>

## <span data-ttu-id="6c180-223">Applications</span><span class="sxs-lookup"><span data-stu-id="6c180-223">Applications</span></span>


### <span data-ttu-id="6c180-224">Tableau blanc Microsoft</span><span class="sxs-lookup"><span data-stu-id="6c180-224">Microsoft Whiteboard</span></span>

<span data-ttu-id="6c180-225">Pour installer le tableau blanc Microsoft, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="6c180-225">To install the Microsoft Whiteboard:</span></span>

 - <span data-ttu-id="6c180-226">Cliquez sur l’icône de l' **espace de travail Windows Ink** dans le coin inférieur droit de la barre des tâches et téléchargez le **tableau blanc**.</span><span class="sxs-lookup"><span data-stu-id="6c180-226">Select the **Windows Ink Workspace** icon on the lower right of the taskbar and download **Whiteboard**.</span></span>
 
   ![Espace de travail Ink](images/ink.png) 

<span data-ttu-id="6c180-228">Vous pouvez également installer le tableau blanc à partir du Microsoft Store:</span><span class="sxs-lookup"><span data-stu-id="6c180-228">Alternatively, you can install Whiteboard from the Microsoft Store:</span></span>

1. <span data-ttu-id="6c180-229">Ouvrez l’application Microsoft Store et recherchez le **tableau blanc**.</span><span class="sxs-lookup"><span data-stu-id="6c180-229">Open Microsoft Store app and search for **Whiteboard**.</span></span>

2. <span data-ttu-id="6c180-230">Choisissez **non merci** pour vous connecter et utiliser les différents appareils.</span><span class="sxs-lookup"><span data-stu-id="6c180-230">Choose **No thanks** to sign in and use across devices.</span></span>

3. <span data-ttu-id="6c180-231">Épingler le tableau blanc dans la barre des tâches.</span><span class="sxs-lookup"><span data-stu-id="6c180-231">Pin Whiteboard to the taskbar.</span></span>

### <span data-ttu-id="6c180-232">Application surface</span><span class="sxs-lookup"><span data-stu-id="6c180-232">Surface app</span></span>

1. <span data-ttu-id="6c180-233">Dans la boutique Microsoft, recherchez **surface**.</span><span class="sxs-lookup"><span data-stu-id="6c180-233">In the Microsoft Store, search for **Surface**.</span></span>

2. <span data-ttu-id="6c180-234">Définissez le **niveau de filtrage disponible sur** **tous les appareils**.</span><span class="sxs-lookup"><span data-stu-id="6c180-234">Set the **Available on** filter to **All devices**.</span></span>

3. <span data-ttu-id="6c180-235">Installez l’application **surface** .</span><span class="sxs-lookup"><span data-stu-id="6c180-235">Install the **Surface** app.</span></span> <span data-ttu-id="6c180-236">Il s’agit de la première application répertoriée.</span><span class="sxs-lookup"><span data-stu-id="6c180-236">This should be the first app listed.</span></span> <span data-ttu-id="6c180-237">Vous devrez peut-être associer votre MSA au Windows Store pour pouvoir installer l’application.</span><span class="sxs-lookup"><span data-stu-id="6c180-237">You might need to associate your MSA to the Store in order to install the app.</span></span>

4. <span data-ttu-id="6c180-238">Épingler l’application **surface** à la barre des tâches.</span><span class="sxs-lookup"><span data-stu-id="6c180-238">Pin the **Surface** app to taskbar.</span></span>

### <span data-ttu-id="6c180-239">Capture d'écran et Croquis</span><span class="sxs-lookup"><span data-stu-id="6c180-239">Snip & Sketch</span></span>

1. <span data-ttu-id="6c180-240">Ouvrez l’application de **capture & esquisse** et épinglez-la à la barre des tâches.</span><span class="sxs-lookup"><span data-stu-id="6c180-240">Open the **Snip & Sketch** app and pin it to the taskbar.</span></span>

2. <span data-ttu-id="6c180-241">Sélectionnez les points de suspension dans le coin supérieur droit, puis sélectionnez **paramètres**.</span><span class="sxs-lookup"><span data-stu-id="6c180-241">Select the ellipsis in the upper right corner and then select **Settings**.</span></span>

3. <span data-ttu-id="6c180-242">Dans **paramètres**, activez la fonction de **copie automatique dans le presse-papiers**, **Enregistrez les captures**et les **fenêtres multiples** (facultatif).</span><span class="sxs-lookup"><span data-stu-id="6c180-242">In **Settings**, turn on **Auto copy to clipboard**, **Save snips**, and **Multiple windows** (optional).</span></span>

### <span data-ttu-id="6c180-243">MicrosoftOffice</span><span class="sxs-lookup"><span data-stu-id="6c180-243">Microsoft Office</span></span>

1. <span data-ttu-id="6c180-244">Ouvrez le <a href="https://portal.office.com/account#installs" target="_blank"> portail Office </a> et installez les applications souhaitées.</span><span class="sxs-lookup"><span data-stu-id="6c180-244">Open the <a href="https://portal.office.com/account#installs" target="_blank"> Office Portal</a> and install your desired applications.</span></span>

2. <span data-ttu-id="6c180-245">Épinglez les applications Office souhaitées dans la barre des tâches.</span><span class="sxs-lookup"><span data-stu-id="6c180-245">Pin desired Office applications to the taskbar.</span></span>

3. <span data-ttu-id="6c180-246">Si Outlook est installé, assurez-vous de définir le cache OST Outlook de façon à ce qu’il enregistre uniquement le cache des deux dernières semaines.</span><span class="sxs-lookup"><span data-stu-id="6c180-246">If Outlook is installed, be sure to set the Outlook OST to only save last two weeks cache.</span></span> <span data-ttu-id="6c180-247">Le temps d’utilisation et de configuration du disque sera considérablement réduit.</span><span class="sxs-lookup"><span data-stu-id="6c180-247">This will vastly reduce disk usage and setup time.</span></span>

    - <span data-ttu-id="6c180-248">Sélectionnez **File**  >  **paramètres du compte** de fichier, puis sélectionnez votre compte.</span><span class="sxs-lookup"><span data-stu-id="6c180-248">Select **File** > **Account Settings** and select your account.</span></span>
    
    - <span data-ttu-id="6c180-249">Sélectionnez **modifier** , puis positionnez le curseur pour **utiliser le mode Exchange mis en cache** à 14 jours.</span><span class="sxs-lookup"><span data-stu-id="6c180-249">Select **Change** and set the slider for **Use Cached Exchange Mode** to 14 days.</span></span>

### <span data-ttu-id="6c180-250">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6c180-250">Microsoft Teams</span></span>

1. <span data-ttu-id="6c180-251">Télécharger et installer <a href="https://teams.microsoft.com/downloads" target="_blank"> Microsoft teams </a> .</span><span class="sxs-lookup"><span data-stu-id="6c180-251">Download and install <a href="https://teams.microsoft.com/downloads" target="_blank"> Microsoft Teams </a>.</span></span>

2. <span data-ttu-id="6c180-252">Configurez les paramètres de démarrage automatique de l’application (facultatif).</span><span class="sxs-lookup"><span data-stu-id="6c180-252">Configure settings to Auto-start application (optional).</span></span>

3. <span data-ttu-id="6c180-253">Épingler des équipes dans la barre des tâches.</span><span class="sxs-lookup"><span data-stu-id="6c180-253">Pin Teams to the taskbar.</span></span>

4. <span data-ttu-id="6c180-254">Envisagez de réduire les notifications d’équipe sur l’appareil pour éviter toute distraction (facultatif).</span><span class="sxs-lookup"><span data-stu-id="6c180-254">Consider reducing Teams notifications on the device to avoid distractions (optional).</span></span>

   ![Notifications teams](images/teams.png)

### <span data-ttu-id="6c180-256">Connecter l’application</span><span class="sxs-lookup"><span data-stu-id="6c180-256">Connect app</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6c180-257">Dans Windows 10, version 2004 et ultérieure, l’application connexion pour la projection sans fil à l’aide de Miracast n’est pas installée par défaut, mais est disponible sous la forme d’une fonctionnalité facultative.</span><span class="sxs-lookup"><span data-stu-id="6c180-257">In Windows 10, version 2004 and later, the Connect app for wireless projection using Miracast is not installed by default, but is available as an optional feature.</span></span> <span data-ttu-id="6c180-258">Si vous avez installé (ou mis à jour vers) Windows version 2004 ou une version ultérieure, il est possible que vous voyiez ce qui suit sur l’écran de projet vers ce PC dans les paramètres:</span><span class="sxs-lookup"><span data-stu-id="6c180-258">If you have installed (or updated to) Windows version 2004 or later, you may see the following on the Projecting to this PC screen in settings:</span></span>

![Projetez sur ce PC](images/sh2-project.png) 


1. <span data-ttu-id="6c180-260">Pour installer l’application à partir de la page de paramètres «projection vers ce PC», sélectionnez **fonctionnalités facultatives**  >  **Ajouter une fonctionnalité** , puis installez l’application d' **affichage sans fil** .</span><span class="sxs-lookup"><span data-stu-id="6c180-260">To install the app from the “Projecting to this PC” settings page, select **Optional features** > **Add a feature** and then install the **Wireless Display** app.</span></span>

2. <span data-ttu-id="6c180-261">Sous **certains appareils Windows et Android peuvent projeter sur ce PC lorsque vous prononcez la mention OK**, choisissez:</span><span class="sxs-lookup"><span data-stu-id="6c180-261">Under **Some Windows and Android devices can project to this PC when you say it's OK**, choose:</span></span>

    - <span data-ttu-id="6c180-262">**Disponible partout** si l’appareil n’est pas sur un réseau d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="6c180-262">**Available everywhere** if the device is not on a corporate network.</span></span>
    - <span data-ttu-id="6c180-263">Dans le cas contraire, choisissez **disponible partout sur des réseaux sécurisés**.</span><span class="sxs-lookup"><span data-stu-id="6c180-263">Otherwise, choose **Available everywhere on secure networks**.</span></span>
    
3. <span data-ttu-id="6c180-264">Sous **demander à Project pour ce PC**, choisissez **première fois uniquement**.</span><span class="sxs-lookup"><span data-stu-id="6c180-264">Under **Ask to project to this PC**, choose **First time only**.</span></span>

4. <span data-ttu-id="6c180-265">Sous **exiger le code confidentiel pour le jumelage**, sélectionnez **jamais**.</span><span class="sxs-lookup"><span data-stu-id="6c180-265">Under **Require PIN for pairing**, choose **Never**.</span></span>

5. <span data-ttu-id="6c180-266">Pour lancer l’application et l’épingler à la barre des tâches, recherchez **connexion**.</span><span class="sxs-lookup"><span data-stu-id="6c180-266">To then launch the app and pin it to the taskbar, search for **Connect**.</span></span>

6. <span data-ttu-id="6c180-267">Ouvrez l’application.</span><span class="sxs-lookup"><span data-stu-id="6c180-267">Open the app.</span></span> <span data-ttu-id="6c180-268">Lorsque l’application est ouverte, cliquez avec le bouton droit sur l’icône de l’application connectée dans la barre des tâches, puis sélectionnez **Épingler à la barre des tâches**.</span><span class="sxs-lookup"><span data-stu-id="6c180-268">While the app is open, right-click on the Connect app icon on the taskbar, and select **pin to taskbar**.</span></span>

7. <span data-ttu-id="6c180-269">Fermez ensuite l’application connexion.</span><span class="sxs-lookup"><span data-stu-id="6c180-269">Then close the Connect app.</span></span> <span data-ttu-id="6c180-270">Le **projet sur ce PC** peut ne pas fonctionner tant que l’application n’a pas été exécutée au moins une fois.</span><span class="sxs-lookup"><span data-stu-id="6c180-270">**Project to this PC** might not work unless the app has been run at least once.</span></span>

<span data-ttu-id="6c180-271">Configuration recommandée hors du réseau d’entreprise:</span><span class="sxs-lookup"><span data-stu-id="6c180-271">Recommended configuration when not on the corporate network:</span></span>

![Paramètres à la maison](images/project1.png)

<span data-ttu-id="6c180-273">Configuration recommandée sur le réseau d’entreprise:</span><span class="sxs-lookup"><span data-stu-id="6c180-273">Recommended configuration on the corporate network:</span></span>

![Paramètres au bureau](images/project2.png)

### <span data-ttu-id="6c180-275">Votre Téléphone</span><span class="sxs-lookup"><span data-stu-id="6c180-275">Your Phone</span></span>

<span data-ttu-id="6c180-276">L’application **votre téléphone** est installée par défaut sur Windows 10.</span><span class="sxs-lookup"><span data-stu-id="6c180-276">The **Your Phone** app is installed by default on Windows 10.</span></span> <span data-ttu-id="6c180-277">Si ce n’est pas le cas, vous pouvez également l’installer à partir du Windows Store.</span><span class="sxs-lookup"><span data-stu-id="6c180-277">If it is not present, you can also install it from the Windows Store.</span></span>

<span data-ttu-id="6c180-278">Pour plus d’informations sur la configuration de l’application, reportez-vous à la rubrique Configuration de <a href="https://www.windowscentral.com/how-set-your-phone-windows-10" target="_blank"> votre téléphone sur Windows 10 et synchronisation des données entre votre ordinateur et votre téléphone </a> .</span><span class="sxs-lookup"><span data-stu-id="6c180-278">For information about setting up the app, see <a href="https://www.windowscentral.com/how-set-your-phone-windows-10" target="_blank"> How to set up Your Phone on Windows 10 and sync data between your PC and phone</a>.</span></span> <span data-ttu-id="6c180-279">Consultez également <a href="https://www.windowscentral.com/how-fix-common-problems-your-phone-app-windows-10" target="_blank"> la rubrique Comment résoudre les problèmes courants liés à votre application de téléphone sur Windows 10 </a> .</span><span class="sxs-lookup"><span data-stu-id="6c180-279">Also see <a href="https://www.windowscentral.com/how-fix-common-problems-your-phone-app-windows-10" target="_blank"> How to fix common problems with Your Phone app on Windows 10</a>.</span></span>

###  <span data-ttu-id="6c180-280">Zones fantaisie</span><span class="sxs-lookup"><span data-stu-id="6c180-280">Fancy Zones</span></span>


<span data-ttu-id="6c180-281">Les **zones fantaisie** font partie d’un ensemble d’outils appelé <a href="https://github.com/microsoft/PowerToys/releases" target="_blank"> PowerToys </a> sur GitHub.</span><span class="sxs-lookup"><span data-stu-id="6c180-281">**Fancy Zones** is part of a collection of tools called <a href="https://github.com/microsoft/PowerToys/releases" target="_blank"> PowerToys</a> on GitHub..</span></span> <span data-ttu-id="6c180-282">C’est un excellent moyen d’utiliser l’écran en surface Hub 2 en vous permettant de définir des dispositions fixes sur votre écran («zones»), puis de sélectionner l’application qui sera exécutée dans chaque zone.</span><span class="sxs-lookup"><span data-stu-id="6c180-282">It is a great way to utilize the screen real-estate on a Surface Hub 2 by giving you the ability to define fixed layouts on your display (“zones”), and then select which app will then run in each zone.</span></span> 


<span data-ttu-id="6c180-283">Le [wiki PowerToys](https://github.com/microsoft/PowerToys/wiki) comporte des instructions sur l’utilisation et la personnalisation de chaque outil, y compris [FancyZones](https://github.com/microsoft/PowerToys/wiki/FancyZones-Overview).</span><span class="sxs-lookup"><span data-stu-id="6c180-283">The [PowerToys wiki](https://github.com/microsoft/PowerToys/wiki) has instructions for how to use and customize each tool, including [FancyZones](https://github.com/microsoft/PowerToys/wiki/FancyZones-Overview).</span></span> <span data-ttu-id="6c180-284">À un niveau élevé, après l’installation de PowerToys, vous pouvez sélectionner ou créer une disposition personnalisée, puis maintenir la touche Maj enfoncée et faire glisser ou utiliser les touches du clavier pour déplacer une application en cours d’exécution dans des zones spécifiques.</span><span class="sxs-lookup"><span data-stu-id="6c180-284">At a high level – after installing PowerToys, you can select or create a custom layout, and then hold the shift key down and drag or use keyboard keys to move a running app into specific zones.</span></span> <span data-ttu-id="6c180-285">L’utilisation d’un clavier et d’une souris Bluetooth ou USB peut vous être utile, ou vous pouvez utiliser le clavier tactile et le pavé tactile.</span><span class="sxs-lookup"><span data-stu-id="6c180-285">Using a Bluetooth or USB keyboard and mouse will help with this, or you can use the on-screen touch keyboard and touchpad.</span></span>

**<span data-ttu-id="6c180-286">Conseils pour Power Toys</span><span class="sxs-lookup"><span data-stu-id="6c180-286">Power toys tips</span></span>**
- <span data-ttu-id="6c180-287">Pour recevoir des notifications par courrier électronique concernant les mises à jour de la version PowerToys sur GitHub, cliquez sur le bouton «inscription» en haut de la [page](https://github.com/microsoft/PowerToys/releases).</span><span class="sxs-lookup"><span data-stu-id="6c180-287">To receive email notifications of PowerToys release updates on GitHub, click the “sign-up” button at the top of the [page](https://github.com/microsoft/PowerToys/releases).</span></span>
- <span data-ttu-id="6c180-288">Après l’installation de PowerToys, vous pouvez recevoir des notifications Windows et/ou télécharger et installer les dernières mises à jour en configurant les paramètres de PowerToys **Télécharger les mises à jour automatiquement** sur activé.</span><span class="sxs-lookup"><span data-stu-id="6c180-288">Once PowerToys is installed, you can receive Windows notifications and/or download and install the latest updates by configuring the PowerToys settings **Download updates automatically** to on.</span></span>
- <span data-ttu-id="6c180-289">Pour accéder aux paramètres de PowerToys, sélectionnez l’icône d' **exécution des applications** carats dans la barre des tâches, puis cliquez avec le bouton droit ou appuyez longuement sur l’icône PowerToys jusqu’à ce que le menu apparaisse.</span><span class="sxs-lookup"><span data-stu-id="6c180-289">To get to the PowerToys settings, select the up carat **Running apps** on the taskbar, and then right click or press and hold the PowerToys icon until the menu appears.</span></span> <span data-ttu-id="6c180-290">Sélectionnez «Paramètres».</span><span class="sxs-lookup"><span data-stu-id="6c180-290">Select “Settings”.</span></span>
- <span data-ttu-id="6c180-291">En bas de la page des paramètres de PowerToys, activez la fonction **Télécharger les mises à jour automatiquement** .</span><span class="sxs-lookup"><span data-stu-id="6c180-291">At the bottom of the PowerToys settings page, turn **Download updates automatically** to on.</span></span>
- <span data-ttu-id="6c180-292">Lorsqu’une mise à jour a été publiée, une notification Windows s’affiche pour vous permettre d’installer la mise à jour.</span><span class="sxs-lookup"><span data-stu-id="6c180-292">When an update has been released, a Windows notification will appear giving you the option of when to install the update.</span></span>


### <span data-ttu-id="6c180-293">Navigateur Microsoft Edge chrome</span><span class="sxs-lookup"><span data-stu-id="6c180-293">Edge Chromium browser</span></span>

<span data-ttu-id="6c180-294">Téléchargez et installez le nouveau <a href="https://www.microsoft.com/en-us/edge?form=MY01BL&OCID=MY01BL" target="_blank"> navigateur Microsoft Edge chrome </a> .</span><span class="sxs-lookup"><span data-stu-id="6c180-294">Download and install the new <a href="https://www.microsoft.com/en-us/edge?form=MY01BL&OCID=MY01BL" target="_blank">Edge Chromium browser</a>.</span></span>


### <span data-ttu-id="6c180-295">Outil de diagnostic du matériel surface Hub</span><span class="sxs-lookup"><span data-stu-id="6c180-295">Surface Hub Hardware Diagnostic tool</span></span>

<span data-ttu-id="6c180-296"><a href="https://www.microsoft.com/p/surface-hub-hardware-diagnostic/9nblggh51f2g" target="_blank">Outil de diagnostic du matériel surface Hub </a> disponible gratuitement sur le Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="6c180-296">The <a href="https://www.microsoft.com/p/surface-hub-hardware-diagnostic/9nblggh51f2g" target="_blank"> Surface Hub Hardware Diagnostic tool</a> available for free from the Microsoft Store.</span></span> <span data-ttu-id="6c180-297">L’outil est conçu pour vous aider à veiller à ce que votre surface Hub fonctionne de façon optimale.</span><span class="sxs-lookup"><span data-stu-id="6c180-297">The tool is designed to help you make sure your Surface Hub is performing at its best.</span></span> <span data-ttu-id="6c180-298">Il contient des tests permettant de déterminer si le microprogramme est à jour et s’il est configuré correctement.</span><span class="sxs-lookup"><span data-stu-id="6c180-298">It contains tests to determine if your firmware is up to date and configured correctly.</span></span> <span data-ttu-id="6c180-299">Les tests interactifs vous permettent de vérifier que les fonctionnalités essentielles fonctionnent comme prévu.</span><span class="sxs-lookup"><span data-stu-id="6c180-299">Interactive tests allow you to confirm essential functionality is working as expected.</span></span> <span data-ttu-id="6c180-300">Si des problèmes surviennent, les résultats peuvent être enregistrés et partagés avec l’équipe du Support Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="6c180-300">If problems are encountered, results can be saved and shared with the Surface Hub Support Team.</span></span> <span data-ttu-id="6c180-301">Cliquez sur le lien pour l’installer à partir du Microsoft Store, puis épinglez l’application à votre barre des tâches.</span><span class="sxs-lookup"><span data-stu-id="6c180-301">Click on the link to install it from the Microsoft Store, and then pin the application to your taskbar.</span></span>

## <span data-ttu-id="6c180-302">Paramètres supplémentaires</span><span class="sxs-lookup"><span data-stu-id="6c180-302">Additional settings</span></span>

### <span data-ttu-id="6c180-303">Stylo d’aileron sélectionner pour lancer le tableau blanc</span><span class="sxs-lookup"><span data-stu-id="6c180-303">Pen tail select to launch Whiteboard</span></span>

1. <span data-ttu-id="6c180-304">Recherchez **stylo** et sélectionnez **stylo & paramètres Windows Ink**.</span><span class="sxs-lookup"><span data-stu-id="6c180-304">Search for **Pen** and select **Pen & Windows Ink settings**.</span></span>

2. <span data-ttu-id="6c180-305">Dans la partie inférieure de la page, sous **raccourcis clavier** , définissez l' **option Sélectionner une fois** sur le **tableau blanc collaboratif Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="6c180-305">Near the bottom of the page, under **Pen shortcuts** set **Select once** to **Microsoft Whiteboard**.</span></span> 

### <span data-ttu-id="6c180-306">Gestion de l’alimentation</span><span class="sxs-lookup"><span data-stu-id="6c180-306">Power management</span></span>

<span data-ttu-id="6c180-307">Plusieurs paramètres d’alimentation sont disponibles pour tirer le meilleur parti de Windows 10 professionnel ou Enterprise sur surface Hub 2.</span><span class="sxs-lookup"><span data-stu-id="6c180-307">There are several power settings available to get the best experience using Windows 10 Pro or Enterprise on Surface Hub 2.</span></span> <span data-ttu-id="6c180-308">Cela inclut les délais d’expiration de l’écran et du PC, la façon dont ils interagissent avec le système de détection humaine intégré (Doppler), l’économiseur d’écran et la protection par mot de passe, puis, le cas échéant, les paramètres d’alimentation de la stratégie de groupe pour les utilisateurs de l’ordinateur portable ou du bureau.</span><span class="sxs-lookup"><span data-stu-id="6c180-308">This includes screen and pc timeouts and how they interact with the built-in human presence detection (Doppler), the screen saver and password protection, and then if appropriate how to by-pass group policy power settings intended for laptop / desktop users.</span></span>

<span data-ttu-id="6c180-309">Windows 10 professionnel ou entreprise sur surface Hub 2 vous permet d’accéder à l’écran par le biais de la fonction d’effleurement, de la souris et du clavier, ainsi que de la détection d’occupation humaine intégrée (Doppler).</span><span class="sxs-lookup"><span data-stu-id="6c180-309">Windows 10 Pro or Enterprise on Surface Hub 2 keeps the screen from going to sleep by touch, mouse, and keyboard actions, as well as the built-in human occupancy detection (Doppler).</span></span> <span data-ttu-id="6c180-310">La détection d’occupation humaine est activée par défaut, mais si vous le souhaitez, elle peut être désactivée dans UEFI en faisant basculer l’option d’appareil dans l’outil de Configurateur surface UEFI dans le cadre de la migration initiale, ou en construisant et en appliquant un package de configuration UEFI ultérieur.</span><span class="sxs-lookup"><span data-stu-id="6c180-310">Human occupancy detection is enabled by default, but if desired it can be disabled in UEFI by toggling the device option in the Surface UEFI Configurator tool either as part of the initial migration, or by building and applying a later UEFI configuration package.</span></span> 

**<span data-ttu-id="6c180-311">Gestion de l’alimentation: paramètres de veille de l’écran et du PC</span><span class="sxs-lookup"><span data-stu-id="6c180-311">Power Management: Screen and PC sleep settings</span></span>**

1. <span data-ttu-id="6c180-312">Sélectionnez **Démarrer**les  >  **paramètres**  >  **système**  >  **d’alimentation & Sleep**.</span><span class="sxs-lookup"><span data-stu-id="6c180-312">Select **Start** > **Settings** > **System** > **Power & sleep**.</span></span>

2. <span data-ttu-id="6c180-313">Positionnez le curseur mode d’alimentation sur **meilleures performances**.</span><span class="sxs-lookup"><span data-stu-id="6c180-313">Set the power mode slider to **Best performance**.</span></span>

3. <span data-ttu-id="6c180-314">Configurez les valeurs de l’écran et de la mise en veille de votre choix en tenant compte de la détection de présence Doppler qui met l’appareil en éveil lorsque le mouvement est détecté.</span><span class="sxs-lookup"><span data-stu-id="6c180-314">Configure screen and sleep values to your preference while also accounting for Doppler presence detection that wakes up the device when movement is detected.</span></span> <span data-ttu-id="6c180-315">Par conséquent, il est recommandé de configurer l’écran pour qu’il soit **désactivé au bout de 2 heures** et du PC pour le désactiver **après 4 heures.**</span><span class="sxs-lookup"><span data-stu-id="6c180-315">Accordingly, as a best practice, it's recommended to set Screen to **Turn off after 2 hours** and the PC to **Turn off after 4 hours.**</span></span>

**<span data-ttu-id="6c180-316">Gestion de l’alimentation: économiseur d’écran</span><span class="sxs-lookup"><span data-stu-id="6c180-316">Power Management: Screen saver</span></span>**

1. <span data-ttu-id="6c180-317">Recherchez l' **écran de verrouillage** et ouvrez les paramètres de l' **écran de verrouillage**.</span><span class="sxs-lookup"><span data-stu-id="6c180-317">Search for **Lock Screen** and open **Lock screen settings**.</span></span>

2. <span data-ttu-id="6c180-318">Configurez vos préférences en matière de **paramètres de délai d’écran** et de paramètres d' **écran de veille** .</span><span class="sxs-lookup"><span data-stu-id="6c180-318">Configure **Screen timeout settings** and **Screen saver settings** to your preference.</span></span> <span data-ttu-id="6c180-319">Les valeurs par défaut recommandées sont les suivantes:</span><span class="sxs-lookup"><span data-stu-id="6c180-319">Recommended default values are:</span></span>

   - <span data-ttu-id="6c180-320">Écran de veille (aucun) ou écran de votre choix.</span><span class="sxs-lookup"><span data-stu-id="6c180-320">Screen saver to (None) or a screen saver of your choice.</span></span>
   - <span data-ttu-id="6c180-321">Temps d’attente de 15 minutes.</span><span class="sxs-lookup"><span data-stu-id="6c180-321">Wait time to 15 minutes.</span></span>
   - <span data-ttu-id="6c180-322">En sortie, affichez l’écran de connexion.</span><span class="sxs-lookup"><span data-stu-id="6c180-322">On resume, display logon screen.</span></span>


**<span data-ttu-id="6c180-323">Gestion de l’alimentation: stratégie de groupe</span><span class="sxs-lookup"><span data-stu-id="6c180-323">Power Management: Group Policy</span></span>**

<span data-ttu-id="6c180-324">Avant d’effectuer la procédure suivante, contactez votre service informatique pour obtenir de l’aide afin d’exclure un périphérique surface Hub 2 de la stratégie de gestion de l’alimentation globale.</span><span class="sxs-lookup"><span data-stu-id="6c180-324">Before performing the following procedure, check with your IT department for approval to exclude a Surface Hub 2S device from global power management policy.</span></span> <span data-ttu-id="6c180-325">Certains paramètres de gestion de l’alimentation peuvent désactiver la fonction de détection de présence.</span><span class="sxs-lookup"><span data-stu-id="6c180-325">Some power management settings can disable the presence detection function.</span></span>

1. <span data-ttu-id="6c180-326">Recherchez le **Centre de logiciels** et ouvrez-le.</span><span class="sxs-lookup"><span data-stu-id="6c180-326">Search for **Software Center** and open it.</span></span>

2. <span data-ttu-id="6c180-327">Sélectionnez **options**.</span><span class="sxs-lookup"><span data-stu-id="6c180-327">Select **Options**.</span></span>

3. <span data-ttu-id="6c180-328">Développez la gestion de l' **alimentation**  et sélectionnez **ne pas appliquer les paramètres d’alimentation du service informatique à cet ordinateur**.</span><span class="sxs-lookup"><span data-stu-id="6c180-328">Expand the **Power management**  and select **Do not apply power settings from my IT department to this computer**.</span></span>

   ![Paramètres logiciels](images/soft-cntr.png)

### <span data-ttu-id="6c180-330">Assistant Stockage</span><span class="sxs-lookup"><span data-stu-id="6c180-330">Storage Sense</span></span>

<span data-ttu-id="6c180-331">Surface Hub 2 étant doté d’un appareil compact de 128 Go pour le stockage local, il est nécessaire de tenir compte de l’utilisation des mesures d’enregistrement de stockage en cas d’utilisation normale.</span><span class="sxs-lookup"><span data-stu-id="6c180-331">The Surface Hub 2 has a 128GB SSD for local storage, so it is necessary to consider the use of storage saving measures during normal usage.</span></span>  <span data-ttu-id="6c180-332">Pour configurer le sens de stockage:</span><span class="sxs-lookup"><span data-stu-id="6c180-332">To configure Storage Sense:</span></span>

1.  <span data-ttu-id="6c180-333">Recherchez **paramètres de stockage**dans les **paramètres système**.</span><span class="sxs-lookup"><span data-stu-id="6c180-333">Search for **storage settings**, which is found under **System settings**.</span></span>

2.  <span data-ttu-id="6c180-334">Sous **paramètres**, sélectionnez l’option **activer le stockage** pour ouvrir la page Paramètres de **stockage** .</span><span class="sxs-lookup"><span data-stu-id="6c180-334">Under **Settings**, select **Turn on storage sense** to open the **Storage** settings page.</span></span>

3.  <span data-ttu-id="6c180-335">Activez **le stockage sur activé**.</span><span class="sxs-lookup"><span data-stu-id="6c180-335">Turn Storage Sense to **On**.</span></span>

4.  <span data-ttu-id="6c180-336">Sélectionnez **configurer un sens de stockage ou exécutez-le maintenant** et configurez les paramètres permettant de conserver les fichiers en ligne le plus possible (en raison de l’espace disque limité).</span><span class="sxs-lookup"><span data-stu-id="6c180-336">Select **Configure Storage Sense or run it now** and configure settings to keep files online as much as possible (due to limited drive space).</span></span>

<span data-ttu-id="6c180-337">Paramètres recommandés:</span><span class="sxs-lookup"><span data-stu-id="6c180-337">Recommended settings:</span></span>

- <span data-ttu-id="6c180-338">Utilisez l’outil de stockage = quotidiennement.</span><span class="sxs-lookup"><span data-stu-id="6c180-338">Run Storage Sense = Every Day.</span></span>
- <span data-ttu-id="6c180-339">Supprimez les fichiers temporaires que mes applications n’utilisent pas = tous les 14 jours (au moins).</span><span class="sxs-lookup"><span data-stu-id="6c180-339">Delete temporary files that my apps aren't using = Every 14 days (at least).</span></span>
- <span data-ttu-id="6c180-340">Supprimer les fichiers du dossier téléchargements s’ils y étaient depuis plus de 30 jours.</span><span class="sxs-lookup"><span data-stu-id="6c180-340">Delete files in my Downloads folder if they have been there for over = 30 days.</span></span>
- <span data-ttu-id="6c180-341">OneDrive: le contenu devient en ligne uniquement s’il n’est pas ouvert pendant plus de 30 jours.</span><span class="sxs-lookup"><span data-stu-id="6c180-341">OneDrive: Content will become online-only if not opened for more than = 30 days.</span></span>

### <span data-ttu-id="6c180-342">Mode tablette</span><span class="sxs-lookup"><span data-stu-id="6c180-342">Tablet mode</span></span>

<span data-ttu-id="6c180-343">Activez le mode tablette si vous le souhaitez, pour les besoins en matière d’accessibilité.</span><span class="sxs-lookup"><span data-stu-id="6c180-343">Turn on Tablet mode if desired for accessibility needs.</span></span>


### <span data-ttu-id="6c180-344">Paramètres du son</span><span class="sxs-lookup"><span data-stu-id="6c180-344">Sound settings</span></span>

1. <span data-ttu-id="6c180-345">Recherchez les **paramètres audio** et ouvrez cette page.</span><span class="sxs-lookup"><span data-stu-id="6c180-345">Search for **Sounds settings** and open this page.</span></span>

2. <span data-ttu-id="6c180-346">Sélectionnez **son panneau de configuration** sur la droite, puis sélectionnez l’onglet **sons** .</span><span class="sxs-lookup"><span data-stu-id="6c180-346">Select **Sound Control Panel** on the right and select the **Sounds** tab.</span></span>

3. <span data-ttu-id="6c180-347">Sous **événements** , définissez l’option **connexion** de l’appareil et **Débranchez l’appareil** à **aucun**.</span><span class="sxs-lookup"><span data-stu-id="6c180-347">Under **Program Events** set **Device Connect** and **Device Disconnect** to **None**.</span></span>

### <span data-ttu-id="6c180-348">Notifications de silence</span><span class="sxs-lookup"><span data-stu-id="6c180-348">Silence notifications</span></span>

1. <span data-ttu-id="6c180-349">Recherchez **assistance au focus** et ouvrez cette page.</span><span class="sxs-lookup"><span data-stu-id="6c180-349">Search for **Focus assist** and open this page.</span></span>

2. <span data-ttu-id="6c180-350">Sélectionner **alarmes uniquement**.</span><span class="sxs-lookup"><span data-stu-id="6c180-350">Select **Alarms Only**.</span></span> <span data-ttu-id="6c180-351">Cela évite les menus volants de notifications constantes.</span><span class="sxs-lookup"><span data-stu-id="6c180-351">This will avoid constant notification flyouts.</span></span>

### <span data-ttu-id="6c180-352">Nettoyage de disque</span><span class="sxs-lookup"><span data-stu-id="6c180-352">Disk Cleanup</span></span>

1. <span data-ttu-id="6c180-353">Recherchez **Disk Cleanup** et ouvrez cette application.</span><span class="sxs-lookup"><span data-stu-id="6c180-353">Search for **Disk Cleanup** and open this app.</span></span>

2. <span data-ttu-id="6c180-354">Sous **fichiers à supprimer**, sélectionnez les fichiers que vous souhaitez supprimer.</span><span class="sxs-lookup"><span data-stu-id="6c180-354">Under **Files to delete**, select the files you wish to delete.</span></span> 

3. <span data-ttu-id="6c180-355">Sélectionnez également **nettoyer les fichiers système**.</span><span class="sxs-lookup"><span data-stu-id="6c180-355">Also select **Clean up system files**.</span></span>

## <span data-ttu-id="6c180-356">Achever et vérifier</span><span class="sxs-lookup"><span data-stu-id="6c180-356">Complete and verify</span></span>

1. <span data-ttu-id="6c180-357">Recherchez et installez toutes les mises à jour Windows.</span><span class="sxs-lookup"><span data-stu-id="6c180-357">Scan for and install all Windows Updates.</span></span>

2. <span data-ttu-id="6c180-358">Mettez à jour la stratégie de groupe.</span><span class="sxs-lookup"><span data-stu-id="6c180-358">Update Group Policy.</span></span>

   1. <span data-ttu-id="6c180-359">À l’invite de commandes avec élévation de privilèges, entrez **gpupdate/force/Boot/Wait: 0**.</span><span class="sxs-lookup"><span data-stu-id="6c180-359">At an elevated command prompt, enter **gpupdate /force /boot /wait:0**.</span></span>
   
3. <span data-ttu-id="6c180-360">Redémarrez l’appareil.</span><span class="sxs-lookup"><span data-stu-id="6c180-360">Restart the device.</span></span>

4. <span data-ttu-id="6c180-361">Vérifiez les applications de la barre des tâches.</span><span class="sxs-lookup"><span data-stu-id="6c180-361">Verify taskbar apps.</span></span>

   - <span data-ttu-id="6c180-362">Connecter l’application</span><span class="sxs-lookup"><span data-stu-id="6c180-362">Connect App</span></span>
   - <span data-ttu-id="6c180-363">Icône de verrouillage</span><span class="sxs-lookup"><span data-stu-id="6c180-363">Lock Icon</span></span>
   - <span data-ttu-id="6c180-364">Capture d'écran et Croquis</span><span class="sxs-lookup"><span data-stu-id="6c180-364">Snip & Sketch</span></span>
   - <span data-ttu-id="6c180-365">Teams (le cas échéant)</span><span class="sxs-lookup"><span data-stu-id="6c180-365">Teams (if applicable)</span></span>
   - <span data-ttu-id="6c180-366">Applications Office (le cas échéant)</span><span class="sxs-lookup"><span data-stu-id="6c180-366">Office Apps (if applicable)</span></span>
   - <span data-ttu-id="6c180-367">Application surface</span><span class="sxs-lookup"><span data-stu-id="6c180-367">Surface App</span></span>
   - <span data-ttu-id="6c180-368">Tableau blanc</span><span class="sxs-lookup"><span data-stu-id="6c180-368">Whiteboard</span></span>
    
5. <span data-ttu-id="6c180-369">Vérifier la détection de présence.</span><span class="sxs-lookup"><span data-stu-id="6c180-369">Verify presence detection.</span></span>

   - <span data-ttu-id="6c180-370">La détection de présence sera une icône verte dans la barre d’état système.</span><span class="sxs-lookup"><span data-stu-id="6c180-370">Presence detection will be a green icon in the system tray.</span></span>
    
6. <span data-ttu-id="6c180-371">Vérifiez que l’option de projection vers ce PC est activée avec l’application connexion.</span><span class="sxs-lookup"><span data-stu-id="6c180-371">Verify projecting to this PC is enabled with the Connect App.</span></span> <span data-ttu-id="6c180-372">Après la configuration  **de Project avec ce paramètre de PC** , exécutez l’application de connexion au moins une fois.</span><span class="sxs-lookup"><span data-stu-id="6c180-372">After configuring  **Project to this PC** settings, run the Connect App at least once.</span></span> <span data-ttu-id="6c180-373">(Par la suite, l’application connexion n’a pas besoin d’être en cours d’exécution pour projeter sur surface Hub.)</span><span class="sxs-lookup"><span data-stu-id="6c180-373">(Subsequently, the Connect App does not need to be running in order to project to Surface Hub.)</span></span>

7. <span data-ttu-id="6c180-374">Vérifiez les paramètres d’alimentation et de veille.</span><span class="sxs-lookup"><span data-stu-id="6c180-374">Verify power and sleep settings.</span></span>

    - <span data-ttu-id="6c180-375">Écran de veille: 15 minutes, définie sur (aucune), mystification ou Blank; Vérifiez que la case à cocher demander un mot de passe est activée.</span><span class="sxs-lookup"><span data-stu-id="6c180-375">Screen Saver: 15 minutes, set to (none), Mystify or Blank; ensure the check box for requiring password is selected.</span></span>
    - <span data-ttu-id="6c180-376">Écran: **désactiver après 2 heures**.</span><span class="sxs-lookup"><span data-stu-id="6c180-376">Screen: **Turn off after 2 hours**.</span></span>
    - <span data-ttu-id="6c180-377">PC:  **désactivez après 4 heures**.</span><span class="sxs-lookup"><span data-stu-id="6c180-377">PC:  **Turn off after 4 hours**.</span></span>
    
8. <span data-ttu-id="6c180-378">Vérifiez que Windows Hello fonctionne.</span><span class="sxs-lookup"><span data-stu-id="6c180-378">Verify Windows Hello is working.</span></span>

9. <span data-ttu-id="6c180-379">Vérifier la synchronisation vos paramètres sont désactivés.</span><span class="sxs-lookup"><span data-stu-id="6c180-379">Verify sync your settings is disabled.</span></span>

10. <span data-ttu-id="6c180-380">Vérifiez les applications de démarrage.</span><span class="sxs-lookup"><span data-stu-id="6c180-380">Verify startup apps.</span></span>

> [!TIP]
> <span data-ttu-id="6c180-381">Après l’installation et la configuration de Windows 10, les applications de surface Hub 2 peuvent être gérées comme n’importe quel autre appareil Windows 10.</span><span class="sxs-lookup"><span data-stu-id="6c180-381">After installing and configuring Windows 10, the Surface Hub 2S can be managed just like any other Windows 10 device.</span></span>

## <span data-ttu-id="6c180-382">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="6c180-382">Related topics</span></span>

<a href="surface-hub-2s-migrate-os.md" target="_blank"> <span data-ttu-id="6c180-383">Migrer vers Windows 10 Professionnel ou Entreprise sur Surface Hub 2</span><span class="sxs-lookup"><span data-stu-id="6c180-383">Migrate to Windows 10 Pro or Enterprise on Surface Hub 2</span></span></a>
