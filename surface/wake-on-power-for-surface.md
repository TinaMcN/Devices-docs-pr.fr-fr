---
title: Comment activer la mise en éveil pour surface
ms.author: v-todmc
author: mccoybot
ms.date: 7/30/2020
audience: ITPro
search.appverid:
- SPO160
- MET150
appliesto:
- Surface Book 3
- Surface Pro 7
- Surface Laptop 3
- Surface Pro X
ms.custom:
- CI 121602
ms.reviewer: johnk@cadencepreferred.com
description: Décrit comment activer et désactiver la mise en éveil pour les appareils surface.
keywords: mise à jour, déploiement, pilote, WOL, Wake-on-LAN
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
ms.localizationpriority: medium
ms.topic: article
manager: laurawi
ms.audience: itpro
ms.openlocfilehash: 272c19baedb295abac08e90012246e453b88f42f
ms.sourcegitcommit: 6fd7008992503db9ae1f56654aa80110348924d3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/03/2020
ms.locfileid: "10903393"
---
# Wake on Power pour les appareils Surface

Les appareils surface peuvent être éteints lorsque vous n’êtes pas sur votre bureau, ou en mode hibernation pour économiser l’autonomie de la batterie. Pour améliorer la gestion de ces appareils, l’éveil à la consommation permet aux périphériques de surface compatibles de démarrer automatiquement lorsqu’ils sont reconnectés à l’alimentation. Pour configurer la mise en éveil, vous pouvez utiliser le mode de gestion de surface Enterprise (SEMM) via le configurateur de surface ou le gestionnaire UEFI.

La fonctionnalité de mise en éveil est disponible sur les appareils suivants:

- SurfaceBook3
- SurfacePro7
- Surface Laptop3
- SurfaceProX 

## Présentation et configuration requise

Le Configurator du Configurateur de surface vous permet d’enregistrer les paramètres UEFI individuels d’un package Windows Installer. msi à des fins de distribution à des appareils cibles. 

> [!NOTE]
> Cet article part du principe que vous savez comment utiliser SEMM. Pour plus d’informations, reportez-vous à la documentation du [mode de gestion des entreprises de surface (SEMM)](surface-enterprise-management-mode.md) .

## Pour activer la mise en éveil

1.  Téléchargez la version la plus récente de [surface Configurator Configurator](https://www.microsoft.com/download/confirmation.aspx?id=46703).
2.  Connectez-vous à votre périphérique surface en tant qu’administrateur, ouvrez le **Configurateur de surface UEFI**, sélectionnez **appareils surface**, puis sélectionnez **suivant**.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-1.png" alt-text="Sélectionnez périphériques surface, puis sélectionnez suivant.":::
3.  Sélectionnez **Démarrer**, puis cliquez sur **créer** sous **package de configuration**.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-2.png" alt-text="Sélectionnez créer un package de configuration.":::
4.  Sélectionnez **protection de certificat**, puis ajoutez votre fichier Certificate. pfx. 
5. Entrez votre mot de passe, sélectionnez **suivant**, ajoutez une **protection par mot de passe**, le cas échéant, puis sélectionnez **suivant**.
6.  Dans la page **sélectionnez le type de surface que vous souhaitez cibler** , sélectionnez les appareils cibles appropriés. Par exemple, sélectionnez **surface Pro 7**.
7.  Sur la page **fonctionnalités avancées** , sélectionnez **mise en éveil** **, activez la fonctionnalité, puis**sélectionnez **suivant**.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-3.png" alt-text="Sélectionnez éveil et activation."::: 
8.  Dans la page **réussite** , sélectionnez **fin**.

    > [!NOTE]
    > S’il s’agit de la première fois que vous fournissez des paramètres à votre appareil, vous serez invité à fournir également les deux derniers caractères de l’empreinte du certificat. 
9.  Enregistrez le package. msi. 

## Appliquer le package MSI 

Vous pouvez appliquer le package MSI aux appareils de votre réseau à l’aide d’outils de distribution de logiciels tels que Microsoft Endpoint Configuration Manager. Cette procédure inclut les étapes permettant d’installer le package sur votre ordinateur local. 

1.  À l’invite de commandes avec élévation de privilèges, entrez le chemin d’accès complet du fichier. msi pour exécuter le package. msi. 

    ```
    C:\SEMM\wake-on-power.msi 
    ```

2.  Dans la boîte de dialogue d' **Avertissement** , sélectionnez **OK** ou désactiver BitLocker, selon le cas.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-4.png" alt-text="Sélectionnez OK ou désactivez BitLocker selon le cas.":::
3.  Dans la page d’accueil, sélectionnez **Next (suivant** ) pour exécuter le package et appliquer le paramètre UEFI nouvellement configuré.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-5.png" alt-text="Dans la page Bienvenue, sélectionnez suivant.":::
4.  Redémarrez votre appareil. 

La mise en éveil est désormais configurée. Pour tester les paramètres, éteignez votre appareil, débranchez le cordon d’alimentation, puis rebranchez le cordon d’alimentation. Le périphérique doit démarrer automatiquement. 

## Références

Pour plus d’informations, consultez les articles suivants. 

- [Mode de gestion SurfaceEnterprise](surface-enterprise-management-mode.md)
- [Wake on LAN pour les appareils surface](wake-on-lan-for-surface-devices.md)

Encore besoin d’aide? Accédez à la [communauté Microsoft](https://answers.microsoft.com/).