---
title: Installer la version d'évaluation de mise à jour Windows10 Collaboration2020
description: La dernière mise à jour du système d’exploitation surface Hub, mise à jour d’équipe 2020 de Windows 10 est désormais disponible.
keywords: séparer les valeurs par des virgules
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 08/07/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 79e6c35deba5c4635945c3b376a1069e3df324d9
ms.sourcegitcommit: 83530906c7e34c92bbee90b723321acd61e77669
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/08/2020
ms.locfileid: "10918914"
---
# Installer la version d'évaluation de mise à jour Windows10 Collaboration2020 

La dernière mise à jour du système d’exploitation surface Hub, **mise à jour de l’équipe 2020 de Windows 10**, est désormais disponible sans frais supplémentaires pour les appareils Windows insider 50-inch et surface hub 2 55 pouces à partir du [programme Windows Insider](https://insider.windows.com). Le modèle surface Hub 84-pouces sera pris en charge dans la version finale de la mise à jour d’équipe 2020 de Windows 10.

La mise à jour de l’équipe 2020 de Windows 10 apporte des améliorations majeures au déploiement et à la gestion des appareils ainsi qu’aux dernières fonctionnalités de Windows 10. Pour en savoir plus sur les nouveautés, voir le billet de blog suivant: [nouvelle mise à jour du système d’exploitation surface Hub publiée pour public preview.](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/new-surface-hub-os-update-released-for-public-preview/ba-p/1534823) Pour connaître les problèmes connus, voir la section «problèmes connus» ci-dessous.
 
## Prérequis

- Inscrivez-vous au [programme Windows Insider](https://insider.windows.com/).
- Téléchargez la version d’évaluation de la mise à jour d’équipe 2020 de Windows 10 à partir du canal rapide du programme Windows Insider.
- Après l’installation de la version d’évaluation, téléchargez les mises à jour de microprogramme nécessaires. Remarque: les mises à jour de microprogramme ne peuvent pas être désinstallées, même si vous décidez de quitter le programme Windows Insider.

## Préparer votre surface Hub

Avant de commencer, vérifiez que votre surface Hub dispose des dernières mises à jour de Windows Update et que vous enregistrez la clé BitLocker associée à votre appareil.

**Pour rechercher manuellement les mises à jour:**

1. Sur surface Hub, ouvrez **paramètres** , puis entrez vos informations d’identification d’administrateur lorsque vous y êtes invité.
2. Accédez à **mettre à jour &** mettre à jour la sécurité  >  **Windows** , puis sélectionnez **Rechercher les mises à jour**.

Pour plus d’informations, voir [gérer les mises à jour Windows sur surface Hub](https://docs.microsoft.com/surface-hub/manage-windows-updates-for-surface-hub).

**Pour enregistrer manuellement votre clé BitLocker:**

1. Insérez un lecteur USB dans surface Hub.
2. Sur surface Hub, ouvrez **paramètres** , puis entrez vos informations d’identification d’administrateur lorsque vous y êtes invité.
3. Accédez à **mettre à jour &**  >  **restauration**de la sécurité.
4. Sous **BitLocker**, sélectionnez **Enregistrer**. La clé BitLocker est enregistrée dans un fichier texte sur le lecteur USB.

Pour plus d’informations, voir [enregistrer votre clé BitLocker](https://docs.microsoft.com/surface-hub/save-bitlocker-key-surface-hub).
 
## Installation de la version préliminaire de Windows 10 Team 2020 Update preview

1. Sur surface Hub, ouvrez **paramètres** , puis entrez vos informations d’identification d’administrateur lorsque vous y êtes invité.
2. Accédez à **confidentialité > diagnostics & commentaires** et **complet** pour les données de diagnostic. 
3. Accédez à **mettre à jour &**  >  **programme Windows Insider** Security et sélectionnez **commencer**.
4. Suivez les invites pour vous inscrire au programme Windows Insider à l’aide de votre compte professionnelle (recommandé) ou de votre compte Microsoft personnel. Pour plus d’informations sur les avantages liés à l’inscription auprès de votre compte professionnel, voir Inscrivez-vous [au programme Windows Insider pour les entreprises](https://docs.microsoft.com/windows-insider/at-work-pro/wip-4-biz-register).
5. Sous sélectionnez **vos paramètres Insider**, sélectionnez **rapide**.
6. Autorisez surface Hub à installer automatiquement la build Preview et les mises à jour requises du microprogramme sur les 3 à 4 jours suivants. L’appareil télécharge et installe automatiquement les mises à jour dans les [fenêtres de maintenance](https://docs.microsoft.com/surface-hub/manage-windows-updates-for-surface-hub#maintenance-window)journalière. Par exemple:

- Lors de la première fenêtre de maintenance, surface Hub commence à télécharger la version d’évaluation à partir de Windows Update.
- Dans une deuxième fenêtre de maintenance, l’appareil redémarre pour achever la mise à jour.
- Pendant une troisième fenêtre de maintenance, l’appareil télécharge et installe les mises à jour de microprogramme nécessaires.

> [!IMPORTANT]
> Microsoft recommande de réserver le Hub surface pour 3-4 jours pour permettre au périphérique de terminer l’installation de la version d’évaluation et des mises à jour requises du microprogramme. Vous pouvez avoir des problèmes liés à l’interface utilisateur, audio et vidéo si vous utilisez l’appareil pendant ce processus.

### Si vous choisissez d’installer manuellement la version preview et les mises à jour de microprogramme requises:

1. Après vous être inscrit au programme Windows Insider, accédez **Settings**à la  >  **mise à jour des paramètres & sécurité**  >  **Windows Update** , puis sélectionnez **Rechercher les mises à jour** pour installer la version d’évaluation.
2. Après l’installation de la version d’évaluation (il est possible qu’elle prenne jusqu’à 14 heures), sélectionnez **redémarrer maintenant** pour terminer l’installation.
3. Après le redémarrage de l’appareil, accédez à **paramètres**  >  **mise à jour & sécurité**  >  **Windows Update**, puis sélectionnez **Rechercher les mises à jour pour installer les mises à jour de microprogramme nécessaires**.
4. Lorsque le microprogramme est installé, sélectionnez **redémarrer maintenant**.

> [!WARNING]
> Vous pouvez constater des problèmes d’interface utilisateur, audio et vidéo si vous installez la version d’évaluation sans installer les mises à jour requises du microprogramme.

> [!NOTE]
> Si vous choisissez de quitter le programme Windows Insider et que vous rétablissez une version antérieure du système d’exploitation, vous devez d’abord [Réinitialiser votre appareil](https://docs.microsoft.com/surface-hub/device-reset-surface-hub). Par la suite, vous devrez suivre le [premier programme exécuter](https://docs.microsoft.com/surface-hub/first-run-program-surface-hub) pour reconfigurer votre appareil.
 

## En savoir plus

- [Problèmes connus: mise à jour d’équipe 2020 de Windows 10](surface-hub-2020-team-update-known-issues.md)
- [Nouvelle mise à jour du système d’exploitation surface Hub publiée pour la version publique preview.](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/new-surface-hub-os-update-released-for-public-preview/ba-p/1534823)
- [Prise en main du Programme Windows Insider pour Entreprises](https://docs.microsoft.com/windows-insider/at-work-pro/wip-4-biz-manage)