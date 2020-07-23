---
title: Authentification moderne sur surface Hub
description: Cette page décrit l’utilisation de l’authentification moderne sur surface Hub, par contraste de l’authentification de base héritée.
keywords: séparer les valeurs par des virgules
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 07/21/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 387d799e15ae25bb1043e9ee3417aa3c31676825
ms.sourcegitcommit: 8738f44f2f4c86e3a45e9fbcbe6469388fc15924
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/22/2020
ms.locfileid: "10893137"
---
# <span data-ttu-id="ddc0b-104">Authentification moderne sur surface Hub</span><span class="sxs-lookup"><span data-stu-id="ddc0b-104">Modern authentication on Surface Hub</span></span>

<span data-ttu-id="ddc0b-105">La prise en charge de l’authentification moderne des comptes Cloud est entièrement intégrée à la mise à jour de l’équipe 2020 de Windows 10, qui vous permet de migrer à partir de l’authentification de base héritée et de bénéficier des dernières améliorations en matière de sécurité à partir de Microsoft Azure et Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="ddc0b-105">Support for modern authentication of cloud-based accounts is fully integrated in Windows 10 Team 2020 Update, allowing you to migrate from legacy basic authentication and utilize the latest security improvements from Microsoft Azure and Exchange Online.</span></span> <span data-ttu-id="ddc0b-106">Avec la mise à jour 2020, surface Hub prend en charge les protocoles Exchange Web Services (EWS) et l’authentification basée sur la bibliothèque d’authentification active ADAL</span><span class="sxs-lookup"><span data-stu-id="ddc0b-106">With the 2020 Update, Surface Hub supports Exchange Web Services (EWS) protocols and Active Directory Authentication Library (ADAL) based authentication enabling Exchange Online for Device Account syncing.</span></span>

<span data-ttu-id="ddc0b-107">Pour les nouveaux comptes Cloud, surface Hub utilise automatiquement l’authentification moderne pour se connecter à Exchange Online sans nécessiter de configuration supplémentaire au-delà de la simple création de comptes d’appareil à l’aide du format [alias@contoso.com](mailto:alias@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="ddc0b-107">For new cloud-based accounts, Surface Hub automatically uses Modern Authentication to connect to Exchange Online without requiring additional configuration beyond simply creating device accounts using the format [alias@contoso.com](mailto:alias@contoso.com).</span></span> <span data-ttu-id="ddc0b-108">N’utilisez pas le format hérité-Contoso\alias, qui n’est pas pris en charge pour l’authentification moderne.</span><span class="sxs-lookup"><span data-stu-id="ddc0b-108">Do not use the legacy format – Contoso\alias, which is not supported for modern authentication.</span></span> <span data-ttu-id="ddc0b-109">Pour plus d’informations, reportez-vous à la section [créer un compte de périphérique de surface Hub 2](https://docs.microsoft.com/surface-hub/surface-hub-2s-account).</span><span class="sxs-lookup"><span data-stu-id="ddc0b-109">For more information, see [Create Surface Hub 2S device account](https://docs.microsoft.com/surface-hub/surface-hub-2s-account).</span></span>

> [!NOTE]
> <span data-ttu-id="ddc0b-110">Surface Hub ne prend pas en charge l’authentification moderne pour les comptes locaux.</span><span class="sxs-lookup"><span data-stu-id="ddc0b-110">Surface Hub does not support modern authentication for on-premises accounts.</span></span> <span data-ttu-id="ddc0b-111">Les comptes doivent être créés dans le Cloud.</span><span class="sxs-lookup"><span data-stu-id="ddc0b-111">The accounts must be created in the cloud.</span></span>

