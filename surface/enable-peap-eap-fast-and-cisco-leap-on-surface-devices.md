---
title: ActiverPEAP, EAP-FAST et CiscoLEAP sur des appareilsSurface
description: Découvrez comment activer la prise en charge des protocolesPEAP, EAP-FAST ou CiscoLEAP sur votre appareilSurface.
ms.assetid: A281EFA3-1552-467D-8A21-EB151E58856D
ms.reviewer: ''
manager: laurawi
keywords: réseau, sans fil, appareil, déployer, authentification, protocole
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.openlocfilehash: 1a9bef0a6e0bfdd4bede1b508b4013fd14e1a0bd
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10833497"
---
# <span data-ttu-id="0ca0c-104">Activer les protocolesPEAP, EAP-FAST et CiscoLEAP sur des appareilsSurface</span><span class="sxs-lookup"><span data-stu-id="0ca0c-104">Enable PEAP, EAP-FAST, and Cisco LEAP on Surface devices</span></span>


<span data-ttu-id="0ca0c-105">Découvrez comment activer la prise en charge des protocolesPEAP, EAP-FAST ou CiscoLEAP sur votre appareilSurface.</span><span class="sxs-lookup"><span data-stu-id="0ca0c-105">Find out how to enable support for PEAP, EAP-FAST, or Cisco LEAP protocols on your Surface device.</span></span>

<span data-ttu-id="0ca0c-106">Si vous utilisez ces protocoles dans votre réseau d’entreprise, vous savez probablement déjà que ces trois protocoles d’authentification sans fil ne sont pas pris en charge par les appareilsSurface prêts à l’emploi.</span><span class="sxs-lookup"><span data-stu-id="0ca0c-106">If you use PEAP, EAP-FAST, or Cisco LEAP in your enterprise network, you probably already know that these three wireless authentication protocols are not supported by Surface devices out of the box.</span></span> <span data-ttu-id="0ca0c-107">Les utilisateurs peuvent s’en rendre compte lorsqu’ils tentent de se connecter à votre réseau sans fil, ou lorsqu’ils constatent qu’ils ne peuvent pas accéder aux ressources situées au sein du réseau (partages de fichiers et sites internes, par exemple).</span><span class="sxs-lookup"><span data-stu-id="0ca0c-107">Some users may discover this when they attempt to connect to your wireless network; others may discover it when they are unable to gain access to resources inside the network, like file shares and internal sites.</span></span> <span data-ttu-id="0ca0c-108">Pour en savoir plus, voir [Extensible Authentication Protocol](https://technet.microsoft.com/network/bb643147).</span><span class="sxs-lookup"><span data-stu-id="0ca0c-108">For more information, see [Extensible Authentication Protocol](https://technet.microsoft.com/network/bb643147).</span></span>

<span data-ttu-id="0ca0c-109">Vous pouvez ajouter la prise en charge de chaque protocole en exécutant un petit packageMSI à partir d’une cléUSB ou d’un partage de fichiers.</span><span class="sxs-lookup"><span data-stu-id="0ca0c-109">You can add support for each protocol by executing a small MSI package from a USB stick or from a file share.</span></span> <span data-ttu-id="0ca0c-110">Pour les organisations qui souhaitent activer la prise en charge du protocole EAP sur leurs appareils surface, le format de package MSI prend en charge le déploiement de nombreux outils de gestion et de déploiement, tels que Microsoft Deployment Toolkit (MDT) et Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="0ca0c-110">For organizations that want to enable EAP support on their Surface devices, the MSI package format supports deployment with many management and deployment tools, like the Microsoft Deployment Toolkit (MDT) and Microsoft Endpoint Configuration Manager.</span></span>

## <a href="" id="download-peap--eap-fast--or-cisco-leap-installation-files--"></a><span data-ttu-id="0ca0c-111">Télécharger les fichiers d’installation des protocolesPEAP, EAP-FAST ou CiscoLEAP</span><span class="sxs-lookup"><span data-stu-id="0ca0c-111">Download PEAP, EAP-FAST, or Cisco LEAP installation files</span></span>


<span data-ttu-id="0ca0c-112">Vous pouvez télécharger les fichiers d’installationMSI pour PEAP, EAP-FAST ou CiscoLEAP dans un fichier d’archivezip unique à partir du Centre de téléchargementMicrosoft.</span><span class="sxs-lookup"><span data-stu-id="0ca0c-112">You can download the MSI installation files for PEAP, EAP-FAST, or Cisco LEAP in a single zip archive file from the Microsoft Download Center.</span></span> <span data-ttu-id="0ca0c-113">Pour télécharger ce fichier, accédez à la page du Centre de téléchargementMicrosoft relative à [SurfaceTools for IT](https://www.microsoft.com/download/details.aspx?id=46703), cliquez sur **Télécharger**, puis sélectionnez le fichier **Cisco EAP-Supplicant Installer.zip**.</span><span class="sxs-lookup"><span data-stu-id="0ca0c-113">To download this file, go to the [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) page on the Microsoft Download Center, click **Download**, and then select the **Cisco EAP-Supplicant Installer.zip** file.</span></span>

## <span data-ttu-id="0ca0c-114">Déployer les protocolesPEAP, EAP-FAST ou CiscoLEAP avec MDT</span><span class="sxs-lookup"><span data-stu-id="0ca0c-114">Deploy PEAP, EAP-FAST, or Cisco LEAP with MDT</span></span>


<span data-ttu-id="0ca0c-115">Si vous effectuez déjà un déploiement de Windows sur des appareilsSurface dans votre entreprise, vous pouvez rapidement ajouter des fichiers d’installation pour chaque protocole dans votre partage de déploiement et configurer l’installation automatique lors du déploiement, en toute simplicité.</span><span class="sxs-lookup"><span data-stu-id="0ca0c-115">If you are already performing a Windows deployment to Surface devices in your organization, it is quick and easy to add the installation files for each protocol to your deployment share and configure automatic installation during deployment.</span></span> <span data-ttu-id="0ca0c-116">Il est même possible de configurer une séquence de tâches qui mette à jour les appareilsSurface précédemment déployés, afin d’assurer la prise en charge de ces protocoles, via le même processus.</span><span class="sxs-lookup"><span data-stu-id="0ca0c-116">You can even configure a task sequence that updates previously deployed Surface devices to provide support for these protocols using the same process.</span></span>

<span data-ttu-id="0ca0c-117">Pour activer la prise en charge de PEAP, EAP-FAST ou CiscoLEAP sur des appareilsSurface récemment déployés, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="0ca0c-117">To enable support for PEAP, EAP-FAST, or Cisco LEAP on newly deployed Surface devices, follow these steps:</span></span>

1.  <span data-ttu-id="0ca0c-118">Téléchargez et installez les fichiers d’installation de chaque protocole dans des dossiers distincts faciles d’accès.</span><span class="sxs-lookup"><span data-stu-id="0ca0c-118">Download and extract the installation files for each protocol to separate folders in an easily accessible location.</span></span>

2.  <span data-ttu-id="0ca0c-119">Ouvrez MDTDeploymentWorkbench et développez votre partage de déploiement, sur le dossier **Applications**.</span><span class="sxs-lookup"><span data-stu-id="0ca0c-119">Open the MDT Deployment Workbench and expand your deployment share to the **Applications** folder.</span></span>

3.  <span data-ttu-id="0ca0c-120">Sélectionnez **Nouvelle application** dans le volet **Action**.</span><span class="sxs-lookup"><span data-stu-id="0ca0c-120">Select **New Application** from the **Action** pane.</span></span>

4.  <span data-ttu-id="0ca0c-121">Choisissez **Application avec les fichiers sources** pour copier les fichiersMSI dans le partage de déploiement.</span><span class="sxs-lookup"><span data-stu-id="0ca0c-121">Choose **Application with source files** to copy the MSI files into the Deployment Share.</span></span>

5.  <span data-ttu-id="0ca0c-122">Sélectionnez le dossier que vous avez créé à l’étape1 pour le protocole souhaité.</span><span class="sxs-lookup"><span data-stu-id="0ca0c-122">Select the folder you created in step 1 for the desired protocol.</span></span>

6.  <span data-ttu-id="0ca0c-123">Nommez le dossier dans le partage de déploiement dans lequel les fichiers d’installation doivent être stockés.</span><span class="sxs-lookup"><span data-stu-id="0ca0c-123">Name the folder in the deployment share where the installation files will be stored.</span></span>

7.  <span data-ttu-id="0ca0c-124">Spécifiez la ligne de commande permettant de déployer l’application:</span><span class="sxs-lookup"><span data-stu-id="0ca0c-124">Specify the command line to deploy the application:</span></span>

    -   <span data-ttu-id="0ca0c-125">Pour PEAP: **EAP-PEAP.msi /qn /norestart**.</span><span class="sxs-lookup"><span data-stu-id="0ca0c-125">For PEAP use **EAP-PEAP.msi /qn /norestart**.</span></span>

    -   <span data-ttu-id="0ca0c-126">Pour LEAP: **EAP-LEAP.msi /qn /norestart**.</span><span class="sxs-lookup"><span data-stu-id="0ca0c-126">For LEAP use **EAP-LEAP.msi /qn /norestart**.</span></span>

    -   <span data-ttu-id="0ca0c-127">Pour EAP-FAST: **EAP-FAST.msi /qn /norestart**.</span><span class="sxs-lookup"><span data-stu-id="0ca0c-127">For EAP-FAST use **EAP-FAST.msi /qn /norestart**.</span></span>

8.  <span data-ttu-id="0ca0c-128">Pour l’Assistant Nouvelleapplication, utilisez les options par défaut.</span><span class="sxs-lookup"><span data-stu-id="0ca0c-128">Use the default options to complete the New Application Wizard.</span></span>

9.  <span data-ttu-id="0ca0c-129">Répétez les étapes3 à 8 pour chaque protocole souhaité.</span><span class="sxs-lookup"><span data-stu-id="0ca0c-129">Repeat steps 3 through 8 for each desired protocol.</span></span>

<span data-ttu-id="0ca0c-130">Une fois que vous avez exécuté ces étapes et importé les trois packagesMSI en tant qu’applications dans MDT, vous pouvez sélectionner ces derniers dans la pageApplications de l’Assistant de déploiement Windows.</span><span class="sxs-lookup"><span data-stu-id="0ca0c-130">After you’ve performed these steps to import the three MSI packages as applications into MDT, they will be available for selection in the Applications page of the Windows Deployment Wizard.</span></span> <span data-ttu-id="0ca0c-131">Dans certains scénarios de déploiement simples, la sélection de chaque package, par le technicien, lors du déploiement, peut suffire, mais ce n’est pas recommandé.</span><span class="sxs-lookup"><span data-stu-id="0ca0c-131">Although in some simple deployment scenarios it might be sufficient to have technicians select each package at the time of deployment, it is not recommended.</span></span> <span data-ttu-id="0ca0c-132">En effet, il se peut que le technicien tente d’appliquer ces packages à des ordinateurs autres que des appareilsSurface, ou qu’un appareilSurface soit déployé sans que la prise en charge du protocoleEAP ne soit activée, suite à une erreur humaine.</span><span class="sxs-lookup"><span data-stu-id="0ca0c-132">This practice introduces the possibility that a technician could attempt to apply these packages to computers other than Surface devices, or that a Surface device could be deployed without EAP support due to human error.</span></span>

<span data-ttu-id="0ca0c-133">Pour masquer ces applications à partir de la pageInstaller des applications, cochez la case **Masquer cette application dans l’Assistant de déploiement** dans les propriétés de chaque application.</span><span class="sxs-lookup"><span data-stu-id="0ca0c-133">To hide these applications from the Install Applications page, select the **Hide this application in the Deployment Wizard** checkbox in the properties of each application.</span></span> <span data-ttu-id="0ca0c-134">Une fois masquées, les applications n’apparaissent pas comme facultatives lors du déploiement.</span><span class="sxs-lookup"><span data-stu-id="0ca0c-134">After the applications are hidden, they will not be displayed as optional applications during deployment.</span></span> <span data-ttu-id="0ca0c-135">Pour pouvoir les déployer au cours de votre séquence de tâches de déploiementSurface, vous devez les définir de manière explicite pour une installation via une étape distincte de cette séquence.</span><span class="sxs-lookup"><span data-stu-id="0ca0c-135">To deploy them in your Surface deployment task sequence, they must be explicitly defined for installation through a separate step in the task sequence.</span></span>

<span data-ttu-id="0ca0c-136">Pour spécifier le ou les protocoles de manière explicite, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="0ca0c-136">To specify the protocol(s) explicitly, follow these steps:</span></span>

1.  <span data-ttu-id="0ca0c-137">Ouvrez les propriétés de la séquence de tâches de déploiement de votre appareilSurface dans MDTDeploymentWorkbench.</span><span class="sxs-lookup"><span data-stu-id="0ca0c-137">Open your Surface deployment task sequence properties from the MDT Deployment Workbench.</span></span>

2.  <span data-ttu-id="0ca0c-138">Sur l’onglet **Séquence de tâches**, sélectionnez l’étape **Installer les applications**, sous **Restauration de l’état**.</span><span class="sxs-lookup"><span data-stu-id="0ca0c-138">On the **Task Sequence** tab, select the **Install Applications** step under **State Restore**.</span></span> <span data-ttu-id="0ca0c-139">En général, elle se trouve entre les étapes de mise à jour deWindows avant et après l’application.</span><span class="sxs-lookup"><span data-stu-id="0ca0c-139">This is typically found between the pre-application and post-application Windows Update steps.</span></span>

3.  <span data-ttu-id="0ca0c-140">Utilisez le bouton **Ajouter** pour créer une étape **Installer l’application** dans la catégorie **Général**.</span><span class="sxs-lookup"><span data-stu-id="0ca0c-140">Use the **Add** button to create a new **Install Application** step from the **General** category.</span></span>

4.  <span data-ttu-id="0ca0c-141">Sélectionnez **Installer une seule application** dans l’onglet **Propriétés** de l’étape.</span><span class="sxs-lookup"><span data-stu-id="0ca0c-141">Select **Install a single application** in the step **Properties** tab.</span></span>

5.  <span data-ttu-id="0ca0c-142">Sélectionnez le protocoleEAP souhaité dans la liste.</span><span class="sxs-lookup"><span data-stu-id="0ca0c-142">Select the desired EAP protocol from the list.</span></span>

6.  <span data-ttu-id="0ca0c-143">Répétez les étapes2 à 5 pour chaque protocole souhaité.</span><span class="sxs-lookup"><span data-stu-id="0ca0c-143">Repeat steps 2 through 5 for each desired protocol.</span></span>

## <span data-ttu-id="0ca0c-144">Déployer les protocolesPEAP, EAP-FAST ou CiscoLEAP avec SystemCenterConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="0ca0c-144">Deploy PEAP, EAP-FAST, or Cisco LEAP with Configuration Manager</span></span>


<span data-ttu-id="0ca0c-145">Pour les organisations qui gèrent les appareilsSurface avec le SystemCenterConfigurationManager, il est encore plus simple de déployer la prise en charge des protocolesPEAP, EAP-FAST ou CiscoLEAP sur les appareilsSurface.</span><span class="sxs-lookup"><span data-stu-id="0ca0c-145">For organizations that manage Surface devices with Configuration Manager, it is even easier to deploy PEAP, EAP-FAST, or Cisco LEAP support to Surface devices.</span></span> <span data-ttu-id="0ca0c-146">Il vous suffit d’importer chaque fichierMSI en tant qu’application à partir de la bibliothèque de logiciels et de configurer un déploiement dans votre regroupement d’appareilsSurface.</span><span class="sxs-lookup"><span data-stu-id="0ca0c-146">Simply import each MSI file as an application from the Software Library and configure a deployment to your Surface device collection.</span></span>

<span data-ttu-id="0ca0c-147">Pour en savoir plus sur le déploiement des applications avec ConfigurationManager, voir [Comment créer des applications dans ConfigurationManager](https://technet.microsoft.com/library/gg682159.aspx) et [Comment déployer des applications dans ConfigurationManager](https://technet.microsoft.com/library/gg682082.aspx).</span><span class="sxs-lookup"><span data-stu-id="0ca0c-147">For more information on how to deploy applications with Configuration Manager see [How to Create Applications in Configuration Manager](https://technet.microsoft.com/library/gg682159.aspx) and [How to Deploy Applications in Configuration Manager](https://technet.microsoft.com/library/gg682082.aspx).</span></span>

 

 





