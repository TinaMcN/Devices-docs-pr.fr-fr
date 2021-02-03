---
title: Appliquer des stratégies ActiveSync à des comptes d’appareil (Surface Hub)
description: Le compte d’appareil du Microsoft Surface Hub utilise ActiveSync pour synchroniser la messagerie et le calendrier. Cela permet à des personnes de participer à des réunions planifiées, de les démarrer à partir du Surface Hub et d’envoyer par courrier électronique n’importe quel tableau blanc réalisé au cours de leur réunion.
ms.assetid: FAABBA74-3088-4275-B58E-EC1070F4D110
ms.reviewer: ''
manager: laurawi
keywords: Surface Hub, stratégies ActiveSync
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 06/20/2019
ms.localizationpriority: medium
ms.openlocfilehash: b5f828ee6757c150b1287e8210c81592e970b74a
ms.sourcegitcommit: 5cfac94c220c8a8d4620c6a7fa75ae2fae089c7f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2021
ms.locfileid: "11311960"
---
# Appliquer des stratégies ActiveSync à des comptes d’appareil (Surface Hub)


Le compte d’appareil du Microsoft Surface Hub utilise ActiveSync pour synchroniser la messagerie et le calendrier. Cela permet à des personnes de participer à des réunions planifiées, de les démarrer à partir du Surface Hub et d’envoyer par courrier électronique n’importe quel tableau blanc réalisé au cours de leur réunion.

Pour le bon fonctionnement de ces fonctionnalités, les stratégies ActiveSync de votre organisation doivent être configurées comme suit :

-   Il ne peut pas s’agir de stratégies globales qui bloquent la synchronisation de la boîte aux lettres de ressources utilisée par le compte d’appareil du Surface Hub. S’il existe une telle stratégie de blocage, vous devez ajouter le Surface Hub en tant qu’appareil autorisé.
-   Vous devez définir une stratégie de boîte aux lettres d’appareil mobile où le paramètre **PasswordEnabled** a la valeur False. Les autres paramètres de stratégie de boîte aux lettres d’appareil mobile ne sont pas compatibles avec le Surface Hub.

## Autoriser deviceID

Votre organisation peut avoir une stratégie globale empêchant la synchronisation de comptes d’appareil mis en service sur les Surface Hub. Pour configurer cette propriété, voir [Autoriser les ID d’appareil pour ActiveSync](appendix-a-powershell-scripts-for-surface-hub.md#allowing-device-ids-for-activesync).

## Défnir PasswordEnabled

Le compte d’appareil doit disposer d’une stratégie ActiveSync où l’attribut **PasswordEnabled** est défini sur False ou sur 0. Pour configurer cette propriété, voir [Création d’une stratégie Microsoft Exchange ActiveSync compatible Surface Hub](appendix-a-powershell-scripts-for-surface-hub.md#create-compatible-as-policy).

 

 





