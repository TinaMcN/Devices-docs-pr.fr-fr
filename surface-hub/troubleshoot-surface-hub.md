---
title: Résoudre les problèmes liés au MicrosoftSurfaceHub
description: Résolvez les problèmes courants, notamment les problèmes d’installation et les erreurs ExchangeActiveSync.
ms.assetid: CF58F74D-8077-48C3-981E-FCFDCA34B34A
ms.reviewer: ''
manager: laurawi
keywords: Résolvez les problèmes courants, notamment les problèmes d’installation et les erreurs ExchangeActiveSync.
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 03/16/2018
ms.localizationpriority: medium
ms.openlocfilehash: fe87c56474a05152f991a5b63f6abf0cf05e8b03
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832687"
---
# <span data-ttu-id="64375-104">Résoudre les problèmes liés au Microsoft Surface Hub</span><span class="sxs-lookup"><span data-stu-id="64375-104">Troubleshoot Microsoft Surface Hub</span></span>


<span data-ttu-id="64375-105">Résolvez les problèmes courants, notamment les problèmes d’installation et les erreurs ExchangeActiveSync.</span><span class="sxs-lookup"><span data-stu-id="64375-105">Troubleshoot common problems, including setup issues, Exchange ActiveSync errors.</span></span>

<span data-ttu-id="64375-106">L’[outil de diagnostic du matériel Surface Hub](https://www.microsoft.com/store/p/surface-hub-hardware-diagnostic/9nblggh51f2g?rtc=1&activetab=pivot%3aoverviewtab) contient des tests interactifs qui permettent de vérifier si les fonctionnalités essentielles de votre Hub correspondent aux résultats attendus.</span><span class="sxs-lookup"><span data-stu-id="64375-106">The [Surface Hub Hardware Diagnostic tool](https://www.microsoft.com/store/p/surface-hub-hardware-diagnostic/9nblggh51f2g?rtc=1&activetab=pivot%3aoverviewtab) contains interactive tests which allow you to confirm essential functionality of your Hub is working as expected.</span></span> <span data-ttu-id="64375-107">En plus des tests du matériel, le diagnostic permet de tester le compte de ressource pour vérifier qu’il est configuré correctement pour votre environnement.</span><span class="sxs-lookup"><span data-stu-id="64375-107">In addition to testing hardware, the diagnostic can test the resource account to verify that it is configured properly for your environment.</span></span> <span data-ttu-id="64375-108">Si des problèmes surviennent, les résultats peuvent être enregistrés et partagés avec l’équipe du Support Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="64375-108">If problems are encountered, results can be saved and shared with the Surface Hub Support Team.</span></span> <span data-ttu-id="64375-109">Pour plus d’informations sur l’utilisation, consultez [Utilisation de l’outil de diagnostic du matériel Surface Hub pour tester un compte d’appareil](https://support.microsoft.com/help/4077574/using-the-surface-hub-hardware-diagnostic-tool-to-test-a-device-accoun).</span><span class="sxs-lookup"><span data-stu-id="64375-109">For usage information, see [Using the Surface Hub Hardware Diagnostic Tool to test a device account](https://support.microsoft.com/help/4077574/using-the-surface-hub-hardware-diagnostic-tool-to-test-a-device-accoun).</span></span>

<span data-ttu-id="64375-110">Les problèmes courants sont répertoriés dans le tableau suivant, de même que leurs causes et les solutions possibles.</span><span class="sxs-lookup"><span data-stu-id="64375-110">Common issues are listed in the following table, along with causes and possible fixes.</span></span> <span data-ttu-id="64375-111">La section [Résolution des problèmes d’installation](#setup-troubleshooting) contient une liste des problèmes qui peuvent survenir sur l’appareil, ainsi que plusieurs types de problèmes qui peuvent se produire lors de sa première utilisation.</span><span class="sxs-lookup"><span data-stu-id="64375-111">The [Setup troubleshooting](#setup-troubleshooting) section contains a listing of on-device problems, along with several types of issues that may be encountered during the first-run experience.</span></span> <span data-ttu-id="64375-112">La section [Erreurs ExchangeActiveSync](#exchange-activesync-errors) répertorie les erreurs courantes que l’appareil peut rencontrer lorsque vous essayez de le synchroniser avec un serveur MicrosoftExchangeActiveSync.</span><span class="sxs-lookup"><span data-stu-id="64375-112">The [Exchange ActiveSync errors](#exchange-activesync-errors) section lists common errors the device may encounter when trying to synchronize with an Microsoft Exchange ActiveSync server.</span></span>




## <span data-ttu-id="64375-113">Résolution des problèmes d’installation</span><span class="sxs-lookup"><span data-stu-id="64375-113">Setup troubleshooting</span></span>


<span data-ttu-id="64375-114">Cette section répertorie les causes des problèmes et les solutions possibles pour faciliter la résolution des problèmes que vous risquez de rencontrer lors de l’installation de votre Microsoft SurfaceHub.</span><span class="sxs-lookup"><span data-stu-id="64375-114">This section lists causes, and possible fixes to help troubleshoot issues you might find when you set up your Microsoft Surface Hub.</span></span>

### <span data-ttu-id="64375-115">Sur l’appareil</span><span class="sxs-lookup"><span data-stu-id="64375-115">On-device</span></span>

<span data-ttu-id="64375-116">Solutions possibles aux problèmes survenant sur le SurfaceHub une fois le programme de première utilisation terminé.</span><span class="sxs-lookup"><span data-stu-id="64375-116">Possible fixes for issues on the Surface Hub after you've completed the first-run program.</span></span>

<table>
<tr>
<th><span data-ttu-id="64375-117">Problème</span><span class="sxs-lookup"><span data-stu-id="64375-117">Issue</span></span></th>
<th><span data-ttu-id="64375-118">Causes</span><span class="sxs-lookup"><span data-stu-id="64375-118">Causes</span></span></th>
<th><span data-ttu-id="64375-119">Solutions possibles</span><span class="sxs-lookup"><span data-stu-id="64375-119">Possible fixes</span></span></th>
</tr>
<tr>
<td rowspan="2">
<p><span data-ttu-id="64375-120">Non-réception de messages automatiques d’acceptation/de refus.</span><span class="sxs-lookup"><span data-stu-id="64375-120">Not receiving automatic accept/decline messages.</span></span></p>
</td>
<td>
<p><span data-ttu-id="64375-121">Le compte d’appareil n’est pas configuré pour accepter/refuser les messages automatiquement.</span><span class="sxs-lookup"><span data-stu-id="64375-121">The device account isn't configured to automatically accept/decline messages.</span></span></p>
</td>
<td>
<p><span data-ttu-id="64375-122">Utilisez l’applet de commande PowerShell <code>Set-CalendarProcessing $upn -AutomateProcessing AutoAccept</code>.</span><span class="sxs-lookup"><span data-stu-id="64375-122">Use PowerShell cmdlet <code>Set-CalendarProcessing $upn -AutomateProcessing AutoAccept</code>.</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="64375-123">Le compte d’appareil n’est pas configuré pour traiter les demandes de réunions externes.</span><span class="sxs-lookup"><span data-stu-id="64375-123">The device account isn't configured to process external meeting requests.</span></span></p>
</td>
<td>
<p><span data-ttu-id="64375-124">Utilisez l’applet de commande PowerShell <code>Set-CalendarProcessing $upn -ProcessExternalMeetingMessages $true</code>.</span><span class="sxs-lookup"><span data-stu-id="64375-124">Use PowerShell cmdlet <code>Set-CalendarProcessing $upn -ProcessExternalMeetingMessages $true</code>.</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="64375-125">Le calendrier ne s’affiche pas sur l’écran de démarrage ou le message «Rendez-vous à cette date (aucun compte configuré)» s’affiche.</span><span class="sxs-lookup"><span data-stu-id="64375-125">Calendar is not showing on the Welcome screen, or message "Appointments of date (no account provisioned)" is being displayed.</span></span></p>
</td>
<td>
<p><span data-ttu-id="64375-126">Aucun compte d’appareil n’est configuré sur ce SurfaceHub.</span><span class="sxs-lookup"><span data-stu-id="64375-126">No device account is set up on this Surface Hub.</span></span></p>
</td>
<td>
<p><span data-ttu-id="64375-127">Approvisionnez un compte d’appareil via Paramètres.</span><span class="sxs-lookup"><span data-stu-id="64375-127">Provision a device account through Settings.</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="64375-128">Le calendrier ne s’affiche pas sur l’écran de démarrage ou le message «Rendez-vous à cette date (compte surutilisé)» s’affiche.</span><span class="sxs-lookup"><span data-stu-id="64375-128">Calendar is not showing on the Welcome screen or message "Appointments of date (overprovisioned)" is being displayed.</span></span></p>
</td>
<td>
<p><span data-ttu-id="64375-129">Le compte d’appareil est approvisionné sur un trop grand nombre d’appareils.</span><span class="sxs-lookup"><span data-stu-id="64375-129">The device account is provisioned on too many devices.</span></span></p>
</td>
<td>
<p><span data-ttu-id="64375-130">Supprimez le compte d’appareil des autres appareils sur lesquels il est approvisionné.</span><span class="sxs-lookup"><span data-stu-id="64375-130">Remove the device account from other devices that it's provisioned to.</span></span> <span data-ttu-id="64375-131">Vous pouvez le faire à l’aide du portail d’administration Exchange.</span><span class="sxs-lookup"><span data-stu-id="64375-131">This can be done using the Exchange admin portal.</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="64375-132">Le calendrier ne s’affiche pas sur l’écran de démarrage ou le message «Rendez-vous à cette date (informations d’identification non valides)» s’affiche.</span><span class="sxs-lookup"><span data-stu-id="64375-132">Calendar is not showing on the Welcome screen or message "Appointments of date (invalid credentials)" is being displayed.</span></span></p>
</td>
<td>
<p><span data-ttu-id="64375-133">Le mot de passe du compte d’appareil a expiré et n’est plus valide.</span><span class="sxs-lookup"><span data-stu-id="64375-133">The device account's password has expired and is no longer valid.</span></span></p>
</td>
<td>
<p><span data-ttu-id="64375-134">Mettez à jour le mot de passe du compte dans Paramètres.</span><span class="sxs-lookup"><span data-stu-id="64375-134">Update the account's password in Settings.</span></span> <span data-ttu-id="64375-135">Consultez également <a href="password-management-for-surface-hub-device-accounts.md">Gestion des mots de passe</a>.</span><span class="sxs-lookup"><span data-stu-id="64375-135">Also see <a href="password-management-for-surface-hub-device-accounts.md">Password management</a>.</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="64375-136">Le calendrier ne s’affiche pas sur l’écran de démarrage ou le message «Rendez-vous à cette date (stratégie de compte)» s’affiche.</span><span class="sxs-lookup"><span data-stu-id="64375-136">Calendar is not showing on the Welcome screen or message "Appointments of date (account policy)" is being displayed.</span></span></p>
</td>
<td>
<p><span data-ttu-id="64375-137">Le compte d’appareil utilise une stratégie ActiveSync non valide.</span><span class="sxs-lookup"><span data-stu-id="64375-137">The device account is using an invalid ActiveSync policy.</span></span></p>
</td>
<td>
<p><span data-ttu-id="64375-138">Assurez-vous que le compte d’appareil dispose d’une stratégie ActiveSync où <code>PasswordEnabled == False</code>.</span><span class="sxs-lookup"><span data-stu-id="64375-138">Make sure the device account has an ActiveSync policy where <code>PasswordEnabled == False</code>.</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="64375-139">Le calendrier ne s’affiche pas sur l’écran de démarrage ou le message «Les rendez-vous ne sont peut-être pas à jour» s’affiche.</span><span class="sxs-lookup"><span data-stu-id="64375-139">Calendar is not showing on the Welcome screen or message "Appointments may be out of date" is being displayed.</span></span></p>
</td>
<td>
<p><span data-ttu-id="64375-140">Exchange n’est pas activé.</span><span class="sxs-lookup"><span data-stu-id="64375-140">Exchange is not enabled.</span></span></p>
</td>
<td><span data-ttu-id="64375-141">Activer le compte d’appareil pour les services Exchange via Paramètres.</span><span class="sxs-lookup"><span data-stu-id="64375-141">Enable the device account for Exchange services through Settings.</span></span> <span data-ttu-id="64375-142">Vous devez vous assurer que vous disposez de l’ensemble approprié de stratégies ActiveSync et que vous avez installé tous les certificats nécessaires au fonctionnement des services Exchange.</span><span class="sxs-lookup"><span data-stu-id="64375-142">You need to make sure you have the right set of ActiveSync policies and have also installed any necessary certificates for Exchange services to work.</span></span></td>
</tr>
<tr>
<td>
<p><span data-ttu-id="64375-143">Impossible de se connecter à Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="64375-143">Can't log in to Skype for Business.</span></span></p>
</td>
<td>
<p><span data-ttu-id="64375-144">Le compte d’appareil ne possède pas de propriété d’adresse de protocoleSIP (Session Initiation Protocol).</span><span class="sxs-lookup"><span data-stu-id="64375-144">The device account does not have a Session Initiation Protocol (SIP) address property.</span></span></p>
</td>
<td>
<p><span data-ttu-id="64375-145">Le compte ne possède pas de propriété d’adresse de protocoleSIP et son nom d’utilisateur principal (UPN) ne correspond pas à l’adresseSIP réelle.</span><span class="sxs-lookup"><span data-stu-id="64375-145">The account does not have a SIP address property and its User Principal Name (UPN) does not match the actual SIP address.</span></span> <span data-ttu-id="64375-146">Le compte doit avoir son adresseSIP définie, ou l’adresseSIP doit être ajoutée à l’aide de l’application Paramètres.</span><span class="sxs-lookup"><span data-stu-id="64375-146">The account must have its SIP address set, or the SIP address should be added using the Settings app.</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="64375-147">Impossible de se connecter à SkypeEntreprise.</span><span class="sxs-lookup"><span data-stu-id="64375-147">Can't log in to Skype for Business.</span></span></p>
</td>
<td>
<p><span data-ttu-id="64375-148">Le compte d’appareil nécessite un certificat pour s’authentifier à SkypeEntreprise.</span><span class="sxs-lookup"><span data-stu-id="64375-148">The device account requires a certificate to authenticate into Skype for Business.</span></span></p>
</td>
<td>
<p><span data-ttu-id="64375-149">Installez le certificat approprié à l’aide des packages de mise en service.</span><span class="sxs-lookup"><span data-stu-id="64375-149">Install the appropriate certificate using provisioning packages.</span></span></p>
</td>
</tr>
</table>
 

### <span data-ttu-id="64375-150">Première utilisation</span><span class="sxs-lookup"><span data-stu-id="64375-150">First run</span></span>

<span data-ttu-id="64375-151">Solutions possibles aux problèmes survenant avec le programme de première utilisation de SurfaceHub.</span><span class="sxs-lookup"><span data-stu-id="64375-151">Possible fixes for issues with Surface Hub first-run program.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="64375-152">Problème</span><span class="sxs-lookup"><span data-stu-id="64375-152">Issue</span></span></th>
<th align="left"><span data-ttu-id="64375-153">Causes</span><span class="sxs-lookup"><span data-stu-id="64375-153">Causes</span></span></th>
<th align="left"><span data-ttu-id="64375-154">Solutions possibles</span><span class="sxs-lookup"><span data-stu-id="64375-154">Possible fixes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="64375-155">Compte introuvable avec le domaine et le nom d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="64375-155">Cannot find account when asked for domain and user name.</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-156">Le domaine doit être le nom de domaine complet.</span><span class="sxs-lookup"><span data-stu-id="64375-156">Domain needs to be the fully qualified domain name (FQDN).</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-157">Le nom de domaine complet doit être fourni dans le champ Domaine.</span><span class="sxs-lookup"><span data-stu-id="64375-157">The FQDN should be provided in the domain field.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="first-run-device-acct-page"></a><span data-ttu-id="64375-158">Page Compte d’appareil, problèmes liés aux paramètres d’un nouveau compte</span><span class="sxs-lookup"><span data-stu-id="64375-158">Device account page, issues for new account settings</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="64375-159">Problème</span><span class="sxs-lookup"><span data-stu-id="64375-159">Issue</span></span></th>
<th align="left"><span data-ttu-id="64375-160">Causes</span><span class="sxs-lookup"><span data-stu-id="64375-160">Causes</span></span></th>
<th align="left"><span data-ttu-id="64375-161">Solutions possibles</span><span class="sxs-lookup"><span data-stu-id="64375-161">Possible fixes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="64375-162">Impossible de trouver le compte fourni dans AzureAD.</span><span class="sxs-lookup"><span data-stu-id="64375-162">Unable to find the provided account in Azure AD.</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-163">Le nom d’utilisateur principal (UPN) du compte fourni possède un client qui ne peut pas être contacté dans AzureAD.</span><span class="sxs-lookup"><span data-stu-id="64375-163">The provided account's User Principal Name (UPN) has a tenant that can't be reached in Azure AD.</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-164">Vérifiez que votre connexion Internet fonctionne et que l’appareil peut contacter MicrosoftOnlineServices.</span><span class="sxs-lookup"><span data-stu-id="64375-164">Make sure that you have a working Internet connection, and that the device can reach Microsoft Online Services.</span></span> <span data-ttu-id="64375-165">Assurez-vous que les informations d’identification de compte sont saisies correctement.</span><span class="sxs-lookup"><span data-stu-id="64375-165">Make sure the account credentials are entered correctly.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="64375-166">Impossible de contacter le répertoire spécifié.</span><span class="sxs-lookup"><span data-stu-id="64375-166">Unable to reach the specified directory.</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-167">Le domaine du compte fourni spécifie un domaine qui ne peut pas être contacté.</span><span class="sxs-lookup"><span data-stu-id="64375-167">The provided account domain specifies a domain that can't be reached.</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-168">Vérifiez que votre connexion réseau fonctionne et que l’appareil peut contacter le contrôleur de domaine.</span><span class="sxs-lookup"><span data-stu-id="64375-168">Make sure that you have a working network connection, and that the device can reach the domain controller.</span></span> <span data-ttu-id="64375-169">Assurez-vous que les informations d’identification de compte sont saisies correctement.</span><span class="sxs-lookup"><span data-stu-id="64375-169">Make sure the account credentials are entered correctly.</span></span> <span data-ttu-id="64375-170">Vous pouvez également essayer d’utiliser le nom de domaine complet à la place.</span><span class="sxs-lookup"><span data-stu-id="64375-170">You can also try using the FQDN instead.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="64375-171">Impossible de détecter automatiquement le serveur Exchange.</span><span class="sxs-lookup"><span data-stu-id="64375-171">Can't auto-discover Exchange server.</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-172">Le serveur Exchange n’est pas configuré pour la détection automatique.</span><span class="sxs-lookup"><span data-stu-id="64375-172">The Exchange server isn't configured for auto-discovery.</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-173">Activez la détection automatique du serveur Exchange pour le compte d’appareil, ou saisissez manuellement l’adresse du serveur Exchange du compte.</span><span class="sxs-lookup"><span data-stu-id="64375-173">Enable auto-discovery of the Exchange server for the device account, or enter the account's Exchange server address manually.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="64375-174">Impossible de détecter l’adresseSIP après la saisie des informations d’identification de compte.</span><span class="sxs-lookup"><span data-stu-id="64375-174">Could not discover the SIP address after entering the account credentials.</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-175">Il n’existait aucune entrée d’adresseSIP dans ActiveDirectory ou AzureAD.</span><span class="sxs-lookup"><span data-stu-id="64375-175">There was no SIP address entry in Active Directory or Azure AD.</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-176">Assurez-vous que le compte est activé avec SkypeEntreprise et qu’il dispose d’une adresseSIP.</span><span class="sxs-lookup"><span data-stu-id="64375-176">Make sure the account is enabled with Skype for Business and has a SIP address.</span></span> <span data-ttu-id="64375-177">Si ce n’est pas le cas, vous pouvez saisir manuellement l’adresseSIP dans la zone de texte.</span><span class="sxs-lookup"><span data-stu-id="64375-177">If not, you can enter the SIP address manually into the text box.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="64375-178">Page Compte d’appareil, problèmes liés aux paramètres d’un compte existant</span><span class="sxs-lookup"><span data-stu-id="64375-178">Device account page, issues for existing account settings</span></span>

<table>
<tr>
<th><span data-ttu-id="64375-179">Problème</span><span class="sxs-lookup"><span data-stu-id="64375-179">Issue</span></span></th>
<th><span data-ttu-id="64375-180">Causes</span><span class="sxs-lookup"><span data-stu-id="64375-180">Causes</span></span></th>
<th><span data-ttu-id="64375-181">Codes d’erreur</span><span class="sxs-lookup"><span data-stu-id="64375-181">Error codes</span></span></th>
<th><span data-ttu-id="64375-182">Solutions possibles</span><span class="sxs-lookup"><span data-stu-id="64375-182">Possible fixes</span></span></th>
</tr>
<tr>
<td>
<p><span data-ttu-id="64375-183">Le compte n’a pas pu s’authentifier avec les informations d’identification spécifiées.</span><span class="sxs-lookup"><span data-stu-id="64375-183">Account could not authenticate with the specified credentials.</span></span></p>
</td>
<td>
<p><span data-ttu-id="64375-184">Le compte n’est pas activé en tant qu’utilisateur dans ActiveDirectory (AD), a besoin d’un mot de passe pour s’authentifier ou le mot de passe est incorrect.</span><span class="sxs-lookup"><span data-stu-id="64375-184">The account is not enabled as a user in Active Directory (AD), needs a password to authenticate, or the password is incorrect.</span></span></p>
</td>
<td>
<p><span data-ttu-id="64375-185">None</span><span class="sxs-lookup"><span data-stu-id="64375-185">None</span></span></p>
</td>
<td>
<p><span data-ttu-id="64375-186">Assurez-vous que les informations d’identification sont saisies correctement.</span><span class="sxs-lookup"><span data-stu-id="64375-186">Make sure the credentials are entered correctly.</span></span> <span data-ttu-id="64375-187">Activez le compte en tant qu’utilisateur dans AD et ajoutez un mot de passe, ou définissez RoomMailboxPassword</span><span class="sxs-lookup"><span data-stu-id="64375-187">Enable the account as a user in AD and add a password, or set the RoomMailboxPassword</span></span></p><span data-ttu-id="64375-188">.</span><span class="sxs-lookup"><span data-stu-id="64375-188">.</span></span> </td>
</tr>
<tr>
<td>
<p><span data-ttu-id="64375-189">L’erreur 0x800C0019 s’affiche lors de la fourniture d’un serveur Exchange.</span><span class="sxs-lookup"><span data-stu-id="64375-189">Error 0x800C0019 is displayed when providing an Exchange server.</span></span></p>
</td>
<td>
<p><span data-ttu-id="64375-190">Le compte d’appareil nécessite un certificat pour s’authentifier.</span><span class="sxs-lookup"><span data-stu-id="64375-190">The device account requires a certificate to authenticate.</span></span></p>
</td>
<td>
<p><span data-ttu-id="64375-191">0x800C0019</span><span class="sxs-lookup"><span data-stu-id="64375-191">0x800C0019</span></span></p>
</td>
<td>
<p><span data-ttu-id="64375-192">Installez le certificat approprié à l’aide des packages de mise en service.</span><span class="sxs-lookup"><span data-stu-id="64375-192">Install the appropriate certificate using provisioning packages.</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="64375-193">Les informations d’identification de compte d’appareil ne sont pas valides pour le serveur Exchange fourni.</span><span class="sxs-lookup"><span data-stu-id="64375-193">Device account credentials are not valid for the provided Exchange server.</span></span></p>
</td>
<td>
<p><span data-ttu-id="64375-194">Le serveur Exchange fourni ne se trouve pas à l’emplacement où la boîte aux lettres du compte d’appareil est hébergée.</span><span class="sxs-lookup"><span data-stu-id="64375-194">The provided Exchange server is not where the device account's mailbox is hosted.</span></span></p>
</td>
<td>
<p><span data-ttu-id="64375-195">None</span><span class="sxs-lookup"><span data-stu-id="64375-195">None</span></span></p>
</td>
<td>
<p><span data-ttu-id="64375-196">Vérifiez que vous fournissez le serveur de messagerie Exchange approprié pour le compte d’appareil.</span><span class="sxs-lookup"><span data-stu-id="64375-196">Make sure you are providing the correct Exchange mail server for the device account.</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="64375-197">Expiration HTTP lors de la tentative de contact du serveur Exchange.</span><span class="sxs-lookup"><span data-stu-id="64375-197">HTTP timeout while trying to reach Exchange server.</span></span></p>
</td>
<td></td>
<td>
<p><span data-ttu-id="64375-198">0x80072EE2</span><span class="sxs-lookup"><span data-stu-id="64375-198">0x80072EE2</span></span></p>
</td>
<td></td>
</tr>
<tr>
<td>
<p><span data-ttu-id="64375-199">Serveur Exchange fourni introuvable.</span><span class="sxs-lookup"><span data-stu-id="64375-199">Couldn't find the provided Exchange server.</span></span></p>
</td>
<td>
<p><span data-ttu-id="64375-200">Le serveur Exchange fourni est introuvable.</span><span class="sxs-lookup"><span data-stu-id="64375-200">The Exchange server provided could not be found.</span></span></p>
</td>
<td>
<p><span data-ttu-id="64375-201">Aucun</span><span class="sxs-lookup"><span data-stu-id="64375-201">None</span></span></p>
</td>
<td>
<p><span data-ttu-id="64375-202">Assurez-vous que votre connexion réseau ou Internet fonctionne et que le serveur Exchange que vous avez fourni est correct.</span><span class="sxs-lookup"><span data-stu-id="64375-202">Ensure that you have a working network or Internet connection, and that the Exchange server you provided is correct.</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="64375-203">Protocole HTTP non pris en charge.</span><span class="sxs-lookup"><span data-stu-id="64375-203">http not supported.</span></span></p>
</td>
<td>
<p><span data-ttu-id="64375-204">Un serveur Exchange avec <i>http://</i> à la place de <i>https://</i> a été fourni.</span><span class="sxs-lookup"><span data-stu-id="64375-204">An Exchange server with <i>http://</i> instead of <i>https://</i> was provided.</span></span></p>
</td>
<td>
<p><span data-ttu-id="64375-205">None</span><span class="sxs-lookup"><span data-stu-id="64375-205">None</span></span></p>
</td>
<td>
<p><span data-ttu-id="64375-206">Utilisez un serveur Exchange qui utilise le protocole HTTPS.</span><span class="sxs-lookup"><span data-stu-id="64375-206">Use an Exchange server that uses https.</span></span></p>
</td>
</tr>
<tr>
<td rowspan="3">
<div><p><span data-ttu-id="64375-207">Les utilisateurs arrivent sur la page intitulée «Ce compte présente un problème» concernant ActiveSync.</span><span class="sxs-lookup"><span data-stu-id="64375-207">People land on the page titled "There's a problem with this account" regarding ActiveSync.</span></span></p>
</div>
<div> </div>
</td>
<td>
<p><span data-ttu-id="64375-208">La stratégie ActiveSync PasswordEnabled est définie sur True (ou 1).</span><span class="sxs-lookup"><span data-stu-id="64375-208">The ActiveSync policy PasswordEnabled is set to True (or 1).</span></span></p>
</td>
<td>
<p><span data-ttu-id="64375-209">None</span><span class="sxs-lookup"><span data-stu-id="64375-209">None</span></span></p>
</td>
<td>
<p><span data-ttu-id="64375-210">Créez une politique ActiveSync où PasswordEnabled est défini sur False (ou 0), puis appliquez cette stratégie au compte.</span><span class="sxs-lookup"><span data-stu-id="64375-210">Create a new ActiveSync policy where PasswordEnabled is set to False (or 0), and then apply that policy to the account.</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="64375-211">Le SurfaceHub n’est pas connecté à Exchange.</span><span class="sxs-lookup"><span data-stu-id="64375-211">The Surface Hub doesn't have a connection to Exchange.</span></span></p>
</td>
<td>
<p><span data-ttu-id="64375-212">Aucun</span><span class="sxs-lookup"><span data-stu-id="64375-212">None</span></span></p>
</td>
<td>
<p><span data-ttu-id="64375-213">Vérifiez que vous disposez d’une connexion réseau ou Internet qui fonctionne.</span><span class="sxs-lookup"><span data-stu-id="64375-213">Make sure that you have a working network or Internet connection.</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="64375-214">Exchange renvoie un code d’état indiquant une erreur.</span><span class="sxs-lookup"><span data-stu-id="64375-214">Exchange returns a status code indicating an error.</span></span></p>
</td>
<td>
<p><span data-ttu-id="64375-215">Aucun</span><span class="sxs-lookup"><span data-stu-id="64375-215">None</span></span></p>
</td>
<td>
<p><span data-ttu-id="64375-216">Vérifiez que vous disposez d’une connexion réseau ou Internet qui fonctionne.</span><span class="sxs-lookup"><span data-stu-id="64375-216">Make sure that you have a working network or Internet connection.</span></span></p>
</td>
</tr>
</table>
 

### <a href="" id="first-run-domain-join-page"></a><span data-ttu-id="64375-217">Première utilisation, problèmes de jonction de domaine</span><span class="sxs-lookup"><span data-stu-id="64375-217">First run, Domain join page issues</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="64375-218">Problème</span><span class="sxs-lookup"><span data-stu-id="64375-218">Issue</span></span></th>
<th align="left"><span data-ttu-id="64375-219">Causes</span><span class="sxs-lookup"><span data-stu-id="64375-219">Causes</span></span></th>
<th align="left"><span data-ttu-id="64375-220">Solutions possibles</span><span class="sxs-lookup"><span data-stu-id="64375-220">Possible fixes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="64375-221">Lorsque vous essayez de joindre un domaine, une erreur indique que le compte n’a pas pu s’authentifier à l’aide des informations d’identification spécifiées.</span><span class="sxs-lookup"><span data-stu-id="64375-221">When trying to join a domain, an error shows that the account couldn't authenticate using the specified credentials.</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-222">Les informations d’identification fournies ne sont pas en mesure de joindre le domaine spécifié.</span><span class="sxs-lookup"><span data-stu-id="64375-222">The credentials provided are not capable of joining the specified domain.</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-223">Saisissez les informations d’identification correctes pour un compte qui existe dans le domaine spécifié.</span><span class="sxs-lookup"><span data-stu-id="64375-223">Enter correct credentials for an account that exists in the specified domain.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="64375-224">Lorsque vous spécifiez un groupe d’un domaine, une erreur indique que le groupe est introuvable dans le domaine.</span><span class="sxs-lookup"><span data-stu-id="64375-224">When specifying a group from a domain, an error shows that the group couldn't be found on the domain.</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-225">Il est possible que le groupe ait été supprimé ou qu’il n’existe plus.</span><span class="sxs-lookup"><span data-stu-id="64375-225">The group may have been removed or no longer exists.</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-226">Vérifiez que le groupe existe au sein du domaine.</span><span class="sxs-lookup"><span data-stu-id="64375-226">Verify that the group exists within the domain.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="64375-227">Première utilisation, page Serveur Exchange</span><span class="sxs-lookup"><span data-stu-id="64375-227">First run, Exchange server page</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="64375-228">Problème</span><span class="sxs-lookup"><span data-stu-id="64375-228">Issue</span></span></th>
<th align="left"><span data-ttu-id="64375-229">Causes</span><span class="sxs-lookup"><span data-stu-id="64375-229">Causes</span></span></th>
<th align="left"><span data-ttu-id="64375-230">Solutions possibles</span><span class="sxs-lookup"><span data-stu-id="64375-230">Possible fixes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="64375-231">Les utilisateurs arrivent sur cette page et l’adresse du serveur Exchange leur est demandée.</span><span class="sxs-lookup"><span data-stu-id="64375-231">People land on this page and are asked for the Exchange server address.</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-232">Le serveur Exchange n’est pas configuré pour la détection automatique.</span><span class="sxs-lookup"><span data-stu-id="64375-232">The Exchange server isn't configured for auto-discovery.</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-233">Activez la détection automatique du serveur Exchange pour le compte d’appareil, ou saisissez manuellement l’adresse du serveur Exchange du compte.</span><span class="sxs-lookup"><span data-stu-id="64375-233">Enable auto-discovery of the Exchange server for the device account, or enter the account's Exchange server address manually.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="first-run-on-device"></a><span data-ttu-id="64375-234">Première utilisation, problèmes sur l’appareil</span><span class="sxs-lookup"><span data-stu-id="64375-234">First run, On-device issues</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="64375-235">Problème</span><span class="sxs-lookup"><span data-stu-id="64375-235">Issue</span></span></th>
<th align="left"><span data-ttu-id="64375-236">Causes</span><span class="sxs-lookup"><span data-stu-id="64375-236">Causes</span></span></th>
<th align="left"><span data-ttu-id="64375-237">Codes d’erreur</span><span class="sxs-lookup"><span data-stu-id="64375-237">Error codes</span></span></th>
<th align="left"><span data-ttu-id="64375-238">Solutions possibles</span><span class="sxs-lookup"><span data-stu-id="64375-238">Possible fixes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="64375-239">Impossible de synchroniser le courrier/le calendrier.</span><span class="sxs-lookup"><span data-stu-id="64375-239">Can't sync mail/calendar.</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-240">Le compte n’a pas approuvé le SurfaceHub en tant qu’appareil autorisé.</span><span class="sxs-lookup"><span data-stu-id="64375-240">The account has not allowed the Surface Hub as an allowed device.</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-241">0x86000C1C</span><span class="sxs-lookup"><span data-stu-id="64375-241">0x86000C1C</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-242">Ajoutez l’ID de l’appareil surface Hub à la liste autorisée en définissant la <strong> </strong> propriété ActiveSyncAllowedDeviceIds de la boîte aux lettres.</span><span class="sxs-lookup"><span data-stu-id="64375-242">Add the Surface Hub device ID to the allowed list by setting the <strong>ActiveSyncAllowedDeviceIds</strong> property for the mailbox.</span></span></p></td>
</tr>
</tbody>
</table>

 



 

## <span data-ttu-id="64375-243">Erreurs ExchangeActiveSync</span><span class="sxs-lookup"><span data-stu-id="64375-243">Exchange ActiveSync errors</span></span>


<span data-ttu-id="64375-244">Cette section répertorie les codes d’état, les mappages, les messages des utilisateurs et les mesures qu’un administrateur peut prendre pour résoudre les erreurs ExchangeActiveSync.</span><span class="sxs-lookup"><span data-stu-id="64375-244">This section lists status codes, mapping, user messages, and actions an admin can take to solve Exchange ActiveSync errors.</span></span>

<table>
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="64375-245">Code hexadécimal</span><span class="sxs-lookup"><span data-stu-id="64375-245">Hex Code</span></span></th>
<th align="left"><span data-ttu-id="64375-246">Mappage</span><span class="sxs-lookup"><span data-stu-id="64375-246">Mapping</span></span></th>
<th align="left"><span data-ttu-id="64375-247">Message convivial</span><span class="sxs-lookup"><span data-stu-id="64375-247">User-Friendly Message</span></span></th>
<th align="left"><span data-ttu-id="64375-248">Mesure que l’administrateur doit prendre</span><span class="sxs-lookup"><span data-stu-id="64375-248">Action admin should take</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="64375-249">0x85010002</span><span class="sxs-lookup"><span data-stu-id="64375-249">0x85010002</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-250">E_HTTP_DENIED</span><span class="sxs-lookup"><span data-stu-id="64375-250">E_HTTP_DENIED</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-251">Le mot de passe doit être mis à jour.</span><span class="sxs-lookup"><span data-stu-id="64375-251">The password must be updated.</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-252">Mettez à jour le mot de passe.</span><span class="sxs-lookup"><span data-stu-id="64375-252">Update the password.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="64375-253">0x80072EFD</span><span class="sxs-lookup"><span data-stu-id="64375-253">0x80072EFD</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-254">WININET_E_CANNOT_CONNECT</span><span class="sxs-lookup"><span data-stu-id="64375-254">WININET_E_CANNOT_CONNECT</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-255">Impossible de se connecter au serveur pour le moment.</span><span class="sxs-lookup"><span data-stu-id="64375-255">Can't connect to the server right now.</span></span> <span data-ttu-id="64375-256">Patientez quelques instants et réessayez, ou vérifiez les paramètres du compte.</span><span class="sxs-lookup"><span data-stu-id="64375-256">Wait a while and try again, or check the account settings.</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-257">Vérifiez que le nom du serveur est correct et accessible.</span><span class="sxs-lookup"><span data-stu-id="64375-257">Verify that the server name is correct and reachable.</span></span> <span data-ttu-id="64375-258">Vérifiez que l’appareil est connecté au réseau.</span><span class="sxs-lookup"><span data-stu-id="64375-258">Verify that the device is connected to the network.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="64375-259">0x86000C29</span><span class="sxs-lookup"><span data-stu-id="64375-259">0x86000C29</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-260">E_NEXUS_STATUS_DEVICE_NOTPROVISIONED (les stratégies ne correspondent pas)</span><span class="sxs-lookup"><span data-stu-id="64375-260">E_NEXUS_STATUS_DEVICE_NOTPROVISIONED (policies don't match)</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-261">Le compte est configuré avec des stratégies non compatibles avec SurfaceHub.</span><span class="sxs-lookup"><span data-stu-id="64375-261">The account is configured with policies not compatible with Surface Hub.</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-262">Désactivez la stratégie <strong>PasswordEnabled</strong> pour ce compte.</span><span class="sxs-lookup"><span data-stu-id="64375-262">Disable the <strong>PasswordEnabled</strong> policy for this account.</span></span></p>
<p><span data-ttu-id="64375-263">Nous avons rencontré un bogue qui nous est peut-être lors de la mise en surface de la stratégie si le compte ne reçoit pas de notifications de serveur dans le cadre de l’intervalle d’actualisation</span><span class="sxs-lookup"><span data-stu-id="64375-263">We have a bug were we may surface policy errors if the account doesn't receive any server notifications within the policy refresh interval.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="64375-264">0x86000C4C</span><span class="sxs-lookup"><span data-stu-id="64375-264">0x86000C4C</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-265">E_NEXUS_STATUS_MAXIMUMDEVICESREACHED</span><span class="sxs-lookup"><span data-stu-id="64375-265">E_NEXUS_STATUS_MAXIMUMDEVICESREACHED</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-266">Le compte possède trop de partenariats avec des appareils.</span><span class="sxs-lookup"><span data-stu-id="64375-266">The account has too many device partnerships.</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-267">Supprimez un ou plusieurs partenariats sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="64375-267">Delete one or more partnerships on the server.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="64375-268">0x86000C0A</span><span class="sxs-lookup"><span data-stu-id="64375-268">0x86000C0A</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-269">E_NEXUS_STATUS_SERVERERROR_RETRYLATER</span><span class="sxs-lookup"><span data-stu-id="64375-269">E_NEXUS_STATUS_SERVERERROR_RETRYLATER</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-270">Impossible de se connecter au serveur pour le moment.</span><span class="sxs-lookup"><span data-stu-id="64375-270">Can't connect to the server right now.</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-271">Patientez jusqu’à ce que le serveur revienne en ligne.</span><span class="sxs-lookup"><span data-stu-id="64375-271">Wait until the server comes back online.</span></span> <span data-ttu-id="64375-272">Si le problème persiste, réapprovisionnez le compte.</span><span class="sxs-lookup"><span data-stu-id="64375-272">If the issue persists, re-provision the account.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="64375-273">0x85050003</span><span class="sxs-lookup"><span data-stu-id="64375-273">0x85050003</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-274">E_CREDENTIALS_EXPIRED (les informations d’identification ont expiré et doivent être mises à jour)</span><span class="sxs-lookup"><span data-stu-id="64375-274">E_CREDENTIALS_EXPIRED (Credentials have expired and need to be updated)</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-275">Le mot de passe doit être mis à jour.</span><span class="sxs-lookup"><span data-stu-id="64375-275">The password must be updated.</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-276">Mettez à jour le mot de passe.</span><span class="sxs-lookup"><span data-stu-id="64375-276">Update the password.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="64375-277">0x8505000D</span><span class="sxs-lookup"><span data-stu-id="64375-277">0x8505000D</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-278">E_AIRSYNC_RESET_RETRY</span><span class="sxs-lookup"><span data-stu-id="64375-278">E_AIRSYNC_RESET_RETRY</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-279">Impossible de se connecter au serveur pour le moment.</span><span class="sxs-lookup"><span data-stu-id="64375-279">Can't connect to the server right now.</span></span> <span data-ttu-id="64375-280">Veuillez patienter quelques instants ou vérifier les paramètres du compte.</span><span class="sxs-lookup"><span data-stu-id="64375-280">Wait a while or check the account's settings.</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-281">Il s’agit normalement d’une erreur temporaire, mais si le problème persiste, vérifiez le nombre d’appareils associés au compte et supprimez certains d’entre eux s’il y en a trop.</span><span class="sxs-lookup"><span data-stu-id="64375-281">This is normally a transient error but if the issue persists check the number of devices associated with the account and delete some of them if the number is large.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="64375-282">0x86000C16</span><span class="sxs-lookup"><span data-stu-id="64375-282">0x86000C16</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-283">E_NEXUS_STATUS_USER_HASNOMAILBOX</span><span class="sxs-lookup"><span data-stu-id="64375-283">E_NEXUS_STATUS_USER_HASNOMAILBOX</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-284">La boîte aux lettres a migré vers un autre serveur.</span><span class="sxs-lookup"><span data-stu-id="64375-284">The mailbox was migrated to a different server.</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-285">Vous ne devriez jamais voir cette erreur.</span><span class="sxs-lookup"><span data-stu-id="64375-285">You should never see this error.</span></span> <span data-ttu-id="64375-286">Si le problème persiste, réapprovisionnez le compte.</span><span class="sxs-lookup"><span data-stu-id="64375-286">If the issue persists, re-provision the account.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="64375-287">0x85010004</span><span class="sxs-lookup"><span data-stu-id="64375-287">0x85010004</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-288">E_HTTP_FORBIDDEN</span><span class="sxs-lookup"><span data-stu-id="64375-288">E_HTTP_FORBIDDEN</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-289">Impossible de se connecter au serveur pour le moment.</span><span class="sxs-lookup"><span data-stu-id="64375-289">Can't connect to the server right now.</span></span> <span data-ttu-id="64375-290">Patientez quelques instants, puis réessayez, ou vérifiez les paramètres du compte.</span><span class="sxs-lookup"><span data-stu-id="64375-290">Wait a while and try again, or check the account's settings.</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-291">Vérifiez le nom du serveur pour vous assurer qu’il est correct.</span><span class="sxs-lookup"><span data-stu-id="64375-291">Verify the server name to make sure it is correct.</span></span> <span data-ttu-id="64375-292">Si le compte utilise l’authentification basée sur la certification, assurez-vous que le certificat est toujours valide, et mettez-le à jour si ce n’est pas le cas.</span><span class="sxs-lookup"><span data-stu-id="64375-292">If the account is using cert based authentication make sure the certificate is still valid and update it if not.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="64375-293">0x85030028</span><span class="sxs-lookup"><span data-stu-id="64375-293">0x85030028</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-294">E_ACTIVESYNC_PASSWORD_OR_GETCERT</span><span class="sxs-lookup"><span data-stu-id="64375-294">E_ACTIVESYNC_PASSWORD_OR_GETCERT</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-295">Le mot de passe ou le certificat client du compte est manquant ou non valide.</span><span class="sxs-lookup"><span data-stu-id="64375-295">The account's password or client certificate are missing or invalid.</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-296">Mettez à jour le mot de passe et/ou déployez le certificat client.</span><span class="sxs-lookup"><span data-stu-id="64375-296">Update the password and/or deploy the client certificate.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="64375-297">0x86000C2A</span><span class="sxs-lookup"><span data-stu-id="64375-297">0x86000C2A</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-298">E_NEXUS_STATUS_DEVICE_POLICYREFRESH</span><span class="sxs-lookup"><span data-stu-id="64375-298">E_NEXUS_STATUS_DEVICE_POLICYREFRESH</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-299">Le compte est configuré avec des stratégies non compatibles avec SurfaceHub.</span><span class="sxs-lookup"><span data-stu-id="64375-299">The account is configured with policies not compatible with Surface Hub.</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-300">Désactivez la stratégie PasswordEnabled pour ce compte.</span><span class="sxs-lookup"><span data-stu-id="64375-300">Disable the PasswordEnabled policy for this account.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="64375-301">0x85050002</span><span class="sxs-lookup"><span data-stu-id="64375-301">0x85050002</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-302">E_CREDENTIALS_UNAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="64375-302">E_CREDENTIALS_UNAVAILABLE</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-303">Le mot de passe doit être mis à jour.</span><span class="sxs-lookup"><span data-stu-id="64375-303">The password must be updated.</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-304">Mettez à jour le mot de passe.</span><span class="sxs-lookup"><span data-stu-id="64375-304">Update the password.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="64375-305">0x80072EE2</span><span class="sxs-lookup"><span data-stu-id="64375-305">0x80072EE2</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-306">WININET_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="64375-306">WININET_E_TIMEOUT</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-307">Le réseau ne prend pas en charge le délai d’inactivité minimal requis pour recevoir des notifications de serveur, ou le serveur est hors connexion.</span><span class="sxs-lookup"><span data-stu-id="64375-307">The network doesn't support the minimum idle timeout required to receive server notification, or the server is offline.</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-308">Vérifiez que le serveur est en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="64375-308">Verify that the server is running.</span></span> <span data-ttu-id="64375-309">Vérifiez les paramètres NAT.</span><span class="sxs-lookup"><span data-stu-id="64375-309">Verify the NAT settings.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="64375-310">0x85002004</span><span class="sxs-lookup"><span data-stu-id="64375-310">0x85002004</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-311">E_FAIL_ABORT</span><span class="sxs-lookup"><span data-stu-id="64375-311">E_FAIL_ABORT</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-312">Cette erreur est utilisée pour interrompre la synchronisation en suspens et ne sera pas exposée aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="64375-312">This error is used to interrupt the hanging sync, and will not be exposed to users.</span></span> <span data-ttu-id="64375-313">Elle s’affiche dans les données de diagnostic si vous forcez une synchronisation interactive, supprimez le compte ou mettez à jour ses paramètres.</span><span class="sxs-lookup"><span data-stu-id="64375-313">It will be shown in the diagnostic data if you force an interactive sync, delete the account, or update its settings.</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-314">Aucune.</span><span class="sxs-lookup"><span data-stu-id="64375-314">Nothing.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="64375-315">0x85010017</span><span class="sxs-lookup"><span data-stu-id="64375-315">0x85010017</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-316">E_HTTP_SERVICE_UNAVAIL</span><span class="sxs-lookup"><span data-stu-id="64375-316">E_HTTP_SERVICE_UNAVAIL</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-317">Impossible de se connecter au serveur pour le moment.</span><span class="sxs-lookup"><span data-stu-id="64375-317">Can't connect to the server right now.</span></span> <span data-ttu-id="64375-318">Veuillez patienter quelques instants ou vérifier les paramètres du compte.</span><span class="sxs-lookup"><span data-stu-id="64375-318">Wait a while or check the account's settings.</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-319">Vérifiez le nom du serveur pour vous assurer qu’il est correct.</span><span class="sxs-lookup"><span data-stu-id="64375-319">Verify the server name to make sure it is correct.</span></span> <span data-ttu-id="64375-320">Patientez jusqu’à ce que le serveur revienne en ligne.</span><span class="sxs-lookup"><span data-stu-id="64375-320">Wait until the server comes back online.</span></span> <span data-ttu-id="64375-321">Si le problème persiste, réapprovisionnez le compte.</span><span class="sxs-lookup"><span data-stu-id="64375-321">If the issue persists, re-provision the account.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="64375-322">0x86000C0D</span><span class="sxs-lookup"><span data-stu-id="64375-322">0x86000C0D</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-323">E_NEXUS_STATUS_MAILBOX_SERVEROFFLINE</span><span class="sxs-lookup"><span data-stu-id="64375-323">E_NEXUS_STATUS_MAILBOX_SERVEROFFLINE</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-324">Impossible de se connecter au serveur pour le moment.</span><span class="sxs-lookup"><span data-stu-id="64375-324">Can't connect to the server right now.</span></span> <span data-ttu-id="64375-325">Veuillez patienter quelques instants ou vérifier les paramètres du compte.</span><span class="sxs-lookup"><span data-stu-id="64375-325">Wait a while or check the account's settings.</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-326">Vérifiez le nom du serveur pour vous assurer qu’il est correct.</span><span class="sxs-lookup"><span data-stu-id="64375-326">Verify the server name to make sure it is correct.</span></span> <span data-ttu-id="64375-327">Patientez jusqu’à ce que le serveur revienne en ligne.</span><span class="sxs-lookup"><span data-stu-id="64375-327">Wait until the server comes back online.</span></span> <span data-ttu-id="64375-328">Si le problème persiste, réapprovisionnez le compte.</span><span class="sxs-lookup"><span data-stu-id="64375-328">If the issue persists, re-provision the account.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="64375-329">0x85030027</span><span class="sxs-lookup"><span data-stu-id="64375-329">0x85030027</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-330">E_ACTIVESYNC_GETCERT</span><span class="sxs-lookup"><span data-stu-id="64375-330">E_ACTIVESYNC_GETCERT</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-331">Le serveur Exchange exige un certificat.</span><span class="sxs-lookup"><span data-stu-id="64375-331">The Exchange server requires a certificate.</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-332">Importez le certificat EAS approprié sur le SurfaceHub.</span><span class="sxs-lookup"><span data-stu-id="64375-332">Import the appropriate EAS certificate on the Surface Hub.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="64375-333">0x86000C2B</span><span class="sxs-lookup"><span data-stu-id="64375-333">0x86000C2B</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-334">E_NEXUS_STATUS_INVALID_POLICYKEY</span><span class="sxs-lookup"><span data-stu-id="64375-334">E_NEXUS_STATUS_INVALID_POLICYKEY</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-335">Le compte est configuré avec des stratégies non compatibles avec SurfaceHub.</span><span class="sxs-lookup"><span data-stu-id="64375-335">The account is configured with policies not compatible with Surface Hub.</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-336">Désactivez la stratégie PasswordEnabled pour ce compte.</span><span class="sxs-lookup"><span data-stu-id="64375-336">Disable the PasswordEnabled policy for this account.</span></span></p>
<p><span data-ttu-id="64375-337">Nous avons rencontré un bogue qui nous est peut-être lors de la mise en surface de la stratégie si le compte ne reçoit pas de notifications de serveur dans le cadre de l’intervalle d’actualisation</span><span class="sxs-lookup"><span data-stu-id="64375-337">We have a bug were we may surface policy errors if the account doesn't receive any server notifications within the policy refresh interval.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="64375-338">0x85010005</span><span class="sxs-lookup"><span data-stu-id="64375-338">0x85010005</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-339">E_HTTP_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="64375-339">E_HTTP_NOT_FOUND</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-340">Le nom du serveur est non valide.</span><span class="sxs-lookup"><span data-stu-id="64375-340">The server name is invalid.</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-341">Vérifiez le nom du serveur pour vous assurer qu’il est correct.</span><span class="sxs-lookup"><span data-stu-id="64375-341">Verify the server name to make sure it is correct.</span></span> <span data-ttu-id="64375-342">Si le problème persiste, réapprovisionnez le compte.</span><span class="sxs-lookup"><span data-stu-id="64375-342">If the issue persists, re-provision the account.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="64375-343">0x85010014</span><span class="sxs-lookup"><span data-stu-id="64375-343">0x85010014</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-344">E_HTTP_SERVER_ERROR</span><span class="sxs-lookup"><span data-stu-id="64375-344">E_HTTP_SERVER_ERROR</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-345">Impossible de se connecter au serveur.</span><span class="sxs-lookup"><span data-stu-id="64375-345">Can't connect to the server.</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-346">Vérifiez le nom du serveur pour vous assurer qu’il est correct.</span><span class="sxs-lookup"><span data-stu-id="64375-346">Verify the server name to make sure it is correct.</span></span> <span data-ttu-id="64375-347">Déclenchez une synchronisation et, si le problème persiste, réapprovisionnez le compte.</span><span class="sxs-lookup"><span data-stu-id="64375-347">Trigger a sync and, if the issue persists, re-provision the account.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="64375-348">0x80072EE7</span><span class="sxs-lookup"><span data-stu-id="64375-348">0x80072EE7</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-349">WININET_E_NAME_NOT_RESOLVED</span><span class="sxs-lookup"><span data-stu-id="64375-349">WININET_E_NAME_NOT_RESOLVED</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-350">Impossible de résoudre le nom du serveur ou l’adresse.</span><span class="sxs-lookup"><span data-stu-id="64375-350">The server name or address could not be resolved.</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-351">Assurez-vous que le nom du serveur est saisi correctement.</span><span class="sxs-lookup"><span data-stu-id="64375-351">Make sure the server name is entered correctly.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="64375-352">0x8007052F</span><span class="sxs-lookup"><span data-stu-id="64375-352">0x8007052F</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-353">ERROR_ACCOUNT_RESTRICTION</span><span class="sxs-lookup"><span data-stu-id="64375-353">ERROR_ACCOUNT_RESTRICTION</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-354">Lors de la détection automatique du serveur Exchange, une stratégie est appliquée et empêche l’utilisateur connecté de se connecter au serveur.</span><span class="sxs-lookup"><span data-stu-id="64375-354">While auto-discovering the Exchange server, a policy is applied that prevents the logged-in user from logging in to the server.</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-355">Il s’agit d’un problème de minutage.</span><span class="sxs-lookup"><span data-stu-id="64375-355">This is a timing issue.</span></span> <span data-ttu-id="64375-356">Vérifiez de nouveau les informations d’identification de compte.</span><span class="sxs-lookup"><span data-stu-id="64375-356">Re-verify the account's credentials.</span></span> <span data-ttu-id="64375-357">Si elles sont correctes, essayez de les réapprovisionner.</span><span class="sxs-lookup"><span data-stu-id="64375-357">Try to re-provision when they're correct.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="64375-358">0x800C0019</span><span class="sxs-lookup"><span data-stu-id="64375-358">0x800C0019</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-359">INET_E_INVALID_CERTIFICATE</span><span class="sxs-lookup"><span data-stu-id="64375-359">INET_E_INVALID_CERTIFICATE</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-360">Le certificat de sécurité requis pour accéder à cette ressource est non valide.</span><span class="sxs-lookup"><span data-stu-id="64375-360">Security certificate required to access this resource is invalid.</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-361">Installez le certificat ActiveSync approprié nécessaire pour le compte d’appareil fourni.</span><span class="sxs-lookup"><span data-stu-id="64375-361">Install the correct ActiveSync certificate needed for the provided device account.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="64375-362">0x80072F0D</span><span class="sxs-lookup"><span data-stu-id="64375-362">0x80072F0D</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-363">WININET_E_INVALID_CA</span><span class="sxs-lookup"><span data-stu-id="64375-363">WININET_E_INVALID_CA</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-364">L’autorité de certification est non valide ou incorrecte.</span><span class="sxs-lookup"><span data-stu-id="64375-364">The certificate authority is invalid or is incorrect.</span></span> <span data-ttu-id="64375-365">Impossible de détecter automatiquement un serveur Exchange car il manque un certificat.</span><span class="sxs-lookup"><span data-stu-id="64375-365">Could not auto-discover the Exchange server because a certificate is missing.</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-366">Installez le certificat ActiveSync approprié nécessaire pour le compte d’appareil fourni.</span><span class="sxs-lookup"><span data-stu-id="64375-366">Install the correct ActiveSync certificate needed for the provided device account.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="64375-367">0x80004005</span><span class="sxs-lookup"><span data-stu-id="64375-367">0x80004005</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-368">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="64375-368">E_FAIL</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-369">Le domaine fourni est introuvable.</span><span class="sxs-lookup"><span data-stu-id="64375-369">The domain provided couldn't be found.</span></span> <span data-ttu-id="64375-370">Le serveur Exchange n’a pas pu être détecté automatiquement et n’a pas été fourni dans les paramètres.</span><span class="sxs-lookup"><span data-stu-id="64375-370">The Exchange server could not be auto-discovered and was not provided in the settings.</span></span></p></td>
<td align="left"><p><span data-ttu-id="64375-371">Assurez-vous que le domaine saisi est le nom de domaine complet, et qu’un serveur Exchange est saisi dans la zone de texte Serveur Exchange.</span><span class="sxs-lookup"><span data-stu-id="64375-371">Make sure that the domain entered is the FQDN, and that there is an Exchange server entered in the Exchange server text box.</span></span></p></td>
</tr>
</tbody>
</table>

## <span data-ttu-id="64375-372">Contacter le support</span><span class="sxs-lookup"><span data-stu-id="64375-372">Contact Support</span></span>

<span data-ttu-id="64375-373">Si vous avez des questions ou si vous avez besoin d’aide, vous pouvez [créer une demande de support](https://support.microsoft.com/supportforbusiness/productselection).</span><span class="sxs-lookup"><span data-stu-id="64375-373">If you have questions or need help, you can [create a support request](https://support.microsoft.com/supportforbusiness/productselection).</span></span>


 
## <span data-ttu-id="64375-374">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="64375-374">Related content</span></span>

- [<span data-ttu-id="64375-375">Résolution des problèmes de connexion de Miracast au Surface Hub</span><span class="sxs-lookup"><span data-stu-id="64375-375">Troubleshooting Miracast connection to the Surface Hub</span></span>](https://docs.microsoft.com/surface-hub/miracast-troubleshooting)
 





