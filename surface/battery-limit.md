---
title: Paramètre de limite de batterie (Surface)
description: La limite de batterie est un paramètre UEFI qui modifie la façon dont la batterie de l’appareil Surface est chargée et peut prolonger sa long terme.
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.reviewer: jesko
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
manager: laurawi
audience: itpro
ms.date: 1/15/2021
ms.openlocfilehash: 8ce1dcfc621a547aca9ca1db322f3ed2ce082728
ms.sourcegitcommit: 1b86286bd13b13749ddbf454ae78d9a24fec44ee
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "11271141"
---
# Paramètre de limite de la batterie

L’option Limite de batterie est un paramètre UEFI qui modifie la façon dont la batterie de l’appareil Surface est chargée et peut prolonger sa long terme. Ce paramètre est recommandé dans les cas où l’appareil est connecté en permanence à l’alimentation, par exemple lorsque les appareils sont intégrés aux solutions kiosque.  

## Fonctionnement de la limite de batterie

La définition de l’appareil sur la limite de batterie modifie le protocole de chargement de la batterie de l’appareil. Lorsque la limite de batterie est activée, la charge de la batterie est limitée à 50 % de sa capacité maximale. Le niveau de charge signalé dans Windows reflètera cette limite. Par conséquent, il indique que la batterie est chargée jusqu’à 50 % et qu’elle ne sera pas chargée au-delà de cette limite. Si vous activez la limite de batterie alors que la charge de l’appareil est supérieure à 50 %, l’icône Batterie indique que l’appareil est branché, mais qu’il est déconnecté jusqu’à ce qu’il atteigne 50 % de sa capacité de charge maximale.  

## Appareils pris en charge

Le paramètre UEFI de limite de batterie est intégré aux appareils Surface les plus récents, notamment Surface Pro 7+, Surface Pro 7 et Surface Laptop 3. Les appareils précédents nécessitent une mise à jour du microprogramme [UEFI Surface,](manage-surface-driver-and-firmware-updates.md)disponible via Windows Update ou via les packages de microprogramme et de pilote MSI sur le site de [support Surface.](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware-for-surface) Activez « Limite de batterie » pour les appareils Surface qui doivent être branchés pendant de [longues périodes](https://support.microsoft.com/help/4464941) pour la version UEFI Surface spécifique requise pour chaque appareil pris en charge. 

## Activation de la limite de batterie dans l’UEFI Surface (Surface Pro 4 et ultérieur)

Le paramètre de limite de batterie UEFI Surface peut être configuré en délateur dans Surface UEFI **(Power + Vol Up** lors de l’alimentation de l’appareil). Choisissez **la configuration de**démarrage, puis, sous Options **avancées,** basculez **Activer** le mode limite de batterie **sur Activé.**  

![Options avancées de limite de batterie](images/enable-bl.png) 

## Activation de la limite de batterie sur Surface Go et Surface Go 2
Le paramètre de limite de la batterie Surface peut être configuré en délateur dans l’UEFI Surface **(Power + Vol Up** lors de l’alimentation de l’appareil). Choisissez **la configuration de**démarrage, puis, en **mode**plein écran, déplacez le curseur à droite pour définir la limite de batterie **sur Activé.**  

![Limite de batterie en mode plein écran dans Surface Go](images/go-batterylimit.png) 

## Activation de la limite de batterie dans l’UEFI Surface (Surface Pro 3)

Le paramètre de limite de batterie UEFI Surface peut être configuré en délateur dans Surface UEFI **(Power + Vol Up** lors de l’alimentation de l’appareil). Choose **Kiosk Mode**, select Battery **Limit**, and then choose **Enabled**.

![Capture d’écran des options avancées](images/enable-bl-sp3.png) 

![Options avancées](images/enable-bl-sp3-2.png) 

## Activation de la limite de batterie à l’aide des scripts PowerShell du microprogramme Surface Enterprise Management Mode (SEMM) ou Surface Pro 3

La limite de batterie UEFI Surface est également disponible pour la configuration via les méthodes suivantes :

- Surface Pro 4 et les ultérieures 
    - [Configurateur UEFI Microsoft Surface](https://docs.microsoft.com/surface/surface-enterprise-management-mode)  
    - Scripts Surface UEFI Manager Powershell (SEMM_Powershell.zip) dans les [téléchargements surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703)
- Surface Pro3 
    - [SP3_Firmware_Powershell_Scripts.zip](https://www.microsoft.com/download/details.aspx?id=46703)

### Utilisation de Microsoft Surface UEFI Configurator

Pour configurer le mode limite de batterie, définissez le paramètre **Kiosk Overrides** sur la page de configuration des **paramètres** avancés dans SEMM (Surface Pro 4 et ultérieur).

![Capture d’écran des paramètres avancés](images/semm-bl.png)

### Utilisation des scripts PowerShell du Gestionnaire UEFI Surface

La fonctionnalité de limite de batterie est contrôlée via le paramètre suivant :  

`407 = Battery Profile`

**Description :** schéma de gestion actif pour le modèle d’utilisation de la batterie

**Par**défaut :  `0` 

Définissez cette limite `1` pour activer la limite de batterie.

### Utilisation des outils de microprogramme Surface Pro 3

La fonctionnalité de limite de batterie est contrôlée via le paramètre suivant :  

**Name**: BatteryLimitEnable

**Description**: BatteryLimit

**Valeur actuelle**:  `0` 

**Valeur par défaut**: `0`

**Valeur proposée**: `0` 

Définissez cette limite `1` pour activer la limite de batterie.

>[!NOTE]
>Pour configurer ce paramètre, vous devez utiliser [SP3_Firmware_Powershell_Scripts.zip](https://www.microsoft.com/download/details.aspx?id=46703). 

