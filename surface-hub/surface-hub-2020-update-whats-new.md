---
title: Nouveautés de Windows 10 Collaboration mise à jour2020
description: Découvrez les nouveautés de la dernière mise à jour du système d’exploitation Surface Hub, Windows 10 Team 2020 Update.
keywords: séparer les valeurs par des virgules
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 02/01/2021
ms.localizationpriority: Medium
ms.openlocfilehash: f87b8f084b8731bfb329b6c52403d565bca03e3e
ms.sourcegitcommit: 5cfac94c220c8a8d4620c6a7fa75ae2fae089c7f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2021
ms.locfileid: "11312050"
---
# Nouveautés de Windows 10 Collaboration mise à jour2020

Windows 10 Team 2020 Update apporte des améliorations majeures au déploiement et à la gestion des appareils, ainsi que les dernières fonctionnalités de Windows 10.

##  Déploiement et gestion

- **Authentification moderne pour les comptes d’appareil cloud.** Le Surface Hub prend en charge l’authentification basée sur les services web Exchange (EWS) et la bibliothèque d’authentification Active Directory (ADAL) pour se connecter à Exchange, ce qui permet aux clients d’utiliser l’authentification de base. Pour en savoir plus, consultez [l’authentification moderne sur Surface Hub.](https://docs.microsoft.com/surface-hub/surface-hub-modern-auth)
- **Plus de 20 stratégies**de gestion des périphériques mobiles (MDM) nouvelles et mises à jour.      Ces stratégies offrent aux administrateurs informatiques un meilleur contrôle sur plusieurs paramètres d’appareil, notamment : les mises à jour d’applications à partir du Microsoft Store, les paramètres de projection sans fil tels que l’infrastructure Miracast over, les paramètres réseau tels que la qualité de service et l’authentification câblé 802.1x, ainsi que les nouveaux paramètres liés à la confidentialité et au R GDPR. Pour plus d’informations, voir : 
- [Gérer le Surface Hub 2S avec Microsoft Intune.](surface-hub-2s-manage-intune.md)
- [Fournisseurs de services de configuration de stratégies pris en charge par Microsoft Surface Hub](https://docs.microsoft.com//windows/client-management/mdm/policy-csps-supported-by-surface-hub)

##  Appareils joints à Azure Active Directory

- **Sign-on unique (SSO) pour les appareils joints à Azure AD**. Lorsque les utilisateurs se connectent avec leurs informations d’identification Microsoft 365 à « Mes réunions et mes fichiers », leurs informations d’identification d’utilisateur circulent de façon transparente d’une application à l’autre, y compris les expériences Microsoft 365 dans le navigateur.
- **Accès conditionnel (CA) pour les appareils joints à Azure AD.**       Les administrateurs informatiques peuvent déployer des stratégies de sécurité au niveau de l’appareil sur leur Surface Hub joint à Azure AD pour contrôler l’accès aux ressources organisationnelles conformément aux exigences de sécurité et de conformité de l’entreprise.
- **Prise en charge des administrateurs non globaux pour les appareils joints à Azure AD.** Les clients peuvent choisir un ensemble plus granulaire d’administrateurs au sein de leur hiérarchie d’administration pour gérer le Surface Hub. Pour plus d’informations, voir Configurer des comptes d’administrateur non globaux [sur Surface Hub 2S.](surface-hub-2s-nonglobal-admin.md)


## Navigateur et stylet

- **Prise en charge du nouveau Microsoft Edge**. Microsoft Edge a été reconstruit pour optimiser les performances de compatibilité, la sécurité et la confidentialité. Pour en savoir plus, voir [Installer et configurer le nouveau Microsoft Edge sur Surface Hub.](https://docs.microsoft.com/surface-hub/surface-hub-install-chromium-edge)
- - **L’inking à double stylet sur Surface Hub 2S**.   Les utilisateurs peuvent tableau blanc et collaborer côte à côte sur Surface Hub 2S à l’aide de deux stylets Surface Hub 2. Les mises à jour du microprogramme requises pour activer l’inking à double stylet seront publiées avec une mise à jour ultérieure.

## Microsoft Teams  

- **Microsoft Teams installé par défaut.**        Microsoft Teams est inclus comme application de réunion, d’appel et de collaboration par défaut sur de nouveaux appareils Surface Hub qui peuvent être modifiés ou configurés via la gestion des périphériques mobiles ou directement sur Surface Hub à l’aide de l’application Paramètres. Pour plus d’informations, voir [Déployer Microsoft Teams.](https://docs.microsoft.com/MicrosoftTeams/teams-surface-hub)
- **Prise en charge de la jointité de proximité avec Microsoft Teams.**  La jointur de proximité permet aux utilisateurs de prendre des appels Microsoft Teams programmés sur un Surface Hub à proximité à l’aide de leur ordinateur portable/téléphone, ou de passer en toute transparence d’une réunion en cours vers un Surface Hub à proximité. Windows 10 Team 2020 Update ajoute la prise en charge de la gestion des périphériques mobiles (MDM) pour configurer la jointage de proximité. Pour plus d’informations, voir : 

  - [Blog Microsoft Teams](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/microsoft-teams-devices-for-shared-spaces-july-and-august-update/ba-p/1604833). 
  - [Gérer les paramètres Microsoft Teams sur Surface Hub](https://docs.microsoft.com/microsoftteams/rooms/surface-hub-manage-config)

- **Prise en charge des réunions coordonnées avec Microsoft Teams.** Dans les salles de réunion qui disposent d’un Surface Hub et d’un appareil de salle Microsoft Teams, ou d’espaces avec deux appareils Surface Hub, les réunions coordonnées permettent aux utilisateurs d’utiliser facilement les deux appareils lors d’une réunion Microsoft Teams. En un seul clic, les utilisateurs peuvent participer à une réunion à partir de l’un ou l’autre appareil et optimiser l’espace de l’écran en affichant des flux vidéo sur un appareil, ainsi qu’un tableau blanc numérique ou du contenu sur l’autre. Windows 10 Team 2020 Update ajoute la prise en charge de la gestion des périphériques mobiles (MDM) pour configurer les réunions coordonnées. La fonctionnalité sera ensuite publiée sous la forme d’une mise à jour de Microsoft Teams via Microsoft Store.To pour en savoir plus, voir Configurer des réunions coordonnées avec les [salles Microsoft Teams](https://docs.microsoft.com/microsoftteams/rooms/coordinated-meetings)et Surface Hub.

## Sécurité

- **Connexion sans mot de passe à l’aide des clés de sécurité FIDO2**     À l’aide des clés de sécurité FIDO2, les clients peuvent se connecter rapidement et facilement au Surface Hub sans avoir à taper de nom d’utilisateur et de mot de passe. Combinée avec l’authentification Sign-On unique (SSO), cette fonctionnalité fournit une authentification rapide et transparente aux fichiers, applications et sites web au cours d’une réunion. Pour plus d’informations, voir Configurer la [sign-in sans](https://docs.microsoft.com/surface-hub/surface-hub-2s-phone-authenticate)mot de passe sur Surface Hub.
- **Améliorations apportées à la sign-in sans mot de passe à l’aide de Microsoft Authenticator**.  Pour les organisations qui utilisent Azure AD, les utilisateurs peuvent utiliser l’application Microsoft Authenticator pour se connecter sans avoir à taper de nom d’utilisateur et de mot de passe. En outre, les utilisateurs peuvent se connecter à l’aide de leurs alias de messagerie préférés dans Azure AD en plus de leur nom d’utilisateur principal (UPN). Pour plus d’informations, voir [Se connectez au Surface Hub avec Microsoft Authenticator.](https://docs.microsoft.com/surface-hub/surface-hub-authenticator-app)


## Si vous souhaitez en savoir plus

- [Mise à jour du déploiement de Windows 10 Collaboration](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/update-to-the-windows-10-team-rollout/ba-p/1669655)
- [Installer la mise à jour de Windows 10 Team 2020](surface-hub-2020-update.md)  
 