---
title: Mettre en œuvre la qualité de service sur SurfaceHub
ms.reviewer: ''
manager: laurawi
description: Apprenez à configurer la qualité de service (QoS) sur surface Hub.
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: 99172e77be260559c770f5fc8a1438734bed660f
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832910"
---
# <span data-ttu-id="fec71-103">Mettre en œuvre la qualité de service (QoS) sur surface Hub</span><span class="sxs-lookup"><span data-stu-id="fec71-103">Implement Quality of Service (QoS) on Surface Hub</span></span>

<span data-ttu-id="fec71-104">La qualité de service (QoS) est une combinaison de technologies réseau qui permet aux administrateurs d’optimiser l’utilisation de communications audio/vidéo et de partage d’application en temps réel.</span><span class="sxs-lookup"><span data-stu-id="fec71-104">Quality of Service (QoS) is a combination of network technologies that allows the administrators to optimize the experience of real time audio/video and application sharing communications.</span></span>
 
<span data-ttu-id="fec71-105">La configuration [de la qualité de service (QoS) pour Skype entreprise](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp) sur surface Hub peut être réalisée à l’aide de votre [fournisseur de gestion des périphériques mobiles (GPM)](manage-settings-with-mdm-for-surface-hub.md) ou d’un [package de mise](provisioning-packages-for-surface-hub.md)à niveau.</span><span class="sxs-lookup"><span data-stu-id="fec71-105">Configuring [QoS for Skype for Business](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp) on the Surface Hub can be done using your [mobile device management (MDM) provider](manage-settings-with-mdm-for-surface-hub.md) or through a [provisioning package](provisioning-packages-for-surface-hub.md).</span></span> 
 
 
<span data-ttu-id="fec71-106">Cette procédure vous explique comment configurer la qualité de service (QoS) pour surface Hub à l’aide de Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="fec71-106">This procedure explains how to configure QoS for Surface Hub using Microsoft Intune.</span></span> 

1. <span data-ttu-id="fec71-107">Dans Intune, [créez une stratégie personnalisée](https://docs.microsoft.com/intune/custom-settings-configure).</span><span class="sxs-lookup"><span data-stu-id="fec71-107">In Intune, [create a custom policy](https://docs.microsoft.com/intune/custom-settings-configure).</span></span>

    ![Capture d’écran de la boîte de dialogue de création d’une stratégie personnalisée dans Intune](images/qos-create.png)

2. <span data-ttu-id="fec71-109">Dans **les paramètres d’URI OMA personnalisés**, sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="fec71-109">In **Custom OMA-URI Settings**, select **Add**.</span></span> <span data-ttu-id="fec71-110">Pour chaque paramètre que vous ajoutez, vous devez entrer un nom, une description (facultatif), un type de données, un URI OMA et une valeur.</span><span class="sxs-lookup"><span data-stu-id="fec71-110">For each setting that you add, you will enter a name, description (optional), data type, OMA-URI, and value.</span></span>

    ![Capture d’écran de la boîte de dialogue paramètre d’URI OMA vide](images/qos-setting.png)

3. <span data-ttu-id="fec71-112">Ajoutez les paramètres d’URI OMA personnalisés suivants:</span><span class="sxs-lookup"><span data-stu-id="fec71-112">Add the following custom OMA-URI settings:</span></span>

    <span data-ttu-id="fec71-113">Nom</span><span class="sxs-lookup"><span data-stu-id="fec71-113">Name</span></span> | <span data-ttu-id="fec71-114">Type de données</span><span class="sxs-lookup"><span data-stu-id="fec71-114">Data type</span></span> | <span data-ttu-id="fec71-115">OMA-URI</span><span class="sxs-lookup"><span data-stu-id="fec71-115">OMA-URI</span></span><br><span data-ttu-id="fec71-116">./Device/Vendor/MSFT/NetworkQoSPolicy</span><span class="sxs-lookup"><span data-stu-id="fec71-116">./Device/Vendor/MSFT/NetworkQoSPolicy</span></span> |  <span data-ttu-id="fec71-117">Valeur</span><span class="sxs-lookup"><span data-stu-id="fec71-117">Value</span></span>
    --- | --- | --- | ---
    <span data-ttu-id="fec71-118">Port source audio</span><span class="sxs-lookup"><span data-stu-id="fec71-118">Audio Source Port</span></span> | <span data-ttu-id="fec71-119">String</span><span class="sxs-lookup"><span data-stu-id="fec71-119">String</span></span> |  <span data-ttu-id="fec71-120">/HubAudio/SourcePortMatchCondition</span><span class="sxs-lookup"><span data-stu-id="fec71-120">/HubAudio/SourcePortMatchCondition</span></span>  |   <span data-ttu-id="fec71-121">Obtenez les valeurs de votre administrateur Skype</span><span class="sxs-lookup"><span data-stu-id="fec71-121">Get the values from your Skype administrator</span></span>
    <span data-ttu-id="fec71-122">Valeur DSCP de l’audio</span><span class="sxs-lookup"><span data-stu-id="fec71-122">Audio DSCP</span></span> | <span data-ttu-id="fec71-123">Integer</span><span class="sxs-lookup"><span data-stu-id="fec71-123">Integer</span></span> |  <span data-ttu-id="fec71-124">/HubAudio/DSCPAction</span><span class="sxs-lookup"><span data-stu-id="fec71-124">/HubAudio/DSCPAction</span></span>  |   <span data-ttu-id="fec71-125">46</span><span class="sxs-lookup"><span data-stu-id="fec71-125">46</span></span>
    <span data-ttu-id="fec71-126">Port source vidéo</span><span class="sxs-lookup"><span data-stu-id="fec71-126">Video Source Port</span></span> | <span data-ttu-id="fec71-127">String</span><span class="sxs-lookup"><span data-stu-id="fec71-127">String</span></span> |  <span data-ttu-id="fec71-128">/HubVideo/SourcePortMatchCondition</span><span class="sxs-lookup"><span data-stu-id="fec71-128">/HubVideo/SourcePortMatchCondition</span></span>   |  <span data-ttu-id="fec71-129">Obtenez les valeurs de votre administrateur Skype</span><span class="sxs-lookup"><span data-stu-id="fec71-129">Get the values from your Skype administrator</span></span>
    <span data-ttu-id="fec71-130">Valeur DSCP de la vidéo</span><span class="sxs-lookup"><span data-stu-id="fec71-130">Video DSCP</span></span> | <span data-ttu-id="fec71-131">Integer</span><span class="sxs-lookup"><span data-stu-id="fec71-131">Integer</span></span> |  <span data-ttu-id="fec71-132">/HubVideo/DSCPAction</span><span class="sxs-lookup"><span data-stu-id="fec71-132">/HubVideo/DSCPAction</span></span>   |   <span data-ttu-id="fec71-133">34</span><span class="sxs-lookup"><span data-stu-id="fec71-133">34</span></span>
    <span data-ttu-id="fec71-134">Nom du processus audio</span><span class="sxs-lookup"><span data-stu-id="fec71-134">Audio Process Name</span></span> | <span data-ttu-id="fec71-135">String</span><span class="sxs-lookup"><span data-stu-id="fec71-135">String</span></span> |  <span data-ttu-id="fec71-136">/HubAudio/AppPathNameMatchCondition</span><span class="sxs-lookup"><span data-stu-id="fec71-136">/HubAudio/AppPathNameMatchCondition</span></span>  |   <span data-ttu-id="fec71-137">Microsoft.PPISkype.Windows.exe</span><span class="sxs-lookup"><span data-stu-id="fec71-137">Microsoft.PPISkype.Windows.exe</span></span>
    <span data-ttu-id="fec71-138">Nom de processus vidéo</span><span class="sxs-lookup"><span data-stu-id="fec71-138">Video Process Name</span></span> | <span data-ttu-id="fec71-139">String</span><span class="sxs-lookup"><span data-stu-id="fec71-139">String</span></span> |  <span data-ttu-id="fec71-140">/HubVideo/AppPathNameMatchCondition</span><span class="sxs-lookup"><span data-stu-id="fec71-140">/HubVideo/AppPathNameMatchCondition</span></span>  |   <span data-ttu-id="fec71-141">Microsoft.PPISkype.Windows.exe</span><span class="sxs-lookup"><span data-stu-id="fec71-141">Microsoft.PPISkype.Windows.exe</span></span>

    >[!IMPORTANT]
    ><span data-ttu-id="fec71-142">Chaque chemin d’accès de l' **URI OMA** commence par `./Device/Vendor/MSFT/NetworkQoSPolicy` .</span><span class="sxs-lookup"><span data-stu-id="fec71-142">Each **OMA-URI** path begins with `./Device/Vendor/MSFT/NetworkQoSPolicy`.</span></span> <span data-ttu-id="fec71-143">Le chemin d’accès complet du paramètre de port source audio, par exemple, sera `./Device/Vendor/MSFT/NetworkQoSPolicy/HubAudio/SourcePortMatchCondition` .</span><span class="sxs-lookup"><span data-stu-id="fec71-143">The full path for the audio source port setting, for example, will be `./Device/Vendor/MSFT/NetworkQoSPolicy/HubAudio/SourcePortMatchCondition`.</span></span>




4. <span data-ttu-id="fec71-144">Lorsque la stratégie a été créée, [déployez-la sur surface Hub.](manage-settings-with-mdm-for-surface-hub.md#manage-surface-hub-settings-with-mdm)</span><span class="sxs-lookup"><span data-stu-id="fec71-144">When the policy has been created, [deploy it to the Surface Hub.](manage-settings-with-mdm-for-surface-hub.md#manage-surface-hub-settings-with-mdm)</span></span>


>[!WARNING]
><span data-ttu-id="fec71-145">Pour le moment, vous ne pouvez pas configurer le paramètre **IPProtocolMatchCondition** dans le [CSP NetworkQoSPolicy](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp).</span><span class="sxs-lookup"><span data-stu-id="fec71-145">Currently, you cannot configure the setting **IPProtocolMatchCondition** in the [NetworkQoSPolicy CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp).</span></span> <span data-ttu-id="fec71-146">Si ce paramètre est configuré, la stratégie ne sera pas appliquée.</span><span class="sxs-lookup"><span data-stu-id="fec71-146">If this setting is configured, the policy will fail to apply.</span></span>
 
