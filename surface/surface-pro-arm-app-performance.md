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
ms.date: 10/01/2020
ms.reviewer: jessko
manager: laurawi
ms.audience: itpro
ms.openlocfilehash: 40aa2a89c3f3c4371d2a6ecaeb8d2769e5b420f7
ms.sourcegitcommit: e0047f07c42b1e3cbd074b66a4704ea72e9d7bae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/02/2020
ms.locfileid: "11093914"
---
# Compatibilité des applications Surface ProX



 ![Image d’un utilisateur d’un PC](images/4527790_en_4.png)<br><br>



Les PC Windows 10 ARM vous permettent de continuer à travailler où que vous soyez. Voici quelques-uns des avantages principaux:

- **Toujours connecté à Internet.** Grâce à une connexion de données cellulaires, vous pouvez vous connecter à n’importe quel appareil mobile, comme avec votre téléphone mobile. Lorsque vous êtes au travail, chez vous ou à l’aide d’un autre réseau Wi-Fi approuvé, vous pouvez vous connecter à un réseau Wi-Fi pour enregistrer les données cellulaires et continuer à travailler.

- **Durée de vie de la batterie supérieure à toute la journée.**  La consommation d’énergie est moins importante que sur les autres PC, vous pouvez donc passer d’une journée de travail ou d’un établissement scolaire classique sans manquer de batterie ou vous soucier du branchement d’une prise. Si vous voulez utiliser votre PC pour une plus grande plaisir, vous pouvez lire des vidéos stockées sur votre ordinateur pendant plus d’heures sans recharger votre batterie.

- **Activez instantanément.** Lorsque vous n’utilisez pas votre PC, il suffit d’appuyer sur le bouton d’alimentation comme sur votre téléphone mobile pour désactiver l’écran. Lorsque vous prenez votre PC et que vous le réactivez, il s’allume instantanément. Chaque fois que vous avez quelques minutes entre les classes, les réunions ou d’autres activités, vous pouvez accomplir vos tâches sans attendre le démarrage de votre PC.

Notez que les applications s’exécutent différemment sur les PC Windows 10 ARM tels que surface Pro X. les limitations incluent les suivantes:

- **Les pilotes pour matériel, jeux et applications ne fonctionnent que s’ils sont conçus pour un PC Windows 10 ARM**. Pour plus d’informations, contactez le fabricant du matériel ou l’organisation qui a développé le pilote. Les pilotes sont des programmes logiciels qui communiquent avec des appareils physiques; ils sont souvent utilisés pour les logiciels antivirus et anti-programme malveillant, l’impression, les logiciels de protection de fichiers PDF, les technologies d’assistance, les utilitaires de CD et DVD et les logiciels de virtualisation. Si un pilote ne fonctionne pas, l’application ou le matériel qui s’en repose ne fonctionne pas (au moins). Les périphériques et périphériques fonctionnent uniquement si les pilotes qu’ils dépendent sont intégrés à Windows 10, ou si le développeur de matériel a désactivé les pilotes ARM64 pour l’appareil.
- **applications 64 bits (x64)** L’émulation de 64 bits est disponible dans la version d’évaluation par le biais du programme Windows Insider, vous pourrez exécuter des applications 64 bits (x64) sur surface Pro X. Sans la prise en charge de l’émulation de 64 bits, vous pouvez exécuter des applications 64 (ARM64), des applications 32 (ARM32) ou des applications 32 (x86) (à l’aide de l’émulateur x86). En règle générale, vous pouvez rechercher des versions de 32 bits (x86) d’applications, mais certains développeurs d’applications proposent uniquement des applications 64 bits (x64).
- **Certains jeux ne fonctionnent pas**. Les jeux et applications ne fonctionnent pas s’ils utilisent une version d’OpenGL supérieure à 1,1 ou s’ils s’appuient sur des pilotes de type «antifraude» qui n’ont pas été faits pour les PC Windows 10 ARM. Contactez votre éditeur de jeu pour savoir s’il fonctionne.
- **Les applications qui personnalisent l’interface Windows peuvent rencontrer des problèmes**. Cela inclut des éditeurs de méthode d’entrée (IME), des technologies d’assistance et des applications de stockage cloud. L’organisation qui développe l’application détermine si son application fonctionne sur un PC Windows 10 ARM.
- **Certains logiciels antivirus tiers ne peuvent pas être installés**. Vous ne serez pas en mesure d’installer un logiciel antivirus tiers sur un PC Windows 10 ARM. Toutefois, la sécurité Windows vous aide à protéger la durée de vie de votre appareil Windows 10 en toute sécurité.
- Le logiciel **télécopie et numérisation Windows n’est pas disponible**. Cette fonctionnalité n’est pas disponible sur un PC Windows 10 ARM.

## Garantie de l’application

Microsoft s’engage à garantir que les clients disposent d’une bonne qualité de compatibilité avec Windows 10 sur les appareils ARM64 tels que surface Pro X. Nous avons étendu le programme application pour garantir la prise en charge des clients qui rencontrent des problèmes de compatibilité des applications en permettant aux ingénieurs de résoudre les problèmes liés aux applications, sans aucun frais supplémentaire. Ce service est disponible pour les clients commerciaux et EDU pour vos applications métier, ISV et Microsoft tierces ciblant Windows 10 sur ARM64. 

Pour plus d’informations sur la compatibilité entre applications, voir [FAQ sur les ordinateurs Windows 10 ARM](https://support.microsoft.com/en-us/help/4521606).
