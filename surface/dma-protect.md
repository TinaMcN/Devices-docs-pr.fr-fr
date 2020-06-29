---
title: Protection de surface DMA
description: Cet article décrit la protection DMA sur les appareils surface compatibles.
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 6/10/2020
ms.reviewer: carlol
manager: laurawi
audience: itpro
ms.openlocfilehash: 00994263cd61086ab86996920543a717a63d5078
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832849"
---
# <span data-ttu-id="3e2e8-103">Protection DMA sur les appareils surface</span><span class="sxs-lookup"><span data-stu-id="3e2e8-103">DMA Protection on Surface devices</span></span>

<span data-ttu-id="3e2e8-104">La protection de l’accès direct à la mémoire (DMA) est conçue pour limiter les failles de sécurité potentielles associées à l’utilisation de périphériques amovibles ou de stockage externes amovibles.</span><span class="sxs-lookup"><span data-stu-id="3e2e8-104">Direct Memory Access (DMA) protection is designed to mitigate potential security vulnerabilities associated with using removable SSDs or external storage devices.</span></span> <span data-ttu-id="3e2e8-105">Par défaut, la protection par DMA est activée sur les appareils surface plus récents.</span><span class="sxs-lookup"><span data-stu-id="3e2e8-105">Newer Surface devices come with DMA Protection enabled by default.</span></span> <span data-ttu-id="3e2e8-106">Il s’agit notamment de surface Pro 7, de surface Laptop 3 et de surface Pro X.  Pour vérifier la présence de la fonctionnalité de protection de DMA sur votre appareil, ouvrez informations système (**Démarrez**  >  **msinfo32.exe**), comme illustré dans la figure ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="3e2e8-106">These include Surface Pro 7, Surface Laptop 3, and Surface Pro X.  To check the presence of DMA protection feature on your device, open System Information (**Start** > **msinfo32.exe**), as shown in the figure below.</span></span>

![Informations système indiquant la protection de DMA activée](images/systeminfodma.png)

<span data-ttu-id="3e2e8-108">S’il s’agit d’une falsification de surface amovible, l’appareil s’allume.</span><span class="sxs-lookup"><span data-stu-id="3e2e8-108">If a Surface removable SSD is tampered with, the device will shutoff power.</span></span> <span data-ttu-id="3e2e8-109">Le redémarrage obtenu entraîne la réinitialisation de la mémoire par UEFI pour effacer les données résiduelles.</span><span class="sxs-lookup"><span data-stu-id="3e2e8-109">The resulting reboot causes UEFI to wipe memory, to erase any residual data.</span></span>
