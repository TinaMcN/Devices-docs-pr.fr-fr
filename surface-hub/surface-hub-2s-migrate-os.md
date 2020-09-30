---
title: Migrer vers Windows 10 Professionnel ou Entreprise sur Surface Hub 2
description: Cet article décrit le processus de migration de l’équipe Windows 10 sur surface Hub 2 vers Windows 10 professionnel ou Windows 10 entreprise.
keywords: Bureau surface Hub, surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 09/29/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 0c6a52d1023377f51ae6a63879e54b86db16cb9a
ms.sourcegitcommit: 35f64110ce8e0c0b019b02023d746f648f554c1c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/29/2020
ms.locfileid: "11088628"
---
# Migrer vers Windows 10 Professionnel ou Entreprise sur Surface Hub 2

## Introduction

Surface Hub 2 est préinstallé avec l’équipe Windows 10, une édition personnalisée de Windows 10 conçue pour faciliter la collaboration dans les environnements de salle de réunion. À présent, vous avez la possibilité d’exécuter Windows 10 professionnel ou entreprise pour utiliser surface Hub 2S de la même façon que n’importe quel autre PC. 

> [!IMPORTANT]
>Contrairement à une mise à niveau ou une migration classique, il est nécessaire de suivre une procédure d’instructions, comme décrit dans cette page. Avant de continuer, passez en revue les composants de la [solution](#solution-components) et le [flux de travail de migration et d’installation](#migration-and-installation-workflow-summary) .


> [!NOTE]
> Lors de l’installation de Windows 10 professionnel ou entreprise, vous avez besoin d’une nouvelle licence distincte de celle de votre licence d’équipe Windows 10 existante. 


Vous commencez la migration à partir de l’équipe Windows 10 à l’aide d’un PC distinct et du **Configurateur** d’outils de surface (Configurator) pour créer un package contenant un nouveau paramètre UEFI que vous appliquez à surface Hub 2.  Fonction de Configurateur de surface UEFI en tant qu’interface en mode de gestion de surface entreprise (SEMM), conçue pour faciliter la gestion centralisée des paramètres du microprogramme sur les appareils surface dans un environnement d’entreprise. Pour en savoir plus sur SEMM, voir [la documentation du mode de gestion Microsoft surface Enterprise](https://docs.microsoft.com/surface/surface-enterprise-management-mode).
 

## Composants de solution

- Périphérique surface Hub 2 exécutant un système d’exploitation Windows 10
- Autre appareil exécutant Windows 10
- Outil de configuration de surface UEFI pour créer le package SEMM
- Image Windows 10 professionnel ou entreprise du système d’exploitation version 1903 ou ultérieure
- Deux lecteurs USB avec 16 Go de stockage, format FAT32
- Pilotes et microprogrammes pour Windows 10 professionnel sur surface Hub 2, Windows Installer. Fichier MSI
- Connexion Internet
- Solution d’imagerie (facultative)

 
## Résumé du flux de travail de la migration et de l’installation

| Étape  | Action                                                                                                 | Résumé                                                                                                                                                                                                                                                                                                                                                                                                  |
| - | ------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1 | [Vérifier la version UEFI sur surface Hub 2 répond à la configuration minimale requise](#verify-uefi-version-on-surface-hub-2s-meets-minimum-requirements)                                  | Assurez-vous que la version UEFI est 694.2938.768.0 ou ultérieure.                                                                                                                                                                                                                                                                                                                                                      |
| deuxième | [Télécharger les pilotes et le microprogramme du Configurateur de surface UEFI et de surface Hub 2](#download-surface-uefi-configurator-and-surface-hub-2-drivers-and-firmware)                             | Cliquez sur le bouton Télécharger dans la page [Outils surface pour cette](https://www.microsoft.com/download/details.aspx?id=46703) page, puis sélectionnez et téléchargez **surface UEFI Configurator. Et l'** installer sur un PC distinct. Téléchargez les [pilotes et le microprogramme pour Windows 10 professionnel et entreprise sur surface Hub 2. Et enregistrez](https://www.microsoft.com/download/details.aspx?id=101974) -le pour l’utiliser à l’étape 5. |
| 3D | [Préparer le certificat SEMM](#prepare-semm-certificate)                                                                          | Préparez le certificat requis pour l’exécution du configurateur surface UEFI ou utilisez votre certificat actuel.                                                                                                                                                                                                                                                                                                      |
| n°4 | [Créer un package SEMM](#create-semm-package)                                                                               | Lancer le configurateur de surface pour créer un package SEMM sur un lecteur USB qui contient les fichiers de configuration nécessaires à appliquer sur surface Hub 2. Copiez ces fichiers de package SEMM vers un dossier sur votre PC.                                                                                                                                                                                          |
| n°5 | [Préparer le lecteur flash USB contenant l’image Windows 10, le package SEMM, ainsi que les pilotes et le microprogramme pour Windows 10 professionnel ou surface Hub 2](#prepare-usb-flash-drive-containing-windows-10-image-semm-package-and-surface-hub-2-drivers-and-firmware) | Créez un lecteur USB unique (nommé **BOOTME** dans cet exemple) contenant une image Windows 10. Ajoutez vos pilotes et microprogrammes pour Windows 10 professionnel ou entreprise sur surface Hub 2 (étape 2) et SEMM les fichiers de package (étape 4) vers le lecteur **BOOTME** .                                                                                                                                                                                                  |
| 6 | [Mise à jour de UEFI sur surface Hub 2S pour permettre la migration du système d’exploitation](#update-uefi-on-surface-hub-2s-to-enable-os-migration)                                              | Utilisez le lecteur **BOOTME** pour démarrer surface Hub 2 dans le menu UEFI et installez SEMM package.|
| 6 | [Installation de Windows 10 professionnel ou version 1903 ou version ultérieure](#install-windows-10-pro-or-enterprise)                                        | Utilisez le lecteur **BOOTME** pour installer **Windows 10 professionnel ou** version 1903 ou une version ultérieure.                                                                                                                                                                                                                                                                                 |
| version8 | [Installation de pilotes et de microprogrammes pour Windows 10 professionnel et entreprise sur surface Hub 2](#install-surface-hub-2-drivers-and-firmware)                                        | Pour vous assurer que votre périphérique dispose de l’ensemble des mises à jour et pilotes les plus récents, installez les [pilotes et le microprogramme pour Windows 10 professionnel ou surface Hub 2. Fichier MSI](https://www.microsoft.com/download/details.aspx?id=101974)                                                                                                                                                                                                                                                                                  |
| 09 | [Configurer entièrement surface Hub 2S en tant que périphérique de productivité personnel](#next-steps)                                        |  Activez l’ensemble de paramètres et applications recommandés pour optimiser l’utilisation de surface Hub 2S en tant que périphérique de productivité personnel.                                                                                                                                                                                                                                                                    |

### Vérifier la version UEFI sur surface Hub 2 répond à la configuration minimale requise

La version UEFI minimale requise avant la migration de surface hub d’une équipe Windows 10 vers Windows 10 Desktop est **694.2938.768.0**.
 
**Pour vérifier la version UEFI actuelle sur votre système:**

1. Dans l’écran d’accueil de surface Hub 2, sélectionnez **Démarrer** , puis ouvrez l' **SurfaceApp** (surface de**toutes les applications**  >  **Surface**).

2. Sélectionnez **votre surface** pour afficher des informations sur l’appareil surface Hub, y compris la version actuelle de l’interface UEFI sur l’appareil. S’il s’agit de **694.2938.768.0** ou d’une version ultérieure, comme illustré ci-dessous, la version UEFI est éligible pour vous permettre de créer le package SEMM pour la migration du système d’exploitation.

    ![Ouvrir l’application surface & sélectionner votre surface](images/shm-fig1.png)
 
3. Si la version UEFI est antérieure à la version **694.2938.768.0**, vous devez obtenir une version actuelle à l’aide de Windows Update.

**Pour mettre à jour UEFI à partir de Windows Update:**

1. Sur votre surface Hub 2, connectez-vous en tant qu' **administrateur**, accédez à la **All apps**  >  **Settings** >  **mise à jour des**paramètres d’applications et à la sécurité  >  **Windows Update** et installez toutes les mises à jour, puis redémarrez l’appareil. Vérifiez la version UEFI à l’aide de l’application surface. Remarque: Si vous ne connaissez pas votre nom d’utilisateur ou votre mot de passe d’administrateur, vous devez réinitialiser l’appareil. Pour en savoir plus, voir [Réinitialiser et récupérer des éléments MultiSurface](https://docs.microsoft.com/surface-hub/surface-hub-2s-recover-reset).

2. Répétez ces étapes jusqu’à ce que la version UEFI soit **694.2938.768.0** ou une version ultérieure.

3. Si vous ne voyez toujours pas le contrôle UEFI mis à jour après plusieurs tentatives, activez **l’historique des mises à jour** et recherchez les instances des installations de microprogramme ayant échoué. Il est possible que vous deviez réinitialiser**Settings**votre appareil (  >  **mise à jour des paramètres &**  >  **appareil de réinitialisation**de la sécurité).

### Télécharger les pilotes et le microprogramme du Configurateur de surface UEFI et de surface Hub 2

Sur un PC différent:

- Téléchargez Microsoft [surface Configurateur](https://www.microsoft.com/download/details.aspx?id=46703) à partir d’outils surface. Le configurateur surface surface ne peut pas être exécuté sur surface Hub 2, alors que l’équipe Windows 10 est installée.

- Téléchargez [les pilotes surface Hub 2 et le programme d’installation de Windows. Fichier MSI](https://www.microsoft.com/download/details.aspx?id=101974) à appliquer lors de l’installation du nouveau système d’exploitation.

### Préparer le certificat SEMM

S’il s’agit de votre première utilisation du Configurateur de surface pour la première fois, vous devez préparer un certificat. Ce certificat vérifie qu’une fois qu’un appareil est inscrit dans SEMM, seuls les packages créés avec le certificat approuvé peuvent être utilisés pour modifier les paramètres UEFI. Le mode d’acquisition d’un certificat est susceptible de varier selon la taille ou la complexité de votre organisation:

- En général, les grandes entreprises disposent de leur propre infrastructure de certification pour générer des certificats par le biais de pratiques standard en matière de sécurité.

- Les entreprises de taille moyenne et d’autres personnes pourront choisir d’obtenir un certificat de fournisseurs tiers. Cette option est recommandée pour les organisations sans compétences informatiques suffisantes ou par équipe de sécurité informatique dédiée.

- Vous pouvez également générer un certificat auto-signé à l’aide d’un script PowerShell par le biais de la documentation suivante: [exigences de certificat en mode de gestion des entreprises en surface](https://docs.microsoft.com/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements). Vous pouvez utiliser PowerShell pour créer votre propre certificat en fonction de la documentation suivante: [New-SelfSignedCertificate](https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate).

Le package SEMM créé à l’aide de l’outil de configuration de surface UEFI doit être sécurisé avec un certificat pour vérifier la signature des fichiers de configuration avant que les paramètres UEFI puissent être appliqués. Pour en savoir plus, voir documentation sur le [mode de gestion de surface Enterprise](https://docs.microsoft.com/surface/surface-enterprise-management-mode) .
 
 
### Créer un package SEMM

1. Installez les outils de **Configurateur surface UEFI** téléchargés précédemment sur un autre ordinateur. 
2. Ouvrez le **Configurateur surface UEFI** et sélectionnez **Démarrer**.

   ![Ouverture du configurateur surface UEFI](images/shm-fig2.png)
   
3. Sélectionnez **périphériques surface** , puis sélectionnez **suivant**.

   ![Sélectionner des appareils surface](images/shm-fig3.png)
  
4. Sélectionnez **package de configuration**.

   ![Sélectionner le package de configuration](images/shm-fig4.png)
  
5. Sélectionnez **protection des certificats**.

   ![Sélectionner une protection de certificat](images/shm-fig5.png)

6. Vous serez invité à ajouter votre fichier Certificate. pfx.

   ![Vous serez invité à ajouter votre certificat](images/shm-fig6.png)
   
7. Entrez votre **mot de passe de certificat** et sélectionnez **OK**.

   ![Entrez votre mot de passe de certificat et sélectionnez OK.](images/shm-fig7.png)

8. Sélectionnez **protection par mot de passe** pour ajouter un mot de passe pour la surface UEFI. Ce mot de passe est requis chaque fois que vous démarrez l’ordinateur. Il est **vivement recommandé** de définir un mot de passe UEFI que vous utiliserez sur surface Hub 2.

   ![Cliquez sur protection par mot de passe](images/shm-fig8.png)
   
9. Définissez un **mot de passe UEFI** et sélectionnez **OK**.

 > [!IMPORTANT]
   > Enregistrez le mot de passe à un emplacement sécurisé accessible aux administrateurs informatiques de votre organisation responsable de la gestion des hubs de surface. Si le mot de passe est perdu, il n’y a pas de processus de récupération. 

   ![Entrer votre mot de passe UEFI](images/shm-fig9.png)

10. Sélectionnez **surface Hub 2** , puis sélectionnez **suivant**.

   ![Sélectionner surface Hub 2](images/shm-fig10.png)
   
11. Sélectionnez **Suivant**.

    ![Sélectionner suivant](images/shm-fig10a.png)

12. Pour autoriser l’installation de Windows 10 professionnel ou entreprise, sélectionnez **EnableOsMigration.**

    ![Sélectionnez Activer la migration du système d’exploitation](images/shm-fig11.png)
    
13. Définissez **EnableOSMigration** **sur on** et sélectionnez **Next (suivant**).

    ![Définir l’activation de la migration du système d’exploitation](images/shm-fig12.png)

> [!NOTE]
> Lorsque vous appliquez un package SEMM, tous les paramètres UEFI apparaissent comme grisés dans le menu UEFI de l’appareil. Cela inclut les valeurs par défaut pour d’autres paramètres, tels que IPv6 pour le démarrage PXE. Pour modifier les paramètres UEFI, vous devez appliquer un autre package SEMM ou annuler l’inscription de l’appareil à partir de SEMM.

#### Enregistrer le package SEMM sur le lecteur USB

1. Connectez un lecteur USB à votre PC. Sélectionnez **Hub 2** , puis sélectionnez **suivant**.

   ![Sélectionner USB](images/shm-fig13.png)
   
2. Sélectionnez **générer**.

   ![Sélectionner générer](images/shm-fig14.png)

3. Capturez une capture d’écran de cette page, puis sélectionnez **fin**. Votre package SEMM est désormais prêt et contient le package SEMM **DfciUpdate. DFI** et un fichier texte avec l’empreinte SEMM (les deux derniers caractères de l’empreinte numérique du certificat).

   ![Sélectionner fin](images/shm-fig15.png)
   
4. Enregistrez les 2 derniers caractères de l’empreinte de certificat, qui est requis pour activer SEMM lorsque vous appliquez le package sur surface Hub 2.

### Préparer le lecteur flash USB contenant l’image Windows 10, le package SEMM et les pilotes et microprogramme de surface Hub 2

Vous pouvez installer une image Windows 10 professionnel ou entreprise (version 1903 ou ultérieure) en utilisant l’une des options suivantes:

- Votre solution d’imagerie actuelle.

- Le [accélérateur de déploiement de surface](https://docs.microsoft.com/surface/microsoft-surface-deployment-accelerator) vous permet de créer une image Windows 10 amorçable qui peut inclure toutes les mises à jour Windows 10 actuelles, Office, d’autres applications de votre choix, ainsi que les pilotes et le microprogramme nécessaires. 

- CLÉ USB avec Windows 10 professionnel ou image d’entreprise, puis installation de  [pilotes et de microprogrammes pour Windows 10 Pro et Enterprise sur surface Hub 2](https://www.microsoft.com/download/details.aspx?id=101974).
 
Cette procédure décrit la création d’un lecteur flash USB à partir du support d’installation, puis l’ajout des fichiers et pilotes de package SEMM et du microprogramme pour Windows 10 professionnel et entreprise sur surface Hub 2. Fichier MSI. Si vous utilisez d’autres méthodes de déploiement, passez à la section suivante: [mise à jour de UEFI sur surface Hub 2 pour activer la migration du système d’exploitation](#update-uefi-on-surface-hub-2s-to-enable-os-migration).

> [!NOTE]
> Une fois l’installation effectuée, vous aurez besoin d’une licence valide pour Windows 10 professionnel ou Windows 10 entreprise.

1. Pour créer une installation de Windows 10 professionnel, suivez les instructions de la page [Télécharger Windows 10](https://www.microsoft.com/software-download/windows10) pour utiliser l’outil de **création de médias** . Pour télécharger Windows 10 entreprise, accédez au centre de gestion des [licences en volume Microsoft.](https://www.microsoft.com/licensing/servicecenter/default.aspx)

2. Insérez un nouveau lecteur de **stockage USB** . Démarrez l’outil de **création de médias** , sélectionnez créer un **support d’installation** , puis sélectionnez **suivant**.

   ![Créer un support d’installation](images/shm-fig16.png)
   
3. Sélectionnez langue, Windows 10 et 64 bits (x64), puis sélectionnez **suivant**.

   ![Sélectionner la langue, Windows 10 et 64 bits & sélectionner suivant](images/shm-fig17.png)
   
4. Sélectionnez **clé USB** , puis sélectionnez **suivant**.

   ![Sélectionnez lecteur flash USB, puis sélectionnez suivant.](images/shm-fig18.png)
   
5. Lorsque le téléchargement est terminé, sélectionnez **Terminer**.

   ![Sélectionnez terminer](images/shm-fig19.png)
   
6. Copiez les fichiers du package SEMM et les pilotes et le microprogramme pour Windows 10 professionnel ou Enterprise sur surface Hub 2 (. Fichier MSI) à la racine de la clé USB USB (**BOOTME**) contenant votre image Windows 10. Le lecteur USB BOOTME contient les éléments suivants:

    - Image de démarrage de Windows 10
    - Fichiers de package SEMM (copiés à la racine du lecteur USB)
        - DfciUpdate. DFI
        - Fichier texte avec l’empreinte numérique SEMM. (Dans cet exemple: SurfaceUEFI_2020Aug25_1058.txt. La date d’horodatage de la génération automatique correspond à la date à laquelle vous avez créé le fichier à l’aide de surface UEFI Configurator.)
    - Pilotes et microprogrammes pour Windows 10 professionnel et entreprise sur surface Hub 2 (SurfaceHub2S_Win10_18362_20.082.25682.0.msi)

### Mise à jour de UEFI sur surface Hub 2S pour permettre la migration du système d’exploitation

1. Insérez votre lecteur **BOOTME** dans le port USB-A sur surface Hub 2.

2. Pour démarrer dans UEFI:

   1. Première alimentation (arrêt) de votre surface Hub 2.
   1. Appuyez de façon prolongée sur **volume +** , puis appuyez sur le bouton d’alimentation et relâchez le bouton **d’alimentation** .
   1. Maintenez la **touche Ctrl** enfoncée et appuyez sur le menu UEFI.
   
      ![Maintenir le volume en attente + jusqu’à ce que le menu UEFI apparaisse](images/shm-fig20.png)
      
3. Au redémarrage de l’appareil, entrez le mot de passe UEFI que vous avez créé précédemment, le cas échéant (fortement recommandé).

   ![Au redémarrage de l’appareil, entrez votre paassword UEFI.](images/shm-fig22.png)
   
4. Dans le menu UEFI, sélectionnez **Management**  >  **installation de gestion depuis USB**.

   ![Sélectionner gestion & installer à partir du bus USB](images/shm-fig21.png)
   
5. Sélectionnez **redémarrer maintenant**, comme illustré ci-dessous. Le périphérique redémarre et affiche le logo blanc 4 carrés au milieu de l’écran, puis il s’éteint.

   ![Sélectionner redémarrer maintenant](images/shm-fig25.png)
   
6. Appuyez une fois sur le bouton d’alimentation et relâchez le bouton d’alimentation qui s’affiche lorsque vous êtes invité à activer le mode de gestion de l’entreprise surface. 

7. Entrez votre **empreinte de certificat**à deux caractères, votre **mot de passe de paramètres UEFI** , puis sélectionnez **OK**.

   ![Entrez votre empreinte numérique de certificat 2 caractères](images/shm-fig23.png)
 
   > [!NOTE]
   > Dès lors que vous activez SEMM sur votre appareil, le nouveau paramètre UEFI **EnableOSMigration** est appliqué. Vous ne serez plus en mesure d’accéder à l’équipe Windows 10 et devez passer à l’étape suivante et installer Windows 10 professionnel ou Windows 10 entreprise. 

8. Le périphérique redémarre, affiche le logo blanc à 4 carrés au milieu de l’écran, puis il s’éteint de nouveau

### Installation de Windows 10 professionnel ou entreprise

1. Si votre lecteur Windows 10 professionnel ou entreprise amorçable n’est pas déjà installé sur le bus USB surface Hub 2-A port, insérez-le maintenant, puis appuyez sur le bouton d’alimentation et relâchez le bouton d’alimentation.

2. Le périphérique démarre, vous verrez le carré 4 carrés au milieu de l’écran, et vous verrez un cercle de rotation en dessous du logo blanc à quatre carrées.

3. Si l’appareil ne démarre pas automatiquement sur le lecteur USB, éteignez le périphérique (débranchez le cordon d’alimentation et rebranchez-le). Après avoir branché le cordon d’alimentation, le périphérique doit être redémarré après quelques secondes du logo blanc 4 pouces au milieu de l’écran, ou vous pouvez appuyer sur le bouton d’alimentation et le relâcher pour le rallumer. Immédiatement après avoir affiché le logo à quatre carrées au milieu de l’écran, appuyez de façon prolongée sur le bouton de volume vers le bas jusqu’à ce que le cercle en forme de quatrième carré s’affiche.
 
   ![Démarrer vers Windows 10 à partir de la norme USB](images/shm-fig26.png)
   
4. Lorsque le programme OOBE (out-of-Box Experience) est lancé, suivez les instructions d’installation de Windows 10 professionnel ou entreprise (version 1903 ou ultérieure).

### Installer les pilotes et le microprogramme de surface Hub 2

 - Pour vous assurer que votre périphérique dispose de l’ensemble des mises à jour et pilotes les plus récents, installez les [pilotes et le microprogramme pour Windows 10 professionnel ou surface Hub 2](https://www.microsoft.com/download/details.aspx?id=101974).
 
### Étapes suivantes

Pour configurer entièrement surface Hub 2S en tant que périphérique de productivité personnel, reportez-vous à la rubrique [configuration de Windows 10 professionnel ou entreprise sur surface Hub 2](surface-hub-2-post-install.md).

> [!NOTE]
>Si vous ne parvenez pas à effectuer la migration de votre appareil vers Windows 10 professionnel ou entreprise pour surface Hub 2 après avoir suivi les étapes décrites dans ce document, contactez le [support surface Hub](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support).

### Restauration de l’équipe Windows 10

Si vous souhaitez restaurer votre appareil vers l’équipe Windows 10, voir [Réinitialiser et récupérer pour surface Hub 2](surface-hub-2s-recover-reset.md)

## Historique des versions

| Version | Date               | Description                                                                                           |
| ------- | ------------------ | ----------------------------------------------------------------------------------------------------- |
| version. 1,2  | 29 septembre 2020 | Diverses mises à jour des commentaires sur l’utilisation.                                                        |
| version. 1,1  | 15 septembre 2020 | Placement d’une note supplémentaire dans l’introduction clarification des conditions de licence pour l’installation d’un nouveau système d’exploitation. |
| version. 1.0  | 1er septembre 2020  | Nouvel article.                                                                                           |
