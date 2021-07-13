---
title: Windows Defender Toepassingsbeheer - WDAC
description: Overzicht van wat Windows Defender Toepassingsbeheer is en hoe u dit kunt gebruiken voor het beheren HoloLens mixed reality apparaten.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/26/2020
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: a27a16913873c5245f734dbe084eb2b7ed007c20
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639927"
---
# <a name="windows-defender-application-control---wdac"></a><span data-ttu-id="caf86-103">Windows Defender Toepassingsbeheer - WDAC</span><span class="sxs-lookup"><span data-stu-id="caf86-103">Windows Defender Application Control - WDAC</span></span>

<span data-ttu-id="caf86-104">Met WDAC kan een IT-beheerder zijn apparaten configureren om het starten van apps op apparaten te blokkeren.</span><span class="sxs-lookup"><span data-stu-id="caf86-104">WDAC allows an IT Admin to configure their devices to block the launch of apps on devices.</span></span> <span data-ttu-id="caf86-105">Dit verschilt van de apparaatbeperkingsmethoden, zoals de kioskmodus, waarbij de gebruiker een gebruikersinterface krijgt te zien die de apps op het apparaat verbergt, maar nog steeds kan worden gestart.</span><span class="sxs-lookup"><span data-stu-id="caf86-105">This is different than methods of device restriction such as Kiosk mode, where  the user is presented with a UI that hides the apps on the device but they can still be launched.</span></span> <span data-ttu-id="caf86-106">Terwijl WDAC is geïmplementeerd, zijn de apps nog steeds zichtbaar in de lijst Alle apps, maar WDAC voorkomt dat deze apps en processen kunnen worden gestart door de gebruiker van het apparaat.</span><span class="sxs-lookup"><span data-stu-id="caf86-106">While WDAC is implemented, the apps are still visible in the All Apps list but WDAC stops those apps and processes from being able to be launched by the device user.</span></span>

<span data-ttu-id="caf86-107">Aan een apparaat kan meer dan één WDAC-beleid worden toegewezen.</span><span class="sxs-lookup"><span data-stu-id="caf86-107">A device may be assigned more than one WDAC policy.</span></span> <span data-ttu-id="caf86-108">Als er meerdere WDAC-beleidsregels zijn ingesteld op een systeem, worden de meest beperkende beleidsregels van kracht.</span><span class="sxs-lookup"><span data-stu-id="caf86-108">If multiple WDAC policies are set on a system, most restrictive ones take effect.</span></span> 

> [!NOTE]
> <span data-ttu-id="caf86-109">Wanneer eindgebruikers proberen een app te starten die is geblokkeerd door WDAC, ontvangen ze op HoloLens geen melding dat ze die app niet kunnen starten.</span><span class="sxs-lookup"><span data-stu-id="caf86-109">When end users attempt to launch an app that is blocked by WDAC, on HoloLens they will not receive a notification about not being able to launch that app.</span></span>

<span data-ttu-id="caf86-110">Hier volgt een handleiding voor gebruikers voor meer informatie over het gebruik van [WDAC](/mem/intune/configuration/custom-profile-hololens)en Windows PowerShell voor het toestaan of blokkeren van apps op HoloLens 2-apparaten met Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="caf86-110">The following is a guide for users to learn how to [use WDAC and Windows PowerShell to allow or block apps on HoloLens 2 devices with Microsoft Intune](/mem/intune/configuration/custom-profile-hololens).</span></span>

<span data-ttu-id="caf86-111">Wanneer gebruikers zoeken naar apps die zijn geïnstalleerd op hun Windows 10 pc met behulp van de eerste voorbeeldstap, moeten ze mogelijk enkele pogingen doen om de resultaten te beperken.</span><span class="sxs-lookup"><span data-stu-id="caf86-111">When users search for apps installed on their Windows 10 PC using the first example step, they may need to make a few attempts to narrow down the results.</span></span>

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

<span data-ttu-id="caf86-112">Als u de volledige naam van het pakket niet weet, moet u mogelijk 'Get-AppxPackage -name YourBestGuess' een paar keer uitvoeren om het te \* \* vinden.</span><span class="sxs-lookup"><span data-stu-id="caf86-112">If you don’t know the full name of the package, you may need to run ‘Get-AppxPackage -name \*YourBestGuess\*’ a few times to find it.</span></span> <span data-ttu-id="caf86-113">Wanneer u de naam hebt, voer dan '$package 1 = Get-AppxPackage -name Actual.PackageName' uit</span><span class="sxs-lookup"><span data-stu-id="caf86-113">Then once you have the name run ‘$package1 = Get-AppxPackage -name Actual.PackageName‘</span></span>

<span data-ttu-id="caf86-114">Als u bijvoorbeeld het volgende Microsoft Edge, wordt er meer dan één resultaat weergegeven, maar uit die lijst kunt u zien dat de volledige naam die u nodig hebt Microsoft.MicrosoftEdge is.</span><span class="sxs-lookup"><span data-stu-id="caf86-114">For example running the following for Microsoft Edge will return more than one result, but from that list you can identify that the full name you need is Microsoft.MicrosoftEdge.</span></span>

```powershell
Get-AppxPackage -name *edge*
``` 

## <a name="package-family-names-for-apps-on-hololens"></a><span data-ttu-id="caf86-115">Familienamen van pakketten voor apps op HoloLens</span><span class="sxs-lookup"><span data-stu-id="caf86-115">Package Family Names for apps on HoloLens</span></span>

<span data-ttu-id="caf86-116">In de bovenstaande handleiding kunt u handmatig de newPolicy.xml en regels toevoegen voor toepassingen die alleen zijn geïnstalleerd op HoloLens met de familienamen van pakketten.</span><span class="sxs-lookup"><span data-stu-id="caf86-116">In the guide linked above, you can manually edit newPolicy.xml and add rules for applications that are only installed on HoloLens with their package family names.</span></span> <span data-ttu-id="caf86-117">Soms zijn er apps die u kunt gebruiken en die zich niet op uw desktop-pc die u aan het beleid wilt toevoegen.</span><span class="sxs-lookup"><span data-stu-id="caf86-117">Sometimes there are apps you may use to use that are not on your desktop PC that you wish to add to policy.</span></span>

<span data-ttu-id="caf86-118">Hier is een lijst met veelgebruikte en In-Box apps voor HoloLens 2 apparaten.</span><span class="sxs-lookup"><span data-stu-id="caf86-118">Here is a list of commonly used and In-Box apps for HoloLens 2 devices.</span></span>

| <span data-ttu-id="caf86-119">App-naam</span><span class="sxs-lookup"><span data-stu-id="caf86-119">App Name</span></span>                   | <span data-ttu-id="caf86-120">Naam pakketfamilie</span><span class="sxs-lookup"><span data-stu-id="caf86-120">Package Family Name</span></span>                                |
|----------------------------|----------------------------------------------------|
| <span data-ttu-id="caf86-121">3D-viewer</span><span class="sxs-lookup"><span data-stu-id="caf86-121">3D Viewer</span></span>                  | <span data-ttu-id="caf86-122">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="caf86-122">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="caf86-123">App-installatieprogramma</span><span class="sxs-lookup"><span data-stu-id="caf86-123">App Installer</span></span>              | <span data-ttu-id="caf86-124">Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="caf86-124">Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</sup></span></span>         |
| <span data-ttu-id="caf86-125">Kalender</span><span class="sxs-lookup"><span data-stu-id="caf86-125">Calendar</span></span>                   | <span data-ttu-id="caf86-126">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="caf86-126">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="caf86-127">Camera</span><span class="sxs-lookup"><span data-stu-id="caf86-127">Camera</span></span>                     | <span data-ttu-id="caf86-128">HoloCamera_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="caf86-128">HoloCamera_cw5n1h2txyewy</span></span>                           |
| <span data-ttu-id="caf86-129">Cortana</span><span class="sxs-lookup"><span data-stu-id="caf86-129">Cortana</span></span>                    | <span data-ttu-id="caf86-130">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="caf86-130">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span></span>              |
| <span data-ttu-id="caf86-131">Dynamics 365 Guides</span><span class="sxs-lookup"><span data-stu-id="caf86-131">Dynamics 365 Guides</span></span>        | <span data-ttu-id="caf86-132">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="caf86-132">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="caf86-133">Dynamics 365 Remote Assist</span><span class="sxs-lookup"><span data-stu-id="caf86-133">Dynamics 365 Remote Assist</span></span> | <span data-ttu-id="caf86-134">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="caf86-134">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span></span>      |
| <span data-ttu-id="caf86-135">Feedback-hub</span><span class="sxs-lookup"><span data-stu-id="caf86-135">Feedback Hub</span></span>               | <span data-ttu-id="caf86-136">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="caf86-136">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="caf86-137">Verkenner</span><span class="sxs-lookup"><span data-stu-id="caf86-137">File Explorer</span></span>              | <span data-ttu-id="caf86-138">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="caf86-138">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span></span> |
| <span data-ttu-id="caf86-139">Mail</span><span class="sxs-lookup"><span data-stu-id="caf86-139">Mail</span></span>                       | <span data-ttu-id="caf86-140">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="caf86-140">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="caf86-141">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="caf86-141">Microsoft Store</span></span>            | <span data-ttu-id="caf86-142">Microsoft.WindowsStore_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="caf86-142">Microsoft.WindowsStore_8wekyb3d8bbwe</span></span>               |
| <span data-ttu-id="caf86-143">Films & TV</span><span class="sxs-lookup"><span data-stu-id="caf86-143">Movies & TV</span></span>                | <span data-ttu-id="caf86-144">Microsoft.ZuneVideo_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="caf86-144">Microsoft.ZuneVideo_8wekyb3d8bbwe</span></span>                  |
| <span data-ttu-id="caf86-145">OneDrive</span><span class="sxs-lookup"><span data-stu-id="caf86-145">OneDrive</span></span>                   | <span data-ttu-id="caf86-146">microsoft.microsoftskydrive_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="caf86-146">microsoft.microsoftskydrive_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="caf86-147">Foto's</span><span class="sxs-lookup"><span data-stu-id="caf86-147">Photos</span></span>                     | <span data-ttu-id="caf86-148">Microsoft. Windows. Photos_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="caf86-148">Microsoft.Windows.Photos_8wekyb3d8bbwe</span></span>             |
| <span data-ttu-id="caf86-149">Instellingen</span><span class="sxs-lookup"><span data-stu-id="caf86-149">Settings</span></span>                   | <span data-ttu-id="caf86-150">HolographicSystemSettings_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="caf86-150">HolographicSystemSettings_cw5n1h2txyewy</span></span>            |
| <span data-ttu-id="caf86-151">Tips</span><span class="sxs-lookup"><span data-stu-id="caf86-151">Tips</span></span>                       | <span data-ttu-id="caf86-152">Microsoft.HoloLensTips_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="caf86-152">Microsoft.HoloLensTips_8wekyb3d8bbwe</span></span>               |

- <span data-ttu-id="caf86-153">1: als u App-installatieprogramma blokkeert, wordt alleen de App-installatieprogramma-app geblokkeerd en niet apps die zijn geïnstalleerd vanuit andere bronnen, zoals de Microsoft Store of van uw MDM-oplossing.</span><span class="sxs-lookup"><span data-stu-id="caf86-153">1 - Blocking App Installer will only block the App Installer app, and not apps installed from other sources such as the Microsoft Store or from your MDM solution.</span></span>

### <a name="how-to-find-a-package-family-name"></a><span data-ttu-id="caf86-154">Een pakketfamilienaam zoeken</span><span class="sxs-lookup"><span data-stu-id="caf86-154">How to find a Package Family Name</span></span>

<span data-ttu-id="caf86-155">Als een app niet in deze lijst staat, kan een gebruiker Apparaatportal gebruiken, verbonden met een HoloLens 2 die de app heeft geïnstalleerd, om de PackageRelativeID te bepalen en van hieruit de PackageFamilyName op te halen.</span><span class="sxs-lookup"><span data-stu-id="caf86-155">If an app is not on this list, then a user may use Device Portal, connected to a HoloLens 2 that has installed the app wished to be blocked, to determine the PackageRelativeID and from there get the PackageFamilyName.</span></span>

1. <span data-ttu-id="caf86-156">Installeer de app op HoloLens 2 apparaat.</span><span class="sxs-lookup"><span data-stu-id="caf86-156">Install the app on your HoloLens 2 device.</span></span> 
1. <span data-ttu-id="caf86-157">Open Instellingen -> Updates & Security -> For developers en schakel de **ontwikkelaarsmodus** en vervolgens **Apparaatportal in.**</span><span class="sxs-lookup"><span data-stu-id="caf86-157">Open Settings -> Updates & Security -> For developers, and enable **Developer mode** and then **Device portal**.</span></span> 
    1. <span data-ttu-id="caf86-158">Lees hier meer informatie over de installatie [en het gebruik van de apparaatportal.](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)</span><span class="sxs-lookup"><span data-stu-id="caf86-158">More more details instructions read more about [setup and use of device portal here](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).</span></span>
1. <span data-ttu-id="caf86-159">Zodra Apparaatportal is verbonden, gaat u naar **Weergaven en** vervolgens **naar Apps.**</span><span class="sxs-lookup"><span data-stu-id="caf86-159">Once Device Portal is connected, navigate to **Views** then **Apps**.</span></span> 
1. <span data-ttu-id="caf86-160">Gebruik in het deelvenster Geïnstalleerde apps de vervolgkeuze selecteren om de geïnstalleerde app te selecteren.</span><span class="sxs-lookup"><span data-stu-id="caf86-160">Within the Installed Apps panel, use the dropdown to select the installed app.</span></span> 
1. <span data-ttu-id="caf86-161">Zoek de PackageRelativeID.</span><span class="sxs-lookup"><span data-stu-id="caf86-161">Locate the PackageRelativeID.</span></span> 
1. <span data-ttu-id="caf86-162">Kopieer app-tekens vóór de . Deze tekens zijn uw PackageFamilyName.</span><span class="sxs-lookup"><span data-stu-id="caf86-162">Copy app characters before the !, these characters will be your PackageFamilyName.</span></span>


