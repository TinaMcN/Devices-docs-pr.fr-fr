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
# Configurer les comptes surface Hub 2 locaux avec PowerShell

## Se connecter à Exchange Server PowerShell

> [!IMPORTANT]
> Vous aurez besoin du nom de domaine complet (FQDN) pour le service d’accès client du serveur Exchange local pour certaines de ces applets de fonction.

```PowerShell
$ExchServer = Read-Host "Please Enter the FQDN of your Exchange Server"
$ExchSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri http://$ExchServer/PowerShell/ -Authentication Kerberos -Credential (Get-Credential)
Import-PSSession $ExchSession
```

## Créer le compte de l’appareil

```PowerShell
New-Mailbox -UserPrincipalName Hub01@contoso.com -Alias Hub01 -Name "Hub 01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

## Définir le traitement automatique du calendrier

```PowerShell
Set-CalendarProcessing -Identity "HUB01@contoso.com" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts   $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This room is equipped with a Surface Hub"
```

## Activation de l’objet Skype entreprise

> [!NOTE]
> Il est important que vous connaissiez le nom de domaine complet (FQDN) du pool d’inscriptions Skype entreprise.

```PowerShell
Enable-CsMeetingRoom -Identity Contoso\HUB01 -SipAddressType emailaddress -RegistrarPool SfbIEFE01.contoso.local
```

## Stratégie de messagerie d’appareil mobile

Vous devrez peut-être créer une stratégie de boîte aux lettres d’appareil mobile (également appelée stratégie ActiveSync) pour permettre à votre surface Hub de se connecter à votre environnement en ligne ou sur site.

## Créer une stratégie de messagerie d’appareil mobile surface Hub

```PowerShell
New-MobileDeviceMailboxPolicy -Name “Surface Hubs” -PasswordEnabled $false
```

## Paramètres supplémentaires

Nous vous recommandons d’ajouter un alerte aux salles de surface Hub de sorte que les utilisateurs n’aient pas à faire de la réunion une réunion Skype entreprise ou teams:

```PowerShell
Set-Mailbox "Surface Hub 2S" -MailTip "This is a Surface Hub room. Please make sure this is a Microsoft Teams meeting."
```
