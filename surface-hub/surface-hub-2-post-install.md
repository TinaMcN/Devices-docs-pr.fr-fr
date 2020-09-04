---
title: Configurer Windows 10 professionnel ou entreprise sur surface Hub 2
description: Cet article inclut des recommandations pour garantir une meilleure utilisation lors de l’utilisation d’un ordinateur de stylet et d’un grand écran personnalisés.
keywords: Surface Hub, Windows 10, ordinateur de bureau, installer, configuration
ms.prod: surface-hub
ms.mktglfcycl: deploy
ms.localizationpriority: low
ms.sitesec: library
ms.pagetype: deploy
audience: admin
manager: laurawi
ms.audience: itpro
author: greg-lindsay
ms.collection: M365-modern-desktop
ms.topic: article
ms.openlocfilehash: 47852284c35d213b81dd7b87ca875b400d8c713f
ms.sourcegitcommit: c74835239cf4e304af59465fb6fc785de4a0c5cc
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/03/2020
ms.locfileid: "10994590"
---
# Configurer Windows 10 professionnel ou entreprise sur surface Hub 2

**S’applique à: surface Hub 2** 

Après avoir terminé le processus d’installation de la migration vers Windows 10 professionnel ou entreprise, vous pouvez effectuer les étapes suivantes pour configurer les applications et les paramètres sur votre surface Hub 2. Ces étapes sont recommandées pour garantir la meilleure utilisation de cette fonction d’affichage du stylo et de l’écran grand écran.

Lors de cette procédure, il peut s’avérer utile d’utiliser un clavier et une souris sans fil.

## Configurer les paramètres système

1. Connectez-vous à l’aide d’un compte disposant de privilèges d’administrateur local sur l’appareil.  
    - Sur les appareils disposant d’Azure AD, l’utilisateur qui exécute la jointure Azure AD est automatiquement ajouté au groupe d’administrateurs local. Les administrateurs généraux d’Azure AD et d’Azure AD sont [également administrateurs locaux](https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin). 
    - Vous pouvez taper **administrateurs .net localgroup** à une invite de commandes pour répertorier les comptes disposant de droits d’administrateur local.
2. Renommez l’appareil en utilisant un nom convivial, par exemple: **nom_utilisateur-SHub-Desktop**.
3. Sélectionnez **Démarrer**  >  les**paramètres**des  >  **comptes**pour  >  **synchroniser vos paramètres** et désactiver les **paramètres de synchronisation** . 
    - Les paramètres utilisés ici sont destinés à permettre une meilleure utilisation de l’affichage des fonctions visuelles de grande taille et, par conséquent, vous ne souhaitez pas synchroniser d’autres appareils.
4. Redémarrez l'appareil.

## Activez le clavier tactile et le pavé tactile.

1. Appuyez de façon prolongée ou cliquez avec le bouton droit sur la barre des tâches, puis sélectionnez **afficher le bouton du clavier tactile** et **afficher le bouton du pavé**tactile. 
    - Le clavier tactile est utile pour la saisie directe de l’utilisateur, et le pavé tactile virtuel permet d’effectuer des sélections précises, de pointage sur les info-bulles ou d’appuyer longuement sur un clic avec le bouton droit. 
    - Consultez l’exemple suivant.

     ![Paramètres d’interaction](images/touch.png)

2. Configurez le clavier visuel sur azerty et flottez.
    1. Cliquez sur l’icône de clavier dans la barre des tâches pour afficher le clavier visuel.
    2. Sur le clavier visuel, sélectionnez l’icône de clavier dans le coin supérieur gauche pour ouvrir les paramètres du clavier.
    3. Activez la case à cocher en regard de dernier type de clavier dans la ligne du haut pour activer AZERTY, et la dernière option pour activer le mode flottant, ce qui est très utile sur ce grand écran. Consultez les exemples suivants.

     ![Paramètres du clavier](images/kbd.png)

3. Configurez les paramètres de clavier logiciels.
    1. Recherchez et ouvrez les **paramètres de saisie** 
    2. Activez toutes les options sous orthographe, saisie et clavier vocal.


L’exemple suivant illustre pavé tactile, qui est utile pour naviguer et sélectionner des options. Le clavier à l’écran est utilisé pour effectuer une recherche sur le Microsoft Store:

![Utiliser le pavé tactile](images/store.png)

## Configurer le clavier et la souris Bluetooth (facultatif)

Connectez un clavier et une souris si vous utilisez le périphérique en tant qu’appareil Windows principal, ou si vous utilisez souvent cette fonctionnalité pour la saisie ou la précision du fonctionnement.

Si votre périphérique surface Hub est proche d’un PC, vous pouvez utiliser [la souris sans bordure](https://aka.ms/mm) pour vous déplacer en douceur entre le centre de surface et le PC. Pour plus d’informations, reportez-vous [à la rubrique téléchargement de Microsoft à partir du garage: souris sans bordure](https://blogs.microsoft.com/ai/microsoft-download-from-the-garage-mouse-without-borders/).

## OneDriveEntreprise

Utilisez [OneDrive entreprise](https://docs.microsoft.com/onedrive/onedrive) pour partager facilement des outils, des journaux et d’autres fichiers entre tous vos périphériques de travail.

- OneDrive vous permet de partager vos fichiers de travail entre votre ordinateur portable, votre bureau surface Hub et vos appareils mobiles gérés par Intune. Les fichiers peuvent être modifiés sur n’importe quel appareil, et tous les appareils connectés réseau sont mis à jour avec les modifications.
- Si vous considérez la taille de la fonction SSD de surface Hub (128 Go), si vous configurez OneDrive sur votre appareil de bureau surface Hub, assurez-vous que la configuration par défaut est de conserver les fichiers en ligne et de télécharger des fichiers lorsque vous les utilisez.

Pour configurer OneDrive pour télécharger les fichiers uniquement lorsque cela est nécessaire, définissez le paramètre **fichiers à la demande** pour **économiser de l’espace et télécharger les fichiers lorsque vous les utilisez**. Pour plus d’informations, reportez-vous à [la rubrique interroger et définir des fichiers à la demande dans Windows](https://docs.microsoft.com/onedrive/files-on-demand-windows).

![Paramètres de OneDrive](images/onedrive.png)

> [!NOTE]
> Vous pouvez également répéter ces étapes pour configurer votre espace OneDrive personnel, mais n’êtes pas sûr de ménager de l’espace disque et de télécharger uniquement les fichiers dont vous avez besoin.

## SharePoint et Teams

Les fichiers de canal SharePoint et teams peuvent également être synchronisés localement sur vos appareils de bureau, tels que les ordinateurs portables et les hubs de surface, à l’aide du moteur de synchronisation OneDrive.

Pour synchroniser des fichiers d’entreprise internes sur votre disque local à l’aide de l’application de synchronisation OneDrive:

1. Accédez à un site SharePoint et naviguez jusqu’au répertoire de documents de niveau supérieur correspondant aux fichiers que vous souhaitez afficher ou modifier à partir de votre appareil local.
2. Cliquez sur le bouton **synchroniser** situé en haut du ruban SharePoint.
3. Sélectionner sur **ouvrir** dans le menu contextuel **ce site tente d’ouvrir Microsoft OneDrive**.
4. Vérifiez que les fichiers SharePoint sont synchronisés avec votre lecteur local en sélectionnant l’icône OneDrive située en bas à droite de la barre des tâches.
5. Vérifiez que la configuration est définie pour conserver les fichiers en ligne et télécharger les fichiers uniquement lors de leur utilisation:
    1. Ouvrez l’Explorateur de fichiers.
    2. Naviguez jusqu’à droite et sélectionnez dans la section **Microsoft \ \<SharePoint Document Folder Name\> **.
    3. Sélectionnez **libérer**de l’espace.
    4. La colonne État affiche l’état des fichiers et des dossiers. Pour plus d’informations, voir [synchroniser des fichiers SharePoint avec le client de synchronisation OneDrive](https://support.microsoft.com/office/sync-sharepoint-files-with-the-onedrive-sync-client-groove-exe-59b1de2b-519e-4d3a-8f45-51647cf291cd).
6. Les fichiers de canal teams sont stockés sur des sites SharePoint, avec toutes les mêmes fonctionnalités de documents SharePoint, y compris l’historique des versions et la synchronisation avec les appareils de bureau locaux. Pour synchroniser des fichiers de canal d’équipe:
    1. Accédez au canal d’intérêt de l’équipe et sélectionnez l’onglet **fichiers** en haut. Sélectionnez **synchroniser**. Les fichiers commenceront à se synchroniser et sont visibles dans l’Explorateur de fichiers sur le **Bureau \ Microsoft \ \<name of the Teams Channel\> **.
    2. Utilisez la même procédure que celle que vous avez utilisée pour synchroniser des sites SharePoint afin de conserver les fichiers dans le Cloud et de les télécharger uniquement lorsque vous les utilisez, appuyez longuement ou cliquez avec le bouton droit dans l’Explorateur de fichiers sur le nom du canal Teams, puis sélectionnez libérer de l' **espace**.

## Couplez le stylet surface Hub

Pour jumeler l’appareil de stylet:

1. Sélectionnez Paramètres de **démarrage**de l'  >  **Settings**  >  **appareil**.
2. Sélectionnez **Ajouter un appareil Bluetooth ou un autre appareil**.
3. Sélectionnez **Bluetooth**.
4. Supprimez le bouton de queue du stylo et secouez la connexion à la batterie.
5. Placez le capuchon en retour, puis appuyez de façon prolongée sur le capuchon jusqu’à ce que le voyant du jumelage clignote.
6. Dans les paramètres Bluetooth surface Hub, sélectionnez **surface Hub 2 PEN**.
7. Terminez l’opération de jumelage. 
8. Si le jumelage ne fonctionne pas, essayez à nouveau de jumeler le stylet. Le cas échéant, redémarrez l’appareil, puis réessayez.

## Configuration de la caméra

Vous pouvez monter la caméra sur le dessus ou sur l’un ou l’autre extrémité de l’appareil. Montez l’appareil photo en position pour optimiser l’angle de la caméra si vous utilisez le concentrateur avec un socle de bureau plutôt qu’un panier, ou que vous êtes en proximité du Hub. Comme la caméra ne pivote pas automatiquement, vous devez disposer d’une touche hexadécimale 2mm pour faire pivoter manuellement la caméra. 

Pour plus d’informations sur la façon de monter la caméra et de la faire pivoter manuellement, voir orientation de l’objectif de la caméra [surface Hub](https://support.microsoft.com/help/4509729/surface-hub-2s-camera-lens-orientation).

## Configuration de Windows Hello

Surface Hub 2-xxxxx xxx XXXXXXX XXXXXXX xxxx xxx xxxxxxx xxx XXXXXXX XXXXXXX XXXXXXX XXXXXXX XXXXXXX XXXXXXX XXXXXXX XXXXXXX xxxx. Les accessoires du lecteur d’empreintes digitales de surface Hub 2 peuvent être branchés dans n’importe quel port USB-C de l’appareil. 

> <i>Le lecteur d’empreintes digitales surface Hub 2 sera bientôt disponible à l’achat. Consultez de nouveau cette page pour en savoir plus sur l’achat.</i>

Après avoir inséré le lecteur d’empreintes digitales **, sélectionnez**  >  **paramètres**  >  **Accounts**  >  **de connexion comptes options de connexion dans**  >  votre**empreinte digitale Windows Hello** pour inscrire votre empreinte digitale.

Utilisez un appareil certifié Windows Hello pour la reconnaissance faciale. La caméra surface Hub 2 ne prend pas en charge la reconnaissance faciale Windows Hello.

## Activer un raccourci de l’écran de verrouillage dans la barre des tâches

Pour ajouter une icône à la barre des tâches qui permet le verrouillage de l’écran à une seule touche, comme le raccourci clavier Windows-L: 

1.  Appuyez de façon prolongée ou cliquez avec le bouton droit sur le bureau, sélectionnez **nouveau**  >  **raccourci**  >  **Parcourir**le  >  **Bureau**  >  **OK**  >  **suivant**.

1.  Indiquez un nom pour le raccourci tel que **verrouiller mon PC**, puis cliquez sur **Terminer**.

1.  Cliquez avec le bouton droit ou appuyez longuement sur le raccourci qui vient d’être créé sur le bureau, puis sélectionnez **Propriétés**. Dans l’onglet **raccourci** , entrez les informations suivantes dans le champ **cible** : **Rundll32.exe User32.dll LockWorkStation**

1.  Cliquez sur le bouton **modifier l’icône** et recherchez **C:\Windows\System32\imageres.dll** et sélectionnez une icône à utiliser. 

    Consultez l’exemple suivant:

    ![Choisir une icône](images/lock.png)
    
1.  Cliquez sur **OK** pour enregistrer le raccourci.

1.  Cliquez avec le bouton droit ou appuyez longuement sur le raccourci et sélectionnez **Épingler à la barre des tâches**.

## Applications

### Mettre à jour les applications installées

Pour mettre à jour toutes les applications du Windows Store installées:

1. Ouvrez l’application Microsoft Store et sélectionnez les points de suspension **voir plus** dans le coin supérieur droit.
2. Sélectionnez **Téléchargements et mises à jour**.
2. Sélectionnez **Obtenir les mises à jour**.

### Tableau blanc collaboratif Microsoft

Pour installer le tableau blanc Microsoft, procédez comme suit:

 - Cliquez sur l’icône de l' **espace de travail Windows Ink** dans le coin inférieur droit de la barre des tâches et téléchargez le **tableau blanc**.
 
   ![Espace de travail Ink](images/ink.png) 

Vous pouvez également installer le tableau blanc à partir du Microsoft Store:

1. Ouvrez l’application Microsoft Store et recherchez le **tableau blanc**.
2. Choisissez **non merci** pour vous connecter et utiliser les différents appareils.
3. Épingler le tableau blanc dans la barre des tâches.

### Application surface

1. Dans la boutique Microsoft, recherchez **surface**.
2. Définissez le **niveau de filtrage disponible sur** **tous les appareils**.
3. Installez l’application **surface** . Il s’agit de la première application répertoriée. Vous devrez peut-être associer votre MSA au Windows Store pour pouvoir installer l’application.
4. Épingler l’application **surface** à la barre des tâches.

### Capture & croquis

1. Ouvrez l’application de **capture & esquisse** et épinglez-la à la barre des tâches.
2. Sélectionnez les points de suspension dans le coin supérieur droit, puis sélectionnez **paramètres**.
3. Dans **paramètres**, activez la fonction de **copie automatique dans le presse-papiers**, **Enregistrez les captures**et les **fenêtres multiples** (facultatif).

### MicrosoftOffice

1. Ouvrez le [portail Office](https://portal.office.com/account#installs) et installez les applications souhaitées.
2. Épinglez les applications Office souhaitées dans la barre des tâches.
3. Si Outlook est installé, assurez-vous de définir le cache OST Outlook de façon à ce qu’il enregistre uniquement le cache des deux dernières semaines. Le temps d’utilisation et de configuration du disque sera considérablement réduit.
    - Sélectionnez **File**  >  **paramètres du compte** de fichier, puis sélectionnez votre compte.
    - Sélectionnez **modifier** , puis positionnez le curseur pour **utiliser le mode Exchange mis en cache** à 14 jours.

### Microsoft Teams

1. Télécharger et installer [Microsoft teams](https://teams.microsoft.com/downloads).
2. Configurez les paramètres de démarrage automatique de l’application (facultatif).
3. Épingler des équipes dans la barre des tâches.
4. Envisagez de réduire les notifications d’équipe sur l’appareil pour éviter toute distraction (facultatif).

  ![Notifications teams](images/teams.png)

### Connecter l’application

> [!IMPORTANT]
> Dans Windows 10, version 2004 et ultérieure, l’application connexion pour la projection sans fil à l’aide de Miracast n’est pas installée par défaut, mais est disponible sous la forme d’une fonctionnalité facultative. Pour installer l’application, sélectionnez les **Settings**  >  **Apps**  >  **fonctionnalités facultatives**  >  **Ajouter une fonctionnalité** aux applications, puis installez l’application d' **affichage sans fil** .

1. Recherchez **connexion**.
2. Ouvrez l’application, puis fermez-la (**Project à ce PC** peut ne pas fonctionner tant que l’application n’a pas été exécutée au moins une fois).
3. Appuyez de façon prolongée ou cliquez avec le bouton droit pour épingler à la barre des tâches.
4. Recherchez les **paramètres de projection**.
5. Sous **certains appareils Windows et Android peuvent projeter sur ce PC lorsque vous prononcez**la mention OK, choisissez **disponible partout** si l’appareil n’est pas sur un réseau d’entreprise. Dans le cas contraire, vous pouvez choisir **partout sur des réseaux sécurisés**.
6. Sous **demander à Project pour ce PC**, choisissez **première fois uniquement**.
7. Sous **exiger le code confidentiel pour le jumelage**, sélectionnez **jamais**.

Configuration recommandée hors du réseau d’entreprise:

  ![Paramètres à la maison](images/project1.png)

Configuration recommandée sur le réseau d’entreprise:

  ![Paramètres au bureau](images/project2.png)

### Votre téléphone

L’application **votre téléphone** est installée par défaut sur Windows 10. Si ce n’est pas le cas, vous pouvez également l’installer à partir du Windows Store.

Pour plus d’informations sur la configuration de l’application, reportez-vous à la rubrique Configuration de [votre téléphone sur Windows 10 et synchronisation des données entre votre ordinateur et votre téléphone](https://www.windowscentral.com/how-set-your-phone-windows-10). Consultez également [la rubrique Comment résoudre les problèmes courants liés à votre application de téléphone sur Windows 10](https://www.windowscentral.com/how-fix-common-problems-your-phone-app-windows-10).

### Zones super fantaisie

Les **zones super fantaisie** permettent aux utilisateurs de réorganiser les fenêtres afin de maximiser l’espace disponible à l’écran. Elle est désormais incluse dans [PowerToys](https://github.com/microsoft/PowerToys/releases) sur GitHub.

### Navigateur Microsoft Edge chrome

Téléchargez et installez le nouveau [navigateur Microsoft Edge chrome](https://www.microsoft.com/en-us/edge?form=MY01BL&OCID=MY01BL).

## Paramètres supplémentaires

### Stylo d’aileron sélectionner pour lancer le tableau blanc

1. Recherchez **stylo** et sélectionnez **stylo & paramètres Windows Ink**.
2. Dans la partie inférieure de la page, sous **raccourcis clavier** , définissez l' **option Sélectionner une fois** sur le **tableau blanc collaboratif Microsoft**. 

### Paramètres d’alimentation et de veille

1. Sélectionnez **Démarrer**les  >  **paramètres**  >  **système**  >  **d’alimentation & Sleep**.
2. Positionnez le curseur mode d’alimentation sur **meilleures performances**.
3. Configurez les valeurs de l’écran et du mode veille à votre choix.

### Écran de veille

1. Recherchez l' **écran de verrouillage** et ouvrez les paramètres de l' **écran de verrouillage**.
2. Configurez vos préférences en matière de **paramètres de délai d’écran** et de paramètres d' **écran de veille** .

### Assistant Stockage

Surface Hub 2 étant doté d’un appareil compact de 128 Go pour le stockage local, il est nécessaire de tenir compte de l’utilisation des mesures d’enregistrement de stockage en cas d’utilisation normale.  Pour configurer le sens de stockage:

1.  Recherchez **paramètres de stockage**dans les **paramètres système**.
2.  Sous **paramètres**, sélectionnez l’option **activer le stockage** pour ouvrir la page Paramètres de **stockage** .
3.  Activez **le stockage sur activé**.
4.  Sélectionnez **configurer un sens de stockage ou exécutez-le maintenant** et configurez les paramètres permettant de conserver les fichiers en ligne le plus possible (en raison de l’espace disque limité).

Paramètres recommandés:
- Utilisez l’outil de stockage = quotidiennement.
- Supprimez les fichiers temporaires que mes applications n’utilisent pas = tous les 14 jours (au moins).
- Supprimer les fichiers du dossier téléchargements s’ils y étaient depuis plus de 30 jours.
- OneDrive: le contenu devient en ligne uniquement s’il n’est pas ouvert pendant plus de 30 jours.

### Mode tablette

Activez le mode tablette si vous le souhaitez, pour les besoins en matière d’accessibilité.

### Gestion de l’alimentation

> [!NOTE]
> Avant d’effectuer la procédure suivante, contactez votre service informatique pour obtenir de l’aide afin d’exclure un périphérique surface Hub 2 de la stratégie de gestion de l’alimentation globale. Certains paramètres de gestion de l’alimentation peuvent désactiver la fonction de détection de présence.

1. Recherchez le **Centre de logiciels** et ouvrez-le.
2. Sélectionnez des **options** dans le volet de navigation.
3. Développez la section gestion de l' **alimentation** et sélectionnez **ne pas appliquer les paramètres d’alimentation du service informatique à cet ordinateur**.

   ![Paramètres logiciels](images/soft-cntr.png)

### Paramètres du son

1. Recherchez les **paramètres audio** et ouvrez cette page.
2. Sélectionnez **son panneau de configuration** sur la droite, puis sélectionnez l’onglet **sons** .
3. Sous **événements** , définissez l’option **connexion** de l’appareil et **Débranchez l’appareil** à **aucun**.

### Notifications de silence

1. Recherchez **assistance au focus** et ouvrez cette page.
2. Sélectionner **alarmes uniquement**. Cela évite les menus volants de notifications constantes.

### Nettoyage de disque

1. Recherchez **Disk Cleanup** et ouvrez cette application.
2. Sous **fichiers à supprimer**, sélectionnez les fichiers que vous souhaitez supprimer. 
3. Sélectionnez également **nettoyer les fichiers système**.

## Achever et vérifier

1. Recherchez et installez toutes les mises à jour Windows.
2. Mise à jour de la stratégie de groupe
    1. À l’invite de commandes avec élévation de privilèges, entrez **gpupdate/force/Boot/Wait: 0**.
3. Redémarrez l'appareil.
4. Vérifiez les applications de la barre des tâches.
    - Connecter l’application
    - Icône de verrouillage
    - Capture & croquis
    - Teams (le cas échéant)
    - Applications Office (le cas échéant)
    - Application surface
    - Tableau blanc
5. Vérifier la détection de présence.
    - La détection de présence sera une icône verte dans la barre d’état système
6. Vérifier que l’application de Project à ce PC est activée avec l’application connexion (l’application n’a pas besoin d’être en cours d’exécution avant la connexion).
7. Vérifiez les paramètres d’alimentation et de veille.
    - Écran de veille: 15 minutes, définie sur (aucune), mystification ou Blank; la case à cocher pour exiger un mot de passe est activée
    - Écran: 2 heures
    - PC: 4 heures
8. Vérifiez que Windows Hello fonctionne.
9. Vérifiez les paramètres d’alimentation.
10. Vérifier la synchronisation vos paramètres sont désactivés.
11. Vérifiez les applications de démarrage.

> [!TIP]
> Après l’installation et la configuration de Windows 10, les applications de surface Hub 2 peuvent être gérées comme n’importe quel autre appareil Windows 10.

## Rubriquesassociées

[Migrer vers Windows 10 Professionnel ou Entreprise sur Surface Hub 2](surface-hub-2s-migrate-os.md)
