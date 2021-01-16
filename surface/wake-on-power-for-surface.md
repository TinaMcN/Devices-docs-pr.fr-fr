---
title: Comment activer Wake on Power pour Surface
ms.author: v-todmc
author: mccoybot
audience: ITPro
search.appverid:
- SPO160
- MET150
appliesto:
- Surface Book 3
- Surface Pro 7+
- Surface Pro 7
- Surface Laptop 3
- Surface Pro X
- Surface Laptop Go
ms.custom:
- CI 121602
ms.reviewer: hachidan
description: Décrit comment activer et désactiver la fonction Wake on Power pour les appareils Surface.
keywords: mettre à jour, déployer, pilote, wake-on-lan
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
ms.localizationpriority: medium
ms.topic: article
manager: laurawi
ms.audience: itpro
ms.date: 01/15/2021
ms.openlocfilehash: 6ad359861f6af29c567bf0fbf26878ec15c7c642
ms.sourcegitcommit: 1053479c191fd10651d31a466fad1769fb0cd28b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/16/2021
ms.locfileid: "11271558"
---
# <span data-ttu-id="385ed-104">Wake on Power pour les appareils Surface</span><span class="sxs-lookup"><span data-stu-id="385ed-104">Wake on Power for Surface devices</span></span>

<span data-ttu-id="385ed-105">Les appareils Surface peuvent être éteints lorsque vous êtes absent de votre bureau ou en mode veille prolongée pour économiser l’autonomie de la batterie.</span><span class="sxs-lookup"><span data-stu-id="385ed-105">Surface devices can be powered off while you're away from your desk, or set to hibernate mode to save battery life.</span></span> <span data-ttu-id="385ed-106">Pour améliorer la gestion de ces appareils, Wake on Power permet aux appareils Surface compatibles de démarrer automatiquement lorsqu’ils sont reconnectés à l’alimentation.</span><span class="sxs-lookup"><span data-stu-id="385ed-106">To improve the manageability of these devices, Wake on Power enables compatible Surface devices to automatically start when they're reconnected to power.</span></span> <span data-ttu-id="385ed-107">Pour configurer Wake on Power, vous pouvez utiliser le mode SEMM (Surface Enterprise Management Mode) via le configurateur UEFI Surface ou le Gestionnaire UEFI.</span><span class="sxs-lookup"><span data-stu-id="385ed-107">To configure Wake on Power, you can use Surface Enterprise Management Mode (SEMM) either through Surface UEFI Configurator or the UEFI Manager.</span></span>

<span data-ttu-id="385ed-108">La fonctionnalité Veille sur l’alimentation est disponible sur les appareils suivants :</span><span class="sxs-lookup"><span data-stu-id="385ed-108">The Wake on Power feature is available on the following devices:</span></span>

- <span data-ttu-id="385ed-109">Surface Pro 7+</span><span class="sxs-lookup"><span data-stu-id="385ed-109">Surface Pro 7+</span></span>
- <span data-ttu-id="385ed-110">SurfaceBook3</span><span class="sxs-lookup"><span data-stu-id="385ed-110">Surface Book 3</span></span>
- <span data-ttu-id="385ed-111">SurfacePro7</span><span class="sxs-lookup"><span data-stu-id="385ed-111">Surface Pro 7</span></span>
- <span data-ttu-id="385ed-112">Surface Laptop3</span><span class="sxs-lookup"><span data-stu-id="385ed-112">Surface Laptop 3</span></span>
- <span data-ttu-id="385ed-113">Surface Laptop Go</span><span class="sxs-lookup"><span data-stu-id="385ed-113">Surface Laptop Go</span></span>
- <span data-ttu-id="385ed-114">SurfaceProX</span><span class="sxs-lookup"><span data-stu-id="385ed-114">Surface Pro X</span></span> 


## <span data-ttu-id="385ed-115">Vue d’ensemble et conditions préalables</span><span class="sxs-lookup"><span data-stu-id="385ed-115">Overview and prerequisites</span></span>

<span data-ttu-id="385ed-116">Surface UEFI Configurator vous permet d’enregistrer des paramètres UEFI individuels dans un package .msi Windows Installer pour la distribution sur les appareils cibles.</span><span class="sxs-lookup"><span data-stu-id="385ed-116">Surface UEFI Configurator lets you save individual UEFI settings in a Windows Installer .msi package for distribution to target devices.</span></span> 

> [!NOTE]
> <span data-ttu-id="385ed-117">Cet article suppose que vous savez utiliser SEMM.</span><span class="sxs-lookup"><span data-stu-id="385ed-117">This article assumes that you know how to use SEMM.</span></span> <span data-ttu-id="385ed-118">Pour plus d’informations, voir la documentation [seMM (Surface Enterprise Management Mode).](surface-enterprise-management-mode.md)</span><span class="sxs-lookup"><span data-stu-id="385ed-118">For more information, see [Surface Enterprise Management Mode (SEMM)](surface-enterprise-management-mode.md) documentation.</span></span>

## <span data-ttu-id="385ed-119">Pour activer Wake on Power</span><span class="sxs-lookup"><span data-stu-id="385ed-119">To enable Wake on Power</span></span>

1.  <span data-ttu-id="385ed-120">Téléchargez la dernière version de [Surface UEFI Configurator](https://www.microsoft.com/download/confirmation.aspx?id=46703).</span><span class="sxs-lookup"><span data-stu-id="385ed-120">Download the latest version of [Surface UEFI Configurator](https://www.microsoft.com/download/confirmation.aspx?id=46703).</span></span>
2.  <span data-ttu-id="385ed-121">Connectez-vous à votre appareil Surface en tant qu’administrateur, ouvrez **le configurateur UEFI Surface,** sélectionnez **Appareils Surface,** puis sélectionnez **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="385ed-121">Sign in to your Surface device as an administrator, open **Surface UEFI Configurator**, select **Surface Devices**, and then select **Next**.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-1.png" alt-text="Sélectionnez Appareils Surface et Suivant.":::
3.  <span data-ttu-id="385ed-123">Sélectionnez **Démarrer,** puis **créez sous** **Package de configuration.**</span><span class="sxs-lookup"><span data-stu-id="385ed-123">Select **Start**, and then select **Create** under **Configuration Package**.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-2.png" alt-text="Sélectionnez Créer un package de configuration.":::
4.  <span data-ttu-id="385ed-125">Sélectionnez **Protection des**certificats et ajoutez votre fichier .pfx de certificat.</span><span class="sxs-lookup"><span data-stu-id="385ed-125">Select **Certificate Protection**, and add your certificate .pfx file.</span></span> 
5. <span data-ttu-id="385ed-126">Entrez votre mot de passe, **sélectionnez Suivant,** ajoutez **la protection par**mot de passe, le cas échéant, puis sélectionnez **Suivant.**</span><span class="sxs-lookup"><span data-stu-id="385ed-126">Enter your password, select **Next**, add **Password Protection**, as appropriate, and then select **Next**.</span></span>
6.  <span data-ttu-id="385ed-127">Dans la page Choisir le type de surface que **vous souhaitez cibler,** sélectionnez vos appareils cibles selon le cas.</span><span class="sxs-lookup"><span data-stu-id="385ed-127">On the **Choose which Surface type you want to target** page, select your target devices as appropriate.</span></span> <span data-ttu-id="385ed-128">Par exemple, **sélectionnez Surface Pro 7.**</span><span class="sxs-lookup"><span data-stu-id="385ed-128">For example, select **Surface Pro 7**.</span></span>
7.  <span data-ttu-id="385ed-129">Dans la page **Fonctionnalités avancées,** sélectionnez **Wake on Power,** définissez la fonctionnalité sur **On,** puis sélectionnez **Next**.</span><span class="sxs-lookup"><span data-stu-id="385ed-129">On the **Advanced Features** page, select **Wake on Power**, set the feature to **On**, and then select **Next**.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-3.png" alt-text="Sélectionnez Wake on Power et définissez sur On."::: 
8.  <span data-ttu-id="385ed-131">Dans la page **Réussite,** sélectionnez **Fin**.</span><span class="sxs-lookup"><span data-stu-id="385ed-131">On the **Successful** page, select **End**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="385ed-132">Si c’est la première fois que vous fournissez des paramètres à votre appareil, vous êtes invité à fournir également les deux derniers caractères de l’empreinte numérique du certificat.</span><span class="sxs-lookup"><span data-stu-id="385ed-132">If this is the first time that you are providing settings to your device, you will be prompted to also provide the last two characters of the certificate thumbprint.</span></span> 
9.  <span data-ttu-id="385ed-133">Enregistrez le package .msi.</span><span class="sxs-lookup"><span data-stu-id="385ed-133">Save the .msi package.</span></span> 

## <span data-ttu-id="385ed-134">Appliquer le package MSI</span><span class="sxs-lookup"><span data-stu-id="385ed-134">Apply the MSI package</span></span> 

<span data-ttu-id="385ed-135">Vous pouvez appliquer le package MSI aux appareils de votre réseau à l’aide d’outils de distribution de logiciels tels que Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="385ed-135">You can apply the MSI package to devices across your network by using software distribution tools such as Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="385ed-136">Cette procédure comprend les étapes d’installation du package sur votre ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="385ed-136">This procedure includes steps to install the package on your local computer.</span></span> 

1.  <span data-ttu-id="385ed-137">À une invite de commandes avec élévation de niveau élevé, entrez le chemin d’accès complet du fichier .msi pour exécuter le package .msi.</span><span class="sxs-lookup"><span data-stu-id="385ed-137">At an elevated command prompt, enter the full path of the .msi file to run the .msi package.</span></span> 

    ```
    C:\SEMM\wake-on-power.msi 
    ```

2.  <span data-ttu-id="385ed-138">Dans la **boîte de dialogue** Avertissement, sélectionnez **OK** ou désactivez BitLocker, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="385ed-138">In the **Warning** dialog box, select **OK** or disable BitLocker, as appropriate.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-4.png" alt-text="Sélectionnez OK ou désactivez BitLocker selon le cas.":::
3.  <span data-ttu-id="385ed-140">Dans la page d’accueil, **sélectionnez Suivant** pour exécuter le package et appliquez le paramètre UEFI nouvellement configuré.</span><span class="sxs-lookup"><span data-stu-id="385ed-140">On the Welcome page, select **Next** to run the package and apply the newly configured UEFI setting.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-5.png" alt-text="Une page d’accueil, sélectionnez Suivant.":::
4.  <span data-ttu-id="385ed-142">Redémarrez votre appareil.</span><span class="sxs-lookup"><span data-stu-id="385ed-142">Restart your device.</span></span> 

<span data-ttu-id="385ed-143">L’alimentation de veille est maintenant configurée.</span><span class="sxs-lookup"><span data-stu-id="385ed-143">Wake on Power is now configured.</span></span> <span data-ttu-id="385ed-144">Pour tester les paramètres, désconnectez votre appareil, déconnectez l’alimentation, puis reconnectez-la.</span><span class="sxs-lookup"><span data-stu-id="385ed-144">To test the settings, turn off your device, disconnect the power, and then reconnect the power.</span></span> <span data-ttu-id="385ed-145">L’appareil doit démarrer automatiquement.</span><span class="sxs-lookup"><span data-stu-id="385ed-145">The device should start automatically.</span></span> 

## <span data-ttu-id="385ed-146">Références</span><span class="sxs-lookup"><span data-stu-id="385ed-146">References</span></span>

<span data-ttu-id="385ed-147">Pour plus d’informations, voir les articles suivants.</span><span class="sxs-lookup"><span data-stu-id="385ed-147">For more information, see the following articles.</span></span> 

- [<span data-ttu-id="385ed-148">Mode de gestion SurfaceEnterprise</span><span class="sxs-lookup"><span data-stu-id="385ed-148">Surface Enterprise Management Mode</span></span>](surface-enterprise-management-mode.md)
- [<span data-ttu-id="385ed-149">Wake on LAN for Surface devices</span><span class="sxs-lookup"><span data-stu-id="385ed-149">Wake on LAN for Surface devices</span></span>](wake-on-lan-for-surface-devices.md)

<span data-ttu-id="385ed-150">Encore besoin d’aide?</span><span class="sxs-lookup"><span data-stu-id="385ed-150">Still need help?</span></span> <span data-ttu-id="385ed-151">Go to [Microsoft Community](https://answers.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="385ed-151">Go to [Microsoft Community](https://answers.microsoft.com/).</span></span>