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

- **Calendrier Microsoft teams et Skype entreprise:** Définissez le [**traitement automatique de calendrier**](https://docs.microsoft.com/surface-hub/surface-hub-2s-account?source=docs#set-calendar-auto-processing) pour ce compte.

## Créer un compte à l’aide de PowerShell

Au lieu d’utiliser le portail du centre d’administration Microsoft, vous pouvez créer le compte à l’aide de PowerShell.

### Connexion à Exchange Online PowerShell

```powershell
Install-Module -Name ExchangeOnlineManagement
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName admin@contoso.com -ShowProgress $true
```

### Créer une boîte aux lettres

```powershell
New-Mailbox -MicrosoftOnlineServicesID 'SurfaceHub01@contoso.com' -Alias SurfaceHub01 -Name "Surface Hub 01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String 'Pass@word1' -AsPlainText -Force)
```

### Définir le traitement automatique du calendrier

```powershell
Set-CalendarProcessing -Identity 'SurfaceHub01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity 'SurfaceHub01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Surface Hub. Please make sure this meeting is a Microsoft Teams meeting!"
```

### Activer ActiveSync si l’utilisation de l’application de messagerie est requise

 La stratégie ActiveSync par défaut fonctionne si unchnaged. Dans le cas contraire, créez une nouvelle stratégie et attribuez-la.

```powershell
New-MobileDeviceMailboxPolicy -Name:"SurfaceHub" -PasswordEnabled:$false
#Assign Policy to Hub:
Set-CASMailbox -Identity SurfaceHub01@contoso.com -ActiveSyncMailboxPolicy "SurfaceHub"
```
### Se connecter à AzureAD

```powershell
Connect-AzureAD
```

### Attribuer une licence

```powershell
Set-AzureADUser -ObjectId 'SurfaceHub01@contoso.com' -UsageLocation US
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense 
$License.SkuId = "c7df2760-2c81-4ef7-b578-5b5392b571df" 
$Licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses 
$Licenses.AddLicenses = $License 
Set-AzureADUserLicense -ObjectId 'SurfaceHub01@contoso.com' -AssignedLicenses $Licenses
```

### Vérifier les licences disponibles

```powershell
Get-AzureADUser -Filter "userPrincipalName eq 'SurfaceHub01@contoso.com'" |fl *
#Meeting Room Standard SKU:
6070a4c8-34c6-4937-8dfb-39bbc6397a60
```