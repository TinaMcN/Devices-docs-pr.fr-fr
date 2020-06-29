---
title: Gérer les paramètres avec un fournisseur GPM (SurfaceHub)
description: Microsoft Surface Hub offre une solution de gestion d’entreprise pour aider les administrateurs informatiques à gérer des stratégies et des applications métiers sur ces appareils à l’aide d’une solution de gestion des périphériques mobiles (GPM).
ms.assetid: 18EB8464-6E22-479D-B0C3-21C4ADD168FE
ms.reviewer: ''
manager: laurawi
keywords: gestion des périphériques mobiles, GPM, gérer les stratégies
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 03/07/2018
ms.localizationpriority: medium
ms.openlocfilehash: d96f5748533a2d83a0ca68cd42a0663506514d36
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10834250"
---
# Gérer les paramètres avec un fournisseurGPM (SurfaceHub)

Le SurfaceHub et les autres appareils Windows10 permettent aux administrateurs informatiques de gérer les paramètres et stratégies à l’aide d’un fournisseur de gestion des périphériques mobiles (GPM). Comme un composant de gestion intégré communique avec le serveur d’administration, il n’est pas nécessaire d’installer des clients supplémentaires sur l’appareil. Pour plus d’informations, voir [Gestion des appareils mobiles Windows10](https://msdn.microsoft.com/library/windows/hardware/dn914769.aspx).

Surface Hub a été validé auprès des fournisseurs de services de gestion des périphériques mobiles de Microsoft:
- MicrosoftIntune autonome
- MDM locale avec Microsoft Endpoint Configuration Manager

Vous pouvez également gérer les SurfaceHub en faisant appel à tout fournisseurGPM tiers qui peut communiquer avec Windows10 à l’aide du protocoleGPM.

## <a href="" id="enroll-into-mdm"></a>Inscrire un SurfaceHub dans GPM
Vous pouvez inscrire vos hubs de surface à l’aide d’une inscription en bloc, manuelle ou automatique.

### Inscription en bloc
**Pour configurer l’inscription en bloc**
- Le SurfaceHub prend en charge le [fournisseur CSP d’approvisionnement](https://msdn.microsoft.com/library/windows/hardware/mt203665.aspx) pour l’inscription en bloc dansGPM. Pour en savoir plus, voir [Inscription en bloc](https://msdn.microsoft.com/library/windows/hardware/mt613115.aspx).<br>
--OU--
- Si vous disposez d’une infrastructure de configuration de points de terminaison Microsoft locale, consultez [la rubrique inscription en bloc de périphériques avec la gestion des appareils mobiles locale dans Microsoft Endpoint Manager](https://docs.microsoft.com/configmgr/mdm/deploy-use/bulk-enroll-devices-on-premises-mdm).

### Inscription manuelle
**Pour configurer l’inscription manuelle**
1. Sur votre Surface Hub, ouvrez **Paramètres**.
2. Entrez les informations d’identification d’administrateur de l’appareil lorsque vous y êtes invité.
3. Sélectionnez **Cet appareil**, puis accédez à **Gestion des appareils**.
4. Sous **Gestion des appareils**, sélectionnez **Gestion de plus d’appareils**.
5. Suivez les instructions affichées dans la boîte de dialogue pour vous connecter à votre fournisseurGPM.

### Inscription automatique par le biais d’Azure Active Directory Join

Surface Hub permet désormais de s’inscrire automatiquement dans Intune en adhérant l’appareil à Azure Active Directory. 

La première étape consiste à configurer l’inscription automatique de la gestion des périphériques mobiles. Pour plus d’activation, voir [activer l’inscription automatique Windows 10](https://docs.microsoft.com/intune/windows-enroll#enable-windows-10-automatic-enrollment).

Lorsque les appareils sont configurés lors de la première exécution, sélectionnez l’option permettant d’accéder à Azure Active Directory, voir [configurer des administrateurs pour cet appareil](https://docs.microsoft.com/surface-hub/first-run-program-surface-hub#set-up-admins-for-this-device-page) .

## Gérer les paramètres SurfaceHub avec GPM

Vous pouvez utiliser GPM pour gérer certains [Paramètres CSP SurfaceHub](#supported-surface-hub-csp-settings) et [Paramètres Windows10](#supported-windows-10-settings). Selon le fournisseur GPM que vous utilisez, vous pouvez définir ces paramètres à l’aide d’une interface utilisateur intégrée, ou en déployant SyncML personnalisé. Microsoft Intune et Microsoft Endpoint Manager fournissent des expériences intégrées pour vous aider à créer des modèles de stratégie pour surface Hub. Reportez-vous à la documentation de votre fournisseur GPM pour découvrir comment créer et déployer SyncML.

### Paramètres CSP SurfaceHub pris en charge

Vous pouvez configurer les paramètres SurfaceHub indiqués dans le tableau ci-dessous à l’aide de GPM. Le tableau indique si le paramètre est pris en charge dans Microsoft Intune, Microsoft Endpoint Manager ou SyncML.

Pour plus d’informations, voir [Fournisseur de services de configuration SurfaceHub](https://msdn.microsoft.com/library/windows/hardware/mt608323). 


|                                     Paramètre                                      |                                                    Nœud dans le fournisseur de services de configuration SurfaceHub                                                    |            Pris en charge avec<br>Intune?             |    Pris en charge avec<br>Configuration Manager?     | Pris en charge avec<br>SyncML*? |
|----------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
|                                Heures de maintenance                                 |                        MaintenanceHoursSimple/Hours/StartTime <br> MaintenanceHoursSimple/Hours/Duration                         |                       Oui                        |                       Oui                       |             Oui             |
|              Activer l’écran automatiquement via des capteurs de mouvement               |                                                 InBoxApps/Welcome/AutoWakeScreen                                                 |                       Oui                        |                       Oui                       |             Oui             |
|                      Exiger un code confidentiel pour la projection sans fil                       |                                             InBoxApps/WirelessProjection/PINRequired                                             |                       Oui                        |                       Oui                       |             Oui             |
|                            Activer la projection sans fil                            |                                               InBoxApps/WirelessProjection/Enabled                                               |                       Oui                        | Oui.<br> [Utilisez un paramètre personnalisé.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Oui             |
|                 Canal Miracast à utiliser pour la projection sans fil                  |                                               InBoxApps/WirelessProjection/Channel                                               |                       Oui                        | Oui.<br> [Utilisez un paramètre personnalisé.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Oui             |
|              Se connecter à votre espace de travail Operations Management Suite               |                                         MOMAgent/WorkspaceID <br> MOMAgent/WorkspaceKey                                          |                       Oui                        | Oui.<br> [Utilisez un paramètre personnalisé.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Oui             |
|                         Image d’arrière-plan de l’écran d’accueil                          |                                             InBoxApps/Welcome/CurrentBackgroundPath                                              |                       Oui                        | Oui.<br> [Utilisez un paramètre personnalisé.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Oui             |
|               Informations de réunion affichées sur l’écran d’accueil                |                                               InBoxApps/Welcome/MeetingInfoOption                                                |                       Oui                        | Oui.<br> [Utilisez un paramètre personnalisé.] (#example-Manage-surface-Settings-with-Microsoft-Endpoint-Configuration-Manager |             Oui             |
|                      Nom convivial de la projection sans fil                       |                                                     Properties/FriendlyName                                                      | Oui <br> [Utilisez une stratégie personnalisée.](#example-manage-surface-hub-settings-with-microsoft-intune) | Oui.<br> [Utilisez un paramètre personnalisé.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Oui             |
|                   Compte d’appareil, incluant la rotation de mot de passe                    | DeviceAccount/*`<name_of_policy>`* <br> Voir [Fournisseur CSP SurfaceHub](https://msdn.microsoft.com/library/windows/hardware/mt608323.aspx). |                        Non                        |                       Non                        |             Oui             |
|                               Spécifiez le domaine Skype                               |                                              InBoxApps/SkypeForBusiness/DomainName                                               |                    Oui </br>                     | Oui.<br> [Utilisez un paramètre personnalisé.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Oui             |
|               Démarrage automatique de l’application de connexion lors du lancement de la projection               |                                                   InBoxApps/Connect/AutoLaunch                                                   |                    Oui </br>                     | Oui.<br> [Utilisez un paramètre personnalisé.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Oui             |
|                                Définir le volume par défaut                                |                                                     Propriétés/DefaultVolume                                                     |                    Oui </br>                     | Oui.<br> [Utilisez un paramètre personnalisé.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Oui             |
|                                Définir le délai d’expiration de l’écran                                |                                                     Properties/ScreenTimeout                                                     |                    Oui </br>                     | Oui.<br> [Utilisez un paramètre personnalisé.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Oui             |
|                               Définir le délai d’expiration de la session                                |                                                    Properties/SessionTimeout                                                     |                    Oui </br>                     | Oui.<br> [Utilisez un paramètre personnalisé.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Oui             |
|                                Définir le délai d’expiration de la veille                                 |                                                     Properties/SleepTimeout                                                      |                    Oui </br>                     | Oui.<br> [Utilisez un paramètre personnalisé.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Oui             |
|                   Autoriser la reprise de la session après une inactivité de l’écran                   |                                                  Properties/AllowSessionResume                                                   |                    Oui </br>                     | Oui.<br> [Utilisez un paramètre personnalisé.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Oui             |
|             Autoriser l’utilisation du compte de l’appareil pour l’authentification proxy             |                                                  Properties/AllowAutoProxyAuth                                                   |                    Oui </br>                     | Oui.<br> [Utilisez un paramètre personnalisé.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Oui             |
| Désactiver le renseignement automatique de la boîte de dialogue de connexion avec les noms des invités des réunions planifiées |                                               Properties/DisableSignInSuggestions                                                |                    Oui </br>                     | Oui.<br> [Utilisez un paramètre personnalisé.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Oui             |
|              Désactiver la fonctionnalité «Mes réunions et fichiers» dans le menu Démarrer               |                                              Properties/DoNotShowMyMeetingsAndFiles                                              |                    Oui </br>                     | Oui.<br> [Utilisez un paramètre personnalisé.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Oui             |
|                     Définir le Profil LAN pour l’authentification 802.1x câblée                     |                                                         Dot3/LanProfile                                                          | Oui <br> [Utilisez une stratégie personnalisée.](#example-manage-surface-hub-settings-with-microsoft-intune) | Oui.<br> [Utilisez un paramètre personnalisé.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Oui             |
|                    Définir EapUserData pour l’authentification 802.1x câblée                     |                                                         Dot3/EapUserData                                                         | Oui <br> [Utilisez une stratégie personnalisée.](#example-manage-surface-hub-settings-with-microsoft-intune) | Oui.<br> [Utilisez un paramètre personnalisé.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Oui             |

\*Les paramètres pris en charge avec SyncML peuvent également être configurés dans un package de mise en service du concepteur de configuration Windows.

### Paramètres Windows10 pris en charge

Outre les paramètres propres au SurfaceHub, de nombreux paramètres sont communs à tous les appareils Windows10. Ces paramètres sont définis dans les [informations de référence sur les fournisseurs de services de configuration](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference). 

Les tableaux ci-dessous incluent des informations sur les paramètres Windows10 qui ont été validés avec le SurfaceHub. Il existe un tableau comprenant des paramètres pour les zones suivantes: sécurité, navigateur, mises à jour Windows, WindowsDefender, redémarrage à distance, certificats et journaux. Chaque table détermine si le paramètre est pris en charge avec Microsoft Intune, Microsoft Endpoint Manager ou SyncML.

#### Paramètres de sécurité

|      Paramètre       |                                            Détails                                             |                                                                          Informations de référence sur le fournisseur CSP                                                                           |            Pris en charge avec<br>Intune?             |    Pris en charge avec<br>Configuration Manager?     | Pris en charge avec<br>SyncML*? |
|--------------------|------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
|  Autoriser le Bluetooth   |                      Maintenez ce paramètre activé pour prendre en charge des périphériques Bluetooth.                       |                   [Connectivity/AllowBluetooth](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Connectivity_AllowBluetooth)                   |                    Oui. <br>                     | Oui.<br> [Utilisez un paramètre personnalisé.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Oui             |
| Stratégies Bluetooth | À utiliser pour définir le nom du périphérique Bluetooth et bloquer les publicités, la découverte et le couplage automatique. |                     Bluetooth/*`<name of policy>`* <br> Voir [Fournisseur CSP de stratégie](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx).                      |                    Oui. <br>                     | Oui.<br> [Utilisez un paramètre personnalisé.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Oui             |
|    Autoriser l’appareil photo    |                           Maintenez ce paramètre activé pour SkypeEntreprise.                            |                            [Camera/AllowCamera](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Camera_AllowCamera)                            |                    Oui. <br>                     | Oui.<br> [Utilisez un paramètre personnalisé.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Oui             |
|   Autoriser le service de localisation   |                        Maintenez ce paramètre activé pour prendre en charge des applications telles que Cartes.                         |                          [Système/AllowLocation](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#System_AllowLocation)                          |                   Oui. <br> .                    | Oui.<br> [Utilisez un paramètre personnalisé.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Oui             |
|  Autoriser la télémétrie   |                    Maintenez ce paramètre activé pour aider Microsoft à améliorer SurfaceHub.                    |                         [System/AllowTelemetry](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#System_AllowTelemetry)                         |                    Oui. <br>                     | Oui.<br> [Utilisez un paramètre personnalisé.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Oui             |
|  Autoriser les lecteurs USB  |                     Maintenez ce paramètre activé pour permettre la prise en charge des lecteurs USB sur Surface Hub                     | [System/AllowStorageCard](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#system-allowstoragecard) | Oui <br> [Utilisez une stratégie personnalisée.](#example-manage-surface-hub-settings-with-microsoft-intune) | Oui.<br> [Utilisez un paramètre personnalisé.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Oui             |

\*Les paramètres pris en charge avec SyncML peuvent également être configurés dans un package de mise en service du concepteur de configuration Windows. 

#### Paramètres du navigateur

|                          Paramètre                          |                                                                        Détails                                                                        |                                                                             Informations de référence sur le fournisseur CSP                                                                              |            Pris en charge avec<br>Intune?             |    Pris en charge avec<br>Configuration Manager?     | Pris en charge avec<br>SyncML*? |
|-----------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
|                         Pages d’accueil                         |                                               À utiliser pour configurer les pages d’accueil par défaut dans MicrosoftEdge.                                               |                                [Browser/Homepages](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_Homepages)                                | Oui <br> [Utilisez une stratégie personnalisée.](#example-manage-surface-hub-settings-with-microsoft-intune) | Oui.<br> [Utilisez un paramètre personnalisé.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Oui             |
|                       Autoriser les cookies                       |                    Le SurfaceHub supprime automatiquement les cookies à la fin d’une session. Utilisez ce paramètre pour bloquer les cookies au sein d’une session.                     |                             [Browser/AllowCookies](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_AllowCookies)                             | Oui <br> [Utilisez une stratégie personnalisée.](#example-manage-surface-hub-settings-with-microsoft-intune) | Oui.<br> [Utilisez un paramètre personnalisé.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Oui             |
|                   Autoriser les outils de développement                   |                                                   À utiliser pour empêcher l’utilisation des outils de développementF12.                                                   |                      [Browser/AllowDeveloperTools](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_AllowDeveloperTools)                      | Oui <br> [Utilisez une stratégie personnalisée.](#example-manage-surface-hub-settings-with-microsoft-intune) | Oui.<br> [Utilisez un paramètre personnalisé.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Oui             |
|                    Autoriser Ne pas me suivre                     |                                                          À utiliser pour autoriser les en-têtes Ne pas me suivre.                                                          |                          [Browser/AllowDoNotTrack](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_AllowDoNotTrack)                          | Oui <br> [Utilisez une stratégie personnalisée.](#example-manage-surface-hub-settings-with-microsoft-intune) | Oui.<br> [Utilisez un paramètre personnalisé.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Oui             |
|                       Autoriser les fenêtres contextuelles                       |                                                         À utiliser pour bloquer les fenêtres indépendantes du navigateur.                                                          |                              [Browser/AllowPopups](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_AllowPopups)                              | Oui <br> [Utilisez une stratégie personnalisée.](#example-manage-surface-hub-settings-with-microsoft-intune) | Oui.<br> [Utilisez un paramètre personnalisé.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Oui             |
|                 Autoriser les suggestions de recherche                  |                                                  À utiliser pour bloquer les suggestions de recherche dans la barre d’adresses.                                                  |       [Browser/AllowSearchSuggestionsinAddressBar](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_AllowSearchSuggestionsinAddressBar)       | Oui <br> [Utilisez une stratégie personnalisée.](#example-manage-surface-hub-settings-with-microsoft-intune) | Oui.<br> [Utilisez un paramètre personnalisé.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Oui             |
|                     Autoriser Windows Defender SmartScreen                     |                                                       Activez cette option pour activer Windows Defender SmartScreen.                                                       |                         [Browser/AllowSmartScreen](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_AllowSmartScreen)                         | Oui <br> [Utilisez une stratégie personnalisée.](#example-manage-surface-hub-settings-with-microsoft-intune) | Oui.<br> [Utilisez un paramètre personnalisé.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Oui             |
| Éviter d’ignorer les avertissements de Windows Defender SmartScreen pour les sites Web |     Pour une sécurité supplémentaire, utilisez les éléments pour empêcher les utilisateurs d’ignorer les avertissements Windows Defender SmartScreen et de les empêcher d’accéder à des sites Web potentiellement malveillants.     |         [Browser/PreventSmartScreenPromptOverride](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_PreventSmartScreenPromptOverride)         | Oui <br> [Utilisez une stratégie personnalisée.](#example-manage-surface-hub-settings-with-microsoft-intune) | Oui.<br> [Utilisez un paramètre personnalisé.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Oui             |
|  Éviter d’ignorer les avertissements Windows Defender SmartScreen pour les fichiers   | Pour une sécurité supplémentaire, utilisez les éléments pour empêcher les utilisateurs d’ignorer les avertissements Windows Defender SmartScreen et les empêcher de télécharger des fichiers non vérifiés à partir de Microsoft Edge. | [Browser/PreventSmartScreenPromptOverrideForFiles](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_PreventSmartScreenPromptOverrideForFiles) | Oui <br> [Utilisez une stratégie personnalisée.](#example-manage-surface-hub-settings-with-microsoft-intune) | Oui.<br> [Utilisez un paramètre personnalisé.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Oui             |

\*Les paramètres pris en charge avec SyncML peuvent également être configurés dans un package de mise en service du concepteur de configuration Windows.

#### Paramètres de Windows Update

|                      Paramètre                      |                                                                                                           Détails                                                                                                            |                                                                    Informations de référence sur le fournisseur CSP                                                                    |            Pris en charge avec<br>Intune?             |    Pris en charge avec<br>Configuration Manager?     | Pris en charge avec<br>SyncML*? |
|---------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
| Utiliser Current Branch ou Current Branch for Business |                                                       À utiliser pour configurer WindowsUpdate for Business (voir [Mises à jour Windows](manage-windows-updates-for-surface-hub.md)).                                                       |            [Update/BranchReadinessLevel](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Update_BranchReadinessLevel)             | Oui <br> [Utilisez une stratégie personnalisée.](#example-manage-surface-hub-settings-with-microsoft-intune) | Oui.<br> [Utilisez un paramètre personnalisé.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Oui             |
|               Différer les mises à jour de fonctionnalité               |                                                                                                          Voir ci-dessus.                                                                                                          | [Update/DeferFeatureUpdatesPeriodInDays](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Update_DeferFeatureUpdatesPeriodInDays) | Oui <br> [Utilisez une stratégie personnalisée.](#example-manage-surface-hub-settings-with-microsoft-intune) | Oui.<br> [Utilisez un paramètre personnalisé.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Oui             |
|               Différer les mises à jour qualité               |                                                                                                          Voir ci-dessus.                                                                                                          | [Update/DeferQualityUpdatesPeriodInDays](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Update_DeferQualityUpdatesPeriodInDays)  | Oui <br> [Utilisez une stratégie personnalisée.](#example-manage-surface-hub-settings-with-microsoft-intune) | Oui.<br> [Utilisez un paramètre personnalisé.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Oui             |
|               Suspendre les mises à jour des fonctionnalités               |                                                                                                          Voir ci-dessus.                                                                                                          |             [Update/PauseFeatureUpdates](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Update_PauseFeatureUpdates)              | Oui <br> [Utilisez une stratégie personnalisée.](#example-manage-surface-hub-settings-with-microsoft-intune) | Oui.<br> [Utilisez un paramètre personnalisé.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Oui             |
|               Suspendre les mises à jour qualité               |                                                                                                          Voir ci-dessus.                                                                                                          |             [Update/PauseQualityUpdates](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Update_PauseQualityUpdates)              | Oui <br> [Utilisez une stratégie personnalisée.](#example-manage-surface-hub-settings-with-microsoft-intune) | Oui.<br> [Utilisez un paramètre personnalisé.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Oui             |
|           Configurer l’appareil pour utiliser WSUS            |                                            À utiliser pour connecter votre SurfaceHub à WSUS à la place de WindowsUpdate (voir [Mises à jour Windows](manage-windows-updates-for-surface-hub.md)).                                             |                [Update/UpdateServiceUrl](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Update_UpdateServiceUrl)                 | Oui <br> [Utilisez une stratégie personnalisée.](#example-manage-surface-hub-settings-with-microsoft-intune) | Oui.<br> [Utilisez un paramètre personnalisé.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Oui             |
|               Optimisation de la distribution               | Utilisez le partage de contenu entre homologues pour réduire les problèmes de bande passante pendant les mises à jour. Pour plus d’informations, voir [Configurer l’optimisation de la distribution des mises à jour Windows10](https://technet.microsoft.com/itpro/windows/manage/waas-delivery-optimization). |         DeliveryOptimization/*`<name of policy>`* <br> Voir [Fournisseur CSP de stratégie](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx).          | Oui <br> [Utilisez une stratégie personnalisée.](#example-manage-surface-hub-settings-with-microsoft-intune) | Oui.<br> [Utilisez un paramètre personnalisé.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Oui             |

\*Les paramètres pris en charge avec SyncML peuvent également être configurés dans un package de mise en service du concepteur de configuration Windows.

#### Paramètres de WindowsDefender

|      Paramètre      |                                              Détails                                               |                                                     Informations de référence sur le fournisseur CSP                                                      |            Pris en charge avec<br>Intune?             |    Pris en charge avec<br>Configuration Manager?     | Pris en charge avec<br>SyncML*? |
|-------------------|----------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
| Stratégies de Defender |            À utiliser pour configurer différents paramètres de Defender, notamment une heure d’analyse planifiée.            | Defender/*`<name of policy>`* <br> Voir [Fournisseur CSP de stratégie](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx). | Oui <br> [Utilisez une stratégie personnalisée.](#example-manage-surface-hub-settings-with-microsoft-intune) | Oui.<br> [Utilisez un paramètre personnalisé.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Oui             |
|  Statut de Defender  | Pour initier une analyse de protection, forcer une mise à jour de sécurité, interroger les menaces détectées. |                   [Fournisseur de services de configuration Defender](https://msdn.microsoft.com/library/windows/hardware/mt187856.aspx)                    |                       Oui                        |                       Oui                       |             Oui             |

\*Les paramètres pris en charge avec SyncML peuvent également être configurés dans un package de mise en service du concepteur de configuration Windows.

#### Redémarrage à distance

|                       Paramètre                        |                                                          Détails                                                          |                                                             Informations de référence sur le fournisseur CSP                                                             |            Pris en charge avec<br>Intune?             |    Pris en charge avec<br>Configuration Manager?     | Pris en charge avec<br>SyncML*? |
|------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
|            Redémarrer l’appareil immédiatement             | À utiliser conjointement avec OMS pour réduire les coûts de support (voir [Surveiller votre Microsoft Surface Hub](monitor-surface-hub.md)). |        ./Vendor/MSFT/Reboot/RebootNow <br> Voir [Fournisseur CSP du redémarrage](https://msdn.microsoft.com/library/windows/hardware/mt720802.aspx)        |                       Oui                        |                       Non                        |             Oui             |
|    Redémarrer l’appareil à une date et une heure planifiées    |                                                        Voir ci-dessus.                                                         |     ./Vendor/MSFT/Reboot/Schedule/Single <br> Voir [Fournisseur CSP du redémarrage](https://msdn.microsoft.com/library/windows/hardware/mt720802.aspx)     | Oui <br> [Utilisez une stratégie personnalisée.](#example-manage-surface-hub-settings-with-microsoft-intune) | Oui.<br> [Utilisez un paramètre personnalisé.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Oui             |
| Redémarrer l’appareil quotidiennement à une date et une heure planifiées |                                                        Voir ci-dessus.                                                         | ./Vendor/MSFT/Reboot/Schedule/DailyRecurrent <br> Voir [Fournisseur CSP du redémarrage](https://msdn.microsoft.com/library/windows/hardware/mt720802.aspx) | Oui <br> [Utilisez une stratégie personnalisée.](#example-manage-surface-hub-settings-with-microsoft-intune) | Oui.<br> [Utilisez un paramètre personnalisé.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Oui             |

\*Les paramètres pris en charge avec SyncML peuvent également être configurés dans un package de mise en service du concepteur de configuration Windows.

#### Installer des certificats

|             Paramètre             |                           Détails                            |                                           Informations de référence sur le fournisseur CSP                                            |                                                         Pris en charge avec<br>Intune?                                                          |                                                                  Pris en charge avec<br>Configuration Manager?                                                                  | Pris en charge avec<br>SyncML*? |
|---------------------------------|--------------------------------------------------------------|----------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------|
| Installer des certificats d’autorité de certification approuvés | À utiliser pour déployer des certificats d’autorité de certification racine et intermédiaires approuvés. | [Fournisseur CSP RootCATrustedCertificates](https://msdn.microsoft.com/library/windows/hardware/dn904970.aspx) | Oui. <br> Voir [Configurer les profils de certificats Intune](https://docs.microsoft.com/intune/deploy-use/configure-intune-certificate-profiles). | Oui. <br> Découvrez [comment créer des profils de certificats dans Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/configmgr/protect/deploy-use/create-certificate-profiles). |             Oui             |

<!--
| Install client certificates  | Use to deploy Personal Information Exchange (.pfx, .p12) certificates. | [ClientCertificateInstall CSP](https://msdn.microsoft.com/library/windows/hardware/dn920023.aspx) | Yes. <br> See [How to Create and Deploy PFX Certificate Profiles in Intune Standalone](https://blogs.technet.microsoft.com/karanrustagi/2016/03/16/want-to-push-a-certificate-to-device-but-cant-use-ndes-continue-reading/). | Yes. <br> See [How to create PFX certificate profiles in Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/configmgr/protect/deploy-use/create-pfx-certificate-profiles). | Yes |
-->
\*Les paramètres pris en charge avec SyncML peuvent également être configurés dans un package de mise en service du concepteur de configuration Windows.

#### Collecter les journaux

|     Paramètre      |                      Détails                       |                                     Informations de référence sur le fournisseur CSP                                      | Pris en charge avec<br>Intune? | Pris en charge avec<br>Configuration Manager? | Pris en charge avec<br>SyncML*? |
|------------------|----------------------------------------------------|----------------------------------------------------------------------------------------|---------------------------|------------------------------------------|-----------------------------|
| Collecter les journaux de suivi des événements ETW | À utiliser pour collecter à distance les journaux ETW du SurfaceHub. | [Fournisseur CSP DiagnosticLog](https://msdn.microsoft.com/library/windows/hardware/mt219118.aspx) |            Non             |                    Non                    |             Oui             |

<!--
| Collect security auditing logs | Use to remotely collect security auditing logs from Surface Hub. | SecurityAuditing node in [Reporting CSP](https://msdn.microsoft.com/library/windows/hardware/mt608321.aspx) | No | No | Yes |-->
\*Les paramètres pris en charge avec SyncML peuvent également être configurés dans un package de mise en service du concepteur de configuration Windows.

#### Définir la stratégie de qualité du service (QoS) réseau

|        Paramètre         |                                                            Détails                                                             |                                                    Informations de référence sur le fournisseur CSP                                                     |            Pris en charge avec<br>Intune?             |    Pris en charge avec<br>Configuration Manager?     | Pris en charge avec<br>SyncML*? |
|------------------------|--------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
| Définir la stratégie de qualité de service (QoS) réseau | Permet de définir une stratégie de qualité de service pour effectuer un ensemble d’actions sur le trafic réseau. Cela est utile pour hiérarchiser les paquets réseau Skype. | [CSP NetworkQoSPolicy](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/networkqospolicy-csp) | Oui <br> [Utilisez une stratégie personnalisée.](#example-manage-surface-hub-settings-with-microsoft-intune) | Oui.<br> [Utilisez un paramètre personnalisé.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Oui             |

\*Les paramètres pris en charge avec SyncML peuvent également être configurés dans un package de mise en service du concepteur de configuration Windows.

#### Définir un proxy réseau

|      Paramètre      |                               Détails                               |                                                Informations de référence sur le fournisseur CSP                                                 |            Pris en charge avec<br>Intune?             |    Pris en charge avec<br>Configuration Manager?     | Pris en charge avec<br>SyncML*? |
|-------------------|---------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
| Définir un proxy réseau | Permet de configurer un serveur proxy pour les connexions Ethernet et Wi-Fi. | [CSP NetworkProxy](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/networkproxy-csp) | Oui <br> [Utilisez une stratégie personnalisée.](#example-manage-surface-hub-settings-with-microsoft-intune) | Oui.<br> [Utilisez un paramètre personnalisé.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Oui             |

\*Les paramètres pris en charge avec SyncML peuvent également être configurés dans un package de mise en service du concepteur de configuration Windows.

#### Configurer le menu Démarrer

|       Paramètre        |                                                                       Détails                                                                        |                                                        Informations de référence sur le fournisseur CSP                                                         |            Pris en charge avec<br>Intune?             |    Pris en charge avec<br>Configuration Manager?     | Pris en charge avec<br>SyncML*? |
|----------------------|------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
| Configurer le menu Démarrer | Utilisez cette option pour configurer les applications qui s’affichent dans le menu Démarrer. Pour plus d’informations, consultez [Configurer le menu Démarrer de Surface Hub](surface-hub-start-menu.md). | [Fournisseur CSP de stratégie: Démarrer/StartLayout](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-start#start-startlayout) | Oui <br> [Utilisez une stratégie personnalisée.](#example-manage-surface-hub-settings-with-microsoft-intune) | Oui.<br> [Utilisez un paramètre personnalisé.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Oui             |

\*Les paramètres pris en charge avec SyncML peuvent également être configurés dans un package de mise en service du concepteur de configuration Windows.

### Générer des OMA URI pour les paramètres 
Vous devez utiliser un URI OMA d’un paramètre pour créer une stratégie personnalisée dans Intune ou un paramètre personnalisé dans Microsoft Endpoint Manager.

**Pour générer l’OMA URI pour les paramètres indiqués dans la documentation du fournisseur CSP**
1. Dans la documentation du fournisseur CSP, identifiez le nœud racine du fournisseur CSP. Il ressemble généralement à `./Vendor/MSFT/<name of CSP>` <br>
*Par exemple, le nœud racine du [fournisseur CSP SurfaceHub](https://msdn.microsoft.com/library/windows/hardware/mt608323.aspx) est `./Vendor/MSFT/SurfaceHub`.*
2. Identifiez le chemin d’accès au nœud pour le paramètre que vous voulez utiliser. <br>
*Par exemple, le chemin d’accès au nœud pour le paramètre permettant d’activer la projection sans fil est `InBoxApps/WirelessProjection/Enabled`.*
3. Ajoutez le chemin d’accès au nœud au nœud racine pour générer l’OMA URI. <br>
*Par exemple, l’OMA URI pour le paramètre permettant d’activer la projection sans fil est `./Vendor/MSFT/SurfaceHub/InBoxApps/WirelessProjection/Enabled`.*

Le type de données est également indiqué dans la documentation du fournisseur CSP. Les types de données les plus courants sont les suivants:
- char (chaîne)
- int (entier)
- bool (booléen)


## Exemple: Gérer les paramètres Surface Hub avec MicrosoftIntune

Vous pouvez utiliser MicrosoftIntune pour gérer les paramètres Surface Hub. Pour les paramètres personnalisés, suivez les instructions qui se trouvent dans [Comment configurer les paramètres d’appareil personnalisés dans MicrosoftIntune](https://docs.microsoft.com/intune/custom-settings-configure). Pour **Plateforme**, sélectionnez **Windows10 et versions ultérieures**et dans **Type de profil**, sélectionnez **Restrictions d’appareil (Windows10 Collaboration)**.



## Exemple: gérer les paramètres de surface Hub avec Microsoft Endpoint Configuration Manager
Configuration Manager prend en charge la gestion des appareils modernes qui ne nécessitent pas le client Configuration Manager pour les gérer, y compris surface Hub. Si vous utilisez déjà Configuration Manager pour gérer d’autres appareils de votre organisation, vous pouvez continuer à utiliser la console Configuration Manager comme emplacement unique pour gérer les hubs de surface.

> [!NOTE]
> Ces instructions sont basées sur la branche actuelle de Configuration Manager.

**Pour créer un élément de configuration pour les paramètres SurfaceHub**

1. Dans l’espace de travail **Ressources et conformité** de la console Configuration Manager, cliquez sur **Vue d’ensemble** > **Paramètres de compatibilité** > **Éléments de configuration**.
2. Dans l’onglet **Accueil**, dans le groupe **Créer**, cliquez sur **Créer un élément de configuration**.
3. Dans la page **Général** de l’Assistant Création d’élément de configuration, spécifiez un nom et une description facultative pour l’élément de configuration.
4. Sous **Paramètres pour les appareils gérés sans le client Configuration Manager**, sélectionnez **Windows 8.1 et Windows 10**, puis cliquez sur **Suivant**.

    ![exemple d’interfaceutilisateur](images/configmgr-create.png)
5. Dans la page **Plateformes prises en charge**, développez **Windows10** et sélectionnez **Tous les appareils Windows10 Collaboration et versions supérieures**. Désélectionnez les autres plateformes Windows, puis cliquez sur **Suivant**.

    ![sélection d’une plateforme](images/configmgr-platform.png)
7. Dans la page **Paramètres de l’appareil**, sous **Groupes de paramètres d’appareils**, sélectionnez **Windows10 Collaboration**.


8. Dans la page **Windows10 Collaboration**, configurez les paramètres requis.

    ![Windows 10 Collaboration](images/configmgr-team.png)
9. Vous devez créer des paramètres personnalisés pour gérer ceux qui ne sont pas disponibles dans la page Windows10 Collaboration. Dans la page **Paramètres de l’appareil**, cochez la case **Configurer d’autres paramètres qui ne se trouvent pas dans les groupes de paramètres par défaut**.

    ![paramètres supplémentaires](images/configmgr-additional.png)
10. Dans la page **Paramètres supplémentaires**, cliquez sur **Ajouter**.
11. Dans la boîte de dialogue **Parcourir les paramètres**, cliquez sur **Créer un paramètre**.
12. Dans la boîte de dialogue **Créer un paramètre**, dans l’onglet **Général**, spécifiez un nom et une description facultative pour le paramètre personnalisé.
13. Sous **Type de paramètre**, sélectionnez **OMA URI**.
14. Complétez le formulaire pour créer un paramètre, puis cliquez sur **OK**.

    ![paramètre OMA URI](images/configmgr-oma-uri.png)
15. Dans la boîte de dialogue **Parcourir les paramètres**, sous **Paramètres disponibles**, sélectionnez le nouveau paramètre que vous avez créé, puis cliquez sur **Sélectionner**.
16. Dans la boîte de dialogue **Créer une règle**, complétez le formulaire pour spécifier une règle pour le paramètre, puis cliquez sur **OK**.
17. Répétez les étapes9 à 15 pour chaque paramètre personnalisé à ajouter à l’élément de configuration.
18. Une fois que vous avez terminé, dans la boîte de dialogue **Parcourir les paramètres**, cliquez sur **Fermer**.
19. Terminez l’Assistant. <br> Vous pouvez afficher le nouvel élément de configuration dans le nœud **Éléments de configuration** de l’espace de travail **Ressources et conformité**.

Pour plus d’informations, consultez [créer des éléments de configuration pour windows 8,1 et les appareils Windows 10 gérés sans le client Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/configmgr/compliance/deploy-use/create-configuration-items-for-windows-8.1-and-windows-10-devices-managed-without-the-client).

## Rubriques connexes

[Gérer Microsoft SurfaceHub](manage-surface-hub.md)











