---
title: Mise à jour du microprogramme de stylet sur surface Hub 2
description: Cette page décrit comment mettre à jour le microprogramme pour le stylet surface Hub 2.
keywords: séparer les valeurs par des virgules
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 02/26/2020
ms.localizationpriority: Medium
ms.openlocfilehash: c0ad8f275d2476e42c9a5bd3f1130fbca85a5599
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10833054"
---
# Mise à jour du microprogramme de stylet sur surface Hub 2

Vous pouvez mettre à jour le microprogramme sur un stylet surface Hub 2 à partir de Windows Update pour les entreprises ou en téléchargeant la mise à jour du microprogramme sur un autre ordinateur. La mise à jour du microprogramme est disponible dans Windows Update à compter du 26 février 2020. 

## Mise à jour du microprogramme du stylo à l’aide de Windows Update pour les entreprises

Cette section explique comment mettre à jour le microprogramme du stylo par le biais des cycles de maintenance automatisés pour Windows Update, configurés par défaut pour se produire de manière nocturne à 3 heures. Vous devrez prévoir deux cycles de maintenance pour pouvoir terminer l’installation de la mise à jour du stylet surface Hub 2. Vous pouvez également utiliser Windows Server Update Services (WSUS) pour appliquer le microprogramme de stylet. Pour plus d’informations, consultez [gestion des mises à jour Windows sur surface Hub](manage-windows-updates-for-surface-hub.md).

1. Assurez-vous que le stylet surface Hub 2 est couplé aux éléments surface Hub 2: appuyez longuement sur le bouton du **haut** jusqu’à ce que le témoin lumineux de l’indicateur de blanche clignote. <br>
![Stylet surface Hub 2](images/sh2-pen-1.png) <br>
2. Sur surface Hub, ouvrez une session en tant qu’administrateur, ouvrez **paramètres**, puis recherchez de nouveaux appareils Bluetooth.
3. Sélectionnez le stylet pour terminer le processus de jumelage.
4. Appuyez sur le bouton du **haut** du stylo pour appliquer la mise à jour. L’opération risque de durer jusqu’à 2 heures.

## Mettez à jour le microprogramme du stylo en le téléchargeant sur un PC distinct

Vous pouvez mettre à jour le microprogramme sur un stylet surface Hub 2 à partir d’un autre PC exécutant Windows 10. Cette méthode vous permet également de vérifier que le microprogramme du stylo a été correctement mis à jour avec la version la plus récente.

1. Couplez le stylet surface Hub 2 à votre PC compatible Bluetooth: Appuyez de façon prolongée sur le bouton du **haut** jusqu’à ce que le témoin lumineux de l’indicateur blanche clignote. <br>
![Stylet surface Hub 2](images/sh2-pen-1.png) <br>
2. Sur le PC, recherchez les nouveaux appareils Bluetooth.
3. Sélectionnez le stylet pour terminer le processus de jumelage.
4. Déconnectez tous les autres stylets surface Hub avant de commencer une nouvelle mise à jour.
3. Téléchargez l' [outil de mise à jour du microprogramme de surface Hub 2](https://download.microsoft.com/download/8/3/F/83FD5089-D14E-42E3-AF7C-6FC36F80D347/Pen_Firmware_Tool.zip) sur votre PC.
4. Exécutez **PenCfu.exe.** La progression de l’installation s’affiche dans l’outil. La mise à jour risque de durer quelques minutes. 


## Vérifier la version du microprogramme de PEN surface Hub 2

1. Exécutez **get_version.bat** et appuyez sur le bouton du **haut** du stylo.
2. L’outil rapportera la version du microprogramme du stylo. Exemple :
    - L’ancien microprogramme est 468.2727.368
    - Le nouveau microprogramme est 468.2863.369

## Options de ligne de commande

Vous pouvez exécuter l’outil de mise à jour de la mise à jour du microprogramme de surface Hub 2 (PenCfu.exe) depuis la ligne de commande.

1. Couplez le stylo à votre PC et cliquez sur le bouton du **haut** du stylo.
2. Double-cliquez sur **PenCfu.exe** pour lancer la mise à jour du microprogramme. Notez que le fichier de configuration et les fichiers image du microprogramme doivent être stockés dans le même dossier que l’outil.
3. Pour accéder à d’autres options, exécutez **PenCfu.exe-h** pour afficher les paramètres disponibles, comme indiqué dans le tableau suivant.  
    - Exemple: PenCfu.exe-h
4. Pour fermer l’outil, **Appuyez sur Ctrl + C** .

 

| **Commande**    | **Description**                                                                                                                                                                                                                                                                                                                                                                                |
| -------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| -h-aide        | Outils d’affichage de l’interface de ligne de commande et de sortie.                                                                                                                                                                                                                                                                                                                                             |
| version-v     | Affichez la version de l’outil d’affichage et quittez.                                                                                                                                                                                                                                                                                                                                                                 |
| Journal-l-filtre  | Définissez un niveau de filtre pour le fichier journal. Les messages du journal disposent de 4 niveaux possibles: déboguer (le plus petit), informations, avertissement et erreur (plus haut). La définition d’un niveau de filtre du journal filtre les messages dans un seul message de niveau supérieur. Par exemple, si le niveau de filtre est défini sur WARNING, seuls les messages d’avertissement et d’erreur sont enregistrés. Par défaut, cette option est désactivée, ce qui désactive la journalisation. |
| -g get-version | Si ce paramètre est spécifié, l’outil obtient uniquement la version de microcontrôle du stylo connecté qui correspond au fichier de configuration qui est stocké dans le même dossier que l’outil.                                                                                                                                                                                                                                    