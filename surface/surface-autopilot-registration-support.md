---
title: Prise en charge de l’inscription en surface pour Windows AutoPilot
description: Cet article décrit les conditions requises pour l’envoi de demandes d’inscription Autopilot au Support Microsoft.
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 9/14/2020
ms.reviewer: brrecord
manager: laurawi
audience: itpro
ms.openlocfilehash: 4ff3803701ffe71e1c5c0c36200c40e833a7fb25
ms.sourcegitcommit: 1053479c191fd10651d31a466fad1769fb0cd28b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/16/2021
ms.locfileid: "11271388"
---
# Prise en charge de l’inscription en surface pour Windows AutoPilot

Un processus simplifié d’inscription des appareils Surface pour le déploiement De Windows Autopilot est désormais disponible auprès du Support Microsoft. À compter de septembre 2020, les clients et les fournisseurs de solutions Microsoft Cloud (CSP) peuvent inscrire des appareils Surface en envoyant des demandes au support Microsoft. Cette page décrit les conditions requises pour les scénarios d’inscription Autopilot pris en charge suivants :
 

- **Surface Device Autopilot Registration**. Envoie une demande d’inscription des appareils Surface dans Windows Autopilot.
- **Demande de hachage matériel de l’appareil Surface.** Envoie une demande au support Microsoft pour vous fournir des hachages matériels que les clients ou les CSP peuvent utiliser pour inscrire eux-mêmes des appareils via Microsoft Intune ou l’Microsoft Partner Center.
- **Surface Device Autopilot Deregistration.** Envoie une demande de suppression d’appareils de Windows Autopilot, généralement utilisé dans les scénarios de fin de vie des appareils.

Consultez le tableau suivant pour plus d’informations sur les informations que vous devrez collecter avant d’envoyer des demandes d’inscription au Support Microsoft.
 
**Tableau1. Informations requises pour les demandes d’inscription Autopilot**
 

| Informations requises                   | Description                                                                                                                                                                                                                                                                                    | Autopilot Registration | Demande de hachage matériel | Autopilot<br>Deregistration |
| -------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------- | --------------------- | --------------------------- |
| **ID de client Azure Active Directory**   | Votre ID de client Azure Active Directory est un identificateur global unique (GUID) différent du nom ou du domaine de votre organisation.<br> <br>Pour trouver votre ID de client, connectez-vous au portail Azure [ici.](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) | Y                      | N                     | Y                           |
| **Nom de domaine Azure Active Directory** | Votre nom de domaine de niveau supérieur ; par exemple, contoso.com.                                                                                                                                                                                                                                          | Y                      | N                     | Y                           |
| **Preuve de propriété**                 | Vérifiez la preuve de propriété en téléchargeant la facture ou la facture d’origine au format PDF. Les captures d’écran ne sont pas acceptées.<br> <br>La facture doit inclure les suivants :<br>Numéros de série d’appareil.<br>Nom de la société.                                                           | Y                      | Y                     | Y                           |
| **Numéros de série d’appareil**              | Téléchargez un fichier Excel au format CSV avec chaque numéro de série d’appareil dans une nouvelle ligne.                                                                                                                                                                                                                  | Y                      | Y                     | Y                           |

 

## Envoyer des demandes de support

  [![Get Autopilot Registration Support for Surface](images/autopilot-reg-support-surface.png)](https://prod.support.services.microsoft.com/supportrequestform/0d8bf192-cab7-6d39-143d-5a17840b9f5f)
 
 
 
## Si vous souhaitez en savoir plus

- [Windows Autopilot et appareils Surface](windows-autopilot-and-surface-devices.md)
- [Inscrire des appareils Windows à Intune à l’aide de Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)
- [Vue d’ensemble de Windows Autopilot](https://docs.microsoft.com/mem/autopilot/windows-autopilot)

 
 
 

