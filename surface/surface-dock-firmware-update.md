---
title: Mise à jour du microprogramme Microsoft surface Dock-informations techniques destinées aux administrateurs informatiques
description: Cet article décrit l’utilisation de la mise à jour du microprogramme Microsoft surface Dock pour mettre à jour le microprogramme du Dock surface. Lorsqu’il est installé sur votre appareil surface, il met à jour tout Dock de surface relié à votre surface.
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
ms.date: 8/07/2020
ms.openlocfilehash: 9069903421d6e621dfbc31cd1cfaffb045fa9f19
ms.sourcegitcommit: c1efb75e8524193bdc0a5f7496dc23a92ac665c8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/12/2020
ms.locfileid: "11114552"
---
# <span data-ttu-id="cd242-104">Mise à jour du microprogramme Microsoft surface Dock: informations techniques destinées aux administrateurs informatiques</span><span class="sxs-lookup"><span data-stu-id="cd242-104">Microsoft Surface Dock Firmware Update: Technical information for IT admins</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cd242-105">Cet article contient des instructions techniques destinées aux administrateurs informatiques.</span><span class="sxs-lookup"><span data-stu-id="cd242-105">This article contains technical instructions for IT administrators.</span></span> <span data-ttu-id="cd242-106">Si vous êtes un particulier, voir [Comment mettre à jour le microprogramme de votre Dock surface](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock)   sur le site du support Microsoft.</span><span class="sxs-lookup"><span data-stu-id="cd242-106">If you are a home user, please see [How to update your Surface Dock Firmware](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock) on the Microsoft Support site.</span></span> <span data-ttu-id="cd242-107">Les instructions sur le site d’assistance sont les mêmes que les étapes générales d’installation ci-dessous, mais cet article contient des informations supplémentaires pour surveiller, vérifier et déployer la mise à jour sur plusieurs appareils sur un réseau.</span><span class="sxs-lookup"><span data-stu-id="cd242-107">The instructions at the support site are the same as the general installation steps below, but this article has additional information for monitoring, verifying, and deploying the update to multiple devices on a network.</span></span>

<span data-ttu-id="cd242-108">Cet article explique comment utiliser la mise à jour du microprogramme Microsoft surface Dock pour mettre à jour le microprogramme sur le Dock 1 de surface d’origine et ne s’applique pas à l’ancrage surface 2.</span><span class="sxs-lookup"><span data-stu-id="cd242-108">This article explains how to use Microsoft Surface Dock Firmware Update to update firmware on the original Surface Dock 1 and does not apply to Surface Dock 2.</span></span> <span data-ttu-id="cd242-109">Lorsqu’il est installé sur votre appareil surface, il met à jour tout Dock de surface relié à votre surface.</span><span class="sxs-lookup"><span data-stu-id="cd242-109">When installed on your Surface device, it will update any Surface Dock attached to your Surface device.</span></span> 

<span data-ttu-id="cd242-110">Cet outil remplace l’outil de mise à jour de l’outil de mise à jour de Microsoft surface Dock antérieur, auparavant disponible en téléchargement dans le cadre des outils surface.</span><span class="sxs-lookup"><span data-stu-id="cd242-110">This tool supersedes the earlier Microsoft Surface Dock Updater tool, previously available for download as part of Surface Tools for IT.</span></span> <span data-ttu-id="cd242-111">L’outil précédent a été nommé Surface_Dock_Updater_vx.xx.xxx.x.msi (où x indique le numéro de version) et n’est plus disponible en téléchargement et ne doit pas être utilisé.</span><span class="sxs-lookup"><span data-stu-id="cd242-111">The earlier tool was named Surface_Dock_Updater_vx.xx.xxx.x.msi (where x indicates the version number) and is no longer available for download and should not be used.</span></span>

## <span data-ttu-id="cd242-112">Installez la mise à jour du microprogramme de surface Dock</span><span class="sxs-lookup"><span data-stu-id="cd242-112">Install the Surface Dock Firmware Update</span></span>

<span data-ttu-id="cd242-113">Cette section décrit comment installer manuellement la mise à jour du microprogramme.</span><span class="sxs-lookup"><span data-stu-id="cd242-113">This section describes how to manually install the firmware update.</span></span>

> [!NOTE]
> <span data-ttu-id="cd242-114">Microsoft publie régulièrement de nouvelles versions de la mise à jour du microprogramme de surface Dock.</span><span class="sxs-lookup"><span data-stu-id="cd242-114">Microsoft periodically releases new versions of Surface Dock Firmware Update.</span></span> <span data-ttu-id="cd242-115">Le fichier MSI n’est pas mis à jour automatiquement.</span><span class="sxs-lookup"><span data-stu-id="cd242-115">The MSI file is not self-updating.</span></span> <span data-ttu-id="cd242-116">Si vous avez déployé le MSI sur les appareils surface et qu’une nouvelle version du microprogramme est publiée, vous devrez déployer la nouvelle version.</span><span class="sxs-lookup"><span data-stu-id="cd242-116">If you have deployed the MSI to Surface devices and a new version of the firmware is released, you will need to deploy the new version.</span></span>

1. <span data-ttu-id="cd242-117">Téléchargez et installez la [mise à jour du microprogramme Microsoft surface Dock](https://www.microsoft.com/download/details.aspx?id=46703).</span><span class="sxs-lookup"><span data-stu-id="cd242-117">Download and install [Microsoft Surface Dock Firmware Update](https://www.microsoft.com/download/details.aspx?id=46703).</span></span>
    - <span data-ttu-id="cd242-118">La mise à jour nécessite un appareil surface exécutant Windows 10, version 1803 ou ultérieure.</span><span class="sxs-lookup"><span data-stu-id="cd242-118">The update requires a Surface device running Windows 10, version 1803 or later.</span></span>
    - <span data-ttu-id="cd242-119">L’installation du fichier MSI peut vous inviter à redémarrer surface.</span><span class="sxs-lookup"><span data-stu-id="cd242-119">Installing the MSI file might prompt you to restart Surface.</span></span> <span data-ttu-id="cd242-120">Toutefois, le redémarrage n’est pas nécessaire pour effectuer la mise à jour.</span><span class="sxs-lookup"><span data-stu-id="cd242-120">However, restarting is not required to perform the update.</span></span>

2. <span data-ttu-id="cd242-121">Déconnectez votre appareil de surface du quai de surface, attendez ~ 5 secondes, puis reconnectez-vous.</span><span class="sxs-lookup"><span data-stu-id="cd242-121">Disconnect your Surface device from the Surface Dock, wait ~5 seconds, and then reconnect.</span></span> <span data-ttu-id="cd242-122">La mise à jour du microprogramme de surface Dock met à jour le Dock en silence en arrière-plan.</span><span class="sxs-lookup"><span data-stu-id="cd242-122">The Surface Dock Firmware Update will update the dock silently in background.</span></span> <span data-ttu-id="cd242-123">Le processus peut prendre quelques minutes et continuer même en cas d’interruption.</span><span class="sxs-lookup"><span data-stu-id="cd242-123">The process can take a few minutes to complete and will continue even if interrupted.</span></span> 

## <span data-ttu-id="cd242-124">Surveiller la mise à jour du microprogramme de surface Dock</span><span class="sxs-lookup"><span data-stu-id="cd242-124">Monitor the Surface Dock Firmware Update</span></span>

<span data-ttu-id="cd242-125">Cette section est facultative et offre une vue d’ensemble de la façon de surveiller l’installation de la mise à jour du microprogramme.</span><span class="sxs-lookup"><span data-stu-id="cd242-125">This section is optional and provides an overview of how to monitor installation of the firmware update.</span></span> 

<span data-ttu-id="cd242-126">Pour surveiller la mise à jour:</span><span class="sxs-lookup"><span data-stu-id="cd242-126">To monitor the update:</span></span>

1. <span data-ttu-id="cd242-127">Ouvrez l’observateur d’événements, accédez à l' **application journaux de >** à l’application, puis, sous **actions** dans le volet droit, cliquez sur **filtrer le journal actuel**, entrez **SurfaceDockFwUpdate** en regard de **sources d’événements**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="cd242-127">Open Event Viewer, browse to **Windows Logs > Application**, and then under **Actions** in the right-hand pane click **Filter Current Log**, enter **SurfaceDockFwUpdate** next to **Event sources**, and then click **OK**.</span></span>

2. <span data-ttu-id="cd242-128">Tapez la commande suivante à l’invite de commandes avec élévation de privilèges:</span><span class="sxs-lookup"><span data-stu-id="cd242-128">Type the following command at an elevated command prompt:</span></span>

    ```cmd
    Reg query "HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\WUDF\Services\SurfaceDockFwUpdate\Parameters"
    ```
3. <span data-ttu-id="cd242-129">Installez la mise à jour comme décrit dans la [section suivante](#install-the-surface-dock-firmware-update) de cet article.</span><span class="sxs-lookup"><span data-stu-id="cd242-129">Install the update as described in the [next section](#install-the-surface-dock-firmware-update) of this article.</span></span>
4. <span data-ttu-id="cd242-130">L’événement 2007 avec le texte suivant indique une mise à jour réussie: **mise à jour du microprogramme terminée. hr = 0 DriverTelementry eventCode = 2007**.</span><span class="sxs-lookup"><span data-stu-id="cd242-130">Event 2007 with the following text indicates a successful update: **Firmware update finished. hr=0 DriverTelementry EventCode = 2007**.</span></span> 
    - <span data-ttu-id="cd242-131">Si la mise à jour échoue, l’événement ID 2007 est affiché en tant qu’événement d' **erreur** plutôt que par **informations**.</span><span class="sxs-lookup"><span data-stu-id="cd242-131">If the update is not successful, then event ID 2007 will be displayed as an **Error** event rather than **Information**.</span></span> <span data-ttu-id="cd242-132">Par ailleurs, la version indiquée dans le Registre Windows ne sera pas la version actuelle.</span><span class="sxs-lookup"><span data-stu-id="cd242-132">Additionally, the version reported in the Windows Registry will not be current.</span></span>
5. <span data-ttu-id="cd242-133">À l’issue de la mise à jour, les valeurs DWORD mises à jour s’affichent dans le Registre Windows, correspondant à la version actuelle de l’outil.</span><span class="sxs-lookup"><span data-stu-id="cd242-133">When the update is complete, updated DWORD values will be displayed in the Windows Registry, corresponding to the current version of the tool.</span></span> <span data-ttu-id="cd242-134">Pour plus d’informations, consultez la section de [référence des versions](#versions-reference) de cet article.</span><span class="sxs-lookup"><span data-stu-id="cd242-134">See the [Versions reference](#versions-reference) section in this article for details.</span></span> <span data-ttu-id="cd242-135">Par exemple:</span><span class="sxs-lookup"><span data-stu-id="cd242-135">For example:</span></span>
    - <span data-ttu-id="cd242-136">Component10CurrentFwVersion 0x04ac3970 (78395760)</span><span class="sxs-lookup"><span data-stu-id="cd242-136">Component10CurrentFwVersion 0x04ac3970 (78395760)</span></span>
    - <span data-ttu-id="cd242-137">Component20CurrentFwVersion 0x04915a70 (76634736)</span><span class="sxs-lookup"><span data-stu-id="cd242-137">Component20CurrentFwVersion 0x04915a70 (76634736)</span></span>

>[!TIP]
><span data-ttu-id="cd242-138">Si vous voyez «la description de l’ID d’événement XXXX à partir de la source SurfaceDockFwUpdate est introuvable» dans le texte de l’événement, il est attendu et peut être ignoré.</span><span class="sxs-lookup"><span data-stu-id="cd242-138">If you see "The description for Event ID xxxx from source SurfaceDockFwUpdate cannot be found" in event text, this is expected and can be ignored.</span></span>

<span data-ttu-id="cd242-139">Reportez-vous également aux sections suivantes de cet article:</span><span class="sxs-lookup"><span data-stu-id="cd242-139">Also see the following sections in this article:</span></span> 
  - [<span data-ttu-id="cd242-140">Vérifier la fin de la mise à jour du microprogramme</span><span class="sxs-lookup"><span data-stu-id="cd242-140">How to verify completion of firmware update</span></span>](#how-to-verify-completion-of-the-firmware-update)
  - [<span data-ttu-id="cd242-141">Journalisation des événements</span><span class="sxs-lookup"><span data-stu-id="cd242-141">Event logging</span></span>](#event-logging)
  - [<span data-ttu-id="cd242-142">Conseils pour la résolution des problèmes</span><span class="sxs-lookup"><span data-stu-id="cd242-142">Troubleshooting tips</span></span>](#troubleshooting-tips)
  - [<span data-ttu-id="cd242-143">Réf version</span><span class="sxs-lookup"><span data-stu-id="cd242-143">Versions reference</span></span>](#versions-reference)

## <span data-ttu-id="cd242-144">Déploiement réseau</span><span class="sxs-lookup"><span data-stu-id="cd242-144">Network deployment</span></span>

<span data-ttu-id="cd242-145">Vous pouvez utiliser les commandes du programme d’installation Windows (Msiexec.exe) pour déployer la mise à jour de microprogramme de surface Dock sur plusieurs appareils sur votre réseau.</span><span class="sxs-lookup"><span data-stu-id="cd242-145">You can use Windows Installer commands (Msiexec.exe) to deploy Surface Dock Firmware Update to multiple devices across your network.</span></span> <span data-ttu-id="cd242-146">Lors de l’utilisation du gestionnaire de configuration de point de terminaison Microsoft ou d’un autre outil de déploiement, entrez la syntaxe suivante pour vous assurer que l’installation est silencieuse:</span><span class="sxs-lookup"><span data-stu-id="cd242-146">When using Microsoft Endpoint Configuration Manager or other deployment tool, enter the following syntax to ensure the installation is silent:</span></span>

- **<span data-ttu-id="cd242-147">Msiexec.exe/i \<path to msi file\> /Quiet/norestart</span><span class="sxs-lookup"><span data-stu-id="cd242-147">Msiexec.exe /i \<path to msi file\> /quiet /norestart</span></span>** 

  <span data-ttu-id="cd242-148">Par exemple:</span><span class="sxs-lookup"><span data-stu-id="cd242-148">For example:</span></span>
  ```
  msiexec /i "\\share\folder\Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.msi" /quiet /norestart
  ```

  > [!NOTE]
  > <span data-ttu-id="cd242-149">Par défaut, un fichier journal n’est pas créé.</span><span class="sxs-lookup"><span data-stu-id="cd242-149">A log file is not created by default.</span></span> <span data-ttu-id="cd242-150">Pour créer un fichier journal, vous devrez ajouter «/l*v [chemin]». Par exemple: Msiexec.exe/i \<path to msi file\> /l*v%windir%\logs\ SurfaceDockFWI. log "</span><span class="sxs-lookup"><span data-stu-id="cd242-150">In order to create a log file, you will need to append "/l*v [path]". For example: Msiexec.exe /i \<path to msi file\> /l*v %windir%\logs\ SurfaceDockFWI.log"</span></span>

  <span data-ttu-id="cd242-151">Pour plus d’informations, voir la documentation des [options de ligne de commande](https://docs.microsoft.com/windows/win32/msi/command-line-options) .</span><span class="sxs-lookup"><span data-stu-id="cd242-151">For more information, refer to [Command line options](https://docs.microsoft.com/windows/win32/msi/command-line-options) documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cd242-152">Si vous souhaitez conserver votre ancrage de surface à jour à l’aide d’une autre méthode, voir [mettre à jour votre station](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock) de dessin de surface pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="cd242-152">If you want to keep your Surface Dock updated using any other method, refer to [Update your Surface Dock](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock) for details.</span></span>

## <span data-ttu-id="cd242-153">Déploiement de Intune</span><span class="sxs-lookup"><span data-stu-id="cd242-153">Intune deployment</span></span>

<span data-ttu-id="cd242-154">Vous pouvez utiliser Intune pour distribuer les mises à jour de microprogramme de surface Dock sur vos appareils.</span><span class="sxs-lookup"><span data-stu-id="cd242-154">You can use Intune to distribute Surface Dock Firmware Update to your devices.</span></span> <span data-ttu-id="cd242-155">Tout d’abord, vous devez convertir le fichier MSI au format. intunewin, comme décrit dans la documentation suivante: [Intune standalone-gestion des applications Win32](https://docs.microsoft.com/intune/apps/apps-win32-app-management).</span><span class="sxs-lookup"><span data-stu-id="cd242-155">First you will need to convert the MSI file to the .intunewin format, as described in the following documentation: [Intune Standalone - Win32 app management](https://docs.microsoft.com/intune/apps/apps-win32-app-management).</span></span>

<span data-ttu-id="cd242-156">Utilisez la commande suivante:</span><span class="sxs-lookup"><span data-stu-id="cd242-156">Use the following command:</span></span>
  - **<span data-ttu-id="cd242-157">msiexec/i \<path to msi file\> /Quiet/q</span><span class="sxs-lookup"><span data-stu-id="cd242-157">msiexec /i \<path to msi file\> /quiet /q</span></span>**

## <span data-ttu-id="cd242-158">Vérifier la fin de la mise à jour du microprogramme</span><span class="sxs-lookup"><span data-stu-id="cd242-158">How to verify completion of the firmware update</span></span>

<span data-ttu-id="cd242-159">Le microcode de surface Dock comporte deux composants:</span><span class="sxs-lookup"><span data-stu-id="cd242-159">Surface dock firmware consists of two components:</span></span>

- <span data-ttu-id="cd242-160">**Component10:** Microcontroller Unit (MCU)</span><span class="sxs-lookup"><span data-stu-id="cd242-160">**Component10:** Micro controller unit (MCU) firmware</span></span>
- <span data-ttu-id="cd242-161">**Component20:** Microprogramme de port d’affichage (DP).</span><span class="sxs-lookup"><span data-stu-id="cd242-161">**Component20:** Display port (DP) firmware.</span></span>

<span data-ttu-id="cd242-162">Réussite de la mise à jour du microprogramme du Dock de surface entraîne de nouvelles valeurs de clé de Registre pour ces composants microprogrammes.</span><span class="sxs-lookup"><span data-stu-id="cd242-162">Successful completion of Surface Dock Firmware Update results in new registry key values for these firmware components.</span></span>

**<span data-ttu-id="cd242-163">Pour vérifier les mises à jour:</span><span class="sxs-lookup"><span data-stu-id="cd242-163">To verify updates:</span></span>**

1. <span data-ttu-id="cd242-164">Ouvrez Regedit et naviguez jusqu’au chemin de Registre suivant:</span><span class="sxs-lookup"><span data-stu-id="cd242-164">Open Regedit and navigate to the following registry path:</span></span>

    - **<span data-ttu-id="cd242-165">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\WUDF\Services\SurfaceDockFwUpdate\Parameters</span><span class="sxs-lookup"><span data-stu-id="cd242-165">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\WUDF\Services\SurfaceDockFwUpdate\Parameters</span></span>**

2. <span data-ttu-id="cd242-166">Recherchez les clés de Registre suivantes: **Component10CurrentFwVersion et Component20CurrentFwVersion**, qui font référence au microprogramme actuellement sur l’appareil.</span><span class="sxs-lookup"><span data-stu-id="cd242-166">Look for the registry keys: **Component10CurrentFwVersion and Component20CurrentFwVersion**, which refer to the firmware that is currently on the device.</span></span>

   ![Processus d’installation de la mise à jour du microprogramme du Dock surface](images/regeditDock.png)

3. <span data-ttu-id="cd242-168">Vérifiez que les nouvelles valeurs de clé de Registre correspondent aux valeurs de clé de Registre mises à jour répertoriées dans la référence de versions à la fin de ce document.</span><span class="sxs-lookup"><span data-stu-id="cd242-168">Verify the new registry key values match the updated registry key values listed in the Versions reference at the end of this document.</span></span> <span data-ttu-id="cd242-169">Si les valeurs correspondent, le microprogramme a été correctement mis à jour.</span><span class="sxs-lookup"><span data-stu-id="cd242-169">If the values match, the firmware was updated successfully.</span></span>

4. <span data-ttu-id="cd242-170">Si vous ne parvenez pas à vérifier, consultez la journalisation des événements et conseils de dépannage dans la section suivante.</span><span class="sxs-lookup"><span data-stu-id="cd242-170">If unable to verify, review Event logging and Troubleshooting tips in the next section.</span></span>

## <span data-ttu-id="cd242-171">Journalisation des événements</span><span class="sxs-lookup"><span data-stu-id="cd242-171">Event logging</span></span>

**<span data-ttu-id="cd242-172">Tableau1.</span><span class="sxs-lookup"><span data-stu-id="cd242-172">Table 1.</span></span> <span data-ttu-id="cd242-173">Fichiers journaux pour la mise à jour du microprogramme de surface Dock</span><span class="sxs-lookup"><span data-stu-id="cd242-173">Log files for Surface Dock Firmware Update</span></span>**

| <span data-ttu-id="cd242-174">Journal</span><span class="sxs-lookup"><span data-stu-id="cd242-174">Log</span></span>                              | <span data-ttu-id="cd242-175">Location</span><span class="sxs-lookup"><span data-stu-id="cd242-175">Location</span></span>                               | <span data-ttu-id="cd242-176">Remarques</span><span class="sxs-lookup"><span data-stu-id="cd242-176">Notes</span></span>                                                                                                                                                                                                         |
| -------------------------------- | --------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="cd242-177">Journal des mises à jour du microprogramme du Dock surface</span><span class="sxs-lookup"><span data-stu-id="cd242-177">Surface Dock Firmware Update log</span></span> | <span data-ttu-id="cd242-178">Le chemin d’accès doit être spécifié (voir remarque)</span><span class="sxs-lookup"><span data-stu-id="cd242-178">Path needs to be specified (see note)</span></span> | <span data-ttu-id="cd242-179">Les versions précédentes de cet outil écrivaient des événements pour les applications et les services Logs\Microsoft de mise à jour de surface Dock.</span><span class="sxs-lookup"><span data-stu-id="cd242-179">Earlier versions of this tool wrote events to Applications and Services Logs\Microsoft Surface Dock Updater.</span></span>                                                                                                  |
| <span data-ttu-id="cd242-180">Journal d’installation des appareils Windows</span><span class="sxs-lookup"><span data-stu-id="cd242-180">Windows Device Install log</span></span>       | <span data-ttu-id="cd242-181">%windir%\inf\setupapi.dev.log</span><span class="sxs-lookup"><span data-stu-id="cd242-181">%windir%\inf\setupapi.dev.log</span></span>           | <span data-ttu-id="cd242-182">Pour plus d’informations sur l’utilisation du journal d’installation de périphériques, voir la documentation sur l' [enregistrement Setupapi](https://docs.microsoft.com/windows-hardware/drivers/install/setupapi-logging--windows-vista-and-later-) .</span><span class="sxs-lookup"><span data-stu-id="cd242-182">For more information about using Device Install Log, refer to [SetupAPI Logging](https://docs.microsoft.com/windows-hardware/drivers/install/setupapi-logging--windows-vista-and-later-) documentation.</span></span> |


**<span data-ttu-id="cd242-183">Tableau2.</span><span class="sxs-lookup"><span data-stu-id="cd242-183">Table 2.</span></span> <span data-ttu-id="cd242-184">ID du journal des événements pour la mise à jour du microprogramme de surface Dock</span><span class="sxs-lookup"><span data-stu-id="cd242-184">Event log IDs for Surface Dock Firmware Update</span></span>**<br>
<span data-ttu-id="cd242-185">Les événements sont enregistrés dans le journal des événements de l’application.</span><span class="sxs-lookup"><span data-stu-id="cd242-185">Events are logged in the Application Event Log.</span></span>  <span data-ttu-id="cd242-186">Remarque: les versions antérieures de cet outil écrivaient des événements pour les applications et les services Logs\Microsoft de mise à jour de surface Dock.</span><span class="sxs-lookup"><span data-stu-id="cd242-186">Note:  Earlier versions of this tool wrote events to Applications and Services Logs\Microsoft Surface Dock Updater.</span></span>

| <span data-ttu-id="cd242-187">ID d’événement</span><span class="sxs-lookup"><span data-stu-id="cd242-187">Event ID</span></span> | <span data-ttu-id="cd242-188">Type d’événement</span><span class="sxs-lookup"><span data-stu-id="cd242-188">Event type</span></span>                                                           |
| -------- | -------------------------------------------------------------------- |
| <span data-ttu-id="cd242-189">2001</span><span class="sxs-lookup"><span data-stu-id="cd242-189">2001</span></span>     | <span data-ttu-id="cd242-190">La mise à jour du microprogramme est lancée.</span><span class="sxs-lookup"><span data-stu-id="cd242-190">Dock firmware update has started.</span></span>                                    |
| <span data-ttu-id="cd242-191">2002</span><span class="sxs-lookup"><span data-stu-id="cd242-191">2002</span></span>     | <span data-ttu-id="cd242-192">Le retrait du microprogramme a été ignoré, car le Dock est connu comme étant à jour.</span><span class="sxs-lookup"><span data-stu-id="cd242-192">Dock firmware update skipped because dock is known to be up to date.</span></span> |
| <span data-ttu-id="cd242-193">2003</span><span class="sxs-lookup"><span data-stu-id="cd242-193">2003</span></span>     | <span data-ttu-id="cd242-194">La mise à jour du microprogramme a échoué pour obtenir la version du microprogramme.</span><span class="sxs-lookup"><span data-stu-id="cd242-194">Dock firmware update failed to get firmware version.</span></span>                 |
| <span data-ttu-id="cd242-195">2004</span><span class="sxs-lookup"><span data-stu-id="cd242-195">2004</span></span>     | <span data-ttu-id="cd242-196">Interrogation de la version du microprogramme.</span><span class="sxs-lookup"><span data-stu-id="cd242-196">Querying the firmware version.</span></span>                                       |
| <span data-ttu-id="cd242-197">2005</span><span class="sxs-lookup"><span data-stu-id="cd242-197">2005</span></span>     | <span data-ttu-id="cd242-198">Échec du démarrage de la mise à jour du microprogramme.</span><span class="sxs-lookup"><span data-stu-id="cd242-198">Dock firmware failed to start update.</span></span>                                |
| <span data-ttu-id="cd242-199">2006</span><span class="sxs-lookup"><span data-stu-id="cd242-199">2006</span></span>     | <span data-ttu-id="cd242-200">Échec de l’envoi des paires d’avantages et de charges utiles.</span><span class="sxs-lookup"><span data-stu-id="cd242-200">Failed to send offer/payload pairs.</span></span>                                  |
| <span data-ttu-id="cd242-201">2007</span><span class="sxs-lookup"><span data-stu-id="cd242-201">2007</span></span>     | <span data-ttu-id="cd242-202">Mise à jour du microprogramme terminée.</span><span class="sxs-lookup"><span data-stu-id="cd242-202">Firmware update finished.</span></span>                                            |
| <span data-ttu-id="cd242-203">2008</span><span class="sxs-lookup"><span data-stu-id="cd242-203">2008</span></span>     | <span data-ttu-id="cd242-204">COMMENCER la télémétrie de la station d’accueil.</span><span class="sxs-lookup"><span data-stu-id="cd242-204">BEGIN dock telemetry.</span></span>                                                |
| <span data-ttu-id="cd242-205">2011</span><span class="sxs-lookup"><span data-stu-id="cd242-205">2011</span></span>     | <span data-ttu-id="cd242-206">Télémétrie du Dock.</span><span class="sxs-lookup"><span data-stu-id="cd242-206">END dock telemetry.</span></span>                                                  |

## <span data-ttu-id="cd242-207">Conseils pour la résolution des problèmes</span><span class="sxs-lookup"><span data-stu-id="cd242-207">Troubleshooting tips</span></span>

- <span data-ttu-id="cd242-208">Déconnectez complètement l’alimentation du Dock de surface de l’alimentation CA pour réinitialiser le quai de surface.</span><span class="sxs-lookup"><span data-stu-id="cd242-208">Completely disconnect power for Surface dock from the AC power to reset the Surface Dock.</span></span>
- <span data-ttu-id="cd242-209">Déconnectez tous les périphériques à l’exception du Dock surface.</span><span class="sxs-lookup"><span data-stu-id="cd242-209">Disconnect all peripherals except for the Surface Dock.</span></span>
- <span data-ttu-id="cd242-210">Désinstallez toutes les mises à jour de microprogramme de surface Dock actuelles, puis installez la version la plus récente.</span><span class="sxs-lookup"><span data-stu-id="cd242-210">Uninstall any current Surface Dock Firmware Update and then install the latest version.</span></span>
- <span data-ttu-id="cd242-211">Assurez-vous que le Dock de surface est déconnecté, puis Prévoyez suffisamment de temps pour que la mise à jour s’exécute comme surveillé par le biais d’un témoin sur le port Ethernet du Dock.</span><span class="sxs-lookup"><span data-stu-id="cd242-211">Ensure that the Surface Dock is disconnected, and then allow enough time for the update to complete as monitored via an LED in the Ethernet port of the dock.</span></span> <span data-ttu-id="cd242-212">Patientez jusqu’à ce que le témoin lumineux cesse de clignoter avant de débrancher le quai de surface.</span><span class="sxs-lookup"><span data-stu-id="cd242-212">Wait until the LED stops blinking before you unplug Surface Dock from power.</span></span>
- <span data-ttu-id="cd242-213">Connectez le Dock de surface à un autre appareil pour voir s’il est en mesure de mettre à jour le Dock.</span><span class="sxs-lookup"><span data-stu-id="cd242-213">Connect the Surface Dock to a different device to see if it is able to update the dock.</span></span>

## <span data-ttu-id="cd242-214">Réf version</span><span class="sxs-lookup"><span data-stu-id="cd242-214">Versions reference</span></span>

>[!NOTE]
><span data-ttu-id="cd242-215">Le fichier d’installation est mis en forme avec le format d’attribution de noms suivant: **Surface_Dock_FwUpdate_X.XX.XXX_Win10_XXXXX_XX.XXX.XXXXX_X.MSI** (par exemple: Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.msi) et installé par défaut dans C:\Program Files\SurfaceUpdate.</span><span class="sxs-lookup"><span data-stu-id="cd242-215">The installation file is released with the following naming format: **Surface_Dock_FwUpdate_X.XX.XXX_Win10_XXXXX_XX.XXX.XXXXX_X.MSI** (ex: Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.msi) and installs by default to C:\Program Files\SurfaceUpdate.</span></span>

### <span data-ttu-id="cd242-216">Version 1.53.139.0</span><span class="sxs-lookup"><span data-stu-id="cd242-216">Version 1.53.139.0</span></span>
*<span data-ttu-id="cd242-217">Date de publication: 4 août 2020</span><span class="sxs-lookup"><span data-stu-id="cd242-217">Release Date: August 4, 2020</span></span>*

<span data-ttu-id="cd242-218">Cette version de la mise à jour de microprogramme de surface Dock inclut des correctifs et une prise en charge pour:</span><span class="sxs-lookup"><span data-stu-id="cd242-218">This version of Surface Dock Firmware Update includes bug fixes and support for:</span></span>
- <span data-ttu-id="cd242-219">Mise à jour de surface Dock 1 à l’aide de surface Pro X.</span><span class="sxs-lookup"><span data-stu-id="cd242-219">Updating Surface Dock 1 using Surface Pro X.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="cd242-220">Si vous exécutez surface Pro X, téléchargez le. Version de ARM64.</span><span class="sxs-lookup"><span data-stu-id="cd242-220">If you're running Surface Pro X, download the .ARM64 build.</span></span> <span data-ttu-id="cd242-221">Pour tous les autres appareils, utilisez la build AMD64.</span><span class="sxs-lookup"><span data-stu-id="cd242-221">For all other devices, use the AMD64 build.</span></span> 
 


### <span data-ttu-id="cd242-222">Version 1.42.139</span><span class="sxs-lookup"><span data-stu-id="cd242-222">Version 1.42.139</span></span> 
*<span data-ttu-id="cd242-223">Date de publication: 18 2019 septembre</span><span class="sxs-lookup"><span data-stu-id="cd242-223">Release Date: September 18 2019</span></span>*

<span data-ttu-id="cd242-224">Cette version, incluse dans Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.MSI, met à jour le microprogramme en arrière-plan.</span><span class="sxs-lookup"><span data-stu-id="cd242-224">This version, contained in Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.MSI, updates firmware in the background.</span></span> 
**<span data-ttu-id="cd242-225">Valeurs de clé de Registre mises à jour:</span><span class="sxs-lookup"><span data-stu-id="cd242-225">Updated registry key values:</span></span>**<br>

- <span data-ttu-id="cd242-226">Component10CurrentFwVersion mis à jour sur **4ac3970**.</span><span class="sxs-lookup"><span data-stu-id="cd242-226">Component10CurrentFwVersion updated to **4ac3970**.</span></span>
- <span data-ttu-id="cd242-227">Component20CurrentFwVersion mis à jour sur **4a1d570**.</span><span class="sxs-lookup"><span data-stu-id="cd242-227">Component20CurrentFwVersion updated to **4a1d570**.</span></span>

<span data-ttu-id="cd242-228">La prise en charge de surface Pro 7 et de surface Laptop 3 est ajoutée.</span><span class="sxs-lookup"><span data-stu-id="cd242-228">It adds support for Surface Pro 7 and Surface Laptop 3.</span></span>

## <span data-ttu-id="cd242-229">Versions héritées</span><span class="sxs-lookup"><span data-stu-id="cd242-229">Legacy versions</span></span>

### <span data-ttu-id="cd242-230">Version 2.23.139.0</span><span class="sxs-lookup"><span data-stu-id="cd242-230">Version 2.23.139.0</span></span>
*<span data-ttu-id="cd242-231">Date de publication: 10 octobre 2018</span><span class="sxs-lookup"><span data-stu-id="cd242-231">Release Date: 10 October 2018</span></span>*

<span data-ttu-id="cd242-232">Cette version de Surface Dock Updater ajoute une prise en charge des éléments suivants:</span><span class="sxs-lookup"><span data-stu-id="cd242-232">This version of Surface Dock Updater adds support for the following:</span></span>

- <span data-ttu-id="cd242-233">Ajouter la prise en charge de surface Pro 6</span><span class="sxs-lookup"><span data-stu-id="cd242-233">Add support for Surface Pro 6</span></span>
- <span data-ttu-id="cd242-234">Ajouter la prise en charge de surface Laptop 2</span><span class="sxs-lookup"><span data-stu-id="cd242-234">Add support for Surface Laptop 2</span></span>


### <span data-ttu-id="cd242-235">Version 2.22.139.0</span><span class="sxs-lookup"><span data-stu-id="cd242-235">Version 2.22.139.0</span></span>
*<span data-ttu-id="cd242-236">Date de publication: 26 juillet 2018</span><span class="sxs-lookup"><span data-stu-id="cd242-236">Release Date: 26 July 2018</span></span>*

<span data-ttu-id="cd242-237">Cette version de Surface Dock Updater ajoute une prise en charge des éléments suivants:</span><span class="sxs-lookup"><span data-stu-id="cd242-237">This version of Surface Dock Updater adds support for the following:</span></span>

- <span data-ttu-id="cd242-238">Augmenter la fiabilité des mises à jour</span><span class="sxs-lookup"><span data-stu-id="cd242-238">Increase update reliability</span></span>
- <span data-ttu-id="cd242-239">Ajouter la prise en charge de surface Go</span><span class="sxs-lookup"><span data-stu-id="cd242-239">Add support for Surface Go</span></span>

### <span data-ttu-id="cd242-240">Version2.12.136.0</span><span class="sxs-lookup"><span data-stu-id="cd242-240">Version 2.12.136.0</span></span>
*<span data-ttu-id="cd242-241">Date de publication: 29 janvier2018</span><span class="sxs-lookup"><span data-stu-id="cd242-241">Release Date: 29 January 2018</span></span>*

<span data-ttu-id="cd242-242">Cette version de Surface Dock Updater ajoute une prise en charge des éléments suivants:</span><span class="sxs-lookup"><span data-stu-id="cd242-242">This version of Surface Dock Updater adds support for the following:</span></span>
* <span data-ttu-id="cd242-243">Mise à jour du microprogramme du principal circuit microprogrammé de Surface Dock</span><span class="sxs-lookup"><span data-stu-id="cd242-243">Update for Surface Dock Main Chipset Firmware</span></span>
* <span data-ttu-id="cd242-244">Mise à jour du microprogramme DisplayPort de Surface Dock</span><span class="sxs-lookup"><span data-stu-id="cd242-244">Update for Surface Dock DisplayPort Firmware</span></span>
* <span data-ttu-id="cd242-245">Stabilité d’affichage améliorée pour les écrans externes lorsqu'ils sont utilisés avec Surface Book ou Surface Book2</span><span class="sxs-lookup"><span data-stu-id="cd242-245">Improved display stability for external displays when used with Surface Book or Surface Book 2</span></span>

<span data-ttu-id="cd242-246">En outre, l’installation de cette version de Surface Dock Updater sur les appareils Surface Book comprend les éléments suivants:</span><span class="sxs-lookup"><span data-stu-id="cd242-246">Additionally, installation of this version of Surface Dock Updater on Surface Book devices includes the following:</span></span>
* <span data-ttu-id="cd242-247">Mise à jour du microprogramme de base Surface Book</span><span class="sxs-lookup"><span data-stu-id="cd242-247">Update for Surface Book Base Firmware</span></span>
* <span data-ttu-id="cd242-248">Prise en charge des mises à jour du microprogramme de la station d’accueil Surface avec des améliorations destinées aux appareils Surface Book</span><span class="sxs-lookup"><span data-stu-id="cd242-248">Added support for Surface Dock firmware updates with improvements targeted to Surface Book devices</span></span>


### <span data-ttu-id="cd242-249">Version2.9.136.0</span><span class="sxs-lookup"><span data-stu-id="cd242-249">Version 2.9.136.0</span></span>
*<span data-ttu-id="cd242-250">Date de publication: 3novembre2017</span><span class="sxs-lookup"><span data-stu-id="cd242-250">Release date: November 3, 2017</span></span>*

<span data-ttu-id="cd242-251">Cette version de Surface Dock Updater ajoute une prise en charge des éléments suivants:</span><span class="sxs-lookup"><span data-stu-id="cd242-251">This version of Surface Dock Updater adds support for the following:</span></span>

* <span data-ttu-id="cd242-252">Mise à jour du microprogramme DisplayPort de Surface Dock</span><span class="sxs-lookup"><span data-stu-id="cd242-252">Update for Surface Dock DisplayPort Firmware</span></span>
* <span data-ttu-id="cd242-253">Résout un problème audio sur les cartes DisplayPort passives</span><span class="sxs-lookup"><span data-stu-id="cd242-253">Resolves an issue with audio over passive display port adapters</span></span>

### <span data-ttu-id="cd242-254">Version 2.1.15.0</span><span class="sxs-lookup"><span data-stu-id="cd242-254">Version 2.1.15.0</span></span>
*<span data-ttu-id="cd242-255">Date de publication: 19 juin2017</span><span class="sxs-lookup"><span data-stu-id="cd242-255">Release date: June 19, 2017</span></span>*

<span data-ttu-id="cd242-256">Cette version de Surface Dock Updater ajoute une prise en charge des éléments suivants:</span><span class="sxs-lookup"><span data-stu-id="cd242-256">This version of Surface Dock Updater adds support for the following:</span></span>

* <span data-ttu-id="cd242-257">Surface Laptop</span><span class="sxs-lookup"><span data-stu-id="cd242-257">Surface Laptop</span></span>
* <span data-ttu-id="cd242-258">SurfacePro</span><span class="sxs-lookup"><span data-stu-id="cd242-258">Surface Pro</span></span>

### <span data-ttu-id="cd242-259">Version 2.1.6.0</span><span class="sxs-lookup"><span data-stu-id="cd242-259">Version 2.1.6.0</span></span>
*<span data-ttu-id="cd242-260">Date de publication: 7 avril2017</span><span class="sxs-lookup"><span data-stu-id="cd242-260">Release date: April 7, 2017</span></span>*

<span data-ttu-id="cd242-261">Cette version de Surface Dock Updater ajoute une prise en charge des éléments suivants:</span><span class="sxs-lookup"><span data-stu-id="cd242-261">This version of Surface Dock Updater adds support for the following:</span></span>

* <span data-ttu-id="cd242-262">Mise à jour du microprogramme DisplayPort de Surface Dock</span><span class="sxs-lookup"><span data-stu-id="cd242-262">Update for Surface Dock DisplayPort firmware</span></span>
* <span data-ttu-id="cd242-263">Requiert Windows10</span><span class="sxs-lookup"><span data-stu-id="cd242-263">Requires Windows 10</span></span>

### <span data-ttu-id="cd242-264">Version 2.0.22.0</span><span class="sxs-lookup"><span data-stu-id="cd242-264">Version 2.0.22.0</span></span>
*<span data-ttu-id="cd242-265">Date de publication: 21 octobre2016</span><span class="sxs-lookup"><span data-stu-id="cd242-265">Release date: October 21, 2016</span></span>*

<span data-ttu-id="cd242-266">Cette version de Surface Dock Updater ajoute une prise en charge des éléments suivants:</span><span class="sxs-lookup"><span data-stu-id="cd242-266">This version of Surface Dock Updater adds support for the following:</span></span>

* <span data-ttu-id="cd242-267">Mise à jour du microprogramme Surface Dock USB</span><span class="sxs-lookup"><span data-stu-id="cd242-267">Update for Surface Dock USB firmware</span></span>
* <span data-ttu-id="cd242-268">Plus grande fiabilité d’Ethernet, du son et des ports USB</span><span class="sxs-lookup"><span data-stu-id="cd242-268">Improved reliability of Ethernet, audio, and USB ports</span></span>

### <span data-ttu-id="cd242-269">Version 1.0.8.0</span><span class="sxs-lookup"><span data-stu-id="cd242-269">Version 1.0.8.0</span></span>
*<span data-ttu-id="cd242-270">Date de publication: 26 avril2016</span><span class="sxs-lookup"><span data-stu-id="cd242-270">Release date: April 26, 2016</span></span>*

<span data-ttu-id="cd242-271">Cette version de Surface Dock Updater ajoute une prise en charge des éléments suivants:</span><span class="sxs-lookup"><span data-stu-id="cd242-271">This version of Surface Dock Updater adds support for the following:</span></span>

* <span data-ttu-id="cd242-272">Mise à jour du microprogramme du principal circuit microprogrammé de Surface Dock</span><span class="sxs-lookup"><span data-stu-id="cd242-272">Update for Surface Dock Main Chipset firmware</span></span>
* <span data-ttu-id="cd242-273">Mise à jour du microprogramme DisplayPort de Surface Dock</span><span class="sxs-lookup"><span data-stu-id="cd242-273">Update for Surface Dock DisplayPort firmware</span></span>

