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
# <span data-ttu-id="c465d-104">Configurer l’authentification par mot de passe sur surface Hub</span><span class="sxs-lookup"><span data-stu-id="c465d-104">Configure passwordless sign-in on Surface Hub</span></span>

 
<span data-ttu-id="c465d-105">La connexion à un mot de passe simplifie l’accès à vos applications, réunions et fichiers.</span><span class="sxs-lookup"><span data-stu-id="c465d-105">Passwordless sign-in simplifies access to your apps, meetings, and files.</span></span> <span data-ttu-id="c465d-106">Surface Hub prend en charge la connexion à l’aide de l’application Microsoft Authenticator et des clés de sécurité FIDO2 fournies par votre organisation.</span><span class="sxs-lookup"><span data-stu-id="c465d-106">Surface Hub supports signing in using the Microsoft Authenticator app and FIDO2 security keys provided by your organization.</span></span>

<span data-ttu-id="c465d-107">**Important:** Ce contenu est destiné aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="c465d-107">**Important:** This content is intended for users.</span></span> <span data-ttu-id="c465d-108">Pour pouvoir utiliser la connexion à l’aide d’un mot de passe, votre administrateur doit activer l’authentification par mot de passe pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="c465d-108">To use passwordless sign-in, your IT admin must enable passwordless authentication for your organization.</span></span> <span data-ttu-id="c465d-109">Pour plus d’informations, voir:</span><span class="sxs-lookup"><span data-stu-id="c465d-109">For more information, see:</span></span>

- [<span data-ttu-id="c465d-110">Activer la connexion téléphonique pour les mots de passe</span><span class="sxs-lookup"><span data-stu-id="c465d-110">Enable passwordless phone sign-in</span></span>](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-phone)
- [<span data-ttu-id="c465d-111">Activer la connexion à la clé de sécurité en tant que mot de passe</span><span class="sxs-lookup"><span data-stu-id="c465d-111">Enable passwordless security key sign-in</span></span>](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key)


## <span data-ttu-id="c465d-112">Configurer la connexion à l’aide de l’application Microsoft Authenticator</span><span class="sxs-lookup"><span data-stu-id="c465d-112">Configure sign-in using Microsoft Authenticator app</span></span>

<span data-ttu-id="c465d-113">**Remarque:** À partir de la mise à jour de l’équipe 2020 de Windows 10, les utilisateurs peuvent utiliser leurs alias de messagerie préférés dans Azure AD, ainsi que leur nom d’utilisateur principal (UPN), pour se connecter à l’aide de Microsoft Authenticator.</span><span class="sxs-lookup"><span data-stu-id="c465d-113">**Note:** Starting with Windows 10 Team 2020 Update, users can use their preferred email aliases in Azure AD, as well as their User Principal Name (UPN), to sign in using Microsoft Authenticator.</span></span> <span data-ttu-id="c465d-114">Par exemple, un utilisateur peut utiliser son alias préféré (John.Doe@contoso.com) ou son UPN (jdoe@contoso.com) pour se connecter.</span><span class="sxs-lookup"><span data-stu-id="c465d-114">For example, a user can use either their preferred alias (John.Doe@contoso.com) or their UPN (jdoe@contoso.com) to sign in.</span></span>
 
<span data-ttu-id="c465d-115">L’application Microsoft Authenticator vous permet de vous connecter à surface Hub à l’aide de votre appareil mobile.</span><span class="sxs-lookup"><span data-stu-id="c465d-115">The Microsoft Authenticator app helps you sign-in to Surface Hub using your mobile device.</span></span> <span data-ttu-id="c465d-116">Pour configurer la connexion à l’aide de Microsoft Authenticator:</span><span class="sxs-lookup"><span data-stu-id="c465d-116">To configure sign-in using Microsoft Authenticator:</span></span>


1. <span data-ttu-id="c465d-117">Sur votre appareil mobile, téléchargez l’application Microsoft Authenticator.</span><span class="sxs-lookup"><span data-stu-id="c465d-117">On your mobile device, download the Microsoft Authenticator app.</span></span>
    - <span data-ttu-id="c465d-118">Google Android: sur votre appareil Android, rendez-vous sur Google Play pour [Télécharger et installer l’application Microsoft Authenticator](https://app.adjust.com/e3rxkc_7lfdtm?fallback=https%3A%2F%2Fplay.google.com%2Fstore%2Fapps%2Fdetails%3Fid%3Dcom.azure.authenticator).</span><span class="sxs-lookup"><span data-stu-id="c465d-118">Google Android: On your Android device, go to Google Play to [download and install the Microsoft Authenticator app](https://app.adjust.com/e3rxkc_7lfdtm?fallback=https%3A%2F%2Fplay.google.com%2Fstore%2Fapps%2Fdetails%3Fid%3Dcom.azure.authenticator).</span></span>
    - <span data-ttu-id="c465d-119">Apple iOS: sur votre appareil iOS Apple, accédez à l’App Store pour [Télécharger et installer l’application Microsoft Authenticator](https://app.adjust.com/e3rxkc_7lfdtm?fallback=https%3A%2F%2Fitunes.apple.com%2Fus%2Fapp%2Fmicrosoft-authenticator%2Fid983156458).</span><span class="sxs-lookup"><span data-stu-id="c465d-119">Apple iOS: On your Apple iOS device, go to the App Store to [download and install the Microsoft Authenticator app](https://app.adjust.com/e3rxkc_7lfdtm?fallback=https%3A%2F%2Fitunes.apple.com%2Fus%2Fapp%2Fmicrosoft-authenticator%2Fid983156458).</span></span>
2. <span data-ttu-id="c465d-120">Sur votre PC, [configurez l’application Microsoft Authenticator à partir de la page des informations de sécurité](https://docs.microsoft.com/azure/active-directory/user-help/security-info-setup-auth-app#set-up-the-microsoft-authenticator-app-from-the-security-info-page) pour votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="c465d-120">On your PC, [setup the Microsoft Authenticator app from the Security info page](https://docs.microsoft.com/azure/active-directory/user-help/security-info-setup-auth-app#set-up-the-microsoft-authenticator-app-from-the-security-info-page) for your work or school account.</span></span>
3. <span data-ttu-id="c465d-121">À partir de l’application Microsoft Authenticator sur votre appareil mobile, [activez et utilisez la connexion téléphonique](https://docs.microsoft.com/azure/active-directory/user-help/user-help-auth-app-sign-in#turn-on-and-use-phone-sign-in-for-your-work-or-school-account) pour votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="c465d-121">From the Microsoft Authenticator app on your mobile device, [turn on and use phone sign-in](https://docs.microsoft.com/azure/active-directory/user-help/user-help-auth-app-sign-in#turn-on-and-use-phone-sign-in-for-your-work-or-school-account) for your work or school account.</span></span>

 
## <span data-ttu-id="c465d-122">Configurer la connexion à l’aide de clés de sécurité FIDO2</span><span class="sxs-lookup"><span data-stu-id="c465d-122">Configure sign-in using FIDO2 security keys</span></span>

> [!NOTE]
>  <span data-ttu-id="c465d-123">La connexion avec un mot de passe sur surface Hub à l’aide de clés de sécurité FIDO2 nécessite la mise à jour d’équipe 2020 de Windows 10.</span><span class="sxs-lookup"><span data-stu-id="c465d-123">Passwordless sign-in on Surface Hub using FIDO2 security keys requires the Windows 10 Team 2020 Update.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c465d-124">Surface Hub ne prend en charge que les clés de sécurité USB.</span><span class="sxs-lookup"><span data-stu-id="c465d-124">Surface Hub only supports USB security keys.</span></span>
 
<span data-ttu-id="c465d-125">Vous pouvez également vous connecter à surface Hub à l’aide d’une clé de sécurité FIDO2 fournie par votre organisation.</span><span class="sxs-lookup"><span data-stu-id="c465d-125">You can also sign into Surface Hub using a FIDO2 security key provided by your organization.</span></span> 

### <span data-ttu-id="c465d-126">Pour configurer la connexion à l’aide d’une clé de sécurité:</span><span class="sxs-lookup"><span data-stu-id="c465d-126">To configure sign-in using a security key:</span></span>


1. <span data-ttu-id="c465d-127">Sur votre PC, accédez à la [https://myprofile.microsoft.com/](https://myprofile.microsoft.com/) page et connectez-vous à votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="c465d-127">On your PC, go to your [https://myprofile.microsoft.com/](https://myprofile.microsoft.com/) page and sign in to your work or school account.</span></span>
2. <span data-ttu-id="c465d-128">Dans le volet de navigation gauche, sélectionnez **Security Info** ou cliquez sur le lien dans le bloc d' **informations de sécurité** , puis sélectionnez **Ajouter une méthode** à partir de la page des informations de **sécurité** .</span><span class="sxs-lookup"><span data-stu-id="c465d-128">Select **Security info** from the left navigation pane or from the link in the **Security info** block, and then select **Add method** from the **Security info** page.</span></span>
3. <span data-ttu-id="c465d-129">Dans la page **Ajouter une méthode** , sélectionnez **clé de sécurité** dans la liste déroulante, puis sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="c465d-129">On the **Add a method** page, select **Security key** from the drop-down list, and then select **Add**.</span></span>
4. <span data-ttu-id="c465d-130">Dans la page **clé de sécurité** , sélectionnez **périphérique USB**.</span><span class="sxs-lookup"><span data-stu-id="c465d-130">On the **Security key** page, choose **USB device**.</span></span>
5. <span data-ttu-id="c465d-131">Préparez votre clé de sécurité, puis sélectionnez **suivant**.</span><span class="sxs-lookup"><span data-stu-id="c465d-131">Have your security key ready and select **Next**.</span></span>
6. <span data-ttu-id="c465d-132">Dans la boîte de dialogue qui s’affiche, suivez les instructions pour insérer la clé de sécurité, créer ou entrer un code confidentiel et effectuer le mouvement (biométrique ou entrée tactile) requis.</span><span class="sxs-lookup"><span data-stu-id="c465d-132">In the dialog box that appears, follow the instructions to insert the security key, create or enter a PIN, and perform the required gesture (either biometric or touch).</span></span>
7. <span data-ttu-id="c465d-133">Dans la page **clé de sécurité** , attribuez un nom à votre clé de sécurité, puis sélectionnez **suivant**.</span><span class="sxs-lookup"><span data-stu-id="c465d-133">On the **Security key** page, give your security key a name, then select **Next**.</span></span>
8. <span data-ttu-id="c465d-134">Sélectionnez **terminé** pour terminer le processus.</span><span class="sxs-lookup"><span data-stu-id="c465d-134">Select **Done** to complete the process.</span></span>

## <span data-ttu-id="c465d-135">Se connecter à surface Hub</span><span class="sxs-lookup"><span data-stu-id="c465d-135">Sign-in to Surface Hub</span></span>

<span data-ttu-id="c465d-136">Une fois que vous avez configuré la connexion en utilisant un mot de passe, vous pouvez l’utiliser pour accéder facilement à vos applications, réunions et fichiers sur surface Hub:</span><span class="sxs-lookup"><span data-stu-id="c465d-136">Once you've configured passwordless sign-in, you can use it to make it easier to access your apps, meetings, and files on the Surface Hub:</span></span>

- <span data-ttu-id="c465d-137">Participez rapidement à vos réunions et ouvrez des fichiers Microsoft 365 récents.</span><span class="sxs-lookup"><span data-stu-id="c465d-137">Quickly join your meetings and open recent Microsoft 365 files.</span></span> <span data-ttu-id="c465d-138">Pour plus d’informations, consultez [**se connecter pour afficher vos réunions et vos fichiers**](https://support.microsoft.com/help/4506480/sign-in-to-see-your-meetings-and-files-on-surface-hub).</span><span class="sxs-lookup"><span data-stu-id="c465d-138">For more information, see [**Sign in to see your meetings and files**](https://support.microsoft.com/help/4506480/sign-in-to-see-your-meetings-and-files-on-surface-hub).</span></span>
- <span data-ttu-id="c465d-139">Connectez-vous rapidement aux applications Microsoft telles que le tableau blanc, PowerPoint, Word, Excel, OneDrive et Power BI.</span><span class="sxs-lookup"><span data-stu-id="c465d-139">Quickly sign in to Microsoft apps like Whiteboard, PowerPoint, Word, Excel, OneDrive, and Power BI.</span></span>
- <span data-ttu-id="c465d-140">Connectez-vous rapidement à votre nouveau Microsoft Edge pour accéder à vos favoris et vos préférences de navigation.</span><span class="sxs-lookup"><span data-stu-id="c465d-140">Quickly sign in to the new Microsoft Edge to access your favorites and browsing preferences.</span></span> <span data-ttu-id="c465d-141">Pour plus d’informations, voir [installer et configurer le nouveau Microsoft Edge](surface-hub-install-chromium-edge.md).</span><span class="sxs-lookup"><span data-stu-id="c465d-141">For more information, see [Install and configure the new Microsoft Edge](surface-hub-install-chromium-edge.md).</span></span>
- <span data-ttu-id="c465d-142">Après vous être connecté à surface Hub, vous pouvez utiliser d’autres applications sans avoir à vous reconnecter tant que vous n’avez pas sélectionné l’option **arrêter la session**.</span><span class="sxs-lookup"><span data-stu-id="c465d-142">Once you've signed into Surface Hub, you can use other apps without having to sign in again until you select **End session**.</span></span> <span data-ttu-id="c465d-143">La sélection de l’option arrêt de la **session** entraîne la suppression de vos informations d’identification, de vos fichiers et de vos données personnelles sur l’appareil.</span><span class="sxs-lookup"><span data-stu-id="c465d-143">Selecting **End session** deletes your credentials, files, and personal data from the device.</span></span> <span data-ttu-id="c465d-144">Pour plus d’informations, consultez la section [terminer une session](finishing-your-surface-hub-meeting.md).</span><span class="sxs-lookup"><span data-stu-id="c465d-144">For more information, see [End session](finishing-your-surface-hub-meeting.md).</span></span>


## <span data-ttu-id="c465d-145">En savoir plus</span><span class="sxs-lookup"><span data-stu-id="c465d-145">Learn more</span></span>

- [<span data-ttu-id="c465d-146">Options d’authentification par mot de passe d’Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="c465d-146">Passwordless authentication options for Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/authentication/concept-authentication-passwordless)
- [<span data-ttu-id="c465d-147">Connexion sans mot de passe avec l’application Microsoft Authenticator</span><span class="sxs-lookup"><span data-stu-id="c465d-147">Passwordless sign-in with the Microsoft Authenticator app</span></span>](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-phone)
- [<span data-ttu-id="c465d-148">Connexion en utilisant le mot de passe à l’aide de clés de sécurité FIDO2</span><span class="sxs-lookup"><span data-stu-id="c465d-148">Passwordless sign-in using FIDO2 security keys</span></span>](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key#user-registration-and-management-of-fido2-security-keys)

