---
title: Wake On LAN pour les appareils Surface (Surface)
description: Découvrez comment utiliser Wake On LAN pour faire s’activer à distance les appareils pour effectuer des tâches de gestion ou de maintenance, ou pour activer les solutions de gestion automatiquement, même si les appareils sont sous tension.
keywords: mettre à jour, déployer, pilote, wake-on-lan
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
ms.localizationpriority: medium
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: scottmca
manager: laurawi
ms.audience: itpro
ms.date: 1/15/2021
ms.openlocfilehash: 709286cc0d62bd0b4c1e28e7626529fc4a215ae2
ms.sourcegitcommit: 1b86286bd13b13749ddbf454ae78d9a24fec44ee
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "11271121"
---
# <span data-ttu-id="b892b-104">Wake On LAN pour les appareils Surface</span><span class="sxs-lookup"><span data-stu-id="b892b-104">Wake On LAN for Surface devices</span></span>

<span data-ttu-id="b892b-105">Les appareils Surface qui exécutent Windows 10, version 1607 (également appelée Mise à jour anniversaire Windows 10) ou version ultérieure et utilisent un adaptateur Ethernet Surface pour se connecter à un réseau câblé, sont capables d’être mis à jour à l’aide d’un réseau local de veille connectée à partir de la veille connectée.</span><span class="sxs-lookup"><span data-stu-id="b892b-105">Surface devices that run Windows 10, version 1607 (also known as Windows 10 Anniversary Update) or later and use a Surface Ethernet adapter to connect to a wired network, are capable of Wake On LAN (WOL) from Connected Standby.</span></span> <span data-ttu-id="b892b-106">Grâce à LASO, vous pouvez faire s’activer à distance les appareils pour effectuer des tâches de gestion ou de maintenance, ou activer automatiquement des solutions de gestion (telles que Microsoft Endpoint Configuration Manager).</span><span class="sxs-lookup"><span data-stu-id="b892b-106">With WOL, you can remotely wake up devices to perform management or maintenance tasks or enable management solutions (such as Microsoft Endpoint Configuration Manager) automatically.</span></span> <span data-ttu-id="b892b-107">Par exemple, vous pouvez déployer des applications sur des appareils Surface ancres à gauche avec une station d’accueil Surface Pro 3 ou une station d’accueil Surface Pro 3 à l’aide de Microsoft Endpoint Configuration Manager pendant une fenêtre au milieu de la nuit, lorsque le bureau est vide.</span><span class="sxs-lookup"><span data-stu-id="b892b-107">For example, you can deploy applications to Surface devices left docked with a Surface Dock or Surface Pro 3 Docking Station by using Microsoft Endpoint Configuration Manager during a window in the middle of the night, when the office is empty.</span></span>

>[!NOTE]
><span data-ttu-id="b892b-108">Les appareils Surface doivent être connectés à l’alimentation ac et en veille connectée (veille connectée) pour prendre en charge la prise en charge de LASO.</span><span class="sxs-lookup"><span data-stu-id="b892b-108">Surface devices must be connected to AC power and in Connected Standby (Sleep) to support WOL.</span></span> <span data-ttu-id="b892b-109">La mise en veille prolongée ou la mise hors tension de l’appareil n’est pas possible pour les appareils en veille prolongée.</span><span class="sxs-lookup"><span data-stu-id="b892b-109">WOL is not possible from devices that are in hibernation or powered off.</span></span>

## <span data-ttu-id="b892b-110">Appareils pris en charge</span><span class="sxs-lookup"><span data-stu-id="b892b-110">Supported devices</span></span>

<span data-ttu-id="b892b-111">Les appareils suivants sont pris en charge pour LASO :</span><span class="sxs-lookup"><span data-stu-id="b892b-111">The following devices are supported for WOL:</span></span>

* <span data-ttu-id="b892b-112">Adaptateur Ethernet Surface</span><span class="sxs-lookup"><span data-stu-id="b892b-112">Surface Ethernet adapter</span></span>
* <span data-ttu-id="b892b-113">Surface USB-C vers Ethernet et adaptateur USB</span><span class="sxs-lookup"><span data-stu-id="b892b-113">Surface USB-C to Ethernet and USB Adapter</span></span>
* <span data-ttu-id="b892b-114">Station d’accueilSurface</span><span class="sxs-lookup"><span data-stu-id="b892b-114">Surface Dock</span></span>
* <span data-ttu-id="b892b-115">Station d’accueil Surface pour Surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="b892b-115">Surface Docking Station for Surface Pro 3</span></span>
* <span data-ttu-id="b892b-116">Surface3</span><span class="sxs-lookup"><span data-stu-id="b892b-116">Surface 3</span></span>
* <span data-ttu-id="b892b-117">Surface Pro3</span><span class="sxs-lookup"><span data-stu-id="b892b-117">Surface Pro 3</span></span>
* <span data-ttu-id="b892b-118">Surface Pro4</span><span class="sxs-lookup"><span data-stu-id="b892b-118">Surface Pro 4</span></span>
* <span data-ttu-id="b892b-119">Surface Pro (5e génération)</span><span class="sxs-lookup"><span data-stu-id="b892b-119">Surface Pro (5th Gen)</span></span>
* <span data-ttu-id="b892b-120">Surface Pro (5e génération) avec LTE Advanced</span><span class="sxs-lookup"><span data-stu-id="b892b-120">Surface Pro (5th Gen) with LTE Advanced</span></span>
* <span data-ttu-id="b892b-121">SurfaceBook</span><span class="sxs-lookup"><span data-stu-id="b892b-121">Surface Book</span></span>
* <span data-ttu-id="b892b-122">Surface Laptop (1re génération)</span><span class="sxs-lookup"><span data-stu-id="b892b-122">Surface Laptop (1st Gen)</span></span>
* <span data-ttu-id="b892b-123">SurfacePro6</span><span class="sxs-lookup"><span data-stu-id="b892b-123">Surface Pro 6</span></span>
* <span data-ttu-id="b892b-124">SurfaceBook2</span><span class="sxs-lookup"><span data-stu-id="b892b-124">Surface Book 2</span></span>
* <span data-ttu-id="b892b-125">Surface Laptop2</span><span class="sxs-lookup"><span data-stu-id="b892b-125">Surface Laptop 2</span></span>
* <span data-ttu-id="b892b-126">SurfaceGo</span><span class="sxs-lookup"><span data-stu-id="b892b-126">Surface Go</span></span>
* <span data-ttu-id="b892b-127">SurfaceGo avec LTE Advanced</span><span class="sxs-lookup"><span data-stu-id="b892b-127">Surface Go with LTE Advanced</span></span>
* <span data-ttu-id="b892b-128">Surface Studio 2 (voir les instructions de Surface Studio 2 ci-dessous)</span><span class="sxs-lookup"><span data-stu-id="b892b-128">Surface Studio 2 (see Surface Studio 2 instructions below)</span></span>
* <span data-ttu-id="b892b-129">SurfacePro7</span><span class="sxs-lookup"><span data-stu-id="b892b-129">Surface Pro 7</span></span>
* <span data-ttu-id="b892b-130">Surface Laptop3</span><span class="sxs-lookup"><span data-stu-id="b892b-130">Surface Laptop 3</span></span>
* <span data-ttu-id="b892b-131">Surface Laptop Go</span><span class="sxs-lookup"><span data-stu-id="b892b-131">Surface Laptop Go</span></span>
* <span data-ttu-id="b892b-132">Surface Pro 7+</span><span class="sxs-lookup"><span data-stu-id="b892b-132">Surface Pro 7+</span></span>

## <span data-ttu-id="b892b-133">Pilote DNS</span><span class="sxs-lookup"><span data-stu-id="b892b-133">WOL driver</span></span>

<span data-ttu-id="b892b-134">Pour activer la prise en charge DELS sur les appareils Surface, un pilote spécifique pour l’adaptateur Ethernet Surface est requis.</span><span class="sxs-lookup"><span data-stu-id="b892b-134">To enable WOL support on Surface devices, a specific driver for the Surface Ethernet adapter is required.</span></span> <span data-ttu-id="b892b-135">Ce pilote n’est pas inclus dans le pack de microprogramme et de pilote standard pour les appareils Surface : vous devez le télécharger et l’installer séparément.</span><span class="sxs-lookup"><span data-stu-id="b892b-135">This driver is not included in the standard driver and firmware pack for Surface devices – you must download and install it separately.</span></span> <span data-ttu-id="b892b-136">Vous pouvez télécharger le pilote SURFACE SurfaceWOL.msi à partir de la page [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) du Centre de téléchargement Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b892b-136">You can download the Surface WOL driver (SurfaceWOL.msi) from the [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) page in the Microsoft Download Center.</span></span>

<span data-ttu-id="b892b-137">Vous pouvez exécuter ce fichier Microsoft Windows Installer (.msi) sur un appareil Surface pour installer le pilote SURFACE PDF ou le distribuer aux appareils Surface avec une solution de déploiement d’application, telle que Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="b892b-137">You can run this Microsoft Windows Installer (.msi) file on a Surface device to install the Surface WOL driver, or you can distribute it to Surface devices with an application deployment solution, such as Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="b892b-138">Pour inclure le pilote SURFACE AU COURS du déploiement, vous pouvez installer le fichier .msi en tant qu’application pendant le processus de déploiement.</span><span class="sxs-lookup"><span data-stu-id="b892b-138">To include the Surface WOL driver during deployment, you can install the .msi file as an application during the deployment process.</span></span> <span data-ttu-id="b892b-139">Vous pouvez également extraire les fichiers de pilotes SURFACE EXTRACT pour les inclure dans le processus de déploiement.</span><span class="sxs-lookup"><span data-stu-id="b892b-139">You can also extract the Surface WOL driver files to include them in the deployment process.</span></span> <span data-ttu-id="b892b-140">Par exemple, vous pouvez les inclure dans votre partage de déploiement Microsoft Deployment Shared Computer Toolkit (MDT).</span><span class="sxs-lookup"><span data-stu-id="b892b-140">For example, you can include them in your Microsoft Deployment Toolkit (MDT) deployment share.</span></span> <span data-ttu-id="b892b-141">Vous pouvez en savoir plus sur le déploiement de Surface avec MDT dans [Déployer Windows 10](https://technet.microsoft.com/itpro/surface/deploy-windows-10-to-surface-devices-with-mdt)sur des appareils Surface avec Microsoft Deployment Shared Computer Toolkit .</span><span class="sxs-lookup"><span data-stu-id="b892b-141">You can read more about Surface deployment with MDT in [Deploy Windows 10 to Surface devices with Microsoft Deployment Toolkit](https://technet.microsoft.com/itpro/surface/deploy-windows-10-to-surface-devices-with-mdt).</span></span>

> [!NOTE]
> <span data-ttu-id="b892b-142">Lors de l’installation de SurfaceWOL.msi, la clé de Registre suivante est définie sur la valeur 1, ce qui permet d’identifier facilement les systèmes sur lesquels le pilote TOL a été installé.</span><span class="sxs-lookup"><span data-stu-id="b892b-142">During the installation of SurfaceWOL.msi, the following registry key is set to a value of 1, which allows easy identification of systems where the WOL driver has been installed.</span></span> <span data-ttu-id="b892b-143">Si vous avez choisi d’extraire et d’installer ces pilotes séparément lors du déploiement, cette clé de Registre ne sera pas configurée et doit être configurée manuellement ou avec un script.</span><span class="sxs-lookup"><span data-stu-id="b892b-143">If you chose to extract and install these drivers separately during deployment, this registry key will not be configured and must be configured manually or with a script.</span></span>
> 
> **<span data-ttu-id="b892b-144">HKLM\SYSTEM\CurrentControlSet\Control\Power AllowSystemRequiredPowerRequests</span><span class="sxs-lookup"><span data-stu-id="b892b-144">HKLM\SYSTEM\CurrentControlSet\Control\Power AllowSystemRequiredPowerRequests</span></span>** 

<span data-ttu-id="b892b-145">Pour extraire le contenu de SurfaceWOL.msi, utilisez l’option d’installation administrative MSIExec (**/a**), comme illustré dans l’exemple suivant, pour extraire le contenu dans le dossier C:\EXTRACT\ :</span><span class="sxs-lookup"><span data-stu-id="b892b-145">To extract the contents of SurfaceWOL.msi, use the MSIExec administrative installation option (**/a**), as shown in the following example, to extract the contents to the C:\WOL\ folder:</span></span>

   `msiexec /a surfacewol.msi targetdir=C:\WOL /qn`

## <span data-ttu-id="b892b-146">Instructions de Surface Studio 2</span><span class="sxs-lookup"><span data-stu-id="b892b-146">Surface Studio 2 instructions</span></span>

<span data-ttu-id="b892b-147">Pour activer LASO sur Surface Studio 2, vous devez utiliser la procédure suivante :</span><span class="sxs-lookup"><span data-stu-id="b892b-147">To enable WOL on Surface Studio 2, you must use the following procedure</span></span>

1. <span data-ttu-id="b892b-148">Créez les clés de Registre suivantes :</span><span class="sxs-lookup"><span data-stu-id="b892b-148">Create the following registry keys:</span></span>

   ```console
   ; Set CONNECTIVITYINSTANDBY to 1:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power\PowerSettings\F15576E8-98B7-4186-B944-EAFA664402D9]
   "Attributes"=dword:00000001
   ; Set EnforceDisconnectedStandby to 0 and AllowSystemRequiredPowerRequests to 1:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power]
   "EnforceDisconnectedStandby"=dword:00000000
   "AllowSystemRequiredPowerRequests"=dword:00000001
   ```

2. <span data-ttu-id="b892b-149">Exécutez la commande suivante</span><span class="sxs-lookup"><span data-stu-id="b892b-149">Run the following command</span></span>

    ```powercfg /SETACVALUEINDEX SCHEME_BALANCED SUB_NONE CONNECTIVITYINSTANDBY 1```

## <span data-ttu-id="b892b-150">Utilisation de surface SURFACE</span><span class="sxs-lookup"><span data-stu-id="b892b-150">Using Surface WOL</span></span>

<span data-ttu-id="b892b-151">Le pilote SURFACE COMMUT est conforme à la norme COMMUT, selon laquelle l’appareil est paré par une communication réseau spéciale appelée paquet de magie.</span><span class="sxs-lookup"><span data-stu-id="b892b-151">The Surface WOL driver conforms to the WOL standard, whereby the device is woken by a special network communication known as a magic packet.</span></span> <span data-ttu-id="b892b-152">Le paquet magique se compose de 6 octets de 255 (ou FF en hexadécimal) suivi de 16 répétitions de l’adresse MAC de l’ordinateur cible.</span><span class="sxs-lookup"><span data-stu-id="b892b-152">The magic packet consists of 6 bytes of 255 (or FF in hexadecimal) followed by 16 repetitions of the target computer’s MAC address.</span></span> <span data-ttu-id="b892b-153">Vous pouvez en savoir plus sur le paquet de magie et la norme WIKIPEDIA sur [Wikipedia](https://wikipedia.org/wiki/Wake-on-LAN#Magic_packet).</span><span class="sxs-lookup"><span data-stu-id="b892b-153">You can read more about the magic packet and the WOL standard on [Wikipedia](https://wikipedia.org/wiki/Wake-on-LAN#Magic_packet).</span></span>

>[!NOTE]
><span data-ttu-id="b892b-154">Pour envoyer un paquet de magie et faire s’agiter d’un appareil à l’aide de LASO, vous devez connaître l’adresse MAC de l’appareil cible et de l’adaptateur Ethernet.</span><span class="sxs-lookup"><span data-stu-id="b892b-154">To send a magic packet and wake up a device by using WOL, you must know the MAC address of the target device and Ethernet adapter.</span></span> <span data-ttu-id="b892b-155">Étant donné que le paquet magique n’utilise pas le protocole réseau IP, il n’est pas possible d’utiliser l’adresse IP ou le nom DNS de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="b892b-155">Because the magic packet does not use the IP network protocol, it is not possible to use the IP address or DNS name of the device.</span></span>

<span data-ttu-id="b892b-156">De nombreuses solutions de gestion, telles que Configuration Manager, offrent une prise en charge intégrée de LASO.</span><span class="sxs-lookup"><span data-stu-id="b892b-156">Many management solutions, such as Configuration Manager, provide built-in support for WOL.</span></span> <span data-ttu-id="b892b-157">Il existe également de nombreuses solutions, notamment des applications du Microsoft Store, des modules PowerShell, des applications tierces et des solutions de gestion tierces qui vous permettent d’envoyer un paquet magique pour l’alimentation d’un appareil.</span><span class="sxs-lookup"><span data-stu-id="b892b-157">There are also many solutions, including Microsoft Store apps, PowerShell modules, third-party applications, and third-party management solutions that allow you to send a magic packet to wake up a device.</span></span> <span data-ttu-id="b892b-158">Par exemple, vous pouvez utiliser le [module PowerShell Wake On LAN](https://gallery.technet.microsoft.com/scriptcenter/Wake-On-Lan-815424c4) à partir du Centre de scripts TechNet.</span><span class="sxs-lookup"><span data-stu-id="b892b-158">For example, you can use the [Wake On LAN PowerShell module](https://gallery.technet.microsoft.com/scriptcenter/Wake-On-Lan-815424c4) from the TechNet Script Center.</span></span> 

>[!NOTE]
><span data-ttu-id="b892b-159">Une fois qu’un appareil a été mis en veille avec un paquet magique, il revient en veille si une application n’empêche pas activement la mise en veille sur le système ou si la clé de Registre AllowSystemRequiredPowerRequests n’est pas configurée sur 1, ce qui permet aux applications d’empêcher la mise en veille.</span><span class="sxs-lookup"><span data-stu-id="b892b-159">After a device has been woken up with a magic packet, the device will return to sleep if an application is not actively preventing sleep on the system or if the AllowSystemRequiredPowerRequests registry key is not configured to 1, which allows applications to prevent sleep.</span></span> <span data-ttu-id="b892b-160">Pour plus [d’informations](#wol-driver) sur cette clé de Registre, consultez la section pilote DUTL de cet article.</span><span class="sxs-lookup"><span data-stu-id="b892b-160">See the [WOL driver](#wol-driver) section of this article for more information about this registry key.</span></span>
