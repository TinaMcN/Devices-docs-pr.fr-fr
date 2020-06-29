---
title: Gérer la rotation du mot de passe du compte d’appareil
description: Découvrez comment configurer des comptes surface Hub 2 locaux avec PowerShell
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
ms.openlocfilehash: ea445588fe2242e3200284a39fdb4a3a8473f94a
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10833996"
---
# <span data-ttu-id="58ded-104">Gérer la rotation du mot de passe du compte d’appareil</span><span class="sxs-lookup"><span data-stu-id="58ded-104">Manage device account password rotation</span></span>

<span data-ttu-id="58ded-105">Vous pouvez configurer l’interface MultiSurface pour modifier automatiquement le mot de passe d’un compte d’appareil sans avoir besoin de mettre à jour manuellement les informations du compte de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="58ded-105">You can configure Surface Hub 2S to automatically change a device account password without requiring you to manually update the device account information.</span></span>

<span data-ttu-id="58ded-106">Si vous activez la rotation du mot de passe, surface Hub 2 modifie le mot de passe tous les 7 jours.</span><span class="sxs-lookup"><span data-stu-id="58ded-106">If you turn on Password Rotation, Surface Hub 2S changes the password every 7 days.</span></span> <span data-ttu-id="58ded-107">Le mot de passe généré automatiquement contient des caractères 15-32, y compris une combinaison de lettres majuscules et minuscules, des chiffres et des caractères spéciaux.</span><span class="sxs-lookup"><span data-stu-id="58ded-107">The automatically generated passwords contain 15-32 characters including  a combination of uppercase and lowercase letters, numbers, and special characters.</span></span>

<span data-ttu-id="58ded-108">Les mots de passe ne changent pas au cours d’une réunion.</span><span class="sxs-lookup"><span data-stu-id="58ded-108">Passwords do not change during a meeting.</span></span> <span data-ttu-id="58ded-109">Si surface Hub 2 est désactivé, l’application tente de changer le mot de passe immédiatement lorsque ce dernier est activé ou toutes les 10 minutes.</span><span class="sxs-lookup"><span data-stu-id="58ded-109">If Surface Hub 2S is turned off, it attempts to change the password immediately when turned on or every 10 minutes until successful.</span></span>
