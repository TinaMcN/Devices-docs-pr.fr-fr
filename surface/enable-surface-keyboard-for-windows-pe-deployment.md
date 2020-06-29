---
title: Comment activer le clavier surface Laptop pour le clavier portable surface lors du déploiement de MDT
description: Lorsque vous utilisez MDT pour déployer Windows 10 sur des ordinateurs portables en surface, vous devez importer les pilotes de clavier à utiliser dans l’environnement Windows PE.
keywords: surface Windows 10, automatiser, personnaliser, MDT
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
appliesto:
- Surface Laptop (1st Gen)
- Surface Laptop 2
- Surface Laptop 3
ms.openlocfilehash: 5d4e4b46c109d9fe24fe75151c9eb1e0a8b702c0
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832555"
---
# Comment activer le clavier surface Laptop pour le clavier portable surface lors du déploiement de MDT

Cet article traite d’une approche de déploiement qui utilise le kit de développement Microsoft Deployment (MDT). Vous pouvez également appliquer ces informations à d’autres méthodes de déploiement. Sur la plupart des types de périphériques surface, le clavier doit fonctionner au cours de l’installation LTI (LTI). En revanche, le portable surface nécessite des pilotes supplémentaires pour activer le clavier. Pour les appareils mobiles surface (1ère génération) et surface Laptop 2, vous devez préparer les profils de structure et de sélection des dossiers pour vous permettre de spécifier les pilotes de clavier à utiliser lors de la phase de l’environnement de préinstallation Windows (Windows PE) de LTI. Pour plus d’informations sur cette structure de dossiers, consultez [la rubrique déploiement d’une image Windows 10 à l’aide de MDT: étape 5: préparer le référentiel de pilotes](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt?redirectedfrom=MSDN#step-5-prepare-the-drivers-repository).

> [!NOTE]
> Pour l’instant, cette fonctionnalité n’est pas prise en charge pour ajouter les pilotes de clavier surface Laptop 2 et surface Laptop 3 dans la même instance de démarrage Windows PE en raison d’un conflit de pilote. Utilisez plutôt des instances distinctes.

> [!IMPORTANT]
> Si vous déployez une image Windows 10 sur un ordinateur portable sur lequel le mode Windows 10 en S est préinstallé, voir KB [4032347, problèmes lors du déploiement de Windows sur les appareils surface avec Windows 10 en mode s préinstallé](https://support.microsoft.com/help/4032347/surface-preinstall-windows10-s-mode-issues).

Pour ajouter les pilotes du clavier au profil de sélection, procédez comme suit:

1. Téléchargez le dernier fichier MSI surface Laptop à partir des emplacements appropriés:
    - [Pilotes de surface Laptop (1ère génération) et microprogramme](https://www.microsoft.com/download/details.aspx?id=55489)
    - [Micropilote surface Laptop 2 et microprogramme](https://www.microsoft.com/download/details.aspx?id=57515)
    - [Surface Laptop 3 avec pilotes de processeur Intel et microprogramme](https://www.microsoft.com/download/details.aspx?id=100429)

2. Extrayez le contenu du fichier MSI surface Laptop dans un dossier que vous pouvez facilement retrouver (par exemple, c:\ surface_laptop_drivers). Pour extraire le contenu, ouvrez une fenêtre d’invite de commandes avec élévation de privilèges et exécutez la commande à partir de l’exemple suivant:

   ```cmd
   Msiexec.exe /a SurfaceLaptop_Win10_15063_1703008_1.msi targetdir=c:\surface_laptop_drivers /qn
   ```

3. Ouvrez le Deployment Workbench et développez le nœud **partages de déploiement** et votre partage de déploiement, puis accédez au dossier **WindowsPEX64** .

   ![Image illustrant l’emplacement du dossier WindowsPEX64 dans Deployment Workbench](./images/surface-laptop-keyboard-1.png)

4. Cliquez avec le bouton droit sur le dossier **WindowsPEX64** et sélectionnez **Importer les pilotes**.
5. Pour importer les dossiers de pilotes dans le dossier WindowsPEX64, suivez les instructions de l’Assistant importation de pilote.  

> [!NOTE]
>  Vérifiez le package MSI téléchargé pour déterminer le format et la structure du répertoire.  La structure de l’annuaire va commencer par SurfacePlatformInstaller (fichiers MSI plus anciens) ou SurfaceUpdate (nouveaux fichiers MSI) selon le moment de la sortie du MSI. 

Pour prendre en charge l’ordinateur portable surface (1ère génération), importez les dossiers suivants:

 - SurfacePlatformInstaller\Drivers\System\GPIO
 - SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver
 - SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver
 - SurfacePlatformInstaller\Drivers\System\PreciseTouch

Ou, pour les nouveaux fichiers MSI commençant par «SurfaceUpdate», utilisez:

- SurfaceUpdate\SerialIOGPIO
- SurfaceUpdate\SurfaceHidMiniDriver
- SurfaceUpdate\SurfaceSerialHubDriver
- SurfaceUpdate\Itouch

Pour prendre en charge surface Laptop 2, importez les dossiers suivants:

 - SurfacePlatformInstaller\Drivers\System\GPIO
 - SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver
 - SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver
 - SurfacePlatformInstaller\Drivers\System\I2C
 - SurfacePlatformInstaller\Drivers\System\SPI
 - SurfacePlatformInstaller\Drivers\System\UART
 - SurfacePlatformInstaller\Drivers\System\PreciseTouch

Ou, pour les nouveaux fichiers MSI commençant par «SurfaceUpdate», utilisez:

- SurfaceUpdate\SerialIOGPIO
- SurfaceUpdate\IclSerialIOI2C
- SurfaceUpdate\IclSerialIOSPI
- SurfaceUpdate\IclSerialIOUART
- SurfaceUpdate\SurfaceHidMini
- SurfaceUpdate\SurfaceSerialHub
- SurfaceUpdate\Itouch

 
Pour prendre en charge l’ordinateur portable surface 3 avec le processeur Intel, importez les dossiers suivants:

- SurfaceUpdate\IclSerialIOGPIO
- SurfaceUpdate\IclSerialIOI2C
- SurfaceUpdate\IclSerialIOSPI
- SurfaceUpdate\IclSerialIOUART
- SurfaceUpdate\SurfaceHidMini
- SurfaceUpdate\SurfaceSerialHub
- SurfaceUpdate\SurfaceHotPlug
- SurfaceUpdate\Itouch

L’importation des dossiers suivants permettra de bénéficier de la fonctionnalité complète du clavier, de pavé tactile et de l’interaction avec le complément PE pour surface Laptop 3.

- IclSerialIOGPIO
- IclSerialIOI2C
- IclSerialIOSPI
- IclSerialIOUART
- iTouch
- IclChipset
- IclChipsetLPSS
- IclChipsetNorthpeak
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
    >  Vérifiez le package MSI téléchargé pour déterminer le format et la structure du répertoire.  La structure de l’annuaire va commencer par SurfacePlatformInstaller (fichiers MSI plus anciens) ou SurfaceUpdate (nouveaux fichiers MSI) selon le moment de la sortie du MSI. 

    Pour prendre en charge l’ordinateur portable surface (1ère génération), importez les dossiers suivants:

     - SurfacePlatformInstaller\Drivers\System\GPIO
     - SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver
     - SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver
     - SurfacePlatformInstaller\Drivers\System\PreciseTouch

    Ou, pour les nouveaux fichiers MSI commençant par «SurfaceUpdate», utilisez:

    - SurfaceUpdate\SerialIOGPIO
    - SurfaceUpdate\SurfaceHidMiniDriver
    - SurfaceUpdate\SurfaceSerialHubDriver
    - SurfaceUpdate\Itouch

    Pour prendre en charge surface Laptop 2, importez les dossiers suivants:

     - SurfacePlatformInstaller\Drivers\System\GPIO
     - SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver
     - SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver
     - SurfacePlatformInstaller\Drivers\System\I2C
     - SurfacePlatformInstaller\Drivers\System\SPI
     - SurfacePlatformInstaller\Drivers\System\UART
     - SurfacePlatformInstaller\Drivers\System\PreciseTouch

    Ou, pour les nouveaux fichiers MSI commençant par «SurfaceUpdate», utilisez:

    - SurfaceUpdate\SerialIOGPIO
    - SurfaceUpdate\IclSerialIOI2C
    - SurfaceUpdate\IclSerialIOSPI
    - SurfaceUpdate\IclSerialIOUART
    - SurfaceUpdate\SurfaceHidMini
    - SurfaceUpdate\SurfaceSerialHub
    - SurfaceUpdate\Itouch

    Pour prendre en charge l’ordinateur portable surface 3 avec le processeur Intel, importez les dossiers suivants:

    - SurfaceUpdate\IclSerialIOGPIO
    - SurfaceUpdate\IclSerialIOI2C
    - SurfaceUpdate\IclSerialIOSPI
    - SurfaceUpdate\IclSerialIOUART
    - SurfaceUpdate\SurfaceHidMini
    - SurfaceUpdate\SurfaceSerialHub
    - SurfaceUpdate\SurfaceHotPlug
    - SurfaceUpdate\Itouch

    > [!NOTE]
    > Pour surface Laptop 3 avec processeur Intel, le modèle est surface Laptop 3. Les pilotes portables surface restants se trouvent dans le dossier \MDT de déploiement Share\Out-of-Box Drivers\Windows10\X64\Surface portable 3.

6. Vérifiez que le dossier WindowsPEX64 contient désormais les pilotes importés. Le dossier doit ressembler à ce qui suit:  

   ![Image illustrant les pilotes nouvellement importés dans le dossier WindowsPEX64 du Deployment Workbench](./images/surface-laptop-keyboard-2.png)

7. Configurez un profil de sélection qui utilise le dossier WindowsPEX64. Le profil de sélection doit ressembler à ce qui suit:  

   ![Image illustrant le dossier WindowsPEX64 sélectionné dans le cadre d’un profil de sélection](./images/surface-laptop-keyboard-3.png)

8. Configurez les propriétés Windows PE du partage de déploiement MDT pour utiliser le nouveau profil de sélection, comme suit:  

   - Pour **plate-forme**, sélectionnez **x64**.
   - Pour **profil de sélection**, sélectionnez le nouveau profil.
   - Sélectionnez **inclure tous les pilotes dans le profil de sélection**.
   
   ![Image illustrant les propriétés Windows PE du partage de déploiement MDT](./images/surface-laptop-keyboard-4.png)

9. Vérifiez que vous avez configuré les pilotes de surface mobile restants à l’aide d’un profil de sélection ou d’une variable **DriverGroup001** .  
   - Pour les ordinateurs portables surface (1er génération), le modèle est **surface Laptop**. Les autres pilotes de surface pour portables surface doivent résider dans le dossier de déploiement \MDT Share\Out-of-Box Drivers\Windows10\X64\Surface d’ordinateur portable, comme illustré dans la figure qui suit cette liste.
   - Pour surface Laptop 2, le modèle est **surface Laptop 2**. Les autres pilotes de surface pour ordinateur portable doivent résider dans le dossier \MDT de déploiement Share\Out-of-Box Drivers\Windows10\X64\Surface portable 2. 
   - Pour surface Laptop 3 avec processeur Intel, le modèle est surface Laptop 3. Les pilotes portables surface restants se trouvent dans le dossier \MDT de déploiement Share\Out-of-Box Drivers\Windows10\X64\Surface portable 3.

   ![Image illustrant les pilotes surface Laptop (1ère génération) standard dans le dossier surface Laptop du Deployment Workbench](./images/surface-laptop-keyboard-5.png)

Après avoir configuré le partage de déploiement MDT pour utiliser le nouveau profil de sélection et les paramètres associés, continuez le processus de déploiement comme décrit dans [la section déploiement d’une image Windows 10 à l’aide de MDT: étape 6: créer la séquence de tâches de déploiement](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt#step-6-create-the-deployment-task-sequence).
