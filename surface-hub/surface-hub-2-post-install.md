---
title: Configurer Windows 10 professionnel ou entreprise sur surface Hub 2
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
ms.openlocfilehash: f6ea6324799981e57c36a11b33cf2e22ea80039e
ms.sourcegitcommit: d24759da42dfe0b913fd9ebf716407a673c2b818
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/09/2020
ms.locfileid: "11004476"
---
# <span data-ttu-id="b9dc4-104">Configurer Windows 10 professionnel ou entreprise sur surface Hub 2</span><span class="sxs-lookup"><span data-stu-id="b9dc4-104">Configure Windows 10 Pro or Enterprise on Surface Hub 2</span></span>

**<span data-ttu-id="b9dc4-105">S’applique à: surface Hub 2</span><span class="sxs-lookup"><span data-stu-id="b9dc4-105">Applies to: Surface Hub 2S</span></span>** 

<span data-ttu-id="b9dc4-106">Après avoir terminé le processus d’installation de la migration vers Windows 10 professionnel ou entreprise, vous pouvez effectuer les étapes suivantes pour configurer les applications et les paramètres sur votre surface Hub 2.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-106">After you have completed the installation process of migrating to Windows 10 Pro or Enterprise, you can perform the following steps to configure apps and settings on your Surface Hub 2.</span></span> <span data-ttu-id="b9dc4-107">Ces étapes sont recommandées pour garantir la meilleure utilisation de cette fonction d’affichage du stylo et de l’écran grand écran.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-107">These steps are recommended to ensure the best experience when using this personalized large screen touch and pen computer.</span></span>

<span data-ttu-id="b9dc4-108">Lors de cette procédure, il peut s’avérer utile d’utiliser un clavier et une souris sans fil.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-108">When performing these steps, you might find it useful to use a wired or wireless keyboard and mouse.</span></span>

## <span data-ttu-id="b9dc4-109">Configurer les paramètres système</span><span class="sxs-lookup"><span data-stu-id="b9dc4-109">Configure system settings</span></span>

1. <span data-ttu-id="b9dc4-110">Connectez-vous à l’aide d’un compte disposant de privilèges d’administrateur local sur l’appareil.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-110">Sign in with an account that has local administrator privileges on the device.</span></span>  
    - <span data-ttu-id="b9dc4-111">Sur les appareils disposant d’Azure AD, l’utilisateur qui exécute la jointure Azure AD est automatiquement ajouté au groupe d’administrateurs local.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-111">On Azure AD joined devices, the user that performs the Azure AD join is automatically added to the local administrator group.</span></span> <span data-ttu-id="b9dc4-112">Les administrateurs généraux d’Azure AD et d’Azure AD sont [également administrateurs locaux](https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin).</span><span class="sxs-lookup"><span data-stu-id="b9dc4-112">Azure AD global administrators and Azure AD devices administrators are [also local administrators](https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin).</span></span> 
    - <span data-ttu-id="b9dc4-113">Vous pouvez taper **administrateurs .net localgroup** à une invite de commandes pour répertorier les comptes disposant de droits d’administrateur local.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-113">You can type **net localgroup administrators** at a command prompt to list the accounts that have local administrator rights.</span></span>
2. <span data-ttu-id="b9dc4-114">Renommez l’appareil en utilisant un nom convivial, par exemple: **nom_utilisateur-SHub-Desktop**.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-114">Rename the device using a friendly name, for example: **username-SHub-Desktop**.</span></span>
3. <span data-ttu-id="b9dc4-115">Sélectionnez **Démarrer**  >  les**paramètres**des  >  **comptes**pour  >  **synchroniser vos paramètres** et désactiver les **paramètres de synchronisation** .</span><span class="sxs-lookup"><span data-stu-id="b9dc4-115">Select **Start** > **Settings** > **Accounts** > **Sync your settings** and turn **Sync settings** off.</span></span> 
    - <span data-ttu-id="b9dc4-116">Les paramètres utilisés ici sont destinés à permettre une meilleure utilisation de l’affichage des fonctions visuelles de grande taille et, par conséquent, vous ne souhaitez pas synchroniser d’autres appareils.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-116">The settings used here are intended to enable the best large-screen touch experience, and therefore you may not want to sync other devices.</span></span>
4. <span data-ttu-id="b9dc4-117">Redémarrez l'appareil.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-117">Reboot the device.</span></span>

## <span data-ttu-id="b9dc4-118">Activez le clavier tactile et le pavé tactile.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-118">Enable the touch keyboard and touchpad</span></span>

1. <span data-ttu-id="b9dc4-119">Appuyez de façon prolongée ou cliquez avec le bouton droit sur la barre des tâches, puis sélectionnez **afficher le bouton du clavier tactile** et **afficher le bouton du pavé**tactile.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-119">Tap and hold or right-click the taskbar and then select **Show touch keyboard button** and **Show touchpad button**.</span></span> 
    - <span data-ttu-id="b9dc4-120">Le clavier tactile est utile pour la saisie directe de l’utilisateur, et le pavé tactile virtuel permet d’effectuer des sélections précises, de pointage sur les info-bulles ou d’appuyer longuement sur un clic avec le bouton droit.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-120">The touch keyboard is helpful for direct user input, and the virtual touchpad helps with precise selections, hovering screen tips, or as an alternative to tap and hold for right-click.</span></span> 
    - <span data-ttu-id="b9dc4-121">Consultez l’exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-121">See the following example.</span></span>

     ![Paramètres d’interaction](images/touch.png)

2. <span data-ttu-id="b9dc4-123">Configurez le clavier visuel sur azerty et flottez.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-123">Configure the touch keyboard to QWERTY and floating.</span></span>
    1. <span data-ttu-id="b9dc4-124">Cliquez sur l’icône de clavier dans la barre des tâches pour afficher le clavier visuel.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-124">Select the keyboard icon on the taskbar to show the touch keyboard.</span></span>
    2. <span data-ttu-id="b9dc4-125">Sur le clavier visuel, sélectionnez l’icône de clavier dans le coin supérieur gauche pour ouvrir les paramètres du clavier.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-125">On the touch keyboard, select the keyboard icon in the upper left corner to open keyboard settings.</span></span>
    3. <span data-ttu-id="b9dc4-126">Activez la case à cocher en regard de dernier type de clavier dans la ligne du haut pour activer AZERTY, et la dernière option pour activer le mode flottant, ce qui est très utile sur ce grand écran.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-126">Select the next to last keyboard type on the top row to enable QWERTY, and the last option on the second row to enable floating, which is very helpful on this large screen.</span></span> <span data-ttu-id="b9dc4-127">Consultez les exemples suivants.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-127">See the following examples.</span></span>

     ![Paramètres du clavier](images/kbd.png)

3. <span data-ttu-id="b9dc4-129">Configurez les paramètres de clavier logiciels.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-129">Configure the soft keyboard settings.</span></span>
    1. <span data-ttu-id="b9dc4-130">Recherchez et ouvrez les **paramètres de saisie**</span><span class="sxs-lookup"><span data-stu-id="b9dc4-130">Search for and open **Typing settings**</span></span> 
    2. <span data-ttu-id="b9dc4-131">Activez toutes les options sous orthographe, saisie et clavier vocal.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-131">Enable all the options under Spelling, Typing, and Touch keyboard.</span></span>


<span data-ttu-id="b9dc4-132">L’exemple suivant illustre pavé tactile, qui est utile pour naviguer et sélectionner des options.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-132">The following example shows the trackpad, which is useful to navigate and select options.</span></span> <span data-ttu-id="b9dc4-133">Le clavier à l’écran est utilisé pour effectuer une recherche sur le Microsoft Store:</span><span class="sxs-lookup"><span data-stu-id="b9dc4-133">The onscreen keyboard is being used to search the Microsoft Store:</span></span>

![Utiliser le pavé tactile](images/store.png)

## <span data-ttu-id="b9dc4-135">Configurer le clavier et la souris Bluetooth (facultatif)</span><span class="sxs-lookup"><span data-stu-id="b9dc4-135">Configure bluetooth keyboard and mouse (optional)</span></span>

<span data-ttu-id="b9dc4-136">Connectez un clavier et une souris si vous utilisez le périphérique en tant qu’appareil Windows principal, ou si vous utilisez souvent cette fonctionnalité pour la saisie ou la précision du fonctionnement.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-136">Connect a keyboard and mouse if you are using the device as your primary Windows device, or you use it often for typing or precision work.</span></span>

<span data-ttu-id="b9dc4-137">Si votre périphérique surface Hub est proche d’un PC, vous pouvez utiliser [la souris sans bordure](https://aka.ms/mm) pour vous déplacer en douceur entre le centre de surface et le PC.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-137">If your Surface Hub device is near to a PC, you can use [Mouse without Borders](https://aka.ms/mm) to move seamlessly between the Surface Hub and the PC.</span></span> <span data-ttu-id="b9dc4-138">Pour plus d’informations, reportez-vous [à la rubrique téléchargement de Microsoft à partir du garage: souris sans bordure](https://blogs.microsoft.com/ai/microsoft-download-from-the-garage-mouse-without-borders/).</span><span class="sxs-lookup"><span data-stu-id="b9dc4-138">For more information, see [Microsoft download from The Garage: Mouse without Borders](https://blogs.microsoft.com/ai/microsoft-download-from-the-garage-mouse-without-borders/).</span></span>

## <span data-ttu-id="b9dc4-139">OneDriveEntreprise</span><span class="sxs-lookup"><span data-stu-id="b9dc4-139">OneDrive for Business</span></span>

<span data-ttu-id="b9dc4-140">Utilisez [OneDrive entreprise](https://docs.microsoft.com/onedrive/onedrive) pour partager facilement des outils, des journaux et d’autres fichiers entre tous vos périphériques de travail.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-140">Use [OneDrive for Business](https://docs.microsoft.com/onedrive/onedrive) to easily share tools, logs, and other files between all your work devices.</span></span>

- <span data-ttu-id="b9dc4-141">OneDrive vous permet de partager vos fichiers de travail entre votre ordinateur portable, votre bureau surface Hub et vos appareils mobiles gérés par Intune.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-141">OneDrive enables you to share your work files between your laptops, Surface Hub Desktop, and your Intune-managed mobile devices.</span></span> <span data-ttu-id="b9dc4-142">Les fichiers peuvent être modifiés sur n’importe quel appareil, et tous les appareils connectés réseau sont mis à jour avec les modifications.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-142">Files can be edited on any device, and all network connected devices will be updated with the changes.</span></span>
- <span data-ttu-id="b9dc4-143">Si vous considérez la taille de la fonction SSD de surface Hub (128 Go), si vous configurez OneDrive sur votre appareil de bureau surface Hub, assurez-vous que la configuration par défaut est de conserver les fichiers en ligne et de télécharger des fichiers lorsque vous les utilisez.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-143">Considering the size of the Surface Hub SSD (128GB), if you configure OneDrive on your Surface Hub Desktop device, make sure the default configuration is to keep the files online and download files as you use them.</span></span>

<span data-ttu-id="b9dc4-144">Pour configurer OneDrive pour télécharger les fichiers uniquement lorsque cela est nécessaire, définissez le paramètre **fichiers à la demande** pour **économiser de l’espace et télécharger les fichiers lorsque vous les utilisez**.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-144">To configure OneDrive to download files only when needed, set the **Files On-Demand** setting to **Save space and download files as you use them**.</span></span> <span data-ttu-id="b9dc4-145">Pour plus d’informations, reportez-vous à [la rubrique interroger et définir des fichiers à la demande dans Windows](https://docs.microsoft.com/onedrive/files-on-demand-windows).</span><span class="sxs-lookup"><span data-stu-id="b9dc4-145">For more information, see [Query and set Files On-Demand states in Windows](https://docs.microsoft.com/onedrive/files-on-demand-windows).</span></span>

![Paramètres de OneDrive](images/onedrive.png)

> [!NOTE]
> <span data-ttu-id="b9dc4-147">Vous pouvez également répéter ces étapes pour configurer votre espace OneDrive personnel, mais n’êtes pas sûr de ménager de l’espace disque et de télécharger uniquement les fichiers dont vous avez besoin.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-147">You can also repeat these steps to configure a personal OneDrive but be sure to conserve drive space and only download files as you need them.</span></span>

## <span data-ttu-id="b9dc4-148">SharePoint et Teams</span><span class="sxs-lookup"><span data-stu-id="b9dc4-148">SharePoint and Teams</span></span>

<span data-ttu-id="b9dc4-149">Les fichiers de canal SharePoint et teams peuvent également être synchronisés localement sur vos appareils de bureau, tels que les ordinateurs portables et les hubs de surface, à l’aide du moteur de synchronisation OneDrive.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-149">SharePoint and Teams Channel files can also sync locally to your desktop devices, such as laptops and Surface Hubs, using the OneDrive sync engine.</span></span>

<span data-ttu-id="b9dc4-150">Pour synchroniser des fichiers d’entreprise internes sur votre disque local à l’aide de l’application de synchronisation OneDrive:</span><span class="sxs-lookup"><span data-stu-id="b9dc4-150">To sync internal corporate files to your local drive with the OneDrive sync app:</span></span>

1. <span data-ttu-id="b9dc4-151">Accédez à un site SharePoint et naviguez jusqu’au répertoire de documents de niveau supérieur correspondant aux fichiers que vous souhaitez afficher ou modifier à partir de votre appareil local.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-151">Go to a SharePoint site and navigate to the top-level document directory for files that you are interested in viewing or editing from your local device.</span></span>
2. <span data-ttu-id="b9dc4-152">Cliquez sur le bouton **synchroniser** situé en haut du ruban SharePoint.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-152">Select on the **Sync** button on the top of the SharePoint ribbon.</span></span>
3. <span data-ttu-id="b9dc4-153">Sélectionner sur **ouvrir** dans le menu contextuel **ce site tente d’ouvrir Microsoft OneDrive**.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-153">Select on **Open** on the popup **This site is trying to open Microsoft OneDrive**.</span></span>
4. <span data-ttu-id="b9dc4-154">Vérifiez que les fichiers SharePoint sont synchronisés avec votre lecteur local en sélectionnant l’icône OneDrive située en bas à droite de la barre des tâches.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-154">Verify that the SharePoint files are synchronizing to your local drive by selecting on the OneDrive icon at the bottom right of the taskbar.</span></span>
5. <span data-ttu-id="b9dc4-155">Vérifiez que la configuration est définie pour conserver les fichiers en ligne et télécharger les fichiers uniquement lors de leur utilisation:</span><span class="sxs-lookup"><span data-stu-id="b9dc4-155">Verify the configuration is set to keep the files online and download the files only as you use them:</span></span>
    1. <span data-ttu-id="b9dc4-156">Ouvrez l’Explorateur de fichiers.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-156">Open file explorer.</span></span>
    2. <span data-ttu-id="b9dc4-157">Naviguez jusqu’à droite et sélectionnez dans la section \*\*Microsoft \ \<SharePoint Document Folder Name\> \*\*.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-157">Navigate to and right select on the **Microsoft \ \<SharePoint Document Folder Name\>**.</span></span>
    3. <span data-ttu-id="b9dc4-158">Sélectionnez **libérer**de l’espace.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-158">Select **Free up space**.</span></span>
    4. <span data-ttu-id="b9dc4-159">La colonne État affiche l’état des fichiers et des dossiers.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-159">The Status column will display the status of files and folders.</span></span> <span data-ttu-id="b9dc4-160">Pour plus d’informations, voir [synchroniser des fichiers SharePoint avec le client de synchronisation OneDrive](https://support.microsoft.com/office/sync-sharepoint-files-with-the-onedrive-sync-client-groove-exe-59b1de2b-519e-4d3a-8f45-51647cf291cd).</span><span class="sxs-lookup"><span data-stu-id="b9dc4-160">For more information, see [Sync SharePoint files with the OneDrive sync client](https://support.microsoft.com/office/sync-sharepoint-files-with-the-onedrive-sync-client-groove-exe-59b1de2b-519e-4d3a-8f45-51647cf291cd).</span></span>
6. <span data-ttu-id="b9dc4-161">Les fichiers de canal teams sont stockés sur des sites SharePoint, avec toutes les mêmes fonctionnalités de documents SharePoint, y compris l’historique des versions et la synchronisation avec les appareils de bureau locaux.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-161">Teams Channel files are stored in SharePoint sites, with all of the same SharePoint document functionality, including version history and synchronizing to your local desktop devices.</span></span> <span data-ttu-id="b9dc4-162">Pour synchroniser des fichiers de canal d’équipe:</span><span class="sxs-lookup"><span data-stu-id="b9dc4-162">To sync Teams Channel files:</span></span>
    1. <span data-ttu-id="b9dc4-163">Accédez au canal d’intérêt de l’équipe et sélectionnez l’onglet **fichiers** en haut.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-163">Navigate to the Teams Channel of interest and select on the **Files** tab at the top.</span></span> <span data-ttu-id="b9dc4-164">Sélectionnez **synchroniser**. Les fichiers commenceront à se synchroniser et sont visibles dans l’Explorateur de fichiers sur le \*\*Bureau \ Microsoft \ \<name of the Teams Channel\> \*\*.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-164">Then select **Sync**. The files will start synchronizing and will be visible in File Explorer at **Desktop \ Microsoft \ \<name of the Teams Channel\>**.</span></span>
    2. <span data-ttu-id="b9dc4-165">Utilisez la même procédure que celle que vous avez utilisée pour synchroniser des sites SharePoint afin de conserver les fichiers dans le Cloud et de les télécharger uniquement lorsque vous les utilisez, appuyez longuement ou cliquez avec le bouton droit dans l’Explorateur de fichiers sur le nom du canal Teams, puis sélectionnez libérer de l' **espace**.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-165">Use the same procedure that you used for synchronizing SharePoint sites to keep the files in the cloud and only download them when you use them, by tap and hold or right-click in File Explorer on the Teams Channel name, and then selecting **Free up space**.</span></span>

## <span data-ttu-id="b9dc4-166">Couplez le stylet surface Hub</span><span class="sxs-lookup"><span data-stu-id="b9dc4-166">Pair the Surface Hub pen</span></span>

<span data-ttu-id="b9dc4-167">Pour jumeler l’appareil de stylet:</span><span class="sxs-lookup"><span data-stu-id="b9dc4-167">To pair the pen device:</span></span>

1. <span data-ttu-id="b9dc4-168">Sélectionnez Paramètres de **démarrage**de l'  >  **Settings**  >  **appareil**.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-168">Select **Start** > **Settings** > **Devices**.</span></span>
2. <span data-ttu-id="b9dc4-169">Sélectionnez **Ajouter un appareil Bluetooth ou un autre appareil**.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-169">Select **Add Bluetooth or other device**.</span></span>
3. <span data-ttu-id="b9dc4-170">Sélectionnez **Bluetooth**.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-170">Choose **Bluetooth**.</span></span>
4. <span data-ttu-id="b9dc4-171">Supprimez le bouton de queue du stylo et secouez la connexion à la batterie.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-171">Remove the pen tail button and shake to disconnect the battery connection.</span></span>
5. <span data-ttu-id="b9dc4-172">Placez le capuchon en retour, puis appuyez de façon prolongée sur le capuchon jusqu’à ce que le voyant du jumelage clignote.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-172">Put the cap back on and press and hold the cap until the pairing LED flashes.</span></span>
6. <span data-ttu-id="b9dc4-173">Dans les paramètres Bluetooth surface Hub, sélectionnez **surface Hub 2 PEN**.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-173">On the Surface Hub Bluetooth settings, choose **Surface Hub 2 Pen**.</span></span>
7. <span data-ttu-id="b9dc4-174">Terminez l’opération de jumelage.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-174">Complete the pairing operation.</span></span> 
8. <span data-ttu-id="b9dc4-175">Si le jumelage ne fonctionne pas, essayez à nouveau de jumeler le stylet.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-175">If the pairing is not successful, attempt to pair the pen again.</span></span> <span data-ttu-id="b9dc4-176">Le cas échéant, redémarrez l’appareil, puis réessayez.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-176">If necessary, reboot the device and then try again.</span></span>

## <span data-ttu-id="b9dc4-177">Configuration de la caméra</span><span class="sxs-lookup"><span data-stu-id="b9dc4-177">Camera configuration</span></span>

<span data-ttu-id="b9dc4-178">Vous pouvez monter la caméra sur le dessus ou sur l’un ou l’autre extrémité de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-178">You can mount the camera on the top or on either side of the device.</span></span> <span data-ttu-id="b9dc4-179">Montez l’appareil photo en position pour optimiser l’angle de la caméra si vous utilisez le concentrateur avec un socle de bureau plutôt qu’un panier, ou que vous êtes en proximité du Hub.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-179">Mount the camera in a position to optimize the camera angle if you are using the Hub with a desktop stand instead of a cart, or are in close proximity to the Hub.</span></span> <span data-ttu-id="b9dc4-180">Comme la caméra ne pivote pas automatiquement, vous devez disposer d’une touche hexadécimale 2mm pour faire pivoter manuellement la caméra.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-180">The camera does not auto-rotate, so you need to have a 2mm hex key to manually rotate the camera.</span></span> 

<span data-ttu-id="b9dc4-181">Pour plus d’informations sur la façon de monter la caméra et de la faire pivoter manuellement, voir orientation de l’objectif de la caméra [surface Hub](https://support.microsoft.com/help/4509729/surface-hub-2s-camera-lens-orientation).</span><span class="sxs-lookup"><span data-stu-id="b9dc4-181">For more information on how to side-mount the camera and rotate the camera manually, see [Surface Hub 2S camera lens orientation](https://support.microsoft.com/help/4509729/surface-hub-2s-camera-lens-orientation).</span></span>

## <span data-ttu-id="b9dc4-182">Configuration de Windows Hello</span><span class="sxs-lookup"><span data-stu-id="b9dc4-182">Windows Hello configuration</span></span>

<span data-ttu-id="b9dc4-183">Surface Hub 2-xxxxx xxx XXXXXXX XXXXXXX xxxx xxx xxxxxxx xxx XXXXXXX XXXXXXX XXXXXXX XXXXXXX XXXXXXX XXXXXXX XXXXXXX XXXXXXX xxxx.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-183">Surface Hub 2S running Windows 10 Enterprise allows the full suite of Win32 desktop applications as well as biometric Windows Hello options.</span></span> <span data-ttu-id="b9dc4-184">Les accessoires du lecteur d’empreintes digitales de surface Hub 2 peuvent être branchés dans n’importe quel port USB-C de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-184">The Surface Hub 2 Fingerprint Reader accessory can be plugged into any USB-C port on the device.</span></span> 

> <i><span data-ttu-id="b9dc4-185">Le lecteur d’empreintes digitales surface Hub 2 sera bientôt disponible à l’achat.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-185">The Surface Hub 2 Fingerprint Reader will be available for purchase soon.</span></span> <span data-ttu-id="b9dc4-186">Consultez de nouveau cette page pour en savoir plus sur l’achat.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-186">Please check back on this page for more information including how to purchase.</span></span></i>

<span data-ttu-id="b9dc4-187">Après avoir inséré le lecteur d’empreintes digitales **, sélectionnez**  >  **paramètres**  >  **Accounts**  >  **de connexion comptes options de connexion dans**  >  votre**empreinte digitale Windows Hello** pour inscrire votre empreinte digitale.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-187">After inserting the fingerprint reader, select **Start** > **Settings** > **Accounts** > **Sign-in options** > **Windows Hello Fingerprint** to enroll your fingerprint.</span></span>

<span data-ttu-id="b9dc4-188">Utilisez un appareil certifié Windows Hello pour la reconnaissance faciale.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-188">Use a Windows Hello certified device for face recognition.</span></span> <span data-ttu-id="b9dc4-189">La caméra surface Hub 2 ne prend pas en charge la reconnaissance faciale Windows Hello.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-189">The Surface Hub 2S camera does not support Windows Hello face recognition.</span></span>

## <span data-ttu-id="b9dc4-190">Activer un raccourci de l’écran de verrouillage dans la barre des tâches</span><span class="sxs-lookup"><span data-stu-id="b9dc4-190">Enable a Lock Screen shortcut icon on the taskbar</span></span>

<span data-ttu-id="b9dc4-191">Pour ajouter une icône à la barre des tâches qui permet le verrouillage de l’écran à une seule touche, comme le raccourci clavier Windows-L:</span><span class="sxs-lookup"><span data-stu-id="b9dc4-191">To add an icon to the taskbar that enables one-touch screen lock similar to the Windows-L keyboard shortcut:</span></span> 

1.  <span data-ttu-id="b9dc4-192">Appuyez de façon prolongée ou cliquez avec le bouton droit sur le bureau, sélectionnez **nouveau**  >  **raccourci**  >  **Parcourir**le  >  **Bureau**  >  **OK**  >  **suivant**.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-192">Tap and hold or right-click on the desktop, select **New** > **Shortcut** > **Browse** > **Desktop** > **OK** > **Next**.</span></span>

1.  <span data-ttu-id="b9dc4-193">Indiquez un nom pour le raccourci tel que **verrouiller mon PC**, puis cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-193">Provide a name for the shortcut such as **Lock my PC**, and then select **Finish**.</span></span>

1.  <span data-ttu-id="b9dc4-194">Cliquez avec le bouton droit ou appuyez longuement sur le raccourci qui vient d’être créé sur le bureau, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-194">Right-click or tap and hold the newly created shortcut on the desktop, and select **Properties**.</span></span> <span data-ttu-id="b9dc4-195">Dans l’onglet **raccourci** , entrez les informations suivantes dans le champ **cible** : **Rundll32.exe User32.dll LockWorkStation**</span><span class="sxs-lookup"><span data-stu-id="b9dc4-195">On the **Shortcut** tab, enter the following in the **Target** field: **Rundll32.exe User32.dll,LockWorkStation**</span></span>

1.  <span data-ttu-id="b9dc4-196">Cliquez sur le bouton **modifier l’icône** et recherchez **C:\Windows\System32\imageres.dll** et sélectionnez une icône à utiliser.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-196">Select the **Change Icon** button and browse to **C:\Windows\System32\imageres.dll** and select an icon to use.</span></span> 

    <span data-ttu-id="b9dc4-197">Consultez l’exemple suivant:</span><span class="sxs-lookup"><span data-stu-id="b9dc4-197">See the following example:</span></span>

    ![Choisir une icône](images/lock.png)
    
1.  <span data-ttu-id="b9dc4-199">Cliquez sur **OK** pour enregistrer le raccourci.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-199">Select **OK** to save the shortcut.</span></span>

1.  <span data-ttu-id="b9dc4-200">Cliquez avec le bouton droit ou appuyez longuement sur le raccourci et sélectionnez **Épingler à la barre des tâches**.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-200">Right-click or tap and hold the shortcut and select **Pin to taskbar**.</span></span>

## <span data-ttu-id="b9dc4-201">Applications</span><span class="sxs-lookup"><span data-stu-id="b9dc4-201">Applications</span></span>

### <span data-ttu-id="b9dc4-202">Mettre à jour les applications installées</span><span class="sxs-lookup"><span data-stu-id="b9dc4-202">Update installed apps</span></span>

<span data-ttu-id="b9dc4-203">Pour mettre à jour toutes les applications du Windows Store installées:</span><span class="sxs-lookup"><span data-stu-id="b9dc4-203">To update all installed Store apps:</span></span>

1. <span data-ttu-id="b9dc4-204">Ouvrez l’application Microsoft Store et sélectionnez les points de suspension **voir plus** dans le coin supérieur droit.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-204">Open Microsoft Store app and select the **See more** ellipsis in the top-right corner.</span></span>
2. <span data-ttu-id="b9dc4-205">Sélectionnez **Téléchargements et mises à jour**.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-205">Select **Downloads and updates**.</span></span>
2. <span data-ttu-id="b9dc4-206">Sélectionnez **Obtenir les mises à jour**.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-206">Select **Get updates**.</span></span>

### <span data-ttu-id="b9dc4-207">Tableau blanc collaboratif Microsoft</span><span class="sxs-lookup"><span data-stu-id="b9dc4-207">Microsoft Whiteboard</span></span>

<span data-ttu-id="b9dc4-208">Pour installer le tableau blanc Microsoft, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="b9dc4-208">To install the Microsoft Whiteboard:</span></span>

 - <span data-ttu-id="b9dc4-209">Cliquez sur l’icône de l' **espace de travail Windows Ink** dans le coin inférieur droit de la barre des tâches et téléchargez le **tableau blanc**.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-209">Select the **Windows Ink Workspace** icon on the lower right of the taskbar and download **Whiteboard**.</span></span>
 
   ![Espace de travail Ink](images/ink.png) 

<span data-ttu-id="b9dc4-211">Vous pouvez également installer le tableau blanc à partir du Microsoft Store:</span><span class="sxs-lookup"><span data-stu-id="b9dc4-211">Alternatively, you can install Whiteboard from the Microsoft Store:</span></span>

1. <span data-ttu-id="b9dc4-212">Ouvrez l’application Microsoft Store et recherchez le **tableau blanc**.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-212">Open Microsoft Store app and search for **Whiteboard**.</span></span>
2. <span data-ttu-id="b9dc4-213">Choisissez **non merci** pour vous connecter et utiliser les différents appareils.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-213">Choose **No thanks** to sign in and use across devices.</span></span>
3. <span data-ttu-id="b9dc4-214">Épingler le tableau blanc dans la barre des tâches.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-214">Pin Whiteboard to the taskbar.</span></span>

### <span data-ttu-id="b9dc4-215">Application surface</span><span class="sxs-lookup"><span data-stu-id="b9dc4-215">Surface app</span></span>

1. <span data-ttu-id="b9dc4-216">Dans la boutique Microsoft, recherchez **surface**.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-216">In the Microsoft Store, search for **Surface**.</span></span>
2. <span data-ttu-id="b9dc4-217">Définissez le **niveau de filtrage disponible sur** **tous les appareils**.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-217">Set the **Available on** filter to **All devices**.</span></span>
3. <span data-ttu-id="b9dc4-218">Installez l’application **surface** .</span><span class="sxs-lookup"><span data-stu-id="b9dc4-218">Install the **Surface** app.</span></span> <span data-ttu-id="b9dc4-219">Il s’agit de la première application répertoriée.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-219">This should be the first app listed.</span></span> <span data-ttu-id="b9dc4-220">Vous devrez peut-être associer votre MSA au Windows Store pour pouvoir installer l’application.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-220">You might need to associate your MSA to the Store in order to install the app.</span></span>
4. <span data-ttu-id="b9dc4-221">Épingler l’application **surface** à la barre des tâches.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-221">Pin the **Surface** app to taskbar.</span></span>

### <span data-ttu-id="b9dc4-222">Capture & croquis</span><span class="sxs-lookup"><span data-stu-id="b9dc4-222">Snip & Sketch</span></span>

1. <span data-ttu-id="b9dc4-223">Ouvrez l’application de **capture & esquisse** et épinglez-la à la barre des tâches.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-223">Open the **Snip & Sketch** app and pin it to the taskbar.</span></span>
2. <span data-ttu-id="b9dc4-224">Sélectionnez les points de suspension dans le coin supérieur droit, puis sélectionnez **paramètres**.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-224">Select the ellipsis in the upper right corner and then select **Settings**.</span></span>
3. <span data-ttu-id="b9dc4-225">Dans **paramètres**, activez la fonction de **copie automatique dans le presse-papiers**, **Enregistrez les captures**et les **fenêtres multiples** (facultatif).</span><span class="sxs-lookup"><span data-stu-id="b9dc4-225">In **Settings**, turn on **Auto copy to clipboard**, **Save snips**, and **Multiple windows** (optional).</span></span>

### <span data-ttu-id="b9dc4-226">MicrosoftOffice</span><span class="sxs-lookup"><span data-stu-id="b9dc4-226">Microsoft Office</span></span>

1. <span data-ttu-id="b9dc4-227">Ouvrez le [portail Office](https://portal.office.com/account#installs) et installez les applications souhaitées.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-227">Open the [Office Portal](https://portal.office.com/account#installs) and install your desired applications.</span></span>
2. <span data-ttu-id="b9dc4-228">Épinglez les applications Office souhaitées dans la barre des tâches.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-228">Pin desired Office applications to the taskbar.</span></span>
3. <span data-ttu-id="b9dc4-229">Si Outlook est installé, assurez-vous de définir le cache OST Outlook de façon à ce qu’il enregistre uniquement le cache des deux dernières semaines.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-229">If Outlook is installed, be sure to set the Outlook OST to only save last two weeks cache.</span></span> <span data-ttu-id="b9dc4-230">Le temps d’utilisation et de configuration du disque sera considérablement réduit.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-230">This will vastly reduce disk usage and setup time.</span></span>
    - <span data-ttu-id="b9dc4-231">Sélectionnez **File**  >  **paramètres du compte** de fichier, puis sélectionnez votre compte.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-231">Select **File** > **Account Settings** and select your account.</span></span>
    - <span data-ttu-id="b9dc4-232">Sélectionnez **modifier** , puis positionnez le curseur pour **utiliser le mode Exchange mis en cache** à 14 jours.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-232">Select **Change** and set the slider for **Use Cached Exchange Mode** to 14 days.</span></span>

### <span data-ttu-id="b9dc4-233">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b9dc4-233">Microsoft Teams</span></span>

1. <span data-ttu-id="b9dc4-234">Télécharger et installer [Microsoft teams](https://teams.microsoft.com/downloads).</span><span class="sxs-lookup"><span data-stu-id="b9dc4-234">Download and install [Microsoft Teams](https://teams.microsoft.com/downloads).</span></span>
2. <span data-ttu-id="b9dc4-235">Configurez les paramètres de démarrage automatique de l’application (facultatif).</span><span class="sxs-lookup"><span data-stu-id="b9dc4-235">Configure settings to Auto-start application (optional).</span></span>
3. <span data-ttu-id="b9dc4-236">Épingler des équipes dans la barre des tâches.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-236">Pin Teams to the taskbar.</span></span>
4. <span data-ttu-id="b9dc4-237">Envisagez de réduire les notifications d’équipe sur l’appareil pour éviter toute distraction (facultatif).</span><span class="sxs-lookup"><span data-stu-id="b9dc4-237">Consider reducing Teams notifications on the device to avoid distractions (optional).</span></span>

  ![Notifications teams](images/teams.png)

### <span data-ttu-id="b9dc4-239">Connecter l’application</span><span class="sxs-lookup"><span data-stu-id="b9dc4-239">Connect app</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b9dc4-240">Dans Windows 10, version 2004 et ultérieure, l’application connexion pour la projection sans fil à l’aide de Miracast n’est pas installée par défaut, mais est disponible sous la forme d’une fonctionnalité facultative.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-240">In Windows 10, version 2004 and later, the Connect app for wireless projection using Miracast is not installed by default, but is available as an optional feature.</span></span> <span data-ttu-id="b9dc4-241">Pour installer l’application, sélectionnez les **Settings**  >  **Apps**  >  **fonctionnalités facultatives**  >  **Ajouter une fonctionnalité** aux applications, puis installez l’application d' **affichage sans fil** .</span><span class="sxs-lookup"><span data-stu-id="b9dc4-241">To install the app, select on **Settings** > **Apps** > **Optional features** > **Add a feature** and then install the **Wireless Display** app.</span></span>

1. <span data-ttu-id="b9dc4-242">Recherchez **connexion**.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-242">Search for **Connect**.</span></span>
2. <span data-ttu-id="b9dc4-243">Ouvrez l’application, puis fermez-la (**Project à ce PC** peut ne pas fonctionner tant que l’application n’a pas été exécutée au moins une fois).</span><span class="sxs-lookup"><span data-stu-id="b9dc4-243">Open the app and then close it (**Project to this PC** might not work unless the app has been run at least once).</span></span>
3. <span data-ttu-id="b9dc4-244">Appuyez de façon prolongée ou cliquez avec le bouton droit pour épingler à la barre des tâches.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-244">Tap and hold or right-click to pin to taskbar.</span></span>
4. <span data-ttu-id="b9dc4-245">Recherchez les **paramètres de projection**.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-245">Search for **Projection settings**.</span></span>
5. <span data-ttu-id="b9dc4-246">Sous **certains appareils Windows et Android peuvent projeter sur ce PC lorsque vous prononcez**la mention OK, choisissez **disponible partout** si l’appareil n’est pas sur un réseau d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-246">Under **Some Windows and Android devices can project to this PC when you say it's OK**, choose **Available everywhere** if the device is not on a corporate network.</span></span> <span data-ttu-id="b9dc4-247">Dans le cas contraire, vous pouvez choisir **partout sur des réseaux sécurisés**.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-247">Otherwise, you can choose **Available everywhere on secure networks**.</span></span>
6. <span data-ttu-id="b9dc4-248">Sous **demander à Project pour ce PC**, choisissez **première fois uniquement**.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-248">Under **Ask to project to this PC**, choose **First time only**.</span></span>
7. <span data-ttu-id="b9dc4-249">Sous **exiger le code confidentiel pour le jumelage**, sélectionnez **jamais**.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-249">Under **Require PIN for pairing**, choose **Never**.</span></span>

<span data-ttu-id="b9dc4-250">Configuration recommandée hors du réseau d’entreprise:</span><span class="sxs-lookup"><span data-stu-id="b9dc4-250">Recommended configuration when not on the corporate network:</span></span>

  ![Paramètres à la maison](images/project1.png)

<span data-ttu-id="b9dc4-252">Configuration recommandée sur le réseau d’entreprise:</span><span class="sxs-lookup"><span data-stu-id="b9dc4-252">Recommended configuration on the corporate network:</span></span>

  ![Paramètres au bureau](images/project2.png)

### <span data-ttu-id="b9dc4-254">Votre téléphone</span><span class="sxs-lookup"><span data-stu-id="b9dc4-254">Your Phone</span></span>

<span data-ttu-id="b9dc4-255">L’application **votre téléphone** est installée par défaut sur Windows 10.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-255">The **Your Phone** app is installed by default on Windows 10.</span></span> <span data-ttu-id="b9dc4-256">Si ce n’est pas le cas, vous pouvez également l’installer à partir du Windows Store.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-256">If it is not present, you can also install it from the Windows Store.</span></span>

<span data-ttu-id="b9dc4-257">Pour plus d’informations sur la configuration de l’application, reportez-vous à la rubrique Configuration de [votre téléphone sur Windows 10 et synchronisation des données entre votre ordinateur et votre téléphone](https://www.windowscentral.com/how-set-your-phone-windows-10).</span><span class="sxs-lookup"><span data-stu-id="b9dc4-257">For information about setting up the app, see [How to set up Your Phone on Windows 10 and sync data between your PC and phone](https://www.windowscentral.com/how-set-your-phone-windows-10).</span></span> <span data-ttu-id="b9dc4-258">Consultez également [la rubrique Comment résoudre les problèmes courants liés à votre application de téléphone sur Windows 10](https://www.windowscentral.com/how-fix-common-problems-your-phone-app-windows-10).</span><span class="sxs-lookup"><span data-stu-id="b9dc4-258">Also see [How to fix common problems with Your Phone app on Windows 10](https://www.windowscentral.com/how-fix-common-problems-your-phone-app-windows-10).</span></span>

### <span data-ttu-id="b9dc4-259">Zones super fantaisie</span><span class="sxs-lookup"><span data-stu-id="b9dc4-259">Super Fancy Zones</span></span>

<span data-ttu-id="b9dc4-260">Les **zones super fantaisie** permettent aux utilisateurs de réorganiser les fenêtres afin de maximiser l’espace disponible à l’écran.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-260">**Super Fancy Zones** helps users arrange windows to maximize screen real estate.</span></span> <span data-ttu-id="b9dc4-261">Elle est désormais incluse dans [PowerToys](https://github.com/microsoft/PowerToys/releases) sur GitHub.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-261">It is now included in [PowerToys](https://github.com/microsoft/PowerToys/releases) on GitHub.</span></span>

### <span data-ttu-id="b9dc4-262">Navigateur Microsoft Edge chrome</span><span class="sxs-lookup"><span data-stu-id="b9dc4-262">Edge Chromium browser</span></span>

<span data-ttu-id="b9dc4-263">Téléchargez et installez le nouveau [navigateur Microsoft Edge chrome](https://www.microsoft.com/en-us/edge?form=MY01BL&OCID=MY01BL).</span><span class="sxs-lookup"><span data-stu-id="b9dc4-263">Download and install the new [Edge Chromium browser](https://www.microsoft.com/en-us/edge?form=MY01BL&OCID=MY01BL).</span></span>

## <span data-ttu-id="b9dc4-264">Paramètres supplémentaires</span><span class="sxs-lookup"><span data-stu-id="b9dc4-264">Additional settings</span></span>

### <span data-ttu-id="b9dc4-265">Stylo d’aileron sélectionner pour lancer le tableau blanc</span><span class="sxs-lookup"><span data-stu-id="b9dc4-265">Pen tail select to launch Whiteboard</span></span>

1. <span data-ttu-id="b9dc4-266">Recherchez **stylo** et sélectionnez **stylo & paramètres Windows Ink**.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-266">Search for **Pen** and select **Pen & Windows Ink settings**.</span></span>
2. <span data-ttu-id="b9dc4-267">Dans la partie inférieure de la page, sous **raccourcis clavier** , définissez l' **option Sélectionner une fois** sur le **tableau blanc collaboratif Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-267">Near the bottom of the page, under **Pen shortcuts** set **Select once** to **Microsoft Whiteboard**.</span></span> 

### <span data-ttu-id="b9dc4-268">Paramètres d’alimentation et de veille</span><span class="sxs-lookup"><span data-stu-id="b9dc4-268">Power and sleep settings</span></span>

1. <span data-ttu-id="b9dc4-269">Sélectionnez **Démarrer**les  >  **paramètres**  >  **système**  >  **d’alimentation & Sleep**.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-269">Select **Start** > **Settings** > **System** > **Power & sleep**.</span></span>
2. <span data-ttu-id="b9dc4-270">Positionnez le curseur mode d’alimentation sur **meilleures performances**.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-270">Set the power mode slider to **Best performance**.</span></span>
3. <span data-ttu-id="b9dc4-271">Configurez les valeurs de l’écran et du mode veille à votre choix.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-271">Configure screen and sleep values to your preference.</span></span>

### <span data-ttu-id="b9dc4-272">Écran de veille</span><span class="sxs-lookup"><span data-stu-id="b9dc4-272">Screen saver</span></span>

1. <span data-ttu-id="b9dc4-273">Recherchez l' **écran de verrouillage** et ouvrez les paramètres de l' **écran de verrouillage**.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-273">Search for **Lock Screen** and open **Lock screen settings**.</span></span>
2. <span data-ttu-id="b9dc4-274">Configurez vos préférences en matière de **paramètres de délai d’écran** et de paramètres d' **écran de veille** .</span><span class="sxs-lookup"><span data-stu-id="b9dc4-274">Configure **Screen timeout settings** and **Screen saver settings** to your preference.</span></span>

### <span data-ttu-id="b9dc4-275">Assistant Stockage</span><span class="sxs-lookup"><span data-stu-id="b9dc4-275">Storage Sense</span></span>

<span data-ttu-id="b9dc4-276">Surface Hub 2 étant doté d’un appareil compact de 128 Go pour le stockage local, il est nécessaire de tenir compte de l’utilisation des mesures d’enregistrement de stockage en cas d’utilisation normale.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-276">The Surface Hub 2 has a 128GB SSD for local storage, so it is necessary to consider the use of storage saving measures during normal usage.</span></span>  <span data-ttu-id="b9dc4-277">Pour configurer le sens de stockage:</span><span class="sxs-lookup"><span data-stu-id="b9dc4-277">To configure Storage Sense:</span></span>

1.  <span data-ttu-id="b9dc4-278">Recherchez **paramètres de stockage**dans les **paramètres système**.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-278">Search for **storage settings**, which is found under **System settings**.</span></span>
2.  <span data-ttu-id="b9dc4-279">Sous **paramètres**, sélectionnez l’option **activer le stockage** pour ouvrir la page Paramètres de **stockage** .</span><span class="sxs-lookup"><span data-stu-id="b9dc4-279">Under **Settings**, select **Turn on storage sense** to open the **Storage** settings page.</span></span>
3.  <span data-ttu-id="b9dc4-280">Activez **le stockage sur activé**.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-280">Turn Storage Sense to **On**.</span></span>
4.  <span data-ttu-id="b9dc4-281">Sélectionnez **configurer un sens de stockage ou exécutez-le maintenant** et configurez les paramètres permettant de conserver les fichiers en ligne le plus possible (en raison de l’espace disque limité).</span><span class="sxs-lookup"><span data-stu-id="b9dc4-281">Select **Configure Storage Sense or run it now** and configure settings to keep files online as much as possible (due to limited drive space).</span></span>

<span data-ttu-id="b9dc4-282">Paramètres recommandés:</span><span class="sxs-lookup"><span data-stu-id="b9dc4-282">Recommended settings:</span></span>
- <span data-ttu-id="b9dc4-283">Utilisez l’outil de stockage = quotidiennement.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-283">Run Storage Sense = Every Day.</span></span>
- <span data-ttu-id="b9dc4-284">Supprimez les fichiers temporaires que mes applications n’utilisent pas = tous les 14 jours (au moins).</span><span class="sxs-lookup"><span data-stu-id="b9dc4-284">Delete temporary files that my apps aren't using = Every 14 days (at least).</span></span>
- <span data-ttu-id="b9dc4-285">Supprimer les fichiers du dossier téléchargements s’ils y étaient depuis plus de 30 jours.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-285">Delete files in my Downloads folder if they have been there for over = 30 days.</span></span>
- <span data-ttu-id="b9dc4-286">OneDrive: le contenu devient en ligne uniquement s’il n’est pas ouvert pendant plus de 30 jours.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-286">OneDrive: Content will become online-only if not opened for more than = 30 days.</span></span>

### <span data-ttu-id="b9dc4-287">Mode tablette</span><span class="sxs-lookup"><span data-stu-id="b9dc4-287">Tablet mode</span></span>

<span data-ttu-id="b9dc4-288">Activez le mode tablette si vous le souhaitez, pour les besoins en matière d’accessibilité.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-288">Turn on Tablet mode if desired for accessibility needs.</span></span>

### <span data-ttu-id="b9dc4-289">Gestion de l’alimentation</span><span class="sxs-lookup"><span data-stu-id="b9dc4-289">Power management</span></span>

> [!NOTE]
> <span data-ttu-id="b9dc4-290">Avant d’effectuer la procédure suivante, contactez votre service informatique pour obtenir de l’aide afin d’exclure un périphérique surface Hub 2 de la stratégie de gestion de l’alimentation globale.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-290">Before performing the following procedure, check with your IT department for approval to exclude a Surface Hub 2S device from global power management policy.</span></span> <span data-ttu-id="b9dc4-291">Certains paramètres de gestion de l’alimentation peuvent désactiver la fonction de détection de présence.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-291">Some power management settings can disable the presence detection function.</span></span>

1. <span data-ttu-id="b9dc4-292">Recherchez le **Centre de logiciels** et ouvrez-le.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-292">Search for **Software Center** and open it.</span></span>
2. <span data-ttu-id="b9dc4-293">Sélectionnez des **options** dans le volet de navigation.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-293">Select **Options** in the navigation pane.</span></span>
3. <span data-ttu-id="b9dc4-294">Développez la section gestion de l' **alimentation** et sélectionnez **ne pas appliquer les paramètres d’alimentation du service informatique à cet ordinateur**.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-294">Expand the **Power management** section and select **Do not apply power settings from my IT department to this computer**.</span></span>

   ![Paramètres logiciels](images/soft-cntr.png)

### <span data-ttu-id="b9dc4-296">Paramètres du son</span><span class="sxs-lookup"><span data-stu-id="b9dc4-296">Sound settings</span></span>

1. <span data-ttu-id="b9dc4-297">Recherchez les **paramètres audio** et ouvrez cette page.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-297">Search for **Sounds settings** and open this page.</span></span>
2. <span data-ttu-id="b9dc4-298">Sélectionnez **son panneau de configuration** sur la droite, puis sélectionnez l’onglet **sons** .</span><span class="sxs-lookup"><span data-stu-id="b9dc4-298">Select **Sound Control Panel** on the right and select the **Sounds** tab.</span></span>
3. <span data-ttu-id="b9dc4-299">Sous **événements** , définissez l’option **connexion** de l’appareil et **Débranchez l’appareil** à **aucun**.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-299">Under **Program Events** set **Device Connect** and **Device Disconnect** to **None**.</span></span>

### <span data-ttu-id="b9dc4-300">Notifications de silence</span><span class="sxs-lookup"><span data-stu-id="b9dc4-300">Silence notifications</span></span>

1. <span data-ttu-id="b9dc4-301">Recherchez **assistance au focus** et ouvrez cette page.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-301">Search for **Focus assist** and open this page.</span></span>
2. <span data-ttu-id="b9dc4-302">Sélectionner **alarmes uniquement**.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-302">Select **Alarms Only**.</span></span> <span data-ttu-id="b9dc4-303">Cela évite les menus volants de notifications constantes.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-303">This will avoid constant notification flyouts.</span></span>

### <span data-ttu-id="b9dc4-304">Nettoyage de disque</span><span class="sxs-lookup"><span data-stu-id="b9dc4-304">Disk Cleanup</span></span>

1. <span data-ttu-id="b9dc4-305">Recherchez **Disk Cleanup** et ouvrez cette application.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-305">Search for **Disk Cleanup** and open this app.</span></span>
2. <span data-ttu-id="b9dc4-306">Sous **fichiers à supprimer**, sélectionnez les fichiers que vous souhaitez supprimer.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-306">Under **Files to delete**, select the files you wish to delete.</span></span> 
3. <span data-ttu-id="b9dc4-307">Sélectionnez également **nettoyer les fichiers système**.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-307">Also select **Clean up system files**.</span></span>

## <span data-ttu-id="b9dc4-308">Achever et vérifier</span><span class="sxs-lookup"><span data-stu-id="b9dc4-308">Complete and verify</span></span>

1. <span data-ttu-id="b9dc4-309">Recherchez et installez toutes les mises à jour Windows.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-309">Scan for and install all Windows Updates.</span></span>
2. <span data-ttu-id="b9dc4-310">Mise à jour de la stratégie de groupe</span><span class="sxs-lookup"><span data-stu-id="b9dc4-310">Update Group Policy</span></span>
    1. <span data-ttu-id="b9dc4-311">À l’invite de commandes avec élévation de privilèges, entrez **gpupdate/force/Boot/Wait: 0**.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-311">At an elevated command prompt, enter **gpupdate /force /boot /wait:0**.</span></span>
3. <span data-ttu-id="b9dc4-312">Redémarrez l'appareil.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-312">Reboot the device.</span></span>
4. <span data-ttu-id="b9dc4-313">Vérifiez les applications de la barre des tâches.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-313">Verify taskbar apps.</span></span>
    - <span data-ttu-id="b9dc4-314">Connecter l’application</span><span class="sxs-lookup"><span data-stu-id="b9dc4-314">Connect App</span></span>
    - <span data-ttu-id="b9dc4-315">Icône de verrouillage</span><span class="sxs-lookup"><span data-stu-id="b9dc4-315">Lock Icon</span></span>
    - <span data-ttu-id="b9dc4-316">Capture & croquis</span><span class="sxs-lookup"><span data-stu-id="b9dc4-316">Snip & Sketch</span></span>
    - <span data-ttu-id="b9dc4-317">Teams (le cas échéant)</span><span class="sxs-lookup"><span data-stu-id="b9dc4-317">Teams (if applicable)</span></span>
    - <span data-ttu-id="b9dc4-318">Applications Office (le cas échéant)</span><span class="sxs-lookup"><span data-stu-id="b9dc4-318">Office Apps (if applicable)</span></span>
    - <span data-ttu-id="b9dc4-319">Application surface</span><span class="sxs-lookup"><span data-stu-id="b9dc4-319">Surface App</span></span>
    - <span data-ttu-id="b9dc4-320">Tableau blanc</span><span class="sxs-lookup"><span data-stu-id="b9dc4-320">Whiteboard</span></span>
5. <span data-ttu-id="b9dc4-321">Vérifier la détection de présence.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-321">Verify presence detection.</span></span>
    - <span data-ttu-id="b9dc4-322">La détection de présence sera une icône verte dans la barre d’état système</span><span class="sxs-lookup"><span data-stu-id="b9dc4-322">Presence detection will be a green icon in the system tray</span></span>
6. <span data-ttu-id="b9dc4-323">Vérifier que l’application de Project à ce PC est activée avec l’application connexion (l’application n’a pas besoin d’être en cours d’exécution avant la connexion).</span><span class="sxs-lookup"><span data-stu-id="b9dc4-323">Verify projecting to this PC is enabled with the Connect App (the application does not need to be running before connecting).</span></span>
7. <span data-ttu-id="b9dc4-324">Vérifiez les paramètres d’alimentation et de veille.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-324">Verify power and sleep settings.</span></span>
    - <span data-ttu-id="b9dc4-325">Écran de veille: 15 minutes, définie sur (aucune), mystification ou Blank; la case à cocher pour exiger un mot de passe est activée</span><span class="sxs-lookup"><span data-stu-id="b9dc4-325">Screen Saver: 15 minutes, set to (none), Mystify or Blank; check box for requiring password is checked</span></span>
    - <span data-ttu-id="b9dc4-326">Écran: 2 heures</span><span class="sxs-lookup"><span data-stu-id="b9dc4-326">Screen: 2 hours</span></span>
    - <span data-ttu-id="b9dc4-327">PC: 4 heures</span><span class="sxs-lookup"><span data-stu-id="b9dc4-327">PC: 4 hours</span></span>
8. <span data-ttu-id="b9dc4-328">Vérifiez que Windows Hello fonctionne.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-328">Verify Windows Hello is working.</span></span>
9. <span data-ttu-id="b9dc4-329">Vérifiez les paramètres d’alimentation.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-329">Verify power settings.</span></span>
10. <span data-ttu-id="b9dc4-330">Vérifier la synchronisation vos paramètres sont désactivés.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-330">Verify sync your settings is disabled.</span></span>
11. <span data-ttu-id="b9dc4-331">Vérifiez les applications de démarrage.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-331">Verify startup apps.</span></span>

> [!TIP]
> <span data-ttu-id="b9dc4-332">Après l’installation et la configuration de Windows 10, les applications de surface Hub 2 peuvent être gérées comme n’importe quel autre appareil Windows 10.</span><span class="sxs-lookup"><span data-stu-id="b9dc4-332">After installing and configuring Windows 10, the Surface Hub 2S can be managed just like any other Windows 10 device.</span></span>

## <span data-ttu-id="b9dc4-333">Rubriquesassociées</span><span class="sxs-lookup"><span data-stu-id="b9dc4-333">Related topics</span></span>

[<span data-ttu-id="b9dc4-334">Migrer vers Windows 10 Professionnel ou Entreprise sur Surface Hub 2</span><span class="sxs-lookup"><span data-stu-id="b9dc4-334">Migrate to Windows 10 Pro or Enterprise on Surface Hub 2</span></span>](surface-hub-2s-migrate-os.md)
