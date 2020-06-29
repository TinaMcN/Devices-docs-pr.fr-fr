---
title: Inscrire et configurer des appareils surface avec SEMM (surface)
description: Apprenez-en davantage sur la création d’un package de configuration de surface UEFI pour contrôler les paramètres de surface UEFI, ainsi que l’inscription d’un appareil surface dans SEMM.
keywords: gestion des entreprises de surface
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices, security
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
ms.audience: itpro
ms.reviewer: ''
manager: laurawi
ms.openlocfilehash: 183eceee47eba8b8d1e794e9e7d3efffa7a9b2e0
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10833480"
---
# Inscrire et configurer les appareilsSurface auprès de SEMM

Le mode de gestion de l’entreprise Microsoft surface (SEMM) vous permet de configurer en toute sécurité les paramètres de surface UEFI sur un appareil surface et de gérer ces paramètres sur les appareils surface de votre organisation. Lorsqu’un appareil surface est géré par SEMM, ce périphérique est considéré comme *inscrit* (parfois appelé activation). Cet article vous montre comment créer un package de configuration de surface UEFI qui ne doit contrôler que les paramètres de surface UEFI, mais également inscrire un appareil surface dans SEMM.

Pour une vue d’ensemble détaillée de SEMM, voir mode de gestion de l' [entreprise Microsoft surface](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode).

Une méthode simplifiée de gestion du microprogramme à partir du Cloud sur surface Pro 7, surface Pro X et surface Laptop 3 est désormais disponible via la version publique preview. Pour plus d’informations, reportez-vous à la rubrique [gestion Intune des paramètres de surface UEFI](surface-manage-dfci-guide.md).

> [!NOTE]
> SEMM est pris en charge sur surface Pro X par le biais du gestionnaire UEFI uniquement. Pour plus d’informations, reportez-vous à la rubrique [déploiement, gestion et maintenance de surface Pro X](surface-pro-arm-app-management.md).

#### Télécharger et installer Microsoft surface UEFI Configurator
L’outil utilisé pour créer des packages SEMM est Microsoft surface UEFI Configurator. Vous pouvez télécharger Microsoft surface configurateur à partir de la page [Outils surface pour cette application](https://www.microsoft.com/download/details.aspx?id=46703) dans le centre de téléchargement Microsoft.
Exécutez le fichier Windows Installer (. msi) Microsoft surface. Configurator pour démarrer l’installation de l’outil. À la fin du programme d’installation, recherchez Microsoft surface UEFI Configurator dans la section toutes les applications du menu Démarrer.

>[!NOTE]
>Le configurateur Microsoft surface UEFI est uniquement pris en charge sur Windows 10.

## Créer un package de configuration de surface UEFI

Le package de configuration de surface UEFI exécute le rôle de l’application d’une nouvelle configuration des paramètres de surface UEFI à un appareil de surface géré avec SEMM et au rôle d’inscription des appareils de surface dans SEMM. Lors de la création d’un package de configuration, vous devez disposer d’un certificat de signature à utiliser avec SEMM pour sécuriser la configuration des paramètres UEFI sur chaque périphérique surface. Pour plus d’informations sur la configuration requise pour le certificat SEMM, voir mode de gestion de l' [entreprise Microsoft surface](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode).

Pour créer un package de configuration de surface UEFI, procédez comme suit:

1. Ouvrez le configurateur Microsoft surface UEFI à partir du menu Démarrer.
2. Cliquez sur **Démarrer**.
3. Cliquez sur **package de configuration**, comme illustré dans la figure 1.

   ![Créer un package pour l’inscription de SEMM](images/surface-ent-mgmt-fig1-uefi-configurator.png "Create a package for SEMM enrollment")

   *Figure1. Sélectionner le package de configuration pour créer un package pour l’inscription et la configuration d’SEMM*

4. Cliquez sur **protection des certificats** pour ajouter le fichier de certificat exporté avec la clé privée (. pfx), comme illustré dans la figure 2. Naviguez jusqu’à l’emplacement de votre fichier de certificat, sélectionnez le fichier, puis cliquez sur **OK**.

   ![Ajouter le certificat SEM et le mot de passe UEFI de surface au package de configuration](images/surface-ent-mgmt-fig2-securepackage.png "Add the SEM certificate and Surface UEFI password to configuration package")

   *Figure2. Ajouter le certificat SEMM et le mot de passe UEFI de surface à un package de configuration UEFI de surface*

5. Lorsque vous êtes invité à confirmer le mot de passe du certificat, entrez et confirmez le mot de passe de votre fichier de certificat, puis cliquez sur **OK**.
6. Cliquez sur **protection par mot de passe** pour ajouter un mot de passe à la surface UEFI. Ce mot de passe est requis chaque fois que vous démarrez l’ordinateur. Si ce mot de passe n’est pas entré, seules les informations relatives à l' **ordinateur**, **à propos**de, à la gestion de l' **entreprise**et à la page de **sortie** seront affichées. Cette étape est facultative.
7. Lorsque vous y êtes invité, entrez et confirmez le mot de passe que vous avez choisi pour la surface UEFI, puis cliquez sur **OK**. Si vous souhaitez supprimer un mot de passe de surface UEFI existant, laissez le champ Password vide.
8. Si vous ne souhaitez pas que le package UEFI s’applique à un appareil particulier, dans la page **Choisissez le type de surface que vous souhaitez cibler** , cliquez sur le curseur situé sous le livret surface correspondant ou sur surface Pro 4 image pour le placer en position **désactivé** . (Comme illustré dans la figure 3.)
   > [!NOTE] 
   > Vous devez sélectionner un appareil tel qu’aucun n’est sélectionné par défaut.

   ![Sélectionner des appareils pour la compatibilité du package](images/surface-semm-enroll-fig3.jpg "Choose devices for package compatibility")

   *Figure3. Choisir les appareils pour la compatibilité du package*

9. Cliquez sur **Suivant**.
10. Si vous voulez désactiver un composant sur des appareils de surface gérée, dans la page **Choisissez quels composants vous souhaitez activer ou désactiver** , cliquez sur le curseur en regard de n’importe quel appareil ou groupe d’appareils que vous souhaitez désactiver de sorte que le curseur se trouve en position **désactivée** . (Illustré dans la figure 4.) La configuration par défaut de chaque appareil est **activée**. Cliquez sur le bouton **Réinitialiser** pour rétablir la position par défaut de toutes les diapositives.

    ![Désactiver ou activer les composants de surface](images/surface-ent-mgmt-fig3-enabledisable.png "Disable or enable Surface components")

    *Figure4. Désactiver ou activer des composants de surface individuels*

11. Cliquez sur **Suivant**.
12. Pour activer ou désactiver des options avancées dans surface UEFI ou l’affichage de pages UEFI de surface, sur la page **choisir les paramètres avancés pour vos appareils** , cliquez sur le curseur en regard du paramètre souhaité pour configurer cette option sur **activée** ou **désactivée** (illustrée dans la figure 5). Dans la section **page frontale UEFI** , vous pouvez utiliser les curseurs de **sécurité**, de **périphériques**et de **démarrage** pour contrôler les pages disponibles aux utilisateurs qui démarrent en surface UEFI. (Pour plus d’informations sur les paramètres de surface UEFI, voir [gérer les paramètres de surface UEFI](https://technet.microsoft.com/itpro/surface/manage-surface-uefi-settings).) Cliquez sur **générer** lorsque vous avez fini de sélectionner les options pour générer et enregistrer le package.

    ![Contrôle des paramètres de surface UEFI et des pages UEFI de surface](images/surface-ent-mgmt-fig4-advancedsettings.png "Control advanced Surface UEFI settings and Surface UEFI pages")

    *Figure5. Contrôler les paramètres de surface UEFI et les pages UEFI de surface avec SEMM*

13. Dans la boîte de dialogue **Enregistrer sous** , spécifiez un nom pour le package de configuration de surface UEFI, accédez à l’emplacement où vous souhaitez enregistrer le fichier, puis cliquez sur **Enregistrer**.
14. Lorsque le package est créé et enregistré, la page **réussie** s’affiche.

>[!NOTE]
>Enregistrez les caractères d’empreinte de certificat qui s’affichent sur cette page, comme illustré dans la figure 6. Vous aurez besoin de ces caractères pour confirmer l’inscription des nouveaux appareils surface dans SEMM. Cliquez sur **Terminer** pour terminer la création du package et fermer le configurateur Microsoft surface UEFI.

![Affichage des caractères d’empreinte numérique du certificat](images/surface-ent-mgmt-fig5-success.png "Display of certificate thumbprint characters")

*Figure6. Les deux derniers caractères de l’empreinte numérique du certificat s’affichent dans la page réussite*

À présent que vous avez créé votre package de configuration UEFI de surface, vous pouvez inscrire ou configurer des appareils surface.

>[!NOTE]
>Lors de la création d’un package de configuration de surface UEFI, un fichier journal est créé sur le bureau avec les détails des paramètres et options du package de configuration.

## Inscrire un appareil surface dans SEMM
Lorsque le package de configuration de surface UEFI est en cours d’exécution, le certificat SEMM et les fichiers de configuration UEFI de surface sont intermédiaires dans le stockage du microprogramme de l’appareil surface. Lors du redémarrage de l’appareil surface, UEFI traite ces fichiers et commence le processus d’application de la configuration UEFI de surface ou de l’inscription de l’appareil surface dans SEMM, comme illustré dans la figure 7.

![Processus SEMM pour la configuration de la surface UEFI ou de l’inscription](images/surface-semm-enroll-fig7.png "SEMM process for configuration of Surface UEFI or enrollment")

*Figure7. Processus SEMM pour la configuration de surface UEFI ou d’inscription d’un appareil surface*

Avant de commencer le processus d’inscription d’un appareil surface dans SEMM, assurez-vous que vous avez bien les deux derniers caractères de l’empreinte de certificat. Vous aurez besoin de ces caractères pour confirmer l’inscription de l’appareil (voir figure 6).

Pour inscrire un appareil surface dans SEMM à l’aide d’un package de configuration UEFI de surface, procédez comme suit:

1. Exécutez le fichier Package. msi de configuration de surface UEFI sur le périphérique surface que vous voulez inscrire dans SEMM. Le fichier de configuration de surface UEFI est alors mis en service dans le microprogramme de l’appareil.
2. Cochez la case **J’accepte les termes du contrat de licence** pour accepter le contrat de licence utilisateur final (CLUF), puis cliquez sur **installer** pour démarrer le processus d’installation.
3. Cliquez sur **Terminer** pour achever l’installation du package de configuration de surface UEFI, puis redémarrez l’appareil surface lorsque vous êtes invité à le faire.
4. Surface UEFI charge le fichier de configuration et détermine que SEMM n’est pas activé sur l’appareil. Surface UEFI démarre alors le processus d’inscription SEMM, comme suit:
   * Surface UEFI vérifie que le fichier de configuration SEMM contient un certificat SEMM.
   * Surface UEFI vous invite à entrer les deux derniers caractères de l’empreinte numérique du certificat pour confirmer l’inscription de l’appareil surface dans SEMM, comme illustré dans la figure 8.

      ![L’inscription de SEMM nécessite les deux derniers caractères de l’empreinte numérique du certificat](images/surface-semm-enroll-fig8.png "SEMM enrollment requires last two characters of certificate thumbprint")

      *Figure8. L’inscription dans SEMM nécessite les deux derniers caractères de l’empreinte numérique du certificat.*

   * Surface UEFI stocke le certificat SEMM dans le microprogramme et applique les paramètres de configuration spécifiés dans le fichier de configuration de surface UEFI.
   
5. Le périphérique surface est désormais inscrit dans SEMM et démarre à Windows.

Vous pouvez vérifier qu’un appareil surface a été correctement inscrit dans SEMM en recherchant le package de **configuration de surface Microsoft** dans **les programmes et fonctionnalités** (comme illustré dans la figure 9), ou dans les événements stockés dans le journal de **configuration de Microsoft surface UEFI** , qui se trouvent sous **journaux des applications et services** dans l’observateur d’événements (comme illustré dans la figure 10).

![Vérifier l’inscription d’un appareil surface dans SEMM dans les programmes et fonctionnalités](images/surface-semm-enroll-fig9.png "Verify enrollment of Surface device in SEMM in Programs and Features")

*Figure9. Vérification de l’inscription d’un appareil surface dans SEMM dans les programmes et fonctionnalités*

![Vérifier l’inscription d’un appareil surface dans SEMM dans l’observateur d’événements](images/surface-semm-enroll-fig10.png "Verify enrollment of Surface device in SEMM in Event Viewer")

*Figure10. Vérifier l’inscription d’un appareil surface dans SEMM dans l’observateur d’événements*

Vous pouvez également vérifier que l’appareil est inscrit dans SEMM dans surface UEFI, pendant que l’appareil est inscrit, que surface UEFI contiendra la page gestion de l' **entreprise** (comme illustré dans la figure 11).

![Page de gestion de surface UEFI entreprise](images/surface-semm-enroll-fig11.png "Surface UEFI Enterprise management page")

*Figure11. Page de gestion de surface UEFI entreprise*


## Configurer les paramètres de surface UEFI avec SEMM

Une fois qu’un appareil est inscrit dans SEMM, vous pouvez exécuter des packages de configuration de surface UEFI signés avec le même certificat SEMM pour appliquer les nouveaux paramètres UEFI de surface. Ces paramètres sont appliqués automatiquement lors du prochain démarrage de l’appareil, sans intervention de l’utilisateur. Vous pouvez utiliser des solutions de déploiement d’application telles que le gestionnaire de configuration de point de terminaison Microsoft pour déployer des packages de configuration de surface UEFI vers des appareils surface afin de modifier ou de gérer les paramètres dans surface UEFI.

Pour plus d’informations sur le déploiement de fichiers Windows Installer (. msi) avec Configuration Manager, voir [déployer et gérer des applications avec Microsoft Endpoint Configuration Manager](https://technet.microsoft.com/library/mt627959).

Si vous avez sécurisé surface UEFI à l’aide d’un mot de passe, les utilisateurs ne disposant pas du mot de passe qui tente de démarrer dans surface UEFI ne disposeront que des **informations**sur le PC, sur la **gestion**de l’entreprise et **sur**les pages de **sortie** .

Si vous n’avez pas sécurisé surface UEFI à l’aide d’un mot de passe ou si un utilisateur entre correctement le mot de passe, les paramètres qui sont configurés avec SEMM seront grisés (indisponibles) et le texte que les paramètres sont gérés par votre organisation s’affichera en haut de la page, comme illustré dans la figure 12.

![Paramètres gérés par SEMM désactivés dans surface UEFI](images/surface-semm-enroll-fig12.png "Settings managed by SEMM disabled in Surface UEFI")

*Figure12. Les paramètres gérés par SEMM seront désactivés dans surface UEFI.*
