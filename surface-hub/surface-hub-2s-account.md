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
ms.date: 06/20/2019
ms.localizationpriority: Medium
ms.openlocfilehash: 6d8c41872481d86316d8985871fe74823e005ed8
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10833803"
---
# <span data-ttu-id="c371b-104">Créer un compte d’appareil SurfaceHub2S</span><span class="sxs-lookup"><span data-stu-id="c371b-104">Create Surface Hub 2S device account</span></span>

<span data-ttu-id="c371b-105">La création d’un compte de périphérique surface Hub (également connu sous le nom de boîte aux lettres de salle) permet à surface Hub 2 de recevoir, approuver ou refuser des demandes de réunion et de participer à des réunions à l’aide de Microsoft teams ou de Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="c371b-105">Creating a Surface Hub device account (also known as a Room mailbox) allows Surface Hub 2S to receive, approve, or decline meeting requests and join meetings using either Microsoft Teams or Skype for Business.</span></span> <span data-ttu-id="c371b-106">Configurez le compte de l’appareil lors de l’installation de OOBE (out-of-Box Experience).</span><span class="sxs-lookup"><span data-stu-id="c371b-106">Configure the device account during Out-of-Box Experience (OOBE) setup.</span></span> <span data-ttu-id="c371b-107">Le cas échéant, vous pouvez le modifier ultérieurement (sans passer par la configuration OOBE).</span><span class="sxs-lookup"><span data-stu-id="c371b-107">If needed, you can change it later (without going through OOBE setup).</span></span>

<span data-ttu-id="c371b-108">Contrairement aux boîtes aux lettres standard de salle qui ne sont pas désactivées par défaut, vous devez activer le compte de périphérique surface Hub 2S pour vous connecter à Microsoft teams et à Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="c371b-108">Unlike standard Room mailboxes that remain disabled by default, you need to enable the Surface Hub 2S device account to sign on to Microsoft Teams and Skype for Business.</span></span> <span data-ttu-id="c371b-109">Surface Hub 2 repose sur Exchange ActiveSync, qui nécessite une stratégie de boîte aux lettres ActiveSync sur le compte de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="c371b-109">Surface Hub 2S relies on Exchange ActiveSync, which requires an ActiveSync mailbox policy on the device account.</span></span> <span data-ttu-id="c371b-110">Appliquez la stratégie de boîte aux lettres ActiveSync par défaut fournie avec Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="c371b-110">Apply the default ActiveSync mailbox policy that comes with Exchange Online.</span></span>

<span data-ttu-id="c371b-111">Créez le compte à l’aide du centre d’administration 365 Microsoft ou en utilisant PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c371b-111">Create the account by using the Microsoft 365 admin center or by using PowerShell.</span></span> <span data-ttu-id="c371b-112">Vous pouvez utiliser Exchange Online PowerShell pour configurer des fonctionnalités spécifiques, notamment:</span><span class="sxs-lookup"><span data-stu-id="c371b-112">You can use Exchange Online PowerShell to configure specific features including:</span></span>

- <span data-ttu-id="c371b-113">Traitement de calendrier pour chaque compte d’appareil surface Hub.</span><span class="sxs-lookup"><span data-stu-id="c371b-113">Calendar processing for every Surface Hub device account.</span></span>
- <span data-ttu-id="c371b-114">Réponses automatiques personnalisées à des demandes de planification.</span><span class="sxs-lookup"><span data-stu-id="c371b-114">Custom auto replies to scheduling requests.</span></span>
- <span data-ttu-id="c371b-115">Si la stratégie de boîte aux lettres ActiveSync par défaut a déjà été modifiée par une autre personne ou par un autre processus, il est probable que vous deviez créer et affecter une nouvelle stratégie de boîte aux lettres ActiveSync.</span><span class="sxs-lookup"><span data-stu-id="c371b-115">If the default ActiveSync mailbox policy has already been modified by someone else or by another process, you will likely have to create and assign a new ActiveSync mailbox policy.</span></span>

> [!NOTE]  
> <span data-ttu-id="c371b-116">Le compte de l’appareil surface Hub ne prend pas en charge les fournisseurs d’identité fédérés tiers (FIPs) et doit être un compte Active Directory standard ou Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c371b-116">The Surface Hub device account doesn’t support third-party Federated Identity Providers (FIPs) and must be a standard Active Directory or Azure Active Directory account.</span></span>

## <span data-ttu-id="c371b-117">Créer un compte à l’aide du centre d’administration 365 Microsoft</span><span class="sxs-lookup"><span data-stu-id="c371b-117">Create account using Microsoft 365 admin center</span></span>

1. <span data-ttu-id="c371b-118">Dans le centre d’administration 365 Microsoft, accédez à **ressources** , puis sélectionnez **salles & équipements** et sélectionnez **+ salle**.</span><span class="sxs-lookup"><span data-stu-id="c371b-118">In the Microsoft 365 admin center, go to **Resources** and choose **Rooms & Equipment** and then select **+ Room**.</span></span>

2. <span data-ttu-id="c371b-119">Fournissez un nom et une adresse de courrier pour le compte de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="c371b-119">Provide a name and email address for the device account.</span></span> <span data-ttu-id="c371b-120">Ne modifiez pas les paramètres restants dans l’État par défaut.</span><span class="sxs-lookup"><span data-stu-id="c371b-120">Leave remaining settings unchanged in the default state.</span></span>

   ![Fournir un nom et une adresse de courrier](images/sh2-account2.png)

   ![Ne pas modifier les paramètres restants dans l’État par défaut](images/sh2-account3.png)

3. <span data-ttu-id="c371b-123">Définissez le mot de passe du compte de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="c371b-123">Set the password for the device account.</span></span> <span data-ttu-id="c371b-124">Pour définir le mot de passe, sélectionnez **utilisateurs** , puis **utilisateurs actifs**.</span><span class="sxs-lookup"><span data-stu-id="c371b-124">To set the password, choose **Users** and then select **Active Users**.</span></span> <span data-ttu-id="c371b-125">Recherchez ensuite l’utilisateur nouvellement créé pour définir le mot de passe.</span><span class="sxs-lookup"><span data-stu-id="c371b-125">Now search for the newly created user to set the password.</span></span> <span data-ttu-id="c371b-126">Assurez-vous de **ne pas** sélectionner l’option faire en sorte que l' **utilisateur modifie son mot de passe lors de sa première connexion.**</span><span class="sxs-lookup"><span data-stu-id="c371b-126">Ensure that you **do not** select the option **Make this user change their password when they first sign in.**</span></span>

   ![Définir le mot de passe du compte d’appareil](images/sh2-account4.png)

4. <span data-ttu-id="c371b-128">Affectez la salle à une licence Office 365.</span><span class="sxs-lookup"><span data-stu-id="c371b-128">Assign the room with an Office 365 license.</span></span> <span data-ttu-id="c371b-129">Il est recommandé d’affecter la licence de **salle de réunion** Office 365, une nouvelle option qui active automatiquement le compte pour Skype entreprise Online et Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c371b-129">It’s recommended to assign the Office 365 **Meeting Room** license, a new option that automatically enables the account for Skype for Business Online and Microsoft Teams.</span></span>

   ![Attribution d’une licence Office 365](images/sh2-account5.png)

### <span data-ttu-id="c371b-131">Finalisez la configuration via PowerShell</span><span class="sxs-lookup"><span data-stu-id="c371b-131">Finalize setup via PowerShell</span></span>

- <span data-ttu-id="c371b-132">**Skype entreprise:** Pour Skype entreprise uniquement (local ou en ligne), vous pouvez activer l’objet Skype entreprise en exécutant **Enable-CsMeetingRoom** pour activer des fonctionnalités telles que la demande de salle de réunion pour les appels audio et salle d’attente.</span><span class="sxs-lookup"><span data-stu-id="c371b-132">**Skype for Business:** For Skype for Business only (on-premises or online), you can enable the Skype for Business object by running **Enable-CsMeetingRoom** to enable features such as Meeting room prompt for audio and Lobby hold.</span></span>

- <span data-ttu-id="c371b-133">**Calendrier Microsoft teams et Skype entreprise:** Définissez le [**traitement automatique de calendrier**](https://docs.microsoft.com/surface-hub/surface-hub-2s-account?source=docs#set-calendar-auto-processing) pour ce compte.</span><span class="sxs-lookup"><span data-stu-id="c371b-133">**Microsoft Teams and Skype for Business Calendar:** Set [**Calendar Auto processing**](https://docs.microsoft.com/surface-hub/surface-hub-2s-account?source=docs#set-calendar-auto-processing) for this account.</span></span>

## <span data-ttu-id="c371b-134">Créer un compte à l’aide de PowerShell</span><span class="sxs-lookup"><span data-stu-id="c371b-134">Create account using PowerShell</span></span>

<span data-ttu-id="c371b-135">Au lieu d’utiliser le portail du centre d’administration Microsoft, vous pouvez créer le compte à l’aide de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c371b-135">Instead of using the Microsoft Admin Center portal, you can create the account using PowerShell.</span></span>

### <span data-ttu-id="c371b-136">Connexion à Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="c371b-136">Connect to Exchange Online PowerShell</span></span>

```powershell
$365Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell -Credential (Get-Credential) -Authentication Basic –AllowRedirection
$ImportResults = Import-PSSession $365Session
```

### <span data-ttu-id="c371b-137">Créer une boîte aux lettres de salle</span><span class="sxs-lookup"><span data-stu-id="c371b-137">Create a new Room mailbox</span></span>

```powershell
New-Mailbox -MicrosoftOnlineServicesID account@YourDomain.com -Alias SurfaceHub2S -Name SurfaceHub2S -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString  -String "<Enter Strong Password>" -AsPlainText -Force)
```

### <span data-ttu-id="c371b-138">Définir le traitement automatique du calendrier</span><span class="sxs-lookup"><span data-stu-id="c371b-138">Set Calendar auto-processing</span></span>

```powershell
Set-CalendarProcessing -Identity "account@YourDomain.com" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts   $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This room is equipped with a Surface Hub"
```

### <span data-ttu-id="c371b-139">Attribuer une licence</span><span class="sxs-lookup"><span data-stu-id="c371b-139">Assign a license</span></span>

```powershell
Connect-MsolService
Set-Msoluser -UserPrincipalName account@YourDomain.com -UsageLocation IE
Set-MsolUserLicense -UserPrincipalName "account@YourDomain.com" -AddLicenses "contoso:MEETING_ROOM"
```

## <span data-ttu-id="c371b-140">Se connecter à Skype entreprise Online à l’aide de PowerShell</span><span class="sxs-lookup"><span data-stu-id="c371b-140">Connect to Skype for Business Online using PowerShell</span></span>

### <span data-ttu-id="c371b-141">Installer les conditions préalables</span><span class="sxs-lookup"><span data-stu-id="c371b-141">Install pre-requisites</span></span>

- [<span data-ttu-id="c371b-142">Visual C++ 2017 redistribuable</span><span class="sxs-lookup"><span data-stu-id="c371b-142">Visual C++ 2017 Redistributable</span></span>](https://aka.ms/vs/15/release/vc_redist.x64.exe)
- [<span data-ttu-id="c371b-143">Module PowerShell de Skype entreprise Online</span><span class="sxs-lookup"><span data-stu-id="c371b-143">Skype for Business Online PowerShell Module</span></span>](https://www.microsoft.com/download/confirmation.aspx?id=39366)

```powershell
Import-Module LyncOnlineConnector
$SfBSession = New-CsOnlineSession -Credential (Get-Credential)
Import-PSSession $SfBSession -AllowClobber

# Enable the Skype for Business meeting room
Enable-CsMeetingRoom -Identity account@YourDomain.com -RegistrarPool(Get-CsTenant).Registrarpool -SipAddressType EmailAddress
```
