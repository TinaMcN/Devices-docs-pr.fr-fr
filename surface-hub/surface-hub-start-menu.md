---
title: Configurer le menu Démarrer de Surface Hub
description: Utilisez la GPM pour personnaliser le menu Démarrer de Surface Hub.
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
ms.topic: article
ms.date: 08/15/2018
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: c5b6a083d543649eab899d2fea36327d08f8bc29
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832405"
---
# <span data-ttu-id="70ec0-103">Configurer le menu Démarrer de Surface Hub</span><span class="sxs-lookup"><span data-stu-id="70ec0-103">Configure Surface Hub Start menu</span></span>

<span data-ttu-id="70ec0-104">La [mise à jour vers Windows10 du 17janvier2018](https://support.microsoft.com/help/4057144) (build 15063.877) permet de personnaliser les menus Démarrer des appareils Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="70ec0-104">The [January 17, 2018 update to Windows 10](https://support.microsoft.com/help/4057144) (build 15063.877) enables customized Start menus on Surface Hub devices.</span></span> <span data-ttu-id="70ec0-105">Vous appliquez la disposition personnalisée du menu Démarrer à l’aide de la gestion des périphériques mobiles (GPM).</span><span class="sxs-lookup"><span data-stu-id="70ec0-105">You apply the customized Start menu layout using mobile device management (MDM).</span></span>

<span data-ttu-id="70ec0-106">Si vous appliquez une disposition personnalisée du menu Démarrer de SurfaceHub, les utilisateurs ne peuvent pas épingler, désépingler ou désinstaller des applications depuis l’écran de démarrage.</span><span class="sxs-lookup"><span data-stu-id="70ec0-106">When you apply a customized Start menu layout to Surface Hub, users cannot pin, unpin, or uninstall apps from Start.</span></span> 

## <span data-ttu-id="70ec0-107">Comment appliquer un menu Démarrer personnalisé à Surface Hub</span><span class="sxs-lookup"><span data-stu-id="70ec0-107">How to apply a customized Start menu to Surface Hub</span></span>

<span data-ttu-id="70ec0-108">Le menu Démarrer personnalisé est défini dans un fichier XML de disposition de l’écran de démarrage.</span><span class="sxs-lookup"><span data-stu-id="70ec0-108">The customized Start menu is defined in a Start layout XML file.</span></span> <span data-ttu-id="70ec0-109">Vous avez deux options pour créer votre fichier XML de disposition de l’écran de démarrage:</span><span class="sxs-lookup"><span data-stu-id="70ec0-109">You have two options for creating your Start layout XML file:</span></span>

- <span data-ttu-id="70ec0-110">Modifier le [XML par défaut du menu Démarrer de Surface Hub](#default)</span><span class="sxs-lookup"><span data-stu-id="70ec0-110">Edit the [default Surface Hub Start XML](#default)</span></span>

    <span data-ttu-id="70ec0-111">- ou -</span><span class="sxs-lookup"><span data-stu-id="70ec0-111">-or-</span></span>

- <span data-ttu-id="70ec0-112">Configurer le menu Démarrer souhaité sur un ordinateur de bureau (en épinglant uniquement les applications qui sont disponibles sur Surface Hub), puis [exporter la disposition](https://docs.microsoft.com/windows/configuration/customize-and-export-start-layout#export-the-start-layout).</span><span class="sxs-lookup"><span data-stu-id="70ec0-112">Configure the desired Start menu on a desktop (pinning only apps that are available on Surface Hub), and then [export the layout](https://docs.microsoft.com/windows/configuration/customize-and-export-start-layout#export-the-start-layout).</span></span>

>[!TIP]
><span data-ttu-id="70ec0-113">Pour ajouter une vignette avec un lien web au menu Démarrer de votre bureau, accédez au lien dans MicrosoftEdge, sélectionnez `...`dans le coin supérieur droit et sélectionnez **Épingler cette page au menu Démarrer**.</span><span class="sxs-lookup"><span data-stu-id="70ec0-113">To add a tile with a web link to your desktop start menu, go to the link in Microsoft Edge, select `...` in the top right corner, and select **Pin this page to Start**.</span></span> <span data-ttu-id="70ec0-114">Reportez-vous à [une disposition du menu Démarrer comprenant un lien MicrosoftEdge](#edge) pour voir comment les liens s’affichent dans le code XML.</span><span class="sxs-lookup"><span data-stu-id="70ec0-114">See [a Start layout that includes a Microsoft Edge link](#edge) for an example of how links will appear in the XML.</span></span>

<span data-ttu-id="70ec0-115">Pour modifier le code XML par défaut ou la disposition exportée, familiarisez-vous avec le [XML de disposition du menu Démarrer](https://docs.microsoft.com/windows/configuration/start-layout-xml-desktop).</span><span class="sxs-lookup"><span data-stu-id="70ec0-115">To edit the default XML or the exported layout, familiarize yourself with the [Start layout XML](https://docs.microsoft.com/windows/configuration/start-layout-xml-desktop).</span></span> <span data-ttu-id="70ec0-116">Il existe quelques [différences entre la disposition du menu Démarrer sur un PC de bureau et un Surface Hub.](#differences)</span><span class="sxs-lookup"><span data-stu-id="70ec0-116">There are a few [differences between Start layout on a deskop and a Surface Hub.](#differences)</span></span>

<span data-ttu-id="70ec0-117">Lorsque votre menu Démarrer est défini dans une disposition XML, [créez une stratégie GPM pour appliquer la disposition.](https://docs.microsoft.com/windows/configuration/customize-windows-10-start-screens-by-using-mobile-device-management#a-href-idbkmk-domaingpodeploymentacreate-a-policy-for-your-customized-start-layout)</span><span class="sxs-lookup"><span data-stu-id="70ec0-117">When you have your Start menu defined in a Start layout XML, [create an MDM policy to apply the layout.](https://docs.microsoft.com/windows/configuration/customize-windows-10-start-screens-by-using-mobile-device-management#a-href-idbkmk-domaingpodeploymentacreate-a-policy-for-your-customized-start-layout)</span></span>

<span id="differences" />
## <span data-ttu-id="70ec0-118">Différences entre les menus Démarrer de Surface Hub et d’un PC de bureau</span><span class="sxs-lookup"><span data-stu-id="70ec0-118">Differences between Surface Hub and desktop Start menu</span></span>

<span data-ttu-id="70ec0-119">Il existe quelques différences importantes entre la personnalisation du menu Démarrer pour Surface Hub et un ordinateur de bureau Windows10:</span><span class="sxs-lookup"><span data-stu-id="70ec0-119">There are a few key differences between Start menu customization for Surface Hub and a Windows 10 desktop:</span></span>

- <span data-ttu-id="70ec0-120">Vous ne pouvez pas utiliser **DesktopApplicationTile** ( https://docs.microsoft.com/windows/configuration/start-layout-xml-desktop#startdesktopapplicationtile) dans votre code XML de disposition de début car les applications de bureau Windows (Win32) ne sont pas prises en charge sur surface Hub.</span><span class="sxs-lookup"><span data-stu-id="70ec0-120">You cannot use **DesktopApplicationTile** (https://docs.microsoft.com/windows/configuration/start-layout-xml-desktop#startdesktopapplicationtile) in your Start layout XML because Windows desktop applications (Win32) are not supported on Surface Hub.</span></span>
- <span data-ttu-id="70ec0-121">Vous ne pouvez pas utiliser le XML de disposition du menu Démarrer pour configurer la barre des tâches ou l’écran d’accueil de Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="70ec0-121">You cannot use the Start layout XML to configure the taskbar or the Welcome screen for Surface Hub.</span></span>  
- <span data-ttu-id="70ec0-122">Surface Hub prend en charge un maximum de 6colonnes (6vignettes de 1x1); toutefois, vous **devez** définir `GroupCellWidth=8` même si le Surface Hub n’affiche que les vignettes des colonnes 0 à 5, pas des colonnes 6 et 7.</span><span class="sxs-lookup"><span data-stu-id="70ec0-122">Surface Hub supports a maximum of 6 columns (6 1x1 tiles), however, you **must** define `GroupCellWidth=8` even though Surface Hub will only display tiles in columns 0-5, not columns 6 and 7.</span></span>
- <span data-ttu-id="70ec0-123">Surface Hub prend en charge un nombre maximal de 6lignes (6vignettes de 1x1)</span><span class="sxs-lookup"><span data-stu-id="70ec0-123">Surface Hub supports a maximum 6 rows (6 1x1 tiles)</span></span>
- `SecondaryTile`<span data-ttu-id="70ec0-124">, qui sont utilisées pour les liens; SurfaceHub ouvre les liens dans MicrosoftEdge.</span><span class="sxs-lookup"><span data-stu-id="70ec0-124">, which is used for links, will open the link in Microsoft Edge.</span></span>


<span id="default" />
## <span data-ttu-id="70ec0-125">Exemple: disposition par défaut de la disposition du menu Démarrer de Surface Hub</span><span class="sxs-lookup"><span data-stu-id="70ec0-125">Example: Default Surface Hub Start layout</span></span>

```xml
<LayoutModificationTemplate Version="1" xmlns="http://schemas.microsoft.com/Start/2014/LayoutModification">
  <LayoutOptions StartTileGroupCellWidth="8" />
  <DefaultLayoutOverride>
    <StartLayoutCollection>
      <defaultlayout:StartLayout GroupCellWidth="8" xmlns:defaultlayout="http://schemas.microsoft.com/Start/2014/FullDefaultLayout">
        <start:Group Name="" xmlns:start="http://schemas.microsoft.com/Start/2014/StartLayout">
        <start:Tile
            AppUserModelID="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge"
            Size="2x2"
            Row="0"
            Column="0"/>
        <start:Tile
            AppUserModelID="Microsoft.Getstarted_8wekyb3d8bbwe!App"
            Size="4x2"
            Row="0"
            Column="2"/>
        <start:Tile
            AppUserModelID="Microsoft.Office.PowerPoint_8wekyb3d8bbwe!Microsoft.pptim"
            Size="2x2"
            Row="2"
            Column="0"/>
        <start:Tile
            AppUserModelID="Microsoft.Office.Word_8wekyb3d8bbwe!Microsoft.Word"
            Size="2x2"
            Row="2"
            Column="2"/>
        <start:Tile
            AppUserModelID="Microsoft.Office.Excel_8wekyb3d8bbwe!Microsoft.Excel"
            Size="2x2"
            Row="2"
            Column="4"/>
        <start:Tile
            AppUserModelID="c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy!App"
            Size="2x2"
            Row="4"
            Column="0"/>
        <start:Tile
            AppUserModelID="microsoft.microsoftskydrive_8wekyb3d8bbwe!App"
            Size="2x2"
            Row="4"
            Column="2"/>
        <start:Tile
            AppUserModelID="Microsoft.MicrosoftPowerBIForWindows_8wekyb3d8bbwe!Microsoft.MicrosoftPowerBIForWindows"
            Size="2x2"
            Row="4"
            Column="4"/>
        </start:Group>
      </defaultlayout:StartLayout>
    </StartLayoutCollection>
  </DefaultLayoutOverride>
</LayoutModificationTemplate>
```

<span id="edge" />
## <span data-ttu-id="70ec0-126">Exemple: disposition du menu Démarrer comprenant un lien MicrosoftEdge</span><span class="sxs-lookup"><span data-stu-id="70ec0-126">Example: Start layout that includes a Microsoft Edge link</span></span>

<span data-ttu-id="70ec0-127">Cet exemple montre un lien vers un site web et un lien vers un fichier .pdf.</span><span class="sxs-lookup"><span data-stu-id="70ec0-127">This example shows a link to a website and a link to a .pdf file.</span></span> <span data-ttu-id="70ec0-128">La vignette secondaire de Microsoft Edge utilise une icône de 150 x 150 pixels.</span><span class="sxs-lookup"><span data-stu-id="70ec0-128">The secondary tile for Microsoft Edge uses a 150 x 150 pixel icon.</span></span>

```xml
<LayoutModificationTemplate Version="1" xmlns="http://schemas.microsoft.com/Start/2014/LayoutModification">
  <LayoutOptions StartTileGroupCellWidth="8" />
  <DefaultLayoutOverride>
    <StartLayoutCollection>
      <defaultlayout:StartLayout GroupCellWidth="8" xmlns:defaultlayout="http://schemas.microsoft.com/Start/2014/FullDefaultLayout">
        <start:Group Name="" xmlns:start="http://schemas.microsoft.com/Start/2014/StartLayout">
    <start:Tile
              AppUserModelID="Microsoft.Office.PowerPoint_8wekyb3d8bbwe!Microsoft.pptim"
              Size="2x2"
              Row="0"
              Column="0"/>
          <start:Tile
              AppUserModelID="Microsoft.Office.Word_8wekyb3d8bbwe!Microsoft.Word"
              Size="2x2"
              Row="0"
              Column="2"/>
          <start:Tile
              AppUserModelID="Microsoft.Office.Excel_8wekyb3d8bbwe!Microsoft.Excel"
              Size="2x2"
              Row="0"
              Column="4"/>
    <start:Tile
              AppUserModelID="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge"
              Size="2x2"
              Row="2"
              Column="0"/>
    <start:Tile
              AppUserModelID="microsoft.microsoftskydrive_8wekyb3d8bbwe!App"
              Size="2x2" 
             Row="2"
             Column="2"/>   
  <start:SecondaryTile
            AppUserModelID="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge"
           TileID="2678823080"
           DisplayName="Bing"
           Arguments="https://www.bing.com/"
           Square150x150LogoUri="ms-appx:///"
           Wide310x150LogoUri="ms-appx:///"
           ShowNameOnSquare150x150Logo="true"
           ShowNameOnWide310x150Logo="false"
           BackgroundColor="#ffe9e7e7"
           ForegroundText="dark"
           Size="2x2"
           Column="4"
           Row="2"  />
    <start:Tile
              AppUserModelID="Microsoft.Windows.Photos_8wekyb3d8bbwe!App"
              Size="2x2"
              Row="4"
              Column="0"/>
    <start:SecondaryTile
             AppUserModelID="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge"
             TileID="6153963000"
             DisplayName="cstrtqbiology.pdf"
             Arguments="-contentTile -formatVersion 0x00000003 -pinnedTimeLow 0x45b7376e -pinnedTimeHigh 0x01d2356c -securityFlags 0x00000000 -tileType 0x00000000 -url 0x0000003a https://www.ada.gov/regs2010/2010ADAStandards/Guidance_2010ADAStandards.pdf"
             Square150x150LogoUri="ms-appx:///Assets/MicrosoftEdgeSquare150x150.png"
             Wide310x150LogoUri="ms-appx:///" 
             ShowNameOnSquare150x150Logo="true"
             ShowNameOnWide310x150Logo="false"
             BackgroundColor="#ff4e4248"
             Size="4x2" 
             Row="4"
             Column="2"/>
        </start:Group>
      </defaultlayout:StartLayout>
    </StartLayoutCollection>
  </DefaultLayoutOverride>
</LayoutModificationTemplate>
```

>[!NOTE]
><span data-ttu-id="70ec0-129">La valeur par défaut pour `ForegroundText` est Light; vous n’avez pas besoin d’inclure `ForegroundText` dans votre code XML, sauf si vous changez la valeur en Dark.</span><span class="sxs-lookup"><span data-stu-id="70ec0-129">The default value for `ForegroundText` is light; you don't need to include `ForegroundText` in your XML unless you're changing the value to dark.</span></span>
