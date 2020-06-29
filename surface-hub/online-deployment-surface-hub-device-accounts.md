---
title: Déploiement en ligne avec Office365 (SurfaceHub)
description: Cette rubrique contient des instructions concernant l’ajout d’un compte d’appareil pour votre Microsoft SurfaceHub lorsque vous disposez d’un déploiement pur, en ligne.
ms.assetid: D325CA68-A03F-43DF-8520-EACF7C3EDEC1
ms.reviewer: ''
manager: laurawi
keywords: compte d’appareil du SurfaceHub, déploiement en ligne
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 02/21/2018
ms.localizationpriority: medium
ms.openlocfilehash: b38b8eb0ef13c2e945d63821e6e246ac7a59b2d7
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10833617"
---
# <span data-ttu-id="1e536-104">Déploiement en ligne avec Office365 (SurfaceHub)</span><span class="sxs-lookup"><span data-stu-id="1e536-104">Online deployment with Office 365 (Surface Hub)</span></span>


<span data-ttu-id="1e536-105">Cette rubrique contient des instructions concernant l’ajout d’un compte d’appareil pour votre Microsoft SurfaceHub lorsque vous disposez d’un déploiement pur, en ligne.</span><span class="sxs-lookup"><span data-stu-id="1e536-105">This topic has instructions for adding a device account for your Microsoft Surface Hub when you have a pure, online deployment.</span></span>

<span data-ttu-id="1e536-106">Si vous disposez d’un déploiement pur, en ligne (O365), vous pouvez [utiliser les scripts PowerShell fournis](appendix-a-powershell-scripts-for-surface-hub.md#create-os356-ps-scripts) pour créer des comptes d’appareil.</span><span class="sxs-lookup"><span data-stu-id="1e536-106">If you have a pure, online (O365) deployment, then you can [use the provided PowerShell scripts](appendix-a-powershell-scripts-for-surface-hub.md#create-os356-ps-scripts) to create device accounts.</span></span> 

1. <span data-ttu-id="1e536-107">Démarrez une session PowerShell à distance sur unPC et connectez-vous à Exchange.</span><span class="sxs-lookup"><span data-stu-id="1e536-107">Start a remote PowerShell session on a PC and connect to Exchange.</span></span>

   <span data-ttu-id="1e536-108">Assurez-vous de disposer de l’ensemble approprié d’autorisations pour exécuter les applets de commande associées.</span><span class="sxs-lookup"><span data-stu-id="1e536-108">Be sure you have the right permissions set to run the associated cmdlets.</span></span>

   ```PowerShell
   Set-ExecutionPolicy RemoteSigned
   $org='contoso.microsoft.com'
   $cred=Get-Credential admin@$org
   $sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic -AllowRedirection
   Import-PSSession $sess
   ```

2. <span data-ttu-id="1e536-109">Une fois une session établie, vous allez créer une boîte aux lettres et l’activer en tant que RoomMailboxAccount, ou vous allez modifier les paramètres d’une boîte aux lettres de salle existante.</span><span class="sxs-lookup"><span data-stu-id="1e536-109">After establishing a session, you’ll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="1e536-110">Cela permettra au compte de s’authentifier sur le SurfaceHub.</span><span class="sxs-lookup"><span data-stu-id="1e536-110">This will allow the account to authenticate into the Surface Hub.</span></span>

   <span data-ttu-id="1e536-111">Si vous modifiez une boîte aux lettres de ressources existante:</span><span class="sxs-lookup"><span data-stu-id="1e536-111">If you're changing an existing resource mailbox:</span></span>

   ```PowerShell
   Set-Mailbox -Identity 'HUB01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

   <span data-ttu-id="1e536-112">Si vous créez une boîte aux lettres de ressources:</span><span class="sxs-lookup"><span data-stu-id="1e536-112">If you’re creating a new resource mailbox:</span></span>

   ```PowerShell
   New-Mailbox -MicrosoftOnlineServicesID HUB01@contoso.com -Alias HUB01 -Name "Hub-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="1e536-113">Après avoir configuré la boîte aux lettres, vous devez créer une stratégie ExchangeActiveSync ou utiliser une stratégie existante compatible.</span><span class="sxs-lookup"><span data-stu-id="1e536-113">After setting up the mailbox, you will need to either create a new Exchange ActiveSync policy, or use a compatible existing policy.</span></span>

   <span data-ttu-id="1e536-114">Les Surface Hub sont uniquement compatibles avec les comptes d’appareil dotés d’une stratégie ActiveSync, où la propriété **PasswordEnabled** est définie sur False.</span><span class="sxs-lookup"><span data-stu-id="1e536-114">Surface Hubs are only compatible with device accounts that have an ActiveSync policy where the **PasswordEnabled** property is set to False.</span></span> <span data-ttu-id="1e536-115">Si la propriété n’est pas définie correctement, les services Exchange sur le SurfaceHub (courrier, calendrier et accès aux réunions) ne seront pas activés.</span><span class="sxs-lookup"><span data-stu-id="1e536-115">If this isn’t set properly, then Exchange services on the Surface Hub (mail, calendar, and joining meetings), will not be enabled.</span></span>

   <span data-ttu-id="1e536-116">Si vous n’avez pas encore créé de stratégie compatible, utilisez l’applet de commande suivante: celle-ci crée une stratégie appelée SurfaceHub.</span><span class="sxs-lookup"><span data-stu-id="1e536-116">If you haven’t created a compatible policy yet, use the following cmdlet—this one creates a policy called "Surface Hubs".</span></span> <span data-ttu-id="1e536-117">Une fois qu’elle est créée, vous pouvez appliquer la même stratégie à d’autres comptes d’appareil.</span><span class="sxs-lookup"><span data-stu-id="1e536-117">Once it’s created, you can apply the same policy to other device accounts.</span></span>

   ```PowerShell
   $easPolicy = New-MobileDeviceMailboxPolicy -Name "SurfaceHubs" -PasswordEnabled $false -AllowNonProvisionableDevices $True
   ```

   <span data-ttu-id="1e536-118">Une fois que vous disposez d’une stratégie compatible, vous devez l’appliquer au compte d’appareil.</span><span class="sxs-lookup"><span data-stu-id="1e536-118">Once you have a compatible policy, then you will need to apply the policy to the device account.</span></span>

   ```PowerShell
   Set-CASMailbox 'HUB01@contoso.com' -ActiveSyncMailboxPolicy $easPolicy.Id
   ```

4. <span data-ttu-id="1e536-119">Diverses propriétés Exchange doivent être définies sur le compte d’appareil pour améliorer l’expérience de réunions.</span><span class="sxs-lookup"><span data-stu-id="1e536-119">Various Exchange properties must be set on the device account to improve the meeting experience.</span></span> <span data-ttu-id="1e536-120">Vous pouvez voir les propriétés qui doivent être définies dans la section [Propriétés Exchange](exchange-properties-for-surface-hub-device-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="1e536-120">You can see which properties need to be set in the [Exchange properties](exchange-properties-for-surface-hub-device-accounts.md) section.</span></span>

   ```PowerShell
   Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
   ```

5. <span data-ttu-id="1e536-121">Connectez-vous à AzureAD.</span><span class="sxs-lookup"><span data-stu-id="1e536-121">Connect to Azure AD.</span></span>
    
   <span data-ttu-id="1e536-122">Vous devez d’abord installer le module Azure AD pour PowerShell version2.</span><span class="sxs-lookup"><span data-stu-id="1e536-122">You first need to install Azure AD module for PowerShell version 2.</span></span> <span data-ttu-id="1e536-123">Dans une invite de commandes avec élévation de privilèges, exécutez la commande suivante:</span><span class="sxs-lookup"><span data-stu-id="1e536-123">In an elevated powershell prompt run the following command :</span></span>
    
   ```PowerShell
   Install-Module -Name AzureAD
   ```
   <span data-ttu-id="1e536-124">Vous devez vous connecter à AzureAD pour appliquer certains paramètres du compte.</span><span class="sxs-lookup"><span data-stu-id="1e536-124">You need to connect to Azure AD to apply some account settings.</span></span> <span data-ttu-id="1e536-125">Vous pouvez exécuter cette applet de commande pour vous connecter.</span><span class="sxs-lookup"><span data-stu-id="1e536-125">You can run this cmdlet to connect.</span></span>

   ```PowerShell
   Import-Module AzureAD
   Connect-AzureAD -Credential $cred
   ```

6. <span data-ttu-id="1e536-126">Si vous décidez que le mot de passe n’expire pas, vous pouvez également définir cette option avec des applets de commande PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1e536-126">If you decide to have the password not expire, you can set that with PowerShell cmdlets too.</span></span> <span data-ttu-id="1e536-127">Consultez [Gestion des mots de passe](password-management-for-surface-hub-device-accounts.md) pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="1e536-127">See [Password management](password-management-for-surface-hub-device-accounts.md) for more information.</span></span>

   ```PowerShell
   Set-AzureADUser -ObjectId "HUB01@contoso.com" -PasswordPolicies "DisablePasswordExpiration"
   ```

7. <span data-ttu-id="1e536-128">Surface Hub nécessite une licence pour les fonctionnalités de Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="1e536-128">Surface Hub requires a license for Skype for Business functionality.</span></span> <span data-ttu-id="1e536-129">Pour activer SkypeEntreprise, votre environnement doit respecter les [conditions préalables pour Skype Entreprise Online](hybrid-deployment-surface-hub-device-accounts.md#skype-for-business-online).</span><span class="sxs-lookup"><span data-stu-id="1e536-129">In order to enable Skype for Business, your environment will need to meet the [prerequisites for Skype for Business online](hybrid-deployment-surface-hub-device-accounts.md#skype-for-business-online).</span></span>
   
   <span data-ttu-id="1e536-130">Ensuite, vous pouvez utiliser `Get-AzureADSubscribedSku` pour récupérer la liste des références (SKU) disponibles pour votre clientO365.</span><span class="sxs-lookup"><span data-stu-id="1e536-130">Next, you can use `Get-AzureADSubscribedSku` to retrieve a list of available SKUs for your O365 tenant.</span></span>

   <span data-ttu-id="1e536-131">Une fois que vous avez répertorié les références, vous devez attribuer le SkuId que vous souhaitez à la variable `$License.SkuId`.</span><span class="sxs-lookup"><span data-stu-id="1e536-131">Once you list out the SKUs, you'll need to assign the SkuId you want to the `$License.SkuId` variable.</span></span>

   ```PowerShell
   Set-AzureADUser -ObjectId "HUB01@contoso.com" -UsageLocation "US"
    
   Get-AzureADSubscribedSku | Select Sku*,*Units
   $License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
   $License.SkuId = SkuId You selected 
    
   $AssignedLicenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
   $AssignedLicenses.AddLicenses = $License
   $AssignedLicenses.RemoveLicenses = @()
    
   Set-AzureADUserLicense -ObjectId "HUB01@contoso.com"  -AssignedLicenses $AssignedLicenses
   ```

8. <span data-ttu-id="1e536-132">Activez le compte d’appareil avec SkypeEntreprise.</span><span class="sxs-lookup"><span data-stu-id="1e536-132">Enable the device account with Skype for Business.</span></span>
   <span data-ttu-id="1e536-133">Si le module PowerShell de Skype Entreprise n’est pas installé, [téléchargez le module Windows PowerShell de Skype Entreprise Online](https://www.microsoft.com/download/details.aspx?id=39366).</span><span class="sxs-lookup"><span data-stu-id="1e536-133">If the Skype for Business PowerShell module is not installed, [download the Skype for Business Online Windows PowerShell Module](https://www.microsoft.com/download/details.aspx?id=39366).</span></span> 

   - <span data-ttu-id="1e536-134">Commencez par créer une session PowerShell à distance à partir d’un PC.</span><span class="sxs-lookup"><span data-stu-id="1e536-134">Start by creating a remote PowerShell session from a PC.</span></span>

     ```PowerShell
     Import-Module SkypeOnlineConnector  
     $cssess=New-CsOnlineSession -Credential $cred  
     Import-PSSession $cssess -AllowClobber
     ```

   - <span data-ttu-id="1e536-135">Ensuite, si vous n’êtes pas certain de la valeur à utiliser pour le paramètre `RegistrarPool` dans votre environnement, vous pouvez obtenir cette valeur à partir d’un utilisateur Skype Entreprise existant en utilisant l'applet de commande suivante (par exemple, <em>alice@contoso.com</em>):</span><span class="sxs-lookup"><span data-stu-id="1e536-135">Next, if you aren't sure what value to use for the `RegistrarPool` parameter in your environment, you can get the value from an existing Skype for Business user using this cmdlet (for example, <em>alice@contoso.com</em>):</span></span>

       ```PowerShell
       Get-CsOnlineUser -Identity 'alice@contoso.com' | fl registrarpool
       ```
       <span data-ttu-id="1e536-136">OU en définissant une variable</span><span class="sxs-lookup"><span data-stu-id="1e536-136">OR by setting a variable</span></span>
        
       ```PowerShell
    $strRegistrarPool = Get-CsOnlineUser -Identity 'alice@contoso.com' | fl registrarpool | out-string
    $strRegistrarPool = $strRegistrarPool.Substring($strRegistrarPool.IndexOf(':') + 2)
       ```
        
   - <span data-ttu-id="1e536-137">Activez le compte Surface Hub à l’aide de l’applet de commande suivante:</span><span class="sxs-lookup"><span data-stu-id="1e536-137">Enable the Surface Hub account with the following cmdlet:</span></span>
      
       ```PowerShell
       Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool yourRegistrarPool -SipAddressType EmailAddress
       ```
        
       <span data-ttu-id="1e536-138">OU en utilisant la variable $strRegistarPool ci-dessus</span><span class="sxs-lookup"><span data-stu-id="1e536-138">OR using the $strRegistarPool variable from above</span></span>
        
       ```PowerShell
       Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool $strRegistrarPool -SipAddressType EmailAddress
       ```

<span data-ttu-id="1e536-139">Pour la validation, vous devez être en mesure d’utiliser n’importe quel client Skype Entreprise (PC, Android, etc.) pour vous connecter à ce compte.</span><span class="sxs-lookup"><span data-stu-id="1e536-139">For validation, you should be able to use any Skype for Business client (PC, Android, etc) to sign in to this account.</span></span>





