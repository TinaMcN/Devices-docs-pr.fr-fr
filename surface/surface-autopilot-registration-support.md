---
title: Prise en charge de l’inscription de surface pour Windows AutoPilot
description: Cet article décrit la configuration requise pour envoyer des demandes d’enregistrement d’AutoPilot au support technique Microsoft.
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
ms.openlocfilehash: 9a308edb37cc2cfd99490acad16bd2ae6a4d458a
ms.sourcegitcommit: c2df79cab0e59e9d7ea6640e5899531b57cd383f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/16/2020
ms.locfileid: "11016470"
---
# Prise en charge de l’inscription de surface pour Windows AutoPilot

Un processus simplifié d’inscription des appareils surface pour le déploiement de Windows AutoPilot est désormais disponible auprès du support technique de Microsoft. Le début du 2020 de septembre, les clients et les fournisseurs de solutions de Cloud Computing Microsoft (CSP) peuvent enregistrer des appareils surface en envoyant des demandes au support Microsoft. Cette page présente la configuration requise pour les scénarios d’inscription AutoPilot suivants pris en charge:
 

- **Enregistrement**automatique du pilotage de surface Envoie une demande d’enregistrement de périphériques de surface dans Windows AutoPilot.
- **Demande de hachage du matériel du périphérique surface.** Envoie une demande d’assistance au support technique de Microsoft pour vous fournir des hachages physiques qui peuvent être utilisés par les clients ou fournisseurs de services de cryptographie pour l’auto-enregistrement de périphériques via Microsoft Intune ou le Centre des partenaires Microsoft.
- **Annulation du pilotage automatique de l’appareil surface.** Envoie une demande de suppression d’appareils à partir du pilotage automatique Windows, généralement utilisé dans les scénarios de fin de vie de l’appareil.

Consultez le tableau ci-dessous pour obtenir des informations détaillées sur les informations dont vous devez disposer avant de soumettre des demandes d’inscription au support technique Microsoft.
 
**Tableau1. Informations requises pour les demandes d’inscription au pilotage automatique**
 

| Informations requises                   | Description                                                                                                                                                                                                                                                                                    | Inscription AutoPilot | Demande de hachage matérielle | AutoPilot<br>Annulation |
| -------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------- | --------------------- | --------------------------- |
| **ID de client Azure Active Directory**   | Votre ID de client Azure Active Directory est un identificateur global unique (GUID) qui est différent du nom ou du domaine de votre organisation.<br> <br>Pour trouver votre ID de [locataire, accédez](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)au portail Azure. | Y                      | N                     | Y                           |
| **Nom de domaine Azure Active Directory** | Le nom de domaine de niveau supérieur; par exemple, contoso.com.                                                                                                                                                                                                                                          | Y                      | N                     | Y                           |
| **Preuve de propriété**                 | Confirmez la preuve de propriété en chargeant la facture d’origine ou la facture au format PDF. Les captures d’écran ne sont pas acceptées.<br> <br>La facture ou la facture doit inclure ce qui suit:<br>Numéros de série de périphériques.<br>Nom de la société.                                                           | Y                      | Y                     | Y                           |
| **Numéros de série de périphériques**              | Téléchargez un fichier Excel au format CSV avec chaque numéro de série de l’appareil sur une nouvelle ligne.                                                                                                                                                                                                                  | Y                      | Y                     | Y                           |

 

## Envoi des demandes de support

  [![Get prise en charge de l’enregistrement AutoPilot pour surface](images/autopilot-reg-support-surface.png)](https://support.microsoft.com/supportrequestform/0d8bf192-cab7-6d39-143d-5a17840b9f5f)
 
 
 
## En savoir plus

- [Windows Autopilot et appareils Surface](windows-autopilot-and-surface-devices.md)
- [Inscrire des appareils Windows à Intune à l’aide de Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)
- [Vue d’ensemble de Windows Autopilot](https://docs.microsoft.com/mem/autopilot/windows-autopilot)

 
 
 

