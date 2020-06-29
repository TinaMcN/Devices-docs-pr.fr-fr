---
title: Paramètre de limite de batterie (surface)
description: La limite de batterie est un paramètre UEFI qui modifie le mode de charge de la batterie de l’appareil surface et peut prolonger sa longévité.
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.reviewer: jesko
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
manager: laurawi
audience: itpro
ms.date: 5/06/2020
ms.openlocfilehash: 927f00681bd5756f380025adf00a08a34a3f411f
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10833509"
---
# <span data-ttu-id="c28c2-103">Paramètre de limite de la batterie</span><span class="sxs-lookup"><span data-stu-id="c28c2-103">Battery Limit setting</span></span>

<span data-ttu-id="c28c2-104">L’option de limite de batterie est un paramètre UEFI qui modifie le mode de charge de la batterie de l’appareil surface et peut prolonger sa longévité.</span><span class="sxs-lookup"><span data-stu-id="c28c2-104">Battery Limit option is a UEFI setting that changes how the Surface device battery is charged and may prolong its longevity.</span></span> <span data-ttu-id="c28c2-105">Ce paramètre est recommandé dans les cas où l’appareil est continuellement connecté à la puissance, par exemple lorsque les appareils sont intégrés dans les solutions Kiosk.</span><span class="sxs-lookup"><span data-stu-id="c28c2-105">This setting is recommended in  cases  in which the device is continuously connected to power, for example when devices are integrated into kiosk solutions.</span></span>  

## <span data-ttu-id="c28c2-106">Fonctionnement de la limitation de batterie</span><span class="sxs-lookup"><span data-stu-id="c28c2-106">How Battery Limit works</span></span>

<span data-ttu-id="c28c2-107">La configuration de l’appareil sur la limite des batteries a pour changement le protocole pour la charge de la batterie de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="c28c2-107">Setting the device on Battery Limit changes the protocol for charging the device battery.</span></span> <span data-ttu-id="c28c2-108">Lorsque la limite de batterie est activée, le coût de la batterie est limité à 50% de la capacité maximale.</span><span class="sxs-lookup"><span data-stu-id="c28c2-108">When Battery Limit is enabled, the battery charge will be limited to 50% of its maximum capacity.</span></span> <span data-ttu-id="c28c2-109">Le niveau de charge signalé dans Windows reflétera cette limite.</span><span class="sxs-lookup"><span data-stu-id="c28c2-109">The charge level reported in Windows will reflect this limit.</span></span> <span data-ttu-id="c28c2-110">Par conséquent, la batterie sera débitée de 50% et ne sera pas facturée au-delà de cette limite.</span><span class="sxs-lookup"><span data-stu-id="c28c2-110">Therefore, it will show that the battery is charged up to 50% and will not charge beyond  this limit.</span></span> <span data-ttu-id="c28c2-111">Si vous activez le nombre maximal de batteries alors que l’appareil est supérieur à 50%, l’icône de batterie indique que l’appareil est branché, mais qu’il est en cours de rejet jusqu’à 50% de la capacité de chargement maximale.</span><span class="sxs-lookup"><span data-stu-id="c28c2-111">If you enable Battery Limit while the device is above 50% charge, the Battery icon will show that the device is plugged in but discharging until the device reaches 50% of its maximum charge capacity.</span></span>  

## <span data-ttu-id="c28c2-112">Appareils pris en charge</span><span class="sxs-lookup"><span data-stu-id="c28c2-112">Supported devices</span></span>
<span data-ttu-id="c28c2-113">Le paramètre UEFI de limitation de batterie est intégré aux périphériques de surface les plus récents, y compris surface Pro 7 et surface Laptop 3.</span><span class="sxs-lookup"><span data-stu-id="c28c2-113">The Battery Limit UEFI setting is built into the latest Surface devices including Surface Pro 7 and Surface Laptop 3.</span></span> <span data-ttu-id="c28c2-114">Les appareils antérieurs nécessitent une [mise à jour de microprogramme de surface UEFI](manage-surface-driver-and-firmware-updates.md), disponible via Windows Update ou via le pilote msi et des packages de microprogramme sur le [site de support surface](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware-for-surface).</span><span class="sxs-lookup"><span data-stu-id="c28c2-114">Earlier devices require a [Surface UEFI firmware update](manage-surface-driver-and-firmware-updates.md), available through Windows Update or via the MSI driver and firmware packages on the [Surface Support site](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware-for-surface).</span></span> <span data-ttu-id="c28c2-115">Cochez la case [activer le «plafond de batterie» pour les appareils surface qui doivent être branchés pour des périodes de temps longues](https://support.microsoft.com/help/4464941) pour la version UEFI de surface spécifique requise pour chaque appareil pris en charge.</span><span class="sxs-lookup"><span data-stu-id="c28c2-115">Check [Enable "Battery Limit" for Surface devices that have to be plugged in for extended periods of time](https://support.microsoft.com/help/4464941) for the specific Surface UEFI version required for each supported device.</span></span> 

## <span data-ttu-id="c28c2-116">Activation de la limite de batterie dans surface UEFI (surface Pro 4 et versions ultérieures)</span><span class="sxs-lookup"><span data-stu-id="c28c2-116">Enabling Battery Limit in Surface UEFI (Surface Pro 4 and later)</span></span>

<span data-ttu-id="c28c2-117">Ce paramètre peut être configuré en démarrant en surface UEFI (**Power + vol haut** lors de l’activation de l’appareil).</span><span class="sxs-lookup"><span data-stu-id="c28c2-117">The Surface UEFI Battery Limit setting can be configured by booting into Surface UEFI (**Power + Vol Up** when turning on the device).</span></span> <span data-ttu-id="c28c2-118">Sélectionnez **configuration de démarrage**, puis, sous **Options avancées**, **activez activer le mode de limite de batterie** sur **activé**.</span><span class="sxs-lookup"><span data-stu-id="c28c2-118">Choose **boot configuration**, and then, under **Advanced Options**, toggle **Enable Battery Limit Mode** to **On**.</span></span>  

![Capture d’écran des options avancées](images/enable-bl.png) 

## <span data-ttu-id="c28c2-120">Activation de la limitation de batteries dans surface Go et surface Go 2</span><span class="sxs-lookup"><span data-stu-id="c28c2-120">Enabling battery limit on Surface Go and Surface Go 2</span></span>
<span data-ttu-id="c28c2-121">Le paramètre de limite de batterie de surface peut être configuré en démarrant en surface UEFI (**Power + vol vers le haut** lors de l’activation de l’appareil).</span><span class="sxs-lookup"><span data-stu-id="c28c2-121">The Surface Battery Limit setting can be configured by booting into Surface UEFI (**Power + Vol Up** when turning on the device).</span></span> <span data-ttu-id="c28c2-122">Sélectionnez **configuration de démarrage**, puis, sous **mode kiosque**, déplacez le curseur vers la droite pour définir le seuil de batterie sur **activé**.</span><span class="sxs-lookup"><span data-stu-id="c28c2-122">Choose **boot configuration**, and then, under **Kiosk Mode**, move the slider to the right to set Battery Limit to **Enabled**.</span></span>  

![Capture d’écran de la limite de batterie du mode kiosque dans surface Go](images/go-batterylimit.png) 

## <span data-ttu-id="c28c2-124">Activation de la limite de batterie dans surface UEFI (surface Pro 3)</span><span class="sxs-lookup"><span data-stu-id="c28c2-124">Enabling Battery Limit in Surface UEFI (Surface Pro 3)</span></span>

<span data-ttu-id="c28c2-125">Ce paramètre peut être configuré en démarrant en surface UEFI (**Power + vol haut** lors de l’activation de l’appareil).</span><span class="sxs-lookup"><span data-stu-id="c28c2-125">The Surface UEFI Battery Limit setting can be configured by booting into Surface UEFI (**Power + Vol Up** when turning on the device).</span></span> <span data-ttu-id="c28c2-126">Cliquez sur **mode plein écran**, sélectionnez **limite de batterie**, puis **activé**.</span><span class="sxs-lookup"><span data-stu-id="c28c2-126">Choose **Kiosk Mode**, select **Battery Limit**, and then choose **Enabled**.</span></span>

![Capture d’écran des options avancées](images/enable-bl-sp3.png) 

![Capture d’écran des options avancées](images/enable-bl-sp3-2.png) 

## <span data-ttu-id="c28c2-129">Activation d’une limite de batterie à l’aide de scripts PowerShell du microprogramme de surface Management SEMM (surface Management Mode) ou de surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="c28c2-129">Enabling Battery Limit using Surface Enterprise Management Mode (SEMM) or Surface Pro 3 firmware PowerShell scripts</span></span>

<span data-ttu-id="c28c2-130">Le seuil de batterie de surface UEFI peut également être configuré via les méthodes suivantes:</span><span class="sxs-lookup"><span data-stu-id="c28c2-130">The Surface UEFI battery limit is also available for configuration via the following methods:</span></span>

- <span data-ttu-id="c28c2-131">Surface Pro 4 et version ultérieure</span><span class="sxs-lookup"><span data-stu-id="c28c2-131">Surface Pro 4 and later</span></span> 
    - [<span data-ttu-id="c28c2-132">Configurateur Microsoft surface UEFI</span><span class="sxs-lookup"><span data-stu-id="c28c2-132">Microsoft Surface UEFI Configurator</span></span>](https://docs.microsoft.com/surface/surface-enterprise-management-mode)  
    - <span data-ttu-id="c28c2-133">Scripts PowerShell de surface UEFI Manager (SEMM_Powershell.zip) dans les [Outils surface pour le téléchargement](https://www.microsoft.com/download/details.aspx?id=46703)</span><span class="sxs-lookup"><span data-stu-id="c28c2-133">Surface UEFI Manager Powershell scripts (SEMM_Powershell.zip) in the [Surface Tools for IT downloads](https://www.microsoft.com/download/details.aspx?id=46703)</span></span>
- <span data-ttu-id="c28c2-134">Surface Pro3</span><span class="sxs-lookup"><span data-stu-id="c28c2-134">Surface Pro 3</span></span> 
    - [<span data-ttu-id="c28c2-135">SP3_Firmware_Powershell_Scripts.zip</span><span class="sxs-lookup"><span data-stu-id="c28c2-135">SP3_Firmware_Powershell_Scripts.zip</span></span>](https://www.microsoft.com/download/details.aspx?id=46703)

### <span data-ttu-id="c28c2-136">Utilisation du configurateur Microsoft surface UEFI</span><span class="sxs-lookup"><span data-stu-id="c28c2-136">Using Microsoft Surface UEFI Configurator</span></span>

<span data-ttu-id="c28c2-137">Pour configurer le mode de limitation de batterie, définissez le paramètre **Kiosk Overrides** sur la page configuration **avancée des paramètres** dans SEMM (surface Pro 4 et versions ultérieures).</span><span class="sxs-lookup"><span data-stu-id="c28c2-137">To configure Battery Limit mode, set the **Kiosk Overrides** setting on the **Advanced Settings** configuration page in SEMM (Surface Pro 4 and later).</span></span>

![Capture d’écran des paramètres avancés](images/semm-bl.png)

### <span data-ttu-id="c28c2-139">Utilisation de scripts PowerShell de surface UEFI Manager</span><span class="sxs-lookup"><span data-stu-id="c28c2-139">Using Surface UEFI Manager PowerShell scripts</span></span>

<span data-ttu-id="c28c2-140">La fonctionnalité de limite de batterie est contrôlée via le paramètre suivant:</span><span class="sxs-lookup"><span data-stu-id="c28c2-140">The battery limit feature is controlled via the following setting:</span></span>  

`407 = Battery Profile`

<span data-ttu-id="c28c2-141">**Description**: schéma de gestion actif pour le modèle d’utilisation de la batterie</span><span class="sxs-lookup"><span data-stu-id="c28c2-141">**Description**:  Active management scheme for battery usage pattern</span></span>

<span data-ttu-id="c28c2-142">**Par défaut**:</span><span class="sxs-lookup"><span data-stu-id="c28c2-142">**Default**:</span></span>  `0` 

<span data-ttu-id="c28c2-143">Définissez cette valeur sur `1` pour activer le nombre maximal de batteries.</span><span class="sxs-lookup"><span data-stu-id="c28c2-143">Set this to `1` to enable Battery Limit.</span></span>

### <span data-ttu-id="c28c2-144">Utilisation des outils de microprogramme de surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="c28c2-144">Using Surface Pro 3 firmware tools</span></span>

<span data-ttu-id="c28c2-145">La fonctionnalité de limite de batterie est contrôlée via le paramètre suivant:</span><span class="sxs-lookup"><span data-stu-id="c28c2-145">The battery limit feature is controlled via the following setting:</span></span>  

<span data-ttu-id="c28c2-146">**Nom**: BatteryLimitEnable</span><span class="sxs-lookup"><span data-stu-id="c28c2-146">**Name**: BatteryLimitEnable</span></span>

<span data-ttu-id="c28c2-147">**Description**: BatteryLimit</span><span class="sxs-lookup"><span data-stu-id="c28c2-147">**Description**:  BatteryLimit</span></span>

<span data-ttu-id="c28c2-148">**Valeur actuelle**:</span><span class="sxs-lookup"><span data-stu-id="c28c2-148">**Current Value**:</span></span>  `0` 

<span data-ttu-id="c28c2-149">**Valeur par défaut**:</span><span class="sxs-lookup"><span data-stu-id="c28c2-149">**Default Value**:</span></span> `0`

<span data-ttu-id="c28c2-150">**Valeur proposée**:</span><span class="sxs-lookup"><span data-stu-id="c28c2-150">**Proposed Value**:</span></span> `0` 

<span data-ttu-id="c28c2-151">Définissez cette valeur sur `1` pour activer le nombre maximal de batteries.</span><span class="sxs-lookup"><span data-stu-id="c28c2-151">Set this to `1` to enable Battery Limit.</span></span>

>[!NOTE]
><span data-ttu-id="c28c2-152">Pour configurer ce paramètre, vous devez utiliser [SP3_Firmware_Powershell_Scripts.zip](https://www.microsoft.com/download/details.aspx?id=46703).</span><span class="sxs-lookup"><span data-stu-id="c28c2-152">To configure this setting, you must use [SP3_Firmware_Powershell_Scripts.zip](https://www.microsoft.com/download/details.aspx?id=46703).</span></span> 

