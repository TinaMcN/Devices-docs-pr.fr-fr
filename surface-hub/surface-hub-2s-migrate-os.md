---
title: Migrer vers Windows 10 Professionnel ou Entreprise sur Surface Hub 2
description: Comment migrer de Windows 10 Team sur Surface Hub 2 vers Windows 10 Professionnel ou Windows 10 Entreprise.
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
ms.openlocfilehash: d7ecee2ca66640b054efc106191d12c1844b90a1
ms.sourcegitcommit: 1bc22f7343af9b1b1b8b375d540adee2af68e693
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2021
ms.locfileid: "11297637"
---
# Migrer vers Windows 10 Professionnel ou Entreprise sur Surface Hub 2

- [Historique des versions de l’article](#version-history)

Surface Hub 2S est livré avec Windows 10 Team installé. Cette édition personnalisée de Windows 10 facilite la collaboration dans les environnements de salle de réunion. Vous pouvez désormais exécuter Windows 10 Professionnel ou Entreprise pour utiliser votre Surface Hub 2S comme n’importe quel autre PC.

> [!IMPORTANT]
> Ce processus de migration nécessite que vous suiviez la procédure spécifique décrite dans cet article. Avant de continuer, lisez [composants de solution](#solution-components) et [flux de travail de migration et d’installation.](#migration-and-installation-workflow-summary)

> [!NOTE]
> Lorsque vous installez Windows 10 Professionnel ou Entreprise, vous avez besoin d’une nouvelle licence distincte de votre licence Windows 10 Team existante.

Démarrez la migration à partir de Windows 10 Team à l’aide d’un PC distinct et de l’outil de configuration *UEFI Surface téléchargeable.* L’outil crée un package qui contient un nouveau paramètre UEFI que vous appliquez au Surface Hub 2S.  

Le configurateur UEFI Surface fonctionne comme une interface dans le mode SEMM (Surface Enterprise Management Mode). Il permet une gestion centralisée des paramètres de microprogramme sur les appareils Surface dans un environnement d’entreprise. Pour plus d’informations, [voir Microsoft Surface Enterprise Management Mode](https://docs.microsoft.com/surface/surface-enterprise-management-mode).
 
## Composants de solution

- Appareil Surface Hub 2S exécutant Windows 10 Team
- Appareil distinct exécutant Windows 10
- Outil de configuration UEFI Surface pour créer le package SEMM
- Image du système d’exploitation Windows 10 Professionnel ou Entreprise, version 1903 ou ultérieure
- Deux lecteurs USB avec 16 Go de stockage au format FAT32
- Pilotes et microprogramme pour Windows 10 Professionnel et Entreprise dans un fichier Microsoft Windows Installer Surface Hub 2 (MSI)
- Connexion Internet
- Solution d’imagerie (facultative)
 
## Résumé du flux de travail de migration et d’installation

| Étape  | Action                                                                                                 | Résumé                                                                                                                                                                                                                                                                                                                                                                                                  |
| - | ------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1 | [Vérifiez la version UEFI sur le Surface Hub 2S.](#verify-the-uefi-version-on-surface-hub-2s)                                  | La version UEFI doit être la version *694.2938.768.0* ou ultérieure.                                                                                                                                                                                                                                                                                                                                                      |
| 2 | [Téléchargez le configurateur UEFI Surface et les pilotes et microprogrammes Surface Hub 2.](#download-surface-uefi-configurator-and-surface-hub-2-drivers-and-firmware)                             | Dans la page **[Des outils Surface pour l’informatique,](https://www.microsoft.com/download/details.aspx?id=46703)** </a> sélectionnez **Télécharger.** Ensuite, sélectionnez et téléchargez le fichier **MSI du configurateur UEFI Surface,** puis installez-le sur un PC distinct. Téléchargez également [les pilotes et le microprogramme pour Windows 10 Professionnel](https://www.microsoft.com/download/details.aspx?id=101974)et le système d’exploitation d’entreprise sur le fichier MSI Surface Hub 2.</a> Enregistrez ce package pour l’utiliser à l’étape 5. |
| 3 | [Préparez le certificat SEMM.](#prepare-the-semm-certificate)                                                                          | Préparez le certificat requis pour exécuter le configurateur UEFI Surface ou utilisez votre certificat actuel.                                                                                                                                                                                                                                                                                                      |
| 4 | [Créez un package SEMM.](#create-a-semm-package)                                                                               | Démarrez le configurateur UEFI Surface pour créer un package SEMM sur un lecteur USB. Ce package contient les fichiers de configuration que vous devez appliquer sur Surface Hub 2S. Copiez ces fichiers de package SEMM dans un dossier de votre PC.                                                                                                                                                                                          |
| 5 | [Chargez un disque mémoire USB avec l’image Windows 10, le package SEMM, les pilotes et le microprogramme.](#load-a-usb-flash-drive-with-a-windows-10-image-semm-package-and-surface-hub-2-drivers-and-firmware) | Créez un lecteur USB qui contient une image Windows 10. Dans cet exemple, le lecteur est nommé *BOOTME*. Ajoutez les pilotes et le microprogramme pour Windows 10 Professionnel et enterprise OS sur Surface Hub 2 (à partir de l’étape 2) et les fichiers de package SEMM (à partir de l’étape 4) au lecteur *BOOTME.*                                                                                                                                                                                                  |
| 6 | [Mettez à jour l’UEFI sur le Surface Hub 2S pour activer la migration du système d’exploitation.](#update-uefi-on-surface-hub-2s-to-enable-os-migration)                                              | Utilisez le *lecteur BOOTME* pour démarrer le Surface Hub 2S dans le menu UEFI et installer le package SEMM.|
| 7 | [Installez Windows 10 Professionnel ou Entreprise.](#install-windows-10-pro-or-enterprise)                                        | Utilisez le *lecteur BOOTME* pour installer Windows 10 Professionnel ou Entreprise version 1903 ou ultérieure.                                                                                                                                                                                                                                                                                 |
| 8 | [Installez les pilotes et le microprogramme pour Windows 10 Professionnel et Entreprise.](#install-surface-hub-2-drivers-and-firmware)                                        | Pour vous assurer que votre appareil dispose de toutes les dernières mises à jour et pilotes, installez les pilotes et le microprogramme de Windows 10 Professionnel et du système d’exploitation d’entreprise sur le fichier <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> MSI Surface Hub 2.</a>                                                                                                                                                                                                                                                                                  |
| 9 | [Configurez surface Hub 2S comme appareil de productivité personnel.](#configure-recommended-settings)                                        |  Activez les paramètres et applications recommandés pour optimiser le Surface Hub 2S en tant qu’appareil de productivité personnel.                                                                                                                                                                                                                                                                    |

### Vérifier la version UEFI sur Surface Hub 2S

Avant de migrer le Surface Hub de Windows 10 Team vers Windows 10 Desktop, vous avez besoin de la version UEFI *694.2938.768.0* ou ultérieure.
 
**Pour vérifier la version UEFI sur votre système :**

1. Sur la page d’accueil du Surface Hub 2S, sélectionnez **Démarrer,** puis ouvrez l’application Surface (**Toutes les applications**  >  **Surface).**

2. Sélectionnez **Votre Surface** pour afficher des informations sur surface hub, y compris la version UEFI actuelle sur l’appareil. 
   - Si la version UEFI est *694.2938.768.0* ou ultérieure, comme l’illustre l’image suivante, vous pouvez créer le package SEMM pour activer la migration du système d’exploitation.

       ![Screenshot shows the «Your Surface» page in the Surface app.](images/shm-fig1.png)
 
   - Si la version UEFI est antérieure à la version *694.2938.768.0,* utilisez l’une des méthodes suivantes pour obtenir une version plus récente
   
#### Mettre à jour l’UEFI via Windows Update

1. Sur votre Surface Hub 2S, connectez-vous en tant **qu’administrateur.**

    >[!Note]
    > Si vous ne connaissez pas votre nom d’utilisateur ou votre mot de passe d’administrateur, vous devez réinitialiser l’appareil. Pour plus d’informations, voir [Réinitialiser et récupérer pour Surface Hub 2S.](https://docs.microsoft.com/surface-hub/surface-hub-2s-recover-reset)

1. Go to **All apps**  >  **Settings**  >  **Update and Security**Windows  >  **Update**, and install all updates.
1. Redémarrez l’appareil.
1. Vérifiez la version UEFI à l’aide de l’application Surface. Si la version UEFI n’est pas la version *694.2938.768.0* ou ultérieure, répétez ces étapes ou utilisez la procédure suivante pour obtenir la dernière version de l’UEFI.

#### Mettre à jour l’image UEFI via une récupération complète (BMR)

1.  Go to the [Surface recovery site](https://support.microsoft.com/surfacerecoveryimage) and select Surface Hub **2S**.
3.  Entrez votre numéro de série Hub. Il se trouve à l’arrière du Hub à côté de la connexion d’alimentation.
4.  Suivez les instructions pour télécharger l’image sur un lecteur USB mis en forme en installant windows 10 Team 2020 Update.
5.  Après la mise à jour, l’appareil entre dans la configuration OOBE (Out-of-Box Experience). Vous n’avez pas besoin de terminer l’installation. La version UEFI est déjà mise à jour. À la place, allumez l’appareil en maintenant le bouton d’alimentation enfoncé jusqu’à ce que l’écran soit éteint.

### Télécharger le microprogramme et les pilotes UEFI Configurator Surface et Surface Hub 2

Sur un PC distinct, suivez les étapes suivantes :

1. Dans la <a href="https://www.microsoft.com/download/details.aspx?id=46703" target="_blank"> page Outils Surface pour l’informatique, </a> sélectionnez **Télécharger.**  
1. Sélectionnez et téléchargez le fichier MSI du configurateur UEFI Surface, puis installez-le sur un PC distinct. L’outil Configurateur UEFI Surface ne peut pas être exécuté sur un Surface Hub 2S pendant l’installation de l’édition Windows 10 Team.

1. Téléchargez le fichier MSI Windows Installer des pilotes et du [microprogramme Surface Hub 2.](https://www.microsoft.com/download/details.aspx?id=101974) Vous utiliserez ce fichier lors de l’installation du nouveau système d’exploitation.

### Préparer le certificat SEMM

Si vous n’avez jamais utilisé le configurateur UEFI Surface, vous devez préparer un certificat. Ce certificat garantit qu’une fois qu’un appareil est inscrit au seMM, vous ne pouvez modifier les paramètres UEFI qu’à l’aide de packages créés avec le certificat approuvé.

La façon dont vous obtenez un certificat dépend de la taille ou de la complexité de votre organisation :

- Les organisations d’entreprise conservent généralement leur propre infrastructure pour générer des certificats conformément aux pratiques de sécurité standard.

- Les entreprises de taille moyenne et d’autres choisissent souvent d’obtenir des certificats auprès de fournisseurs partenaires. Cette option est recommandée pour les organisations qui n’ont pas autant d’expertise informatique ou qui n’ont pas d’équipe dédiée à la sécurité informatique.

- Vous pouvez également générer un certificat auto-signé à l’aide d’un script PowerShell. Pour plus d’informations, consultez les conditions requises pour les certificats du mode Gestion [d’entreprise Surface.](https://docs.microsoft.com/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements) Vous pouvez également utiliser PowerShell pour créer votre propre certificat. Pour plus d’informations, voir la documentation [New-SelfSignedCertificate.](https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate)

Le package SEMM créé par le configurateur UEFI Surface doit être sécurisé avec un certificat. Le certificat vérifie la signature des fichiers de configuration avant que les paramètres UEFI ne soient appliqués. Pour plus d’informations, voir la documentation [SEMM.](https://docs.microsoft.com/surface/surface-enterprise-management-mode)
 
### Créer un package SEMM

1. Sur un PC distinct, installez l’outil Configurateur UEFI Surface que vous avez téléchargé précédemment.

1. Ouvrez le configurateur UEFI Surface, puis sélectionnez **Démarrer.**

   ![Écran de démarrage du configurateur UEFI Surface.](images/shm-fig2.png)
   
1. Sélectionnez **Appareils Surface,** puis sélectionnez **Suivant.**

   ![Screenshot shows the Surface Devices option selected.](images/shm-fig3.png)
  
1. Sélectionnez **le package de configuration.**

   ![Screenshot shows «Select Configuration Package» selected.](images/shm-fig4.png)
  
1. Sélectionnez **Protection des certificats.**

   ![Screenshot shows were to choose «Select Certificate Protection».](images/shm-fig5.png)

   Vous serez invité à ajouter votre fichier .pfx de certificat.

   ![Screenshot shows where to add your certificate file.](images/shm-fig6.png)
   
1. Entrez votre mot de passe de certificat, puis sélectionnez **OK.**

   ![Screenshot shows fields to enter and confirm your certificate password.](images/shm-fig7.png)

1. Sélectionnez **Protection par mot de** passe pour ajouter un mot de passe à l’UEFI Surface. Vous aurez besoin de ce mot de passe chaque fois que vous démarrerez sur l’UEFI. *Nous vous recommandons vivement de définir un mot de passe UEFI que vous utiliserez sur Surface Hub 2S.*

   ![Screenshot shows where to select Password Protection.](images/shm-fig8.png)
   
1. Définissez un mot de passe UEFI, puis sélectionnez **OK.**

   > [!IMPORTANT]
   > Enregistrez le mot de passe dans un emplacement sécurisé accessible aux administrateurs informatiques qui gèrent le Surface Hub. *Si ce mot de passe est perdu, il ne peut pas être récupéré.*

   ![Screenshot shows where you set the UEFI password.](images/shm-fig9.png)

1. Sélectionnez **Surface Hub 2S,** puis sélectionnez **Suivant.**

    ![Screenshot shows where to select Surface Hub 2S.](images/shm-fig10.png)
   
1. Sélectionnez **à nouveau** Suivant.

    ![Screenshot shows to select Next under «Choose which components».](images/shm-fig10a.png)

1. Pour autoriser l’installation de Windows 10 Professionnel ou Entreprise, activez **EnableOsMigration,** puis sélectionnez **Suivant**.

    ![Screenshot shows where to select Enable O S Migration.](images/shm-fig11.png)
    
    ![Screenshot shows where to set Enable OS Migration to on.](images/shm-fig12.png)

### Gérer l’inscription SEMM

L’inscription d’un appareil dans SEMM affecte la façon dont vous pouvez le gérer. Par exemple, après avoir appliqué un package SEMM, tous les paramètres UEFI ne sont pas disponibles (verrouillés) dans le menu UEFI de l’appareil. Les valeurs par défaut pour d’autres paramètres tels que **IPv6 pour** le démarrage PXE sont également indisponibles.

Pour modifier les paramètres UEFI après avoir terminé la migration, appliquez un autre package SEMM ou désinscrimez l’appareil à partir de SEMM. Si vous appliquez un autre package SEMM pour modifier les paramètres UEFI, vous devez utiliser le certificat d’origine lorsque vous créez le nouveau package SEMM. Utilisez l’outil configurateur UEFI et laissez **EnableOSMigration** *éteint* (et non *activé* comme dans les étapes de migration d’origine).

#### Si vous travaillez avec des partenaires

Si votre entreprise externalise la migration du Surface Hub 2 vers Windows 10 Professionnel ou Entreprise, vous souhaitez peut-être que le partenaire vous transfère le certificat SEMM, le package SEMM et le mot de passe UEFI. Ou, après avoir migré le Hub, vous pouvez immédiatement le désinscrire de SEMM. Cette étape permet l’administration locale de l’UEFI et le transfert de l’appareil à une autre partie. Toutefois, nous vous recommandons vivement d’utiliser un mot de passe UEFI, qui peut être configuré après la migration. Pour plus d’informations, voir [Gérer les paramètres UEFI Surface.](https://docs.microsoft.com/surface/manage-surface-uefi-settings) 

#### Pour revenir à Windows 10 Team

Si vous choisissez de restaurer votre appareil vers Windows 10 Team après la migration, comme décrit plus loin dans cet [article,](#to-roll-back-to-windows-10-team)nous vous recommandons d’abord de désinscrire le Hub de SEMM. Pour plus d’informations, voir [Désinscrire des appareils Surface à partir de SEMM.](https://docs.microsoft.com/surface/unenroll-surface-devices-from-semm)

#### Enregistrer le package SEMM sur un lecteur USB

1. Connectez un lecteur USB à votre PC.
1. Choisissez **Hub 2S,** puis sélectionnez **Suivant.**

   ![Screenshot shows where to select Hub 2S](images/shm-fig13.png)

   > [!WARNING]
   > Toutes les données existantes sur le lecteur USB seront effacées lors de la construction du package SEMM. Avant de créer le package SEMM, supprimez les fichiers dont vous avez besoin du lecteur USB.
   
1. Sélectionnez **Build**.

   ![Screenshot shows where to select Build.](images/shm-fig14.png)

1. Capturez une capture d’écran de cette page, puis sélectionnez **Fin.** Votre package SEMM est maintenant prêt. Il contient le package SEMM *DfciUpdate.dfi* et un fichier texte qui inclut l’empreinte NUMÉRIQUE *SEMM,* qui est les deux derniers caractères de l’empreinte numérique du certificat.

   ![Screenshot shows where to select End.](images/shm-fig15.png)
   
4. Enregistrez les deux derniers caractères de l’empreinte numérique du certificat. Vous aurez besoin de ces caractères pour activer SEMM lorsque vous appliquerez le package sur Surface Hub 2S.

### Charger un disque mémoire USB avec une image Windows 10, un package SEMM et des pilotes et microprogrammes Surface Hub 2

Vous pouvez installer une image Windows 10 Professionnel ou Entreprise (version *1903* ou ultérieure) à l’aide de l’une des options suivantes :

- Votre solution d’imagerie actuelle.

- [Surface Deployment Accelerator](https://docs.microsoft.com/surface/microsoft-surface-deployment-accelerator). Utilisez cet outil pour créer une image Windows 10 amorçable. L’image peut inclure toutes les mises à jour Windows 10 actuelles, Microsoft Office, d’autres applications, ainsi que les pilotes et microprogrammes requis.

- Un disque mémoire USB qui contient une image Windows 10 Professionnel ou Entreprise. Installez ensuite [les pilotes et le microprogramme pour Windows 10 Professionnel et Entreprise](https://www.microsoft.com/download/details.aspx?id=101974) sur Surface Hub 2.
 
Les étapes suivantes montrent comment créer un disque mémoire USB à partir d’un support d’installation, puis ajouter les fichiers de package SEMM, ainsi que les pilotes et microprogrammes pour Windows 10 Professionnel et enterprise OS sur le fichier MSI Surface Hub 2. Si vous utilisez une autre méthode de déploiement, allez à la section Mettre à jour l’UEFI sur [Surface Hub 2S](#update-uefi-on-surface-hub-2s-to-enable-os-migration) pour activer la migration du système d’exploitation de cet article.

> [!NOTE]
> Une fois l’installation terminé, vous aurez besoin d’une licence valide pour Windows 10 Professionnel ou Windows 10 Entreprise distincte de votre licence Windows 10 Team existante.

1. Pour créer une installation De Windows 10 Professionnel, suivez les instructions pour télécharger l’outil de création de médias sur [Télécharger Windows 10](https://www.microsoft.com/software-download/windows10). Pour télécharger Windows 10 Entreprise, allez dans le Centre de gestion des licences [en volume Microsoft.](https://www.microsoft.com/licensing/servicecenter/default.aspx)

1. Insérez un nouveau lecteur de stockage USB.
1. Ouvrez l’outil de création de médias, **sélectionnez Créer un**support d’installation, puis sélectionnez **Suivant**.

   ![Screenshot shows the option to create installation media.](images/shm-fig16.png)
   
3. Sélectionnez une langue, puis **sélectionnez Windows 10** et **64 bits (x64).** Ensuite, **sélectionnez Suivant.**

   ![Screenshot shows where you select the language, O S edition, and architecture type.](images/shm-fig17.png)
   
4. Sélectionnez **lecteur flash USB,** puis sélectionnez **Suivant**.

   ![Screenshot shows where to select U S B flash drive.](images/shm-fig18.png)
   
5. Une fois le téléchargement terminé, sélectionnez **Terminer.**

   ![L’écran signale que le lecteur U S B est prêt et inclut un bouton Terminer.](images/shm-fig19.png)
   
6. Copiez les fichiers de package SEMM, ainsi que les pilotes et microprogrammes de Windows 10 Professionnel et du système d’exploitation d’entreprise sur Surface Hub 2 (fichier MSI) à la racine du disque mémoire USB *(BOOTME)* qui contient votre image Windows 10. Le lecteur USB BOOTME contient :

    - Votre image de démarrage Windows 10.
    
    - Fichiers de package SEMM, copiés à la racine du lecteur USB :
    
      - *DfciUpdate.dfi*.
      - Fichier texte qui inclut l’empreinte SEMM. (Dans cet exemple, le fichier est *SurfaceUEFI_2020Aug25_1058.txt*.) L’horodateur de date et d’heure généré automatiquement correspond à la date à laquelle vous avez créé le fichier à l’aide du configurateur UEFI Surface.

   - Les pilotes et le microprogramme de Windows 10 Professionnel et du système d’exploitation d’entreprise sur Surface Hub 2 (SurfaceHub2S_Win10_18362_20.082.25682.0.msi). Copiez ce fichier à la racine du lecteur USB.

### Mettre à jour l’UEFI sur Surface Hub 2S pour activer la migration du système d’exploitation

1. Insérez votre lecteur BOOTME dans le port USB-A sur le Surface Hub 2S. Pour obtenir la liste de son contenu requis, consultez la section précédente.

1. Pour démarrer dans UEFI :

   1. Désactiver (arrêter) votre Surface Hub 2S.
   1. Appuyez et **maintenez le volume +**, puis appuyez sur le bouton d’alimentation et relâchez-le. Maintenez le **volume + jusqu’à** ce que le menu UEFI s’affiche.
   
      ![Le dessin montre les boutons de volume et d’alimentation.](images/shm-fig20.png)
      
3. Lorsque l’appareil redémarre, entrez le mot de passe UEFI que vous avez créé précédemment, le cas échéant (recommandé).

   ![Écran mot de passe système.](images/shm-fig22.png)
   
4. Dans le menu UEFI, sélectionnez **Gestion.** Ensuite, **sélectionnez Installer à partir du port USB.**

   ![Screenshot shows where to select Management and then «Install from U S B».](images/shm-fig21.png)
   
5. Sélectionnez **Redémarrer maintenant,** comme l’illustre l’image suivante. L’appareil redémarrera. Il affiche un logo Microsoft blanc au milieu de la fenêtre, puis s’arrête.

   ![Screenshot shows a message prompting you to restart.](images/shm-fig25.png)
   
6. Appuyez sur le bouton d’alimentation et relâchez-le. Dans la boîte de dialogue rouge qui s’affiche, choisissez d’activer le mode de gestion Surface Enterprise.

7. Entrez votre empreinte numérique de certificat à deux caractères et votre mot de passe de paramètres UEFI. Ensuite, **sélectionnez OK**.

   ![Screenshot shows the confirm-activation dialog box where you enter your two-character certificate thumbprint and your UEFI settings password.](images/shm-fig23.png)
 
   > [!NOTE]
   > Après avoir activé SEMM sur votre appareil, le nouveau paramètre UEFI **EnableOSMigration** est appliqué. Vous ne pouvez plus accéder à Windows 10 Team. Au lieu de cela, vous devez continuer à l’étape suivante et installer Windows 10 Professionnel ou Windows 10 Entreprise.

   L’appareil redémarre. Il affiche le logo blanc au milieu de l’écran, puis s’arrête à nouveau.

### Installer Windows 10 Professionnel ou Entreprise

1. Si votre lecteur Windows 10 Professionnel ou Entreprise amorçable ne se trouve pas déjà dans le port USB-A surface Hub 2, insérez-le maintenant. Appuyez ensuite sur le bouton d’alimentation et relâchez-le.

    Lorsque l’appareil démarre, le logo blanc s’affiche au milieu de l’écran. Un cercle pivotant s’affiche ensuite sous le logo blanc.

3. Si l’appareil Surface ne démarre pas automatiquement sur le lecteur USB, éteint l’appareil (débrancher le cordon d’alimentation, puis le brancher à nouveau). Après avoir de nouveau brancher le cordon d’alimentation, l’appareil doit démarrer après quelques secondes. Vous verrez ensuite le logo blanc au milieu de l’écran.

    Si l’appareil ne s’allume pas, appuyez sur le bouton d’alimentation et relâchez-le. Immédiatement après avoir vu le logo au milieu de l’écran, appuyez et maintenez le bouton de volume enfoncé jusqu’à ce que le cercle pivote sous le logo blanc.
 
   ![Image des boutons de volume et d’alimentation.](images/shm-fig26.png)
   
4. Lorsque l’installation OOBE (Out-of-Box Experience) démarre, suivez les instructions pour installer Windows 10 Professionnel ou Entreprise (version 1903 ou ultérieure).

### Installer les pilotes et microprogrammes Surface Hub 2

Pour vous assurer que votre Surface Hub 2 est à jour, installez les pilotes et le [microprogramme pour Windows 10 Professionnel et Entreprise.](https://www.microsoft.com/download/details.aspx?id=101974) Redémarrez ensuite l’appareil. Maintenez la Surface allumée pendant une heure, puis redémarrez-la à nouveau. Vous n’êtes pas invité à redémarrer le deuxième redémarrage. Cette pause et ce redémarrage supplémentaire garantissent que le microprogramme a été entièrement mis à jour.
 
## Configurer les paramètres recommandés

Pour configurer Surface Hub 2S en tant qu’appareil de productivité personnel, voir Configurer Windows 10 Professionnel ou Entreprise [sur Surface Hub 2.](surface-hub-2-post-install.md)

> [!NOTE]
>Si vous ne pouvez pas migrer correctement votre appareil vers Windows 10 Professionnel ou Entreprise pour Surface Hub 2 en suivant les étapes décrites dans cet article, contactez le support [Surface Hub.](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support)

## Pour revenir à Windows 10 Team

Si vous souhaitez restaurer votre appareil vers Windows 10 Team, voir Réinitialiser et [récupérer pour Surface Hub 2S.](surface-hub-2s-recover-reset.md)

> [!NOTE]
> Avant de revenir à Windows 10 Team, nous vous recommandons de désinscrire d’abord le Surface Hub de SEMM. Pour plus d’informations, voir [Désinscrire des appareils Surface à partir de SEMM.](https://docs.microsoft.com/surface/unenroll-surface-devices-from-semm)

## Historique des versions

Le tableau suivant récapitule les modifications apportées à cet article.

| Version | Date               | Description                                                                                           |
| ------- | ------------------ | ----------------------------------------------------------------------------------------------------- |
| v. 1.4  | 14 décembre 2020 | Fournit [](#install-surface-hub-2-drivers-and-firmware) des informations supplémentaires sur l’installation du fichier MSI pour « Pilotes et microprogramme pour Windows 10 Professionnel et Enterprise OS sur Surface Hub 2 », en vous informant qu’un second redémarrage peut être nécessaire en fonction de l’état de votre système.                                                          |
| v. 1.3  | 3 décembre 2020 | Mise à jour avec des conseils [sur la gestion de l’inscription SEMM.](#manage-semm-enrollment)                                                       |
| v. 1.2  | 29 septembre 2020 | Mises à jour diverses qui abordent les commentaires d’utilisation.                                                        |
| v. 1.1  | 15 septembre 2020 | Introduction d’une note supplémentaire qui clarifie les exigences de licence pour l’installation d’un nouveau système d’exploitation. |
| v. 1.0  | 1er septembre 2020  | Nouvel article.                                                                                           |
