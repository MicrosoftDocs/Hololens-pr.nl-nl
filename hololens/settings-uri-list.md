---
title: Zichtbaarheid van pagina-instellingen
description: Blijf op de hoogte van onze lijst met ondersteunde URI's voor PageVisibilityList en Guide on HoloLens mixed reality apparaten.
author: evmill
ms.author: v-evmill
ms.date: 10/13/2020
ms.topic: article
keywords: hololens, hololens 2, toegewezen toegang, kiosk, instellingenpagina
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: widuff
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: d28994d911532a940d82756aa45609571ee80ac3
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924329"
---
# <a name="page-settings-visibility"></a><span data-ttu-id="520db-104">Zichtbaarheid van pagina-instellingen</span><span class="sxs-lookup"><span data-stu-id="520db-104">Page Settings Visibility</span></span>

<span data-ttu-id="520db-105">Een van de beheerbare functies voor HoloLens-apparaten is het gebruik van het beleid [Instellingen/PaginaVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) om de pagina's in de app Instellingen te beperken.</span><span class="sxs-lookup"><span data-stu-id="520db-105">One of the manageable features for HoloLens devices is using the [Settings/PageVisibilityList policy](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) to restrict the pages seen within the Settings app.</span></span> <span data-ttu-id="520db-106">PageVisibilityList is een beleid waarmee IT-beheerders kunnen voorkomen dat specifieke pagina's in de app Systeeminstellingen zichtbaar of toegankelijk zijn, of om dit te doen voor alle pagina's behalve de pagina's die zijn opgegeven.</span><span class="sxs-lookup"><span data-stu-id="520db-106">PageVisibilityList is a policy that allows IT Admins to either prevent specific pages in the System Settings app from being visible or accessible, or to do so for all pages except those specified.</span></span>

> [!NOTE]
> <span data-ttu-id="520db-107">Deze functie is alleen beschikbaar in [Windows Holographic, versie 20H2](hololens-release-notes.md#windows-holographic-version-20h2) of hoger voor HoloLens 2 apparaten.</span><span class="sxs-lookup"><span data-stu-id="520db-107">This feature is only avalible in [Windows Holographic, version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) or higher for HoloLens 2 devices.</span></span> <span data-ttu-id="520db-108">Zorg ervoor dat de apparaten voor wie u dit wilt gebruiken, zijn bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="520db-108">Please ensure devices you intend to use this for are updated.</span></span>

<span data-ttu-id="520db-109">In het volgende voorbeeld ziet u een beleid dat alleen toegang toestaat tot de about- en bluetooth-pagina's, die respectievelijk URI 'ms-settings:network-wifi' en 'ms-settings:bluetooth' hebben:</span><span class="sxs-lookup"><span data-stu-id="520db-109">The following example illustrates a policy that would allow access only to the about and bluetooth pages, which have URI "ms-settings:network-wifi" and "ms-settings:bluetooth" respectively:</span></span>
- `showonly:network-wifi;network-proxy;bluetooth`

<span data-ttu-id="520db-110">Dit instellen via een inrichtingspakket:</span><span class="sxs-lookup"><span data-stu-id="520db-110">To set this via a Provisioning Package:</span></span>

1. <span data-ttu-id="520db-111">Navigeer tijdens het maken van uw pakket in Windows Configuration Designer **naar Beleidsregels > Instellingen > PageVisibilityList**</span><span class="sxs-lookup"><span data-stu-id="520db-111">While creating your package in Windows Configuration Designer navigate to **Policies > Settings > PageVisibilityList**</span></span>
1. <span data-ttu-id="520db-112">Voer de tekenreeks in: **`showonly:network-wifi;network-proxy;bluetooth`**</span><span class="sxs-lookup"><span data-stu-id="520db-112">Enter the string: **`showonly:network-wifi;network-proxy;bluetooth`**</span></span>
1. <span data-ttu-id="520db-113">Exporteert u uw inrichtingspakket.</span><span class="sxs-lookup"><span data-stu-id="520db-113">Export your Provisioning Package.</span></span>
1. <span data-ttu-id="520db-114">Pas het pakket toe op uw apparaat.</span><span class="sxs-lookup"><span data-stu-id="520db-114">Apply the package to your device.</span></span>
<span data-ttu-id="520db-115">Ga naar deze pagina voor meer informatie over het maken en toepassen van een [inrichtingspakket.](hololens-provisioning.md)</span><span class="sxs-lookup"><span data-stu-id="520db-115">For full details on how to create and apply a provisioning package visit [this page](hololens-provisioning.md).</span></span>

<span data-ttu-id="520db-116">U kunt dit doen via Intune met oma-URI:</span><span class="sxs-lookup"><span data-stu-id="520db-116">This can be done via Intune using OMA-URI:</span></span>

1. <span data-ttu-id="520db-117">Maak een **aangepast beleid.**</span><span class="sxs-lookup"><span data-stu-id="520db-117">Create a **Custom policy**.</span></span>
1. <span data-ttu-id="520db-118">Gebruik de tekenreeks bij het instellen van de OMA-URI: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**</span><span class="sxs-lookup"><span data-stu-id="520db-118">When setting the OMA-URI use the string: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**</span></span>
1. <span data-ttu-id="520db-119">Kies bij het selecteren van de gegevens de optie **Tekenreeks:**</span><span class="sxs-lookup"><span data-stu-id="520db-119">When selecting the data pick choose: **String**</span></span>
1. <span data-ttu-id="520db-120">Wanneer u de waarde typt, gebruikt u: **`showonly:network-wifi;network-proxy;bluetooth`**</span><span class="sxs-lookup"><span data-stu-id="520db-120">When typing the value use: **`showonly:network-wifi;network-proxy;bluetooth`**</span></span>
1. <span data-ttu-id="520db-121">Zorg ervoor dat u de aangepaste apparaatconfiguratie toewijst aan een groep waarin het apparaat is bedoeld.</span><span class="sxs-lookup"><span data-stu-id="520db-121">Make sure to assign the custom device configuration to a group the device is intended to be in.</span></span>

<span data-ttu-id="520db-122">Zie [HoloLens MDM-configuratie](hololens-mdm-configure.md) voor meer informatie over Intune-groepen en apparaatconfiguraties.</span><span class="sxs-lookup"><span data-stu-id="520db-122">See [HoloLens MDM configuration](hololens-mdm-configure.md) for more information on Intune groups and device configurations.</span></span>

<span data-ttu-id="520db-123">Ongeacht de gekozen methode ontvangt uw apparaat nu de wijzigingen en krijgen gebruikers de volgende instellingen-app te zien.</span><span class="sxs-lookup"><span data-stu-id="520db-123">Regardless of method chosen your device should now receive the changes and users will be presented with the following Settings App.</span></span>

![Schermopname van actieve uren die worden gewijzigd in de app Instellingen](images/hololens-page-visibility-list.jpg)

<span data-ttu-id="520db-125">Als u de app-pagina's Instellingen wilt configureren om uw eigen selectie pagina's weer te geven of te verbergen, bekijkt u de instellingen-URI's die beschikbaar zijn op HoloLens.</span><span class="sxs-lookup"><span data-stu-id="520db-125">To configure the Settings app pages to show or hide your own selection of pages, take a look at the Settings URIs available on HoloLens.</span></span>

## <a name="settings-uris"></a><span data-ttu-id="520db-126">Instellingen-URI's</span><span class="sxs-lookup"><span data-stu-id="520db-126">Settings URIs</span></span>

<span data-ttu-id="520db-127">HoloLens-apparaten Windows 10 apparaten hebben een andere selectie pagina's in de app Instellingen.</span><span class="sxs-lookup"><span data-stu-id="520db-127">HoloLens devices and Windows 10 devices have a different selection of pages within the Settings app.</span></span> <span data-ttu-id="520db-128">Op deze pagina vindt u alleen de instellingen die bestaan op HoloLens.</span><span class="sxs-lookup"><span data-stu-id="520db-128">On this page, you will find only the settings that exist on HoloLens.</span></span>

### <a name="accounts"></a><span data-ttu-id="520db-129">Accounts</span><span class="sxs-lookup"><span data-stu-id="520db-129">Accounts</span></span>
| <span data-ttu-id="520db-130">Pagina Instellingen</span><span class="sxs-lookup"><span data-stu-id="520db-130">Settings page</span></span>           | <span data-ttu-id="520db-131">URI</span><span class="sxs-lookup"><span data-stu-id="520db-131">URI</span></span>                                            |
|-------------------------|------------------------------------------------|
| <span data-ttu-id="520db-132">Werk- of schoolaccount openen</span><span class="sxs-lookup"><span data-stu-id="520db-132">Access work or school</span></span> | `ms-settings:workplace`                         |
| <span data-ttu-id="520db-133">Iris-inschrijving</span><span class="sxs-lookup"><span data-stu-id="520db-133">Iris Enrollment</span></span>       | `ms-settings:signinoptions-launchirisenrollment` |
| <span data-ttu-id="520db-134">Aanmeldingsopties</span><span class="sxs-lookup"><span data-stu-id="520db-134">Sign In Options</span></span>         | ` ms-settings:signinoptions `                   |

### <a name="apps"></a><span data-ttu-id="520db-135">Apps</span><span class="sxs-lookup"><span data-stu-id="520db-135">Apps</span></span>
| <span data-ttu-id="520db-136">Pagina Instellingen</span><span class="sxs-lookup"><span data-stu-id="520db-136">Settings page</span></span> | <span data-ttu-id="520db-137">URI</span><span class="sxs-lookup"><span data-stu-id="520db-137">URI</span></span>                          |
|---------------|------------------------------|
| <span data-ttu-id="520db-138">Apps & functies<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="520db-138">Apps & features<sup>2</sup></span></span>     | `ms-settings:appsfeatures` <br> |
| <span data-ttu-id="520db-139">Apps & functies > Geavanceerde opties <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="520db-139">Apps & features > Advanced Options <sup>2</sup></span></span>     | `ms-settings::appsfeatures-app` <br> |
| <span data-ttu-id="520db-140">Apps & functies > Offline Maps <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="520db-140">Apps & features > Offline Maps <sup>2</sup></span></span>     | `ms-settings:maps-maps` <br> |
| <span data-ttu-id="520db-141">Apps & functies > Offline maps > Download maps <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="520db-141">Apps & features > Offline Maps > Download maps <sup>2</sup></span></span>     | `ms-settings:maps-downloadmaps` <br> |

### <a name="devices"></a><span data-ttu-id="520db-142">Apparaten</span><span class="sxs-lookup"><span data-stu-id="520db-142">Devices</span></span>
| <span data-ttu-id="520db-143">Pagina Instellingen</span><span class="sxs-lookup"><span data-stu-id="520db-143">Settings page</span></span> | <span data-ttu-id="520db-144">URI</span><span class="sxs-lookup"><span data-stu-id="520db-144">URI</span></span>                          |
|---------------|------------------------------|
| <span data-ttu-id="520db-145">Bluetooth</span><span class="sxs-lookup"><span data-stu-id="520db-145">Bluetooth</span></span>     | `ms-settings:bluetooth` <br> `ms-settings:connecteddevices` |
| <span data-ttu-id="520db-146">Muis <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="520db-146">Mouse <sup>2</sup></span></span>      | `ms-settings:mouse` <br>  |
| <span data-ttu-id="520db-147">USB <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="520db-147">USB <sup>2</sup></span></span>      | `ms-settings:usb` <br>  |

### <a name="privacy"></a><span data-ttu-id="520db-148">Privacy</span><span class="sxs-lookup"><span data-stu-id="520db-148">Privacy</span></span>
| <span data-ttu-id="520db-149">Pagina Instellingen</span><span class="sxs-lookup"><span data-stu-id="520db-149">Settings page</span></span>            | <span data-ttu-id="520db-150">URI</span><span class="sxs-lookup"><span data-stu-id="520db-150">URI</span></span>                                             |
|--------------------------|-------------------------------------------------|
| <span data-ttu-id="520db-151">Accountgegevens</span><span class="sxs-lookup"><span data-stu-id="520db-151">Account Info</span></span>             | `ms-settings:privacy-accountinfo`              |
| <span data-ttu-id="520db-152">App Diagnostics</span><span class="sxs-lookup"><span data-stu-id="520db-152">App Diagnostics</span></span>        | `ms-settings:privacy-appdiagnostics`              |
| <span data-ttu-id="520db-153">Achtergrond-apps</span><span class="sxs-lookup"><span data-stu-id="520db-153">Background Apps</span></span>        | `ms-settings:privacy-backgroundapps`              |
| <span data-ttu-id="520db-154">Kalender</span><span class="sxs-lookup"><span data-stu-id="520db-154">Calendar</span></span>                 | `ms-settings:privacy-calendar`                    |
| <span data-ttu-id="520db-155">Oproepgeschiedenis</span><span class="sxs-lookup"><span data-stu-id="520db-155">Call History</span></span>             | `ms-settings:privacy-callhistory`                 |
| <span data-ttu-id="520db-156">Camera</span><span class="sxs-lookup"><span data-stu-id="520db-156">Camera</span></span>                   | `ms-settings:privacy-webcam`                      |
| <span data-ttu-id="520db-157">Contactpersonen</span><span class="sxs-lookup"><span data-stu-id="520db-157">Contacts</span></span>                 | `ms-settings:privacy-contacts`                    |
| <span data-ttu-id="520db-158">Feedback over & diagnostische gegevens</span><span class="sxs-lookup"><span data-stu-id="520db-158">Diagnostics & Feedback</span></span> | `ms-settings:privacy-feedback`                    |
| <span data-ttu-id="520db-159">Documenten</span><span class="sxs-lookup"><span data-stu-id="520db-159">Documents</span></span>                | `ms-settings:privacy-documents`                   |
| <span data-ttu-id="520db-160">E-mail</span><span class="sxs-lookup"><span data-stu-id="520db-160">Email</span></span>                    | `ms-settings:privacy-email`                       |
| <span data-ttu-id="520db-161">Bestandssysteem</span><span class="sxs-lookup"><span data-stu-id="520db-161">File system</span></span>              | `ms-settings:privacy-broadfilesystemaccess`       |
| <span data-ttu-id="520db-162">Algemeen <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="520db-162">General <sup>2</sup></span></span>             | `ms-settings:privacy-general`       |
| <span data-ttu-id="520db-163">Ink & personalisatie <sup>typen 2</sup></span><span class="sxs-lookup"><span data-stu-id="520db-163">Ink & typing personalization <sup>2</sup></span></span>             | `ms-settings:privacy-speechtyping`       |
| <span data-ttu-id="520db-164">Locatie</span><span class="sxs-lookup"><span data-stu-id="520db-164">Location</span></span>                 | `ms-settings:privacy-location`                    |
| <span data-ttu-id="520db-165">Berichten</span><span class="sxs-lookup"><span data-stu-id="520db-165">Messaging</span></span>                | `ms-settings:privacy-messaging`                   |
| <span data-ttu-id="520db-166">Microfoon</span><span class="sxs-lookup"><span data-stu-id="520db-166">Microphone</span></span>               | `ms-settings:privacy-microphone`                  |
| <span data-ttu-id="520db-167">Beweging <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="520db-167">Motion <sup>2</sup></span></span>               | `ms-settings:privacy-motion`                  |
| <span data-ttu-id="520db-168">Meldingen</span><span class="sxs-lookup"><span data-stu-id="520db-168">Notifications</span></span>            | `ms-settings:privacy-notifications`               |
| <span data-ttu-id="520db-169">Andere apparaten</span><span class="sxs-lookup"><span data-stu-id="520db-169">Other devices</span></span>            | `ms-settings:privacy-customdevices`               |
| <span data-ttu-id="520db-170">Afbeeldingen</span><span class="sxs-lookup"><span data-stu-id="520db-170">Pictures</span></span>                 | `ms-settings:privacy-pictures`                    |
| <span data-ttu-id="520db-171">Radios</span><span class="sxs-lookup"><span data-stu-id="520db-171">Radios</span></span>                   | `ms-settings:privacy-radios`                      |
| <span data-ttu-id="520db-172">Schermopname van randen <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="520db-172">Screenshot borders <sup>2</sup></span></span>             | `ms-settings:privacy-graphicsCaptureWithoutBorder`       |
| <span data-ttu-id="520db-173">Schermopnamen en apps <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="520db-173">Screenshots and apps <sup>2</sup></span></span>             | `ms-settings:privacy-graphicsCaptureProgrammatic`       |
| <span data-ttu-id="520db-174">Spraak</span><span class="sxs-lookup"><span data-stu-id="520db-174">Speech</span></span>                   | `ms-settings:privacy-speech`                      |
| <span data-ttu-id="520db-175">Taken</span><span class="sxs-lookup"><span data-stu-id="520db-175">Tasks</span></span>                    | `ms-settings:privacy-tasks`                       |
| <span data-ttu-id="520db-176">Gebruikersverloop</span><span class="sxs-lookup"><span data-stu-id="520db-176">User movements</span></span>           | `ms-settings:privacy-backgroundspatialperception` |
| <span data-ttu-id="520db-177">Video's</span><span class="sxs-lookup"><span data-stu-id="520db-177">Videos</span></span>                   | `ms-settings:privacy-videos`                      |
| <span data-ttu-id="520db-178">Spraakactivering</span><span class="sxs-lookup"><span data-stu-id="520db-178">Voice Activation</span></span>       | `ms-settings:privacy-voiceactivation`             |

### <a name="network--internet"></a><span data-ttu-id="520db-179">Netwerk en internet</span><span class="sxs-lookup"><span data-stu-id="520db-179">Network & Internet</span></span>
| <span data-ttu-id="520db-180">Pagina Instellingen</span><span class="sxs-lookup"><span data-stu-id="520db-180">Settings page</span></span> | <span data-ttu-id="520db-181">URI</span><span class="sxs-lookup"><span data-stu-id="520db-181">URI</span></span>                              |
|---------------|----------------------------------|
| <span data-ttu-id="520db-182">Vliegtuigmodus <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="520db-182">Airplane Mode <sup>2</sup></span></span> | `ms-settings:network-airplanemode`        |
| <span data-ttu-id="520db-183">Proxy</span><span class="sxs-lookup"><span data-stu-id="520db-183">Proxy</span></span> | `ms-settings:network-proxy`        |
| <span data-ttu-id="520db-184">VPN</span><span class="sxs-lookup"><span data-stu-id="520db-184">VPN</span></span>   | `ms-settings:network-vpn`          |
| <span data-ttu-id="520db-185">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="520db-185">Wi-Fi</span></span>  | `ms-settings:network-wifi`<br>`ms-settings:network-wifisettings`<br>`ms-settings:network-status`<br>`ms-settings:wifi-provisioning`    |



### <a name="system"></a><span data-ttu-id="520db-186">Systeem</span><span class="sxs-lookup"><span data-stu-id="520db-186">System</span></span>
| <span data-ttu-id="520db-187">Pagina Instellingen</span><span class="sxs-lookup"><span data-stu-id="520db-187">Settings page</span></span>      | <span data-ttu-id="520db-188">URI</span><span class="sxs-lookup"><span data-stu-id="520db-188">URI</span></span>                                |
|--------------------|------------------------------------|
| <span data-ttu-id="520db-189">Accu <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="520db-189">Battery <sup>2</sup></span></span>           | `ms-settings:batterysaver`<br>|
| <span data-ttu-id="520db-190">Accu <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="520db-190">Battery <sup>2</sup></span></span>           | `ms-settings:batterysaver-settings`<br>|
| <span data-ttu-id="520db-191">Kleuren</span><span class="sxs-lookup"><span data-stu-id="520db-191">Colors</span></span>             | `ms-settings:colors`<br>`ms-settings:personalization-colors` |
| <span data-ttu-id="520db-192">Hologrammen <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="520db-192">Holograms <sup>2</sup></span></span>  |  `ms-settings:holograms`  |
| <span data-ttu-id="520db-193"><sup>Kalibratie 2</sup></span><span class="sxs-lookup"><span data-stu-id="520db-193">Calibration <sup>2</sup></span></span> |  `ms-settings:calibration` |
| <span data-ttu-id="520db-194">Meldingen & acties</span><span class="sxs-lookup"><span data-stu-id="520db-194">Notifications & actions</span></span>  | `ms-settings:notifications`          |
| <span data-ttu-id="520db-195">Gedeelde ervaringen</span><span class="sxs-lookup"><span data-stu-id="520db-195">Shared Experiences</span></span> | `ms-settings:crossdevice` 
| <span data-ttu-id="520db-196">Geluid <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="520db-196">Sound <sup>2</sup></span></span>           | `ms-settings:sound`<br>|
| <span data-ttu-id="520db-197">Geluids > app-volume en apparaatvoorkeur <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="520db-197">Sound > App volume and device preference <sup>2</sup></span></span>           | `ms-settings:apps-volume`<br>|
| <span data-ttu-id="520db-198">Geluidsapparaten > beheren <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="520db-198">Sound > Manage sound devices <sup>2</sup></span></span>           | `ms-settings:sound-devices`<br>|
| <span data-ttu-id="520db-199">Storage</span><span class="sxs-lookup"><span data-stu-id="520db-199">Storage</span></span>            | `ms-settings:storagesense`           |
| <span data-ttu-id="520db-200">Opslag > configureren Opslaginzicht <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="520db-200">Storage > Configure Storage Sense <sup>2</sup></span></span>           | `ms-settings:storagepolicies`<br>|

### <a name="time--language"></a><span data-ttu-id="520db-201">Time & Language</span><span class="sxs-lookup"><span data-stu-id="520db-201">Time & Language</span></span>
| <span data-ttu-id="520db-202">Pagina Instellingen</span><span class="sxs-lookup"><span data-stu-id="520db-202">Settings page</span></span> | <span data-ttu-id="520db-203">URI</span><span class="sxs-lookup"><span data-stu-id="520db-203">URI</span></span>                                           |
|---------------|-----------------------------------------------|
| <span data-ttu-id="520db-204">Datum & tijd <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="520db-204">Date & time <sup>2</sup></span></span> | `ms-settings:dateandtime`                  |
| <span data-ttu-id="520db-205">Toetsenbord <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="520db-205">Keyboard <sup>2</sup></span></span> | `ms-settings:keyboard`                  |
| <span data-ttu-id="520db-206">Taal <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="520db-206">Language <sup>2</sup></span></span> | `ms-settings:language`                  |
| <span data-ttu-id="520db-207">Taal <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="520db-207">Language <sup>2</sup></span></span> | `ms-settings:regionlanguage-languageoptions`                  |
| <span data-ttu-id="520db-208">Taal</span><span class="sxs-lookup"><span data-stu-id="520db-208">Language</span></span>      | `ms-settings:regionlanguage`<br>`ms-settings:regionlanguage-adddisplaylanguage`<br>`ms-settings:regionlanguage-setdisplaylanguage` |
| <span data-ttu-id="520db-209">Region</span><span class="sxs-lookup"><span data-stu-id="520db-209">Region</span></span>        | `ms-settings:regionformatting`                  |

### <a name="update--security"></a><span data-ttu-id="520db-210">Beveiliging & bijwerken</span><span class="sxs-lookup"><span data-stu-id="520db-210">Update & Security</span></span>
| <span data-ttu-id="520db-211">Pagina Instellingen</span><span class="sxs-lookup"><span data-stu-id="520db-211">Settings page</span></span>                         | <span data-ttu-id="520db-212">URI</span><span class="sxs-lookup"><span data-stu-id="520db-212">URI</span></span>                                       |
|---------------------------------------|-------------------------------------------|
| <span data-ttu-id="520db-213">Geavanceerde opties</span><span class="sxs-lookup"><span data-stu-id="520db-213">Advanced Options</span></span>                    | `ms-settings:windowsupdate-options`         |
| <span data-ttu-id="520db-214">Herstel & opnieuw <sup>instellen 2</sup></span><span class="sxs-lookup"><span data-stu-id="520db-214">Reset & Recovery <sup>2</sup></span></span>      | `ms-settings:reset`         |
| <span data-ttu-id="520db-215">Windows Insider-programma</span><span class="sxs-lookup"><span data-stu-id="520db-215">Windows Insider Program</span></span>               | `ms-settings:windowsinsider` <br>`ms-settings:windowsinsider-optin`          |
| <span data-ttu-id="520db-216">Windows Update</span><span class="sxs-lookup"><span data-stu-id="520db-216">Windows Update</span></span>                        | `ms-settings:windowsupdate`<br> `ms-settings:windowsupdate-activehours`  <br> `ms-settings:windowsupdate-history` <br> `ms-settings:windowsupdate-optionalupdates` <br><span data-ttu-id="520db-217"><sup>1</sup>`ms-settings:windowsupdate-options`</span><span class="sxs-lookup"><span data-stu-id="520db-217"><sup>1</sup>`ms-settings:windowsupdate-options`</span></span><br><span data-ttu-id="520db-218"><sup>1</sup>`ms-settings:windowsupdate-restartoptions`</span><span class="sxs-lookup"><span data-stu-id="520db-218"><sup>1</sup>`ms-settings:windowsupdate-restartoptions`</span></span> |
| <span data-ttu-id="520db-219">Windows Update: controleert op updates</span><span class="sxs-lookup"><span data-stu-id="520db-219">Windows Update - Checks for updates</span></span> | `ms-settings:windowsupdate-action`          |


- <span data-ttu-id="520db-220"><sup>1:</sup> voor versies vóór Windows Holographic, versie 21H1, gaan de  volgende twee URI's niet daadwerkelijk naar de pagina's Geavanceerde opties **of** Opties; Ze blokkeren of tonen alleen de hoofdpagina Windows Update pagina.</span><span class="sxs-lookup"><span data-stu-id="520db-220"><sup>1</sup> - For versions prior to Windows Holographic, version 21H1, the following two URIs do not actually take you to the **Advanced options** or **Options** pages; they will only block or show the main Windows Update page.</span></span>
  -  <span data-ttu-id="520db-221">ms-settings:windowsupdate-options</span><span class="sxs-lookup"><span data-stu-id="520db-221">ms-settings:windowsupdate-options</span></span>
  -  <span data-ttu-id="520db-222">ms-settings:windowsupdate-restartoptions</span><span class="sxs-lookup"><span data-stu-id="520db-222">ms-settings:windowsupdate-restartoptions</span></span>

- <span data-ttu-id="520db-223"><sup>2:</sup> beschikbaar in Windows Holographic 21H1 of hoger.</span><span class="sxs-lookup"><span data-stu-id="520db-223"><sup>2</sup> - Available in Windows Holographic 21H1 or higher.</span></span>


<span data-ttu-id="520db-224">Ga voor een volledige lijst met Windows 10 Instellingen-URI's naar de [documentatie voor startinstellingen.](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference)</span><span class="sxs-lookup"><span data-stu-id="520db-224">For a full list of Windows 10 Settings URIs, please visit the [launch settings](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference) documentation.</span></span>
