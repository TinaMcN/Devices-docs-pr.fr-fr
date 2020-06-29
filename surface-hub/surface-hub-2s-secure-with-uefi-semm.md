---
title: Sécuriser et gérer les plateformes de surface Hub 2 avec SEMM
description: En savoir plus sur la protection des éléments de surface Hub 2 avec SEMM.
keywords: séparer les valeurs par des virgules
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 06/20/2019
ms.localizationpriority: Medium
ms.openlocfilehash: 03ce1dfa48ade8aade545c63818ca5ae8947e6b7
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832970"
---
# <span data-ttu-id="42786-104">Sécuriser et gérer les SurfaceHub2S avec SEMM et UEFI</span><span class="sxs-lookup"><span data-stu-id="42786-104">Secure and manage Surface Hub 2S with SEMM and UEFI</span></span>

<span data-ttu-id="42786-105">Nouveauté de surface Hub 2, vous pouvez utiliser SEMM pour gérer le paramètre UEFI de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="42786-105">New in Surface Hub 2S, you can use SEMM to manage the UEFI setting of the device.</span></span>
<span data-ttu-id="42786-106">Utilisez le configurateur Microsoft surface UEFI pour contrôler les composants suivants:</span><span class="sxs-lookup"><span data-stu-id="42786-106">Use the Microsoft Surface UEFI Configurator to control the following components:</span></span>

- <span data-ttu-id="42786-107">Réseau local câblé</span><span class="sxs-lookup"><span data-stu-id="42786-107">Wired LAN</span></span>
- <span data-ttu-id="42786-108">Appareils photo</span><span class="sxs-lookup"><span data-stu-id="42786-108">Cameras</span></span>
- <span data-ttu-id="42786-109">Bluetooth</span><span class="sxs-lookup"><span data-stu-id="42786-109">Bluetooth</span></span>
- <span data-ttu-id="42786-110">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="42786-110">Wi-Fi</span></span>
- <span data-ttu-id="42786-111">Capteur d’occupation</span><span class="sxs-lookup"><span data-stu-id="42786-111">Occupancy sensor</span></span>

<span data-ttu-id="42786-112">Utilisez le configurateur Microsoft surface UEFI pour activer ou désactiver les paramètres UEFI suivants:</span><span class="sxs-lookup"><span data-stu-id="42786-112">Use the Microsoft Surface UEFI Configurator to turn on or off the following UEFI settings:</span></span>

- <span data-ttu-id="42786-113">Démarrage</span><span class="sxs-lookup"><span data-stu-id="42786-113">Boot</span></span>

    - <span data-ttu-id="42786-114">IPv6 pour démarrage PXE</span><span class="sxs-lookup"><span data-stu-id="42786-114">IPv6 for PXE Boot</span></span>
    - <span data-ttu-id="42786-115">Autre démarrage</span><span class="sxs-lookup"><span data-stu-id="42786-115">Alternate Boot</span></span>
    - <span data-ttu-id="42786-116">Verrou d’ordre de démarrage</span><span class="sxs-lookup"><span data-stu-id="42786-116">Boot Order Lock</span></span>
    - <span data-ttu-id="42786-117">Démarrage USB</span><span class="sxs-lookup"><span data-stu-id="42786-117">USB Boot</span></span>
- <span data-ttu-id="42786-118">Page frontale UEFI</span><span class="sxs-lookup"><span data-stu-id="42786-118">UEFI Front Page</span></span>

    - <span data-ttu-id="42786-119">Périphériques</span><span class="sxs-lookup"><span data-stu-id="42786-119">Devices</span></span>
    - <span data-ttu-id="42786-120">Démarrage</span><span class="sxs-lookup"><span data-stu-id="42786-120">Boot</span></span>
    - <span data-ttu-id="42786-121">Date/Heure</span><span class="sxs-lookup"><span data-stu-id="42786-121">Date/Time</span></span>

## <span data-ttu-id="42786-122">Image de la création d’une configuration UEFI</span><span class="sxs-lookup"><span data-stu-id="42786-122">Create UEFI configuration image</span></span>

<span data-ttu-id="42786-123">Contrairement aux autres appareils surface, vous ne pouvez pas utiliser un fichier MSI ou une image de type Win PE pour appliquer ces paramètres sur surface Hub 2.</span><span class="sxs-lookup"><span data-stu-id="42786-123">Unlike other Surface devices, you cannot use an MSI file or a Win PE image to apply these settings on Surface Hub 2S.</span></span> <span data-ttu-id="42786-124">Au lieu de cela, vous devez créer une image USB à charger dans l’appareil.</span><span class="sxs-lookup"><span data-stu-id="42786-124">Instead, you need to create a USB image to load into the device.</span></span> <span data-ttu-id="42786-125">Pour créer une image de configuration UEFI surface Hub 2S, téléchargez et installez la dernière version du programme d’installation de Microsoft surface UEFI à partir de la page [Outils surface pour cette application](https://www.microsoft.com/download/details.aspx?id=46703) dans le centre de téléchargement Microsoft.</span><span class="sxs-lookup"><span data-stu-id="42786-125">To create a Surface Hub 2S UEFI configuration image, download and install the latest version of the Microsoft Surface UEFI Configurator from the [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) page in the Microsoft Download Center.</span></span> <span data-ttu-id="42786-126">Pour plus d’informations sur l’utilisation de UEFI et de SEMM, voir mode de gestion de l' [entreprise Microsoft surface](https://docs.microsoft.com/surface/surface-enterprise-management-mode).</span><span class="sxs-lookup"><span data-stu-id="42786-126">For more information about using UEFI and SEMM, see [Microsoft Surface Enterprise Management Mode](https://docs.microsoft.com/surface/surface-enterprise-management-mode).</span></span>

## <span data-ttu-id="42786-127">Pour configurer UEFI sur surface Hub 2</span><span class="sxs-lookup"><span data-stu-id="42786-127">To configure UEFI on Surface Hub 2S</span></span>

1. <span data-ttu-id="42786-128">Démarrez le configurateur UEFI, puis, dans le premier écran, sélectionnez **package de configuration**.</span><span class="sxs-lookup"><span data-stu-id="42786-128">Start the UEFI Configurator and on the first screen, choose **Configuration Package**.</span></span><br><br>
![\* Démarrez le configurateur UEFI et sélectionnez package de configuration \*](images/sh2-uefi1.png) <br> <br>
2. <span data-ttu-id="42786-130">Pour ajouter le certificat à votre package, vous devez disposer d’un certificat valide avec la clé privée au format de fichier. pfx pour signer et protéger le package.</span><span class="sxs-lookup"><span data-stu-id="42786-130">To add the certificate to your package, you must have a valid certificate with the private key in a .pfx file format to sign and protect the package.</span></span> <span data-ttu-id="42786-131">Sélectionnez **+ protection des certificats.**</span><span class="sxs-lookup"><span data-stu-id="42786-131">Select **+ Certificate Protection.**</span></span> <br>
![\* Sélectionnez + protection de certificat \*](images/sh2-uefi2.png) <br><br>
3. <span data-ttu-id="42786-133">Entrez le mot de passe de la clé privée du certificat.</span><span class="sxs-lookup"><span data-stu-id="42786-133">Enter the certificate’s private key’s password.</span></span><br>
![\* Entrez le mot de passe de la clé privée du certificat \*](images/sh2-uefi3.png) <br><br>
4. <span data-ttu-id="42786-135">Après avoir importé la clé privée, continuez à créer le package.</span><span class="sxs-lookup"><span data-stu-id="42786-135">After importing the private key, continue creating the package.</span></span><br>
![\* Continuer à créer le package \*](images/sh2-uefi4.png) <br><br>
5. <span data-ttu-id="42786-137">Sélectionnez **Hub** and **surface Hub 2** en tant que cible pour le package de configuration UEFI.</span><span class="sxs-lookup"><span data-stu-id="42786-137">Choose **Hub** and **Surface Hub 2S** as the target for the UEFI configuration package.</span></span><br>
![\* Sélectionnez Hub and surface Hub 2 en tant que cible pour le package de configuration UEFI \*](images/sh2-uefi5.png) <br><br>
6. <span data-ttu-id="42786-139">Choisissez les composants et les paramètres que vous souhaitez activer ou désactiver sur surface Hub 2.</span><span class="sxs-lookup"><span data-stu-id="42786-139">Choose the components and settings you want to activate or deactivate on Surface Hub 2S.</span></span><br>
![\* Sélectionnez les composants et les paramètres que vous souhaitez activer ou désactiver \*.](images/sh2-uefi6.png) <br><br>
7. <span data-ttu-id="42786-141">Utilisez l’option USB pour exporter le fichier.</span><span class="sxs-lookup"><span data-stu-id="42786-141">Use the USB option to export the file.</span></span><br>
![\* Utiliser l’option USB pour exporter le fichier \*](images/sh2-uefi8.png) <br><br>
8. <span data-ttu-id="42786-143">Insérez et sélectionnez la clé USB que vous voulez utiliser pour ce package.</span><span class="sxs-lookup"><span data-stu-id="42786-143">Insert and choose the USB drive you’d like to use for this package.</span></span> <span data-ttu-id="42786-144">Le lecteur USB sera formaté et vous perdez toutes les informations dont vous disposez.</span><span class="sxs-lookup"><span data-stu-id="42786-144">The USB drive will be formatted and you lose any information you have on it.</span></span><br>
![\* Insérez et sélectionnez le lecteur USB de votre coffret \*](images/sh2-uefi9.png) <br><br>
9. <span data-ttu-id="42786-146">Lors de la création réussie du package, le programme de configuration affiche les deux derniers caractères de l’empreinte de votre certificat.</span><span class="sxs-lookup"><span data-stu-id="42786-146">Upon successful creation of the package, the Configurator will display the last two characters of your certificate’s thumbprint.</span></span> <span data-ttu-id="42786-147">Vous avez besoin de ces caractères lorsque vous importez des éléments dans la configuration en surface Hub 2.</span><span class="sxs-lookup"><span data-stu-id="42786-147">You need these characters when you import to the configuration to Surface Hub 2S.</span></span><br>
![\* Configuration de package \* réussie](images/sh2-uefi10.png) <br>

## <span data-ttu-id="42786-149">Pour démarrer dans UEFI</span><span class="sxs-lookup"><span data-stu-id="42786-149">To boot into UEFI</span></span>

<span data-ttu-id="42786-150">Désactivez l’option surface Hub 2.</span><span class="sxs-lookup"><span data-stu-id="42786-150">Turn off Surface Hub 2S.</span></span> <span data-ttu-id="42786-151">Appuyez de façon prolongée sur le bouton **monter le volume** et appuyez sur le bouton **d’alimentation** .</span><span class="sxs-lookup"><span data-stu-id="42786-151">Press and hold the **Volume Up** button and press the **Power** Button.</span></span> <span data-ttu-id="42786-152">Maintenez la touche enfoncée jusqu’à ce que le menu UEFI apparaisse.</span><span class="sxs-lookup"><span data-stu-id="42786-152">Keep holding the Volume Up button until the UEFI menu appears.</span></span>
