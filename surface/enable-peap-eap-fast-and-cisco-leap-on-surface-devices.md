---
title: ActiverPEAP, EAP-FAST et CiscoLEAP sur des appareilsSurface
description: Découvrez comment activer la prise en charge des protocolesPEAP, EAP-FAST ou CiscoLEAP sur votre appareilSurface.
ms.assetid: A281EFA3-1552-467D-8A21-EB151E58856D
ms.reviewer: ''
manager: laurawi
keywords: réseau, sans fil, appareil, déployer, authentification, protocole
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.openlocfilehash: 1a9bef0a6e0bfdd4bede1b508b4013fd14e1a0bd
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10833497"
---
# Activer les protocolesPEAP, EAP-FAST et CiscoLEAP sur des appareilsSurface


Découvrez comment activer la prise en charge des protocolesPEAP, EAP-FAST ou CiscoLEAP sur votre appareilSurface.

Si vous utilisez ces protocoles dans votre réseau d’entreprise, vous savez probablement déjà que ces trois protocoles d’authentification sans fil ne sont pas pris en charge par les appareilsSurface prêts à l’emploi. Les utilisateurs peuvent s’en rendre compte lorsqu’ils tentent de se connecter à votre réseau sans fil, ou lorsqu’ils constatent qu’ils ne peuvent pas accéder aux ressources situées au sein du réseau (partages de fichiers et sites internes, par exemple). Pour en savoir plus, voir [Extensible Authentication Protocol](https://technet.microsoft.com/network/bb643147).

Vous pouvez ajouter la prise en charge de chaque protocole en exécutant un petit packageMSI à partir d’une cléUSB ou d’un partage de fichiers. Pour les organisations qui souhaitent activer la prise en charge du protocole EAP sur leurs appareils surface, le format de package MSI prend en charge le déploiement de nombreux outils de gestion et de déploiement, tels que Microsoft Deployment Toolkit (MDT) et Microsoft Endpoint Configuration Manager.

## <a href="" id="download-peap--eap-fast--or-cisco-leap-installation-files--"></a>Télécharger les fichiers d’installation des protocolesPEAP, EAP-FAST ou CiscoLEAP


Vous pouvez télécharger les fichiers d’installationMSI pour PEAP, EAP-FAST ou CiscoLEAP dans un fichier d’archivezip unique à partir du Centre de téléchargementMicrosoft. Pour télécharger ce fichier, accédez à la page du Centre de téléchargementMicrosoft relative à [SurfaceTools for IT](https://www.microsoft.com/download/details.aspx?id=46703), cliquez sur **Télécharger**, puis sélectionnez le fichier **Cisco EAP-Supplicant Installer.zip**.

## Déployer les protocolesPEAP, EAP-FAST ou CiscoLEAP avec MDT


Si vous effectuez déjà un déploiement de Windows sur des appareilsSurface dans votre entreprise, vous pouvez rapidement ajouter des fichiers d’installation pour chaque protocole dans votre partage de déploiement et configurer l’installation automatique lors du déploiement, en toute simplicité. Il est même possible de configurer une séquence de tâches qui mette à jour les appareilsSurface précédemment déployés, afin d’assurer la prise en charge de ces protocoles, via le même processus.

Pour activer la prise en charge de PEAP, EAP-FAST ou CiscoLEAP sur des appareilsSurface récemment déployés, procédez comme suit:

1.  Téléchargez et installez les fichiers d’installation de chaque protocole dans des dossiers distincts faciles d’accès.

2.  Ouvrez MDTDeploymentWorkbench et développez votre partage de déploiement, sur le dossier **Applications**.

3.  Sélectionnez **Nouvelle application** dans le volet **Action**.

4.  Choisissez **Application avec les fichiers sources** pour copier les fichiersMSI dans le partage de déploiement.

5.  Sélectionnez le dossier que vous avez créé à l’étape1 pour le protocole souhaité.

6.  Nommez le dossier dans le partage de déploiement dans lequel les fichiers d’installation doivent être stockés.

7.  Spécifiez la ligne de commande permettant de déployer l’application:

    -   Pour PEAP: **EAP-PEAP.msi /qn /norestart**.

    -   Pour LEAP: **EAP-LEAP.msi /qn /norestart**.

    -   Pour EAP-FAST: **EAP-FAST.msi /qn /norestart**.

8.  Pour l’Assistant Nouvelleapplication, utilisez les options par défaut.

9.  Répétez les étapes3 à 8 pour chaque protocole souhaité.

Une fois que vous avez exécuté ces étapes et importé les trois packagesMSI en tant qu’applications dans MDT, vous pouvez sélectionner ces derniers dans la pageApplications de l’Assistant de déploiement Windows. Dans certains scénarios de déploiement simples, la sélection de chaque package, par le technicien, lors du déploiement, peut suffire, mais ce n’est pas recommandé. En effet, il se peut que le technicien tente d’appliquer ces packages à des ordinateurs autres que des appareilsSurface, ou qu’un appareilSurface soit déployé sans que la prise en charge du protocoleEAP ne soit activée, suite à une erreur humaine.

Pour masquer ces applications à partir de la pageInstaller des applications, cochez la case **Masquer cette application dans l’Assistant de déploiement** dans les propriétés de chaque application. Une fois masquées, les applications n’apparaissent pas comme facultatives lors du déploiement. Pour pouvoir les déployer au cours de votre séquence de tâches de déploiementSurface, vous devez les définir de manière explicite pour une installation via une étape distincte de cette séquence.

Pour spécifier le ou les protocoles de manière explicite, procédez comme suit:

1.  Ouvrez les propriétés de la séquence de tâches de déploiement de votre appareilSurface dans MDTDeploymentWorkbench.

2.  Sur l’onglet **Séquence de tâches**, sélectionnez l’étape **Installer les applications**, sous **Restauration de l’état**. En général, elle se trouve entre les étapes de mise à jour deWindows avant et après l’application.

3.  Utilisez le bouton **Ajouter** pour créer une étape **Installer l’application** dans la catégorie **Général**.

4.  Sélectionnez **Installer une seule application** dans l’onglet **Propriétés** de l’étape.

5.  Sélectionnez le protocoleEAP souhaité dans la liste.

6.  Répétez les étapes2 à 5 pour chaque protocole souhaité.

## Déployer les protocolesPEAP, EAP-FAST ou CiscoLEAP avec SystemCenterConfigurationManager


Pour les organisations qui gèrent les appareilsSurface avec le SystemCenterConfigurationManager, il est encore plus simple de déployer la prise en charge des protocolesPEAP, EAP-FAST ou CiscoLEAP sur les appareilsSurface. Il vous suffit d’importer chaque fichierMSI en tant qu’application à partir de la bibliothèque de logiciels et de configurer un déploiement dans votre regroupement d’appareilsSurface.

Pour en savoir plus sur le déploiement des applications avec ConfigurationManager, voir [Comment créer des applications dans ConfigurationManager](https://technet.microsoft.com/library/gg682159.aspx) et [Comment déployer des applications dans ConfigurationManager](https://technet.microsoft.com/library/gg682082.aspx).

 

 





