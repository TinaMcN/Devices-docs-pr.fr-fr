---
title: Réinitialisation et récupération pour Surface Hub 2S
description: Découvrez comment récupérer et réinitialiser surface Hub 2S.
keywords: séparer les valeurs par des virgules
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 12/05/2019
ms.localizationpriority: Medium
ms.openlocfilehash: 88f5d912f7505aecaa5bd7ba659acab2d6c4fa1a
ms.sourcegitcommit: 25b8d880c6438f94b008f47b4fecc3aa4c473e85
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/28/2021
ms.locfileid: "11304807"
---
# <span data-ttu-id="26ad8-104">Réinitialisation et récupération pour Surface Hub 2S</span><span class="sxs-lookup"><span data-stu-id="26ad8-104">Reset and recovery for Surface Hub 2S</span></span>

<span data-ttu-id="26ad8-105">Si vous rencontrez des problèmes avec Surface Hub 2S, vous pouvez rétablir les paramètres d’usine ou restaurer l’appareil à l’aide d’un lecteur USB.</span><span class="sxs-lookup"><span data-stu-id="26ad8-105">If you encounter problems with Surface Hub 2S, you can reset the device to factory settings or restore by using a USB drive.</span></span>

<span data-ttu-id="26ad8-106">Pour commencer, connectez-vous au Surface Hub 2S avec les informations d’identification d’administrateur, ouvrez l’application **Paramètres,** sélectionnez Mettre à jour **& sécurité,** puis sélectionnez **Récupération.**</span><span class="sxs-lookup"><span data-stu-id="26ad8-106">To begin, sign in to Surface Hub 2S with admin credentials, open the **Settings** app, select **Update & security**, and then select **Recovery**.</span></span>

## <span data-ttu-id="26ad8-107">Réinitialisez l’appareil</span><span class="sxs-lookup"><span data-stu-id="26ad8-107">Reset the device</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="26ad8-108">Assurez-vous que votre clé BitLocker est disponible avant de réinitialiser l’appareil, car vous y serez invité ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="26ad8-108">Ensure that you have your BitLocker key available before resetting the device, as you will be prompted for it later.</span></span> <span data-ttu-id="26ad8-109">Pour plus d’informations, voir [Enregistrer votre clé BitLocker.](save-bitlocker-key-surface-hub.md)</span><span class="sxs-lookup"><span data-stu-id="26ad8-109">To learn more, see [Save your BitLocker key](save-bitlocker-key-surface-hub.md).</span></span>

1. <span data-ttu-id="26ad8-110">Pour réinitialiser l’appareil, **sélectionnez Démarrer.**</span><span class="sxs-lookup"><span data-stu-id="26ad8-110">To reset the device, select **Get Started**.</span></span>

2. <span data-ttu-id="26ad8-111">Lorsque la fenêtre **Prêt à réinitialiser cet appareil** s’affiche, sélectionnez **Réinitialiser.**</span><span class="sxs-lookup"><span data-stu-id="26ad8-111">When the **Ready to reset this device** window appears, select **Reset**.</span></span> 
  
   > [!IMPORTANT]
   > <span data-ttu-id="26ad8-112">Lorsque le Hub redémarre sur la partition de récupération, il vous invite à entrer la clé BitLocker.</span><span class="sxs-lookup"><span data-stu-id="26ad8-112">When the Hub reboots to the recovery partition, it will prompt you to enter the BitLocker key.</span></span> <span data-ttu-id="26ad8-113">Ignorer cette invite entraîne l’échec de la réinitialisation.</span><span class="sxs-lookup"><span data-stu-id="26ad8-113">Skipping that prompt will cause reset to fail.</span></span> <span data-ttu-id="26ad8-114">Une fois que vous avez entré la clé BitLocker, le Hub réinstalle le système d’exploitation à partir de la partition de récupération.</span><span class="sxs-lookup"><span data-stu-id="26ad8-114">Once you enter the BitLocker key the Hub reinstalls the operating system from the recovery partition.</span></span> <span data-ttu-id="26ad8-115">Cela peut prendre jusqu’à une heure.</span><span class="sxs-lookup"><span data-stu-id="26ad8-115">This may take up to one hour to complete.</span></span>
  
3. <span data-ttu-id="26ad8-116">Pour reconfigurer l’appareil, exécutez le programme d’installation pour la première fois.</span><span class="sxs-lookup"><span data-stu-id="26ad8-116">To reconfigure the device, run the first-time Setup program.</span></span>

4. <span data-ttu-id="26ad8-117">Si vous gérez l’appareil à l’aide de Microsoft Intune ou d’une autre solution de gestion des appareils mobiles, retirez et supprimez l’enregistrement précédent, puis ré-inscrivez le nouvel appareil.</span><span class="sxs-lookup"><span data-stu-id="26ad8-117">If you manage the device using Microsoft Intune or another mobile device management solution, retire and delete the previous record, and then re-enroll the new device.</span></span> <span data-ttu-id="26ad8-118">Pour plus d’informations, voir Supprimer des appareils à l’aide de l’effacement, de la suppression ou de la [désinscrire manuellement de l’appareil.](https://docs.microsoft.com/intune/devices-wipe)</span><span class="sxs-lookup"><span data-stu-id="26ad8-118">For more information, see [Remove devices by using wipe, retire, or manually unenrolling the device](https://docs.microsoft.com/intune/devices-wipe).</span></span>

   > [!div class="mx-imgBorder"]
   > ![*Réinitialiser et récupérer pour Surface Hub 2S*](images/sh2-reset.png)
   <br/>*<span data-ttu-id="26ad8-120">Figure1.</span><span class="sxs-lookup"><span data-stu-id="26ad8-120">Figure 1.</span></span> <span data-ttu-id="26ad8-121">Réinitialisation et récupération pour Surface Hub 2S</span><span class="sxs-lookup"><span data-stu-id="26ad8-121">Reset and recovery for Surface Hub 2S</span></span>* 

## <span data-ttu-id="26ad8-122">Récupérer le Surface Hub 2S à l’aide d’un lecteur de récupération USB</span><span class="sxs-lookup"><span data-stu-id="26ad8-122">Recover Surface Hub 2S by using a USB recovery drive</span></span>

<span data-ttu-id="26ad8-123">Nouveauté du Surface Hub 2S, vous pouvez désormais réinstaller l’appareil à l’aide d’une image de récupération.</span><span class="sxs-lookup"><span data-stu-id="26ad8-123">New in Surface Hub 2S, you can now reinstall the device by using a recovery image.</span></span>

### <span data-ttu-id="26ad8-124">Récupération à partir d’un lecteur USB</span><span class="sxs-lookup"><span data-stu-id="26ad8-124">Recovery from a USB drive</span></span>

<span data-ttu-id="26ad8-125">À l’aide du Surface Hub 2S, vous pouvez réinstaller l’appareil à l’aide d’une image de récupération.</span><span class="sxs-lookup"><span data-stu-id="26ad8-125">Using Surface Hub 2S, you can reinstall the device by using a recovery image.</span></span> <span data-ttu-id="26ad8-126">En faisant cela, vous pouvez réinstaller l’appareil aux paramètres d’usine si vous avez perdu la clé BitLocker ou si vous n’avez plus d’informations d’identification d’administrateur pour l’application Paramètres.</span><span class="sxs-lookup"><span data-stu-id="26ad8-126">By doing this, you can reinstall the device to the factory settings if you lost the BitLocker key, or if you no longer have admin credentials to the Settings app.</span></span>

>[!NOTE]
><span data-ttu-id="26ad8-127">Utilisez un lecteur USB 3.0 avec 8 Go ou 16 Go de stockage, au format FAT32.</span><span class="sxs-lookup"><span data-stu-id="26ad8-127">Use a USB 3.0 drive with 8 GB or 16 GB of storage, formatted as FAT32.</span></span>

1. <span data-ttu-id="26ad8-128">À partir d’un PC distinct, téléchargez l’image de récupération de fichier .zip à partir du site web [Surface Recovery,](https://support.microsoft.com/surfacerecoveryimage?devicetype=surfacehub2s) puis revenir à ces instructions.</span><span class="sxs-lookup"><span data-stu-id="26ad8-128">From a separate PC, download the .zip file recovery image from the [Surface Recovery website](https://support.microsoft.com/surfacerecoveryimage?devicetype=surfacehub2s) and then return to these instructions.</span></span> 

1. <span data-ttu-id="26ad8-129">Dézipez le fichier téléchargé à la racine du lecteur USB.</span><span class="sxs-lookup"><span data-stu-id="26ad8-129">Unzip the downloaded file onto the root of the USB drive.</span></span>  

1. <span data-ttu-id="26ad8-130">Connectez le lecteur USB à n’importe quel port USB-C ou USB-A sur surface Hub 2S.</span><span class="sxs-lookup"><span data-stu-id="26ad8-130">Connect the USB drive to any USB-C or USB-A port on Surface Hub 2S.</span></span>

1. <span data-ttu-id="26ad8-131">Désactiver l’appareil :</span><span class="sxs-lookup"><span data-stu-id="26ad8-131">Turn off the device:</span></span>

   1. <span data-ttu-id="26ad8-132">Tout en appuyant sur le bouton Descendre le volume, appuyez sur le bouton d’alimentation.</span><span class="sxs-lookup"><span data-stu-id="26ad8-132">While pressing the Volume down button, press the Power button.</span></span>
   1. <span data-ttu-id="26ad8-133">Continuez à appuyer sur les deux boutons jusqu’à ce que le logo Windows s’affiche.</span><span class="sxs-lookup"><span data-stu-id="26ad8-133">Keep pressing both buttons until you see the Windows logo.</span></span>
   1. <span data-ttu-id="26ad8-134">Relâchez le bouton d’alimentation, mais maintenez le bouton Descendre le volume jusqu’à ce que l’interface utilisateur d’installation commence.</span><span class="sxs-lookup"><span data-stu-id="26ad8-134">Release the Power button but continue to hold the Volume down button until the Install UI begins.</span></span>

      ![*Use Volume down and power buttons to initiate recovery*](images/sh2-keypad.png)
      <br>*<span data-ttu-id="26ad8-136">Figure2.</span><span class="sxs-lookup"><span data-stu-id="26ad8-136">Figure 2.</span></span> <span data-ttu-id="26ad8-137">Boutons Volume et Alimentation</span><span class="sxs-lookup"><span data-stu-id="26ad8-137">Volume and Power buttons</span></span>*

1. <span data-ttu-id="26ad8-138">Dans l’écran de sélection de la langue, sélectionnez la langue d’affichage de votre Surface Hub 2S.</span><span class="sxs-lookup"><span data-stu-id="26ad8-138">On the language selection screen, select the display language for your Surface Hub 2S.</span></span>

1. <span data-ttu-id="26ad8-139">Sélectionnez **Récupérer à partir d’un lecteur** et **nettoyez entièrement le lecteur,** puis sélectionnez **Récupérer.**</span><span class="sxs-lookup"><span data-stu-id="26ad8-139">Select **Recover from a drive** and **Fully clean the drive**, and then select **Recover**.</span></span> <span data-ttu-id="26ad8-140">Si vous êtes invité à obtenir une clé BitLocker, **sélectionnez Ignorer ce lecteur.**</span><span class="sxs-lookup"><span data-stu-id="26ad8-140">If you're prompted for a BitLocker key, select **Skip this drive**.</span></span> <span data-ttu-id="26ad8-141">Surface Hub 2S redémarre plusieurs fois et prend environ 30 minutes pour terminer le processus de récupération.</span><span class="sxs-lookup"><span data-stu-id="26ad8-141">Surface Hub 2S reboots several times and takes approximately 30 minutes to complete the recovery process.</span></span>

<span data-ttu-id="26ad8-142">Lorsque l’écran de configuration s’affiche pour la première fois, supprimez le lecteur USB.</span><span class="sxs-lookup"><span data-stu-id="26ad8-142">When the first-time setup screen appears, remove the USB drive.</span></span>

## <span data-ttu-id="26ad8-143">Contacter le support</span><span class="sxs-lookup"><span data-stu-id="26ad8-143">Contact Support</span></span>

<span data-ttu-id="26ad8-144">Si vous avez des questions ou avez besoin d’aide, vous pouvez [créer une demande de support.](https://support.microsoft.com/supportforbusiness/productselection)</span><span class="sxs-lookup"><span data-stu-id="26ad8-144">If you have questions or need help, you can [create a support request](https://support.microsoft.com/supportforbusiness/productselection).</span></span>
