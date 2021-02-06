---
title: PowerShell pour Surface Hub (v1)
description: Cette page inclut des scripts PowerShell destinés au Surface Hub d’origine (v1)
ms.assetid: 3EF48F63-8E4C-4D74-ACD5-461F1C653784
ms.reviewer: ''
manager: laurawi
keywords: PowerShell, configurer Surface Hub, gérer Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 02/01/2021
ms.localizationpriority: medium
appliesto:
- Surface Hub
ms.openlocfilehash: 09d600efbf07bb58de1b5ebffcb6731e4125a62d
ms.sourcegitcommit: 7809222a51eb184f07d6b3ffbdd04a6272b247f9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2021
ms.locfileid: "11314427"
---
# <span data-ttu-id="71f59-104">PowerShell pour Surface Hub (v1)</span><span class="sxs-lookup"><span data-stu-id="71f59-104">PowerShell for Surface Hub (v1)</span></span>

> [!NOTE]
 ><span data-ttu-id="71f59-105">Cette page inclut des scripts PowerShell destinés au Surface Hub d’origine (v1).</span><span class="sxs-lookup"><span data-stu-id="71f59-105">This page includes PowerShell scripts intended for the original Surface Hub (v1).</span></span> <span data-ttu-id="71f59-106">Pour les derniers scripts de création de compte pour Surface Hub 2S, voir Créer un compte d’appareil [Surface Hub 2S.](surface-hub-2s-account.md)</span><span class="sxs-lookup"><span data-stu-id="71f59-106">For the latest account creation scripts for Surface Hub 2S, see [Create Surface Hub 2S device account](surface-hub-2s-account.md).</span></span>

-   [<span data-ttu-id="71f59-107">Scripts PowerShell destinés aux administrateurs Surface Hub</span><span class="sxs-lookup"><span data-stu-id="71f59-107">PowerShell scripts for Surface Hub admins</span></span>](#scripts-for-admins)
    -   [<span data-ttu-id="71f59-108">Créer un compte local</span><span class="sxs-lookup"><span data-stu-id="71f59-108">Create an on-premises account</span></span>](#create-on-premises-ps-scripts)
    -   [<span data-ttu-id="71f59-109">Créer un compte d’appareil à l’aide d’Office 365</span><span class="sxs-lookup"><span data-stu-id="71f59-109">Create a device account using Office 365</span></span>](#create-os356-ps-scripts)
    -   [<span data-ttu-id="71f59-110">Script de vérification de compte</span><span class="sxs-lookup"><span data-stu-id="71f59-110">Account verification script</span></span>](#acct-verification-ps-scripts)
    -   [<span data-ttu-id="71f59-111">Activer Skype Entreprise (EnableSfb.ps1)</span><span class="sxs-lookup"><span data-stu-id="71f59-111">Enable Skype for Business (EnableSfb.ps1)</span></span>](#enable-sfb-ps-scripts)
-   [<span data-ttu-id="71f59-112">Applets de commande utiles</span><span class="sxs-lookup"><span data-stu-id="71f59-112">Useful cmdlets</span></span>](#useful-cmdlets)
    -   [<span data-ttu-id="71f59-113">Création d’une stratégie Exchange ActiveSync compatible avec le Surface Hub</span><span class="sxs-lookup"><span data-stu-id="71f59-113">Creating a Surface Hub-compatible Exchange ActiveSync policy</span></span>](#create-compatible-as-policy)
    -   [<span data-ttu-id="71f59-114">Autoriser les ID d’appareil pour ActiveSync</span><span class="sxs-lookup"><span data-stu-id="71f59-114">Allowing device IDs for ActiveSync</span></span>](#allowing-device-ids-for-activesync)
    -   [<span data-ttu-id="71f59-115">Accepter et refuser automatiquement les demandes de réunion</span><span class="sxs-lookup"><span data-stu-id="71f59-115">Auto-accepting and declining meeting requests</span></span>](#auto-accept-meetings-cmdlet)
    -   [<span data-ttu-id="71f59-116">Accepter les demandes de réunion externes</span><span class="sxs-lookup"><span data-stu-id="71f59-116">Accepting external meeting requests</span></span>](#accept-ext-meetings-cmdlet)
    
 > [!NOTE]
 > <span data-ttu-id="71f59-117">Voir aussi [Modern Auth et Unattended Scripts dans Exchange Online PowerShell V2](https://techcommunity.microsoft.com/t5/exchange-team-blog/modern-auth-and-unattended-scripts-in-exchange-online-powershell/ba-p/1497387)</span><span class="sxs-lookup"><span data-stu-id="71f59-117">See also [Modern Auth and Unattended Scripts in Exchange Online PowerShell V2](https://techcommunity.microsoft.com/t5/exchange-team-blog/modern-auth-and-unattended-scripts-in-exchange-online-powershell/ba-p/1497387)</span></span>

## <span data-ttu-id="71f59-118">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="71f59-118">Prerequisites</span></span>

<span data-ttu-id="71f59-119">Pour exécuter correctement ces scripts PowerShell, vous devez installer les éléments préalablement requis suivants:</span><span class="sxs-lookup"><span data-stu-id="71f59-119">To successfully execute these PowerShell scripts, you will need to install the following prerequisites:</span></span>

- [<span data-ttu-id="71f59-120">Assistant de connexion Microsoft Online Services pour professionnels de l’informatique RTW</span><span class="sxs-lookup"><span data-stu-id="71f59-120">Microsoft Online Services Sign-in Assistant for IT Professionals RTW</span></span>](https://www.microsoft.com/download/details.aspx?id=41950)
- [<span data-ttu-id="71f59-121">Module MicrosoftAzure ActiveDirectory pour Windows PowerShell (version64bits)</span><span class="sxs-lookup"><span data-stu-id="71f59-121">Microsoft Azure Active Directory Module for Windows PowerShell (64-bit version)</span></span>](https://www.powershellgallery.com/packages/MSOnline/1.1.183.17)
- [<span data-ttu-id="71f59-122">Module Windows PowerShell pour Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="71f59-122">Windows PowerShell Module for Skype for Business Online</span></span>](https://www.microsoft.com/download/details.aspx?id=39366)

## <a href="" id="scripts-for-admins"></a><span data-ttu-id="71f59-123">Scripts PowerShell destinés aux administrateurs Surface Hub</span><span class="sxs-lookup"><span data-stu-id="71f59-123">PowerShell scripts for Surface Hub administrators</span></span>

<span data-ttu-id="71f59-124">À quoi servent les scripts?</span><span class="sxs-lookup"><span data-stu-id="71f59-124">What do the scripts do?</span></span>

-   <span data-ttu-id="71f59-125">Créer des comptes d’appareil pour les installations à l’aide d’une forêt unique pure sur site (Microsoft Exchange et Skype2013 et versions ultérieures uniquement) ou en ligne (Microsoft Office365), qui sont configurées correctement pour votre Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="71f59-125">Create device accounts for setups using pure single-forest on-premises (Microsoft Exchange and Skype 2013 and later only) or online (Microsoft Office 365), that are configured correctly for your Surface Hub.</span></span>
-   <span data-ttu-id="71f59-126">Valider des comptes d’appareil existants pour tout programme d’installation (sur site ou en ligne) pour s’assurer qu’ils sont compatibles avec le Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="71f59-126">Validate existing device accounts for any setup (on-premises or online) to make sure they're compatible with Surface Hub.</span></span>
-   <span data-ttu-id="71f59-127">Fournir un modèle de base pour toutes les personnes souhaitant créer leurs propres scripts de création ou de validation de compte d’appareil.</span><span class="sxs-lookup"><span data-stu-id="71f59-127">Provide a base template for anyone wanting to create their own device account creation or validation scripts.</span></span>

<span data-ttu-id="71f59-128">Quels sont les éléments nécessaires à l’exécution des scripts?</span><span class="sxs-lookup"><span data-stu-id="71f59-128">What do you need in order to run the scripts?</span></span>

-   <span data-ttu-id="71f59-129">Accès PowerShell à distance au domaine ou client de votre organisation, aux serveurs Exchange et aux serveurs Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="71f59-129">Remote PowerShell access to your organization's domain or tenant, Exchange servers, and Skype for Business servers.</span></span>
-   <span data-ttu-id="71f59-130">Informations d’identification du domaine ou du client de votre organisation, des serveurs Exchange et des serveurs Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="71f59-130">Admin credentials for your organization's domain or tenant, Exchange servers, and Skype for Business servers.</span></span>

> [!NOTE]
> <span data-ttu-id="71f59-131">Qu’il s’agisse de la création d’un nouveau compte ou de la modification d’un compte déjà existant, le script de validation vérifie que votre compte d’appareil est configuré correctement.</span><span class="sxs-lookup"><span data-stu-id="71f59-131">Whether you’re creating a new account or modifying an already-existing account, the validation script will verify that your device account is configured correctly.</span></span> <span data-ttu-id="71f59-132">Vous devez toujours exécuter le script de validation avant d’ajouter un compte d’appareil au Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="71f59-132">You should always run the validation script before adding a device account to Surface Hub.</span></span>

## <span data-ttu-id="71f59-133">Exécution des scripts</span><span class="sxs-lookup"><span data-stu-id="71f59-133">Running the scripts</span></span>

<span data-ttu-id="71f59-134">Les scripts de création de compte permettent d’effectuer les actions suivantes:</span><span class="sxs-lookup"><span data-stu-id="71f59-134">The account creation scripts will:</span></span>

-   <span data-ttu-id="71f59-135">Demander les informations d’identification de l’administrateur</span><span class="sxs-lookup"><span data-stu-id="71f59-135">Ask for administrator credentials</span></span>
-   <span data-ttu-id="71f59-136">Créer des comptes d’appareil sur votre domaine/client</span><span class="sxs-lookup"><span data-stu-id="71f59-136">Create device accounts in your domain/tenant</span></span>
-   <span data-ttu-id="71f59-137">Créer ou affecter une stratégie ActiveSync compatible avec Surface Hub sur le(s) compte(s) d’appareil</span><span class="sxs-lookup"><span data-stu-id="71f59-137">Create or assign a Surface Hub-compatible ActiveSync policy to the device account(s)</span></span>
-   <span data-ttu-id="71f59-138">Définir des attributs différents pour le(s) compte(s) créé(s) dans Exchange et Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="71f59-138">Set various attributes for the created account(s) in Exchange and Skype for Business.</span></span>
-   <span data-ttu-id="71f59-139">Attribuer des licences et des autorisations au(x) compte(s) créé(s)</span><span class="sxs-lookup"><span data-stu-id="71f59-139">Assign licenses and permissions to the created account(s)</span></span>

<span data-ttu-id="71f59-140">Voici les attributs définis par les scripts:</span><span class="sxs-lookup"><span data-stu-id="71f59-140">These are the attributes that are set by the scripts:</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="71f59-141">Applet de commande</span><span class="sxs-lookup"><span data-stu-id="71f59-141">Cmdlet</span></span></th>
<th align="left"><span data-ttu-id="71f59-142">Attribut</span><span class="sxs-lookup"><span data-stu-id="71f59-142">Attribute</span></span></th>
<th align="left"><span data-ttu-id="71f59-143">Valeur</span><span class="sxs-lookup"><span data-stu-id="71f59-143">Value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="71f59-144">Set-Mailbox</span><span class="sxs-lookup"><span data-stu-id="71f59-144">Set-Mailbox</span></span></p></td>
<td align="left"><p><span data-ttu-id="71f59-145">RoomMailboxPassword</span><span class="sxs-lookup"><span data-stu-id="71f59-145">RoomMailboxPassword</span></span></p></td>
<td align="left"><p><span data-ttu-id="71f59-146">Fourni par l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="71f59-146">User-provided</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="71f59-147">EnableRoomMailboxAccount</span><span class="sxs-lookup"><span data-stu-id="71f59-147">EnableRoomMailboxAccount</span></span></p></td>
<td align="left"><p><span data-ttu-id="71f59-148">Vrai</span><span class="sxs-lookup"><span data-stu-id="71f59-148">True</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="71f59-149">Type</span><span class="sxs-lookup"><span data-stu-id="71f59-149">Type</span></span></p></td>
<td align="left"><p><span data-ttu-id="71f59-150">Salle</span><span class="sxs-lookup"><span data-stu-id="71f59-150">Room</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="71f59-151">Set-CalendarProcessing</span><span class="sxs-lookup"><span data-stu-id="71f59-151">Set-CalendarProcessing</span></span></p></td>
<td align="left"><p><span data-ttu-id="71f59-152">AutomateProcessing</span><span class="sxs-lookup"><span data-stu-id="71f59-152">AutomateProcessing</span></span></p></td>
<td align="left"><p><span data-ttu-id="71f59-153">AutoAccept</span><span class="sxs-lookup"><span data-stu-id="71f59-153">AutoAccept</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="71f59-154">RemovePrivateProperty</span><span class="sxs-lookup"><span data-stu-id="71f59-154">RemovePrivateProperty</span></span></p></td>
<td align="left"><p><span data-ttu-id="71f59-155">Faux</span><span class="sxs-lookup"><span data-stu-id="71f59-155">False</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="71f59-156">DeleteSubject</span><span class="sxs-lookup"><span data-stu-id="71f59-156">DeleteSubject</span></span></p></td>
<td align="left"><p><span data-ttu-id="71f59-157">Faux</span><span class="sxs-lookup"><span data-stu-id="71f59-157">False</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="71f59-158">DeleteComments</span><span class="sxs-lookup"><span data-stu-id="71f59-158">DeleteComments</span></span></p></td>
<td align="left"><p><span data-ttu-id="71f59-159">Faux</span><span class="sxs-lookup"><span data-stu-id="71f59-159">False</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="71f59-160">AddOrganizerToSubject</span><span class="sxs-lookup"><span data-stu-id="71f59-160">AddOrganizerToSubject</span></span></p></td>
<td align="left"><p><span data-ttu-id="71f59-161">Faux</span><span class="sxs-lookup"><span data-stu-id="71f59-161">False</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="71f59-162">AddAdditionalResponse</span><span class="sxs-lookup"><span data-stu-id="71f59-162">AddAdditionalResponse</span></span></p></td>
<td align="left"><p><span data-ttu-id="71f59-163">Vrai</span><span class="sxs-lookup"><span data-stu-id="71f59-163">True</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="71f59-164">AdditionalResponse</span><span class="sxs-lookup"><span data-stu-id="71f59-164">AdditionalResponse</span></span></p></td>
<td align="left"><p><span data-ttu-id="71f59-165">&quot;Il s’agit d’une salle Surface Hub!&quot;</span><span class="sxs-lookup"><span data-stu-id="71f59-165">&quot;This is a Surface Hub room!&quot;</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="71f59-166">New-MobileDeviceMailboxPolicy</span><span class="sxs-lookup"><span data-stu-id="71f59-166">New-MobileDeviceMailboxPolicy</span></span></p></td>
<td align="left"><p><span data-ttu-id="71f59-167">PasswordEnabled</span><span class="sxs-lookup"><span data-stu-id="71f59-167">PasswordEnabled</span></span></p></td>
<td align="left"><p><span data-ttu-id="71f59-168">Faux</span><span class="sxs-lookup"><span data-stu-id="71f59-168">False</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="71f59-169">AllowNonProvisionableDevices</span><span class="sxs-lookup"><span data-stu-id="71f59-169">AllowNonProvisionableDevices</span></span></p></td>
<td align="left"><p><span data-ttu-id="71f59-170">Vrai</span><span class="sxs-lookup"><span data-stu-id="71f59-170">True</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="71f59-171">Enable-CSMeetingRoom</span><span class="sxs-lookup"><span data-stu-id="71f59-171">Enable-CSMeetingRoom</span></span></p></td>
<td align="left"><p><span data-ttu-id="71f59-172">RegistrarPool</span><span class="sxs-lookup"><span data-stu-id="71f59-172">RegistrarPool</span></span></p></td>
<td align="left"><p><span data-ttu-id="71f59-173">Fourni par l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="71f59-173">User-provided</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="71f59-174">SipAddress</span><span class="sxs-lookup"><span data-stu-id="71f59-174">SipAddress</span></span></p></td>
<td align="left"><p><span data-ttu-id="71f59-175">Défini sur le nom d’utilisateur principal (UPN) du compte d’appareil</span><span class="sxs-lookup"><span data-stu-id="71f59-175">Set to the User Principal Name (UPN) of the device account</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="71f59-176">Set-MsolUserLicense (O365 uniquement)</span><span class="sxs-lookup"><span data-stu-id="71f59-176">Set-MsolUserLicense (O365 only)</span></span></p></td>
<td align="left"><p><span data-ttu-id="71f59-177">AddLicenses</span><span class="sxs-lookup"><span data-stu-id="71f59-177">AddLicenses</span></span></p></td>
<td align="left"><p><span data-ttu-id="71f59-178">Fourni par l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="71f59-178">User-provided</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="71f59-179">Set-MsolUser (O365 uniquement)</span><span class="sxs-lookup"><span data-stu-id="71f59-179">Set-MsolUser (O365 only)</span></span></p></td>
<td align="left"><p><span data-ttu-id="71f59-180">PasswordNeverExpires</span><span class="sxs-lookup"><span data-stu-id="71f59-180">PasswordNeverExpires</span></span></p></td>
<td align="left"><p><span data-ttu-id="71f59-181">Vrai</span><span class="sxs-lookup"><span data-stu-id="71f59-181">True</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="71f59-182">Set-AdUser (sur site uniquement)</span><span class="sxs-lookup"><span data-stu-id="71f59-182">Set-AdUser (On-prem only)</span></span></p></td>
<td align="left"><p><span data-ttu-id="71f59-183">Activé</span><span class="sxs-lookup"><span data-stu-id="71f59-183">Enabled</span></span></p></td>
<td align="left"><p><span data-ttu-id="71f59-184">Vrai</span><span class="sxs-lookup"><span data-stu-id="71f59-184">True</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="71f59-185">Set-AdUser (sur site uniquement)</span><span class="sxs-lookup"><span data-stu-id="71f59-185">Set-AdUser (On-prem only)</span></span></p></td>
<td align="left"><p><span data-ttu-id="71f59-186">PasswordNeverExpires</span><span class="sxs-lookup"><span data-stu-id="71f59-186">PasswordNeverExpires</span></span></p></td>
<td align="left"><p><span data-ttu-id="71f59-187">Vrai</span><span class="sxs-lookup"><span data-stu-id="71f59-187">True</span></span></p></td>
</tr>
</tbody>
</table>

## <span data-ttu-id="71f59-188">Scripts de création de compte</span><span class="sxs-lookup"><span data-stu-id="71f59-188">Account creation scripts</span></span>

<span data-ttu-id="71f59-189">Ces scripts créent un compte pour vous.</span><span class="sxs-lookup"><span data-stu-id="71f59-189">These scripts will create a device account for you.</span></span> <span data-ttu-id="71f59-190">Vous pouvez utiliser le [Script de vérification de compte](#acct-verification-ps-scripts) pour vous assurer qu’ils se sont exécutés correctement.</span><span class="sxs-lookup"><span data-stu-id="71f59-190">You can use the [Account verification script](#acct-verification-ps-scripts) to make sure they ran correctly.</span></span>

<span data-ttu-id="71f59-191">Les scripts de création de compte ne peuvent pas modifier un compte déjà existant, mais peuvent être utilisés pour vous aider à savoir les applets de commande à exécuter pour configurer correctement le compte existant.</span><span class="sxs-lookup"><span data-stu-id="71f59-191">The account creation scripts cannot modify an already existing account, but can be used to help you understand which cmdlets need to be run to configure the existing account correctly.</span></span>

### <a href="" id="create-on-premises-ps-scripts"></a><span data-ttu-id="71f59-192">Créer un compte local</span><span class="sxs-lookup"><span data-stu-id="71f59-192">Create an on-premises account</span></span>

<span data-ttu-id="71f59-193">Crée un compte, comme décrit dans [Déploiement sur site](on-premises-deployment-surface-hub-device-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="71f59-193">Creates an account as described in [On-premises deployment](on-premises-deployment-surface-hub-device-accounts.md).</span></span>

```PowerShell
# SHAccountCreateOnPrem.ps1

$Error.Clear()
$ErrorActionPreference = "Stop"
$status = @{}

# Cleans up set state such as remote powershell sessions
function Cleanup()
{
    if ($sessExchange)
    {
        Remove-PSSession $sessExchange
    }
    if ($sessCS)
    {
        Remove-PSSession $sessCS
    }
}

function PrintError($strMsg)
{
    Write-Host $strMsg -foregroundcolor Red
}

function PrintSuccess($strMsg)
{
    Write-Host $strMsg -foregroundcolor Green
}

function PrintAction($strMsg)
{
    Write-Host $strMsg -ForegroundColor Cyan
}


# Cleans up and prints an error message
function CleanupAndFail($strMsg)
{
    if ($strMsg)
    {
        PrintError($strMsg);
    }
    Cleanup
    exit 1
}

# Exits if there is an error set and prints the given message
function ExitIfError($strMsg)
{
    if ($Error)
    {
        CleanupAndFail($strMsg);
    }
}

## Collect account data ##
$credNewAccount = (Get-Credential -Message "Enter the desired UPN and password for this new account")
$strUpn = $credNewAccount.UserName
$strDisplayName = Read-Host "Please enter the display name you would like to use for $strUpn"
if (!$credNewAccount -Or [System.String]::IsNullOrEmpty($strDisplayName) -Or [System.String]::IsNullOrEmpty($credNewAccount.UserName) -Or $credNewAccount.Password.Length -le 0)
{
    CleanupAndFail "Please enter all of the requested data to continue."
    exit 1
}

## Sign in to remote powershell for exchange and lync online ##

$credExchange = $null
$credExchange=Get-Credential -Message "Enter credentials of an Exchange user with mailbox creation rights"
if (!$credExchange)
{
    CleanupAndFail("Valid credentials are required to create and prepare the account.");
}
$strExchangeServer = Read-Host "Please enter the FQDN of your exchange server (e.g. exch.contoso.com)"

# Lync info
$credLync = Get-Credential -Message "Enter credentials of a Skype for Business admin (or cancel if they are the same as Exchange)"
if (!$credLync)
{
    $credLync = $credExchange
}
$strLyncFQDN = Read-Host "Please enter the FQDN of your Lync server (e.g. lync.contoso.com) or enter to use [$strExchangeServer]"
if ([System.String]::IsNullOrEmpty($strLyncFQDN))
{
    $strLyncFQDN = $strExchangeServer
}


PrintAction "Connecting to remote sessions. This can occasionally take a while - please do not enter input..."
try
{
    $sessExchange = New-PSSession -ConfigurationName microsoft.exchange -Credential $credExchange -AllowRedirection -Authentication Kerberos -ConnectionUri "http://$strExchangeServer/powershell" -WarningAction SilentlyContinue
}
catch
{
    CleanupAndFail("Failed to connect to exchange. Please check your credentials and try again. If this continues to fail, you may not have permission for remote powershell - if not, please perform the setup manually. Error message: $_")
}
PrintSuccess "Connected to Remote Exchange Shell"

try
{
    $sessLync = New-PSSession -Credential $credLync -ConnectionURI "https://$strLyncFQDN/OcsPowershell" -AllowRedirection -WarningAction SilentlyContinue
}
catch
{
    CleanupAndFail("Failed to connect to Lync. Please check your credentials and try again. Error message: $_")
}
PrintSuccess "Connected to Lync Server Remote PowerShell"


Import-PSSession $sessExchange -AllowClobber -WarningAction SilentlyContinue
Import-PSSession $sessLync -AllowClobber -WarningAction SilentlyContinue

## Create the Exchange mailbox ##
> [!Note]
> These exchange commandlets do not always throw their errors as exceptions

# Because Get-Mailbox will throw an error if the mailbox is not found
$Error.Clear()
PrintAction "Creating a new account..."
try
{
    $mailbox = $null
    $mailbox = (New-Mailbox -UserPrincipalName $credNewAccount.UserName -Alias $credNewAccount.UserName.substring(0,$credNewAccount.UserName.indexOf('@')) -room -Name $strDisplayName -RoomMailboxPassword $credNewAccount.Password -EnableRoomMailboxAccount $true)
} catch { }
ExitIfError "Failed to create a new mailbox on exchange.";
$status["Mailbox Setup"] = "Successfully created a mailbox for the new account"


$strEmail = $mailbox.WindowsEmailAddress
PrintSuccess "The following mailbox has been created for this room: $strEmail"

## Create or retrieve a policy that will be applied to surface hub devices ##
# The policy disables requiring a device password so that the SurfaceHub does not need to be lockable to use Active Sync
$strPolicy = Read-Host 'Please enter the name for a new Surface Hub ActiveSync policy that will be created and applied to this account.
We will configure that policy to be compatible with Surface Hub devices.
If this script has been used before, please enter the name of the existing policy.'

$easpolicy = $null
try {
    $easpolicy = Get-MobileDeviceMailboxPolicy $strPolicy
}
catch {}

if ($easpolicy)
{
    if (!$easpolicy.PasswordEnabled -and ($easpolicy.AllowNonProvisionableDevices -eq $null -or $easpolicy.AllowNonProvisionableDevices ))
    {
        PrintSuccess "An existing policy has been found and will be applied to this account."
    }
    else
    {
        PrintError "The policy you provided is incompatible with the surface hub."
        $easpolicy = $null
        $status["Device Password Policy"] = "Failed to apply the EAS policy to the account because the policy was invalid."
    }
}
else
{
    $Error.Clear()
    PrintAction "Creating policy..."
    $easpolicy = New-MobileDeviceMailboxPolicy -Name $strPolicy -PasswordEnabled $false -AllowNonProvisionableDevices $true
    if ($easpolicy)
    {
        PrintSuccess "A new device policy has been created; you can use this same policy for all future Surface Hub device accounts."
    }
    else
    {
        PrintError "Could not create $strPolicy"
    }
}

if ($easpolicy)
{
    # Convert mailbox to user type so we can apply the policy (necessary)
    # Sometimes it takes a while for this change to take affect so we have some nasty retry loops
    $Error.Clear();
    try
    {
        Set-Mailbox $credNewAccount.UserName -Type Regular
    } catch {}
    if ($Error)
    {
        $Error.Clear()
        $status["Device Password Policy"] = "Failed to apply the EAS policy to the account."
    }
    else
    {
        # Loop until resource type goes away, up to 5 times
        for ($i = 0; $i -lt 5 -And (Get-Mailbox $credNewAccount.UserName).ResourceType; $i++)
        {
            Start-Sleep -s 5
        }
        # If the mailbox is still a Room we cannot apply the policy
        if (!((Get-Mailbox $credNewAccount.UserName).ResourceType))
        {
            $Error.Clear()
            # Set policy for account
            Set-CASMailbox $credNewAccount.UserName -ActiveSyncMailboxPolicy $strPolicy
            if (!$Error)
            {
                $status["ActiveSync Policy"] = "Successfully applied $strPolicy to the account"
            }
            else
            {
                $status["ActiveSync Policy"] = "Failed to apply the EAS policy to the account."
            }
            $Error.Clear()

            # Convert back to room mailbox
            Set-Mailbox $credNewAccount.UserName -Type Room
            # Loop until resource type goes back to room
            for ($i = 0; ($i -lt 5) -And ((Get-Mailbox $credNewAccount.UserName).ResourceType -ne "Room"); $i++)
            {
                Start-Sleep -s 5
            }
            if ((Get-Mailbox $credNewAccount.UserName).ResourceType -ne "Room")
            {
                # A failure to convert the mailbox back to a room is unfortunate but means the mailbox is unusable.
                $status["Mailbox Setup"] = "A mailbox was created but we could not set it to a room resource type."
            }
            else
            {
                try
                {
                    Set-Mailbox $credNewAccount.UserName -RoomMailboxPassword $credNewAccount.Password -EnableRoomMailboxAccount $true
                } catch { }
                if ($Error)
                {
                    $status["Mailbox Setup"] = "A room mailbox was created but we could not set its password."
                }
                $Error.Clear()
            }

        }
    }
}
PrintSuccess "Account creation completed."

PrintAction "Setting calendar processing rules..."

$Error.Clear();
## Prepare the calendar for automatic meeting responses ##
try {
    Set-CalendarProcessing -Identity $credNewAccount.UserName -AutomateProcessing AutoAccept
} catch { }
if ($Error)
{
    $status["Calendar Acceptance"] = "Failed to configure the account to automatically accept/decline meeting requests"
}
else
{
    $status["Calendar Acceptance"] = "Successfully configured the account to automatically accept/decline meeting requests"
}


$Error.Clear()
try {
    Set-CalendarProcessing -Identity $credNewAccount.UserName -RemovePrivateProperty $false -AddOrganizerToSubject $false -AddAdditionalResponse $true -DeleteSubject $false -DeleteComments $false -AdditionalResponse "This is a Surface Hub room!"
} catch { }
if ($Error)
{
    $status["Calendar Response Configuration"] = "Failed to configure the account's response properties"
}
else
{
    $status["Calendar Response Configuration"] = "Successfully configured the account's response properties"
}

$Error.Clear()
## Configure the Account to not expire ##
PrintAction "Configuring password not to expire..."
Start-Sleep -s 20
try
{
    Set-AdUser $mailbox.UserPrincipalName -PasswordNeverExpires $true -Enabled $true
}
catch
{

}

if ($Error)
{
    $status["Password Expiration Policy"] = "Failed to set the password to never expire"
}
else
{
    $status["Password Expiration Policy"] = "Successfully set the password to never expire"
}

PrintSuccess "Completed Exchange configuration"

## Setup Skype for Business. This is somewhat optional and if it fails we SfbEnable can be used later ##
PrintAction "Configuring account for Skype for Business."

# Getting registrar pool
$strRegPool = $strLyncFQDN
$Error.Clear()
$strRegPoolEntry = Read-Host "Enter a Skype for Business Registrar Pool, or leave blank to use [$strRegPool]"
if (![System.String]::IsNullOrEmpty($strRegPoolEntry))
{
    $strRegPool = $strRegPoolEntry
}

# Try to SfB-enable the account. Note that it may not work right away as the account needs to propagate to active directory
PrintAction "Enabling Skype for Business..."
Start-Sleep -s 10
$Error.Clear()
try {
    Enable-CsMeetingRoom -Identity $credNewAccount.UserName -RegistrarPool $strRegPool -SipAddressType EmailAddress
}
catch { }

if ($Error)
{
    $status["Skype for Business Account Setup"] = "Failed to setup the Skype for Business meeting room - you can run EnableSfb.ps1 to try again."
    $Error.Clear();
}
else
{
    $status["Skype for Business Account Setup"] = "Successfully enabled account as a Skype for Business meeting room"
}

Write-Host

## Cleanup and print results ##
Cleanup
$strDisplay = $mailbox.DisplayName
$strUsr = $credNewAccount.UserName
PrintAction "Summary for creation of $strUsr ($strDisplay)"
if ($status.Count -gt 0)
{
    ForEach($k in $status.Keys)
    {
        $v = $status[$k]
        $color = "yellow"
        if ($v[0] -eq "S") { $color = "green" }
        elseif ($v[0] -eq "F")
        {
            $color = "red"
            $v += " Go to https://aka.ms/shubtshoot"
        }

        Write-Host -NoNewline $k -ForegroundColor $color
        Write-Host -NoNewline ": "
        Write-Host $v
    }
}
else
{
    PrintError "The account could not be created"
}
```

### <a href="" id="create-os356-ps-scripts"></a><span data-ttu-id="71f59-194">Créer un compte d’appareil à l’aide d’Office 365</span><span class="sxs-lookup"><span data-stu-id="71f59-194">Create a device account using Office 365</span></span>

<span data-ttu-id="71f59-195">Crée un compte, comme décrit dans [Créer un compte d’appareil à l’aide d’Office365](create-a-device-account-using-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="71f59-195">Creates an account as described in [Create a device account using Office 365](create-a-device-account-using-office-365.md)</span></span>

```PowerShell
# SHAccountCreateO365.ps1

$Error.Clear()
$ErrorActionPreference = "Stop"
$status = @{}

# Cleans up set state such as remote powershell sessions
function Cleanup()
{
    if ($sessExchange)
    {
        Remove-PSSession $sessExchange
    }
    if ($sessCS)
    {
        Remove-PSSession $sessCS
    }
}

function PrintError($strMsg)
{
    Write-Host $strMsg -foregroundcolor Red
}

function PrintSuccess($strMsg)
{
    Write-Host $strMsg -foregroundcolor Green
}

function PrintAction($strMsg)
{
    Write-Host $strMsg -ForegroundColor Cyan
}


# Cleans up and prints an error message
function CleanupAndFail($strMsg)
{
    if ($strMsg)
    {
        PrintError($strMsg);
    }
    Cleanup
    exit 1
}

# Exits if there is an error set and prints the given message
function ExitIfError($strMsg)
{
    if ($Error)
    {
        CleanupAndFail($strMsg);
    }
}


## Check dependencies ##
try {
    Import-Module SkypeOnlineConnector
    Import-Module MSOnline
}
catch
{
    PrintError "Some dependencies are missing"
    PrintError "Please install the Windows PowerShell Module for Lync Online. For more information go to https://www.microsoft.com/download/details.aspx?id=39366"
    PrintError "Please install the Azure Active Directory module for PowerShell from https://go.microsoft.com/fwlink/p/?linkid=236297"
    CleanupAndFail
}



## Collect account data ##
$credNewAccount = (Get-Credential -Message "Enter the desired UPN and password for this new account")
$strUpn = $credNewAccount.UserName
$strDisplayName = Read-Host "Please enter the display name you would like to use for $strUpn"
if (!$credNewAccount -Or [System.String]::IsNullOrEmpty($strDisplayName) -Or [System.String]::IsNullOrEmpty($credNewAccount.UserName) -Or $credNewAccount.Password.Length -le 0)
{
    CleanupAndFail "Please enter all of the requested data to continue."
    exit 1
}


## Sign in to remote powershell for exchange and lync online ##
$credAdmin = $null
$credAdmin=Get-Credential -Message "Enter credentials of an Exchange and Skype for Business admin"
if (!$credadmin)
{
    CleanupAndFail "Valid admin credentials are required to create and prepare the account."
}
PrintAction "Connecting to remote sessions. This can occasionally take a while - please do not enter input..."
try
{
    $sessExchange = New-PSSession -ConfigurationName microsoft.exchange -Credential $credAdmin -AllowRedirection -Authentication basic -ConnectionUri "https://outlook.office365.com/powershell-liveid/" -WarningAction SilentlyContinue
}
catch
{
    CleanupAndFail "Failed to connect to exchange. Please check your credentials and try again. Error message: $_"
}

try
{
    $sessCS = New-CsOnlineSession -Credential $credAdmin
}
catch
{
    CleanupAndFail "Failed to connect to Skype for Business Online Datacenter. Please check your credentials and try again. Error message: $_"
}

try
{
    Connect-MsolService -Credential $credAdmin
}
catch
{
    CleanupAndFail "Failed to connect to Azure Active Directory. Please check your credentials and try again. Error message: $_"
}

Import-PSSession $sessExchange -AllowClobber -WarningAction SilentlyContinue
Import-PSSession $sessCS -AllowClobber -WarningAction SilentlyContinue

## Create the Exchange mailbox ##
> [!Note]
> These exchange commandlets do not always throw their errors as exceptions

# Because Get-Mailbox will throw an error if the mailbox is not found
$Error.Clear()
PrintAction "Creating a new account..."
try
{
    $mailbox = $null
    $mailbox = (New-Mailbox -MicrosoftOnlineServicesID $credNewAccount.UserName -room -Name $strDisplayName -RoomMailboxPassword $credNewAccount.Password -EnableRoomMailboxAccount $true)
} catch { }
ExitIfError "Failed to create a new mailbox on exchange.";
$status["Mailbox Setup"] = "Successfully created a mailbox for the new account"


$strEmail = $mailbox.WindowsEmailAddress
PrintSuccess "The following mailbox has been created for this room: $strEmail"


## Create or retrieve a policy that will be applied to surface hub devices ##
# The policy disables requiring a device password so that the SurfaceHub does not need to be lockable to use Active Sync
$strPolicy = Read-Host 'Please enter the name for a new Surface Hub ActiveSync policy that will be created and applied to this account.
We will configure that policy to be compatible with Surface Hub devices.
If this script has been used before, please enter the name of the existing policy.'

$easpolicy = $null
try {
    $easpolicy = Get-MobileDeviceMailboxPolicy $strPolicy
}
catch {}

if ($easpolicy)
{
    if (!$easpolicy.PasswordEnabled -and ($easpolicy.AllowNonProvisionableDevices -eq $null -or $easpolicy.AllowNonProvisionableDevices ))
    {
        PrintSuccess "An existing policy has been found and will be applied to this account."
    }
    else
    {
        PrintError "The policy you provided is incompatible with the surface hub."
        $easpolicy = $null
        $status["ActiveSync Policy"] = "Failed to apply the EAS policy to the account because the policy was invalid."
    }
}
else
{
    $Error.Clear()
    PrintAction "Creating policy..."
    $easpolicy = New-MobileDeviceMailboxPolicy -Name $strPolicy -PasswordEnabled $false -AllowNonProvisionableDevices $true
    if ($easpolicy)
    {
        PrintSuccess "A new device policy has been created; you can use this same policy for all future Surface Hub device accounts."
    }
    else
    {
        PrintError "Could not create $strPolicy"
    }
}

if ($easpolicy)
{
    # Convert mailbox to user type so we can apply the policy (necessary)
    # Sometimes it takes a while for this change to take affect so we have some nasty retry loops
    $Error.Clear();
    try
    {
        Set-Mailbox $credNewAccount.UserName -Type Regular
    } catch {}
    if ($Error)
    {
        $Error.Clear()
        $status["Device Password Policy"] = "Failed to apply the EAS policy to the account."
        PrintError "Failed to convert to regular account"
    }
    else
    {
        # Loop until resource type goes away, up to 5 times
        for ($i = 0; $i -lt 5 -And (Get-Mailbox $credNewAccount.UserName).ResourceType; $i++)
        {
            Start-Sleep -s 5
        }
        # If the mailbox is still a Room we cannot apply the policy
        if (!((Get-Mailbox $credNewAccount.UserName).ResourceType))
        {
            $Error.Clear()
            # Set policy for account
            Set-CASMailbox $credNewAccount.UserName -ActiveSyncMailboxPolicy $strPolicy
            if (!$Error)
            {
                $status["Device Password Policy"] = "Successfully applied $strPolicy to the account"
            }
            else
            {
                $status["Device Password Policy"] = "Failed to apply the EAS policy to the account."
                PrintError "Failed to apply policy"
            }
            $Error.Clear()

            # Convert back to room mailbox
            Set-Mailbox $credNewAccount.UserName -Type Room
            # Loop until resource type goes back to room
            for ($i = 0; ($i -lt 5) -And ((Get-Mailbox $credNewAccount.UserName).ResourceType -ne "Room"); $i++)
            {
                Start-Sleep -s 5
            }
            if ((Get-Mailbox $credNewAccount.UserName).ResourceType -ne "Room")
            {
                # A failure to convert the mailbox back to a room is unfortunate but means the mailbox is unusable.
                $status["Mailbox Setup"] = "A mailbox was created but we could not set it to a room resource type."
            }
            else
            {
                Set-Mailbox $credNewAccount.UserName -RoomMailboxPassword $credNewAccount.Password -EnableRoomMailboxAccount $true
                if ($Error)
                {
                    $status["Mailbox Setup"] = "A room mailbox was created but we could not set its password."
                }
                $Error.Clear()
            }

        }
    }
}
else
{
    $status["Device Password Policy"] = "Failed to apply the EAS policy to the account."
    PrintError "Failed to obtain policy"
}
PrintSuccess "Account creation completed."

PrintAction "Setting calendar processing rules..."

$Error.Clear();
## Prepare the calendar for automatic meeting responses ##
try {
    Set-CalendarProcessing -Identity $credNewAccount.UserName -AutomateProcessing AutoAccept
} catch { }
if ($Error)
{
    $status["Calendar Acceptance"] = "Failed to configure the account to automatically accept/decline meeting requests"
}
else
{
    $status["Calendar Acceptance"] = "Successfully configured the account to automatically accept/decline meeting requests"
}


$Error.Clear()
try {
    Set-CalendarProcessing -Identity $credNewAccount.UserName -RemovePrivateProperty $false -AddOrganizerToSubject $false -AddAdditionalResponse $true -DeleteSubject $false -DeleteComments $false -AdditionalResponse "This is a Surface Hub room!"
} catch { }
if ($Error)
{
    $status["Calendar Response Configuration"] = "Failed to configure the account's response properties"
}
else
{
    $status["Calendar Response Configuration"] = "Successfully configured the account's response properties"
}

$Error.Clear()
## Configure the Account to not expire ##
PrintAction "Configuring password not to expire..."
try
{
    Set-MsolUser -UserPrincipalName $credNewAccount.UserName -PasswordNeverExpires $true
}
catch
{

}

if ($Error)
{
    $status["Password Expiration Policy"] = "Failed to set the password to never expire"
}
else
{
    $status["Password Expiration Policy"] = "Successfully set the password to never expire"
}

PrintSuccess "Completed Exchange configuration"

## Setup Skype for Business. This is somewhat optional and if it fails we SfbEnable can be used later ##
PrintAction "Configuring account for Skype for Business."

# Getting registrar pool
$strRegPool = $null
try {
    $strRegPool = (Get-CsTenant).TenantPoolExtension
}
catch {}
$Error.Clear()
if (![System.String]::IsNullOrEmpty($strRegPool))
{
    $strRegPool = $strRegPool.Substring($strRegPool[0].IndexOf(':') + 1)
}
<#
$strRegPoolEntry = Read-Host "Enter a Skype for Business Registrar Pool, or leave blank to use [$strRegPool]"
if (![System.String]::IsNullOrEmpty($strRegPoolEntry))
{
    $strRegPool = $strRegPoolEntry
}
#>

# Try to SfB-enable the account. Note that it may not work right away as the account needs to propagate to active directory
PrintAction "Enabling Skype for Business on $strRegPool"
Start-Sleep -s 10
$Error.Clear()
try {
    Enable-CsMeetingRoom -Identity $credNewAccount.UserName -RegistrarPool $strRegPool -SipAddressType EmailAddress
}
catch { }

if ($Error)
{
    $status["Skype for Business Account Setup"] = "Failed to setup the Skype for Business meeting room - you can run EnableSfb.ps1 to try again."
    $Error.Clear();
}
else
{
    $status["Skype for Business Account Setup"] = "Successfully enabled account as a Skype for Business meeting room"
}

## Now we need to assign a Skype for Business license to the account ##
# Assign a license to thes
$countryCode = (Get-CsTenant).CountryAbbreviation
$loc = Read-Host "Please enter the usage location for this device account (where the account is being used). This is a 2-character code that is used to assign licenses (e.g. $countryCode)"
try {
    $Error.Clear()
    Set-MsolUser -UserPrincipalName $credNewAccount.UserName -UsageLocation $loc
}
catch{}
if ($Error)
{
    $status["Office 365 License"] = "Failed to assign an Office 365 license to the account"
    $Error.Clear()
}
else
{
    PrintAction "We found the following licenses available for your tenant:"
    $skus = (Get-MsolAccountSku | Where-Object { !$_.AccountSkuID.Contains("INTUNE"); })
    $i = 1
    $skus | % {
     Write-Host -NoNewline $i
     Write-Host -NoNewLine ": AccountSKUID: "
     Write-Host -NoNewLine $_.AccountSkuid
     Write-Host -NoNewLine " Active Units: "
     Write-Host -NoNewLine $_.ActiveUnits
     Write-Host -NoNewLine " Consumed Units: "
     Write-Host $_.ConsumedUnits
     $i++
    }
    $iLicenseIndex = 0;
    do
    {
        $iLicenseIndex = Read-Host 'Choose the number for the SKU you want to pick'
    } while ($iLicenseIndex -lt 1 -or $iLicenseIndex -gt $skus.Length)
    $strLicenses = $skus[$iLicenseIndex - 1].AccountSkuId

    if (![System.String]::IsNullOrEmpty($strLicenses))
    {
        try
        {
            $Error.Clear()
            Set-MsolUserLicense -UserPrincipalName $credNewAccount.UserName -AddLicenses $strLicenses
        }
        catch
        {

        }
        if ($Error)
        {
            $Error.Clear()
            $status["Office 365 License"] = "Failed to add a license to the account. Make sure you have remaining licenses."
        }
        else
        {
            $status["Office 365 License"] = "Successfully added license to the account"
        }
    }
    else
    {
        $status["Office 365 License"] = "You opted not to install a license on this account"
    }
}


Write-Host

## Cleanup and print results ##
Cleanup
$strDisplay = $mailbox.DisplayName
$strUsr = $credNewAccount.UserName
PrintAction "Summary for creation of $strUsr ($strDisplay)"
if ($status.Count -gt 0)
{
    ForEach($k in $status.Keys)
    {
        $v = $status[$k]
        $color = "yellow"
        if ($v[0] -eq "S") { $color = "green" }
        elseif ($v[0] -eq "F")
        {
            $color = "red"
            $v += " Go to https://aka.ms/shubtshoot for help"
        }

        Write-Host -NoNewline $k -ForegroundColor $color
        Write-Host -NoNewline ": "
        Write-Host $v
    }
}
else
{
    PrintError "The account could not be created"
}
```

## <a href="" id="acct-verification-ps-scripts"></a><span data-ttu-id="71f59-196">Script de vérification de compte</span><span class="sxs-lookup"><span data-stu-id="71f59-196">Account verification script</span></span>

<span data-ttu-id="71f59-197">Ce script valide le compte d’appareil créé précédemment sur Surface Hub et Surface Hub 2S, quelle que soit la méthode utilisée pour le créer.</span><span class="sxs-lookup"><span data-stu-id="71f59-197">This script validates the previously-created device account on Surface Hub and Surface Hub 2S, no matter which method was used to create it.</span></span> <span data-ttu-id="71f59-198">Ce script est de type réussite/échec.</span><span class="sxs-lookup"><span data-stu-id="71f59-198">This script is basically pass/fail.</span></span> <span data-ttu-id="71f59-199">En cas d’erreur à l’un des tests, un message d’erreur s’affiche, tandis que si tous les tests réussissent, le résultat final obtenu est un rapport de synthèse.</span><span class="sxs-lookup"><span data-stu-id="71f59-199">If one of the test errors out, it will show a detailed error message, but if all tests pass, the end result will be a summary report.</span></span> <span data-ttu-id="71f59-200">Par exemple, voici ce que vous pouvez voir:</span><span class="sxs-lookup"><span data-stu-id="71f59-200">For example, you might see:</span></span>

``` syntax
15 tests executed
0 failures
2 warnings
15 passed
```

<span data-ttu-id="71f59-201">Les détails relatifs aux paramètres spécifiques ne s’affichent pas.</span><span class="sxs-lookup"><span data-stu-id="71f59-201">Details of specific settings will not be shown.</span></span>

```PowerShell
# SHAccountValidate.ps1

$Error.Clear()
$ErrorActionPreference = "Stop"


# Cleans up set state such as remote powershell sessions
function Cleanup()
{
    if ($sessEx)
    {
        Remove-PSSession $sessEx
    }
    if ($sessSfb)
    {
        Remove-PSSession $sessSfb
    }
}

function PrintError($strMsg)
{
    Write-Host $strMsg -foregroundcolor "red"
}

function PrintSuccess($strMsg)
{
    Write-Host $strMsg -foregroundcolor "green"
}

function PrintAction($strMsg)
{
    Write-Host $strMsg -ForegroundColor Cyan
}


# Cleans up and prints an error message
function CleanupAndFail($strMsg)
{
    if ($strMsg)
    {
        PrintError($strMsg);
    }
    Cleanup
    exit 1
}

# Exits if there is an error set and prints the given message
function ExitIfError($strMsg)
{
    if ($Error)
    {
        CleanupAndFail($strMsg);
    }
}

$strUpn = Read-Host "What is the email address of the account you wish to validate?"
if (!$strUpn.Contains('@'))
{
    CleanupAndFail "$strUpn is not a valid email address"
}
$strExServer = Read-Host "What is your exchange server? (leave blank for online tenants)"
if ($strExServer.Equals(""))
{
    $fExIsOnline = $true
}
else
{
    $fExIsOnline = $false
}
$credEx = Get-Credential -Message "Please provide exchange user credentials"

$strRegistrarPool = Read-Host ("What is the Skype for Business registrar pool for $strUpn" + "? (leave blank for online tenants)")
$fSfbIsOnline = $strRegistrarPool.Equals("")

$fHasOnPrem = $true
if ($fSfbIsOnline -and $fExIsOnline)
{
    do
    {
        $strHasOnPrem = (Read-Host "Do you have an on-premises Active Directory (Y/N) (No if your domain services are hosted entirely online)").ToUpper()
    } while ($strHasOnPrem -ne "Y" -and $strHasOnPrem -ne "N")
    $fHasOnPrem = $strHasOnPrem.Equals("Y")
}

$fHasOnline = $false
if ($fSfbIsOnline -or $fExIsOnline)
{
    $fHasOnline = $true
}

if ($fSfbIsOnline)
{
    try {
        Import-Module SkypeOnlineConnector
    }
    catch
    {
        CleanupAndFail "To verify Skype for Business in online tenants you need the Lync Online Connector module from https://www.microsoft.com/download/details.aspx?id=39366"
    }
}
else
{
    $credSfb = (Get-Credential -Message "Please enter Skype for Business admin credentials")
}

if ($fHasOnline)
{
    $credSfb = $credEx
    try {
        Import-Module MSOnline
    }
    catch
    {
        CleanupAndFail "To verify accounts in online tenants you need the Azure Active Directory module for PowerShell from https://go.microsoft.com/fwlink/p/?linkid=236297"
    }
}

PrintAction "Connecting to Exchange Powershell Session..."
[System.Management.Automation.Runspaces.AuthenticationMechanism] $authType = [System.Management.Automation.Runspaces.AuthenticationMechanism]::Kerberos
if ($fExIsOnline)
{
    $authType = [System.Management.Automation.Runspaces.AuthenticationMechanism]::Basic
}
try
{
    $sessEx = $null
    if ($fExIsOnline)
    {
        $sessEx = New-PSSession -ConfigurationName microsoft.exchange -Credential $credEx -AllowRedirection -Authentication $authType -ConnectionUri "https://outlook.office365.com/powershell-liveid/" -WarningAction SilentlyContinue
    }
    else
    {
        $sessEx = New-PSSession -ConfigurationName microsoft.exchange -Credential $credEx -AllowRedirection -Authentication $authType -ConnectionUri https://$strExServer/powershell -WarningAction SilentlyContinue
    }
}
catch
{
}

if (!$sessEx)
{
    CleanupAndFail "Connecting to Exchange Powershell failed, please validate your server is accessible and credentials are correct"
}

PrintSuccess "Connected to Exchange Powershell Session"

PrintAction "Connecting to Skype for Business Powershell Session..."

if ($fSfbIsOnline)
{
    $sessSfb = New-CsOnlineSession -Credential $credSfb
}
else
{
    $sessSfb = New-PSSession -Credential $credSfb -ConnectionURI "https://$strRegistrarPool/OcsPowershell" -AllowRedirection -WarningAction SilentlyContinue
}

if (!$sessSfb)
{
    CleanupAndFail "Connecting to Skype for Business Powershell failed, please validate your server is accessible and credentials are correct"
}

PrintSuccess "Connected to Skype for Business Powershell"

if ($fHasOnline)
{
    $credMsol = $null
    if ($fExIsOnline)
    {
        $credMsol = $credEx
    }
    elseif ($fSfbIsOnline)
    {
        $credMsol = $credSfb
    }
    else
    {
        CleanupAndFail "Internal error - could not determine MS Online credentials"
    }
    try
    {
        PrintAction "Connecting to Azure Active Directory Services..."
        Connect-MsolService -Credential $credMsol
        PrintSuccess "Connected to Azure Active Directory Services"
    }
    catch
    {
        # This really shouldn't happen unless there is a network error
        CleanupAndFail "Failed to connect to MSOnline"
    }
}


PrintAction "Importing remote sessions into the local session..."
try
{
    $importEx = Import-PSSession $sessEx -AllowClobber -WarningAction SilentlyContinue -DisableNameChecking
    $importSfb = Import-PSSession $sessSfb -AllowClobber -WarningAction SilentlyContinue -DisableNameChecking
}
catch
{
}
if (!$importEx -or !$importSfb)
{
    CleanupAndFail "Import failed"
}
PrintSuccess "Import successful"


$mailbox = $null
try
{
    $mailbox = Get-Mailbox -Identity $strUpn
}
catch
{
}

if (!$mailbox)
{
    CleanupAndFail "Account exists check failed. Unable to find the mailbox for $strUpn - please make sure the Exchange account exists on $strExServer"
}

$exchange = $null
if (!$fExIsOnline)
{
    $exchange = Get-ExchangeServer
    if (!$exchange -or !$exchange.IsE14OrLater)
    {
        CleanupAndFail "A compatible exchange server version was not found. Please use at least exchange 2010."
    }
}


$strAlias = $mailbox.UserPrincipalName
$strDisplayName = $mailbox.DisplayName

$strLinkedAccount = $strLinkedDomain = $strLinkedUser = $strLinkedServer = $null
$credLinkedDomain = $Null
if (!$fExIsOnline -and ![System.String]::IsNullOrEmpty($mailbox.LinkedMasterAccount) -and !$mailbox.LinkedMasterAccount.EndsWith("\SELF"))
{
    $strLinkedAccount = $mailbox.LinkedMasterAccount
    $strLinkedDomain = $strLinkedAccount.substring(0,$strLinkedAccount.IndexOf('\'))
    $strLinkedUser = $strLinkedAccount.substring($strLinkedAccount.IndexOf('\') + 1)
    $strLinkedServer = Read-Host "What is the domain controller for the $strLinkedDomain"
    $credLinkedDomain = (Get-Credential -Message "Please provide credentials for $strLinkedDomain")
}







Write-Host
Write-Host
Write-Host
PrintAction "Performing verification checks on $strDisplayName..."
$Global:iTotalFailures = 0
$global:iTotalWarnings = 0
$Global:iTotalPasses = 0

function Validate()
{
    Param(
        [string]$Test,
        [bool]  $Condition,
        [string]$FailureMsg,
        [switch]$WarningOnly
    )

    Write-Host -NoNewline -ForegroundColor White $Test.PadRight(100,'.')
    if ($Condition)
    {
        Write-Host -ForegroundColor Green "Passed"
        $global:iTotalPasses++
    }
    else
    {
        if ($WarningOnly)
        {
            Write-Host -ForegroundColor Yellow ("Warning: "+$FailureMsg)
            $global:iTotalWarnings++
        }
        else
        {
            Write-Host -ForegroundColor Red ("Failed: "+$FailureMsg)
            $global:iTotalFailures++
        }
    }
}

## Exchange ##

Validate -WarningOnly -Test "The mailbox $strUpn is enabled as a room account" -Condition ($mailbox.RoomMailboxAccountEnabled -eq $True) -FailureMsg "RoomMailboxEnabled - without a device account, the Surface Hub will not be able to use various key features."
$calendarProcessing = Get-CalendarProcessing -Identity $strUpn -WarningAction SilentlyContinue -ErrorAction SilentlyContinue
Validate -Test "The mailbox $strUpn is configured to accept meeting requests" -Condition ($calendarProcessing -ne $null -and $calendarProcessing.AutomateProcessing -eq 'AutoAccept') -FailureMsg "AutomateProcessing - the Surface Hub will not be able to send mail or sync its calendar."
Validate -WarningOnly -Test "The mailbox $strUpn will not delete meeting comments" -Condition ($calendarProcessing -ne $null -and !$calendarProcessing.DeleteComments) -FailureMsg "DeleteComments - the Surface Hub may be missing some meeting information on the welcome screen and Skype."
Validate -WarningOnly -Test "The mailbox $strUpn keeps private meetings private" -Condition ($calendarProcessing -ne $null -and !$calendarProcessing.RemovePrivateProperty) -FailureMsg "RemovePrivateProperty - the Surface Hub will make show private meetings."
Validate -Test "The mailbox $strUpn keeps meeting subjects" -Condition ($calendarProcessing -ne $null -and !$calendarProcessing.DeleteSubject) -FailureMsg "DeleteSubject - the Surface Hub will not keep meeting subject information."
Validate -WarningOnly -Test "The mailbox $strUpn does not prepend meeting organizers to subjects" -Condition ($calendarProcessing -ne $null -and !$calendarProcessing.AddOrganizerToSubject) -FailureMsg "AddOrganizerToSubject - the Surface Hub will not display meeting subjects as intended."

if ($fExIsOnline)
{
    #No online specifics
}
else
{
    #No onprem specifics
}

#ActiveSync
$casMailbox = Get-Casmailbox $strUpn -WarningAction SilentlyContinue -ErrorAction SilentlyContinue
Validate -Test "The mailbox $strUpn has a mailbox policy" -Condition ($casMailbox -ne $null) -FailureMsg "PasswordEnabled - unable to find policy - the Surface Hub will not be able to send mail or sync its calendar."
if ($casMailbox)
{
    $policy = $null
    if ($fExIsOnline -or $exchange.IsE15OrLater)
    {
        $strPolicy = $casMailbox.ActiveSyncMailboxPolicy
        $policy = Get-MobileDeviceMailboxPolicy -Identity $strPolicy -WarningAction SilentlyContinue -ErrorAction SilentlyContinue
        Validate -Test "The policy $strPolicy does not require a device password" -Condition ($policy.PasswordEnabled -ne $True) -FailureMsg "PasswordEnabled - policy requires a device password - the Surface Hub will not be able to send mail or sync its calendar."
    }
    else
    {
        $strPolicy = $casMailbox.ActiveSyncMailboxPolicy
        $policy = Get-ActiveSyncMailboxPolicy -Identity $strPolicy -WarningAction SilentlyContinue -ErrorAction SilentlyContinue
        Validate -Test "The policy $strPolicy does not require a device password" -Condition ($policy.PasswordEnabled -ne $True) -FailureMsg "PasswordEnabled - policy requires a device password - the Surface Hub will not be able to send mail or sync its calendar."
    }

    if ($policy -ne $null)
    {
        Validate -Test "The policy $strPolicy allows non-provisionable devices" -Condition ($policy.AllowNonProvisionableDevices -eq $null -or $policy.AllowNonProvisionableDevices -eq $true) -FailureMsg "AllowNonProvisionableDevices - policy will not allow the SurfaceHub to sync"
    }

}


# Check the default access level
$orgSettings = Get-ActiveSyncOrganizationSettings
$strDefaultAccessLevel = $orgSettings.DefaultAccessLevel
Validate -Test "ActiveSync devices are allowed" -Condition ($strDefaultAccessLevel -eq 'Allow') -FailureMsg "DeviceType Windows Mail is accessible - devices are not allowed by default - the surface hub will not be able to send mail or sync its calendar."

# Check if there exists a device access rule that bans the device type Windows Mail
$blockingRules = Get-ActiveSyncDeviceAccessRule | where {($_.AccessLevel -eq 'Block' -or $_.AccessLevel -eq 'Quarantine') -and $_.Characteristic -eq 'DeviceType'-and $_.QueryString -eq 'WindowsMail'}
Validate -Test "Windows mail devices are not blocked or quarantined" -Condition ($blockingRules -eq $null -or $blockingRules.Length -eq 0) -FailureMsg "DeviceType Windows Mail is accessible - devices are blocked or quarantined - the surface hub will not be able to send mail or sync its calendar."

## End Exchange ##



## SfB ##
$strLyncIdentity = $null
if ($fSfbIsOnline)
{
    $strLyncIdentity = $strUpn
}
else
{
    $strLyncIdentity = $strAlias
}

$lyncAccount = $null
try {
    $lyncAccount = Get-CsMeetingRoom -Identity $strLyncIdentity -WarningAction SilentlyContinue -ErrorAction SilentlyContinue
} catch {
    try {
        $lyncAccount = Get-CsUser -Identity $strLyncIdentity -WarningAction SilentlyContinue -ErrorAction SilentlyContinue
    } catch { }
}
Validate -Test "There is a Lync or Skype for Business account for $strLyncIdentity" -Condition ($lyncAccount -ne $null -and $lyncAccount.Enabled) -FailureMsg "SfB Enabled - there is no Skype for Business account - meetings will not support Skype for Business"
if ($lyncAccount)
{
    Validate -Test "The meeting room has a SIP address" -Condition (![System.String]::IsNullOrEmpty($lyncAccount.SipAddress)) -FailureMsg "SfB Enabled - there is no SIP Address - the device account cannot be used to sign into Skype for Business."
}
## End SFB ##


if ($fHasOnline)
{
    #License validation and password expiry
    $accountOnline = Get-MsolUser -UserPrincipalName $strUpn -WarningAction SilentlyContinue -ErrorAction SilentlyContinue
    Validate -Test "There is an online user account for $strUpn" -Condition ($accountOnline -ne $null) -FailureMsg "Could not find a Microsoft Online account for this user even though some services are online"
    if ($accountOnline)
    {
        Validate -Test "The password for $strUpn will not expire" -Condition ($accountOnline.PasswordNeverExpires -eq $True) -FailureMsg "PasswordNeverExpires - the admin will need to update the device account's password on the Surface Hub when it expires."
        if ($fIsSfbOnline -and !$fIsExOnline)
        {
            $strLicenseFailureMsg = "Has O365 license - The devices will not be able to use Skype for Business services."
        }
        elseif ($fIsExOnline -and !$fIsSfbOnline)
        {
            $strLicenseFailureMsg = "Has O365 license - The devices will not be able to use Exchange Online services."
        }
        else
        {
            $strLicenseFailureMsg = "Has O365 license - The devices will not be able to use Skype for Business or Exchange Online services."
        }
        Validate -Test "$strUpn is licensed" -Condition ($accountOnline.IsLicensed -eq $True) -FailureMsg $strLicenseFailureMsg

        Validate -Test "$strUpn is allowed to sign in" -Condition ($accountOnline.BlockCredential -ne $True) -FailureMsg "BlockCredential - This user is not allowed to sign in."
    }
}

#If there is an on-prem component, we can get the authoritative AD user from mailbox
if ($fHasOnPrem)
{
    $accountOnPrem = $null
    if ($strLinkedAccount)
    {
        $accountOnPrem = Get-AdUser $strLinkedUser -server $strLinkedServer -credential $credLinkedDomain -properties PasswordNeverExpires -WarningAction SilentlyContinue -ErrorAction SilentlyContinue
    }
    else
    {
        #AD User enabled validation
        $accountOnPrem = Get-AdUser $mailbox.UserPrincipalName -properties PasswordNeverExpires -WarningAction SilentlyContinue -ErrorAction SilentlyContinue
    }
    $strOnPremUpn = $accountOnPrem.UserPrincipalName
    Validate -Test "There is a user account for $strOnPremUpn" -Condition ($accountOnprem -ne $null) -FailureMsg "Could not find an Active Directory account for this user"
    if ($accountOnPrem)
    {
        Validate -WarningOnly -Test "The password for $strOnPremUpn will not expire" -Condition ($accountOnprem.PasswordNeverExpires -eq $True) -FailureMsg "PasswordNeverExpires - the admin will need to update the device account's password on the Surface Hub when it expires."
        Validate -Test "$strOnPremUpn is enabled" -Condition $accountOnPrem.Enabled -FailureMsg "AccountEnabled - this device account will not sign in"
    }
}


$global:iTotalTests = ($global:iTotalFailures + $global:iTotalPasses + $global:iTotalWarnings)

Write-Host -NoNewline $global:iTotalTests "tests executed: "
Write-Host -NoNewline -ForegroundColor Red $Global:iTotalFailures "failures "
Write-Host -NoNewline -ForegroundColor Yellow $Global:iTotalWarnings "warnings "
Write-Host -ForegroundColor Green $Global:iTotalPasses "passes "

Cleanup
```

## <a href="" id="enable-sfb-ps-scripts"></a><span data-ttu-id="71f59-202">Activer Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="71f59-202">Enable Skype for Business</span></span>

<span data-ttu-id="71f59-203">Ce script permet d’activer Skype Entreprise sur un compte d’appareil.</span><span class="sxs-lookup"><span data-stu-id="71f59-203">This script will enable Skype for Business on a device account.</span></span> <span data-ttu-id="71f59-204">Utilisez-le uniquement si Skype Entreprise n’a pas été activé précédemment lors de la création de compte.</span><span class="sxs-lookup"><span data-stu-id="71f59-204">Use it only if Skype for Business wasn't previously enabled during account creation.</span></span>

```PowerShell
## This script performs only the Enable for Skype for Business step on an account. It should only be run if this step failed in SHAccountCreate and the other steps have been completed ##
# EnableSfb.ps1

$Error.Clear()
$ErrorActionPreference = "Stop"

# Cleans up set state such as remote powershell sessions
function Cleanup()
{
    if ($sessCS)
    {
        Remove-PSSession $sessCS
    }
}

function PrintError($strMsg)
{
    Write-Host $strMsg -foregroundcolor "red"
}

function PrintSuccess($strMsg)
{
    Write-Host $strMsg -foregroundcolor "green"
}

# Cleans up and prints an error message
function CleanupAndFail($strMsg)
{
    if ($strMsg)
    {
        PrintError($strMsg);
    }
    Cleanup
    exit 1
}

# Exits if there is an error set and prints the given message
function ExitIfError($strMsg)
{
    if ($Error)
    {
        CleanupAndFail($strMsg);
    }
}

## Check dependencies ##

$input = Read-Host "Is the account you wish to enable part of an online environment (enter O) or on-premises environment (enter P)"
if ($input -eq "P")
{
    $online = $false
}
elseif ($input -eq "O")
{
    $online = $true
}
else
{
    CleanupAndFail "Invalid selection"
}
if ($online)
{
    try {
        Import-Module SkypeOnlineConnector
    }
    catch
    {
        PrintError "Some dependencies are missing"
        PrintError "Please install the Windows PowerShell Module for Lync Online. For more information go to https://www.microsoft.com/download/details.aspx?id=39366"
        PrintError "Please install the Azure Active Directory module for PowerShell from https://go.microsoft.com/fwlink/p/?linkid=236297"
        CleanupAndFail
    }
}
else
{
    $strRegPool = Read-Host "Enter the FQDN of your Skype for Business Registrar Pool"
}


## Collect account data ##
Write-Host "-----------  Enter info for the account to enable  -----------." -foregroundcolor "magenta"
$strRoomUri=Read-Host 'Please enter the UPN of the account you are enabling (e.g. confroom@surfacehub.microsoft.com)'

if ([System.String]::IsNullOrEmpty($strRoomUri))
{
    CleanupAndFail "Please enter all of the requested data to continue."
    exit 1
}
Write-Host "--------------------------------------------------------------." -foregroundcolor "magenta"



## Sign in to remote powershell for exchange and lync online ##
Write-Host "`n------------------  Establishing connection  -----------------." -foregroundcolor "magenta"
$credAdmin=Get-Credential -Message "Enter credentials of a Skype for Business admin"
if (!$credadmin)
{
    CleanupAndFail("Valid admin credentials are required to create and prepare the account.");
}
Write-Host "Connecting to remote sessions. This can occasionally take a while - please do not enter input..."

try
{
    if ($online)
    {
        $sessCS = New-CsOnlineSession -Credential $credAdmin
    }
    else
    {
        $sessCS = New-PSSession -Credential $credAdmin -ConnectionURI "https://$strRegPool/OcsPowershell" -AllowRedirection -WarningAction SilentlyContinue
    }
}
catch
{
    CleanupAndFail("Failed to connect to Skype for Business server. Please check your credentials and try again. Error message: $_")
}

Import-PSSession $sessCS -AllowClobber


Write-Host "--------------------------------------------------------------." -foregroundcolor "magenta"

# Getting registrar pool
if ($online)
{
    try {
        $strRegPool = $null;
        $strRegPool = (Get-CsTenant).RegistrarPool
    } catch {}
    if ($Error)
    {
        $Error.Clear();
        $strRegPool = "";
        Write-Host "We failed to lookup your Skype for Business Registrar Pool, but you can still enter it manually"
    }
    else
    {
        $strRegPool = $strRegPool[0].Substring($strRegPool[0].IndexOf(':') + 1)
    }
}


$Error.Clear()
try {
    Enable-CsMeetingRoom -Identity $strRoomUri -RegistrarPool $strRegPool -SipAddressType EmailAddress
}
catch {}

ExitIfError("Failed to setup Skype for Business meeting room")

PrintSuccess "Successfully enabled $strRoomUri as a Skype for Business meeting room"

Cleanup
```

## <span data-ttu-id="71f59-205">Applets de commande utiles</span><span class="sxs-lookup"><span data-stu-id="71f59-205">Useful cmdlets</span></span>

### <a href="" id="create-compatible-as-policy"></a><span data-ttu-id="71f59-206">Création d’une stratégie ActiveSync compatible avec le Surface Hub</span><span class="sxs-lookup"><span data-stu-id="71f59-206">Creating a Surface Hub-compatible ActiveSync policy</span></span>

<span data-ttu-id="71f59-207">Un compte d’appareil configuré avec une stratégie ActiveSync compatible doit être mis en service sur l’appareil afin de permettre au Surface Hub d’utiliser les services Exchange.</span><span class="sxs-lookup"><span data-stu-id="71f59-207">For Surface Hub to use Exchange services, a device account configured with a compatible ActiveSync policy must be provisioned on the device.</span></span> <span data-ttu-id="71f59-208">Voici les exigences relatives à cette stratégie:</span><span class="sxs-lookup"><span data-stu-id="71f59-208">This policy has the following requirements:</span></span>

``` syntax
PasswordEnabled == 0
```

<span data-ttu-id="71f59-209">Dans les applets de commande suivantes, `$strPolicy` est le nom de la stratégie ActiveSync, et `$strRoomUpn` l’UPN du compte d’appareil auquel vous voulez appliquer la stratégie.</span><span class="sxs-lookup"><span data-stu-id="71f59-209">In the following cmdlets, `$strPolicy` is the name of the ActiveSync policy, and `$strRoomUpn` is the UPN of the device account you want to apply the policy to.</span></span>

<span data-ttu-id="71f59-210">Notez que pour exécuter les applets de commande, vous devez configurer une session PowerShell distante:</span><span class="sxs-lookup"><span data-stu-id="71f59-210">Note that in order to run the cmdlets, you need to set up a remote PowerShell session and:</span></span>

-   <span data-ttu-id="71f59-211">Votre compte d’administrateur doit être de type remote-PowerShell-enabled.</span><span class="sxs-lookup"><span data-stu-id="71f59-211">Your admin account must be remote-PowerShell-enabled.</span></span> <span data-ttu-id="71f59-212">Cela permet à l’administrateur d’utiliser les applets de commande PowerShell requises par le script.</span><span class="sxs-lookup"><span data-stu-id="71f59-212">This allows the admin to use the PowerShell cmdlets that are needed by the script.</span></span> <span data-ttu-id="71f59-213">(Cette autorisation peut être définie à l’aide de `set-user $admin -RemotePowerShellEnabled $true`)</span><span class="sxs-lookup"><span data-stu-id="71f59-213">(This permission can be set using `set-user $admin -RemotePowerShellEnabled $true`)</span></span>
-   <span data-ttu-id="71f59-214">Votre compte d’administrateur doit disposer du rôle «Réinitialiser le mot de passe» si vous prévoyez d’exécuter les scripts de création.</span><span class="sxs-lookup"><span data-stu-id="71f59-214">Your admin account must have the "Reset Password" role if you plan to run the creation scripts.</span></span> <span data-ttu-id="71f59-215">Cela permet à l’administrateur de modifier le mot de passe du compte, qui est nécessaire pour le script.</span><span class="sxs-lookup"><span data-stu-id="71f59-215">This allows the admin to change the password of the account, which is needed for the script.</span></span> <span data-ttu-id="71f59-216">Le rôle Réinitialiser le mot de passe peut être activé à l’aide du Centre d’administration Exchange.</span><span class="sxs-lookup"><span data-stu-id="71f59-216">The Reset Password Role can be enabled using the Exchange Admin Center.</span></span>

<span data-ttu-id="71f59-217">Créez la stratégie.</span><span class="sxs-lookup"><span data-stu-id="71f59-217">Create the policy.</span></span>

```PowerShell
# Create new policy with PasswordEnabled == false
New-MobileDeviceMailboxPolicy -Name $strPolicy -PasswordEnabled $false –AllowNonProvisionableDevices $true
```

<span data-ttu-id="71f59-218">Pour appliquer la stratégie, la boîte aux lettres ne peut pas être de type Salle. Vous devez d’abord la convertir en utilisateur.</span><span class="sxs-lookup"><span data-stu-id="71f59-218">To apply the policy, the mailbox cannot be a room type, so it has to be converted into a user first.</span></span>

```PowerShell
# Convert user to regular type
Set-Mailbox $strRoomUpn -Type Regular
# Set policy for account
Set-CASMailbox $strRoomUpn -ActiveSyncMailboxPolicy $strPolicy
```

<span data-ttu-id="71f59-219">Maintenant, il suffit de définir de nouveau le type de compte d’appareil sur Salle.</span><span class="sxs-lookup"><span data-stu-id="71f59-219">Now the device account just needs to be converted back into a room type.</span></span>

```PowerShell
# Convert back to room mailbox
Set-Mailbox $strRoomUpn -Type Room
```

### <span data-ttu-id="71f59-220">Autoriser les ID d’appareil pour ActiveSync</span><span class="sxs-lookup"><span data-stu-id="71f59-220">Allowing device IDs for ActiveSync</span></span>

<span data-ttu-id="71f59-221">Pour autoriser un `$strRoomUpn` de compte, exécutez la commande suivante:</span><span class="sxs-lookup"><span data-stu-id="71f59-221">To allow an account `$strRoomUpn`, run the following command:</span></span>

```PowerShell
Set-CASMailbox –Identity $strRoomUpn –ActiveSyncAllowedDeviceIDs “<ID>”
```

<span data-ttu-id="71f59-222">Pour trouver l’ID d’un appareil, exécutez la commande suivante:</span><span class="sxs-lookup"><span data-stu-id="71f59-222">To find a device's ID, run:</span></span>

```PowerShell
Get-ActiveSyncDevice -Mailbox $strRoomUpn
```

<span data-ttu-id="71f59-223">Cela permet de récupérer les informations de tous les appareils sur lesquels le compte a été mis en service, y compris la propriété `DeviceId`.</span><span class="sxs-lookup"><span data-stu-id="71f59-223">This retrieves device information for every device that the account has been provisioned on, Including the `DeviceId` property.</span></span>

### <a href="" id="auto-accept-meetings-cmdlet"></a><span data-ttu-id="71f59-224">Accepter et refuser automatiquement les demandes de réunion</span><span class="sxs-lookup"><span data-stu-id="71f59-224">Auto-accepting and declining meeting requests</span></span>

<span data-ttu-id="71f59-225">Pour qu’un compte d’appareil accepte ou refuse automatiquement les demandes de réunion en fonction de sa disponibilité, l’attribut **AutomateProcessing** doit être défini sur **AutoAccept**.</span><span class="sxs-lookup"><span data-stu-id="71f59-225">For a device account to automatically accept or decline meeting requests based on its availability, the **AutomateProcessing** attribute must be set to **AutoAccept**.</span></span> <span data-ttu-id="71f59-226">Cela est recommandé pour éviter que des réunions se chevauchent.</span><span class="sxs-lookup"><span data-stu-id="71f59-226">This is recommended as to prevent overlapping meetings.</span></span>

```PowerShell
Set-CalendarProcessing $strRoomUpn -AutomateProcessing AutoAccept
```

### <a href="" id="accept-ext-meetings-cmdlet"></a><span data-ttu-id="71f59-227">Accepter les demandes de réunion externes</span><span class="sxs-lookup"><span data-stu-id="71f59-227">Accepting external meeting requests</span></span>

<span data-ttu-id="71f59-228">Pour qu’un compte d’appareil accepte des demandes de réunion externes (une demande de réunion issue d’un compte ne figurant pas sur le même client/domaine), le compte d’appareil doit être défini de manière à autoriser le traitement des demandes de réunion externes.</span><span class="sxs-lookup"><span data-stu-id="71f59-228">For a device account to accept external meeting requests (a meeting request from an account not in the same tenant/domain), the device account must be set to allow processing of external meeting requests.</span></span> <span data-ttu-id="71f59-229">Une fois défini, le compte d’appareil accepte ou refuse automatiquement les demandes de réunion provenant de comptes externes, ainsi que de comptes locaux.</span><span class="sxs-lookup"><span data-stu-id="71f59-229">Once set, the device account will automatically accept or decline meeting requests from external accounts as well as local accounts.</span></span>

> [!Note]
> <span data-ttu-id="71f59-230">Si **l’attribut AutomateProcessing** n’est pas définie sur **AutoAccept,** cela n’aura aucun effet.</span><span class="sxs-lookup"><span data-stu-id="71f59-230">If the **AutomateProcessing** attribute is not set to **AutoAccept**, then setting this will have no effect.</span></span>

```PowerShell
Set-CalendarProcessing $strRoomUpn -ProcessExternalMeetingMessages $true
```
