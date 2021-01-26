---
title: Gérer les paramètres UEFI Surface
description: Les paramètres UEFI Surface vous permettent d’activer ou de désactiver des périphériques ou des composants, de configurer les paramètres de sécurité et d’ajuster les paramètres de démarrage des appareils Surface.
keywords: microprogramme, sécurité, fonctionnalités, configurer, matériel
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: devices, surface
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: hachidan
manager: laurawi
ms.date: 01/25/2021
ms.openlocfilehash: af9eac171dea5d29ce9776766a2c5842bea9eb8c
ms.sourcegitcommit: 1b12ea363785697ddc705b0a0cc7bb35cad6b327
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "11300695"
---
# <span data-ttu-id="a0e15-104">Gérer les paramètres UEFI Surface</span><span class="sxs-lookup"><span data-stu-id="a0e15-104">Manage Surface UEFI settings</span></span>

 <span data-ttu-id="a0e15-105">Les appareils Surface PC sont conçus pour utiliser une interface UEFI (Unified Extensible Firmware Interface) unique conçue par Microsoft spécifiquement pour ces appareils.</span><span class="sxs-lookup"><span data-stu-id="a0e15-105">Surface PC devices are designed to utilize a unique Unified Extensible Firmware Interface (UEFI) engineered by Microsoft specifically for these devices.</span></span> <span data-ttu-id="a0e15-106">Les paramètres UEFI Surface offrent la possibilité d’activer ou de désactiver les appareils et composants intégrés, de protéger les paramètres UEFI contre les changements et d’ajuster les paramètres de démarrage de l’appareil Surface.</span><span class="sxs-lookup"><span data-stu-id="a0e15-106">Surface UEFI settings provide the ability to enable or disable built-in devices and components, protect UEFI settings from being changed, and adjust the Surface device boot settings.</span></span> 

## <span data-ttu-id="a0e15-107">Produits pris en charge</span><span class="sxs-lookup"><span data-stu-id="a0e15-107">Supported products</span></span>

<span data-ttu-id="a0e15-108">La gestion UEFI est prise en charge sur les questions suivantes :</span><span class="sxs-lookup"><span data-stu-id="a0e15-108">UEFI management is supported on the following:</span></span> 

- <span data-ttu-id="a0e15-109">Surface Pro 4, Surface Pro (5e génération), Surface Pro 6, Surface Pro 7, Surface Pro 7+, Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="a0e15-109">Surface Pro 4, Surface Pro (5th Gen), Surface Pro 6, Surface Pro 7, Surface Pro 7+, Surface Pro X</span></span>
- <span data-ttu-id="a0e15-110">Surface Laptop (1ère génération), Surface Laptop 2, Surface Laptop 3, Surface Laptop Go</span><span class="sxs-lookup"><span data-stu-id="a0e15-110">Surface Laptop (1st Gen), Surface Laptop 2, Surface Laptop 3, Surface Laptop Go</span></span>
- <span data-ttu-id="a0e15-111">Surface Studio (1re génération), Surface Studio 2</span><span class="sxs-lookup"><span data-stu-id="a0e15-111">Surface Studio (1st Gen), Surface Studio 2</span></span>
- <span data-ttu-id="a0e15-112">Surface Book, Surface Book 2, Surface Book 3</span><span class="sxs-lookup"><span data-stu-id="a0e15-112">Surface Book, Surface Book 2, Surface Book 3</span></span>
- <span data-ttu-id="a0e15-113">Surface Go, Surface Go 2[ <sup> 1 </sup> ](#references)</span><span class="sxs-lookup"><span data-stu-id="a0e15-113">Surface Go, Surface Go 2[<sup>1</sup>](#references)</span></span>

## <span data-ttu-id="a0e15-114">Prise en charge de la gestion basée sur le cloud</span><span class="sxs-lookup"><span data-stu-id="a0e15-114">Support for cloud-based management</span></span>

<span data-ttu-id="a0e15-115">Avec les profils DFCI (Device Firmware Configuration Interface) intégrés à Microsoft Intune (désormais disponibles en prévisualisation publique), la gestion UEFI Surface étend la pile de gestion moderne jusqu’au niveau matériel UEFI.</span><span class="sxs-lookup"><span data-stu-id="a0e15-115">With Device Firmware Configuration Interface (DFCI) profiles built into Microsoft Intune (now available in public preview), Surface UEFI management extends the modern management stack down to the UEFI hardware level.</span></span> <span data-ttu-id="a0e15-116">DFCI prend en charge l’approvisionnement sans contact, élimine les mots de passe BIOS, contrôle les paramètres de sécurité, y compris les options de démarrage et les périphériques intégrés, et constitue la base des scénarios de sécurité avancés à l’avenir.</span><span class="sxs-lookup"><span data-stu-id="a0e15-116">DFCI supports zero-touch provisioning, eliminates BIOS passwords, provides control of security settings including boot options and built-in peripherals, and lays the groundwork for advanced security scenarios in the future.</span></span> <span data-ttu-id="a0e15-117">DFCI est actuellement disponible pour Surface Pro 7+, Surface Laptop Go, Surface Book 3, Surface Laptop 3, Surface Pro 7 et Surface Pro X.  Pour plus d’informations, reportez-vous à [La gestion Intune des paramètres UEFI Surface.](surface-manage-dfci-guide.md)</span><span class="sxs-lookup"><span data-stu-id="a0e15-117">DFCI is currently available for Surface Pro 7+, Surface Laptop Go, Surface Book 3, Surface Laptop 3, Surface Pro 7, and Surface Pro X.  For more information, refer to [Intune management of Surface UEFI settings](surface-manage-dfci-guide.md).</span></span>

## <span data-ttu-id="a0e15-118">Menu UEFI Open Surface</span><span class="sxs-lookup"><span data-stu-id="a0e15-118">Open Surface UEFI menu</span></span>

<span data-ttu-id="a0e15-119">Pour ajuster les paramètres UEFI au démarrage du système :</span><span class="sxs-lookup"><span data-stu-id="a0e15-119">To adjust UEFI settings during system startup:</span></span>

1. <span data-ttu-id="a0e15-120">Fermez votre Surface et patientez environ 10 secondes pour vous assurer qu’elle est éteinte.</span><span class="sxs-lookup"><span data-stu-id="a0e15-120">Shut down your Surface and wait about 10 seconds to make sure it's off.</span></span>
2. <span data-ttu-id="a0e15-121">Appuyez longuement **sur le bouton** Monter en volume et, en même temps, appuyez sur le bouton **d’alimentation et relâchez-le.**</span><span class="sxs-lookup"><span data-stu-id="a0e15-121">Press and hold the **Volume-up** button  and - at the same time - press and release the **Power button.**</span></span>
3. <span data-ttu-id="a0e15-122">À mesure que le logo Microsoft ou Surface apparaît sur votre écran, maintenez le bouton **Volume-up** enfoncé jusqu’à ce que l’écran UEFI s’affiche.</span><span class="sxs-lookup"><span data-stu-id="a0e15-122">As the Microsoft or Surface logo appears on your screen, continue to hold the **Volume-up** button until the UEFI screen appears.</span></span>

## <span data-ttu-id="a0e15-123">Page d’informations du PC UEFI</span><span class="sxs-lookup"><span data-stu-id="a0e15-123">UEFI PC information page</span></span>

<span data-ttu-id="a0e15-124">La page d’informations du PC contient des informations détaillées sur votre appareil Surface :</span><span class="sxs-lookup"><span data-stu-id="a0e15-124">The PC information page includes detailed information about your Surface device:</span></span> 

- <span data-ttu-id="a0e15-125">**Modèle** : le modèle de votre appareil Surface sera affiché ici, tel que Surface Book 2 ou Surface Pro 7.</span><span class="sxs-lookup"><span data-stu-id="a0e15-125">**Model** – Your Surface device’s model will be displayed here, such as Surface Book 2 or Surface Pro 7.</span></span> <span data-ttu-id="a0e15-126">La configuration exacte de votre appareil (notamment le processeur, la taille du disque ou la taille de la mémoire) n’apparaît pas.</span><span class="sxs-lookup"><span data-stu-id="a0e15-126">The exact configuration of your device is not shown, (such as processor, disk size, or memory size).</span></span> 
- <span data-ttu-id="a0e15-127">**UUID**: cet identificateur global unique est propre à votre appareil et sert à identifier l’appareil dans le cadre des processus de déploiement ou de gestion.</span><span class="sxs-lookup"><span data-stu-id="a0e15-127">**UUID** – This Universally Unique Identification number is specific to your device and is used to identify the device during deployment or management.</span></span> 

- <span data-ttu-id="a0e15-128">**Numéro de série**: ce numéro permet d’identifier cet appareil Surface spécifique pour les scénarios de support et d’étiquetage des ressources.</span><span class="sxs-lookup"><span data-stu-id="a0e15-128">**Serial Number** – This number is used to identify this specific Surface device for asset tagging and support scenarios.</span></span>
- <span data-ttu-id="a0e15-129">**Étiquette d’inventaire**: l’étiquette d’inventaire est affectée à l’appareil Surface avec l’[Outil d’étiquette d’inventaire](https://docs.microsoft.com/surface/assettag).</span><span class="sxs-lookup"><span data-stu-id="a0e15-129">**Asset Tag** – The asset tag is assigned to the Surface device with the [Asset Tag Tool](https://docs.microsoft.com/surface/assettag).</span></span> 

<span data-ttu-id="a0e15-130">Ce champ fournit également des informations détaillées sur le microprogramme de votre appareil Surface.</span><span class="sxs-lookup"><span data-stu-id="a0e15-130">You will also find detailed information about the firmware of your Surface device.</span></span> <span data-ttu-id="a0e15-131">Les appareils Surface intègrent plusieurs composants internes exécutant chacun une version de microprogramme distincte.</span><span class="sxs-lookup"><span data-stu-id="a0e15-131">Surface devices have several internal components that each run different versions of firmware.</span></span> <span data-ttu-id="a0e15-132">La version de microprogramme de chacun des composants ci-après est indiquée sur la page **Informations du PC** (comme illustré à la Figure1):</span><span class="sxs-lookup"><span data-stu-id="a0e15-132">The firmware version of each of the following devices is displayed on the **PC information** page (as shown in Figure 1):</span></span> 

- <span data-ttu-id="a0e15-133">UEFI système</span><span class="sxs-lookup"><span data-stu-id="a0e15-133">System UEFI</span></span> 

- <span data-ttu-id="a0e15-134">Contrôleur SAM</span><span class="sxs-lookup"><span data-stu-id="a0e15-134">SAM Controller</span></span> 

- <span data-ttu-id="a0e15-135">Moteur de gestion Intel</span><span class="sxs-lookup"><span data-stu-id="a0e15-135">Intel Management Engine</span></span> 

- <span data-ttu-id="a0e15-136">Contrôleur système embarqué</span><span class="sxs-lookup"><span data-stu-id="a0e15-136">System Embedded Controller</span></span> 

- <span data-ttu-id="a0e15-137">Microprogramme du contrôleur tactile</span><span class="sxs-lookup"><span data-stu-id="a0e15-137">Touch Firmware</span></span> 

![Informations système et informations sur les versions du microprogramme](images/manage-surface-uefi-figure-1.png "System information and firmware version information")

*<span data-ttu-id="a0e15-139">Figure1.</span><span class="sxs-lookup"><span data-stu-id="a0e15-139">Figure 1.</span></span> <span data-ttu-id="a0e15-140">Informations système et informations sur les versions du microprogramme</span><span class="sxs-lookup"><span data-stu-id="a0e15-140">System information and firmware version information</span></span>*

<span data-ttu-id="a0e15-141">Vous trouverez des informations à jour sur la dernière version de microprogramme pour votre appareil Surface dans l’[Historique des mises à jour de MicrosoftSurface](https://www.microsoft.com/surface/support/install-update-activate/surface-update-history) de votre appareil.</span><span class="sxs-lookup"><span data-stu-id="a0e15-141">You can find up-to-date information about the latest firmware version for your Surface device in the [Surface Update History](https://www.microsoft.com/surface/support/install-update-activate/surface-update-history) for your device.</span></span> 

## <span data-ttu-id="a0e15-142">Page Sécurité UEFI</span><span class="sxs-lookup"><span data-stu-id="a0e15-142">UEFI Security page</span></span> 

![Configurer les paramètres de sécurité UEFI Surface](images/manage-surface-uefi-fig4.png "Configure Surface UEFI security settings")

*<span data-ttu-id="a0e15-144">Figure2.</span><span class="sxs-lookup"><span data-stu-id="a0e15-144">Figure 2.</span></span> <span data-ttu-id="a0e15-145">Configurer les paramètres de sécurité UEFI Surface</span><span class="sxs-lookup"><span data-stu-id="a0e15-145">Configure Surface UEFI security settings</span></span>*

<span data-ttu-id="a0e15-146">La page Sécurité vous permet de définir un mot de passe pour protéger les paramètres UEFI.</span><span class="sxs-lookup"><span data-stu-id="a0e15-146">The Security page allows you to set a password to protect UEFI settings.</span></span> <span data-ttu-id="a0e15-147">Vous devez entrer ce mot de passe lorsque vous démarrez l’appareil Surface en mode UEFI.</span><span class="sxs-lookup"><span data-stu-id="a0e15-147">This password must be entered when you boot the Surface device to UEFI.</span></span> <span data-ttu-id="a0e15-148">Le mot de passe peut contenir les caractères suivants (comme illustré dans la figure 3) :</span><span class="sxs-lookup"><span data-stu-id="a0e15-148">The password can contain the following characters (as shown in Figure 3):</span></span> 

- <span data-ttu-id="a0e15-149">Lettres majuscules: A-Z</span><span class="sxs-lookup"><span data-stu-id="a0e15-149">Uppercase letters: A-Z</span></span> 

- <span data-ttu-id="a0e15-150">Lettres minuscules: a-z</span><span class="sxs-lookup"><span data-stu-id="a0e15-150">Lowercase letters: a-z</span></span> 

- <span data-ttu-id="a0e15-151">Chiffres: 1-0</span><span class="sxs-lookup"><span data-stu-id="a0e15-151">Numbers: 1-0</span></span> 

- <span data-ttu-id="a0e15-152">Caractères spéciaux : !@#$%^&\*()?<>{} []-_=+|.,;:''»</span><span class="sxs-lookup"><span data-stu-id="a0e15-152">Special characters: !@#$%^&\*()?<>{}[]-_=+|.,;:’\`”</span></span> 

<span data-ttu-id="a0e15-153">Le mot de passe doit comporter au moins 6caractères et respecte la casse.</span><span class="sxs-lookup"><span data-stu-id="a0e15-153">The password must be at least 6 characters and is case sensitive.</span></span> 

![Ajouter un mot de passe pour protéger les paramètres UEFI Surface](images/manage-surface-uefi-fig2.png "Add a password to protect Surface UEFI settings")

*<span data-ttu-id="a0e15-155">Figure3.</span><span class="sxs-lookup"><span data-stu-id="a0e15-155">Figure 3.</span></span> <span data-ttu-id="a0e15-156">Ajouter un mot de passe pour protéger les paramètres UEFI Surface</span><span class="sxs-lookup"><span data-stu-id="a0e15-156">Add a password to protect Surface UEFI settings</span></span>*

<span data-ttu-id="a0e15-157">La page Sécurité vous permet également de modifier la configuration du démarrage sécurisé sur votre appareil Surface.</span><span class="sxs-lookup"><span data-stu-id="a0e15-157">On the Security page you can also change the configuration of Secure Boot on your Surface device.</span></span> <span data-ttu-id="a0e15-158">La technologie de démarrage sécurisé empêche tout démarrage d’un code de démarrage non autorisé sur votre appareil Surface, et vous offre ainsi une protection contre les infections par programmes malveillants de type bootkit ou rootkit.</span><span class="sxs-lookup"><span data-stu-id="a0e15-158">Secure Boot technology prevents unauthorized boot code from booting on your Surface device, which protects against bootkit and rootkit-type malware infections.</span></span> <span data-ttu-id="a0e15-159">Vous pouvez désactiver le démarrage sécurisé si vous souhaitez permettre à votre appareil Surface de démarrer des systèmes d’exploitation ou des médias de démarrage tiers.</span><span class="sxs-lookup"><span data-stu-id="a0e15-159">You can disable Secure Boot to allow your Surface device to boot third-party operating systems or bootable media.</span></span> <span data-ttu-id="a0e15-160">Vous pouvez également configurer le démarrage sécurisé pour qu’il fonctionne avec des certificats tiers, comme le montre la figure 4.</span><span class="sxs-lookup"><span data-stu-id="a0e15-160">You can also configure Secure Boot to work with third-party certificates, as shown in Figure 4.</span></span> <span data-ttu-id="a0e15-161">Apprenez-en davantage sur le [démarrage sécurisé](https://msdn.microsoft.com/windows/hardware/commercialize/manufacture/desktop/secure-boot-overview) dans la bibliothèque TechNet.</span><span class="sxs-lookup"><span data-stu-id="a0e15-161">Read more about [Secure Boot](https://msdn.microsoft.com/windows/hardware/commercialize/manufacture/desktop/secure-boot-overview) in the TechNet Library.</span></span>

![Configurer le démarrage sécurisé](images/manage-surface-uefi-fig3.png "Configure Secure Boot")

*<span data-ttu-id="a0e15-163">Figure4.</span><span class="sxs-lookup"><span data-stu-id="a0e15-163">Figure 4.</span></span> <span data-ttu-id="a0e15-164">Configurer le démarrage sécurisé</span><span class="sxs-lookup"><span data-stu-id="a0e15-164">Configure Secure Boot</span></span>*

<span data-ttu-id="a0e15-165">En fonction de votre appareil, vous pouvez également voir si votre TPM est activé ou désactivé.</span><span class="sxs-lookup"><span data-stu-id="a0e15-165">Depending on your device, you may also be able to see if your TPM is enabled or disabled.</span></span> <span data-ttu-id="a0e15-166">Si vous ne voyez pas le paramètre Activer **le TPM,**  ouvrez tpm.msc dans Windows pour vérifier l’état, comme illustré à la Figure 5.</span><span class="sxs-lookup"><span data-stu-id="a0e15-166">If you do not see the **Enable TPM**  setting, open tpm.msc in Windows to check the status, as shown in Figure 5.</span></span> <span data-ttu-id="a0e15-167">Le module TPM permet d’authentifier le chiffrement des données de votre appareil avec BitLocker.</span><span class="sxs-lookup"><span data-stu-id="a0e15-167">The TPM is used to authenticate encryption for your device’s data with BitLocker.</span></span> <span data-ttu-id="a0e15-168">Pour en savoir plus, consultez la vue [d’ensemble de BitLocker.](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview)</span><span class="sxs-lookup"><span data-stu-id="a0e15-168">To learn more, see [BitLocker overview](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview).</span></span> 

![Console TPM](images/manage-surface-uefi-fig5-a.png "TPM console")

*<span data-ttu-id="a0e15-170">Figure5.</span><span class="sxs-lookup"><span data-stu-id="a0e15-170">Figure 5.</span></span> <span data-ttu-id="a0e15-171">Console TPM</span><span class="sxs-lookup"><span data-stu-id="a0e15-171">TPM console</span></span>*


## <span data-ttu-id="a0e15-172">Menu UEFI : Appareils</span><span class="sxs-lookup"><span data-stu-id="a0e15-172">UEFI menu: Devices</span></span> 

<span data-ttu-id="a0e15-173">La page Appareils vous permet d’activer ou de désactiver des appareils et composants spécifiques, notamment :</span><span class="sxs-lookup"><span data-stu-id="a0e15-173">The Devices page allows you to  enable or disable specific devices and components including:</span></span>

- <span data-ttu-id="a0e15-174">Ports de station d’accueil et USB</span><span class="sxs-lookup"><span data-stu-id="a0e15-174">Docking and USB Ports</span></span> 

- <span data-ttu-id="a0e15-175">Emplacement pour carte mémoire Secure Digital ou MicroSD</span><span class="sxs-lookup"><span data-stu-id="a0e15-175">MicroSD or SD Card Slot</span></span> 

- <span data-ttu-id="a0e15-176">Caméra arrière</span><span class="sxs-lookup"><span data-stu-id="a0e15-176">Rear Camera</span></span> 

- <span data-ttu-id="a0e15-177">Caméra frontale</span><span class="sxs-lookup"><span data-stu-id="a0e15-177">Front Camera</span></span> 

- <span data-ttu-id="a0e15-178">Caméra infrarouge (IR)</span><span class="sxs-lookup"><span data-stu-id="a0e15-178">Infrared (IR) Camera</span></span> 

- <span data-ttu-id="a0e15-179">Wi-Fi et Bluetooth</span><span class="sxs-lookup"><span data-stu-id="a0e15-179">Wi-Fi and Bluetooth</span></span> 

- <span data-ttu-id="a0e15-180">Audio intégré (haut-parleurs et microphone)</span><span class="sxs-lookup"><span data-stu-id="a0e15-180">Onboard Audio (Speakers and Microphone)</span></span> 

<span data-ttu-id="a0e15-181">Chaque appareil est répertorié avec un bouton de curseur que vous pouvez déplacer vers la position **Activé** (activé) ou Désactivé **(désactivé),** comme illustré dans la figure 6.</span><span class="sxs-lookup"><span data-stu-id="a0e15-181">Each device is listed with a slider button that you can move to **On** (enabled) or **Off** (disabled) position, as shown in Figure 6.</span></span> 

![Activer et désactiver des périphériques spécifiques](images/manage-surface-uefi-fig5a.png "Enable and disable specific devices")

*<span data-ttu-id="a0e15-183">Figure6.</span><span class="sxs-lookup"><span data-stu-id="a0e15-183">Figure 6.</span></span> <span data-ttu-id="a0e15-184">Activer et désactiver des périphériques spécifiques</span><span class="sxs-lookup"><span data-stu-id="a0e15-184">Enable and disable specific devices</span></span>*

## <span data-ttu-id="a0e15-185">Menu UEFI : configuration du démarrage</span><span class="sxs-lookup"><span data-stu-id="a0e15-185">UEFI menu: Boot configuration</span></span> 

<span data-ttu-id="a0e15-186">La page Configuration du démarrage vous permet de modifier l’ordre de vos périphériques de démarrage, ainsi que d’activer ou de désactiver le démarrage des appareils suivants :</span><span class="sxs-lookup"><span data-stu-id="a0e15-186">The Boot Configuration page allows you to change the order of your boot devices as well as enable or disable boot of the following devices:</span></span> 

- <span data-ttu-id="a0e15-187">Gestionnaire de démarrage Windows</span><span class="sxs-lookup"><span data-stu-id="a0e15-187">Windows Boot Manager</span></span> 

- <span data-ttu-id="a0e15-188">Stockage USB</span><span class="sxs-lookup"><span data-stu-id="a0e15-188">USB Storage</span></span> 

- <span data-ttu-id="a0e15-189">Réseau PXE (Preboot Execution Environment)</span><span class="sxs-lookup"><span data-stu-id="a0e15-189">PXE Network</span></span> 

- <span data-ttu-id="a0e15-190">Stockage interne</span><span class="sxs-lookup"><span data-stu-id="a0e15-190">Internal Storage</span></span> 

<span data-ttu-id="a0e15-191">Vous pouvez démarrer immédiatement l’appareil à partir d’un périphérique spécifique, ou effectuer un mouvement de balayage vers la gauche sur l’entrée de ce périphérique dans la liste en utilisant l’écran tactile.</span><span class="sxs-lookup"><span data-stu-id="a0e15-191">You can boot from a specific device immediately, or you can swipe left on that device’s entry in the list using the touchscreen.</span></span> <span data-ttu-id="a0e15-192">Vous pouvez également démarrer immédiatement à partir d’un périphérique USB ou d’un adaptateur Ethernet USB lorsque l’appareil Surface est éteint en appuyant simultanément sur le bouton **Baisser le volume** et sur le bouton **Marche/Arrêt**.</span><span class="sxs-lookup"><span data-stu-id="a0e15-192">You can also boot immediately to a USB device or USB Ethernet adapter when the Surface device is powered off by pressing the **Volume Down** button and the **Power** button simultaneously.</span></span> 

<span data-ttu-id="a0e15-193">Pour que l’ordre de démarrage spécifié \*\*\*\* prenne effet, vous devez définir l’option Activer la séquence de démarrage secondaire sur **Activé,** comme illustré dans la figure 7.</span><span class="sxs-lookup"><span data-stu-id="a0e15-193">For the specified boot order to take effect, you must set the **Enable Alternate Boot Sequence** option to **On**, as shown in Figure 7.</span></span> 

![Configurer l’ordre de démarrage de votre appareil Surface](images/manage-surface-uefi-fig6.png "Configure the boot order for your Surface device")

*<span data-ttu-id="a0e15-195">Figure7.</span><span class="sxs-lookup"><span data-stu-id="a0e15-195">Figure 7.</span></span> <span data-ttu-id="a0e15-196">Configurer l’ordre de démarrage de votre appareil Surface</span><span class="sxs-lookup"><span data-stu-id="a0e15-196">Configure the boot order for your Surface device</span></span>* 

<span data-ttu-id="a0e15-197">Vous pouvez également activer et désactiver la prise en charge d’IPv6 pour PXE par le biais de l’option **Activer IPv6 pour le démarrage du réseau PXE**, par exemple lorsque vous effectuez un déploiement Windows à l’aide de PXE et que le serveur PXE est uniquement configuré pour IPv4.</span><span class="sxs-lookup"><span data-stu-id="a0e15-197">You can also turn on and off IPv6 support for PXE with the **Enable IPv6 for PXE Network Boot** option, for example when performing a Windows deployment using PXE where the PXE server is configured for IPv4 only.</span></span>  

## <span data-ttu-id="a0e15-198">Menu UEFI : Gestion</span><span class="sxs-lookup"><span data-stu-id="a0e15-198">UEFI menu: Management</span></span>
<span data-ttu-id="a0e15-199">La page Gestion vous permet de gérer l’utilisation de la gestion UEFI Zero Touch et d’autres fonctionnalités sur les appareils éligibles, notamment Surface Pro 7, Surface Pro X et Surface Laptop 3.</span><span class="sxs-lookup"><span data-stu-id="a0e15-199">The Management page allows you to manage use of Zero Touch UEFI Management and other features on eligible devices including Surface Pro 7, Surface Pro X, and Surface Laptop 3.</span></span>  

![<span data-ttu-id="a0e15-200">Gérer l’accès à la gestion UEFI Zero Touch et à d’autres fonctionnalités ](images/manage-surface-uefi-fig7a.png "Manage access to Zero Touch UEFI Management and other features")
 *figure 8. Gérer l’accès à la gestion UEFI Zero Touch et à d’autres fonctionnalités*</span><span class="sxs-lookup"><span data-stu-id="a0e15-200">Manage access to Zero Touch UEFI Management and other features](images/manage-surface-uefi-fig7a.png "Manage access to Zero Touch UEFI Management and other features")
*Figure 8. Manage access to Zero Touch UEFI Management and other features*</span></span> 


<span data-ttu-id="a0e15-201">La gestion UEFI Zero Touch vous permet de gérer à distance les paramètres UEFI à l’aide d’un profil d’appareil dans Intune appelé DFCI (Device Firmware Configuration Interface).</span><span class="sxs-lookup"><span data-stu-id="a0e15-201">Zero Touch UEFI Management lets you remotely manage UEFI settings  by using a device profile within Intune called Device Firmware Configuration Interface (DFCI).</span></span> <span data-ttu-id="a0e15-202">Si vous ne configurez pas ce paramètre, la possibilité de gérer les appareils éligibles avec DFCI est définie sur **Prêt**.</span><span class="sxs-lookup"><span data-stu-id="a0e15-202">If you do not configure this setting, the ability to manage eligible devices with DFCI is set to **Ready**.</span></span> <span data-ttu-id="a0e15-203">Pour empêcher DFCI, sélectionnez **Refuser.**</span><span class="sxs-lookup"><span data-stu-id="a0e15-203">To prevent DFCI, select **Opt-Out**.</span></span> 

> [!NOTE]
> <span data-ttu-id="a0e15-204">La page des paramètres de gestion UEFI et l’utilisation de DFCI sont actuellement disponibles pour Surface Pro 7+, Surface Laptop Go, Surface Book 3, Surface Laptop 3, Surface Pro 7 et Surface Pro X. Pour en savoir plus, consultez [La gestion Intune des paramètres UEFI Surface.](surface-manage-dfci-guide.md)</span><span class="sxs-lookup"><span data-stu-id="a0e15-204">The UEFI Management settings page and use of DFCI is currently available for Surface Pro 7+, Surface Laptop Go, Surface Book 3, Surface Laptop 3, Surface Pro 7, and Surface Pro X. To learn more, see [Intune management of Surface UEFI settings](surface-manage-dfci-guide.md).</span></span>

## <span data-ttu-id="a0e15-205">Menu UEFI : Quitter</span><span class="sxs-lookup"><span data-stu-id="a0e15-205">UEFI menu: Exit</span></span> 

<span data-ttu-id="a0e15-206">Utilisez le **bouton Redémarrer maintenant** dans la page **Quitter** pour quitter les paramètres UEFI, comme illustré dans la figure 9.</span><span class="sxs-lookup"><span data-stu-id="a0e15-206">Use the **Restart Now** button on the **Exit** page to exit UEFI settings, as shown in Figure 9.</span></span> 

![Quitter les paramètres UEFI Surface et redémarrer l’appareil](images/manage-surface-uefi-fig7.png "Exit Surface UEFI and restart the device")

*<span data-ttu-id="a0e15-208">Figure9.</span><span class="sxs-lookup"><span data-stu-id="a0e15-208">Figure 9.</span></span> <span data-ttu-id="a0e15-209">Cliquer sur Redémarrer maintenant pour fermer les paramètres UEFI Surface et redémarrer l’appareil</span><span class="sxs-lookup"><span data-stu-id="a0e15-209">Click Restart Now to exit Surface UEFI and restart the device</span></span>*

## <span data-ttu-id="a0e15-210">Écrans de démarrage UEFI Surface</span><span class="sxs-lookup"><span data-stu-id="a0e15-210">Surface UEFI boot screens</span></span>

<span data-ttu-id="a0e15-211">Lors d’une mise à jour du microprogramme de l’appareil Surface, que ce soit à l’aide de WindowsUpdate ou par une installation manuelle, les modifications ne prennent pas immédiatement effet sur l’appareil, mais plutôt lors du cycle de redémarrage suivant.</span><span class="sxs-lookup"><span data-stu-id="a0e15-211">When you update Surface device firmware, by using either Windows Update or manual installation, the updates are not applied immediately to the device, but instead during the next reboot cycle.</span></span> <span data-ttu-id="a0e15-212">Vous trouverez d’autres informations sur le processus de mise à jour du microprogramme Surface dans [Gérer les mises à jour du microprogramme et des pilotes Surface](https://docs.microsoft.com/surface/manage-surface-pro-3-firmware-updates).</span><span class="sxs-lookup"><span data-stu-id="a0e15-212">You can find out more about the Surface firmware update process in [Manage Surface driver and firmware updates](https://docs.microsoft.com/surface/manage-surface-pro-3-firmware-updates).</span></span> <span data-ttu-id="a0e15-213">La progression de la mise à jour du microprogramme s’affiche sur un écran avec des barres de progression de différentes couleurs indiquant le microprogramme de chaque composant.</span><span class="sxs-lookup"><span data-stu-id="a0e15-213">The progress of the firmware update is displayed on a screen with progress bars of differing colors to indicate the firmware for each component.</span></span> <span data-ttu-id="a0e15-214">La barre de progression de chaque composant est indiquée dans les figures 9 à 18.</span><span class="sxs-lookup"><span data-stu-id="a0e15-214">Each component’s progress bar is shown in Figures 9 through 18.</span></span>

![Mise à jour du microprogramme UEFI Surface avec barre de progression bleue](images/manage-surface-uefi-fig8.png "Surface UEFI firmware update with blue progress bar")

*<span data-ttu-id="a0e15-216">Figure10.</span><span class="sxs-lookup"><span data-stu-id="a0e15-216">Figure 10.</span></span> <span data-ttu-id="a0e15-217">La mise à jour du microprogramme UEFI Surface affiche une barre de progression bleue</span><span class="sxs-lookup"><span data-stu-id="a0e15-217">The Surface UEFI firmware update displays a blue progress bar</span></span>*

![Microprogramme du contrôleur système embarqué avec barre de progression verte](images/manage-surface-uefi-fig9.png "System Embedded Controller firmware with green progress bar")

*<span data-ttu-id="a0e15-219">Figure11.</span><span class="sxs-lookup"><span data-stu-id="a0e15-219">Figure 11.</span></span> <span data-ttu-id="a0e15-220">La mise à jour du microprogramme du contrôleur système embarqué affiche une barre de progression verte</span><span class="sxs-lookup"><span data-stu-id="a0e15-220">The System Embedded Controller firmware update displays a green progress bar</span></span>*

![Mise à jour du microprogramme du contrôleur SAM avec barre de progression orange](images/manage-surface-uefi-fig10.png "SAM Controller firmware update with orange progress bar")

*<span data-ttu-id="a0e15-222">Figure12.</span><span class="sxs-lookup"><span data-stu-id="a0e15-222">Figure 12.</span></span> <span data-ttu-id="a0e15-223">La mise à jour du microprogramme du contrôleur SAM affiche une barre de progression orange</span><span class="sxs-lookup"><span data-stu-id="a0e15-223">The SAM Controller firmware update displays an orange progress bar</span></span>*

![Microprogramme du moteur de gestion Intel avec barre de progression rouge](images/manage-surface-uefi-fig11.png "Intel Management Engine firmware with red progress bar")

*<span data-ttu-id="a0e15-225">Figure13.</span><span class="sxs-lookup"><span data-stu-id="a0e15-225">Figure 13.</span></span> <span data-ttu-id="a0e15-226">La mise à jour du microprogramme du moteur de gestion Intel affiche une barre de progression rouge</span><span class="sxs-lookup"><span data-stu-id="a0e15-226">The Intel Management Engine firmware update displays a red progress bar</span></span>*

![Microprogramme du clavier tactile de Surface avec barre de progression grise](images/manage-surface-uefi-fig12.png "Surface touch firmware with gray progress bar")

*<span data-ttu-id="a0e15-228">Figure14.</span><span class="sxs-lookup"><span data-stu-id="a0e15-228">Figure 14.</span></span> <span data-ttu-id="a0e15-229">La mise à jour du microprogramme du clavier tactile de Surface affiche une barre de progression grise</span><span class="sxs-lookup"><span data-stu-id="a0e15-229">The Surface touch firmware update displays a gray progress bar</span></span>*

![Microprogramme SURFACE FIRMWARE avec barre de progression vert clair](images/manage-surface-uefi-fig13.png "Surface touch firmware with light green progress bar")

*<span data-ttu-id="a0e15-231">Figure15.</span><span class="sxs-lookup"><span data-stu-id="a0e15-231">Figure 15.</span></span> <span data-ttu-id="a0e15-232">La mise à jour du microprogramme SURFACE FIRMWARE affiche une barre de progression vert clair</span><span class="sxs-lookup"><span data-stu-id="a0e15-232">The Surface KIP firmware update displays a light green progress bar</span></span>*

![Microprogramme ISH Surface avec barre de progression rose](images/manage-surface-uefi-fig14.png "Surface ISH firmware with pink progress bar")

*<span data-ttu-id="a0e15-234">Figure 16 La mise à jour du microprogramme ish surface affiche une barre de progression rose clair</span><span class="sxs-lookup"><span data-stu-id="a0e15-234">Figure 16 The Surface ISH firmware update displays a light pink progress bar</span></span>*

![Microprogramme Surface Trackpad avec barre de progression grise](images/manage-surface-uefi-fig15.png "Surface Trackpad firmware with gray progress bar")

*<span data-ttu-id="a0e15-236">Figure17.</span><span class="sxs-lookup"><span data-stu-id="a0e15-236">Figure 17.</span></span> <span data-ttu-id="a0e15-237">La mise à jour du microprogramme du Surface Trackpad affiche une barre de progression rose</span><span class="sxs-lookup"><span data-stu-id="a0e15-237">The Surface Trackpad firmware update displays a pink progress bar</span></span>*

![Microprogramme TCON Surface avec barre de progression gris clair](images/manage-surface-uefi-fig16.png "Surface TCON firmware with light gray progress bar")

*<span data-ttu-id="a0e15-239">Figure18.</span><span class="sxs-lookup"><span data-stu-id="a0e15-239">Figure 18.</span></span> <span data-ttu-id="a0e15-240">La mise à jour du microprogramme TCON Surface affiche une barre de progression gris clair</span><span class="sxs-lookup"><span data-stu-id="a0e15-240">The Surface TCON firmware update displays a light gray progress bar</span></span>*


![Microprogramme du TPM Surface avec barre de progression violet clair](images/manage-surface-uefi-fig17.png "Surface TPM firmware with purple progress bar")

*<span data-ttu-id="a0e15-242">Figure19.</span><span class="sxs-lookup"><span data-stu-id="a0e15-242">Figure 19.</span></span> <span data-ttu-id="a0e15-243">La mise à jour du microprogramme du TPM Surface affiche une barre de progression violet</span><span class="sxs-lookup"><span data-stu-id="a0e15-243">The Surface TPM firmware update displays a purple progress bar</span></span>*


>[!NOTE]
><span data-ttu-id="a0e15-244">Un message d’avertissement supplémentaire qui indique que le démarrage sécurisé est désactivé s’affiche, comme le montre la figure 19.</span><span class="sxs-lookup"><span data-stu-id="a0e15-244">An additional warning message that indicates Secure Boot is disabled is displayed, as shown in Figure 19.</span></span>

![Écran de démarrage Surface indiquant que le démarrage sécurisé a été désactivé.](images/manage-surface-uefi-fig18.png "Surface boot screen that indicates Secure Boot has been disabled")

*<span data-ttu-id="a0e15-246">Figure20.</span><span class="sxs-lookup"><span data-stu-id="a0e15-246">Figure 20.</span></span> <span data-ttu-id="a0e15-247">Écran de démarrage Surface indiquant que le démarrage sécurisé a été désactivé dans les paramètres UEFI Surface</span><span class="sxs-lookup"><span data-stu-id="a0e15-247">Surface boot screen that indicates Secure Boot has been disabled in Surface UEFI settings</span></span>*

## <span data-ttu-id="a0e15-248">Références</span><span class="sxs-lookup"><span data-stu-id="a0e15-248">References</span></span>

1. <span data-ttu-id="a0e15-249">Surface Go et Surface Go 2 utilisent une ueFI tierce et ne sont pas en charge DFCI.</span><span class="sxs-lookup"><span data-stu-id="a0e15-249">Surface Go and Surface Go 2 use a third-party UEFI and do not support DFCI.</span></span> 

## <span data-ttu-id="a0e15-250">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="a0e15-250">Related topics</span></span>

- [<span data-ttu-id="a0e15-251">Gestion Intune des paramètres de surface UEFI</span><span class="sxs-lookup"><span data-stu-id="a0e15-251">Intune management of Surface UEFI settings</span></span>](surface-manage-dfci-guide.md)

-  [<span data-ttu-id="a0e15-252">Mode de gestion SurfaceEnterprise</span><span class="sxs-lookup"><span data-stu-id="a0e15-252">Surface Enterprise Management Mode</span></span>](surface-enterprise-management-mode.md)
