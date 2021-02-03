---
title: Comment activer le clavier Surface Laptop lors du déploiement de MDT
description: Lorsque vous utilisez MDT pour déployer Windows 10 sur des ordinateurs portables Surface, vous devez importer les pilotes de clavier à utiliser dans l’environnement Windows PE.
keywords: surface windows 10, automatiser, personnaliser, mdt
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.reviewer: scottmca
ms.localizationpriority: medium
ms.audience: itpro
manager: jarrettr
ms.date: 02/02/2021
appliesto:
- Surface Laptop (1st Gen)
- Surface Laptop 2
- Surface Laptop 3
ms.openlocfilehash: fb51dd3785882e74c90d8b2717e4cc499d492d6f
ms.sourcegitcommit: 5cfac94c220c8a8d4620c6a7fa75ae2fae089c7f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2021
ms.locfileid: "11312060"
---
# Comment activer le clavier Surface Laptop pendant le déploiement de MDT

Cet article traite d’une approche de déploiement qui utilise Microsoft Deployment Shared Computer Toolkit (MDT). Vous pouvez également appliquer ces informations à d’autres méthodologies de déploiement. Sur la plupart des types d’appareils Surface, le clavier doit fonctionner pendant l’installation Lite Touch (LTI). Toutefois, surface laptop nécessite des pilotes supplémentaires pour activer le clavier. Pour les appareils Surface Laptop (1ère génération) et Surface Laptop 2, vous devez préparer la structure de dossiers et les profils de sélection qui vous permettent de spécifier des pilotes de clavier à utiliser pendant la phase d’environnement de préinstallation Windows (Windows PE) de LTI. Pour plus d’informations sur cette structure de dossiers, voir Déployer une [image Windows 10](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt?redirectedfrom=MSDN#step-5-prepare-the-drivers-repository)à l’aide de MDT : Étape 5 : Préparer le référentiel de pilotes.

> [!TIP]    
> Lorsque vous utilisez des pilotes de clavier pour Surface Laptop 2 et Surface Laptop 3 dans la même instance de démarrage Windows PE, vous devrez peut-être réinitialiser manuellement le microprogramme si le clavier ou le pavé tactile ne fonctionne pas dans Windows PE :
>
> - Appuyez et maintenez le bouton d’alimentation enfoncé pendant 30 secondes. Si vous êtes connecté à une unité d’alimentation, appuyez sur le bouton d’alimentation et maintenez enfoncée le bouton d’alimentation jusqu’à ce que la lumière à la fin du cordon d’alimentation soit brièvement éteinte avant de la désactiver.

> [!IMPORTANT]
> Si vous déployez une image Windows 10 sur un Ordinateur portable Surface sur qui Windows 10 est préinstallé en mode S, voir la KB [4032347,](https://support.microsoft.com/help/4032347/surface-preinstall-windows10-s-mode-issues)Problèmes lors du déploiement de Windows sur des appareils Surface avec Windows 10 préinstallé en mode S.

Pour ajouter les pilotes de clavier au profil de sélection, suivez les étapes suivantes :

1. Téléchargez le dernier fichier MSI Surface Laptop à partir des emplacements appropriés :
    - [Pilotes et microprogrammes Surface Laptop (1ère génération)](https://www.microsoft.com/download/details.aspx?id=55489)
    - [Surface Laptop 2 Drivers and Firmware](https://www.microsoft.com/download/details.aspx?id=57515)
    - [Surface Laptop 3 avec microprogramme et pilotes de processeur Intel](https://www.microsoft.com/download/details.aspx?id=100429)

2. Extrayez le contenu du fichier MSI surface laptop dans un dossier que vous pouvez facilement localiser (par exemple, c:\surface_laptop_drivers). Pour extraire le contenu, ouvrez une fenêtre d’invite de commandes avec élévation de niveaux et exécutez la commande à partir de l’exemple suivant :

   ```cmd
   Msiexec.exe /a SurfaceLaptop_Win10_15063_1703008_1.msi targetdir=c:\surface_laptop_drivers /qn
   ```

3. Ouvrez Deployment Workbench et développez le nœud **Deployment Shares** et votre partage de déploiement, puis accédez au **dossier WindowsPEX64.**

   ![Image qui montre l’emplacement du dossier WindowsPEX64 dans Deployment Workbench](./images/surface-laptop-keyboard-1.png)

4. Cliquez avec le bouton droit **sur le dossier WindowsPEX64** et sélectionnez **Importer des pilotes.**

5. Suivez les instructions de l’Assistant Importation de pilotes pour importer les dossiers de pilotes dans le dossier WindowsPEX64.  

    > [!NOTE]
    >  Vérifiez le package MSI téléchargé pour déterminer le format et la structure du répertoire.  La structure du répertoire commence par SurfacePlatformInstaller (fichiers MSI plus anciens) ou SurfaceUpdate (fichiers MSI plus nouveaux) selon la date de publication du MSI. 

    Pour prendre en charge Surface Laptop (1re génération), importez les dossiers suivants :

     - SurfacePlatformInstaller\Drivers\System\GPIO
     - SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver
     - SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver
     - SurfacePlatformInstaller\Drivers\System\PreciseTouch

    Ou pour les fichiers MSI plus nouveaux commençant par « SurfaceUpdate », utilisez :

    - SurfaceUpdate\SerialIOGPIO
    - SurfaceUpdate\SurfaceHidMiniDriver
    - SurfaceUpdate\SurfaceSerialHubDriver
    - SurfaceUpdate\It sous

    Pour prendre en charge Surface Laptop 2, importez les dossiers suivants :

     - SurfacePlatformInstaller\Drivers\System\GPIO
     - SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver
     - SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver
     - SurfacePlatformInstaller\Drivers\System\I2C
     - SurfacePlatformInstaller\Drivers\System\SPI
     - SurfacePlatformInstaller\Drivers\System\UART
     - SurfacePlatformInstaller\Drivers\System\PreciseTouch

    Ou pour les fichiers MSI plus nouveaux commençant par « SurfaceUpdate », utilisez :

    - SurfaceUpdate\SerialIOGPIO
    - SurfaceUpdate\serialioi2c
    - SurfaceUpdate\SerialIOSPI
    - SurfaceUpdate\SerialIOUART
    - SurfaceUpdate\SurfaceHidMini
    - SurfaceUpdate\SurfaceSerialHub
    - SurfaceUpdate\It sous

     
    Pour prendre en charge Surface Laptop 3 avec le processeur Intel, importez les dossiers suivants :

    - SurfaceUpdate\SerialIOGPIO
    - SurfaceUpdate\SerialIOI2C
    - SurfaceUpdate\SerialIOSPI
    - SurfaceUpdate\SerialIOUART
    - SurfaceUpdate\SurfaceHidMini
    - SurfaceUpdate\SurfaceSerialHub
    - SurfaceUpdate\SurfaceHotPlug
    - SurfaceUpdate\It sous

    L’importation des dossiers suivants activera les fonctionnalités clavier, trackpad et tactile complètes dans PE pour Surface Laptop 3.

    - SerialIOGPIO
    - SerialIOI2C
    - SerialIOSPI
    - SerialIOUART
    - its
    - Chipset
    - ChipsetLPSS
    - ChipsetNorthpeak
    - ManagementEngine
    - SurfaceAcpiNotify
    - SurfaceBattery
    - SurfaceDockIntegration
    - SurfaceHidMini
    - SurfaceHotPlug
    - SurfaceIntegration
    - SurfaceSerialHub
    - SurfaceService
    - SurfaceStorageFwUpdate

     > [!NOTE]
     >  Vérifiez le package MSI téléchargé pour déterminer le format et la structure du répertoire.  La structure du répertoire commence par SurfacePlatformInstaller (fichiers MSI plus anciens) ou SurfaceUpdate (fichiers MSI plus nouveaux) selon la date de publication du MSI. 

     Pour prendre en charge Surface Laptop (1re génération), importez les dossiers suivants :

    - SurfacePlatformInstaller\Drivers\System\GPIO
    - SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver
    - SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver
    - SurfacePlatformInstaller\Drivers\System\PreciseTouch

    Ou pour les fichiers MSI plus nouveaux commençant par « SurfaceUpdate », utilisez :

    - SurfaceUpdate\SerialIOGPIO
    - SurfaceUpdate\SurfaceHidMiniDriver
    - SurfaceUpdate\SurfaceSerialHubDriver
    - SurfaceUpdate\It sous

    Pour prendre en charge Surface Laptop 2, importez les dossiers suivants :

    - SurfacePlatformInstaller\Drivers\System\GPIO
    - SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver
    - SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver
    - SurfacePlatformInstaller\Drivers\System\I2C
    - SurfacePlatformInstaller\Drivers\System\SPI
    - SurfacePlatformInstaller\Drivers\System\UART
    - SurfacePlatformInstaller\Drivers\System\PreciseTouch

    Ou pour les fichiers MSI plus nouveaux commençant par « SurfaceUpdate », utilisez :

    - SurfaceUpdate\SerialIOGPIO
    - SurfaceUpdate\SerialIOI2C
    - SurfaceUpdate\SerialIOSPI
    - SurfaceUpdate\SerialIOUART
    - SurfaceUpdate\SurfaceHidMini
    - SurfaceUpdate\SurfaceSerialHub
    - SurfaceUpdate\It sous

    Pour prendre en charge Surface Laptop 3 avec le processeur Intel, importez les dossiers suivants :

    - SurfaceUpdate\SerialIOGPIO
    - SurfaceUpdate\SerialIOI2C
    - SurfaceUpdate\SerialIOSPI
    - SurfaceUpdate\SerialIOUART
    - SurfaceUpdate\SurfaceHidMini
    - SurfaceUpdate\SurfaceSerialHub
    - SurfaceUpdate\SurfaceHotPlug
    - SurfaceUpdate\It sous

    > [!NOTE]
    > Pour le Surface Laptop 3 avec processeur Intel, le modèle est Surface Laptop 3. Les pilotes Surface Laptop restants se trouvent dans le dossier \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3.

6. Vérifiez que le dossier WindowsPEX64 contient désormais les pilotes importés. Le dossier doit ressembler à ce qui suit :  

   ![Image that shows the newly imported drivers in the WindowsPEX64 folder of the Deployment Workbench](./images/surface-laptop-keyboard-2.png)

7. Configurez un profil de sélection qui utilise le dossier WindowsPEX64. Le profil de sélection doit ressembler à ce qui suit :  

   ![Image shows the WindowsPEX64 folder selected as part of a selection profile](./images/surface-laptop-keyboard-3.png)

8. Configurez les propriétés Windows PE du partage de déploiement MDT pour utiliser le nouveau profil de sélection, comme suit :  

   - Pour **la plateforme,** **sélectionnez x64**.
   - Pour **le profil de**sélection, sélectionnez le nouveau profil.
   - Sélectionnez **Inclure tous les pilotes du profil de sélection.**
   
   ![Image qui illustre les propriétés Windows PE du partage de déploiement MDT](./images/surface-laptop-keyboard-4.png)

9. Vérifiez que vous avez configuré les pilotes Surface Laptop restants à l’aide d’un profil de sélection ou d’une variable **DriverGroup001.**  
   - Pour surface laptop (1ère génération), le modèle est **Surface Laptop**. Les pilotes Surface Laptop restants doivent résider dans le dossier \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop, comme illustré dans la figure qui suit cette liste.
   - Pour Surface Laptop 2, le modèle est **Surface Laptop 2**. Les pilotes Surface Laptop restants doivent résider dans le dossier \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 2. 
   - Pour le Surface Laptop 3 avec processeur Intel, le modèle est Surface Laptop 3. Les pilotes Surface Laptop restants se trouvent dans le dossier \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3.

   ![Image that shows the regular Surface Laptop (1st Gen) drivers in the Surface Laptop folder of the Deployment Workbench](./images/surface-laptop-keyboard-5.png)

Après avoir configuré le partage de déploiement MDT pour utiliser le nouveau profil de sélection et les paramètres associés, poursuivez le processus de déploiement comme décrit dans Déployer une [image Windows 10](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt#step-6-create-the-deployment-task-sequence)à l’aide de MDT : Étape 6 : Créer la séquence de tâches de déploiement.
