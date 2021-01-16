---
title: Déploiement du Kit de ressources de diagnostic pour Surface Entreprise
description: Cette rubrique explique comment utiliser surface Diagnostic Shared Computer Toolkit for Business.
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 01/15/2021
ms.reviewer: hachidan
manager: laurawi
audience: itpro
ms.openlocfilehash: 227463e484a6f3b933fc1118d9dec058f93074a8
ms.sourcegitcommit: 1053479c191fd10651d31a466fad1769fb0cd28b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/16/2021
ms.locfileid: "11271578"
---
# <span data-ttu-id="61e59-103">Déploiement du Kit de ressources de diagnostic pour Surface Entreprise</span><span class="sxs-lookup"><span data-stu-id="61e59-103">Deploy Surface Diagnostic Toolkit for Business</span></span>

<span data-ttu-id="61e59-104">Le Microsoft Surface Diagnostic Shared Computer Toolkit for Business (SDT) permet aux administrateurs informatiques d’examiner, dépanner et résoudre rapidement les problèmes matériels, logiciels et microprogrammes avec les appareils Surface.</span><span class="sxs-lookup"><span data-stu-id="61e59-104">The Microsoft Surface Diagnostic Toolkit for Business (SDT) enables IT administrators to quickly investigate, troubleshoot, and resolve hardware, software, and firmware issues with Surface devices.</span></span> <span data-ttu-id="61e59-105">Vous pouvez exécuter une série de tests de diagnostic et de réparations logicielles en plus d’obtenir des informations sur l’état de l’appareil et des conseils pour résoudre les problèmes.</span><span class="sxs-lookup"><span data-stu-id="61e59-105">You can run a range of diagnostic tests and software repairs in addition to obtaining device health insights and guidance for resolving issues.</span></span> 

<span data-ttu-id="61e59-106">Plus précisément, SDT entreprise vous permet de :</span><span class="sxs-lookup"><span data-stu-id="61e59-106">Specifically, SDT for Business enables you to:</span></span>

- [<span data-ttu-id="61e59-107">Personnalisez le package.</span><span class="sxs-lookup"><span data-stu-id="61e59-107">Customize the package.</span></span>](#preparing-the-sdt-package-for-distribution)
- [<span data-ttu-id="61e59-108">Exécutez l’application à l’aide de commandes.</span><span class="sxs-lookup"><span data-stu-id="61e59-108">Run the app using commands.</span></span>](surface-diagnostic-toolkit-command-line.md)
- [<span data-ttu-id="61e59-109">Exécutez plusieurs tests matériels pour résoudre les problèmes.</span><span class="sxs-lookup"><span data-stu-id="61e59-109">Run multiple hardware tests to troubleshoot issues.</span></span>](surface-diagnostic-toolkit-desktop-mode.md#multiple)
- [<span data-ttu-id="61e59-110">Générer des journaux pour l’analyse des problèmes.</span><span class="sxs-lookup"><span data-stu-id="61e59-110">Generate logs for analyzing issues.</span></span>](surface-diagnostic-toolkit-desktop-mode.md#logs)
- [<span data-ttu-id="61e59-111">Obtenir un rapport détaillé comparant l’appareil et la configuration optimale.</span><span class="sxs-lookup"><span data-stu-id="61e59-111">Obtain detailed report comparing device vs optimal configuration.</span></span>](surface-diagnostic-toolkit-desktop-mode.md#detailed-report)


## <span data-ttu-id="61e59-112">Scénarios principaux et ressources de téléchargement</span><span class="sxs-lookup"><span data-stu-id="61e59-112">Primary scenarios and download resources</span></span> 

<span data-ttu-id="61e59-113">Pour exécuter SDT entreprise, téléchargez les composants répertoriés dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="61e59-113">To run SDT for Business, download the components listed in the following table.</span></span>


<span data-ttu-id="61e59-114">Mode</span><span class="sxs-lookup"><span data-stu-id="61e59-114">Mode</span></span> |  <span data-ttu-id="61e59-115">Scénarios principaux</span><span class="sxs-lookup"><span data-stu-id="61e59-115">Primary scenarios</span></span> | <span data-ttu-id="61e59-116">Télécharger</span><span class="sxs-lookup"><span data-stu-id="61e59-116">Download</span></span> | <span data-ttu-id="61e59-117">Si vous souhaitez en savoir plus</span><span class="sxs-lookup"><span data-stu-id="61e59-117">Learn more</span></span>
--- | --- | --- | ---
<span data-ttu-id="61e59-118">Mode bureau</span><span class="sxs-lookup"><span data-stu-id="61e59-118">Desktop mode</span></span> |  <span data-ttu-id="61e59-119">Aider les utilisateurs à l’exécution de SDT sur leurs appareils Surface pour résoudre les problèmes.</span><span class="sxs-lookup"><span data-stu-id="61e59-119">Assist users in running SDT on their Surface devices to troubleshoot issues.</span></span><br><span data-ttu-id="61e59-120">Créez un package personnalisé à déployer sur un ou plusieurs appareils Surface, ce qui permet aux utilisateurs de sélectionner des journaux spécifiques à collecter et à analyser.</span><span class="sxs-lookup"><span data-stu-id="61e59-120">Create a custom package to deploy on one or more Surface devices allowing users to select specific logs to collect and analyze.</span></span> | <span data-ttu-id="61e59-121">Package MSI distribuable SDT :</span><span class="sxs-lookup"><span data-stu-id="61e59-121">SDT distributable MSI package:</span></span><br><span data-ttu-id="61e59-122">Microsoft Surface Diagnostic Toolkit for Business Installer</span><span class="sxs-lookup"><span data-stu-id="61e59-122">Microsoft Surface Diagnostic Toolkit for Business Installer</span></span><br>[<span data-ttu-id="61e59-123">Outils Surface pour l'informatique</span><span class="sxs-lookup"><span data-stu-id="61e59-123">Surface Tools for IT</span></span>](https://www.microsoft.com/download/details.aspx?id=46703) | [<span data-ttu-id="61e59-124">Utiliser surface Diagnostic Shared Computer Toolkit en mode bureau</span><span class="sxs-lookup"><span data-stu-id="61e59-124">Use Surface Diagnostic Toolkit in desktop mode</span></span>](surface-diagnostic-toolkit-desktop-mode.md)
<span data-ttu-id="61e59-125">Ligne de commande</span><span class="sxs-lookup"><span data-stu-id="61e59-125">Command line</span></span> |  <span data-ttu-id="61e59-126">Dépanner directement les appareils Surface à distance sans intervention de l’utilisateur, à l’aide d’outils standard tels que Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="61e59-126">Directly troubleshoot Surface devices remotely without user interaction, using standard tools such as Configuration Manager.</span></span> <span data-ttu-id="61e59-127">Il inclut les commandes suivantes :</span><span class="sxs-lookup"><span data-stu-id="61e59-127">It includes the following commands:</span></span><br>`-DataCollector` <span data-ttu-id="61e59-128">collecte tous les fichiers journaux</span><span class="sxs-lookup"><span data-stu-id="61e59-128">collects all log files</span></span><br>`-bpa` <span data-ttu-id="61e59-129">exécute des diagnostics d’état à l’aide de Best Practice Analyzer.</span><span class="sxs-lookup"><span data-stu-id="61e59-129">runs health diagnostics using Best Practice Analyzer.</span></span><br>`-windowsupdate` <span data-ttu-id="61e59-130">recherche des mises à jour du microprogramme ou des pilotes manquantes dans Windows Update.</span><span class="sxs-lookup"><span data-stu-id="61e59-130">checks Windows Update for missing firmware or driver updates.</span></span><br>`-warranty` <span data-ttu-id="61e59-131">vérifie les informations de garantie.</span><span class="sxs-lookup"><span data-stu-id="61e59-131">checks warranty information.</span></span> <br><br>| <span data-ttu-id="61e59-132">Application console SDT :</span><span class="sxs-lookup"><span data-stu-id="61e59-132">SDT console app:</span></span><br><span data-ttu-id="61e59-133">Microsoft Surface Diagnostics App Console</span><span class="sxs-lookup"><span data-stu-id="61e59-133">Microsoft Surface Diagnostics App Console</span></span><br>[<span data-ttu-id="61e59-134">Outils Surface pour l'informatique</span><span class="sxs-lookup"><span data-stu-id="61e59-134">Surface Tools for IT</span></span>](https://www.microsoft.com/download/details.aspx?id=46703) | [<span data-ttu-id="61e59-135">Exécuter surface Diagnostic Shared Computer Toolkit à l’aide de commandes</span><span class="sxs-lookup"><span data-stu-id="61e59-135">Run Surface Diagnostic Toolkit using commands</span></span>](surface-diagnostic-toolkit-command-line.md)

## <span data-ttu-id="61e59-136">Appareils pris en charge</span><span class="sxs-lookup"><span data-stu-id="61e59-136">Supported devices</span></span> 

<span data-ttu-id="61e59-137">SDT entreprise est pris en charge sur les appareils Surface 3 et ultérieurs, notamment :</span><span class="sxs-lookup"><span data-stu-id="61e59-137">SDT for Business is supported on Surface 3 and later devices, including:</span></span>

- <span data-ttu-id="61e59-138">Surface Book - toutes les générations</span><span class="sxs-lookup"><span data-stu-id="61e59-138">Surface Book - all generations</span></span>
- <span data-ttu-id="61e59-139">Surface Go - toutes les générations</span><span class="sxs-lookup"><span data-stu-id="61e59-139">Surface Go - all generations</span></span>
- <span data-ttu-id="61e59-140">Surface Laptop - toutes les générations</span><span class="sxs-lookup"><span data-stu-id="61e59-140">Surface Laptop - all generations</span></span>
- <span data-ttu-id="61e59-141">Surface Pro 3 et les ultérieures</span><span class="sxs-lookup"><span data-stu-id="61e59-141">Surface Pro 3 and later</span></span>
- <span data-ttu-id="61e59-142">Surface Pro X - toutes les générations</span><span class="sxs-lookup"><span data-stu-id="61e59-142">Surface Pro X - all generations</span></span>
- <span data-ttu-id="61e59-143">Surface Studio - toutes les générations</span><span class="sxs-lookup"><span data-stu-id="61e59-143">Surface Studio - all generations</span></span>
- <span data-ttu-id="61e59-144">VersionsLTE du modèleSurface3</span><span class="sxs-lookup"><span data-stu-id="61e59-144">Surface 3 LTE</span></span>
- <span data-ttu-id="61e59-145">Surface3</span><span class="sxs-lookup"><span data-stu-id="61e59-145">Surface 3</span></span>


## <span data-ttu-id="61e59-146">Installation de Surface Diagnostic Shared Computer Toolkit for Business</span><span class="sxs-lookup"><span data-stu-id="61e59-146">Installing Surface Diagnostic Toolkit for Business</span></span>

<span data-ttu-id="61e59-147">Pour créer un package SDT que vous pouvez distribuer aux utilisateurs de votre organisation :</span><span class="sxs-lookup"><span data-stu-id="61e59-147">To create an SDT package that you can distribute to users in your organization:</span></span>

1. <span data-ttu-id="61e59-148">Connectez-vous à votre appareil Surface à l’aide du compte Administrateur.</span><span class="sxs-lookup"><span data-stu-id="61e59-148">Sign in to your Surface device using the Administrator account.</span></span>
2. <span data-ttu-id="61e59-149">Téléchargez le package Windows Installer SDT (.msi) à partir de la page de téléchargement des outils [Surface pour](https://www.microsoft.com/download/details.aspx?id=46703) l’informatique et copiez-le à un emplacement préféré sur votre appareil Surface, tel que Bureau.</span><span class="sxs-lookup"><span data-stu-id="61e59-149">Download SDT Windows Installer Package (.msi) from the [Surface Tools for IT download page](https://www.microsoft.com/download/details.aspx?id=46703) and copy it to a preferred location on your Surface device, such as Desktop.</span></span>
3. <span data-ttu-id="61e59-150">L’Assistant Installation de SDT apparaît, comme illustré dans la figure 1.</span><span class="sxs-lookup"><span data-stu-id="61e59-150">The SDT setup wizard appears, as shown in figure 1.</span></span> <span data-ttu-id="61e59-151">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="61e59-151">Click **Next**.</span></span> 

    >[!NOTE]
    ><span data-ttu-id="61e59-152">Si l’Assistant Installation n’apparaît pas, assurez-vous que vous êtes bien inscrit au compte Administrateur sur votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="61e59-152">If the setup wizard does not appear, ensure that you are signed into the Administrator account on your computer.</span></span> 

    ![Bienvenue dans l’Assistant Installation de Surface Diagnostic Shared Computer Toolkit](images/sdt-1.png)

    *<span data-ttu-id="61e59-154">Figure1.</span><span class="sxs-lookup"><span data-stu-id="61e59-154">Figure 1.</span></span> <span data-ttu-id="61e59-155">Assistant Installation de Shared Computer Toolkit diagnostic Surface</span><span class="sxs-lookup"><span data-stu-id="61e59-155">Surface Diagnostic Toolkit setup wizard</span></span>*

4. <span data-ttu-id="61e59-156">Lorsque l’Assistant Configuration de SDT s’affiche, cliquez sur **Suivant**, acceptez le contrat de licence utilisateur final (CLLA)</span><span class="sxs-lookup"><span data-stu-id="61e59-156">When the SDT setup wizard appears, click **Next**, accept the End User License Agreement (EULA)</span></span>

5. <span data-ttu-id="61e59-157">Dans l’écran Options d’installation, modifiez l’emplacement d’installation par défaut si vous le souhaitez.</span><span class="sxs-lookup"><span data-stu-id="61e59-157">On the Install Options screen, change the default install location if desired.</span></span> 
6. <span data-ttu-id="61e59-158">Sous Type d’installation, sélectionnez **Avancé.**</span><span class="sxs-lookup"><span data-stu-id="61e59-158">Under Setup Type, select **Advanced**.</span></span> 

    >[!NOTE]
    ><span data-ttu-id="61e59-159">L’option standard permet aux utilisateurs d’exécuter l’outil de diagnostic directement sur leur appareil Surface à condition qu’ils soient connectés à leur appareil à l’aide d’un compte Administrateur.</span><span class="sxs-lookup"><span data-stu-id="61e59-159">The standard option allows users to run the diagnostic tool directly on their Surface device provided they are signed into their device using an Administrator account.</span></span> 
    
     ![Options d’installation : avancé](images/sdt-install.png)

7. <span data-ttu-id="61e59-161">Cliquez **sur Suivant,** puis sur **Installer.**</span><span class="sxs-lookup"><span data-stu-id="61e59-161">Click **Next** and then click **Install**.</span></span> 

## <span data-ttu-id="61e59-162">Installation à l’aide de la ligne de commande</span><span class="sxs-lookup"><span data-stu-id="61e59-162">Installing using the command line</span></span>
<span data-ttu-id="61e59-163">Si vous le souhaitez, vous pouvez installer SDT à une invite de commandes et définir un indicateur personnalisé pour installer l’outil en mode administrateur.</span><span class="sxs-lookup"><span data-stu-id="61e59-163">If desired, you can install SDT at a command prompt and set a custom flag to install the tool in admin mode.</span></span> <span data-ttu-id="61e59-164">SDT contient les indicateurs d’option d’installation suivants :</span><span class="sxs-lookup"><span data-stu-id="61e59-164">SDT contains the following install option flags:</span></span>

- `SENDTELEMETRY` <span data-ttu-id="61e59-165">envoie des données de télémétrie à Microsoft.</span><span class="sxs-lookup"><span data-stu-id="61e59-165">sends telemetry data to Microsoft.</span></span> <span data-ttu-id="61e59-166">L’indicateur accepte `0` désactivé ou `1` activé.</span><span class="sxs-lookup"><span data-stu-id="61e59-166">The flag accepts `0` for disabled or `1` for enabled.</span></span> <span data-ttu-id="61e59-167">La valeur par défaut est `1` d’envoyer la télémétrie.</span><span class="sxs-lookup"><span data-stu-id="61e59-167">The default value is `1` to send telemetry.</span></span>
- `ADMINMODE` <span data-ttu-id="61e59-168">configure l’outil à installer en mode administrateur.</span><span class="sxs-lookup"><span data-stu-id="61e59-168">configures the tool to be installed in admin mode.</span></span> <span data-ttu-id="61e59-169">L’indicateur accepte `0` le mode client ou le mode Administrateur `1` informatique.</span><span class="sxs-lookup"><span data-stu-id="61e59-169">The flag accepts `0` for client mode or `1` for IT Administrator mode.</span></span> <span data-ttu-id="61e59-170">La valeur par défaut est `0`.</span><span class="sxs-lookup"><span data-stu-id="61e59-170">The default value is `0`.</span></span>

### <span data-ttu-id="61e59-171">Pour installer SDT à partir de la ligne de commande :</span><span class="sxs-lookup"><span data-stu-id="61e59-171">To install SDT from the command line:</span></span>

1. <span data-ttu-id="61e59-172">Ouvrez une invite de commandes et entrez :</span><span class="sxs-lookup"><span data-stu-id="61e59-172">Open a command prompt and enter:</span></span>

    ```
    msiexec.exe /i <the path of installer> ADMINMODE=1. 
    ```
    **<span data-ttu-id="61e59-173">Exemple:</span><span class="sxs-lookup"><span data-stu-id="61e59-173">Example:</span></span>**

    ```
    C:\Users\Administrator> msiexec.exe/I"C:\Users\Administrator\Desktop\Microsoft_Surface_Diagnostic_Toolkit_for_Business_Installer.msi" ADMINMODE=1
    ```

## <span data-ttu-id="61e59-174">Localisation de SDT sur votre appareil Surface</span><span class="sxs-lookup"><span data-stu-id="61e59-174">Locating SDT on your Surface device</span></span>

<span data-ttu-id="61e59-175">SDT et la console d’application SDT sont installés sur `C:\Program Files\Microsoft\Surface\Microsoft Surface Diagnostic Toolkit for Business` .</span><span class="sxs-lookup"><span data-stu-id="61e59-175">Both SDT and the SDT app console are installed at `C:\Program Files\Microsoft\Surface\Microsoft Surface Diagnostic Toolkit for Business`.</span></span>

<span data-ttu-id="61e59-176">Outre le fichier .exe, SDT installe un fichier JSON et un fichier admin.dll (modules\admin.dll), comme le montre la figure 2.</span><span class="sxs-lookup"><span data-stu-id="61e59-176">In addition to the .exe file, SDT installs a JSON file and an admin.dll file (modules\admin.dll), as shown in figure 2.</span></span>

![liste des fichiers SDT installés dans l’Explorateur de fichiers](images/sdt-2.png)

*<span data-ttu-id="61e59-178">Figure2.</span><span class="sxs-lookup"><span data-stu-id="61e59-178">Figure 2.</span></span> <span data-ttu-id="61e59-179">Fichiers installés par SDT</span><span class="sxs-lookup"><span data-stu-id="61e59-179">Files installed by SDT</span></span>*

## <span data-ttu-id="61e59-180">Préparation du package SDT pour la distribution</span><span class="sxs-lookup"><span data-stu-id="61e59-180">Preparing the SDT package for distribution</span></span>

<span data-ttu-id="61e59-181">La création d’un package personnalisé vous permet de cibler l’outil sur des problèmes connus spécifiques.</span><span class="sxs-lookup"><span data-stu-id="61e59-181">Creating a custom package allows you to target the tool to specific known issues.</span></span>

1. <span data-ttu-id="61e59-182">Cliquez **sur Démarrer >,** entrez **Surface,** puis cliquez sur **Surface Diagnostic Shared Computer Toolkit Entreprise.**</span><span class="sxs-lookup"><span data-stu-id="61e59-182">Click **Start > Run**, enter **Surface** and then click **Surface Diagnostic Toolkit for Business**.</span></span> 
2. <span data-ttu-id="61e59-183">Lorsque l’outil s’ouvre, cliquez sur **Créer un package personnalisé,** comme illustré dans la figure 3.</span><span class="sxs-lookup"><span data-stu-id="61e59-183">When the tool opens, click **Create Custom Package**, as shown in figure 3.</span></span>

    ![Option Créer un package personnalisé](images/sdt-3.png)

    *<span data-ttu-id="61e59-185">Figure3.</span><span class="sxs-lookup"><span data-stu-id="61e59-185">Figure 3.</span></span> <span data-ttu-id="61e59-186">Créer un package personnalisé</span><span class="sxs-lookup"><span data-stu-id="61e59-186">Create custom package</span></span>*

### <span data-ttu-id="61e59-187">Paramètres de langue et de télémétrie</span><span class="sxs-lookup"><span data-stu-id="61e59-187">Language and telemetry settings</span></span>

  <span data-ttu-id="61e59-188">Lors de la création d’un package, vous pouvez sélectionner des paramètres de langue ou refuser l’envoi d’informations de télémétrie à Microsoft.</span><span class="sxs-lookup"><span data-stu-id="61e59-188">When creating a package, you can select language settings or opt out of sending telemetry information to Microsoft.</span></span> <span data-ttu-id="61e59-189">Par défaut, SDT envoie à Microsoft une télémétrie qui est utilisée pour améliorer l’application conformément à la déclaration de confidentialité [de Microsoft.](https://privacy.microsoft.com/privacystatement)</span><span class="sxs-lookup"><span data-stu-id="61e59-189">By default, SDT sends telemetry to Microsoft that is used to improve the application in accordance with the [Microsoft Privacy Statement](https://privacy.microsoft.com/privacystatement).</span></span> <span data-ttu-id="61e59-190">Si vous souhaitez refuser, cochez la case lors de la création d’un package personnalisé, comme illustré ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="61e59-190">If you wish to decline, clear the check box when creating a custom package, as shown below.</span></span> <span data-ttu-id="61e59-191">Vous pouvez également effacer **la case à cocher Envoyer** la télémétrie à Microsoft dans la page **Options** d’installation pendant l’installation de SDT.</span><span class="sxs-lookup"><span data-stu-id="61e59-191">Or clear the **Send telemetry to Microsoft** check box on the **Install Options** page during SDT Setup.</span></span> 

>[!NOTE]
><span data-ttu-id="61e59-192">Ce paramètre n’affecte pas la télémétrie minimale automatiquement stockée sur les serveurs Microsoft lors de l’exécution de tests et de réparations qui nécessitent une connexion Internet, telle que Windows Update et la réparation logicielle, ou lorsque vous fournissez des commentaires à l’aide des boutons Souris ou Désapprouver dans la barre d’outils de l’application.</span><span class="sxs-lookup"><span data-stu-id="61e59-192">This setting does not affect the minimal telemetry automatically stored on Microsoft servers when running tests and repairs that require an Internet connection, such as Windows Update and Software repair, or providing feedback using the Smile or Frown buttons in the app toolbar.</span></span> 


![Sélectionner les paramètres de langue et de télémétrie](images/sdt-4.png)

*<span data-ttu-id="61e59-194">Figure4.</span><span class="sxs-lookup"><span data-stu-id="61e59-194">Figure 4.</span></span> <span data-ttu-id="61e59-195">Sélectionner les paramètres de langue et de télémétrie</span><span class="sxs-lookup"><span data-stu-id="61e59-195">Select language and telemetry settings</span></span>*


### <span data-ttu-id="61e59-196">Page Windows Update</span><span class="sxs-lookup"><span data-stu-id="61e59-196">Windows Update page</span></span>

<span data-ttu-id="61e59-197">Sélectionnez l’option appropriée pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="61e59-197">Select the option appropriate for your organization.</span></span> <span data-ttu-id="61e59-198">La plupart des organisations avec plusieurs utilisateurs choisissent généralement de recevoir des mises à jour via Windows Server Update Services (WSUS), comme illustré dans la figure 5.</span><span class="sxs-lookup"><span data-stu-id="61e59-198">Most organizations with multiple users will typically select to receive updates via Windows Server Update Services (WSUS), as shown in figure 5.</span></span> <span data-ttu-id="61e59-199">Si vous utilisez des packages Windows Update locaux ou WSUS, entrez le chemin d’accès le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="61e59-199">If using local Windows Update packages or WSUS, enter the path as appropriate.</span></span> 

![Sélectionner l’option Windows Update](images/sdt-5.png)

*<span data-ttu-id="61e59-201">Figure5.</span><span class="sxs-lookup"><span data-stu-id="61e59-201">Figure 5.</span></span> <span data-ttu-id="61e59-202">Option Windows Update</span><span class="sxs-lookup"><span data-stu-id="61e59-202">Windows Update option</span></span>*

### <span data-ttu-id="61e59-203">Page Réparation des logiciels</span><span class="sxs-lookup"><span data-stu-id="61e59-203">Software repair page</span></span>

<span data-ttu-id="61e59-204">Cela vous permet de sélectionner ou de supprimer l’option permettant d’exécuter des mises à jour de réparation logicielle.</span><span class="sxs-lookup"><span data-stu-id="61e59-204">This allows you to select or remove the option to run software repair updates.</span></span> 

![Sélectionner l’option de réparation logicielle](images/sdt-6.png)

*<span data-ttu-id="61e59-206">Figure6.</span><span class="sxs-lookup"><span data-stu-id="61e59-206">Figure 6.</span></span> <span data-ttu-id="61e59-207">Option de réparation logicielle</span><span class="sxs-lookup"><span data-stu-id="61e59-207">Software repair option</span></span>*

### <span data-ttu-id="61e59-208">Collecte des journaux et enregistrement de la page du package</span><span class="sxs-lookup"><span data-stu-id="61e59-208">Collecting logs and saving package page</span></span>

<span data-ttu-id="61e59-209">Vous pouvez choisir d’exécuter un large éventail de journaux sur les applications, les pilotes, le matériel et le système d’exploitation.</span><span class="sxs-lookup"><span data-stu-id="61e59-209">You can select to run a wide range of logs across applications, drivers, hardware, and the operating system.</span></span> <span data-ttu-id="61e59-210">Cliquez sur la zone appropriée et sélectionnez-la dans le menu des journaux disponibles.</span><span class="sxs-lookup"><span data-stu-id="61e59-210">Click the appropriate area and select from the menu of available logs.</span></span> <span data-ttu-id="61e59-211">Vous pouvez ensuite enregistrer le package dans un point de distribution de logiciels ou un emplacement équivalent accessible aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="61e59-211">You can then save the package to a software distribution point or equivalent location that users can access.</span></span> 

![Sélectionner les options du journal](images/sdt-7.png)

*<span data-ttu-id="61e59-213">Figure7.</span><span class="sxs-lookup"><span data-stu-id="61e59-213">Figure 7.</span></span> <span data-ttu-id="61e59-214">Option Journal et package d’enregistrer</span><span class="sxs-lookup"><span data-stu-id="61e59-214">Log option and save package</span></span>*

## <span data-ttu-id="61e59-215">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="61e59-215">Next steps</span></span>

- [<span data-ttu-id="61e59-216">Utiliser le Kit de ressources de diagnostic pour Surface Entreprise en mode bureau</span><span class="sxs-lookup"><span data-stu-id="61e59-216">Use Surface Diagnostic Toolkit for Business in desktop mode</span></span>](surface-diagnostic-toolkit-desktop-mode.md)
- [<span data-ttu-id="61e59-217">Utiliser surface Diagnostic Shared Computer Toolkit for Business à l’aide de commandes</span><span class="sxs-lookup"><span data-stu-id="61e59-217">Use Surface Diagnostic Toolkit for Business using commands</span></span>](surface-diagnostic-toolkit-command-line.md)

## <span data-ttu-id="61e59-218">Modifications et mises à jour</span><span class="sxs-lookup"><span data-stu-id="61e59-218">Changes and updates</span></span>

### <span data-ttu-id="61e59-219">Version 2.131.139.0</span><span class="sxs-lookup"><span data-stu-id="61e59-219">Version 2.131.139.0</span></span>

<span data-ttu-id="61e59-220">Cette version de Surface Diagnostic Shared Computer Toolkit for Business ajoute la prise en charge des produits suivants :</span><span class="sxs-lookup"><span data-stu-id="61e59-220">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span>

- <span data-ttu-id="61e59-221">Prise en charge de Surface Pro 7+</span><span class="sxs-lookup"><span data-stu-id="61e59-221">Support for Surface Pro 7+</span></span>
- <span data-ttu-id="61e59-222">Expérience de prise en charge transparente sur Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="61e59-222">Seamless support experience on Surface Pro X</span></span>
- <span data-ttu-id="61e59-223">Améliorations de la sécurité</span><span class="sxs-lookup"><span data-stu-id="61e59-223">Security improvements</span></span>
- <span data-ttu-id="61e59-224">Améliorations de l’expérience utilisateur inclusive</span><span class="sxs-lookup"><span data-stu-id="61e59-224">Inclusive user experience improvements</span></span>

### <span data-ttu-id="61e59-225">Version 2.124.139.0</span><span class="sxs-lookup"><span data-stu-id="61e59-225">Version 2.124.139.0</span></span>

<span data-ttu-id="61e59-226">Cette version de Surface Diagnostic Shared Computer Toolkit for Business ajoute la prise en charge des produits suivants :</span><span class="sxs-lookup"><span data-stu-id="61e59-226">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span>

- <span data-ttu-id="61e59-227">Prise en charge intégrée transparente</span><span class="sxs-lookup"><span data-stu-id="61e59-227">Seamless integrated support</span></span>
- <span data-ttu-id="61e59-228">Enregistrer tous les résultats des tests</span><span class="sxs-lookup"><span data-stu-id="61e59-228">Save all test results</span></span>
- <span data-ttu-id="61e59-229">Vérifier si l’image est personnalisée créée</span><span class="sxs-lookup"><span data-stu-id="61e59-229">Check if the image is custom created</span></span>
- <span data-ttu-id="61e59-230">Inclure les avertissements du Gestionnaire de périphériques</span><span class="sxs-lookup"><span data-stu-id="61e59-230">Include warnings from device manager</span></span>
- <span data-ttu-id="61e59-231">Version du microprogramme de station d’accueil</span><span class="sxs-lookup"><span data-stu-id="61e59-231">Dock firmware version</span></span>
- <span data-ttu-id="61e59-232">Indicateur des lecteurs comme des défaillances potentielles dans le test de stockage</span><span class="sxs-lookup"><span data-stu-id="61e59-232">Flag drives as potential failures in storage test</span></span>
- <span data-ttu-id="61e59-233">Supprimer le lien de la boutique</span><span class="sxs-lookup"><span data-stu-id="61e59-233">Remove store link</span></span> 

### <span data-ttu-id="61e59-234">Version 2.121.139</span><span class="sxs-lookup"><span data-stu-id="61e59-234">Version 2.121.139</span></span>
*<span data-ttu-id="61e59-235">Date de publication : 31 juillet 2020</span><span class="sxs-lookup"><span data-stu-id="61e59-235">Release date: July 31 2020</span></span>*<br>
<span data-ttu-id="61e59-236">Cette version de Surface Diagnostic Shared Computer Toolkit for Business ajoute la prise en charge des produits suivants :</span><span class="sxs-lookup"><span data-stu-id="61e59-236">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span>

- <span data-ttu-id="61e59-237">Expérience de support transparente</span><span class="sxs-lookup"><span data-stu-id="61e59-237">Seamless support experience</span></span>
- <span data-ttu-id="61e59-238">Résolutions de bogues</span><span class="sxs-lookup"><span data-stu-id="61e59-238">Bug fixes</span></span>

### <span data-ttu-id="61e59-239">Version 2.94.139.0</span><span class="sxs-lookup"><span data-stu-id="61e59-239">Version 2.94.139.0</span></span>
*<span data-ttu-id="61e59-240">Date de publication : 11 mai 2020</span><span class="sxs-lookup"><span data-stu-id="61e59-240">Release date: May 11, 2020</span></span>*<br>
<span data-ttu-id="61e59-241">Cette version de Surface Diagnostic Shared Computer Toolkit for Business ajoute la prise en charge des produits suivants :</span><span class="sxs-lookup"><span data-stu-id="61e59-241">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span>

- <span data-ttu-id="61e59-242">Possibilité d’ignorer Windows Update pour effectuer une vérification matérielle.</span><span class="sxs-lookup"><span data-stu-id="61e59-242">Ability to skip Windows Update to perform hardware check.</span></span>
- <span data-ttu-id="61e59-243">Possibilité de recevoir des notifications concernant la dernière mise à jour de version</span><span class="sxs-lookup"><span data-stu-id="61e59-243">Ability to receive notifications for about the latest version update</span></span>
- <span data-ttu-id="61e59-244">SurfaceGo2</span><span class="sxs-lookup"><span data-stu-id="61e59-244">Surface Go 2</span></span>
- <span data-ttu-id="61e59-245">SurfaceBook3</span><span class="sxs-lookup"><span data-stu-id="61e59-245">Surface Book 3</span></span>
- <span data-ttu-id="61e59-246">Afficher l’indicateur de progression</span><span class="sxs-lookup"><span data-stu-id="61e59-246">Show progress indicator</span></span>


### <span data-ttu-id="61e59-247">Version 2.43.139.0</span><span class="sxs-lookup"><span data-stu-id="61e59-247">Version 2.43.139.0</span></span>
*<span data-ttu-id="61e59-248">Date de publication : 21 octobre 2019</span><span class="sxs-lookup"><span data-stu-id="61e59-248">Release date: October 21, 2019</span></span>*<br>
<span data-ttu-id="61e59-249">Cette version de Surface Diagnostic Shared Computer Toolkit for Business ajoute la prise en charge des produits suivants :</span><span class="sxs-lookup"><span data-stu-id="61e59-249">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span>

- <span data-ttu-id="61e59-250">SurfacePro7</span><span class="sxs-lookup"><span data-stu-id="61e59-250">Surface Pro 7</span></span>
- <span data-ttu-id="61e59-251">Surface Laptop3</span><span class="sxs-lookup"><span data-stu-id="61e59-251">Surface Laptop 3</span></span>

### <span data-ttu-id="61e59-252">Version 2.42.139.0</span><span class="sxs-lookup"><span data-stu-id="61e59-252">Version 2.42.139.0</span></span>
*<span data-ttu-id="61e59-253">Date de publication : 24 septembre 2019</span><span class="sxs-lookup"><span data-stu-id="61e59-253">Release date: September 24, 2019</span></span>*<br>
<span data-ttu-id="61e59-254">Cette version de Surface Diagnostic Shared Computer Toolkit for Business ajoute la prise en charge des produits suivants :</span><span class="sxs-lookup"><span data-stu-id="61e59-254">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span> 
- <span data-ttu-id="61e59-255">Possibilité de télécharger des rapports matériels.</span><span class="sxs-lookup"><span data-stu-id="61e59-255">Ability to download hardware reports.</span></span>
- <span data-ttu-id="61e59-256">Possibilité de contacter le Support Microsoft directement à partir de l’outil.</span><span class="sxs-lookup"><span data-stu-id="61e59-256">Ability to contact Microsoft Support directly from the tool.</span></span> <br>

### <span data-ttu-id="61e59-257">Version 2.41.139.0</span><span class="sxs-lookup"><span data-stu-id="61e59-257">Version 2.41.139.0</span></span>
*<span data-ttu-id="61e59-258">Date de publication : 24 juin 2019</span><span class="sxs-lookup"><span data-stu-id="61e59-258">Release date: June 24, 2019</span></span>*<br>
<span data-ttu-id="61e59-259">Cette version de Surface Diagnostic Shared Computer Toolkit for Business ajoute la prise en charge des produits suivants :</span><span class="sxs-lookup"><span data-stu-id="61e59-259">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span> 
- <span data-ttu-id="61e59-260">Informations sur la version du pilote incluses dans les journaux et les rapports.</span><span class="sxs-lookup"><span data-stu-id="61e59-260">Driver version information included in logs and report.</span></span>
- <span data-ttu-id="61e59-261">Possibilité de fournir des commentaires sur l’application.</span><span class="sxs-lookup"><span data-stu-id="61e59-261">Ability to provide feedback about the app.</span></span><br>


### <span data-ttu-id="61e59-262">Version 2.36.139.0</span><span class="sxs-lookup"><span data-stu-id="61e59-262">Version 2.36.139.0</span></span>
*<span data-ttu-id="61e59-263">Date de publication : 26 avril 2019</span><span class="sxs-lookup"><span data-stu-id="61e59-263">Release date: April 26, 2019</span></span>*<br>
<span data-ttu-id="61e59-264">Cette version de Surface Diagnostic Shared Computer Toolkit for Business ajoute la prise en charge des produits suivants :</span><span class="sxs-lookup"><span data-stu-id="61e59-264">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span> 
- <span data-ttu-id="61e59-265">Option d’installation avancée pour déverrouiller les fonctionnalités d’administration via l’interface utilisateur du programme d’installation, sans nécessiter de configuration de ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="61e59-265">Advanced Setup option to unlock admin capabilities through the installer UI, without requiring command line configuration.</span></span>
- <span data-ttu-id="61e59-266">Améliorations en matière d’accessibilité.</span><span class="sxs-lookup"><span data-stu-id="61e59-266">Accessibility improvements.</span></span>
- <span data-ttu-id="61e59-267">Paramètres de contrôle de luminosité de surface inclus dans les journaux.</span><span class="sxs-lookup"><span data-stu-id="61e59-267">Surface brightness control settings included in logs.</span></span>
- <span data-ttu-id="61e59-268">Lien de prise en charge de la compatibilité du moniteur externe dans le générateur de rapports.</span><span class="sxs-lookup"><span data-stu-id="61e59-268">External monitor compatibility support link in report generator.</span></span>
