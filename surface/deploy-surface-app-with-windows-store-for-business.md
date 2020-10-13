---
title: Déploiement d’une application de surface avec Microsoft Store entreprise ou Microsoft Store pour l’éducation (surface)
description: Découvrez comment ajouter et télécharger une application de surface avec Microsoft Store pour les entreprises ou Microsoft Store pour l’éducation, et pour installer une application de surface avec PowerShell et MDT.
keywords: application de surface, application, déploiement, personnalisation
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, store
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
ms.audience: itpro
ms.reviewer: ''
manager: laurawi
ms.openlocfilehash: 811feff1f0643ab0ba5d624c5f7d561ba5b0cd4d
ms.sourcegitcommit: c1efb75e8524193bdc0a5f7496dc23a92ac665c8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/12/2020
ms.locfileid: "11114712"
---
# <span data-ttu-id="6badd-104">Déploiement d’une application de surface avec Microsoft Store pour les entreprises et l’éducation</span><span class="sxs-lookup"><span data-stu-id="6badd-104">Deploy Surface app with Microsoft Store for Business and Education</span></span>

**<span data-ttu-id="6badd-105">Concerne</span><span class="sxs-lookup"><span data-stu-id="6badd-105">Applies to</span></span>**

- <span data-ttu-id="6badd-106">Surface Laptop Go</span><span class="sxs-lookup"><span data-stu-id="6badd-106">Surface Laptop Go</span></span>
- <span data-ttu-id="6badd-107">SurfacePro7</span><span class="sxs-lookup"><span data-stu-id="6badd-107">Surface Pro 7</span></span>
- <span data-ttu-id="6badd-108">Surface Laptop3</span><span class="sxs-lookup"><span data-stu-id="6badd-108">Surface Laptop 3</span></span>
- <span data-ttu-id="6badd-109">SurfacePro6</span><span class="sxs-lookup"><span data-stu-id="6badd-109">Surface Pro 6</span></span>
- <span data-ttu-id="6badd-110">Surface Laptop2</span><span class="sxs-lookup"><span data-stu-id="6badd-110">Surface Laptop 2</span></span>
- <span data-ttu-id="6badd-111">SurfaceGo</span><span class="sxs-lookup"><span data-stu-id="6badd-111">Surface Go</span></span>
- <span data-ttu-id="6badd-112">Surface Go avec LTE</span><span class="sxs-lookup"><span data-stu-id="6badd-112">Surface Go with LTE</span></span>
- <span data-ttu-id="6badd-113">SurfaceBook2</span><span class="sxs-lookup"><span data-stu-id="6badd-113">Surface Book 2</span></span>
- <span data-ttu-id="6badd-114">SurfacePro avec LTE Advanced (modèle1807)</span><span class="sxs-lookup"><span data-stu-id="6badd-114">Surface Pro with LTE Advanced (Model 1807)</span></span>
- <span data-ttu-id="6badd-115">SurfacePro (modèle1796)</span><span class="sxs-lookup"><span data-stu-id="6badd-115">Surface Pro (Model 1796)</span></span>
- <span data-ttu-id="6badd-116">Surface Laptop</span><span class="sxs-lookup"><span data-stu-id="6badd-116">Surface Laptop</span></span>
- <span data-ttu-id="6badd-117">SurfaceStudio</span><span class="sxs-lookup"><span data-stu-id="6badd-117">Surface Studio</span></span>
- <span data-ttu-id="6badd-118">Surface Studio2</span><span class="sxs-lookup"><span data-stu-id="6badd-118">Surface Studio 2</span></span>
- <span data-ttu-id="6badd-119">SurfaceBook</span><span class="sxs-lookup"><span data-stu-id="6badd-119">Surface Book</span></span>
- <span data-ttu-id="6badd-120">Surface Pro4</span><span class="sxs-lookup"><span data-stu-id="6badd-120">Surface Pro 4</span></span>
- <span data-ttu-id="6badd-121">VersionsLTE du modèleSurface3</span><span class="sxs-lookup"><span data-stu-id="6badd-121">Surface 3 LTE</span></span>
- <span data-ttu-id="6badd-122">Surface3</span><span class="sxs-lookup"><span data-stu-id="6badd-122">Surface 3</span></span>
- <span data-ttu-id="6badd-123">Surface Pro3</span><span class="sxs-lookup"><span data-stu-id="6badd-123">Surface Pro 3</span></span>


<span data-ttu-id="6badd-124">L’application surface est une application légère du Microsoft Store qui fournit le contrôle de nombreux paramètres et options spécifiques à la surface, notamment:</span><span class="sxs-lookup"><span data-stu-id="6badd-124">The Surface app is a lightweight Microsoft Store app that provides control of many Surface-specific settings and options, including:</span></span> 

* <span data-ttu-id="6badd-125">Activer ou désactiver le boutonWindows sur l’appareilSurface</span><span class="sxs-lookup"><span data-stu-id="6badd-125">Enable or disable the Windows button on the Surface device</span></span> 

* <span data-ttu-id="6badd-126">Ajuster la sensibilité du styletSurface</span><span class="sxs-lookup"><span data-stu-id="6badd-126">Adjust the sensitivity of a Surface Pen</span></span> 

* <span data-ttu-id="6badd-127">Personnaliser les actions des boutons des styletsSurface</span><span class="sxs-lookup"><span data-stu-id="6badd-127">Customize Surface Pen button actions</span></span> 

* <span data-ttu-id="6badd-128">Activer ou désactiver les améliorations audio de l’appareilSurface</span><span class="sxs-lookup"><span data-stu-id="6badd-128">Enable or disable Surface audio enhancements</span></span> 

* <span data-ttu-id="6badd-129">Accès rapide à la documentation et aux informations de support pour votre appareil</span><span class="sxs-lookup"><span data-stu-id="6badd-129">Quick access to support documentation and information for your device</span></span>

<span data-ttu-id="6badd-130">Les clients qui utilisent Windows Update recevront généralement l’application surface dans le cadre de mises à jour automatiques.</span><span class="sxs-lookup"><span data-stu-id="6badd-130">Customers using Windows Update will ordinarily receive Surface app as part of automatic updates.</span></span> <span data-ttu-id="6badd-131">En revanche, si votre organisation prépare des images à déployer sur vos appareils surface, vous pouvez inclure l’application surface (auparavant appelée surface Hub) dans votre processus d’imagerie et de déploiement au lieu de demander aux utilisateurs de chaque appareil de télécharger et d’installer l’application à partir du Microsoft Store ou de la boutique Microsoft pour les entreprises.</span><span class="sxs-lookup"><span data-stu-id="6badd-131">But if your organization is preparing images for deployment to your Surface devices, you may want to include the Surface app (formerly called the Surface Hub) in your imaging and deployment process instead of requiring users of each individual device to download and install the app from the Microsoft Store or your Microsoft Store for Business.</span></span> 

> [!NOTE]
> <span data-ttu-id="6badd-132">Cet article ne s’applique pas à surface Pro X. Pour plus d’informations, reportez-vous à [déploiement, gestion et maintenance de surface Pro X](surface-pro-arm-app-management.md) .</span><span class="sxs-lookup"><span data-stu-id="6badd-132">This article does not apply to Surface Pro X. For more information, refer to [Deploying, managing, and servicing Surface Pro X](surface-pro-arm-app-management.md)</span></span>

## <span data-ttu-id="6badd-133">Présentation de l’application surface</span><span class="sxs-lookup"><span data-stu-id="6badd-133">Surface app overview</span></span>

<span data-ttu-id="6badd-134">L’application surface est disponible en téléchargement gratuit à partir du [Microsoft Store](https://www.microsoft.com/store/apps/Surface/9WZDNCRFJB8P).</span><span class="sxs-lookup"><span data-stu-id="6badd-134">The Surface app is available as a free download from the [Microsoft Store](https://www.microsoft.com/store/apps/Surface/9WZDNCRFJB8P).</span></span> <span data-ttu-id="6badd-135">Les utilisateurs peuvent le télécharger et l’installer à partir du Microsoft Store, mais si votre organisation utilise plutôt le Microsoft Store entreprise, vous devez l’ajouter au stock de votre magasin et éventuellement inclure l’application dans le cadre de votre processus de déploiement Windows.</span><span class="sxs-lookup"><span data-stu-id="6badd-135">Users can download and install it from the Microsoft Store, but if your organization uses Microsoft Store for Business instead, you will need to add it to your store’s inventory and possibly include the app as part of your Windows deployment process.</span></span> <span data-ttu-id="6badd-136">Ces processus sont abordés dans cet article.</span><span class="sxs-lookup"><span data-stu-id="6badd-136">These processes are discussed throughout this article.</span></span> <span data-ttu-id="6badd-137">Pour plus d’informations sur le Microsoft Store pour les entreprises, voir [Microsoft Store pour les entreprises](https://docs.microsoft.com/microsoft-store/) dans le Windows TechCenter.</span><span class="sxs-lookup"><span data-stu-id="6badd-137">For more information about Microsoft Store for Business, see [Microsoft Store for Business](https://docs.microsoft.com/microsoft-store/) in the Windows TechCenter.</span></span> 

## <span data-ttu-id="6badd-138">Ajouter une application de surface à un compte Microsoft Store pour les entreprises</span><span class="sxs-lookup"><span data-stu-id="6badd-138">Add Surface app to a Microsoft Store for Business account</span></span> 

<span data-ttu-id="6badd-139">Pour que les utilisateurs puissent installer ou déployer une application à partir du compte Microsoft Store entreprise d’une entreprise, les applications souhaitées doivent d’abord être mises à disposition et sous licence des utilisateurs d’une entreprise.</span><span class="sxs-lookup"><span data-stu-id="6badd-139">Before users can install or deploy an app from a company’s Microsoft Store for Business account, the desired app(s) must first be made available and licensed to the users of a business.</span></span> 

1. <span data-ttu-id="6badd-140">Si vous ne l’avez pas déjà fait, créez un [compte Microsoft Store pour les entreprises](https://www.microsoft.com/business-store).</span><span class="sxs-lookup"><span data-stu-id="6badd-140">If you have not already done so, create a [Microsoft Store for Business account](https://www.microsoft.com/business-store).</span></span> 

2. <span data-ttu-id="6badd-141">Ouvrez une session sur le portail.</span><span class="sxs-lookup"><span data-stu-id="6badd-141">Log on to the portal.</span></span> 

3. <span data-ttu-id="6badd-142">Activez la gestion >des licences hors connexion: cliquez sur **gérer les paramètres**du Windows Store, puis activez la case à cocher **afficher les applications sous licence hors connexion aux personnes qui se trouvent dans le Windows Store** , comme illustré dans la figure 1.</span><span class="sxs-lookup"><span data-stu-id="6badd-142">Enable offline licensing: click **Manage->Store settings**, and then select the **Show offline licensed apps to people shopping in the store** checkbox, as shown in Figure 1.</span></span> <span data-ttu-id="6badd-143">Pour plus d’informations sur les modèles de licences d’application Microsoft Store pour les entreprises, voir [applications dans le Microsoft Store pour les entreprises et l’éducation](https://docs.microsoft.com/microsoft-store/).</span><span class="sxs-lookup"><span data-stu-id="6badd-143">For more information about Microsoft Store for Business app licensing models, see [Apps in Microsoft Store for Business and Education](https://docs.microsoft.com/microsoft-store/).</span></span>

   > [!div class="mx-imgBorder"]
   > ![Case à cocher Afficher les applications de licences hors connexion](images/deploysurfapp-figure1-enablingapps.png "Show offline licenses apps checkbox")<br/>
   *<span data-ttu-id="6badd-145">Figure1.</span><span class="sxs-lookup"><span data-stu-id="6badd-145">Figure 1.</span></span> <span data-ttu-id="6badd-146">Activer les applications pour une utilisation hors connexion</span><span class="sxs-lookup"><span data-stu-id="6badd-146">Enable apps for offline use</span></span>*

4. <span data-ttu-id="6badd-147">Ajoutez une application de surface à votre compte Microsoft Store pour les entreprises en procédant comme suit:</span><span class="sxs-lookup"><span data-stu-id="6badd-147">Add Surface app to your Microsoft Store for Business account by following this procedure:</span></span>

    * <span data-ttu-id="6badd-148">Cliquez sur le menu **Shop** .</span><span class="sxs-lookup"><span data-stu-id="6badd-148">Click the **Shop** menu.</span></span>
    
    * <span data-ttu-id="6badd-149">Dans la zone de recherche, tapez **application surface**, puis cliquez sur l’icône Rechercher.</span><span class="sxs-lookup"><span data-stu-id="6badd-149">In the search box, type **Surface app**, and then click the search icon.</span></span>
    
    * <span data-ttu-id="6badd-150">Après la présentation de l’application surface dans les résultats de la recherche, cliquez sur l’icône de l’application.</span><span class="sxs-lookup"><span data-stu-id="6badd-150">After the Surface app is presented in the search results, click the app’s icon.</span></span>
    
    * <span data-ttu-id="6badd-151">Vous avez le choix entre une option (sélectionnez **en ligne** ou en **mode hors connexion**), comme illustré dans la figure 2.</span><span class="sxs-lookup"><span data-stu-id="6badd-151">You are presented with a choice (select **Online** or **Offline**), as shown in Figure 2.</span></span>
    
      > [!div class="mx-imgBorder"]
      > ![Sélectionner le mode de gestion des licences hors connexion et ajouter l’application à votre inventaire](images/deploysurfapp-fig2-selectingofflinelicense.png "Select the Offline licensing mode and add the app to your inventory")   
      *<span data-ttu-id="6badd-153">Figure2.</span><span class="sxs-lookup"><span data-stu-id="6badd-153">Figure 2.</span></span> <span data-ttu-id="6badd-154">Sélectionner le mode de gestion des licences hors connexion et ajouter l’application à votre inventaire</span><span class="sxs-lookup"><span data-stu-id="6badd-154">Select the Offline licensing mode and add the app to your inventory</span></span>*
    
    * <span data-ttu-id="6badd-155">Cliquez sur **hors connexion** pour sélectionner le mode de gestion des licences hors connexion.</span><span class="sxs-lookup"><span data-stu-id="6badd-155">Click **Offline** to select the Offline licensing mode.</span></span>
    
    * <span data-ttu-id="6badd-156">Cliquez sur **obtenir l’application** pour ajouter l’application à votre inventaire Microsoft Store pour les entreprises.</span><span class="sxs-lookup"><span data-stu-id="6badd-156">Click **Get the app** to add the app to your Microsoft Store for Business inventory.</span></span> <span data-ttu-id="6badd-157">Comme le montre la figure 3, une boîte de dialogue s’affiche pour vous demander d’accepter que les applications hors connexion peuvent être déployées à l’aide d’un outil de gestion ou téléchargées à partir de la page d’inventaire de la société dans leur magasin privé.</span><span class="sxs-lookup"><span data-stu-id="6badd-157">As shown in Figure 3, you’ll see a dialog box that prompts you to acknowledge that offline apps can be deployed using a management tool or downloaded from the company’s inventory page in their private store.</span></span>
    
      > [!div class="mx-imgBorder"]
      > ![<span data-ttu-id="6badd-158">Fenêtre accusé de réception de l’application sous licence hors connexion ](images/deploysurfapp-fig3-acknowledge.png "Offline-licensed app acknowledgement window")
       *figure 3. Accusé de réception de l’application sous licence hors connexion*</span><span class="sxs-lookup"><span data-stu-id="6badd-158">Offline-licensed app acknowledgement window](images/deploysurfapp-fig3-acknowledge.png "Offline-licensed app acknowledgement window")
*Figure 3. Offline-licensed app acknowledgement*</span></span>
      
    * <span data-ttu-id="6badd-159">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="6badd-159">Click **OK**.</span></span>

## <span data-ttu-id="6badd-160">Télécharger l’application surface à partir d’un compte Microsoft Store pour les entreprises</span><span class="sxs-lookup"><span data-stu-id="6badd-160">Download Surface app from a Microsoft Store for Business account</span></span>
<span data-ttu-id="6badd-161">Après avoir ajouté une application au compte Microsoft Store entreprise en mode hors connexion, vous pouvez télécharger et ajouter l’application en tant que fichier AppxBundle à un partage de déploiement.</span><span class="sxs-lookup"><span data-stu-id="6badd-161">After you add an app to the Microsoft Store for Business account in Offline mode, you can download and add the app as an AppxBundle to a deployment share.</span></span>

1. <span data-ttu-id="6badd-162">Connectez-vous au compte Microsoft Store pour les entreprises à l’adresse https://businessstore.microsoft.com .</span><span class="sxs-lookup"><span data-stu-id="6badd-162">Log on to the Microsoft Store for Business account at https://businessstore.microsoft.com.</span></span>

2. <span data-ttu-id="6badd-163">Cliquez sur **gérer->applications & logiciel**.</span><span class="sxs-lookup"><span data-stu-id="6badd-163">Click **Manage->Apps & software**.</span></span> <span data-ttu-id="6badd-164">La liste de toutes les applications de votre entreprise s’affiche, y compris l’application surface que vous avez ajoutée dans la section [Ajouter une application surface à un compte Microsoft Store pour les entreprises](#add-surface-app-to-a-microsoft-store-for-business-account) de cet article.</span><span class="sxs-lookup"><span data-stu-id="6badd-164">A list of all of your company’s apps is displayed, including the Surface app you added in the [Add Surface app to a Microsoft Store for Business account](#add-surface-app-to-a-microsoft-store-for-business-account) section of this article.</span></span>

3. <span data-ttu-id="6badd-165">Sous **actions**, cliquez sur les points de suspension (**...**), puis sur **Télécharger pour une utilisation en mode hors connexion** pour l’application surface.</span><span class="sxs-lookup"><span data-stu-id="6badd-165">Under **Actions**, click the ellipsis (**…**), and then click **Download for offline use** for the Surface app.</span></span>

4. <span data-ttu-id="6badd-166">Sélectionnez les options de **plateforme** et d' **architecture** souhaitées dans les sélections disponibles pour l’application sélectionnée, comme illustré dans la figure 4.</span><span class="sxs-lookup"><span data-stu-id="6badd-166">Select the desired **Platform** and **Architecture** options from the available selections for the selected app, as shown in Figure 4.</span></span>

    > [!div class="mx-imgBorder"]
    > ![Exemple du package AppxBundle](images/deploysurfapp-fig4-downloadappxbundle.png "Example of the AppxBundle package")<br/>
    *<span data-ttu-id="6badd-168">Figure4.</span><span class="sxs-lookup"><span data-stu-id="6badd-168">Figure 4.</span></span> <span data-ttu-id="6badd-169">Télécharger le package AppxBundle pour une application</span><span class="sxs-lookup"><span data-stu-id="6badd-169">Download the AppxBundle package for an app</span></span>*
    
5. <span data-ttu-id="6badd-170">Cliquez sur **Télécharger**.</span><span class="sxs-lookup"><span data-stu-id="6badd-170">Click **Download**.</span></span> <span data-ttu-id="6badd-171">Le package AppxBundle sera téléchargé.</span><span class="sxs-lookup"><span data-stu-id="6badd-171">The AppxBundle package will be downloaded.</span></span> <span data-ttu-id="6badd-172">Assurez-vous de noter le chemin du fichier téléchargé, car vous en aurez besoin plus tard dans cet article.</span><span class="sxs-lookup"><span data-stu-id="6badd-172">Make sure you note the path of the downloaded file because you’ll need that later in this article.</span></span>

6. <span data-ttu-id="6badd-173">Cliquez sur l’option **licence encodée** ou **licence** non codée.</span><span class="sxs-lookup"><span data-stu-id="6badd-173">Click either the **Encoded license** or **Unencoded license** option.</span></span> <span data-ttu-id="6badd-174">Utilisez l’option de licence encodée avec des outils de gestion tels que Microsoft Endpoint Configuration Manager ou lorsque vous utilisez le concepteur de configuration Windows pour créer un package de mise en service.</span><span class="sxs-lookup"><span data-stu-id="6badd-174">Use the Encoded license option with management tools like Microsoft Endpoint Configuration Manager or when you use Windows Configuration Designer to create a provisioning package.</span></span> <span data-ttu-id="6badd-175">Sélectionnez l’option de licence non encodée lorsque vous utilisez des solutions de maintenance et de gestion des images de déploiement en fonction de l’image, y compris le kit de développement logiciel Microsoft Deployment (MDT).</span><span class="sxs-lookup"><span data-stu-id="6badd-175">Select the Unencoded license option when you use Deployment Image Servicing and Management (DISM) or deployment solutions based on imaging, including the Microsoft Deployment Toolkit (MDT).</span></span>

7. <span data-ttu-id="6badd-176">Cliquez sur **générer** pour générer et télécharger la licence de l’application.</span><span class="sxs-lookup"><span data-stu-id="6badd-176">Click **Generate** to generate and download the license for the app.</span></span> <span data-ttu-id="6badd-177">Assurez-vous de noter le chemin d’accès du fichier de licence, car vous en aurez besoin plus tard dans cet article.</span><span class="sxs-lookup"><span data-stu-id="6badd-177">Make sure you note the path of the license file because you’ll need that later in this article.</span></span>

>[!NOTE]
><span data-ttu-id="6badd-178">Lorsque vous téléchargez une application pour une utilisation en mode hors connexion, par exemple, l’application surface, vous pouvez remarquer une section en bas de la page intitulée **infrastructures requises**.</span><span class="sxs-lookup"><span data-stu-id="6badd-178">When you download an app for offline use, such as the Surface app, you may notice a section at the bottom of the page labeled **Required frameworks**.</span></span> <span data-ttu-id="6badd-179">Pour qu’une application puisse s’exécuter sur vos ordinateurs cibles, il est possible que vous deviez répéter le processus de téléchargement de chaque infrastructure requise pour votre architecture (x86 ou x64) et les inclure dans le cadre de votre déploiement Windows abordé plus loin dans cet article.</span><span class="sxs-lookup"><span data-stu-id="6badd-179">Your target computers must have the frameworks installed for the app to run, so you may need to repeat the download process for each of the required frameworks for your architecture (either x86 or x64) and also include them as part of your Windows deployment discussed later in this article.</span></span>

<span data-ttu-id="6badd-180">La figure 5 montre les infrastructures nécessaires pour l’application surface.</span><span class="sxs-lookup"><span data-stu-id="6badd-180">Figure 5 shows the required frameworks for the Surface app.</span></span>

> [!div class="mx-imgBorder"]
> ![Infrastructures requises pour l’application surface](images/deploysurfapp-fig5-requiredframework.png "Required frameworks for the Surface app")<br/>
*<span data-ttu-id="6badd-182">Figure5.</span><span class="sxs-lookup"><span data-stu-id="6badd-182">Figure 5.</span></span> <span data-ttu-id="6badd-183">Infrastructures requises pour l’application surface</span><span class="sxs-lookup"><span data-stu-id="6badd-183">Required frameworks for the Surface app</span></span>*

>[!NOTE]
><span data-ttu-id="6badd-184">Les numéros de version de l’application surface et les infrastructures requises seront modifiés à mesure que les applications sont mises à jour.</span><span class="sxs-lookup"><span data-stu-id="6badd-184">The version numbers of the Surface app and required frameworks will change as the apps are updated.</span></span> <span data-ttu-id="6badd-185">Recherchez la dernière version de l’application surface et chaque infrastructure de la boutique Microsoft pour les entreprises.</span><span class="sxs-lookup"><span data-stu-id="6badd-185">Check for the latest version of Surface app and each framework in Microsoft Store for Business.</span></span> <span data-ttu-id="6badd-186">Utilisez toujours l’application surface et les versions d’infrastructure recommandées fournies par le Microsoft Store pour entreprises.</span><span class="sxs-lookup"><span data-stu-id="6badd-186">Always use the Surface app and recommended framework versions as provided by Microsoft Store for Business.</span></span> <span data-ttu-id="6badd-187">L’utilisation d’infrastructures obsolètes ou de versions incorrectes risque de provoquer des erreurs ou des blocages d’applications.</span><span class="sxs-lookup"><span data-stu-id="6badd-187">Using outdated frameworks or the incorrect versions may result in errors or application crashes.</span></span>

<span data-ttu-id="6badd-188">Pour télécharger les infrastructures requises pour l’application surface, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="6badd-188">To download the required frameworks for the Surface app, follow these steps:</span></span>

1. <span data-ttu-id="6badd-189">Cliquez sur le bouton **Télécharger** sous **Microsoft. VCLibs. 140.00 _14.0.23816.0 _x64__8wekyb3d8bbwe**.</span><span class="sxs-lookup"><span data-stu-id="6badd-189">Click the **Download** button under **Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe**.</span></span> <span data-ttu-id="6badd-190">Cette opération télécharge le VCLibs. 140.00 _14.0.23816.0 _x64__8wekyb3d8bbwe. Fichier AppX dans le dossier spécifié.</span><span class="sxs-lookup"><span data-stu-id="6badd-190">This downloads the Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe.Appx file to your specified folder.</span></span>

2. <span data-ttu-id="6badd-191">Cliquez sur le bouton **Télécharger** sous **Microsoft. net. native. Runtime. 1.1 _ _ 1.23406.0 _x64__8wekyb3d8bbwe**.</span><span class="sxs-lookup"><span data-stu-id="6badd-191">Click the **Download** button under **Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe**.</span></span> <span data-ttu-id="6badd-192">Le téléchargement du fichier Microsoft. NET. native. Runtime. 1.1 _ 1.23406. _x64__8wekyb3d8bbwe. AppX dans le dossier spécifié.</span><span class="sxs-lookup"><span data-stu-id="6badd-192">This downloads the Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe.Appx file to your specified folder.</span></span>

>[!NOTE]
><span data-ttu-id="6badd-193">Seule la version 64 bits (x64) de chaque infrastructure est nécessaire pour les appareils surface.</span><span class="sxs-lookup"><span data-stu-id="6badd-193">Only the 64-bit (x64) version of each framework is required for Surface devices.</span></span> <span data-ttu-id="6badd-194">64 les appareils surface s’exécutent sous la seule version et ne sont pas compatibles avec les versions 32 bits (x86) de Windows qui nécessitent des infrastructures 32.</span><span class="sxs-lookup"><span data-stu-id="6badd-194">Surface devices are native 64-bit UEFI devices and are not compatible with 32-bit (x86) versions of Windows that would require 32-bit frameworks.</span></span> 

## <span data-ttu-id="6badd-195">Installation de l’application surface sur votre ordinateur avec PowerShell</span><span class="sxs-lookup"><span data-stu-id="6badd-195">Install Surface app on your computer with PowerShell</span></span>
<span data-ttu-id="6badd-196">La procédure suivante met en service l’application surface sur votre ordinateur et la rend disponible pour tous les comptes d’utilisateurs créés sur l’ordinateur ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="6badd-196">The following procedure provisions the Surface app onto your computer and makes it available for any user accounts created on the computer afterwards.</span></span>

1. <span data-ttu-id="6badd-197">À l’aide de la procédure décrite dans la section [Comment télécharger l’application de surface à partir d’un compte Microsoft Store pour les entreprises](#download-surface-app-from-a-microsoft-store-for-business-account) de cet article, téléchargez l’application de surface AppxBundle et le fichier de licence.</span><span class="sxs-lookup"><span data-stu-id="6badd-197">Using the procedure described in the [How to download Surface app from a Microsoft Store for Business account](#download-surface-app-from-a-microsoft-store-for-business-account) section of this article, download the Surface app AppxBundle and license file.</span></span> 

2. <span data-ttu-id="6badd-198">Lancez une sessionPowerShell avec élévation des privilèges.</span><span class="sxs-lookup"><span data-stu-id="6badd-198">Begin an elevated PowerShell session.</span></span>

    >[!NOTE]
    ><span data-ttu-id="6badd-199">Si vous n’exécutez pas PowerShell en tant qu’administrateur, la session n’aura pas les autorisations requises pour installer l’application.</span><span class="sxs-lookup"><span data-stu-id="6badd-199">If you don’t run PowerShell as an Administrator, the session won’t have the required permissions to install the app.</span></span>
    
3. <span data-ttu-id="6badd-200">Dans la sessionPowerShell avec élévation de privilèges, copiez et collez la commande suivante:</span><span class="sxs-lookup"><span data-stu-id="6badd-200">In the elevated PowerShell session, copy and paste the following command:</span></span>

    ```powershell
    Add-AppxProvisionedPackage –Online –PackagePath <DownloadPath>\ Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle –LicensePath <DownloadPath>\ Microsoft.SurfaceHub_8wekyb3d8bbwe_a53ef8ab-9dbd-dec1-46c5-7b664d4dd003.xml
    ```

    <span data-ttu-id="6badd-201">Où `<DownloadPath>` se trouve le dossier dans lequel vous avez téléchargé les fichiers AppxBundle et de licence à partir du compte Microsoft Store pour les entreprises.</span><span class="sxs-lookup"><span data-stu-id="6badd-201">Where `<DownloadPath>` is the folder where you downloaded the AppxBundle and license file from the Microsoft Store for Business account.</span></span>

    <span data-ttu-id="6badd-202">Par exemple, si vous avez téléchargé les fichiers sur c:\Temp, la commande exécutée est la suivante:</span><span class="sxs-lookup"><span data-stu-id="6badd-202">For example, if you downloaded the files to c:\Temp, the command you run is:</span></span>
    
    ```powershell
    Add-AppxProvisionedPackage –Online –PackagePath c:\Temp\ Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle –LicensePath c:\Temp\ Microsoft.SurfaceHub_8wekyb3d8bbwe_a53ef8ab-9dbd-dec1-46c5-7b664d4dd003.xml
    ```

4. <span data-ttu-id="6badd-203">L’applicationSurface est désormais disponible sur votre ordinateurWindows actuel.</span><span class="sxs-lookup"><span data-stu-id="6badd-203">The Surface app will now be available on your current Windows computer.</span></span> 

   <span data-ttu-id="6badd-204">Pour que l’application surface fonctionne sur l’ordinateur sur lequel elle a été configurée, vous devez également configurer les infrastructures décrites précédemment dans cet article.</span><span class="sxs-lookup"><span data-stu-id="6badd-204">Before the Surface app is functional on the computer where it has been provisioned, you must also provision the frameworks described earlier in this article.</span></span> <span data-ttu-id="6badd-205">Pour mettre en service ces infrastructures, utilisez la procédure suivante dans la session PowerShell avec élévation de privilèges que vous avez utilisée pour approvisionner l’application surface.</span><span class="sxs-lookup"><span data-stu-id="6badd-205">To provision these frameworks, use the following procedure in the elevated PowerShell session you used to provision the Surface app.</span></span>

5. <span data-ttu-id="6badd-206">Dans la sessionPowerShell avec élévation de privilèges, copiez et collez la commande suivante:</span><span class="sxs-lookup"><span data-stu-id="6badd-206">In the elevated PowerShell session, copy and paste the following command:</span></span>

   ```powershell
   Add-AppxProvisionedPackage –Online –SkipLicense –PackagePath <DownloadPath>\Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe.Appx
   ```
   
6. <span data-ttu-id="6badd-207">Dans la sessionPowerShell avec élévation de privilèges, copiez et collez la commande suivante:</span><span class="sxs-lookup"><span data-stu-id="6badd-207">In the elevated PowerShell session, copy and paste the following command:</span></span>

   ```powershell
   Add-AppxProvisionedPackage –Online –SkipLicense –PackagePath <DownloadPath>\Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe.Appx
   ```

## <span data-ttu-id="6badd-208">Installation de surface App avec MDT</span><span class="sxs-lookup"><span data-stu-id="6badd-208">Install Surface app with MDT</span></span>
<span data-ttu-id="6badd-209">La procédure suivante utilise MDT pour automatiser l’installation de l’application surface au moment du déploiement.</span><span class="sxs-lookup"><span data-stu-id="6badd-209">The following procedure uses MDT to automate installation of the Surface app at the time of deployment.</span></span> <span data-ttu-id="6badd-210">L’application est automatiquement provisionnée par MDT au cours du déploiement. Ainsi, vous pouvez utiliser ce processus avec des images existantes.</span><span class="sxs-lookup"><span data-stu-id="6badd-210">The application is provisioned automatically by MDT during deployment and thus you can use this process with existing images.</span></span> <span data-ttu-id="6badd-211">Il s’agit du processus recommandé pour le déploiement de l’application surface dans le cadre d’un déploiement Windows sur des appareils surface, car elle ne permet pas de réduire la compatibilité entre les plateformes de l’image Windows.</span><span class="sxs-lookup"><span data-stu-id="6badd-211">This is the recommended process to deploy the Surface app as part of a Windows deployment to Surface devices because it does not reduce the cross platform compatibility of the Windows image.</span></span>

1. <span data-ttu-id="6badd-212">À l’aide de la procédure décrite [précédemment dans cet article](#download-surface-app-from-a-microsoft-store-for-business-account), téléchargez l’application surface AppxBundle et le fichier de licence.</span><span class="sxs-lookup"><span data-stu-id="6badd-212">Using the procedure described [earlier in this article](#download-surface-app-from-a-microsoft-store-for-business-account), download the Surface app AppxBundle and license file.</span></span> 

2. <span data-ttu-id="6badd-213">À l’aide de l’Assistant Nouvelle application dans le déploiement de MDT Deployment Workbench, importez les fichiers téléchargés en tant que nouvelle **application avec des fichiers sources**.</span><span class="sxs-lookup"><span data-stu-id="6badd-213">Using the New Application Wizard in the MDT Deployment Workbench, import the downloaded files as a new **Application with source files**.</span></span>

3. <span data-ttu-id="6badd-214">Dans la page Détails de la **commande** de l’Assistant Nouvelle application, spécifiez le **Répertoire de travail** par défaut et pour la **commande** spécifiez le nom du fichier AppxBundle, comme suit:</span><span class="sxs-lookup"><span data-stu-id="6badd-214">On the **Command Details** page of the New Application Wizard, specify the default **Working Directory** and for the **Command** specify the file name of the AppxBundle, as follows:</span></span>

   * <span data-ttu-id="6badd-215">Commande</span><span class="sxs-lookup"><span data-stu-id="6badd-215">Command:</span></span>
   
     ```console
     Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle
     ```
     
   * <span data-ttu-id="6badd-216">Répertoire de travail:%DEPLOYROOT%\Applications\SurfaceApp</span><span class="sxs-lookup"><span data-stu-id="6badd-216">Working Directory: %DEPLOYROOT%\Applications\SurfaceApp</span></span>

<span data-ttu-id="6badd-217">Pour que l’application surface puisse fonctionner sur l’ordinateur cible, elle doit également utiliser les infrastructures décrites précédemment dans cet article.</span><span class="sxs-lookup"><span data-stu-id="6badd-217">For the Surface app to function on the target computer, it will also require the frameworks described earlier in this article.</span></span> <span data-ttu-id="6badd-218">Utilisez la procédure suivante pour importer les infrastructures requises pour l’application surface dans MDT et pour les configurer en tant que dépendances.</span><span class="sxs-lookup"><span data-stu-id="6badd-218">Use the following procedure to import the frameworks required for the Surface app into MDT and to configure them as dependencies.</span></span>

1. <span data-ttu-id="6badd-219">À l’aide de la procédure décrite précédemment dans cet article, téléchargez les fichiers de l’infrastructure.</span><span class="sxs-lookup"><span data-stu-id="6badd-219">Using the procedure described earlier in this article, download the framework files.</span></span> <span data-ttu-id="6badd-220">Stockez chaque infrastructure dans un dossier distinct.</span><span class="sxs-lookup"><span data-stu-id="6badd-220">Store each framework in a separate folder.</span></span>

2. <span data-ttu-id="6badd-221">À l’aide de l’Assistant Nouvelle application dans le déploiement de MDT Deployment Workbench, importez les fichiers téléchargés en tant que nouvelle **application avec des fichiers sources**.</span><span class="sxs-lookup"><span data-stu-id="6badd-221">Using the New Application Wizard in the MDT Deployment Workbench, import the downloaded files as a new **Application with source files**.</span></span>

3. <span data-ttu-id="6badd-222">Dans la page Détails de la **commande** , tapez le nom de fichier de chaque application téléchargée dans le champ de **commande** et le répertoire de travail par défaut.</span><span class="sxs-lookup"><span data-stu-id="6badd-222">On the **Command Details** page, type the file name of each application you downloaded in the **Command** field and the default Working Directory.</span></span>

<span data-ttu-id="6badd-223">Pour configurer les infrastructures en tant que dépendances de l’application de surface, utilisez ce processus:</span><span class="sxs-lookup"><span data-stu-id="6badd-223">To configure the frameworks as dependencies of the Surface app, use this process:</span></span>

1. <span data-ttu-id="6badd-224">Ouvrez les propriétés de l’application surface dans le déploiement de MDT Deployment Workbench.</span><span class="sxs-lookup"><span data-stu-id="6badd-224">Open the properties of the Surface app in the MDT Deployment Workbench.</span></span>

2. <span data-ttu-id="6badd-225">Cliquez sur l’onglet **dépendances** , puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="6badd-225">Click the **Dependencies** tab, and then click **Add**.</span></span>

3. <span data-ttu-id="6badd-226">Activez les cases à cocher correspondant à chaque infrastructure en utilisant le nom que vous avez fourni dans l’Assistant Nouvelle application.</span><span class="sxs-lookup"><span data-stu-id="6badd-226">Select the check box for each framework using the name you provided in the New Application Wizard.</span></span>

<span data-ttu-id="6badd-227">Après l’importation, l’application surface sera disponible pour sélection à l’étape **applications** de l’Assistant Déploiement de Windows.</span><span class="sxs-lookup"><span data-stu-id="6badd-227">After import, the Surface app will be available for selection in the **Applications** step of the Windows Deployment Wizard.</span></span> <span data-ttu-id="6badd-228">Vous pouvez également lancer l’installation automatique de l’application en la spécifiant dans la séquence de tâches de déploiement, via la procédure suivante:</span><span class="sxs-lookup"><span data-stu-id="6badd-228">You can also install the application automatically by specifying the application in the deployment task sequence by following this process:</span></span>

1. <span data-ttu-id="6badd-229">Ouvrez la séquence de tâches de déploiement dans MDTDeploymentWorkbench.</span><span class="sxs-lookup"><span data-stu-id="6badd-229">Open your deployment task sequence in the MDT Deployment Workbench.</span></span>

2. <span data-ttu-id="6badd-230">Ajoutez une nouvelle tâche **Installer l’application** dans la section **Restauration de l’état** du déploiement.</span><span class="sxs-lookup"><span data-stu-id="6badd-230">Add a new **Install Application** task in the **State Restore** section of deployment.</span></span>

3. <span data-ttu-id="6badd-231">Sélectionnez **installer une seule application** et spécifiez l’application **surface** **à**installer.</span><span class="sxs-lookup"><span data-stu-id="6badd-231">Select **Install a single application** and specify the **Surface App** as the **Application to be installed**.</span></span>

<span data-ttu-id="6badd-232">Pour plus d’informations sur l’ajout d’applications dans vos déploiements Windows, consultez [la rubrique déploiement de Windows 10 à l’aide du kit de développement Microsoft Deployment](https://technet.microsoft.com/itpro/windows/deploy/deploy-windows-10-with-the-microsoft-deployment-toolkit).</span><span class="sxs-lookup"><span data-stu-id="6badd-232">For more information about including apps into your Windows deployments, see [Deploy Windows 10 with the Microsoft Deployment Toolkit](https://technet.microsoft.com/itpro/windows/deploy/deploy-windows-10-with-the-microsoft-deployment-toolkit).</span></span>
