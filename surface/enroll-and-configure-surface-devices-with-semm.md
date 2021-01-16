---
title: Inscrire et configurer des appareils Surface avec SEMM (Surface)
description: Découvrez comment créer un package de configuration UEFI Surface pour contrôler les paramètres de l’UEFI Surface, et inscrire un appareil Surface dans SEMM.
keywords: gestion d’entreprise surface
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices, security
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
ms.audience: itpro
ms.reviewer: hachinda
manager: laurawi
ms.date: 1/15/2021
ms.openlocfilehash: f310b4a43a8a0fc0e77295344ac723770ce821bc
ms.sourcegitcommit: 1b86286bd13b13749ddbf454ae78d9a24fec44ee
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "11271061"
---
# Inscrire et configurer les appareilsSurface auprès de SEMM

Avec microsoft Surface Enterprise Management Mode (SEMM), vous pouvez configurer en toute sécurité les paramètres de l’UEFI Surface sur un appareil Surface et gérer ces paramètres sur les appareils Surface de votre organisation. Lorsqu’un appareil Surface est géré par SEMM, il est considéré comme étant inscrit *(parfois* appelé activé). Cet article vous montre comment créer un package de configuration UEFI Surface qui non seulement contrôle les paramètres de l’UEFI Surface, mais inscrit également un appareil Surface dans SEMM.

Pour une vue d’ensemble plus générale de SEMM, voir [Microsoft Surface Enterprise Management Mode](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode).

En remplacement de SEMM, les appareils Surface les plus nouveaux peuvent gérer à distance un sous-ensemble de paramètres de microprogramme via Microsoft Intune. Pour plus d’informations, reportez-vous à [la gestion Intune des paramètres UEFI Surface.](surface-manage-dfci-guide.md)

> [!NOTE]
> SEMM est uniquement pris en charge sur Surface Pro X via le Gestionnaire UEFI. Pour plus d’informations, reportez-vous [au déploiement, à la gestion et à la maintenance de Surface Pro X.](surface-pro-arm-app-management.md)

#### Télécharger et installer microsoft Surface UEFI Configurator

L’outil utilisé pour créer des packages SEMM est Microsoft Surface UEFI Configurator. Vous pouvez télécharger microsoft Surface UEFI Configurator à partir de la page [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) du Centre de téléchargement Microsoft.
Exécutez le fichier Microsoft Surface UEFI Configurator Windows Installer (.msi) pour démarrer l’installation de l’outil. Une fois le programme d’installation terminé, recherchez Microsoft Surface UEFI Configurator dans la section Toutes les applications de votre menu Démarrer.

>[!NOTE]
>Microsoft Surface UEFI Configurator est pris en charge uniquement sur Windows 10.

## Créer un package de configuration UEFI Surface

Le package de configuration UEFI Surface joue à la fois le rôle d’application d’une nouvelle configuration des paramètres UEFI Surface à un appareil Surface géré avec SEMM et le rôle d’inscription des appareils Surface dans SEMM. La création d’un package de configuration nécessite l’utilisation d’un certificat de signature avec SEMM pour sécuriser la configuration des paramètres UEFI sur chaque appareil Surface. Pour plus d’informations sur les conditions requises pour le certificat SEMM, voir [Microsoft Surface Enterprise Management Mode](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode).

Pour créer un package de configuration UEFI Surface, suivez les étapes suivantes :

1. Ouvrez microsoft Surface UEFI Configurator à partir du menu Démarrer.
2. Cliquez sur **Démarrer**.
3. Cliquez **sur Package de configuration,** comme illustré dans la figure 1.

   ![Créer un package pour l’inscription SEMM](images/surface-ent-mgmt-fig1-uefi-configurator.png "Create a package for SEMM enrollment")

   *Figure1. Sélectionnez le package de configuration pour créer un package pour l’inscription et la configuration SEMM*

4. Cliquez **sur Protection des** certificats pour ajouter votre fichier de certificat exporté avec une clé privée (.pfx), comme illustré dans la figure 2. Accédez à l’emplacement de votre fichier de certificat, sélectionnez le fichier, puis cliquez sur **OK.**

   ![Ajouter le certificat SEM et le mot de passe UEFI Surface au package de configuration](images/surface-ent-mgmt-fig2-securepackage.png "Add the SEM certificate and Surface UEFI password to configuration package")

   *Figure2. Ajouter le certificat SEMM et le mot de passe UEFI Surface à un package de configuration UEFI Surface*

5. Lorsque vous êtes invité à confirmer le mot de passe du certificat, entrez et confirmez le mot de passe de votre fichier de certificat, puis cliquez sur **OK**.
6. Cliquez **sur Protection par mot de** passe pour ajouter un mot de passe à l’UEFI Surface. Ce mot de passe est requis chaque fois que vous démarrez sur UEFI. Si ce mot de passe n’est pas entré, seules les **informations de PC**, À propos de , Gestion de l’entreprise et Quitter les pages seront affichées. **** **** **** Cette étape est facultative.
7. Lorsque vous y êtes invité, entrez et confirmez le mot de passe que vous avez choisi pour l’UEFI Surface, puis cliquez sur **OK**. Si vous souhaitez effacer un mot de passe UEFI Surface existant, laissez le champ mot de passe vide.
8. Si vous ne souhaitez pas que le package UEFI Surface s’applique à un appareil particulier, dans la page Choisir le **type de Surface** que vous souhaitez cibler, cliquez sur le curseur sous l’image Surface Book ou Surface Pro 4 correspondante afin qu’il se trouve en position Hors connexion. **** (Comme le montre la figure 3.)
   > [!NOTE] 
   > Vous devez sélectionner un appareil, car aucun n’est sélectionné par défaut.

   ![Choisir des appareils pour la compatibilité des packages](images/surface-semm-enroll-fig3.jpg "Choose devices for package compatibility")

   *Figure3. Choisir les appareils pour la compatibilité des packages*

9. Cliquez sur **Suivant**.
10. Si vous souhaitez désactiver un composant sur les appareils Surface **gérés,** dans la page Choisir les composants que vous souhaitez activer ou désactiver, cliquez sur le curseur à côté de n’importe quel appareil ou groupe d’appareils que vous souhaitez désactiver afin que le curseur soit en **position** Désactivée. (Illustré dans la figure 4.) La configuration par défaut de chaque appareil est **sur**. Cliquez sur **le bouton** Réinitialiser si vous souhaitez rétablir la position par défaut de tous les curseurs.

    ![Désactiver ou activer les composants Surface](images/surface-ent-mgmt-fig3-enabledisable.png "Disable or enable Surface components")

    *Figure4. Désactiver ou activer des composants Surface individuels*

11. Cliquez sur **Suivant**.
12. Pour activer ou désactiver les options avancées dans l’UEFI Surface ou l’affichage des pages UEFI Surface, dans la page Choisir les **paramètres** avancés de vos appareils, cliquez sur le curseur en dehors du paramètre souhaité pour configurer cette option sur **Activé** ou Désactivé **(illustré** à la figure 5). Dans la section Page d’accueil **UEFI,** vous **** pouvez utiliser **** les curseurs pour la **sécurité,** les périphériques et le démarrage pour contrôler les pages disponibles pour les utilisateurs qui démarrent dans l’UEFI Surface. (Pour plus d’informations sur les paramètres UEFI Surface, voir Gérer les [paramètres UEFI Surface.)](https://technet.microsoft.com/itpro/surface/manage-surface-uefi-settings) Cliquez **sur Générer** lorsque vous avez terminé de sélectionner les options à générer et à enregistrer le package.

    ![Contrôler les paramètres UEFI Surface avancés et les pages UEFI Surface](images/surface-ent-mgmt-fig4-advancedsettings.png "Control advanced Surface UEFI settings and Surface UEFI pages")

    *Figure5. Contrôler les paramètres UEFI Surface avancés et les pages UEFI Surface avec SEMM*

13. Dans la **boîte** de dialogue Enregistrer sous, spécifiez un nom pour le package de configuration UEFI Surface, accédez à l’emplacement où vous souhaitez enregistrer le fichier, puis cliquez sur **Enregistrer**.
14. Lorsque le package est créé et enregistré, **la** page Réussite s’affiche.

>[!NOTE]
>Enregistrez les caractères d’empreinte numérique de certificat qui sont affichés sur cette page, comme le montre la figure 6. Vous aurez besoin de ces caractères pour confirmer l’inscription des nouveaux appareils Surface dans SEMM. Cliquez **sur Fin** pour terminer la création du package et fermez microsoft Surface UEFI Configurator.

![Affichage des caractères d’empreinte numérique du certificat](images/surface-ent-mgmt-fig5-success.png "Display of certificate thumbprint characters")

*Figure6. Les deux derniers caractères de l’empreinte numérique du certificat sont affichés sur la page Réussite*

Maintenant que vous avez créé votre package de configuration UEFI Surface, vous pouvez inscrire ou configurer des appareils Surface.

>[!NOTE]
>Lorsqu’un package de configuration UEFI Surface est créé, un fichier journal est créé sur le bureau avec les détails des paramètres et options du package de configuration.

## Inscrire un appareil Surface dans SEMM
Lorsque le package de configuration UEFI Surface est exécuté, le certificat SEMM et les fichiers de configuration UEFI Surface sont mis en place dans le stockage du microprogramme de l’appareil Surface. Lorsque l’appareil Surface redémarre, l’UEFI Surface traite ces fichiers et commence le processus d’application de la configuration UEFI Surface ou d’inscription de l’appareil Surface dans SEMM, comme le montre la figure 7.

![Processus SEMM pour la configuration de Surface UEFI ou l’inscription](images/surface-semm-enroll-fig7.png "SEMM process for configuration of Surface UEFI or enrollment")

*Figure7. Processus SEMM pour la configuration de l’UEFI Surface ou l’inscription d’un appareil Surface*

Avant de commencer le processus d’inscription d’un appareil Surface dans SEMM, assurez-vous que vous avez les deux derniers caractères de l’empreinte numérique du certificat. Vous aurez besoin de ces caractères pour confirmer l’inscription de l’appareil (voir figure 6).

Pour inscrire un appareil Surface dans SEMM avec un package de configuration UEFI Surface, suivez les étapes suivantes :

1. Exécutez le fichier .msi du package de configuration UEFI Surface sur l’appareil Surface que vous souhaitez inscrire dans SEMM. Cela permet de mettre en service le fichier de configuration UEFI Surface dans le microprogramme de l’appareil.
2. Cochez **la case J’accepte** les termes de la case contrat de licence pour accepter le contrat de licence utilisateur final, puis cliquez sur **Installer** pour commencer le processus d’installation.
3. Cliquez **sur Terminer** pour terminer l’installation du package de configuration UEFI Surface et redémarrez l’appareil Surface lorsque vous y êtes invité.
4. Surface UEFI charge le fichier de configuration et détermine que SEMM n’est pas activé sur l’appareil. Surface UEFI démarre ensuite le processus d’inscription SEMM, comme suit :
   * Surface UEFI vérifie que le fichier de configuration SEMM contient un certificat SEMM.
   * L’UEFI Surface vous invite à entrer les deux derniers caractères de l’empreinte numérique du certificat pour confirmer l’inscription de l’appareil Surface dans SEMM, comme illustré à la Figure 8.

      ![L’inscription SEMM nécessite les deux derniers caractères de l’empreinte numérique du certificat](images/surface-semm-enroll-fig8.png "SEMM enrollment requires last two characters of certificate thumbprint")

      *Figure8. L’inscription dans SEMM nécessite les deux derniers caractères de l’empreinte numérique du certificat*

   * Surface UEFI stocke le certificat SEMM dans le microprogramme et applique les paramètres de configuration spécifiés dans le fichier de configuration UEFI Surface.
   
5. L’appareil Surface est désormais inscrit à SEMM et démarre sur Windows.

Vous pouvez vérifier qu’un appareil Surface a été inscrit avec succès au seMM en cherchant le package de **configuration Microsoft Surface** dans **Programmes** et fonctionnalités (comme illustré à la figure 9) ou dans les événements stockés dans le journal du configurateur **UEFI Microsoft Surface,** qui se trouvent sous **Journaux** des applications et des services dans l’Observateur d’événements (comme illustré à la figure 10).

![Vérifier l’inscription de l’appareil Surface dans SEMM dans programmes et fonctionnalités](images/surface-semm-enroll-fig9.png "Verify enrollment of Surface device in SEMM in Programs and Features")

*Figure9. Vérifier l’inscription d’un appareil Surface dans SEMM dans Programmes et fonctionnalités*

![Vérifier l’inscription de l’appareil Surface dans SEMM dans l’Observateur d’événements](images/surface-semm-enroll-fig10.png "Verify enrollment of Surface device in SEMM in Event Viewer")

*Figure10. Vérifier l’inscription d’un appareil Surface dans SEMM dans l’Observateur d’événements*

Vous pouvez également vérifier que l’appareil est inscrit au seMM dans l’UEFI Surface . Pendant que l’appareil est inscrit, l’UEFI Surface contient la **page** de gestion d’entreprise (comme illustré dans la figure 11).

![Page de gestion UEFI Entreprise Surface](images/surface-semm-enroll-fig11.png "Surface UEFI Enterprise management page")

*Figure11. Page De gestion UEFI Entreprise Surface*


## Configurer les paramètres UEFI Surface avec SEMM

Une fois qu’un appareil est inscrit à SEMM, vous pouvez exécuter des packages de configuration UEFI Surface signés avec le même certificat SEMM pour appliquer de nouveaux paramètres UEFI Surface. Ces paramètres sont appliqués automatiquement lors du prochain démarrement de l’appareil, sans aucune interaction de l’utilisateur. Vous pouvez utiliser des solutions de déploiement d’applications telles que Microsoft Endpoint Configuration Manager pour déployer des packages de configuration UEFI Surface sur des appareils Surface afin de modifier ou de gérer les paramètres de Surface UEFI.

Pour plus d’informations sur le déploiement de fichiers Windows Installer (.msi) avec Configuration Manager, voir Déployer et gérer des applications avec [Microsoft Endpoint Configuration Manager.](https://technet.microsoft.com/library/mt627959)

Si vous avez sécurisé l’UEFI Surface avec un mot de passe, les utilisateurs sans le mot de passe qui tentent de démarrer sur Surface UEFI n’auront que les **informations** de **PC** **,** À propos **de**, Gestion de l’entreprise et Quitter les pages qui leur sont affichées.

Si vous n’avez pas sécurisé l’interface UEFI Surface avec un mot de passe ou si un utilisateur entre le mot de passe correctement, les paramètres configurés avec SEMM sont estommés (non disponibles) et le texte Certains paramètres sont gérés par votre organisation s’affiche en haut de la page, comme illustré à la figure 12.

![Paramètres gérés par SEMM désactivés dans Surface UEFI](images/surface-semm-enroll-fig12.png "Settings managed by SEMM disabled in Surface UEFI")

*Figure12. Les paramètres gérés par SEMM seront désactivés dans l’UEFI Surface*
