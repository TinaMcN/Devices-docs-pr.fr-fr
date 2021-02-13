---
title: Installer et configurer le nouveau Microsoft Edge on Surface Hub
description: Installez et configurez le nouveau Microsoft Edge sur le Surface Hub.
keywords: séparer les valeurs par des virgules
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 02/10/2021
ms.localizationpriority: Medium
appliesto:
- Surface Hub
- Surface Hub 2S
ms.openlocfilehash: 2bc11fb18137ce21cba27368e0c12bbb9e73a4c2
ms.sourcegitcommit: 7e028c1e66fb393dc0e8917dac257ce95e5e9ce7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/12/2021
ms.locfileid: "11327308"
---
# Installer et configurer le nouveau Microsoft Edge on Surface Hub

Windows 10 Team 2020 Update prend en charge le nouveau Microsoft Edge basé sur Chromium (version 85 et supérieures) en tant que navigateur recommandé pour Surface Hub 2S et Surface Hub (v1). Cet article explique comment installer le navigateur à l’aide de l’une des trois méthodes : un package d’approvisionnement, Microsoft Intune ou un fournisseur de gestion des périphériques mobiles (MDM) tiers.

> [!IMPORTANT]
> Par défaut, les appareils Surface Hub sont préinstallés avec l’ancienne version de Microsoft Edge (version 44). Après avoir installé la mise à jour [2020,](surface-hub-2020-update.md)il est recommandé de basculer vers le nouveau navigateur Microsoft Edge . La prise [en charge de l’héritage](https://support.microsoft.com/microsoft-edge/what-is-microsoft-edge-legacy-3e779e55-4c55-08e6-ecc8-2333768c0fb0) de Microsoft Edge prendra fin le 9 mars 2021.

## Installer Microsoft Edge à l’aide d’un package d’approvisionnement

1. À partir d’un PC, téléchargez le package d’approvisionnement [Microsoft Edge](https://aka.ms/HubEdge) (MicrosoftEdgeInstaller.ppkg) dans le dossier racine d’un lecteur USB.
2. Insérez le lecteur USB dans le Surface Hub.
3. À partir du Surface Hub, ouvrez **Paramètres** et entrez vos informations d’identification d’administrateur lorsque vous y être invité.
4. Accédez à **Surface Hub** > **Gestion des appareils**. Sous **Packages d’approvisionnement**, sélectionnez **Ajouter ou supprimer un package d’approvisionnement**.
5. Sélectionnez **Ajouter un package**.
6. Choisissez le package d’approvisionnement Microsoft Edge et sélectionnez **Ajouter.**
7. Vous verrez un résumé des modifications que le package d’approvisionnement applique. Sélectionner **Oui, l’ajouter**.
8. Attendez la fin de l’installation de Microsoft Edge. Une fois l’installation installée, accédez au menu Démarrer du Surface Hub pour accéder au nouveau Microsoft Edge.              

> [!NOTE]
> Si une version plus récente de Microsoft Edge est disponible, elle sera automatiquement mise à jour.
 
## Installer Microsoft Edge à l’aide d’Intune
 
> [!NOTE]
> L’appareil Surface Hub doit être inscrit et géré à l’aide d’Intune. Pour plus d’informations, voir [Gérer Surface Hub 2S avec Microsoft Intune.](https://docs.microsoft.com/surface-hub/surface-hub-2s-manage-intune)
 

1. [Téléchargez le programme d’installation de Microsoft Edge.](https://www.microsoft.com/edge/business/download)
    - Utiliser la version actuelle à partir [du canal stable](https://docs.microsoft.com/deployedge/microsoft-edge-channels) **(version 85)**
    - Choisir **Windows 64 bits**
2. [Ajoutez le programme d’installation Microsoft Edge en tant qu’application métier à Microsoft Intune.](https://docs.microsoft.com/mem/intune/apps/lob-apps-windows)
    - Si vous choisissez d’utiliser Microsoft Edge Update pour gérer les mises à jour automatiques de Microsoft Edge, assurez-vous de configurer le paramètre Ignorer la **version** de l’application dans le volet d’informations de l’application. **** Lorsque vous basculez ce paramètre sur **Oui,** Microsoft Intune n’applique pas la version de l’application installée sur l’appareil Surface Hub.

## Installer Microsoft Edge à l’aide d’un fournisseur de gestion des données de gestion des données tiers

1. [Téléchargez le programme d’installation de Microsoft Edge à partir de Microsoft.](https://www.microsoft.com/edge/business/download)
    - Utiliser la version actuelle à partir [du canal stable](https://docs.microsoft.com/deployedge/microsoft-edge-channels) **(version 85)**
    - Choisir **Windows 64 bits**
2. Stage the Microsoft Edge installer on a hosted location, such as a local file share (\\server\share\MicrosoftEdgeEnterpriseX64.msi). L’appareil Surface Hub doit être autorisé à accéder à l’emplacement hébergé.
3. Utilisez le fournisseur de services de [configuration EnterpriseDesktopAppManagement (CSP)](https://docs.microsoft.com/windows/client-management/mdm/enterprisedesktopappmanagement-csp) via votre fournisseur de gestion des solutions de gestion des données (MDM) pour installer Microsoft Edge.

## Configurer MicrosoftEdge

### Stratégies Microsoft Edge par défaut pour Surface Hub

Microsoft Edge est préconfiguré avec les configurations de stratégie suivantes pour fournir une expérience optimisée pour le Surface Hub.
 
> [!TIP]
> Il est recommandé de conserver la valeur par défaut pour ces paramètres de stratégie.
 

| Paramètre de stratégie                                                                                                   | Expérience recommandée                                                                                                                                                                                                                                               | Valeur par défaut |
| ---------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------- |
| [AutoImportAtFirstRun](https://docs.microsoft.com/deployedge/microsoft-edge-policies#autoimportatfirstrun)             | N’importez pas automatiquement les types de données et les paramètres à partir de l’hérité de Microsoft Edge. Cela évite de modifier les profils des utilisateurs avec des paramètres partagés à partir du Surface Hub.                                                                                                 | 4                 |
| [BackgroundModeEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#backgroundmodeenabled)           | Autorisez les processus Microsoft Edge à continuer à s’exécutent en arrière-plan même après la fermeture de la dernière fenêtre de navigateur, ce qui permet d’accéder plus rapidement aux applications web au cours d’une session.                                                                                                      | 1                 |
| [BrowserAddProfileEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#browseraddprofileenabled)     | N’autorisez pas les utilisateurs à créer de nouveaux profils dans Microsoft Edge. Cela simplifie l’expérience de navigation et de signature.                                                                                                                                                      | 0                 |
| [BrowserGuestModeEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#browserguestmodeenabled)       | Permet à un seul utilisateur de se connecter à Microsoft Edge. Cela simplifie l’expérience de navigation et de la session                                                                                                                                                                | 0                 |
| [BrowserSignin](https://docs.microsoft.com/deployedge/microsoft-edge-policies#browsersignin)                           | Permet aux utilisateurs de profiter des Sign-On (SSO) dans Microsoft Edge. Lorsqu’un utilisateur est inscrit au Surface Hub, ses informations d’identification peuvent circuler vers les sites web pris en charge sans avoir à s’authentifier à nouveau.  | 1                 |
| [ExtensionInstallBlockList](https://docs.microsoft.com/deployedge/microsoft-edge-policies#extensioninstallblocklist)   | Empêche les utilisateurs non administrateurs d’installer de nouvelles extensions dans Microsoft Edge. Pour configurer une liste d’extensions à installer par défaut, utilisez [ExtensionInstallForcelist](https://docs.microsoft.com/deployedge/microsoft-edge-policies#extensioninstallforcelist). | *                 |
| [HideFirstRunExperience](https://docs.microsoft.com/deployedge/microsoft-edge-policies#hidefirstrunexperience)         | Masque l’expérience de première expérience d’affichage et l’écran de départ qui s’affiche normalement lorsque les utilisateurs exécutent Microsoft Edge pour la première fois. Étant donné que le Surface Hub est un appareil partagé, cela simplifie l’expérience utilisateur.                                                                      | 1                 |
| [InPrivateModeAvailability](https://docs.microsoft.com/deployedge/microsoft-edge-policies#inprivatemodeavailability)   | Désactive le mode InPrivate. Étant donné que end Session effacera déjà les données de navigation, cela simplifie l’expérience de navigation et de la session.                                                                                                                                          | 1                 |
| [NewTabPageSetFeedType](https://docs.microsoft.com/deployedge/microsoft-edge-policies#newtabpagesetfeedtype)           | Affiche l’expérience de flux Office 365 sur les nouvelles pages d’onglets. Lorsqu’un utilisateur est inscrit au Surface Hub, cela permet un accès rapide à ses fichiers et à son contenu sur Office 365.                                                                                                        | 1                 |
| [NonRemovableProfileEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#nonremovableprofileenabled) | Lorsqu’un utilisateur est inscrit au Surface Hub, un profil non amovible est créé à l’aide de son compte d’organisation. Cela simplifie l’expérience Sign-On (SSO).                                                                                                 | 1                 |
| [PrintingEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#printingenabled)                       | Désactive l’impression dans Microsoft Edge. Le Surface Hub ne prend pas en charge l’impression.                                                                                                                                                                                              | 0                 |
| [ProActiveAuthEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#proactiveauthenabled)             | Permet à Microsoft Edge d’authentifier de manière proactive les utilisateurs avec les services Microsoft. Cela simplifie l’expérience Sign-On (SSO).                                                                                                                         | 1                 |
| [PromptForDownloadLocation](https://docs.microsoft.com/deployedge/microsoft-edge-policies#promptfordownloadlocation)   | Enregistre automatiquement les fichiers dans le dossier Téléchargements, au lieu de demander aux utilisateurs où enregistrer le fichier. Cela simplifie l’expérience de navigation.                                                                                                                             | 0                 |

> [!IMPORTANT]
> Les applications web progressives déployables ne sont actuellement pas pris en charge sur le système d’exploitation Windows 10 Team.  Notez également que le paramètre de stratégie Microsoft Edge [WebAppInstallForceList n’est](https://docs.microsoft.com/deployedge/microsoft-edge-policies#webappinstallforcelist) pas pris en charge sur le Surface Hub. 

### Configurer les paramètres de stratégie Microsoft Edge

Utilisez [les stratégies de navigateur Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-policies) pour configurer les paramètres de navigateur dans Microsoft Edge. Ces stratégies peuvent être appliquées à l’aide des éléments ci-après :

- [Microsoft Intune](https://docs.microsoft.com/deployedge/configure-edge-with-intune),
- [Votre fournisseur de gestion des périphériques mobiles (MDM) préféré qui prend en charge l’ingestion ADMX,](https://docs.microsoft.com/deployedge/configure-edge-with-mdm)ou
- [Packages d’approvisionnement à l’aide de l’ingestion ADMX dans le Concepteur de configuration Windows.](https://docs.microsoft.com/windows/configuration/wcd/wcd-admxingestion)

 
### Configurer les mises à jour De Microsoft Edge

Par défaut, Microsoft Edge est mis à jour automatiquement. Utilisez [les stratégies de mise à](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies) jour de Microsoft Edge pour configurer les paramètres de Microsoft Edge Update.
Notez que le Surface Hub ne prend pas en charge les stratégies de mise à jour Microsoft Edge suivantes :

- **Allowsxs :** sur Surface Hub, le canal stable Microsoft Edge remplace toujours l’ancien canal Microsoft Edge.
- **CreateDesktopShortcut** – Surface Hub n’utilise pas de raccourcis de bureau.

> [!TIP]
>  MicrosoftEdge nécessite une connectivité à Internet pour prendre en charge ses fonctionnalités. Assurez-vous que les URL de domaine nécessaires sont [ajoutées](https://docs.microsoft.com/deployedge/microsoft-edge-security-endpoints) à la liste d’adresses permises pour garantir les communications par le biais de pare-feu et d’autres mécanismes de sécurité.

## Liens connexes

- [Documentation MicrosoftEdge](https://docs.microsoft.com/microsoft-edge/)

