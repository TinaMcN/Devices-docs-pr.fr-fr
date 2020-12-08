---
title: Configurer les comptes d’administrateur non global sur surface Hub 2
description: Cet article décrit comment configurer des comptes d’administrateur non global pour gérer les éléments de surface Hub 2.
keywords: SurfaceHub2S
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 12/07/2020
ms.localizationpriority: Medium
appliesto:
- Surface Hub 2S 2020 Update
ms.openlocfilehash: 647a7bf53e5ca8dc52ddec21ec8393cc574ee95a
ms.sourcegitcommit: 16cc2e8d9dfc5d6e061e0b5b6ddfcf35547643f2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/08/2020
ms.locfileid: "11196798"
---
# Configurer les comptes d’administrateur non global sur surface Hub 2

Lorsque vous rejoignez surface Hub 2S à un domaine Azure AD, vous pouvez configurer des comptes d’administration non globale qui limitent les autorisations de gestion de l’application paramètres sur surface Hub 2S. Cela vous permet de limiter les autorisations d’administration de surface Hub 2 uniquement et d’empêcher l’accès d’un administrateur potentiellement indésirable à l’intégralité d’un domaine Azure AD. Avant de commencer, assurez-vous que votre surface Hub 2 est liée à Azure AD. Si ce n’est pas le cas, vous devez réinitialiser surface Hub 2S et terminer le programme d’installation pour la première fois (OOBE), en choisissant l’option pour accéder à Azure AD.

## Résumé 

Le processus de création d’un compte d’administrateur non global implique les étapes suivantes: 

1. Dans Microsoft Intune, créez un groupe de sécurité contenant les administrateurs désignés pour gérer surface Hub 2.
2. Obtenez le SID du groupe Azure AD à l’aide de PowerShell.
3. Créer un fichier XML contenant le SID du groupe Azure AD.
4. Créer un groupe de sécurité contenant les appareils surface Hub 2 qui seront gérés par le groupe de sécurité des administrateurs non globaux.
5. Créez un profil de configuration personnalisé ciblant le groupe de sécurité qui contient vos appareils surface Hub 2S. 


## Créer des groupes de sécurité Azure AD

Tout d’abord, créez un groupe de sécurité contenant les comptes d’administrateur. Ensuite, créez un autre groupe de sécurité pour les appareils surface Hub.  

### Créer un groupe de sécurité pour les comptes d’administrateur

1. Connectez-vous à Intune via le [Centre d’administration Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431), sélectionnez **groupes**  >  **nouveau groupe** > et sous type de groupe, sélectionnez **sécurité.** 
2. Entrez un nom de groupe (par exemple, **administrateurs de surface Hub** ), puis sélectionnez **créer.** 

     ![Créer un groupe de sécurité pour les administrateurs du Hub](images/sh-create-sec-group.png)

3. Ouvrez le groupe, sélectionnez **membres**, puis choisissez **Ajouter des membres** pour entrer les comptes d’administrateur que vous voulez désigner comme administrateurs non généraux sur surface Hub 2. Pour en savoir plus sur la création de groupes dans Intune, voir  [Ajouter des groupes pour organiser les utilisateurs et les appareils](https://docs.microsoft.com/mem/intune/fundamentals/groups-add).

### Créer un groupe de sécurité pour des appareils surface Hub 2S

1. Répétez la procédure précédente pour créer un groupe de sécurité distinct pour les appareils concentrateurs; par exemple, les **appareils surface Hub**. 

     ![Créer un groupe de sécurité pour les appareils concentrateurs](images/sh-create-sec-group-devices.png) 

## Obtenir le SID du groupe Azure AD à l’aide de PowerShell

1. Lancez PowerShell avec des privilèges de compte élevés (**exécuter en tant qu’administrateur**) et vérifiez que votre système est configuré pour exécuter les scripts PowerShell. Pour plus d’informations, reportez-vous à à [propos des stratégies d’exécution](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies?). 
2. [Installez le module Azure PowerShell](https://docs.microsoft.com/powershell/azure/install-az-ps).
3. Connectez-vous à votre client Azure AD.

    ```powershell
    Connect-AzureAD
    ```

4. Lorsque vous êtes connecté à votre client, exécutez l’applet de commande suivante. Il vous invite à «entrer l’ID d’objet de votre groupe Azure AD».

    ```powershell
    function Convert-ObjectIdToSid
    {    param([String] $ObjectId)   
         $d=[UInt32[]]::new(4);[Buffer]::BlockCopy([Guid]::Parse($ObjectId).ToByteArray(),0,$d,0,16);"S-1-12-1-$d".Replace(' ','-')
         
    }
    ```

5. Dans Intune, sélectionnez le groupe que vous avez créé précédemment et copiez l’ID d’objet, comme illustré dans la figure ci-dessous. 

     ![Copier l’ID d’objet du groupe de sécurité](images/sh-objectid.png)

6. Exécutez l’applet de commande suivante pour obtenir le SID du groupe de sécurité:

    ```powershell
    $AADGroup = Read-Host "Please type the Object ID of your Azure AD Group"
    $Result = Convert-ObjectIdToSid $AADGroup
    Write-Host "Your Azure Ad Group SID is" -ForegroundColor Yellow $Result
    ```
    
7. Collez l’ID d’objet dans l’applet de commande PowerShell, appuyez sur **entrée**, puis copiez le **SID du groupe Azure ad** dans un éditeur de texte. 

## Créer un fichier XML contenant le SID du groupe Azure AD

1. Copiez les éléments suivants dans un éditeur de texte: 

    ```xml
      <groupmembership>   
      <accessgroup desc = "Administrators">        
      <member name = "Administrator" />        
      <member name = "S-1-12-1-XXXXXXXXXX-XXXXXXXXXX-XXXXXXXXXX-XXXXXXXXXX" />  
      </accessgroup>
      </groupmembership>
      ```

2. Remplacez le SID de l’espace réservé (en commençant par S-1-12-1) par votre **SID de groupe Azure ad** , puis enregistrez le fichier au format XML. par exemple, **aad-local-admin.xml**. 

## Créer un profil de configuration personnalisé

1. Dans le gestionnaire de points de terminaison, sélectionnez profils de configuration des **appareils**pour  >  **Configuration profiles**  >  **créer un profil**. 
2. Sous plateforme **, sélectionnez Windows 10 ou version ultérieure.** Sous profil, sélectionnez **personnalisé**, puis **créer.**
3. Ajoutez un nom et une description, puis sélectionnez **suivant.**
4. Sous **paramètres**  >  **de configuration-paramètres d’URI OMA**, sélectionnez **Ajouter**.
5. Dans le volet ajouter une ligne, ajoutez un nom, puis sous     **URI OMA**, ajoutez la chaîne suivante: 

    ```OMA-URI
    ./Device/Vendor/MSFT/Policy/Config/RestrictedGroups/ConfigureGroupMembership
    ```
6. Sous type de données, sélectionnez **chaîne XML** et recherchez le fichier XML que vous avez créé à l’étape précédente. 

     ![Télécharger le fichier de configuration XML d’administrateur local](images/sh-local-admin-config.png)

7. Cliquez sur **Save**.
8. Cliquez sur **Sélectionner des groupes à inclure** et choisissez le [groupe de sécurité que vous avez créé précédemment](#create-security-group-for-surface-hub-2s-devices) (**appareils surface Hub**). Cliquez sur **Suivant**.
9. Sous règles d’Applicabilitation, ajoutez une règle le cas échéant. Dans le cas contraire, sélectionnez **suivant** , puis sélectionnez **créer**.

Pour en savoir plus sur les profils de configuration personnalisés utilisant des chaînes d’URI OMA, voir [utiliser des paramètres personnalisés pour les appareils Windows 10 dans Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10).


## Administrateurs non globaux gérant surface Hub 2

Les membres du groupe de sécurité des **administrateurs de surface Hub** peuvent désormais se connecter à l’application paramètres sur surface Hub 2S et gérer les paramètres.
