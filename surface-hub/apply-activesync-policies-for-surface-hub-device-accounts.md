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
ms.openlocfilehash: 6e93069c2d90bdc4c2f505bc28ba0ec1a4f08076
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10833366"
---
# Appliquer des stratégies ActiveSync à des comptes d’appareil (Surface Hub)


Le compte d’appareil du Microsoft Surface Hub utilise ActiveSync pour synchroniser la messagerie et le calendrier. Cela permet à des personnes de participer à des réunions planifiées, de les démarrer à partir du Surface Hub et d’envoyer par courrier électronique n’importe quel tableau blanc réalisé au cours de leur réunion.

Pour le bon fonctionnement de ces fonctionnalités, les stratégies ActiveSync de votre organisation doivent être configurées comme suit :

-   Il ne peut pas s’agir de stratégies globales qui bloquent la synchronisation de la boîte aux lettres de ressources utilisée par le compte d’appareil du Surface Hub. S’il existe une telle stratégie de blocage, vous devez ajouter la surface Hub en tant qu’appareil autorisé.
-   Vous devez définir une stratégie de boîte aux lettres d’appareil mobile où le paramètre **PasswordEnabled** a la valeur False. Les autres paramètres de stratégie de boîte aux lettres d’appareil mobile ne sont pas compatibles avec le Surface Hub.

## Autorisation de l’identificateur de l’ID


Votre organisation peut avoir une stratégie globale empêchant la synchronisation de comptes d’appareil mis en service sur les Surface Hub. Pour configurer cette propriété, voir [Autoriser les ID d’appareil pour ActiveSync](appendix-a-powershell-scripts-for-surface-hub.md#whitelisting-device-ids-cmdlet).

## Défnir PasswordEnabled


Le compte d’appareil doit disposer d’une stratégie ActiveSync où l’attribut **PasswordEnabled** est défini sur False ou sur 0. Pour configurer cette propriété, voir [Création d’une stratégie Microsoft Exchange ActiveSync compatible Surface Hub](appendix-a-powershell-scripts-for-surface-hub.md#create-compatible-as-policy).

 

 





