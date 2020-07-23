---
title: Configurer une connexion sans mot de passe sur surface Hub
description: Découvrez comment simplifier la connexion à surface Hub.
keywords: séparer les valeurs par des virgules
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 07/21/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 0eaa48200be9ff3c8087530b6dfddeb9aa4620d8
ms.sourcegitcommit: 8738f44f2f4c86e3a45e9fbcbe6469388fc15924
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/22/2020
ms.locfileid: "10893046"
---
# Configurer l’authentification par mot de passe sur surface Hub

 
La connexion à un mot de passe simplifie l’accès à vos applications, réunions et fichiers. Surface Hub prend en charge la connexion à l’aide de l’application Microsoft Authenticator et des clés de sécurité FIDO2 fournies par votre organisation.

**Important:** Ce contenu est destiné aux utilisateurs. Pour pouvoir utiliser la connexion à l’aide d’un mot de passe, votre administrateur doit activer l’authentification par mot de passe pour votre organisation. Pour plus d’informations, voir:

- [Activer la connexion téléphonique pour les mots de passe](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-phone)
- [Activer la connexion à la clé de sécurité en tant que mot de passe](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key)


## Configurer la connexion à l’aide de l’application Microsoft Authenticator

**Remarque:** À partir de la mise à jour de l’équipe 2020 de Windows 10, les utilisateurs peuvent utiliser leurs alias de messagerie préférés dans Azure AD, ainsi que leur nom d’utilisateur principal (UPN), pour se connecter à l’aide de Microsoft Authenticator. Par exemple, un utilisateur peut utiliser son alias préféré (John.Doe@contoso.com) ou son UPN (jdoe@contoso.com) pour se connecter.
 
L’application Microsoft Authenticator vous permet de vous connecter à surface Hub à l’aide de votre appareil mobile. Pour configurer la connexion à l’aide de Microsoft Authenticator:


1. Sur votre appareil mobile, téléchargez l’application Microsoft Authenticator.
    - Google Android: sur votre appareil Android, rendez-vous sur Google Play pour [Télécharger et installer l’application Microsoft Authenticator](https://app.adjust.com/e3rxkc_7lfdtm?fallback=https%3A%2F%2Fplay.google.com%2Fstore%2Fapps%2Fdetails%3Fid%3Dcom.azure.authenticator).
    - Apple iOS: sur votre appareil iOS Apple, accédez à l’App Store pour [Télécharger et installer l’application Microsoft Authenticator](https://app.adjust.com/e3rxkc_7lfdtm?fallback=https%3A%2F%2Fitunes.apple.com%2Fus%2Fapp%2Fmicrosoft-authenticator%2Fid983156458).
2. Sur votre PC, [configurez l’application Microsoft Authenticator à partir de la page des informations de sécurité](https://docs.microsoft.com/azure/active-directory/user-help/security-info-setup-auth-app#set-up-the-microsoft-authenticator-app-from-the-security-info-page) pour votre compte professionnel ou scolaire.
3. À partir de l’application Microsoft Authenticator sur votre appareil mobile, [activez et utilisez la connexion téléphonique](https://docs.microsoft.com/azure/active-directory/user-help/user-help-auth-app-sign-in#turn-on-and-use-phone-sign-in-for-your-work-or-school-account) pour votre compte professionnel ou scolaire.

 
## Configurer la connexion à l’aide de clés de sécurité FIDO2

> [!NOTE]
>  La connexion avec un mot de passe sur surface Hub à l’aide de clés de sécurité FIDO2 nécessite la mise à jour d’équipe 2020 de Windows 10.

> [!IMPORTANT]
> Surface Hub ne prend en charge que les clés de sécurité USB.
 
Vous pouvez également vous connecter à surface Hub à l’aide d’une clé de sécurité FIDO2 fournie par votre organisation. 

### Pour configurer la connexion à l’aide d’une clé de sécurité:


1. Sur votre PC, accédez à la [https://myprofile.microsoft.com/](https://myprofile.microsoft.com/) page et connectez-vous à votre compte professionnel ou scolaire.
2. Dans le volet de navigation gauche, sélectionnez **Security Info** ou cliquez sur le lien dans le bloc d' **informations de sécurité** , puis sélectionnez **Ajouter une méthode** à partir de la page des informations de **sécurité** .
3. Dans la page **Ajouter une méthode** , sélectionnez **clé de sécurité** dans la liste déroulante, puis sélectionnez **Ajouter**.
4. Dans la page **clé de sécurité** , sélectionnez **périphérique USB**.
5. Préparez votre clé de sécurité, puis sélectionnez **suivant**.
6. Dans la boîte de dialogue qui s’affiche, suivez les instructions pour insérer la clé de sécurité, créer ou entrer un code confidentiel et effectuer le mouvement (biométrique ou entrée tactile) requis.
7. Dans la page **clé de sécurité** , attribuez un nom à votre clé de sécurité, puis sélectionnez **suivant**.
8. Sélectionnez **terminé** pour terminer le processus.

## Se connecter à surface Hub

Une fois que vous avez configuré la connexion en utilisant un mot de passe, vous pouvez l’utiliser pour accéder facilement à vos applications, réunions et fichiers sur surface Hub:

- Participez rapidement à vos réunions et ouvrez des fichiers Microsoft 365 récents. Pour plus d’informations, consultez [**se connecter pour afficher vos réunions et vos fichiers**](https://support.microsoft.com/help/4506480/sign-in-to-see-your-meetings-and-files-on-surface-hub).
- Connectez-vous rapidement aux applications Microsoft telles que le tableau blanc, PowerPoint, Word, Excel, OneDrive et Power BI.
- Connectez-vous rapidement à votre nouveau Microsoft Edge pour accéder à vos favoris et vos préférences de navigation. Pour plus d’informations, voir [installer et configurer le nouveau Microsoft Edge](surface-hub-install-chromium-edge.md).
- Après vous être connecté à surface Hub, vous pouvez utiliser d’autres applications sans avoir à vous reconnecter tant que vous n’avez pas sélectionné l’option **arrêter la session**. La sélection de l’option arrêt de la **session** entraîne la suppression de vos informations d’identification, de vos fichiers et de vos données personnelles sur l’appareil. Pour plus d’informations, consultez la section [terminer une session](finishing-your-surface-hub-meeting.md).


## En savoir plus

- [Options d’authentification par mot de passe d’Azure Active Directory](https://docs.microsoft.com/azure/active-directory/authentication/concept-authentication-passwordless)
- [Connexion sans mot de passe avec l’application Microsoft Authenticator](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-phone)
- [Connexion en utilisant le mot de passe à l’aide de clés de sécurité FIDO2](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key#user-registration-and-management-of-fido2-security-keys)

