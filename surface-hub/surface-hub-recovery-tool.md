---
title: Utilisation de l’outil de récupération de SurfaceHub
description: Découvrez comment utiliser l’outil de récupération de surface Hub pour réutiliser le SSD.
ms.assetid: FDB6182C-1211-4A92-A930-6C106BCD5DC1
ms.reviewer: ''
manager: laurawi
keywords: gérer le Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 05/22/2018
ms.localizationpriority: medium
ms.openlocfilehash: 1988a6ed59525d7dc77872e532247dbc50f01bdf
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10834169"
---
# <span data-ttu-id="667c7-104">Utilisation de l’outil de récupération de SurfaceHub</span><span class="sxs-lookup"><span data-stu-id="667c7-104">Using the Surface Hub Recovery Tool</span></span>

<span data-ttu-id="667c7-105">L' [outil de récupération Microsoft surface Hub](https://www.microsoft.com/download/details.aspx?id=52210) permet de réutiliser votre périphérique de bureau de surface Hub à l’aide d’un appareil de bureau Windows 10, sans appeler le support technique ou en remplaçant le disque SSD.</span><span class="sxs-lookup"><span data-stu-id="667c7-105">The [Microsoft Surface Hub Recovery Tool](https://www.microsoft.com/download/details.aspx?id=52210) helps you re-image your Surface Hub Solid State Drive (SSD) using a Windows 10 desktop device, without calling support or replacing the SSD.</span></span> <span data-ttu-id="667c7-106">Grâce à cet outil, vous pouvez Redisposer une image de type SSD dont le mot de passe est inconnu, qu’il n’est pas possible de terminer une récupération du Cloud ou d’un appareil doté d’une version antérieure du système d’exploitation.</span><span class="sxs-lookup"><span data-stu-id="667c7-106">With this tool, you can reimage an SSD that has an unknown Administrator password, boot errors, was unable to complete a cloud recovery, or for a device that has an older version of the operating system.</span></span> <span data-ttu-id="667c7-107">L’outil ne résoudra pas les SSDs physiques endommagés.</span><span class="sxs-lookup"><span data-stu-id="667c7-107">The tool will not fix physically damaged SSDs.</span></span>

<span data-ttu-id="667c7-108">Pour réutiliser le disque SSD surface Hub à l’aide de l’outil de récupération, vous devez supprimer le disque SSD de surface Hub, connecter le lecteur au câble USB-à-SATA, puis raccorder le câble au PC de bureau sur lequel est installé l’outil de récupération.</span><span class="sxs-lookup"><span data-stu-id="667c7-108">To re-image the Surface Hub SSD using the Recovery Tool, you'll need to remove the SSD from the Surface Hub, connect the drive to the USB-to-SATA cable, and then connect the cable to the desktop PC on which the Recovery Tool is installed.</span></span> <span data-ttu-id="667c7-109">Pour plus d’informations sur la façon de supprimer le lecteur existant de votre surface Hub, voir [remplacement de SSD de surface Hub](surface-hub-ssd-replacement.md).</span><span class="sxs-lookup"><span data-stu-id="667c7-109">For more information on how to remove the existing drive from your Surface Hub, see [Surface Hub SSD replacement](surface-hub-ssd-replacement.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="667c7-110">Ne laissez pas le périphérique dormir en veille ou interrompez le téléchargement du fichier image.</span><span class="sxs-lookup"><span data-stu-id="667c7-110">Do not let the device go to sleep or interrupt the download of the image file.</span></span>

<span data-ttu-id="667c7-111">Si l’outil ne parvenez pas à réimagingr votre lecteur, contactez le [support surface Hub](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support).</span><span class="sxs-lookup"><span data-stu-id="667c7-111">If the tool is unsuccessful in reimaging your drive, please contact [Surface Hub Support](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support).</span></span>

## <span data-ttu-id="667c7-112">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="667c7-112">Prerequisites</span></span>

### <span data-ttu-id="667c7-113">Mandatory</span><span class="sxs-lookup"><span data-stu-id="667c7-113">Mandatory</span></span>

- <span data-ttu-id="667c7-114">ORDINATEUR hôte exécutant une version 64 bits, version 1607 ou ultérieure.</span><span class="sxs-lookup"><span data-stu-id="667c7-114">Host PC running 64-bit version of Windows 10, version 1607 or higher.</span></span>
- <span data-ttu-id="667c7-115">Accès Internet</span><span class="sxs-lookup"><span data-stu-id="667c7-115">Internet access</span></span>
- <span data-ttu-id="667c7-116">Ouvrez USB 2,0 ou une version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="667c7-116">Open USB 2.0 or greater port</span></span>
- <span data-ttu-id="667c7-117">Câble USB vers SATA</span><span class="sxs-lookup"><span data-stu-id="667c7-117">USB-to-SATA cable</span></span>
- <span data-ttu-id="667c7-118">10 Go d’espace disque disponible sur l’ordinateur hôte</span><span class="sxs-lookup"><span data-stu-id="667c7-118">10 GB of free disk space on the host computer</span></span>
- <span data-ttu-id="667c7-119">SSDs fourni avec surface Hub ou un SSD fourni par le support technique en tant que remplacement.</span><span class="sxs-lookup"><span data-stu-id="667c7-119">SSDs shipped with Surface Hub or a SSD provided by Support as a replacement.</span></span> <span data-ttu-id="667c7-120">SSDs non fourni par Microsoft n’est pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="667c7-120">SSDs not supplied by Microsoft are not supported.</span></span>

### <span data-ttu-id="667c7-121">Nos recommandations</span><span class="sxs-lookup"><span data-stu-id="667c7-121">Recommended</span></span>

- <span data-ttu-id="667c7-122">Connexion Internet haut débit</span><span class="sxs-lookup"><span data-stu-id="667c7-122">High-speed Internet connection</span></span>
- <span data-ttu-id="667c7-123">Ouvrir le port USB 3,0</span><span class="sxs-lookup"><span data-stu-id="667c7-123">Open USB 3.0 port</span></span>
- <span data-ttu-id="667c7-124">Câble USB 3,0 ou une version ultérieure USB-SATA</span><span class="sxs-lookup"><span data-stu-id="667c7-124">USB 3.0 or higher USB-to-SATA cable</span></span>
- <span data-ttu-id="667c7-125">L’outil d’imagerie a été testé avec la marque et le modèle de câble suivants:</span><span class="sxs-lookup"><span data-stu-id="667c7-125">The imaging tool was tested with the following make and model of cables:</span></span>
    - <span data-ttu-id="667c7-126">Startech USB312SAT3CB</span><span class="sxs-lookup"><span data-stu-id="667c7-126">Startech USB312SAT3CB</span></span>
    - <span data-ttu-id="667c7-127">Rosewill RCUC16001</span><span class="sxs-lookup"><span data-stu-id="667c7-127">Rosewill RCUC16001</span></span>
    - <span data-ttu-id="667c7-128">Ugreen 20231</span><span class="sxs-lookup"><span data-stu-id="667c7-128">Ugreen 20231</span></span>

## <span data-ttu-id="667c7-129">Télécharger l’outil de récupération de surface Hub</span><span class="sxs-lookup"><span data-stu-id="667c7-129">Download Surface Hub Recovery Tool</span></span>

<span data-ttu-id="667c7-130">L’outil de récupération de surface Hub est disponible en téléchargement à partir des [Outils surface Hub pour ce dernier](https://www.microsoft.com/download/details.aspx?id=52210) sous le nom de fichier **SurfaceHub_Recovery_v1.14.137.0.msi**.</span><span class="sxs-lookup"><span data-stu-id="667c7-130">Surface Hub Recovery Tool is available for download from [Surface Hub Tools for IT](https://www.microsoft.com/download/details.aspx?id=52210)  under the file name **SurfaceHub_Recovery_v1.14.137.0.msi**.</span></span>

<span data-ttu-id="667c7-131">Pour démarrer le téléchargement, cliquez sur **Télécharger**, choisissez **SurfaceHub_Recovery_v1.14.137.0.msi** dans la liste, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="667c7-131">To start the download, click **Download**, choose **SurfaceHub_Recovery_v1.14.137.0.msi** from the list, and click **Next**.</span></span> <span data-ttu-id="667c7-132">Dans la fenêtre qui s’affiche, choisissez l’une des options suivantes:</span><span class="sxs-lookup"><span data-stu-id="667c7-132">From the pop-up, choose one of the following:</span></span>

- <span data-ttu-id="667c7-133">Cliquez sur **exécuter** pour démarrer l’installation immédiatement.</span><span class="sxs-lookup"><span data-stu-id="667c7-133">Click **Run** to start the installation immediately.</span></span>
- <span data-ttu-id="667c7-134">Cliquez sur **Enregistrer** pour copier le téléchargement sur votre ordinateur pour une installation ultérieure.</span><span class="sxs-lookup"><span data-stu-id="667c7-134">Click **Save** to copy the download to your computer for later installation.</span></span>

<span data-ttu-id="667c7-135">Installez l’outil de récupération de surface Hub sur l’ordinateur hôte.</span><span class="sxs-lookup"><span data-stu-id="667c7-135">Install Surface Hub Recovery Tool on the host PC.</span></span>

## <span data-ttu-id="667c7-136">Exécuter l’outil de récupération de surface Hub</span><span class="sxs-lookup"><span data-stu-id="667c7-136">Run Surface Hub Recovery Tool</span></span>

1. <span data-ttu-id="667c7-137">Sur l’ordinateur hôte, sélectionnez le bouton **Démarrer** , faites défiler la liste alphabétique sur la gauche, puis sélectionnez le raccourci de l’outil de récupération.</span><span class="sxs-lookup"><span data-stu-id="667c7-137">On the host PC, select the **Start** button, scroll through the alphabetical list on the left, and select the recovery tool shortcut.</span></span>

    ![Raccourci de l’outil de récupération Microsoft surface Hub](images/shrt-shortcut.png)

2. <span data-ttu-id="667c7-139">Cliquez sur **Démarrer**.</span><span class="sxs-lookup"><span data-stu-id="667c7-139">Click **Start**.</span></span>

    ![Bouton Démarrer de l’outil de récupération](images/shrt-start.png)

3. <span data-ttu-id="667c7-141">Dans la fenêtre d' **aide** , cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="667c7-141">In the **Guidance** window, click **Next**.</span></span>

    ![Ne laissez pas votre ordinateur accéder aux conseils de mise en veille](images/shrt-guidance.png)

4. <span data-ttu-id="667c7-143">Cliquez sur **Oui** pour télécharger l’image.</span><span class="sxs-lookup"><span data-stu-id="667c7-143">click **Yes** to download the image.</span></span> <span data-ttu-id="667c7-144">Le temps de téléchargement de l’image de récupération dépend des vitesses de connexion Internet.</span><span class="sxs-lookup"><span data-stu-id="667c7-144">Time to download the recovery image is dependent on internet connection speeds.</span></span> <span data-ttu-id="667c7-145">Sur une connexion d’entreprise moyenne, il peut s’écouler jusqu’à une heure pour télécharger le fichier image de 8 Go.</span><span class="sxs-lookup"><span data-stu-id="667c7-145">On an average corporate connection, it can take up to an hour to download the 8GB image file.</span></span>

    ![Télécharger l’image?](images/shrt-download.png)

5. <span data-ttu-id="667c7-147">Lorsque le téléchargement est terminé, l’outil vous demande de connecter un disque SSD.</span><span class="sxs-lookup"><span data-stu-id="667c7-147">When the download is complete, the tool instructs you to connect an SSD drive.</span></span> <span data-ttu-id="667c7-148">Si l’outil ne parvient pas à trouver le lecteur en pièce jointe, il est possible que le câble utilisé ne signale pas le nom de l’objet SSD dans Windows.</span><span class="sxs-lookup"><span data-stu-id="667c7-148">If the tool is unable to locate the attached drive, there is a good chance that the cable being used is not reporting the name of the SSD to Windows.</span></span>  <span data-ttu-id="667c7-149">L’outil d’imagerie doit trouver le nom du lecteur comme «LITEON L-128V2S USB» pour pouvoir continuer.</span><span class="sxs-lookup"><span data-stu-id="667c7-149">The imaging tool must find the name of the drive as "LITEON L CH-128V2S USB Device" before it can continue.</span></span>  <span data-ttu-id="667c7-150">Pour plus d’informations sur la façon de supprimer le lecteur existant de votre surface Hub, voir [remplacement de SSD de surface Hub](surface-hub-ssd-replacement.md).</span><span class="sxs-lookup"><span data-stu-id="667c7-150">For more information on how to remove the existing drive from your Surface Hub, see [Surface Hub SSD replacement](surface-hub-ssd-replacement.md).</span></span>

    ![Connexion SSD](images/shrt-drive.png)

6. <span data-ttu-id="667c7-152">Lorsque le lecteur est reconnu, cliquez sur **Démarrer** pour démarrer le processus de nouvelle image.</span><span class="sxs-lookup"><span data-stu-id="667c7-152">When the drive is recognized, click **Start** to begin the re-imaging process.</span></span> <span data-ttu-id="667c7-153">Sur le message d’avertissement indiquant que toutes les données du lecteur seront effacées, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="667c7-153">On the warning that all data on the drive will be erased, click **OK**.</span></span>

    ![Commencer à recréer une image de la vidéo SSD](images/shrt-drive-start.png)

    <span data-ttu-id="667c7-155">Avant d’appliquer l’image système au lecteur, le disque SSD est repartitionné et mis en forme.</span><span class="sxs-lookup"><span data-stu-id="667c7-155">Prior to applying the system image to the drive, the SSD is repartitioned and formatted.</span></span> <span data-ttu-id="667c7-156">La copie des fichiers binaires du système prend environ 30 minutes, mais peut prendre plus de temps en fonction de la vitesse de votre bus USB, du câble utilisé ou du logiciel antivirus installé sur votre système.</span><span class="sxs-lookup"><span data-stu-id="667c7-156">Copying the system binaries will take approximately 30 minutes, but can take longer depending on the speed of your USB bus, the cable being used, or antivirus software installed on your system.</span></span>

    ![Copie réalisée](images/shrt-done.png)

    ![Recréation d’image terminée](images/shrt-complete.png)

## <span data-ttu-id="667c7-159">Résolution des problèmes et problèmes courants</span><span class="sxs-lookup"><span data-stu-id="667c7-159">Troubleshooting and common problems</span></span>

<span data-ttu-id="667c7-160">Problème</span><span class="sxs-lookup"><span data-stu-id="667c7-160">Issue</span></span> | <span data-ttu-id="667c7-161">Remarques</span><span class="sxs-lookup"><span data-stu-id="667c7-161">Notes</span></span>
--- | ---
<span data-ttu-id="667c7-162">L’outil ne parvient pas à imager le SSD</span><span class="sxs-lookup"><span data-stu-id="667c7-162">The tool fails to image the SSD</span></span> | <span data-ttu-id="667c7-163">Vérifiez que vous utilisez un SSD fourni par un fabricant et un des câbles testés.</span><span class="sxs-lookup"><span data-stu-id="667c7-163">Make sure you are using a factory-supplied SSD and one of the tested cables.</span></span>
<span data-ttu-id="667c7-164">Le processus de recréation d’image apparaît arrêté ou figé</span><span class="sxs-lookup"><span data-stu-id="667c7-164">The reimaging process appears halted/frozen</span></span> | <span data-ttu-id="667c7-165">Il est possible de fermer et de redémarrer l’outil de récupération de surface Hub sans effet pour le SSD.</span><span class="sxs-lookup"><span data-stu-id="667c7-165">It is safe to close and restart the Surface Hub Recovery Tool with no ill effect to the SSD.</span></span>
<span data-ttu-id="667c7-166">Le lecteur n’est pas reconnu par l’outil</span><span class="sxs-lookup"><span data-stu-id="667c7-166">The drive isn’t recognized by the tool</span></span> | <span data-ttu-id="667c7-167">Vérifiez que l’interface SSD surface Hub est énumérée comme un lecteur Lite-on, «LITEON L-128V2S USB».</span><span class="sxs-lookup"><span data-stu-id="667c7-167">Verify that the Surface Hub SSD is enumerated as a Lite-On drive, "LITEON L CH-128V2S USB Device".</span></span>  <span data-ttu-id="667c7-168">Si le lecteur est reconnu comme un autre périphérique appelé, votre câble actuel n’est pas compatible.</span><span class="sxs-lookup"><span data-stu-id="667c7-168">If the drive is recognized as another named device, your current cable isn’t compatible.</span></span> <span data-ttu-id="667c7-169">Essayez un autre câble ou un câble testé indiqué ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="667c7-169">Try another cable or one of the tested cable listed above.</span></span>
<span data-ttu-id="667c7-170">Erreur:-2147024809</span><span class="sxs-lookup"><span data-stu-id="667c7-170">Error: -2147024809</span></span> | <span data-ttu-id="667c7-171">Ouvrez le gestionnaire de disques et supprimez les partitions sur le lecteur surface Hub.</span><span class="sxs-lookup"><span data-stu-id="667c7-171">Open Disk Manager and remove the partitions on the Surface Hub drive.</span></span>  <span data-ttu-id="667c7-172">Déconnectez-vous et reconnectez-vous à l’ordinateur hôte.</span><span class="sxs-lookup"><span data-stu-id="667c7-172">Disconnect and reconnect the drive to the host machine.</span></span> <span data-ttu-id="667c7-173">Redémarrez de nouveau l’outil d’imagerie.</span><span class="sxs-lookup"><span data-stu-id="667c7-173">Restart the imaging tool again.</span></span>

<span data-ttu-id="667c7-174">Si l’outil ne parvenez pas à réimagingr votre lecteur, contactez le [support surface Hub](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support).</span><span class="sxs-lookup"><span data-stu-id="667c7-174">If the tool is unsuccessful in reimaging your drive, please contact [Surface Hub Support](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support).</span></span>
