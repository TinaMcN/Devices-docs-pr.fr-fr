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
# Propriétés de Microsoft Exchange (Surface Hub)


Certaines propriétés MicrosoftExchange du compte d’appareil sont définies sur des valeurs dédiées pour optimiser l’expérience de réunion sur le Surface Hub. Le tableau suivant répertorie les différentes propriétés Exchange en fonction des paramètres d’applet de commande Windows PowerShell, leur objectif et les valeurs sur lesquelles elles doivent être définies.

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Propriété</th>
<th align="left">Description</th>
<th align="left">Valeur</th>
<th align="left">Impact</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>AutomateProcessing</p></td>
<td align="left"><p>Le paramètre AutomateProcessing active ou désactive le traitement du calendrier sur la boîte aux lettres.</p></td>
<td align="left"><p>AutoAccept</p></td>
<td align="left"><p>Le Surface Hub sera en mesure d’accepter ou de refuser automatiquement des demandes de réunion en fonction de sa disponibilité.</p></td>
</tr>
<tr class="even">
<td align="left"><p>AddOrganizerToSubject</p></td>
<td align="left"><p>Le paramètre AddOrganizerToSubject indique si le nom de l’organisateur de la réunion est utilisé comme objet de la demande de réunion.</p></td>
<td align="left"><p>$False</p></td>
<td align="left"><p>L’organisateur de la réunion ne s’affiche qu’une seule fois sur l’écran d’accueil (au lieu de l’indiquer comme organisateur et dans l’objet de la réunion).</p></td>
</tr>
<tr class="odd">
<td align="left"><p>AllowConflicts</p></td>
<td align="left"><p>Le paramètre AllowConflicts indique si vous autorisez les demandes de réunion conflictuelles.</p></td>
<td align="left"><p>$False</p></td>
<td align="left"><p>Le Surface Hub refusera les demandes de réunion en conflit avec une autre heure de réunion.</p></td>
</tr>
<tr class="even">
<td align="left"><p>DeleteComments</p></td>
<td align="left"><p>Le paramètre DeleteComments indique si vous souhaitez supprimer ou conserver le texte dans le corps du message de demandes de réunion entrantes.</p></td>
<td align="left"><p>$False</p></td>
<td align="left"><p>Le corps du message des réunions peut être conservé et récupéré à partir d’un Surface Hub en cas de besoin lors d’une réunion.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>DeleteSubject</p></td>
<td align="left"><p>Le paramètre DeleteSubject indique si vous souhaitez supprimer ou conserver l’objet des demandes de réunion entrantes.</p></td>
<td align="left"><p>$False</p></td>
<td align="left"><p>Les objets des demandes de réunion peuvent s’afficher sur le Surface Hub.</p></td>
</tr>
<tr class="even">
<td align="left"><p>RemovePrivateProperty</p></td>
<td align="left"><p>Le paramètre RemovePrivateProperty indique s’il convient d’effacer l’indicateur privé des demandes de réunion entrantes.</p></td>
<td align="left"><p>$False</p></td>
<td align="left"><p>Les objets des réunions privées s’affichent comme «Privé» sur l’écran d’accueil.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>AddAdditionalResponse</p></td>
<td align="left"><p>Le paramètre AddAdditionalResponse indique si les informations supplémentaires sont envoyées à partir de la boîte aux lettres de ressources lors de la réponse aux demandes de réunion.</p></td>
<td align="left"><p>$True</p></td>
<td align="left"><p>Quand une réponse est envoyée à une demande de réunion, un texte personnalisé est fourni dans la réponse.</p></td>
</tr>
<tr class="even">
<td align="left"><p>AdditionalResponse</p></td>
<td align="left"><p>Le paramètre AdditionalResponse indique les informations supplémentaires à inclure dans les réponses aux demandes de réunion.</p>
<div class="alert">
<strong>Remarque </strong> ce texte ne sera pas envoyé tant que AddAdditionalResponse n’est pas défini sur $true.
</div>
<div>
 
</div></td>
<td align="left"><p>Vous avez le choix d’utiliser la réponse supplémentaire pour informer les utilisateurs sur la manière d’utiliser un Surface Hub ou la diriger vers des ressources.</p></td>
<td align="left"><p>L’ajout d’un message de réponse supplémentaire permet de fournir une présentation de l’utilisation d’un Surface Hub en réunion.</p></td>
</tr>
</tbody>
</table>

 

 

 





