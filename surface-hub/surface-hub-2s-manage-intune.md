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
ms.date: 07/23/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 389db218d06f9f8d3f510e711b03487daf4e06f9
ms.sourcegitcommit: ac34f0ec1a9df74ea688bf0da2a51fadf5139a41
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/18/2020
ms.locfileid: "10934864"
---
# Gérer le Surface Hub 2S avec Intune

## Inscrire le Surface Hub 2S avec Intune

Le Surface Hub 2S permet aux administrateurs informatiques de gérer les paramètres et les stratégies à l’aide d’un fournisseur de gestion des périphériques mobiles (GPM). Surface Hub 2S dispose d’un composant de gestion intégré pour communiquer avec le serveur d’administration, il n’est donc pas nécessaire d’installer des clients supplémentaires sur l’appareil.

### Inscription manuelle

1. Connectez-vous en tant qu’administrateur local sur le Surface Hub 2S et ouvrez l’application **Paramètres**. Sélectionnez **SurfaceHub** > **Gestion des périphériques** puis **+** pour l’ajouter.
2. Une fois l’authentification effectuée, l’appareil est automatiquement enregistré avec Intune.

   ![Inscrire le Surface Hub 2S avec Intune](images/sh2-set-intune1.png)<br>

### Inscription automatique — Azure Active Directory affilié

Au cours du processus de configuration initial, l’appareil est inscrit automatiquement avec Intune lors de l’affiliation du SurfaceHub avec un client AzureAD sur lequel l’inscription automatique Intune est activée. Si vous souhaitez en savoir plus, consultez la page [Méthodes d’inscription Intune pour les appareils Windows](https://docs.microsoft.com/intune/enrollment/windows-enrollment-methods). L’affiliation AzureAD et l’inscription automatique Intune sont requises pour que le SurfaceHub soit un «appareil compatible» dans Intune. 

## Gestion des paramètres d’équipe Windows 10 avec Intune

1. Connectez-vous au **Gestionnaire de points de terminaison Microsoft**, puis sélectionnez profils de configuration des **appareils**  >  **Configuration profiles**  >  **créer un profil**. 
2. Sous **plateforme**, sélectionnez **Windows 10 et les versions ultérieures**de  >  **restrictions d’appareils (équipe Windows 10)** , puis sélectionnez **créer**. 
3. Vous pouvez désormais parcourir et sélectionner les paramètres de restriction d’appareil prédéfinis pour surface Hub et surface Hub 2.

 ![Configurez les restrictions des périphériques pour le Surface Hub 2S.](images/sh2-set-intune3.png) <br>

Ces paramètres s’étendent sur les catégories suivantes: applications et utilisation, Azure Operation Insights, maintenance, session et projection sans fil.  

## Fournisseurs de services de configuration pris en charge (CSP)

Outre les stratégies disponibles directement via la console Intune, il existe de nombreux fournisseurs de services de configuration (CSP) qui mappent à des clés de registre ou des fichiers. 

Microsoft fournit généralement de nouveaux fournisseurs de services cryptographiques avec chaque nouvelle version du système d’exploitation Windows 10. La [mise à jour d’équipe 2020 de Windows 10](surface-hub-install-2020preview.md), disponible dans la version d’évaluation par le biais du programme Windows Insider, inclut plus de 20 stratégies de gestion des périphériques nouvelles et mises à jour pour surface Hub et surface Hub. Ces stratégies de gestion des périphériques mobiles permettent aux administrateurs d’améliorer le contrôle des mises à jour de l’application à partir de la boutique Microsoft, des paramètres de projection sans fil, tels que Miracast sur l’infrastructure, des paramètres réseau tels que la qualité du service et l’authentification filaire 802.1 x, ainsi que les nouveaux paramètres liés à la confidentialité et à RGPD.

Pour plus d’informations, voir les ressources suivantes : 

- [Informations de référence sur les fournisseurs de services de configuration](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference) 
- [Fournisseur de services de configuration SurfaceHub](https://docs.microsoft.com/windows/client-management/mdm/surfacehub-csp)
- [Fournisseurs de services de configuration de stratégies pris en charge par Microsoft Surface Hub](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-surface-hub)

## Paramètres de la Qualité de service (QoS, Quality of Service)

Pour obtenir une qualité vidéo et audio optimale sur le Surface Hub 2S, ajoutez les paramètres de QoS suivants à l’appareil. 

### Paramètres de QoS de Microsoft Teams 

| Nom | Description | OMA-URI | Type | Valeur |
|:------ |:------------- |:--------- |:------ |:------- |
|**Ports audio**| Plage du port audio | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsAudio/DestinationPortMatchCondition | String  | 3478-3479 |
|**Valeur DSCP de l’audio**| Marquage des ports audio | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsAudio/DSCPAction | Integer | 46 |
|**Port vidéo**| Plage du port vidéo | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsVideo/DestinationPortMatchCondition | String  | 3480 |
|**Valeur DSCP de la vidéo**| Marquage des ports vidéo | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsVideo/DSCPAction | Integer | 34 |
|**Ports audio pour le P2P**| Plage du port audio | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PAudio/DestinationPortMatchCondition | String  | 50000-50019 |
|**Valeur DSCP de l’audio pour le P2P**| Marquage des ports audio | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PAudio/DSCPAction | Integer | 46 |
|**Ports vidéo pour le P2P**| Plage du port vidéo | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PVideo/DestinationPortMatchCondition | String  | 50020-50039 |
|**Valeur DSCP de la vidéo pour le P2P**| Marquage des ports vidéo | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PVideo/DSCPAction | Integer | 34 |


### Paramètres QoS de Skype Entreprise

| Nom               | Description         | OMA-URI                                                                  | Type    | Valeur                          |
| ------------------ | ------------------- | ------------------------------------------------------------------------ | ------- | ------------------------------ |
| Ports audio        | Plage du port audio    | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBAudio/SourcePortMatchCondition  | String  | 50000-50019                    |
| Valeur DSCP de l’audio         | Marquage des ports audio | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBAudio/DSCPAction                | Integer | 46                             |
| Source audio du média | Nom de l’application Skype      | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBAudio/AppPathNameMatchCondition | String  | Microsoft.PPISkype.Windows.exe |
| Ports vidéo        | Plage du port vidéo    | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBVideo/SourcePortMatchCondition  | String  | 50020-50039                    |
| Valeur DSCP de la vidéo         | Marquage des ports vidéo | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBVideo/DSCPAction                | Integer | 34                             |
| Source vidéo du média | Nom de l’application Skype      | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBVideo/AppPathNameMatchCondition | String  | Microsoft.PPISkype.Windows.exe |

> [!NOTE]
> Les deux tableaux affichent les plages des ports par défaut. Les administrateurs peuvent modifier les plages des ports dans le panneau de configuration de SkypeEntreprise et de Teams.

## Paramètres du mode Microsoft Teams

Vous pouvez configurer le mode application de Microsoft Teams à l’aide de Intune. Microsoft Teams est nativement installé et défini sur le mode 0 sur le Surface Hub 2S, qui prend en charge Microsoft Teams et Skype Entreprise. Vous pouvez régler les modes comme illustré ci-dessous.

### Modes:

- Mode0: Skype Entreprise avec la fonctionnalité Microsoft Teams pour les réunions planifiées.
- Mode1: Microsoft Teams avec la fonctionnalité Skype Entreprise pour les réunions planifiées.
- Mode2: Microsoft Teams uniquement.

Pour configurer les modes, ajoutez les paramètres suivants à un profil de configuration de périphérique personnalisé.

| Nom | Description | OMA-URI | Type | Valeur |
|:--- |:--- |:--- |:--- |:--- |
|**ID de l’application Teams**|Nom de l’application|./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId|String| Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe!Teams|
|**Mode de l’application Teams**|Mode Teams|./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode|Integer| 0 ou 1 ou 2|
