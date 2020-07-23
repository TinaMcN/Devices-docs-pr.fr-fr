---
title: Installation de Windows 10 Team 2020 Update Preview Build
description: La dernière mise à jour du système d’exploitation surface Hub, mise à jour d’équipe 2020 de Windows 10 est désormais disponible.
keywords: séparer les valeurs par des virgules
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 07/22/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 9177b184d7a1d6dca63e94740b6208987d97229f
ms.sourcegitcommit: df1e178b724966e4cf8ff219c5e937e6c31cd9b4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/22/2020
ms.locfileid: "10894110"
---
# Installation de Windows 10 Team 2020 Update Preview Build 

La dernière mise à jour du système d’exploitation surface Hub, **mise à jour de l’équipe 2020 de Windows 10**, est désormais disponible sans frais supplémentaires pour les appareils Windows insider 50-inch et surface hub 2 55 pouces à partir du [programme Windows Insider](https://insider.windows.com). Le modèle surface Hub 84-pouces sera pris en charge dans la version finale de la mise à jour d’équipe 2020 de Windows 10.

La mise à jour de l’équipe 2020 de Windows 10 apporte des améliorations majeures au déploiement et à la gestion des appareils ainsi qu’aux dernières fonctionnalités de Windows 10. Pour en savoir plus sur les nouveautés, voir le billet de blog suivant: [nouvelle mise à jour du système d’exploitation surface Hub publiée pour public preview.](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/new-surface-hub-os-update-released-for-public-preview/ba-p/1534823) Pour connaître les problèmes connus, voir la section «problèmes connus» ci-dessous.
 
## Conditions préalables

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
2. Accédez à **mettre à jour &**  >  **programme Windows Insider** Security et sélectionnez **commencer**.
3. Suivez les invites pour vous inscrire au programme Windows Insider à l’aide de votre compte professionnelle (recommandé) ou de votre compte Microsoft personnel. Pour plus d’informations sur les avantages liés à l’inscription auprès de votre compte professionnel, voir Inscrivez-vous [au programme Windows Insider pour les entreprises](https://docs.microsoft.com/windows-insider/at-work-pro/wip-4-biz-register).
4. Sous sélectionnez **vos paramètres Insider**, sélectionnez **rapide**.
5. Autorisez surface Hub à installer automatiquement la build Preview et les mises à jour requises du microprogramme sur les 3 à 4 jours suivants. L’appareil télécharge et installe automatiquement les mises à jour dans les [fenêtres de maintenance](https://docs.microsoft.com/surface-hub/manage-windows-updates-for-surface-hub#maintenance-window)journalière. Par exemple:

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
 
## Problèmes connus: build de l’aperçu des mises à jour de Windows 10 Team 2020

### Problèmes liés aux graphiques, à l’audio et à l’interface utilisateur 

Vous pouvez avoir des problèmes liés à l’interface utilisateur et aux graphiques divers si vous installez la version d’évaluation, mais que vous n’avez pas installé les mises à jour requises du microprogramme ultérieurement. Microsoft envisage de résoudre ces problèmes lors de la publication de la mise à jour d’équipe 2020 de Windows 10.

### Surface Hub 84-pouces: problèmes de graphiques et d’interface utilisateur

Vous pouvez avoir des problèmes liés à l’interface utilisateur et aux graphiques divers si vous installez la version d’évaluation sur un appareil 84-pouces surface Hub. Surface Hub 84-pouces sera pris en charge dans la version finale de la mise à jour de l’équipe 2020 de Windows 10.

### La connexion est affectée lorsque des stratégies d’accès conditionnel sont appliquées

- La connexion échoue lorsque vous tentez de vous connecter à des applications telles que le tableau blanc collaboratif Microsoft. Les utilisateurs doivent d’abord se connecter à partir de [mes réunions et fichiers](https://support.microsoft.com/help/4506480/sign-in-to-see-your-meetings-and-files-on-surface-hub) à partir du menu Démarrer.

- La connexion échoue si votre compte d’utilisateur est inscrit à un autre client Azure AD que celui utilisé par surface Hub pour accéder à Azure AD.

Microsoft envisage de résoudre ces problèmes lors de la publication de la mise à jour d’équipe 2020 de Windows 10.

### Windows Update vous invite à installer de nouveaux pilotes lorsqu’aucun n’est disponible

Lorsque vous accédez à **paramètres**de  >  **mise à jour & sécurité**  >  **Windows Update** après avoir installé Windows 10 Team 2020 et les mises à jour requises du microprogramme, le message d’erreur suivant risque de s’afficher: 

- «Il est possible que le pilote actif sur votre PC soit supérieur au pilote que nous essayons d’installer. Nous allons continuer à procéder à l’installation.» 

Cette erreur peut être ignorée en toute sécurité. Microsoft étudie activement ce problème.

### Impossible d’installer des stratégies de surface Hub à l’aide de packages de mise en service

Les packages de mise en service qui utilisent des stratégies du fournisseur de services de configuration (CSP) surface Hub ne s’installent pas. Pour le moment, utilisez Microsoft Intune ou un autre fournisseur de gestion des périphériques mobiles (GPM) pour appliquer les stratégies de surface Hub. Microsoft envisage de résoudre ce problème lors de la publication de la mise à jour d’équipe 2020 de Windows 10.

### Invite de suppression du lecteur USB prématurément lors de la première exécution

Lors de l’utilisation d’un package de mise à service de surface Hub lors de la première exécution, vous êtes invité à supprimer le lecteur USB avant que l’appareil ne puisse lire le fichier de configuration surface Hub. Ignorez le message si vous utilisez un fichier de configuration pour configurer votre compte d’appareil. Microsoft étudie activement ce problème.
 
### Impossible de configurer les paramètres du proxy lors de la première exécution

Si vous utilisez un proxy pour vous connecter à Internet, il est possible que vous ayez une connectivité Internet limitée lors du premier programme d’exécution. Microsoft envisage de résoudre ce problème lors de la publication de la mise à jour d’équipe 2020 de Windows 10.
 
### Une erreur s’affiche lorsque vous téléchargez des applications à partir de la boutique Microsoft

Pour télécharger une application à partir du Microsoft Store, une invite s’affiche pour vous connecter. Un problème connu entraîne l’apparition d’une erreur lors de la connexion, mais n’affecte pas la possibilité de télécharger des applications. Microsoft étudie activement ce problème.

### Surface Hub 2 a perdu par intermittence une connexion Wi-Fi.

Essayez de débrancher votre appareil et de le brancher ou d’utiliser un câble Ethernet pour vous connecter à Internet. Microsoft étudie activement ce problème.

### Surface Hub 2 ne parvient pas à sortir du mode veille par intermittence

Surface Hub 2 risque de ne pas fonctionner de façon intermittente et de ne plus répondre sur un écran affichant le logo Microsoft. Essayez de débrancher votre appareil et de le brancher. 

Pour éviter ce problème, procédez comme suit:

1. Sur surface Hub, ouvrez **paramètres** , puis entrez vos informations d’identification d’administrateur lorsque vous y êtes invité.
2. Accédez à la session **surface Hub**  >  **& alimentation**. 
3. Sous **lors de la mise en veille de l’appareil, utilisez ce paramètre d’alimentation**, sélectionnez **veille connectée.**
4. Sous **en l’absence de personne, mettez le périphérique en veille après**, sélectionnez **jamais.**

Microsoft envisage de résoudre ce problème dans une mise à jour de microprogramme avant la version finale de la mise à jour de Windows 10 Team 2020.

### Problèmes de projection lorsque l’application de connexion n’est pas dans l’affichage

- Lorsque vous utilisez un câble pour projeter sur surface Hub, touchback cesse de fonctionner si vous naviguez hors de l’application connexion.
- Lorsque vous projetez sur surface Hub à l’aide de Miracast, la connexion sans fil s’interrompt dès que vous quittez l’application de connexion.

Microsoft étudie activement ces problèmes.

### Skype entreprise n’utilise pas de proxy pour le trafic multimédia

Pour certains appareils qui utilisent un proxy, Skype entreprise est en mesure de se connecter, mais n’utilise pas le serveur proxy pour le trafic multimédia. Microsoft étudie activement ce problème.

Nous vous invitons à partager vos idées et vos suggestions grâce au support Microsoft.

## En savoir plus

- [Nouvelle mise à jour du système d’exploitation surface Hub publiée pour la version publique preview.](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/new-surface-hub-os-update-released-for-public-preview/ba-p/1534823)
- [Prise en main du Programme Windows Insider pour Entreprises](https://docs.microsoft.com/windows-insider/at-work-pro/wip-4-biz-manage)