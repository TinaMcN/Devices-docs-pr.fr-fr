---
title: Déploiement d’applications sur SurfaceHub2S à l’aide d’Intune
description: Découvrez comment déployer des applications sur surface Hub 2 à l’aide de Intune.
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
ms.openlocfilehash: 51e54a5b2881519f2fc361675253c9e50bad0864
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10833282"
---
# Déploiement d’applications sur SurfaceHub2S à l’aide d’Intune

Vous pouvez installer des applications supplémentaires pour répondre aux besoins de votre équipe ou de votre organisation.

## Recommandations en matière de développement

- Le SurfaceHub exécute uniquement des [applications de plateforme Windows universelle (UWP)](https://msdn.microsoft.com/windows/uwp/get-started/whats-a-uwp). Les applications créées à l’aide de [Desktop App Converter](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-run-desktop-app-converter) ne s’exécuteront pas sur le Surface Hub.
- Les applications doivent être ciblées pour la [famille d’appareils universels](https://msdn.microsoft.com/library/windows/apps/dn894631) ou la famille d'appareils Windows.
- Surface Hub ne prend en charge que les [applications sous licence hors connexion](https://docs.microsoft.com/microsoft-store/distribute-offline-apps) de la [Boutique Microsoft pour les entreprises](https://businessstore.microsoft.com/store).
- Par défaut, les applications doivent être signées par le WindowsStore pour être installées. Au cours des phases de test et de développement, vous pouvez également choisir d’exécuter des applicationsUWP signées par le développeur en plaçant l’appareil en mode développeur.
- Lorsque vous développez et soumettez des applications sur le Microsoft Store, définissez les options disponibilité de la famille d’appareils et gestion des licences pour vérifier que les applications sont disponibles pour s’exécuter sur surface Hub.
- Vous avez besoin d’informations d’identification d’administrateur pour installer des applications sur un appareil surface Hub. Conçu pour une utilisation dans des salles de réunion et d’autres espaces partagés, surface Hub empêche les utilisateurs normaux d’accéder au Microsoft Store pour télécharger et installer des applications.

## Recommandations en matière de déploiement

Vous pouvez déployer des applications de plateforme Windows universelle (UWP) sur surface Hub 2 à l’aide de Intune, ce qui facilite le déploiement d’applications sur les appareils.

1. Pour déployer des applications, activez le GPM pour votre organisation. Dans le portail Intune, sélectionnez **Intune** en tant qu’autorité GPM (recommandé). <br>

    ![Choix de l’autorité GPM](images/sh2-set-intune5.png)

2. Activez le Microsoft Store pour les entreprises dans Intune. Ouvrez Intune et sélectionnez **applications clientes**  >  **Microsoft Store pour les entreprises.** <br>

    ![Activer le Windows Store pour les entreprises](images/sh2-deploy-apps-sync.png)

3. Dans Intune, ouvrez le **Microsoft Store pour les entreprises** et sélectionnez **paramètres**  >  **distribuer**les  >  **outils de gestion**. Choisissez **Microsoft Intune** comme outil de gestion. <br>

    ![Ajouter Intune comme outil de gestion](images/sh2-set-intune8.png)

4. Dans la boutique Microsoft pour les entreprises, sélectionnez **paramètres**de la  >  **Boutique**  >  **Shopping Experience**, puis sélectionnez **afficher les applications hors connexion**. Les applications hors connexion font référence aux applications qui peuvent être synchronisées avec Intune et centralisées sur un appareil.
5. Après avoir activé les achats en mode hors connexion, vous pouvez acquérir des licences hors connexion pour les applications que vous pouvez synchroniser avec Intune et déployer en tant que gestion des licences de périphériques.
6. Dans **Intune**les  >  **applications clientes**Intune  >  **Microsoft Store pour les entreprises**, sélectionnez **synchroniser**.
7. Dans la page applications clientes, recherchez l’application dans la liste d’applications. Affectez les applications au groupe ou groupes de périphériques souhaité. Sélectionnez **Assignments**le  >  **groupe ajouter**des devoirs. <br>

![* Affectation d’applications à des groupes *](images/sh2-assign-group.png) <br>

8. Sous type d’affectation, sélectionnez **obligatoire**. <br>

![* Affectation d’applications à des groupes *](images/sh2-add-group.png) <br>

9. Pour les groupes sélectionnés, sélectionnez **licence** de l’appareil, puis **OK** et enregistrez le devoir. <br>
 
![* Affectation d’applications à des groupes *](images/sh2-apps-assign.png)
