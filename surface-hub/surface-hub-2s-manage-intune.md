---
title: Gérer le Surface Hub 2S avec Intune
description: Découvrez comment mettre à jour et gérer le Surface Hub 2S à l’aide de Intune.
keywords: séparer les valeurs par des virgules
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 12/10/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 3b3b5ed47e3a34369c6890aac051436db1f42347
ms.sourcegitcommit: f8f32455b1230742c58ee74004cbaaad037069b6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2021
ms.locfileid: "11328208"
---
# Gérer le Surface Hub 2S avec Intune

## Inscrire le Surface Hub 2S avec Intune

Le Surface Hub 2S permet aux administrateurs informatiques de gérer les paramètres et les stratégies à l’aide d’un fournisseur de gestion des périphériques mobiles (GPM). Surface Hub 2S dispose d’un composant de gestion intégré pour communiquer avec le serveur d’administration, il n’est donc pas nécessaire d’installer des clients supplémentaires sur l’appareil.

### Inscription manuelle

1. Ouvrez **l’application Paramètres** sur le Surface Hub 2S et connectez-vous en tant qu’administrateur local. Sélectionnez **SurfaceHub** > **Gestion des périphériques** puis **+** pour l’ajouter.
2. Vous serez invité à vous connecter avec le compte à utiliser pour Intune. Une fois l’authentification effectuée, l’appareil est automatiquement enregistré avec Intune.

   ![Inscrire le Surface Hub 2S avec Intune](images/sh2-set-intune1.png)<br>
   
> [!NOTE]
> Le compte utilisé pour l’authentification sera le compte d’inscription Intune et doit être sous licence pour Intune.

### Inscription automatique — Azure Active Directory affilié

Au cours du processus de configuration initial, l’appareil est inscrit automatiquement avec Intune lors de l’affiliation du SurfaceHub avec un client AzureAD sur lequel l’inscription automatique Intune est activée. Si vous souhaitez en savoir plus, consultez la page [Méthodes d’inscription Intune pour les appareils Windows](https://docs.microsoft.com/intune/enrollment/windows-enrollment-methods). L’affiliation AzureAD et l’inscription automatique Intune sont requises pour que le SurfaceHub soit un «appareil compatible» dans Intune. 

## Gestion des paramètres de Windows 10 Team avec Intune

1. Connectez-vous **à Microsoft Endpoint Manager,** sélectionnez ****  >  **Profils de configuration des appareils**Créer un  >  **profil.** 
2. Sous **Plateforme,** sélectionnez Restrictions d’appareil **Windows 10**et  >  **ultérieures (Windows 10 Équipe),** puis sélectionnez **Créer.** 
3. Vous pouvez désormais parcourir et sélectionner des paramètres de restriction d’appareil prédéfini pour Surface Hub et Surface Hub 2S.

 ![Configurez les restrictions des périphériques pour le Surface Hub 2S.](images/sh2-set-intune3.png) <br>

Ces paramètres englobent les catégories suivantes : applications et expérience, informations opérationnelles Azure, maintenance, session et projection sans fil.  

## Fournisseurs de services de configuration (CSP) pris en charge

Outre les stratégies disponibles directement via la console Intune, de nombreux fournisseurs de services de configuration (CSP) sont mappés à des clés de Registre ou des fichiers. 

Microsoft fournit généralement de nouveaux CSP avec chaque nouvelle version du système d’exploitation Windows 10. La mise à jour [de Windows 10 Team 2020](surface-hub-2020-update.md) inclut plus de 20 stratégies de gestion des appareils nouvelles et mises à jour pour Surface Hub et Surface Hub 2S. Ces stratégies de gestion des périphériques mobiles offrent aux administrateurs informatiques un meilleur contrôle sur les mises à jour des applications à partir du Microsoft Store, les paramètres de projection sans fil tels que l’infrastructure Miracast sur, les paramètres réseau tels que la qualité de service et l’authentification câblé 802.1x, ainsi que les nouveaux paramètres liés à la confidentialité et au R GDPR.

Pour plus d'informations, voir les ressources suivantes: 

- [Informations de référence sur les fournisseurs de services de configuration](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference) 
- [Fournisseur de services de configuration SurfaceHub](https://docs.microsoft.com/windows/client-management/mdm/surfacehub-csp)
- [Fournisseurs de services de configuration de stratégies pris en charge par Microsoft Surface Hub](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-surface-hub)
- [Nouveautés de la mise à jour de Surface Hub Team 2020](surface-hub-2020-update-whats-new.md)

## Paramètres de la Qualité de service (QoS, Quality of Service)

Pour obtenir une qualité vidéo et audio optimale sur le Surface Hub 2S, ajoutez les paramètres de QoS suivants à l’appareil. 

### Paramètres de QoS de Microsoft Teams 

| Nom | Description | OMA-URI | Type | Valeur |
|:------ |:------------- |:--------- |:------ |:------- |
|**Ports audio**| Plage du port audio | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsAudio/DestinationPortMatchCondition | String  | 3478-3479 |
|**Valeur DSCP de l’audio**| Marquage des ports audio | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsAudio/DSCPAction | Integer | 46 |
|**Port vidéo**| Plage du port vidéo | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsVideo/DestinationPortMatchCondition | String  | 3480 |
|**Valeur DSCP de la vidéo**| Marquage des ports vidéo | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsVideo/DSCPAction | Integer | 34 |
|**Port de partage**| Partage d’une plage de ports | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsSharing/DestinationPortMatchCondition | Chaîne  | 3481 |
|**Partage DSCP**| Marquage des ports de partage | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsSharing/DSCPAction | entier. | 18 |
|**Ports audio pour le P2P**| Plage du port audio | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PAudio/DestinationPortMatchCondition | String  | 50000-50019 |
|**Valeur DSCP de l’audio pour le P2P**| Marquage des ports audio | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PAudio/DSCPAction | Integer | 46 |
|**Ports vidéo pour le P2P**| Plage du port vidéo | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PVideo/DestinationPortMatchCondition | String  | 50020-50039 |
|**Valeur DSCP de la vidéo pour le P2P**| Marquage des ports vidéo | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PVideo/DSCPAction | Integer | 34 |
|**Ports de partage P2P**| Partage d’une plage de ports | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PSharing/DestinationPortMatchCondition | String  | 50040-50059 |
|**Partage P2P DSCP**| Marquage des ports de partage | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PSharing/DSCPAction | Integer | 18 |


### Paramètres QoS de Skype Entreprise

| Nom                 | Description           | OMA-URI                                                                    | Type    | Valeur                          |
| -------------------- | --------------------- | -------------------------------------------------------------------------- | ------- | ------------------------------ |
| Ports audio          | Plage du port audio      | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBAudio/SourcePortMatchCondition    | String  | 50000-50019                    |
| Valeur DSCP de l’audio           | Marquage des ports audio   | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBAudio/DSCPAction                  | Integer | 46                             |
| Source audio du média   | Nom de l’application Skype        | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBAudio/AppPathNameMatchCondition   | String  | Microsoft.PPISkype.Windows.exe |
| Ports vidéo          | Plage du port vidéo      | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBVideo/SourcePortMatchCondition    | String  | 50020-50039                    |
| Valeur DSCP de la vidéo           | Marquage des ports vidéo   | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBVideo/DSCPAction                  | Integer | 34                             |
| Source vidéo du média   | Nom de l’application Skype        | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBVideo/AppPathNameMatchCondition   | String  | Microsoft.PPISkype.Windows.exe |
| Partage de ports        | Partage d’une plage de ports    | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBSharing/SourcePortMatchCondition  | Chaîne  | 50040-50059                    |
| Partage DSCP         | Marquage des ports de partage | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBSharing/DSCPAction                | entier. | 18                             |
| Partage d’une source multimédia | Nom de l’application Skype        | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBSharing/AppPathNameMatchCondition | String  | Microsoft.PPISkype.Windows.exe |

> [!NOTE]
> Les deux tableaux affichent les plages des ports par défaut. Les administrateurs peuvent modifier les plages des ports dans le panneau de configuration de SkypeEntreprise et de Teams.

## Paramètres De Microsoft Teams

Vous pouvez configurer différents paramètres Microsoft Teams à l’aide d’Intune.

### Modes

Microsoft Teams est nativement installé et défini sur le mode 0 sur le Surface Hub 2S, qui prend en charge Microsoft Teams et Skype Entreprise. Les modes fonctionnent comme décrit ci-dessous :

- Mode0: Skype Entreprise avec la fonctionnalité Microsoft Teams pour les réunions planifiées.
- Mode1: Microsoft Teams avec la fonctionnalité Skype Entreprise pour les réunions planifiées.
- Mode2: Microsoft Teams uniquement.

Pour ajuster le mode, ajoutez les paramètres suivants à un [profil de configuration d’appareil personnalisé.](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure)

| Nom | Description | OMA-URI | Type | Valeur |
|:--- |:--- |:--- |:--- |:--- |
|**ID de l’application Teams**|Nom de l’application|./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId|String| Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe!Teams|
|**Mode de l’application Teams**|Mode Teams|./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode|Integer| 0 ou 1 ou 2|

### Réunions coordonnées et proximité

Les fonctionnalités de réunion coordonnée teams et de proximité peuvent être configurées par le biais d’un fichier [XML](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure) déployé via un profil Intune.
