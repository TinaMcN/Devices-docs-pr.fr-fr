---
title: Migrer vers Windows 10 Professionnel ou Entreprise sur Surface Hub 2
description: Cet article décrit la migration de l’équipe Windows 10 sur surface Hub 2 vers Windows 10 professionnel ou Windows 10 entreprise.
keywords: Bureau surface Hub, surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 12/14/2020
ms.localizationpriority: Medium
ms.openlocfilehash: c2851505b3595ea768217de443676b45cc01a9ae
ms.sourcegitcommit: efc38524f81238e0c36371f462eb57123e46d09b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/15/2020
ms.locfileid: "11228555"
---
# Migrer vers Windows 10 Professionnel ou Entreprise sur Surface Hub 2

- [Article historique des versions](#version-history)

Surface Hub 2S est préinstallé avec l’équipe Windows 10. Cette édition personnalisée de Windows 10 est conçue pour faciliter la collaboration dans les environnements de salle de réunion. À présent, vous avez la possibilité d’exécuter Windows 10 professionnel ou entreprise pour utiliser surface Hub 2S de la même façon que n’importe quel autre PC. 

> [!IMPORTANT]
>À la différence d’une mise à niveau ou d’une migration classique, vous devez suivre une procédure d’instructions de ce processus, comme décrit dans cet article. Avant de continuer, passez en revue les composants de la [solution](#solution-components) et le [flux de travail de migration et d’installation](#migration-and-installation-workflow-summary) .


> [!NOTE]
> Lors de l’installation de Windows 10 professionnel ou entreprise, vous avez besoin d’une nouvelle licence distincte de celle de votre licence d’équipe Windows 10 existante. 


Démarrez la migration à partir de l’équipe Windows 10 à l’aide d’un PC distinct et du *Configurateur UEFI surface Configurator*. Utilisez l’outil pour créer un package qui contient un nouveau paramètre UEFI que vous appliquez à surface Hub 2.  

Le Configurator du Configurateur de surface fonctionne en tant qu’interface en mode de gestion de surface entreprise (SEMM). Il est conçu pour faciliter la gestion centralisée des paramètres du microprogramme sur les appareils surface dans un environnement d’entreprise. Pour plus d’informations, consultez la <a href="https://docs.microsoft.com/surface/surface-enterprise-management-mode" target="_blank"> documentation de Microsoft SEMM</a>
 

## Composants de solution

- Périphérique surface Hub 2 exécutant le système d’exploitation de l’équipe Windows 10
- Autre appareil exécutant Windows 10
- Outil de configuration de surface UEFI pour créer le package SEMM
- Image de Windows 10 professionnel ou du système d’exploitation de l’entreprise, version 1903 ou ultérieure
- Deux lecteurs USB ayant 16 Go d’espace de stockage, format FAT32
- Les pilotes et microprogrammes pour Windows 10 professionnel pour le système d’exploitation Windows 10 professionnel sur surface Hub 2 Microsoft Windows Installer (MSI)
- Connexion Internet
- Solution d’imagerie (facultative)

 
## Résumé du flux de travail de la migration et de l’installation

| Étape  | Action                                                                                                 | Résumé                                                                                                                                                                                                                                                                                                                                                                                                  |
| - | ------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1 | [Vérifiez que la version UEFI sur surface Hub 2 répond à la configuration minimale requise.](#verify-uefi-version-on-surface-hub-2s-meets-minimum-requirements)                                  | Assurez-vous que la version UEFI est 694.2938.768.0 ou ultérieure.                                                                                                                                                                                                                                                                                                                                                      |
| deuxième | [Téléchargez les pilotes et le microprogramme du Configurateur de surface noyau et de surface Hub 2.](#download-surface-uefi-configurator-and-surface-hub-2-drivers-and-firmware)                             | Sur la <a href="https://www.microsoft.com/download/details.aspx?id=46703" target="_blank"> page **Outils surface pour cette** page </a> , sélectionnez **Télécharger**. Ensuite, sélectionnez et téléchargez le **Configurateur surface UEFI. Et l'** installer sur un PC distinct. Téléchargez les <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> pilotes et le microprogrammes pour Windows 10 professionnel et le système d’exploitation Windows 10 sur le fichier MSI surface Hub 2.</a> Enregistrez-le pour l’utiliser à l’étape 5. |
| 3D | [Préparez le certificat SEMM.](#prepare-the-semm-certificate)                                                                          | Préparez le certificat requis pour exécuter le configurateur surface UEFI. Ou utilisez votre certificat actuel.                                                                                                                                                                                                                                                                                                      |
| n°4 | [Créer un package SEMM.](#create-a-semm-package)                                                                               | Démarrez le configurateur de surface pour créer un package SEMM sur un lecteur USB, qui contient les fichiers de configuration que vous devez appliquer sur surface Hub 2. Copiez ces fichiers de package SEMM vers un dossier sur votre PC.                                                                                                                                                                                          |
| n°5 | [Préparez le lecteur flash USB qui contient l’image Windows 10, le package SEMM et les pilotes et microprogrammes pour Windows 10 professionnel et le système d’exploitation sur surface Hub 2.](#prepare-a-usb-flash-drive-that-contains-a-windows-10-image-semm-package-and-surface-hub-2-drivers-and-firmware) | Créez un lecteur USB unique contenant une image Windows 10. Dans cet exemple, le lecteur porte le nom *BOOTME*. Ajoutez vos pilotes et microprogrammes pour Windows 10 professionnel et le système d’exploitation Windows 10 professionnel sur surface Hub 2 (étape 2) et SEMM packages (étape 4) au lecteur *BOOTME* .                                                                                                                                                                                                  |
| 6 | [Mettez à jour UEFI sur surface Hub 2 pour activer la migration du système d’exploitation.](#update-uefi-on-surface-hub-2s-to-enable-os-migration)                                              | Utilisez le lecteur *BOOTME* pour démarrer surface Hub 2 dans le menu UEFI et installez le package SEMM.|
| 6 | [Installez Windows 10 professionnel ou version 1903 ou une version ultérieure.](#install-windows-10-pro-or-enterprise)                                        | Utilisez le lecteur *BOOTME* pour installer Windows 10 professionnel ou version 1903 ou une version ultérieure.                                                                                                                                                                                                                                                                                 |
| version8 | [Installez les pilotes et le microprogrammes pour Windows 10 professionnel et le système d’exploitation sur surface Hub 2.](#install-surface-hub-2-drivers-and-firmware)                                        | Pour vous assurer que votre périphérique dispose de l’ensemble des mises à jour et pilotes les plus récents, installez les <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> pilotes et le microprogramme pour Windows 10 professionnel et le système d’exploitation Windows 10 professionnel sur le fichier MSI surface Hub 2.</a>                                                                                                                                                                                                                                                                                  |
| 09 | [Configurez entièrement surface Hub 2S en tant que périphérique de productivité personnel.](#configure-recommended-settings)                                        |  Activez les applications et paramètres recommandés pour optimiser surface Hub 2S en tant que périphérique de productivité personnel.                                                                                                                                                                                                                                                                    |

### Vérifier la version UEFI sur surface Hub 2 répond à la configuration minimale requise

Avant de migrer surface hub d’une équipe Windows 10 vers une version de bureau Windows 10, vous avez besoin d’une version UEFI d’au moins *694.2938.768.0*.
 
**Pour vérifier la version UEFI sur votre système:**

1. Sur la page d’accueil de surface Hub 2, sélectionnez **Démarrer**, puis ouvrez l’application surface (surface de**toutes les applications**  >  ****).

2. Sélectionnez **votre surface** pour afficher des informations sur surface Hub, y compris la version UEFI actuelle sur l’appareil. 
   - S’il s’agit d' *694.2938.768.0* ou d’une version ultérieure, comme le montre l’image suivante, vous pouvez créer le package SEMM pour activer la migration du système d’exploitation.

       ![Capture d’écran montrant la page de surface dans l’application surface.](images/shm-fig1.png)
 
   - Si la version UEFI est antérieure à la version 694.2938.768.0, vous devez obtenir une version actuelle en installant la mise à jour de l’application 10 d’équipe 2020 de mise à jour sur le matériel vierge
   
**Pour mettre à jour UEFI via Windows Update:**

1. Sur votre surface Hub 2, connectez-vous en tant qu' **administrateur**. 
    >[!Note]
    > Si vous ignorez votre nom d’utilisateur ou votre mot de passe d’administrateur, vous devez réinitialiser l’appareil. Pour plus d’informations, reportez-vous à <a href="https://docs.microsoft.com/surface-hub/surface-hub-2s-recover-reset" target="_blank"> Reset et Recovery pour surface Hub 2.</a>

1. Accédez à **** la  >  mise à jour des**paramètres**d’applications et à la mise à jour de  >  **sécurité**  >  **Windows**, puis installez toutes les mises à jour. 
1. Redémarrez l’appareil. 
1. Vérifiez la version UEFI à l’aide de l’application surface. 
1. À ce stade, si la version UEFI n’est pas encore version 694.2938.768.0 ou ultérieure, vous pouvez soit répéter les étapes ci-dessus, soit vous pouvez obtenir la dernière version de UEFI en installant l’image de l’application de mise à jour complète de l' 2020 équipe Windows 10.

**Pour mettre à jour UEFI via l’image de récupération de matériel vierge (BMR):**

1.  Accédez au [site de récupération de surface](https://support.microsoft.com/surfacerecoveryimage) et sélectionnez **surface Hub 2**
3.  Entrez le numéro de série de votre concentrateur (qui se trouve sur le côté arrière du Hub en regard de Power Connection).
4.  Suivez les instructions pour télécharger l’image sur un lecteur USB formaté par le biais de l’installation de la mise à jour d’équipe 2020 de Windows 10.
5.  À l’issue de la mise à jour et lorsque l’appareil entre dans la première configuration du programme OOBE, vous n’avez pas besoin de compléter OOBE, la version UEFI est mise à jour. Mettez l’appareil hors tension en maintenant le bouton d’alimentation enfoncé jusqu’à ce que l’écran soit éteint. 

### Télécharger les pilotes et le microprogramme du Configurateur de surface UEFI et de surface Hub 2

Sur un PC différent:

1. Sur la <a href="https://www.microsoft.com/download/details.aspx?id=46703" target="_blank"> page outils surface pour cette page </a> , sélectionnez **Télécharger**.  
1. Sélectionner et télécharger le fichier MSI de Configurateur surface UEFI et l’installer sur un PC distinct. L’outil de Configurateur surface UEFI ne peut pas être exécuté sur un surface Hub 2 Lorsque Windows 10 Team Edition est installé

1. Téléchargez les <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> pilotes surface Hub 2 et le microprogramme du programme d’installation Windows Installer </a> . Vous utiliserez ce fichier lors de l’installation du nouveau système d’exploitation.

### Préparer le certificat SEMM

Si vous n’avez encore jamais utilisé le configurateur UEFI de surface, vous devez préparer un certificat. Ce certificat vérifie qu’une fois qu’un appareil est inscrit dans SEMM, vous pouvez modifier les paramètres UEFI uniquement à l’aide de packages créés avec le certificat approuvé. 

La méthode d’obtention d’un certificat dépend de la taille ou de la complexité de votre organisation:

- Les organisations d’entreprise préservent généralement leur propre infrastructure pour générer des certificats conformément aux pratiques de sécurité standard.

- Les entreprises de taille moyenne et d’autres peuvent choisir d’obtenir des certificats auprès des fournisseurs partenaires. Cette option est recommandée pour les organisations qui ne disposent pas de compétences informatiques suffisantes ou d’une équipe dédiée à la sécurité informatique.

- Vous pouvez également générer un certificat auto-signé à l’aide d’un script PowerShell. Pour plus d’informations, voir la <a href="https://docs.microsoft.com/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements" target="_blank"> Configuration requise pour le certificat en mode de gestion des entreprises de surface </a> . Vous pouvez ou utiliser PowerShell pour créer votre propre certificat. Pour plus d’informations, reportez-vous à la <a href="https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate" target="_blank"> documentation nouvelle-SelfSignedCertificate </a> .

Le package SEMM créé par surface Configurator doit être sécurisé à l’aide d’un certificat. Le certificat vérifie la signature des fichiers de configuration avant que les paramètres UEFI puissent être appliqués. Pour plus d’informations, consultez la <a href="https://docs.microsoft.com/surface/surface-enterprise-management-mode" target="_blank"> documentation SEMM </a> .
 
 
### Créer un package SEMM

1. Sur un PC distinct, installez l’outil de configuration de surface UEFI que vous avez téléchargé précédemment. 

2. Ouvrez le configurateur surface UEFI, puis sélectionnez **Démarrer**.

   ![Ouvrez le configurateur surface UEFI.](images/shm-fig2.png)
   
3. Sélectionnez **périphériques surface**, puis sélectionnez **suivant**.

   ![Sélectionnez périphériques surface.](images/shm-fig3.png)
  
4. Sélectionnez **package de configuration**.

   ![Sélectionnez package de configuration.](images/shm-fig4.png)
  
5. Sélectionnez **protection des certificats**.

   ![Sélectionnez protection des certificats.](images/shm-fig5.png)

   Vous êtes invité à ajouter votre fichier Certificate. pfx.

   ![Ajoutez votre certificat.](images/shm-fig6.png)
   
7. Entrez votre mot de passe de certificat, puis sélectionnez **OK**.

   ![Entrez votre mot de passe de certificat et sélectionnez OK.](images/shm-fig7.png)

8. Sélectionnez **protection par mot de passe** pour ajouter un mot de passe pour la surface UEFI. Vous aurez besoin de ce mot de passe chaque fois que vous démarrez l’ordinateur. Nous *vous recommandons vivement* de définir un mot de passe UEFI que vous utiliserez sur surface Hub 2.

   ![Sélectionnez protection par mot de passe.](images/shm-fig8.png)
   
9. Définissez un mot de passe UEFI, puis sélectionnez **OK**.

   > [!IMPORTANT]
   > Enregistrez le mot de passe à un emplacement sécurisé accessible à vos administrateurs informatiques qui gèrent surface Hub. Si le mot de passe est perdu, il ne peut pas être récupéré. 

   ![Entrez votre mot de passe UEFI.](images/shm-fig9.png)

10. Sélectionnez **surface Hub 2**, puis sélectionnez **suivant**.

    ![Sélectionnez surface Hub 2.](images/shm-fig10.png)
   
11. Sélectionnez **Suivant**.

    ![Sélectionnez Suivant.](images/shm-fig10a.png)

12. Pour autoriser l’installation de Windows 10 professionnel ou entreprise, activez **EnableOsMigration**, puis sélectionnez **suivant**.

    ![Sélectionnez Activer la migration de O S.](images/shm-fig11.png)
    
    ![Définissez Activer la migration du système d’exploitation sur activé.](images/shm-fig12.png)

### Gestion de l’inscription de SEMM

L’inscription de périphériques dans SEMM affecte la façon dont vous pouvez gérer l’appareil à l’avenir. Par exemple, après avoir appliqué un package SEMM, dans le menu UEFI de l’appareil, tous les paramètres UEFI ne sont pas disponibles (verrouillés). Les valeurs par défaut pour les autres paramètres, tels que **IPv6 pour le démarrage PXE** , ne sont pas disponibles. 

Pour modifier les paramètres UEFI une fois la migration terminée, appliquez un autre package SEMM ou désinscrivez l’appareil à partir de SEMM. Si vous appliquez un autre package SEMM pour modifier les paramètres UEFI, vous devez utiliser le certificat d’origine lors de la création du nouveau package SEMM. Servez-vous de l’outil de Configurateur UEFI et quittez **EnableOSMigration** (pas activé, comme indiqué dans les étapes de migration d’origine).

#### Utiliser les partenaires

Si votre entreprise utilise la migration vers Windows 10 professionnel ou entreprise sur surface Hub 2, vous souhaiterez peut-être que le partenaire transfère le certificat SEMM, le package SEMM et le mot de passe UEFI.  Par ailleurs, après avoir migré le concentrateur, vous pouvez immédiatement annuler l’inscription à partir de SEMM, ce qui permettra l’administration locale de UEFI et de transférer le périphérique à une autre partie. Néanmoins, il est vivement recommandé d’utiliser un mot de passe UEFI qui peut être configuré après la migration. Pour en savoir plus, voir [gérer les paramètres de surface UEFI](https://docs.microsoft.com/surface/manage-surface-uefi-settings). 

#### Restauration de l’équipe Windows 10

Après la migration, choisissez de restaurer votre appareil à l’équipe Windows 10, [comme décrit ci-dessous](#roll-back-to-windows-10-team), nous vous conseillons d’initialiser d’abord le concentrateur de SEMM. Pour en savoir plus, voir [désinscrire des appareils de surface à partir de SEMM](https://docs.microsoft.com/surface/unenroll-surface-devices-from-semm).


#### Enregistrez le package SEMM sur un lecteur USB.

1. Connectez un lecteur USB à votre PC. 
1. Sélectionnez **Hub 2**, puis sélectionnez **suivant**.

   ![Sélectionner USB](images/shm-fig13.png)

   > [!WARNING]
   > Toutes les données existantes sur le lecteur USB sont effacées lors de la création du package SEMM. Avant de générer le package SEMM, supprimez tous les fichiers du lecteur USB que vous souhaitez enregistrer.
   
2. Sélectionnez **générer**.

   ![Sélectionnez générer.](images/shm-fig14.png)

3. Capturez une capture d’écran de cette page, puis sélectionnez **fin**. Votre package SEMM est désormais prêt. Il contient le package SEMM *DfciUpdate. DFI* et un fichier texte qui inclut l’empreinte numérique SEMM (les deux derniers caractères de l’empreinte numérique du certificat).

   ![Sélectionnez fin.](images/shm-fig15.png)
   
4. Enregistrez les deux derniers caractères de l’empreinte de certificat. Vous aurez besoin de ces caractères pour activer SEMM lorsque vous appliquez le package sur surface Hub 2.

### Préparer un lecteur flash USB contenant une image Windows 10, un package SEMM et des pilotes et microprogramme surface Hub 2

Vous pouvez installer une image Windows 10 professionnel ou entreprise (version 1903 ou ultérieure) en utilisant l’une des options suivantes:

- Votre solution d’imagerie actuelle.

- <a href="https://docs.microsoft.com/surface/microsoft-surface-deployment-accelerator" target="_blank"> Accélérateur de déploiement de surface </a> . Utilisez cet outil pour créer une image Windows 10 amorçable. L’image peut inclure toutes les mises à jour de Windows 10 actuelles, Office, d’autres applications que vous choisissez, ainsi que les pilotes et le microprogramme nécessaires. 

- Lecteur flash USB contenant une image Windows 10 professionnel ou entreprise. Ensuite, installez les <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> pilotes et le microprogramme pour Windows 10 professionnel et le système d’exploitation sur surface Hub 2 </a> .
 
La procédure suivante vous explique comment créer une clé USB à partir du support d’installation, puis ajouter les fichiers de package SEMM et les pilotes et le microprogramme pour Windows 10 professionnel pour le système d’exploitation Windows 10 professionnel et sur le fichier MSI surface Hub 2. Si vous utilisez d’autres méthodes de déploiement, accédez à la section [mettre à jour UEFI sur surface Hub 2S pour activer la section migration du système d’exploitation](#update-uefi-on-surface-hub-2s-to-enable-os-migration) de cet article.

> [!NOTE]
> Une fois l’installation terminée, vous avez besoin d’une licence valide pour Windows 10 professionnel ou Windows 10 entreprise séparée de votre licence d’équipe Windows 10 existante.

1. Pour créer une installation de Windows 10 professionnel, dans la <a href="https://www.microsoft.com/software-download/windows10" target="_blank"> page Télécharger Windows 10 </a> , suivez les instructions de téléchargement de l’outil de création de médias. Pour télécharger Windows 10 entreprise, accédez au centre de gestion des <a href="https://www.microsoft.com/licensing/servicecenter/default.aspx" target="_blank"> licences en volume Microsoft </a> .

2. Insérez un nouveau lecteur de stockage USB. 
1. Ouvrez l’outil de création de média, sélectionnez **créer un support d’installation**, puis sélectionnez **suivant**.

   ![Créer un support d’installation.](images/shm-fig16.png)
   
3. Sélectionnez une langue, puis choisissez **Windows 10** et **64 bits (x64)**. Puis sélectionnez **suivant**.

   ![Sélectionnez langue, puis sélectionnez Windows 10 et 64 bits. Puis sélectionnez suivant.](images/shm-fig17.png)
   
4. Sélectionnez **clé USB**, puis sélectionnez **suivant**.

   ![Sélectionnez U S B Flash Drive et sélectionnez Next (suivant).](images/shm-fig18.png)
   
5. Lorsque le téléchargement est terminé, sélectionnez **Terminer**.

   ![Cliquez sur Terminer.](images/shm-fig19.png)
   
6. Copiez les fichiers de package SEMM ainsi que les pilotes et le microprogramme pour Windows 10 professionnel et Enterprise OS sur surface Hub 2 (le fichier MSI) à la racine de la clé USB (*BOOTME*), qui contient votre image Windows 10. Le lecteur USB BOOTME contient les éléments suivants:

    - Votre image de démarrage Windows 10.
    
    - Fichiers de package SEMM (copiés à la racine du lecteur USB).
    
      - *DfciUpdate. DFI*.
      - Fichier texte qui inclut l’empreinte numérique SEMM. (Dans cet exemple, le fichier est *SurfaceUEFI_2020Aug25_1058.txt*.) Le cachet de date généré automatiquement correspond à la date à laquelle vous avez créé le fichier à l’aide de surface Configurator Configurator.

   - Pilotes et microprogrammes pour Windows 10 professionnel et le système d’exploitation sur surface Hub 2 (SurfaceHub2S_Win10_18362_20.082.25682.0.msi). Copiez ce fichier à la racine du lecteur USB.

### Mise à jour de UEFI sur surface Hub 2S pour permettre la migration du système d’exploitation

1. Insérez votre lecteur BOOTME dans le bus USB-Port sur surface Hub 2. Pour obtenir la liste des fichiers requis, voir la section précédente.

2. Pour démarrer dans UEFI:

   1. Désactivez (arrêtez) votre surface Hub 2.
   1. Appuyez de façon prolongée sur **volume +**, puis appuyez sur le bouton d’alimentation et relâchez-le.
   1. Maintenez la **touche Ctrl** enfoncée et appuyez sur le menu UEFI.
   
      ![Appuyez de façon prolongée sur le bouton du volume vers le haut jusqu’à ce que le menu UEFI apparaisse.](images/shm-fig20.png)
      
3. Au redémarrage de l’appareil, entrez le mot de passe UEFI que vous avez créé précédemment, le cas échéant (fortement recommandé).

   ![Entrez le mot de passe UEFI.](images/shm-fig22.png)
   
4. Dans le menu UEFI, sélectionnez ****  >  **installation de gestion depuis USB**.

   ![Sélectionnez gestion et installer à partir d’U S B.](images/shm-fig21.png)
   
5. Sélectionnez **redémarrer maintenant**, comme le montre l’image suivante. L’appareil est redémarré. Il affiche un logo Microsoft blanc au milieu de la fenêtre, puis arrête.

   ![Sélectionnez redémarrer maintenant.](images/shm-fig25.png)
   
6. Appuyez et relâchez le bouton d’alimentation. Dans la fenêtre rouge qui s’affiche, activez le mode de gestion de l’entreprise surface. 

7. Entrez votre empreinte de certificat à deux caractères et votre mot de passe de paramètres UEFI. Puis sélectionnez **OK**.

   ![Entrez votre empreinte de certificat à deux caractères et votre mot de passe de paramètres UEFI.](images/shm-fig23.png)
 
   > [!NOTE]
   > Après avoir activé SEMM sur votre appareil, le nouveau paramètre UEFI **EnableOSMigration** est appliqué. Vous ne pourrez plus accéder à l’équipe Windows 10. À la place, vous devez passer à l’étape suivante et installer Windows 10 professionnel ou Windows 10 entreprise. 

   L’appareil est redémarré. Il affiche le logo blanc au milieu de l’écran, puis s’arrête de nouveau.

### Installation de Windows 10 professionnel ou entreprise

1. Si votre lecteur Windows 10 professionnel ou entreprise amorçable ne se trouve pas déjà dans la surface Hub 2 USB-A port, insérez-le maintenant. Appuyez ensuite sur le bouton d’alimentation et relâchez-le. 

    Au démarrage de l’appareil, vous pouvez voir le logo blanc au milieu de l’écran. Vous voyez alors un cercle tournant en dessous du logo blanc.

3. Si l’appareil ne démarre pas automatiquement sur le lecteur USB, éteignez le périphérique (débranchez le cordon d’alimentation, puis rebranchez-le). Une fois que vous avez branché le cordon d’alimentation, le périphérique doit être amorcé après quelques secondes. Vous pouvez ensuite voir le logo blanc au milieu de l’écran. 

    Si l’appareil ne s’allume pas, appuyez sur le bouton d’alimentation et relâchez-le. Immédiatement après avoir affiché le logo au milieu de l’écran, appuyez sur le bouton de volume et maintenez-le enfoncé jusqu’à ce que le cercle tourne au-dessous du logo blanc.
 
   ![Démarrez sur Windows 10 à partir du lecteur U S B.](images/shm-fig26.png)
   
4. Lorsque le programme d’installation de OOBE (out-of-Box Experience) démarre, suivez les instructions d’installation de Windows 10 professionnel ou entreprise (version 1903 ou ultérieure).

### Installer les pilotes et le microprogramme de surface Hub 2

Pour vous assurer que votre appareil dispose de l’ensemble des mises à jour et pilotes les plus récents, installez les <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> pilotes et le microprogramme pour Windows 10 professionnel et le système d’exploitation sur surface Hub 2 </a> . Après l’installation des pilotes et de la version MSI du microprogramme, redémarrez l’appareil. Ensuite, après avoir réactivé le concentrateur, assurez-vous que le PC est alimenté pendant une heure, puis redémarrez l’appareil. Vous ne serez pas invité à entrer le second redémarrage. En fonction de l’état de votre ordinateur avant de procéder à la migration vers Windows 10 professionnel ou entreprise, cette deuxième étape peut être nécessaire pour que l’intégralité du microprogramme ait été mise à jour.
 
## Configurer les paramètres recommandés

Pour configurer entièrement surface Hub 2S en tant que périphérique de productivité personnel, reportez-vous à la rubrique <a href="surface-hub-2-post-install.md" target="_blank"> configuration de Windows 10 professionnel ou entreprise sur surface Hub 2 </a> .

> [!NOTE]
>Si les étapes décrites dans cet article ne migrent pas correctement votre appareil vers Windows 10 professionnel ou entreprise pour surface Hub 2, contactez le <a href="https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support" target="_blank"> support surface Hub </a> .

## Revenir à l’équipe Windows 10

Si vous voulez restaurer votre appareil vers l’équipe Windows 10, voir <a href="surface-hub-2s-recover-reset.md" target="_blank"> Réinitialiser et récupérer pour surface Hub 2S </a> .

> [!NOTE]
> Avant de revenir à l’équipe Windows 10, nous vous conseillons d’annuler d’abord le concentrateur auprès de SEMM. Pour en savoir plus, voir [désinscrire des appareils de surface à partir de SEMM](https://docs.microsoft.com/surface/unenroll-surface-devices-from-semm).

## Historique des versions

Le tableau suivant répertorie les modifications apportées à cet article.

| Version | Date               | Description                                                                                           |
| ------- | ------------------ | ----------------------------------------------------------------------------------------------------- |
| version. 1,4  | 14 décembre 2020 | Fournit des [informations supplémentaires](#install-surface-hub-2-drivers-and-firmware) sur l’installation du fichier MSI pour «pilotes et microprogrammes pour Windows 10 professionnel pour le système d’exploitation Windows 10 professionnel sur surface Hub 2», qui vous avertit que le second redémarrage est nécessaire en fonction de l’état de votre système.                                                          |
| version. 1,3  | 3 décembre 2020 | Mis à jour avec des recommandations sur la gestion de l' [inscription de SEMM](#managing-semm-enrollment).                                                       |
| version. 1,2  | 29 septembre 2020 | Les mises à jour diverses qui répondent aux commentaires sur la convivialité.                                                        |
| version. 1,1  | 15 septembre 2020 | A placé une note supplémentaire dans l’introduction qui clarifie les conditions de licence pour l’installation d’un nouveau système d’exploitation. |
| version. 1.0  | 1er septembre 2020  | Nouvel article.                                                                                           |
