---
title: Gestion Intune des paramètres de surface UEFI
description: Cet article explique comment configurer un environnement DFCI dans Microsoft Intune et gérer les paramètres de microprogramme pour les appareils Surface ciblés.
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 10/09/2020
ms.reviewer: jesko
manager: laurawi
ms.audience: itpro
appliesto:
- Surface Pro 7+
- Surface Pro 7
- Surface Pro X
- Surface Laptop 3
- Surface Book 3
- Surface Laptop Go
ms.openlocfilehash: dde34126c726ec0ac8093a665804c4fb0f639e3e
ms.sourcegitcommit: 1053479c191fd10651d31a466fad1769fb0cd28b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/16/2021
ms.locfileid: "11271568"
---
# Gestion Intune des paramètres de surface UEFI

## Introduction

La possibilité de gérer les appareils à partir du cloud a considérablement simplifié le déploiement et la mise en service informatiques tout au long du cycle de vie. Avec les profils DFCI (Device Firmware Configuration Interface) intégrés à [Microsoft Intune,](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)la gestion UEFI Surface étend la pile de gestion moderne jusqu’au niveau matériel UEFI. DFCI prend en charge l’approvisionnement sans contact, élimine les mots de passe BIOS, contrôle les paramètres de sécurité, y compris les options de démarrage et les périphériques intégrés, et constitue la base des scénarios de sécurité avancés à l’avenir. Pour obtenir des réponses aux questions fréquemment posées, voir Ignite 2019 : Annonce de la gestion à distance des [paramètres UEFI Surface à partir d’Intune.](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333)

### Arrière-plan

Comme tout ordinateur exécutant Windows 10, les appareils Surface s’appuient sur du code stocké dans le SoC qui permet à l’UC de s’interfacer avec des disques durs, des périphériques d’affichage, des ports USB et d’autres appareils. Les programmes stockés dans cette mémoire en lecture seule (ROM) sont appelés microprogrammes (alors que les programmes stockés dans des supports dynamiques sont appelés logiciels).

Contrairement aux autres appareils Windows 10 disponibles sur le marché aujourd’hui, Surface offre aux administrateurs informatiques la possibilité de configurer et de gérer le microprogramme via un ensemble enrichi de paramètres de configuration UEFI. Cela fournit une couche de contrôle matériel en plus de la gestion des stratégies logicielles telle qu’implémentée via les stratégies de gestion des périphériques mobiles (MDM), Configuration Manager ou stratégie de groupe. Par exemple, les organisations déployant des appareils dans des zones hautement sécurisées avec des informations sensibles peuvent empêcher l’utilisation de l’appareil photo en supprimant des fonctionnalités au niveau du matériel. Du point de vue de l’appareil, le fait de dés éteindre l’appareil photo via un paramètre de microprogramme équivaut à supprimer physiquement l’appareil photo. Comparez la sécurité ajoutée de la gestion au niveau du microprogramme à la confiance uniquement sur les paramètres logiciels du système d’exploitation. Par exemple, si vous désactivez le service audio Windows via un paramètre de stratégie dans un environnement de domaine, un administrateur local peut toujours le réactiver.

### DFCI par rapport à SEMM

Auparavant, la gestion du microprogramme nécessitait l’inscription des appareils en mode SEMM (Surface Enterprise Management Mode) avec la surcharge des tâches informatiques manuelles en cours. Par exemple, SEMM exige que le personnel technique accède physiquement à chaque PC pour entrer une broche à deux chiffres dans le cadre du processus de gestion des certificats. Bien que seMM reste une bonne solution pour les organisations dans un environnement strictement local, sa complexité et ses exigences it intensives font que son utilisation est coûteuse.

 Grâce aux fonctionnalités intégrées de gestion des microprogrammes UEFI dans Microsoft Intune, la possibilité de verrouiller le matériel est simplifiée et plus facile à utiliser avec les nouvelles fonctionnalités d’approvisionnement, de sécurité et de mise à jour simplifiée dans une seule console, désormais unifiée comme [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager). La figure suivante montre les paramètres UEFI directement sur l’appareil (à gauche) et dans la console endpoint Manager (à droite).

![Paramètres UEFI affichés sur l’appareil (à gauche) et dans la console endpoint Manager (à droite)](images/uefidfci.png)

D’une manière cruciale, DFCI permet une gestion sans intervention tactile, ce qui élimine la nécessité d’une interaction manuelle par les administrateurs informatiques. DFCI est déployé via Windows Autopilot à l’aide de la fonctionnalité profils d’appareil dans Intune. Un profil d’appareil vous permet d’ajouter et de configurer des paramètres qui peuvent ensuite être déployés sur les appareils inscrits à la gestion au sein de votre organisation. Une fois que l’appareil reçoit le profil de l’appareil, les fonctionnalités et les paramètres sont appliqués automatiquement. Exemples de profils d’appareil courants : messagerie électronique, restrictions d’appareil, VPN, Wi-Fi et modèles d’administration. DFCI est simplement un profil d’appareil supplémentaire qui vous permet de gérer les paramètres de configuration UEFI à partir du cloud sans avoir à gérer l’infrastructure locale.  

## Appareils pris en charge

DFCI est pris en charge sur les appareils suivants :

- Surface Pro 7+
- SurfacePro7
- SurfaceProX
- Surface Laptop3
- SurfaceBook3
- Surface Laptop Go

> [!NOTE]
> Surface Pro X ne prend pas en charge la gestion des paramètres DFCI pour l’appareil photo intégré, l’audio et le Wi-Fi/Bluetooth.

## Conditions préalables

- Les appareils doivent être enregistrés auprès de Windows Autopilot par un partenaire fournisseur de solutions [Microsoft Cloud (CSP)](https://partner.microsoft.com/membership/cloud-solution-provider) ou un distributeur OEM.

- Avant de configurer DFCI pour Surface, vous devez connaître les exigences de configuration d’Autopilot dans  [Microsoft Intune](https://docs.microsoft.com/intune/) et [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/) (Azure AD).

## Avant de commencer

Ajoutez vos appareils Surface cibles à un groupe de sécurité Azure AD. Pour plus d’informations sur la création et la gestion des groupes de sécurité, consultez la [documentation Intune.](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows#create-your-azure-ad-security-groups)

## Configurer la gestion DFCI pour les appareils Surface

Un environnement DFCI nécessite la configuration d’un profil DFCI qui contient les paramètres et un profil Autopilot pour appliquer les paramètres aux appareils inscrits. Un profil d’état d’inscription est également recommandé pour vous assurer que les paramètres sont bas lors de la configuration OOBE lorsque les utilisateurs démarrent l’appareil pour la première fois. Ce guide explique comment configurer l’environnement DFCI et gérer les paramètres de configuration UEFI pour les appareils Surface ciblés.

## Créer un profil DFCI

Avant de configurer les paramètres de stratégie DFCI, créez d’abord un profil DFCI et affectez-le au groupe de sécurité Azure AD qui contient vos appareils cibles.

1. Connectez-vous à votre client devicemanagement.microsoft.com.
2. Dans le Centre d’administration Microsoft Endpoint Manager, sélectionnez > **profils** de configuration > créer un profil et entrez un nom . par exemple, **stratégie de configuration DFCI.**
3. Sélectionnez **Windows 10 et les ultérieures pour** le type de plateforme.
4. Dans la liste du type de profil, sélectionnez Interface de **configuration** du microprogramme d’appareil pour ouvrir le blade DFCI contenant tous les paramètres de stratégie disponibles. Pour plus d’informations sur les paramètres DFCI, reportez-vous au tableau 1 de cette page ou à la [documentation Intune.](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows) Vous pouvez configurer les paramètres DFCI pendant le processus d’installation initial ou ultérieur en éditant le profil DFCI.

    ![Créer un profil DFCI](images/df1.png)

5. Cliquez **sur OK,** puis sélectionnez **Créer.**
6. Sélectionnez **Affectations** et sous **Sélectionner** des groupes à inclure, sélectionnez le groupe de sécurité Azure AD qui contient vos appareils cibles, comme illustré dans la figure suivante. Cliquez sur **Enregistrer**.

    ![Affecter un groupe de sécurité](images/df2a.png)

## Créer un profil Autopilot

1. Dans le Gestionnaire de points de terminaison devicemanagement.microsoft.com, sélectionnez les appareils **>'inscription Windows** et faites défiler vers le bas jusqu’aux **profils de déploiement.**
2. Sélectionnez **Créer un profil** et entrez un nom . par exemple, **mon profil Autopilot**et sélectionnez **Suivant**.
3. Sélectionnez les paramètres suivants :

    - Mode de déploiement : **piloté par l’utilisateur.**
    - Type de joint : Joint à Azure **AD.**

4. Laissez les paramètres par défaut restants inchangés et sélectionnez **Suivant,** comme illustré dans la figure suivante.

    ![Créer un profil Autopilot](images/df3b.png)

5. Dans la page Affectations, sélectionnez **Sélectionner les groupes à inclure et** cliquez sur votre groupe de sécurité Azure AD. Sélectionnez **Suivant**.
6. Acceptez le résumé, puis sélectionnez **Créer.** Le profil Autopilot est maintenant créé et affecté au groupe.

## Page Configurer l’état de l’inscription

Pour vous assurer que les appareils appliquent la configuration DFCI pendant la OOBE avant que les utilisateurs ne se connectent, vous devez configurer l’état d’inscription.

Pour plus d’informations, reportez-vous [à la page Configurer un état d’inscription.](https://docs.microsoft.com/intune/enrollment/windows-enrollment-status)


## Configurer les paramètres DFCI sur les appareils Surface

DFCI inclut un ensemble simplifié de stratégies de configuration UEFI qui fournissent un niveau supplémentaire de sécurité en verrouiller les appareils au niveau matériel. DFCI est conçu pour être utilisé conjointement avec les paramètres de gestion des appareils mobiles au niveau du logiciel. Notez que les paramètres DFCI affectent uniquement les composants matériels intégrés aux appareils Surface et ne s’étendent pas aux périphériques connectés tels que les webcams USB. (Toutefois, vous pouvez utiliser des stratégies de restriction d’appareil dans Intune pour désactiver l’accès aux périphériques connectés au niveau logiciel).

Vous configurez les paramètres de stratégie DFCI en éditant le profil DFCI à partir du Gestionnaire de point de terminaison, comme illustré dans la figure ci-dessous. 

- Dans endpoint Manager chez devicemanagement.microsoft.com, sélectionnez Appareils > Profils de configuration Windows > > « Nom de profil **DFCI » > propriétés > paramètres.**

    ![Configurer les paramètres DFCI](images/dfciconfig.png)

### Bloquer l’accès des utilisateurs aux paramètres UEFI

Pour de nombreux clients, la possibilité d’empêcher les utilisateurs de modifier les paramètres UEFI est essentielle et constitue une raison principale d’utiliser DFCI. Comme répertorié dans le tableau 1, cette opération est gérée via le paramètre Autoriser **l’utilisateur local à modifier les paramètres UEFI.** Si vous ne modifiez pas ou ne configurez pas ce paramètre, les utilisateurs locaux pourront modifier tout paramètre UEFI non géré par Intune. Par conséquent, il est vivement recommandé de désactiver autoriser **l’utilisateur local à modifier les paramètres UEFI.**
Le reste des paramètres DFCI vous permet de désactiver les fonctionnalités qui seraient autrement disponibles pour les utilisateurs. Par exemple, si vous avez besoin de protéger les informations sensibles dans des zones hautement sécurisées, vous pouvez désactiver l’appareil photo et si vous ne souhaitez pas que les utilisateurs démarrent à partir de lecteurs USB, vous pouvez également le désactiver.

### Tableau1. Scénarios DFCI

| Objectif de gestion des appareils                        | Étapes de configuration                                                                           |
| --------------------------------------------- | --------------------------------------------------------------------------------------------- |
| Empêcher les utilisateurs locaux de modifier les paramètres UEFI | Under **Security Features > Allow local user to change UEFI settings**, select **None**.              |
| Désactiver les caméras                               | Under **Built in Hardware > Cameras,** select **Disabled**.                                       |
| Désactiver les microphones et les haut-parleurs              | Under **Built in Hardware > Microphones and speakers,** select **Disabled**.                      |
| Désactiver les radios (Bluetooth, Wi-Fi)             | Under **Built in Hardware > Radios (Bluetooth, Wi-Fi, etc...)**, select **Disabled**.                   |
| Désactiver le démarrage à partir d’un support externe (USB, SD)    | Under **Built in Hardware > Boot Options > Boot from external media (USB, SD)**, select **Disabled**. |

> [!CAUTION]
> Le **paramètre Désactiver les radios (Bluetooth, Wi-Fi)** ne doit être utilisé que sur les appareils qui ont une connexion Ethernet câblé.
 
> [!NOTE]
>  DFCI dans Intune inclut deux paramètres qui ne s’appliquent pas actuellement aux appareils Surface : (1) la virtualisation de l’UC et de l’E/S et (2) désactiver le démarrage à partir des cartes réseau.
 
Intune fournit des balises d’étendue pour déléguer des droits d’administration et des règles d’applicabilité pour gérer les types d’appareils. Pour plus d’informations sur la prise en charge de la gestion des stratégies et des détails complets sur tous les paramètres DFCI, reportez-vous à la [documentation de Microsoft Intune.](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)

## Inscrire des appareils dans Autopilot

Comme indiqué ci-dessus, DFCI ne peut être appliqué que sur les appareils enregistrés dans Windows Autopilot par votre revendeur ou distributeur et est uniquement pris en charge sur Surface Pro 7+, Surface Laptop Go, Surface Pro 7, Surface Pro X et Surface Laptop 3. Pour des raisons de sécurité, il n’est pas possible de « mettre en service automatiquement » vos appareils dans Autopilot. Pour en savoir plus, consultez la prise en charge [de l’inscription Surface pour Windows Autopilot.](surface-autopilot-registration-support.md) 

## Synchroniser manuellement les appareils Autopilot

Bien que les paramètres de stratégie Intune soient généralement appliqués presque immédiatement, il peut y avoir un délai de 10 minutes avant que les paramètres prennent effet sur les appareils ciblés. Dans de rares cas, des retards de 8 heures maximum sont possibles. Pour vous assurer que les paramètres s’appliquent dès que possible (par exemple, dans les scénarios de test), vous pouvez synchroniser manuellement les appareils cibles.

- Dans le Gestionnaire de points de terminaison devicemanagement.microsoft.com, sélectionnez Appareils > Inscription d’appareils **> inscription Windows > Windows Autopilot Devices** et sélectionnez **Synchroniser.**

 Pour plus d’informations, reportez-vous [à Synchroniser manuellement votre appareil Windows.](https://docs.microsoft.com/intune-user-help/sync-your-device-manually-windows)

> [!NOTE]
> Lors de l’ajustement des paramètres directement dans UEFI, vous devez vous assurer que l’appareil redémarre entièrement vers la connexion Windows standard.

## Vérification des paramètres UEFI sur les appareils gérés par DFCI

Dans un environnement de test, vous pouvez vérifier les paramètres dans l’interface UEFI Surface.

1. Ouvrez l’UEFI Surface, ce qui implique d’appuyer sur les boutons **Volume +** et **Alimentation** en même temps.
2. Sélectionnez **Appareils**. Le menu UEFI reflètera les paramètres configurés, comme illustré dans la figure suivante.

    ![Surface UEFI](images/df3.png)

    Notez comment :

      - Les paramètres sont grisés, car autoriser l’utilisateur local à modifier le paramètre **UEFI** est définie sur Aucun.
      - L’audio est désactivé car les **microphones** et les haut-parleurs sont **désactivés.**

## Suppression des paramètres de stratégie DFCI

Lorsque vous créez un profil DFCI, tous les paramètres configurés restent en vigueur sur tous les appareils dans l’étendue de gestion du profil. Vous pouvez uniquement supprimer les paramètres de stratégie DFCI en éditant directement le profil DFCI.

Si le profil DFCI d’origine a été supprimé, vous pouvez supprimer les paramètres de stratégie en créant un profil, puis en les éditant, le cas échéant.

## Suppression de la gestion DFCI

**Pour supprimer la gestion DFCI et remettre l’appareil à l’état d’usine :**

1. Retirez l’appareil d’Intune :
    1. Dans endpoint Manager at devicemanagement.microsoft.com, choose **Groups > All Devices**. Sélectionnez les appareils que vous souhaitez retirer, puis choisissez **Retirer/Effacer.** Pour en savoir plus, reportez-vous à Supprimer des appareils à l’aide de la suppression, de la suppression ou de la [désinscrire manuellement de l’appareil.](https://docs.microsoft.com/intune/remote-actions/devices-wipe) 
2. Supprimez l’inscription Autopilot d’Intune :
    1.  Choose **Device enrollment > Windows enrollment > Devices**.
    2. Sous Appareils Windows Autopilot, choisissez les appareils que vous souhaitez supprimer, puis choisissez **Supprimer.**
3. Connectez l’appareil à Internet câblé avec un adaptateur ethernet de marque Surface. Redémarrez l’appareil et ouvrez le menu UEFI (appuyez et maintenez le bouton d’augmentation du volume tout en appuyant et en libérant le bouton d’alimentation).
4. Sélectionnez **Gestion > configurer > actualiser** à partir du réseau, puis choisissez **Refuser.**

Pour continuer à gérer l’appareil avec Intune, mais sans la gestion DFCI, inscrivez-le automatiquement sur Autopilot et inscrivez-le dans Intune. DFCI ne sera pas appliqué aux appareils auto-enregistrés.

## Si vous souhaitez en savoir plus
- Ignite 2019 : Annonce de la gestion à distance des [paramètres UEFI Surface à partir d’Intune](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333) 
 [Windows Autopilot](https://www.microsoft.com/microsoft-365/windows/windows-autopilot)
- [Windows Autopilot et appareils Surface](windows-autopilot-and-surface-devices.md) 
- [Utiliser des profils DFCI sur les appareils Windows dans Microsoft Intune](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)
