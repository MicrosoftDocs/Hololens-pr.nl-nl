---
title: HoloLens Problemen met apparaten oplossen
description: Blijf op de hoogte van de meest voorkomende oplossingen voor HoloLens en probleemoplossingstechnieken.
author: mattzmsft
ms.author: mazeller
ms.date: 12/02/2019
ms.prod: hololens
ms.topic: article
audience: HoloLens
ms.localizationpriority: medium
manager: jarrettr
ms.custom:
- CI 111456
- CSSTroubleshooting
keywords: problemen, fout, probleem, oplossen, oplossen, hulp, ondersteuning, HoloLens, emulator
ms.openlocfilehash: b07514e73e43d267aa856c0fb9a256448e565000
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635446"
---
# <a name="device-troubleshooting"></a><span data-ttu-id="11839-104">Problemen met apparaten oplossen</span><span class="sxs-lookup"><span data-stu-id="11839-104">Device Troubleshooting</span></span>

<span data-ttu-id="11839-105">In dit artikel wordt beschreven hoe u verschillende veelvoorkomende problemen HoloLens oplossen.</span><span class="sxs-lookup"><span data-stu-id="11839-105">This article describes how to resolve several common HoloLens issues.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="11839-106">Voordat u een probleemoplossingsprocedure start, moet u ervoor zorgen dat uw apparaat, indien mogelijk, wordt op geladen tot **20 tot 40** procent van de accucapaciteit.</span><span class="sxs-lookup"><span data-stu-id="11839-106">Before you start any troubleshooting procedure, make sure that your device is charged to **20 to 40 percent** of battery capacity, if possible.</span></span> <span data-ttu-id="11839-107">De [accuindicatorlichten onder](hololens2-setup.md#lights-that-indicate-the-battery-level) de aan/uit-knop zijn een snelle manier om de accucapaciteit te controleren zonder u aan te melden bij het apparaat.</span><span class="sxs-lookup"><span data-stu-id="11839-107">The [battery indicator lights](hololens2-setup.md#lights-that-indicate-the-battery-level) located under the power button are a quick way to verify the battery capacity without logging into the device.</span></span>

<a id="list"></a>

<span data-ttu-id="11839-108">**Bekende problemen**</span><span class="sxs-lookup"><span data-stu-id="11839-108">**Known Issues**</span></span>
- [<span data-ttu-id="11839-109">Remote Assist video wordt na 20 minuten stil leggen</span><span class="sxs-lookup"><span data-stu-id="11839-109">Remote Assist video freezes after 20 minutes</span></span>](#remote-assist-video-freezes-after-20-minutes)
- [<span data-ttu-id="11839-110">Auto-login vraagt om aanmelden</span><span class="sxs-lookup"><span data-stu-id="11839-110">Auto-login asks for log-in</span></span>](#auto-login-asks-for-log-in)
- [<span data-ttu-id="11839-111">Microsoft Edge kan niet worden starten</span><span class="sxs-lookup"><span data-stu-id="11839-111">Microsoft Edge fails to launch</span></span>](#microsoft-edge-fails-to-launch)
- [<span data-ttu-id="11839-112">Toetsenbord schakelt niet over naar speciale tekens</span><span class="sxs-lookup"><span data-stu-id="11839-112">Keyboard doesn't switch to special characters</span></span>](#keyboard-doesnt-switch-to-special-characters)
- [<span data-ttu-id="11839-113">Er wordt geen fout weergegeven bij het downloaden van vergrendelde bestanden</span><span class="sxs-lookup"><span data-stu-id="11839-113">Downloading locked files doesn't show error</span></span>](#downloading-locked-files-doesnt-error)
- [<span data-ttu-id="11839-114">Apparaatportal voor het uploaden/downloaden van bestanden</span><span class="sxs-lookup"><span data-stu-id="11839-114">Device Portal file upload/download times out</span></span>](#device-portal-file-uploaddownload-times-out)
- [<span data-ttu-id="11839-115">Blauw scherm na uitschrijving van Insider Preview op een apparaat dat is geflitst met een Insider-build</span><span class="sxs-lookup"><span data-stu-id="11839-115">Blue screen after unenrolling from Insider preview on a device flashed with an Insider build</span></span>](#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)
- [<span data-ttu-id="11839-116">OneDrive uploadt niet automatisch afbeeldingen</span><span class="sxs-lookup"><span data-stu-id="11839-116">OneDrive doesn't automatically upload pictures</span></span>](#onedrive-doesnt-automatically-upload-pictures)

<span data-ttu-id="11839-117">**Algemeen**</span><span class="sxs-lookup"><span data-stu-id="11839-117">**General**</span></span>
- [<span data-ttu-id="11839-118">HoloLens reageert niet of start niet</span><span class="sxs-lookup"><span data-stu-id="11839-118">HoloLens is unresponsive or won't start</span></span>](#hololens-is-unresponsive-or-wont-start)
- [<span data-ttu-id="11839-119">Fout: 'Weinig schijfruimte'</span><span class="sxs-lookup"><span data-stu-id="11839-119">"Low Disk Space" error</span></span>](#low-disk-space-error)
- [<span data-ttu-id="11839-120">Mislukt de kalibratie</span><span class="sxs-lookup"><span data-stu-id="11839-120">Calibration Fails</span></span>](#calibration-fails)
- [<span data-ttu-id="11839-121">Kan niet aanmelden omdat mijn HoloLens eerder is ingesteld voor iemand anders</span><span class="sxs-lookup"><span data-stu-id="11839-121">Can't sign in because my HoloLens was previously set up for someone else</span></span>](#cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else)
- [<span data-ttu-id="11839-122">Unity werkt niet</span><span class="sxs-lookup"><span data-stu-id="11839-122">Unity isn't working</span></span>](#unity-isnt-working)
- [<span data-ttu-id="11839-123">Windows Apparaatportal werkt niet goed</span><span class="sxs-lookup"><span data-stu-id="11839-123">Windows Device Portal isn't working correctly</span></span>](#windows-device-portal-isnt-working-correctly)
- [<span data-ttu-id="11839-124">De HoloLens Emulator werkt niet</span><span class="sxs-lookup"><span data-stu-id="11839-124">The HoloLens Emulator isn't working</span></span>](#the-hololens-emulator-isnt-working)

<span data-ttu-id="11839-125">**Invoer**</span><span class="sxs-lookup"><span data-stu-id="11839-125">**Input**</span></span>
- [<span data-ttu-id="11839-126">Spraakopdrachten werken niet</span><span class="sxs-lookup"><span data-stu-id="11839-126">Voice commands aren't working</span></span>](#voice-commands-arent-working)
- [<span data-ttu-id="11839-127">Handinvoer werkt niet</span><span class="sxs-lookup"><span data-stu-id="11839-127">Hand input isn't working</span></span>](#hand-input-isnt-working)

<span data-ttu-id="11839-128">**Connectiviteit**</span><span class="sxs-lookup"><span data-stu-id="11839-128">**Connectivity**</span></span>
- [<span data-ttu-id="11839-129">Kan geen verbinding maken met Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="11839-129">Can't connect to Wi-Fi</span></span>](#cant-connect-to-wi-fi)

<span data-ttu-id="11839-130">**Externe apparaten**</span><span class="sxs-lookup"><span data-stu-id="11839-130">**External Devices**</span></span> 
- [<span data-ttu-id="11839-131">Bluetooth apparaten zijn niet gekoppeld</span><span class="sxs-lookup"><span data-stu-id="11839-131">Bluetooth devices aren't pairing</span></span>](#bluetooth-devices-arent-pairing)
- [<span data-ttu-id="11839-132">USB-C-microfoon werkt niet</span><span class="sxs-lookup"><span data-stu-id="11839-132">USB-C Microphone isn't working</span></span>](#usb-c-microphone-isnt-working)
- [<span data-ttu-id="11839-133">Apparaten die worden vermeld als beschikbaar in Instellingen werken niet</span><span class="sxs-lookup"><span data-stu-id="11839-133">Devices listed as available in Settings don't work</span></span>](#devices-listed-as-available-in-settings-dont-work)

## <a name="remote-assist-video-freezes-after-20-minutes"></a><span data-ttu-id="11839-134">Remote Assist video wordt na 20 minuten stil leggen</span><span class="sxs-lookup"><span data-stu-id="11839-134">Remote Assist video freezes after 20 minutes</span></span>

> [!NOTE]
> <span data-ttu-id="11839-135">Er is een nieuwere versie van Remote Assist met een oplossing voor dit probleem.</span><span class="sxs-lookup"><span data-stu-id="11839-135">There is a newer version of Remote Assist which has a fix for this issue.</span></span> <span data-ttu-id="11839-136">Werk [de Remote Assist](holographic-store-apps.md#update-apps) naar de nieuwste versie om dit probleem te voorkomen.</span><span class="sxs-lookup"><span data-stu-id="11839-136">Please [update Remote Assist](holographic-store-apps.md#update-apps) to the latest version to avoid this issue.</span></span>

> [!NOTE]
> <span data-ttu-id="11839-137">Vanwege de ernst van dit bekende probleem is de beschikbaarheid van Windows Holographic, versie 21H1, tijdelijk onderbroken.</span><span class="sxs-lookup"><span data-stu-id="11839-137">Due to this Known Issue's severity we had temporarily paused the availability of Windows Holographic, version 21H1.</span></span> <span data-ttu-id="11839-138">De build 21H1 is nu weer beschikbaar, dus apparaten kunnen opnieuw worden bijgewerkt naar de nieuwste 21H1-build.</span><span class="sxs-lookup"><span data-stu-id="11839-138">The 21H1 build is now available again, so devices may once again be updated to the latest 21H1 build.</span></span>

<span data-ttu-id="11839-139">In de nieuwste versie [van Windows Holographic, versie 21H1,](hololens-release-notes.md#windows-holographic-version-21h1)hebben sommige gebruikers van Remote Assist te maken gehad met video's die gedurende meer dan 20 minuten vast komen te staan tijdens oproepen.</span><span class="sxs-lookup"><span data-stu-id="11839-139">On the latest release of [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1), some users of Remote Assist have experienced video freezing during calls over 20 minutes.</span></span> <span data-ttu-id="11839-140">Dit is een **bekend probleem.**</span><span class="sxs-lookup"><span data-stu-id="11839-140">This is a **known issue**.</span></span>

### <a name="workarounds"></a><span data-ttu-id="11839-141">Tijdelijke oplossingen</span><span class="sxs-lookup"><span data-stu-id="11839-141">Workarounds</span></span>

<span data-ttu-id="11839-142">Als u de update niet kunt Remote Assist naar een nieuwere build, probeer dan de volgende stappen.</span><span class="sxs-lookup"><span data-stu-id="11839-142">If you are unable to update Remote Assist to a newer build try the following work around.</span></span>

#### <a name="restart-in-between-calls"></a><span data-ttu-id="11839-143">Opnieuw opstarten tussen aanroepen</span><span class="sxs-lookup"><span data-stu-id="11839-143">Restart in between calls</span></span>

<span data-ttu-id="11839-144">Als uw aanroepen langer dan 20 minuten duren en u dit probleem ondervindt, start u het apparaat opnieuw op.</span><span class="sxs-lookup"><span data-stu-id="11839-144">If your calls are going over a length of 20 minutes and you are experiencing this issue, try rebooting your device.</span></span> <span data-ttu-id="11839-145">Als u het apparaat opnieuw opstart Remote Assist de aanroepen, wordt uw apparaat vernieuwd en weer in een goede staat gezet.</span><span class="sxs-lookup"><span data-stu-id="11839-145">Rebooting your device between Remote Assist calls will refresh your device and put it back into a good state.</span></span>

<span data-ttu-id="11839-146">Als u een apparaat snel opnieuw wilt opstarten op Windows Holographic, opent u versie [21H1](hololens-release-notes.md#windows-holographic-version-21h1) het menu Start en selecteert u het gebruikerspictogram en selecteert u opnieuw **opstarten.**</span><span class="sxs-lookup"><span data-stu-id="11839-146">To quickly restart a device on [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) open the start menu, and select the user icon, then select **Restart**.</span></span>

[<span data-ttu-id="11839-147">Terug naar lijst</span><span class="sxs-lookup"><span data-stu-id="11839-147">Back to list</span></span>](#list)

## <a name="auto-login-asks-for-log-in"></a><span data-ttu-id="11839-148">Auto-login vraagt om aanmelden</span><span class="sxs-lookup"><span data-stu-id="11839-148">Auto-login asks for log-in</span></span>

<span data-ttu-id="11839-149">Een HoloLens 2 kan worden geconfigureerd om automatisch aan te melden via **aanmeldingsopties voor**  ->    ->  **Instellingen-accounts**  -> en onder Vereist de waarde in te stellen op **Nooit.**</span><span class="sxs-lookup"><span data-stu-id="11839-149">A HoloLens 2 device can be configured to automatically login in via **Settings** -> **Accounts** -> **Sign-in Options** -> and under **Required** setting the value to **Never**.</span></span> <span data-ttu-id="11839-150">Sommige gebruikers moeten zich mogelijk opnieuw aanmelden bij het apparaat bij het bijwerken van een apparaat met een aanzienlijk grote update, zoals een functie-update.</span><span class="sxs-lookup"><span data-stu-id="11839-150">Some users may be required to log-in to the device again when updating a device with a substantially large update, such as a feature update.</span></span> <span data-ttu-id="11839-151">Dit is een **bekend probleem.**</span><span class="sxs-lookup"><span data-stu-id="11839-151">This is a **known issue**.</span></span>

<span data-ttu-id="11839-152">Voorbeeld van wanneer dit kan gebeuren:</span><span class="sxs-lookup"><span data-stu-id="11839-152">Example of when this could occur:</span></span>

- <span data-ttu-id="11839-153">Een apparaat bijwerken van Windows Holographic versie 2004 (build 19041.xxxx) naar Windows Holographic, versie 21H1 (build 20346.xxxx)</span><span class="sxs-lookup"><span data-stu-id="11839-153">Updating a device from Windows Holographic, version 2004 (Build 19041.xxxx) to Windows Holographic, version 21H1 (Build 20346.xxxx)</span></span>
- <span data-ttu-id="11839-154">Een apparaat bijwerken voor een grote update op dezelfde grote build, bijvoorbeeld Windows Holographic, versie 2004 naar Windows Holographic, versie 20H2</span><span class="sxs-lookup"><span data-stu-id="11839-154">Updating a device to take a large update on the same major build, e.g. Windows Holographic, version 2004 to Windows Holographic, version 20H2</span></span>
- <span data-ttu-id="11839-155">Een apparaat bijwerken van een fabrieksafbeelding naar de nieuwste afbeelding</span><span class="sxs-lookup"><span data-stu-id="11839-155">Updating a device from a factory image to the latest image</span></span>

<span data-ttu-id="11839-156">Dit mag niet gebeuren tijdens:</span><span class="sxs-lookup"><span data-stu-id="11839-156">This should not occur during:</span></span>

- <span data-ttu-id="11839-157">Apparaten die een maandelijkse onderhoudsupdate ontvangen</span><span class="sxs-lookup"><span data-stu-id="11839-157">Devices taking a monthly servicing update</span></span>

<span data-ttu-id="11839-158">Methoden om te werken:</span><span class="sxs-lookup"><span data-stu-id="11839-158">Work around methods:</span></span>

- <span data-ttu-id="11839-159">Aanmeldingsmethoden zoals pincode, wachtwoord, iris, webverificatie of FIDO2-sleutels.</span><span class="sxs-lookup"><span data-stu-id="11839-159">Sign-in methods such as PIN, Password, Iris, Web Authentication, or FIDO2 keys.</span></span>
- <span data-ttu-id="11839-160">Als de pincode van het apparaat niet kan worden onthouden en andere verificatiemethoden niet beschikbaar zijn, kan een gebruiker de modus [voor handmatige reflashing gebruiken.](hololens-recovery.md#manual-procedure)</span><span class="sxs-lookup"><span data-stu-id="11839-160">If device PIN cannot be remembered, and other authentication methods are not available, then a user can use [manual reflashing mode](hololens-recovery.md#manual-procedure).</span></span>

[<span data-ttu-id="11839-161">Terug naar lijst</span><span class="sxs-lookup"><span data-stu-id="11839-161">Back to list</span></span>](#list)

## <a name="microsoft-edge-fails-to-launch"></a><span data-ttu-id="11839-162">Microsoft Edge kan niet worden starten</span><span class="sxs-lookup"><span data-stu-id="11839-162">Microsoft Edge fails to launch</span></span>

> [!NOTE]
> <span data-ttu-id="11839-163">Dit probleem is oorspronkelijk gemaakt met de verzendversie van Microsoft Edge rekening mee.</span><span class="sxs-lookup"><span data-stu-id="11839-163">This issue was originally created with the shipping version of Microsoft Edge in-mind.</span></span> <span data-ttu-id="11839-164">Dit probleem kan worden opgelost in de [nieuwe Microsoft Edge](hololens-new-edge.md).</span><span class="sxs-lookup"><span data-stu-id="11839-164">This issue may be resolved in the [new Microsoft Edge](hololens-new-edge.md).</span></span> <span data-ttu-id="11839-165">Als dat niet het zo is, kunt u feedback geven.</span><span class="sxs-lookup"><span data-stu-id="11839-165">If it is not, please file feedback.</span></span>

<span data-ttu-id="11839-166">Een aantal klanten heeft een probleem gerapporteerd waarbij Microsoft Edge kan worden gelanceerd.</span><span class="sxs-lookup"><span data-stu-id="11839-166">A few customers have reported an issue where Microsoft Edge fails to launch.</span></span> <span data-ttu-id="11839-167">Voor deze klanten blijft het probleem bestaan door opnieuw op te starten en wordt het niet opgelost met Windows of toepassingsupdates.</span><span class="sxs-lookup"><span data-stu-id="11839-167">For these customers, the issue persists through reboot and is not resolved with Windows or application updates.</span></span> <span data-ttu-id="11839-168">Als u dit probleem ondervindt en u hebt bevestigd dat [Windows up-to-date is,](hololens-updates.md#manually-check-for-updates)kunt u een fout in de [Feedback-hub-app](hololens-feedback.md) indienen met de volgende categorie en subcategorie: Installeren en bijwerken van > Downloaden, installeren en configureren van Windows Update.</span><span class="sxs-lookup"><span data-stu-id="11839-168">If you're experiencing this issue and you've confirmed [Windows is up-to-date](hololens-updates.md#manually-check-for-updates), please file a bug from the [Feedback Hub app](hololens-feedback.md) with the following category and sub-category: Install and Update > Downloading, installing, and configuring Windows Update.</span></span>

<span data-ttu-id="11839-169">Er zijn geen tijdelijke oplossingen bekend, omdat we het probleem tot nu toe niet hebben kunnen hoofdoorzaak van het probleem.</span><span class="sxs-lookup"><span data-stu-id="11839-169">There are no known workarounds as we've been unable to root cause the issue so far.</span></span> <span data-ttu-id="11839-170">Het indienen van een bug via Feedback-hub helpt ons onderzoek!</span><span class="sxs-lookup"><span data-stu-id="11839-170">Filing a bug via Feedback Hub will help our investigation!</span></span> <span data-ttu-id="11839-171">Dit is een **bekend probleem.**</span><span class="sxs-lookup"><span data-stu-id="11839-171">This is a **known issue**.</span></span>

[<span data-ttu-id="11839-172">Terug naar lijst</span><span class="sxs-lookup"><span data-stu-id="11839-172">Back to list</span></span>](#list)

## <a name="keyboard-doesnt-switch-to-special-characters"></a><span data-ttu-id="11839-173">Toetsenbord schakelt niet over naar speciale tekens</span><span class="sxs-lookup"><span data-stu-id="11839-173">Keyboard doesn't switch to special characters</span></span>

<span data-ttu-id="11839-174">Er is een probleem tijdens OOBE, waarbij wanneer de gebruiker een werk- of schoolaccount heeft gekozen en zijn of haar wachtwoord inschakelt, probeert over te schakelen naar de speciale tekens op het toetsenbord door op de knop &123 te tikken, er geen speciale tekens worden gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="11839-174">There is an issue during OOBE, where once the user has chosen a work or school account and is entering their password, trying to switch to the special characters on the keyboard by tapping the &123 button does not change to special characters.</span></span> <span data-ttu-id="11839-175">Dit is een **bekend probleem.**</span><span class="sxs-lookup"><span data-stu-id="11839-175">This is a **known issue**.</span></span>

<span data-ttu-id="11839-176">Work-arounds:</span><span class="sxs-lookup"><span data-stu-id="11839-176">Work-arounds:</span></span>
-   <span data-ttu-id="11839-177">Sluit het toetsenbord en open het opnieuw door op het tekstveld te tikken.</span><span class="sxs-lookup"><span data-stu-id="11839-177">Close the keyboard and reopen it by tapping the text field.</span></span>
-   <span data-ttu-id="11839-178">Voer ten onrechte uw wachtwoord in.</span><span class="sxs-lookup"><span data-stu-id="11839-178">Incorrectly enter your password.</span></span> <span data-ttu-id="11839-179">Wanneer het toetsenbord de volgende keer opnieuw wordt gelanceerd, werkt het zoals verwacht.</span><span class="sxs-lookup"><span data-stu-id="11839-179">When the keyboard is relaunched next time it will then work as expected.</span></span>
- <span data-ttu-id="11839-180">Webverificatie, sluit het toetsenbord en selecteer **Aanmelden vanaf een ander apparaat.**</span><span class="sxs-lookup"><span data-stu-id="11839-180">Web Authentication, close the keyboard and select **Sign in from another device**.</span></span>
-   <span data-ttu-id="11839-181">Als u alleen getallen intoetst, kan een gebruiker bepaalde sleutels indrukken en vasthouden om een uitgebreid menu te openen.</span><span class="sxs-lookup"><span data-stu-id="11839-181">If entering only numbers, a user may press and hold certain keys to open an expanded menu.</span></span>
-   <span data-ttu-id="11839-182">Met behulp van een USB-toetsenbord.</span><span class="sxs-lookup"><span data-stu-id="11839-182">Using a USB keyboard.</span></span>

<span data-ttu-id="11839-183">Dit heeft geen invloed op:</span><span class="sxs-lookup"><span data-stu-id="11839-183">This does not affect:</span></span>
- <span data-ttu-id="11839-184">Gebruikers die ervoor kiezen om een persoonlijk account te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="11839-184">Users who choose to use a personal account.</span></span>

[<span data-ttu-id="11839-185">Terug naar lijst</span><span class="sxs-lookup"><span data-stu-id="11839-185">Back to list</span></span>](#list)

## <a name="downloading-locked-files-doesnt-error"></a><span data-ttu-id="11839-186">Er wordt geen fout opgetreden bij het downloaden van vergrendelde bestanden</span><span class="sxs-lookup"><span data-stu-id="11839-186">Downloading locked files doesn't error</span></span>

> [!NOTE]
> <span data-ttu-id="11839-187">Dit is een **bekend probleem dat** is opgelost in Windows Insider-build, versie 20348.1403.</span><span class="sxs-lookup"><span data-stu-id="11839-187">This is a **known issue** that is fixed in Windows Insider build, version 20348.1403.</span></span>

<span data-ttu-id="11839-188">In eerdere versies van Windows Holographic zou het resultaat een HTTP-foutpagina zijn wanneer u probeert een vergrendeld bestand te downloaden.</span><span class="sxs-lookup"><span data-stu-id="11839-188">In previous builds of Windows Holographic, when attempting to download a locked file, the result would be an HTTP error page.</span></span> <span data-ttu-id="11839-189">In de Windows Holographic, update van versie 21H1, wordt geprobeerd een vergrendeld bestand te downloaden. Er gebeurt niets. Het bestand wordt niet gedownload en er is geen fout opgetreden.</span><span class="sxs-lookup"><span data-stu-id="11839-189">In the Windows Holographic, version 21H1 update, trying to download a locked file results in nothing visible happening—the file doesn’t download and there’s no error.</span></span>

[<span data-ttu-id="11839-190">Terug naar lijst</span><span class="sxs-lookup"><span data-stu-id="11839-190">Back to list</span></span>](#list)

## <a name="device-portal-file-uploaddownload-times-out"></a><span data-ttu-id="11839-191">Apparaatportal voor het uploaden/downloaden van bestanden</span><span class="sxs-lookup"><span data-stu-id="11839-191">Device Portal file upload/download times out</span></span>
> [!NOTE]
> <span data-ttu-id="11839-192">Dit is een **bekend probleem dat** is opgelost in Windows Insider-build, versie 20348.1403.</span><span class="sxs-lookup"><span data-stu-id="11839-192">This is a **known issue** that is fixed in Windows Insider build, version 20348.1403.</span></span> <span data-ttu-id="11839-193">Als u de SSL-verbinding eerder hebt uitgeschakeld als onderdeel van de tijdelijke oplossing, raden we u ten zeerste aan deze opnieuw in te stellen.</span><span class="sxs-lookup"><span data-stu-id="11839-193">If you previously disabled SSL Connection as part of the workaround, we highly recommend you re-enable it.</span></span>


<span data-ttu-id="11839-194">Sommige klanten hebben geconstateerd dat wanneer ze bestanden proberen te uploaden of downloaden, de bewerking lijkt vast te hangen en er vervolgens een time-out is of dat deze bewerking nooit is voltooid.</span><span class="sxs-lookup"><span data-stu-id="11839-194">Some customers have found, when attempting to upload or download files, the operation might appear to hang and then time out or never complete.</span></span> <span data-ttu-id="11839-195">Dit staat los van het bekende probleem['bestand](#downloading-locked-files-doesnt-error) vergrendeld'. Dit is van invloed op Windows Holographic, versies 2004, 20H2 en 21H1 in-market builds.</span><span class="sxs-lookup"><span data-stu-id="11839-195">This is separate from the '[file locked' known issue](#downloading-locked-files-doesnt-error) -- this affects Windows Holographic, versions 2004, 20H2 and 21H1 in-market builds.</span></span> <span data-ttu-id="11839-196">Het probleem is veroorzaakt door een fout in de Apparaatportal van bepaalde aanvragen en wordt het meest consistent getroffen bij het gebruik van https. Dit is de standaardinstelling.</span><span class="sxs-lookup"><span data-stu-id="11839-196">The problem has been root caused to a bug in Device Portal's handling of certain requests, and is most consistently hit when using https, which is the default.</span></span> 

### <a name="workaround"></a><span data-ttu-id="11839-197">Tijdelijke oplossing</span><span class="sxs-lookup"><span data-stu-id="11839-197">Workaround</span></span>

<span data-ttu-id="11839-198">Deze tijdelijke oplossing, die evenveel van toepassing is op Wi-Fi en UsbNcm, is het uitschakelen van de optie 'vereist' onder 'SSL-verbinding'.</span><span class="sxs-lookup"><span data-stu-id="11839-198">This workaround, which applies equally to Wi-Fi and UsbNcm, is to disable the "required" option under "SSL Connection".</span></span> <span data-ttu-id="11839-199">Ga om dit te doen naar Apparaatportal, **Systeem** en selecteer de **pagina Voorkeuren.**</span><span class="sxs-lookup"><span data-stu-id="11839-199">To do so, navigate to Device Portal, **System**, and select the **Preferences** page.</span></span> <span data-ttu-id="11839-200">Zoek in **de sectie Apparaatbeveiliging** de **optie SSL-verbinding** en schakel het selectievakje Vereist **uit.**</span><span class="sxs-lookup"><span data-stu-id="11839-200">In the **Device Security** section, locate **SSL Connection**, and uncheck to disable **Required**.</span></span>

<span data-ttu-id="11839-201">De gebruiker moet vervolgens naar http:// gaan, niet https:// (IP-adres) en functies zoals het uploaden en downloaden van bestanden werken.</span><span class="sxs-lookup"><span data-stu-id="11839-201">The user should then go to http://, not https:// (IP address) and features like file upload and download will work.</span></span>

[<span data-ttu-id="11839-202">Terug naar lijst</span><span class="sxs-lookup"><span data-stu-id="11839-202">Back to list</span></span>](#list)

## <a name="blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build"></a><span data-ttu-id="11839-203">Blauw scherm na uitschrijving van Insider Preview op een apparaat dat is geflitst met een Insider-build</span><span class="sxs-lookup"><span data-stu-id="11839-203">Blue screen after unenrolling from Insider preview on a device flashed with an Insider build</span></span>

<span data-ttu-id="11839-204">Dit is een probleem dat van invloed is op gebruikers die een Insider preview-build hebben gemaakt, hun HoloLens 2 hebben geslasht met een nieuwe insider preview-build en vervolgens zijn uitgeschreven bij het Insider-programma.</span><span class="sxs-lookup"><span data-stu-id="11839-204">This is an issue affecting that affects users who are were on an Insider preview build, reflashed their HoloLens 2 with a new insider preview build, and then unenrolled from the Insider program.</span></span> <span data-ttu-id="11839-205">Dit is een **bekend probleem.**</span><span class="sxs-lookup"><span data-stu-id="11839-205">This is a **known issue**.</span></span>

<span data-ttu-id="11839-206">Dit heeft geen invloed op:</span><span class="sxs-lookup"><span data-stu-id="11839-206">This does not affect:</span></span>
- <span data-ttu-id="11839-207">Gebruikers die niet zijn ingeschreven bij Windows Insider</span><span class="sxs-lookup"><span data-stu-id="11839-207">Users who are not enrolled in Windows Insider</span></span> 
- <span data-ttu-id="11839-208">Insiders:</span><span class="sxs-lookup"><span data-stu-id="11839-208">Insiders:</span></span>
    - <span data-ttu-id="11839-209">Als een apparaat is ingeschreven sinds Insider-builds versie 18362.x waren</span><span class="sxs-lookup"><span data-stu-id="11839-209">If a device has been enrolled since Insider builds were version 18362.x</span></span>
    - <span data-ttu-id="11839-210">Als ze een Insider-build 19041.x hebben gesigneerd en ingeschreven blijven in het Insider-programma</span><span class="sxs-lookup"><span data-stu-id="11839-210">If they flashed an Insider signed 19041.x build AND stay enrolled in the Insider program</span></span>

<span data-ttu-id="11839-211">Work-around:</span><span class="sxs-lookup"><span data-stu-id="11839-211">Work-around:</span></span> 
- <span data-ttu-id="11839-212">Vermijd het probleem</span><span class="sxs-lookup"><span data-stu-id="11839-212">Avoid the issue</span></span> 
    - <span data-ttu-id="11839-213">Flash een niet-insider build.</span><span class="sxs-lookup"><span data-stu-id="11839-213">Flash a non-insider build.</span></span> <span data-ttu-id="11839-214">Een van de regelmatige maandelijkse updates.</span><span class="sxs-lookup"><span data-stu-id="11839-214">One of the regular monthly updates.</span></span>
    - <span data-ttu-id="11839-215">Blijf op Insider Preview</span><span class="sxs-lookup"><span data-stu-id="11839-215">Stay on Insider Preview</span></span>
- <span data-ttu-id="11839-216">Reflash op het apparaat</span><span class="sxs-lookup"><span data-stu-id="11839-216">Reflash the device</span></span>

    1. <span data-ttu-id="11839-217">Plaats de [HoloLens 2 in de flashmodus](hololens-recovery.md) door volledig uit te schakelen terwijl u geen verbinding maakt.</span><span class="sxs-lookup"><span data-stu-id="11839-217">Put the [HoloLens 2 into flashing mode](hololens-recovery.md) manually by fully powering down while not connect.</span></span> <span data-ttu-id="11839-218">Tik vervolgens terwijl u Volume omhoog houdt op de aan/uit-knop.</span><span class="sxs-lookup"><span data-stu-id="11839-218">Then while holding Volume up, tap the Power button.</span></span>
    
    1. <span data-ttu-id="11839-219">Verbinding maken naar de pc en open Advanced Recovery Companion.</span><span class="sxs-lookup"><span data-stu-id="11839-219">Connect to the PC and open Advanced Recovery Companion.</span></span>
    
    1. <span data-ttu-id="11839-220">Flash de HoloLens 2 naar de standaard build.</span><span class="sxs-lookup"><span data-stu-id="11839-220">Flash the HoloLens 2 to the default build.</span></span>

[<span data-ttu-id="11839-221">Terug naar lijst</span><span class="sxs-lookup"><span data-stu-id="11839-221">Back to list</span></span>](#list)

## <a name="onedrive-doesnt-automatically-upload-pictures"></a><span data-ttu-id="11839-222">OneDrive uploadt niet automatisch afbeeldingen</span><span class="sxs-lookup"><span data-stu-id="11839-222">OneDrive doesn't automatically upload pictures</span></span>

<span data-ttu-id="11839-223">De OneDrive-app voor HoloLens biedt geen ondersteuning voor het automatisch uploaden van camera's voor werk- of schoolaccounts.</span><span class="sxs-lookup"><span data-stu-id="11839-223">The OneDrive app for HoloLens does not support automatic camera upload for work or school accounts.</span></span> <span data-ttu-id="11839-224">Dit is een **bekend probleem.**</span><span class="sxs-lookup"><span data-stu-id="11839-224">This is a **known issue**.</span></span>

<span data-ttu-id="11839-225">Oplossingen:</span><span class="sxs-lookup"><span data-stu-id="11839-225">Workarounds:</span></span>

- <span data-ttu-id="11839-226">Indien geschikt voor uw bedrijf, wordt automatisch uploaden van camera's ondersteund voor Microsoft-consumentenaccounts.</span><span class="sxs-lookup"><span data-stu-id="11839-226">If viable for your business, automatic camera upload is supported on consumer Microsoft accounts.</span></span> <span data-ttu-id="11839-227">U kunt zich aanmelden bij uw Microsoft-account naast uw werk- of schoolaccount (de OneDrive-app ondersteunt dubbele aanmelding).</span><span class="sxs-lookup"><span data-stu-id="11839-227">You can sign in to your Microsoft account in addition to your work or school account (the OneDrive app supports dual sign-in).</span></span> <span data-ttu-id="11839-228">Vanuit uw Microsoft-account in OneDrive kunt u automatisch uploaden van camera's op de achtergrond inschakelen.</span><span class="sxs-lookup"><span data-stu-id="11839-228">From your Microsoft account profile within OneDrive you can enable automatic, background camera roll upload.</span></span>

- <span data-ttu-id="11839-229">Als u een consumentenaccount niet veilig kunt Microsoft-account om uw foto's automatisch te uploaden, kunt u foto's handmatig uploaden naar uw werk- of schoolaccount vanuit de OneDrive app.</span><span class="sxs-lookup"><span data-stu-id="11839-229">If you cannot safely use a consumer Microsoft account for uploading your photos automatically, you can manually upload photos to your work or school account from the OneDrive app.</span></span> <span data-ttu-id="11839-230">Zorg ervoor dat u bent aangemeld bij uw werk- of schoolaccount in de OneDrive app.</span><span class="sxs-lookup"><span data-stu-id="11839-230">To do that, make sure you're signed into your work or school account in the OneDrive app.</span></span> <span data-ttu-id="11839-231">Selecteer de **+** knop en kies **Upload**.</span><span class="sxs-lookup"><span data-stu-id="11839-231">Select the **+** button and choose **Upload**.</span></span> <span data-ttu-id="11839-232">Zoek de foto's of video's die u wilt uploaden door te navigeren naar **Afbeeldingen > Camera Roll**.</span><span class="sxs-lookup"><span data-stu-id="11839-232">Find the photos or videos you want to upload by navigating to **Pictures > Camera Roll**.</span></span> <span data-ttu-id="11839-233">Selecteer de foto's of video's die u wilt uploaden en selecteer vervolgens de **knop** Openen.</span><span class="sxs-lookup"><span data-stu-id="11839-233">Select the photos or videos you want to upload, and then select the **Open** button.</span></span>

[<span data-ttu-id="11839-234">Terug naar lijst</span><span class="sxs-lookup"><span data-stu-id="11839-234">Back to list</span></span>](#list)

## <a name="hololens-is-unresponsive-or-wont-start"></a><span data-ttu-id="11839-235">HoloLens reageert niet of start niet</span><span class="sxs-lookup"><span data-stu-id="11839-235">HoloLens is unresponsive or won't start</span></span>

<span data-ttu-id="11839-236">Als uw HoloLens niet starten:</span><span class="sxs-lookup"><span data-stu-id="11839-236">If your HoloLens won't start:</span></span>

- <span data-ttu-id="11839-237">Als de LED's naast de aan/uit-knop niet worden licht of slechts één LED kort knippert, moet u mogelijk uw [HoloLens.](hololens2-charging.md#charging-the-device)</span><span class="sxs-lookup"><span data-stu-id="11839-237">If the LEDs next to the power button don't light up, or only one LED briefly blinks, you may need to [charge your HoloLens.](hololens2-charging.md#charging-the-device)</span></span>
- <span data-ttu-id="11839-238">Als de LED's worden weergegeven wanneer u op de aan/uit-knop drukt, maar er niets op de schermen wordt weergegeven, moet u het apparaat hard [opnieuw instellen.](hololens-recovery.md#hard-reset-procedure)</span><span class="sxs-lookup"><span data-stu-id="11839-238">If the LEDs light up when you press the power button but you can't see anything on the displays, [do a hard reset of the device](hololens-recovery.md#hard-reset-procedure).</span></span>

<span data-ttu-id="11839-239">Als uw HoloLens bevroren of niet meer reageert:</span><span class="sxs-lookup"><span data-stu-id="11839-239">If your HoloLens becomes frozen or unresponsive:</span></span>

- <span data-ttu-id="11839-240">Schakel uw HoloLens door op de aan/uit-knop te drukken totdat alle vijf de LED's zichzelf uitschakelen of 15 seconden lang als de led's niet reageren.</span><span class="sxs-lookup"><span data-stu-id="11839-240">Turn off your HoloLens by pressing the power button until all five of the LEDs turn themselves off, or for 15 seconds if the LEDs are unresponsive.</span></span> <span data-ttu-id="11839-241">Als u de HoloLens, drukt u opnieuw op de aan/uit-knop.</span><span class="sxs-lookup"><span data-stu-id="11839-241">To start your HoloLens, press the power button again.</span></span>

<span data-ttu-id="11839-242">Als deze stappen niet werken, [](hololens-recovery.md) kunt u proberen uw HoloLens 2 of een HoloLens [(1e generatie) te herstellen.](hololens1-recovery.md)</span><span class="sxs-lookup"><span data-stu-id="11839-242">If these steps don't work, you can try [recovering your HoloLens 2 device](hololens-recovery.md) or [HoloLens (1st gen) device.](hololens1-recovery.md)</span></span>

[<span data-ttu-id="11839-243">Terug naar lijst</span><span class="sxs-lookup"><span data-stu-id="11839-243">Back to list</span></span>](#list)

## <a name="low-disk-space-error"></a><span data-ttu-id="11839-244">Fout: 'Weinig schijfruimte'</span><span class="sxs-lookup"><span data-stu-id="11839-244">"Low Disk Space" error</span></span>

<span data-ttu-id="11839-245">U moet opslagruimte vrij maken door een of meer van de volgende dingen te doen:</span><span class="sxs-lookup"><span data-stu-id="11839-245">You'll need to free up some storage space by doing one or more of the following:</span></span>

- <span data-ttu-id="11839-246">Verwijder enkele ongebruikte spaties.</span><span class="sxs-lookup"><span data-stu-id="11839-246">Delete some unused spaces.</span></span> <span data-ttu-id="11839-247">Ga naar **Instellingen**  >  **systeemruimten,** selecteer een spatie die u niet meer nodig hebt  >  en selecteer **vervolgens Verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="11839-247">Go to **Settings** > **System** > **Spaces**, select a space that you no longer need, and then select **Remove**.</span></span>
- <span data-ttu-id="11839-248">Verwijder enkele hologrammen die u hebt geplaatst.</span><span class="sxs-lookup"><span data-stu-id="11839-248">Remove some of the holograms that you've placed.</span></span>
- <span data-ttu-id="11839-249">Verwijder enkele afbeeldingen en video's uit de Foto's app.</span><span class="sxs-lookup"><span data-stu-id="11839-249">Delete some pictures and videos from the Photos app.</span></span>
- <span data-ttu-id="11839-250">Verwijder enkele apps van uw HoloLens.</span><span class="sxs-lookup"><span data-stu-id="11839-250">Uninstall some apps from your HoloLens.</span></span> <span data-ttu-id="11839-251">Tik in **Alle apps** lijst op de app die u wilt verwijderen en houd deze in de wacht. Selecteer **vervolgens Verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="11839-251">In the **All apps** list, tap and hold the app you want to uninstall, and then select **Uninstall**.</span></span>

[<span data-ttu-id="11839-252">Terug naar lijst</span><span class="sxs-lookup"><span data-stu-id="11839-252">Back to list</span></span>](#list)

## <a name="calibration-fails"></a><span data-ttu-id="11839-253">Mislukt de kalibratie</span><span class="sxs-lookup"><span data-stu-id="11839-253">Calibration fails</span></span>

<span data-ttu-id="11839-254">Kalibratie zou voor de meeste mensen moeten werken, maar er zijn gevallen waarin de kalibratie mislukt.</span><span class="sxs-lookup"><span data-stu-id="11839-254">Calibration should work for most people, but there are cases where calibration fails.</span></span>
  
<span data-ttu-id="11839-255">Enkele mogelijke redenen voor het mislukken van de kalibratie zijn:</span><span class="sxs-lookup"><span data-stu-id="11839-255">Some potential reasons for calibration failure include:</span></span>

- <span data-ttu-id="11839-256">Afgeleid raken en de kalibratiedoelen niet volgen</span><span class="sxs-lookup"><span data-stu-id="11839-256">Getting distracted and not following the calibration targets</span></span>
- <span data-ttu-id="11839-257">Vervuilde of gekrast apparaat visor of apparaat visor niet goed geplaatst</span><span class="sxs-lookup"><span data-stu-id="11839-257">Dirty or scratched device visor or device visor not positioned properly</span></span>
- <span data-ttu-id="11839-258">Vervuilde of gekraste bril</span><span class="sxs-lookup"><span data-stu-id="11839-258">Dirty or scratched glasses</span></span>
- <span data-ttu-id="11839-259">Bepaalde soorten contactlenzen en bril (gekleurde contactlenzen, sommige tor-contactlenzen, blokkerende IR-bril, een bril met hoge bril, zonnebrillen of iets dergelijks)</span><span class="sxs-lookup"><span data-stu-id="11839-259">Certain types of contact lenses and glasses (colored contact lenses, some toric contact lenses, IR blocking glasses, some high prescription glasses, sunglasses, or similar)</span></span>
- <span data-ttu-id="11839-260">Meer uitgesprokenen en een aantal eyelash-extensies</span><span class="sxs-lookup"><span data-stu-id="11839-260">More-pronounced makeup and some eyelash extensions</span></span>
- <span data-ttu-id="11839-261">Frames met een haar of een dicht bril als ze blokkeren dat het apparaat uw ogen niet meer ziet</span><span class="sxs-lookup"><span data-stu-id="11839-261">Hair or thick eyeglass frames if they're blocking the device from seeing your eyes</span></span>
- <span data-ttu-id="11839-262">Bepaalde oogbuien, oogomstandigheden of oogoperaties, zoals smalle ogen, lange oogslashen, amblyopie, nystagmus, sommige gevallen van LASIK of andere oogpieken</span><span class="sxs-lookup"><span data-stu-id="11839-262">Certain eye physiology, eye conditions, or eye surgery such as narrow eyes, long eyelashes, amblyopia, nystagmus, some cases of LASIK or other eye surgeries</span></span>

<span data-ttu-id="11839-263">Als de kalibratie mislukt, probeert u het volgende:</span><span class="sxs-lookup"><span data-stu-id="11839-263">If calibration is unsuccessful try:</span></span>

- <span data-ttu-id="11839-264">Uw apparaat-visor opsporing</span><span class="sxs-lookup"><span data-stu-id="11839-264">Cleaning your device visor</span></span>
- <span data-ttu-id="11839-265">Uw bril opsnuurt</span><span class="sxs-lookup"><span data-stu-id="11839-265">Cleaning your glasses</span></span>
- <span data-ttu-id="11839-266">Uw apparaat-visor zo dicht mogelijk bij uw ogen pushen</span><span class="sxs-lookup"><span data-stu-id="11839-266">Pushing your device visor as close to your eyes as possible</span></span>
- <span data-ttu-id="11839-267">Objecten in uw visor uit de weg verplaatsen (zoals haar)</span><span class="sxs-lookup"><span data-stu-id="11839-267">Moving objects in your visor out of the way (such as hair)</span></span>
- <span data-ttu-id="11839-268">Een licht in uw kamer in- of uitschakelen</span><span class="sxs-lookup"><span data-stu-id="11839-268">Turning on a light in your room or moving out of direct sunlight</span></span>

<span data-ttu-id="11839-269">Als u alle richtlijnen hebt gevolgd en de kalibratie nog steeds mislukt, kunt u de prompt voor het kalibratieproces uitschakelen in Instellingen.</span><span class="sxs-lookup"><span data-stu-id="11839-269">If you followed all guidelines and calibration is still failing, you can disable the calibration prompt in Settings.</span></span> <span data-ttu-id="11839-270">Laat het ons ook weten door feedback in te dienen [Feedback-hub.](hololens-feedback.md)</span><span class="sxs-lookup"><span data-stu-id="11839-270">Also let us know by filing feedback in [Feedback Hub](hololens-feedback.md).</span></span>

<span data-ttu-id="11839-271">Zie ook gerelateerde informatie over het oplossen van problemen [met de kleur of helderheid van afbeeldingen.](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)</span><span class="sxs-lookup"><span data-stu-id="11839-271">Also see related information for [image color or brightness troubleshooting.](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)</span></span>

<span data-ttu-id="11839-272">Het instellen van IPD is niet van toepassing op HoloLens 2, omdat oogposities worden berekend door het systeem.</span><span class="sxs-lookup"><span data-stu-id="11839-272">Setting IPD is not applicable for HoloLens 2, since eye positions are computed by the system.</span></span> 

[<span data-ttu-id="11839-273">Terug naar lijst</span><span class="sxs-lookup"><span data-stu-id="11839-273">Back to list</span></span>](#list)

## <a name="cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else"></a><span data-ttu-id="11839-274">Kan niet aanmelden omdat mijn HoloLens eerder is ingesteld voor iemand anders</span><span class="sxs-lookup"><span data-stu-id="11839-274">Can't sign in because my HoloLens was previously set up for someone else</span></span>

<span data-ttu-id="11839-275">U kunt [het apparaat in de **flashmodus zetten** en Advanced Recovery Companion](hololens-recovery.md#clean-reflash-the-device) gebruiken om het apparaat te herstellen.</span><span class="sxs-lookup"><span data-stu-id="11839-275">You can [put the device into **Flashing Mode** and use Advanced Recovery Companion](hololens-recovery.md#clean-reflash-the-device) to recover the device.</span></span>

[<span data-ttu-id="11839-276">Terug naar lijst</span><span class="sxs-lookup"><span data-stu-id="11839-276">Back to list</span></span>](#list)


## <a name="unity-isnt-working"></a><span data-ttu-id="11839-277">Unity werkt niet</span><span class="sxs-lookup"><span data-stu-id="11839-277">Unity isn't working</span></span>

- <span data-ttu-id="11839-278">Zie [Install the tools](/windows/mixed-reality/install-the-tools) for the most-to-date version of Unity recommended for HoloLens development (De hulpprogramma's installeren voor de meest recente versie van Unity die wordt HoloLens ontwikkeling).</span><span class="sxs-lookup"><span data-stu-id="11839-278">See [Install the tools](/windows/mixed-reality/install-the-tools) for the most up-to-date version of Unity recommended for HoloLens development.</span></span>
- <span data-ttu-id="11839-279">Bekende problemen met de Unity HoloLens Technical Preview worden beschreven in de [HoloLens Unity-forums.](https://forum.unity3d.com/threads/known-issues.394627/)</span><span class="sxs-lookup"><span data-stu-id="11839-279">Known issues with the Unity HoloLens Technical Preview are documented in the [HoloLens Unity forums](https://forum.unity3d.com/threads/known-issues.394627/).</span></span>

[<span data-ttu-id="11839-280">Terug naar lijst</span><span class="sxs-lookup"><span data-stu-id="11839-280">Back to list</span></span>](#list)

## <a name="windows-device-portal-isnt-working-correctly"></a><span data-ttu-id="11839-281">Windows Apparaatportal werkt niet goed</span><span class="sxs-lookup"><span data-stu-id="11839-281">Windows Device Portal isn't working correctly</span></span>

- <span data-ttu-id="11839-282">De functie Live Preview in Mixed Reality capture kan enkele seconden latentie vertonen.</span><span class="sxs-lookup"><span data-stu-id="11839-282">The Live Preview feature in Mixed Reality capture may exhibit several seconds of latency.</span></span>

- <span data-ttu-id="11839-283">Op de pagina Virtuele invoer zijn de besturingselementen Beweging en Scroll onder de sectie Virtuele gebaren niet functioneel.</span><span class="sxs-lookup"><span data-stu-id="11839-283">On the Virtual Input page, the Gesture and Scroll controls under the Virtual Gestures section are not functional.</span></span> <span data-ttu-id="11839-284">Het gebruik ervan heeft geen effect.</span><span class="sxs-lookup"><span data-stu-id="11839-284">Using them will have no effect.</span></span> <span data-ttu-id="11839-285">Het virtuele toetsenbord op de virtuele invoerpagina werkt correct.</span><span class="sxs-lookup"><span data-stu-id="11839-285">The virtual keyboard on the virtual input page works correctly.</span></span>

- <span data-ttu-id="11839-286">Nadat u de ontwikkelaarsmodus in Instellingen ingeschakeld, kan het enkele seconden duren voordat de schakelknop is ingeschakeld Apparaatportal ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="11839-286">After enabling Developer Mode in Settings, it may take a few seconds before the switch to turn on the Device Portal is enabled.</span></span>

[<span data-ttu-id="11839-287">Terug naar lijst</span><span class="sxs-lookup"><span data-stu-id="11839-287">Back to list</span></span>](#list)

## <a name="the-hololens-emulator-isnt-working"></a><span data-ttu-id="11839-288">De HoloLens Emulator werkt niet</span><span class="sxs-lookup"><span data-stu-id="11839-288">The HoloLens Emulator isn't working</span></span>

<span data-ttu-id="11839-289">Informatie over de HoloLens emulator vindt u in onze documentatie voor ontwikkelaars.</span><span class="sxs-lookup"><span data-stu-id="11839-289">Information about the HoloLens emulator is located in our developer documentation.</span></span>  <span data-ttu-id="11839-290">Lees meer over het [oplossen van problemen met HoloLens emulator](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-hololens-emulator#troubleshooting).</span><span class="sxs-lookup"><span data-stu-id="11839-290">Read more about [troubleshooting the HoloLens emulator](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-hololens-emulator#troubleshooting).</span></span>


- <span data-ttu-id="11839-291">Niet alle apps in de Microsoft Store zijn compatibel met de emulator.</span><span class="sxs-lookup"><span data-stu-id="11839-291">Not all apps in the Microsoft Store are compatible with the emulator.</span></span> <span data-ttu-id="11839-292">Zo kunnen Young Conker en Fragmenten niet worden afspelen op de emulator.</span><span class="sxs-lookup"><span data-stu-id="11839-292">For example, Young Conker and Fragments are not playable on the emulator.</span></span>
- <span data-ttu-id="11839-293">U kunt de pc-webcam niet gebruiken in de Emulator.</span><span class="sxs-lookup"><span data-stu-id="11839-293">You cannot use the PC webcam in the Emulator.</span></span>
- <span data-ttu-id="11839-294">De functie Live Preview van de Windows Apparaatportal werkt niet met de emulator.</span><span class="sxs-lookup"><span data-stu-id="11839-294">The Live Preview feature of the Windows Device Portal does not work with the emulator.</span></span> <span data-ttu-id="11839-295">U kunt nog steeds Mixed Reality video's en afbeeldingen vastleggen.</span><span class="sxs-lookup"><span data-stu-id="11839-295">You can still capture Mixed Reality videos and images.</span></span>

[<span data-ttu-id="11839-296">Terug naar lijst</span><span class="sxs-lookup"><span data-stu-id="11839-296">Back to list</span></span>](#list)

## <a name="voice-commands-arent-working"></a><span data-ttu-id="11839-297">Spraakopdrachten werken niet</span><span class="sxs-lookup"><span data-stu-id="11839-297">Voice commands aren't working</span></span>

<span data-ttu-id="11839-298">Als Cortana niet reageert op uw spraakopdrachten, moet u ervoor zorgen dat Cortana is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="11839-298">If Cortana isn't responding to your voice commands, make sure Cortana is turned on.</span></span> <span data-ttu-id="11839-299">Selecteer in Alle apps lijst de **optie**  >  **Cortana Menu**  >  **Notebook**  >  **Instellingen** wijzigingen aan te brengen.</span><span class="sxs-lookup"><span data-stu-id="11839-299">On the All apps list, select **Cortana** > **Menu** > **Notebook** > **Settings** to make changes.</span></span> <span data-ttu-id="11839-300">Zie Uw stem gebruiken met HoloLens voor meer informatie [over wat u kunt HoloLens.](hololens-cortana.md)</span><span class="sxs-lookup"><span data-stu-id="11839-300">To learn more about what you can say, see [Use your voice with HoloLens](hololens-cortana.md).</span></span>

<span data-ttu-id="11839-301">Op HoloLens (eerste generatie) kan ingebouwde spraakherkenning niet worden geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="11839-301">On HoloLens (1st gen), built-in speech recognition is not configurable.</span></span> <span data-ttu-id="11839-302">Deze is altijd ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="11839-302">It is always turned on.</span></span> <span data-ttu-id="11839-303">Op HoloLens 2 kunt u kiezen of u zowel spraakherkenning als Cortana tijdens de installatie van het apparaat wilt inrichten.</span><span class="sxs-lookup"><span data-stu-id="11839-303">On HoloLens 2, you can choose whether to turn on both speech recognition and Cortana during device setup.</span></span>

<span data-ttu-id="11839-304">Als uw HoloLens 2 niet reageert op uw stem, zorgt u ervoor dat Spraakherkenning is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="11839-304">If your HoloLens 2 is not responding to your voice, make sure Speech recognition is turned on.</span></span> <span data-ttu-id="11839-305">Ga naar **Start**  >  **Instellingen**  >  **Privacy**  >  **Speech en** schakel **Spraakherkenning in.**</span><span class="sxs-lookup"><span data-stu-id="11839-305">Go to **Start** > **Settings** > **Privacy** > **Speech** and turn on **Speech recognition**.</span></span>

[<span data-ttu-id="11839-306">Terug naar lijst</span><span class="sxs-lookup"><span data-stu-id="11839-306">Back to list</span></span>](#list)

## <a name="hand-input-isnt-working"></a><span data-ttu-id="11839-307">Handinvoer werkt niet</span><span class="sxs-lookup"><span data-stu-id="11839-307">Hand input isn't working</span></span>

<span data-ttu-id="11839-308">Om ervoor te HoloLens dat u uw handen kunt zien, moet u ze in het bewegingsframe houden.</span><span class="sxs-lookup"><span data-stu-id="11839-308">To ensure that HoloLens can see your hands, you need to keep them in the gesture frame.</span></span>  <span data-ttu-id="11839-309">De Mixed Reality Start geeft feedback waarmee u kunt zien wanneer uw handen worden bijgespoord.</span><span class="sxs-lookup"><span data-stu-id="11839-309">The Mixed Reality Home provides feedback that lets you know when your hands are tracked.</span></span>  <span data-ttu-id="11839-310">De feedback verschilt van de verschillende versies van HoloLens:</span><span class="sxs-lookup"><span data-stu-id="11839-310">The feedback is different on different versions of HoloLens:</span></span>
- <span data-ttu-id="11839-311">Op HoloLens (eerste generatie) verandert de muisaanwijzer van een punt in een ring</span><span class="sxs-lookup"><span data-stu-id="11839-311">On HoloLens (1st gen), the gaze cursor changes from a dot to a ring</span></span>
- <span data-ttu-id="11839-312">Op HoloLens 2 wordt een cursor met de hand weergegeven wanneer uw hand zich dicht bij een slate en een hand ray wordt weergegeven wanneer de slates verder weg zijn</span><span class="sxs-lookup"><span data-stu-id="11839-312">On HoloLens 2, a fingertip cursor appears when your hand is close to a slate, and a hand ray appears when slates are further away</span></span>

<span data-ttu-id="11839-313">Veel in immersieve apps volgen invoerpatronen die vergelijkbaar zijn met Mixed Reality Start.</span><span class="sxs-lookup"><span data-stu-id="11839-313">Many immersive apps follow input patterns that are similar to Mixed Reality Home.</span></span>  <span data-ttu-id="11839-314">Meer informatie over het gebruik van [handinvoer op HoloLens (1e generatie)](hololens1-basic-usage.md#use-hololens-with-your-hands) en [HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame).</span><span class="sxs-lookup"><span data-stu-id="11839-314">Learn more about using hand input on [HoloLens (1st gen)](hololens1-basic-usage.md#use-hololens-with-your-hands) and [HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame).</span></span>

<span data-ttu-id="11839-315">Houd er rekening mee dat sommige typen schoenen niet werken met handtracking.</span><span class="sxs-lookup"><span data-stu-id="11839-315">If you are wearing gloves, note that some types of gloves do not work with hand tracking.</span></span>  <span data-ttu-id="11839-316">Een veelvoorkomende voorbeeld is zwarte rubberen pakken, die vaak licht van de diepte opnemen en niet worden opgepikt door de dieptecamera.</span><span class="sxs-lookup"><span data-stu-id="11839-316">A common example is black rubber gloves, which tend to absorb infrared light and are not picked up by the depth camera.</span></span>  <span data-ttu-id="11839-317">Als uw werk bestaat uit een elastiekje, raden we u aan om een lichtere kleur te gebruiken, zoals blauw of grijs.</span><span class="sxs-lookup"><span data-stu-id="11839-317">If your work involves rubber gloves, we recommend trying a lighter color such as blue or gray.</span></span>  <span data-ttu-id="11839-318">Een ander voorbeeld zijn grote baggy-pakken, die de vorm van uw hand doorgaans verborgen houden.</span><span class="sxs-lookup"><span data-stu-id="11839-318">Another example is large baggy gloves, which tend to obscure the shape of your hand.</span></span> <span data-ttu-id="11839-319">We raden u aan om de beste resultaten te krijgen door gebruik te maken van zo goed mogelijk vormfitting.</span><span class="sxs-lookup"><span data-stu-id="11839-319">We recommend using gloves that are as form-fitting as possible for best results.</span></span>

<span data-ttu-id="11839-320">Als uw visor vingerafdrukken of smudges heeft, gebruikt u de microfiberschoonmaak die bij de visor is HoloLens om uw visor op te schonen.</span><span class="sxs-lookup"><span data-stu-id="11839-320">If your visor has fingerprints or smudges, use the microfiber cleaning cloth that came with the HoloLens to clean your visor gently.</span></span>

[<span data-ttu-id="11839-321">Terug naar lijst</span><span class="sxs-lookup"><span data-stu-id="11839-321">Back to list</span></span>](#list)

## <a name="cant-connect-to-wi-fi"></a><span data-ttu-id="11839-322">Kan geen verbinding maken met Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="11839-322">Can't connect to Wi-Fi</span></span>

<span data-ttu-id="11839-323">Hier zijn enkele dingen die u kunt proberen als u uw netwerk niet kunt verbinden HoloLens een Wi-Fi netwerk:</span><span class="sxs-lookup"><span data-stu-id="11839-323">Here are some things to try if you can't connect your HoloLens to a Wi-Fi network:</span></span>

- <span data-ttu-id="11839-324">Zorg ervoor dat Wi-Fi is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="11839-324">Make sure that Wi-Fi is turned on.</span></span> <span data-ttu-id="11839-325">Als u dit wilt controleren, gebruikt u de beweging Starten en selecteert **u Instellingen**  >  **Wi-Fi &amp; voor netwerkinternet.**  >  </span><span class="sxs-lookup"><span data-stu-id="11839-325">To check, use the Start gesture, then select **Settings** > **Network &amp; Internet** > **Wi-Fi**.</span></span> <span data-ttu-id="11839-326">Als Wi-Fi is, probeert u deze uit te schakelen en vervolgens weer aan.</span><span class="sxs-lookup"><span data-stu-id="11839-326">If Wi-Fi is on, try turning it off and then on again.</span></span>
- <span data-ttu-id="11839-327">Ga dichter bij de router of het toegangspunt zitten.</span><span class="sxs-lookup"><span data-stu-id="11839-327">Move closer to the router or access point.</span></span>
- <span data-ttu-id="11839-328">Start uw Wi-Fi router opnieuw op en [start HoloLens](hololens-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="11839-328">Restart your Wi-Fi router, then [restart HoloLens](hololens-recovery.md).</span></span> <span data-ttu-id="11839-329">Probeer opnieuw verbinding te maken.</span><span class="sxs-lookup"><span data-stu-id="11839-329">Try connecting again.</span></span>
- <span data-ttu-id="11839-330">Als geen van deze dingen werkt, controleert u of uw router de meest recente firmware gebruikt.</span><span class="sxs-lookup"><span data-stu-id="11839-330">If none of these things work, check to make sure that your router is using the latest firmware.</span></span> <span data-ttu-id="11839-331">U vindt deze informatie op de website van de fabrikant.</span><span class="sxs-lookup"><span data-stu-id="11839-331">You can find this information on the manufacturer website.</span></span>

[<span data-ttu-id="11839-332">Terug naar lijst</span><span class="sxs-lookup"><span data-stu-id="11839-332">Back to list</span></span>](#list)

## <a name="bluetooth-devices-arent-pairing"></a><span data-ttu-id="11839-333">Bluetooth apparaten worden niet gekoppeld</span><span class="sxs-lookup"><span data-stu-id="11839-333">Bluetooth devices aren't pairing</span></span>

<span data-ttu-id="11839-334">Als u problemen hebt met het [koppelen van een Bluetooth apparaat,](hololens-connect-devices.md)probeert u het volgende:</span><span class="sxs-lookup"><span data-stu-id="11839-334">If you're having problems [pairing a Bluetooth device](hololens-connect-devices.md), try the following:</span></span>

- <span data-ttu-id="11839-335">Ga naar **Instellingen**  >  **Apparaten** en zorg ervoor dat Bluetooth is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="11839-335">Go to **Settings** > **Devices**, and make sure that Bluetooth is turned on.</span></span> <span data-ttu-id="11839-336">Als dat zo is, kunt u deze uitschakelen en opnieuw in- en uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="11839-336">If it is, turn it off and on again.</span></span>
- <span data-ttu-id="11839-337">Zorg ervoor dat uw Bluetooth volledig is geladen of dat het nieuwe accu's heeft.</span><span class="sxs-lookup"><span data-stu-id="11839-337">Make sure that your Bluetooth device is fully charged or has fresh batteries.</span></span>
- <span data-ttu-id="11839-338">Als u nog steeds geen verbinding kunt maken, start [u de HoloLens](hololens-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="11839-338">If you still can't connect, [restart the HoloLens](hololens-recovery.md).</span></span>

[<span data-ttu-id="11839-339">Terug naar lijst</span><span class="sxs-lookup"><span data-stu-id="11839-339">Back to list</span></span>](#list)

## <a name="usb-c-microphone-isnt-working"></a><span data-ttu-id="11839-340">USB-C-microfoon werkt niet</span><span class="sxs-lookup"><span data-stu-id="11839-340">USB-C Microphone isn't working</span></span>
<span data-ttu-id="11839-341">Let erop dat sommige USB-C-microfoons zichzelf ten onrechte als microfoon en *spreker* melden.</span><span class="sxs-lookup"><span data-stu-id="11839-341">Be aware that some USB-C microphones incorrectly report themselves as both a microphone *and* a speaker.</span></span> <span data-ttu-id="11839-342">Dit is een probleem met de microfoon en niet met HoloLens.</span><span class="sxs-lookup"><span data-stu-id="11839-342">This is a problem with the microphone and not with HoloLens.</span></span> <span data-ttu-id="11839-343">Wanneer u een van deze microfoons op het HoloLens, gaat het geluid mogelijk verloren.</span><span class="sxs-lookup"><span data-stu-id="11839-343">When plugging one of these microphones into HoloLens, sound may be lost.</span></span> <span data-ttu-id="11839-344">Gelukkig is er een eenvoudige oplossing.</span><span class="sxs-lookup"><span data-stu-id="11839-344">Fortunately there is a simple fix.</span></span>  

<span data-ttu-id="11839-345">In **Instellingen** System Sound stelt u de  ->    ->  ingebouwde sprekers **(Analog Feature Audio Driver)** expliciet in als **het standaardapparaat**.</span><span class="sxs-lookup"><span data-stu-id="11839-345">In **Settings** -> **System** -> **Sound**, explicitly set the built-in speakers **(Analog Feature Audio Driver)** as the **Default device**.</span></span> <span data-ttu-id="11839-346">HoloLens moet deze instelling onthouden, zelfs als de microfoon wordt verwijderd en later opnieuw wordt verbonden.</span><span class="sxs-lookup"><span data-stu-id="11839-346">HoloLens should remember this setting even if the microphone is removed and reconnected later.</span></span>

![Problemen met USB-C-microfoons oplossen](images/usbc-mic-4.png)

## <a name="devices-listed-as-available-in-settings-dont-work"></a><span data-ttu-id="11839-348">Apparaten die worden vermeld als beschikbaar in Instellingen werken niet</span><span class="sxs-lookup"><span data-stu-id="11839-348">Devices listed as available in Settings don't work</span></span>

<span data-ttu-id="11839-349">HoloLens (eerste generatie) biedt geen ondersteuning voor Bluetooth audioprofielen.</span><span class="sxs-lookup"><span data-stu-id="11839-349">HoloLens (1st gen) doesn't support Bluetooth audio profiles.</span></span> <span data-ttu-id="11839-350">Bluetooth audioapparaten, zoals sprekers en headsets, kunnen als beschikbaar worden weergegeven in HoloLens instellingen, maar worden niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="11839-350">Bluetooth audio devices, such as speakers and headsets, may appear as available in HoloLens settings, but they aren't supported.</span></span>

<span data-ttu-id="11839-351">HoloLens 2 biedt ondersteuning voor het Bluetooth A2DP-audioprofiel voor stereo afspelen.</span><span class="sxs-lookup"><span data-stu-id="11839-351">HoloLens 2 supports the Bluetooth A2DP audio profile for stereo playback.</span></span> <span data-ttu-id="11839-352">Het Bluetooth Hands Free-profiel waarmee microfoonopname van een Bluetooth randapparaat wordt niet ondersteund op HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="11839-352">The Bluetooth Hands Free profile which enables microphone capture from a Bluetooth peripheral is not supported on HoloLens 2.</span></span>

<span data-ttu-id="11839-353">Als u problemen hebt met het gebruik van Bluetooth apparaat, moet u ervoor zorgen dat het een ondersteund apparaat is.</span><span class="sxs-lookup"><span data-stu-id="11839-353">If you're having trouble using a Bluetooth device, make sure that it's a supported device.</span></span> <span data-ttu-id="11839-354">Ondersteunde apparaten zijn onder andere:</span><span class="sxs-lookup"><span data-stu-id="11839-354">Supported devices include the following:</span></span>

- <span data-ttu-id="11839-355">In het Engels QWERTY Bluetooth toetsenborden (u kunt deze overal gebruiken waar u het holografische toetsenbord gebruikt).</span><span class="sxs-lookup"><span data-stu-id="11839-355">English-language QWERTY Bluetooth keyboards (you can use these anywhere that you use the holographic keyboard).</span></span>
- <span data-ttu-id="11839-356">Bluetooth mice.</span><span class="sxs-lookup"><span data-stu-id="11839-356">Bluetooth mice.</span></span>
- <span data-ttu-id="11839-357">Klik [HoloLens de knop](hololens1-clicker.md).</span><span class="sxs-lookup"><span data-stu-id="11839-357">The [HoloLens clicker](hololens1-clicker.md).</span></span>

<span data-ttu-id="11839-358">U kunt andere BLUETOOTH EN GATT-apparaten koppelen aan uw HoloLens.</span><span class="sxs-lookup"><span data-stu-id="11839-358">You can pair other Bluetooth HID and GATT devices together with your HoloLens.</span></span> <span data-ttu-id="11839-359">Mogelijk moet u echter bijbehorende companion-apps installeren van Microsoft Store om de apparaten daadwerkelijk te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="11839-359">However, you may have to install corresponding companion apps from Microsoft Store to actually use the devices.</span></span>

[<span data-ttu-id="11839-360">Terug naar lijst</span><span class="sxs-lookup"><span data-stu-id="11839-360">Back to list</span></span>](#list)
