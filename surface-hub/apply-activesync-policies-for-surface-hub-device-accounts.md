---
title: Appliquer des stratégies ActiveSync à des comptes d’appareil (Surface Hub)
description: Le compte d’appareil du Microsoft Surface Hub utilise ActiveSync pour synchroniser la messagerie et le calendrier. Cela permet à des personnes de participer à des réunions planifiées, de les démarrer à partir du Surface Hub et d’envoyer par courrier électronique n’importe quel tableau blanc réalisé au cours de leur réunion.
ms.assetid: FAABBA74-3088-4275-B58E-EC1070F4D110
ms.reviewer: ''
manager: laurawi
keywords: Surface Hub, stratégies ActiveSync
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 06/20/2019
ms.localizationpriority: medium
ms.openlocfilehash: 6e93069c2d90bdc4c2f505bc28ba0ec1a4f08076
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10833366"
---
# <span data-ttu-id="17d4e-105">Appliquer des stratégies ActiveSync à des comptes d’appareil (Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="17d4e-105">Applying ActiveSync policies to device accounts (Surface Hub)</span></span>


<span data-ttu-id="17d4e-106">Le compte d’appareil du Microsoft Surface Hub utilise ActiveSync pour synchroniser la messagerie et le calendrier.</span><span class="sxs-lookup"><span data-stu-id="17d4e-106">The Microsoft Surface Hub's device account uses ActiveSync to sync mail and calendar.</span></span> <span data-ttu-id="17d4e-107">Cela permet à des personnes de participer à des réunions planifiées, de les démarrer à partir du Surface Hub et d’envoyer par courrier électronique n’importe quel tableau blanc réalisé au cours de leur réunion.</span><span class="sxs-lookup"><span data-stu-id="17d4e-107">This allows people to join and start scheduled meetings from the Surface Hub, and allows them to email any whiteboards they have made during their meeting.</span></span>

<span data-ttu-id="17d4e-108">Pour le bon fonctionnement de ces fonctionnalités, les stratégies ActiveSync de votre organisation doivent être configurées comme suit :</span><span class="sxs-lookup"><span data-stu-id="17d4e-108">For these features to work, the ActiveSync policies for your organization must be configured as follows:</span></span>

-   <span data-ttu-id="17d4e-109">Il ne peut pas s’agir de stratégies globales qui bloquent la synchronisation de la boîte aux lettres de ressources utilisée par le compte d’appareil du Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="17d4e-109">There can't be any global policies that block synchronization of the resource mailbox that's being used by the Surface Hub’s device account.</span></span> <span data-ttu-id="17d4e-110">S’il existe une telle stratégie de blocage, vous devez ajouter la surface Hub en tant qu’appareil autorisé.</span><span class="sxs-lookup"><span data-stu-id="17d4e-110">If there is such a blocking policy, you need to add the Surface Hub as an allowed device.</span></span>
-   <span data-ttu-id="17d4e-111">Vous devez définir une stratégie de boîte aux lettres d’appareil mobile où le paramètre **PasswordEnabled** a la valeur False.</span><span class="sxs-lookup"><span data-stu-id="17d4e-111">You must set a mobile device mailbox policy where the **PasswordEnabled** setting is set to False.</span></span> <span data-ttu-id="17d4e-112">Les autres paramètres de stratégie de boîte aux lettres d’appareil mobile ne sont pas compatibles avec le Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="17d4e-112">Other mobile device mailbox policy settings are not compatible with the Surface Hub.</span></span>

## <span data-ttu-id="17d4e-113">Autorisation de l’identificateur de l’ID</span><span class="sxs-lookup"><span data-stu-id="17d4e-113">Allowing the DeviceID</span></span>


<span data-ttu-id="17d4e-114">Votre organisation peut avoir une stratégie globale empêchant la synchronisation de comptes d’appareil mis en service sur les Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="17d4e-114">Your organization may have a global policy that prevents syncing of device accounts provisioned on Surface Hubs.</span></span> <span data-ttu-id="17d4e-115">Pour configurer cette propriété, voir [Autoriser les ID d’appareil pour ActiveSync](appendix-a-powershell-scripts-for-surface-hub.md#whitelisting-device-ids-cmdlet).</span><span class="sxs-lookup"><span data-stu-id="17d4e-115">To configure this property, see [Allowing device IDs for ActiveSync](appendix-a-powershell-scripts-for-surface-hub.md#whitelisting-device-ids-cmdlet).</span></span>

## <span data-ttu-id="17d4e-116">Défnir PasswordEnabled</span><span class="sxs-lookup"><span data-stu-id="17d4e-116">Setting PasswordEnabled</span></span>


<span data-ttu-id="17d4e-117">Le compte d’appareil doit disposer d’une stratégie ActiveSync où l’attribut **PasswordEnabled** est défini sur False ou sur 0.</span><span class="sxs-lookup"><span data-stu-id="17d4e-117">The device account must have an ActiveSync policy where the **PasswordEnabled** attribute is set to False or 0.</span></span> <span data-ttu-id="17d4e-118">Pour configurer cette propriété, voir [Création d’une stratégie Microsoft Exchange ActiveSync compatible Surface Hub](appendix-a-powershell-scripts-for-surface-hub.md#create-compatible-as-policy).</span><span class="sxs-lookup"><span data-stu-id="17d4e-118">To configure this property, see [Creating a Surface Hub-compatible Microsoft Exchange ActiveSync policy](appendix-a-powershell-scripts-for-surface-hub.md#create-compatible-as-policy).</span></span>

 

 





