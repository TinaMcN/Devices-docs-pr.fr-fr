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
# <span data-ttu-id="63dfc-104">Fonctionnalités de sécuritéUEFI avancées pour SurfacePro3</span><span class="sxs-lookup"><span data-stu-id="63dfc-104">Advanced UEFI security features for Surface Pro 3</span></span>


<span data-ttu-id="63dfc-105">Cet article décrit comment installer et configurer la mise à jour v3.11.760.0 de l’UEFI pour activer les options de sécurité supplémentaires pour les appareils SurfacePro3.</span><span class="sxs-lookup"><span data-stu-id="63dfc-105">This article describes how to install and configure the v3.11.760.0 UEFI update to enable additional security options for Surface Pro 3 devices.</span></span>

<span data-ttu-id="63dfc-106">Pour avoir un contrôle plus précis de la sécurité des appareils Surface, la mise à jour v3.11.760.0 de l’UEFI fournit des options de sécurité supplémentaires qui vous permettent de désactiver des périphériques matériels spécifiques ou d’empêcher le démarrage à partir de ces derniers.</span><span class="sxs-lookup"><span data-stu-id="63dfc-106">To address more granular control over the security of Surface devices, the v3.11.760.0 UEFI update provides additional security options that allow you to disable specific hardware devices or to prevent starting from those devices.</span></span> <span data-ttu-id="63dfc-107">Une fois la mise à jour de l’UEFI installée sur un appareil, vous pouvez la configurer automatiquement ou manuellement en exécutant un script.</span><span class="sxs-lookup"><span data-stu-id="63dfc-107">After the UEFI update is installed on a device, you can configure it manually or automatically by running a script.</span></span>

## <span data-ttu-id="63dfc-108">Installation manuelle de la mise à jour de l’UEFI</span><span class="sxs-lookup"><span data-stu-id="63dfc-108">Manually install the UEFI update</span></span>


<span data-ttu-id="63dfc-109">Avant de pouvoir configurer les fonctionnalités de sécurité avancée de votre appareilSurface, vous devez tout d’abord installer la mise à jour v3.11.760.0 de l’UEFI.</span><span class="sxs-lookup"><span data-stu-id="63dfc-109">Before you can configure the advanced security features of your Surface device, you must first install the v3.11.760.0 UEFI update.</span></span> <span data-ttu-id="63dfc-110">Cette mise à jour s’installe automatiquement si vous recevez vos mises à jour à partir de WindowsUpdate.</span><span class="sxs-lookup"><span data-stu-id="63dfc-110">This update is installed automatically if you receive your updates from Windows Update.</span></span> <span data-ttu-id="63dfc-111">Pour en savoir plus sur la configuration de Windows pour recevoir des mises à jour automatiques à partir de WindowsUpdate, voir [Comment faire pour configurer et utiliser les mises à jour automatiques dans Windows](https://support.microsoft.com/kb/306525).</span><span class="sxs-lookup"><span data-stu-id="63dfc-111">For more information about how to configure Windows to update automatically by using Windows Update, see [How to configure and use Automatic Updates in Windows](https://support.microsoft.com/kb/306525).</span></span>

<span data-ttu-id="63dfc-112">Pour mettre à jour les fonctionnalitésUEFI sur SurfacePro3, vous pouvez télécharger et installer les mises à jour UEFISurface à partir du pack des microprogrammes et des pilotesSurfacePro3.</span><span class="sxs-lookup"><span data-stu-id="63dfc-112">To update the UEFI on Surface Pro 3, you can download and install the Surface UEFI updates as part of the Surface Pro 3 Firmware and Driver Pack.</span></span> <span data-ttu-id="63dfc-113">Ces packs du microprogramme et des pilotes sont disponibles sur la [page Surface Pro 3](https://www.microsoft.com/download/details.aspx?id=38826) du Centre de téléchargement Microsoft.</span><span class="sxs-lookup"><span data-stu-id="63dfc-113">These firmware and driver packs are available from the [Surface Pro 3 page](https://www.microsoft.com/download/details.aspx?id=38826) on the Microsoft Download Center.</span></span> <span data-ttu-id="63dfc-114">Pour plus d’informations sur les packs du microprogramme et des pilotes, consultez la section [Télécharger le dernier microprogramme et les pilotes les plus récents pour les appareilsSurface](https://technet.microsoft.com/itpro/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices).</span><span class="sxs-lookup"><span data-stu-id="63dfc-114">You can find out more about the firmware and driver packs at [Download the latest firmware and drivers for Surface devices](https://technet.microsoft.com/itpro/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices).</span></span> <span data-ttu-id="63dfc-115">Les packs du microprogramme et des pilotes sont disponibles aux formats autonomes WindowsInstaller(.msi) et d’archive (.zip).</span><span class="sxs-lookup"><span data-stu-id="63dfc-115">The firmware and driver packs are available as both self-contained Windows Installer (.msi) and archive (.zip) formats.</span></span> <span data-ttu-id="63dfc-116">Pour plus d’informations sur ces deuxformats et sur la manière dont vous pouvez les utiliser pour mettre à jour vos pilotes, accédez à la section [Gérer les mises à jour du microprogramme et des pilotes Surface](https://technet.microsoft.com/itpro/surface/manage-surface-pro-3-firmware-updates).</span><span class="sxs-lookup"><span data-stu-id="63dfc-116">You can find out more about these two formats and how you can use them to update your drivers at [Manage Surface driver and firmware updates](https://technet.microsoft.com/itpro/surface/manage-surface-pro-3-firmware-updates).</span></span>

## <span data-ttu-id="63dfc-117">Configurer manuellement des paramètres de sécurité supplémentaires</span><span class="sxs-lookup"><span data-stu-id="63dfc-117">Manually configure additional security settings</span></span>


>[!NOTE]
><span data-ttu-id="63dfc-118">Pour régler les paramètres de microprogramme sur un appareil Surface, celui-ci doit d’abord être hors tension. Appuyez longuement sur le bouton **Augmenter le volume**, puis appuyez sur et relâchez le bouton **Marche/Arrêt**. Relâchez le bouton **Augmenter le volume** lorsque l’appareil démarre.</span><span class="sxs-lookup"><span data-stu-id="63dfc-118">To enter firmware setup on a Surface device, begin with the device powered off, press and hold the **Volume Up** button, then press and release the **Power** button, then release the **Volume Up** button after the device has begun to boot.</span></span>

<span data-ttu-id="63dfc-119">Une fois que la mise à jour v3.11.760.0 de l’UEFI est installée sur un appareil Surface, un menu UEFI supplémentaire nommé **Sécurité avancée de l’appareil** devient disponible.</span><span class="sxs-lookup"><span data-stu-id="63dfc-119">After the v3.11.760.0 UEFI update is installed on a Surface device, an additional UEFI menu named **Advanced Device Security** becomes available.</span></span> <span data-ttu-id="63dfc-120">Si vous cliquez sur ce menu, les options suivantes sont affichées:</span><span class="sxs-lookup"><span data-stu-id="63dfc-120">If you click this menu, the following options are displayed:</span></span>

| <span data-ttu-id="63dfc-121">Option</span><span class="sxs-lookup"><span data-stu-id="63dfc-121">Option</span></span>         | <span data-ttu-id="63dfc-122">Description</span><span class="sxs-lookup"><span data-stu-id="63dfc-122">Description</span></span>                                                                                                                                                                          | <span data-ttu-id="63dfc-123">Paramètres disponibles (les paramètres par défaut sont en gras)</span><span class="sxs-lookup"><span data-stu-id="63dfc-123">Available settings (default listed in bold)</span></span> |
|----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------|
| <span data-ttu-id="63dfc-124">Démarrage réseau</span><span class="sxs-lookup"><span data-stu-id="63dfc-124">Network Boot</span></span>   | <span data-ttu-id="63dfc-125">Active ou désactive la possibilité pour l’appareil Surface de démarrer à partir du réseau (également appelé démarrage PXE).</span><span class="sxs-lookup"><span data-stu-id="63dfc-125">Enables or disables the ability of your Surface device to boot from the network (also known as PXE boot).</span></span>                                                                            | <span data-ttu-id="63dfc-126">**Activé**, Non démarrable</span><span class="sxs-lookup"><span data-stu-id="63dfc-126">**Enabled**, Not Bootable</span></span>                   |
| <span data-ttu-id="63dfc-127">PortUSB latéral</span><span class="sxs-lookup"><span data-stu-id="63dfc-127">Side USB</span></span>       | <span data-ttu-id="63dfc-128">Active ou désactive le port USB sur le côté de l’appareil Surface.</span><span class="sxs-lookup"><span data-stu-id="63dfc-128">Enables or disables the USB port on the side of the Surface device.</span></span> <span data-ttu-id="63dfc-129">En outre, le port USB peut être activé, mais sans autoriser le démarrage.</span><span class="sxs-lookup"><span data-stu-id="63dfc-129">Additionally, the USB port can be enabled, but not allow booting.</span></span>                                                | <span data-ttu-id="63dfc-130">**Activé**, Non démarrable, Désactivé</span><span class="sxs-lookup"><span data-stu-id="63dfc-130">**Enabled**, Not Bootable, Disabled</span></span>         |
| <span data-ttu-id="63dfc-131">Port de station d’accueil</span><span class="sxs-lookup"><span data-stu-id="63dfc-131">Docking Port</span></span>   | <span data-ttu-id="63dfc-132">Active ou désactive les ports sur la station d’accueil de l’appareil Surface.</span><span class="sxs-lookup"><span data-stu-id="63dfc-132">Enables or disables the ports on the Surface docking station.</span></span> <span data-ttu-id="63dfc-133">En outre, le port de station d’accueil peut être activé, tout en étant capable de bloquer le démarrage à partir d’un port USB ou Ethernet quelconque dans la station d’accueil.</span><span class="sxs-lookup"><span data-stu-id="63dfc-133">Additionally, the docking port can be enabled, but block booting from any USB or Ethernet port in the docking station.</span></span> | <span data-ttu-id="63dfc-134">**Activé**, Non démarrable, Désactivé</span><span class="sxs-lookup"><span data-stu-id="63dfc-134">**Enabled**, Not Bootable, Disabled</span></span>         |
| <span data-ttu-id="63dfc-135">Caméra frontale</span><span class="sxs-lookup"><span data-stu-id="63dfc-135">Front Camera</span></span>   | <span data-ttu-id="63dfc-136">Active ou désactive la caméra frontale de l’appareil Surface.</span><span class="sxs-lookup"><span data-stu-id="63dfc-136">Enables or disables the camera on the front of the Surface device.</span></span>                                                                                                                   | <span data-ttu-id="63dfc-137">**Activé**, Désactivé</span><span class="sxs-lookup"><span data-stu-id="63dfc-137">**Enabled**, Disabled</span></span>                       |
| <span data-ttu-id="63dfc-138">Caméra arrière</span><span class="sxs-lookup"><span data-stu-id="63dfc-138">Rear Camera</span></span>    | <span data-ttu-id="63dfc-139">Active ou désactive la caméra arrière de l’appareil Surface.</span><span class="sxs-lookup"><span data-stu-id="63dfc-139">Enables or disables the camera on the rear of the Surface device.</span></span>                                                                                                                    | <span data-ttu-id="63dfc-140">**Activé**, Désactivé</span><span class="sxs-lookup"><span data-stu-id="63dfc-140">**Enabled**, Disabled</span></span>                       |
| <span data-ttu-id="63dfc-141">Audio intégré</span><span class="sxs-lookup"><span data-stu-id="63dfc-141">On Board Audio</span></span> | <span data-ttu-id="63dfc-142">Active ou désactive l’audio sur l’appareil Surface.</span><span class="sxs-lookup"><span data-stu-id="63dfc-142">Enables or disables audio on the Surface device.</span></span>                                                                                                                                     | <span data-ttu-id="63dfc-143">**Activé**, Désactivé</span><span class="sxs-lookup"><span data-stu-id="63dfc-143">**Enabled**, Disabled</span></span>                       |
| <span data-ttu-id="63dfc-144">microSD</span><span class="sxs-lookup"><span data-stu-id="63dfc-144">microSD</span></span>        | <span data-ttu-id="63dfc-145">Active ou désactive la fente microSD sur l’appareil Surface.</span><span class="sxs-lookup"><span data-stu-id="63dfc-145">Enables or disables the microSD slot on the Surface device.</span></span>                                                                                                                          | <span data-ttu-id="63dfc-146">**Activé**, Désactivé</span><span class="sxs-lookup"><span data-stu-id="63dfc-146">**Enabled**, Disabled</span></span>                       |
| <span data-ttu-id="63dfc-147">WiFi</span><span class="sxs-lookup"><span data-stu-id="63dfc-147">WiFi</span></span>           | <span data-ttu-id="63dfc-148">Active ou désactive le transmetteur Wi-Fi intégré à l’appareil Surface.</span><span class="sxs-lookup"><span data-stu-id="63dfc-148">Enables or disables the built-in Wi-Fi transceiver in the Surface device.</span></span> <span data-ttu-id="63dfc-149">Désactive également le Bluetooth.</span><span class="sxs-lookup"><span data-stu-id="63dfc-149">This also disables Bluetooth.</span></span>                                                                              | <span data-ttu-id="63dfc-150">**Activé**, Désactivé</span><span class="sxs-lookup"><span data-stu-id="63dfc-150">**Enabled**, Disabled</span></span>                       |
| <span data-ttu-id="63dfc-151">Bluetooth</span><span class="sxs-lookup"><span data-stu-id="63dfc-151">Bluetooth</span></span>      | <span data-ttu-id="63dfc-152">Active ou désactive le transmetteur Bluetooth intégré à l’appareil Surface.</span><span class="sxs-lookup"><span data-stu-id="63dfc-152">Enables or disables the built-in Bluetooth transceiver in the Surface device.</span></span>                                                                                                        | <span data-ttu-id="63dfc-153">**Activé**, Désactivé</span><span class="sxs-lookup"><span data-stu-id="63dfc-153">**Enabled**, Disabled</span></span>                       |

 

## <span data-ttu-id="63dfc-154">Automatiser les paramètres de sécurité supplémentaires</span><span class="sxs-lookup"><span data-stu-id="63dfc-154">Automate additional security settings</span></span>


<span data-ttu-id="63dfc-155">En tant que professionnel de l’informatique avec des privilèges d’administration, vous pouvez automatiser la configuration des paramètres UEFI en tirant parti des [Outils de microprogramme de SurfacePro3 (476Ko)](https://go.microsoft.com/fwlink/p/?LinkID=618038), disponibles dans le Centre de téléchargementMicrosoft.</span><span class="sxs-lookup"><span data-stu-id="63dfc-155">As an IT professional with administrative privileges, you can automate the configuration of UEFI settings by leveraging [Surface Pro 3 Firmware Tools (476 KB)](https://go.microsoft.com/fwlink/p/?LinkID=618038) available from the Microsoft Download Center.</span></span> <span data-ttu-id="63dfc-156">Ces outils installent un assembly .NET qui peut être appelé à partir d’applications ou de scripts personnalisés quelconques.</span><span class="sxs-lookup"><span data-stu-id="63dfc-156">These tools install a .NET assembly that can be called from any custom application or script.</span></span>

**<span data-ttu-id="63dfc-157">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="63dfc-157">Prerequisites</span></span>**

-   <span data-ttu-id="63dfc-158">Les exemples de script ci-dessous utilisent l’extension mentionnée précédemment et supposent donc que l’outil a été installé sur l’appareil géré.</span><span class="sxs-lookup"><span data-stu-id="63dfc-158">The sample scripts below leverage the previously mentioned extension and therefore assume that the tool has been installed on the device being managed.</span></span>
-   <span data-ttu-id="63dfc-159">Les scripts doivent être exécutés avec des privilèges d’administration.</span><span class="sxs-lookup"><span data-stu-id="63dfc-159">The scripts must be run with administrative privilege.</span></span>
-   <span data-ttu-id="63dfc-160">La commande WindowsPowerShell [**Set-ExecutionPolicy Unrestricted**](https://technet.microsoft.com/library/ee176961.aspx) doit être appelée avant l’exécution des exemples de script s’ils n’ont pas été signés numériquement.</span><span class="sxs-lookup"><span data-stu-id="63dfc-160">The Windows PowerShell command [**Set-ExecutionPolicy Unrestricted**](https://technet.microsoft.com/library/ee176961.aspx) must be called prior to running sample scripts if they are not digitally signed.</span></span>

**<span data-ttu-id="63dfc-161">Exemples de scripts</span><span class="sxs-lookup"><span data-stu-id="63dfc-161">Sample scripts</span></span>**

><span data-ttu-id="63dfc-162">**Remarque**:&nbsp;&nbsp;Le mot de passe UEFI utilisé dans les exemples de script ci-dessous est présenté en texte clair.</span><span class="sxs-lookup"><span data-stu-id="63dfc-162">**Note**:&nbsp;&nbsp;The UEFI password used in the sample scripts below is presented in clear text.</span></span> <span data-ttu-id="63dfc-163">Nous vous recommandons vivement d’enregistrer les scripts dans un emplacement protégé et de les exécuter dans un environnement contrôlé.</span><span class="sxs-lookup"><span data-stu-id="63dfc-163">We strongly recommend saving the scripts in a protected location and running them in a controlled environment.</span></span>


<span data-ttu-id="63dfc-164">Afficher toutes les options configurables:</span><span class="sxs-lookup"><span data-stu-id="63dfc-164">Show all configurable options:</span></span>

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

<span data-ttu-id="63dfc-165">Définir ou modifier le mot de passe UEFI:</span><span class="sxs-lookup"><span data-stu-id="63dfc-165">Set or change UEFI password:</span></span>

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

<span data-ttu-id="63dfc-166">Vérifier l’état des modifications proposées:</span><span class="sxs-lookup"><span data-stu-id="63dfc-166">Check status of proposed changes:</span></span>

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

<span data-ttu-id="63dfc-167">Rétablir les valeurs par défaut de l’UEFI:</span><span class="sxs-lookup"><span data-stu-id="63dfc-167">Revert UEFI to default values:</span></span>

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

<span data-ttu-id="63dfc-168">Interprétation du code d’état</span><span class="sxs-lookup"><span data-stu-id="63dfc-168">Status code interpretation</span></span>

-   <span data-ttu-id="63dfc-169">00 - La mise à jour proposée a réussi</span><span class="sxs-lookup"><span data-stu-id="63dfc-169">00 - The proposed update was a success</span></span>
-   <span data-ttu-id="63dfc-170">02 - L’une des valeurs proposées contenait une valeur non valide</span><span class="sxs-lookup"><span data-stu-id="63dfc-170">02 - One of the proposed values had an invalid value</span></span>
-   <span data-ttu-id="63dfc-171">03 - Un ensemble de valeurs proposé n’a pas été reconnu</span><span class="sxs-lookup"><span data-stu-id="63dfc-171">03 - There was a proposed value set that was not recognized</span></span>
-   <span data-ttu-id="63dfc-172">0F - Le mot de passe de déverrouillage ne correspond pas au mot de passe défini</span><span class="sxs-lookup"><span data-stu-id="63dfc-172">0F - The unlock password did not match currently set password</span></span>

 

 





