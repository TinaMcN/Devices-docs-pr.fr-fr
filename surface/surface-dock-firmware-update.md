---
title: Mise à jour du microprogramme de Microsoft Surface Dock 1
description: Cet article explique comment utiliser la mise à jour du microprogramme de station d’accueil Microsoft Surface pour installer et gérer le microprogramme sur la station d’accueil Surface 1 d’origine. Lorsqu’il est installé sur votre appareil Surface, il met à jour les appareils de la station d’accueil Surface 1 attachés à votre appareil Surface.
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
ms.topic: article
ms.reviewer: scottmca
manager: laurawi
ms.audience: itpro
ms.date: 2/08/2021
ms.openlocfilehash: a0acaaf0676c3f4403a2b233297781579ca1f4ae
ms.sourcegitcommit: 7029e80d9ca1a3de5c336cf662e566ed4b6b3e7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/09/2021
ms.locfileid: "11319208"
---
# <span data-ttu-id="2257b-104">Mise à jour du microprogramme de station d’accueil Microsoft Surface</span><span class="sxs-lookup"><span data-stu-id="2257b-104">Microsoft Surface Dock Firmware Update</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2257b-105">Cet article contient des instructions techniques pour les administrateurs informatiques.</span><span class="sxs-lookup"><span data-stu-id="2257b-105">This article contains technical instructions for IT administrators.</span></span> <span data-ttu-id="2257b-106">Si vous êtes un utilisateur d’accueil, voir comment mettre à jour votre [microprogramme](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock)de station d’accueil Surface sur le site de   support Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2257b-106">If you are a home user, please see [How to update your Surface Dock Firmware](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock) on the Microsoft Support site.</span></span> <span data-ttu-id="2257b-107">Les instructions du site de support sont les mêmes que les étapes d’installation générale ci-dessous, mais cet article contient des informations supplémentaires sur la surveillance, la vérification et le déploiement de la mise à jour sur plusieurs appareils sur un réseau.</span><span class="sxs-lookup"><span data-stu-id="2257b-107">The instructions at the support site are the same as the general installation steps below, but this article has additional information for monitoring, verifying, and deploying the update to multiple devices on a network.</span></span>

<span data-ttu-id="2257b-108">Cet article explique comment utiliser la mise à jour du microprogramme de station d’accueil Microsoft Surface pour installer et gérer le microprogramme sur la station d’accueil Surface 1 d’origine.</span><span class="sxs-lookup"><span data-stu-id="2257b-108">This article explains how to use Microsoft Surface Dock Firmware Update to install and manage firmware on the original Surface Dock 1.</span></span> <span data-ttu-id="2257b-109">Lorsqu’il est installé sur votre appareil Surface, il met à jour les appareils de la station d’accueil Surface 1 attachés à votre appareil Surface.</span><span class="sxs-lookup"><span data-stu-id="2257b-109">When installed on your Surface device, it will update Surface Dock 1 devices attached to your Surface device.</span></span>

> [!NOTE]
> <span data-ttu-id="2257b-110">Cet article ne s’applique pas à la station d’accueil Surface 2, qui reçoit automatiquement les mises à jour via Windows Update ou à l’aide de Microsoft Endpoint Configuration Manager ou d’autres outils de déploiement MSI.</span><span class="sxs-lookup"><span data-stu-id="2257b-110">This article does not apply to Surface Dock 2, which receives updates automatically via Windows Update or by using Microsoft Endpoint Configuration Manager or other MSI deployment tools.</span></span> <span data-ttu-id="2257b-111">Pour plus d’informations, [voir Nouveautés de la station d’accueil Surface.](surface-dock-whats-new.md)</span><span class="sxs-lookup"><span data-stu-id="2257b-111">To learn more, see [What’s new in Surface Dock](surface-dock-whats-new.md).</span></span>

<span data-ttu-id="2257b-112">Cet outil a la place de l’outil Microsoft Surface Dock Updater précédent, précédemment disponible en téléchargement dans le cadre des outils Surface pour l’informatique.</span><span class="sxs-lookup"><span data-stu-id="2257b-112">This tool supersedes the earlier Microsoft Surface Dock Updater tool, previously available for download as part of Surface Tools for IT.</span></span> <span data-ttu-id="2257b-113">L’outil précédent, nommé Surface_Dock_Updater_vx.xx.xxx.x.msi (où x indique le numéro de version), n’est plus disponible en téléchargement et ne doit pas être utilisé.</span><span class="sxs-lookup"><span data-stu-id="2257b-113">The earlier tool was named Surface_Dock_Updater_vx.xx.xxx.x.msi (where x indicates the version number) and is no longer available for download and should not be used.</span></span>

## <span data-ttu-id="2257b-114">Installer la mise à jour du microprogramme de station d’accueil Surface</span><span class="sxs-lookup"><span data-stu-id="2257b-114">Install the Surface Dock Firmware Update</span></span>

<span data-ttu-id="2257b-115">Cette section décrit comment installer manuellement la mise à jour du microprogramme.</span><span class="sxs-lookup"><span data-stu-id="2257b-115">This section describes how to manually install the firmware update.</span></span>

> [!NOTE]
> <span data-ttu-id="2257b-116">Microsoft publie régulièrement de nouvelles versions de la mise à jour du microprogramme de station d’accueil Surface.</span><span class="sxs-lookup"><span data-stu-id="2257b-116">Microsoft periodically releases new versions of Surface Dock Firmware Update.</span></span> <span data-ttu-id="2257b-117">Le fichier MSI n’est pas auto-mis à jour.</span><span class="sxs-lookup"><span data-stu-id="2257b-117">The MSI file is not self-updating.</span></span> <span data-ttu-id="2257b-118">Si vous avez déployé le MSI sur les appareils Surface et qu’une nouvelle version du microprogramme est publiée, vous devez déployer la nouvelle version.</span><span class="sxs-lookup"><span data-stu-id="2257b-118">If you have deployed the MSI to Surface devices and a new version of the firmware is released, you will need to deploy the new version.</span></span>

1. <span data-ttu-id="2257b-119">Téléchargez et installez [la mise à jour du microprogramme de la station d’accueil Microsoft Surface.](https://www.microsoft.com/download/details.aspx?id=46703)</span><span class="sxs-lookup"><span data-stu-id="2257b-119">Download and install [Microsoft Surface Dock Firmware Update](https://www.microsoft.com/download/details.aspx?id=46703).</span></span>
    - <span data-ttu-id="2257b-120">La mise à jour nécessite un appareil Surface exécutant Windows 10, version 1803 ou ultérieure.</span><span class="sxs-lookup"><span data-stu-id="2257b-120">The update requires a Surface device running Windows 10, version 1803 or later.</span></span>
    - <span data-ttu-id="2257b-121">L’installation du fichier MSI peut vous demander de redémarrer Surface.</span><span class="sxs-lookup"><span data-stu-id="2257b-121">Installing the MSI file might prompt you to restart Surface.</span></span> <span data-ttu-id="2257b-122">Toutefois, le redémarrage n’est pas nécessaire pour effectuer la mise à jour.</span><span class="sxs-lookup"><span data-stu-id="2257b-122">However, restarting is not required to perform the update.</span></span>

2. <span data-ttu-id="2257b-123">Déconnectez votre appareil Surface de la station d’accueil Surface, patientez environ 5 secondes, puis reconnectez-vous.</span><span class="sxs-lookup"><span data-stu-id="2257b-123">Disconnect your Surface device from the Surface Dock, wait ~5 seconds, and then reconnect.</span></span> <span data-ttu-id="2257b-124">La mise à jour du microprogramme de station d’accueil Surface met à jour la station d’accueil en mode silencieux en arrière-plan.</span><span class="sxs-lookup"><span data-stu-id="2257b-124">The Surface Dock Firmware Update will update the dock silently in background.</span></span> <span data-ttu-id="2257b-125">Le processus peut prendre quelques minutes et se poursuivre même s’il est interrompu.</span><span class="sxs-lookup"><span data-stu-id="2257b-125">The process can take a few minutes to complete and will continue even if interrupted.</span></span> 

## <span data-ttu-id="2257b-126">Surveiller la mise à jour du microprogramme de station d’accueil Surface</span><span class="sxs-lookup"><span data-stu-id="2257b-126">Monitor the Surface Dock Firmware Update</span></span>

<span data-ttu-id="2257b-127">Cette section est facultative et fournit une vue d’ensemble de la surveillance de l’installation de la mise à jour du microprogramme.</span><span class="sxs-lookup"><span data-stu-id="2257b-127">This section is optional and provides an overview of how to monitor installation of the firmware update.</span></span> 

<span data-ttu-id="2257b-128">Pour surveiller la mise à jour :</span><span class="sxs-lookup"><span data-stu-id="2257b-128">To monitor the update:</span></span>

1. <span data-ttu-id="2257b-129">Ouvrez l’Observateur d’événements, accédez à **Windows Logs > Application,** puis sous **Actions** dans le volet droit, cliquez sur Filtrer le journal **actuel,** entrez **SurfaceDockFwUpdate** en regard des **sources**d’événements, puis cliquez sur **OK.**</span><span class="sxs-lookup"><span data-stu-id="2257b-129">Open Event Viewer, browse to **Windows Logs > Application**, and then under **Actions** in the right-hand pane click **Filter Current Log**, enter **SurfaceDockFwUpdate** next to **Event sources**, and then click **OK**.</span></span>

2. <span data-ttu-id="2257b-130">Tapez la commande suivante à une invite de commandes avec élévation de élévation de niveaux :</span><span class="sxs-lookup"><span data-stu-id="2257b-130">Type the following command at an elevated command prompt:</span></span>

    ```console
    Reg query "HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\WUDF\Services\SurfaceDockFwUpdate\Parameters"
    ```
3. <span data-ttu-id="2257b-131">Installez la mise à jour comme décrit dans [la section suivante](#install-the-surface-dock-firmware-update) de cet article.</span><span class="sxs-lookup"><span data-stu-id="2257b-131">Install the update as described in the [next section](#install-the-surface-dock-firmware-update) of this article.</span></span>

4. <span data-ttu-id="2257b-132">L’événement 2007 avec le texte suivant indique une mise à jour réussie : Mise à jour du microprogramme **terminée. hr=0 DriverTelementry EventCode = 2007**.</span><span class="sxs-lookup"><span data-stu-id="2257b-132">Event 2007 with the following text indicates a successful update: **Firmware update finished. hr=0 DriverTelementry EventCode = 2007**.</span></span> 

   <span data-ttu-id="2257b-133">Si la mise à jour n’est pas réussie, l’ID d’événement 2007 s’affichera en tant qu’événement **d’erreur** au lieu **d’informations.**</span><span class="sxs-lookup"><span data-stu-id="2257b-133">If the update is not successful, then event ID 2007 will be displayed as an **Error** event rather than **Information**.</span></span> <span data-ttu-id="2257b-134">En outre, la version signalée dans le Registre Windows n’est pas à jour.</span><span class="sxs-lookup"><span data-stu-id="2257b-134">Additionally, the version reported in the Windows Registry will not be current.</span></span>
   
5. <span data-ttu-id="2257b-135">Une fois la mise à jour terminée, les valeurs DWORD mises à jour s’affichent dans le Registre Windows, correspondant à la version actuelle de l’outil.</span><span class="sxs-lookup"><span data-stu-id="2257b-135">When the update is complete, updated DWORD values will be displayed in the Windows Registry, corresponding to the current version of the tool.</span></span> <span data-ttu-id="2257b-136">Pour plus [d’informations, voir](#versions-reference) la section de référence versions de cet article.</span><span class="sxs-lookup"><span data-stu-id="2257b-136">See the [Versions reference](#versions-reference) section in this article for details.</span></span> <span data-ttu-id="2257b-137">Par exemple:</span><span class="sxs-lookup"><span data-stu-id="2257b-137">For example:</span></span>

    - <span data-ttu-id="2257b-138">Component10CurrentFwVersion 0x04ac3970 (78395760)</span><span class="sxs-lookup"><span data-stu-id="2257b-138">Component10CurrentFwVersion 0x04ac3970 (78395760)</span></span>
    - <span data-ttu-id="2257b-139">Component20CurrentFwVersion 0x04915a70 (76634736)</span><span class="sxs-lookup"><span data-stu-id="2257b-139">Component20CurrentFwVersion 0x04915a70 (76634736)</span></span>

>[!TIP]
><span data-ttu-id="2257b-140">Si vous voyez « Impossible de trouver la description de l’ID d’événement xxxx de la source SurfaceDockFwUpdate » dans le texte de l’événement, cette description est attendue et peut être ignorée.</span><span class="sxs-lookup"><span data-stu-id="2257b-140">If you see "The description for Event ID xxxx from source SurfaceDockFwUpdate cannot be found" in event text, this is expected and can be ignored.</span></span>

<span data-ttu-id="2257b-141">Consultez également les sections suivantes de cet article :</span><span class="sxs-lookup"><span data-stu-id="2257b-141">Also see the following sections in this article:</span></span> 
  - [<span data-ttu-id="2257b-142">Comment vérifier la fin de la mise à jour du microprogramme</span><span class="sxs-lookup"><span data-stu-id="2257b-142">How to verify completion of firmware update</span></span>](#how-to-verify-completion-of-the-firmware-update)
  - [<span data-ttu-id="2257b-143">Journalisation des événements</span><span class="sxs-lookup"><span data-stu-id="2257b-143">Event logging</span></span>](#event-logging)
  - [<span data-ttu-id="2257b-144">Conseils pour la résolution des problèmes</span><span class="sxs-lookup"><span data-stu-id="2257b-144">Troubleshooting tips</span></span>](#troubleshooting-tips)
  - [<span data-ttu-id="2257b-145">Référence des versions</span><span class="sxs-lookup"><span data-stu-id="2257b-145">Versions reference</span></span>](#versions-reference)

## <span data-ttu-id="2257b-146">Déploiement réseau</span><span class="sxs-lookup"><span data-stu-id="2257b-146">Network deployment</span></span>

<span data-ttu-id="2257b-147">Vous pouvez utiliser les commandes Windows Installer (Msiexec.exe) pour déployer la mise à jour du microprogramme de station d’accueil Surface sur plusieurs appareils sur votre réseau.</span><span class="sxs-lookup"><span data-stu-id="2257b-147">You can use Windows Installer commands (Msiexec.exe) to deploy Surface Dock Firmware Update to multiple devices across your network.</span></span> <span data-ttu-id="2257b-148">Lorsque vous utilisez Microsoft Endpoint Configuration Manager ou un autre outil de déploiement, entrez la syntaxe suivante pour vous assurer que l’installation est silencieuse :</span><span class="sxs-lookup"><span data-stu-id="2257b-148">When using Microsoft Endpoint Configuration Manager or other deployment tool, enter the following syntax to ensure the installation is silent:</span></span>

- **<span data-ttu-id="2257b-149">Msiexec.exe /i \<path to msi file\> /quiet /norestart</span><span class="sxs-lookup"><span data-stu-id="2257b-149">Msiexec.exe /i \<path to msi file\> /quiet /norestart</span></span>** 

<span data-ttu-id="2257b-150">Par exemple:</span><span class="sxs-lookup"><span data-stu-id="2257b-150">For example:</span></span>

```console
msiexec /i "\\share\folder\Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.msi" /quiet /norestart
```

> [!NOTE]
> <span data-ttu-id="2257b-151">Un fichier journal n’est pas créé par défaut.</span><span class="sxs-lookup"><span data-stu-id="2257b-151">A log file is not created by default.</span></span> <span data-ttu-id="2257b-152">Pour créer un fichier journal, vous devez l’ajoutez « /l*v [chemin d’accès] ». Par exemple : Msiexec.exe /i \<path to msi file\> /l*v %windir%\logs\ SurfaceDockFWI.log »</span><span class="sxs-lookup"><span data-stu-id="2257b-152">In order to create a log file, you will need to append "/l*v [path]". For example: Msiexec.exe /i \<path to msi file\> /l*v %windir%\logs\ SurfaceDockFWI.log"</span></span>

<span data-ttu-id="2257b-153">Pour plus d’informations, reportez-vous à la documentation [des options de ligne de](https://docs.microsoft.com/windows/win32/msi/command-line-options) commande.</span><span class="sxs-lookup"><span data-stu-id="2257b-153">For more information, refer to [Command line options](https://docs.microsoft.com/windows/win32/msi/command-line-options) documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2257b-154">Si vous souhaitez maintenir la mise à jour de votre station d’accueil Surface à l’aide d’une autre méthode, reportez-vous à Mettre à jour votre station d’accueil [Surface](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock) pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="2257b-154">If you want to keep your Surface Dock updated using any other method, refer to [Update your Surface Dock](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock) for details.</span></span>

## <span data-ttu-id="2257b-155">Déploiement d’Intune</span><span class="sxs-lookup"><span data-stu-id="2257b-155">Intune deployment</span></span>

<span data-ttu-id="2257b-156">Vous pouvez utiliser Intune pour distribuer la mise à jour du microprogramme de station d’accueil Surface à vos appareils.</span><span class="sxs-lookup"><span data-stu-id="2257b-156">You can use Intune to distribute Surface Dock Firmware Update to your devices.</span></span> <span data-ttu-id="2257b-157">Vous devez d’abord convertir le fichier MSI au format .intunewin, comme décrit dans la documentation suivante : Intune Autonome - Gestion des applications [Win32.](https://docs.microsoft.com/intune/apps/apps-win32-app-management)</span><span class="sxs-lookup"><span data-stu-id="2257b-157">First you will need to convert the MSI file to the .intunewin format, as described in the following documentation: [Intune Standalone - Win32 app management](https://docs.microsoft.com/intune/apps/apps-win32-app-management).</span></span>

<span data-ttu-id="2257b-158">Utilisez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="2257b-158">Use the following command:</span></span>
  - **<span data-ttu-id="2257b-159">msiexec /i \<path to msi file\> /quiet /q</span><span class="sxs-lookup"><span data-stu-id="2257b-159">msiexec /i \<path to msi file\> /quiet /q</span></span>**

## <span data-ttu-id="2257b-160">Comment vérifier la fin de la mise à jour du microprogramme</span><span class="sxs-lookup"><span data-stu-id="2257b-160">How to verify completion of the firmware update</span></span>

<span data-ttu-id="2257b-161">Le microprogramme de station d’accueil Surface se compose de deux composants :</span><span class="sxs-lookup"><span data-stu-id="2257b-161">Surface dock firmware consists of two components:</span></span>

- <span data-ttu-id="2257b-162">**Component10 :** Microprogramme de l’unité de micro-contrôleur (MCU)</span><span class="sxs-lookup"><span data-stu-id="2257b-162">**Component10:** Micro controller unit (MCU) firmware</span></span>
- <span data-ttu-id="2257b-163">**Component20 :** Microprogramme de port d’affichage (DP).</span><span class="sxs-lookup"><span data-stu-id="2257b-163">**Component20:** Display port (DP) firmware.</span></span>

<span data-ttu-id="2257b-164">L’exécution réussie de la mise à jour du microprogramme de station d’accueil Surface a abouti à de nouvelles valeurs de clé de Registre pour ces composants de microprogramme.</span><span class="sxs-lookup"><span data-stu-id="2257b-164">Successful completion of Surface Dock Firmware Update results in new registry key values for these firmware components.</span></span>

**<span data-ttu-id="2257b-165">Pour vérifier les mises à jour :</span><span class="sxs-lookup"><span data-stu-id="2257b-165">To verify updates:</span></span>**

1. <span data-ttu-id="2257b-166">Ouvrez Regedit et accédez au chemin de Registre suivant :</span><span class="sxs-lookup"><span data-stu-id="2257b-166">Open Regedit and navigate to the following registry path:</span></span>

    - **<span data-ttu-id="2257b-167">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\WUDF\Services\SurfaceDockFwUpdate\Parameters</span><span class="sxs-lookup"><span data-stu-id="2257b-167">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\WUDF\Services\SurfaceDockFwUpdate\Parameters</span></span>**

2. <span data-ttu-id="2257b-168">Recherchez les clés de Registre **: Component10CurrentFwVersion et Component20CurrentFwVersion**, qui font référence au microprogramme actuellement présent sur l’appareil.</span><span class="sxs-lookup"><span data-stu-id="2257b-168">Look for the registry keys: **Component10CurrentFwVersion and Component20CurrentFwVersion**, which refer to the firmware that is currently on the device.</span></span>

   ![Processus d’installation de la mise à jour du microprogramme de station d’accueil Surface](images/regeditDock.png)

3. <span data-ttu-id="2257b-170">Vérifiez que les nouvelles valeurs de clé de Registre correspondent aux valeurs de clé de Registre mises à jour répertoriées dans la référence versions à la fin de ce document.</span><span class="sxs-lookup"><span data-stu-id="2257b-170">Verify the new registry key values match the updated registry key values listed in the Versions reference at the end of this document.</span></span> <span data-ttu-id="2257b-171">Si les valeurs correspondent, le microprogramme a été mis à jour avec succès.</span><span class="sxs-lookup"><span data-stu-id="2257b-171">If the values match, the firmware was updated successfully.</span></span>

4. <span data-ttu-id="2257b-172">Si vous ne parvenez pas à le vérifier, examinez les conseils de journalisation et de dépannage des événements dans la section suivante.</span><span class="sxs-lookup"><span data-stu-id="2257b-172">If unable to verify, review Event logging and Troubleshooting tips in the next section.</span></span>

## <span data-ttu-id="2257b-173">Journalisation des événements</span><span class="sxs-lookup"><span data-stu-id="2257b-173">Event logging</span></span>

**<span data-ttu-id="2257b-174">Tableau1.</span><span class="sxs-lookup"><span data-stu-id="2257b-174">Table 1.</span></span> <span data-ttu-id="2257b-175">Fichiers journaux pour la mise à jour du microprogramme de station d’accueil Surface</span><span class="sxs-lookup"><span data-stu-id="2257b-175">Log files for Surface Dock Firmware Update</span></span>**

| <span data-ttu-id="2257b-176">Journal</span><span class="sxs-lookup"><span data-stu-id="2257b-176">Log</span></span>                              | <span data-ttu-id="2257b-177">Emplacement</span><span class="sxs-lookup"><span data-stu-id="2257b-177">Location</span></span>                               | <span data-ttu-id="2257b-178">Remarques</span><span class="sxs-lookup"><span data-stu-id="2257b-178">Notes</span></span>                                                                                                                                                                                                         |
| -------------------------------- | --------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="2257b-179">Journal de mise à jour du microprogramme de station d’accueil Surface</span><span class="sxs-lookup"><span data-stu-id="2257b-179">Surface Dock Firmware Update log</span></span> | <span data-ttu-id="2257b-180">Le chemin d’accès doit être spécifié (voir la remarque)</span><span class="sxs-lookup"><span data-stu-id="2257b-180">Path needs to be specified (see note)</span></span> | <span data-ttu-id="2257b-181">Les versions antérieures de cet outil ont écrit des événements dans Journaux des applications et des services\Microsoft Surface Dock Updater.</span><span class="sxs-lookup"><span data-stu-id="2257b-181">Earlier versions of this tool wrote events to Applications and Services Logs\Microsoft Surface Dock Updater.</span></span>                                                                                                  |
| <span data-ttu-id="2257b-182">Journal d’installation de l’appareil Windows</span><span class="sxs-lookup"><span data-stu-id="2257b-182">Windows Device Install log</span></span>       | <span data-ttu-id="2257b-183">%windir%\inf\setupapi.dev.log</span><span class="sxs-lookup"><span data-stu-id="2257b-183">%windir%\inf\setupapi.dev.log</span></span>           | <span data-ttu-id="2257b-184">Pour plus d’informations sur l’utilisation du journal d’installation des appareils, consultez la documentation [de journalisation SetupAPI.](https://docs.microsoft.com/windows-hardware/drivers/install/setupapi-logging--windows-vista-and-later-)</span><span class="sxs-lookup"><span data-stu-id="2257b-184">For more information about using Device Install Log, refer to [SetupAPI Logging](https://docs.microsoft.com/windows-hardware/drivers/install/setupapi-logging--windows-vista-and-later-) documentation.</span></span> |


**<span data-ttu-id="2257b-185">Tableau2.</span><span class="sxs-lookup"><span data-stu-id="2257b-185">Table 2.</span></span> <span data-ttu-id="2257b-186">ID du journal des événements pour la mise à jour du microprogramme de station d’accueil Surface</span><span class="sxs-lookup"><span data-stu-id="2257b-186">Event log IDs for Surface Dock Firmware Update</span></span>**<br>
<span data-ttu-id="2257b-187">Les événements sont consignés dans le journal des événements de l’application.</span><span class="sxs-lookup"><span data-stu-id="2257b-187">Events are logged in the Application Event Log.</span></span>  <span data-ttu-id="2257b-188">Remarque : les versions antérieures de cet outil ont écrit des événements dans Journaux des applications et des services\Microsoft Surface Dock Updater.</span><span class="sxs-lookup"><span data-stu-id="2257b-188">Note:  Earlier versions of this tool wrote events to Applications and Services Logs\Microsoft Surface Dock Updater.</span></span>

| <span data-ttu-id="2257b-189">ID d’événement</span><span class="sxs-lookup"><span data-stu-id="2257b-189">Event ID</span></span> | <span data-ttu-id="2257b-190">Type d’événement</span><span class="sxs-lookup"><span data-stu-id="2257b-190">Event type</span></span>                                                           |
| -------- | -------------------------------------------------------------------- |
| <span data-ttu-id="2257b-191">2001</span><span class="sxs-lookup"><span data-stu-id="2257b-191">2001</span></span>     | <span data-ttu-id="2257b-192">La mise à jour du microprogramme de la station d’accueil a démarré.</span><span class="sxs-lookup"><span data-stu-id="2257b-192">Dock firmware update has started.</span></span>                                    |
| <span data-ttu-id="2257b-193">2002</span><span class="sxs-lookup"><span data-stu-id="2257b-193">2002</span></span>     | <span data-ttu-id="2257b-194">La mise à jour du microprogramme de la station d’accueil a été ignorée, car la station d’accueil est connue pour être à jour.</span><span class="sxs-lookup"><span data-stu-id="2257b-194">Dock firmware update skipped because dock is known to be up to date.</span></span> |
| <span data-ttu-id="2257b-195">2003</span><span class="sxs-lookup"><span data-stu-id="2257b-195">2003</span></span>     | <span data-ttu-id="2257b-196">Échec de la mise à jour du microprogramme de la station d’accueil pour obtenir la version du microprogramme.</span><span class="sxs-lookup"><span data-stu-id="2257b-196">Dock firmware update failed to get firmware version.</span></span>                 |
| <span data-ttu-id="2257b-197">2004</span><span class="sxs-lookup"><span data-stu-id="2257b-197">2004</span></span>     | <span data-ttu-id="2257b-198">Interrogation de la version du microprogramme.</span><span class="sxs-lookup"><span data-stu-id="2257b-198">Querying the firmware version.</span></span>                                       |
| <span data-ttu-id="2257b-199">2005</span><span class="sxs-lookup"><span data-stu-id="2257b-199">2005</span></span>     | <span data-ttu-id="2257b-200">Le microprogramme de station d’accueil n’a pas réussi à démarrer la mise à jour.</span><span class="sxs-lookup"><span data-stu-id="2257b-200">Dock firmware failed to start update.</span></span>                                |
| <span data-ttu-id="2257b-201">2006</span><span class="sxs-lookup"><span data-stu-id="2257b-201">2006</span></span>     | <span data-ttu-id="2257b-202">Échec de l’envoi des paires offre/charge utile.</span><span class="sxs-lookup"><span data-stu-id="2257b-202">Failed to send offer/payload pairs.</span></span>                                  |
| <span data-ttu-id="2257b-203">2007</span><span class="sxs-lookup"><span data-stu-id="2257b-203">2007</span></span>     | <span data-ttu-id="2257b-204">Mise à jour du microprogramme terminée.</span><span class="sxs-lookup"><span data-stu-id="2257b-204">Firmware update finished.</span></span>                                            |
| <span data-ttu-id="2257b-205">2008</span><span class="sxs-lookup"><span data-stu-id="2257b-205">2008</span></span>     | <span data-ttu-id="2257b-206">BEGIN dock telemetry.</span><span class="sxs-lookup"><span data-stu-id="2257b-206">BEGIN dock telemetry.</span></span>                                                |
| <span data-ttu-id="2257b-207">2011</span><span class="sxs-lookup"><span data-stu-id="2257b-207">2011</span></span>     | <span data-ttu-id="2257b-208">Télémétrie end dock.</span><span class="sxs-lookup"><span data-stu-id="2257b-208">END dock telemetry.</span></span>                                                  |

## <span data-ttu-id="2257b-209">Conseils pour la résolution des problèmes</span><span class="sxs-lookup"><span data-stu-id="2257b-209">Troubleshooting tips</span></span>

- <span data-ttu-id="2257b-210">Déconnectez complètement la station d’accueil Surface de l’alimentation ac pour réinitialiser la station d’accueil Surface.</span><span class="sxs-lookup"><span data-stu-id="2257b-210">Completely disconnect power for Surface dock from the AC power to reset the Surface Dock.</span></span>
- <span data-ttu-id="2257b-211">Déconnectez tous les périphériques à l’exception de la station d’accueil Surface.</span><span class="sxs-lookup"><span data-stu-id="2257b-211">Disconnect all peripherals except for the Surface Dock.</span></span>
- <span data-ttu-id="2257b-212">Désinstallez toute mise à jour du microprogramme de station d’accueil Surface actuelle, puis installez la dernière version.</span><span class="sxs-lookup"><span data-stu-id="2257b-212">Uninstall any current Surface Dock Firmware Update and then install the latest version.</span></span>
- <span data-ttu-id="2257b-213">Assurez-vous que la station d’accueil Surface est déconnectée, puis laissez suffisamment de temps pour que la mise à jour se termine comme surveillé via un LED dans le port Ethernet de la station d’accueil.</span><span class="sxs-lookup"><span data-stu-id="2257b-213">Ensure that the Surface Dock is disconnected, and then allow enough time for the update to complete as monitored via an LED in the Ethernet port of the dock.</span></span> <span data-ttu-id="2257b-214">Patientez jusqu’à ce que le voyant cesse de clignoter avant de débrancher la station d’accueil Surface de l’alimentation.</span><span class="sxs-lookup"><span data-stu-id="2257b-214">Wait until the LED stops blinking before you unplug Surface Dock from power.</span></span>
- <span data-ttu-id="2257b-215">Connectez la station d’accueil Surface à un autre appareil pour voir s’il est en mesure de mettre à jour la station d’accueil.</span><span class="sxs-lookup"><span data-stu-id="2257b-215">Connect the Surface Dock to a different device to see if it is able to update the dock.</span></span>

## <span data-ttu-id="2257b-216">Référence des versions</span><span class="sxs-lookup"><span data-stu-id="2257b-216">Versions reference</span></span>

>[!NOTE]
><span data-ttu-id="2257b-217">Le fichier d’installation est publié avec le format d’attribution de noms suivant : **Surface_Dock_FwUpdate_X.XX.XXX_Win10_XXXXX_XX.XXX.XXXXX_X.MSI** (ex: Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.msi) et s’installe par défaut sur C:\Program Files\SurfaceUpdate.</span><span class="sxs-lookup"><span data-stu-id="2257b-217">The installation file is released with the following naming format: **Surface_Dock_FwUpdate_X.XX.XXX_Win10_XXXXX_XX.XXX.XXXXX_X.MSI** (ex: Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.msi) and installs by default to C:\Program Files\SurfaceUpdate.</span></span>

### <span data-ttu-id="2257b-218">Version 1.53.139.0</span><span class="sxs-lookup"><span data-stu-id="2257b-218">Version 1.53.139.0</span></span>
*<span data-ttu-id="2257b-219">Date de publication : 4 août 2020</span><span class="sxs-lookup"><span data-stu-id="2257b-219">Release Date: August 4, 2020</span></span>*

<span data-ttu-id="2257b-220">Cette version de la mise à jour du microprogramme de station d’accueil Surface inclut des correctifs de bogue et la prise en charge des :</span><span class="sxs-lookup"><span data-stu-id="2257b-220">This version of Surface Dock Firmware Update includes bug fixes and support for:</span></span>
- <span data-ttu-id="2257b-221">Mise à jour de la station d’accueil Surface 1 à l’aide de Surface Pro X.</span><span class="sxs-lookup"><span data-stu-id="2257b-221">Updating Surface Dock 1 using Surface Pro X.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="2257b-222">Si vous exécutez Surface Pro X, téléchargez le . Build ARM64.</span><span class="sxs-lookup"><span data-stu-id="2257b-222">If you're running Surface Pro X, download the .ARM64 build.</span></span> <span data-ttu-id="2257b-223">Pour tous les autres appareils, utilisez la build AMD64.</span><span class="sxs-lookup"><span data-stu-id="2257b-223">For all other devices, use the AMD64 build.</span></span> 

#### <span data-ttu-id="2257b-224">Valeurs des clés de Registre</span><span class="sxs-lookup"><span data-stu-id="2257b-224">Registry key values</span></span>

<span data-ttu-id="2257b-225">Les valeurs de Registre qui indiquent l’état des mises à jour du microprogramme restent inchangées par rapport à la version précédente de cet outil :</span><span class="sxs-lookup"><span data-stu-id="2257b-225">The registry values that indicate the status of firmware updates are unchanged from the previous version of this tool:</span></span> 

- <span data-ttu-id="2257b-226">Component10CurrentFwVersion mis à jour vers **4ac3970**.</span><span class="sxs-lookup"><span data-stu-id="2257b-226">Component10CurrentFwVersion updated to **4ac3970**.</span></span>
- <span data-ttu-id="2257b-227">Component20CurrentFwVersion mis à jour vers **4a1d570**.</span><span class="sxs-lookup"><span data-stu-id="2257b-227">Component20CurrentFwVersion updated to **4a1d570**.</span></span>
 
### <span data-ttu-id="2257b-228">Version 1.42.139</span><span class="sxs-lookup"><span data-stu-id="2257b-228">Version 1.42.139</span></span> 
*<span data-ttu-id="2257b-229">Date de publication : 18 septembre 2019</span><span class="sxs-lookup"><span data-stu-id="2257b-229">Release Date: September 18 2019</span></span>*

<span data-ttu-id="2257b-230">Cette version, contenue dans Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.MSI, met à jour le microprogramme en arrière-plan.</span><span class="sxs-lookup"><span data-stu-id="2257b-230">This version, contained in Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.MSI, updates firmware in the background.</span></span> 

#### <span data-ttu-id="2257b-231">Valeurs de clé de Registre mises à jour</span><span class="sxs-lookup"><span data-stu-id="2257b-231">Updated registry key values</span></span>

- <span data-ttu-id="2257b-232">Component10CurrentFwVersion mis à jour vers **4ac3970**.</span><span class="sxs-lookup"><span data-stu-id="2257b-232">Component10CurrentFwVersion updated to **4ac3970**.</span></span>
- <span data-ttu-id="2257b-233">Component20CurrentFwVersion mis à jour vers **4a1d570**.</span><span class="sxs-lookup"><span data-stu-id="2257b-233">Component20CurrentFwVersion updated to **4a1d570**.</span></span>

<span data-ttu-id="2257b-234">Il ajoute la prise en charge de Surface Pro 7 et surface laptop 3.</span><span class="sxs-lookup"><span data-stu-id="2257b-234">It adds support for Surface Pro 7 and Surface Laptop 3.</span></span>

## <span data-ttu-id="2257b-235">Versions héritées</span><span class="sxs-lookup"><span data-stu-id="2257b-235">Legacy versions</span></span>

### <span data-ttu-id="2257b-236">Version 2.23.139.0</span><span class="sxs-lookup"><span data-stu-id="2257b-236">Version 2.23.139.0</span></span>
*<span data-ttu-id="2257b-237">Date de publication : 10 octobre 2018</span><span class="sxs-lookup"><span data-stu-id="2257b-237">Release Date: 10 October 2018</span></span>*

<span data-ttu-id="2257b-238">Cette version de Surface Dock Updater ajoute une prise en charge des éléments suivants:</span><span class="sxs-lookup"><span data-stu-id="2257b-238">This version of Surface Dock Updater adds support for the following:</span></span>

- <span data-ttu-id="2257b-239">Ajouter la prise en charge de Surface Pro 6</span><span class="sxs-lookup"><span data-stu-id="2257b-239">Add support for Surface Pro 6</span></span>
- <span data-ttu-id="2257b-240">Ajouter la prise en charge de Surface Laptop 2</span><span class="sxs-lookup"><span data-stu-id="2257b-240">Add support for Surface Laptop 2</span></span>


### <span data-ttu-id="2257b-241">Version 2.22.139.0</span><span class="sxs-lookup"><span data-stu-id="2257b-241">Version 2.22.139.0</span></span>
*<span data-ttu-id="2257b-242">Date de publication : 26 juillet 2018</span><span class="sxs-lookup"><span data-stu-id="2257b-242">Release Date: 26 July 2018</span></span>*

<span data-ttu-id="2257b-243">Cette version de Surface Dock Updater ajoute une prise en charge des éléments suivants:</span><span class="sxs-lookup"><span data-stu-id="2257b-243">This version of Surface Dock Updater adds support for the following:</span></span>

- <span data-ttu-id="2257b-244">Augmenter la fiabilité des mises à jour</span><span class="sxs-lookup"><span data-stu-id="2257b-244">Increase update reliability</span></span>
- <span data-ttu-id="2257b-245">Ajouter la prise en charge de Surface Go</span><span class="sxs-lookup"><span data-stu-id="2257b-245">Add support for Surface Go</span></span>

### <span data-ttu-id="2257b-246">Version2.12.136.0</span><span class="sxs-lookup"><span data-stu-id="2257b-246">Version 2.12.136.0</span></span>
*<span data-ttu-id="2257b-247">Date de publication: 29 janvier2018</span><span class="sxs-lookup"><span data-stu-id="2257b-247">Release Date: 29 January 2018</span></span>*

<span data-ttu-id="2257b-248">Cette version de Surface Dock Updater ajoute une prise en charge des éléments suivants:</span><span class="sxs-lookup"><span data-stu-id="2257b-248">This version of Surface Dock Updater adds support for the following:</span></span>
* <span data-ttu-id="2257b-249">Mise à jour du microprogramme du principal circuit microprogrammé de Surface Dock</span><span class="sxs-lookup"><span data-stu-id="2257b-249">Update for Surface Dock Main Chipset Firmware</span></span>
* <span data-ttu-id="2257b-250">Mise à jour du microprogramme DisplayPort de Surface Dock</span><span class="sxs-lookup"><span data-stu-id="2257b-250">Update for Surface Dock DisplayPort Firmware</span></span>
* <span data-ttu-id="2257b-251">Stabilité d’affichage améliorée pour les écrans externes lorsqu'ils sont utilisés avec Surface Book ou Surface Book2</span><span class="sxs-lookup"><span data-stu-id="2257b-251">Improved display stability for external displays when used with Surface Book or Surface Book 2</span></span>

<span data-ttu-id="2257b-252">En outre, l’installation de cette version de Surface Dock Updater sur les appareils Surface Book comprend les éléments suivants:</span><span class="sxs-lookup"><span data-stu-id="2257b-252">Additionally, installation of this version of Surface Dock Updater on Surface Book devices includes the following:</span></span>
* <span data-ttu-id="2257b-253">Mise à jour du microprogramme de base Surface Book</span><span class="sxs-lookup"><span data-stu-id="2257b-253">Update for Surface Book Base Firmware</span></span>
* <span data-ttu-id="2257b-254">Prise en charge des mises à jour du microprogramme de la station d’accueil Surface avec des améliorations destinées aux appareils Surface Book</span><span class="sxs-lookup"><span data-stu-id="2257b-254">Added support for Surface Dock firmware updates with improvements targeted to Surface Book devices</span></span>


### <span data-ttu-id="2257b-255">Version2.9.136.0</span><span class="sxs-lookup"><span data-stu-id="2257b-255">Version 2.9.136.0</span></span>
*<span data-ttu-id="2257b-256">Date de publication: 3novembre2017</span><span class="sxs-lookup"><span data-stu-id="2257b-256">Release date: November 3, 2017</span></span>*

<span data-ttu-id="2257b-257">Cette version de Surface Dock Updater ajoute une prise en charge des éléments suivants:</span><span class="sxs-lookup"><span data-stu-id="2257b-257">This version of Surface Dock Updater adds support for the following:</span></span>

* <span data-ttu-id="2257b-258">Mise à jour du microprogramme DisplayPort de Surface Dock</span><span class="sxs-lookup"><span data-stu-id="2257b-258">Update for Surface Dock DisplayPort Firmware</span></span>
* <span data-ttu-id="2257b-259">Résout un problème audio sur les cartes DisplayPort passives</span><span class="sxs-lookup"><span data-stu-id="2257b-259">Resolves an issue with audio over passive display port adapters</span></span>

### <span data-ttu-id="2257b-260">Version 2.1.15.0</span><span class="sxs-lookup"><span data-stu-id="2257b-260">Version 2.1.15.0</span></span>
*<span data-ttu-id="2257b-261">Date de publication: 19 juin2017</span><span class="sxs-lookup"><span data-stu-id="2257b-261">Release date: June 19, 2017</span></span>*

<span data-ttu-id="2257b-262">Cette version de Surface Dock Updater ajoute une prise en charge des éléments suivants:</span><span class="sxs-lookup"><span data-stu-id="2257b-262">This version of Surface Dock Updater adds support for the following:</span></span>

* <span data-ttu-id="2257b-263">Surface Laptop</span><span class="sxs-lookup"><span data-stu-id="2257b-263">Surface Laptop</span></span>
* <span data-ttu-id="2257b-264">SurfacePro</span><span class="sxs-lookup"><span data-stu-id="2257b-264">Surface Pro</span></span>

### <span data-ttu-id="2257b-265">Version 2.1.6.0</span><span class="sxs-lookup"><span data-stu-id="2257b-265">Version 2.1.6.0</span></span>
*<span data-ttu-id="2257b-266">Date de publication: 7 avril2017</span><span class="sxs-lookup"><span data-stu-id="2257b-266">Release date: April 7, 2017</span></span>*

<span data-ttu-id="2257b-267">Cette version de Surface Dock Updater ajoute une prise en charge des éléments suivants:</span><span class="sxs-lookup"><span data-stu-id="2257b-267">This version of Surface Dock Updater adds support for the following:</span></span>

* <span data-ttu-id="2257b-268">Mise à jour du microprogramme DisplayPort de Surface Dock</span><span class="sxs-lookup"><span data-stu-id="2257b-268">Update for Surface Dock DisplayPort firmware</span></span>
* <span data-ttu-id="2257b-269">Requiert Windows10</span><span class="sxs-lookup"><span data-stu-id="2257b-269">Requires Windows 10</span></span>

### <span data-ttu-id="2257b-270">Version 2.0.22.0</span><span class="sxs-lookup"><span data-stu-id="2257b-270">Version 2.0.22.0</span></span>
*<span data-ttu-id="2257b-271">Date de publication: 21 octobre2016</span><span class="sxs-lookup"><span data-stu-id="2257b-271">Release date: October 21, 2016</span></span>*

<span data-ttu-id="2257b-272">Cette version de Surface Dock Updater ajoute une prise en charge des éléments suivants:</span><span class="sxs-lookup"><span data-stu-id="2257b-272">This version of Surface Dock Updater adds support for the following:</span></span>

* <span data-ttu-id="2257b-273">Mise à jour du microprogramme Surface Dock USB</span><span class="sxs-lookup"><span data-stu-id="2257b-273">Update for Surface Dock USB firmware</span></span>
* <span data-ttu-id="2257b-274">Plus grande fiabilité d’Ethernet, du son et des ports USB</span><span class="sxs-lookup"><span data-stu-id="2257b-274">Improved reliability of Ethernet, audio, and USB ports</span></span>

### <span data-ttu-id="2257b-275">Version 1.0.8.0</span><span class="sxs-lookup"><span data-stu-id="2257b-275">Version 1.0.8.0</span></span>
*<span data-ttu-id="2257b-276">Date de publication: 26 avril2016</span><span class="sxs-lookup"><span data-stu-id="2257b-276">Release date: April 26, 2016</span></span>*

<span data-ttu-id="2257b-277">Cette version de Surface Dock Updater ajoute une prise en charge des éléments suivants:</span><span class="sxs-lookup"><span data-stu-id="2257b-277">This version of Surface Dock Updater adds support for the following:</span></span>

* <span data-ttu-id="2257b-278">Mise à jour du microprogramme du principal circuit microprogrammé de Surface Dock</span><span class="sxs-lookup"><span data-stu-id="2257b-278">Update for Surface Dock Main Chipset firmware</span></span>
* <span data-ttu-id="2257b-279">Mise à jour du microprogramme DisplayPort de Surface Dock</span><span class="sxs-lookup"><span data-stu-id="2257b-279">Update for Surface Dock DisplayPort firmware</span></span>

