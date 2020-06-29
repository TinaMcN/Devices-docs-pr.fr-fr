---
title: Activer l’authentification 802.1x câblée
description: Les stratégies GPM d'authentification filaire802.1x ont été activées sur les appareils Surface Hub.
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 11/15/2017
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: 119f879d74ccda5d53da27d842413346a50693f1
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10833707"
---
# <span data-ttu-id="c0d86-103">Activer l'authentification filaire802.1x</span><span class="sxs-lookup"><span data-stu-id="c0d86-103">Enable 802.1x wired authentication</span></span>

<span data-ttu-id="c0d86-104">La [mise à jour vers Windows10 du 14 novembre2017](https://support.microsoft.com/help/4048954/windows-10-update-kb4048954) (build15063.726) permet d'activer des stratégies GPM d'authentification filaire802.1x sur les appareils Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="c0d86-104">The [November 14, 2017 update to Windows 10](https://support.microsoft.com/help/4048954/windows-10-update-kb4048954) (build 15063.726) enables 802.1x wired authentication MDM policies on Surface Hub devices.</span></span> <span data-ttu-id="c0d86-105">Cette fonctionnalité permet aux organisations de mettre en œuvre une authentification réseau filaire normalisée à l'aide du [protocole d’authentificationIEEE802.1x](http://www.ieee802.org/1/pages/802.1x-2010.html).</span><span class="sxs-lookup"><span data-stu-id="c0d86-105">The feature allows organizations to enforce standardized wired network authentication using the [IEEE 802.1x authentication protocol](http://www.ieee802.org/1/pages/802.1x-2010.html).</span></span> <span data-ttu-id="c0d86-106">Cette option est déjà disponible pour l’authentification sans fil à l’aide de profils WLAN via GPM.</span><span class="sxs-lookup"><span data-stu-id="c0d86-106">This is already available for wireless authentication using WLAN profiles via MDM.</span></span> <span data-ttu-id="c0d86-107">Cette rubrique explique comment configurer un Surface Hub pour l'utiliser avec l’authentification filaire.</span><span class="sxs-lookup"><span data-stu-id="c0d86-107">This topic explains how to  configure a Surface Hub for use with wired authentication.</span></span> 

<span data-ttu-id="c0d86-108">La mise en œuvre et l’activation de l’authentification filaire802.1x sur Surface Hub peut s'effectuer via la [définition de paramètres OMA-URI](https://docs.microsoft.com/intune-classic/deploy-use/windows-10-policy-settings-in-microsoft-intune#oma-uri-settings) de GPM.</span><span class="sxs-lookup"><span data-stu-id="c0d86-108">Enforcement and enablement of 802.1x wired authentication on Surface Hub can be done through MDM [OMA-URI definition](https://docs.microsoft.com/intune-classic/deploy-use/windows-10-policy-settings-in-microsoft-intune#oma-uri-settings).</span></span> 

<span data-ttu-id="c0d86-109">La principale configuration à définir est la stratégie **LanProfile**.</span><span class="sxs-lookup"><span data-stu-id="c0d86-109">The primary configuration to set is the **LanProfile** policy.</span></span> <span data-ttu-id="c0d86-110">En fonction de la méthode d’authentification sélectionnée, d'autres stratégies peuvent être nécessaires: la stratégie **EapUserData** ou l'utilisation de stratégies GPM pour l'ajout de certificats d’utilisateur ou d’ordinateur (comme [ClientCertificateInstall](https://docs.microsoft.com/windows/client-management/mdm/clientcertificateinstall-csp) pour les certificats d'utilisateur/appareil ou [RootCATrustedCertificates](https://docs.microsoft.com/windows/client-management/mdm/rootcacertificates-csp) pour les certificats d'appareil).</span><span class="sxs-lookup"><span data-stu-id="c0d86-110">Depending on the authentication method selected, other policies may be required, either the **EapUserData** policy or through MDM policies for adding user or machine certificates (such as [ClientCertificateInstall](https://docs.microsoft.com/windows/client-management/mdm/clientcertificateinstall-csp) for user/device certificates or [RootCATrustedCertificates](https://docs.microsoft.com/windows/client-management/mdm/rootcacertificates-csp) for device certificates).</span></span> 

## <span data-ttu-id="c0d86-111">Élément de stratégie LanProfile</span><span class="sxs-lookup"><span data-stu-id="c0d86-111">LanProfile policy element</span></span>

<span data-ttu-id="c0d86-112">Pour configurer le Surface Hub en vue d'utiliser l'une des méthodes d’authentification802.1x prises en charge, utilisez l’OMA-URI suivant.</span><span class="sxs-lookup"><span data-stu-id="c0d86-112">To configure Surface Hub to use one of the supported 802.1x authentication methods, utilize the following OMA-URI.</span></span> 

```
./Vendor/MSFT/SurfaceHub/Dot3/LanProfile
```

<span data-ttu-id="c0d86-113">Ce nœud OMA-URI prend une chaîne de texte XML comme paramètre.</span><span class="sxs-lookup"><span data-stu-id="c0d86-113">This OMA-URI node takes a text string of XML as a parameter.</span></span> <span data-ttu-id="c0d86-114">Le code XML fourni comme paramètre doit être conforme au [schéma de profil du réseau local câblé](https://msdn.microsoft.com/library/cc233002.aspx), notamment les éléments du [schéma802.1X](https://msdn.microsoft.com/library/cc233003.aspx).</span><span class="sxs-lookup"><span data-stu-id="c0d86-114">The XML provided as a parameter should conform to the [Wired LAN Profile Schema](https://msdn.microsoft.com/library/cc233002.aspx) including elements from the [802.1X schema](https://msdn.microsoft.com/library/cc233003.aspx).</span></span> 

<span data-ttu-id="c0d86-115">Dans la plupart des cas, un administrateur ou un utilisateur peut exporter le code XML LanProfile à partir d’un PC existant, déjà configuré sur le réseau pour802.1X, à l’aide de la commande NETSH suivante.</span><span class="sxs-lookup"><span data-stu-id="c0d86-115">In most instances, an administrator or user can export the LanProfile XML from an existing PC that is already configured on the network for 802.1X using this following NETSH command.</span></span> 

```
netsh lan export profile folder=.
```

<span data-ttu-id="c0d86-116">L'exécution de cette commande donnera la sortie suivante et placera un fichier intitulé **Ethernet.xml** dans le répertoire actif.</span><span class="sxs-lookup"><span data-stu-id="c0d86-116">Running this command will give the following output and place a file titled **Ethernet.xml** in the current directory.</span></span> 

```
Interface: Ethernet
Profile File Name: .\Ethernet.xml
1 profile(s) were exported successfully.
```

## <span data-ttu-id="c0d86-117">Élément de stratégie EapUserData</span><span class="sxs-lookup"><span data-stu-id="c0d86-117">EapUserData policy element</span></span>

<span data-ttu-id="c0d86-118">Si votre méthode d’authentification requiert un nom d’utilisateur et un mot de passe par opposition à un certificat, vous pouvez utiliser l'élément **EapUserData** pour spécifier des informations d’identification pour l'appareil à utiliser pour s’authentifier sur le réseau.</span><span class="sxs-lookup"><span data-stu-id="c0d86-118">If your selected authentication method requires a username and password as opposed to a certificate, you can use the **EapUserData** element to specify credentials for the device to use to authenticate to the network.</span></span> 

```
./Vendor/MSFT/SurfaceHub/Dot3/EapUserData 
```

<span data-ttu-id="c0d86-119">Ce nœud OMA-URI prend une chaîne de texte XML comme paramètre.</span><span class="sxs-lookup"><span data-stu-id="c0d86-119">This OMA-URI node takes a text string of XML as a parameter.</span></span> <span data-ttu-id="c0d86-120">Le code XML fourni comme paramètre doit être conforme à [l'exemple de Propriétés de l'utilisateur PEAP MS-CHAPv2](https://msdn.microsoft.com/library/windows/desktop/bb891979).</span><span class="sxs-lookup"><span data-stu-id="c0d86-120">The XML provided as a parameter should conform to the [PEAP MS-CHAPv2 User Properties example](https://msdn.microsoft.com/library/windows/desktop/bb891979).</span></span> <span data-ttu-id="c0d86-121">Dans l’exemple, vous devez remplacer toutes les instances de *test* et *ias-domain* par vos informations.</span><span class="sxs-lookup"><span data-stu-id="c0d86-121">In the example, you will need to replace all instances of *test* and *ias-domain* with your information.</span></span>



## <span data-ttu-id="c0d86-122">Ajout de certificats</span><span class="sxs-lookup"><span data-stu-id="c0d86-122">Adding certificates</span></span>

<span data-ttu-id="c0d86-123">Si votre méthode d’authentification sélectionnée est basée sur des certificats, vous devez [créer un package](provisioning-packages-for-surface-hub.md)de mise en service, utiliser la gestion des périphériques mobiles ( [GPM](https://docs.microsoft.com/windows/client-management/mdm/clientcertificateinstall-csp)) ou importer un certificat à partir des paramètres (**Settings**  >  **mise à jour des paramètres et**  >  **certificats**de sécurité) pour déployer ces certificats sur votre appareil surface Hub dans le magasin de certificats approprié.</span><span class="sxs-lookup"><span data-stu-id="c0d86-123">If your selected authentication method is certificate-based, you will need to [create a provisioning package](provisioning-packages-for-surface-hub.md), [utilize MDM](https://docs.microsoft.com/windows/client-management/mdm/clientcertificateinstall-csp), or import a certificate from settings (**Settings** > **Update and Security** > **Certificates**) to deploy those certificates to your Surface Hub device in the appropriate Certificate Store.</span></span> <span data-ttu-id="c0d86-124">Lorsque vous ajoutez des certificats, chaque PFX doit contenir un seul certificat (un PFX ne doit pas avoir plusieurs certificats).</span><span class="sxs-lookup"><span data-stu-id="c0d86-124">When adding certificates, each PFX must contain only one certificate (a PFX cannot have multiple certificates).</span></span>

