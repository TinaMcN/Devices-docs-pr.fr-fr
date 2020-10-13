---
title: Wake on LAN pour les appareils surface (surface)
description: Découvrez comment utiliser la fonctionnalité Wake on LAN pour réactiver à distance des appareils afin d’effectuer des tâches de gestion ou de maintenance, ou pour activer les solutions de gestion automatiquement, même si les appareils sont mis à niveau.
keywords: mise à jour, déploiement, pilote, WOL, Wake-on-LAN
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
ms.openlocfilehash: a56f6e01a4d7bf1cc40d73f34c3abf8e04443989
ms.sourcegitcommit: c1efb75e8524193bdc0a5f7496dc23a92ac665c8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/12/2020
ms.locfileid: "11114612"
---
# <span data-ttu-id="ad811-104">Wake On LAN pour les appareils Surface</span><span class="sxs-lookup"><span data-stu-id="ad811-104">Wake On LAN for Surface devices</span></span>

<span data-ttu-id="ad811-105">Les appareils surface qui exécutent Windows 10, version 1607 (également connu sous le nom de mise à jour anniversaire Windows 10) ou version ultérieure, et utilisent une carte Ethernet surface pour se connecter à un réseau câblé, peuvent utiliser la fonction Wake on LAN (WOL) de la veille connectée.</span><span class="sxs-lookup"><span data-stu-id="ad811-105">Surface devices that run Windows 10, version 1607 (also known as Windows 10 Anniversary Update) or later and use a Surface Ethernet adapter to connect to a wired network, are capable of Wake On LAN (WOL) from Connected Standby.</span></span> <span data-ttu-id="ad811-106">Avec WOL, vous pouvez réactiver les appareils à distance pour effectuer des tâches de gestion ou de maintenance, ou activer des solutions de gestion (comme Microsoft Endpoint Configuration Manager) automatiquement.</span><span class="sxs-lookup"><span data-stu-id="ad811-106">With WOL, you can remotely wake up devices to perform management or maintenance tasks or enable management solutions (such as Microsoft Endpoint Configuration Manager) automatically.</span></span> <span data-ttu-id="ad811-107">Par exemple, vous pouvez déployer des applications sur des appareils de surface à l’aide d’une station d’ancrage de surface d’amarrage ou de surface Pro 3 à l’aide du gestionnaire de configuration de points de terminaison Microsoft pendant une fenêtre au milieu de la nuit, lorsque le bureau est vide.</span><span class="sxs-lookup"><span data-stu-id="ad811-107">For example, you can deploy applications to Surface devices left docked with a Surface Dock or Surface Pro 3 Docking Station by using Microsoft Endpoint Configuration Manager during a window in the middle of the night, when the office is empty.</span></span>

>[!NOTE]
><span data-ttu-id="ad811-108">Les appareils surface doivent être connectés à une alimentation CA et en veille connectée pour prendre en charge WOL.</span><span class="sxs-lookup"><span data-stu-id="ad811-108">Surface devices must be connected to AC power and in Connected Standby (Sleep) to support WOL.</span></span> <span data-ttu-id="ad811-109">WOL ne peut pas être utilisé avec des appareils qui sont en veille ou qui sont éteints.</span><span class="sxs-lookup"><span data-stu-id="ad811-109">WOL is not possible from devices that are in hibernation or powered off.</span></span>

## <span data-ttu-id="ad811-110">Appareils pris en charge</span><span class="sxs-lookup"><span data-stu-id="ad811-110">Supported devices</span></span>

<span data-ttu-id="ad811-111">Les appareils suivants sont pris en charge pour WOL:</span><span class="sxs-lookup"><span data-stu-id="ad811-111">The following devices are supported for WOL:</span></span>

* <span data-ttu-id="ad811-112">Carte Ethernet surface</span><span class="sxs-lookup"><span data-stu-id="ad811-112">Surface Ethernet adapter</span></span>
* <span data-ttu-id="ad811-113">Surface USB-C vers Ethernet et adaptateur USB</span><span class="sxs-lookup"><span data-stu-id="ad811-113">Surface USB-C to Ethernet and USB Adapter</span></span>
* <span data-ttu-id="ad811-114">Station d’accueilSurface</span><span class="sxs-lookup"><span data-stu-id="ad811-114">Surface Dock</span></span>
* <span data-ttu-id="ad811-115">Station d’ancrage surface pour surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="ad811-115">Surface Docking Station for Surface Pro 3</span></span>
* <span data-ttu-id="ad811-116">Surface3</span><span class="sxs-lookup"><span data-stu-id="ad811-116">Surface 3</span></span>
* <span data-ttu-id="ad811-117">Surface Pro3</span><span class="sxs-lookup"><span data-stu-id="ad811-117">Surface Pro 3</span></span>
* <span data-ttu-id="ad811-118">Surface Pro4</span><span class="sxs-lookup"><span data-stu-id="ad811-118">Surface Pro 4</span></span>
* <span data-ttu-id="ad811-119">Surface Pro (5e génération)</span><span class="sxs-lookup"><span data-stu-id="ad811-119">Surface Pro (5th Gen)</span></span>
* <span data-ttu-id="ad811-120">Surface Pro (5e génération) avec LTE Advanced</span><span class="sxs-lookup"><span data-stu-id="ad811-120">Surface Pro (5th Gen) with LTE Advanced</span></span>
* <span data-ttu-id="ad811-121">SurfaceBook</span><span class="sxs-lookup"><span data-stu-id="ad811-121">Surface Book</span></span>
* <span data-ttu-id="ad811-122">Surface Laptop (1ère génération)</span><span class="sxs-lookup"><span data-stu-id="ad811-122">Surface Laptop (1st Gen)</span></span>
* <span data-ttu-id="ad811-123">SurfacePro6</span><span class="sxs-lookup"><span data-stu-id="ad811-123">Surface Pro 6</span></span>
* <span data-ttu-id="ad811-124">SurfaceBook2</span><span class="sxs-lookup"><span data-stu-id="ad811-124">Surface Book 2</span></span>
* <span data-ttu-id="ad811-125">Surface Laptop2</span><span class="sxs-lookup"><span data-stu-id="ad811-125">Surface Laptop 2</span></span>
* <span data-ttu-id="ad811-126">SurfaceGo</span><span class="sxs-lookup"><span data-stu-id="ad811-126">Surface Go</span></span>
* <span data-ttu-id="ad811-127">SurfaceGo avec LTE Advanced</span><span class="sxs-lookup"><span data-stu-id="ad811-127">Surface Go with LTE Advanced</span></span>
* <span data-ttu-id="ad811-128">Surface Studio 2 (voir les instructions de surface Studio 2 ci-dessous)</span><span class="sxs-lookup"><span data-stu-id="ad811-128">Surface Studio 2 (see Surface Studio 2 instructions below)</span></span>
* <span data-ttu-id="ad811-129">SurfacePro7</span><span class="sxs-lookup"><span data-stu-id="ad811-129">Surface Pro 7</span></span>
* <span data-ttu-id="ad811-130">Surface Laptop3</span><span class="sxs-lookup"><span data-stu-id="ad811-130">Surface Laptop 3</span></span>
* <span data-ttu-id="ad811-131">Surface Laptop Go</span><span class="sxs-lookup"><span data-stu-id="ad811-131">Surface Laptop Go</span></span>

## <span data-ttu-id="ad811-132">Pilote WOL</span><span class="sxs-lookup"><span data-stu-id="ad811-132">WOL driver</span></span>

<span data-ttu-id="ad811-133">Pour permettre la prise en charge de la fonction WOL sur les appareils surface, il est nécessaire de disposer d’un pilote spécifique pour la carte Ethernet surface.</span><span class="sxs-lookup"><span data-stu-id="ad811-133">To enable WOL support on Surface devices, a specific driver for the Surface Ethernet adapter is required.</span></span> <span data-ttu-id="ad811-134">Ce pilote n’est pas inclus dans le kit de pilotes et de microprogramme standard pour les appareils surface, vous devez le télécharger et l’installer séparément.</span><span class="sxs-lookup"><span data-stu-id="ad811-134">This driver is not included in the standard driver and firmware pack for Surface devices – you must download and install it separately.</span></span> <span data-ttu-id="ad811-135">Vous pouvez télécharger le pilote surface WOL (SurfaceWOL.msi) à partir de la page [Outils surface pour l’application](https://www.microsoft.com/download/details.aspx?id=46703) dans le centre de téléchargement Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ad811-135">You can download the Surface WOL driver (SurfaceWOL.msi) from the [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) page in the Microsoft Download Center.</span></span>

<span data-ttu-id="ad811-136">Vous pouvez exécuter ce fichier Microsoft Windows Installer (. msi) sur un appareil surface pour installer le pilote de surface WOL ou vous pouvez le distribuer sur des appareils surface avec une solution de déploiement d’application, telle que Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="ad811-136">You can run this Microsoft Windows Installer (.msi) file on a Surface device to install the Surface WOL driver, or you can distribute it to Surface devices with an application deployment solution, such as Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="ad811-137">Pour inclure le pilote surface WOL lors du déploiement, vous pouvez installer le fichier. msi en tant qu’application pendant le processus de déploiement.</span><span class="sxs-lookup"><span data-stu-id="ad811-137">To include the Surface WOL driver during deployment, you can install the .msi file as an application during the deployment process.</span></span> <span data-ttu-id="ad811-138">Vous pouvez également extraire les fichiers de pilote de surface WOL pour les inclure dans le processus de déploiement.</span><span class="sxs-lookup"><span data-stu-id="ad811-138">You can also extract the Surface WOL driver files to include them in the deployment process.</span></span> <span data-ttu-id="ad811-139">Par exemple, vous pouvez les inclure dans le partage de votre kit de développement Microsoft (MDT).</span><span class="sxs-lookup"><span data-stu-id="ad811-139">For example, you can include them in your Microsoft Deployment Toolkit (MDT) deployment share.</span></span> <span data-ttu-id="ad811-140">Vous pouvez en savoir plus sur le déploiement de surface avec MDT dans le [déploiement de Windows 10 sur les appareils surface avec le kit de développement Microsoft Deployment](https://technet.microsoft.com/itpro/surface/deploy-windows-10-to-surface-devices-with-mdt).</span><span class="sxs-lookup"><span data-stu-id="ad811-140">You can read more about Surface deployment with MDT in [Deploy Windows 10 to Surface devices with Microsoft Deployment Toolkit](https://technet.microsoft.com/itpro/surface/deploy-windows-10-to-surface-devices-with-mdt).</span></span>

> [!NOTE]
> <span data-ttu-id="ad811-141">Lors de l’installation de SurfaceWOL.msi, la clé de Registre suivante est définie sur une valeur de 1, ce qui permet d’identifier facilement les systèmes sur lesquels le pilote WOL a été installé.</span><span class="sxs-lookup"><span data-stu-id="ad811-141">During the installation of SurfaceWOL.msi, the following registry key is set to a value of 1, which allows easy identification of systems where the WOL driver has been installed.</span></span> <span data-ttu-id="ad811-142">Si vous avez choisi d’extraire et d’installer ces pilotes séparément lors du déploiement, cette clé de registre ne sera pas configurée et doit être configurée manuellement ou à l’aide d’un script.</span><span class="sxs-lookup"><span data-stu-id="ad811-142">If you chose to extract and install these drivers separately during deployment, this registry key will not be configured and must be configured manually or with a script.</span></span>
> 
> **<span data-ttu-id="ad811-143">HKLM\SYSTEM\CurrentControlSet\Control\Power AllowSystemRequiredPowerRequests</span><span class="sxs-lookup"><span data-stu-id="ad811-143">HKLM\SYSTEM\CurrentControlSet\Control\Power AllowSystemRequiredPowerRequests</span></span>** 

<span data-ttu-id="ad811-144">Pour extraire le contenu de SurfaceWOL.msi, utilisez l’option d’installation administrative de MSIExec (**/a**), comme indiqué dans l’exemple suivant, pour extraire le contenu dans le dossier C:\WOL\:</span><span class="sxs-lookup"><span data-stu-id="ad811-144">To extract the contents of SurfaceWOL.msi, use the MSIExec administrative installation option (**/a**), as shown in the following example, to extract the contents to the C:\WOL\ folder:</span></span>

   `msiexec /a surfacewol.msi targetdir=C:\WOL /qn`

## <span data-ttu-id="ad811-145">Instructions surface Studio 2</span><span class="sxs-lookup"><span data-stu-id="ad811-145">Surface Studio 2 instructions</span></span>

<span data-ttu-id="ad811-146">Pour activer la fonction WOL sur surface Studio 2, vous devez procéder comme suit:</span><span class="sxs-lookup"><span data-stu-id="ad811-146">To enable WOL on Surface Studio 2, you must use the following procedure</span></span>

1. <span data-ttu-id="ad811-147">Créez les clés de Registre suivantes:</span><span class="sxs-lookup"><span data-stu-id="ad811-147">Create the following registry keys:</span></span>

   ```console
   ; Set CONNECTIVITYINSTANDBY to 1:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power\PowerSettings\F15576E8-98B7-4186-B944-EAFA664402D9]
   "Attributes"=dword:00000001
   ; Set EnforceDisconnectedStandby to 0 and AllowSystemRequiredPowerRequests to 1:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power]
   "EnforceDisconnectedStandby"=dword:00000000
   "AllowSystemRequiredPowerRequests"=dword:00000001
   ```

2. <span data-ttu-id="ad811-148">Exécutez la commande suivante</span><span class="sxs-lookup"><span data-stu-id="ad811-148">Run the following command</span></span>

    ```powercfg /SETACVALUEINDEX SCHEME_BALANCED SUB_NONE CONNECTIVITYINSTANDBY 1```

## <span data-ttu-id="ad811-149">Utilisation de surface WOL</span><span class="sxs-lookup"><span data-stu-id="ad811-149">Using Surface WOL</span></span>

<span data-ttu-id="ad811-150">Le pilote surface WOL est conforme à la norme WOL, ce qui indique que le périphérique est réveillée par une communication réseau spéciale appelée Magic Packet.</span><span class="sxs-lookup"><span data-stu-id="ad811-150">The Surface WOL driver conforms to the WOL standard, whereby the device is woken by a special network communication known as a magic packet.</span></span> <span data-ttu-id="ad811-151">Le paquet Magic est composé de 6 octets de 255 (ou de FF en hexadécimal), suivis de 16 répétitions de l’adresse MAC de l’ordinateur cible.</span><span class="sxs-lookup"><span data-stu-id="ad811-151">The magic packet consists of 6 bytes of 255 (or FF in hexadecimal) followed by 16 repetitions of the target computer’s MAC address.</span></span> <span data-ttu-id="ad811-152">Vous pouvez en savoir plus sur le paquet Magic et la norme WOL sur [Wikipédia](https://wikipedia.org/wiki/Wake-on-LAN#Magic_packet).</span><span class="sxs-lookup"><span data-stu-id="ad811-152">You can read more about the magic packet and the WOL standard on [Wikipedia](https://wikipedia.org/wiki/Wake-on-LAN#Magic_packet).</span></span>

>[!NOTE]
><span data-ttu-id="ad811-153">Pour envoyer un paquet Magic et réveiller un appareil à l’aide de WOL, vous devez connaître l’adresse MAC de l’appareil cible et de la carte Ethernet.</span><span class="sxs-lookup"><span data-stu-id="ad811-153">To send a magic packet and wake up a device by using WOL, you must know the MAC address of the target device and Ethernet adapter.</span></span> <span data-ttu-id="ad811-154">Dans la mesure où le paquet Magic n’utilise pas le protocole réseau IP, il n’est pas possible d’utiliser l’adresse IP ou le nom DNS de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="ad811-154">Because the magic packet does not use the IP network protocol, it is not possible to use the IP address or DNS name of the device.</span></span>

<span data-ttu-id="ad811-155">De nombreuses solutions de gestion telles que Configuration Manager fournissent une prise en charge intégrée de WOL.</span><span class="sxs-lookup"><span data-stu-id="ad811-155">Many management solutions, such as Configuration Manager, provide built-in support for WOL.</span></span> <span data-ttu-id="ad811-156">Il y a également de nombreuses solutions, notamment les applications du Windows Store, les modules PowerShell, les applications tierces et les solutions de gestion tierces qui vous permettent d’envoyer un paquet Magic pour réactiver un périphérique.</span><span class="sxs-lookup"><span data-stu-id="ad811-156">There are also many solutions, including Microsoft Store apps, PowerShell modules, third-party applications, and third-party management solutions that allow you to send a magic packet to wake up a device.</span></span> <span data-ttu-id="ad811-157">Par exemple, vous pouvez utiliser le [module Wake on LAN PowerShell](https://gallery.technet.microsoft.com/scriptcenter/Wake-On-Lan-815424c4) dans le centre de scripts technet.</span><span class="sxs-lookup"><span data-stu-id="ad811-157">For example, you can use the [Wake On LAN PowerShell module](https://gallery.technet.microsoft.com/scriptcenter/Wake-On-Lan-815424c4) from the TechNet Script Center.</span></span> 

>[!NOTE]
><span data-ttu-id="ad811-158">Une fois qu’un appareil est réveillée avec un paquet Magic, l’appareil revient en mode veille si une application n’empêche pas activement la mise en veille sur le système ou si la clé de Registre AllowSystemRequiredPowerRequests n’est pas configurée sur 1, ce qui permet aux applications d’éviter la mise en veille.</span><span class="sxs-lookup"><span data-stu-id="ad811-158">After a device has been woken up with a magic packet, the device will return to sleep if an application is not actively preventing sleep on the system or if the AllowSystemRequiredPowerRequests registry key is not configured to 1, which allows applications to prevent sleep.</span></span> <span data-ttu-id="ad811-159">Pour plus d’informations sur cette clé de Registre, voir la section [pilote WOL](#wol-driver) de cet article.</span><span class="sxs-lookup"><span data-stu-id="ad811-159">See the [WOL driver](#wol-driver) section of this article for more information about this registry key.</span></span>
