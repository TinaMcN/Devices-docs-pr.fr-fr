---
title: Authentification moderne sur SurfaceHub
description: Cette page décrit l’utilisation de l’authentification moderne sur surface Hub, par contraste de l’authentification de base héritée.
keywords: séparer les valeurs par des virgules
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 09/08/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 14be433923ca564123952c2d1d7b1c158e725af3
ms.sourcegitcommit: d24759da42dfe0b913fd9ebf716407a673c2b818
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/09/2020
ms.locfileid: "11004466"
---
# <span data-ttu-id="a9c0a-104">Authentification moderne sur SurfaceHub</span><span class="sxs-lookup"><span data-stu-id="a9c0a-104">Modern authentication on Surface Hub</span></span>

<span data-ttu-id="a9c0a-105">La prise en charge de l’authentification moderne des comptes Cloud est entièrement intégrée à la prochaine mise à jour de l’équipe 2020 de Windows 10 avec les versions d’évaluation disponibles dans le [programme Windows Insider](https://insider.windows.com/).</span><span class="sxs-lookup"><span data-stu-id="a9c0a-105">Support for modern authentication of cloud-based accounts is fully integrated in the upcoming Windows 10 Team 2020 Update, with preview builds available from the [Windows Insider Program](https://insider.windows.com/).</span></span> <span data-ttu-id="a9c0a-106">Une fois que vous avez [installé la version d’évaluation](surface-hub-install-2020preview.md), vous pouvez effectuer une migration à partir de l’authentification de base héritée et bénéficier des dernières améliorations en matière de sécurité dans Microsoft Azure et Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="a9c0a-106">Once you [install the preview build](surface-hub-install-2020preview.md), you can migrate from legacy basic authentication and utilize the latest security improvements from Microsoft Azure and Exchange Online.</span></span> <span data-ttu-id="a9c0a-107">Avec la mise à jour 2020, surface Hub prend en charge les protocoles Exchange Web Services (EWS) et l’authentification basée sur la bibliothèque d’authentification active ADAL</span><span class="sxs-lookup"><span data-stu-id="a9c0a-107">With the 2020 Update, Surface Hub supports Exchange Web Services (EWS) protocols and Active Directory Authentication Library (ADAL) based authentication enabling Exchange Online for Device Account syncing.</span></span>

<span data-ttu-id="a9c0a-108">Pour les nouveaux comptes Cloud, surface Hub utilise automatiquement l’authentification moderne pour se connecter à Exchange Online sans nécessiter de configuration supplémentaire au-delà de la simple création de comptes d’appareil à l’aide du format [alias@contoso.com](mailto:alias@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="a9c0a-108">For new cloud-based accounts, Surface Hub automatically uses Modern Authentication to connect to Exchange Online without requiring additional configuration beyond simply creating device accounts using the format [alias@contoso.com](mailto:alias@contoso.com).</span></span> <span data-ttu-id="a9c0a-109">N’utilisez pas le format hérité-Contoso\alias, qui n’est pas pris en charge pour l’authentification moderne.</span><span class="sxs-lookup"><span data-stu-id="a9c0a-109">Do not use the legacy format – Contoso\alias, which is not supported for modern authentication.</span></span> <span data-ttu-id="a9c0a-110">Pour plus d’informations, reportez-vous à la section [créer un compte de périphérique de surface Hub 2](https://docs.microsoft.com/surface-hub/surface-hub-2s-account).</span><span class="sxs-lookup"><span data-stu-id="a9c0a-110">For more information, see [Create Surface Hub 2S device account](https://docs.microsoft.com/surface-hub/surface-hub-2s-account).</span></span>

> [!NOTE]
> <span data-ttu-id="a9c0a-111">Surface Hub ne prend pas en charge l’authentification moderne pour les comptes locaux.</span><span class="sxs-lookup"><span data-stu-id="a9c0a-111">Surface Hub does not support modern authentication for on-premises accounts.</span></span> <span data-ttu-id="a9c0a-112">Les comptes doivent être créés dans le Cloud.</span><span class="sxs-lookup"><span data-stu-id="a9c0a-112">The accounts must be created in the cloud.</span></span>

