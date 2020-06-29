---
title: Sécuriser et gérer les plateformes de surface Hub 2 avec SEMM
description: En savoir plus sur la protection des éléments de surface Hub 2 avec SEMM.
keywords: séparer les valeurs par des virgules
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 06/20/2019
ms.localizationpriority: Medium
ms.openlocfilehash: 03ce1dfa48ade8aade545c63818ca5ae8947e6b7
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832970"
---
# Sécuriser et gérer les SurfaceHub2S avec SEMM et UEFI

Nouveauté de surface Hub 2, vous pouvez utiliser SEMM pour gérer le paramètre UEFI de l’appareil.
Utilisez le configurateur Microsoft surface UEFI pour contrôler les composants suivants:

- Réseau local câblé
- Appareils photo
- Bluetooth
- Wi-Fi
- Capteur d’occupation

Utilisez le configurateur Microsoft surface UEFI pour activer ou désactiver les paramètres UEFI suivants:

- Démarrage

    - IPv6 pour démarrage PXE
    - Autre démarrage
    - Verrou d’ordre de démarrage
    - Démarrage USB
- Page frontale UEFI

    - Périphériques
    - Démarrage
    - Date/Heure

## Image de la création d’une configuration UEFI

Contrairement aux autres appareils surface, vous ne pouvez pas utiliser un fichier MSI ou une image de type Win PE pour appliquer ces paramètres sur surface Hub 2. Au lieu de cela, vous devez créer une image USB à charger dans l’appareil. Pour créer une image de configuration UEFI surface Hub 2S, téléchargez et installez la dernière version du programme d’installation de Microsoft surface UEFI à partir de la page [Outils surface pour cette application](https://www.microsoft.com/download/details.aspx?id=46703) dans le centre de téléchargement Microsoft. Pour plus d’informations sur l’utilisation de UEFI et de SEMM, voir mode de gestion de l' [entreprise Microsoft surface](https://docs.microsoft.com/surface/surface-enterprise-management-mode).

## Pour configurer UEFI sur surface Hub 2

1. Démarrez le configurateur UEFI, puis, dans le premier écran, sélectionnez **package de configuration**.<br><br>
![* Démarrez le configurateur UEFI et sélectionnez package de configuration *](images/sh2-uefi1.png) <br> <br>
2. Pour ajouter le certificat à votre package, vous devez disposer d’un certificat valide avec la clé privée au format de fichier. pfx pour signer et protéger le package. Sélectionnez **+ protection des certificats.** <br>
![* Sélectionnez + protection de certificat *](images/sh2-uefi2.png) <br><br>
3. Entrez le mot de passe de la clé privée du certificat.<br>
![* Entrez le mot de passe de la clé privée du certificat *](images/sh2-uefi3.png) <br><br>
4. Après avoir importé la clé privée, continuez à créer le package.<br>
![* Continuer à créer le package *](images/sh2-uefi4.png) <br><br>
5. Sélectionnez **Hub** and **surface Hub 2** en tant que cible pour le package de configuration UEFI.<br>
![* Sélectionnez Hub and surface Hub 2 en tant que cible pour le package de configuration UEFI *](images/sh2-uefi5.png) <br><br>
6. Choisissez les composants et les paramètres que vous souhaitez activer ou désactiver sur surface Hub 2.<br>
![* Sélectionnez les composants et les paramètres que vous souhaitez activer ou désactiver *.](images/sh2-uefi6.png) <br><br>
7. Utilisez l’option USB pour exporter le fichier.<br>
![* Utiliser l’option USB pour exporter le fichier *](images/sh2-uefi8.png) <br><br>
8. Insérez et sélectionnez la clé USB que vous voulez utiliser pour ce package. Le lecteur USB sera formaté et vous perdez toutes les informations dont vous disposez.<br>
![* Insérez et sélectionnez le lecteur USB de votre coffret *](images/sh2-uefi9.png) <br><br>
9. Lors de la création réussie du package, le programme de configuration affiche les deux derniers caractères de l’empreinte de votre certificat. Vous avez besoin de ces caractères lorsque vous importez des éléments dans la configuration en surface Hub 2.<br>
![* Configuration de package * réussie](images/sh2-uefi10.png) <br>

## Pour démarrer dans UEFI

Désactivez l’option surface Hub 2. Appuyez de façon prolongée sur le bouton **monter le volume** et appuyez sur le bouton **d’alimentation** . Maintenez la touche enfoncée jusqu’à ce que le menu UEFI apparaisse.
