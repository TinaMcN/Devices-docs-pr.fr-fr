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
ms.openlocfilehash: 66860af06f4fad8f19ca26702350f19cc85ffef1
ms.sourcegitcommit: bad416f04c6877f2200f134a69146bb633155f22
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/10/2020
ms.locfileid: "10919223"
---
# <span data-ttu-id="78640-103">Recommandations en matière de suppression de disques durs de périphériques de surface compatibles</span><span class="sxs-lookup"><span data-stu-id="78640-103">Best practices for SSD removal from compatible Surface devices</span></span>

> [!IMPORTANT]
> <span data-ttu-id="78640-104">Cet article est destiné aux techniciens informatiques qualifiés au sein d’une organisation d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="78640-104">This article is intended for use by qualified IT technicians in an enterprise organization only.</span></span> <span data-ttu-id="78640-105">Il présente les meilleures pratiques recommandées pour les techniciens informatiques qualifiés lors de la suppression et du remplacement de SSDs dans des appareils surface dotés de SSDs amovible.</span><span class="sxs-lookup"><span data-stu-id="78640-105">It describes the recommended best practices for use by qualified IT technicians when they remove and replace SSDs in Surface devices that have removable SSDs.</span></span> 

> [!WARNING]
> <span data-ttu-id="78640-106">L’ouverture de périphériques et le remplacement des composants de périphériques peuvent présenter un choc électrique, un dommage de l’appareil, un incendie, des risques liés au préjudice personnel et autres dangers.</span><span class="sxs-lookup"><span data-stu-id="78640-106">Opening devices and replacing device components can present electric shock, device damage, fire, and personal injury risks, and other hazards.</span></span>  <span data-ttu-id="78640-107">Soyez toujours prudent lorsque vous exercez de telles activités.</span><span class="sxs-lookup"><span data-stu-id="78640-107">Always use caution when you undertake such activities.</span></span> <span data-ttu-id="78640-108">Suivez les consignes et procédures de sécurité qui sont identifiées dans le [Guide de suppression de rSSD pour les entreprises](https://www.microsoft.com/download/100440).</span><span class="sxs-lookup"><span data-stu-id="78640-108">Follow the safety precautions and procedures that are identified in the [rSSD Removal Guide for Enterprise](https://www.microsoft.com/download/100440).</span></span> <span data-ttu-id="78640-109">Nous vous recommandons d’obtenir une assistance technique si vous ne pouvez pas suivre les consignes de sécurité et les procédures indiquées dans le Guide de suppression de rSSD pour les entreprises.</span><span class="sxs-lookup"><span data-stu-id="78640-109">We recommend that you get professional assistance if you cannot follow the safety precautions and procedures that are specified in the "rSSD Removal Guide for Enterprise."</span></span>

## <span data-ttu-id="78640-110">Prérequis</span><span class="sxs-lookup"><span data-stu-id="78640-110">Prerequisites</span></span>

> [!IMPORTANT]
> <span data-ttu-id="78640-111">Cet article part du principe que vous comprenez les consignes générales en matière de sécurité et les stratégies et procédures de sécurité décrites dans le «Guide de suppression rSSD pour les entreprises».</span><span class="sxs-lookup"><span data-stu-id="78640-111">This article assumes that you understand the General Safety Precautions and Safety policies and procedures that are described in the "rSSD Removal Guide for Enterprise."</span></span>

## <span data-ttu-id="78640-112">Préparer la suppression de votre microinstallation</span><span class="sxs-lookup"><span data-stu-id="78640-112">Prepare for SSD removal</span></span> 

### <span data-ttu-id="78640-113">Installer les mises à jour les plus récentes</span><span class="sxs-lookup"><span data-stu-id="78640-113">Install the latest updates</span></span> 

<span data-ttu-id="78640-114">Avant de commencer, assurez-vous que votre version de Windows comporte les mises à jour les plus récentes:</span><span class="sxs-lookup"><span data-stu-id="78640-114">Before you begin, make sure that your version of Windows has the latest updates intalled:</span></span>

1.  <span data-ttu-id="78640-115">Accédez à **Start**  >  **Settings**  >  **mise à jour**des paramètres de démarrage & sécurité, puis sélectionnez **Rechercher les mises à jour**.</span><span class="sxs-lookup"><span data-stu-id="78640-115">Go to **Start** > **Settings** > **Update & Security**, and select **Check for updates**.</span></span> <span data-ttu-id="78640-116">Installez toutes les mises à jour disponibles.</span><span class="sxs-lookup"><span data-stu-id="78640-116">Install all available updates.</span></span> 
2. <span data-ttu-id="78640-117">Installez toutes les mises à jour disponibles.</span><span class="sxs-lookup"><span data-stu-id="78640-117">Install all available updates.</span></span>
3. <span data-ttu-id="78640-118">Vérifiez que vous disposez des mots de passe nécessaires pour accéder à l’appareil.</span><span class="sxs-lookup"><span data-stu-id="78640-118">Verify that you have any passwords that are necessary to access the device.</span></span>  
 
## <span data-ttu-id="78640-119">Gérer BitLocker</span><span class="sxs-lookup"><span data-stu-id="78640-119">Manage BitLocker</span></span> 

> [!NOTE]
> <span data-ttu-id="78640-120">Cette section contient des recommandations pour les organisations ayant activé le chiffrement BitLocker pour les disques durs.</span><span class="sxs-lookup"><span data-stu-id="78640-120">This section includes recommendations for organizations that have enabled BitLocker encryption for hard disks.</span></span> <span data-ttu-id="78640-121">Pour plus d’informations, voir le [Guide de récupération de BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan).</span><span class="sxs-lookup"><span data-stu-id="78640-121">For more information, see the [BitLocker Recovery Guide](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan).</span></span> 

### <span data-ttu-id="78640-122">Si le chiffrement BitLocker est désactivé lors de la suppression et du remplacement de disques durs</span><span class="sxs-lookup"><span data-stu-id="78640-122">If BitLocker encryption is disabled during SSD removal and replacement</span></span>

<span data-ttu-id="78640-123">Si l’appareil peut être déchiffré avant la suppression et le remplacement de votre appareil, procédez comme suit pour désactiver BitLocker:</span><span class="sxs-lookup"><span data-stu-id="78640-123">If the device can be unencrypted before SSD removal and replacement, follow these steps to turn off BitLocker:</span></span>

1.  <span data-ttu-id="78640-124">Dans **paramètres**, tapez **BitLocker**, puis sélectionnez **gérer BitLocker**.</span><span class="sxs-lookup"><span data-stu-id="78640-124">In **Settings**, type **Bitlocker**, and then select **Manage Bitlocker**.</span></span> 
2.  <span data-ttu-id="78640-125">Sélectionnez **Désactiver BitLocker**.</span><span class="sxs-lookup"><span data-stu-id="78640-125">Select **Turn Off Bitlocker**.</span></span> 
3.  <span data-ttu-id="78640-126">Allumez l’appareil.</span><span class="sxs-lookup"><span data-stu-id="78640-126">Power down the device.</span></span> 

### <span data-ttu-id="78640-127">Si le chiffrement BitLocker est activé lors de la suppression et du remplacement de disques durs</span><span class="sxs-lookup"><span data-stu-id="78640-127">If BitLocker encryption is enabled during SSD removal and replacement</span></span>

<span data-ttu-id="78640-128">Si l’appareil est chiffré avant la suppression et le remplacement de votre appareil, procédez comme suit pour générer une clé de récupération BitLocker et l’enregistrer dans le stockage USB:</span><span class="sxs-lookup"><span data-stu-id="78640-128">If the device is encrypted before SSD removal and replacement, follow these steps to generate a BitLocker recovery key and save it to USB storage:</span></span>

1.  <span data-ttu-id="78640-129">Dans **paramètres**, tapez **BitLocker**.</span><span class="sxs-lookup"><span data-stu-id="78640-129">In **Settings**, type **Bitlocker**.</span></span>
2. <span data-ttu-id="78640-130">Sélectionnez **gérer BitLocker**  > **générer la clé de récupération BitLocker**.</span><span class="sxs-lookup"><span data-stu-id="78640-130">Select **Manage Bitlocker** >**Generate Bitlocker Recovery Key**.</span></span>
2.  <span data-ttu-id="78640-131">Insérez un lecteur USB.</span><span class="sxs-lookup"><span data-stu-id="78640-131">Insert a USB drive.</span></span> 
3.  <span data-ttu-id="78640-132">Enregistrez la clé de récupération sur le stockage USB.</span><span class="sxs-lookup"><span data-stu-id="78640-132">Save the recovery key to USB storage.</span></span>  
4.  <span data-ttu-id="78640-133">Retirez le lecteur USB.</span><span class="sxs-lookup"><span data-stu-id="78640-133">Remove the USB drive.</span></span>  
5.  <span data-ttu-id="78640-134">Allumez l’appareil.</span><span class="sxs-lookup"><span data-stu-id="78640-134">Power down the device.</span></span> 

## <span data-ttu-id="78640-135">Supprimer et remplacer la SSD</span><span class="sxs-lookup"><span data-stu-id="78640-135">Remove and replace the SSD</span></span> 

1.  <span data-ttu-id="78640-136">Supprimez le SSD en suivant les instructions du [Guide de suppression de rSSD pour les entreprises](https://www.microsoft.com/download/100440).</span><span class="sxs-lookup"><span data-stu-id="78640-136">Remove the SSD by using the instructions in [rSSD Removal Guide for Enterprise](https://www.microsoft.com/download/100440).</span></span> 
2. <span data-ttu-id="78640-137">Placez le fichier SSD d’origine dans un nouvel appareil et connectez le nouvel appareil à une connexion Internet câblée.</span><span class="sxs-lookup"><span data-stu-id="78640-137">Put the original SSD into a new device, and connect the new device to a wired internet connection.</span></span>
2.  <span data-ttu-id="78640-138">Allumez le nouvel appareil.</span><span class="sxs-lookup"><span data-stu-id="78640-138">Power on the new device.</span></span> <span data-ttu-id="78640-139">Il est possible que l’appareil passe par une mise à jour du microprogramme lors du démarrage.</span><span class="sxs-lookup"><span data-stu-id="78640-139">The device may go through a firmware update during startup.</span></span>  
 
## <span data-ttu-id="78640-140">Après suppression et remplacement de disques durs</span><span class="sxs-lookup"><span data-stu-id="78640-140">After SSD removal and replacement</span></span>

### <span data-ttu-id="78640-141">Gérer les SSDs non chiffrés</span><span class="sxs-lookup"><span data-stu-id="78640-141">Manage unencrypted SSDs</span></span> 

<span data-ttu-id="78640-142">Si le SSD n’est toujours pas chiffré lors du transfert, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="78640-142">If the SSD remains unencrypted during the transfer, follow these steps:</span></span> 

1.  <span data-ttu-id="78640-143">Accédez à **options de connexion**  >  **mot de passe** (représenté par l’icône de clé située sur le côté gauche).</span><span class="sxs-lookup"><span data-stu-id="78640-143">Go to **Sign-In Options** > **Password** (represented by the key icon on the left side).</span></span>  
2.  <span data-ttu-id="78640-144">Entrez le mot de passe, puis connectez-vous en attente d’exécution de l’authentification à deux facteurs (le cas échéant).</span><span class="sxs-lookup"><span data-stu-id="78640-144">Enter the password, and sign in pending completion of two-factor authentication (if applicable).</span></span>
3.  <span data-ttu-id="78640-145">Une fois que vous êtes connecté, **accédez à la**  >  **Account**  >  **déconnexion**de votre compte.</span><span class="sxs-lookup"><span data-stu-id="78640-145">After you are fully signed in, go to **Start** > **Account** > **Sign out**.</span></span>  
4.  <span data-ttu-id="78640-146">Reconnectez-vous à l’aide du mot de passe, puis configurez Windows Hello et un code confidentiel lorsque vous y êtes invité.</span><span class="sxs-lookup"><span data-stu-id="78640-146">Sign back in by using the password, and set up Windows Hello and a PIN when you are prompted.</span></span> 
    - <span data-ttu-id="78640-147">Si l’appareil a été désactivé par BitLocker pour faciliter la suppression et le remplacement de disques durs et que vous souhaitez activer BitLocker après le remplacement, accédez à **BitLocker**  >  **Manage BitLocker**  >  **Resume BitLocker**.</span><span class="sxs-lookup"><span data-stu-id="78640-147">If the device was BitLocker-disabled to facilitate SSD removal and replacement, and you want to enable BitLocker after the replacement, go to **Bitlocker** > **Manage Bitlocker** > **Resume Bitlocker**.</span></span>  
6.  <span data-ttu-id="78640-148">Exécutez le kit de connaissances Microsoft surface diagnostic pour les entreprises (SDT) pour vérifier le fonctionnement complet de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="78640-148">Run the Microsoft Surface Diagnostic Toolkit for Business (SDT) to verify full device functionality.</span></span>  
7.  <span data-ttu-id="78640-149">Recherchez l’activation de Windows en accédant à activation des **paramètres**  >  **Activation**.</span><span class="sxs-lookup"><span data-stu-id="78640-149">Check for Windows activation by navigating to **Settings** > **Activation**.</span></span>  <span data-ttu-id="78640-150">Si un message d’erreur s’affiche, sélectionnez **résoudre les problèmes**.</span><span class="sxs-lookup"><span data-stu-id="78640-150">If you see any error messages, select **Troubleshoot**.</span></span> 
8.  <span data-ttu-id="78640-151">Pour vérifier le compte Office, ouvrez l' **application Office**, accédez au compte de **fichier**,  >  **Account** puis recherchez les messages d’erreur.</span><span class="sxs-lookup"><span data-stu-id="78640-151">Check the Office account by opening the **Office App**, navigate to **File** > **Account** and then check for any error messages.</span></span>  

### <span data-ttu-id="78640-152">Gestion des SSDs chiffrés</span><span class="sxs-lookup"><span data-stu-id="78640-152">Managing encrypted SSDs</span></span> 

> [!NOTE]
> <span data-ttu-id="78640-153">Vous devez disposer d’un deuxième appareil pour lire la clé de récupération BitLocker qui a été enregistrée sur le lecteur USB.</span><span class="sxs-lookup"><span data-stu-id="78640-153">You will have to have a second device to read the BitLocker Recovery key that was saved on the USB drive.</span></span> 

<span data-ttu-id="78640-154">Si le SSD est resté crypté pendant le transfert, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="78640-154">If the SSD remained encrypted during the transfer, follow these steps:</span></span>

1.  <span data-ttu-id="78640-155">Insérez le lecteur USB contenant la clé de récupération BitLocker dans le second appareil.</span><span class="sxs-lookup"><span data-stu-id="78640-155">Insert the USB drive that contains the Bitlocker recovery key into the second device.</span></span> 
2.  <span data-ttu-id="78640-156">Ouvrez le fichier. txt contenant la clé de récupération BitLocker.</span><span class="sxs-lookup"><span data-stu-id="78640-156">Open the .txt file that contains the Bitlocker recovery key.</span></span> 
3.  <span data-ttu-id="78640-157">Entrez manuellement la clé de récupération BitLocker sur le nouvel appareil contenant la clé SSD d’origine.</span><span class="sxs-lookup"><span data-stu-id="78640-157">Manually enter the Bitlocker recovery key on the new device that contains the original SSD.</span></span>  
4.  <span data-ttu-id="78640-158">Après avoir entré la clé de récupération BitLocker, accédez au mot de passe des **options de connexion**  >  **Password** (représenté par l’icône de clé située sur le côté gauche).</span><span class="sxs-lookup"><span data-stu-id="78640-158">After you have successfully entered the BitLocker recovery key, go to **Sign-In Options** > **Password** (represented by the key icon on the left side).</span></span>  
5.  <span data-ttu-id="78640-159">Entrez le mot de passe et connectez-vous en attente d’exécution de l’authentification à deux facteurs (le cas échéant).</span><span class="sxs-lookup"><span data-stu-id="78640-159">Enter the password and sign in, pending completion of two-factor authentication (if applicable).</span></span>
6.  <span data-ttu-id="78640-160">Une fois que vous êtes connecté, **accédez à la**  >  **Account**  >  **déconnexion**de votre compte.</span><span class="sxs-lookup"><span data-stu-id="78640-160">After you are fully signed in, go to **Start** > **Account** > **Sign out**.</span></span>  
7.  <span data-ttu-id="78640-161">Reconnectez-vous à l’aide du mot de passe, puis configurez Windows Hello et ajoutez un code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="78640-161">Sign back in by using the password, and then set up Windows Hello and add a PIN.</span></span> 
8.  <span data-ttu-id="78640-162">Si l’appareil a été désactivé par BitLocker pour faciliter la suppression et le remplacement de disques durs, et si vous souhaitez activer BitLocker après le remplacement, accédez à **paramètres**  >  **BitLocker**  >  **gérer**BitLocker-  >  **reprise**BitLocker.</span><span class="sxs-lookup"><span data-stu-id="78640-162">If the device was BitLocker-disabled to facilitate SSD removal and replacement, and if you want to enable BitLocker after the replacement, go to **Settings** > **Bitlocker** > **Manage Bitlocker** > **Resume Bitlocker**.</span></span>  
9.  <span data-ttu-id="78640-163">Exécutez **SDT** pour vérifier la fonctionnalité complète de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="78640-163">Run **SDT** to verify full device functionality.</span></span>  
10. <span data-ttu-id="78640-164">Vérifiez l’activation de Windows en accédant à activation des **paramètres**  >  **Activation**.</span><span class="sxs-lookup"><span data-stu-id="78640-164">Check Windows activation by navigating to **Settings** > **Activation**.</span></span>  <span data-ttu-id="78640-165">Si un message d’erreur s’affiche, sélectionnez **résoudre les problèmes**.</span><span class="sxs-lookup"><span data-stu-id="78640-165">If you see any error messages, select **Troubleshoot**.</span></span>
11. <span data-ttu-id="78640-166">Pour vérifier l’état du compte Office, ouvrez l' **application Office**, puis accédez à compte de **fichier**  >  **Account** pour vérifier la présence de messages d’erreur.</span><span class="sxs-lookup"><span data-stu-id="78640-166">To check the status of the Office account, open the **Office App**, then go to **File** > **Account** to check for any error messages.</span></span>

## <span data-ttu-id="78640-167">Informations supplémentaires</span><span class="sxs-lookup"><span data-stu-id="78640-167">More information</span></span> 

<span data-ttu-id="78640-168">Pour plus d’informations, consultez les articles suivants:</span><span class="sxs-lookup"><span data-stu-id="78640-168">For more information, see the following articles:</span></span>

- [<span data-ttu-id="78640-169">Guide de suppression de rSSD pour les entreprises</span><span class="sxs-lookup"><span data-stu-id="78640-169">rSSD Removal Guide for Enterprise</span></span>](https://www.microsoft.com/download/100440)
- [<span data-ttu-id="78640-170">Guide de récupération BitLocker</span><span class="sxs-lookup"><span data-stu-id="78640-170">BitLocker Recovery Guide</span></span>](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)

<span data-ttu-id="78640-171">Encore besoin d’aide?</span><span class="sxs-lookup"><span data-stu-id="78640-171">Still need help?</span></span> <span data-ttu-id="78640-172">Accédez à la [communauté Microsoft](https://answers.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="78640-172">Go to [Microsoft Community](https://answers.microsoft.com/).</span></span>