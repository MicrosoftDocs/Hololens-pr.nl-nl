---
title: Insider-preview voor Microsoft HoloLens
description: Leer hoe u aan de slag kunt gaan met Insider-builds en waardevolle feedback kunt geven voor onze volgende belangrijke update van het besturingssysteem voor HoloLens.
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
ms.openlocfilehash: a4949ab68121cb772fdb8a62411ed70868a6ccb6
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924363"
---
# <a name="insider-preview-for-microsoft-hololens"></a><span data-ttu-id="c6ba2-103">Insider-preview voor Microsoft HoloLens</span><span class="sxs-lookup"><span data-stu-id="c6ba2-103">Insider preview for Microsoft HoloLens</span></span>

<span data-ttu-id="c6ba2-104">Welkom bij de nieuwste Insider Preview-builds voor HoloLens.</span><span class="sxs-lookup"><span data-stu-id="c6ba2-104">Welcome to the latest Insider Preview builds for HoloLens!</span></span> <span data-ttu-id="c6ba2-105">Het is eenvoudig om aan de slag [te gaan](hololens-insider.md#start-receiving-insider-builds) en waardevolle feedback te geven voor onze volgende belangrijke update van het besturingssysteem voor HoloLens.</span><span class="sxs-lookup"><span data-stu-id="c6ba2-105">It's simple to [get started](hololens-insider.md#start-receiving-insider-builds) and provide valuable feedback for our next major operating system update for HoloLens.</span></span>

## <a name="windows-insider-release-notes"></a><span data-ttu-id="c6ba2-106">Windows Insider opmerkingen bij de release</span><span class="sxs-lookup"><span data-stu-id="c6ba2-106">Windows Insider Release Notes</span></span>

<span data-ttu-id="c6ba2-107">We zijn blij dat we weer nieuwe functies aan Windows Insiders kunnen toevoegen.</span><span class="sxs-lookup"><span data-stu-id="c6ba2-107">We're excited to start flighting new features to Windows Insiders again.</span></span> <span data-ttu-id="c6ba2-108">Nieuwe builds worden naar de dev- en bètakanalen gerouteert voor de nieuwste updates.</span><span class="sxs-lookup"><span data-stu-id="c6ba2-108">New builds will be flighting to the Dev and Beta Channels for the latest updates.</span></span> <span data-ttu-id="c6ba2-109">We blijven deze pagina bijwerken wanneer we meer functies en updates toevoegen aan onze Windows Insider builds.</span><span class="sxs-lookup"><span data-stu-id="c6ba2-109">We will continue to update this page as we add more features and updates to our Windows Insider builds.</span></span> <span data-ttu-id="c6ba2-110">Word enthousiast en bereid u voor om deze updates in uw realiteit te combineren.</span><span class="sxs-lookup"><span data-stu-id="c6ba2-110">Get excited and ready to mix these updates into your reality.</span></span> 

### <a name="csp-changes-on-hololens"></a><span data-ttu-id="c6ba2-111">CSP-wijzigingen in HoloLens</span><span class="sxs-lookup"><span data-stu-id="c6ba2-111">CSP changes on HoloLens</span></span>
 
- <span data-ttu-id="c6ba2-112">Geïntroduceerd in Windows Insider build, 20348.1403</span><span class="sxs-lookup"><span data-stu-id="c6ba2-112">Introduced in Windows Insider build, 20348.1403</span></span>

#### <a name="devdetail-csp"></a><span data-ttu-id="c6ba2-113">DevDetail CSP</span><span class="sxs-lookup"><span data-stu-id="c6ba2-113">DevDetail CSP</span></span>

<span data-ttu-id="c6ba2-114">DevDetail CSP rapporteert nu ook vrije opslagruimte op een HoloLens-apparaat.</span><span class="sxs-lookup"><span data-stu-id="c6ba2-114">DevDetail CSP now also reports free storage space on HoloLens device.</span></span> <span data-ttu-id="c6ba2-115">Dit moet ongeveer overeenkomen met de waarde die wordt weergegeven op de pagina Opslag van de app Instellingen.</span><span class="sxs-lookup"><span data-stu-id="c6ba2-115">This should approximately match with the value shown in Settings App's Storage page.</span></span> <span data-ttu-id="c6ba2-116">Hieronder vindt u het specifieke knooppunt met deze informatie.</span><span class="sxs-lookup"><span data-stu-id="c6ba2-116">Following is the specific node containing this information.</span></span>

- <span data-ttu-id="c6ba2-117">./DevDetail/Ext/Microsoft/FreeStorage (alleen GET-bewerking)</span><span class="sxs-lookup"><span data-stu-id="c6ba2-117">./DevDetail/Ext/Microsoft/FreeStorage (GET operation only)</span></span>

#### <a name="devicestatus-csp"></a><span data-ttu-id="c6ba2-118">DeviceStatus CSP</span><span class="sxs-lookup"><span data-stu-id="c6ba2-118">DeviceStatus CSP</span></span>

<span data-ttu-id="c6ba2-119">DeviceStatus CSP rapporteert nu ook SSID en BSSID van het Wifi-netwerk waarmee HoloLens actief is verbonden.</span><span class="sxs-lookup"><span data-stu-id="c6ba2-119">DeviceStatus CSP now also reports SSID and BSSID of Wifi network with which HoloLens is actively connected.</span></span> <span data-ttu-id="c6ba2-120">Hieronder vindt u de specifieke knooppunten die deze informatie bevatten.</span><span class="sxs-lookup"><span data-stu-id="c6ba2-120">Following are the specific nodes containing this information.</span></span>

- <span data-ttu-id="c6ba2-121">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac-adres van Wi-Fi adapter*/SSID</span><span class="sxs-lookup"><span data-stu-id="c6ba2-121">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/SSID</span></span>
- <span data-ttu-id="c6ba2-122">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac-adres van Wi-Fi adapter*/BSSID</span><span class="sxs-lookup"><span data-stu-id="c6ba2-122">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/BSSID</span></span>

<span data-ttu-id="c6ba2-123">Voorbeeld van syncml-blob (voor MDM-leveranciers) om een query uit te voeren voor NetworkIdentifiers</span><span class="sxs-lookup"><span data-stu-id="c6ba2-123">Example syncml blob (for MDM vendors) to query for NetworkIdentifiers</span></span>

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

### <a name="fixes-and-improvements"></a><span data-ttu-id="c6ba2-124">Oplossingen en verbeteringen:</span><span class="sxs-lookup"><span data-stu-id="c6ba2-124">Fixes and improvements:</span></span>

- <span data-ttu-id="c6ba2-125">Er is een bekend probleem opgelost voor Apparaatportal er geen prompt [was om vergrendelde bestanden te downloaden.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)</span><span class="sxs-lookup"><span data-stu-id="c6ba2-125">Fixed a [known issue for Device Portal where there was no prompt downloading locked files.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)</span></span>
- <span data-ttu-id="c6ba2-126">Er is [een bekend probleem opgelost voor Apparaatportal met time-outs voor](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out) het uploaden en downloaden van bestanden.</span><span class="sxs-lookup"><span data-stu-id="c6ba2-126">Fixed a [known issue for Device Portal with file upload and download time outs.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)</span></span>

## <a name="start-receiving-insider-builds"></a><span data-ttu-id="c6ba2-127">Beginnen met het ontvangen van Insider-builds</span><span class="sxs-lookup"><span data-stu-id="c6ba2-127">Start receiving Insider builds</span></span>
> [!NOTE]
> <span data-ttu-id="c6ba2-128">Als u het apparaat niet recent hebt bijgewerkt, start u het apparaat opnieuw op om de status bij te werken en de nieuwste build op te halen.</span><span class="sxs-lookup"><span data-stu-id="c6ba2-128">If you haven’t updated recently, please reboot your device to update state and get the latest build.</span></span>
> - <span data-ttu-id="c6ba2-129">De spraakopdracht 'Apparaat opnieuw opstarten' werkt goed.</span><span class="sxs-lookup"><span data-stu-id="c6ba2-129">The “Reboot device” voice command works well.</span></span> 
> - <span data-ttu-id="c6ba2-130">U kunt ook de knop Opnieuw opstarten kiezen in Instellingen/Windows Insider-programma.</span><span class="sxs-lookup"><span data-stu-id="c6ba2-130">You can also choose the restart button in Settings/Windows Insider Program.</span></span>
>
> <span data-ttu-id="c6ba2-131">Er is een fout in de back-end die u mogelijk hebt aangetroffen, zodat u weer op schema komt.</span><span class="sxs-lookup"><span data-stu-id="c6ba2-131">We had a bug on the back-end that you may have encountered and this will get you back on track.</span></span>

<span data-ttu-id="c6ba2-132">Ga op HoloLens 2 apparaat **naar**  >  **InstellingenUpdate & beveiligingsbeleid**  >  **Windows Insider-programma** selecteer **Aan de slag.**</span><span class="sxs-lookup"><span data-stu-id="c6ba2-132">On a HoloLens 2 device go to **Settings** > **Update & Security** > **Windows Insider Program** and select **Get started**.</span></span> <span data-ttu-id="c6ba2-133">Koppel het account dat u hebt gebruikt om u te registreren als Windows Insider.</span><span class="sxs-lookup"><span data-stu-id="c6ba2-133">Link the account you used to register as a Windows Insider.</span></span>
<span data-ttu-id="c6ba2-134">Windows Insider wordt nu verplaatst naar Kanalen.</span><span class="sxs-lookup"><span data-stu-id="c6ba2-134">Windows insider is now moving to Channels.</span></span> <span data-ttu-id="c6ba2-135">De **Fast-ring** wordt het **Dev-kanaal,** de langzame **ring** wordt de **bèta-kanaal** en de **Release Preview-ring** wordt het **Release Preview-kanaal.**</span><span class="sxs-lookup"><span data-stu-id="c6ba2-135">The **Fast** ring will become the **Dev Channel**, the **Slow** ring will become the **Beta Channel**, and the **Release Preview** ring will become the **Release Preview Channel**.</span></span> <span data-ttu-id="c6ba2-136">Hier ziet u hoe die toewijzing eruit ziet: Windows Insider Uitleg van kanalen Zie Introductie ![ ](images/WindowsInsiderChannels.png) Windows Insider [kanalen](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) in Windows-blogs voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="c6ba2-136">Here is what that mapping looks like: ![Windows Insider Channels explanation](images/WindowsInsiderChannels.png) For more information, see [Introducing Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) on Windows Blogs.</span></span>
<span data-ttu-id="c6ba2-137">Selecteer vervolgens **Actieve ontwikkeling van Windows,** kies of u het **Dev-kanaal** wilt ontvangen of bèta-kanaal **builds** en bekijk de programmavoorwaarden.</span><span class="sxs-lookup"><span data-stu-id="c6ba2-137">Then, select **Active development of Windows**, choose whether you'd like to receive **Dev Channel** or **Beta Channel** builds, and review the program terms.</span></span>
<span data-ttu-id="c6ba2-138">Selecteer **Bevestigen > Nu opnieuw opstarten om** te voltooien.</span><span class="sxs-lookup"><span data-stu-id="c6ba2-138">Select **Confirm > Restart Now** to finish up.</span></span> <span data-ttu-id="c6ba2-139">Nadat het apparaat opnieuw is opgestart, gaat u naar Instellingen **> Update & Security > Controleren** op updates om de meest recente build op te halen.</span><span class="sxs-lookup"><span data-stu-id="c6ba2-139">After your device has rebooted, go to **Settings > Update & Security > Check for updates** to get the latest build.</span></span>
### <a name="update-error-0x80070490-work-around"></a><span data-ttu-id="c6ba2-140">Updatefout 0x80070490 work-around</span><span class="sxs-lookup"><span data-stu-id="c6ba2-140">Update error 0x80070490 work-around</span></span>
<span data-ttu-id="c6ba2-141">Als er een updatefout wordt 0x80070490 bij het bijwerken op het kanaal Dev of Beta, probeert u de volgende kortetermijnversie.</span><span class="sxs-lookup"><span data-stu-id="c6ba2-141">If you encounter an update error 0x80070490 when updating on the Dev or Beta channel, try the following short-term work around.</span></span> <span data-ttu-id="c6ba2-142">Dit omvat het verplaatsen van uw insider-kanaal, het ophalen van de update en vervolgens het terug verplaatsen van uw Insider-kanaal.</span><span class="sxs-lookup"><span data-stu-id="c6ba2-142">It involves moving your insider channel, picking up the update and then moving your Insider channel back.</span></span>
#### <a name="stage-one---release-preview"></a><span data-ttu-id="c6ba2-143">Fase 1 - preview-versie</span><span class="sxs-lookup"><span data-stu-id="c6ba2-143">Stage one - Release Preview</span></span>
1.  <span data-ttu-id="c6ba2-144">Instellingen, Update & Beveiliging, Windows Insider-programma selecteer **Release Preview-kanaal.**</span><span class="sxs-lookup"><span data-stu-id="c6ba2-144">Settings, Update & Security, Windows Insider Program, select **Release Preview Channel**.</span></span>
2.  <span data-ttu-id="c6ba2-145">Instellingen, & bijwerken, Windows Update, **Controleren op updates.**</span><span class="sxs-lookup"><span data-stu-id="c6ba2-145">Settings, Update & Security, Windows Update, **Check for updates**.</span></span> <span data-ttu-id="c6ba2-146">Na de update gaat u verder met Fase 2.</span><span class="sxs-lookup"><span data-stu-id="c6ba2-146">After the update, continue on to Stage two.</span></span>
#### <a name="stage-two---dev-channel"></a><span data-ttu-id="c6ba2-147">Fase 2 - Dev-kanaal</span><span class="sxs-lookup"><span data-stu-id="c6ba2-147">Stage two - Dev Channel</span></span>
1. <span data-ttu-id="c6ba2-148">Instellingen, Update & Security en selecteer Windows Insider-programma **Dev Channel.**</span><span class="sxs-lookup"><span data-stu-id="c6ba2-148">Settings, Update & Security, Windows Insider Program, select **Dev Channel**.</span></span>
2. <span data-ttu-id="c6ba2-149">Instellingen, & bijwerken, Windows Update, **Controleren op updates.**</span><span class="sxs-lookup"><span data-stu-id="c6ba2-149">Settings, Update & Security, Windows Update, **Check for updates**.</span></span>
## <a name="ffu-download-and-flash-directions"></a><span data-ttu-id="c6ba2-150">FFU-download- en flashbeschrijvingen</span><span class="sxs-lookup"><span data-stu-id="c6ba2-150">FFU download and flash directions</span></span>
<span data-ttu-id="c6ba2-151">Als u wilt testen met een met een vlucht ondertekende ffu, moet u eerst uw apparaat ontgrendelen voordat de met de vlucht ondertekende ffu wordt geflitst.</span><span class="sxs-lookup"><span data-stu-id="c6ba2-151">To test with a flight signed ffu, you first have to flight unlock your device prior to flashing the flight signed ffu.</span></span>
1. <span data-ttu-id="c6ba2-152">Op pc:</span><span class="sxs-lookup"><span data-stu-id="c6ba2-152">On PC:</span></span>
    1. <span data-ttu-id="c6ba2-153">Download ffu naar uw pc vanaf [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .</span><span class="sxs-lookup"><span data-stu-id="c6ba2-153">Download ffu to your PC from [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload).</span></span>
    
    1. <span data-ttu-id="c6ba2-154">Installeer ARC (Advanced Recovery Companion) vanuit de Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .</span><span class="sxs-lookup"><span data-stu-id="c6ba2-154">Install ARC (Advanced Recovery Companion) from the Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span>
    
1. <span data-ttu-id="c6ba2-155">Op HoloLens - Ontgrendelen met vlucht: **Open** Instellingen  >  **Bijwerken & Beveiligingsbeleid**  >  **Windows Insider-programma** u zich vervolgens aan te melden en het apparaat opnieuw op te starten.</span><span class="sxs-lookup"><span data-stu-id="c6ba2-155">On HoloLens - Flight Unlock: Open **Settings** > **Update & Security** > **Windows Insider Program** then sign up, reboot device.</span></span>
1. <span data-ttu-id="c6ba2-156">Flash-FFU: u kunt nu de met de vlucht ondertekende FFU flashen met behulp van ARC.</span><span class="sxs-lookup"><span data-stu-id="c6ba2-156">Flash FFU - Now you can flash the flight signed FFU using ARC.</span></span>
### <a name="provide-feedback-and-report-issues"></a><span data-ttu-id="c6ba2-157">Feedback geven en problemen rapporteren</span><span class="sxs-lookup"><span data-stu-id="c6ba2-157">Provide feedback and report issues</span></span>
<span data-ttu-id="c6ba2-158">Gebruik de [app Feedback-hub uw](hololens-feedback.md) HoloLens om feedback te geven en problemen te melden.</span><span class="sxs-lookup"><span data-stu-id="c6ba2-158">Please use [the Feedback Hub app](hololens-feedback.md) on your HoloLens to provide feedback and report issues.</span></span> <span data-ttu-id="c6ba2-159">Het Feedback-hub zorgt ervoor dat alle benodigde diagnostische gegevens worden opgenomen om onze technici te helpen snel fouten op te sporen en het probleem op te lossen.</span><span class="sxs-lookup"><span data-stu-id="c6ba2-159">Using Feedback Hub ensures that all necessary diagnostics information is included to help our engineers quickly debug and resolve the problem.</span></span>  <span data-ttu-id="c6ba2-160">Problemen met de Chinese en Japanse versie van HoloLens moeten op dezelfde manier worden gerapporteerd.</span><span class="sxs-lookup"><span data-stu-id="c6ba2-160">Issues with the Chinese and Japanese version of HoloLens should be reported the same way.</span></span>
> [!NOTE]
> <span data-ttu-id="c6ba2-161">Zorg ervoor dat u de prompt accepteert waarin wordt gevraagd of u Feedback-hub documenten wilt openen (selecteer **Ja** wanneer u hier om wordt gevraagd).</span><span class="sxs-lookup"><span data-stu-id="c6ba2-161">Be sure to accept the prompt that asks whether you'd like Feedback Hub to access your Documents folder (select **Yes** when prompted).</span></span>
## <a name="note-for-developers"></a><span data-ttu-id="c6ba2-162">Opmerking voor ontwikkelaars</span><span class="sxs-lookup"><span data-stu-id="c6ba2-162">Note for developers</span></span>
<span data-ttu-id="c6ba2-163">U bent welkom en aangemoedigd om uw toepassingen te ontwikkelen met behulp van Insider-builds van HoloLens.</span><span class="sxs-lookup"><span data-stu-id="c6ba2-163">You are welcome and encouraged to try developing your applications using Insider builds of HoloLens.</span></span>  <span data-ttu-id="c6ba2-164">Bekijk de [Documentatie voor HoloLens-ontwikkelaars om](https://developer.microsoft.com/windows/mixed-reality/development) aan de slag te gaan.</span><span class="sxs-lookup"><span data-stu-id="c6ba2-164">Check out the [HoloLens Developer Documentation](https://developer.microsoft.com/windows/mixed-reality/development) to get started.</span></span> <span data-ttu-id="c6ba2-165">Dezelfde instructies werken met Insider-builds van HoloLens.</span><span class="sxs-lookup"><span data-stu-id="c6ba2-165">Those same instructions work with Insider builds of HoloLens.</span></span>  <span data-ttu-id="c6ba2-166">U kunt dezelfde builds van Unity en Visual Studio die u al gebruikt voor HoloLens-ontwikkeling.</span><span class="sxs-lookup"><span data-stu-id="c6ba2-166">You can use the same builds of Unity and Visual Studio that you're already using for HoloLens development.</span></span>
## <a name="stop-receiving-insider-builds"></a><span data-ttu-id="c6ba2-167">Ontvangst van Insider-builds stoppen</span><span class="sxs-lookup"><span data-stu-id="c6ba2-167">Stop receiving Insider builds</span></span>
<span data-ttu-id="c6ba2-168">Als u geen Insider-builds van Windows Holographic meer wilt ontvangen, kunt u zich uitloggen [](hololens-recovery.md) wanneer op uw HoloLens een productie-build wordt uitgevoerd, of u kunt uw apparaat herstellen met behulp van advanced recovery companion om uw apparaat te herstellen naar een niet-Insider-versie van Windows Holographic.</span><span class="sxs-lookup"><span data-stu-id="c6ba2-168">If you no longer want to receive Insider builds of Windows Holographic, you can opt out when your HoloLens is running a production build, or you can [recover your device](hololens-recovery.md) using the Advanced Recovery Companion to recover your device to a non-Insider version of Windows Holographic.</span></span>
> [!CAUTION]
> <span data-ttu-id="c6ba2-169">Er is een bekend probleem waarbij gebruikers die de registratie van Insider Preview-builds ongedaan maken nadat ze handmatig een nieuwe preview-build hebben geïnstalleerd, een blauw scherm krijgen.</span><span class="sxs-lookup"><span data-stu-id="c6ba2-169">There is a known issue in which users who un-enroll from Insider Preview builds after manually reinstalling a fresh preview build would experience a blue screen.</span></span> <span data-ttu-id="c6ba2-170">Daarna moeten ze hun apparaat handmatig herstellen.</span><span class="sxs-lookup"><span data-stu-id="c6ba2-170">Afterwards they must manually recover their device.</span></span> <span data-ttu-id="c6ba2-171">Bekijk meer over dit bekende probleem voor meer informatie over of u hier al dan niet [mee te maken zou krijgen.](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)</span><span class="sxs-lookup"><span data-stu-id="c6ba2-171">For full details on if you would be impacted or not, please view more on this [Known Issue](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build).</span></span>
<span data-ttu-id="c6ba2-172">Controleren of op uw HoloLens een productie-build wordt uitgevoerd:</span><span class="sxs-lookup"><span data-stu-id="c6ba2-172">To verify that your HoloLens is running a production build:</span></span>
1. <span data-ttu-id="c6ba2-173">Ga naar **Instellingen > Systeem > Over** en zoek het buildnummer.</span><span class="sxs-lookup"><span data-stu-id="c6ba2-173">Go to **Settings > System > About**, and find the build number.</span></span>
1. <span data-ttu-id="c6ba2-174">[Zie de releasenotities voor productie-buildnummers.](hololens-release-notes.md)</span><span class="sxs-lookup"><span data-stu-id="c6ba2-174">[See the release notes for production build numbers](hololens-release-notes.md).</span></span>
<span data-ttu-id="c6ba2-175">Als u zich wilt af melden voor Insider-builds:</span><span class="sxs-lookup"><span data-stu-id="c6ba2-175">To opt out of Insider builds:</span></span>
1. <span data-ttu-id="c6ba2-176">Ga op een HoloLens met een productie-build naar Instellingen **> Update & Security > Windows Insider-programma** en selecteer Stop Insider **builds.**</span><span class="sxs-lookup"><span data-stu-id="c6ba2-176">On a HoloLens running a production build, go to **Settings > Update & Security > Windows Insider Program**, and select **Stop Insider builds**.</span></span>
1. <span data-ttu-id="c6ba2-177">Volg de instructies om uw apparaat uit te kiezen.</span><span class="sxs-lookup"><span data-stu-id="c6ba2-177">Follow the instructions to opt out your device.</span></span>
