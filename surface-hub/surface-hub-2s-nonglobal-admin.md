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
# <span data-ttu-id="706f0-104">Configurer les comptes d’administrateur non global sur surface Hub 2</span><span class="sxs-lookup"><span data-stu-id="706f0-104">Configure non Global admin accounts on Surface Hub 2S</span></span>

<span data-ttu-id="706f0-105">Lorsque vous rejoignez surface Hub 2S à un domaine Azure AD, vous pouvez configurer des comptes d’administration non globale qui limitent les autorisations de gestion de l’application paramètres sur surface Hub 2S.</span><span class="sxs-lookup"><span data-stu-id="706f0-105">When you join Surface Hub 2S to an Azure AD domain, you can configure non Global admin accounts that limit permissions to management of the Settings app on Surface Hub 2S.</span></span> <span data-ttu-id="706f0-106">Cela vous permet de limiter les autorisations d’administration de surface Hub 2 uniquement et d’empêcher l’accès d’un administrateur potentiellement indésirable à l’intégralité d’un domaine Azure AD.</span><span class="sxs-lookup"><span data-stu-id="706f0-106">This enables you to scope admin permissions for Surface Hub 2S only and prevent potentially unwanted admin access an entire Azure AD domain.</span></span> <span data-ttu-id="706f0-107">Avant de commencer, assurez-vous que votre surface Hub 2 est liée à Azure AD.</span><span class="sxs-lookup"><span data-stu-id="706f0-107">Before you begin, make sure your Surface Hub 2S is joined to Azure AD.</span></span> <span data-ttu-id="706f0-108">Si ce n’est pas le cas, vous devez réinitialiser surface Hub 2S et terminer le programme d’installation pour la première fois (OOBE), en choisissant l’option pour accéder à Azure AD.</span><span class="sxs-lookup"><span data-stu-id="706f0-108">If not, you will need to reset Surface Hub 2S and complete the first-time, out-of-the-box (OOBE) setup program, choosing the option to join Azure AD.</span></span>

## <span data-ttu-id="706f0-109">Résumé</span><span class="sxs-lookup"><span data-stu-id="706f0-109">Summary</span></span> 

<span data-ttu-id="706f0-110">Le processus de création d’un compte d’administrateur non global implique les étapes suivantes:</span><span class="sxs-lookup"><span data-stu-id="706f0-110">The process of creating non Global admin accounts involves the following steps:</span></span> 

1. <span data-ttu-id="706f0-111">Dans Microsoft Intune, créez un groupe de sécurité contenant les administrateurs désignés pour gérer surface Hub 2.</span><span class="sxs-lookup"><span data-stu-id="706f0-111">In Microsoft Intune, create a Security group containing the admins designated to manage Surface Hub 2S.</span></span>
2. <span data-ttu-id="706f0-112">Obtenez le SID du groupe Azure AD à l’aide de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="706f0-112">Obtain Azure AD Group SID using PowerShell.</span></span>
3. <span data-ttu-id="706f0-113">Créer un fichier XML contenant le SID du groupe Azure AD.</span><span class="sxs-lookup"><span data-stu-id="706f0-113">Create XML file containing Azure AD Group SID.</span></span>
4. <span data-ttu-id="706f0-114">Créer un groupe de sécurité contenant les appareils surface Hub 2 qui seront gérés par le groupe de sécurité des administrateurs non globaux.</span><span class="sxs-lookup"><span data-stu-id="706f0-114">Create a Security Group containing the Surface Hub 2S devices that will be managed by the non-Global admins Security group.</span></span>
5. <span data-ttu-id="706f0-115">Créez un profil de configuration personnalisé ciblant le groupe de sécurité qui contient vos appareils surface Hub 2S.</span><span class="sxs-lookup"><span data-stu-id="706f0-115">Create a custom Configuration profile targeting the security group that contains your Surface Hub 2S devices.</span></span> 


## <span data-ttu-id="706f0-116">Créer des groupes de sécurité Azure AD</span><span class="sxs-lookup"><span data-stu-id="706f0-116">Create Azure AD security groups</span></span>

<span data-ttu-id="706f0-117">Tout d’abord, créez un groupe de sécurité contenant les comptes d’administrateur.</span><span class="sxs-lookup"><span data-stu-id="706f0-117">First create a security group containing the admin accounts.</span></span> <span data-ttu-id="706f0-118">Ensuite, créez un autre groupe de sécurité pour les appareils surface Hub.</span><span class="sxs-lookup"><span data-stu-id="706f0-118">Then create another security group for Surface Hub devices.</span></span>  

### <span data-ttu-id="706f0-119">Créer un groupe de sécurité pour les comptes d’administrateur</span><span class="sxs-lookup"><span data-stu-id="706f0-119">Create security group for Admin accounts</span></span>

1. <span data-ttu-id="706f0-120">Connectez-vous à Intune via le [Centre d’administration Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431), sélectionnez **groupes**  >  **nouveau groupe** > et sous type de groupe, sélectionnez **sécurité.**</span><span class="sxs-lookup"><span data-stu-id="706f0-120">Sign into Intune via the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), select **Groups** > **New Group** > and under Group type, select **Security.**</span></span> 
2. <span data-ttu-id="706f0-121">Entrez un nom de groupe (par exemple, **administrateurs de surface Hub** ), puis sélectionnez **créer.**</span><span class="sxs-lookup"><span data-stu-id="706f0-121">Enter a Group name -- for example, **Surface Hub Local Admins** -- and then select **Create.**</span></span> 

     ![Créer un groupe de sécurité pour les administrateurs du Hub](images/sh-create-sec-group.png)

3. <span data-ttu-id="706f0-123">Ouvrez le groupe, sélectionnez **membres**, puis choisissez **Ajouter des membres** pour entrer les comptes d’administrateur que vous voulez désigner comme administrateurs non généraux sur surface Hub 2.</span><span class="sxs-lookup"><span data-stu-id="706f0-123">Open the group, select **Members**, and then choose **Add members** to enter the Administrator accounts that you wish to designate as non Global admins on Surface Hub 2S.</span></span> <span data-ttu-id="706f0-124">Pour en savoir plus sur la création de groupes dans Intune, voir  [Ajouter des groupes pour organiser les utilisateurs et les appareils](https://docs.microsoft.com/mem/intune/fundamentals/groups-add).</span><span class="sxs-lookup"><span data-stu-id="706f0-124">To learn more about creating groups in Intune, see  [Add groups to organize users and devices](https://docs.microsoft.com/mem/intune/fundamentals/groups-add).</span></span>

### <span data-ttu-id="706f0-125">Créer un groupe de sécurité pour des appareils surface Hub 2S</span><span class="sxs-lookup"><span data-stu-id="706f0-125">Create security group for Surface Hub 2S devices</span></span>

1. <span data-ttu-id="706f0-126">Répétez la procédure précédente pour créer un groupe de sécurité distinct pour les appareils concentrateurs; par exemple, les **appareils surface Hub**.</span><span class="sxs-lookup"><span data-stu-id="706f0-126">Repeat the previous procedure to create a separate security group for Hub devices; for example, **Surface Hub devices**.</span></span> 

     ![Créer un groupe de sécurité pour les appareils concentrateurs](images/sh-create-sec-group-devices.png) 

## <span data-ttu-id="706f0-128">Obtenir le SID du groupe Azure AD à l’aide de PowerShell</span><span class="sxs-lookup"><span data-stu-id="706f0-128">Obtain Azure AD Group SID using PowerShell</span></span>

1. <span data-ttu-id="706f0-129">Lancez PowerShell avec des privilèges de compte élevés (**exécuter en tant qu’administrateur**) et vérifiez que votre système est configuré pour exécuter les scripts PowerShell.</span><span class="sxs-lookup"><span data-stu-id="706f0-129">Launch PowerShell with elevated account privileges (**Run as Administrator**) and ensure your system is configured to run PowerShell scripts.</span></span> <span data-ttu-id="706f0-130">Pour plus d’informations, reportez-vous à à [propos des stratégies d’exécution](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies?).</span><span class="sxs-lookup"><span data-stu-id="706f0-130">To learn more, refer to [About Execution Policies](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies?).</span></span> 
2. <span data-ttu-id="706f0-131">[Installez le module Azure PowerShell](https://docs.microsoft.com/powershell/azure/install-az-ps).</span><span class="sxs-lookup"><span data-stu-id="706f0-131">[Install Azure PowerShell module](https://docs.microsoft.com/powershell/azure/install-az-ps).</span></span>
3. <span data-ttu-id="706f0-132">Connectez-vous à votre client Azure AD.</span><span class="sxs-lookup"><span data-stu-id="706f0-132">Sign into your Azure AD tenant.</span></span>

    ```powershell
    Connect-AzureAD
    ```

4. <span data-ttu-id="706f0-133">Lorsque vous êtes connecté à votre client, exécutez l’applet de commande suivante.</span><span class="sxs-lookup"><span data-stu-id="706f0-133">When you're signed into your tenant, run the following commandlet.</span></span> <span data-ttu-id="706f0-134">Il vous invite à «entrer l’ID d’objet de votre groupe Azure AD».</span><span class="sxs-lookup"><span data-stu-id="706f0-134">It will prompt you to "Please type the Object ID of your Azure AD Group."</span></span>

    ```powershell
    function Convert-ObjectIdToSid
    {    param([String] $ObjectId)   
         $d=[UInt32[]]::new(4);[Buffer]::BlockCopy([Guid]::Parse($ObjectId).ToByteArray(),0,$d,0,16);"S-1-12-1-$d".Replace(' ','-')
         
    }
    ```

5. <span data-ttu-id="706f0-135">Dans Intune, sélectionnez le groupe que vous avez créé précédemment et copiez l’ID d’objet, comme illustré dans la figure ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="706f0-135">In Intune, select the group you created earlier and copy the Object id, as shown in the following figure.</span></span> 

     ![Copier l’ID d’objet du groupe de sécurité](images/sh-objectid.png)

6. <span data-ttu-id="706f0-137">Exécutez l’applet de commande suivante pour obtenir le SID du groupe de sécurité:</span><span class="sxs-lookup"><span data-stu-id="706f0-137">Run the following commandlet to get the security group's SID:</span></span>

    ```powershell
    $AADGroup = Read-Host "Please type the Object ID of your Azure AD Group"
    $Result = Convert-ObjectIdToSid $AADGroup
    Write-Host "Your Azure Ad Group SID is" -ForegroundColor Yellow $Result
    ```
    
7. <span data-ttu-id="706f0-138">Collez l’ID d’objet dans l’applet de commande PowerShell, appuyez sur **entrée**, puis copiez le **SID du groupe Azure ad** dans un éditeur de texte.</span><span class="sxs-lookup"><span data-stu-id="706f0-138">Paste the Object id into the PowerShell commandlet, press **Enter**, and then copy the **Azure AD Group SID** into a text editor.</span></span> 

## <span data-ttu-id="706f0-139">Créer un fichier XML contenant le SID du groupe Azure AD</span><span class="sxs-lookup"><span data-stu-id="706f0-139">Create XML file containing Azure AD Group SID</span></span>

1. <span data-ttu-id="706f0-140">Copiez les éléments suivants dans un éditeur de texte:</span><span class="sxs-lookup"><span data-stu-id="706f0-140">Copy the following into a text editor:</span></span> 

    ```xml
      <groupmembership>   
      <accessgroup desc = "Administrators">        
      <member name = "Administrator" />        
      <member name = "S-1-12-1-XXXXXXXXXX-XXXXXXXXXX-XXXXXXXXXX-XXXXXXXXXX" />  
      </accessgroup>
      </groupmembership>
      ```

2. <span data-ttu-id="706f0-141">Remplacez le SID de l’espace réservé (en commençant par S-1-12-1) par votre **SID de groupe Azure ad** , puis enregistrez le fichier au format XML. par exemple, **aad-local-admin.xml**.</span><span class="sxs-lookup"><span data-stu-id="706f0-141">Replace the placeholder SID (beginning with S-1-12-1) with your **Azure AD Group SID** and then save the file as XML; for example, **aad-local-admin.xml**.</span></span> 

## <span data-ttu-id="706f0-142">Créer un profil de configuration personnalisé</span><span class="sxs-lookup"><span data-stu-id="706f0-142">Create Custom configuration profile</span></span>

1. <span data-ttu-id="706f0-143">Dans le gestionnaire de points de terminaison, sélectionnez profils de configuration des **appareils**pour  >  **Configuration profiles**  >  **créer un profil**.</span><span class="sxs-lookup"><span data-stu-id="706f0-143">In Endpoint Manager, select **Devices** > **Configuration profiles** > **Create profile**.</span></span> 
2. <span data-ttu-id="706f0-144">Sous plateforme **, sélectionnez Windows 10 ou version ultérieure.**</span><span class="sxs-lookup"><span data-stu-id="706f0-144">Under Platform select **Windows 10 and later.**</span></span> <span data-ttu-id="706f0-145">Sous profil, sélectionnez **personnalisé**, puis **créer.**</span><span class="sxs-lookup"><span data-stu-id="706f0-145">Under Profile, select **Custom**, and then select **Create.**</span></span>
3. <span data-ttu-id="706f0-146">Ajoutez un nom et une description, puis sélectionnez **suivant.**</span><span class="sxs-lookup"><span data-stu-id="706f0-146">Add a name and description and then select **Next.**</span></span>
4. <span data-ttu-id="706f0-147">Sous **paramètres**  >  **de configuration-paramètres d’URI OMA**, sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="706f0-147">Under **Configuration settings** > **OMA-URI Settings**, select **Add**.</span></span>
5. <span data-ttu-id="706f0-148">Dans le volet ajouter une ligne, ajoutez un nom, puis sous     **URI OMA**, ajoutez la chaîne suivante:</span><span class="sxs-lookup"><span data-stu-id="706f0-148">In the Add Row pane, add a name and under     **OMA-URI**, add the following  string:</span></span> 

    ```OMA-URI
    ./Device/Vendor/MSFT/Policy/Config/RestrictedGroups/ConfigureGroupMembership
    ```
6. <span data-ttu-id="706f0-149">Sous type de données, sélectionnez **chaîne XML** et recherchez le fichier XML que vous avez créé à l’étape précédente.</span><span class="sxs-lookup"><span data-stu-id="706f0-149">Under Data type, select **String XML** and browse to open the XML file you created in the previous step.</span></span> 

     ![Télécharger le fichier de configuration XML d’administrateur local](images/sh-local-admin-config.png)

7. <span data-ttu-id="706f0-151">Cliquez sur **Save**.</span><span class="sxs-lookup"><span data-stu-id="706f0-151">Click **Save**.</span></span>
8. <span data-ttu-id="706f0-152">Cliquez sur **Sélectionner des groupes à inclure** et choisissez le [groupe de sécurité que vous avez créé précédemment](#create-security-group-for-surface-hub-2s-devices) (**appareils surface Hub**).</span><span class="sxs-lookup"><span data-stu-id="706f0-152">Click **Select groups to include** and choose the [security group you created earlier](#create-security-group-for-surface-hub-2s-devices) (**Surface Hub devices**).</span></span> <span data-ttu-id="706f0-153">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="706f0-153">Click **Next.**</span></span>
9. <span data-ttu-id="706f0-154">Sous règles d’Applicabilitation, ajoutez une règle le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="706f0-154">Under Applicability rules, add a Rule if desired.</span></span> <span data-ttu-id="706f0-155">Dans le cas contraire, sélectionnez **suivant** , puis sélectionnez **créer**.</span><span class="sxs-lookup"><span data-stu-id="706f0-155">Otherwise, select **Next** and then select **Create**.</span></span>

<span data-ttu-id="706f0-156">Pour en savoir plus sur les profils de configuration personnalisés utilisant des chaînes d’URI OMA, voir [utiliser des paramètres personnalisés pour les appareils Windows 10 dans Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10).</span><span class="sxs-lookup"><span data-stu-id="706f0-156">To learn more about custom configuration profiles using OMA-URI strings, see [Use custom settings for Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10).</span></span>


## <span data-ttu-id="706f0-157">Administrateurs non globaux gérant surface Hub 2</span><span class="sxs-lookup"><span data-stu-id="706f0-157">Non Global admins managing Surface Hub 2S</span></span>

<span data-ttu-id="706f0-158">Les membres du groupe de sécurité des **administrateurs de surface Hub** peuvent désormais se connecter à l’application paramètres sur surface Hub 2S et gérer les paramètres.</span><span class="sxs-lookup"><span data-stu-id="706f0-158">Members of the **Surface Hub Local Admins** Security group can now sign in to the Settings app on Surface Hub 2S and manage settings.</span></span>
