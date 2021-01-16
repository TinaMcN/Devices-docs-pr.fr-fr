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
ms.reviewer: hachidan
manager: laurawi
ms.date: 01/15/2021
ms.openlocfilehash: d8d47db3bd6f69783670b285a797337373e02d72
ms.sourcegitcommit: 1053479c191fd10651d31a466fad1769fb0cd28b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/16/2021
ms.locfileid: "11271428"
---
# Gérer les paramètres UEFI Surface

Toutes les générations actuelles et futures d’appareils Surface utilisent une interface UEFI (Unified Extensible Firmware Interface) unique conçue par Microsoft spécifiquement pour ces appareils. Les paramètres UEFI Surface offrent la possibilité d’activer ou de désactiver les appareils et composants intégrés, de protéger les paramètres UEFI contre les changements et d’ajuster les paramètres de démarrage de l’appareil Surface. 

## Produits pris en charge

La gestion UEFI est prise en charge sur les questions suivantes : 

- Surface Pro 4, Surface Pro (5e génération), Surface Pro 6, Surface Pro 7, Surface Pro 7+, Surface Pro X
- Surface Laptop (1re génération), Surface Laptop 2, Surface Laptop 3, Surface Laptop Go
- Surface Studio (1re génération), Surface Studio 2
- Surface Book, Surface Book 2, Surface Book 3
- Surface Go, Surface Go 2

## Prise en charge de la gestion basée sur le cloud

Avec les profils DFCI (Device Firmware Configuration Interface) intégrés à Microsoft Intune (désormais disponibles en prévisualisation publique), la gestion UEFI Surface étend la pile de gestion moderne jusqu’au niveau matériel UEFI. DFCI prend en charge l’approvisionnement sans contact, élimine les mots de passe BIOS, contrôle les paramètres de sécurité, y compris les options de démarrage et les périphériques intégrés, et constitue la base des scénarios de sécurité avancés à l’avenir. DFCI est actuellement disponible pour Surface Pro 7+, Surface Laptop Go, Surface Book 3, Surface Laptop 3, Surface Pro 7 et Surface Pro X.  Pour plus d’informations, reportez-vous à [La gestion Intune des paramètres UEFI Surface.](surface-manage-dfci-guide.md)

## Menu UEFI Open Surface

Pour ajuster les paramètres UEFI au démarrage du système :

1. Fermez votre Surface et patientez environ 10 secondes pour vous assurer qu’elle est éteinte.
2. Appuyez longuement **sur le bouton** Monter en volume et, en même temps, appuyez sur le bouton **d’alimentation et relâchez-le.**
3. À mesure que le logo Microsoft ou Surface apparaît sur votre écran, maintenez le bouton **Volume-up** enfoncé jusqu’à ce que l’écran UEFI s’affiche.

## Page d’informations du PC UEFI

La page d’informations du PC contient des informations détaillées sur votre appareil Surface : 

- **Modèle** : le modèle de votre appareil Surface sera affiché ici, tel que Surface Book 2 ou Surface Pro 7. La configuration exacte de votre appareil (notamment le processeur, la taille du disque ou la taille de la mémoire) n’apparaît pas. 
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

## Page Sécurité UEFI 

![Configurer les paramètres de sécurité UEFI Surface](images/manage-surface-uefi-fig4.png "Configure Surface UEFI security settings")

*Figure2. Configurer les paramètres de sécurité UEFI Surface*

La page Sécurité vous permet de définir un mot de passe pour protéger les paramètres UEFI. Vous devez entrer ce mot de passe lorsque vous démarrez l’appareil Surface en mode UEFI. Le mot de passe peut contenir les caractères suivants (comme illustré dans la figure 3) : 

- Lettres majuscules: A-Z 

- Lettres minuscules: a-z 

- Chiffres: 1-0 

- Caractères spéciaux : !@#$%^&*()?<>{} []-_=+|.,;:''» 

Le mot de passe doit comporter au moins 6caractères et respecte la casse. 

![Ajouter un mot de passe pour protéger les paramètres UEFI Surface](images/manage-surface-uefi-fig2.png "Add a password to protect Surface UEFI settings")

*Figure3. Ajouter un mot de passe pour protéger les paramètres UEFI Surface*

La page Sécurité vous permet également de modifier la configuration du démarrage sécurisé sur votre appareil Surface. La technologie de démarrage sécurisé empêche tout démarrage d’un code de démarrage non autorisé sur votre appareil Surface, et vous offre ainsi une protection contre les infections par programmes malveillants de type bootkit ou rootkit. Vous pouvez désactiver le démarrage sécurisé si vous souhaitez permettre à votre appareil Surface de démarrer des systèmes d’exploitation ou des médias de démarrage tiers. Vous pouvez également configurer le démarrage sécurisé pour qu’il fonctionne avec des certificats tiers, comme le montre la figure 4. Apprenez-en davantage sur le [démarrage sécurisé](https://msdn.microsoft.com/windows/hardware/commercialize/manufacture/desktop/secure-boot-overview) dans la bibliothèque TechNet.

![Configurer le démarrage sécurisé](images/manage-surface-uefi-fig3.png "Configure Secure Boot")

*Figure4. Configurer le démarrage sécurisé*

En fonction de votre appareil, vous pouvez également voir si votre TPM est activé ou désactivé. Si vous ne voyez pas le paramètre Activer **le TPM,**  ouvrez tpm.msc dans Windows pour vérifier l’état, comme le montre la figure 5. Le module TPM permet d’authentifier le chiffrement des données de votre appareil avec BitLocker. Pour en savoir plus, consultez la vue [d’ensemble de BitLocker.](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview) 

![Console TPM](images/manage-surface-uefi-fig5-a.png "TPM console")

*Figure5. Console TPM*


## Menu UEFI : Appareils 

La page Appareils vous permet d’activer ou de désactiver des appareils et composants spécifiques, notamment :

- Ports de station d’accueil et USB 

- Emplacement pour carte mémoire Secure Digital ou MicroSD 

- Caméra arrière 

- Caméra frontale 

- Caméra infrarouge (IR) 

- Wi-Fi et Bluetooth 

- Audio intégré (haut-parleurs et microphone) 

Chaque appareil est répertorié avec un bouton de curseur que vous pouvez déplacer vers la position **Activée** (activée) ou **Désactivée** (désactivée), comme le montre la figure 6. 

![Activer et désactiver des périphériques spécifiques](images/manage-surface-uefi-fig5a.png "Enable and disable specific devices")

*Figure6. Activer et désactiver des périphériques spécifiques*

## Menu UEFI : configuration du démarrage 

La page Configuration du démarrage vous permet de modifier l’ordre de vos périphériques de démarrage, ainsi que d’activer ou de désactiver le démarrage des appareils suivants : 

- Gestionnaire de démarrage Windows 

- Stockage USB 

- Réseau PXE (Preboot Execution Environment) 

- Stockage interne 

Vous pouvez démarrer immédiatement l’appareil à partir d’un périphérique spécifique, ou effectuer un mouvement de balayage vers la gauche sur l’entrée de ce périphérique dans la liste en utilisant l’écran tactile. Vous pouvez également démarrer immédiatement à partir d’un périphérique USB ou d’un adaptateur Ethernet USB lorsque l’appareil Surface est éteint en appuyant simultanément sur le bouton **Baisser le volume** et sur le bouton **Marche/Arrêt**. 

Pour que l’ordre de démarrage spécifié **** prenne effet, vous devez définir l’option Activer la séquence de démarrage secondaire sur **Activé,** comme illustré dans la figure 7. 

![Configurer l’ordre de démarrage de votre appareil Surface](images/manage-surface-uefi-fig6.png "Configure the boot order for your Surface device")

*Figure7. Configurer l’ordre de démarrage de votre appareil Surface* 

Vous pouvez également activer et désactiver la prise en charge d’IPv6 pour PXE par le biais de l’option **Activer IPv6 pour le démarrage du réseau PXE**, par exemple lorsque vous effectuez un déploiement Windows à l’aide de PXE et que le serveur PXE est uniquement configuré pour IPv4.  

## Menu UEFI : Gestion
La page Gestion vous permet de gérer l’utilisation de la gestion UEFI Zero Touch et d’autres fonctionnalités sur les appareils éligibles, notamment Surface Pro 7, Surface Pro X et Surface Laptop 3.  

![Gérer l’accès à la gestion UEFI Zero Touch et à d’autres fonctionnalités ](images/manage-surface-uefi-fig7a.png "Manage access to Zero Touch UEFI Management and other features")
 *figure 8. Gérer l’accès à la gestion UEFI Zero Touch et à d’autres fonctionnalités* 


La gestion UEFI Zero Touch vous permet de gérer à distance les paramètres UEFI à l’aide d’un profil d’appareil dans Intune appelé DFCI (Device Firmware Configuration Interface). Si vous ne configurez pas ce paramètre, la possibilité de gérer les appareils éligibles avec DFCI est définie sur **Prêt**. Pour empêcher DFCI, sélectionnez **Refuser.** 

> [!NOTE]
> La page des paramètres de gestion UEFI et l’utilisation de DFCI sont actuellement disponibles pour Surface Pro 7+, Surface Laptop Go, Surface Book 3, Surface Laptop 3, Surface Pro 7 et Surface Pro X. Pour en savoir plus, consultez [La gestion Intune des paramètres UEFI Surface.](surface-manage-dfci-guide.md)

## Menu UEFI : Quitter 

Utilisez le **bouton Redémarrer maintenant** dans la page **Quitter** pour quitter les paramètres UEFI, comme illustré dans la figure 9. 

![Quitter les paramètres UEFI Surface et redémarrer l’appareil](images/manage-surface-uefi-fig7.png "Exit Surface UEFI and restart the device")

*Figure9. Cliquer sur Redémarrer maintenant pour fermer les paramètres UEFI Surface et redémarrer l’appareil*

## Écrans de démarrage UEFI Surface

Lors d’une mise à jour du microprogramme de l’appareil Surface, que ce soit à l’aide de WindowsUpdate ou par une installation manuelle, les modifications ne prennent pas immédiatement effet sur l’appareil, mais plutôt lors du cycle de redémarrage suivant. Vous trouverez d’autres informations sur le processus de mise à jour du microprogramme Surface dans [Gérer les mises à jour du microprogramme et des pilotes Surface](https://docs.microsoft.com/surface/manage-surface-pro-3-firmware-updates). La progression de la mise à jour du microprogramme s’affiche sur un écran avec des barres de progression de différentes couleurs indiquant le microprogramme de chaque composant. La barre de progression de chaque composant est indiquée dans les figures 9 à 18.

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

![Microprogramme SURFACE FIRMWARE avec barre de progression vert clair](images/manage-surface-uefi-fig13.png "Surface touch firmware with light green progress bar")

*Figure15. La mise à jour du microprogramme SURFACE FIRMWARE affiche une barre de progression vert clair*

![Microprogramme ISH Surface avec barre de progression rose](images/manage-surface-uefi-fig14.png "Surface ISH firmware with pink progress bar")

*Figure 16 La mise à jour du microprogramme ish surface affiche une barre de progression rose clair*

![Microprogramme Surface Trackpad avec barre de progression grise](images/manage-surface-uefi-fig15.png "Surface Trackpad firmware with gray progress bar")

*Figure17. La mise à jour du microprogramme du Surface Trackpad affiche une barre de progression rose*

![Microprogramme TCON Surface avec barre de progression gris clair](images/manage-surface-uefi-fig16.png "Surface TCON firmware with light gray progress bar")

*Figure18. La mise à jour du microprogramme TCON Surface affiche une barre de progression gris clair*


![Microprogramme du TPM Surface avec barre de progression violet clair](images/manage-surface-uefi-fig17.png "Surface TPM firmware with purple progress bar")

*Figure19. La mise à jour du microprogramme du TPM Surface affiche une barre de progression violet*


>[!NOTE]
>Un message d’avertissement supplémentaire qui indique que le démarrage sécurisé est désactivé s’affiche, comme le montre la figure 19.

![Écran de démarrage Surface indiquant que le démarrage sécurisé a été désactivé.](images/manage-surface-uefi-fig18.png "Surface boot screen that indicates Secure Boot has been disabled")

*Figure20. Écran de démarrage Surface indiquant que le démarrage sécurisé a été désactivé dans les paramètres UEFI Surface*

## Rubriques associées

- [Gestion Intune des paramètres de surface UEFI](surface-manage-dfci-guide.md)

-  [Mode de gestion SurfaceEnterprise](surface-enterprise-management-mode.md)
