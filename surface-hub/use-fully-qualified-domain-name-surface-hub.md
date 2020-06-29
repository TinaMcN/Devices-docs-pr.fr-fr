---
title: Utiliser un nom de domaine complet avec le SurfaceHub
description: Résolvez les problèmes courants, notamment les problèmes d’installation et les erreurs ExchangeActiveSync.
keywords:
- Résoudre les problèmes courants
- problèmes d’installation
- Erreurs ExchangeActiveSync
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.prod: surface-hub
ms.sitesec: library
ms.openlocfilehash: 79507f5b4bb22b23d1e6c4db6b4aab6ea891d876
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832657"
---
# Configurer un nom de domaine pour SkypeEntreprise

Quelques scénarios impliquent que vous deviez spécifier le nom de domaine de votre serveur SkypeEntreprise:
- **Plusieurs suffixes DNS**: lorsque votre infrastructure SkypeEntreprise comporte des espaces de noms disjoints, de sorte qu’un ou plusieurs serveurs présentent un suffixe DNS différent du suffixe de l’adresse de connexion de SkypeEntreprise.  
- **Suffixes SkypeEntreprise différents des suffixes Exchange**: lorsque le suffixe de l’adresse de connexion de SkypeEntreprise diffère de celui de l’adresse Exchange utilisée pour le compte d’appareil.
- L' **utilisation de certificats** (organisations de grande taille avec des serveurs Skype entreprise locaux utilisent fréquemment des certificats avec leur propre autorité de certification racine). Il est courant que le domaine de l’autorité de certification diffère du domaine du serveur SkypeEntreprise, ce qui entraîne la non-approbation du certificat, et donc l’échec de la connexion.  Skype doit connaître le nom de domaine du certificat pour configurer une relation d’approbation. Les entreprises utilisent généralement une stratégie de groupe pour transmettre cette information à l’application de bureau Skype, mais les stratégies de groupe ne sont pas prises en charge sur le SurfaceHub.

**Pour configurer le nom de domaine de votre serveur SkypeEntreprise:**</br>
1. Sur le SurfaceHub, ouvrez **Paramètres**.
2. Cliquez sur **Surface Hub**, puis cliquez sur **Appel et Audio**. 
3. Sous **Configuration de SkypeEntreprise**, cliquez sur **Configurer le nom de domaine**. 
4. Tapez le nom de domaine de votre serveur SkypeEntreprise, puis cliquez sur **OK**. 
   > [!TIP]
   > Vous pouvez taper plusieurs noms de domaine en les séparant par une virgule. <br> Exemple: lync.com, outlook.com, lync.glbdns.microsoft.com.

    ![Ajouter un nom de domaine complet Skype entreprise aux paramètres](images/system-settings-add-fqdn.png)
