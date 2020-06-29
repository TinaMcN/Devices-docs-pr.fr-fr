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
# <span data-ttu-id="9e841-105">Enregistrer votre clé BitLocker (SurfaceHub)</span><span class="sxs-lookup"><span data-stu-id="9e841-105">Save your BitLocker key (Surface Hub)</span></span>


<span data-ttu-id="9e841-106">Chaque Microsoft SurfaceHub est automatiquement configuré à l’aide du logiciel de chiffrement de lecteur BitLocker.</span><span class="sxs-lookup"><span data-stu-id="9e841-106">Every Microsoft Surface Hub is automatically set up with BitLocker drive encryption software.</span></span> <span data-ttu-id="9e841-107">Microsoft recommande vivement de sauvegarder vos clés de récupération BitLocker.</span><span class="sxs-lookup"><span data-stu-id="9e841-107">Microsoft strongly recommends that you make sure you back up your BitLocker recovery keys.</span></span>

<span data-ttu-id="9e841-108">Le Surface Hub propose plusieurs façons de gérer votre clé BitLocker.</span><span class="sxs-lookup"><span data-stu-id="9e841-108">There are several ways to manage your BitLocker key on the Surface Hub.</span></span>

1.  <span data-ttu-id="9e841-109">Si vous avez joint le Surface Hub à un domaine, l’appareil sauvegarde la clé sur le domaine et la stocke sous l’objet ordinateur.</span><span class="sxs-lookup"><span data-stu-id="9e841-109">If you’ve joined the Surface Hub to a domain, the device will back up the key on the domain and store it under the computer object.</span></span>

    <span data-ttu-id="9e841-110">Si vous ne trouvez pas la clé BitLocker après avoir joint l’appareil à un domaine, il est probable que votre schéma Active Directory ne prenne pas en charge la sauvegarde de clés BitLocker.</span><span class="sxs-lookup"><span data-stu-id="9e841-110">If you can’t find the BitLocker key after joining the device to a domain, it’s likely that your Active Directory schema doesn’t support BitLocker key backup.</span></span> <span data-ttu-id="9e841-111">Si vous ne voulez pas modifier le schéma, vous pouvez enregistrer la clé BitLocker en accédant à Paramètres et en suivant la procédure d’utilisation d’un compte d’administrateur local, qui est détaillée plus loin dans cette liste.</span><span class="sxs-lookup"><span data-stu-id="9e841-111">If you don’t want to change the schema, you can save the BitLocker key by going to Settings and following the procedure for using a local admin account, which is detailed later in this list.</span></span>

2.  <span data-ttu-id="9e841-112">Si vous avez joint le Surface Hub à Azure Active Directory (Azure AD), la clé BitLocker sera stockée sous le compte utilisé pour joindre l’appareil.</span><span class="sxs-lookup"><span data-stu-id="9e841-112">If you’ve joined the Surface Hub to Azure Active Directory (Azure AD), the BitLocker key will be stored under the account that was used to join the device.</span></span>

3.  <span data-ttu-id="9e841-113">Si vous utilisez un compte d’administrateur local pour gérer l’appareil, vous pouvez enregistrer la clé BitLocker en accédant à l’application **paramètres** et en accédant à **mettre à jour &** &gt; **récupération**de sécurité.</span><span class="sxs-lookup"><span data-stu-id="9e841-113">If you’re using a local admin account to manage the device, you can save the BitLocker key by going to the **Settings** app and navigating to **Update & security** &gt; **Recovery**.</span></span> <span data-ttu-id="9e841-114">Insérez un lecteur USB, puis sélectionnez l’option permettant d’enregistrer la clé BitLocker.</span><span class="sxs-lookup"><span data-stu-id="9e841-114">Insert a USB drive and select the option to save the BitLocker key.</span></span> <span data-ttu-id="9e841-115">La clé est enregistrée dans un fichier texte sur le lecteur USB.</span><span class="sxs-lookup"><span data-stu-id="9e841-115">The key will be saved to a text file on the USB drive.</span></span>


## <span data-ttu-id="9e841-116">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="9e841-116">Related topics</span></span>

[<span data-ttu-id="9e841-117">Gérer le Microsoft SurfaceHub</span><span class="sxs-lookup"><span data-stu-id="9e841-117">Manage Microsoft Surface Hub</span></span>](manage-surface-hub.md)

[<span data-ttu-id="9e841-118">Guide de l’administrateur Microsoft Surface Hub</span><span class="sxs-lookup"><span data-stu-id="9e841-118">Microsoft Surface Hub administrator's guide</span></span>](surface-hub-administrators-guide.md)

 

 





