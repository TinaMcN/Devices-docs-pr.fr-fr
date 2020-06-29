---
title: SurfaceHub est susceptible d’installer des mises à jour et de redémarrer les heures de maintenance externes
description: informations de résolution des problèmes de surface Hub concernant les mises à jour automatiques
ms.assetid: 6C09A9F8-F9CF-4491-BBFB-67A1A1DED0AA
keywords: surface Hub, fenêtre de maintenance, mise à jour
ms.prod: surface-hub
ms.sitesec: library
author: Teresa-MOTIV
ms.author: v-tea
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: 117c18cfce6dfb84b4fe2156ea98198f96da2abf
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10833821"
---
# SurfaceHub est susceptible d’installer des mises à jour et de redémarrer les heures de maintenance externes

Dans des circonstances spécifiques, surface Hub installe les mises à jour pendant les heures d’activité plutôt que dans la fenêtre de maintenance normale. Le périphérique redémarre si nécessaire. Vous ne pouvez pas utiliser l’appareil tant que le processus n’est pas terminé.

> [!NOTE]  
> Ce comportement n’est pas attendu pour une fenêtre de maintenance. Ce problème se produit uniquement si le périphérique est obsolète depuis longtemps.

## Cause
Pour vous assurer que le concentrateur de surface reste disponible pendant les heures d’activité, le Hub est configuré pour effectuer des fonctions d’administration au cours d’une fenêtre de maintenance définie dans les paramètres (voir «références» ci-dessous). Pendant cette période de maintenance, le Hub installe automatiquement les mises à jour disponibles par le biais de Windows Update ou du service de mise à jour Windows Server (WSUS). Une fois les mises à jour terminées, le concentrateur risque de redémarrer.

Les mises à jour peuvent être installées dans la fenêtre de maintenance uniquement si le surface Hub est activé, mais qu’il n’est pas en cours d’utilisation ou de réservation. Par exemple, si la surface Hub est planifiée pour une réunion qui dure 24 heures, toutes les mises à jour qui doivent être installées seront différées jusqu’à ce que le concentrateur soit disponible dans la fenêtre de maintenance suivante. Si le concentrateur reste occupé et qu’il n’y a pas de fenêtres de maintenance, il finira par installer et télécharger les mises à jour. Cela peut se produire pendant ou en dehors de la fenêtre de maintenance. Une fois le téléchargement et l’installation démarrés, le périphérique peut redémarrer.

## Pour éviter ce problème

Il est important de mettre en place le temps de maintenance de surface Hub pour effectuer des fonctions d’administration. La réservation de surface Hub pour 24 heures ou l’utilisation de l’appareil pendant la période de maintenance retarde l’installation des mises à jour. Nous vous recommandons de ne pas utiliser ou réserver le concentrateur pendant la période de maintenance planifiée. Une fenêtre de deux heures doit être réservée à des fins de mise à jour.

Une option que vous pouvez utiliser pour contrôler la disponibilité des mises à jour est Windows Server Update Service (WSUS). WSUS vous permet de contrôler les mises à jour qui sont installées.

## Références 
 
[Mettre à jour le Surface Hub](first-run-program-surface-hub.md#update-the-surface-hub) 

[Fenêtre de maintenance](manage-windows-updates-for-surface-hub.md#maintenance-window) 

[Déploie les mises à jour Windows10 à l’aide de WindowsServer Update Services (WSUS)](/windows/deployment/update/waas-manage-updates-wsus) 


