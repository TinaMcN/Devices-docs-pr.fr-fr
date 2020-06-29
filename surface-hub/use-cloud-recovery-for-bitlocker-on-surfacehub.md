---
title: Comment utiliser la récupération Cloud pour BitLocker sur un appareil SurfaceHub
description: Comment utiliser la récupération Cloud pour BitLocker sur un appareil SurfaceHub
ms.assetid: c0bde23a-49de-40f3-a675-701e3576d44d
keywords: Paramètres d’accessibilité, application Paramètres, Options d’ergonomie
ms.prod: surface-hub
ms.sitesec: library
author: v-miegge
ms.author: v-miegge
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: 7912f9d1bab2ba625995c56d6d7da4e6b2d3df37
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832670"
---
# <span data-ttu-id="1d6ee-104">Résumé</span><span class="sxs-lookup"><span data-stu-id="1d6ee-104">Summary</span></span>

<span data-ttu-id="1d6ee-105">Cet article décrit comment utiliser la fonction de récupération Cloud si vous êtes invité de façon inattendue par BitLocker sur un appareil surface Hub.</span><span class="sxs-lookup"><span data-stu-id="1d6ee-105">This article describes how to use the cloud recovery function if you are unexpectedly prompted by BitLocker on a Surface Hub device.</span></span>

> [!NOTE]
> <span data-ttu-id="1d6ee-106">Suivez ces étapes uniquement si aucune clé de récupération BitLocker n’est disponible.</span><span class="sxs-lookup"><span data-stu-id="1d6ee-106">You should follow these steps only if a BitLocker recovery key isn't available.</span></span>

> [!WARNING]
> * <span data-ttu-id="1d6ee-107">Ce processus de récupération supprime le contenu du disque interne.</span><span class="sxs-lookup"><span data-stu-id="1d6ee-107">This recovery process deletes the contents of the internal drive.</span></span> <span data-ttu-id="1d6ee-108">En cas d’échec du processus, le disque interne devient entièrement inutilisable.</span><span class="sxs-lookup"><span data-stu-id="1d6ee-108">If the process fails, the internal drive will become completely unusable.</span></span> <span data-ttu-id="1d6ee-109">Si tel est le cas, vous devrez consigner une demande de service auprès de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1d6ee-109">If this occurs, you will have to log a service request with Microsoft for a resolution.</span></span>
> * <span data-ttu-id="1d6ee-110">Une fois le processus de récupération terminé, l’appareil est réinitialisé aux paramètres d’usine et est retourné à son état d’arrêt hors champ.</span><span class="sxs-lookup"><span data-stu-id="1d6ee-110">After the recovery process is complete, the device will be reset to the factory settings and returned to its Out of Box Experience state.</span></span>
> * <span data-ttu-id="1d6ee-111">Après la récupération, surface hub doit être complètement reconfiguré.</span><span class="sxs-lookup"><span data-stu-id="1d6ee-111">After the recovery, the Surface Hub must be completely reconfigured.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1d6ee-112">Ce processus nécessite une connexion Internet ouverte qui n’utilise pas de proxy ou d’autre méthode d’authentification.</span><span class="sxs-lookup"><span data-stu-id="1d6ee-112">This process requires an open Internet connection that does not use a proxy or other authentication method.</span></span>

## <span data-ttu-id="1d6ee-113">Processus de récupération Cloud</span><span class="sxs-lookup"><span data-stu-id="1d6ee-113">Cloud recovery process</span></span>

<span data-ttu-id="1d6ee-114">Pour effectuer une récupération du Cloud, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="1d6ee-114">To perform a cloud recovery, follow these steps:</span></span>

1. <span data-ttu-id="1d6ee-115">**Pour plus d’options de récupération, sélectionnez appuyer sur ÉCHAP**.</span><span class="sxs-lookup"><span data-stu-id="1d6ee-115">Select **Press Esc for more recovery options**.</span></span>

   ![Capture d’écran de l’échappement](images/01-escape.png)

1. <span data-ttu-id="1d6ee-117">Sélectionnez **ignorer ce lecteur**.</span><span class="sxs-lookup"><span data-stu-id="1d6ee-117">Select **Skip this drive**.</span></span>

   ![Capture d’écran de la commande ignorer ce lecteur](images/02-skip-this-drive.png)

1. <span data-ttu-id="1d6ee-119">Sélectionnez **récupérer dans le Cloud**.</span><span class="sxs-lookup"><span data-stu-id="1d6ee-119">Select **Recover from the cloud**.</span></span>

   ![Capture d’écran de la restauration à partir du Cloud](images/03-recover-from-cloud.png)

1. <span data-ttu-id="1d6ee-121">Sélectionnez **Oui**.</span><span class="sxs-lookup"><span data-stu-id="1d6ee-121">Select **Yes**.</span></span>

   ![Capture d’écran de Oui](images/04-yes.png)

1. <span data-ttu-id="1d6ee-123">Sélectionnez **réinstaller**.</span><span class="sxs-lookup"><span data-stu-id="1d6ee-123">Select **Reinstall**.</span></span>

   ![Capture d’écran de la réinstallation](images/05a-reinstall.png)

   ![Capture d’écran du téléchargement](images/05b-downloading.png)

1. <span data-ttu-id="1d6ee-126">Une fois le processus de récupération du Cloud terminé, démarrez la reconfiguration en utilisant le mode **hors connexion**.</span><span class="sxs-lookup"><span data-stu-id="1d6ee-126">After the cloud recovery process is complete, start the reconfiguration by using the **Out of Box Experience**.</span></span>

   ![Capture d’écran de la zone prêts à l’emploi](images/06-out-of-box.png)

## <span data-ttu-id="1d6ee-128">Message d’erreur «un problème est survenu»</span><span class="sxs-lookup"><span data-stu-id="1d6ee-128">"Something went Wrong" error message</span></span>

<span data-ttu-id="1d6ee-129">Cette erreur est généralement provoquée par des problèmes de réseau qui se produisent pendant le téléchargement de récupération.</span><span class="sxs-lookup"><span data-stu-id="1d6ee-129">This error is usually caused by network issues that occur during the recovery download.</span></span> <span data-ttu-id="1d6ee-130">Lorsque ce problème survient, ne désactivez pas le concentrateur, car vous ne pourrez pas le redémarrer.</span><span class="sxs-lookup"><span data-stu-id="1d6ee-130">When this issue occurs, don't turn off the Hub because you won't be able to restart it.</span></span> <span data-ttu-id="1d6ee-131">Si vous recevez ce message d’erreur, revenez à l’étape «récupérer à partir du Cloud», puis redémarrez le processus de récupération.</span><span class="sxs-lookup"><span data-stu-id="1d6ee-131">If you receive this error message, return to the "Recover from the cloud" step, and then restart the recovery process.</span></span>

1. <span data-ttu-id="1d6ee-132">Sélectionnez **Annuler**.</span><span class="sxs-lookup"><span data-stu-id="1d6ee-132">Select **Cancel**.</span></span>

   ![Capture d’écran de l’annulation](images/07-cancel.png)

1. <span data-ttu-id="1d6ee-134">Sélectionnez **résolution des problèmes**.</span><span class="sxs-lookup"><span data-stu-id="1d6ee-134">Select **Troubleshoot**.</span></span>

   ![Capture d’écran de la résolution des problèmes](images/08-troubleshoot.png)

1. <span data-ttu-id="1d6ee-136">Sélectionnez **récupérer dans le Cloud**.</span><span class="sxs-lookup"><span data-stu-id="1d6ee-136">Select **Recover from the cloud**.</span></span>

   ![Capture d’écran de la restauration à partir du Cloud](images/09-recover-from-cloud2.png)

1. <span data-ttu-id="1d6ee-138">Si l’erreur « **réseau filaire introuvable** » s’affiche, sélectionnez **Annuler**, puis laissez surface Hub découvrir le réseau filaire.</span><span class="sxs-lookup"><span data-stu-id="1d6ee-138">If the **Wired network isn't found** error occurs, select **Cancel**, and then let the Surface Hub rediscover the wired network.</span></span>

   ![Capture d’écran du réseau filaire introuvable](images/10-cancel.png)