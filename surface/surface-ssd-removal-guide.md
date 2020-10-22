---
title: Suppression de SSD dans des appareils surface compatibles
description: Cet article, destiné aux techniciens informatiques qualifiés, présente les meilleures pratiques recommandées en matière de suppression et de remplacement de SSDs dans surface Laptop 3, surface Pro X et surface Laptop Go.
ms.prod: w10
ms.localizationpriority: medium
ms.mktglfcycl: manage
ms.sitesec: library
author: mccoybot
ms.author: v-todmc
ms.topic: article
ms.date: 10/21/2020
ms.reviewer: ''
manager: laurawi
ms.audience: itpro
audience: ITPro
appliesto:
- Surface Laptop 3
- Surface Pro X
- Surface Laptop Go
ms.custom:
- CI 121887
- CSSTroubleshoot
ms.openlocfilehash: 56c740b39d86ea3fab386e88efa6932e050bb957
ms.sourcegitcommit: 959d2d856b1e5b5c72cd636f576b5feb1b633048
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/21/2020
ms.locfileid: "11133169"
---
# <span data-ttu-id="469fd-103">Recommandations en matière de suppression de disques durs de périphériques de surface compatibles</span><span class="sxs-lookup"><span data-stu-id="469fd-103">Best practices for SSD removal from compatible Surface devices</span></span>

> [!IMPORTANT]
> <span data-ttu-id="469fd-104">Cet article est destiné aux techniciens informatiques qualifiés au sein d’une organisation d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="469fd-104">This article is intended for use by qualified IT technicians in an enterprise organization only.</span></span> <span data-ttu-id="469fd-105">Il présente les meilleures pratiques recommandées pour les techniciens informatiques qualifiés lors de la suppression et du remplacement de SSDs sur les appareils surface compatibles suivants:</span><span class="sxs-lookup"><span data-stu-id="469fd-105">It describes the recommended best practices for use by qualified IT technicians in the removal and replacement of SSDs in the following compatible Surface devices:</span></span> 

- <span data-ttu-id="469fd-106">Surface Laptop3</span><span class="sxs-lookup"><span data-stu-id="469fd-106">Surface Laptop 3</span></span> 
- <span data-ttu-id="469fd-107">SurfaceProX</span><span class="sxs-lookup"><span data-stu-id="469fd-107">Surface Pro X</span></span> 
- <span data-ttu-id="469fd-108">Surface Laptop Go</span><span class="sxs-lookup"><span data-stu-id="469fd-108">Surface Laptop Go</span></span>

> [!WARNING]
> <span data-ttu-id="469fd-109">L’ouverture de périphériques et le remplacement des composants de périphériques peuvent présenter un choc électrique, un dommage de l’appareil, un incendie, des risques liés au préjudice personnel et autres dangers.</span><span class="sxs-lookup"><span data-stu-id="469fd-109">Opening devices and replacing device components can present electric shock, device damage, fire, and personal injury risks, and other hazards.</span></span>  <span data-ttu-id="469fd-110">Soyez toujours prudent lorsque vous exercez de telles activités.</span><span class="sxs-lookup"><span data-stu-id="469fd-110">Always use caution when you undertake such activities.</span></span> <span data-ttu-id="469fd-111">Suivez les consignes et procédures de sécurité qui sont identifiées dans le [Guide de suppression de rSSD pour les entreprises](https://www.microsoft.com/download/100440).</span><span class="sxs-lookup"><span data-stu-id="469fd-111">Follow the safety precautions and procedures that are identified in the [rSSD Removal Guide for Enterprise](https://www.microsoft.com/download/100440).</span></span> <span data-ttu-id="469fd-112">Nous vous recommandons d’obtenir une assistance technique si vous ne pouvez pas suivre les consignes de sécurité et les procédures indiquées dans le Guide de suppression de rSSD pour les entreprises.</span><span class="sxs-lookup"><span data-stu-id="469fd-112">We recommend that you get professional assistance if you cannot follow the safety precautions and procedures that are specified in the "rSSD Removal Guide for Enterprise."</span></span>

## <span data-ttu-id="469fd-113">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="469fd-113">Prerequisites</span></span>

> [!IMPORTANT]
> <span data-ttu-id="469fd-114">Cet article part du principe que vous comprenez les consignes générales en matière de sécurité et les stratégies et procédures de sécurité décrites dans le «Guide de suppression rSSD pour les entreprises».</span><span class="sxs-lookup"><span data-stu-id="469fd-114">This article assumes that you understand the General Safety Precautions and Safety policies and procedures that are described in the "rSSD Removal Guide for Enterprise."</span></span>

## <span data-ttu-id="469fd-115">Préparer la suppression de votre microinstallation</span><span class="sxs-lookup"><span data-stu-id="469fd-115">Prepare for SSD removal</span></span> 

### <span data-ttu-id="469fd-116">Installer les mises à jour les plus récentes</span><span class="sxs-lookup"><span data-stu-id="469fd-116">Install the latest updates</span></span> 

<span data-ttu-id="469fd-117">Avant de commencer, assurez-vous que votre version de Windows dispose des dernières mises à jour:</span><span class="sxs-lookup"><span data-stu-id="469fd-117">Before you begin, make sure that your version of Windows has the latest updates installed:</span></span>

1.  <span data-ttu-id="469fd-118">Accédez à **Start**  >  **Settings**  >  **mise à jour**des paramètres de démarrage & sécurité, puis sélectionnez **Rechercher les mises à jour**.</span><span class="sxs-lookup"><span data-stu-id="469fd-118">Go to **Start** > **Settings** > **Update & Security**, and select **Check for updates**.</span></span>
2. <span data-ttu-id="469fd-119">Installez toutes les mises à jour disponibles.</span><span class="sxs-lookup"><span data-stu-id="469fd-119">Install all available updates.</span></span>
3. <span data-ttu-id="469fd-120">Vérifiez les mots de passe nécessaires pour accéder à l’appareil.</span><span class="sxs-lookup"><span data-stu-id="469fd-120">Verify any passwords that are necessary to access the device.</span></span>  
 
## <span data-ttu-id="469fd-121">Gérer BitLocker</span><span class="sxs-lookup"><span data-stu-id="469fd-121">Manage BitLocker</span></span> 

> [!NOTE]
> <span data-ttu-id="469fd-122">Cette section contient des recommandations pour les organisations ayant activé le chiffrement BitLocker pour les disques durs.</span><span class="sxs-lookup"><span data-stu-id="469fd-122">This section includes recommendations for organizations that have enabled BitLocker encryption for hard disks.</span></span> <span data-ttu-id="469fd-123">Pour plus d’informations, reportez-vous au  [Guide de récupération de BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan).</span><span class="sxs-lookup"><span data-stu-id="469fd-123">For more information, see  [BitLocker Recovery Guide](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan).</span></span> 

### <span data-ttu-id="469fd-124">Si le chiffrement BitLocker est désactivé lors de la suppression et du remplacement de disques durs</span><span class="sxs-lookup"><span data-stu-id="469fd-124">If BitLocker encryption is disabled during SSD removal and replacement</span></span>

<span data-ttu-id="469fd-125">Si l’appareil peut être déchiffré avant la suppression et le remplacement de votre appareil, procédez comme suit pour désactiver BitLocker:</span><span class="sxs-lookup"><span data-stu-id="469fd-125">If the device can be unencrypted before SSD removal and replacement, follow these steps to turn off BitLocker:</span></span>

1.  <span data-ttu-id="469fd-126">Dans **paramètres**, tapez **BitLocker** et sélectionnez **gérer BitLocker**.</span><span class="sxs-lookup"><span data-stu-id="469fd-126">In **Settings**, type **BitLocker** and then select **Manage BitLocker**.</span></span> 
2.  <span data-ttu-id="469fd-127">Sélectionnez **Désactiver BitLocker**.</span><span class="sxs-lookup"><span data-stu-id="469fd-127">Select **Turn Off BitLocker**.</span></span> 
3.  <span data-ttu-id="469fd-128">Allumez l’appareil.</span><span class="sxs-lookup"><span data-stu-id="469fd-128">Power down the device.</span></span> 

### <span data-ttu-id="469fd-129">Si le chiffrement BitLocker est activé lors de la suppression et du remplacement de disques durs</span><span class="sxs-lookup"><span data-stu-id="469fd-129">If BitLocker encryption is enabled during SSD removal and replacement</span></span>

<span data-ttu-id="469fd-130">Si l’appareil est chiffré avant la suppression et le remplacement de votre appareil, procédez comme suit pour générer une clé de récupération BitLocker et l’enregistrer dans le stockage USB:</span><span class="sxs-lookup"><span data-stu-id="469fd-130">If the device is encrypted before SSD removal and replacement, follow these steps to generate a BitLocker recovery key and save it to USB storage:</span></span>

1.  <span data-ttu-id="469fd-131">Dans **paramètres**, tapez **BitLocker**.</span><span class="sxs-lookup"><span data-stu-id="469fd-131">In **Settings**, type **BitLocker**.</span></span>
2. <span data-ttu-id="469fd-132">Sélectionnez **gérer BitLocker**  > **générer la clé de récupération BitLocker**.</span><span class="sxs-lookup"><span data-stu-id="469fd-132">Select **Manage BitLocker** >**Generate BitLocker Recovery Key**.</span></span>
2.  <span data-ttu-id="469fd-133">Insérez un lecteur USB.</span><span class="sxs-lookup"><span data-stu-id="469fd-133">Insert a USB drive.</span></span> 
4.  <span data-ttu-id="469fd-134">Enregistrez la clé de récupération sur le stockage USB.</span><span class="sxs-lookup"><span data-stu-id="469fd-134">Save the recovery key to USB storage.</span></span>  
5.  <span data-ttu-id="469fd-135">Retirez le lecteur USB.</span><span class="sxs-lookup"><span data-stu-id="469fd-135">Remove the USB drive.</span></span>  
6.  <span data-ttu-id="469fd-136">Allumez l’appareil.</span><span class="sxs-lookup"><span data-stu-id="469fd-136">Power down the device.</span></span> 

## <span data-ttu-id="469fd-137">Supprimer et remplacer la SSD</span><span class="sxs-lookup"><span data-stu-id="469fd-137">Remove and replace SSD</span></span> 

1.  <span data-ttu-id="469fd-138">Supprimez le SSD en suivant les instructions du [Guide de suppression de rSSD pour les entreprises](https://www.microsoft.com/download/100440).</span><span class="sxs-lookup"><span data-stu-id="469fd-138">Remove the SSD by using the instructions in [rSSD Removal Guide for Enterprise](https://www.microsoft.com/download/100440).</span></span> 
2.  <span data-ttu-id="469fd-139">Insérez la nouvelle image SSD dans un nouvel appareil et connectez le nouvel appareil à une connexion Internet câblée.</span><span class="sxs-lookup"><span data-stu-id="469fd-139">Put the original SSD into a new device and connect the new device to a wired internet connection.</span></span>
3.  <span data-ttu-id="469fd-140">Allumez le nouvel appareil.</span><span class="sxs-lookup"><span data-stu-id="469fd-140">Power on the new device.</span></span> <span data-ttu-id="469fd-141">Il est possible que l’appareil passe par une mise à jour du microprogramme lors du démarrage.</span><span class="sxs-lookup"><span data-stu-id="469fd-141">The device may go through a firmware update during startup.</span></span>  
 
## <span data-ttu-id="469fd-142">Après suppression et remplacement de disques durs</span><span class="sxs-lookup"><span data-stu-id="469fd-142">After SSD removal and replacement</span></span>

### <span data-ttu-id="469fd-143">Gérer les SSDs non chiffrés</span><span class="sxs-lookup"><span data-stu-id="469fd-143">Manage unencrypted SSDs</span></span> 

<span data-ttu-id="469fd-144">Si le SSD n’est pas chiffré lors du transfert, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="469fd-144">If the SSD is unencrypted during the transfer, follow these steps:</span></span> 

1.  <span data-ttu-id="469fd-145">Accédez à **options de connexion**  >  **mot de passe** (représenté par l’icône de clé située sur le côté gauche).</span><span class="sxs-lookup"><span data-stu-id="469fd-145">Go to **Sign-In Options** > **Password** (represented by the key icon on the left side).</span></span>  
2.  <span data-ttu-id="469fd-146">Entrez le mot de passe et connectez-vous en attente d’exécution de l’authentification à deux facteurs (le cas échéant).</span><span class="sxs-lookup"><span data-stu-id="469fd-146">Enter the password and sign in pending completion of two-factor authentication (if applicable).</span></span>
3.  <span data-ttu-id="469fd-147">Une fois que vous êtes connecté, **accédez à la**  >  **Account**  >  **déconnexion**de votre compte.</span><span class="sxs-lookup"><span data-stu-id="469fd-147">After you are fully signed in, go to **Start** > **Account** > **Sign out**.</span></span>  
4.  <span data-ttu-id="469fd-148">Reconnectez-vous à l’aide du mot de passe et configurez Windows Hello et un code confidentiel lorsque vous y êtes invité.</span><span class="sxs-lookup"><span data-stu-id="469fd-148">Sign back in by using the password and set up Windows Hello and a PIN when you are prompted.</span></span> 
    - <span data-ttu-id="469fd-149">Si l’appareil a été désactivé par BitLocker pour faciliter la suppression et le remplacement de disques durs et que vous souhaitez activer BitLocker après le remplacement, accédez à **BitLocker**  >  **Manage BitLocker**  >  **Resume BitLocker**.</span><span class="sxs-lookup"><span data-stu-id="469fd-149">If the device was BitLocker-disabled to facilitate SSD removal and replacement, and you want to enable BitLocker after the replacement, go to **BitLocker** > **Manage BitLocker** > **Resume BitLocker**.</span></span>  
6.  <span data-ttu-id="469fd-150">Exécutez le [Kit de connaissances Microsoft surface diagnostic pour les entreprises](surface-diagnostic-toolkit-for-business-intro.md) (SDT) pour vérifier le fonctionnement complet de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="469fd-150">Run the [Microsoft Surface Diagnostic Toolkit for Business](surface-diagnostic-toolkit-for-business-intro.md) (SDT) to verify full device functionality.</span></span>  
7.  <span data-ttu-id="469fd-151">Recherchez l’activation de Windows en accédant à activation des **paramètres**  >  **Activation**.</span><span class="sxs-lookup"><span data-stu-id="469fd-151">Check for Windows activation by navigating to **Settings** > **Activation**.</span></span>  <span data-ttu-id="469fd-152">Si un message d’erreur s’affiche, sélectionnez **résoudre les problèmes**.</span><span class="sxs-lookup"><span data-stu-id="469fd-152">If you see any error messages, select **Troubleshoot**.</span></span> 
8.  <span data-ttu-id="469fd-153">Pour vérifier le compte Office, ouvrez l' **application Office**, accédez au compte de **fichier**,  >  **Account** puis recherchez les messages d’erreur.</span><span class="sxs-lookup"><span data-stu-id="469fd-153">Check the Office account by opening the **Office App**, navigate to **File** > **Account** and then check for any error messages.</span></span>  

### <span data-ttu-id="469fd-154">Gestion des SSDs chiffrés</span><span class="sxs-lookup"><span data-stu-id="469fd-154">Managing encrypted SSDs</span></span> 

> [!NOTE]
> <span data-ttu-id="469fd-155">Vous devez disposer d’un deuxième appareil pour lire la clé de récupération BitLocker qui a été enregistrée sur le lecteur USB.</span><span class="sxs-lookup"><span data-stu-id="469fd-155">You will have to have a second device to read the BitLocker Recovery key that was saved on the USB drive.</span></span> 

<span data-ttu-id="469fd-156">Si le SSD est crypté lors du transfert, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="469fd-156">If the SSD is encrypted during the transfer, follow these steps:</span></span>

1.  <span data-ttu-id="469fd-157">Insérez le lecteur USB contenant la clé de récupération BitLocker dans le second appareil.</span><span class="sxs-lookup"><span data-stu-id="469fd-157">Insert the USB drive that contains the BitLocker recovery key into the second device.</span></span> 
2.  <span data-ttu-id="469fd-158">Ouvrez le fichier. txt contenant la clé de récupération BitLocker.</span><span class="sxs-lookup"><span data-stu-id="469fd-158">Open the .txt file that contains the Bitlocker recovery key.</span></span> 
3.  <span data-ttu-id="469fd-159">Entrez manuellement la clé de récupération BitLocker sur le nouvel appareil contenant la clé SSD d’origine.</span><span class="sxs-lookup"><span data-stu-id="469fd-159">Manually enter the BitLocker recovery key on the new device that contains the original SSD.</span></span>  
4.  <span data-ttu-id="469fd-160">Après avoir entré la clé de récupération BitLocker, accédez au mot de passe des **options de connexion**  >  **Password** (représenté par l’icône de clé située sur le côté gauche).</span><span class="sxs-lookup"><span data-stu-id="469fd-160">After you have successfully entered the BitLocker recovery key, go to **Sign-In Options** > **Password** (represented by the key icon on the left side).</span></span>  
5.  <span data-ttu-id="469fd-161">Entrez le mot de passe et connectez-vous en attente d’exécution de l’authentification à deux facteurs (le cas échéant).</span><span class="sxs-lookup"><span data-stu-id="469fd-161">Enter the password and sign in, pending completion of two-factor authentication (if applicable).</span></span>
6.  <span data-ttu-id="469fd-162">Une fois que vous êtes connecté, **accédez à la**  >  **Account**  >  **déconnexion**de votre compte.</span><span class="sxs-lookup"><span data-stu-id="469fd-162">After you are fully signed in, go to **Start** > **Account** > **Sign out**.</span></span>  
7.  <span data-ttu-id="469fd-163">Reconnectez-vous à l’aide du mot de passe, puis configurez Windows Hello et ajoutez un code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="469fd-163">Sign back in by using the password, and then set up Windows Hello and add a PIN.</span></span> 
8.  <span data-ttu-id="469fd-164">Si l’appareil a été désactivé par BitLocker pour faciliter la suppression et le remplacement de disques durs, et si vous souhaitez activer BitLocker après le remplacement, accédez à **paramètres**  >  **BitLocker**  >  **gérer**BitLocker-  >  **reprise**BitLocker.</span><span class="sxs-lookup"><span data-stu-id="469fd-164">If the device was BitLocker-disabled to facilitate SSD removal and replacement, and if you want to enable BitLocker after the replacement, go to **Settings** > **BitLocker** > **Manage BitLocker** > **Resume BitLocker**.</span></span>  
9.  <span data-ttu-id="469fd-165">Exécutez **[SDT](surface-diagnostic-toolkit-for-business-intro.md)** pour vérifier la fonctionnalité complète de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="469fd-165">Run **[SDT](surface-diagnostic-toolkit-for-business-intro.md)** to verify full device functionality.</span></span>  
10. <span data-ttu-id="469fd-166">Pour vérifier l’activation de Windows, sélectionnez activation des **paramètres**  >  **Activation**.</span><span class="sxs-lookup"><span data-stu-id="469fd-166">To check Windows activation, select **Settings** > **Activation**.</span></span>  <span data-ttu-id="469fd-167">Si un message d’erreur s’affiche, sélectionnez **résoudre les problèmes**.</span><span class="sxs-lookup"><span data-stu-id="469fd-167">If you see any error messages, select **Troubleshoot**.</span></span>
11. <span data-ttu-id="469fd-168">Pour vérifier l’état du compte Office, ouvrez l' **application Office**, puis accédez à compte de **fichier**  >  **Account** pour vérifier la présence de messages d’erreur.</span><span class="sxs-lookup"><span data-stu-id="469fd-168">To check the status of the Office account, open the **Office App**, then go to **File** > **Account** to check for any error messages.</span></span>

## <span data-ttu-id="469fd-169">En savoir plus</span><span class="sxs-lookup"><span data-stu-id="469fd-169">Learn more</span></span>

- [<span data-ttu-id="469fd-170">Guide de suppression de rSSD pour les entreprises</span><span class="sxs-lookup"><span data-stu-id="469fd-170">rSSD Removal Guide for Enterprise</span></span>](https://www.microsoft.com/download/100440)
- [<span data-ttu-id="469fd-171">Guide de récupération BitLocker</span><span class="sxs-lookup"><span data-stu-id="469fd-171">BitLocker Recovery Guide</span></span>](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)

<span data-ttu-id="469fd-172">Encore besoin d’aide?</span><span class="sxs-lookup"><span data-stu-id="469fd-172">Still need help?</span></span> <span data-ttu-id="469fd-173">Accédez à la [communauté Microsoft](https://answers.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="469fd-173">Go to [Microsoft Community](https://answers.microsoft.com/).</span></span>