---
title: Optimiser la connectivité Wi-Fi pour les appareils surface
description: Cette rubrique décrit les paramètres de Wi-Fi pour s’assurer que les appareils Surface restent connectés dans des environnements réseau saturés et des scénarios mobiles.
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
ms.date: 01/15/2021
ms.openlocfilehash: 69ca7bc7383a122dfd4f069135319b92ff7edfb0
ms.sourcegitcommit: 1053479c191fd10651d31a466fad1769fb0cd28b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/16/2021
ms.locfileid: "11271378"
---
# Optimiser la connectivité Wi-Fi pour les appareils surface


Pour rester connectés toute la journée à l’autonomie de la batterie, les appareils Surface implémentent des paramètres de connectivité sans fil qui équilibrent les performances et la conservation de l’énergie. En dehors des scénarios de mobilité les plus exigeants, les utilisateurs peuvent maintenir une connectivité sans fil suffisante sans modifier la carte réseau par défaut ou les paramètres associés. Cette page présente les principales considérations en matière de connectivité sans fil dans les scénarios mobiles utilisant les appareils Surface les plus récents, notamment Surface Pro 7+, Surface Laptop Go, Surface Go 2, Surface Pro X, Surface Laptop 3, Surface Book 3 et Surface Pro 7.

## Conditions préalables

Ce document suppose que vous avez déployé avec succès un réseau sans fil qui prend en charge 802.11n (Wi-Fi 4) ou une ultérieure, conformément aux recommandations des meilleures pratiques des principaux fournisseurs d’équipements.

## Configuration des points d’accès pour des fonctionnalités d’itinérance optimales

Si vous gérez un réseau sans fil qui est généralement accessible par de nombreux types différents d’appareils clients, il est recommandé d’activer des protocoles spécifiques sur les points d’accès dans votre réseau local sans fil, comme décrit dans l’itinérance rapide avec [802.11k, 802.11v et 802.11r.](https://docs.microsoft.com/windows-hardware/drivers/network/fast-roaming-with-802-11k--802-11v--and-802-11r) Les appareils Surface peuvent tirer parti des protocoles sans fil suivants :

- **802.11r.** «**Transition BSS** rapide » accélère la connexion aux nouveaux points d’accès sans fil en réduisant le nombre d’images requises pour que votre appareil puisse accéder à une autre API lorsque vous vous déplacez avec votre appareil. Dans la nouvelle génération d’appareils Surface publiée depuis 2019, les utilisateurs finaux peuvent accéder aux paramètres d’itinérance agressif sur leur appareil. Bien que la modification des paramètres par défaut ne soit pas recommandée, les utilisateurs doivent connaître cette fonctionnalité et comprendre comment des paramètres spécifiques peuvent avoir un impact sur leur capacité à rester connectés.
- **802,11K.** **« Rapports voisins »** fournit aux appareils des informations sur les conditions actuelles aux points d’accès voisins. Il peut aider votre appareil Surface à choisir la meilleure API à l’aide de critères autres que la force du signal, tels que l’utilisation de l’AP.

Des appareils Surface spécifiques peuvent également utiliser les « images de gestion de la transition BSS » 802.11v, qui fonctionnent de la même façon que 802,11k pour fournir des informations sur les projets APS candidats à proximité. Il s’agit notamment de Surface Pro 7+, Surface Go, Surface Go 2, Surface Pro 7, Surface Pro X et Surface Laptop 3. 

## Gestion des paramètres utilisateur

Vous pouvez obtenir des fonctionnalités d’itinérance optimales via un réseau bien conçu qui prend en charge 802.11r et 802.11k sur tous les points d’accès. Il est recommandé de s’assurer que votre réseau est correctement configuré pour offrir aux utilisateurs la meilleure expérience sans fil possible par rapport à la tentative de gestion des paramètres utilisateur sur des appareils individuels. 

### Meilleures pratiques et paramètres utilisateur recommandés

Dans certains cas, la modification des paramètres avancés de carte réseau intégrés aux appareils Surface peut faciliter une connexion plus fiable. Gardez à l’esprit toutefois qu’une incapacité à se connecter aux ressources sans fil est plus souvent due à un problème de point d’accès, à une faille de conception réseau ou à un problème de site environnemental.

> [!NOTE]
> La façon dont vous maintenez votre Surface Pro ou Surface Go peut également affecter la force du signal. Si vous rencontrez une perte de bande passante, vérifiez que vous ne maintenez pas la partie supérieure de l’affichage, où se trouve le récepteur d'Wi-Fi radio. Bien que le fait de maintenir la partie supérieure de l’affichage ne bloque pas les signaux sans fil, il peut déclencher le pilote de périphérique pour initier des modifications qui réduisent la connectivité.

### Conserver le paramètre automatique par défaut pour la fonctionnalité de bande passante double

Sur la plupart des appareils Surface, vous pouvez configurer les paramètres de carte réseau client de manière à ce qu’ils ne se connectent qu’aux APS sans fil de plus de 5 gigahertz (GHz), se connectent uniquement à plus de 2,4 GHz ou laisser le système d’exploitation choisir la meilleure option (paramètre automatique par défaut).

**Pour accéder aux paramètres de carte réseau, accédez à :**

- **Démarrer**  >  **Panneau de contrôle**  >  **Centre de réseau et de partage**  >  **votre adaptateur Wi-Fi réseau**  >  **Propriétés**  >  **Configurer**  >  **Avancé**.

![* Paramètres de la bande wifi*](images/wifi-band.png) <br>

Gardez à l’esprit que 2,4 GHz présente certains avantages par rapport à 5 GHz : il s’étend de plus en plus facilement à travers les murs ou d’autres objets unis. Sauf si vous avez un cas d’utilisation clair qui justifie la connexion à 5 GHz, il est recommandé de laisser le paramètre bande dans l’état par défaut afin d’éviter les conséquences négatives possibles. Par exemple:


- De nombreux points d’accès situés dans les restaurants, les café et les aéroports utilisent toujours uniquement 2,4 GHz, ce qui bloque l’accès aux appareils si la bande est définie sur 5 GHz uniquement.
- Étant donné que les connexions d’affichage sans fil Miracast nécessitent la liaison initiale sur des canaux de 2,4 GHz, les appareils ne pourront pas se connecter à 5 GHz uniquement.

> [!NOTE]
> Par défaut, les appareils Surface préfèrent se connecter à 5 GHz s’ils sont disponibles. Toutefois, pour préserver l’alimentation dans un état de batterie faible, Surface recherche d’abord une connexion à 2,4 GHz.

Vous pouvez également faire bascule le paramètre de bande selon vos besoins en fonction de votre environnement. Par exemple, les utilisateurs qui habitent dans des immeubles à immeubles à densité élevée avec plusieurs points d’accès Wi-Fi (en mettant en avant la présence d’appareils grand public qui diffusent toutes les données via 2,4 GHz) bénéficieront probablement de la configuration de leur appareil Surface pour qu’il se connecte uniquement à 5 GHz, puis revenir à l’auto si nécessaire.

### Paramètres d’itinérance agressif sur les appareils Surface avec adaptateurs Intel 

Les utilisateurs peuvent sélectionner un seuil de force du signal qui invite l’appareil à rechercher un nouveau point d’accès lorsque le signal tombe en puissance (intensité d’itinérance). Par défaut, les appareils Surface avec cartes Intel tentent d’accéder à un nouveau point d’accès si la force du signal passe en dessous de **moyenne** (force du signal de 72 %). Notez également que les organisations peuvent implémenter des protocoles sans fil spécifiques sur plusieurs points d’accès réseau pour faciliter l’itinérance des environnements réseau saturés, comme expliqué précédemment sur cette page. 

Bien que l’augmentation **** de l’intensité de l’itinérance au-dessus de la moyenne puisse améliorer la connectivité dans les environnements de bureau ou résidentiels très saturés, cela peut entraîner une connectivité dégradée en dehors de ces environnements. 

Il est recommandé de laisser le paramètre d’agressive itinérance dans l’état par défaut, sauf si vous rencontrez des problèmes de connectivité dans des scénarios mobiles spécifiques tels que la conduite d’inspections de sites environnementaux tout en conservant la connectivité vocale et vidéo pendant une réunion de conférence. Si vous ne remarquez aucune amélioration, revenir à l’état moyen par défaut. Notez que si vous augmentez l’accélération de l’itinérance, vous accélèrez également la consommation d’énergie de la batterie. 

**Pour activer l’itinérance agressive sur Surface :**

1. Go to **Start**  >  **Device Manager**.
2. Sous **Cartes réseau,** sélectionnez **Intel Wi-Fi 6,** puis cliquez avec le bouton droit sur **Propriétés.**
3. Sélectionnez **l’onglet** Avancé.
4. Sélectionnez **l’itinérance agressive et** choisissez votre valeur préférée dans le menu déroulant.

![* Paramètres d’agressif d’itinérance -Intel *](images/wifi-roaming-int.png) <br>

### Paramètres d’agressif d’itinérance sur Surface Go et Surface Pro X

Les employés de ligne frontale utilisant Surface Go peuvent sélectionner un seuil de force du signal qui invite l’appareil à rechercher un nouveau point d’accès lorsque la force du signal diminue (intensité d’itinérance). Par défaut, les appareils Surface tentent d’accéder à un nouveau point d’accès si la force du signal passe en dessous de **moyenne** (force du signal de 50 %). Notez que chaque fois que vous augmentez l’accélération de l’itinérance, vous accélèrez la consommation d’énergie de la batterie.

Laissez le paramètre d’itinérance agressif dans l’état par défaut, sauf si vous rencontrez des problèmes de connectivité dans des scénarios mobiles spécifiques, tels que la conduite d’inspections de sites environnementaux tout en conservant la connectivité vocale et vidéo pendant une réunion de conférence. Si vous ne remarquez aucune amélioration, revenir à l’état **moyen** par défaut.

**Pour activer l’itinérance agressive sur Surface Go :**

1. Go to **Start > Control Panel**Network and  >  **Internet**Network and Sharing  >  **Center.**
2. Sous **Connexions,** **sélectionnez Wi-Fi,** puis **Propriétés.**
3. Sélectionnez **Client pour Les réseaux Microsoft,** puis **Configurer**
4. Sélectionnez ****  >  **Advanced Roaming Aggressiveness et** choisissez votre valeur préférée dans le menu déroulant.

![* Paramètres d’agressif d’itinérance -QualComm *](images/wifi-roaming.png) <br>


## Conclusion

Les appareils Surface sont conçus avec des paramètres par défaut pour une connectivité sans fil optimale équilibrée et la nécessité de préserver l’autonomie de la batterie. Le moyen le plus efficace d’activer une connectivité fiable pour les appareils Surface consiste à passer par un réseau bien conçu qui prend en charge les appareils 802.11r et 802.11k. Les utilisateurs peuvent ajuster les paramètres de carte réseau ou l’agressive de l’itinérance, mais ne doivent le faire qu’en réponse à des facteurs environnementaux spécifiques et revenir à l’état par défaut en l’absence d’amélioration notable.
