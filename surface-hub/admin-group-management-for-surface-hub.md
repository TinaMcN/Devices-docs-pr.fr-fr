---
title: Administrer la gestion des groupes (Surface Hub)
description: Chaque Microsoft Surface Hub peut être configuré individuellement en ouvrant l’application Paramètres sur l’appareil.
ms.assetid: FA67209E-B355-4333-B903-482C4A3BDCCE
ms.reviewer: ''
manager: laurawi
keywords: administrer la gestion des groupes, application Paramètres, configurer le Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.localizationpriority: medium
ms.openlocfilehash: 716e409bf988e7178ec45e21165aad070d027eee
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10833774"
---
# Administrer la gestion des groupes (SurfaceHub)


Chaque SurfaceHub peut être configuré localement à l’aide de l’application Paramètres de celui-ci. Pour empêcher les utilisateurs non autorisés de modifier les paramètres, l’application Paramètres nécessite des informations d’identification d’administrateur pour ouvrir l’application.


## Administrer la gestion des groupes

Vous pouvez configurer des comptes d’administrateur pour l’appareil de l’une des troismanières suivantes:

-   Créer un compte d’administrateur local
-   Joindre l’appareil à un domaine ActiveDirectory (AD)
-   Joindre l’appareil à Azure ActiveDirectory (AzureAD)


### Créer un compte d’administrateur local

Pour créer un administrateur local, [choisissez d’utiliser un administrateur local lors de la première utilisation](first-run-program-surface-hub.md#use-a-local-admin). Cela permet de créer un compte d’administrateur local unique sur le SurfaceHub avec le nom d’utilisateur et le mot de passe de votre choix. Utilisez ces informations d’identification pour ouvrir l’application Paramètres.

Notez que les informations de compte d’administrateur local ne sont pas stockées par un service d’annuaire. Nous vous recommandons de choisir uniquement un administrateur local si l’appareil n’a pas accès à ActiveDirectory (AD) ou Azure ActiveDirectory (AzureAD). Si vous le souhaitez, vous pouvez modifier le mot de passe de l’administrateur local dans Paramètres. Toutefois, si vous souhaitez passer de l’utilisation du compte d’administrateur local à celle d’un groupe de votre domaine ou client AzureAD, vous devez [réinitialiser l’appareil](device-reset-surface-hub.md) et passer de nouveau par le programme initial.

### Joindre l’appareil à un domaine ActiveDirectory (AD)

Vous pouvez joindre le SurfaceHub à votre domaine ActiveDirectory pour autoriser les utilisateurs d’un groupe de sécurité spécifié à configurer des paramètres. Lors de la première utilisation, choisissez d’utiliser [Active Directory Domain Services](first-run-program-surface-hub.md#use-active-directory-domain-services). Vous devez fournir des informations d’identification permettant de joindre le domaine de votre choix, ainsi que le nom d’un groupe de sécurité existant. Tout utilisateur membre de ce groupe de sécurité peut entrer ses informations d’identification et déverrouiller l’application Paramètres.

#### Que se passe-t-il lorsque vous joignez votre SurfaceHub au domaine?
Les SurfaceHub utilisent la jonction de domaine pour:
- Accorder des droits d’administrateur aux membres d’un groupe de sécurité spécifié dans ActiveDirectory.
- Sauvegarder la clé de récupération BitLocker de l’appareil en la stockant sous l’objet ordinateur dans ActiveDirectory. Pour plus d’informations, voir [Enregistrer la clé BitLocker](save-bitlocker-key-surface-hub.md).
- Synchroniser l’horloge système avec le contrôleur de domaine pour la communication chiffrée

Le SurfaceHub ne prend pas en charge l’application des stratégies de groupe ou des certificats du contrôleur de domaine.

> [!NOTE]
> Si votre SurfaceHub perd son approbation auprès du domaine (par exemple, si vous supprimez le SurfaceHub du domaine une fois qu’il est joint au domaine), vous ne serez pas en mesure de vous authentifier sur l’appareil et d’ouvrir l’application Paramètres. Si vous décidez de supprimer la relation d’approbation du SurfaceHub avec votre domaine, commencez par [réinitialiser l’appareil](device-reset-surface-hub.md).


### Joindre l’appareil à Azure ActiveDirectory (AzureAD)

Vous pouvez joindre le SurfaceHub à AzureAD pour autoriser les professionnels de l’informatique de votre client AzureAD à configurer les paramètres. Lors de la première utilisation, choisissez d’utiliser [Microsoft Azure Active Directory](first-run-program-surface-hub.md#use-microsoft-azure-active-directory). Vous devez fournir des informations d’identification permettant de joindre le client AzureAD de votre choix. Une fois que vous avez joint le SurfaceHub à AzureAD, des droits d’administrateur sur l’appareil sont octroyés aux personnes appropriées.

Par défaut, des droits d’administrateur sur un SurfaceHub joint à AzureAD sont octroyés à tous les **administrateurs globaux**. Avec **AzureAD Premium** ou **Enterprise Mobility Suite (EMS)**, vous pouvez ajouter des administrateurs supplémentaires:
1.  Dans le [portail AzureClassic](https://manage.windowsazure.com/), cliquez sur **ActiveDirectory**, puis sur le nom du répertoire de votre organisation.
2.  Dans la page **Configurer**, sous **Appareils** > **Administrateurs supplémentaires sur les appareils joints à Azure AD**, cliquez sur **Sélectionné**.
3.  Cliquez sur **Ajouter**, puis sélectionnez les utilisateurs que vous voulez ajouter comme administrateurs sur le SurfaceHub et les autres appareils joints à AzureAD.
4.  Lorsque vous avez terminé, cliquez sur la coche pour enregistrer vos modifications.

#### Que se passe-t-il lorsque vous joignez votre SurfaceHub à AzureAD?
Les SurfaceHub utilisent la jonction à AzureAD pour:
- Accorder des droits d’administrateur aux utilisateurs appropriés de votre client AzureAD.
- Sauvegarder la clé de récupération BitLocker de l’appareil en la stockant sous le compte qui a été utilisé pour joindre l’appareil à AzureAD. Pour plus d’informations, voir [Enregistrer la clé BitLocker](save-bitlocker-key-surface-hub.md).

### Inscription automatique par le biais d’Azure Active Directory Join

Surface Hub permet désormais de s’inscrire automatiquement dans Intune en adhérant l’appareil à Azure Active Directory. 

Pour plus d’informations, voir [activer l’inscription automatique de Windows 10](https://docs.microsoft.com/intune/windows-enroll#enable-windows-10-automatic-enrollment).

### Que choisir?

Si votre organisation utilise AD ou AzureAD, nous vous recommandons de joindre le SurfaceHub à un domaine ou à AzureAD, principalement pour des raisons de sécurité. Les personnes pourront s’authentifier et déverrouiller l’application Paramètres à l’aide de leurs propres informations d’identification, et elles peuvent être intégrées à des groupes de sécurité associés à votre domaine ou en être exclues.

| Option                                            | Conditions requises                            | Informations d’identification pouvant être utilisées pour accéder à l’application Paramètres  |
|---------------------------------------------------|-----------------------------------------|-------|
| Créer un compte d’administrateur local                      | Aucune                                    | Nom d’utilisateur et mot de passe spécifiés lors de la première utilisation |
| Joindre l’appareil à un domaine ActiveDirectory (AD)              | Votre organisation utilise AD               | Tout utilisateur AD d’un groupe de sécurité spécifique de votre domaine |
| Joindre l’appareil à Azure ActiveDirectory (AzureAD) | Votre organisation utilise AzureAD Standard   | Administrateurs généraux uniquement |
| &nbsp;                                            | Votre organisation utilise AzureAD Premium ou Enterprise Mobility Suite (EMS) | Administrateurs globaux et supplémentaires |


