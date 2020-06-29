---
title: Connecter des appareils à SurfaceHub2S
description: Cet article explique comment connecter des périphériques externes aux périphériques surface Hub 2.
keywords: séparer les valeurs par des virgules
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 02/24/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 1c4f9b4a74b50edb5587185f28a18163a02d62f9
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10833324"
---
# Connecter des appareils à SurfaceHub2S
Surface Hub 2 vous permet de connecter des périphériques externes, de mettre en miroir l’affichage sur surface Hub 2S sur un autre périphérique, et de connecter plusieurs périphériques tiers, notamment les appareils photo de visioconférence, les téléphones de conférences et les systèmes de salle.

Vous pouvez afficher du contenu de vos périphériques sur surface Hub 2. S’il s’agit d’un périphérique Windows, ce périphérique peut également fournir TouchBack et InkBack, qui prend du contenu audio et vidéo à partir de l’appareil connecté et les présente sur surface Hub 2S. Si surface Hub 2 rencontre un signal de protection de contenu numérique (HDCP) à bande passante élevée (par exemple, un lecteur DVD Blu-Ray), la source s’affiche sous la forme d’une image noire.

> [!NOTE]
> Surface Hub 2 utilise l’entrée vidéo sélectionnée tant qu’une nouvelle connexion n’est pas établie, que la connexion existante est perturbée ou que l’application connectée est fermée.

## Configurations câblées recommandées 

En règle générale, il est recommandé d’utiliser des connexions de câble natives dans la mesure du possible, par exemple USB-C ou HDMI à HDMI. D’autres combinaisons comme MiniDP vers HDMI ou MiniDP vers USB-C fonctionneront également. Une configuration supplémentaire est nécessaire pour optimiser l’interface vidéo, comme décrit sur cette page.

| **Connexion** | **Fonctionnalités** | **Description**|
| --- | --- | ---|
| HDMI + USB-C | HDMI-in pour le son et la vidéo<br><br>USB-C pour TouchBack et InkBack | USB-C prend en charge TouchBack et InkBack avec la connexion HDMI A/V.<br><br>Utilisez le bus USB-C à USB-A pour vous connecter à d’anciens ordinateurs.<br><br>**Remarque:** Pour obtenir de meilleurs résultats, connectez HDMI avant de connecter un câble USB-C. Si l’ordinateur que vous utilisez pour HDMI n’est pas compatible avec TouchBack et InkBack, vous n’aurez pas besoin d’un câble USB-C. |
| USB-C <br> (via le module de calcul) | Vidéo-en <br>Entrée audio | Câble unique requis pour A/V<br><br>TouchBack et InkBack sont pris en charge<br><br>Protection HDCP activée |
| HDMI (dans Port) | Vidéo, audio en surface Hub 2 | Câble unique requis pour A/V<br><br>TouchBack et InkBack non pris en charge<br><br>Protection HDCP activée |
| MiniDP 1,2 sortie | Des vidéos telles que la mise en miroir sur un plus grand projecteur. | Câble unique requis pour A/V |

Lorsque vous connectez un ordinateur invité aux périphériques surface Hub 2 via le port USB-C, plusieurs périphériques USB sont détectés et configurés. Ces périphériques sont créés pour TouchBack et InkBack. Comme indiqué dans le tableau suivant, les périphériques périphériques peuvent être affichés dans le gestionnaire de périphériques (Device Manager) pour afficher les noms en double pour certains appareils, comme indiqué dans le tableau suivant.

 
|**Périphérique**| **Entrée dans le gestionnaire de périphériques** |
| ---------------------------- |------------- | ------------------------------|
| Périphériques d’interface utilisateur | Périphérique de contrôle consommateurHID<br>StyletHID<br>StyletHID (élément en double)<br>StyletHID (élément en double)<br>Écran tactileHID<br>Périphérique d’entréeUSB<br>Périphérique d’entréeUSB (élément en double) |
| Claviers | ClavierPS/2 standard |
| Souris et autres dispositifs de pointage | SourisHID |
| Contrôleurs USB | ConcentrateurUSB générique<br>PériphériqueUSB composite |

## Connexion d’une vidéo dans surface Hub 2

Vous pouvez entrer de la vidéo sur surface Hub 2 en utilisant USB-C ou HDMI, comme indiqué dans le tableau suivant.  

### Paramètres vidéo dans surface Hub 2

| **Type de signal** | **Résolution** | **Fréquence d’images** | **HDMI** | **USB-C** |
| --------------- | -------------- | -------------- | -------- | --------- |
| PC              | 640x480      | 60             | X        | X         |
| PC              | 720x480      | 60             | X        | X         |
| PC              | 1024x768     | 60             | X        | X         |
| PC              | 1920 x 1080    | 60             | X        | X         |
| PC              | 3840x2560      | trente             | X        | X         |
| HDTV            | 720p           | 60             | X        | X         |
| HDTV            | 1080p          | 60             | X        | X         |
| 4KO UHD          | 3840x2560      | trente             | X        | X         |

> [!NOTE]
> La résolution UHD 4Ko (3840 × 2560) est uniquement prise en charge pour la connexion aux ports du module de calcul. Il n’est pas pris en charge sur les ports USB d’invité situés à gauche, en haut et à droite de l’appareil.

> [!NOTE]
> La vidéo d’un PC externe connecté risque d’apparaître plus petit lorsqu’elle est affichée sur surface Hub 2.

## Mise en miroir des affichages de surface Hub 2S sur un autre appareil

Vous pouvez sortir de la vidéo vers un autre affichage à l’aide de MiniDP, comme indiqué dans le tableau suivant.

### Paramètres de sortie vidéo de surface Hub 2

| **Type de signal** | **Résolution** | **Fréquence d’images** | **MiniDP** |
| --------------- | -------------- | -------------- | ---------- |
| PC              | 640x480      | 60             | X          |
| PC              | 720x480      | 60             | X          |
| PC              | 1024x768     | 60             | X          |
| PC              | 1920 x 1080    | 60             | X          |
| PC              | 3840 x 2560    | 60             | X          |
| HDTV            | 720p           | 60             | X          |
| HDTV            | 1080p          | 60             | X          |
| 4KO UHD          | 3840 x 2560    | 60             | X          |


 
Surface Hub 2 inclut un port de vidéo MiniDP pour la projection de contenu visuel à partir de surface Hub 2 vers un autre affichage. Si vous envisagez d’utiliser les éléments de surface Hub 2 pour projeter vers un autre écran, tenez compte des recommandations suivantes:

- **Clavier obligatoire.** Avant de commencer, vous devez connecter un clavier externe compatible câblé ou Bluetooth aux surface Hub 2. Notez que contrairement à l’original surface Hub, un clavier pour surface Hub 2 est vendu séparément et n’est pas inclus dans le package d’expédition.<br><br>
- **Définir le mode dupliquer** Surface Hub 2 prend en charge la vidéo en mode doublon uniquement. Toutefois, vous devrez quand même configurer manuellement le mode d’affichage quand vous vous connectez pour la première fois:
    1. Entrez la **touche de logo Windows**  +  **P**, qui ouvre le volet projet sur le côté droit de surface Hub 2, puis sélectionnez mode **dupliquer** .
    2. Lorsque vous avez fini d’utiliser votre session surface Hub 2S, sélectionnez **arrêter la session**. Cela permet de s’assurer que le paramètre dupliqué est enregistré pour la session suivante.<br><br>
- **Planifiez des proportions différentes.** À l’instar des autres appareils surface, surface Hub 2 utilise un rapport hauteur/largeur d’affichage 3:2 (relation entre la largeur et la hauteur de l’affichage). Projection de surface Hub 2 sur les écrans avec des proportions différentes est prise en charge. Notez que, dans la mesure où surface Hub 2 duplique l’affichage, la sortie MiniDP s’affichera également dans des proportions d’une 3:2, ce qui peut entraîner un letterboxing ou une rideau en fonction des proportions de l’affichage de réception. 

> [!NOTE]
> Si votre deuxième moniteur utilise des proportions 16:9 (le rapport entre la plupart des écrans de télévision), des barres noires apparaissent sur les côtés droit et gauche de l’affichage en miroir. Si tel est le cas, vous souhaiterez peut-être informer vos utilisateurs qu’il n’est pas nécessaire de régler le second affichage.

## Sélection de câbles

Tenez compte des recommandations suivantes:

- **USB.** Câble USB 3,1 Gen 2
- **MiniDP.** Câbles DisplayPort certifiés pour une longueur maximale de 3 mètres.
- **Norme.** S’il est nécessaire de disposer d’un long câble, HDMI est recommandé en raison de la grande disponibilité des câbles économiques et de longue durée pour pouvoir installer des répéteurs si nécessaire.

> [!NOTE]
> La plupart des sources DisplayPort basculent automatiquement vers la signalisation HDMI s’il est détecté.

## Connexion sans fil à surface Hub 2

Windows 10 prend en charge le mode natif, qui vous permet de vous connecter sans fil aux surface Hub 2.<br><br>

### Pour vous connecter à l’aide de Miracast:

1. Sur votre appareil Windows 10, entrez la **touche du logo Windows**  +  **K**. 
2. Dans la fenêtre de connexion, recherchez le nom de votre surface Hub 2 dans la liste des appareils à proximité. Vous pouvez trouver le nom de votre surface Hub 2 dans le coin inférieur gauche de l’affichage.
3. Entrez un code confidentiel si votre administrateur système a activé le paramètre code confidentiel pour les connexions Miracast. Pour la première fois, vous devez entrer un numéro de broche lorsque vous vous connectez à surface Hub 2.

> [!NOTE]
>Si vous ne voyez pas le nom de l’appareil surface Hub 2 comme prévu, il est possible que la session précédente ait été fermée prématurément. Si tel est le cas, connectez-vous à surface Hub 2 directement pour mettre fin à la session précédente, puis connectez-vous à partir de votre appareil externe.

## Connexion des périphériques aux surface Hub 2

### Accessoires Bluetooth

Vous pouvez vous connecter aux accessoires suivants sur surface Hub-2 à l’aide de la technologie Bluetooth:

- Souris
- Claviers
- Casques
- Haut-parleurs
- Stylos surface Hub 2

> [!NOTE]
> Une fois connecté à un haut-parleur ou un casque Bluetooth, vous devrez peut-être modifier les paramètres par défaut du microphone et des haut-parleurs. Pour plus d’informations, reportez-vous à la rubrique [**gestion locale des paramètres de surface Hub**](https://docs.microsoft.com/surface-hub/local-management-surface-hub-settings).
