---
title: Utilisation de l’outil de récupération de SurfaceHub
description: Découvrez comment utiliser l’outil de récupération de surface Hub pour réutiliser le SSD.
ms.assetid: FDB6182C-1211-4A92-A930-6C106BCD5DC1
ms.reviewer: ''
manager: laurawi
keywords: gérer le Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 05/22/2018
ms.localizationpriority: medium
ms.openlocfilehash: 1988a6ed59525d7dc77872e532247dbc50f01bdf
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10834169"
---
# Utilisation de l’outil de récupération de SurfaceHub

L' [outil de récupération Microsoft surface Hub](https://www.microsoft.com/download/details.aspx?id=52210) permet de réutiliser votre périphérique de bureau de surface Hub à l’aide d’un appareil de bureau Windows 10, sans appeler le support technique ou en remplaçant le disque SSD. Grâce à cet outil, vous pouvez Redisposer une image de type SSD dont le mot de passe est inconnu, qu’il n’est pas possible de terminer une récupération du Cloud ou d’un appareil doté d’une version antérieure du système d’exploitation. L’outil ne résoudra pas les SSDs physiques endommagés.

Pour réutiliser le disque SSD surface Hub à l’aide de l’outil de récupération, vous devez supprimer le disque SSD de surface Hub, connecter le lecteur au câble USB-à-SATA, puis raccorder le câble au PC de bureau sur lequel est installé l’outil de récupération. Pour plus d’informations sur la façon de supprimer le lecteur existant de votre surface Hub, voir [remplacement de SSD de surface Hub](surface-hub-ssd-replacement.md).

> [!IMPORTANT]
> Ne laissez pas le périphérique dormir en veille ou interrompez le téléchargement du fichier image.

Si l’outil ne parvenez pas à réimagingr votre lecteur, contactez le [support surface Hub](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support).

## Conditions préalables

### Mandatory

- ORDINATEUR hôte exécutant une version 64 bits, version 1607 ou ultérieure.
- Accès Internet
- Ouvrez USB 2,0 ou une version ultérieure.
- Câble USB vers SATA
- 10 Go d’espace disque disponible sur l’ordinateur hôte
- SSDs fourni avec surface Hub ou un SSD fourni par le support technique en tant que remplacement. SSDs non fourni par Microsoft n’est pas pris en charge.

### Nos recommandations

- Connexion Internet haut débit
- Ouvrir le port USB 3,0
- Câble USB 3,0 ou une version ultérieure USB-SATA
- L’outil d’imagerie a été testé avec la marque et le modèle de câble suivants:
    - Startech USB312SAT3CB
    - Rosewill RCUC16001
    - Ugreen 20231

## Télécharger l’outil de récupération de surface Hub

L’outil de récupération de surface Hub est disponible en téléchargement à partir des [Outils surface Hub pour ce dernier](https://www.microsoft.com/download/details.aspx?id=52210) sous le nom de fichier **SurfaceHub_Recovery_v1.14.137.0.msi**.

Pour démarrer le téléchargement, cliquez sur **Télécharger**, choisissez **SurfaceHub_Recovery_v1.14.137.0.msi** dans la liste, puis cliquez sur **suivant**. Dans la fenêtre qui s’affiche, choisissez l’une des options suivantes:

- Cliquez sur **exécuter** pour démarrer l’installation immédiatement.
- Cliquez sur **Enregistrer** pour copier le téléchargement sur votre ordinateur pour une installation ultérieure.

Installez l’outil de récupération de surface Hub sur l’ordinateur hôte.

## Exécuter l’outil de récupération de surface Hub

1. Sur l’ordinateur hôte, sélectionnez le bouton **Démarrer** , faites défiler la liste alphabétique sur la gauche, puis sélectionnez le raccourci de l’outil de récupération.

    ![Raccourci de l’outil de récupération Microsoft surface Hub](images/shrt-shortcut.png)

2. Cliquez sur **Démarrer**.

    ![Bouton Démarrer de l’outil de récupération](images/shrt-start.png)

3. Dans la fenêtre d' **aide** , cliquez sur **suivant**.

    ![Ne laissez pas votre ordinateur accéder aux conseils de mise en veille](images/shrt-guidance.png)

4. Cliquez sur **Oui** pour télécharger l’image. Le temps de téléchargement de l’image de récupération dépend des vitesses de connexion Internet. Sur une connexion d’entreprise moyenne, il peut s’écouler jusqu’à une heure pour télécharger le fichier image de 8 Go.

    ![Télécharger l’image?](images/shrt-download.png)

5. Lorsque le téléchargement est terminé, l’outil vous demande de connecter un disque SSD. Si l’outil ne parvient pas à trouver le lecteur en pièce jointe, il est possible que le câble utilisé ne signale pas le nom de l’objet SSD dans Windows.  L’outil d’imagerie doit trouver le nom du lecteur comme «LITEON L-128V2S USB» pour pouvoir continuer.  Pour plus d’informations sur la façon de supprimer le lecteur existant de votre surface Hub, voir [remplacement de SSD de surface Hub](surface-hub-ssd-replacement.md).

    ![Connexion SSD](images/shrt-drive.png)

6. Lorsque le lecteur est reconnu, cliquez sur **Démarrer** pour démarrer le processus de nouvelle image. Sur le message d’avertissement indiquant que toutes les données du lecteur seront effacées, cliquez sur **OK**.

    ![Commencer à recréer une image de la vidéo SSD](images/shrt-drive-start.png)

    Avant d’appliquer l’image système au lecteur, le disque SSD est repartitionné et mis en forme. La copie des fichiers binaires du système prend environ 30 minutes, mais peut prendre plus de temps en fonction de la vitesse de votre bus USB, du câble utilisé ou du logiciel antivirus installé sur votre système.

    ![Copie réalisée](images/shrt-done.png)

    ![Recréation d’image terminée](images/shrt-complete.png)

## Résolution des problèmes et problèmes courants

Problème | Remarques
--- | ---
L’outil ne parvient pas à imager le SSD | Vérifiez que vous utilisez un SSD fourni par un fabricant et un des câbles testés.
Le processus de recréation d’image apparaît arrêté ou figé | Il est possible de fermer et de redémarrer l’outil de récupération de surface Hub sans effet pour le SSD.
Le lecteur n’est pas reconnu par l’outil | Vérifiez que l’interface SSD surface Hub est énumérée comme un lecteur Lite-on, «LITEON L-128V2S USB».  Si le lecteur est reconnu comme un autre périphérique appelé, votre câble actuel n’est pas compatible. Essayez un autre câble ou un câble testé indiqué ci-dessus.
Erreur:-2147024809 | Ouvrez le gestionnaire de disques et supprimez les partitions sur le lecteur surface Hub.  Déconnectez-vous et reconnectez-vous à l’ordinateur hôte. Redémarrez de nouveau l’outil d’imagerie.

Si l’outil ne parvenez pas à réimagingr votre lecteur, contactez le [support surface Hub](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support).
