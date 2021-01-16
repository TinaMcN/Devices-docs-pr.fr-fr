---
title: Windows Autopilot et appareils Surface
ms.reviewer: ''
manager: laurawi
description: Découvrez les options de déploiement De Windows Autopilot pour les appareils Surface.
keywords: autopilot, windows 10, surface, déploiement
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
ms.openlocfilehash: 31f11db8c3ab12d1af754267022d9060d3a8c026
ms.sourcegitcommit: 1b86286bd13b13749ddbf454ae78d9a24fec44ee
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "11271100"
---
# Windows Autopilot et appareils Surface

Windows Autopilot est une technologie de déploiement informatique dans Windows 10. Vous pouvez utiliser Windows Autopilot pour déployer et configurer des appareils à distance dans un processus zero-touch dès la première utilisation.

En mode classique, les professionnels de l’informatique passent beaucoup de temps à créer et à personnaliser des images qui seront ensuite déployées sur des appareils qui sont déjà intégrés à un système d’exploitation parfaitement adapté déjà installé sur ces derniers. Windows Autopilot introduit une nouvelle approche de déploiement zero-touch à l’aide d’un ensemble de technologies pour configurer et configurer des appareils Windows. Cela permet à un service informatique de configurer/personnaliser des images avec peu ou pas d’infrastructure à gérer et un processus facile et simple. Du point de vue de l’utilisateur, il suffit de quelques étapes simples pour mettre surface à un état productif. En fait, la seule interaction requise de l’utilisateur final consiste à se connecter à un réseau et à vérifier ses informations d’identification. Après cela, tout est entièrement automatisé.

Windows Autopilot vous permet de :

- Joindre automatiquement des appareils à Azure Active Directory (Azure AD).
- Inscrire automatiquement des appareils dans des services de gestion des périphériques mobiles, tels que Microsoft Intune (nécessite un abonnement Azure AD Premium).
- Limiter la création de compte administrateur. Autopilot est le seul moyen d’entrer la première personne qui se connecte à Windows en tant qu’utilisateur standard.
- Créer et attribuer automatiquement des appareils à des groupes de configuration basés sur des profils d’appareil.
- Personnalisez le contenu et la personnalisation OOBE (Out-of-Box Experience) pour répondre aux besoins de l’organisation.
- Activez la configuration complète de l’appareil avec Intune.
- Réinitialisez ou redémarrez les appareils à distance.

## Fonctionnement

Les appareils enregistrés par Windows Autopilot sont identifiés sur Internet au premier démarrage via une signature unique d’appareil appelée hachage *matériel.* Ils sont automatiquement inscrits et configurés à l’aide de solutions de gestion modernes telles qu’Azure Active Directory (Azure AD) et la gestion des appareils mobiles.

Vous pouvez inscrire des appareils Surface au moment de l’achat auprès d’un partenaire Surface activé pour Windows Autopilot. Ces partenaires peuvent expédier de nouveaux appareils directement à vos utilisateurs. Les appareils sont automatiquement inscrits et configurés lorsqu’ils sont allumés pour la première fois. Ce processus élimine la réinventation pendant le déploiement, ce qui vous permet d’implémenter de nouvelles méthodes agiles de gestion et de distribution des appareils.

## Gestion moderne

Autopilot est l’option de déploiement recommandée pour les appareils Surface, y compris Surface Pro 7+, Surface Laptop 3, Surface Pro 7 et Surface Pro X, spécialement conçu pour le déploiement via Autopilot.

 Il est préférable d’inscrire vos appareils Surface à l’aide d’un fournisseur de solutions Microsoft Cloud. Cette étape vous permet de gérer les paramètres du microprogramme UEFI sur Surface directement à partir d’Intune. Cela évite d’avoir à toucher physiquement des appareils pour la gestion des certificats. Voir [la gestion Intune des paramètres UEFI Surface](surface-manage-dfci-guide.md) pour plus d’informations.

## Considérations sur la version de Windows

Le déploiement à grande échelle des appareils Surface via Windows Autopilot, y compris l’inscription par les partenaires Surface au moment de l’achat, nécessite Windows 10 Version 1709 (Fall Creators Update) ou une version ultérieure.

Ces versions de Windows prendre en charge une valeur de hachage de 4 000 byte (4k) qui identifie de manière unique les appareils pour Windows Autopilot, ce qui est nécessaire pour les déploiements à grande échelle. Tous les nouveaux appareils Surface, y compris Surface Pro 7+, Surface Pro X et Surface Laptop 3 sont inclus avec Windows 10 version 1903 ou ultérieure.

## Expérience Exchange sur les appareils Surface qui ont besoin d’être réparés ou remplacés

Microsoft vérifie automatiquement chaque Surface pour l’inscription Autopilot et désinscription de l’appareil du client.  Microsoft s’assure que l’appareil de remplacement est inscrit dans Windows Autopilot une fois qu’un remplacement est livré au client. Ce service est disponible sur toutes les commandes de service Exchange d’appareil directement avec Microsoft.

> [!NOTE]
> Lorsque les clients utilisent un partenaire pour retourner des appareils, le partenaire est responsable de la gestion du processus d’échange, y compris de l’inscription et de l’inscription des appareils dans Windows Autopilot.

## Inscription au Support Microsoft

Les clients et les fournisseurs de solutions Microsoft Cloud (CSP) ont la possibilité d’inscrire des appareils Surface en envoyant des demandes au support Microsoft. Pour en savoir plus, consultez la prise [en charge de l’inscription Surface pour Windows Autopilot.](surface-autopilot-registration-support.md)

## Partenaires Surface activés pour Windows Autopilot

Sélectionnez les partenaires Surface qui peuvent inscrire des appareils Surface dans Windows Autopilot au moment de l’achat. Ils peuvent également expédier des appareils inscrits directement à vos utilisateurs. Les appareils peuvent être entièrement configurés via un processus zero-touch à l’aide de Windows Autopilot, d’Azure AD et de la gestion des appareils mobiles.

Les partenaires Surface activés pour Windows Autopilot sont les suivants :

| Partenaires américains | Partenaires globaux | Distributeurs américains |
|--------------|---------------|-------------------|
| * [CDW](https://www.cdw.com/) | * [ALSO](https://www.also.com/ec/cms5/de_1010/1010_anbieter/microsoft/windows-autopilot/index.jsp) | * [Synnex](https://www.synnexcorp.com/us/microsoft/surface-autopilot/)  |
| * [Connexion](https://www.connection.com/brand/microsoft/microsoft-surface)   | * [ATEA](https://www.atea.com/) | * [Techdata](https://www.techdata.com/)  |
| * [Insight](https://www.insight.com/en_US/buy/partner/microsoft/surface/windows-autopilot.html)  | * [Bechtle](https://www.bechtle.com/marken/microsoft/microsoft-windows-autopilot) | * [Ingram](https://go.microsoft.com/fwlink/p/?LinkID=2128954)   |
| * [ERZ](https://www.shi.com/Surface) | * [Cancom](https://www.cancom.de/) |    |
| * [LDI Connect](https://www.myldi.com/managed-it/)  | * [Computacenter](https://www.computacenter.com/uk) |    |
| * [F1](https://www.functiononeit.com/#empower)  |   |  |
| * [Confiance protégée](https://go.microsoft.com/fwlink/p/?LinkID=2129005) | | | 

## Si vous souhaitez en savoir plus

Pour plus d’informations sur Windows Autopilot, voir :
- [Vue d’ensemble de Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-10-autopilot)
- [Configuration requise de Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements)
- [Prise en charge de l’inscription en surface pour Windows AutoPilot](surface-autopilot-registration-support.md)