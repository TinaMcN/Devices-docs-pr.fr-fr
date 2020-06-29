---
title: Ports 2 de la station d’accueil de surface sécurisée avec le mode de gestion de surface entreprise (SEMM)
description: Ce document fournit des recommandations pour la configuration des paramètres de port UEFI pour le quai de surface 2 s’il est connecté à des appareils de surface compatibles, notamment surface Book 3, surface Laptop 3 et surface Pro 7.
ms.assetid: 2808a8be-e2d4-4cb6-bd53-9d10c0d3e1d6
ms.reviewer: ''
manager: laurawi
keywords: Résoudre les problèmes courants, les problèmes de configuration
ms.prod: w10
ms.mktglfcycl: support
ms.sitesec: library
ms.pagetype: surfacehub
author: v-miegge
ms.author: jesko
ms.topic: article
ms.date: 06/08/2020
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: de16d76581926a90585b2c6beb2a7bf3b7a695bc
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832274"
---
# Ports 2 de la station d’accueil de surface sécurisée avec le mode de gestion de surface entreprise (SEMM)

## Introduction

Le mode de gestion de surface Enterprise (SEMM) permet aux administrateurs informatiques de sécuriser et de gérer les ports de dock de surface 2 en configurant les paramètres UEFI dans un package de configuration du programme d’installation Windows (. Un fichier MSI) déployé sur des appareils surface compatibles au sein d’un environnement d’entreprise.

### Appareils pris en charge

La gestion de surface Dock 2 avec SEMM est disponible pour les stations d’accueil connectées à surface Book 3, surface Laptop 3 et surface Pro 7. Ces périphériques de surface compatibles sont souvent appelés **périphériques hôtes**. Un package est appliqué aux appareils hôtes en fonction du fait qu’un appareil hôte est **authentifié ou non** **authentifié**. Les paramètres configurés résident dans la couche UEFI sur les appareils hôtes qui vous permettent, l’administrateur informatique, de gérer surface Dock 2 comme n’importe quel autre périphérique intégré, tel que la caméra.

>[!NOTE]
>Vous pouvez gérer les ports de l’ancrage de surface 2 uniquement lorsque le Dock est connecté à l’un des appareils compatibles suivants: surface Book 3, surface Laptop 3 et surface Pro 7. Tout appareil qui ne reçoit pas les paramètres de stratégie UEFI s’il s’agit d’un appareil non authentifié par nature.

### Scénarios

La limitation de surface Dock 2 aux personnes autorisées connectées à un appareil hôte d’entreprise fournit une autre couche de protection des données. Cette possibilité de verrouiller surface Dock 2 est essentielle pour les clients spécifiques dans les environnements hautement sécurisés qui souhaitent bénéficier de la fonctionnalité et de la productivité du Dock tout en préservant la conformité à des protocoles de sécurité stricts. Nous pensons que l’utilisation de SEMM avec surface Dock 2 sera particulièrement utile dans les bureaux ouverts et les espaces partagés, en particulier pour les clients souhaitant verrouiller les ports USB pour des raisons de sécurité. Pour une démonstration vidéo, consultez [SEMM pour surface Dock 2](https://youtu.be/VLV19ISvq_s).

## Configuration et déploiement des paramètres UEFI pour le Dock de surface 2

Cette section fournit des instructions pas à pas pour les tâches suivantes:

1. Installez [**surface Configurator Configurator**](https://www.microsoft.com/download/details.aspx?id=46703).
1. Créez ou obtenez des certificats de clé publique.
1. Créer un. Package de configuration MSI.
   1. Ajoutez vos certificats.
   1. Entrez le numéro à 16 chiffres RN pour les appareils de votre station d’accueil de surface 2.
   1. Configurer les paramètres UEFI.
1. Créez et appliquez le package de configuration aux appareils surface ciblés (surface Book 3, surface Laptop 3 ou surface Pro 7).

>[!NOTE]
>Le **numéro aléatoire (RN)** est un identificateur unique de code hexadécimal à 16 chiffres configuré sur la fabrique et imprimé en petit type sur le côté du Dock. Le RN se distingue de la plupart des numéros de série en ce qu’il ne peut pas être lu électroniquement. Cela permet de garantir que la preuve de propriété est essentiellement établie uniquement en lisant la RN lors de l’accès à l’appareil. Le RN peut également être obtenu lors de la transaction d’achat et enregistré dans les systèmes d’inventaire Microsoft.

### Installation de SEMM et du configurateur surface UEFI

Installez SEMM en exécutant **SurfaceUEFI_Configurator_v2.71.139.0.msi**. Il s’agit d’un programme d’installation autonome qui contient tout ce dont vous avez besoin pour créer et distribuer des packages de configuration pour surface Dock 2.

- Téléchargez **surface Configurator Configurator** à partir [d’outils surface](https://www.microsoft.com/en-us/download/details.aspx?id=46703).

## Créer des certificats de clé publique

Cette section fournit des spécifications pour la création des certificats nécessaires à la gestion des ports pour le quai de surface 2.

### Conditions préalables

Cet article part du principe que vous obtenez des certificats d’un fournisseur tiers ou que vous disposez déjà d’une expertise dans les services de certificats PKI et que vous savez créer votre propre fournisseur.  Familiarisez-vous avec les recommandations générales de création de certificats comme décrit dans la documentation du [mode de gestion de surface Enterprise (SEMM)](https://docs.microsoft.com/surface/surface-enterprise-management-mode) , à l’exception de celle-ci. Les certificats décrits sur cette page requièrent des conditions d’expiration de 30 ans pour l' **autorité de certification du Dock**et de 20 ans pour le **certificat d’authentification hôte**.

Pour plus d’informations, reportez-vous à la documentation sur l' [architecture des services de certificats](https://docs.microsoft.com/windows/win32/seccrypto/certificate-services-architecture) et passez en revue les chapitres appropriés dans [Windows Server 2019 Inside Out](https://www.microsoftpressstore.com/store/windows-server-2019-inside-out-9780135492277)ou [Windows Server 2008 PKI et la sécurité des certificats](https://www.microsoftpressstore.com/store/windows-server-2008-pki-and-certificate-security-9780735640788) disponibles auprès de Microsoft Press.

### Exigences relatives aux certificats racines et hôtes

Avant de créer le package de configuration, vous devez préparer des certificats de clé publique qui authentifient la propriété de surface Dock 2 et facilitent tout changement ultérieur de propriété au cours du cycle de vie de l’appareil. Les certificats d’hébergement et de mise en service nécessitent la saisie d’ID EKU sans être désignés par le biais des **identificateurs d’objet de l’utilisation améliorée de la clé d’authentification client**.

Les valeurs EKU requises sont indiquées dans les tableaux 1 et 2.

#### Tableau1. Conditions requises pour les certificats racines et Dock

|Certificat|Algorithm|Description|Expiration|IDENTIFICATEUR EKU|
|---|---|---|---|---|
|Autorité de certification racine|ECDSA_P384|-Certificat racine avec l’algorithme de signature numérique de l' 384-bit prime (ECDSA)<br>-SHA 256 clé d’utilisation:<br>CERT_DIGITAL_SIGNATURE_KEY_USAGE<br>-CERT_KEY_CERT_SIGN_KEY_USAGE<br>CERT_CRL_SIGN_KEY_USAGE|30 ans|N/A
|Ancrer une autorité de certification|Courbe ECC P256|-Certificat d’hôte avec chiffrement à courbe elliptique de 256 bits<br>-SHA 256 clé d’utilisation:<br>CERT_KEY_CERT_SIGN_KEY_USAGE<br>-Contrainte de longueur du chemin d’accès = 0|20 ans|1.3.6.1.4.1.311.76.9.21.2<br>1.3.6.1.4.1.311.76.9.21.3|

   >[!NOTE]
   >L’autorité de certification du Dock doit être exportée sous la forme d’un fichier. p7b.

### Conditions requises pour le certificat d’administration de la mise en service

Chaque appareil hôte doit avoir la CA doc et deux certificats, comme indiqué dans le tableau 2.

#### Tableau2. Conditions requises pour le certificat d’administration de la mise en service

|Certificat|Algorithm|Description|IDENTIFICATEUR EKU|
|---|---|---|---|
|Certificat d’authentification hôte|ECC P256<br>SHA 256|Prouve l’identité de l’appareil hôte.|1.3.6.1.4.1.311.76.9.21.2|
|Certificat d’administration de la mise en service|ECC P256<br>SHA256|Vous permet de modifier la propriété du Dock et/ou les paramètres de la stratégie en vous permettant de remplacer l’autorité de certification actuellement installée sur le Dock.|1.3.6.1.4.1.311.76.9.21.3<br>1.3.6.1.4.1.311.76.9.21.4|

   >[!NOTE]
   >Les certificats d’authentification et de mise en service de l’hôte doivent être exportés sous forme de fichiers. pfx.

### Créer un package de configuration

Lorsque vous avez obtenu ou créé les certificats, vous pouvez créer le package de configuration MSI qui sera appliqué aux périphériques de surface cible.

1. Exécutez le **Configurateur surface UEFI**.

   ![Exécuter le configurateur surface UEFI](images/secure-surface-dock-ports-semm-1.png)

1. Sélectionnez **quai de surface**.

   ![Sélectionnez quai de surface](images/secure-surface-dock-ports-semm-2.png)

1. Dans la page certificat, entrez les **certificats**appropriés.

   ![Entrez les certificats appropriés.](images/secure-surface-dock-ports-semm-3.png)

1. Ajoutez RNs d’ancrage approprié à la liste.

   >[!NOTE]
   >Lors de la création d’un package de configuration pour plusieurs appareils de station de dessin de surface 2, au lieu d’entrer chacune d’elles manuellement, vous pouvez utiliser un fichier. csv contenant une liste de RNs.

1. Spécifiez vos paramètres de stratégie pour les ports de données USB, Ethernet et audio. Le configurateur UEFI vous permet de configurer des paramètres de stratégie pour les utilisateurs authentifiés (stratégie authentifiée) et les utilisateurs non authentifiés (stratégie non authentifiée). La figure suivante illustre l’accès au port activé pour les utilisateurs authentifiés et désactivé pour les utilisateurs non authentifiés.

   ![Choisissez quels composants vous souhaitez activer ou désactiver.](images/secure-surface-dock-ports-semm-4.png)

   - L’utilisateur authentifié fait référence à un appareil surface sur lequel les certificats appropriés sont installés, comme configuré dans le. Package de configuration MSI appliqué aux appareils cibles. Il s’applique aux utilisateurs authentifiés de l’utilisateur qui se connectent à l’appareil. 
   - Un utilisateur non authentifié fait référence à un autre appareil.
   - Sélectionnez **Reset (réinitialiser** ) pour créer un package spécial «Reset» (réinitialisation) qui supprimera tout package de configuration antérieur accepté par le Dock.

1. Sélectionnez **Build** pour créer le package spécifié.

### Appliquer le package de configuration à un quai de surface 2

1. Emportez le fichier MSI généré par surface Configurator et installez-le sur un appareil hôte de surface. Les appareils hôtes compatibles sont surface Book 3, surface Laptop 3 ou surface Pro 7.
1. Connectez l’appareil hôte à la surface Dock 2. Lors de la connexion des paramètres de stratégie UEFI de la station d’accueil sont appliqués.

## Vérifier l’état géré à l’aide de l’application surface

Une fois le package de configuration appliqué, vous pouvez rapidement vérifier l’état de stratégie résultant du Dock directement à partir de l’application de surface, installé par défaut sur tous les appareils surface. Si l’application surface n’est pas présente sur l’appareil, vous pouvez la télécharger et l’installer à partir du Microsoft Store.

### Scénario de test

Objectif: configurez les paramètres de stratégie pour autoriser l’accès aux ports par les utilisateurs authentifiés.

1. Activez tous les ports pour les utilisateurs authentifiés et désactivez-les pour les utilisateurs non authentifiés.

   ![Activation de ports pour les utilisateurs authentifiés](images/secure-surface-dock-ports-semm-4.png)

1. Appliquez le package de configuration à votre appareil cible, puis reliez surface Dock 2.

1. Ouvrez l' **application surface** et sélectionnez **quai** de surface pour afficher l’état de stratégie résultant de votre quai de surface. Si les paramètres de stratégie sont appliqués, l’application surface indiquera que les ports seront disponibles.

   ![Surface App affiche tous les ports sont disponibles pour les utilisateurs authentifiés](images/secure-surface-dock-ports-semm-5.png)

1. À présent, vous devez vérifier que les paramètres de stratégie ont correctement désactivé tous les ports pour les utilisateurs non authentifiés. Connectez surface Dock 2 à un appareil non géré, c’est-à-dire tout appareil surface extérieur à l’étendue de la gestion du package de configuration que vous avez créé.

1. Ouvrez l' **application surface** et sélectionnez **quai de surface**. L’état de stratégie résultant indique qu’il est désactivé.

   ![Application surface montrant les ports désactivés pour les utilisateurs non authentifiés ](images/secure-surface-dock-ports-semm-6.png)

>[!NOTE]
>Si vous souhaitez conserver la propriété de l’appareil, mais autoriser tous les utilisateurs à accéder à tous les utilisateurs, vous pouvez créer un nouveau package tout en activant. Si vous souhaitez supprimer définitivement les restrictions et la propriété de l’appareil (le rendre non géré), sélectionnez **Réinitialiser** dans le configurateur de surface pour créer un package à appliquer aux appareils cibles.

Félicitations. Vous avez réussi à gérer les ports de la station d’accueil surface 2 sur les appareils hôtes ciblés.

## En savoir plus

- [Documentation du mode de gestion des entreprises de surface (SEMM)](https://docs.microsoft.com/surface/surface-enterprise-management-mode)
- [Architecture des services de certificats](https://docs.microsoft.com/windows/win32/seccrypto/certificate-services-architecture)
- [Windows Server 2019 Inside Out](https://www.microsoftpressstore.com/store/windows-server-2019-inside-out-9780135492277)
- [Sécurité des certificats et PKI de Windows Server 2008](https://www.microsoftpressstore.com/store/windows-server-2008-pki-and-certificate-security-9780735640788)
