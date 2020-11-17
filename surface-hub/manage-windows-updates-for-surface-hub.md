---
title: Gérer les mises à jourWindows sur SurfaceHub
description: Décrit les meilleures pratiques en matière de gestion des mises à jour sur Microsoft surface Hub ou surface Hub 2.
ms.assetid: A737BD50-2D36-4DE5-A604-55053D549045
ms.reviewer: ''
manager: laurawi
keywords: gestion des mises à jour Windows, de surface Hub, de Windows Server Update Services
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 10/27/2020
ms.localizationpriority: medium
ms.openlocfilehash: e5ffefa44560d01135b3ac656d9357f1115110ba
ms.sourcegitcommit: d60f82d9d22fe118f9c8dc24458d2c144b138eb8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2020
ms.locfileid: "11174724"
---
# Gérer les mises à jourWindows sur SurfaceHub

De nouvelles versions du système d’exploitation de SurfaceHub sont publiées par le biais de WindowsUpdate, tout comme les versions de Windows10. Cette page présente les meilleures pratiques en matière de gestion des mises à jour pour les appareils surface Hub. 

## WindowsUpdate for Business

Windows Update pour les entreprises est un ensemble de fonctionnalités conçues pour permettre aux entreprises d’avoir davantage de contrôle sur la façon dont Windows Update installe les versions, tout en réduisant les coûts de gestion des périphériques. À l’aide de cette méthode, les SurfaceHub sont directement connectés au service WindowsUpdate de Microsoft.

- Recevoir les mises à jour directement depuis le service WindowsUpdate de Microsoft, sans infrastructure supplémentaire nécessaire. 
- Différer les mises à jour pour offrir un délai supplémentaire pour les tests et l’évaluation. 
- Déployer les mises à jour vers des groupes d’appareils sélectionnés. 
- Définir les fenêtres de maintenance pour l’installation des mises à jour. 

> [!TIP]
> Utilisez le partage de contenu entre homologues pour réduire les problèmes de bande passante pendant les mises à jour. Pour plus d’informations, voir [Optimiser la distribution des mises à jour Windows10](https://technet.microsoft.com/itpro/windows/manage/waas-optimize-windows-10-updates).

> [!NOTE]
> Pour le moment, le SurfaceHub ne prend pas en charge la restauration des mises à jour.


## Modèle de maintenance du SurfaceHub

Le SurfaceHub utilise le modèle de maintenance de Windows10, appelé [Windows as a Service (WaaS)](https://docs.microsoft.com/windows/deployment/update/waas-overview). Traditionnellement, les nouvelles fonctionnalités étaient ajoutées uniquement dans les nouvelles versions de Windows qui étaient publiées tous les deux ou troisans. Chaque nouvelle version nécessite des processus longs et coûteux pour être déployée dans une organisation. Par conséquent, les utilisateurs finaux et les organisations ne bénéficient pas fréquemment des avantages d’une innovation. L’objectif de Windows as a Service est de fournir continuellement de nouvelles fonctionnalités tout en conservant un niveau de qualité élevé.

Microsoft publie régulièrement deuxtypes de version de SurfaceHub:
- **Mises à jour des fonctionnalités**: mises à jour qui installent les toutes nouvelles fonctions, expériences et fonctionnalités. Microsoft s’attend à publier deux nouvelles mises à jour de fonctionnalités par an.
- **Mises à jour qualité**: mises à jour qui se concentrent sur l’installation de correctifs de sécurité, de pilotes et d’autres mises à jour de maintenance. Microsoft compte publier une mise à jour qualité cumulative par mois.

Pour améliorer la qualité des versions et simplifier les déploiements, toutes les nouvelles versions que Microsoft publiera pour Windows10, notamment le SurfaceHub, seront cumulatives. Cela signifie que les nouvelles mises à jour de fonctionnalités et mises à jour qualité contiendront la charge utile de toutes les versions précédentes (sous forme optimisée pour réduire les besoins de stockage et de gestion de réseau), et que l’installation de la nouvelle version sur un appareil aura pour effet de le mettre complètement à jour. Par ailleurs, contrairement aux versions antérieures de Windows, vous ne pouvez pas installer un sous-ensemble du contenu d’une mise à jour qualité de Windows10. Par exemple, si une mise à jour qualité contient des correctifs pour troisfailles de sécurité et un problème de fiabilité, son déploiement entraîne l’installation des quatrecorrectifs.

Le système d’exploitation du Surface Hub reçoit des mises à jour sur le [canal semi-annuel](https://docs.microsoft.com/windows/deployment/update/waas-overview#naming-changes). À l’instar des autres éditions de Windows 10, la durée de vie de maintenance est limitée. Vous devez installer les nouvelles mises à jour des fonctionnalités sur les ordinateurs exécutant ces branches pour continuer à recevoir les mises à jour qualité.

Pour plus d’informations sur Windows as a Service, voir [Vue d’ensemble de Windows as a Service](https://technet.microsoft.com/itpro/windows/manage/waas-overview).


## Utiliser WindowsUpdate for Business

Les SurfaceHub, comme tous les appareils Windows10, incluent **Windows Update for Business (WUfB)** pour vous permettre de contrôler la façon dont vos appareils sont mis à jour. Windows Update for Business contribue à réduire les coûts de gestion d’appareil, fournit des contrôles sur le déploiement des mises à jour, offre un accès plus rapide aux mises à jour de sécurité, et donne également accès aux dernières innovations de Microsoft de manière régulière. Pour plus d’informations, voir [Gérer les mises à jour à l’aide de Windows Update for Business](https://technet.microsoft.com/itpro/windows/manage/waas-manage-updates-wufb).

**Pour configurer WindowsUpdate for Business:**
1. [Regrouper les SurfaceHub dans des anneaux de déploiement.](#group-surface-hub-into-deployment-rings)
2. [Configurer à quel moment le SurfaceHub reçoit des mises à jour](#configure-when-surface-hub-receives-updates).

> [!NOTE]
> Vous pouvez utiliser Microsoft Intune, Microsoft Endpoint Configuration Manager ou un fournisseur de services de gestion des appareils mobiles tiers pris en charge pour configurer WUfB. [Procédure pas à pas: Utiliser MicrosoftIntune pour configurer WindowsUpdate for Business.](https://docs.microsoft.com/windows/deployment/update/waas-wufb-intune)


### Regrouper les SurfaceHub dans des anneaux de déploiement

Utilisez les anneaux de déploiement pour contrôler le moment auquel les mises à jour sont déployées sur vos SurfaceHub, ce qui vous donne le temps de les valider. Par exemple, vous pouvez commencer par mettre à jour un petit pool d’appareils pour vérifier la qualité d’une mise à jour avant d’effectuer un déploiement plus large dans votre organisation. En fonction de la personne chargée de gérer le SurfaceHub dans votre organisation, pensez à incorporer le SurfaceHub dans les anneaux de déploiement que vous avez créés pour vos autres appareils Windows10. Pour plus d’informations sur les anneaux de déploiement, voir [Créer des anneaux de déploiement pour les mises à jour Windows10](https://technet.microsoft.com/itpro/windows/manage/waas-deployment-rings-windows-10-updates).

Consultez le tableau ci-dessous pour obtenir des exemples d’anneaux de déploiement.

| Anneau de déploiement | Taille de l’anneau | Branche de maintenance | Report des mises à jour des fonctionnalités | Report des mises à jour qualité (correctifs de sécurité, pilotes et autres mises à jour) | Étape de validation |
| --------- | --------- | --------- | --------- | --------- | --------- |
| Évaluation (par exemple, appareils non essentiels ou de test) | Petite | Windows Insider preview | Aucun.  | Aucun.  | Testez et évaluez les nouvelles fonctionnalités manuellement. Suspendez les mises à jour en cas de problèmes. |
| Version (par exemple, appareils utilisés par les équipes sélectionnées) | Moyen | Canal semi-annuel  | Aucun. | Aucun.  | Surveillez l’utilisation des appareils et les commentaires des utilisateurs. Suspendez les mises à jour en cas de problèmes. |
| Déploiement large (par exemple, la plupart des appareils de votre organisation) | Grande | Canal semi-annuel |  120jours après la publication. | 7-14jours après la publication. | Surveillez l’utilisation des appareils et les commentaires des utilisateurs. Suspendez les mises à jour en cas de problèmes. |
| Stratégique (par exemple, appareils des salles de réunion de direction) | Petite | Canal semi-annuel |  180jours après la publication (report maximal des mises à jour des fonctionnalités). | 30jours après la publication (report maximal des mises à jour qualité). | Surveillez l’utilisation des appareils et les commentaires des utilisateurs. |


### Configurer à quel moment le SurfaceHub reçoit des mises à jour

Une fois que vous avez déterminé les anneaux de déploiement pour vos SurfaceHub, configurez des stratégies de report de mise à jour pour chaque anneau:
- Pour différer les mises à jour des fonctionnalités, définissez une stratégie [Update/DeferFeatureUpdatesPeriodInDays](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-deferfeatureupdatesperiodindays) appropriée pour chaque anneau.
- Pour différer les mises à jour qualité, définissez une stratégie [Update/DeferQualityUpdatesPeriodInDays](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-deferqualityupdatesperiodindays) appropriée pour chaque anneau.

> [!NOTE]
> Si vous rencontrez des problèmes lors du déploiement des mises à jour, vous pouvez les suspendre à l’aide des stratégies [Update/PauseFeatureUpdates](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-pausefeatureupdates) et [Update/PauseQualityUpdates](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-pausequalityupdates).

**Si vous utilisez un serveur proxy ou une autre méthode pour bloquer les URL**

Ajoutez les URL suivantes du site de confiance Windows Update à la liste verte:
- `http(s)://*.update.microsoft.com`
- `http://download.windowsupdate.com` 
- `http://windowsupdate.microsoft.com`

Une fois la Mise à jour anniversaire Windows10 Collaboration installée, vous pourrez retirer ces adresses pour revenir à l'état initial de votre Surface Hub.

## Fenêtre de maintenance

Pour veiller à ce que l’appareil puisse toujours être utilisé pendant les heures d’ouverture, le SurfaceHub effectue ses fonctions d’administration pendant une fenêtre de maintenance spécifiée. Pendant la fenêtre de maintenance, surface Hub installe automatiquement les mises à jour par le biais de Windows Update, puis redémarre l’appareil 20 minutes avant la fin de la fenêtre.

Le SurfaceHub suit les instructions suivantes pour appliquer les mises à jour:
- Il installe la mise à jour au cours de la prochaine fenêtre de maintenance. Si le démarrage d’une réunion est planifié pour se produire lors d’une fenêtre de maintenance ou si les capteurs du SurfaceHub détectent l’utilisation de l’appareil, la mise à jour en attente est repoussée à la fenêtre de maintenance suivante.
- Si la fenêtre de maintenance suivante se trouve au-delà de la période de grâce prescrite de la mise à jour, l’appareil calcule le créneau suivant disponible pendant les heures d’ouverture à l’aide de l’heure d’installation estimée d’après les métadonnées de la mise à jour. Il continue de reporter la mise à jour si une réunion est planifiée ou si les capteurs du SurfaceHub détectent que l’appareil est utilisé.
- Si la fenêtre de maintenance suivante ne se trouve **pas** au-delà de la période de grâce de la mise à jour, l’aire surface Hub continue de différer la mise à jour.
- Si un redémarrage est nécessaire, le SurfaceHub redémarre automatiquement au cours de la fenêtre de maintenance suivante.

> [!NOTE]
> Laissez du temps pour les mises à jour lors de la première configuration de votre SurfaceHub. Par exemple, un backlog des définitions de virus disponible doit être installé immédiatement.

Une fenêtre de maintenance par défaut est définie pour tous les nouveaux SurfaceHub:
-   **Heure de début:** 2:00 AM
-   **Durée:** 2 heures

**Pour modifier manuellement la fenêtre de maintenance:**
1.  Sur votre SurfaceHub, ouvrez **Paramètres**.
2.  Accédez à **Mise à jour et sécurité** > **Windows Update** > **Options avancées**.
3.  Sous **Heures de maintenance**, sélectionnez **Modifier**.

Pour changer la fenêtre de maintenance à l’aide de la gestion des périphériques mobiles, définissez le nœud **MaintenanceHoursSimple** dans le [fournisseur de services de configuration SurfaceHub](https://msdn.microsoft.com/library/windows/hardware/mt608323.aspx). Pour plus d’informations, voir [Gérer les paramètres avec un fournisseur GPM](manage-settings-with-mdm-for-surface-hub.md).


## Informations supplémentaires

- [Billet de blog: maintenance, version d’évaluation et gestion des mises à jour pour surface Hub (avec Intune, bien entendu)](https://blogs.technet.microsoft.com/y0av/2018/05/31/7-3/)


## Rubriques connexes

[Gérer Microsoft Surface Hub](manage-surface-hub.md)

[Guide de l’administrateur Microsoft Surface Hub](surface-hub-administrators-guide.md)

