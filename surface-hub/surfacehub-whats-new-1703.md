---
title: Nouveautés de Windows10 version1703 pour Surface Hub
description: Windows10 version1703 (Creators Update) apporte de nouvelles fonctionnalités à MicrosoftSurface Hub.
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 01/18/2018
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: 722309a6b018c32bde329cb7b2cdd68b859fc1ca
ms.sourcegitcommit: 8e809e8481023fe4421abcdaa1e055a6f2f74f5f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/11/2020
ms.locfileid: "10924940"
---
# Quelles sont les nouveautés dans Windows10, version 1703 pour Microsoft Surface Hub?

Regardez l'ingénieur de Surface Hub Jordan Marchese nous présenter les mises à jour de MicrosoftSurface Hub qui paraissent avec Windows10, version1703 (Creators Update). 

<a href="https://www.youtube.com/watch?v=R8tX10VIgq0" target="_blank"> <img src="images/whats-new-video-thumbnail.png" alt="Link to Surface Hub video on Youtube" /></a>

Windows10 version1703 (également appelée Creators Update) présente les modifications suivantes pour MicrosoftSurface Hub.

## Nouveaux paramètres

Des paramètres ont été ajoutés à la gestion des périphériques mobiles (GPM) et aux fournisseurs de services de configuration (CSP) pour développer les fonctionnalités de gestion de Surface Hub. [Les nouveaux paramètres sont notamment les suivants](manage-settings-with-mdm-for-surface-hub.md):

- InBoxApps/SkypeForBusiness/DomainName
- InBoxApps/Connect/AutoLaunch
- Properties/DefaultVolume
- Properties/ScreenTimeout
- Properties/SessionTimeout
- Properties/SleepTimeout
- Properties/AllowSessionResume
- Properties/AllowAutoProxyAuth
- Properties/DisableSigninSuggestions
- Properties/DoNotShowMyMeetingsAndFiles
- System/AllowStorageCard

En plus des paramètres fondés sur les nouveaux [CSP NetworkQoSPolicy](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/networkqospolicy-csp) et [CSP NetworkProxy](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/networkproxy-csp).
</br>

## Assistant d’approvisionnement

Un assistant simple d’utilisation vous permet de créer rapidement des packages d’approvisionnement que vous pouvez appliquer à plusieurs appareils Surface Hub. Il inclut une jonction à Azure ActiveDirectory en bloc. [Découvrez comment créer un package d’approvisionnement pour Surface Hub.](provisioning-packages-for-certificates-surface-hub.md)

![étapes de l’Assistant d’approvisionnement d’appareils Surface Hub](images/wcd-wizard.png)
    
## Miracast sur votre réseau local ou réseau sans fil existant 

Microsoft a étendu la possibilité [d’envoyer un flux Miracast sur un réseau local](miracast-over-infrastructure.md) plutôt que sur une liaison sans fil directe. 
    
## Récupération sur le cloud

Lorsque vous réinitialisez un appareil Surface Hub, vous avez désormais la possibilité de télécharger et d’installer une version d’usine du système d’exploitation à partir du cloud. [En savoir plus sur la récupération sur le cloud.](device-reset-surface-hub.md#cloud-recovery)

>[!NOTE]
>La récupération sur le cloud ne fonctionne pas si vous utilisez des serveurs proxy.
    
![Réinstaller](images/reinstall.png)
    
## Terminer la session

**J’ai terminé** a été remplacé par **Terminer la session**. [Découvrez comment utiliser Terminer la session.](finishing-your-surface-hub-meeting.md) 

![terminer la session](images/end-session.png)



 

 
