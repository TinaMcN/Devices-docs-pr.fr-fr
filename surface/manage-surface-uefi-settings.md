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
ms.date: 10/12/2020
ms.openlocfilehash: 218f98b23adcb7bae2af92655d85144c6e5665e6
ms.sourcegitcommit: c1efb75e8524193bdc0a5f7496dc23a92ac665c8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/12/2020
ms.locfileid: "11114722"
---
# <span data-ttu-id="fed20-104">Gérer les paramètres UEFI Surface</span><span class="sxs-lookup"><span data-stu-id="fed20-104">Manage Surface UEFI settings</span></span>

<span data-ttu-id="fed20-105">Toutes les générations actuelles et futures des appareils surface utilisent une interface de microprogramme unique unifiée (UEFI) conçue par Microsoft en particulier pour ces appareils.</span><span class="sxs-lookup"><span data-stu-id="fed20-105">All current and future generations of Surface devices use a unique Unified Extensible Firmware Interface (UEFI) engineered by Microsoft specifically for these devices.</span></span> <span data-ttu-id="fed20-106">Les paramètres de surface UEFI permettent d’activer ou de désactiver les appareils et composants intégrés, de protéger les paramètres UEFI et de modifier les paramètres de démarrage de l’appareil surface.</span><span class="sxs-lookup"><span data-stu-id="fed20-106">Surface UEFI settings provide the ability to enable or disable built-in devices and components, protect UEFI settings from being changed, and adjust the Surface device boot settings.</span></span> 

## <span data-ttu-id="fed20-107">Produits pris en charge</span><span class="sxs-lookup"><span data-stu-id="fed20-107">Supported products</span></span>

<span data-ttu-id="fed20-108">La gestion UEFI est prise en charge sur les éléments suivants:</span><span class="sxs-lookup"><span data-stu-id="fed20-108">UEFI management is supported on the following:</span></span> 

- <span data-ttu-id="fed20-109">Surface Pro 4, surface Pro (5e génération), surface Pro 6, surface Pro 7, surface Pro X</span><span class="sxs-lookup"><span data-stu-id="fed20-109">Surface Pro 4, Surface Pro (5th Gen), Surface Pro 6, Surface Pro 7, Surface Pro X</span></span>
- <span data-ttu-id="fed20-110">Surface Laptop (1ère génération), surface Laptop 2, surface Laptop 3, surface Laptop Go</span><span class="sxs-lookup"><span data-stu-id="fed20-110">Surface Laptop (1st Gen), Surface Laptop 2, Surface Laptop 3, Surface Laptop Go</span></span>
- <span data-ttu-id="fed20-111">Surface Studio (1ère génération), surface Studio 2</span><span class="sxs-lookup"><span data-stu-id="fed20-111">Surface Studio (1st Gen), Surface Studio 2</span></span>
- <span data-ttu-id="fed20-112">Surface Book, surface Book 2, surface Book 3</span><span class="sxs-lookup"><span data-stu-id="fed20-112">Surface Book, Surface Book 2, Surface Book 3</span></span>
- <span data-ttu-id="fed20-113">Surface Go, surface Go 2</span><span class="sxs-lookup"><span data-stu-id="fed20-113">Surface Go, Surface Go 2</span></span>

## <span data-ttu-id="fed20-114">Prise en charge de la gestion basée sur le Cloud</span><span class="sxs-lookup"><span data-stu-id="fed20-114">Support for cloud-based management</span></span>

<span data-ttu-id="fed20-115">Les profils d’interface de configuration de microprogramme de périphériques (DFCI) intégrés à Microsoft Intune (désormais disponibles en préversion publique) permettent de faire en sorte que la gestion de surface UEFI étende la pile de gestion moderne au niveau matériel UEFI.</span><span class="sxs-lookup"><span data-stu-id="fed20-115">With Device Firmware Configuration Interface (DFCI) profiles built into Microsoft Intune (now available in public preview), Surface UEFI management extends the modern management stack down to the UEFI hardware level.</span></span> <span data-ttu-id="fed20-116">DFCI prend en charge la mise en service des fonctions d’approvisionnement nulle, élimine les mots de passe BIOS et contrôle les paramètres de sécurité, notamment les options de démarrage et les périphériques intégrés, et vous permet de créer des scénarios de sécurité avancée à l’avenir.</span><span class="sxs-lookup"><span data-stu-id="fed20-116">DFCI supports zero-touch provisioning, eliminates BIOS passwords, provides control of security settings including boot options and built-in peripherals, and lays the groundwork for advanced security scenarios in the future.</span></span> <span data-ttu-id="fed20-117">DFCI est actuellement disponible pour surface Pro 7, surface Pro X et surface Laptop 3.</span><span class="sxs-lookup"><span data-stu-id="fed20-117">DFCI is currently available for Surface Pro 7, Surface Pro X, and Surface Laptop 3.</span></span> <span data-ttu-id="fed20-118">Pour plus d’informations, reportez-vous à la rubrique [gestion Intune des paramètres de surface UEFI](surface-manage-dfci-guide.md).</span><span class="sxs-lookup"><span data-stu-id="fed20-118">For more information, refer to [Intune management of Surface UEFI settings](surface-manage-dfci-guide.md).</span></span>

## <span data-ttu-id="fed20-119">Ouvrir le menu surface UEFI</span><span class="sxs-lookup"><span data-stu-id="fed20-119">Open Surface UEFI menu</span></span>

<span data-ttu-id="fed20-120">Pour ajuster les paramètres UEFI lors du démarrage du système:</span><span class="sxs-lookup"><span data-stu-id="fed20-120">To adjust UEFI settings during system startup:</span></span>

1. <span data-ttu-id="fed20-121">Arrêtez votre surface et attendez environ 10 secondes pour vous assurer qu’il est désactivé.</span><span class="sxs-lookup"><span data-stu-id="fed20-121">Shut down your Surface and wait about 10 seconds to make sure it's off.</span></span>
2. <span data-ttu-id="fed20-122">Appuyez de façon prolongée sur le bouton **volume** enfoncé et, en même temps, appuyez sur le **bouton d’alimentation** et relâchez-le.</span><span class="sxs-lookup"><span data-stu-id="fed20-122">Press and hold the **Volume-up** button  and - at the same time - press and release the **Power button.**</span></span>
3. <span data-ttu-id="fed20-123">Lorsque le logo Microsoft ou surface apparaît à l’écran, appuyez sur le bouton **volume** enfoncé jusqu’à ce que l’écran UEFI apparaisse.</span><span class="sxs-lookup"><span data-stu-id="fed20-123">As the Microsoft or Surface logo appears on your screen, continue to hold the **Volume-up** button until the UEFI screen appears.</span></span>

## <span data-ttu-id="fed20-124">Page informations sur le PC UEFI</span><span class="sxs-lookup"><span data-stu-id="fed20-124">UEFI PC information page</span></span>

<span data-ttu-id="fed20-125">La page informations sur le PC inclut des informations détaillées sur votre périphérique surface:</span><span class="sxs-lookup"><span data-stu-id="fed20-125">The PC information page includes detailed information about your Surface device:</span></span> 

- <span data-ttu-id="fed20-126">**Modèle** : le modèle de votre appareil de surface s’affichera ici, par exemple surface Book 2 ou surface Pro 7.</span><span class="sxs-lookup"><span data-stu-id="fed20-126">**Model** – Your Surface device’s model will be displayed here, such as Surface Book 2 or Surface Pro 7.</span></span> <span data-ttu-id="fed20-127">La configuration exacte de votre appareil (notamment le processeur, la taille du disque ou la taille de la mémoire) n’apparaît pas.</span><span class="sxs-lookup"><span data-stu-id="fed20-127">The exact configuration of your device is not shown, (such as processor, disk size, or memory size).</span></span> 
- <span data-ttu-id="fed20-128">**UUID**: cet identificateur global unique est propre à votre appareil et sert à identifier l’appareil dans le cadre des processus de déploiement ou de gestion.</span><span class="sxs-lookup"><span data-stu-id="fed20-128">**UUID** – This Universally Unique Identification number is specific to your device and is used to identify the device during deployment or management.</span></span> 

- <span data-ttu-id="fed20-129">**Numéro de série**: ce numéro permet d’identifier cet appareil Surface spécifique pour les scénarios de support et d’étiquetage des ressources.</span><span class="sxs-lookup"><span data-stu-id="fed20-129">**Serial Number** – This number is used to identify this specific Surface device for asset tagging and support scenarios.</span></span>
- <span data-ttu-id="fed20-130">**Étiquette d’inventaire**: l’étiquette d’inventaire est affectée à l’appareil Surface avec l’[Outil d’étiquette d’inventaire](https://docs.microsoft.com/surface/assettag).</span><span class="sxs-lookup"><span data-stu-id="fed20-130">**Asset Tag** – The asset tag is assigned to the Surface device with the [Asset Tag Tool](https://docs.microsoft.com/surface/assettag).</span></span> 

<span data-ttu-id="fed20-131">Ce champ fournit également des informations détaillées sur le microprogramme de votre appareil Surface.</span><span class="sxs-lookup"><span data-stu-id="fed20-131">You will also find detailed information about the firmware of your Surface device.</span></span> <span data-ttu-id="fed20-132">Les appareils Surface intègrent plusieurs composants internes exécutant chacun une version de microprogramme distincte.</span><span class="sxs-lookup"><span data-stu-id="fed20-132">Surface devices have several internal components that each run different versions of firmware.</span></span> <span data-ttu-id="fed20-133">La version de microprogramme de chacun des composants ci-après est indiquée sur la page **Informations du PC** (comme illustré à la Figure1):</span><span class="sxs-lookup"><span data-stu-id="fed20-133">The firmware version of each of the following devices is displayed on the **PC information** page (as shown in Figure 1):</span></span> 

- <span data-ttu-id="fed20-134">UEFI système</span><span class="sxs-lookup"><span data-stu-id="fed20-134">System UEFI</span></span> 

- <span data-ttu-id="fed20-135">Contrôleur SAM</span><span class="sxs-lookup"><span data-stu-id="fed20-135">SAM Controller</span></span> 

- <span data-ttu-id="fed20-136">Moteur de gestion Intel</span><span class="sxs-lookup"><span data-stu-id="fed20-136">Intel Management Engine</span></span> 

- <span data-ttu-id="fed20-137">Contrôleur système embarqué</span><span class="sxs-lookup"><span data-stu-id="fed20-137">System Embedded Controller</span></span> 

- <span data-ttu-id="fed20-138">Microprogramme du contrôleur tactile</span><span class="sxs-lookup"><span data-stu-id="fed20-138">Touch Firmware</span></span> 

![Informations système et informations sur les versions du microprogramme](images/manage-surface-uefi-figure-1.png "System information and firmware version information")

*<span data-ttu-id="fed20-140">Figure1.</span><span class="sxs-lookup"><span data-stu-id="fed20-140">Figure 1.</span></span> <span data-ttu-id="fed20-141">Informations système et informations sur les versions du microprogramme</span><span class="sxs-lookup"><span data-stu-id="fed20-141">System information and firmware version information</span></span>*

<span data-ttu-id="fed20-142">Vous trouverez des informations à jour sur la dernière version de microprogramme pour votre appareil Surface dans l’[Historique des mises à jour de MicrosoftSurface](https://www.microsoft.com/surface/support/install-update-activate/surface-update-history) de votre appareil.</span><span class="sxs-lookup"><span data-stu-id="fed20-142">You can find up-to-date information about the latest firmware version for your Surface device in the [Surface Update History](https://www.microsoft.com/surface/support/install-update-activate/surface-update-history) for your device.</span></span> 

## <span data-ttu-id="fed20-143">Page de sécurité UEFI</span><span class="sxs-lookup"><span data-stu-id="fed20-143">UEFI Security page</span></span> 

![Configurer les paramètres de sécurité UEFI Surface](images/manage-surface-uefi-fig4.png "Configure Surface UEFI security settings")

*<span data-ttu-id="fed20-145">Figure2.</span><span class="sxs-lookup"><span data-stu-id="fed20-145">Figure 2.</span></span> <span data-ttu-id="fed20-146">Configurer les paramètres de sécurité UEFI Surface</span><span class="sxs-lookup"><span data-stu-id="fed20-146">Configure Surface UEFI security settings</span></span>*

<span data-ttu-id="fed20-147">La page sécurité vous permet de définir un mot de passe pour protéger les paramètres UEFI.</span><span class="sxs-lookup"><span data-stu-id="fed20-147">The Security page allows you to set a password to protect UEFI settings.</span></span> <span data-ttu-id="fed20-148">Vous devez entrer ce mot de passe lorsque vous démarrez l’appareil Surface en mode UEFI.</span><span class="sxs-lookup"><span data-stu-id="fed20-148">This password must be entered when you boot the Surface device to UEFI.</span></span> <span data-ttu-id="fed20-149">Le mot de passe peut contenir les caractères suivants (comme illustré dans la figure 3):</span><span class="sxs-lookup"><span data-stu-id="fed20-149">The password can contain the following characters (as shown in Figure 3):</span></span> 

- <span data-ttu-id="fed20-150">Lettres majuscules: A-Z</span><span class="sxs-lookup"><span data-stu-id="fed20-150">Uppercase letters: A-Z</span></span> 

- <span data-ttu-id="fed20-151">Lettres minuscules: a-z</span><span class="sxs-lookup"><span data-stu-id="fed20-151">Lowercase letters: a-z</span></span> 

- <span data-ttu-id="fed20-152">Chiffres: 1-0</span><span class="sxs-lookup"><span data-stu-id="fed20-152">Numbers: 1-0</span></span> 

- <span data-ttu-id="fed20-153">Caractères spéciaux:! @ # $% ^& \* ()? <>{} []-_ = + |.,;: "'"</span><span class="sxs-lookup"><span data-stu-id="fed20-153">Special characters: !@#$%^&\*()?<>{}[]-_=+|.,;:’\`”</span></span> 

<span data-ttu-id="fed20-154">Le mot de passe doit comporter au moins 6caractères et respecte la casse.</span><span class="sxs-lookup"><span data-stu-id="fed20-154">The password must be at least 6 characters and is case sensitive.</span></span> 

![Ajouter un mot de passe pour protéger les paramètres UEFI Surface](images/manage-surface-uefi-fig2.png "Add a password to protect Surface UEFI settings")

*<span data-ttu-id="fed20-156">Figure3.</span><span class="sxs-lookup"><span data-stu-id="fed20-156">Figure 3.</span></span> <span data-ttu-id="fed20-157">Ajouter un mot de passe pour protéger les paramètres UEFI Surface</span><span class="sxs-lookup"><span data-stu-id="fed20-157">Add a password to protect Surface UEFI settings</span></span>*

<span data-ttu-id="fed20-158">La page Sécurité vous permet également de modifier la configuration du démarrage sécurisé sur votre appareil Surface.</span><span class="sxs-lookup"><span data-stu-id="fed20-158">On the Security page you can also change the configuration of Secure Boot on your Surface device.</span></span> <span data-ttu-id="fed20-159">La technologie de démarrage sécurisé empêche tout démarrage d’un code de démarrage non autorisé sur votre appareil Surface, et vous offre ainsi une protection contre les infections par programmes malveillants de type bootkit ou rootkit.</span><span class="sxs-lookup"><span data-stu-id="fed20-159">Secure Boot technology prevents unauthorized boot code from booting on your Surface device, which protects against bootkit and rootkit-type malware infections.</span></span> <span data-ttu-id="fed20-160">Vous pouvez désactiver le démarrage sécurisé si vous souhaitez permettre à votre appareil Surface de démarrer des systèmes d’exploitation ou des médias de démarrage tiers.</span><span class="sxs-lookup"><span data-stu-id="fed20-160">You can disable Secure Boot to allow your Surface device to boot third-party operating systems or bootable media.</span></span> <span data-ttu-id="fed20-161">Vous pouvez également configurer le démarrage sécurisé pour travailler avec des certificats tiers, comme illustré dans la figure 4.</span><span class="sxs-lookup"><span data-stu-id="fed20-161">You can also configure Secure Boot to work with third-party certificates, as shown in Figure 4.</span></span> <span data-ttu-id="fed20-162">Apprenez-en davantage sur le [démarrage sécurisé](https://msdn.microsoft.com/windows/hardware/commercialize/manufacture/desktop/secure-boot-overview) dans la bibliothèque TechNet.</span><span class="sxs-lookup"><span data-stu-id="fed20-162">Read more about [Secure Boot](https://msdn.microsoft.com/windows/hardware/commercialize/manufacture/desktop/secure-boot-overview) in the TechNet Library.</span></span>

![Configurer le démarrage sécurisé](images/manage-surface-uefi-fig3.png "Configure Secure Boot")

*<span data-ttu-id="fed20-164">Figure4.</span><span class="sxs-lookup"><span data-stu-id="fed20-164">Figure 4.</span></span> <span data-ttu-id="fed20-165">Configurer le démarrage sécurisé</span><span class="sxs-lookup"><span data-stu-id="fed20-165">Configure Secure Boot</span></span>*

<span data-ttu-id="fed20-166">En fonction de votre appareil, vous serez peut-être en mesure de voir si votre TPM est activé ou désactivé.</span><span class="sxs-lookup"><span data-stu-id="fed20-166">Depending on your device, you may also be able to see if your TPM is enabled or disabled.</span></span> <span data-ttu-id="fed20-167">Si vous ne voyez pas le paramètre **activer le module de plateforme sécurisée**  , ouvrez TPM. msc dans Windows pour vérifier l’État, comme illustré dans la figure 5.</span><span class="sxs-lookup"><span data-stu-id="fed20-167">If you do not see the **Enable TPM**  setting, open tpm.msc in Windows to check the status, as shown in Figure 5.</span></span> <span data-ttu-id="fed20-168">Le module TPM permet d’authentifier le chiffrement des données de votre appareil avec BitLocker.</span><span class="sxs-lookup"><span data-stu-id="fed20-168">The TPM is used to authenticate encryption for your device’s data with BitLocker.</span></span> <span data-ttu-id="fed20-169">Pour en savoir plus, voir [vue d’ensemble de BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview).</span><span class="sxs-lookup"><span data-stu-id="fed20-169">To learn more, see [BitLocker overview](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview).</span></span> 

![Console du TPM](images/manage-surface-uefi-fig5-a.png "TPM console")

*<span data-ttu-id="fed20-171">Figure5.</span><span class="sxs-lookup"><span data-stu-id="fed20-171">Figure 5.</span></span> <span data-ttu-id="fed20-172">Console du TPM</span><span class="sxs-lookup"><span data-stu-id="fed20-172">TPM console</span></span>*


## <span data-ttu-id="fed20-173">Menu UEFI: périphériques</span><span class="sxs-lookup"><span data-stu-id="fed20-173">UEFI menu: Devices</span></span> 

<span data-ttu-id="fed20-174">La page appareils vous permet d’activer ou de désactiver des appareils et composants spécifiques, notamment:</span><span class="sxs-lookup"><span data-stu-id="fed20-174">The Devices page allows you to  enable or disable specific devices and components including:</span></span>

- <span data-ttu-id="fed20-175">Ports de station d’accueil et USB</span><span class="sxs-lookup"><span data-stu-id="fed20-175">Docking and USB Ports</span></span> 

- <span data-ttu-id="fed20-176">Emplacement pour carte mémoire Secure Digital ou MicroSD</span><span class="sxs-lookup"><span data-stu-id="fed20-176">MicroSD or SD Card Slot</span></span> 

- <span data-ttu-id="fed20-177">Caméra arrière</span><span class="sxs-lookup"><span data-stu-id="fed20-177">Rear Camera</span></span> 

- <span data-ttu-id="fed20-178">Caméra frontale</span><span class="sxs-lookup"><span data-stu-id="fed20-178">Front Camera</span></span> 

- <span data-ttu-id="fed20-179">Caméra infrarouge (IR)</span><span class="sxs-lookup"><span data-stu-id="fed20-179">Infrared (IR) Camera</span></span> 

- <span data-ttu-id="fed20-180">Wi-Fi et Bluetooth</span><span class="sxs-lookup"><span data-stu-id="fed20-180">Wi-Fi and Bluetooth</span></span> 

- <span data-ttu-id="fed20-181">Audio intégré (haut-parleurs et microphone)</span><span class="sxs-lookup"><span data-stu-id="fed20-181">Onboard Audio (Speakers and Microphone)</span></span> 

<span data-ttu-id="fed20-182">Chacun d’eux est répertorié avec un bouton **de** curseur que vous pouvez activer (activé) ou **désactivé** (désactivé), comme illustré dans la figure 6.</span><span class="sxs-lookup"><span data-stu-id="fed20-182">Each device is listed with a slider button that you can move to **On** (enabled) or **Off** (disabled) position, as shown in Figure 6.</span></span> 

![Activer et désactiver des périphériques spécifiques](images/manage-surface-uefi-fig5a.png "Enable and disable specific devices")

*<span data-ttu-id="fed20-184">Figure6.</span><span class="sxs-lookup"><span data-stu-id="fed20-184">Figure 6.</span></span> <span data-ttu-id="fed20-185">Activer et désactiver des périphériques spécifiques</span><span class="sxs-lookup"><span data-stu-id="fed20-185">Enable and disable specific devices</span></span>*

## <span data-ttu-id="fed20-186">Menu UEFI: configuration de démarrage</span><span class="sxs-lookup"><span data-stu-id="fed20-186">UEFI menu: Boot configuration</span></span> 

<span data-ttu-id="fed20-187">La page Configuration de démarrage vous permet de changer l’ordre de vos périphériques de démarrage et d’activer ou de désactiver les appareils suivants:</span><span class="sxs-lookup"><span data-stu-id="fed20-187">The Boot Configuration page allows you to change the order of your boot devices as well as enable or disable boot of the following devices:</span></span> 

- <span data-ttu-id="fed20-188">Gestionnaire de démarrage Windows</span><span class="sxs-lookup"><span data-stu-id="fed20-188">Windows Boot Manager</span></span> 

- <span data-ttu-id="fed20-189">Stockage USB</span><span class="sxs-lookup"><span data-stu-id="fed20-189">USB Storage</span></span> 

- <span data-ttu-id="fed20-190">Réseau PXE (Preboot Execution Environment)</span><span class="sxs-lookup"><span data-stu-id="fed20-190">PXE Network</span></span> 

- <span data-ttu-id="fed20-191">Stockage interne</span><span class="sxs-lookup"><span data-stu-id="fed20-191">Internal Storage</span></span> 

<span data-ttu-id="fed20-192">Vous pouvez démarrer immédiatement l’appareil à partir d’un périphérique spécifique, ou effectuer un mouvement de balayage vers la gauche sur l’entrée de ce périphérique dans la liste en utilisant l’écran tactile.</span><span class="sxs-lookup"><span data-stu-id="fed20-192">You can boot from a specific device immediately, or you can swipe left on that device’s entry in the list using the touchscreen.</span></span> <span data-ttu-id="fed20-193">Vous pouvez également démarrer immédiatement à partir d’un périphérique USB ou d’un adaptateur Ethernet USB lorsque l’appareil Surface est éteint en appuyant simultanément sur le bouton **Baisser le volume** et sur le bouton **Marche/Arrêt**.</span><span class="sxs-lookup"><span data-stu-id="fed20-193">You can also boot immediately to a USB device or USB Ethernet adapter when the Surface device is powered off by pressing the **Volume Down** button and the **Power** button simultaneously.</span></span> 

<span data-ttu-id="fed20-194">Pour que l’ordre de démarrage spécifié prenne effet, vous devez définir l’option Activer le mode de **démarrage alternatif** sur **activé**, comme illustré dans la figure 7.</span><span class="sxs-lookup"><span data-stu-id="fed20-194">For the specified boot order to take effect, you must set the **Enable Alternate Boot Sequence** option to **On**, as shown in Figure 7.</span></span> 

![Configurer l’ordre de démarrage de votre appareil Surface](images/manage-surface-uefi-fig6.png "Configure the boot order for your Surface device")

*<span data-ttu-id="fed20-196">Figure7.</span><span class="sxs-lookup"><span data-stu-id="fed20-196">Figure 7.</span></span> <span data-ttu-id="fed20-197">Configurer l’ordre de démarrage de votre appareil Surface</span><span class="sxs-lookup"><span data-stu-id="fed20-197">Configure the boot order for your Surface device</span></span>* 

<span data-ttu-id="fed20-198">Vous pouvez également activer et désactiver la prise en charge d’IPv6 pour PXE par le biais de l’option **Activer IPv6 pour le démarrage du réseau PXE**, par exemple lorsque vous effectuez un déploiement Windows à l’aide de PXE et que le serveur PXE est uniquement configuré pour IPv4.</span><span class="sxs-lookup"><span data-stu-id="fed20-198">You can also turn on and off IPv6 support for PXE with the **Enable IPv6 for PXE Network Boot** option, for example when performing a Windows deployment using PXE where the PXE server is configured for IPv4 only.</span></span>  

## <span data-ttu-id="fed20-199">Menu UEFI: gestion</span><span class="sxs-lookup"><span data-stu-id="fed20-199">UEFI menu: Management</span></span>
<span data-ttu-id="fed20-200">La page de gestion vous permet de gérer l’utilisation de la gestion de la fonction TouchWare de zéro et d’autres fonctionnalités sur les appareils éligibles, y compris surface Pro 7, surface Pro X et surface Laptop 3.</span><span class="sxs-lookup"><span data-stu-id="fed20-200">The Management page allows you to manage use of Zero Touch UEFI Management and other features on eligible devices including Surface Pro 7, Surface Pro X, and Surface Laptop 3.</span></span>  

![<span data-ttu-id="fed20-201">Vous pouvez gérer l’accès à la gestion de la fonction TouchWare de zéro et aux autres fonctionnalités ](images/manage-surface-uefi-fig7a.png "Manage access to Zero Touch UEFI Management and other features")
 *figure 8. Gestion de l’accès à la gestion de la fonction TouchWare de zéro et aux autres fonctionnalités*</span><span class="sxs-lookup"><span data-stu-id="fed20-201">Manage access to Zero Touch UEFI Management and other features](images/manage-surface-uefi-fig7a.png "Manage access to Zero Touch UEFI Management and other features")
*Figure 8. Manage access to Zero Touch UEFI Management and other features*</span></span> 


<span data-ttu-id="fed20-202">La gestion de la fonction TouchWare de Zero vous permet de gérer les paramètres UEFI à distance à l’aide d’un profil d’appareil dans Intune appelé interface de configuration du microprogramme de périphériques (DFCI).</span><span class="sxs-lookup"><span data-stu-id="fed20-202">Zero Touch UEFI Management lets you remotely manage UEFI settings  by using a device profile within Intune called Device Firmware Configuration Interface (DFCI).</span></span> <span data-ttu-id="fed20-203">Si vous ne configurez pas ce paramètre, la possibilité de gérer les appareils éligibles avec DFCI est définie sur **Ready**.</span><span class="sxs-lookup"><span data-stu-id="fed20-203">If you do not configure this setting, the ability to manage eligible devices with DFCI is set to **Ready**.</span></span> <span data-ttu-id="fed20-204">Pour empêcher DFCI, sélectionnez **refuser**.</span><span class="sxs-lookup"><span data-stu-id="fed20-204">To prevent DFCI, select **Opt-Out**.</span></span> 

> [!NOTE]
> <span data-ttu-id="fed20-205">La page des paramètres de gestion UEFI et l’utilisation de DFCI est uniquement disponible dans surface Pro 7, surface Pro X et surface Laptop 3.</span><span class="sxs-lookup"><span data-stu-id="fed20-205">The UEFI Management settings page and use of DFCI is only available on Surface Pro 7, Surface Pro X, and Surface Laptop 3.</span></span>  

<span data-ttu-id="fed20-206">Pour plus d’informations, reportez-vous à la rubrique [gestion Intune des paramètres de surface UEFI](surface-manage-dfci-guide.md).</span><span class="sxs-lookup"><span data-stu-id="fed20-206">For more information, refer to [Intune management of Surface UEFI settings](surface-manage-dfci-guide.md).</span></span>

## <span data-ttu-id="fed20-207">Menu UEFI: quitter</span><span class="sxs-lookup"><span data-stu-id="fed20-207">UEFI menu: Exit</span></span> 

<span data-ttu-id="fed20-208">Utilisez le bouton **redémarrer maintenant** sur la page de **sortie** pour quitter les paramètres UEFI, comme illustré dans la figure 9.</span><span class="sxs-lookup"><span data-stu-id="fed20-208">Use the **Restart Now** button on the **Exit** page to exit UEFI settings, as shown in Figure 9.</span></span> 

![Quitter les paramètres UEFI Surface et redémarrer l’appareil](images/manage-surface-uefi-fig7.png "Exit Surface UEFI and restart the device")

*<span data-ttu-id="fed20-210">Figure9.</span><span class="sxs-lookup"><span data-stu-id="fed20-210">Figure 9.</span></span> <span data-ttu-id="fed20-211">Cliquer sur Redémarrer maintenant pour fermer les paramètres UEFI Surface et redémarrer l’appareil</span><span class="sxs-lookup"><span data-stu-id="fed20-211">Click Restart Now to exit Surface UEFI and restart the device</span></span>*

## <span data-ttu-id="fed20-212">Écrans de démarrage UEFI Surface</span><span class="sxs-lookup"><span data-stu-id="fed20-212">Surface UEFI boot screens</span></span>

<span data-ttu-id="fed20-213">Lors d’une mise à jour du microprogramme de l’appareil Surface, que ce soit à l’aide de WindowsUpdate ou par une installation manuelle, les modifications ne prennent pas immédiatement effet sur l’appareil, mais plutôt lors du cycle de redémarrage suivant.</span><span class="sxs-lookup"><span data-stu-id="fed20-213">When you update Surface device firmware, by using either Windows Update or manual installation, the updates are not applied immediately to the device, but instead during the next reboot cycle.</span></span> <span data-ttu-id="fed20-214">Vous trouverez d’autres informations sur le processus de mise à jour du microprogramme Surface dans [Gérer les mises à jour du microprogramme et des pilotes Surface](https://docs.microsoft.com/surface/manage-surface-pro-3-firmware-updates).</span><span class="sxs-lookup"><span data-stu-id="fed20-214">You can find out more about the Surface firmware update process in [Manage Surface driver and firmware updates](https://docs.microsoft.com/surface/manage-surface-pro-3-firmware-updates).</span></span> <span data-ttu-id="fed20-215">La progression de la mise à jour du microprogramme s’affiche sur un écran avec des barres de progression de différentes couleurs indiquant le microprogramme de chaque composant.</span><span class="sxs-lookup"><span data-stu-id="fed20-215">The progress of the firmware update is displayed on a screen with progress bars of differing colors to indicate the firmware for each component.</span></span> <span data-ttu-id="fed20-216">La barre de progression de chaque composant est affichée dans les figures 9 à 18.</span><span class="sxs-lookup"><span data-stu-id="fed20-216">Each component’s progress bar is shown in Figures 9 through 18.</span></span>

![Mise à jour du microprogramme UEFI Surface avec barre de progression bleue](images/manage-surface-uefi-fig8.png "Surface UEFI firmware update with blue progress bar")

*<span data-ttu-id="fed20-218">Figure10.</span><span class="sxs-lookup"><span data-stu-id="fed20-218">Figure 10.</span></span> <span data-ttu-id="fed20-219">La mise à jour du microprogramme UEFI Surface affiche une barre de progression bleue</span><span class="sxs-lookup"><span data-stu-id="fed20-219">The Surface UEFI firmware update displays a blue progress bar</span></span>*

![Microprogramme du contrôleur système embarqué avec barre de progression verte](images/manage-surface-uefi-fig9.png "System Embedded Controller firmware with green progress bar")

*<span data-ttu-id="fed20-221">Figure11.</span><span class="sxs-lookup"><span data-stu-id="fed20-221">Figure 11.</span></span> <span data-ttu-id="fed20-222">La mise à jour du microprogramme du contrôleur système embarqué affiche une barre de progression verte</span><span class="sxs-lookup"><span data-stu-id="fed20-222">The System Embedded Controller firmware update displays a green progress bar</span></span>*

![Mise à jour du microprogramme du contrôleur SAM avec barre de progression orange](images/manage-surface-uefi-fig10.png "SAM Controller firmware update with orange progress bar")

*<span data-ttu-id="fed20-224">Figure12.</span><span class="sxs-lookup"><span data-stu-id="fed20-224">Figure 12.</span></span> <span data-ttu-id="fed20-225">La mise à jour du microprogramme du contrôleur SAM affiche une barre de progression orange</span><span class="sxs-lookup"><span data-stu-id="fed20-225">The SAM Controller firmware update displays an orange progress bar</span></span>*

![Microprogramme du moteur de gestion Intel avec barre de progression rouge](images/manage-surface-uefi-fig11.png "Intel Management Engine firmware with red progress bar")

*<span data-ttu-id="fed20-227">Figure13.</span><span class="sxs-lookup"><span data-stu-id="fed20-227">Figure 13.</span></span> <span data-ttu-id="fed20-228">La mise à jour du microprogramme du moteur de gestion Intel affiche une barre de progression rouge</span><span class="sxs-lookup"><span data-stu-id="fed20-228">The Intel Management Engine firmware update displays a red progress bar</span></span>*

![Microprogramme du clavier tactile de Surface avec barre de progression grise](images/manage-surface-uefi-fig12.png "Surface touch firmware with gray progress bar")

*<span data-ttu-id="fed20-230">Figure14.</span><span class="sxs-lookup"><span data-stu-id="fed20-230">Figure 14.</span></span> <span data-ttu-id="fed20-231">La mise à jour du microprogramme du clavier tactile de Surface affiche une barre de progression grise</span><span class="sxs-lookup"><span data-stu-id="fed20-231">The Surface touch firmware update displays a gray progress bar</span></span>*

![Microprogramme de surface pour microprogramme avec une barre de progression verte claire](images/manage-surface-uefi-fig13.png "Surface touch firmware with light green progress bar")

*<span data-ttu-id="fed20-233">Figure15.</span><span class="sxs-lookup"><span data-stu-id="fed20-233">Figure 15.</span></span> <span data-ttu-id="fed20-234">La mise à jour du microprogramme surface-en-voyant affiche une barre de progression verte</span><span class="sxs-lookup"><span data-stu-id="fed20-234">The Surface KIP firmware update displays a light green progress bar</span></span>*

![Microprogramme ISH surface avec barre de progression rose](images/manage-surface-uefi-fig14.png "Surface ISH firmware with pink progress bar")

*<span data-ttu-id="fed20-236">Figure 16 la mise à jour de surface ISH microprogramme affiche une barre de progression rose clair</span><span class="sxs-lookup"><span data-stu-id="fed20-236">Figure 16 The Surface ISH firmware update displays a light pink progress bar</span></span>*

![Microprogramme pavé tactile surface avec une barre de progression grise](images/manage-surface-uefi-fig15.png "Surface Trackpad firmware with gray progress bar")

*<span data-ttu-id="fed20-238">Figure17.</span><span class="sxs-lookup"><span data-stu-id="fed20-238">Figure 17.</span></span> <span data-ttu-id="fed20-239">La mise à jour de surface pavé tactile microprogramme affiche une barre de progression rose</span><span class="sxs-lookup"><span data-stu-id="fed20-239">The Surface Trackpad firmware update displays a pink progress bar</span></span>*

![Microprogramme TCON surface avec une barre de progression gris clair](images/manage-surface-uefi-fig16.png "Surface TCON firmware with light gray progress bar")

*<span data-ttu-id="fed20-241">Figure18.</span><span class="sxs-lookup"><span data-stu-id="fed20-241">Figure 18.</span></span> <span data-ttu-id="fed20-242">La mise à jour de surface TCON microprogramme affiche une barre de progression gris clair</span><span class="sxs-lookup"><span data-stu-id="fed20-242">The Surface TCON firmware update displays a light gray progress bar</span></span>*


![Microprogramme GPC de surface avec barre de progression pourpre clair](images/manage-surface-uefi-fig17.png "Surface TPM firmware with purple progress bar")

*<span data-ttu-id="fed20-244">Figure19.</span><span class="sxs-lookup"><span data-stu-id="fed20-244">Figure 19.</span></span> <span data-ttu-id="fed20-245">La mise à jour du microprogramme de surface GPC affiche une barre de progression pourpre</span><span class="sxs-lookup"><span data-stu-id="fed20-245">The Surface TPM firmware update displays a purple progress bar</span></span>*


>[!NOTE]
><span data-ttu-id="fed20-246">Un message d’avertissement supplémentaire indiquant le démarrage sécurisé est désactivé s’affiche, comme illustré dans la figure 19.</span><span class="sxs-lookup"><span data-stu-id="fed20-246">An additional warning message that indicates Secure Boot is disabled is displayed, as shown in Figure 19.</span></span>

![Écran de démarrage Surface indiquant que le démarrage sécurisé a été désactivé.](images/manage-surface-uefi-fig18.png "Surface boot screen that indicates Secure Boot has been disabled")

*<span data-ttu-id="fed20-248">Figure20.</span><span class="sxs-lookup"><span data-stu-id="fed20-248">Figure 20.</span></span> <span data-ttu-id="fed20-249">Écran de démarrage Surface indiquant que le démarrage sécurisé a été désactivé dans les paramètres UEFI Surface</span><span class="sxs-lookup"><span data-stu-id="fed20-249">Surface boot screen that indicates Secure Boot has been disabled in Surface UEFI settings</span></span>*

## <span data-ttu-id="fed20-250">Rubriques associées</span><span class="sxs-lookup"><span data-stu-id="fed20-250">Related topics</span></span>

- [<span data-ttu-id="fed20-251">Gestion Intune des paramètres de surface UEFI</span><span class="sxs-lookup"><span data-stu-id="fed20-251">Intune management of Surface UEFI settings</span></span>](surface-manage-dfci-guide.md)

-  [<span data-ttu-id="fed20-252">Mode de gestion SurfaceEnterprise</span><span class="sxs-lookup"><span data-stu-id="fed20-252">Surface Enterprise Management Mode</span></span>](surface-enterprise-management-mode.md)
