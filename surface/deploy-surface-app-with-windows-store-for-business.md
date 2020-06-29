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
ms.openlocfilehash: e25e146de49110dca1fea797f9630d9fa2d953e3
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832861"
---
# Déploiement d’une application de surface avec Microsoft Store pour les entreprises et l’éducation

**S'applique à**

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

3. Activez la gestion >des licences hors connexion: cliquez sur **gérer les paramètres**du Windows Store, puis activez la case à cocher **afficher les applications sous licence hors connexion aux personnes qui se trouvent dans le Windows Store** , comme illustré dans la figure 1. Pour plus d’informations sur les modèles de licences d’application Microsoft Store pour les entreprises, voir [applications dans le Microsoft Store pour les entreprises et l’éducation](https://docs.microsoft.com/microsoft-store/).<br/> <br/>
   ![Case à cocher Afficher les applications de licences hors connexion](images/deploysurfapp-figure1-enablingapps.png "Show offline licenses apps checkbox")<br/>
   *Figure1. Activer les applications pour une utilisation hors connexion*

4. Ajoutez une application de surface à votre compte Microsoft Store pour les entreprises en procédant comme suit:
    * Cliquez sur le menu **Shop** .
    * Dans la zone de recherche, tapez **application surface**, puis cliquez sur l’icône Rechercher.
    * Après la présentation de l’application surface dans les résultats de la recherche, cliquez sur l’icône de l’application.
    * Vous avez le choix entre une option (sélectionnez **en ligne** ou en **mode hors connexion**), comme illustré dans la figure 2.<br/><br/>
    
    ![Sélectionner le mode de gestion des licences hors connexion et ajouter l’application à votre inventaire](images/deploysurfapp-fig2-selectingofflinelicense.png "Select the Offline licensing mode and add the app to your inventory")
    
    *Figure2. Sélectionner le mode de gestion des licences hors connexion et ajouter l’application à votre inventaire*
    
    * Cliquez sur **hors connexion** pour sélectionner le mode de gestion des licences hors connexion.
    * Cliquez sur **obtenir l’application** pour ajouter l’application à votre inventaire Microsoft Store pour les entreprises. Comme le montre la figure 3, une boîte de dialogue s’affiche pour vous demander d’accepter que les applications hors connexion peuvent être déployées à l’aide d’un outil de gestion ou téléchargées à partir de la page d’inventaire de la société dans leur magasin privé.
    
    ![Fenêtre accusé de réception de l’application sous licence hors connexion](images/deploysurfapp-fig3-acknowledge.png "Offline-licensed app acknowledgement window")
    
    *Figure3. Accusé de réception de l’application sous licence hors connexion*
    * Cliquez sur **OK**.

## Télécharger l’application surface à partir d’un compte Microsoft Store pour les entreprises
Après avoir ajouté une application au compte Microsoft Store entreprise en mode hors connexion, vous pouvez télécharger et ajouter l’application en tant que fichier AppxBundle à un partage de déploiement.
1. Connectez-vous au compte Microsoft Store pour les entreprises à l’adresse https://businessstore.microsoft.com .
2. Cliquez sur **gérer->applications & logiciel**. La liste de toutes les applications de votre entreprise s’affiche, y compris l’application surface que vous avez ajoutée dans la section [Ajouter une application surface à un compte Microsoft Store pour les entreprises](#add-surface-app-to-a-microsoft-store-for-business-account) de cet article.
3. Sous **actions**, cliquez sur les points de suspension (**...**), puis sur **Télécharger pour une utilisation en mode hors connexion** pour l’application surface.
4. Sélectionnez les options de **plateforme** et d' **architecture** souhaitées dans les sélections disponibles pour l’application sélectionnée, comme illustré dans la figure 4.

    ![Exemple du package AppxBundle](images/deploysurfapp-fig4-downloadappxbundle.png "Example of the AppxBundle package")

    *Figure4. Télécharger le package AppxBundle pour une application*
5. Cliquez sur **Télécharger**. Le package AppxBundle sera téléchargé. Assurez-vous de noter le chemin du fichier téléchargé, car vous en aurez besoin plus tard dans cet article.
6. Cliquez sur l’option **licence encodée** ou **licence** non codée. Utilisez l’option de licence encodée avec des outils de gestion tels que Microsoft Endpoint Configuration Manager ou lorsque vous utilisez le concepteur de configuration Windows pour créer un package de mise en service. Sélectionnez l’option de licence non encodée lorsque vous utilisez des solutions de maintenance et de gestion des images de déploiement en fonction de l’image, y compris le kit de développement logiciel Microsoft Deployment (MDT).
7. Cliquez sur **générer** pour générer et télécharger la licence de l’application. Assurez-vous de noter le chemin d’accès du fichier de licence, car vous en aurez besoin plus tard dans cet article.

>[!NOTE]
>Lorsque vous téléchargez une application pour une utilisation en mode hors connexion, par exemple, l’application surface, vous pouvez remarquer une section en bas de la page intitulée **infrastructures requises**. Pour qu’une application puisse s’exécuter sur vos ordinateurs cibles, il est possible que vous deviez répéter le processus de téléchargement de chaque infrastructure requise pour votre architecture (x86 ou x64) et les inclure dans le cadre de votre déploiement Windows abordé plus loin dans cet article.

La figure 5 montre les infrastructures nécessaires pour l’application surface.

![Infrastructures requises pour l’application surface](images/deploysurfapp-fig5-requiredframework.png "Required frameworks for the Surface app")

*Figure5. Infrastructures requises pour l’application surface*

>[!NOTE]
>Les numéros de version de l’application surface et les infrastructures requises seront modifiés à mesure que les applications sont mises à jour. Recherchez la dernière version de l’application surface et chaque infrastructure de la boutique Microsoft pour les entreprises. Utilisez toujours l’application surface et les versions d’infrastructure recommandées fournies par le Microsoft Store pour entreprises. L’utilisation d’infrastructures obsolètes ou de versions incorrectes risque de provoquer des erreurs ou des blocages d’applications.

Pour télécharger les infrastructures requises pour l’application surface, procédez comme suit:
1. Cliquez sur le bouton **Télécharger** sous **Microsoft. VCLibs. 140.00 _ 14.0.23816.0_x64__8wekyb3d8bbwe**. Le téléchargement de Microsoft. VCLibs. 140.00 _ 14.0.23816.0_x64__8wekyb3d8bbwe. Fichier AppX dans le dossier spécifié.
2. Cliquez sur le bouton **Télécharger** sous **Microsoft. net. native. Runtime. 1.1 _ 1.1.23406.0_x64__8wekyb3d8bbwe**. Cette opération télécharge le fichier Microsoft. NET. native. Runtime. 1.1 _ 1.1.23406.0_x64__8wekyb3d8bbwe. AppX dans le dossier spécifié.

>[!NOTE]
>Seule la version 64 bits (x64) de chaque infrastructure est nécessaire pour les appareils surface. 64 les appareils surface s’exécutent sous la seule version et ne sont pas compatibles avec les versions 32 bits (x86) de Windows qui nécessitent des infrastructures 32. 

## Installation de l’application surface sur votre ordinateur avec PowerShell
La procédure suivante met en service l’application surface sur votre ordinateur et la rend disponible pour tous les comptes d’utilisateurs créés sur l’ordinateur ultérieurement.
1. À l’aide de la procédure décrite dans la section [Comment télécharger l’application de surface à partir d’un compte Microsoft Store pour les entreprises](#download-surface-app-from-a-microsoft-store-for-business-account) de cet article, téléchargez l’application de surface AppxBundle et le fichier de licence. 
2. Lancez une sessionPowerShell avec élévation des privilèges.

    >[!NOTE]
    >Si vous n’exécutez pas PowerShell en tant qu’administrateur, la session n’aura pas les autorisations requises pour installer l’application.
    
3. Dans la sessionPowerShell avec élévation de privilèges, copiez et collez la commande suivante:
    ```
    Add-AppxProvisionedPackage –Online –PackagePath <DownloadPath>\ Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle –LicensePath <DownloadPath>\ Microsoft.SurfaceHub_8wekyb3d8bbwe_a53ef8ab-9dbd-dec1-46c5-7b664d4dd003.xml
    ```

    Où `<DownloadPath>` se trouve le dossier dans lequel vous avez téléchargé les fichiers AppxBundle et de licence à partir du compte Microsoft Store pour les entreprises.

    Par exemple, si vous avez téléchargé les fichiers sur c:\Temp, la commande exécutée est la suivante:
    ````
    Add-AppxProvisionedPackage –Online –PackagePath c:\Temp\ Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle –LicensePath c:\Temp\ Microsoft.SurfaceHub_8wekyb3d8bbwe_a53ef8ab-9dbd-dec1-46c5-7b664d4dd003.xml
    ```

4. The Surface app will now be available on your current Windows computer. 

Before the Surface app is functional on the computer where it has been provisioned, you must also provision the frameworks described earlier in this article. To provision these frameworks, use the following procedure in the elevated PowerShell session you used to provision the Surface app.

5. In the elevated PowerShell session, copy and paste the following command:
   ```
   Add-AppxProvisionedPackage –Online –SkipLicense –PackagePath <DownloadPath>\Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe.Appx
   ```
6. In the elevated PowerShell session, copy and paste the following command:
   ```
   Add-AppxProvisionedPackage –Online –SkipLicense –PackagePath <DownloadPath>\Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe.Appx
   ```

## Install Surface app with MDT
The following procedure uses MDT to automate installation of the Surface app at the time of deployment. The application is provisioned automatically by MDT during deployment and thus you can use this process with existing images. This is the recommended process to deploy the Surface app as part of a Windows deployment to Surface devices because it does not reduce the cross platform compatibility of the Windows image.
1. Using the procedure described [earlier in this article](#download-surface-app-from-a-microsoft-store-for-business-account), download the Surface app AppxBundle and license file. 
2. Using the New Application Wizard in the MDT Deployment Workbench, import the downloaded files as a new **Application with source files**.
3. On the **Command Details** page of the New Application Wizard, specify the default **Working Directory** and for the **Command** specify the file name of the AppxBundle, as follows:

   * Command:
     ```
     Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle
     ```
   * Working Directory: %DEPLOYROOT%\Applications\SurfaceApp

For the Surface app to function on the target computer, it will also require the frameworks described earlier in this article. Use the following procedure to import the frameworks required for the Surface app into MDT and to configure them as dependencies.
1. Using the procedure described earlier in this article, download the framework files. Store each framework in a separate folder.
2. Using the New Application Wizard in the MDT Deployment Workbench, import the downloaded files as a new **Application with source files**.
3. On the **Command Details** page, type the file name of each application you downloaded in the **Command** field and the default Working Directory.

To configure the frameworks as dependencies of the Surface app, use this process:
1. Open the properties of the Surface app in the MDT Deployment Workbench.
2. Click the **Dependencies** tab, and then click **Add**.
3. Select the check box for each framework using the name you provided in the New Application Wizard.

After import, the Surface app will be available for selection in the **Applications** step of the Windows Deployment Wizard. You can also install the application automatically by specifying the application in the deployment task sequence by following this process:
1. Open your deployment task sequence in the MDT Deployment Workbench.
2. Add a new **Install Application** task in the **State Restore** section of deployment.
3. Select **Install a single application** and specify the **Surface App** as the **Application to be installed**.

For more information about including apps into your Windows deployments, see [Deploy Windows 10 with the Microsoft Deployment Toolkit](https://technet.microsoft.com/itpro/windows/deploy/deploy-windows-10-with-the-microsoft-deployment-toolkit).
