---
title: Vue d’ensemble de la sécurité Surface Hub
description: Cette page décrit la conception de Défense en profondeur de Surface Hub, ainsi que les améliorations apportées à la sécurité dans Surface Hub 2S, les protections de sécurité sans fil et les fonctionnalités associées.
keywords: séparer les valeurs par des virgules
ms.prod: surface-hub
ms.sitesec: library
author: coveminer
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 01/26/2021
ms.localizationpriority: High
ms.openlocfilehash: 446166618161fc54a77bab94b2d61ad85359a082
ms.sourcegitcommit: 25b8d880c6438f94b008f47b4fecc3aa4c473e85
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/28/2021
ms.locfileid: "11304847"
---
# Vue d’ensemble de la sécurité Surface Hub

Le Surface Hub offre une expérience verrouillée comme une appliance avec un microprogramme de plateforme personnalisé exécutant le système d’exploitation Windows 10 Team. L’appareil qui en résulte se base sur la philosophie traditionnelle de kiosque sécurisé à «usage unique», «exécutez seulement ce dont vous avez besoin» et fournit une approche moderne. Conçu pour prendre en charge une expérience utilisateur de collaboration riche, Surface Hub est protégé contre les menaces de sécurité en perpétuelle évolution.

Conçu sur Windows 10, Surface Hub offre aux administrateurs informatiques une sécurité moderne à échelle de l’entreprise, leur permettant d’appliquer la protection des données avec BitLocker, le module de plateforme sécurisée 2,0 (TPM), ainsi que la sécurité dans le Cloud avec Windows Defender (également appelé Microsoft Defender).

## Sécurité renforcée

Les protocoles de sécurité sont démarrés dès que Surface Hub est activé. Au niveau du microprogramme, Surface Hub charge uniquement le système d’exploitation et ses composants en réponse à plusieurs vérifications de sécurité. Surface Hub utilise une stratégie de défense en profondeur impliquant la superposition de sous-composants défensifs indépendants afin de protéger le système dans son ensemble en cas de défaillance partielle. Cette pratique s’avère particulièrement efficace pour limiter les possibles attaques unilatérales et faiblesses liées aux sous-composants.

L’interface UEFI (Unified Extensible Firmware Interface) moderne est configurée de manière statique et sécurisée par Microsoft pour démarrer uniquement un système d’exploitation Windows 10 Team authentifié à partir du stockage interne.  La signature de chaque ligne de code exécutée sur Surface Hub est préalablement vérifiée. Seules les applications signées par Microsoft, dans le cadre du système d’exploitation ou installées via le Microsoft Store, peuvent s’exécuter sur Surface Hub. Tout code ou application ne répondant pas à ces exigences est bloqué.

Les systèmes de sécurité Surface Hub incluent ce qui suit:

- **Défenses au démarrage.** Chargent uniquement les composants approuvés du système d’exploitation Surface Hub.
- **Défenses du système d'exploitation.** Protègent contre l’exécution d’un logiciel ou d’un code imprévu ou malveillant.
- **Défenses de l’interface utilisateur.** Fournissent aux utilisateurs finaux une interface utilisateur sécurisée, empêchant ainsi l’accès à des activités potentiellement dangereuses telles que l’exécution de fichiers exécutables à partir de la ligne de commande.

### Défenses au démarrage

Le SoC dispose d’un processeur de sécurité séparé de tous les autres cœurs. Lors du premier démarrage Surface Hub, seul le processeur de sécurité démarre avant tout autre chargement.

![Phases de démarrage Surface Hub montrant les dispositifs de protection du processeur de sécurité](images/hub-sec-1.png)

#### Démarrage sécurisé

Le démarrage sécurisé permet de vérifier que les composants du processus de démarrage, pilotes et système d’exploitation compris, sont validés par rapport à une base de données de signatures valides et connues. Sur Surface Hub, une signature spécifique à la plateforme doit être validée préalablement au chargement du système d’exploitation Windows Team autorisé. Cela permet d’éviter les attaques émanant d’un système cloné ou modifié exécutant un code malveillant masqué dans ce qui s’apparente à une expérience utilisateur normale.  Pour plus d'informations, consultez [Vue d’ensemble du démarrage sécurisé](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot).

### Défenses du système d'exploitation

Une fois le système d’exploitation vérifié comme émanant de Microsoft et le processus de démarrage Surface Hub terminé, l’appareil examine le code exécutable. En matière de sécurisation du système d’exploitation, notre approche consiste à identifier la signature du code de tous les fichiers exécutables et en autorisant uniquement ceux qui transmettent nos restrictions dans le runtime. Cette méthode de signature de code permet au système d’exploitation d’en vérifier l’auteur et de s’assurer que le code n’a pas été modifié avant d’être exécuté sur l’appareil.

Surface Hub utilise une fonctionnalité de signature de code connue sous l’abréviation d’UMCI (User Mode Code Integrity - Intégrité du code du mode utilisateur) dans le contrôle d’application Windows (anciennement Device Guard). Les paramètres de stratégie sont configurés de manière à autoriser uniquement les applications répondant à l’une des exigences suivantes:

- Applications de plateforme Windows universelle (Microsoft Store) [officiellement certifiées](https://docs.microsoft.com/windows/uwp/publish/the-app-certification-process).
- Applications signées avec l’autorité de certification racine de production Microsoft unique, que seuls les employés Microsoft dotés d’un accès autorisé à ces certificats peuvent signer.
- Applications signées avec l’autorité de certification racine de production Surface Hub unique.

Le fichier de configuration est signé à l’aide de l’autorité de certification racine de production conçue pour empêcher la suppression ou la modification de restrictions par un tiers. À ce stade, les autres fichiers exécutables sont bloqués au niveau du système d’exploitation et ne peuvent accéder à la puissance de traitement. Cette réduction de la surface d'attaque offre les protections suivantes:

- Aucun mode de document hérité
- Aucun moteur de script hérité
- Aucun langage VML (Vector Markup Language)
- Aucun objet d’assistance du navigateur
- Aucun contrôle ActiveX

Outre le blocage du code non signé ou incorrectement signé via UMCI, Surface Hub utilise le contrôle d’application Windows pour bloquer les composants Windows, tels que l’invite de commandes, PowerShell et le Gestionnaire des tâches. Ces dispositifs de protection reflètent une fonctionnalité de conception essentielle Surface Hub en tant qu’appareil informatique sécurisé. Pour plus d'informations, reportez-vous aux éléments suivants:

- [Vue d’ensemble du contrôle des applications](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control)

- [Contrôle d’application Windows Defender et protection basée sur la virtualisation d’intégrité du code](https://docs.microsoft.com/windows/security/threat-protection/device-guard/introduction-to-device-guard-virtualization-based-security-and-windows-defender-application-control)

### Défenses de l’interface utilisateur

Alors que les défenses au démarrage et les protections de verrouillage du système d'exploitation offrent une sécurité fondamentale, l'interface utilisateur fournit une couche supplémentaire conçue pour limiter encore davantage les risques. Pour éviter que du code malveillant n’atteigne l’appareil via les pilotes, Surface Hub ne télécharge pas les pilotes avancés des périphériques plug-and-play (PnP). Les appareils utilisant des pilotes de base, tels que les disques mémoire flash USB ou périphériques Surface Hub certifiés (haut-parleurs, microphones, caméras), fonctionnent comme prévu, mais pas les systèmes avancés tels que les imprimantes.

Les défenses de l’interface utilisateur simplifient également l’interface utilisateur, et empêchent l’exécution d’un logiciel ou d’un code malveillant. Les éléments de l’interface utilisateur Surface Hub suivants renforcent la sécurité de base fournie par le code de signature:

- **Explorateur de fichiers.** Surface Hub est doté d’un Explorateur de fichiers personnalisé qui permet d’accéder rapidement aux dossiers Musique, Vidéos, Documents, Images et Téléchargements, sans exposer les utilisateurs au système ou aux Program Files. Les autres emplacements du disque dur local ne sont pas disponibles via l’Explorateur de fichiers. En outre, de nombreux types de fichiers, tels que les fichiers .exe et .msi, ne peuvent pas être exécutés pour offrir une couche de sécurité supplémentaire contre les programmes potentiellement malveillants.

- **Démarrer et Toutes les applications.** Les composants Démarrer et Toutes les applications de Surface Hub n’exposent pas l’accès à l’invite de commandes, à PowerShell ou à d’autres composants Windows bloqués via le contrôle d’application. De plus, les fonctionnalités d’exécution de Windows généralement accessibles sur PC à partir de la zone de recherche sont désactivées pour Surface Hub.

## Améliorations de la sécurité sur Surface Hub 2S

Bien que les Surface Hub et Surface Hub 2S exécutent les mêmes logiciels de système d’exploitation, certaines fonctionnalités propres à Surface Hub 2S fournissent des fonctionnalités de gestion et de sécurité supplémentaires qui permettent aux administrateurs informatiques d’effectuer les tâches suivantes:

- Gérer les paramètres UEFI avec SEMM
- Restaurer Hub avec une clé USB de démarrage
- Renforcer le compte d’appareil avec la rotation du mot de passe

### Gérer les paramètres UEFI avec SEMM

UEFI est une interface entre les éléments de plateforme matérielle sous-jacente et le système d’exploitation. Sur Surface Hub, une implémentation UEFI personnalisée permet un contrôle granulaire de ces paramètres et empêche toute entité non Microsoft de modifier les paramètres UEFI de l’appareil, ou de démarrer sur un lecteur amovible pour modifier le système d’exploitation.

À un niveau élevé, lors du processus de mise en service en usine, les paramètres UEFI Surface Hub sont préconfiguré pour activer le démarrage sécurisé, et configurés pour démarrer uniquement à partir du disque SSD interne, avec accès aux menus UEFI verrouillés et raccourcis supprimés. Cela scelle l’accès à UEFI et permet à l’appareil de démarrer uniquement dans le système d’exploitation Windows Team installé sur Surface Hub.

Moyennant une gestion via Microsoft Surface Enterprise Management Mode (SEMM), les administrateurs informatiques peuvent déployer des paramètres UEFI sur les appareils Hub au sein d’une organisation. Cela comprend notamment la possibilité d’activer ou de désactiver les composants matériels intégrés, de protéger les paramètres UEFI contre toute modification par des utilisateurs non autorisés et d’ajuster les paramètres de démarrage.

![Paramètres UEFI SurfaceHub](images/hub-sec-2.png)

Les administrateurs peuvent implémenter des appareils SEMM et des appareils Surface Hub 2S inscrits à l’aide du [Configurateur UEFI Microsoft Surface](https://www.microsoft.com/download/details.aspx?id=46703). Pour plus d’informations, consultez [Sécuriser et gérer les SurfaceHub2S avec SEMM et UEFI](https://docs.microsoft.com/surface-hub/surface-hub-2s-secure-with-uefi-semm).
Sécurisé à l’aide d’un certificat visant à protéger la configuration contre toute falsification ou suppression non autorisée, SEMM permet de gérer les composants suivants:

- Réseau local câblé
- Appareil photo
- Bluetooth
- Wi-Fi
- Capteur d’occupation
- IPv6 pour démarrage PXE
- Autre démarrage
- Verrou d’ordre de démarrage
- Démarrage USB
- Interface Front Page UEFI
    - Périphériques
    - Démarrage
    - Date/Heure

    
### Restaurer Hub avec une clé USB de démarrage

Surface Hub 2S permet aux administrateurs de restaurer les paramètres d’usine de l’appareil à l’aide d’une image de récupération en moins de 20minutes. En règle générale, vous optez pour cette solution lorsque votre Surface Hub ne fonctionne plus. Cette restauration est également utile si vous avez perdu la clé BitLocker ou ne disposez plus des informations d’identification d’administrateur pour l’application Paramètres.

### Renforcer le compte d’appareil avec la rotation du mot de passe

Surface Hub utilise un compte d’appareil, également appelé «compte de salle» pour s’authentifier auprès d’Exchange, de Microsoft Teams et d’autres services. Lorsque vous activez la rotation du mot de passe, Hub 2S génère automatiquement un nouveau mot de passe tous les 7jours, et celui-ci est composé de 15 à 32caractères avec une combinaison de lettres majuscules et minuscules, de chiffres et de caractères spéciaux. Dans la mesure où personne ne connaît le mot de passe, la rotation du mot de passe des comptes d’appareils atténue efficacement les risques ayant trait aux erreurs humaines et aux possibles attaques liées à la sécurité d’ingénierie sociale.

## Sécurité Windows10 Entreprise

Outre les configurations et fonctionnalités spécifiques à Surface Hub dont il est question dans ce document, Surface Hub utilise également les fonctionnalités de sécurité standard de Windows10. Par exemple:

- **BitLocker**. Le SSD de Surface Hub est équipé de BitLocker pour protéger les données sur l’appareil. Sa configuration respecte les normes du secteur. Pour plus d’informations, consultez [Vue d’ensemble de BitLocker](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot).
- **Windows Defender.** Le moteur anti-programme malveillant de Windows Defender s’exécute en continu sur Surface Hub afin de corriger automatiquement les menaces détectées. Le moteur Windows Defender reçoit automatiquement les mises à jour et peut être géré à l’aide d’outils de gestion à distance destinés aux administrateurs informatiques. Le moteur Windows Defender illustre parfaitement notre approche en matière de défense en profondeur: si un programme malveillant parvient à contourner notre solution de sécurité basé sur la signature de code, il est détecté ici. Pour plus d’informations, consultez [Contrôle d’application Windows Defender et protection basée sur la virtualisation d’intégrité du code](https://docs.microsoft.com/windows/security/threat-protection/device-guard/introduction-to-device-guard-virtualization-based-security-and-windows-defender-application-control).
- **Pilotes plug-and-play.** Pour éviter que du code malveillant n’atteigne l’appareil via les pilotes, Surface Hub ne télécharge pas les pilotes avancés des périphériques PnP. Ainsi, les appareils qui utilisent des pilotes de base tels que des lecteurs flash USB peuvent fonctionner comme prévu tout en bloquant les systèmes plus avancés tels que les imprimantes.
- **Module de plateforme sécurisée2.0.** Surface Hub est doté d’un module de plateforme sécurisée (dTPM - discrete Trusted Platform Module) afin de générer et stocker les clés cryptographiques et les hachages. Le module dTPM protège les clés utilisées pour la vérification des phases de démarrage, la clé principale BitLocker, la clé de connexion sans mot de passe et bien plus encore. Le module dTPM est conforme à la certification [FIPS 140-2 de niveau2](https://docs.microsoft.com/windows/security/threat-protection/fips-140-validation), norme de sécurité informatique des États-Unis, de même qu’à la certification [Critères communs](https://docs.microsoft.com/windows/security/threat-protection/windows-platform-common-criteria) utilisée dans le monde entier.

## Sécurité sans fil pour Surface Hub

Surface Hub utilise la technologie de Wi-Fi Direct / Miracast et des normes Wi-Fi Protected Access (WPA2) et Wireless Protected Setup (WPS) 802.11 associées. Étant donné que l'appareil prend uniquement en charge WPS (contrairement à la clé prépartagée WPA2 (PSK) ou WPA2 Entreprise), les problèmes traditionnellement liés au chiffrement 802.11 sont simplifiés de par sa conception.

Miracast fait partie de la norme Wi-Fi Display, elle-même prise en charge par le protocole Wi-Fi Direct. Ces normes sont prises en charge sur les appareils mobiles modernes pour le partage d’écran et la collaboration.

Wi-Fi Direct ou Wi-Fi «pair à pair» (P2P) est une norme publiée par Wi-Fi Alliance pour les réseaux «Ad Hoc». Elle permet aux appareils compatibles de communiquer directement et de créer des groupes de réseaux sans l'aide d’un point d’accès Wi-Fi traditionnel ou d'une connexion Internet.

La sécurité de Wi-Fi Direct est assurée par WPA2 à l’aide de la norme WPS. Les appareils peuvent être authentifiés à l’aide d’un code PIN numérique (WPS-PIN), d’un bouton physique ou virtuel (WPS-PBC) ou d’un message hors-bande utilisant la communication en champ proche. Surface Hub prend en charge le bouton de commande par défaut, de même que les méthodes PIN. Pour plus d’informations, consultez [Comment Surface Hub résout les problèmes de sécurité de Wi-Fi Direct](https://docs.microsoft.com/surface-hub/surface-hub-wifi-direct).

## En savoir plus

- [Vue d’ensemble du démarrage sécurisé](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot)

- [Vue d’ensemble de BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview)

- [Vue d’ensemble du contrôle des applications](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control)

- [Sécuriser et gérer les SurfaceHub2S avec SEMM et UEFI](https://docs.microsoft.com/surface-hub/surface-hub-2s-secure-with-uefi-semm)

- [Comment Surface Hub résout les problèmes de sécurité de Wi-Fi Direct](https://docs.microsoft.com/surface-hub/surface-hub-wifi-direct)

- [Contrôle d’application Windows Defender et protection basée sur la virtualisation d’intégrité du code](https://docs.microsoft.com/windows/security/threat-protection/device-guard/introduction-to-device-guard-virtualization-based-security-and-windows-defender-application-control)

- [Outils Surface pour l'informatique](https://www.microsoft.com/download/details.aspx?id=46703)

- [FIPS 140-2 de niveau2](https://docs.microsoft.com/windows/security/threat-protection/fips-140-validation)

- [Certifications sur critères communs](https://docs.microsoft.com/windows/security/threat-protection/windows-platform-common-criteria)
