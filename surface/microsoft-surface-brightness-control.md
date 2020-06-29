---
title: Contrôle de luminosité Surface
description: Cette rubrique décrit comment utiliser l’application contrôle de luminosité de surface pour gérer la luminosité de l’affichage dans les scénarios de point de vente et Kiosk.
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: hachidan
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: 197ed9fe1abc880779ad6bb0f85d2970086395f6
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10833372"
---
# Contrôle de luminosité Surface

Lorsque vous déployez des appareils surface dans un point de vente ou d’autres scénarios de kiosque «toujours sur», vous pouvez optimiser la gestion de l’alimentation à l’aide de la nouvelle application de contrôle de luminosité de surface.

Disponible en téléchargement avec les [Outils surface](https://www.microsoft.com/download/details.aspx?id=46703).
Le contrôle de luminosité de surface est conçu pour vous aider à réduire la charge thermique et à abaisser l’encombrement global du carbone pour les appareils de surface déployés.
Si vous envisagez d’obtenir uniquement cet outil à partir de la page de téléchargement, sélectionnez le fichier **Surface_Brightness_Control_v1.16.137.0.msi** dans la liste des fichiers disponibles.
L’outil estompe automatiquement l’écran lorsqu’il n’est pas en cours d’utilisation et comprend les options de configuration suivantes:

- Période d’inactivité avant de estomper l’écran.

- Niveau de luminosité grisé.

- Niveau de luminosité maximal en cours d’utilisation.

**Pour exécuter le contrôle de luminosité de surface:**

- Installer surfacebrightnesscontrol.msi sur l’appareil cible et le contrôle de luminosité de surface commencera à fonctionner immédiatement.

## Configurer le contrôle de luminosité de surface

Vous pouvez ajuster les valeurs par défaut par le biais du Registre Windows. Pour plus d’informations sur l’utilisation du Registre Windows, consultez la [documentation relative au registre](https://docs.microsoft.com/windows/desktop/sysinfo/registry).

1.  Exécutez regedit à partir d’une invite de commandes pour ouvrir l’éditeur du Registre Windows.
    
      - Computer\HKEY\ _LOCAL \ _MACHINE contrôle de luminosité \SOFTWARE\WOW6432Node\Microsoft\Surface\Surface 
    
    Si vous utilisez une version plus ancienne du contrôle de luminosité de surface, exécutez la commande suivante à la place:
    
      - Computer\HKEY\ _LOCAL \ _MACHINE contrôle de luminosité \SOFTWARE\Microsoft\Surface\Surface


| Paramètre de Registre | Données| Description  
|-----------|------------|---------------
| Contrôle de luminosité activé  |  Par défaut: 01  <br> Option: 01, 00 <br> Type: REG_BINARY |  Ce paramètre vous permet d’activer ou de désactiver le contrôle de luminosité de surface. Pour désactiver le contrôle de luminosité de surface, définissez la valeur sur 00. Si vous ne configurez pas ce paramètre, le contrôle de luminosité de surface est activé. |
| Contrôle de luminosité sur alimentation activée| Par défaut: 01 <br> Options: 01, 00 <br> Type: REG_BINARY | Ce paramètre vous permet de désactiver le contrôle de luminosité de surface lorsque l’appareil est connecté directement à l’alimentation. Pour désactiver le contrôle de luminosité de surface lors du branchement de l’alimentation, définissez la valeur sur 00. Si vous ne configurez pas ce paramètre, le contrôle de luminosité de surface est activé. |
| Luminosité grisée   | Par défaut: 20  <br>Option: plage de 0-100% de la luminosité de l’écran <br> Type de données: entier positif <br> Type: REG_DWORD | Ce paramètre vous permet de gérer la plage de luminosité pendant les périodes d’inactivité. Si vous ne configurez pas ce paramètre, le niveau de luminosité est inférieur à 20% de la luminosité complète après 30 secondes d’inactivité. |
Luminosité complète   | Par défaut: 100  <br>Option: plage de 0-100% de la luminosité de l’écran <br> Type de données: entier positif <br> Type: REG_DWORD  | Ce paramètre vous permet de gérer la gamme de luminosité maximale pour l’appareil. Si vous ne configurez pas ce paramètre, la plage de luminosité maximale est de 100%.|  
| Délai d’inactivité| Par défaut: 30 secondes <br>Option: toute valeur numérique  <br>Type de données: entier  <br> Type: REG_DWORD | Ce paramètre vous permet de gérer la durée d’inactivité avant de estomper l’appareil. Si vous ne configurez pas ce paramètre, le délai d’inactivité est de 30 secondes.|
| Télémétrie activée | Par défaut: 01 <br>Option: 01, 00 <br> Type: REG_BINARY  | Ce paramètre vous permet de gérer le partage des informations d’utilisation des applications pour améliorer les logiciels et garantir une meilleure expérience utilisateur. Pour désactiver la télémétrie, définissez la valeur sur 00. Si vous ne configurez pas ce paramètre, les informations de télémétrie sont partagées avec Microsoft conformément à la [déclaration de confidentialité de Microsoft](https://privacy.microsoft.com/privacystatement). |

## Modifications et mises à jour

### Version 1.16.137<br>
*Date de publication: 22 octobre 2019*<br>
Cette version du contrôle de luminosité de surface ajoute une prise en charge pour les éléments suivants:-recompiled pour x86, ajout de la prise en charge de surface Pro 7, surface Pro X et surface Laptop 3. 

### Version 1.12.239.0
*Date de publication: 26 avril 2019*<br>
Cette version du contrôle de luminosité de surface ajoute une prise en charge pour les éléments suivants:
- Correction des retards.


## Rubriques connexes

- [Paramètre de limite de batterie](battery-limit.md)
