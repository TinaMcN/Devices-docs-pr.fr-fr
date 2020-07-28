---
title: Gérer les mises à jour de pilotes Surface dans Configuration Manager
description: Cet article décrit les options disponibles pour gérer et déployer des mises à jour de microprogramme et de pilote pour les appareils surface.
ms.assetid: b64879c4-37eb-4fcf-a000-e05cbb3d26ea
ms.reviewer: ''
author: v-miegge
manager: laurawi
keywords: Surface, Surface Pro3, microprogramme, mettre à jour, appareil, gérer, déployer, pilote, USB
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
ms.author: daclark
ms.topic: article
audience: itpro
ms.openlocfilehash: be32309b26ff6a873c36927cc39595022c4dbb90
ms.sourcegitcommit: ed4478dd3c6116a25b1e01a3a0f5ff6c1f940013
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/27/2020
ms.locfileid: "10897072"
---
# Gérer les mises à jour de pilotes Surface dans Configuration Manager

## Résumé

À compter de la [version 1710 de Microsoft System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/changes/whats-new-in-version-1710#software-updates), vous pouvez synchroniser et déployer des mises à jour de pilote et de microprogramme Microsoft surface directement via le client Configuration Manager. Le processus ressemble au déploiement de mises à jour régulières. Toutefois, certaines configurations supplémentaires sont nécessaires pour obtenir les mises à jour du pilote surface dans votre catalogue.

## Conditions préalables

Pour gérer les mises à jour de pilote surface, les conditions préalables suivantes doivent être remplies:

- Vous devez utiliser Configuration Manager version 1710 ou une version ultérieure.
- Tous les points de mise à jour logicielle (SUPs) doivent exécuter Windows Server 2016 ou une version ultérieure. Dans le cas contraire, le gestionnaire de configuration ignore ce paramètre et les pilotes de surface ne seront pas synchronisés.

> [!NOTE]
> Si votre environnement ne répond pas à la configuration requise, reportez-vous aux différentes [méthodes](https://support.microsoft.com/help/4098906/manage-surface-driver-updates-in-configuration-manager#1) de déploiement des mises à jour de pilote de surface et de microprogramme dans la section [FAQ](#frequently-asked-questions-faq) .

## Fichiers journaux utiles

Les journaux suivants sont particulièrement utiles lorsque vous gérez les mises à jour de pilote surface.

|Nom du journal|Description|
|---|---|
|WCM. log|Enregistre les détails relatifs à la configuration du point de mise à jour logicielle, ainsi que les connexions au serveur WSUS pour les catégories, classifications et langues de mise à jour abonnées.|
|WsyncMgr. log|Enregistre des informations sur le processus de synchronisation des mises à jour logicielles.|

Ces journaux sont situés sur le serveur de site qui gère le SUP ou sur le SUP s’il est installé directement sur un serveur de site.
Pour obtenir la liste complète des journaux du gestionnaire de configurations, voir [fichiers journaux dans System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/log-files).

## Activation de la gestion des mises à jour de pilotes surface

Pour activer la gestion des mises à jour de pilotes de surface dans Configuration Manager, procédez comme suit:

1. Dans la console Configuration Manager, accédez à **Administration**  >  **vue d’ensemble**de l’administration  >  **site de configuration**  >  **Sites**.
1. Sélectionnez le site contenant le serveur SUP de niveau supérieur pour votre environnement.
1. Dans le ruban, sélectionnez **configurer les composants de site**, puis **point de mise à jour logicielle**. Ou cliquez avec le bouton droit sur le site, puis sélectionnez **configurer**le  >  **point de mise à jour logicielle**des composants de site.
1. Sous l’onglet **classifications** , activez la case à cocher **inclure les pilotes de surface Microsoft et les mises à jour du microprogramme** .

   ![Propriétés du composant du point de mise à jour logicielle](images/manage-surface-driver-updates-1.png)

1. Lorsque le message d’avertissement suivant apparaît, sélectionnez **OK**.

   ![Configuration Manager](images/manage-surface-driver-updates-2.png)

1. Dans l’onglet produits, sélectionnez les produits que vous voulez mettre à jour, puis cliquez sur **OK**.

   La plupart des pilotes appartiennent aux groupes de produits suivants:

   - Pilotes Windows 10 et versions ultérieures
   - Mise à niveau vers Windows 10 et versions ultérieures & de pilotes de service
   - Mise à jour anniversaire Windows 10 et pilotes de maintenance ultérieures
   - Mise à jour anniversaire de Windows 10 et mise à niveau ultérieure & les pilotes de maintenance
   - Pilotes de maintenance de Windows 10 Creators Update et version ultérieure
   - Mise à jour de Windows 10 Creators Update et version ultérieure & les pilotes de maintenance
   - Windows 10 automne Creators Update et les pilotes de maintenance ultérieurs
   - Windows 10 automne créateurs mise à jour et mise à niveau ultérieure & les pilotes de maintenance
   - Pilotes de service Windows 10 S et versions ultérieures
   - Versions 1709 et ultérieures de Windows 10 S avec les pilotes de maintenance
   - Mise à niveau vers la version 1709 de Windows 10 et les versions ultérieures & pilotes de maintenance pour le test

   > [!NOTE]
   > La plupart des pilotes de surface appartiennent à plusieurs groupes de produits Windows 10. Il est possible que vous n’ayez pas besoin de sélectionner tous les produits répertoriés ici. Pour réduire le nombre de produits qui remplissent votre catalogue de mise à jour, nous vous recommandons de sélectionner uniquement les produits requis par votre environnement pour la synchronisation.

## Vérification de la configuration

Pour vérifier que le SUP est configuré correctement, procédez comme suit:

1. Ouvrez WsyncMgr. log, puis recherchez l’entrée suivante:

   ```console
   Surface Drivers can be supported in this hierarchy since all SUPs are on Windows Server 2016, WCM SCF property Sync Catalog Drivers is set.

   Sync Catalog Drivers SCF value is set to : 1
   ```

   Si l’une des entrées suivantes est enregistrée dans WsyncMgr. log, revérifier l’étape 4 de la section précédente:

   ```console
   Sync Surface Drivers option is not set

   Sync Catalog Drivers SCF value is set to : 0
   ```

1. Ouvrez WCM. log, puis recherchez une entrée qui ressemble à ce qui suit:

   ![Paramètres de WCM. log](images/manage-surface-driver-updates-3.png)

   Cette entrée est un élément XML qui recense chaque groupe de produits et classification actuellement synchronisé par votre serveur SUP. Par exemple, il se peut que vous voyiez une entrée semblable à ce qui suit:

   ```xml
   <Categories>
       <Category Id="Product:05eebf61-148b-43cf-80da-1c99ab0b8699"><![CDATA[Windows 10 and later drivers]]></Category>
       <Category Id="Product:06da2f0c-7937-4e28-b46c-a37317eade73"><![CDATA[Windows 10 Creators Update and Later Upgrade & Servicing Drivers]]></Category>
       <Category Id="Product:c1006636-eab4-4b0b-b1b0-d50282c0377e"><![CDATA[Windows 10 S and Later Servicing Drivers]]></Category>
   </Categories>
   ```

   Si vous ne trouvez pas les produits sélectionnés à l’étape 6 de la section précédente, vérifiez si les paramètres SUP sont enregistrés.

   Vous pouvez également attendre la fin de la synchronisation suivante, puis vérifier si les mises à jour de pilote de surface et de microprogramme apparaissent dans les mises à jour logicielles dans la console Configuration Manager. Par exemple, la console peut afficher les informations suivantes.

   ![Tous les résultats de la recherche mises à jour logicielles](images/manage-surface-driver-updates-4.png)

## Synchronisation manuelle

Si vous ne voulez pas attendre la prochaine synchronisation, procédez comme suit pour démarrer une synchronisation:

1. Dans la console Configuration Manager, accédez à **Software Library**  >  **vue d’ensemble**des bibliothèques logicielles  >  **mises à jour**de  >  **toutes les mises à jour logicielles**.
1. Dans le ruban, sélectionnez **synchroniser les mises à jour logicielles**. Ou cliquez avec le bouton droit sur **toutes les mises à jour logicielles**, puis sélectionnez **synchroniser la mise à jour logicielle**.
1. Pour surveiller la progression de la synchronisation, recherchez les entrées suivantes dans WsyncMgr. log:

   ```console
   Surface Drivers can be supported in this hierarchy since all SUPs are on Windows Server 2016, WCM SCF property Sync Catalog Drivers is set.

   sync: SMS synchronizing categories 
   sync: SMS synchronizing categories, processed 0 out of 311 items (0%)
   sync: SMS synchronizing categories, processed 311 out of 311 items (100%)
   sync: SMS synchronizing categories, processed 311 out of 311 items (100%)
   sync: SMS synchronizing updates

   Synchronizing update 7eaa0148-c42b-45fd-a1ab-012c82972de6 - Microsoft driver update for Surface Type Cover Integration
   Synchronizing update 2dcb07f8-37ec-41ef-8cd5-030bf24dc1d8 - Surface driver update for Surface Pen Pairing
   Synchronizing update 63067414-ae52-422b-b3d1-0382a4d6519a - Surface driver update for Surface UEFI
   Synchronizing update 8e4e3a41-a784-4dd7-9a42-041f43ddb775 - Surface driver update for Surface Integration
   Synchronizing update 7f8baee8-419f-47e2-918a-045a15a188e7 - Microsoft driver update for Surface DTX
   Synchronizing update aed66e05-719b-48cd-a0e7-059e50f67fdc - Microsoft driver update for Surface Base Firmware Update
   Synchronizing update 8ffe1526-6e66-43cc-86e3-05ad92a24e3a - Surface driver update for Surface UEFI
   Synchronizing update 74102899-0a49-48cf-97e6-05bde18a27ff - Microsoft driver update for Surface UEFI
   ```

## Déploiement de mises à jour de microprogrammes et de pilotes de surface

Vous pouvez déployer des mises à jour de microprogrammes et de pilotes de surface de la même manière que lors du déploiement d’autres mises à jour.

Pour plus d’informations sur le déploiement, voir [System Center 2012 Configuration Manager-part7: mises à jour logicielles (déploiement)](https://blogs.technet.microsoft.com/elie/2012/05/25/system-center-2012-configuration-managerpart7-software-updates-deploy/).

## Forum Aux Questions (FAQ)

**Après avoir suivi les étapes décrites dans cet article, les pilotes de surface ne sont toujours pas synchronisés. Pourquoi?**

Si vous effectuez une synchronisation à partir d’un serveur Windows Server Update Services (WSUS) en amont au lieu de Microsoft Update, assurez-vous que le serveur WSUS en amont est configuré pour prendre en charge et synchroniser les mises à jour de pilote surface. Tous les serveurs en aval sont limités aux mises à jour présentes dans la base de données du serveur WSUS en amont.

Il existe plusieurs mises à jour de 68 000 classées comme pilotes dans WSUS. Pour empêcher les pilotes non liés à la surface d’être synchronisés avec la Configuration Manager, Microsoft filtre la synchronisation du pilote sur une liste verte. Une fois la nouvelle liste verte publiée et incorporée dans Configuration Manager, les nouveaux pilotes sont ajoutés à la console à la suite de la synchronisation suivante. Microsoft a pour but de télécharger les pilotes de surface ajoutés à la liste verte chaque mois en fonction de leurs mises à jour mensuelles, afin de les rendre disponibles pour la synchronisation avec Configuration Manager.

Si votre environnement Configuration Manager est hors connexion, une nouvelle liste verte est importée chaque fois que vous importez des [mises à jour de maintenance](https://docs.microsoft.com/mem/configmgr/core/servers/manage/use-the-service-connection-tool) dans Configuration Manager. Vous devrez également importer un [nouveau catalogue WSUS](https://docs.microsoft.com/mem/configmgr/sum/get-started/synchronize-software-updates-disconnected) qui contient les pilotes avant que les mises à jour ne soient affichées dans la console Configuration Manager. Dans la mesure où un environnement WSUS autonome comporte plus de pilotes qu’un SUP Configuration Manager, nous vous recommandons de créer un environnement Configuration Manager doté de fonctionnalités en ligne et de le configurer pour synchroniser les pilotes de surface. Cela fournit une plus petite exportation WSUS qui ressemble étroitement à l’environnement hors connexion.

Si votre environnement Configuration Manager est connecté et en mesure de détecter de nouvelles mises à jour, vous recevrez automatiquement les mises à jour de la liste. Si vous ne voyez pas les pilotes attendus, consultez les fichiers WCM. log et WsyncMgr. log pour les échecs de synchronisation.

**Mon environnement Configuration Manager est hors connexion. Puis-je importer manuellement des pilotes de surface dans WSUS?**

Non. Même si la mise à jour est importée dans WSUS, la mise à jour ne sera pas importée dans la console Configuration Manager à des fins de déploiement, si elle ne figure pas dans la liste verte. Vous devez utiliser l' [outil de connexion de service](https://docs.microsoft.com/mem/configmgr/core/servers/manage/use-the-service-connection-tool) pour importer les mises à jour de maintenance dans Configuration Manager afin de mettre à jour la liste verte.

**Quelles sont les méthodes qui s’offrent à vous pour déployer les mises à jour de pilote et de microprogramme de surface?**

Pour plus d’informations sur le déploiement des mises à jour de pilote de surface et de microprogramme par le biais de canaux secondaires, voir [gérer les mises à jour de pilote de surface et de microprogramme](manage-surface-driver-and-firmware-updates.md). Pour télécharger le fichier. msi ou. exe et le déployer par le biais de canaux de déploiement de logiciels traditionnels, voir [maintenir le microprogramme de surface mis à jour avec Configuration Manager](https://docs.microsoft.com/archive/blogs/thejoncallahan/keeping-surface-firmware-updated-with-configuration-manager).

## Informations supplémentaires

Pour plus d’informations sur les mises à jour de pilote surface et de microprogramme, voir les articles suivants:

- [Gérer les mises à jour du microprogramme et des pilotesSurface](manage-surface-driver-and-firmware-updates.md)
- [Considérations relatives à Surface et à System Center Configuration Manager](considerations-for-surface-and-system-center-configuration-manager.md)
