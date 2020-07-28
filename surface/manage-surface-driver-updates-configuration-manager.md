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
# <span data-ttu-id="9f60e-104">Gérer les mises à jour de pilotes Surface dans Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="9f60e-104">Manage Surface driver updates in Configuration Manager</span></span>

## <span data-ttu-id="9f60e-105">Résumé</span><span class="sxs-lookup"><span data-stu-id="9f60e-105">Summary</span></span>

<span data-ttu-id="9f60e-106">À compter de la [version 1710 de Microsoft System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/changes/whats-new-in-version-1710#software-updates), vous pouvez synchroniser et déployer des mises à jour de pilote et de microprogramme Microsoft surface directement via le client Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="9f60e-106">Starting in [Microsoft System Center Configuration Manager version 1710](https://docs.microsoft.com/sccm/core/plan-design/changes/whats-new-in-version-1710#software-updates), you can synchronize and deploy Microsoft Surface firmware and driver updates directly through the Configuration Manager client.</span></span> <span data-ttu-id="9f60e-107">Le processus ressemble au déploiement de mises à jour régulières.</span><span class="sxs-lookup"><span data-stu-id="9f60e-107">The process resembles deploying regular updates.</span></span> <span data-ttu-id="9f60e-108">Toutefois, certaines configurations supplémentaires sont nécessaires pour obtenir les mises à jour du pilote surface dans votre catalogue.</span><span class="sxs-lookup"><span data-stu-id="9f60e-108">However, some additional configurations are required to get the Surface driver updates into your catalog.</span></span>

## <span data-ttu-id="9f60e-109">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="9f60e-109">Prerequisites</span></span>

<span data-ttu-id="9f60e-110">Pour gérer les mises à jour de pilote surface, les conditions préalables suivantes doivent être remplies:</span><span class="sxs-lookup"><span data-stu-id="9f60e-110">To manage Surface driver updates, the following prerequisites must be met:</span></span>

- <span data-ttu-id="9f60e-111">Vous devez utiliser Configuration Manager version 1710 ou une version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="9f60e-111">You must use Configuration Manager version 1710 or a later version.</span></span>
- <span data-ttu-id="9f60e-112">Tous les points de mise à jour logicielle (SUPs) doivent exécuter Windows Server 2016 ou une version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="9f60e-112">All Software Update Points (SUPs) must run Windows Server 2016 or a later version.</span></span> <span data-ttu-id="9f60e-113">Dans le cas contraire, le gestionnaire de configuration ignore ce paramètre et les pilotes de surface ne seront pas synchronisés.</span><span class="sxs-lookup"><span data-stu-id="9f60e-113">Otherwise, Configuration Manager ignores this setting and Surface drivers won't be synchronized.</span></span>

> [!NOTE]
> <span data-ttu-id="9f60e-114">Si votre environnement ne répond pas à la configuration requise, reportez-vous aux différentes [méthodes](https://support.microsoft.com/help/4098906/manage-surface-driver-updates-in-configuration-manager#1) de déploiement des mises à jour de pilote de surface et de microprogramme dans la section [FAQ](#frequently-asked-questions-faq) .</span><span class="sxs-lookup"><span data-stu-id="9f60e-114">If your environment doesn’t meet the prerequisites, refer to the [alternative methods](https://support.microsoft.com/help/4098906/manage-surface-driver-updates-in-configuration-manager#1) to deploy Surface driver and firmware updates in the [FAQ](#frequently-asked-questions-faq) section.</span></span>

## <span data-ttu-id="9f60e-115">Fichiers journaux utiles</span><span class="sxs-lookup"><span data-stu-id="9f60e-115">Useful log files</span></span>

<span data-ttu-id="9f60e-116">Les journaux suivants sont particulièrement utiles lorsque vous gérez les mises à jour de pilote surface.</span><span class="sxs-lookup"><span data-stu-id="9f60e-116">The following logs are especially useful when you manage Surface driver updates.</span></span>

|<span data-ttu-id="9f60e-117">Nom du journal</span><span class="sxs-lookup"><span data-stu-id="9f60e-117">Log name</span></span>|<span data-ttu-id="9f60e-118">Description</span><span class="sxs-lookup"><span data-stu-id="9f60e-118">Description</span></span>|
|---|---|
|<span data-ttu-id="9f60e-119">WCM. log</span><span class="sxs-lookup"><span data-stu-id="9f60e-119">WCM.log</span></span>|<span data-ttu-id="9f60e-120">Enregistre les détails relatifs à la configuration du point de mise à jour logicielle, ainsi que les connexions au serveur WSUS pour les catégories, classifications et langues de mise à jour abonnées.</span><span class="sxs-lookup"><span data-stu-id="9f60e-120">Records details about the software update point configuration and connections to the WSUS server for subscribed update categories, classifications, and languages.</span></span>|
|<span data-ttu-id="9f60e-121">WsyncMgr. log</span><span class="sxs-lookup"><span data-stu-id="9f60e-121">WsyncMgr.log</span></span>|<span data-ttu-id="9f60e-122">Enregistre des informations sur le processus de synchronisation des mises à jour logicielles.</span><span class="sxs-lookup"><span data-stu-id="9f60e-122">Records details about the software updates sync process.</span></span>|

<span data-ttu-id="9f60e-123">Ces journaux sont situés sur le serveur de site qui gère le SUP ou sur le SUP s’il est installé directement sur un serveur de site.</span><span class="sxs-lookup"><span data-stu-id="9f60e-123">These logs are located on the site server that manages the SUP, or on the SUP itself if it's installed directly on a site server.</span></span>
<span data-ttu-id="9f60e-124">Pour obtenir la liste complète des journaux du gestionnaire de configurations, voir [fichiers journaux dans System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/log-files).</span><span class="sxs-lookup"><span data-stu-id="9f60e-124">For a complete list of Configuration Manager logs, see [Log files in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/log-files).</span></span>

## <span data-ttu-id="9f60e-125">Activation de la gestion des mises à jour de pilotes surface</span><span class="sxs-lookup"><span data-stu-id="9f60e-125">Enabling Surface driver updates management</span></span>

<span data-ttu-id="9f60e-126">Pour activer la gestion des mises à jour de pilotes de surface dans Configuration Manager, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="9f60e-126">To enable Surface driver updates management in Configuration Manager, follow these steps:</span></span>

1. <span data-ttu-id="9f60e-127">Dans la console Configuration Manager, accédez à **Administration**  >  **vue d’ensemble**de l’administration  >  **site de configuration**  >  **Sites**.</span><span class="sxs-lookup"><span data-stu-id="9f60e-127">In the Configuration Manager console, go to **Administration** > **Overview** > **Site Configuration** > **Sites**.</span></span>
1. <span data-ttu-id="9f60e-128">Sélectionnez le site contenant le serveur SUP de niveau supérieur pour votre environnement.</span><span class="sxs-lookup"><span data-stu-id="9f60e-128">Select the site that contains the top-level SUP server for your environment.</span></span>
1. <span data-ttu-id="9f60e-129">Dans le ruban, sélectionnez **configurer les composants de site**, puis **point de mise à jour logicielle**.</span><span class="sxs-lookup"><span data-stu-id="9f60e-129">On the ribbon, select **Configure Site Components**, and then select **Software Update Point**.</span></span> <span data-ttu-id="9f60e-130">Ou cliquez avec le bouton droit sur le site, puis sélectionnez **configurer**le  >  **point de mise à jour logicielle**des composants de site.</span><span class="sxs-lookup"><span data-stu-id="9f60e-130">Or, right-click the site, and then select **Configure Site Components** > **Software Update Point**.</span></span>
1. <span data-ttu-id="9f60e-131">Sous l’onglet **classifications** , activez la case à cocher **inclure les pilotes de surface Microsoft et les mises à jour du microprogramme** .</span><span class="sxs-lookup"><span data-stu-id="9f60e-131">On the **Classifications** tab, select the **Include Microsoft Surface drivers and firmware updates** check box.</span></span>

   ![Propriétés du composant du point de mise à jour logicielle](images/manage-surface-driver-updates-1.png)

1. <span data-ttu-id="9f60e-133">Lorsque le message d’avertissement suivant apparaît, sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="9f60e-133">When you're prompted by the following warning message, select **OK**.</span></span>

   ![Configuration Manager](images/manage-surface-driver-updates-2.png)

1. <span data-ttu-id="9f60e-135">Dans l’onglet produits, sélectionnez les produits que vous voulez mettre à jour, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="9f60e-135">On the Products tab, select the products that you want to update, and then select **OK**.</span></span>

   <span data-ttu-id="9f60e-136">La plupart des pilotes appartiennent aux groupes de produits suivants:</span><span class="sxs-lookup"><span data-stu-id="9f60e-136">Most drivers belong to the following product groups:</span></span>

   - <span data-ttu-id="9f60e-137">Pilotes Windows 10 et versions ultérieures</span><span class="sxs-lookup"><span data-stu-id="9f60e-137">Windows 10 and later version drivers</span></span>
   - <span data-ttu-id="9f60e-138">Mise à niveau vers Windows 10 et versions ultérieures & de pilotes de service</span><span class="sxs-lookup"><span data-stu-id="9f60e-138">Windows 10 and later Upgrade & Servicing Drivers</span></span>
   - <span data-ttu-id="9f60e-139">Mise à jour anniversaire Windows 10 et pilotes de maintenance ultérieures</span><span class="sxs-lookup"><span data-stu-id="9f60e-139">Windows 10 Anniversary Update and Later Servicing Drivers</span></span>
   - <span data-ttu-id="9f60e-140">Mise à jour anniversaire de Windows 10 et mise à niveau ultérieure & les pilotes de maintenance</span><span class="sxs-lookup"><span data-stu-id="9f60e-140">Windows 10 Anniversary Update and Later Upgrade & Servicing Drivers</span></span>
   - <span data-ttu-id="9f60e-141">Pilotes de maintenance de Windows 10 Creators Update et version ultérieure</span><span class="sxs-lookup"><span data-stu-id="9f60e-141">Windows 10 Creators Update and Later Servicing Drivers</span></span>
   - <span data-ttu-id="9f60e-142">Mise à jour de Windows 10 Creators Update et version ultérieure & les pilotes de maintenance</span><span class="sxs-lookup"><span data-stu-id="9f60e-142">Windows 10 Creators Update and Later Upgrade & Servicing Drivers</span></span>
   - <span data-ttu-id="9f60e-143">Windows 10 automne Creators Update et les pilotes de maintenance ultérieurs</span><span class="sxs-lookup"><span data-stu-id="9f60e-143">Windows 10 Fall Creators Update and Later Servicing Drivers</span></span>
   - <span data-ttu-id="9f60e-144">Windows 10 automne créateurs mise à jour et mise à niveau ultérieure & les pilotes de maintenance</span><span class="sxs-lookup"><span data-stu-id="9f60e-144">Windows 10 Fall Creators Update and Later Upgrade & Servicing Drivers</span></span>
   - <span data-ttu-id="9f60e-145">Pilotes de service Windows 10 S et versions ultérieures</span><span class="sxs-lookup"><span data-stu-id="9f60e-145">Windows 10 S and Later Servicing Drivers</span></span>
   - <span data-ttu-id="9f60e-146">Versions 1709 et ultérieures de Windows 10 S avec les pilotes de maintenance</span><span class="sxs-lookup"><span data-stu-id="9f60e-146">Windows 10 S Version 1709 and Later Servicing Drivers for testing</span></span>
   - <span data-ttu-id="9f60e-147">Mise à niveau vers la version 1709 de Windows 10 et les versions ultérieures & pilotes de maintenance pour le test</span><span class="sxs-lookup"><span data-stu-id="9f60e-147">Windows 10 S Version 1709 and Later Upgrade & Servicing Drivers for testing</span></span>

   > [!NOTE]
   > <span data-ttu-id="9f60e-148">La plupart des pilotes de surface appartiennent à plusieurs groupes de produits Windows 10.</span><span class="sxs-lookup"><span data-stu-id="9f60e-148">Most Surface drivers belong to multiple Windows 10 product groups.</span></span> <span data-ttu-id="9f60e-149">Il est possible que vous n’ayez pas besoin de sélectionner tous les produits répertoriés ici.</span><span class="sxs-lookup"><span data-stu-id="9f60e-149">You may not have to select all the products that are listed here.</span></span> <span data-ttu-id="9f60e-150">Pour réduire le nombre de produits qui remplissent votre catalogue de mise à jour, nous vous recommandons de sélectionner uniquement les produits requis par votre environnement pour la synchronisation.</span><span class="sxs-lookup"><span data-stu-id="9f60e-150">To help reduce the number of products that populate your Update Catalog, we recommend that you select only the products that are required by your environment for synchronization.</span></span>

## <span data-ttu-id="9f60e-151">Vérification de la configuration</span><span class="sxs-lookup"><span data-stu-id="9f60e-151">Verifying the configuration</span></span>

<span data-ttu-id="9f60e-152">Pour vérifier que le SUP est configuré correctement, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="9f60e-152">To verify that the SUP is configured correctly, follow these steps:</span></span>

1. <span data-ttu-id="9f60e-153">Ouvrez WsyncMgr. log, puis recherchez l’entrée suivante:</span><span class="sxs-lookup"><span data-stu-id="9f60e-153">Open WsyncMgr.log, and then look for the following entry:</span></span>

   ```console
   Surface Drivers can be supported in this hierarchy since all SUPs are on Windows Server 2016, WCM SCF property Sync Catalog Drivers is set.

   Sync Catalog Drivers SCF value is set to : 1
   ```

   <span data-ttu-id="9f60e-154">Si l’une des entrées suivantes est enregistrée dans WsyncMgr. log, revérifier l’étape 4 de la section précédente:</span><span class="sxs-lookup"><span data-stu-id="9f60e-154">If either of the following entries is logged in WsyncMgr.log, recheck step 4 in the previous section:</span></span>

   ```console
   Sync Surface Drivers option is not set

   Sync Catalog Drivers SCF value is set to : 0
   ```

1. <span data-ttu-id="9f60e-155">Ouvrez WCM. log, puis recherchez une entrée qui ressemble à ce qui suit:</span><span class="sxs-lookup"><span data-stu-id="9f60e-155">Open WCM.log, and then look for an entry that resembles the following:</span></span>

   ![Paramètres de WCM. log](images/manage-surface-driver-updates-3.png)

   <span data-ttu-id="9f60e-157">Cette entrée est un élément XML qui recense chaque groupe de produits et classification actuellement synchronisé par votre serveur SUP.</span><span class="sxs-lookup"><span data-stu-id="9f60e-157">This entry is an XML element that lists every product group and classification that's currently synchronized by your SUP server.</span></span> <span data-ttu-id="9f60e-158">Par exemple, il se peut que vous voyiez une entrée semblable à ce qui suit:</span><span class="sxs-lookup"><span data-stu-id="9f60e-158">For example, you might see an entry that resembles the following:</span></span>

   ```xml
   <Categories>
       <Category Id="Product:05eebf61-148b-43cf-80da-1c99ab0b8699"><![CDATA[Windows 10 and later drivers]]></Category>
       <Category Id="Product:06da2f0c-7937-4e28-b46c-a37317eade73"><![CDATA[Windows 10 Creators Update and Later Upgrade & Servicing Drivers]]></Category>
       <Category Id="Product:c1006636-eab4-4b0b-b1b0-d50282c0377e"><![CDATA[Windows 10 S and Later Servicing Drivers]]></Category>
   </Categories>
   ```

   <span data-ttu-id="9f60e-159">Si vous ne trouvez pas les produits sélectionnés à l’étape 6 de la section précédente, vérifiez si les paramètres SUP sont enregistrés.</span><span class="sxs-lookup"><span data-stu-id="9f60e-159">If you can't find the products that you selected in step 6 in the previous section, double-check whether the SUP settings are saved.</span></span>

   <span data-ttu-id="9f60e-160">Vous pouvez également attendre la fin de la synchronisation suivante, puis vérifier si les mises à jour de pilote de surface et de microprogramme apparaissent dans les mises à jour logicielles dans la console Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="9f60e-160">You can also wait until the next synchronization finishes, and then check whether the Surface driver and firmware updates are listed in Software Updates in the Configuration Manager console.</span></span> <span data-ttu-id="9f60e-161">Par exemple, la console peut afficher les informations suivantes.</span><span class="sxs-lookup"><span data-stu-id="9f60e-161">For example, the console might display the following information.</span></span>

   ![Tous les résultats de la recherche mises à jour logicielles](images/manage-surface-driver-updates-4.png)

## <span data-ttu-id="9f60e-163">Synchronisation manuelle</span><span class="sxs-lookup"><span data-stu-id="9f60e-163">Manual synchronization</span></span>

<span data-ttu-id="9f60e-164">Si vous ne voulez pas attendre la prochaine synchronisation, procédez comme suit pour démarrer une synchronisation:</span><span class="sxs-lookup"><span data-stu-id="9f60e-164">If you don't want to wait until the next synchronization, follow these steps to start a synchronization:</span></span>

1. <span data-ttu-id="9f60e-165">Dans la console Configuration Manager, accédez à **Software Library**  >  **vue d’ensemble**des bibliothèques logicielles  >  **mises à jour**de  >  **toutes les mises à jour logicielles**.</span><span class="sxs-lookup"><span data-stu-id="9f60e-165">In the Configuration Manager console, go to **Software Library** > **Overview** > **Software Updates** > **All Software Updates**.</span></span>
1. <span data-ttu-id="9f60e-166">Dans le ruban, sélectionnez **synchroniser les mises à jour logicielles**.</span><span class="sxs-lookup"><span data-stu-id="9f60e-166">On the ribbon, select **Synchronize Software Updates**.</span></span> <span data-ttu-id="9f60e-167">Ou cliquez avec le bouton droit sur **toutes les mises à jour logicielles**, puis sélectionnez **synchroniser la mise à jour logicielle**.</span><span class="sxs-lookup"><span data-stu-id="9f60e-167">Or, right-click **All Software Update**, and then select **Synchronize Software Update**.</span></span>
1. <span data-ttu-id="9f60e-168">Pour surveiller la progression de la synchronisation, recherchez les entrées suivantes dans WsyncMgr. log:</span><span class="sxs-lookup"><span data-stu-id="9f60e-168">Monitor the synchronization progress by looking for the following entries in WsyncMgr.log:</span></span>

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

## <span data-ttu-id="9f60e-169">Déploiement de mises à jour de microprogrammes et de pilotes de surface</span><span class="sxs-lookup"><span data-stu-id="9f60e-169">Deploying Surface firmware and driver updates</span></span>

<span data-ttu-id="9f60e-170">Vous pouvez déployer des mises à jour de microprogrammes et de pilotes de surface de la même manière que lors du déploiement d’autres mises à jour.</span><span class="sxs-lookup"><span data-stu-id="9f60e-170">You can deploy Surface firmware and driver updates in the same manner as you deploy other updates.</span></span>

<span data-ttu-id="9f60e-171">Pour plus d’informations sur le déploiement, voir [System Center 2012 Configuration Manager-part7: mises à jour logicielles (déploiement)](https://blogs.technet.microsoft.com/elie/2012/05/25/system-center-2012-configuration-managerpart7-software-updates-deploy/).</span><span class="sxs-lookup"><span data-stu-id="9f60e-171">For more information about deployment, see [System Center 2012 Configuration Manager–Part7: Software Updates (Deploy)](https://blogs.technet.microsoft.com/elie/2012/05/25/system-center-2012-configuration-managerpart7-software-updates-deploy/).</span></span>

## <span data-ttu-id="9f60e-172">Forum Aux Questions (FAQ)</span><span class="sxs-lookup"><span data-stu-id="9f60e-172">Frequently asked questions (FAQ)</span></span>

**<span data-ttu-id="9f60e-173">Après avoir suivi les étapes décrites dans cet article, les pilotes de surface ne sont toujours pas synchronisés.</span><span class="sxs-lookup"><span data-stu-id="9f60e-173">After I follow the steps in this article, my Surface drivers are still not synchronized.</span></span> <span data-ttu-id="9f60e-174">Pourquoi?</span><span class="sxs-lookup"><span data-stu-id="9f60e-174">Why?</span></span>**

<span data-ttu-id="9f60e-175">Si vous effectuez une synchronisation à partir d’un serveur Windows Server Update Services (WSUS) en amont au lieu de Microsoft Update, assurez-vous que le serveur WSUS en amont est configuré pour prendre en charge et synchroniser les mises à jour de pilote surface.</span><span class="sxs-lookup"><span data-stu-id="9f60e-175">If you synchronize from an upstream Windows Server Update Services (WSUS) server, instead of Microsoft Update, make sure that the upstream WSUS server is configured to support and synchronize Surface driver updates.</span></span> <span data-ttu-id="9f60e-176">Tous les serveurs en aval sont limités aux mises à jour présentes dans la base de données du serveur WSUS en amont.</span><span class="sxs-lookup"><span data-stu-id="9f60e-176">All downstream servers are limited to updates that are present in the upstream WSUS server database.</span></span>

<span data-ttu-id="9f60e-177">Il existe plusieurs mises à jour de 68 000 classées comme pilotes dans WSUS.</span><span class="sxs-lookup"><span data-stu-id="9f60e-177">There are more than 68,000 updates that are classified as drivers in WSUS.</span></span> <span data-ttu-id="9f60e-178">Pour empêcher les pilotes non liés à la surface d’être synchronisés avec la Configuration Manager, Microsoft filtre la synchronisation du pilote sur une liste verte.</span><span class="sxs-lookup"><span data-stu-id="9f60e-178">To prevent non-Surface related drivers from synchronizing to Configuration Manager, Microsoft filters driver synchronization against an allow list.</span></span> <span data-ttu-id="9f60e-179">Une fois la nouvelle liste verte publiée et incorporée dans Configuration Manager, les nouveaux pilotes sont ajoutés à la console à la suite de la synchronisation suivante.</span><span class="sxs-lookup"><span data-stu-id="9f60e-179">After the new allow list is published and incorporated into Configuration Manager, the new drivers are added to the console following the next synchronization.</span></span> <span data-ttu-id="9f60e-180">Microsoft a pour but de télécharger les pilotes de surface ajoutés à la liste verte chaque mois en fonction de leurs mises à jour mensuelles, afin de les rendre disponibles pour la synchronisation avec Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="9f60e-180">Microsoft aims to get the Surface drivers added to the allow list each month in alignment with monthly update releases to make them available for synchronization to Configuration Manager.</span></span>

<span data-ttu-id="9f60e-181">Si votre environnement Configuration Manager est hors connexion, une nouvelle liste verte est importée chaque fois que vous importez des [mises à jour de maintenance](https://docs.microsoft.com/mem/configmgr/core/servers/manage/use-the-service-connection-tool) dans Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="9f60e-181">If your Configuration Manager environment is offline, a new allow list is imported every time that you import [servicing updates](https://docs.microsoft.com/mem/configmgr/core/servers/manage/use-the-service-connection-tool) to Configuration Manager.</span></span> <span data-ttu-id="9f60e-182">Vous devrez également importer un [nouveau catalogue WSUS](https://docs.microsoft.com/mem/configmgr/sum/get-started/synchronize-software-updates-disconnected) qui contient les pilotes avant que les mises à jour ne soient affichées dans la console Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="9f60e-182">You will also have to import a [new WSUS catalog](https://docs.microsoft.com/mem/configmgr/sum/get-started/synchronize-software-updates-disconnected) that contains the drivers before the updates are displayed in the Configuration Manager console.</span></span> <span data-ttu-id="9f60e-183">Dans la mesure où un environnement WSUS autonome comporte plus de pilotes qu’un SUP Configuration Manager, nous vous recommandons de créer un environnement Configuration Manager doté de fonctionnalités en ligne et de le configurer pour synchroniser les pilotes de surface.</span><span class="sxs-lookup"><span data-stu-id="9f60e-183">Because a standalone WSUS environment contains more drivers than a Configuration Manager SUP, we recommend that you establish a Configuration Manager environment that has online capabilities, and that you configure it to synchronize Surface drivers.</span></span> <span data-ttu-id="9f60e-184">Cela fournit une plus petite exportation WSUS qui ressemble étroitement à l’environnement hors connexion.</span><span class="sxs-lookup"><span data-stu-id="9f60e-184">This provides a smaller WSUS export that closely resembles the offline environment.</span></span>

<span data-ttu-id="9f60e-185">Si votre environnement Configuration Manager est connecté et en mesure de détecter de nouvelles mises à jour, vous recevrez automatiquement les mises à jour de la liste.</span><span class="sxs-lookup"><span data-stu-id="9f60e-185">If your Configuration Manager environment is online and able to detect new updates, you will receive updates to the list automatically.</span></span> <span data-ttu-id="9f60e-186">Si vous ne voyez pas les pilotes attendus, consultez les fichiers WCM. log et WsyncMgr. log pour les échecs de synchronisation.</span><span class="sxs-lookup"><span data-stu-id="9f60e-186">If you don’t see the expected drivers, please review the WCM.log and WsyncMgr.log files for any synchronization failures.</span></span>

**<span data-ttu-id="9f60e-187">Mon environnement Configuration Manager est hors connexion.</span><span class="sxs-lookup"><span data-stu-id="9f60e-187">My Configuration Manager environment is offline.</span></span> <span data-ttu-id="9f60e-188">Puis-je importer manuellement des pilotes de surface dans WSUS?</span><span class="sxs-lookup"><span data-stu-id="9f60e-188">Can I manually import Surface drivers into WSUS?</span></span>**

<span data-ttu-id="9f60e-189">Non.</span><span class="sxs-lookup"><span data-stu-id="9f60e-189">No.</span></span> <span data-ttu-id="9f60e-190">Même si la mise à jour est importée dans WSUS, la mise à jour ne sera pas importée dans la console Configuration Manager à des fins de déploiement, si elle ne figure pas dans la liste verte.</span><span class="sxs-lookup"><span data-stu-id="9f60e-190">Even if the update is imported into WSUS, the update won't be imported into the Configuration Manager console for deployment if it isn't listed in the allow list.</span></span> <span data-ttu-id="9f60e-191">Vous devez utiliser l' [outil de connexion de service](https://docs.microsoft.com/mem/configmgr/core/servers/manage/use-the-service-connection-tool) pour importer les mises à jour de maintenance dans Configuration Manager afin de mettre à jour la liste verte.</span><span class="sxs-lookup"><span data-stu-id="9f60e-191">You must use the [Service Connection Tool](https://docs.microsoft.com/mem/configmgr/core/servers/manage/use-the-service-connection-tool) to import servicing updates to Configuration Manager to update the allow list.</span></span>

**<span data-ttu-id="9f60e-192">Quelles sont les méthodes qui s’offrent à vous pour déployer les mises à jour de pilote et de microprogramme de surface?</span><span class="sxs-lookup"><span data-stu-id="9f60e-192">What alternative methods do I have to deploy Surface driver and firmware updates?</span></span>**

<span data-ttu-id="9f60e-193">Pour plus d’informations sur le déploiement des mises à jour de pilote de surface et de microprogramme par le biais de canaux secondaires, voir [gérer les mises à jour de pilote de surface et de microprogramme](manage-surface-driver-and-firmware-updates.md).</span><span class="sxs-lookup"><span data-stu-id="9f60e-193">For information about how to deploy Surface driver and firmware updates through alternative channels, see [Manage Surface driver and firmware updates](manage-surface-driver-and-firmware-updates.md).</span></span> <span data-ttu-id="9f60e-194">Pour télécharger le fichier. msi ou. exe et le déployer par le biais de canaux de déploiement de logiciels traditionnels, voir [maintenir le microprogramme de surface mis à jour avec Configuration Manager](https://docs.microsoft.com/archive/blogs/thejoncallahan/keeping-surface-firmware-updated-with-configuration-manager).</span><span class="sxs-lookup"><span data-stu-id="9f60e-194">If you want to download the .msi or .exe file, and then deploy through traditional software deployment channels, see [Keeping Surface Firmware Updated with Configuration Manager](https://docs.microsoft.com/archive/blogs/thejoncallahan/keeping-surface-firmware-updated-with-configuration-manager).</span></span>

## <span data-ttu-id="9f60e-195">Informations supplémentaires</span><span class="sxs-lookup"><span data-stu-id="9f60e-195">Additional Information</span></span>

<span data-ttu-id="9f60e-196">Pour plus d’informations sur les mises à jour de pilote surface et de microprogramme, voir les articles suivants:</span><span class="sxs-lookup"><span data-stu-id="9f60e-196">For more information about Surface driver and firmware updates, see the following articles:</span></span>

- [<span data-ttu-id="9f60e-197">Gérer les mises à jour du microprogramme et des pilotesSurface</span><span class="sxs-lookup"><span data-stu-id="9f60e-197">Manage Surface driver and firmware updates</span></span>](manage-surface-driver-and-firmware-updates.md)
- [<span data-ttu-id="9f60e-198">Considérations relatives à Surface et à System Center Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="9f60e-198">Considerations for Surface and System Center Configuration Manager</span></span>](considerations-for-surface-and-system-center-configuration-manager.md)
