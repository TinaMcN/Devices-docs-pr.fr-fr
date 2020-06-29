---
title: Déploiement sur site à forêts multiples (SurfaceHub)
description: Cette rubrique explique comment ajouter un compte d’appareil pour votre Microsoft SurfaceHub lorsque vous disposez d’un déploiement sur site à forêts multiples.
keywords: déploiement à forêts multiples, déploiement sur site, compte d’appareil, SurfaceHub
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.date: 08/28/2018
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: 48fe874175a2c55b7e95ba0974cefe29f710c134
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10833618"
---
# <span data-ttu-id="c3285-104">Déploiement sur site pour SurfaceHub dans un environnement à forêts multiples</span><span class="sxs-lookup"><span data-stu-id="c3285-104">On-premises deployment for Surface Hub in a multi-forest environment</span></span>


<span data-ttu-id="c3285-105">Cette rubrique explique comment ajouter un compte d’appareil pour votre Microsoft SurfaceHub lorsque vous disposez d’un déploiement sur site à forêts multiples.</span><span class="sxs-lookup"><span data-stu-id="c3285-105">This topic explains how you add a device account for your Microsoft Surface Hub when you have a multi-forest, on-premises deployment.</span></span>

<span data-ttu-id="c3285-106">Si vous disposez d’un déploiement sur site à forêts multiples avec MicrosoftExchange2013 ou une version ultérieure et SkypeEntreprise2013 ou une version ultérieure, vous pouvez [utiliser les scripts PowerShell fournis](appendix-a-powershell-scripts-for-surface-hub.md#create-on-premises-ps-scripts) pour créer des comptes d’appareil.</span><span class="sxs-lookup"><span data-stu-id="c3285-106">If you have a multi-forest on-premises deployment with Microsoft Exchange 2013 or later and Skype for Business 2013 or later, then you can [use the provided PowerShell scripts](appendix-a-powershell-scripts-for-surface-hub.md#create-on-premises-ps-scripts) to create device accounts.</span></span> <span data-ttu-id="c3285-107">Si vous utilisez un déploiement à forêt unique, consultez [Déploiement sur site pour SurfaceHub dans un environnement à forêt unique](on-premises-deployment-surface-hub-device-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="c3285-107">If you’re using a single-forest deployment, see [On-premises deployment for Surface Hub in a single-forest environment](on-premises-deployment-surface-hub-device-accounts.md).</span></span>

1.  <span data-ttu-id="c3285-108">Démarrez une session PowerShell à distance à partir d’un PC et connectez-vous à Exchange.</span><span class="sxs-lookup"><span data-stu-id="c3285-108">Start a remote PowerShell session from a PC and connect to Exchange.</span></span>

    <span data-ttu-id="c3285-109">Assurez-vous de disposer de l’ensemble approprié d’autorisations pour exécuter les applets de commande associées.</span><span class="sxs-lookup"><span data-stu-id="c3285-109">Be sure you have the right permissions set to run the associated cmdlets.</span></span>

    <span data-ttu-id="c3285-110">Notez ici que `$strExchangeServer` est le nom de domaine complet de votre serveur Exchange, et que `$strLyncFQDN` est le nom de domaine complet de votre serveur Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="c3285-110">Note here that `$strExchangeServer` is the fully qualified domain name (FQDN) of your Exchange server, and `$strLyncFQDN` is the FQDN of your Skype for Business server.</span></span>

    ```PowerShell
    Set-ExecutionPolicy Unrestricted
    $org='contoso.microsoft.com'
    $cred=Get-Credential $admin@$org
    $sessExchange = New-PSSession -ConfigurationName microsoft.exchange -Credential $cred -AllowRedirection -Authentication Kerberos -ConnectionUri "http://$strExchangeServer/powershell" -WarningAction SilentlyContinue
    $sessLync = New-PSSession -Credential $cred -ConnectionURI "https://$strLyncFQDN/OcsPowershell" -AllowRedirection -WarningAction SilentlyContinue
    Import-PSSession $sessExchange
    Import-PSSession $sessLync
    ```

2.  <span data-ttu-id="c3285-111">Après avoir établi une session, créez une nouvelle boîte aux lettres dans la forêt de ressources.</span><span class="sxs-lookup"><span data-stu-id="c3285-111">After establishing a session, create a new mailbox in the Resource Forest.</span></span> <span data-ttu-id="c3285-112">Cela permettra au compte de s’authentifier sur le SurfaceHub.</span><span class="sxs-lookup"><span data-stu-id="c3285-112">This will allow the account to authenticate into the Surface Hub.</span></span>

    <span data-ttu-id="c3285-113">Si vous modifiez une boîte aux lettres de ressources existante:</span><span class="sxs-lookup"><span data-stu-id="c3285-113">If you're changing an existing resource mailbox:</span></span>

    ```PowerShell
    New-Mailbox -UserPrincipalName HUB01@contoso.com -Alias HUB01 -Name "Hub-01"
    ```

3.  <span data-ttu-id="c3285-114">Après avoir configuré la boîte aux lettres, vous devez créer une stratégie ExchangeActiveSync ou utiliser une stratégie existante compatible.</span><span class="sxs-lookup"><span data-stu-id="c3285-114">After setting up the mailbox, you will need to either create a new Exchange ActiveSync policy, or use a compatible existing policy.</span></span>

    <span data-ttu-id="c3285-115">Les Surface Hub sont uniquement compatibles avec les comptes d’appareil dotés d’une stratégie ActiveSync, où la propriété **PasswordEnabled** est définie sur **False**.</span><span class="sxs-lookup"><span data-stu-id="c3285-115">Surface Hubs are only compatible with device accounts that have an ActiveSync policy where the **PasswordEnabled** property is set to **False**.</span></span> <span data-ttu-id="c3285-116">Si la propriété n’est pas définie correctement, les services Exchange sur le SurfaceHub (courrier, calendrier et accès aux réunions) ne seront pas activés.</span><span class="sxs-lookup"><span data-stu-id="c3285-116">If this isn’t set properly, then Exchange services on the Surface Hub (mail, calendar, and joining meetings), will not be enabled.</span></span>

    <span data-ttu-id="c3285-117">Si vous n’avez pas encore créé de stratégie compatible, utilisez l’applet de commande suivante: celle-ci crée une stratégie appelée SurfaceHub.</span><span class="sxs-lookup"><span data-stu-id="c3285-117">If you haven’t created a compatible policy yet, use the following cmdlet-—this one creates a policy called "Surface Hubs".</span></span> <span data-ttu-id="c3285-118">Une fois qu’elle est créée, vous pouvez appliquer la même stratégie à d’autres comptes d’appareil.</span><span class="sxs-lookup"><span data-stu-id="c3285-118">Once it’s created, you can apply the same policy to other device accounts.</span></span>

    ```PowerShell
    $easPolicy = New-MobileDeviceMailboxPolicy -Name “SurfaceHubs” -PasswordEnabled $false
    ```

    <span data-ttu-id="c3285-119">Une fois que vous disposez d’une stratégie compatible, vous devez l’appliquer au compte d’appareil.</span><span class="sxs-lookup"><span data-stu-id="c3285-119">Once you have a compatible policy, then you will need to apply the policy to the device account.</span></span> 

    ```PowerShell
    Set-CASMailbox $acctUpn -ActiveSyncMailboxPolicy $easPolicy -ActiveSyncEnabled $true
    Set-Mailbox $acctUpn -Type Room
    ```

4.  <span data-ttu-id="c3285-120">Diverses propriétés Exchange peuvent être définies sur le compte d’appareil afin d'améliorer l’expérience de réunion pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="c3285-120">Various Exchange properties can be set on the device account to improve the meeting experience for people.</span></span> <span data-ttu-id="c3285-121">Vous pouvez voir les propriétés qui doivent être définies dans la section [Propriétés Exchange](exchange-properties-for-surface-hub-device-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="c3285-121">You can see which properties need to be set in the [Exchange properties](exchange-properties-for-surface-hub-device-accounts.md) section.</span></span>

    ```PowerShell
    Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
    Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
    ```

5.  <span data-ttu-id="c3285-122">Si vous décidez que le mot de passe n’expire pas, vous pouvez également définir cette option avec des applets de commande PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c3285-122">If you decide to have the password not expire, you can set that with PowerShell cmdlets too.</span></span> <span data-ttu-id="c3285-123">Consultez [Gestion des mots de passe](password-management-for-surface-hub-device-accounts.md) pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="c3285-123">See [Password management](password-management-for-surface-hub-device-accounts.md) for more information.</span></span> <span data-ttu-id="c3285-124">Cela doit être défini dans la forêt d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="c3285-124">This should be set in the User Forest.</span></span>

    ```PowerShell
    Set-AdUser $acctUpn -PasswordNeverExpires $true
    ```

6.  <span data-ttu-id="c3285-125">Activez le compte dans Active Directory de sorte qu’il s’authentifie auprès du SurfaceHub.</span><span class="sxs-lookup"><span data-stu-id="c3285-125">Enable the account in Active Directory so it will authenticate to the Surface Hub.</span></span> <span data-ttu-id="c3285-126">Cela doit être défini dans la forêt d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="c3285-126">This should be set in the User Forest.</span></span>

    ```PowerShell
    Set-AdUser $acctUpn -Enabled $true
    ```

6. <span data-ttu-id="c3285-127">Vous devez maintenant changer la boîte aux lettres de salle en boîte aux lettres liée:</span><span class="sxs-lookup"><span data-stu-id="c3285-127">You now need to change the room mailbox to a linked mailbox:</span></span>

    ```PowerShell
    $cred=Get-Credential AuthForest\ADAdmin
    Set-mailbox -Alias LinkedRoomTest1 -LinkedMasterAccount AuthForest\LinkedRoomTest1 -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -Name LinkedRoomTest1 -LinkedCredential $cred -Identity LinkedRoomTest1
    ```

7.  <span data-ttu-id="c3285-128">Activez le compte d’appareil avec Skype Entreprise en activant votre compte AD Surface Hub sur un pool Skype Entreprise Server:</span><span class="sxs-lookup"><span data-stu-id="c3285-128">Enable the device account with Skype for Business by enabling your Surface Hub AD account on a Skype for Business Server pool:</span></span>

    ```PowerShell
    Enable-CsMeetingRoom -SipAddress "sip:HUB01@contoso.com"
     -DomainController DC-ND-001.contoso.com -RegistrarPool LYNCPool15.contoso.com
     -Identity HUB01
    ```

    <span data-ttu-id="c3285-129">Vous devrez utiliser l’adresse et le contrôleur de domaine du protocole SIP (Session Initiation Protocol) du Surface Hub, ainsi que vos propres identificateur de pool et identité d’utilisateur Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="c3285-129">You'll need to use the Session Initiation Protocol (SIP) address and domain controller for the Surface Hub, along with your own Skype for Business Server pool identifier and user identity.</span></span>


## <span data-ttu-id="c3285-130">Désactiver la messagerie instantanée et la messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="c3285-130">Disable anonymous email and IM</span></span>



<span data-ttu-id="c3285-131">Surface Hub utilise un compte d’appareil pour fournir des services de messagerie et de collaboration (messagerie instantanée, vidéo, voix).</span><span class="sxs-lookup"><span data-stu-id="c3285-131">Surface Hub uses a device account to provide email and collaboration services (IM, video, voice).</span></span> <span data-ttu-id="c3285-132">Ce compte d’appareil est utilisé comme identité d’origine (la partie «de») lors de l’envoi d’e-mails, de messages instantanés et de la mise des appels.</span><span class="sxs-lookup"><span data-stu-id="c3285-132">This device account is used as the originating identity (the “from” party) when sending email, IM, and placing calls.</span></span> <span data-ttu-id="c3285-133">Étant donné que ce compte ne provient pas d’un utilisateur identifiable individuel, il est considéré comme «anonyme», car il provient du compte de l’appareil de surface Hub.</span><span class="sxs-lookup"><span data-stu-id="c3285-133">As this account is not coming from an individual, identifiable user, it is deemed “anonymous” because it originated from the Surface Hub's device account.</span></span>  

<span data-ttu-id="c3285-134">Supposez qu’une stratégie de client par utilisateur est affectée à chaque appareil de salle de réunion ayant une identité de **SurfaceHubPolicy**.</span><span class="sxs-lookup"><span data-stu-id="c3285-134">Assume you have a per-user client policy assigned to each meeting room device with an identity of **SurfaceHubPolicy**.</span></span> <span data-ttu-id="c3285-135">Pour désactiver la messagerie instantanée et la messagerie électronique anonyme, vous devez ajouter un clientPolicyEntry à cette stratégie client en utilisant les commandes suivantes.</span><span class="sxs-lookup"><span data-stu-id="c3285-135">To disable anonymous email and messaging, you add a clientPolicyEntry to this client policy by using the following commands.</span></span>

```
$policyEntry = New-CsClientPolicyEntry -Name AllowResourceAccountSendMessage -value $false
$clientPolicy = Get-CsClientPolicy -Identity SurfaceHubPolicy
$clientPolicy.PolicyEntry.Add($policyEntry)
Set-CsClientPolicy -Instance $clientPolicy
```

<span data-ttu-id="c3285-136">Pour vérifier que la stratégie a été définie:</span><span class="sxs-lookup"><span data-stu-id="c3285-136">To verify that the policy has been set:</span></span>

```
Select-Object -InputObject $clientPolicy -Property PolicyEntry
```

<span data-ttu-id="c3285-137">La sortie doit être:</span><span class="sxs-lookup"><span data-stu-id="c3285-137">The output should be:</span></span>

```
PolicyEntry
-----------
{Name=AllowResourceAccountSendMessage;Value=False}
```
    
    
<span data-ttu-id="c3285-138">Pour modifier l’entrée de stratégie:</span><span class="sxs-lookup"><span data-stu-id="c3285-138">To change the policy entry:</span></span>

```
$policyEntry =  New-CsClientPolicyEntry -Name AllowResourceAccountSendMessage -value $true
$clientPolicy | Set-CsClientPolicy -PolicyEntry @{Replace = $policyEntry}
``` 
    
<span data-ttu-id="c3285-139">Pour supprimer l’entrée de stratégie:</span><span class="sxs-lookup"><span data-stu-id="c3285-139">To remove the policy entry:</span></span>

```
$policyEntry = New-CsClientPolicyEntry -Name AllowResourceAccountSendMessage -value $true
$clientPolicy | Set-CsClientPolicy -PolicyEntry @{Remove = $policyEntry}
```
 





