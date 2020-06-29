---
title: AdaptateursEthernet et déploiement d’appareilsSurface
description: Cet article fournit des instructions et des réponses pour vous aider à effectuer un déploiement de réseau sur des appareilsSurface.
ms.assetid: 5273C59E-6039-4E50-96B3-426BB38A64C0
ms.reviewer: ''
manager: laurawi
keywords: ethernet, déployer, composant qui peut être supprimé, réseau, connectivité, démarrage, microprogramme, appareil, adaptateur, démarragePXE, USB
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.audience: itpro
ms.openlocfilehash: 4b0cfd9cadab33d82ae3d0acaa83e007229c6fb8
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832549"
---
# AdaptateursEthernet et déploiement d’appareilsSurface


Cet article fournit des recommandations et des réponses pour vous aider à effectuer un déploiement réseau sur des appareils surface, dont surface Pro 3 et version ultérieure.

Un déploiement de réseau sur des appareilsSurface peut engendrer des défis uniques pour les administrateurs système. Comme aucun adaptateur Ethernet câblé natif n’est fourni, les administrateurs doivent assurer la connectivité via un adaptateurEthernet amovible.

## Sélectionner une carteEthernet pour des appareilsSurface


Avant de déterminer comment démarrer l’appareil dans l’environnement de déploiement, ou le mode de reconnaissance des appareils par une solution de déploiement, vous devez utiliser un adaptateur réseau câblé.

Lors de la sélection d’un adaptateurEthernet, la première question à se poser est de savoir comment il doit démarrer l’appareilSurface à partir du réseau. Si vous utilisez la version préliminaire des clients avec les services de déploiement Windows ou si vous utilisez Microsoft Endpoint Configuration Manager, vous pouvez également envisager de dédier les cartes Ethernet amovibles à un appareil surface spécifique ou partagées entre plusieurs appareils. Pour plus d’informations sur les conflits potentiels liés aux cartes partagées, voir [gérer les adresses Mac avec des cartes Ethernet amovibles](#manage-mac-addresses) plus loin dans cet article.

La fonction de démarrage à partir du réseau (démarragePXE) est uniquement prise en charge lorsque vous utilisez un adaptateurEthernet ou une station d’accueil de Microsoft. Pour effectuer un démarrage à partir du réseau, le circuit microprogrammé de l’adaptateurEthernet ou de la station d’accueil doit être détecté et configuré en tant que périphérique de démarrage dans le microprogramme de l’appareilSurface. Les adaptateursEthernet Microsoft, tels que l’adaptateur Ethernet Surface et la [station d’accueilSurface](https://www.microsoft.com/surface/accessories/surface-dock), utilisent un circuit microprogrammé compatible avec le microprogramme de l’appareilSurface.

Les appareilsEthernet suivants sont pris en charge pour un démarrage réseau avec des appareilsSurface:

-   Surface USB-C vers Ethernet et carte 3,0 USB

-   Carte Ethernet 3,0 vers bus USB surface

-   Station d’accueilSurface

-   Station d’accueilSurface3

-   Station d’accueilSurfacePro3

-   Station d’accueil pour SurfacePro et SurfacePro2

Les adaptateursEthernet tiers sont également pris en charge pour le déploiement réseau, même s’ils ne prennent pas en charge le démarragePXE. Pour pouvoir utiliser un adaptateurEthernet tiers, vous devez charger les pilotes dans l’image de démarrage du déploiement, puis lancer cette image depuis un appareil de stockage distinct, par exemple une cléUSB.

## Démarrer des appareilsSurface à partir du réseau

Pour pouvoir le démarrer depuis le réseau ou une cléUSB connectée, vous devez indiquer à l’appareilSurface de démarrer depuis un périphérique de démarrage secondaire. Vous pouvez modifier l’ordre de démarrage dans le microprogramme système afin de classer les périphériques de démarrageUSB par ordre de priorité, ou lui indiquer qu’il doit démarrer depuis un périphérique de démarrage secondaire lors du processus de lancement.

Pour démarrer un appareilSurface depuis un autre périphérique de démarrage alternatif, procédez comme suit:

1.  Assurez-vous que l’appareilSurface est hors tension.
2.  Maintenez le bouton **Baisser le volume** enfoncé.
3.  Appuyez, puis relâchez le bouton **Marche/Arrêt**.
4.  Lorsque le système démarre à partir de la cléUSB ou de l’adaptateurEthernet, relâchez le bouton **Baisser le volume**.

>[!NOTE]
>En plus de l'adaptateurEthernet, vous devez connecter un clavier à l'appareilSurface pour accéder à l'environnement de préinstallation et parcourir l'Assistant de déploiement.

 
Pour Windows10, version1511 et ultérieures, y compris le Kit de déploiement et d’évaluation Windows pour Windows10, version1511, les pilotes pour les cartes Ethernet Microsoft Surface sont présentes par défaut. Si vous vous servez d’une solution de déploiement utilisant l’environnement de préinstallation Windows (WinPE), tels que Microsoft Deployment Toolkit et démarrant à partir du réseau avec PXE, assurez-vous que votre solution de déploiement utilise la dernière version de Windows ADK.

## <a href="" id="manage-mac-addresses"></a>Gérer les adressesMAC avec des adaptateursEthernet amovibles

Les administrateurs effectuant un déploiement de Windows sur le réseau doivent également répondre à la question suivante: comment identifier les différents ordinateurs en cas d’utilisation du même adaptateur Ethernet pour le déploiement de ces derniers? Les technologies de déploiement utilisent souvent l’adresseMAC (Media Access Control) associée à chaque adaptateurEthernet en tant qu’identificateur. Toutefois, lorsque vous utilisez le même adaptateurEthernet pour effectuer le déploiement sur plusieurs ordinateurs, vous ne pouvez pas utiliser une technologie de déploiement qui inspecte les adressesMAC, car il n’existe aucun moyen de différencier l’adresseMAC de l’adaptateur amovible lorsqu’il est utilisé sur des ordinateurs différents.

La solution la plus simple pour éviter les conflits d’adressesMAC consiste à fournir un adaptateurEthernet amovible dédié pour chaque appareilSurface. Cela peut être pertinent dans de nombreux scénarios, lorsque l’adaptateurEthernet ou la fonctionnalité supplémentaire de la station d’accueil doivent être utilisés régulièrement. Cependant, tous les scénarios possibles ne requièrent pas la connectivité supplémentaire d’une station d’accueil ou la prise en charge de réseaux câblés.

Pour éviter les conflits en cas de partage d’adaptateurs, vous pouvez également recourir à [MicrosoftDeploymentToolkit (MDT)](https://technet.microsoft.com/windows/dn475741) pour le déploiement sur des appareilsSurface. Le logicielMDT n’utilise pas l’adresseMAC pour identifier les ordinateurs individuels; par conséquent, il n’est pas soumis à cette limitation. Toutefois, il utilise les Services de déploiementWindows pour assurer la fonctionnalité de démarragePXE; de ce fait, il est soumis à certaines limitations concernant les clients de préinstallation. Nous en parlerons un peu plus tard dans cette section.

Lorsque vous utilisez un adaptateur partagé pour le déploiement, la solution, pour les technologies de déploiement affectées, consiste à recourir à un autre moyen pour identifier les systèmes uniques. Pour ConfigurationManager et les Services de déploiementWindows (tous deux potentiellement affectés par ce problème), la solution consiste à utiliser l’UUID du système, qui est intégré dans le microprogramme de l’ordinateur par le fabricant de ce dernier. Pour les appareilsSurface, vous pouvez voir cette entrée dans le microprogramme de l’ordinateur, sous **Informations sur le périphérique**.

Pour accéder au microprogramme d’un appareilSurface, procédez comme suit :

1.  Assurez-vous que l’appareilSurface est hors tension.
2.  Maintenez le bouton **Augmenter le volume** enfoncé.
3.  Appuyez, puis relâchez le bouton **Marche/Arrêt**.
4.  Lorsque l’appareil démarre, relâchez le bouton **Augmenter le volume**.

Lors d’un déploiement avec les Services de déploiementWindows, l’adresseMAC est uniquement utilisée pour identifier un ordinateur lorsque le serveur de déploiement est configuré pour répondre uniquement aux clients connus et préinstallés. Lors de la préparation d’un client, un administrateur crée un compte d’ordinateur dans ActiveDirectory et définit cet ordinateur en fonction de l’adresseMAC ou de l’UUID du système. Pour éviter les conflits d’identité causés par le partage d’adaptateursEthernet, vous devez utiliser [l’UUID du système pour définir les clients préinstallés](https://technet.microsoft.com/library/cc742034). Par ailleurs, vous pouvez configurer les Services de déploiementWindows pour répondre aux clients inconnus qui ne nécessitent pas de définition en fonction de l’adresseMAC ou de l’UUID système. Pour cela, sélectionnez l’option **Répondre à tous les ordinateurs clients (connus et inconnus)** sur [l’onglet **Réponse PXE**](https://technet.microsoft.com/library/cc732360) dans **Propriétés des serveurs de déploiementWindows**.

Le risque de conflits avec les adaptateursEthernet partagés est nettement plus élevé dans ConfigurationManager. Les Services de déploiementWindows utilisent les adressesMAC pour définir des systèmes individuels lorsqu’ils sont configurés à cette fin, alors que ConfigurationManager les exploitent pour définir ces systèmes lorsqu’ils effectuent un déploiement vers des ordinateurs inconnus ou nouveaux. Cela peut entraîner des erreurs de configuration des appareils, voire l’incapacité de la fonctionnalité à déployer plusieurs systèmes avec un adaptateurEthernet partagé. Il existe plusieurs solutions possibles pour cette situation qui sont décrites en détail dans l' [article utilisation de la même carte Ethernet externe pour plusieurs OSD de SCCM](https://techcommunity.microsoft.com/t5/core-infrastructure-and-security/how-to-use-the-same-external-ethernet-adapter-for-multiple-sccm/ba-p/257374), un billet de blog sur le blog infrastructure et sécurité de base.

 

 





