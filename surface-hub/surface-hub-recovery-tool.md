---
title: Utilisation de l’outil de récupération de SurfaceHub
description: Utilisation de l’outil de récupération Surface Hub pour ré-imager le SSD.
ms.assetid: FDB6182C-1211-4A92-A930-6C106BCD5DC1
ms.reviewer: ''
manager: laurawi
keywords: gérer le Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 02/11/2020
ms.localizationpriority: medium
ms.openlocfilehash: 0cc444eab51e9c3cc0bf2f9c2f0c36ac491906b1
ms.sourcegitcommit: 7b09b4bc757c5385c4f5560713cb03448afde9ea
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/16/2021
ms.locfileid: "11339365"
---
# Utilisation de l’outil de récupération de SurfaceHub

L’outil de récupération [Microsoft Surface Hub](https://www.microsoft.com/download/details.aspx?id=52210) vous permet de ré-imager votre SSD (Solid State Drive) Surface Hub à l’aide d’un appareil de bureau Windows 10, sans appeler la prise en charge ni remplacer le SSD. Avec cet outil, vous pouvez réimager un SSD qui a un mot de passe administrateur inconnu, des erreurs de démarrage, n’a pas pu effectuer une récupération cloud ou pour un appareil qui dispose d’une version antérieure du système d’exploitation. L’outil ne corrige pas les SSD physiquement endommagés.

Pour ré-imager le SSD Surface Hub à l’aide de l’outil de récupération, vous devez supprimer le SSD du Surface Hub, connecter le lecteur au câble USB à SATA, puis connecter le câble au PC de bureau sur lequel l’outil de récupération est installé. Pour plus d’informations sur la suppression du lecteur existant de votre Surface Hub, voir remplacement du [SSD Surface Hub.](surface-hub-ssd-replacement.md)

> [!IMPORTANT]
> Ne laissez pas l’appareil se mettre en veille ou interrompre le téléchargement du fichier image.

Si l’outil n’a pas réussi à réinventer votre lecteur, contactez le support [Surface Hub.](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support)

## Prérequis

### Mandatory

- PC hôte exécutant la version 64 bits de Windows 10, version 1607 ou supérieure.
- Accès Internet
- Ouvrir le port USB 2.0 ou supérieur
- Câble USB-SATA
- 10 Go d’espace disque libre sur l’ordinateur hôte
- SSD livrés avec Surface Hub ou un SSD fourni par le support en remplacement. Les SSD non fournis par Microsoft ne sont pas pris en charge.

### Nos recommandations

- Connexion Internet haut débit
- Ouvrir le port USB 3.0
- Câble USB 3.0 ou un câble USB-SATA supérieur
- L’outil d’imagerie a été testé avec la création et le modèle de câbles suivants :
    - Startech USB312SAT3CB
    - Rosewill RCUC16001
    - Ugreen 20231

## Télécharger l’outil de récupération Surface Hub

L’outil de récupération Surface Hub est disponible en téléchargement à partir des outils [Surface Hub](https://www.microsoft.com/download/details.aspx?id=52210)  pour les services informatiques sous le nom de ** fichierSurfaceHub_Recovery_v2.7.139.0.msi**.

> [!IMPORTANT]
> Cette version, publiée le 11 février 2021, remplace la version antérieure, qui n’est plus fonctionnelle. Si vous avez téléchargé cet outil précédemment, désinstallez-le et installez la version actuelle.

Pour démarrer le téléchargement, cliquez sur **Télécharger,** choisissez **SurfaceHub_Recovery_v2.7.139.0.msi**  dans la liste, puis cliquez sur **Suivant**. Dans la fenêtre pop-up, choisissez l’une des touches suivantes :

- Cliquez **sur Exécuter** pour démarrer l’installation immédiatement.
- Cliquez **sur Enregistrer** pour copier le téléchargement sur votre ordinateur pour une installation ultérieure.

Installez l’outil de récupération Surface Hub sur le PC hôte.

## Exécuter l’outil de récupération Surface Hub

1. Sur le PC hôte, sélectionnez le bouton Démarrer, faites défiler la liste alphabétique à gauche, puis sélectionnez le raccourci de l’outil de récupération. ****

    ![Raccourci de l’outil de récupération Microsoft Surface Hub](images/shrt-shortcut.png)

2. Cliquez sur **Démarrer**.

    ![Bouton Démarrer de l’outil de récupération](images/shrt-start.png)


3. Dans la **fenêtre Recommandations,** cliquez sur **Suivant.**

    ![Ne laissez pas votre ordinateur passer à l’aide de la veille](images/shrt-guidance.png)

4. Dans la fenêtre Sélectionner une image, cliquez sur **RS2** ou son successeur **20H2,** sélectionnez **Continuer,** puis sélectionnez **Télécharger l’image.**

     ![Image de téléchargement de l’outil de récupération ](images/shrt-select-image.png) ![ d’image Sélectionner l’outil de récupération d’image](images/shrt-download-image.png)

5. Le temps de téléchargement de l’image de récupération dépend des vitesses de connexion Internet. En moyenne, une connexion d’entreprise peut prendre jusqu’à une heure pour télécharger le fichier image de 8 Go.

    ![Téléchargement d’une image](images/shrt-download.png)



5. Une fois le téléchargement terminé, l’outil vous demande de connecter un lecteur SSD. Si l’outil ne parvient pas à localiser le lecteur attaché, il est possible que le câble utilisé ne rapporte pas le nom du SSD à Windows.  L’outil d’imagerie doit trouver le nom du lecteur comme « Périphérique USB LITEON L CH-128V2S » avant de pouvoir continuer.  Pour plus d’informations sur la suppression du lecteur existant de votre Surface Hub, voir remplacement du [SSD Surface Hub.](surface-hub-ssd-replacement.md)

    ![Connect SSD](images/shrt-drive.png)

6. Lorsque le lecteur est reconnu, cliquez sur **Démarrer** pour commencer le processus de ré-imagerie. Dans l’avertissement signalant que toutes les données du lecteur seront effacées, cliquez sur **OK**.



    Avant d’appliquer l’image système au lecteur, le SSD est repartitioné et formaté. La copie des binaires système prend environ 30 minutes, mais peut prendre plus de temps en fonction de la vitesse de votre bus USB, du câble utilisé ou du logiciel antivirus installé sur votre système.



## Résolution des problèmes et problèmes courants

Problème | Remarques
--- | ---
L’outil ne parvient pas à imager le SSD | Assurez-vous que vous utilisez un SSD fourni en usine et l’un des câbles testés.
Le processus de réinventation semble interrompu/figé | Il est sûr de fermer et de redémarrer l’outil de récupération Surface Hub sans que le SSD n’en soit souffrant.
Le lecteur n’est pas reconnu par l’outil | Vérifiez que le SSD Surface Hub est indiqué en tant que lecteur Lite-On, « Périphérique USB LITEON L CH-128V2S ».  Si le lecteur est reconnu comme un autre périphérique nommé, votre câble actuel n’est pas compatible. Essayez un autre câble ou l’un des câbles testés répertoriés ci-dessus.
Erreur : -2147024809 | Ouvrez le Gestionnaire de disques et supprimez les partitions sur le lecteur Surface Hub.  Déconnectez et reconnectez le lecteur à l’ordinateur hôte. Redémarrez l’outil d’imagerie.

Si l’outil n’a pas réussi à réinventer votre lecteur, contactez le support [Surface Hub.](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support)

## Historique des versions


### Version v2.7.139.0

*Date de publication : 11 février 2021*<br>
Cette version de l’outil de récupération Surface Hub ajoute la prise en charge des opérations suivantes :

- Mise à jour de sécurité


### Version v2.0.139.0

> [!IMPORTANT]
> Cette version n’est plus fonctionnelle. Veuillez télécharger la version actuelle, répertoriée ci-dessus. 

*Date de publication : 18 décembre 2020*<br>
Cette version de l’outil de récupération Surface Hub ajoute la prise en charge des opérations suivantes :
- Mise à jour pour prendre en charge windows 10 Team 2020 Update (20H2)
- Améliorations de l’expérience utilisateur
- Modifications architecturales
- Ajouts de télémétrie

