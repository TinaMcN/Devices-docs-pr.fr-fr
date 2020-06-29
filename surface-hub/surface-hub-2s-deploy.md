---
title: Créer des packages de configuration pour SurfaceHub2S
description: Cette page décrit le déploiement de surface Hub 2 à l’aide des packages de mise en service et d’autres outils.
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
ms.openlocfilehash: 8f91b751a10977d80210d10ac1b48a93d9ba0f6f
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10834186"
---
# <span data-ttu-id="29512-104">Créer des packages de configuration pour SurfaceHub2S</span><span class="sxs-lookup"><span data-stu-id="29512-104">Create provisioning packages for Surface Hub 2S</span></span>

<span data-ttu-id="29512-105">Vous pouvez utiliser le concepteur de configuration Windows (WCD) pour créer des packages de mise en service pour automatiser le processus de déploiement de surface Hub 2.</span><span class="sxs-lookup"><span data-stu-id="29512-105">You can use Windows Configuration Designer (WCD) to create provisioning packages to automate the deployment process of Surface Hub 2S.</span></span> <span data-ttu-id="29512-106">Utiliser les packages de mise en service pour ajouter des certificats, configurer des proxys, configurer des administrateurs d’appareils et des comptes de périphériques.</span><span class="sxs-lookup"><span data-stu-id="29512-106">Use provisioning packages to add certificates, configure proxies, set up device administrators and device accounts.</span></span> <span data-ttu-id="29512-107">Vous pouvez également utiliser les packages de mise en service avec un fichier de configuration pour déployer plusieurs hubs surface avec une seule clé USB.</span><span class="sxs-lookup"><span data-stu-id="29512-107">You can also use provisioning packages along with a configuration file to deploy multiple Surface Hubs with a single USB thumb drive.</span></span>

### <span data-ttu-id="29512-108">Installer le Concepteur de configuration Windows</span><span class="sxs-lookup"><span data-stu-id="29512-108">Install Windows Configuration Designer</span></span>

<span data-ttu-id="29512-109">Installez l’éditeur de configuration Windows à partir du kit d’évaluation et de déploiement Windows (ADK) pour Windows 10.</span><span class="sxs-lookup"><span data-stu-id="29512-109">Install Windows Configuration Designer from the Windows Assessment and Deployment Kit (ADK) for Windows 10.</span></span> <span data-ttu-id="29512-110">Téléchargez et installez la [version ADK pour Windows 10, version 1703](https://go.microsoft.com/fwlink/p/?LinkId=845542).</span><span class="sxs-lookup"><span data-stu-id="29512-110">Download and install the [ADK for Windows 10, version 1703](https://go.microsoft.com/fwlink/p/?LinkId=845542).</span></span> <span data-ttu-id="29512-111">Pour plus d’informations, reportez-vous à [Télécharger et installer Windows ADK](https://docs.microsoft.com/windows-hardware/get-started/adk-install).</span><span class="sxs-lookup"><span data-stu-id="29512-111">For more information, see [Download and install the Windows ADK](https://docs.microsoft.com/windows-hardware/get-started/adk-install).</span></span>

### <span data-ttu-id="29512-112">Ajouter des certificats</span><span class="sxs-lookup"><span data-stu-id="29512-112">Add certificates</span></span>

<span data-ttu-id="29512-113">Vous pouvez importer des certificats d’autorité de certification sur surface Hub 2.</span><span class="sxs-lookup"><span data-stu-id="29512-113">You can import Certificate Authority certificates to Surface Hub 2S.</span></span>
<span data-ttu-id="29512-114">Pour ajouter des certificats à surface Hub 2, vous avez besoin d’une copie de chaque certificat en tant que X. 509 au format. cer.</span><span class="sxs-lookup"><span data-stu-id="29512-114">To add certificates to Surface Hub 2S, you need a copy of each certificate as X.509 in .cer format.</span></span> <span data-ttu-id="29512-115">Vous ne pouvez pas importer. CRT,. pfx ou d’autres formats de conteneur.</span><span class="sxs-lookup"><span data-stu-id="29512-115">You cannot import .crt, .pfx or other container formats.</span></span> <span data-ttu-id="29512-116">Les certificats doivent être importés dans le concepteur de configuration Windows et organisés par hiérarchie:</span><span class="sxs-lookup"><span data-stu-id="29512-116">Certificates must be imported into Windows Configuration Designer and arranged by hierarchy:</span></span>

 ![Ajouter des certificats](images/sh2-wcd.png)

### <span data-ttu-id="29512-118">Configurer le proxy lors de l’OOBE</span><span class="sxs-lookup"><span data-stu-id="29512-118">Configure proxy during OOBE</span></span>

<span data-ttu-id="29512-119">Dans le concepteur de configuration Windows, accédez à l’onglet configurer les paramètres du proxy et entrez les paramètres appropriés, comme illustré ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="29512-119">In Windows Configuration Designer, go to the Configure proxy settings tab and enter the appropriate settings as shown below.</span></span>

 ![Configurer les paramètres de proxy](images/sh2-proxy.png) 

> [!NOTE]
> <span data-ttu-id="29512-121">Lorsque vous configurez les paramètres de proxy, désactivez l’option **détecter automatiquement les paramètres** de connexion si vous envisagez d’utiliser un script de configuration ou un serveur proxy.</span><span class="sxs-lookup"><span data-stu-id="29512-121">When configuring proxy settings, turn off **Automatically detect settings** if you intend to use a setup script or a proxy server.</span></span> <span data-ttu-id="29512-122">Vous pouvez utiliser un script de configuration *ou* un serveur proxy, et non les deux.</span><span class="sxs-lookup"><span data-stu-id="29512-122">You can use a setup script *or* a proxy server, not both.</span></span>

### <span data-ttu-id="29512-123">Centre d’affiliation surface Hub 2 avec Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="29512-123">Affiliate Surface Hub 2S with Azure Active Directory</span></span>

<span data-ttu-id="29512-124">Vous pouvez affilier surface Hub 2 avec Azure Active Directory à l’aide d’un package de mise à niveau: en tant qu’administrateur général Azure Active Directory, vous pouvez rejoindre un grand nombre de nouveaux appareils Windows sur Azure Active Directory et Intune en utilisant un jeton de bloc.</span><span class="sxs-lookup"><span data-stu-id="29512-124">You can affiliate Surface Hub 2S with Azure Active Directory using a provisioning package: As an Azure Active Directory Global Administrator, you can join large numbers of new Windows devices to Azure Active Directory and Intune using a bulk token.</span></span>

<span data-ttu-id="29512-125">Pour créer un jeton de bloc, donnez-lui un nom convivial, configurez la date d’expiration (maximale de 30 jours) et utilisez vos informations d’identification d’administrateur pour acquérir le jeton, comme illustré ci-dessous:</span><span class="sxs-lookup"><span data-stu-id="29512-125">To create a bulk token, give it a friendly name, configure the expiration date (maximum of 30 days) and use your Admin credentials to acquire the token as shown below:</span></span>

 ![Configurer des administrateurs d’appareils](images/sh2-token.png) <br><br>
 ![Configurer des administrateurs d’appareils](images/sh2-token2.png) <br><br>
 ![Configurer des administrateurs d’appareils](images/sh2-token3.png) <br><br>

### <span data-ttu-id="29512-129">Attribution de plusieurs appareils (fichier. csv)</span><span class="sxs-lookup"><span data-stu-id="29512-129">Provisioning multiple devices (.csv file)</span></span>

<span data-ttu-id="29512-130">Outre le package de mise en service, vous pouvez utiliser un fichier de configuration surface Hub pour faciliter la configuration de vos appareils.</span><span class="sxs-lookup"><span data-stu-id="29512-130">In addition to the provisioning package, you can use a Surface Hub configuration file to make it even easier to set up your devices.</span></span> <span data-ttu-id="29512-131">Un fichier de configuration surface hub contient une liste de comptes de périphériques et de noms conviviaux pour la projection sans fil.</span><span class="sxs-lookup"><span data-stu-id="29512-131">A Surface Hub configuration file contains a list of device accounts and friendly names for wireless projection.</span></span> <span data-ttu-id="29512-132">Lors de la première exécution, vous avez la possibilité de choisir un compte d’appareil et un nom convivial à partir d’un fichier de configuration.</span><span class="sxs-lookup"><span data-stu-id="29512-132">During first run, you get an option to choose a device account and friendly name from a configuration file.</span></span>

### <span data-ttu-id="29512-133">Pour créer un fichier de configuration surface Hub</span><span class="sxs-lookup"><span data-stu-id="29512-133">To create a Surface Hub configuration file</span></span>

1. <span data-ttu-id="29512-134">À l’aide de Microsoft Excel ou d’un autre éditeur de fichiers CSV, créez un fichier CSV intitulé: **SurfaceHubConfiguration.csv**</span><span class="sxs-lookup"><span data-stu-id="29512-134">Using Microsoft Excel or another CSV editor, create a CSV file named: **SurfaceHubConfiguration.csv**</span></span>
2. <span data-ttu-id="29512-135">Entrez dans ce format une liste de comptes d’appareils et de noms conviviaux:</span><span class="sxs-lookup"><span data-stu-id="29512-135">Enter a list of device accounts and friendly names in this format:</span></span>

```
<DeviceAccountName>,<DeviceAccountPassword>,<FriendlyName>
```

3. <span data-ttu-id="29512-136">Enregistrez le fichier à la racine du lecteur USB dans lequel vous avez copié le fichier PPKG.</span><span class="sxs-lookup"><span data-stu-id="29512-136">Save the file to the root of the USB thumb drive where you copied the PPKG file.</span></span>

    ![Exemple de fichier de configuration](images/sh2-config-file.png)
