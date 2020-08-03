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
ms.custom:
- CI 121602
ms.reviewer: johnk@cadencepreferred.com
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
ms.openlocfilehash: 271831651280299a40c4e7a7480fa86e29bd1cf5
ms.sourcegitcommit: f875a45961ff5f3c04006afc8690b5e5965e4d80
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/31/2020
ms.locfileid: "10903004"
---
# <span data-ttu-id="f8762-104">Mise en éveil des appareils surface</span><span class="sxs-lookup"><span data-stu-id="f8762-104">Wake on Power for Surface devices</span></span>

<span data-ttu-id="f8762-105">Les appareils surface peuvent être éteints lorsque vous êtes absent du bureau ou configurés pour économiser la batterie.</span><span class="sxs-lookup"><span data-stu-id="f8762-105">Surface devices can be powered off while away from the desk or set to hibernate mode to save battery.</span></span> <span data-ttu-id="f8762-106">Pour améliorer la gestion de ces appareils, l’éveil à la consommation permet aux périphériques de surface compatibles de démarrer automatiquement lors de leur reconnexion à l’alimentation.</span><span class="sxs-lookup"><span data-stu-id="f8762-106">To improve the manageability of these devices, Wake on Power enables compatible Surface devices to automatically start when reconnected to power.</span></span> <span data-ttu-id="f8762-107">La configuration de la mise en éveil nécessite l’utilisation du mode de gestion de surface entreprise (SEMM) par le biais du Configurateur de surface UEFI ou du gestionnaire UEFI.</span><span class="sxs-lookup"><span data-stu-id="f8762-107">Configuring Wake on Power requires using Surface Enterprise Management Mode (SEMM) either through Surface UEFI Configurator or the UEFI Manager.</span></span>

<span data-ttu-id="f8762-108">La mise en éveil est une fonctionnalité disponible sur les appareils suivants:</span><span class="sxs-lookup"><span data-stu-id="f8762-108">Wake on Power is a feature available on the following devices:</span></span>

- <span data-ttu-id="f8762-109">SurfaceBook3</span><span class="sxs-lookup"><span data-stu-id="f8762-109">Surface Book 3</span></span>
- <span data-ttu-id="f8762-110">SurfacePro7</span><span class="sxs-lookup"><span data-stu-id="f8762-110">Surface Pro 7</span></span>
- <span data-ttu-id="f8762-111">Surface Laptop3</span><span class="sxs-lookup"><span data-stu-id="f8762-111">Surface Laptop 3</span></span>
- <span data-ttu-id="f8762-112">SurfaceProX</span><span class="sxs-lookup"><span data-stu-id="f8762-112">Surface Pro X</span></span> 

## <span data-ttu-id="f8762-113">Présentation et configuration requise</span><span class="sxs-lookup"><span data-stu-id="f8762-113">Overview and prerequisites</span></span>

<span data-ttu-id="f8762-114">Vous pouvez utiliser le configurateur surface UEFI pour configurer les paramètres UEFI individuels enregistrés dans un package Windows Installer. msi pour une distribution vers des appareils cibles.</span><span class="sxs-lookup"><span data-stu-id="f8762-114">You can use the Surface UEFI Configurator to configure individual UEFI settings that are saved in a Windows Installer .msi package for distribution to target devices.</span></span> 

> [!NOTE]
> <span data-ttu-id="f8762-115">Cet article part du principe que vous êtes familiarisé avec l’utilisation de SEMM.</span><span class="sxs-lookup"><span data-stu-id="f8762-115">This article assumes that you are familiar with using SEMM.</span></span> <span data-ttu-id="f8762-116">Pour plus d’informations, reportez-vous à la documentation du [mode de gestion des entreprises de surface (SEMM)](surface-enterprise-management-mode.md) .</span><span class="sxs-lookup"><span data-stu-id="f8762-116">For more information, see [Surface Enterprise Management Mode (SEMM)](surface-enterprise-management-mode.md) documentation.</span></span>

## <span data-ttu-id="f8762-117">Pour activer la mise en éveil</span><span class="sxs-lookup"><span data-stu-id="f8762-117">To enable Wake on Power</span></span>

1.  <span data-ttu-id="f8762-118">Téléchargez la version la plus récente de [surface Configurator Configurator](https://www.microsoft.com/download/confirmation.aspx?id=46703).</span><span class="sxs-lookup"><span data-stu-id="f8762-118">Download the latest version of [Surface UEFI Configurator](https://www.microsoft.com/download/confirmation.aspx?id=46703).</span></span>
2.  <span data-ttu-id="f8762-119">Connectez-vous à votre périphérique surface en tant qu’administrateur, ouvrez le **Configurateur de surface UEFI**, sélectionnez **appareils surface**, puis sélectionnez **suivant**.</span><span class="sxs-lookup"><span data-stu-id="f8762-119">Sign into your Surface device as an Administrator, open **Surface UEFI Configurator**, select **Surface Devices**, and then select **Next**.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-1.png" alt-text="Sélectionnez périphériques surface, puis sélectionnez suivant.":::
3.  <span data-ttu-id="f8762-121">Sélectionnez **Démarrer** , puis sous **package de configuration** , sélectionnez **créer**.</span><span class="sxs-lookup"><span data-stu-id="f8762-121">Select **Start** and then under **Configuration Package** select **Create**.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-2.png" alt-text="Sélectionnez créer un package de configuration.":::
4.  <span data-ttu-id="f8762-123">Sélectionnez **protection des certificats** et ajoutez votre fichier Certificate. pfx.</span><span class="sxs-lookup"><span data-stu-id="f8762-123">Select **Certificate Protection** and add your certificate .pfx file.</span></span> <span data-ttu-id="f8762-124">Après avoir entré votre mot de passe, sélectionnez **suivant**.</span><span class="sxs-lookup"><span data-stu-id="f8762-124">After entering your password, select **Next**.</span></span> <span data-ttu-id="f8762-125">Ajoutez une **protection par mot de passe**, le cas échéant, puis sélectionnez **suivant**.</span><span class="sxs-lookup"><span data-stu-id="f8762-125">Add **Password Protection**, as appropriate, and then select **Next**.</span></span>
5.  <span data-ttu-id="f8762-126">Dans la page **sélectionnez le type de surface que vous souhaitez cibler** , sélectionnez les appareils cibles appropriés.</span><span class="sxs-lookup"><span data-stu-id="f8762-126">On the **Choose which Surface type you want to target** page, select your target devices as appropriate.</span></span> <span data-ttu-id="f8762-127">Par exemple, **surface Pro 7**.</span><span class="sxs-lookup"><span data-stu-id="f8762-127">For example, **Surface Pro 7**.</span></span>
6.  <span data-ttu-id="f8762-128">**Sur la**page **fonctionnalités avancées** , sélectionnez **éveil et activation** .</span><span class="sxs-lookup"><span data-stu-id="f8762-128">On the **Advanced Features** page, select **Wake on Power** and set to **On**.</span></span> <span data-ttu-id="f8762-129">Sélectionnez **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="f8762-129">Select **Next**.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-3.png" alt-text="Sélectionnez éveil et activation."::: 
7.  <span data-ttu-id="f8762-131">Dans la page **réussite** , sélectionnez **fin**.</span><span class="sxs-lookup"><span data-stu-id="f8762-131">On the **Successful** page, select **End**.</span></span> <span data-ttu-id="f8762-132">S’il s’agit de votre première utilisation de paramètres pour votre appareil, vous serez invité à fournir les deux derniers caractères de l’empreinte du certificat.</span><span class="sxs-lookup"><span data-stu-id="f8762-132">If this is your first time providing settings to your device, you will be prompted to provide the last two characters of the certificate thumbprint.</span></span> 
8.  <span data-ttu-id="f8762-133">Enregistrez le package. msi.</span><span class="sxs-lookup"><span data-stu-id="f8762-133">Save the .msi package.</span></span> 

## <span data-ttu-id="f8762-134">Appliquer le package MSI</span><span class="sxs-lookup"><span data-stu-id="f8762-134">Apply the MSI package</span></span> 

<span data-ttu-id="f8762-135">Vous pouvez appliquer le package MSI aux appareils de votre réseau à l’aide d’outils de distribution de logiciels tels que Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="f8762-135">You can apply the MSI package to devices across your network using software distribution tools such as Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="f8762-136">Cette procédure décrit comment installer le package sur votre ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="f8762-136">This procedure includes steps for installing the package on your local machine.</span></span> 

1.  <span data-ttu-id="f8762-137">Ouvrez une invite de commandes avec élévation de privilèges et entrez le chemin d’accès complet du fichier. msi pour exécuter le package. msi.</span><span class="sxs-lookup"><span data-stu-id="f8762-137">Open an elevated command prompt and enter the full path of the .msi file to run the .msi package.</span></span> 

    ```
    C:\SEMM\wake-on-power.msi 
    ```

2.  <span data-ttu-id="f8762-138">Dans la boîte de dialogue d' **Avertissement** , sélectionnez **OK** ou désactivez BitLocker selon le cas.</span><span class="sxs-lookup"><span data-stu-id="f8762-138">On the **Warning** dialog box, select **OK** or disable Bitlocker as appropriate.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-4.png" alt-text="Sélectionnez OK ou désactivez BitLocker selon le cas.":::
3.  <span data-ttu-id="f8762-140">Dans la page d’accueil, sélectionnez **Next (suivant** ) pour exécuter le package et appliquer le paramètre UEFI nouvellement configuré.</span><span class="sxs-lookup"><span data-stu-id="f8762-140">On the Welcome page, select **Next** to run the package and apply the newly configured UEFI setting.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-5.png" alt-text="Dans la page Bienvenue, sélectionnez suivant.":::
4.  <span data-ttu-id="f8762-142">Redémarrez votre appareil.</span><span class="sxs-lookup"><span data-stu-id="f8762-142">Restart your device.</span></span> 

<span data-ttu-id="f8762-143">La mise en éveil est désormais configurée.</span><span class="sxs-lookup"><span data-stu-id="f8762-143">Wake on Power is now configured.</span></span> <span data-ttu-id="f8762-144">Pour tester le paramètre, éteignez votre appareil, débranchez le cordon d’alimentation, puis rebranchez le cordon d’alimentation.</span><span class="sxs-lookup"><span data-stu-id="f8762-144">To test the setting, turn off your device, disconnect the power, and then reconnect the power.</span></span> <span data-ttu-id="f8762-145">L’appareil démarre automatiquement.</span><span class="sxs-lookup"><span data-stu-id="f8762-145">The device will start automatically.</span></span> 

## <span data-ttu-id="f8762-146">Informations supplémentaires</span><span class="sxs-lookup"><span data-stu-id="f8762-146">More information</span></span>

<span data-ttu-id="f8762-147">Pour plus d’informations, consultez les articles suivants.</span><span class="sxs-lookup"><span data-stu-id="f8762-147">For more information, see the following articles.</span></span> 

- [<span data-ttu-id="f8762-148">Mode de gestion SurfaceEnterprise</span><span class="sxs-lookup"><span data-stu-id="f8762-148">Surface Enterprise Management Mode</span></span>](surface-enterprise-management-mode.md)
- [<span data-ttu-id="f8762-149">Wake on LAN pour les appareils surface</span><span class="sxs-lookup"><span data-stu-id="f8762-149">Wake on LAN for Surface devices</span></span>](wake-on-lan-for-surface-devices.md)

<span data-ttu-id="f8762-150">Encore besoin d’aide?</span><span class="sxs-lookup"><span data-stu-id="f8762-150">Still need help?</span></span> <span data-ttu-id="f8762-151">Accédez à la [communauté Microsoft](https://answers.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="f8762-151">Go to [Microsoft Community](https://answers.microsoft.com/).</span></span>