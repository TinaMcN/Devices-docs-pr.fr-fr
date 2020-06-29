---
title: Utiliser un nom de domaine complet avec le SurfaceHub
description: Résolvez les problèmes courants, notamment les problèmes d’installation et les erreurs ExchangeActiveSync.
keywords:
- Résoudre les problèmes courants
- problèmes d’installation
- Erreurs ExchangeActiveSync
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.prod: surface-hub
ms.sitesec: library
ms.openlocfilehash: 79507f5b4bb22b23d1e6c4db6b4aab6ea891d876
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832657"
---
# <span data-ttu-id="2331d-106">Configurer un nom de domaine pour SkypeEntreprise</span><span class="sxs-lookup"><span data-stu-id="2331d-106">Configure domain name for Skype for Business</span></span>

<span data-ttu-id="2331d-107">Quelques scénarios impliquent que vous deviez spécifier le nom de domaine de votre serveur SkypeEntreprise:</span><span class="sxs-lookup"><span data-stu-id="2331d-107">There are a few scenarios where you need to specify the domain name of your Skype for Business server:</span></span>
- <span data-ttu-id="2331d-108">**Plusieurs suffixes DNS**: lorsque votre infrastructure SkypeEntreprise comporte des espaces de noms disjoints, de sorte qu’un ou plusieurs serveurs présentent un suffixe DNS différent du suffixe de l’adresse de connexion de SkypeEntreprise.</span><span class="sxs-lookup"><span data-stu-id="2331d-108">**Multiple DNS suffixes** - When your Skype for Business infrastructure has disjointed namespaces such that one or more servers have a DNS suffix that doesn't match the suffix of the sign-in address (SIP) for Skype for Business.</span></span>  
- <span data-ttu-id="2331d-109">**Suffixes SkypeEntreprise différents des suffixes Exchange**: lorsque le suffixe de l’adresse de connexion de SkypeEntreprise diffère de celui de l’adresse Exchange utilisée pour le compte d’appareil.</span><span class="sxs-lookup"><span data-stu-id="2331d-109">**Skype for Business and Exchange suffixes are different** - When the suffix of the sign-in address for Skype for Business differs from the suffix of the Exchange address used for the device account.</span></span>
- <span data-ttu-id="2331d-110">L' **utilisation de certificats** (organisations de grande taille avec des serveurs Skype entreprise locaux utilisent fréquemment des certificats avec leur propre autorité de certification racine).</span><span class="sxs-lookup"><span data-stu-id="2331d-110">**Working with certificates** - Large organizations with on-premises Skype for Business servers commonly use certificates with their own root certificate authority (CA).</span></span> <span data-ttu-id="2331d-111">Il est courant que le domaine de l’autorité de certification diffère du domaine du serveur SkypeEntreprise, ce qui entraîne la non-approbation du certificat, et donc l’échec de la connexion.</span><span class="sxs-lookup"><span data-stu-id="2331d-111">It is common for the CA domain to be different than the domain of the Skype for Business server which causes the certificate to not be trusted, and sign-in fails.</span></span>  <span data-ttu-id="2331d-112">Skype doit connaître le nom de domaine du certificat pour configurer une relation d’approbation.</span><span class="sxs-lookup"><span data-stu-id="2331d-112">Skype needs to know the domain name of the certificate in order to set up a trust relationship.</span></span> <span data-ttu-id="2331d-113">Les entreprises utilisent généralement une stratégie de groupe pour transmettre cette information à l’application de bureau Skype, mais les stratégies de groupe ne sont pas prises en charge sur le SurfaceHub.</span><span class="sxs-lookup"><span data-stu-id="2331d-113">Enterprises typically use Group Policy to push this out to Skype desktop, but Group Policy is not supported on Surface Hub.</span></span>

**<span data-ttu-id="2331d-114">Pour configurer le nom de domaine de votre serveur SkypeEntreprise:</span><span class="sxs-lookup"><span data-stu-id="2331d-114">To configure the domain name for your Skype for Business server</span></span>**</br>
1. <span data-ttu-id="2331d-115">Sur le SurfaceHub, ouvrez **Paramètres**.</span><span class="sxs-lookup"><span data-stu-id="2331d-115">On Surface Hub, open **Settings**.</span></span>
2. <span data-ttu-id="2331d-116">Cliquez sur **Surface Hub**, puis cliquez sur **Appel et Audio**.</span><span class="sxs-lookup"><span data-stu-id="2331d-116">Click **Surface Hub**, and then click **Calling & Audio**.</span></span> 
3. <span data-ttu-id="2331d-117">Sous **Configuration de SkypeEntreprise**, cliquez sur **Configurer le nom de domaine**.</span><span class="sxs-lookup"><span data-stu-id="2331d-117">Under **Skype for Business configuration**, click **Configure domain name**.</span></span> 
4. <span data-ttu-id="2331d-118">Tapez le nom de domaine de votre serveur SkypeEntreprise, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="2331d-118">Type the domain name for your Skype for Business server, and then click **Ok**.</span></span> 
   > [!TIP]
   > <span data-ttu-id="2331d-119">Vous pouvez taper plusieurs noms de domaine en les séparant par une virgule.</span><span class="sxs-lookup"><span data-stu-id="2331d-119">You can type multiple domain names, separated by commas.</span></span> <br> <span data-ttu-id="2331d-120">Exemple: lync.com, outlook.com, lync.glbdns.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="2331d-120">For example: lync.com, outlook.com, lync.glbdns.microsoft.com</span></span>

    ![Ajouter un nom de domaine complet Skype entreprise aux paramètres](images/system-settings-add-fqdn.png)
