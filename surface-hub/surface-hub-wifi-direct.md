---
title: Comment Surface Hub résout les problèmes de sécurité de Wi-Fi Direct
description: Recommandations en matière de risques liés à la sécurité Wi-Fi direct.
keywords: historique des modifications
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 11/27/2019
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: d877d9b6a4e330a74a9d79cf1150487d89c0da23
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832766"
---
# Comment le Surface Hub traite les problèmes de sécurité liés à Wi-Fi Direct

MicrosoftSurface Hub est un outil de productivité tout-en-un qui permet aux équipes d'assurer un meilleur brainstorming, une meilleure collaboration et de partager des idées plus facilement. Surface Hub repose sur Miracast pour la projection sans fil via Wi-Fi direct.

Cet article décrit les failles de sécurité Wi-Fi direct, la façon dont surface Hub répond à ces risques et la manière dont les administrateurs peuvent configurer surface Hub pour le niveau de sécurité le plus élevé. Ces informations permettront aux clients ayant des exigences de sécurité élevée de protéger leurs réseaux et leurs données connectés en surface Hub.

Le public ciblé pour cet article s’adresse aux administrateurs de réseaux et de réseaux informatiques qui souhaitent déployer surface Hub dans leur environnement d’entreprise avec des paramètres de sécurité optimaux.

## Vue d'ensemble

La sécurité de surface Hub dépend largement de la norme Wi-Fi direct/Miracast et de la 802,11 associée, de l’accès protégé Wi-Fi (WPA2) et de l’installation protégée sans fil (WPS). Étant donné que l’appareil ne prend en charge que les services WPS (par opposition à la clé pré-partagée de WPA2 [PSK] ou WPA2 Enterprise), les problèmes souvent liés au chiffrement 802,11 sont simplifiés.

Surface Hub s’exécute sur pair avec le champ des récepteurs Miracast. C’est pourquoi il est vulnérable à un ensemble similaire d’exploits en tant que tous les appareils réseau sans fil basés sur WPS. Toutefois, la mise en œuvre de la surface Hub de WPS est dotée de fonctions supplémentaires intégrées. Par ailleurs, son architecture interne permet d’éviter à un attaquant qui a compromis la couche Wi-Fi direct/Miracast de se déplacer au-delà de l’interface réseau vers d’autres surfaces d’attaque et des réseaux d’entreprise connectés.

## Arrière-plan Wi-Fi Direct

Miracast fait partie de la norme d’affichage Wi-Fi, qui est prise en charge par le protocole Wi-Fi direct. Ces normes sont prises en charge sur les appareils mobiles modernes pour le partage d’écran et la collaboration.

Le Wi-Fi direct ou le Wi-Fi «pair à pair» (P2P) est une norme de l’alliance Wi-Fi pour les réseaux «ad-hoc». Les appareils pris en charge peuvent communiquer directement et créer des groupes de réseaux sans un point d’accès Wi-Fi ou une connexion Internet classique.

La sécurité pour Wi-Fi direct est fournie par WPA2 dans la norme WPS. Le mécanisme d’authentification pour les appareils peut être un code confidentiel numérique (WPS-PIN), un bouton de Poussée physique ou virtuel (WPS-PBC), ou un message hors-bande tel que la communication de champ proche (WPS-OOO). Surface Hub prend en charge à la fois la méthode PIN et la méthode de bouton bascule, qui est la valeur par défaut.

Dans Wi-Fi direct, les groupes sont créés comme l’un des types suivants:
- *Permanent*, qui peut être utilisé pour la reconnexion automatique à l’aide de la documentation de clé stockée
- *Temporaire*, où les appareils ne peuvent pas s’authentifier de nouveau sans action de l’utilisateur

Les groupes Wi-Fi direct déterminent le propriétaire d’un *groupe* (Go) par le biais d’un protocole de négociation qui imite la fonctionnalité «station» ou «point d’accès» pour le groupe Wi-Fi établi. Le Wi-Fi direct GO fournit une authentification (via un «bureau d’enregistrement interne») et facilite les connexions réseau en amont. Dans le cas de surface Hub, il n’y a aucun problème de négociation. Le réseau fonctionne uniquement en mode autonome et surface Hub est toujours le propriétaire du groupe. Enfin, surface Hub ne relie pas d’autres réseaux WiFi directs en tant que client.

## Comment surface Hub traite les vulnérabilités du Wi-Fi direct

**Vulnérabilités et attaques dans le processus d’invitation, de diffusion et de découverte directes Wi-Fi:** Les attaques Wi-Fi direct/Miracast pourront cibler des faiblesses dans l’établissement du groupe, la découverte d’homologues, la diffusion d’appareil ou les processus d’invitation.

|Vulnérabilité Wi-Fi direct | Réduction de surface Hub |
| --- | --- |
| Le processus de découverte peut rester actif pendant une période prolongée, ce qui peut permettre l’établissement d’invitations et de connexions sans l’approbation du propriétaire de l’appareil. | Surface Hub ne fonctionne que en tant que propriétaire du groupe, qui n’effectue pas les processus de découverte du client et de négociation automatique. Vous pouvez désactiver entièrement la projection sans fil pour désactiver la diffusion. |
| L’invitation et la découverte par le biais de PBC permet à un attaquant non authentifié d’effectuer des tentatives de connexion répétées, ou des connexions non authentifiées sont automatiquement acceptées. | Si vous avez besoin de la sécurité du code confidentiel WPS, les administrateurs peuvent réduire le risque d’accès non autorisé à ces connexions ou «inviter une invitation» à plusieurs |

Installation de la fonctionnalité **Wi-Fi Protected (WPS) sur le bouton d’accès rapide (PBC)** Les faiblesses publiques ont été illustrées dans la conception et l’implémentation de la méthode d’ÉPINGLe WPS. WPS-PBC a d’autres vulnérabilités qui pourraient permettre des attaques actives par le biais d’un protocole conçu pour une utilisation ponctuelle.

| Vulnérabilité Wi-Fi direct | Réduction de surface Hub |
| --- | --- |
| La méthode de connexion au moyen d'un bouton WPS est vulnérable aux personnes malveillantes actives. Les États de spécification WPS suivants: «la méthode PBC possède zéro bit d’entropie et ne protège qu’contre les attaques d’espionnage passif. Elle protège contre les écoutes clandestines passives et prend les mesures nécessaires pour empêcher un appareil de rejoindre un réseau non sélectionné par le propriétaire de l'appareil. En revanche, l’absence d’authentification implique qu’PBC ne protège pas contre les attaques actives.» Les pirates peuvent utiliser le brouillage sélectif sans fil ou d’autres techniques de déni de service pour déclencher une connexion ou un accès Wi-Fi involontaire. Par ailleurs, un attaquant actif qui a simplement une proximité physique peut détruire de manière répétée tout groupe Wi-Fi direct et tenter de l’attaquer jusqu’à ce qu’il réussisse. | Activez la sécurité du code confidentiel WPS dans la configuration surface Hub. Les spécifications du Wi-Fi: "la méthode PBC doit être utilisée uniquement si aucun bureau d’enregistrement prenant en charge l’ÉPINGLe n’est disponible et que l’utilisateur du réseau local sans fil accepte les risques associés à PBC." |
| Les implémentations de code confidentiel (WPS) peuvent faire l’objet d’attaques en force visant à cibler une vulnérabilité dans la norme WPS. La vérification de la réutilisation du code confidentiel a conduit à plusieurs vulnérabilités d’implémentation au cours des dernières années sur une gamme de constructeurs de matériel Wi-Fi. Dans 2011, les chercheurs Stefan Viehböck et Craig Heffner ont divulgué des informations sur cette vulnérabilité et des outils tels que «réagissez» en tant que preuve de concept. |   L’implémentation Microsoft de WPS dans surface Hub change le code confidentiel toutes les 30 secondes. Pour déchiffrer le code confidentiel, une personne malveillante doit achever toute l’opération en moins de 30 secondes. En raison de l’état actuel des outils et de la recherche dans le cadre de cette zone, une attaque par craquage en force de l’utilisateur sur WPS est improbable. |
| WPS-PIN peut être piraté par une attaque hors connexion en raison d’une touche initiale faible (E-S1, E S2) entropique. Dans 2014, Dominique Bongard a décrit une attaque de type «Pixie poussière» dans laquelle le générateur de nombres aléatoires (PRNG) de l’appareil sans fil a permis une attaque en force insuffisante. | L’implémentation Microsoft de WPS dans surface Hub ne peut pas être exposée aux attaques brutales en force. Le protocole WPS-PIN est choisi au hasard pour chaque connexion. |

**Exposition inattendue des services réseau:** Les démons réseau destinés aux services Ethernet ou WLAN peuvent être exposés par erreur en raison d’une configuration inattendue (par exemple, une liaison à des interfaces «All»/0.0.0.0). D’autres causes possibles incluent un pare-feu de périphérique mal configuré ou des règles de pare-feu manquantes.

| Vulnérabilité Wi-Fi direct | Réduction de surface Hub |
| --- | --- |
| Une configuration incorrecte lie un service réseau vulnérable ou non authentifié à «toutes» les interfaces, ce qui inclut l’interface Wi-Fi Direct. Cela peut exposer des services qui ne sont pas accessibles aux clients Wi-Fi direct, qui peuvent être authentifiés de manière faible ou automatique. | Dans surface Hub, les règles de pare-feu par défaut autorisent uniquement les ports réseau TCP et UDP requis et refusent par défaut toutes les connexions entrantes. Configurez une authentification forte en activant le mode code confidentiel WPS.|

**Pontage Wi-Fi direct et autres réseaux filaires ou sans fil:** Le pontage réseau entre les réseaux WLAN ou Ethernet est une violation de la spécification Wi-Fi direct. Une telle passerelle ou configuration infructueuse risque de limiter ou de supprimer efficacement les contrôles d’accès sans fil pour le réseau d’entreprise interne.

| Vulnérabilité Wi-Fi direct | Réduction de surface Hub |
| --- | --- |
| Les appareils Wi-Fi Direct peuvent autoriser un accès non authentifié ou faiblement authentifié aux connexions réseau reliées par un pont. Cela peut permettre aux réseaux Wi-Fi d’acheminer le trafic vers un réseau local Ethernet ou une autre infrastructure ou des réseaux WLAN d’entreprise en violation de protocoles de sécurité informatiques existants. | Surface Hub ne peut pas être configuré pour relier les interfaces sans fil ou autoriser le routage entre réseaux disparates. Les règles de pare-feu par défaut ajoutent une défense en profondeur à tous ces routages ou ces connexions de pont. |

**Utilisation du mode «hérité» Wi-Fi direct:** L’exposition à des réseaux ou périphériques inattendus est susceptible de se produire lorsque vous travaillez en mode «hérité». Des usurpations d'appareil ou des connexions involontaires peuvent survenir si le protocole WPS-PIN n'est pas activé.

| Vulnérabilité Wi-Fi direct | Réduction de surface Hub |
| --- | --- |
| En prenant en charge à la fois Wi-Fi Direct et les clients d’infrastructure 802.11, le système fonctionne en mode de prise en charge «hérité». Cela risque de rendre la phase de configuration de la connexion indéfinie, ce qui permet aux groupes d’être liés ou aux périphériques invités de se connecter bien après la fin de la phase de configuration prévue. |    Surface Hub ne prend pas en charge les clients hérités Wi-Fi direct. Seules les connexions Wi-Fi Direct peuvent être effectuées sur le Surface Hub, même lorsque le mode WPS-PIN est activé. |

**Négociation de l’accès Wi-Fi direct lors de la configuration de la connexion:** Le propriétaire du groupe dans Wi-Fi direct est analogue au point d’accès d’un réseau sans fil 802,11 conventionnel. La négociation peut être manipulée par un appareil malveillant.

|Vulnérabilité Wi-Fi direct |   Réduction de surface Hub |
| --- | --- |
| Si les groupes sont établis de manière dynamique ou si l’appareil Wi-Fi direct peut être mis en place pour joindre de nouveaux groupes, la négociation de propriétaire de groupe peut être gagnée par un appareil malveillant qui spécifie toujours la valeur de propriétaire du groupe maximale de 15. (Toutefois, la connexion échoue si l’appareil est configuré pour être toujours propriétaire du groupe.)  | Surface Hub tire parti du «mode autonome» Wi-Fi direct qui ignore la phase de négociation GO de l’installation de connexion. Et surface Hub est toujours le propriétaire du groupe. |

**Désauthentification Wi-Fi involontaire ou malveillante:** La désactivation de la technologie Wi-Fi est une vieille attaque qui permet à un attaquant d’expédier des fuites d’informations dans le processus de configuration de la connexion, de déclencher de nouvelles négociations à quatre directions, de cibler des WPS Wi-Fi directs-PBC pour les attaques actives ou de créer des attaques par déni de service.

| Vulnérabilité Wi-Fi direct | Réduction de surface Hub |
| --- | --- |
| Les paquets de connexion peuvent être envoyés par un attaquant non authentifié de sorte que la station puisse s’authentifier de nouveau pour espionner la connexion. Des attaques cryptographiques ou par force brute peuvent être tentées lors de cet établissement de liaison. La prévention de ces attaques implique de mettre en œuvre des stratégies de longueur et de complexité pour les clés prépartagées, en configurant le point d’accès (le cas échéant) pour détecter les niveaux malveillants de paquets de connexion et en utilisant WPS pour générer automatiquement des clés fortes. Dans le mode PBC, l’utilisateur interagit avec un bouton physique ou virtuel pour autoriser une association de périphériques arbitraire. Ce processus doit se produire uniquement lors de l’installation, au sein d’une courte fenêtre. Une fois que le bouton est automatiquement «appuyé», l’appareil accepte toute station qui s’associe par le biais d’une valeur de code confidentiel canonique (toutes les zéros). La désauthentification peut forcer un processus de configuration récurrent. |   Surface Hub utilise des WPS en mode code confidentiel ou PBC. Aucune configuration PSK n’est autorisée. Cette méthode permet d’appliquer une génération de clés fortes. Il est recommandé d’activer la sécurité du code confidentiel WPS pour surface Hub. |
| Outre les attaques par déni de service, les paquets de connexion peuvent être utilisés pour déclencher une reconnexion qui s’ouvre de nouveau dans la fenêtre de la possibilité d’attaques actives contre WPS-PBC. |   Activez la sécurité du code confidentiel WPS dans la configuration surface Hub. |

**Divulgation de base des informations sans fil:** Les réseaux sans fil, 802,11 ou autres, sont inhérents au risque de divulgation d’informations. Même si ces informations sont essentiellement des métadonnées de connexion ou de périphérique, ce problème reste un risque connu pour tout administrateur réseau 802,11. Wi-Fi Direct avec une authentification d'appareil via WPS-PIN révèle dans les faits les mêmes informations qu'un réseau 802.11 Entreprise ou PSK.

| Vulnérabilité Wi-Fi direct | Réduction de surface Hub |
| --- | --- |
| Lors de la diffusion, de la configuration de la connexion ou même du fonctionnement normal de connexions déjà chiffrées, les informations de base sur les appareils et les tailles de paquets sont transmises sans fil. D’un point de vue général, un agresseur local qui se trouve dans la plage sans fil peut examiner les éléments d’informations 802,11 pertinents pour déterminer les noms des appareils sans fil, les adresses MAC des équipements de communication et éventuellement d’autres informations, telles que la version de la pile sans fil, la taille des paquets ou les options du point d’accès ou du propriétaire du groupe configurées.  | Le réseau Wi-Fi direct qu’utilise surface Hub ne peut pas être protégé par des fuites de métadonnées, comme pour les réseaux sans fil 802,11 entreprise ou PSK. La sécurité physique et la suppression des menaces potentielles provenant de la proximité sans fil peuvent vous aider à réduire le risque de fuite d’informations potentielles. |

**Piratages sans fil ou usurpation d’identité:**  L’usurpation du nom sans fil est une exploitation simple et notoire qu’un agresseur local peut utiliser pour inciter les utilisateurs à se connecter.

| Vulnérabilité Wi-Fi direct | Réduction de surface Hub |
| --- | --- |
| Par l’usurpation d’identité ou le clonage du nom sans fil ou du «SSID» du réseau cible, une personne malveillante pourrait amener l’utilisateur à se connecter à un réseau malveillant factice. Par le biais d’une prise en charge non authentifiée et automatique de Miracast, un attaquant peut capturer les matériaux d’affichage prévus ou lancer des attaques réseau sur l’appareil de connexion. | Même s’il n’existe aucune protection spécifique contre la participation à un hub surface usurpé, cette vulnérabilité est partiellement atténuée de deux manières. En premier lieu, toute attaque potentielle doit être lancée physiquement dans le cadre de la portée Wi-Fi. Deuxièmement, cette attaque n’est possible que pendant la première connexion. Les connexions suivantes utilisent un groupe Wi-Fi permanent et Windows mémorisera et définira la priorité de cette connexion antérieure lors de l’utilisation future du Hub. (Remarque: l’usurpation d’adresse MAC, du canal Wi-Fi et de l’identifiant SSID simultanément n’a pas été envisagée pour ce rapport et risque de produire un comportement Wi-Fi incohérent. Globalement, cette faiblesse est un problème fondamental pour n’importe quel réseau sans fil 802,11 dépourvu de protocoles Enterprise WPA2 tels que EAP-TLS ou EAP-PWD, qui ne prend pas en charge le Wi-Fi direct. |

## Recommandations renforcées concernant Surface Hub

Le Surface Hub est conçu pour favoriser la collaboration et permettre aux utilisateurs de rapidement et efficacement démarrer des réunions ou d'y participer. Les paramètres Wi-Fi par défaut de surface Hub sont optimisés pour ce scénario.

Pour une sécurité supplémentaire de l’interface sans fil, les utilisateurs de surface Hub doivent activer le paramètre de sécurité WPS-PIN. Ce paramètre désactive le mode WPS-PBC et propose une authentification client. Il offre le niveau de protection le plus élevé en empêchant toute connexion non autorisée à surface Hub.

Si vous avez encore des doutes sur l’authentification et l’autorisation de surface Hub, nous vous recommandons de connecter l’appareil à un réseau distinct. Vous pouvez utiliser un réseau Wi-Fi (par exemple, un réseau Wi-Fi «invité») ou un réseau Ethernet distinct, de préférence un réseau physique entièrement différent. Mais un VLAN peut également renforcer la sécurité. Bien entendu, cette approche risque d’empêcher les connexions aux ressources ou services réseau internes et de nécessiter une configuration réseau supplémentaire pour pouvoir obtenir l’accès.

Également recommandé:
- [Installer les mises à jour système normales](manage-windows-updates-for-surface-hub.md) 
- Mettre à jour les paramètres Miracast pour désactiver le mode de présentation automatique

## En savoir plus

- [Spécifications Wi-Fi Direct](http://www.wi-fi.org/discover-wi-fi/wi-fi-direct)
- [Spécification de WPS (Wireless Protected Setup)](http://www.wi-fi.org/discover-wi-fi/wi-fi-protected-setup)



