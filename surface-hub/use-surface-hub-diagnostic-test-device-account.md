---
title: Utilisation de l’outil de diagnostic du matériel SurfaceHub pour tester un compte d’appareil
description: Utilisation de l’outil de diagnostic du matériel SurfaceHub pour tester un compte d’appareil
ms.assetid: a87b7d41-d0a7-4acc-bfa6-b9070f99bc9c
keywords: Paramètres d’accessibilité, application Paramètres, Options d’ergonomie
ms.prod: surface-hub
ms.sitesec: library
author: v-miegge
ms.author: v-miegge
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: 127be0a5f320418d8a1086aec3de62e3ef54e42a
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832681"
---
# Utilisation de l’outil de diagnostic du matériel SurfaceHub pour tester un compte d’appareil

## Introduction

> [!NOTE]
> La section «paramètres du compte» de l’outil de diagnostic du matériel surface Hub ne recueille aucune information. L’adresse de messagerie et le mot de passe entrés en tant qu’entrée sont utilisés uniquement dans votre environnement et ne sont pas collectés et transférés à quiconque. Les informations de connexion persistent uniquement jusqu’à ce que l’application soit fermée ou que vous fermiez la session actuelle sur surface Hub.

> [!IMPORTANT]
> * Les privilèges d’administrateur ne sont pas requis pour exécuter cette application.
> * Les résultats du diagnostic doivent être abordés avec votre administrateur local avant d’ouvrir un appel de service auprès de Microsoft.

### Diagnostic matériel surface Hub

Par défaut, l’application de [diagnostic matérielle surface Hub](https://www.microsoft.com/store/apps/9nblggh51f2g) n’est pas installée dans les versions antérieures du système de surface Hub. L’application est disponible gratuitement sur le Microsoft Store. Les privilèges d’administrateur sont requis pour l’installation de l’application.

   ![Capture d’écran du diagnostic matériel](images/01-diagnostic.png)

## À propos de l’outil de diagnostic du matériel surface Hub

L’outil de diagnostic du matériel surface Hub est un outil facile à parcourir qui permet à l’utilisateur de tester de nombreux composants matériels au sein de l’appareil surface Hub. Cet outil permet également de tester et de vérifier un compte d’appareil surface Hub. Cet article décrit comment utiliser le test des paramètres de compte dans l’outil de diagnostic du matériel surface Hub.

> [!NOTE]
> Le compte d’appareil pour le surface hub doit être créé avant la fin des tests. Le Guide d’administration de surface Hub fournit des instructions et des scripts PowerShell pour vous aider à créer des comptes locaux, en ligne (Office 365) ou des appareils hybrides. Pour plus d’informations, accédez à la rubrique [créer et tester un compte d’appareil (surface Hub)](https://docs.microsoft.com/surface-hub/create-and-test-a-device-account-surface-hub) dans le guide.

### Processus de test de compte d’appareil

1. Accédez à **toutes les applications**, puis recherchez l’application de diagnostic du matériel surface Hub.

    ![Capture d’écran de toutes les applications](images/02-all-apps.png)

1. Au démarrage de l’application, la page d' **Accueil** fournit une fenêtre de texte pour documenter la raison pour laquelle vous testez le Hub. Cette note peut être enregistrée dans USB conjointement avec les résultats de diagnostic lors de la fin des tests. Lorsque vous avez fini d’entrer une note, cliquez sur le bouton **Continuer** .

    ![Capture d’écran de l’accueil](images/03-welcome.png)

1. L’écran suivant vous permet de tester l’ensemble ou certaines des composantes de surface Hub. Pour commencer à tester le compte de l’appareil, sélectionnez l’icône **résultats du test** .

    ![Capture d’écran des résultats de test](images/04-test-results-1.png)

    ![Capture d’écran des résultats de test](images/05-test-results-2.png)

1. Sélectionnez **paramètres du compte**.  

    ![Capture d’écran des paramètres de compte](images/06-account-settings.png)

    L’écran Paramètres du compte permet de tester votre compte d’appareil.

    ![Capture d’écran des paramètres de compte](images/07-account-settings-details.png)

1. Entrez l’adresse de messagerie de votre compte d’appareil. Le mot de passe est facultatif, mais il est recommandé. Cliquez sur le bouton **tester le compte** lorsque vous êtes prêt à continuer.

    ![Capture d’écran du compte de test](images/08-test-account.png)

1. Une fois le test terminé, passez en revue les résultats pour les quatre domaines de test. Vous pouvez développer ou réduire chaque section en sélectionnant le signe plus ou moins en regard de chaque sujet.

    **Network**

    ![Capture d’écran du réseau](images/09-network.png)

    **Environnement**

    ![Capture d’écran d’un environnement](images/10-environment.png)

    **Certificats**

    ![Capture d’écran des certificats](images/11-certificates.png)

    **Modèle d’approbation**

    ![Capture d’écran d’un modèle d’approbation](images/12-trust-model.png)

## Annexe

### Messages et résolution de champs

#### Network

Champ |Réussite |Échec |Comment |Référence
|------|------|------|------|------|
Connectivité Internet |L’appareil est connecté à Internet |L’appareil n’est pas connecté à Internet |Vérifie la connectivité Internet, y compris la connexion proxy |
Version HTTP |1,1 |1.0 |Si le protocole HTTP 1,0 est détecté, il engendre un problème avec WU et Store |
Connectivité Internet directe |Aucun proxy configuré sur l’appareil |N/A |Information. Votre appareil est-il derrière un proxy? |
Adresse proxy | | |S’il est configuré, renvoie l’adresse du proxy. |
Authentification du proxy |Le proxy ne requiert pas d’authentification |Le proxy nécessite l’authentification par proxy |Le résultat peut être un faux positif si un utilisateur possède déjà une session ouverte dans Edge et s’est authentifiée par le biais du proxy. |
Types d’authentifications de proxy | | |Si l’authentification par proxy est utilisée, retournez les méthodes d’authentification annoncées par le proxy.  |

#### Environnement

Champ |Réussite |Échec |Comment |Référence
|------|------|------|------|------|
Domaine SIP | | |Information.  |
Environnement Skype |Skype entreprise Online, Skype entreprise hébergé, Skype entreprise hybride |Information. |Type d’environnement détecté. Remarque: la valeur hybride ne peut être détectée que si le mot de passe est entré.
Nom de domaine complet LyncDiscover | | |Information. Affiche le résultat DNS de LyncDiscover |
URI LyncDiscover | | |Information. Affiche l’URL utilisée pour effectuer une LyncDiscover sur votre environnement.|
LyncDiscover |Connexion réussie |Échec de la connexion |Réponse du service Web LyncDiscover. |
Nom d’hôte du pool SIP | | |Information. Afficher le nom du pool SIP détecté à partir de LyncDiscover |

#### Certificats (environnement hybride local uniquement)

Certificat LyncDiscover

Champ |Réussite |Échec |Comment |Référence
|------|------|------|------|------|
LyncDiscover CERT NC | | |Information. Affiche le nom usuel du certificat LD |
CA Cert LyncDiscover | | |Information. Affiche l’autorité de certification LD CERT |
Autorité de certification racine de LyncDiscover CERT | | |Information. Affiche l’autorité de certification racine de CERT, le cas échéant. |
LD état d’approbation |Le certificat est approuvé. |Le certificat n’est pas approuvé, ajoutez l’autorité de certification racine. |Vérifiez le certificat par rapport au magasin de certificats local. Retourne un résultat positif si l’ordinateur approuve le certificat.|[Télécharger et déployer des certificats Skype entreprise à l’aide de PowerShell](https://blogs.msdn.microsoft.com/surfacehub/2016/06/07/download-and-deploy-skype-for-business-certificates-using-powershell/) / [Éléments pris en charge pour les packages de mise en service de surface Hub](https://docs.microsoft.com/surface-hub/provisioning-packages-for-surface-hub#supported-items-for-surface-hub-provisioning-packages)

Certification du pool SIP

Champ |Réussite |Échec |Comment |Référence
|------|------|------|------|------|
CERT du pool SIP | | |TENEUR |
Autorité de certification du pool SIP | | |TENEUR |
État d’approbation du pool SIP |Le certificat est approuvé. |Le certificat n’est pas approuvé, ajoutez l’autorité de certification racine. |Vérifiez le certificat par rapport au magasin de certificats local et renvoyez un résultat positif si les appareils approuvent le certificat. |
Autorité de certification racine de certification du pool SIP | | |Concernant. Affichez la racine de certification de la liste SIP, le cas échéant. |

#### Modèle de confiance (environnement hybride local uniquement)

Champ |Réussite |Échec |Comment |Référence
|------|------|------|------|------|
État du modèle de confiance |Aucun problème de modèle de confiance détecté. |Le domaine SIP et le domaine du serveur sont différents ajoutez les domaines suivants. |Vérifiez le nom du serveur LD FQDN/LD nom de serveur/pool pour le problème de modèle d’approbation. 
Nom (s) de domaine | | |Renvoyez la liste des domaines qui doivent être ajoutés pour que marketing se connecte. |
