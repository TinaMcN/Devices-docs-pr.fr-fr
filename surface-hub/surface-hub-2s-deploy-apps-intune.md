---
title: Déploiement d’applications sur SurfaceHub2S à l’aide d’Intune
description: Découvrez comment déployer des applications sur surface Hub 2 à l’aide de Intune.
keywords: séparer les valeurs par des virgules
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 06/20/2019
ms.localizationpriority: Medium
ms.openlocfilehash: 51e54a5b2881519f2fc361675253c9e50bad0864
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10833282"
---
# <span data-ttu-id="2164a-104">Déploiement d’applications sur SurfaceHub2S à l’aide d’Intune</span><span class="sxs-lookup"><span data-stu-id="2164a-104">Deploy apps to Surface Hub 2S using Intune</span></span>

<span data-ttu-id="2164a-105">Vous pouvez installer des applications supplémentaires pour répondre aux besoins de votre équipe ou de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="2164a-105">You can install additional apps to fit your team or organization's needs.</span></span>

## <span data-ttu-id="2164a-106">Recommandations en matière de développement</span><span class="sxs-lookup"><span data-stu-id="2164a-106">Developer guidelines</span></span>

- <span data-ttu-id="2164a-107">Le SurfaceHub exécute uniquement des [applications de plateforme Windows universelle (UWP)](https://msdn.microsoft.com/windows/uwp/get-started/whats-a-uwp).</span><span class="sxs-lookup"><span data-stu-id="2164a-107">Surface Hub only runs [Universal Windows Platform (UWP) apps](https://msdn.microsoft.com/windows/uwp/get-started/whats-a-uwp).</span></span> <span data-ttu-id="2164a-108">Les applications créées à l’aide de [Desktop App Converter](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-run-desktop-app-converter) ne s’exécuteront pas sur le Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="2164a-108">Apps created using the [Desktop App Converter](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-run-desktop-app-converter) will not run on Surface Hub.</span></span>
- <span data-ttu-id="2164a-109">Les applications doivent être ciblées pour la [famille d’appareils universels](https://msdn.microsoft.com/library/windows/apps/dn894631) ou la famille d'appareils Windows.</span><span class="sxs-lookup"><span data-stu-id="2164a-109">Apps must be targeted for the [Universal device family](https://msdn.microsoft.com/library/windows/apps/dn894631) or Windows Team device family.</span></span>
- <span data-ttu-id="2164a-110">Surface Hub ne prend en charge que les [applications sous licence hors connexion](https://docs.microsoft.com/microsoft-store/distribute-offline-apps) de la [Boutique Microsoft pour les entreprises](https://businessstore.microsoft.com/store).</span><span class="sxs-lookup"><span data-stu-id="2164a-110">Surface Hub only supports [offline-licensed apps](https://docs.microsoft.com/microsoft-store/distribute-offline-apps) from [Microsoft Store for Business](https://businessstore.microsoft.com/store).</span></span>
- <span data-ttu-id="2164a-111">Par défaut, les applications doivent être signées par le WindowsStore pour être installées.</span><span class="sxs-lookup"><span data-stu-id="2164a-111">By default, apps must be Store-signed to be installed.</span></span> <span data-ttu-id="2164a-112">Au cours des phases de test et de développement, vous pouvez également choisir d’exécuter des applicationsUWP signées par le développeur en plaçant l’appareil en mode développeur.</span><span class="sxs-lookup"><span data-stu-id="2164a-112">During testing and development, you can also choose to run developer-signed UWP apps by placing the device in developer mode.</span></span>
- <span data-ttu-id="2164a-113">Lorsque vous développez et soumettez des applications sur le Microsoft Store, définissez les options disponibilité de la famille d’appareils et gestion des licences pour vérifier que les applications sont disponibles pour s’exécuter sur surface Hub.</span><span class="sxs-lookup"><span data-stu-id="2164a-113">When developing and submitting apps to the Microsoft Store, set Device family availability and Organizational licensing options to ensure that apps are available to run on Surface Hub.</span></span>
- <span data-ttu-id="2164a-114">Vous avez besoin d’informations d’identification d’administrateur pour installer des applications sur un appareil surface Hub.</span><span class="sxs-lookup"><span data-stu-id="2164a-114">You need admin credentials to install apps on Surface Hub.</span></span> <span data-ttu-id="2164a-115">Conçu pour une utilisation dans des salles de réunion et d’autres espaces partagés, surface Hub empêche les utilisateurs normaux d’accéder au Microsoft Store pour télécharger et installer des applications.</span><span class="sxs-lookup"><span data-stu-id="2164a-115">Designed for use in meeting rooms and other shared spaces, Surface Hub prevents regular users from accessing the Microsoft Store to download and install apps.</span></span>

## <span data-ttu-id="2164a-116">Recommandations en matière de déploiement</span><span class="sxs-lookup"><span data-stu-id="2164a-116">Deployment guidelines</span></span>

<span data-ttu-id="2164a-117">Vous pouvez déployer des applications de plateforme Windows universelle (UWP) sur surface Hub 2 à l’aide de Intune, ce qui facilite le déploiement d’applications sur les appareils.</span><span class="sxs-lookup"><span data-stu-id="2164a-117">You can deploy Universal Windows Platform (UWP) apps to Surface Hub 2S using Intune, easing app deployment to devices.</span></span>

1. <span data-ttu-id="2164a-118">Pour déployer des applications, activez le GPM pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="2164a-118">To deploy apps, enable MDM for your organization.</span></span> <span data-ttu-id="2164a-119">Dans le portail Intune, sélectionnez **Intune** en tant qu’autorité GPM (recommandé).</span><span class="sxs-lookup"><span data-stu-id="2164a-119">In the Intune portal, select **Intune** as your MDM Authority (recommended).</span></span> <br>

    ![Choix de l’autorité GPM](images/sh2-set-intune5.png)

2. <span data-ttu-id="2164a-121">Activez le Microsoft Store pour les entreprises dans Intune.</span><span class="sxs-lookup"><span data-stu-id="2164a-121">Enable the Microsoft Store for Business in Intune.</span></span> <span data-ttu-id="2164a-122">Ouvrez Intune et sélectionnez **applications clientes**  >  **Microsoft Store pour les entreprises.**</span><span class="sxs-lookup"><span data-stu-id="2164a-122">Open Intune, select **Client apps** > **Microsoft Store for Business.**</span></span> <br>

    ![Activer le Windows Store pour les entreprises](images/sh2-deploy-apps-sync.png)

3. <span data-ttu-id="2164a-124">Dans Intune, ouvrez le **Microsoft Store pour les entreprises** et sélectionnez **paramètres**  >  **distribuer**les  >  **outils de gestion**.</span><span class="sxs-lookup"><span data-stu-id="2164a-124">In Intune open **Microsoft Store for Business** and select **Settings** > **Distribute** > **Management tools**.</span></span> <span data-ttu-id="2164a-125">Choisissez **Microsoft Intune** comme outil de gestion.</span><span class="sxs-lookup"><span data-stu-id="2164a-125">Choose **Microsoft Intune** as your management tool.</span></span> <br>

    ![Ajouter Intune comme outil de gestion](images/sh2-set-intune8.png)

4. <span data-ttu-id="2164a-127">Dans la boutique Microsoft pour les entreprises, sélectionnez **paramètres**de la  >  **Boutique**  >  **Shopping Experience**, puis sélectionnez **afficher les applications hors connexion**.</span><span class="sxs-lookup"><span data-stu-id="2164a-127">In Microsoft Store for Business, select **Settings** > **Shop** > **Shopping Experience**, and then select **Show offline apps**.</span></span> <span data-ttu-id="2164a-128">Les applications hors connexion font référence aux applications qui peuvent être synchronisées avec Intune et centralisées sur un appareil.</span><span class="sxs-lookup"><span data-stu-id="2164a-128">Offline apps refer to apps that can be synced to Intune and centrally deployed to a device.</span></span>
5. <span data-ttu-id="2164a-129">Après avoir activé les achats en mode hors connexion, vous pouvez acquérir des licences hors connexion pour les applications que vous pouvez synchroniser avec Intune et déployer en tant que gestion des licences de périphériques.</span><span class="sxs-lookup"><span data-stu-id="2164a-129">After enabling Offline shopping, you can acquire offline licenses for apps that you can sync to Intune and deploy as Device licensing.</span></span>
6. <span data-ttu-id="2164a-130">Dans **Intune**les  >  **applications clientes**Intune  >  **Microsoft Store pour les entreprises**, sélectionnez **synchroniser**.</span><span class="sxs-lookup"><span data-stu-id="2164a-130">In **Intune** > **Client apps** > **Microsoft Store for Business**, select **Sync**.</span></span>
7. <span data-ttu-id="2164a-131">Dans la page applications clientes, recherchez l’application dans la liste d’applications.</span><span class="sxs-lookup"><span data-stu-id="2164a-131">In the Client apps page, search for the app in the apps list.</span></span> <span data-ttu-id="2164a-132">Affectez les applications au groupe ou groupes de périphériques souhaité.</span><span class="sxs-lookup"><span data-stu-id="2164a-132">Assign the apps to the desired device group or groups.</span></span> <span data-ttu-id="2164a-133">Sélectionnez **Assignments**le  >  **groupe ajouter**des devoirs.</span><span class="sxs-lookup"><span data-stu-id="2164a-133">Select **Assignments** > **Add group**.</span></span> <br>

![\* Affectation d’applications à des groupes \*](images/sh2-assign-group.png) <br>

8. <span data-ttu-id="2164a-135">Sous type d’affectation, sélectionnez **obligatoire**.</span><span class="sxs-lookup"><span data-stu-id="2164a-135">Under assignment type, choose **Required**.</span></span> <br>

![\* Affectation d’applications à des groupes \*](images/sh2-add-group.png) <br>

9. <span data-ttu-id="2164a-137">Pour les groupes sélectionnés, sélectionnez **licence** de l’appareil, puis **OK** et enregistrez le devoir.</span><span class="sxs-lookup"><span data-stu-id="2164a-137">For the selected groups, choose **Device licensing** and then select **OK** and save the assignment.</span></span> <br>
 
![\* Affectation d’applications à des groupes \*](images/sh2-apps-assign.png)
