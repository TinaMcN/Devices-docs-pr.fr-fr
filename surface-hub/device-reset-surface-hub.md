---
title: Réinitialiser ou récupérer un surface Hub
description: Décrit les processus de réinitialisation et de récupération pour surface Hub, et fournit des instructions.
ms.assetid: 44E82EEE-1905-464B-A758-C2A1463909FF
ms.reviewer: ''
manager: laurawi
keywords: réinitialisation de surface Hub, récupération
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/31/2019
ms.localizationpriority: medium
ms.openlocfilehash: c5cf643d0f4a68344bb098916a909dd66e1dac9b
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10833731"
---
# Réinitialiser ou récupérer un surface Hub

Cet article décrit comment réinitialiser ou récupérer un Microsoft surface Hub.  

[La réinitialisation de surface Hub](#reset-a-surface-hub) renvoie son système d’exploitation vers la dernière mise à jour de Windows, ainsi que des informations de configuration et des fichiers utilisateur locaux. Les informations supprimées incluent les éléments suivants:

- Le compte d’appareil
- Informations de compte pour les administrateurs locaux de l’appareil
- Informations de jointure ou de domaine Azure AD
- Informations d’inscription de la gestion des périphériques mobiles (GPM)
- Informations de configuration définies à l’aide de la gestion des périphériques mobiles ou de l’application paramètres

[La récupération d’un surface Hub à partir du Cloud](#recover-a-surface-hub-from-the-cloud) entraîne également celle de ces informations. Par ailleurs, surface Hub télécharge une nouvelle image de système d’exploitation et l’installe. Vous pouvez spécifier si le processus de récupération conserve d’autres informations stockées sur l’appareil surface Hub.

## Réinitialiser un surface Hub

Il est possible que vous deviez réinitialiser votre concentrateur surface pour les raisons suivantes:

- Vous réactivez l’appareil pour un nouvel espace de réunion et voulez le reconfigurer.
- Vous souhaitez modifier la façon dont vous gérez localement l’appareil.
- Le nom d’utilisateur ou le mot de passe du compte de l’appareil ou du compte d’administrateur a été perdu.
- Après l’installation d’une mise à jour, les performances de l’appareil sont réduites.

Pendant le processus de réinitialisation, si vous voyez un écran vide sur de longues périodes, veuillez patienter et ne pas effectuer d’action.

> [!WARNING]
> Le processus de réinitialisation de l’appareil risque de durer jusqu’à 6 heures. Ne désactivez pas ou ne débranchez pas le concentrateur de surface tant que le processus n’est pas terminé. Si vous interrompez le processus, l’appareil devient inopérant. Le service de garantie doit être utilisé pour que l’appareil soit opérationnel de nouveau.

1. Sur votre Surface Hub, ouvrez **Paramètres**.

   ![Image montrant l’application paramètres pour surface Hub.](images/sh-settings.png)

1. Sélectionnez **mettre à jour & sécurité**.

   ![Image illustrant le groupe de sécurité mise à jour & dans l’application paramètres pour surface Hub.](images/sh-settings-update-security.png)

1. Sélectionnez **récupération**, puis, sous **Réinitialiser l’appareil**, sélectionnez mise en **route**.

   ![Image illustrant l’option de réinitialisation de l’appareil dans l’application paramètres pour surface Hub.](images/sh-settings-reset-device.png)

   À la fin du processus de réinitialisation, le concentrateur de surface démarre de nouveau le [programme de premier exécution](first-run-program-surface-hub.md) . Si le processus de réinitialisation rencontre un problème, il restaure le centre de surface sur l’image du système d’exploitation déjà existant, puis affiche l’écran d’accueil.

<span id="cloud-recovery" />

## Récupérer un Surface Hub à partir du cloud

Si, pour une raison quelconque, le concentrateur de surface devient inutilisable, vous pouvez toujours le récupérer à partir du Cloud sans assistance de la part du support Microsoft. Surface Hub peut télécharger une nouvelle image de système d’exploitation à partir du Cloud et utiliser cette image pour réinstaller son système d’exploitation.

Il est possible que vous deviez utiliser ce type de processus de récupération dans les cas suivants:

- [Surface Hub ou ses comptes liés ont entré un état instable](#recover-a-surface-hub-in-a-bad-state)
- [Surface Hub est verrouillé](#recover-a-locked-surface-hub)

>[!IMPORTANT]
>La **récupération à partir du processus Cloud** nécessite une connexion Internet ouverte (aucune doublure ou autre authentification). Il est recommandé d’avoir une connexion Ethernet.

### Récupérer un Surface Hub se trouvant dans un état incorrect

Si le compte d’appareil est dans un état instable ou si le compte d’administrateur rencontre des problèmes, vous pouvez utiliser l’application paramètres pour démarrer le processus de récupération Cloud. Vous devez uniquement utiliser le processus de récupération Cloud lorsque le processus de [réinitialisation](#reset-a-surface-hub) de l’appareil ne résout pas le problème.

1. Sur votre surface Hub, sélectionnez **Settings** &gt; **mise à jour** des paramètres & récupération de la sécurité &gt; **Recovery**.

1. Sous **récupérer dans le Cloud**, sélectionnez **redémarrer maintenant**.

   ![récupérer à partir du cloud](images/recover-from-the-cloud.png)

### Récupérer un Surface Hub verrouillé

À de rares occasions, un SurfaceHub peut rencontrer une erreur lors du nettoyage des données utilisateur et d’application à la fin d’une session. Lorsque c’est le cas, l’appareil redémarre automatiquement et tente de nouveau l’opération. Néanmoins, si cette opération échoue de manière répétée, l’appareil se verrouille automatiquement pour protéger les données des utilisateurs. Pour le déverrouiller, vous devez [Réinitialiser l’appareil](#reset-a-surface-hub) ou, si cela ne fonctionne pas, le récupérer à partir du Cloud.

1. Recherchez le bouton marche/arrêt dans la partie inférieure de surface Hub. Le bouton marche/arrêt se trouve à côté de l’option connexion du cordon d’alimentation. Pour plus d’informations sur le basculement, voir le [Guide de compatibilité du site surface Hub (PDF)](surface-hub-site-readiness-guide.md).

1. Lorsque l’écran d’accueil de surface Hub est affiché, utilisez le commutateur de puissance pour éteindre le surface Hub.

1. Utilisez le commutateur Power Pivot pour réactiver le centre de surface. Le périphérique démarre et affiche l’écran du logo surface Hub. Lorsque vous voyez des points de rotation sous le logo surface Hub, utilisez le commutateur d’alimentation pour réactiver le centre de surface.  

1. Répétez l’étape 3 3 ou jusqu’à ce que surface Hub affiche le message «préparation automatique». Après avoir affiché ce message, l’application surface Hub affiche l’écran Windows RE.

1. Sélectionnez **Options avancées**.

1. Sélectionnez **récupérer dans le Cloud**. (Vous pouvez également sélectionner **Réinitialiser**. Néanmoins, la **récupération à partir du Cloud** est l’approche recommandée.)

   ![Récupérer à partir du cloud](images/recover-from-cloud.png)
1. Si vous êtes invité à entrer la clé BitLocker, effectuez l’une des opérations suivantes:

   - Pour conserver les informations que BitLocker protège sur surface Hub, entrez la clé BitLocker.
   - Pour ignorer les informations protégées, sélectionnez **ignorer ce lecteur** .  

1. Lorsque vous y êtes invité, sélectionnez **réinstaller**.

    ![Réinstaller](images/reinstall.png)

1. Pour repartitionner le disque, sélectionnez **Oui**.

   ![Repartitionner](images/repartition.png)

   Tout d’abord, le processus de récupération télécharge l’image du système d’exploitation à partir du Cloud.  

   ![téléchargement 97%](images/recover-progress.png)

   Lorsque le téléchargement est terminé, le processus de récupération restaure le centre de surface conformément aux options que vous avez sélectionnées.
   

## Contacter le support

Si vous avez des questions ou si vous avez besoin d’aide, vous pouvez [créer une demande de support](https://support.microsoft.com/supportforbusiness/productselection).


## Rubriques connexes

[Gérer le Microsoft SurfaceHub](manage-surface-hub.md)

[Guide de l’administrateur Microsoft Surface Hub](surface-hub-administrators-guide.md)
