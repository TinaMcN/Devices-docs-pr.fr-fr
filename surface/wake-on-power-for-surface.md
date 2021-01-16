---
title: Comment activer Wake on Power pour Surface
ms.author: v-todmc
author: mccoybot
audience: ITPro
search.appverid:
- SPO160
- MET150
appliesto:
- Surface Book 3
- Surface Pro 7+
- Surface Pro 7
- Surface Laptop 3
- Surface Pro X
- Surface Laptop Go
ms.custom:
- CI 121602
ms.reviewer: hachidan
description: Décrit comment activer et désactiver la fonction Wake on Power pour les appareils Surface.
keywords: mettre à jour, déployer, pilote, wake-on-lan
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
ms.localizationpriority: medium
ms.topic: article
manager: laurawi
ms.audience: itpro
ms.date: 01/15/2021
ms.openlocfilehash: 6ad359861f6af29c567bf0fbf26878ec15c7c642
ms.sourcegitcommit: 1053479c191fd10651d31a466fad1769fb0cd28b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/16/2021
ms.locfileid: "11271558"
---
# Wake on Power pour les appareils Surface

Les appareils Surface peuvent être éteints lorsque vous êtes absent de votre bureau ou en mode veille prolongée pour économiser l’autonomie de la batterie. Pour améliorer la gestion de ces appareils, Wake on Power permet aux appareils Surface compatibles de démarrer automatiquement lorsqu’ils sont reconnectés à l’alimentation. Pour configurer Wake on Power, vous pouvez utiliser le mode SEMM (Surface Enterprise Management Mode) via le configurateur UEFI Surface ou le Gestionnaire UEFI.

La fonctionnalité Veille sur l’alimentation est disponible sur les appareils suivants :

- Surface Pro 7+
- SurfaceBook3
- SurfacePro7
- Surface Laptop3
- Surface Laptop Go
- SurfaceProX 


## Vue d’ensemble et conditions préalables

Surface UEFI Configurator vous permet d’enregistrer des paramètres UEFI individuels dans un package .msi Windows Installer pour la distribution sur les appareils cibles. 

> [!NOTE]
> Cet article suppose que vous savez utiliser SEMM. Pour plus d’informations, voir la documentation [seMM (Surface Enterprise Management Mode).](surface-enterprise-management-mode.md)

## Pour activer Wake on Power

1.  Téléchargez la dernière version de [Surface UEFI Configurator](https://www.microsoft.com/download/confirmation.aspx?id=46703).
2.  Connectez-vous à votre appareil Surface en tant qu’administrateur, ouvrez **le configurateur UEFI Surface,** sélectionnez **Appareils Surface,** puis sélectionnez **Suivant**.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-1.png" alt-text="Sélectionnez Appareils Surface et Suivant.":::
3.  Sélectionnez **Démarrer,** puis **créez sous** **Package de configuration.**

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-2.png" alt-text="Sélectionnez Créer un package de configuration.":::
4.  Sélectionnez **Protection des**certificats et ajoutez votre fichier .pfx de certificat. 
5. Entrez votre mot de passe, **sélectionnez Suivant,** ajoutez **la protection par**mot de passe, le cas échéant, puis sélectionnez **Suivant.**
6.  Dans la page Choisir le type de surface que **vous souhaitez cibler,** sélectionnez vos appareils cibles selon le cas. Par exemple, **sélectionnez Surface Pro 7.**
7.  Dans la page **Fonctionnalités avancées,** sélectionnez **Wake on Power,** définissez la fonctionnalité sur **On,** puis sélectionnez **Next**.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-3.png" alt-text="Sélectionnez Wake on Power et définissez sur On."::: 
8.  Dans la page **Réussite,** sélectionnez **Fin**.

    > [!NOTE]
    > Si c’est la première fois que vous fournissez des paramètres à votre appareil, vous êtes invité à fournir également les deux derniers caractères de l’empreinte numérique du certificat. 
9.  Enregistrez le package .msi. 

## Appliquer le package MSI 

Vous pouvez appliquer le package MSI aux appareils de votre réseau à l’aide d’outils de distribution de logiciels tels que Microsoft Endpoint Configuration Manager. Cette procédure comprend les étapes d’installation du package sur votre ordinateur local. 

1.  À une invite de commandes avec élévation de niveau élevé, entrez le chemin d’accès complet du fichier .msi pour exécuter le package .msi. 

    ```
    C:\SEMM\wake-on-power.msi 
    ```

2.  Dans la **boîte de dialogue** Avertissement, sélectionnez **OK** ou désactivez BitLocker, le cas échéant.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-4.png" alt-text="Sélectionnez OK ou désactivez BitLocker selon le cas.":::
3.  Dans la page d’accueil, **sélectionnez Suivant** pour exécuter le package et appliquez le paramètre UEFI nouvellement configuré.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-5.png" alt-text="Une page d’accueil, sélectionnez Suivant.":::
4.  Redémarrez votre appareil. 

L’alimentation de veille est maintenant configurée. Pour tester les paramètres, désconnectez votre appareil, déconnectez l’alimentation, puis reconnectez-la. L’appareil doit démarrer automatiquement. 

## Références

Pour plus d’informations, voir les articles suivants. 

- [Mode de gestion SurfaceEnterprise](surface-enterprise-management-mode.md)
- [Wake on LAN for Surface devices](wake-on-lan-for-surface-devices.md)

Encore besoin d’aide? Go to [Microsoft Community](https://answers.microsoft.com/).