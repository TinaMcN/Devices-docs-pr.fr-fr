---
title: Première installation de surface Hub 2
description: Découvrez comment procéder à la première configuration de surface Hub 2.
keywords: séparer les valeurs par des virgules
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 07/03/2019
ms.localizationpriority: Medium
ms.openlocfilehash: 47a393944c1b524931a6ac56962cc2cd60786007
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10833611"
---
# <span data-ttu-id="0e5e9-104">Première installation de surface Hub 2</span><span class="sxs-lookup"><span data-stu-id="0e5e9-104">First time Setup for Surface Hub 2S</span></span>

<span data-ttu-id="0e5e9-105">Lorsque vous démarrez surface Hub 2 pour la première fois, l’appareil accède automatiquement au mode d’installation du premier plan pour vous guider dans la configuration du compte et les paramètres associés.</span><span class="sxs-lookup"><span data-stu-id="0e5e9-105">When you first start Surface Hub 2S, the device automatically enters first time Setup mode to guide you through account configuration and related settings.</span></span>

## <span data-ttu-id="0e5e9-106">Configuration du compte surface Hub 2S</span><span class="sxs-lookup"><span data-stu-id="0e5e9-106">Configuring Surface Hub 2S account</span></span>

1. **<span data-ttu-id="0e5e9-107">Configurez vos paramètres régionaux.</span><span class="sxs-lookup"><span data-stu-id="0e5e9-107">Configure your locale.</span></span>** <span data-ttu-id="0e5e9-108">Entrez les informations de région, de langue, de disposition du clavier et de fuseau horaire.</span><span class="sxs-lookup"><span data-stu-id="0e5e9-108">Enter region, language, keyboard layout and time zone information.</span></span> <span data-ttu-id="0e5e9-109">Sélectionnez **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="0e5e9-109">Select **Next**.</span></span>

   ![\* Configurez vos paramètres régionaux \*](images/sh2-run1.png) <br>
1. **<span data-ttu-id="0e5e9-111">Se connecter à un réseau sans fil.</span><span class="sxs-lookup"><span data-stu-id="0e5e9-111">Connect  to a wireless network.</span></span>** <span data-ttu-id="0e5e9-112">Choisissez votre réseau sans fil préféré et sélectionnez **Next (suivant).**</span><span class="sxs-lookup"><span data-stu-id="0e5e9-112">Choose your preferred wireless network and select **Next.**</span></span>

- <span data-ttu-id="0e5e9-113">Cette option n’apparaît pas s’il s’agit d’une connexion à l’aide d’un câble Ethernet.</span><span class="sxs-lookup"><span data-stu-id="0e5e9-113">This option is not shown if connected using an Ethernet cable.</span></span>
- <span data-ttu-id="0e5e9-114">Vous ne pouvez pas vous connecter à un réseau sans fil sur les points d’accès (portails indirects) qui redirigent les demandes de connexion au site Web du fournisseur.</span><span class="sxs-lookup"><span data-stu-id="0e5e9-114">You cannot connect to a wireless network in hotspots (captive portals) that redirect sign-in requests to a provider’s website.</span></span>

3. **<span data-ttu-id="0e5e9-115">Entrez les informations de compte de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="0e5e9-115">Enter device account info.</span></span>** <span data-ttu-id="0e5e9-116">Utiliser **domaine\utilisateur** pour les environnements locaux et hybrides et l' **utilisateur \ @example. com** pour les environnements en ligne.</span><span class="sxs-lookup"><span data-stu-id="0e5e9-116">Use **domain\user** for on-premises and hybrid environments and **user\@example.com** for online environments.</span></span> <span data-ttu-id="0e5e9-117">Sélectionnez **Next (suivant).**</span><span class="sxs-lookup"><span data-stu-id="0e5e9-117">Select **Next.**</span></span>

   ![\* Entrer les informations sur le compte de l’appareil \*](images/sh2-run2.png) <br>
1. **<span data-ttu-id="0e5e9-119">Entrez des informations supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="0e5e9-119">Enter additional info.</span></span>** <span data-ttu-id="0e5e9-120">Le cas échéant, indiquez l’adresse de votre serveur Exchange, puis sélectionnez **suivant.**</span><span class="sxs-lookup"><span data-stu-id="0e5e9-120">If requested, provide your Exchange server address and then select **Next.**</span></span>

    ![\* Entrez plus d’informations; par exemple, nom du serveur Exchange \*](images/sh2-run3.png) <br>

1. **<span data-ttu-id="0e5e9-122">Nommez cet appareil.</span><span class="sxs-lookup"><span data-stu-id="0e5e9-122">Name this device.</span></span>** <span data-ttu-id="0e5e9-123">Entrez un nom pour votre appareil ou utilisez le nom suggéré en fonction du nom d’affichage de votre compte et du nom d’utilisateur principal [UPN].</span><span class="sxs-lookup"><span data-stu-id="0e5e9-123">Enter a name for your device or use the suggested one based on your account’s display name and user principle name [UPN].</span></span> <span data-ttu-id="0e5e9-124">**Sélectionnez Next (suivant**).</span><span class="sxs-lookup"><span data-stu-id="0e5e9-124">**Select Next**.</span></span>

- <span data-ttu-id="0e5e9-125">Le **nom convivial** est visible dans le coin inférieur gauche de surface Hub 2 et s’affiche lors de la projection sur le périphérique.</span><span class="sxs-lookup"><span data-stu-id="0e5e9-125">The **Friendly name** is visible on the bottom left corner of Surface Hub 2S and is shown when projecting to the device.</span></span>

- <span data-ttu-id="0e5e9-126">Le **nom** de l’appareil identifie l’appareil lorsqu’il est affilié à Active Directory ou Azure Active Directory, et lors de l’inscription de l’appareil avec Intune.</span><span class="sxs-lookup"><span data-stu-id="0e5e9-126">The **Device name** identifies the device when affiliated with Active Directory or Azure Active Directory, and when enrolling the device with Intune.</span></span>

  ![\* Nommer cet appareil \*](images/sh2-run4.png) <br>
 
## <span data-ttu-id="0e5e9-128">Configuration de comptes d’administrateur de périphériques</span><span class="sxs-lookup"><span data-stu-id="0e5e9-128">Configuring device admin accounts</span></span>

<span data-ttu-id="0e5e9-129">La première fois que vous configurez un administrateur d’appareil.</span><span class="sxs-lookup"><span data-stu-id="0e5e9-129">You can only set up device admins during first time Setup.</span></span> <span data-ttu-id="0e5e9-130">Pour plus d’informations, reportez-vous à la rubrique affiliation de l' [appareil surface Hub](https://docs.microsoft.com/surface-hub/surface-hub-2s-prepare-environment#device-affiliation).</span><span class="sxs-lookup"><span data-stu-id="0e5e9-130">For more information, refer to [Surface Hub 2S device affiliation](https://docs.microsoft.com/surface-hub/surface-hub-2s-prepare-environment#device-affiliation).</span></span>

 <span data-ttu-id="0e5e9-131">Dans la fenêtre **configurer les administrateurs pour ce périphérique** , sélectionnez l’une des options suivantes: services de domaine Active Directory, Azure Active Directory ou administrateur local.</span><span class="sxs-lookup"><span data-stu-id="0e5e9-131">In the **Setup admins for this device** window, select one of the following options: Active Directory Domain Services, Azure Active Directory, or Local admin.</span></span>

   ![\* Administrateurs de configuration pour cet appareil \*](images/sh2-run5.png) <br>

### <span data-ttu-id="0e5e9-133">Services de domaine ActiveDirectory</span><span class="sxs-lookup"><span data-stu-id="0e5e9-133">Active Directory Domain Services</span></span>

1. <span data-ttu-id="0e5e9-134">Entrez les informations d’identification d’un utilisateur disposant des autorisations de connexion de l’appareil à Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0e5e9-134">Enter the credentials of a user who has permissions to join the device to Active Directory.</span></span>

    ![\* Administrateurs de l’installation à l’aide de Domain Join \*](images/sh2-run6.png) <br>

2. <span data-ttu-id="0e5e9-136">Sélectionnez le groupe de sécurité Active Directory contenant les membres autorisés à se connecter à l’application paramètres sur surface Hub 2S.</span><span class="sxs-lookup"><span data-stu-id="0e5e9-136">Select the Active Directory Security Group containing members allowed to log on to the Settings app on Surface Hub 2S.</span></span>

    ![\* Entrer un groupe de sécurité \*](images/sh2-run7.png) <br>
1. <span data-ttu-id="0e5e9-138">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="0e5e9-138">Select **Finish**.</span></span> <span data-ttu-id="0e5e9-139">Le périphérique redémarrera.</span><span class="sxs-lookup"><span data-stu-id="0e5e9-139">The device will restart.</span></span>

### <span data-ttu-id="0e5e9-140">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="0e5e9-140">Azure Active Directory</span></span>

<span data-ttu-id="0e5e9-141">Lorsque vous choisissez d’affilier votre appareil à Azure Active Directory, le périphérique redémarre immédiatement et affiche la page suivante.</span><span class="sxs-lookup"><span data-stu-id="0e5e9-141">When choosing to affiliate your device with Azure Active Directory, the device will immediately restart and display the following page.</span></span> <span data-ttu-id="0e5e9-142">Sélectionnez **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="0e5e9-142">Select **Next**.</span></span>

![\* Si votre organisation utilise Office 365 ou d’autres services professionnels de Microsoft, nous inscrivons cet appareil avec votre organisation \*](images/sh2-run8.png) <br>

1. <span data-ttu-id="0e5e9-144">Entrez l’adresse de messagerie ou le nom d’utilisateur principal d’un compte **avec le plan Intune 1** ou une version ultérieure, puis sélectionnez **suivant.**</span><span class="sxs-lookup"><span data-stu-id="0e5e9-144">Enter the email address or UPN of an account **with Intune Plan 1** or greater and then select **Next.**</span></span>

    ![\* Entrez votre compte professionnel ou scolaire \*](images/sh2-run9.png) <br>

2. <span data-ttu-id="0e5e9-146">Si vous êtes redirigé, authentifiez-vous à l’aide de la page de connexion de votre organisation et fournissez des informations d’ouverture de session supplémentaires, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="0e5e9-146">If redirected, authenticate using your organization’s sign-in page and provide additional logon information if requested.</span></span> <span data-ttu-id="0e5e9-147">Le périphérique redémarrera.</span><span class="sxs-lookup"><span data-stu-id="0e5e9-147">The device will restart.</span></span>

## <span data-ttu-id="0e5e9-148">Compte d’administrateur local</span><span class="sxs-lookup"><span data-stu-id="0e5e9-148">Local Administrator account</span></span>

- <span data-ttu-id="0e5e9-149">Entrez un nom d’utilisateur et un mot de passe pour votre administrateur local. Le périphérique redémarrera.</span><span class="sxs-lookup"><span data-stu-id="0e5e9-149">Enter a username and password for your local admin. The device will restart.</span></span>

     ![\* Configurer un compte d’administrateur \*](images/sh2-run10.png) <br>
 
## <span data-ttu-id="0e5e9-151">Utiliser les packages de mise en service</span><span class="sxs-lookup"><span data-stu-id="0e5e9-151">Using provisioning packages</span></span>

<span data-ttu-id="0e5e9-152">Si vous insérez une clé USB avec un module de mise en service dans l’un des ports USB lorsque vous démarrez surface Hub 2, le périphérique affiche la page suivante.</span><span class="sxs-lookup"><span data-stu-id="0e5e9-152">If you insert a USB thumb drive with a provisioning package into one of the USB ports when you start Surface Hub 2S, the device displays the following page.</span></span>

1. <span data-ttu-id="0e5e9-153">Entrez les paramètres demandés et sélectionnez **configurer**.</span><span class="sxs-lookup"><span data-stu-id="0e5e9-153">Enter the requested settings and select **Set up**.</span></span>

    ![\* Saisie des paramètres régionaux pour le package de mise en service](images/sh2-run11.png) <br>

    ![\* Mise en service de cet appareil à partir de médias amovibles \*](images/sh2-run12.png) <br>
2. <span data-ttu-id="0e5e9-156">Choisissez le package de mise en service que vous voulez utiliser.</span><span class="sxs-lookup"><span data-stu-id="0e5e9-156">Choose the provisioning package you’d like to use.</span></span>

   ![\* Choisir le package de mise à service à utiliser \*](images/sh2-run13.png) <br>

3. <span data-ttu-id="0e5e9-158">Si vous avez créé un fichier CSV de plusieurs appareils, vous pouvez choisir une configuration d’appareil.</span><span class="sxs-lookup"><span data-stu-id="0e5e9-158">If you created a multiple devices CSV file, you will be able to choose a device configuration.</span></span> <span data-ttu-id="0e5e9-159">Pour plus d’informations, reportez-vous à [créer des packages de mise en service pour surface Hub 2](https://docs.microsoft.com/surface-hub/surface-hub-2s-deploy#provisioning-multiple-devices-csv-file).</span><span class="sxs-lookup"><span data-stu-id="0e5e9-159">For more information, refer to [Create provisioning packages for Surface Hub 2S](https://docs.microsoft.com/surface-hub/surface-hub-2s-deploy#provisioning-multiple-devices-csv-file).</span></span>


    ![\* Sélectionnez un compte d’appareil et un nom convivial dans votre fichier de configuration \*](images/sh2-run14.png) <br>

4. <span data-ttu-id="0e5e9-161">Suivez les instructions pour la première fois.</span><span class="sxs-lookup"><span data-stu-id="0e5e9-161">Follow the instructions to complete first time Setup.</span></span>
