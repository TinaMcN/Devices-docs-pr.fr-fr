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
# Protection DMA sur les appareils surface

La protection de l’accès direct à la mémoire (DMA) est conçue pour limiter les failles de sécurité potentielles associées à l’utilisation de périphériques amovibles ou de stockage externes amovibles. Par défaut, la protection par DMA est activée sur les appareils surface plus récents. Il s’agit notamment de surface Pro 7, de surface Laptop 3 et de surface Pro X.  Pour vérifier la présence de la fonctionnalité de protection de DMA sur votre appareil, ouvrez informations système (**Démarrez**  >  **msinfo32.exe**), comme illustré dans la figure ci-dessous.

![Informations système indiquant la protection de DMA activée](images/systeminfodma.png)

S’il s’agit d’une falsification de surface amovible, l’appareil s’allume. Le redémarrage obtenu entraîne la réinitialisation de la mémoire par UEFI pour effacer les données résiduelles.
