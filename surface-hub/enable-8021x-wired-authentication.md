---
title: Activer l’authentification 802.1x câblée
description: Les stratégies GPM d'authentification filaire802.1x ont été activées sur les appareils Surface Hub.
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 11/15/2017
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: 119f879d74ccda5d53da27d842413346a50693f1
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10833707"
---
# Activer l'authentification filaire802.1x

La [mise à jour vers Windows10 du 14 novembre2017](https://support.microsoft.com/help/4048954/windows-10-update-kb4048954) (build15063.726) permet d'activer des stratégies GPM d'authentification filaire802.1x sur les appareils Surface Hub. Cette fonctionnalité permet aux organisations de mettre en œuvre une authentification réseau filaire normalisée à l'aide du [protocole d’authentificationIEEE802.1x](http://www.ieee802.org/1/pages/802.1x-2010.html). Cette option est déjà disponible pour l’authentification sans fil à l’aide de profils WLAN via GPM. Cette rubrique explique comment configurer un Surface Hub pour l'utiliser avec l’authentification filaire. 

La mise en œuvre et l’activation de l’authentification filaire802.1x sur Surface Hub peut s'effectuer via la [définition de paramètres OMA-URI](https://docs.microsoft.com/intune-classic/deploy-use/windows-10-policy-settings-in-microsoft-intune#oma-uri-settings) de GPM. 

La principale configuration à définir est la stratégie **LanProfile**. En fonction de la méthode d’authentification sélectionnée, d'autres stratégies peuvent être nécessaires: la stratégie **EapUserData** ou l'utilisation de stratégies GPM pour l'ajout de certificats d’utilisateur ou d’ordinateur (comme [ClientCertificateInstall](https://docs.microsoft.com/windows/client-management/mdm/clientcertificateinstall-csp) pour les certificats d'utilisateur/appareil ou [RootCATrustedCertificates](https://docs.microsoft.com/windows/client-management/mdm/rootcacertificates-csp) pour les certificats d'appareil). 

## Élément de stratégie LanProfile

Pour configurer le Surface Hub en vue d'utiliser l'une des méthodes d’authentification802.1x prises en charge, utilisez l’OMA-URI suivant. 

```
./Vendor/MSFT/SurfaceHub/Dot3/LanProfile
```

Ce nœud OMA-URI prend une chaîne de texte XML comme paramètre. Le code XML fourni comme paramètre doit être conforme au [schéma de profil du réseau local câblé](https://msdn.microsoft.com/library/cc233002.aspx), notamment les éléments du [schéma802.1X](https://msdn.microsoft.com/library/cc233003.aspx). 

Dans la plupart des cas, un administrateur ou un utilisateur peut exporter le code XML LanProfile à partir d’un PC existant, déjà configuré sur le réseau pour802.1X, à l’aide de la commande NETSH suivante. 

```
netsh lan export profile folder=.
```

L'exécution de cette commande donnera la sortie suivante et placera un fichier intitulé **Ethernet.xml** dans le répertoire actif. 

```
Interface: Ethernet
Profile File Name: .\Ethernet.xml
1 profile(s) were exported successfully.
```

## Élément de stratégie EapUserData

Si votre méthode d’authentification requiert un nom d’utilisateur et un mot de passe par opposition à un certificat, vous pouvez utiliser l'élément **EapUserData** pour spécifier des informations d’identification pour l'appareil à utiliser pour s’authentifier sur le réseau. 

```
./Vendor/MSFT/SurfaceHub/Dot3/EapUserData 
```

Ce nœud OMA-URI prend une chaîne de texte XML comme paramètre. Le code XML fourni comme paramètre doit être conforme à [l'exemple de Propriétés de l'utilisateur PEAP MS-CHAPv2](https://msdn.microsoft.com/library/windows/desktop/bb891979). Dans l’exemple, vous devez remplacer toutes les instances de *test* et *ias-domain* par vos informations.



## Ajout de certificats

Si votre méthode d’authentification sélectionnée est basée sur des certificats, vous devez [créer un package](provisioning-packages-for-surface-hub.md)de mise en service, utiliser la gestion des périphériques mobiles ( [GPM](https://docs.microsoft.com/windows/client-management/mdm/clientcertificateinstall-csp)) ou importer un certificat à partir des paramètres (**Settings**  >  **mise à jour des paramètres et**  >  **certificats**de sécurité) pour déployer ces certificats sur votre appareil surface Hub dans le magasin de certificats approprié. Lorsque vous ajoutez des certificats, chaque PFX doit contenir un seul certificat (un PFX ne doit pas avoir plusieurs certificats).

