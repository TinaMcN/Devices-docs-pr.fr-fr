---
title: Créer un compte d’appareil à l’aide de l’interface utilisateur (Surface Hub v1)
description: Pour utiliser une IU graphique, créez un compte pour votre Surface Hub avec l’interface utilisateur Office365 ou le Centre d’administration Exchange.
ms.assetid: D11BCDC4-DABA-4B9A-9ECB-58E02CC8218C
ms.reviewer: ''
manager: laurawi
keywords: créer un compte d’appareil, interface utilisateur Office 365, Centre d’administration Exchange, Centre d’administration Microsoft 365, Skype Entreprise, stratégie de boîte aux lettres d’appareil mobile
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 05/04/2018
ms.localizationpriority: medium
ms.openlocfilehash: dd19e2fd2417acd29e71c7555e94ee849fbc1bec
ms.sourcegitcommit: 32b6c25698479fa289f642c5b5761ff3be15b686
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/08/2021
ms.locfileid: "11318008"
---
# Créer un compte d’appareil à l’aide de l’interface utilisateur (Surface Hub v1)

 > [!NOTE]
 >Cette page contient des informations sur le Surface Hub d’origine (v1). Pour Surface Hub 2S, voir [Créer un compte d’appareil Surface Hub 2S.](surface-hub-2s-account.md)

Pour utiliser une IU graphique, créez un compte pour votre MicrosoftSurfaceHub avec l’[interface utilisateur Office365](#create-device-acct-o365) ou le [Centre d’administration Exchange](#create-device-acct-eac).

## <a href="" id="create-device-acct-o365"></a>Créer un compte d’appareil à l’aide d’Office 365


1.  [Créez le compte dans le Centre d’administration Microsoft 365.](#create-device-acct-o365-admin-ctr)
2.  [Créez une stratégie de boîte aux lettres d’appareil mobile (ActiveSync) à partir du Centre d’administration Exchange](#create-device-acct-o365-mbx-policy).
3.  [Utiliser Windows PowerShell pour terminer la création du compte d’appareil](#create-device-acct-o365-complete-acct).
4.  [Utilisez PowerShell pour configurer les propriétés Exchange du compte](#create-device-acct-o365-configure-exch-prop).
5.  [Activez le compte d’appareil avec SkypeEntreprise.](#create-device-acct-o365-skype-for-business).

### <a href="" id="create-device-acct-o365-admin-ctr"></a>Créer le compte dans le Centre d’administration

1.  Connectez-vous à Office 365 en visitant [https://portal.office.com](https://portal.office.com) .

2.  Fournissez les informations d’identification d’administration de votre client Office365. Cela vous permettra d’aller dans votre Centre d’administration Microsoft 365.

    > [!div class="mx-imgBorder"]
    > ![Centre d’administration Microsoft 365.](images/setupdeviceaccto365-02.png)

3. Dans le Centre d’administration, accédez à **Ressources** dans le panneau gauche, puis cliquez sur **Salles & équipement.**

    > [!div class="mx-imgBorder"]
    > ![Option Salles &'équipement dans le Centre d’administration](images/room-equipment.png)

4. Cliquez sur **Ajouter** pour créer un nouveau compte de salle. Entrez un nom d'affichage et une adresse e-mail pour le compte, puis cliquez sur **Ajouter**.

    > [!div class="mx-imgBorder"]
    > ![Créer une nouvelle fenêtre de compte de salle](images/room-add.png)

5. Sélectionnez le compte de salle que vous venez de créer dans la liste Utilisateurs actifs. Dans le volet droit, vous pouvez voir les propriétés du compte et plusieurs actions facultatives. Cliquez sur **Réinitialiser le mot de passe** pour modifier le mot de passe, décochez la case demandant aux **utilisateurs de modifier leur mot de passe lors de leur première connexion**, car il n’est pas possible de modifier le mot de passe à partir du flux de connexion Surface Hub.

6. Cliquez sur **Modifier** dans la section **Licence attribuée**, puis sur la flèche déroulante en regard de la licence appropriée pour développer les détails. Sélectionnez un emplacement d’utilisateur, puis dans la liste des licences, activez **Skype Entreprise Online (Plan 2)**, puis cliquez sur **Enregistrer**. La licence peut varier en fonction de votre organisation (par exemple, vous disposez peut-être du plan2 ou du plan3).

### <a href="" id="create-device-acct-o365-mbx-policy"></a>Créer une stratégie de boîte aux lettres d’appareil mobile (ActiveSync) à partir du Centre d’administration Exchange

1.  Dans le panneau gauche du Centre d’administration, cliquez sur **ADMIN,** puis sur **Exchange**.

    > [!div class="mx-imgBorder"]
    > ![centre d’administration, affichant les utilisateurs exchange actifs.](images/setupdeviceaccto365-08.png)

2.  Un autre onglet s’ouvre sur votre navigateur pour accéder au Centre d’administration Exchange, où vous pouvez créer et définir le paramètre de boîte aux lettres du Surface Hub.

    > [!div class="mx-imgBorder"]
    > ![Centre d’administration Exchange.](images/setupdeviceaccto365-09.png)

3.  Pour créer une stratégie de boîte aux lettres d’appareil mobile, cliquez sur **Mobile** dans le volet gauche, puis sur **Stratégies de boîte aux lettres de périphérique mobile**. Les Surfaces Hub requièrent un compte doté d’une stratégie de boîte aux lettres d’appareil mobile qui ne nécessite pas de mot de passe. Ainsi, si vous avez déjà une stratégie existante qui correspond à cette exigence, vous pouvez l’appliquer au compte. Dans le cas contraire, procédez comme suit pour en créer une nouvelle à utiliser uniquement pour les comptes d’appareil Surface Hub.

    > [!div class="mx-imgBorder"]
    > ![Centre d’administration Exchange - création d’une stratégie de boîte aux lettres d’appareil mobile.](images/setupdeviceaccto365-10.png)

4.  Pour créer une nouvelle stratégie de boîte aux lettres d’appareil mobile Surface Hub, cliquez sur le bouton **+** dans les commandes situées au-dessus de la liste des stratégies pour en ajouter une nouvelle. Indiquez un nom qui vous aidera à distinguer cette stratégie des autres comptes d’appareil (par exemple, *SurfaceHubDeviceMobilePolicy*). Assurez-vous que la stratégie ne nécessite pas de mot de passe pour les appareils affectés à celle-ci. Par conséquent, veillez à ce que la case **Exiger un mot de passe** soit décochée, puis cliquez sur **Enregistrer**.

    ![Image montrant une nouvelle stratégie d’appareil mobile.](images/setupdeviceaccto365-11.png)

5.  Après avoir créé la stratégie de boîte aux lettres d’appareil mobile, revenez au **Centre d’administration Exchange** dans lequel s’affiche la nouvelle stratégie.

    > [!div class="mx-imgBorder"]
    > ![Image montrant une nouvelle stratégie de boîte aux lettres d’appareil mobile dans le Centre d’administration Exchange.](images/setupdeviceaccto365-12.png)



### <a href="" id="create-device-acct-o365-complete-acct"></a>Utiliser Windows PowerShell pour terminer la création du compte d’appareil

À partir de là, vous devrez terminer le processus de création de compte à l’aide de PowerShell pour définir une configuration.

Pour exécuter les applets de commande utilisées par ces scripts PowerShell, les éléments suivants doivent être installés pour la console d’administration PowerShell:

-   [assistant Microsoft Online Services Sign-In pour les professionnels de l’informatique RTW](https://www.microsoft.com/download/details.aspx?id=41950)
-   [Module Windows Active Directory pour Windows PowerShell](https://www.microsoft.com/web/handlers/webpi.ashx/getinstaller/WindowsAzurePowershellGet.3f.3f.3fnew.appids)
-   [Skype Entreprise Online, module Windows PowerShell](https://www.microsoft.com/download/details.aspx?id=39366)

Installez le module suivant dans PowerShell.

```powershell
install-module AzureAD
Install-module MsOnline
```

### Connexion aux services en ligne

1.  Exécutez Windows PowerShell en tant qu’administrateur.

    > [!div class="mx-imgBorder"]
    > ![Image montrant comment démarrer Windows PowerShell et l’exécuter en tant qu’administrateur.](images/setupdeviceaccto365-17.png)

2.  Créez un objet Informations d’identification, puis créez une nouvelle session qui se connecte à Skype Entreprise Online. Indiquez ensuite le compte d’administrateur du client global, puis cliquez sur **OK**.

    ![Image relative à la demande d’informations d’identification Windows PowerShell.](images/setupdeviceaccto365-18.png)

3.  Pour se connecter à Microsoft Online Services, exécutez la commande suivante:

    ```powershell
    Connect-MsolService -Credential $Cred
    ```

    ![Image montrant une applet de commande PowerShell.](images/setupdeviceaccto365-19.png)

4.  À présent pour vous connecter à Skype Entreprise Online, exécutez la commande suivante:

    ```powershell
    $sfbsession = New-CsOnlineSession -Credential $cred
    ```

    ![Image montrant une applet de commande PowerShell.](images/setupdeviceaccto365-20.png)

5.  Enfin, pour vous connecter aux services Exchange Online, exécutez la commande suivante:

    ```powershell
    $exchangeSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://outlook.office365.com/powershell-liveid/" -Credential $cred -Authentication "Basic" –AllowRedirection
    ```

    ![Image montrant une applet de commande PowerShell.](images/setupdeviceaccto365-21.png)

6.  Maintenant, vous devez importer les sessions Skype Entreprise Online et Exchange Online que vous venez de créer pour importer les commandes Exchange et Skype afin de les utiliser localement.

    ```powershell
    Import-PSSession $exchangesession -AllowClobber -WarningAction SilentlyContinue
    Import-PSSession $sfbsession -AllowClobber -WarningAction SilentlyContinue
    ```

    Notez que cette opération peut prendre un certain temps.

    ![Image montrant une applet de commande PowerShell.](images/setupdeviceaccto365-22.png)

7.  Une fois que vous êtes connecté aux services en ligne, vous devez encore exécuter quelques applets de commande pour configurer ce compte comme compte d’appareil Surface Hub.

### <a href="" id="create-device-acct-o365-configure-exch-prop"></a>Utiliser PowerShell pour configurer les propriétés Exchange du compte

Maintenant que vous êtes connecté aux services en ligne, vous pouvez terminer la configuration du compte d’appareil. Vous allez utiliser l’adresse électronique du compte d’appareil pour effectuer les actions suivantes:

-   Modifier le type de boîte aux lettres pour le convertir de «standard» à «de salle».
-   Définir le mot de passe et activer le compte de boîte aux lettres de salle
-   Modifier les différentes propriétés d’Exchange
-   Définir le mot de passe du compte d’utilisateur de sorte qu’il n’expire jamais.

1.  Vous devez entrer l’adresse de messagerie du compte et créer une variable avec la valeur suivante:

    ```powershell
    $mailbox = (Get-Mailbox <your device account’s alias>)
    ```

    Pour stocker la valeur, obtenez-la à partir de la boîte aux lettres à l’aide de la commande suivante:

    ```powershell
    $strEmail = $mailbox.WindowsEmailAddress
    ```

    Imprimez la valeur à l’aide de la commande suivante:

    ```powershell
    $strEmail
    ```

    L’adresse de messagerie appropriée s’affiche.

    ![Image montrant une applet de commande PowerShell.](images/setupdeviceaccto365-23.png)

2. Exécutez l’cmdlet suivante :

    ```powershell
    Set-CASMailbox $strEmail  -ActiveSyncMailboxPolicy "SurfaceHubDeviceMobilePolicy"
    ```

4.  Diverses propriétés Exchange peuvent être définies sur le compte d’appareil pour améliorer l’expérience de réunion. Vous pouvez voir les propriétés à définir dans la section [Propriétés Exchange](exchange-properties-for-surface-hub-device-accounts.md).

    ```powershell
    Set-CalendarProcessing -Identity $strEmail -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts   $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
    Set-CalendarProcessing -Identity $strEmail -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
    ```

    ![Image montrant une applet de commande PowerShell.](images/setupdeviceaccto365-26.png)

5.  Si vous décidez que le mot de passe n’expire pas, vous pouvez également définir cette option avec des applets de commande PowerShell. Consultez [Gestion des mots de passe](password-management-for-surface-hub-device-accounts.md) pour plus d’informations.

    ```powershell
    Set-MsolUser -UserPrincipalName $strEmail -PasswordNeverExpires $True
    ```

### <a href="" id="create-device-acct-o365-skype-for-business"></a>Activer le compte avec SkypeEntreprise

Activez le compte d’appareil avec SkypeEntreprise.

Pour activer SkypeEntreprise, votre environnement doit respecter la configuration suivante:

-   Vous devez avoir Skype Entreprise Online Plan autonome 2 ou supérieur dans votre plan O365. L’abonnement doit prendre en charge la fonctionnalité Conférence.
-   Si vous avez besoin Voix Entreprise (téléphonie PSTN) à l’aide de fournisseurs de services de téléphonie pour le Surface Hub, vous avez besoin de Skype Entreprise Online Plan autonome 3.
-   Vos utilisateurs clients doivent disposer de boîtes aux lettres Exchange.
-   Votre compte Surface Hub nécessite une licence Skype Entreprise Online Plan autonome 2 ou Skype Entreprise Online Plan autonome 3, mais il ne nécessite pas de licence Exchange Online.

1.  Commencez par créer une session PowerShell à distance à partir d’un PC.

    ```PowerShell
    Import-Module SkypeOnlineConnector
    $cssess=New-CsOnlineSession -Credential $cred
    Import-PSSession $cssess -AllowClobber
    ```

2.  Pour activer votre compte SurfaceHub pour Skype Entreprise Server, exécutez l’applet de commande suivante:

    ```powershell
    Enable-CsMeetingRoom -Identity $strEmail -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
    ```

     Si vous n’êtes pas certain de la valeur à utiliser pour le paramètre`RegistrarPool` dans votre environnement, vous pouvez obtenir cette valeur à partir d’un utilisateur Skype Entreprise existant en utilisant l’applet de commande suivante:

    ```powershell
    Get-CsOnlineUser -Identity ‘alice@contoso.microsoft.com’| fl *registrarpool*
    ```

## <a href="" id="create-device-acct-eac"></a>Créer un compte d’appareil à l’aide du Centre d’administration Exchange

>[!NOTE]
>Cette méthode ne fonctionne que si vous synchronisez à partir d’un annuaire Active Directory local.

Vous pouvez utiliser le Centre d’administration Exchange pour créer un compte d’appareil:

1.  [Créez un compte et une boîte aux lettres à l’aide du Centre d’administration Exchange](#create-device-acct-exch-admin-ctr).
2.  [Créez une stratégie de boîte aux lettres d’appareil mobile à partir du Centre d’administration Exchange](#create-device-acct-exch-mbx-policy).
3.  [Utilisez PowerShell pour configurer le compte](#create-device-acct-exch-powershell-conf).
4.  [Activez le compte avec SkypeEntreprise](#create-device-acct-exch-skype-for-business).

### <a href="" id="create-device-acct-exch-admin-ctr"></a>Créer un compte et une boîte aux lettres à l’aide du Centre d’administration Exchange

1.  Connectez-vous à votre Centre d’administration Exchange à l’aide des informations d’identification d’administration Exchange.
2.  Une fois dans le Centre d’administration Exchange, accédez à **Destinataires** dans le volet gauche.

    ![Image montrant des boîtes aux lettres du Centre d’administration Exchange.](images/setupdeviceacctexch-01.png)

3.  Dans les commandes situées au-dessus de la liste des boîtes aux lettres, choisissez **+** pour en créer une, et indiquez un **Nom complet**, un **Nom**, et un **Nom d’ouverture de session de l’utilisateur**, puis cliquez sur **Enregistrer**.

    ![Image illustrant la création d’une nouvelle boîte aux lettres.](images/setupdeviceacctexch-02.png)

### <a href="" id="create-device-acct-exch-mbx-policy"></a>Créer une stratégie de boîte aux lettres d’appareil mobile à partir du Centre d’administration Exchange

>[!NOTE]
>Si vous souhaitez créer et affecter une stratégie au compte que vous avez créé et que vous utilisez Exchange 2010, recherchez les informations correspondantes concernant la création et l’attribution de stratégie lors de l’utilisation de la console de gestion Exchange (EMC).

 

1.  Accédez au Centre d’administration Exchange.

    ![Image illustrant le Centre d’administration Exchange.](images/setupdeviceacctexch-03.png)

2.  Pour créer une stratégie de boîte aux lettres d’appareil mobile, cliquez sur **Mobile** dans le volet gauche, puis sur **Stratégies de boîte aux lettres de périphérique mobile**. Les Surfaces Hub requièrent un compte doté d’une stratégie de boîte aux lettres d’appareil mobile qui ne nécessite pas de mot de passe. Ainsi, si vous avez déjà une stratégie existante qui correspond à cette exigence, vous pouvez l’appliquer au compte. Dans le cas contraire, procédez comme suit pour en créer une nouvelle à utiliser uniquement pour les comptes d’appareil Surface Hub.

    ![Image illustrant la création d’une stratégie de boîte aux lettres d’appareil mobile à partir du Centre d’administration Exchange.](images/setupdeviceacctexch-05.png)

3.  Pour créer une nouvelle stratégie de boîte aux lettres de compte d’appareil mobile, cliquez sur le bouton **+** dans les commandes situées au-dessus de la liste des stratégies pour ajouter une nouvelle stratégie. Indiquez un nom qui vous aidera à distinguer cette stratégie des autres comptes d’appareil (par exemple, *SurfaceHubDeviceMobilePolicy*). La stratégie ne doit pas être protégée par mot de passe. Veillez donc à ce que la case **Exiger un mot de passe** reste décochée, puis cliquez sur **Enregistrer**.

    ![Image montrant une nouvelle stratégie de boîte aux lettres d’appareil mobile.](images/setupdeviceacctexch-06.png)

4.  Après avoir créé la stratégie de boîte aux lettres d’appareil mobile, revenez au Centre d’administration Exchange, dans lequel s’affiche la nouvelle stratégie.

    ![Image montrant une nouvelle stratégie de boîte aux lettres d’appareil mobile dans le Centre d’administration Exchange.](images/setupdeviceacctexch-07.png)

5.  Pour appliquer la stratégie ActiveSync sans l’aide de PowerShell, vous pouvez procédez comme suit:

    -   Dans le Centre d’administration Exchange, cliquez sur **Destinataires** &gt; **Boîtes aux lettres**, puis sélectionnez une boîte aux lettres.

        ![Image illustrant le Centre d’administration Exchange.](images/setupdeviceacctexch-08.png)

    -   Dans le volet **Détails**, faites défiler jusqu’à **Fonctionnalités téléphoniques et vocales** et cliquez sur **Afficher les détails** pour afficher l’écran **Paramètres du périphérique mobile**.

        ![Image montrant les informations de boîte aux lettres.](images/setupdeviceacctexch-09.png)

    -   La stratégie de boîte aux lettres d’appareil mobile actuellement affectée est affichée. Pour modifier la stratégie de boîte aux lettres d’appareil mobile, cliquez sur **Parcourir**.

        ![Image montrant la stratégie de boîte aux lettres d’appareil mobile actuellement affectée.](images/setupdeviceacctexch-10.png)

    -   Choisissez la stratégie de boîte aux lettres d’appareil mobile appropriée dans la liste, cliquez sur **OK**, puis sur **Enregistrer**.

        ![Image montrant une liste des stratégies de boîte aux lettres d’appareil mobile. ](images/setupdeviceacctexch-11.png)

### <a href="" id="create-device-acct-exch-powershell-conf"></a>Utiliser PowerShell pour configurer le compte

Maintenant que vous êtes connecté aux services en ligne, vous pouvez terminer la configuration du compte d’appareil. Vous allez utiliser l’adresse électronique du compte d’appareil pour effectuer les actions suivantes:

-   Modifier le type de boîte aux lettres pour le convertir de «standard» à «de salle».
-   Modifier les différentes propriétés d’Exchange
-   Définir le mot de passe du compte d’utilisateur de sorte qu’il n’expire jamais.

1.  Vous devez entrer l’adresse de messagerie du compte et créer une variable avec la valeur suivante:

    ```powershell
    $mailbox = (Get-Mailbox <your device account’s alias>)
    ```

    Pour stocker la valeur, obtenez-la à partir de la boîte aux lettres à l’aide de la commande suivante:

    ```powershell
    $strEmail = $mailbox.WindowsEmailAddress
    ```

    Imprimez la valeur en exécutant la commande suivante:

    ```powershell
    $strEmail
    ```

    L’adresse de messagerie appropriée s’affiche.

2.  Vous devez convertir le compte en boîte aux lettres de salle. Exécutez donc :

    ```powershell
    Set-Mailbox $strEmail -Type Room
    ```

3.  Pour que le compte d’appareil puisse être authentifié sur une Surface Hub, vous devez activer le compte de boîte aux lettres de salle et définir un mot de passe, afin que le compte puisse être utilisé par l’appareil pour obtenir des informations de réunion à l’aide d’ActiveSync et se connecter à Skype Entreprise.

    ```powershell
    Set-Mailbox $strEmail -RoomMailboxPassword (ConvertTo-SecureString  -String "<your password>" -AsPlainText -Force) -EnableRoomMailboxAccount $true
    ```

4.  Diverses propriétés Exchange peuvent être définies sur le compte d’appareil pour améliorer l’expérience de réunion. Vous pouvez voir les propriétés à définir dans la section [Propriétés Exchange](exchange-properties-for-surface-hub-device-accounts.md).

    ```powershell
    Set-CalendarProcessing -Identity $strEmail -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts   $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
    Set-CalendarProcessing -Identity $strEmail -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
    ```

5.  Nous devons maintenant définir quelques propriétés dans AD. Pour ce faire, vous avez besoin de l’alias du compte (partie du nom d’utilisateur principal qui se transforme avant le «@»).

    ```powershell
    $strAlias = “<your device account’s alias>”
    ```

6.  L’utilisateur doit être activé dans AD avant de pouvoir s’authentifier avec un Surface Hub. Exécutez la commande suivante:

    ```powershell
    Set-ADUser $strAlias -Enabled $True
    ```

7.  Si vous décidez que le mot de passe n’expire pas, vous pouvez également définir cette option avec des applets de commande PowerShell. Consultez [Gestion des mots de passe](password-management-for-surface-hub-device-accounts.md) pour plus d’informations.

    ```powershell
    Set-ADUser $strAlias -PasswordNeverExpires $True
    ```

### <a href="" id="create-device-acct-exch-skype-for-business"></a>Activer le compte avec SkypeEntreprise

Activez le compte d’appareil avec SkypeEntreprise.

Pour activer SkypeEntreprise, votre environnement doit respecter la configuration suivante:

- Vous devez avoir Skype Entreprise Online Plan autonome 2 ou supérieur dans votre plan O365. L’abonnement doit prendre en charge la fonctionnalité Conférence.
- Si vous avez besoin Voix Entreprise (téléphonie PSTN) à l’aide de fournisseurs de services de téléphonie pour le Surface Hub, vous avez besoin de Skype Entreprise Online Plan autonome 3.
- Vos utilisateurs clients doivent disposer de boîtes aux lettres Exchange.
- Votre compte Surface Hub nécessite une licence Skype Entreprise Online Plan autonome 2 ou Skype Entreprise Online Plan autonome 3, mais il ne nécessite pas de licence Exchange Online.

1. Commencez par créer une session PowerShell à distance à partir d’un PC.

    ```PowerShell
    Import-Module SkypeOnlineConnector
    $cssess=New-CsOnlineSession -Credential $cred
    Import-PSSession $cssess -AllowClobber
    ```

2. Récupérez votre pool de bureaux d’enregistrement de comptes Surface Hub.

   Si vous n’êtes pas certain de la valeur à utiliser pour le paramètre `RegistrarPool` dans votre environnement, vous pouvez obtenir cette valeur à partir d’un utilisateur Skype Entreprise existant en utilisant l’applet de commande suivante :

   ```PowerShell
   Get-CsOnlineUser -Identity ‘alice@contoso.microsoft.com’| fl *registrarpool*
   ```

3. Pour activer votre compte Surface Hub pour Skype Entreprise Server, exécutez l’applet de commande suivante:

   ```PowerShell
   Enable-CsMeetingRoom -Identity $strEmail -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```