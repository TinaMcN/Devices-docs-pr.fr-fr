---
title: Listes de vérification de déploiement de surface Hub 2
description: Vérifiez votre déploiement de surface Hub 2 à l’aide de listes de vérification avant et après le déploiement.
keywords: séparer les valeurs par des virgules
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 06/20/2019
ms.localizationpriority: Medium
ms.openlocfilehash: 3c30892a3ae4f534006aa32ad6d969b42a52cbf2
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10833792"
---
# Listes de vérification de déploiement de surface Hub 2

## Liste de contrôle de pré-déploiement surface Hub 2

|**Élément**|**Réponse**|
|:------ |:------ |
|**Nom du compte de l’appareil**| |
|**Nom d’utilisateur principal du compte d’appareil**| |
|**Stratégie ActiveSync**| |
|**Configuration du traitement du calendrier terminée**| ☐ Oui <br>  ☐ Non |
|**Nom convivial de l’appareil**| |
|**Nom d’hôte de l’appareil**| |
|**Affilié**| ☐ Aucun <br> ☐ D’affiliation Active Directory <br> ☐ Azure Active Directory |
|**Mode Microsoft teams**| ☐ Mode 0 <br> Mode de ☐ 1 <br> ☐ Mode 2 |
|**Gestion des périphériques**| ☐ Oui, Microsoft Intune <br> ☐ Oui, le gestionnaire de périphériques mobiles (MDM) <br> ☐ Aucun |  
|**Proxy**| Configuration automatique ☐ <br> Serveur proxy ☐ <br> Fichier de configuration automatique de proxy de ☐ (PAC) |
|**Authentification du proxy**| ☐ Informations d’identification du compte de l’appareil <br> Invite ☐ pour les informations d’identification |
|**Rotation du mot de passe**| ☐ <br> ☐ Désactivé |
|**Noms de domaine supplémentaires Skype entreprise (local uniquement)**| |
|**Délai d’expiration de session**| |
|**Action délai d’expiration de session**| ☐ De fin de session <br> ☐ Autoriser le curriculum vitae |
|**Mes réunions et mes fichiers**| ☐ Activé <br> ☐ Désactivé |
|**Délai d’expiration de l’écran de verrouillage**| |
|**Délai d’inactivité du mode Sleep**| |
|**Bluetooth**| ☐ <br> ☐ Désactivé |
|**Utiliser uniquement les lecteurs USB BitLocker**| ☐ <br> ☐ Désactivé |
|**Installer des certificats supplémentaires (local uniquement)**| |
|**Windows Update**| ☐ Windows Update pour les entreprises <br> ☐ Windows Server Update Services [WSUS] |
|**Paramètre de haut-parleur de l’application surface**| Support de roulement ☐ <br> ☐ Monté sur le mur |
|**Adresse IP**| ☐ Filaire — protocole DHCP <br> ☐ Câblée — réservation DHCP <br> ☐ Sans fil — protocole DHCP <br> ☐ Sans fil — réservation DHCP |

## Liste de vérification après le déploiement surface Hub 2

|**Vérification**|**Réponse**|
|:------|:---------|
|**Synchronisation d’un compte d’appareil**| ☐ Oui <br> ☐ Non |
|**Clé BitLocker**| ☐ Enregistré dans le fichier (pas d’affiliation) <br> ☐ Enregistrées dans Active Directory (affiliation publicitaire) <br>☐ Enregistrées dans Azure AD (affiliation Azure AD) |
|**Mises à jour du système d’exploitation de l’appareil**| ☐ Terminé |
|**Mises à jour du Windows Store**| ☐ Automatique <br> ☐ Manuel |
|**Réunion planifiée Microsoft teams**| Courrier électronique de confirmation reçu ☐ <br> ☐ Réunion apparaît sur l’écran d’accueil <br>  ☐ Des fonctions de jointure en une seule effleure <br> ☐ Capable d’accéder à l’audio <br> ☐ Capable de rejoindre une vidéo <br> ☐ Peut partager l’écran ||
|**Réunion programmée Skype entreprise**| Courrier électronique de confirmation reçu ☐ <br> ☐ Réunion apparaît sur l’écran d’accueil <br> ☐ Jointure en une seule saisie fonctionne correctement <br> ☐ Capable d’accéder à l’audio <br> ☐ Capable de rejoindre une vidéo <br> ☐ Peut partager l’écran <br> ☐ Capable d’envoyer et de recevoir des messages instantanés |
|**Réunion programmée lorsque vous avez déjà invité**| ☐ Réunion refusée |
|**Réunion ad-hoc de Microsoft teams**| ☐ Inviter d’autres utilisateurs <br> ☐ Capable d’accéder à l’audio <br> ☐ Capable de rejoindre une vidéo <br> ☐ Peut partager l’écran |
|**Réunion programmée Skype entreprise**| ☐ Inviter d’autres utilisateurs <br> ☐ Capable d’accéder à l’audio <br> ☐ Capable de rejoindre une vidéo <br> ☐ Peut partager l’écran <br> ☐ Capable d’envoyer et de recevoir des messages instantanés |
|**Tableau blanc collaboratif Microsoft**| Écran de démarrage de ☐ à partir de l’écran d’accueil <br> Lancer ☐ à partir de Microsoft teams | 
|**Appel Skype/teams entrant**| ☐ Capable d’accéder à l’audio<br>☐ Capable de rejoindre une vidéo <br> ☐ Peut partager l’écran <br> ☐ Capable d’envoyer et de recevoir des messages instantanés (Skype entreprise uniquement) |
|**Flux vidéo en direct entrants**| ☐ Maximum 2 (Skype entreprise) <br> ☐ 4 maximum (Microsoft Teams) |
|**Comportement 0 du mode Microsoft teams**| ☐ Vignette Skype entreprise sur l’écran d’accueil/démarrer <br> ☐ Pouvez rejoindre des réunions Skype entreprise programmées (interface utilisateur Skype) <br> ☐ Pouvez rejoindre les réunions planifiées d’équipes (interface utilisateur de Teams) |
|**Comportement de Microsoft teams en mode 1**| Vignette d' ☐ équipes sur l’écran d’accueil/démarrer <br> ☐ Pouvez rejoindre des réunions Skype entreprise programmées (interface utilisateur Skype) <br> ☐ Pouvez rejoindre les réunions planifiées d’équipes (interface utilisateur de Teams) |
|**Comportement du mode 2 de Microsoft teams**| Vignette d' ☐ équipes sur l’écran d’accueil/démarrer <br> ☐ Pouvez rejoindre les réunions planifiées d’équipes <br> ☐ Ne parvenez pas à rejoindre des réunions Skype entreprise |
