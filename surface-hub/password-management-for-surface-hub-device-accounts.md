---
title: Gestion des mots de passe (Surface Hub)
description: Chaque compte d’appareil Microsoft Surface Hub nécessite un mot de passe pour l’authentification et pour l’activation des fonctionnalités sur l’appareil.
ms.assetid: 0FBFB546-05F0-430E-905E-87111046E4B8
ms.reviewer: ''
manager: laurawi
keywords: mot de passe, gestion des mots de passe, rotation de mot de passe, compte d’appareil
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.localizationpriority: medium
ms.openlocfilehash: bef626fce875d5074f3ed47ed957e821beec7c77
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10834026"
---
# <span data-ttu-id="e4758-104">Gestion des mots de passe (Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="e4758-104">Password management (Surface Hub)</span></span>

<span data-ttu-id="e4758-105">Chaque compte d’appareil Microsoft SurfaceHub nécessite un mot de passe pour l’authentification et pour l’activation des fonctionnalités sur l’appareil.</span><span class="sxs-lookup"><span data-stu-id="e4758-105">Every Microsoft Surface Hub device account requires a password to authenticate and enable features on the device.</span></span> <span data-ttu-id="e4758-106">Pour des raisons de sécurité, vous voudrez peut-être modifier (ou «faire tourner») ce mot de passe régulièrement.</span><span class="sxs-lookup"><span data-stu-id="e4758-106">For security reasons, you may want to change (or "rotate") this password regularly.</span></span> <span data-ttu-id="e4758-107">Toutefois, si le mot de passe du compte d’appareil change, celui qui était stocké sur le SurfaceHub devient non valide, et toutes les fonctionnalités qui dépendent du compte d’appareil sont désactivées.</span><span class="sxs-lookup"><span data-stu-id="e4758-107">However, if the device account’s password changes, the password that was previously stored on the Surface Hub will be invalid, and all features that depend on the device account will be disabled.</span></span> <span data-ttu-id="e4758-108">Vous devez alors mettre à jour le mot de passe du compte d’appareil sur le SurfaceHub à partir de l’application Paramètres pour réactiver ces fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="e4758-108">You will need to update the device account’s password on the Surface Hub from the Settings app to re-enable these features.</span></span>

<span data-ttu-id="e4758-109">Pour simplifier la gestion des mots de passe de vos comptes d’appareil SurfaceHub, deuxoptions s’offrent à vous:</span><span class="sxs-lookup"><span data-stu-id="e4758-109">To simplify password management for your Surface Hub device accounts, there are two options:</span></span>

1.  <span data-ttu-id="e4758-110">Désactiver l’expiration du mot de passe du compte d’appareil.</span><span class="sxs-lookup"><span data-stu-id="e4758-110">Turn off password expiration for the device account.</span></span>
2.  <span data-ttu-id="e4758-111">Autoriser le SurfaceHub à faire tourner automatiquement le mot de passe du compte d’appareil.</span><span class="sxs-lookup"><span data-stu-id="e4758-111">Allow the Surface Hub to automatically rotate the device account’s password.</span></span>


## <span data-ttu-id="e4758-112">Désactiver la rotation du mot de passe du compte d’appareil</span><span class="sxs-lookup"><span data-stu-id="e4758-112">Turn off password rotation for the device account</span></span>

<span data-ttu-id="e4758-113">Définissez la propriété **PasswordNeverExpires** du compte d’appareil sur True.</span><span class="sxs-lookup"><span data-stu-id="e4758-113">Set the device account’s **PasswordNeverExpires** property to True.</span></span> <span data-ttu-id="e4758-114">Vous devez vérifier si cela répond aux exigences de sécurité de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="e4758-114">You should verify whether this meets your organization’s security requirements.</span></span>


## <span data-ttu-id="e4758-115">Autoriser le SurfaceHub à faire tourner automatiquement le mot de passe du compte d’appareil</span><span class="sxs-lookup"><span data-stu-id="e4758-115">Allow the Surface Hub to automatically rotate the device account’s password</span></span>

<span data-ttu-id="e4758-116">Le SurfaceHub peut gérer le mot de passe d’un compte d’appareil en le modifiant fréquemment sans que vous ayez besoin de mettre à jour manuellement les informations du compte d’appareil.</span><span class="sxs-lookup"><span data-stu-id="e4758-116">The Surface Hub can manage a device account’s password by changing it frequently without requiring you to manually update the device account’s information.</span></span> <span data-ttu-id="e4758-117">Vous pouvez activer cette fonctionnalité dans **Paramètres**.</span><span class="sxs-lookup"><span data-stu-id="e4758-117">You can enable this feature in **Settings**.</span></span> <span data-ttu-id="e4758-118">Une fois cette fonctionnalité activée, le mot de passe du compte d’appareil est modifié toutes les semaines pendant les heures de maintenance.</span><span class="sxs-lookup"><span data-stu-id="e4758-118">Once enabled, the device account's password will change weekly during maintenance hours.</span></span>

<span data-ttu-id="e4758-119">Notez que lorsque le mot de passe du compte d’appareil est modifié, le nouveau mot de passe ne s’affiche pas.</span><span class="sxs-lookup"><span data-stu-id="e4758-119">Note that when the device account’s password is changed, you will not be shown the new password.</span></span> <span data-ttu-id="e4758-120">Si vous devez vous connecter au compte ou fournir à nouveau le mot de passe (par exemple, si vous souhaitez modifier les paramètres du compte d’appareil sur le SurfaceHub), vous devez utiliser ActiveDirectory ou le portail d’administration d’Office365 pour réinitialiser le mot de passe.</span><span class="sxs-lookup"><span data-stu-id="e4758-120">If you need to sign in to the account, or to provide the password again (for example, if you want to change the device account settings on the Surface Hub), then you'll need use Active Directory or the Office 365 admin portal to reset the password.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e4758-121">Si votre organisation utilise une topologie hybride (certains services sont hébergés sur site tandis que d’autres le sont en ligne via Office365), vous devez configurer le compte d’appareil au format **domaine\nom_utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="e4758-121">If your organization uses a hybrid topology (some services are hosted on-premises and some are hosted online through Office 365), you must setup the device account in **domain\username** format.</span></span> <span data-ttu-id="e4758-122">Dans le cas contraire, la rotation de mot de passe ne fonctionne pas.</span><span class="sxs-lookup"><span data-stu-id="e4758-122">Otherwise, password rotation will not work.</span></span>
