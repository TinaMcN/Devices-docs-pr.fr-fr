---
title: Migrer vers Windows 10 Professionnel ou Entreprise sur Surface Hub 2
description: Cet article explique comment migrer de Windows 10 Team sur Surface Hub 2 vers Windows 10 Professionnel ou Windows 10 Entreprise.
keywords: Surface Hub Desktop, Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 12/14/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 9878e64e414f4fe9ec3abfbd49adf233edc1da1d
ms.sourcegitcommit: 53d1eac8840fafbcd155798fce0d8c843f48dca3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/09/2021
ms.locfileid: "11255486"
---
# Migrer vers Windows 10 Professionnel ou Entreprise sur Surface Hub 2

- [Historique des versions de l’article](#version-history)

Surface Hub 2S est préinstallé avec Windows 10 Team. Cette édition personnalisée de Windows 10 est conçue pour faciliter la collaboration dans les environnements de salle de réunion. Vous avez désormais la possibilité d’utiliser Windows 10 Professionnel ou Entreprise pour utiliser surface Hub 2S comme n’importe quel autre PC. 

> [!IMPORTANT]
>Contrairement à une mise à niveau ou une migration classique, ce processus nécessite que vous suiviez une procédure normative, comme décrit dans cet article. Examinez les [composants solution et](#solution-components) le flux de travail de migration et [d’installation](#migration-and-installation-workflow-summary) avant de continuer.


> [!NOTE]
> Lorsque vous installez Windows 10 Professionnel ou Entreprise, vous avez besoin d’une nouvelle licence distincte de votre licence Windows 10 Team existante. 


Démarrez la migration à partir de Windows 10 Team à l’aide d’un PC distinct et de l’outil *téléchargeable Surface UEFI Configurator*. Utilisez l’outil pour créer un package qui contient un nouveau paramètre UEFI que vous appliquez au Surface Hub 2S.  

Le configurateur UEFI Surface fonctionne comme une interface dans le mode SEMM (Surface Enterprise Management Mode). Il est conçu pour faciliter la gestion centralisée des paramètres de microprogramme sur les appareils Surface dans un environnement d’entreprise. Pour plus d’informations, voir la <a href="https://docs.microsoft.com/surface/surface-enterprise-management-mode" target="_blank"> documentation microsoft </a> SEMM.
 

## Composants de solution

- Appareil Surface Hub 2S exécutant le système d’exploitation Windows 10 Team
- Appareil distinct exécutant Windows 10
- Outil de configuration UEFI Surface pour créer le package SEMM
- Image du système d’exploitation Windows 10 Professionnel ou Entreprise, version 1903 ou ultérieure
- Deux lecteurs USB avec 16 Go de stockage au format FAT32
- Les pilotes et le microprogramme pour Windows 10 Professionnel et le système d’exploitation d’entreprise sur le Microsoft Windows Installer Surface Hub 2 (MSI)
- Connexion Internet
- Solution d’imagerie (facultative)

 
## Résumé du flux de travail de migration et d’installation

| Étape  | Action                                                                                                 | Résumé                                                                                                                                                                                                                                                                                                                                                                                                  |
| - | ------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1 | [Vérifiez que la version UEFI sur Surface Hub 2S répond aux exigences minimales.](#verify-uefi-version-on-surface-hub-2s-meets-minimum-requirements)                                  | Assurez-vous que la version UEFI est 694.2938.768.0 ou ultérieure.                                                                                                                                                                                                                                                                                                                                                      |
| 2 | [Téléchargez les pilotes et microprogrammes surface UEFI Configurator et Surface Hub 2.](#download-surface-uefi-configurator-and-surface-hub-2-drivers-and-firmware)                             | Dans la page <a href="https://www.microsoft.com/download/details.aspx?id=46703" target="_blank"> **Outils Surface pour l’informatique,** </a> sélectionnez **Télécharger.** Ensuite, sélectionnez et téléchargez **le configurateur UEFI Surface. Fichier MSI et** installation sur un PC distinct. Téléchargez les pilotes et le microprogramme pour Windows 10 Professionnel et le système d’exploitation d’entreprise sur le <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> fichier MSI Surface Hub 2.</a> Enregistrez-le pour l’utiliser à l’étape 5. |
| 3 | [Préparer le certificat SEMM.](#prepare-the-semm-certificate)                                                                          | Préparez le certificat requis pour exécuter le configurateur UEFI Surface. Vous pouvez également utiliser votre certificat actuel.                                                                                                                                                                                                                                                                                                      |
| 4 | [Créez un package SEMM.](#create-a-semm-package)                                                                               | Démarrez surface UEFI Configurator pour créer un package SEMM sur un lecteur USB, qui contiendra les fichiers de configuration que vous devez appliquer sur Surface Hub 2S. Copiez ces fichiers de package SEMM dans un dossier de votre PC.                                                                                                                                                                                          |
| 5 | [Préparez le lecteur flash USB qui contient l’image Windows 10, le package SEMM, ainsi que les pilotes et microprogrammes pour Windows 10 Professionnel et Enterprise OS sur Surface Hub 2.](#prepare-a-usb-flash-drive-that-contains-a-windows-10-image-semm-package-and-surface-hub-2-drivers-and-firmware) | Créez un lecteur USB unique qui contient une image Windows 10. Dans cet exemple, le lecteur est nommé *BOOTME*. Ajoutez vos pilotes et microprogrammes pour Windows 10 Professionnel et enterprise OS sur surface Hub 2 (étape 2) et fichiers de package SEMM (étape 4) au lecteur *BOOTME.*                                                                                                                                                                                                  |
| 6 | [Mettez à jour l’UEFI sur Surface Hub 2S pour activer la migration du système d’exploitation.](#update-uefi-on-surface-hub-2s-to-enable-os-migration)                                              | Utilisez le *lecteur BOOTME* pour démarrer Surface Hub 2S dans le menu UEFI et installer le package SEMM.|
| 7 | [Installez Windows 10 Professionnel ou Entreprise version 1903 ou ultérieure.](#install-windows-10-pro-or-enterprise)                                        | Utilisez le *lecteur BOOTME* pour installer Windows 10 Professionnel ou Entreprise version 1903 ou ultérieure.                                                                                                                                                                                                                                                                                 |
| 8 | [Installez les pilotes et le microprogramme de Windows 10 Professionnel et du système d’exploitation d’entreprise sur Surface Hub 2.](#install-surface-hub-2-drivers-and-firmware)                                        | Pour vous assurer que votre appareil dispose de toutes les dernières mises à jour et pilotes, installez les pilotes et le microprogramme de Windows 10 Professionnel et du système d’exploitation d’entreprise sur le fichier <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> MSI Surface Hub 2.</a>                                                                                                                                                                                                                                                                                  |
| 9 | [Configurez entièrement Surface Hub 2S en tant qu’appareil de productivité personnel.](#configure-recommended-settings)                                        |  Activez les applications et paramètres recommandés pour optimiser le Surface Hub 2S en tant qu’appareil de productivité personnel.                                                                                                                                                                                                                                                                    |

### Vérifier que la version UEFI sur Surface Hub 2S répond aux exigences minimales

Avant de migrer le Surface Hub de Windows 10 Team vers Windows 10 Desktop, vous avez besoin d’une version UEFI d’au moins *694.2938.768.0.*
 
**Pour vérifier la version UEFI sur votre système :**

1. Sur la page d’accueil du Surface Hub 2S, sélectionnez **Démarrer,** puis ouvrez l’application Surface (**Toutes les applications**  >  **Surface).**

2. Sélectionnez **Votre Surface** pour afficher des informations sur surface hub, y compris la version UEFI actuelle sur l’appareil. 
   - Si la version UEFI est *694.2938.768.0* ou ultérieure, comme l’illustre l’image suivante, vous pouvez créer le package SEMM pour activer la migration du système d’exploitation.

       ![Capture d’écran montrant la page Votre surface dans l’application Surface.](images/shm-fig1.png)
 
   - Si la version UEFI est antérieure à la version 694.2938.768.0, vous devez obtenir une version actuelle en installant l’image BMR (Update Bare Metal Recovery) de Windows 10 Team 2020 ou à l’aide de Windows Update.
   
**Pour mettre à jour l’UEFI via Windows Update :**

1. Sur votre Surface Hub 2S, connectez-vous en tant **qu’administrateur.** 

    >[!Note]
    > Si vous ne connaissez pas votre nom d’utilisateur ou votre mot de passe d’administrateur, vous devez réinitialiser l’appareil. Pour plus d’informations, voir <a href="https://docs.microsoft.com/surface-hub/surface-hub-2s-recover-reset" target="_blank"> Réinitialiser et récupérer pour Surface Hub 2S.</a>

1. Go to **All apps**  >  **Settings**  >  **Update and Security**Windows  >  **Update,** and then install all updates. 

1. Redémarrez l’appareil. 

1. Vérifiez la version UEFI à l’aide de l’application Surface.

1. À ce stade, si la version UEFI n’est pas encore la version 694.2938.768.0 ou ultérieure, vous pouvez répéter les étapes ci-dessus ou vous pouvez obtenir la dernière UEFI en installant l’image BMR (Update Bare Metal Recovery) de Windows 10 Team 2020.

**Pour mettre à jour l’UEFI via l’image BMR (Bare Metal Recovery) :**

1.  Go to the [Surface recovery site](https://support.microsoft.com/surfacerecoveryimage) and select Surface Hub **2S**.

3.  Entrez votre numéro de série Hub (situé sur le côté arrière du Hub en face de la connexion d’alimentation).

4.  Suivez les instructions pour télécharger l’image sur un lecteur USB mis en forme via l’installation de la mise à jour de Windows 10 Team 2020.

5.  Une fois que la mise à jour est terminée et que l’appareil entre dans la configuration OOBE pour la première fois, vous n’avez pas besoin d’effectuer la mise à jour OOBE. La version UEFI est mise à jour. À la place, allumez l’appareil en maintenant le bouton d’alimentation enfoncé jusqu’à ce que l’écran soit éteint. 

### Télécharger le microprogramme et les pilotes UEFI Configurator Surface et Surface Hub 2

Sur un PC distinct :

1. Dans la <a href="https://www.microsoft.com/download/details.aspx?id=46703" target="_blank"> page Outils Surface pour l’informatique, </a> sélectionnez **Télécharger.**

1. Sélectionnez et téléchargez le fichier MSI du configurateur UEFI Surface et installez-le sur un PC distinct. L’outil Configurateur UEFI Surface ne peut pas être exécuté sur un Surface Hub 2S pendant l’installation de l’édition Windows 10 Team.

1. Téléchargez le fichier MSI Windows Installer des pilotes et du <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> microprogramme Surface Hub </a> 2. Vous utiliserez ce fichier lors de l’installation du nouveau système d’exploitation.

### Préparer le certificat SEMM

Si vous n’avez pas encore utilisé le configurateur UEFI Surface, vous devez préparer un certificat. Ce certificat garantit qu’une fois qu’un appareil est inscrit au seMM, vous pouvez modifier les paramètres UEFI uniquement à l’aide de packages créés avec le certificat approuvé. 

La façon dont vous obtenez un certificat dépend de la taille ou de la complexité de votre organisation :

- Les organisations d’entreprise conservent généralement leur propre infrastructure pour générer des certificats conformément aux pratiques de sécurité standard.

- Les entreprises de taille moyenne et d’autres peuvent choisir d’obtenir des certificats auprès de fournisseurs partenaires. Cette option est recommandée pour les organisations qui ne sont pas suffisamment spécialisées en informatique ou une équipe dédiée à la sécurité informatique.

- Vous pouvez également générer un certificat auto-signé à l’aide d’un script PowerShell. Pour plus d’informations, consultez les conditions requises pour les certificats du mode Gestion <a href="https://docs.microsoft.com/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements" target="_blank"> d’entreprise </a> Surface. Vous pouvez également utiliser PowerShell pour créer votre propre certificat. Pour plus d’informations, voir <a href="https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate" target="_blank"> la documentation New-SelfSignedCertificate. </a>

Le package SEMM créé par le configurateur UEFI Surface doit être sécurisé avec un certificat. Le certificat vérifie la signature des fichiers de configuration avant que les paramètres UEFI ne soient appliqués. Pour plus d’informations, voir la <a href="https://docs.microsoft.com/surface/surface-enterprise-management-mode" target="_blank"> documentation </a> SEMM.
 
 
### Créer un package SEMM

1. Sur un PC distinct, installez l’outil Configurateur UEFI Surface que vous avez téléchargé précédemment. 

2. Ouvrez le configurateur UEFI Surface, puis sélectionnez **Démarrer.**

   ![Ouvrez le configurateur UEFI Surface.](images/shm-fig2.png)
   
3. Sélectionnez **Appareils Surface,** puis sélectionnez **Suivant**.

   ![Sélectionnez Appareils Surface.](images/shm-fig3.png)
  
4. Sélectionnez **le package de configuration.**

   ![Sélectionnez Package de configuration.](images/shm-fig4.png)
  
5. Sélectionnez **Protection des certificats.**

   ![Sélectionnez Protection des certificats.](images/shm-fig5.png)

   Vous êtes invité à ajouter votre fichier .pfx de certificat.

   ![Ajoutez votre certificat.](images/shm-fig6.png)
   
7. Entrez votre mot de passe de certificat, puis sélectionnez **OK.**

   ![Entrez votre mot de passe de certificat et sélectionnez OK.](images/shm-fig7.png)

8. Sélectionnez **Protection par mot de** passe pour ajouter un mot de passe à l’UEFI Surface. Vous aurez besoin de ce mot de passe chaque fois que vous démarrerez sur UEFI. Nous *vous recommandons vivement* de définir un mot de passe UEFI que vous utiliserez sur Surface Hub 2S.

   ![Sélectionnez Protection par mot de passe.](images/shm-fig8.png)
   
9. Définissez un mot de passe UEFI, puis sélectionnez **OK.**

   > [!IMPORTANT]
   > Enregistrez le mot de passe dans un emplacement sécurisé accessible aux administrateurs informatiques qui gèrent le Surface Hub. Si le mot de passe est perdu, il ne peut pas être récupéré. 

   ![Entrez votre mot de passe UEFI.](images/shm-fig9.png)

10. Sélectionnez **Surface Hub 2S,** puis sélectionnez **Suivant.**

    ![Sélectionnez Surface Hub 2S.](images/shm-fig10.png)
   
11. Sélectionnez **Suivant**.

    ![Sélectionnez Suivant.](images/shm-fig10a.png)

12. Pour autoriser l’installation de Windows 10 Professionnel ou Entreprise, activez **EnableOsMigration,** puis sélectionnez **Suivant**.

    ![Sélectionnez Activer la migration O S.](images/shm-fig11.png)
    
    ![Définissez Activer la migration du système d’exploitation.](images/shm-fig12.png)

### Gestion de l’inscription SEMM

L’inscription d’appareils dans SEMM affecte la façon dont vous pouvez gérer l’appareil à l’avenir. Par exemple, après avoir appliqué un package SEMM, dans le menu UEFI de l’appareil, tous les paramètres UEFI ne sont pas disponibles (verrouillés). Les valeurs par défaut pour d’autres paramètres tels que **IPv6 pour** le démarrage PXE sont également indisponibles. 

Pour modifier les paramètres UEFI après avoir terminé la migration, appliquez un autre package SEMM ou désinscrimez l’appareil à partir de SEMM. Si vous appliquez un autre package SEMM pour modifier les paramètres UEFI, vous devez utiliser le certificat d’origine lorsque vous créez le nouveau package SEMM. Utilisez l’outil Configurateur UEFI et laissez **EnableOSMigration** éteint (et non activé, comme indiqué dans les étapes de migration d’origine).

#### Collaborer avec des partenaires

Si votre entreprise sous-traite la migration vers Windows 10 Professionnel ou Entreprise sur Surface Hub 2, vous souhaitez peut-être que le partenaire vous transfère le certificat SEMM, le package SEMM et le mot de passe UEFI.  Par ailleurs, après avoir migré le Hub, vous pouvez immédiatement le désinscrire de SEMM, ce qui permet l’administration locale de l’UEFI et le transfert de l’appareil à une autre partie. Néanmoins, il est toujours vivement recommandé d’utiliser un mot de passe UEFI, qui peut être configuré après la migration. Pour plus d’informations, voir [Gérer les paramètres UEFI Surface.](https://docs.microsoft.com/surface/manage-surface-uefi-settings) 

#### Retour à Windows 10 Team

Si, après la migration, vous choisissez de restaurer votre appareil vers Windows 10 [Team,](#roll-back-to-windows-10-team)comme décrit ci-dessous, il est recommandé de désinscrire d’abord le Hub à partir de SEMM. Pour plus d’informations, voir [Désinscrire des appareils Surface à partir de SEMM.](https://docs.microsoft.com/surface/unenroll-surface-devices-from-semm)


#### Enregistrer le package SEMM sur un lecteur USB

1. Connectez un lecteur USB à votre PC. 

1. Choisissez **Hub 2S,** puis sélectionnez **Suivant.**

   ![Sélectionner USB](images/shm-fig13.png)

   > [!WARNING]
   > Toutes les données existantes sur le lecteur USB sont effacées lors de la construction du package SEMM. Avant de créer le package SEMM, supprimez tous les fichiers du lecteur USB que vous souhaitez enregistrer.
   
2. Sélectionnez **Build**.

   ![Sélectionnez Build.](images/shm-fig14.png)

3. Capturez une capture d’écran de cette page, puis sélectionnez **Fin.** Votre package SEMM est maintenant prêt. Il contient le package SEMM *DfciUpdate.dfi* et un fichier texte qui inclut l’empreinte SEMM (les deux derniers caractères de l’empreinte numérique du certificat).

   ![Sélectionnez Fin.](images/shm-fig15.png)
   
4. Enregistrez les deux derniers caractères de l’empreinte numérique du certificat. Vous aurez besoin de ces caractères pour activer SEMM lorsque vous appliquerez le package sur Surface Hub 2S.

### Préparer un disque mémoire USB qui contient une image Windows 10, un package SEMM et des pilotes et microprogrammes Surface Hub 2

Vous pouvez installer une image Windows 10 Professionnel ou Entreprise (version 1903 ou ultérieure) à l’aide de l’une des options suivantes :

- Votre solution d’imagerie actuelle.

- <a href="https://docs.microsoft.com/surface/microsoft-surface-deployment-accelerator" target="_blank"> Surface Deployment Accelerator </a> . Utilisez cet outil pour créer une image Windows 10 amorçable. L’image peut inclure toutes les mises à jour Windows 10 actuelles, Office, les autres applications que vous choisissez, ainsi que les pilotes et microprogrammes requis. 

- Lecteur flash USB qui contient une image Windows 10 Professionnel ou Entreprise. Ensuite, installez <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> pilotes et microprogramme pour Windows 10 Professionnel et le système d’exploitation d’entreprise sur Surface Hub 2. </a>
 
La procédure suivante décrit comment créer un disque mémoire USB à partir d’un support d’installation, puis ajouter les fichiers de package SEMM et les pilotes et microprogrammes pour Windows 10 Professionnel et le système d’exploitation Entreprise sur le fichier MSI Surface Hub 2. Si vous utilisez d’autres méthodes de déploiement, go to the [Update UEFI on Surface Hub 2S to enable OS migration](#update-uefi-on-surface-hub-2s-to-enable-os-migration) section in this article.

> [!NOTE]
> Une fois l’installation terminé, vous aurez besoin d’une licence valide pour Windows 10 Professionnel ou Windows 10 Entreprise distincte de votre licence Windows 10 Team existante.

1. Pour créer une installation de Windows 10 Professionnel, sur la page Télécharger Windows 10, suivez les instructions pour télécharger <a href="https://www.microsoft.com/software-download/windows10" target="_blank"> l’outil de création de </a> supports. Pour télécharger Windows 10 Entreprise, allez dans le Centre de gestion des licences <a href="https://www.microsoft.com/licensing/servicecenter/default.aspx" target="_blank"> en volume </a> Microsoft.

1. Insérez un nouveau lecteur de stockage USB. 

1. Ouvrez l’outil de création de médias, **sélectionnez Créer un**support d’installation, puis sélectionnez **Suivant**.

   ![Créez un support d’installation.](images/shm-fig16.png)
   
1. Sélectionnez une langue, puis **choisissez Windows 10** et **64 bits (x64).** Ensuite, **sélectionnez Suivant.**

   ![Sélectionnez la langue, puis choisissez Windows 10 et 64 bits. Ensuite, sélectionnez Suivant.](images/shm-fig17.png)
   
1. Sélectionnez **le lecteur flash USB,** puis sélectionnez **Suivant.**

   ![Sélectionnez lecteur flash U S B et sélectionnez Suivant.](images/shm-fig18.png)
   
1. Une fois le téléchargement terminé, sélectionnez **Terminer.**

   ![Sélectionnez Terminer.](images/shm-fig19.png)
   
1. Copiez les fichiers de package SEMM, ainsi que les pilotes et microprogrammes de Windows 10 Professionnel et du système d’exploitation d’entreprise sur Surface Hub 2 (fichier MSI) à la racine du disque mémoire USB *(BOOTME)* qui contient votre image Windows 10. Le lecteur USB BOOTME contient :

    - Votre image de démarrage Windows 10.
    
    - Fichiers de package SEMM (copiés à la racine du lecteur USB).
    
      - *DfciUpdate.dfi*.
      - Fichier texte qui inclut l’empreinte SEMM. (Dans cet exemple, le fichier est *SurfaceUEFI_2020Aug25_1058.txt*.) L’horodateur de date généré automatiquement correspond à la date à laquelle vous avez créé le fichier à l’aide du configurateur UEFI Surface.

   - Pilotes et microprogramme pour Windows 10 Professionnel et système d’exploitation d’entreprise sur Surface Hub 2 (SurfaceHub2S_Win10_18362_20.082.25682.0.msi). Copiez ce fichier à la racine du lecteur USB.

### Mettre à jour l’UEFI sur Surface Hub 2S pour activer la migration du système d’exploitation

1. Insérez votre lecteur BOOTME dans le port USB-A sur Surface Hub 2S. Pour obtenir la liste des fichiers requis, consultez la section précédente.

2. Pour démarrer dans UEFI :

   1. Désactiver (arrêter) votre Surface Hub 2S.
   1. Appuyez et **maintenez le volume +**, puis appuyez sur le bouton d’alimentation et relâchez-le.
   1. Maintenez le **volume + jusqu’à** ce que le menu UEFI apparaisse.
   
      ![Appuyez et maintenez le bouton de volume enfoncé jusqu’à ce que le menu UEFI s’affiche.](images/shm-fig20.png)
      
3. Lorsque l’appareil redémarre, entrez le mot de passe UEFI que vous avez créé précédemment, le cas échéant (vivement recommandé).

   ![Entrez le mot de passe UEFI.](images/shm-fig22.png)
   
4. Dans le menu UEFI, sélectionnez **Installation**  >  **de gestion à partir du port USB.**

   ![Sélectionnez Gestion et Installation à partir de U S B.](images/shm-fig21.png)
   
5. Sélectionnez **Redémarrer maintenant,** comme le montre l’image suivante. L’appareil redémarre. Il affiche un logo Microsoft blanc au milieu de la fenêtre, puis s’arrête.

   ![Sélectionnez Redémarrer maintenant.](images/shm-fig25.png)
   
6. Appuyez sur le bouton d’alimentation et relâchez-le. Dans la fenêtre rouge qui s’affiche, activez le mode de gestion Surface Enterprise. 

7. Entrez votre empreinte numérique de certificat à deux caractères et votre mot de passe de paramètres UEFI. Ensuite, **sélectionnez OK**.

   ![Entrez votre empreinte numérique de certificat à deux caractères et votre mot de passe de paramètres UEFI.](images/shm-fig23.png)
 
   > [!NOTE]
   > Après avoir activé SEMM sur votre appareil, le nouveau paramètre UEFI **EnableOSMigration** est appliqué. Vous ne pourrez plus accéder à Windows 10 Team. Au lieu de cela, vous devez continuer à l’étape suivante et installer Windows 10 Professionnel ou Windows 10 Entreprise. 

   L’appareil redémarre. Il affiche le logo blanc au milieu de l’écran, puis s’arrête à nouveau.

### Installer Windows 10 Professionnel ou Entreprise

1. Si votre lecteur Windows 10 Professionnel ou Entreprise amorçable ne se trouve pas déjà dans le port USB-A surface Hub 2, insérez-le maintenant. Appuyez ensuite sur le bouton d’alimentation et relâchez-le. 

    Lorsque l’appareil démarre, vous voyez le logo blanc au milieu de l’écran. Vous voyez ensuite un cercle pivotant sous le logo blanc.

3. Si l’appareil ne démarre pas automatiquement sur le lecteur USB, éteint l’appareil (débrancher le cordon d’alimentation, puis le brancher à nouveau). Après avoir de nouveau brancher le cordon d’alimentation, l’appareil doit démarrer après quelques secondes. Vous verrez ensuite le logo blanc au milieu de l’écran. 

    Si l’appareil ne s’allume pas, appuyez sur le bouton d’alimentation et relâchez-le. Immédiatement après avoir vu le logo au milieu de l’écran, appuyez et maintenez le bouton Volume enfoncé **jusqu’à** ce que le cercle pivote sous le logo blanc.
 
   ![Démarrez vers Windows 10 à partir du lecteur U S B.](images/shm-fig26.png)
   
4. Lorsque l’installation OOBE (Out-of-Box Experience) démarre, suivez les instructions pour installer Windows 10 Professionnel ou Entreprise (version 1903 ou ultérieure).

### Installer les pilotes et microprogrammes Surface Hub 2

Pour vous assurer que votre appareil dispose de toutes les dernières mises à jour et pilotes, installez les pilotes et le microprogramme de Windows 10 Professionnel et du système d’exploitation Entreprise sur <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> Surface Hub </a> 2. Après l’installation des pilotes et du microprogramme MSI, redémarrez l’appareil. Ensuite, après avoir redémarrage du Hub, conservez l’alimentation du PC pendant une heure et redémarrez l’appareil. Vous ne serez pas invité à redémarrer le deuxième redémarrage. Selon l’état de votre ordinateur avant la migration vers Windows 10 Professionnel ou Entreprise, cette deuxième étape peut être nécessaire pour s’assurer que l’ensemble du microprogramme a été mis à jour.
 
## Configurer les paramètres recommandés

Pour configurer entièrement Surface Hub 2S en tant qu’appareil de productivité personnel, voir Configurer Windows 10 Professionnel ou Entreprise <a href="surface-hub-2-post-install.md" target="_blank"> sur Surface Hub </a> 2.

> [!NOTE]
>Si les étapes décrites dans cet article ne migrent pas correctement votre appareil vers Windows 10 Professionnel ou Entreprise pour Surface Hub 2, contactez le support <a href="https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support" target="_blank"> Surface </a> Hub.

## Revenir à Windows 10 Team

Si vous souhaitez restaurer votre appareil vers Windows 10 Team, voir Réinitialiser et <a href="surface-hub-2s-recover-reset.md" target="_blank"> récupérer pour Surface Hub 2S. </a>

> [!NOTE]
> Avant de revenir à Windows 10 Team, il est recommandé de désinscrire d’abord le Hub de SEMM. Pour plus d’informations, voir [Désinscrire des appareils Surface à partir de SEMM.](https://docs.microsoft.com/surface/unenroll-surface-devices-from-semm)

## Historique des versions

Le tableau suivant récapitule les modifications apportées à cet article.

| Version | Date               | Description                                                                                           |
| ------- | ------------------ | ----------------------------------------------------------------------------------------------------- |
| v. 1.4  | 14 décembre 2020 | Fournit [](#install-surface-hub-2-drivers-and-firmware) des informations supplémentaires sur l’installation du fichier MSI pour « Pilotes et microprogramme pour Windows 10 Professionnel et Le système d’exploitation d’entreprise sur Surface Hub 2 », en vous informant qu’un second redémarrage peut être nécessaire en fonction de l’état de votre système.                                                          |
| v. 1.3  | 3 décembre 2020 | Mise à jour avec des conseils [sur la gestion de l’inscription SEMM.](#managing-semm-enrollment)                                                       |
| v. 1.2  | 29 septembre 2020 | Mises à jour diverses qui abordent les commentaires d’utilisation.                                                        |
| v. 1.1  | 15 septembre 2020 | Introduction d’une note supplémentaire qui clarifie les exigences de licence pour l’installation d’un nouveau système d’exploitation. |
| v. 1.0  | 1er septembre 2020  | Nouvel article.                                                                                           |
