---
title: Manage Windows updates on Surface Hub
description: You can manage Windows updates on your Microsoft Surface Hub or Surface Hub 2S by setting the maintenance window, deferring updates, or using Windows Server Update Services (WSUS).
ms.assetid: A737BD50-2D36-4DE5-A604-55053D549045
ms.reviewer: ''
manager: laurawi
keywords: manage Windows updates, Surface Hub, Windows Server Update Services, WSUS
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: 72214ec9436e6ea106d9e42c957664631ee88a0a
ms.sourcegitcommit: f74253629aaf073b35b1af69439f76e63392c5aa
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/07/2020
ms.locfileid: "11103788"
---
# Manage Windows updates on Surface Hub

New releases of the Surface Hub operating system are published through Windows Update, just like releases of Windows 10. Deuxméthodes vous permettent de gérer les mises à jour installées sur vos SurfaceHub ainsi que le moment auquel les mises à jour sont appliquées.
- **Windows Update for Business**: nouveau dans Windows10, Windows Update for Business regroupe un ensemble de fonctionnalités destinées à fournir aux entreprises un contrôle renforcé sur la façon dont WindowsUpdate installe les versions et sur leurs dates d’installation, tout en réduisant les coûts de gestion de l’appareil. À l’aide de cette méthode, les SurfaceHub sont directement connectés au service WindowsUpdate de Microsoft.
- **WindowsServer Update Services (WSUS)**: ensemble de services qui permettent aux administrateurs informatiques d’obtenir les mises à jour que WindowsUpdate juge applicables aux appareils de leur entreprise, d’effectuer des tests et évaluations supplémentaires, et de sélectionner les mises à jour qu’ils souhaitent installer. À l’aide de cette méthode, les SurfaceHub reçoivent des mises à jour de WSUS à la place de WindowsUpdate.

Vous pouvez également configurer le SurfaceHub pour recevoir les mises à jour de Windows Update for Business et de WSUS. Pour plus d’informations, voir [Intégrer WindowsUpdate for Business à WindowsServerUpdateServices](https://technet.microsoft.com/itpro/windows/manage/waas-integrate-wufb#integrate-windows-update-for-business-with-windows-server-update-services).

| Fonctionnalités | Windows Update for Business | Windows Server Update Services (WSUS) |
| ------------ | --------------------------- | ------------------------------------- |
| Recevoir les mises à jour directement depuis le service WindowsUpdate de Microsoft, sans infrastructure supplémentaire nécessaire.  | Oui  | Non  |
| Différer les mises à jour pour offrir un délai supplémentaire pour les tests et l’évaluation. | Oui  | Oui  |
| Déployer les mises à jour vers des groupes d’appareils sélectionnés. | Oui | Oui |
| Définir les fenêtres de maintenance pour l’installation des mises à jour. | Oui  | Oui  |

> [!TIP]
> Utilisez le partage de contenu entre homologues pour réduire les problèmes de bande passante pendant les mises à jour. Pour plus d’informations, voir [Optimiser la distribution des mises à jour Windows10](https://technet.microsoft.com/itpro/windows/manage/waas-optimize-windows-10-updates).

> [!NOTE]
> Pour le moment, le SurfaceHub ne prend pas en charge la restauration des mises à jour.


## Modèle de maintenance du SurfaceHub

Le SurfaceHub utilise le modèle de maintenance de Windows10, appelé [Windows as a Service (WaaS)](https://docs.microsoft.com/windows/deployment/update/waas-overview). Traditionnellement, les nouvelles fonctionnalités étaient ajoutées uniquement dans les nouvelles versions de Windows qui étaient publiées tous les deux ou troisans. Chaque nouvelle version nécessite des processus longs et coûteux pour être déployée dans une organisation. Par conséquent, les utilisateurs finaux et les organisations ne bénéficient pas fréquemment des avantages d’une innovation. L’objectif de Windows as a Service est de fournir continuellement de nouvelles fonctionnalités tout en conservant un niveau de qualité élevé.

Microsoft publie régulièrement deuxtypes de version de SurfaceHub:
- **Feature updates** - Updates that install the latest new features, experiences, and capabilities. Microsoft expects to publish two new feature updates per year.
- **Quality updates** - Updates that focus on the installation of security fixes, drivers, and other servicing updates. Microsoft compte publier une mise à jour qualité cumulative par mois.

Pour améliorer la qualité des versions et simplifier les déploiements, toutes les nouvelles versions que Microsoft publiera pour Windows10, notamment le SurfaceHub, seront cumulatives. Cela signifie que les nouvelles mises à jour de fonctionnalités et mises à jour qualité contiendront la charge utile de toutes les versions précédentes (sous forme optimisée pour réduire les besoins de stockage et de gestion de réseau), et que l’installation de la nouvelle version sur un appareil aura pour effet de le mettre complètement à jour. Par ailleurs, contrairement aux versions antérieures de Windows, vous ne pouvez pas installer un sous-ensemble du contenu d’une mise à jour qualité de Windows10. Par exemple, si une mise à jour qualité contient des correctifs pour troisfailles de sécurité et un problème de fiabilité, son déploiement entraîne l’installation des quatrecorrectifs.

The Surface Hub operating system receives updates on the [Semi-Annual Channel](https://docs.microsoft.com/windows/deployment/update/waas-overview#naming-changes). Like other editions of Windows 10, the servicing lifetime is finite. You must install new feature updates on machines running these branches in order to continue receiving quality updates.

Pour plus d’informations sur Windows as a Service, voir [Vue d’ensemble de Windows as a Service](https://technet.microsoft.com/itpro/windows/manage/waas-overview).


## Utiliser WindowsUpdate for Business
Les SurfaceHub, comme tous les appareils Windows10, incluent **Windows Update for Business (WUfB)** pour vous permettre de contrôler la façon dont vos appareils sont mis à jour. Windows Update for Business contribue à réduire les coûts de gestion d’appareil, fournit des contrôles sur le déploiement des mises à jour, offre un accès plus rapide aux mises à jour de sécurité, et donne également accès aux dernières innovations de Microsoft de manière régulière. Pour plus d’informations, voir [Gérer les mises à jour à l’aide de Windows Update for Business](https://technet.microsoft.com/itpro/windows/manage/waas-manage-updates-wufb).

**Pour configurer WindowsUpdate for Business:**
1. [Regrouper les SurfaceHub dans des anneaux de déploiement.](#group-surface-hub-into-deployment-rings)
2. [Configure when Surface Hub receives updates](#configure-when-surface-hub-receives-updates).

> [!NOTE]
> You can use Microsoft Intune, Microsoft Endpoint Configuration Manager, or a supported third-party MDM provider to set up WUfB. [Walkthrough: use Microsoft Intune to configure Windows Update for Business.](https://docs.microsoft.com/windows/deployment/update/waas-wufb-intune)


### Regrouper les SurfaceHub dans des anneaux de déploiement
Utilisez les anneaux de déploiement pour contrôler le moment auquel les mises à jour sont déployées sur vos SurfaceHub, ce qui vous donne le temps de les valider. Par exemple, vous pouvez commencer par mettre à jour un petit pool d’appareils pour vérifier la qualité d’une mise à jour avant d’effectuer un déploiement plus large dans votre organisation. En fonction de la personne chargée de gérer le SurfaceHub dans votre organisation, pensez à incorporer le SurfaceHub dans les anneaux de déploiement que vous avez créés pour vos autres appareils Windows10. Pour plus d’informations sur les anneaux de déploiement, voir [Créer des anneaux de déploiement pour les mises à jour Windows10](https://technet.microsoft.com/itpro/windows/manage/waas-deployment-rings-windows-10-updates).

Le tableau ci-dessous donne quelques exemples d’anneaux de déploiement.

| Anneau de déploiement | Taille de l’anneau | Branche de maintenance | Report des mises à jour des fonctionnalités | Report des mises à jour qualité (correctifs de sécurité, pilotes et autres mises à jour) | Étape de validation |
| --------- | --------- | --------- | --------- | --------- | --------- |
| Évaluation (par exemple, appareils non essentiels ou de test) | Small | Windows Insider Preview | None.  | Aucun.  | Testez et évaluez les nouvelles fonctionnalités manuellement. Suspendez les mises à jour en cas de problèmes. |
| Version (par exemple, appareils utilisés par les équipes sélectionnées) | Moyen | Canal semi-annuel  | Aucun. | Aucun.  | Surveillez l’utilisation des appareils et les commentaires des utilisateurs. Suspendez les mises à jour en cas de problèmes. |
| Déploiement large (par exemple, la plupart des appareils de votre organisation) | Grande | Canal semi-annuel |  120jours après la publication. | 7-14jours après la publication. | Surveillez l’utilisation des appareils et les commentaires des utilisateurs. Suspendez les mises à jour en cas de problèmes. |
| Stratégique (par exemple, appareils des salles de réunion de direction) | Petite | Canal semi-annuel |  180jours après la publication (report maximal des mises à jour des fonctionnalités). | 30jours après la publication (report maximal des mises à jour qualité). | Surveillez l’utilisation des appareils et les commentaires des utilisateurs. |





### Configurer à quel moment le SurfaceHub reçoit des mises à jour
Une fois que vous avez déterminé les anneaux de déploiement pour vos SurfaceHub, configurez des stratégies de report de mise à jour pour chaque anneau:
- Pour différer les mises à jour des fonctionnalités, définissez une stratégie [Update/DeferFeatureUpdatesPeriodInDays](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-deferfeatureupdatesperiodindays) appropriée pour chaque anneau.
- Pour différer les mises à jour qualité, définissez une stratégie [Update/DeferQualityUpdatesPeriodInDays](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-deferqualityupdatesperiodindays) appropriée pour chaque anneau.

> [!NOTE]
> Si vous rencontrez des problèmes lors du déploiement des mises à jour, vous pouvez les suspendre à l’aide des stratégies [Update/PauseFeatureUpdates](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-pausefeatureupdates) et [Update/PauseQualityUpdates](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-pausequalityupdates).


## Utiliser Windows Server Update Services

Vous pouvez connecter le SurfaceHub à votre serveur WSUS (Windows Server Update Services) pour gérer les mises à jour. Celles-ci sont contrôlées par le biais d’approbations ou de règles de déploiement automatique configurées sur votre serveur WSUS. Les nouvelles mises à niveau ne sont donc pas déployées tant que vous ne l’avez pas décidé.

**Pour connecter manuellement un SurfaceHub à un serveur WSUS:**
1. Sur votre SurfaceHub, ouvrez **Paramètres**.
2. Entrez les informations d’identification d’administrateur de l’appareil lorsque vous y êtes invité.
3. Accédez à **Mise à jour et sécurité** > **WindowsUpdate** > **Options avancées** > **Configurer le serveur WindowsServer Update Services (WSUS)**.
4. Cliquez sur **Utiliser le serveur WSUS pour télécharger les mises à jour** et tapez l’URL de votre serveur WSUS.

Pour connecter le SurfaceHub à un serveur WSUS à l’aide de GPM, définissez une stratégie [Update/UpdateServiceUrl](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Update_UpdateServiceUrl) appropriée.

**Si vous utilisez un serveur proxy ou une autre méthode pour bloquer les URL**

Si vous utilisez une méthode autre que WSUS pour bloquer certaines URL et empêcher les mises à jour, vous devez ajouter les URL de la mise à jour de Windows dans votre liste de sites autorisés:
- `http(s)://*.update.microsoft.com`
- `http://download.windowsupdate.com` 
- `http://windowsupdate.microsoft.com`

Une fois la Mise à jour anniversaire Windows10 Collaboration installée, vous pourrez retirer ces adresses pour revenir à l'état initial de votre Surface Hub.

## Fenêtre de maintenance

To ensure the device is always available for use during business hours, Surface Hub performs its administrative functions during a specified maintenance window. During the maintenance window, the Surface Hub automatically installs updates through Windows Update or WSUS, and reboots the device 20 minutes before the end of the window.

Surface Hub follows these guidelines to apply updates:
- Il installe la mise à jour au cours de la prochaine fenêtre de maintenance. Si le démarrage d’une réunion est planifié pour se produire lors d’une fenêtre de maintenance ou si les capteurs du SurfaceHub détectent l’utilisation de l’appareil, la mise à jour en attente est repoussée à la fenêtre de maintenance suivante.
- Si la fenêtre de maintenance suivante se trouve au-delà de la période de grâce prescrite de la mise à jour, l’appareil calcule le créneau suivant disponible pendant les heures d’ouverture à l’aide de l’heure d’installation estimée d’après les métadonnées de la mise à jour. Il continue de reporter la mise à jour si une réunion est planifiée ou si les capteurs du SurfaceHub détectent que l’appareil est utilisé.
- If the next maintenance window is **not** past the update's grace period, the Surface Hub will continue to postpone the update.
- If a reboot is needed, the Surface Hub will automatically reboot during the next maintenance window.

> [!NOTE]
> Laissez du temps pour les mises à jour lors de la première configuration de votre SurfaceHub. Par exemple, un backlog des définitions de virus disponible doit être installé immédiatement.

A default maintenance window is set for all new Surface Hubs:
-   **Start time:** 2:00 AM
-   **Duration:** 2 hours

**To manually change the maintenance window:**
1.  Sur votre SurfaceHub, ouvrez **Paramètres**.
2.  Accédez à **Mise à jour et sécurité** > **Windows Update** > **Options avancées**.
3.  Sous **Heures de maintenance**, sélectionnez **Modifier**.

Pour modifier la fenêtre de maintenance à l’aide de GPM, définissez le nœud **MOMAgent** du [fournisseur de services de configuration SurfaceHub](https://msdn.microsoft.com/library/windows/hardware/mt608323.aspx). See [Manage settings with an MDM provider](manage-settings-with-mdm-for-surface-hub.md) for more details.


## More information

- [Blog post: Servicing, Flighting, and Managing updates for Surface Hub (With Intune, of course!)](https://blogs.technet.microsoft.com/y0av/2018/05/31/7-3/)


## Related topics

[Gérer Microsoft Surface Hub](manage-surface-hub.md)

[Guide de l’administrateur Microsoft Surface Hub](surface-hub-administrators-guide.md)

