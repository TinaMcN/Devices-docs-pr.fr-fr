---
title: Suppression du SSD sur les appareils Surface compatibles
description: Cet article, destiné aux techniciens informatiques qualifiés, décrit les meilleures pratiques recommandées pour la suppression et le remplacement de SSD dans Surface Laptop 3, Surface Pro X et Surface Laptop Go.
ms.prod: w10
ms.localizationpriority: medium
ms.mktglfcycl: manage
ms.sitesec: library
author: mccoybot
ms.author: v-todmc
ms.topic: article
ms.date: 01/13/2020
ms.reviewer: ''
manager: laurawi
ms.audience: itpro
audience: ITPro
appliesto:
- Surface Pro 7+
- Surface Pro X
- Surface Laptop Go
- Surface Laptop 3
ms.custom:
- CI 121887
- CSSTroubleshoot
ms.openlocfilehash: b65feb24803311aba809819cd6da273ed6934c75
ms.sourcegitcommit: 41124d496abaa38a0d989159f2afec3542d562ca
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/14/2021
ms.locfileid: "11269105"
---
# Meilleures pratiques pour la suppression de SSD des appareils Surface compatibles

> [!IMPORTANT]
> Cet article est destiné uniquement aux techniciens informatiques qualifiés d’une organisation d’entreprise. Il décrit les meilleures pratiques recommandées pour une utilisation par des techniciens informatiques qualifiés lors de la suppression et du remplacement de SSD sur les appareils Surface compatibles suivants : 

- Surface Pro 7+
- SurfaceProX
- Surface Laptop Go
- Surface Laptop3

> [!WARNING]
> L’ouverture d’appareils et le remplacement des composants de l’appareil peuvent présenter une catastrophe électrique, des dommages de l’appareil, des incendies et des risques personnels, ainsi que d’autres risques.  Faites toujours preuve de prudence lorsque vous entreprenons de telles activités. Suivez les précautions et procédures de sécurité identifiées dans le Guide de suppression [rSSD pour Entreprise.](https://www.microsoft.com/download/100440) Nous vous recommandons d’obtenir une assistance professionnelle si vous ne pouvez pas suivre les précautions et procédures de sécurité spécifiées dans le « Guide de suppression rSSD pour entreprise ».

## Conditions préalables

> [!IMPORTANT]
> Cet article suppose que vous comprenez les stratégies et procédures générales de sécurité et de sécurité décrites dans le « Guide de suppression rSSD pour entreprise ».

## Préparer la suppression de SSD 

### Installer les dernières mises à jour 

Avant de commencer, assurez-vous que les dernières mises à jour de votre version de Windows sont installées :

1.  Go to **Start**  >  **Settings**  >  **Update & Security,** and select Check for **updates**.
2. Installez toutes les mises à jour disponibles.
3. Vérifiez les mots de passe nécessaires pour accéder à l’appareil.  
 
## Gérer BitLocker 

> [!NOTE]
> Cette section contient des recommandations pour les organisations qui ont activé le chiffrement BitLocker pour les disques durs. Pour plus d’informations, [voir le Guide de récupération BitLocker.](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan) 

### Si le chiffrement BitLocker est désactivé lors de la suppression et du remplacement de SSD

Si l’appareil peut être déchiffré avant la suppression et le remplacement de SSD, suivez les étapes suivantes pour désactiver BitLocker :

1.  Dans **Paramètres,** **tapez BitLocker,** puis **sélectionnez Gérer BitLocker.** 
2.  Sélectionnez **Désactiver BitLocker.** 
3.  Alimentation de l’appareil. 

### Si le chiffrement BitLocker est activé lors de la suppression et du remplacement de SSD

Si l’appareil est chiffré avant la suppression et le remplacement de SSD, suivez ces étapes pour générer une clé de récupération BitLocker et l’enregistrer sur le stockage USB :

1.  Dans **Paramètres,** **tapez BitLocker**.
2. Sélectionnez **Gérer BitLocker**  > **générer la clé de récupération BitLocker.**
2.  Insérez un lecteur USB. 
4.  Enregistrez la clé de récupération dans le stockage USB.  
5.  Supprimez le lecteur USB.  
6.  Alimentation de l’appareil. 

## Supprimer et remplacer le SSD 

1.  Supprimez le SSD en suivant les instructions appropriées pour votre appareil incluses dans le Guide de suppression [rSSD pour Entreprise.](https://www.microsoft.com/download/100440) 
2.  Placez le SSD d’origine dans un nouvel appareil et connectez-le à une connexion Internet câblé.
3.  Alimentation sur le nouvel appareil. L’appareil peut passer par une mise à jour du microprogramme au démarrage.  
 
## Après la suppression et le remplacement du SSD

### Gérer les SSD non chiffrés 

Si le SSD n’est pas chiffré pendant le transfert, suivez les étapes suivantes : 

1.  Go to **Sign-In Options**  >  **Password** (represented by the key icon on the left side).  
2.  Entrez le mot de passe et connectez-vous en attendant la fin de l’authentification à deux facteurs (le cas échéant).
3.  Une fois que vous êtes entièrement connectez-vous, allez sur **Démarrer**  >  **la**  >  **signature du compte.**  
4.  Connectez-vous à l’aide du mot de passe et définissez Windows Hello et un code confidentiel lorsque vous y êtes invité. 
    - Si l’appareil a été désactivé par BitLocker pour faciliter la suppression et le remplacement de SSD, et que vous souhaitez activer BitLocker après le remplacement, allez à **BitLocker**  >  **Manage BitLocker**  >  **Resume BitLocker**.  
6.  Exécutez [microsoft Surface Diagnostic Shared Computer Toolkit for Business](surface-diagnostic-toolkit-for-business-intro.md) (SDT) pour vérifier les fonctionnalités complètes de l’appareil.  
7.  Recherchez l’activation de Windows en naviguant vers **l’activation des**  >  **paramètres.**  Si vous voyez des messages d’erreur, sélectionnez **Résoudre les problèmes.** 
8.  Vérifiez le compte Office en ouvrant **** **l’application Office,** accédez à Compte de  >  **** fichier, puis recherchez les messages d’erreur.  

### Gestion des SSD chiffrés 

> [!NOTE]
> Vous devez avoir un deuxième appareil pour lire la clé de récupération BitLocker qui a été enregistrée sur le lecteur USB. 

Si le SSD est chiffré pendant le transfert, suivez les étapes suivantes :

1.  Insérez le lecteur USB qui contient la clé de récupération BitLocker dans le deuxième appareil. 
2.  Ouvrez le fichier .txt qui contient la clé de récupération Bitlocker. 
3.  Entrez manuellement la clé de récupération BitLocker sur le nouvel appareil qui contient le SSD d’origine.  
4.  Une fois que vous avez entré la **** clé de récupération BitLocker, allez sur Mot de passe options de la signature (représenté par l’icône de clé  >  **** sur le côté gauche).  
5.  Entrez le mot de passe et connectez-vous en attendant la fin de l’authentification à deux facteurs (le cas échéant).
6.  Une fois que vous êtes entièrement connectez-vous, allez sur **Démarrer**  >  **la**  >  **signature du compte.**  
7.  Connectez-vous à l’aide du mot de passe, puis définissez Windows Hello et ajoutez un code confidentiel. 
8.  Si l’appareil a été désactivé par BitLocker pour faciliter la suppression et le remplacement de SSD, et si vous souhaitez activer BitLocker après le remplacement, allez à **Paramètres**  >  **BitLocker**  >  **Gérer BitLocker**  >  **Resume BitLocker BitLocker**.  
9.  Exécutez **[SDT pour](surface-diagnostic-toolkit-for-business-intro.md)** vérifier les fonctionnalités complètes de l’appareil.  
10. Pour vérifier l’activation de Windows, sélectionnez **Activation des**  >  **paramètres.**  Si vous voyez des messages d’erreur, sélectionnez **Résoudre les problèmes.**
11. Pour vérifier l’état du compte Office, ouvrez **** l’application **Office,** puis rendez-vous sur Compte de fichier pour vérifier les  >  **** messages d’erreur.

## En savoir plus

- [Guide de suppression rSSD pour entreprise](https://www.microsoft.com/download/100440)
- [Guide de récupération BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)

Encore besoin d’aide? Go to [Microsoft Community](https://answers.microsoft.com/).