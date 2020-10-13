---
title: Comment activer la mise en éveil pour surface
ms.author: v-todmc
author: mccoybot
ms.date: 7/30/2020
audience: ITPro
search.appverid:
- SPO160
- MET150
appliesto:
- Surface Book 3
- Surface Pro 7
- Surface Laptop 3
- Surface Pro X
- Surface Laptop Go
ms.custom:
- CI 121602
ms.reviewer: hachidan
description: Décrit comment activer et désactiver la mise en éveil pour les appareils surface.
keywords: mise à jour, déploiement, pilote, WOL, Wake-on-LAN
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
ms.localizationpriority: medium
ms.topic: article
manager: laurawi
ms.audience: itpro
ms.openlocfilehash: dee2a2962cf6b70a1bf11cf597b4d41f4b5568e4
ms.sourcegitcommit: c1efb75e8524193bdc0a5f7496dc23a92ac665c8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/12/2020
ms.locfileid: "11114572"
---
# <span data-ttu-id="ce775-104">Wake on Power pour les appareils Surface</span><span class="sxs-lookup"><span data-stu-id="ce775-104">Wake on Power for Surface devices</span></span>

<span data-ttu-id="ce775-105">Les appareils surface peuvent être éteints lorsque vous n’êtes pas sur votre bureau, ou en mode hibernation pour économiser l’autonomie de la batterie.</span><span class="sxs-lookup"><span data-stu-id="ce775-105">Surface devices can be powered off while you're away from your desk, or set to hibernate mode to save battery life.</span></span> <span data-ttu-id="ce775-106">Pour améliorer la gestion de ces appareils, l’éveil à la consommation permet aux périphériques de surface compatibles de démarrer automatiquement lorsqu’ils sont reconnectés à l’alimentation.</span><span class="sxs-lookup"><span data-stu-id="ce775-106">To improve the manageability of these devices, Wake on Power enables compatible Surface devices to automatically start when they're reconnected to power.</span></span> <span data-ttu-id="ce775-107">Pour configurer la mise en éveil, vous pouvez utiliser le mode de gestion de surface Enterprise (SEMM) via le configurateur de surface ou le gestionnaire UEFI.</span><span class="sxs-lookup"><span data-stu-id="ce775-107">To configure Wake on Power, you can use Surface Enterprise Management Mode (SEMM) either through Surface UEFI Configurator or the UEFI Manager.</span></span>

<span data-ttu-id="ce775-108">La fonctionnalité de mise en éveil est disponible sur les appareils suivants:</span><span class="sxs-lookup"><span data-stu-id="ce775-108">The Wake on Power feature is available on the following devices:</span></span>

- <span data-ttu-id="ce775-109">SurfaceBook3</span><span class="sxs-lookup"><span data-stu-id="ce775-109">Surface Book 3</span></span>
- <span data-ttu-id="ce775-110">SurfacePro7</span><span class="sxs-lookup"><span data-stu-id="ce775-110">Surface Pro 7</span></span>
- <span data-ttu-id="ce775-111">Surface Laptop3</span><span class="sxs-lookup"><span data-stu-id="ce775-111">Surface Laptop 3</span></span>
- <span data-ttu-id="ce775-112">Surface Laptop Go</span><span class="sxs-lookup"><span data-stu-id="ce775-112">Surface Laptop Go</span></span>
- <span data-ttu-id="ce775-113">SurfaceProX</span><span class="sxs-lookup"><span data-stu-id="ce775-113">Surface Pro X</span></span> 


## <span data-ttu-id="ce775-114">Présentation et configuration requise</span><span class="sxs-lookup"><span data-stu-id="ce775-114">Overview and prerequisites</span></span>

<span data-ttu-id="ce775-115">Le Configurator du Configurateur de surface vous permet d’enregistrer les paramètres UEFI individuels d’un package Windows Installer. msi à des fins de distribution à des appareils cibles.</span><span class="sxs-lookup"><span data-stu-id="ce775-115">Surface UEFI Configurator lets you save individual UEFI settings in a Windows Installer .msi package for distribution to target devices.</span></span> 

> [!NOTE]
> <span data-ttu-id="ce775-116">Cet article part du principe que vous savez comment utiliser SEMM.</span><span class="sxs-lookup"><span data-stu-id="ce775-116">This article assumes that you know how to use SEMM.</span></span> <span data-ttu-id="ce775-117">Pour plus d’informations, reportez-vous à la documentation du [mode de gestion des entreprises de surface (SEMM)](surface-enterprise-management-mode.md) .</span><span class="sxs-lookup"><span data-stu-id="ce775-117">For more information, see [Surface Enterprise Management Mode (SEMM)](surface-enterprise-management-mode.md) documentation.</span></span>

## <span data-ttu-id="ce775-118">Pour activer la mise en éveil</span><span class="sxs-lookup"><span data-stu-id="ce775-118">To enable Wake on Power</span></span>

1.  <span data-ttu-id="ce775-119">Téléchargez la version la plus récente de [surface Configurator Configurator](https://www.microsoft.com/download/confirmation.aspx?id=46703).</span><span class="sxs-lookup"><span data-stu-id="ce775-119">Download the latest version of [Surface UEFI Configurator](https://www.microsoft.com/download/confirmation.aspx?id=46703).</span></span>
2.  <span data-ttu-id="ce775-120">Connectez-vous à votre périphérique surface en tant qu’administrateur, ouvrez le **Configurateur de surface UEFI**, sélectionnez **appareils surface**, puis sélectionnez **suivant**.</span><span class="sxs-lookup"><span data-stu-id="ce775-120">Sign in to your Surface device as an administrator, open **Surface UEFI Configurator**, select **Surface Devices**, and then select **Next**.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-1.png" alt-text="Sélectionnez périphériques surface, puis sélectionnez suivant.":::
3.  <span data-ttu-id="ce775-122">Sélectionnez **Démarrer**, puis cliquez sur **créer** sous **package de configuration**.</span><span class="sxs-lookup"><span data-stu-id="ce775-122">Select **Start**, and then select **Create** under **Configuration Package**.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-2.png" alt-text="Sélectionnez périphériques surface, puis sélectionnez suivant.":::
4.  <span data-ttu-id="ce775-124">Sélectionnez **protection de certificat**, puis ajoutez votre fichier Certificate. pfx.</span><span class="sxs-lookup"><span data-stu-id="ce775-124">Select **Certificate Protection**, and add your certificate .pfx file.</span></span> 
5. <span data-ttu-id="ce775-125">Entrez votre mot de passe, sélectionnez **suivant**, ajoutez une **protection par mot de passe**, le cas échéant, puis sélectionnez **suivant**.</span><span class="sxs-lookup"><span data-stu-id="ce775-125">Enter your password, select **Next**, add **Password Protection**, as appropriate, and then select **Next**.</span></span>
6.  <span data-ttu-id="ce775-126">Dans la page **sélectionnez le type de surface que vous souhaitez cibler** , sélectionnez les appareils cibles appropriés.</span><span class="sxs-lookup"><span data-stu-id="ce775-126">On the **Choose which Surface type you want to target** page, select your target devices as appropriate.</span></span> <span data-ttu-id="ce775-127">Par exemple, sélectionnez **surface Pro 7**.</span><span class="sxs-lookup"><span data-stu-id="ce775-127">For example, select **Surface Pro 7**.</span></span>
7.  <span data-ttu-id="ce775-128">Sur la page **fonctionnalités avancées** , sélectionnez **mise en éveil** **, activez la fonctionnalité, puis**sélectionnez **suivant**.</span><span class="sxs-lookup"><span data-stu-id="ce775-128">On the **Advanced Features** page, select **Wake on Power**, set the feature to **On**, and then select **Next**.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-3.png" alt-text="Sélectionnez périphériques surface, puis sélectionnez suivant."::: 
8.  <span data-ttu-id="ce775-130">Dans la page **réussite** , sélectionnez **fin**.</span><span class="sxs-lookup"><span data-stu-id="ce775-130">On the **Successful** page, select **End**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ce775-131">S’il s’agit de la première fois que vous fournissez des paramètres à votre appareil, vous serez invité à fournir également les deux derniers caractères de l’empreinte du certificat.</span><span class="sxs-lookup"><span data-stu-id="ce775-131">If this is the first time that you are providing settings to your device, you will be prompted to also provide the last two characters of the certificate thumbprint.</span></span> 
9.  <span data-ttu-id="ce775-132">Enregistrez le package. msi.</span><span class="sxs-lookup"><span data-stu-id="ce775-132">Save the .msi package.</span></span> 

## <span data-ttu-id="ce775-133">Appliquer le package MSI</span><span class="sxs-lookup"><span data-stu-id="ce775-133">Apply the MSI package</span></span> 

<span data-ttu-id="ce775-134">Vous pouvez appliquer le package MSI aux appareils de votre réseau à l’aide d’outils de distribution de logiciels tels que Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="ce775-134">You can apply the MSI package to devices across your network by using software distribution tools such as Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="ce775-135">Cette procédure inclut les étapes permettant d’installer le package sur votre ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="ce775-135">This procedure includes steps to install the package on your local computer.</span></span> 

1.  <span data-ttu-id="ce775-136">À l’invite de commandes avec élévation de privilèges, entrez le chemin d’accès complet du fichier. msi pour exécuter le package. msi.</span><span class="sxs-lookup"><span data-stu-id="ce775-136">At an elevated command prompt, enter the full path of the .msi file to run the .msi package.</span></span> 

    ```
    C:\SEMM\wake-on-power.msi 
    ```

2.  <span data-ttu-id="ce775-137">Dans la boîte de dialogue d' **Avertissement** , sélectionnez **OK** ou désactiver BitLocker, selon le cas.</span><span class="sxs-lookup"><span data-stu-id="ce775-137">In the **Warning** dialog box, select **OK** or disable BitLocker, as appropriate.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-4.png" alt-text="Sélectionnez périphériques surface, puis sélectionnez suivant.":::
3.  <span data-ttu-id="ce775-139">Dans la page d’accueil, sélectionnez **Next (suivant** ) pour exécuter le package et appliquer le paramètre UEFI nouvellement configuré.</span><span class="sxs-lookup"><span data-stu-id="ce775-139">On the Welcome page, select **Next** to run the package and apply the newly configured UEFI setting.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-5.png" alt-text="Sélectionnez périphériques surface, puis sélectionnez suivant.":::
4.  <span data-ttu-id="ce775-141">Redémarrez votre appareil.</span><span class="sxs-lookup"><span data-stu-id="ce775-141">Restart your device.</span></span> 

<span data-ttu-id="ce775-142">La mise en éveil est désormais configurée.</span><span class="sxs-lookup"><span data-stu-id="ce775-142">Wake on Power is now configured.</span></span> <span data-ttu-id="ce775-143">Pour tester les paramètres, éteignez votre appareil, débranchez le cordon d’alimentation, puis rebranchez le cordon d’alimentation.</span><span class="sxs-lookup"><span data-stu-id="ce775-143">To test the settings, turn off your device, disconnect the power, and then reconnect the power.</span></span> <span data-ttu-id="ce775-144">Le périphérique doit démarrer automatiquement.</span><span class="sxs-lookup"><span data-stu-id="ce775-144">The device should start automatically.</span></span> 

## <span data-ttu-id="ce775-145">Références</span><span class="sxs-lookup"><span data-stu-id="ce775-145">References</span></span>

<span data-ttu-id="ce775-146">Pour plus d’informations, consultez les articles suivants.</span><span class="sxs-lookup"><span data-stu-id="ce775-146">For more information, see the following articles.</span></span> 

- [<span data-ttu-id="ce775-147">Mode de gestion SurfaceEnterprise</span><span class="sxs-lookup"><span data-stu-id="ce775-147">Surface Enterprise Management Mode</span></span>](surface-enterprise-management-mode.md)
- [<span data-ttu-id="ce775-148">Wake on LAN pour les appareils surface</span><span class="sxs-lookup"><span data-stu-id="ce775-148">Wake on LAN for Surface devices</span></span>](wake-on-lan-for-surface-devices.md)

<span data-ttu-id="ce775-149">Encore besoin d’aide?</span><span class="sxs-lookup"><span data-stu-id="ce775-149">Still need help?</span></span> <span data-ttu-id="ce775-150">Accédez à la [communauté Microsoft](https://answers.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="ce775-150">Go to [Microsoft Community](https://answers.microsoft.com/).</span></span>