---
title: Réinitialiser ou récupérer un surface Hub
description: Décrit les processus de réinitialisation et de récupération pour surface Hub, et fournit des instructions.
ms.assetid: 44E82EEE-1905-464B-A758-C2A1463909FF
ms.reviewer: ''
manager: laurawi
keywords: réinitialisation de surface Hub, récupération
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/31/2019
ms.localizationpriority: medium
ms.openlocfilehash: 1c8d8b6d89ec1a20550b7aa13c82c73a239c3965
ms.sourcegitcommit: d0a5c8fb2b37eb11858c7be4549e55c4b36d7471
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/08/2020
ms.locfileid: "11104816"
---
# <span data-ttu-id="1f9d1-104">Réinitialiser ou récupérer un surface Hub</span><span class="sxs-lookup"><span data-stu-id="1f9d1-104">Reset or recover a Surface Hub</span></span>

<span data-ttu-id="1f9d1-105">Cet article décrit comment réinitialiser ou récupérer un Microsoft surface Hub.</span><span class="sxs-lookup"><span data-stu-id="1f9d1-105">This article describes how to reset or recover a Microsoft Surface Hub.</span></span>  

<span data-ttu-id="1f9d1-106">[La réinitialisation de surface Hub](#reset-a-surface-hub) renvoie son système d’exploitation vers la dernière mise à jour de Windows, ainsi que des informations de configuration et des fichiers utilisateur locaux.</span><span class="sxs-lookup"><span data-stu-id="1f9d1-106">[Resetting the Surface Hub](#reset-a-surface-hub) returns its operating system to the last cumulative Windows update, and removes all local user files and configuration information.</span></span> <span data-ttu-id="1f9d1-107">Les informations supprimées incluent les éléments suivants:</span><span class="sxs-lookup"><span data-stu-id="1f9d1-107">The information that is removed includes the following:</span></span>

- <span data-ttu-id="1f9d1-108">Le compte d’appareil</span><span class="sxs-lookup"><span data-stu-id="1f9d1-108">The device account</span></span>
- <span data-ttu-id="1f9d1-109">Informations de compte pour les administrateurs locaux de l’appareil</span><span class="sxs-lookup"><span data-stu-id="1f9d1-109">Account information for the device's local administrators</span></span>
- <span data-ttu-id="1f9d1-110">Informations de jointure ou de domaine Azure AD</span><span class="sxs-lookup"><span data-stu-id="1f9d1-110">Domain-join or Azure AD-join information</span></span>
- <span data-ttu-id="1f9d1-111">Informations d’inscription de la gestion des périphériques mobiles (GPM)</span><span class="sxs-lookup"><span data-stu-id="1f9d1-111">Mobile Device Management (MDM) enrollment information</span></span>
- <span data-ttu-id="1f9d1-112">Informations de configuration définies à l’aide de la gestion des périphériques mobiles ou de l’application paramètres</span><span class="sxs-lookup"><span data-stu-id="1f9d1-112">Configuration information that was set by using MDM or the Settings app</span></span>

<span data-ttu-id="1f9d1-113">[La récupération d’un surface Hub à partir du Cloud](#recover-a-surface-hub-from-the-cloud) entraîne également celle de ces informations.</span><span class="sxs-lookup"><span data-stu-id="1f9d1-113">[Recovering a Surface Hub from the cloud](#recover-a-surface-hub-from-the-cloud) also removes this information.</span></span> <span data-ttu-id="1f9d1-114">Par ailleurs, surface Hub télécharge une nouvelle image de système d’exploitation et l’installe.</span><span class="sxs-lookup"><span data-stu-id="1f9d1-114">In addition, the Surface Hub downloads a new operating system image and installs it.</span></span> <span data-ttu-id="1f9d1-115">Vous pouvez spécifier si le processus de récupération conserve d’autres informations stockées sur l’appareil surface Hub.</span><span class="sxs-lookup"><span data-stu-id="1f9d1-115">You can specify whether the recovery process preserves other information that is stored on the Surface Hub.</span></span>

## <span data-ttu-id="1f9d1-116">Réinitialiser un surface Hub</span><span class="sxs-lookup"><span data-stu-id="1f9d1-116">Reset a Surface Hub</span></span>

<span data-ttu-id="1f9d1-117">Il est possible que vous deviez réinitialiser votre concentrateur surface pour les raisons suivantes:</span><span class="sxs-lookup"><span data-stu-id="1f9d1-117">You may have to reset your Surface Hub for reasons such as the following:</span></span>

- <span data-ttu-id="1f9d1-118">Vous réactivez l’appareil pour un nouvel espace de réunion et voulez le reconfigurer.</span><span class="sxs-lookup"><span data-stu-id="1f9d1-118">You are re-purposing the device for a new meeting space and want to reconfigure it.</span></span>
- <span data-ttu-id="1f9d1-119">Vous souhaitez modifier la façon dont vous gérez localement l’appareil.</span><span class="sxs-lookup"><span data-stu-id="1f9d1-119">You want to change how you locally manage the device.</span></span>
- <span data-ttu-id="1f9d1-120">Le nom d’utilisateur ou le mot de passe du compte de l’appareil ou du compte d’administrateur a été perdu.</span><span class="sxs-lookup"><span data-stu-id="1f9d1-120">The user name or password for the device account or the Administrator account has been lost.</span></span>
- <span data-ttu-id="1f9d1-121">Après l’installation d’une mise à jour, les performances de l’appareil sont réduites.</span><span class="sxs-lookup"><span data-stu-id="1f9d1-121">After you install an update, the performance of the device decreases.</span></span>

<span data-ttu-id="1f9d1-122">Pendant le processus de réinitialisation, si vous voyez un écran vide sur de longues périodes, veuillez patienter et ne pas effectuer d’action.</span><span class="sxs-lookup"><span data-stu-id="1f9d1-122">During the reset process, if you see a blank screen for long periods of time, please wait and do not take any action.</span></span>

> [!WARNING]
> <span data-ttu-id="1f9d1-123">Le processus de réinitialisation de l’appareil risque de durer jusqu’à 6 heures.</span><span class="sxs-lookup"><span data-stu-id="1f9d1-123">The device reset process may take up to six hours.</span></span> <span data-ttu-id="1f9d1-124">Ne désactivez pas ou ne débranchez pas le concentrateur de surface tant que le processus n’est pas terminé.</span><span class="sxs-lookup"><span data-stu-id="1f9d1-124">Do not turn off or unplug the Surface Hub until the process has finished.</span></span> <span data-ttu-id="1f9d1-125">Si vous interrompez le processus, l’appareil devient inopérant.</span><span class="sxs-lookup"><span data-stu-id="1f9d1-125">If you interrupt the process, the device becomes inoperable.</span></span> <span data-ttu-id="1f9d1-126">Le service de garantie doit être utilisé pour que l’appareil soit opérationnel de nouveau.</span><span class="sxs-lookup"><span data-stu-id="1f9d1-126">The device requires warranty service in order to become functional again.</span></span>

1. <span data-ttu-id="1f9d1-127">Sur votre Surface Hub, ouvrez **Paramètres**.</span><span class="sxs-lookup"><span data-stu-id="1f9d1-127">On your Surface Hub, open **Settings**.</span></span>

   ![Image montrant l’application paramètres pour surface Hub.](images/sh-settings.png)

1. <span data-ttu-id="1f9d1-129">Sélectionnez **mettre à jour & sécurité**.</span><span class="sxs-lookup"><span data-stu-id="1f9d1-129">Select **Update & Security**.</span></span>

   ![Image illustrant le groupe de sécurité mise à jour & dans l’application paramètres pour surface Hub.](images/sh-settings-update-security.png)

1. <span data-ttu-id="1f9d1-131">Sélectionnez **récupération**, puis, sous **Réinitialiser l’appareil**, sélectionnez mise en **route**.</span><span class="sxs-lookup"><span data-stu-id="1f9d1-131">Select **Recovery**, and then, under **Reset device**, select **Get started**.</span></span>

   ![Image illustrant l’option de réinitialisation de l’appareil dans l’application paramètres pour surface Hub.](images/sh-settings-reset-device.png)

   <span data-ttu-id="1f9d1-133">À la fin du processus de réinitialisation, le concentrateur de surface démarre de nouveau le [programme de premier exécution](first-run-program-surface-hub.md) .</span><span class="sxs-lookup"><span data-stu-id="1f9d1-133">After the reset process finishes, the Surface Hub starts the [first run program](first-run-program-surface-hub.md) again.</span></span> <span data-ttu-id="1f9d1-134">Si le processus de réinitialisation rencontre un problème, il restaure le centre de surface sur l’image du système d’exploitation déjà existant, puis affiche l’écran d’accueil.</span><span class="sxs-lookup"><span data-stu-id="1f9d1-134">If the reset process encounters a problem, it rolls the Surface Hub back to the previously-existing operating system image and then displays the Welcome screen.</span></span>

<span id="cloud-recovery" />

## <span data-ttu-id="1f9d1-135">Récupérer un Surface Hub à partir du cloud</span><span class="sxs-lookup"><span data-stu-id="1f9d1-135">Recover a Surface Hub from the cloud</span></span>

<span data-ttu-id="1f9d1-136">Si, pour une raison quelconque, le concentrateur de surface devient inutilisable, vous pouvez toujours le récupérer à partir du Cloud sans assistance de la part du support Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1f9d1-136">If for some reason the Surface Hub becomes unusable, you can still recover it from the cloud without assistance from Microsoft Support.</span></span> <span data-ttu-id="1f9d1-137">Surface Hub peut télécharger une nouvelle image de système d’exploitation à partir du Cloud et utiliser cette image pour réinstaller son système d’exploitation.</span><span class="sxs-lookup"><span data-stu-id="1f9d1-137">The Surface Hub can download a fresh operating system image from the cloud, and use that image to reinstall its operating system.</span></span>

<span data-ttu-id="1f9d1-138">Il est possible que vous deviez utiliser ce type de processus de récupération dans les cas suivants:</span><span class="sxs-lookup"><span data-stu-id="1f9d1-138">You may have to use this type of recovery process under the following circumstances:</span></span>

- [<span data-ttu-id="1f9d1-139">Surface Hub ou ses comptes liés ont entré un état instable</span><span class="sxs-lookup"><span data-stu-id="1f9d1-139">The Surface Hub or its related accounts have entered an unstable state</span></span>](#recover-a-surface-hub-in-a-bad-state)
- [<span data-ttu-id="1f9d1-140">Surface Hub est verrouillé</span><span class="sxs-lookup"><span data-stu-id="1f9d1-140">The Surface Hub is locked</span></span>](#recover-a-locked-surface-hub)

>[!IMPORTANT]
><span data-ttu-id="1f9d1-141">Le processus **de récupération à partir du Cloud** nécessite une connexion câblée qui fournit une connectivité Internet ouverte (pas de proxy ou d’autres invites d’authentification).</span><span class="sxs-lookup"><span data-stu-id="1f9d1-141">The **Recover from the cloud** process requires a wired connection that provides open internet connectivity (no proxy or other authentication prompts).</span></span>

### <span data-ttu-id="1f9d1-142">Récupérer un Surface Hub se trouvant dans un état incorrect</span><span class="sxs-lookup"><span data-stu-id="1f9d1-142">Recover a Surface Hub in a bad state</span></span>

<span data-ttu-id="1f9d1-143">Si le compte d’appareil est dans un état instable ou si le compte d’administrateur rencontre des problèmes, vous pouvez utiliser l’application paramètres pour démarrer le processus de récupération Cloud.</span><span class="sxs-lookup"><span data-stu-id="1f9d1-143">If the device account gets into an unstable state or if the administrator account encounters problems, you can use the Settings app to start the cloud recovery process.</span></span> <span data-ttu-id="1f9d1-144">Vous devez uniquement utiliser le processus de récupération Cloud lorsque le processus de [réinitialisation](#reset-a-surface-hub) de l’appareil ne résout pas le problème.</span><span class="sxs-lookup"><span data-stu-id="1f9d1-144">You should only use the cloud recovery process when the [device reset](#reset-a-surface-hub) process doesn't fix the problem.</span></span>

1. <span data-ttu-id="1f9d1-145">Sur votre surface Hub, sélectionnez **Settings** &gt; **mise à jour** des paramètres & récupération de la sécurité &gt; **Recovery**.</span><span class="sxs-lookup"><span data-stu-id="1f9d1-145">On your Surface Hub, select **Settings** &gt; **Update & security** &gt; **Recovery**.</span></span>

1. <span data-ttu-id="1f9d1-146">Sous **récupérer dans le Cloud**, sélectionnez **redémarrer maintenant**.</span><span class="sxs-lookup"><span data-stu-id="1f9d1-146">Under **Recover from the cloud**, select **Restart now**.</span></span>

   ![récupérer à partir du cloud](images/recover-from-the-cloud.png)

### <span data-ttu-id="1f9d1-148">Récupérer un Surface Hub verrouillé</span><span class="sxs-lookup"><span data-stu-id="1f9d1-148">Recover a locked Surface Hub</span></span>

<span data-ttu-id="1f9d1-149">À de rares occasions, un SurfaceHub peut rencontrer une erreur lors du nettoyage des données utilisateur et d’application à la fin d’une session.</span><span class="sxs-lookup"><span data-stu-id="1f9d1-149">On rare occasions, a Surface Hub may encounter an error while cleaning up user and app data at the end of a session.</span></span> <span data-ttu-id="1f9d1-150">Lorsque c’est le cas, l’appareil redémarre automatiquement et tente de nouveau l’opération.</span><span class="sxs-lookup"><span data-stu-id="1f9d1-150">When this happens, the device automatically restarts and tries the operation again.</span></span> <span data-ttu-id="1f9d1-151">Néanmoins, si cette opération échoue de manière répétée, l’appareil se verrouille automatiquement pour protéger les données des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="1f9d1-151">But if this operation fails repeatedly, the device automatically locks to protect user data.</span></span> <span data-ttu-id="1f9d1-152">Pour le déverrouiller, vous devez [Réinitialiser l’appareil](#reset-a-surface-hub) ou, si cela ne fonctionne pas, le récupérer à partir du Cloud.</span><span class="sxs-lookup"><span data-stu-id="1f9d1-152">To unlock it, you must [reset the device](#reset-a-surface-hub) or, if that doesn't work, recover it from the cloud.</span></span>

1. <span data-ttu-id="1f9d1-153">Recherchez le bouton marche/arrêt dans la partie inférieure de surface Hub.</span><span class="sxs-lookup"><span data-stu-id="1f9d1-153">Locate the power switch on the bottom of Surface Hub.</span></span> <span data-ttu-id="1f9d1-154">Le bouton marche/arrêt se trouve à côté de l’option connexion du cordon d’alimentation.</span><span class="sxs-lookup"><span data-stu-id="1f9d1-154">The power switch is next to the power cord connection.</span></span> <span data-ttu-id="1f9d1-155">Pour plus d’informations sur le basculement, voir le [Guide de compatibilité du site surface Hub (PDF)](surface-hub-site-readiness-guide.md).</span><span class="sxs-lookup"><span data-stu-id="1f9d1-155">For more information about the power switch, see the [Surface Hub Site Readiness Guide (PDF)](surface-hub-site-readiness-guide.md).</span></span>

1. <span data-ttu-id="1f9d1-156">Lorsque l’écran d’accueil de surface Hub est affiché, utilisez le commutateur de puissance pour éteindre le surface Hub.</span><span class="sxs-lookup"><span data-stu-id="1f9d1-156">While the Surface Hub displays the Welcome screen, use the power switch to turn off the Surface Hub.</span></span>

1. <span data-ttu-id="1f9d1-157">Utilisez le commutateur Power Pivot pour réactiver le centre de surface.</span><span class="sxs-lookup"><span data-stu-id="1f9d1-157">Use the power switch to turn the Surface Hub back on.</span></span> <span data-ttu-id="1f9d1-158">Le périphérique démarre et affiche l’écran du logo surface Hub.</span><span class="sxs-lookup"><span data-stu-id="1f9d1-158">The device starts and displays the Surface Hub Logo screen.</span></span> <span data-ttu-id="1f9d1-159">Lorsque vous voyez des points de rotation sous le logo surface Hub, utilisez le commutateur d’alimentation pour réactiver le centre de surface.</span><span class="sxs-lookup"><span data-stu-id="1f9d1-159">When you see spinning dots under the Surface Hub Logo, use the power switch to turn the Surface Hub off again.</span></span>  

1. <span data-ttu-id="1f9d1-160">Répétez l’étape 3 3 ou jusqu’à ce que surface Hub affiche le message «préparation automatique».</span><span class="sxs-lookup"><span data-stu-id="1f9d1-160">Repeat step 3 three times, or until the Surface Hub displays the "Preparing Automatic Repair" message.</span></span> <span data-ttu-id="1f9d1-161">Après avoir affiché ce message, l’application surface Hub affiche l’écran Windows RE.</span><span class="sxs-lookup"><span data-stu-id="1f9d1-161">After it displays this message, the Surface Hub displays the Windows RE screen.</span></span>

1. <span data-ttu-id="1f9d1-162">Sélectionnez **Options avancées**.</span><span class="sxs-lookup"><span data-stu-id="1f9d1-162">Select **Advanced Options**.</span></span>

1. <span data-ttu-id="1f9d1-163">Sélectionnez **récupérer dans le Cloud**.</span><span class="sxs-lookup"><span data-stu-id="1f9d1-163">Select **Recover from the cloud**.</span></span> <span data-ttu-id="1f9d1-164">(Vous pouvez également sélectionner **Réinitialiser**.</span><span class="sxs-lookup"><span data-stu-id="1f9d1-164">(Optionally, you can select **Reset**.</span></span> <span data-ttu-id="1f9d1-165">Néanmoins, la **récupération à partir du Cloud** est l’approche recommandée.)</span><span class="sxs-lookup"><span data-stu-id="1f9d1-165">However, **Recover from the cloud** is the recommended approach.)</span></span>

   ![Récupérer à partir du cloud](images/recover-from-cloud.png)
1. <span data-ttu-id="1f9d1-167">Si vous êtes invité à entrer la clé BitLocker, effectuez l’une des opérations suivantes:</span><span class="sxs-lookup"><span data-stu-id="1f9d1-167">If you are prompted to enter the Bitlocker key, do one of the following:</span></span>

   - <span data-ttu-id="1f9d1-168">Pour conserver les informations que BitLocker protège sur surface Hub, entrez la clé BitLocker.</span><span class="sxs-lookup"><span data-stu-id="1f9d1-168">To preserve the information that Bitlocker protects on the Surface Hub, enter the Bitlocker key.</span></span>
   - <span data-ttu-id="1f9d1-169">Pour ignorer les informations protégées, sélectionnez **ignorer ce lecteur** .</span><span class="sxs-lookup"><span data-stu-id="1f9d1-169">To discard the protected information, select **Skip this drive**</span></span>  

1. <span data-ttu-id="1f9d1-170">Lorsque vous y êtes invité, sélectionnez **réinstaller**.</span><span class="sxs-lookup"><span data-stu-id="1f9d1-170">When you are prompted, select **Reinstall**.</span></span>

    ![Réinstaller](images/reinstall.png)

1. <span data-ttu-id="1f9d1-172">Pour repartitionner le disque, sélectionnez **Oui**.</span><span class="sxs-lookup"><span data-stu-id="1f9d1-172">To repartition the disk, select **Yes**.</span></span>

   ![Repartitionner](images/repartition.png)

   <span data-ttu-id="1f9d1-174">Tout d’abord, le processus de récupération télécharge l’image du système d’exploitation à partir du Cloud.</span><span class="sxs-lookup"><span data-stu-id="1f9d1-174">First, the recovery process downloads the operating system image from the cloud.</span></span>  

   ![téléchargement 97%](images/recover-progress.png)

   <span data-ttu-id="1f9d1-176">Lorsque le téléchargement est terminé, le processus de récupération restaure le centre de surface conformément aux options que vous avez sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="1f9d1-176">When the download finishes, the recovery process restores the Surface Hub according to the options that you selected.</span></span>
   

## <span data-ttu-id="1f9d1-177">Contacter le support</span><span class="sxs-lookup"><span data-stu-id="1f9d1-177">Contact Support</span></span>

<span data-ttu-id="1f9d1-178">Si vous avez des questions ou si vous avez besoin d’aide, vous pouvez [créer une demande de support](https://support.microsoft.com/supportforbusiness/productselection).</span><span class="sxs-lookup"><span data-stu-id="1f9d1-178">If you have questions or need help, you can [create a support request](https://support.microsoft.com/supportforbusiness/productselection).</span></span>


## <span data-ttu-id="1f9d1-179">Rubriquesassociées</span><span class="sxs-lookup"><span data-stu-id="1f9d1-179">Related topics</span></span>

[<span data-ttu-id="1f9d1-180">Gérer Microsoft Surface Hub</span><span class="sxs-lookup"><span data-stu-id="1f9d1-180">Manage Microsoft Surface Hub</span></span>](manage-surface-hub.md)

[<span data-ttu-id="1f9d1-181">Guide de l’administrateur Microsoft Surface Hub</span><span class="sxs-lookup"><span data-stu-id="1f9d1-181">Microsoft Surface Hub administrator's guide</span></span>](surface-hub-administrators-guide.md)
