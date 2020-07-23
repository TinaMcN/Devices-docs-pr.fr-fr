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
# Authentification moderne sur surface Hub

La prise en charge de l’authentification moderne des comptes Cloud est entièrement intégrée à la mise à jour de l’équipe 2020 de Windows 10, qui vous permet de migrer à partir de l’authentification de base héritée et de bénéficier des dernières améliorations en matière de sécurité à partir de Microsoft Azure et Exchange Online. Avec la mise à jour 2020, surface Hub prend en charge les protocoles Exchange Web Services (EWS) et l’authentification basée sur la bibliothèque d’authentification active ADAL

Pour les nouveaux comptes Cloud, surface Hub utilise automatiquement l’authentification moderne pour se connecter à Exchange Online sans nécessiter de configuration supplémentaire au-delà de la simple création de comptes d’appareil à l’aide du format [alias@contoso.com](mailto:alias@contoso.com). N’utilisez pas le format hérité-Contoso\alias, qui n’est pas pris en charge pour l’authentification moderne. Pour plus d’informations, reportez-vous à la section [créer un compte de périphérique de surface Hub 2](https://docs.microsoft.com/surface-hub/surface-hub-2s-account).

> [!NOTE]
> Surface Hub ne prend pas en charge l’authentification moderne pour les comptes locaux. Les comptes doivent être créés dans le Cloud.

