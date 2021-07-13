---
title: Aangepaste apps voor HoloLens beheren (eerste generatie)
description: Meer informatie over het installeren, verwijderen en side loaden van aangepaste holographic-apps op HoloLens apparaten met behulp van de Apparaatportal en Visual Studio.
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 12/10/2020
manager: v-miegge
keywords: hololens, sideload, side load, side-load, store, uwp, app, install
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.topic: article
ms.localizationpriority: medium
ms.custom:
- CI 111456
- CSSTroubleshooting
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: a179032978e1fc062273a6754e3b0a1ad50a5211
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635905"
---
# <a name="manage-custom-apps-for-hololens-1st-gen"></a><span data-ttu-id="b8cd0-104">Aangepaste apps voor HoloLens beheren (eerste generatie)</span><span class="sxs-lookup"><span data-stu-id="b8cd0-104">Manage custom apps for HoloLens (1st gen)</span></span>

<span data-ttu-id="b8cd0-105">HoloLens ondersteunt veel bestaande toepassingen uit de Microsoft Store, evenals nieuwe apps die specifiek zijn gebouwd voor HoloLens.</span><span class="sxs-lookup"><span data-stu-id="b8cd0-105">HoloLens supports many existing applications from the Microsoft Store, as well as new apps built specifically for HoloLens.</span></span> <span data-ttu-id="b8cd0-106">Dit artikel is gericht op aangepaste holografische toepassingen.</span><span class="sxs-lookup"><span data-stu-id="b8cd0-106">This article focuses on custom holographic applications.</span></span>  

<span data-ttu-id="b8cd0-107">Zie Apps beheren met de Store voor meer informatie over [Store-apps.](holographic-store-apps.md)</span><span class="sxs-lookup"><span data-stu-id="b8cd0-107">For more information about store apps, see [Manage apps with the store](holographic-store-apps.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b8cd0-108">De volgende informatie is gemaakt voor de HoloLens (1e generatie), op dat moment ook wel de HoloLens Developer Edition genoemd.</span><span class="sxs-lookup"><span data-stu-id="b8cd0-108">The following information was created for the HoloLens (1st gen), also called the HoloLens Developer Edition at the time.</span></span> <span data-ttu-id="b8cd0-109">Het sideloaden van apps via de apparaatportal en het installeren van apps via Visual Studio waren toen heel gebruikelijk.</span><span class="sxs-lookup"><span data-stu-id="b8cd0-109">As such sideloading apps via device portal and installing apps via Visual Studio were commonplace then.</span></span> <span data-ttu-id="b8cd0-110">Voor bedrijfsimplementaties wordt niet aangeraden om de ontwikkelaarsmodus in te schakelen, die door beide methoden wordt gebruikt.</span><span class="sxs-lookup"><span data-stu-id="b8cd0-110">For enterprise deployments we do not recommend enabling Developer Mode, which both of these methods use.</span></span> <span data-ttu-id="b8cd0-111">Als u geïnteresseerd bent in een implementatiemethode voor beveiligde apps, raadpleegt u [appbeheer: overzicht.](app-deploy-overview.md)</span><span class="sxs-lookup"><span data-stu-id="b8cd0-111">If you are interested in a secure app deployment method please review our [App Management: Overview](app-deploy-overview.md).</span></span>
>
> <span data-ttu-id="b8cd0-112">Als u op zoek bent naar een van beide ontwikkelaarsmethodes voor app-installatie voor HoloLens 2 apparaten, raadpleegt u:</span><span class="sxs-lookup"><span data-stu-id="b8cd0-112">If you are looking for either developer method of app installation for HoloLens 2 devices please refer to:</span></span>
>
> - [<span data-ttu-id="b8cd0-113">Apparaatportal: Een app installeren</span><span class="sxs-lookup"><span data-stu-id="b8cd0-113">Device Portal: Installing an App</span></span>](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
> - [<span data-ttu-id="b8cd0-114">Apps Visual Studio implementeren en fouten opsporen</span><span class="sxs-lookup"><span data-stu-id="b8cd0-114">Using Visual Studio to deploy and debug Apps</span></span>](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

## <a name="install-custom-apps"></a><span data-ttu-id="b8cd0-115">Aangepaste apps installeren</span><span class="sxs-lookup"><span data-stu-id="b8cd0-115">Install custom apps</span></span>

<span data-ttu-id="b8cd0-116">U kunt uw eigen toepassingen op HoloLens installeren met behulp van de Apparaatportal of door de apps te implementeren vanuit Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b8cd0-116">You can install your own applications on HoloLens either by using the Device Portal or by deploying the apps from Visual Studio.</span></span>

### <a name="installing-an-application-package-with-the-device-portal"></a><span data-ttu-id="b8cd0-117">Een toepassingspakket installeren met de Apparaatportal</span><span class="sxs-lookup"><span data-stu-id="b8cd0-117">Installing an application package with the Device Portal</span></span>

1. <span data-ttu-id="b8cd0-118">Stel een verbinding tot [stand Apparaatportal](/windows/mixed-reality/using-the-windows-device-portal) de doelverbinding HoloLens.</span><span class="sxs-lookup"><span data-stu-id="b8cd0-118">Establish a connection from [Device Portal](/windows/mixed-reality/using-the-windows-device-portal) to the target HoloLens.</span></span>

1. <span data-ttu-id="b8cd0-119">Navigeer in het linkernavigatievenster naar de **pagina Apps.**</span><span class="sxs-lookup"><span data-stu-id="b8cd0-119">In the left navigation, navigate to the **Apps** page.</span></span>

1. <span data-ttu-id="b8cd0-120">Blader **onder App-pakket** naar het APPX-bestand dat aan uw toepassing is gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="b8cd0-120">Under **App Package** browse to the .appx file that is associated with your application.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="b8cd0-121">Zorg ervoor dat u verwijst naar alle bijbehorende afhankelijkheids- en certificaatbestanden.</span><span class="sxs-lookup"><span data-stu-id="b8cd0-121">Make sure to reference any associated dependency and certificate files.</span></span>

1. <span data-ttu-id="b8cd0-122">Selecteer **Go.**</span><span class="sxs-lookup"><span data-stu-id="b8cd0-122">Select **Go**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b8cd0-123">![App-formulier installeren in Windows Apparaatportal op Microsoft HoloLens](images/deviceportal-appmanager.jpg)</span><span class="sxs-lookup"><span data-stu-id="b8cd0-123">![Install app form in Windows Device Portal on Microsoft HoloLens](images/deviceportal-appmanager.jpg)</span></span>

### <a name="deploying-from-microsoft-visual-studio-2015"></a><span data-ttu-id="b8cd0-124">Implementeren vanuit Microsoft Visual Studio 2015</span><span class="sxs-lookup"><span data-stu-id="b8cd0-124">Deploying from Microsoft Visual Studio 2015</span></span>

1. <span data-ttu-id="b8cd0-125">Open de oplossing Visual Studio app (.sln-bestand).</span><span class="sxs-lookup"><span data-stu-id="b8cd0-125">Open your app's Visual Studio solution (.sln file).</span></span>

1. <span data-ttu-id="b8cd0-126">Open eigenschappen van **het** project.</span><span class="sxs-lookup"><span data-stu-id="b8cd0-126">Open the project's **Properties**.</span></span>

1. <span data-ttu-id="b8cd0-127">Selecteer de volgende buildconfiguratie: **Master/x86/Remote Machine.**</span><span class="sxs-lookup"><span data-stu-id="b8cd0-127">Select the following build configuration: **Master/x86/Remote Machine**.</span></span>

1. <span data-ttu-id="b8cd0-128">Wanneer u Externe **machine selecteert:**</span><span class="sxs-lookup"><span data-stu-id="b8cd0-128">When you select **Remote Machine**:</span></span>
   - <span data-ttu-id="b8cd0-129">Zorg ervoor dat het adres naar het Wi-Fi IP-adres van uw HoloLens.</span><span class="sxs-lookup"><span data-stu-id="b8cd0-129">Make sure the address points to the Wi-Fi IP address of your HoloLens.</span></span>
   - <span data-ttu-id="b8cd0-130">Stel verificatie in **op Universal (Unencrypted Protocol).**</span><span class="sxs-lookup"><span data-stu-id="b8cd0-130">Set authentication to **Universal (Unencrypted Protocol)**.</span></span>
   
1. <span data-ttu-id="b8cd0-131">Bouw uw oplossing.</span><span class="sxs-lookup"><span data-stu-id="b8cd0-131">Build your solution.</span></span>

1. <span data-ttu-id="b8cd0-132">Als u de app wilt implementeren vanaf uw ontwikkel-pc naar HoloLens, selecteert u **Externe machine.**</span><span class="sxs-lookup"><span data-stu-id="b8cd0-132">To deploy the app from your development PC to your HoloLens, select **Remote Machine**.</span></span> <span data-ttu-id="b8cd0-133">Als u al een bestaande build op de HoloLens, selecteert u **Ja om** deze nieuwere versie te installeren.</span><span class="sxs-lookup"><span data-stu-id="b8cd0-133">If you already have an existing build on the HoloLens, select **Yes** to install this newer version.</span></span>  

   ![Implementatie van externe machines voor apps Microsoft HoloLens in Visual Studio](images/vs2015-remotedeployment.jpg)  
   
1. <span data-ttu-id="b8cd0-135">De toepassing wordt geïnstalleerd en automatisch op uw HoloLens.</span><span class="sxs-lookup"><span data-stu-id="b8cd0-135">The application will install and auto launch on your HoloLens.</span></span>

<span data-ttu-id="b8cd0-136">Nadat u een app hebt geïnstalleerd, vindt u deze in Alle apps **lijst** (**Start**  >  **Alle apps**).</span><span class="sxs-lookup"><span data-stu-id="b8cd0-136">After you've installed an app, you'll find it in the **All apps** list (**Start** > **All apps**).</span></span>
