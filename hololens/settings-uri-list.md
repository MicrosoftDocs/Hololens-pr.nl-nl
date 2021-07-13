---
title: Zichtbaarheid Instellingen pagina's
description: Blijf op de hoogte van onze lijst met ondersteunde URI's voor PageVisibilityList en guide on HoloLens mixed reality apparaten.
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
ms.openlocfilehash: 454d79e8b719feb73d5a39280794dcd76f134952
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639230"
---
# <a name="page-settings-visibility"></a><span data-ttu-id="eafd3-104">Zichtbaarheid Instellingen pagina's</span><span class="sxs-lookup"><span data-stu-id="eafd3-104">Page Settings Visibility</span></span>

<span data-ttu-id="eafd3-105">Een van de beheerbare functies voor HoloLens-apparaten is het gebruik van het [Instellingen/PageVisibilityList-beleid](/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) om de pagina's te beperken die worden weergegeven in de Instellingen app.</span><span class="sxs-lookup"><span data-stu-id="eafd3-105">One of the manageable features for HoloLens devices is using the [Settings/PageVisibilityList policy](/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) to restrict the pages seen within the Settings app.</span></span> <span data-ttu-id="eafd3-106">PageVisibilityList is een beleid waarmee IT-beheerders kunnen voorkomen dat specifieke pagina's in de System Instellingen-app zichtbaar of toegankelijk zijn, of om dit te doen voor alle pagina's, met uitzondering van de opgegeven pagina's.</span><span class="sxs-lookup"><span data-stu-id="eafd3-106">PageVisibilityList is a policy that allows IT Admins to either prevent specific pages in the System Settings app from being visible or accessible, or to do so for all pages except those specified.</span></span>

> [!NOTE]
> <span data-ttu-id="eafd3-107">Deze functie is alleen beschikbaar in [Windows Holographic, versie 20H2](hololens-release-notes.md#windows-holographic-version-20h2) of hoger voor HoloLens 2 apparaten.</span><span class="sxs-lookup"><span data-stu-id="eafd3-107">This feature is only avalible in [Windows Holographic, version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) or higher for HoloLens 2 devices.</span></span> <span data-ttu-id="eafd3-108">Zorg ervoor dat de apparaten voor wie u dit wilt gebruiken, zijn bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="eafd3-108">Please ensure devices you intend to use this for are updated.</span></span>


## <a name="examples"></a><span data-ttu-id="eafd3-109">Voorbeelden</span><span class="sxs-lookup"><span data-stu-id="eafd3-109">Examples</span></span>
<span data-ttu-id="eafd3-110">Pagina's worden geïdentificeerd door een verkorte versie van de gepubliceerde URI's, de URI min het voorvoegsel 'ms-settings:'.</span><span class="sxs-lookup"><span data-stu-id="eafd3-110">Pages are identified by a shortened version of the published URIs, which is the URI minus the "ms-settings:" prefix.</span></span>

<span data-ttu-id="eafd3-111">In het volgende voorbeeld ziet u een beleid waarmee alleen toegang kan worden toegestaan tot de about- en Bluetooth-pagina's, die respectievelijk URI 'network-wifi' en 'bluetooth' hebben:</span><span class="sxs-lookup"><span data-stu-id="eafd3-111">The following example illustrates a policy that would allow access only to the about and bluetooth pages, which have URI "network-wifi" and "bluetooth" respectively:</span></span>
- `showonly:network-wifi;network-proxy;bluetooth`

<span data-ttu-id="eafd3-112">In het volgende voorbeeld ziet u een beleid dat de pagina Voor het opnieuw instellen van het besturingssysteem verbergt:</span><span class="sxs-lookup"><span data-stu-id="eafd3-112">The following example illustrates a policy that would hide the OS Reset page:</span></span>
- `hide:reset`


## <a name="deploying-this-policy-via-intune"></a><span data-ttu-id="eafd3-113">Dit beleid implementeren via Intune</span><span class="sxs-lookup"><span data-stu-id="eafd3-113">Deploying this policy via Intune</span></span>

<span data-ttu-id="eafd3-114">Dit zijn de configuratiewaarden die aan Intune worden opgegeven:</span><span class="sxs-lookup"><span data-stu-id="eafd3-114">These are the configuration values that will be supplied to Intune:</span></span>

- <span data-ttu-id="eafd3-115">**Naam:** Een door de beheerder gewenste weergavenaam voor het profiel.</span><span class="sxs-lookup"><span data-stu-id="eafd3-115">**Name:** An admin preferred display name for the profile.</span></span>
- <span data-ttu-id="eafd3-116">**OMA-URI:** De volledig gekwalificeerde URI van de instellingspagina, inclusief het [bereik](/windows/client-management/mdm/policy-configuration-service-provider).</span><span class="sxs-lookup"><span data-stu-id="eafd3-116">**OMA-URI:** The fully qualified URI of the setting page including its [scope](/windows/client-management/mdm/policy-configuration-service-provider).</span></span> <span data-ttu-id="eafd3-117">In deze voorbeelden op deze pagina wordt het bereik `./Device` gebruikt.</span><span class="sxs-lookup"><span data-stu-id="eafd3-117">This examples on this page are using the `./Device` scope.</span></span>
- <span data-ttu-id="eafd3-118">**Waarde:** Een tekenreekswaarde die aangeeft of  alleen de opgegeven pagina's moeten worden verborgen of weergegeven.</span><span class="sxs-lookup"><span data-stu-id="eafd3-118">**Value:** A string value that indicates whether to hide or show *only* the specified pages.</span></span> <span data-ttu-id="eafd3-119">Mogelijke waarden zijn `hide:<pagename>` en `showonly:<pagename>` .</span><span class="sxs-lookup"><span data-stu-id="eafd3-119">Possible values are `hide:<pagename>` and `showonly:<pagename>`.</span></span> 
 
<span data-ttu-id="eafd3-120">U kunt meerdere pagina's specificeren door ze te scheiden met puntkomma's. Hieronder vindt u een lijst met algemene pagina's.</span><span class="sxs-lookup"><span data-stu-id="eafd3-120">Multiple pages can be specified by separating them with a semicolon, and a listing of common pages can be found below.</span></span>

1. <span data-ttu-id="eafd3-121">Maak een **aangepast beleid.**</span><span class="sxs-lookup"><span data-stu-id="eafd3-121">Create a **Custom policy**.</span></span>
1. <span data-ttu-id="eafd3-122">Bij het instellen van **de OMA-URI** voert u de URI met volledig bereik in.</span><span class="sxs-lookup"><span data-stu-id="eafd3-122">When setting the **OMA-URI** enter the fully scoped URI.</span></span> <span data-ttu-id="eafd3-123">Bijvoorbeeld: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**</span><span class="sxs-lookup"><span data-stu-id="eafd3-123">For example: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**</span></span>
1. <span data-ttu-id="eafd3-124">Kies bij het selecteren van de gegevens de optie **Tekenreeks:**</span><span class="sxs-lookup"><span data-stu-id="eafd3-124">When selecting the data pick choose: **String**</span></span>
1. <span data-ttu-id="eafd3-125">Gebruik de **bovenstaande richtlijnen bij** het opgeven van Waarde.</span><span class="sxs-lookup"><span data-stu-id="eafd3-125">When specifying **Value** use the guidance above.</span></span> <span data-ttu-id="eafd3-126">Bijvoorbeeld: **`showonly:network-wifi;network-proxy;bluetooth`** of **`hide:reset`**</span><span class="sxs-lookup"><span data-stu-id="eafd3-126">For example: **`showonly:network-wifi;network-proxy;bluetooth`** or **`hide:reset`**</span></span> 
> [!IMPORTANT]
> <span data-ttu-id="eafd3-127">Zorg ervoor dat u de aangepaste apparaatconfiguratie toewijst aan een groep waarin het apparaat is bedoeld.</span><span class="sxs-lookup"><span data-stu-id="eafd3-127">Make sure to assign the custom device configuration to a group the device is intended to be in.</span></span> <span data-ttu-id="eafd3-128">Als deze stap niet wordt uitgevoerd, wordt het beleid gep pusht, maar niet toegepast.</span><span class="sxs-lookup"><span data-stu-id="eafd3-128">If this step is not performed, the policy will be pushed but won't be applied.</span></span>

<span data-ttu-id="eafd3-129">Zie [HoloLens MDM-configuratie voor](hololens-mdm-configure.md) meer informatie over Intune-groepen en apparaatconfiguraties.</span><span class="sxs-lookup"><span data-stu-id="eafd3-129">See [HoloLens MDM configuration](hololens-mdm-configure.md) for more information on Intune groups and device configurations.</span></span>


## <a name="deploying-this-policy-via-a-provisioning-package"></a><span data-ttu-id="eafd3-130">Dit beleid implementeren via een inrichtingspakket</span><span class="sxs-lookup"><span data-stu-id="eafd3-130">Deploying this policy via a Provisioning Package</span></span>

<span data-ttu-id="eafd3-131">Dit zijn de configuratiewaarden die worden opgegeven in Windows Configuration Designer:</span><span class="sxs-lookup"><span data-stu-id="eafd3-131">These are the configuration values that will be specified in Windows Configuration Designer:</span></span>

<span data-ttu-id="eafd3-132">**Waarde:** Een tekenreekswaarde die aangeeft of  alleen de opgegeven pagina's moeten worden verborgen of weergegeven.</span><span class="sxs-lookup"><span data-stu-id="eafd3-132">**Value:** A string value that indicates whether to hide or show *only* the specified pages.</span></span> <span data-ttu-id="eafd3-133">Mogelijke waarden zijn `hide:<pagename>` en `showonly:<pagename>` .</span><span class="sxs-lookup"><span data-stu-id="eafd3-133">Possible values are `hide:<pagename>` and `showonly:<pagename>`.</span></span> <span data-ttu-id="eafd3-134">U kunt meerdere pagina's specificeren door ze te scheiden met puntkomma's. Hieronder vindt u een lijst met algemene pagina's.</span><span class="sxs-lookup"><span data-stu-id="eafd3-134">Multiple pages can be specified by separating them with a semicolon, and a listing of common pages can be found below.</span></span>


1. <span data-ttu-id="eafd3-135">Tijdens het maken van uw pakket in Windows Configuration Designer naar **Beleidsregels > Instellingen > PageVisibilityList**</span><span class="sxs-lookup"><span data-stu-id="eafd3-135">While creating your package in Windows Configuration Designer navigate to **Policies > Settings > PageVisibilityList**</span></span>
1. <span data-ttu-id="eafd3-136">Voer de tekenreeks in: **`showonly:network-wifi;network-proxy;bluetooth`**</span><span class="sxs-lookup"><span data-stu-id="eafd3-136">Enter the string: **`showonly:network-wifi;network-proxy;bluetooth`**</span></span>
1. <span data-ttu-id="eafd3-137">Exporteert u uw inrichtingspakket.</span><span class="sxs-lookup"><span data-stu-id="eafd3-137">Export your Provisioning Package.</span></span>
1. <span data-ttu-id="eafd3-138">Pas het pakket toe op uw apparaat.</span><span class="sxs-lookup"><span data-stu-id="eafd3-138">Apply the package to your device.</span></span>
<span data-ttu-id="eafd3-139">Ga naar HoloLens inrichtingspagina voor meer informatie over het maken en toepassen [van een inrichtingspakket.](hololens-provisioning.md)</span><span class="sxs-lookup"><span data-stu-id="eafd3-139">For full details on how to create and apply a provisioning package visit [the HoloLens provisioning page](hololens-provisioning.md).</span></span>


<span data-ttu-id="eafd3-140">Ongeacht de gekozen methode ontvangt uw apparaat nu de wijzigingen en krijgen gebruikers de volgende Instellingen app.</span><span class="sxs-lookup"><span data-stu-id="eafd3-140">Regardless of method chosen your device should now receive the changes and users will be presented with the following Settings App.</span></span>

![Schermopname van actieve uren die worden gewijzigd in de Instellingen app](images/hololens-page-visibility-list.jpg)

<span data-ttu-id="eafd3-142">Als u de pagina Instellingen app wilt configureren om uw eigen selectie pagina's weer te geven of te verbergen, bekijkt u de Instellingen URI's die beschikbaar zijn op HoloLens.</span><span class="sxs-lookup"><span data-stu-id="eafd3-142">To configure the Settings app pages to show or hide your own selection of pages, take a look at the Settings URIs available on HoloLens.</span></span>

## <a name="settings-uris"></a><span data-ttu-id="eafd3-143">Instellingen Uris</span><span class="sxs-lookup"><span data-stu-id="eafd3-143">Settings URIs</span></span>

<span data-ttu-id="eafd3-144">HoloLens apparaten en Windows 10 apparaten hebben een andere selectie pagina's in de Instellingen app.</span><span class="sxs-lookup"><span data-stu-id="eafd3-144">HoloLens devices and Windows 10 devices have a different selection of pages within the Settings app.</span></span> <span data-ttu-id="eafd3-145">Op deze pagina vindt u alleen de instellingen die aanwezig zijn op HoloLens.</span><span class="sxs-lookup"><span data-stu-id="eafd3-145">On this page, you will find only the settings that exist on HoloLens.</span></span>

### <a name="accounts"></a><span data-ttu-id="eafd3-146">Accounts</span><span class="sxs-lookup"><span data-stu-id="eafd3-146">Accounts</span></span>
| <span data-ttu-id="eafd3-147">Pagina Instellingen</span><span class="sxs-lookup"><span data-stu-id="eafd3-147">Settings page</span></span>           | <span data-ttu-id="eafd3-148">URI</span><span class="sxs-lookup"><span data-stu-id="eafd3-148">URI</span></span>                                            |
|-------------------------|------------------------------------------------|
| <span data-ttu-id="eafd3-149">Werk- of schoolaccount openen</span><span class="sxs-lookup"><span data-stu-id="eafd3-149">Access work or school</span></span> | `workplace`                         |
| <span data-ttu-id="eafd3-150">Iris-inschrijving</span><span class="sxs-lookup"><span data-stu-id="eafd3-150">Iris Enrollment</span></span>       | `signinoptions-launchirisenrollment` |
| <span data-ttu-id="eafd3-151">Aanmeldingsopties</span><span class="sxs-lookup"><span data-stu-id="eafd3-151">Sign In Options</span></span>         | ` signinoptions `                   |

### <a name="apps"></a><span data-ttu-id="eafd3-152">Apps</span><span class="sxs-lookup"><span data-stu-id="eafd3-152">Apps</span></span>
| <span data-ttu-id="eafd3-153">Pagina Instellingen</span><span class="sxs-lookup"><span data-stu-id="eafd3-153">Settings page</span></span> | <span data-ttu-id="eafd3-154">URI</span><span class="sxs-lookup"><span data-stu-id="eafd3-154">URI</span></span>                          |
|---------------|------------------------------|
| <span data-ttu-id="eafd3-155">Apps & functies <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="eafd3-155">Apps & features <sup>2</sup></span></span>     | `appsfeatures` <br> |
| <span data-ttu-id="eafd3-156">Apps & functies > Geavanceerde opties <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="eafd3-156">Apps & features > Advanced Options <sup>2</sup></span></span>     | `appsfeatures-app` <br> |
| <span data-ttu-id="eafd3-157">Apps & functies > Offline Kaarten <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="eafd3-157">Apps & features > Offline Maps <sup>2</sup></span></span>     | `maps-maps` <br> |
| <span data-ttu-id="eafd3-158">Apps & functies > Offline Kaarten > Download maps <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="eafd3-158">Apps & features > Offline Maps > Download maps <sup>2</sup></span></span>     | `maps-downloadmaps` <br> |

### <a name="devices"></a><span data-ttu-id="eafd3-159">Apparaten</span><span class="sxs-lookup"><span data-stu-id="eafd3-159">Devices</span></span>
| <span data-ttu-id="eafd3-160">Pagina Instellingen</span><span class="sxs-lookup"><span data-stu-id="eafd3-160">Settings page</span></span> | <span data-ttu-id="eafd3-161">URI</span><span class="sxs-lookup"><span data-stu-id="eafd3-161">URI</span></span>                          |
|---------------|------------------------------|
| <span data-ttu-id="eafd3-162">Bluetooth</span><span class="sxs-lookup"><span data-stu-id="eafd3-162">Bluetooth</span></span>     | `bluetooth` <br> `connecteddevices` |
| <span data-ttu-id="eafd3-163">Muis <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="eafd3-163">Mouse <sup>2</sup></span></span>      | `mouse` <br>  |
| <span data-ttu-id="eafd3-164">USB <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="eafd3-164">USB <sup>2</sup></span></span>      | `usb` <br>  |

### <a name="privacy"></a><span data-ttu-id="eafd3-165">Privacy</span><span class="sxs-lookup"><span data-stu-id="eafd3-165">Privacy</span></span>
| <span data-ttu-id="eafd3-166">Pagina Instellingen</span><span class="sxs-lookup"><span data-stu-id="eafd3-166">Settings page</span></span>            | <span data-ttu-id="eafd3-167">URI</span><span class="sxs-lookup"><span data-stu-id="eafd3-167">URI</span></span>                                             |
|--------------------------|-------------------------------------------------|
| <span data-ttu-id="eafd3-168">Accountgegevens</span><span class="sxs-lookup"><span data-stu-id="eafd3-168">Account Info</span></span>             | `privacy-accountinfo`              |
| <span data-ttu-id="eafd3-169">App Diagnostics</span><span class="sxs-lookup"><span data-stu-id="eafd3-169">App Diagnostics</span></span>        | `privacy-appdiagnostics`              |
| <span data-ttu-id="eafd3-170">Achtergrond-apps</span><span class="sxs-lookup"><span data-stu-id="eafd3-170">Background Apps</span></span>        | `privacy-backgroundapps`              |
| <span data-ttu-id="eafd3-171">Kalender</span><span class="sxs-lookup"><span data-stu-id="eafd3-171">Calendar</span></span>                 | `privacy-calendar`                    |
| <span data-ttu-id="eafd3-172">Oproepgeschiedenis</span><span class="sxs-lookup"><span data-stu-id="eafd3-172">Call History</span></span>             | `privacy-callhistory`                 |
| <span data-ttu-id="eafd3-173">Camera</span><span class="sxs-lookup"><span data-stu-id="eafd3-173">Camera</span></span>                   | `privacy-webcam`                      |
| <span data-ttu-id="eafd3-174">Contactpersonen</span><span class="sxs-lookup"><span data-stu-id="eafd3-174">Contacts</span></span>                 | `privacy-contacts`                    |
| <span data-ttu-id="eafd3-175">Feedback over & diagnostische gegevens</span><span class="sxs-lookup"><span data-stu-id="eafd3-175">Diagnostics & Feedback</span></span> | `privacy-feedback`                    |
| <span data-ttu-id="eafd3-176">Documenten</span><span class="sxs-lookup"><span data-stu-id="eafd3-176">Documents</span></span>                | `privacy-documents`                   |
| <span data-ttu-id="eafd3-177">E-mail</span><span class="sxs-lookup"><span data-stu-id="eafd3-177">Email</span></span>                    | `privacy-email`                       |
| <span data-ttu-id="eafd3-178">Bestandssysteem</span><span class="sxs-lookup"><span data-stu-id="eafd3-178">File system</span></span>              | `privacy-broadfilesystemaccess`       |
| <span data-ttu-id="eafd3-179">Algemeen <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="eafd3-179">General <sup>2</sup></span></span>             | `privacy-general`       |
| <span data-ttu-id="eafd3-180">Ink & het typen van personalisatie <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="eafd3-180">Ink & typing personalization <sup>2</sup></span></span>             | `privacy-speechtyping`       |
| <span data-ttu-id="eafd3-181">Locatie</span><span class="sxs-lookup"><span data-stu-id="eafd3-181">Location</span></span>                 | `privacy-location`                    |
| <span data-ttu-id="eafd3-182">Berichten</span><span class="sxs-lookup"><span data-stu-id="eafd3-182">Messaging</span></span>                | `privacy-messaging`                   |
| <span data-ttu-id="eafd3-183">Microfoon</span><span class="sxs-lookup"><span data-stu-id="eafd3-183">Microphone</span></span>               | `privacy-microphone`                  |
| <span data-ttu-id="eafd3-184">Beweging <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="eafd3-184">Motion <sup>2</sup></span></span>               | `privacy-motion`                  |
| <span data-ttu-id="eafd3-185">Meldingen</span><span class="sxs-lookup"><span data-stu-id="eafd3-185">Notifications</span></span>            | `privacy-notifications`               |
| <span data-ttu-id="eafd3-186">Andere apparaten</span><span class="sxs-lookup"><span data-stu-id="eafd3-186">Other devices</span></span>            | `privacy-customdevices`               |
| <span data-ttu-id="eafd3-187">Afbeeldingen</span><span class="sxs-lookup"><span data-stu-id="eafd3-187">Pictures</span></span>                 | `privacy-pictures`                    |
| <span data-ttu-id="eafd3-188">Radios</span><span class="sxs-lookup"><span data-stu-id="eafd3-188">Radios</span></span>                   | `privacy-radios`                      |
| <span data-ttu-id="eafd3-189">Schermopname van randen <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="eafd3-189">Screenshot borders <sup>2</sup></span></span>             | `privacy-graphicsCaptureWithoutBorder`       |
| <span data-ttu-id="eafd3-190">Schermopnamen en apps <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="eafd3-190">Screenshots and apps <sup>2</sup></span></span>             | `privacy-graphicsCaptureProgrammatic`       |
| <span data-ttu-id="eafd3-191">Spraak</span><span class="sxs-lookup"><span data-stu-id="eafd3-191">Speech</span></span>                   | `privacy-speech`                      |
| <span data-ttu-id="eafd3-192">Taken</span><span class="sxs-lookup"><span data-stu-id="eafd3-192">Tasks</span></span>                    | `privacy-tasks`                       |
| <span data-ttu-id="eafd3-193">Gebruikersverloop</span><span class="sxs-lookup"><span data-stu-id="eafd3-193">User movements</span></span>           | `privacy-backgroundspatialperception` |
| <span data-ttu-id="eafd3-194">Video's</span><span class="sxs-lookup"><span data-stu-id="eafd3-194">Videos</span></span>                   | `privacy-videos`                      |
| <span data-ttu-id="eafd3-195">Spraakactivering</span><span class="sxs-lookup"><span data-stu-id="eafd3-195">Voice Activation</span></span>       | `privacy-voiceactivation`             |

### <a name="network--internet"></a><span data-ttu-id="eafd3-196">Netwerk en internet</span><span class="sxs-lookup"><span data-stu-id="eafd3-196">Network & Internet</span></span>
| <span data-ttu-id="eafd3-197">Pagina Instellingen</span><span class="sxs-lookup"><span data-stu-id="eafd3-197">Settings page</span></span> | <span data-ttu-id="eafd3-198">URI</span><span class="sxs-lookup"><span data-stu-id="eafd3-198">URI</span></span>                              |
|---------------|----------------------------------|
| <span data-ttu-id="eafd3-199">Vliegtuigmodus <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="eafd3-199">Airplane Mode <sup>2</sup></span></span> | `network-airplanemode`        |
| <span data-ttu-id="eafd3-200">Proxy</span><span class="sxs-lookup"><span data-stu-id="eafd3-200">Proxy</span></span> | `network-proxy`        |
| <span data-ttu-id="eafd3-201">VPN</span><span class="sxs-lookup"><span data-stu-id="eafd3-201">VPN</span></span>   | `network-vpn`          |
| <span data-ttu-id="eafd3-202">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="eafd3-202">Wi-Fi</span></span>  | `network-wifi`<br>`network-wifisettings`<br>`network-status`<br>`wifi-provisioning`    |



### <a name="system"></a><span data-ttu-id="eafd3-203">Systeem</span><span class="sxs-lookup"><span data-stu-id="eafd3-203">System</span></span>
| <span data-ttu-id="eafd3-204">Pagina Instellingen</span><span class="sxs-lookup"><span data-stu-id="eafd3-204">Settings page</span></span>      | <span data-ttu-id="eafd3-205">URI</span><span class="sxs-lookup"><span data-stu-id="eafd3-205">URI</span></span>                                |
|--------------------|------------------------------------|
| <span data-ttu-id="eafd3-206">Accu <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="eafd3-206">Battery <sup>2</sup></span></span>           | `batterysaver`<br>|
| <span data-ttu-id="eafd3-207">Accu <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="eafd3-207">Battery <sup>2</sup></span></span>           | `batterysaver-settings`<br>|
| <span data-ttu-id="eafd3-208">Kleuren</span><span class="sxs-lookup"><span data-stu-id="eafd3-208">Colors</span></span>             | `colors`<br>`personalization-colors` |
| <span data-ttu-id="eafd3-209">Hologrammen <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="eafd3-209">Holograms <sup>2</sup></span></span>  |  `holograms`  |
| <span data-ttu-id="eafd3-210"><sup>Kalibratie 2</sup></span><span class="sxs-lookup"><span data-stu-id="eafd3-210">Calibration <sup>2</sup></span></span> |  `calibration` |
| <span data-ttu-id="eafd3-211">Meldingen & acties</span><span class="sxs-lookup"><span data-stu-id="eafd3-211">Notifications & actions</span></span>  | `notifications`          |
| <span data-ttu-id="eafd3-212">Gedeelde ervaringen</span><span class="sxs-lookup"><span data-stu-id="eafd3-212">Shared Experiences</span></span> | `crossdevice` 
| <span data-ttu-id="eafd3-213">Geluid <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="eafd3-213">Sound <sup>2</sup></span></span>           | `sound`<br>|
| <span data-ttu-id="eafd3-214">Geluids > app-volume en apparaatvoorkeur <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="eafd3-214">Sound > App volume and device preference <sup>2</sup></span></span>           | `apps-volume`<br>|
| <span data-ttu-id="eafd3-215">Geluidsapparaten > beheren <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="eafd3-215">Sound > Manage sound devices <sup>2</sup></span></span>           | `sound-devices`<br>|
| <span data-ttu-id="eafd3-216">Storage</span><span class="sxs-lookup"><span data-stu-id="eafd3-216">Storage</span></span>            | `storagesense`           |
| <span data-ttu-id="eafd3-217">Storage > Sense 2 Storage <sup>configureren</sup></span><span class="sxs-lookup"><span data-stu-id="eafd3-217">Storage > Configure Storage Sense <sup>2</sup></span></span>           | `storagepolicies`<br>|

### <a name="time--language"></a><span data-ttu-id="eafd3-218">Time & Language</span><span class="sxs-lookup"><span data-stu-id="eafd3-218">Time & Language</span></span>
| <span data-ttu-id="eafd3-219">Pagina Instellingen</span><span class="sxs-lookup"><span data-stu-id="eafd3-219">Settings page</span></span> | <span data-ttu-id="eafd3-220">URI</span><span class="sxs-lookup"><span data-stu-id="eafd3-220">URI</span></span>                                           |
|---------------|-----------------------------------------------|
| <span data-ttu-id="eafd3-221">Datum & tijd <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="eafd3-221">Date & time <sup>2</sup></span></span> | `dateandtime`                  |
| <span data-ttu-id="eafd3-222">Toetsenbord <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="eafd3-222">Keyboard <sup>2</sup></span></span> | `keyboard`                  |
| <span data-ttu-id="eafd3-223">Taal <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="eafd3-223">Language <sup>2</sup></span></span> | `language`                  |
| <span data-ttu-id="eafd3-224">Taal <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="eafd3-224">Language <sup>2</sup></span></span> | `regionlanguage-languageoptions`                  |
| <span data-ttu-id="eafd3-225">Taal</span><span class="sxs-lookup"><span data-stu-id="eafd3-225">Language</span></span>      | `regionlanguage`<br>`regionlanguage-adddisplaylanguage`<br>`regionlanguage-setdisplaylanguage` |
| <span data-ttu-id="eafd3-226">Region</span><span class="sxs-lookup"><span data-stu-id="eafd3-226">Region</span></span>        | `regionformatting`                  |

### <a name="update--security"></a><span data-ttu-id="eafd3-227">Beveiliging & bijwerken</span><span class="sxs-lookup"><span data-stu-id="eafd3-227">Update & Security</span></span>
| <span data-ttu-id="eafd3-228">Pagina Instellingen</span><span class="sxs-lookup"><span data-stu-id="eafd3-228">Settings page</span></span>                         | <span data-ttu-id="eafd3-229">URI</span><span class="sxs-lookup"><span data-stu-id="eafd3-229">URI</span></span>                                       |
|---------------------------------------|-------------------------------------------|
| <span data-ttu-id="eafd3-230">Geavanceerde opties</span><span class="sxs-lookup"><span data-stu-id="eafd3-230">Advanced Options</span></span>                    | `windowsupdate-options`         |
| <span data-ttu-id="eafd3-231">Herstel & <sup>2 opnieuw instellen</sup></span><span class="sxs-lookup"><span data-stu-id="eafd3-231">Reset & Recovery <sup>2</sup></span></span>      | `reset`         |
| <span data-ttu-id="eafd3-232">Windows Insider-programma</span><span class="sxs-lookup"><span data-stu-id="eafd3-232">Windows Insider Program</span></span>               | `windowsinsider` <br>`windowsinsider-optin`          |
| <span data-ttu-id="eafd3-233">Windows Update</span><span class="sxs-lookup"><span data-stu-id="eafd3-233">Windows Update</span></span>                        | `windowsupdate`<br> `windowsupdate-activehours`  <br> `windowsupdate-history` <br> `windowsupdate-optionalupdates` <br><span data-ttu-id="eafd3-234"><sup>1</sup>`windowsupdate-options`</span><span class="sxs-lookup"><span data-stu-id="eafd3-234"><sup>1</sup>`windowsupdate-options`</span></span><br><span data-ttu-id="eafd3-235"><sup>1</sup>`windowsupdate-restartoptions`</span><span class="sxs-lookup"><span data-stu-id="eafd3-235"><sup>1</sup>`windowsupdate-restartoptions`</span></span> |
| <span data-ttu-id="eafd3-236">Windows Update: controleert op updates</span><span class="sxs-lookup"><span data-stu-id="eafd3-236">Windows Update - Checks for updates</span></span> | `windowsupdate-action`          |


- <span data-ttu-id="eafd3-237"><sup>1:</sup> voor versies vóór Windows Holographic, versie 21H1, gaan de volgende  twee URI's niet daadwerkelijk naar de pagina's Geavanceerde opties of **Opties;** Ze blokkeren of tonen alleen de hoofdpagina Windows Update.</span><span class="sxs-lookup"><span data-stu-id="eafd3-237"><sup>1</sup> - For versions prior to Windows Holographic, version 21H1, the following two URIs do not actually take you to the **Advanced options** or **Options** pages; they will only block or show the main Windows Update page.</span></span>
  -  <span data-ttu-id="eafd3-238">windowsupdate-options</span><span class="sxs-lookup"><span data-stu-id="eafd3-238">windowsupdate-options</span></span>
  -  <span data-ttu-id="eafd3-239">windowsupdate-restartoptions</span><span class="sxs-lookup"><span data-stu-id="eafd3-239">windowsupdate-restartoptions</span></span>

- <span data-ttu-id="eafd3-240"><sup>2</sup> : beschikbaar in Windows Holographic 21H1 of hoger.</span><span class="sxs-lookup"><span data-stu-id="eafd3-240"><sup>2</sup> - Available in Windows Holographic 21H1 or higher.</span></span>


<span data-ttu-id="eafd3-241">Raadpleeg de documentatie voor startinstellingen Windows 10 Instellingen een volledige lijst met [URI's.](/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference)</span><span class="sxs-lookup"><span data-stu-id="eafd3-241">For a full list of Windows 10 Settings URIs, please visit the [launch settings](/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference) documentation.</span></span>
