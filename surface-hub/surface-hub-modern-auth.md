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
# Authentification moderne sur SurfaceHub

La prise en charge de l’authentification moderne des comptes Cloud est entièrement intégrée à la prochaine mise à jour de l’équipe 2020 de Windows 10 avec les versions d’évaluation disponibles dans le [programme Windows Insider](https://insider.windows.com/). Une fois que vous avez [installé la version d’évaluation](surface-hub-install-2020preview.md), vous pouvez effectuer une migration à partir de l’authentification de base héritée et bénéficier des dernières améliorations en matière de sécurité dans Microsoft Azure et Exchange Online. Avec la mise à jour 2020, surface Hub prend en charge les protocoles Exchange Web Services (EWS) et l’authentification basée sur la bibliothèque d’authentification active ADAL

Pour les nouveaux comptes Cloud, surface Hub utilise automatiquement l’authentification moderne pour se connecter à Exchange Online sans nécessiter de configuration supplémentaire au-delà de la simple création de comptes d’appareil à l’aide du format [alias@contoso.com](mailto:alias@contoso.com). N’utilisez pas le format hérité-Contoso\alias, qui n’est pas pris en charge pour l’authentification moderne. Pour plus d’informations, reportez-vous à la section [créer un compte de périphérique de surface Hub 2](https://docs.microsoft.com/surface-hub/surface-hub-2s-account).

> [!NOTE]
> Surface Hub ne prend pas en charge l’authentification moderne pour les comptes locaux. Les comptes doivent être créés dans le Cloud.

