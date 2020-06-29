---
title: Compatibilité des applications Surface ProX
description: Cet article fournit des informations sur la compatibilité des applications d’introduction aux PC fonctionnant sous la surface Pro X ARM.
ms.prod: w10
ms.localizationpriority: medium
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 10/03/2019
ms.reviewer: jessko
manager: laurawi
ms.audience: itpro
ms.openlocfilehash: c236bf066d22cae80f4c0df39cc04450ad57a419
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10833192"
---
# Compatibilité des applications Surface ProX

Les applications s’exécutent différemment sur les PC Windows 10 ARM tels que surface Pro X. les limitations incluent les suivantes:

- **Les pilotes pour matériel, jeux et applications ne fonctionnent que s’ils sont conçus pour un PC Windows 10 ARM**. Pour plus d’informations, contactez le fabricant du matériel ou l’organisation qui a développé le pilote. Les pilotes sont des programmes logiciels qui communiquent avec des appareils physiques; ils sont souvent utilisés pour les logiciels antivirus et anti-programme malveillant, l’impression, les logiciels de protection de fichiers PDF, les technologies d’assistance, les utilitaires de CD et DVD et les logiciels de virtualisation. Si un pilote ne fonctionne pas, l’application ou le matériel qui s’en repose ne fonctionne pas (au moins). Les périphériques et périphériques fonctionnent uniquement si les pilotes qu’ils dépendent sont intégrés à Windows 10, ou si le développeur de matériel a désactivé les pilotes ARM64 pour l’appareil.
- **les applications 64 bits (x64) ne fonctionnent pas**. Vous aurez besoin des applications 64-bit (ARM64), des applications 32-bit (ARM32) ou des applications 32-bits (x86). En règle générale, vous pouvez rechercher des versions de 32 bits (x86) d’applications, mais certains développeurs d’applications proposent uniquement des applications 64 bits (x64).
- **Certains jeux ne fonctionnent pas**. Les jeux et applications ne fonctionnent pas s’ils utilisent une version d’OpenGL supérieure à 1,1 ou s’ils s’appuient sur des pilotes de type «antifraude» qui n’ont pas été faits pour les PC Windows 10 ARM. Contactez votre éditeur de jeu pour savoir s’il fonctionne.
- **Les applications qui personnalisent l’interface Windows peuvent rencontrer des problèmes**. Cela inclut des éditeurs de méthode d’entrée (IME), des technologies d’assistance et des applications de stockage cloud. L’organisation qui développe l’application détermine si son application fonctionne sur un PC Windows 10 ARM.
- **Certains logiciels antivirus tiers ne peuvent pas être installés**. Vous ne serez pas en mesure d’installer un logiciel antivirus tiers sur un PC Windows 10 ARM. Toutefois, la sécurité Windows vous aide à protéger la durée de vie de votre appareil Windows 10 en toute sécurité.
- Le logiciel **télécopie et numérisation Windows n’est pas disponible**. Cette fonctionnalité n’est pas disponible sur un PC Windows 10 ARM.

Pour plus d’informations sur la compatibilité des applications, voir [FAQ sur les ordinateurs Windows 10 ARM](https://support.microsoft.com/en-us/help/4521606)
