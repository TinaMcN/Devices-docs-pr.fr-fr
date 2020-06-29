---
title: Se connecter à Surface Hub avec MicrosoftAuthenticator
description: Utilisez MicrosoftAuthenticator sur votre appareil mobile pour vous connecter à Surface Hub.
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 08/28/2017
ms.reviewer: ''
manager: laurawi
localizationpriority: medium
ms.openlocfilehash: 11768488d2ef7509af6a592b9e4ac945a7e35650
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832958"
---
# Se connecter à Surface Hub avec MicrosoftAuthenticator

Les membres de votre organisation peuvent se connecter à un Surface Hub sans mot de passe à l’aide de l’application MicrosoftAuthenticator, disponible sur iOS et Android.

## Conditions préalables pour l’organisation

Pour permettre aux utilisateurs de votre organisation de se connecter à Surface Hub avec leurs téléphones et autres appareils au lieu d’un mot de passe, vous devez vous assurer que votre organisation remplit ces conditions préalables: 

- Votre organisation doit être une organisation hybride ou Cloud uniquement, appuyée sur Azure ActiveDirectory (AD Azure). Pour plus d’informations, voir [Qu'est-ce que Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/active-directory-whatis).

- Assurez-vous de disposer au moins un abonnement Office365E3. 

- [Configurer l'authentification multifacteur](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-mfasettings). Vérifiez que **Notification via application mobile** est sélectionné. 

    ![Options de l'authentification multifacteur](images/mfa-options.png)

- Activez l’hébergement de contenu sur Azure AD services, tel qu’Office, SharePoint, etc. 

- Le Surface Hub doit exécuter Windows10, version1703 ou ultérieure.

- Le Surface Hub est configuré avec un compte local ou de domaine joint.

Actuellement, vous ne pouvez pas utiliser MicrosoftAuthenticator pour vous connecter à des Surface Hub qui sont joints à AzureAD.

## Conditions préalables des utilisateurs

- Un téléphone Android avec la version 6.0 ou ultérieure, ou un iPhone ou un iPad avec iOS9 ou une version ultérieure 

- La version la plus récente de l’application MicrosoftAuthenticator issue du magasin d’applications approprié

    >[!NOTE]
    >Sur iOS, la version de l’application doit être égale ou ultérieure à5.4.0.
    >
    >L’application MicrosoftAuthenticator sur les téléphones qui exécutent un système d’exploitation Windows ne peut pas être utilisée pour se connecter à Surface Hub.

- Code secret ou écran de verrouillage activé sur votre appareil.

- Une adresse de messagerie SMTP standard (exemple: joe@contoso.com). Les adresses non standard ou les adresses de messagerie de redirection vers un microsite SMTP (exemple: prénom.nom@contoso.com) ne fonctionnent pas actuellement.

## Comment utiliser l’application Microsoft Authenticator

>[!NOTE]
>Si le Portail d’entreprise est installé sur votre appareil Android, désinstallez-le avant de configurer MicrosoftAuthenticator. Quand vous aurez configuré l'application, vous pourrez réinstaller le Portail d’entreprise.
>
>Si vous avez déjà configuré MicrosoftAuthenticator sur votre téléphone et inscrit votre appareil, accédez aux instructions de connexion.

1. Ajoutez votre compte professionnel ou scolaire à MicrosoftAuthenticator pour Multi-Factor Authentication. Vous aurez besoin d’un code QR fourni par votre service informatique. Pour plus d’aide, consultez [Prise en main de l’application MicrosoftAuthenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to).
2. Accédez à **Paramètres** et enregistrez votre appareil.
3. Revenez à la page des comptes et choisissez **Activer la connexion par téléphone** dans le menu déroulant du compte.

## Comment se connecter à Surface Hub pendant une réunion

1. Une fois que vous avez configuré une réunion, accédez au Surface Hub et sélectionnez **Se connecter pour voir vos réunions et vos fichiers**.

    >[!NOTE]
    >Si vous ne savez pas comment programmer une réunion sur un Surface Hub, voir [Programmer une réunion sur Surface Hub](https://support.microsoft.com/help/17325/surfacehub-schedulemeeting).

    ![Capture d’écran de l'option de connexion sur Surface Hub](images/sign-in.png)

2. Vous verrez une liste des personnes invitées à la réunion. Sélectionnez vous-même (ou la personne qui souhaite se connecter – assurez-vous que cette personne a effectué les étapes de configuration de son appareil avant la réunion), puis sélectionnez **Continuer**.

    ![Capture d’écran de la liste des participants à une réunion](images/attendees.png)

    Vous verrez un code sur le Surface Hub.

    ![Capture d’écran du code pour approuver la connexion](images/approve-signin.png)

3. Pour approuver la connexion, ouvrez l’application Authenticator, entrez le code à quatre chiffres qui s’affiche sur le Surface Hub et sélectionnez **Approuver**. Vous devrez entrer le code PIN ou utiliser votre empreinte digitale pour terminer la connexion. 

    ![Capture d’écran de l’écran Approuver la connexion dans MicrosoftAuthenticator](images/approve-signin2.png)

Vous pouvez désormais accéder à tous les fichiers par l'intermédiaire de l’application OneDrive.