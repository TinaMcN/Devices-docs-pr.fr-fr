---
title: Utiliser le gestionnaire de configuration de point de terminaison Microsoft pour gérer les appareils avec SEMM (surface)
description: Découvrez comment gérer le mode de gestion de l’entreprise Microsoft surface (SEMM) avec Endpoint Configuration Manager.
keywords: inscription, mise à jour, scripts, paramètres
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: hachidan
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
ms.date: 10/13/2020
ms.openlocfilehash: bfd10df3bb7a7dd031c1719d4191ffc46418c4e3
ms.sourcegitcommit: 30c1eb469610dfd2ad9169c154ca07e565240fdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/14/2020
ms.locfileid: "11117850"
---
# <span data-ttu-id="af0f2-104">Utilisez Microsoft Endpoint Configuration Manager pour gérer les appareils avec SEMM</span><span class="sxs-lookup"><span data-stu-id="af0f2-104">Use Microsoft Endpoint Configuration Manager to manage devices with SEMM</span></span>

<span data-ttu-id="af0f2-105">La fonctionnalité Microsoft surface Management Mode (SEMM) des appareils surface UEFI permet aux administrateurs de gérer et de sécuriser la configuration des paramètres de surface UEFI.</span><span class="sxs-lookup"><span data-stu-id="af0f2-105">The Microsoft Surface Enterprise Management Mode (SEMM) feature of Surface UEFI devices lets administrators manage and help secure the configuration of Surface UEFI settings.</span></span> <span data-ttu-id="af0f2-106">Pour la plupart des organisations, ce processus est réalisé en créant des packages Windows Installer (. msi) à l’aide de l’outil de configuration de Microsoft surface UEFI.</span><span class="sxs-lookup"><span data-stu-id="af0f2-106">For most organizations, this process is accomplished by creating Windows Installer (.msi) packages with the Microsoft Surface UEFI Configurator tool.</span></span> <span data-ttu-id="af0f2-107">Ces packages sont ensuite exécutés ou déployés sur les appareils surface du client pour inscrire les appareils dans SEMM et mettre à jour la configuration des paramètres de surface UEFI.</span><span class="sxs-lookup"><span data-stu-id="af0f2-107">These packages are then run or deployed to the client Surface devices to enroll the devices in SEMM and to update the Surface UEFI settings configuration.</span></span>

<span data-ttu-id="af0f2-108">Pour les organisations qui utilisent Microsoft Endpoint Configuration Manager, vous pouvez utiliser le processus MSI Microsoft surface. Configurator pour déployer et administrer SEMM.</span><span class="sxs-lookup"><span data-stu-id="af0f2-108">For organizations with Microsoft Endpoint Configuration Manager there is an alternative to using the Microsoft Surface UEFI Configurator .msi process to deploy and administer SEMM.</span></span> <span data-ttu-id="af0f2-109">Le Gestionnaire Microsoft surface UEFI est un programme d’installation léger qui rend les assemblys requis pour la gestion SEMM disponible sur un appareil.</span><span class="sxs-lookup"><span data-stu-id="af0f2-109">Microsoft Surface UEFI Manager is a lightweight installer that makes required assemblies for SEMM management available on a device.</span></span> <span data-ttu-id="af0f2-110">En installant ces assemblys avec le Gestionnaire Microsoft surface UEFI sur un client géré, SEMM peut être administré par Configuration Manager avec des scripts PowerShell, déployés sous la forme d’applications.</span><span class="sxs-lookup"><span data-stu-id="af0f2-110">By installing these assemblies with Microsoft Surface UEFI Manager on a managed client, SEMM can be administered by Configuration Manager with PowerShell scripts, deployed as applications.</span></span> <span data-ttu-id="af0f2-111">Dans le cadre de ce processus, la gestion de SEMM est effectuée dans Configuration Manager, ce qui vous permet d’éviter d’avoir recours à l’outil de Configurateur UEFI extérieur de Microsoft surface.</span><span class="sxs-lookup"><span data-stu-id="af0f2-111">With this process, SEMM management is performed within Configuration Manager, which eliminates the need for the external Microsoft Surface UEFI Configurator tool.</span></span>

> [!Note]
> <span data-ttu-id="af0f2-112">Bien que la procédure décrite dans cet article puisse fonctionner avec des versions antérieures du gestionnaire de configuration de point de terminaison ou avec d’autres solutions de gestion tierces, la gestion de SEMM avec Microsoft surface UEFI Manager et PowerShell est uniquement prise en charge avec la branche actuelle du gestionnaire de configuration de point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="af0f2-112">Although the process described in this article may work with earlier versions of Endpoint Configuration Manager or with other third-party management solutions, management of SEMM with Microsoft Surface UEFI Manager and PowerShell is supported only with the Current Branch of Endpoint Configuration Manager.</span></span>

#### <span data-ttu-id="af0f2-113">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="af0f2-113">Prerequisites</span></span>

<span data-ttu-id="af0f2-114">Avant de commencer la procédure décrite dans cet article, vous devez vous familiariser avec les technologies et les outils suivants:</span><span class="sxs-lookup"><span data-stu-id="af0f2-114">Before you begin the process outlined in this article, familiarize yourself with the following technologies and tools:</span></span>

* [<span data-ttu-id="af0f2-115">Surface UEFI</span><span class="sxs-lookup"><span data-stu-id="af0f2-115">Surface UEFI</span></span>](https://technet.microsoft.com/itpro/surface/manage-surface-uefi-settings)
* [<span data-ttu-id="af0f2-116">SurfaceEnterpriseManagementMode (SEMM)</span><span class="sxs-lookup"><span data-stu-id="af0f2-116">Surface Enterprise Management Mode (SEMM)</span></span>](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode)
* [<span data-ttu-id="af0f2-117">Script PowerShell</span><span class="sxs-lookup"><span data-stu-id="af0f2-117">PowerShell scripting</span></span>](https://technet.microsoft.com/scriptcenter/dd742419)
* [<span data-ttu-id="af0f2-118">Déploiement d’applications System Center Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="af0f2-118">System Center Configuration Manager application deployment</span></span>](https://docs.microsoft.com/sccm/apps/deploy-use/deploy-applications)
* <span data-ttu-id="af0f2-119">Gestion des certificats</span><span class="sxs-lookup"><span data-stu-id="af0f2-119">Certificate management</span></span>

> [!Note]
> <span data-ttu-id="af0f2-120">Vous aurez également accès au certificat que vous envisagez d’utiliser pour sécuriser SEMM.</span><span class="sxs-lookup"><span data-stu-id="af0f2-120">You will also need access to the certificate that you intend to use to secure SEMM.</span></span> <span data-ttu-id="af0f2-121">Pour plus d’informations sur la configuration requise pour ce certificat, voir [exigences de certificat en mode de gestion de surface d’entreprise](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements).</span><span class="sxs-lookup"><span data-stu-id="af0f2-121">For details about the requirements for this certificate, see [Surface Enterprise Management Mode certificate requirements](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements).</span></span>
> 
> <span data-ttu-id="af0f2-122">Il est très important que ce certificat soit maintenu dans un emplacement sûr et correctement sauvegardé.</span><span class="sxs-lookup"><span data-stu-id="af0f2-122">It is very important that this certificate be kept in a safe location and properly backed up.</span></span> <span data-ttu-id="af0f2-123">Si ce certificat est perdu ou inutilisable, il n’est pas possible de réinitialiser surface UEFI, de modifier les paramètres de surface gérée ou de supprimer SEMM d’un appareil surface inscrit.</span><span class="sxs-lookup"><span data-stu-id="af0f2-123">If this certificate becomes lost or unusable, it is not possible to reset Surface UEFI, change managed Surface UEFI settings, or remove SEMM from an enrolled Surface device.</span></span>

#### <span data-ttu-id="af0f2-124">Télécharger le Gestionnaire Microsoft surface UEFI</span><span class="sxs-lookup"><span data-stu-id="af0f2-124">Download Microsoft Surface UEFI Manager</span></span>

<span data-ttu-id="af0f2-125">La gestion de SEMM avec Configuration Manager nécessite l’installation de Microsoft surface UEFI Manager sur chaque périphérique surface du client.</span><span class="sxs-lookup"><span data-stu-id="af0f2-125">Management of SEMM with Configuration Manager requires the installation of Microsoft Surface UEFI Manager on each client Surface device.</span></span> <span data-ttu-id="af0f2-126">Vous pouvez télécharger le Gestionnaire Microsoft surface UEFI (SurfaceUEFIManager.msi) à partir de la page [Outils surface pour cette application](https://www.microsoft.com/download/details.aspx?id=46703) dans le centre de téléchargement Microsoft.</span><span class="sxs-lookup"><span data-stu-id="af0f2-126">You can download Microsoft Surface UEFI Manager (SurfaceUEFIManager.msi) from the [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) page on the Microsoft Download Center.</span></span>

#### <span data-ttu-id="af0f2-127">Télécharger les scripts SEMM pour Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="af0f2-127">Download SEMM scripts for Configuration Manager</span></span>

<span data-ttu-id="af0f2-128">Après avoir installé le Gestionnaire Microsoft surface UEFI sur le périphérique surface du client, SEMM est déployé et géré avec des scripts PowerShell.</span><span class="sxs-lookup"><span data-stu-id="af0f2-128">After Microsoft Surface UEFI Manager is installed on the client Surface device, SEMM is deployed and managed with PowerShell scripts.</span></span> <span data-ttu-id="af0f2-129">Vous pouvez télécharger des exemples de [scripts de gestion de SEMM](https://www.microsoft.com/download/details.aspx?id=46703) à partir du centre de téléchargement.</span><span class="sxs-lookup"><span data-stu-id="af0f2-129">You can download samples of the [SEMM management scripts](https://www.microsoft.com/download/details.aspx?id=46703) from the Download Center.</span></span>

## <span data-ttu-id="af0f2-130">Déployer le Gestionnaire Microsoft surface UEFI</span><span class="sxs-lookup"><span data-stu-id="af0f2-130">Deploy Microsoft Surface UEFI Manager</span></span>

<span data-ttu-id="af0f2-131">Le déploiement de Microsoft surface UEFI Manager est un déploiement d’application classique.</span><span class="sxs-lookup"><span data-stu-id="af0f2-131">Deployment of Microsoft Surface UEFI Manager is a typical application deployment.</span></span> <span data-ttu-id="af0f2-132">Le fichier du programme d’installation du Gestionnaire Microsoft surface UEFI est un fichier Windows Installer standard que vous pouvez installer à l’aide de l' [option silence standard](https://msdn.microsoft.com/library/windows/desktop/aa367988).</span><span class="sxs-lookup"><span data-stu-id="af0f2-132">The Microsoft Surface UEFI Manager installer file is a standard Windows Installer file that you can install with the [standard quiet option](https://msdn.microsoft.com/library/windows/desktop/aa367988).</span></span>

<span data-ttu-id="af0f2-133">La commande d’installation du Gestionnaire Microsoft surface UEFI est la suivante:</span><span class="sxs-lookup"><span data-stu-id="af0f2-133">The command to install Microsoft Surface UEFI Manager is as follows.</span></span>

`msiexec /i "SurfaceUEFIManagerSetup.msi" /q`

<span data-ttu-id="af0f2-134">La commande permettant de désinstaller le Gestionnaire Microsoft surface UEFI est la suivante.</span><span class="sxs-lookup"><span data-stu-id="af0f2-134">The command to uninstall Microsoft Surface UEFI Manager is as follows.</span></span>

`msiexec /x {541DA890-1AEB-446D-B3FD-D5B3BB18F9AF} /q`

<span data-ttu-id="af0f2-135">Pour créer une nouvelle application et la déployer dans une collection qui contient vos périphériques surface, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="af0f2-135">To create a new application and deploy it to a collection that contains your Surface devices, perform the following steps:</span></span>

1. <span data-ttu-id="af0f2-136">Ouvrez la console Configuration Manager à partir de l’écran d' **Accueil** ou du menu **Démarrer** .</span><span class="sxs-lookup"><span data-stu-id="af0f2-136">Open Configuration Manager Console from the **Start** screen or **Start** menu.</span></span>
2. <span data-ttu-id="af0f2-137">Sélectionnez **bibliothèque de logiciels** dans le coin inférieur gauche de la fenêtre.</span><span class="sxs-lookup"><span data-stu-id="af0f2-137">Select **Software Library** in the bottom left corner of the window.</span></span>
3. <span data-ttu-id="af0f2-138">Développez le nœud **gestion des applications** de la bibliothèque logicielle, puis sélectionnez **applications**.</span><span class="sxs-lookup"><span data-stu-id="af0f2-138">Expand the **Application Management** node of the Software Library, and then select **Applications**.</span></span>
4. <span data-ttu-id="af0f2-139">Sélectionnez le bouton **créer une application** sous l’onglet **Accueil** en haut de la fenêtre.</span><span class="sxs-lookup"><span data-stu-id="af0f2-139">Select the **Create Application** button under the **Home** tab at the top of the window.</span></span> <span data-ttu-id="af0f2-140">Cette opération démarre l’Assistant Création d’une application.</span><span class="sxs-lookup"><span data-stu-id="af0f2-140">This starts the Create Application Wizard.</span></span>
5. <span data-ttu-id="af0f2-141">L’Assistant Création d’une application présente les étapes suivantes:</span><span class="sxs-lookup"><span data-stu-id="af0f2-141">The Create Application Wizard presents a series of steps:</span></span>

   * <span data-ttu-id="af0f2-142">**Général** : l’option **détecter automatiquement les informations sur cette application à partir des fichiers d’installation** est activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="af0f2-142">**General** – The **Automatically detect information about this application from installation files** option is selected by default.</span></span> <span data-ttu-id="af0f2-143">Dans le champ **type** , le **programme d’installation Windows (fichier. msi)** est également sélectionné par défaut.</span><span class="sxs-lookup"><span data-stu-id="af0f2-143">In the **Type** field, **Windows Installer (.msi file)** is also selected by default.</span></span> <span data-ttu-id="af0f2-144">Sélectionnez **Parcourir** pour accéder à **SurfaceUEFIManagerSetup.msi**, puis sélectionnez **suivant**.</span><span class="sxs-lookup"><span data-stu-id="af0f2-144">Select **Browse** to navigate to and select **SurfaceUEFIManagerSetup.msi**, and then select **Next**.</span></span>
   
      > [!Note]
      > <span data-ttu-id="af0f2-145">L’emplacement de SurfaceUEFIManagerSetup.msi doit se trouver sur un partage réseau et être placé dans un dossier qui ne contient pas d’autres fichiers.</span><span class="sxs-lookup"><span data-stu-id="af0f2-145">The location of SurfaceUEFIManagerSetup.msi must be on a network share and located in a folder that contains no other files.</span></span> <span data-ttu-id="af0f2-146">Un emplacement de fichier local ne peut pas être utilisé.</span><span class="sxs-lookup"><span data-stu-id="af0f2-146">A local file location cannot be used.</span></span>

   * <span data-ttu-id="af0f2-147">**Importer des informations** : l’Assistant Création d’application analysera le fichier. msi et lira le nom de l' **application** et le **Code du produit**.</span><span class="sxs-lookup"><span data-stu-id="af0f2-147">**Import Information** – The Create Application Wizard will parse the .msi file and read the **Application Name** and **Product Code**.</span></span> <span data-ttu-id="af0f2-148">SurfaceUEFIManagerSetup.msi doit être répertoriée en tant que seul fichier sous les **fichiers de contenu**de ligne, comme illustré dans la figure 1.</span><span class="sxs-lookup"><span data-stu-id="af0f2-148">SurfaceUEFIManagerSetup.msi should be listed as the only file under the line **Content Files**, as shown in Figure 1.</span></span> <span data-ttu-id="af0f2-149">Sélectionnez **Next (suivant** ) pour continuer.</span><span class="sxs-lookup"><span data-stu-id="af0f2-149">Select **Next** to proceed.</span></span>

      ![Les informations de configuration du gestionnaire de surface UEFI sont automatiquement analysées](images/config-mgr-semm-fig1.png "Information from Surface UEFI Manager setup is automatically parsed")

      *<span data-ttu-id="af0f2-151">Figure1.</span><span class="sxs-lookup"><span data-stu-id="af0f2-151">Figure 1.</span></span> <span data-ttu-id="af0f2-152">Les informations du programme d’installation du Gestionnaire Microsoft surface UEFI sont automatiquement analysées.</span><span class="sxs-lookup"><span data-stu-id="af0f2-152">Information from Microsoft Surface UEFI Manager setup is automatically parsed</span></span>*

   * <span data-ttu-id="af0f2-153">**Informations générales** : vous pouvez modifier le nom de l’application et les informations relatives à l’éditeur et à la version, ou ajouter des commentaires sur cette page.</span><span class="sxs-lookup"><span data-stu-id="af0f2-153">**General Information** – You can modify the name of the application and information about the publisher and version, or add comments on this page.</span></span> <span data-ttu-id="af0f2-154">La commande d’installation de Microsoft surface UEFI Manager s’affiche dans le champ programme d’installation.</span><span class="sxs-lookup"><span data-stu-id="af0f2-154">The installation command for Microsoft Surface UEFI Manager is displayed in the Installation Program field.</span></span> <span data-ttu-id="af0f2-155">Le comportement d’installation par défaut de l’installation pour le système permet à Microsoft surface UEFI Manager d’installer les assemblys requis pour SEMM, même si un utilisateur n’est pas connecté à l’appareil surface.</span><span class="sxs-lookup"><span data-stu-id="af0f2-155">The default installation behavior of Install for system will allow Microsoft Surface UEFI Manager to install the required assemblies for SEMM even if a user is not logged on to the Surface device.</span></span> <span data-ttu-id="af0f2-156">Sélectionnez **Next (suivant** ) pour continuer.</span><span class="sxs-lookup"><span data-stu-id="af0f2-156">Select **Next** to proceed.</span></span>
   * <span data-ttu-id="af0f2-157">**Résumé** : les informations analysées lors de l’étape d' **importation des informations** et vos sélections à partir de l’étape **informations générales** apparaissent sur cette page.</span><span class="sxs-lookup"><span data-stu-id="af0f2-157">**Summary** – The information that was parsed in the **Import Information** step and your selections from the **General Information** step is displayed on this page.</span></span> <span data-ttu-id="af0f2-158">Pour confirmer vos sélections et créer l’application, sélectionnez **Next (suivant** ).</span><span class="sxs-lookup"><span data-stu-id="af0f2-158">Select **Next** to confirm your selections and create the application.</span></span>
   * <span data-ttu-id="af0f2-159">**Progression** : affiche une barre de progression et un statut lors de l’importation et de l’ajout de l’application à la bibliothèque de logiciels.</span><span class="sxs-lookup"><span data-stu-id="af0f2-159">**Progress** – Displays a progress bar and status as the application is imported and added to the Software Library.</span></span>
   * <span data-ttu-id="af0f2-160">**Achèvement** : la confirmation de la création de l’application réussie s’affiche lorsque le processus de création d’application est terminé.</span><span class="sxs-lookup"><span data-stu-id="af0f2-160">**Completion** – Confirmation of the successful application creation is displayed when the application creation process is complete.</span></span> <span data-ttu-id="af0f2-161">Sélectionnez **Fermer** pour terminer l’Assistant Création d’une application.</span><span class="sxs-lookup"><span data-stu-id="af0f2-161">Select **Close** to finish the Create Application Wizard.</span></span>

<span data-ttu-id="af0f2-162">Une fois l’application créée dans Configuration Manager, vous pouvez la diffuser sur vos points de distribution et la déployer dans les collections, y compris sur les appareils surface.</span><span class="sxs-lookup"><span data-stu-id="af0f2-162">After the application is created in Configuration Manager, you can distribute it to your distribution points and deploy it to the collections including your Surface devices.</span></span> <span data-ttu-id="af0f2-163">Cette application ne peut pas installer ou activer SEMM sur le périphérique surface.</span><span class="sxs-lookup"><span data-stu-id="af0f2-163">This application will not install or enable SEMM on the Surface device.</span></span> <span data-ttu-id="af0f2-164">Il fournit uniquement les assemblys nécessaires à l’activation de SEMM à l’aide du script PowerShell.</span><span class="sxs-lookup"><span data-stu-id="af0f2-164">It only provides the assemblies required for SEMM to be enabled using the PowerShell script.</span></span>

<span data-ttu-id="af0f2-165">Si vous ne voulez pas installer les assemblys Microsoft surface UEFI Manager sur des appareils qui ne sont pas gérés avec SEMM, vous pouvez configurer le Gestionnaire Microsoft surface UEFI en tant que dépendance des scripts du gestionnaire de configuration SEMM.</span><span class="sxs-lookup"><span data-stu-id="af0f2-165">If you do not want to install the Microsoft Surface UEFI Manager assemblies on devices that will not be managed with SEMM, you can configure Microsoft Surface UEFI Manager as a dependency of the SEMM Configuration Manager scripts.</span></span> <span data-ttu-id="af0f2-166">Ce scénario est abordé dans la section [déploiement de scripts du gestionnaire de configuration SEMM](#deploy-semm-configuration-manager-scripts) , plus loin dans cet article.</span><span class="sxs-lookup"><span data-stu-id="af0f2-166">This scenario is covered in the [Deploy SEMM Configuration Manager Scripts](#deploy-semm-configuration-manager-scripts) section later in this article.</span></span>

## <span data-ttu-id="af0f2-167">Créer ou modifier les scripts du gestionnaire de configuration SEMM</span><span class="sxs-lookup"><span data-stu-id="af0f2-167">Create or modify the SEMM Configuration Manager scripts</span></span>

<span data-ttu-id="af0f2-168">Une fois les assemblys requis installés sur les appareils, le processus d’inscription des appareils dans SEMM et de configuration de surface UEFI est réalisé avec les scripts PowerShell et déployés en tant qu’application de script avec Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="af0f2-168">After the required assemblies have been installed on the devices, the process of enrolling the devices in SEMM and configuring Surface UEFI is done with PowerShell scripts and deployed as a script application with Configuration Manager.</span></span> <span data-ttu-id="af0f2-169">Ces scripts peuvent être modifiés pour répondre aux besoins de votre organisation et de votre environnement.</span><span class="sxs-lookup"><span data-stu-id="af0f2-169">These scripts can be modified to fit the needs of your organization and environment.</span></span> <span data-ttu-id="af0f2-170">Par exemple, vous pouvez créer plusieurs configurations pour les appareils à surface gérée dans différents services ou rôles.</span><span class="sxs-lookup"><span data-stu-id="af0f2-170">For example, you can create multiple configurations for managed Surface devices in different departments or roles.</span></span> <span data-ttu-id="af0f2-171">Vous pouvez télécharger des exemples de scripts pour SEMM et Configuration Manager à partir du lien dans la section [éléments requis](#prerequisites) au début de cet article.</span><span class="sxs-lookup"><span data-stu-id="af0f2-171">You can download samples of the scripts for SEMM and Configuration Manager from the link in the [Prerequisites](#prerequisites) section at the beginning of this article.</span></span>

<span data-ttu-id="af0f2-172">Il existe deux scripts principaux dont vous aurez besoin pour effectuer un déploiement SEMM avec Configuration Manager:</span><span class="sxs-lookup"><span data-stu-id="af0f2-172">There are two primary scripts you will need in order to perform a SEMM deployment with Configuration Manager:</span></span>

* <span data-ttu-id="af0f2-173">**ConfigureSEMM.ps1** : utilisez ce script pour créer des packages de configuration pour vos appareils de surface avec les paramètres UEFI de surface souhaités afin d’appliquer les paramètres spécifiés à un appareil surface, d’inscrire l’appareil dans SEMM et de définir une clé de Registre utilisée pour identifier l’inscription de l’appareil dans SEMM.</span><span class="sxs-lookup"><span data-stu-id="af0f2-173">**ConfigureSEMM.ps1** – Use this script to create configuration packages for your Surface devices with your desired Surface UEFI settings to apply the specified settings to a Surface device, to enroll the device in SEMM, and to set a registry key used to identify the enrollment of the device in SEMM.</span></span>
* <span data-ttu-id="af0f2-174">**ResetSEMM.ps1** : utilisez ce script pour réinitialiser SEMM sur un appareil surface, qui annule son inscription à partir de SEMM et supprime le contrôle sur les paramètres de surface UEFI.</span><span class="sxs-lookup"><span data-stu-id="af0f2-174">**ResetSEMM.ps1** – Use this script to reset SEMM on a Surface device, which unenrolls it from SEMM and removes the control over Surface UEFI settings.</span></span>

<span data-ttu-id="af0f2-175">Les exemples de scripts incluent des exemples illustrant comment définir les paramètres de surface UEFI et comment contrôler les autorisations sur ces paramètres.</span><span class="sxs-lookup"><span data-stu-id="af0f2-175">The sample scripts include examples of how to set Surface UEFI settings and how to control permissions to those settings.</span></span> <span data-ttu-id="af0f2-176">Ces paramètres peuvent être modifiés pour sécuriser surface UEFI et définir les paramètres de surface UEFI en fonction des besoins de votre environnement.</span><span class="sxs-lookup"><span data-stu-id="af0f2-176">These settings can be modified to secure Surface UEFI and set Surface UEFI settings according to the needs of your environment.</span></span> <span data-ttu-id="af0f2-177">Les sections suivantes de cet article expliquent le script de ConfigureSEMM.ps1 et explorent les modifications que vous devez apporter au script pour répondre à vos besoins.</span><span class="sxs-lookup"><span data-stu-id="af0f2-177">The following sections of this article explain the ConfigureSEMM.ps1 script and explore the modifications you need to make to the script to fit your requirements.</span></span>

> [!NOTE]
> <span data-ttu-id="af0f2-178">Les scripts du gestionnaire de configuration SEMM et le fichier de certificat SEMM exporté (. pfx) doivent être placés dans le même dossier sans autres fichiers avant d’être ajoutés à Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="af0f2-178">The SEMM Configuration Manager scripts and the exported SEMM certificate file (.pfx) should be placed in the same folder with no other files before they are added to Configuration Manager.</span></span>

### <span data-ttu-id="af0f2-179">Spécifier les noms des certificats et des packages</span><span class="sxs-lookup"><span data-stu-id="af0f2-179">Specify certificate and package names</span></span>

<span data-ttu-id="af0f2-180">La première zone du script que vous devez modifier est la partie qui spécifie et charge le certificat SEMM, ainsi que la version SurfaceUEFIManager, ainsi que les noms des packages de configuration SEMM et SEMM de réinitialisation du package.</span><span class="sxs-lookup"><span data-stu-id="af0f2-180">The first region of the script that you need to modify is the portion that specifies and loads the SEMM certificate, and also indicates SurfaceUEFIManager version, and the names for the SEMM configuration package and SEMM reset package.</span></span> <span data-ttu-id="af0f2-181">Le nom du certificat et la version SurfaceUEFIManager sont indiqués sur les lignes 56 à 73 dans le script ConfigureSEMM.ps1.</span><span class="sxs-lookup"><span data-stu-id="af0f2-181">The certificate name and SurfaceUEFIManager version are specified on lines 56 through 73 in the ConfigureSEMM.ps1 script.</span></span>

  ```powershell
  56    $WorkingDirPath = split-path -parent $MyInvocation.MyCommand.Definition
  57    $packageRoot = "$WorkingDirPath\Config"
  58    $certName = "FabrikamSEMMSample.pfx"
  59  $DllVersion = "2.26.136.0"
  60
  61  $certNameOnly = [System.IO.Path]::GetFileNameWithoutExtension($certName)
  62  $ProvisioningPackage = $certNameOnly + "ProvisioningPackage.pkg"
  63  $ResetPackage = $certNameOnly + "ResetPackage.pkg"
  64
  65    if (-not (Test-Path $packageRoot))  { New-Item -ItemType Directory -Force -Path $packageRoot }
  66    Copy-Item "$WorkingDirPath\$certName" $packageRoot
  67    
  68    $privateOwnerKey = Join-Path -Path $packageRoot -ChildPath $certName
  69    $ownerPackageName = Join-Path -Path $packageRoot -ChildPath $ProvisioningPackage
  70    $resetPackageName = Join-Path -Path $packageRoot -ChildPath $ResetPackage
  71    
  72    # If your PFX file requires a password then it can be set here, otherwise use a blank string.
  73    $password = "1234" 
  ```

<span data-ttu-id="af0f2-182">Remplacez la valeur **FabrikamSEMMSample. pfx** de la variable **$certName** par le nom de votre fichier de certificat SEMM sur la ligne 58.</span><span class="sxs-lookup"><span data-stu-id="af0f2-182">Replace the **FabrikamSEMMSample.pfx** value for the **$certName** variable with the name of your SEMM Certificate file on line 58.</span></span> <span data-ttu-id="af0f2-183">Le script crée un répertoire de travail (nommé config) dans le dossier où se trouvent vos scripts, puis copie le fichier de certificat dans ce répertoire de travail.</span><span class="sxs-lookup"><span data-stu-id="af0f2-183">The script will create a working directory (named Config) in the folder where your scripts are located, and then copies the certificate file to this working directory.</span></span>

<span data-ttu-id="af0f2-184">Le package de propriétaire et le package de réinitialisation sont également créés dans le répertoire de configuration et contiennent la configuration pour les paramètres et les autorisations de surface UEFI générés par le script.</span><span class="sxs-lookup"><span data-stu-id="af0f2-184">Owner package and reset package will also be created in the Config directory and hold the configuration for Surface UEFI settings and permissions generated by the script.</span></span>

<span data-ttu-id="af0f2-185">Sur la ligne 73, remplacez la valeur de la variable **$Password** , à partir de **1234** par le mot de passe de votre fichier de certificat.</span><span class="sxs-lookup"><span data-stu-id="af0f2-185">On line 73, replace the value of the **$password** variable, from **1234** to the password for your certificate file.</span></span> <span data-ttu-id="af0f2-186">Si aucun mot de passe n’est requis, supprimez le texte **1234** .</span><span class="sxs-lookup"><span data-stu-id="af0f2-186">If a password is not required, delete the **1234** text.</span></span>

> [!Note]
> <span data-ttu-id="af0f2-187">Les deux derniers caractères de l’empreinte numérique du certificat sont requis pour inscrire un périphérique dans SEMM.</span><span class="sxs-lookup"><span data-stu-id="af0f2-187">The last two characters of the certificate thumbprint are required to enroll a device in SEMM.</span></span> <span data-ttu-id="af0f2-188">Ce script affiche ces chiffres pour l’utilisateur, ce qui permet à l’utilisateur ou au technicien d’enregistrer ces chiffres avant que le système ne redémarre pour inscrire l’appareil dans SEMM.</span><span class="sxs-lookup"><span data-stu-id="af0f2-188">This script will display these digits to the user, which allows the user or technician to record these digits before the system reboots to enroll the device in SEMM.</span></span> <span data-ttu-id="af0f2-189">Le script utilise le code suivant, disponible sur les lignes 150-155, pour y parvenir.</span><span class="sxs-lookup"><span data-stu-id="af0f2-189">The script uses the following code, found on lines 150-155, to accomplish this.</span></span>

```powershell
150 # Device owners will need the last two characters of the thumbprint to accept SEMM ownership.
151 # For convenience we get the thumbprint here and present to the user.
152 $pw = ConvertTo-SecureString $password -AsPlainText -Force
153 $certPrint = New-Object System.Security.Cryptography.X509Certificates.X509Certificate2
154 $certPrint.Import($privateOwnerKey, $pw, [System.Security.Cryptography.X509Certificates.X509KeyStorageFlags]::DefaultKeySet)
155 Write-Host "Thumbprint =" $certPrint.Thumbprint
```

Les administrateurs ayant accès au fichier de certificat (. pfx) peuvent lire l’empreinte numérique à tout moment en ouvrant le fichier. pfx dans CertMgr. <span data-ttu-id="af0f2-191">Pour afficher l’empreinte numérique avec CertMgr, suivez ce processus:</span><span class="sxs-lookup"><span data-stu-id="af0f2-191">To view the thumbprint with CertMgr, follow this process:</span></span>

1. <span data-ttu-id="af0f2-192">Cliquez avec le bouton droit sur le fichier. pfx, puis sélectionnez **ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="af0f2-192">Right-click the .pfx file, and then select **Open**.</span></span>
2. <span data-ttu-id="af0f2-193">Développez le dossier dans le volet de navigation.</span><span class="sxs-lookup"><span data-stu-id="af0f2-193">Expand the folder in the navigation pane.</span></span>
3. <span data-ttu-id="af0f2-194">Sélectionnez **certificats**.</span><span class="sxs-lookup"><span data-stu-id="af0f2-194">Select **Certificates**.</span></span>
4. <span data-ttu-id="af0f2-195">Cliquez avec le bouton droit sur votre certificat dans le volet principal, puis sélectionnez **ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="af0f2-195">Right-click your certificate in the main pane, and then select **Open**.</span></span>
5. <span data-ttu-id="af0f2-196">Sélectionnez l’onglet **Détails** .</span><span class="sxs-lookup"><span data-stu-id="af0f2-196">Select the **Details** tab.</span></span>
6. <span data-ttu-id="af0f2-197">**Les** **Propriétés ne** doivent être sélectionnées que dans le menu déroulant **Afficher** .</span><span class="sxs-lookup"><span data-stu-id="af0f2-197">**All** or **Properties Only** must be selected in the **Show** drop-down menu.</span></span>
7. <span data-ttu-id="af0f2-198">Sélectionnez l' **empreinte**de champ.</span><span class="sxs-lookup"><span data-stu-id="af0f2-198">Select the field **Thumbprint**.</span></span>

> [!NOTE]
> <span data-ttu-id="af0f2-199">Le nom et le mot de passe du certificat SEMM doivent également être entrés dans cette section du script de ResetSEMM.ps1 pour permettre à Configuration Manager de supprimer SEMM de l’appareil à l’aide de l’action de désinstallation.</span><span class="sxs-lookup"><span data-stu-id="af0f2-199">The SEMM certificate name and password must also be entered in this section of the ResetSEMM.ps1 script to enable Configuration Manager to remove SEMM from the device with the uninstall action.</span></span>

### <span data-ttu-id="af0f2-200">Configurer des autorisations</span><span class="sxs-lookup"><span data-stu-id="af0f2-200">Configure permissions</span></span>

<span data-ttu-id="af0f2-201">La première zone du script dans laquelle vous spécifiez la configuration de surface UEFI est la région **configurer les autorisations** .</span><span class="sxs-lookup"><span data-stu-id="af0f2-201">The first region of the script where you will specify the configuration for Surface UEFI is the **Configure Permissions** region.</span></span> <span data-ttu-id="af0f2-202">Cette région commence à la ligne 210 dans l’exemple de script avec le commentaire **# configurer les autorisations** et continuer à ligne 247.</span><span class="sxs-lookup"><span data-stu-id="af0f2-202">This region begins at line 210 in the sample script with the comment **# Configure Permissions** and continues to line 247.</span></span> <span data-ttu-id="af0f2-203">Le fragment de code suivant définit d’abord les autorisations d’accès à tous les paramètres de surface UEFI pour qu’il puisse être modifié par SEMM uniquement, puis ajoute des autorisations explicites pour permettre à l’utilisateur local de modifier le mot de passe, le TPM et les caméras avant et arrière de surface.</span><span class="sxs-lookup"><span data-stu-id="af0f2-203">The following code fragment first sets permissions to all Surface UEFI settings so that they may be modified by SEMM only, then adds explicit permissions to allow the local user to modify the Surface UEFI password, TPM, and front and rear cameras.</span></span>

```powershell
210 # Configure Permissions
211 foreach ($uefiV2 IN $surfaceDevices.Values) {
212 if ($uefiV2.SurfaceUefiFamily -eq $Device.Model) {
213 Write-Host "Configuring permissions"
214 Write-Host $Device.Model
215 Write-Host "======================="
216
217 # Here we define which "identities" will be allowed to modify which settings
218 #   PermissionSignerOwner = The primary SEMM enterprise owner identity
219 #   PermissionLocal = The user when booting to the UEFI pre-boot GUI
220 #   PermissionSignerUser, PermissionSignerUser1, PermissionSignerUser2 =
221 #     Additional user identities created so that the signer owner
222 #     can delegate permission control for some settings.
223 $ownerOnly = [Microsoft.Surface.IUefiSetting]::PermissionSignerOwner
224 $ownerAndLocalUser = ([Microsoft.Surface.IUefiSetting]::PermissionSignerOwner -bor [Microsoft.Surface.IUefiSetting]::PermissionLocal)
225 
226 # Make all permissions owner only by default
227 foreach ($setting IN $uefiV2.Settings.Values) {
228 $setting.ConfiguredPermissionFlags = $ownerOnly
229 }
230 
231 # Allow the local user to change their own password
232 $uefiV2.SettingsById[501].ConfiguredPermissionFlags = $ownerAndLocalUser
233
234 Write-Host ""
235  
236 # Create a unique package name based on family and LSV.
237 # We will choose a name that can be parsed by later scripts.
238 $packageName = $uefiV2.SurfaceUefiFamily + "^Permissions^" + $lsv + ".pkg"
239 $fullPackageName = Join-Path -Path $packageRoot -ChildPath $packageName
240 
241 # Build and sign the Permission package then save it to a file.
242 $permissionPackageStream =  $uefiV2.BuildAndSignPermissionPackage($privateOwnerKey, $password, "", $null, $lsv)
243 $permissionPackage = New-Object System.IO.Filestream($fullPackageName, [System.IO.FileMode]::CreateNew, [System.IO.FileAccess]::Write)
244 $permissionPackageStream.CopyTo($permissionPackage)
245 $permissionPackage.Close()
246 }
247 }
```

<span data-ttu-id="af0f2-204">Chaque variable **$uefiV 2** identifie un paramètre de surface UEFI en définissant Name ou ID, puis configure les autorisations sur l’une des valeurs suivantes:</span><span class="sxs-lookup"><span data-stu-id="af0f2-204">Each **$uefiV2** variable identifies a Surface UEFI setting by setting name or ID, and then configures the permissions to one of the following values:</span></span>

* <span data-ttu-id="af0f2-205">**$ownerOnly** – l’autorisation de modifier ce paramètre est accordée uniquement à SEMM.</span><span class="sxs-lookup"><span data-stu-id="af0f2-205">**$ownerOnly** – Permission to modify this setting is granted only to SEMM.</span></span>
* <span data-ttu-id="af0f2-206">**$ownerAndLocalUser** – l’autorisation de modifier ce paramètre est accordée à un utilisateur local qui démarre sur la surface UEFI, ainsi qu’à SEMM.</span><span class="sxs-lookup"><span data-stu-id="af0f2-206">**$ownerAndLocalUser** – Permission to modify this setting is granted to a local user booting to Surface UEFI, as well as to SEMM.</span></span>

<span data-ttu-id="af0f2-207">Vous trouverez des informations sur les noms de paramètres disponibles et les ID de surface UEFI dans la section [noms et ID de paramètres](#settings-names-and-ids) de cet article.</span><span class="sxs-lookup"><span data-stu-id="af0f2-207">You can find information about the available settings names and IDs for Surface UEFI in the [Settings Names and IDs](#settings-names-and-ids) section of this article.</span></span>

### <span data-ttu-id="af0f2-208">Configurer les paramètres</span><span class="sxs-lookup"><span data-stu-id="af0f2-208">Configure settings</span></span>

<span data-ttu-id="af0f2-209">La deuxième zone du script dans laquelle vous spécifiez la configuration de surface UEFI est la région de configuration des **paramètres** du script de ConfigureSEMM.ps1, qui configure si chaque paramètre est activé ou désactivé.</span><span class="sxs-lookup"><span data-stu-id="af0f2-209">The second region of the script where you will specify the configuration for Surface UEFI is the **Configure Settings** region of the ConfigureSEMM.ps1 script, which configures whether each setting is enabled or disabled.</span></span> <span data-ttu-id="af0f2-210">L’exemple de script inclut des instructions permettant de définir les valeurs par défaut de tous les paramètres.</span><span class="sxs-lookup"><span data-stu-id="af0f2-210">The sample script includes instructions to set all settings to their default values.</span></span> <span data-ttu-id="af0f2-211">Le script fournit ensuite des instructions explicites pour désactiver le protocole IPv6 pour le démarrage PXE et ne modifie pas le mot de passe d’administrateur de surface UEFI.</span><span class="sxs-lookup"><span data-stu-id="af0f2-211">The script then provides explicit instructions to disable IPv6 for PXE Boot and to leave the Surface UEFI Administrator password unchanged.</span></span> <span data-ttu-id="af0f2-212">Vous pouvez trouver cette région à partir du commentaire **# configure Settings** à la ligne 291 à ligne 335 dans l’exemple de script.</span><span class="sxs-lookup"><span data-stu-id="af0f2-212">You can find this region beginning with the **# Configure Settings** comment at line 291 through line 335 in the sample script.</span></span> <span data-ttu-id="af0f2-213">La région apparaît comme suit.</span><span class="sxs-lookup"><span data-stu-id="af0f2-213">The region appears as follows.</span></span>

```powershell
291 # Configure Settings
292 foreach ($uefiV2 IN $surfaceDevices.Values) {
293 if ($uefiV2.SurfaceUefiFamily -eq $Device.Model) {
294 Write-Host "Configuring settings"
295 Write-Host $Device.Model
296 Write-Host "===================="
297
298 # In this demo, we will start by setting every setting to the default factory setting.
299 # You may want to start by doing this in your scripts
300 # so that every setting gets set to a known state.
301 foreach ($setting IN $uefiV2.Settings.Values) {
302 $setting.ConfiguredValue = $setting.DefaultValue
303 }
304 
305 $EnabledValue = "Enabled"
306 $DisabledValue = "Disabled"
307
308 # If you want to set something to a different value from the default,
309 # here are examples of how to accomplish this.
310 # This disables IPv6 PXE boot by name:
311 $uefiV2.Settings["IPv6 for PXE Boot"].ConfiguredValue = $DisabledValue
312
313 # This disables IPv6 PXE Boot by ID:
314 $uefiV2.SettingsById[400].ConfiguredValue = $DisabledValue
315
316 Write-Host ""
317
318 # If you want to leave the setting unmodified, set it to $null
319 # PowerShell has issues setting things to $null so ClearConfiguredValue()
320 # is supplied to do this explicitly.
321 # Here is an example of leaving the UEFI administrator password as-is,
322 # even after we initially set it to factory default above.
323 $uefiV2.SettingsById[501].ClearConfiguredValue()
324 
325 # Create a unique package name based on family and LSV.
326 # We will choose a name that can be parsed by later scripts.
327 $packageName = $uefiV2.SurfaceUefiFamily + "^Settings^" + $lsv + ".pkg"
328 $fullPackageName = Join-Path -Path $packageRoot -ChildPath $packageName
329 
330 # Build and sign the Settings package then save it to a file.
331 $settingsPackageStream =  $uefiV2.BuildAndSignSecuredSettingsPackage($privateOwnerKey, $password, "", $null, $lsv)
332 $settingsPackage = New-Object System.IO.Filestream($fullPackageName, [System.IO.FileMode]::CreateNew, [System.IO.FileAccess]::Write)
333 $settingsPackageStream.CopyTo($settingsPackage)
334 $settingsPackage.Close()
335 }
```

<span data-ttu-id="af0f2-214">Comme les autorisations définies dans la section **configurer les autorisations** du script, la configuration de chaque paramètre de surface UEFI est effectuée en définissant la variable **$uefiV 2** .</span><span class="sxs-lookup"><span data-stu-id="af0f2-214">Like the permissions set in the **Configure Permissions** section of the script, the configuration of each Surface UEFI setting is performed by defining the **$uefiV2** variable.</span></span> <span data-ttu-id="af0f2-215">Pour chaque ligne définissant la variable **$uefiV 2** , un paramètre de surface UEFI est identifié par un nom de paramètre ou un ID et la valeur configurée est définie sur **activé** ou **désactivé**.</span><span class="sxs-lookup"><span data-stu-id="af0f2-215">For each line defining the **$uefiV2** variable, a Surface UEFI setting is identified by setting name or ID and the configured value is set to **Enabled** or **Disabled**.</span></span>

<span data-ttu-id="af0f2-216">Si vous ne voulez pas modifier la configuration d’un paramètre de surface UEFI, par exemple pour vous assurer que le mot de passe d’administrateur de surface UEFI n’est pas supprimé en effectuant une action de réinitialisation de tous les paramètres de surface UEFI à sa valeur par défaut, vous pouvez utiliser **ClearConfiguredValue ()** pour appliquer ce paramètre ne sera pas modifié.</span><span class="sxs-lookup"><span data-stu-id="af0f2-216">If you do not want to alter the configuration of a Surface UEFI setting, for example to ensure that the Surface UEFI administrator password is not cleared by the action of resetting all Surface UEFI settings to their default, you can use **ClearConfiguredValue()** to enforce that this setting will not be altered.</span></span> <span data-ttu-id="af0f2-217">Dans l’exemple de script, il est utilisé sur ligne 323 pour empêcher la suppression du mot de passe d’administrateur de surface UEFI, identifié dans l’exemple de script par son ID de paramètre, **501**.</span><span class="sxs-lookup"><span data-stu-id="af0f2-217">In the sample script, this is used on line 323 to prevent the clearing of the Surface UEFI Administrator password, identified in the sample script by its setting ID, **501**.</span></span>

<span data-ttu-id="af0f2-218">Vous trouverez plus d’informations sur les noms de paramètres disponibles et les ID de surface UEFI dans la section [noms et ID des paramètres,](#settings-names-and-ids) plus loin dans cet article.</span><span class="sxs-lookup"><span data-stu-id="af0f2-218">You can find information about the available settings names and IDs for Surface UEFI in the [Settings Names and IDs](#settings-names-and-ids) section later in this article.</span></span>

### <span data-ttu-id="af0f2-219">Clé de Registre paramètres</span><span class="sxs-lookup"><span data-stu-id="af0f2-219">Settings registry key</span></span>

<span data-ttu-id="af0f2-220">Pour identifier les systèmes inscrits de Configuration Manager, le script ConfigureSEMM.ps1 écrit les clés de Registre qui peuvent être utilisées pour identifier les systèmes inscrits comme installés avec le script de configuration SEMM.</span><span class="sxs-lookup"><span data-stu-id="af0f2-220">To identify enrolled systems for Configuration Manager, the ConfigureSEMM.ps1 script writes registry keys that can be used to identify enrolled systems as having been installed with the SEMM configuration script.</span></span> <span data-ttu-id="af0f2-221">Ces clés sont accessibles à l’emplacement suivant.</span><span class="sxs-lookup"><span data-stu-id="af0f2-221">These keys can be found at the following location.</span></span>

`HKLM\SOFTWARE\Microsoft\Surface\SEMM`

<span data-ttu-id="af0f2-222">Le fragment de code suivant, qui se trouve sur les lignes 380-477, est utilisé pour écrire ces clés de registre.</span><span class="sxs-lookup"><span data-stu-id="af0f2-222">The following code fragment, found on lines 380-477, is used to write these registry keys.</span></span>

```powershell
380 # For Endpoint Configuration Manager or other management solutions that wish to know what version is applied, tattoo the LSV and current DateTime (in UTC) to the registry:
381 $UTCDate = (Get-Date).ToUniversalTime().ToString()
382 $certIssuer = $certPrint.Issuer
383 $certSubject = $certPrint.Subject
384 
385 $SurfaceRegKey = "HKLM:\SOFTWARE\Microsoft\Surface\SEMM"
386 New-RegKey $SurfaceRegKey
387 $LSVRegValue = Get-ItemProperty $SurfaceRegKey LSV -ErrorAction SilentlyContinue
388 $DateTimeRegValue = Get-ItemProperty $SurfaceRegKey LastConfiguredUTC -ErrorAction SilentlyContinue
389 $OwnershipSessionIdRegValue = Get-ItemProperty $SurfaceRegKey OwnershipSessionId -ErrorAction SilentlyContinue
390 $PermissionSessionIdRegValue = Get-ItemProperty $SurfaceRegKey PermissionSessionId -ErrorAction SilentlyContinue
391 $SettingsSessionIdRegValue = Get-ItemProperty $SurfaceRegKey SettingsSessionId -ErrorAction SilentlyContinue
392 $IsResetRegValue = Get-ItemProperty $SurfaceRegKey IsReset -ErrorAction SilentlyContinue
393 $certUsedRegValue = Get-ItemProperty $SurfaceRegKey CertName -ErrorAction SilentlyContinue
394 $certIssuerRegValue = Get-ItemProperty $SurfaceRegKey CertIssuer -ErrorAction SilentlyContinue
395 $certSubjectRegValue = Get-ItemProperty $SurfaceRegKey CertSubject -ErrorAction SilentlyContinue
396 
397 
398 If ($LSVRegValue -eq $null)
399 {
400     New-ItemProperty -Path $SurfaceRegKey -Name LSV -PropertyType DWORD -Value $lsv | Out-Null
401 }
402 Else
403 {
404     Set-ItemProperty -Path $SurfaceRegKey -Name LSV -Value $lsv
405 }
406 
407 If ($DateTimeRegValue -eq $null)
408 {
409     New-ItemProperty -Path $SurfaceRegKey -Name LastConfiguredUTC -PropertyType String -Value $UTCDate | Out-Null
410 }
411 Else
412 {
413     Set-ItemProperty -Path $SurfaceRegKey -Name LastConfiguredUTC -Value $UTCDate
414 }
415 
416 If ($OwnershipSessionIdRegValue -eq $null)
417 {
418     New-ItemProperty -Path $SurfaceRegKey -Name OwnershipSessionId -PropertyType String -Value $ownerSessionIdValue | Out-Null
419 }
420 Else
421 {
422     Set-ItemProperty -Path $SurfaceRegKey -Name OwnershipSessionId -Value $ownerSessionIdValue
423 }
424 
425 If ($PermissionSessionIdRegValue -eq $null)
426 {
427     New-ItemProperty -Path $SurfaceRegKey -Name PermissionSessionId -PropertyType String -Value $permissionSessionIdValue | Out-Null
428 }
429 Else
430 {
431     Set-ItemProperty -Path $SurfaceRegKey -Name PermissionSessionId -Value $permissionSessionIdValue
432 }
433 
434 If ($SettingsSessionIdRegValue -eq $null)
435 {
436     New-ItemProperty -Path $SurfaceRegKey -Name SettingsSessionId -PropertyType String -Value $settingsSessionIdValue | Out-Null
437 }
438 Else
439 {
440     Set-ItemProperty -Path $SurfaceRegKey -Name SettingsSessionId -Value $settingsSessionIdValue
441 }
442 
443 If ($IsResetRegValue -eq $null)
444 {
445     New-ItemProperty -Path $SurfaceRegKey -Name IsReset -PropertyType DWORD -Value 0 | Out-Null
446 }
447 Else
448 {
449     Set-ItemProperty -Path $SurfaceRegKey -Name IsReset -Value 0
450 }
451 
452 If ($certUsedRegValue -eq $null)
453 {
454     New-ItemProperty -Path $SurfaceRegKey -Name CertName -PropertyType String -Value $certName | Out-Null
455 }
456 Else
457 {
458     Set-ItemProperty -Path $SurfaceRegKey -Name CertName -Value $certName
459 }
460 
461 If ($certIssuerRegValue -eq $null)
462 {
463     New-ItemProperty -Path $SurfaceRegKey -Name CertIssuer -PropertyType String -Value $certIssuer | Out-Null
464 }
465 Else
466 {
467     Set-ItemProperty -Path $SurfaceRegKey -Name CertIssuer -Value $certIssuer
468 }
469 
470 If ($certSubjectRegValue -eq $null)
471 {
472     New-ItemProperty -Path $SurfaceRegKey -Name CertSubject -PropertyType String -Value $certSubject | Out-Null
473 }
474 Else
475 {
476     Set-ItemProperty -Path $SurfaceRegKey -Name CertSubject -Value $certSubject
477 }
```

### <span data-ttu-id="af0f2-223">ID et noms de paramètres</span><span class="sxs-lookup"><span data-stu-id="af0f2-223">Settings names and IDs</span></span>

<span data-ttu-id="af0f2-224">Pour configurer les paramètres ou les autorisations de surface UEFI pour les paramètres de surface UEFI, vous devez faire référence à chaque paramètre en utilisant son nom de paramètre ou son ID de paramètre.</span><span class="sxs-lookup"><span data-stu-id="af0f2-224">To configure Surface UEFI settings or permissions for Surface UEFI settings, you must refer to each setting by either its setting name or setting ID.</span></span> <span data-ttu-id="af0f2-225">Avec chaque nouvelle mise à jour de surface UEFI, de nouveaux paramètres pourront être ajoutés.</span><span class="sxs-lookup"><span data-stu-id="af0f2-225">With each new update for Surface UEFI, new settings may be added.</span></span> <span data-ttu-id="af0f2-226">Le meilleur moyen d’obtenir une liste complète des paramètres disponibles sur un appareil surface, ainsi que les paramètres de nom et d’ID de paramètres, consiste à utiliser le script ShowSettingsOptions.ps1 de SEMM_Powershell.zip dans les [Outils surface pour les télécharger](https://www.microsoft.com/download/details.aspx?id=46703) .</span><span class="sxs-lookup"><span data-stu-id="af0f2-226">The best way to get a complete list of the settings available on a Surface device, along with the settings name and settings IDs, is to use the ShowSettingsOptions.ps1 script from SEMM_Powershell.zip in [Surface Tools for IT Downloads](https://www.microsoft.com/download/details.aspx?id=46703)</span></span> 

<span data-ttu-id="af0f2-227">Le Gestionnaire Microsoft surface UEFI doit être installé sur l’ordinateur sur lequel ShowSettingsOptions.ps1 est exécuté; il n’est pas nécessaire d’avoir un appareil surface.</span><span class="sxs-lookup"><span data-stu-id="af0f2-227">The computer where ShowSettingsOptions.ps1 is run must have Microsoft Surface UEFI Manager installed, but the script does not require a Surface device.</span></span>

<span data-ttu-id="af0f2-228">Pour afficher les noms de paramètres les plus courants et les ID pour les appareils, la meilleure façon consiste à utiliser le script de ConfigureSEMM.ps1 ou ConfigureSEMM- <device name> . ps1 du SEMM_Powershell.zip dans [Outils surface pour les télécharger](https://www.microsoft.com/download/details.aspx?id=46703).</span><span class="sxs-lookup"><span data-stu-id="af0f2-228">The best way to view the most current Setting names and IDs for devices is to use the ConfigureSEMM.ps1 script or the ConfigureSEMM - <device name>.ps1 from the SEMM_Powershell.zip in [Surface Tools for IT Downloads](https://www.microsoft.com/download/details.aspx?id=46703).</span></span>

<span data-ttu-id="af0f2-229">Il est possible d’afficher les noms et ID de tous les appareils dans l' ConfigureSEMM.ps1 script.</span><span class="sxs-lookup"><span data-stu-id="af0f2-229">Setting names and IDs for all devices can be seen in the ConfigureSEMM.ps1 script.</span></span>

<span data-ttu-id="af0f2-230">Il est possible d’afficher les noms et ID pour des appareils spécifiques dans les scripts ConfigureSEMM- <device name> . ps1.</span><span class="sxs-lookup"><span data-stu-id="af0f2-230">Setting names and IDs for specific devices can be seen in the ConfigureSEMM - <device name>.ps1 scripts.</span></span> 

## <span data-ttu-id="af0f2-231">Déploiement de SEMM Configuration Manager scripts</span><span class="sxs-lookup"><span data-stu-id="af0f2-231">Deploy SEMM Configuration Manager scripts</span></span>

<span data-ttu-id="af0f2-232">Après avoir préparé vos scripts pour configurer et activer SEMM sur l’appareil client, l’étape suivante consiste à ajouter ces scripts en tant qu’application dans Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="af0f2-232">After your scripts are prepared to configure and enable SEMM on the client device, the next step is to add these scripts as an application in Configuration Manager.</span></span> <span data-ttu-id="af0f2-233">Avant d’ouvrir Configuration Manager, vérifiez que les fichiers suivants se trouvent dans un dossier partagé qui n’inclut pas d’autres fichiers:</span><span class="sxs-lookup"><span data-stu-id="af0f2-233">Before you open Configuration Manager, ensure that the following files are in a shared folder that does not include other files:</span></span>

* <span data-ttu-id="af0f2-234">ConfigureSEMM.ps1</span><span class="sxs-lookup"><span data-stu-id="af0f2-234">ConfigureSEMM.ps1</span></span>
* <span data-ttu-id="af0f2-235">ResetSEMM.ps1</span><span class="sxs-lookup"><span data-stu-id="af0f2-235">ResetSEMM.ps1</span></span>
* <span data-ttu-id="af0f2-236">Votre certificat SEMM (par exemple, SEMMCertificate. pfx);</span><span class="sxs-lookup"><span data-stu-id="af0f2-236">Your SEMM certificate (for example SEMMCertificate.pfx)</span></span>

<span data-ttu-id="af0f2-237">Les scripts du gestionnaire de configuration SEMM seront ajoutés à Configuration Manager en tant qu’application de script.</span><span class="sxs-lookup"><span data-stu-id="af0f2-237">The SEMM Configuration Manager scripts will be added to Configuration Manager as a script application.</span></span> <span data-ttu-id="af0f2-238">La commande permettant d’installer SEMM avec ConfigureSEMM.ps1 est la suivante.</span><span class="sxs-lookup"><span data-stu-id="af0f2-238">The command to install SEMM with ConfigureSEMM.ps1 is as follows.</span></span>

`Powershell.exe -file ".\ConfigureSEMM.ps1"`

<span data-ttu-id="af0f2-239">La commande permettant de désinstaller SEMM avec ResetSEMM.ps1 est la suivante.</span><span class="sxs-lookup"><span data-stu-id="af0f2-239">The command to uninstall SEMM with ResetSEMM.ps1 is as follows.</span></span>

`Powershell.exe -file ".\ResetSEMM.ps1"`

<span data-ttu-id="af0f2-240">Pour ajouter les scripts du gestionnaire de configuration SEMM dans Configuration Manager en tant qu’application, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="af0f2-240">To add the SEMM Configuration Manager scripts to Configuration Manager as an application, use the following process:</span></span>

1. <span data-ttu-id="af0f2-241">Démarrez l’Assistant Création d’une application en suivant les étapes 1 à 5 de la section [déployer Microsoft surface UEFI Manager](#deploy-microsoft-surface-uefi-manager) plus haut dans cet article.</span><span class="sxs-lookup"><span data-stu-id="af0f2-241">Start the Create Application Wizard using Step 1 through Step 5 from the [Deploy Microsoft Surface UEFI Manager](#deploy-microsoft-surface-uefi-manager) section earlier in this article.</span></span>

2. <span data-ttu-id="af0f2-242">Suivez les étapes de l’Assistant Création d’une application en procédant comme suit:</span><span class="sxs-lookup"><span data-stu-id="af0f2-242">Proceed through The Create Application Wizard as follows:</span></span>

   - <span data-ttu-id="af0f2-243">**Général** : sélectionnez **spécifier manuellement les informations de l’application**, puis sélectionnez **suivant**.</span><span class="sxs-lookup"><span data-stu-id="af0f2-243">**General** – Select **Manually specify the application information**, and then select **Next**.</span></span>

   - <span data-ttu-id="af0f2-244">**Informations générales** : entrez un nom pour l’application (par exemple SEMM), ainsi que toute autre information de votre choix (par exemple, Publisher, version ou commentaires).</span><span class="sxs-lookup"><span data-stu-id="af0f2-244">**General Information** – Enter a name for the application (for example SEMM) and any other information you want such as publisher, version, or comments on this page.</span></span> <span data-ttu-id="af0f2-245">Sélectionnez **Next (suivant** ) pour continuer.</span><span class="sxs-lookup"><span data-stu-id="af0f2-245">Select **Next** to proceed.</span></span>

   - <span data-ttu-id="af0f2-246">**Catalogue d’applications** : les champs de cette page peuvent être laissés avec leurs valeurs par défaut.</span><span class="sxs-lookup"><span data-stu-id="af0f2-246">**Application Catalog** – The fields on this page can be left with their default values.</span></span> <span data-ttu-id="af0f2-247">Sélectionnez **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="af0f2-247">Select **Next**.</span></span>

   - <span data-ttu-id="af0f2-248">**Types de déploiement** : sélectionnez **Ajouter** pour démarrer l’Assistant Création d’un type de déploiement.</span><span class="sxs-lookup"><span data-stu-id="af0f2-248">**Deployment Types** – Select **Add** to start the Create Deployment Type Wizard.</span></span>

   - <span data-ttu-id="af0f2-249">Suivez les étapes de l’Assistant Création d’un type de déploiement, comme suit:</span><span class="sxs-lookup"><span data-stu-id="af0f2-249">Proceed through the steps of the Create Deployment Type Wizard, as follows:</span></span>

     * <span data-ttu-id="af0f2-250">**Général** : sélectionnez **programme d’installation de script** dans le menu déroulant **type** .</span><span class="sxs-lookup"><span data-stu-id="af0f2-250">**General** – Select **Script Installer** from the **Type** drop-down menu.</span></span> <span data-ttu-id="af0f2-251">L’option **spécifier manuellement les informations de type de déploiement** sera sélectionnée automatiquement.</span><span class="sxs-lookup"><span data-stu-id="af0f2-251">The **Manually specify the deployment type information** option will automatically be selected.</span></span> <span data-ttu-id="af0f2-252">Sélectionnez **Next (suivant** ) pour continuer.</span><span class="sxs-lookup"><span data-stu-id="af0f2-252">Select **Next** to proceed.</span></span>
     * <span data-ttu-id="af0f2-253">**Informations générales** : entrez un nom pour le type de déploiement (par exemple, scripts de configuration SEMM), puis sélectionnez **suivant** pour continuer.</span><span class="sxs-lookup"><span data-stu-id="af0f2-253">**General Information** – Enter a name for the deployment type (for example SEMM Configuration Scripts), and then select **Next** to continue.</span></span>
     * <span data-ttu-id="af0f2-254">**Contenu** : sélectionnez **Parcourir** en regard du champ d' **emplacement du contenu** , puis sélectionnez le dossier dans lequel se trouvent les scripts de votre gestionnaire de configuration SEMM.</span><span class="sxs-lookup"><span data-stu-id="af0f2-254">**Content** – Select **Browse** next to the **Content Location** field, and then select the folder where your SEMM Configuration Manager scripts are located.</span></span> <span data-ttu-id="af0f2-255">Dans le champ **programme d’installation** , tapez la commande d' [installation](#deploy-semm-configuration-manager-scripts) qui est abordée plus haut dans cet article.</span><span class="sxs-lookup"><span data-stu-id="af0f2-255">In the **Installation Program** field, type the [installation command](#deploy-semm-configuration-manager-scripts) found earlier in this article.</span></span> <span data-ttu-id="af0f2-256">Dans le champ désinstaller le **programme** , entrez la [commande de désinstallation](#deploy-semm-configuration-manager-scripts) qui est décrite plus haut dans cet article (illustré dans la figure 2).</span><span class="sxs-lookup"><span data-stu-id="af0f2-256">In the **Uninstall Program** field, enter the [uninstallation command](#deploy-semm-configuration-manager-scripts) found earlier in this article (shown in Figure 2).</span></span> <span data-ttu-id="af0f2-257">Sélectionnez **suivant** pour passer à la page suivante.</span><span class="sxs-lookup"><span data-stu-id="af0f2-257">Select **Next** to move to the next page.</span></span>
    
     ![Définissez les scripts du gestionnaire de configuration SEMM comme commandes installer et désinstaller](images/config-mgr-semm-fig2.png "Set the SEMM Configuration Manager scripts as the install and uninstall commands")

     *<span data-ttu-id="af0f2-259">Figure2.</span><span class="sxs-lookup"><span data-stu-id="af0f2-259">Figure 2.</span></span> <span data-ttu-id="af0f2-260">Définissez les scripts du gestionnaire de configuration SEMM comme commandes installer et désinstaller</span><span class="sxs-lookup"><span data-stu-id="af0f2-260">Set the SEMM Configuration Manager scripts as the install and uninstall commands</span></span>*

     * <span data-ttu-id="af0f2-261">**Méthode de détection** : sélectionnez **Ajouter une clause** pour ajouter la règle de détection de clé de Registre du gestionnaire de configuration SEMM.</span><span class="sxs-lookup"><span data-stu-id="af0f2-261">**Detection Method** – Select **Add Clause** to add the SEMM Configuration Manager script registry key detection rule.</span></span> <span data-ttu-id="af0f2-262">La fenêtre **règle de détection** s’affiche, comme illustré dans la figure 3.</span><span class="sxs-lookup"><span data-stu-id="af0f2-262">The **Detection Rule** window is displayed, as shown in Figure 3.</span></span> <span data-ttu-id="af0f2-263">Utilisez les paramètres suivants:</span><span class="sxs-lookup"><span data-stu-id="af0f2-263">Use the following settings:</span></span>

       - <span data-ttu-id="af0f2-264">Dans le menu déroulant **type de paramètre** , sélectionnez **Registre** .</span><span class="sxs-lookup"><span data-stu-id="af0f2-264">Select **Registry** from the **Setting Type** drop-down menu.</span></span>
       - <span data-ttu-id="af0f2-265">Dans le menu déroulant **Hive** , sélectionnez **HKEY_LOCAL_MACHINE** .</span><span class="sxs-lookup"><span data-stu-id="af0f2-265">Select **HKEY_LOCAL_MACHINE** from the **Hive** drop-down menu.</span></span>
       - <span data-ttu-id="af0f2-266">Entrez **SOFTWARE\Microsoft\Surface\SEMM** dans le champ **clé** .</span><span class="sxs-lookup"><span data-stu-id="af0f2-266">Enter **SOFTWARE\Microsoft\Surface\SEMM** in the **Key** field.</span></span>
       - <span data-ttu-id="af0f2-267">Entrez **CertName** dans le champ **valeur** .</span><span class="sxs-lookup"><span data-stu-id="af0f2-267">Enter **CertName** in the **Value** field.</span></span>
       - <span data-ttu-id="af0f2-268">Dans le menu déroulant **type de données** , sélectionnez **chaîne** .</span><span class="sxs-lookup"><span data-stu-id="af0f2-268">Select **String** from the **Data Type** drop-down menu.</span></span>
       - <span data-ttu-id="af0f2-269">Sélectionnez **ce paramètre de registre doit respecter les règles suivantes pour indiquer la présence de ce bouton d’application** .</span><span class="sxs-lookup"><span data-stu-id="af0f2-269">Select the **This registry setting must satisfy the following rule to indicate the presence of this application** button.</span></span>
       - <span data-ttu-id="af0f2-270">Entrez le nom du certificat que vous avez entré dans la ligne 58 du script dans le champ **valeur** .</span><span class="sxs-lookup"><span data-stu-id="af0f2-270">Enter the name of the certificate you entered in line 58 of the script in the **Value** field.</span></span>
       - <span data-ttu-id="af0f2-271">Sélectionnez **OK** pour fermer la fenêtre **règle de détection** .</span><span class="sxs-lookup"><span data-stu-id="af0f2-271">Select **OK** to close the **Detection Rule** window.</span></span>

     ![Utiliser une clé de Registre pour identifier les appareils inscrits dans SEMM](images/config-mgr-semm-fig3.png "Use a registry key to identify devices enrolled in SEMM")
     
     *<span data-ttu-id="af0f2-273">Figure3.</span><span class="sxs-lookup"><span data-stu-id="af0f2-273">Figure 3.</span></span> <span data-ttu-id="af0f2-274">Utiliser une clé de Registre pour identifier les appareils inscrits dans SEMM</span><span class="sxs-lookup"><span data-stu-id="af0f2-274">Use a registry key to identify devices enrolled in SEMM</span></span>*

     * <span data-ttu-id="af0f2-275">Sélectionnez **suivant** pour passer à la page suivante.</span><span class="sxs-lookup"><span data-stu-id="af0f2-275">Select **Next** to proceed to the next page.</span></span>
     
     * <span data-ttu-id="af0f2-276">**Interface utilisateur** : dans le menu déroulant **comportement d’installation** , sélectionnez **installer pour le système** .</span><span class="sxs-lookup"><span data-stu-id="af0f2-276">**User Experience** – Select **Install for system** from the **Installation Behavior** drop-down menu.</span></span> <span data-ttu-id="af0f2-277">Si vous souhaitez que vos utilisateurs puissent enregistrer et entrer l’empreinte numérique du certificat, ne définissez aucune obligation de connexion **uniquement lorsqu’un utilisateur est connecté**.</span><span class="sxs-lookup"><span data-stu-id="af0f2-277">If you want your users to record and enter the certificate thumbprint themselves, leave the logon requirement set to **Only when a user is logged on**.</span></span> <span data-ttu-id="af0f2-278">Si vous voulez permettre aux administrateurs d’entrer l’empreinte numérique des utilisateurs et que les utilisateurs n’ont pas besoin de voir leur empreinte, sélectionnez **si l’utilisateur est connecté** à partir du menu déroulant **exigences de connexion** .</span><span class="sxs-lookup"><span data-stu-id="af0f2-278">If you want your administrators to enter the thumbprint for users and the users do not need to see the thumbprint, select **Whether or not a user is logged on** from the **Logon Requirement** drop-down menu.</span></span>

     * <span data-ttu-id="af0f2-279">**Configuration requise** : le script de ConfigureSEMM.ps1 vérifie automatiquement que l’appareil est un appareil surface avant d’essayer d’activer SEMM.</span><span class="sxs-lookup"><span data-stu-id="af0f2-279">**Requirements** – The ConfigureSEMM.ps1 script automatically verifies that the device is a Surface device before attempting to enable SEMM.</span></span> <span data-ttu-id="af0f2-280">Toutefois, si vous envisagez de déployer cette application de script sur une collection dont les appareils ne sont pas à gérer avec SEMM, vous pouvez ajouter des spécifications ici pour vous assurer que cette application ne s’exécute que sur les appareils à surface ou les appareils que vous souhaitez gérer avec SEMM.</span><span class="sxs-lookup"><span data-stu-id="af0f2-280">However, if you intend to deploy this script application to a collection with devices other than those to be managed with SEMM, you could add requirements here to ensure this application would run only on Surface devices or devices you intend to manage with SEMM.</span></span> <span data-ttu-id="af0f2-281">Sélectionnez **Next (suivant** ) pour continuer.</span><span class="sxs-lookup"><span data-stu-id="af0f2-281">Select **Next** to continue.</span></span>
     
     * <span data-ttu-id="af0f2-282">**Dépendances** : sélectionnez **Ajouter** pour ouvrir la fenêtre **Ajouter une dépendance** .</span><span class="sxs-lookup"><span data-stu-id="af0f2-282">**Dependencies** – Select **Add** to open the **Add Dependency** window.</span></span>

       * <span data-ttu-id="af0f2-283">Sélectionnez **Ajouter** pour ouvrir la fenêtre **spécifier l’application requise** .</span><span class="sxs-lookup"><span data-stu-id="af0f2-283">Select **Add** to open the **Specify Required Application** window.</span></span>

          - <span data-ttu-id="af0f2-284">Entrez un nom pour les dépendances SEMM dans le champ **nom du groupe de dépendances** (par exemple, *assemblys SEMM*).</span><span class="sxs-lookup"><span data-stu-id="af0f2-284">Enter a name for the SEMM dependencies in the **Dependency Group Name** field (for example, *SEMM Assemblies*).</span></span>

          - <span data-ttu-id="af0f2-285">Sélectionnez **Microsoft surface UEFI Manager** dans la liste des **applications disponibles** et le type de déploiement MSI, puis sélectionnez **OK** pour fermer la fenêtre **spécifier l’application requise** .</span><span class="sxs-lookup"><span data-stu-id="af0f2-285">Select **Microsoft Surface UEFI Manager** from the list of **Available Applications** and the MSI deployment type, and then select **OK** to close the **Specify Required Application** window.</span></span>
          
         *   <span data-ttu-id="af0f2-286">Laissez la case à cocher **installation automatique** sélectionnée si vous voulez que le Gestionnaire Microsoft surface UEFI soit installé automatiquement sur les appareils lorsque vous tentez d’activer SEMM avec les scripts du gestionnaire de configuration.</span><span class="sxs-lookup"><span data-stu-id="af0f2-286">Keep the **Auto Install** check box selected if you want Microsoft Surface UEFI Manager installed automatically on devices when you attempt to enable SEMM with the Configuration Manager scripts.</span></span> <span data-ttu-id="af0f2-287">Sélectionnez **OK** pour fermer la fenêtre **Ajouter une dépendance** .</span><span class="sxs-lookup"><span data-stu-id="af0f2-287">Select **OK** to close the **Add Dependency** window.</span></span>

     * <span data-ttu-id="af0f2-288">Sélectionnez **Next (suivant** ) pour continuer.</span><span class="sxs-lookup"><span data-stu-id="af0f2-288">Select **Next** to proceed.</span></span>
     
     * <span data-ttu-id="af0f2-289">**Résumé** : les informations que vous avez entrées dans l’Assistant Création d’un type de déploiement s’affichent dans cette page.</span><span class="sxs-lookup"><span data-stu-id="af0f2-289">**Summary** – The information you have entered throughout the Create Deployment Type wizard is displayed on this page.</span></span> <span data-ttu-id="af0f2-290">Pour confirmer vos sélections, sélectionnez **Next (suivant** ).</span><span class="sxs-lookup"><span data-stu-id="af0f2-290">Select **Next** to confirm your selections.</span></span>
     
     * <span data-ttu-id="af0f2-291">**Progression** : une barre de progression et un statut en tant que type de déploiement est ajouté pour l’application script SEMM est affiché dans cette page.</span><span class="sxs-lookup"><span data-stu-id="af0f2-291">**Progress** – A progress bar and status as the deployment type is added for the SEMM script application is displayed on this page.</span></span>
     
     * <span data-ttu-id="af0f2-292">**Achèvement** : la confirmation de la création du type de déploiement s’affiche lorsque le processus est terminé.</span><span class="sxs-lookup"><span data-stu-id="af0f2-292">**Completion** – Confirmation of the deployment type creation is displayed when the process is complete.</span></span> <span data-ttu-id="af0f2-293">Sélectionnez **Fermer** pour terminer l’Assistant Création d’un type de déploiement.</span><span class="sxs-lookup"><span data-stu-id="af0f2-293">Select **Close** to finish the Create Deployment Type Wizard.</span></span>

   - <span data-ttu-id="af0f2-294">**Résumé** : les informations que vous avez entrées dans l’Assistant Création d’une application apparaissent.</span><span class="sxs-lookup"><span data-stu-id="af0f2-294">**Summary** – The information that you entered throughout the Create Application Wizard is displayed.</span></span> <span data-ttu-id="af0f2-295">Sélectionnez **suivant** pour créer l’application.</span><span class="sxs-lookup"><span data-stu-id="af0f2-295">Select **Next** to create the application.</span></span>

   - <span data-ttu-id="af0f2-296">**Progression** : une barre de progression et un statut au fur et à mesure de l’ajout de l’application à la bibliothèque logicielle apparaissent sur cette page.</span><span class="sxs-lookup"><span data-stu-id="af0f2-296">**Progress** – A progress bar and status as the application is added to the Software Library is displayed on this page.</span></span>

   - <span data-ttu-id="af0f2-297">**Achèvement** : la confirmation de la création de l’application réussie s’affiche lorsque le processus de création d’application est terminé.</span><span class="sxs-lookup"><span data-stu-id="af0f2-297">**Completion** – Confirmation of the successful application creation is displayed when the application creation process is complete.</span></span> <span data-ttu-id="af0f2-298">Sélectionnez **Fermer** pour terminer l’Assistant Création d’une application.</span><span class="sxs-lookup"><span data-stu-id="af0f2-298">Select **Close** to finish the Create Application Wizard.</span></span>

<span data-ttu-id="af0f2-299">Une fois l’application de script disponible dans la bibliothèque de logiciels de Configuration Manager, vous pouvez distribuer et déployer SEMM en utilisant les scripts que vous avez préparés pour les appareils ou collections.</span><span class="sxs-lookup"><span data-stu-id="af0f2-299">After the script application is available in the Software Library of Configuration Manager, you can distribute and deploy SEMM using the scripts you prepared to devices or collections.</span></span> <span data-ttu-id="af0f2-300">Si vous avez configuré les assemblys Microsoft surface UEFI Manager en tant que dépendance qui sera installée automatiquement, vous pouvez déployer SEMM en une seule étape.</span><span class="sxs-lookup"><span data-stu-id="af0f2-300">If you have configured the Microsoft Surface UEFI Manager assemblies as a dependency that will be automatically installed, you can deploy SEMM in a single step.</span></span> <span data-ttu-id="af0f2-301">Si vous n’avez pas configuré les assemblys en tant que dépendance, ils doivent être installés sur les appareils que vous envisagez de gérer avant d’activer SEMM.</span><span class="sxs-lookup"><span data-stu-id="af0f2-301">If you have not configured the assemblies as a dependency, they must be installed on the devices you intend to manage before you enable SEMM.</span></span>

<span data-ttu-id="af0f2-302">Lorsque vous déployez SEMM à l’aide de cette application de script et d’une configuration qui est visible à l’utilisateur final, le script PowerShell démarre et l’empreinte numérique du certificat s’affiche dans la fenêtre PowerShell.</span><span class="sxs-lookup"><span data-stu-id="af0f2-302">When you deploy SEMM using this script application and with a configuration that is visible to the end user, the PowerShell script will start and the thumbprint for the certificate will be displayed by the PowerShell window.</span></span> <span data-ttu-id="af0f2-303">Vous pouvez faire en sorte que vos utilisateurs enregistrent cette empreinte digitale et l’entrer lorsque vous y êtes invité par surface UEFI après le redémarrage de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="af0f2-303">You can have your users record this thumbprint and enter it when prompted by Surface UEFI after the device reboots.</span></span>

<span data-ttu-id="af0f2-304">Par ailleurs, vous pouvez configurer l’installation de l’application pour qu’elle redémarre automatiquement et qu’elle s’installe de façon transparente pour l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="af0f2-304">Alternatively, you can configure the application installation to reboot automatically and to install invisibly to the user.</span></span> <span data-ttu-id="af0f2-305">Dans ce scénario, un technicien sera tenu d’entrer l’empreinte numérique de chaque appareil au fur et à mesure de son redémarrage.</span><span class="sxs-lookup"><span data-stu-id="af0f2-305">In this scenario, a technician will be required to enter the thumbprint on each device as it reboots.</span></span> <span data-ttu-id="af0f2-306">Tout technicien ayant accès au fichier de certificat peut lire l’empreinte numérique en affichant le certificat avec CertMgr.</span><span class="sxs-lookup"><span data-stu-id="af0f2-306">Any technician with access to the certificate file can read the thumbprint by viewing the certificate with CertMgr.</span></span> <span data-ttu-id="af0f2-307">Les instructions pour afficher l’empreinte numérique avec CertMgr se trouvent dans la section [créer ou modifier les scripts du gestionnaire de configuration SEMM](#create-or-modify-the-semm-configuration-manager-scripts) de cet article.</span><span class="sxs-lookup"><span data-stu-id="af0f2-307">Instructions for viewing the thumbprint with CertMgr are in the [Create or modify the SEMM Configuration Manager scripts](#create-or-modify-the-semm-configuration-manager-scripts) section of this article.</span></span>

<span data-ttu-id="af0f2-308">La suppression de SEMM à partir d’un appareil déployé avec Configuration Manager à l’aide de ces scripts est aussi simple que la désinstallation de l’application avec Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="af0f2-308">Removal of SEMM from a device deployed with Configuration Manager using these scripts is as easy as uninstalling the application with Configuration Manager.</span></span> <span data-ttu-id="af0f2-309">Cette action démarre le script ResetSEMM.ps1 et désinscrit correctement l’appareil avec le même fichier de certificat que celui utilisé lors du déploiement de SEMM.</span><span class="sxs-lookup"><span data-stu-id="af0f2-309">This action starts the ResetSEMM.ps1 script and properly unenrolls the device with the same certificate file that was used during the deployment of SEMM.</span></span>

> [!NOTE]
> <span data-ttu-id="af0f2-310">Microsoft surface recommande de créer des packages de réinitialisation uniquement lorsque vous avez besoin d’annuler l’inscription d’un appareil.</span><span class="sxs-lookup"><span data-stu-id="af0f2-310">Microsoft Surface recommends that you create reset packages only when you need to unenroll a device.</span></span> <span data-ttu-id="af0f2-311">Ces packages de réinitialisation sont généralement valides pour un seul appareil et identifiés par leur numéro de série.</span><span class="sxs-lookup"><span data-stu-id="af0f2-311">These reset packages are typically valid for only one device, identified by its serial number.</span></span> <span data-ttu-id="af0f2-312">En revanche, vous pouvez créer un package de réinitialisation universel qui fonctionne pour tous les appareils inscrits dans SEMM avec ce certificat.</span><span class="sxs-lookup"><span data-stu-id="af0f2-312">You can, however, create a universal reset package that would work for any device enrolled in SEMM with this certificate.</span></span>
> 
> <span data-ttu-id="af0f2-313">Nous vous recommandons vivement de protéger votre package de réinitialisation universelle comme le certificat que vous avez utilisé pour inscrire des appareils dans SEMM.</span><span class="sxs-lookup"><span data-stu-id="af0f2-313">We strongly recommend that you protect your universal reset package as carefully as the certificate you used to enroll devices in SEMM.</span></span> <span data-ttu-id="af0f2-314">N’oubliez pas que, comme le certificat lui-même, ce package de réinitialisation universelle peut être utilisé pour annuler l’inscription de n’importe quel appareil surface de votre organisation à partir de SEMM.</span><span class="sxs-lookup"><span data-stu-id="af0f2-314">Please remember that, just like the certificate itself, this universal reset package can be used to unenroll any of your organization’s Surface devices from SEMM.</span></span>
> 
> <span data-ttu-id="af0f2-315">Lorsque vous installez un package de réinitialisation, la valeur la plus basse prise en charge (LSV) est redéfinie sur 1.</span><span class="sxs-lookup"><span data-stu-id="af0f2-315">When you install a reset package, the Lowest Supported Value (LSV) is reset to a value of 1.</span></span> <span data-ttu-id="af0f2-316">Vous pouvez réinscrire un appareil à l’aide d’un package de configuration existant.</span><span class="sxs-lookup"><span data-stu-id="af0f2-316">You can reenroll a device by using an existing configuration package.</span></span> <span data-ttu-id="af0f2-317">L’appareil vous invitera à entrer l’empreinte du certificat avant la prise de la propriété.</span><span class="sxs-lookup"><span data-stu-id="af0f2-317">The device will prompt for the certificate thumbprint before ownership is taken.</span></span>
> 
> <span data-ttu-id="af0f2-318">C’est la raison pour laquelle la réinscription d’un appareil dans SEMM nécessite la création et l’installation d’un nouveau package sur cet appareil.</span><span class="sxs-lookup"><span data-stu-id="af0f2-318">For this reason, the reenrollment of a device in SEMM would require a new package to be created and installed on that device.</span></span> <span data-ttu-id="af0f2-319">Dans la mesure où cette action est une nouvelle inscription et pas une modification de la configuration sur un appareil déjà inscrit dans SEMM, l’appareil vous invite à entrer l’empreinte du certificat avant la prise de la propriété.</span><span class="sxs-lookup"><span data-stu-id="af0f2-319">Because this action is a new enrollment and not a change in configuration on a device already enrolled in SEMM, the device will prompt for the certificate thumbprint before ownership is taken.</span></span>
