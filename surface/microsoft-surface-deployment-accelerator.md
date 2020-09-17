---
title: Microsoft Surface Deployment Accelerator (Surface)
description: Microsoft Surface Deployment Accelerator offre aux organisations un mécanisme simple et rapide de déploiement dédié à la réinitialisation des appareilsSurface.
ms.assetid: E7991E90-4AAE-44B6-8822-58BFDE3EADE4
ms.reviewer: hachidan
manager: laurawi
ms.localizationpriority: medium
keywords: déployer, installer, outil
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.audience: itpro
ms.date: 5/08/2020
ms.openlocfilehash: 3ede7311289dc4bc720735c0142ff3a46fbb69e7
ms.sourcegitcommit: 582c5a79881c58c4f1aa66cfcab46db966ca9f24
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/16/2020
ms.locfileid: "11016555"
---
# <span data-ttu-id="f8eb8-104">Microsoft Surface Deployment Accelerator</span><span class="sxs-lookup"><span data-stu-id="f8eb8-104">Microsoft Surface Deployment Accelerator</span></span>

<span data-ttu-id="f8eb8-105">Microsoft surface Deployment Accelerator (SDA) automatise la création et la configuration d’une interface de déploiement recommandée par Microsoft en utilisant des outils de déploiement gratuits de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f8eb8-105">Microsoft Surface Deployment Accelerator (SDA) automates the creation and configuration of a Microsoft recommended deployment experience by using free Microsoft deployment tools.</span></span>

<span data-ttu-id="f8eb8-106">Repensée en avril 2020 pour simplifier et automatiser le déploiement d’images surface dans un environnement d’entreprise, l’outil SDA vous permet de générer une image Windows de type usine que vous pouvez personnaliser selon les besoins de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="f8eb8-106">Redesigned in April 2020 to simplify and automate deployment of Surface images in a corporate environment, the SDA tool allows you to build a “factory-like” Windows image that you can customize to your organizational requirements.</span></span>

<span data-ttu-id="f8eb8-107">L’outil SDA Open source, qui est piloté par un script exploite le kit de déploiement d’évaluation et de déploiement Windows (ADK) pour Windows 10, facilitant la création d’images Windows (WIM) dans les environnements de test ou de production.</span><span class="sxs-lookup"><span data-stu-id="f8eb8-107">The open source, script-driven SDA tool leverages the Windows Assessment and Deployment Kit (ADK) for Windows 10, facilitating the creation of Windows images (WIM) in test or production environments.</span></span> <span data-ttu-id="f8eb8-108">Si le dernier logiciel ADK n’est pas déjà installé, il sera téléchargé et installé lors de l’exécution de l’outil SDA.</span><span class="sxs-lookup"><span data-stu-id="f8eb8-108">If the latest ADK is not already installed, it will be downloaded and installed when running the SDA tool.</span></span>

<span data-ttu-id="f8eb8-109">L’image obtenue correspond étroitement à la configuration des images de récupération d’urgence, sans aucune application préinstallée telle que Microsoft Office ou l’application UWP surface.</span><span class="sxs-lookup"><span data-stu-id="f8eb8-109">The resulting image closely matches the configuration of Bare Metal Recovery (BMR) images, without any pre-installed applications such as Microsoft Office or the Surface UWP application.</span></span>

## <span data-ttu-id="f8eb8-110">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="f8eb8-110">Requirements</span></span>

1. <span data-ttu-id="f8eb8-111">Une clé USB USB d’au moins 16 Go.</span><span class="sxs-lookup"><span data-stu-id="f8eb8-111">A USB thumb drive at least 16 GB in size.</span></span> <span data-ttu-id="f8eb8-112">Le lecteur USB sera formaté.</span><span class="sxs-lookup"><span data-stu-id="f8eb8-112">The USB drive will be formatted.</span></span>
2. <span data-ttu-id="f8eb8-113">Un fichier. ISO avec Windows 10 professionnel ou Windows 10 entreprise.</span><span class="sxs-lookup"><span data-stu-id="f8eb8-113">An .iso file with Windows 10 Pro or Windows 10 Enterprise.</span></span> <span data-ttu-id="f8eb8-114">Vous pouvez utiliser l’outil de création de médias pour télécharger Windows 10 et créer un fichier. ISO.</span><span class="sxs-lookup"><span data-stu-id="f8eb8-114">The media creation tool can be used to download Windows 10 and create an .iso file.</span></span> <span data-ttu-id="f8eb8-115">Pour plus d’informations, reportez-vous à [Télécharger Windows 10](https://www.microsoft.com/software-download/windows10).</span><span class="sxs-lookup"><span data-stu-id="f8eb8-115">For more information, see [Download Windows 10](https://www.microsoft.com/software-download/windows10).</span></span>
3. <span data-ttu-id="f8eb8-116">Un appareil exécutant Windows 10, version 2004 ou ultérieure avec accès Internet.</span><span class="sxs-lookup"><span data-stu-id="f8eb8-116">A device running Windows 10, version 2004 or later with Internet access.</span></span>

<span data-ttu-id="f8eb8-117">Pour obtenir la liste détaillée des exigences, voir la section [configuration](https://github.com/microsoft/SurfaceDeploymentAccelerator/blob/master/README.md#prerequisites) requise du document Lisezmoi.</span><span class="sxs-lookup"><span data-stu-id="f8eb8-117">See the [Prerequisites](https://github.com/microsoft/SurfaceDeploymentAccelerator/blob/master/README.md#prerequisites) section of the README document for a detailed list of requirements.</span></span>

## <span data-ttu-id="f8eb8-118">Exécution du SDA</span><span class="sxs-lookup"><span data-stu-id="f8eb8-118">How to run the SDA</span></span>

**<span data-ttu-id="f8eb8-119">Pour exécuter SDA:</span><span class="sxs-lookup"><span data-stu-id="f8eb8-119">To run SDA:</span></span>**

1. <span data-ttu-id="f8eb8-120">Accédez à [SurfaceDeploymentAccelerator](https://github.com/microsoft/SurfaceDeploymentAccelerator) sur GitHub.</span><span class="sxs-lookup"><span data-stu-id="f8eb8-120">Go to [SurfaceDeploymentAccelerator](https://github.com/microsoft/SurfaceDeploymentAccelerator) on GitHub.</span></span> 
2. <span data-ttu-id="f8eb8-121">Consultez la documentation [Lisez-moi](https://github.com/microsoft/SurfaceDeploymentAccelerator/blob/master/README.md) .</span><span class="sxs-lookup"><span data-stu-id="f8eb8-121">Review the [README](https://github.com/microsoft/SurfaceDeploymentAccelerator/blob/master/README.md) documentation.</span></span>
3. <span data-ttu-id="f8eb8-122">Dans la page [SurfaceDeploymentAccelerator](https://github.com/microsoft/SurfaceDeploymentAccelerator) , cliquez sur le bouton **code** , puis sélectionnez **Télécharger zip** pour enregistrer les fichiers localement sur votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="f8eb8-122">On the [SurfaceDeploymentAccelerator](https://github.com/microsoft/SurfaceDeploymentAccelerator) page, click the **Code** button and then select **Download ZIP** to save the files locally on your computer.</span></span>
4. <span data-ttu-id="f8eb8-123">Cliquez avec le bouton droit sur le fichier. zip, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="f8eb8-123">Right-click the .zip file and then click **Properties**.</span></span>
5. <span data-ttu-id="f8eb8-124">Dans l’onglet **général** , activez la case à cocher **débloquer** , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f8eb8-124">On the **General** tab, select the **Unblock** checkbox and then click **OK**.</span></span>
6. <span data-ttu-id="f8eb8-125">Extrayez le fichier. zip vers un emplacement sur votre disque dur (par exemple: C:\SDA).</span><span class="sxs-lookup"><span data-stu-id="f8eb8-125">Extract the .zip file to a location on your hard drive (ex: C:\SDA).</span></span>
7. <span data-ttu-id="f8eb8-126">Ouvrez une invite Windows PowerShell avec élévation de privilèges et définissez ExecutionPolicy pour la session actuelle sur non restreint.</span><span class="sxs-lookup"><span data-stu-id="f8eb8-126">Open an elevated Windows PowerShell prompt and set ExecutionPolicy for the current session to Unrestricted.</span></span>

    ```powershell
    Set-ExecutionPolicy -Scope Process -ExecutionPolicy Unrestricted -Force
    ```
8. <span data-ttu-id="f8eb8-127">Exécutez le script SDA spécifiant les paramètres pour votre environnement.</span><span class="sxs-lookup"><span data-stu-id="f8eb8-127">Run the SDA script specifying parameters for your environment.</span></span> <span data-ttu-id="f8eb8-128">Le script peut être utilisé pour créer des images et installer Windows 10 sur de nombreux appareils surface.</span><span class="sxs-lookup"><span data-stu-id="f8eb8-128">The script can be used to create images to install Windows 10 on a variety of Surface devices.</span></span> <span data-ttu-id="f8eb8-129">Pour obtenir la liste complète des appareils pris en charge, consultez la [Description du paramètre d’appareil](https://github.com/microsoft/SurfaceDeploymentAccelerator/blob/master/README.md#full-parameter-documentation) dans l’article Lisezmoi de SDA.</span><span class="sxs-lookup"><span data-stu-id="f8eb8-129">For a full list of supported devices, see the [Device parameter description](https://github.com/microsoft/SurfaceDeploymentAccelerator/blob/master/README.md#full-parameter-documentation) in the SDA README article.</span></span> 

    <span data-ttu-id="f8eb8-130">Par exemple, la commande suivante permet de créer un lecteur USB amorçable qui peut être utilisé pour [installer Windows 10 sur surface Hub 2](https://docs.microsoft.com/surface-hub/surface-hub-2s-migrate-os):</span><span class="sxs-lookup"><span data-stu-id="f8eb8-130">For example, the following command will create a bootable USB drive that can be used to [install Windows 10 on Surface Hub 2](https://docs.microsoft.com/surface-hub/surface-hub-2s-migrate-os):</span></span>

    ```powershell
    .\CreateSurfaceWindowsImage.ps1 -ISO C:\SDA\enterprise_client.iso -OSSKU Enterprise -DestinationFolder C:\Output -Device SurfaceHub2 -CreateUSB $True
    ```
    <span data-ttu-id="f8eb8-131">Voici un exemple de sortie de script ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="f8eb8-131">Sample script output is below.</span></span>

   ![Outil accélérateur de déploiement de surface exécuté](images/sda1.png)

    <span data-ttu-id="f8eb8-133">Le script nécessite environ 45 minutes pour s’exécuter, mais peut prendre plus de temps en fonction des ressources du processeur et du disque disponibles.</span><span class="sxs-lookup"><span data-stu-id="f8eb8-133">The script will require about 45 minutes to run, but could take longer depending on available CPU and disk resources.</span></span> 

    <span data-ttu-id="f8eb8-134">Une fois que vous avez créé une image Windows, le script vous demande d’insérer et de confirmer la lettre de lecteur de votre lecteur USB.</span><span class="sxs-lookup"><span data-stu-id="f8eb8-134">After creating a Windows image, the script will ask you to insert and confirm the drive letter of your USB drive.</span></span> <span data-ttu-id="f8eb8-135">Le lecteur USB est alors formaté, configuré comme amorçable et les fichiers copiés pour permettre l’installation de l’image Windows 10 personnalisée pour les appareils surface.</span><span class="sxs-lookup"><span data-stu-id="f8eb8-135">The USB drive will then be formatted, configured as bootable, and files copied to enable installation of the custom Windows 10 image for Surface devices.</span></span>

9. <span data-ttu-id="f8eb8-136">Insérez le lecteur USB dans l’appareil sur lequel vous voulez installer Windows 10, puis redémarrez l’installation pour commencer l’installation de Windows 10.</span><span class="sxs-lookup"><span data-stu-id="f8eb8-136">Insert the USB drive into the device where you want to install Windows 10 and reboot to begin installing Windows 10.</span></span> <span data-ttu-id="f8eb8-137">Le démarrage USB doit être activé dans le BIOS, ce qui peut nécessiter le Désactivation temporaire du démarrage sécurisé.</span><span class="sxs-lookup"><span data-stu-id="f8eb8-137">USB boot must be enabled in BIOS, which can require that you temporarily disable Secure Boot.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f8eb8-138">Le démarrage à partir du lecteur USB commence immédiatement l’installation de Windows 10.</span><span class="sxs-lookup"><span data-stu-id="f8eb8-138">Booting from the USB drive will immediately begin installing Windows 10.</span></span> <span data-ttu-id="f8eb8-139">Assurez-vous que votre appareil est prêt avant d’insérer le port USB et de redémarrage.</span><span class="sxs-lookup"><span data-stu-id="f8eb8-139">Ensure that your device is ready before inserting the USB and restarting.</span></span> 

## <span data-ttu-id="f8eb8-140">Liens connexes</span><span class="sxs-lookup"><span data-stu-id="f8eb8-140">Related links</span></span>

 - [<span data-ttu-id="f8eb8-141">Outil de déploiement d’image source ouverte sur GitHub</span><span class="sxs-lookup"><span data-stu-id="f8eb8-141">Open source image deployment tool released on GitHub</span></span>](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/open-source-image-deployment-tool-released-on-github/ba-p/1314115)
 - [<span data-ttu-id="f8eb8-142">Télécharger et installer Windows ADK</span><span class="sxs-lookup"><span data-stu-id="f8eb8-142">Download and install the Windows ADK</span></span>](https://docs.microsoft.com/windows-hardware/get-started/adk-install)
