---
title: Modifier le compte d’appareil Microsoft Surface Hub
description: Vous pouvez changer le compte dans Paramètres pour ajouter un compte si aucun compte n’est configuré ou en modifier les propriétés s’il est déjà mis en service.
ms.assetid: AFC43043-3319-44BC-9310-29B1F375E672
ms.reviewer: ''
manager: laurawi
keywords: modifier compte d’appareil, modifier les propriétés, SurfaceHub
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.localizationpriority: medium
ms.openlocfilehash: b90ef3e208f1e76e4b02fb9f49e3e24030947bc7
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10834080"
---
# Modifier le compte d’appareil Microsoft Surface Hub


Vous pouvez changer le compte d’appareil dans Paramètres pour ajouter un compte si aucun compte n’est encore configuré ou en modifier les propriétés s’il est déjà mis en service.

## Détails


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Valeur</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Nom principal de l’utilisateur</p></td>
<td align="left"><p>Nom d’utilisateur principal (UPN) du compte d’appareil</p></td>
</tr>
<tr class="even">
<td align="left"><p>Mot de passe</p></td>
<td align="left"><p>Mot de passe correspondant au compte d’appareil.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Domaine</p></td>
<td align="left"><p>Domaine auquel appartient le compte d’appareil. Il est inutile de renseigner ce champ pour les comptes Office 365.</p></td>
</tr>
<tr class="even">
<td align="left"><p>Nom d’utilisateur</p></td>
<td align="left"><p>Nom d’utilisateur du compte d’appareil. Il est inutile de renseigner ce champ pour les comptes Office365.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Adresse SIP (Session Initiation Protocol)</p></td>
<td align="left"><p>Adresse SIP du compte d’appareil.</p></td>
</tr>
<tr class="even">
<td align="left"><p>Serveur Microsoft Exchange</p></td>
<td align="left"><p>Serveur Exchange du compte d’appareil. Le nom d’utilisateur et le mot de passe du compte d’appareil doivent permettre une authentification sur le serveur Exchange spécifié.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Activer les services Exchange</p></td>
<td align="left"><p>Lorsque ce paramètre est coché, tous les services Exchange sont activés (par exemple, le calendrier sur l’écran d’accueil ou l’envoi de tableaux blancs par courrier électronique). S’il n’est pas coché, tous les services Exchange sont désactivés et il est inutile d’indiquer le serveur Exchange.</p></td>
</tr>
</tbody>
</table>

 

## Que se passe-t-il?


Le nom d’utilisateur principal et le mot de passe sont utilisés pour valider le compte dans AD ou Azure AD. Si la validation échoue, vous devrez peut-être indiquer le nom d’utilisateur et de domaine.

Nous essaierons de déduire l’adresse SIP à l’aide des informations d’identification fournies. Si une adresse SIP est introuvable, Skype Entreprise utilisera le nom d’utilisateur principal comme adresse SIP. Si cela ne fonctionne pas, vous devrez indiquer l’adresse SIP.

L’adresse du serveur Exchange doit être fournie si l’appareil ne peut pas trouver de serveur associé aux informations d’identification. Microsoft Surface Hub utilisera le serveur Exchange pour communiquer avec ActiveSync, qui active plusieurs fonctionnalités clés sur l’appareil.

## Rubriques connexes


[Gérer le Microsoft SurfaceHub](manage-surface-hub.md)

[Guide de l’administrateur Microsoft Surface Hub](surface-hub-administrators-guide.md)

 

 





