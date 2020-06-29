---
title: Mettre à niveau des appareils surface vers Windows 10 avec le kit de développement Microsoft (surface)
description: Découvrez comment effectuer un déploiement de mise à niveau de Windows 10 sur vos appareils surface.
keywords: surface Windows 10, mise à niveau, personnalisation, MDT
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
ms.audience: itpro
ms.reviewer: ''
manager: laurawi
ms.date: 04/24/2020
ms.openlocfilehash: e1a1d34c4d32c5e6f95c985e335e405c0d9e59e4
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10833168"
---
# <span data-ttu-id="700ec-104">Mettre à niveau des appareils surface vers Windows 10 à l’aide du kit de développement Microsoft Deployment</span><span class="sxs-lookup"><span data-stu-id="700ec-104">Upgrade Surface devices to Windows 10 with Microsoft Deployment Toolkit</span></span>

#### <span data-ttu-id="700ec-105">S'applique à</span><span class="sxs-lookup"><span data-stu-id="700ec-105">Applies to</span></span>
- <span data-ttu-id="700ec-106">SurfacePro6</span><span class="sxs-lookup"><span data-stu-id="700ec-106">Surface Pro 6</span></span>
- <span data-ttu-id="700ec-107">Surface Laptop2</span><span class="sxs-lookup"><span data-stu-id="700ec-107">Surface Laptop 2</span></span>
- <span data-ttu-id="700ec-108">SurfaceGo</span><span class="sxs-lookup"><span data-stu-id="700ec-108">Surface Go</span></span>
- <span data-ttu-id="700ec-109">Surface Go avec LTE</span><span class="sxs-lookup"><span data-stu-id="700ec-109">Surface Go with LTE</span></span>
- <span data-ttu-id="700ec-110">SurfaceBook2</span><span class="sxs-lookup"><span data-stu-id="700ec-110">Surface Book 2</span></span>
- <span data-ttu-id="700ec-111">SurfacePro avec LTE Advanced (modèle1807)</span><span class="sxs-lookup"><span data-stu-id="700ec-111">Surface Pro with LTE Advanced (Model 1807)</span></span>
- <span data-ttu-id="700ec-112">SurfacePro (modèle1796)</span><span class="sxs-lookup"><span data-stu-id="700ec-112">Surface Pro (Model 1796)</span></span>
- <span data-ttu-id="700ec-113">Surface Laptop</span><span class="sxs-lookup"><span data-stu-id="700ec-113">Surface Laptop</span></span>
- <span data-ttu-id="700ec-114">SurfaceStudio</span><span class="sxs-lookup"><span data-stu-id="700ec-114">Surface Studio</span></span>
- <span data-ttu-id="700ec-115">Surface Studio2</span><span class="sxs-lookup"><span data-stu-id="700ec-115">Surface Studio 2</span></span>
- <span data-ttu-id="700ec-116">SurfaceBook</span><span class="sxs-lookup"><span data-stu-id="700ec-116">Surface Book</span></span>
- <span data-ttu-id="700ec-117">Surface Pro4</span><span class="sxs-lookup"><span data-stu-id="700ec-117">Surface Pro 4</span></span>
- <span data-ttu-id="700ec-118">VersionsLTE du modèleSurface3</span><span class="sxs-lookup"><span data-stu-id="700ec-118">Surface 3 LTE</span></span>
- <span data-ttu-id="700ec-119">Surface3</span><span class="sxs-lookup"><span data-stu-id="700ec-119">Surface 3</span></span>
- <span data-ttu-id="700ec-120">Surface Pro3</span><span class="sxs-lookup"><span data-stu-id="700ec-120">Surface Pro 3</span></span>
- <span data-ttu-id="700ec-121">Surface Pro2</span><span class="sxs-lookup"><span data-stu-id="700ec-121">Surface Pro 2</span></span>
- <span data-ttu-id="700ec-122">SurfacePro</span><span class="sxs-lookup"><span data-stu-id="700ec-122">Surface Pro</span></span>
- <span data-ttu-id="700ec-123">Windows 10</span><span class="sxs-lookup"><span data-stu-id="700ec-123">Windows 10</span></span>

<span data-ttu-id="700ec-124">Outre le mode de déploiement traditionnel des appareils de récréation d’image, les administrateurs désireux de mettre à jour les appareils de surface exécutant Windows 8,1 ou Windows 10 peuvent choisir de déployer des mises à niveau.</span><span class="sxs-lookup"><span data-stu-id="700ec-124">In addition to the traditional deployment method of reimaging devices, administrators who want to upgrade Surface devices that are running Windows 8.1 or Windows 10 have the option of deploying upgrades.</span></span> <span data-ttu-id="700ec-125">En effectuant un déploiement de mise à niveau, Windows 10 peut être appliqué aux appareils sans suppression des utilisateurs, des applications ou de la configuration.</span><span class="sxs-lookup"><span data-stu-id="700ec-125">By performing an upgrade deployment, Windows 10 can be applied to devices without removing users, apps, or configuration.</span></span> <span data-ttu-id="700ec-126">Les utilisateurs des appareils déployés peuvent simplement continuer à utiliser les appareils avec les mêmes applications et paramètres que ceux utilisés avant la mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="700ec-126">The users of the deployed devices can simply continue using the devices with the same apps and settings that they used prior to the upgrade.</span></span> 

<span data-ttu-id="700ec-127">Pour plus d’informations sur la mise à niveau de périphériques surface à l’aide de MDT, voir [effectuer une mise à niveau sur place vers Windows 10 avec MDT](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/upgrade-to-windows-10-with-the-microsoft-deployment-toolkit).</span><span class="sxs-lookup"><span data-stu-id="700ec-127">For the latest information about upgrading surface devices using MDT, refer to [Perform an in-place upgrade to Windows 10 with MDT](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/upgrade-to-windows-10-with-the-microsoft-deployment-toolkit).</span></span>

