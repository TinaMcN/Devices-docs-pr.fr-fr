---
title: Référence SKU du système Surface
description: Cette rubrique fournit une référence sur les noms des références SKU système que vous pouvez utiliser pour déterminer rapidement l’état de l’ordinateur d’un appareil spécifique.
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.openlocfilehash: 29cd47beb855c9b643fca42d91c7b316c374fcca
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832844"
---
# Référence SKU du système surface
Ce document fournit une référence sur les noms des références SKU système que vous pouvez utiliser pour déterminer rapidement l’état de l’ordinateur d’un appareil spécifique à l’aide de PowerShell, WMI et des outils connexes. 

La référence SKU système est une variable (en plus du modèle système et d’autres) qui est stockée dans les tables de système de gestion du système (SMBIOS) de la couche UEFI des appareils surface.  Utilisez le nom de référence système à chaque fois que vous avez besoin de faire la différence entre les appareils dotés du même nom de modèle système, tels que surface Pro et surface Pro avec LTE Advanced. 

| **Appareil**| **Modèle système** | **Référence système**|
| --- | ---| --- |
| WiFI surface 3                                               | Surface3        | Surface_3                        |
| Surface 3 LTE au&T                                           | Surface3        | Surface_3_US1                    |
| Surface 3-Verizon Verizon                                        | Surface3        | Surface_3_US2                    |
| Surface 3, Amérique du Nord                                  | Surface3        | Surface_3_NAG                    |
| Surface 3 ETL en dehors de l’Amérique du Nord et du T-mobile au Japon | Surface3        | Surface_3_ROW                    |
| SurfacePro                                                  | SurfacePro      | Surface_Pro_1796                 |
| SurfacePro avec LTE Advanced                                | SurfacePro      | Surface_Pro_1807                 |
| Surface Book 2 13inch                                        | SurfaceBook2   | Surface_Book_1832                |
| Surface Book 2 15inch                                        | SurfaceBook2   | Surface_Book_1793                |
| Client surface Go                                          | SurfaceGo       | Surface_Go_1824_Consumer         |
| Surface Go commercial                                        | SurfaceGo       | Surface_Go_1824_Commercial       |
| SurfaceGo2                                                 | SurfaceGo2     | Surface_Go_2_1927                |
| Grand public surface Pro 6                                       | SurfacePro6    | Surface_Pro_6_1796_Consumer      |
| Commercialisation de surface Pro 6                                     | SurfacePro6    | Surface_Pro_6_1796_Commercial    |
| Grand public surface Laptop 2                                    | Surface Laptop2 | Surface_Laptop_2_1769_Consumer   |
| Ordinateur portable surface 2 commercial                                  | Surface Laptop2 | Surface_Laptop_2_1769_Commercial |

## Utilisation de variables SKU système 

### PowerShell

     gwmi -namespace root\wmi -class MS_SystemInformation | select SystemSKU 

### Informations système
Vous pouvez également trouver la référence système et le modèle système pour un appareil dans les informations système. 
- Cliquez sur **Démarrer**  >   **Msinfo32**.  

### WMIC
Vous pouvez utiliser des variables SKU système dans une condition WMI de séquence de tâches dans Microsoft Deployment Toolkit (MDT) ou Microsoft Endpoint Configuration Manager. Exemple: 

    - Espace de noms WMI – Root\WMI
    - Requête WQL: sélectionnez * dans MS_SystemInformation où SystemSKU = "Surface_Pro_1796"

 
 
 


