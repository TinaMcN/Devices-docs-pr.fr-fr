---
title: Créer des packages d’approvisionnement (SurfaceHub)
description: Pour Windows10, les paramètres qui utilisent le Registre ou un fournisseur de services de configuration (CSP) peuvent être configurés à l’aide de packages d’approvisionnement.
ms.assetid: 8AA25BD4-8A8F-4B95-9268-504A49BA5345
ms.reviewer: ''
manager: laurawi
keywords: ajouter un certificat, package d’approvisionnement
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 03/16/2019
ms.localizationpriority: medium
ms.openlocfilehash: ecbeca9f0910f1fa1ff2721bcf1b745195552ca2
ms.sourcegitcommit: f74253629aaf073b35b1af69439f76e63392c5aa
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/07/2020
ms.locfileid: "11103798"
---
# Créer des packages d’approvisionnement (SurfaceHub)

Cette rubrique décrit comment créer un package d’approvisionnement à l’aide du Concepteur de configuration et d’acquisition d’images Windows, et comment l’appliquer aux appareils SurfaceHub. Pour le SurfaceHub, vous pouvez utiliser des packages d’approvisionnement pour ajouter des certificats, installer des applications de plateforme Windows universelle (UWP), et personnaliser des stratégies et des paramètres.

Vous pouvez appliquer un package d’approvisionnement à l’aide d’une cléUSB lors de la première utilisation, ou par le biais de l’application **Paramètres**. 


## Avantages
-   Configuration rapide des appareils sans utilisation d’un fournisseurGPM.

-   Pas de connectivité réseau requise.

-   Simple à appliquer.

[En savoir plus sur les avantages et les utilisations des packages d’approvisionnement.](https://technet.microsoft.com/itpro/windows/configure/provisioning-packages)


## Configuration requise 

Pour créer un package d’approvisionnement et l’appliquer à un SurfaceHub, vous aurez besoin des éléments suivants:

-   Le Concepteur de configuration Windows, qui peut être installé depuis le Microsoft Store ou à partir du Kit de déploiement et d’évaluation Windows10 (ADK). [Découvrez comment installer le Concepteur de configuration Windows.](https://technet.microsoft.com/itpro/windows/configure/provisioning-install-icd)
-   Une clé USB.
-   Si vous appliquez le package à l’aide de l’application **Paramètres**, vous aurez besoin des informations d’identification d’administrateur de l’appareil.

Vous allez créer le package d’approvisionnement sur unPC exécutant Windows10, l’enregistrer sur un lecteurUSB, puis le déployer sur votre SurfaceHub.


## Éléments pris en charge pour les packages d’approvisionnement du SurfaceHub

À l’aide de l’Assistant d’**approvisionnement d’appareils Surface Hub**, vous pouvez:

- Inscrire l’appareil dans Active Directory, Azure Active Directory ou la GPM 
- Créer un compte d’administrateur pour l’appareil 
- Ajouter des applications et des certificats
- Configurer les paramètres de proxy
- Ajouter un fichier de configuration Surface Hub

>[!WARNING]
>Vous devez exécuter le Concepteur de configuration Windows sur Windows10 pour configurer l’inscription à Azure ActiveDirectory à l’aide de l’Assistant.

À l’aide de l’éditeur d’approvisionnement avancé, vous pouvez ajouter ces éléments à des packages d’approvisionnement pour le SurfaceHub:

- **Stratégies**: le SurfaceHub prend en charge un sous-ensemble des stratégies du [fournisseur de services de configuration de stratégie](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#surfacehubpolicies). 
- **Paramètres**: vous pouvez configurer tous les paramètres dans le [fournisseur de services de configuration SurfaceHub](https://msdn.microsoft.com/library/windows/hardware/mt608323.aspx).

>[!TIP]
> Utilisez l’approvisionnement simple pour créer un package avec les paramètres courants, puis basculez vers l’éditeur avancé pour ajouter d’autres paramètres, des applications, des stratégies, etc.
>
>![ouvrir l’éditeur avancé](images/icd-simple-edit.png)

## Utiliser l’Assistant d’approvisionnement SurfaceHub

Après avoir [installé le Concepteur de configuration Windows](https://technet.microsoft.com/itpro/windows/configure/provisioning-install-icd), vous pouvez créer un package d’approvisionnement.

### Créer le package d’approvisionnement 

1. Ouvrez le Concepteur de configuration Windows:
   - Dans la zone de recherche de l'écran de démarrage ou du menu Démarrer, tapez «Concepteur de configuration Windows», puis cliquez sur le raccourci du Concepteur de configuration Windows, 
    
     ou
    
   - Si vous avez installé le Concepteur de configuration Windows à partir du kit ADK, accédez à `C:\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86` (sur un ordinateur x64) ou à `C:\Program Files\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86\ICD.exe` (sur un ordinateur x86), puis double-cliquez sur **ICD.exe**.

2. Cliquez sur **Approvisionner des appareils Surface Hub**.

3. Nommez votre projet, puis cliquez sur **Suivant**.

### Configurer les paramètres

<table>
<tr><td style="width:45%" valign="top"><img src="images/one.png" alt="step one"/> <img src="images/add-certificates.png" alt="add certificates"/></br></br>Pour configurer l’appareil avec un certificat, cliquez sur <strong>Ajouter un certificat</strong>. Entrez un nom pour le certificat, puis recherchez et sélectionnez le certificat à utiliser.</td><td><img src="images/add-certificates-details.png" alt="add a certificate"/></td></tr> 
<tr><td style="width:45%" valign="top"><img src="images/two.png" alt="step two"/>  <img src="images/proxy.png" alt="configure proxy settings"/></br></br>Activez <strong>Oui</strong> ou <strong>Non</strong> pour les paramètres de proxy. La configuration par défaut pour le SurfaceHub est de détecter automatiquement les paramètres de proxy, ce qui fait que vous pouvez sélectionner <strong>Non</strong> si c’est le paramètre que vous souhaitez. Toutefois, si votre infrastructure nécessitait précédemment l’utilisation d’un serveur proxy et a été modifiée de manière à ce que cela ne soit plus le cas, vous pouvez utiliser un package d’approvisionnement pour ramener vos appareils Surface Hub aux paramètres par défaut en sélectionnant <strong>Oui</strong> et <strong>Détecter automatiquement les paramètres de connexion</strong>. </br></br>Si vous définissez <strong>Oui</strong>, vous pouvez choisir de détecter automatiquement les paramètres de proxy, ou vous pouvez configurer manuellement les paramètres en entrant l’URL d’un script d’installation ou une adresse de serveur proxy statique. Vous pouvez également indiquer si vous souhaitez utiliser le serveur proxy pour les adresses locales, et entrez des exceptions (des adresses auxquelles le Surface Hub doit se connecter directement, sans utiliser le serveur proxy).  </td><td><img src="images/proxy-details.png" alt="configure proxy settings"/></td></tr>
<tr><td style="width:45%" valign="top"><img src="images/three.png" alt="step three"/>  <img src="images/set-up-device-admins.png" alt="device admins"/></br></br>Vous pouvez inscrire l’appareil dans ActiveDirectory et spécifier un groupe de sécurité pour utiliser l’application Paramètres, l’inscrire dans Azure ActiveDirectory pour autoriser les administrateurs généraux à utiliser l’application Paramètres, ou créer un compte d’administrateur local sur l’appareil.</br></br>Pour inscrire l’appareil dans ActiveDirectory, entrez les informations d’identification d’un compte d’utilisateur moins privilégié pour joindre l’appareil au domaine, et spécifiez le groupe de sécurité correspondant aux informations d’identification d’administrateur sur le Surface Hub. Si un package d’approvisionnement qui inscrit un appareil dans ActiveDirectory doit être appliqué à un Surface Hub qui a été réinitialisé, le même compte de domaine peut être utilisé uniquement si le compte répertorié est un administrateur de domaine ou s’il s’agit du même compte que celui qui a servi à configurer le Surface Hub initialement. Sinon, un compte de domaine différent doit être utilisé dans le package d’approvisionnement.</br></br>Avant d’utiliser un Assistant du Concepteur de configuration Windows pour configurer l’inscription en bloc à Azure AD, <a href="https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup" data-raw-source="[set up Azure AD join in your organization](https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup)">configurez la jonction Azure AD dans votre organisation</a>. Le paramètre <strong>Nombre maximal d'appareils par utilisateur</strong> dans votre locataire Azure AD détermine le nombre de fois où le jeton en bloc que vous avez obtenu via l’assistant peut être utilisé. Pour inscrire l’appareil dans Azure AD, sélectionnez cette option et entrez un nom convivial pour le jeton en bloc que vous obtiendrez via l’assistant. Définissez une date d’expiration pour le jeton (30jours maximum à compter de la date à laquelle vous avez reçu le jeton). Cliquez sur <strong>Obtenir le jeton en bloc</strong>. Dans la <strong> fenêtre permettre aux&#39;de vous connecter </strong> , entrez un compte disposant des autorisations nécessaires pour joindre un appareil à Azure ad, puis le mot de passe. Cliquez sur <strong>Accepter</strong> pour conférer au Concepteur de configuration Windows les autorisations nécessaires.</br></br>Pour créer un compte d’administrateur local, sélectionnez cette option et entrez un nom d'utilisateur et un mot de passe. </br></br><strong>Important:</strong> si vous créez un compte local dans le package d’approvisionnement, vous devez modifier le mot de passe à l’aide de l'application <strong>Paramètres</strong> tous les 42jours. Si le mot de passe n’est pas modifié pendant cette période, le compte peut être verrouillé et vous risquez de ne plus pouvoir vous connecter.  </td><td><img src="images/set-up-device-admins-details.png" alt="join Active Directory, Azure AD, or create a local admin account"/></td></tr>
<tr><td style="width:45%" valign="top"><img src="images/four.png" alt="step four"/> <img src="images/enroll-mdm.png" alt="enroll in device management"/></br></br>Activez <strong>Oui</strong> ou <strong>Non</strong> pour l’inscription dans la GPM. </br></br>Si vous définissez <strong>Oui</strong>, vous devez fournir un compte de service et un mot de passe ou une empreinte de certificat disposant des autorisations nécessaires pour inscrire l’appareil, et également spécifier le type d’authentification. Si cela est requis par votre fournisseur GPM, vous devez également entrer les URL pour le service de découverte, le service d’inscription et le service de stratégie. <a href="manage-settings-with-mdm-for-surface-hub.md" data-raw-source="[Learn more about managing Surface Hub with MDM.](manage-settings-with-mdm-for-surface-hub.md)">En savoir plus sur la gestion du Surface Hub avec la GPM.</a></td><td><img src="images/enroll-mdm-details.png" alt="enroll in mobile device management"/></td></tr>
<tr><td style="width:45%" valign="top"><img src="images/five.png" alt="step five"/> <img src="images/add-applications.png" alt="add applications"/></br></br>Vous pouvez installer plusieurs applications de plateforme Windows universelle (UWP) dans un package d’approvisionnement. Pour obtenir de l’aide concernant ces paramètres, voir <a href="https://technet.microsoft.com/itpro/windows/configure/provision-pcs-with-apps" data-raw-source="[Provision PCs with apps](https://technet.microsoft.com/itpro/windows/configure/provision-pcs-with-apps)">Approvisionner les PC avec des applications</a> </br></br><strong>Important: </strong> bien que l’interface de l’Assistant vous permet de sélectionner une application Win32 classique, incluez uniquement les applications UWP dans un package de mise à service qui sera appliqué à surface Hub. Si vous incluez une application Win32classique, l’approvisionnement échouera. </td><td><img src="images/add-applications-details.png" alt="add an application"/></td></tr>
<tr><td style="width:45%" valign="top"><img src="images/six.png" alt="step six"/>  <img src="images/add-config-file.png" alt="Add configuration file"/></br></br>Vous ne&#39;t pas configurer les paramètres de cette étape. Elle fournit des instructions pour inclure un fichier de configuration contenant une liste de comptes d’appareil. Le fichier de configuration ne doit pas contenir d’en-têtes de colonne. Lorsque vous appliquez le package d’approvisionnement au Surface Hub, si un fichier de configuration Surface Hub est inclus sur le lecteur USB, vous pouvez sélectionner à partir du fichier le compte et le nom convivial à utiliser pour l’appareil. Voir <a href="#sample-configuration-file" data-raw-source="[Sample configuration file](#sample-configuration-file)">Exemple de fichier de configuration</a> pour un exemple.</br></br><strong>Important: </strong> le fichier de configuration peut uniquement être appliqué au cours de l’utilisation de l’interface OOBE (out-of-Box) et ne peut être utilisé qu’avec des packages de mise en service créés à l’aide du concepteur de configuration Windows fourni avec Windows 10, version 1703.  </td><td><img src="images/add-config-file-details.png" alt="Add a Surface Hub configuration file"/></td></tr>
<tr><td style="width:45%" valign="top">  <img src="images/finish.png" alt="finish"/></br></br>Vous pouvez définir un mot de passe pour protéger votre package d’approvisionnement. Vous devez entrer ce mot de passe lorsque vous appliquez le package d’approvisionnement à un appareil.</td><td><img src="images/finish-details.png" alt="Protect your package"/></td></tr>
</table>

Quand vous avez terminé, cliquez sur **Créer**. Cela ne prend que quelques secondes. Une fois le package créé, l’emplacement du package s’affiche en tant que lien hypertexte au bas de la page.

## Exemple de fichier de configuration

Un fichier de configuration SurfaceHub contient une liste de comptes d’appareil que votre appareil peut utiliser pour se connecter à Exchange et à SkypeEntreprise. Lorsque vous appliquez un package d’approvisionnement au Surface Hub, vous pouvez inclure un fichier de configuration dans le répertoire racine du lecteur flash USB, puis sélectionner le compte que vous voulez appliquer à l’appareil. Le fichier de configuration ne peut être appliqué qu’au cours de la phase OOBE et ne peut être utilisé qu’avec des packages d’approvisionnement créés à l’aide du Concepteur de configuration Windows publié avec Windows10version1703.

Utilisez MicrosoftExcel ou tout autre éditeur CSV pour créer un fichier CSV nommé`SurfaceHubConfiguration.csv`. Dans le fichier, entrez la liste des comptes d’appareil et des noms conviviaux en utilisant le format suivant:

```console
<DeviceAccountName>,<DeviceAccountPassword>,<FriendlyName>
```
>[!IMPORTANT]
>Étant donné que le fichier de configuration stocke les mots de passe des comptes d’appareil sous la forme de texte brut, nous vous recommandons de mettre à jour les mots de passe après avoir appliqué le package d’approvisionnement à vos appareils. Vous pouvez utiliser le [nœud DeviceAccount](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/surfacehub-csp#deviceaccount) dans le [fournisseur de services de configuration (CSP) du Surface Hub](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/surfacehub-csp) pour mettre à jour les mots de passe via la GPM.


Voici un exemple de `SurfaceHubConfiguration.csv`. 

```console
Rainier@contoso.com,password,Rainier Surface Hub
Adams@contoso.com,password,Adams Surface Hub
Baker@contoso.com,password,Baker Surface Hub
Glacier@constoso.com,password,Glacier Surface Hub
Stuart@contoso.com,password,Stuart Surface Hub
Fernow@contoso.com,password,Fernow Surface Hub
Goode@contoso.com,password,Goode Surface Hub
Shuksan@contoso.com,password,Shuksan Surface Hub
Buckner@contoso.com,password,Buckner Surface Hub
Logan@contoso.com,password,Logan Surface Hub
Maude@consoto.com,password,Maude Surface hub
Spickard@contoso.com,password,Spickard Surface Hub
Redoubt@contoso.com,password,Redoubt Surface Hub
Dome@contoso.com,password,Dome Surface Hub
Eldorado@contoso.com,password,Eldorado Surface Hub
Dragontail@contoso.com,password,Dragontail Surface Hub
Forbidden@contoso.com,password,Forbidden Surface Hub
Oval@contoso.com,password,Oval Surface Hub
StHelens@contoso.com,password,St Helens Surface Hub
Rushmore@contoso.com,password,Rushmore Surface Hub
```

## Utiliser l’approvisionnement avancé

Après avoir [installé le Concepteur de configuration Windows](https://technet.microsoft.com/itpro/windows/configure/provisioning-install-icd), vous pouvez créer un package d’approvisionnement.

### Créer le package d’approvisionnement (avancé)

1. Ouvrez le Concepteur de configuration Windows:
   - Dans la zone de recherche de l'écran de démarrage ou du menu Démarrer, tapez «Concepteur de configuration Windows», puis cliquez sur le raccourci du Concepteur de configuration Windows, 
    
     ou
    
   - Si vous avez installé le Concepteur de configuration Windows à partir du kit ADK, accédez à `C:\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86` (sur un ordinateur x64) ou à `C:\Program Files\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86\ICD.exe` (sur un ordinateur x86), puis double-cliquez sur **ICD.exe**.

2. Cliquez sur **Approvisionnement avancé**.
   
3. Nommez votre projet, puis cliquez sur **Suivant**.

4. Sélectionnez **communs aux équipes Windows 10**, cliquez sur **suivant**, puis sur **Terminer**.

    ![Nouveau projetICD](images/icd-new-project.png)

5. Dans le projet, sous **personnalisations disponibles**, sélectionnez **paramètres d’équipe communs**.

    ![ParamètresICD communs](images/icd-common-settings.png)


### Ajouter un certificat à votre package
Vous pouvez utiliser des packages d’approvisionnement pour installer les certificats qui permettront à l’appareil de s’authentifier auprès de MicrosoftExchange.

> [!NOTE]
> Les packages d’approvisionnement peuvent installer uniquement des certificats dans le magasin de l’appareil (ordinateur local) et non dans celui de l’utilisateur. Si votre organisation exige que les certificats soient installés dans le magasin de l’utilisateur, utilisez la solutionGPM pour les déployer. Reportez-vous à la documentation relative à la solutionGPM pour en savoir plus.

1. Dans le volet **Personnalisations disponibles**, accédez à **Paramètres d’exécution** > **Certificats** > **ClientCertificates**. 

2. Entrez un **CertificateName**, puis cliquez sur **Ajouter**. 

2. Entrez le **CertificatePassword**. 

3. Pour **CertificatePath**, recherchez et sélectionnez le certificat. 

4. Définissez **ExportCertificate** sur **False**.

5. Pour **KeyLocation**, sélectionnez **Logiciel uniquement**.


### Ajouter une application de plateforme Windows universelle (UWP) à votre package
Avant d’ajouter une applicationUWP à un package d’approvisionnement, vous avez besoin du package d’application (.appx ou .appxbundle) et des fichiers de dépendance. Si vous avez acquis l’application à partir du MicrosoftStore pour Entreprises, vous avez également besoin de la licence de l’application *non codée*. Pour découvrir comment télécharger ces éléments à partir du MicrosoftStore pour Entreprises, voir [Distribuer des applications hors connexion](https://technet.microsoft.com/itpro/windows/manage/distribute-offline-apps#download-an-offline-licensed-app).

1. Dans le volet **Personnalisations disponibles**, accédez à **Paramètres d’exécution** > **UniversalAppInstall** > **DeviceContextApp**.

2. Entrez un **PackageFamilyName** pour l’application, puis cliquez sur **Ajouter**. Par souci de cohérence, utilisez le nom de la famille de packages de l’application. Si vous avez acquis l’application à partir du MicrosoftStore pour Entreprises, vous pouvez trouver ce nom dans la licence de l’application. Ouvrez le fichier de licence à l’aide d’un éditeur de texte, puis utilisez la valeur entre les \<PFM\> balises... \</PFM\> .

3. Pour **ApplicationFile**, cliquez sur **Parcourir** pour rechercher et sélectionner l’application cible (\*.appx ou \*.appxbundle).

4. Pour **DependencyAppxFiles**, cliquez sur **Parcourir** pour rechercher et ajouter les dépendances de l’application. Pour le SurfaceHub, vous avez uniquement besoin des versionsx64 de ces dépendances.

Si vous avez acquis l’application à partir du MicrosoftStore pour Entreprises, vous devez également ajouter la licence de l’application à votre package d’approvisionnement.

1. Effectuez une copie de la licence de l’application, puis renommez-la pour utiliser une extension **.ms-windows-store-license**. Par exemple, «example.xml» devient «example.ms-windows-store-licence».

2. Dans le volet **Personnalisations disponibles** du Concepteur de configuration et d’acquisition d’images (ICD) Windows, accédez à **Paramètres d’exécution** > **UniversalAppInstall** > **DeviceContextAppLicense**.

3. Entrez un **LicenseProductId**, puis cliquez sur **Ajouter**. Par souci de cohérence, utilisez l’ID de licence de l’application indiqué dans la licence de l’application. Ouvrez le fichier de licence dans un éditeur de texte, Ensuite, dans la \<License\> balise, utilisez la valeur de l’attribut **LicenseID** .

4. Sélectionnez le nouveau nœud **LicenseProductId**. Pour **LicenseInstall**, cliquez sur **Parcourir** pour rechercher et sélectionner le fichier de licence que vous avez renommé à l’étape1.


### Ajouter une stratégie à votre package
Le SurfaceHub prend en charge un sous-ensemble des stratégies du [fournisseur de services de configuration de stratégie](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx). Certaines de ces stratégies peuvent être configurées avec le Concepteur de configuration et d’acquisition d’images Windows.

1. Dans le volet **Personnalisations disponibles**, accédez à **Paramètres d’exécution** > **Stratégies**.

2. Sélectionnez l’une des zones de stratégie disponibles.

3. Sélectionnez et définissez la stratégie que vous voulez ajouter à votre package d’approvisionnement.


### Ajouter des paramètres SurfaceHub à votre package 

Vous pouvez ajouter des paramètres du [fournisseur de services de configuration SurfaceHub](https://msdn.microsoft.com/library/windows/hardware/mt608323.aspx) à votre package d’approvisionnement. 

1. Dans le volet **personnalisations disponibles** , accédez à **paramètres d’exécution**  >  **SurfaceHub**.

2. Sélectionnez l’une des zones de paramètre disponibles.

3. Sélectionnez et définissez le paramètre que vous voulez ajouter à votre package d’approvisionnement. 


## Générer votre package

1. Lorsque vous avez terminé la configuration du package de configuration, sur le menu **Fichier**, cliquez sur **Enregistrer**.

2. Lisez l’avertissement indiquant que les fichiers de projet peuvent contenir des informations sensibles, puis cliquez sur **OK**.

    > [!IMPORTANT]
    > Lorsque vous générez un package d’approvisionnement, vous pouvez inclure des informations sensibles dans les fichiers projet et dans le fichier du package d’approvisionnement (.ppkg). Bien que vous ayez la possibilité de chiffrer le fichier .ppkg, les fichiers du projet ne sont pas chiffrés. Vous devez stocker les fichiers de projet dans un emplacement sécurisé et supprimer les fichiers du projet lorsqu’ils ne sont plus nécessaires.

3. Dans le menu **Exporter**, cliquez sur **Package d’approvisionnement**.

4. Remplacez **Propriétaire** par **Administrateur informatique**, qui indique que la priorité de ce package d’approvisionnement est supérieure à celle des packages d’approvisionnement provenant d’autres sources appliqués à cet appareil.

5. Définissez une valeur pour **Version du package**, puis sélectionnez **Suivant**.

    > [!TIP]
    > Vous pouvez apporter des modifications aux packages existants et modifier le numéro de version pour mettre à jour les packages précédemment appliqués.

6. Facultatif: vous pouvez choisir de chiffrer le package et d’activer sa signature.

    -   **Enable package encryption**: si vous sélectionnez cette option, un mot de passe généré automatiquement s’affiche à l’écran.

    -   **Activer la signature du package**: si vous sélectionnez cette option, vous devez sélectionner un certificat valide à utiliser pour signer le package. Vous pouvez spécifier le certificat en cliquant sur **Parcourir...** , puis en sélectionnant le certificat que vous voulez utiliser pour signer le package.

        > [!IMPORTANT]
        > Nous vous recommandons d’inclure un certificat d’approvisionnement approuvé dans votre package d’approvisionnement. Lorsque le package est appliqué à un appareil, le certificat est ajouté au magasin système, et un package signé avec ce certificat par la suite peut être appliqué en mode silencieux. 

7. Cliquez sur **Next** pour spécifier l’emplacement de sortie où vous souhaitez diriger le package de configuration une fois ce dernier généré. Par défaut, Windows ICD utilise le dossier de projet comme emplacement de sortie.<p>
Le cas échéant, cliquez sur **Parcourir** pour modifier l’emplacement de sortie par défaut.

8. Cliquez sur **Suivant**.

9. Cliquez sur **Build** pour commencer à générer le package. Les informations du projet s’affichent dans la page de génération, et la barre de progression indique l’état de la génération.<p>
Si vous avez besoin d’annuler la génération, cliquez sur **Cancel**. Cette opération annule le processus de génération en cours, ferme l’Assistant et réaffiche la page **Customizations Page**.

10. Si la génération échoue, un message d’erreur vous présente un lien vers le dossier du projet. Vous pouvez analyser les journaux pour déterminer l’origine de l’erreur. Après avoir corrigé le problème, essayez de relancer la génération du package.<p>
Si la génération aboutit, le nom du package d’approvisionnement, le répertoire de sortie et le répertoire du projet s’affichent.

    -   Si vous le souhaitez, vous pouvez générer de nouveau le package d’approvisionnement en sélectionnant un autre chemin d’accès pour le package de sortie. Pour effectuer cette opération, cliquez sur **Back** pour modifier le nom et le chemin d’accès du package de sortie, puis cliquez sur **Next** pour lancer une autre génération.
    
    -   Si vous avez terminé, cliquez sur **Finish** pour fermer l’Assistant et revenir à la page **Customizations Page**.

11. Sélectionnez le lien **Emplacement de sortie** pour accéder à l’emplacement du package. Copiez le fichier .ppkg sur un disque mémoireUSB vide.


## Appliquer un package d’approvisionnement à un SurfaceHub

Deuxoptions permettent de déployer des packages d’approvisionnement sur un SurfaceHub. [Lors de la première exécution de l’Assistant](#apply-a-provisioning-package-during-first-run), vous pouvez appliquer un package de mise à service qui installe des certificats, ou après la fin de la première exécution, vous pouvez appliquer un package de mise à service qui configure les paramètres, applications et certificats à l’aide des [paramètres](#apply-a-package-using-settings). 


### Appliquer un package d’approvisionnement lors de la première utilisation

> [!IMPORTANT]
> Lors du premier programme exécuté, vous ne pouvez utiliser que les packages de mise à service pour installer des certificats. Utilisez l’application **Paramètres** pour installer des applications et appliquer d’autres paramètres.

1. Lorsque vous activez le SurfaceHub pour la première fois, le programme de première utilisation affiche la page intitulée [**Bonjour**](first-run-program-surface-hub.md#first-page). Assurez-vous que les paramètres sont configurés correctement avant de poursuivre.

2. Insérez le disque mémoireUSB contenant le fichier .ppkg dans le SurfaceHub. Si le package est situé dans le répertoire racine du lecteur, le programme de première utilisation le reconnaît et vous demande si vous voulez configurer l’appareil. Sélectionnez **Configurer**.

    ![Configurer l’appareil?](images/provisioningpackageoobe-01.png)

3. L’écran suivant vous demande de sélectionner une source d’approvisionnement. Sélectionnez **Média amovible** puis touchez **Suivant**.

    ![Approvisionner cet appareil](images/provisioningpackageoobe-02.png)
    
4. Sélectionnez le package d’approvisionnement (\*.ppkg) que vous voulez appliquer et appuyez sur **Suivant**. Notez que vous ne pouvez installer qu’un seul package lors de la première utilisation.

    ![Choisir un package](images/provisioningpackageoobe-03.png)

5. Le programme de première utilisation affiche un résumé des modifications que le package d’approvisionnement appliquera. Sélectionnez **Oui, l’ajouter**.  

    ![Faites-vous confiance à ce package?](images/provisioningpackageoobe-04.png)
    
6. Si un fichier de configuration est inclus dans le répertoire racine du lecteur flash USB, vous verrez s’afficher **Sélectionner une configuration**. Le premier compte d’appareil figurant dans le fichier de configuration s’affiche avec un résumé des informations de compte qui seront appliquées au Surface Hub.

    ![sélectionner une configuration](images/ppkg-config.png)    

7. Dans **Sélectionner une configuration**, sélectionnez le nom d’appareil à appliquer, puis cliquez sur **Suivant**.

    ![sélectionner un nom convivial pour l’appareil](images/ppkg-csv.png)
    
Les paramètres issus du package d’approvisionnement vont être appliqués à l’appareil et la phase OOBE va se terminer. Après le redémarrage du périphérique, vous pouvez retirer le lecteur flash USB.

### Appliquer un package à l’aide de l’application Paramètres

1. Insérez le lecteur flashUSB contenant le fichier .ppkg dans le SurfaceHub.

2. Sur le Surface Hub, ouvrez **Paramètres** et entrez les informations d’identification d’administrateur lorsque vous y êtes invité.

3. Accédez à **Surface Hub** > **Gestion des appareils**. Sous **Packages d’approvisionnement**, sélectionnez **Ajouter ou supprimer un package d’approvisionnement**.

4. Sélectionnez **Ajouter un package**.

5. Choisissez votre package d’approvisionnement, puis sélectionnez **Ajouter**. Vous devrez peut-être entrer à nouveau les informations d’identification d’administrateur si vous y êtes invité.

6. Un résumé des modifications que le package d’approvisionnement appliquera s’affiche. Sélectionnez **Oui, l’ajouter**.


