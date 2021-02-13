---
title: Utilisation de l’outil de récupération de SurfaceHub
description: Utilisation de l’outil de récupération Surface Hub pour ré-imager le SSD.
ms.assetid: FDB6182C-1211-4A92-A930-6C106BCD5DC1
ms.reviewer: ''
manager: laurawi
keywords: gérer le Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 02/11/2020
ms.localizationpriority: medium
ms.openlocfilehash: 34a05eeabd284e0ad43317577b8e7ff9348ffe21
ms.sourcegitcommit: 7e028c1e66fb393dc0e8917dac257ce95e5e9ce7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/12/2021
ms.locfileid: "11327338"
---
# <span data-ttu-id="298bb-104">Utilisation de l’outil de récupération de SurfaceHub</span><span class="sxs-lookup"><span data-stu-id="298bb-104">Using the Surface Hub Recovery Tool</span></span>

<span data-ttu-id="298bb-105">L’outil de récupération [Microsoft Surface Hub](https://www.microsoft.com/download/details.aspx?id=52210) vous permet de ré-imager votre SSD (Solid State Drive) Surface Hub à l’aide d’un appareil de bureau Windows 10, sans appeler la prise en charge ni remplacer le SSD.</span><span class="sxs-lookup"><span data-stu-id="298bb-105">The [Microsoft Surface Hub Recovery Tool](https://www.microsoft.com/download/details.aspx?id=52210) helps you re-image your Surface Hub Solid State Drive (SSD) using a Windows 10 desktop device, without calling support or replacing the SSD.</span></span> <span data-ttu-id="298bb-106">Avec cet outil, vous pouvez réimager un SSD qui a un mot de passe administrateur inconnu, des erreurs de démarrage, n’a pas pu effectuer une récupération cloud ou pour un appareil qui dispose d’une version antérieure du système d’exploitation.</span><span class="sxs-lookup"><span data-stu-id="298bb-106">With this tool, you can reimage an SSD that has an unknown Administrator password, boot errors, was unable to complete a cloud recovery, or for a device that has an older version of the operating system.</span></span> <span data-ttu-id="298bb-107">L’outil ne corrige pas les SSD physiquement endommagés.</span><span class="sxs-lookup"><span data-stu-id="298bb-107">The tool will not fix physically damaged SSDs.</span></span>

<span data-ttu-id="298bb-108">Pour ré-imager le SSD Surface Hub à l’aide de l’outil de récupération, vous devez supprimer le SSD du Surface Hub, connecter le lecteur au câble USB à SATA, puis connecter le câble au PC de bureau sur lequel l’outil de récupération est installé.</span><span class="sxs-lookup"><span data-stu-id="298bb-108">To re-image the Surface Hub SSD using the Recovery Tool, you'll need to remove the SSD from the Surface Hub, connect the drive to the USB-to-SATA cable, and then connect the cable to the desktop PC on which the Recovery Tool is installed.</span></span> <span data-ttu-id="298bb-109">Pour plus d’informations sur la suppression du lecteur existant de votre Surface Hub, voir remplacement du [disque SSD Surface Hub.](surface-hub-ssd-replacement.md)</span><span class="sxs-lookup"><span data-stu-id="298bb-109">For more information on how to remove the existing drive from your Surface Hub, see [Surface Hub SSD replacement](surface-hub-ssd-replacement.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="298bb-110">Ne laissez pas l’appareil se mettre en veille ou interrompre le téléchargement du fichier image.</span><span class="sxs-lookup"><span data-stu-id="298bb-110">Do not let the device go to sleep or interrupt the download of the image file.</span></span>

<span data-ttu-id="298bb-111">Si l’outil n’a pas réussi à réinventer votre lecteur, contactez le support [Surface Hub.](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support)</span><span class="sxs-lookup"><span data-stu-id="298bb-111">If the tool is unsuccessful in reimaging your drive, please contact [Surface Hub Support](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support).</span></span>

## <span data-ttu-id="298bb-112">Prérequis</span><span class="sxs-lookup"><span data-stu-id="298bb-112">Prerequisites</span></span>

### <span data-ttu-id="298bb-113">Mandatory</span><span class="sxs-lookup"><span data-stu-id="298bb-113">Mandatory</span></span>

- <span data-ttu-id="298bb-114">PC hôte exécutant la version 64 bits de Windows 10, version 1607 ou supérieure.</span><span class="sxs-lookup"><span data-stu-id="298bb-114">Host PC running 64-bit version of Windows 10, version 1607 or higher.</span></span>
- <span data-ttu-id="298bb-115">Accès Internet</span><span class="sxs-lookup"><span data-stu-id="298bb-115">Internet access</span></span>
- <span data-ttu-id="298bb-116">Ouvrir le port USB 2.0 ou supérieur</span><span class="sxs-lookup"><span data-stu-id="298bb-116">Open USB 2.0 or greater port</span></span>
- <span data-ttu-id="298bb-117">Câble USB-SATA</span><span class="sxs-lookup"><span data-stu-id="298bb-117">USB-to-SATA cable</span></span>
- <span data-ttu-id="298bb-118">10 Go d’espace disque libre sur l’ordinateur hôte</span><span class="sxs-lookup"><span data-stu-id="298bb-118">10 GB of free disk space on the host computer</span></span>
- <span data-ttu-id="298bb-119">SSD livrés avec Surface Hub ou un SSD fourni par le support en remplacement.</span><span class="sxs-lookup"><span data-stu-id="298bb-119">SSDs shipped with Surface Hub or a SSD provided by Support as a replacement.</span></span> <span data-ttu-id="298bb-120">Les SSD non fournis par Microsoft ne sont pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="298bb-120">SSDs not supplied by Microsoft are not supported.</span></span>

### <span data-ttu-id="298bb-121">Nos recommandations</span><span class="sxs-lookup"><span data-stu-id="298bb-121">Recommended</span></span>

- <span data-ttu-id="298bb-122">Connexion Internet haut débit</span><span class="sxs-lookup"><span data-stu-id="298bb-122">High-speed Internet connection</span></span>
- <span data-ttu-id="298bb-123">Ouvrir le port USB 3.0</span><span class="sxs-lookup"><span data-stu-id="298bb-123">Open USB 3.0 port</span></span>
- <span data-ttu-id="298bb-124">Câble USB 3.0 ou un câble USB-SATA supérieur</span><span class="sxs-lookup"><span data-stu-id="298bb-124">USB 3.0 or higher USB-to-SATA cable</span></span>
- <span data-ttu-id="298bb-125">L’outil d’imagerie a été testé avec la création et le modèle de câbles suivants :</span><span class="sxs-lookup"><span data-stu-id="298bb-125">The imaging tool was tested with the following make and model of cables:</span></span>
    - <span data-ttu-id="298bb-126">Startech USB312SAT3CB</span><span class="sxs-lookup"><span data-stu-id="298bb-126">Startech USB312SAT3CB</span></span>
    - <span data-ttu-id="298bb-127">Rosewill RCUC16001</span><span class="sxs-lookup"><span data-stu-id="298bb-127">Rosewill RCUC16001</span></span>
    - <span data-ttu-id="298bb-128">Ugreen 20231</span><span class="sxs-lookup"><span data-stu-id="298bb-128">Ugreen 20231</span></span>

## <span data-ttu-id="298bb-129">Télécharger l’outil de récupération Surface Hub</span><span class="sxs-lookup"><span data-stu-id="298bb-129">Download Surface Hub Recovery Tool</span></span>

<span data-ttu-id="298bb-130">L’outil de récupération Surface Hub est disponible en téléchargement à partir des outils [Surface Hub](https://www.microsoft.com/download/details.aspx?id=52210)  pour les services informatiques sous le nom de \*\* fichierSurfaceHub_Recovery_v2.7.139.0.msi\*\*.</span><span class="sxs-lookup"><span data-stu-id="298bb-130">Surface Hub Recovery Tool is available for download from [Surface Hub Tools for IT](https://www.microsoft.com/download/details.aspx?id=52210)  under the file name **SurfaceHub_Recovery_v2.7.139.0.msi**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="298bb-131">Cette version, publiée le 11 février 2021, remplace la version antérieure, qui n’est plus fonctionnelle.</span><span class="sxs-lookup"><span data-stu-id="298bb-131">This version, released Feb 11, 2021, replaces the earlier build, which is no longer functional.</span></span> <span data-ttu-id="298bb-132">Si vous avez téléchargé cet outil précédemment, veuillez ignorer et utiliser la version actuelle.</span><span class="sxs-lookup"><span data-stu-id="298bb-132">If you downloaded this tool previously, please discard and use the current version.</span></span>

<span data-ttu-id="298bb-133">Pour démarrer le téléchargement, cliquez sur **Télécharger,** choisissez **SurfaceHub_Recovery_v2.7.139.0.msi**  dans la liste, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="298bb-133">To start the download, click **Download**, choose **SurfaceHub_Recovery_v2.7.139.0.msi**  from the list, and click **Next**.</span></span> <span data-ttu-id="298bb-134">Dans la fenêtre pop-up, choisissez l’une des touches suivantes :</span><span class="sxs-lookup"><span data-stu-id="298bb-134">From the pop-up, choose one of the following:</span></span>

- <span data-ttu-id="298bb-135">Cliquez **sur Exécuter** pour démarrer l’installation immédiatement.</span><span class="sxs-lookup"><span data-stu-id="298bb-135">Click **Run** to start the installation immediately.</span></span>
- <span data-ttu-id="298bb-136">Cliquez **sur Enregistrer** pour copier le téléchargement sur votre ordinateur pour une installation ultérieure.</span><span class="sxs-lookup"><span data-stu-id="298bb-136">Click **Save** to copy the download to your computer for later installation.</span></span>

<span data-ttu-id="298bb-137">Installez l’outil de récupération Surface Hub sur le PC hôte.</span><span class="sxs-lookup"><span data-stu-id="298bb-137">Install Surface Hub Recovery Tool on the host PC.</span></span>

## <span data-ttu-id="298bb-138">Exécuter l’outil de récupération Surface Hub</span><span class="sxs-lookup"><span data-stu-id="298bb-138">Run Surface Hub Recovery Tool</span></span>

1. <span data-ttu-id="298bb-139">Sur le PC hôte, sélectionnez le bouton Démarrer, faites défiler la liste alphabétique à gauche, puis sélectionnez le raccourci de l’outil de récupération. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="298bb-139">On the host PC, select the **Start** button, scroll through the alphabetical list on the left, and select the recovery tool shortcut.</span></span>

    ![Raccourci de l’outil de récupération Microsoft Surface Hub](images/shrt-shortcut.png)

2. <span data-ttu-id="298bb-141">Cliquez sur **Démarrer**.</span><span class="sxs-lookup"><span data-stu-id="298bb-141">Click **Start**.</span></span>

    ![Bouton Démarrer de l’outil de récupération](images/shrt-start.png)


3. <span data-ttu-id="298bb-143">Dans la **fenêtre Recommandations,** cliquez sur **Suivant.**</span><span class="sxs-lookup"><span data-stu-id="298bb-143">In the **Guidance** window, click **Next**.</span></span>

    ![Ne laissez pas votre ordinateur passer aux instructions de veille](images/shrt-guidance.png)

4. <span data-ttu-id="298bb-145">Dans la fenêtre Sélectionner une image, cliquez sur **RS2** ou son successeur **20H2,** sélectionnez **Continuer,** puis sélectionnez **Télécharger l’image.**</span><span class="sxs-lookup"><span data-stu-id="298bb-145">In the Select image window, click either **RS2** or its successor **20H2**, select **Continue,** and then select **Download image.**</span></span>

     <span data-ttu-id="298bb-146">![Image de téléchargement de l’outil de récupération ](images/shrt-select-image.png) ![ d’image Sélectionner l’outil de récupération d’image](images/shrt-download-image.png)</span><span class="sxs-lookup"><span data-stu-id="298bb-146">![Recovery Tool Select image](images/shrt-select-image.png) ![Recovery Tool Download image](images/shrt-download-image.png)</span></span>

5. <span data-ttu-id="298bb-147">Le temps de téléchargement de l’image de récupération dépend des vitesses de connexion Internet.</span><span class="sxs-lookup"><span data-stu-id="298bb-147">Time to download the recovery image is dependent on internet connection speeds.</span></span> <span data-ttu-id="298bb-148">En moyenne, une connexion d’entreprise peut prendre jusqu’à une heure pour télécharger le fichier image de 8 Go.</span><span class="sxs-lookup"><span data-stu-id="298bb-148">On an average corporate connection, it can take up to an hour to download the 8GB image file.</span></span>

    ![Téléchargement d’une image](images/shrt-download.png)



5. <span data-ttu-id="298bb-150">Une fois le téléchargement terminé, l’outil vous demande de connecter un lecteur SSD.</span><span class="sxs-lookup"><span data-stu-id="298bb-150">When the download is complete, the tool instructs you to connect an SSD drive.</span></span> <span data-ttu-id="298bb-151">Si l’outil ne parvient pas à localiser le lecteur attaché, il est possible que le câble utilisé ne rapporte pas le nom du SSD à Windows.</span><span class="sxs-lookup"><span data-stu-id="298bb-151">If the tool is unable to locate the attached drive, there is a good chance that the cable being used is not reporting the name of the SSD to Windows.</span></span>  <span data-ttu-id="298bb-152">L’outil d’imagerie doit trouver le nom du lecteur comme « Périphérique USB LITEON L CH-128V2S » avant de pouvoir continuer.</span><span class="sxs-lookup"><span data-stu-id="298bb-152">The imaging tool must find the name of the drive as "LITEON L CH-128V2S USB Device" before it can continue.</span></span>  <span data-ttu-id="298bb-153">Pour plus d’informations sur la suppression du lecteur existant de votre Surface Hub, voir remplacement du [disque SSD Surface Hub.](surface-hub-ssd-replacement.md)</span><span class="sxs-lookup"><span data-stu-id="298bb-153">For more information on how to remove the existing drive from your Surface Hub, see [Surface Hub SSD replacement](surface-hub-ssd-replacement.md).</span></span>

    ![Connect SSD](images/shrt-drive.png)

6. <span data-ttu-id="298bb-155">Lorsque le lecteur est reconnu, cliquez sur **Démarrer** pour commencer le processus de ré-imagerie.</span><span class="sxs-lookup"><span data-stu-id="298bb-155">When the drive is recognized, click **Start** to begin the re-imaging process.</span></span> <span data-ttu-id="298bb-156">Dans l’avertissement signalant que toutes les données du lecteur seront effacées, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="298bb-156">On the warning that all data on the drive will be erased, click **OK**.</span></span>



    <span data-ttu-id="298bb-157">Avant d’appliquer l’image système au lecteur, le SSD est repartitioné et formaté.</span><span class="sxs-lookup"><span data-stu-id="298bb-157">Prior to applying the system image to the drive, the SSD is repartitioned and formatted.</span></span> <span data-ttu-id="298bb-158">La copie des binaires système prend environ 30 minutes, mais peut prendre plus de temps en fonction de la vitesse de votre bus USB, du câble utilisé ou du logiciel antivirus installé sur votre système.</span><span class="sxs-lookup"><span data-stu-id="298bb-158">Copying the system binaries will take approximately 30 minutes, but can take longer depending on the speed of your USB bus, the cable being used, or antivirus software installed on your system.</span></span>



## <span data-ttu-id="298bb-159">Résolution des problèmes et problèmes courants</span><span class="sxs-lookup"><span data-stu-id="298bb-159">Troubleshooting and common problems</span></span>

<span data-ttu-id="298bb-160">Problème</span><span class="sxs-lookup"><span data-stu-id="298bb-160">Issue</span></span> | <span data-ttu-id="298bb-161">Remarques</span><span class="sxs-lookup"><span data-stu-id="298bb-161">Notes</span></span>
--- | ---
<span data-ttu-id="298bb-162">L’outil ne parvient pas à imager le SSD</span><span class="sxs-lookup"><span data-stu-id="298bb-162">The tool fails to image the SSD</span></span> | <span data-ttu-id="298bb-163">Assurez-vous que vous utilisez un SSD fourni en usine et l’un des câbles testés.</span><span class="sxs-lookup"><span data-stu-id="298bb-163">Make sure you are using a factory-supplied SSD and one of the tested cables.</span></span>
<span data-ttu-id="298bb-164">Le processus de réinventation semble interrompu/figé</span><span class="sxs-lookup"><span data-stu-id="298bb-164">The reimaging process appears halted/frozen</span></span> | <span data-ttu-id="298bb-165">Il est sûr de fermer et de redémarrer l’outil de récupération Surface Hub sans que le SSD n’en soit souffrant.</span><span class="sxs-lookup"><span data-stu-id="298bb-165">It is safe to close and restart the Surface Hub Recovery Tool with no ill effect to the SSD.</span></span>
<span data-ttu-id="298bb-166">Le lecteur n’est pas reconnu par l’outil</span><span class="sxs-lookup"><span data-stu-id="298bb-166">The drive isn’t recognized by the tool</span></span> | <span data-ttu-id="298bb-167">Vérifiez que le SSD Surface Hub est indiqué en tant que lecteur Lite-On, « Périphérique USB LITEON L CH-128V2S ».</span><span class="sxs-lookup"><span data-stu-id="298bb-167">Verify that the Surface Hub SSD is enumerated as a Lite-On drive, "LITEON L CH-128V2S USB Device".</span></span>  <span data-ttu-id="298bb-168">Si le lecteur est reconnu comme un autre périphérique nommé, votre câble actuel n’est pas compatible.</span><span class="sxs-lookup"><span data-stu-id="298bb-168">If the drive is recognized as another named device, your current cable isn’t compatible.</span></span> <span data-ttu-id="298bb-169">Essayez un autre câble ou l’un des câbles testés répertoriés ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="298bb-169">Try another cable or one of the tested cable listed above.</span></span>
<span data-ttu-id="298bb-170">Erreur : -2147024809</span><span class="sxs-lookup"><span data-stu-id="298bb-170">Error: -2147024809</span></span> | <span data-ttu-id="298bb-171">Ouvrez le Gestionnaire de disques et supprimez les partitions sur le lecteur Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="298bb-171">Open Disk Manager and remove the partitions on the Surface Hub drive.</span></span>  <span data-ttu-id="298bb-172">Déconnectez et reconnectez le lecteur à l’ordinateur hôte.</span><span class="sxs-lookup"><span data-stu-id="298bb-172">Disconnect and reconnect the drive to the host machine.</span></span> <span data-ttu-id="298bb-173">Redémarrez l’outil d’imagerie.</span><span class="sxs-lookup"><span data-stu-id="298bb-173">Restart the imaging tool again.</span></span>

<span data-ttu-id="298bb-174">Si l’outil n’a pas réussi à réinventer votre lecteur, contactez le support [Surface Hub.](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support)</span><span class="sxs-lookup"><span data-stu-id="298bb-174">If the tool is unsuccessful in reimaging your drive, please contact [Surface Hub Support](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support).</span></span>

## <span data-ttu-id="298bb-175">Historique des versions</span><span class="sxs-lookup"><span data-stu-id="298bb-175">Version history</span></span>


### <span data-ttu-id="298bb-176">Version v2.7.139.0</span><span class="sxs-lookup"><span data-stu-id="298bb-176">Version v2.7.139.0</span></span>

*<span data-ttu-id="298bb-177">Date de publication : 11 février 2021</span><span class="sxs-lookup"><span data-stu-id="298bb-177">Release date: February 11, 2021</span></span>*<br>
<span data-ttu-id="298bb-178">Cette version de l’outil de récupération Surface Hub ajoute la prise en charge des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="298bb-178">This version of Surface Hub Recovery Tool adds support for the following:</span></span>

- <span data-ttu-id="298bb-179">Mise à jour de sécurité</span><span class="sxs-lookup"><span data-stu-id="298bb-179">Security update</span></span>


### <span data-ttu-id="298bb-180">Version v2.0.139.0</span><span class="sxs-lookup"><span data-stu-id="298bb-180">Version v2.0.139.0</span></span>

> [!IMPORTANT]
> <span data-ttu-id="298bb-181">Cette version n’est plus fonctionnelle.</span><span class="sxs-lookup"><span data-stu-id="298bb-181">This version is no longer functional.</span></span> <span data-ttu-id="298bb-182">Veuillez télécharger la version actuelle, répertoriée ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="298bb-182">Please download the current version, listed above.</span></span> 

*<span data-ttu-id="298bb-183">Date de publication : 18 décembre 2020</span><span class="sxs-lookup"><span data-stu-id="298bb-183">Release date: December 18, 2020</span></span>*<br>
<span data-ttu-id="298bb-184">Cette version de l’outil de récupération Surface Hub ajoute la prise en charge des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="298bb-184">This version of Surface Hub Recovery Tool adds support for the following:</span></span>
- <span data-ttu-id="298bb-185">Mise à jour pour prendre en charge windows 10 Team 2020 Update (20H2)</span><span class="sxs-lookup"><span data-stu-id="298bb-185">Update to support Windows 10 Team 2020 Update (20H2)</span></span>
- <span data-ttu-id="298bb-186">Améliorations de l’expérience utilisateur</span><span class="sxs-lookup"><span data-stu-id="298bb-186">User experience improvements</span></span>
- <span data-ttu-id="298bb-187">Modifications architecturales</span><span class="sxs-lookup"><span data-stu-id="298bb-187">Architectural changes</span></span>
- <span data-ttu-id="298bb-188">Ajouts de télémétrie</span><span class="sxs-lookup"><span data-stu-id="298bb-188">Telemetry additions</span></span>

