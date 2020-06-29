---
title: Personnaliser le modeOOBE pour les déploiements d’appareilsSurface
description: Cet article vous guidera à travers le processus de personnalisation de l’expérience OOBE Surface pour les utilisateurs finaux de votre organisation.
ms.assetid: F6910315-9FA9-4297-8FA8-2C284A4B1D87
ms.reviewer: ''
manager: laurawi
keywords: déployer, personnaliser, automatiser, réseau, stylet, coupler, démarrage
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.audience: itpro
ms.openlocfilehash: 97cc262d803875a76427d04c8f9b70547152f895
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10833269"
---
# Personnaliser le modeOOBE pour les déploiements d’appareilsSurface

Cet article décrit la personnalisation de l’interface hors du cadre pour les utilisateurs finaux au sein de votre organisation.

Une pratique courante dans le cadre d'un déploiementWindows consiste à personnaliser l'expérience utilisateur lors du premier démarrage des ordinateurs déployés (expérience OOBE).

>[!NOTE]
>OOBE est également souvent utilisé pour décrire la phase ou l’étape de configuration de l’installation de Windows au cours de laquelle l’expérience utilisateur est présentée. Pour en savoir plus sur la phase OOBE de l’installation, voir [Fonctionnement des étapes de configuration](https://msdn.microsoft.com/library/windows/hardware/dn898581.aspx).

Dans certains scénarios, vous voudrez peut-être assurer une automatisation complète pour garantir la disponibilité des ordinateurs en fin de déploiement, sans interaction de la part de l’utilisateur. Dans d’autres scénarios, vous voudrez peut-être omettre cette automatisation pour les éléments clés de l’expérience, afin que les utilisateurs puissent eux-mêmes effectuer les actions nécessaires ou choisir les options importantes. Pour les administrateurs qui déploient des appareils Surface, chacun de ces scénarios présente un défi unique à surmonter.

> [!NOTE]
> Cet article ne s’applique pas à surface Pro X. Pour plus d’informations, reportez-vous à [déploiement, gestion et maintenance de surface Pro X](surface-pro-arm-app-management.md) .

Cet article fournit un résumé des scénarios où un déploiement peut nécessiter des étapes supplémentaires. Il fournit également les informations nécessaires pour garantir que l’expérience souhaitée soit atteinte sur n’importe quel appareil Surface récemment déployé. Cet article est destiné aux administrateurs qui sont familiarisés avec le processus de déploiement, ainsi qu'avec des concepts tels que les fichiers de réponses et les [images de référence](https://technet.microsoft.com/itpro/windows/deploy/create-a-windows-10-reference-image).

>[!NOTE]
>Bien que la phase OOBE de l’installation soit toujours exécutée lors d’un déploiement avec une solution de déploiement automatisée telle que le kit de développement [Microsoft Deployment (MDT)](https://go.microsoft.com/fwlink/p/?LinkId=618117) ou le déploiement du système d’exploitation Microsoft Endpoint Manager (OSD), il est automatisé par les paramètres fournis dans l’Assistant Déploiement et la séquence de tâches. Pour plus d’informations, voir:<br/>
>- [Déployer Windows 10 avec Microsoft Deployment Toolkit](https://technet.microsoft.com/itpro/windows/deploy/deploy-windows-10-with-the-microsoft-deployment-toolkit)
>- [Déployer Windows 10 avec System Center 2012 R2 Configuration Manager](https://technet.microsoft.com/itpro/windows/deploy/deploy-windows-10-with-system-center-2012-r2-configuration-manager)

 

## Scénario1: Réseau sans fil et OOBE avec MDT2013


Lorsqu’une carte réseau sans fil est présente durant la phase OOBE, la page **Rejoindre un réseau sans fil** s’affiche, invitant l’utilisateur à se connecter à un réseau sans fil. Cette page n’est pas masquée automatiquement par les technologies de déploiement, y compris MDT2013; par conséquent, elle est affichée même lorsqu’un déploiement est configuré pour une automatisation complète.

Pour vous assurer qu’un déploiement automatisé n’est pas arrêté par cette page, cette dernière doit être masquée. Pour ce faire, un paramètre supplémentaire doit être configuré dans le fichier de réponses: **HideWirelessSetupInOOBE**. Vous trouverez des informations supplémentaires sur le paramètre **HideWirelessSetupInOOBE** dans [Guide de référence de l’installation de Windows sans assistance](https://technet.microsoft.com/library/ff716213.aspx).

## Scénario2: Couplage de Stylet Surface en mode OOBE


Lorsque vous démarrez un appareil SurfacePro3, SurfacePro4, SurfaceBook ou SurfaceStudio pour la première fois, l'introduction de l'interface logicielle lors de la première utilisation de l'image d'usine comprend une invite vous demandant de coupler le Stylet Surface inclus à l'appareil. Cette invite apparaît uniquement lorsque l’image d’usine de l’appareil s’affiche; elle n’est pas comprise dans d’autres images utilisées pour le déploiement, telles que le support d’installation WindowsEntreprise téléchargé à partir de Centre de gestion des licences en volumeMicrosoft. Étant donné que le couplage du stylet Surface Bluetooth en dehors de cette expérience requiert la définition des paramètres du Panneau de configuration ou des paramètres du PC, puis le couplage manuel d’un périphérique Bluetooth, vous devriez peut-être faire en sorte que les utilisateurs ou qu’un technicien utilisent cette invite pour effectuer l’opération de couplage.

Pour rendre possible l’expérience de couplage du stylet Surface en mode OOBE, vous devez copier quatre fichiers à partir de l’image d’usine Surface dans l’image de référence. Vous pouvez copier ces fichiers dans l’environnement de référence avant de capturer l’image de référence. Sinon, vous pouvez les ajouter ultérieurement à l’aide de la Gestion et maintenance des images de déploiement (DISM) afin de monter l’image. Les quatre fichiers requis sont:

-   %windir%\\system32\\oobe\\info\\default\\1033\\oobe.xml
-   %windir%\\system32\\oobe\\info\\default\\1033\\PenPairing\_en-US.png
-   %windir%\\system32\\oobe\\info\\default\\1033\\PenError\_en-US.png
-   %windir%\\system32\\oobe\\info\\default\\1033\\PenSuccess\_en-US.png

>[!NOTE]
>Vous devez copier les fichiers à partir d'une image d'usine relative au même modèle d'appareil Surface que celui que vous envisagez de déployer. Par exemple, vous devez utiliser les fichiers à partir de surface Pro 7 pour effectuer le déploiement sur surface Pro 7 et les fichiers à partir de surface Book 2 pour déployer surface Book 2, mais vous ne devez pas utiliser les fichiers à partir d’un appareil de surface pour le déploiement de surface Pro 7.

 

Le processus pas à pas pour l’ajout de ces fichiers requis à une image est décrit dans le billet de blog [Deploying Surface Pro 3 Pen and OneNote Tips (Conseils pour le déploiement du stylet SurfacePro3 et de OneNote)](https://blogs.technet.microsoft.com/askcore/2014/07/15/deploying-surface-pro-3-pen-and-onenote-tips/). Ce billet comprend également des conseils pour vous assurer que les mises à jour nécessaires relatives à la fonctionnalité de prise de notes rapide du stylet Surface sont installées, ce qui permet aux utilisateurs d’envoyer des notes à OneNote en un seul clic.

 

 





