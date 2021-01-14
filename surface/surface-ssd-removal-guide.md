---
title: Suppression du SSD sur les appareils Surface compatibles
description: Cet article, destiné aux techniciens informatiques qualifiés, décrit les meilleures pratiques recommandées pour la suppression et le remplacement de SSD dans Surface Laptop 3, Surface Pro X et Surface Laptop Go.
ms.prod: w10
ms.localizationpriority: medium
ms.mktglfcycl: manage
ms.sitesec: library
author: mccoybot
ms.author: v-todmc
ms.topic: article
ms.date: 01/13/2020
ms.reviewer: ''
manager: laurawi
ms.audience: itpro
audience: ITPro
appliesto:
- Surface Pro 7+
- Surface Pro X
- Surface Laptop Go
- Surface Laptop 3
ms.custom:
- CI 121887
- CSSTroubleshoot
ms.openlocfilehash: b65feb24803311aba809819cd6da273ed6934c75
ms.sourcegitcommit: 41124d496abaa38a0d989159f2afec3542d562ca
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/14/2021
ms.locfileid: "11269105"
---
# <span data-ttu-id="e972e-103">Meilleures pratiques pour la suppression de SSD des appareils Surface compatibles</span><span class="sxs-lookup"><span data-stu-id="e972e-103">Best practices for SSD removal from compatible Surface devices</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e972e-104">Cet article est destiné uniquement aux techniciens informatiques qualifiés d’une organisation d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="e972e-104">This article is intended for use by qualified IT technicians in an enterprise organization only.</span></span> <span data-ttu-id="e972e-105">Il décrit les meilleures pratiques recommandées pour une utilisation par des techniciens informatiques qualifiés lors de la suppression et du remplacement de SSD sur les appareils Surface compatibles suivants :</span><span class="sxs-lookup"><span data-stu-id="e972e-105">It describes the recommended best practices for use by qualified IT technicians in the removal and replacement of SSDs in the following compatible Surface devices:</span></span> 

- <span data-ttu-id="e972e-106">Surface Pro 7+</span><span class="sxs-lookup"><span data-stu-id="e972e-106">Surface Pro 7+</span></span>
- <span data-ttu-id="e972e-107">SurfaceProX</span><span class="sxs-lookup"><span data-stu-id="e972e-107">Surface Pro X</span></span>
- <span data-ttu-id="e972e-108">Surface Laptop Go</span><span class="sxs-lookup"><span data-stu-id="e972e-108">Surface Laptop Go</span></span>
- <span data-ttu-id="e972e-109">Surface Laptop3</span><span class="sxs-lookup"><span data-stu-id="e972e-109">Surface Laptop 3</span></span>

> [!WARNING]
> <span data-ttu-id="e972e-110">L’ouverture d’appareils et le remplacement des composants de l’appareil peuvent présenter une catastrophe électrique, des dommages de l’appareil, des incendies et des risques personnels, ainsi que d’autres risques.</span><span class="sxs-lookup"><span data-stu-id="e972e-110">Opening devices and replacing device components can present electric shock, device damage, fire, and personal injury risks, and other hazards.</span></span>  <span data-ttu-id="e972e-111">Faites toujours preuve de prudence lorsque vous entreprenons de telles activités.</span><span class="sxs-lookup"><span data-stu-id="e972e-111">Always use caution when you undertake such activities.</span></span> <span data-ttu-id="e972e-112">Suivez les précautions et procédures de sécurité identifiées dans le Guide de suppression [rSSD pour Entreprise.](https://www.microsoft.com/download/100440)</span><span class="sxs-lookup"><span data-stu-id="e972e-112">Follow the safety precautions and procedures that are identified in the [rSSD Removal Guide for Enterprise](https://www.microsoft.com/download/100440).</span></span> <span data-ttu-id="e972e-113">Nous vous recommandons d’obtenir une assistance professionnelle si vous ne pouvez pas suivre les précautions et procédures de sécurité spécifiées dans le « Guide de suppression rSSD pour entreprise ».</span><span class="sxs-lookup"><span data-stu-id="e972e-113">We recommend that you get professional assistance if you cannot follow the safety precautions and procedures that are specified in the "rSSD Removal Guide for Enterprise."</span></span>

## <span data-ttu-id="e972e-114">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="e972e-114">Prerequisites</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e972e-115">Cet article suppose que vous comprenez les stratégies et procédures générales de sécurité et de sécurité décrites dans le « Guide de suppression rSSD pour entreprise ».</span><span class="sxs-lookup"><span data-stu-id="e972e-115">This article assumes that you understand the General Safety Precautions and Safety policies and procedures that are described in the "rSSD Removal Guide for Enterprise."</span></span>

## <span data-ttu-id="e972e-116">Préparer la suppression de SSD</span><span class="sxs-lookup"><span data-stu-id="e972e-116">Prepare for SSD removal</span></span> 

### <span data-ttu-id="e972e-117">Installer les dernières mises à jour</span><span class="sxs-lookup"><span data-stu-id="e972e-117">Install the latest updates</span></span> 

<span data-ttu-id="e972e-118">Avant de commencer, assurez-vous que les dernières mises à jour de votre version de Windows sont installées :</span><span class="sxs-lookup"><span data-stu-id="e972e-118">Before you begin, make sure that your version of Windows has the latest updates installed:</span></span>

1.  <span data-ttu-id="e972e-119">Go to **Start**  >  **Settings**  >  **Update & Security,** and select Check for **updates**.</span><span class="sxs-lookup"><span data-stu-id="e972e-119">Go to **Start** > **Settings** > **Update & Security**, and select **Check for updates**.</span></span>
2. <span data-ttu-id="e972e-120">Installez toutes les mises à jour disponibles.</span><span class="sxs-lookup"><span data-stu-id="e972e-120">Install all available updates.</span></span>
3. <span data-ttu-id="e972e-121">Vérifiez les mots de passe nécessaires pour accéder à l’appareil.</span><span class="sxs-lookup"><span data-stu-id="e972e-121">Verify any passwords that are necessary to access the device.</span></span>  
 
## <span data-ttu-id="e972e-122">Gérer BitLocker</span><span class="sxs-lookup"><span data-stu-id="e972e-122">Manage BitLocker</span></span> 

> [!NOTE]
> <span data-ttu-id="e972e-123">Cette section contient des recommandations pour les organisations qui ont activé le chiffrement BitLocker pour les disques durs.</span><span class="sxs-lookup"><span data-stu-id="e972e-123">This section includes recommendations for organizations that have enabled BitLocker encryption for hard disks.</span></span> <span data-ttu-id="e972e-124">Pour plus d’informations, [voir le Guide de récupération BitLocker.](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)</span><span class="sxs-lookup"><span data-stu-id="e972e-124">For more information, see  [BitLocker Recovery Guide](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan).</span></span> 

### <span data-ttu-id="e972e-125">Si le chiffrement BitLocker est désactivé lors de la suppression et du remplacement de SSD</span><span class="sxs-lookup"><span data-stu-id="e972e-125">If BitLocker encryption is disabled during SSD removal and replacement</span></span>

<span data-ttu-id="e972e-126">Si l’appareil peut être déchiffré avant la suppression et le remplacement de SSD, suivez les étapes suivantes pour désactiver BitLocker :</span><span class="sxs-lookup"><span data-stu-id="e972e-126">If the device can be unencrypted before SSD removal and replacement, follow these steps to turn off BitLocker:</span></span>

1.  <span data-ttu-id="e972e-127">Dans **Paramètres,** **tapez BitLocker,** puis **sélectionnez Gérer BitLocker.**</span><span class="sxs-lookup"><span data-stu-id="e972e-127">In **Settings**, type **BitLocker** and then select **Manage BitLocker**.</span></span> 
2.  <span data-ttu-id="e972e-128">Sélectionnez **Désactiver BitLocker.**</span><span class="sxs-lookup"><span data-stu-id="e972e-128">Select **Turn Off BitLocker**.</span></span> 
3.  <span data-ttu-id="e972e-129">Alimentation de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="e972e-129">Power down the device.</span></span> 

### <span data-ttu-id="e972e-130">Si le chiffrement BitLocker est activé lors de la suppression et du remplacement de SSD</span><span class="sxs-lookup"><span data-stu-id="e972e-130">If BitLocker encryption is enabled during SSD removal and replacement</span></span>

<span data-ttu-id="e972e-131">Si l’appareil est chiffré avant la suppression et le remplacement de SSD, suivez ces étapes pour générer une clé de récupération BitLocker et l’enregistrer sur le stockage USB :</span><span class="sxs-lookup"><span data-stu-id="e972e-131">If the device is encrypted before SSD removal and replacement, follow these steps to generate a BitLocker recovery key and save it to USB storage:</span></span>

1.  <span data-ttu-id="e972e-132">Dans **Paramètres,** **tapez BitLocker**.</span><span class="sxs-lookup"><span data-stu-id="e972e-132">In **Settings**, type **BitLocker**.</span></span>
2. <span data-ttu-id="e972e-133">Sélectionnez **Gérer BitLocker**  > **générer la clé de récupération BitLocker.**</span><span class="sxs-lookup"><span data-stu-id="e972e-133">Select **Manage BitLocker** >**Generate BitLocker Recovery Key**.</span></span>
2.  <span data-ttu-id="e972e-134">Insérez un lecteur USB.</span><span class="sxs-lookup"><span data-stu-id="e972e-134">Insert a USB drive.</span></span> 
4.  <span data-ttu-id="e972e-135">Enregistrez la clé de récupération dans le stockage USB.</span><span class="sxs-lookup"><span data-stu-id="e972e-135">Save the recovery key to USB storage.</span></span>  
5.  <span data-ttu-id="e972e-136">Supprimez le lecteur USB.</span><span class="sxs-lookup"><span data-stu-id="e972e-136">Remove the USB drive.</span></span>  
6.  <span data-ttu-id="e972e-137">Alimentation de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="e972e-137">Power down the device.</span></span> 

## <span data-ttu-id="e972e-138">Supprimer et remplacer le SSD</span><span class="sxs-lookup"><span data-stu-id="e972e-138">Remove and replace SSD</span></span> 

1.  <span data-ttu-id="e972e-139">Supprimez le SSD en suivant les instructions appropriées pour votre appareil incluses dans le Guide de suppression [rSSD pour Entreprise.](https://www.microsoft.com/download/100440)</span><span class="sxs-lookup"><span data-stu-id="e972e-139">Remove the SSD by using the appropriate instructions for your device included in [rSSD Removal Guide for Enterprise](https://www.microsoft.com/download/100440).</span></span> 
2.  <span data-ttu-id="e972e-140">Placez le SSD d’origine dans un nouvel appareil et connectez-le à une connexion Internet câblé.</span><span class="sxs-lookup"><span data-stu-id="e972e-140">Put the original SSD into a new device and connect the new device to a wired internet connection.</span></span>
3.  <span data-ttu-id="e972e-141">Alimentation sur le nouvel appareil.</span><span class="sxs-lookup"><span data-stu-id="e972e-141">Power on the new device.</span></span> <span data-ttu-id="e972e-142">L’appareil peut passer par une mise à jour du microprogramme au démarrage.</span><span class="sxs-lookup"><span data-stu-id="e972e-142">The device may go through a firmware update during startup.</span></span>  
 
## <span data-ttu-id="e972e-143">Après la suppression et le remplacement du SSD</span><span class="sxs-lookup"><span data-stu-id="e972e-143">After SSD removal and replacement</span></span>

### <span data-ttu-id="e972e-144">Gérer les SSD non chiffrés</span><span class="sxs-lookup"><span data-stu-id="e972e-144">Manage unencrypted SSDs</span></span> 

<span data-ttu-id="e972e-145">Si le SSD n’est pas chiffré pendant le transfert, suivez les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="e972e-145">If the SSD is unencrypted during the transfer, follow these steps:</span></span> 

1.  <span data-ttu-id="e972e-146">Go to **Sign-In Options**  >  **Password** (represented by the key icon on the left side).</span><span class="sxs-lookup"><span data-stu-id="e972e-146">Go to **Sign-In Options** > **Password** (represented by the key icon on the left side).</span></span>  
2.  <span data-ttu-id="e972e-147">Entrez le mot de passe et connectez-vous en attendant la fin de l’authentification à deux facteurs (le cas échéant).</span><span class="sxs-lookup"><span data-stu-id="e972e-147">Enter the password and sign in pending completion of two-factor authentication (if applicable).</span></span>
3.  <span data-ttu-id="e972e-148">Une fois que vous êtes entièrement connectez-vous, allez sur **Démarrer**  >  **la**  >  **signature du compte.**</span><span class="sxs-lookup"><span data-stu-id="e972e-148">After you are fully signed in, go to **Start** > **Account** > **Sign out**.</span></span>  
4.  <span data-ttu-id="e972e-149">Connectez-vous à l’aide du mot de passe et définissez Windows Hello et un code confidentiel lorsque vous y êtes invité.</span><span class="sxs-lookup"><span data-stu-id="e972e-149">Sign back in by using the password and set up Windows Hello and a PIN when you are prompted.</span></span> 
    - <span data-ttu-id="e972e-150">Si l’appareil a été désactivé par BitLocker pour faciliter la suppression et le remplacement de SSD, et que vous souhaitez activer BitLocker après le remplacement, allez à **BitLocker**  >  **Manage BitLocker**  >  **Resume BitLocker**.</span><span class="sxs-lookup"><span data-stu-id="e972e-150">If the device was BitLocker-disabled to facilitate SSD removal and replacement, and you want to enable BitLocker after the replacement, go to **BitLocker** > **Manage BitLocker** > **Resume BitLocker**.</span></span>  
6.  <span data-ttu-id="e972e-151">Exécutez [microsoft Surface Diagnostic Shared Computer Toolkit for Business](surface-diagnostic-toolkit-for-business-intro.md) (SDT) pour vérifier les fonctionnalités complètes de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="e972e-151">Run the [Microsoft Surface Diagnostic Toolkit for Business](surface-diagnostic-toolkit-for-business-intro.md) (SDT) to verify full device functionality.</span></span>  
7.  <span data-ttu-id="e972e-152">Recherchez l’activation de Windows en naviguant vers **l’activation des**  >  **paramètres.**</span><span class="sxs-lookup"><span data-stu-id="e972e-152">Check for Windows activation by navigating to **Settings** > **Activation**.</span></span>  <span data-ttu-id="e972e-153">Si vous voyez des messages d’erreur, sélectionnez **Résoudre les problèmes.**</span><span class="sxs-lookup"><span data-stu-id="e972e-153">If you see any error messages, select **Troubleshoot**.</span></span> 
8.  <span data-ttu-id="e972e-154">Vérifiez le compte Office en ouvrant \*\*\*\* **l’application Office,** accédez à Compte de  >  \*\*\*\* fichier, puis recherchez les messages d’erreur.</span><span class="sxs-lookup"><span data-stu-id="e972e-154">Check the Office account by opening the **Office App**, navigate to **File** > **Account** and then check for any error messages.</span></span>  

### <span data-ttu-id="e972e-155">Gestion des SSD chiffrés</span><span class="sxs-lookup"><span data-stu-id="e972e-155">Managing encrypted SSDs</span></span> 

> [!NOTE]
> <span data-ttu-id="e972e-156">Vous devez avoir un deuxième appareil pour lire la clé de récupération BitLocker qui a été enregistrée sur le lecteur USB.</span><span class="sxs-lookup"><span data-stu-id="e972e-156">You will have to have a second device to read the BitLocker Recovery key that was saved on the USB drive.</span></span> 

<span data-ttu-id="e972e-157">Si le SSD est chiffré pendant le transfert, suivez les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="e972e-157">If the SSD is encrypted during the transfer, follow these steps:</span></span>

1.  <span data-ttu-id="e972e-158">Insérez le lecteur USB qui contient la clé de récupération BitLocker dans le deuxième appareil.</span><span class="sxs-lookup"><span data-stu-id="e972e-158">Insert the USB drive that contains the BitLocker recovery key into the second device.</span></span> 
2.  <span data-ttu-id="e972e-159">Ouvrez le fichier .txt qui contient la clé de récupération Bitlocker.</span><span class="sxs-lookup"><span data-stu-id="e972e-159">Open the .txt file that contains the Bitlocker recovery key.</span></span> 
3.  <span data-ttu-id="e972e-160">Entrez manuellement la clé de récupération BitLocker sur le nouvel appareil qui contient le SSD d’origine.</span><span class="sxs-lookup"><span data-stu-id="e972e-160">Manually enter the BitLocker recovery key on the new device that contains the original SSD.</span></span>  
4.  <span data-ttu-id="e972e-161">Une fois que vous avez entré la \*\*\*\* clé de récupération BitLocker, allez sur Mot de passe options de la signature (représenté par l’icône de clé  >  \*\*\*\* sur le côté gauche).</span><span class="sxs-lookup"><span data-stu-id="e972e-161">After you have successfully entered the BitLocker recovery key, go to **Sign-In Options** > **Password** (represented by the key icon on the left side).</span></span>  
5.  <span data-ttu-id="e972e-162">Entrez le mot de passe et connectez-vous en attendant la fin de l’authentification à deux facteurs (le cas échéant).</span><span class="sxs-lookup"><span data-stu-id="e972e-162">Enter the password and sign in, pending completion of two-factor authentication (if applicable).</span></span>
6.  <span data-ttu-id="e972e-163">Une fois que vous êtes entièrement connectez-vous, allez sur **Démarrer**  >  **la**  >  **signature du compte.**</span><span class="sxs-lookup"><span data-stu-id="e972e-163">After you are fully signed in, go to **Start** > **Account** > **Sign out**.</span></span>  
7.  <span data-ttu-id="e972e-164">Connectez-vous à l’aide du mot de passe, puis définissez Windows Hello et ajoutez un code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="e972e-164">Sign back in by using the password, and then set up Windows Hello and add a PIN.</span></span> 
8.  <span data-ttu-id="e972e-165">Si l’appareil a été désactivé par BitLocker pour faciliter la suppression et le remplacement de SSD, et si vous souhaitez activer BitLocker après le remplacement, allez à **Paramètres**  >  **BitLocker**  >  **Gérer BitLocker**  >  **Resume BitLocker BitLocker**.</span><span class="sxs-lookup"><span data-stu-id="e972e-165">If the device was BitLocker-disabled to facilitate SSD removal and replacement, and if you want to enable BitLocker after the replacement, go to **Settings** > **BitLocker** > **Manage BitLocker** > **Resume BitLocker**.</span></span>  
9.  <span data-ttu-id="e972e-166">Exécutez **[SDT pour](surface-diagnostic-toolkit-for-business-intro.md)** vérifier les fonctionnalités complètes de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="e972e-166">Run **[SDT](surface-diagnostic-toolkit-for-business-intro.md)** to verify full device functionality.</span></span>  
10. <span data-ttu-id="e972e-167">Pour vérifier l’activation de Windows, sélectionnez **Activation des**  >  **paramètres.**</span><span class="sxs-lookup"><span data-stu-id="e972e-167">To check Windows activation, select **Settings** > **Activation**.</span></span>  <span data-ttu-id="e972e-168">Si vous voyez des messages d’erreur, sélectionnez **Résoudre les problèmes.**</span><span class="sxs-lookup"><span data-stu-id="e972e-168">If you see any error messages, select **Troubleshoot**.</span></span>
11. <span data-ttu-id="e972e-169">Pour vérifier l’état du compte Office, ouvrez \*\*\*\* l’application **Office,** puis rendez-vous sur Compte de fichier pour vérifier les  >  \*\*\*\* messages d’erreur.</span><span class="sxs-lookup"><span data-stu-id="e972e-169">To check the status of the Office account, open the **Office App**, then go to **File** > **Account** to check for any error messages.</span></span>

## <span data-ttu-id="e972e-170">En savoir plus</span><span class="sxs-lookup"><span data-stu-id="e972e-170">Learn more</span></span>

- [<span data-ttu-id="e972e-171">Guide de suppression rSSD pour entreprise</span><span class="sxs-lookup"><span data-stu-id="e972e-171">rSSD Removal Guide for Enterprise</span></span>](https://www.microsoft.com/download/100440)
- [<span data-ttu-id="e972e-172">Guide de récupération BitLocker</span><span class="sxs-lookup"><span data-stu-id="e972e-172">BitLocker Recovery Guide</span></span>](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)

<span data-ttu-id="e972e-173">Encore besoin d’aide?</span><span class="sxs-lookup"><span data-stu-id="e972e-173">Still need help?</span></span> <span data-ttu-id="e972e-174">Go to [Microsoft Community](https://answers.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="e972e-174">Go to [Microsoft Community](https://answers.microsoft.com/).</span></span>