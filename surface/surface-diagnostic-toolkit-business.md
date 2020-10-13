---
title: Déploiement du Kit de ressources de diagnostic pour Surface Entreprise
description: Cette rubrique explique comment utiliser le kit de gestion de surface diagnostic pour les entreprises.
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 10/12/2020
ms.reviewer: hachidan
manager: laurawi
audience: itpro
ms.openlocfilehash: 1f2661811516507abd432dba602cf8ce81e6dbb3
ms.sourcegitcommit: c1efb75e8524193bdc0a5f7496dc23a92ac665c8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/12/2020
ms.locfileid: "11114662"
---
# <span data-ttu-id="45646-103">Déploiement du Kit de ressources de diagnostic pour Surface Entreprise</span><span class="sxs-lookup"><span data-stu-id="45646-103">Deploy Surface Diagnostic Toolkit for Business</span></span>

<span data-ttu-id="45646-104">Le kit de ressources pour les Diagnostics Microsoft surface pour les entreprises (SDT) permet aux administrateurs informatiques de rechercher rapidement et de résoudre les problèmes liés au matériel, au logiciel et au microprogramme des appareils surface.</span><span class="sxs-lookup"><span data-stu-id="45646-104">The Microsoft Surface Diagnostic Toolkit for Business (SDT) enables IT administrators to quickly investigate, troubleshoot, and resolve hardware, software, and firmware issues with Surface devices.</span></span> <span data-ttu-id="45646-105">Vous pouvez exécuter une gamme de tests de diagnostic et de réparations logicielles en plus d’informations sur l’obtention d’informations sur l’état de l’appareil et des instructions pour la résolution des problèmes.</span><span class="sxs-lookup"><span data-stu-id="45646-105">You can run a range of diagnostic tests and software repairs in addition to obtaining device health insights and guidance for resolving issues.</span></span> 

<span data-ttu-id="45646-106">En particulier, SDT pour les entreprises vous permet d’effectuer les opérations suivantes:</span><span class="sxs-lookup"><span data-stu-id="45646-106">Specifically, SDT for Business enables you to:</span></span>

- [<span data-ttu-id="45646-107">Personnaliser le package.</span><span class="sxs-lookup"><span data-stu-id="45646-107">Customize the package.</span></span>](#create-custom-sdt)
- [<span data-ttu-id="45646-108">Exécutez l’application à l’aide de commandes.</span><span class="sxs-lookup"><span data-stu-id="45646-108">Run the app using commands.</span></span>](surface-diagnostic-toolkit-command-line.md)
- [<span data-ttu-id="45646-109">Exécutez plusieurs tests matériels pour résoudre les problèmes.</span><span class="sxs-lookup"><span data-stu-id="45646-109">Run multiple hardware tests to troubleshoot issues.</span></span>](surface-diagnostic-toolkit-desktop-mode.md#multiple)
- [<span data-ttu-id="45646-110">Génération de journaux pour l’analyse des problèmes.</span><span class="sxs-lookup"><span data-stu-id="45646-110">Generate logs for analyzing issues.</span></span>](surface-diagnostic-toolkit-desktop-mode.md#logs)
- [<span data-ttu-id="45646-111">Obtenez un rapport détaillé comparant la configuration de l’appareil et de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="45646-111">Obtain detailed report comparing device vs optimal configuration.</span></span>](surface-diagnostic-toolkit-desktop-mode.md#detailed-report)


## <span data-ttu-id="45646-112">Principaux scénarios et ressources de téléchargement</span><span class="sxs-lookup"><span data-stu-id="45646-112">Primary scenarios and download resources</span></span> 

<span data-ttu-id="45646-113">Pour exécuter SDT pour les entreprises, téléchargez les composants indiqués dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="45646-113">To run SDT for Business, download the components listed in the following table.</span></span>


<span data-ttu-id="45646-114">Mode</span><span class="sxs-lookup"><span data-stu-id="45646-114">Mode</span></span> |  <span data-ttu-id="45646-115">Principaux scénarios</span><span class="sxs-lookup"><span data-stu-id="45646-115">Primary scenarios</span></span> | <span data-ttu-id="45646-116">Télécharger</span><span class="sxs-lookup"><span data-stu-id="45646-116">Download</span></span> | <span data-ttu-id="45646-117">En savoir plus</span><span class="sxs-lookup"><span data-stu-id="45646-117">Learn more</span></span>
--- | --- | --- | ---
<span data-ttu-id="45646-118">Mode bureau</span><span class="sxs-lookup"><span data-stu-id="45646-118">Desktop mode</span></span> |  <span data-ttu-id="45646-119">Aidez les utilisateurs à exécuter SDT sur leurs appareils surface pour résoudre les problèmes.</span><span class="sxs-lookup"><span data-stu-id="45646-119">Assist users in running SDT on their Surface devices to troubleshoot issues.</span></span><br><span data-ttu-id="45646-120">Créer un package personnalisé à déployer sur un ou plusieurs appareils de surface permettant aux utilisateurs de sélectionner des journaux spécifiques à collecter et analyser.</span><span class="sxs-lookup"><span data-stu-id="45646-120">Create a custom package to deploy on one or more Surface devices allowing users to select specific logs to collect and analyze.</span></span> | <span data-ttu-id="45646-121">Package MSI du SDT distribuable:</span><span class="sxs-lookup"><span data-stu-id="45646-121">SDT distributable MSI package:</span></span><br><span data-ttu-id="45646-122">Programme d’installation du kit de connaissances Microsoft surface diagnostic pour les entreprises</span><span class="sxs-lookup"><span data-stu-id="45646-122">Microsoft Surface Diagnostic Toolkit for Business Installer</span></span><br>[<span data-ttu-id="45646-123">Outils Surface pour l'informatique</span><span class="sxs-lookup"><span data-stu-id="45646-123">Surface Tools for IT</span></span>](https://www.microsoft.com/download/details.aspx?id=46703) | [<span data-ttu-id="45646-124">Utiliser le kit de diagnostic de surface pour le mode Bureau</span><span class="sxs-lookup"><span data-stu-id="45646-124">Use Surface Diagnostic Toolkit in desktop mode</span></span>](surface-diagnostic-toolkit-desktop-mode.md)
<span data-ttu-id="45646-125">Ligne de commande</span><span class="sxs-lookup"><span data-stu-id="45646-125">Command line</span></span> |  <span data-ttu-id="45646-126">Résoudre les problèmes liés aux appareils surface à distance sans interaction utilisateur, à l’aide d’outils standard tels que Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="45646-126">Directly troubleshoot Surface devices remotely without user interaction, using standard tools such as Configuration Manager.</span></span> <span data-ttu-id="45646-127">Il inclut les commandes suivantes:</span><span class="sxs-lookup"><span data-stu-id="45646-127">It includes the following commands:</span></span><br>`-DataCollector` <span data-ttu-id="45646-128">recueille tous les fichiers journaux</span><span class="sxs-lookup"><span data-stu-id="45646-128">collects all log files</span></span><br>`-bpa` <span data-ttu-id="45646-129">exécute des diagnostics d’intégrité à l’aide de la méthode recommandée Analyzer.</span><span class="sxs-lookup"><span data-stu-id="45646-129">runs health diagnostics using Best Practice Analyzer.</span></span><br>`-windowsupdate` <span data-ttu-id="45646-130">vérifie Windows Update pour les mises à jour de microprogramme ou de pilote manquantes.</span><span class="sxs-lookup"><span data-stu-id="45646-130">checks Windows Update for missing firmware or driver updates.</span></span><br>`-warranty` <span data-ttu-id="45646-131">vérifie les informations de garantie.</span><span class="sxs-lookup"><span data-stu-id="45646-131">checks warranty information.</span></span> <br><br>| <span data-ttu-id="45646-132">Application console SDT:</span><span class="sxs-lookup"><span data-stu-id="45646-132">SDT console app:</span></span><br><span data-ttu-id="45646-133">Console d’application Diagnostics Microsoft surface</span><span class="sxs-lookup"><span data-stu-id="45646-133">Microsoft Surface Diagnostics App Console</span></span><br>[<span data-ttu-id="45646-134">Outils Surface pour l'informatique</span><span class="sxs-lookup"><span data-stu-id="45646-134">Surface Tools for IT</span></span>](https://www.microsoft.com/download/details.aspx?id=46703) | [<span data-ttu-id="45646-135">Exécuter le kit de diagnostics de surface</span><span class="sxs-lookup"><span data-stu-id="45646-135">Run Surface Diagnostic Toolkit using commands</span></span>](surface-diagnostic-toolkit-command-line.md)

## <span data-ttu-id="45646-136">Appareils pris en charge</span><span class="sxs-lookup"><span data-stu-id="45646-136">Supported devices</span></span> 

<span data-ttu-id="45646-137">Le SDT pour les entreprises est pris en charge sur les appareils surface 3 et les versions ultérieures, notamment:</span><span class="sxs-lookup"><span data-stu-id="45646-137">SDT for Business is supported on Surface 3 and later devices, including:</span></span>

- <span data-ttu-id="45646-138">Surface Laptop Go</span><span class="sxs-lookup"><span data-stu-id="45646-138">Surface Laptop Go</span></span>
- <span data-ttu-id="45646-139">SurfaceBook3</span><span class="sxs-lookup"><span data-stu-id="45646-139">Surface Book 3</span></span>
- <span data-ttu-id="45646-140">SurfaceGo2</span><span class="sxs-lookup"><span data-stu-id="45646-140">Surface Go 2</span></span>
- <span data-ttu-id="45646-141">SurfaceProX</span><span class="sxs-lookup"><span data-stu-id="45646-141">Surface Pro X</span></span>
- <span data-ttu-id="45646-142">SurfacePro7</span><span class="sxs-lookup"><span data-stu-id="45646-142">Surface Pro 7</span></span>
- <span data-ttu-id="45646-143">Surface Laptop3</span><span class="sxs-lookup"><span data-stu-id="45646-143">Surface Laptop 3</span></span>
- <span data-ttu-id="45646-144">SurfacePro6</span><span class="sxs-lookup"><span data-stu-id="45646-144">Surface Pro 6</span></span>
- <span data-ttu-id="45646-145">Surface Laptop2</span><span class="sxs-lookup"><span data-stu-id="45646-145">Surface Laptop 2</span></span>
- <span data-ttu-id="45646-146">SurfaceGo</span><span class="sxs-lookup"><span data-stu-id="45646-146">Surface Go</span></span>
- <span data-ttu-id="45646-147">Surface Go avec LTE</span><span class="sxs-lookup"><span data-stu-id="45646-147">Surface Go with LTE</span></span>
- <span data-ttu-id="45646-148">SurfaceBook2</span><span class="sxs-lookup"><span data-stu-id="45646-148">Surface Book 2</span></span>
- <span data-ttu-id="45646-149">SurfacePro avec LTE Advanced (modèle1807)</span><span class="sxs-lookup"><span data-stu-id="45646-149">Surface Pro with LTE Advanced (Model 1807)</span></span>
- <span data-ttu-id="45646-150">SurfacePro (modèle1796)</span><span class="sxs-lookup"><span data-stu-id="45646-150">Surface Pro (Model 1796)</span></span>
- <span data-ttu-id="45646-151">Surface Laptop</span><span class="sxs-lookup"><span data-stu-id="45646-151">Surface Laptop</span></span>
- <span data-ttu-id="45646-152">SurfaceStudio</span><span class="sxs-lookup"><span data-stu-id="45646-152">Surface Studio</span></span>
- <span data-ttu-id="45646-153">Surface Studio2</span><span class="sxs-lookup"><span data-stu-id="45646-153">Surface Studio 2</span></span>
- <span data-ttu-id="45646-154">SurfaceBook</span><span class="sxs-lookup"><span data-stu-id="45646-154">Surface Book</span></span>
- <span data-ttu-id="45646-155">Surface Pro4</span><span class="sxs-lookup"><span data-stu-id="45646-155">Surface Pro 4</span></span>
- <span data-ttu-id="45646-156">VersionsLTE du modèleSurface3</span><span class="sxs-lookup"><span data-stu-id="45646-156">Surface 3 LTE</span></span>
- <span data-ttu-id="45646-157">Surface3</span><span class="sxs-lookup"><span data-stu-id="45646-157">Surface 3</span></span>
- <span data-ttu-id="45646-158">Surface Pro3</span><span class="sxs-lookup"><span data-stu-id="45646-158">Surface Pro 3</span></span>

## <span data-ttu-id="45646-159">Installation de surface diagnostic Toolkit pour les entreprises</span><span class="sxs-lookup"><span data-stu-id="45646-159">Installing Surface Diagnostic Toolkit for Business</span></span>

<span data-ttu-id="45646-160">Pour créer un package SDT que vous pouvez distribuer aux utilisateurs de votre organisation:</span><span class="sxs-lookup"><span data-stu-id="45646-160">To create an SDT package that you can distribute to users in your organization:</span></span>

1. <span data-ttu-id="45646-161">Connectez-vous à votre périphérique surface en utilisant le compte administrateur.</span><span class="sxs-lookup"><span data-stu-id="45646-161">Sign in to your Surface device using the Administrator account.</span></span>
2. <span data-ttu-id="45646-162">Téléchargez le package Windows Installer (. msi) de l' [application outils surface pour le téléchargement](https://www.microsoft.com/download/details.aspx?id=46703) , puis copiez-le dans un emplacement préféré sur votre appareil surface, tel que le bureau.</span><span class="sxs-lookup"><span data-stu-id="45646-162">Download SDT Windows Installer Package (.msi) from the [Surface Tools for IT download page](https://www.microsoft.com/download/details.aspx?id=46703) and copy it to a preferred location on your Surface device, such as Desktop.</span></span>
3. <span data-ttu-id="45646-163">L’Assistant Installation de SDT s’affiche, comme illustré dans la figure 1.</span><span class="sxs-lookup"><span data-stu-id="45646-163">The SDT setup wizard appears, as shown in figure 1.</span></span> <span data-ttu-id="45646-164">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="45646-164">Click **Next**.</span></span> 

    >[!NOTE]
    ><span data-ttu-id="45646-165">S’il n’apparaît pas, vérifiez que vous êtes connecté au compte d’administrateur sur votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="45646-165">If the setup wizard does not appear, ensure that you are signed into the Administrator account on your computer.</span></span> 

    ![Bienvenue dans l’Assistant Installation de surface diagnostic Toolkit](images/sdt-1.png)

    *<span data-ttu-id="45646-167">Figure1.</span><span class="sxs-lookup"><span data-stu-id="45646-167">Figure 1.</span></span> <span data-ttu-id="45646-168">Assistant de configuration du kit de diagnostics surface</span><span class="sxs-lookup"><span data-stu-id="45646-168">Surface Diagnostic Toolkit setup wizard</span></span>*

4. <span data-ttu-id="45646-169">Lorsque l’Assistant Configuration de SDT s’affiche, cliquez sur **suivant**, acceptez le contrat de licence utilisateur final (CLUF).</span><span class="sxs-lookup"><span data-stu-id="45646-169">When the SDT setup wizard appears, click **Next**, accept the End User License Agreement (EULA)</span></span>

5. <span data-ttu-id="45646-170">Dans l’écran Options d’installation, modifiez l’emplacement d’installation par défaut si vous le souhaitez.</span><span class="sxs-lookup"><span data-stu-id="45646-170">On the Install Options screen, change the default install location if desired.</span></span> 
6. <span data-ttu-id="45646-171">Sous type d’installation, sélectionnez **avancé**.</span><span class="sxs-lookup"><span data-stu-id="45646-171">Under Setup Type, select **Advanced**.</span></span> 

    >[!NOTE]
    ><span data-ttu-id="45646-172">L’option standard permet aux utilisateurs d’exécuter l’outil de diagnostic directement sur leur appareil surface, à condition qu’ils soient connectés à leur appareil à l’aide d’un compte d’administrateur.</span><span class="sxs-lookup"><span data-stu-id="45646-172">The standard option allows users to run the diagnostic tool directly on their Surface device provided they are signed into their device using an Administrator account.</span></span> 
    
     ![Options d’installation: options avancées](images/sdt-install.png)

7. <span data-ttu-id="45646-174">Cliquez sur **suivant** , puis sur **installer**.</span><span class="sxs-lookup"><span data-stu-id="45646-174">Click **Next** and then click **Install**.</span></span> 

## <span data-ttu-id="45646-175">Installation à l’aide de la ligne de commande</span><span class="sxs-lookup"><span data-stu-id="45646-175">Installing using the command line</span></span>
<span data-ttu-id="45646-176">Si vous le souhaitez, vous pouvez installer le SDT à l’invite de commandes et définir un indicateur personnalisé pour installer l’outil en mode administrateur.</span><span class="sxs-lookup"><span data-stu-id="45646-176">If desired, you can install SDT at a command prompt and set a custom flag to install the tool in admin mode.</span></span> <span data-ttu-id="45646-177">Le SDT contient les indicateurs d’option d’installation suivants:</span><span class="sxs-lookup"><span data-stu-id="45646-177">SDT contains the following install option flags:</span></span>

- `SENDTELEMETRY` <span data-ttu-id="45646-178">envoie les données de télémétrie à Microsoft.</span><span class="sxs-lookup"><span data-stu-id="45646-178">sends telemetry data to Microsoft.</span></span> <span data-ttu-id="45646-179">L’indicateur accepte `0` pour désactivé ou `1` activé.</span><span class="sxs-lookup"><span data-stu-id="45646-179">The flag accepts `0` for disabled or `1` for enabled.</span></span> <span data-ttu-id="45646-180">La valeur par défaut consiste `1` à envoyer la télémétrie.</span><span class="sxs-lookup"><span data-stu-id="45646-180">The default value is `1` to send telemetry.</span></span>
- `ADMINMODE` <span data-ttu-id="45646-181">configure l’outil pour qu’il soit installé en mode administrateur.</span><span class="sxs-lookup"><span data-stu-id="45646-181">configures the tool to be installed in admin mode.</span></span> <span data-ttu-id="45646-182">L’indicateur accepte `0` pour le mode client ou `1` pour le mode administrateur informatique.</span><span class="sxs-lookup"><span data-stu-id="45646-182">The flag accepts `0` for client mode or `1` for IT Administrator mode.</span></span> <span data-ttu-id="45646-183">La valeur par défaut est `0`.</span><span class="sxs-lookup"><span data-stu-id="45646-183">The default value is `0`.</span></span>

### <span data-ttu-id="45646-184">Pour installer le SDT à partir de la ligne de commande:</span><span class="sxs-lookup"><span data-stu-id="45646-184">To install SDT from the command line:</span></span>

1. <span data-ttu-id="45646-185">Ouvrez une invite de commandes et entrez:</span><span class="sxs-lookup"><span data-stu-id="45646-185">Open a command prompt and enter:</span></span>

    ```
    msiexec.exe /i <the path of installer> ADMINMODE=1. 
    ```
    **<span data-ttu-id="45646-186">Exemple:</span><span class="sxs-lookup"><span data-stu-id="45646-186">Example:</span></span>**

    ```
    C:\Users\Administrator> msiexec.exe/I"C:\Users\Administrator\Desktop\Microsoft_Surface_Diagnostic_Toolkit_for_Business_Installer.msi" ADMINMODE=1
    ```

## <span data-ttu-id="45646-187">Localisation du SDT sur votre appareil surface</span><span class="sxs-lookup"><span data-stu-id="45646-187">Locating SDT on your Surface device</span></span>

<span data-ttu-id="45646-188">Le SDT et la console de l’application SDT sont tous deux installés sur `C:\Program Files\Microsoft\Surface\Microsoft Surface Diagnostic Toolkit for Business` .</span><span class="sxs-lookup"><span data-stu-id="45646-188">Both SDT and the SDT app console are installed at `C:\Program Files\Microsoft\Surface\Microsoft Surface Diagnostic Toolkit for Business`.</span></span>

<span data-ttu-id="45646-189">Outre le fichier. exe, SDT installe un fichier JSON et un fichier admin.dll (modules\admin.dll), comme illustré dans la figure 2.</span><span class="sxs-lookup"><span data-stu-id="45646-189">In addition to the .exe file, SDT installs a JSON file and an admin.dll file (modules\admin.dll), as shown in figure 2.</span></span>

![Liste des fichiers du SDT installés dans l’Explorateur de fichiers](images/sdt-2.png)

*<span data-ttu-id="45646-191">Figure2.</span><span class="sxs-lookup"><span data-stu-id="45646-191">Figure 2.</span></span> <span data-ttu-id="45646-192">Fichiers installés par SDT</span><span class="sxs-lookup"><span data-stu-id="45646-192">Files installed by SDT</span></span>*

<span id="create-custom-sdt" />

## <span data-ttu-id="45646-193">Préparation du package SDT à des fins de distribution</span><span class="sxs-lookup"><span data-stu-id="45646-193">Preparing the SDT package for distribution</span></span>

<span data-ttu-id="45646-194">La création d’un package personnalisé vous permet de cibler l’outil vers des problèmes connus spécifiques.</span><span class="sxs-lookup"><span data-stu-id="45646-194">Creating a custom package allows you to target the tool to specific known issues.</span></span>

1. <span data-ttu-id="45646-195">Cliquez sur **démarrer > exécuter**, entrez **surface** , puis cliquez sur **Kit de diagnostics de surface pour les entreprises**.</span><span class="sxs-lookup"><span data-stu-id="45646-195">Click **Start > Run**, enter **Surface** and then click **Surface Diagnostic Toolkit for Business**.</span></span> 
2. <span data-ttu-id="45646-196">Lorsque l’outil s’ouvre, cliquez sur **créer un package personnalisé**, comme illustré dans la figure 3.</span><span class="sxs-lookup"><span data-stu-id="45646-196">When the tool opens, click **Create Custom Package**, as shown in figure 3.</span></span>

    ![Option créer un package personnalisé](images/sdt-3.png)

    *<span data-ttu-id="45646-198">Figure3.</span><span class="sxs-lookup"><span data-stu-id="45646-198">Figure 3.</span></span> <span data-ttu-id="45646-199">Créer un package personnalisé</span><span class="sxs-lookup"><span data-stu-id="45646-199">Create custom package</span></span>*

### <span data-ttu-id="45646-200">Paramètres de langue et de télémétrie</span><span class="sxs-lookup"><span data-stu-id="45646-200">Language and telemetry settings</span></span>

  <span data-ttu-id="45646-201">Lors de la création d’un package, vous pouvez sélectionner des paramètres de langue ou annuler l’envoi d’informations de télémétrie à Microsoft.</span><span class="sxs-lookup"><span data-stu-id="45646-201">When creating a package, you can select language settings or opt out of sending telemetry information to Microsoft.</span></span> <span data-ttu-id="45646-202">Par défaut, le SDT envoie la télémétrie à Microsoft qui est utilisée pour améliorer l’application conformément à la [déclaration de confidentialité de Microsoft](https://privacy.microsoft.com/privacystatement).</span><span class="sxs-lookup"><span data-stu-id="45646-202">By default, SDT sends telemetry to Microsoft that is used to improve the application in accordance with the [Microsoft Privacy Statement](https://privacy.microsoft.com/privacystatement).</span></span> <span data-ttu-id="45646-203">Si vous souhaitez le décliner, désactivez la case à cocher lors de la création d’un package personnalisé, comme illustré ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="45646-203">If you wish to decline, clear the check box when creating a custom package, as shown below.</span></span> <span data-ttu-id="45646-204">Vous pouvez activer ou désactiver la case à cocher **Envoyer un télémétrie à Microsoft** sur la page **options d’installation** lors de la configuration de SDT.</span><span class="sxs-lookup"><span data-stu-id="45646-204">Or clear the **Send telemetry to Microsoft** check box on the **Install Options** page during SDT Setup.</span></span> 

>[!NOTE]
><span data-ttu-id="45646-205">Ce paramètre n’a pas d’incidence sur le niveau de télémétrie minimal stocké automatiquement sur les serveurs Microsoft lors de l’exécution de tests et de réparations qui nécessitent une connexion Internet (par exemple, Windows Update et la réparation du logiciel) ou la fourniture de commentaires à l’aide des boutons sourire ou Smiley de la barre d’outils de l’application.</span><span class="sxs-lookup"><span data-stu-id="45646-205">This setting does not affect the minimal telemetry automatically stored on Microsoft servers when running tests and repairs that require an Internet connection, such as Windows Update and Software repair, or providing feedback using the Smile or Frown buttons in the app toolbar.</span></span> 


![Sélectionner les paramètres de langue et de télémétrie](images/sdt-4.png)

*<span data-ttu-id="45646-207">Figure4.</span><span class="sxs-lookup"><span data-stu-id="45646-207">Figure 4.</span></span> <span data-ttu-id="45646-208">Sélectionner les paramètres de langue et de télémétrie</span><span class="sxs-lookup"><span data-stu-id="45646-208">Select language and telemetry settings</span></span>*


### <span data-ttu-id="45646-209">Page Windows Update</span><span class="sxs-lookup"><span data-stu-id="45646-209">Windows Update page</span></span>

<span data-ttu-id="45646-210">Sélectionnez l’option adaptée à votre organisation.</span><span class="sxs-lookup"><span data-stu-id="45646-210">Select the option appropriate for your organization.</span></span> <span data-ttu-id="45646-211">La plupart des organisations qui utilisent plusieurs utilisateurs peuvent généralement sélectionner pour recevoir des mises à jour via Windows Server Update Services (WSUS), comme illustré dans la figure 5.</span><span class="sxs-lookup"><span data-stu-id="45646-211">Most organizations with multiple users will typically select to receive updates via Windows Server Update Services (WSUS), as shown in figure 5.</span></span> <span data-ttu-id="45646-212">Si vous utilisez des packages de mise à jour Windows locaux ou WSUS, entrez le chemin d’accès selon le cas.</span><span class="sxs-lookup"><span data-stu-id="45646-212">If using local Windows Update packages or WSUS, enter the path as appropriate.</span></span> 

![Sélectionner l’option Windows Update](images/sdt-5.png)

*<span data-ttu-id="45646-214">Figure5.</span><span class="sxs-lookup"><span data-stu-id="45646-214">Figure 5.</span></span> <span data-ttu-id="45646-215">Option Windows Update</span><span class="sxs-lookup"><span data-stu-id="45646-215">Windows Update option</span></span>*

### <span data-ttu-id="45646-216">Page de réparation du logiciel</span><span class="sxs-lookup"><span data-stu-id="45646-216">Software repair page</span></span>

<span data-ttu-id="45646-217">Cela vous permet de sélectionner ou de supprimer l’option d’exécution des mises à jour de réparation de logiciels.</span><span class="sxs-lookup"><span data-stu-id="45646-217">This allows you to select or remove the option to run software repair updates.</span></span> 

![Sélectionner l’option de réparation logicielle](images/sdt-6.png)

*<span data-ttu-id="45646-219">Figure6.</span><span class="sxs-lookup"><span data-stu-id="45646-219">Figure 6.</span></span> <span data-ttu-id="45646-220">Option de réparation de logiciels</span><span class="sxs-lookup"><span data-stu-id="45646-220">Software repair option</span></span>*

### <span data-ttu-id="45646-221">Page de collecte des journaux et enregistrement de package</span><span class="sxs-lookup"><span data-stu-id="45646-221">Collecting logs and saving package page</span></span>

<span data-ttu-id="45646-222">Vous pouvez choisir d’exécuter une large gamme de journaux entre les applications, les pilotes, le matériel et le système d’exploitation.</span><span class="sxs-lookup"><span data-stu-id="45646-222">You can select to run a wide range of logs across applications, drivers, hardware, and the operating system.</span></span> <span data-ttu-id="45646-223">Cliquez sur la zone appropriée et sélectionnez-en un dans le menu de journaux disponibles.</span><span class="sxs-lookup"><span data-stu-id="45646-223">Click the appropriate area and select from the menu of available logs.</span></span> <span data-ttu-id="45646-224">Vous pouvez ensuite enregistrer le package dans un point de distribution de logiciels ou un emplacement équivalent auquel les utilisateurs peuvent accéder.</span><span class="sxs-lookup"><span data-stu-id="45646-224">You can then save the package to a software distribution point or equivalent location that users can access.</span></span> 

![Sélectionner les options de journalisation](images/sdt-7.png)

*<span data-ttu-id="45646-226">Figure7.</span><span class="sxs-lookup"><span data-stu-id="45646-226">Figure 7.</span></span> <span data-ttu-id="45646-227">Option journal et enregistrer le package</span><span class="sxs-lookup"><span data-stu-id="45646-227">Log option and save package</span></span>*

## <span data-ttu-id="45646-228">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="45646-228">Next steps</span></span>

- [<span data-ttu-id="45646-229">Utiliser le Kit de ressources de diagnostic pour Surface Entreprise en mode bureau</span><span class="sxs-lookup"><span data-stu-id="45646-229">Use Surface Diagnostic Toolkit for Business in desktop mode</span></span>](surface-diagnostic-toolkit-desktop-mode.md)
- [<span data-ttu-id="45646-230">Utiliser les commandes de la trousse à outils de diagnostic de surface pour les entreprises</span><span class="sxs-lookup"><span data-stu-id="45646-230">Use Surface Diagnostic Toolkit for Business using commands</span></span>](surface-diagnostic-toolkit-command-line.md)

## <span data-ttu-id="45646-231">Modifications et mises à jour</span><span class="sxs-lookup"><span data-stu-id="45646-231">Changes and updates</span></span>

### <span data-ttu-id="45646-232">Version 2.124.139.0</span><span class="sxs-lookup"><span data-stu-id="45646-232">Version 2.124.139.0</span></span>

<span data-ttu-id="45646-233">Cette version du kit de diagnostics de surface pour les entreprises ajoute une prise en charge pour les éléments suivants:</span><span class="sxs-lookup"><span data-stu-id="45646-233">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span>

- <span data-ttu-id="45646-234">Support intégré transparente</span><span class="sxs-lookup"><span data-stu-id="45646-234">Seamless integrated support</span></span>
- <span data-ttu-id="45646-235">Enregistrer tous les résultats des tests</span><span class="sxs-lookup"><span data-stu-id="45646-235">Save all test results</span></span>
- <span data-ttu-id="45646-236">Vérifier que l’image est créée personnalisé</span><span class="sxs-lookup"><span data-stu-id="45646-236">Check if the image is custom created</span></span>
- <span data-ttu-id="45646-237">Inclure les avertissements du gestionnaire de périphériques</span><span class="sxs-lookup"><span data-stu-id="45646-237">Include warnings from device manager</span></span>
- <span data-ttu-id="45646-238">Version du microprogramme du Dock</span><span class="sxs-lookup"><span data-stu-id="45646-238">Dock firmware version</span></span>
- <span data-ttu-id="45646-239">Marquer des lecteurs comme des échecs potentiels dans le test de stockage</span><span class="sxs-lookup"><span data-stu-id="45646-239">Flag drives as potential failures in storage test</span></span>
- <span data-ttu-id="45646-240">Supprimer le lien vers le magasin</span><span class="sxs-lookup"><span data-stu-id="45646-240">Remove store link</span></span> 

### <span data-ttu-id="45646-241">Version 2.121.139</span><span class="sxs-lookup"><span data-stu-id="45646-241">Version 2.121.139</span></span>
*<span data-ttu-id="45646-242">Date de publication: 31 2020 juillet</span><span class="sxs-lookup"><span data-stu-id="45646-242">Release date: July 31 2020</span></span>*<br>
<span data-ttu-id="45646-243">Cette version du kit de diagnostics de surface pour les entreprises ajoute une prise en charge pour les éléments suivants:</span><span class="sxs-lookup"><span data-stu-id="45646-243">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span>

- <span data-ttu-id="45646-244">Une prise en charge transparente</span><span class="sxs-lookup"><span data-stu-id="45646-244">Seamless support experience</span></span>
- <span data-ttu-id="45646-245">Correction de bogues</span><span class="sxs-lookup"><span data-stu-id="45646-245">Bug fixes</span></span>

### <span data-ttu-id="45646-246">Version 2.94.139.0</span><span class="sxs-lookup"><span data-stu-id="45646-246">Version 2.94.139.0</span></span>
*<span data-ttu-id="45646-247">Date de publication: 11 2020</span><span class="sxs-lookup"><span data-stu-id="45646-247">Release date: May 11, 2020</span></span>*<br>
<span data-ttu-id="45646-248">Cette version du kit de diagnostics de surface pour les entreprises ajoute une prise en charge pour les éléments suivants:</span><span class="sxs-lookup"><span data-stu-id="45646-248">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span>

- <span data-ttu-id="45646-249">Possibilité d’ignorer Windows Update pour procéder à la vérification matérielle.</span><span class="sxs-lookup"><span data-stu-id="45646-249">Ability to skip Windows Update to perform hardware check.</span></span>
- <span data-ttu-id="45646-250">Possibilité de recevoir des notifications concernant la dernière mise à jour de la version</span><span class="sxs-lookup"><span data-stu-id="45646-250">Ability to receive notifications for about the latest version update</span></span>
- <span data-ttu-id="45646-251">SurfaceGo2</span><span class="sxs-lookup"><span data-stu-id="45646-251">Surface Go 2</span></span>
- <span data-ttu-id="45646-252">SurfaceBook3</span><span class="sxs-lookup"><span data-stu-id="45646-252">Surface Book 3</span></span>
- <span data-ttu-id="45646-253">Afficher l’indicateur de progression</span><span class="sxs-lookup"><span data-stu-id="45646-253">Show progress indicator</span></span>


### <span data-ttu-id="45646-254">Version 2.43.139.0</span><span class="sxs-lookup"><span data-stu-id="45646-254">Version 2.43.139.0</span></span>
*<span data-ttu-id="45646-255">Date de publication: 21 octobre 2019</span><span class="sxs-lookup"><span data-stu-id="45646-255">Release date: October 21, 2019</span></span>*<br>
<span data-ttu-id="45646-256">Cette version du kit de diagnostics de surface pour les entreprises ajoute une prise en charge pour les éléments suivants:</span><span class="sxs-lookup"><span data-stu-id="45646-256">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span>

- <span data-ttu-id="45646-257">SurfacePro7</span><span class="sxs-lookup"><span data-stu-id="45646-257">Surface Pro 7</span></span>
- <span data-ttu-id="45646-258">Surface Laptop3</span><span class="sxs-lookup"><span data-stu-id="45646-258">Surface Laptop 3</span></span>

### <span data-ttu-id="45646-259">Version 2.42.139.0</span><span class="sxs-lookup"><span data-stu-id="45646-259">Version 2.42.139.0</span></span>
*<span data-ttu-id="45646-260">Date de publication: 24 septembre 2019</span><span class="sxs-lookup"><span data-stu-id="45646-260">Release date: September 24, 2019</span></span>*<br>
<span data-ttu-id="45646-261">Cette version du kit de diagnostics de surface pour les entreprises ajoute une prise en charge pour les éléments suivants:</span><span class="sxs-lookup"><span data-stu-id="45646-261">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span> 
- <span data-ttu-id="45646-262">Possibilité de télécharger des rapports de matériel.</span><span class="sxs-lookup"><span data-stu-id="45646-262">Ability to download hardware reports.</span></span>
- <span data-ttu-id="45646-263">Possibilité de contacter le support Microsoft directement à partir de l’outil.</span><span class="sxs-lookup"><span data-stu-id="45646-263">Ability to contact Microsoft Support directly from the tool.</span></span> <br>

### <span data-ttu-id="45646-264">Version 2.41.139.0</span><span class="sxs-lookup"><span data-stu-id="45646-264">Version 2.41.139.0</span></span>
*<span data-ttu-id="45646-265">Date de publication: 24 juin 2019</span><span class="sxs-lookup"><span data-stu-id="45646-265">Release date: June 24, 2019</span></span>*<br>
<span data-ttu-id="45646-266">Cette version du kit de diagnostics de surface pour les entreprises ajoute une prise en charge pour les éléments suivants:</span><span class="sxs-lookup"><span data-stu-id="45646-266">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span> 
- <span data-ttu-id="45646-267">Informations de version du pilote intégrées aux journaux et au rapport.</span><span class="sxs-lookup"><span data-stu-id="45646-267">Driver version information included in logs and report.</span></span>
- <span data-ttu-id="45646-268">Possibilité de fournir des commentaires sur l’application.</span><span class="sxs-lookup"><span data-stu-id="45646-268">Ability to provide feedback about the app.</span></span><br>


### <span data-ttu-id="45646-269">Version 2.36.139.0</span><span class="sxs-lookup"><span data-stu-id="45646-269">Version 2.36.139.0</span></span>
*<span data-ttu-id="45646-270">Date de publication: 26 avril 2019</span><span class="sxs-lookup"><span data-stu-id="45646-270">Release date: April 26, 2019</span></span>*<br>
<span data-ttu-id="45646-271">Cette version du kit de diagnostics de surface pour les entreprises ajoute une prise en charge pour les éléments suivants:</span><span class="sxs-lookup"><span data-stu-id="45646-271">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span> 
- <span data-ttu-id="45646-272">Option de configuration avancée permettant de déverrouiller les fonctionnalités d’administration par le biais de l’interface utilisateur du programme d’installation, sans nécessiter de configuration de ligne</span><span class="sxs-lookup"><span data-stu-id="45646-272">Advanced Setup option to unlock admin capabilities through the installer UI, without requiring command line configuration.</span></span>
- <span data-ttu-id="45646-273">Améliorations apportées à l’accessibilité.</span><span class="sxs-lookup"><span data-stu-id="45646-273">Accessibility improvements.</span></span>
- <span data-ttu-id="45646-274">Paramètres de contrôle de surface de surface intégrés aux journaux.</span><span class="sxs-lookup"><span data-stu-id="45646-274">Surface brightness control settings included in logs.</span></span>
- <span data-ttu-id="45646-275">Lien support de compatibilité du moniteur externe dans le générateur de rapports.</span><span class="sxs-lookup"><span data-stu-id="45646-275">External monitor compatibility support link in report generator.</span></span>
