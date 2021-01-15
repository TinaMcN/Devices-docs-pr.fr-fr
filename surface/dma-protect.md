---
title: Protection d’accès direct à la mémoire (DMA) surface
description: Cet article décrit la protection DMA sur les appareils Surface compatibles
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 1/14/2021
ms.reviewer: carlol
manager: laurawi
audience: itpro
appliesto:
- Surface Pro 7+
- Surface Pro 7
- Surface Laptop 3
- Surface Pro X
ms.openlocfilehash: af5187a2b110804a2dff82291f1d5f912ac61a7b
ms.sourcegitcommit: d4e2a29aa21a911ee55642cd66b4337b89eebdd8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/14/2021
ms.locfileid: "11270619"
---
# <span data-ttu-id="c0675-103">Protection DMA sur les appareils Surface</span><span class="sxs-lookup"><span data-stu-id="c0675-103">DMA Protection on Surface devices</span></span>

<span data-ttu-id="c0675-104">La protection DMA (Direct Memory Access) est conçue pour atténuer les vulnérabilités de sécurité potentielles associées à l’utilisation de SSD amovibles ou de périphériques de stockage externes.</span><span class="sxs-lookup"><span data-stu-id="c0675-104">Direct Memory Access (DMA) protection is designed to mitigate potential security vulnerabilities associated with using removable SSDs or external storage devices.</span></span> <span data-ttu-id="c0675-105">Les appareils Surface plus nouveaux sont fourni avec la protection DMA activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="c0675-105">Newer Surface devices come with DMA Protection enabled by default.</span></span> <span data-ttu-id="c0675-106">Il s’agit notamment de Surface Pro 7+.</span><span class="sxs-lookup"><span data-stu-id="c0675-106">These include Surface Pro 7+.</span></span> <span data-ttu-id="c0675-107">Surface Pro 7, Surface Laptop 3 et Surface Pro X.  Pour vérifier la présence de la fonctionnalité de protection DMA sur votre appareil, ouvrez Informations système **(** Démarrermsinfo32.exe), comme illustré dans la figure  >  \*\* \*\*ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="c0675-107">Surface Pro 7, Surface Laptop 3, and Surface Pro X.  To check the presence of DMA protection feature on your device, open System Information (**Start** > **msinfo32.exe**), as shown in the figure below.</span></span>

![Informations système indiquant que la protection DMA est activée](images/systeminfodma.png)

<span data-ttu-id="c0675-109">Si un SSD amovible Surface est falsifié, l’appareil arrête l’alimentation.</span><span class="sxs-lookup"><span data-stu-id="c0675-109">If a Surface removable SSD is tampered with, the device will shutoff power.</span></span> <span data-ttu-id="c0675-110">Le redémarrage qui en résulte entraîne l’effacement de la mémoire par l’UEFI, afin d’effacer les données inttérables.</span><span class="sxs-lookup"><span data-stu-id="c0675-110">The resulting reboot causes UEFI to wipe memory, to erase any residual data.</span></span>
