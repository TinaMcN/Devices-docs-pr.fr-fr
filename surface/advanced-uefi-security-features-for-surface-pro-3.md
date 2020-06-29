---
title: Fonctionnalités de sécuritéUEFI avancées pourSurfacePro3(Surface)
description: Cet article décrit comment installer et configurer la mise à jour v3.11.760.0 de l’UEFI pour activer les options de sécurité supplémentaires pour SurfacePro3.
ms.assetid: 90F790C0-E5FC-4482-AD71-60589E3C9C93
ms.reviewer: ''
manager: laurawi
keywords: sécurité, fonctionnalités, configurer, matériel, appareil, personnaliser, script, mise à jour
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices, security
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.openlocfilehash: 9460b4a5e8b44cbf4b6af57d01aab3b09afb49de
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832580"
---
# Fonctionnalités de sécuritéUEFI avancées pour SurfacePro3


Cet article décrit comment installer et configurer la mise à jour v3.11.760.0 de l’UEFI pour activer les options de sécurité supplémentaires pour les appareils SurfacePro3.

Pour avoir un contrôle plus précis de la sécurité des appareils Surface, la mise à jour v3.11.760.0 de l’UEFI fournit des options de sécurité supplémentaires qui vous permettent de désactiver des périphériques matériels spécifiques ou d’empêcher le démarrage à partir de ces derniers. Une fois la mise à jour de l’UEFI installée sur un appareil, vous pouvez la configurer automatiquement ou manuellement en exécutant un script.

## Installation manuelle de la mise à jour de l’UEFI


Avant de pouvoir configurer les fonctionnalités de sécurité avancée de votre appareilSurface, vous devez tout d’abord installer la mise à jour v3.11.760.0 de l’UEFI. Cette mise à jour s’installe automatiquement si vous recevez vos mises à jour à partir de WindowsUpdate. Pour en savoir plus sur la configuration de Windows pour recevoir des mises à jour automatiques à partir de WindowsUpdate, voir [Comment faire pour configurer et utiliser les mises à jour automatiques dans Windows](https://support.microsoft.com/kb/306525).

Pour mettre à jour les fonctionnalitésUEFI sur SurfacePro3, vous pouvez télécharger et installer les mises à jour UEFISurface à partir du pack des microprogrammes et des pilotesSurfacePro3. Ces packs du microprogramme et des pilotes sont disponibles sur la [page Surface Pro 3](https://www.microsoft.com/download/details.aspx?id=38826) du Centre de téléchargement Microsoft. Pour plus d’informations sur les packs du microprogramme et des pilotes, consultez la section [Télécharger le dernier microprogramme et les pilotes les plus récents pour les appareilsSurface](https://technet.microsoft.com/itpro/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices). Les packs du microprogramme et des pilotes sont disponibles aux formats autonomes WindowsInstaller(.msi) et d’archive (.zip). Pour plus d’informations sur ces deuxformats et sur la manière dont vous pouvez les utiliser pour mettre à jour vos pilotes, accédez à la section [Gérer les mises à jour du microprogramme et des pilotes Surface](https://technet.microsoft.com/itpro/surface/manage-surface-pro-3-firmware-updates).

## Configurer manuellement des paramètres de sécurité supplémentaires


>[!NOTE]
>Pour régler les paramètres de microprogramme sur un appareil Surface, celui-ci doit d’abord être hors tension. Appuyez longuement sur le bouton **Augmenter le volume**, puis appuyez sur et relâchez le bouton **Marche/Arrêt**. Relâchez le bouton **Augmenter le volume** lorsque l’appareil démarre.

Une fois que la mise à jour v3.11.760.0 de l’UEFI est installée sur un appareil Surface, un menu UEFI supplémentaire nommé **Sécurité avancée de l’appareil** devient disponible. Si vous cliquez sur ce menu, les options suivantes sont affichées:

| Option         | Description                                                                                                                                                                          | Paramètres disponibles (les paramètres par défaut sont en gras) |
|----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------|
| Démarrage réseau   | Active ou désactive la possibilité pour l’appareil Surface de démarrer à partir du réseau (également appelé démarrage PXE).                                                                            | **Activé**, Non démarrable                   |
| PortUSB latéral       | Active ou désactive le port USB sur le côté de l’appareil Surface. En outre, le port USB peut être activé, mais sans autoriser le démarrage.                                                | **Activé**, Non démarrable, Désactivé         |
| Port de station d’accueil   | Active ou désactive les ports sur la station d’accueil de l’appareil Surface. En outre, le port de station d’accueil peut être activé, tout en étant capable de bloquer le démarrage à partir d’un port USB ou Ethernet quelconque dans la station d’accueil. | **Activé**, Non démarrable, Désactivé         |
| Caméra frontale   | Active ou désactive la caméra frontale de l’appareil Surface.                                                                                                                   | **Activé**, Désactivé                       |
| Caméra arrière    | Active ou désactive la caméra arrière de l’appareil Surface.                                                                                                                    | **Activé**, Désactivé                       |
| Audio intégré | Active ou désactive l’audio sur l’appareil Surface.                                                                                                                                     | **Activé**, Désactivé                       |
| microSD        | Active ou désactive la fente microSD sur l’appareil Surface.                                                                                                                          | **Activé**, Désactivé                       |
| WiFi           | Active ou désactive le transmetteur Wi-Fi intégré à l’appareil Surface. Désactive également le Bluetooth.                                                                              | **Activé**, Désactivé                       |
| Bluetooth      | Active ou désactive le transmetteur Bluetooth intégré à l’appareil Surface.                                                                                                        | **Activé**, Désactivé                       |

 

## Automatiser les paramètres de sécurité supplémentaires


En tant que professionnel de l’informatique avec des privilèges d’administration, vous pouvez automatiser la configuration des paramètres UEFI en tirant parti des [Outils de microprogramme de SurfacePro3 (476Ko)](https://go.microsoft.com/fwlink/p/?LinkID=618038), disponibles dans le Centre de téléchargementMicrosoft. Ces outils installent un assembly .NET qui peut être appelé à partir d’applications ou de scripts personnalisés quelconques.

**Conditions préalables**

-   Les exemples de script ci-dessous utilisent l’extension mentionnée précédemment et supposent donc que l’outil a été installé sur l’appareil géré.
-   Les scripts doivent être exécutés avec des privilèges d’administration.
-   La commande WindowsPowerShell [**Set-ExecutionPolicy Unrestricted**](https://technet.microsoft.com/library/ee176961.aspx) doit être appelée avant l’exécution des exemples de script s’ils n’ont pas été signés numériquement.

**Exemples de scripts**

>**Remarque**:&nbsp;&nbsp;Le mot de passe UEFI utilisé dans les exemples de script ci-dessous est présenté en texte clair. Nous vous recommandons vivement d’enregistrer les scripts dans un emplacement protégé et de les exécuter dans un environnement contrôlé.


Afficher toutes les options configurables:

```
# Load the extension 
[System.Reflection.Assembly]::Load("SurfaceUefiManager, Version=1.0.5483.22783, Culture=neutral, PublicKeyToken=20606f4b5276c705")  
 
# Get the collection of all configurable settings 
$uefiOptions = [Microsoft.Surface.FirmwareOption]::All() 
 
foreach ($uefiOption in $uefiOptions) 
{ 
    Write-Host "Name:" $uefiOption.Name 
    Write-Host " Description =" $uefiOption.Description 
    Write-Host " Current Value =" $uefiOption.CurrentValue 
    Write-Host " Default Value =" $uefiOption.DefaultValue 
    Write-Host " Proposed Value =" $uefiOption.ProposedValue 
     
    # This gives usage and validation information 
    Write-Host " Allowed Values =" $uefiOption.FriendlyRegEx 
    Write-Host " Regular Expression =" $uefiOption.RegEx 
     
    Write-Host 
}
```

Définir ou modifier le mot de passe UEFI:

```
# Load the extension 
[System.Reflection.Assembly]::Load("SurfaceUefiManager, Version=1.0.5483.22783, Culture=neutral, PublicKeyToken=20606f4b5276c705")  
 
# Must supply UEFI administrator Password if set 
# If it is not currently set this is ignored 
[Microsoft.Surface.FirmwareOption]::Unlock("1234") 
 
$Password = [Microsoft.Surface.FirmwareOption]::Find("Password") 
 
# Set New value to 12345 
$Password.ProposedValue = "12345"
```

Vérifier l’état des modifications proposées:

```
# Load the extension 
[System.Reflection.Assembly]::Load("SurfaceUefiManager, Version=1.0.5483.22783, Culture=neutral, PublicKeyToken=20606f4b5276c705")  
 
# Check update status 
$updateStatus = [Microsoft.Surface.FirmwareOption]::UpdateStatus 
$updateIteration = [Microsoft.Surface.FirmwareOption]::UpdateIteration 
Write-Host "Last Update Status =" $updateStatus 
Write-Host "Last Update Iteration =" $updateIteration 
 
# Get the individual results for the last proposed update 
# If the device has never had an update attempt this will be an empty list 
$details = [Microsoft.Surface.FirmwareOption]::UpdateStatusDetails 
Write-Host $details.Count "Settings were proposed" 
if ($details.Count -gt 0) 
{ 
    Write-Host "Result Details" 
    foreach ($detail in $details.GetEnumerator()) 
    { 
        Write-Host " " $detail.Key "=" $detail.Value 
    } 
}
```

Rétablir les valeurs par défaut de l’UEFI:

```
# Load the extension 
[System.Reflection.Assembly]::Load("SurfaceUefiManager, Version=1.0.5483.22783, Culture=neutral, PublicKeyToken=20606f4b5276c705")  
 
# Must supply UEFI administrator Password if set 
# If it is not currently set this is ignored 
[Microsoft.Surface.FirmwareOption]::Unlock("1234") 
 
# Get the collection of all configurable settings 
$uefiOptions = [Microsoft.Surface.FirmwareOption]::All() 
 
# Reset all options to the factory default 
foreach ($uefiOption in $uefiOptions) 
{ 
    $uefiOption.ProposedValue = $uefiOption.DefaultValue 
}
```

Interprétation du code d’état

-   00 - La mise à jour proposée a réussi
-   02 - L’une des valeurs proposées contenait une valeur non valide
-   03 - Un ensemble de valeurs proposé n’a pas été reconnu
-   0F - Le mot de passe de déverrouillage ne correspond pas au mot de passe défini

 

 





