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
ms.openlocfilehash: 271831651280299a40c4e7a7480fa86e29bd1cf5
ms.sourcegitcommit: f875a45961ff5f3c04006afc8690b5e5965e4d80
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/31/2020
ms.locfileid: "10903004"
---
# Mise en éveil des appareils surface

Les appareils surface peuvent être éteints lorsque vous êtes absent du bureau ou configurés pour économiser la batterie. Pour améliorer la gestion de ces appareils, l’éveil à la consommation permet aux périphériques de surface compatibles de démarrer automatiquement lors de leur reconnexion à l’alimentation. La configuration de la mise en éveil nécessite l’utilisation du mode de gestion de surface entreprise (SEMM) par le biais du Configurateur de surface UEFI ou du gestionnaire UEFI.

La mise en éveil est une fonctionnalité disponible sur les appareils suivants:

- SurfaceBook3
- SurfacePro7
- Surface Laptop3
- SurfaceProX 

## Présentation et configuration requise

Vous pouvez utiliser le configurateur surface UEFI pour configurer les paramètres UEFI individuels enregistrés dans un package Windows Installer. msi pour une distribution vers des appareils cibles. 

> [!NOTE]
> Cet article part du principe que vous êtes familiarisé avec l’utilisation de SEMM. Pour plus d’informations, reportez-vous à la documentation du [mode de gestion des entreprises de surface (SEMM)](surface-enterprise-management-mode.md) .

## Pour activer la mise en éveil

1.  Téléchargez la version la plus récente de [surface Configurator Configurator](https://www.microsoft.com/download/confirmation.aspx?id=46703).
2.  Connectez-vous à votre périphérique surface en tant qu’administrateur, ouvrez le **Configurateur de surface UEFI**, sélectionnez **appareils surface**, puis sélectionnez **suivant**.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-1.png" alt-text="Sélectionnez périphériques surface, puis sélectionnez suivant.":::
3.  Sélectionnez **Démarrer** , puis sous **package de configuration** , sélectionnez **créer**.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-2.png" alt-text="Sélectionnez créer un package de configuration.":::
4.  Sélectionnez **protection des certificats** et ajoutez votre fichier Certificate. pfx. Après avoir entré votre mot de passe, sélectionnez **suivant**. Ajoutez une **protection par mot de passe**, le cas échéant, puis sélectionnez **suivant**.
5.  Dans la page **sélectionnez le type de surface que vous souhaitez cibler** , sélectionnez les appareils cibles appropriés. Par exemple, **surface Pro 7**.
6.  **Sur la**page **fonctionnalités avancées** , sélectionnez **éveil et activation** . Sélectionnez **Suivant**.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-3.png" alt-text="Sélectionnez éveil et activation."::: 
7.  Dans la page **réussite** , sélectionnez **fin**. S’il s’agit de votre première utilisation de paramètres pour votre appareil, vous serez invité à fournir les deux derniers caractères de l’empreinte du certificat. 
8.  Enregistrez le package. msi. 

## Appliquer le package MSI 

Vous pouvez appliquer le package MSI aux appareils de votre réseau à l’aide d’outils de distribution de logiciels tels que Microsoft Endpoint Configuration Manager. Cette procédure décrit comment installer le package sur votre ordinateur local. 

1.  Ouvrez une invite de commandes avec élévation de privilèges et entrez le chemin d’accès complet du fichier. msi pour exécuter le package. msi. 

    ```
    C:\SEMM\wake-on-power.msi 
    ```

2.  Dans la boîte de dialogue d' **Avertissement** , sélectionnez **OK** ou désactivez BitLocker selon le cas.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-4.png" alt-text="Sélectionnez OK ou désactivez BitLocker selon le cas.":::
3.  Dans la page d’accueil, sélectionnez **Next (suivant** ) pour exécuter le package et appliquer le paramètre UEFI nouvellement configuré.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-5.png" alt-text="Dans la page Bienvenue, sélectionnez suivant.":::
4.  Redémarrez votre appareil. 

La mise en éveil est désormais configurée. Pour tester le paramètre, éteignez votre appareil, débranchez le cordon d’alimentation, puis rebranchez le cordon d’alimentation. L’appareil démarre automatiquement. 

## Informations supplémentaires

Pour plus d’informations, consultez les articles suivants. 

- [Mode de gestion SurfaceEnterprise](surface-enterprise-management-mode.md)
- [Wake on LAN pour les appareils surface](wake-on-lan-for-surface-devices.md)

Encore besoin d’aide? Accédez à la [communauté Microsoft](https://answers.microsoft.com/).