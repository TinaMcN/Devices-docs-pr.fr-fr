---
title: Wake on LAN pour les appareils surface (surface)
description: Découvrez comment utiliser la fonctionnalité Wake on LAN pour réactiver à distance des appareils afin d’effectuer des tâches de gestion ou de maintenance, ou pour activer les solutions de gestion automatiquement, même si les appareils sont mis à niveau.
keywords: mise à jour, déploiement, pilote, WOL, Wake-on-LAN
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
ms.openlocfilehash: a56f6e01a4d7bf1cc40d73f34c3abf8e04443989
ms.sourcegitcommit: c1efb75e8524193bdc0a5f7496dc23a92ac665c8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/12/2020
ms.locfileid: "11114612"
---
# Wake On LAN pour les appareils Surface

Les appareils surface qui exécutent Windows 10, version 1607 (également connu sous le nom de mise à jour anniversaire Windows 10) ou version ultérieure, et utilisent une carte Ethernet surface pour se connecter à un réseau câblé, peuvent utiliser la fonction Wake on LAN (WOL) de la veille connectée. Avec WOL, vous pouvez réactiver les appareils à distance pour effectuer des tâches de gestion ou de maintenance, ou activer des solutions de gestion (comme Microsoft Endpoint Configuration Manager) automatiquement. Par exemple, vous pouvez déployer des applications sur des appareils de surface à l’aide d’une station d’ancrage de surface d’amarrage ou de surface Pro 3 à l’aide du gestionnaire de configuration de points de terminaison Microsoft pendant une fenêtre au milieu de la nuit, lorsque le bureau est vide.

>[!NOTE]
>Les appareils surface doivent être connectés à une alimentation CA et en veille connectée pour prendre en charge WOL. WOL ne peut pas être utilisé avec des appareils qui sont en veille ou qui sont éteints.

## Appareils pris en charge

Les appareils suivants sont pris en charge pour WOL:

* Carte Ethernet surface
* Surface USB-C vers Ethernet et adaptateur USB
* Station d’accueilSurface
* Station d’ancrage surface pour surface Pro 3
* Surface3
* Surface Pro3
* Surface Pro4
* Surface Pro (5e génération)
* Surface Pro (5e génération) avec LTE Advanced
* SurfaceBook
* Surface Laptop (1ère génération)
* SurfacePro6
* SurfaceBook2
* Surface Laptop2
* SurfaceGo
* SurfaceGo avec LTE Advanced
* Surface Studio 2 (voir les instructions de surface Studio 2 ci-dessous)
* SurfacePro7
* Surface Laptop3
* Surface Laptop Go

## Pilote WOL

Pour permettre la prise en charge de la fonction WOL sur les appareils surface, il est nécessaire de disposer d’un pilote spécifique pour la carte Ethernet surface. Ce pilote n’est pas inclus dans le kit de pilotes et de microprogramme standard pour les appareils surface, vous devez le télécharger et l’installer séparément. Vous pouvez télécharger le pilote surface WOL (SurfaceWOL.msi) à partir de la page [Outils surface pour l’application](https://www.microsoft.com/download/details.aspx?id=46703) dans le centre de téléchargement Microsoft.

Vous pouvez exécuter ce fichier Microsoft Windows Installer (. msi) sur un appareil surface pour installer le pilote de surface WOL ou vous pouvez le distribuer sur des appareils surface avec une solution de déploiement d’application, telle que Microsoft Endpoint Configuration Manager. Pour inclure le pilote surface WOL lors du déploiement, vous pouvez installer le fichier. msi en tant qu’application pendant le processus de déploiement. Vous pouvez également extraire les fichiers de pilote de surface WOL pour les inclure dans le processus de déploiement. Par exemple, vous pouvez les inclure dans le partage de votre kit de développement Microsoft (MDT). Vous pouvez en savoir plus sur le déploiement de surface avec MDT dans le [déploiement de Windows 10 sur les appareils surface avec le kit de développement Microsoft Deployment](https://technet.microsoft.com/itpro/surface/deploy-windows-10-to-surface-devices-with-mdt).

> [!NOTE]
> Lors de l’installation de SurfaceWOL.msi, la clé de Registre suivante est définie sur une valeur de 1, ce qui permet d’identifier facilement les systèmes sur lesquels le pilote WOL a été installé. Si vous avez choisi d’extraire et d’installer ces pilotes séparément lors du déploiement, cette clé de registre ne sera pas configurée et doit être configurée manuellement ou à l’aide d’un script.
> 
> **HKLM\SYSTEM\CurrentControlSet\Control\Power AllowSystemRequiredPowerRequests** 

Pour extraire le contenu de SurfaceWOL.msi, utilisez l’option d’installation administrative de MSIExec (**/a**), comme indiqué dans l’exemple suivant, pour extraire le contenu dans le dossier C:\WOL\:

   `msiexec /a surfacewol.msi targetdir=C:\WOL /qn`

## Instructions surface Studio 2

Pour activer la fonction WOL sur surface Studio 2, vous devez procéder comme suit:

1. Créez les clés de Registre suivantes:

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

## Utilisation de surface WOL

Le pilote surface WOL est conforme à la norme WOL, ce qui indique que le périphérique est réveillée par une communication réseau spéciale appelée Magic Packet. Le paquet Magic est composé de 6 octets de 255 (ou de FF en hexadécimal), suivis de 16 répétitions de l’adresse MAC de l’ordinateur cible. Vous pouvez en savoir plus sur le paquet Magic et la norme WOL sur [Wikipédia](https://wikipedia.org/wiki/Wake-on-LAN#Magic_packet).

>[!NOTE]
>Pour envoyer un paquet Magic et réveiller un appareil à l’aide de WOL, vous devez connaître l’adresse MAC de l’appareil cible et de la carte Ethernet. Dans la mesure où le paquet Magic n’utilise pas le protocole réseau IP, il n’est pas possible d’utiliser l’adresse IP ou le nom DNS de l’appareil.

De nombreuses solutions de gestion telles que Configuration Manager fournissent une prise en charge intégrée de WOL. Il y a également de nombreuses solutions, notamment les applications du Windows Store, les modules PowerShell, les applications tierces et les solutions de gestion tierces qui vous permettent d’envoyer un paquet Magic pour réactiver un périphérique. Par exemple, vous pouvez utiliser le [module Wake on LAN PowerShell](https://gallery.technet.microsoft.com/scriptcenter/Wake-On-Lan-815424c4) dans le centre de scripts technet. 

>[!NOTE]
>Une fois qu’un appareil est réveillée avec un paquet Magic, l’appareil revient en mode veille si une application n’empêche pas activement la mise en veille sur le système ou si la clé de Registre AllowSystemRequiredPowerRequests n’est pas configurée sur 1, ce qui permet aux applications d’éviter la mise en veille. Pour plus d’informations sur cette clé de Registre, voir la section [pilote WOL](#wol-driver) de cet article.
