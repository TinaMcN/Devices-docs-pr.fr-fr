---
title: Résoudre les problèmes liés à Miracast sur SurfaceHub
description: Apprenez à résoudre les problèmes rencontrés avec Miracast sur Surface Hub.
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 06/20/2019
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: 96c7c42fe0176f275a8657165d88bf447e57772b
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10834190"
---
# Résoudre les problèmes liés à Miracast sur SurfaceHub

Surface Hub prend en charge la projection sans fil par l'intermédiaire du protocole Miracast. La plupart des moniteurs sans fil et des cartes disponibles aujourd'hui utilisent l’implémentation d’origine de Miracast. Le Surface Hub utilise une version légèrement différente de Miracast, appelée **Miracast AGO (Propriétaire de groupe autonome)**. Une étape de résolution de problème courante en cas d’échec de la projection sans fil sur Surface Hub consiste à tester la projection sur un autre moniteur ou une autre carte sans fil. Toutefois, dans la plupart des cas, ces périphériques n'utilisent pas Miracast AGO et ne traiteront pas la projection sans fil de la même manière que Surface Hub.

Dans la version Miracast classique, l’appareil de projection se connecte au point d’accès configuré par le moniteur prenant en charge Miracast, puis le moniteur renvoie le trafic vers l’appareil de projection au travers du canal réseau de l’appareil de projection. Miracast AGO est un processus de connexion en deux étapes:

- La première étape est une connexion initiale 2,4GHz. 
- Après cette liaison initiale, l’appareil de projection envoie le trafic vers le moniteur en utilisant les paramètres de canal sans fil sur le moniteur. Si le Surface Hub est connecté à un réseau Wi-Fi, le point d’accès, il utilisera le même canal que le réseau connecté; dans le cas contraire, il utilisera le canal Miracast à partir des paramètres.

Il existe généralement deux types de problèmes avec Miracast sur Surface Hub: la [connexion](#connect-issues) et les [performances](#performance-issues). Dans les deux cas, nous vous conseillons de consulter une présentation générale de l’activité du réseau sans fil dans l’emplacement du Hub de surface. L'exécution d'un outil d’analyse de réseau vous montrera les réseaux disponibles et l’utilisation du canal dans l’environnement.

## Problèmes de connexion

Assurez-vous que le Wi-Fi et Miracast sont tous les deux activés dans les paramètres du Surface Hub. 

Si vous avez exécuté une analyse de réseau, vous devez voir Miracast Surface Hub répertorié comme point d’accès. Si le réseau Miracast de surface Hub apparaît sur l’analyse, mais que vous ne pouvez pas l’afficher en tant qu’appareil disponible, vous pouvez essayer d’ajuster le canal Miracast utilisé par surface Hub. 

Lorsque le Surface Hub est connecté à un réseau Wi-Fi, il utilise les mêmes paramètres de canal que le point d’accès Wi-Fi de son point d’accès Miracast. Aux fins de la résolution de problème, débranchez le Surface Hub de tous les réseaux Wi-Fi (tout en gardant le Wi-Fi activé), afin de vérifier le canal utilisé pour Miracast. Vous pouvez sélectionner manuellement le canal Miracast dans les Paramètres. Vous devrez redémarrer le Surface Hub après chaque modification. En règle générale, vous devrez utiliser des canaux qui ne présentent pas une utilisation importante au vu de l’analyse du réseau.

Il est également possible que le problème de connexion soit le résultat d’un problème sur le périphérique connecté. Si l’appareil de projection exécute Windows, il doit s'agir de Windows8.1 ou d'une version ultérieure pour la prise en charge complète de Miracast. Là encore, pour la résolution des problèmes, déconnectez le périphérique de projection de tous les réseaux Wi-Fi. Cela éliminera le basculement de canal entre le canal du point d'accès et le canal Miracast défini sur Surface Hub. En outre, certains paramètres de pare-feu et de stratégie de groupe peuvent être associés à un réseau Wi-Fi.

### Vérifier les pilotes

Il est également conseillé de vérifier que les derniers pilotes et leurs mises à jour sont installés sur l’appareil de projection. Dans le Gestionnaire de périphériques, ouvrez la carte Wi-Fi et la carte vidéo et vérifiez la version de pilote mise à jour. Le [Correctif logiciel 3120232](https://support.microsoft.com/help/3120232/poor-wireless-performance-on-5-ghz-connections-on-surface-pro-3-and-surface-3) est fortement recommandé pour Surface Pro 3 et Surface Pro 4 s’ils disposent d'un ancien pilote Wi-Fi. 

### Consulter le support Miracast

Ensuite, vérifiez que Miracast est pris en charge sur l’appareil. 

1. Appuyez sur les touches Windows + R et tapez `dxdiag`. 
2. Cliquez sur «enregistrer toutes les informations». 
3. Ouvrez le fichier dxdiag.txt enregistré et recherchez **Miracast**. Il doit indiquer **Disponible, avec HDCP**. 
    
### Vérifier le pare-feu
    
Le pare-feu Windows peut bloquer le trafic de Miracast. Le test le plus simple consiste à désactiver le pare-feu et à faire un test de projection. Si Miracast fonctionne avec le pare-feu désactivé, ajoutez une exception pour.

    C:\Windows\System32\WUDFHost.exe
    Allow In/Out connections for TCP and UDP, Ports: All.

### Vérifier les Paramètres de stratégie de groupe

Sur les appareils joints au domaine, la Stratégie de groupe peut également bloquer Miracast. 

1. Utilisez les touches Windows + R et tapez `rsop.msc` pour exécuter le composant logiciel enfichable **Jeu de stratégies résultant**. Cela fait s'afficher les stratégies actuelles appliquées au PC. 
2. Passez en revue **Configuration ordinateur** > **ParamètresWindows** > **Paramètres de sécurité** > **Stratégies de réseau sans fil (IEEE 802.11)**. Il doit s'y trouver un paramètre pour les stratégies sans fil. 
3. Double-cliquez sur le paramètre pour les stratégies sans fil; une boîte de dialogue s’affiche. 
4. Ouvrez l'onglet **Autorisations réseau** et sélectionnez **Autoriser tout le monde à créer tous les profils utilisateur**.

### Consulter les journaux d’événements

Le dernier endroit à vérifier est les journaux des événements. Les événements de Miracast seront enregistrés dans **Wlanautoconfig**. Cela est vrai sur Surface Hub et l’appareil de projection. Si vous exportez les journaux surface Hub, vous pouvez afficher les Wlanautoconfig du Hub de surface dans le dossier **WindowsEventLog** . Les erreurs du journal des événements peuvent fournir des informations supplémentaires sur l'endroit où la connexion a échoué.

## Problèmes de performances

Une fois que la projection sans fil est connectée, il est possible de voir des problèmes de performances à l’origine de latence. C’est généralement le résultat d’une saturation globale du canal ou d'une situation qui entraîne le basculement de canal. 

Dans le cas de la saturation du canal, reportez-vous à l’analyse de réseau et essayez d’utiliser des canaux comportant moins de trafic.

Le basculement de canal a lieu lorsque la carte Wi-Fi doit envoyer le trafic sur plusieurs canaux. Certains canaux prennent en charge la sélection de fréquence dynamique (DFS). La DFS est utilisée sur les canaux 49 à 148. Certains pilotes Wi-Fi affichent des performances médiocres lorsqu'ils sont connectés à un canal DFS. Si Miracast présente des performances médiocres lorsque connecté à un canal DFS, essayez la projection sur un canal non DFS. Le Surface Hub et l'appareil de projection doivent utiliser des canaux non DFS.

Si l’appareil de projection et le Surface Hub sont tous deux connectés au réseau Wi-Fi, par des points d’accès différents avec des canaux différents, cela force le Surface Hub et l’appareil de projection à basculer de réseau pendant la connexion de Miracast. Cela entraîne une projection sans fil médiocre et des performances réseau médiocres sur le Wi-Fi. Le basculement de réseau affecte les performances de tout le trafic sans fil, pas simplement de la projection sans fil. 

Le basculement de réseau se produit également si l’appareil de projection est connecté à un réseau Wi-Fi à l’aide d’un autre canal que le canal qu'utilise le Surface Hub pour Miracast. Par conséquent, il est recommandé de définir le canal Miracast du Hub de surface pour le même canal que le point d’accès le plus communément utilisé. 

S’il existe plusieurs réseaux Wi-Fi ou points d’accès dans l’environnement, le basculement de canal est inévitable dans une certaine mesure. La meilleure solution dans ce cas consiste à vérifier que tous les pilotes Wi-Fi sont bien à jour.

## Contacter le support

Si vous avez des questions ou si vous avez besoin d’aide, vous pouvez [créer une demande de support](https://support.microsoft.com/supportforbusiness/productselection).
