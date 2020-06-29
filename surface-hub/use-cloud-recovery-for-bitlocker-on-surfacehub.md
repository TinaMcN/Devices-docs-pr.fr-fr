---
title: Comment utiliser la récupération Cloud pour BitLocker sur un appareil SurfaceHub
description: Comment utiliser la récupération Cloud pour BitLocker sur un appareil SurfaceHub
ms.assetid: c0bde23a-49de-40f3-a675-701e3576d44d
keywords: Paramètres d’accessibilité, application Paramètres, Options d’ergonomie
ms.prod: surface-hub
ms.sitesec: library
author: v-miegge
ms.author: v-miegge
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: 7912f9d1bab2ba625995c56d6d7da4e6b2d3df37
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832670"
---
# Résumé

Cet article décrit comment utiliser la fonction de récupération Cloud si vous êtes invité de façon inattendue par BitLocker sur un appareil surface Hub.

> [!NOTE]
> Suivez ces étapes uniquement si aucune clé de récupération BitLocker n’est disponible.

> [!WARNING]
> * Ce processus de récupération supprime le contenu du disque interne. En cas d’échec du processus, le disque interne devient entièrement inutilisable. Si tel est le cas, vous devrez consigner une demande de service auprès de Microsoft.
> * Une fois le processus de récupération terminé, l’appareil est réinitialisé aux paramètres d’usine et est retourné à son état d’arrêt hors champ.
> * Après la récupération, surface hub doit être complètement reconfiguré.

> [!IMPORTANT]
> Ce processus nécessite une connexion Internet ouverte qui n’utilise pas de proxy ou d’autre méthode d’authentification.

## Processus de récupération Cloud

Pour effectuer une récupération du Cloud, procédez comme suit:

1. **Pour plus d’options de récupération, sélectionnez appuyer sur ÉCHAP**.

   ![Capture d’écran de l’échappement](images/01-escape.png)

1. Sélectionnez **ignorer ce lecteur**.

   ![Capture d’écran de la commande ignorer ce lecteur](images/02-skip-this-drive.png)

1. Sélectionnez **récupérer dans le Cloud**.

   ![Capture d’écran de la restauration à partir du Cloud](images/03-recover-from-cloud.png)

1. Sélectionnez **Oui**.

   ![Capture d’écran de Oui](images/04-yes.png)

1. Sélectionnez **réinstaller**.

   ![Capture d’écran de la réinstallation](images/05a-reinstall.png)

   ![Capture d’écran du téléchargement](images/05b-downloading.png)

1. Une fois le processus de récupération du Cloud terminé, démarrez la reconfiguration en utilisant le mode **hors connexion**.

   ![Capture d’écran de la zone prêts à l’emploi](images/06-out-of-box.png)

## Message d’erreur «un problème est survenu»

Cette erreur est généralement provoquée par des problèmes de réseau qui se produisent pendant le téléchargement de récupération. Lorsque ce problème survient, ne désactivez pas le concentrateur, car vous ne pourrez pas le redémarrer. Si vous recevez ce message d’erreur, revenez à l’étape «récupérer à partir du Cloud», puis redémarrez le processus de récupération.

1. Sélectionnez **Annuler**.

   ![Capture d’écran de l’annulation](images/07-cancel.png)

1. Sélectionnez **résolution des problèmes**.

   ![Capture d’écran de la résolution des problèmes](images/08-troubleshoot.png)

1. Sélectionnez **récupérer dans le Cloud**.

   ![Capture d’écran de la restauration à partir du Cloud](images/09-recover-from-cloud2.png)

1. Si l’erreur « **réseau filaire introuvable** » s’affiche, sélectionnez **Annuler**, puis laissez surface Hub découvrir le réseau filaire.

   ![Capture d’écran du réseau filaire introuvable](images/10-cancel.png)