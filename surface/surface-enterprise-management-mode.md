---
title: Mode de gestion des entreprises de surface (surface)
description: Découvrez comment cette fonctionnalité des appareils surface avec la surface UEFI vous permet de sécuriser et de gérer les paramètres de microprogramme au sein de votre organisation.
keywords: UEFI, configurer, microprogramme, sécurité SEMM
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
ms.date: 09/01/2020
ms.openlocfilehash: 239b5e4659ff48e6c0fd9d2fca03341eadb9a27d
ms.sourcegitcommit: 78694f3958117a339a28d3a5854908181f1b65d7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993664"
---
# Microsoft surface Enterprise Management mode

Le mode Microsoft surface Enterprise Management (SEMM) est une fonctionnalité des appareils surface dotés de surface UEFI qui vous permet de sécuriser et de gérer les paramètres du microprogramme au sein de votre organisation. Avec SEMM, les professionnels de l’informatique peuvent préparer des configurations de paramètres UEFI et les installer sur un appareil surface. Outre la possibilité de configurer les paramètres UEFI, SEMM utilise également un certificat pour protéger la configuration contre toute falsification ou suppression non autorisée. SEMM est une obligation d’être en mesure de migrer un surface Hub 2 vers Windows 10 professionnel ou entreprise.

>[!NOTE]
>SEMM est uniquement disponible sur les appareils dotés d’un microprogramme surface UEFI. Cela comprend la plupart des appareils surface, y compris surface Pro 7, surface Pro X, surface Hub 2 et les références SKU de surface Laptop 3 avec un processeur Intel. SEMM n’est pas pris en charge sur la référence de 15 pouces surface pour le processeur AMD (disponible uniquement pour les points de vente). 

Lorsque les appareils de surface sont configurés par SEMM et protégés par le certificat SEMM, ils sont considérés comme *inscrits* dans SEMM. Lorsque le certificat SEMM est supprimé et que le contrôle des paramètres UEFI est retourné à l’utilisateur de l’appareil, le périphérique surface est considéré comme non *inscrit* dans SEMM.

Il existe deux options d’administration que vous pouvez utiliser pour gérer SEMM et inscrire les appareils surface: un outil autonome ou une intégration avec Microsoft Endpoint Configuration Manager. L’outil autonome SEMM, appelé Microsoft surface UEFI Configurator, est décrit dans cet article. Pour plus d’informations sur la gestion de SEMM avec Microsoft Endpoint Configuration Manager, voir [utiliser Microsoft Endpoint Configuration Manager pour gérer les appareils avec SEMM](https://technet.microsoft.com/itpro/surface/use-system-center-configuration-manager-to-manage-devices-with-semm).


## Configurateur Microsoft surface UEFI

L’espace de travail principal de SEMM est Microsoft surface UEFI Configurator, comme illustré dans la figure 1. Le programme de configuration de Microsoft surface UEFI est un outil qui permet de créer des packages Windows Installer (. msi) ou des images WinPE utilisés pour inscrire, configurer et désinscrire SEMM sur un appareil surface. Ces packages contiennent un fichier de configuration dans lequel les paramètres de UEFI sont spécifiés. Les packages SEMM contiennent également un certificat, qui est installé et stocké dans le microprogramme et utilisé pour vérifier la signature des fichiers de configuration avant l’application des paramètres UEFI.

>[!NOTE]
>Vous pouvez désormais utiliser le configurateur surface UEFI et SEMM pour gérer les ports sur surface Dock 2. Pour en savoir plus, voir [Secure surface Dock 2 ports avec SEMM](secure-surface-dock-ports-semm.md).

![Configurateur Microsoft surface UEFI](images/surface-ent-mgmt-fig1-uefi-configurator.png "Microsoft Surface UEFI Configurator")

*Figure1. Configurateur Microsoft surface UEFI*


Vous pouvez utiliser l’outil de configuration de Microsoft surface UEFI en trois modes:

* [Package de configuration de surface UEFI](#configuration-package). Utilisez ce mode pour créer un package de configuration de surface UEFI afin d’inscrire un appareil surface dans SEMM et de configurer les paramètres UEFI sur des appareils inscrits.
* [Package de réinitialisation UEFI surface](#reset-package). Utilisez ce mode pour désinscrire un appareil surface à partir de SEMM.
* [Demande de récupération de surface UEFI](#recovery-request). Utilisez ce mode pour répondre à une demande de récupération et annuler l’inscription d’un appareil surface à partir de SEMM où une opération de réinitialisation du package échoue.


#### Télécharger le configurateur Microsoft surface UEFI

Vous pouvez télécharger Microsoft surface configurateur à partir de la page [Outils surface pour cette application](https://www.microsoft.com/download/details.aspx?id=46703) dans le centre de téléchargement Microsoft.

### Package de configuration

Les packages de configuration de surface UEFI constituent le principal mécanisme de mise en œuvre et de gestion des SEMM sur les appareils surface. Ces packages contiennent un fichier de configuration des paramètres UEFI spécifiés lors de la création du package dans le programme de configuration de Microsoft surface UEFI et un fichier de certificat, comme illustré dans la figure 2. Lorsqu’un package de configuration est exécuté pour la première fois sur un appareil surface qui n’est pas déjà inscrit dans SEMM, il met en service le fichier de certificat dans le microprogramme de l’appareil et inscrit le périphérique dans SEMM. Lors de l’inscription d’un appareil dans SEMM, vous êtes invité à confirmer l’opération en fournissant les deux derniers chiffres de l’empreinte numérique du certificat SEMM avant que le fichier de certificat ne soit stocké et que l’inscription puisse aboutir. Ce message de confirmation nécessite que l’utilisateur puisse se présenter physiquement auprès de l’appareil au moment de l’inscription pour effectuer la confirmation.

![Sécuriser un package de configuration SEMM avec un certificat](images/surface-ent-mgmt-fig2-securepackage.png "Secure a SEMM configuration package with a certificate")

*Figure2. Sécuriser un package de configuration SEMM avec un certificat*

Pour plus d’informations sur la configuration requise pour le certificat SEMM, voir la section [conditions de certification du mode de gestion des entreprises de surface](#surface-enterprise-management-mode-certificate-requirements) dans cet article.

>[!NOTE]
>Vous pouvez également spécifier un mot de passe UEFI avec SEMM requis pour afficher les pages de **sécurité**, les **appareils**, la **configuration de démarrage**ou les pages de gestion d' **entreprise** de surface UEFI.

Une fois qu’un appareil est inscrit dans SEMM, le fichier de configuration est lu et les paramètres spécifiés dans le fichier sont appliqués à UEFI. Lorsque vous exécutez un package de configuration sur un appareil déjà inscrit dans SEMM, la signature du fichier de configuration est comparée au certificat stocké dans le microprogramme du périphérique. Si la signature ne correspond pas, aucune modification n’est appliquée à l’appareil.

### Activer ou désactiver des appareils dans surface UEFI avec SEMM

La liste suivante répertorie tous les appareils disponibles que vous pouvez gérer dans SEMM:

* Port USB d’amarrage
* Audio intégré
* DGPU
* Type Cover
* Carte micro SD
* Caméra frontale
* Caméra arrière
* Caméra infrarouge, pour Windows Hello
* Bluetooth uniquement
* Wi-Fi et Bluetooth
*              LTE           

 >[!NOTE]
>Les appareils intégrés qui s’affichent dans la page périphériques UEFI peuvent varier en fonction de votre appareil ou de votre environnement d’entreprise. Par exemple, la page périphériques UEFI n’est pas prise en charge sur surface Pro X. LTE apparaît uniquement sur les appareils dotés de LTE. 
### Configurer les paramètres avancés avec SEMM
**Tableau1. Paramètres avancés**

| Paramètre                            | Description                                                                                                                                                                                        |
| ---------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| IPv6 pour démarrage PXE                  | Vous permet de gérer la prise en charge du protocole IPv6 pour le démarrage PXE. Si vous ne configurez pas ce paramètre, la prise en charge D’ipv6 pour le démarrage PXE est désactivée.                                                                               |
| Autre démarrage                     | Vous permet de gérer l’utilisation d’un autre ordre de démarrage pour démarrer directement sur un appareil USB ou Ethernet en appuyant sur le bouton du volume et sur le bouton d’alimentation lors du démarrage. Si vous ne configurez pas ce paramètre, le démarrage alternatif est activé. |
| Verrou d’ordre de démarrage                    | Vous permet de verrouiller l’ordre de démarrage pour empêcher les modifications. Si vous ne configurez pas ce paramètre, le verrouillage du bon de démarrage est désactivé.                                                                                                        |
| Démarrage USB                           | Vous permet de gérer le démarrage sur des périphériques USB. Si vous ne configurez pas ce paramètre, le démarrage USB est activé.                                                                                                                 |
| Pile réseau                      | Vous permet de gérer les paramètres de démarrage de la pile réseau. Si vous ne configurez pas ce paramètre, la possibilité de gérer les paramètres de démarrage de la pile réseau est désactivée.                                                                                                           |
| Alimentation automatique                      | Vous permet de gérer les paramètres de démarrage automatique de l’alimentation. Si vous ne configurez pas ce paramètre, la fonction d’alimentation automatique est activée.                                                                                                        |
| Multi-Threading simultané (SMT) | Vous permet de gérer le multithreading simultané (SMT) pour activer ou désactiver l’hyperthreading. Si vous ne configurez pas ce paramètre, SMT est activé.                                                  |
|Activer le nombre maximal de batteries| Vous permet de gérer les fonctionnalités de limite de batterie. Si vous ne configurez pas ce paramètre, la limite de batterie est activée. |
| Sécurité                           | Affiche la page de **sécurité** de surface UEFI. Si vous ne configurez pas ce paramètre, la page sécurité s’affiche.                                                                                                                 |
| Périphériques                            | Affiche la page **périphériques** UEFI. Si vous ne configurez pas ce paramètre, la page périphériques s’affiche.                                                                                                                     |
| Démarrage                               | Affiche la page de **démarrage** de surface UEFI. Si vous ne configurez pas ce paramètre, la page de démarrage s’affiche.                                                                                                                                                            |
| DateTime                           | Affiche la page **DateTime** UEFI surface. Si vous ne configurez pas ce paramètre, la page DateHeure s’affiche.                                                                                                                |
| EnableOSMigration                          | Vous permet de migrer surface Hub 2 de l’équipe Windows 10 vers Windows 10 professionnel ou entreprise. Si vous ne configurez pas ce paramètre, les appareils surface Hub 2 peuvent uniquement exécuter le système d’exploitation Windows 10.   Remarque: le double démarrage entre l’équipe Windows 10 et Windows 10 professionnel entreprise n’est pas disponible sur surface Hub 2.                                                                                                           |


>[!NOTE]
>Lorsque vous créez un package de configuration SEMM, deux caractères s’affichent dans la page **réussite** , comme illustré dans la figure 3.

![Affichage de l’empreinte numérique du certificat](images/surface-ent-mgmt-fig5-success.png "Certificate thumbprint display")

*Figure3. Afficher les deux derniers caractères de l’empreinte numérique du certificat dans la page réussite*

Ces caractères sont les deux derniers caractères de l’empreinte numérique du certificat qui doivent être écrits ou enregistrés. Les caractères sont requis pour confirmer l’inscription dans SEMM sur un appareil surface, comme illustré dans la figure 4.

![Confirmation d’inscription dans SEMM](images/surface-ent-mgmt-fig6-enrollconfirm.png "Enrollment confirmation in SEMM")

*Figure4. Confirmation d’inscription dans SEMM avec l’empreinte numérique du certificat SEMM*

>[!NOTE]
>Les administrateurs ayant accès au fichier de certificat (. pfx) peuvent lire l’empreinte numérique à tout moment en ouvrant le fichier. pfx dans CertMgr. Pour afficher l’empreinte numérique avec CertMgr, suivez ce processus:
>1. Cliquez avec le bouton droit sur le fichier. pfx, puis cliquez sur **ouvrir**.
>2. Développez le dossier dans le volet de navigation.
>3. Cliquez sur **Certificats**.
>4. Cliquez avec le bouton droit sur votre certificat dans le volet principal, puis cliquez sur **ouvrir**.
>5. Cliquez sur l’onglet **Détails** .
>6. **Les** **Propriétés ne** doivent être sélectionnées que dans le menu déroulant **Afficher** .
>7. Sélectionnez l' **empreinte**de champ.

Pour inscrire un appareil surface dans SEMM ou appliquer la configuration UEFI à partir d’un package de configuration, il vous suffit d’exécuter le fichier. msi doté de privilèges d’administration sur le périphérique surface prévu. Vous pouvez utiliser les technologies de déploiement d’application ou de déploiement du système d’exploitation, telles que le [Gestionnaire de configuration de point de terminaison Microsoft](https://technet.microsoft.com/library/mt346023) ou le [Kit de développement logiciel Microsoft Deployment](https://technet.microsoft.com/windows/dn475741). Lors de l’inscription d’un appareil dans SEMM, vous devez être présent physiquement pour confirmer l’inscription sur l’appareil. L’interaction utilisateur n’est pas requise lorsque vous appliquez une configuration à des appareils déjà inscrits dans SEMM.

Pour obtenir une procédure pas à pas illustrant l’inscription d’un appareil surface dans SEMM ou l’application d’une configuration UEFI de surface à SEMM, voir [inscrire et configurer des appareils de surface avec SEMM](https://technet.microsoft.com/itpro/surface/enroll-and-configure-surface-devices-with-semm).

### Réinitialiser le package

Un package de réinitialisation de surface UEFI est utilisé pour effectuer une seule tâche, pour annuler l’inscription d’un appareil surface à partir de SEMM. Le package de réinitialisation contient des instructions signées permettant de supprimer le certificat SEMM du microprogramme de l’appareil et de réinitialiser les paramètres UEFI par défaut. À l’instar d’un package de configuration UEFI de surface, un package de réinitialisation doit être signé avec le même certificat SEMM configuré sur le périphérique surface. Lorsque vous créez un package de réinitialisation SEMM, vous devez fournir le numéro de série de l’appareil surface que vous voulez réinitialiser. SEMM les packages de réinitialisation ne sont pas universels et sont spécifiques à un appareil.

### Demande de récupération

Dans certains cas, il est possible qu’il soit impossible d’utiliser un package de réinitialisation UEFI surface. (Par exemple, si Windows est devenu inutilisable sur le périphérique surface.) Dans ces scénarios, vous pouvez désinscrire le périphérique surface d’SEMM via la page de gestion de l' **entreprise** de surface UEFI (illustrée dans la figure 5) avec une opération de requête de récupération.

![Lancer une demande de récupération de SEMM](images/surface-ent-mgmt-fig7-semmrecovery.png "Initiate a SEMM recovery request")

*Figure5. Lancer une demande de récupération de SEMM sur la page gestion d’entreprise*

Lorsque vous utilisez le processus sur la page **gestion d’entreprise** pour réinitialiser SEMM sur un appareil surface, vous avez reçu une demande de réinitialisation. Cette demande de réinitialisation peut être enregistrée sous forme de fichier sur un lecteur USB, copié en tant que texte ou lue en tant que code QR avec un appareil mobile pour être facilement appelé par courrier électronique ou message. Utilisez l’option de demande de réinitialisation du configurateur Microsoft surface UEFI pour charger un fichier de demande de réinitialisation ou entrez le texte de demande de réinitialisation ou le code QR. Le configurateur Microsoft surface UEFI génère un code de vérification qui peut être entré sur le périphérique surface. Si vous entrez le code sur le périphérique surface et cliquez sur **redémarrer**, l’appareil est désinscrit de SEMM. 

>[!NOTE]
>Une demande de réinitialisation expire deux heures après sa création.

Pour obtenir une procédure pas à pas illustrant l’inscription de périphériques surface à partir de SEMM, voir [désinscription des appareils de surface d’SEMM](https://technet.microsoft.com/itpro/surface/unenroll-surface-devices-from-semm).

## Exigences de certificat en mode de gestion de surface entreprise
L’utilisation de SEMM avec le configurateur Microsoft surface UEFI nécessite un certificat pour vérifier la signature de fichiers de configuration avant que les paramètres UEFI puissent être appliqués. Ce certificat vérifie qu’une fois qu’un appareil est inscrit dans SEMM, seuls les packages créés avec le certificat approuvé peuvent être utilisés pour modifier les paramètres de UEFI.

>[!NOTE]
>Le certificat SEMM est requis pour effectuer une modification apportée aux paramètres d’SEMM ou de surface UEFI sur des appareils surface inscrits. Si le certificat SEMM est endommagé ou perdu, SEMM ne peut pas être supprimé ou réinitialisé. Gérez votre certificat SEMM en conséquence avec une solution appropriée pour la sauvegarde et la récupération.

Les packages créés à l’aide de l’outil de configuration du configurateur Microsoft surface UEFI sont signés avec un certificat. Ce certificat vérifie qu’une fois qu’un appareil est inscrit dans SEMM, seuls les packages créés avec le certificat approuvé peuvent être utilisés pour modifier les paramètres de UEFI. 
### Paramètres de certificat recommandés
Les paramètres suivants sont recommandés pour le certificat SEMM:

* **Algorithme de clé** -RSA 
* **Longueur** de la clé – 2048
* **Algorithme de hachage** -SHA-256
* **Type** – authentification du serveur SSL
* **Utilisation** de la clé – signature numérique, chiffrement de la clé
* **Fournisseur** -fournisseur de services cryptographiques Microsoft Enhanced RSA et AES
* **Date d’expiration** : 15 mois de création de certificats
* **Politique d’exportation clé** -exportable

Il est également recommandé d’authentifier le certificat SEMM dans une architecture de l’infrastructure à clé publique (PKI) sur deux couches, dans laquelle l’autorité de certification intermédiaire est dédiée à SEMM, activant la révocation des certificats. Pour plus d’informations sur la configuration d’une PKI sur deux couches, voir le [Guide du laboratoire de test: déploiement d’une hiérarchie PKI à deux couches AD CS](https://technet.microsoft.com/library/hh831348).

### Certificat auto-signé 
Vous pouvez utiliser l’exemple de script PowerShell suivant pour créer un certificat auto-signé à utiliser dans les scénarios de validation.
Pour utiliser ce script, copiez le texte suivant dans le bloc-notes et enregistrez le fichier en tant que script PowerShell (. ps1). Remarque: ce script crée un certificat dont le mot de passe est `12345678` . Le certificat généré par ce script n’est pas recommandé pour les environnements de production.
  
   ```
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
>Pour l’utilisation de SEMM et du configurateur Microsoft surface UEFI, le certificat doit être exporté à l’aide de la clé privée et de la protection par mot de passe. Le programme de configuration de Microsoft surface UEFI vous invite à sélectionner le fichier de certificat SEMM (. pfx) et le mot de passe de certificat lorsque ce dernier est requis.

1.  Créez un dossier sur votre lecteur C:, à partir duquel vous allez enregistrer le script. par exemple, C:\SEMM.
2.  Copiez l’exemple de script dans le bloc-notes ou l’éditeur de texte équivalent, puis enregistrez le fichier en tant que script PowerShell (. ps1).
3.  Connectez-vous à votre PC à l’aide d’informations d’identification d’administrateur, puis ouvrez une session PowerShell avec élévation de privilèges.
4.  Vérifiez que vos autorisations sont définies pour autoriser l’exécution des scripts. Par défaut, les scripts ne peuvent pas être en cours d’exécution sauf si vous modifiez la stratégie d’exécution. Pour en savoir plus, voir [à propos des stratégies d’exécution](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies).
5.  À l’invite de commandes, entrez le chemin d’accès complet du script, puis appuyez sur entrée. Le script crée un certificat de démonstration appelé TempOwner. pfx.

Vous pouvez également créer votre propre certificat auto-signé à l’aide de PowerShell. Pour plus d’informations, consultez la documentation PowerShell suivante: [New-SelfSignedCertificate](https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate).




>[!NOTE]
>Pour les organisations qui utilisent une racine hors connexion dans leur infrastructure PKI, le configurateur Microsoft surface UEFI doit être exécuté dans un environnement connecté à l’autorité de certification racine pour authentifier le certificat SEMM. Les packages générés par le Configurator du Configurateur de surface Microsoft peuvent être transférés en tant que fichiers et peuvent donc être transférés hors de l’environnement réseau hors connexion avec un support amovible, tel qu’un stick USB.

### FAQ sur la gestion des certificats

La longueur *minimum* recommandée est 15 mois. Vous pouvez utiliser un certificat qui expire dans moins de 15 mois ou utiliser un certificat qui expire dans plus de 15 mois.

>[!NOTE] 
>La date d’expiration d’un certificat n’est pas automatiquement renouvelé. 


**Un certificat expiré affectera-t-il la fonctionnalité des périphériques inscrits par le SEMM?**<br><br>
Non, un certificat affecte uniquement les tâches de gestion des administrateurs informatiques dans SEMM et n’a aucun effet sur les fonctionnalités de l’appareil lorsqu’il arrive à expiration.


**Le package et le certificat SEMM doivent-ils être mis à jour sur tous les ordinateurs qui l’utilisent?**

Si vous voulez que la réinitialisation ou la restauration de SEMM fonctionne, le certificat doit être valide et non expiré. 

**Est-il possible de créer des packages de réinitialisation en bloc pour chaque surface que nous commande? Est-il possible de générer une configuration qui réinitialise tous les ordinateurs de notre environnement?**

Les exemples PowerShell qui créent un package de configuration pour un type d’appareil spécifique peuvent également être utilisés pour créer un package de réinitialisation qui est indépendant du numéro de série. Si le certificat est toujours valide, vous pouvez créer un package de réinitialisation en utilisant PowerShell pour réinitialiser SEMM.

## Historique des versions


### Version 2.73.136.0

Cette version de SEMM inclut les éléments suivants:

- L’audio peut désormais être désactivé sur surface Hub2S à l’aide de SEMM
- Prise en charge de surface Pro X pour Dock 2
- Prise en charge du gestionnaire UEFI pour les opérations connexes Dock 2
- Correctif pour le bogue de réinitialisation du package surface Go
- La prise en charge de la migration des appareils surface Hub 2 du système d’exploitation Windows 10 vers Windows 10 professionnel ou entreprise.

### Version 2.71.139.0

Cette version de SEMM ajoute une prise en charge des fonctionnalités de gestion de l’ancrage de surface 2 pour le livre surface 3, surface Laptop 3 et surface Pro 7, y compris:

- Activation de l’audio (verrouillage/déverrouillage), ports Ethernet et USB
- Possibilité de créer des packages de dock pour les hôtes authentifiés et non authentifiés

### Version 2.70.130.0

Cette version de SEMM inclut les éléments suivants:

- Prise en charge de surface Go 2
- Prise en charge de surface Book 3
- Correction de bogues


### Version 2.59.139.0

* La prise en charge des modèles de surface Pro 7, de surface Pro X et de surface Laptop 3 13,5 et 15 pouces avec le processeur Intel. Remarque: le processeur AMD surface Laptop 3 15 "n’est pas pris en charge.

- Prise en charge de la fonctionnalité de mise en éveil

### Version 2.54.139.0
* Prise en charge de surface Hub 2
* Correction de bogues

### Version 2.43.136.0
* Prise en charge de l’activation/désactivation de la simulatenousing 
* Options distinctes pour Wi-Fi et Bluetooth pour certains appareils 
* Limite de batterie supprimée pour surface Studio 

### Version 2.26.136.0
* Ajouter la prise en charge de surface Studio 2
* Fonctionnalité de limite de batterie

### Version 2.21.136.0
* Ajouter la prise en charge de surface Pro 6
* Ajouter la prise en charge de surface Laptop 2

### Version 2.14.136.0
* Ajouter la prise en charge des Go de surface

### Version2.9.136.0
* Ajouter la prise en charge de surface Book 2
* Ajouter la prise en charge de surface Pro
* Améliorations apportées à l’accessibilité

### Version 1.0.74.0
* Ajouter la prise en charge de l’ordinateur portable surface
* Ajouter la prise en charge de surface Pro
* Correction de bogues et amélioration générale

## Rubriquesassociées

- [Inscrire et configurer les appareilsSurface auprès de SEMM](enroll-and-configure-surface-devices-with-semm.md)
- [Désinscrire les appareils Surface de SEMM](unenroll-surface-devices-from-semm.md)
- [Sécuriser les ports de Surface Dock 2 avec SEMM](secure-surface-dock-ports-semm.md)
