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
ms.date: 12/10/2020
ms.localizationpriority: Medium
appliesto:
- Surface Hub 2S 2020 Update
ms.openlocfilehash: dd0b0ad257abbc52c443b075e62db00dcf5713ea
ms.sourcegitcommit: 4b1cfcac090910a3ea634929942063eb51fc54f9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/11/2020
ms.locfileid: "11206278"
---
# Authentification moderne sur SurfaceHub

La prise en charge de l’authentification moderne des comptes Cloud est entièrement intégrée à la [mise à jour de l’équipe 2020 de Windows 10](surface-hub-2020-update.md). Après l’installation de la mise à jour 2020, vous pouvez effectuer une migration à partir de l’authentification de base héritée et utiliser les dernières améliorations en matière de sécurité à partir de Microsoft Azure et Exchange Online. Avec la mise à jour 2020, surface Hub prend en charge les protocoles Exchange Web Services (EWS) et l’authentification basée sur la bibliothèque d’authentification active ADAL

Pour les nouveaux comptes Cloud, surface Hub utilise automatiquement l’authentification moderne pour se connecter à Exchange Online sans nécessiter de configuration supplémentaire au-delà de la simple création de comptes d’appareil à l’aide du format [alias@contoso.com](mailto:alias@contoso.com). N’utilisez pas le format hérité-Contoso\alias, qui n’est pas pris en charge pour l’authentification moderne. Pour plus d’informations, reportez-vous à la section [créer un compte de périphérique de surface Hub 2](https://docs.microsoft.com/surface-hub/surface-hub-2s-account).

> [!NOTE]
> Surface Hub ne prend pas en charge l’authentification moderne pour les comptes locaux. Les comptes doivent être créés dans le Cloud.

