---
title: Comment activer le clavier surface Laptop pour le clavier portable surface lors du déploiement de MDT
description: Lorsque vous utilisez MDT pour déployer Windows 10 sur des ordinateurs portables en surface, vous devez importer les pilotes de clavier à utiliser dans l’environnement Windows PE.
keywords: surface Windows 10, automatiser, personnaliser, MDT
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
appliesto:
- Surface Laptop (1st Gen)
- Surface Laptop 2
- Surface Laptop 3
ms.openlocfilehash: d7ae6fc434f77cad86e73f111243968493de4ff2
ms.sourcegitcommit: e6224f81f8efb6ac862afec0e60e3ddb182e9e6f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/22/2020
ms.locfileid: "11247306"
---
# <span data-ttu-id="c4a2f-104">Comment activer le clavier surface Laptop pour le clavier portable surface lors du déploiement de MDT</span><span class="sxs-lookup"><span data-stu-id="c4a2f-104">How to enable the Surface Laptop keyboard during MDT deployment</span></span>

<span data-ttu-id="c4a2f-105">Cet article traite d’une approche de déploiement qui utilise le kit de développement Microsoft Deployment (MDT).</span><span class="sxs-lookup"><span data-stu-id="c4a2f-105">This article addresses a deployment approach that uses Microsoft Deployment Toolkit (MDT).</span></span> <span data-ttu-id="c4a2f-106">Vous pouvez également appliquer ces informations à d’autres méthodes de déploiement.</span><span class="sxs-lookup"><span data-stu-id="c4a2f-106">You can also apply this information to other deployment methodologies.</span></span> <span data-ttu-id="c4a2f-107">Sur la plupart des types de périphériques surface, le clavier doit fonctionner au cours de l’installation LTI (LTI).</span><span class="sxs-lookup"><span data-stu-id="c4a2f-107">On most types of Surface devices, the keyboard should work during Lite Touch Installation (LTI).</span></span> <span data-ttu-id="c4a2f-108">En revanche, le portable surface nécessite des pilotes supplémentaires pour activer le clavier.</span><span class="sxs-lookup"><span data-stu-id="c4a2f-108">However, Surface Laptop requires some additional drivers to enable the keyboard.</span></span> <span data-ttu-id="c4a2f-109">Pour les appareils mobiles surface (1ère génération) et surface Laptop 2, vous devez préparer les profils de structure et de sélection des dossiers pour vous permettre de spécifier les pilotes de clavier à utiliser lors de la phase de l’environnement de préinstallation Windows (Windows PE) de LTI.</span><span class="sxs-lookup"><span data-stu-id="c4a2f-109">For Surface Laptop (1st Gen) and Surface Laptop 2 devices, you must prepare the folder structure and selection profiles that allow you to specify keyboard drivers for use during the Windows Preinstallation Environment (Windows PE) phase of LTI.</span></span> <span data-ttu-id="c4a2f-110">Pour plus d’informations sur cette structure de dossiers, consultez [la rubrique déploiement d’une image Windows 10 à l’aide de MDT: étape 5: préparer le référentiel de pilotes](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt?redirectedfrom=MSDN#step-5-prepare-the-drivers-repository).</span><span class="sxs-lookup"><span data-stu-id="c4a2f-110">For more information about this folder structure, see [Deploy a Windows 10 image using MDT: Step 5: Prepare the drivers repository](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt?redirectedfrom=MSDN#step-5-prepare-the-drivers-repository).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="c4a2f-111">Si vous déployez une image Windows 10 sur un ordinateur portable sur lequel le mode Windows 10 en S est préinstallé, voir KB [4032347, problèmes lors du déploiement de Windows sur les appareils surface avec Windows 10 en mode s préinstallé](https://support.microsoft.com/help/4032347/surface-preinstall-windows10-s-mode-issues).</span><span class="sxs-lookup"><span data-stu-id="c4a2f-111">If you are deploying a Windows 10 image to a Surface Laptop that has Windows 10 in S mode preinstalled, see KB [4032347, Problems when deploying Windows to Surface devices with preinstalled Windows 10 in S mode](https://support.microsoft.com/help/4032347/surface-preinstall-windows10-s-mode-issues).</span></span>

<span data-ttu-id="c4a2f-112">Pour ajouter les pilotes du clavier au profil de sélection, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="c4a2f-112">To add the keyboard drivers to the selection profile, follow these steps:</span></span>

1. <span data-ttu-id="c4a2f-113">Téléchargez le dernier fichier MSI surface Laptop à partir des emplacements appropriés:</span><span class="sxs-lookup"><span data-stu-id="c4a2f-113">Download the latest Surface Laptop MSI file from the appropriate locations:</span></span>
    - [<span data-ttu-id="c4a2f-114">Pilotes de surface Laptop (1ère génération) et microprogramme</span><span class="sxs-lookup"><span data-stu-id="c4a2f-114">Surface Laptop (1st Gen) Drivers and Firmware</span></span>](https://www.microsoft.com/download/details.aspx?id=55489)
    - [<span data-ttu-id="c4a2f-115">Micropilote surface Laptop 2 et microprogramme</span><span class="sxs-lookup"><span data-stu-id="c4a2f-115">Surface Laptop 2 Drivers and Firmware</span></span>](https://www.microsoft.com/download/details.aspx?id=57515)
    - [<span data-ttu-id="c4a2f-116">Surface Laptop 3 avec pilotes de processeur Intel et microprogramme</span><span class="sxs-lookup"><span data-stu-id="c4a2f-116">Surface Laptop 3 with Intel Processor Drivers and Firmware</span></span>](https://www.microsoft.com/download/details.aspx?id=100429)

2. <span data-ttu-id="c4a2f-117">Extrayez le contenu du fichier MSI surface Laptop dans un dossier que vous pouvez facilement retrouver (par exemple, c:\ surface_laptop_drivers).</span><span class="sxs-lookup"><span data-stu-id="c4a2f-117">Extract the contents of the Surface Laptop MSI file to a folder that you can easily locate (for example, c:\surface_laptop_drivers).</span></span> <span data-ttu-id="c4a2f-118">Pour extraire le contenu, ouvrez une fenêtre d’invite de commandes avec élévation de privilèges et exécutez la commande à partir de l’exemple suivant:</span><span class="sxs-lookup"><span data-stu-id="c4a2f-118">To extract the contents, open an elevated Command Prompt window and run the command from the following example:</span></span>

   ```cmd
   Msiexec.exe /a SurfaceLaptop_Win10_15063_1703008_1.msi targetdir=c:\surface_laptop_drivers /qn
   ```

3. <span data-ttu-id="c4a2f-119">Ouvrez le Deployment Workbench et développez le nœud **partages de déploiement** et votre partage de déploiement, puis accédez au dossier **WindowsPEX64** .</span><span class="sxs-lookup"><span data-stu-id="c4a2f-119">Open the Deployment Workbench and expand the **Deployment Shares** node and your deployment share, then navigate to the **WindowsPEX64** folder.</span></span>

   ![Image illustrant l’emplacement du dossier WindowsPEX64 dans Deployment Workbench](./images/surface-laptop-keyboard-1.png)

4. <span data-ttu-id="c4a2f-121">Cliquez avec le bouton droit sur le dossier **WindowsPEX64** et sélectionnez **Importer les pilotes**.</span><span class="sxs-lookup"><span data-stu-id="c4a2f-121">Right-click the **WindowsPEX64** folder and select **Import Drivers**.</span></span>
5. <span data-ttu-id="c4a2f-122">Pour importer les dossiers de pilotes dans le dossier WindowsPEX64, suivez les instructions de l’Assistant importation de pilote.</span><span class="sxs-lookup"><span data-stu-id="c4a2f-122">Follow the instructions in the Import Driver Wizard to import the driver folders into the WindowsPEX64 folder.</span></span>  

> [!NOTE]
>  <span data-ttu-id="c4a2f-123">Vérifiez le package MSI téléchargé pour déterminer le format et la structure du répertoire.</span><span class="sxs-lookup"><span data-stu-id="c4a2f-123">Check the downloaded MSI package to determine the format and directory structure.</span></span>  <span data-ttu-id="c4a2f-124">La structure de l’annuaire va commencer par SurfacePlatformInstaller (fichiers MSI plus anciens) ou SurfaceUpdate (nouveaux fichiers MSI) selon le moment de la sortie du MSI.</span><span class="sxs-lookup"><span data-stu-id="c4a2f-124">The directory structure will start with either SurfacePlatformInstaller (older MSI files) or SurfaceUpdate (Newer MSI files) depending on when the MSI was released.</span></span> 

<span data-ttu-id="c4a2f-125">Pour prendre en charge l’ordinateur portable surface (1ère génération), importez les dossiers suivants:</span><span class="sxs-lookup"><span data-stu-id="c4a2f-125">To support Surface Laptop (1st Gen), import the following folders:</span></span>

 - <span data-ttu-id="c4a2f-126">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="c4a2f-126">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
 - <span data-ttu-id="c4a2f-127">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="c4a2f-127">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span></span>
 - <span data-ttu-id="c4a2f-128">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="c4a2f-128">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
 - <span data-ttu-id="c4a2f-129">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="c4a2f-129">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

<span data-ttu-id="c4a2f-130">Ou, pour les nouveaux fichiers MSI commençant par «SurfaceUpdate», utilisez:</span><span class="sxs-lookup"><span data-stu-id="c4a2f-130">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

- <span data-ttu-id="c4a2f-131">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="c4a2f-131">SurfaceUpdate\SerialIOGPIO</span></span>
- <span data-ttu-id="c4a2f-132">SurfaceUpdate\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="c4a2f-132">SurfaceUpdate\SurfaceHidMiniDriver</span></span>
- <span data-ttu-id="c4a2f-133">SurfaceUpdate\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="c4a2f-133">SurfaceUpdate\SurfaceSerialHubDriver</span></span>
- <span data-ttu-id="c4a2f-134">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="c4a2f-134">SurfaceUpdate\Itouch</span></span>

<span data-ttu-id="c4a2f-135">Pour prendre en charge surface Laptop 2, importez les dossiers suivants:</span><span class="sxs-lookup"><span data-stu-id="c4a2f-135">To support Surface Laptop 2, import the following folders:</span></span>

 - <span data-ttu-id="c4a2f-136">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="c4a2f-136">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
 - <span data-ttu-id="c4a2f-137">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span><span class="sxs-lookup"><span data-stu-id="c4a2f-137">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span></span>
 - <span data-ttu-id="c4a2f-138">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="c4a2f-138">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
 - <span data-ttu-id="c4a2f-139">SurfacePlatformInstaller\Drivers\System\I2C</span><span class="sxs-lookup"><span data-stu-id="c4a2f-139">SurfacePlatformInstaller\Drivers\System\I2C</span></span>
 - <span data-ttu-id="c4a2f-140">SurfacePlatformInstaller\Drivers\System\SPI</span><span class="sxs-lookup"><span data-stu-id="c4a2f-140">SurfacePlatformInstaller\Drivers\System\SPI</span></span>
 - <span data-ttu-id="c4a2f-141">SurfacePlatformInstaller\Drivers\System\UART</span><span class="sxs-lookup"><span data-stu-id="c4a2f-141">SurfacePlatformInstaller\Drivers\System\UART</span></span>
 - <span data-ttu-id="c4a2f-142">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="c4a2f-142">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

<span data-ttu-id="c4a2f-143">Ou, pour les nouveaux fichiers MSI commençant par «SurfaceUpdate», utilisez:</span><span class="sxs-lookup"><span data-stu-id="c4a2f-143">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

- <span data-ttu-id="c4a2f-144">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="c4a2f-144">SurfaceUpdate\SerialIOGPIO</span></span>
- <span data-ttu-id="c4a2f-145">SurfaceUpdate\IclSerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="c4a2f-145">SurfaceUpdate\IclSerialIOI2C</span></span>
- <span data-ttu-id="c4a2f-146">SurfaceUpdate\IclSerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="c4a2f-146">SurfaceUpdate\IclSerialIOSPI</span></span>
- <span data-ttu-id="c4a2f-147">SurfaceUpdate\IclSerialIOUART</span><span class="sxs-lookup"><span data-stu-id="c4a2f-147">SurfaceUpdate\IclSerialIOUART</span></span>
- <span data-ttu-id="c4a2f-148">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="c4a2f-148">SurfaceUpdate\SurfaceHidMini</span></span>
- <span data-ttu-id="c4a2f-149">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="c4a2f-149">SurfaceUpdate\SurfaceSerialHub</span></span>
- <span data-ttu-id="c4a2f-150">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="c4a2f-150">SurfaceUpdate\Itouch</span></span>

 
<span data-ttu-id="c4a2f-151">Pour prendre en charge l’ordinateur portable surface 3 avec le processeur Intel, importez les dossiers suivants:</span><span class="sxs-lookup"><span data-stu-id="c4a2f-151">To support Surface Laptop 3 with Intel Processor, import the following folders:</span></span>

- <span data-ttu-id="c4a2f-152">SurfaceUpdate\IclSerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="c4a2f-152">SurfaceUpdate\IclSerialIOGPIO</span></span>
- <span data-ttu-id="c4a2f-153">SurfaceUpdate\IclSerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="c4a2f-153">SurfaceUpdate\IclSerialIOI2C</span></span>
- <span data-ttu-id="c4a2f-154">SurfaceUpdate\IclSerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="c4a2f-154">SurfaceUpdate\IclSerialIOSPI</span></span>
- <span data-ttu-id="c4a2f-155">SurfaceUpdate\IclSerialIOUART</span><span class="sxs-lookup"><span data-stu-id="c4a2f-155">SurfaceUpdate\IclSerialIOUART</span></span>
- <span data-ttu-id="c4a2f-156">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="c4a2f-156">SurfaceUpdate\SurfaceHidMini</span></span>
- <span data-ttu-id="c4a2f-157">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="c4a2f-157">SurfaceUpdate\SurfaceSerialHub</span></span>
- <span data-ttu-id="c4a2f-158">SurfaceUpdate\SurfaceHotPlug</span><span class="sxs-lookup"><span data-stu-id="c4a2f-158">SurfaceUpdate\SurfaceHotPlug</span></span>
- <span data-ttu-id="c4a2f-159">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="c4a2f-159">SurfaceUpdate\Itouch</span></span>

<span data-ttu-id="c4a2f-160">L’importation des dossiers suivants permettra de bénéficier de la fonctionnalité complète du clavier, de pavé tactile et de l’interaction avec le complément PE pour surface Laptop 3.</span><span class="sxs-lookup"><span data-stu-id="c4a2f-160">Importing the following folders will enable full keyboard, trackpad, and touch functionality in PE for Surface Laptop 3.</span></span>

- <span data-ttu-id="c4a2f-161">IclSerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="c4a2f-161">IclSerialIOGPIO</span></span>
- <span data-ttu-id="c4a2f-162">IclSerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="c4a2f-162">IclSerialIOI2C</span></span>
- <span data-ttu-id="c4a2f-163">IclSerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="c4a2f-163">IclSerialIOSPI</span></span>
- <span data-ttu-id="c4a2f-164">IclSerialIOUART</span><span class="sxs-lookup"><span data-stu-id="c4a2f-164">IclSerialIOUART</span></span>
- <span data-ttu-id="c4a2f-165">iTouch</span><span class="sxs-lookup"><span data-stu-id="c4a2f-165">itouch</span></span>
- <span data-ttu-id="c4a2f-166">IclChipset</span><span class="sxs-lookup"><span data-stu-id="c4a2f-166">IclChipset</span></span>
- <span data-ttu-id="c4a2f-167">IclChipsetLPSS</span><span class="sxs-lookup"><span data-stu-id="c4a2f-167">IclChipsetLPSS</span></span>
- <span data-ttu-id="c4a2f-168">IclChipsetNorthpeak</span><span class="sxs-lookup"><span data-stu-id="c4a2f-168">IclChipsetNorthpeak</span></span>
- <span data-ttu-id="c4a2f-169">ManagementEngine</span><span class="sxs-lookup"><span data-stu-id="c4a2f-169">ManagementEngine</span></span>
- <span data-ttu-id="c4a2f-170">SurfaceAcpiNotify</span><span class="sxs-lookup"><span data-stu-id="c4a2f-170">SurfaceAcpiNotify</span></span>
- <span data-ttu-id="c4a2f-171">SurfaceBattery</span><span class="sxs-lookup"><span data-stu-id="c4a2f-171">SurfaceBattery</span></span>
- <span data-ttu-id="c4a2f-172">SurfaceDockIntegration</span><span class="sxs-lookup"><span data-stu-id="c4a2f-172">SurfaceDockIntegration</span></span>
- <span data-ttu-id="c4a2f-173">SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="c4a2f-173">SurfaceHidMini</span></span>
- <span data-ttu-id="c4a2f-174">SurfaceHotPlug</span><span class="sxs-lookup"><span data-stu-id="c4a2f-174">SurfaceHotPlug</span></span>
- <span data-ttu-id="c4a2f-175">SurfaceIntegration</span><span class="sxs-lookup"><span data-stu-id="c4a2f-175">SurfaceIntegration</span></span>
- <span data-ttu-id="c4a2f-176">SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="c4a2f-176">SurfaceSerialHub</span></span>
- <span data-ttu-id="c4a2f-177">SurfaceService</span><span class="sxs-lookup"><span data-stu-id="c4a2f-177">SurfaceService</span></span>
- <span data-ttu-id="c4a2f-178">SurfaceStorageFwUpdate</span><span class="sxs-lookup"><span data-stu-id="c4a2f-178">SurfaceStorageFwUpdate</span></span>


    > [!NOTE]
    >  <span data-ttu-id="c4a2f-179">Vérifiez le package MSI téléchargé pour déterminer le format et la structure du répertoire.</span><span class="sxs-lookup"><span data-stu-id="c4a2f-179">Check the downloaded MSI package to determine the format and directory structure.</span></span>  <span data-ttu-id="c4a2f-180">La structure de l’annuaire va commencer par SurfacePlatformInstaller (fichiers MSI plus anciens) ou SurfaceUpdate (nouveaux fichiers MSI) selon le moment de la sortie du MSI.</span><span class="sxs-lookup"><span data-stu-id="c4a2f-180">The directory structure will start with either SurfacePlatformInstaller (older MSI files) or SurfaceUpdate (Newer MSI files) depending on when the MSI was released.</span></span> 

    <span data-ttu-id="c4a2f-181">Pour prendre en charge l’ordinateur portable surface (1ère génération), importez les dossiers suivants:</span><span class="sxs-lookup"><span data-stu-id="c4a2f-181">To support Surface Laptop (1st Gen), import the following folders:</span></span>

     - <span data-ttu-id="c4a2f-182">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="c4a2f-182">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
     - <span data-ttu-id="c4a2f-183">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="c4a2f-183">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span></span>
     - <span data-ttu-id="c4a2f-184">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="c4a2f-184">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
     - <span data-ttu-id="c4a2f-185">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="c4a2f-185">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

    <span data-ttu-id="c4a2f-186">Ou, pour les nouveaux fichiers MSI commençant par «SurfaceUpdate», utilisez:</span><span class="sxs-lookup"><span data-stu-id="c4a2f-186">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

    - <span data-ttu-id="c4a2f-187">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="c4a2f-187">SurfaceUpdate\SerialIOGPIO</span></span>
    - <span data-ttu-id="c4a2f-188">SurfaceUpdate\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="c4a2f-188">SurfaceUpdate\SurfaceHidMiniDriver</span></span>
    - <span data-ttu-id="c4a2f-189">SurfaceUpdate\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="c4a2f-189">SurfaceUpdate\SurfaceSerialHubDriver</span></span>
    - <span data-ttu-id="c4a2f-190">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="c4a2f-190">SurfaceUpdate\Itouch</span></span>

    <span data-ttu-id="c4a2f-191">Pour prendre en charge surface Laptop 2, importez les dossiers suivants:</span><span class="sxs-lookup"><span data-stu-id="c4a2f-191">To support Surface Laptop 2, import the following folders:</span></span>

     - <span data-ttu-id="c4a2f-192">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="c4a2f-192">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
     - <span data-ttu-id="c4a2f-193">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span><span class="sxs-lookup"><span data-stu-id="c4a2f-193">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span></span>
     - <span data-ttu-id="c4a2f-194">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="c4a2f-194">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
     - <span data-ttu-id="c4a2f-195">SurfacePlatformInstaller\Drivers\System\I2C</span><span class="sxs-lookup"><span data-stu-id="c4a2f-195">SurfacePlatformInstaller\Drivers\System\I2C</span></span>
     - <span data-ttu-id="c4a2f-196">SurfacePlatformInstaller\Drivers\System\SPI</span><span class="sxs-lookup"><span data-stu-id="c4a2f-196">SurfacePlatformInstaller\Drivers\System\SPI</span></span>
     - <span data-ttu-id="c4a2f-197">SurfacePlatformInstaller\Drivers\System\UART</span><span class="sxs-lookup"><span data-stu-id="c4a2f-197">SurfacePlatformInstaller\Drivers\System\UART</span></span>
     - <span data-ttu-id="c4a2f-198">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="c4a2f-198">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

    <span data-ttu-id="c4a2f-199">Ou, pour les nouveaux fichiers MSI commençant par «SurfaceUpdate», utilisez:</span><span class="sxs-lookup"><span data-stu-id="c4a2f-199">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

    - <span data-ttu-id="c4a2f-200">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="c4a2f-200">SurfaceUpdate\SerialIOGPIO</span></span>
    - <span data-ttu-id="c4a2f-201">SurfaceUpdate\IclSerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="c4a2f-201">SurfaceUpdate\IclSerialIOI2C</span></span>
    - <span data-ttu-id="c4a2f-202">SurfaceUpdate\IclSerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="c4a2f-202">SurfaceUpdate\IclSerialIOSPI</span></span>
    - <span data-ttu-id="c4a2f-203">SurfaceUpdate\IclSerialIOUART</span><span class="sxs-lookup"><span data-stu-id="c4a2f-203">SurfaceUpdate\IclSerialIOUART</span></span>
    - <span data-ttu-id="c4a2f-204">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="c4a2f-204">SurfaceUpdate\SurfaceHidMini</span></span>
    - <span data-ttu-id="c4a2f-205">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="c4a2f-205">SurfaceUpdate\SurfaceSerialHub</span></span>
    - <span data-ttu-id="c4a2f-206">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="c4a2f-206">SurfaceUpdate\Itouch</span></span>

    <span data-ttu-id="c4a2f-207">Pour prendre en charge l’ordinateur portable surface 3 avec le processeur Intel, importez les dossiers suivants:</span><span class="sxs-lookup"><span data-stu-id="c4a2f-207">To support Surface Laptop 3 with Intel Processor, import the following folders:</span></span>

    - <span data-ttu-id="c4a2f-208">SurfaceUpdate\IclSerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="c4a2f-208">SurfaceUpdate\IclSerialIOGPIO</span></span>
    - <span data-ttu-id="c4a2f-209">SurfaceUpdate\IclSerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="c4a2f-209">SurfaceUpdate\IclSerialIOI2C</span></span>
    - <span data-ttu-id="c4a2f-210">SurfaceUpdate\IclSerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="c4a2f-210">SurfaceUpdate\IclSerialIOSPI</span></span>
    - <span data-ttu-id="c4a2f-211">SurfaceUpdate\IclSerialIOUART</span><span class="sxs-lookup"><span data-stu-id="c4a2f-211">SurfaceUpdate\IclSerialIOUART</span></span>
    - <span data-ttu-id="c4a2f-212">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="c4a2f-212">SurfaceUpdate\SurfaceHidMini</span></span>
    - <span data-ttu-id="c4a2f-213">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="c4a2f-213">SurfaceUpdate\SurfaceSerialHub</span></span>
    - <span data-ttu-id="c4a2f-214">SurfaceUpdate\SurfaceHotPlug</span><span class="sxs-lookup"><span data-stu-id="c4a2f-214">SurfaceUpdate\SurfaceHotPlug</span></span>
    - <span data-ttu-id="c4a2f-215">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="c4a2f-215">SurfaceUpdate\Itouch</span></span>

    > [!NOTE]
    > <span data-ttu-id="c4a2f-216">Pour surface Laptop 3 avec processeur Intel, le modèle est surface Laptop 3.</span><span class="sxs-lookup"><span data-stu-id="c4a2f-216">For Surface Laptop 3 with Intel processor, the model is Surface Laptop 3.</span></span> <span data-ttu-id="c4a2f-217">Les pilotes portables surface restants se trouvent dans le dossier \MDT de déploiement Share\Out-of-Box Drivers\Windows10\X64\Surface portable 3.</span><span class="sxs-lookup"><span data-stu-id="c4a2f-217">The remaining Surface Laptop drivers are located in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3 folder.</span></span>

6. <span data-ttu-id="c4a2f-218">Vérifiez que le dossier WindowsPEX64 contient désormais les pilotes importés.</span><span class="sxs-lookup"><span data-stu-id="c4a2f-218">Verify that the WindowsPEX64 folder now contains the imported drivers.</span></span> <span data-ttu-id="c4a2f-219">Le dossier doit ressembler à ce qui suit:</span><span class="sxs-lookup"><span data-stu-id="c4a2f-219">The folder should resemble the following:</span></span>  

   ![Image illustrant les pilotes nouvellement importés dans le dossier WindowsPEX64 du Deployment Workbench](./images/surface-laptop-keyboard-2.png)

7. <span data-ttu-id="c4a2f-221">Configurez un profil de sélection qui utilise le dossier WindowsPEX64.</span><span class="sxs-lookup"><span data-stu-id="c4a2f-221">Configure a selection profile that uses the WindowsPEX64 folder.</span></span> <span data-ttu-id="c4a2f-222">Le profil de sélection doit ressembler à ce qui suit:</span><span class="sxs-lookup"><span data-stu-id="c4a2f-222">The selection profile should resemble the following:</span></span>  

   ![Image illustrant le dossier WindowsPEX64 sélectionné dans le cadre d’un profil de sélection](./images/surface-laptop-keyboard-3.png)

8. <span data-ttu-id="c4a2f-224">Configurez les propriétés Windows PE du partage de déploiement MDT pour utiliser le nouveau profil de sélection, comme suit:</span><span class="sxs-lookup"><span data-stu-id="c4a2f-224">Configure the Windows PE properties of the MDT deployment share to use the new selection profile, as follows:</span></span>  

   - <span data-ttu-id="c4a2f-225">Pour **plate-forme**, sélectionnez **x64**.</span><span class="sxs-lookup"><span data-stu-id="c4a2f-225">For **Platform**, select **x64**.</span></span>
   - <span data-ttu-id="c4a2f-226">Pour **profil de sélection**, sélectionnez le nouveau profil.</span><span class="sxs-lookup"><span data-stu-id="c4a2f-226">For **Selection profile**, select the new profile.</span></span>
   - <span data-ttu-id="c4a2f-227">Sélectionnez **inclure tous les pilotes dans le profil de sélection**.</span><span class="sxs-lookup"><span data-stu-id="c4a2f-227">Select **Include all drivers from the selection profile**.</span></span>
   
   ![Image illustrant les propriétés Windows PE du partage de déploiement MDT](./images/surface-laptop-keyboard-4.png)

9. <span data-ttu-id="c4a2f-229">Vérifiez que vous avez configuré les pilotes de surface mobile restants à l’aide d’un profil de sélection ou d’une variable **DriverGroup001** .</span><span class="sxs-lookup"><span data-stu-id="c4a2f-229">Verify that you have configured the remaining Surface Laptop drivers by using either a selection profile or a **DriverGroup001** variable.</span></span>  
   - <span data-ttu-id="c4a2f-230">Pour les ordinateurs portables surface (1er génération), le modèle est **surface Laptop**.</span><span class="sxs-lookup"><span data-stu-id="c4a2f-230">For Surface Laptop (1st Gen), the model is **Surface Laptop**.</span></span> <span data-ttu-id="c4a2f-231">Les autres pilotes de surface pour portables surface doivent résider dans le dossier de déploiement \MDT Share\Out-of-Box Drivers\Windows10\X64\Surface d’ordinateur portable, comme illustré dans la figure qui suit cette liste.</span><span class="sxs-lookup"><span data-stu-id="c4a2f-231">The remaining Surface Laptop drivers should reside in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop folder as shown in the figure that follows this list.</span></span>
   - <span data-ttu-id="c4a2f-232">Pour surface Laptop 2, le modèle est **surface Laptop 2**.</span><span class="sxs-lookup"><span data-stu-id="c4a2f-232">For Surface Laptop 2, the model is **Surface Laptop 2**.</span></span> <span data-ttu-id="c4a2f-233">Les autres pilotes de surface pour ordinateur portable doivent résider dans le dossier \MDT de déploiement Share\Out-of-Box Drivers\Windows10\X64\Surface portable 2.</span><span class="sxs-lookup"><span data-stu-id="c4a2f-233">The remaining Surface Laptop drivers should reside in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 2 folder.</span></span> 
   - <span data-ttu-id="c4a2f-234">Pour surface Laptop 3 avec processeur Intel, le modèle est surface Laptop 3.</span><span class="sxs-lookup"><span data-stu-id="c4a2f-234">For Surface Laptop 3 with Intel processor, the model is Surface Laptop 3.</span></span> <span data-ttu-id="c4a2f-235">Les pilotes portables surface restants se trouvent dans le dossier \MDT de déploiement Share\Out-of-Box Drivers\Windows10\X64\Surface portable 3.</span><span class="sxs-lookup"><span data-stu-id="c4a2f-235">The remaining Surface Laptop drivers are located in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3 folder.</span></span>

   ![Image illustrant les pilotes surface Laptop (1ère génération) standard dans le dossier surface Laptop du Deployment Workbench](./images/surface-laptop-keyboard-5.png)

<span data-ttu-id="c4a2f-237">Après avoir configuré le partage de déploiement MDT pour utiliser le nouveau profil de sélection et les paramètres associés, continuez le processus de déploiement comme décrit dans [la section déploiement d’une image Windows 10 à l’aide de MDT: étape 6: créer la séquence de tâches de déploiement](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt#step-6-create-the-deployment-task-sequence).</span><span class="sxs-lookup"><span data-stu-id="c4a2f-237">After configuring the MDT Deployment Share to use the new selection profile and related settings, continue the deployment process as described in [Deploy a Windows 10 image using MDT: Step 6: Create the deployment task sequence](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt#step-6-create-the-deployment-task-sequence).</span></span>
