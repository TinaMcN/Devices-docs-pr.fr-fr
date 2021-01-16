---
title: Paramètre de limite de batterie (Surface)
description: La limite de batterie est un paramètre UEFI qui modifie la façon dont la batterie de l’appareil Surface est chargée et peut prolonger sa long terme.
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
ms.date: 1/15/2021
ms.openlocfilehash: 8ce1dcfc621a547aca9ca1db322f3ed2ce082728
ms.sourcegitcommit: 1b86286bd13b13749ddbf454ae78d9a24fec44ee
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "11271141"
---
# <span data-ttu-id="b7132-103">Paramètre de limite de la batterie</span><span class="sxs-lookup"><span data-stu-id="b7132-103">Battery Limit setting</span></span>

<span data-ttu-id="b7132-104">L’option Limite de batterie est un paramètre UEFI qui modifie la façon dont la batterie de l’appareil Surface est chargée et peut prolonger sa long terme.</span><span class="sxs-lookup"><span data-stu-id="b7132-104">Battery Limit option is a UEFI setting that changes how the Surface device battery is charged and may prolong its longevity.</span></span> <span data-ttu-id="b7132-105">Ce paramètre est recommandé dans les cas où l’appareil est connecté en permanence à l’alimentation, par exemple lorsque les appareils sont intégrés aux solutions kiosque.</span><span class="sxs-lookup"><span data-stu-id="b7132-105">This setting is recommended in  cases  in which the device is continuously connected to power, for example when devices are integrated into kiosk solutions.</span></span>  

## <span data-ttu-id="b7132-106">Fonctionnement de la limite de batterie</span><span class="sxs-lookup"><span data-stu-id="b7132-106">How Battery Limit works</span></span>

<span data-ttu-id="b7132-107">La définition de l’appareil sur la limite de batterie modifie le protocole de chargement de la batterie de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="b7132-107">Setting the device on Battery Limit changes the protocol for charging the device battery.</span></span> <span data-ttu-id="b7132-108">Lorsque la limite de batterie est activée, la charge de la batterie est limitée à 50 % de sa capacité maximale.</span><span class="sxs-lookup"><span data-stu-id="b7132-108">When Battery Limit is enabled, the battery charge will be limited to 50% of its maximum capacity.</span></span> <span data-ttu-id="b7132-109">Le niveau de charge signalé dans Windows reflètera cette limite.</span><span class="sxs-lookup"><span data-stu-id="b7132-109">The charge level reported in Windows will reflect this limit.</span></span> <span data-ttu-id="b7132-110">Par conséquent, il indique que la batterie est chargée jusqu’à 50 % et qu’elle ne sera pas chargée au-delà de cette limite.</span><span class="sxs-lookup"><span data-stu-id="b7132-110">Therefore, it will show that the battery is charged up to 50% and will not charge beyond  this limit.</span></span> <span data-ttu-id="b7132-111">Si vous activez la limite de batterie alors que la charge de l’appareil est supérieure à 50 %, l’icône Batterie indique que l’appareil est branché, mais qu’il est déconnecté jusqu’à ce qu’il atteigne 50 % de sa capacité de charge maximale.</span><span class="sxs-lookup"><span data-stu-id="b7132-111">If you enable Battery Limit while the device is above 50% charge, the Battery icon will show that the device is plugged in but discharging until the device reaches 50% of its maximum charge capacity.</span></span>  

## <span data-ttu-id="b7132-112">Appareils pris en charge</span><span class="sxs-lookup"><span data-stu-id="b7132-112">Supported devices</span></span>

<span data-ttu-id="b7132-113">Le paramètre UEFI de limite de batterie est intégré aux appareils Surface les plus récents, notamment Surface Pro 7+, Surface Pro 7 et Surface Laptop 3.</span><span class="sxs-lookup"><span data-stu-id="b7132-113">The Battery Limit UEFI setting is built into the latest Surface devices including Surface Pro 7+, Surface Pro 7, and Surface Laptop 3.</span></span> <span data-ttu-id="b7132-114">Les appareils précédents nécessitent une mise à jour du microprogramme [UEFI Surface,](manage-surface-driver-and-firmware-updates.md)disponible via Windows Update ou via les packages de microprogramme et de pilote MSI sur le site de [support Surface.](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware-for-surface)</span><span class="sxs-lookup"><span data-stu-id="b7132-114">Earlier devices require a [Surface UEFI firmware update](manage-surface-driver-and-firmware-updates.md), available through Windows Update or via the MSI driver and firmware packages on the [Surface Support site](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware-for-surface).</span></span> <span data-ttu-id="b7132-115">Activez « Limite de batterie » pour les appareils Surface qui doivent être branchés pendant de [longues périodes](https://support.microsoft.com/help/4464941) pour la version UEFI Surface spécifique requise pour chaque appareil pris en charge.</span><span class="sxs-lookup"><span data-stu-id="b7132-115">Check [Enable "Battery Limit" for Surface devices that have to be plugged in for extended periods of time](https://support.microsoft.com/help/4464941) for the specific Surface UEFI version required for each supported device.</span></span> 

## <span data-ttu-id="b7132-116">Activation de la limite de batterie dans l’UEFI Surface (Surface Pro 4 et ultérieur)</span><span class="sxs-lookup"><span data-stu-id="b7132-116">Enabling Battery Limit in Surface UEFI (Surface Pro 4 and later)</span></span>

<span data-ttu-id="b7132-117">Le paramètre de limite de batterie UEFI Surface peut être configuré en délateur dans Surface UEFI **(Power + Vol Up** lors de l’alimentation de l’appareil).</span><span class="sxs-lookup"><span data-stu-id="b7132-117">The Surface UEFI Battery Limit setting can be configured by booting into Surface UEFI (**Power + Vol Up** when turning on the device).</span></span> <span data-ttu-id="b7132-118">Choisissez **la configuration de**démarrage, puis, sous Options **avancées,** basculez **Activer** le mode limite de batterie **sur Activé.**</span><span class="sxs-lookup"><span data-stu-id="b7132-118">Choose **boot configuration**, and then, under **Advanced Options**, toggle **Enable Battery Limit Mode** to **On**.</span></span>  

![Options avancées de limite de batterie](images/enable-bl.png) 

## <span data-ttu-id="b7132-120">Activation de la limite de batterie sur Surface Go et Surface Go 2</span><span class="sxs-lookup"><span data-stu-id="b7132-120">Enabling battery limit on Surface Go and Surface Go 2</span></span>
<span data-ttu-id="b7132-121">Le paramètre de limite de la batterie Surface peut être configuré en délateur dans l’UEFI Surface **(Power + Vol Up** lors de l’alimentation de l’appareil).</span><span class="sxs-lookup"><span data-stu-id="b7132-121">The Surface Battery Limit setting can be configured by booting into Surface UEFI (**Power + Vol Up** when turning on the device).</span></span> <span data-ttu-id="b7132-122">Choisissez **la configuration de**démarrage, puis, en **mode**plein écran, déplacez le curseur à droite pour définir la limite de batterie **sur Activé.**</span><span class="sxs-lookup"><span data-stu-id="b7132-122">Choose **boot configuration**, and then, under **Kiosk Mode**, move the slider to the right to set Battery Limit to **Enabled**.</span></span>  

![Limite de batterie en mode plein écran dans Surface Go](images/go-batterylimit.png) 

## <span data-ttu-id="b7132-124">Activation de la limite de batterie dans l’UEFI Surface (Surface Pro 3)</span><span class="sxs-lookup"><span data-stu-id="b7132-124">Enabling Battery Limit in Surface UEFI (Surface Pro 3)</span></span>

<span data-ttu-id="b7132-125">Le paramètre de limite de batterie UEFI Surface peut être configuré en délateur dans Surface UEFI **(Power + Vol Up** lors de l’alimentation de l’appareil).</span><span class="sxs-lookup"><span data-stu-id="b7132-125">The Surface UEFI Battery Limit setting can be configured by booting into Surface UEFI (**Power + Vol Up** when turning on the device).</span></span> <span data-ttu-id="b7132-126">Choose **Kiosk Mode**, select Battery **Limit**, and then choose **Enabled**.</span><span class="sxs-lookup"><span data-stu-id="b7132-126">Choose **Kiosk Mode**, select **Battery Limit**, and then choose **Enabled**.</span></span>

![Capture d’écran des options avancées](images/enable-bl-sp3.png) 

![Options avancées](images/enable-bl-sp3-2.png) 

## <span data-ttu-id="b7132-129">Activation de la limite de batterie à l’aide des scripts PowerShell du microprogramme Surface Enterprise Management Mode (SEMM) ou Surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="b7132-129">Enabling Battery Limit using Surface Enterprise Management Mode (SEMM) or Surface Pro 3 firmware PowerShell scripts</span></span>

<span data-ttu-id="b7132-130">La limite de batterie UEFI Surface est également disponible pour la configuration via les méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="b7132-130">The Surface UEFI battery limit is also available for configuration via the following methods:</span></span>

- <span data-ttu-id="b7132-131">Surface Pro 4 et les ultérieures</span><span class="sxs-lookup"><span data-stu-id="b7132-131">Surface Pro 4 and later</span></span> 
    - [<span data-ttu-id="b7132-132">Configurateur UEFI Microsoft Surface</span><span class="sxs-lookup"><span data-stu-id="b7132-132">Microsoft Surface UEFI Configurator</span></span>](https://docs.microsoft.com/surface/surface-enterprise-management-mode)  
    - <span data-ttu-id="b7132-133">Scripts Surface UEFI Manager Powershell (SEMM_Powershell.zip) dans les [téléchargements surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703)</span><span class="sxs-lookup"><span data-stu-id="b7132-133">Surface UEFI Manager Powershell scripts (SEMM_Powershell.zip) in the [Surface Tools for IT downloads](https://www.microsoft.com/download/details.aspx?id=46703)</span></span>
- <span data-ttu-id="b7132-134">Surface Pro3</span><span class="sxs-lookup"><span data-stu-id="b7132-134">Surface Pro 3</span></span> 
    - [<span data-ttu-id="b7132-135">SP3_Firmware_Powershell_Scripts.zip</span><span class="sxs-lookup"><span data-stu-id="b7132-135">SP3_Firmware_Powershell_Scripts.zip</span></span>](https://www.microsoft.com/download/details.aspx?id=46703)

### <span data-ttu-id="b7132-136">Utilisation de Microsoft Surface UEFI Configurator</span><span class="sxs-lookup"><span data-stu-id="b7132-136">Using Microsoft Surface UEFI Configurator</span></span>

<span data-ttu-id="b7132-137">Pour configurer le mode limite de batterie, définissez le paramètre **Kiosk Overrides** sur la page de configuration des **paramètres** avancés dans SEMM (Surface Pro 4 et ultérieur).</span><span class="sxs-lookup"><span data-stu-id="b7132-137">To configure Battery Limit mode, set the **Kiosk Overrides** setting on the **Advanced Settings** configuration page in SEMM (Surface Pro 4 and later).</span></span>

![Capture d’écran des paramètres avancés](images/semm-bl.png)

### <span data-ttu-id="b7132-139">Utilisation des scripts PowerShell du Gestionnaire UEFI Surface</span><span class="sxs-lookup"><span data-stu-id="b7132-139">Using Surface UEFI Manager PowerShell scripts</span></span>

<span data-ttu-id="b7132-140">La fonctionnalité de limite de batterie est contrôlée via le paramètre suivant :</span><span class="sxs-lookup"><span data-stu-id="b7132-140">The battery limit feature is controlled via the following setting:</span></span>  

`407 = Battery Profile`

<span data-ttu-id="b7132-141">**Description :** schéma de gestion actif pour le modèle d’utilisation de la batterie</span><span class="sxs-lookup"><span data-stu-id="b7132-141">**Description**:  Active management scheme for battery usage pattern</span></span>

<span data-ttu-id="b7132-142">**Par**défaut :</span><span class="sxs-lookup"><span data-stu-id="b7132-142">**Default**:</span></span>  `0` 

<span data-ttu-id="b7132-143">Définissez cette limite `1` pour activer la limite de batterie.</span><span class="sxs-lookup"><span data-stu-id="b7132-143">Set this to `1` to enable Battery Limit.</span></span>

### <span data-ttu-id="b7132-144">Utilisation des outils de microprogramme Surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="b7132-144">Using Surface Pro 3 firmware tools</span></span>

<span data-ttu-id="b7132-145">La fonctionnalité de limite de batterie est contrôlée via le paramètre suivant :</span><span class="sxs-lookup"><span data-stu-id="b7132-145">The battery limit feature is controlled via the following setting:</span></span>  

<span data-ttu-id="b7132-146">**Name**: BatteryLimitEnable</span><span class="sxs-lookup"><span data-stu-id="b7132-146">**Name**: BatteryLimitEnable</span></span>

<span data-ttu-id="b7132-147">**Description**: BatteryLimit</span><span class="sxs-lookup"><span data-stu-id="b7132-147">**Description**:  BatteryLimit</span></span>

<span data-ttu-id="b7132-148">**Valeur actuelle**:</span><span class="sxs-lookup"><span data-stu-id="b7132-148">**Current Value**:</span></span>  `0` 

<span data-ttu-id="b7132-149">**Valeur par défaut**:</span><span class="sxs-lookup"><span data-stu-id="b7132-149">**Default Value**:</span></span> `0`

<span data-ttu-id="b7132-150">**Valeur proposée**:</span><span class="sxs-lookup"><span data-stu-id="b7132-150">**Proposed Value**:</span></span> `0` 

<span data-ttu-id="b7132-151">Définissez cette limite `1` pour activer la limite de batterie.</span><span class="sxs-lookup"><span data-stu-id="b7132-151">Set this to `1` to enable Battery Limit.</span></span>

>[!NOTE]
><span data-ttu-id="b7132-152">Pour configurer ce paramètre, vous devez utiliser [SP3_Firmware_Powershell_Scripts.zip](https://www.microsoft.com/download/details.aspx?id=46703).</span><span class="sxs-lookup"><span data-stu-id="b7132-152">To configure this setting, you must use [SP3_Firmware_Powershell_Scripts.zip](https://www.microsoft.com/download/details.aspx?id=46703).</span></span> 

