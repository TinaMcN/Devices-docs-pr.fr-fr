---
title: Suppression de SSD dans des appareils surface compatibles
description: Cet article, destiné aux techniciens informatiques qualifiés, présente les meilleures pratiques recommandées en matière de suppression et de remplacement de SSDs dans surface Laptop 3, surface Pro X et surface Laptop Go.
ms.prod: w10
ms.localizationpriority: medium
ms.mktglfcycl: manage
ms.sitesec: library
author: mccoybot
ms.author: v-todmc
ms.topic: article
ms.date: 10/21/2020
ms.reviewer: ''
manager: laurawi
ms.audience: itpro
audience: ITPro
appliesto:
- Surface Laptop 3
- Surface Pro X
- Surface Laptop Go
ms.custom:
- CI 121887
- CSSTroubleshoot
ms.openlocfilehash: 56c740b39d86ea3fab386e88efa6932e050bb957
ms.sourcegitcommit: 959d2d856b1e5b5c72cd636f576b5feb1b633048
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/21/2020
ms.locfileid: "11133169"
---
# Recommandations en matière de suppression de disques durs de périphériques de surface compatibles

> [!IMPORTANT]
> Cet article est destiné aux techniciens informatiques qualifiés au sein d’une organisation d’entreprise. Il présente les meilleures pratiques recommandées pour les techniciens informatiques qualifiés lors de la suppression et du remplacement de SSDs sur les appareils surface compatibles suivants: 

- Surface Laptop3 
- SurfaceProX 
- Surface Laptop Go

> [!WARNING]
> L’ouverture de périphériques et le remplacement des composants de périphériques peuvent présenter un choc électrique, un dommage de l’appareil, un incendie, des risques liés au préjudice personnel et autres dangers.  Soyez toujours prudent lorsque vous exercez de telles activités. Suivez les consignes et procédures de sécurité qui sont identifiées dans le [Guide de suppression de rSSD pour les entreprises](https://www.microsoft.com/download/100440). Nous vous recommandons d’obtenir une assistance technique si vous ne pouvez pas suivre les consignes de sécurité et les procédures indiquées dans le Guide de suppression de rSSD pour les entreprises.

## Conditions préalables

> [!IMPORTANT]
> Cet article part du principe que vous comprenez les consignes générales en matière de sécurité et les stratégies et procédures de sécurité décrites dans le «Guide de suppression rSSD pour les entreprises».

## Préparer la suppression de votre microinstallation 

### Installer les mises à jour les plus récentes 

Avant de commencer, assurez-vous que votre version de Windows dispose des dernières mises à jour:

1.  Accédez à **Start**  >  **Settings**  >  **mise à jour**des paramètres de démarrage & sécurité, puis sélectionnez **Rechercher les mises à jour**.
2. Installez toutes les mises à jour disponibles.
3. Vérifiez les mots de passe nécessaires pour accéder à l’appareil.  
 
## Gérer BitLocker 

> [!NOTE]
> Cette section contient des recommandations pour les organisations ayant activé le chiffrement BitLocker pour les disques durs. Pour plus d’informations, reportez-vous au  [Guide de récupération de BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan). 

### Si le chiffrement BitLocker est désactivé lors de la suppression et du remplacement de disques durs

Si l’appareil peut être déchiffré avant la suppression et le remplacement de votre appareil, procédez comme suit pour désactiver BitLocker:

1.  Dans **paramètres**, tapez **BitLocker** et sélectionnez **gérer BitLocker**. 
2.  Sélectionnez **Désactiver BitLocker**. 
3.  Allumez l’appareil. 

### Si le chiffrement BitLocker est activé lors de la suppression et du remplacement de disques durs

Si l’appareil est chiffré avant la suppression et le remplacement de votre appareil, procédez comme suit pour générer une clé de récupération BitLocker et l’enregistrer dans le stockage USB:

1.  Dans **paramètres**, tapez **BitLocker**.
2. Sélectionnez **gérer BitLocker**  > **générer la clé de récupération BitLocker**.
2.  Insérez un lecteur USB. 
4.  Enregistrez la clé de récupération sur le stockage USB.  
5.  Retirez le lecteur USB.  
6.  Allumez l’appareil. 

## Supprimer et remplacer la SSD 

1.  Supprimez le SSD en suivant les instructions du [Guide de suppression de rSSD pour les entreprises](https://www.microsoft.com/download/100440). 
2.  Insérez la nouvelle image SSD dans un nouvel appareil et connectez le nouvel appareil à une connexion Internet câblée.
3.  Allumez le nouvel appareil. Il est possible que l’appareil passe par une mise à jour du microprogramme lors du démarrage.  
 
## Après suppression et remplacement de disques durs

### Gérer les SSDs non chiffrés 

Si le SSD n’est pas chiffré lors du transfert, procédez comme suit: 

1.  Accédez à **options de connexion**  >  **mot de passe** (représenté par l’icône de clé située sur le côté gauche).  
2.  Entrez le mot de passe et connectez-vous en attente d’exécution de l’authentification à deux facteurs (le cas échéant).
3.  Une fois que vous êtes connecté, **accédez à la**  >  **Account**  >  **déconnexion**de votre compte.  
4.  Reconnectez-vous à l’aide du mot de passe et configurez Windows Hello et un code confidentiel lorsque vous y êtes invité. 
    - Si l’appareil a été désactivé par BitLocker pour faciliter la suppression et le remplacement de disques durs et que vous souhaitez activer BitLocker après le remplacement, accédez à **BitLocker**  >  **Manage BitLocker**  >  **Resume BitLocker**.  
6.  Exécutez le [Kit de connaissances Microsoft surface diagnostic pour les entreprises](surface-diagnostic-toolkit-for-business-intro.md) (SDT) pour vérifier le fonctionnement complet de l’appareil.  
7.  Recherchez l’activation de Windows en accédant à activation des **paramètres**  >  **Activation**.  Si un message d’erreur s’affiche, sélectionnez **résoudre les problèmes**. 
8.  Pour vérifier le compte Office, ouvrez l' **application Office**, accédez au compte de **fichier**,  >  **Account** puis recherchez les messages d’erreur.  

### Gestion des SSDs chiffrés 

> [!NOTE]
> Vous devez disposer d’un deuxième appareil pour lire la clé de récupération BitLocker qui a été enregistrée sur le lecteur USB. 

Si le SSD est crypté lors du transfert, procédez comme suit:

1.  Insérez le lecteur USB contenant la clé de récupération BitLocker dans le second appareil. 
2.  Ouvrez le fichier. txt contenant la clé de récupération BitLocker. 
3.  Entrez manuellement la clé de récupération BitLocker sur le nouvel appareil contenant la clé SSD d’origine.  
4.  Après avoir entré la clé de récupération BitLocker, accédez au mot de passe des **options de connexion**  >  **Password** (représenté par l’icône de clé située sur le côté gauche).  
5.  Entrez le mot de passe et connectez-vous en attente d’exécution de l’authentification à deux facteurs (le cas échéant).
6.  Une fois que vous êtes connecté, **accédez à la**  >  **Account**  >  **déconnexion**de votre compte.  
7.  Reconnectez-vous à l’aide du mot de passe, puis configurez Windows Hello et ajoutez un code confidentiel. 
8.  Si l’appareil a été désactivé par BitLocker pour faciliter la suppression et le remplacement de disques durs, et si vous souhaitez activer BitLocker après le remplacement, accédez à **paramètres**  >  **BitLocker**  >  **gérer**BitLocker-  >  **reprise**BitLocker.  
9.  Exécutez **[SDT](surface-diagnostic-toolkit-for-business-intro.md)** pour vérifier la fonctionnalité complète de l’appareil.  
10. Pour vérifier l’activation de Windows, sélectionnez activation des **paramètres**  >  **Activation**.  Si un message d’erreur s’affiche, sélectionnez **résoudre les problèmes**.
11. Pour vérifier l’état du compte Office, ouvrez l' **application Office**, puis accédez à compte de **fichier**  >  **Account** pour vérifier la présence de messages d’erreur.

## En savoir plus

- [Guide de suppression de rSSD pour les entreprises](https://www.microsoft.com/download/100440)
- [Guide de récupération BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)

Encore besoin d’aide? Accédez à la [communauté Microsoft](https://answers.microsoft.com/).