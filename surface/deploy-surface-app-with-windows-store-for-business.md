---
title: Déployer une application Surface avec Microsoft Store pour Entreprises ou Microsoft Store pour Éducation (Surface)
description: Découvrez comment ajouter et télécharger l’application Surface avec Microsoft Store pour Entreprises ou Microsoft Store pour Éducation, ainsi que l’installation de l’application Surface avec PowerShell et MDT.
keywords: application surface, application, déploiement, personnaliser
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, store
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
ms.audience: itpro
ms.reviewer: ''
manager: laurawi
ms.date: 1/15/2021
ms.openlocfilehash: 87e24bcfa1e2d4ab05d24a05b203fea92637d3f4
ms.sourcegitcommit: 1b86286bd13b13749ddbf454ae78d9a24fec44ee
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "11271071"
---
# Déployer une application Surface avec Microsoft Store pour Entreprises et Éducation

**S'applique à**

- Surface Pro 7+
- Surface Laptop Go
- SurfacePro7
- Surface Laptop3
- SurfacePro6
- Surface Laptop2
- SurfaceGo
- Surface Go avec LTE
- SurfaceBook2
- SurfacePro avec LTE Advanced (modèle1807)
- SurfacePro (modèle1796)
- Surface Laptop
- SurfaceStudio
- Surface Studio2
- SurfaceBook
- Surface Pro4
- VersionsLTE du modèleSurface3
- Surface3
- Surface Pro3


L’application Surface est une application légère du Microsoft Store qui permet de contrôler de nombreux paramètres et options propres à Surface, notamment : 

* Activer ou désactiver le boutonWindows sur l’appareilSurface 

* Ajuster la sensibilité du styletSurface 

* Personnaliser les actions des boutons des styletsSurface 

* Activer ou désactiver les améliorations audio de l’appareilSurface 

* Accès rapide à la documentation et aux informations de prise en charge de votre appareil

Les clients qui utilisent Windows Update reçoivent généralement l’application Surface dans le cadre des mises à jour automatiques. Toutefois, si votre organisation prépare des images pour le déploiement sur vos appareils Surface, vous pouvez inclure l’application Surface (anciennement appelée Surface Hub) dans votre processus d’imagerie et de déploiement au lieu de demander aux utilisateurs de chaque appareil individuel de télécharger et d’installer l’application à partir du Microsoft Store ou de votre Microsoft Store pour Entreprises. 

> [!NOTE]
> Cet article ne s’applique pas à Surface Pro X. Pour plus d’informations, voir [Déploiement, gestion et maintenance de Surface Pro X](surface-pro-arm-app-management.md)

## Vue d’ensemble de l’application Surface

L’application Surface est disponible en téléchargement gratuit à partir du [Microsoft Store.](https://www.microsoft.com/store/apps/Surface/9WZDNCRFJB8P) Les utilisateurs peuvent le télécharger et l’installer à partir du Microsoft Store, mais si votre organisation utilise plutôt Microsoft Store pour Entreprises, vous devrez l’ajouter à l’inventaire de votre magasin et éventuellement inclure l’application dans le cadre de votre processus de déploiement de Windows. Ces processus sont décrits tout au long de cet article. Pour plus d’informations sur Microsoft Store pour Entreprises, voir [Microsoft Store](https://docs.microsoft.com/microsoft-store/) pour Entreprises dans le TechCenter Windows. 

## Ajouter une application Surface à un compte Microsoft Store pour Entreprises 

Avant que les utilisateurs ne peuvent installer ou déployer une application à partir du compte Microsoft Store pour Entreprises d’une entreprise, les applications souhaitées doivent d’abord être disponibles et sous licence pour les utilisateurs d’une entreprise. 

1. Si ce n’est pas déjà fait, créez un [compte Microsoft Store pour Entreprises.](https://www.microsoft.com/business-store) 

2. Connectez-vous au portail. 

3. Activez la gestion des licences hors connexion : cliquez sur Gérer **les paramètres du**Windows Store >, puis sélectionnez Afficher les applications sous licence hors connexion pour les achats dans la case à cocher du **Store,** comme le montre la figure 1. Pour plus d’informations sur les modèles de licence d’application du Microsoft Store pour Entreprises, voir Applications dans [Microsoft Store pour Entreprises et Éducation.](https://docs.microsoft.com/microsoft-store/)

   > [!div class="mx-imgBorder"]
   > ![Afficher la case à cocher des applications de licences hors connexion](images/deploysurfapp-figure1-enablingapps.png "Show offline licenses apps checkbox")<br/>
   *Figure1. Activer les applications pour une utilisation hors connexion*

4. Ajoutez l’application Surface à votre compte Microsoft Store pour Entreprises en suivant cette procédure :

    * Cliquez sur le menu **Magasin.**
    
    * Dans la zone de recherche, tapez **Application Surface,** puis cliquez sur l’icône de recherche.
    
    * Une fois l’application Surface présentée dans les résultats de la recherche, cliquez sur l’icône de l’application.
    
    * Un choix s’affiche (sélectionnez **En ligne** ou Hors **connexion),** comme le montre la figure 2.
    
      > [!div class="mx-imgBorder"]
      > ![Sélectionnez le mode de licence hors connexion et ajoutez l’application à votre inventaire](images/deploysurfapp-fig2-selectingofflinelicense.png "Select the Offline licensing mode and add the app to your inventory")   
      *Figure2. Sélectionnez le mode de licence hors connexion et ajoutez l’application à votre inventaire*
    
    * Cliquez **sur Hors connexion** pour sélectionner le mode de licence hors connexion.
    
    * Cliquez **sur Obtenir l’application** pour l’ajouter à votre inventaire du Microsoft Store pour Entreprises. Comme le montre la figure 3, une boîte de dialogue vous invite à reconnaître que les applications hors connexion peuvent être déployées à l’aide d’un outil de gestion ou téléchargées à partir de la page d’inventaire de l’entreprise dans leur magasin privé.
    
      > [!div class="mx-imgBorder"]
      > ![Fenêtre d’accusé de réception d’application avec licence hors connexion ](images/deploysurfapp-fig3-acknowledge.png "Offline-licensed app acknowledgement window")
       *Figure 3. Accusé de réception d’application avec licence hors connexion*
      
    * Cliquez sur **OK**.

## Télécharger l’application Surface à partir d’un compte Microsoft Store pour Entreprises
Après avoir ajouté une application au compte Microsoft Store pour Entreprises en mode hors connexion, vous pouvez télécharger et ajouter l’application en tant qu’AppxBundle à un partage de déploiement.

1. Connectez-vous au compte Microsoft Store pour Entreprises à l’aide de https://businessstore.microsoft.com .

2. Cliquez **sur Gérer les >applications & logiciel.** Une liste de toutes les applications de votre entreprise s’affiche, y compris l’application Surface que vous avez ajoutée dans la section Ajouter une application Surface à un compte [Microsoft Store](#add-surface-app-to-a-microsoft-store-for-business-account) pour Entreprises de cet article.

3. Sous **Actions,** cliquez sur les ellipses (**...**), puis cliquez sur **Télécharger** pour une utilisation hors connexion pour l’application Surface.

4. Sélectionnez les options **de** plateforme et **d’architecture** souhaitées parmi les sélections disponibles pour l’application sélectionnée, comme le montre la figure 4.

    > [!div class="mx-imgBorder"]
    > ![Exemple de package AppxBundle](images/deploysurfapp-fig4-downloadappxbundle.png "Example of the AppxBundle package")<br/>
    *Figure4. Télécharger le package AppxBundle pour une application*
    
5. Cliquez **sur Télécharger.** Le package AppxBundle sera téléchargé. Assurez-vous de noter le chemin d’accès du fichier téléchargé, car vous en aurez besoin plus loin dans cet article.

6. Cliquez sur **l’option** de licence codée ou non **codée.** Utilisez l’option de licence codée avec des outils de gestion tels que Microsoft Endpoint Configuration Manager ou lorsque vous utilisez le Concepteur de configuration Windows pour créer un package d’approvisionnement. Sélectionnez l’option de licence non codée lorsque vous utilisez la gestion et la maintenance des images de déploiement (DISM) ou des solutions de déploiement basées sur l’imagerie, y compris microsoft Deployment Shared Computer Toolkit (MDT).

7. Cliquez **sur Générer** pour générer et télécharger la licence de l’application. Assurez-vous de noter le chemin d’accès du fichier de licence, car vous en aurez besoin plus loin dans cet article.

>[!NOTE]
>Lorsque vous téléchargez une application pour une utilisation hors connexion, telle que l’application Surface, vous remarquerez peut-être une section en bas de la page libellée **Infrastructure requise.** Les infrastructure de vos ordinateurs cibles doivent être installées pour que l’application s’exécute, vous devrez peut-être répéter le processus de téléchargement pour chacune des infrastructure requises pour votre architecture (x86 ou x64) et les inclure également dans le cadre de votre déploiement Windows décrit plus loin dans cet article.

La figure 5 illustre les frameworks requis pour l’application Surface.

> [!div class="mx-imgBorder"]
> ![Infrastructure requise pour l’application Surface](images/deploysurfapp-fig5-requiredframework.png "Required frameworks for the Surface app")<br/>
*Figure5. Infrastructure requise pour l’application Surface*

>[!NOTE]
>Les numéros de version de l’application Surface et les frameworks requis changent au cours de la mise à jour des applications. Recherchez la dernière version de l’application Surface et chaque infrastructure du Microsoft Store pour Entreprises. Utilisez toujours l’application Surface et les versions d’infrastructure recommandées telles que fournies par le Microsoft Store pour Entreprises. L’utilisation d’infrastructure obsolètes ou de versions incorrectes peut entraîner des erreurs ou des pannes d’application.

Pour télécharger les frameworks requis pour l’application Surface, suivez les étapes suivantes :

1. Cliquez sur **le** bouton Télécharger **sous Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe**. Cette application télécharge Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe. Fichier Appx dans le dossier spécifié.

2. Cliquez sur **le** bouton Télécharger **sous Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe**. Cela télécharge le fichier Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe.Appx dans votre dossier spécifié.

>[!NOTE]
>Seule la version 64 bits (x64) de chaque infrastructure est requise pour les appareils Surface. Les appareils Surface sont des appareils UEFI 64 bits natifs et ne sont pas compatibles avec les versions 32 bits (x86) de Windows qui nécessitent des infrastructure 32 bits. 

## Installer l’application Surface sur votre ordinateur avec PowerShell
La procédure suivante met en place l’application Surface sur votre ordinateur et la met à disposition pour tous les comptes d’utilisateur créés sur l’ordinateur par la suite.

1. À l’aide de la procédure décrite dans la section Comment télécharger l’application Surface à partir d’un compte [Microsoft Store](#download-surface-app-from-a-microsoft-store-for-business-account) pour Entreprises de cet article, téléchargez le fichier de licence et AppxBundle de l’application Surface. 

2. Lancez une sessionPowerShell avec élévation des privilèges.

    >[!NOTE]
    >Si vous n’exécutez pas PowerShell en tant qu’administrateur, la session ne sera pas autorisée à installer l’application.
    
3. Dans la sessionPowerShell avec élévation de privilèges, copiez et collez la commande suivante:

    ```powershell
    Add-AppxProvisionedPackage –Online –PackagePath <DownloadPath>\ Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle –LicensePath <DownloadPath>\ Microsoft.SurfaceHub_8wekyb3d8bbwe_a53ef8ab-9dbd-dec1-46c5-7b664d4dd003.xml
    ```

    Où se trouve le dossier dans lequel vous avez téléchargé le fichier appxBundle et le fichier de licence à partir `<DownloadPath>` du compte Microsoft Store pour Entreprises.

    Par exemple, si vous avez téléchargé les fichiers dans c:\Temp, la commande que vous exécutez est :
    
    ```powershell
    Add-AppxProvisionedPackage –Online –PackagePath c:\Temp\ Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle –LicensePath c:\Temp\ Microsoft.SurfaceHub_8wekyb3d8bbwe_a53ef8ab-9dbd-dec1-46c5-7b664d4dd003.xml
    ```

4. L’applicationSurface est désormais disponible sur votre ordinateurWindows actuel. 

   Avant que l’application Surface soit fonctionnelle sur l’ordinateur sur lequel elle a été mise en service, vous devez également mettre en service les infrastructure décrites plus tôt dans cet article. Pour mettre en service ces infrastructure, utilisez la procédure suivante dans la session PowerShell avec élévation de niveaux que vous avez utilisée pour mettre en service l’application Surface.

5. Dans la sessionPowerShell avec élévation de privilèges, copiez et collez la commande suivante:

   ```powershell
   Add-AppxProvisionedPackage –Online –SkipLicense –PackagePath <DownloadPath>\Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe.Appx
   ```
   
6. Dans la sessionPowerShell avec élévation de privilèges, copiez et collez la commande suivante:

   ```powershell
   Add-AppxProvisionedPackage –Online –SkipLicense –PackagePath <DownloadPath>\Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe.Appx
   ```

## Installer l’application Surface avec MDT
La procédure suivante utilise MDT pour automatiser l’installation de l’application Surface au moment du déploiement. L’application est automatiquement provisionnée par MDT au cours du déploiement. Ainsi, vous pouvez utiliser ce processus avec des images existantes. Il s’agit du processus recommandé pour déployer l’application Surface dans le cadre d’un déploiement Windows sur des appareils Surface, car il ne réduit pas la compatibilité entre les plateformes de l’image Windows.

1. À l’aide de la procédure [décrite plus tôt dans cet article,](#download-surface-app-from-a-microsoft-store-for-business-account)téléchargez le fichier de licence et appxBundle de l’application Surface. 

2. À l’aide de l’Assistant Nouvelle application dans MDT Deployment Workbench, importez les fichiers téléchargés en tant que nouvelle **application avec des fichiers sources.**

3. Dans la page **Détails** de la commande **** de l’Assistant **** Nouvelle application, spécifiez le répertoire de travail par défaut et, pour la commande, spécifiez le nom de fichier appxBundle, comme suit :

   * Commande :
   
     ```console
     Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle
     ```
     
   * Répertoire de travail : %DEPLOYROOT%\Applications\SurfaceApp

Pour que l’application Surface fonctionne sur l’ordinateur cible, elle nécessite également les frameworks décrits plus tôt dans cet article. Utilisez la procédure suivante pour importer les frameworks requis pour l’application Surface dans MDT et les configurer en tant que dépendances.

1. À l’aide de la procédure décrite plus tôt dans cet article, téléchargez les fichiers d’infrastructure. Stockez chaque infrastructure dans un dossier distinct.

2. À l’aide de l’Assistant Nouvelle application dans MDT Deployment Workbench, importez les fichiers téléchargés en tant que nouvelle **application avec des fichiers sources.**

3. Dans la page **Détails de la** commande, tapez **** le nom de fichier de chaque application que vous avez téléchargée dans le champ Commande et le répertoire de travail par défaut.

Pour configurer les frameworks en tant que dépendances de l’application Surface, utilisez ce processus :

1. Ouvrez les propriétés de l’application Surface dans MDT Deployment Workbench.

2. Cliquez sur **l’onglet Dépendances,** puis cliquez sur **Ajouter.**

3. Cochez la case pour chaque infrastructure à l’aide du nom que vous avez fourni dans l’Assistant Nouvelle application.

Après l’importation, l’application Surface sera disponible pour sélection à l’étape **Applications** de l’Assistant Déploiement de Windows. Vous pouvez également lancer l’installation automatique de l’application en la spécifiant dans la séquence de tâches de déploiement, via la procédure suivante:

1. Ouvrez la séquence de tâches de déploiement dans MDTDeploymentWorkbench.

2. Ajoutez une nouvelle tâche **Installer l’application** dans la section **Restauration de l’état** du déploiement.

3. Sélectionnez **Installer une application unique** et spécifiez **l’application Surface en** tant qu’application à **installer.**

Pour plus d’informations sur l’utilisation d’applications dans vos déploiements Windows, voir [Déployer Windows 10 avec](https://technet.microsoft.com/itpro/windows/deploy/deploy-windows-10-with-the-microsoft-deployment-toolkit)microsoft Deployment Shared Computer Toolkit .
