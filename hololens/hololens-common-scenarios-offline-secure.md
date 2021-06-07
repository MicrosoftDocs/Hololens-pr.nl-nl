---
title: "Algemene scenario's : offline beveiligde HoloLens 2"
description: Meer informatie over het instellen van een scenario voor offline beveiligde implementatie en app-implementatie met inrichting voor HoloLens-apparaten.
keywords: HoloLens, beheer, offline, offline beveiligd
ms.date: 9/25/2020
manager: yannisle
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
appliesto:
- HoloLens 2
ms.openlocfilehash: 8828444a69d7e5d46293340ff771f97eb5eb01e6
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/25/2021
ms.locfileid: "111377776"
---
# <a name="common-scenarios--offline-secure-hololens-2"></a><span data-ttu-id="b76c4-104">Algemene scenario's : offline beveiligde HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="b76c4-104">Common Scenarios – Offline Secure HoloLens 2</span></span>

## <a name="overview"></a><span data-ttu-id="b76c4-105">Overzicht</span><span class="sxs-lookup"><span data-stu-id="b76c4-105">Overview</span></span>

<span data-ttu-id="b76c4-106">Deze handleiding bevat richtlijnen voor het toepassen van een voorbeeld van een inrichtingspakket dat een HoloLens 2 vergrendelt voor gebruik in beveiligde omgevingen met de volgende beperkingen:</span><span class="sxs-lookup"><span data-stu-id="b76c4-106">This guide provides guidance for applying a sample Provisioning Package that will lock down a HoloLens 2 for use in secure environments with the following restrictions:</span></span>

-   <span data-ttu-id="b76c4-107">Wi-Fi uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="b76c4-107">Disable WiFi.</span></span>
-   <span data-ttu-id="b76c4-108">Schakel BlueTooth uit.</span><span class="sxs-lookup"><span data-stu-id="b76c4-108">Disable BlueTooth.</span></span>
-   <span data-ttu-id="b76c4-109">Schakel Microfoons uit.</span><span class="sxs-lookup"><span data-stu-id="b76c4-109">Disable Microphones.</span></span>
-   <span data-ttu-id="b76c4-110">Hiermee voorkomt u dat inrichtingspakketten worden toegevoegd of verwijderd.</span><span class="sxs-lookup"><span data-stu-id="b76c4-110">Prevents adding or removing provisioning packages.</span></span>
-   <span data-ttu-id="b76c4-111">Geen enkele gebruiker kan een van de bovenstaande beperkte onderdelen inschakelen.</span><span class="sxs-lookup"><span data-stu-id="b76c4-111">No user can enable any of the above restricted components.</span></span>

<span data-ttu-id="b76c4-112">[![Scenario voor offline-beveiliging ](./images/deployment-guides-revised-scenario-c-01.png)](./images/deployment-guides-revised-scenario-c-01.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="b76c4-112">[ ![Offline Secure scenario](./images/deployment-guides-revised-scenario-c-01.png) ](./images/deployment-guides-revised-scenario-c-01.png#lightbox)</span></span>

## <a name="prepare"></a><span data-ttu-id="b76c4-113">Voorbereiden</span><span class="sxs-lookup"><span data-stu-id="b76c4-113">Prepare</span></span>

<span data-ttu-id="b76c4-114">Windows 10 pc installeren</span><span class="sxs-lookup"><span data-stu-id="b76c4-114">Windows 10 PC Setup</span></span>
1. <span data-ttu-id="b76c4-115">[Download het meest recente HoloLens 2 besturingssysteembestand](https://aka.ms/hololens2download) rechtstreeks naar een pc.</span><span class="sxs-lookup"><span data-stu-id="b76c4-115">[Download the latest HoloLens 2 OS file](https://aka.ms/hololens2download) directly to a PC.</span></span> 
   1. <span data-ttu-id="b76c4-116">Ondersteuning voor deze configuratie is opgenomen in build 19041.1117 en hoger.</span><span class="sxs-lookup"><span data-stu-id="b76c4-116">Support for this configuration is included in Build 19041.1117 and above.</span></span>
1. <span data-ttu-id="b76c4-117">Download/installeer het hulpprogramma Advanced Recovery Companion (ARC) [van de Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) op uw pc</span><span class="sxs-lookup"><span data-stu-id="b76c4-117">Download/Install the Advanced Recovery Companion(ARC) tool [from the Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) to your PC</span></span>
1. <span data-ttu-id="b76c4-118">Download/installeer het nieuwste [wcd-hulpprogramma (Windows Configuration Designer)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) van de Microsoft Store op uw pc.</span><span class="sxs-lookup"><span data-stu-id="b76c4-118">Download/Install the latest [Windows Configuration Designer (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) tool from the Microsoft Store to your PC.</span></span>
1. <span data-ttu-id="b76c4-119">[Download de OfflineSecureHL2_Sample map met de projectbestanden om](https://aka.ms/HoloLensDocs-SecureOfflineSample) de PPKG te bouwen.</span><span class="sxs-lookup"><span data-stu-id="b76c4-119">[Download the OfflineSecureHL2_Sample folder with the project files](https://aka.ms/HoloLensDocs-SecureOfflineSample) to build the PPKG.</span></span>
1. <span data-ttu-id="b76c4-120">Bereid uw offline [Line-Of-Business-toepassing voor op ppkg-implementatie.](app-deploy-provisioning-package.md)</span><span class="sxs-lookup"><span data-stu-id="b76c4-120">Prepare your offline [Line of Business application for PPKG deployment](app-deploy-provisioning-package.md).</span></span> 


## <a name="configure"></a><span data-ttu-id="b76c4-121">Configureren</span><span class="sxs-lookup"><span data-stu-id="b76c4-121">Configure</span></span>

<span data-ttu-id="b76c4-122">Een pakket voor beveiligde configuratie-inrichting bouwen</span><span class="sxs-lookup"><span data-stu-id="b76c4-122">Build a Secure Configuration Provisioning Package</span></span>

1. <span data-ttu-id="b76c4-123">Start het WCD-hulpprogramma op uw pc.</span><span class="sxs-lookup"><span data-stu-id="b76c4-123">Launch the WCD tool on your PC.</span></span>
1. <span data-ttu-id="b76c4-124">Selecteer **Bestand -> Project openen.**</span><span class="sxs-lookup"><span data-stu-id="b76c4-124">Select **File -> Open project**.</span></span>
  1. <span data-ttu-id="b76c4-125">Navigeer naar de locatie van de eerder OfflineSecureHL2_Sample map en selecteer: OfflineSecureHL2_Sample.icdproj.xml</span><span class="sxs-lookup"><span data-stu-id="b76c4-125">Navigate to the location of the previously saved OfflineSecureHL2_Sample folder, and select: OfflineSecureHL2_Sample.icdproj.xml</span></span>
1. <span data-ttu-id="b76c4-126">Het project wordt geopend en u hebt nu een lijst met beschikbare aanpassingen:</span><span class="sxs-lookup"><span data-stu-id="b76c4-126">The project should open and you should now have a list of Available Customizations:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b76c4-127">![Schermopname van het configuratiepakket dat is geopend in WCD](images/offline-secure-sample-wcd.png)</span><span class="sxs-lookup"><span data-stu-id="b76c4-127">![Screenshot of the configuration package open in WCD](images/offline-secure-sample-wcd.png)</span></span>

   <span data-ttu-id="b76c4-128">Configuraties die zijn ingesteld in dit inrichtingspakket:</span><span class="sxs-lookup"><span data-stu-id="b76c4-128">Configurations set in this provisioning package:</span></span>
   
   |     <span data-ttu-id="b76c4-129">Item</span><span class="sxs-lookup"><span data-stu-id="b76c4-129">Item</span></span>                                                |     <span data-ttu-id="b76c4-130">Instelling</span><span class="sxs-lookup"><span data-stu-id="b76c4-130">Setting</span></span>                       |     <span data-ttu-id="b76c4-131">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="b76c4-131">Description</span></span>                                                                                                                    |
   |---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
   |     <span data-ttu-id="b76c4-132">Accounts/gebruikers</span><span class="sxs-lookup"><span data-stu-id="b76c4-132">Accounts / Users</span></span>                                    |     <span data-ttu-id="b76c4-133">Lokaal gebruikersnaam & wachtwoord</span><span class="sxs-lookup"><span data-stu-id="b76c4-133">Local User Name & Password</span></span>    |     <span data-ttu-id="b76c4-134">Voor deze offlineapparaten moeten één gebruikersnaam en wachtwoord worden ingesteld en gedeeld door alle gebruikers van het apparaat.</span><span class="sxs-lookup"><span data-stu-id="b76c4-134">For these offline devices, a single user name and password will need to be set and shared by all users of the device.</span></span>          |
   |     <span data-ttu-id="b76c4-135">First Experience / HoloLens / SkipCalibration</span><span class="sxs-lookup"><span data-stu-id="b76c4-135">First Experience / HoloLens / SkipCalibration</span></span>       |     <span data-ttu-id="b76c4-136">Waar</span><span class="sxs-lookup"><span data-stu-id="b76c4-136">True</span></span>                          |     <span data-ttu-id="b76c4-137">Overslaan van kalibratie tijdens de eerste installatie van het apparaat alleen</span><span class="sxs-lookup"><span data-stu-id="b76c4-137">Skips calibration during initial device setup only</span></span>                                                                             |
   |     <span data-ttu-id="b76c4-138">First Experience /HoloLens/SkipTraining</span><span class="sxs-lookup"><span data-stu-id="b76c4-138">First Experience / HoloLens / SkipTraining</span></span>          |     <span data-ttu-id="b76c4-139">Waar</span><span class="sxs-lookup"><span data-stu-id="b76c4-139">True</span></span>                          |     <span data-ttu-id="b76c4-140">Apparaattraining overslaan tijdens de eerste installatie van het apparaat</span><span class="sxs-lookup"><span data-stu-id="b76c4-140">Skips device training during initial device setup</span></span>                                                                              |
   |     <span data-ttu-id="b76c4-141">Eerste ervaring / HoloLens / Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="b76c4-141">First Experience / HoloLens / WiFi</span></span>                  |     <span data-ttu-id="b76c4-142">Waar</span><span class="sxs-lookup"><span data-stu-id="b76c4-142">True</span></span>                          |     <span data-ttu-id="b76c4-143">Slaat de Wi-Fi over tijdens de eerste configuratie van het apparaat</span><span class="sxs-lookup"><span data-stu-id="b76c4-143">Skips Wi-Fi config during initial device setup</span></span>                                                                                 |
   |     <span data-ttu-id="b76c4-144">Beleid/Connectiviteit/AllowBluetooth</span><span class="sxs-lookup"><span data-stu-id="b76c4-144">Policies/Connectivity/AllowBluetooth</span></span>                |     <span data-ttu-id="b76c4-145">Nee</span><span class="sxs-lookup"><span data-stu-id="b76c4-145">No</span></span>                            |     <span data-ttu-id="b76c4-146">Bluetooth uitschakelen</span><span class="sxs-lookup"><span data-stu-id="b76c4-146">Disables Bluetooth</span></span>                                                                                                             |
   |     <span data-ttu-id="b76c4-147">Beleid/Ervaring/AllowCortana</span><span class="sxs-lookup"><span data-stu-id="b76c4-147">Policies/Experience/AllowCortana</span></span>                    |     <span data-ttu-id="b76c4-148">Nee</span><span class="sxs-lookup"><span data-stu-id="b76c4-148">No</span></span>                            |     <span data-ttu-id="b76c4-149">Hiermee schakelt u Cortana uit (om mogelijke problemen te voorkomen omdat de microfoons zijn uitgeschakeld)</span><span class="sxs-lookup"><span data-stu-id="b76c4-149">Disables Cortana (to eliminate potential problems since the microphones are disabled)</span></span>                                          |
   |     <span data-ttu-id="b76c4-150">Policies/MixedReality/MicrophoneDisabled</span><span class="sxs-lookup"><span data-stu-id="b76c4-150">Policies/MixedReality/MicrophoneDisabled</span></span>            |     <span data-ttu-id="b76c4-151">Ja</span><span class="sxs-lookup"><span data-stu-id="b76c4-151">Yes</span></span>                           |     <span data-ttu-id="b76c4-152">Microfoon uitschakelen</span><span class="sxs-lookup"><span data-stu-id="b76c4-152">Disables Microphone</span></span>                                                                                                            |
   |     <span data-ttu-id="b76c4-153">Policies/Privacy/LetAppsAccessLocation</span><span class="sxs-lookup"><span data-stu-id="b76c4-153">Policies/Privacy/LetAppsAccessLocation</span></span>              |     <span data-ttu-id="b76c4-154">Weigeren forcen</span><span class="sxs-lookup"><span data-stu-id="b76c4-154">Force deny</span></span>                    |     <span data-ttu-id="b76c4-155">Hiermee voorkomt u dat apps toegang proberen te krijgen tot locatiegegevens (om mogelijke problemen te voorkomen omdat het bijhouden van de locatie is uitgeschakeld)</span><span class="sxs-lookup"><span data-stu-id="b76c4-155">Prevents Apps from trying to access Location data (to eliminate potential problems since the Location tracking is disabled)</span></span>    |
   |     <span data-ttu-id="b76c4-156">Policies/Privacy/LetAppsAccessMicrophone</span><span class="sxs-lookup"><span data-stu-id="b76c4-156">Policies/Privacy/LetAppsAccessMicrophone</span></span>            |     <span data-ttu-id="b76c4-157">Weigeren forcen</span><span class="sxs-lookup"><span data-stu-id="b76c4-157">Force deny</span></span>                    |     <span data-ttu-id="b76c4-158">Hiermee voorkomt u dat apps toegang proberen te krijgen tot microfoons (om mogelijke problemen te voorkomen omdat de microfoons zijn uitgeschakeld)</span><span class="sxs-lookup"><span data-stu-id="b76c4-158">Prevents Apps from trying to access Microphones (to eliminate potential problems since the Microphones are disabled)</span></span>           |
   |     <span data-ttu-id="b76c4-159">Policies/Security/AllowAddProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="b76c4-159">Policies/Security/AllowAddProvisioningPackage</span></span>       |     <span data-ttu-id="b76c4-160">Nee</span><span class="sxs-lookup"><span data-stu-id="b76c4-160">No</span></span>                            |     <span data-ttu-id="b76c4-161">Hiermee voorkomt u dat iemand inrichtingspakketten toevoegt die mogelijk proberen vergrendeld beleid te overschrijven.</span><span class="sxs-lookup"><span data-stu-id="b76c4-161">Prevents anyone from adding provisioning packages that might attempt to override locked down policies.</span></span>                         |
   |     <span data-ttu-id="b76c4-162">Policies/Security/AllowRemoveProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="b76c4-162">Policies/Security/AllowRemoveProvisioningPackage</span></span>    |     <span data-ttu-id="b76c4-163">Nee</span><span class="sxs-lookup"><span data-stu-id="b76c4-163">No</span></span>                            |     <span data-ttu-id="b76c4-164">Hiermee voorkomt u dat iemand dit vergrendelde inrichtingspakket kan verwijderen.</span><span class="sxs-lookup"><span data-stu-id="b76c4-164">Prevents anyone from removing this locked down provisioning package.</span></span>                                                           |
   |     <span data-ttu-id="b76c4-165">Policies/System/AllowLocation</span><span class="sxs-lookup"><span data-stu-id="b76c4-165">Policies/System/AllowLocation</span></span>                       |     <span data-ttu-id="b76c4-166">Nee</span><span class="sxs-lookup"><span data-stu-id="b76c4-166">No</span></span>                            |     <span data-ttu-id="b76c4-167">Hiermee voorkomt u dat het apparaat locatiegegevens probeert bij te houden.</span><span class="sxs-lookup"><span data-stu-id="b76c4-167">Prevents the device from trying to track location data.</span></span>                                                                        |
   |     <span data-ttu-id="b76c4-168">Beleid/Wi-Fi/AllowWiFi</span><span class="sxs-lookup"><span data-stu-id="b76c4-168">Policies/WiFi/AllowWiFi</span></span>                             |     <span data-ttu-id="b76c4-169">Nee</span><span class="sxs-lookup"><span data-stu-id="b76c4-169">No</span></span>                            |     <span data-ttu-id="b76c4-170">Schakelt Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="b76c4-170">Disables Wi-Fi</span></span>                                                                                                                 |

1. <span data-ttu-id="b76c4-171">Selecteer onder Runtime-instellingen **de optie Accounts /Users/UserName: Holo/Password.**</span><span class="sxs-lookup"><span data-stu-id="b76c4-171">Under Runtime Settings, Select **Accounts / Users / UserName: Holo / Password**.</span></span>

   <span data-ttu-id="b76c4-172">Noteer het wachtwoord en stel het indien gewenst opnieuw in.</span><span class="sxs-lookup"><span data-stu-id="b76c4-172">Note the password and reset if desired.</span></span>

1. <span data-ttu-id="b76c4-173">Navigeer naar UniversalAppInstall/UserContextApp en configureer de [LOB-app](app-deploy-provisioning-package.md) die u op deze apparaten gaat implementeren.</span><span class="sxs-lookup"><span data-stu-id="b76c4-173">Navigate to UniversalAppInstall / UserContextApp and [configure the LOB app](app-deploy-provisioning-package.md) you will be deploying to these devices.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b76c4-174">![Schermopname van waar u uw app toevoegt in WCD.](images/offline-secure-sample-wcd-usercontextapp2.png)</span><span class="sxs-lookup"><span data-stu-id="b76c4-174">![Screenshot of where to add your app in WCD.](images/offline-secure-sample-wcd-usercontextapp2.png)</span></span>

1. <span data-ttu-id="b76c4-175">Als u klaar is, selecteert u de knop Exporteren en volgt u alle prompts totdat uw inrichtingspakket is gemaakt.</span><span class="sxs-lookup"><span data-stu-id="b76c4-175">Once complete, select the “Export” button and follow all prompts until your provisioning package is created.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b76c4-176">![Schermopname van de knop Exporteren voor dit pakket in WCD.](images/offline-secure-sample-wcd-export.png)</span><span class="sxs-lookup"><span data-stu-id="b76c4-176">![Screenshot of the Export button for this package in WCD.](images/offline-secure-sample-wcd-export.png)</span></span>

## <a name="deploy"></a><span data-ttu-id="b76c4-177">Implementeren</span><span class="sxs-lookup"><span data-stu-id="b76c4-177">Deploy</span></span>

1. <span data-ttu-id="b76c4-178">Sluit de HL2 aan op uw Windows 10 pc via een USB-kabel.</span><span class="sxs-lookup"><span data-stu-id="b76c4-178">Connect the HL2 to your Windows 10 PC via USB cable.</span></span>
1. <span data-ttu-id="b76c4-179">Start het ARC-hulpprogramma en selecteer **HoloLens 2**</span><span class="sxs-lookup"><span data-stu-id="b76c4-179">Launch the ARC tool and select **HoloLens 2**</span></span>

   ![HoloLens 2 eerste scherm nieuwe reflash maken](images/ARC2.png)

1. <span data-ttu-id="b76c4-181">Selecteer in het volgende scherm **Handmatige pakketselectie.**</span><span class="sxs-lookup"><span data-stu-id="b76c4-181">On the next screen select **Manual package selection**.</span></span>

   ![HoloLens 2 ARC-infoscherm](images/arc_device_info.png)

1. <span data-ttu-id="b76c4-183">Navigeer naar het eerder gedownloade FFU-bestand en selecteer **Openen.**</span><span class="sxs-lookup"><span data-stu-id="b76c4-183">Navigate to the previously downloaded .ffu file, and select **Open**.</span></span>
1. <span data-ttu-id="b76c4-184">Selecteer op de pagina Waarschuwing **doorgaan.**</span><span class="sxs-lookup"><span data-stu-id="b76c4-184">At the Warning page select **Continue**.</span></span>

   ![HoloLens 2 ARC-waarschuwingsscherm](images/arc_warning.png)

1. <span data-ttu-id="b76c4-186">Wacht tot het ARC-hulpprogramma de installatie van HoloLens 2 besturingssysteem heeft voltooid.</span><span class="sxs-lookup"><span data-stu-id="b76c4-186">Wait for the ARC tool to complete the HoloLens 2 OS install.</span></span>
1. <span data-ttu-id="b76c4-187">Nadat het apparaat de installatie heeft voltooid en opnieuw is opgeslagen, gaat u vanaf uw pc naar Verkenner en kopieert u het eerder opgeslagen PPKG-bestand naar de map van het apparaat.</span><span class="sxs-lookup"><span data-stu-id="b76c4-187">Once the device completes the install and boots back up, from your PC navigate to File Explorer and copy the previously saved PPKG file over to the device folder.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b76c4-188">![PPKG-bestand op pc in het venster Bestandenverkenner.](images/offline-secure-file-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="b76c4-188">![PPKG file on PC in File Explorer window.](images/offline-secure-file-explorer.png)</span></span>

1. <span data-ttu-id="b76c4-189">Druk in HoloLens 2 op de volgende knopcombinatie om het inrichtingspakket  uit te voeren: tik tegelijkertijd op **Volume** omlaag en aan/uit.</span><span class="sxs-lookup"><span data-stu-id="b76c4-189">On the HoloLens 2, press the following button combo to run the Provisioning Package: Tap **Volume Down** and **Power Button** at the same time.</span></span>
1. <span data-ttu-id="b76c4-190">U wordt gevraagd het inrichtingspakket toe te passen. Selecteer **Bevestigen**</span><span class="sxs-lookup"><span data-stu-id="b76c4-190">You will be prompted to apply the Provisioning Package, select **Confirm**</span></span>
1. <span data-ttu-id="b76c4-191">Zodra het inrichtingspakket is voltooid, selecteert u **OK**.</span><span class="sxs-lookup"><span data-stu-id="b76c4-191">Once the provisioning package completes select **OK**.</span></span>
1. <span data-ttu-id="b76c4-192">Vervolgens wordt u gevraagd u aan te melden bij het apparaat met het gedeelde lokale account en wachtwoord.</span><span class="sxs-lookup"><span data-stu-id="b76c4-192">You should then be prompted to sign into the device with the shared local account and password.</span></span>

## <a name="maintain"></a><span data-ttu-id="b76c4-193">Onderhouden</span><span class="sxs-lookup"><span data-stu-id="b76c4-193">Maintain</span></span>

<span data-ttu-id="b76c4-194">Met deze configuratie wordt het aanbevolen om het bovenstaande proces opnieuw op te starten en het apparaat met het ARC-hulpprogramma te reflashen en een nieuwe PPKG toe te passen om eventuele updates aan te brengen in het besturingssysteem en/of de toepassing(en).</span><span class="sxs-lookup"><span data-stu-id="b76c4-194">With this configuration, it is recommended to restart the process above and reflash the device with the ARC tool and apply a new PPKG to make any updates to the OS and/or application(s).</span></span>
