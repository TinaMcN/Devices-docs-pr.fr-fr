---
title: Référence SKU système (surface)
description: Voir une référence pour les noms de modèle système et de référence système.
keywords: UEFI, configurer, microprogramme, sécurité SEMM
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices, security
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 03/09/2020
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: 1fa192902b17ca811d4ecc8eac65abe1655ce370
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10833191"
---
# Référence SKU système

Ce document fournit une référence sur le modèle système et les noms de référence système que vous pouvez utiliser pour déterminer rapidement l’état de la machine d’un appareil spécifique à l’aide de PowerShell ou WMI.

Les variables de modèle système et de référence système sont des variables qui sont stockées dans des tables SMBIOS (System Management BIOS) dans la couche UEFI des appareils surface. Le nom de référence système est requis pour différencier les appareils qui ont le même nom de modèle système, par exemple surface Pro et surface Pro avec LTE Advanced. 

| Appareil   | Modèle système | Référence système       |
| ---------- | ----------- | -------------- |
| WiFI surface 3                                               | Surface3        | Surface_3                        |
| Surface 3 LTE au&T                                           | Surface3        | Surface_3_US1                    |
| Surface 3-Verizon Verizon                                        | Surface3        | Surface_3_US2                    |
| Surface 3, Amérique du Nord                                  | Surface3        | Surface_3_NAG                    |
| Surface 3 ETL en dehors de l’Amérique du Nord et Y! mobiles au Japon | Surface3        | Surface_3_ROW                    |
| SurfacePro                                                  | SurfacePro      | Surface_Pro_1796                 |
| SurfacePro avec LTE Advanced                                | SurfacePro      | Surface_Pro_1807                 |
| Surface Book 2 13 "                                        | SurfaceBook2   | Surface_Book_1832                |
| Surface Book 2 15 "                                        | SurfaceBook2   | Surface_Book_1793                |
| Client surface Go LTE  | SurfaceGo | Surface_Go_1825_Consumer |
| Surface Go pour le Midmarket | Système Go | Surface_Go_1825_Commercial |
| Client surface Go                                          | SurfaceGo       | Surface_Go_1824_Consumer         |
| Surface Go commercial                                        | SurfaceGo       | Surface_Go_1824_Commercial       |
| Grand public surface Pro 6                                       | SurfacePro6    | Surface_Pro_6_1796_Consumer      |
| Commercialisation de surface Pro 6                                     | SurfacePro6    | Surface_Pro_6_1796_Commercial    |
| Surface Laptop                                               | Surface Laptop   | Surface_Laptop                   |
| Grand public surface Laptop 2                                    | Surface Laptop2 | Surface_Laptop_2_1769_Consumer   |
| Ordinateur portable surface 2 commercial                                  | Surface Laptop2 | Surface_Laptop_2_1769_Commercial |
| SurfacePro7                 | SurfacePro7    | Surface_Pro_7_1866         |
| SurfaceProX                 | SurfaceProX    | Surface_Pro_X_1876         |
| Surface Laptop 3 13 "Intel | Surface Laptop3 | Surface_Laptop_3_1867:1868 |
| Surface Laptop 3 15 "Intel | Surface Laptop3 | Surface_Laptop_3_1872      |
| Ordinateur portable surface 3 15 "AMD   | Surface Laptop3 | Surface_Laptop_3_1873      | 

## Exemples 

**Récupération de la référence (SKU) à l’aide de PowerShell**  
Pour récupérer les informations de référence système, utilisez la commande PowerShell suivante:

 ``` powershell  
gwmi -namespace root\wmi -class MS_SystemInformation | select SystemSKU 
```

**Récupération de la référence (SKU) à l’aide des informations système**  
Vous pouvez également trouver la référence système et le modèle système pour un appareil dans les **informations système**. Pour cela, procédez comme suit:

1. Sélectionnez **Démarrer**, puis tapez **Msinfo32** dans la zone de recherche.  
1. Cliquez **sur informations système**.

**Utilisation de la référence SKU dans une condition WMI de séquence de tâches**  
Vous pouvez utiliser les informations relatives à la référence système dans Microsoft Deployment Toolkit (MDT) ou Microsoft Endpoint Configuration Manager dans le cadre d’une condition WMI de séquence de tâches.

 ``` powershell  
    - WMI Namespace – Root\WMI
    - WQL Query – SELECT * FROM MS_SystemInformation WHERE SystemSKU = "Surface_Pro_1796"
 ``` 
