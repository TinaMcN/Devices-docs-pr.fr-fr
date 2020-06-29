---
title: Enregistrer votre clé BitLocker (SurfaceHub)
description: Chaque Microsoft SurfaceHub est automatiquement configuré à l’aide du logiciel de chiffrement de lecteur BitLocker. Microsoft vous recommande vivement de sauvegarder vos clés de récupération BitLocker.
ms.assetid: E11E4AB6-B13E-4ACA-BCE1-4EDC9987E4F2
ms.reviewer: ''
manager: laurawi
keywords: SurfaceHub, BitLocker, clés de récupération BitLocker
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/08/2019
ms.localizationpriority: medium
ms.openlocfilehash: 73efa418fa80ef90a643d4fb4c457280ab982b38
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10833864"
---
# Enregistrer votre clé BitLocker (SurfaceHub)


Chaque Microsoft SurfaceHub est automatiquement configuré à l’aide du logiciel de chiffrement de lecteur BitLocker. Microsoft recommande vivement de sauvegarder vos clés de récupération BitLocker.

Le Surface Hub propose plusieurs façons de gérer votre clé BitLocker.

1.  Si vous avez joint le Surface Hub à un domaine, l’appareil sauvegarde la clé sur le domaine et la stocke sous l’objet ordinateur.

    Si vous ne trouvez pas la clé BitLocker après avoir joint l’appareil à un domaine, il est probable que votre schéma Active Directory ne prenne pas en charge la sauvegarde de clés BitLocker. Si vous ne voulez pas modifier le schéma, vous pouvez enregistrer la clé BitLocker en accédant à Paramètres et en suivant la procédure d’utilisation d’un compte d’administrateur local, qui est détaillée plus loin dans cette liste.

2.  Si vous avez joint le Surface Hub à Azure Active Directory (Azure AD), la clé BitLocker sera stockée sous le compte utilisé pour joindre l’appareil.

3.  Si vous utilisez un compte d’administrateur local pour gérer l’appareil, vous pouvez enregistrer la clé BitLocker en accédant à l’application **paramètres** et en accédant à **mettre à jour &** &gt; **récupération**de sécurité. Insérez un lecteur USB, puis sélectionnez l’option permettant d’enregistrer la clé BitLocker. La clé est enregistrée dans un fichier texte sur le lecteur USB.


## Rubriques connexes

[Gérer le Microsoft SurfaceHub](manage-surface-hub.md)

[Guide de l’administrateur Microsoft Surface Hub](surface-hub-administrators-guide.md)

 

 





