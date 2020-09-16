---
title: Microsoft Surface Deployment Accelerator (Surface)
description: Microsoft Surface Deployment Accelerator offre aux organisations un mécanisme simple et rapide de déploiement dédié à la réinitialisation des appareilsSurface.
ms.assetid: E7991E90-4AAE-44B6-8822-58BFDE3EADE4
ms.reviewer: hachidan
manager: laurawi
ms.localizationpriority: medium
keywords: déployer, installer, outil
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.audience: itpro
ms.date: 5/08/2020
ms.openlocfilehash: 0e136bd0a69db7a4c4e5cea7d2c065727dcc8fcc
ms.sourcegitcommit: c2df79cab0e59e9d7ea6640e5899531b57cd383f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/16/2020
ms.locfileid: "11016436"
---
# Microsoft Surface Deployment Accelerator

Microsoft surface Deployment Accelerator (SDA) automatise la création et la configuration d’une interface de déploiement recommandée par Microsoft en utilisant des outils de déploiement gratuits de Microsoft.

Repensée en avril 2020 pour simplifier et automatiser le déploiement d’images surface dans un environnement d’entreprise, l’outil SDA vous permet de générer une image Windows de type usine que vous pouvez personnaliser selon les besoins de votre organisation.

L’outil SDA Open source, qui est piloté par un script exploite le kit de déploiement d’évaluation et de déploiement Windows (ADK) pour Windows 10, facilitant la création d’images Windows (WIM) dans les environnements de test ou de production. Si le dernier logiciel ADK n’est pas déjà installé, il sera téléchargé et installé lors de l’exécution de l’outil SDA.

L’image obtenue correspond étroitement à la configuration des images de récupération d’urgence, sans aucune application préinstallée telle que Microsoft Office ou l’application UWP surface.

## Configuration requise

1. Une clé USB USB d’au moins 16 Go. Le lecteur USB sera formaté.
2. Un fichier. ISO avec Windows 10 professionnel ou Windows 10 entreprise. Vous pouvez utiliser l’outil de création de médias pour télécharger Windows 10 et créer un fichier. ISO. Pour plus d’informations, reportez-vous à [Télécharger Windows 10](https://www.microsoft.com/software-download/windows10).

## Exécution de SDA

**Pour exécuter SDA:**

1. Accédez à [SurfaceDeploymentAccelerator](https://github.com/microsoft/SurfaceDeploymentAccelerator) sur GitHub. 
2. Consultez la documentation [Lisez-moi](https://github.com/microsoft/SurfaceDeploymentAccelerator/blob/master/README.md) .
3. Dans la page [SurfaceDeploymentAccelerator](https://github.com/microsoft/SurfaceDeploymentAccelerator) , cliquez sur le bouton **code** , puis sélectionnez **Télécharger zip** pour enregistrer les fichiers localement sur votre ordinateur.
4. Cliquez avec le bouton droit sur le fichier. zip, puis cliquez sur **Propriétés**.
5. Dans l’onglet **général** , activez la case à cocher **débloquer** , puis cliquez sur **OK**.
6. Extrayez le fichier. zip vers un emplacement sur votre disque dur (par exemple: C:\SDA).
7. Ouvrez une invite Windows PowerShell avec élévation de privilèges et définissez ExecutionPolicy pour la session actuelle sur non restreint.

    ```powershell
    Set-ExecutionPolicy -Scope Process -ExecutionPolicy Unrestricted -Force
    ```
8. Exécutez le script SDA spécifiant les paramètres pour votre environnement. Par exemple, la commande suivante permet de créer un lecteur USB amorçable qui peut être utilisé pour installer Windows 10 sur un surface Hub 2:

    ```powershell
    .\CreateSurfaceWindowsImage.ps1 -ISO C:\SDA\enterprise_client.iso -OSSKU Enterprise -DestinationFolder C:\Output -Device SurfaceHub2 -CreateUSB $True
    ```

   ![Outil accélérateur de déploiement de surface exécuté](images/sda1.png)

    Le script nécessite environ 45 minutes pour s’exécuter, mais peut prendre plus de temps en fonction des ressources du processeur et du disque disponibles. 

    Une fois que vous avez créé une image Windows, le script vous demande de confirmer la lettre de lecteur de votre lecteur USB. Le lecteur USB est alors formaté, configuré comme amorçable et les fichiers copiés pour permettre l’installation de l’image Windows 10 personnalisée pour les appareils surface.

9. Insérez le lecteur USB dans l’appareil sur lequel vous voulez installer Windows 10, puis redémarrez l’installation pour commencer l’installation de Windows 10. Le démarrage USB doit être activé dans le BIOS, ce qui peut nécessiter le Désactivation temporaire du démarrage sécurisé.

> [!IMPORTANT]
> Le démarrage à partir du lecteur USB commence immédiatement l’installation de Windows 10. Assurez-vous que votre appareil est prêt avant d’insérer le port USB et de redémarrage. 

## Liens connexes

 - [Outil de déploiement d’image source ouverte sur GitHub](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/open-source-image-deployment-tool-released-on-github/ba-p/1314115)

 - [Télécharger et installer Windows ADK](https://docs.microsoft.com/windows-hardware/get-started/adk-install)
