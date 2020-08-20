---
title: Gestion Intune des paramètres de surface UEFI
description: Cet article décrit la configuration d’un environnement DFCI dans Microsoft Intune et la gestion des paramètres du microprogramme pour les appareils surface ciblés.
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 08/19/2020
ms.reviewer: jesko
manager: laurawi
ms.audience: itpro
appliesto:
- Surface Pro 7
- Surface Pro X
- Surface Laptop 3
- Surface Book 3
ms.openlocfilehash: 9d83fe9b7febf996d2cb314399505ed050a69a92
ms.sourcegitcommit: b94832cba98e01014f7d184c85d79f8339e046c4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/20/2020
ms.locfileid: "10941663"
---
# Gestion Intune des paramètres de surface UEFI

## Introduction

La possibilité de gérer les appareils à partir du Cloud a considérablement simplifié le déploiement et la mise en service informatiques dans le cycle de vie. Les profils d’interface de configuration de microprogramme de périphériques (DFCI) intégrés à Microsoft Intune (désormais disponibles en préversion [publique](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)) permettent de faire en sorte que la gestion de surface UEFI étende la pile de gestion moderne au niveau matériel UEFI. DFCI prend en charge la mise en service des fonctions d’approvisionnement nulle, élimine les mots de passe BIOS et contrôle les paramètres de sécurité, notamment les options de démarrage et les périphériques intégrés, et vous permet de créer des scénarios de sécurité avancée à l’avenir. Pour obtenir des réponses aux questions fréquemment posées, voir [Enflammer 2019: annonçant la gestion à distance des paramètres de surface UEFI de Intune](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333).

### Arrière-plan

Comme n’importe quel ordinateur exécutant Windows 10, les appareils surface dépendent du code stocké dans le SoC qui permet au processeur d’être intégré aux disques durs, aux périphériques d’affichage, aux ports USB et aux autres périphériques. Les programmes stockés dans cette mémoire morte (ROM) s’appelle le microprogramme (alors que les programmes stockés dans le média dynamique sont appelés logiciels).

Contrairement aux autres appareils Windows 10 disponibles sur le marché aujourd’hui, surface fournit aux administrateurs informatiques la possibilité de configurer et de gérer le microprogramme grâce à un ensemble enrichi de paramètres de configuration UEFI. Cela fournit une couche de contrôle matériel sur la gestion des stratégies logicielles mise en œuvre via des stratégies de gestion des périphériques mobiles (GPM), de configuration ou de groupe. Par exemple, les organisations qui déploient des appareils dans des zones fortement sécurisées, avec des informations sensibles, peuvent empêcher l’utilisation de l’appareil photo en supprimant les fonctionnalités au niveau matériel. À partir d’un point de vue de l’appareil, la désactivation de la caméra par le biais d’un paramètre de microprogramme équivaut à la suppression physique de la caméra. Comparez la sécurité supplémentaire de gestion au niveau du microprogramme pour compter uniquement sur les paramètres logiciels du système d’exploitation. Par exemple, si vous désactivez le service audio Windows par le biais d’un paramètre de stratégie dans un environnement de domaine, un administrateur local peut quand même le réactiver.

### DFCI et SEMM

Jusqu’à présent, la gestion du microprogramme requis lors de l’inscription de périphériques en mode de gestion des entreprises de surface (SEMM) avec la surcharge des tâches manuelles en temps réel. Par exemple, SEMM nécessite que le personnel informatique accède physiquement à chaque PC pour entrer un code confidentiel à deux chiffres dans le cadre du processus de gestion des certificats. Bien que SEMM ne soit pas une bonne solution pour les organisations dans un environnement strictement local, sa complexité et les exigences informatiques qu’il implique requièrent une utilisation onéreuse.

Maintenant que vous disposez de nouvelles fonctionnalités de gestion de microprogramme UEFI intégrées dans Microsoft Intune, la possibilité de verrouiller le matériel est simplifiée et facile à utiliser avec de nouvelles fonctionnalités pour la mise en service, la sécurité et les mises à jour rationalisées dans une seule console, désormais unifiée en tant que [Gestionnaire de points de terminaison Microsoft](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager). La figure suivante illustre les paramètres UEFI affichés directement sur l’appareil (à gauche) et consultés dans la console du gestionnaire de points de terminaison (à droite).

![Paramètres UEFI affichés sur l’appareil (vers la gauche) et dans la console Endpoint Manager (vers la droite)](images/uefidfci.png)

Le DFCI permet une gestion sans égale nulle, ce qui évite d’avoir recours à l’intervention manuelle de la part des administrateurs informatiques. DFCI est déployé par le biais du pilotage automatique Windows à l’aide de la fonctionnalité profils d’appareil dans Intune. Un profil d’appareil vous permet d’ajouter et de configurer des paramètres qui peuvent ensuite être déployés sur des appareils inscrits à la gestion au sein de votre organisation. Une fois que l’appareil a reçu le profil de l’appareil, les fonctionnalités et paramètres sont automatiquement appliqués. Voici quelques exemples de profils d’appareil communs: le courrier électronique, les restrictions d’appareil, le VPN, le Wi-Fi et les modèles d’administration. DFCI est simplement un profil supplémentaire qui vous permet de gérer les paramètres de configuration UEFI à partir du Cloud sans avoir à gérer l’infrastructure locale.  

## Appareils pris en charge

DFCI est pris en charge sur les appareils suivants:

- SurfacePro7
- SurfaceProX
- Surface Laptop3
- SurfaceBook3

> [!NOTE]
> Surface Pro X ne prend pas en charge la gestion des paramètres de DFCI pour les appareils photo, audio et Wi-Fi intégrés.

## Conditions préalables

- Un appareil doit être inscrit auprès de Windows AutoPilot par un [partenaire fournisseur de solutions Cloud Microsoft](https://partner.microsoft.com/membership/cloud-solution-provider) ou un distributeur OEM.

- Avant de configurer DFCI pour la surface, vous devez être familiarisé avec la configuration requise dans  [Microsoft Intune](https://docs.microsoft.com/intune/) et [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/) (Azure AD).

## Avant de commencer

Ajoutez vos périphériques surface cibles à un groupe de sécurité Azure AD. Pour plus d’informations sur la création et la gestion des groupes de sécurité, voir [documentation sur Intune](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows#create-your-azure-ad-security-groups).

## Configurer la gestion des DFCI pour les appareils surface

Dans un environnement DFCI, vous devez configurer un profil DFCI qui contient les paramètres et un profil AutoPilot pour appliquer les paramètres à des appareils enregistrés. Il est également recommandé d’utiliser un profil d’état d’inscription pour vous assurer que les paramètres sont déplacés pendant l’installation de OOBE lors du premier démarrage de l’appareil. Ce guide décrit comment configurer l’environnement DFCI et gérer les paramètres de configuration UEFI pour les appareils surface ciblés.

## Créer un profil DFCI

Avant de configurer les paramètres de stratégie DFCI, commencez par créer un profil DFCI et attribuez-le au groupe de sécurité Azure AD qui contient vos périphériques cibles.

1. Connectez-vous à votre client sur devicemanagement.microsoft.com.
2. Dans le centre d’administration Microsoft Endpoint Manager, sélectionnez **périphériques > profils de Configuration > créer un profil** , puis entrez un nom. par exemple, la **stratégie de configuration DFCI.**
3. Sélectionnez **Windows 10 et versions ultérieures** pour type de plateforme.
4. Dans la liste déroulante type de profil, sélectionnez **interface de configuration du microprogramme de périphériques** pour ouvrir la Blade DFCI contenant tous les paramètres de stratégie disponibles. Pour plus d’informations sur les paramètres de DFCI, voir le tableau 1 sur cette page ou la [documentation Intune](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows). Vous pouvez configurer les paramètres de DFCI lors du processus de configuration initial ou ultérieurement en modifiant le profil DFCI.

    ![Créer un profil DFCI](images/df1.png)

5. Cliquez sur **OK** , puis sélectionnez **créer**.
6. Sélectionnez **devoirs** et, sous **Sélectionner des groupes** , sélectionnez le groupe de sécurité Azure ad qui contient vos périphériques cibles, comme illustré dans la figure ci-dessous. Cliquez sur **Save**.

    ![Attribuer un groupe de sécurité](images/df2a.png)

## Créer un profil AutoPilot

1. Dans le gestionnaire de points de terminaison sur devicemanagement.microsoft.com, sélectionnez **appareils > l’inscription Windows** et faites défiler vers le bas jusqu’à **profils de déploiement**.
2. Cliquez sur **créer un profil** , puis tapez un nom. par exemple, **mon profil AutoPilot**, puis sélectionnez **suivant**.
3. Sélectionnez les paramètres suivants:

    - Mode de déploiement: **piloté par l’utilisateur**.
    - Type de jointure: Azure **ad jointe**.

4. Ne modifiez pas les paramètres par défaut restants, puis sélectionnez **suivant**, comme illustré dans la figure ci-dessous.

    ![Créer un profil AutoPilot](images/df3b.png)

5. Dans la page affectations, sélectionnez l' **option Sélectionner les groupes à inclure** , puis cliquez sur votre groupe de sécurité Azure ad. Sélectionnez **Suivant**.
6. Acceptez le résumé, puis sélectionnez **créer**. Le profil AutoPilot est désormais créé et attribué au groupe.

## Configurer la page d’état d’inscription

Pour vous assurer que les appareils appliquent la configuration DFCI lors de la connexion de l’utilisateur, vous devez configurer l’état de l’inscription.

Pour plus d’informations, reportez-vous à la rubrique [configuration d’une page d’état d’inscription](https://docs.microsoft.com/intune/enrollment/windows-enrollment-status).


## Configurer les paramètres DFCI sur les appareils surface

DFCI inclut un ensemble de stratégies de configuration UEFI rationalisées qui fournissent un niveau de sécurité supplémentaire en verrouillant les appareils au niveau matériel. DFCI est conçu pour être utilisé en association avec des paramètres de gestion des périphériques mobiles au niveau logiciel. Notez que les paramètres de DFCI affectent uniquement les composants matériels intégrés aux appareils surface et ne s’étendent pas aux périphériques connectés, tels que les webcams USB. (Toutefois, vous pouvez utiliser des stratégies de restriction d’appareil dans Intune pour désactiver l’accès aux périphériques connectés au niveau logiciel).

Vous pouvez configurer les paramètres de stratégie DFCI en modifiant le profil DFCI à partir de Endpoint Manager, comme illustré dans la figure ci-dessous. 

- Dans le gestionnaire de points de terminaison à devicemanagement.microsoft.com, sélectionnez **appareils > Windows > les profils de Configuration > «DFCI nom du profil >» propriétés > paramètres**.

    ![Configurer les paramètres de DFCI](images/dfciconfig.png)

### Bloquer l’accès des utilisateurs aux paramètres UEFI

Pour de nombreux clients, il est essentiel de bloquer les utilisateurs lors de la modification des paramètres UEFI et d’utiliser DFCI pour une raison principale. Comme indiqué dans le tableau 1, cela est géré par le biais du paramètre **permettre à l’utilisateur local de changer les paramètres UEFI**. Si vous ne modifiez pas ou ne configurez pas ce paramètre, les utilisateurs locaux pourront modifier n’importe quel paramètre UEFI qui n’est pas géré par Intune. Par conséquent, il est vivement conseillé de désactiver l’option **autoriser l’utilisateur local à modifier les paramètres UEFI.**
Le reste des paramètres d’DFCI vous permet de désactiver les fonctionnalités qui seraient autrement disponibles pour les utilisateurs. Par exemple, si vous avez besoin de protéger des informations sensibles dans des zones fortement sécurisées, vous pouvez désactiver l’appareil photo et, si vous ne voulez pas que les utilisateurs démarrent à partir de pilotes USB, vous pouvez désactiver cette possibilité.

### Tableau1. Scénarios de DFCI

| Objectif de gestion de l’appareil                        | Étapes de configuration                                                                           |
| --------------------------------------------- | --------------------------------------------------------------------------------------------- |
| Bloquer les utilisateurs locaux lors de la modification des paramètres UEFI | Sous **fonctionnalités de sécurité > permettre à l’utilisateur local de changer les paramètres UEFI**, sélectionnez **aucun**.              |
| Désactiver les webcams                               | Sous **composants matériels > appareils photo intégrés**, sélectionnez **désactivé**.                                       |
| Désactiver le microphone et les haut-parleurs              | Sous **composants matériels intégrés > les micros et haut-parleurs**, sélectionnez **désactivé**.                      |
| Désactiver les radios (Bluetooth; Wi-Fi)             | Sous **matériel intégré > les radios (Bluetooth, Wi-Fi, etc.)**, sélectionnez **désactivé**.                   |
| Désactiver le démarrage à partir de médias externes (USB, SD)    | Sous **composants matériels intégrés > de démarrage > démarrez à partir de médias externes (USB, SD)**, sélectionnez **désactivé**. |

> [!CAUTION]
> Ce **paramètre ne** doit être utilisé que sur les appareils dotés d’une connexion Ethernet câblée.
 
> [!NOTE]
>  DFCI dans Intune inclut deux paramètres qui ne s’appliquent pas actuellement aux appareils surface: (1) CPU et virtualisation d’e/s et (2) désactiver le démarrage des cartes réseau.
 
Intune fournit des balises Scope pour déléguer des droits d’administration et des règles d’applicabilité pour gérer les types d’appareil. Pour plus d’informations sur la prise en charge de la gestion des stratégies et des détails complets sur tous les paramètres DFCI, voir [la documentation Microsoft Intune](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows).

## Inscrire des appareils dans AutoPilot

Comme indiqué ci-dessus, DFCI ne peut être appliqué qu’aux appareils inscrits dans Windows AutoPilot par votre revendeur ou distributeur et est uniquement pris en charge, à ce stade, sur surface Pro 7, surface Pro X et surface Laptop 3. Pour des raisons de sécurité, il n’est pas possible de «mettre en service en libre-service» vos appareils dans AutoPilot.

## Synchronisation manuelle des appareils AutoPilot

Bien que les paramètres de stratégie Intune soient généralement appliqués presque, il est possible qu’il y ait un délai de 10 minutes avant que les paramètres n’entrent en vigueur sur les appareils ciblés. Dans de rares cas, il est possible de retarder huit heures maximum. Pour vous assurer que les paramètres s’appliquent dès que possible (par exemple, dans le cadre de scénarios de test), vous pouvez synchroniser manuellement les appareils cibles.

- Dans Endpoint Manager dans devicemanagement.microsoft.com, accédez à **périphériques > inscription de l’appareil > inscription windows > périphériques Windows AutoPilot** et sélectionnez **synchroniser**.

 Pour plus d’informations, reportez-vous à [la rubrique synchroniser votre appareil Windows manuellement](https://docs.microsoft.com/intune-user-help/sync-your-device-manually-windows).

> [!NOTE]
> Lorsque vous ajustez les paramètres directement dans UEFI, vous devez vous assurer que le périphérique redémarre complètement sur la connexion Windows standard.

## Vérification des paramètres UEFI sur les appareils gérés par DFCI

Dans un environnement de test, vous pouvez vérifier les paramètres dans l’interface UEFI de surface.

1. Ouvrez surface UEFI, qui implique d’appuyer sur les boutons **volume +** et **alimentation** en même temps.
2. Sélectionnez **appareils**. Le menu UEFI reflétera les paramètres configurés, comme illustré dans la figure ci-dessous.

    ![Surface UEFI](images/df3.png)

    Remarque:

      - Les paramètres sont grisés, car l’option **autoriser l’utilisateur local à modifier UEFI** est définie sur aucune.
      - Le son est réglé sur désactivé, car les **micros et les haut-parleurs** sont définis sur **Disabled**.

## Supprimer les paramètres de stratégie DFCI

Lorsque vous créez un profil DFCI, tous les paramètres configurés resteront appliqués sur tous les appareils dans le cadre de la gestion du profil. Vous pouvez uniquement supprimer des paramètres de stratégie DFCI en modifiant directement le profil DFCI.

Si le profil DFCI d’origine a été supprimé, vous pouvez supprimer des paramètres de stratégie en créant un nouveau profil et en modifiant les paramètres, le cas échéant.

## Suppression de la gestion des DFCI

**Pour supprimer la gestion de DFCI et revenir au nouvel état d’usine de l’appareil:**

1. Retirer l’appareil de Intune:
    1. Dans Endpoint Manager dans devicemanagement.microsoft.com, sélectionnez **groupes > tous les appareils**. Sélectionnez les appareils que vous voulez supprimer, puis sélectionnez **supprimer/effacer.** Pour en savoir plus [, voir supprimer des appareils à l’aide de la réinitialisation, de la mise hors service ou de l’annulation manuelle de l’appareil](https://docs.microsoft.com/intune/remote-actions/devices-wipe). 
2. Supprimez l’enregistrement AutoPilot de Intune:
    1.  Sélectionnez **inscription de l’appareil > > les appareils Windows**.
    2. Sous appareils AutoPilot Windows, sélectionnez les appareils que vous voulez supprimer, puis sélectionnez **supprimer**.
3. Connexion d’un périphérique à un réseau câblé à l’aide d’une carte Ethernet de marque en surface. Redémarrez l’appareil, puis ouvrez le menu UEFI (appuyez longuement sur le bouton de volume enfoncé tout en appuyant sur le bouton d’alimentation.
4. Sélectionnez **gestion > configurer > actualiser du réseau** , puis choisissez **refuser.**

Pour continuer à gérer l’appareil avec Intune, mais sans la gestion de DFCI, inscrivez-le automatiquement à l’appareil pour le pilotage automatique et inscrivez-le à Intune. DFCI ne sera pas appliqué aux appareils auto-enregistrés.

## En savoir plus
- [Enflammer 2019: annonçant la gestion à distance des paramètres de surface UEFI à partir de Intune](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333) 
 [Pilotage automatique Windows](https://www.microsoft.com/microsoft-365/windows/windows-autopilot)
- [Windows Autopilot et appareils Surface](windows-autopilot-and-surface-devices.md) 
- [Utiliser les profils DFCI sur les appareils Windows dans Microsoft Intune](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)
