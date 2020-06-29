---
title: Présentation technique de surface Book 3 GPU
description: Cet article fournit une évaluation technique des capacités du GPU sur les modèles surface Book 3.
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 5/06/2020
ms.reviewer: brrecord
manager: laurawi
audience: itpro
ms.openlocfilehash: a3bfe6eec313c9cd9a38f966a1bed46fbc1ca92b
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832231"
---
# Présentation technique de surface Book 3 GPU

## Introduction

Surface Book 3, le portable surface le plus puissant qui a été mis à jour, intègre des fonctionnalités de calcul et graphiques entièrement modernes dans leur facteur de forme amovible.  Dirigé par le cœur 4 de 10e GEN Intel® Core™ i7 et NVIDIA® Quadro RTX 3000™ Unity Processing Unit (GPU) sur le modèle 15 pouces, surface Book 3 est une gamme de configurations destinées aux particuliers, aux professionnels de l’informatique, aux architectes, aux ingénieurs et aux scientifiques de données. Cet article décrit les principales différences entre les configurations de GPU sur des modèles de 13 pouces et de 15 pouces de surface Book 3.

Un différentiateur important entre les modèles surface Book 3 est la configuration de GPU. Outre le processeur graphique Intel intégré intégré à tous les modèles, tous les modèles, à l’exception de l’appareil i5 de niveau d’entrée de 13,5 niveau supérieur, disposent également d’une carte graphique NVIDIA discrète avec le modèle Max-Q, qui intègre des fonctionnalités qui permettent d’optimiser l’efficacité énergétique des facteurs de forme mobiles.

Intégrées à la base du clavier, le processeur graphique NVIDIA supplémentaire fournit des fonctionnalités de rendu graphique avancées et est fourni avec deux configurations principales: GeForce® GTX® 1650/1660 TI pour les particuliers ou le Creative RTX 3000 pour les professionnels de l’informatique, les ingénieurs et les professionnels de l’entreprise qui ont besoin de capacités graphiques avancées ou d’une expérience d’apprentissage approfondie. Cet article décrit également comment optimiser l’utilisation de l’application processeurs graphiques en spécifiant les applications qui doivent utiliser le iGPU intégré par rapport au GPU NVIDIA discrète.

## Processeurs surface Book 3

Cette section décrit les processeurs graphiques intégrés et discrets entre les modèles surface Book 3. Pour obtenir des informations de configuration de tous les modèles, reportez-vous à [l’annexe A: références SKU de surface Book 3](#).

### Graphismes Intel IRIS™ plus

Le GPU intégré (iGPU) inclus sur tous les modèles surface Book 3 intègre un moteur graphique plus large et un contrôleur de mémoire repensé doté de la prise en charge de LPDDR4X. Installés en tant que GPU secondaire sur la plupart des modèles surface Book 3, les fonctions graphiques d’Intel IRIS plus en tant que GPU singulier dans le modèle i5, 13,5-pouces principal. Même si le périphérique de niveau d’entrée dans la ligne surface surface 3 est doté d’un niveau d’entrée, il fournit des fonctionnalités graphiques avancées permettant aux particuliers, aux amateurs et aux créateurs en ligne d’exécuter les derniers logiciels de productivité comme Adobe Creative sur le Cloud ou apprécier les titres de jeu au 1080p.  

### NVIDIA GeForce GTX 1650

CARTE graphique NVIDIA GeForce GTX 1650 avec Max-Q de conception fournit une mise à niveau majeure du processus de diffusion en continu de base pour gérer plus efficacement le graphique complexe des jeux modernes. Son exécution simultanée d’opérations de virgule flottante et d’entiers amplifie les performances du calcul de charge de travail importante de jeux modernes. Une nouvelle architecture de mémoire unifiée à deux fois le cache de son prédécesseur permet d’améliorer les performances des jeux modernes complexes. Les nouvelles améliorations d’ombrage permettent d’améliorer les performances, d’améliorer la qualité de l’image et de produire de nouveaux niveaux de complexité géométrique.

### NVIDIA GeForce GTX 1660 TI

Comparé à la GeForce GTX 1650, le plus rapide GeForce GTX 1660 TI fournit surface Book 3 avec des améliorations de performances supplémentaires et inclut le nouveau codeur NVIDIA, ce qui le rend plus facile pour les particuliers, les joueurs, les flux de travail en direct et les professionnels du Creative.

Grâce à 6 Go de mémoire graphique GDDR6, les modèles surface Book 3 dotés de la NVIDIA GeForce GTX 1660 TI fournissent des vitesses supérieures sur les logiciels avancés de productivité d’entreprise et les jeux populaires, en particulier lors de l’exécution des titres ou livestreaming les plus modernes. Avec un lecteur de disques SSD de 2 to (disponible en U.S. uniquement), le modèle de 15 pouces doté de la carte graphique GeForce GTX 1660 TI offre le plus de stockage de n’importe quel appareil surface Book 3.

### NVIDIA Quadro RTX 3000

NVIDIA Quadro RTX 3000 déverrouille plusieurs fonctionnalités clés pour les utilisateurs professionnels: l’accélération du rendu des rayons et l’accélération de l’AI, et les graphiques avancés et la performance. Une combinaison de 30 coeurs, de 240 tensor de base et de 6 Go de mémoire graphique GDDR6 permet de multiples tâches avancées, notamment les flux de travail en 3D, la création de contenus 3D, les fonctionnalités de montage vidéo avancée, de diffusion professionnelle et de flux de travail à plusieurs applications. Le support matériel et logiciel de niveau entreprise intègre les outils de déploiement pour optimiser la disponibilité et réduire les besoins en matière de support informatique. Certifié pour le logiciel le plus avancé du monde, les pilotes Quadro sont optimisés pour les applications professionnelles et sont ajustés, testés et validés de manière à fournir une certification d’application, une fiabilité de niveau entreprise, une fiabilité, une disponibilité et une assistance technique avec la disponibilité des produits étendus.
 

## Comparaison des processeurs de surface dans le carnet d’apparence 3

Les processeurs graphiques NVIDIA fournissent aux utilisateurs une excellente performance pour les jeux, la diffusion en temps réel et la création de contenus. Les produits GeForce GTX sont très pratiques pour les joueurs et les créateurs de contenu. Les produits RTX sont dirigés vers des utilisateurs professionnels, offrent de meilleures performances en matière de jeu et de création de contenu, ainsi que les fonctionnalités suivantes:

- Accélération RTX pour le traçage de rayons et l’AI. Ainsi, il est possible d’afficher des objets et des environnements photographiquement photoréalistes avec des ombres, des réflexions et des réfractions physiques précises.  Quant à ses fonctionnalités AI accélérées sur le matériel, les fonctionnalités d’AI avancées des applications populaires peuvent s’exécuter plus vite qu’auparavant.
- Le matériel et les pilotes de niveau entreprise, ainsi que les certifications d’applications ISV.
- Fonctionnalités de gestion informatiques incluant une couche supplémentaire d’outils d’entreprise dédiés à la gestion à distance qui vous permettent d’optimiser votre disponibilité et de réduire les besoins en matière de support informatique.

 À moins que vous ne comptez parmi les rangs d’ingénierie, de conception, d’architecture ou de spécialistes de la science de l’informatique avancés, le livre surface 3 équipé de capacités graphiques NVIDIA GeForce est susceptible de répondre à vos besoins. Dans le cas contraire, si vous êtes déjà en cours d’utilisation (ou inversement), vous avez besoin de capacités graphiques très avancées dans un facteur de forme portable qui vous permet de travailler en tout lieu, à surface Book 3 avec Quadro RTX 3000 mérite de sérieusement considération. Pour en savoir plus, reportez-vous à la présentation technique de surface Book 3 Quadro RTX 3000.
 
**Tableau1. Cartes graphiques discrètes sur surface Book 3**

|                      | **GeForce GTX 1650**                   | **GeForce GTX 1660 TI**                            | **Quadro RTX 3000**                                                                                       |
| -------------------- | -------------------------------------- | -------------------------------------------------- | --------------------------------------------------------------------------------------------------------- |
| **Utilisateurs ciblés**     | Joueurs, amateurs et créateurs en ligne  | Joueurs, Creative Professionals et créateurs en ligne | Creative Professionals, architectes, ingénieurs, développeurs, scientifiques de données                                |
| **Flux**        | Conception graphique<br>Photographie<br>Vidéo | Conception graphique<br>Photographie<br>Vidéo             | Flux de travail à l’école  <br>Certifications d’application<br>Vidéo haute résolution<br>Diffusion professionnelle<br>Flux de travail à plusieurs applications |
| **Principales applications**         | Adobe Creative Suite                   | Adobe Creative Suite                               | Adobe Creative Suite<br>Autodesk AutoCAD<br>Dassault Systemes SolidWorks                                  |
| **Accélération GPU** | Traitement des images et des vidéos             | Traitement des images et des vidéos                         | Suivi de rayons + AI + 6K vidéo<br>Fonctionnalités de diffusion Pro<br>Support aux entreprises                            |


**Tableau2. Spécifications technologiques du GPU sur surface Book 3**

|                                                          | **GeForce GTX 1650** | **GeForce GTX 1660 TI** | **Quadro RTX 3000** |
| -------------------------------------------------------- | -------------------- | ----------------------- | ------------------- |
| **Processeurs CUDA NVIDIA**                         | 1024                 | 1536                    | 1920                |
| **Cœurs NVIDIA tensor**                                  | Non                   | Non                      | 240                 |
| **Cœurs NVIDIA RT**                                      | Non                   | Non                      | trente                  |
| **Mémoire GPU**                                           | 4 Go                 | 6 GO                    | 6 GO                |
| **Bande passante (Go/s)**                            | Jusqu’à 112            | Jusqu’à 288               | Jusqu’à 288           |
| **Type de mémoire**                                          | GDDR5                | GDDR6                   | GDDR6               |
| **Interface de mémoire**                                     | 128 bits              | 192 bits                 | 192 bits             |
| **Augmenter l’horloge MHz**                                      | 1245                 | 1425                    | 1305                |
| **Horloge de base (MHz)**                                     | 1020                 | 1245                    | 765                 |
| **Suivi de rayons en temps réel**                                | Non                   | Non                      | Oui                 |
| **Accélération matérielle AI**                             | Non                   | Non                      | Oui                 |
| **Codeur matériel**                                     | Oui                  | Oui                     | Oui                 |
| **Pilote prêt de jeu (GRD)**                              | Oui <sup> 1</sup>                                   | Oui <sup> 1</sup>          |Oui <sup> 2</sup> 
| **Driver Studio (SD)**                                   | Oui <sup> 1</sup>            | Oui <sup> 1</sup>                 | Oui <sup> 1</sup>           |
| **Pilote optimal pour Enterprise (ODE)**                  | Non                   | Non                      | Oui            |
| **Nouveau pilote de fonctionnalité Quadro (QNF)**                      | Non                   | Non                      | Oui            |
| **API Microsoft DirectX 12, API Vulkan, Open GL 4,6**    | Oui                  | Oui                     | Oui                 |
| **2,2 de protection de contenu numérique haut débit (HDCP)** | Oui                  | Oui                     | Oui                 |
| **Processeur graphique NVIDIA Booster**                                     | Oui                  | Oui                     | Oui                 |


 1. *Nos recommandations*
 2.  *Pris en charge*

## Optimisation de la puissance et des performances de surface Book 3

Windows 10 inclut un mode économiseur de batterie doté d’un curseur de performance qui vous permet d’optimiser les performances des applications (en les faisant glisser vers la droite) ou de préserver l’autonomie de la batterie (en les faisant glisser vers la gauche). Surface Book 3 implémente les fonctionnalités de manière algorithmique pour optimiser la puissance et les performances des composants suivants:

- Les registres d’efficacité énergétique de l’UC (technologie Intel Speed Shift) et d’autres paramètres de réglage SoC pour optimiser l’efficacité.
- Nombre maximal de RPM de fan avec quatre modes: quiet, nominaux, performance et max.
- Points d’arrêt du processeur (PL1/PL2).
- Limitations du processeur IA.

Par défaut, lorsque l’économiseur de batterie est inférieur à 20%, l’économiseur de batterie ajuste les paramètres pour prolonger l’autonomie de la batterie. Lorsque la connexion à Power Book 3 est définie par défaut sur «meilleures performances» pour garantir que les applications s’exécutent en mode haute performance sur le processeur graphique NVIDIA secondaire présent sur tous les systèmes i7 surface Book 3.

L’utilisation des paramètres par défaut est recommandée pour des performances optimales lorsqu’elles sont utilisées en tant qu’ordinateur portable ou détachées en mode tablette ou Studio. Vous pouvez accéder à l’économiseur de batterie en sélectionnant l’icône de batterie située à l’extrémité droite de la barre des tâches.

### Mode jeu

Surface Book 3 inclut un nouveau mode jeu qui sélectionne automatiquement les paramètres de performances maximaux lors du lancement.

### Détachement sécurisé

Nouveauté dans surface Book 3, les applications activées pour le détachement sécurisé vous permettent de vous déconnecter lorsque l’application utilise le GPU. Pour les applications prises en charge comme le *monde de Warcraft*, votre tâche est déplacée vers le iGPU.

### Modification des paramètres d’application pour toujours utiliser une carte graphique spécifique

Vous pouvez basculer entre l’économie d’énergie, tout en conservant les graphiques Intel intégrés et le processeur graphique NVIDIA discrète plus puissant et associer un GPU à une application spécifique. Par défaut, Windows 10 sélectionne automatiquement le GPU approprié, en assignant des applications demandant de manière graphique au processeur graphique NVIDIA discrète. Dans la plupart des cas, il n’est pas nécessaire d’ajuster les paramètres manuellement. Toutefois, si vous détachez et rattachez fréquemment l’affichage à partir de la base du clavier lors de l’utilisation d’une application dont l’utilisation est graphiquement exigeante, vous devez généralement fermer l’application avant de la détacher. Pour permettre une utilisation continue de l’application sans avoir à la fermer chaque fois que vous détachez ou Rattachez l’affichage, vous pouvez l’affecter à l’unité de traitement graphique intégré, même si la perte de performance graphique est perdue.  

Dans certains cas, Windows 10 est susceptible d’affecter une application graphiquement gourmande iGPU; par exemple, si l’application n’est pas entièrement optimisée pour les graphiques hybrides. Pour y remédier, vous pouvez affecter l’application manuellement à l’unité de traitement graphique NVIDIA discrète.

**Pour configurer des applications à l’aide d’options personnalisées par GPU:**  

1. Accédez à **paramètres**d’affichage du  >  **système**  >  **Display** et sélectionnez **paramètres graphiques**.

    1. Dans le cas d’un programme de bureau Windows, sélectionnez **classique application**  >  **Parcourir** , puis recherchez le programme.
    2. Pour une application UWP, sélectionnez **application universelle** , puis sélectionnez l’application dans la liste déroulante.

2. Sélectionnez **Ajouter** pour créer une nouvelle entrée dans la liste pour le programme que vous avez sélectionné, sélectionnez les options d’ouverture des caractéristiques graphiques, puis sélectionnez l’option souhaitée.

   ![Sélectionner les options d’économie d’énergie ou de GPU hautes performances](./images/graphics-settings2.png)

3. Pour vérifier le GPU utilisé pour chaque application, ouvrez le **Gestionnaire des tâches,** sélectionnez **performance,** puis affichez la colonne du **moteur GPU** .


## Annexe A: références SKU de surface Book 3

| **Affichage**   | **Processeur**                     | **Processeur graphique**                                                                                              | **Mémoire vive (RAM)**    | **Stockage** |
| ------------- | --------------------------------- | ---------------------------------------------------------------------------------------------------- | ---------- | ----------- |
| **13,5 pouces** | Quadruple cœur 10e GEN i5-1035G7 | Graphismes Intel IRIS™ plus                                                                            | 16 LPDDR4x | 256 GO      |
| **13,5 pouces** | Quadruple cœur 10e GEN i7-1065G7 | Graphismes Intel IRIS plus<br>NVIDIA GeForce GTX 1650. Conception Max-Q avec 4 Go de mémoire graphique GDDR5    | 16 LPDDR4x | 256 GO      |
| **13,5 pouces** | Quadruple cœur 10e GEN i7-1065G7 | Graphismes Intel IRIS plus<br>NVIDIA GeForce GTX 1650. Conception Max-Q avec 4 Go de mémoire graphique GDDR5    | 32 LPDDR4x | 512 GO      |
| **13,5 pouces** | Quadruple cœur 10e GEN i7-1065G7 | Graphismes Intel IRIS plus<br>NVIDIA GeForce GTX 1650. Conception Max-Q avec 4 Go de mémoire graphique GDDR5    | 32 LPDDR4x | 1To        |
| **15 pouces**   | Quadruple cœur 10e GEN i7-1065G7 | Graphismes Intel IRIS plus<br>NVIDIA GeForce GTX 1660 TI. Conception Max-Q avec 6 Go de mémoire graphique GDDR6 | 16 LPDDR4x | 256 GO      |
| **15 pouces**   | Quadruple cœur 10e GEN i7-1065G7 | Graphismes Intel IRIS plus<br>NVIDIA GeForce GTX 1660 TI. Conception Max-Q avec 6 Go de mémoire graphique GDDR6 | 32 LPDDR4x | 512 GO      |
| **15 pouces**   | Quadruple cœur 10e GEN i7-1065G7 | Graphismes Intel IRIS plus<br>NVIDIA GeForce GTX 1660 TI. Conception Max-Q avec 6 Go de mémoire graphique GDDR6 | 32 LPDDR4x | 1To        |
| **15 pouces**   | Quadruple cœur 10e GEN i7-1065G7 | Graphismes Intel IRIS plus<br>NVIDIA GeForce GTX 1660 TI. Conception Max-Q avec 6 Go de mémoire graphique GDDR6 | 32 LPDDR4x | 2 TO        |
| **15 pouces**   | Quadruple cœur 10e GEN i7-1065G7 | Graphismes Intel IRIS plus<br>NVIDIA Quadro RTX 3000. Conception Max-Q avec 6 Go de mémoire graphique GDDR6     | 32 LPDDR4x | 512 GO      |
| **15 pouces**   | Quadruple cœur 10e GEN i7-1065G7 | Graphismes Intel IRIS plus<br>NVIDIA Quadro RTX 3000. Conception Max-Q avec 6 Go de mémoire graphique GDDR6     | 32 LPDDR4x | 1To        |

> [!NOTE]
> 2 to de SSD disponibles en U.S. uniquement: surface Book 3 15 "avec la carte NVIDIA GTX 1660Ti

## Résumé

Conçu pour les performances, surface Book 3 inclut différentes configurations de GPU optimisées pour répondre à des besoins spécifiques en matière de charge de travail et d’utilisation. Un processeur graphique mobile Intel Iris intégré fonctionne comme le GPU unique sur l’appareil i5 principal de niveau d’entrée et en tant que GPU secondaire sur tous les autres modèles. GeForce GTX 1650 est une mise à niveau majeure du processus principal de multiprocesseur streaming pour exécuter plus efficacement les graphiques complexes. La plus rapide GeForce GTX de 1660 TI fournit surface Book 3 avec des améliorations des performances supplémentaires pour améliorer les performances des particuliers, des joueurs, des flux de travail en direct et des professionnels du Creative. Quadro RTX 3000 déverrouille les différentes fonctionnalités clés pour les utilisateurs professionnels: l’affichage du suivi des rayons et l’accélération de l’utilisation du son, ainsi que les graphiques avancés et la performance de calcul.


## En savoir plus

- [Présentation technique du surface Book 3 Quadro RTX 3000](surface-book-quadro.md)
- [Surface pour les entreprises](https://www.microsoft.com/surface/business)
