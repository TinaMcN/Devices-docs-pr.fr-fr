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
ms.openlocfilehash: 32d8fded8c325766f7ab6bbc750ba7fe13e01d70
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832310"
---
# <span data-ttu-id="c929d-104">Microsoft Surface Deployment Accelerator</span><span class="sxs-lookup"><span data-stu-id="c929d-104">Microsoft Surface Deployment Accelerator</span></span>

<span data-ttu-id="c929d-105">Microsoft surface Deployment Accelerator (SDA) automatise la création et la configuration d’une interface de déploiement recommandée par Microsoft en utilisant des outils de déploiement gratuits de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c929d-105">Microsoft Surface Deployment Accelerator (SDA) automates the creation and configuration of a Microsoft recommended deployment experience by using free Microsoft deployment tools.</span></span>

<span data-ttu-id="c929d-106">Repensée en avril 2020 pour simplifier et automatiser le déploiement d’images surface dans un environnement d’entreprise, l’outil SDA vous permet de générer une image Windows de type usine que vous pouvez personnaliser selon les besoins de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="c929d-106">Redesigned in April 2020 to simplify and automate deployment of Surface images in a corporate environment, the SDA tool allows you to build a “factory-like” Windows image that you can customize to your organizational requirements.</span></span>

<span data-ttu-id="c929d-107">L’outil SDA Open source, qui est piloté par un script exploite le kit de déploiement d’évaluation et de déploiement Windows (ADK) pour Windows 10, facilitant la création d’images Windows (WIM) dans les environnements de test ou de production.</span><span class="sxs-lookup"><span data-stu-id="c929d-107">The open source, script-driven SDA tool leverages the Windows Assessment and Deployment Kit (ADK) for Windows 10, facilitating the creation of Windows images (WIM) in test or production environments.</span></span> <span data-ttu-id="c929d-108">Si le dernier logiciel ADK n’est pas déjà installé, il sera téléchargé et installé lors de l’exécution de l’outil SDA.</span><span class="sxs-lookup"><span data-stu-id="c929d-108">If the latest ADK is not already installed, it will be downloaded and installed when running the SDA tool.</span></span>

<span data-ttu-id="c929d-109">L’image obtenue correspond étroitement à la configuration des images de récupération d’urgence, sans aucune application préinstallée telle que Microsoft Office ou l’application UWP surface.</span><span class="sxs-lookup"><span data-stu-id="c929d-109">The resulting image closely matches the configuration of Bare Metal Recovery (BMR) images, without any pre-installed applications such as Microsoft Office or the Surface UWP application.</span></span>

**<span data-ttu-id="c929d-110">Pour exécuter SDA:</span><span class="sxs-lookup"><span data-stu-id="c929d-110">To run SDA:</span></span>**

1. <span data-ttu-id="c929d-111">Accédez à [SurfaceDeploymentAccelerator](https://github.com/microsoft/SurfaceDeploymentAccelerator) sur GitHub.</span><span class="sxs-lookup"><span data-stu-id="c929d-111">Go to [SurfaceDeploymentAccelerator](https://github.com/microsoft/SurfaceDeploymentAccelerator) on GitHub.</span></span> 
2. <span data-ttu-id="c929d-112">Sélectionnez **Clone ou télécharger** et examinez le fichier Lisez-moi.</span><span class="sxs-lookup"><span data-stu-id="c929d-112">Select **Clone or Download** and review the Readme file.</span></span>
3. <span data-ttu-id="c929d-113">Modifiez le script avec les variables appropriées pour votre environnement, comme indiqué dans le fichier Lisez-moi et examinez-le avant de l’exécuter dans votre environnement de test.</span><span class="sxs-lookup"><span data-stu-id="c929d-113">Edit the script with the appropriate variables for your environment, as documented in the Readme, and review before running it in your test environment.</span></span> 

   ![Outil accélérateur de déploiement de surface exécuté](images/surface-deployment-accelerator.png)

## <span data-ttu-id="c929d-115">Liens connexes</span><span class="sxs-lookup"><span data-stu-id="c929d-115">Related links</span></span>

 - [<span data-ttu-id="c929d-116">Outil de déploiement d’image source ouverte sur GitHub</span><span class="sxs-lookup"><span data-stu-id="c929d-116">Open source image deployment tool released on GitHub</span></span>](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/open-source-image-deployment-tool-released-on-github/ba-p/1314115)

 - [<span data-ttu-id="c929d-117">Télécharger et installer Windows ADK</span><span class="sxs-lookup"><span data-stu-id="c929d-117">Download and install the Windows ADK</span></span>](https://docs.microsoft.com/windows-hardware/get-started/adk-install)
