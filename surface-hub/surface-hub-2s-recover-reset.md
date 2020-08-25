---
title: Réinitialiser et récupérer des surface Hub 2
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
ms.openlocfilehash: 7d79fab22b62e6ef29832be6241c484e9caf72e0
ms.sourcegitcommit: 537fa38bdd21fcd679af0764e734f4b8efb6a03f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/25/2020
ms.locfileid: "10959946"
---
# <span data-ttu-id="615e8-104">Réinitialiser et récupérer des surface Hub 2</span><span class="sxs-lookup"><span data-stu-id="615e8-104">Reset and recovery for Surface Hub 2S</span></span>

<span data-ttu-id="615e8-105">Si vous rencontrez des problèmes avec l’interface de surface Hub 2, vous pouvez rétablir les paramètres d’usine de l’appareil ou le restaurer à l’aide d’un lecteur USB.</span><span class="sxs-lookup"><span data-stu-id="615e8-105">If you encounter problems with Surface Hub 2S, you can reset the device to factory settings or restore by using a USB drive.</span></span>

<span data-ttu-id="615e8-106">Pour commencer, connectez-vous à surface Hub 2 avec les informations d’identification d’administrateur, ouvrez l’application **paramètres** , sélectionnez **mettre à jour & sécurité**, puis sélectionnez **récupération**.</span><span class="sxs-lookup"><span data-stu-id="615e8-106">To begin, sign in to Surface Hub 2S with admin credentials, open the **Settings** app, select **Update & security**, and then select **Recovery**.</span></span>

## <span data-ttu-id="615e8-107">Réinitialisez l’appareil</span><span class="sxs-lookup"><span data-stu-id="615e8-107">Reset the device</span></span>

1. <span data-ttu-id="615e8-108">Pour réinitialiser l’appareil, sélectionnez **commencer**.</span><span class="sxs-lookup"><span data-stu-id="615e8-108">To reset the device, select **Get Started**.</span></span>

2. <span data-ttu-id="615e8-109">Lorsque la fenêtre **prêt pour la réinitialisation de l’appareil** s’affiche, sélectionnez **Réinitialiser**.</span><span class="sxs-lookup"><span data-stu-id="615e8-109">When the **Ready to reset this device** window appears, select **Reset**.</span></span> 
  
   > [!NOTE]
   > <span data-ttu-id="615e8-110">Surface Hub 2 réinstalle le système d’exploitation à partir de la partition de récupération.</span><span class="sxs-lookup"><span data-stu-id="615e8-110">Surface Hub 2S reinstalls the operating system from the recovery partition.</span></span> <span data-ttu-id="615e8-111">L’opération risque de prendre jusqu’à une heure.</span><span class="sxs-lookup"><span data-stu-id="615e8-111">This may take up to one hour to complete.</span></span>
  
3. <span data-ttu-id="615e8-112">Pour reconfigurer l’appareil, exécutez le programme de configuration pour la première fois.</span><span class="sxs-lookup"><span data-stu-id="615e8-112">To reconfigure the device, run the first-time Setup program.</span></span>

4. <span data-ttu-id="615e8-113">Si vous gérez l’appareil à l’aide de Microsoft Intune ou d’une autre solution de gestion des appareils mobiles, retirez et supprimez l’enregistrement précédent, puis réinscrivez le nouvel appareil.</span><span class="sxs-lookup"><span data-stu-id="615e8-113">If you manage the device using Microsoft Intune or another mobile device management solution, retire and delete the previous record, and then re-enroll the new device.</span></span> <span data-ttu-id="615e8-114">Pour plus d’informations, reportez-vous [à la section supprimer des appareils à l’aide de l’effet de réinitialisation](https://docs.microsoft.com/intune/devices-wipe)</span><span class="sxs-lookup"><span data-stu-id="615e8-114">For more information, see [Remove devices by using wipe, retire, or manually unenrolling the device](https://docs.microsoft.com/intune/devices-wipe).</span></span>

> [!div class="mx-imgBorder"]
> ![\* Reset et Recovery for surface Hub 2 \*](images/sh2-reset.png)
<br/>*<span data-ttu-id="615e8-116">Figure1.</span><span class="sxs-lookup"><span data-stu-id="615e8-116">Figure 1.</span></span> <span data-ttu-id="615e8-117">Réinitialiser et récupérer des surface Hub 2</span><span class="sxs-lookup"><span data-stu-id="615e8-117">Reset and recovery for Surface Hub 2S</span></span>* 

## <span data-ttu-id="615e8-118">Récupérer des surface Hub 2 à l’aide d’un lecteur de récupération USB</span><span class="sxs-lookup"><span data-stu-id="615e8-118">Recover Surface Hub 2S by using a USB recovery drive</span></span>

<span data-ttu-id="615e8-119">Nouveauté de surface Hub 2, vous pouvez maintenant réinstaller l’appareil à l’aide d’une image de récupération.</span><span class="sxs-lookup"><span data-stu-id="615e8-119">New in Surface Hub 2S, you can now reinstall the device by using a recovery image.</span></span>

### <span data-ttu-id="615e8-120">Restauration à partir d’un lecteur USB</span><span class="sxs-lookup"><span data-stu-id="615e8-120">Recovery from a USB drive</span></span>

<span data-ttu-id="615e8-121">À l’aide de surface Hub 2, vous pouvez réinstaller l’appareil à l’aide d’une image de récupération.</span><span class="sxs-lookup"><span data-stu-id="615e8-121">Using Surface Hub 2S, you can reinstall the device by using a recovery image.</span></span> <span data-ttu-id="615e8-122">En procédant ainsi, vous pouvez réinstaller l’appareil sur les paramètres d’usine si vous avez perdu la clé BitLocker ou si vous n’avez plus d’informations d’identification d’administrateur dans l’application paramètres.</span><span class="sxs-lookup"><span data-stu-id="615e8-122">By doing this, you can reinstall the device to the factory settings if you lost the BitLocker key, or if you no longer have admin credentials to the Settings app.</span></span>

>[!NOTE]
><span data-ttu-id="615e8-123">Utilisez un lecteur USB 3,0 avec 8 Go ou 16 Go d’espace de stockage, formaté en FAT32.</span><span class="sxs-lookup"><span data-stu-id="615e8-123">Use a USB 3.0 drive with 8 GB or 16 GB of storage, formatted as FAT32.</span></span>

1. <span data-ttu-id="615e8-124">À partir d’un autre PC, téléchargez l’image de récupération de fichier. zip à partir du [site Web de récupération de surface](https://support.microsoft.com/surfacerecoveryimage?devicetype=surfacehub2s) , puis revenez à ces instructions.</span><span class="sxs-lookup"><span data-stu-id="615e8-124">From a separate PC, download the .zip file recovery image from the [Surface Recovery website](https://support.microsoft.com/surfacerecoveryimage?devicetype=surfacehub2s) and then return to these instructions.</span></span> 

1. <span data-ttu-id="615e8-125">Décompressez le fichier téléchargé sur la racine du lecteur USB.</span><span class="sxs-lookup"><span data-stu-id="615e8-125">Unzip the downloaded file onto the root of the USB drive.</span></span>  

1. <span data-ttu-id="615e8-126">Connectez le lecteur USB à tout port USB-C ou USB-Port sur surface Hub 2.</span><span class="sxs-lookup"><span data-stu-id="615e8-126">Connect the USB drive to any USB-C or USB-A port on Surface Hub 2S.</span></span>

1. <span data-ttu-id="615e8-127">Éteindre le périphérique:</span><span class="sxs-lookup"><span data-stu-id="615e8-127">Turn off the device:</span></span>

   1. <span data-ttu-id="615e8-128">Tout en appuyant sur le bouton volume haut, appuyez sur le bouton d’alimentation.</span><span class="sxs-lookup"><span data-stu-id="615e8-128">While pressing the Volume up button, press the Power button.</span></span>
   1. <span data-ttu-id="615e8-129">Continuez à appuyer sur les deux boutons jusqu’à ce que vous voyiez le logo Windows.</span><span class="sxs-lookup"><span data-stu-id="615e8-129">Keep pressing both buttons until you see the Windows logo.</span></span>
   1. <span data-ttu-id="615e8-130">Relâchez le bouton d’alimentation tout en maintenant le bouton volume enfoncé jusqu’à ce que l’interface utilisateur de l’installation démarre.</span><span class="sxs-lookup"><span data-stu-id="615e8-130">Release the Power button but continue to hold the Volume up button until the Install UI begins.</span></span>

   ![\* Utiliser le volume et les boutons d’alimentation pour démarrer la restauration \*](images/sh2-keypad.png) <br>
   **<span data-ttu-id="615e8-132">Figure2.</span><span class="sxs-lookup"><span data-stu-id="615e8-132">Figure 2.</span></span> <span data-ttu-id="615e8-133">Boutons volume et alimentation</span><span class="sxs-lookup"><span data-stu-id="615e8-133">Volume and Power buttons</span></span>**

1. <span data-ttu-id="615e8-134">Dans l’écran de sélection de la langue, sélectionnez la langue d’affichage de votre surface Hub 2.</span><span class="sxs-lookup"><span data-stu-id="615e8-134">On the language selection screen, select the display language for your Surface Hub 2S.</span></span>

1. <span data-ttu-id="615e8-135">Sélectionnez **récupérer à partir d’un disque** , **Nettoyez entièrement le lecteur**, puis sélectionnez **récupérer**.</span><span class="sxs-lookup"><span data-stu-id="615e8-135">Select **Recover from a drive** and **Fully clean the drive**, and then select **Recover**.</span></span> <span data-ttu-id="615e8-136">Si vous êtes invité à entrer une clé BitLocker, sélectionnez **ignorer ce lecteur**.</span><span class="sxs-lookup"><span data-stu-id="615e8-136">If you're prompted for a BitLocker key, select **Skip this drive**.</span></span> <span data-ttu-id="615e8-137">Surface Hub 2 réamorce plusieurs fois et nécessite environ 30 minutes pour terminer le processus de récupération.</span><span class="sxs-lookup"><span data-stu-id="615e8-137">Surface Hub 2S reboots several times and takes approximately 30 minutes to complete the recovery process.</span></span>

<span data-ttu-id="615e8-138">Lorsque l’écran de configuration pour la première fois apparaît, supprimez le lecteur USB.</span><span class="sxs-lookup"><span data-stu-id="615e8-138">When the first-time setup screen appears, remove the USB drive.</span></span>

## <span data-ttu-id="615e8-139">Contacter le support</span><span class="sxs-lookup"><span data-stu-id="615e8-139">Contact Support</span></span>

<span data-ttu-id="615e8-140">Si vous avez des questions ou si vous avez besoin d’aide, vous pouvez [créer une demande de support](https://support.microsoft.com/supportforbusiness/productselection).</span><span class="sxs-lookup"><span data-stu-id="615e8-140">If you have questions or need help, you can [create a support request](https://support.microsoft.com/supportforbusiness/productselection).</span></span>
