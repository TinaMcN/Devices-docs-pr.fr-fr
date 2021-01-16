---
title: Bonne pratique pour les paramètres d’alimentation des appareils Surface
description: Cette rubrique fournit des recommandations pour maintenir des paramètres d’alimentation optimaux et explique comment Surface simplifie l’expérience de gestion de l’alimentation. Cet article s’applique à tous les appareils Surface actuellement pris en charge, notamment Surface Pro 7+, Surface Pro 7, Surface Pro X et Surface Laptop 3.
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
ms.date: 1/15/2021
ms.openlocfilehash: 54aff228e8a72d413fc53bd14fe15d8ad7b15ab0
ms.sourcegitcommit: 1053479c191fd10651d31a466fad1769fb0cd28b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/16/2021
ms.locfileid: "11271398"
---
# Bonne pratique pour les paramètres d’alimentation des appareils Surface

Les appareils Surface sont conçus pour tirer parti des dernières avancées en matière de consommation d’énergie des appareils mobiles afin d’offrir une expérience optimisée sur l’ensemble des charges de travail. En fonction de ce que vous faites, Surface affinera dynamiquement la façon dont l’alimentation circule vers les composants matériels individuels, réessant momentanément les composants système pour gérer les tâches en arrière-plan (par exemple, un courrier entrant ou le trafic réseau) avant de revenir à un état d’inactivité de faible puissance (S0ix).

## Résumé des recommandations pour les administrateurs informatiques

Pour vous assurer que les appareils Surface de votre organisation bénéficient pleinement des fonctionnalités d’optimisation de l’alimentation Surface :

-  Installez les pilotes et microprogrammes les plus récents à partir de Windows Update ou du pilote Surface et du microprogramme MSI. Cela crée le plan d’alimentation équilibrée (également appelé profil d’alimentation) par défaut et configure les paramètres d’alimentation optimaux.  Pour plus d’informations, voir Gérer et déployer les mises à jour des pilotes et [microprogrammes Surface.](manage-surface-driver-and-firmware-updates.md)
- Évitez de créer des profils d’alimentation personnalisés ou d’ajuster les paramètres d’alimentation avancés qui ne sont pas visibles dans l’interface utilisateur par défaut **(mise**en veille  >  **& système).**
- Si vous devez gérer le profil d’alimentation des appareils sur votre réseau (par exemple, dans les organisations hautement gérées), utilisez l’outil de commande powercfg pour exporter le plan d’alimentation à partir de l’image d’usine de l’appareil Surface, puis importez-le dans le package d’approvisionnement de vos appareils Surface. 

    >[!NOTE]
    >Vous pouvez uniquement exporter un plan d’alimentation sur le même type d’appareil Surface.  Par exemple, vous ne pouvez pas exporter un plan d’alimentation à partir du Surface Laptop et l’importer sur Surface Pro.  Pour plus d’informations, voir [Configurer les paramètres d’alimentation.](https://docs.microsoft.com/windows-hardware/customize/power-settings/configure-power-settings)

- Exclure les appareils Surface de tous les paramètres de stratégie de gestion de l’alimentation existants. 

## Arrière-plan

La façon dont Surface implémente la gestion de l’alimentation diffère considérablement de la norme de système d’exploitation antérieure qui réduit et éteint progressivement l’alimentation via une série d’états de veille ; par exemple, le cycle S1, S2, S3, etc.

Au lieu de cela, Surface est image avec un profil d’alimentation personnalisé qui remplace les fonctionnalités de veille et de consommation d’énergie héritées par des fonctionnalités de veille moderne et un ajustement dynamique. Ce profil d’alimentation personnalisé est implémenté via le pilote Surface Serial Hub et le module d’agrégation système (SAM). La puce SAM fonctionne en tant que propriétaire de stratégie d’alimentation de l’appareil Surface, à l’aide d’algorithmes pour calculer les besoins d’alimentation optimaux. Il fonctionne conjointement avec le Gestionnaire d’alimentation Windows pour allouer ou limiter uniquement la quantité exacte de puissance requise pour le fonctionnement des composants matériels. Cet article s’applique à tous les appareils Surface actuellement pris en charge, notamment Surface Pro 7+, Surface Laptop Go, Surface Pro 7, Surface Pro X et Surface Laptop 3.

## Utilisation du profil d’alimentation personnalisé dans Surface

Si vous vous rendez dans les options d’alimentation d’un appareil surface, vous verrez qu’un plan d’alimentation unique est disponible. Il s’agit du profil d’alimentation personnalisé. Et si vous allez aux paramètres d’alimentation avancés, vous verrez un sous-ensemble beaucoup plus petit d’options d’alimentation par rapport à un PC générique exécutant Windows 10. Contrairement aux appareils génériques, Surface dispose de microprogrammes et de composants personnalisés pour gérer ces options d’alimentation.


## Veille moderne

Le profil d’alimentation personnalisé incorporé de façon algorithmique permet une connectivité de veille moderne pour Surface en conservant un état d’alimentation faible pour les fonctionnalités d’personnalisation activée/instantanée typiques des smartphones. S0ix, également connu sous le nom d’état de plateforme d’inactivité du runtime (DRIPS), est le mode d’alimentation par défaut pour les appareils Surface. La veille moderne a deux modes :

- **Veille connectée.** Mode par défaut pour la remise à jour des messages électroniques, de la messagerie et des données synchronisées dans le cloud, la veille connectée conserve Wi-Fi et maintient la connectivité réseau.

- **Veille déconnectée.** Mode facultatif pour une autonomie étendue de la batterie, la veille déconnectée offre la même expérience d’inséparable et économise de l’énergie en dés mode Wi-Fi, Bluetooth et connectivité réseau associée.

Pour en savoir plus sur la veille moderne, consultez le Centre [de dév. matériel Microsoft.](https://docs.microsoft.com/windows-hardware/design/device-experiences/modern-standby-wake-sources)

## Comment Surface simplifie l’expérience de gestion de l’alimentation 

Surface intègre les fonctionnalités suivantes conçues pour aider les utilisateurs à optimiser l’expérience de gestion de l’alimentation :

- [Plan d’alimentation unique](#singular-power-plan)

- [Interface utilisateur des paramètres d’alimentation simplifiés](#simplified-power-settings-user-interface)

- [Curseur d’alimentation des performances Windows](#windows-performance-power-slider)

### Plan d’alimentation unique

Surface est conçu pour une expérience de gestion de l’alimentation simplifiée qui élimine la nécessité de créer des plans d’alimentation personnalisés ou de configurer manuellement les paramètres d’alimentation. Microsoft simplifie l’expérience utilisateur en propose un plan d’alimentation unique (équilibré) qui remplace les plans d’alimentation multiples des builds Windows standard.

### Interface utilisateur des paramètres d’alimentation simplifiés

Surface fournit une interface utilisateur simplifiée en accord avec les recommandations de réglage d’alimentation des meilleures pratiques. En règle générale, il est recommandé d’ajuster uniquement les paramètres visibles dans l’interface utilisateur par défaut et d’éviter de configurer les paramètres d’alimentation avancés ou de stratégie de groupe. L’utilisation des délai d’affichage et de veille par défaut tout en évitant les niveaux de luminosité maximum est la façon la plus efficace pour les utilisateurs de maintenir une autonomie de batterie étendue.

![Figure1. Paramètres d’alimentation & de veille simplifiée](images/powerintrofig1.png)

Figure1. Paramètres d’alimentation et de veille simplifiés

### Curseur d’alimentation des performances Windows

Les appareils Surface exécutant Windows 10, build 1709 et ultérieures incluent un curseur d’alimentation qui vous permet de hiérarchiser l’autonomie de la batterie si nécessaire ou de privilégier les performances si vous le souhaitez. Vous pouvez accéder au curseur d’alimentation à partir de la barre des tâches en cliquant sur l’icône de batterie. Faites glisser vers la gauche pour une durée de vie plus longue de la batterie (mode économiseur de batterie) ou faites glisser vers la droite pour des performances plus rapides.

![Figure2. Curseur d’alimentation](images/powerintrofig2a.png)

Figure2. Curseur d’alimentation

Le curseur d’alimentation active quatre états, comme décrit dans le tableau suivant :

| Mode curseur| Description |
|---|---|
| Économiseur de batterie| Permet d’économiser de l’énergie et de prolonger l’autonomie de la batterie lorsque le système est déconnecté d’une source d’alimentation. Lorsque l’économiseur de batterie est en place, certaines fonctionnalités De Windows sont désactivées, limitées ou se comportent différemment. La luminosité de l’écran est également réduite. L’économiseur de batterie est disponible uniquement lors de l’utilisation de l’alimentation de la batterie. Pour en savoir plus, [consultez l’Économiseur de batterie.](https://docs.microsoft.com/windows-hardware/design/component-guidelines/battery-saver)|
| Nos recommandations | Offre une autonomie de batterie plus longue que les paramètres par défaut dans les versions antérieures de Windows. |
| Meilleures performances | Privilégie légèrement les performances par rapport à l’autonomie de la batterie, qui fonctionne comme mode de curseur par défaut. |
| Meilleures performances | Privilégie les performances par rapport à l’alimentation pour les charges de travail nécessitant des performances et une réactivité maximales, quelle que soit la consommation d’énergie de la batterie.|

Les modes curseur d’alimentation contrôlent directement des composants matériels spécifiques indiqués dans le tableau suivant.

| Composant | Fonctionnalité de curseur |
|---|---|
| Indication de préférence sur les performances énergétiques et intel speed shift (registres d’énergie du processeur). | Sélectionne la meilleure fréquence et la meilleure fréquence d’exploitation pour optimiser les performances et la puissance. La préférence de performances énergétiques (PERFEPP) est un conseil global d’efficacité énergétique pour l’UC. |
| Vitesse de l’éventail (RPM)| Le cas échéant, s’ajuste pour modifier les conditions telles que le mode silencieux du curseur de l’économiseur de batterie.|
| Limites d’alimentation du package processeur (PL1/PL2).| Nécessite que l’UC gère ses choix de fréquence pour s’adapter à une limite de puissance moyenne en cours d’exécution pour les charges de travail d’état stable (PL1) et de pl2.|
| Limites de fréquence processeur processeur (limitations de limitations de l’IA). | Ajuste les performances du processeur et des graphiques, ce qui permet aux cœurs de processeur de s’exécuter plus rapidement ou plus lentement que la fréquence d’exploitation noté.                                                |

>[!NOTE]
>Le curseur d’alimentation est entièrement indépendant des paramètres d’alimentation du système d’exploitation, qu’ils soient configurés à partir du Panneau de configuration/ Options d’alimentation, de la stratégie de groupe ou des méthodes associées.

Pour plus d’informations, voir :

-   [Personnaliser le curseur d’alimentation des performances Windows](https://docs.microsoft.com/windows-hardware/customize/desktop/customize-power-slider)

-   [Économiseur de batterie.](https://docs.microsoft.com/windows-hardware/design/component-guidelines/battery-saver)

## Meilleures pratiques pour une autonomie de batterie étendue


| Meilleure pratique | Allez à | Étapes suivantes |
|---|---|---|                                                                                                                                    
| Vérifier que votre appareil Surface est à jour| WindowsUpdate | Dans la zone de recherche de la barre des tâches, tapez **Windows Update** et **sélectionnez Rechercher les mises à jour.** |
| Choisissez le meilleur paramètre d’alimentation pour ce que vous faites | Curseur d’alimentation | Dans la barre des tâches, sélectionnez l’icône de la batterie, puis choisissez Meilleures **performances,** **Meilleure**autonomie de la batterie ou quelque part entre les deux.|
| Économiser la batterie lorsqu’elle est faible | Économiseur de batterie | Dans la barre des tâches, sélectionnez l’icône de batterie, puis cliquez sur **Paramètres de la batterie.** Sélectionnez **Activer automatiquement l’économiseur** de batterie si ma batterie tombe en dessous, puis déplacez le curseur plus à droite pour une durée de vie plus longue de la batterie. |
| Configurer la luminosité optimale de l’écran | Économiseur de batterie | Dans la barre des tâches, sélectionnez l’icône de la batterie et cliquez sur **Paramètres**de la batterie, sélectionnez Luminosité de l’écran inférieure dans **l’économiseur de batterie.** |
| Économiser de l’énergie lorsque vous n’êtes pas branché | Économiseur de batterie| Sélectionnez **Activer l’état de l’économiseur de batterie jusqu’à la prochaine charge.**|
| Examinez les problèmes liés à vos paramètres d’alimentation. | Dépannage de l’alimentation | Dans la recherche de la barre des tâches pour la résolution des problèmes, sélectionnez Résoudre **les**problèmes, puis **sélectionnez Alimentation** et suivez les instructions.|
| Vérifier l’utilisation de l’application | Vos applications | Fermez les applications.|
| Vérifiez si votre cordon d’alimentation est endommagé.| Votre cordon d’alimentation | Remplacez le cordon d’alimentation en cas d’endommagement ou d’endommagement.|

## Si vous souhaitez en savoir plus 

- [Veille moderne](https://docs.microsoft.com/windows-hardware/design/device-experiences/modern-standby-wake-sources)

<!-- -->

- [Personnaliser le curseur d’alimentation des performances Windows](https://docs.microsoft.com/windows-hardware/customize/desktop/customize-power-slider)

- [Économiseur de batterie](https://docs.microsoft.com/windows-hardware/design/component-guidelines/battery-saver)
- [Gérer et déployer les mises à jour du microprogramme et des pilotes Surface](manage-surface-driver-and-firmware-updates.md)
