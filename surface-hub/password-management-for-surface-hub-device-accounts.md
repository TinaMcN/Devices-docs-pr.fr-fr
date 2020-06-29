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
# Gestion des mots de passe (Surface Hub)

Chaque compte d’appareil Microsoft SurfaceHub nécessite un mot de passe pour l’authentification et pour l’activation des fonctionnalités sur l’appareil. Pour des raisons de sécurité, vous voudrez peut-être modifier (ou «faire tourner») ce mot de passe régulièrement. Toutefois, si le mot de passe du compte d’appareil change, celui qui était stocké sur le SurfaceHub devient non valide, et toutes les fonctionnalités qui dépendent du compte d’appareil sont désactivées. Vous devez alors mettre à jour le mot de passe du compte d’appareil sur le SurfaceHub à partir de l’application Paramètres pour réactiver ces fonctionnalités.

Pour simplifier la gestion des mots de passe de vos comptes d’appareil SurfaceHub, deuxoptions s’offrent à vous:

1.  Désactiver l’expiration du mot de passe du compte d’appareil.
2.  Autoriser le SurfaceHub à faire tourner automatiquement le mot de passe du compte d’appareil.


## Désactiver la rotation du mot de passe du compte d’appareil

Définissez la propriété **PasswordNeverExpires** du compte d’appareil sur True. Vous devez vérifier si cela répond aux exigences de sécurité de votre organisation.


## Autoriser le SurfaceHub à faire tourner automatiquement le mot de passe du compte d’appareil

Le SurfaceHub peut gérer le mot de passe d’un compte d’appareil en le modifiant fréquemment sans que vous ayez besoin de mettre à jour manuellement les informations du compte d’appareil. Vous pouvez activer cette fonctionnalité dans **Paramètres**. Une fois cette fonctionnalité activée, le mot de passe du compte d’appareil est modifié toutes les semaines pendant les heures de maintenance.

Notez que lorsque le mot de passe du compte d’appareil est modifié, le nouveau mot de passe ne s’affiche pas. Si vous devez vous connecter au compte ou fournir à nouveau le mot de passe (par exemple, si vous souhaitez modifier les paramètres du compte d’appareil sur le SurfaceHub), vous devez utiliser ActiveDirectory ou le portail d’administration d’Office365 pour réinitialiser le mot de passe.

> [!IMPORTANT]
> Si votre organisation utilise une topologie hybride (certains services sont hébergés sur site tandis que d’autres le sont en ligne via Office365), vous devez configurer le compte d’appareil au format **domaine\nom_utilisateur**. Dans le cas contraire, la rotation de mot de passe ne fonctionne pas.
