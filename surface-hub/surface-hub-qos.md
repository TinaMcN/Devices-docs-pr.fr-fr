---
title: Mettre en œuvre la qualité de service sur SurfaceHub
ms.reviewer: ''
manager: laurawi
description: Apprenez à configurer la qualité de service (QoS) sur surface Hub.
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: 99172e77be260559c770f5fc8a1438734bed660f
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832910"
---
# Mettre en œuvre la qualité de service (QoS) sur surface Hub

La qualité de service (QoS) est une combinaison de technologies réseau qui permet aux administrateurs d’optimiser l’utilisation de communications audio/vidéo et de partage d’application en temps réel.
 
La configuration [de la qualité de service (QoS) pour Skype entreprise](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp) sur surface Hub peut être réalisée à l’aide de votre [fournisseur de gestion des périphériques mobiles (GPM)](manage-settings-with-mdm-for-surface-hub.md) ou d’un [package de mise](provisioning-packages-for-surface-hub.md)à niveau. 
 
 
Cette procédure vous explique comment configurer la qualité de service (QoS) pour surface Hub à l’aide de Microsoft Intune. 

1. Dans Intune, [créez une stratégie personnalisée](https://docs.microsoft.com/intune/custom-settings-configure).

    ![Capture d’écran de la boîte de dialogue de création d’une stratégie personnalisée dans Intune](images/qos-create.png)

2. Dans **les paramètres d’URI OMA personnalisés**, sélectionnez **Ajouter**. Pour chaque paramètre que vous ajoutez, vous devez entrer un nom, une description (facultatif), un type de données, un URI OMA et une valeur.

    ![Capture d’écran de la boîte de dialogue paramètre d’URI OMA vide](images/qos-setting.png)

3. Ajoutez les paramètres d’URI OMA personnalisés suivants:

    Nom | Type de données | OMA-URI<br>./Device/Vendor/MSFT/NetworkQoSPolicy |  Valeur
    --- | --- | --- | ---
    Port source audio | String |  /HubAudio/SourcePortMatchCondition  |   Obtenez les valeurs de votre administrateur Skype
    Valeur DSCP de l’audio | Integer |  /HubAudio/DSCPAction  |   46
    Port source vidéo | String |  /HubVideo/SourcePortMatchCondition   |  Obtenez les valeurs de votre administrateur Skype
    Valeur DSCP de la vidéo | Integer |  /HubVideo/DSCPAction   |   34
    Nom du processus audio | String |  /HubAudio/AppPathNameMatchCondition  |   Microsoft.PPISkype.Windows.exe
    Nom de processus vidéo | String |  /HubVideo/AppPathNameMatchCondition  |   Microsoft.PPISkype.Windows.exe

    >[!IMPORTANT]
    >Chaque chemin d’accès de l' **URI OMA** commence par `./Device/Vendor/MSFT/NetworkQoSPolicy` . Le chemin d’accès complet du paramètre de port source audio, par exemple, sera `./Device/Vendor/MSFT/NetworkQoSPolicy/HubAudio/SourcePortMatchCondition` .




4. Lorsque la stratégie a été créée, [déployez-la sur surface Hub.](manage-settings-with-mdm-for-surface-hub.md#manage-surface-hub-settings-with-mdm)


>[!WARNING]
>Pour le moment, vous ne pouvez pas configurer le paramètre **IPProtocolMatchCondition** dans le [CSP NetworkQoSPolicy](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp). Si ce paramètre est configuré, la stratégie ne sera pas appliquée.
 
