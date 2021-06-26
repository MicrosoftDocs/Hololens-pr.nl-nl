---
title: HoloLens 2 implementatie en het oplossen van problemen met beheerde apparaten oplossen
description: Problemen met HoloLens 2 in een bedrijfsomgeving oplossen
author: JoyJaz
ms.author: v-jjaswinski
ms.date: 6/22/2021
ms.topic: article
keywords: problemen oplossen
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
appliesto:
- HoloLens 2
ms.openlocfilehash: 911e5b9494eae00ace8007ee6a29b30e6aaf98dd
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/25/2021
ms.locfileid: "112961635"
---
# <a name="troubleshooting-implementation-and-managed-devices"></a><span data-ttu-id="55669-104">Problemen met implementatie en beheerde apparaten oplossen</span><span class="sxs-lookup"><span data-stu-id="55669-104">Troubleshooting implementation and managed devices</span></span> 

<span data-ttu-id="55669-105">In dit artikel wordt beschreven hoe u verschillende problemen kunt oplossen of vragen kunt beantwoorden met betrekking tot de implementatie en het beheer van HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="55669-105">This article describes how to resolve several issues or answer questions regarding implementation and management of HoloLens 2.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="55669-106">Voordat u een probleemoplossingsprocedure start, moet u ervoor zorgen dat uw apparaat, indien mogelijk, wordt geladen op **20 tot 40** procent van de accucapaciteit.</span><span class="sxs-lookup"><span data-stu-id="55669-106">Before you start any troubleshooting procedure, make sure that your device is charged to **20 to 40 percent** of battery capacity, if possible.</span></span> <span data-ttu-id="55669-107">De [accuindicatorlichten onder](hololens2-setup.md#lights-that-indicate-the-battery-level) de aan/uit-knop zijn een snelle manier om de accucapaciteit te controleren zonder u aan te melden bij het apparaat.</span><span class="sxs-lookup"><span data-stu-id="55669-107">The [battery indicator lights](hololens2-setup.md#lights-that-indicate-the-battery-level) located under the power button are a quick way to verify the battery capacity without logging into the device.</span></span>


<a id="list"></a>
- [<span data-ttu-id="55669-108">Problemen met EAP oplossen</span><span class="sxs-lookup"><span data-stu-id="55669-108">EAP Troubleshooting</span></span>](#eap-troubleshooting)
- [<span data-ttu-id="55669-109">Problemen met Wi-Fi oplossen</span><span class="sxs-lookup"><span data-stu-id="55669-109">Wi-Fi Troubleshooting</span></span>](#wi-fi-troubleshooting)
- [<span data-ttu-id="55669-110">Problemen met het netwerk oplossen</span><span class="sxs-lookup"><span data-stu-id="55669-110">Network Troubleshooting</span></span>](#network-troubleshooting)
- [<span data-ttu-id="55669-111">Kan niet aanmelden bij een eerder ingesteld HoloLens-apparaat</span><span class="sxs-lookup"><span data-stu-id="55669-111">Can't sign in to a previously setup HoloLens device</span></span>](#cant-sign-in-to-a-previously-setup-hololens-device)
- [<span data-ttu-id="55669-112">Kan niet aanmelden na het bijwerken naar Windows Holographic 21H1</span><span class="sxs-lookup"><span data-stu-id="55669-112">Can't login after updating to Windows Holographic 21H1</span></span>](#cant-login-after-updating-to-windows-holographic-21h1)
- [<span data-ttu-id="55669-113">Problemen met Autopilot oplossen</span><span class="sxs-lookup"><span data-stu-id="55669-113">Autopilot Troubleshooting</span></span>](#autopilot-troubleshooting)
- [<span data-ttu-id="55669-114">Veelgestelde vragen over beheerde HoloLens-apparaten</span><span class="sxs-lookup"><span data-stu-id="55669-114">Managed HoloLens Devices FAQs</span></span>](#managed-hololens-devices-faqs)

## <a name="eap-troubleshooting"></a><span data-ttu-id="55669-115">Problemen met EAP oplossen</span><span class="sxs-lookup"><span data-stu-id="55669-115">EAP Troubleshooting</span></span>
1. <span data-ttu-id="55669-116">Controleer of Wi-Fi profiel de juiste instellingen heeft:</span><span class="sxs-lookup"><span data-stu-id="55669-116">Double check Wi-Fi profile has right settings:</span></span>
    - <span data-ttu-id="55669-117">EAP-type is correct geconfigureerd, algemene EAP-typen: EAP-TLS (13), EAP-TTLS (21) en PEAP (25).</span><span class="sxs-lookup"><span data-stu-id="55669-117">EAP type is configured correctly, common EAP types: EAP-TLS (13), EAP-TTLS (21) and PEAP (25).</span></span>
    - <span data-ttu-id="55669-118">Wi-Fi SSID-naam juist is en overeenkomt met HEX-tekenreeks.</span><span class="sxs-lookup"><span data-stu-id="55669-118">Wi-Fi SSID name is right and matches with HEX string.</span></span>
    - <span data-ttu-id="55669-119">Voor EAP-TLS bevat TrustedRootCA de SHA-1-hash van het vertrouwde basis-CA-certificaat van de server.</span><span class="sxs-lookup"><span data-stu-id="55669-119">For EAP-TLS, TrustedRootCA contains the SHA-1 hash of server's trusted root CA certificate.</span></span> <span data-ttu-id="55669-120">Op Windows-pc 'certutil.exe -dump cert_file_name'-opdracht wordt de SHA-1-hash-tekenreeks van een certificaat weer gegeven.</span><span class="sxs-lookup"><span data-stu-id="55669-120">On Windows PC "certutil.exe -dump cert_file_name" command will show a certificate's SHA-1 hash string.</span></span>
2. <span data-ttu-id="55669-121">Verzamel netwerkpakketopname op de logboeken van het toegangspunt, de controller of de AAA-server om erachter te komen waar de EAP-sessie mislukt.</span><span class="sxs-lookup"><span data-stu-id="55669-121">Collect network packet capture on the Access Point or Controller or AAA server logs to find out where the EAP session fails.</span></span>
    - <span data-ttu-id="55669-122">Als de EAP-identiteit die wordt geleverd door HoloLens niet wordt verwacht, controleert u of de identiteit correct is ingericht via Wi-Fi-profiel of clientcertificaat.</span><span class="sxs-lookup"><span data-stu-id="55669-122">If the EAP identity provided by HoloLens is not expected, check whether the identity has been correctly provisioned through Wi-Fi profile or client certificate.</span></span>
    - <span data-ttu-id="55669-123">Als de server het HoloLens-clientcertificaat weigert, controleert u of het vereiste clientcertificaat is ingericht op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="55669-123">If server rejects HoloLens client certificate, check whether the required client certificate has been provisioned on the device.</span></span>
    - <span data-ttu-id="55669-124">Als HoloLens het servercertificaat weigert, controleert u of het basis-CA-certificaat voor de server is ingericht op HoloLens.</span><span class="sxs-lookup"><span data-stu-id="55669-124">If HoloLens rejects server certificate, check if the server root CA certificate has been provisioned on HoloLens.</span></span>
3. <span data-ttu-id="55669-125">Als het ondernemingsprofiel is ingericht via Wi-Fi inrichtingspakket, kunt u overwegen het inrichtingspakket toe te passen op een Windows 10 pc.</span><span class="sxs-lookup"><span data-stu-id="55669-125">If the enterprise profile is provisioned through Wi-Fi provisioning package, consider applying the provisioning package on a Windows 10 PC.</span></span> <span data-ttu-id="55669-126">Als dit ook mislukt op Windows 10 pc, volgt u de probleemoplossingsgids voor Windows-client 802.1X-verificatie.</span><span class="sxs-lookup"><span data-stu-id="55669-126">If it also fails on Windows 10 PC, follow the Windows client 802.1X authentication troubleshooting guide.</span></span>
4. <span data-ttu-id="55669-127">Stuur ons feedback via Feedback-hub.</span><span class="sxs-lookup"><span data-stu-id="55669-127">Send us feedback through Feedback Hub.</span></span>

[<span data-ttu-id="55669-128">Terug naar lijst</span><span class="sxs-lookup"><span data-stu-id="55669-128">Back to list</span></span>](#list)

## <a name="wi-fi-troubleshooting"></a><span data-ttu-id="55669-129">Wi-Fi oplossen</span><span class="sxs-lookup"><span data-stu-id="55669-129">Wi-Fi Troubleshooting</span></span>

<span data-ttu-id="55669-130">Hier zijn enkele dingen die u kunt proberen als u uw HoloLens niet kunt verbinden met Wi-Fi netwerk:</span><span class="sxs-lookup"><span data-stu-id="55669-130">Here are some things to try if you can't connect your HoloLens to a Wi-Fi network:</span></span>

1. <span data-ttu-id="55669-131">Zorg ervoor dat Wi-Fi is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="55669-131">Make sure that Wi-Fi is turned on.</span></span> <span data-ttu-id="55669-132">Als u dit wilt controleren, gebruikt u de beweging Starten en selecteert u vervolgens Instellingen > Netwerk & Internet > Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="55669-132">To check, use the Start gesture, then select Settings > Network & Internet > Wi-Fi.</span></span> <span data-ttu-id="55669-133">Als Wi-Fi is aan, probeert u deze uit te schakelen en vervolgens weer aan.</span><span class="sxs-lookup"><span data-stu-id="55669-133">If Wi-Fi is on, try turning it off and then on again.</span></span>
2. <span data-ttu-id="55669-134">Ga dichter bij de router of het toegangspunt zitten.</span><span class="sxs-lookup"><span data-stu-id="55669-134">Move closer to the router or access point.</span></span>
3. <span data-ttu-id="55669-135">Start uw Wi-Fi en start HoloLens opnieuw.</span><span class="sxs-lookup"><span data-stu-id="55669-135">Restart your Wi-Fi router, then restart HoloLens.</span></span> <span data-ttu-id="55669-136">Probeer opnieuw verbinding te maken.</span><span class="sxs-lookup"><span data-stu-id="55669-136">Try connecting again.</span></span>
4. <span data-ttu-id="55669-137">Als geen van deze dingen werkt, controleert u of uw router de meest recente firmware gebruikt.</span><span class="sxs-lookup"><span data-stu-id="55669-137">If none of these things work, check to make sure that your router is using the latest firmware.</span></span> <span data-ttu-id="55669-138">U vindt deze informatie op de website van de fabrikant.</span><span class="sxs-lookup"><span data-stu-id="55669-138">You can find this information on the manufacturer website.</span></span>

<span data-ttu-id="55669-139">Wanneer u zich op het apparaat bij een bedrijfs- of organisatieaccount aankeert, kan het ook MDM-beleid (Mobile Device Management) toepassen als het beleid is geconfigureerd door uw IT-beheerder.</span><span class="sxs-lookup"><span data-stu-id="55669-139">When you sign into an enterprise or organizational account on the device, it may also apply Mobile Device Management (MDM) policy, if the policy is configured by your IT administrator.</span></span>

## <a name="network-troubleshooting"></a><span data-ttu-id="55669-140">Problemen met het netwerk oplossen</span><span class="sxs-lookup"><span data-stu-id="55669-140">Network Troubleshooting</span></span>
<span data-ttu-id="55669-141">Als netwerkproblemen een obstakel vormen voor het succesvol implementeren en gebruiken van HoloLens 2 in uw organisatie, leert u hoe u met twee bekende hulpprogramma's voor netwerkdiagnose, Fiddler en Wireshark, problemen kunt scannen, diagnosticeren en identificeren.</span><span class="sxs-lookup"><span data-stu-id="55669-141">If network issues are an obstacle to successfully deploying and using HoloLens 2 in your organization, learn how two well-known network diagnostic tools, Fiddler and Wireshark can help you scan, diagnose, and identify problems.</span></span> <span data-ttu-id="55669-142">Bekijk dit [blog voor](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/diagnose-hololens-2-network-issues-with-fiddler-and-wireshark/ba-p/2322458) meer informatie.</span><span class="sxs-lookup"><span data-stu-id="55669-142">Check out this [blog](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/diagnose-hololens-2-network-issues-with-fiddler-and-wireshark/ba-p/2322458) for more details.</span></span>

[<span data-ttu-id="55669-143">Terug naar lijst</span><span class="sxs-lookup"><span data-stu-id="55669-143">Back to list</span></span>](#list)

## <a name="cant-sign-in-to-a-previously-setup-hololens-device"></a><span data-ttu-id="55669-144">Kan niet aanmelden bij een eerder ingesteld HoloLens-apparaat</span><span class="sxs-lookup"><span data-stu-id="55669-144">Can't sign in to a previously setup HoloLens device</span></span>

<span data-ttu-id="55669-145">Als uw apparaat eerder is ingesteld voor iemand anders, voor een client of voor een voormalige werknemer, en u geen wachtwoord [](https://docs.microsoft.com/intune/remote-actions/devices-wipe) hebt om het apparaat te ontgrendelen, kunt u Intune gebruiken om het apparaat op afstand te wissen.</span><span class="sxs-lookup"><span data-stu-id="55669-145">If your device was previously set up for someone else, either for a client or for a former employee, and you don't have their password to unlock the device, you can use Intune to remotely [wipe](https://docs.microsoft.com/intune/remote-actions/devices-wipe) the device.</span></span> <span data-ttu-id="55669-146">Het apparaat wordt vervolgens opnieuw geflitst.</span><span class="sxs-lookup"><span data-stu-id="55669-146">The device then re-flashes itself.</span></span>  
> [!IMPORTANT]
> <span data-ttu-id="55669-147">Wanneer u het apparaat wist, zorg er dan voor dat Inschrijvingstoestand en gebruikersaccount **behouden** uitgeschakeld blijven.</span><span class="sxs-lookup"><span data-stu-id="55669-147">When you wipe the device, make sure to leave **Retain enrollment state and user account** unchecked.</span></span>
[<span data-ttu-id="55669-148">Terug naar lijst</span><span class="sxs-lookup"><span data-stu-id="55669-148">Back to list</span></span>](#list)

## <a name="cant-login-after-updating-to-windows-holographic-21h1"></a><span data-ttu-id="55669-149">Kan niet aanmelden na het bijwerken naar Windows Holographic 21H1</span><span class="sxs-lookup"><span data-stu-id="55669-149">Can't login after updating to Windows Holographic 21H1</span></span>

### <a name="symptoms"></a><span data-ttu-id="55669-150">Symptomen</span><span class="sxs-lookup"><span data-stu-id="55669-150">Symptoms</span></span>
- <span data-ttu-id="55669-151">Het gebruik van een pincode voor aanmelding mislukt nadat u de juiste pincode hebt invoeren.</span><span class="sxs-lookup"><span data-stu-id="55669-151">Using PIN to logon will fail after entering the correct PIN.</span></span>
- <span data-ttu-id="55669-152">Het gebruik van de web-aanmeldingsmethode mislukt nadat u zich hebt aanmelden op de webpagina.</span><span class="sxs-lookup"><span data-stu-id="55669-152">Using the web logon method will fail after successfully signing in on the web page.</span></span>
- <span data-ttu-id="55669-153">Het apparaat wordt niet vermeld als 'Azure AD-toegevoegd' in [Azure Portal](https://portal.azure.com/) -> Azure Active Directory -> Devices.</span><span class="sxs-lookup"><span data-stu-id="55669-153">The device is not listed as “Azure AD joined” in [Azure portal](https://portal.azure.com/) -> Azure Active Directory -> Devices.</span></span>

### <a name="cause"></a><span data-ttu-id="55669-154">Oorzaak</span><span class="sxs-lookup"><span data-stu-id="55669-154">Cause</span></span>
<span data-ttu-id="55669-155">Het beïnvloede apparaat is mogelijk verwijderd uit de Azure AD-tenant.</span><span class="sxs-lookup"><span data-stu-id="55669-155">The impacted device may have been deleted from the Azure AD tenant.</span></span> <span data-ttu-id="55669-156">Dit kan bijvoorbeeld gebeuren omdat:</span><span class="sxs-lookup"><span data-stu-id="55669-156">For example, this may happen because:</span></span>

- <span data-ttu-id="55669-157">Een beheerder of gebruiker heeft het apparaat verwijderd in de Azure Portal of met behulp van PowerShell.</span><span class="sxs-lookup"><span data-stu-id="55669-157">An administrator or user deleted the device in the Azure portal or using PowerShell.</span></span>
- <span data-ttu-id="55669-158">Het apparaat is verwijderd uit de Azure AD-tenant vanwege inactiviteit.</span><span class="sxs-lookup"><span data-stu-id="55669-158">The device was removed from the Azure AD tenant due to inactivity.</span></span> <span data-ttu-id="55669-159">Voor een efficiënt beheerde omgeving raden we IT-beheerders doorgaans aan verouderde, inactieve apparaten uit hun [Azure AD-tenant te verwijderen.](https://docs.microsoft.com/azure/active-directory/devices/manage-stale-devices)</span><span class="sxs-lookup"><span data-stu-id="55669-159">For an efficiently managed environment, we typically recommend IT admins to [remove stale, inactive devices from their Azure AD tenant](https://docs.microsoft.com/azure/active-directory/devices/manage-stale-devices).</span></span>

<span data-ttu-id="55669-160">Wanneer een beïnvloed apparaat opnieuw contact probeert op te nemen met de Azure AD-tenant nadat het is verwijderd, mislukt de verificatie bij Azure AD.</span><span class="sxs-lookup"><span data-stu-id="55669-160">When an impacted device attempts to contact the Azure AD tenant again after it has been deleted it will fail to authenticate with Azure AD.</span></span> <span data-ttu-id="55669-161">Dit effect is vaak onzichtbaar voor de gebruiker van het apparaat, omdat aanmelding in de cache via een pincode de gebruiker blijft toestaan zich aan te geven.</span><span class="sxs-lookup"><span data-stu-id="55669-161">This effect is often invisible to the user of the device, as cached logon via PIN will continue to allow the user to logon.</span></span>

### <a name="mitigation"></a><span data-ttu-id="55669-162">Oplossing</span><span class="sxs-lookup"><span data-stu-id="55669-162">Mitigation</span></span>
<span data-ttu-id="55669-163">Er is momenteel geen manier om een verwijderd HoloLens-apparaat weer toe te voegen aan Azure AD.</span><span class="sxs-lookup"><span data-stu-id="55669-163">There is currently no way to add a deleted HoloLens device back into Azure AD.</span></span> <span data-ttu-id="55669-164">Betrokken apparaten moeten clean reflashed worden door de instructies te volgen voor [het reflashen van hun apparaat.](hololens-recovery.md#clean-reflash-the-device)</span><span class="sxs-lookup"><span data-stu-id="55669-164">Affected devices will need to be clean-reflashed by following the instructions on [reflashing their device](hololens-recovery.md#clean-reflash-the-device).</span></span>

## <a name="autopilot-troubleshooting"></a><span data-ttu-id="55669-165">Problemen met Autopilot oplossen</span><span class="sxs-lookup"><span data-stu-id="55669-165">Autopilot Troubleshooting</span></span>

<span data-ttu-id="55669-166">De volgende artikelen kunnen een nuttige informatiebron zijn voor meer informatie en het oplossen van Autopilot-problemen. Houd er echter rekening mee dat deze artikelen zijn gebaseerd op Windows 10 Desktop en dat niet alle informatie van toepassing is op HoloLens:</span><span class="sxs-lookup"><span data-stu-id="55669-166">The following articles may be a useful resource for you to learn more information and troubleshoot Autopilot Issues, however please be aware that these articles are based on Windows 10 Desktop and not all information may apply to HoloLens:</span></span>

- [<span data-ttu-id="55669-167">Windows Autopilot- bekende problemen</span><span class="sxs-lookup"><span data-stu-id="55669-167">Windows Autopilot - known issues</span></span>](https://docs.microsoft.com/mem/autopilot/known-issues)
- [<span data-ttu-id="55669-168">Problemen met inschrijving van Windows-apparaten in Microsoft Intune oplossen</span><span class="sxs-lookup"><span data-stu-id="55669-168">Troubleshoot Windows device enrollment problems in Microsoft Intune</span></span>](https://docs.microsoft.com/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [<span data-ttu-id="55669-169">Windows Autopilot - Beleidsconflicten</span><span class="sxs-lookup"><span data-stu-id="55669-169">Windows Autopilot - Policy Conflicts</span></span>](https://docs.microsoft.com/mem/autopilot/policy-conflicts)

## <a name="managed-hololens-devices-faqs"></a><span data-ttu-id="55669-170">Veelgestelde vragen over beheerde HoloLens-apparaten</span><span class="sxs-lookup"><span data-stu-id="55669-170">Managed HoloLens Devices FAQs</span></span>

### <a name="can-i-use-system-center-configuration-manager-sccm-to-manage-hololens-devices"></a><span data-ttu-id="55669-171">Kan ik System Center Configuration Manager (SCCM) gebruiken om HoloLens-apparaten te beheren?</span><span class="sxs-lookup"><span data-stu-id="55669-171">Can I use System Center Configuration Manager (SCCM) to manage HoloLens devices?</span></span>

<span data-ttu-id="55669-172">Nee.</span><span class="sxs-lookup"><span data-stu-id="55669-172">No.</span></span> <span data-ttu-id="55669-173">U moet een MDM-systeem gebruiken om HoloLens-apparaten te beheren.</span><span class="sxs-lookup"><span data-stu-id="55669-173">You have to use an MDM system to manage HoloLens devices.</span></span>

### <a name="can-i-use-active-directory-domain-services-ad-ds-to-manage-hololens-user-accounts"></a><span data-ttu-id="55669-174">Kan ik Active Directory Domain Services (AD DS) gebruiken om HoloLens-gebruikersaccounts te beheren?</span><span class="sxs-lookup"><span data-stu-id="55669-174">Can I use Active Directory Domain Services (AD DS) to manage HoloLens user accounts?</span></span>

<span data-ttu-id="55669-175">Nee.</span><span class="sxs-lookup"><span data-stu-id="55669-175">No.</span></span> <span data-ttu-id="55669-176">U moet een Azure Active Directory (Azure AD) gebruiken om gebruikersaccounts voor HoloLens-apparaten te beheren.</span><span class="sxs-lookup"><span data-stu-id="55669-176">You have to use Azure Active Directory (Azure AD) to manage user accounts for HoloLens devices.</span></span>

### <a name="is-hololens-capable-of-automated-data-capture-systems-adcs-auto-enrollment"></a><span data-ttu-id="55669-177">Is HoloLens geschikt voor automatische ADCS-inschrijving (Automated Data Capture Systems)?</span><span class="sxs-lookup"><span data-stu-id="55669-177">Is HoloLens capable of Automated Data Capture Systems (ADCS) auto-enrollment?</span></span>

<span data-ttu-id="55669-178">Nee.</span><span class="sxs-lookup"><span data-stu-id="55669-178">No.</span></span>

### <a name="can-hololens-participate-in-integrated-windows-authentication"></a><span data-ttu-id="55669-179">Kan HoloLens deelnemen aan Geïntegreerde Windows-verificatie?</span><span class="sxs-lookup"><span data-stu-id="55669-179">Can HoloLens participate in Integrated Windows Authentication?</span></span>

<span data-ttu-id="55669-180">Nee.</span><span class="sxs-lookup"><span data-stu-id="55669-180">No.</span></span>

### <a name="does-hololens-support-branding"></a><span data-ttu-id="55669-181">Ondersteunt HoloLens de huisstijl?</span><span class="sxs-lookup"><span data-stu-id="55669-181">Does HoloLens support branding?</span></span>

<span data-ttu-id="55669-182">Nee.</span><span class="sxs-lookup"><span data-stu-id="55669-182">No.</span></span> <span data-ttu-id="55669-183">U kunt dit probleem echter op een van de volgende manieren oplossen:</span><span class="sxs-lookup"><span data-stu-id="55669-183">However, you can work around this issue by using one of the following approaches:</span></span>

- <span data-ttu-id="55669-184">Maak een aangepaste app en schakel vervolgens [kioskmodus in.](hololens-kiosk.md)</span><span class="sxs-lookup"><span data-stu-id="55669-184">Create a custom app, and then [enable Kiosk mode](hololens-kiosk.md).</span></span> <span data-ttu-id="55669-185">De aangepaste app kan een huisstijl hebben en kan andere apps starten (zoals Remote Assist).</span><span class="sxs-lookup"><span data-stu-id="55669-185">The custom app can have branding, and can launch other apps (such as Remote Assist).</span></span>  
- <span data-ttu-id="55669-186">Wijzig alle gebruikersprofielfoto's in Azure AD in uw bedrijfslogo.</span><span class="sxs-lookup"><span data-stu-id="55669-186">Change all of the user profile pictures in Azure AD to your company logo.</span></span> <span data-ttu-id="55669-187">Dit is echter mogelijk niet wenselijk voor alle scenario's.</span><span class="sxs-lookup"><span data-stu-id="55669-187">However, this may not be desirable for all scenarios.</span></span>

### <a name="what-logging-capabilities-does-hololens-2-offer"></a><span data-ttu-id="55669-188">Welke logboekregistratiemogelijkheden biedt HoloLens 2 bieden?</span><span class="sxs-lookup"><span data-stu-id="55669-188">What logging capabilities does HoloLens 2 offer?</span></span>

<span data-ttu-id="55669-189">Logboekregistratie is beperkt tot traceringen die kunnen worden vastgelegd in ontwikkel- of probleemoplossingsscenario's, of telemetrie die de apparaten naar Microsoft-servers verzenden.</span><span class="sxs-lookup"><span data-stu-id="55669-189">Logging is limited to traces that can be captured in development or troubleshooting scenarios, or telemetry that the devices send to Microsoft servers.</span></span>

## <a name="questions-about-securing-hololens-devices"></a><span data-ttu-id="55669-190">Vragen over het beveiligen van HoloLens-apparaten</span><span class="sxs-lookup"><span data-stu-id="55669-190">Questions about securing HoloLens devices</span></span>

<span data-ttu-id="55669-191">Zie [onze HoloLens 2 beveiligingsgegevens](security-overview.md).</span><span class="sxs-lookup"><span data-stu-id="55669-191">See [our HoloLens 2 security information](security-overview.md).</span></span>
<span data-ttu-id="55669-192">Raadpleeg deze veelgestelde vragen voor HoloLens 1st [Gen-apparaten.](hololens1-faq-security.md)</span><span class="sxs-lookup"><span data-stu-id="55669-192">For HoloLens 1st Gen devices please review [this FAQ](hololens1-faq-security.md).</span></span>

[<span data-ttu-id="55669-193">Terug naar lijst</span><span class="sxs-lookup"><span data-stu-id="55669-193">Back to list</span></span>](#list)
