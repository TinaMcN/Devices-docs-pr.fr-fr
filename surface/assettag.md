---
title: Outil étiquette surface Asset
description: Cette rubrique explique comment utiliser l’outil balise surface Asset.
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: hachidan
manager: laurawi
ms.openlocfilehash: ca6a71a6b864692953fcd96eb687c2752527c9f5
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832579"
---
# <span data-ttu-id="58a5a-103">Outil étiquette surface Asset</span><span class="sxs-lookup"><span data-stu-id="58a5a-103">Surface Asset Tag Tool</span></span>

<span data-ttu-id="58a5a-104">La balise surface Asset est un utilitaire d’interface de ligne de commande qui vous permet d’afficher, d’affecter et de modifier une valeur d’étiquette d’élément affectée pour les appareils surface.</span><span class="sxs-lookup"><span data-stu-id="58a5a-104">Surface Asset Tag is a command line interface (CLI) utility that allows you to view, assign, and modify an assigned asset tag value for Surface devices.</span></span> <span data-ttu-id="58a5a-105">Il fonctionne sur surface Pro 3 et sur tous les appareils surface plus récents.</span><span class="sxs-lookup"><span data-stu-id="58a5a-105">It works on Surface Pro 3 and all newer Surface devices.</span></span>

## <span data-ttu-id="58a5a-106">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="58a5a-106">System requirements</span></span>

- <span data-ttu-id="58a5a-107">Surface Pro 3 ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="58a5a-107">Surface Pro 3 or later</span></span>

- <span data-ttu-id="58a5a-108">3.9.150.0 ou version ultérieure du microprogramme UEFI</span><span class="sxs-lookup"><span data-stu-id="58a5a-108">UEFI firmware version 3.9.150.0 or later</span></span>

## <span data-ttu-id="58a5a-109">Utilisation de la balise Asset surface</span><span class="sxs-lookup"><span data-stu-id="58a5a-109">Using Surface Asset Tag</span></span> 

<span data-ttu-id="58a5a-110">Pour exécuter la balise d’élément de surface:</span><span class="sxs-lookup"><span data-stu-id="58a5a-110">To run Surface Asset Tag:</span></span>

1.  <span data-ttu-id="58a5a-111">Sur l’appareil surface, téléchargez le **Tag.zipde ressources de surface** à partir du centre de [téléchargement Microsoft](https://www.microsoft.com/download/details.aspx?id=46703), extrayez le fichier zip et enregistrez AssetTag.exe dans le dossier souhaité (dans cet exemple, C:\\assets).</span><span class="sxs-lookup"><span data-stu-id="58a5a-111">On the Surface device, download **Surface Asset Tag.zip** from the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=46703), extract the zip file, and save AssetTag.exe in desired folder (in this example, C:\\assets).</span></span>

    > [!NOTE]
    > <span data-ttu-id="58a5a-112">Pour surface Pro X, utilisez l’application nommée **AssetTag_x86** dans le fichier zip.</span><span class="sxs-lookup"><span data-stu-id="58a5a-112">For Surface Pro X, use the application named **AssetTag_x86**  in the ZIP file.</span></span> 

2.  <span data-ttu-id="58a5a-113">Ouvrez une console de commandes en tant qu’administrateur, exécutez AssetTag.exe, en entrant le chemin complet de l’outil.</span><span class="sxs-lookup"><span data-stu-id="58a5a-113">Open a command console as an Administrator and run AssetTag.exe, entering the full path to the tool.</span></span>

3.  <span data-ttu-id="58a5a-114">Redémarrez surface.</span><span class="sxs-lookup"><span data-stu-id="58a5a-114">Restart Surface.</span></span>

### <span data-ttu-id="58a5a-115">Commandes de l’outil étiquette de ressource</span><span class="sxs-lookup"><span data-stu-id="58a5a-115">Asset Tag tool commands</span></span>   
<span data-ttu-id="58a5a-116">Dans les exemples suivants, AssetTag.exe est enregistré dans un répertoire sur un ordinateur local (C:\assets).</span><span class="sxs-lookup"><span data-stu-id="58a5a-116">In the following examples, AssetTag.exe is saved in a directory on a local machine (C:\assets).</span></span> 

<span data-ttu-id="58a5a-117">Pour obtenir la balise d’élément proposée, exécutez AssetTag-g.</span><span class="sxs-lookup"><span data-stu-id="58a5a-117">To get the proposed asset tag, run AssetTag -g.</span></span>

**<span data-ttu-id="58a5a-118">Exemple</span><span class="sxs-lookup"><span data-stu-id="58a5a-118">Example</span></span>**

   ```
 C:\assets\AssetTag.exe -g
  ```
 
 <span data-ttu-id="58a5a-119">Pour effacer la balise de ressources proposées, exécutez AssetTag-s.</span><span class="sxs-lookup"><span data-stu-id="58a5a-119">To clear the proposed asset tag, run AssetTag -s.</span></span>
 
 **<span data-ttu-id="58a5a-120">Exemple</span><span class="sxs-lookup"><span data-stu-id="58a5a-120">Example</span></span>**
 
   ```
C:\assets\AssetTag.exe -s
  ```
<span data-ttu-id="58a5a-121">Pour définir la balise de ressources proposées, exécutez AssetTag-s testassettag12.</span><span class="sxs-lookup"><span data-stu-id="58a5a-121">To set the proposed asset tag, run AssetTag -s testassettag12.</span></span>

**<span data-ttu-id="58a5a-122">Exemple</span><span class="sxs-lookup"><span data-stu-id="58a5a-122">Example</span></span>**

```
C:\assets\AssetTag.exe -s testassettag12
```

>[!NOTE]
><span data-ttu-id="58a5a-123">La valeur de la balise Asset doit contenir entre 1 et 36 caractères.</span><span class="sxs-lookup"><span data-stu-id="58a5a-123">The asset tag value must contain between 1 and 36 characters.</span></span> <span data-ttu-id="58a5a-124">Les caractères valides incluent A-Z, a-z, 0-9, point (.) et trait d’Union (-).</span><span class="sxs-lookup"><span data-stu-id="58a5a-124">Valid characters include A-Z, a-z, 0-9, period (.) and hyphen (-).</span></span>


## <span data-ttu-id="58a5a-125">Gestion des indicateurs de ressources</span><span class="sxs-lookup"><span data-stu-id="58a5a-125">Managing asset tags</span></span>

<span data-ttu-id="58a5a-126">Vous pouvez afficher la balise de ressource existante dans les paramètres UEFI sous informations sur l’appareil (**panneau de configuration > restauration > démarrage avancée > redémarrer maintenant**.)</span><span class="sxs-lookup"><span data-stu-id="58a5a-126">You can view the existing asset tag in the UEFI settings under Device Information (**Control Panel > Recovery > Advanced Startup > Restart now**.)</span></span>

<span data-ttu-id="58a5a-127">La figure ci-dessous montre les résultats obtenus lors de l’exécution de l’outil étiquette de ressource sur surface Go.</span><span class="sxs-lookup"><span data-stu-id="58a5a-127">The figure below shows the results of running the Asset Tag Tool on Surface Go.</span></span>

![<span data-ttu-id="58a5a-128">Résultats de l’exécution de l’outil d’étiquette de surface de surface dans surface Go.</span><span class="sxs-lookup"><span data-stu-id="58a5a-128">Results of running Surface Asset Tag tool on Surface Go.</span></span>
](images/assettag-fig1.png)

> **<span data-ttu-id="58a5a-129">Figure1.</span><span class="sxs-lookup"><span data-stu-id="58a5a-129">Figure 1.</span></span>** <span data-ttu-id="58a5a-130">Résultats de l’exécution de l’outil d’étiquette de surface de surface dans surface Go</span><span class="sxs-lookup"><span data-stu-id="58a5a-130">Results of running Surface Asset Tag tool on Surface Go</span></span>

<span data-ttu-id="58a5a-131">Vous pouvez également utiliser WMI pour interroger la balise de ressource existante sur un appareil:</span><span class="sxs-lookup"><span data-stu-id="58a5a-131">Alternately, you can use WMI to query the existing asset tag on a device:</span></span>

<span data-ttu-id="58a5a-132">(Get-WmiObject-query "Select \* from Win32_SystemEnclosure")</span><span class="sxs-lookup"><span data-stu-id="58a5a-132">(Get-WmiObject -query “Select \* from Win32_SystemEnclosure”)</span></span>

**<span data-ttu-id="58a5a-133">Exemple</span><span class="sxs-lookup"><span data-stu-id="58a5a-133">Example</span></span>**

   ```
C:\Windows\System32> (Get-WmiObject -query “Select * from Win32_SystemEnclosure”)
  ```
  
### <span data-ttu-id="58a5a-134">Avec PowerShell</span><span class="sxs-lookup"><span data-stu-id="58a5a-134">Using PowerShell</span></span>

<span data-ttu-id="58a5a-135">Vous pouvez utiliser le script ci-dessous pour obtenir la valeur proposée et interpréter les erreurs éventuelles.</span><span class="sxs-lookup"><span data-stu-id="58a5a-135">You can use the script below as a way of getting the proposed value and interpreting any errors.</span></span>

 ```
AssetTag -g \> $asset\_tag 2\> $error\_message  
$asset\_tag\_return\_code = $LASTEXITCODE  
$asset\_tag = $asset\_tag.Trim(“\`r\`n”)

if ($asset\_tag\_return\_code -eq 0) {  
Write-Output (“Good Tag = ” + $asset\_tag)  
} else {  
Write-Output (  
“Failure: Code = ” + $asset\_tag\_return\_code +  
“Tag = ” + $asset\_tag +  
“Message = ” + $error\_message)

}
 ```
