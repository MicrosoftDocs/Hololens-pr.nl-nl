---
title: Overzicht van CSP's en apparaatbeheer configureren
description: Meer informatie over het configureren van CSP's, beleid en apparaatbeheer met mobile device management en inrichtingspakketten.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 09/16/2020
ms.reviewer: lavinds
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 60e73a9a70a70c5c583edc73a0add2f0f502ef80
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/19/2021
ms.locfileid: "111377918"
---
# <a name="configure-csps-and-device-management-overview"></a><span data-ttu-id="0c880-103">Overzicht van CSP's en apparaatbeheer configureren</span><span class="sxs-lookup"><span data-stu-id="0c880-103">Configure CSPs and Device Management overview</span></span>

<span data-ttu-id="0c880-104">IT-beheerders kunnen beleidsinstellingen definiëren en implementeren op HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="0c880-104">IT Administrators can define and implement policy settings on HoloLens 2.</span></span> <span data-ttu-id="0c880-105">Welke configuratie-instellingen u gebruikt, is afhankelijk van het implementatiescenario en bedrijfsapparaten bieden IT het breedste beheerbereik.</span><span class="sxs-lookup"><span data-stu-id="0c880-105">What configuration settings you use will differ based on the deployment scenario, and corporate devices will offer IT the broadest range of control.</span></span> <span data-ttu-id="0c880-106">In Windows 10 CSP's (Configuration Service Providers) een interface voor het lezen, instellen, wijzigen of verwijderen van configuratie-instellingen op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="0c880-106">In Windows 10, Configuration Service Providers (CSP)s are an interface to read, set, modify, or delete configuration settings on the device.</span></span> <span data-ttu-id="0c880-107">Deze instellingen worden aan registersleutels of bestanden toe te passen.</span><span class="sxs-lookup"><span data-stu-id="0c880-107">These settings map to registry keys or files.</span></span> <span data-ttu-id="0c880-108">Sommige configuratieserviceproviders ondersteunen de WAP-indeling, sommige bieden ondersteuning voor SyncML en sommige bieden ondersteuning voor beide.</span><span class="sxs-lookup"><span data-stu-id="0c880-108">Some configuration service providers support the WAP format, some support SyncML, and some support both.</span></span>

<span data-ttu-id="0c880-109">Zie voor meer informatie Windows 10 Holographic CSP's voor apparaatbeheer de volledige lijst met CSP's die worden ondersteund [in HoloLens-apparaten.](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)</span><span class="sxs-lookup"><span data-stu-id="0c880-109">For more information about Windows 10 Holographic device management CSPs, see the full list of [CSPs supported in HoloLens devices](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens).</span></span>
<span data-ttu-id="0c880-110">IT-beheerders kunnen ook beleids-CSP op apparaten beheren. Zie de volledige lijst met beleids-CSP's die worden ondersteund [door HoloLens 2](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2).</span><span class="sxs-lookup"><span data-stu-id="0c880-110">IT Administrators can also manage Policy CSP on devices, see the full list of [Policy CSPs supported by HoloLens 2](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2).</span></span>

## <a name="configuration-methods"></a><span data-ttu-id="0c880-111">Configuratiemethoden</span><span class="sxs-lookup"><span data-stu-id="0c880-111">Configuration methods</span></span>

### <a name="configure-with-mdm"></a><span data-ttu-id="0c880-112">Configureren met MDM</span><span class="sxs-lookup"><span data-stu-id="0c880-112">Configure with MDM</span></span>

<span data-ttu-id="0c880-113">CSP's en beleidsregels kunnen eenvoudig worden beheerd op elk persoonlijk of zakelijk apparaat dat is ingeschreven in een MDM-systeem.</span><span class="sxs-lookup"><span data-stu-id="0c880-113">CSPs and Policies can be easily managed on any personal or corporate device enrolled in an MDM system.</span></span> <span data-ttu-id="0c880-114">Zodra een apparaat is ingeschreven bij uw MDM-oplossing, kunt u dat apparaat of een set apparaten beheren met behulp van apparaatconfiguraties.</span><span class="sxs-lookup"><span data-stu-id="0c880-114">Once a device is enrolled in your MDM solution, you will be able to manage that device, or set of devices using device configurations.</span></span> <span data-ttu-id="0c880-115">Meer informatie over het beheren [van uw HoloLens-apparaten via MDM.](hololens-mdm-configure.md)</span><span class="sxs-lookup"><span data-stu-id="0c880-115">Learn more about how to [manage your HoloLens devices through MDM](hololens-mdm-configure.md).</span></span>

### <a name="configure-with-provisioning-packages"></a><span data-ttu-id="0c880-116">Configureren met inrichtingspakketten</span><span class="sxs-lookup"><span data-stu-id="0c880-116">Configure with Provisioning Packages</span></span>

<span data-ttu-id="0c880-117">HoloLens 2 ondersteunt ook het instellen van een beperkte set CSP-configuraties voor HoloLens 2 apparaten via aangepaste inrichtingspakketten.</span><span class="sxs-lookup"><span data-stu-id="0c880-117">HoloLens 2 also supports setting a limited set of CSP configurations for HoloLens 2 devices through custom Provisioning Packages.</span></span> <span data-ttu-id="0c880-118">Inrichtingspakketten worden doorgaans gebruikt voor niet door MDM beheerde apparaten en moeten handmatig worden toegepast op elk apparaat.</span><span class="sxs-lookup"><span data-stu-id="0c880-118">Provisioning Packages are typically leveraged for non-MDM managed devices and require to be manually applied to each device.</span></span> <span data-ttu-id="0c880-119">Lees informatie over het bouwen [van aangepaste inrichtingspakketten voor HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning).</span><span class="sxs-lookup"><span data-stu-id="0c880-119">Read information on building custom [Provisioning Packages for HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning).</span></span>

## <a name="configurations"></a><span data-ttu-id="0c880-120">Configuraties</span><span class="sxs-lookup"><span data-stu-id="0c880-120">Configurations</span></span>

### <a name="common-device-restrictions"></a><span data-ttu-id="0c880-121">Algemene apparaatbeperkingen</span><span class="sxs-lookup"><span data-stu-id="0c880-121">Common device restrictions</span></span>

<span data-ttu-id="0c880-122">Sommige apparaatbeperkingen zijn net zo eenvoudig en schakelen een functionaliteit of verbinding met het apparaat uit.</span><span class="sxs-lookup"><span data-stu-id="0c880-122">Some device restrictions are as simple and disabling a functionality or connection to the device.</span></span> <span data-ttu-id="0c880-123">Lees meer over algemene [apparaatbeperkingen voor meer informatie.](hololens-common-device-restrictions.md)</span><span class="sxs-lookup"><span data-stu-id="0c880-123">To learn about these read more about [common device restrictions.](hololens-common-device-restrictions.md)</span></span>

### <a name="kiosk-modes"></a><span data-ttu-id="0c880-124">Kioskmodi</span><span class="sxs-lookup"><span data-stu-id="0c880-124">Kiosk modes</span></span>

<span data-ttu-id="0c880-125">Gebruik kioskmodus om te bepalen welke identiteiten standaard toegang hebben tot welke apps.</span><span class="sxs-lookup"><span data-stu-id="0c880-125">Use Kiosk mode to control which identities have access to which apps by default.</span></span> <span data-ttu-id="0c880-126">Kiosken kunnen worden gebruikt voor een gebruikersinterface voor één of meerdere apps.</span><span class="sxs-lookup"><span data-stu-id="0c880-126">Kiosks can be used for a single app or multiple app UI experience.</span></span> <span data-ttu-id="0c880-127">Kioskconfiguraties variëren van één app voor iedereen die het apparaat gebruikt, tot verschillende apps voor verschillende groepen.</span><span class="sxs-lookup"><span data-stu-id="0c880-127">Kiosk configurations range from a single app for anyone using the device, to different selections of apps for different groups.</span></span> <span data-ttu-id="0c880-128">De kioskmodus zorgt er niet voor dat 'toegestane apps' andere apps starten en was niet bedoeld voor ooit.</span><span class="sxs-lookup"><span data-stu-id="0c880-128">Kiosk mode does not stop “allowed apps” from launching other apps and was not intended to ever.</span></span> <span data-ttu-id="0c880-129">Lees meer over [kioskmodi en hoe u deze kunt gebruiken.](hololens-kiosk.md)</span><span class="sxs-lookup"><span data-stu-id="0c880-129">Learn more by [reading about Kiosk modes and how to use them](hololens-kiosk.md).</span></span>

### <a name="settings-page-visibility"></a><span data-ttu-id="0c880-130">Zichtbaarheid van de pagina Instellingen</span><span class="sxs-lookup"><span data-stu-id="0c880-130">Settings Page Visibility</span></span>

<span data-ttu-id="0c880-131">Gebruik app-beleid instellingen om te bepalen welke identiteiten standaard toegang hebben tot instellingen.</span><span class="sxs-lookup"><span data-stu-id="0c880-131">Use Settings app policy to control which identities have access to settings by default.</span></span> <span data-ttu-id="0c880-132">Met dit beleid kan de app Instellingen zodanig worden geconfigureerd dat alleen de geselecteerde pagina's worden weergegeven of dat alle geselecteerde pagina's worden verborgen.</span><span class="sxs-lookup"><span data-stu-id="0c880-132">Using this policy the Settings app can be configured to either show only the select pages, or hide all selected pages.</span></span> <span data-ttu-id="0c880-133">[Meer informatie over het configureren van de beschikbare pagina's.](settings-uri-list.md)</span><span class="sxs-lookup"><span data-stu-id="0c880-133">[Read about how to configure the pages available](settings-uri-list.md).</span></span>

<span data-ttu-id="0c880-134">Deze functie is momenteel alleen beschikbaar in [Windows Insider builds.](hololens-insider.md)</span><span class="sxs-lookup"><span data-stu-id="0c880-134">This feature is currently only available in [Windows Insider builds](hololens-insider.md).</span></span> <span data-ttu-id="0c880-135">Zorg ervoor dat apparaten voor wie u deze functie wilt gebruiken, zich op build 19041.1349+ hebben.</span><span class="sxs-lookup"><span data-stu-id="0c880-135">Ensure devices you intend to use this feature for are on build 19041.1349+.</span></span>

### <a name="wdac"></a><span data-ttu-id="0c880-136">WDAC</span><span class="sxs-lookup"><span data-stu-id="0c880-136">WDAC</span></span>

<span data-ttu-id="0c880-137">Gebruik WDAC-configuratie om te bepalen welke apps/processen zijn toegestaan/niet mogen worden gestart, ongeacht of het systeem zich in de kioskmodus of niet.</span><span class="sxs-lookup"><span data-stu-id="0c880-137">Use WDAC configuration to control which apps / processes are allowed / disallowed to be launched irrespective of whether system is in kiosk mode or not.</span></span>
[<span data-ttu-id="0c880-138">Zie ons overzicht voor WDAC.</span><span class="sxs-lookup"><span data-stu-id="0c880-138">See our overview for WDAC.</span></span>](windows-defender-application-control-wdac.md)
