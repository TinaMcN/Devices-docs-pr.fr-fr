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
# Outil étiquette surface Asset

La balise surface Asset est un utilitaire d’interface de ligne de commande qui vous permet d’afficher, d’affecter et de modifier une valeur d’étiquette d’élément affectée pour les appareils surface. Il fonctionne sur surface Pro 3 et sur tous les appareils surface plus récents.

## Configuration requise

- Surface Pro 3 ou version ultérieure

- 3.9.150.0 ou version ultérieure du microprogramme UEFI

## Utilisation de la balise Asset surface 

Pour exécuter la balise d’élément de surface:

1.  Sur l’appareil surface, téléchargez le **Tag.zipde ressources de surface** à partir du centre de [téléchargement Microsoft](https://www.microsoft.com/download/details.aspx?id=46703), extrayez le fichier zip et enregistrez AssetTag.exe dans le dossier souhaité (dans cet exemple, C:\\assets).

    > [!NOTE]
    > Pour surface Pro X, utilisez l’application nommée **AssetTag_x86** dans le fichier zip. 

2.  Ouvrez une console de commandes en tant qu’administrateur, exécutez AssetTag.exe, en entrant le chemin complet de l’outil.

3.  Redémarrez surface.

### Commandes de l’outil étiquette de ressource   
Dans les exemples suivants, AssetTag.exe est enregistré dans un répertoire sur un ordinateur local (C:\assets). 

Pour obtenir la balise d’élément proposée, exécutez AssetTag-g.

**Exemple**

   ```
 C:\assets\AssetTag.exe -g
  ```
 
 Pour effacer la balise de ressources proposées, exécutez AssetTag-s.
 
 **Exemple**
 
   ```
C:\assets\AssetTag.exe -s
  ```
Pour définir la balise de ressources proposées, exécutez AssetTag-s testassettag12.

**Exemple**

```
C:\assets\AssetTag.exe -s testassettag12
```

>[!NOTE]
>La valeur de la balise Asset doit contenir entre 1 et 36 caractères. Les caractères valides incluent A-Z, a-z, 0-9, point (.) et trait d’Union (-).


## Gestion des indicateurs de ressources

Vous pouvez afficher la balise de ressource existante dans les paramètres UEFI sous informations sur l’appareil (**panneau de configuration > restauration > démarrage avancée > redémarrer maintenant**.)

La figure ci-dessous montre les résultats obtenus lors de l’exécution de l’outil étiquette de ressource sur surface Go.

![Résultats de l’exécution de l’outil d’étiquette de surface de surface dans surface Go.
](images/assettag-fig1.png)

> **Figure1.** Résultats de l’exécution de l’outil d’étiquette de surface de surface dans surface Go

Vous pouvez également utiliser WMI pour interroger la balise de ressource existante sur un appareil:

(Get-WmiObject-query "Select * from Win32_SystemEnclosure")

**Exemple**

   ```
C:\Windows\System32> (Get-WmiObject -query “Select * from Win32_SystemEnclosure”)
  ```
  
### Avec PowerShell

Vous pouvez utiliser le script ci-dessous pour obtenir la valeur proposée et interpréter les erreurs éventuelles.

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
