---
title: Microsoft Surface Data Eraser (Surface)
description: Découvrez comment l’outil Microsoft Surface Data Eraser peut vous aider à effacer en toute sécurité vos données sur vos appareilsSurface.
ms.assetid: 8DD3F9FE-5458-4467-BE26-E9200341CF10
ms.reviewer: hachidan
manager: laurawi
ms.localizationpriority: medium
keywords: outil, USB, données, effacer
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices, security
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
audience: itpro
ms.date: 01/15/2021
ms.openlocfilehash: 2ae1b7b3af93c1449b96bf6307c830a928c1f0a7
ms.sourcegitcommit: 1053479c191fd10651d31a466fad1769fb0cd28b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/16/2021
ms.locfileid: "11271408"
---
# Microsoft Surface Data Eraser


Découvrez comment l’outil Microsoft Surface Data Eraser peut vous aider à effacer en toute sécurité vos données sur vos appareilsSurface.

[Microsoft Surface Data Eraser](https://www.microsoft.com/download/details.aspx?id=46703) est un outil qui démarre à partir d’une cléUSB. Il assure l’effacement sécurisé de toutes les données d’un appareil Surface compatible. Une cléUSB Microsoft Surface Data Eraser nécessite uniquement la capacité de démarrage à partir du formatUSB. La cléUSB est facile à créer à l’aide de l’assistant fourni, Microsoft Surface Data Eraser Wrapper. Par ailleurs, il est simple d’utilisation avec une interface graphique épurée; aucune ligne de commande n’est requise. Pour plus d'informations sur les fonctionnalités d'effacement des données et sur les pratiques appliquées par Microsoft au cours du processus de maintenance des appareils Surface, consultez l'article [Protection de vos données si vous envoyez votre tablette Surface pour une intervention de maintenance](https://www.microsoft.com/surface/support/security-sign-in-and-accounts/data-wiping-policy).

>[!IMPORTANT]
>MicrosoftSurface Data Eraser utilise la commande de formatage NVM Express (NVMe) pour effacer les données, selon l’autorisation définie dans la [publication spéciale800à88 de l’institut NIST révision 1](http://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-88r1.pdf). 

Appareils Surface compatibles:

- Surface Book (toutes éditions)
- Surface Go (toutes éditions)
- Surface Pro X (toutes les éditions)
- Surface Laptop (toutes éditions)
- Surface Laptop Go
- Surface Studio (toutes éditions)
- Surface Pro 2 et les ultérieures
- Windows 10 Professionnel et Entreprise sur Surface Hub 2

Voici quelques scénarios durant lesquels l’outil Microsoft Surface Data Eraser peut s’avérer utile:

-   Préparation à l’envoi pour réparation d’un appareil Surface

-   Désactivation d’un appareil Surface à retirer du système de l’entreprise ou de l’organisation

-   Réaffectation d’un appareil Surface à utiliser dans un autre service ou à attribuer à un nouvel utilisateur

-   Procédure de routine de réinitialisation des appareils utilisés avec des données sensibles

>[!NOTE]
>les appareils tiers, les appareils Surface exécutant WindowsRT (notamment Surface et Surface2) et les appareils SurfacePro ne sont pas compatibles avec Microsoft Surface Data Eraser.

>[!NOTE]
>Étant donné que la capacité de démarrage sur formatUSB est requise pour exécuter l’outil Microsoft Surface Data Eraser, si l’appareil n’est pas configuré pour démarrer à partir du formatUSB ou s’il ne peut pas démarrer ou suivre la procédure POST, l’outil Microsoft Surface Data Eraser ne fonctionne pas.

>[!NOTE]
>Jusqu'à 6 minutes peuvent être nécessaires pour que Surface Data Eraser sur Surface Studio et Surface Studio 2 redémarre dans WinPE avant l'effacement du disque.


## Comment créer une cléUSB Microsoft Surface Data Eraser


Pour créer une cléUSBMicrosoft Surface Data Eraser, commencez par installer l’outil de configuration Microsoft Surface Data Eraser du Centre de téléchargement Microsoft en cliquant sur le lien fourni au début de cet article. Vous n’avez pas besoin d’appareil Surface pour *créer* la clé USB. Une fois que vous avez téléchargé le fichier d’installation sur votre ordinateur, suivez la procédure suivante pour installer l’outil de création Microsoft Surface Data Eraser:

1.  Exécutez le fichier d’installation DataEraserSetup.msi téléchargé à partir du [Centre de téléchargementMicrosoft](https://www.microsoft.com/download/details.aspx?id=46703).

2.  Sélectionnez la case à cocher afin d’accepter les termes du contrat de licence, puis cliquez sur **Installer**.

3.  Cliquez sur **Terminer** pour fermer la fenêtre de configuration Microsoft Surface Data Eraser.

Une fois l’outil de création installé, suivez la procédure suivante pour créer un port USBMicrosoft Surface Data Eraser. Avant de démarrer la procédure, vérifiez que vous disposez d’une cléUSB d’une capacité minimale de 4Go connectée à votre ordinateur.

1. Démarrez l’outil Microsoft Surface Data Eraser à partir du menu Démarrer ou de l’écran de démarrage.

2. Cliquez sur **Générer** pour commencer le processus de création de la clé USB Microsoft Surface Data Eraser. 

3. Cliquez sur **Démarrer** pour confirmer que vous avez connecté une cléUSB présentant une capacité minimale de 4Go, comme illustré dans la Figure1.

   ![Démarrer l’outil Microsoft Surface Data Eraser](images/dataeraser-start-tool.png "Start the Microsoft Surface Data Eraser tool")

   *Figure1. Démarrer l’outil Microsoft Surface Data Eraser*
4.  Sélectionnez **x64** pour la plupart des appareils Surface ou **ARM64** pour le Surface Pro X dans la page **Sélection de l’architecture**, comme illustré dans la figure2. Sélectionnez **Continuer**.

    ![Sélection de l’architecture](images/dataeraser-arch.png "Architecture Selection")<br>
       *Figure2. Sélectionnez l'architecture de l'appareil*
    

4. Comme indiqué dans la Figure 3, sélectionnez la cléUSB de votre choix sur la page **Sélection de la cléUSB**, puis cliquez sur **Démarrer** pour commencer le processus de création de clé USB. Le lecteur sélectionné sera formaté; toutes les données existantes seront perdues.

   >[!NOTE]
   >Si le bouton Démarrer est désactivé, vérifiez que votre lecteur amovible affiche une capacité totale minimale de 4Go.
  
   ![Sélection de la cléUSB](images/dataeraser-usb-selection.png "USB thumb drive selection")

   *Figure3. Sélection de la cléUSB*

5. Une fois le processus de création terminé, le lecteur USB est formaté et l’ensemble des binaires sont copiés dessus. Cliquez sur **Opération réussie**.

6. Quand la page **Félicitations s’affiche**, vous pouvez éjecter et retirer le lecteurUSB. Le lecteur peut être inséré dans un appareilSurface, être utilisé pour le démarrage et effacer les données sur l’appareil. Cliquez sur **Terminer** pour finir le processus de création de cléUSB, comme illustré dans la Figure4.

   ![Processus de création de clé USB Surface Data Eraser](images/dataeraser-complete-process.png "Surface Data Eraser USB creation process")

   *Figure4. Terminer le processus de création de clé USB Microsoft Surface Data Eraser*

7. Cliquez sur **X** pour fermer l’outil Microsoft Surface Data Eraser.

## Comment utiliser une clé USB Microsoft Surface Data Eraser


Une fois que vous avez créé une clé USB Microsoft Surface Data Eraser, vous pouvez démarrer un appareilSurface pris en charge à partir de cette dernière. Pour ce faire, exécutez la procédure suivante:

1. Insérez la clé USB démarrable Microsoft Surface Data Eraser dans l’appareilSurface pris en charge.

2. Démarrez votre périphérique Surface à partir de la clé USB MicrosoftSurface Data Eraser. Pour démarrer votre appareil à partir de la clé USB, procédez comme suit:

   a. Éteignez votre appareil Surface.

   b. Maintenez le bouton **Baisser le volume** enfoncé.

   c. Pressez puis relâchez le bouton **Marche/Arrêt**.

   d. Relâchez le bouton **Baisser le volume**.
    
   >[!NOTE]
   >Si votre périphérique ne démarre pas sur format USB en suivant ces étapes, vous devrez peut-être activer l'option **Activer la séquence de démarrage alternative** dans UEFI Surface. Vous pouvez en savoir plus sur la configuration de démarrage UEFI Surface dans [Gérer les paramètres UEFI Surface](https://technet.microsoft.com/itpro/surface/manage-surface-uefi-settings).

3. Lorsque l’appareil Surface démarre, un fichier texte **SoftwareLicenseTerms** s'affiche, comme illustré sur la Figure5.

   ![Démarrage de la clé USB Microsoft Surface Data Eraser](images/data-eraser-3.png "Booting the Microsoft Surface Data Eraser USB stick")

   *Figure5. Démarrage de la clé USB Microsoft Surface Data Eraser*

4. Lisez les termes du contrat de licence logiciel, puis fermez le fichier Bloc-notes.

5. Pour accepter ou refuser les termes du contrat de licence, saisissez **Accepter** ou **Refuser**. Vous devez accepter les termes du contrat de licence pour continuer.

6. Le script MicrosoftSurface Data Eraser détecte les périphériques de stockage présents dans votre appareil Surface et affiche les détails de l’appareil de stockage natif. Pour continuer, appuyez sur **Y** (cette action exécute MicrosoftSurface Data Eraser et supprime toutes les données à partir du périphérique de stockage) ou appuyez sur **N** (cette action entraîne l'arrêt de l’appareil sans supprimer les données).

   >[!NOTE]
   >L’outil MicrosoftSurface Data Eraser supprimera toutes les données, y compris les fichiers de système d’exploitation Windows requis pour démarrer l’appareil, de manière sécurisée et non récupérable. Pour démarrer un appareil Surface qui a été réinitialisé avec MicrosoftSurface Data Eraser, vous devez d’abord réinstaller le système d’exploitation Windows. Pour supprimer les données à partir d’un appareil Surface sans supprimer le système d’exploitation Windows, vous pouvez utiliser la fonction **Réinitialiser votre PC**. Toutefois, cela n’empêche pas vos données d’être récupérées grâce à des capacités d'investigation ou de récupération des données. Voir [Options de récupération dans Windows10](https://support.microsoft.com/help/12415/windows-10-recovery-options) pour plus d’informations.

   ![Affichage de la partition à effacer](images/sda-fig5-erase.png "Partition to be erased is displayed")
  
   *Figure6. La partition à effacer s’affiche dans l’outil Microsoft Surface Data Eraser*

7. Si vous avez appuyé sur **Y** à l’étape6, en raison de la nature destructrice du processus d’effacement des données, une boîte de dialogue supplémentaire de confirmation s’affiche.

8. Cliquez sur le bouton **Oui** pour poursuivre l’effacement des données sur l’appareilSurface.

   >[!NOTE]
   >Lorsque vous exécutez Surface Data Eraser sur le lecteur USB Surface Data Eraser, un fichier journal est généré dans le dossier **SurfaceDataEraserLogs**.

## Modifications et mises à jour

MicrosoftSurface Data Eraser est régulièrement mis à jour par Microsoft. Pour plus d’informations sur les modifications apportées dans chaque nouvelle version, consultez les rubriques suivantes:

### 2.34.139.0
*Date de publication : 15 janvier 2021*

Cette version de Surface Data Eraser:

- Inclut des correctifs de bogues

### 3.33.139
*Date de publication : 9 septembre 2020*

Cette version de Surface Data Eraser inclut des correctifs de bogues et ajoute la prise en charge des : 

- Nouvelle conception de l’architecture pour réduire la nécessité d’une mise à jour avec de nouvelles mises à jour de produits
- Notification disponible pour les nouvelles mises à jour d’outils
- Ajouts de télémétrie
- Windows 10 Professionnel et Entreprise sur Surface Hub 2


### 3.30.139
*Date de sortie: 11mai2020*

Cette version de Surface Data Eraser prend désormais en charge: 
- SurfaceBook3
- SurfaceGo2
- Nouveau SSD dans SurfaceGo

### 3.28.137
*Date de publication : 11 novembre 2019*

Cette version de Surface Data Eraser:

- Inclut des correctifs de bogues

### Version 3.21.137
*Date de publication : 21 octobre 2019*

Cette version de Surface Data Eraser est compilée pour x86 et ajoute la prise en charge des appareils suivants :

- Surface Pro 7, Surface Pro X et Surface Laptop 3

### Version 3.2.78.0

*Date de publication: 4 décembre 2018*

Cette version de Surface Data Eraser:

- Inclut des correctifs de bogues


### Version 3.2.75.0

*Date de publication: 12novembre2018*

Cette version de Surface Data Eraser:

- Ajouter la prise en charge de Surface Studio2
- Résolution des problèmes liés à la carte SD

### Version 3.2.69.0

*Date de publication: 12 octobre2018*

Cette version de Surface Data Eraser prend désormais en charge les produits suivants:

- SurfacePro6
- Surface Laptop2

### Version 3.2.68.0

Cette version de Microsoft Surface Data Eraser prend désormais en charge les produits suivants:

- SurfaceGo


### Version 3.2.58.0

Cette version de Microsoft Surface Data Eraser prend désormais en charge les produits suivants:

- Périphériques de stockage supplémentaires (lecteurs) pour les appareils Surface Pro et Surface Laptop


### Version3.2.46.0

Cette version de Microsoft Surface Data Eraser prend désormais en charge les produits suivants:

- SurfacePro avec LTE Advanced


### Version3.2.45.0

Cette version de Microsoft Surface Data Eraser prend désormais en charge les produits suivants:

- SurfaceBook2

- Surface Pro 1TB

   >[!NOTE]
   >Surface Data Eraser version3.2.45.0 et versions supérieures permet de restaurer des appareils Surface Pro ou Surface Laptop avec option de stockage 1To dans le cas où l’appareil affiche deux volumes distincts de 512Go ou rencontre des erreurs quand vous tentez de déployer ou d'installer Windows10. Pour plus d'informations, voir [Surface Pro modèle1796 et Surface Laptop 1TB affichent deux lecteurs](https://support.microsoft.com/help/4046105/surface-pro-model-1796-and-surface-laptop-1tb-display-two-drives).


### Version3.2.36.0

Cette version de Microsoft Surface Data Eraser prend désormais en charge les produits suivants:

- SurfacePro

- Surface Laptop

>[!NOTE]
>L’outil de création de lecteur USB MicrosoftSurface Data Eraser ne peut pas s’exécuter sur Windows10S. Pour réinitialiser un Surface Laptop exécutant Windows10 S, vous devez d’abord créer le lecteur USB MicrosoftSurface Data Eraser sur un autre ordinateur avec Windows10 Pro ou Windows10 Entreprise.
