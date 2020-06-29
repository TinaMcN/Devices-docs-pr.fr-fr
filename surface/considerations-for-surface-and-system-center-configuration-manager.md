---
title: Remarques concernant surface et Microsoft Endpoint Configuration Manager
description: La gestion et le déploiement de périphériques surface avec Configuration Manager sont fondamentalement les mêmes que sur tout autre PC. Cet article décrit des scénarios susceptibles de nécessiter des considérations supplémentaires.
keywords: gestion, déploiement, mises à jour, pilote, microprogramme
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
ms.audience: itpro
ms.reviewer: ''
manager: laurawi
ms.openlocfilehash: 4fa62d227deb0b0b07fa0fbc6552ea5b04c1b87b
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832567"
---
# Remarques concernant surface et Microsoft Endpoint Configuration Manager

Fondamentalement, la gestion et le déploiement des appareils surface avec Microsoft Endpoint Configuration Manager sont les mêmes que pour la gestion et le déploiement de tout autre PC. À l’instar des autres PC, un déploiement vers des appareils surface inclut l’importation de pilotes, l’importation d’une image Windows, la séquence de tâches de déploiement, puis le déploiement de la séquence de tâches sur une collection. Après le déploiement, les appareils surface sont comme n’importe quel autre client Windows; pour publier des applications, des paramètres et des stratégies, utilisez la même procédure que celle que vous utiliseriez pour tout autre appareil.

Pour plus d’informations sur l’utilisation du gestionnaire de configuration pour le déploiement et la gestion des appareils, voir la [documentation relative à Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/sccm/index).

Bien que le déploiement et la gestion des appareils de surface soient fondamentalement les mêmes que sur tout autre PC, il existe certains scénarios qui peuvent nécessiter des considérations ou des étapes supplémentaires. Cet article fournit des descriptions et des instructions pour ces scénarios. Les solutions décrites dans cet article s’appliquent également aux autres appareils et constructeurs.

> [!NOTE]
> Pour la gestion des appareils surface, il est recommandé d’utiliser la branche actuelle du gestionnaire de configuration de point de terminaison Microsoft.

## Mise à jour des pilotes de périphériques superficiel et du microprogramme

Pour les appareils qui reçoivent des mises à jour par le biais de Windows Update, les pilotes pour les composants de surface (et même les mises à jour de microprogramme) s’appliquent automatiquement dans le cadre du processus Windows Update. Pour les appareils avec des mises à jour gérées, telles que celles mises à jour via Windows Server Update Services (WSUS) ou Configuration Manager, voir [gérer les mises à jour du pilote de surface et du microprogramme](https://docs.microsoft.com/surface/manage-surface-driver-and-firmware-updates/).

> [!NOTE]
> Les pilotes de périphérique surface et le microprogramme sont signés avec SHA-256, qui n’est pas pris en charge en mode natif par Windows Server 2008 R2. Une solution de contournement est disponible pour les environnements Configuration Manager s’exécutant sur Windows Server 2008 R2. Pour plus d’informations, voir [Impossible d’importer des pilotes dans Microsoft Endpoint Configuration Manager (KB3025419)](https://support.microsoft.com/kb/3025419).

## Cartes Ethernet surface et déploiement du gestionnaire de configuration

Le mécanisme par défaut utilisé par le gestionnaire de configuration pour identifier les appareils lors du déploiement est l’adresse de contrôle d’accès au média (MAC). Dans la mesure où l’adresse MAC est associée à la manette Ethernet, une carte Ethernet partagée entre plusieurs appareils entraîne l’identification de chacun d’eux sur un seul appareil. Cela peut entraîner l’application d’un déploiement de Windows Manager à des appareils prévus.

Pour vous assurer que les appareils surface qui utilisent le même adaptateur Ethernet sont identifiés comme des appareils uniques au cours du déploiement, vous pouvez indiquer à Configuration Manager d’identifier les appareils à l’aide d’une autre méthode. Il peut s’agir de l’adresse MAC de la carte réseau sans fil ou de l’identificateur unique universel du système (UUID). Vous pouvez spécifier que Configuration Manager utilise d’autres méthodes d’identification avec les options suivantes:

* Ajoutez une exclusion pour les adresses MAC des cartes Ethernet surface, ce qui force le gestionnaire de configuration à ignorer l’adresse MAC par rapport aux préférences de l’UUID du système, comme indiqué dans la [réutilisation de la même carte réseau pour plusieurs déploiements PXE dans](https://blogs.technet.microsoft.com/system_center_configuration_manager_operating_system_deployment_support_blog/2015/08/27/reusing-the-same-nic-for-multiple-pxe-initiated-deployments-in-system-center-configuration-manger-osd/) le billet de blog OSD de Microsoft Endpoint Manager.

* Les appareils prédéfinis par UUID système comme indiqués dans la [réutilisation de la même carte réseau pour plusieurs déploiements PXE dans le billet de blog OSD de Microsoft Endpoint Manager](https://blogs.technet.microsoft.com/system_center_configuration_manager_operating_system_deployment_support_blog/2015/08/27/reusing-the-same-nic-for-multiple-pxe-initiated-deployments-in-system-center-configuration-manger-osd/) .

* Utilisez un script pour identifier un nouvel appareil surface déployé par l’adresse MAC de son adaptateur sans fil, comme indiqué dans l' [article utilisation de la même carte Ethernet externe pour plusieurs billets de blog OSD](https://blogs.technet.microsoft.com/askpfeplat/2014/07/27/how-to-use-the-same-external-ethernet-adapter-for-multiple-sccm-osd/) .

Une autre considération pour la carte Ethernet surface lors du déploiement avec Configuration Manager est le pilote pour le contrôleur Ethernet. À partir de Windows 10, version 1511, le pilote pour la carte Ethernet de surface est inclus par défaut dans Windows. Pour les organisations qui souhaitent déployer la dernière version de Windows 10 et utiliser la dernière version de WinPE, l’utilisation de la carte Ethernet surface ne nécessite aucune action supplémentaire.

Pour les versions de Windows antérieures à Windows 10, version 1511 (y compris Windows 10 RTM et Windows 8,1), il est possible que vous deviez installer le pilote de carte Ethernet de surface et inclure le pilote dans votre média de démarrage WinPE. Dans Windows 10, le pilote n’est plus disponible en téléchargement à partir du centre de téléchargement Microsoft. Pour télécharger le pilote de carte Ethernet de surface, téléchargez-le à partir du catalogue Microsoft Update, comme indiqué dans le billet de blog [périphériques Ethernet de surface](https://blogs.technet.microsoft.com/askcore/2016/08/18/surface-ethernet-drivers/) dans le blog poser une équipe.

## Déploiement de l’application de surface avec Configuration Manager

Avec la version de Microsoft Store pour les entreprises, l’application surface n’est plus disponible en tant que pilote et téléchargement du microprogramme. Les organisations qui souhaitent déployer l’application superficielle sur des appareils à surface gérées ou lors d’un déploiement avec Configuration Manager doivent acquérir une application de surface via le Microsoft Store pour entreprises, puis déployer l’application de surface avec PowerShell. Vous pouvez trouver les commandes PowerShell pour le déploiement de l’application surface, les instructions pour télécharger l’application surface et les infrastructures prérequises à partir de la boutique Microsoft pour les entreprises dans l’article déploiement de l' [application surface avec Microsoft Store pour les entreprises](https://technet.microsoft.com/itpro/surface/deploy-surface-app-with-windows-store-for-business) dans la bibliothèque TechNet.

## Utiliser du contenu multimédia prédéfini avec des clients de surface

Si votre organisation utilise des éléments multimédias prédéfinis pour le préchargement des ressources de déploiement sur des ordinateurs avant le déploiement avec Configuration Manager, la nature des appareils surface en tant qu’appareils UEFI risque de nécessiter des étapes supplémentaires. Plus précisément, un environnement UEFI natif nécessite que vous créez plusieurs partitions sur le disque de démarrage du système. Si vous suivez la documentation et la [documentation relative aux éléments multimédias prédéfinis](https://technet.microsoft.com/library/79465d90-4831-4872-96c2-2062d80f5583?f=255&MSPPError=-2147217396#BKMK_CreatePrestagedMedia), les instructions ne permettent d’utiliser que des disques de démarrage de partitions uniques, et par conséquent, ne peuvent pas être appliquées à des appareils surface.

Vous trouverez des instructions sur l’application de médias prédéfinis sur des appareils UEFI, tels que les appareils surface, dans la [page Ajouter des éléments multimédias prédéfinis sur les disques à partitions multiples pour le BIOS ou les PC UEFI dans le billet de blog Microsoft Endpoint Manager](https://blogs.technet.microsoft.com/system_center_configuration_manager_operating_system_deployment_support_blog/2014/04/02/how-to-apply-task-sequence-prestaged-media-on-multi-partitioned-disks-for-bios-or-uefi-pcs-in-system-center-configuration-manager/) .

## Conflits de licence avec l’activation OEM 3,0

Les appareils surface sont préinstallés avec une copie sous licence de Windows. Par exemple, surface Pro 4 est préinstallé avec Windows 10 professionnel. La clé de licence associée à cette copie de Windows est incorporée au microprogramme de l’appareil avec l’activation OEM 3,0 (OA 3,0). Lorsque vous exécutez un support d’installation Windows sur un appareil équipé d’une clé OA 3,0, le programme d’installation de Windows lit automatiquement la clé de licence et l’utilise pour installer et activer Windows. Dans la plupart des cas, vous simplifiez la réinstallation de Windows, car l’utilisateur n’a pas besoin de rechercher ou d’entrer une clé de licence.

Lorsque vous reimagez un appareil à l’aide de Windows entreprise, cette clé de licence incorporée ne cause aucun conflit. En effet, le support d’installation de Windows entreprise est configuré pour installer uniquement une édition Enterprise de Windows et est donc incompatible avec la clé de licence intégrée au microprogramme du système. Si aucune clé de produit n’est spécifiée (par exemple, quand vous envisagez d’activer avec des services de gestion de clés [KMS] ou Active Directory), une clé de licence en volume générique (clé) est utilisée tant que Windows n’est pas activé par l’une de ces technologies.

Toutefois, des problèmes peuvent se produire lorsque les organisations envisagent d’utiliser des versions de Windows compatibles avec la clé incorporée du microprogramme. Par exemple, dans le cadre de l’installation de Windows 10 professionnel sur un appareil surface 3 qui est fourni par le biais de Windows 10 édition familiale, il est possible que le programme d’installation détecte automatiquement la touche édition familiale au cours de l’installation et qu’elle s’installe en tant qu’édition familiale plutôt que professionnel. Pour éviter ce conflit, vous pouvez utiliser le fichier EI. cfg ou Pid.txt pour demander explicitement au programme d’installation de Windows d’inviter une clé de produit, ou vous pouvez entrer une clé de produit spécifique dans la séquence de tâches de déploiement. Pour plus d’informations, reportez-vous aux [fichiers de configuration et d’ID de produit Windows](https://technet.microsoft.com/library/hh824952.aspx). Si vous n’avez pas de clé spécifique, vous pouvez utiliser les clés de produit par défaut pour Windows, que vous pouvez trouver dans [personnaliser et déployer un système d’exploitation Windows 10](https://dpcenter.microsoft.com/en/Windows/Build/cp-Windows-10-build) sur le Centre des partenaires de périphériques.

## Appliquer une balise d’élément lors du déploiement

Surface Studio, Book surface, surface Pro 4, surface Pro 3 et appareils surface 3 prennent toutes en charge l’application d’une balise de ressources dans UEFI. Cette balise d’élément peut être utilisée pour identifier l’appareil à partir de UEFI, même en cas d’échec du système d’exploitation, et peut également être interrogé à partir du système d’exploitation. Pour en savoir plus sur la fonction de balise de surface de surface, voir l' [outil balise de ressources pour le billet de blog surface Pro 3](https://blogs.technet.microsoft.com/askcore/2014/10/20/asset-tag-tool-for-surface-pro-3/) .

Pour appliquer une balise de ressource à l’aide de l' [utilitaire ILC d’étiquette de surface de surface](https://www.microsoft.com/download/details.aspx?id=44076) dans une séquence de tâches de déploiement du gestionnaire de configuration, utilisez le script et les instructions figurant dans la [balise définir l’élément de surface dans un](https://blogs.technet.microsoft.com/jchalfant/set-surface-pro-3-asset-tag-during-a-configuration-manager-task-sequence/) billet de blog de séquence de tâches.

## Configuration de la réinitialisation du bouton bascule

Lorsque vous déployez Windows sur un appareil surface, la fonctionnalité de réinitialisation du bouton bascule de Windows est configurée par défaut pour rétablir l’état du système à l’emplacement où l’environnement n’est pas encore configuré. Lorsque la fonction Reset est utilisée, le système supprime les applications et paramètres installés. Même si dans certains cas, il peut être utile de restaurer le système dans un État sans application ni paramètre, dans un environnement professionnel qui rend le système inutilisable pour l’utilisateur final.

La fonction de réinitialisation du bouton bascule peut toutefois être configurée pour rétablir l’état de la configuration du système à un emplacement où il est prêt à être utilisé par l’utilisateur final. Suivez la procédure décrite dans [déployer les fonctionnalités](https://msdn.microsoft.com/windows/hardware/commercialize/manufacture/desktop/deploy-push-button-reset-features) de réinitialisation du bouton de déploiement pour personnaliser l’interface de réinitialisation de vos appareils.
