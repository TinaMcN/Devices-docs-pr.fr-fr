---
title: Wake On LAN pour les appareils Surface (Surface)
description: Découvrez comment utiliser Wake On LAN pour faire s’activer à distance les appareils pour effectuer des tâches de gestion ou de maintenance, ou pour activer les solutions de gestion automatiquement, même si les appareils sont sous tension.
keywords: mettre à jour, déployer, pilote, wake-on-lan
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
ms.localizationpriority: medium
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: scottmca
manager: laurawi
ms.audience: itpro
ms.date: 1/15/2021
ms.openlocfilehash: 709286cc0d62bd0b4c1e28e7626529fc4a215ae2
ms.sourcegitcommit: 1b86286bd13b13749ddbf454ae78d9a24fec44ee
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "11271121"
---
# Wake On LAN pour les appareils Surface

Les appareils Surface qui exécutent Windows 10, version 1607 (également appelée Mise à jour anniversaire Windows 10) ou version ultérieure et utilisent un adaptateur Ethernet Surface pour se connecter à un réseau câblé, sont capables d’être mis à jour à l’aide d’un réseau local de veille connectée à partir de la veille connectée. Grâce à LASO, vous pouvez faire s’activer à distance les appareils pour effectuer des tâches de gestion ou de maintenance, ou activer automatiquement des solutions de gestion (telles que Microsoft Endpoint Configuration Manager). Par exemple, vous pouvez déployer des applications sur des appareils Surface ancres à gauche avec une station d’accueil Surface Pro 3 ou une station d’accueil Surface Pro 3 à l’aide de Microsoft Endpoint Configuration Manager pendant une fenêtre au milieu de la nuit, lorsque le bureau est vide.

>[!NOTE]
>Les appareils Surface doivent être connectés à l’alimentation ac et en veille connectée (veille connectée) pour prendre en charge la prise en charge de LASO. La mise en veille prolongée ou la mise hors tension de l’appareil n’est pas possible pour les appareils en veille prolongée.

## Appareils pris en charge

Les appareils suivants sont pris en charge pour LASO :

* Adaptateur Ethernet Surface
* Surface USB-C vers Ethernet et adaptateur USB
* Station d’accueilSurface
* Station d’accueil Surface pour Surface Pro 3
* Surface3
* Surface Pro3
* Surface Pro4
* Surface Pro (5e génération)
* Surface Pro (5e génération) avec LTE Advanced
* SurfaceBook
* Surface Laptop (1re génération)
* SurfacePro6
* SurfaceBook2
* Surface Laptop2
* SurfaceGo
* SurfaceGo avec LTE Advanced
* Surface Studio 2 (voir les instructions de Surface Studio 2 ci-dessous)
* SurfacePro7
* Surface Laptop3
* Surface Laptop Go
* Surface Pro 7+

## Pilote DNS

Pour activer la prise en charge DELS sur les appareils Surface, un pilote spécifique pour l’adaptateur Ethernet Surface est requis. Ce pilote n’est pas inclus dans le pack de microprogramme et de pilote standard pour les appareils Surface : vous devez le télécharger et l’installer séparément. Vous pouvez télécharger le pilote SURFACE SurfaceWOL.msi à partir de la page [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) du Centre de téléchargement Microsoft.

Vous pouvez exécuter ce fichier Microsoft Windows Installer (.msi) sur un appareil Surface pour installer le pilote SURFACE PDF ou le distribuer aux appareils Surface avec une solution de déploiement d’application, telle que Microsoft Endpoint Configuration Manager. Pour inclure le pilote SURFACE AU COURS du déploiement, vous pouvez installer le fichier .msi en tant qu’application pendant le processus de déploiement. Vous pouvez également extraire les fichiers de pilotes SURFACE EXTRACT pour les inclure dans le processus de déploiement. Par exemple, vous pouvez les inclure dans votre partage de déploiement Microsoft Deployment Shared Computer Toolkit (MDT). Vous pouvez en savoir plus sur le déploiement de Surface avec MDT dans [Déployer Windows 10](https://technet.microsoft.com/itpro/surface/deploy-windows-10-to-surface-devices-with-mdt)sur des appareils Surface avec Microsoft Deployment Shared Computer Toolkit .

> [!NOTE]
> Lors de l’installation de SurfaceWOL.msi, la clé de Registre suivante est définie sur la valeur 1, ce qui permet d’identifier facilement les systèmes sur lesquels le pilote TOL a été installé. Si vous avez choisi d’extraire et d’installer ces pilotes séparément lors du déploiement, cette clé de Registre ne sera pas configurée et doit être configurée manuellement ou avec un script.
> 
> **HKLM\SYSTEM\CurrentControlSet\Control\Power AllowSystemRequiredPowerRequests** 

Pour extraire le contenu de SurfaceWOL.msi, utilisez l’option d’installation administrative MSIExec (**/a**), comme illustré dans l’exemple suivant, pour extraire le contenu dans le dossier C:\EXTRACT\ :

   `msiexec /a surfacewol.msi targetdir=C:\WOL /qn`

## Instructions de Surface Studio 2

Pour activer LASO sur Surface Studio 2, vous devez utiliser la procédure suivante :

1. Créez les clés de Registre suivantes :

   ```console
   ; Set CONNECTIVITYINSTANDBY to 1:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power\PowerSettings\F15576E8-98B7-4186-B944-EAFA664402D9]
   "Attributes"=dword:00000001
   ; Set EnforceDisconnectedStandby to 0 and AllowSystemRequiredPowerRequests to 1:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power]
   "EnforceDisconnectedStandby"=dword:00000000
   "AllowSystemRequiredPowerRequests"=dword:00000001
   ```

2. Exécutez la commande suivante

    ```powercfg /SETACVALUEINDEX SCHEME_BALANCED SUB_NONE CONNECTIVITYINSTANDBY 1```

## Utilisation de surface SURFACE

Le pilote SURFACE COMMUT est conforme à la norme COMMUT, selon laquelle l’appareil est paré par une communication réseau spéciale appelée paquet de magie. Le paquet magique se compose de 6 octets de 255 (ou FF en hexadécimal) suivi de 16 répétitions de l’adresse MAC de l’ordinateur cible. Vous pouvez en savoir plus sur le paquet de magie et la norme WIKIPEDIA sur [Wikipedia](https://wikipedia.org/wiki/Wake-on-LAN#Magic_packet).

>[!NOTE]
>Pour envoyer un paquet de magie et faire s’agiter d’un appareil à l’aide de LASO, vous devez connaître l’adresse MAC de l’appareil cible et de l’adaptateur Ethernet. Étant donné que le paquet magique n’utilise pas le protocole réseau IP, il n’est pas possible d’utiliser l’adresse IP ou le nom DNS de l’appareil.

De nombreuses solutions de gestion, telles que Configuration Manager, offrent une prise en charge intégrée de LASO. Il existe également de nombreuses solutions, notamment des applications du Microsoft Store, des modules PowerShell, des applications tierces et des solutions de gestion tierces qui vous permettent d’envoyer un paquet magique pour l’alimentation d’un appareil. Par exemple, vous pouvez utiliser le [module PowerShell Wake On LAN](https://gallery.technet.microsoft.com/scriptcenter/Wake-On-Lan-815424c4) à partir du Centre de scripts TechNet. 

>[!NOTE]
>Une fois qu’un appareil a été mis en veille avec un paquet magique, il revient en veille si une application n’empêche pas activement la mise en veille sur le système ou si la clé de Registre AllowSystemRequiredPowerRequests n’est pas configurée sur 1, ce qui permet aux applications d’empêcher la mise en veille. Pour plus [d’informations](#wol-driver) sur cette clé de Registre, consultez la section pilote DUTL de cet article.
