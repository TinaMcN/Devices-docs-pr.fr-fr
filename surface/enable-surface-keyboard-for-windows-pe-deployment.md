---
title: Comment activer le clavier Surface Laptop lors du déploiement de MDT
description: Lorsque vous utilisez MDT pour déployer Windows 10 sur des ordinateurs portables Surface, vous devez importer les pilotes de clavier à utiliser dans l’environnement Windows PE.
keywords: surface windows 10, automatiser, personnaliser, mdt
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.reviewer: scottmca
ms.localizationpriority: medium
ms.audience: itpro
manager: jarrettr
ms.date: 02/02/2021
appliesto:
- Surface Laptop (1st Gen)
- Surface Laptop 2
- Surface Laptop 3
ms.openlocfilehash: fb51dd3785882e74c90d8b2717e4cc499d492d6f
ms.sourcegitcommit: 5cfac94c220c8a8d4620c6a7fa75ae2fae089c7f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2021
ms.locfileid: "11312060"
---
# <span data-ttu-id="b897f-104">Comment activer le clavier Surface Laptop pendant le déploiement de MDT</span><span class="sxs-lookup"><span data-stu-id="b897f-104">How to enable the Surface Laptop keyboard during MDT deployment</span></span>

<span data-ttu-id="b897f-105">Cet article traite d’une approche de déploiement qui utilise Microsoft Deployment Shared Computer Toolkit (MDT).</span><span class="sxs-lookup"><span data-stu-id="b897f-105">This article addresses a deployment approach that uses Microsoft Deployment Toolkit (MDT).</span></span> <span data-ttu-id="b897f-106">Vous pouvez également appliquer ces informations à d’autres méthodologies de déploiement.</span><span class="sxs-lookup"><span data-stu-id="b897f-106">You can also apply this information to other deployment methodologies.</span></span> <span data-ttu-id="b897f-107">Sur la plupart des types d’appareils Surface, le clavier doit fonctionner pendant l’installation Lite Touch (LTI).</span><span class="sxs-lookup"><span data-stu-id="b897f-107">On most types of Surface devices, the keyboard should work during Lite Touch Installation (LTI).</span></span> <span data-ttu-id="b897f-108">Toutefois, surface laptop nécessite des pilotes supplémentaires pour activer le clavier.</span><span class="sxs-lookup"><span data-stu-id="b897f-108">However, Surface Laptop requires some additional drivers to enable the keyboard.</span></span> <span data-ttu-id="b897f-109">Pour les appareils Surface Laptop (1ère génération) et Surface Laptop 2, vous devez préparer la structure de dossiers et les profils de sélection qui vous permettent de spécifier des pilotes de clavier à utiliser pendant la phase d’environnement de préinstallation Windows (Windows PE) de LTI.</span><span class="sxs-lookup"><span data-stu-id="b897f-109">For Surface Laptop (1st Gen) and Surface Laptop 2 devices, you must prepare the folder structure and selection profiles that allow you to specify keyboard drivers for use during the Windows Preinstallation Environment (Windows PE) phase of LTI.</span></span> <span data-ttu-id="b897f-110">Pour plus d’informations sur cette structure de dossiers, voir Déployer une [image Windows 10](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt?redirectedfrom=MSDN#step-5-prepare-the-drivers-repository)à l’aide de MDT : Étape 5 : Préparer le référentiel de pilotes.</span><span class="sxs-lookup"><span data-stu-id="b897f-110">For more information about this folder structure, see [Deploy a Windows 10 image using MDT: Step 5: Prepare the drivers repository](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt?redirectedfrom=MSDN#step-5-prepare-the-drivers-repository).</span></span>

> [!TIP]    
> <span data-ttu-id="b897f-111">Lorsque vous utilisez des pilotes de clavier pour Surface Laptop 2 et Surface Laptop 3 dans la même instance de démarrage Windows PE, vous devrez peut-être réinitialiser manuellement le microprogramme si le clavier ou le pavé tactile ne fonctionne pas dans Windows PE :</span><span class="sxs-lookup"><span data-stu-id="b897f-111">When using keyboard drivers for Surface Laptop 2 and Surface Laptop 3 in the same Windows PE boot instance, you may need to manually reset the firmware if the keyboard or touchpad don’t work in Windows PE:</span></span>
>
> - <span data-ttu-id="b897f-112">Appuyez et maintenez le bouton d’alimentation enfoncé pendant 30 secondes.</span><span class="sxs-lookup"><span data-stu-id="b897f-112">Press and hold the Power button for 30 seconds.</span></span> <span data-ttu-id="b897f-113">Si vous êtes connecté à une unité d’alimentation, appuyez sur le bouton d’alimentation et maintenez enfoncée le bouton d’alimentation jusqu’à ce que la lumière à la fin du cordon d’alimentation soit brièvement éteinte avant de la désactiver.</span><span class="sxs-lookup"><span data-stu-id="b897f-113">If you are connected to a power supply unit (PSU), press and hold the Power button until you see the light at the end of the PSU cord briefly turn off before turning back on.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b897f-114">Si vous déployez une image Windows 10 sur un Ordinateur portable Surface sur qui Windows 10 est préinstallé en mode S, voir la KB [4032347,](https://support.microsoft.com/help/4032347/surface-preinstall-windows10-s-mode-issues)Problèmes lors du déploiement de Windows sur des appareils Surface avec Windows 10 préinstallé en mode S.</span><span class="sxs-lookup"><span data-stu-id="b897f-114">If you are deploying a Windows 10 image to a Surface Laptop that has Windows 10 in S mode preinstalled, see KB [4032347, Problems when deploying Windows to Surface devices with preinstalled Windows 10 in S mode](https://support.microsoft.com/help/4032347/surface-preinstall-windows10-s-mode-issues).</span></span>

<span data-ttu-id="b897f-115">Pour ajouter les pilotes de clavier au profil de sélection, suivez les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="b897f-115">To add the keyboard drivers to the selection profile, follow these steps:</span></span>

1. <span data-ttu-id="b897f-116">Téléchargez le dernier fichier MSI Surface Laptop à partir des emplacements appropriés :</span><span class="sxs-lookup"><span data-stu-id="b897f-116">Download the latest Surface Laptop MSI file from the appropriate locations:</span></span>
    - [<span data-ttu-id="b897f-117">Pilotes et microprogrammes Surface Laptop (1ère génération)</span><span class="sxs-lookup"><span data-stu-id="b897f-117">Surface Laptop (1st Gen) Drivers and Firmware</span></span>](https://www.microsoft.com/download/details.aspx?id=55489)
    - [<span data-ttu-id="b897f-118">Surface Laptop 2 Drivers and Firmware</span><span class="sxs-lookup"><span data-stu-id="b897f-118">Surface Laptop 2 Drivers and Firmware</span></span>](https://www.microsoft.com/download/details.aspx?id=57515)
    - [<span data-ttu-id="b897f-119">Surface Laptop 3 avec microprogramme et pilotes de processeur Intel</span><span class="sxs-lookup"><span data-stu-id="b897f-119">Surface Laptop 3 with Intel Processor Drivers and Firmware</span></span>](https://www.microsoft.com/download/details.aspx?id=100429)

2. <span data-ttu-id="b897f-120">Extrayez le contenu du fichier MSI surface laptop dans un dossier que vous pouvez facilement localiser (par exemple, c:\surface_laptop_drivers).</span><span class="sxs-lookup"><span data-stu-id="b897f-120">Extract the contents of the Surface Laptop MSI file to a folder that you can easily locate (for example, c:\surface_laptop_drivers).</span></span> <span data-ttu-id="b897f-121">Pour extraire le contenu, ouvrez une fenêtre d’invite de commandes avec élévation de niveaux et exécutez la commande à partir de l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="b897f-121">To extract the contents, open an elevated Command Prompt window and run the command from the following example:</span></span>

   ```cmd
   Msiexec.exe /a SurfaceLaptop_Win10_15063_1703008_1.msi targetdir=c:\surface_laptop_drivers /qn
   ```

3. <span data-ttu-id="b897f-122">Ouvrez Deployment Workbench et développez le nœud **Deployment Shares** et votre partage de déploiement, puis accédez au **dossier WindowsPEX64.**</span><span class="sxs-lookup"><span data-stu-id="b897f-122">Open the Deployment Workbench and expand the **Deployment Shares** node and your deployment share, then navigate to the **WindowsPEX64** folder.</span></span>

   ![Image qui montre l’emplacement du dossier WindowsPEX64 dans Deployment Workbench](./images/surface-laptop-keyboard-1.png)

4. <span data-ttu-id="b897f-124">Cliquez avec le bouton droit **sur le dossier WindowsPEX64** et sélectionnez **Importer des pilotes.**</span><span class="sxs-lookup"><span data-stu-id="b897f-124">Right-click the **WindowsPEX64** folder and select **Import Drivers**.</span></span>

5. <span data-ttu-id="b897f-125">Suivez les instructions de l’Assistant Importation de pilotes pour importer les dossiers de pilotes dans le dossier WindowsPEX64.</span><span class="sxs-lookup"><span data-stu-id="b897f-125">Follow the instructions in the Import Driver Wizard to import the driver folders into the WindowsPEX64 folder.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="b897f-126">Vérifiez le package MSI téléchargé pour déterminer le format et la structure du répertoire.</span><span class="sxs-lookup"><span data-stu-id="b897f-126">Check the downloaded MSI package to determine the format and directory structure.</span></span>  <span data-ttu-id="b897f-127">La structure du répertoire commence par SurfacePlatformInstaller (fichiers MSI plus anciens) ou SurfaceUpdate (fichiers MSI plus nouveaux) selon la date de publication du MSI.</span><span class="sxs-lookup"><span data-stu-id="b897f-127">The directory structure will start with either SurfacePlatformInstaller (older MSI files) or SurfaceUpdate (Newer MSI files) depending on when the MSI was released.</span></span> 

    <span data-ttu-id="b897f-128">Pour prendre en charge Surface Laptop (1re génération), importez les dossiers suivants :</span><span class="sxs-lookup"><span data-stu-id="b897f-128">To support Surface Laptop (1st Gen), import the following folders:</span></span>

     - <span data-ttu-id="b897f-129">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="b897f-129">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
     - <span data-ttu-id="b897f-130">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="b897f-130">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span></span>
     - <span data-ttu-id="b897f-131">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="b897f-131">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
     - <span data-ttu-id="b897f-132">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="b897f-132">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

    <span data-ttu-id="b897f-133">Ou pour les fichiers MSI plus nouveaux commençant par « SurfaceUpdate », utilisez :</span><span class="sxs-lookup"><span data-stu-id="b897f-133">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

    - <span data-ttu-id="b897f-134">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="b897f-134">SurfaceUpdate\SerialIOGPIO</span></span>
    - <span data-ttu-id="b897f-135">SurfaceUpdate\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="b897f-135">SurfaceUpdate\SurfaceHidMiniDriver</span></span>
    - <span data-ttu-id="b897f-136">SurfaceUpdate\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="b897f-136">SurfaceUpdate\SurfaceSerialHubDriver</span></span>
    - <span data-ttu-id="b897f-137">SurfaceUpdate\It sous</span><span class="sxs-lookup"><span data-stu-id="b897f-137">SurfaceUpdate\Itouch</span></span>

    <span data-ttu-id="b897f-138">Pour prendre en charge Surface Laptop 2, importez les dossiers suivants :</span><span class="sxs-lookup"><span data-stu-id="b897f-138">To support Surface Laptop 2, import the following folders:</span></span>

     - <span data-ttu-id="b897f-139">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="b897f-139">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
     - <span data-ttu-id="b897f-140">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span><span class="sxs-lookup"><span data-stu-id="b897f-140">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span></span>
     - <span data-ttu-id="b897f-141">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="b897f-141">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
     - <span data-ttu-id="b897f-142">SurfacePlatformInstaller\Drivers\System\I2C</span><span class="sxs-lookup"><span data-stu-id="b897f-142">SurfacePlatformInstaller\Drivers\System\I2C</span></span>
     - <span data-ttu-id="b897f-143">SurfacePlatformInstaller\Drivers\System\SPI</span><span class="sxs-lookup"><span data-stu-id="b897f-143">SurfacePlatformInstaller\Drivers\System\SPI</span></span>
     - <span data-ttu-id="b897f-144">SurfacePlatformInstaller\Drivers\System\UART</span><span class="sxs-lookup"><span data-stu-id="b897f-144">SurfacePlatformInstaller\Drivers\System\UART</span></span>
     - <span data-ttu-id="b897f-145">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="b897f-145">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

    <span data-ttu-id="b897f-146">Ou pour les fichiers MSI plus nouveaux commençant par « SurfaceUpdate », utilisez :</span><span class="sxs-lookup"><span data-stu-id="b897f-146">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

    - <span data-ttu-id="b897f-147">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="b897f-147">SurfaceUpdate\SerialIOGPIO</span></span>
    - <span data-ttu-id="b897f-148">SurfaceUpdate\serialioi2c</span><span class="sxs-lookup"><span data-stu-id="b897f-148">SurfaceUpdate\serialioi2c</span></span>
    - <span data-ttu-id="b897f-149">SurfaceUpdate\SerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="b897f-149">SurfaceUpdate\SerialIOSPI</span></span>
    - <span data-ttu-id="b897f-150">SurfaceUpdate\SerialIOUART</span><span class="sxs-lookup"><span data-stu-id="b897f-150">SurfaceUpdate\SerialIOUART</span></span>
    - <span data-ttu-id="b897f-151">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="b897f-151">SurfaceUpdate\SurfaceHidMini</span></span>
    - <span data-ttu-id="b897f-152">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="b897f-152">SurfaceUpdate\SurfaceSerialHub</span></span>
    - <span data-ttu-id="b897f-153">SurfaceUpdate\It sous</span><span class="sxs-lookup"><span data-stu-id="b897f-153">SurfaceUpdate\Itouch</span></span>

     
    <span data-ttu-id="b897f-154">Pour prendre en charge Surface Laptop 3 avec le processeur Intel, importez les dossiers suivants :</span><span class="sxs-lookup"><span data-stu-id="b897f-154">To support Surface Laptop 3 with Intel Processor, import the following folders:</span></span>

    - <span data-ttu-id="b897f-155">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="b897f-155">SurfaceUpdate\SerialIOGPIO</span></span>
    - <span data-ttu-id="b897f-156">SurfaceUpdate\SerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="b897f-156">SurfaceUpdate\SerialIOI2C</span></span>
    - <span data-ttu-id="b897f-157">SurfaceUpdate\SerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="b897f-157">SurfaceUpdate\SerialIOSPI</span></span>
    - <span data-ttu-id="b897f-158">SurfaceUpdate\SerialIOUART</span><span class="sxs-lookup"><span data-stu-id="b897f-158">SurfaceUpdate\SerialIOUART</span></span>
    - <span data-ttu-id="b897f-159">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="b897f-159">SurfaceUpdate\SurfaceHidMini</span></span>
    - <span data-ttu-id="b897f-160">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="b897f-160">SurfaceUpdate\SurfaceSerialHub</span></span>
    - <span data-ttu-id="b897f-161">SurfaceUpdate\SurfaceHotPlug</span><span class="sxs-lookup"><span data-stu-id="b897f-161">SurfaceUpdate\SurfaceHotPlug</span></span>
    - <span data-ttu-id="b897f-162">SurfaceUpdate\It sous</span><span class="sxs-lookup"><span data-stu-id="b897f-162">SurfaceUpdate\Itouch</span></span>

    <span data-ttu-id="b897f-163">L’importation des dossiers suivants activera les fonctionnalités clavier, trackpad et tactile complètes dans PE pour Surface Laptop 3.</span><span class="sxs-lookup"><span data-stu-id="b897f-163">Importing the following folders will enable full keyboard, trackpad, and touch functionality in PE for Surface Laptop 3.</span></span>

    - <span data-ttu-id="b897f-164">SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="b897f-164">SerialIOGPIO</span></span>
    - <span data-ttu-id="b897f-165">SerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="b897f-165">SerialIOI2C</span></span>
    - <span data-ttu-id="b897f-166">SerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="b897f-166">SerialIOSPI</span></span>
    - <span data-ttu-id="b897f-167">SerialIOUART</span><span class="sxs-lookup"><span data-stu-id="b897f-167">SerialIOUART</span></span>
    - <span data-ttu-id="b897f-168">its</span><span class="sxs-lookup"><span data-stu-id="b897f-168">itouch</span></span>
    - <span data-ttu-id="b897f-169">Chipset</span><span class="sxs-lookup"><span data-stu-id="b897f-169">Chipset</span></span>
    - <span data-ttu-id="b897f-170">ChipsetLPSS</span><span class="sxs-lookup"><span data-stu-id="b897f-170">ChipsetLPSS</span></span>
    - <span data-ttu-id="b897f-171">ChipsetNorthpeak</span><span class="sxs-lookup"><span data-stu-id="b897f-171">ChipsetNorthpeak</span></span>
    - <span data-ttu-id="b897f-172">ManagementEngine</span><span class="sxs-lookup"><span data-stu-id="b897f-172">ManagementEngine</span></span>
    - <span data-ttu-id="b897f-173">SurfaceAcpiNotify</span><span class="sxs-lookup"><span data-stu-id="b897f-173">SurfaceAcpiNotify</span></span>
    - <span data-ttu-id="b897f-174">SurfaceBattery</span><span class="sxs-lookup"><span data-stu-id="b897f-174">SurfaceBattery</span></span>
    - <span data-ttu-id="b897f-175">SurfaceDockIntegration</span><span class="sxs-lookup"><span data-stu-id="b897f-175">SurfaceDockIntegration</span></span>
    - <span data-ttu-id="b897f-176">SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="b897f-176">SurfaceHidMini</span></span>
    - <span data-ttu-id="b897f-177">SurfaceHotPlug</span><span class="sxs-lookup"><span data-stu-id="b897f-177">SurfaceHotPlug</span></span>
    - <span data-ttu-id="b897f-178">SurfaceIntegration</span><span class="sxs-lookup"><span data-stu-id="b897f-178">SurfaceIntegration</span></span>
    - <span data-ttu-id="b897f-179">SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="b897f-179">SurfaceSerialHub</span></span>
    - <span data-ttu-id="b897f-180">SurfaceService</span><span class="sxs-lookup"><span data-stu-id="b897f-180">SurfaceService</span></span>
    - <span data-ttu-id="b897f-181">SurfaceStorageFwUpdate</span><span class="sxs-lookup"><span data-stu-id="b897f-181">SurfaceStorageFwUpdate</span></span>

     > [!NOTE]
     >  <span data-ttu-id="b897f-182">Vérifiez le package MSI téléchargé pour déterminer le format et la structure du répertoire.</span><span class="sxs-lookup"><span data-stu-id="b897f-182">Check the downloaded MSI package to determine the format and directory structure.</span></span>  <span data-ttu-id="b897f-183">La structure du répertoire commence par SurfacePlatformInstaller (fichiers MSI plus anciens) ou SurfaceUpdate (fichiers MSI plus nouveaux) selon la date de publication du MSI.</span><span class="sxs-lookup"><span data-stu-id="b897f-183">The directory structure will start with either SurfacePlatformInstaller (older MSI files) or SurfaceUpdate (Newer MSI files) depending on when the MSI was released.</span></span> 

     <span data-ttu-id="b897f-184">Pour prendre en charge Surface Laptop (1re génération), importez les dossiers suivants :</span><span class="sxs-lookup"><span data-stu-id="b897f-184">To support Surface Laptop (1st Gen), import the following folders:</span></span>

    - <span data-ttu-id="b897f-185">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="b897f-185">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
    - <span data-ttu-id="b897f-186">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="b897f-186">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span></span>
    - <span data-ttu-id="b897f-187">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="b897f-187">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
    - <span data-ttu-id="b897f-188">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="b897f-188">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

    <span data-ttu-id="b897f-189">Ou pour les fichiers MSI plus nouveaux commençant par « SurfaceUpdate », utilisez :</span><span class="sxs-lookup"><span data-stu-id="b897f-189">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

    - <span data-ttu-id="b897f-190">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="b897f-190">SurfaceUpdate\SerialIOGPIO</span></span>
    - <span data-ttu-id="b897f-191">SurfaceUpdate\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="b897f-191">SurfaceUpdate\SurfaceHidMiniDriver</span></span>
    - <span data-ttu-id="b897f-192">SurfaceUpdate\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="b897f-192">SurfaceUpdate\SurfaceSerialHubDriver</span></span>
    - <span data-ttu-id="b897f-193">SurfaceUpdate\It sous</span><span class="sxs-lookup"><span data-stu-id="b897f-193">SurfaceUpdate\Itouch</span></span>

    <span data-ttu-id="b897f-194">Pour prendre en charge Surface Laptop 2, importez les dossiers suivants :</span><span class="sxs-lookup"><span data-stu-id="b897f-194">To support Surface Laptop 2, import the following folders:</span></span>

    - <span data-ttu-id="b897f-195">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="b897f-195">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
    - <span data-ttu-id="b897f-196">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span><span class="sxs-lookup"><span data-stu-id="b897f-196">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span></span>
    - <span data-ttu-id="b897f-197">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="b897f-197">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
    - <span data-ttu-id="b897f-198">SurfacePlatformInstaller\Drivers\System\I2C</span><span class="sxs-lookup"><span data-stu-id="b897f-198">SurfacePlatformInstaller\Drivers\System\I2C</span></span>
    - <span data-ttu-id="b897f-199">SurfacePlatformInstaller\Drivers\System\SPI</span><span class="sxs-lookup"><span data-stu-id="b897f-199">SurfacePlatformInstaller\Drivers\System\SPI</span></span>
    - <span data-ttu-id="b897f-200">SurfacePlatformInstaller\Drivers\System\UART</span><span class="sxs-lookup"><span data-stu-id="b897f-200">SurfacePlatformInstaller\Drivers\System\UART</span></span>
    - <span data-ttu-id="b897f-201">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="b897f-201">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

    <span data-ttu-id="b897f-202">Ou pour les fichiers MSI plus nouveaux commençant par « SurfaceUpdate », utilisez :</span><span class="sxs-lookup"><span data-stu-id="b897f-202">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

    - <span data-ttu-id="b897f-203">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="b897f-203">SurfaceUpdate\SerialIOGPIO</span></span>
    - <span data-ttu-id="b897f-204">SurfaceUpdate\SerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="b897f-204">SurfaceUpdate\SerialIOI2C</span></span>
    - <span data-ttu-id="b897f-205">SurfaceUpdate\SerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="b897f-205">SurfaceUpdate\SerialIOSPI</span></span>
    - <span data-ttu-id="b897f-206">SurfaceUpdate\SerialIOUART</span><span class="sxs-lookup"><span data-stu-id="b897f-206">SurfaceUpdate\SerialIOUART</span></span>
    - <span data-ttu-id="b897f-207">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="b897f-207">SurfaceUpdate\SurfaceHidMini</span></span>
    - <span data-ttu-id="b897f-208">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="b897f-208">SurfaceUpdate\SurfaceSerialHub</span></span>
    - <span data-ttu-id="b897f-209">SurfaceUpdate\It sous</span><span class="sxs-lookup"><span data-stu-id="b897f-209">SurfaceUpdate\Itouch</span></span>

    <span data-ttu-id="b897f-210">Pour prendre en charge Surface Laptop 3 avec le processeur Intel, importez les dossiers suivants :</span><span class="sxs-lookup"><span data-stu-id="b897f-210">To support Surface Laptop 3 with Intel Processor, import the following folders:</span></span>

    - <span data-ttu-id="b897f-211">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="b897f-211">SurfaceUpdate\SerialIOGPIO</span></span>
    - <span data-ttu-id="b897f-212">SurfaceUpdate\SerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="b897f-212">SurfaceUpdate\SerialIOI2C</span></span>
    - <span data-ttu-id="b897f-213">SurfaceUpdate\SerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="b897f-213">SurfaceUpdate\SerialIOSPI</span></span>
    - <span data-ttu-id="b897f-214">SurfaceUpdate\SerialIOUART</span><span class="sxs-lookup"><span data-stu-id="b897f-214">SurfaceUpdate\SerialIOUART</span></span>
    - <span data-ttu-id="b897f-215">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="b897f-215">SurfaceUpdate\SurfaceHidMini</span></span>
    - <span data-ttu-id="b897f-216">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="b897f-216">SurfaceUpdate\SurfaceSerialHub</span></span>
    - <span data-ttu-id="b897f-217">SurfaceUpdate\SurfaceHotPlug</span><span class="sxs-lookup"><span data-stu-id="b897f-217">SurfaceUpdate\SurfaceHotPlug</span></span>
    - <span data-ttu-id="b897f-218">SurfaceUpdate\It sous</span><span class="sxs-lookup"><span data-stu-id="b897f-218">SurfaceUpdate\Itouch</span></span>

    > [!NOTE]
    > <span data-ttu-id="b897f-219">Pour le Surface Laptop 3 avec processeur Intel, le modèle est Surface Laptop 3.</span><span class="sxs-lookup"><span data-stu-id="b897f-219">For Surface Laptop 3 with Intel processor, the model is Surface Laptop 3.</span></span> <span data-ttu-id="b897f-220">Les pilotes Surface Laptop restants se trouvent dans le dossier \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3.</span><span class="sxs-lookup"><span data-stu-id="b897f-220">The remaining Surface Laptop drivers are located in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3 folder.</span></span>

6. <span data-ttu-id="b897f-221">Vérifiez que le dossier WindowsPEX64 contient désormais les pilotes importés.</span><span class="sxs-lookup"><span data-stu-id="b897f-221">Verify that the WindowsPEX64 folder now contains the imported drivers.</span></span> <span data-ttu-id="b897f-222">Le dossier doit ressembler à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="b897f-222">The folder should resemble the following:</span></span>  

   ![Image that shows the newly imported drivers in the WindowsPEX64 folder of the Deployment Workbench](./images/surface-laptop-keyboard-2.png)

7. <span data-ttu-id="b897f-224">Configurez un profil de sélection qui utilise le dossier WindowsPEX64.</span><span class="sxs-lookup"><span data-stu-id="b897f-224">Configure a selection profile that uses the WindowsPEX64 folder.</span></span> <span data-ttu-id="b897f-225">Le profil de sélection doit ressembler à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="b897f-225">The selection profile should resemble the following:</span></span>  

   ![Image shows the WindowsPEX64 folder selected as part of a selection profile](./images/surface-laptop-keyboard-3.png)

8. <span data-ttu-id="b897f-227">Configurez les propriétés Windows PE du partage de déploiement MDT pour utiliser le nouveau profil de sélection, comme suit :</span><span class="sxs-lookup"><span data-stu-id="b897f-227">Configure the Windows PE properties of the MDT deployment share to use the new selection profile, as follows:</span></span>  

   - <span data-ttu-id="b897f-228">Pour **la plateforme,** **sélectionnez x64**.</span><span class="sxs-lookup"><span data-stu-id="b897f-228">For **Platform**, select **x64**.</span></span>
   - <span data-ttu-id="b897f-229">Pour **le profil de**sélection, sélectionnez le nouveau profil.</span><span class="sxs-lookup"><span data-stu-id="b897f-229">For **Selection profile**, select the new profile.</span></span>
   - <span data-ttu-id="b897f-230">Sélectionnez **Inclure tous les pilotes du profil de sélection.**</span><span class="sxs-lookup"><span data-stu-id="b897f-230">Select **Include all drivers from the selection profile**.</span></span>
   
   ![Image qui illustre les propriétés Windows PE du partage de déploiement MDT](./images/surface-laptop-keyboard-4.png)

9. <span data-ttu-id="b897f-232">Vérifiez que vous avez configuré les pilotes Surface Laptop restants à l’aide d’un profil de sélection ou d’une variable **DriverGroup001.**</span><span class="sxs-lookup"><span data-stu-id="b897f-232">Verify that you have configured the remaining Surface Laptop drivers by using either a selection profile or a **DriverGroup001** variable.</span></span>  
   - <span data-ttu-id="b897f-233">Pour surface laptop (1ère génération), le modèle est **Surface Laptop**.</span><span class="sxs-lookup"><span data-stu-id="b897f-233">For Surface Laptop (1st Gen), the model is **Surface Laptop**.</span></span> <span data-ttu-id="b897f-234">Les pilotes Surface Laptop restants doivent résider dans le dossier \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop, comme illustré dans la figure qui suit cette liste.</span><span class="sxs-lookup"><span data-stu-id="b897f-234">The remaining Surface Laptop drivers should reside in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop folder as shown in the figure that follows this list.</span></span>
   - <span data-ttu-id="b897f-235">Pour Surface Laptop 2, le modèle est **Surface Laptop 2**.</span><span class="sxs-lookup"><span data-stu-id="b897f-235">For Surface Laptop 2, the model is **Surface Laptop 2**.</span></span> <span data-ttu-id="b897f-236">Les pilotes Surface Laptop restants doivent résider dans le dossier \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 2.</span><span class="sxs-lookup"><span data-stu-id="b897f-236">The remaining Surface Laptop drivers should reside in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 2 folder.</span></span> 
   - <span data-ttu-id="b897f-237">Pour le Surface Laptop 3 avec processeur Intel, le modèle est Surface Laptop 3.</span><span class="sxs-lookup"><span data-stu-id="b897f-237">For Surface Laptop 3 with Intel processor, the model is Surface Laptop 3.</span></span> <span data-ttu-id="b897f-238">Les pilotes Surface Laptop restants se trouvent dans le dossier \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3.</span><span class="sxs-lookup"><span data-stu-id="b897f-238">The remaining Surface Laptop drivers are located in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3 folder.</span></span>

   ![Image that shows the regular Surface Laptop (1st Gen) drivers in the Surface Laptop folder of the Deployment Workbench](./images/surface-laptop-keyboard-5.png)

<span data-ttu-id="b897f-240">Après avoir configuré le partage de déploiement MDT pour utiliser le nouveau profil de sélection et les paramètres associés, poursuivez le processus de déploiement comme décrit dans Déployer une [image Windows 10](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt#step-6-create-the-deployment-task-sequence)à l’aide de MDT : Étape 6 : Créer la séquence de tâches de déploiement.</span><span class="sxs-lookup"><span data-stu-id="b897f-240">After configuring the MDT Deployment Share to use the new selection profile and related settings, continue the deployment process as described in [Deploy a Windows 10 image using MDT: Step 6: Create the deployment task sequence](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt#step-6-create-the-deployment-task-sequence).</span></span>
