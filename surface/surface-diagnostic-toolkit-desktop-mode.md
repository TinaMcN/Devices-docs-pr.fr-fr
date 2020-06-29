---
title: Utiliser le Kit de ressources de diagnostic pour Surface Entreprise en mode bureau
description: Comment utiliser SDT pour aider les utilisateurs de votre organisation à exécuter l’outil d’identification et de diagnostic des problèmes avec le périphérique surface.
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: hachidan
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: 9e6b34a8d34081fc12cab4851104f0b67c3dfea4
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832219"
---
# <span data-ttu-id="b20b0-103">Utiliser le Kit de ressources de diagnostic pour Surface Entreprise en mode bureau</span><span class="sxs-lookup"><span data-stu-id="b20b0-103">Use Surface Diagnostic Toolkit for Business in desktop mode</span></span>

<span data-ttu-id="b20b0-104">Cette rubrique explique comment utiliser le kit de ressources de diagnostic de surface (SDT) pour aider les utilisateurs de votre organisation à exécuter l’outil d’identification et de diagnostic des problèmes liés à l’appareil surface.</span><span class="sxs-lookup"><span data-stu-id="b20b0-104">This topic explains how to use the Surface Diagnostic Toolkit (SDT) to help users in your organization run the tool to identify and diagnose issues with the Surface device.</span></span> <span data-ttu-id="b20b0-105">L’exécution réussie de SDT peut déterminer rapidement si un problème signalé est lié à un problème de matériel ou d’erreur d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b20b0-105">Successfully running SDT can quickly determine if a reported issue is caused by failed hardware or user error.</span></span> <span data-ttu-id="b20b0-106">Pour obtenir la liste des appareils surface pris en charge dans le SDT, voir [déploiement de surface diagnostic Toolkit pour les entreprises](surface-diagnostic-toolkit-business.md).</span><span class="sxs-lookup"><span data-stu-id="b20b0-106">For a list of supported Surface devices in SDT, refer to [Deploy Surface Diagnostic Toolkit for Business](surface-diagnostic-toolkit-business.md).</span></span>


1. <span data-ttu-id="b20b0-107">Demandez à l’utilisateur d’installer [le package SDT](surface-diagnostic-toolkit-business.md#create-custom-sdt) à partir d’un point de distribution de logiciels ou d’un partage réseau.</span><span class="sxs-lookup"><span data-stu-id="b20b0-107">Direct the user to install [the SDT package](surface-diagnostic-toolkit-business.md#create-custom-sdt) from a software distribution point or network share.</span></span> <span data-ttu-id="b20b0-108">Une fois l’installation terminée, vous pouvez guider l’utilisateur dans le cadre d’une série de tests.</span><span class="sxs-lookup"><span data-stu-id="b20b0-108">After it is installed, you’re ready to guide the user through a series of tests.</span></span> 

2. <span data-ttu-id="b20b0-109">Commencez sur la page d’accueil, qui permet aux utilisateurs d’entrer une description du problème, puis cliquez sur **Continuer**, comme illustré dans la figure 1.</span><span class="sxs-lookup"><span data-stu-id="b20b0-109">Begin at the home page, which allows users to enter a description of the issue, and click **Continue**, as shown in figure 1.</span></span>

    ![<span data-ttu-id="b20b0-110">Démarrer le SDT en mode Bureau ](images/sdt-desk-1.png)
 *figure 1. SDT en mode Bureau*</span><span class="sxs-lookup"><span data-stu-id="b20b0-110">Start SDT in desktop mode](images/sdt-desk-1.png)
*Figure 1. SDT in desktop mode*</span></span>

3. <span data-ttu-id="b20b0-111">Lorsque le SDT indique que l’appareil comporte les mises à jour les plus récentes, cliquez sur **Continuer** pour accéder au catalogue de tests disponibles, comme illustré dans la figure 2.</span><span class="sxs-lookup"><span data-stu-id="b20b0-111">When SDT indicates the device has the latest updates, click **Continue** to advance to the catalog of available tests, as shown in figure 2.</span></span>

    ![<span data-ttu-id="b20b0-112">Sélectionnez à partir des options SDT ](images/sdt-desk-2.png)
 *figure 2. Sélectionner à partir des options SDT*</span><span class="sxs-lookup"><span data-stu-id="b20b0-112">Select from SDT options](images/sdt-desk-2.png)
*Figure 2. Select from SDT options*</span></span>

4. <span data-ttu-id="b20b0-113">Vous pouvez choisir d’exécuter tous les tests de diagnostic.</span><span class="sxs-lookup"><span data-stu-id="b20b0-113">You can choose to run all the diagnostic tests.</span></span> <span data-ttu-id="b20b0-114">Ou, si vous soupçonnez un problème particulier tel qu’un affichage défectueux ou un problème d’alimentation électrique, cliquez sur **Sélectionner** pour effectuer votre choix parmi les tests disponibles, puis cliquez sur **exécuter la sélection**, comme illustré dans la figure 3.</span><span class="sxs-lookup"><span data-stu-id="b20b0-114">Or, if you already suspect a particular issue such as a faulty display or a power supply problem, click **Select** to choose from the available tests and click **Run Selected**, as shown in figure 3.</span></span> <span data-ttu-id="b20b0-115">Pour plus d’informations sur chaque test, consultez le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="b20b0-115">See the following table for details of each test.</span></span> 

    ![<span data-ttu-id="b20b0-116">Sélectionnez tests matériels ](images/sdt-desk-3.png)
 *figure 3. Sélectionner tests matériels*</span><span class="sxs-lookup"><span data-stu-id="b20b0-116">Select hardware tests](images/sdt-desk-3.png)
*Figure 3. Select hardware tests*</span></span>

    <span data-ttu-id="b20b0-117">Test du matériel</span><span class="sxs-lookup"><span data-stu-id="b20b0-117">Hardware test</span></span> | <span data-ttu-id="b20b0-118">Description</span><span class="sxs-lookup"><span data-stu-id="b20b0-118">Description</span></span>
    --- | ---
    <span data-ttu-id="b20b0-119">Alimentation électrique et batterie</span><span class="sxs-lookup"><span data-stu-id="b20b0-119">Power Supply and Battery</span></span> |  <span data-ttu-id="b20b0-120">Vérifie que l’alimentation secteur fonctionne de façon optimale.</span><span class="sxs-lookup"><span data-stu-id="b20b0-120">Checks Power supply is functioning optimally</span></span>
    <span data-ttu-id="b20b0-121">Affichage et son</span><span class="sxs-lookup"><span data-stu-id="b20b0-121">Display and Sound</span></span>   | <span data-ttu-id="b20b0-122">Contrôle le fonctionnement de la luminosité, du son coincé ou du micro</span><span class="sxs-lookup"><span data-stu-id="b20b0-122">Checks brightness, stuck or dead pixels, speaker and microphone functioning</span></span>
    <span data-ttu-id="b20b0-123">Ports et accessoires</span><span class="sxs-lookup"><span data-stu-id="b20b0-123">Ports and Accessories</span></span>   | <span data-ttu-id="b20b0-124">Vérifie les accessoires, l’ajout d’écran et le fonctionnement USB</span><span class="sxs-lookup"><span data-stu-id="b20b0-124">Checks accessories, screen attach and USB functioning</span></span>
    <span data-ttu-id="b20b0-125">Connectivité</span><span class="sxs-lookup"><span data-stu-id="b20b0-125">Connectivity</span></span> |  <span data-ttu-id="b20b0-126">Vérifie la connectivité Bluetooth, sans fil et LTE</span><span class="sxs-lookup"><span data-stu-id="b20b0-126">Checks Bluetooth, wireless and LTE connectivity</span></span>
    <span data-ttu-id="b20b0-127">Sécurité</span><span class="sxs-lookup"><span data-stu-id="b20b0-127">Security</span></span>    | <span data-ttu-id="b20b0-128">Vérifie les problèmes liés à la sécurité</span><span class="sxs-lookup"><span data-stu-id="b20b0-128">Checks security related issues</span></span>
    <span data-ttu-id="b20b0-129">Commandes tactiles</span><span class="sxs-lookup"><span data-stu-id="b20b0-129">Touch</span></span>   | <span data-ttu-id="b20b0-130">Vérifie les problèmes liés à l’interaction</span><span class="sxs-lookup"><span data-stu-id="b20b0-130">Checks touch related issues</span></span>
    <span data-ttu-id="b20b0-131">Clavier et fonctions vocales</span><span class="sxs-lookup"><span data-stu-id="b20b0-131">Keyboard and touch</span></span> |    <span data-ttu-id="b20b0-132">Vérifie la connexion au clavier intégrée et la couverture de type</span><span class="sxs-lookup"><span data-stu-id="b20b0-132">Checks integrated keyboard connection and type cover</span></span>
    <span data-ttu-id="b20b0-133">Capteurs</span><span class="sxs-lookup"><span data-stu-id="b20b0-133">Sensors</span></span> | <span data-ttu-id="b20b0-134">Vérifie le fonctionnement de différents capteurs dans l’appareil.</span><span class="sxs-lookup"><span data-stu-id="b20b0-134">Checks functioning of different sensors in the device</span></span>
    <span data-ttu-id="b20b0-135">Matériel</span><span class="sxs-lookup"><span data-stu-id="b20b0-135">Hardware</span></span> |  <span data-ttu-id="b20b0-136">Vérifie les problèmes liés à différents composants matériels tels que la carte graphique et l’appareil photo</span><span class="sxs-lookup"><span data-stu-id="b20b0-136">Checks issues with different hardware components such as graphics card and camera</span></span>





<span id="multiple" />

## <span data-ttu-id="b20b0-137">Exécution de plusieurs tests matériels pour résoudre les problèmes</span><span class="sxs-lookup"><span data-stu-id="b20b0-137">Running multiple hardware tests to troubleshoot issues</span></span>

<span data-ttu-id="b20b0-138">Le SDT est conçu comme un outil interactif qui exécute une série de tests.</span><span class="sxs-lookup"><span data-stu-id="b20b0-138">SDT is designed as an interactive tool that runs a series of tests.</span></span> <span data-ttu-id="b20b0-139">Pour chaque test, le SDT fournit des instructions résumant la nature du test, ainsi que les utilisateurs qui doivent s’attendre à la réussite pour le test.</span><span class="sxs-lookup"><span data-stu-id="b20b0-139">For each test, SDT provides instructions summarizing  the nature of the test and what users should expect or look for in order for the test to be successful.</span></span> <span data-ttu-id="b20b0-140">Par exemple, pour diagnostiquer le bon fonctionnement de la luminosité de l’écran, le SDT démarre à zéro et augmente la luminosité à 100 pour cent, demandant aux utilisateurs de confirmer, en répondant à **Yes** ou **no** --la luminosité fonctionne comme prévu, comme illustré dans la figure 4.</span><span class="sxs-lookup"><span data-stu-id="b20b0-140">For example, to diagnose if the display brightness is working properly, SDT starts at zero and increases the brightness to 100 percent, asking users to confirm – by answering **Yes** or **No** -- that brightness is functioning as expected, as shown in figure 4.</span></span> 

<span data-ttu-id="b20b0-141">Pour chaque test, si la fonctionnalité ne fonctionne pas comme prévu et que l’utilisateur clique sur **non**, Sdt génère un rapport des causes possibles et des moyens de résoudre les problèmes.</span><span class="sxs-lookup"><span data-stu-id="b20b0-141">For each test, if functionality does not work as expected and the user clicks **No**, SDT generates a report of the possible causes and ways to troubleshoot it.</span></span> 

![<span data-ttu-id="b20b0-142">Exécution des tests de diagnostic de matériel ](images/sdt-desk-4.png)
 *figure 4. Exécution de diagnostics de matériel*</span><span class="sxs-lookup"><span data-stu-id="b20b0-142">Running hardware diagnostics](images/sdt-desk-4.png)
*Figure 4. Running hardware diagnostics*</span></span>

1. <span data-ttu-id="b20b0-143">Si la luminosité est ajustée à partir de 0-100% comme prévu, demandez à l’utilisateur de cliquer sur **Oui** , puis cliquez sur **Continuer**.</span><span class="sxs-lookup"><span data-stu-id="b20b0-143">If the brightness successfully adjusts from 0-100 percent as expected, direct the user to click **Yes** and then click **Continue**.</span></span> 
2. <span data-ttu-id="b20b0-144">Si la luminosité ne s’ajuste pas à partir de 0-100% comme prévu, demandez à l’utilisateur de cliquer sur **non** , puis sur **Continuer**.</span><span class="sxs-lookup"><span data-stu-id="b20b0-144">If the brightness fails to adjust from 0-100 percent as expected, direct the user to click **No** and then click **Continue**.</span></span> 
3. <span data-ttu-id="b20b0-145">Guidez les utilisateurs dans les tests restants, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="b20b0-145">Guide users through remaining tests as appropriate.</span></span> <span data-ttu-id="b20b0-146">Lorsque vous avez terminé, SDT fournit automatiquement une synthèse générale du rapport, y compris les causes possibles des problèmes matériels et des recommandations en matière de résolution.</span><span class="sxs-lookup"><span data-stu-id="b20b0-146">When finished, SDT automatically provides a high-level summary of the report, including the possible causes of any hardware issues along with guidance for resolution.</span></span>


### <span data-ttu-id="b20b0-147">Réparation d’applications</span><span class="sxs-lookup"><span data-stu-id="b20b0-147">Repairing applications</span></span>

<span data-ttu-id="b20b0-148">Le SDT vous permet de diagnostiquer et réparer des applications susceptibles de causer des problèmes, comme illustré dans la figure 5.</span><span class="sxs-lookup"><span data-stu-id="b20b0-148">SDT enables you to diagnose and repair applications that may be causing issues, as shown in figure 5.</span></span>

![<span data-ttu-id="b20b0-149">Exécution des réparations ](images/sdt-desk-5.png)
 *figure 5. Exécution des réparations*</span><span class="sxs-lookup"><span data-stu-id="b20b0-149">Running repairs](images/sdt-desk-5.png)
*Figure 5. Running repairs*</span></span>
<span id="logs" />

### <span data-ttu-id="b20b0-150">Génération de journaux pour l’analyse des problèmes</span><span class="sxs-lookup"><span data-stu-id="b20b0-150">Generating logs for analyzing issues</span></span> 

<span data-ttu-id="b20b0-151">SDT fournit une prise en charge complète du diagnostic compatible avec les applications, les pilotes, le matériel et les problèmes de système d’exploitation, comme illustré dans la figure 6.</span><span class="sxs-lookup"><span data-stu-id="b20b0-151">SDT provides extensive log-enabled diagnosis support across applications, drivers, hardware, and operating system issues, as shown in figure 6.</span></span>

![<span data-ttu-id="b20b0-152">Génération de journaux ](images/sdt-desk-6.png)
 *figure 6. Génération de journaux*</span><span class="sxs-lookup"><span data-stu-id="b20b0-152">Generating logs](images/sdt-desk-6.png)
*Figure 6. Generating logs*</span></span>

<span id="detailed-report" />

### <span data-ttu-id="b20b0-153">Génération d’un rapport détaillé comparant l’appareil et la configuration optimale</span><span class="sxs-lookup"><span data-stu-id="b20b0-153">Generating detailed report comparing device vs. optimal configuration</span></span>

<span data-ttu-id="b20b0-154">D’après les journaux, SDT génère un rapport pour les problèmes de logiciels et de microprogrammes que vous pouvez enregistrer dans un emplacement préféré.</span><span class="sxs-lookup"><span data-stu-id="b20b0-154">Based on the logs, SDT generates a report for software- and firmware-based issues that you can save to a preferred location.</span></span>

## <span data-ttu-id="b20b0-155">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="b20b0-155">Related topics</span></span>

- [<span data-ttu-id="b20b0-156">Exécuter le Kit de ressources de diagnostic pour Surface Entreprise à l’aide de commandes</span><span class="sxs-lookup"><span data-stu-id="b20b0-156">Run Surface Diagnostic Toolkit for Business using commands</span></span>](surface-diagnostic-toolkit-command-line.md)

