---
title: Créer des packages de configuration pour SurfaceHub2S
description: Cette page décrit le déploiement de surface Hub 2 à l’aide des packages de mise en service et d’autres outils.
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
ms.openlocfilehash: 8f91b751a10977d80210d10ac1b48a93d9ba0f6f
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10834186"
---
# Créer des packages de configuration pour SurfaceHub2S

Vous pouvez utiliser le concepteur de configuration Windows (WCD) pour créer des packages de mise en service pour automatiser le processus de déploiement de surface Hub 2. Utiliser les packages de mise en service pour ajouter des certificats, configurer des proxys, configurer des administrateurs d’appareils et des comptes de périphériques. Vous pouvez également utiliser les packages de mise en service avec un fichier de configuration pour déployer plusieurs hubs surface avec une seule clé USB.

### Installer le Concepteur de configuration Windows

Installez l’éditeur de configuration Windows à partir du kit d’évaluation et de déploiement Windows (ADK) pour Windows 10. Téléchargez et installez la [version ADK pour Windows 10, version 1703](https://go.microsoft.com/fwlink/p/?LinkId=845542). Pour plus d’informations, reportez-vous à [Télécharger et installer Windows ADK](https://docs.microsoft.com/windows-hardware/get-started/adk-install).

### Ajouter des certificats

Vous pouvez importer des certificats d’autorité de certification sur surface Hub 2.
Pour ajouter des certificats à surface Hub 2, vous avez besoin d’une copie de chaque certificat en tant que X. 509 au format. cer. Vous ne pouvez pas importer. CRT,. pfx ou d’autres formats de conteneur. Les certificats doivent être importés dans le concepteur de configuration Windows et organisés par hiérarchie:

 ![Ajouter des certificats](images/sh2-wcd.png)

### Configurer le proxy lors de l’OOBE

Dans le concepteur de configuration Windows, accédez à l’onglet configurer les paramètres du proxy et entrez les paramètres appropriés, comme illustré ci-dessous.

 ![Configurer les paramètres de proxy](images/sh2-proxy.png) 

> [!NOTE]
> Lorsque vous configurez les paramètres de proxy, désactivez l’option **détecter automatiquement les paramètres** de connexion si vous envisagez d’utiliser un script de configuration ou un serveur proxy. Vous pouvez utiliser un script de configuration *ou* un serveur proxy, et non les deux.

### Centre d’affiliation surface Hub 2 avec Azure Active Directory

Vous pouvez affilier surface Hub 2 avec Azure Active Directory à l’aide d’un package de mise à niveau: en tant qu’administrateur général Azure Active Directory, vous pouvez rejoindre un grand nombre de nouveaux appareils Windows sur Azure Active Directory et Intune en utilisant un jeton de bloc.

Pour créer un jeton de bloc, donnez-lui un nom convivial, configurez la date d’expiration (maximale de 30 jours) et utilisez vos informations d’identification d’administrateur pour acquérir le jeton, comme illustré ci-dessous:

 ![Configurer des administrateurs d’appareils](images/sh2-token.png) <br><br>
 ![Configurer des administrateurs d’appareils](images/sh2-token2.png) <br><br>
 ![Configurer des administrateurs d’appareils](images/sh2-token3.png) <br><br>

### Attribution de plusieurs appareils (fichier. csv)

Outre le package de mise en service, vous pouvez utiliser un fichier de configuration surface Hub pour faciliter la configuration de vos appareils. Un fichier de configuration surface hub contient une liste de comptes de périphériques et de noms conviviaux pour la projection sans fil. Lors de la première exécution, vous avez la possibilité de choisir un compte d’appareil et un nom convivial à partir d’un fichier de configuration.

### Pour créer un fichier de configuration surface Hub

1. À l’aide de Microsoft Excel ou d’un autre éditeur de fichiers CSV, créez un fichier CSV intitulé: **SurfaceHubConfiguration.csv**
2. Entrez dans ce format une liste de comptes d’appareils et de noms conviviaux:

```
<DeviceAccountName>,<DeviceAccountPassword>,<FriendlyName>
```

3. Enregistrez le fichier à la racine du lecteur USB dans lequel vous avez copié le fichier PPKG.

    ![Exemple de fichier de configuration](images/sh2-config-file.png)
