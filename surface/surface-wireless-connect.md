---
title: Optimiser la connectivité Wi-Fi pour les appareils surface
description: Cette rubrique décrit les paramètres Wi-Fi recommandés pour garantir la connexion des appareils surface dans les environnements réseau et mobiles encombrés.
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.audience: itpro
ms.localizationpriority: medium
ms.author: greglin
ms.topic: article
ms.reviewer: tokatz
manager: laurawi
ms.openlocfilehash: 2fb64f86e3c1da0e4ba3834877548898e98fd893
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10833179"
---
# Optimiser la connectivité Wi-Fi pour les appareils surface


Pour rester en contact avec une autonomie de batterie d’une journée entière, les appareils surface mettent en œuvre des paramètres de connectivité sans fil qui équilibrent les performances et la conservation de l’alimentation. En dehors des scénarios de mobilité les plus exigeants, les utilisateurs peuvent maintenir une connectivité sans fil suffisante sans modifier la carte réseau par défaut ou les paramètres associés. 

Dans les environnements réseau encombrés, les organisations peuvent implémenter des protocoles sans fil intégrés sur plusieurs points d’accès réseau pour faciliter l’itinérance. Cette page met en évidence les considérations en matière de connectivité sans fil dans les scénarios mobiles utilisant surface Pro 3 et les versions ultérieures, les surface Book, surface Laptop et surface Go.

## Conditions préalables

Ce document part du principe que vous avez correctement déployé un réseau sans fil qui prend en charge la norme 802.11 n (Wi-Fi 4) ou une version ultérieure conformément aux recommandations en matière de meilleures pratiques de fournisseurs d’équipements leaders.

## Configuration de points d’accès pour des capacités d’itinérance optimales

Si vous gérez un réseau sans fil auquel il est généralement accédé par de nombreux types d’appareils clients, il est recommandé d’activer des protocoles spécifiques sur les points d’accès (APs) dans votre réseau local, comme décrit dans [itinérance rapide avec 802.11 k, 802.11 v et 802.11 r](https://docs.microsoft.com/windows-hardware/drivers/network/fast-roaming-with-802-11k--802-11v--and-802-11r). Les appareils surface peuvent tirer parti des protocoles sans fil suivants:

- **802.11 r.** «**Transition rapide BSS»** accélère la connexion aux nouveaux points d’accès sans fil en réduisant le nombre de trames nécessaires avant que votre appareil puisse accéder à un autre point d’accès lorsque vous vous déplacez sur votre appareil.
- **802.11 k.** Les **«rapports sur les voisins»** fournissent des informations sur les conditions actuelles du voisinage de points d’accès. Il peut aider votre périphérique surface à choisir le meilleur point d’accès à l’aide de critères autres que la force du signal, tels que l’utilisation de la comptabilité.

Les appareils de surface spécifiques peuvent également utiliser les trames de gestion de la transition BSS de 802.11 v, qui fonctionnent de la même manière que le 802.11 k pour fournir des informations sur les points d’accès de la fonction de proximité. Il s’agit notamment de surface Go, de surface Pro 7, de surface Pro X et de surface Laptop 3. 

## Gestion des paramètres utilisateur

Vous pouvez obtenir des fonctionnalités d’itinérance optimale par le biais d’un réseau bien conçu qui prend en charge les normes 802.11 r et 802.11 k sur tous les points d’accès. Le bon fonctionnement de votre réseau pour offrir aux utilisateurs la meilleure utilisation sans fil est l’approche recommandée par rapport à la tentative de gestion des paramètres utilisateur sur des appareils individuels. Par ailleurs, dans de nombreux environnements d’entreprise, les utilisateurs d’appareils de surface ne pourront pas accéder aux paramètres de carte réseau avancée sans autorisation explicite ou par droits d’administrateur local. Dans d’autres réseaux à gestion allégée, les utilisateurs peuvent bénéficier de l’avantage de savoir comment les paramètres spécifiques peuvent avoir un impact sur la possibilité de rester connectés.

### Paramètres utilisateur recommandés et meilleures pratiques

Dans certains cas, la modification des paramètres de carte réseau avancée intégrés aux périphériques surface risque de faciliter une connexion plus fiable. Gardez à l’esprit qu’une incapacité à se connecter à des ressources sans fil est plus fréquente en raison d’un problème de point d’accès, d’une faille de conception de réseau ou d’un problème de site environnemental.

> [!NOTE]
> La façon dont vous tenez votre surface Pro ou surface Go peut également affecter la force du signal. Si vous subissez une perte de bande passante, assurez-vous que vous ne disposez pas de la partie supérieure de l’écran, à l’endroit où se trouve le récepteur radio Wi-Fi. Même si la partie supérieure de l’affichage ne bloque pas les signaux sans fil, elle peut déclencher le pilote de périphérique pour lancer des modifications qui réduisent la connectivité.

### Conserver la valeur automatique par défaut pour la fonctionnalité de bande passante double
Sur la plupart des appareils surface, vous pouvez configurer les paramètres d’adaptateur du réseau du client de manière à ce qu’ils se connectent uniquement aux points d’accès sans fil de plus de 5 gigahertz (GHz), se connecter à plus de 2,4 GHz ou laisser le système d’exploitation choisir la meilleure option (paramètre automatique par défaut).

**Pour accéder aux paramètres de carte réseau, accédez à:**

- Le **menu Démarrer**  >  **Panneau de configuration**  >  Centre de réseaux **et de partage**  >  **votre carte**  >  Wi-Fi **Propriété**  >  **Configurer**  >  **Avancée**.

![* paramètres WiFi-Band *](images/wifi-band.png) <br>

Gardez à l’esprit que 2,4 GHz dispose de quelques avantages par rapport à 5 GHz: il s’étend de plus en plus et plus facilement dans les murs ou autres objets solides. Si vous n’avez pas de cas d’utilisation claire qui justifie la connexion à 5 GHz, il est recommandé de conserver le paramètre Band dans l’État par défaut afin d’éviter d’éventuelles conséquences indésirables. Exemple:


- Bon nombre de points d’accès présents dans les hôtels, les cafés et les aéroports n’utilisent toujours 2,4 GHz qu’en bloquant l’accès aux appareils si la bande est définie sur 5 GHz uniquement.
- Dans la mesure où les connexions d’affichage sans fil Miracast nécessitent la fin de l’établissement d’une liaison de 2,4 GHz, les appareils ne seront pas en mesure de se connecter à 5 GHz uniquement.

> [!NOTE]
> Par défaut, les appareils de surface préfèreront une connexion à 5 GHz, le cas échéant. Toutefois, pour préserver la puissance dans un état de batterie faible, surface doit d’abord chercher une connexion de 2,4 GHz.

Vous pouvez également changer le paramètre de bande selon vos besoins en fonction de votre environnement. Par exemple, les utilisateurs qui vivent dans des immeubles de réorganisation de grande densité et disposant de multiples points d’accès Wi-Fi, en compactant la présence de périphériques grand public en passant par 2,4 GHz, peuvent bénéficier de l’avantage de définir leur périphérique de surface pour une connexion de 5 GHz uniquement, puis de revenir à l’auto lorsque cela est nécessaire.

### Paramètres d’itinérance en itinérance sur surface Go

Les employés à l’aide de surface Go doivent sélectionner un seuil de puissance du signal qui invite l’appareil à rechercher un nouveau point d’accès lorsque la force du signal est chute (agressivité de l’itinérance). Par défaut, les appareils de surface essaient d’accéder à un nouveau point d’accès si la force du signal passe au-dessous de **moyenne** (la force du signal de 50 pour cent). Notez que lorsque vous augmentez l’itinérance, vous accélérez la consommation d’énergie de la batterie.

Conservez le paramètre de sécurité d’itinérance dans l’État par défaut, sauf si vous rencontrez des problèmes de connectivité dans des scénarios mobiles spécifiques, par exemple pour effectuer des inspections de site environnemental tout en préservant la connectivité audio et vidéo pendant une réunion. Si vous ne remarquez aucune amélioration, rétablissez l’état de **moyenne** par défaut.

**Pour activer l’itinérance en itinérance dans surface Go, procédez comme suit:**

1. Accédez à **Démarrer > le réseau du panneau**  >  **de configuration et**au  >  **Centre de réseaux et de partage Internet.**
2. Sous **connexions** , sélectionnez **Wi-Fi** , puis cliquez sur **Propriétés.**
3. Sélectionnez **client pour réseaux Microsoft** , puis **configurer** .
4. **Advanced**  >  Dans le menu déroulant, sélectionnez**agressivité** avancée sur l’itinérance et choisissez votre valeur préférée.

![* Paramètres d’itinérance](images/wifi-roaming.png) <br>

## Conclusion

Les appareils surface sont conçus à l’aide de paramètres par défaut pour une connectivité sans fil optimale, parallèlement à la nécessité de préserver l’autonomie de la batterie. Le moyen le plus efficace d’activer une connectivité fiable pour les appareils surface consiste à utiliser un réseau bien conçu qui prend en charge les normes 802.11 r et 802.11 k. Les utilisateurs peuvent régler les paramètres de carte réseau ou les paramètres d’itinérance, mais ils doivent uniquement le faire en réponse à des facteurs environnementaux spécifiques et rétablir l’État par défaut s’il n’y a pas d’amélioration notable.
