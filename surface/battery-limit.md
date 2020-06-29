---
title: Paramètre de limite de batterie (surface)
description: La limite de batterie est un paramètre UEFI qui modifie le mode de charge de la batterie de l’appareil surface et peut prolonger sa longévité.
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
ms.date: 5/06/2020
ms.openlocfilehash: 927f00681bd5756f380025adf00a08a34a3f411f
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10833509"
---
# Paramètre de limite de la batterie

L’option de limite de batterie est un paramètre UEFI qui modifie le mode de charge de la batterie de l’appareil surface et peut prolonger sa longévité. Ce paramètre est recommandé dans les cas où l’appareil est continuellement connecté à la puissance, par exemple lorsque les appareils sont intégrés dans les solutions Kiosk.  

## Fonctionnement de la limitation de batterie

La configuration de l’appareil sur la limite des batteries a pour changement le protocole pour la charge de la batterie de l’appareil. Lorsque la limite de batterie est activée, le coût de la batterie est limité à 50% de la capacité maximale. Le niveau de charge signalé dans Windows reflétera cette limite. Par conséquent, la batterie sera débitée de 50% et ne sera pas facturée au-delà de cette limite. Si vous activez le nombre maximal de batteries alors que l’appareil est supérieur à 50%, l’icône de batterie indique que l’appareil est branché, mais qu’il est en cours de rejet jusqu’à 50% de la capacité de chargement maximale.  

## Appareils pris en charge
Le paramètre UEFI de limitation de batterie est intégré aux périphériques de surface les plus récents, y compris surface Pro 7 et surface Laptop 3. Les appareils antérieurs nécessitent une [mise à jour de microprogramme de surface UEFI](manage-surface-driver-and-firmware-updates.md), disponible via Windows Update ou via le pilote msi et des packages de microprogramme sur le [site de support surface](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware-for-surface). Cochez la case [activer le «plafond de batterie» pour les appareils surface qui doivent être branchés pour des périodes de temps longues](https://support.microsoft.com/help/4464941) pour la version UEFI de surface spécifique requise pour chaque appareil pris en charge. 

## Activation de la limite de batterie dans surface UEFI (surface Pro 4 et versions ultérieures)

Ce paramètre peut être configuré en démarrant en surface UEFI (**Power + vol haut** lors de l’activation de l’appareil). Sélectionnez **configuration de démarrage**, puis, sous **Options avancées**, **activez activer le mode de limite de batterie** sur **activé**.  

![Capture d’écran des options avancées](images/enable-bl.png) 

## Activation de la limitation de batteries dans surface Go et surface Go 2
Le paramètre de limite de batterie de surface peut être configuré en démarrant en surface UEFI (**Power + vol vers le haut** lors de l’activation de l’appareil). Sélectionnez **configuration de démarrage**, puis, sous **mode kiosque**, déplacez le curseur vers la droite pour définir le seuil de batterie sur **activé**.  

![Capture d’écran de la limite de batterie du mode kiosque dans surface Go](images/go-batterylimit.png) 

## Activation de la limite de batterie dans surface UEFI (surface Pro 3)

Ce paramètre peut être configuré en démarrant en surface UEFI (**Power + vol haut** lors de l’activation de l’appareil). Cliquez sur **mode plein écran**, sélectionnez **limite de batterie**, puis **activé**.

![Capture d’écran des options avancées](images/enable-bl-sp3.png) 

![Capture d’écran des options avancées](images/enable-bl-sp3-2.png) 

## Activation d’une limite de batterie à l’aide de scripts PowerShell du microprogramme de surface Management SEMM (surface Management Mode) ou de surface Pro 3

Le seuil de batterie de surface UEFI peut également être configuré via les méthodes suivantes:

- Surface Pro 4 et version ultérieure 
    - [Configurateur Microsoft surface UEFI](https://docs.microsoft.com/surface/surface-enterprise-management-mode)  
    - Scripts PowerShell de surface UEFI Manager (SEMM_Powershell.zip) dans les [Outils surface pour le téléchargement](https://www.microsoft.com/download/details.aspx?id=46703)
- Surface Pro3 
    - [SP3_Firmware_Powershell_Scripts.zip](https://www.microsoft.com/download/details.aspx?id=46703)

### Utilisation du configurateur Microsoft surface UEFI

Pour configurer le mode de limitation de batterie, définissez le paramètre **Kiosk Overrides** sur la page configuration **avancée des paramètres** dans SEMM (surface Pro 4 et versions ultérieures).

![Capture d’écran des paramètres avancés](images/semm-bl.png)

### Utilisation de scripts PowerShell de surface UEFI Manager

La fonctionnalité de limite de batterie est contrôlée via le paramètre suivant:  

`407 = Battery Profile`

**Description**: schéma de gestion actif pour le modèle d’utilisation de la batterie

**Par défaut**:  `0` 

Définissez cette valeur sur `1` pour activer le nombre maximal de batteries.

### Utilisation des outils de microprogramme de surface Pro 3

La fonctionnalité de limite de batterie est contrôlée via le paramètre suivant:  

**Nom**: BatteryLimitEnable

**Description**: BatteryLimit

**Valeur actuelle**:  `0` 

**Valeur par défaut**: `0`

**Valeur proposée**: `0` 

Définissez cette valeur sur `1` pour activer le nombre maximal de batteries.

>[!NOTE]
>Pour configurer ce paramètre, vous devez utiliser [SP3_Firmware_Powershell_Scripts.zip](https://www.microsoft.com/download/details.aspx?id=46703). 

