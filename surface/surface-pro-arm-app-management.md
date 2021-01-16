---
title: Déploiement, gestion et maintenance de SurfaceProX
description: Cet article fournit une vue d’ensemble des principales considérations relatives au déploiement, à la gestion et à la maintenance de Surface ProX.
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: high
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 1/15/2021
ms.reviewer: jessko
manager: laurawi
ms.audience: itpro
ms.openlocfilehash: 30f7cd7d861b6497cd536aeb0ea348b6946a2674
ms.sourcegitcommit: 1053479c191fd10651d31a466fad1769fb0cd28b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/16/2021
ms.locfileid: "11271358"
---
# Déploiement, gestion et maintenance de SurfaceProX

## Introduction

Conçu pour gérer les exigences commerciales hautes performances, SurfaceProX innove en intégrant les processeurs les plus puissants dans leur catégorie, les circuits microprogrammés MicrosoftSQ1 et MicrosoftSQ1ARM.

Alimenté par un processeur 3GHz et une GPU 2,1Téraflop, Surface ProX fournit une expérience Windows complète. L’autonomie de 15heures de sa batterie 4GLTE intégrée et sa polyvalence entre l’interaction tactile, le stylet, la tablette et l’ordinateur portable en font l’outil idéal pour les professionnels nomades des secteurs financier, juridique et médical ou toute autre fonction nécessitant une autonomie de batterie importante et des capacités de connectivité continue.

L’appareil SurfaceProX est conçu presque exclusivement pour un environnement basé sur le cloud moderne et fonctionne de manière optimale lorsqu’il est associé avec Microsoft365, Intune et WindowsAutopilot. Cet article présente les principales fonctionnalités de Surface ProX et les éléments à prendre en compte pour le déploiement, la gestion et la maintenance de Surface ProX.

## Déploiement de SurfaceProX

Pour une expérience optimale, déployez Surface Pro X à l’aide de Windows Autopilot avec l’aide d’un Fournisseur de solutions MicrosoftCloud ou en auto-configuration à l’aide de profils de déploiement Autopilot et de fonctionnalités connexes. Pour plus d’informations, consultez:

- [Windows Autopilot et appareils Surface](windows-autopilot-and-surface-devices.md)
- [Vue d’ensemble de Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot)

Le déploiement Autopilot présente plusieurs avantages: il permet d’utiliser le système d’exploitation configuré en usine, rationalisé pour un déploiement Zero-Touch, qui intègre la préinstallation d’Office Pro Plus.

Les entreprises qui utilisent déjà des solutions modernes de gestion, de sécurité et de productivité sont bien positionnées pour tirer parti des fonctionnalités de performances uniques de Surface Pro X. Les clients qui utilisent des applications métier modernes, des applications du Microsoft Store (UWP) ou des solutions de bureau à distance peuvent également en bénéficier.

## Considérations relatives au déploiement basé sur des images

Microsoft Deployment Toolkit (MDT) et MicrosoftEndpoint Configuration Manager (anciennement SystemCenter Configuration Manager) ne prennent pas en charge Surface Pro X actuellement pour le déploiement du système d’exploitation. Les clients qui s’appuient sur un déploiement basé sur des images doivent envisager Surface Pro 7+ pendant qu’ils continuent d’évaluer le bon moment pour passer à des solutions de déploiement modernes. 

## Gestion des appareils Surface ProX

### Intune

Composant de MicrosoftEnterprise Mobility + Security, Intune s’intègre à Azure ActiveDirectory pour le contrôle des accès et des identités et fournit une gestion granulaire des appareils Surface Pro X inscrits. Les stratégies de gestion des appareils mobiles Intune présentent un certain nombre d’avantages par rapport aux anciens outils locaux, tels que la stratégie de groupe Windows. Parmi ces avantages, citons la réduction du délai de connexion aux appareils et la rationalisation du catalogue, qui permet une gestion complète des appareils à partir du cloud. Par exemple, vous pouvez gérer LTE à l’aide de profils eSIM pour configurer des forfaits de données et déployer des codes d’activation sur plusieurs appareils.<br> 

Pour plus d’informations sur l’utilisation d’Intune, reportez-vous à la [documentation Intune](https://docs.microsoft.com/intune/).

### Cogestion

Une fois déployé dans Autopilot, vous pouvez joindre des appareils Surface Pro X à AzureAD ou ActiveDirectory (jonction Azure AD Hybride), où vous serez en mesure de gérer les appareils avec Intune ou de les gérer conjointement avec Endpoint ConfigurationManager, qui installera le client x86 ConfigMgr 32bits.

### Solution MDM tierces

Vous pourrez peut-être utiliser des outils de gestion d’appareils mobiles tiers pour gérer les appareils Surface Pro X. Pour plus d’informations, contactez votre fournisseur d’outils de gestion d’appareils mobiles.

### Logiciel antivirus

Windows Defender vous aide à protéger Windows10 sur les PC ARM pendant la durée de vie prise en charge de l’appareil Windows10. 

Certains antivirus tiers ne peuvent pas être installés sur un PC Windows10 qui s’exécute avec un processeur ARM. La collaboration avec des fournisseurs de logiciels antivirus tiers se poursuit pour la préparation des applications AV sur les PC ARM. Contactez votre fournisseur de logiciels antivirus pour déterminer quand ses applications seront disponibles.

## Maintenance de SurfaceProX

SurfaceProX est inclus dans la version2004 de Windows10 et prend en charge les versions1903 et ultérieures de Windows10. En tant qu’appareil ARM, il a des exigences spécifiques en matière de maintenance des pilotes et des microprogrammes les plus récents. 

Surface Pro X a été conçu pour utiliser Windows Update afin de simplifier le processus de mise à jour des pilotes et du microprogramme pour les utilisateurs domestiques et les utilisateurs des petites entreprises. Utilisez les paramètres par défaut pour recevoir les mises à jour automatiques.  Pour vérifier ces paramètres:

1. Accédez à **Démarrer** > **Paramètres > Mise à jour et sécurité > Windows Update** > **Options avancées.**
2. Sous **Choisir le mode d’installation des mises à jour**, sélectionnez **Automatique (recommandé)**.

### Recommandations pour les clients commerciaux

- Utilisez Windows Update ou Windows Update pour Entreprise pour être sûr de disposer des pilotes et microprogrammes les plus récents. Pour plus d’informations, consultez [Déployer les mises à jour à l’aide de Windows Update pour Entreprise](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb).
- Pour plus d’informations sur le déploiement et la gestion des mises à jour sur les appareils Surface, consultez [Gestion et déploiement du microprogramme et des pilotes pour les appareils Surface](manage-surface-driver-and-firmware-updates.md).
- Notez que WindowsServerUpdateServices (WSUS) ne prend pas en charge la possibilité de fournir des pilotes et des microprogrammes à Surface Pro X.

## Exécution d’applications sur Surface Pro X

La plupart des applications s’exécutent sur des PC Windows10 ARM avec des exclusions limitées.

### Applications prises en charge

- La plupart des applications Win32 x86 s’exécutent sur Surface Pro X.
- Les applications UWP ARM64 et MicrosoftStore natives offrent une excellente expérience utilisateur en utilisant la vitesse native totale du processeur ARM tout en optimisant l’autonomie de la batterie.
- Applications utilisant des pilotes conçus pour un PC Windows10 fonctionnant sur un processeur ARM.

> [!NOTE]
> Avec l'émulation 64 bits qui sera bientôt disponible dans Aperçu via le programme Windows Insider, vous pourrez exécuter des applications 64 bits (x64) sur Surface Pro X.

### Soutien aux applications de FastTrack 

Le programme de Soutien aux applications est à la disposition des clients commerciaux pour leurs applications métier, éditeurs de logiciels indépendants et applications Microsoft internes ciblant Windows10 sur ARM. Si les clients commerciaux rencontrent un problème de compatibilité avec une application fonctionnant sous Windows10ARM, Microsoft fournit des ressources pour les développeurs afin de résoudre les problèmes et de fournir une aide dans le cadre des corrections d’applications, sans frais supplémentaires. Si vous souhaitez en savoir plus, visitez [aka.ms/AppAssure](https://docs.microsoft.com/fasttrack/products-and-capabilities#app-assure).

Pour plus d’informations sur l’exécution d’applications sur Surface Pro X, consultez:

- [FAQ du support des PC Windows10 basés sur ARM](https://support.microsoft.com/help/4521606)
- [Documentation Windows10 sur ARM](https://docs.microsoft.com/windows/arm)

## Bureaux virtuels

Windows Virtual Desktop permet d’accéder aux postes de travail, applications et données Windows sur n’importe quel appareil ou plateforme informatique, à partir de n’importe quel emplacement. Pour en savoir plus, reportez-vous au [site Windows Virtual Desktop](https://aka.ms/wvd). 

## Navigation avec Surface Pro X

Les navigateurs les plus populaires s’exécutent sur Surface Pro X:

- In-box Edge, Firefox, Chrome et Internet Explorer s’exécutent tous sur Surface Pro X.
- Firefox et MicrosoftEdge basés sur Chromium s’exécutent en mode natif et présentent donc de performances améliorées sur un PC Windows10 sur un processeur ARM.

## Installation et utilisation de MicrosoftOffice

- Utilisez Office365 pour une expérience optimale sur un PC Windows10 sur un processeur ARM.
- L’option Office365 «Démarrer en un clic» installe Outlook, Word, Excel et PowerPoint, optimisés pour une exécution sur un PC Windows10 équipé d’un processeur ARM.
- Microsoft Teams s’exécutent parfaitement sur Surface Pro X.
- Pour les «versions perpétuelles» d’Office telles que Office2019, installez la version32bits.

## VPN

Pour vérifier si un VPN tiers spécifique prend en charge un PC Windows10 sur un processeur ARM, contactez le fournisseur de VPN.

## Résumé des fonctionnalités

Les tableaux suivants indiquent la disponibilité des fonctionnalités clés sélectionnées sur SurfaceProX avec Windows10ARM.


**Déploiement**

| Fonctionnalité                                                           | (O/N) | Remarques                                                                                                                             |
| ----------------------------------------------------------------- | --- | --------------------------------------------------------------------------------------------------------------------------------- |
| Windows Autopilot                                                 | Oui |                                                                                                                                   |
| Prise en charge du démarrage réseau (PXE)                                    | Non  |                                                                                                                                   |
| Concepteur de configuration Windows                                    | Non  | Non recommandé pour Surface Pro X.                                                                                                |
| WinPE                                                             | Oui | Non recommandé pour Surface Pro X. Microsoft ne fournit pas le fichier.ISO et les pilotes nécessaires pour prendre en charge WinPE avec Surface Pro X. |
| Endpoint Configuration Manager: Déploiement de système d’exploitation (OSD) | Non  | Non pris en charge sur Surface Pro X.                                                                                                   |
| MDT                                                               | Non  | Non pris en charge sur Surface Pro X.                                                                                                   |

 
 
 **Management**
 

| Fonctionnalité                                       | (O/N)     | Remarques                                                                                 |
| --------------------------------------------- | ------- | ------------------------------------------------------------------------------------- |
| Intune                                        | Oui     | Gérer LTE avec les profils eSIM.                                                        |
| WindowsAutopilot                             | Oui     |                                                                                       |
| AzureAD (co-gestion)                      | Oui     | Possibilité de joindre Surface Pro X à AzureAD ou à Active Directory (jonction AzureAD Hybride). |
| Endpoint Configuration Manager                | Oui     |                                                                                       |
| Mise sous tension lors de la restauration AC                      | Oui     |                                                                                       |
| Kit de ressources de diagnostic pour Surface pour Entreprise | Oui     |                                                                                       |
| Outil pour étiquette d’inventaire Surface                        | Oui     |                                                                                       |
| SurfaceEnterpriseManagementMode (SEMM)     | Partiel | Aucune option permettant de désactiver le matériel sur Surface Pro X au niveau du microprogramme.                 |
| Configurateur de surface UEFI                     | Non      | Aucune option de désactivation du matériel sur Surface Pro X au niveau du microprogramme.                |
| Gestionnaire UEFI Surface                          | Partiel | Aucune option permettant de désactiver le matériel sur Surface Pro X au niveau du microprogramme.                 |

 

**Sécurité**
 

 Fonctionnalité                                       | (O/N)     | Remarques                                                                                 |
| --------------------------------------------- | ------- | ------------------------------------------------------------------------------------- |
| BitLocker                                     | Oui     |                                                       |
| WindowsDefender                              | Oui     |                                                                                       |
| Prise en charge d’antivirus tiers             | Voir la remarque| Certains antivirus tiers ne peuvent pas être installés sur un PC Windows10 qui s’exécute avec un processeur ARM. La collaboration avec des fournisseurs de logiciels antivirus tiers se poursuit pour la préparation des applications AV sur les PC ARM. Contactez votre fournisseur de logiciels antivirus pour déterminer quand ses applications seront disponibles. |
| Démarrage sécurisé               | Oui     |                                                                                       |
| Protection des informations Windows                      | Oui     |                                                                                       |
| SurfaceDataEraser (SDE)     | Oui     |                                                                                       |




## Forum Aux Questions

### Puis-je déployer Surface Pro X avec MDT ou Endpoint ConfigurationManager?

Microsoft Deployment Toolkit (MDT) et Microsoft Endpoint Configuration Manager ne prennent pas en charge Surface Pro X actuellement  pour le déploiement du système d’exploitation. Les clients qui s’appuient sur un déploiement basé sur des images doivent envisager Surface Pro 7+ pendant qu’ils continuent d’évaluer le bon moment pour passer au cloud.

### Comment puis-je déployer Surface Pro X?

Déployez Surface Pro X à l’aide de Windows Autopilot.

### Une récupération complète (BMR) est-elle disponible?

Oui. Consultez [Télécharger une image de récupération pour votre Surface](https://support.microsoft.com/surfacerecoveryimage).

### Intune est-il nécessaire pour gérer Surface Pro X?

Il est recommandé d’utiliser Intune, mais ce n’est pas obligatoire. Une fois déployé dans Autopilot, vous pouvez joindre des appareils Surface Pro X à AzureAD ou ActiveDirectory (jonction Azure AD Hybride), où vous serez en mesure de gérer les appareils avec Intune ou de les gérer conjointement avec Endpoint ConfigurationManager, qui installera le client x86 ConfigMgr 32bits.
