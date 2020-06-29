---
title: Réinitialiser et récupérer des surface Hub 2
description: Découvrez comment récupérer et réinitialiser surface Hub 2S.
keywords: séparer les valeurs par des virgules
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 12/05/2019
ms.localizationpriority: Medium
ms.openlocfilehash: fb7e1a39d96c2da6d27d5558ebefcff52bd6e159
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10833005"
---
# Réinitialiser et récupérer des surface Hub 2

Si vous rencontrez des problèmes avec l’interface de surface Hub 2, vous pouvez rétablir les paramètres d’usine de l’appareil ou le restaurer à l’aide d’un lecteur USB.

Pour commencer, connectez-vous à surface Hub 2 avec les informations d’identification d’administrateur, ouvrez l’application **paramètres** , sélectionnez **mettre à jour & sécurité**, puis sélectionnez **récupération**.

## Réinitialiser l’appareil

1. Pour réinitialiser l’appareil, sélectionnez **commencer**.
2. Lorsque la fenêtre **prêt pour la réinitialisation de l’appareil** s’affiche, sélectionnez **Réinitialiser**. 
  
  >[!NOTE]
  >Surface Hub 2 réinstalle le système d’exploitation à partir de la partition de récupération. L’opération risque de prendre jusqu’à une heure.
  
3. Pour reconfigurer l’appareil, exécutez le programme de configuration pour la première fois.
4. Si vous gérez l’appareil à l’aide de Microsoft Intune ou d’une autre solution de gestion des appareils mobiles, retirez et supprimez l’enregistrement précédent, puis réinscrivez le nouvel appareil. Pour plus d’informations, reportez-vous [à la section supprimer des appareils à l’aide de l’effet de réinitialisation](https://docs.microsoft.com/intune/devices-wipe)

![* Reset et Recovery for surface Hub 2 *](images/sh2-reset.png)<br>
*Figure1. Réinitialiser et récupérer des surface Hub 2* 

## Récupérer des surface Hub 2 à l’aide d’un lecteur de récupération USB

Nouveauté de surface Hub 2, vous pouvez maintenant réinstaller l’appareil à l’aide d’une image de récupération.

### Restauration à partir d’un lecteur USB

À l’aide de surface Hub 2, vous pouvez réinstaller l’appareil à l’aide d’une image de récupération. En procédant ainsi, vous pouvez réinstaller l’appareil sur les paramètres d’usine si vous avez perdu la clé BitLocker ou si vous n’avez plus d’informations d’identification d’administrateur dans l’application paramètres.

>[!NOTE]
>Utilisez un lecteur USB 3,0 avec 8 Go ou 16 Go d’espace de stockage, formaté en FAT32.

1. À partir d’un autre PC, téléchargez l’image de récupération de fichier. zip à partir du [site Web de récupération de surface](https://support.microsoft.com/surfacerecoveryimage?devicetype=surfacehub2s) , puis revenez à ces instructions. 
1. Décompressez le fichier téléchargé sur la racine du lecteur USB.  
1. Connectez le lecteur USB à tout port USB-C ou USB-Port sur surface Hub 2.
1. Éteindre le périphérique:
   1. Tout en maintenant la touche enfoncée, appuyez sur le bouton d’alimentation.
   1. Maintenez les deux boutons appuyés jusqu’à ce que vous voyiez le logo Windows.
   1. Relâchez le bouton d’alimentation tout en continuant de maintenir le volume jusqu’à ce que l’interface utilisateur de l’installation démarre.

    ![* Utiliser le volume et les boutons d’alimentation pour démarrer la restauration *](images/sh2-keypad.png) <br>
   **Figure2. Boutons volume et alimentation**

1. Dans l’écran de sélection de la langue, sélectionnez la langue d’affichage de votre surface Hub 2.
1. Sélectionnez **récupérer à partir d’un disque** , **Nettoyez entièrement le lecteur**, puis sélectionnez **récupérer**. Si vous êtes invité à entrer une clé BitLocker, sélectionnez **ignorer ce lecteur**. Surface Hub 2 réamorce plusieurs fois et nécessite environ 30 minutes pour terminer le processus de récupération.

Lorsque l’écran de configuration pour la première fois apparaît, supprimez le lecteur USB.

## Contacter le support

Si vous avez des questions ou si vous avez besoin d’aide, vous pouvez [créer une demande de support](https://support.microsoft.com/supportforbusiness/productselection).
