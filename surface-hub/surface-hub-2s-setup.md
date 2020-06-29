---
title: Première installation de surface Hub 2
description: Découvrez comment procéder à la première configuration de surface Hub 2.
keywords: séparer les valeurs par des virgules
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 07/03/2019
ms.localizationpriority: Medium
ms.openlocfilehash: 47a393944c1b524931a6ac56962cc2cd60786007
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10833611"
---
# Première installation de surface Hub 2

Lorsque vous démarrez surface Hub 2 pour la première fois, l’appareil accède automatiquement au mode d’installation du premier plan pour vous guider dans la configuration du compte et les paramètres associés.

## Configuration du compte surface Hub 2S

1. **Configurez vos paramètres régionaux.** Entrez les informations de région, de langue, de disposition du clavier et de fuseau horaire. Sélectionnez **Suivant**.

   ![* Configurez vos paramètres régionaux *](images/sh2-run1.png) <br>
1. **Se connecter à un réseau sans fil.** Choisissez votre réseau sans fil préféré et sélectionnez **Next (suivant).**

- Cette option n’apparaît pas s’il s’agit d’une connexion à l’aide d’un câble Ethernet.
- Vous ne pouvez pas vous connecter à un réseau sans fil sur les points d’accès (portails indirects) qui redirigent les demandes de connexion au site Web du fournisseur.

3. **Entrez les informations de compte de l’appareil.** Utiliser **domaine\utilisateur** pour les environnements locaux et hybrides et l' **utilisateur \ @example. com** pour les environnements en ligne. Sélectionnez **Next (suivant).**

   ![* Entrer les informations sur le compte de l’appareil *](images/sh2-run2.png) <br>
1. **Entrez des informations supplémentaires.** Le cas échéant, indiquez l’adresse de votre serveur Exchange, puis sélectionnez **suivant.**

    ![* Entrez plus d’informations; par exemple, nom du serveur Exchange *](images/sh2-run3.png) <br>

1. **Nommez cet appareil.** Entrez un nom pour votre appareil ou utilisez le nom suggéré en fonction du nom d’affichage de votre compte et du nom d’utilisateur principal [UPN]. **Sélectionnez Next (suivant**).

- Le **nom convivial** est visible dans le coin inférieur gauche de surface Hub 2 et s’affiche lors de la projection sur le périphérique.

- Le **nom** de l’appareil identifie l’appareil lorsqu’il est affilié à Active Directory ou Azure Active Directory, et lors de l’inscription de l’appareil avec Intune.

  ![* Nommer cet appareil *](images/sh2-run4.png) <br>
 
## Configuration de comptes d’administrateur de périphériques

La première fois que vous configurez un administrateur d’appareil. Pour plus d’informations, reportez-vous à la rubrique affiliation de l' [appareil surface Hub](https://docs.microsoft.com/surface-hub/surface-hub-2s-prepare-environment#device-affiliation).

 Dans la fenêtre **configurer les administrateurs pour ce périphérique** , sélectionnez l’une des options suivantes: services de domaine Active Directory, Azure Active Directory ou administrateur local.

   ![* Administrateurs de configuration pour cet appareil *](images/sh2-run5.png) <br>

### Services de domaine ActiveDirectory

1. Entrez les informations d’identification d’un utilisateur disposant des autorisations de connexion de l’appareil à Active Directory.

    ![* Administrateurs de l’installation à l’aide de Domain Join *](images/sh2-run6.png) <br>

2. Sélectionnez le groupe de sécurité Active Directory contenant les membres autorisés à se connecter à l’application paramètres sur surface Hub 2S.

    ![* Entrer un groupe de sécurité *](images/sh2-run7.png) <br>
1. Cliquez sur **Terminer**. Le périphérique redémarrera.

### Azure Active Directory

Lorsque vous choisissez d’affilier votre appareil à Azure Active Directory, le périphérique redémarre immédiatement et affiche la page suivante. Sélectionnez **Suivant**.

![* Si votre organisation utilise Office 365 ou d’autres services professionnels de Microsoft, nous inscrivons cet appareil avec votre organisation *](images/sh2-run8.png) <br>

1. Entrez l’adresse de messagerie ou le nom d’utilisateur principal d’un compte **avec le plan Intune 1** ou une version ultérieure, puis sélectionnez **suivant.**

    ![* Entrez votre compte professionnel ou scolaire *](images/sh2-run9.png) <br>

2. Si vous êtes redirigé, authentifiez-vous à l’aide de la page de connexion de votre organisation et fournissez des informations d’ouverture de session supplémentaires, le cas échéant. Le périphérique redémarrera.

## Compte d’administrateur local

- Entrez un nom d’utilisateur et un mot de passe pour votre administrateur local. Le périphérique redémarrera.

     ![* Configurer un compte d’administrateur *](images/sh2-run10.png) <br>
 
## Utiliser les packages de mise en service

Si vous insérez une clé USB avec un module de mise en service dans l’un des ports USB lorsque vous démarrez surface Hub 2, le périphérique affiche la page suivante.

1. Entrez les paramètres demandés et sélectionnez **configurer**.

    ![* Saisie des paramètres régionaux pour le package de mise en service](images/sh2-run11.png) <br>

    ![* Mise en service de cet appareil à partir de médias amovibles *](images/sh2-run12.png) <br>
2. Choisissez le package de mise en service que vous voulez utiliser.

   ![* Choisir le package de mise à service à utiliser *](images/sh2-run13.png) <br>

3. Si vous avez créé un fichier CSV de plusieurs appareils, vous pouvez choisir une configuration d’appareil. Pour plus d’informations, reportez-vous à [créer des packages de mise en service pour surface Hub 2](https://docs.microsoft.com/surface-hub/surface-hub-2s-deploy#provisioning-multiple-devices-csv-file).


    ![* Sélectionnez un compte d’appareil et un nom convivial dans votre fichier de configuration *](images/sh2-run14.png) <br>

4. Suivez les instructions pour la première fois.
