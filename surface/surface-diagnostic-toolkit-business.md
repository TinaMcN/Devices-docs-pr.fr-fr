---
title: Déploiement du Kit de ressources de diagnostic pour Surface Entreprise
description: Cette rubrique explique comment utiliser surface Diagnostic Shared Computer Toolkit for Business.
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 01/15/2021
ms.reviewer: hachidan
manager: laurawi
audience: itpro
ms.openlocfilehash: 227463e484a6f3b933fc1118d9dec058f93074a8
ms.sourcegitcommit: 1053479c191fd10651d31a466fad1769fb0cd28b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/16/2021
ms.locfileid: "11271578"
---
# Déploiement du Kit de ressources de diagnostic pour Surface Entreprise

Le Microsoft Surface Diagnostic Shared Computer Toolkit for Business (SDT) permet aux administrateurs informatiques d’examiner, dépanner et résoudre rapidement les problèmes matériels, logiciels et microprogrammes avec les appareils Surface. Vous pouvez exécuter une série de tests de diagnostic et de réparations logicielles en plus d’obtenir des informations sur l’état de l’appareil et des conseils pour résoudre les problèmes. 

Plus précisément, SDT entreprise vous permet de :

- [Personnalisez le package.](#preparing-the-sdt-package-for-distribution)
- [Exécutez l’application à l’aide de commandes.](surface-diagnostic-toolkit-command-line.md)
- [Exécutez plusieurs tests matériels pour résoudre les problèmes.](surface-diagnostic-toolkit-desktop-mode.md#multiple)
- [Générer des journaux pour l’analyse des problèmes.](surface-diagnostic-toolkit-desktop-mode.md#logs)
- [Obtenir un rapport détaillé comparant l’appareil et la configuration optimale.](surface-diagnostic-toolkit-desktop-mode.md#detailed-report)


## Scénarios principaux et ressources de téléchargement 

Pour exécuter SDT entreprise, téléchargez les composants répertoriés dans le tableau suivant.


Mode |  Scénarios principaux | Télécharger | Si vous souhaitez en savoir plus
--- | --- | --- | ---
Mode bureau |  Aider les utilisateurs à l’exécution de SDT sur leurs appareils Surface pour résoudre les problèmes.<br>Créez un package personnalisé à déployer sur un ou plusieurs appareils Surface, ce qui permet aux utilisateurs de sélectionner des journaux spécifiques à collecter et à analyser. | Package MSI distribuable SDT :<br>Microsoft Surface Diagnostic Toolkit for Business Installer<br>[Outils Surface pour l'informatique](https://www.microsoft.com/download/details.aspx?id=46703) | [Utiliser surface Diagnostic Shared Computer Toolkit en mode bureau](surface-diagnostic-toolkit-desktop-mode.md)
Ligne de commande |  Dépanner directement les appareils Surface à distance sans intervention de l’utilisateur, à l’aide d’outils standard tels que Configuration Manager. Il inclut les commandes suivantes :<br>`-DataCollector` collecte tous les fichiers journaux<br>`-bpa` exécute des diagnostics d’état à l’aide de Best Practice Analyzer.<br>`-windowsupdate` recherche des mises à jour du microprogramme ou des pilotes manquantes dans Windows Update.<br>`-warranty` vérifie les informations de garantie. <br><br>| Application console SDT :<br>Microsoft Surface Diagnostics App Console<br>[Outils Surface pour l'informatique](https://www.microsoft.com/download/details.aspx?id=46703) | [Exécuter surface Diagnostic Shared Computer Toolkit à l’aide de commandes](surface-diagnostic-toolkit-command-line.md)

## Appareils pris en charge 

SDT entreprise est pris en charge sur les appareils Surface 3 et ultérieurs, notamment :

- Surface Book - toutes les générations
- Surface Go - toutes les générations
- Surface Laptop - toutes les générations
- Surface Pro 3 et les ultérieures
- Surface Pro X - toutes les générations
- Surface Studio - toutes les générations
- VersionsLTE du modèleSurface3
- Surface3


## Installation de Surface Diagnostic Shared Computer Toolkit for Business

Pour créer un package SDT que vous pouvez distribuer aux utilisateurs de votre organisation :

1. Connectez-vous à votre appareil Surface à l’aide du compte Administrateur.
2. Téléchargez le package Windows Installer SDT (.msi) à partir de la page de téléchargement des outils [Surface pour](https://www.microsoft.com/download/details.aspx?id=46703) l’informatique et copiez-le à un emplacement préféré sur votre appareil Surface, tel que Bureau.
3. L’Assistant Installation de SDT apparaît, comme illustré dans la figure 1. Cliquez sur **Suivant**. 

    >[!NOTE]
    >Si l’Assistant Installation n’apparaît pas, assurez-vous que vous êtes bien inscrit au compte Administrateur sur votre ordinateur. 

    ![Bienvenue dans l’Assistant Installation de Surface Diagnostic Shared Computer Toolkit](images/sdt-1.png)

    *Figure1. Assistant Installation de Shared Computer Toolkit diagnostic Surface*

4. Lorsque l’Assistant Configuration de SDT s’affiche, cliquez sur **Suivant**, acceptez le contrat de licence utilisateur final (CLLA)

5. Dans l’écran Options d’installation, modifiez l’emplacement d’installation par défaut si vous le souhaitez. 
6. Sous Type d’installation, sélectionnez **Avancé.** 

    >[!NOTE]
    >L’option standard permet aux utilisateurs d’exécuter l’outil de diagnostic directement sur leur appareil Surface à condition qu’ils soient connectés à leur appareil à l’aide d’un compte Administrateur. 
    
     ![Options d’installation : avancé](images/sdt-install.png)

7. Cliquez **sur Suivant,** puis sur **Installer.** 

## Installation à l’aide de la ligne de commande
Si vous le souhaitez, vous pouvez installer SDT à une invite de commandes et définir un indicateur personnalisé pour installer l’outil en mode administrateur. SDT contient les indicateurs d’option d’installation suivants :

- `SENDTELEMETRY` envoie des données de télémétrie à Microsoft. L’indicateur accepte `0` désactivé ou `1` activé. La valeur par défaut est `1` d’envoyer la télémétrie.
- `ADMINMODE` configure l’outil à installer en mode administrateur. L’indicateur accepte `0` le mode client ou le mode Administrateur `1` informatique. La valeur par défaut est `0`.

### Pour installer SDT à partir de la ligne de commande :

1. Ouvrez une invite de commandes et entrez :

    ```
    msiexec.exe /i <the path of installer> ADMINMODE=1. 
    ```
    **Exemple:**

    ```
    C:\Users\Administrator> msiexec.exe/I"C:\Users\Administrator\Desktop\Microsoft_Surface_Diagnostic_Toolkit_for_Business_Installer.msi" ADMINMODE=1
    ```

## Localisation de SDT sur votre appareil Surface

SDT et la console d’application SDT sont installés sur `C:\Program Files\Microsoft\Surface\Microsoft Surface Diagnostic Toolkit for Business` .

Outre le fichier .exe, SDT installe un fichier JSON et un fichier admin.dll (modules\admin.dll), comme le montre la figure 2.

![liste des fichiers SDT installés dans l’Explorateur de fichiers](images/sdt-2.png)

*Figure2. Fichiers installés par SDT*

## Préparation du package SDT pour la distribution

La création d’un package personnalisé vous permet de cibler l’outil sur des problèmes connus spécifiques.

1. Cliquez **sur Démarrer >,** entrez **Surface,** puis cliquez sur **Surface Diagnostic Shared Computer Toolkit Entreprise.** 
2. Lorsque l’outil s’ouvre, cliquez sur **Créer un package personnalisé,** comme illustré dans la figure 3.

    ![Option Créer un package personnalisé](images/sdt-3.png)

    *Figure3. Créer un package personnalisé*

### Paramètres de langue et de télémétrie

  Lors de la création d’un package, vous pouvez sélectionner des paramètres de langue ou refuser l’envoi d’informations de télémétrie à Microsoft. Par défaut, SDT envoie à Microsoft une télémétrie qui est utilisée pour améliorer l’application conformément à la déclaration de confidentialité [de Microsoft.](https://privacy.microsoft.com/privacystatement) Si vous souhaitez refuser, cochez la case lors de la création d’un package personnalisé, comme illustré ci-dessous. Vous pouvez également effacer **la case à cocher Envoyer** la télémétrie à Microsoft dans la page **Options** d’installation pendant l’installation de SDT. 

>[!NOTE]
>Ce paramètre n’affecte pas la télémétrie minimale automatiquement stockée sur les serveurs Microsoft lors de l’exécution de tests et de réparations qui nécessitent une connexion Internet, telle que Windows Update et la réparation logicielle, ou lorsque vous fournissez des commentaires à l’aide des boutons Souris ou Désapprouver dans la barre d’outils de l’application. 


![Sélectionner les paramètres de langue et de télémétrie](images/sdt-4.png)

*Figure4. Sélectionner les paramètres de langue et de télémétrie*


### Page Windows Update

Sélectionnez l’option appropriée pour votre organisation. La plupart des organisations avec plusieurs utilisateurs choisissent généralement de recevoir des mises à jour via Windows Server Update Services (WSUS), comme illustré dans la figure 5. Si vous utilisez des packages Windows Update locaux ou WSUS, entrez le chemin d’accès le cas échéant. 

![Sélectionner l’option Windows Update](images/sdt-5.png)

*Figure5. Option Windows Update*

### Page Réparation des logiciels

Cela vous permet de sélectionner ou de supprimer l’option permettant d’exécuter des mises à jour de réparation logicielle. 

![Sélectionner l’option de réparation logicielle](images/sdt-6.png)

*Figure6. Option de réparation logicielle*

### Collecte des journaux et enregistrement de la page du package

Vous pouvez choisir d’exécuter un large éventail de journaux sur les applications, les pilotes, le matériel et le système d’exploitation. Cliquez sur la zone appropriée et sélectionnez-la dans le menu des journaux disponibles. Vous pouvez ensuite enregistrer le package dans un point de distribution de logiciels ou un emplacement équivalent accessible aux utilisateurs. 

![Sélectionner les options du journal](images/sdt-7.png)

*Figure7. Option Journal et package d’enregistrer*

## Étapes suivantes

- [Utiliser le Kit de ressources de diagnostic pour Surface Entreprise en mode bureau](surface-diagnostic-toolkit-desktop-mode.md)
- [Utiliser surface Diagnostic Shared Computer Toolkit for Business à l’aide de commandes](surface-diagnostic-toolkit-command-line.md)

## Modifications et mises à jour

### Version 2.131.139.0

Cette version de Surface Diagnostic Shared Computer Toolkit for Business ajoute la prise en charge des produits suivants :

- Prise en charge de Surface Pro 7+
- Expérience de prise en charge transparente sur Surface Pro X
- Améliorations de la sécurité
- Améliorations de l’expérience utilisateur inclusive

### Version 2.124.139.0

Cette version de Surface Diagnostic Shared Computer Toolkit for Business ajoute la prise en charge des produits suivants :

- Prise en charge intégrée transparente
- Enregistrer tous les résultats des tests
- Vérifier si l’image est personnalisée créée
- Inclure les avertissements du Gestionnaire de périphériques
- Version du microprogramme de station d’accueil
- Indicateur des lecteurs comme des défaillances potentielles dans le test de stockage
- Supprimer le lien de la boutique 

### Version 2.121.139
*Date de publication : 31 juillet 2020*<br>
Cette version de Surface Diagnostic Shared Computer Toolkit for Business ajoute la prise en charge des produits suivants :

- Expérience de support transparente
- Résolutions de bogues

### Version 2.94.139.0
*Date de publication : 11 mai 2020*<br>
Cette version de Surface Diagnostic Shared Computer Toolkit for Business ajoute la prise en charge des produits suivants :

- Possibilité d’ignorer Windows Update pour effectuer une vérification matérielle.
- Possibilité de recevoir des notifications concernant la dernière mise à jour de version
- SurfaceGo2
- SurfaceBook3
- Afficher l’indicateur de progression


### Version 2.43.139.0
*Date de publication : 21 octobre 2019*<br>
Cette version de Surface Diagnostic Shared Computer Toolkit for Business ajoute la prise en charge des produits suivants :

- SurfacePro7
- Surface Laptop3

### Version 2.42.139.0
*Date de publication : 24 septembre 2019*<br>
Cette version de Surface Diagnostic Shared Computer Toolkit for Business ajoute la prise en charge des produits suivants : 
- Possibilité de télécharger des rapports matériels.
- Possibilité de contacter le Support Microsoft directement à partir de l’outil. <br>

### Version 2.41.139.0
*Date de publication : 24 juin 2019*<br>
Cette version de Surface Diagnostic Shared Computer Toolkit for Business ajoute la prise en charge des produits suivants : 
- Informations sur la version du pilote incluses dans les journaux et les rapports.
- Possibilité de fournir des commentaires sur l’application.<br>


### Version 2.36.139.0
*Date de publication : 26 avril 2019*<br>
Cette version de Surface Diagnostic Shared Computer Toolkit for Business ajoute la prise en charge des produits suivants : 
- Option d’installation avancée pour déverrouiller les fonctionnalités d’administration via l’interface utilisateur du programme d’installation, sans nécessiter de configuration de ligne de commande.
- Améliorations en matière d’accessibilité.
- Paramètres de contrôle de luminosité de surface inclus dans les journaux.
- Lien de prise en charge de la compatibilité du moniteur externe dans le générateur de rapports.
