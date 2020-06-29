---
title: Windows Autopilot et appareils Surface
ms.reviewer: ''
manager: laurawi
description: Apprenez-en davantage sur les options de déploiement de Windows AutoPilot pour les appareils surface.
keywords: pilotage automatique, Windows 10, surface, déploiement
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: ea5920649a4a29841b102de73c88187440968910
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832483"
---
# Windows Autopilot et appareils Surface

Windows AutoPilot est une technologie de déploiement basée sur le Cloud dans Windows 10. Vous pouvez utiliser Windows AutoPilot pour déployer et configurer à distance des appareils dans le cadre d’un processus de zéro-clic.

Windows AutoPilot-les appareils enregistrés sont identifiés sur Internet au premier démarrage à l’aide d’une signature d’appareil unique appelée « *hachage matérielle*». Ils sont automatiquement inscrits et configurés à l’aide d’Azure Active Directory (Azure AD) et de la gestion des périphériques mobiles.

Vous pouvez enregistrer des appareils surface au moment de l’achat auprès d’un partenaire de surface activé pour Windows AutoPilot. Ces partenaires peuvent livrer de nouveaux appareils directement à vos utilisateurs. Les appareils seront automatiquement inscrits et configurés lorsqu’ils sont activés pour la première fois. Ce processus élimine la réimagerie lors du déploiement, qui vous permet d’implémenter de nouvelles méthodes agiles de gestion et de distribution de périphériques.

## Gestion moderne

AutoPilot est l’option de déploiement recommandée pour les appareils surface, y compris surface Pro 7, surface Laptop 3 et surface Pro X, spécialement conçue pour le déploiement via AutoPilot.

 Il est préférable d’inscrire vos périphériques de surface à l’aide d’un fournisseur de solutions Microsoft Cloud. Cette étape permet de gérer les paramètres de microprogramme UEFI sur une surface directement à partir de Intune. Il n’est pas nécessaire d’utiliser des appareils pour la gestion des certificats. Pour plus d’informations, consultez [gestion Intune des paramètres de surface UEFI](surface-manage-dfci-guide.md) .

## Remarques sur les versions de Windows

Le déploiement de périphériques surface par le biais du pilotage automatique Windows, y compris par les partenaires de surface au moment de l’achat, nécessite Windows 10 version 1709 (automne Creators Update) ou version ultérieure.

Ces versions de Windows prennent en charge une valeur de hachage de 4 000 octets (4Ko) qui identifie de manière unique les appareils pour Windows AutoPilot, qui sont nécessaires pour les déploiements à l’échelle. Tous les nouveaux appareils surface, y compris surface Pro 7, surface Pro X et surface Laptop 3, sont fournis avec Windows 10 version 1903 ou ultérieure.

## L’interface Exchange sur les appareils surface qui nécessitent une réparation ou un remplacement

Microsoft vérifie automatiquement chaque surface pour l’inscription au pilote automatique et annule l’inscription de l’appareil auprès du client du client.  Microsoft vous permet de vous assurer que l’appareil de remplacement est inscrit à Windows AutoPilot dès qu’un remplacement a été renvoyé au client. Ce service est disponible sur toutes les commandes de service d’échange d’appareils directement avec Microsoft.

> [!NOTE]
> Lorsque les clients utilisent un partenaire pour retourner des appareils, le partenaire est responsable de la gestion du processus Exchange, y compris l’enregistrement et l’inscription des appareils dans Windows AutoPilot.

## Partenaires de surface activés pour Windows AutoPilot

Sélectionnez les partenaires de surface peuvent inscrire des appareils surface dans Windows AutoPilot pour vous au moment de l’achat. Ils peuvent également expédier des périphériques inscrits directement à vos utilisateurs. Les appareils peuvent être configurés complètement par le biais d’un processus Zero-effleurement à l’aide du pilotage automatique Windows, d’Azure AD et de la gestion des appareils mobiles.

Les partenaires de surface qui sont activés pour Windows AutoPilot incluent:

| Partenaires américains | Partenaires généraux | Distributeurs américains |
|--------------|---------------|-------------------|
| * [CHOISI](https://www.cdw.com/) | * [PLUS](https://www.also.com/ec/cms5/de_1010/1010_anbieter/microsoft/windows-autopilot/index.jsp) | * [Synnex](https://www.synnexcorp.com/us/microsoft/surface-autopilot/)  |
| * [Relation](https://www.connection.com/brand/microsoft/microsoft-surface)   | * [ATEA](https://www.atea.com/) | * [Techdata](https://www.techdata.com/)  |
| * [Comprendre](https://www.insight.com/en_US/buy/partner/microsoft/surface/windows-autopilot.html)  | * [Bechtle](https://www.bechtle.com/marken/microsoft/microsoft-windows-autopilot) | * [Ingram](https://go.microsoft.com/fwlink/p/?LinkID=2128954)   |
| * [Chi](https://www.shi.com/Surface) | * [Cancom](https://www.cancom.de/) |    |
| * [Connexion LDI](https://www.myldi.com/managed-it/)  | * [Computacenter](https://www.computacenter.com/uk) |    |
| * [F1](https://www.functiononeit.com/#empower)  |   |  |
| * [Confiance protégée](https://go.microsoft.com/fwlink/p/?LinkID=2129005) | | | 

## En savoir plus

Pour plus d’informations sur Windows AutoPilot, voir:
- [Vue d’ensemble de Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-10-autopilot)
- [Configuration requise de Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements)