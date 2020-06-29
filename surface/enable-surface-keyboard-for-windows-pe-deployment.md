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
ms.openlocfilehash: 5d4e4b46c109d9fe24fe75151c9eb1e0a8b702c0
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832555"
---
# <span data-ttu-id="6123c-104">Comment activer le clavier surface Laptop pour le clavier portable surface lors du déploiement de MDT</span><span class="sxs-lookup"><span data-stu-id="6123c-104">How to enable the Surface Laptop keyboard during MDT deployment</span></span>

<span data-ttu-id="6123c-105">Cet article traite d’une approche de déploiement qui utilise le kit de développement Microsoft Deployment (MDT).</span><span class="sxs-lookup"><span data-stu-id="6123c-105">This article addresses a deployment approach that uses Microsoft Deployment Toolkit (MDT).</span></span> <span data-ttu-id="6123c-106">Vous pouvez également appliquer ces informations à d’autres méthodes de déploiement.</span><span class="sxs-lookup"><span data-stu-id="6123c-106">You can also apply this information to other deployment methodologies.</span></span> <span data-ttu-id="6123c-107">Sur la plupart des types de périphériques surface, le clavier doit fonctionner au cours de l’installation LTI (LTI).</span><span class="sxs-lookup"><span data-stu-id="6123c-107">On most types of Surface devices, the keyboard should work during Lite Touch Installation (LTI).</span></span> <span data-ttu-id="6123c-108">En revanche, le portable surface nécessite des pilotes supplémentaires pour activer le clavier.</span><span class="sxs-lookup"><span data-stu-id="6123c-108">However, Surface Laptop requires some additional drivers to enable the keyboard.</span></span> <span data-ttu-id="6123c-109">Pour les appareils mobiles surface (1ère génération) et surface Laptop 2, vous devez préparer les profils de structure et de sélection des dossiers pour vous permettre de spécifier les pilotes de clavier à utiliser lors de la phase de l’environnement de préinstallation Windows (Windows PE) de LTI.</span><span class="sxs-lookup"><span data-stu-id="6123c-109">For Surface Laptop (1st Gen) and Surface Laptop 2 devices, you must prepare the folder structure and selection profiles that allow you to specify keyboard drivers for use during the Windows Preinstallation Environment (Windows PE) phase of LTI.</span></span> <span data-ttu-id="6123c-110">Pour plus d’informations sur cette structure de dossiers, consultez [la rubrique déploiement d’une image Windows 10 à l’aide de MDT: étape 5: préparer le référentiel de pilotes](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt?redirectedfrom=MSDN#step-5-prepare-the-drivers-repository).</span><span class="sxs-lookup"><span data-stu-id="6123c-110">For more information about this folder structure, see [Deploy a Windows 10 image using MDT: Step 5: Prepare the drivers repository](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt?redirectedfrom=MSDN#step-5-prepare-the-drivers-repository).</span></span>

> [!NOTE]
> <span data-ttu-id="6123c-111">Pour l’instant, cette fonctionnalité n’est pas prise en charge pour ajouter les pilotes de clavier surface Laptop 2 et surface Laptop 3 dans la même instance de démarrage Windows PE en raison d’un conflit de pilote. Utilisez plutôt des instances distinctes.</span><span class="sxs-lookup"><span data-stu-id="6123c-111">It is currently not supported to add Surface Laptop 2 and Surface Laptop 3 keyboard drivers in the same Windows PE boot instance due to a driver conflict; use separate instances instead.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6123c-112">Si vous déployez une image Windows 10 sur un ordinateur portable sur lequel le mode Windows 10 en S est préinstallé, voir KB [4032347, problèmes lors du déploiement de Windows sur les appareils surface avec Windows 10 en mode s préinstallé](https://support.microsoft.com/help/4032347/surface-preinstall-windows10-s-mode-issues).</span><span class="sxs-lookup"><span data-stu-id="6123c-112">If you are deploying a Windows 10 image to a Surface Laptop that has Windows 10 in S mode preinstalled, see KB [4032347, Problems when deploying Windows to Surface devices with preinstalled Windows 10 in S mode](https://support.microsoft.com/help/4032347/surface-preinstall-windows10-s-mode-issues).</span></span>

<span data-ttu-id="6123c-113">Pour ajouter les pilotes du clavier au profil de sélection, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="6123c-113">To add the keyboard drivers to the selection profile, follow these steps:</span></span>

1. <span data-ttu-id="6123c-114">Téléchargez le dernier fichier MSI surface Laptop à partir des emplacements appropriés:</span><span class="sxs-lookup"><span data-stu-id="6123c-114">Download the latest Surface Laptop MSI file from the appropriate locations:</span></span>
    - [<span data-ttu-id="6123c-115">Pilotes de surface Laptop (1ère génération) et microprogramme</span><span class="sxs-lookup"><span data-stu-id="6123c-115">Surface Laptop (1st Gen) Drivers and Firmware</span></span>](https://www.microsoft.com/download/details.aspx?id=55489)
    - [<span data-ttu-id="6123c-116">Micropilote surface Laptop 2 et microprogramme</span><span class="sxs-lookup"><span data-stu-id="6123c-116">Surface Laptop 2 Drivers and Firmware</span></span>](https://www.microsoft.com/download/details.aspx?id=57515)
    - [<span data-ttu-id="6123c-117">Surface Laptop 3 avec pilotes de processeur Intel et microprogramme</span><span class="sxs-lookup"><span data-stu-id="6123c-117">Surface Laptop 3 with Intel Processor Drivers and Firmware</span></span>](https://www.microsoft.com/download/details.aspx?id=100429)

2. <span data-ttu-id="6123c-118">Extrayez le contenu du fichier MSI surface Laptop dans un dossier que vous pouvez facilement retrouver (par exemple, c:\ surface_laptop_drivers).</span><span class="sxs-lookup"><span data-stu-id="6123c-118">Extract the contents of the Surface Laptop MSI file to a folder that you can easily locate (for example, c:\surface_laptop_drivers).</span></span> <span data-ttu-id="6123c-119">Pour extraire le contenu, ouvrez une fenêtre d’invite de commandes avec élévation de privilèges et exécutez la commande à partir de l’exemple suivant:</span><span class="sxs-lookup"><span data-stu-id="6123c-119">To extract the contents, open an elevated Command Prompt window and run the command from the following example:</span></span>

   ```cmd
   Msiexec.exe /a SurfaceLaptop_Win10_15063_1703008_1.msi targetdir=c:\surface_laptop_drivers /qn
   ```

3. <span data-ttu-id="6123c-120">Ouvrez le Deployment Workbench et développez le nœud **partages de déploiement** et votre partage de déploiement, puis accédez au dossier **WindowsPEX64** .</span><span class="sxs-lookup"><span data-stu-id="6123c-120">Open the Deployment Workbench and expand the **Deployment Shares** node and your deployment share, then navigate to the **WindowsPEX64** folder.</span></span>

   ![Image illustrant l’emplacement du dossier WindowsPEX64 dans Deployment Workbench](./images/surface-laptop-keyboard-1.png)

4. <span data-ttu-id="6123c-122">Cliquez avec le bouton droit sur le dossier **WindowsPEX64** et sélectionnez **Importer les pilotes**.</span><span class="sxs-lookup"><span data-stu-id="6123c-122">Right-click the **WindowsPEX64** folder and select **Import Drivers**.</span></span>
5. <span data-ttu-id="6123c-123">Pour importer les dossiers de pilotes dans le dossier WindowsPEX64, suivez les instructions de l’Assistant importation de pilote.</span><span class="sxs-lookup"><span data-stu-id="6123c-123">Follow the instructions in the Import Driver Wizard to import the driver folders into the WindowsPEX64 folder.</span></span>  

> [!NOTE]
>  <span data-ttu-id="6123c-124">Vérifiez le package MSI téléchargé pour déterminer le format et la structure du répertoire.</span><span class="sxs-lookup"><span data-stu-id="6123c-124">Check the downloaded MSI package to determine the format and directory structure.</span></span>  <span data-ttu-id="6123c-125">La structure de l’annuaire va commencer par SurfacePlatformInstaller (fichiers MSI plus anciens) ou SurfaceUpdate (nouveaux fichiers MSI) selon le moment de la sortie du MSI.</span><span class="sxs-lookup"><span data-stu-id="6123c-125">The directory structure will start with either SurfacePlatformInstaller (older MSI files) or SurfaceUpdate (Newer MSI files) depending on when the MSI was released.</span></span> 

<span data-ttu-id="6123c-126">Pour prendre en charge l’ordinateur portable surface (1ère génération), importez les dossiers suivants:</span><span class="sxs-lookup"><span data-stu-id="6123c-126">To support Surface Laptop (1st Gen), import the following folders:</span></span>

 - <span data-ttu-id="6123c-127">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="6123c-127">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
 - <span data-ttu-id="6123c-128">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="6123c-128">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span></span>
 - <span data-ttu-id="6123c-129">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="6123c-129">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
 - <span data-ttu-id="6123c-130">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="6123c-130">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

<span data-ttu-id="6123c-131">Ou, pour les nouveaux fichiers MSI commençant par «SurfaceUpdate», utilisez:</span><span class="sxs-lookup"><span data-stu-id="6123c-131">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

- <span data-ttu-id="6123c-132">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="6123c-132">SurfaceUpdate\SerialIOGPIO</span></span>
- <span data-ttu-id="6123c-133">SurfaceUpdate\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="6123c-133">SurfaceUpdate\SurfaceHidMiniDriver</span></span>
- <span data-ttu-id="6123c-134">SurfaceUpdate\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="6123c-134">SurfaceUpdate\SurfaceSerialHubDriver</span></span>
- <span data-ttu-id="6123c-135">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="6123c-135">SurfaceUpdate\Itouch</span></span>

<span data-ttu-id="6123c-136">Pour prendre en charge surface Laptop 2, importez les dossiers suivants:</span><span class="sxs-lookup"><span data-stu-id="6123c-136">To support Surface Laptop 2, import the following folders:</span></span>

 - <span data-ttu-id="6123c-137">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="6123c-137">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
 - <span data-ttu-id="6123c-138">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span><span class="sxs-lookup"><span data-stu-id="6123c-138">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span></span>
 - <span data-ttu-id="6123c-139">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="6123c-139">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
 - <span data-ttu-id="6123c-140">SurfacePlatformInstaller\Drivers\System\I2C</span><span class="sxs-lookup"><span data-stu-id="6123c-140">SurfacePlatformInstaller\Drivers\System\I2C</span></span>
 - <span data-ttu-id="6123c-141">SurfacePlatformInstaller\Drivers\System\SPI</span><span class="sxs-lookup"><span data-stu-id="6123c-141">SurfacePlatformInstaller\Drivers\System\SPI</span></span>
 - <span data-ttu-id="6123c-142">SurfacePlatformInstaller\Drivers\System\UART</span><span class="sxs-lookup"><span data-stu-id="6123c-142">SurfacePlatformInstaller\Drivers\System\UART</span></span>
 - <span data-ttu-id="6123c-143">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="6123c-143">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

<span data-ttu-id="6123c-144">Ou, pour les nouveaux fichiers MSI commençant par «SurfaceUpdate», utilisez:</span><span class="sxs-lookup"><span data-stu-id="6123c-144">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

- <span data-ttu-id="6123c-145">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="6123c-145">SurfaceUpdate\SerialIOGPIO</span></span>
- <span data-ttu-id="6123c-146">SurfaceUpdate\IclSerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="6123c-146">SurfaceUpdate\IclSerialIOI2C</span></span>
- <span data-ttu-id="6123c-147">SurfaceUpdate\IclSerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="6123c-147">SurfaceUpdate\IclSerialIOSPI</span></span>
- <span data-ttu-id="6123c-148">SurfaceUpdate\IclSerialIOUART</span><span class="sxs-lookup"><span data-stu-id="6123c-148">SurfaceUpdate\IclSerialIOUART</span></span>
- <span data-ttu-id="6123c-149">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="6123c-149">SurfaceUpdate\SurfaceHidMini</span></span>
- <span data-ttu-id="6123c-150">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="6123c-150">SurfaceUpdate\SurfaceSerialHub</span></span>
- <span data-ttu-id="6123c-151">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="6123c-151">SurfaceUpdate\Itouch</span></span>

 
<span data-ttu-id="6123c-152">Pour prendre en charge l’ordinateur portable surface 3 avec le processeur Intel, importez les dossiers suivants:</span><span class="sxs-lookup"><span data-stu-id="6123c-152">To support Surface Laptop 3 with Intel Processor, import the following folders:</span></span>

- <span data-ttu-id="6123c-153">SurfaceUpdate\IclSerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="6123c-153">SurfaceUpdate\IclSerialIOGPIO</span></span>
- <span data-ttu-id="6123c-154">SurfaceUpdate\IclSerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="6123c-154">SurfaceUpdate\IclSerialIOI2C</span></span>
- <span data-ttu-id="6123c-155">SurfaceUpdate\IclSerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="6123c-155">SurfaceUpdate\IclSerialIOSPI</span></span>
- <span data-ttu-id="6123c-156">SurfaceUpdate\IclSerialIOUART</span><span class="sxs-lookup"><span data-stu-id="6123c-156">SurfaceUpdate\IclSerialIOUART</span></span>
- <span data-ttu-id="6123c-157">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="6123c-157">SurfaceUpdate\SurfaceHidMini</span></span>
- <span data-ttu-id="6123c-158">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="6123c-158">SurfaceUpdate\SurfaceSerialHub</span></span>
- <span data-ttu-id="6123c-159">SurfaceUpdate\SurfaceHotPlug</span><span class="sxs-lookup"><span data-stu-id="6123c-159">SurfaceUpdate\SurfaceHotPlug</span></span>
- <span data-ttu-id="6123c-160">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="6123c-160">SurfaceUpdate\Itouch</span></span>

<span data-ttu-id="6123c-161">L’importation des dossiers suivants permettra de bénéficier de la fonctionnalité complète du clavier, de pavé tactile et de l’interaction avec le complément PE pour surface Laptop 3.</span><span class="sxs-lookup"><span data-stu-id="6123c-161">Importing the following folders will enable full keyboard, trackpad, and touch functionality in PE for Surface Laptop 3.</span></span>

- <span data-ttu-id="6123c-162">IclSerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="6123c-162">IclSerialIOGPIO</span></span>
- <span data-ttu-id="6123c-163">IclSerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="6123c-163">IclSerialIOI2C</span></span>
- <span data-ttu-id="6123c-164">IclSerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="6123c-164">IclSerialIOSPI</span></span>
- <span data-ttu-id="6123c-165">IclSerialIOUART</span><span class="sxs-lookup"><span data-stu-id="6123c-165">IclSerialIOUART</span></span>
- <span data-ttu-id="6123c-166">iTouch</span><span class="sxs-lookup"><span data-stu-id="6123c-166">itouch</span></span>
- <span data-ttu-id="6123c-167">IclChipset</span><span class="sxs-lookup"><span data-stu-id="6123c-167">IclChipset</span></span>
- <span data-ttu-id="6123c-168">IclChipsetLPSS</span><span class="sxs-lookup"><span data-stu-id="6123c-168">IclChipsetLPSS</span></span>
- <span data-ttu-id="6123c-169">IclChipsetNorthpeak</span><span class="sxs-lookup"><span data-stu-id="6123c-169">IclChipsetNorthpeak</span></span>
- <span data-ttu-id="6123c-170">ManagementEngine</span><span class="sxs-lookup"><span data-stu-id="6123c-170">ManagementEngine</span></span>
- <span data-ttu-id="6123c-171">SurfaceAcpiNotify</span><span class="sxs-lookup"><span data-stu-id="6123c-171">SurfaceAcpiNotify</span></span>
- <span data-ttu-id="6123c-172">SurfaceBattery</span><span class="sxs-lookup"><span data-stu-id="6123c-172">SurfaceBattery</span></span>
- <span data-ttu-id="6123c-173">SurfaceDockIntegration</span><span class="sxs-lookup"><span data-stu-id="6123c-173">SurfaceDockIntegration</span></span>
- <span data-ttu-id="6123c-174">SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="6123c-174">SurfaceHidMini</span></span>
- <span data-ttu-id="6123c-175">SurfaceHotPlug</span><span class="sxs-lookup"><span data-stu-id="6123c-175">SurfaceHotPlug</span></span>
- <span data-ttu-id="6123c-176">SurfaceIntegration</span><span class="sxs-lookup"><span data-stu-id="6123c-176">SurfaceIntegration</span></span>
- <span data-ttu-id="6123c-177">SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="6123c-177">SurfaceSerialHub</span></span>
- <span data-ttu-id="6123c-178">SurfaceService</span><span class="sxs-lookup"><span data-stu-id="6123c-178">SurfaceService</span></span>
- <span data-ttu-id="6123c-179">SurfaceStorageFwUpdate</span><span class="sxs-lookup"><span data-stu-id="6123c-179">SurfaceStorageFwUpdate</span></span>


    > [!NOTE]
    >  <span data-ttu-id="6123c-180">Vérifiez le package MSI téléchargé pour déterminer le format et la structure du répertoire.</span><span class="sxs-lookup"><span data-stu-id="6123c-180">Check the downloaded MSI package to determine the format and directory structure.</span></span>  <span data-ttu-id="6123c-181">La structure de l’annuaire va commencer par SurfacePlatformInstaller (fichiers MSI plus anciens) ou SurfaceUpdate (nouveaux fichiers MSI) selon le moment de la sortie du MSI.</span><span class="sxs-lookup"><span data-stu-id="6123c-181">The directory structure will start with either SurfacePlatformInstaller (older MSI files) or SurfaceUpdate (Newer MSI files) depending on when the MSI was released.</span></span> 

    <span data-ttu-id="6123c-182">Pour prendre en charge l’ordinateur portable surface (1ère génération), importez les dossiers suivants:</span><span class="sxs-lookup"><span data-stu-id="6123c-182">To support Surface Laptop (1st Gen), import the following folders:</span></span>

     - <span data-ttu-id="6123c-183">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="6123c-183">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
     - <span data-ttu-id="6123c-184">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="6123c-184">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span></span>
     - <span data-ttu-id="6123c-185">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="6123c-185">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
     - <span data-ttu-id="6123c-186">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="6123c-186">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

    <span data-ttu-id="6123c-187">Ou, pour les nouveaux fichiers MSI commençant par «SurfaceUpdate», utilisez:</span><span class="sxs-lookup"><span data-stu-id="6123c-187">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

    - <span data-ttu-id="6123c-188">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="6123c-188">SurfaceUpdate\SerialIOGPIO</span></span>
    - <span data-ttu-id="6123c-189">SurfaceUpdate\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="6123c-189">SurfaceUpdate\SurfaceHidMiniDriver</span></span>
    - <span data-ttu-id="6123c-190">SurfaceUpdate\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="6123c-190">SurfaceUpdate\SurfaceSerialHubDriver</span></span>
    - <span data-ttu-id="6123c-191">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="6123c-191">SurfaceUpdate\Itouch</span></span>

    <span data-ttu-id="6123c-192">Pour prendre en charge surface Laptop 2, importez les dossiers suivants:</span><span class="sxs-lookup"><span data-stu-id="6123c-192">To support Surface Laptop 2, import the following folders:</span></span>

     - <span data-ttu-id="6123c-193">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="6123c-193">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
     - <span data-ttu-id="6123c-194">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span><span class="sxs-lookup"><span data-stu-id="6123c-194">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span></span>
     - <span data-ttu-id="6123c-195">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="6123c-195">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
     - <span data-ttu-id="6123c-196">SurfacePlatformInstaller\Drivers\System\I2C</span><span class="sxs-lookup"><span data-stu-id="6123c-196">SurfacePlatformInstaller\Drivers\System\I2C</span></span>
     - <span data-ttu-id="6123c-197">SurfacePlatformInstaller\Drivers\System\SPI</span><span class="sxs-lookup"><span data-stu-id="6123c-197">SurfacePlatformInstaller\Drivers\System\SPI</span></span>
     - <span data-ttu-id="6123c-198">SurfacePlatformInstaller\Drivers\System\UART</span><span class="sxs-lookup"><span data-stu-id="6123c-198">SurfacePlatformInstaller\Drivers\System\UART</span></span>
     - <span data-ttu-id="6123c-199">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="6123c-199">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

    <span data-ttu-id="6123c-200">Ou, pour les nouveaux fichiers MSI commençant par «SurfaceUpdate», utilisez:</span><span class="sxs-lookup"><span data-stu-id="6123c-200">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

    - <span data-ttu-id="6123c-201">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="6123c-201">SurfaceUpdate\SerialIOGPIO</span></span>
    - <span data-ttu-id="6123c-202">SurfaceUpdate\IclSerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="6123c-202">SurfaceUpdate\IclSerialIOI2C</span></span>
    - <span data-ttu-id="6123c-203">SurfaceUpdate\IclSerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="6123c-203">SurfaceUpdate\IclSerialIOSPI</span></span>
    - <span data-ttu-id="6123c-204">SurfaceUpdate\IclSerialIOUART</span><span class="sxs-lookup"><span data-stu-id="6123c-204">SurfaceUpdate\IclSerialIOUART</span></span>
    - <span data-ttu-id="6123c-205">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="6123c-205">SurfaceUpdate\SurfaceHidMini</span></span>
    - <span data-ttu-id="6123c-206">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="6123c-206">SurfaceUpdate\SurfaceSerialHub</span></span>
    - <span data-ttu-id="6123c-207">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="6123c-207">SurfaceUpdate\Itouch</span></span>

    <span data-ttu-id="6123c-208">Pour prendre en charge l’ordinateur portable surface 3 avec le processeur Intel, importez les dossiers suivants:</span><span class="sxs-lookup"><span data-stu-id="6123c-208">To support Surface Laptop 3 with Intel Processor, import the following folders:</span></span>

    - <span data-ttu-id="6123c-209">SurfaceUpdate\IclSerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="6123c-209">SurfaceUpdate\IclSerialIOGPIO</span></span>
    - <span data-ttu-id="6123c-210">SurfaceUpdate\IclSerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="6123c-210">SurfaceUpdate\IclSerialIOI2C</span></span>
    - <span data-ttu-id="6123c-211">SurfaceUpdate\IclSerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="6123c-211">SurfaceUpdate\IclSerialIOSPI</span></span>
    - <span data-ttu-id="6123c-212">SurfaceUpdate\IclSerialIOUART</span><span class="sxs-lookup"><span data-stu-id="6123c-212">SurfaceUpdate\IclSerialIOUART</span></span>
    - <span data-ttu-id="6123c-213">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="6123c-213">SurfaceUpdate\SurfaceHidMini</span></span>
    - <span data-ttu-id="6123c-214">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="6123c-214">SurfaceUpdate\SurfaceSerialHub</span></span>
    - <span data-ttu-id="6123c-215">SurfaceUpdate\SurfaceHotPlug</span><span class="sxs-lookup"><span data-stu-id="6123c-215">SurfaceUpdate\SurfaceHotPlug</span></span>
    - <span data-ttu-id="6123c-216">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="6123c-216">SurfaceUpdate\Itouch</span></span>

    > [!NOTE]
    > <span data-ttu-id="6123c-217">Pour surface Laptop 3 avec processeur Intel, le modèle est surface Laptop 3.</span><span class="sxs-lookup"><span data-stu-id="6123c-217">For Surface Laptop 3 with Intel processor, the model is Surface Laptop 3.</span></span> <span data-ttu-id="6123c-218">Les pilotes portables surface restants se trouvent dans le dossier \MDT de déploiement Share\Out-of-Box Drivers\Windows10\X64\Surface portable 3.</span><span class="sxs-lookup"><span data-stu-id="6123c-218">The remaining Surface Laptop drivers are located in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3 folder.</span></span>

6. <span data-ttu-id="6123c-219">Vérifiez que le dossier WindowsPEX64 contient désormais les pilotes importés.</span><span class="sxs-lookup"><span data-stu-id="6123c-219">Verify that the WindowsPEX64 folder now contains the imported drivers.</span></span> <span data-ttu-id="6123c-220">Le dossier doit ressembler à ce qui suit:</span><span class="sxs-lookup"><span data-stu-id="6123c-220">The folder should resemble the following:</span></span>  

   ![Image illustrant les pilotes nouvellement importés dans le dossier WindowsPEX64 du Deployment Workbench](./images/surface-laptop-keyboard-2.png)

7. <span data-ttu-id="6123c-222">Configurez un profil de sélection qui utilise le dossier WindowsPEX64.</span><span class="sxs-lookup"><span data-stu-id="6123c-222">Configure a selection profile that uses the WindowsPEX64 folder.</span></span> <span data-ttu-id="6123c-223">Le profil de sélection doit ressembler à ce qui suit:</span><span class="sxs-lookup"><span data-stu-id="6123c-223">The selection profile should resemble the following:</span></span>  

   ![Image illustrant le dossier WindowsPEX64 sélectionné dans le cadre d’un profil de sélection](./images/surface-laptop-keyboard-3.png)

8. <span data-ttu-id="6123c-225">Configurez les propriétés Windows PE du partage de déploiement MDT pour utiliser le nouveau profil de sélection, comme suit:</span><span class="sxs-lookup"><span data-stu-id="6123c-225">Configure the Windows PE properties of the MDT deployment share to use the new selection profile, as follows:</span></span>  

   - <span data-ttu-id="6123c-226">Pour **plate-forme**, sélectionnez **x64**.</span><span class="sxs-lookup"><span data-stu-id="6123c-226">For **Platform**, select **x64**.</span></span>
   - <span data-ttu-id="6123c-227">Pour **profil de sélection**, sélectionnez le nouveau profil.</span><span class="sxs-lookup"><span data-stu-id="6123c-227">For **Selection profile**, select the new profile.</span></span>
   - <span data-ttu-id="6123c-228">Sélectionnez **inclure tous les pilotes dans le profil de sélection**.</span><span class="sxs-lookup"><span data-stu-id="6123c-228">Select **Include all drivers from the selection profile**.</span></span>
   
   ![Image illustrant les propriétés Windows PE du partage de déploiement MDT](./images/surface-laptop-keyboard-4.png)

9. <span data-ttu-id="6123c-230">Vérifiez que vous avez configuré les pilotes de surface mobile restants à l’aide d’un profil de sélection ou d’une variable **DriverGroup001** .</span><span class="sxs-lookup"><span data-stu-id="6123c-230">Verify that you have configured the remaining Surface Laptop drivers by using either a selection profile or a **DriverGroup001** variable.</span></span>  
   - <span data-ttu-id="6123c-231">Pour les ordinateurs portables surface (1er génération), le modèle est **surface Laptop**.</span><span class="sxs-lookup"><span data-stu-id="6123c-231">For Surface Laptop (1st Gen), the model is **Surface Laptop**.</span></span> <span data-ttu-id="6123c-232">Les autres pilotes de surface pour portables surface doivent résider dans le dossier de déploiement \MDT Share\Out-of-Box Drivers\Windows10\X64\Surface d’ordinateur portable, comme illustré dans la figure qui suit cette liste.</span><span class="sxs-lookup"><span data-stu-id="6123c-232">The remaining Surface Laptop drivers should reside in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop folder as shown in the figure that follows this list.</span></span>
   - <span data-ttu-id="6123c-233">Pour surface Laptop 2, le modèle est **surface Laptop 2**.</span><span class="sxs-lookup"><span data-stu-id="6123c-233">For Surface Laptop 2, the model is **Surface Laptop 2**.</span></span> <span data-ttu-id="6123c-234">Les autres pilotes de surface pour ordinateur portable doivent résider dans le dossier \MDT de déploiement Share\Out-of-Box Drivers\Windows10\X64\Surface portable 2.</span><span class="sxs-lookup"><span data-stu-id="6123c-234">The remaining Surface Laptop drivers should reside in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 2 folder.</span></span> 
   - <span data-ttu-id="6123c-235">Pour surface Laptop 3 avec processeur Intel, le modèle est surface Laptop 3.</span><span class="sxs-lookup"><span data-stu-id="6123c-235">For Surface Laptop 3 with Intel processor, the model is Surface Laptop 3.</span></span> <span data-ttu-id="6123c-236">Les pilotes portables surface restants se trouvent dans le dossier \MDT de déploiement Share\Out-of-Box Drivers\Windows10\X64\Surface portable 3.</span><span class="sxs-lookup"><span data-stu-id="6123c-236">The remaining Surface Laptop drivers are located in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3 folder.</span></span>

   ![Image illustrant les pilotes surface Laptop (1ère génération) standard dans le dossier surface Laptop du Deployment Workbench](./images/surface-laptop-keyboard-5.png)

<span data-ttu-id="6123c-238">Après avoir configuré le partage de déploiement MDT pour utiliser le nouveau profil de sélection et les paramètres associés, continuez le processus de déploiement comme décrit dans [la section déploiement d’une image Windows 10 à l’aide de MDT: étape 6: créer la séquence de tâches de déploiement](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt#step-6-create-the-deployment-task-sequence).</span><span class="sxs-lookup"><span data-stu-id="6123c-238">After configuring the MDT Deployment Share to use the new selection profile and related settings, continue the deployment process as described in [Deploy a Windows 10 image using MDT: Step 6: Create the deployment task sequence](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt#step-6-create-the-deployment-task-sequence).</span></span>
