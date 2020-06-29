---
title: Gérer et déployer les mises à jour du microprogramme et des pilotes Surface
description: Cet article décrit les options disponibles pour gérer et déployer des mises à jour de microprogramme et de pilote pour les appareils surface.
ms.assetid: CD1219BA-8EDE-4BC8-BEEF-99B50C211D73
ms.reviewer: ''
manager: laurawi
keywords: Surface, Surface Pro3, microprogramme, mettre à jour, appareil, gérer, déployer, pilote, USB
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.audience: itpro
ms.openlocfilehash: 91cde5fdf4a7745d491bd2eb928baca75955b90d
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832831"
---
# Gérer et déployer les mises à jour du microprogramme et des pilotes Surface

La façon dont vous gérez les mises à jour de pilote de surface et de microprogramme varie en fonction de votre environnement et de vos exigences d’organisation. Sur les appareils surface, le microprogramme est exposé au système d’exploitation en tant que pilote et est visible dans le gestionnaire de périphériques, ce qui permet de mettre à jour automatiquement le microprogramme et les pilotes de l’appareil à l’aide de Windows Update ou de Windows Update pour les entreprises. Même si cette approche simplifiée peut être réalisable pour les entreprises de démarrage et les petites et moyennes entreprises, les organisations de grande taille ont généralement besoin d’avoir besoin de distribuer des mises à jour en interne. Cela risque de nécessiter une planification complète, des tests de compatibilité entre applications, des mises à jour et des mises à jour, avant l’approbation et la distribution finales sur le réseau.

> [!NOTE]
> Cet article est destiné aux agents de support technique et aux professionnels de l’informatique et ne s’applique qu’aux appareils surface. Pour obtenir de l’aide sur l’installation des mises à jour de surface ou du microprogramme sur un appareil familial, voir [mettre à jour le microprogramme de surface et Windows 10](https://support.microsoft.com/help/4023505).

Pendant que les solutions de distribution de logiciels de niveau entreprise continuent d’évoluer, le raisonnement de l’entreprise pour gérer les mises à jour de manière centralisée reste le même: maintenir la sécurité des appareils surface et les mettre à jour avec les derniers systèmes d’exploitation et améliorations de fonctionnalités. Il est essentiel de soutenir un environnement de production stable et de veiller à ce que les utilisateurs ne soient pas bloqués. Cet article fournit une vue d’ensemble des outils et processus recommandés pour les grandes organisations et à ce propos.

## Gestion des mises à jour centralisées en environnement commercial

Microsoft dispose d’outils rationalisés pour la gestion des appareils, notamment les mises à jour de pilotes et de microprogrammes, en une seule et même interface unifiée appelée [Centre d’administration du gestionnaire de points de terminaison Microsoft](https://devicemanagement.microsoft.com/) accessible à partir de devicemanagement.Microsoft.com.

### Gestion des mises à jour avec Configuration Manager et Intune

Microsoft Endpoint Configuration Manager vous permet de synchroniser et de déployer des mises à jour de microprogramme et de pilote de surface avec le client Configuration Manager. L’intégration à Microsoft Intune vous permet d’afficher tous les appareils gérés, gérés par des partenaires et gérés au sein d’un seul et même emplacement. Il s’agit de la solution recommandée pour les grandes organisations qui peuvent gérer les mises à jour de surface.

Pour consulter la procédure détaillée, consultez les ressources suivantes:

- [Gestion des mises à jour de pilote surface dans Configuration Manager](https://docs.microsoft.com/surface/manage-surface-driver-updates-configuration-manager)
- [Déploiement d’applications avec Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/deploy-applications)
- [Documentation sur Endpoint Configuration Manager](https://docs.microsoft.com/configmgr/)

### Gestion des mises à jour à l’aide du kit de développement Microsoft Deployment

Inclus dans le gestionnaire de configuration de point de terminaison, le kit de développement Microsoft Deployment (MDT) contient des outils de déploiement facultatifs que vous pouvez utiliser selon votre environnement. Il s’agit de l’évaluation Windows et du kit de déploiement Windows (Windows ADK), du gestionnaire d’images de déploiement, de la gestion des services d’image de déploiement (DISM) et de l’outil de migration des États utilisateur. Vous pouvez télécharger la dernière version de MDT à partir de la [page de téléchargement du kit de développement Microsoft Deployment](https://www.microsoft.com/download/details.aspx?id=54259).

Pour consulter la procédure détaillée, consultez les ressources suivantes:

- [Documentation sur le kit de développement Microsoft](https://docs.microsoft.com/configmgr/mdt/)
- [Déployer Windows10 avec Microsoft Deployment Toolkit](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-windows-10-with-the-microsoft-deployment-toolkit)
- [Déploiement de Windows 10 sur les appareils surface avec le kit de développement Microsoft Deployment](https://docs.microsoft.com/surface/deploy-windows-10-to-surface-devices-with-mdt)

Les mises à jour de pilote de surface et de microprogramme sont empaquetées sous forme de fichiers Windows Installer (*. msi). Pour déployer ces packages Windows Installer, vous pouvez utiliser le gestionnaire de configuration de point de terminaison ou MDT. Pour plus d’informations sur la sélection du fichier. msi approprié pour un appareil et un système d’exploitation, reportez-vous aux instructions suivantes sur le téléchargement de fichiers. msi.

Pour obtenir des instructions sur le déploiement des mises à jour à l’aide du gestionnaire de configuration de point de terminaison, voir [déployer des applications avec Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/deploy-applications). Pour obtenir des instructions sur le déploiement des mises à jour à l’aide de MDT, voir [déploiement d’une image Windows 10 à l'](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt)aide de MDT.

**WindowsPE, microprogramme et pilotes de surface**

Le gestionnaire de configuration de point de terminaison et MDT utilisent l’environnement de préinstallation Windows (WindowsPE) pendant le processus de déploiement. WindowsPE ne prend en charge qu’un ensemble limité de pilotes de base, tels que ceux destinés aux cartes réseau et aux contrôleurs de stockage. Les pilotes pour composants Windows qui ne font pas partie de WindowsPE peuvent générer des erreurs. Il est recommandé d’éviter de telles erreurs en configurant le processus de déploiement de manière à ce qu’il utilise uniquement les pilotes requis lors de la phase WindowsPE.

### Endpoint Configuration Manager

À partir du gestionnaire de configuration de point de terminaison, vous pouvez synchroniser et déployer des mises à jour de pilote et de microprogramme Microsoft surface à l’aide du client Configuration Manager. Pour plus d’informations, voir KB 4098906, [Comment gérer les mises à jour de pilote surface dans Configuration Manager](https://support.microsoft.com/help/4098906/manage-surface-driver-updates-in-configuration-manager).

## Appareils pris en charge

Des fichiers. msi peuvent être téléchargés pour les appareils surface à partir de surface Pro 2 ou version ultérieure. Pour plus d’informations sur les fichiers. msi correspondant aux périphériques de surface les plus récents tels que surface Pro 7, surface Pro X et surface Laptop 3, vous pouvez accéder à cette page lors de la publication.

## Gestion du microprogramme avec DFCI

Les profils d’interface de configuration de microprogramme de périphérique (DFCI) intégrés à Intune (désormais disponible dans la version [publique Preview](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)), la gestion de surface UEFI étend la pile de gestion moderne au niveau matériel UEFI. DFCI prend en charge la mise en service des fonctions d’approvisionnement nulle, élimine les mots de passe BIOS et contrôle les paramètres de sécurité, notamment les options de démarrage et les périphériques intégrés, et vous permet de créer des scénarios de sécurité avancée à l’avenir. Pour plus d’informations, voir:

- [Gestion Intune des paramètres UEFI Surface](https://docs.microsoft.com/surface/surface-manage-dfci-guide)
- [Enflammer 2019: annonçant la gestion à distance des paramètres de surface UEFI de Intune](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333).

## Recommandations en matière de processus de déploiement des mises à jour

Pour conserver un environnement stable, il est vivement recommandé de conserver la parité avec la version la plus récente de Windows 10.  Pour obtenir des recommandations en matière de meilleures pratiques, voir [créer des anneaux de déploiement pour les mises à jour de Windows 10](https://docs.microsoft.com/windows/deployment/update/waas-deployment-rings-windows-10-updates).

## Packages de mise à jour de surface téléchargeables

Les versions spécifiques de Windows 10 disposent de fichiers. msi distincts, chacun contenant toutes les mises à jour de pilote et de microprogramme nécessaires pour les appareils surface. Les packages de mise à jour peuvent inclure tout ou partie des composants suivants:

- Wi-Fi et LTE
- Vidéo
- Disque SSD
- Module d’agrégation de systèmes (SAM)
- Autonomie
- Contrôleur du clavier
- Contrôleur incorporé (EC)
- Moteur de gestion (ME)
- Interface de microprogramme Unified EFI

### Télécharger des fichiers. msi

1. Naviguez jusqu’à [Télécharger les pilotes et le microprogramme pour surface](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware) dans le centre de téléchargement Microsoft.
2. Sélectionnez le nom du fichier. msi qui correspond au modèle de surface et à la version de Windows. Le nom du fichier. msi inclut le numéro de build Windows minimal pris en charge requis pour installer les pilotes et le microprogramme. Par exemple, comme illustré dans la figure ci-dessous, pour mettre à jour un surface Book 2 avec la build 18362 de Windows 10, sélectionnez **SurfaceBook2_Win10_18362_19.101.13994.msi.** Pour un livre surface 2 avec la build 16299 de Windows 10, sélectionnez **SurfaceBook2_Win10_16299_1803509_3.msi**.

    ![Figure1. Téléchargement des mises à jour de surface](images/fig1-downloads-msi.png)

    *Figure1. Téléchargement des mises à jour de surface*

### Convention d’affectation de noms surface. msi

Depuis le 2019 août, les fichiers. msi ont utilisé la Convention d’affectation de noms suivante:

- Numéro de version de Windows du *produit*_*Windows release*_*numéro*de_*version*_*du numéro de version du numéro de version (généralement zéro)*.

**Exemple**

- SurfacePro6_Win10_18362_19.073.44195_0.msi

Ce nom de fichier fournit les informations suivantes:

- **Produit:** SurfacePro6
- **Version de Windows:** Win10
- **Version:** 18362
- **Version:** 19.073.44195: indique la date et l’heure auxquelles le fichier a été créé, comme suit:
  - **Année:** 19 (2019)
  - **Mois et semaine:** 073 (troisième semaine de juillet)
  - **Minute du mois:** 44195
- **Version:** 0 (première version de cette version)

### Convention d’affectation des noms de surface héritée. msi

Les fichiers. msi hérités (fichiers générés avant le 2019 d’août) suivi la même formule d’appellation globale mais ont utilisé une méthode différente pour dériver le numéro de version.

**Exemple**

- SurfacePro6_Win10_16299_1900307_0.msi

Ce nom de fichier fournit les informations suivantes:

- **Produit:** SurfacePro6
- **Version de Windows:** Win10
- **Version:** 16299
- **Version:** 1900307: il s’agit de la date à laquelle le fichier a été créé et de sa position dans la séquence de publication, comme suit:
  - **Année:** 19 (2019)
  - **Numéro de publication:** 003 (troisième version de l’année)
  - **Numéro de version du produit:** 07 (surface Pro 6 est officiellement la septième version de surface Pro)
- **Version:** 0 (première version de cette version)

## En savoir plus

- [Télécharger les pilotes et le microprogramme pour surface](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware)
- [Gestion des mises à jour de pilote surface dans Configuration Manager](https://support.microsoft.com/help/4098906/manage-surface-driver-updates-in-configuration-manager)
- [Déploiement d’applications avec Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/deploy-applications)
- [Documentation sur Endpoint Configuration Manager](https://docs.microsoft.com/configmgr/)
- [Documentation sur le kit de développement Microsoft](https://docs.microsoft.com/configmgr/mdt/)
- [Déployer Windows10 avec Microsoft Deployment Toolkit](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-windows-10-with-the-microsoft-deployment-toolkit)
- [Déploiement de Windows 10 sur les appareils surface avec le kit de développement Microsoft Deployment](https://docs.microsoft.com/surface/deploy-windows-10-to-surface-devices-with-mdt)  
- [Gestion Intune des paramètres UEFI Surface](https://docs.microsoft.com/surface/surface-manage-dfci-guide)
- [Enflammer 2019: annonçant la gestion à distance des paramètres de surface UEFI de Intune](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333).
- [Créer des anneaux de déploiement pour les mises à jour Windows10](https://docs.microsoft.com/windows/deployment/update/waas-deployment-rings-windows-10-updates)
