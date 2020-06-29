---
title: Connecter d’autres appareils et les afficher avec le Surface Hub
description: Vous pouvez connecter d’autres appareils à votre Surface Hub pour en afficher le contenu.
ms.assetid: 8BB80FA3-D364-4A90-B72B-65F0F0FC1F0D
ms.reviewer: ''
manager: laurawi
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.localizationpriority: medium
ms.openlocfilehash: 2d8d814d5e33a878fab066321a0d7800ae5104c0
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10834044"
---
# Connecter d’autres appareils et les afficher avec le SurfaceHub


Vous pouvez connecter d’autres appareils à votre Microsoft Surface Hub pour en afficher le contenu. Cette rubrique décrit le mode Invité, le mode PC de remplacement et la fonctionnalité de sortie vidéo disponible avec des connexions câblées. Elle répertorie également les accessoires que vous pouvez connecter à Surface Hub à l’aide de [Bluetooth](#bluetooth-accessories).

>[!NOTE]
>Surface Hub utilisera l’entrée vidéo que vous sélectionnez tant que vous n’avez pas créé de connexion, la connexion existante est interrompue ou l’application connectée est fermée.

## Quelle méthode choisir?

Lorsque vous connectez des appareils externes à un Surface Hub pour en afficher le contenu, vous disposez de plusieurs options. La méthode que vous allez utiliser dépend de votre scénario et de vos besoins. 

| Si vous souhaitez: | Utilisez cette méthode: |
| --- | --- |
| Mettre en miroir l’écran du Surface Hub sur un autre appareil. | [Sortie vidéo](#video-out) |
| Afficher le contenu d’un autre appareil sur l’écran Surface Hub et interagir à la fois avec le contenu de l’appareil et l’expérience intégrée du Surface Hub. | [Mode Invité](#guest-mode) |
| Alimenter le Surface Hub à partir d’un PC Windows10 externe, en éteignant l’ordinateur intégré du Surface Hub. Les caméras, les microphones, les haut-parleurs et autres périphériques sont envoyés au PC externe, en plus du stylet et de la fonction tactile. | [ModePC de remplacement](#replacement-pc-mode) |


## Mode Invité


Le mode Invité utilise une connexion câblée. Les utilisateurs peuvent donc afficher le contenu de leurs appareils sur le Surface Hub. Si l’appareil source est basé sur Windows, il peut alors fournir les fonctionnalités Touchback et Inkback. Le PC interne du Surface Hub reçoit l’image et le son de l’appareil connecté pour les afficher sur le Surface Hub. Si surface Hub rencontre un signal de protection de contenu numérique à forte bande passante, la source sera affichée sous forme d’image noire. Pour afficher votre contenu sans enfreindre les exigences HDCP, utilisez le pavé numérique sur le côté droit du Surface Hub pour choisir directement la source externe.

>[!NOTE]
>Lorsqu’une source HDCP est connectée, utilisez le clavier latéral pour modifier les entrées source.

### Ports

Utilisez ces ports sur le Surface Hub pour le mode Invité.

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>Interface</th>
<th>Type</th>
<th>Description</th>
<th>Fonctionnalités</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Port d’affichage1.1a</p></td>
<td><p>Entrée vidéo</p></td>
<td><p>Entrée invité n°1</p></td>
<td><ul>
<li><p>Prend en charge l’affichage simultané de l’entrée invité avec l’entrée invité n°2 et l’entrée invité n°3 (une haute résolution et deuxminiatures).</p></li>
<li><p>CompatibleHDCP en mode Contournement</p></li>
<li><p>Fonctionnalité Touchback activée</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>HDMI1.4</p></td>
<td><p>Entrée vidéo</p></td>
<td><p>Entrée invité n°2</p></td>
<td><ul>
<li><p>Prend en charge l’affichage simultané de l’entrée invité avec l’entrée invité n°1 et l’entrée invité n°3 (une haute résolution et deuxminiatures).</p></li>
<li><p>CompatibleHDCP en mode Contournement</p></li>
<li><p>Fonctionnalité Touchback activée</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>VGA</p></td>
<td><p>Entrée vidéo</p></td>
<td><p>Entrée invité n°3</p></td>
<td><ul>
<li><p>Prend en charge l’affichage simultané de l’entrée invité avec l’entrée invité n°1 et l’entrée invité n°2 (une haute résolution et deuxminiatures).</p></li>
<li><p>CompatibleHDCP en mode Contournement</p></li>
<li><p>Fonctionnalité Touchback activée</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Connecteur 3,5mm</p></td>
<td><p>Entrée audio</p></td>
<td><p>Entrée audio analogique</p></td>
<td><ul>
<li><p>Réception sur le PC du Surface Hub, généralement avec l’entrée vidéoVGA.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>USB2.0, typeB</p></td>
<td><p>SortieUSB</p></td>
<td><p>Touchback</p></td>
<td><ul>
<li><p>Fournit un accès aux périphériques d’entréeHID (souris, interaction tactile, clavier et stylet) au PC invité.</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

### Emplacement des ports

Voici les connexions de port utilisées pour le mode Invité sur les Surface Hub 55et 84pouces.

![image présentant des ports invité sur un surfacehub 55pouces.](images/sh-55-guest-ports.png)

Connexions de port câblées sur un Surface Hub 55pouces

![image présentant des ports invité sur un surfacehub 84pouces.](images/sh-84-guest-ports.png)

Connexions de port câblées sur un Surface Hub 84pouces

### Énumération de port

Lorsqu’un Surface Hub est connecté à un ordinateur invité via un portUSB de connexion câblée, plusieurs périphériquesUSB sont détectés et configurés. Ces périphériques sont créés pour les fonctionnalités Touchback et Inkback, et peuvent être affichés dans le Gestionnaire de périphériques. Le Gestionnaire de périphériques affiche les noms en double pour certains périphériques.

**Périphériques d’interface utilisateur**

-   Périphérique de contrôle consommateurHID

-   StyletHID

-   StyletHID (élément en double)

-   StyletHID (élément en double)

-   Écran tactileHID

-   Périphérique d’entréeUSB

-   Périphérique d’entréeUSB (élément en double)

**Claviers**

-   ClavierPS/2 standard

**Souris et autres dispositifs de pointage**

-   SourisHID

**Contrôleurs de busUSB**

-   ConcentrateurUSB générique

-   PériphériqueUSB composite

### Connectivité en mode Invité

Votre choix de câble vidéo est déterminé par ce qui est disponible à partir de votre entrée source. Le Surface Hub présente troischoix d’entrée vidéo: DisplayPort, HDMI etVGA. Voir le tableau suivant pour connaître les résolutions disponibles.

<table style="width:100%;">
<colgroup>
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
</colgroup>
<thead>
<tr class="header">
<th>Type de signal</th>
<th>Résolution</th>
<th>Fréquence d’images</th>
<th>HDMI-RVB</th>
<th>DisplayPort</th>
<th>VGA</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PC</p></td>
<td><p>640x480</p></td>
<td><p>59,94/60</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
<tr class="even">
<td><p>PC</p></td>
<td><p>720x480</p></td>
<td><p>59,94/60</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>PC</p></td>
<td><p>1024x768</p></td>
<td><p>60</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
<tr class="even">
<td><p>HDTV</p></td>
<td><p>720p</p></td>
<td><p>59,94/60</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
<tr class="odd">
<td><p>HDTV</p></td>
<td><p>1080p</p></td>
<td><p>59,94/60</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
</tbody>
</table>

 

Les données audio source sont fournies par les câbles DisplayPort et HDMI. Si vous devez utiliserVGA, le Surface Hub possède un port d’entrée audio qui utilise une fiche 3,5mm. Le Surface Hub utilise également un câbleUSB qui fournit les fonctionnalités Touchback et Inkback du Surface Hub aux appareils Windows10 compatibles. Le câbleUSB peut être utilisé avec toute entrée vidéo déjà connectée à l’aide d’un câble.

Toute personne utilisant le mode Invité pour se connecter à unPC peut utiliser l’une des options suivantes:

**DisplayPort**: câble DisplayPort et câbleUSB2.0

**HDMI**: câbleHDMI et câbleUSB2.0

**VGA**: câbleVGA, câble audio3,5mm et câbleUSB2.0

Si l’ordinateur que vous utilisez pour le mode Invité n’est pas compatible avec les fonctionnalités Touchback et Inkback, vous n’avez pas besoin du câbleUSB.

## ModePC de remplacement


En modePC de remplacement, l’ordinateur incorporé du Surface Hub est désactivé, et unPC externe est connecté au Surface Hub. Les connexions aux ports duPC de remplacement permettent d’accéder aux principaux périphériques sur le Surface Hub, notamment l’écran, le stylet et les fonctionnalités tactiles. Cela signifie que votre Surface Hub ne tire pas profit de l’expérience Équipe Windows, mais que vous disposez de la flexibilité offerte en fournissant et en gérant votre propre ordinateur Windows.

### Configuration logicielle requise

Vous pouvez utiliser le Surface Hub en modePC de remplacement avec les versions64bits de Windows10 Famille, Windows10 Professionnel et Windows10 Entreprise. Vous pouvez télécharger le [package de pilotesPC de remplacement du Surface Hub](https://www.microsoft.com/download/details.aspx?id=52210) à partir du Centre de téléchargement Microsoft. Nous vous recommandons d’installer ces pilotes sur les ordinateurs que vous envisagez d’utiliser commePC de remplacement.

### Configuration matérielle requise

Le Surface Hub est compatible avec une large gamme de matériel. Choisissez la configuration du processeur et de la mémoire de votrePC de remplacement afin qu’il prenne en charge les programmes que vous utilisez. Le matériel de votrePC de remplacement doit prendre en charge les versions 64bits de Windows10.

### Carte graphique

En modePC de remplacement, le Surface Hub prend en charge toute carte graphique pouvant produire un signal DisplayPort. Vous allez améliorer votre expérience avec une carte graphique pouvant correspondre à la résolution et à la fréquence de rafraîchissement du Surface Hub. Par exemple, l’expérience dePC de remplacement recommandée et appropriée sur le Surface Hub est un signal vidéo de 120Hz.

**Surface Hub55pouces**: pour une expérience optimale, utilisez une carte graphique prenant en charge la résolution1080p à 120Hz.

**Surface Hub84pouces**: pour une expérience optimale, utilisez une carte graphique prenant en charge la sortie de quatreflux DisplayPort1.2 pour produire une résolution 2160p à 120Hz (3840x2160 à une fréquence de rafraîchissement verticale de 120Hz). Nous avons vérifié que cela fonctionne avec les graphiques NVIDIA Quadro K2200, NVIDIA Quadro K4200, NVIDIA Quadro M6000, AMD FirePro W5100, AMD FirePro W7100 et AMD FirePro W9100. Ce ne sont pas les seules cartes graphiques; il en existe d’autres proposées par d’autres fournisseurs. 

Vérifiez les derniers pilotes directement auprès des fournisseurs de cartes graphiques.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Fournisseur graphique</th>
<th>Page de téléchargement des pilotes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>NVIDIA</p></td>
<td><p><a href="http://nvidia.com/Download/index.aspx" data-raw-source="[http://nvidia.com/Download/index.aspx](http://nvidia.com/Download/index.aspx)">http://nvidia.com/Download/index.aspx</a></p></td>
</tr>
<tr class="even">
<td><p>AMD</p></td>
<td><p><a href="http://support.amd.com/en-us/download" data-raw-source="[http://support.amd.com/en-us/download](http://support.amd.com/en-us/download)">http://support.amd.com/en-us/download</a></p></td>
</tr>
<tr class="odd">
<td><p>Intel</p></td>
<td><p><a href="https://downloadcenter.intel.com/" data-raw-source="[https://downloadcenter.intel.com/](https://downloadcenter.intel.com/)">https://downloadcenter.intel.com/</a></p></td>
</tr>
</tbody>
</table>

 

### Ports

Ports d’unPC de remplacement sur un Surface Hub 55pouces

![image illustrant les ports d’unpc de remplacement sur un surfacehub 55pouces.](images/sh-55-rpc-ports.png)

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>Description</th>
<th>Type</th>
<th>Interface</th>
<th>Détails</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>VidéoPC</p></td>
<td><p>Entrée vidéo</p></td>
<td><p>DisplayPort 1.2</p></td>
<td><ul>
<li><p>Affichage plein écran de 1080p à 120Hz, plus données audio</p></li>
<li><p>CompatibleHDCP</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Périphériques internes</p></td>
<td><p>SortieUSB</p></td>
<td><p>USB2.0 typeB</p></td>
<td><ul>
<li><p>Interaction tactile</p></li>
<li><p>Stylet</p></li>
<li><p>Haut-parleurs</p></li>
<li><p>Microphone</p></li>
<li><p>Appareils photo</p></li>
<li><p>CapteurNFC</p></li>
<li><p>Capteur de lumière ambiante</p></li>
<li><p>Capteur infrarouge passif</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>ConcentrateurUSB</p></td>
<td><p>SortieUSB</p></td>
<td><p>USB2.0 typeB</p></td>
<td><ul>
<li><p>PortsUSB inférieurs</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

Ports d’unPC de remplacement sur un Surface Hub 84pouces

![image illustrant les ports d’unpc de remplacement sur un surfacehub 84pouces.](images/sh-84-rpc-ports.png)

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>Description</th>
<th>Type</th>
<th>Interface</th>
<th>Détails</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>VidéoPC</p></td>
<td><p>Entrée vidéo</p></td>
<td><p>DisplayPort 1.2 (2x)</p></td>
<td><ul>
<li><p>Affichage plein écran de 2160p à 120Hz, plus données audio</p></li>
<li><p>CompatibleHDCP</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Périphériques internes</p></td>
<td><p>SortieUSB</p></td>
<td><p>USB2.0 typeB</p></td>
<td><ul>
<li><p>Interaction tactile</p></li>
<li><p>Stylet</p></li>
<li><p>Haut-parleurs</p></li>
<li><p>Microphone</p></li>
<li><p>Appareils photo</p></li>
<li><p>CapteurNFC</p></li>
<li><p>Capteur de lumière ambiante</p></li>
<li><p>Capteur infrarouge passif</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>ConcentrateurUSB</p></td>
<td><p>SortieUSB</p></td>
<td><p>USB2.0 typeB</p></td>
<td><ul>
<li><p>PortsUSB inférieurs</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

### Instructions d’installation d’unPC de remplacement

**Pour utiliser le modePC de remplacement**

1.  Téléchargez et installez le [package de pilotesPC de remplacement du Surface Hub](https://www.microsoft.com/download/details.aspx?id=52210) sur lePC de remplacement.

    >[!NOTE]
    >Nous vous recommandons de définir le mode veille ou veille prolongée sur lePC de remplacement afin que le Surface Hub désactive l’affichage lorsqu’il n’est pas utilisé.

2.  Désactivez le Surface Hub à l’aide du bouton marche/arrêt situé à côté du câble d’alimentation.

3.  Connectez les câbles des ports duPC de remplacement du Surface Hub auPC de remplacement. Ces ports sont généralement recouverts par un capuchon en plastique amovible.

    Surface Hub 55pouces: connectez un câbleDisplayPort et deuxcâblesUSB.

    Surface Hub 84pouces: connectez deuxcâblesDisplayPort et deuxcâblesUSB.

4.  Basculez le commutateur Mode sur**PC de remplacement**. Le commutateur Mode est situé à côté des portsPC de remplacement.

5.  Activez le Surface Hub à l’aide du bouton marche/arrêt situé à côté du câble d’alimentation.

6.  Appuyez sur le bouton d’alimentation situé sur le côté droit du Surface Hub.

Vous pouvez activer le Surface Hub pour utiliser lePC interne.

**Pour basculer à nouveau vers lePC interne**

1.  Désactivez le Surface Hub à l’aide du bouton marche/arrêt situé à côté du câble d’alimentation.

2.  Basculez le commutateur Mode surPC interne. Le commutateur Mode est situé à côté des portsPC de remplacement.

3.  Activez le Surface Hub à l’aide du bouton marche/arrêt situé à côté du câble d’alimentation.

 
## Sortie vidéo
 
Le Surface Hub inclut un port de sortie vidéo pour mettre en miroir le contenu visuel du Surface Hub sur un autre écran.

### Ports

Port de sortie vidéo sur le Surface Hub 55pouces

![image illustrant le port de sortie vidéo](images/video-out-55.png)

Port de sortie vidéo sur le Surface Hub 84pouces

![image illustrant le port de sortie vidéo](images/video-out-84.png)

<table>
<thead>
<tr class="header">
<th>Description</th>
<th>Type</th>
<th>Interface</th>
<th>Fonctionnalités</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Sortie vidéo miroir</p></td>
<td><p>Sortie vidéo</p></td>
<td><p>Sortie vidéo</p></td>
<td><ul>
<li><p>Prend en charge la connexion à un moniteur DisplayPort standard (prend en charge uniquement 4 liaisons affichant une résolution de 1080x60 24bpp)</p></li>
<li><p>Prend en charge l’utilisation avec des moniteurs HDMI (prise en charge de 1080p60) à l’aide d’un adaptateur DisplayPort-HDMI</p></li>
</ul></td>
</tr>
</tbody>
</table>

## Câbles

Le bon fonctionnement des appareils Surface Hub 55" et 84" a été vérifié avec des câbles certifiés DisplayPort et HDMI.  Bien que des fournisseurs vendent des câbles plus longs capables de fonctionner avec le Surface Hub, seuls les câbles certifiés par les laboratoires de test fonctionneront à coup sûr avec le Hub. Par exemple, les câbles DisplayPort ne sont certifiés que jusqu'à 3mètres, bien que de nombreux fournisseurs vendent des modèles 3fois plus longs. Si un long câble est nécessaire, nous vous conseillons vivement d’utiliser la norme HDMI.  Le HDMI dispose de nombreuses solutions économiques pour les câbles longue distance, notamment l’utilisation de répéteurs. Presque toutes les sources DisplayPort basculent automatiquement vers le HDMI et préviennent si un récepteur HDMI est détecté.


## Accessoires Bluetooth

Vous pouvez connecter les accessoires suivants à Surface Hub à l’aide du Bluetooth:

- Souris
- Claviers
- Casques
- Haut-parleurs

>[!NOTE]
>Une fois connecté à un haut-parleur ou un casque Bluetooth, vous devrez peut-être modifier les [paramètres par défaut du microphone et des haut-parleurs](local-management-surface-hub-settings.md).
