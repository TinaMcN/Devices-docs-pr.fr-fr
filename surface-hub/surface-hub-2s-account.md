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
# Créer un compte d’appareil SurfaceHub2S

La création d’un compte de périphérique surface Hub (également connu sous le nom de boîte aux lettres de salle) permet à surface Hub 2 de recevoir, approuver ou refuser des demandes de réunion et de participer à des réunions à l’aide de Microsoft teams ou de Skype entreprise. Configurez le compte de l’appareil lors de l’installation de OOBE (out-of-Box Experience). Le cas échéant, vous pouvez le modifier ultérieurement (sans passer par la configuration OOBE).

Contrairement aux boîtes aux lettres standard de salle qui ne sont pas désactivées par défaut, vous devez activer le compte de périphérique surface Hub 2S pour vous connecter à Microsoft teams et à Skype entreprise. Surface Hub 2 repose sur Exchange ActiveSync, qui nécessite une stratégie de boîte aux lettres ActiveSync sur le compte de l’appareil. Appliquez la stratégie de boîte aux lettres ActiveSync par défaut fournie avec Exchange Online.

Créez le compte à l’aide du centre d’administration 365 Microsoft ou en utilisant PowerShell. Vous pouvez utiliser Exchange Online PowerShell pour configurer des fonctionnalités spécifiques, notamment:

- Traitement de calendrier pour chaque compte d’appareil surface Hub.
- Réponses automatiques personnalisées à des demandes de planification.
- Si la stratégie de boîte aux lettres ActiveSync par défaut a déjà été modifiée par une autre personne ou par un autre processus, il est probable que vous deviez créer et affecter une nouvelle stratégie de boîte aux lettres ActiveSync.

> [!NOTE]  
> Le compte de l’appareil surface Hub ne prend pas en charge les fournisseurs d’identité fédérés tiers (FIPs) et doit être un compte Active Directory standard ou Azure Active Directory.

## Créer un compte à l’aide du centre d’administration 365 Microsoft

1. Dans le centre d’administration 365 Microsoft, accédez à **ressources** , puis sélectionnez **salles & équipements** et sélectionnez **+ salle**.

2. Fournissez un nom et une adresse de courrier pour le compte de l’appareil. Ne modifiez pas les paramètres restants dans l’État par défaut.

   ![Fournir un nom et une adresse de courrier](images/sh2-account2.png)

   ![Ne pas modifier les paramètres restants dans l’État par défaut](images/sh2-account3.png)

3. Définissez le mot de passe du compte de l’appareil. Pour définir le mot de passe, sélectionnez **utilisateurs** , puis **utilisateurs actifs**. Recherchez ensuite l’utilisateur nouvellement créé pour définir le mot de passe. Assurez-vous de **ne pas** sélectionner l’option faire en sorte que l' **utilisateur modifie son mot de passe lors de sa première connexion.**

   ![Définir le mot de passe du compte d’appareil](images/sh2-account4.png)

4. Affectez la salle à une licence Office 365. Il est recommandé d’affecter la licence de **salle de réunion** Office 365, une nouvelle option qui active automatiquement le compte pour Skype entreprise Online et Microsoft Teams.

   ![Attribution d’une licence Office 365](images/sh2-account5.png)

### Finalisez la configuration via PowerShell

- **Skype entreprise:** Pour Skype entreprise uniquement (local ou en ligne), vous pouvez activer l’objet Skype entreprise en exécutant **Enable-CsMeetingRoom** pour activer des fonctionnalités telles que la demande de salle de réunion pour les appels audio et salle d’attente.

- **Calendrier Microsoft teams et Skype entreprise:** Définissez le [**traitement automatique de calendrier**](https://docs.microsoft.com/surface-hub/surface-hub-2s-account?source=docs#set-calendar-auto-processing) pour ce compte.

## Créer un compte à l’aide de PowerShell

Au lieu d’utiliser le portail du centre d’administration Microsoft, vous pouvez créer le compte à l’aide de PowerShell.

### Connexion à Exchange Online PowerShell

```powershell
$365Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell -Credential (Get-Credential) -Authentication Basic –AllowRedirection
$ImportResults = Import-PSSession $365Session
```

### Créer une boîte aux lettres de salle

```powershell
New-Mailbox -MicrosoftOnlineServicesID account@YourDomain.com -Alias SurfaceHub2S -Name SurfaceHub2S -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString  -String "<Enter Strong Password>" -AsPlainText -Force)
```

### Définir le traitement automatique du calendrier

```powershell
Set-CalendarProcessing -Identity "account@YourDomain.com" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts   $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This room is equipped with a Surface Hub"
```

### Attribuer une licence

```powershell
Connect-MsolService
Set-Msoluser -UserPrincipalName account@YourDomain.com -UsageLocation IE
Set-MsolUserLicense -UserPrincipalName "account@YourDomain.com" -AddLicenses "contoso:MEETING_ROOM"
```

## Se connecter à Skype entreprise Online à l’aide de PowerShell

### Installer les conditions préalables

- [Visual C++ 2017 redistribuable](https://aka.ms/vs/15/release/vc_redist.x64.exe)
- [Module PowerShell de Skype entreprise Online](https://www.microsoft.com/download/confirmation.aspx?id=39366)

```powershell
Import-Module LyncOnlineConnector
$SfBSession = New-CsOnlineSession -Credential (Get-Credential)
Import-PSSession $SfBSession -AllowClobber

# Enable the Skype for Business meeting room
Enable-CsMeetingRoom -Identity account@YourDomain.com -RegistrarPool(Get-CsTenant).Registrarpool -SipAddressType EmailAddress
```
