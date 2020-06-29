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
# Gérer la rotation du mot de passe du compte d’appareil

Vous pouvez configurer l’interface MultiSurface pour modifier automatiquement le mot de passe d’un compte d’appareil sans avoir besoin de mettre à jour manuellement les informations du compte de l’appareil.

Si vous activez la rotation du mot de passe, surface Hub 2 modifie le mot de passe tous les 7 jours. Le mot de passe généré automatiquement contient des caractères 15-32, y compris une combinaison de lettres majuscules et minuscules, des chiffres et des caractères spéciaux.

Les mots de passe ne changent pas au cours d’une réunion. Si surface Hub 2 est désactivé, l’application tente de changer le mot de passe immédiatement lorsque ce dernier est activé ou toutes les 10 minutes.
