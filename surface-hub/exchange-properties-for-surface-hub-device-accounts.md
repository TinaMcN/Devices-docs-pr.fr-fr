---
title: Propriétés de Microsoft Exchange (Surface Hub)
description: Certaines propriétés MicrosoftExchange du compte d’appareil sont définies sur des valeurs dédiées pour optimiser l’expérience de réunion sur le Surface Hub.
ms.assetid: 3E84393B-C425-45BF-95A6-D6502BA1BF29
ms.reviewer: ''
manager: laurawi
keywords: Propriétés de MicrosoftExchange, compte d’appareil, SurfaceHub, applet de commandeWindowsPowerShell
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 06/20/2019
ms.localizationpriority: medium
ms.openlocfilehash: 8879762857146011f3e1a198b72a895bc6bf9473
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10833696"
---
# <span data-ttu-id="b261a-104">Propriétés de Microsoft Exchange (Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="b261a-104">Microsoft Exchange properties (Surface Hub)</span></span>


<span data-ttu-id="b261a-105">Certaines propriétés MicrosoftExchange du compte d’appareil sont définies sur des valeurs dédiées pour optimiser l’expérience de réunion sur le Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="b261a-105">Some Microsoft Exchange properties of the device account must be set to particular values to have the best meeting experience on Microsoft Surface Hub.</span></span> <span data-ttu-id="b261a-106">Le tableau suivant répertorie les différentes propriétés Exchange en fonction des paramètres d’applet de commande Windows PowerShell, leur objectif et les valeurs sur lesquelles elles doivent être définies.</span><span class="sxs-lookup"><span data-stu-id="b261a-106">The following table lists various Exchange properties based on PowerShell cmdlet parameters, their purpose, and the values they should be set to.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="b261a-107">Propriété</span><span class="sxs-lookup"><span data-stu-id="b261a-107">Property</span></span></th>
<th align="left"><span data-ttu-id="b261a-108">Description</span><span class="sxs-lookup"><span data-stu-id="b261a-108">Description</span></span></th>
<th align="left"><span data-ttu-id="b261a-109">Valeur</span><span class="sxs-lookup"><span data-stu-id="b261a-109">Value</span></span></th>
<th align="left"><span data-ttu-id="b261a-110">Impact</span><span class="sxs-lookup"><span data-stu-id="b261a-110">Impact</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b261a-111">AutomateProcessing</span><span class="sxs-lookup"><span data-stu-id="b261a-111">AutomateProcessing</span></span></p></td>
<td align="left"><p><span data-ttu-id="b261a-112">Le paramètre AutomateProcessing active ou désactive le traitement du calendrier sur la boîte aux lettres.</span><span class="sxs-lookup"><span data-stu-id="b261a-112">The AutomateProcessing parameter enables or disables calendar processing on the mailbox.</span></span></p></td>
<td align="left"><p><span data-ttu-id="b261a-113">AutoAccept</span><span class="sxs-lookup"><span data-stu-id="b261a-113">AutoAccept</span></span></p></td>
<td align="left"><p><span data-ttu-id="b261a-114">Le Surface Hub sera en mesure d’accepter ou de refuser automatiquement des demandes de réunion en fonction de sa disponibilité.</span><span class="sxs-lookup"><span data-stu-id="b261a-114">The Surface Hub will be able to automatically accept or decline meeting requests based on its availability.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b261a-115">AddOrganizerToSubject</span><span class="sxs-lookup"><span data-stu-id="b261a-115">AddOrganizerToSubject</span></span></p></td>
<td align="left"><p><span data-ttu-id="b261a-116">Le paramètre AddOrganizerToSubject indique si le nom de l’organisateur de la réunion est utilisé comme objet de la demande de réunion.</span><span class="sxs-lookup"><span data-stu-id="b261a-116">The AddOrganizerToSubject parameter specifies whether the meeting organizer's name is used as the subject of the meeting request.</span></span></p></td>
<td align="left"><p><span data-ttu-id="b261a-117">$False</span><span class="sxs-lookup"><span data-stu-id="b261a-117">$False</span></span></p></td>
<td align="left"><p><span data-ttu-id="b261a-118">L’organisateur de la réunion ne s’affiche qu’une seule fois sur l’écran d’accueil (au lieu de l’indiquer comme organisateur et dans l’objet de la réunion).</span><span class="sxs-lookup"><span data-stu-id="b261a-118">The welcome screen will not show the meeting organizer twice (instead of showing it as both the organizer and in the meeting subject).</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b261a-119">AllowConflicts</span><span class="sxs-lookup"><span data-stu-id="b261a-119">AllowConflicts</span></span></p></td>
<td align="left"><p><span data-ttu-id="b261a-120">Le paramètre AllowConflicts indique si vous autorisez les demandes de réunion conflictuelles.</span><span class="sxs-lookup"><span data-stu-id="b261a-120">The AllowConflicts parameter specifies whether to allow conflicting meeting requests.</span></span></p></td>
<td align="left"><p><span data-ttu-id="b261a-121">$False</span><span class="sxs-lookup"><span data-stu-id="b261a-121">$False</span></span></p></td>
<td align="left"><p><span data-ttu-id="b261a-122">Le Surface Hub refusera les demandes de réunion en conflit avec une autre heure de réunion.</span><span class="sxs-lookup"><span data-stu-id="b261a-122">The Surface Hub will decline meeting requests that conflict with another meeting’s time.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b261a-123">DeleteComments</span><span class="sxs-lookup"><span data-stu-id="b261a-123">DeleteComments</span></span></p></td>
<td align="left"><p><span data-ttu-id="b261a-124">Le paramètre DeleteComments indique si vous souhaitez supprimer ou conserver le texte dans le corps du message de demandes de réunion entrantes.</span><span class="sxs-lookup"><span data-stu-id="b261a-124">The DeleteComments parameter specifies whether to remove or keep any text in the message body of incoming meeting requests.</span></span></p></td>
<td align="left"><p><span data-ttu-id="b261a-125">$False</span><span class="sxs-lookup"><span data-stu-id="b261a-125">$False</span></span></p></td>
<td align="left"><p><span data-ttu-id="b261a-126">Le corps du message des réunions peut être conservé et récupéré à partir d’un Surface Hub en cas de besoin lors d’une réunion.</span><span class="sxs-lookup"><span data-stu-id="b261a-126">The message body of meetings can be retained and retrieved from a Surface Hub if you need it during a meeting.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b261a-127">DeleteSubject</span><span class="sxs-lookup"><span data-stu-id="b261a-127">DeleteSubject</span></span></p></td>
<td align="left"><p><span data-ttu-id="b261a-128">Le paramètre DeleteSubject indique si vous souhaitez supprimer ou conserver l’objet des demandes de réunion entrantes.</span><span class="sxs-lookup"><span data-stu-id="b261a-128">The DeleteSubject parameter specifies whether to remove or keep the subject of incoming meeting requests.</span></span></p></td>
<td align="left"><p><span data-ttu-id="b261a-129">$False</span><span class="sxs-lookup"><span data-stu-id="b261a-129">$False</span></span></p></td>
<td align="left"><p><span data-ttu-id="b261a-130">Les objets des demandes de réunion peuvent s’afficher sur le Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="b261a-130">Meeting request subjects can be shown on the Surface Hub.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b261a-131">RemovePrivateProperty</span><span class="sxs-lookup"><span data-stu-id="b261a-131">RemovePrivateProperty</span></span></p></td>
<td align="left"><p><span data-ttu-id="b261a-132">Le paramètre RemovePrivateProperty indique s’il convient d’effacer l’indicateur privé des demandes de réunion entrantes.</span><span class="sxs-lookup"><span data-stu-id="b261a-132">The RemovePrivateProperty parameter specifies whether to clear the private flag for incoming meeting requests.</span></span></p></td>
<td align="left"><p><span data-ttu-id="b261a-133">$False</span><span class="sxs-lookup"><span data-stu-id="b261a-133">$False</span></span></p></td>
<td align="left"><p><span data-ttu-id="b261a-134">Les objets des réunions privées s’affichent comme «Privé» sur l’écran d’accueil.</span><span class="sxs-lookup"><span data-stu-id="b261a-134">Private meeting subjects will show as Private on the welcome screen.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b261a-135">AddAdditionalResponse</span><span class="sxs-lookup"><span data-stu-id="b261a-135">AddAdditionalResponse</span></span></p></td>
<td align="left"><p><span data-ttu-id="b261a-136">Le paramètre AddAdditionalResponse indique si les informations supplémentaires sont envoyées à partir de la boîte aux lettres de ressources lors de la réponse aux demandes de réunion.</span><span class="sxs-lookup"><span data-stu-id="b261a-136">The AddAdditionalResponse parameter specifies whether additional information will be sent from the resource mailbox when responding to meeting requests.</span></span></p></td>
<td align="left"><p><span data-ttu-id="b261a-137">$True</span><span class="sxs-lookup"><span data-stu-id="b261a-137">$True</span></span></p></td>
<td align="left"><p><span data-ttu-id="b261a-138">Quand une réponse est envoyée à une demande de réunion, un texte personnalisé est fourni dans la réponse.</span><span class="sxs-lookup"><span data-stu-id="b261a-138">When a response is sent to a meeting request, custom text will be provided in the response.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b261a-139">AdditionalResponse</span><span class="sxs-lookup"><span data-stu-id="b261a-139">AdditionalResponse</span></span></p></td>
<td align="left"><p><span data-ttu-id="b261a-140">Le paramètre AdditionalResponse indique les informations supplémentaires à inclure dans les réponses aux demandes de réunion.</span><span class="sxs-lookup"><span data-stu-id="b261a-140">The AdditionalResponse parameter specifies the additional information to be included in responses to meeting requests.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="b261a-141">Remarque </strong> ce texte ne sera pas envoyé tant que AddAdditionalResponse n’est pas défini sur $true.</span><span class="sxs-lookup"><span data-stu-id="b261a-141">Note</strong>This text will not be sent unless AddAdditionalResponse is set to $True.</span></span>
</div>
<div>
 
</div></td>
<td align="left"><p><span data-ttu-id="b261a-142">Vous avez le choix d’utiliser la réponse supplémentaire pour informer les utilisateurs sur la manière d’utiliser un Surface Hub ou la diriger vers des ressources.</span><span class="sxs-lookup"><span data-stu-id="b261a-142">Your choice—the additional response can be used to inform people how to use a Surface Hub or point them towards resources.</span></span></p></td>
<td align="left"><p><span data-ttu-id="b261a-143">L’ajout d’un message de réponse supplémentaire permet de fournir une présentation de l’utilisation d’un Surface Hub en réunion.</span><span class="sxs-lookup"><span data-stu-id="b261a-143">Adding an additional response message can provide people an introduction to how they can use a Surface Hub in their meeting.</span></span></p></td>
</tr>
</tbody>
</table>

 

 

 





