---
title: Préparer votre environnement pour SurfaceHub 2S
description: Découvrez ce que vous devez faire pour préparer votre environnement pour surface Hub 2.
keywords: séparer les valeurs par des virgules
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 12/28/2020
ms.localizationpriority: Medium
ms.openlocfilehash: af66449806c9aa525fa3f5df84012d3daeed96ba
ms.sourcegitcommit: dbd14649442ad039aeb265cd60ed029d483a4bb0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/29/2020
ms.locfileid: "11251451"
---
# Préparer votre environnement pour SurfaceHub 2S

## Office 365 Readiness

Si vous utilisez Exchange Online, Skype entreprise Online, Microsoft teams ou le tableau blanc Microsoft et souhaitez gérer surface Hub 2 avec Intune, consultez d’abord la [Configuration requise pour Office 365 pour les points de terminaison](https://docs.microsoft.com/office365/enterprise/office-365-endpoints).

Les points de terminaison Office 365 permettent d’optimiser votre réseau en envoyant toutes les demandes réseau Office 365 approuvées directement par le biais de votre pare-feu, en évitant tout traitement ou contrôle supplémentaire au niveau des paquets. Cette fonctionnalité permet de réduire la latence et les besoins en matière de capacité de périmètre.

Microsoft met régulièrement à jour le service Office 365 avec de nouvelles fonctionnalités, qui pourraient modifier les ports, URL et adresses IP nécessaires. Pour évaluer, configurer et rester à jour avec les modifications, abonnez-vous à l' [adresse IP d’Office 365 et au service Web d’URL](https://docs.microsoft.com/office365/enterprise/office-365-ip-web-service).

> [!NOTE]
> Surface Hub fonctionne avec Microsoft Teams, Skype entreprise Server 2019, Skype entreprise Server 2015 ou Skype entreprise online.
Les plates-formes précédentes, telles que Lync Server 2013, ne sont pas prises en charge. Surface Hub n’est pas pris en charge dans les environnements GCC-High ou DoD.


## Affiliation d’appareil

Utilisez affiliation d’appareil pour gérer l’accès utilisateur à l’application paramètres sur surface Hub 2S.
Le système d’exploitation de l’équipe Windows 10 (exécuté sur surface Hub 2) permet uniquement aux utilisateurs autorisés d’ajuster les paramètres à l’aide de l’application paramètres. Dans la mesure où le choix de l’affiliation peut affecter la disponibilité des fonctionnalités, planifiez de manière appropriée pour vous assurer que les utilisateurs peuvent accéder aux fonctions comme prévu.

> [!NOTE]
> Dans le cadre de la configuration initiale du programme OOBE (OOBE), vous ne pouvez définir aucune affiliation d’appareil. Si vous devez réinitialiser l’affiliation de l’appareil, vous devez répéter l’installation d’OOBE.

## Aucune affiliation

Aucune affiliation n’est comme si vous aviez surface Hub 2S au sein d’un groupe de travail disposant d’un compte d’administrateur local différent sur chaque surface Hub 2S. Si vous ne sélectionnez pas d’affiliation, vous devez enregistrer localement la [clé BitLocker sur une clé USB](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-key-management-faq). Vous pouvez toujours inscrire l’appareil avec Intune; en revanche, seul l’administrateur local peut accéder à l’application paramètres en utilisant les informations d’identification du compte configurées lors de l’utilisation de la version OOBE. Vous pouvez modifier le mot de passe du compte d’administrateur à partir de l’application paramètres.

## Services de domaine ActiveDirectory

Si vous affiliationz surface Hub 2 à des services de domaine Active Directory locaux, vous devez gérer l’accès à l’application paramètres à l’aide d’un groupe de sécurité sur votre domaine. Cela permet de s’assurer que tous les membres du groupe de sécurité disposent des autorisations nécessaires pour modifier les paramètres des composants surface Hub 2. Notez également ce qui suit:

- Lorsque surface Hub 2 affiliés à vos services de domaine Active Directory locaux, vous pouvez enregistrer la clé BitLocker dans le schéma Active Directory. Pour plus d’informations, consultez [la rubrique préparer votre organisation pour BitLocker: planification et stratégies](https://docs.microsoft.com/windows/security/information-protection/bitlocker/prepare-your-organization-for-bitlocker-planning-and-policies).

- Les autorités de certification racines de confiance de votre organisation sont transmises au même conteneur dans surface Hub 2, ce qui signifie que vous n’avez pas besoin de les importer à l’aide d’un package de mise en service.

- Vous pouvez toujours inscrire l’appareil auprès de Intune pour gérer de façon centralisée les paramètres sur votre surface Hub 2.

## Azure Active Directory

Lorsque vous choisissez d’affilier votre surface Hub 2 à Azure Active Directory (Azure AD), tous les utilisateurs du groupe de sécurité administrateurs généraux peuvent se connecter à l’application paramètres sur surface Hub 2. Pour l’instant, il est impossible de délégué un autre groupe pour vous connecter à l’application paramètres sur surface Hub 2.

Si vous avez activé l’inscription automatique de Intune pour votre organisation, surface Hub 2 s’inscrit automatiquement auprès de Intune. La clé BitLocker de l’appareil est automatiquement enregistrée dans Azure AD. Lorsque vous affiliating surface Hub 2 avec Azure AD, l’authentification unique et la connexion facile ne fonctionnent pas.
