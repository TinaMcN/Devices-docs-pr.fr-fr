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
ms.date: 9/14/2020
ms.openlocfilehash: d2a948d236ffa286192937cc5ca71099b6eeeafb
ms.sourcegitcommit: c2df79cab0e59e9d7ea6640e5899531b57cd383f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/16/2020
ms.locfileid: "11016423"
---
# Windows Autopilot et appareils Surface

Windows AutoPilot est une technologie de déploiement basée sur le Cloud dans Windows 10. Vous pouvez utiliser Windows AutoPilot pour déployer et configurer à distance des appareils dans le cadre d’un processus de zéro-clic.

Traditionnellement, les professionnels de l’informatique passent beaucoup de temps à créer et à personnaliser des images qui seront ensuite déployées sur les appareils qui disposent déjà d’un système d’exploitation parfaitement adapté. Windows AutoPilot introduit une nouvelle approche de déploiement de zéro-effleurement à l’aide d’une collection de technologies de configuration et de configuration des appareils Windows. Cela permet à un service informatique de configurer/personnaliser des images avec peu ou pas d’infrastructure pour gérer le processus et d’en simplifier le processus. Du point de vue de l’utilisateur, il ne suffit pas de quelques étapes simples pour rendre la surface dans un État productif. En fait, la seule interaction requise de la part de l’utilisateur final consiste à se connecter à un réseau et à vérifier ses informations d’identification. Tout ce qui se passe après le niveau entièrement automatisé.

Windows AutoPilot vous permet d’effectuer les opérations suivantes:

- Joindre automatiquement des appareils à Azure Active Directory (Azure AD).
- Inscription automatique des appareils dans les services de gestion des périphériques mobiles, tels que Microsoft Intune (nécessite un abonnement Azure AD Premium).
- Limiter la création de compte administrateur. AutoPilot est le seul moyen de faire en sorte que la première personne se connecte à Windows en tant qu’utilisateur standard.
- Créer et affecter automatiquement des appareils aux groupes de configuration en fonction de profils d’appareil.
- Personnalisez le contenu OOBE (out-of-Box Experience) et la personnalisation selon les besoins de l’organisation.
- Activez la configuration complète de l’appareil avec Intune.
- Reconfigurez ou redémarrez les appareils à distance.

## Fonctionnement

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

## Enregistrement du support Microsoft

Les clients et les fournisseurs de solutions de Cloud Computing Microsoft (CSP) ont la possibilité d’inscrire des appareils surface en envoyant des demandes au support Microsoft. Pour en savoir plus, voir [prise en charge de l’enregistrement de surface pour Windows AutoPilot](surface-autopilot-registration-support.md).

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
- [Prise en charge de l’inscription de surface pour Windows AutoPilot](surface-autopilot-registration-support.md)