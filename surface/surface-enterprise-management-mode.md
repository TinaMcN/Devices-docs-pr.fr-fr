---
title: Surface Enterprise Management Mode (Surface)
description: Découvrez comment cette fonctionnalité des appareils Surface avec l’uefi Surface vous permet de sécuriser et de gérer les paramètres de microprogramme au sein de votre organisation.
keywords: uefi, configurer, microprogramme, sécurisé, semm
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices, security
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: hachidan
manager: laurawi
ms.localizationpriority: medium
audience: itpro
ms.date: 01/15/2021
ms.openlocfilehash: e6f81639253c646f5d3956243a80f4d61c91028a
ms.sourcegitcommit: 1053479c191fd10651d31a466fad1769fb0cd28b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/16/2021
ms.locfileid: "11271418"
---
# Mode de gestion Microsoft Surface Enterprise

Microsoft Surface Enterprise Management Mode (SEMM) est une fonctionnalité des appareils Surface avec UEFI Surface qui vous permet de sécuriser et de gérer les paramètres de microprogramme au sein de votre organisation. Avec SEMM, les professionnels de l’informatique peuvent préparer les configurations des paramètres UEFI et les installer sur un appareil Surface. Outre la possibilité de configurer les paramètres UEFI, SEMM utilise également un certificat pour protéger la configuration contre toute falsification ou suppression non autorisée. SEMM est une condition requise pour pouvoir migrer un Surface Hub 2S vers Windows 10 Professionnel et Entreprise.

>[!NOTE]
>SEMM est disponible uniquement sur les appareils avec le microprogramme UEFI Surface. Cela comprend la plupart des autres appareils Surface, notamment surface Pro 7+, Surface Pro X, Surface Hub 2S et SSO commerciales Surface Laptop 3 avec un processeur Intel et Surface Laptop Go. SEMM n’est pas pris en charge sur la référence 15 pouces Surface Laptop 3 avec processeur AMD (disponible uniquement en tant que référence SKU au détail). 

Lorsque les appareils Surface sont configurés par SEMM et sécurisés avec le certificat SEMM, ils sont considérés comme inscrits *à* SEMM. Lorsque le certificat SEMM est supprimé et que le contrôle des paramètres UEFI est renvoyé à l’utilisateur de l’appareil, l’appareil Surface est considéré comme non inscrit *dans* SEMM.

Il existe deux options d’administration que vous pouvez utiliser pour gérer SEMM et inscrire des appareils Surface : un outil autonome ou une intégration avec Microsoft Endpoint Configuration Manager. L’outil autonome SEMM, appelé Configurateur UEFI Microsoft Surface, est décrit dans cet article. Pour plus d’informations sur la gestion de SEMM avec Microsoft Endpoint Configuration Manager, voir Utiliser Microsoft Endpoint Configuration Manager pour gérer les appareils avec [SEMM.](https://technet.microsoft.com/itpro/surface/use-system-center-configuration-manager-to-manage-devices-with-semm)


## Configurateur UEFI Microsoft Surface

L’espace de travail principal de SEMM est Microsoft Surface UEFI Configurator, comme le montre la figure 1. Microsoft Surface UEFI Configurator est un outil utilisé pour créer des packages Windows Installer (.msi) ou des images WinPE utilisées pour inscrire, configurer et désinscrire SEMM sur un appareil Surface. Ces packages contiennent un fichier de configuration dans lequel les paramètres de l’UEFI sont spécifiés. Les packages SEMM contiennent également un certificat, qui est installé et stocké dans le microprogramme et utilisé pour vérifier la signature des fichiers de configuration avant l’application des paramètres UEFI.

>[!NOTE]
>Vous pouvez désormais utiliser le configurateur UEFI Surface et seMM pour gérer les ports sur la station d’accueil Surface 2. Pour en savoir plus, [consultez les ports Secure Surface Dock 2 avec SEMM.](secure-surface-dock-ports-semm.md)

![Configurateur UEFI Microsoft Surface](images/surface-ent-mgmt-fig1-uefi-configurator.png "Microsoft Surface UEFI Configurator")

*Figure1. Configurateur UEFI Microsoft Surface*


Vous pouvez utiliser l’outil Microsoft Surface UEFI Configurator en trois modes :

* [Package de configuration UEFI Surface.](#configuration-package) Utilisez ce mode pour créer un package de configuration UEFI Surface pour inscrire un appareil Surface dans SEMM et pour configurer les paramètres UEFI sur les appareils inscrits.
* [Surface UEFI Reset Package](#reset-package). Utilisez ce mode pour désinscrire un appareil Surface de SEMM.
* [Demande de récupération UEFI Surface.](#recovery-request) Utilisez ce mode pour répondre à une demande de récupération pour désinscrire un appareil Surface de SEMM en cas d’échec d’une opération de réinitialisation du package.


#### Télécharger Microsoft Surface UEFI Configurator

Vous pouvez télécharger microsoft Surface UEFI Configurator à partir de la page [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) du Centre de téléchargement Microsoft.

### Package de configuration

Les packages de configuration UEFI Surface sont le mécanisme principal pour implémenter et gérer SEMM sur les appareils Surface. Ces packages contiennent un fichier de configuration des paramètres UEFI spécifiés lors de la création du package dans microsoft Surface UEFI Configurator et un fichier de certificat, comme le montre la figure 2. Lorsqu’un package de configuration est exécuté pour la première fois sur un appareil Surface qui n’est pas déjà inscrit au SEMM, il a mis en place le fichier de certificat dans le microprogramme de l’appareil et inscrit l’appareil dans SEMM. Lorsque vous inscrivez un appareil dans SEMM, vous êtes invité à confirmer l’opération en fournissant les deux derniers chiffres de l’empreinte numérique du certificat SEMM avant que le fichier de certificat ne soit stocké et que l’inscription puisse se terminer. Cette confirmation nécessite qu’un utilisateur soit physiquement présent sur l’appareil au moment de l’inscription pour effectuer la confirmation.

![Sécuriser un package de configuration SEMM avec un certificat](images/surface-ent-mgmt-fig2-securepackage.png "Secure a SEMM configuration package with a certificate")

*Figure2. Sécuriser un package de configuration SEMM avec un certificat*

Pour plus [d’informations sur](#surface-enterprise-management-mode-certificate-requirements) les conditions requises pour le certificat SEMM, voir la section sur les certificats requis pour le mode Gestion de l’entreprise Surface de cet article.

>[!NOTE]
>Vous pouvez également spécifier un mot de passe UEFI avec SEMM requis pour afficher les **pages** **Sécurité,** **Appareils,** **Configuration**de démarrage ou Gestion de l’entreprise de Surface UEFI.

Une fois qu’un appareil est inscrit au seMM, le fichier de configuration est lu et les paramètres spécifiés dans le fichier sont appliqués à UEFI. Lorsque vous exécutez un package de configuration sur un appareil déjà inscrit au seMM, la signature du fichier de configuration est vérifiée par rapport au certificat stocké dans le microprogramme de l’appareil. Si la signature ne correspond pas, aucune modification n’est appliquée à l’appareil.

### Activer ou désactiver des appareils dans l’UEFI Surface avec SEMM

La liste suivante présente tous les appareils disponibles que vous pouvez gérer dans SEMM :

* Port USB d’accueil
* Audio à l’bord
* DGPU
* Type Cover
* Carte Micro SD
* Caméra frontale
* Caméra arrière
* Caméra infrarouge, pour Windows Hello
* Bluetooth uniquement
* Wi-Fi et Bluetooth
*              LTE           

 >[!NOTE]
>Les appareils intégrés qui apparaissent dans la page Appareils UEFI peuvent varier en fonction de votre appareil ou de votre environnement d’entreprise. Par exemple, la page Appareils UEFI n’est pas prise en charge sur Surface Pro X ; LTE apparaît uniquement sur les appareils équipés de LTE. 
### Configurer les paramètres avancés avec SEMM
**Tableau1. Paramètres avancés**

| Paramètre                            | Description                                                                                                                                                                                        |
| ---------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| IPv6 pour démarrage PXE                  | Vous permet de gérer la prise en charge d’IPv6 pour le démarrage PXE. Si vous ne configurez pas ce paramètre, la prise en charge du démarrage PXE par IPv6 est désactivée.                                                                               |
| Autre démarrage                     | Vous permet de gérer l’utilisation d’un autre ordre de démarrage pour démarrer directement sur un périphérique USB ou Ethernet en appuyant à la fois sur le bouton Baisser le volume et sur le bouton d’alimentation pendant le démarrage. Si vous ne configurez pas ce paramètre, le démarrage alternatif est activé. |
| Verrou d’ordre de démarrage                    | Vous permet de verrouiller l’ordre de démarrage pour empêcher les modifications. Si vous ne configurez pas ce paramètre, le verrouillage de l’ordre de démarrage est désactivé.                                                                                                        |
| Démarrage USB                           | Vous permet de gérer le démarrage sur des périphériques USB. Si vous ne configurez pas ce paramètre, le démarrage USB est activé.                                                                                                                 |
| Pile réseau                      | Vous permet de gérer les paramètres de démarrage de la pile réseau. Si vous ne configurez pas ce paramètre, la possibilité de gérer les paramètres de démarrage de la pile réseau est désactivée.                                                                                                           |
| Mise sous alimentation automatique                      | Vous permet de gérer les paramètres de démarrage d’alimentation automatique. Si vous ne configurez pas ce paramètre, l’alimentation automatique est activée.                                                                                                        |
| SMT (Simultaneous Multi-Threading) | Vous permet de gérer l’outil SMT (Simultaneous Multi-Threading) pour activer ou désactiver l’hyperthreading. Si vous ne configurez pas ce paramètre, l’environnement SMT est activé.                                                  |
|Activer la limite de batterie| Vous permet de gérer la fonctionnalité de limite de batterie. Si vous ne configurez pas ce paramètre, la limite de la batterie est activée. |
| Sécurité                           | Affiche la **page** Sécurité UEFI Surface. Si vous ne configurez pas ce paramètre, la page Sécurité s’affiche.                                                                                                                 |
| Périphériques                            | Affiche la **page** Appareils UEFI Surface. Si vous ne configurez pas ce paramètre, la page Appareils s’affiche.                                                                                                                     |
| Démarrage                               | Affiche la **page** de démarrage UEFI Surface. Si vous ne configurez pas ce paramètre, la page de démarrage s’affiche.                                                                                                                                                            |
| DateTime                           | Affiche la page **DateTime** UEFI Surface. Si vous ne configurez pas ce paramètre, la page DateTime s’affiche.                                                                                                                |
| EnableOSMigration                          | Permet de migrer le Surface Hub 2 de Windows 10 Team vers Windows 10 Professionnel ou Entreprise. Si vous ne configurez pas ce paramètre, les appareils Surface Hub 2 peuvent uniquement exécuter windows 10 Team OS.   Remarque : le double démarrage entre Windows 10 Team et Windows 10 Professionnel/Entreprise n’est pas disponible sur Surface Hub 2.                                                                                                           |


>[!NOTE]
>Lorsque vous créez un package de configuration SEMM, deux caractères sont affichés sur la **page** Réussite, comme le montre la figure 3.

![Affichage de l’empreinte numérique du certificat](images/surface-ent-mgmt-fig5-success.png "Certificate thumbprint display")

*Figure3. Affichage des deux derniers caractères de l’empreinte numérique du certificat sur la page Réussite*

Ces caractères sont les deux derniers caractères de l’empreinte numérique du certificat et doivent être écrits ou enregistrés. Les caractères sont requis pour confirmer l’inscription à SEMM sur un appareil Surface, comme illustré à la Figure 4.

![Confirmation de l’inscription dans SEMM](images/surface-ent-mgmt-fig6-enrollconfirm.png "Enrollment confirmation in SEMM")

*Figure4. Confirmation de l’inscription dans SEMM avec l’empreinte du certificat SEMM*

>[!NOTE]
>Les administrateurs ayant accès au fichier de certificat (.pfx) peuvent lire l’empreinte numérique à tout moment en ouvrant le fichier .pfx dans CertMgr. Pour afficher l’empreinte numérique avec CertMgr, suivez ce processus :
>1. Cliquez avec le bouton droit sur le fichier .pfx, puis cliquez sur **Ouvrir.**
>2. Développez le dossier dans le volet de navigation.
>3. Cliquez sur **Certificats**.
>4. Cliquez avec le bouton droit sur votre certificat dans le volet principal, puis cliquez sur **Ouvrir.**
>5. Cliquez sur **l’onglet Détails.**
>6. **Toutes** ou **propriétés uniquement** doivent être sélectionnées dans **le** menu déroulant Afficher.
>7. Sélectionnez le **champ Empreinte numérique**.

Pour inscrire un appareil Surface dans SEMM ou pour appliquer la configuration UEFI à partir d’un package de configuration, il vous suffit d’exécuter le fichier .msi avec des privilèges d’administration sur l’appareil Surface prévu. Vous pouvez utiliser des technologies de déploiement d’application ou de système d’exploitation telles que [Microsoft Endpoint Configuration Manager](https://technet.microsoft.com/library/mt346023) ou Microsoft Deployment [Shared Computer Toolkit](https://technet.microsoft.com/windows/dn475741). Lorsque vous inscrivez un appareil dans SEMM, vous devez être physiquement présent pour confirmer l’inscription sur l’appareil. L’interaction utilisateur n’est pas requise lorsque vous appliquez une configuration à des appareils déjà inscrits à SEMM.

Pour une étape pas à pas sur l’inscription d’un appareil Surface dans SEMM ou l’application d’une configuration UEFI Surface avec SEMM, voir Inscrire et configurer des appareils Surface avec [SEMM.](https://technet.microsoft.com/itpro/surface/enroll-and-configure-surface-devices-with-semm)

### Réinitialiser le package

Un package de réinitialisation UEFI Surface est utilisé pour effectuer une seule tâche, à savoir désinscrire un appareil Surface de SEMM. Le package de réinitialisation contient des instructions signées pour supprimer le certificat SEMM du microprogramme de l’appareil et rétablir les paramètres UEFI par défaut. Comme un package de configuration UEFI Surface, un package de réinitialisation doit être signé avec le même certificat SEMM que celui qui est provisioné sur l’appareil Surface. Lorsque vous créez un package de réinitialisation SEMM, vous devez fournir le numéro de série de l’appareil Surface que vous avez l’intention de réinitialiser. Les packages de réinitialisation SEMM ne sont pas universels et sont spécifiques à un appareil.

### Demande de récupération

Dans certains scénarios, il peut être impossible d’utiliser un package de réinitialisation UEFI Surface. (Par exemple, si Windows devient inutilisable sur l’appareil Surface.) Dans ces scénarios, vous pouvez désinscrire l’appareil Surface de SEMM via la **page** Gestion de l’entreprise de Surface UEFI (illustré à la figure 5) avec une opération de demande de récupération.

![Lancer une demande de récupération SEMM](images/surface-ent-mgmt-fig7-semmrecovery.png "Initiate a SEMM recovery request")

*Figure5. Lancer une demande de récupération SEMM sur la page Gestion de l’entreprise*

Lorsque vous utilisez le processus de la page **Gestion** de l’entreprise pour réinitialiser SEMM sur un appareil Surface, une demande de réinitialisation vous est fournie. Cette demande de réinitialisation peut être enregistrée en tant que fichier sur un lecteur USB, copiée sous forme de texte ou lue en tant que code QR avec un appareil mobile pour être facilement envoyé par courrier électronique ou par message électronique. Utilisez l’option de demande de réinitialisation UEFI Microsoft Surface pour charger un fichier de demande de réinitialisation ou entrez le texte de la demande de réinitialisation ou le code QR. Microsoft Surface UEFI Configurator génère un code de vérification qui peut être entré sur l’appareil Surface. Si vous entrez le code sur l’appareil Surface et cliquez sur **Redémarrer,** l’appareil sera désinstauré de SEMM. 

>[!NOTE]
>Une demande de réinitialisation expire deux heures après sa création.

Pour obtenir une walkthrough pas à pas de la façon de désinscrire des appareils Surface à partir de SEMM, voir [Désinscrire](https://technet.microsoft.com/itpro/surface/unenroll-surface-devices-from-semm)les appareils Surface de SEMM.

## Conditions requises pour les certificats du mode Gestion de l’entreprise Surface
L’utilisation de SEMM avec microsoft Surface UEFI Configurator nécessite un certificat pour vérifier la signature des fichiers de configuration avant que les paramètres UEFI ne soient appliqués. Ce certificat garantit qu’une fois qu’un appareil est inscrit au SEMM, seuls les packages créés avec le certificat approuvé peuvent être utilisés pour modifier les paramètres de l’UEFI.

>[!NOTE]
>Le certificat SEMM est requis pour effectuer toute modification des paramètres SEMM ou SURFACE UEFI sur les appareils Surface inscrits. Si le certificat SEMM est endommagé ou perdu, seMM ne peut pas être supprimé ou réinitialisé. Gérez votre certificat SEMM en conséquence avec une solution appropriée pour la sauvegarde et la récupération.

Les packages créés avec l’outil Microsoft Surface UEFI Configurator sont signés avec un certificat. Ce certificat garantit qu’une fois qu’un appareil est inscrit au SEMM, seuls les packages créés avec le certificat approuvé peuvent être utilisés pour modifier les paramètres de l’UEFI. 
### Paramètres de certificat recommandés
Les paramètres suivants sont recommandés pour le certificat SEMM :

* **Algorithme de clé** – RSA 
* **Longueur de clé** – 2048
* **Algorithme de hachage** – SHA-256
* **Type** – Authentification SSL Server
* **Utilisation de la** clé : signature numérique, chiffrement de clé
* **Fournisseur** – Microsoft Enhanced RSA et AES Cryptographic Provider
* **Date d’expiration** : 15 mois après la création du certificat
* **Stratégie d’exportation de clé** : exportable

Il est également recommandé que le certificat SEMM soit authentifié dans une architecture d’infrastructure à clé publique (PKI) à deux niveaux dans laquelle l’autorité de certification intermédiaire est dédiée au SEMM, ce qui permet la révocation des certificats. Pour plus d’informations sur une configuration pKI à deux niveaux, voir Guide de laboratoire de test : Déploiement d’une hiérarchie [PKI Two-Tier AD CS.](https://technet.microsoft.com/library/hh831348)

### Certificat auto-signé 
Vous pouvez utiliser l’exemple de script PowerShell suivant pour créer un certificat auto-signé à utiliser dans des scénarios de preuve de concept.
Pour utiliser ce script, copiez le texte suivant dans le Bloc-notes et enregistrez le fichier en tant que script PowerShell (.ps1). 

> [!NOTE]
> Ce script crée un certificat avec un mot de passe de `12345678` . Le certificat généré par ce script n’est pas recommandé pour les environnements de production.
  
```powershell
if (-not (Test-Path "Demo Certificate"))  { New-Item -ItemType Directory -Force -Path "Demo Certificate" }
if (Test-Path "Demo Certificate\TempOwner.pfx") { Remove-Item "Demo Certificate\TempOwner.pfx" }

# Generate the Ownership private signing key with password 12345678
$pw = ConvertTo-SecureString "12345678" -AsPlainText -Force

$TestUefiV2 = New-SelfSignedCertificate `
  -Subject "CN=Surface Demo Kit, O=Contoso Corporation, C=US" `
  -Type SSLServerAuthentication `
  -HashAlgorithm sha256 `
  -KeyAlgorithm RSA `
  -KeyLength 2048 `
  -KeyUsage KeyEncipherment `
  -KeyUsageProperty All `
  -Provider "Microsoft Enhanced RSA and AES Cryptographic Provider" `
  -NotAfter (Get-Date).AddYears(25) `
  -TextExtension @("2.5.29.37={text}1.2.840.113549.1.1.1") `
  -KeyExportPolicy Exportable

$TestUefiV2 | Export-PfxCertificate -Password $pw -FilePath "Demo Certificate\TempOwner.pfx"
```

>[!IMPORTANT]
>Pour une utilisation avec SEMM et Microsoft Surface UEFI Configurator, le certificat doit être exporté avec la clé privée et avec la protection par mot de passe. Microsoft Surface UEFI Configurator vous invite à sélectionner le fichier de certificat SEMM (.pfx) et le mot de passe du certificat lorsque cela est nécessaire.

1.  Créez un dossier sur votre lecteur C: où vous enregistrerez le script . par exemple, C:\SEMM.
2.  Copiez l’exemple de script dans le Bloc-notes ou l’éditeur de texte équivalent et enregistrez le fichier en tant que script PowerShell (.ps1).
3.  Connectez-vous à votre PC avec les informations d’identification de l’administrateur et ouvrez une session PowerShell avec élévation de niveaux.
4.  Assurez-vous que vos autorisations sont définies pour autoriser l’exécuter. Par défaut, l’exécution des scripts est bloquée, sauf si vous modifiez la stratégie d’exécution. Pour plus d’informations, voir [À propos des stratégies d’exécution.](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies)
5.  À l’invite de commandes, entrez le chemin d’accès complet du script, puis appuyez sur Entrée. Le script crée un certificat de démonstration nommé TempOwner.pfx.

Vous pouvez également créer votre propre certificat auto-signé à l’aide de PowerShell. Pour plus d’informations, voir la documentation PowerShell suivante : [New-SelfSignedCertificate](https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate).




>[!NOTE]
>Pour les organisations qui utilisent une racine hors connexion dans leur infrastructure PKI, microsoft Surface UEFI Configurator doit être exécuté dans un environnement connecté à l’ac racine pour authentifier le certificat SEMM. Les packages générés par microsoft Surface UEFI Configurator peuvent être transférés en tant que fichiers et peuvent par conséquent être transférés en dehors de l’environnement réseau hors connexion avec un stockage amovible, tel qu’une clé USB.

### FAQ sur la gestion des certificats

La durée *minimale recommandée* est de 15 mois. Vous pouvez utiliser un certificat qui expire dans moins de 15 mois ou un certificat qui expire dans plus de 15 mois.

>[!NOTE] 
>Lorsqu’un certificat expire, il n’est pas renouvelé automatiquement. 


**Un certificat expiré affectera-t-il les fonctionnalités des appareils inscrits à LAMM ?**<br><br>
Non, un certificat n’a d’impact que sur les tâches de gestion des administrateurs informatiques dans SEMM et n’a aucun effet sur les fonctionnalités de l’appareil à l’expiration.


**Le package SEMM et le certificat devront-ils être mis à jour sur tous les ordinateurs qui en ont ?**

Si vous souhaitez que la réinitialisation ou la récupération SEMM fonctionne, le certificat doit être valide et non expiré. 

**Est-il possible de créer des packages de réinitialisation en bloc pour chaque surface que nous commandeons ? Est-il possible de construire une machine qui réinitialise tous les ordinateurs de notre environnement ?**

Les exemples PowerShell qui créent un package de config pour un type d’appareil spécifique peuvent également être utilisés pour créer un package de réinitialisation indépendant du numéro de série. Si le certificat est toujours valide, vous pouvez créer un package de réinitialisation à l’aide de PowerShell pour réinitialiser SEMM.

## Historique des versions

### Version 2.79.139.0

Cette version de SEMM inclut :
- Prise en charge de Surface Pro 7+
- Améliorations de l’expérience utilisateur


### Version 2.78.139.0

Cette version de SEMM inclut :

- Prise en charge de Surface Laptop Go et Surface Pro X
- Notifications pour la nouvelle version
- Possibilité de créer des packages personnalisés pour modifier la propriété
- Résolutions de bogues

### Version 2.73.136.0

Cette version de SEMM inclut :

- L’audio peut désormais être désactivé sur Surface Hub2S à l’aide de SEMM
- Prise en charge de Surface Pro X pour la station d’accueil 2
- Prise en charge du Gestionnaire UEFI pour les opérations liées à Dock 2
- Correctif de bogue du package de réinitialisation de Surface Go
- Prise en charge de la migration des appareils Surface Hub 2 de Windows 10 Team OS vers Windows 10 Professionnel ou Entreprise.

### Version 2.71.139.0

Cette version de SEMM ajoute la prise en charge des fonctionnalités de gestion de Surface Dock 2 pour Surface Book 3, Surface Laptop 3 et Surface Pro 7, notamment :

- Activation des ports audio (verrouillage/déverrouillage), Ethernet et USB
- Possibilité de créer des packages de station d’accueil pour les hôtes authentifiés et non authentifiés

### Version 2.70.130.0

Cette version de SEMM inclut :

- Prise en charge de Surface Go 2
- Prise en charge du Surface Book 3
- Résolutions de bogues


### Version 2.59.139.0

* Prise en charge des modèles Surface Pro 7, Surface Pro X et Surface Laptop 3 13,5 pouces et 15 pouces avec processeur Intel. Remarque : le processeur AMD Surface Laptop 3 15 pouces n’est pas pris en charge.

- Prise en charge de la fonctionnalité Veille sur l’alimentation

### Version 2.54.139.0
* Prise en charge de Surface Hub 2S
* Résolutions de bogues

### Version 2.43.136.0
* Prise en charge pour activer/désactiver la simulation multithreating 
* Options distinctes pour le WiFi et les Bluetooth pour certains appareils 
* Limite de batterie supprimée pour Surface Studio 

### Version 2.26.136.0
* Ajouter la prise en charge de Surface Studio 2
* Fonctionnalité de limite de batterie

### Version 2.21.136.0
* Ajouter la prise en charge de Surface Pro 6
* Ajouter la prise en charge de Surface Laptop 2

### Version 2.14.136.0
* Ajouter la prise en charge de Surface Go

### Version2.9.136.0
* Ajouter la prise en charge de Surface Book 2
* Ajouter la prise en charge de Surface Pro LTE
* Améliorations de l’accessibilité

### Version 1.0.74.0
* Ajouter la prise en charge de Surface Laptop
* Ajouter une prise en charge à Surface Pro
* Résolutions de bogues et amélioration générale

## Rubriques associées

- [Inscrire et configurer les appareilsSurface auprès de SEMM](enroll-and-configure-surface-devices-with-semm.md)
- [Désinscrire les appareils Surface de SEMM](unenroll-surface-devices-from-semm.md)
- [Sécuriser les ports de Surface Dock 2 avec SEMM](secure-surface-dock-ports-semm.md)
