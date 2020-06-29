---
title: Compatibilité des appareils surface avec Windows 10 longue durée du canal de maintenance (surface)
description: Découvrez les limites de compatibilité et de limitations des appareils surface exécutant Windows 10 Enterprise LTSB Edition.
keywords: ltsb, mise à jour, options de service de surface
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
ms.audience: itpro
ms.reviewer: scottmca
manager: laurawi
ms.openlocfilehash: db3dfd57c3b79fcec507ffd146483915490801b9
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832237"
---
# Compatibilité des appareils de surface avec Windows 10 longue durée du canal de maintenance (LTSC)

Les appareils surface sont conçus pour fournir des expériences de meilleure qualité dans le cadre de la productivité et des scénarios généraux. Les mises à jour régulières permettent aux périphériques de surface d’apporter leurs nouvelles innovations et d’évoluer grâce aux nouvelles fonctionnalités fournies par les mises à jour des fonctionnalités de Windows 10. Les mises à jour de fonctionnalités ne sont disponibles que dans les éditions Windows 10 professionnel ou Windows 10 entreprise qui reçoivent des mises à jour en continu via le canal semi-annuel (SAC).

Contrairement à l’option de maintenance SAC, auparavant appelée les options de maintenance de la succursale actuelle ou du branchement actuel (CBB), vous ne pouvez pas sélectionner l’option canal de maintenance à long terme (LTSC) dans les paramètres Windows 10. Pour utiliser l’option de maintenance LTSC, vous devez installer une autre version de Windows 10 entreprise, connue sous le nom de Windows 10 Enterprise LTSC, auparavant appelée Windows 10 entreprise LTSB (succursale de maintenance à long terme). En plus de fournir un modèle de service étendu, Windows 10 Enterprise LTSC Edition fournit également un environnement avec plusieurs composants Windows supprimés. Les expériences de surface principales affectées par LTSC sont les suivantes:

* Mises à jour des fonctionnalités de Windows, notamment les améliorations telles que:

  *  Améliorations apportées à l’entrée manuscrite et au refus de paume fournies par Windows 10, version 1607 (également appelée mise à jour anniversaire)
  *  Prise en charge améliorée des applications PPP élevées fournies dans Windows 10, version 1703 (également appelée créateurs de mise à jour)

* Paramètres de sensibilité à la pression fournis par l’application surface

* Espace de travail Windows Ink

* Applications sans clavier optimisées pour l’interaction vidéo, dont Microsoft Edge, OneNote, le calendrier et l’appareil photo

L’utilisation de l’environnement LTSC de Windows 10 entreprise sur les appareils surface a pour effet d’optimiser les expériences des utilisateurs finaux et vous devez éviter de les utiliser dans les environnements où les utilisateurs veulent obtenir une expérience utilisateur de qualité supérieure et à jour.

L’option de maintenance LTSC est conçue pour les types d’appareils et les scénarios dans lesquels l’attribut key est destiné aux fonctionnalités ou aux fonctionnalités qui ne changent jamais. Les exemples incluent des systèmes qui fabriquent ou importent des équipements médicaux ou des systèmes incorporés dans des bornes, telles que des DAB ou des systèmes de ticket d’aéroport.

>[!NOTE]
>Pour obtenir des informations générales sur les branches de maintenance Windows, notamment LTSC, voir [vue d’ensemble de Windows en tant que service](https://technet.microsoft.com/itpro/windows/update/waas-overview#long-term-servicing-branch).

En règle générale, les appareils qui remplissent les critères suivants sont considérés comme des périphériques généraux, et doivent être associés à Windows 10 professionnel ou à Windows 10 entreprise à l’aide de l’option de maintenance du canal semi-annuel:

* Appareils exécutant des logiciels de productivité tels que Microsoft Office

* Appareils utilisant les applications du Microsoft Store

* Les appareils qui sont utilisés pour la navigation Internet générale (par exemple, recherche ou accès aux réseaux sociaux);

Avant de choisir d’utiliser Windows 10 Enterprise LTSC Edition sur des appareils surface, tenez compte des limitations suivantes:

* Les mises à jour de pilotes et de microprogrammes ne sont pas testées explicitement sur les versions de Windows 10 Enterprise LTSC.

* Si vous rencontrez des problèmes, le support technique Microsoft vous fournira une assistance de dépannage. Toutefois, en raison de la nature de maintenance de Windows LTSC, la résolution des problèmes risque de nécessiter la mise à niveau de périphériques vers une version plus récente de Windows 10 Enterprise LTSC, ou vers Windows 10 professionnel ou entreprise avec l’option de maintenance SAC.

* Les remplacements de périphériques de surface (par exemple, les appareils remplacés par la garantie) pourront contenir des variations subtiles dans les composants matériels qui nécessitent des pilotes de périphériques et des microprogrammes mis à jour. La compatibilité avec ces mises à jour est susceptible de nécessiter l’installation d’une version plus récente de Windows 10 entreprise LTSC ou Windows 10 professionnel ou entreprise à l’aide de l’option de maintenance SAC.

>[!NOTE]
>Il est possible que les organisations standardisant une version spécifique de Windows 10 entreprise LTSC ne puissent pas adopter de nouvelles générations de matériel de surface telles que surface Pro 7, surface Pro X ou surface Laptop 3 sans mise à jour vers une version plus récente de Windows 10 entreprise LTSC ou Windows 10 professionnel ou entreprise. Pour plus d’informations, consultez la rubrique **Comment Windows 10 LTSBs sera-t-il pris en charge?** rubrique dans la section prise en charge **du processeur et du chipset sur Windows** du FAQ sur la politique de support technique [: produits Windows](https://support.microsoft.com/help/18581/lifecycle-policy-faq-windows-products#b4).

Les appareils surface exécutant Windows 10 Enterprise LTSC Edition ne recevront pas de nouvelles fonctionnalités. Dans de nombreux cas, ces fonctionnalités sont demandées par les clients pour améliorer la convivialité et les capacités du matériel de surface. Par exemple, les nouvelles améliorations apportées aux applications PPP élevées dans Windows 10, version 1703. Les clients qui utilisent des appareils de surface dans la configuration LTSC ne verront pas les améliorations tant qu’il n’y a pas de mise à jour vers une nouvelle version de Windows 10 Enterprise LTSC ou une mise à niveau vers une version de Windows 10 avec prise en charge de l’option de maintenance SAC.

Les appareils peuvent être changés de Windows 10 entreprise LTSC vers une version plus récente de Windows 10 entreprise, avec la prise en charge de l’option de maintenance SAC, sans perte de données utilisateur en effectuant une installation de mise à niveau. Vous pouvez également effectuer une installation de mise à niveau sur plusieurs appareils en tirant parti des modèles de séquence de tâches de mise à niveau disponibles dans Microsoft Deployment Toolkit (MDT) et Microsoft Endpoint Configuration Manager. Pour plus d’informations, reportez-vous à la rubrique [mise à niveau des appareils surface vers Windows 10 avec le kit de développement Microsoft](https://technet.microsoft.com/itpro/surface/upgrade-surface-devices-to-windows-10-with-mdt).
