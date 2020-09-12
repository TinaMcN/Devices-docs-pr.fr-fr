---
title: Installer et configurer le nouveau Microsoft Edge sur SurfaceHub
description: Installez et configurez le nouveau Microsoft Edge sur surface Hub.
keywords: séparer les valeurs par des virgules
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 09/11/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 6de949c7341f9d9bee60f808dab77770377acefc
ms.sourcegitcommit: a64f5f375ebc0611e5735c63afd9540db0f807c4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/11/2020
ms.locfileid: "11013695"
---
# Installer et configurer le nouveau Microsoft Edge sur SurfaceHub

La mise à jour de l’équipe 2020 de Windows 10 prend en charge le nouveau Microsoft Edge basé sur le chrome (version 85 et versions ultérieures) comme navigateur de surface Hub recommandé. Vous pouvez installer Microsoft Edge manuellement à l’aide d’un package de mise à service, à distance à l’aide de Microsoft Intune ou de votre fournisseur de gestion des périphériques mobiles (GPM).

Par défaut, les appareils surface Hub sont préinstallés avec la version 44 de Microsoft Edge.
 
> [!NOTE]
> Si vous avez déjà installé Edge dev, procédez comme suit:
>
>1. Si vous ne connaissez pas la version que vous voulez confirmer, ouvrez votre navigateur Edge et rendez-vous sur edge://version.
>2. Accédez à **surface Hub > gestion des appareils**. Sous **packages de déploiement**, sélectionnez **Ajouter ou supprimer un package de mise à service.**
>3. Si vous avez utilisé le programme d’installation antérieur pour épingler Microsoft Edge dev dans le menu Démarrer, cliquez sur **menu Démarrer personnalisé** dans la liste, puis cliquez sur **Supprimer.**
>4. Si vous avez utilisé une stratégie de disposition de démarrage personnalisée, vous devez la modifier à l’aide du chemin Edge le plus récent, comme décrit dans la section ci-dessous [Afficher Microsoft Edge dans le menu Démarrer de surface Hub](#display-microsoft-edge-in-the-surface-hub-start-menu).
>5. Vous pouvez à présent approvisionner MicrosoftEdgeDevUninstaller. ppkg.
>6. Après la suppression de l’application Edge pour **toutes les applications**, supprimez d’abord «MicrosoftEdgeDevInstaller», puis supprimez «MicrosoftEdgeDevUninstaller».
>7. La désinstallation de Microsoft Edge dev a réussi. Vous pouvez à présent installer la version standard.

 
 
## Installation de Microsoft Edge

### Installer Microsoft Edge à l’aide d’un package de mise à service

1. À partir d’un PC, téléchargez le [package de mise en service de Microsoft Edge](https://aka.ms/HubEdge) (MicrosoftEdgeInstaller. ppkg) dans le dossier racine d’un lecteur USB.
2. Insérez la clé USB dans surface Hub.
3. À partir de surface Hub, ouvrez **paramètres** , puis entrez vos informations d’identification d’administrateur lorsque vous y êtes invité.
4. Accédez à **Surface Hub** > **Gestion des appareils**. Sous **Packages d’approvisionnement**, sélectionnez **Ajouter ou supprimer un package d’approvisionnement**.
5. Sélectionnez **Ajouter un package**.
6. Choisissez le package de mise en service de Microsoft Edge, puis cliquez sur **Ajouter**.
7. Vous verrez un résumé des modifications que le package de mise en service applique. Sélectionner **Oui, l’ajouter**.
8. Attendez la fin de l’installation de Microsoft Edge. Une fois l’installation terminée, accédez au menu Démarrer de surface Hub pour accéder au nouveau Microsoft Edge.              

> [!NOTE]
> Si une nouvelle version de Microsoft Edge est disponible, elle est automatiquement mise à jour.
 
### Installer Microsoft Edge à l’aide de Intune
 
> [!NOTE]
> L’appareil surface hub doit être inscrit et géré à l’aide de Intune. Pour plus d’informations, voir [gérer les éléments de surface Hub 2 avec Microsoft Intune](https://docs.microsoft.com/surface-hub/surface-hub-2s-manage-intune).
 

1. [Téléchargez le programme d’installation de Microsoft Edge de Microsoft](https://www.microsoft.com/edge/business/download).
    - Utiliser la version actuelle du [canal stable](https://docs.microsoft.com/deployedge/microsoft-edge-channels) **(version 85)**
    - Choisir **Windows 64** bits
2. [Ajoutez le programme d’installation de Microsoft Edge en tant qu’application métier à Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/lob-apps-windows).
    - Si vous choisissez d’utiliser Microsoft Edge Update pour gérer les mises à jour automatiques de Microsoft Edge, veillez à configurer le paramètre **ignorer la version** de l’application dans le volet **informations sur l’application** . Lorsque vous basculez ce paramètre sur **Oui**, Microsoft Intune n’applique pas la version de l’application installée sur l’appareil surface Hub.

 
### Installation de Microsoft Edge à l’aide de la gestion des appareils mobiles

1. [Téléchargez le programme d’installation de Microsoft Edge de Microsoft](https://www.microsoft.com/edge/business/download).
    - Utiliser la version actuelle du [canal stable](https://docs.microsoft.com/deployedge/microsoft-edge-channels) **(version 85)**
    - Choisir **Windows 64** bits
2. Étape du programme d’installation de Microsoft Edge sur un emplacement hébergé, tel qu’un partage de fichiers local (\\server\share\MicrosoftEdgeEnterpriseX64.msi). L’appareil surface hub doit être autorisé à accéder à l’emplacement hébergé.
3. Utilisez le [fournisseur de services de configuration EnterpriseDesktopAppManagement](https://docs.microsoft.com/windows/client-management/mdm/enterprisedesktopappmanagement-csp) auprès de votre fournisseur de services de téléphonie mobile pour installer Microsoft Edge.

 

## Configurer MicrosoftEdge

### Stratégies Microsoft Edge par défaut pour surface Hub
Microsoft Edge est préconfiguré avec les stratégies suivantes pour fournir une expérience optimisée pour surface Hub.
 
> [!NOTE]
>  Nous vous recommandons de maintenir la valeur par défaut pour ces stratégies.
 

| Stratégie Microsoft Edge                                                                                                    | Meilleure interface                                                                                                                                                                                                                                               | Valeur par défaut |
| ---------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------- |
| [AutoImportAtFirstRun](https://docs.microsoft.com/deployedge/microsoft-edge-policies#autoimportatfirstrun)             | N’importez pas automatiquement de types de données et de paramètres à partir de l’ancien hérité Microsoft Edge. Cela évite de changer les profils des utilisateurs connectés avec des paramètres partagés à partir de surface Hub.                                                                                                 | n°4                 |
| [BackgroundModeEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#backgroundmodeenabled)           | Autorisez les processus Microsoft Edge à s’exécuter en arrière-plan même après la fermeture de la dernière fenêtre du navigateur, ce qui permet d’accéder plus rapidement aux applications Web lors d’une session.                                                                                                      | 1                 |
| [BrowserAddProfileEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#browseraddprofileenabled)     | Ne pas autoriser les utilisateurs à créer des profils dans Microsoft Edge. Cela simplifie la navigation et l’expertise de connexion.                                                                                                                                                      | 0,4                 |
| [BrowserGuestModeEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#browserguestmodeenabled)       | Autorise un seul utilisateur à se connecter à Microsoft Edge. Cela simplifie la navigation et l’expertise de connexion.                                                                                                                                                                | 0,4                 |
| [BrowserSignin](https://docs.microsoft.com/deployedge/microsoft-edge-policies#browsersignin)                           | Permet aux utilisateurs de profiter de l’authentification unique dans Microsoft Edge. Lorsqu’un utilisateur est connecté à surface Hub, ses informations d’identification peuvent être acheminées vers des sites Web pris en charge sans avoir à s’authentifier de nouveau.  | 1                 |
| [ExtensionInstallBlockList](https://docs.microsoft.com/deployedge/microsoft-edge-policies#extensioninstallblocklist)   | Empêche les utilisateurs non administrateurs d’installer de nouvelles extensions dans Microsoft Edge. Pour configurer une liste d’extensions à installer par défaut, utilisez [ExtensionInstallForcelist](https://docs.microsoft.com/deployedge/microsoft-edge-policies#extensioninstallforcelist). | *                 |
| [HideFirstRunExperience](https://docs.microsoft.com/deployedge/microsoft-edge-policies#hidefirstrunexperience)         | Masque la première utilisation et l’écran de démarrage qui s’affichent normalement lorsque les utilisateurs exécutent Microsoft Edge pour la première fois. Dans la mesure où surface Hub est un périphérique partagé, cela permet de simplifier l’utilisation de l’utilisateur.                                                                      | 1                 |
| [InPrivateModeAvailability](https://docs.microsoft.com/deployedge/microsoft-edge-policies#inprivatemodeavailability)   | Désactive le mode InPrivate. Dans la mesure où l’opération de fin de session efface déjà les données de navigation, cela simplifie la navigation et l’activation de la fonctionnalité de connexion.                                                                                                                                          | 1                 |
| [NewTabPageSetFeedType](https://docs.microsoft.com/deployedge/microsoft-edge-policies#newtabpagesetfeedtype)           | Affiche l’interface de flux d’Office 365 sur les nouvelles pages d’onglets. Lorsqu’un utilisateur est connecté à surface Hub, cela permet un accès rapide à leurs fichiers et contenus sur Office 365.                                                                                                        | 1                 |
| [NonRemovableProfileEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#nonremovableprofileenabled) | Lorsqu’un utilisateur est connecté à surface Hub, un profil non amovible est créé à l’aide de son compte professionnel. Cela simplifie l’interface de l’authentification unique (SSO).                                                                                                 | 1                 |
| [PrintingEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#printingenabled)                       | Désactive l’impression dans Microsoft Edge. Surface Hub ne prend pas en charge l’impression.                                                                                                                                                                                              | 0,4                 |
| [ProActiveAuthEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#proactiveauthenabled)             | Permet à Microsoft Edge d’authentifier de manière proactive des utilisateurs de connexion avec les services Microsoft. Cela simplifie l’interface de l’authentification unique (SSO).                                                                                                                         | 1                 |
| [PromptForDownloadLocation](https://docs.microsoft.com/deployedge/microsoft-edge-policies#promptfordownloadlocation)   | Enregistre automatiquement les fichiers dans le dossier téléchargements au lieu de demander aux utilisateurs où enregistrer le fichier. Cela simplifie l’interface de navigation.                                                                                                                             | 0,4                 |

> [!IMPORTANT]
> Les applications Web progressives en déploiement (PWAs) ne sont actuellement pas prises en charge sur le système d’exploitation Windows 10.  Notez également que le paramètre de stratégie Microsoft Edge [WebAppInstallForceList](https://docs.microsoft.com/deployedge/microsoft-edge-policies#webappinstallforcelist) n’est pas pris en charge sur surface Hub. 

### Configurer les paramètres de stratégie Microsoft Edge

Utilisez les [stratégies de navigateur Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-policies) pour configurer les paramètres du navigateur dans Microsoft Edge. Ces stratégies peuvent être appliquées à l’aide de:

- [Microsoft Intune](https://docs.microsoft.com/deployedge/configure-edge-with-intune),
- [Votre fournisseur de gestion des périphériques mobiles (GPM) préféré prenant en charge l’intégration de ADMX](https://docs.microsoft.com/deployedge/configure-edge-with-mdm)ou
- [Mise en service des packages à l’aide de l’intégration ADMX dans le concepteur de configuration Windows](https://docs.microsoft.com/windows/configuration/wcd/wcd-admxingestion).

 
### Configurer les mises à jour de Microsoft Edge

Par défaut, Microsoft Edge est mis à jour automatiquement. Utilisez les [stratégies Microsoft Edge Update](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies) pour configurer les paramètres de mise à jour de Microsoft Edge.
Notez que surface Hub ne prend pas en charge les stratégies de mise à jour Microsoft Edge suivantes:

- **Allowsxs** : sur surface Hub, le canal stable Microsoft Edge remplace toujours l’ancien.
- **CreateDesktopShortcut** – surface Hub n’utilise aucun raccourci sur le bureau.

> [!NOTE]
>  MicrosoftEdge nécessite une connectivité à Internet pour prendre en charge ses fonctionnalités. Assurez-vous que les [URL de domaine nécessaires](https://docs.microsoft.com/deployedge/microsoft-edge-security-endpoints) sont ajoutées à la liste verte pour garantir des communications par le biais de pare-feu et d’autres mécanismes de sécurité.
 
### Afficher Microsoft Edge dans le menu Démarrer de surface Hub

Si vous utilisez la disposition du menu démarrer par défaut, vous pouvez installer le menu Démarrer avec le package de mise en service de Microsoft Edge pour ajouter Microsoft Edge en tant qu’application épinglée.
Si vous voulez appliquer une mise en page de menu de démarrage personnalisée, utilisez le code XML suivant pour ajouter une vignette épinglée à Microsoft Edge.

```xml

<start:DesktopApplicationTile

DesktopApplicationLinkPath="C:\Program Files (x86)\Microsoft\Edge\Application\msedge.exe"

Size="2x2"

Row="0"

Column="0"/>
```

Pour plus d’informations, voir [configurer le menu Démarrer de surface Hub](https://docs.microsoft.com/surface-hub/surface-hub-start-menu).
 
> [!NOTE]
> Le nouveau Microsoft Edge ne prend pas en charge les liens et sites Web épinglés à l’aide de SecondaryTiles.

## Liens connexes

- [Documentation Microsoft Edge](https://docs.microsoft.com/microsoft-edge/).

