---
title: Bonne pratique pour les paramètres d’alimentation des appareils Surface
description: Cette rubrique décrit les recommandations en matière de meilleures pratiques pour maintenir des paramètres d’alimentation optimaux et explique comment la surface simplifie l’expérience de gestion de l’alimentation. Cet article s’applique à tous les appareils surface actuellement pris en charge, y compris surface Pro 7, surface Pro X et surface Laptop 3.
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
ms.date: 10/28/2019
ms.openlocfilehash: 73a74dc05a5a6929fa6360e04aac5d342b9c06a8
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832513"
---
# Bonne pratique pour les paramètres d’alimentation des appareils Surface

Les appareils surface permettent de tirer parti des dernières améliorations apportées à la consommation d’énergie des appareils mobiles afin d’offrir une expérience rationalisée optimisée pour les charges de travail. En fonction de ce que vous faites, surface détermine de manière dynamique le fonctionnement de l’alimentation des composants matériels individuels, en réappliquant momentanément les composants système pour gérer les tâches en arrière-plan (par exemple, courrier électronique entrant ou trafic réseau) avant de revenir à un État faible de faible consommation (S0ix).

## Résumé des recommandations destinées aux administrateurs informatiques

Pour garantir que les appareils surface au sein de votre organisation bénéficient pleinement des fonctionnalités d’optimisation de la puissance de surface:

-  Installez les pilotes et le microprogramme les plus récents à partir de Windows Update ou du pilote surface et du MSI. Le plan de gestion de l’alimentation (c’est-à-dire le profil d’alimentation) est créé par défaut et les paramètres d’alimentation sont optimaux.  Pour plus d’informations, reportez-vous à [gérer et déployer des mises à jour de microprogramme et de pilotes de surface](manage-surface-driver-and-firmware-updates.md).
- Évitez de créer des profils d’alimentation personnalisés ou d’ajuster les paramètres d’alimentation avancés invisibles dans l’interface utilisateur par défaut (alimentation du**système**  >  **& veille**).
- Si vous devez gérer le profil d’alimentation des appareils sur votre réseau (par exemple, dans les organisations hautement gérées), utilisez l’outil de commande powercfg pour exporter le plan de gestion de l’alimentation à partir de l’image de fabrique de l’appareil surface, puis importez-le dans le package de mise en service de vos appareils de surface. 

    >[!NOTE]
    >Vous pouvez uniquement exporter un plan de gestion de l’alimentation sur le même type d’appareil surface.  Par exemple, vous ne pouvez pas exporter un plan d’alimentation à partir de surface Laptop et l’importer dans surface Pro.  Pour plus d’informations, voir [configurer les paramètres d’alimentation](https://docs.microsoft.com/windows-hardware/customize/power-settings/configure-power-settings).

- Excluez les appareils surface de tous les paramètres de stratégie de gestion de l’alimentation existants. 

## Arrière-plan

Le mode de mise en œuvre de la surface gestion de l’alimentation diffère considérablement de l’ancienne norme du système d’exploitation, qui réduit progressivement et désactive la puissance via une série d’États en veille. par exemple, le passage en revue de S1, S2, S3, etc.

Au lieu de cela, surface est associée à un profil d’alimentation personnalisé qui remplace les fonctionnalités de veille et de consommation d’énergie héritées par des fonctionnalités de mise en réserve modernes et un ajustement affiné dynamique. Ce profil d’alimentation personnalisé est implémenté par le biais du pilote de surface Hub de surface et du module d’agrégation de systèmes (SAM). La puce SAM est le propriétaire de la politique de l’appareil surface, qui utilise des algorithmes pour calculer la puissance requise. Il fonctionne conjointement avec Windows Power Manager pour allouer ou limiter uniquement le volume exact d’alimentation nécessaire aux composants matériels pour fonctionner. Cet article s’applique à tous les appareils surface actuellement pris en charge, y compris surface Pro 7, surface Pro X et surface Laptop 3.

## Utilisation du profil d’alimentation personnalisé en surface

Si vous accédez à l’option Power Options sur un appareil surface, vous verrez qu’il existe un seul plan d’alimentation disponible. Il s’agit du profil d’alimentation personnalisé. Et si vous accédez aux paramètres d’alimentation avancés, vous verrez un sous-ensemble plus petit d’options de puissance par rapport à un PC générique exécutant Windows 10. Contrairement aux appareils génériques, surface dispose de microprogrammes et de composants personnalisés pour gérer ces options d’alimentation.


## Veille moderne

Le profil d’alimentation personnalisé incorporé à l’aide d’un algorithme de surface permet une connectivité moderne en veille pour la surface en assurant un état de faible consommation d’énergie dans les smartphones. S0ix, également connu sous le nom de l’état de la plateforme d’inactivité d’exécution plus profonde (DRIPS), est le mode d’alimentation par défaut pour les appareils surface. Le mode veille moderne possède deux modes:

- **Veille connectée.** Le mode par défaut pour la remise à la minute de messages électroniques, de messages et de données synchronisées dans le Cloud, la fonction de veille connectée assure le Wi-Fi et maintient la connectivité réseau.

- **Veille déconnectée.** Le mode facultatif pour prolonger l’autonomie de la batterie, la veille déconnectée offre la même fonctionnalité d’instantané et l’économie d’énergie en désactivant le Wi-Fi, la Bluetooth et la connectivité réseau liée.

Pour en savoir plus sur la mise en veille moderne, consultez le [Centre de développement matériel Microsoft](https://docs.microsoft.com/windows-hardware/design/device-experiences/modern-standby-wake-sources).

## Comment surface rationalise l’utilisation de la gestion de l’alimentation 

Surface intègre les fonctionnalités suivantes conçues pour aider les utilisateurs à optimiser l’interface de gestion de l’alimentation:

- [Plan d’alimentation singulier](#singular-power-plan)

- [Interface utilisateur simplifiée de paramètres d’alimentation](#simplified-power-settings-user-interface)

- [Windows Power performance](#windows-performance-power-slider)

### Plan d’alimentation singulier

Surface est conçue pour une interface de gestion de l’alimentation rationalisée qui évite d’avoir à créer des plans d’alimentation personnalisés ou à configurer manuellement des paramètres d’alimentation. Microsoft rationalise l’utilisation des utilisateurs en effectuant un seul plan de gestion de l’alimentation (équilibré) qui remplace les différents plans d’alimentation des builds Windows standard.

### Interface utilisateur simplifiée de paramètres d’alimentation

Surface fournit une interface utilisateur simplifiée associée aux recommandations en matière de paramètres d’alimentation. En règle générale, il est recommandé de régler uniquement les paramètres visibles dans l’interface utilisateur par défaut et d’éviter de configurer les paramètres d’alimentation avancés ou les paramètres de stratégie de groupe. L’utilisation de l’écran par défaut et des délais d’attente dans le cadre d’une prévention maximale est la méthode la plus efficace pour les utilisateurs de conserver une autonomie de batterie étendue.

![Figure1. Paramètres de mise en veille de l’alimentation & simplifiée](images/powerintrofig1.png)

Figure1. Paramètres d’alimentation et de veille simplifiés

### Windows Power performance

Les appareils surface exécutant Windows 10 Build 1709 et les versions ultérieures incluent un curseur d’alimentation qui vous permet de hiérarchiser l’autonomie de la batterie quand cela est nécessaire ou de privilégier les performances si vous le souhaitez. Vous pouvez accéder au curseur alimentation à partir de la barre des tâches en cliquant sur l’icône de batterie. Faites glisser vers la gauche pour prolonger l’autonomie de la batterie (mode économiseur de batterie) ou glissez vers la droite pour des performances plus rapides.

![Figure2. Curseur d’alimentation](images/powerintrofig2a.png)

Figure2. Curseur d’alimentation

Le curseur d’alimentation permet de disposer de quatre États comme décrit dans le tableau suivant:

| Mode curseur| Description |
|---|---|
| Économiseur de batterie| Permet d’économiser l’énergie et de prolonger l’autonomie de la batterie lorsque le système est déconnecté d’une source d’alimentation. Lorsque l’économiseur de batterie est activé, certaines fonctionnalités Windows sont désactivées, limitées ou se comportent différemment. La luminosité de l’écran est également réduite. L’économiseur de batterie est uniquement disponible en cas d’utilisation de la batterie. Pour en savoir plus, voir [économiseur de batterie](https://docs.microsoft.com/windows-hardware/design/component-guidelines/battery-saver).|
| Nos recommandations | Le cycle de vie de la batterie est supérieur à celui des paramètres par défaut dans les versions antérieures de Windows. |
| Meilleures performances | Préfère sensiblement les performances de l’autonomie de la batterie, en vous servant du mode curseur par défaut. |
| Meilleures performances | Privilégie les performances par rapport à la puissance des charges de travail qui nécessitent des performances et une réactivité maximales, quelle que soit la consommation d’énergie de la batterie.|

Le mode de glissement d’alimentation contrôle directement les composants matériels spécifiques indiqués dans le tableau suivant.

| Composant | Fonctionnalité de curseur |
|---|---|
| Le changement de vitesse d’Intel (registres de l’énergie du processeur) et les conseils relatifs aux préférences de performance énergétique. | Sélectionne la meilleure fréquence opératoire et la même tension pour optimiser les performances et la puissance. Les préférences de performance énergétique (PERFEPP) constituent une astuce globale d’efficacité énergétique pour le processeur. |
| Débit du ventilateur (RPM)| Le cas échéant, ajuste les conditions en cas de modification des conditions comme le maintien du ventilateur silencieuse dans le mode d’économiseur de batterie.|
| Limites d’alimentation des packages de processeur (PL1/PL2).| Nécessite que le processeur gère son choix de fréquence pour s’adapter à une moyenne de puissance moyenne pour les charges de travail de l’état stabilisé (PL1) et de Turbo (PL2).|
| Limites de fréquence de microprocesseur (cauns des limitations d’IA). | Ajuste les performances du processeur et du graphique pour permettre à des cœurs de processeur de fonctionner plus rapidement ou plus lentement que la fréquence de fonctionnement nominale.                                                |

>[!NOTE]
>Le curseur alimentation est entièrement indépendant des paramètres d’alimentation du système d’exploitation, qu’il soit configuré à partir du panneau de configuration ou des options d’alimentation, de la stratégie de groupe ou des méthodes associées.

Pour en savoir plus, voir:

-   [Personnaliser le curseur d’alimentation des performances de Windows](https://docs.microsoft.com/windows-hardware/customize/desktop/customize-power-slider)

-   [Économiseur de batterie.](https://docs.microsoft.com/windows-hardware/design/component-guidelines/battery-saver)

## Meilleures pratiques pour une autonomie de batterie étendue


| Meilleure pratique | Allez à | Étapes suivantes |
|---|---|---|                                                                                                                                    
| Vérifiez que votre périphérique surface est à jour| WindowsUpdate | Dans la zone de recherche de la barre des tâches, tapez **Windows Update** et sélectionnez **Rechercher les mises à jour**. |
| Choisissez le paramètre d’alimentation le plus approprié pour ce que vous faites | Curseur d’alimentation | Dans la barre des tâches, sélectionnez l’icône de batterie, puis sélectionnez **meilleures performances**, **meilleure autonomie**de la batterie ou entre les deux.|
| Économiser la batterie lorsque celle-ci est faible | Économiseur de batterie | Dans la barre des tâches, sélectionnez l’icône de batterie, puis cliquez sur paramètres de la **batterie**. Sélectionnez **activer automatiquement l’économiseur de batterie si ma batterie** est située en dessous, puis déplacez le curseur vers la droite pour prolonger l’autonomie de la batterie. |
| Configurer une luminosité optimale de l’écran | Économiseur de batterie | Dans la barre des tâches, sélectionnez l’icône de batterie, puis cliquez sur paramètres de la **batterie**et sélectionnez **diminuer la luminosité de l’écran pendant l’économiseur de batterie**. |
| Économisez l’énergie dès que vous n’êtes pas connecté | Économiseur de batterie| Sélectionnez **activer le statut de l’économiseur de batterie jusqu’au prochain prélèvement**.|
| Identifiez les problèmes liés à vos paramètres d’alimentation. | Utilitaire de dépannage de l’alimentation | Dans la barre des tâches, recherchez résoudre les problèmes, sélectionnez **résolution**des problèmes, puis **alimentation** et suivez les instructions.|
| Vérifier l’utilisation de l’application | Vos applications | Fermez les applications.|
| Vérifiez que le cordon d’alimentation est endommagé.| Votre cordon d’alimentation | Remplacez le cordon d’alimentation s’il est usé ou endommagé.|

## En savoir plus 

- [Veille moderne](https://docs.microsoft.com/windows-hardware/design/device-experiences/modern-standby-wake-sources)

<!-- -->

- [Personnaliser le curseur d’alimentation des performances de Windows](https://docs.microsoft.com/windows-hardware/customize/desktop/customize-power-slider)

- [Économiseur de batterie](https://docs.microsoft.com/windows-hardware/design/component-guidelines/battery-saver)
- [Gérer et déployer les mises à jour du microprogramme et des pilotes Surface](manage-surface-driver-and-firmware-updates.md)
