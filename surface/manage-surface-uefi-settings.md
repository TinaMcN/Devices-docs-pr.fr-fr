---
title: Gérer les paramètres UEFI Surface
description: Les paramètres UEFI Surface vous permettent d’activer ou de désactiver des périphériques ou des composants, de configurer les paramètres de sécurité et d’ajuster les paramètres de démarrage des appareils Surface.
keywords: microprogramme, sécurité, fonctionnalités, configurer, matériel
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: devices, surface
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: ''
manager: laurawi
ms.openlocfilehash: ce857260c3f4b42ae560a7dba51d47d0e20233bd
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10833408"
---
# Gérer les paramètres UEFI Surface

Toutes les générations actuelles et futures des appareils surface utilisent une interface de microprogramme unique unifiée (UEFI) conçue par Microsoft en particulier pour ces appareils. Les paramètres de surface UEFI permettent d’activer ou de désactiver les appareils et composants intégrés, de protéger les paramètres UEFI et de modifier les paramètres de démarrage de l’appareil surface. 

## Prise en charge de la gestion basée sur le Cloud

Les profils d’interface de configuration de microprogramme de périphériques (DFCI) intégrés à Microsoft Intune (désormais disponibles en préversion publique) permettent de faire en sorte que la gestion de surface UEFI étende la pile de gestion moderne au niveau matériel UEFI. DFCI prend en charge la mise en service des fonctions d’approvisionnement nulle, élimine les mots de passe BIOS et contrôle les paramètres de sécurité, notamment les options de démarrage et les périphériques intégrés, et vous permet de créer des scénarios de sécurité avancée à l’avenir. DFCI est actuellement disponible pour surface Pro 7, surface Pro X et surface Laptop 3. Pour plus d’informations, reportez-vous à la rubrique [gestion Intune des paramètres de surface UEFI](surface-manage-dfci-guide.md).

## Ouvrir le menu surface UEFI

Pour ajuster les paramètres UEFI lors du démarrage du système:

1. Arrêtez votre surface et attendez environ 10 secondes pour vous assurer qu’il est désactivé.
2. Appuyez de façon prolongée sur le bouton **volume** enfoncé et, en même temps, appuyez sur le **bouton d’alimentation** et relâchez-le.
3. Lorsque le logo Microsoft ou surface apparaît à l’écran, appuyez sur le bouton **volume** enfoncé jusqu’à ce que l’écran UEFI apparaisse.

## Page informations sur le PC UEFI

La page informations sur le PC inclut des informations détaillées sur votre périphérique surface: 

- **Modèle** : le modèle de votre appareil de surface s’affichera ici, par exemple surface Book 2 ou surface Pro 7. La configuration exacte de votre appareil (notamment le processeur, la taille du disque ou la taille de la mémoire) n’apparaît pas. 
- **UUID**: cet identificateur global unique est propre à votre appareil et sert à identifier l’appareil dans le cadre des processus de déploiement ou de gestion. 

- **Numéro de série**: ce numéro permet d’identifier cet appareil Surface spécifique pour les scénarios de support et d’étiquetage des ressources.
- **Étiquette d’inventaire**: l’étiquette d’inventaire est affectée à l’appareil Surface avec l’[Outil d’étiquette d’inventaire](https://docs.microsoft.com/surface/assettag). 

Ce champ fournit également des informations détaillées sur le microprogramme de votre appareil Surface. Les appareils Surface intègrent plusieurs composants internes exécutant chacun une version de microprogramme distincte. La version de microprogramme de chacun des composants ci-après est indiquée sur la page **Informations du PC** (comme illustré à la Figure1): 

- UEFI système 

- Contrôleur SAM 

- Moteur de gestion Intel 

- Contrôleur système embarqué 

- Microprogramme du contrôleur tactile 

![Informations système et informations sur les versions du microprogramme](images/manage-surface-uefi-figure-1.png "System information and firmware version information")

*Figure1. Informations système et informations sur les versions du microprogramme*

Vous trouverez des informations à jour sur la dernière version de microprogramme pour votre appareil Surface dans l’[Historique des mises à jour de MicrosoftSurface](https://www.microsoft.com/surface/support/install-update-activate/surface-update-history) de votre appareil. 

## Page de sécurité UEFI 

![Configurer les paramètres de sécurité UEFI Surface](images/manage-surface-uefi-fig4.png "Configure Surface UEFI security settings")

*Figure2. Configurer les paramètres de sécurité UEFI Surface*

La page sécurité vous permet de définir un mot de passe pour protéger les paramètres UEFI. Vous devez entrer ce mot de passe lorsque vous démarrez l’appareil Surface en mode UEFI. Le mot de passe peut contenir les caractères suivants (comme illustré dans la figure 3): 

- Lettres majuscules: A-Z 

- Lettres minuscules: a-z 

- Chiffres: 1-0 

- Caractères spéciaux:! @ # $% ^& * ()? <>{} []-_ = + |.,;: "'" 

Le mot de passe doit comporter au moins 6caractères et respecte la casse. 

![Ajouter un mot de passe pour protéger les paramètres UEFI Surface](images/manage-surface-uefi-fig2.png "Add a password to protect Surface UEFI settings")

*Figure3. Ajouter un mot de passe pour protéger les paramètres UEFI Surface*

La page Sécurité vous permet également de modifier la configuration du démarrage sécurisé sur votre appareil Surface. La technologie de démarrage sécurisé empêche tout démarrage d’un code de démarrage non autorisé sur votre appareil Surface, et vous offre ainsi une protection contre les infections par programmes malveillants de type bootkit ou rootkit. Vous pouvez désactiver le démarrage sécurisé si vous souhaitez permettre à votre appareil Surface de démarrer des systèmes d’exploitation ou des médias de démarrage tiers. Vous pouvez également configurer le démarrage sécurisé pour travailler avec des certificats tiers, comme illustré dans la figure 4. Apprenez-en davantage sur le [démarrage sécurisé](https://msdn.microsoft.com/windows/hardware/commercialize/manufacture/desktop/secure-boot-overview) dans la bibliothèque TechNet.

![Configurer le démarrage sécurisé](images/manage-surface-uefi-fig3.png "Configure Secure Boot")

*Figure4. Configurer le démarrage sécurisé*

En fonction de votre appareil, vous serez peut-être en mesure de voir si votre TPM est activé ou désactivé. Si vous ne voyez pas le paramètre **activer le module de plateforme sécurisée** , ouvrez TPM. msc dans Windows pour vérifier l’État, comme illustré dans la figure 5. Le module TPM permet d’authentifier le chiffrement des données de votre appareil avec BitLocker. Pour en savoir plus, voir [vue d’ensemble de BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview). 

![Console du TPM](images/manage-surface-uefi-fig5-a.png "TPM console")

*Figure5. Console du TPM*


## Menu UEFI: périphériques 

La page appareils vous permet d’activer ou de désactiver des appareils et composants spécifiques, notamment:

- Ports de station d’accueil et USB 

- Emplacement pour carte mémoire Secure Digital ou MicroSD 

- Caméra arrière 

- Caméra frontale 

- Caméra infrarouge (IR) 

- Wi-Fi et Bluetooth 

- Audio intégré (haut-parleurs et microphone) 

Chacun d’eux est répertorié avec un bouton **de** curseur que vous pouvez activer (activé) ou **désactivé** (désactivé), comme illustré dans la figure 6. 

![Activer et désactiver des périphériques spécifiques](images/manage-surface-uefi-fig5a.png "Enable and disable specific devices")

*Figure6. Activer et désactiver des périphériques spécifiques*

## Menu UEFI: configuration de démarrage 

La page Configuration de démarrage vous permet de changer l’ordre de vos périphériques de démarrage et d’activer ou de désactiver les appareils suivants: 

- Gestionnaire de démarrage Windows 

- Stockage USB 

- Réseau PXE (Preboot Execution Environment) 

- Stockage interne 

Vous pouvez démarrer immédiatement l’appareil à partir d’un périphérique spécifique, ou effectuer un mouvement de balayage vers la gauche sur l’entrée de ce périphérique dans la liste en utilisant l’écran tactile. Vous pouvez également démarrer immédiatement à partir d’un périphérique USB ou d’un adaptateur Ethernet USB lorsque l’appareil Surface est éteint en appuyant simultanément sur le bouton **Baisser le volume** et sur le bouton **Marche/Arrêt**. 

Pour que l’ordre de démarrage spécifié prenne effet, vous devez définir l’option Activer le mode de **démarrage alternatif** sur **activé**, comme illustré dans la figure 7. 

![Configurer l’ordre de démarrage de votre appareil Surface](images/manage-surface-uefi-fig6.png "Configure the boot order for your Surface device")

*Figure7. Configurer l’ordre de démarrage de votre appareil Surface* 

Vous pouvez également activer et désactiver la prise en charge d’IPv6 pour PXE par le biais de l’option **Activer IPv6 pour le démarrage du réseau PXE**, par exemple lorsque vous effectuez un déploiement Windows à l’aide de PXE et que le serveur PXE est uniquement configuré pour IPv4.  

## Menu UEFI: gestion
La page de gestion vous permet de gérer l’utilisation de la gestion de la fonction TouchWare de zéro et d’autres fonctionnalités sur les appareils éligibles, y compris surface Pro 7, surface Pro X et surface Laptop 3.  

![Vous pouvez gérer l’accès à la gestion de la fonction TouchWare de zéro et aux autres fonctionnalités ](images/manage-surface-uefi-fig7a.png "Manage access to Zero Touch UEFI Management and other features")
 *figure 8. Gestion de l’accès à la gestion de la fonction TouchWare de zéro et aux autres fonctionnalités* 


La gestion de la fonction TouchWare de Zero vous permet de gérer les paramètres UEFI à distance à l’aide d’un profil d’appareil dans Intune appelé interface de configuration du microprogramme de périphériques (DFCI). Si vous ne configurez pas ce paramètre, la possibilité de gérer les appareils éligibles avec DFCI est définie sur **Ready**. Pour empêcher DFCI, sélectionnez **refuser**. 

> [!NOTE]
> La page des paramètres de gestion UEFI et l’utilisation de DFCI est uniquement disponible dans surface Pro 7, surface Pro X et surface Laptop 3.  

Pour plus d’informations, reportez-vous à la rubrique [gestion Intune des paramètres de surface UEFI](surface-manage-dfci-guide.md).

## Menu UEFI: quitter 

Utilisez le bouton **redémarrer maintenant** sur la page de **sortie** pour quitter les paramètres UEFI, comme illustré dans la figure 9. 

![Quitter les paramètres UEFI Surface et redémarrer l’appareil](images/manage-surface-uefi-fig7.png "Exit Surface UEFI and restart the device")

*Figure9. Cliquer sur Redémarrer maintenant pour fermer les paramètres UEFI Surface et redémarrer l’appareil*

## Écrans de démarrage UEFI Surface

Lors d’une mise à jour du microprogramme de l’appareil Surface, que ce soit à l’aide de WindowsUpdate ou par une installation manuelle, les modifications ne prennent pas immédiatement effet sur l’appareil, mais plutôt lors du cycle de redémarrage suivant. Vous trouverez d’autres informations sur le processus de mise à jour du microprogramme Surface dans [Gérer les mises à jour du microprogramme et des pilotes Surface](https://docs.microsoft.com/surface/manage-surface-pro-3-firmware-updates). La progression de la mise à jour du microprogramme s’affiche sur un écran avec des barres de progression de différentes couleurs indiquant le microprogramme de chaque composant. La barre de progression de chaque composant est affichée dans les figures 9 à 18.

![Mise à jour du microprogramme UEFI Surface avec barre de progression bleue](images/manage-surface-uefi-fig8.png "Surface UEFI firmware update with blue progress bar")

*Figure10. La mise à jour du microprogramme UEFI Surface affiche une barre de progression bleue*

![Microprogramme du contrôleur système embarqué avec barre de progression verte](images/manage-surface-uefi-fig9.png "System Embedded Controller firmware with green progress bar")

*Figure11. La mise à jour du microprogramme du contrôleur système embarqué affiche une barre de progression verte*

![Mise à jour du microprogramme du contrôleur SAM avec barre de progression orange](images/manage-surface-uefi-fig10.png "SAM Controller firmware update with orange progress bar")

*Figure12. La mise à jour du microprogramme du contrôleur SAM affiche une barre de progression orange*

![Microprogramme du moteur de gestion Intel avec barre de progression rouge](images/manage-surface-uefi-fig11.png "Intel Management Engine firmware with red progress bar")

*Figure13. La mise à jour du microprogramme du moteur de gestion Intel affiche une barre de progression rouge*

![Microprogramme du clavier tactile de Surface avec barre de progression grise](images/manage-surface-uefi-fig12.png "Surface touch firmware with gray progress bar")

*Figure14. La mise à jour du microprogramme du clavier tactile de Surface affiche une barre de progression grise*

![Microprogramme de surface pour microprogramme avec une barre de progression verte claire](images/manage-surface-uefi-fig13.png "Surface touch firmware with light green progress bar")

*Figure15. La mise à jour du microprogramme surface-en-voyant affiche une barre de progression verte*

![Microprogramme ISH surface avec barre de progression rose](images/manage-surface-uefi-fig14.png "Surface ISH firmware with pink progress bar")

*Figure 16 la mise à jour de surface ISH microprogramme affiche une barre de progression rose clair*

![Microprogramme pavé tactile surface avec une barre de progression grise](images/manage-surface-uefi-fig15.png "Surface Trackpad firmware with gray progress bar")

*Figure17. La mise à jour de surface pavé tactile microprogramme affiche une barre de progression rose*

![Microprogramme TCON surface avec une barre de progression gris clair](images/manage-surface-uefi-fig16.png "Surface TCON firmware with light gray progress bar")

*Figure18. La mise à jour de surface TCON microprogramme affiche une barre de progression gris clair*


![Microprogramme GPC de surface avec barre de progression pourpre clair](images/manage-surface-uefi-fig17.png "Surface TPM firmware with purple progress bar")

*Figure19. La mise à jour du microprogramme de surface GPC affiche une barre de progression pourpre*


>[!NOTE]
>Un message d’avertissement supplémentaire indiquant le démarrage sécurisé est désactivé s’affiche, comme illustré dans la figure 19.

![Écran de démarrage Surface indiquant que le démarrage sécurisé a été désactivé.](images/manage-surface-uefi-fig18.png "Surface boot screen that indicates Secure Boot has been disabled")

*Figure20. Écran de démarrage Surface indiquant que le démarrage sécurisé a été désactivé dans les paramètres UEFI Surface*

## Rubriques associées

- [Gestion Intune des paramètres UEFI Surface](surface-manage-dfci-guide.md)

-  [Mode de gestion SurfaceEnterprise](surface-enterprise-management-mode.md)
