---
title: Déploiement d’une application de surface avec Microsoft Store entreprise ou Microsoft Store pour l’éducation (surface)
description: Découvrez comment ajouter et télécharger une application de surface avec Microsoft Store pour les entreprises ou Microsoft Store pour l’éducation, et pour installer une application de surface avec PowerShell et MDT.
keywords: application de surface, application, déploiement, personnalisation
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
ms.openlocfilehash: 811feff1f0643ab0ba5d624c5f7d561ba5b0cd4d
ms.sourcegitcommit: c1efb75e8524193bdc0a5f7496dc23a92ac665c8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/12/2020
ms.locfileid: "11114712"
---
# Déploiement d’une application de surface avec Microsoft Store pour les entreprises et l’éducation

**Concerne**

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


L’application surface est une application légère du Microsoft Store qui fournit le contrôle de nombreux paramètres et options spécifiques à la surface, notamment: 

* Activer ou désactiver le boutonWindows sur l’appareilSurface 

* Ajuster la sensibilité du styletSurface 

* Personnaliser les actions des boutons des styletsSurface 

* Activer ou désactiver les améliorations audio de l’appareilSurface 

* Accès rapide à la documentation et aux informations de support pour votre appareil

Les clients qui utilisent Windows Update recevront généralement l’application surface dans le cadre de mises à jour automatiques. En revanche, si votre organisation prépare des images à déployer sur vos appareils surface, vous pouvez inclure l’application surface (auparavant appelée surface Hub) dans votre processus d’imagerie et de déploiement au lieu de demander aux utilisateurs de chaque appareil de télécharger et d’installer l’application à partir du Microsoft Store ou de la boutique Microsoft pour les entreprises. 

> [!NOTE]
> Cet article ne s’applique pas à surface Pro X. Pour plus d’informations, reportez-vous à [déploiement, gestion et maintenance de surface Pro X](surface-pro-arm-app-management.md) .

## Présentation de l’application surface

L’application surface est disponible en téléchargement gratuit à partir du [Microsoft Store](https://www.microsoft.com/store/apps/Surface/9WZDNCRFJB8P). Les utilisateurs peuvent le télécharger et l’installer à partir du Microsoft Store, mais si votre organisation utilise plutôt le Microsoft Store entreprise, vous devez l’ajouter au stock de votre magasin et éventuellement inclure l’application dans le cadre de votre processus de déploiement Windows. Ces processus sont abordés dans cet article. Pour plus d’informations sur le Microsoft Store pour les entreprises, voir [Microsoft Store pour les entreprises](https://docs.microsoft.com/microsoft-store/) dans le Windows TechCenter. 

## Ajouter une application de surface à un compte Microsoft Store pour les entreprises 

Pour que les utilisateurs puissent installer ou déployer une application à partir du compte Microsoft Store entreprise d’une entreprise, les applications souhaitées doivent d’abord être mises à disposition et sous licence des utilisateurs d’une entreprise. 

1. Si vous ne l’avez pas déjà fait, créez un [compte Microsoft Store pour les entreprises](https://www.microsoft.com/business-store). 

2. Ouvrez une session sur le portail. 

3. Activez la gestion >des licences hors connexion: cliquez sur **gérer les paramètres**du Windows Store, puis activez la case à cocher **afficher les applications sous licence hors connexion aux personnes qui se trouvent dans le Windows Store** , comme illustré dans la figure 1. Pour plus d’informations sur les modèles de licences d’application Microsoft Store pour les entreprises, voir [applications dans le Microsoft Store pour les entreprises et l’éducation](https://docs.microsoft.com/microsoft-store/).

   > [!div class="mx-imgBorder"]
   > ![Case à cocher Afficher les applications de licences hors connexion](images/deploysurfapp-figure1-enablingapps.png "Show offline licenses apps checkbox")<br/>
   *Figure1. Activer les applications pour une utilisation hors connexion*

4. Ajoutez une application de surface à votre compte Microsoft Store pour les entreprises en procédant comme suit:

    * Cliquez sur le menu **Shop** .
    
    * Dans la zone de recherche, tapez **application surface**, puis cliquez sur l’icône Rechercher.
    
    * Après la présentation de l’application surface dans les résultats de la recherche, cliquez sur l’icône de l’application.
    
    * Vous avez le choix entre une option (sélectionnez **en ligne** ou en **mode hors connexion**), comme illustré dans la figure 2.
    
      > [!div class="mx-imgBorder"]
      > ![Sélectionner le mode de gestion des licences hors connexion et ajouter l’application à votre inventaire](images/deploysurfapp-fig2-selectingofflinelicense.png "Select the Offline licensing mode and add the app to your inventory")   
      *Figure2. Sélectionner le mode de gestion des licences hors connexion et ajouter l’application à votre inventaire*
    
    * Cliquez sur **hors connexion** pour sélectionner le mode de gestion des licences hors connexion.
    
    * Cliquez sur **obtenir l’application** pour ajouter l’application à votre inventaire Microsoft Store pour les entreprises. Comme le montre la figure 3, une boîte de dialogue s’affiche pour vous demander d’accepter que les applications hors connexion peuvent être déployées à l’aide d’un outil de gestion ou téléchargées à partir de la page d’inventaire de la société dans leur magasin privé.
    
      > [!div class="mx-imgBorder"]
      > ![Fenêtre accusé de réception de l’application sous licence hors connexion ](images/deploysurfapp-fig3-acknowledge.png "Offline-licensed app acknowledgement window")
       *figure 3. Accusé de réception de l’application sous licence hors connexion*
      
    * Cliquez sur **OK**.

## Télécharger l’application surface à partir d’un compte Microsoft Store pour les entreprises
Après avoir ajouté une application au compte Microsoft Store entreprise en mode hors connexion, vous pouvez télécharger et ajouter l’application en tant que fichier AppxBundle à un partage de déploiement.

1. Connectez-vous au compte Microsoft Store pour les entreprises à l’adresse https://businessstore.microsoft.com .

2. Cliquez sur **gérer->applications & logiciel**. La liste de toutes les applications de votre entreprise s’affiche, y compris l’application surface que vous avez ajoutée dans la section [Ajouter une application surface à un compte Microsoft Store pour les entreprises](#add-surface-app-to-a-microsoft-store-for-business-account) de cet article.

3. Sous **actions**, cliquez sur les points de suspension (**...**), puis sur **Télécharger pour une utilisation en mode hors connexion** pour l’application surface.

4. Sélectionnez les options de **plateforme** et d' **architecture** souhaitées dans les sélections disponibles pour l’application sélectionnée, comme illustré dans la figure 4.

    > [!div class="mx-imgBorder"]
    > ![Exemple du package AppxBundle](images/deploysurfapp-fig4-downloadappxbundle.png "Example of the AppxBundle package")<br/>
    *Figure4. Télécharger le package AppxBundle pour une application*
    
5. Cliquez sur **Télécharger**. Le package AppxBundle sera téléchargé. Assurez-vous de noter le chemin du fichier téléchargé, car vous en aurez besoin plus tard dans cet article.

6. Cliquez sur l’option **licence encodée** ou **licence** non codée. Utilisez l’option de licence encodée avec des outils de gestion tels que Microsoft Endpoint Configuration Manager ou lorsque vous utilisez le concepteur de configuration Windows pour créer un package de mise en service. Sélectionnez l’option de licence non encodée lorsque vous utilisez des solutions de maintenance et de gestion des images de déploiement en fonction de l’image, y compris le kit de développement logiciel Microsoft Deployment (MDT).

7. Cliquez sur **générer** pour générer et télécharger la licence de l’application. Assurez-vous de noter le chemin d’accès du fichier de licence, car vous en aurez besoin plus tard dans cet article.

>[!NOTE]
>Lorsque vous téléchargez une application pour une utilisation en mode hors connexion, par exemple, l’application surface, vous pouvez remarquer une section en bas de la page intitulée **infrastructures requises**. Pour qu’une application puisse s’exécuter sur vos ordinateurs cibles, il est possible que vous deviez répéter le processus de téléchargement de chaque infrastructure requise pour votre architecture (x86 ou x64) et les inclure dans le cadre de votre déploiement Windows abordé plus loin dans cet article.

La figure 5 montre les infrastructures nécessaires pour l’application surface.

> [!div class="mx-imgBorder"]
> ![Infrastructures requises pour l’application surface](images/deploysurfapp-fig5-requiredframework.png "Required frameworks for the Surface app")<br/>
*Figure5. Infrastructures requises pour l’application surface*

>[!NOTE]
>Les numéros de version de l’application surface et les infrastructures requises seront modifiés à mesure que les applications sont mises à jour. Recherchez la dernière version de l’application surface et chaque infrastructure de la boutique Microsoft pour les entreprises. Utilisez toujours l’application surface et les versions d’infrastructure recommandées fournies par le Microsoft Store pour entreprises. L’utilisation d’infrastructures obsolètes ou de versions incorrectes risque de provoquer des erreurs ou des blocages d’applications.

Pour télécharger les infrastructures requises pour l’application surface, procédez comme suit:

1. Cliquez sur le bouton **Télécharger** sous **Microsoft. VCLibs. 140.00 _14.0.23816.0 _x64__8wekyb3d8bbwe**. Cette opération télécharge le VCLibs. 140.00 _14.0.23816.0 _x64__8wekyb3d8bbwe. Fichier AppX dans le dossier spécifié.

2. Cliquez sur le bouton **Télécharger** sous **Microsoft. net. native. Runtime. 1.1 _ _ 1.23406.0 _x64__8wekyb3d8bbwe**. Le téléchargement du fichier Microsoft. NET. native. Runtime. 1.1 _ 1.23406. _x64__8wekyb3d8bbwe. AppX dans le dossier spécifié.

>[!NOTE]
>Seule la version 64 bits (x64) de chaque infrastructure est nécessaire pour les appareils surface. 64 les appareils surface s’exécutent sous la seule version et ne sont pas compatibles avec les versions 32 bits (x86) de Windows qui nécessitent des infrastructures 32. 

## Installation de l’application surface sur votre ordinateur avec PowerShell
La procédure suivante met en service l’application surface sur votre ordinateur et la rend disponible pour tous les comptes d’utilisateurs créés sur l’ordinateur ultérieurement.

1. À l’aide de la procédure décrite dans la section [Comment télécharger l’application de surface à partir d’un compte Microsoft Store pour les entreprises](#download-surface-app-from-a-microsoft-store-for-business-account) de cet article, téléchargez l’application de surface AppxBundle et le fichier de licence. 

2. Lancez une sessionPowerShell avec élévation des privilèges.

    >[!NOTE]
    >Si vous n’exécutez pas PowerShell en tant qu’administrateur, la session n’aura pas les autorisations requises pour installer l’application.
    
3. Dans la sessionPowerShell avec élévation de privilèges, copiez et collez la commande suivante:

    ```powershell
    Add-AppxProvisionedPackage –Online –PackagePath <DownloadPath>\ Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle –LicensePath <DownloadPath>\ Microsoft.SurfaceHub_8wekyb3d8bbwe_a53ef8ab-9dbd-dec1-46c5-7b664d4dd003.xml
    ```

    Où `<DownloadPath>` se trouve le dossier dans lequel vous avez téléchargé les fichiers AppxBundle et de licence à partir du compte Microsoft Store pour les entreprises.

    Par exemple, si vous avez téléchargé les fichiers sur c:\Temp, la commande exécutée est la suivante:
    
    ```powershell
    Add-AppxProvisionedPackage –Online –PackagePath c:\Temp\ Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle –LicensePath c:\Temp\ Microsoft.SurfaceHub_8wekyb3d8bbwe_a53ef8ab-9dbd-dec1-46c5-7b664d4dd003.xml
    ```

4. L’applicationSurface est désormais disponible sur votre ordinateurWindows actuel. 

   Pour que l’application surface fonctionne sur l’ordinateur sur lequel elle a été configurée, vous devez également configurer les infrastructures décrites précédemment dans cet article. Pour mettre en service ces infrastructures, utilisez la procédure suivante dans la session PowerShell avec élévation de privilèges que vous avez utilisée pour approvisionner l’application surface.

5. Dans la sessionPowerShell avec élévation de privilèges, copiez et collez la commande suivante:

   ```powershell
   Add-AppxProvisionedPackage –Online –SkipLicense –PackagePath <DownloadPath>\Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe.Appx
   ```
   
6. Dans la sessionPowerShell avec élévation de privilèges, copiez et collez la commande suivante:

   ```powershell
   Add-AppxProvisionedPackage –Online –SkipLicense –PackagePath <DownloadPath>\Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe.Appx
   ```

## Installation de surface App avec MDT
La procédure suivante utilise MDT pour automatiser l’installation de l’application surface au moment du déploiement. L’application est automatiquement provisionnée par MDT au cours du déploiement. Ainsi, vous pouvez utiliser ce processus avec des images existantes. Il s’agit du processus recommandé pour le déploiement de l’application surface dans le cadre d’un déploiement Windows sur des appareils surface, car elle ne permet pas de réduire la compatibilité entre les plateformes de l’image Windows.

1. À l’aide de la procédure décrite [précédemment dans cet article](#download-surface-app-from-a-microsoft-store-for-business-account), téléchargez l’application surface AppxBundle et le fichier de licence. 

2. À l’aide de l’Assistant Nouvelle application dans le déploiement de MDT Deployment Workbench, importez les fichiers téléchargés en tant que nouvelle **application avec des fichiers sources**.

3. Dans la page Détails de la **commande** de l’Assistant Nouvelle application, spécifiez le **Répertoire de travail** par défaut et pour la **commande** spécifiez le nom du fichier AppxBundle, comme suit:

   * Commande
   
     ```console
     Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle
     ```
     
   * Répertoire de travail:%DEPLOYROOT%\Applications\SurfaceApp

Pour que l’application surface puisse fonctionner sur l’ordinateur cible, elle doit également utiliser les infrastructures décrites précédemment dans cet article. Utilisez la procédure suivante pour importer les infrastructures requises pour l’application surface dans MDT et pour les configurer en tant que dépendances.

1. À l’aide de la procédure décrite précédemment dans cet article, téléchargez les fichiers de l’infrastructure. Stockez chaque infrastructure dans un dossier distinct.

2. À l’aide de l’Assistant Nouvelle application dans le déploiement de MDT Deployment Workbench, importez les fichiers téléchargés en tant que nouvelle **application avec des fichiers sources**.

3. Dans la page Détails de la **commande** , tapez le nom de fichier de chaque application téléchargée dans le champ de **commande** et le répertoire de travail par défaut.

Pour configurer les infrastructures en tant que dépendances de l’application de surface, utilisez ce processus:

1. Ouvrez les propriétés de l’application surface dans le déploiement de MDT Deployment Workbench.

2. Cliquez sur l’onglet **dépendances** , puis cliquez sur **Ajouter**.

3. Activez les cases à cocher correspondant à chaque infrastructure en utilisant le nom que vous avez fourni dans l’Assistant Nouvelle application.

Après l’importation, l’application surface sera disponible pour sélection à l’étape **applications** de l’Assistant Déploiement de Windows. Vous pouvez également lancer l’installation automatique de l’application en la spécifiant dans la séquence de tâches de déploiement, via la procédure suivante:

1. Ouvrez la séquence de tâches de déploiement dans MDTDeploymentWorkbench.

2. Ajoutez une nouvelle tâche **Installer l’application** dans la section **Restauration de l’état** du déploiement.

3. Sélectionnez **installer une seule application** et spécifiez l’application **surface** **à**installer.

Pour plus d’informations sur l’ajout d’applications dans vos déploiements Windows, consultez [la rubrique déploiement de Windows 10 à l’aide du kit de développement Microsoft Deployment](https://technet.microsoft.com/itpro/windows/deploy/deploy-windows-10-with-the-microsoft-deployment-toolkit).
