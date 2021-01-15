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
# Protection DMA sur les appareils Surface

La protection DMA (Direct Memory Access) est conçue pour atténuer les vulnérabilités de sécurité potentielles associées à l’utilisation de SSD amovibles ou de périphériques de stockage externes. Les appareils Surface plus nouveaux sont fourni avec la protection DMA activée par défaut. Il s’agit notamment de Surface Pro 7+. Surface Pro 7, Surface Laptop 3 et Surface Pro X.  Pour vérifier la présence de la fonctionnalité de protection DMA sur votre appareil, ouvrez Informations système **(** Démarrermsinfo32.exe), comme illustré dans la figure  >  ** **ci-dessous.

![Informations système indiquant que la protection DMA est activée](images/systeminfodma.png)

Si un SSD amovible Surface est falsifié, l’appareil arrête l’alimentation. Le redémarrage qui en résulte entraîne l’effacement de la mémoire par l’UEFI, afin d’effacer les données inttérables.
