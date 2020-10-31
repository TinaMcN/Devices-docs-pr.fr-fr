---
title: Déploiement du Kit de ressources de diagnostic pour Surface Entreprise
description: Cette rubrique explique comment utiliser le kit de gestion de surface diagnostic pour les entreprises.
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 10/12/2020
ms.reviewer: hachidan
manager: laurawi
audience: itpro
ms.openlocfilehash: 97d0a3d76cf9286ca946e08be9f605084084b2ba
ms.sourcegitcommit: 5448f775d3fe177806fce6cbaf0b2b091ed8b7d1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/31/2020
ms.locfileid: "11145959"
---
# Déploiement du Kit de ressources de diagnostic pour Surface Entreprise

Le kit de ressources pour les Diagnostics Microsoft surface pour les entreprises (SDT) permet aux administrateurs informatiques de rechercher rapidement et de résoudre les problèmes liés au matériel, au logiciel et au microprogramme des appareils surface. Vous pouvez exécuter une gamme de tests de diagnostic et de réparations logicielles en plus d’informations sur l’obtention d’informations sur l’état de l’appareil et des instructions pour la résolution des problèmes. 

En particulier, SDT pour les entreprises vous permet d’effectuer les opérations suivantes:

- [Personnaliser le package.](#preparing-the-sdt-package-for-distribution)
- [Exécutez l’application à l’aide de commandes.](surface-diagnostic-toolkit-command-line.md)
- [Exécutez plusieurs tests matériels pour résoudre les problèmes.](surface-diagnostic-toolkit-desktop-mode.md#multiple)
- [Génération de journaux pour l’analyse des problèmes.](surface-diagnostic-toolkit-desktop-mode.md#logs)
- [Obtenez un rapport détaillé comparant la configuration de l’appareil et de l’appareil.](surface-diagnostic-toolkit-desktop-mode.md#detailed-report)


## Principaux scénarios et ressources de téléchargement 

Pour exécuter SDT pour les entreprises, téléchargez les composants indiqués dans le tableau suivant.


Mode |  Principaux scénarios | Télécharger | En savoir plus
--- | --- | --- | ---
Mode bureau |  Aidez les utilisateurs à exécuter SDT sur leurs appareils surface pour résoudre les problèmes.<br>Créer un package personnalisé à déployer sur un ou plusieurs appareils de surface permettant aux utilisateurs de sélectionner des journaux spécifiques à collecter et analyser. | Package MSI du SDT distribuable:<br>Programme d’installation du kit de connaissances Microsoft surface diagnostic pour les entreprises<br>[Outils Surface pour l'informatique](https://www.microsoft.com/download/details.aspx?id=46703) | [Utiliser le kit de diagnostic de surface pour le mode Bureau](surface-diagnostic-toolkit-desktop-mode.md)
Ligne de commande |  Résoudre les problèmes liés aux appareils surface à distance sans interaction utilisateur, à l’aide d’outils standard tels que Configuration Manager. Il inclut les commandes suivantes:<br>`-DataCollector` recueille tous les fichiers journaux<br>`-bpa` exécute des diagnostics d’intégrité à l’aide de la méthode recommandée Analyzer.<br>`-windowsupdate` vérifie Windows Update pour les mises à jour de microprogramme ou de pilote manquantes.<br>`-warranty` vérifie les informations de garantie. <br><br>| Application console SDT:<br>Console d’application Diagnostics Microsoft surface<br>[Outils Surface pour l'informatique](https://www.microsoft.com/download/details.aspx?id=46703) | [Exécuter le kit de diagnostics de surface](surface-diagnostic-toolkit-command-line.md)

## Appareils pris en charge 

Le SDT pour les entreprises est pris en charge sur les appareils surface 3 et les versions ultérieures, notamment:

- Surface Laptop Go
- SurfaceBook3
- SurfaceGo2
- SurfaceProX
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

## Installation de surface diagnostic Toolkit pour les entreprises

Pour créer un package SDT que vous pouvez distribuer aux utilisateurs de votre organisation:

1. Connectez-vous à votre périphérique surface en utilisant le compte administrateur.
2. Téléchargez le package Windows Installer (. msi) de l' [application outils surface pour le téléchargement](https://www.microsoft.com/download/details.aspx?id=46703) , puis copiez-le dans un emplacement préféré sur votre appareil surface, tel que le bureau.
3. L’Assistant Installation de SDT s’affiche, comme illustré dans la figure 1. Cliquez sur **Suivant**. 

    >[!NOTE]
    >S’il n’apparaît pas, vérifiez que vous êtes connecté au compte d’administrateur sur votre ordinateur. 

    ![Bienvenue dans l’Assistant Installation de surface diagnostic Toolkit](images/sdt-1.png)

    *Figure1. Assistant de configuration du kit de diagnostics surface*

4. Lorsque l’Assistant Configuration de SDT s’affiche, cliquez sur **suivant**, acceptez le contrat de licence utilisateur final (CLUF).

5. Dans l’écran Options d’installation, modifiez l’emplacement d’installation par défaut si vous le souhaitez. 
6. Sous type d’installation, sélectionnez **avancé**. 

    >[!NOTE]
    >L’option standard permet aux utilisateurs d’exécuter l’outil de diagnostic directement sur leur appareil surface, à condition qu’ils soient connectés à leur appareil à l’aide d’un compte d’administrateur. 
    
     ![Options d’installation: options avancées](images/sdt-install.png)

7. Cliquez sur **suivant** , puis sur **installer**. 

## Installation à l’aide de la ligne de commande
Si vous le souhaitez, vous pouvez installer le SDT à l’invite de commandes et définir un indicateur personnalisé pour installer l’outil en mode administrateur. Le SDT contient les indicateurs d’option d’installation suivants:

- `SENDTELEMETRY` envoie les données de télémétrie à Microsoft. L’indicateur accepte `0` pour désactivé ou `1` activé. La valeur par défaut consiste `1` à envoyer la télémétrie.
- `ADMINMODE` configure l’outil pour qu’il soit installé en mode administrateur. L’indicateur accepte `0` pour le mode client ou `1` pour le mode administrateur informatique. La valeur par défaut est `0`.

### Pour installer le SDT à partir de la ligne de commande:

1. Ouvrez une invite de commandes et entrez:

    ```
    msiexec.exe /i <the path of installer> ADMINMODE=1. 
    ```
    **Exemple:**

    ```
    C:\Users\Administrator> msiexec.exe/I"C:\Users\Administrator\Desktop\Microsoft_Surface_Diagnostic_Toolkit_for_Business_Installer.msi" ADMINMODE=1
    ```

## Localisation du SDT sur votre appareil surface

Le SDT et la console de l’application SDT sont tous deux installés sur `C:\Program Files\Microsoft\Surface\Microsoft Surface Diagnostic Toolkit for Business` .

Outre le fichier. exe, SDT installe un fichier JSON et un fichier admin.dll (modules\admin.dll), comme illustré dans la figure 2.

![Liste des fichiers du SDT installés dans l’Explorateur de fichiers](images/sdt-2.png)

*Figure2. Fichiers installés par SDT*

## Préparation du package SDT à des fins de distribution

La création d’un package personnalisé vous permet de cibler l’outil vers des problèmes connus spécifiques.

1. Cliquez sur **démarrer > exécuter**, entrez **surface** , puis cliquez sur **Kit de diagnostics de surface pour les entreprises**. 
2. Lorsque l’outil s’ouvre, cliquez sur **créer un package personnalisé**, comme illustré dans la figure 3.

    ![Option créer un package personnalisé](images/sdt-3.png)

    *Figure3. Créer un package personnalisé*

### Paramètres de langue et de télémétrie

  Lors de la création d’un package, vous pouvez sélectionner des paramètres de langue ou annuler l’envoi d’informations de télémétrie à Microsoft. Par défaut, le SDT envoie la télémétrie à Microsoft qui est utilisée pour améliorer l’application conformément à la [déclaration de confidentialité de Microsoft](https://privacy.microsoft.com/privacystatement). Si vous souhaitez le décliner, désactivez la case à cocher lors de la création d’un package personnalisé, comme illustré ci-dessous. Vous pouvez activer ou désactiver la case à cocher **Envoyer un télémétrie à Microsoft** sur la page **options d’installation** lors de la configuration de SDT. 

>[!NOTE]
>Ce paramètre n’a pas d’incidence sur le niveau de télémétrie minimal stocké automatiquement sur les serveurs Microsoft lors de l’exécution de tests et de réparations qui nécessitent une connexion Internet (par exemple, Windows Update et la réparation du logiciel) ou la fourniture de commentaires à l’aide des boutons sourire ou Smiley de la barre d’outils de l’application. 


![Sélectionner les paramètres de langue et de télémétrie](images/sdt-4.png)

*Figure4. Sélectionner les paramètres de langue et de télémétrie*


### Page Windows Update

Sélectionnez l’option adaptée à votre organisation. La plupart des organisations qui utilisent plusieurs utilisateurs peuvent généralement sélectionner pour recevoir des mises à jour via Windows Server Update Services (WSUS), comme illustré dans la figure 5. Si vous utilisez des packages de mise à jour Windows locaux ou WSUS, entrez le chemin d’accès selon le cas. 

![Sélectionner l’option Windows Update](images/sdt-5.png)

*Figure5. Option Windows Update*

### Page de réparation du logiciel

Cela vous permet de sélectionner ou de supprimer l’option d’exécution des mises à jour de réparation de logiciels. 

![Sélectionner l’option de réparation logicielle](images/sdt-6.png)

*Figure6. Option de réparation de logiciels*

### Page de collecte des journaux et enregistrement de package

Vous pouvez choisir d’exécuter une large gamme de journaux entre les applications, les pilotes, le matériel et le système d’exploitation. Cliquez sur la zone appropriée et sélectionnez-en un dans le menu de journaux disponibles. Vous pouvez ensuite enregistrer le package dans un point de distribution de logiciels ou un emplacement équivalent auquel les utilisateurs peuvent accéder. 

![Sélectionner les options de journalisation](images/sdt-7.png)

*Figure7. Option journal et enregistrer le package*

## Étapes suivantes

- [Utiliser le Kit de ressources de diagnostic pour Surface Entreprise en mode bureau](surface-diagnostic-toolkit-desktop-mode.md)
- [Utiliser les commandes de la trousse à outils de diagnostic de surface pour les entreprises](surface-diagnostic-toolkit-command-line.md)

## Modifications et mises à jour

### Version 2.124.139.0

Cette version du kit de diagnostics de surface pour les entreprises ajoute une prise en charge pour les éléments suivants:

- Support intégré transparente
- Enregistrer tous les résultats des tests
- Vérifier que l’image est créée personnalisé
- Inclure les avertissements du gestionnaire de périphériques
- Version du microprogramme du Dock
- Marquer des lecteurs comme des échecs potentiels dans le test de stockage
- Supprimer le lien vers le magasin 

### Version 2.121.139
*Date de publication: 31 2020 juillet*<br>
Cette version du kit de diagnostics de surface pour les entreprises ajoute une prise en charge pour les éléments suivants:

- Une prise en charge transparente
- Correction de bogues

### Version 2.94.139.0
*Date de publication: 11 2020*<br>
Cette version du kit de diagnostics de surface pour les entreprises ajoute une prise en charge pour les éléments suivants:

- Possibilité d’ignorer Windows Update pour procéder à la vérification matérielle.
- Possibilité de recevoir des notifications concernant la dernière mise à jour de la version
- SurfaceGo2
- SurfaceBook3
- Afficher l’indicateur de progression


### Version 2.43.139.0
*Date de publication: 21 octobre 2019*<br>
Cette version du kit de diagnostics de surface pour les entreprises ajoute une prise en charge pour les éléments suivants:

- SurfacePro7
- Surface Laptop3

### Version 2.42.139.0
*Date de publication: 24 septembre 2019*<br>
Cette version du kit de diagnostics de surface pour les entreprises ajoute une prise en charge pour les éléments suivants: 
- Possibilité de télécharger des rapports de matériel.
- Possibilité de contacter le support Microsoft directement à partir de l’outil. <br>

### Version 2.41.139.0
*Date de publication: 24 juin 2019*<br>
Cette version du kit de diagnostics de surface pour les entreprises ajoute une prise en charge pour les éléments suivants: 
- Informations de version du pilote intégrées aux journaux et au rapport.
- Possibilité de fournir des commentaires sur l’application.<br>


### Version 2.36.139.0
*Date de publication: 26 avril 2019*<br>
Cette version du kit de diagnostics de surface pour les entreprises ajoute une prise en charge pour les éléments suivants: 
- Option de configuration avancée permettant de déverrouiller les fonctionnalités d’administration par le biais de l’interface utilisateur du programme d’installation, sans nécessiter de configuration de ligne
- Améliorations apportées à l’accessibilité.
- Paramètres de contrôle de surface de surface intégrés aux journaux.
- Lien support de compatibilité du moniteur externe dans le générateur de rapports.
