---
title: Installer des applications sur le Microsoft Surface Hub
description: Les administrateurs peuvent installer des applications à partir du MicrosoftStore ou du MicrosoftStore pour Entreprises.
ms.assetid: 3885CB45-D496-4424-8533-C9E3D0EDFD94
ms.reviewer: ''
manager: laurawi
keywords: installer des applications, MicrosoftStore, MicrosoftStore pour Entreprises
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 10/23/2018
ms.localizationpriority: medium
audience: ITPro
ms.openlocfilehash: 462b76451bd12547d1c1560054a51bb88c218f96
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10833353"
---
# Installer des applications sur le Microsoft SurfaceHub

Vous pouvez installer des applications supplémentaires sur votre SurfaceHub en fonction des besoins de votre équipe ou de votre organisation. Différentes méthodes permettent d’installer des applications selon que vous développez et testez une application ou déployez une application finale. Cette rubrique décrit les méthodes d’installation des applications pour chaque scénario.

Quelques éléments à connaître des applications sur le SurfaceHub:
- Le SurfaceHub exécute uniquement des [applications de plateforme Windows universelle (UWP)](https://msdn.microsoft.com/windows/uwp/get-started/whats-a-uwp). Les applications créées à l’aide de [Desktop App Converter](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-run-desktop-app-converter) ne s’exécuteront pas sur le Surface Hub.
- Les applications doivent être ciblées pour la [famille d’appareils universels](https://msdn.microsoft.com/library/windows/apps/dn894631) ou la famille d'appareils Windows.
- Surface Hub ne prend en charge que les [applications sous licence hors connexion](https://docs.microsoft.com/microsoft-store/distribute-offline-apps) de la [Boutique Microsoft pour les entreprises](https://businessstore.microsoft.com/store).
- Par défaut, les applications doivent être signées par le WindowsStore pour être installées. Au cours des phases de test et de développement, vous pouvez également choisir d’exécuter des applicationsUWP signées par le développeur en plaçant l’appareil en mode développeur.
- Lorsque vous soumettez une application au Microsoft Store, les développeurs doivent définir la disponibilité de la famille d’appareils et les options de gestion des licences organisationnelles pour s’assurer qu’une application sera disponible pour être exécutée sur surface Hub.
- Vous avez besoin des informations d’identification d’administrateur pour installer des applications sur votre SurfaceHub. Étant donné que l’appareil est conçu pour être utilisé dans des espaces communs comme des salles de réunion, ses utilisateurs ne pourront pas accéder au MicrosoftStore pour télécharger et installer des applications.


## Développer et tester des applications
Lorsque vous développez votre propre application, quelques options sont à votre disposition pour tester des applications sur le SurfaceHub.

### Mode développeur
Par défaut, le SurfaceHub n’exécute que les applicationsUWP qui ont été publiées sur le MicrosoftStore et signées par ce dernier. Les applications soumises au MicrosoftStore font l’objet de tests de sécurité et de conformité dans le cadre du [processus de certification d’application](https://msdn.microsoft.com/windows/uwp/publish/the-app-certification-process); votre SurfaceHub est ainsi protégé contre les applications malveillantes.
 
En activant le mode développeur, vous pouvez également installer des applicationsUWP signées par le développeur.
 
> [!IMPORTANT]
> Une fois le mode développeur activé, vous devez réinitialiser le SurfaceHub pour le désactiver. La réinitialisation de l’appareil supprime l’ensemble des configurations et des fichiers utilisateur locaux, puis réinstalle Windows.

**Pour activer le mode développeur** 
1. À partir de votre SurfaceHub, démarrez **Paramètres**.
2. Entrez les informations d’identification d’administrateur de l’appareil lorsque vous y êtes invité.
3. Accédez à **Mise à jour et sécurité** > **Pour les développeurs**.
4. Sélectionnez **Mode développeur** et acceptez le message d’avertissement.

### VisualStudio
Pendant le développement, le moyen le plus simple de tester votre application sur un SurfaceHub consiste à utiliser VisualStudio. La fonctionnalité de débogage à distance de VisualStudio vous permet de détecter les problèmes de votre application avant de la déployer. Pour plus d’informations, voir [Tester les applications de SurfaceHub à l’aide de VisualStudio](https://msdn.microsoft.com/windows/uwp/debug-test-perf/test-surface-hub-apps-using-visual-studio).

### Package d’approvisionnement
Utilisez VisualStudio pour [créer un package d’application](https://msdn.microsoft.com/library/windows/apps/hh454036.aspx) pour votre applicationUWP, signée à l’aide d’un certificat de test. Utilisez ensuite le Concepteur de configuration et d’acquisition d’images (ICD) Windows pour créer un package d’approvisionnement contenant le package d’application. Pour plus d’informations, voir [Créer des packages de mise en service (SurfaceHub)](provisioning-packages-for-certificates-surface-hub.md).


## Soumettre des applications au MicrosoftStore
Une fois qu’une application est prête à être publiée, les développeurs doivent la soumettre et la publier sur le MicrosoftStore. Pour plus d’informations, voir [Publier des applications Windows](https://developer.microsoft.com/store/publish-apps).

Lors de la soumission d’une application, les développeurs doivent définir la **disponibilité de la famille d’appareils** et les options **Gestion des licences organisationnelles** pour s’assurer que l’application pourra s’exécuter sur le SurfaceHub.

**Pour définir la disponibilité de la famille d’appareils**  
1. Dans le [Centre de développement Windows](https://developer.microsoft.com), accédez à la page de soumission de votre application.
2. Sélectionnez **Packages**.
3. Sous **Disponibilité de la famille d’appareils**, sélectionnez les options suivantes:
    
    - **Windows 10 Collaboration**
    - **Laisser à Microsoft le soin de décider si l’application sera disponible pour les familles d’appareils à venir**
  
![Image illustrant la page Disponibilité de la famille d’appareils (partie du processus de soumission d’applications au MicrosoftStore).](images/device-family.png)  
    
Pour plus d’informations, voir [Disponibilité de la famille d’appareils](https://msdn.microsoft.com/windows/uwp/publish/upload-app-packages#device-family-availability).

**Pour définir la gestion des licences organisationnelles**
1. Dans le [Centre de développement Windows](https://developer.microsoft.com), accédez à la page de soumission de votre application.
2. Sélectionnez **Tarification et disponibilité**.
3. Sous Gestion des licences organisationnelles, sélectionnez **Permettre aux entreprises d’acheter des licences en mode hors connexion**.

![Image illustrant la page Gestion des licences organisationnelles (partie du processus de soumission d’applications au MicrosoftStore).](images/sh-org-licensing.png)

> [!NOTE]
> Par défaut, la case **Proposer mon application aux organisations via le service de gestion de licences et de distribution (en ligne) du WindowsStore** est cochée.

> [!NOTE]
> Les développeurs peuvent également publier des applications métier directement pour les entreprises sans les rendre disponibles à grande échelle dans le WindowsStore. Pour plus d’informations, voir [Distribuer des applications métier aux entreprises](https://msdn.microsoft.com/windows/uwp/publish/distribute-lob-apps-to-enterprises).

Pour plus d’informations, voir [Options de gestion des licences organisationnelles](https://msdn.microsoft.com/windows/uwp/publish/organizational-licensing).


## Déployer des applications publiées

Plusieurs options permettent d’installer les applications qui ont été publiées dans le MicrosoftStore, selon que vous voulez les évaluer sur quelques appareils ou les déployer dans votre organisation.

Pour installer des applications publiées:
- Téléchargez l’application à l’aide de l’application du MicrosoftStore, ou
- Téléchargez le package d’application à partir du MicrosoftStore pour Entreprises et distribuez-le à l’aide d’un package d’approvisionnement ou d’un fournisseurGPM pris en charge.

### Application du MicrosoftStore
Pour évaluer les applications publiées sur le MicrosoftStore, utilisez l’application du MicrosoftStore sur le SurfaceHub pour rechercher et télécharger des applications.

> [!NOTE]
> Utiliser l’application du MicrosoftStore n’est pas recommandé pour déployer des applications à l’échelle de votre organisation:
> - Pour télécharger des applications, vous devez vous connecter à l’application du MicrosoftStore avec un compte Microsoft ou un compte professionnel. Toutefois, vous ne pouvez connecter un compte qu’à un maximum de 10appareils à la fois. Si vous possédez plus de 10SurfaceHub, vous devez créer plusieurs comptes ou supprimer des appareils de votre compte entre les installations d’application.
> - Pour installer des applications, vous devez vous connecter manuellement à l’application du MicrosoftStore sur chaque SurfaceHub que vous possédez.

**Pour parcourir le MicrosoftStore sur le SurfaceHub** 
1. À partir de votre SurfaceHub, démarrez **Paramètres**.
2. Entrez les informations d’identification d’administrateur de l’appareil lorsque vous y êtes invité.
3. Accédez à **Cet appareil** > **Applications et fonctionnalités**.
4. Sélectionnez **Ouvrir le Store**.

### Télécharger des packages d’application à partir du MicrosoftStore pour Entreprises
Pour télécharger le package d’application, vous devez installer des applications sur votre SurfaceHub, puis visiter le [MicrosoftStore pour Entreprises](https://www.microsoft.com/business-store). Le WindowsStore pour Entreprises est l’emplacement où vous pouvez rechercher, acquérir et gérer des applications pour les appareils Windows10 de votre organisation, notamment le SurfaceHub.
 
> [!NOTE]
> Pour le moment, le SurfaceHub ne prend en charge que les applications sous licence hors connexion, disponibles via le WindowsStore pour Entreprises. Les développeurs des applications définissent la disponibilité des licences hors connexion lorsqu’ils soumettent leurs applications.

Recherchez et acquérez l’application souhaitée, puis téléchargez:
- le package d’application sous licence hors connexion (fichier .appx ou .appxbundle);
- le fichier de licence *non codée* (si vous utilisez des packages d’approvisionnement pour installer l’application);
- le fichier de licence *codée* (si vous utilisezGPM pour distribuer l’application);
- tous les fichiers de dépendance nécessaires.

Pour plus d’informations, voir [Télécharger une application avec licence hors connexion](https://technet.microsoft.com/itpro/windows/manage/distribute-offline-apps#download-an-offline-licensed-app).

### Package d’approvisionnement
Vous pouvez installer manuellement les applications sous licence hors connexion que vous avez téléchargées à partir du WindowsStore pour Entreprises sur quelques SurfaceHub à l’aide de packages d’approvisionnement. Utilisez le Concepteur de configuration et d’acquisition d’images (ICD) Windows pour créer un package d’approvisionnement contenant le package d’application et le fichier de licence *non codée* que vous avez téléchargés à partir du WindowsStore pour Entreprises. Pour plus d’informations, voir [Créer des packages de mise en service (SurfaceHub)](provisioning-packages-for-certificates-surface-hub.md).

### FournisseurGPM pris en charge
Pour déployer des applications sur plusieurs SurfaceHub de votre organisation, utilisez un fournisseurGPM pris en charge. Le tableau ci-dessous présente les fournisseursGPM qui prennent en charge le déploiement de packages d’application sous licence hors connexion.

| FournisseurGPM                | Prend en charge les packages d’application sous licence hors connexion |
|-----------------------------|----------------------------------------|
| MDM locale avec Configuration Manager (à partir de la version 1602) | Oui |
|
| FournisseurGPM tiers    | Vérifiez que votre fournisseurGPM prend en charge le déploiement des packages d’application sous licence hors connexion. |

**Pour déployer des applications à distance à l’aide de Microsoft Endpoint Configuration Manager**

> [!NOTE]
> Ces instructions sont basées sur la branche actuelle du gestionnaire de configuration de points de terminaison Microsoft.

1. Inscrivez votre surface hubs dans Configuration Manager. Pour plus d’informations, voir [Inscrire un SurfaceHub dans GPM](manage-settings-with-mdm-for-surface-hub.md#enroll-into-mdm).
2. Téléchargez le package d’application sous licence hors connexion, le fichier de licence *codée* et les fichiers de dépendance nécessaires à partir du WindowsStore pour Entreprises. Pour plus d’informations, voir [Télécharger une application avec licence hors connexion](https://technet.microsoft.com/itpro/windows/manage/distribute-offline-apps#download-an-offline-licensed-app). Placez les fichiers téléchargés dans le même dossier d’un partage réseau.
3. Dans l’espace de travail **Bibliothèque de logiciels** de la console Configuration Manager, cliquez sur **Vue d’ensemble** > **Gestion des applications** > **Applications**.
4. Dans l’onglet **Accueil**, dans le groupe **Créer**, cliquez sur **Créer une application**.
5. Dans la page **Général** de l’**Assistant Création d’une application**, cochez la case **Détecter automatiquement les informations de cette application à partir des fichiers d’installation**.
6. Dans la liste déroulante **Type**, sélectionnez **Package d’application Windows (\*.appx, \*.appxbundle)**.
7. Dans le champ **Emplacement**, spécifiez le chemin d’accèsUNC, sous la forme \\serveur\partage\\nom_fichier, du package d’application sous licence hors connexion que vous avez téléchargé à partir du WindowsStore pour Entreprises. Vous pouvez également cliquer sur **Parcourir** pour accéder au package d’application.
8. Dans la page **Importer des informations**, passez en revue les informations importées, puis cliquez sur **Suivant**. Si nécessaire, vous pouvez cliquer sur **Précédent** pour revenir en arrière et corriger les éventuelles erreurs.
9. Dans la page **Informations générales**, complétez les informations supplémentaires sur l’application. Certaines de ces informations peuvent déjà être renseignées si elles ont été obtenues automatiquement à partir du package d’application.
10. Cliquez sur **Suivant**, passez en revue les informations d’application dans la page Résumé, puis terminez l’Assistant Création d’une application. 
11. Créez un type de déploiement pour l’application. Pour plus d’informations, voir [Créer des types de déploiement pour l’application](https://docs.microsoft.com/sccm/apps/deploy-use/create-applications#create-deployment-types-for-the-application).
12. Déployez l’application sur vos SurfaceHub. Pour plus d’informations, voir [déployer des applications avec Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/sccm/apps/deploy-use/deploy-applications).
13. Au besoin, mettez à jour l’application en téléchargeant un nouveau package à partir du WindowsStore pour Entreprises et en publiant une révision de l’application dans ConfigurationManager. Pour plus d’informations, reportez-vous [à mettre à jour et supprimer des applications avec Microsoft Endpoint Configuration Manager](https://technet.microsoft.com/library/mt595704.aspx). 

> [!NOTE] 
> Si vous utilisez Microsoft Endpoint Configuration Manager (succursale actuelle), vous pouvez ignorer les étapes ci-dessus en connectant le Windows Store pour les entreprises à la Configuration Manager. Ainsi, vous pouvez synchroniser la liste des applications que vous avez achetées avec Configuration Manager, les voir dans la console Configuration Manager et les déployer comme vous le feriez avec une autre application. Pour plus d’informations, voir [gérer des applications à partir du Microsoft Store pour les entreprises avec Configuration Manager](https://technet.microsoft.com/library/mt740630.aspx).


## Résumé

Plusieurs méthodes s’offrent à vous pour installer des applications sur votre surface Hub en fonction du développement d’applications, de l’évaluation d’applications sur un petit nombre d’appareils ou du déploiement d’applications à grande échelle pour votre organisation. Ce tableau récapitule les méthodes prises en charge:

| Méthode d’installation             | Développement d’applications | Évaluation des applications sur <br> quelques appareils | Déploiement d’applications à grande échelle <br> dans votre organisation |
| -------------------------- | --------------- | ------------------------------------- | ---------------------- |
| VisualStudio              | X |   |   |
| Package d’approvisionnement       | X | X |   |
| Application du MicrosoftStore          |   | X |   |
| FournisseurGPM pris en charge     |   |   | X |

## Plus d’informations

- [Billet de blog: déployer des applications du MicrosoftStore sur Surface Hub à l’aide de Intune](https://blogs.technet.microsoft.com/y0av/2018/01/18/7-2/)


## Rubriquesassociées

[Gérer le Microsoft SurfaceHub](manage-surface-hub.md)

[Guide de l’administrateur Microsoft Surface Hub](surface-hub-administrators-guide.md)

 

 





