---
title: Configurer les comptes surface Hub 2 locaux avec PowerShell
description: Découvrez comment configurer des comptes surface Hub 2 locaux avec PowerShell
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
ms.openlocfilehash: 6832f4e4b5bc307746ec5838c0f80d043a22021a
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10834001"
---
# <span data-ttu-id="bcb8b-104">Configurer les comptes surface Hub 2 locaux avec PowerShell</span><span class="sxs-lookup"><span data-stu-id="bcb8b-104">Configure Surface Hub 2S on-premises accounts with PowerShell</span></span>

## <span data-ttu-id="bcb8b-105">Se connecter à Exchange Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="bcb8b-105">Connect to Exchange Server PowerShell</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bcb8b-106">Vous aurez besoin du nom de domaine complet (FQDN) pour le service d’accès client du serveur Exchange local pour certaines de ces applets de fonction.</span><span class="sxs-lookup"><span data-stu-id="bcb8b-106">You'll need the Fully Qualified Domain Name (FQDN) for the Client Access service of the on-premises Exchange server for some of these cmdlets.</span></span>

```PowerShell
$ExchServer = Read-Host "Please Enter the FQDN of your Exchange Server"
$ExchSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri http://$ExchServer/PowerShell/ -Authentication Kerberos -Credential (Get-Credential)
Import-PSSession $ExchSession
```

## <span data-ttu-id="bcb8b-107">Créer le compte de l’appareil</span><span class="sxs-lookup"><span data-stu-id="bcb8b-107">Create the device account</span></span>

```PowerShell
New-Mailbox -UserPrincipalName Hub01@contoso.com -Alias Hub01 -Name "Hub 01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

## <span data-ttu-id="bcb8b-108">Définir le traitement automatique du calendrier</span><span class="sxs-lookup"><span data-stu-id="bcb8b-108">Set automatic calendar processing</span></span>

```PowerShell
Set-CalendarProcessing -Identity "HUB01@contoso.com" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts   $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This room is equipped with a Surface Hub"
```

## <span data-ttu-id="bcb8b-109">Activation de l’objet Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="bcb8b-109">Enable the Skype for Business object</span></span>

> [!NOTE]
> <span data-ttu-id="bcb8b-110">Il est important que vous connaissiez le nom de domaine complet (FQDN) du pool d’inscriptions Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="bcb8b-110">It is important that you know the FQDN of the Skype for Business Registrar Pool.</span></span>

```PowerShell
Enable-CsMeetingRoom -Identity Contoso\HUB01 -SipAddressType emailaddress -RegistrarPool SfbIEFE01.contoso.local
```

## <span data-ttu-id="bcb8b-111">Stratégie de messagerie d’appareil mobile</span><span class="sxs-lookup"><span data-stu-id="bcb8b-111">Mobile Device Mailbox Policy</span></span>

<span data-ttu-id="bcb8b-112">Vous devrez peut-être créer une stratégie de boîte aux lettres d’appareil mobile (également appelée stratégie ActiveSync) pour permettre à votre surface Hub de se connecter à votre environnement en ligne ou sur site.</span><span class="sxs-lookup"><span data-stu-id="bcb8b-112">You may need to create a Mobile Device Mailbox Policy (also known as ActiveSync Policy) to allow your Surface Hub to connect to your online or on-premises environment.</span></span>

## <span data-ttu-id="bcb8b-113">Créer une stratégie de messagerie d’appareil mobile surface Hub</span><span class="sxs-lookup"><span data-stu-id="bcb8b-113">Create a Surface Hub mobile device mailbox policy</span></span>

```PowerShell
New-MobileDeviceMailboxPolicy -Name “Surface Hubs” -PasswordEnabled $false
```

## <span data-ttu-id="bcb8b-114">Paramètres supplémentaires</span><span class="sxs-lookup"><span data-stu-id="bcb8b-114">Additional settings</span></span>

<span data-ttu-id="bcb8b-115">Nous vous recommandons d’ajouter un alerte aux salles de surface Hub de sorte que les utilisateurs n’aient pas à faire de la réunion une réunion Skype entreprise ou teams:</span><span class="sxs-lookup"><span data-stu-id="bcb8b-115">It is recommended to add a MailTip to Surface Hub rooms so users remember to make the meeting a Skype for Business or Teams meeting:</span></span>

```PowerShell
Set-Mailbox "Surface Hub 2S" -MailTip "This is a Surface Hub room. Please make sure this is a Microsoft Teams meeting."
```
