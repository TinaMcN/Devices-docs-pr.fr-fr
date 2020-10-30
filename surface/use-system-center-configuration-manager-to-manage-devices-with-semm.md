---
title: Utiliser le gestionnaire de configuration de point de terminaison Microsoft pour gérer les appareils avec SEMM (surface)
description: Découvrez comment gérer le mode de gestion de l’entreprise Microsoft surface (SEMM) avec Endpoint Configuration Manager.
keywords: inscription, mise à jour, scripts, paramètres
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: hachidan
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
ms.date: 10/28/2020
ms.openlocfilehash: 2d31f520d8c4da54f47b2b89b58b43e2cb983f1a
ms.sourcegitcommit: 7f5b97275fe301ef700f9c77954a1054e2e8d046
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/30/2020
ms.locfileid: "11145615"
---
# Utilisez Microsoft Endpoint Configuration Manager pour gérer les appareils avec SEMM

La fonctionnalité Microsoft surface Management Mode (SEMM) des appareils surface UEFI permet aux administrateurs de gérer et de sécuriser la configuration des paramètres de surface UEFI. Pour la plupart des organisations, ce processus est réalisé en créant des packages Windows Installer (. msi) à l’aide de l’outil de configuration de Microsoft surface UEFI. Ces packages sont ensuite exécutés ou déployés sur les appareils surface du client pour inscrire les appareils dans SEMM et mettre à jour la configuration des paramètres de surface UEFI.

Pour les organisations qui utilisent Microsoft Endpoint Configuration Manager, vous pouvez utiliser le processus MSI Microsoft surface. Configurator pour déployer et administrer SEMM. Le Gestionnaire Microsoft surface UEFI est un programme d’installation léger qui rend les assemblys requis pour la gestion SEMM disponible sur un appareil. En installant ces assemblys avec le Gestionnaire Microsoft surface UEFI sur un client géré, SEMM peut être administré par Configuration Manager avec des scripts PowerShell, déployés sous la forme d’applications. Dans le cadre de ce processus, la gestion de SEMM est effectuée dans Configuration Manager, ce qui vous permet d’éviter d’avoir recours à l’outil de Configurateur UEFI extérieur de Microsoft surface.

> [!Note]
> Bien que la procédure décrite dans cet article puisse fonctionner avec des versions antérieures du gestionnaire de configuration de point de terminaison ou avec d’autres solutions de gestion tierces, la gestion de SEMM avec Microsoft surface UEFI Manager et PowerShell est uniquement prise en charge avec la branche actuelle du gestionnaire de configuration de point de terminaison.

#### Conditions préalables

Avant de commencer la procédure décrite dans cet article, vous devez vous familiariser avec les technologies et les outils suivants:

* [Surface UEFI](https://technet.microsoft.com/itpro/surface/manage-surface-uefi-settings)
* [SurfaceEnterpriseManagementMode (SEMM)](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode)
* [Script PowerShell](https://technet.microsoft.com/scriptcenter/dd742419)
* [Déploiement d’applications System Center Configuration Manager](https://docs.microsoft.com/sccm/apps/deploy-use/deploy-applications)
* Gestion des certificats

> [!Note]
> Vous aurez également accès au certificat que vous envisagez d’utiliser pour sécuriser SEMM. Pour plus d’informations sur la configuration requise pour ce certificat, voir [exigences de certificat en mode de gestion de surface d’entreprise](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements).
> 
> Il est très important que ce certificat soit maintenu dans un emplacement sûr et correctement sauvegardé. Si ce certificat est perdu ou inutilisable, il n’est pas possible de réinitialiser surface UEFI, de modifier les paramètres de surface gérée ou de supprimer SEMM d’un appareil surface inscrit.

#### Télécharger le Gestionnaire Microsoft surface UEFI

La gestion de SEMM avec Configuration Manager nécessite l’installation de Microsoft surface UEFI Manager sur chaque périphérique surface du client. Vous pouvez télécharger le Gestionnaire Microsoft surface UEFI (SurfaceUEFIManager.msi) à partir de la page [Outils surface pour cette application](https://www.microsoft.com/download/details.aspx?id=46703) dans le centre de téléchargement Microsoft.

#### Télécharger les scripts SEMM pour Configuration Manager

Après avoir installé le Gestionnaire Microsoft surface UEFI sur le périphérique surface du client, SEMM est déployé et géré avec des scripts PowerShell. Vous pouvez télécharger des exemples de [scripts de gestion de SEMM](https://www.microsoft.com/download/details.aspx?id=46703) à partir du centre de téléchargement.

## Déployer le Gestionnaire Microsoft surface UEFI

Le déploiement de Microsoft surface UEFI Manager est un déploiement d’application classique. Le fichier du programme d’installation du Gestionnaire Microsoft surface UEFI est un fichier Windows Installer standard que vous pouvez installer à l’aide de l' [option silence standard](https://msdn.microsoft.com/library/windows/desktop/aa367988).

La commande d’installation du Gestionnaire Microsoft surface UEFI est la suivante:

`msiexec /i "SurfaceUEFIManagerSetup.msi" /q`

La commande permettant de désinstaller le Gestionnaire Microsoft surface UEFI est la suivante.

`msiexec /x {541DA890-1AEB-446D-B3FD-D5B3BB18F9AF} /q`

Pour créer une nouvelle application et la déployer dans une collection qui contient vos périphériques surface, procédez comme suit:

1. Ouvrez la console Configuration Manager à partir de l’écran d' **Accueil** ou du menu **Démarrer** .
2. Sélectionnez **bibliothèque de logiciels** dans le coin inférieur gauche de la fenêtre.
3. Développez le nœud **gestion des applications** de la bibliothèque logicielle, puis sélectionnez **applications**.
4. Sélectionnez le bouton **créer une application** sous l’onglet **Accueil** en haut de la fenêtre. Cette opération démarre l’Assistant Création d’une application.
5. L’Assistant Création d’une application présente les étapes suivantes:

   * **Général** : l’option **détecter automatiquement les informations sur cette application à partir des fichiers d’installation** est activée par défaut. Dans le champ **type** , le **programme d’installation Windows (fichier. msi)** est également sélectionné par défaut. Sélectionnez **Parcourir** pour accéder à **SurfaceUEFIManagerSetup.msi**, puis sélectionnez **suivant**.
   
      > [!Note]
      > L’emplacement de SurfaceUEFIManagerSetup.msi doit se trouver sur un partage réseau et être placé dans un dossier qui ne contient pas d’autres fichiers. Un emplacement de fichier local ne peut pas être utilisé.

   * **Importer des informations** : l’Assistant Création d’application analysera le fichier. msi et lira le nom de l' **application** et le **Code du produit**. SurfaceUEFIManagerSetup.msi doit être répertoriée en tant que seul fichier sous les **fichiers de contenu**de ligne, comme illustré dans la figure 1. Sélectionnez **Next (suivant** ) pour continuer.

      ![Les informations de configuration du gestionnaire de surface UEFI sont automatiquement analysées](images/config-mgr-semm-fig1.png "Information from Surface UEFI Manager setup is automatically parsed")

      *Figure1. Les informations du programme d’installation du Gestionnaire Microsoft surface UEFI sont automatiquement analysées.*

   * **Informations générales** : vous pouvez modifier le nom de l’application et les informations relatives à l’éditeur et à la version, ou ajouter des commentaires sur cette page. La commande d’installation de Microsoft surface UEFI Manager s’affiche dans le champ programme d’installation. Le comportement d’installation par défaut de l’installation pour le système permet à Microsoft surface UEFI Manager d’installer les assemblys requis pour SEMM, même si un utilisateur n’est pas connecté à l’appareil surface. Sélectionnez **Next (suivant** ) pour continuer.
   * **Résumé** : les informations analysées lors de l’étape d' **importation des informations** et vos sélections à partir de l’étape **informations générales** apparaissent sur cette page. Pour confirmer vos sélections et créer l’application, sélectionnez **Next (suivant** ).
   * **Progression** : affiche une barre de progression et un statut lors de l’importation et de l’ajout de l’application à la bibliothèque de logiciels.
   * **Achèvement** : la confirmation de la création de l’application réussie s’affiche lorsque le processus de création d’application est terminé. Sélectionnez **Fermer** pour terminer l’Assistant Création d’une application.

Une fois l’application créée dans Configuration Manager, vous pouvez la diffuser sur vos points de distribution et la déployer dans les collections, y compris sur les appareils surface. Cette application ne peut pas installer ou activer SEMM sur le périphérique surface. Il fournit uniquement les assemblys nécessaires à l’activation de SEMM à l’aide du script PowerShell.

Si vous ne voulez pas installer les assemblys Microsoft surface UEFI Manager sur des appareils qui ne sont pas gérés avec SEMM, vous pouvez configurer le Gestionnaire Microsoft surface UEFI en tant que dépendance des scripts du gestionnaire de configuration SEMM. Ce scénario est abordé dans la section [déploiement de scripts du gestionnaire de configuration SEMM](#deploy-semm-configuration-manager-scripts) , plus loin dans cet article.

## Créer ou modifier les scripts du gestionnaire de configuration SEMM

Une fois les assemblys requis installés sur les appareils, le processus d’inscription des appareils dans SEMM et de configuration de surface UEFI est réalisé avec les scripts PowerShell et déployés en tant qu’application de script avec Configuration Manager. Ces scripts peuvent être modifiés pour répondre aux besoins de votre organisation et de votre environnement. Par exemple, vous pouvez créer plusieurs configurations pour les appareils à surface gérée dans différents services ou rôles. Vous pouvez télécharger des exemples de scripts pour SEMM et Configuration Manager à partir du lien dans la section [éléments requis](#prerequisites) au début de cet article.

Il existe deux scripts principaux dont vous aurez besoin pour effectuer un déploiement SEMM avec Configuration Manager:

* **ConfigureSEMM.ps1** : utilisez ce script pour créer des packages de configuration pour vos appareils de surface avec les paramètres UEFI de surface souhaités afin d’appliquer les paramètres spécifiés à un appareil surface, d’inscrire l’appareil dans SEMM et de définir une clé de Registre utilisée pour identifier l’inscription de l’appareil dans SEMM.
* **ResetSEMM.ps1** : utilisez ce script pour réinitialiser SEMM sur un appareil surface, qui annule son inscription à partir de SEMM et supprime le contrôle sur les paramètres de surface UEFI.

Les exemples de scripts incluent des exemples illustrant comment définir les paramètres de surface UEFI et comment contrôler les autorisations sur ces paramètres. Ces paramètres peuvent être modifiés pour sécuriser surface UEFI et définir les paramètres de surface UEFI en fonction des besoins de votre environnement. Les sections suivantes de cet article expliquent le script de ConfigureSEMM.ps1 et explorent les modifications que vous devez apporter au script pour répondre à vos besoins.

> [!NOTE]
> Les scripts du gestionnaire de configuration SEMM et le fichier de certificat SEMM exporté (. pfx) doivent être placés dans le même dossier sans autres fichiers avant d’être ajoutés à Configuration Manager.

### Spécifier les noms des certificats et des packages

La première zone du script que vous devez modifier est la partie qui spécifie et charge le certificat SEMM, ainsi que la version SurfaceUEFIManager, ainsi que les noms des packages de configuration SEMM et SEMM de réinitialisation du package. Le nom du certificat et la version SurfaceUEFIManager sont indiqués sur les lignes 56 à 73 dans le script ConfigureSEMM.ps1.

  ```powershell
  56    $WorkingDirPath = split-path -parent $MyInvocation.MyCommand.Definition
  57    $packageRoot = "$WorkingDirPath\Config"
  58    $certName = "FabrikamSEMMSample.pfx"
  59  $DllVersion = "2.26.136.0"
  60
  61  $certNameOnly = [System.IO.Path]::GetFileNameWithoutExtension($certName)
  62  $ProvisioningPackage = $certNameOnly + "ProvisioningPackage.pkg"
  63  $ResetPackage = $certNameOnly + "ResetPackage.pkg"
  64
  65    if (-not (Test-Path $packageRoot))  { New-Item -ItemType Directory -Force -Path $packageRoot }
  66    Copy-Item "$WorkingDirPath\$certName" $packageRoot
  67    
  68    $privateOwnerKey = Join-Path -Path $packageRoot -ChildPath $certName
  69    $ownerPackageName = Join-Path -Path $packageRoot -ChildPath $ProvisioningPackage
  70    $resetPackageName = Join-Path -Path $packageRoot -ChildPath $ResetPackage
  71    
  72    # If your PFX file requires a password then it can be set here, otherwise use a blank string.
  73    $password = "1234" 
  ```

Remplacez la valeur **FabrikamSEMMSample. pfx** de la variable **$certName** par le nom de votre fichier de certificat SEMM sur la ligne 58. Le script crée un répertoire de travail (nommé config) dans le dossier où se trouvent vos scripts, puis copie le fichier de certificat dans ce répertoire de travail.

Le package de propriétaire et le package de réinitialisation sont également créés dans le répertoire de configuration et contiennent la configuration pour les paramètres et les autorisations de surface UEFI générés par le script.

Sur la ligne 73, remplacez la valeur de la variable **$Password** , à partir de **1234** par le mot de passe de votre fichier de certificat. Si aucun mot de passe n’est requis, supprimez le texte **1234** .

> [!Note]
> Les deux derniers caractères de l’empreinte numérique du certificat sont requis pour inscrire un périphérique dans SEMM. Ce script affiche ces chiffres pour l’utilisateur, ce qui permet à l’utilisateur ou au technicien d’enregistrer ces chiffres avant que le système ne redémarre pour inscrire l’appareil dans SEMM. Le script utilise le code suivant, disponible sur les lignes 150-155, pour y parvenir.

```powershell
150 # Device owners will need the last two characters of the thumbprint to accept SEMM ownership.
151 # For convenience we get the thumbprint here and present to the user.
152 $pw = ConvertTo-SecureString $password -AsPlainText -Force
153 $certPrint = New-Object System.Security.Cryptography.X509Certificates.X509Certificate2
154 $certPrint.Import($privateOwnerKey, $pw, [System.Security.Cryptography.X509Certificates.X509KeyStorageFlags]::DefaultKeySet)
155 Write-Host "Thumbprint =" $certPrint.Thumbprint
```

Les administrateurs ayant accès au fichier de certificat (. pfx) peuvent lire l’empreinte numérique à tout moment en ouvrant le fichier. pfx dans CertMgr. Pour afficher l’empreinte numérique avec CertMgr, suivez ce processus:

1. Cliquez avec le bouton droit sur le fichier. pfx, puis sélectionnez **ouvrir**.
2. Développez le dossier dans le volet de navigation.
3. Sélectionnez **certificats**.
4. Cliquez avec le bouton droit sur votre certificat dans le volet principal, puis sélectionnez **ouvrir**.
5. Sélectionnez l’onglet **Détails** .
6. **Les** **Propriétés ne** doivent être sélectionnées que dans le menu déroulant **Afficher** .
7. Sélectionnez l' **empreinte**de champ.

> [!NOTE]
> Le nom et le mot de passe du certificat SEMM doivent également être entrés dans cette section du script de ResetSEMM.ps1 pour permettre à Configuration Manager de supprimer SEMM de l’appareil à l’aide de l’action de désinstallation.

### Configurer des autorisations

La première zone du script dans laquelle vous spécifiez la configuration de surface UEFI est la région **configurer les autorisations** . Cette région commence à la ligne 210 dans l’exemple de script avec le commentaire **# configurer les autorisations** et continuer à ligne 247. Le fragment de code suivant définit d’abord les autorisations d’accès à tous les paramètres de surface UEFI pour qu’il puisse être modifié par SEMM uniquement, puis ajoute des autorisations explicites pour permettre à l’utilisateur local de modifier le mot de passe, le TPM et les caméras avant et arrière de surface.

```powershell
210 # Configure Permissions
211 foreach ($uefiV2 IN $surfaceDevices.Values) {
212 if ($uefiV2.SurfaceUefiFamily -eq $Device.Model) {
213 Write-Host "Configuring permissions"
214 Write-Host $Device.Model
215 Write-Host "======================="
216
217 # Here we define which "identities" will be allowed to modify which settings
218 #   PermissionSignerOwner = The primary SEMM enterprise owner identity
219 #   PermissionLocal = The user when booting to the UEFI pre-boot GUI
220 #   PermissionSignerUser, PermissionSignerUser1, PermissionSignerUser2 =
221 #     Additional user identities created so that the signer owner
222 #     can delegate permission control for some settings.
223 $ownerOnly = [Microsoft.Surface.IUefiSetting]::PermissionSignerOwner
224 $ownerAndLocalUser = ([Microsoft.Surface.IUefiSetting]::PermissionSignerOwner -bor [Microsoft.Surface.IUefiSetting]::PermissionLocal)
225 
226 # Make all permissions owner only by default
227 foreach ($setting IN $uefiV2.Settings.Values) {
228 $setting.ConfiguredPermissionFlags = $ownerOnly
229 }
230 
231 # Allow the local user to change their own password
232 $uefiV2.SettingsById[501].ConfiguredPermissionFlags = $ownerAndLocalUser
233
234 Write-Host ""
235  
236 # Create a unique package name based on family and LSV.
237 # We will choose a name that can be parsed by later scripts.
238 $packageName = $uefiV2.SurfaceUefiFamily + "^Permissions^" + $lsv + ".pkg"
239 $fullPackageName = Join-Path -Path $packageRoot -ChildPath $packageName
240 
241 # Build and sign the Permission package then save it to a file.
242 $permissionPackageStream =  $uefiV2.BuildAndSignPermissionPackage($privateOwnerKey, $password, "", $null, $lsv)
243 $permissionPackage = New-Object System.IO.Filestream($fullPackageName, [System.IO.FileMode]::CreateNew, [System.IO.FileAccess]::Write)
244 $permissionPackageStream.CopyTo($permissionPackage)
245 $permissionPackage.Close()
246 }
247 }
```

Chaque variable **$uefiV 2** identifie un paramètre de surface UEFI en définissant Name ou ID, puis configure les autorisations sur l’une des valeurs suivantes:

* **$ownerOnly** – l’autorisation de modifier ce paramètre est accordée uniquement à SEMM.
* **$ownerAndLocalUser** – l’autorisation de modifier ce paramètre est accordée à un utilisateur local qui démarre sur la surface UEFI, ainsi qu’à SEMM.

Vous trouverez des informations sur les noms de paramètres disponibles et les ID de surface UEFI dans la section [noms et ID de paramètres](#settings-names-and-ids) de cet article.

### Configurer les paramètres

La deuxième zone du script dans laquelle vous spécifiez la configuration de surface UEFI est la région de configuration des **paramètres** du script de ConfigureSEMM.ps1, qui configure si chaque paramètre est activé ou désactivé. L’exemple de script inclut des instructions permettant de définir les valeurs par défaut de tous les paramètres. Le script fournit ensuite des instructions explicites pour désactiver le protocole IPv6 pour le démarrage PXE et ne modifie pas le mot de passe d’administrateur de surface UEFI. Vous pouvez trouver cette région à partir du commentaire **# configure Settings** à la ligne 291 à ligne 335 dans l’exemple de script. La région apparaît comme suit.

```powershell
291 # Configure Settings
292 foreach ($uefiV2 IN $surfaceDevices.Values) {
293 if ($uefiV2.SurfaceUefiFamily -eq $Device.Model) {
294 Write-Host "Configuring settings"
295 Write-Host $Device.Model
296 Write-Host "===================="
297
298 # In this demo, we will start by setting every setting to the default factory setting.
299 # You may want to start by doing this in your scripts
300 # so that every setting gets set to a known state.
301 foreach ($setting IN $uefiV2.Settings.Values) {
302 $setting.ConfiguredValue = $setting.DefaultValue
303 }
304 
305 $EnabledValue = "Enabled"
306 $DisabledValue = "Disabled"
307
308 # If you want to set something to a different value from the default,
309 # here are examples of how to accomplish this.
310 # This disables IPv6 PXE boot by name:
311 $uefiV2.Settings["IPv6 for PXE Boot"].ConfiguredValue = $DisabledValue
312
313 # This disables IPv6 PXE Boot by ID:
314 $uefiV2.SettingsById[400].ConfiguredValue = $DisabledValue
315
316 Write-Host ""
317
318 # If you want to leave the setting unmodified, set it to $null
319 # PowerShell has issues setting things to $null so ClearConfiguredValue()
320 # is supplied to do this explicitly.
321 # Here is an example of leaving the UEFI administrator password as-is,
322 # even after we initially set it to factory default above.
323 $uefiV2.SettingsById[501].ClearConfiguredValue()
324 
325 # Create a unique package name based on family and LSV.
326 # We will choose a name that can be parsed by later scripts.
327 $packageName = $uefiV2.SurfaceUefiFamily + "^Settings^" + $lsv + ".pkg"
328 $fullPackageName = Join-Path -Path $packageRoot -ChildPath $packageName
329 
330 # Build and sign the Settings package then save it to a file.
331 $settingsPackageStream =  $uefiV2.BuildAndSignSecuredSettingsPackage($privateOwnerKey, $password, "", $null, $lsv)
332 $settingsPackage = New-Object System.IO.Filestream($fullPackageName, [System.IO.FileMode]::CreateNew, [System.IO.FileAccess]::Write)
333 $settingsPackageStream.CopyTo($settingsPackage)
334 $settingsPackage.Close()
335 }
```

Comme les autorisations définies dans la section **configurer les autorisations** du script, la configuration de chaque paramètre de surface UEFI est effectuée en définissant la variable **$uefiV 2** . Pour chaque ligne définissant la variable **$uefiV 2** , un paramètre de surface UEFI est identifié par un nom de paramètre ou un ID et la valeur configurée est définie sur **activé** ou **désactivé**.

Si vous ne voulez pas modifier la configuration d’un paramètre de surface UEFI, par exemple pour vous assurer que le mot de passe d’administrateur de surface UEFI n’est pas supprimé en effectuant une action de réinitialisation de tous les paramètres de surface UEFI à sa valeur par défaut, vous pouvez utiliser **ClearConfiguredValue ()** pour appliquer ce paramètre ne sera pas modifié. Dans l’exemple de script, il est utilisé sur ligne 323 pour empêcher la suppression du mot de passe d’administrateur de surface UEFI, identifié dans l’exemple de script par son ID de paramètre, **501**.

Vous trouverez plus d’informations sur les noms de paramètres disponibles et les ID de surface UEFI dans la section [noms et ID des paramètres,](#settings-names-and-ids) plus loin dans cet article.

### Clé de Registre paramètres

Pour identifier les systèmes inscrits de Configuration Manager, le script ConfigureSEMM.ps1 écrit les clés de Registre qui peuvent être utilisées pour identifier les systèmes inscrits comme installés avec le script de configuration SEMM. Ces clés sont accessibles à l’emplacement suivant.

`HKLM\SOFTWARE\Microsoft\Surface\SEMM`

Le fragment de code suivant, qui se trouve sur les lignes 380-477, est utilisé pour écrire ces clés de registre.

```powershell
380 # For Endpoint Configuration Manager or other management solutions that wish to know what version is applied, tattoo the LSV and current DateTime (in UTC) to the registry:
381 $UTCDate = (Get-Date).ToUniversalTime().ToString()
382 $certIssuer = $certPrint.Issuer
383 $certSubject = $certPrint.Subject
384 
385 $SurfaceRegKey = "HKLM:\SOFTWARE\Microsoft\Surface\SEMM"
386 New-RegKey $SurfaceRegKey
387 $LSVRegValue = Get-ItemProperty $SurfaceRegKey LSV -ErrorAction SilentlyContinue
388 $DateTimeRegValue = Get-ItemProperty $SurfaceRegKey LastConfiguredUTC -ErrorAction SilentlyContinue
389 $OwnershipSessionIdRegValue = Get-ItemProperty $SurfaceRegKey OwnershipSessionId -ErrorAction SilentlyContinue
390 $PermissionSessionIdRegValue = Get-ItemProperty $SurfaceRegKey PermissionSessionId -ErrorAction SilentlyContinue
391 $SettingsSessionIdRegValue = Get-ItemProperty $SurfaceRegKey SettingsSessionId -ErrorAction SilentlyContinue
392 $IsResetRegValue = Get-ItemProperty $SurfaceRegKey IsReset -ErrorAction SilentlyContinue
393 $certUsedRegValue = Get-ItemProperty $SurfaceRegKey CertName -ErrorAction SilentlyContinue
394 $certIssuerRegValue = Get-ItemProperty $SurfaceRegKey CertIssuer -ErrorAction SilentlyContinue
395 $certSubjectRegValue = Get-ItemProperty $SurfaceRegKey CertSubject -ErrorAction SilentlyContinue
396 
397 
398 If ($LSVRegValue -eq $null)
399 {
400     New-ItemProperty -Path $SurfaceRegKey -Name LSV -PropertyType DWORD -Value $lsv | Out-Null
401 }
402 Else
403 {
404     Set-ItemProperty -Path $SurfaceRegKey -Name LSV -Value $lsv
405 }
406 
407 If ($DateTimeRegValue -eq $null)
408 {
409     New-ItemProperty -Path $SurfaceRegKey -Name LastConfiguredUTC -PropertyType String -Value $UTCDate | Out-Null
410 }
411 Else
412 {
413     Set-ItemProperty -Path $SurfaceRegKey -Name LastConfiguredUTC -Value $UTCDate
414 }
415 
416 If ($OwnershipSessionIdRegValue -eq $null)
417 {
418     New-ItemProperty -Path $SurfaceRegKey -Name OwnershipSessionId -PropertyType String -Value $ownerSessionIdValue | Out-Null
419 }
420 Else
421 {
422     Set-ItemProperty -Path $SurfaceRegKey -Name OwnershipSessionId -Value $ownerSessionIdValue
423 }
424 
425 If ($PermissionSessionIdRegValue -eq $null)
426 {
427     New-ItemProperty -Path $SurfaceRegKey -Name PermissionSessionId -PropertyType String -Value $permissionSessionIdValue | Out-Null
428 }
429 Else
430 {
431     Set-ItemProperty -Path $SurfaceRegKey -Name PermissionSessionId -Value $permissionSessionIdValue
432 }
433 
434 If ($SettingsSessionIdRegValue -eq $null)
435 {
436     New-ItemProperty -Path $SurfaceRegKey -Name SettingsSessionId -PropertyType String -Value $settingsSessionIdValue | Out-Null
437 }
438 Else
439 {
440     Set-ItemProperty -Path $SurfaceRegKey -Name SettingsSessionId -Value $settingsSessionIdValue
441 }
442 
443 If ($IsResetRegValue -eq $null)
444 {
445     New-ItemProperty -Path $SurfaceRegKey -Name IsReset -PropertyType DWORD -Value 0 | Out-Null
446 }
447 Else
448 {
449     Set-ItemProperty -Path $SurfaceRegKey -Name IsReset -Value 0
450 }
451 
452 If ($certUsedRegValue -eq $null)
453 {
454     New-ItemProperty -Path $SurfaceRegKey -Name CertName -PropertyType String -Value $certName | Out-Null
455 }
456 Else
457 {
458     Set-ItemProperty -Path $SurfaceRegKey -Name CertName -Value $certName
459 }
460 
461 If ($certIssuerRegValue -eq $null)
462 {
463     New-ItemProperty -Path $SurfaceRegKey -Name CertIssuer -PropertyType String -Value $certIssuer | Out-Null
464 }
465 Else
466 {
467     Set-ItemProperty -Path $SurfaceRegKey -Name CertIssuer -Value $certIssuer
468 }
469 
470 If ($certSubjectRegValue -eq $null)
471 {
472     New-ItemProperty -Path $SurfaceRegKey -Name CertSubject -PropertyType String -Value $certSubject | Out-Null
473 }
474 Else
475 {
476     Set-ItemProperty -Path $SurfaceRegKey -Name CertSubject -Value $certSubject
477 }
```

### ID et noms de paramètres

Pour configurer les paramètres ou les autorisations de surface UEFI pour les paramètres de surface UEFI, vous devez faire référence à chaque paramètre en utilisant son nom de paramètre ou son ID de paramètre. Avec chaque nouvelle mise à jour de surface UEFI, de nouveaux paramètres pourront être ajoutés. Le meilleur moyen d’obtenir une liste complète des paramètres disponibles sur un appareil surface, ainsi que les paramètres de nom et d’ID de paramètres, consiste à utiliser le script ShowSettingsOptions.ps1 de SEMM_Powershell.zip dans les [Outils surface pour les télécharger](https://www.microsoft.com/download/details.aspx?id=46703) . 

Le Gestionnaire Microsoft surface UEFI doit être installé sur l’ordinateur sur lequel ShowSettingsOptions.ps1 est exécuté; il n’est pas nécessaire d’avoir un appareil surface.


## Déploiement de SEMM Configuration Manager scripts

Après avoir préparé vos scripts pour configurer et activer SEMM sur l’appareil client, l’étape suivante consiste à ajouter ces scripts en tant qu’application dans Configuration Manager. Avant d’ouvrir Configuration Manager, vérifiez que les fichiers suivants se trouvent dans un dossier partagé qui n’inclut pas d’autres fichiers:

* ConfigureSEMM.ps1
* ResetSEMM.ps1
* Votre certificat SEMM (par exemple, SEMMCertificate. pfx);

Les scripts du gestionnaire de configuration SEMM seront ajoutés à Configuration Manager en tant qu’application de script. La commande permettant d’installer SEMM avec ConfigureSEMM.ps1 est la suivante.

`Powershell.exe -file ".\ConfigureSEMM.ps1"`

La commande permettant de désinstaller SEMM avec ResetSEMM.ps1 est la suivante.

`Powershell.exe -file ".\ResetSEMM.ps1"`

Pour ajouter les scripts du gestionnaire de configuration SEMM dans Configuration Manager en tant qu’application, procédez comme suit:

1. Démarrez l’Assistant Création d’une application en suivant les étapes 1 à 5 de la section [déployer Microsoft surface UEFI Manager](#deploy-microsoft-surface-uefi-manager) plus haut dans cet article.

2. Suivez les étapes de l’Assistant Création d’une application en procédant comme suit:

   - **Général** : sélectionnez **spécifier manuellement les informations de l’application**, puis sélectionnez **suivant**.

   - **Informations générales** : entrez un nom pour l’application (par exemple SEMM), ainsi que toute autre information de votre choix (par exemple, Publisher, version ou commentaires). Sélectionnez **Next (suivant** ) pour continuer.

   - **Catalogue d’applications** : les champs de cette page peuvent être laissés avec leurs valeurs par défaut. Sélectionnez **Suivant**.

   - **Types de déploiement** : sélectionnez **Ajouter** pour démarrer l’Assistant Création d’un type de déploiement.

   - Suivez les étapes de l’Assistant Création d’un type de déploiement, comme suit:

     * **Général** : sélectionnez **programme d’installation de script** dans le menu déroulant **type** . L’option **spécifier manuellement les informations de type de déploiement** sera sélectionnée automatiquement. Sélectionnez **Next (suivant** ) pour continuer.
     * **Informations générales** : entrez un nom pour le type de déploiement (par exemple, scripts de configuration SEMM), puis sélectionnez **suivant** pour continuer.
     * **Contenu** : sélectionnez **Parcourir** en regard du champ d' **emplacement du contenu** , puis sélectionnez le dossier dans lequel se trouvent les scripts de votre gestionnaire de configuration SEMM. Dans le champ **programme d’installation** , tapez la commande d' [installation](#deploy-semm-configuration-manager-scripts) qui est abordée plus haut dans cet article. Dans le champ désinstaller le **programme** , entrez la [commande de désinstallation](#deploy-semm-configuration-manager-scripts) qui est décrite plus haut dans cet article (illustré dans la figure 2). Sélectionnez **suivant** pour passer à la page suivante.
    
     ![Définissez les scripts du gestionnaire de configuration SEMM comme commandes installer et désinstaller](images/config-mgr-semm-fig2.png "Set the SEMM Configuration Manager scripts as the install and uninstall commands")

     *Figure2. Définissez les scripts du gestionnaire de configuration SEMM comme commandes installer et désinstaller*

     * **Méthode de détection** : sélectionnez **Ajouter une clause** pour ajouter la règle de détection de clé de Registre du gestionnaire de configuration SEMM. La fenêtre **règle de détection** s’affiche, comme illustré dans la figure 3. Utilisez les paramètres suivants:

       - Dans le menu déroulant **type de paramètre** , sélectionnez **Registre** .
       - Dans le menu déroulant **Hive** , sélectionnez **HKEY_LOCAL_MACHINE** .
       - Entrez **SOFTWARE\Microsoft\Surface\SEMM** dans le champ **clé** .
       - Entrez **CertName** dans le champ **valeur** .
       - Dans le menu déroulant **type de données** , sélectionnez **chaîne** .
       - Sélectionnez **ce paramètre de registre doit respecter les règles suivantes pour indiquer la présence de ce bouton d’application** .
       - Entrez le nom du certificat que vous avez entré dans la ligne 58 du script dans le champ **valeur** .
       - Sélectionnez **OK** pour fermer la fenêtre **règle de détection** .

     ![Utiliser une clé de Registre pour identifier les appareils inscrits dans SEMM](images/config-mgr-semm-fig3.png "Use a registry key to identify devices enrolled in SEMM")
     
     *Figure3. Utiliser une clé de Registre pour identifier les appareils inscrits dans SEMM*

     * Sélectionnez **suivant** pour passer à la page suivante.
     
     * **Interface utilisateur** : dans le menu déroulant **comportement d’installation** , sélectionnez **installer pour le système** . Si vous souhaitez que vos utilisateurs puissent enregistrer et entrer l’empreinte numérique du certificat, ne définissez aucune obligation de connexion **uniquement lorsqu’un utilisateur est connecté**. Si vous voulez permettre aux administrateurs d’entrer l’empreinte numérique des utilisateurs et que les utilisateurs n’ont pas besoin de voir leur empreinte, sélectionnez **si l’utilisateur est connecté** à partir du menu déroulant **exigences de connexion** .

     * **Configuration requise** : le script de ConfigureSEMM.ps1 vérifie automatiquement que l’appareil est un appareil surface avant d’essayer d’activer SEMM. Toutefois, si vous envisagez de déployer cette application de script sur une collection dont les appareils ne sont pas à gérer avec SEMM, vous pouvez ajouter des spécifications ici pour vous assurer que cette application ne s’exécute que sur les appareils à surface ou les appareils que vous souhaitez gérer avec SEMM. Sélectionnez **Next (suivant** ) pour continuer.
     
     * **Dépendances** : sélectionnez **Ajouter** pour ouvrir la fenêtre **Ajouter une dépendance** .

       * Sélectionnez **Ajouter** pour ouvrir la fenêtre **spécifier l’application requise** .

          - Entrez un nom pour les dépendances SEMM dans le champ **nom du groupe de dépendances** (par exemple, *assemblys SEMM*).

          - Sélectionnez **Microsoft surface UEFI Manager** dans la liste des **applications disponibles** et le type de déploiement MSI, puis sélectionnez **OK** pour fermer la fenêtre **spécifier l’application requise** .
          
         *   Laissez la case à cocher **installation automatique** sélectionnée si vous voulez que le Gestionnaire Microsoft surface UEFI soit installé automatiquement sur les appareils lorsque vous tentez d’activer SEMM avec les scripts du gestionnaire de configuration. Sélectionnez **OK** pour fermer la fenêtre **Ajouter une dépendance** .

     * Sélectionnez **Next (suivant** ) pour continuer.
     
     * **Résumé** : les informations que vous avez entrées dans l’Assistant Création d’un type de déploiement s’affichent dans cette page. Pour confirmer vos sélections, sélectionnez **Next (suivant** ).
     
     * **Progression** : une barre de progression et un statut en tant que type de déploiement est ajouté pour l’application script SEMM est affiché dans cette page.
     
     * **Achèvement** : la confirmation de la création du type de déploiement s’affiche lorsque le processus est terminé. Sélectionnez **Fermer** pour terminer l’Assistant Création d’un type de déploiement.

   - **Résumé** : les informations que vous avez entrées dans l’Assistant Création d’une application apparaissent. Sélectionnez **suivant** pour créer l’application.

   - **Progression** : une barre de progression et un statut au fur et à mesure de l’ajout de l’application à la bibliothèque logicielle apparaissent sur cette page.

   - **Achèvement** : la confirmation de la création de l’application réussie s’affiche lorsque le processus de création d’application est terminé. Sélectionnez **Fermer** pour terminer l’Assistant Création d’une application.

Une fois l’application de script disponible dans la bibliothèque de logiciels de Configuration Manager, vous pouvez distribuer et déployer SEMM en utilisant les scripts que vous avez préparés pour les appareils ou collections. Si vous avez configuré les assemblys Microsoft surface UEFI Manager en tant que dépendance qui sera installée automatiquement, vous pouvez déployer SEMM en une seule étape. Si vous n’avez pas configuré les assemblys en tant que dépendance, ils doivent être installés sur les appareils que vous envisagez de gérer avant d’activer SEMM.

Lorsque vous déployez SEMM à l’aide de cette application de script et d’une configuration qui est visible à l’utilisateur final, le script PowerShell démarre et l’empreinte numérique du certificat s’affiche dans la fenêtre PowerShell. Vous pouvez faire en sorte que vos utilisateurs enregistrent cette empreinte digitale et l’entrer lorsque vous y êtes invité par surface UEFI après le redémarrage de l’appareil.

Par ailleurs, vous pouvez configurer l’installation de l’application pour qu’elle redémarre automatiquement et qu’elle s’installe de façon transparente pour l’utilisateur. Dans ce scénario, un technicien sera tenu d’entrer l’empreinte numérique de chaque appareil au fur et à mesure de son redémarrage. Tout technicien ayant accès au fichier de certificat peut lire l’empreinte numérique en affichant le certificat avec CertMgr. Les instructions pour afficher l’empreinte numérique avec CertMgr se trouvent dans la section [créer ou modifier les scripts du gestionnaire de configuration SEMM](#create-or-modify-the-semm-configuration-manager-scripts) de cet article.

La suppression de SEMM à partir d’un appareil déployé avec Configuration Manager à l’aide de ces scripts est aussi simple que la désinstallation de l’application avec Configuration Manager. Cette action démarre le script ResetSEMM.ps1 et désinscrit correctement l’appareil avec le même fichier de certificat que celui utilisé lors du déploiement de SEMM.

> [!NOTE]
> Microsoft surface recommande de créer des packages de réinitialisation uniquement lorsque vous avez besoin d’annuler l’inscription d’un appareil. Ces packages de réinitialisation sont généralement valides pour un seul appareil et identifiés par leur numéro de série. En revanche, vous pouvez créer un package de réinitialisation universel qui fonctionne pour tous les appareils inscrits dans SEMM avec ce certificat.
> 
> Nous vous recommandons vivement de protéger votre package de réinitialisation universelle comme le certificat que vous avez utilisé pour inscrire des appareils dans SEMM. N’oubliez pas que, comme le certificat lui-même, ce package de réinitialisation universelle peut être utilisé pour annuler l’inscription de n’importe quel appareil surface de votre organisation à partir de SEMM.
> 
> Lorsque vous installez un package de réinitialisation, la valeur la plus basse prise en charge (LSV) est redéfinie sur 1. Vous pouvez réinscrire un appareil à l’aide d’un package de configuration existant. L’appareil vous invitera à entrer l’empreinte du certificat avant la prise de la propriété.
> 
> C’est la raison pour laquelle la réinscription d’un appareil dans SEMM nécessite la création et l’installation d’un nouveau package sur cet appareil. Dans la mesure où cette action est une nouvelle inscription et pas une modification de la configuration sur un appareil déjà inscrit dans SEMM, l’appareil vous invite à entrer l’empreinte du certificat avant la prise de la propriété.
