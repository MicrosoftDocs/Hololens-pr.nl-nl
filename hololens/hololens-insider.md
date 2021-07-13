---
title: Insider-preview voor Microsoft HoloLens
description: Meer informatie over hoe u aan de slag gaat met Insider-builds en waardevolle feedback geeft voor onze volgende belangrijke update van het besturingssysteem voor HoloLens.
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 04/01/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 87b606e634d4035da02802ddd1a8e1a980f1f1d6
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/12/2021
ms.locfileid: "113636087"
---
# <a name="insider-preview-for-microsoft-hololens"></a><span data-ttu-id="cab3b-103">Insider-preview voor Microsoft HoloLens</span><span class="sxs-lookup"><span data-stu-id="cab3b-103">Insider preview for Microsoft HoloLens</span></span>

<span data-ttu-id="cab3b-104">Welkom bij de nieuwste Insider Preview-builds voor HoloLens.</span><span class="sxs-lookup"><span data-stu-id="cab3b-104">Welcome to the latest Insider Preview builds for HoloLens!</span></span> <span data-ttu-id="cab3b-105">Het is eenvoudig om aan de slag [te gaan](hololens-insider.md#start-receiving-insider-builds) en waardevolle feedback te geven voor onze volgende belangrijke update van het besturingssysteem voor HoloLens.</span><span class="sxs-lookup"><span data-stu-id="cab3b-105">It's simple to [get started](hololens-insider.md#start-receiving-insider-builds) and provide valuable feedback for our next major operating system update for HoloLens.</span></span>

## <a name="windows-insider-release-notes"></a><span data-ttu-id="cab3b-106">Windows Opmerkingen bij de release van Insider</span><span class="sxs-lookup"><span data-stu-id="cab3b-106">Windows Insider Release Notes</span></span>

<span data-ttu-id="cab3b-107">We zijn blij om weer nieuwe functies te kunnen Windows Insiders.</span><span class="sxs-lookup"><span data-stu-id="cab3b-107">We're excited to start flighting new features to Windows Insiders again.</span></span> <span data-ttu-id="cab3b-108">Nieuwe builds worden naar de dev- en bètakanalen gerouteert voor de nieuwste updates.</span><span class="sxs-lookup"><span data-stu-id="cab3b-108">New builds will be flighting to the Dev and Beta Channels for the latest updates.</span></span> <span data-ttu-id="cab3b-109">We blijven deze pagina bijwerken wanneer we meer functies en updates toevoegen aan onze Windows Insider-builds.</span><span class="sxs-lookup"><span data-stu-id="cab3b-109">We will continue to update this page as we add more features and updates to our Windows Insider builds.</span></span> <span data-ttu-id="cab3b-110">Word enthousiast en bereid u voor om deze updates in uw realiteit te combineren.</span><span class="sxs-lookup"><span data-stu-id="cab3b-110">Get excited and ready to mix these updates into your reality.</span></span>

| <span data-ttu-id="cab3b-111">Functie</span><span class="sxs-lookup"><span data-stu-id="cab3b-111">Feature</span></span>                 | <span data-ttu-id="cab3b-112">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="cab3b-112">Description</span></span>                | <span data-ttu-id="cab3b-113">Gebruiker of scenario</span><span class="sxs-lookup"><span data-stu-id="cab3b-113">User or Scenario</span></span> | <span data-ttu-id="cab3b-114">Build geïntroduceerd</span><span class="sxs-lookup"><span data-stu-id="cab3b-114">Build introduced</span></span> |
|-------------------------|----------------------------|--------------|------------------|
| [<span data-ttu-id="cab3b-115">CSP-wijzigingen voor rapportagegegevens HoloLens details</span><span class="sxs-lookup"><span data-stu-id="cab3b-115">CSP changes for reporting HoloLens details</span></span>](#csp-changes-for-reporting-hololens-details) | <span data-ttu-id="cab3b-116">Nieuwe CSP's voor om query's uit te voeren op gegevens</span><span class="sxs-lookup"><span data-stu-id="cab3b-116">New CSPs for to query data</span></span> | <span data-ttu-id="cab3b-117">IT-beheerders</span><span class="sxs-lookup"><span data-stu-id="cab3b-117">IT Admins</span></span>    | <span data-ttu-id="cab3b-118">20348.1403</span><span class="sxs-lookup"><span data-stu-id="cab3b-118">20348.1403</span></span>                 |
| [<span data-ttu-id="cab3b-119">Beleid voor automatisch aanmelden beheerd door CSP</span><span class="sxs-lookup"><span data-stu-id="cab3b-119">Auto login policy controlled by CSP</span></span>](#auto-login-policy-controlled-by-csp) | <span data-ttu-id="cab3b-120">Wordt gebruikt om automatisch aan te melden bij een account</span><span class="sxs-lookup"><span data-stu-id="cab3b-120">Used to log in an account automatically</span></span> | <span data-ttu-id="cab3b-121">IT-beheerders</span><span class="sxs-lookup"><span data-stu-id="cab3b-121">IT Admins</span></span> | <span data-ttu-id="cab3b-122">20348.1405</span><span class="sxs-lookup"><span data-stu-id="cab3b-122">20348.1405</span></span> |
| [<span data-ttu-id="cab3b-123">Ondersteuning van PFX-bestanden voor Certificaatbeheer</span><span class="sxs-lookup"><span data-stu-id="cab3b-123">PFX file support for Certificate Manager</span></span>](#pfx-file-support-for-certificate-manager) | <span data-ttu-id="cab3b-124">PFX-certificaten toevoegen via Instellingen UI</span><span class="sxs-lookup"><span data-stu-id="cab3b-124">Add PFX certs via Settings UI</span></span> | <span data-ttu-id="cab3b-125">Eindgebruiker</span><span class="sxs-lookup"><span data-stu-id="cab3b-125">End User</span></span> | <span data-ttu-id="cab3b-126">20348.1405</span><span class="sxs-lookup"><span data-stu-id="cab3b-126">20348.1405</span></span> |
| [<span data-ttu-id="cab3b-127">Geavanceerd diagnostisch rapport weergeven in Instellingen op HoloLens</span><span class="sxs-lookup"><span data-stu-id="cab3b-127">View advanced diagnostic report in Settings on HoloLens</span></span>](#view-advanced-diagnostic-report-in-settings-on-hololens) | <span data-ttu-id="cab3b-128">Diagnostische MDM-logboeken op het apparaat weergeven</span><span class="sxs-lookup"><span data-stu-id="cab3b-128">View MDM diagnostic logs on device</span></span> | <span data-ttu-id="cab3b-129">Problemen oplossen</span><span class="sxs-lookup"><span data-stu-id="cab3b-129">Troubleshooting</span></span> | <span data-ttu-id="cab3b-130">20348.1405</span><span class="sxs-lookup"><span data-stu-id="cab3b-130">20348.1405</span></span> |
| [<span data-ttu-id="cab3b-131">Offline diagnostische meldingen</span><span class="sxs-lookup"><span data-stu-id="cab3b-131">Offline Diagnostics notifications</span></span>](#offline-diagnostics-notifications) | <span data-ttu-id="cab3b-132">Feedback geven over het verzamelen van logboeken</span><span class="sxs-lookup"><span data-stu-id="cab3b-132">Audiovisual feedback for log collection</span></span> | <span data-ttu-id="cab3b-133">Problemen oplossen</span><span class="sxs-lookup"><span data-stu-id="cab3b-133">Troubleshooting</span></span> | <span data-ttu-id="cab3b-134">20348.1405</span><span class="sxs-lookup"><span data-stu-id="cab3b-134">20348.1405</span></span> |


### <a name="csp-changes-for-reporting-hololens-details"></a><span data-ttu-id="cab3b-135">CSP-wijzigingen voor rapportagegegevens HoloLens details</span><span class="sxs-lookup"><span data-stu-id="cab3b-135">CSP changes for reporting HoloLens details</span></span>

- <span data-ttu-id="cab3b-136">Geïntroduceerd in Windows Insider-build, 20348.1403</span><span class="sxs-lookup"><span data-stu-id="cab3b-136">Introduced in Windows Insider build, 20348.1403</span></span>

<span data-ttu-id="cab3b-137">De volgende CSP's zijn bijgewerkt met nieuwe manieren om informatie van uw HoloLens rapporteren.</span><span class="sxs-lookup"><span data-stu-id="cab3b-137">The following CSPs have been updated with new ways to report information from your HoloLens devices.</span></span>

#### <a name="devdetail-csp---free-storage"></a><span data-ttu-id="cab3b-138">DevDetail CSP - Gratis Storage</span><span class="sxs-lookup"><span data-stu-id="cab3b-138">DevDetail CSP - Free Storage</span></span>

<span data-ttu-id="cab3b-139">DevDetail CSP rapporteert nu ook vrije opslagruimte op HoloLens apparaat.</span><span class="sxs-lookup"><span data-stu-id="cab3b-139">DevDetail CSP now also reports free storage space on HoloLens device.</span></span> <span data-ttu-id="cab3b-140">Dit moet ongeveer overeenkomen met de waarde die wordt weergegeven op Instellingen pagina van Storage app.</span><span class="sxs-lookup"><span data-stu-id="cab3b-140">This should approximately match with the value shown in Settings App's Storage page.</span></span> <span data-ttu-id="cab3b-141">Hieronder vindt u het specifieke knooppunt met deze informatie.</span><span class="sxs-lookup"><span data-stu-id="cab3b-141">Following is the specific node containing this information.</span></span>

- <span data-ttu-id="cab3b-142">./DevDetail/Ext/Microsoft/FreeStorage (alleen GET-bewerking)</span><span class="sxs-lookup"><span data-stu-id="cab3b-142">./DevDetail/Ext/Microsoft/FreeStorage (GET operation only)</span></span>

#### <a name="devicestatus-csp---ssid-and-bssid"></a><span data-ttu-id="cab3b-143">DeviceStatus CSP - SSID en BSSID</span><span class="sxs-lookup"><span data-stu-id="cab3b-143">DeviceStatus CSP - SSID and BSSID</span></span>

<span data-ttu-id="cab3b-144">DeviceStatus CSP rapporteert nu ook SSID en BSSID van Wi-Fi netwerk waarmee HoloLens actief is verbonden.</span><span class="sxs-lookup"><span data-stu-id="cab3b-144">DeviceStatus CSP now also reports SSID and BSSID of Wi-Fi network with which HoloLens is actively connected.</span></span> <span data-ttu-id="cab3b-145">Hieronder vindt u de specifieke knooppunten die deze informatie bevatten.</span><span class="sxs-lookup"><span data-stu-id="cab3b-145">Following are the specific nodes containing this information.</span></span>

- <span data-ttu-id="cab3b-146">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac-adres van Wi-Fi adapter*/SSID</span><span class="sxs-lookup"><span data-stu-id="cab3b-146">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/SSID</span></span>
- <span data-ttu-id="cab3b-147">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac-adres van Wi-Fi adapter*/BSSID</span><span class="sxs-lookup"><span data-stu-id="cab3b-147">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/BSSID</span></span>

<span data-ttu-id="cab3b-148">Voorbeeld van syncml-blob (voor MDM-leveranciers) om een query uit te voeren voor NetworkIdentifiers</span><span class="sxs-lookup"><span data-stu-id="cab3b-148">Example syncml blob (for MDM vendors) to query for NetworkIdentifiers</span></span>

```xml
<SyncML>
<SyncBody>
    <Get>
        <CmdID>$CmdID$</CmdID>
        <Item>
            <Target>
            <LocURI>
                ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers?list=StructData
            </LocURI>
            </Target>
        </Item>
    </Get>
    <Final/>
</SyncBody>
</SyncML>
```

### <a name="auto-login-policy-controlled-by-csp"></a><span data-ttu-id="cab3b-149">Beleid voor automatisch aanmelden beheerd door CSP</span><span class="sxs-lookup"><span data-stu-id="cab3b-149">Auto login policy controlled by CSP</span></span>

<span data-ttu-id="cab3b-150">Met dit nieuwe beleid AutoLogonUser bepaalt u of een gebruiker automatisch wordt aangemeld.</span><span class="sxs-lookup"><span data-stu-id="cab3b-150">This new AutoLogonUser policy controls whether a user will be automatically logged on.</span></span> <span data-ttu-id="cab3b-151">Sommige klanten willen apparaten instellen die zijn gekoppeld aan een identiteit, maar geen aanmeldingservaring willen.</span><span class="sxs-lookup"><span data-stu-id="cab3b-151">Some customers want to set up devices that are tied to an identity but don't want any sign-in experience.</span></span> <span data-ttu-id="cab3b-152">Imagine apparaat ophalen en direct hulp op afstand gebruiken.</span><span class="sxs-lookup"><span data-stu-id="cab3b-152">Imagine picking up a device and using remote assist immediately.</span></span> <span data-ttu-id="cab3b-153">Of hebben een voordeel van het snel distribueren van HoloLens apparaten en hun eindgebruikers in staat stellen zich sneller aan te melden.</span><span class="sxs-lookup"><span data-stu-id="cab3b-153">Or have a benefit of being able to rapidly  distribute HoloLens devices and enable their end users to expedite login.</span></span>

<span data-ttu-id="cab3b-154">Wanneer het beleid is ingesteld op een niet-lege waarde, wordt het e-mailadres van de gebruiker voor automatische aanmelding opgegeven.</span><span class="sxs-lookup"><span data-stu-id="cab3b-154">When the policy is set to a non-empty value, it specifies the email address of the auto-logon user.</span></span> <span data-ttu-id="cab3b-155">De opgegeven gebruiker moet zich ten minste één keer bij het apparaat laten aanmelding inschakelen.</span><span class="sxs-lookup"><span data-stu-id="cab3b-155">The specified user must logon to the device at least once to enable auto-logon.</span></span>

<span data-ttu-id="cab3b-156">De OMA-URI van nieuwe `./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser` beleidsreekswaarde</span><span class="sxs-lookup"><span data-stu-id="cab3b-156">The OMA-URI of new policy `./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser` String value</span></span>

- <span data-ttu-id="cab3b-157">De gebruiker met hetzelfde e-mailadres heeft automatische aanmelding ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="cab3b-157">User with the same email address will have auto logon enabled.</span></span>

<span data-ttu-id="cab3b-158">Op een apparaat waarop dit beleid is geconfigureerd, moet de gebruiker die is opgegeven in het beleid ten minste één keer worden aanmelding.</span><span class="sxs-lookup"><span data-stu-id="cab3b-158">On a device where this policy is configured, the user specified in the policy will need to logon at least once.</span></span> <span data-ttu-id="cab3b-159">Als het apparaat na de eerste aanmelding opnieuw wordt opgestart, wordt de opgegeven gebruiker automatisch aangemeld.</span><span class="sxs-lookup"><span data-stu-id="cab3b-159">Subsequent reboots of the device after the first logon will have the specified user automatically logged on.</span></span> <span data-ttu-id="cab3b-160">Er wordt slechts één gebruiker voor automatische aanmelding ondersteund.</span><span class="sxs-lookup"><span data-stu-id="cab3b-160">Only a single auto-logon user is supported.</span></span> <span data-ttu-id="cab3b-161">Zodra deze is ingeschakeld, kan de automatisch aangemelde gebruiker zich niet meer handmatig afmelden.</span><span class="sxs-lookup"><span data-stu-id="cab3b-161">Once enabled, the automatically logged on user will not be able to log out manually.</span></span> <span data-ttu-id="cab3b-162">Als u zich als een andere gebruiker wilt laten aanmeldingen, moet het beleid eerst worden uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="cab3b-162">To logon as a different user, the policy must first be disabled.</span></span>

> [!NOTE]
> - <span data-ttu-id="cab3b-163">Voor sommige gebeurtenissen, zoals belangrijke updates van het besturingssysteem, moet de opgegeven gebruiker zich mogelijk opnieuw bij het apparaat laten aanmeldingen om automatisch aanmeldingsgedrag te hervatten.</span><span class="sxs-lookup"><span data-stu-id="cab3b-163">Some events such as major OS updates may require the specified user to logon to the device again to resume auto-logon behavior.</span></span> 
> - <span data-ttu-id="cab3b-164">Automatische aanmelding wordt alleen ondersteund voor MSA- en AAD-gebruikers.</span><span class="sxs-lookup"><span data-stu-id="cab3b-164">Auto-logon is only supported for MSA and AAD users.</span></span>

### <a name="pfx-file-support-for-certificate-manager"></a><span data-ttu-id="cab3b-165">Ondersteuning van PFX-bestanden voor Certificaatbeheer</span><span class="sxs-lookup"><span data-stu-id="cab3b-165">PFX file support for Certificate Manager</span></span>

<span data-ttu-id="cab3b-166">Geïntroduceerd in Windows Insider-build 20348.1405.</span><span class="sxs-lookup"><span data-stu-id="cab3b-166">Introduced in Windows Insider build 20348.1405.</span></span> <span data-ttu-id="cab3b-167">Er is nu ondersteuning toegevoegd aan [Certificaatbeheer om PFX-certificaten](certificate-manager.md) te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="cab3b-167">We’ve added support to the [Certificate Manager](certificate-manager.md) to now use .pfx certificates.</span></span> <span data-ttu-id="cab3b-168">Wanneer gebruikers naar **Instellingen** Update & Security Certificates gaan en Een certificaat installeren selecteren, ondersteunt de gebruikersinterface nu het  >    >  PFX-certificaatbestand. </span><span class="sxs-lookup"><span data-stu-id="cab3b-168">When users navigate to **Settings** > **Update & Security** > **Certificates**, and select **Install a certificate** the UI now supports .pfx certificate file.</span></span>
<span data-ttu-id="cab3b-169">Gebruikers kunnen een PFX-certificaat met een persoonlijke sleutel importeren in een gebruikers- of machineopslag.</span><span class="sxs-lookup"><span data-stu-id="cab3b-169">Users can import .pfx certificate, with private key, to user store or machine store.</span></span>

### <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a><span data-ttu-id="cab3b-170">Geavanceerd diagnostisch rapport weergeven in Instellingen op HoloLens</span><span class="sxs-lookup"><span data-stu-id="cab3b-170">View advanced diagnostic report in Settings on HoloLens</span></span>

<span data-ttu-id="cab3b-171">Voor beheerde apparaten bij het oplossen van problemen is het bevestigen dat een verwachte beleidsconfiguratie wordt toegepast een belangrijke stap.</span><span class="sxs-lookup"><span data-stu-id="cab3b-171">For managed devices when troubleshooting behavior, confirming that an expected policy configuration is applied is an important step.</span></span> <span data-ttu-id="cab3b-172">Voorheen moest dit voor deze nieuwe functie via MDM of in de buurt van het apparaat worden gedaan na het exporteren van diagnostische MDM-logboeken die zijn verzameld via  ->  **Instellingen-accounts** Toegang tot werk of  >  **school,** en selecteert u **Uw beheerlogboeken** exporteren en weergeven op een pc in de buurt.</span><span class="sxs-lookup"><span data-stu-id="cab3b-172">Previously to this new feature, this had to be done off device via MDM or near the device after exporting MDM diagnostic logs gathered via **Settings** -> **Accounts** > **Access work or school**, and select **Export your management logs** and viewed on a nearby PC.</span></span>

<span data-ttu-id="cab3b-173">De MDM-diagnostische gegevens kunnen nu worden weergegeven op het apparaat met behulp van de Edge-browser.</span><span class="sxs-lookup"><span data-stu-id="cab3b-173">Now the MDM Diagnostics can be viewed on device using the Edge browser.</span></span> <span data-ttu-id="cab3b-174">Als u het diagnostischE MDM-rapport eenvoudiger wilt weergeven, gaat u naar de pagina Werk of school openen en **selecteert u Geavanceerd diagnostisch rapport weergeven.**</span><span class="sxs-lookup"><span data-stu-id="cab3b-174">To more easily view the MDM Diagnostic report navigate to the Access work or school page, and select **View advanced diagnostic report**.</span></span> <span data-ttu-id="cab3b-175">Hiermee wordt het rapport gegenereerd en geopend in een nieuw Edge-venster.</span><span class="sxs-lookup"><span data-stu-id="cab3b-175">This will generate and open the report in a new Edge window.</span></span>

![Bekijk het geavanceerde diagnostische rapport in Instellingen app.](./images/view-advanced-diagnostic-report.jpg)

### <a name="offline-diagnostics-notifications"></a><span data-ttu-id="cab3b-177">Offline diagnostische meldingen</span><span class="sxs-lookup"><span data-stu-id="cab3b-177">Offline Diagnostics notifications</span></span>

<span data-ttu-id="cab3b-178">Dit is een update voor een bestaande functie met de [naam Offlinediagnose.](hololens-diagnostic-logs.md#offline-diagnostics)</span><span class="sxs-lookup"><span data-stu-id="cab3b-178">This an update for an existing feature called [Offline Diagnostics](hololens-diagnostic-logs.md#offline-diagnostics).</span></span> <span data-ttu-id="cab3b-179">Voorheen was er geen duidelijke indicator voor gebruikers dat ze de diagnostische verzameling hadden geactiveerd of dat deze was voltooid.</span><span class="sxs-lookup"><span data-stu-id="cab3b-179">Previously, there was no clear indicator to users that they had triggered diagnostic collection or it had completed.</span></span>
<span data-ttu-id="cab3b-180">Nu toegevoegd aan Windows Insider-builds, zijn er twee vormen feedback over offlinediagnose.</span><span class="sxs-lookup"><span data-stu-id="cab3b-180">Now added in Windows Insider builds, there are two forms of audiovisual feedback for Offline Diagnostics.</span></span> <span data-ttu-id="cab3b-181">De eerste zijn pop-upmeldingen die worden weergegeven voor zowel wanneer de verzameling wordt gestart als voltooid.</span><span class="sxs-lookup"><span data-stu-id="cab3b-181">The first being toasts notifications displayed for both when collection starts and completes.</span></span> <span data-ttu-id="cab3b-182">Deze worden weergegeven wanneer de gebruiker is aangemeld en visuals heeft.</span><span class="sxs-lookup"><span data-stu-id="cab3b-182">These will be displayed when the user is logged in and has visuals.</span></span>

![Pop-up voor het verzamelen van logboeken.](./images/logcollection1.jpg)

![Pop-up wanneer het verzamelen van logboeken is voltooid.](./images/logcollection2.jpg)
 
<span data-ttu-id="cab3b-185">Omdat gebruikers vaak offlinediagnose gebruiken als mechanisme voor het verzamelen van terugvallogboeken wanneer ze geen toegang hebben tot een weergave, zich niet kunnen aanmelden of zich nog steeds in OOBE kunnen aanmelden, wordt er ook een audio-cue afgespeeld wanneer logboeken worden verzameld.</span><span class="sxs-lookup"><span data-stu-id="cab3b-185">Because users often use Offline Diagnostics as a fallback log gathering mechanism for when they don’t have access to a display, can’t log-in or are still in OOBE there will also be an audio cue played when logs are gathered.</span></span> <span data-ttu-id="cab3b-186">Dit geluid wordt afgespeeld naast de pop-upmelding.</span><span class="sxs-lookup"><span data-stu-id="cab3b-186">This sound will be played in addition to the toast notification.</span></span>

<span data-ttu-id="cab3b-187">Deze nieuwe functie wordt ingeschakeld wanneer uw apparaat wordt bijgewerkt en hoeft niet te worden ingeschakeld of beheerd.</span><span class="sxs-lookup"><span data-stu-id="cab3b-187">This new feature will be enabled when your device updates, and doesn’t need to be enabled or managed.</span></span> <span data-ttu-id="cab3b-188">In elk geval dat deze nieuwe feedback niet kan worden weergegeven of gehoord, wordt offlinediagnose nog steeds gegenereerd.</span><span class="sxs-lookup"><span data-stu-id="cab3b-188">In any event that this new feedback cannot be displayed or heard, Offline Diagnostics will still be generated.</span></span>

<span data-ttu-id="cab3b-189">We hopen dat het met deze nieuwere toevoeging van feedback gemakkelijker is om diagnostische gegevens te verzamelen en sneller in staat te zijn om uw problemen op te lossen.</span><span class="sxs-lookup"><span data-stu-id="cab3b-189">We hope with this newer addition of audiovisual feedback it is easier to gather diagnostic data, and more quickly be able to troubleshoot your problems.</span></span>



### <a name="fixes-and-improvements"></a><span data-ttu-id="cab3b-190">Oplossingen en verbeteringen:</span><span class="sxs-lookup"><span data-stu-id="cab3b-190">Fixes and improvements:</span></span>

- <span data-ttu-id="cab3b-191">Er is een bekend probleem opgelost voor Apparaatportal er geen prompt [was om vergrendelde bestanden te downloaden.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)</span><span class="sxs-lookup"><span data-stu-id="cab3b-191">Fixed a [known issue for Device Portal where there was no prompt downloading locked files.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)</span></span>
- <span data-ttu-id="cab3b-192">Er is [een bekend probleem opgelost voor Apparaatportal met time-outs](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out) voor het uploaden en downloaden van bestanden.</span><span class="sxs-lookup"><span data-stu-id="cab3b-192">Fixed a [known issue for Device Portal with file upload and download time outs.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)</span></span>


## <a name="start-receiving-insider-builds"></a><span data-ttu-id="cab3b-193">Beginnen met het ontvangen van Insider-builds</span><span class="sxs-lookup"><span data-stu-id="cab3b-193">Start receiving Insider builds</span></span>

> [!NOTE]
> <span data-ttu-id="cab3b-194">Als u het apparaat niet recent hebt bijgewerkt, start u het apparaat opnieuw op om de status bij te werken en de nieuwste build op te halen.</span><span class="sxs-lookup"><span data-stu-id="cab3b-194">If you haven’t updated recently, please reboot your device to update state and get the latest build.</span></span>
> - <span data-ttu-id="cab3b-195">De spraakopdracht 'Apparaat opnieuw opstarten' werkt goed.</span><span class="sxs-lookup"><span data-stu-id="cab3b-195">The “Reboot device” voice command works well.</span></span> 
> - <span data-ttu-id="cab3b-196">U kunt ook de knop Opnieuw opstarten kiezen in Instellingen/Windows Insider-programma.</span><span class="sxs-lookup"><span data-stu-id="cab3b-196">You can also choose the restart button in Settings/Windows Insider Program.</span></span>
>
> <span data-ttu-id="cab3b-197">Er is een fout in de back-end die u mogelijk hebt aangetroffen, zodat u weer op schema komt.</span><span class="sxs-lookup"><span data-stu-id="cab3b-197">We had a bug on the back-end that you may have encountered and this will get you back on track.</span></span>

<span data-ttu-id="cab3b-198">Ga op HoloLens 2 apparaat naar **Instellingen**  >  **Update & Security**  >  **Windows Insider-programma** en selecteer **Aan de slag.**</span><span class="sxs-lookup"><span data-stu-id="cab3b-198">On a HoloLens 2 device go to **Settings** > **Update & Security** > **Windows Insider Program** and select **Get started**.</span></span> <span data-ttu-id="cab3b-199">Koppel het account dat u hebt gebruikt om u te registreren als Windows Insider.</span><span class="sxs-lookup"><span data-stu-id="cab3b-199">Link the account you used to register as a Windows Insider.</span></span>

<span data-ttu-id="cab3b-200">Windows insider gaat nu over op Kanalen.</span><span class="sxs-lookup"><span data-stu-id="cab3b-200">Windows insider is now moving to Channels.</span></span> <span data-ttu-id="cab3b-201">De **fast-ring** wordt **het Dev-kanaal,** de langzame **ring** wordt de **bèta-kanaal** en de **Release Preview-ring** wordt het **Release Preview-kanaal.**</span><span class="sxs-lookup"><span data-stu-id="cab3b-201">The **Fast** ring will become the **Dev Channel**, the **Slow** ring will become the **Beta Channel**, and the **Release Preview** ring will become the **Release Preview Channel**.</span></span> <span data-ttu-id="cab3b-202">Deze toewijzing ziet er als volgende uit:</span><span class="sxs-lookup"><span data-stu-id="cab3b-202">Here is what that mapping looks like:</span></span>

![Windows Uitleg insider-kanalen](images/WindowsInsiderChannels.png)

<span data-ttu-id="cab3b-204">Zie [Introducing Windows Insider Channels (Introductie Windows Insider-kanalen)](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) op Windows Blogs.</span><span class="sxs-lookup"><span data-stu-id="cab3b-204">For more information, see [Introducing Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) on Windows Blogs.</span></span>
<span data-ttu-id="cab3b-205">Selecteer vervolgens **Actieve ontwikkeling van Windows**, kies of u **Dev Channel-** of **bèta-kanaal-builds** wilt ontvangen en bekijk de programmavoorwaarden.</span><span class="sxs-lookup"><span data-stu-id="cab3b-205">Then, select **Active development of Windows**, choose whether you'd like to receive **Dev Channel** or **Beta Channel** builds, and review the program terms.</span></span>
<span data-ttu-id="cab3b-206">Selecteer **Bevestigen > Nu opnieuw opstarten om** te voltooien.</span><span class="sxs-lookup"><span data-stu-id="cab3b-206">Select **Confirm > Restart Now** to finish up.</span></span> <span data-ttu-id="cab3b-207">Nadat het apparaat opnieuw is opgestart, gaat u naar **Instellingen > Update & Security > Controleren** op updates om de nieuwste build op te halen.</span><span class="sxs-lookup"><span data-stu-id="cab3b-207">After your device has rebooted, go to **Settings > Update & Security > Check for updates** to get the latest build.</span></span>

### <a name="update-error-0x80070490-work-around"></a><span data-ttu-id="cab3b-208">Updatefout 0x80070490 work-around</span><span class="sxs-lookup"><span data-stu-id="cab3b-208">Update error 0x80070490 work-around</span></span>

<span data-ttu-id="cab3b-209">Als er een updatefout wordt 0x80070490 bij het bijwerken op het kanaal Dev of Beta, kunt u de volgende kortetermijnwerkfase proberen.</span><span class="sxs-lookup"><span data-stu-id="cab3b-209">If you encounter an update error 0x80070490 when updating on the Dev or Beta channel, try the following short-term work around.</span></span> <span data-ttu-id="cab3b-210">Het omvat het verplaatsen van uw insider-kanaal, het ophalen van de update en vervolgens het terug verplaatsen van uw Insider-kanaal.</span><span class="sxs-lookup"><span data-stu-id="cab3b-210">It involves moving your insider channel, picking up the update and then moving your Insider channel back.</span></span>

#### <a name="stage-one---release-preview"></a><span data-ttu-id="cab3b-211">Fase 1 - releasevoorbeeld</span><span class="sxs-lookup"><span data-stu-id="cab3b-211">Stage one - Release Preview</span></span>

1.  <span data-ttu-id="cab3b-212">Instellingen, Update & Security en selecteer Windows Insider-programma **Release Preview Channel.**</span><span class="sxs-lookup"><span data-stu-id="cab3b-212">Settings, Update & Security, Windows Insider Program, select **Release Preview Channel**.</span></span>

2.  <span data-ttu-id="cab3b-213">Instellingen, & bijwerken, Windows Bijwerken, Controleren op **updates.**</span><span class="sxs-lookup"><span data-stu-id="cab3b-213">Settings, Update & Security, Windows Update, **Check for updates**.</span></span> <span data-ttu-id="cab3b-214">Na de update gaat u verder met Fase 2.</span><span class="sxs-lookup"><span data-stu-id="cab3b-214">After the update, continue on to Stage two.</span></span>

#### <a name="stage-two---dev-channel"></a><span data-ttu-id="cab3b-215">Fase 2 - Dev Channel</span><span class="sxs-lookup"><span data-stu-id="cab3b-215">Stage two - Dev Channel</span></span>

1. <span data-ttu-id="cab3b-216">Instellingen, Update & Security en Windows Insider-programma **Dev Channel.**</span><span class="sxs-lookup"><span data-stu-id="cab3b-216">Settings, Update & Security, Windows Insider Program, select **Dev Channel**.</span></span>

2. <span data-ttu-id="cab3b-217">Instellingen, & bijwerken, Windows Bijwerken, Controleren op **updates.**</span><span class="sxs-lookup"><span data-stu-id="cab3b-217">Settings, Update & Security, Windows Update, **Check for updates**.</span></span>

## <a name="ffu-download-and-flash-directions"></a><span data-ttu-id="cab3b-218">FFU-download- en flashbeschrijvingen</span><span class="sxs-lookup"><span data-stu-id="cab3b-218">FFU download and flash directions</span></span>

<span data-ttu-id="cab3b-219">Als u wilt testen met een ffu die is ondertekend met een vlucht, moet u eerst uw apparaat ontgrendelen voordat de ffu met een ondertekende vlucht wordt geflitst.</span><span class="sxs-lookup"><span data-stu-id="cab3b-219">To test with a flight signed ffu, you first have to flight unlock your device prior to flashing the flight signed ffu.</span></span>

1. <span data-ttu-id="cab3b-220">Op pc:</span><span class="sxs-lookup"><span data-stu-id="cab3b-220">On PC:</span></span>
    1. <span data-ttu-id="cab3b-221">Download ffu naar uw pc vanaf [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .</span><span class="sxs-lookup"><span data-stu-id="cab3b-221">Download ffu to your PC from [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload).</span></span>
    
    1. <span data-ttu-id="cab3b-222">Installeer ARC (Advanced Recovery Companion) vanuit de Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .</span><span class="sxs-lookup"><span data-stu-id="cab3b-222">Install ARC (Advanced Recovery Companion) from the Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span>
    
1. <span data-ttu-id="cab3b-223">On HoloLens- Flight Unlock: Open **Instellingen** Update & Security Windows Insider-programma registreer het apparaat en start  >    >   het opnieuw op.</span><span class="sxs-lookup"><span data-stu-id="cab3b-223">On HoloLens - Flight Unlock: Open **Settings** > **Update & Security** > **Windows Insider Program** then sign up, reboot device.</span></span>

1. <span data-ttu-id="cab3b-224">Flash-FFU: u kunt nu de met vlucht ondertekende FFU flashen met behulp van ARC.</span><span class="sxs-lookup"><span data-stu-id="cab3b-224">Flash FFU - Now you can flash the flight signed FFU using ARC.</span></span>

### <a name="provide-feedback-and-report-issues"></a><span data-ttu-id="cab3b-225">Feedback geven en problemen melden</span><span class="sxs-lookup"><span data-stu-id="cab3b-225">Provide feedback and report issues</span></span>

<span data-ttu-id="cab3b-226">Gebruik de [Feedback-hub-app op](hololens-feedback.md) uw HoloLens feedback te geven en problemen te melden.</span><span class="sxs-lookup"><span data-stu-id="cab3b-226">Please use [the Feedback Hub app](hololens-feedback.md) on your HoloLens to provide feedback and report issues.</span></span> <span data-ttu-id="cab3b-227">Door Feedback-hub zorgt u ervoor dat alle benodigde diagnostische gegevens worden opgenomen om onze technici te helpen het probleem snel op te sporen en op te lossen.</span><span class="sxs-lookup"><span data-stu-id="cab3b-227">Using Feedback Hub ensures that all necessary diagnostics information is included to help our engineers quickly debug and resolve the problem.</span></span>  <span data-ttu-id="cab3b-228">Problemen met de Chinese en Japanse versie van HoloLens moeten op dezelfde manier worden gerapporteerd.</span><span class="sxs-lookup"><span data-stu-id="cab3b-228">Issues with the Chinese and Japanese version of HoloLens should be reported the same way.</span></span>

> [!NOTE]
> <span data-ttu-id="cab3b-229">Zorg ervoor dat u de prompt accepteert waarin wordt gevraagd of u Feedback-hub documenten wilt openen (selecteer **Ja** wanneer u hier om wordt gevraagd).</span><span class="sxs-lookup"><span data-stu-id="cab3b-229">Be sure to accept the prompt that asks whether you'd like Feedback Hub to access your Documents folder (select **Yes** when prompted).</span></span>

## <a name="note-for-developers"></a><span data-ttu-id="cab3b-230">Opmerking voor ontwikkelaars</span><span class="sxs-lookup"><span data-stu-id="cab3b-230">Note for developers</span></span>

<span data-ttu-id="cab3b-231">U bent welkom en aangemoedigd om uw toepassingen te ontwikkelen met insider-builds van HoloLens.</span><span class="sxs-lookup"><span data-stu-id="cab3b-231">You are welcome and encouraged to try developing your applications using Insider builds of HoloLens.</span></span>  <span data-ttu-id="cab3b-232">Bekijk de documentatie [HoloLens ontwikkelaars om aan](https://developer.microsoft.com/windows/mixed-reality/development) de slag te gaan.</span><span class="sxs-lookup"><span data-stu-id="cab3b-232">Check out the [HoloLens Developer Documentation](https://developer.microsoft.com/windows/mixed-reality/development) to get started.</span></span> <span data-ttu-id="cab3b-233">Dezelfde instructies werken met Insider-builds van HoloLens.</span><span class="sxs-lookup"><span data-stu-id="cab3b-233">Those same instructions work with Insider builds of HoloLens.</span></span>  <span data-ttu-id="cab3b-234">U kunt dezelfde builds van Unity en Visual Studio die u al gebruikt voor HoloLens ontwikkeling.</span><span class="sxs-lookup"><span data-stu-id="cab3b-234">You can use the same builds of Unity and Visual Studio that you're already using for HoloLens development.</span></span>

## <a name="stop-receiving-insider-builds"></a><span data-ttu-id="cab3b-235">Geen Insider-builds meer ontvangen</span><span class="sxs-lookup"><span data-stu-id="cab3b-235">Stop receiving Insider builds</span></span>

<span data-ttu-id="cab3b-236">Als u geen Insider-builds van Windows Holographic meer wilt ontvangen, kunt u zich uitloggen wanneer uw [](hololens-recovery.md) HoloLens een productie-build wordt uitgevoerd. U kunt uw apparaat ook herstellen met de Advanced Recovery Companion om uw apparaat te herstellen naar een niet-Insider-versie van Windows Holographic.</span><span class="sxs-lookup"><span data-stu-id="cab3b-236">If you no longer want to receive Insider builds of Windows Holographic, you can opt out when your HoloLens is running a production build, or you can [recover your device](hololens-recovery.md) using the Advanced Recovery Companion to recover your device to a non-Insider version of Windows Holographic.</span></span>

> [!CAUTION]
> <span data-ttu-id="cab3b-237">Er is een bekend probleem waarbij gebruikers die de registratie van Insider Preview-builds ongedaan maken nadat ze handmatig een nieuwe preview-build hebben geïnstalleerd, een blauw scherm krijgen.</span><span class="sxs-lookup"><span data-stu-id="cab3b-237">There is a known issue in which users who un-enroll from Insider Preview builds after manually reinstalling a fresh preview build would experience a blue screen.</span></span> <span data-ttu-id="cab3b-238">Daarna moeten ze hun apparaat handmatig herstellen.</span><span class="sxs-lookup"><span data-stu-id="cab3b-238">Afterwards they must manually recover their device.</span></span> <span data-ttu-id="cab3b-239">Bekijk meer over dit bekende probleem voor meer informatie over of u hier al dan niet [mee te maken zou krijgen.](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)</span><span class="sxs-lookup"><span data-stu-id="cab3b-239">For full details on if you would be impacted or not, please view more on this [Known Issue](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build).</span></span>

<span data-ttu-id="cab3b-240">Om te controleren of uw HoloLens een productie-build wordt uitgevoerd:</span><span class="sxs-lookup"><span data-stu-id="cab3b-240">To verify that your HoloLens is running a production build:</span></span>

1. <span data-ttu-id="cab3b-241">Ga naar **Instellingen > System > About** en zoek het buildnummer.</span><span class="sxs-lookup"><span data-stu-id="cab3b-241">Go to **Settings > System > About**, and find the build number.</span></span>

1. <span data-ttu-id="cab3b-242">[Zie de releasenotities voor productie-buildnummers.](hololens-release-notes.md)</span><span class="sxs-lookup"><span data-stu-id="cab3b-242">[See the release notes for production build numbers](hololens-release-notes.md).</span></span>

<span data-ttu-id="cab3b-243">Als u zich wilt af melden voor Insider-builds:</span><span class="sxs-lookup"><span data-stu-id="cab3b-243">To opt out of Insider builds:</span></span>

1. <span data-ttu-id="cab3b-244">Ga op HoloLens een productie-build naar Update **Instellingen > & Security > Windows Insider-programma** en selecteer Stop Insider **builds.**</span><span class="sxs-lookup"><span data-stu-id="cab3b-244">On a HoloLens running a production build, go to **Settings > Update & Security > Windows Insider Program**, and select **Stop Insider builds**.</span></span>

1. <span data-ttu-id="cab3b-245">Volg de instructies om uw apparaat uit te kiezen.</span><span class="sxs-lookup"><span data-stu-id="cab3b-245">Follow the instructions to opt out your device.</span></span>
