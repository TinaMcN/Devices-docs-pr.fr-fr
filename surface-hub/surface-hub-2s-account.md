---
title: Créer un compte d’appareil SurfaceHub2S
description: Cette page décrit la procédure de création du compte de l’appareil surface Hub 2S.
keywords: séparer les valeurs par des virgules
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 12/07/2020
ms.localizationpriority: Medium
ms.openlocfilehash: e171d7c2db8a0d69594ca8d5f3a54f33ecebc9ae
ms.sourcegitcommit: dc08a2096a1fe955eb67e736e2a4453f75e926be
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/07/2020
ms.locfileid: "11196727"
---
# <span data-ttu-id="946d0-104">Créer un compte d’appareil SurfaceHub2S</span><span class="sxs-lookup"><span data-stu-id="946d0-104">Create Surface Hub 2S device account</span></span>

<span data-ttu-id="946d0-105">La création d’un compte de périphérique surface Hub (également connu sous le nom de boîte aux lettres de salle) permet à surface Hub 2 de recevoir, approuver ou refuser des demandes de réunion et de participer à des réunions à l’aide de Microsoft teams ou de Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="946d0-105">Creating a Surface Hub device account (also known as a Room mailbox) allows Surface Hub 2S to receive, approve, or decline meeting requests and join meetings using either Microsoft Teams or Skype for Business.</span></span> <span data-ttu-id="946d0-106">Configurez le compte de l’appareil lors de l’installation de OOBE (out-of-Box Experience).</span><span class="sxs-lookup"><span data-stu-id="946d0-106">Configure the device account during Out-of-Box Experience (OOBE) setup.</span></span> <span data-ttu-id="946d0-107">Le cas échéant, vous pouvez le modifier ultérieurement (sans passer par la configuration OOBE).</span><span class="sxs-lookup"><span data-stu-id="946d0-107">If needed, you can change it later (without going through OOBE setup).</span></span>

<span data-ttu-id="946d0-108">Contrairement aux boîtes aux lettres standard de salle qui ne sont pas désactivées par défaut, vous devez activer le compte de périphérique surface Hub 2S pour vous connecter à Microsoft teams et à Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="946d0-108">Unlike standard Room mailboxes that remain disabled by default, you need to enable the Surface Hub 2S device account to sign on to Microsoft Teams and Skype for Business.</span></span> <span data-ttu-id="946d0-109">Surface Hub 2 repose sur Exchange ActiveSync, qui nécessite une stratégie de boîte aux lettres ActiveSync sur le compte de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="946d0-109">Surface Hub 2S relies on Exchange ActiveSync, which requires an ActiveSync mailbox policy on the device account.</span></span> <span data-ttu-id="946d0-110">Appliquez la stratégie de boîte aux lettres ActiveSync par défaut fournie avec Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="946d0-110">Apply the default ActiveSync mailbox policy that comes with Exchange Online.</span></span>

<span data-ttu-id="946d0-111">Créez le compte à l’aide du centre d’administration 365 Microsoft ou en utilisant PowerShell.</span><span class="sxs-lookup"><span data-stu-id="946d0-111">Create the account by using the Microsoft 365 admin center or by using PowerShell.</span></span> <span data-ttu-id="946d0-112">Vous pouvez utiliser Exchange Online PowerShell pour configurer des fonctionnalités spécifiques, notamment:</span><span class="sxs-lookup"><span data-stu-id="946d0-112">You can use Exchange Online PowerShell to configure specific features including:</span></span>

- <span data-ttu-id="946d0-113">Traitement de calendrier pour chaque compte d’appareil surface Hub.</span><span class="sxs-lookup"><span data-stu-id="946d0-113">Calendar processing for every Surface Hub device account.</span></span>
- <span data-ttu-id="946d0-114">Réponses automatiques personnalisées à des demandes de planification.</span><span class="sxs-lookup"><span data-stu-id="946d0-114">Custom auto replies to scheduling requests.</span></span>
- <span data-ttu-id="946d0-115">Si la stratégie de boîte aux lettres ActiveSync par défaut a déjà été modifiée par une autre personne ou par un autre processus, il est probable que vous deviez créer et affecter une nouvelle stratégie de boîte aux lettres ActiveSync.</span><span class="sxs-lookup"><span data-stu-id="946d0-115">If the default ActiveSync mailbox policy has already been modified by someone else or by another process, you will likely have to create and assign a new ActiveSync mailbox policy.</span></span>

> [!NOTE]  
> <span data-ttu-id="946d0-116">Le compte de l’appareil surface Hub ne prend pas en charge les fournisseurs d’identité fédérés tiers (FIPs) et doit être un compte Active Directory standard ou Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="946d0-116">The Surface Hub device account doesn’t support third-party Federated Identity Providers (FIPs) and must be a standard Active Directory or Azure Active Directory account.</span></span>

## <span data-ttu-id="946d0-117">Créer un compte à l’aide du centre d’administration 365 Microsoft</span><span class="sxs-lookup"><span data-stu-id="946d0-117">Create account using Microsoft 365 admin center</span></span>

1. <span data-ttu-id="946d0-118">Dans le centre d’administration 365 Microsoft, accédez à **ressources** , puis sélectionnez **salles & équipements** et sélectionnez **+ salle**.</span><span class="sxs-lookup"><span data-stu-id="946d0-118">In the Microsoft 365 admin center, go to **Resources** and choose **Rooms & Equipment** and then select **+ Room**.</span></span>

2. <span data-ttu-id="946d0-119">Fournissez un nom et une adresse de courrier pour le compte de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="946d0-119">Provide a name and email address for the device account.</span></span> <span data-ttu-id="946d0-120">Ne modifiez pas les paramètres restants dans l’État par défaut.</span><span class="sxs-lookup"><span data-stu-id="946d0-120">Leave remaining settings unchanged in the default state.</span></span>

   ![Fournir un nom et une adresse de courrier](images/sh2-account2.png)

   ![Ne pas modifier les paramètres restants dans l’État par défaut](images/sh2-account3.png)

3. <span data-ttu-id="946d0-123">Définissez le mot de passe du compte de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="946d0-123">Set the password for the device account.</span></span> <span data-ttu-id="946d0-124">Pour définir le mot de passe, sélectionnez **utilisateurs** , puis **utilisateurs actifs**.</span><span class="sxs-lookup"><span data-stu-id="946d0-124">To set the password, choose **Users** and then select **Active Users**.</span></span> <span data-ttu-id="946d0-125">Recherchez ensuite l’utilisateur nouvellement créé pour définir le mot de passe.</span><span class="sxs-lookup"><span data-stu-id="946d0-125">Now search for the newly created user to set the password.</span></span> <span data-ttu-id="946d0-126">Assurez-vous de **ne pas** sélectionner l’option faire en sorte que l' **utilisateur modifie son mot de passe lors de sa première connexion.**</span><span class="sxs-lookup"><span data-stu-id="946d0-126">Ensure that you **do not** select the option **Make this user change their password when they first sign in.**</span></span>

   ![Définir le mot de passe du compte d’appareil](images/sh2-account4.png)

4. <span data-ttu-id="946d0-128">Affectez la salle à une licence Office 365.</span><span class="sxs-lookup"><span data-stu-id="946d0-128">Assign the room with an Office 365 license.</span></span> <span data-ttu-id="946d0-129">Il est recommandé d’affecter la licence de **salle de réunion** Office 365, une nouvelle option qui active automatiquement le compte pour Skype entreprise Online et Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="946d0-129">It’s recommended to assign the Office 365 **Meeting Room** license, a new option that automatically enables the account for Skype for Business Online and Microsoft Teams.</span></span>

   ![Attribution d’une licence Office 365](images/sh2-account5.png)

### <span data-ttu-id="946d0-131">Finalisez la configuration via PowerShell</span><span class="sxs-lookup"><span data-stu-id="946d0-131">Finalize setup via PowerShell</span></span>

- <span data-ttu-id="946d0-132">**Calendrier Microsoft teams et Skype entreprise:** Définissez le [**traitement automatique de calendrier**](https://docs.microsoft.com/surface-hub/surface-hub-2s-account?source=docs#set-calendar-auto-processing) pour ce compte.</span><span class="sxs-lookup"><span data-stu-id="946d0-132">**Microsoft Teams and Skype for Business Calendar:** Set [**Calendar Auto processing**](https://docs.microsoft.com/surface-hub/surface-hub-2s-account?source=docs#set-calendar-auto-processing) for this account.</span></span>

## <span data-ttu-id="946d0-133">Créer un compte à l’aide de PowerShell</span><span class="sxs-lookup"><span data-stu-id="946d0-133">Create account using PowerShell</span></span>

<span data-ttu-id="946d0-134">Au lieu d’utiliser le portail du centre d’administration Microsoft, vous pouvez créer le compte à l’aide de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="946d0-134">Instead of using the Microsoft Admin Center portal, you can create the account using PowerShell.</span></span>

### <span data-ttu-id="946d0-135">Connexion à Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="946d0-135">Connect to Exchange Online PowerShell</span></span>

```powershell
Install-Module -Name ExchangeOnlineManagement
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName admin@contoso.com -ShowProgress $true
```

### <span data-ttu-id="946d0-136">Créer une boîte aux lettres</span><span class="sxs-lookup"><span data-stu-id="946d0-136">Create mailbox</span></span>

```powershell
New-Mailbox -MicrosoftOnlineServicesID 'SurfaceHub01@contoso.com' -Alias SurfaceHub01 -Name "Surface Hub 01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String 'Pass@word1' -AsPlainText -Force)
```

### <span data-ttu-id="946d0-137">Définir le traitement automatique du calendrier</span><span class="sxs-lookup"><span data-stu-id="946d0-137">Set Calendar auto-processing</span></span>

```powershell
Set-CalendarProcessing -Identity 'SurfaceHub01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity 'SurfaceHub01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Surface Hub. Please make sure this meeting is a Microsoft Teams meeting!"
```

### <span data-ttu-id="946d0-138">Activer ActiveSync si l’utilisation de l’application de messagerie est requise</span><span class="sxs-lookup"><span data-stu-id="946d0-138">Enable ActiveSync if use of email app is required</span></span>

 <span data-ttu-id="946d0-139">La stratégie ActiveSync par défaut fonctionne si unchnaged.</span><span class="sxs-lookup"><span data-stu-id="946d0-139">The default ActiveSync Policy will work if unchnaged.</span></span> <span data-ttu-id="946d0-140">Dans le cas contraire, créez une nouvelle stratégie et attribuez-la.</span><span class="sxs-lookup"><span data-stu-id="946d0-140">Otherwise create a new Policy and assign.</span></span>

```powershell
New-MobileDeviceMailboxPolicy -Name:"SurfaceHub" -PasswordEnabled:$false
#Assign Policy to Hub:
Set-CASMailbox -Identity SurfaceHub01@contoso.com -ActiveSyncMailboxPolicy "SurfaceHub"
```
### <span data-ttu-id="946d0-141">Se connecter à AzureAD</span><span class="sxs-lookup"><span data-stu-id="946d0-141">Connect to Azure AD</span></span>

```powershell
Connect-AzureAD
```

### <span data-ttu-id="946d0-142">Attribuer une licence</span><span class="sxs-lookup"><span data-stu-id="946d0-142">Assign a license</span></span>

```powershell
Set-AzureADUser -ObjectId 'SurfaceHub01@contoso.com' -UsageLocation US
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense 
$License.SkuId = "c7df2760-2c81-4ef7-b578-5b5392b571df" 
$Licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses 
$Licenses.AddLicenses = $License 
Set-AzureADUserLicense -ObjectId 'SurfaceHub01@contoso.com' -AssignedLicenses $Licenses
```

### <span data-ttu-id="946d0-143">Vérifier les licences disponibles</span><span class="sxs-lookup"><span data-stu-id="946d0-143">Check for available licenses</span></span>

```powershell
Get-AzureADUser -Filter "userPrincipalName eq 'SurfaceHub01@contoso.com'" |fl *
#Meeting Room Standard SKU:
6070a4c8-34c6-4937-8dfb-39bbc6397a60
```