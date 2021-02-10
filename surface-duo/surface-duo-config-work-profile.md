---
title: Configurer le profil de travail d’entreprise Android pour Surface Duo
description: Cet article explique comment configurer le profil de travail sur Surface Duo.
ms.technology: windows
ms.prod: surface
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 9/25/2020
ms.reviewer: karand
manager: laurawi
ms.audience: itpro
audience: ITPro
ms.localizationpriority: medium
appliesto:
- Surface Duo
ms.openlocfilehash: 393844a4e4f0f06f16d11d1313ec9aacfa109d57
ms.sourcegitcommit: 37e0994e2b8ae62b0352b016b698edcc7ca500fb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/10/2021
ms.locfileid: "11326157"
---
# <span data-ttu-id="cfc95-103">Configurer le profil de travail d’entreprise Android pour Surface Duo</span><span class="sxs-lookup"><span data-stu-id="cfc95-103">Configure Android Enterprise Work Profile for Surface Duo</span></span>

<span data-ttu-id="cfc95-104">Destinés aux déploiements BYOD, les profils de travail fournissent un espace distinct sur Duo pour les applications et données de travail, offrant aux organisations un contrôle total sur leurs données, applications et stratégies de sécurité sans empêcher les employés d’utiliser leur appareil pour les applications et données personnelles.</span><span class="sxs-lookup"><span data-stu-id="cfc95-104">Targeted at  BYOD deployments, work profiles provide a separate space on Duo for work apps and data, giving organizations full control of their data, apps, and security policies without preventing employees from using their device for personal apps and data.</span></span>

### <span data-ttu-id="cfc95-105">Configurer le profil de travail d’entreprise Android</span><span class="sxs-lookup"><span data-stu-id="cfc95-105">Set up Android Enterprise Work Profile</span></span>

<span data-ttu-id="cfc95-106">Utilisez les profils professionnels pour gérer les données d’entreprise et les applications sur les appareils Android dont l’utilisateur est propriétaire.</span><span class="sxs-lookup"><span data-stu-id="cfc95-106">Use work profiles to manage corporate data and apps on user-owned Android devices.</span></span> <span data-ttu-id="cfc95-107">Par défaut, l’inscription des appareils de profil de travail personnels est activée et ne nécessite aucune configuration supplémentaire de l’administrateur.</span><span class="sxs-lookup"><span data-stu-id="cfc95-107">By default, enrollment of personally owned work profile devices is enabled and requires no further admin configuration.</span></span>  

**<span data-ttu-id="cfc95-108">Pour activer profil de travail d’entreprise :</span><span class="sxs-lookup"><span data-stu-id="cfc95-108">To enable Enterprise Work Profile:</span></span>**

- <span data-ttu-id="cfc95-109">Dans le Gestionnaire de points de terminaison, sélectionnez **Appareils**  >  **Android**  >  **inscription,** puis **sélectionnez Appareils personnels avec profil de travail**.</span><span class="sxs-lookup"><span data-stu-id="cfc95-109">In Endpoint Manager, select **Devices** > **Android** > **Android enrollment** and then select **Personal devices with work profile**.</span></span>
<br><br>
 ![Activer le profil de travail d’entreprise](images/enroll-start.png)

 
**<span data-ttu-id="cfc95-111">Connectez-vous à Surface Duo avec profil de travail d’entreprise Android</span><span class="sxs-lookup"><span data-stu-id="cfc95-111">Sign into Surface Duo with Android Enterprise Work Profile</span></span>**

1. <span data-ttu-id="cfc95-112">Installez l’application Portail d’entreprise à partir de Google Play Store et connectez-vous avec votre compte scolaire ou scolaire ou scolaire Microsoft.</span><span class="sxs-lookup"><span data-stu-id="cfc95-112">Install the Company Portal app from Google Play Store and sign in with your Microsoft work or school account.</span></span><br><br>
![Connectez-vous à Surface Duo](images/duo-wp-1.png)
 
2. <span data-ttu-id="cfc95-114">Dans la page Installation d’Access, **sélectionnez Commencer.**</span><span class="sxs-lookup"><span data-stu-id="cfc95-114">On the Access Setup page, select **Begin**.</span></span><br><br>
![Begin](images/duo-wp-2.png)

3. <span data-ttu-id="cfc95-116">Examinez les informations sur la page de confidentialité et sélectionnez **Continuer.**</span><span class="sxs-lookup"><span data-stu-id="cfc95-116">Review the information on the privacy page and select **Continue**.</span></span><br><br>
 ![Continuer](images/duo-wp-3.png)
<br><br>
 ![Sélectionner continuer](images/duo-wp-4.png)
 
4. <span data-ttu-id="cfc95-119">Une fois l’installation du profil de travail terminée, sélectionnez **Continuer** à activer et inscrire l’appareil.</span><span class="sxs-lookup"><span data-stu-id="cfc95-119">When the work profile setup completes, select **Continue** to activate and register the device.</span></span><br><br>
 ![Sélectionnez Continuer à activer et inscrire l’appareil](images/duo-wp-5.png)

5. <span data-ttu-id="cfc95-121">Sélectionnez **Continuer**.</span><span class="sxs-lookup"><span data-stu-id="cfc95-121">Select **Continue**.</span></span><br><br>
 ![Sélectionnez continuer à nouveau](images/duo-wp-6.png)

6. <span data-ttu-id="cfc95-123">Lorsque vous avez activé le profil de travail, sélectionnez **Continuer à** mettre à jour les paramètres de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="cfc95-123">When you have activated the work profile, select **Continue** to update device settings.</span></span> <span data-ttu-id="cfc95-124">Dans cet exemple, le profil de travail applique un paramètre MDM pour exiger un mot de passe alphanumérique à 6 chiffres plus fort.</span><span class="sxs-lookup"><span data-stu-id="cfc95-124">In this example, the work profile applies an MDM setting to require a stronger 6-digit alphanumeric password.</span></span> <br><br>

     ![Exemple de mot de passe alphanumérique](images/duo-wp-7.png)<br><br>
7. <span data-ttu-id="cfc95-126">Sélectionnez **Résoudre** pour entrer l’authentification requise, puis **continuez** pour terminer la configuration du profil de travail.</span><span class="sxs-lookup"><span data-stu-id="cfc95-126">Select **Resolve** to enter the required authentication and then select **Continue** to complete Work Profile setup.</span></span> <br><br>
     ![Sélectionnez Continuer à terminer l’installation](images/duo-wp-8.png)<br><br>
     ![terminer l’installation](images/duo-wp-9.png)<br><br>

## <span data-ttu-id="cfc95-129">Si vous souhaitez en savoir plus</span><span class="sxs-lookup"><span data-stu-id="cfc95-129">Learn more</span></span>

- [<span data-ttu-id="cfc95-130">Configurer l’inscription des appareils de profil de travail Android Enterprise</span><span class="sxs-lookup"><span data-stu-id="cfc95-130">Set up enrollment of Android Enterprise work profile devices</span></span>](https://docs.microsoft.com/mem/intune/enrollment/android-work-profile-enroll)

