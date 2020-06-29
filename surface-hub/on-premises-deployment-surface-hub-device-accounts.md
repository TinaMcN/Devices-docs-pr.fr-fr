---
title: Déploiement sur site à forêt unique (SurfaceHub)
description: Cette rubrique explique comment ajouter un compte d’appareil pour votre MicrosoftSurfaceHub lorsque vous disposez d’un déploiement sur site à forêt unique.
ms.assetid: 80E12195-A65B-42D1-8B84-ECC3FCBAAFC6
ms.reviewer: ''
manager: laurawi
keywords: déploiement à forêt unique, déploiement sur site, compte d’appareil, SurfaceHub
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.date: 08/28/2018
ms.localizationpriority: medium
ms.openlocfilehash: 37b157268769ddcdeaef67b7e19cc7260cd392b9
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10833642"
---
# <span data-ttu-id="fe62e-104">Déploiement sur site pour SurfaceHub dans un environnement à forêt unique</span><span class="sxs-lookup"><span data-stu-id="fe62e-104">On-premises deployment for Surface Hub in a single-forest environment</span></span>


<span data-ttu-id="fe62e-105">Cette rubrique explique comment ajouter un compte d’appareil pour votre Microsoft SurfaceHub lorsque vous disposez d’un déploiement sur site à forêt unique.</span><span class="sxs-lookup"><span data-stu-id="fe62e-105">This topic explains how you add a device account for your Microsoft Surface Hub when you have a single-forest, on-premises deployment.</span></span>

<span data-ttu-id="fe62e-106">Si vous disposez d’un déploiement sur site à forêt unique avec MicrosoftExchange2013 ou une version ultérieure et SkypeEntreprise2013 ou une version ultérieure, vous pouvez [utiliser les scripts PowerShell fournis](appendix-a-powershell-scripts-for-surface-hub.md#create-on-premises-ps-scripts) pour créer des comptes d’appareil.</span><span class="sxs-lookup"><span data-stu-id="fe62e-106">If you have a single-forest on-premises deployment with Microsoft Exchange 2013 or later and Skype for Business 2013 or later, then you can [use the provided PowerShell scripts](appendix-a-powershell-scripts-for-surface-hub.md#create-on-premises-ps-scripts) to create device accounts.</span></span> <span data-ttu-id="fe62e-107">Si vous utilisez un déploiement à forêts multiples, consultez [Déploiement sur site pour SurfaceHub dans un environnement à forêts multiples](on-premises-deployment-surface-hub-multi-forest.md).</span><span class="sxs-lookup"><span data-stu-id="fe62e-107">If you’re using a multi-forest deployment, see [On-premises deployment for Surface Hub in a multi-forest environment](on-premises-deployment-surface-hub-multi-forest.md).</span></span>

1. <span data-ttu-id="fe62e-108">Démarrez une session PowerShell à distance à partir d’un PC et connectez-vous à Exchange.</span><span class="sxs-lookup"><span data-stu-id="fe62e-108">Start a remote PowerShell session from a PC and connect to Exchange.</span></span>

   <span data-ttu-id="fe62e-109">Assurez-vous de disposer de l’ensemble approprié d’autorisations pour exécuter les applets de commande associées.</span><span class="sxs-lookup"><span data-stu-id="fe62e-109">Be sure you have the right permissions set to run the associated cmdlets.</span></span>

   <span data-ttu-id="fe62e-110">Notez ici que `$strExchangeServer` est le nom de domaine complet de votre serveur Exchange, et que `$strLyncFQDN` est le nom de domaine complet de votre serveur Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="fe62e-110">Note here that `$strExchangeServer` is the fully qualified domain name (FQDN) of your Exchange server, and `$strLyncFQDN` is the FQDN of your Skype for Business server.</span></span>

   ```PowerShell
   Set-ExecutionPolicy Unrestricted
   $org='contoso.microsoft.com'
   $cred=Get-Credential $admin@$org
   $sessExchange = New-PSSession -ConfigurationName microsoft.exchange -Credential $cred -AllowRedirection -Authentication Kerberos -ConnectionUri "http://$strExchangeServer/powershell" -WarningAction SilentlyContinue
   $sessLync = New-PSSession -Credential $cred -ConnectionURI "https://$strLyncFQDN/OcsPowershell" -AllowRedirection -WarningAction SilentlyContinue
   Import-PSSession $sessExchange
   Import-PSSession $sessLync
   ```

2. <span data-ttu-id="fe62e-111">Une fois une session établie, vous allez créer une boîte aux lettres et l’activer en tant que RoomMailboxAccount, ou vous allez modifier les paramètres d’une boîte aux lettres de salle existante.</span><span class="sxs-lookup"><span data-stu-id="fe62e-111">After establishing a session, you’ll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="fe62e-112">Cela permettra au compte de s’authentifier sur le SurfaceHub.</span><span class="sxs-lookup"><span data-stu-id="fe62e-112">This will allow the account to authenticate into the Surface Hub.</span></span>

   <span data-ttu-id="fe62e-113">Si vous modifiez une boîte aux lettres de ressources existante:</span><span class="sxs-lookup"><span data-stu-id="fe62e-113">If you're changing an existing resource mailbox:</span></span>

   ```PowerShell
   Set-Mailbox -Identity 'HUB01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

   <span data-ttu-id="fe62e-114">Si vous créez une boîte aux lettres de ressources :</span><span class="sxs-lookup"><span data-stu-id="fe62e-114">If you’re creating a new resource mailbox:</span></span>

   ```PowerShell
   New-Mailbox -UserPrincipalName HUB01@contoso.com -Alias HUB01 -Name "Hub-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```
> [!IMPORTANT] 
> <span data-ttu-id="fe62e-115">L’authentification de base de l’annuaire virtuelle ActiveSync doit être activée car surface Hub ne peut pas s’authentifier à l’aide d’autres méthodes d’authentification.</span><span class="sxs-lookup"><span data-stu-id="fe62e-115">ActiveSync Virtual Directory Basic Authentication is required to be enabled as the Surface Hub is unable to authenticate using other authentication methods.</span></span>

3. <span data-ttu-id="fe62e-116">Après avoir configuré la boîte aux lettres, vous devez créer une stratégie Exchange ActiveSync ou utiliser une stratégie existante compatible.</span><span class="sxs-lookup"><span data-stu-id="fe62e-116">After setting up the mailbox, you will need to either create a new Exchange ActiveSync policy, or use a compatible existing policy.</span></span>

   <span data-ttu-id="fe62e-117">Les Surface Hub sont uniquement compatibles avec les comptes d’appareil dotés d’une stratégie ActiveSync, où la propriété **PasswordEnabled** est définie sur False.</span><span class="sxs-lookup"><span data-stu-id="fe62e-117">Surface Hubs are only compatible with device accounts that have an ActiveSync policy where the **PasswordEnabled** property is set to False.</span></span> <span data-ttu-id="fe62e-118">Si la propriété n’est pas définie correctement, les services Exchange sur le SurfaceHub (courrier, calendrier et accès aux réunions) ne seront pas activés.</span><span class="sxs-lookup"><span data-stu-id="fe62e-118">If this isn’t set properly, then Exchange services on the Surface Hub (mail, calendar, and joining meetings), will not be enabled.</span></span>

   <span data-ttu-id="fe62e-119">Si vous n’avez pas encore créé de stratégie compatible, utilisez l’applet de commande suivante: celle-ci crée une stratégie appelée SurfaceHub.</span><span class="sxs-lookup"><span data-stu-id="fe62e-119">If you haven’t created a compatible policy yet, use the following cmdlet—this one creates a policy called "Surface Hubs".</span></span> <span data-ttu-id="fe62e-120">Une fois qu’elle est créée, vous pouvez appliquer la même stratégie à d’autres comptes d’appareil.</span><span class="sxs-lookup"><span data-stu-id="fe62e-120">Once it’s created, you can apply the same policy to other device accounts.</span></span>

   ```PowerShell
   $easPolicy = New-MobileDeviceMailboxPolicy -Name “SurfaceHubs” -PasswordEnabled $false
   ```

   <span data-ttu-id="fe62e-121">Une fois que vous disposez d’une stratégie compatible, vous devez l’appliquer au compte d’appareil.</span><span class="sxs-lookup"><span data-stu-id="fe62e-121">Once you have a compatible policy, then you will need to apply the policy to the device account.</span></span> <span data-ttu-id="fe62e-122">Toutefois, les stratégies peuvent uniquement être appliquées aux comptes d’utilisateurs et non aux boîtes aux lettres de ressources.</span><span class="sxs-lookup"><span data-stu-id="fe62e-122">However, policies can only be applied to user accounts and not resource mailboxes.</span></span> <span data-ttu-id="fe62e-123">Vous devez convertir la boîte aux lettres en un type d’utilisateur, appliquer la stratégie, puis effectuer une nouvelle conversion en boîte aux lettres. Vous devrez peut-être la réactiver et également redéfinir le mot de passe.</span><span class="sxs-lookup"><span data-stu-id="fe62e-123">You need to convert the mailbox into a user type, apply the policy, and then convert it back into a mailbox—you may need to re-enable it and set the password again too.</span></span>

   ```PowerShell
   $acctUpn = Get-Mailbox -Identity "<mailbox identity>"
   $credNewAccount.Password = ConvertTo-SecureString -String <room mailbox password> -AsPlainText -Force
   Set-Mailbox $acctUpn -Type Regular
   Set-CASMailbox $acctUpn -ActiveSyncMailboxPolicy $easPolicy
   Set-Mailbox $acctUpn -Type Room
   Set-Mailbox $acctUpn -RoomMailboxPassword $credNewAccount.Password -EnableRoomMailboxAccount $true
   ```

4. <span data-ttu-id="fe62e-124">Diverses propriétés Exchange peuvent être définies sur le compte d’appareil pour améliorer l’expérience de réunions pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="fe62e-124">Various Exchange properties can be set on the device account to improve the meeting experience for people.</span></span> <span data-ttu-id="fe62e-125">Vous pouvez voir les propriétés qui doivent être définies dans la section [Propriétés Exchange](exchange-properties-for-surface-hub-device-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="fe62e-125">You can see which properties need to be set in the [Exchange properties](exchange-properties-for-surface-hub-device-accounts.md) section.</span></span>

   ```PowerShell
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
   ```

5. <span data-ttu-id="fe62e-126">Si vous décidez que le mot de passe n’expire pas, vous pouvez également définir cette option avec des applets de commande PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fe62e-126">If you decide to have the password not expire, you can set that with PowerShell cmdlets too.</span></span> <span data-ttu-id="fe62e-127">Consultez [Gestion des mots de passe](password-management-for-surface-hub-device-accounts.md) pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="fe62e-127">See [Password management](password-management-for-surface-hub-device-accounts.md) for more information.</span></span>

   ```PowerShell
   Set-AdUser $acctUpn -PasswordNeverExpires $true
   ```

6. <span data-ttu-id="fe62e-128">Activez le compte dans Active Directory de sorte qu’il s’authentifie au Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="fe62e-128">Enable the account in Active Directory so it will authenticate to the Surface Hub.</span></span>

   ```PowerShell
   Set-AdUser $acctUpn -Enabled $true
   ```

7. <span data-ttu-id="fe62e-129">Activez le compte d’appareil avec Skype Entreprise en activant votre compte AD Surface Hub sur un pool Skype Entreprise Server:</span><span class="sxs-lookup"><span data-stu-id="fe62e-129">Enable the device account with Skype for Business by enabling your Surface Hub AD account on a Skype for Business Server pool:</span></span>

   ```PowerShell
   Enable-CsMeetingRoom -SipAddress "sip:HUB01@contoso.com"
    -DomainController DC-ND-001.contoso.com -RegistrarPool LYNCPool15.contoso.com
    -Identity HUB01
   ```

   <span data-ttu-id="fe62e-130">Vous devrez utiliser l’adresse et le contrôleur de domaine du protocole SIP (Session Initiation Protocol) du Surface Hub, ainsi que vos propres identificateur de pool et identité d’utilisateur Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="fe62e-130">You'll need to use the Session Initiation Protocol (SIP) address and domain controller for the Surface Hub, along with your own Skype for Business Server pool identifier and user identity.</span></span>

8. <span data-ttu-id="fe62e-131">FACULTATIF: vous pouvez également autoriser votre Surface Hub à passer et à recevoir des appels téléphoniques RTC (réseau téléphonique commuté) en activant Voix Entreprise pour votre compte</span><span class="sxs-lookup"><span data-stu-id="fe62e-131">OPTIONAL: You can also allow your Surface Hub to make and receive public switched telephone network (PSTN) phone calls by enabling Enterprise Voice for your account.</span></span> <span data-ttu-id="fe62e-132">Voix Entreprise n’est pas une condition requise pour Surface Hub, mais si vous souhaitez que le client Surface Hub bénéficie de la fonctionnalité de numérotation RTC, voici comment l’activer:</span><span class="sxs-lookup"><span data-stu-id="fe62e-132">Enterprise Voice isn't a requirement for Surface Hub, but if you want PSTN dialing functionality for the Surface Hub client, here's how to enable it:</span></span>

   ```PowerShell
   Set-CsMeetingRoom  -Identity HUB01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"  -EnterpriseVoiceEnabled $true
   ```

   <span data-ttu-id="fe62e-133">Là encore, vous devez remplacer les exemples de contrôleur de domaine et de numéro de téléphone fournis par vos propres informations.</span><span class="sxs-lookup"><span data-stu-id="fe62e-133">Again, you need to replace the provided domain controller and phone number examples with your own information.</span></span> <span data-ttu-id="fe62e-134">La valeur du paramètre `$true` reste identique.</span><span class="sxs-lookup"><span data-stu-id="fe62e-134">The parameter value `$true` stays the same.</span></span>
    

 ## <span data-ttu-id="fe62e-135">Désactiver la messagerie instantanée et la messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="fe62e-135">Disable anonymous email and IM</span></span>




<span data-ttu-id="fe62e-136">Surface Hub utilise un compte d’appareil pour fournir des services de messagerie et de collaboration (messagerie instantanée, vidéo, voix).</span><span class="sxs-lookup"><span data-stu-id="fe62e-136">Surface Hub uses a device account to provide email and collaboration services (IM, video, voice).</span></span> <span data-ttu-id="fe62e-137">Ce compte d’appareil est utilisé comme identité d’origine (la partie «de») lors de l’envoi d’e-mails, de messages instantanés et de la mise des appels.</span><span class="sxs-lookup"><span data-stu-id="fe62e-137">This device account is used as the originating identity (the “from” party) when sending email, IM, and placing calls.</span></span> <span data-ttu-id="fe62e-138">Étant donné que ce compte ne provient pas d’un utilisateur identifiable individuel, il est considéré comme «anonyme», car il provient du compte de l’appareil de surface Hub.</span><span class="sxs-lookup"><span data-stu-id="fe62e-138">As this account is not coming from an individual, identifiable user, it is deemed “anonymous” because it originated from the Surface Hub's device account.</span></span>  

<span data-ttu-id="fe62e-139">Supposez qu’une stratégie de client par utilisateur est affectée à chaque appareil de salle de réunion ayant une identité de **SurfaceHubPolicy**.</span><span class="sxs-lookup"><span data-stu-id="fe62e-139">Assume you have a per-user client policy assigned to each meeting room device with an identity of **SurfaceHubPolicy**.</span></span> <span data-ttu-id="fe62e-140">Pour désactiver la messagerie instantanée et la messagerie électronique anonyme, vous devez ajouter un clientPolicyEntry à cette stratégie client en utilisant les commandes suivantes.</span><span class="sxs-lookup"><span data-stu-id="fe62e-140">To disable anonymous email and messaging, you add a clientPolicyEntry to this client policy by using the following commands.</span></span>

```
$policyEntry = New-CsClientPolicyEntry -Name AllowResourceAccountSendMessage -value $false
$clientPolicy = Get-CsClientPolicy -Identity SurfaceHubPolicy
$clientPolicy.PolicyEntry.Add($policyEntry)
Set-CsClientPolicy -Instance $clientPolicy
```

<span data-ttu-id="fe62e-141">Pour vérifier que la stratégie a été définie:</span><span class="sxs-lookup"><span data-stu-id="fe62e-141">To verify that the policy has been set:</span></span>

```
Select-Object -InputObject $clientPolicy -Property PolicyEntry
```

<span data-ttu-id="fe62e-142">La sortie doit être:</span><span class="sxs-lookup"><span data-stu-id="fe62e-142">The output should be:</span></span>

```
PolicyEntry
-----------
{Name=AllowResourceAccountSendMessage;Value=False}
```
    
    
<span data-ttu-id="fe62e-143">Pour modifier l’entrée de stratégie:</span><span class="sxs-lookup"><span data-stu-id="fe62e-143">To change the policy entry:</span></span>

```
$policyEntry =  New-CsClientPolicyEntry -Name AllowResourceAccountSendMessage -value $true
$clientPolicy | Set-CsClientPolicy -PolicyEntry @{Replace = $policyEntry}
``` 
    
<span data-ttu-id="fe62e-144">Pour supprimer l’entrée de stratégie:</span><span class="sxs-lookup"><span data-stu-id="fe62e-144">To remove the policy entry:</span></span>

```
$policyEntry = New-CsClientPolicyEntry -Name AllowResourceAccountSendMessage -value $true
$clientPolicy | Set-CsClientPolicy -PolicyEntry @{Remove = $policyEntry}
```

 





