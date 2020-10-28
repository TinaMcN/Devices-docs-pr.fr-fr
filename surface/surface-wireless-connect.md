---
title: Optimiser la connectivité Wi-Fi pour les appareils surface
description: Cette rubrique décrit les paramètres de Wi-Fi recommandés pour garantir que les périphériques de surface restent connectés dans les environnements réseau congestionnés et les scénarios mobiles.
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
ms.date: 10/26/2020
ms.openlocfilehash: d211ceea20b89824d45e433cf9670abe137130a0
ms.sourcegitcommit: 07ac65bf70c8c6efcda28eecc3013983fc386e0d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "11136142"
---
# Optimiser la connectivité Wi-Fi pour les appareils surface


Pour rester en contact avec une autonomie de batterie d’une journée entière, les appareils surface mettent en œuvre des paramètres de connectivité sans fil qui équilibrent les performances et la conservation de l’alimentation. En dehors des scénarios de mobilité les plus exigeants, les utilisateurs peuvent maintenir une connectivité sans fil suffisante sans modifier la carte réseau par défaut ou les paramètres associés. Cette page présente les principales considérations relatives à la connectivité sans fil dans les scénarios mobiles utilisant les derniers périphériques de surface, y compris surface Pro 7, surface Pro X, surface Laptop 3, surface surface 3, surface Go 2 et surface Laptop Go.  

## Conditions préalables

Ce document part du principe que vous avez correctement déployé un réseau sans fil qui prend en charge la norme 802.11 n (Wi-Fi 4) ou une version ultérieure conformément aux recommandations en matière de meilleures pratiques de fournisseurs d’équipements leaders.

## Configuration de points d’accès pour des capacités d’itinérance optimales

Si vous gérez un réseau sans fil auquel il est généralement accédé par de nombreux types d’appareils clients, il est recommandé d’activer des protocoles spécifiques sur les points d’accès (APs) dans votre réseau local, comme décrit dans [itinérance rapide avec 802.11 k, 802.11 v et 802.11 r](https://docs.microsoft.com/windows-hardware/drivers/network/fast-roaming-with-802-11k--802-11v--and-802-11r). Les appareils surface peuvent tirer parti des protocoles sans fil suivants:

- **802.11 r.** «**Transition rapide BSS»** accélère la connexion aux nouveaux points d’accès sans fil en réduisant le nombre de trames nécessaires avant que votre appareil puisse accéder à un autre point d’accès lorsque vous vous déplacez sur votre appareil. Dans la nouvelle génération de périphériques surface parus depuis 2019, les utilisateurs finaux peuvent accéder aux paramètres d’itinérance sur leur appareil. Même si la modification des paramètres par défaut n’est pas recommandée, les utilisateurs doivent être conscients de cette fonctionnalité et comprendre la manière dont les paramètres spécifiques peuvent avoir un impact sur la possibilité de rester connectés.
- **802.11 k.** Les **«rapports sur les voisins»** fournissent des informations sur les conditions actuelles du voisinage de points d’accès. Il peut aider votre périphérique surface à choisir le meilleur point d’accès à l’aide de critères autres que la force du signal, tels que l’utilisation de la comptabilité.

Les appareils de surface spécifiques peuvent également utiliser les trames de gestion de la transition BSS de 802.11 v, qui fonctionnent de la même manière que le 802.11 k pour fournir des informations sur les points d’accès de la fonction de proximité. Il s’agit notamment de surface Go, de surface Pro 7, de surface Pro X et de surface Laptop 3. 

## Gestion des paramètres utilisateur

Vous pouvez obtenir des fonctionnalités d’itinérance optimale par le biais d’un réseau bien conçu qui prend en charge les normes 802.11 r et 802.11 k sur tous les points d’accès. Le bon fonctionnement de votre réseau pour offrir aux utilisateurs la meilleure utilisation sans fil est l’approche recommandée par rapport à la tentative de gestion des paramètres utilisateur sur des appareils individuels. 

### Paramètres utilisateur recommandés et meilleures pratiques

Dans certains cas, la modification des paramètres de carte réseau avancée intégrés aux périphériques surface risque de faciliter une connexion plus fiable. Gardez à l’esprit qu’une incapacité à se connecter à des ressources sans fil est plus fréquente en raison d’un problème de point d’accès, d’une faille de conception de réseau ou d’un problème de site environnemental.

> [!NOTE]
> La façon dont vous tenez votre surface Pro ou surface Go peut également affecter la force du signal. Si vous subissez une perte de bande passante, assurez-vous que vous ne disposez pas de la partie supérieure de l’écran, à l’endroit où se trouve le Wi-Fi de téléphone. Même si la partie supérieure de l’affichage ne bloque pas les signaux sans fil, elle peut déclencher le pilote de périphérique pour lancer des modifications qui réduisent la connectivité.

### Conserver la valeur automatique par défaut pour la fonctionnalité de bande passante double

Sur la plupart des appareils surface, vous pouvez configurer les paramètres d’adaptateur du réseau du client de manière à ce qu’ils se connectent uniquement aux points d’accès sans fil de plus de 5 gigahertz (GHz), se connecter à plus de 2,4 GHz ou laisser le système d’exploitation choisir la meilleure option (paramètre automatique par défaut).

**Pour accéder aux paramètres de carte réseau, accédez à:**

- Le **menu Démarrer**  >  **Panneau de configuration**  >  Centre de réseaux **et de partage**  >  **votre carte Wi-Fi**  >  **Propriété**  >  **Configurer**  >  **Avancée**.

![* paramètres WiFi-Band *](images/wifi-band.png) <br>

Gardez à l’esprit que 2,4 GHz dispose de quelques avantages par rapport à 5 GHz: il s’étend de plus en plus et plus facilement dans les murs ou autres objets solides. Si vous n’avez pas de cas d’utilisation claire qui justifie la connexion à 5 GHz, il est recommandé de conserver le paramètre Band dans l’État par défaut afin d’éviter d’éventuelles conséquences indésirables. Par exemple:


- Bon nombre de points d’accès présents dans les hôtels, les cafés et les aéroports n’utilisent toujours 2,4 GHz qu’en bloquant l’accès aux appareils si la bande est définie sur 5 GHz uniquement.
- Dans la mesure où les connexions d’affichage sans fil Miracast nécessitent la fin de l’établissement d’une liaison de 2,4 GHz, les appareils ne seront pas en mesure de se connecter à 5 GHz uniquement.

> [!NOTE]
> Par défaut, les appareils de surface préfèreront une connexion à 5 GHz, le cas échéant. Toutefois, pour préserver la puissance dans un état de batterie faible, surface doit d’abord chercher une connexion de 2,4 GHz.

Vous pouvez également changer le paramètre de bande selon vos besoins en fonction de votre environnement. Par exemple, les utilisateurs qui vivent dans des immeubles de réorganisation de grande densité et disposant de multiples Wi-Fi de points d’accès: en fonction de la présence de périphériques grand public qui se connectent via 2,4 GHz peuvent tirer parti d’une telle connexion de l’appareil surface pour la connexion à 5 GHz uniquement, puis de nouveau basculer sur auto en cas de besoin.

### Paramètres d’itinérance en itinérance sur les appareils surface avec des cartes Intel 

Les utilisateurs peuvent sélectionner un seuil de force du signal qui demande à l’appareil de rechercher un nouveau point d’accès lorsque le signal est en niveau de perte de l’itinérance. Par défaut, les appareils de surface avec des cartes Intel essaient d’être déplacés vers un nouveau point d’accès si la force du signal passe au-dessous de **moyenne** (la puissance du signal de 72 pour cent). Notez également que les organisations peuvent implémenter des protocoles sans fil intégrés sur plusieurs points d’accès réseau pour faciliter l’itinérance d’environnements réseau congestionnés, comme expliqué plus haut dans cette page. 

Même si l’augmentation de l’itinérance au-dessus du **support** peut générer une connectivité améliorée dans les environnements Office ou résidentiels fortement encombrés, elle peut générer une connectivité détériorée lors de l’exécution d’une étape en dehors de ces environnements. 

Il est recommandé de conserver le paramètre de sécurité d’itinérance dans l’État par défaut, sauf si vous rencontrez des problèmes de connectivité dans des scénarios mobiles spécifiques, par exemple, l’exécution d’inspections de site environnemental tout en préservant la connectivité audio et vidéo pendant une réunion. Si vous n’avez remarqué aucune amélioration, rétablissez l’état de moyenne par défaut. Notez que si vous augmentez l’intensité d’itinérance, vous pouvez également accélérer la consommation d’énergie de la batterie. 

**Pour activer l’itinérance en itinérance sur surface:**

1. Accédez à **Démarrer**le  >  **Gestionnaire de périphériques**.
2. Sous **cartes réseau** , sélectionnez **Intel Wi-Fi 6** , puis cliquez avec le bouton droit sur **Propriétés**.
3. Sélectionnez l’onglet **avancé** .
4. Sélectionnez **agressivité d’itinérance** et choisissez votre valeur préférée dans le menu déroulant.

![* Paramètres d’itinérance d’itinérance-Intel *](images/wifi-roaming-int.png) <br>

### Paramètres d’itinérance sur surface Go et surface Pro X

Les employés à l’aide de surface Go doivent sélectionner un seuil de puissance du signal qui invite l’appareil à rechercher un nouveau point d’accès lorsque la force du signal est chute (agressivité de l’itinérance). Par défaut, les appareils de surface essaient d’accéder à un nouveau point d’accès si la force du signal passe au-dessous de **moyenne** (la force du signal de 50 pour cent). Notez que lorsque vous augmentez l’itinérance, vous accélérez la consommation d’énergie de la batterie.

Conservez le paramètre de sécurité d’itinérance dans l’État par défaut, sauf si vous rencontrez des problèmes de connectivité dans des scénarios mobiles spécifiques, par exemple pour effectuer des inspections de site environnemental tout en préservant la connectivité audio et vidéo pendant une réunion. Si vous ne remarquez aucune amélioration, rétablissez l’état de **moyenne** par défaut.

**Pour activer l’itinérance en itinérance dans surface Go, procédez comme suit:**

1. Accédez à **Démarrer > le réseau du panneau**  >  **de configuration et**au  >  **Centre de réseaux et de partage Internet.**
2. Sous **connexions** , sélectionnez **Wi-Fi** , puis cliquez sur **Propriétés.**
3. Sélectionnez **client pour réseaux Microsoft** , puis **configurer** .
4. **Advanced**  >  Dans le menu déroulant, sélectionnez**agressivité** avancée sur l’itinérance et choisissez votre valeur préférée.

![* Paramètres de l’itinérance-QualComm *](images/wifi-roaming.png) <br>


## Conclusion

Les appareils surface sont conçus à l’aide de paramètres par défaut pour une connectivité sans fil optimale, parallèlement à la nécessité de préserver l’autonomie de la batterie. Le moyen le plus efficace d’activer une connectivité fiable pour les appareils surface consiste à utiliser un réseau bien conçu qui prend en charge les normes 802.11 r et 802.11 k. Les utilisateurs peuvent régler les paramètres de carte réseau ou les paramètres d’itinérance, mais ils doivent uniquement le faire en réponse à des facteurs environnementaux spécifiques et rétablir l’État par défaut s’il n’y a pas d’amélioration notable.
