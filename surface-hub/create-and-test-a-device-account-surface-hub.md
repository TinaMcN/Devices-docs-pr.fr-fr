---
title: Créer et tester un compte d’appareil (Surface Hub)
description: Cette rubrique présente comment créer et tester le compte d’appareil utilisé par le Microsoft Surface Hub pour communiquer avec Microsoft Exchange et Skype.
ms.assetid: C8605B5F-2178-4C3A-B4E0-CE32C70ECF67
ms.reviewer: rikot
manager: laurawi
keywords: créer et tester un compte d’appareil, compte d’appareil, Surface Hub et MicrosoftExchange, Surface Hub et Skype
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 03/06/2018
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: 20ec9b3a81ad511bcb7880de6b53025fbac0a561
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10833773"
---
# Créer et tester un compte d’appareil (Surface Hub)


Cette rubrique indique comment créer et tester le compte d’appareil utilisé par le Microsoft SurfaceHub pour communiquer avec Microsoft Exchange et Skype.

Un **compte d’appareil** est un compte de ressource Exchange utilisé par le SurfaceHub pour:

-   afficher le calendrier des réunions;
-   Rejoindre des équipes ou des appels Skype entreprise
-   envoyer des messages électroniques (par exemple, le contenu du tableau blanc d’une réunion).

Une fois le compte d’appareil approvisionné sur un SurfaceHub, les utilisateurs peuvent l’ajouter à une invitation à une réunion de la même façon qu’ils inviteraient une salle de réunion. 

## Présentation de la configuration

Le tableau ci-dessous décrit les principales décisions de configuration et étapes qui jalonnent la création d’un compte d’appareil. 
 
| Étape | Description                     |  Objectif                             |
|------|---------------------------------|--------------------------------------|
| 1    | Créer une boîte aux lettres de ressources Exchange dont l’ouverture de session est activée (Exchange2013 ou ultérieur, ou Exchange Online) | Cette boîte aux lettres de ressources permet à l’appareil de gérer un calendrier des réunions, de recevoir des demandes de réunion et d’envoyer du courrier. Son ouverture de session doit être activée afin qu’elle soit approvisionnée sur un SurfaceHub. |
| deuxième    | Configurer les propriétés de la boîte aux lettres | La boîte aux lettres doit être configurée avec les propriétés appropriées pour optimiser l’expérience de réunion sur le SurfaceHub. Pour plus d’informations sur les propriétés de la boîte aux lettres, voir [Propriétés de Microsoft Exchange (SurfaceHub)](exchange-properties-for-surface-hub-device-accounts.md). |
| 3D    | Appliquer à la boîte aux lettres une stratégie de boîte aux lettres d’appareils mobiles compatible | Le SurfaceHub est géré à l’aide de la gestion des périphériques mobiles (GPM) plutôt que par le biais de stratégies de boîte aux lettres d’appareils mobiles. Pour une question de compatibilité, une stratégie de boîte aux lettres d’appareils mobiles où le paramètre **PasswordEnabled** est défini sur False, doit être configurée dans le compte d’appareil. Dans le cas contraire, le SurfaceHub ne pourra synchroniser ni le courrier électronique ni les informations du calendrier. |
| n°4    | Activer la boîte aux lettres avec SkypeEntreprise (LyncServer2013 ou version ultérieure, ou SkypeEntrepriseOnline) | L’application SkypeEntreprise doit être activée pour que vous puissiez utiliser les fonctionnalités de conférence, telles que les appels vidéo, la messagerie instantanée et le partage d’écran.  |
| n°5    | (Facultatif) Placer l’ID d’appareil ActiveSync dans une liste verte | Votre organisation peut disposer d’une stratégie globale empêchant les comptes d’appareil de synchroniser le courrier électronique et les informations du calendrier. Si tel est le cas, vous devez autoriser l’ID d’appareil ActiveSync de votre surface Hub. |
| 6    | (Facultatif) Désactiver l’expiration du mot de passe | Pour simplifier la gestion, vous pouvez désactiver l’expiration du mot de passe du compte d’appareil et autoriser le SurfaceHub à faire tourner automatiquement le mot de passe du compte d’appareil. Pour plus d’informations sur la gestion des mots de passe, voir [Gestion des mots de passe (SurfaceHub)](password-management-for-surface-hub-device-accounts.md).  |

## Étapes de configuration détaillées 

Nous vous recommandons de configurer vos comptes d’appareil à l’aide de PowerShell à distance. Des scripts PowerShell sont à votre disposition pour vous aider à créer et à valider des comptes d’appareil. Pour plus d’informations sur les scripts PowerShell et pour obtenir les instructions afférentes, voir [AnnexeA: PowerShell (SurfaceHub)](appendix-a-powershell-scripts-for-surface-hub.md). 

Pour consulter les étapes détaillées liées à l’utilisation de PowerShell pour approvisionner un compte d’appareil, choisissez une option dans le tableau en fonction du déploiement effectué dans votre organisation. 

| Déploiement dans votre organisation             |  Description                  |
|---------------------------------|--------------------------------------|
| [Déploiement en ligne (Office365)](online-deployment-surface-hub-device-accounts.md) | L’environnement de votre organisation est intégralement déployé sur Office365. |
| [Déploiement local (une seule forêt)](on-premises-deployment-surface-hub-device-accounts.md) | Votre organisation dispose de serveurs qu’elle contrôle et utilise pour héberger ActiveDirectory, Exchange et Skype Entreprise (ou Lync) dans un environnement d'une seule forêt. |
| [Déploiement local (plusieurs forêts)](on-premises-deployment-surface-hub-multi-forest.md) | Votre organisation dispose de serveurs qu’elle contrôle et utilise pour héberger ActiveDirectory, Exchange et Skype Entreprise (ou Lync) dans un environnement à plusieurs forêts. |
| [Déploiement hybride](hybrid-deployment-surface-hub-device-accounts.md) | Votre organisation dispose d’une combinaison de services, dont certains sont hébergés sur site tandis que d’autres le sont en ligne via Office365. |
| [Déploiement en ligne ou hybride à l’aide de l’environnement Hybrid Voice de Skype](skype-hybrid-voice.md) | Votre organisation dispose de pools d’accueil SkypeEntreprise et de serveursExchange dans le cloud, et utilise un pool local de SkypeEntreprise2015 ou CloudConnectorEdition connecté via un réseau téléphonique commuté (PSTN). |


Si vous préférez utiliser une interface graphique utilisateur (IU), vous pouvez effectuer certaines étapes à l’aide de l’interface utilisateur et non de PowerShell. Pour plus d’informations, voir [Créer un compte d’appareil à l’aide de l’IU (SurfaceHub)](create-a-device-account-using-office-365.md).

## Vérification et test de compte

Il existe deux méthodes que vous pouvez utiliser pour valider et tester un compte d’appareil Surface Hub: [Scripts de vérification de compte](appendix-a-powershell-scripts-for-surface-hub.md#acct-verification-ps-scripts) et [Application de diagnostic matériel de Surface Hub](https://www.microsoft.com/store/apps/9nblggh51f2g). Le script de vérification de compte valide un compte d’appareil créé précédemment en utilisant PowerShell à partir de votre bureau. L’application de diagnostic matériel de Surface Hub est installée sur votre Surface Hub et fournit des commentaires détaillés sur les échecs de communication et de connexion. Les deux sont des outils précieux pour tester les comptes d’appareil récemment créés et ils doivent être utilisés pour garantir une disponibilité optimale des comptes.

 

 

 





