---
title: Nouveautés de surface Dock 2
description: Cet article présente les nouvelles fonctionnalités pour le Dock surface nouvelle génération.
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 6/25/2020
ms.reviewer: brrecord
manager: laurawi
audience: itpro
ms.openlocfilehash: 92838599a9d05dbe75f1caad948b97c9cb75bcac
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832232"
---
# Nouveautés de surface Dock 2

Le Dock surface 2, le Dock de surface de nouvelle génération, permet aux utilisateurs de connecter des moniteurs externes et de nombreux périphériques pour obtenir une expérience de bureau entièrement moderne à partir d’un appareil surface. Conçue pour optimiser l’efficacité au bureau, dans un espace de travail flexible, ou à la maison, surface Dock 2 comporte sept ports, y compris deux ports USB-C, avec 15 watts de puissance de chargement rapide pour les téléphones et les accessoires. 

### Prise en charge de la gestion complète des appareils

Surface Dock 2 est conçu pour simplifier la gestion informatique, permettant ainsi aux administrateurs d’automatiser les mises à jour de microprogramme à l’aide de Windows Update ou de centralisation des mises à jour avec les outils de distribution de logiciels internes.

- Le mode de gestion des entreprises de surface (SEMM) permet aux administrateurs informatiques de sécuriser les ports du Dock 2. Pour plus d’informations, reportez-vous à la section [Secure surface Dock 2 ports avec le mode Enterprise Management surface](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/secure-surface-dock-2-ports-with-surface-enterprise-management/ba-p/1418999).
-  La prise en charge de WMI (Windows Management Instrumentation) permet aux administrateurs informatiques de surveiller et de gérer à distance les derniers microprogrammes, l’état de la stratégie et les données associées sur les appareils de l’ancrage surface 2. Pour plus d’informations, reportez-vous à [gérer surface Dock 2 avec WMI](surface-dock2-wmi.md).

## Configuration système requise

- Windows 10 version 1809. Il n’y a pas de prise en charge pour les appareils hôtes Windows 7, Windows 8 et non surface. Le quai de surface 2 fonctionne avec les appareils surface suivants:

  - Surface Pro (5e génération)
  - Surface Pro (5e génération) avec LTE Advanced
  - Surface Laptop (1ère génération)
  - SurfacePro6
  - SurfaceBook2
  - Surface Laptop2
  - SurfaceGo
  - SurfaceGo avec LTE Advanced 
  - SurfacePro7
  - Surface Laptop3
  - SurfaceBook3
  - SurfaceGo2
  - Surface Go 2 avec LTE Advanced


## Composants du Dock surface 2

![Composants du Dock surface 2](./images/surface-dock2.png)
 
### USB

- Deux ports USB-C en face.
- Deux ports USB-C (Gen 2) arrière.
- Deux bus USB tournés vers l’arrière. 

### Vidéo
    
- Deux 4K@60hz. Prend en charge jusqu’à deux affichages sur les appareils suivants:

  - SurfaceBook3
  - SurfaceGo2
  - Surface Go 2 avec LTE Advanced
  - SurfacePro7
  - SurfaceProX
  - Surface Laptop3

- 4K@30Hz 4K@. Prend en charge jusqu’à deux affichages sur les appareils suivants:

  - SurfacePro6
  - Surface Pro (5e génération)
  - Surface Pro (5e génération) avec LTE Advanced
  - Surface Laptop2
  - Surface Laptop (1ère génération)
  - SurfaceGo
  - Surface Book 2.

### Ethernet

- 1 port Gigabit Ethernet. 

### Alimentation électrique externe

- 199 watts prenant en charge 100V-240 v.


## Comparer le Dock surface 2 

### Tableau1. Comparaison des caractéristiques techniques du Dock de surface 2

|Composant|Station d’accueilSurface|Quai de surface 2|
|---|---|---|
|Surflink|Oui|Oui|
|USB-A|2 port frontal USB 3,1 Gen 1<br>2 USB 3,1 Gen 1|2 bus USB 3,2 Gen 2 de l’arrière|
|Mini-port d’affichage|2 face arrière (DP 1,2)|None|
|USB-C|None|2 interface USB 3,2 Gen 2<br>(alimentation 15W)<br>2 USB 3,2 Gen 2 (DP 1.4 a)<br>(7,5 w puissance)|
|entrée/sortie audio de 3,5 mm|Oui|Oui|
|Ethernet|Oui, 1 Gigabit|Oui 1 Gigabit|
|Alimentation C.C.|Oui|Oui|
|Antivol Kensington|Oui|Oui|
|Longueur du câble SurfLink|65cm|80cm|
|Puissance de l’hôte SurfLink|60W|120W|
|Puissance de chargement USB|30W|60W|
|Taux binaire USB|5 Gbit/s|10 Gbit/s|
|Surveiller la prise en charge|2 x 4Ko @30fps ou<br>1 x 4 000 @ des|2 x 4 000 @ des|
|Wake-on-LAN du mode veille connectée <sup> 1</sup>|Oui|Oui|
|Wake-on-LAN à partir du mode veille S4/S5|Non|Oui|
|Démarrage du réseau PXE|Oui|Oui|
|Contrôle d’accès de l’hôte SEMM|Non|Oui
|Contrôle d’accès au port SEMM <sup> 2</sup>|Non|Oui|
|Maintenance du support technique|MSI|Windows Update ou MSI|
||||

1. *Les appareils doivent être configurés pour la fonction Wake on LAN via le mode de gestion de surface entreprise (SEMM) ou l’interface de contrôle du microprogramme de l’appareil (DFCI) pour sortir de la mise en veille La mise en éveil est prise en charge sur surface Pro 7, surface Laptop 3, surface Pro X, surface Book 3 et surface Go 2.  Licence logicielle requise pour certaines fonctionnalités. Vendu séparément.*

2. *Licence logicielle requise pour certaines fonctionnalités. Vendu séparément.*

## Gestion rationalisée des appareils

Surface dispose de fonctionnalités de gestion rationalisées par le biais de Windows Update, ce qui permet aux administrateurs informatiques d’utiliser les fonctionnalités de niveau entreprise suivantes:

- Les **mises à jour apportées par friction**. Mettez à jour vos ancrages de manière silencieuse et automatique, à l’aide de Windows Update ou du gestionnaire de configuration de point de terminaison Microsoft (anciennement System Center Configuration Manager-SCCM) ou d’autres outils de déploiement MSI. 
- **Sortir du réseau**. Gérer et accéder aux appareils d’entreprise sans dépendre des utilisateurs pour maintenir leurs appareils allumés. Même lorsqu’un appareil fixe est en veille, en veille ou en mode hors connexion, votre équipe peut sortir du réseau pour le service et la gestion, à l’aide du gestionnaire de configuration de point de terminaison ou d’autres outils de gestion d’entreprise.
- **Contrôle informatique centralisé**. Déterminez qui peut se connecter à l’ancrage surface 2 en activant ou en désactivant les ports. Restreignez les appareils hôtes qui peuvent être utilisés avec l’ancrage surface 2. Limitez l’accès à un utilisateur unique ou configurez les stations d’accueil de sorte qu’elles soient accessibles uniquement par des utilisateurs spécifiques de votre équipe ou de toute la société.

## Étapes suivantes

- [Ports 2 du Dock de surface sécurisée avec le mode de gestion de surface entreprise](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/secure-surface-dock-2-ports-with-surface-enterprise-management/ba-p/1418999)
- [Mode de gestion SurfaceEnterprise](surface-enterprise-management-mode.md)
- [Bonne pratique pour les paramètres d’alimentation des appareils Surface](maintain-optimal-power-settings-on-Surface-devices.md)
