---
title: SurfaceHub est susceptible d’installer des mises à jour et de redémarrer les heures de maintenance externes
description: informations de résolution des problèmes de surface Hub concernant les mises à jour automatiques
ms.assetid: 6C09A9F8-F9CF-4491-BBFB-67A1A1DED0AA
keywords: surface Hub, fenêtre de maintenance, mise à jour
ms.prod: surface-hub
ms.sitesec: library
author: Teresa-MOTIV
ms.author: v-tea
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: 117c18cfce6dfb84b4fe2156ea98198f96da2abf
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10833821"
---
# <span data-ttu-id="a60d7-104">SurfaceHub est susceptible d’installer des mises à jour et de redémarrer les heures de maintenance externes</span><span class="sxs-lookup"><span data-stu-id="a60d7-104">Surface Hub may install updates and restart outside maintenance hours</span></span>

<span data-ttu-id="a60d7-105">Dans des circonstances spécifiques, surface Hub installe les mises à jour pendant les heures d’activité plutôt que dans la fenêtre de maintenance normale.</span><span class="sxs-lookup"><span data-stu-id="a60d7-105">Under specific circumstances, Surface Hub installs updates during business hours instead of during the regular maintenance window.</span></span> <span data-ttu-id="a60d7-106">Le périphérique redémarre si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="a60d7-106">The device then restarts if it is necessary.</span></span> <span data-ttu-id="a60d7-107">Vous ne pouvez pas utiliser l’appareil tant que le processus n’est pas terminé.</span><span class="sxs-lookup"><span data-stu-id="a60d7-107">You cannot use the device until the process is completed.</span></span>

> [!NOTE]  
> <span data-ttu-id="a60d7-108">Ce comportement n’est pas attendu pour une fenêtre de maintenance.</span><span class="sxs-lookup"><span data-stu-id="a60d7-108">This isn't expected behavior for missing a maintenance window.</span></span> <span data-ttu-id="a60d7-109">Ce problème se produit uniquement si le périphérique est obsolète depuis longtemps.</span><span class="sxs-lookup"><span data-stu-id="a60d7-109">It occurs only if the device is out-of-date for a long time.</span></span>

## <span data-ttu-id="a60d7-110">Cause</span><span class="sxs-lookup"><span data-stu-id="a60d7-110">Cause</span></span>
<span data-ttu-id="a60d7-111">Pour vous assurer que le concentrateur de surface reste disponible pendant les heures d’activité, le Hub est configuré pour effectuer des fonctions d’administration au cours d’une fenêtre de maintenance définie dans les paramètres (voir «références» ci-dessous).</span><span class="sxs-lookup"><span data-stu-id="a60d7-111">To ensure that Surface Hub remains available for use during business hours, the Hub is configured to perform administrative functions during a maintenance window that is defined in Settings (see "References," below).</span></span> <span data-ttu-id="a60d7-112">Pendant cette période de maintenance, le Hub installe automatiquement les mises à jour disponibles par le biais de Windows Update ou du service de mise à jour Windows Server (WSUS).</span><span class="sxs-lookup"><span data-stu-id="a60d7-112">During this maintenance period, the Hub automatically installs any available updates through Windows Update or Windows Server Update Service (WSUS).</span></span> <span data-ttu-id="a60d7-113">Une fois les mises à jour terminées, le concentrateur risque de redémarrer.</span><span class="sxs-lookup"><span data-stu-id="a60d7-113">Once updates are complete, the Hub may restart.</span></span>

<span data-ttu-id="a60d7-114">Les mises à jour peuvent être installées dans la fenêtre de maintenance uniquement si le surface Hub est activé, mais qu’il n’est pas en cours d’utilisation ou de réservation.</span><span class="sxs-lookup"><span data-stu-id="a60d7-114">Updates can be installed during the maintenance window only if the Surface Hub is turned on but not in use or reserved.</span></span> <span data-ttu-id="a60d7-115">Par exemple, si la surface Hub est planifiée pour une réunion qui dure 24 heures, toutes les mises à jour qui doivent être installées seront différées jusqu’à ce que le concentrateur soit disponible dans la fenêtre de maintenance suivante.</span><span class="sxs-lookup"><span data-stu-id="a60d7-115">For example, if the Surface Hub is scheduled for a meeting that lasts 24 hours, any updates that are scheduled to be installed will be deferred until the Hub is available during the next maintenance window.</span></span> <span data-ttu-id="a60d7-116">Si le concentrateur reste occupé et qu’il n’y a pas de fenêtres de maintenance, il finira par installer et télécharger les mises à jour.</span><span class="sxs-lookup"><span data-stu-id="a60d7-116">If the Hub continues to be busy and misses multiple maintenance windows, the Hub will eventually begin to install and download updates.</span></span> <span data-ttu-id="a60d7-117">Cela peut se produire pendant ou en dehors de la fenêtre de maintenance.</span><span class="sxs-lookup"><span data-stu-id="a60d7-117">This can occur during or outside the maintenance window.</span></span> <span data-ttu-id="a60d7-118">Une fois le téléchargement et l’installation démarrés, le périphérique peut redémarrer.</span><span class="sxs-lookup"><span data-stu-id="a60d7-118">Once the download and installation has begun, the device may restart.</span></span>

## <span data-ttu-id="a60d7-119">Pour éviter ce problème</span><span class="sxs-lookup"><span data-stu-id="a60d7-119">To avoid this issue</span></span>

<span data-ttu-id="a60d7-120">Il est important de mettre en place le temps de maintenance de surface Hub pour effectuer des fonctions d’administration.</span><span class="sxs-lookup"><span data-stu-id="a60d7-120">It's important that you set aside maintenance time for Surface Hub to perform administrative functions.</span></span> <span data-ttu-id="a60d7-121">La réservation de surface Hub pour 24 heures ou l’utilisation de l’appareil pendant la période de maintenance retarde l’installation des mises à jour.</span><span class="sxs-lookup"><span data-stu-id="a60d7-121">Reserving the Surface Hub for 24 hour intervals or using the device during the maintenance window delays installing updates.</span></span> <span data-ttu-id="a60d7-122">Nous vous recommandons de ne pas utiliser ou réserver le concentrateur pendant la période de maintenance planifiée.</span><span class="sxs-lookup"><span data-stu-id="a60d7-122">We recommend that you not use or reserve the Hub during scheduled maintenance period.</span></span> <span data-ttu-id="a60d7-123">Une fenêtre de deux heures doit être réservée à des fins de mise à jour.</span><span class="sxs-lookup"><span data-stu-id="a60d7-123">A two-hour window should be reserved for updating.</span></span>

<span data-ttu-id="a60d7-124">Une option que vous pouvez utiliser pour contrôler la disponibilité des mises à jour est Windows Server Update Service (WSUS).</span><span class="sxs-lookup"><span data-stu-id="a60d7-124">One option that you can use to control the availability of updates is Windows Server Update Service (WSUS).</span></span> <span data-ttu-id="a60d7-125">WSUS vous permet de contrôler les mises à jour qui sont installées.</span><span class="sxs-lookup"><span data-stu-id="a60d7-125">WSUS provides control over what updates are installed and when.</span></span>

## <span data-ttu-id="a60d7-126">Références</span><span class="sxs-lookup"><span data-stu-id="a60d7-126">References</span></span> 
 
[<span data-ttu-id="a60d7-127">Mettre à jour le Surface Hub</span><span class="sxs-lookup"><span data-stu-id="a60d7-127">Update the Surface Hub</span></span>](first-run-program-surface-hub.md#update-the-surface-hub) 

[<span data-ttu-id="a60d7-128">Fenêtre de maintenance</span><span class="sxs-lookup"><span data-stu-id="a60d7-128">Maintenance window</span></span>](manage-windows-updates-for-surface-hub.md#maintenance-window) 

[<span data-ttu-id="a60d7-129">Déploie les mises à jour Windows10 à l’aide de WindowsServer Update Services (WSUS)</span><span class="sxs-lookup"><span data-stu-id="a60d7-129">Deploy Windows 10 updates using Windows Server Update Services (WSUS)</span></span>](/windows/deployment/update/waas-manage-updates-wsus) 


