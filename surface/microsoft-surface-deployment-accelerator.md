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
# Microsoft Surface Deployment Accelerator

Microsoft surface Deployment Accelerator (SDA) automatise la création et la configuration d’une interface de déploiement recommandée par Microsoft en utilisant des outils de déploiement gratuits de Microsoft.

Repensée en avril 2020 pour simplifier et automatiser le déploiement d’images surface dans un environnement d’entreprise, l’outil SDA vous permet de générer une image Windows de type usine que vous pouvez personnaliser selon les besoins de votre organisation.

L’outil SDA Open source, qui est piloté par un script exploite le kit de déploiement d’évaluation et de déploiement Windows (ADK) pour Windows 10, facilitant la création d’images Windows (WIM) dans les environnements de test ou de production. Si le dernier logiciel ADK n’est pas déjà installé, il sera téléchargé et installé lors de l’exécution de l’outil SDA.

L’image obtenue correspond étroitement à la configuration des images de récupération d’urgence, sans aucune application préinstallée telle que Microsoft Office ou l’application UWP surface.

**Pour exécuter SDA:**

1. Accédez à [SurfaceDeploymentAccelerator](https://github.com/microsoft/SurfaceDeploymentAccelerator) sur GitHub. 
2. Sélectionnez **Clone ou télécharger** et examinez le fichier Lisez-moi.
3. Modifiez le script avec les variables appropriées pour votre environnement, comme indiqué dans le fichier Lisez-moi et examinez-le avant de l’exécuter dans votre environnement de test. 

   ![Outil accélérateur de déploiement de surface exécuté](images/surface-deployment-accelerator.png)

## Liens connexes

 - [Outil de déploiement d’image source ouverte sur GitHub](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/open-source-image-deployment-tool-released-on-github/ba-p/1314115)

 - [Télécharger et installer Windows ADK](https://docs.microsoft.com/windows-hardware/get-started/adk-install)
