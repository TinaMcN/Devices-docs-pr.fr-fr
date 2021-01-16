---
title: Référence SKU système (Surface)
description: Voir une référence aux noms de modèle système et de référence du système.
keywords: uefi, configurer, microprogramme, sécurisé, semm
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices, security
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 1/15/2021
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: 2140faf346229842bffc4f9348041f4667b94686
ms.sourcegitcommit: 1053479c191fd10651d31a466fad1769fb0cd28b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/16/2021
ms.locfileid: "11271368"
---
# Référence SKU système

Ce document fournit une référence aux noms de modèle système et de référence système que vous pouvez utiliser pour déterminer rapidement l’état de l’ordinateur d’un appareil spécifique à l’aide de PowerShell ou WMI.

Le modèle système et la référence SKU système sont des variables stockées dans les tables SMBIOS (System Management BIOS) de la couche UEFI des appareils Surface. Utilisez le nom de la référence système chaque fois que vous devez différencier les appareils du même nom de modèle système, tels que Surface Pro et Surface Pro avec LTE Advanced.

| Appareil   | Modèle système | Référence (SKU) système       |
| ---------- | ----------- | -------------- |
| Surface 3 WiFI                                               | Surface3        | Surface_3                        |
| Surface 3 LTE AT&T                                           | Surface3        | Surface_3_US1                    |
| Surface 3 LTE Verizon                                        | Surface3        | Surface_3_US2                    |
| Surface 3 LTE Amérique du Nord                                  | Surface3        | Surface_3_NAG                    |
| Surface 3 LTE en dehors de l’Amérique du Nord et Y!mobile au Japon | Surface3        | Surface_3_ROW                    |
| SurfacePro                                                  | SurfacePro      | Surface_Pro_1796                 |
| SurfacePro avec LTE Advanced                                | SurfacePro      | Surface_Pro_1807                 |
| Surface Book 2 13»                                        | SurfaceBook2   | Surface_Book_1832                |
| Surface Book 2 15»                                        | SurfaceBook2   | Surface_Book_1793                |
| Surface Book 3 13»                                        | SurfaceBook3   | Surface_Book_3_1900                |
| Surface Book 3 15»                                        | SurfaceBook3   | Surface_Book_3_1899
| Surface Go LTE Commercial | System Go | Surface_Go_1825_Commercial |
| Surface Go Consumer                                          | SurfaceGo       | Surface_Go_1824_Consumer         |
| Surface Go Commercial                                        | SurfaceGo       | Surface_Go_1824_Commercial       |
| SurfaceGo2                                                 | SurfaceGo2     | Surface_Go_2_1927                |
| Surface Pro 6 Consumer                                       | SurfacePro6    | Surface_Pro_6_1796_Consumer      |
| Surface Pro 6 Commercial                                     | SurfacePro6    | Surface_Pro_6_1796_Commercial    |
| Surface Laptop                                               | Surface Laptop   | Surface_Laptop                   |
| Surface Laptop 2 Consumer                                    | Surface Laptop2 | Surface_Laptop_2_1769_Consumer   |
| Surface Laptop 2 Commercial                                  | Surface Laptop2 | Surface_Laptop_2_1769_Commercial |
| Surface Pro 7+                                               | Surface Pro 7+ | Surface_Pro_7+_1960|
| Surface Pro 7+ LTE                                           | Surface Pro 7+ | Surface_Pro_7+_with_LTE_Advanced_1961|
| SurfacePro7                 | SurfacePro7    | Surface_Pro_7_1866         |
| SurfaceProX                 | SurfaceProX    | Surface_Pro_X_1876         |
| Surface Pro X avec processeur SQ2                | SurfaceProX    | Surface_Pro_X_H_1876        |
| Surface Laptop 3 13 pouces Intel | Surface Laptop3 | Surface_Laptop_3_1867:1868 |
| Surface Laptop 3 15 pouces Intel | Surface Laptop3 | Surface_Laptop_3_1872      |
| Surface Laptop 3 15 pouces AMD   | Surface Laptop3 | Surface_Laptop_3_1873      | 
| Surface Laptop Go  | Surface Laptop Go | Surface_Laptop_Go_1943      | 

## Exemples 

**Récupération de la référence (SKU) à l’aide de PowerShell**  
Utilisez la commande PowerShell suivante pour obtenir les informations de référence système :

 ``` powershell  
gwmi -namespace root\wmi -class MS_SystemInformation | select SystemSKU 
```

**Récupération de la référence (SKU) à l’aide des informations système**  
Vous pouvez également trouver la référence système et le modèle système d’un appareil dans **Les informations système.** Pour ce faire, procédez comme suit:

1. **Sélectionnez**Démarrer, puis **tapez MSInfo32** dans la zone de recherche.  
1. Sélectionnez **Informations système.**

**Utilisation de la référence (SKU) dans une condition WMI de séquence de tâches**  
Vous pouvez utiliser les informations de référence système dans microsoft Deployment Shared Computer Toolkit (MDT) ou Microsoft Endpoint Configuration Manager dans le cadre d’une condition WMI de séquence de tâches.

 ``` powershell  
    - WMI Namespace – Root\WMI
    - WQL Query – SELECT * FROM MS_SystemInformation WHERE SystemSKU = "Surface_Pro_1796"
 ``` 
