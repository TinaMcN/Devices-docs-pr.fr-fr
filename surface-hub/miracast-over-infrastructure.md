---
title: Miracast sur le réseau local ou le réseau sans fil existant
description: Windows10vous permet d’envoyer un flux Miracast sur un réseau local.
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 04/24/2020
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: d63b3de0f76cb70fe86fff246d82cbe166278461
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10834207"
---
# Miracast sur l’infrastructure

Dans Windows10, version1703, Microsoft a étendu la possibilité d’envoyer un flux Miracast sur un réseau local plutôt que sur une liaison sans fil directe. Cette fonctionnalité est basée sur le protocole [MS-MICE (Miracast over Infrastructure Connection Establishment)](https://msdn.microsoft.com/library/mt796768.aspx).

Miracast over Infrastructure offre un certain nombre d’avantages:

- Windows détecte automatiquement lorsque l’envoi du flux vidéo sur ce chemin d’accès est applicable.
- Windows ne choisit cet itinéraire que si la connexion transite via Ethernet ou un réseau Wi-Fi sécurisé.
- Les utilisateurs n’ont pas à modifier la façon dont ils se connectent à un récepteur Miracast. Ils utilisent la même expérience utilisateur que pour les connexions Miracast standard.
- Aucune modification des pilotes sans fil actuels ou du matériel du PC n’est requise.
- Cela fonctionne correctement avec le matériel sans fil ancien, non optimisé pour Miracast sur Wi-Fi Direct.
- Il s’appuie sur une connexion existante qui réduit le temps de connexion et fournit un flux très stable.


## Fonctionnement

Les utilisateurs essaient de se connecter à un destinataire Miracast par le biais de leur adaptateur Wi-Fi comme auparavant. Lorsque la liste des récepteurs Miracast est remplie, Windows10 identifie que le récepteur est capable de prendre en charge une connexion sur l’infrastructure. Lorsque l’utilisateur sélectionne un récepteur Miracast, Windows10 tente de résoudre le nom d’hôte de l’appareil via un DNS standard et via la multidiffusion DNS (mDNS). Si le nom n’est pas résolu par l’une ou l’autre méthodeDNS, Windows10 rétablit la session Miracast avec la connexion Wi-Fi Direct standard.

> [!NOTE]
> Pour plus d’informations sur la séquence de négociation de connexion, voir [Miracast sur le protocole MS-souris établissant une](https://msdn.microsoft.com/library/mt796768.aspx) connexion.




## Activation de Miracast over Infrastructure 

Si vous avez un Surface Hub ou un autre appareil Windows10 qui a été mis à jour vers Windows10, version1703, vous disposez automatiquement de cette nouvelle fonctionnalité. Pour en bénéficier dans votre environnement, vous devez vous assurer que les conditions suivantes sont remplies dans votre déploiement:

- Le SurfaceHub ou l'appareil (PC ou téléphone Windows) doit exécuter Windows10, version1703.
- Ouvrez le port TCP: **7250**.
- Un Surface Hub ou un PC Windows peut se comporter comme un *récepteur* Miracast over Infrastructure. Un PC ou un téléphone Windows peut se comporter comme une *source* Miracast over Infrastructure.
    - En tant que récepteur Miracast, le Surface Hub ou l'appareil doit être connecté à votre réseau d’entreprise via Ethernet ou une connexion Wi-Fi sécurisée (par exemple, WPA2-Enterprise ou WPA2-PSK). Si surface Hub ou appareil est connecté à une connexion Wi-Fi ouverte, Miracast sur l’infrastructure sera désactivé.
    - En tant que source Miracast, le PC ou le téléphone Windows doit être connecté au même réseau d’entreprise via Ethernet ou une connexion Wi-Fi sécurisée.
- Le nom d’hôte DNS (nom de l’appareil) du Hub surface ou de l’appareil doit être résolu via vos serveurs DNS. Vous pouvez y parvenir en autorisant votre SurfaceHub à s’inscrire automatiquement via le DNS dynamique ou en créant manuellement un enregistrementA ouAAAA pour le nom d’hôte du SurfaceHub. 
- Les PC Windows10 doivent être connectés au même réseau d’entreprise via Ethernet ou une connexion Wi-Fi sécurisée. 
-   Sur les PC Windows 10, la fonctionnalité **de projection vers ce PC** doit être activée dans les paramètres système et l’interface Wi-Fi doit être activée pour répondre aux demandes de découverte qui ne se produisent que par le biais de la carte Wi-Fi.


Il est important de noter que le protocole Miracast over Infrastructure ne remplace pas le protocole Miracast standard. En revanche, la fonctionnalité est complémentaire et fournit un avantage aux utilisateurs qui font partie du réseau d’entreprise. Les utilisateurs qui sont invités dans un emplacement particulier et n’ont pas accès au réseau d’entreprise continuent à se connecter à l’aide de la méthode de connexion Wi-Fi Direct.

Le paramètre **InBoxApps/WirelessProjection/PinRequired** dans le [Fournisseur de services de configuration (CSP) SurfaceHub](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/surfacehub-csp) n’est pas nécessaire pour Miracast over Infrastructure. Cela est dû au fait que Miracast over Infrastructure fonctionne uniquement lorsque les deux appareils sont connectés au même réseau d’entreprise. Cela élimine la restriction de sécurité qui manquait auparavant à Miracast. Nous vous recommandons de continuer à utiliser ce paramètre (si vous le faisiez précédemment), car Miracast se rétablit à la version Miracast normale si la connexion de l’infrastructure ne fonctionne pas. 

## Forum Aux Questions
**Pourquoi ai-je besoin d’un Wi-Fi pour utiliser Miracast sur l’infrastructure?**<br>
Les demandes de découverte pour identifier les récepteurs Miracast peuvent uniquement se produire par le biais de la carte Wi-Fi. Une fois les récepteurs identifiés, Windows 10 peut essayer de se connecter au réseau.
