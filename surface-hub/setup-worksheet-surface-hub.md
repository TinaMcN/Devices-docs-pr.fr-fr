---
title: Fiche d’installation (SurfaceHub)
description: Lorsque vous avez terminé l’installation préalable et que vous êtes prêt à commencer la première installation de votre SurfaceHub, assurez-vous que vous disposez de toutes les informations répertoriées dans cette section.
ms.assetid: AC6F925B-BADE-48F5-8D53-8B6FFF6EE3EB
ms.reviewer: ''
manager: laurawi
keywords: Fiche d’installation, installation préalable, première installation
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 06/20/2019
ms.localizationpriority: medium
ms.openlocfilehash: e0c31082669336d3762fd02f46a939aa8b0ff1bc
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10833852"
---
# Fiche d’installation (SurfaceHub)


Lorsque vous avez terminé l’installation préalable et que vous êtes prêt à commencer la première installation de votre SurfaceHub, assurez-vous que vous disposez de toutes les informations répertoriées dans cette section.

Vous devez remplir une seule liste pour chaque Surface Hub que vous avez besoin de configurer, bien que certaines informations puissent être utilisées sur tous les SurfaceHub, notamment les informations du proxy ou les informations d’identification de domaine. Certaines de ces informations peuvent ne pas être nécessaires, en fonction de la façon dont vous avez décidé de configurer votre appareil, ou selon la manière dont l’environnement est configuré pour l’infrastructure de votre organisation.

<table>
<tr>
<th>Propriété</th>
<th>Utilisation</th>
<th>Exemple</th>
<th>Valeur réelle</th>
</tr>
<tr>
<td>
<p>Informations du proxy</p>
</td>
<td>
<p>Si votre réseau utilise un proxy pour l’accès au réseau et/ou à Internet, vous devez fournir un script ou des informations de serveur/port.</p>
</td>
<td>
<p>Script de proxy: <code>http://contoso/proxy.pa</code> </br>
- - ou - </br>
Informations de serveur et de port: 10.10.10.100, port80
</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p>Informations d’identification du réseau sans fil (nom d’utilisateur et mot de passe)</p>
</td>
<td>
<p>Si vous décidez de connecter votre appareil au Wi-Fi et que votre réseau sans fil nécessite des informations d’identification utilisateur.</p>
</td>
<td>
<p>admin1@contoso.com, #MyPassw0rd</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p>Nom d’utilisateur principal du compte d’appareil ou Domaine\nom d’utilisateur et mot de passe du compte d’appareil</p>
</td>
<td>
<p>Il s’agit du nom d’utilisateur principal ou du domaine\nom d’utilisateur, et du mot de passe du compte d’appareil. Le courrier, le calendrier et Skype Entreprise dépendent d’un compte d’appareil compatible.</p>
</td>
<td>
<p> UPN: ConfRoom15@contoso.com, #Passw0rd1 </br>
- - ou - <br> 
Domaine et nom d’utilisateur: CONTOSO\ConfRoom15, #Passw0rd1</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p>Serveur MicrosoftExchange du compte d’appareil</p>
</td>
<td>
<p>Il s’agit du serveur Exchange du compte d’appareil.
Le courrier, le calendrier et Skype Entreprise dépendent d’un compte d’appareil compatible.
Pour que le courrier et le calendrier fonctionnent, le compte d’appareil doit disposer d’un serveur Exchange valide. L’appareil essaiera de trouver cet élément automatiquement.</p>
</td>
<td>
<p>outlook.office365.com</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p>AdresseSIP (Session Initiation Protocol) du compte d’appareil</p>
</td>
<td>
<p>Il s’agit de l’adresseSIP Skype Entreprise du compte d’appareil.
Le courrier, le calendrier et SkypeEntreprise dépendent d’un compte d’appareil compatible.
Pour que SkypeEntreprise fonctionne, le compte d’appareil doit disposer d’une adresseSIP valide. L’appareil essaiera de trouver cet élément automatiquement.</p>
</td>
<td>
<p>sip: ConfRoom15@contoso.com</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p>Nom convivial</p>
</td>
<td>
<p>Le nom convivial de l’appareil est le nom de diffusion que les utilisateurs voient lorsqu’ils essaient de se connecter sans fil au SurfaceHub. Ce nom sera clairement affiché sur l’écran du Surface Hub.
Nous vous conseillons de choisir un nom convivial identifiable et unique afin que les utilisateurs puissent distinguer un Surface Hub d’un autre lorsqu’ils essaient de se connecter.</p>
</td>
<td>
<p>Salle de conférence15</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p>Nom de l’appareil</p>
</td>
<td>
<p>Le nom de l’appareil est le nom qui sera utilisé pour la jonction de domaine et est l’identité que vous verrez dans votre fournisseur GPM si l’appareil est inscrit à GPM.
Le nom d’appareil que vous choisissez ne doit pas être identique à celui de tout autre appareil dans le domaine Active Directory de l’utilisateur (si vous décidez de joindre l’appareil au domaine). L’appareil ne peut pas joindre le domaine si son nom n’est pas unique.
</p>
</td>
<td>
<p>confroom15</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td colspan="4">
<p><b>SI VOUS JOIGNEZ AZUREAD</b></p>
</td>
</tr>
<tr>
<td>
<p>Informations d’identification de l’utilisateur client AzureAD (nom d’utilisateur et mot de passe)</p>
</td>
<td>
<p>Si vous décidez de transformer des utilisateurs de votre organisation Azure Active Directory (Azure AD) en administrateurs sur l’appareil, alors vous devrez joindre Azure AD.
Pour joindre AzureAD, vous aurez besoin d’informations d’identification d’utilisateur valides.</p>
</td>
<td>
<p>admin1@contoso.com, #MyPassw0rd</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td colspan="4">
<p><b>SI VOUS JOIGNEZ UN DOMAINE</b></p>
</td>
</tr>
<tr>
<td>
<p>Domaine à joindre</p>
</td>
<td>
<p>Il s’agit du domaine que vous devez joindre pour qu’un groupe de sécurité de votre choix puisse administrer l’appareil.
Vous aurez besoin du nom de domaine complet.</p>
</td>
<td>
<p>contoso (nom court) OU contoso.corp.com (nom de domaine complet)</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p>Informations d’identification du compte de domaine (nom d’utilisateur et mot de passe)</p>
</td>
<td>
<p>Un domaine ne peut pas être joint sauf si vous fournissez des informations d’identification de compte suffisantes pour joindre le domaine. Une fois que vous fournissez un domaine à joindre et des informations d’identification pour joindre le domaine, un groupe de sécurité de votre choix peut modifier les paramètres sur l’appareil.</p>
</td>
<td>
<p>admin1, #MyPassw0rd</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p>Alias du groupe de sécurité administrateur</p>
</td>
<td>
<p>Il s’agit d’un groupe de sécurité dans votre Active Directory (AD); tous les membres de ce groupe de sécurité peuvent modifier les paramètres sur l’appareil.</p>
</td>
<td>
<p>SurfaceHubAdmins</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td colspan="4">
<p><b>SI VOUS RECOUREZ À UN ADMINISTRATEUR LOCAL</b></p>
</td>
</tr>
<tr>
<td>
<p>Informations d’identification du compte administrateur local (nom d’utilisateur et mot de passe)</p>
</td>
<td>
<p>Si vous décidez de ne pas joindre un domaine AD ou Azure AD, vous pouvez créer un compte administrateur local sur l’appareil.</p>
</td>
<td>
<p>admin1, #MyPassw0rd</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td colspan="4">
<p><b>SI VOUS AVEZ BESOIN D’INSTALLER DES CERTIFICATS OU DES APPLICATIONS</b></p>
</td>
</tr>
<tr>
<td>
<p>Lecteur USB</p>
</td>
<td>
<p>Si vous savez avant la première utilisation que vous souhaitez installer des certificats ou des applications universelles, suivez les étapes de la section <a href="provisioning-packages-for-certificates-surface-hub.md">Créer des packages de mise en service</a>. Vos packages de mise en service seront créés sur un lecteur USB.</p>
</td>
<td>
<p></p>
</td>
<td>
<p></p>
</td>
</tr>
</table> 





