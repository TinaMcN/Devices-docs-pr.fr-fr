---
title: Programme de première utilisation (Surface Hub)
description: L’expression \ 0034;première utilisation \ 0034; fait référence à la procédure par laquelle vous passez la première fois que vous allumez votre Microsoft Surface Hub. Elle est synonyme de \ 0034;out-of-box experience \ 0034; (OOBE). Cette section va vous guider dans cette procédure.
ms.assetid: 07C9E84C-1245-4511-B3B3-75939AD57C49
ms.reviewer: ''
manager: laurawi
keywords: première utilisation, Surface Hub, out-of-box experience, OOBE
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 10/27/2020
ms.localizationpriority: medium
ms.openlocfilehash: e070c28d13cd8466bff47022f4508fdb8aa06331
ms.sourcegitcommit: 19d2a78242777590bd09af3ac6552c07b032e0a1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "11142913"
---
# Programme de première utilisation (Surface Hub)


L’expression «première utilisation» fait référence à la procédure par laquelle vous passez la première fois que vous allumez votre Microsoft Surface Hub. Elle est synonyme de «out-of-box experience» (OOBE). Cette section va vous guider dans cette procédure.

À présent, vous devriez avoir effectué toutes les étapes précédentes :

-   [Préparer votre environnement pour Surface Hub](prepare-your-environment-for-surface-hub.md)
-   [Installer physiquement votre appareil Surface Hub](physically-install-your-surface-hub-device.md) et
-   [Fiche d’installation](setup-worksheet-surface-hub.md)

Dans cette hypothèse, la première utilisation devrait être à la fois simple et rapide.
La procédure normale passe par six étapes :

1.  [Page Bonjour](#first-page)
2.  [Page Configuration pour vous](#set-up-for-you)
3.  [Page Compte d’appareil](#device-account)
4.  [Page Nommer cet appareil](#name-this-device)
5.  [Page Configurer des administrateurs pour cet appareil](#setup-admins)
6.  [Mettre à jour le Surface Hub](#update-surface-hub)

Chacune de ces sections contient également des informations sur les chemins que vous pouvez emprunter lorsque quelque chose est différent. Par exemple, la plupart des Surface Hub utilisent une connexion réseau filaire, mais certains sont configurés avec la technologie sans fil à la place. Des détails sont fournis le cas échéant.

>[!NOTE]
>Le clavier séparé fourni avec votre Surface Hub doit être configuré et prêt avant que vous ne commenciez. Consultez le Guide d’installation de SurfaceHub pour plus d’informations.

 

## <a href="" id="first-page"></a>Page Bonjour


Il s’agit du premier écran qui s’affiche lorsque vous allumez le Surface Hub pour la première fois. C’est la page où vous saisissez les informations sur la localisation de votre appareil.

>[!NOTE]
>Elle vous permet également de commencer le processus facultatif de déploiement d’un package d’approvisionnement. Consultez [Créer des packages d’approvisionnement](provisioning-packages-for-certificates-surface-hub.md) le cas échéant.

 Sélectionnez une langue; les options de configuration initiales s’affichent.

![Image illustrant la liste de vérification des optionsICD.](images/setuplocale.png)

### Détails

Si les valeurs par défaut affichées sont correctes, vous pouvez ensuite cliquer sur **Suivant** pour continuer. Dans le cas contraire, vous devrez saisir des données dans les champs appropriés.

-   **Pays/région :** sélectionnez le pays ou la région où le Surface Hub est utilisé.
-   **Langue de l’application :** les applications et fonctionnalités s’affichent dans cette langue et ce format de langue.
-   **Disposition du clavier :** sélectionnez la disposition du clavier pour les claviers à l’écran et physique utilisés avec votre appareil.
-   **Fuseau horaire:** sélectionnez le fuseau horaire dans lequel le Surface Hub est utilisé.

### Que se passe-t-il?

>[!NOTE]
> Une fois que les paramètres de cette page sont entrés, vous ne pouvez pas revenir à cet écran, sauf si vous réinitialisez l’appareil (consultez [Réinitialiser l'appareil](device-reset-surface-hub.md)). Assurez-vous que les paramètres sont configurés correctement avant de poursuivre.

 

Une fois que les paramètres sont acceptés, l’appareil recherche une connexion réseau filaire. Si la connexion est correcte, la [page Configuration pour vous](#set-up-for-you)s’affiche. S’il y a un problème avec la connexion filaire, l’appareil affiche la [page Configuration réseau](#network-setup).

Si aucune connexion filaire n’est détectée, l’appareil essaie de configurer une connexion sans fil et affiche la [page Configuration réseau](#network-setup).

## <a href="" id="network-setup"></a>page Configuration réseau


Si votre appareil ne détecte pas de connexion filaire qu’il peut utiliser pour se connecter à un réseau ou à Internet, vous verrez cette page. Ici, vous pouvez vous connecter à un réseau sans fil, ou ignorer l’étape de configuration de la connexion réseau.

![Image illustrant la page de configuration réseau.](images/setupnetworksetup-1.png)

### Détails

Cet écran s’affiche uniquement si l’appareil ne parvient pas à détecter un réseau filaire. Si vous voyez cet écran, trois options s’offrent à vous :

-   Vous pouvez sélectionner l’un des réseaux sans fil indiqués. Si le réseau est sécurisé, vous êtes dirigé vers une page d’ouverture de session. Consultez [Configuration du réseau sans fil](#wireless) pour plus d’informations.
-   Cliquez sur **Ignorer cette étape** pour ignorer l’étape de connexion à un réseau. Vous allez être dirigé vers la [page Configuration pour vous](#set-up-for-you).
    >[!NOTE]
    >Si vous ignorez cette étape, l’appareil ne disposera pas d’une connexion réseau, et les fonctions nécessitant une connexion réseau sur votre Surface Hub ne fonctionneront pas, notamment les mises à jour du système et la synchronisation du courrier électronique et du calendrier. Vous pouvez vous connecter à un réseau sans fil ultérieurement à l’aide de paramètres (voir [gestion de réseau sans fil](wireless-network-management-for-surface-hub.md)).

     

-   Vous pouvez brancher un câble réseau tandis que cet écran est visible. L’appareil le détectera et ajoutera l’option **Suivant** à l’écran. Cliquez sur **Suivant** pour continuer avec la configuration de la connexion filaire.

### Que se passe-t-il ?

Si l’appareil dispose d’une connexion filaire au démarrage et que vous pouvez établir une connexion réseau ou Internet, cette page ne s’affiche pas. Si vous souhaitez connecter l’appareil à une connexion sans fil, assurez-vous qu’aucun câble Ethernet n’est branché lors de la première utilisation, ce qui vous amènera à cet écran. Quelle que soit l’option que vous choisissez de configurer maintenant, vous pouvez [utiliser Paramètres](wireless-network-management-for-surface-hub.md) pour configurer des connexions différentes plus tard.

Si vous souhaitez vous connecter à un réseau sans fil sécurisé à partir de cette page, cliquez sur le réseau de votre choix, puis fournissez les informations nécessaires (mot de passe ou informations d’identification de compte) pour vous connecter. Consultez [Configuration du réseau sans fil](#wireless).

## <a href="" id="wireless"></a>Configuration du réseau sans fil


Cette page s’affiche lorsque vous avez sélectionné un réseau sans fil sécurisé.

![Image illustrant la page de configuration d’un réseau sans fil.](images/setupnetworksetup-3.png)

### Détails

-   **Nom d’utilisateur :** saisissez le nom d’utilisateur pour le réseau sans fil sélectionné.
-   **Mot de passe :** il s’agit du mot de passe du réseau.

### Que se passe-t-il ?

L’appareil essaie de se connecter au réseau spécifié. Si la connexion réussit, vous êtes dirigé vers la [page Configuration pour vous](#set-up-for-you).

## <a href="" id="proxy"></a>Configuration du proxy réseau


Cette page s’affiche lorsque l’appareil détecte une connexion filaire avec une connectivité limitée. Trois options s’offrent à vous :

-   Vous pouvez sélectionner un réseau sans fil à utiliser au lieu de la connexion filaire limitée.
-   Vous pouvez ignorer l’étape de connexion à un réseau en sélectionnant **Ignorer cette étape**. Vous allez être dirigé vers la [page Configuration pour vous](#set-up-for-you).
    **Remarque**  Si vous ignorez cette étape, l’appareil ne disposera pas d’une connexion réseau, et les fonctions nécessitant une connexion réseau sur votre Surface Hub ne fonctionneront pas, notamment la synchronisation du courrier électronique et du calendrier. Vous pouvez vous connecter à un réseau sans fil ultérieurement à l’aide de paramètres (voir [gestion de réseau sans fil](wireless-network-management-for-surface-hub.md)).

     

-   Vous pouvez sélectionner **Entrer les paramètres du proxy** ce qui vous permettra de spécifier l’utilisation du proxy réseau. Vous allez être dirigé vers l’écran suivant.

    ![Image illustrant la page du proxy réseau.](images/setupnetworksetup-2.png)

    Il s’agit de l’écran qui s’affiche si vous avez cliqué sur **Entrer les paramètres du proxy** dans l’écran précédent.

    ![Image illustrant les détails des paramètres du serveur proxy.](images/setupnetworksetup-4.png)

### Détails

Afin d’établir une connexion réseau, vous devrez indiquer un nom de script, ou le serveur proxy et les informations de port.

-   **Script de proxy :** fournissez l’adresse d’un script de proxy.
-   **Serveur proxy et port :** vous pouvez fournir l’adresse et le port du serveur proxy.

### Que se passe-t-il ?

Lorsque vous cliquez sur **Suivant**, l’appareil essaie de se connecter au serveur proxy. Si la connexion réussit, vous êtes dirigé vers la [page Configuration pour vous](#set-up-for-you).

Vous pouvez ignorer l’étape de connexion à un réseau en sélectionnant **Ignorer cette étape**. Vous allez être dirigé vers la [page Configuration pour vous](#set-up-for-you).

>[!NOTE]
>Si vous ignorez cette étape, l’appareil ne disposera pas d’une connexion réseau, et les fonctions nécessitant une connexion réseau sur votre Surface Hub ne fonctionneront pas, notamment la synchronisation du courrier électronique et du calendrier. Vous pouvez vous connecter à un réseau sans fil ultérieurement à l’aide de paramètres (voir [gestion de réseau sans fil](wireless-network-management-for-surface-hub.md)).

 

## <a href="" id="set-up-for-you"></a>Page Configuration pour vous


Cet écran est purement informatif et affiche les paramètres recommandés qui ont été activés par défaut.

![Image illustrant la page configuration pour vous.](images/setupsetupforyou.png)

### Détails

Vous devez lire cet écran et noter les services qui ont été activés par défaut. Au besoin, ils peuvent tous être modifiés à l’aide de l’application Paramètres, mais vous devez être conscient des effets d’une telle action. Consultez [Présentation du Surface Hub](intro-to-surface-hub.md) pour plus d’informations.

Une fois que vous avez terminé de passer en revue les paramètres, cliquez sur **Suivant** pour continuer.

### Que se passe-t-il ?

Les paramètres affichés sur la page ont déjà été appliqués et ne peuvent être modifiés avant la fin du programme de première utilisation.

## <a href="" id="device-account"></a>Page Compte d’appareil


Dans cette page, le Surface Hub demande des informations d’identification pour le compte d’appareil que vous avez configuré préalablement. (Voir [Créer et tester un compte d’appareil](create-and-test-a-device-account-surface-hub.md).) Le Surface Hub essaie de découvrir les différentes propriétés du compte et peut demander des informations supplémentaires sur une autre page, s’il n’y parvient pas.

>[!NOTE]
>Cette section ne traite pas des erreurs spécifiques qui peuvent se produire lors de la première utilisation. Consultez [Résoudre les problèmes liés au Surface Hub](troubleshoot-surface-hub.md) pour plus d’informations sur les erreurs.


![Image illustrant la page Entrez les informations de compte d’appareil.](images/setupdeviceacct.png)

### Détails

Utilisez un **nom d’utilisateur principal (UPN)** ou un **domaine\\nom d’utilisateur** en tant qu’identificateur de compte dans le premier champ d’entrée. Utilisez le format qui correspond à votre environnement, puis entrez le mot de passe.


|                      Environnement                      | Format requis pour le compte d’appareil |
|-------------------------------------------------------|------------------------------------|
|         Compte d’appareil hébergé uniquement en ligne         |        nom_utilisateur@domaine.com         |
|        Compte d’appareil hébergé uniquement sur site         |          DOMAINE\Nom d’utilisateur           |
| Compte d’appareil hébergé en ligne et sur site (hybride) |          DOMAINE\Nom d’utilisateur           |

Cliquez sur **Ignorer la configuration d’un compte d’appareil** pour passer l’étape de configuration d’un compte d’appareil. Toutefois, si vous ne configurez pas un compte d’appareil, l’appareil ne sera pas entièrement intégré à votre infrastructure. Par exemple, les utilisateurs ne pourront pas :

-   Afficher un calendrier de réunion sur l’écran de démarrage
-   Démarrer une réunion sur l’écran de démarrage
-   Envoyer par e-mail des tableaux blancs à partir de OneNote
-   Utiliser SkypeEntreprise pour les réunions

Si vous ignorez l’étape de configuration dans l’immédiat, vous pouvez ajouter un compte d’appareil ultérieurement à l’aide de l’application Paramètres.

Si vous cliquez sur **Ignorer la configuration d’un compte d’appareil**, l’appareil affiche une boîte de dialogue montrant ce qui se passera si l’appareil ne possède pas de compte d’appareil. Si vous choisissez **Oui, ignorer**, vous êtes dirigé vers la [page Nommer cet appareil](#name-this-device).

![Image illustrant le message le est affiché pour confirmer que vous voulez ignorer la création d’un compte d’appareil.](images/setupskipdeviceacct.png)

### Que se passe-t-il?

L’appareil utilisera le nom d’utilisateur principal ou l’option DOMAINE\\nom d’utilisateur et mot de passe du compte d’appareil pour effectuer les tâches suivantes:

-   Vérifier si le compte existe dans ActiveDirectory (AD) ou Azure ActiveDirectory (Azure AD):

    -   Si un nom d’utilisateur principal a été entré: l’appareil recherche le compte dans AzureAD.
    -   Si un DOMAINE\\nom d’utilisateur a été entré: l’appareil recherche le compte dans AD.
-   Rechercher la boîte aux lettres du compte dans le serveur MicrosoftExchange.
-   Rechercher l’adresse de protocole SIP (Session Initiation Protocol) pour le compte.
-   Extraire les attributs de nom d’affichage et d’alias du compte.

## <a href="" id="exchange-server"></a>Page Serveur Exchange


Cette page s’affichera uniquement en cas de problème. En règle générale, cela signifie que le compte d’appareil que vous avez fourni a été trouvé dans ActiveDirectory (AD) ou Azure ActiveDirectory (Azure AD), mais que le serveur Exchange pour le compte n’a pas été détecté.

![Image illustrant la page du serveur Exchange.](images/setupexchangeserver-01.png)

### Détails

Saisissez le nom du serveur Exchange où la boîte aux lettres du compte d’appareil est hébergée.

Cliquez sur **Ignorer la configuration de services Exchange** pour ignorer cette étape. Si vous le faites, les utilisateurs ne pourront pas :

-   Afficher un calendrier de réunion sur l’écran de démarrage.
-   Démarrer une réunion sur l’écran de démarrage.
-   Envoyer par e-mail des tableaux blancs à partir de OneNote.

Consultez [Présentation de Surface Hub](intro-to-surface-hub.md) pour des informations sur les dépendances de l’installation.

Vous pouvez activer les services Exchange pour un compte d’appareil ultérieurement à l’aide de l’application Paramètres.

Si vous cliquez sur **Ignorer la configuration de services Exchange**, l’appareil affichera une boîte de dialogue montrant ce qui se passera. Si vous choisissez **Oui, ignorer**, les services Exchange ne seront pas configurés.

![Image illustrant le message de confirmation qui s’affiche lorsque vous ignorez la configuration des services Exchange.](images/setupexchangeserver-02.png)

### Que se passe-t-il?

Le Surface Hub essaie de valider le compte d’appareil sur le serveur Exchange auquel vous accédez ici. Si le serveur Exchange peut être contacté et validé, le programme de première utilisation se poursuit.

Si vous choisissez d’ignorer la configuration de services Exchange, le Surface Hub cessera de rechercher le serveur Exchange, et aucun service Exchange (courrier et calendrier) ne sera activé.

## <a href="" id="exchange-policies"></a>Page Stratégies Exchange


Cette page s’affiche dans les situations suivantes :

-   Le compte d’appareil utilise une stratégie Exchange ActiveSync (EAS) dans laquelle la stratégie PasswordEnabled est définie sur 1.
-   Il n’existe aucune connexion à Exchange.
-   Exchange renvoie un code d’état indiquant une erreur. (Par exemple : le compte a été approvisionné pour un trop grand nombre d’appareils.)
-   Les protocoles pris en charge par Exchange ne sont pas pris en charge par le Surface Hub.
-   Exchange renvoie un fichierXML incorrect.

![Image illustrant la page de stratégies Exchange.](images/setupexchangepolicies.png)

### Détails

Cette page est purement informative, aucune saisie n’est nécessaire. Toutefois, deux options s’offrent à vous pour poursuivre : ignorer la suite ou réessayer la validation qui a provoqué l’erreur. Avant de décider de la meilleure option, lisez la section **Que se passe-t-il ?** ci-après. Vous pourrez peut-être résoudre le problème à un autre endroit avant de cliquer sur l’une des options.

-   **Cliquer ici pour continuer à utiliser des stratégies non prises en charge**: cliquez sur cette option pour continuer le programme de première utilisation. Le Surface Hub ne sera pas en mesure d’utiliser les services Exchange ou la synchronisation.
-   **Réessayer**: vérifiez à nouveau la stratégie sur le serveur Exchange.

### Que se passe-t-il ?

Le Surface Hub vérifie si la stratégie EAS du compte d’appareil a la propriété PasswordEnabled définie sur 0 (False). Si ce n’est pas le cas, le courrier et le calendrier ne peuvent pas être synchronisés et le Surface Hub ne peut utiliser aucun service Exchange. Vous pouvez utiliser vos outils de gestion Exchange à partir d’un PC pour vérifier que la stratégie PasswordEnabled du compte d’appareil est définie sur 0. Si ce n’est pas le cas, vous pouvez reconfigurer le compte et cliquer sur **Réessayer** ici.

Si la stratégie a déjà été configurée correctement, vérifiez que votre appareil est correctement connecté au réseau ou à Internet et qu’il peut contacter votre serveur Exchange, car cette page s’affichera également si le Surface Hub ne peut pas contacter le serveur Exchange.

Autre raison expliquant l’impossibilité d’atteindre Exchange : l’authentification basée sur les certificats. Vous pouvez vous retrouver sur cette page en raison de problèmes de certificat. Notez que si l’appareil affiche les codes d’erreur 0x80072F0D ou 0X800C0019, un certificat est requis. Étant donné que la mise en service est effectuée sur la première page du processus de première utilisation, vous devez désactiver les services Exchange en cliquant sur **Cliquer ici pour continuer à utiliser des stratégies non prises en charge**, puis installer les certificats appropriés par le biais de l’application Paramètres.

Si vous choisissez d’ignorer cette vérification, le Surface Hub cessera de rechercher le serveur Exchange et de valider les stratégies EAS, et aucun service Exchange ne sera activé. Consultez [Présentation de Surface Hub](intro-to-surface-hub.md) pour des informations sur les dépendances de l’installation.

## <a href="" id="name-this-device"></a>Page Nommer cet appareil


Cette page vous demande de fournir deuxnoms qui seront utilisés pour identifier le Surface Hub.

![Image illustrant la page Nommer cet appareil.](images/setupnamedevice.png)

### Détails

Si les valeurs par défaut affichées sont correctes, vous pouvez ensuite cliquer sur **Suivant** pour continuer. Sinon, saisissez des données dans l’une ou les deux zones de texte.

-   **Nom convivial :** c’est le nom que les utilisateurs voient lorsqu’ils souhaitent se connecter sans fil au Surface Hub.
-   **Nom de l’appareil :** peut être défini avec n’importe quel nom unique comme indiqué à l’écran.

Tant que ces deux noms respectent les exigences de longueur et n’utilisent pas de caractères non autorisés, le fait de cliquer sur **Suivant** vous dirige vers la page suivante, [Configurer des administrateurs pour cet appareil](#setup-admins).

### Que se passe-t-il ?

Le Surface Hub requiert deux noms pour l’appareil, par défaut :

-   **Nom convivial :** par défaut, le nom d’affichage du compte d’appareil
-   **Nom de l’appareil :** par défaut, l’alias du compte d’appareil

Bien que ces deux noms puissent être modifiés ultérieurement, gardez à l’esprit que :

-   Le nom convivial doit être identifiable et différent afin que les utilisateurs puissent distinguer un Surface Hub d’un autre lorsqu’ils essaient de se connecter sans fil.
-   Si vous décidez de joindre l’appareil au domaine, le nom de l’appareil ne doit pas être identique à celui de tout autre appareil sur le domaine Active Directory du compte. L’appareil ne peut pas joindre le domaine s’il utilise le même nom qu’un autre appareil joint au domaine.

>[!NOTE]
>Si vous souhaitez activer [Miracast over Infrastructure](miracast-over-infrastructure.md), le nom de l’appareil doit être détectable via DNS. Vous pouvez y parvenir en autorisant votre SurfaceHub à s’inscrire automatiquement via le DNS dynamique ou en créant manuellement un enregistrementA ouAAAA pour le nom d’appareil du Surface Hub.

## <a href="" id="setup-admins"></a>Page Configurer des administrateurs pour cet appareil


Sur cette page, à partir de plusieurs options, vous choisirez la façon dont vous souhaitez configurer des comptes administrateur pour gérer votre appareil localement.

Dans la mesure où chaque Surface Hub peut être utilisé par un nombre illimité d’employés authentifiés, les paramètres sont verrouillés afin qu’ils ne puissent pas être modifiés d’une session à l’autre. Seuls les administrateurs peuvent configurer les paramètres sur l’appareil et, sur cette page, vous choisissez le type d’administrateur disposant de ce privilège.

>[!NOTE]
>L’objectif de cette page est principalement de déterminer qui peut configurer l’appareil à partir de l’interface utilisateur de l’appareil, autrement dit, qui peut réellement visiter un appareil, se connecter, ouvrir l’application Paramètres et modifier les paramètres.

 

![Image illustrant la page Configurer des administrateurs pour cet appareil.](images/setupsetupadmins.png)

### Détails

Choisissez l’une des trois options disponibles :

-   **Utiliser Microsoft Azure Active Directory**
-   **Utiliser des services de domaine Active Directory**
-   **Utiliser un administrateur local**

### Que se passe-t-il ?

Voici ce qui se passe lorsque vous choisissez une option.

-   **Utiliser Microsoft Azure Active Directory**

    Cliquer sur cette option vous permet de joindre l’appareil à Azure AD. Une fois que vous cliquez sur **Suivant**, l’appareil redémarre pour appliquer certains paramètres. Ensuite, vous êtes dirigé vers la page [Utiliser Microsoft Azure Active Directory](#use-microsoft-azure) et invité à saisir des informations d’identification qui peuvent vous permettre de joindre Azure AD. Les membres du rôle administrateur général Azure de l’organisation jointe pourront utiliser l’application paramètres. Les utilisateurs qui sont spécifiquement autorisés dépendent de votre abonnement Azure AD et de la façon dont vous avez configuré les paramètres pour votre organisation Azure AD.
    
    > [!IMPORTANT]
    > Les administrateurs ajoutés au rôle Administrateurs d’appareils Azure une fois que vous avez rejoint l’appareil sur Azure AD ne seront pas en mesure d’utiliser l’application paramètres.
    >
    > Si vous joignez le Surface Hub à AzureAD lors de la configuration de première utilisation, l’authentification unique (SSO) pour les applications Office ne fonctionnera pas correctement. Les utilisateurs devront se connecter à chaque application Office individuellement.

-   **Utiliser les services de domaine ActiveDirectory**

    Cliquez sur cette option pour joindre l’appareil à AD. Une fois que vous cliquez sur **Suivant**, vous êtes dirigé vers la page [Utiliser des services de domaine Active Directory](#use-active-directory) et invité à saisir des informations d’identification qui vous permettent de joindre le domaine spécifié. Une fois la jonction effectuée, vous pouvez choisir un groupe de sécurité du domaine joint ; les utilisateurs de ce groupe de sécurité sont en mesure d’utiliser l’application Paramètres.

-   **Utiliser un administrateur local**

    Le choix de cette option vous autorise à créer un seul administrateur local. Cet administrateur ne sera soutenu par aucun service de répertoire. Nous vous recommandons de choisir uniquement cette option si l’appareil n’a pas accès à Azure AD ou à AD. Une fois que vous avez créé le nom d’utilisateur et le mot de passe d’un administrateur sur la page [Utiliser un administrateur local](#use-a-local-admin) , vous devez entrer à nouveau ces mêmes informations d’identification à chaque fois que vous ouvrez l’application Paramètres.

    Notez qu’un administrateur local doit disposer d’un accès physique au Surface Hub pour se connecter.

>[!NOTE]
>Une fois que vous aurez terminé ce processus, vous ne serez pas en mesure de modifier l’option d’administration de l’appareil, sauf si vous le réinitialisez.

 

### <a href="" id="use-microsoft-azure"></a>Utiliser Microsoft Azure Active Directory

Si vous avez décidé de joindre votre Surface Hub à Azure Active Directory (Azure AD), vous verrez cette page **Étapes suivantes** . Lisez-la et cliquez sur **Suivant** pour accéder à la **page Vous connecter**.

Joindre Azure AD présente deux avantages principaux :

1.  Certains employés de votre entreprise seront en mesure d’accéder à l’appareil en tant qu’administrateurs, de démarrer l’application Paramètres et de configurer l’appareil. Les utilisateurs disposant d’autorisations d’administration seront définis dans votre abonnement Azure AD.

2.  Si votre AzureAD est connecté à une solution de gestion des périphériques mobiles (GPM), l’appareil s’inscrira avec cette solution GPM afin que vous puissiez appliquer les stratégies et la configuration.

    ![Image illustrant le message affiché lorsque vous joignez votre Surface Hub à Azure ActiveDirectory.](images/setupjoiningazuread-1.png)

### Détails

Les informations suivantes sont nécessaires :

-   **Nom d’utilisateur principal :** le nom de l’utilisateur principal du compte qui peut joindre Azure AD.
-   **Mot de passe:** mot de passe du compte que vous utilisez pour joindre AzureAD.

![Image illustrant des informations de connexion du compte.](images/setupjoiningazuread-2.png)

Si vous arrivez à ce stade et que vous n’avez pas d’informations d’identification valides pour un compte AzureAD, l’appareil vous permettra de continuer en créant un compte administrateur local. Cliquez sur **Configurer plutôt Windows à l’aide d’un compte local**.

![Image illustrant la page Configurer un compte administrateur.](images/setupjoiningazuread-3.png)

### Que se passe-t-il?

Une fois que vous saisissez des informations d’identification de compte Azure AD valides, l’appareil essaie de joindre l’organisation Azure AD associée. Si cette tentative aboutit, l’appareil configure les employés de cette organisation afin qu’ils soient les administrateurs locaux sur l’appareil. Si votre client Azure AD a été configuré pour cela, l’appareil s’inscrira également à GPM.

### <a href="" id="use-active-directory"></a>Utiliser des services de domaine Active Directory

Cette page vous demande des informations d’identification pour joindre un domaine de sorte que le Surface Hub puisse configurer un groupe de sécurité en tant qu’administrateurs de l’appareil.

Une fois que l’appareil a été joint au domaine, vous devez spécifier un groupe de sécurité du domaine que vous avez joint. Ce groupe de sécurité sera configuré en tant qu’administrateur sur le Surface Hub, et tous les utilisateurs du groupe de sécurité pourront entrer leurs informations d’identification de domaine pour accéder à Paramètres.

![Image illustrant la page Configurer des administrateurs avec la jonction de domaine.](images/setupdomainjoin.png)

### Détails

Les informations suivantes sont nécessaires :

-   **Domaine :** il s’agit du nom de domaine complet du domaine que vous souhaitez joindre. Un groupe de sécurité de ce domaine peut être utilisé pour gérer l’appareil.
-   **Nom d’utilisateur:** le nom d’utilisateur d’un compte disposant d’autorisations suffisantes pour joindre le domaine spécifié. 
-   **Mot de passe:** le mot de passe du compte.

Une fois les informations d’identification vérifiées, vous devez saisir un nom de groupe de sécurité. Cette information est obligatoire.

![Image illustrant la page Entrer un groupe de sécurité.](images/setupsecuritygroup-1.png)

### Que se passe-t-il?

En utilisant le domaine fourni, les informations d’identification de compte issues de la [page Utiliser des services de domaine Active Directory](#use-active-directory) et le nom de l’appareil issu de la page [Nommer cet appareil](#name-this-device) , le Surface Hub tentera de joindre le domaine. Si la jonction réussit, le programme de première utilisation continue et vous demandera un groupe de sécurité. Si la jonction échoue, le programme de première utilisation s’interrompt et vous invitera à modifier les informations fournies.

Si la jonction réussit, vous verrez la page **Entrer un groupe de sécurité** . Lorsque vous cliquez sur le bouton **Sélectionner** sur cette page, l’appareil recherche le groupe de sécurité spécifié sur votre domaine. S’il le trouve, le groupe fait l’objet d’une vérification. Cliquez sur **Terminer** pour terminer le processus de première utilisation.

>[!NOTE]
>Si votre domaine joint le Surface Hub, vous ne pouvez pas annuler la jonction de l’appareil sans le réinitialiser.

 

### Utiliser un administrateur local

Si vous décidez de ne pas utiliser AzureActive Directory (AzureAD) ou ActiveDirectory (AD) pour gérer le Surface Hub, vous devrez créer un compte administrateur local.

![Image illustrant la page Configurer un compte administrateur pour un administrateur local.](images/setuplocaladmin.png)

### Détails

Les informations suivantes sont nécessaires :

-   **Nom d’utilisateur :** C’est le nom d’utilisateur du compte administrateur local qui est créé pour ce Surface Hub.
-   **Mot de passe :** il s’agit du mot de passe du compte d’appareil.
-   **Entrer à nouveau le mot de passe :** vérifie le mot de passe saisi dans le champ précédent.

### Que se passe-t-il ?

Cette page tente de créer un compte administrateur en utilisant les informations d’identification que vous saisissez ici. Si la tentative réussit, le processus de première utilisation est terminé. Si ce n’est pas le cas, vous êtes invité à fournir des informations d’identification différentes.

## <a href="" id="update-surface-hub"></a>Mettre à jour le Surface Hub


>[!IMPORTANT]
>Avant d’effectuer les mises à jour, veillez à lire [Enregistrer votre clé BitLocker](save-bitlocker-key-surface-hub.md) afin de vous assurer de disposer d’une sauvegarde de la clé.

 

Pour recevoir les fonctionnalités et correctifs les plus récents, mettez à jour votre Surface Hub dès que vous avez terminé toutes les étapes précédentes de première utilisation.

1.  Assurez-vous que l’appareil a accès aux serveurs Windows Update. 
2.  Ouvrez Paramètres, puis cliquez successivement sur **Mise à jour et sécurité**, **Windows Update** et **Rechercher les mises à jour**.
3.  Si des mises à jour sont disponibles, elles seront téléchargées. Une fois que le téléchargement est terminé, cliquez sur le bouton **Mettre à jour à maintenant** pour installer les mises à jour.
4.  Suivez les instructions à l’écran une fois que les mises à jour installées. Vous devrez peut-être redémarrer l’appareil.

 

 





