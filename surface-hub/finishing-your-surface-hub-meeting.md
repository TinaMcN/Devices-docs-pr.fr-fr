---
title: 'Terminer la session: mettre fin à une réunion Surface Hub'
description: Pour mettre fin à une réunion Surface Hub, appuyez sur Terminer la session. Le Surface Hub nettoie l’état de l’application, l’état du système d’exploitation et l’interface utilisateur afin d’être prêt pour la prochaine réunion.
keywords: J’ai terminé, terminer une réunion Surface Hub, fin d’une réunion Surface Hub, nettoyer une réunion Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: b18bc4b15b8a3925aeecdd9999b09b61011d1db5
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10833695"
---
# Mettre fin à une réunion Surface Hub avec Terminer la session
Le SurfaceHub est un appareil de collaboration conçu pour être utilisé dans des espaces de réunion par différents groupes d’utilisateurs. À l’issue d’une réunion, les utilisateurs peuvent appuyer sur **Terminer la session** pour nettoyer les données sensibles et préparer l’appareil pour la prochaine réunion. Le SurfaceHub nettoie ou réinitialise les états suivants:
- Applications
- Système d’exploitation
- Interface utilisateur

Cette rubrique explique ce que **Terminer la session** réinitialise pour chacun de ces états.

## Applications
Quand vous démarrez des applications sur le Surface Hub, elles sont stockées en mémoire tandis que les données sont stockées au niveau de l’application. Les données sont accessibles à tous les utilisateurs au cours de cette session (ou de la réunion) jusqu’à ce que la date soit supprimée ou remplacée. Quand **Terminer la session** est sélectionné, l’état des applications du Surface Hub est effacé en fermant les applications, en supprimant l’historique du navigateur, en réinitialisant les applications et en supprimant les journaux Skype.

### Fermer les applications
Le Surface Hub ferme toutes les fenêtres visibles, notamment les applications Win32 et les applications de plateforme Windows universelle. L’étape de fermeture des applications utilise la vue multitâche pour interroger les fenêtres visibles. Les fenêtres Win32 qui ne sont pas fermées dans un certain laps de temps le sont à l’aide de **TerminateProcess**. 
   
### Supprimer l’historique de navigateur
Le Surface Hub utilise Supprimer l’historique du navigateur dans Edge pour effacer l’historique Edge et les données mises en cache. Ce processus est semblable à la façon dont un utilisateur peut effacer l’historique de son navigateur manuellement, mais **Terminer la session** permet également de s’assurer que les états d’application sont effacés et que les données sont supprimées avant la prochaine session ou la prochaine réunion. 
 
### Réinitialiser les applications
**Terminer la session** réinitialise l’état de chaque application installée sur le Surface Hub. La réinitialisation d’une application permet d’effacer toutes les tâches en arrière-plan, les données d’application, les notifications et les boîtes de dialogue de consentement de l’utilisateur. L’état de première utilisation des applications est rétabli pour les utilisateurs suivants du Surface Hub.  
 
### Supprimer les journaux Skype
Skype ne stocke pas les informations d’identification personnelle sur le Surface Hub. Ces informations sont stockées dans le service Skype pour répondre aux conseils de SkypeEntreprise. Les informations de journalisation de Skype locales sont les seules données supprimées lorsque **Terminer la session** est sélectionné. Cela inclut les journauxUCCP (Unified Communications Client Platform) et les journaux multimédias.   

## Systèmed’exploitation
Le système d’exploitation héberge une variété d’informations sur l’état des sessions qui doivent être effacées après chaque réunion Surface Hub. 

### Système de fichiers
Les participants aux réunions ont accès à un ensemble limité de répertoires sur le Surface Hub. Quand **Terminer la session** est sélectionné, le Surface Hub efface ces répertoires:<br>
- Musique
- Vidéos
- Documents
- Images
- Téléchargements

Le Surface Hub efface également les répertoires ci-dessous, étant donné que de nombreuses applications écrivent souvent dans ceux-ci:
- Bureau
- Favoris
- Récents
- Documents publics
- Musique publique
- Vidéos publiques
- Téléchargements publics

### Informations d’identification
Les informations d’identification de l’utilisateur qui sont stockées dans **TokenBroker**, **PasswordVault** ou dans le **Gestionnaire d’informations d’identification** sont effacées lorsque vous appuyez sur **Terminer la session**.

## Interface utilisateur
Les valeurs par défaut des paramètres de l’interface utilisateur sont rétablies lorsque **Terminer la session** est sélectionné. 

### Éléments de l’interface utilisateur
- Rétablir l’état par défaut des actions rapides
- Effacer les notifications toast
- Réinitialiser les niveaux de volume
- Réinitialiser la largeur de barre latérale
- Rétablir la disposition en mode tablette
- Déconnecter l’utilisateur des réunions et fichiers Office365

### Accessibilité
Les paramètres par défaut des fonctionnalités et des applications d’accessibilité sont rétablis lorsque **Terminer la session** est sélectionné.
- Touches filtres
- Contraste élevé
- Touches rémanentes
- Touches bascules
- Touches de souris
- Loupe
- Narrateur

### Presse-papiers
Le Presse-papiers est vidé pour supprimer les données qui y ont été copiées durant la session. 

## Forum aux questions
**Que se passe-t-il si j’oublie d’appuyer sur Terminer la session à la fin d’une réunion, et que le SurfaceHub est utilisé par quelqu’un d’autre ultérieurement?**<br>
Le SurfaceHub nettoie uniquement le contenu de la réunion lorsque les utilisateurs appuient sur **Terminer la session**. Si vous quittez la réunion sans appuyer sur **Terminer la session**, l’appareil affiche de nouveau l’écran d’accueil après un certain temps. Dans l’écran d’accueil, les utilisateurs ont la possibilité de reprendre la session précédente ou d’en démarrer une nouvelle. Vous pouvez également désactiver la possibilité de reprendre une session si **Terminer la session** n’est pas sélectionné.

**Les documents sont-ils récupérables?**<br> La suppression des fichiers sur le disque dur lorsque le bouton **Terminer la session** est sélectionné équivaut simplement à toute autre suppression de fichier sur un disque dur. Des logiciels tiers sont peut-être en mesure de récupérer les données du disque dur, mais la récupération des fichiers n’est pas une fonctionnalité prise en charge sur le SurfaceHub. Pour empêcher toute perte de données, veillez à toujours enregistrer celles dont vous avez besoin avant de quitter une réunion.

**Les actions de nettoyage effectuées à partir du bouton Terminer la session sont-elles conformes à la norme de nettoyage et de vidage du département américain de la Défense: DoD5220.22-M?**<br>
Non. Actuellement, les actions de nettoyage effectuées à partir de **Terminer la session** ne sont pas conformes à cette norme.  
  
