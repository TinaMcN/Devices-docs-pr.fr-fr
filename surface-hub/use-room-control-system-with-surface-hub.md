---
title: Utilisation d’un système de contrôle d’espace (Surface Hub)
description: Les systèmes de contrôle d’espace peuvent être utilisés avec votre Microsoft Surface Hub.
ms.assetid: DC365002-6B35-45C5-A2B8-3E1EB0CB8B50
ms.reviewer: ''
manager: laurawi
keywords: système de contrôle d’espace, Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.localizationpriority: medium
ms.openlocfilehash: 0e3b1706e58edb6e37156eda8d06fb0faefa4c91
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832652"
---
# Utilisation d’un système de contrôle d’espace (Surface Hub)


Les systèmes de contrôle d’espace peuvent être utilisés avec votre Microsoft Surface Hub.

L’utilisation d’un système de contrôle d’espace avec Surface Hub implique la connexion du matériel de contrôle d’espace au Surface Hub, généralement via le port série RJ11 situé au bas du Surface Hub.

## Paramètres du terminal

La connexion à un système de contrôle d’espace ne nécessite pas la configuration de paramètres du terminal sur le Surface Hub. Si vous voulez connecter un PC ou un ordinateur portable à votre Surface Hub et envoyer des commandes de série à partir de ce dernier, vous pouvez utiliser un programme d’émulation de terminal tel que Tera Term ou PuTTY. 

| Paramètre | Valeur |
| --- | --- |
| Vitesse (en bauds) | 115200 |
| Bits de données | version8 | 
| Bits d’arrêt | 1 |
| Parité | aucun |
| Contrôle de flux | aucun |
| Saut de ligne | chaque retour chariot |
 

## Diagramme de connexion

Vous pouvez utiliser un connecteur RJ-11 (6P6C) standard pour la connexion au port série Surface Hub à un système de contrôle d’espace. Il s’agit de la méthode recommandée. Vous pouvez également utiliser un câble conducteur à 4fils RJ-11, toutefois cette méthode n’est pas recommandée.

Ce diagramme montre le brochage correct utilisé pour un connecteur RJ-11 (6P6C) vers un câble DB9.

![Image illustrant le schéma de connexion.](images/room-control-wiring-diagram.png)

## Jeux de commandes

Les systèmes de contrôle d’espace utilisent des scénarios de salle courants pour les commandes. Les commandes sont issues du système de contrôle d’espace et communiquées via une connexion en série au Surface Hub. Il s’agit de commandes ASCII. Le Surface Hub reconnaît la survenue d’un changement d’état.

Les modificateurs de commande suivants sont disponibles. Les commandes se terminent par un saut de ligne (\n). Les réponses peuvent survenir à tout moment en réaction aux changements d’état qui ne sont pas déclenchés directement par une commande du port de gestion.

| Modificateur | Résultat |
| --- | --- |
| + | Incrémente une valeur |
| - | Réduit une valeur |
| = | Définir une valeur discrète |
| ? | Requêtes pour une valeur actuelle |
 

## Alimentation

Le Surface Hub peut se trouver dans l’un des états suivants:

| État | État Energy Star| Description |
| --- | --- | --- |
| 0,4 | S5 | Désactivé |
| 1 | - | Mise sous tension (indéterminé) |
| deuxième | S3 | Veille |
| n°5 | S0 | Prêt |


En mode PC de remplacement, les états d’alimentation sont uniquement Prêt et Désactivé et modifient seulement l’affichage. Le port de gestion ne permet pas de mettre le PC de remplacement sous tension. 

| État | État Energy Star| Description |
| --- | --- | --- |
| 0,4 | S5 | Désactivé |
| n°5 | S0 | Prêt |

Pour un appareil de contrôle, tout autre état que 5/Prêt doit être considéré comme désactivé. Chaque commande PowerOn génère deux modifications et réponses d’État. 

| Commande | Changement d’état| Réponse |
| --- | --- | --- |
| PowerOn | L’appareil se met sous tension (écran + PC).</br></br>Le service du PC informe le SMC que le PC est prêt. |  Power=0</br></br>Power=5 |
| PowerOff | L’appareil passe à l’état ambiant (PC allumé, assombrissement de l’affichage). |  Power=0 |
| Power? |  Le SMC indique le dernier état d’alimentation connu. |  Marche/Arrêt=<#> |



## Luminosité

Le niveau de luminosité actuel est une plage comprise entre 0 et 100.

Les modifications apportées aux niveaux de luminosité peuvent être envoyées par un système de contrôle d’espace ou d’autres systèmes.

| Commande | Changement d’état |Réponse |
| --- | --- | --- |
| Brightness+ | Le contrôleur de gestion de système (SMC) envoie la commande d’augmentation de la luminosité.</br></br>Le service du PC du système de contrôle d’espace informe le SMC du nouveau niveau de luminosité. |  Brightness = 51 |
| Brightness- |  Le SMC envoie la commande de réduction de la luminosité.</br></br>Le service du PC informe le SMC du nouveau niveau de luminosité. | Brightness = 50 |

## Volume

Le niveau de volume actuel est une plage comprise entre 0 et 100.

Les modifications apportées aux niveaux de volume peuvent être envoyées par un système de contrôle d’espace ou d’autres systèmes.

>[!NOTE]
>La commande Volume contrôle uniquement le volume pour le mode incorporé ou le mode PC de remplacement, pas à partir de [sources invitées](connect-and-display-with-surface-hub.md).

| Commande | Changement d’état | Réponse</br>(Activée en [ModePC de remplacement](connect-and-display-with-surface-hub.md#replacement-pc-mode)) |
| --- | --- | --- |
| Volume+ |  Le SMC envoie la commande d’augmentation du volume.</br></br>Le service du PC informe le SMC du nouveau niveau de volume. |  Volume = 51 |
| Volume- |  Le SMC envoie la commande de baisse du volume.</br></br>Le service du PC informe le SMC du nouveau niveau de volume. |  Volume = 50 |


 

## Désactivation du son

Le son peut être désactivé.

| Commande | Changement d’état | Réponse |
| --- | --- | --- |
| AudioMute+ |  Le SMC envoie la commande de désactivation du son.</br></br>Le service du PC informe le SMC que le son est désactivé. |  aucune |


 

## Source vidéo

Plusieurs sources vidéo peuvent être utilisées.

| État | Description | 
| --- | --- |
| 0,4 |  PC intégré |
| 1 |  DisplayPort |
| deuxième |  HDMI |
| 3D |  VGA |


 

Les modifications apportées à la source vidéo peuvent être envoyées par un système de contrôle d’espace ou d’autres systèmes.

| Commande | Changement d’état | Réponse |
| --- | --- | --- |
| Source=# |  Modifications SMC à la source souhaitée.</br></br>Le service du PC informe le SMC que la source d’affichage a changé. |  Source=&lt;#&gt; |
| Source+ |  Le SMC recherche la source d’entrée active suivante.</br></br>Le service du PC informe le SMC de la source d’entrée actuelle. |  Source=&lt;#&gt; |
| Source- | Le SMC recherche la source d’entrée active précédente.</br></br>Le service du PC informe le SMC de la source d’entrée actuelle. |  Source=&lt;#&gt; |
| Source? |  Le SMC interroge le service du PC concernant la source d’entrée active.</br></br>Le service du PC indique au SMC la source d’entrée actuelle. | Source=&lt;#&gt; |

## Erreurs

Les erreurs sont renvoyées au format indiqué dans le tableau suivant.

| Erreur | Remarques |
| --- | --- |
| Error: Unknown command ’&lt;input&gt;’. |  L’instruction contient une commande initiale inconnue. Par exemple, &quot;VOL+&quot; ne serait pas valide et renverrait &quot; Error: Unknown command ’VOL’&quot;. |
| Error: Unknown operator ’&lt;input&gt;’. |  L’instruction contient un opérateur inconnu. Par exemple, &quot;Volume!&quot; ne serait pas valide et renverrait &quot; Error: Unknown operator ’!’&quot; |
| Error: Unknown parameter ’&lt;input&gt;’. |  L’instruction contient un paramètre inconnu. Par exemple, &quot;Volume=abc&quot; ne serait pas valide et renverrait &quot; Error: Unknown parameter ’abc’&quot;. |
| Error: Command not available when off ’&lt;input&gt;’. |  Quand le Surface Hub est désactivé, les commandes autres que celle relative à la gestion de l’alimentation renvoient cette erreur. Par exemple, &quot;Volume+&quot; ne serait pas valide et renverrait &quot; Error: Command not available when off ’Volume’&quot;. |


 

## Rubriques connexes


[Gérer le Microsoft SurfaceHub](manage-surface-hub.md)

[Guide de l’administrateur Microsoft Surface Hub](surface-hub-administrators-guide.md)

 

 





