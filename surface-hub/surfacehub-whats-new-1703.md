---
title: Nouveautés de Windows10 version1703 pour Surface Hub
description: Windows10 version1703 (Creators Update) apporte de nouvelles fonctionnalités à MicrosoftSurface Hub.
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 01/18/2018
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: 722309a6b018c32bde329cb7b2cdd68b859fc1ca
ms.sourcegitcommit: 8e809e8481023fe4421abcdaa1e055a6f2f74f5f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/11/2020
ms.locfileid: "10924940"
---
# <span data-ttu-id="2af94-103">Quelles sont les nouveautés dans Windows10, version 1703 pour Microsoft Surface Hub?</span><span class="sxs-lookup"><span data-stu-id="2af94-103">What's new in Windows 10, version 1703 for Microsoft Surface Hub?</span></span>

<span data-ttu-id="2af94-104">Regardez l'ingénieur de Surface Hub Jordan Marchese nous présenter les mises à jour de MicrosoftSurface Hub qui paraissent avec Windows10, version1703 (Creators Update).</span><span class="sxs-lookup"><span data-stu-id="2af94-104">Watch Surface Hub engineer Jordan Marchese present updates to Microsoft Surface Hub with Windows 10, version 1703 (Creators Update).</span></span> 

<a href="https://www.youtube.com/watch?v=R8tX10VIgq0" target="_blank"> <img src="images/whats-new-video-thumbnail.png" alt="Link to Surface Hub video on Youtube" /></a>

<span data-ttu-id="2af94-105">Windows10 version1703 (également appelée Creators Update) présente les modifications suivantes pour MicrosoftSurface Hub.</span><span class="sxs-lookup"><span data-stu-id="2af94-105">Windows 10, version 1703 (also called the Creators Update), introduces the following changes for Microsoft Surface Hub.</span></span>

## <span data-ttu-id="2af94-106">Nouveaux paramètres</span><span class="sxs-lookup"><span data-stu-id="2af94-106">New settings</span></span>

<span data-ttu-id="2af94-107">Des paramètres ont été ajoutés à la gestion des périphériques mobiles (GPM) et aux fournisseurs de services de configuration (CSP) pour développer les fonctionnalités de gestion de Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="2af94-107">Settings have been added to mobile device management (MDM) and configuration service providers (CSPs) to expand the Surface Hub management capabilities.</span></span> <span data-ttu-id="2af94-108">[Les nouveaux paramètres sont notamment les suivants](manage-settings-with-mdm-for-surface-hub.md):</span><span class="sxs-lookup"><span data-stu-id="2af94-108">[New settings include](manage-settings-with-mdm-for-surface-hub.md):</span></span>

- <span data-ttu-id="2af94-109">InBoxApps/SkypeForBusiness/DomainName</span><span class="sxs-lookup"><span data-stu-id="2af94-109">InBoxApps/SkypeForBusiness/DomainName</span></span>
- <span data-ttu-id="2af94-110">InBoxApps/Connect/AutoLaunch</span><span class="sxs-lookup"><span data-stu-id="2af94-110">InBoxApps/Connect/AutoLaunch</span></span>
- <span data-ttu-id="2af94-111">Properties/DefaultVolume</span><span class="sxs-lookup"><span data-stu-id="2af94-111">Properties/DefaultVolume</span></span>
- <span data-ttu-id="2af94-112">Properties/ScreenTimeout</span><span class="sxs-lookup"><span data-stu-id="2af94-112">Properties/ScreenTimeout</span></span>
- <span data-ttu-id="2af94-113">Properties/SessionTimeout</span><span class="sxs-lookup"><span data-stu-id="2af94-113">Properties/SessionTimeout</span></span>
- <span data-ttu-id="2af94-114">Properties/SleepTimeout</span><span class="sxs-lookup"><span data-stu-id="2af94-114">Properties/SleepTimeout</span></span>
- <span data-ttu-id="2af94-115">Properties/AllowSessionResume</span><span class="sxs-lookup"><span data-stu-id="2af94-115">Properties/AllowSessionResume</span></span>
- <span data-ttu-id="2af94-116">Properties/AllowAutoProxyAuth</span><span class="sxs-lookup"><span data-stu-id="2af94-116">Properties/AllowAutoProxyAuth</span></span>
- <span data-ttu-id="2af94-117">Properties/DisableSigninSuggestions</span><span class="sxs-lookup"><span data-stu-id="2af94-117">Properties/DisableSigninSuggestions</span></span>
- <span data-ttu-id="2af94-118">Properties/DoNotShowMyMeetingsAndFiles</span><span class="sxs-lookup"><span data-stu-id="2af94-118">Properties/DoNotShowMyMeetingsAndFiles</span></span>
- <span data-ttu-id="2af94-119">System/AllowStorageCard</span><span class="sxs-lookup"><span data-stu-id="2af94-119">System/AllowStorageCard</span></span>

<span data-ttu-id="2af94-120">En plus des paramètres fondés sur les nouveaux [CSP NetworkQoSPolicy](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/networkqospolicy-csp) et [CSP NetworkProxy](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/networkproxy-csp).</span><span class="sxs-lookup"><span data-stu-id="2af94-120">Plus settings based on the new [NetworkQoSPolicy CSP](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/networkqospolicy-csp) and [NetworkProxy CSP](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/networkproxy-csp).</span></span>
</br>

## <span data-ttu-id="2af94-121">Assistant d’approvisionnement</span><span class="sxs-lookup"><span data-stu-id="2af94-121">Provisioning wizard</span></span>

<span data-ttu-id="2af94-122">Un assistant simple d’utilisation vous permet de créer rapidement des packages d’approvisionnement que vous pouvez appliquer à plusieurs appareils Surface Hub. Il inclut une jonction à Azure ActiveDirectory en bloc.</span><span class="sxs-lookup"><span data-stu-id="2af94-122">An easy-to-use wizard helps you quickly create provisioning packages that you can apply to multiple Surface Hub devices, and includes bulk join to Azure Active Directory.</span></span> [<span data-ttu-id="2af94-123">Découvrez comment créer un package d’approvisionnement pour Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="2af94-123">Learn how to create a provisioning package for Surface Hub.</span></span>](provisioning-packages-for-certificates-surface-hub.md)

![étapes de l’Assistant d’approvisionnement d’appareils Surface Hub](images/wcd-wizard.png)
    
## <span data-ttu-id="2af94-125">Miracast sur votre réseau local ou réseau sans fil existant</span><span class="sxs-lookup"><span data-stu-id="2af94-125">Miracast on your existing wireless network or LAN</span></span> 

<span data-ttu-id="2af94-126">Microsoft a étendu la possibilité [d’envoyer un flux Miracast sur un réseau local](miracast-over-infrastructure.md) plutôt que sur une liaison sans fil directe.</span><span class="sxs-lookup"><span data-stu-id="2af94-126">Microsoft has extended the ability to [send a Miracast stream over a local network](miracast-over-infrastructure.md) rather than over a direct wireless link.</span></span> 
    
## <span data-ttu-id="2af94-127">Récupération sur le cloud</span><span class="sxs-lookup"><span data-stu-id="2af94-127">Cloud recovery</span></span>

<span data-ttu-id="2af94-128">Lorsque vous réinitialisez un appareil Surface Hub, vous avez désormais la possibilité de télécharger et d’installer une version d’usine du système d’exploitation à partir du cloud.</span><span class="sxs-lookup"><span data-stu-id="2af94-128">When you reset a Surface Hub device, you now have the ability to download and install a factory build of the operating system from the cloud.</span></span> [<span data-ttu-id="2af94-129">En savoir plus sur la récupération sur le cloud.</span><span class="sxs-lookup"><span data-stu-id="2af94-129">Learn more about cloud recovery.</span></span>](device-reset-surface-hub.md#cloud-recovery)

>[!NOTE]
><span data-ttu-id="2af94-130">La récupération sur le cloud ne fonctionne pas si vous utilisez des serveurs proxy.</span><span class="sxs-lookup"><span data-stu-id="2af94-130">Cloud recovery doesn't work if you use proxy servers.</span></span>
    
![Réinstaller](images/reinstall.png)
    
## <span data-ttu-id="2af94-132">Terminer la session</span><span class="sxs-lookup"><span data-stu-id="2af94-132">End session</span></span>

<span data-ttu-id="2af94-133">**J’ai terminé** a été remplacé par **Terminer la session**.</span><span class="sxs-lookup"><span data-stu-id="2af94-133">**I'm done** is now **End session**.</span></span> [<span data-ttu-id="2af94-134">Découvrez comment utiliser Terminer la session.</span><span class="sxs-lookup"><span data-stu-id="2af94-134">Learn how to use End session.</span></span>](finishing-your-surface-hub-meeting.md) 

![terminer la session](images/end-session.png)



 

 
