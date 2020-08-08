---
title: Suppression de SSD dans des appareils surface compatibles
description: Comment transférer un SSD d’un périphérique surface à un autre.
ms.prod: w10
ms.localizationpriority: medium
ms.mktglfcycl: manage
ms.sitesec: library
author: mccoybot
ms.author: v-todmc
ms.topic: article
ms.date: 8/7/2020
ms.reviewer: johnk
manager: laurawi
ms.audience: itpro
audience: ITPro
appliesto:
- Surface Laptop 3
- Surface Pro X
ms.custom:
- CI 121887
- CSSTroubleshoot
ms.openlocfilehash: 9cde08c8106703b50218bf7f5ed60e3d7fea0b67
ms.sourcegitcommit: 83530906c7e34c92bbee90b723321acd61e77669
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/08/2020
ms.locfileid: "10918949"
---
# <span data-ttu-id="e496a-103">Recommandations en matière de suppression de SSD dans les appareils surface compatibles</span><span class="sxs-lookup"><span data-stu-id="e496a-103">Best practices for SSD removal in compatible Surface devices</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e496a-104">Cet article est destiné aux techniciens informatiques qualifiés au sein d’une organisation d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="e496a-104">This article is intended for use by qualified IT technicians in an enterprise organization only.</span></span> <span data-ttu-id="e496a-105">Il présente les meilleures pratiques recommandées pour les techniciens informatiques qualifiés lors de la suppression et du remplacement de SSDs dans des appareils surface dotés de SSDs amovible.</span><span class="sxs-lookup"><span data-stu-id="e496a-105">It describes the recommended best practices for use by qualified IT technicians when removing and replacing SSDs in Surface devices with removable SSDs.</span></span> 

> [!WARNING]
> <span data-ttu-id="e496a-106">L’ouverture de périphériques et le remplacement des composants de périphériques peuvent présenter un choc électrique, un dommage de l’appareil, un incendie, des risques liés au préjudice personnel et autres dangers.</span><span class="sxs-lookup"><span data-stu-id="e496a-106">Opening devices and replacing device components can present electric shock, device damage, fire, and personal injury risks, and other hazards.</span></span>  <span data-ttu-id="e496a-107">Soyez toujours prudent lorsque vous exercez de telles activités.</span><span class="sxs-lookup"><span data-stu-id="e496a-107">Always use caution when undertaking such activities.</span></span> <span data-ttu-id="e496a-108">Suivez les consignes et procédures de sécurité mentionnées dans le Guide de suppression de rSSD pour les entreprises.</span><span class="sxs-lookup"><span data-stu-id="e496a-108">Follow the safety precautions and procedures identified in the rSSD Removal Guide for Enterprise.</span></span> <span data-ttu-id="e496a-109">Microsoft vous recommande de rechercher une assistance technique si vous ne parvenez pas à suivre les consignes de sécurité et les procédures indiquées dans le Guide de suppression de rSSD pour les entreprises.</span><span class="sxs-lookup"><span data-stu-id="e496a-109">Microsoft recommends that you seek professional assistance if you are unable to follow the safety precautions and procedures specified in the rSSD Removal Guide for Enterprise.</span></span> 

## <span data-ttu-id="e496a-110">Prérequis</span><span class="sxs-lookup"><span data-stu-id="e496a-110">Prerequisites</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e496a-111">Cet article part du principe que vous comprenez les consignes générales en matière de sécurité et les procédures de sécurité décrites dans le [Guide de suppression d’rSSD pour les entreprises](https://www.microsoft.com/download/100440).</span><span class="sxs-lookup"><span data-stu-id="e496a-111">This article assumes you understand the General Safety Precautions and Safety policies and procedures described in [rSSD Removal Guide for Enterprise](https://www.microsoft.com/download/100440).</span></span>

## <span data-ttu-id="e496a-112">Préparer la suppression de votre microinstallation</span><span class="sxs-lookup"><span data-stu-id="e496a-112">Prepare for SSD removal</span></span> 

### <span data-ttu-id="e496a-113">Installer les mises à jour les plus récentes</span><span class="sxs-lookup"><span data-stu-id="e496a-113">Install the latest updates</span></span> 

<span data-ttu-id="e496a-114">Avant de commencer, assurez-vous que votre version de Windows dispose des dernières mises à jour.</span><span class="sxs-lookup"><span data-stu-id="e496a-114">Before you begin, make sure your version of Windows has the latest updates.</span></span>

1.  <span data-ttu-id="e496a-115">Accédez à **Start**  >  **Settings**  >  **mise à jour** des paramètres de démarrage & sécurité, puis sélectionnez **Rechercher les mises à jour**.</span><span class="sxs-lookup"><span data-stu-id="e496a-115">Go to **Start** > **Settings** > **Update & Security** and select **Check for updates**.</span></span> <span data-ttu-id="e496a-116">Installez toutes les mises à jour disponibles.</span><span class="sxs-lookup"><span data-stu-id="e496a-116">Install all available updates.</span></span>  

2.  <span data-ttu-id="e496a-117">Vérifiez que vous disposez des mots de passe nécessaires pour accéder à l’appareil.</span><span class="sxs-lookup"><span data-stu-id="e496a-117">Confirm that you have any passwords needed to access the device.</span></span>  
 
## <span data-ttu-id="e496a-118">Gérer BitLocker</span><span class="sxs-lookup"><span data-stu-id="e496a-118">Manage Bitlocker</span></span> 

> [!NOTE]
> <span data-ttu-id="e496a-119">Cette section contient des recommandations pour les organisations ayant activé le chiffrement BitLocker pour les disques durs.</span><span class="sxs-lookup"><span data-stu-id="e496a-119">This section includes recommendations for organizations that have enabled BitLocker encryption for hard drives.</span></span> <span data-ttu-id="e496a-120">Pour plus d’informations, voir le [Guide de récupération de BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan).</span><span class="sxs-lookup"><span data-stu-id="e496a-120">For more information, see the [BitLocker Recovery Guide](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan).</span></span> 

### <span data-ttu-id="e496a-121">Si le chiffrement BitLocker est désactivé lors de la suppression et du remplacement de disques durs</span><span class="sxs-lookup"><span data-stu-id="e496a-121">If BitLocker encryption is disabled during SSD removal and replacement</span></span>

<span data-ttu-id="e496a-122">Si l’appareil peut être déchiffré avant la suppression et le remplacement de votre appareil, procédez comme suit pour désactiver BitLocker:</span><span class="sxs-lookup"><span data-stu-id="e496a-122">If the device can be unencrypted before SSD removal and replacement, follow these steps to turn off BitLocker:</span></span>

1.  <span data-ttu-id="e496a-123">Dans **paramètres**, tapez **BitLocker** et sélectionnez **gérer BitLocker**.</span><span class="sxs-lookup"><span data-stu-id="e496a-123">In **Settings**, type **Bitlocker** and select **Manage Bitlocker**.</span></span> 
2.  <span data-ttu-id="e496a-124">Sélectionnez **Désactiver BitLocker**.</span><span class="sxs-lookup"><span data-stu-id="e496a-124">Select **Turn Off Bitlocker**.</span></span> 
3.  <span data-ttu-id="e496a-125">Allumez l’appareil.</span><span class="sxs-lookup"><span data-stu-id="e496a-125">Power down the device.</span></span> 

### <span data-ttu-id="e496a-126">Si le chiffrement BitLocker est activé lors de la suppression et du remplacement de disques durs</span><span class="sxs-lookup"><span data-stu-id="e496a-126">If BitLocker encryption is enabled during SSD removal and replacement</span></span>

<span data-ttu-id="e496a-127">Si l’appareil est chiffré avant la suppression et le remplacement de votre appareil, procédez comme suit pour générer une clé de récupération BitLocker et l’enregistrer dans le stockage USB:</span><span class="sxs-lookup"><span data-stu-id="e496a-127">If the device is encrypted before SSD removal and replacement, follow these steps to generate a BitLocker recovery key and save it to USB storage:</span></span>

1.  <span data-ttu-id="e496a-128">Accédez à **paramètres** et tapez **BitLocker**.</span><span class="sxs-lookup"><span data-stu-id="e496a-128">Go to **Settings** and type **Bitlocker**.</span></span>
2. <span data-ttu-id="e496a-129">Sélectionnez **gérer BitLocker**  > **générer la clé de récupération BitLocker**.</span><span class="sxs-lookup"><span data-stu-id="e496a-129">Select **Manage Bitlocker** >**Generate Bitlocker Recovery Key**.</span></span>
2.  <span data-ttu-id="e496a-130">Insérez un lecteur USB.</span><span class="sxs-lookup"><span data-stu-id="e496a-130">Insert a USB drive.</span></span> 
3.  <span data-ttu-id="e496a-131">Enregistrez la clé de récupération sur le stockage USB.</span><span class="sxs-lookup"><span data-stu-id="e496a-131">Save the recovery key to USB storage.</span></span>  
4.  <span data-ttu-id="e496a-132">Retirez le lecteur USB.</span><span class="sxs-lookup"><span data-stu-id="e496a-132">Remove the USB drive.</span></span>  
5.  <span data-ttu-id="e496a-133">Allumez l’appareil.</span><span class="sxs-lookup"><span data-stu-id="e496a-133">Power down the device.</span></span> 

## <span data-ttu-id="e496a-134">Supprimer et remplacer la SSD</span><span class="sxs-lookup"><span data-stu-id="e496a-134">Remove and replace the SSD</span></span> 

1.  <span data-ttu-id="e496a-135">Supprimez le SSD en suivant les instructions du [Guide de suppression de rSSD pour les entreprises](https://www.microsoft.com/download/100440).</span><span class="sxs-lookup"><span data-stu-id="e496a-135">Remove the SSD using the instructions in [rSSD Removal Guide for Enterprise](https://www.microsoft.com/download/100440).</span></span> 
2. <span data-ttu-id="e496a-136">Placez le fichier SSD d’origine sur un nouvel appareil et connectez le nouvel appareil à une connexion Internet câblée.</span><span class="sxs-lookup"><span data-stu-id="e496a-136">Place the original SSD in a new device and connect the new device to a wired internet connection.</span></span>
2.  <span data-ttu-id="e496a-137">Allumez le nouvel appareil.</span><span class="sxs-lookup"><span data-stu-id="e496a-137">Power on the new device.</span></span> <span data-ttu-id="e496a-138">Il est possible que l’appareil passe par une mise à jour du microprogramme lors du démarrage.</span><span class="sxs-lookup"><span data-stu-id="e496a-138">The device may go through a firmware update during startup.</span></span>  
 
## <span data-ttu-id="e496a-139">Après suppression et remplacement de disques durs</span><span class="sxs-lookup"><span data-stu-id="e496a-139">After SSD removal and replacement</span></span>

### <span data-ttu-id="e496a-140">Gérer les SSDs non chiffrés</span><span class="sxs-lookup"><span data-stu-id="e496a-140">Manage unencrypted SSDs</span></span> 

<span data-ttu-id="e496a-141">Si le SSD n’est toujours pas chiffré lors du transfert, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="e496a-141">If the SSD remains unencrypted during the transfer, complete the following:</span></span> 

1.  <span data-ttu-id="e496a-142">Accédez à **options de connexion**  >  **mot de passe** (représenté par une icône de clé située sur le côté gauche).</span><span class="sxs-lookup"><span data-stu-id="e496a-142">Go to **Sign-In Options** > **Password** (represented as the key icon on the left side).</span></span>  
2.  <span data-ttu-id="e496a-143">Entrez le mot de passe et connectez-vous en attente d’exécution de l’authentification à deux facteurs (le cas échéant).</span><span class="sxs-lookup"><span data-stu-id="e496a-143">Enter the password and sign in pending completion of two-factor authentication (if applicable).</span></span>
3.  <span data-ttu-id="e496a-144">Une fois que vous êtes connecté, **accédez à la**  >  **Account**  >  **déconnexion**de votre compte.</span><span class="sxs-lookup"><span data-stu-id="e496a-144">Once fully signed in, go to **Start** > **Account** > **Sign out**.</span></span>  
4.  <span data-ttu-id="e496a-145">Reconnectez-vous à l’aide du mot de passe et configurez Windows Hello et un code confidentiel lorsque vous y êtes invité.</span><span class="sxs-lookup"><span data-stu-id="e496a-145">Sign back in with the password and set up Windows Hello and a PIN when prompted.</span></span> 
    - <span data-ttu-id="e496a-146">Si l’appareil a été désactivé par BitLocker pour faciliter la suppression et le remplacement de disques durs et que vous souhaitez activer BitLocker après le remplacement, accédez à **BitLocker**  >  **Manage BitLocker**  >  **Resume BitLocker**.</span><span class="sxs-lookup"><span data-stu-id="e496a-146">If the device was BitLocker-disabled to facilitate SSD removal and replacement and you want to enable BitLocker after the replacement, go to **Bitlocker** > **Manage Bitlocker** > **Resume Bitlocker**.</span></span>  
6.  <span data-ttu-id="e496a-147">Exécutez **SDT** pour confirmer la fonctionnalité complète de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="e496a-147">Run **SDT** to confirm full device functionality.</span></span>  
7.  <span data-ttu-id="e496a-148">Recherchez l’activation de Windows en accédant à activation des **paramètres**  >  **Activation**.</span><span class="sxs-lookup"><span data-stu-id="e496a-148">Check for Windows activation by navigating to **Settings** > **Activation**.</span></span>  <span data-ttu-id="e496a-149">S’il y a des messages d’erreur, sélectionnez **résoudre les problèmes**.</span><span class="sxs-lookup"><span data-stu-id="e496a-149">If there are any error messages, select **Troubleshoot**.</span></span> 
8.  <span data-ttu-id="e496a-150">Vérifiez le compte Office en ouvrant l' **application Office**, puis accédez à **File**  >  **compte** de fichier et recherchez les messages d’erreur.</span><span class="sxs-lookup"><span data-stu-id="e496a-150">Check the Office account by opening the **Office App**, then navigate to **File** > **Account** and check for any error messages.</span></span>  

### <span data-ttu-id="e496a-151">Gestion des SSDs chiffrés</span><span class="sxs-lookup"><span data-stu-id="e496a-151">Managing encrypted SSDs</span></span> 

> [!NOTE]
> <span data-ttu-id="e496a-152">Vous aurez besoin d’un deuxième appareil pour lire la clé de récupération BitLocker qui a été enregistrée sur le lecteur USB.</span><span class="sxs-lookup"><span data-stu-id="e496a-152">You will need a second device to read the BitLocker Recovery key that was saved on the USB drive.</span></span> 

<span data-ttu-id="e496a-153">Si le SSD est resté crypté lors du transfert, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="e496a-153">If the SSD remained encrypted during the transfer, complete the following:</span></span>

1.  <span data-ttu-id="e496a-154">Insérez le lecteur USB contenant la clé de récupération BitLocker dans le second appareil.</span><span class="sxs-lookup"><span data-stu-id="e496a-154">Insert the USB drive containing the Bitlocker Recovery key into the second device.</span></span> 
2.  <span data-ttu-id="e496a-155">Ouvrez le fichier. txt contenant la clé de récupération BitLocker.</span><span class="sxs-lookup"><span data-stu-id="e496a-155">Open the .txt file containing the Bitlocker Recovery key.</span></span> 
3.  <span data-ttu-id="e496a-156">Entrez manuellement la clé de récupération BitLocker dans le nouvel appareil qui contient la clé SSD d’origine.</span><span class="sxs-lookup"><span data-stu-id="e496a-156">Manually enter the Bitlocker Recovery key into the new device that contains the original SSD.</span></span>  
4.  <span data-ttu-id="e496a-157">Après avoir entré la clé de récupération BitLocker, accédez au mot de passe des **options de connexion**  >  **Password** (représenté par l’icône de clé située sur le côté gauche).</span><span class="sxs-lookup"><span data-stu-id="e496a-157">After you have successfully entered the BitLocker Recovery key, go to **Sign-In Options** > **Password** (represented by the key icon on the left side).</span></span>  
5.  <span data-ttu-id="e496a-158">Entrez le mot de passe et connectez-vous en attente d’exécution de l’authentification à deux facteurs (le cas échéant).</span><span class="sxs-lookup"><span data-stu-id="e496a-158">Enter the password and sign in, pending completion of two-factor authentication (if applicable)</span></span> 
6.  <span data-ttu-id="e496a-159">Une fois que vous êtes connecté, **accédez à la**  >  **Account**  >  **déconnexion**de votre compte.</span><span class="sxs-lookup"><span data-stu-id="e496a-159">Once fully signed in, go to **Start** > **Account** > **Sign out**.</span></span>  
7.  <span data-ttu-id="e496a-160">Reconnectez-vous à l’aide du mot de passe et configurez Windows Hello et ajoutez un code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="e496a-160">Sign back in with the password and set up Windows Hello and add a PIN.</span></span> 
8.  <span data-ttu-id="e496a-161">Si l’appareil a été désactivé par BitLocker pour faciliter la suppression et le remplacement de disques durs et que vous souhaitez activer BitLocker après le remplacement, accédez à **paramètres**  >  **BitLocker**  >  **gérer**BitLocker-  >  **reprise**BitLocker.</span><span class="sxs-lookup"><span data-stu-id="e496a-161">If the device was BitLocker-disabled to facilitate SSD removal and replacement, and you want to enable BitLocker after the replacement, go to to **Settings** > **Bitlocker** > **Manage Bitlocker** > **Resume Bitlocker**.</span></span>  
9.  <span data-ttu-id="e496a-162">Exécutez **SDT** pour confirmer la fonctionnalité complète de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="e496a-162">Run **SDT** to confirm full device functionality.</span></span>  
10. <span data-ttu-id="e496a-163">Vérifiez l’activation de Windows en accédant à activation des **paramètres**  >  **Activation**.</span><span class="sxs-lookup"><span data-stu-id="e496a-163">Check Windows activation by navigating to **Settings** > **Activation**.</span></span>  <span data-ttu-id="e496a-164">S’il y a des messages d’erreur, sélectionnez **résoudre les problèmes**.</span><span class="sxs-lookup"><span data-stu-id="e496a-164">If there are any error messages, select **Troubleshoot**.</span></span>
11. <span data-ttu-id="e496a-165">Pour vérifier le compte Office, ouvrez l' **application Office**, puis accédez à **File**  >  **compte** de fichier et recherchez les messages d’erreur.</span><span class="sxs-lookup"><span data-stu-id="e496a-165">To check the Office Account, open the **Office App**, then go to **File** > **Account** and check for any error messages.</span></span>

## <span data-ttu-id="e496a-166">Informations supplémentaires</span><span class="sxs-lookup"><span data-stu-id="e496a-166">More information</span></span> 

<span data-ttu-id="e496a-167">Pour plus d’informations, consultez les articles suivants:</span><span class="sxs-lookup"><span data-stu-id="e496a-167">For more information, see the following articles:</span></span>

- [<span data-ttu-id="e496a-168">Guide de suppression de rSSD pour les entreprises</span><span class="sxs-lookup"><span data-stu-id="e496a-168">rSSD Removal Guide for Enterprise</span></span>](https://www.microsoft.com/download/100440)
- [<span data-ttu-id="e496a-169">Guide de récupération BitLocker</span><span class="sxs-lookup"><span data-stu-id="e496a-169">BitLocker Recovery Guide</span></span>](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)

<span data-ttu-id="e496a-170">Encore besoin d’aide?</span><span class="sxs-lookup"><span data-stu-id="e496a-170">Still need help?</span></span> <span data-ttu-id="e496a-171">Accédez à la [communauté Microsoft](https://answers.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="e496a-171">Go to [Microsoft Community](https://answers.microsoft.com/).</span></span>