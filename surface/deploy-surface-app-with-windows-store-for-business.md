---
title: Déployer une application Surface avec Microsoft Store pour Entreprises ou Microsoft Store pour Éducation (Surface)
description: Découvrez comment ajouter et télécharger l’application Surface avec Microsoft Store pour Entreprises ou Microsoft Store pour Éducation, ainsi que l’installation de l’application Surface avec PowerShell et MDT.
keywords: application surface, application, déploiement, personnaliser
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
ms.date: 1/15/2021
ms.openlocfilehash: 87e24bcfa1e2d4ab05d24a05b203fea92637d3f4
ms.sourcegitcommit: 1b86286bd13b13749ddbf454ae78d9a24fec44ee
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "11271071"
---
# <span data-ttu-id="0b3ee-104">Déployer une application Surface avec Microsoft Store pour Entreprises et Éducation</span><span class="sxs-lookup"><span data-stu-id="0b3ee-104">Deploy Surface app with Microsoft Store for Business and Education</span></span>

**<span data-ttu-id="0b3ee-105">S'applique à</span><span class="sxs-lookup"><span data-stu-id="0b3ee-105">Applies to</span></span>**

- <span data-ttu-id="0b3ee-106">Surface Pro 7+</span><span class="sxs-lookup"><span data-stu-id="0b3ee-106">Surface Pro 7+</span></span>
- <span data-ttu-id="0b3ee-107">Surface Laptop Go</span><span class="sxs-lookup"><span data-stu-id="0b3ee-107">Surface Laptop Go</span></span>
- <span data-ttu-id="0b3ee-108">SurfacePro7</span><span class="sxs-lookup"><span data-stu-id="0b3ee-108">Surface Pro 7</span></span>
- <span data-ttu-id="0b3ee-109">Surface Laptop3</span><span class="sxs-lookup"><span data-stu-id="0b3ee-109">Surface Laptop 3</span></span>
- <span data-ttu-id="0b3ee-110">SurfacePro6</span><span class="sxs-lookup"><span data-stu-id="0b3ee-110">Surface Pro 6</span></span>
- <span data-ttu-id="0b3ee-111">Surface Laptop2</span><span class="sxs-lookup"><span data-stu-id="0b3ee-111">Surface Laptop 2</span></span>
- <span data-ttu-id="0b3ee-112">SurfaceGo</span><span class="sxs-lookup"><span data-stu-id="0b3ee-112">Surface Go</span></span>
- <span data-ttu-id="0b3ee-113">Surface Go avec LTE</span><span class="sxs-lookup"><span data-stu-id="0b3ee-113">Surface Go with LTE</span></span>
- <span data-ttu-id="0b3ee-114">SurfaceBook2</span><span class="sxs-lookup"><span data-stu-id="0b3ee-114">Surface Book 2</span></span>
- <span data-ttu-id="0b3ee-115">SurfacePro avec LTE Advanced (modèle1807)</span><span class="sxs-lookup"><span data-stu-id="0b3ee-115">Surface Pro with LTE Advanced (Model 1807)</span></span>
- <span data-ttu-id="0b3ee-116">SurfacePro (modèle1796)</span><span class="sxs-lookup"><span data-stu-id="0b3ee-116">Surface Pro (Model 1796)</span></span>
- <span data-ttu-id="0b3ee-117">Surface Laptop</span><span class="sxs-lookup"><span data-stu-id="0b3ee-117">Surface Laptop</span></span>
- <span data-ttu-id="0b3ee-118">SurfaceStudio</span><span class="sxs-lookup"><span data-stu-id="0b3ee-118">Surface Studio</span></span>
- <span data-ttu-id="0b3ee-119">Surface Studio2</span><span class="sxs-lookup"><span data-stu-id="0b3ee-119">Surface Studio 2</span></span>
- <span data-ttu-id="0b3ee-120">SurfaceBook</span><span class="sxs-lookup"><span data-stu-id="0b3ee-120">Surface Book</span></span>
- <span data-ttu-id="0b3ee-121">Surface Pro4</span><span class="sxs-lookup"><span data-stu-id="0b3ee-121">Surface Pro 4</span></span>
- <span data-ttu-id="0b3ee-122">VersionsLTE du modèleSurface3</span><span class="sxs-lookup"><span data-stu-id="0b3ee-122">Surface 3 LTE</span></span>
- <span data-ttu-id="0b3ee-123">Surface3</span><span class="sxs-lookup"><span data-stu-id="0b3ee-123">Surface 3</span></span>
- <span data-ttu-id="0b3ee-124">Surface Pro3</span><span class="sxs-lookup"><span data-stu-id="0b3ee-124">Surface Pro 3</span></span>


<span data-ttu-id="0b3ee-125">L’application Surface est une application légère du Microsoft Store qui permet de contrôler de nombreux paramètres et options propres à Surface, notamment :</span><span class="sxs-lookup"><span data-stu-id="0b3ee-125">The Surface app is a lightweight Microsoft Store app that provides control of many Surface-specific settings and options, including:</span></span> 

* <span data-ttu-id="0b3ee-126">Activer ou désactiver le boutonWindows sur l’appareilSurface</span><span class="sxs-lookup"><span data-stu-id="0b3ee-126">Enable or disable the Windows button on the Surface device</span></span> 

* <span data-ttu-id="0b3ee-127">Ajuster la sensibilité du styletSurface</span><span class="sxs-lookup"><span data-stu-id="0b3ee-127">Adjust the sensitivity of a Surface Pen</span></span> 

* <span data-ttu-id="0b3ee-128">Personnaliser les actions des boutons des styletsSurface</span><span class="sxs-lookup"><span data-stu-id="0b3ee-128">Customize Surface Pen button actions</span></span> 

* <span data-ttu-id="0b3ee-129">Activer ou désactiver les améliorations audio de l’appareilSurface</span><span class="sxs-lookup"><span data-stu-id="0b3ee-129">Enable or disable Surface audio enhancements</span></span> 

* <span data-ttu-id="0b3ee-130">Accès rapide à la documentation et aux informations de prise en charge de votre appareil</span><span class="sxs-lookup"><span data-stu-id="0b3ee-130">Quick access to support documentation and information for your device</span></span>

<span data-ttu-id="0b3ee-131">Les clients qui utilisent Windows Update reçoivent généralement l’application Surface dans le cadre des mises à jour automatiques.</span><span class="sxs-lookup"><span data-stu-id="0b3ee-131">Customers using Windows Update will ordinarily receive Surface app as part of automatic updates.</span></span> <span data-ttu-id="0b3ee-132">Toutefois, si votre organisation prépare des images pour le déploiement sur vos appareils Surface, vous pouvez inclure l’application Surface (anciennement appelée Surface Hub) dans votre processus d’imagerie et de déploiement au lieu de demander aux utilisateurs de chaque appareil individuel de télécharger et d’installer l’application à partir du Microsoft Store ou de votre Microsoft Store pour Entreprises.</span><span class="sxs-lookup"><span data-stu-id="0b3ee-132">But if your organization is preparing images for deployment to your Surface devices, you may want to include the Surface app (formerly called the Surface Hub) in your imaging and deployment process instead of requiring users of each individual device to download and install the app from the Microsoft Store or your Microsoft Store for Business.</span></span> 

> [!NOTE]
> <span data-ttu-id="0b3ee-133">Cet article ne s’applique pas à Surface Pro X. Pour plus d’informations, voir [Déploiement, gestion et maintenance de Surface Pro X](surface-pro-arm-app-management.md)</span><span class="sxs-lookup"><span data-stu-id="0b3ee-133">This article does not apply to Surface Pro X. For more information, refer to [Deploying, managing, and servicing Surface Pro X](surface-pro-arm-app-management.md)</span></span>

## <span data-ttu-id="0b3ee-134">Vue d’ensemble de l’application Surface</span><span class="sxs-lookup"><span data-stu-id="0b3ee-134">Surface app overview</span></span>

<span data-ttu-id="0b3ee-135">L’application Surface est disponible en téléchargement gratuit à partir du [Microsoft Store.](https://www.microsoft.com/store/apps/Surface/9WZDNCRFJB8P)</span><span class="sxs-lookup"><span data-stu-id="0b3ee-135">The Surface app is available as a free download from the [Microsoft Store](https://www.microsoft.com/store/apps/Surface/9WZDNCRFJB8P).</span></span> <span data-ttu-id="0b3ee-136">Les utilisateurs peuvent le télécharger et l’installer à partir du Microsoft Store, mais si votre organisation utilise plutôt Microsoft Store pour Entreprises, vous devrez l’ajouter à l’inventaire de votre magasin et éventuellement inclure l’application dans le cadre de votre processus de déploiement de Windows.</span><span class="sxs-lookup"><span data-stu-id="0b3ee-136">Users can download and install it from the Microsoft Store, but if your organization uses Microsoft Store for Business instead, you will need to add it to your store’s inventory and possibly include the app as part of your Windows deployment process.</span></span> <span data-ttu-id="0b3ee-137">Ces processus sont décrits tout au long de cet article.</span><span class="sxs-lookup"><span data-stu-id="0b3ee-137">These processes are discussed throughout this article.</span></span> <span data-ttu-id="0b3ee-138">Pour plus d’informations sur Microsoft Store pour Entreprises, voir [Microsoft Store](https://docs.microsoft.com/microsoft-store/) pour Entreprises dans le TechCenter Windows.</span><span class="sxs-lookup"><span data-stu-id="0b3ee-138">For more information about Microsoft Store for Business, see [Microsoft Store for Business](https://docs.microsoft.com/microsoft-store/) in the Windows TechCenter.</span></span> 

## <span data-ttu-id="0b3ee-139">Ajouter une application Surface à un compte Microsoft Store pour Entreprises</span><span class="sxs-lookup"><span data-stu-id="0b3ee-139">Add Surface app to a Microsoft Store for Business account</span></span> 

<span data-ttu-id="0b3ee-140">Avant que les utilisateurs ne peuvent installer ou déployer une application à partir du compte Microsoft Store pour Entreprises d’une entreprise, les applications souhaitées doivent d’abord être disponibles et sous licence pour les utilisateurs d’une entreprise.</span><span class="sxs-lookup"><span data-stu-id="0b3ee-140">Before users can install or deploy an app from a company’s Microsoft Store for Business account, the desired app(s) must first be made available and licensed to the users of a business.</span></span> 

1. <span data-ttu-id="0b3ee-141">Si ce n’est pas déjà fait, créez un [compte Microsoft Store pour Entreprises.](https://www.microsoft.com/business-store)</span><span class="sxs-lookup"><span data-stu-id="0b3ee-141">If you have not already done so, create a [Microsoft Store for Business account](https://www.microsoft.com/business-store).</span></span> 

2. <span data-ttu-id="0b3ee-142">Connectez-vous au portail.</span><span class="sxs-lookup"><span data-stu-id="0b3ee-142">Log on to the portal.</span></span> 

3. <span data-ttu-id="0b3ee-143">Activez la gestion des licences hors connexion : cliquez sur Gérer **les paramètres du**Windows Store >, puis sélectionnez Afficher les applications sous licence hors connexion pour les achats dans la case à cocher du **Store,** comme le montre la figure 1.</span><span class="sxs-lookup"><span data-stu-id="0b3ee-143">Enable offline licensing: click **Manage->Store settings**, and then select the **Show offline licensed apps to people shopping in the store** checkbox, as shown in Figure 1.</span></span> <span data-ttu-id="0b3ee-144">Pour plus d’informations sur les modèles de licence d’application du Microsoft Store pour Entreprises, voir Applications dans [Microsoft Store pour Entreprises et Éducation.](https://docs.microsoft.com/microsoft-store/)</span><span class="sxs-lookup"><span data-stu-id="0b3ee-144">For more information about Microsoft Store for Business app licensing models, see [Apps in Microsoft Store for Business and Education](https://docs.microsoft.com/microsoft-store/).</span></span>

   > [!div class="mx-imgBorder"]
   > ![Afficher la case à cocher des applications de licences hors connexion](images/deploysurfapp-figure1-enablingapps.png "Show offline licenses apps checkbox")<br/>
   *<span data-ttu-id="0b3ee-146">Figure1.</span><span class="sxs-lookup"><span data-stu-id="0b3ee-146">Figure 1.</span></span> <span data-ttu-id="0b3ee-147">Activer les applications pour une utilisation hors connexion</span><span class="sxs-lookup"><span data-stu-id="0b3ee-147">Enable apps for offline use</span></span>*

4. <span data-ttu-id="0b3ee-148">Ajoutez l’application Surface à votre compte Microsoft Store pour Entreprises en suivant cette procédure :</span><span class="sxs-lookup"><span data-stu-id="0b3ee-148">Add Surface app to your Microsoft Store for Business account by following this procedure:</span></span>

    * <span data-ttu-id="0b3ee-149">Cliquez sur le menu **Magasin.**</span><span class="sxs-lookup"><span data-stu-id="0b3ee-149">Click the **Shop** menu.</span></span>
    
    * <span data-ttu-id="0b3ee-150">Dans la zone de recherche, tapez **Application Surface,** puis cliquez sur l’icône de recherche.</span><span class="sxs-lookup"><span data-stu-id="0b3ee-150">In the search box, type **Surface app**, and then click the search icon.</span></span>
    
    * <span data-ttu-id="0b3ee-151">Une fois l’application Surface présentée dans les résultats de la recherche, cliquez sur l’icône de l’application.</span><span class="sxs-lookup"><span data-stu-id="0b3ee-151">After the Surface app is presented in the search results, click the app’s icon.</span></span>
    
    * <span data-ttu-id="0b3ee-152">Un choix s’affiche (sélectionnez **En ligne** ou Hors **connexion),** comme le montre la figure 2.</span><span class="sxs-lookup"><span data-stu-id="0b3ee-152">You are presented with a choice (select **Online** or **Offline**), as shown in Figure 2.</span></span>
    
      > [!div class="mx-imgBorder"]
      > ![Sélectionnez le mode de licence hors connexion et ajoutez l’application à votre inventaire](images/deploysurfapp-fig2-selectingofflinelicense.png "Select the Offline licensing mode and add the app to your inventory")   
      *<span data-ttu-id="0b3ee-154">Figure2.</span><span class="sxs-lookup"><span data-stu-id="0b3ee-154">Figure 2.</span></span> <span data-ttu-id="0b3ee-155">Sélectionnez le mode de licence hors connexion et ajoutez l’application à votre inventaire</span><span class="sxs-lookup"><span data-stu-id="0b3ee-155">Select the Offline licensing mode and add the app to your inventory</span></span>*
    
    * <span data-ttu-id="0b3ee-156">Cliquez **sur Hors connexion** pour sélectionner le mode de licence hors connexion.</span><span class="sxs-lookup"><span data-stu-id="0b3ee-156">Click **Offline** to select the Offline licensing mode.</span></span>
    
    * <span data-ttu-id="0b3ee-157">Cliquez **sur Obtenir l’application** pour l’ajouter à votre inventaire du Microsoft Store pour Entreprises.</span><span class="sxs-lookup"><span data-stu-id="0b3ee-157">Click **Get the app** to add the app to your Microsoft Store for Business inventory.</span></span> <span data-ttu-id="0b3ee-158">Comme le montre la figure 3, une boîte de dialogue vous invite à reconnaître que les applications hors connexion peuvent être déployées à l’aide d’un outil de gestion ou téléchargées à partir de la page d’inventaire de l’entreprise dans leur magasin privé.</span><span class="sxs-lookup"><span data-stu-id="0b3ee-158">As shown in Figure 3, you’ll see a dialog box that prompts you to acknowledge that offline apps can be deployed using a management tool or downloaded from the company’s inventory page in their private store.</span></span>
    
      > [!div class="mx-imgBorder"]
      > ![<span data-ttu-id="0b3ee-159">Fenêtre d’accusé de réception d’application avec licence hors connexion ](images/deploysurfapp-fig3-acknowledge.png "Offline-licensed app acknowledgement window")
       *Figure 3. Accusé de réception d’application avec licence hors connexion*</span><span class="sxs-lookup"><span data-stu-id="0b3ee-159">Offline-licensed app acknowledgement window](images/deploysurfapp-fig3-acknowledge.png "Offline-licensed app acknowledgement window")
*Figure 3. Offline-licensed app acknowledgement*</span></span>
      
    * <span data-ttu-id="0b3ee-160">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="0b3ee-160">Click **OK**.</span></span>

## <span data-ttu-id="0b3ee-161">Télécharger l’application Surface à partir d’un compte Microsoft Store pour Entreprises</span><span class="sxs-lookup"><span data-stu-id="0b3ee-161">Download Surface app from a Microsoft Store for Business account</span></span>
<span data-ttu-id="0b3ee-162">Après avoir ajouté une application au compte Microsoft Store pour Entreprises en mode hors connexion, vous pouvez télécharger et ajouter l’application en tant qu’AppxBundle à un partage de déploiement.</span><span class="sxs-lookup"><span data-stu-id="0b3ee-162">After you add an app to the Microsoft Store for Business account in Offline mode, you can download and add the app as an AppxBundle to a deployment share.</span></span>

1. <span data-ttu-id="0b3ee-163">Connectez-vous au compte Microsoft Store pour Entreprises à l’aide de https://businessstore.microsoft.com .</span><span class="sxs-lookup"><span data-stu-id="0b3ee-163">Log on to the Microsoft Store for Business account at https://businessstore.microsoft.com.</span></span>

2. <span data-ttu-id="0b3ee-164">Cliquez **sur Gérer les >applications & logiciel.**</span><span class="sxs-lookup"><span data-stu-id="0b3ee-164">Click **Manage->Apps & software**.</span></span> <span data-ttu-id="0b3ee-165">Une liste de toutes les applications de votre entreprise s’affiche, y compris l’application Surface que vous avez ajoutée dans la section Ajouter une application Surface à un compte [Microsoft Store](#add-surface-app-to-a-microsoft-store-for-business-account) pour Entreprises de cet article.</span><span class="sxs-lookup"><span data-stu-id="0b3ee-165">A list of all of your company’s apps is displayed, including the Surface app you added in the [Add Surface app to a Microsoft Store for Business account](#add-surface-app-to-a-microsoft-store-for-business-account) section of this article.</span></span>

3. <span data-ttu-id="0b3ee-166">Sous **Actions,** cliquez sur les ellipses (**...**), puis cliquez sur **Télécharger** pour une utilisation hors connexion pour l’application Surface.</span><span class="sxs-lookup"><span data-stu-id="0b3ee-166">Under **Actions**, click the ellipsis (**…**), and then click **Download for offline use** for the Surface app.</span></span>

4. <span data-ttu-id="0b3ee-167">Sélectionnez les options **de** plateforme et **d’architecture** souhaitées parmi les sélections disponibles pour l’application sélectionnée, comme le montre la figure 4.</span><span class="sxs-lookup"><span data-stu-id="0b3ee-167">Select the desired **Platform** and **Architecture** options from the available selections for the selected app, as shown in Figure 4.</span></span>

    > [!div class="mx-imgBorder"]
    > ![Exemple de package AppxBundle](images/deploysurfapp-fig4-downloadappxbundle.png "Example of the AppxBundle package")<br/>
    *<span data-ttu-id="0b3ee-169">Figure4.</span><span class="sxs-lookup"><span data-stu-id="0b3ee-169">Figure 4.</span></span> <span data-ttu-id="0b3ee-170">Télécharger le package AppxBundle pour une application</span><span class="sxs-lookup"><span data-stu-id="0b3ee-170">Download the AppxBundle package for an app</span></span>*
    
5. <span data-ttu-id="0b3ee-171">Cliquez **sur Télécharger.**</span><span class="sxs-lookup"><span data-stu-id="0b3ee-171">Click **Download**.</span></span> <span data-ttu-id="0b3ee-172">Le package AppxBundle sera téléchargé.</span><span class="sxs-lookup"><span data-stu-id="0b3ee-172">The AppxBundle package will be downloaded.</span></span> <span data-ttu-id="0b3ee-173">Assurez-vous de noter le chemin d’accès du fichier téléchargé, car vous en aurez besoin plus loin dans cet article.</span><span class="sxs-lookup"><span data-stu-id="0b3ee-173">Make sure you note the path of the downloaded file because you’ll need that later in this article.</span></span>

6. <span data-ttu-id="0b3ee-174">Cliquez sur **l’option** de licence codée ou non **codée.**</span><span class="sxs-lookup"><span data-stu-id="0b3ee-174">Click either the **Encoded license** or **Unencoded license** option.</span></span> <span data-ttu-id="0b3ee-175">Utilisez l’option de licence codée avec des outils de gestion tels que Microsoft Endpoint Configuration Manager ou lorsque vous utilisez le Concepteur de configuration Windows pour créer un package d’approvisionnement.</span><span class="sxs-lookup"><span data-stu-id="0b3ee-175">Use the Encoded license option with management tools like Microsoft Endpoint Configuration Manager or when you use Windows Configuration Designer to create a provisioning package.</span></span> <span data-ttu-id="0b3ee-176">Sélectionnez l’option de licence non codée lorsque vous utilisez la gestion et la maintenance des images de déploiement (DISM) ou des solutions de déploiement basées sur l’imagerie, y compris microsoft Deployment Shared Computer Toolkit (MDT).</span><span class="sxs-lookup"><span data-stu-id="0b3ee-176">Select the Unencoded license option when you use Deployment Image Servicing and Management (DISM) or deployment solutions based on imaging, including the Microsoft Deployment Toolkit (MDT).</span></span>

7. <span data-ttu-id="0b3ee-177">Cliquez **sur Générer** pour générer et télécharger la licence de l’application.</span><span class="sxs-lookup"><span data-stu-id="0b3ee-177">Click **Generate** to generate and download the license for the app.</span></span> <span data-ttu-id="0b3ee-178">Assurez-vous de noter le chemin d’accès du fichier de licence, car vous en aurez besoin plus loin dans cet article.</span><span class="sxs-lookup"><span data-stu-id="0b3ee-178">Make sure you note the path of the license file because you’ll need that later in this article.</span></span>

>[!NOTE]
><span data-ttu-id="0b3ee-179">Lorsque vous téléchargez une application pour une utilisation hors connexion, telle que l’application Surface, vous remarquerez peut-être une section en bas de la page libellée **Infrastructure requise.**</span><span class="sxs-lookup"><span data-stu-id="0b3ee-179">When you download an app for offline use, such as the Surface app, you may notice a section at the bottom of the page labeled **Required frameworks**.</span></span> <span data-ttu-id="0b3ee-180">Les infrastructure de vos ordinateurs cibles doivent être installées pour que l’application s’exécute, vous devrez peut-être répéter le processus de téléchargement pour chacune des infrastructure requises pour votre architecture (x86 ou x64) et les inclure également dans le cadre de votre déploiement Windows décrit plus loin dans cet article.</span><span class="sxs-lookup"><span data-stu-id="0b3ee-180">Your target computers must have the frameworks installed for the app to run, so you may need to repeat the download process for each of the required frameworks for your architecture (either x86 or x64) and also include them as part of your Windows deployment discussed later in this article.</span></span>

<span data-ttu-id="0b3ee-181">La figure 5 illustre les frameworks requis pour l’application Surface.</span><span class="sxs-lookup"><span data-stu-id="0b3ee-181">Figure 5 shows the required frameworks for the Surface app.</span></span>

> [!div class="mx-imgBorder"]
> ![Infrastructure requise pour l’application Surface](images/deploysurfapp-fig5-requiredframework.png "Required frameworks for the Surface app")<br/>
*<span data-ttu-id="0b3ee-183">Figure5.</span><span class="sxs-lookup"><span data-stu-id="0b3ee-183">Figure 5.</span></span> <span data-ttu-id="0b3ee-184">Infrastructure requise pour l’application Surface</span><span class="sxs-lookup"><span data-stu-id="0b3ee-184">Required frameworks for the Surface app</span></span>*

>[!NOTE]
><span data-ttu-id="0b3ee-185">Les numéros de version de l’application Surface et les frameworks requis changent au cours de la mise à jour des applications.</span><span class="sxs-lookup"><span data-stu-id="0b3ee-185">The version numbers of the Surface app and required frameworks will change as the apps are updated.</span></span> <span data-ttu-id="0b3ee-186">Recherchez la dernière version de l’application Surface et chaque infrastructure du Microsoft Store pour Entreprises.</span><span class="sxs-lookup"><span data-stu-id="0b3ee-186">Check for the latest version of Surface app and each framework in Microsoft Store for Business.</span></span> <span data-ttu-id="0b3ee-187">Utilisez toujours l’application Surface et les versions d’infrastructure recommandées telles que fournies par le Microsoft Store pour Entreprises.</span><span class="sxs-lookup"><span data-stu-id="0b3ee-187">Always use the Surface app and recommended framework versions as provided by Microsoft Store for Business.</span></span> <span data-ttu-id="0b3ee-188">L’utilisation d’infrastructure obsolètes ou de versions incorrectes peut entraîner des erreurs ou des pannes d’application.</span><span class="sxs-lookup"><span data-stu-id="0b3ee-188">Using outdated frameworks or the incorrect versions may result in errors or application crashes.</span></span>

<span data-ttu-id="0b3ee-189">Pour télécharger les frameworks requis pour l’application Surface, suivez les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="0b3ee-189">To download the required frameworks for the Surface app, follow these steps:</span></span>

1. <span data-ttu-id="0b3ee-190">Cliquez sur **le** bouton Télécharger **sous Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe**.</span><span class="sxs-lookup"><span data-stu-id="0b3ee-190">Click the **Download** button under **Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe**.</span></span> <span data-ttu-id="0b3ee-191">Cette application télécharge Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe. Fichier Appx dans le dossier spécifié.</span><span class="sxs-lookup"><span data-stu-id="0b3ee-191">This downloads the Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe.Appx file to your specified folder.</span></span>

2. <span data-ttu-id="0b3ee-192">Cliquez sur **le** bouton Télécharger **sous Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe**.</span><span class="sxs-lookup"><span data-stu-id="0b3ee-192">Click the **Download** button under **Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe**.</span></span> <span data-ttu-id="0b3ee-193">Cela télécharge le fichier Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe.Appx dans votre dossier spécifié.</span><span class="sxs-lookup"><span data-stu-id="0b3ee-193">This downloads the Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe.Appx file to your specified folder.</span></span>

>[!NOTE]
><span data-ttu-id="0b3ee-194">Seule la version 64 bits (x64) de chaque infrastructure est requise pour les appareils Surface.</span><span class="sxs-lookup"><span data-stu-id="0b3ee-194">Only the 64-bit (x64) version of each framework is required for Surface devices.</span></span> <span data-ttu-id="0b3ee-195">Les appareils Surface sont des appareils UEFI 64 bits natifs et ne sont pas compatibles avec les versions 32 bits (x86) de Windows qui nécessitent des infrastructure 32 bits.</span><span class="sxs-lookup"><span data-stu-id="0b3ee-195">Surface devices are native 64-bit UEFI devices and are not compatible with 32-bit (x86) versions of Windows that would require 32-bit frameworks.</span></span> 

## <span data-ttu-id="0b3ee-196">Installer l’application Surface sur votre ordinateur avec PowerShell</span><span class="sxs-lookup"><span data-stu-id="0b3ee-196">Install Surface app on your computer with PowerShell</span></span>
<span data-ttu-id="0b3ee-197">La procédure suivante met en place l’application Surface sur votre ordinateur et la met à disposition pour tous les comptes d’utilisateur créés sur l’ordinateur par la suite.</span><span class="sxs-lookup"><span data-stu-id="0b3ee-197">The following procedure provisions the Surface app onto your computer and makes it available for any user accounts created on the computer afterwards.</span></span>

1. <span data-ttu-id="0b3ee-198">À l’aide de la procédure décrite dans la section Comment télécharger l’application Surface à partir d’un compte [Microsoft Store](#download-surface-app-from-a-microsoft-store-for-business-account) pour Entreprises de cet article, téléchargez le fichier de licence et AppxBundle de l’application Surface.</span><span class="sxs-lookup"><span data-stu-id="0b3ee-198">Using the procedure described in the [How to download Surface app from a Microsoft Store for Business account](#download-surface-app-from-a-microsoft-store-for-business-account) section of this article, download the Surface app AppxBundle and license file.</span></span> 

2. <span data-ttu-id="0b3ee-199">Lancez une sessionPowerShell avec élévation des privilèges.</span><span class="sxs-lookup"><span data-stu-id="0b3ee-199">Begin an elevated PowerShell session.</span></span>

    >[!NOTE]
    ><span data-ttu-id="0b3ee-200">Si vous n’exécutez pas PowerShell en tant qu’administrateur, la session ne sera pas autorisée à installer l’application.</span><span class="sxs-lookup"><span data-stu-id="0b3ee-200">If you don’t run PowerShell as an Administrator, the session won’t have the required permissions to install the app.</span></span>
    
3. <span data-ttu-id="0b3ee-201">Dans la sessionPowerShell avec élévation de privilèges, copiez et collez la commande suivante:</span><span class="sxs-lookup"><span data-stu-id="0b3ee-201">In the elevated PowerShell session, copy and paste the following command:</span></span>

    ```powershell
    Add-AppxProvisionedPackage –Online –PackagePath <DownloadPath>\ Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle –LicensePath <DownloadPath>\ Microsoft.SurfaceHub_8wekyb3d8bbwe_a53ef8ab-9dbd-dec1-46c5-7b664d4dd003.xml
    ```

    <span data-ttu-id="0b3ee-202">Où se trouve le dossier dans lequel vous avez téléchargé le fichier appxBundle et le fichier de licence à partir `<DownloadPath>` du compte Microsoft Store pour Entreprises.</span><span class="sxs-lookup"><span data-stu-id="0b3ee-202">Where `<DownloadPath>` is the folder where you downloaded the AppxBundle and license file from the Microsoft Store for Business account.</span></span>

    <span data-ttu-id="0b3ee-203">Par exemple, si vous avez téléchargé les fichiers dans c:\Temp, la commande que vous exécutez est :</span><span class="sxs-lookup"><span data-stu-id="0b3ee-203">For example, if you downloaded the files to c:\Temp, the command you run is:</span></span>
    
    ```powershell
    Add-AppxProvisionedPackage –Online –PackagePath c:\Temp\ Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle –LicensePath c:\Temp\ Microsoft.SurfaceHub_8wekyb3d8bbwe_a53ef8ab-9dbd-dec1-46c5-7b664d4dd003.xml
    ```

4. <span data-ttu-id="0b3ee-204">L’applicationSurface est désormais disponible sur votre ordinateurWindows actuel.</span><span class="sxs-lookup"><span data-stu-id="0b3ee-204">The Surface app will now be available on your current Windows computer.</span></span> 

   <span data-ttu-id="0b3ee-205">Avant que l’application Surface soit fonctionnelle sur l’ordinateur sur lequel elle a été mise en service, vous devez également mettre en service les infrastructure décrites plus tôt dans cet article.</span><span class="sxs-lookup"><span data-stu-id="0b3ee-205">Before the Surface app is functional on the computer where it has been provisioned, you must also provision the frameworks described earlier in this article.</span></span> <span data-ttu-id="0b3ee-206">Pour mettre en service ces infrastructure, utilisez la procédure suivante dans la session PowerShell avec élévation de niveaux que vous avez utilisée pour mettre en service l’application Surface.</span><span class="sxs-lookup"><span data-stu-id="0b3ee-206">To provision these frameworks, use the following procedure in the elevated PowerShell session you used to provision the Surface app.</span></span>

5. <span data-ttu-id="0b3ee-207">Dans la sessionPowerShell avec élévation de privilèges, copiez et collez la commande suivante:</span><span class="sxs-lookup"><span data-stu-id="0b3ee-207">In the elevated PowerShell session, copy and paste the following command:</span></span>

   ```powershell
   Add-AppxProvisionedPackage –Online –SkipLicense –PackagePath <DownloadPath>\Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe.Appx
   ```
   
6. <span data-ttu-id="0b3ee-208">Dans la sessionPowerShell avec élévation de privilèges, copiez et collez la commande suivante:</span><span class="sxs-lookup"><span data-stu-id="0b3ee-208">In the elevated PowerShell session, copy and paste the following command:</span></span>

   ```powershell
   Add-AppxProvisionedPackage –Online –SkipLicense –PackagePath <DownloadPath>\Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe.Appx
   ```

## <span data-ttu-id="0b3ee-209">Installer l’application Surface avec MDT</span><span class="sxs-lookup"><span data-stu-id="0b3ee-209">Install Surface app with MDT</span></span>
<span data-ttu-id="0b3ee-210">La procédure suivante utilise MDT pour automatiser l’installation de l’application Surface au moment du déploiement.</span><span class="sxs-lookup"><span data-stu-id="0b3ee-210">The following procedure uses MDT to automate installation of the Surface app at the time of deployment.</span></span> <span data-ttu-id="0b3ee-211">L’application est automatiquement provisionnée par MDT au cours du déploiement. Ainsi, vous pouvez utiliser ce processus avec des images existantes.</span><span class="sxs-lookup"><span data-stu-id="0b3ee-211">The application is provisioned automatically by MDT during deployment and thus you can use this process with existing images.</span></span> <span data-ttu-id="0b3ee-212">Il s’agit du processus recommandé pour déployer l’application Surface dans le cadre d’un déploiement Windows sur des appareils Surface, car il ne réduit pas la compatibilité entre les plateformes de l’image Windows.</span><span class="sxs-lookup"><span data-stu-id="0b3ee-212">This is the recommended process to deploy the Surface app as part of a Windows deployment to Surface devices because it does not reduce the cross platform compatibility of the Windows image.</span></span>

1. <span data-ttu-id="0b3ee-213">À l’aide de la procédure [décrite plus tôt dans cet article,](#download-surface-app-from-a-microsoft-store-for-business-account)téléchargez le fichier de licence et appxBundle de l’application Surface.</span><span class="sxs-lookup"><span data-stu-id="0b3ee-213">Using the procedure described [earlier in this article](#download-surface-app-from-a-microsoft-store-for-business-account), download the Surface app AppxBundle and license file.</span></span> 

2. <span data-ttu-id="0b3ee-214">À l’aide de l’Assistant Nouvelle application dans MDT Deployment Workbench, importez les fichiers téléchargés en tant que nouvelle **application avec des fichiers sources.**</span><span class="sxs-lookup"><span data-stu-id="0b3ee-214">Using the New Application Wizard in the MDT Deployment Workbench, import the downloaded files as a new **Application with source files**.</span></span>

3. <span data-ttu-id="0b3ee-215">Dans la page **Détails** de la commande \*\*\*\* de l’Assistant \*\*\*\* Nouvelle application, spécifiez le répertoire de travail par défaut et, pour la commande, spécifiez le nom de fichier appxBundle, comme suit :</span><span class="sxs-lookup"><span data-stu-id="0b3ee-215">On the **Command Details** page of the New Application Wizard, specify the default **Working Directory** and for the **Command** specify the file name of the AppxBundle, as follows:</span></span>

   * <span data-ttu-id="0b3ee-216">Commande :</span><span class="sxs-lookup"><span data-stu-id="0b3ee-216">Command:</span></span>
   
     ```console
     Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle
     ```
     
   * <span data-ttu-id="0b3ee-217">Répertoire de travail : %DEPLOYROOT%\Applications\SurfaceApp</span><span class="sxs-lookup"><span data-stu-id="0b3ee-217">Working Directory: %DEPLOYROOT%\Applications\SurfaceApp</span></span>

<span data-ttu-id="0b3ee-218">Pour que l’application Surface fonctionne sur l’ordinateur cible, elle nécessite également les frameworks décrits plus tôt dans cet article.</span><span class="sxs-lookup"><span data-stu-id="0b3ee-218">For the Surface app to function on the target computer, it will also require the frameworks described earlier in this article.</span></span> <span data-ttu-id="0b3ee-219">Utilisez la procédure suivante pour importer les frameworks requis pour l’application Surface dans MDT et les configurer en tant que dépendances.</span><span class="sxs-lookup"><span data-stu-id="0b3ee-219">Use the following procedure to import the frameworks required for the Surface app into MDT and to configure them as dependencies.</span></span>

1. <span data-ttu-id="0b3ee-220">À l’aide de la procédure décrite plus tôt dans cet article, téléchargez les fichiers d’infrastructure.</span><span class="sxs-lookup"><span data-stu-id="0b3ee-220">Using the procedure described earlier in this article, download the framework files.</span></span> <span data-ttu-id="0b3ee-221">Stockez chaque infrastructure dans un dossier distinct.</span><span class="sxs-lookup"><span data-stu-id="0b3ee-221">Store each framework in a separate folder.</span></span>

2. <span data-ttu-id="0b3ee-222">À l’aide de l’Assistant Nouvelle application dans MDT Deployment Workbench, importez les fichiers téléchargés en tant que nouvelle **application avec des fichiers sources.**</span><span class="sxs-lookup"><span data-stu-id="0b3ee-222">Using the New Application Wizard in the MDT Deployment Workbench, import the downloaded files as a new **Application with source files**.</span></span>

3. <span data-ttu-id="0b3ee-223">Dans la page **Détails de la** commande, tapez \*\*\*\* le nom de fichier de chaque application que vous avez téléchargée dans le champ Commande et le répertoire de travail par défaut.</span><span class="sxs-lookup"><span data-stu-id="0b3ee-223">On the **Command Details** page, type the file name of each application you downloaded in the **Command** field and the default Working Directory.</span></span>

<span data-ttu-id="0b3ee-224">Pour configurer les frameworks en tant que dépendances de l’application Surface, utilisez ce processus :</span><span class="sxs-lookup"><span data-stu-id="0b3ee-224">To configure the frameworks as dependencies of the Surface app, use this process:</span></span>

1. <span data-ttu-id="0b3ee-225">Ouvrez les propriétés de l’application Surface dans MDT Deployment Workbench.</span><span class="sxs-lookup"><span data-stu-id="0b3ee-225">Open the properties of the Surface app in the MDT Deployment Workbench.</span></span>

2. <span data-ttu-id="0b3ee-226">Cliquez sur **l’onglet Dépendances,** puis cliquez sur **Ajouter.**</span><span class="sxs-lookup"><span data-stu-id="0b3ee-226">Click the **Dependencies** tab, and then click **Add**.</span></span>

3. <span data-ttu-id="0b3ee-227">Cochez la case pour chaque infrastructure à l’aide du nom que vous avez fourni dans l’Assistant Nouvelle application.</span><span class="sxs-lookup"><span data-stu-id="0b3ee-227">Select the check box for each framework using the name you provided in the New Application Wizard.</span></span>

<span data-ttu-id="0b3ee-228">Après l’importation, l’application Surface sera disponible pour sélection à l’étape **Applications** de l’Assistant Déploiement de Windows.</span><span class="sxs-lookup"><span data-stu-id="0b3ee-228">After import, the Surface app will be available for selection in the **Applications** step of the Windows Deployment Wizard.</span></span> <span data-ttu-id="0b3ee-229">Vous pouvez également lancer l’installation automatique de l’application en la spécifiant dans la séquence de tâches de déploiement, via la procédure suivante:</span><span class="sxs-lookup"><span data-stu-id="0b3ee-229">You can also install the application automatically by specifying the application in the deployment task sequence by following this process:</span></span>

1. <span data-ttu-id="0b3ee-230">Ouvrez la séquence de tâches de déploiement dans MDTDeploymentWorkbench.</span><span class="sxs-lookup"><span data-stu-id="0b3ee-230">Open your deployment task sequence in the MDT Deployment Workbench.</span></span>

2. <span data-ttu-id="0b3ee-231">Ajoutez une nouvelle tâche **Installer l’application** dans la section **Restauration de l’état** du déploiement.</span><span class="sxs-lookup"><span data-stu-id="0b3ee-231">Add a new **Install Application** task in the **State Restore** section of deployment.</span></span>

3. <span data-ttu-id="0b3ee-232">Sélectionnez **Installer une application unique** et spécifiez **l’application Surface en** tant qu’application à **installer.**</span><span class="sxs-lookup"><span data-stu-id="0b3ee-232">Select **Install a single application** and specify the **Surface App** as the **Application to be installed**.</span></span>

<span data-ttu-id="0b3ee-233">Pour plus d’informations sur l’utilisation d’applications dans vos déploiements Windows, voir [Déployer Windows 10 avec](https://technet.microsoft.com/itpro/windows/deploy/deploy-windows-10-with-the-microsoft-deployment-toolkit)microsoft Deployment Shared Computer Toolkit .</span><span class="sxs-lookup"><span data-stu-id="0b3ee-233">For more information about including apps into your Windows deployments, see [Deploy Windows 10 with the Microsoft Deployment Toolkit](https://technet.microsoft.com/itpro/windows/deploy/deploy-windows-10-with-the-microsoft-deployment-toolkit).</span></span>
