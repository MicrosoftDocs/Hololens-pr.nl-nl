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
ms.openlocfilehash: 9f3950de51e4bfa2a76431a2a070d87aa81ed443
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/12/2021
ms.locfileid: "113636874"
---
# <a name="troubleshooting-implementation-and-managed-devices"></a><span data-ttu-id="2b009-104">Problemen met implementatie en beheerde apparaten oplossen</span><span class="sxs-lookup"><span data-stu-id="2b009-104">Troubleshooting implementation and managed devices</span></span> 

<span data-ttu-id="2b009-105">In dit artikel wordt beschreven hoe u verschillende problemen kunt oplossen of vragen kunt beantwoorden met betrekking tot de implementatie en het beheer van HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="2b009-105">This article describes how to resolve several issues or answer questions regarding implementation and management of HoloLens 2.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="2b009-106">Voordat u een probleemoplossingsprocedure start, moet u ervoor zorgen dat uw apparaat, indien mogelijk, wordt geladen op **20 tot 40** procent van de accucapaciteit.</span><span class="sxs-lookup"><span data-stu-id="2b009-106">Before you start any troubleshooting procedure, make sure that your device is charged to **20 to 40 percent** of battery capacity, if possible.</span></span> <span data-ttu-id="2b009-107">De [accuindicatorlichten onder](hololens2-setup.md#lights-that-indicate-the-battery-level) de aan/uit-knop zijn een snelle manier om de accucapaciteit te controleren zonder u aan te melden bij het apparaat.</span><span class="sxs-lookup"><span data-stu-id="2b009-107">The [battery indicator lights](hololens2-setup.md#lights-that-indicate-the-battery-level) located under the power button are a quick way to verify the battery capacity without logging into the device.</span></span>


<a id="list"></a>
- [<span data-ttu-id="2b009-108">Problemen met EAP oplossen</span><span class="sxs-lookup"><span data-stu-id="2b009-108">EAP Troubleshooting</span></span>](#eap-troubleshooting)
- [<span data-ttu-id="2b009-109">Problemen met Wi-Fi oplossen</span><span class="sxs-lookup"><span data-stu-id="2b009-109">Wi-Fi Troubleshooting</span></span>](#wi-fi-troubleshooting)
- [<span data-ttu-id="2b009-110">Problemen met het netwerk oplossen</span><span class="sxs-lookup"><span data-stu-id="2b009-110">Network Troubleshooting</span></span>](#network-troubleshooting)
- [<span data-ttu-id="2b009-111">Kan niet aanmelden bij een eerder ingesteld HoloLens apparaat</span><span class="sxs-lookup"><span data-stu-id="2b009-111">Can't sign in to a previously setup HoloLens device</span></span>](#cant-sign-in-to-a-previously-setup-hololens-device)
- [<span data-ttu-id="2b009-112">Kan niet aanmelden na het bijwerken naar Windows Holographic 21H1</span><span class="sxs-lookup"><span data-stu-id="2b009-112">Can't login after updating to Windows Holographic 21H1</span></span>](#cant-login-after-updating-to-windows-holographic-21h1)
- [<span data-ttu-id="2b009-113">Problemen met Autopilot oplossen</span><span class="sxs-lookup"><span data-stu-id="2b009-113">Autopilot Troubleshooting</span></span>](#autopilot-troubleshooting)
- [<span data-ttu-id="2b009-114">Veelgestelde HoloLens beheerde apparaten</span><span class="sxs-lookup"><span data-stu-id="2b009-114">Managed HoloLens Devices FAQs</span></span>](#managed-hololens-devices-faqs)

## <a name="eap-troubleshooting"></a><span data-ttu-id="2b009-115">Problemen met EAP oplossen</span><span class="sxs-lookup"><span data-stu-id="2b009-115">EAP Troubleshooting</span></span>
1. <span data-ttu-id="2b009-116">Controleer of Wi-Fi profiel de juiste instellingen heeft:</span><span class="sxs-lookup"><span data-stu-id="2b009-116">Double check Wi-Fi profile has right settings:</span></span>
    - <span data-ttu-id="2b009-117">EAP-type is correct geconfigureerd, algemene EAP-typen: EAP-TLS (13), EAP-TTLS (21) en PEAP (25).</span><span class="sxs-lookup"><span data-stu-id="2b009-117">EAP type is configured correctly, common EAP types: EAP-TLS (13), EAP-TTLS (21) and PEAP (25).</span></span>
    - <span data-ttu-id="2b009-118">Wi-Fi SSID-naam juist is en overeenkomt met HEX-tekenreeks.</span><span class="sxs-lookup"><span data-stu-id="2b009-118">Wi-Fi SSID name is right and matches with HEX string.</span></span>
    - <span data-ttu-id="2b009-119">Voor EAP-TLS bevat TrustedRootCA de SHA-1-hash van het vertrouwde basis-CA-certificaat van de server.</span><span class="sxs-lookup"><span data-stu-id="2b009-119">For EAP-TLS, TrustedRootCA contains the SHA-1 hash of server's trusted root CA certificate.</span></span> <span data-ttu-id="2b009-120">Op Windows pc 'certutil.exe -dump cert_file_name'-opdracht wordt de SHA-1-hash-tekenreeks van een certificaat weer gegeven.</span><span class="sxs-lookup"><span data-stu-id="2b009-120">On Windows PC "certutil.exe -dump cert_file_name" command will show a certificate's SHA-1 hash string.</span></span>
2. <span data-ttu-id="2b009-121">Verzamel netwerkpakketopname op de logboeken van het toegangspunt, de controller of de AAA-server om erachter te komen waar de EAP-sessie mislukt.</span><span class="sxs-lookup"><span data-stu-id="2b009-121">Collect network packet capture on the Access Point or Controller or AAA server logs to find out where the EAP session fails.</span></span>
    - <span data-ttu-id="2b009-122">Als de EAP-identiteit die wordt geleverd door HoloLens niet wordt verwacht, controleert u of de identiteit correct is ingericht via Wi-Fi profiel of clientcertificaat.</span><span class="sxs-lookup"><span data-stu-id="2b009-122">If the EAP identity provided by HoloLens is not expected, check whether the identity has been correctly provisioned through Wi-Fi profile or client certificate.</span></span>
    - <span data-ttu-id="2b009-123">Als de server het HoloLens clientcertificaat weigert, controleert u of het vereiste clientcertificaat is ingericht op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="2b009-123">If server rejects HoloLens client certificate, check whether the required client certificate has been provisioned on the device.</span></span>
    - <span data-ttu-id="2b009-124">Als HoloLens servercertificaat weigert, controleert u of het basis-CA-certificaat van de server is ingericht op HoloLens.</span><span class="sxs-lookup"><span data-stu-id="2b009-124">If HoloLens rejects server certificate, check if the server root CA certificate has been provisioned on HoloLens.</span></span>
3. <span data-ttu-id="2b009-125">Als het ondernemingsprofiel is ingericht via Wi-Fi inrichtingspakket, kunt u overwegen het inrichtingspakket toe te passen op een Windows 10 pc.</span><span class="sxs-lookup"><span data-stu-id="2b009-125">If the enterprise profile is provisioned through Wi-Fi provisioning package, consider applying the provisioning package on a Windows 10 PC.</span></span> <span data-ttu-id="2b009-126">Als dit ook mislukt op Windows 10 pc, volgt u de probleemoplossingsgids Windows client 802.1X-verificatie.</span><span class="sxs-lookup"><span data-stu-id="2b009-126">If it also fails on Windows 10 PC, follow the Windows client 802.1X authentication troubleshooting guide.</span></span>
4. <span data-ttu-id="2b009-127">Stuur ons feedback via Feedback-hub.</span><span class="sxs-lookup"><span data-stu-id="2b009-127">Send us feedback through Feedback Hub.</span></span>

[<span data-ttu-id="2b009-128">Terug naar lijst</span><span class="sxs-lookup"><span data-stu-id="2b009-128">Back to list</span></span>](#list)

## <a name="wi-fi-troubleshooting"></a><span data-ttu-id="2b009-129">Wi-Fi oplossen</span><span class="sxs-lookup"><span data-stu-id="2b009-129">Wi-Fi Troubleshooting</span></span>

<span data-ttu-id="2b009-130">Hier zijn enkele dingen die u kunt proberen als u uw HoloLens niet kunt verbinden met Wi-Fi netwerk:</span><span class="sxs-lookup"><span data-stu-id="2b009-130">Here are some things to try if you can't connect your HoloLens to a Wi-Fi network:</span></span>

1. <span data-ttu-id="2b009-131">Zorg ervoor dat Wi-Fi is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="2b009-131">Make sure that Wi-Fi is turned on.</span></span> <span data-ttu-id="2b009-132">Als u dit wilt controleren, gebruikt u de beweging Start en selecteert u Instellingen > Network & Internet > Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="2b009-132">To check, use the Start gesture, then select Settings > Network & Internet > Wi-Fi.</span></span> <span data-ttu-id="2b009-133">Als Wi-Fi is aan, probeert u deze uit te schakelen en vervolgens weer aan.</span><span class="sxs-lookup"><span data-stu-id="2b009-133">If Wi-Fi is on, try turning it off and then on again.</span></span>
2. <span data-ttu-id="2b009-134">Ga dichter bij de router of het toegangspunt zitten.</span><span class="sxs-lookup"><span data-stu-id="2b009-134">Move closer to the router or access point.</span></span>
3. <span data-ttu-id="2b009-135">Start uw Wi-Fi router opnieuw op en start HoloLens.</span><span class="sxs-lookup"><span data-stu-id="2b009-135">Restart your Wi-Fi router, then restart HoloLens.</span></span> <span data-ttu-id="2b009-136">Probeer opnieuw verbinding te maken.</span><span class="sxs-lookup"><span data-stu-id="2b009-136">Try connecting again.</span></span>
4. <span data-ttu-id="2b009-137">Als geen van deze dingen werkt, controleert u of uw router de meest recente firmware gebruikt.</span><span class="sxs-lookup"><span data-stu-id="2b009-137">If none of these things work, check to make sure that your router is using the latest firmware.</span></span> <span data-ttu-id="2b009-138">U vindt deze informatie op de website van de fabrikant.</span><span class="sxs-lookup"><span data-stu-id="2b009-138">You can find this information on the manufacturer website.</span></span>

<span data-ttu-id="2b009-139">Wanneer u zich op het apparaat bij een bedrijfs- of organisatieaccount aankeert, kan het ook MDM-beleid (Mobile Device Management) toepassen als het beleid is geconfigureerd door uw IT-beheerder.</span><span class="sxs-lookup"><span data-stu-id="2b009-139">When you sign into an enterprise or organizational account on the device, it may also apply Mobile Device Management (MDM) policy, if the policy is configured by your IT administrator.</span></span>

[<span data-ttu-id="2b009-140">Terug naar lijst</span><span class="sxs-lookup"><span data-stu-id="2b009-140">Back to list</span></span>](#list)

## <a name="network-troubleshooting"></a><span data-ttu-id="2b009-141">Problemen met het netwerk oplossen</span><span class="sxs-lookup"><span data-stu-id="2b009-141">Network Troubleshooting</span></span>
<span data-ttu-id="2b009-142">Als netwerkproblemen een obstakel vormen voor het succesvol implementeren en gebruiken van HoloLens 2 in uw organisatie, configureert u Fiddler en/of Wireshark om HTTP/HTTPS-verkeer vast te leggen en te analyseren.</span><span class="sxs-lookup"><span data-stu-id="2b009-142">If network issues are an obstacle to successfully deploying and using HoloLens 2 in your organization, configure Fiddler and/or Wireshark to capture and analyze HTTP/HTTPS traffic.</span></span> 

### <a name="configure-fiddler-to-capture-http-traffic"></a><span data-ttu-id="2b009-143">Fiddler configureren om HTTP-verkeer vast te leggen</span><span class="sxs-lookup"><span data-stu-id="2b009-143">Configure Fiddler to capture HTTP traffic</span></span>
<span data-ttu-id="2b009-144">Fiddler is een webdebuggingsproxy en wordt gebruikt om HTTP(S)-problemen op te lossen.</span><span class="sxs-lookup"><span data-stu-id="2b009-144">Fiddler is a web debugging proxy and is used to troubleshoot HTTP(S) issues.</span></span> <span data-ttu-id="2b009-145">Het legt elke HTTP-aanvraag vast die de computer maakt en registreert alles wat ermee is gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="2b009-145">It captures every HTTP request the computer makes and records everything associated with it.</span></span> <span data-ttu-id="2b009-146">Het blootleggen van verificatieproblemen voor uw HTTPS-apps zorgt voor een betere productiviteit en efficiëntie voor HoloLens 2 gebruiksgevallen.</span><span class="sxs-lookup"><span data-stu-id="2b009-146">Uncovering end-user authentication issues for your HTTPS apps drives better productivity and efficiency for your target HoloLens 2 use cases.</span></span> 

#### <a name="prerequisites"></a><span data-ttu-id="2b009-147">Vereisten</span><span class="sxs-lookup"><span data-stu-id="2b009-147">Prerequisites</span></span>
 
- <span data-ttu-id="2b009-148">HoloLens 2 apparaten en uw pc moeten zich in hetzelfde netwerk</span><span class="sxs-lookup"><span data-stu-id="2b009-148">HoloLens 2 devices and your PC must be on the same network</span></span>
- <span data-ttu-id="2b009-149">Noteer het IP-adres van uw pc</span><span class="sxs-lookup"><span data-stu-id="2b009-149">Note the IP address of your PC</span></span>

#### <a name="install-and-configure-fiddler"></a><span data-ttu-id="2b009-150">Fiddler installeren en configureren</span><span class="sxs-lookup"><span data-stu-id="2b009-150">Install and Configure Fiddler</span></span>

1. <span data-ttu-id="2b009-151">Op uw pc: [installeer en](https://docs.telerik.com/fiddler-everywhere/get-started/installation-procedure) start Fiddler.</span><span class="sxs-lookup"><span data-stu-id="2b009-151">On your PC - [install](https://docs.telerik.com/fiddler-everywhere/get-started/installation-procedure) and start Fiddler.</span></span>  
1. <span data-ttu-id="2b009-152">Op uw pc: configureer Fiddler zodat externe computers verbinding kunnen maken.</span><span class="sxs-lookup"><span data-stu-id="2b009-152">On your PC - configure Fiddler to allow remote computers to connect.</span></span>
    1. <span data-ttu-id="2b009-153">Ga naar Fiddler Instellingen -> Connections</span><span class="sxs-lookup"><span data-stu-id="2b009-153">Go to Fiddler Settings -> Connections</span></span>
    1. <span data-ttu-id="2b009-154">Let op de luisterpoort voor Fiddler (standaard is dit 8866)</span><span class="sxs-lookup"><span data-stu-id="2b009-154">Note the listening port for Fiddler (default is 8866)</span></span>
    1. <span data-ttu-id="2b009-155">Controleer Externe computers toestaan verbinding te maken</span><span class="sxs-lookup"><span data-stu-id="2b009-155">Check Allow remote computers to connect</span></span>
    1. <span data-ttu-id="2b009-156">Klik op Opslaan</span><span class="sxs-lookup"><span data-stu-id="2b009-156">Click Save</span></span>
3. <span data-ttu-id="2b009-157">Configureer fiddler op uw HoloLens 2 als proxyserver<sup>1</sup>:</span><span class="sxs-lookup"><span data-stu-id="2b009-157">On your HoloLens 2 – configure Fiddler as the proxy server<sup>1</sup>:</span></span>
    1. <span data-ttu-id="2b009-158">Open het Startmenu en selecteer Instellingen</span><span class="sxs-lookup"><span data-stu-id="2b009-158">Open the Start menu and select Settings</span></span>
    1. <span data-ttu-id="2b009-159">Selecteer Network & Internet en vervolgens Proxy in het menu links</span><span class="sxs-lookup"><span data-stu-id="2b009-159">Select Network & Internet and then Proxy on the left menu</span></span>
    1. <span data-ttu-id="2b009-160">Schuif omlaag naar Handmatige proxy-installatie en stel Een proxyserver gebruiken in op Aan</span><span class="sxs-lookup"><span data-stu-id="2b009-160">Scroll down to Manual proxy setup and toggle Use a proxy server to On</span></span>
    1. <span data-ttu-id="2b009-161">Voer het IP-adres in van de pc waarop Fiddler is geïnstalleerd</span><span class="sxs-lookup"><span data-stu-id="2b009-161">Enter the IP address of the PC where Fiddler is installed</span></span>
    1. <span data-ttu-id="2b009-162">Voer het poortnummer in dat u hierboven vermeldt (de standaardwaarde is 8866)</span><span class="sxs-lookup"><span data-stu-id="2b009-162">Enter the port number noted above (default is 8866)</span></span>
    1. <span data-ttu-id="2b009-163">Klik op Opslaan</span><span class="sxs-lookup"><span data-stu-id="2b009-163">Click Save</span></span>

<span data-ttu-id="2b009-164"><sup>1</sup> Voor builds 20279.1006+ (Insiders en de volgende release) gebruikt u de volgende stappen om de proxy te configureren:</span><span class="sxs-lookup"><span data-stu-id="2b009-164"><sup>1</sup> For builds 20279.1006+ (Insiders and the upcoming release), use the following steps to configure proxy:</span></span>
1. <span data-ttu-id="2b009-165">Open de Startmenu en ga naar de Wi-Fi van uw netwerk</span><span class="sxs-lookup"><span data-stu-id="2b009-165">Open the Start menu and go to your Wi-Fi Network’s Properties page</span></span> 
1. <span data-ttu-id="2b009-166">Schuif omlaag naar Proxy</span><span class="sxs-lookup"><span data-stu-id="2b009-166">Scroll down to Proxy</span></span>
1. <span data-ttu-id="2b009-167">Wijzigen in Handmatige installatie</span><span class="sxs-lookup"><span data-stu-id="2b009-167">Change to Manual Setup</span></span>
1. <span data-ttu-id="2b009-168">Voer het IP-adres in van de pc waarop Fiddler is geïnstalleerd</span><span class="sxs-lookup"><span data-stu-id="2b009-168">Enter the IP address of the PC where Fiddler is installed</span></span>
1. <span data-ttu-id="2b009-169">Voer het hierboven genoteerde poortnummer in.</span><span class="sxs-lookup"><span data-stu-id="2b009-169">Enter the port number noted above.</span></span> <span data-ttu-id="2b009-170">(de standaardwaarde is 8866)</span><span class="sxs-lookup"><span data-stu-id="2b009-170">(default is 8866)</span></span>
1. <span data-ttu-id="2b009-171">Klik op Toepassen</span><span class="sxs-lookup"><span data-stu-id="2b009-171">Click Apply</span></span>
    
#### <a name="decrypt-https-traffic-from-hololens-2"></a><span data-ttu-id="2b009-172">HTTPS-verkeer ontsleutelen van HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="2b009-172">Decrypt HTTPS traffic from HoloLens 2</span></span>

1. <span data-ttu-id="2b009-173">Exporteert u het Fiddler-certificaat op uw pc.</span><span class="sxs-lookup"><span data-stu-id="2b009-173">On your PC – export the Fiddler certificate.</span></span>
    1. <span data-ttu-id="2b009-174">Ga naar Fiddler Instellingen -> HTTPS en vouw Geavanceerde Instellingen</span><span class="sxs-lookup"><span data-stu-id="2b009-174">Go to Fiddler Settings -> HTTPS and expand Advanced Settings</span></span>
    2. <span data-ttu-id="2b009-175">Klik op Fiddler-certificaat exporteren.</span><span class="sxs-lookup"><span data-stu-id="2b009-175">Click Export Fiddler certificate.</span></span> <span data-ttu-id="2b009-176">Het wordt op uw bureaublad op slaan</span><span class="sxs-lookup"><span data-stu-id="2b009-176">It will save to your desktop</span></span>
    3. <span data-ttu-id="2b009-177">Verplaats het certificaat naar de map Downloads op uw HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="2b009-177">Move the certificate over to the Downloads folder on your HoloLens 2</span></span>

2.  <span data-ttu-id="2b009-178">Importeer HoloLens 2 Fiddler-certificaat op uw HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="2b009-178">On your HoloLens 2 - import the Fiddler certificate.</span></span>
    1. <span data-ttu-id="2b009-179">Ga naar Instellingen -> Update and Security -> Certificates</span><span class="sxs-lookup"><span data-stu-id="2b009-179">Go to Settings -> Update and Security -> Certificates</span></span>
    2. <span data-ttu-id="2b009-180">Klik op Certificaat installeren, blader naar de map Downloads en selecteer het Fiddler-certificaat</span><span class="sxs-lookup"><span data-stu-id="2b009-180">Click Install Certificate, browse to the Downloads folder and select the Fiddler certificate</span></span>
    3. <span data-ttu-id="2b009-181">Winkellocatie wijzigen in Lokale computer</span><span class="sxs-lookup"><span data-stu-id="2b009-181">Change Store Location to Local Machine</span></span>
    4. <span data-ttu-id="2b009-182">Certificaatopslag wijzigen in root</span><span class="sxs-lookup"><span data-stu-id="2b009-182">Change Certificate Store to root</span></span>
    5. <span data-ttu-id="2b009-183">Selecteer Installeren</span><span class="sxs-lookup"><span data-stu-id="2b009-183">Select Install</span></span>
    6. <span data-ttu-id="2b009-184">Controleer of het certificaat wordt weergegeven in de lijst met certificaten.</span><span class="sxs-lookup"><span data-stu-id="2b009-184">Confirm the certificate is showing in the list of certificates.</span></span> <span data-ttu-id="2b009-185">Als dat niet het beste is, herhaalt u de bovenstaande stappen</span><span class="sxs-lookup"><span data-stu-id="2b009-185">If not, repeat the above steps</span></span>

#### <a name="inspect-https-sessions"></a><span data-ttu-id="2b009-186">HTTP(S)-sessies inspecteren</span><span class="sxs-lookup"><span data-stu-id="2b009-186">Inspect HTTP(S) sessions</span></span>

<span data-ttu-id="2b009-187">Op uw pc geeft Fiddler de live HTTP(S)-sessies van de HoloLens 2 van de gebruiker weer.</span><span class="sxs-lookup"><span data-stu-id="2b009-187">On your PC, Fiddler will show the HoloLens 2’s live HTTP(S) sessions.</span></span> <span data-ttu-id="2b009-188">In het deelvenster Inspectors in Fiddler kunnen HTTP(S)-aanvragen/-antwoorden in verschillende weergaven worden weergegeven. In de weergave Onbewerkt ziet u bijvoorbeeld de onbewerkte aanvraag of het antwoord in tekst zonder tekst.</span><span class="sxs-lookup"><span data-stu-id="2b009-188">The Inspectors panel in Fiddler can show HTTP(S) request/response in different views - for example, the “Raw” view shows the raw request or response in plain text.</span></span> 

### <a name="configure-wireshark-to-capture-network-traffic"></a><span data-ttu-id="2b009-189">Wireshark configureren om netwerkverkeer vast te leggen</span><span class="sxs-lookup"><span data-stu-id="2b009-189">Configure Wireshark to capture network traffic</span></span>
<span data-ttu-id="2b009-190">Wireshark is een netwerkprotocolanalyse en wordt gebruikt om TCP/UDP-verkeer van en naar uw HoloLens 2 controleren.</span><span class="sxs-lookup"><span data-stu-id="2b009-190">Wireshark is a network protocol analyzer and is used to inspect TCP/UDP traffic from and to your HoloLens 2 devices.</span></span> <span data-ttu-id="2b009-191">Zo kunt u eenvoudig bepalen welk verkeer uw netwerk doorkruist naar uw HoloLens 2, hoeveel ervan, hoe vaak, hoeveel latentie er is tussen bepaalde hops, enzovoort.</span><span class="sxs-lookup"><span data-stu-id="2b009-191">This makes it easy to identify what traffic is crossing your network to your HoloLens 2, how much of it, how frequently, how much latency there is between certain hops, and so forth.</span></span>

#### <a name="prerequisites"></a><span data-ttu-id="2b009-192">Vereisten:</span><span class="sxs-lookup"><span data-stu-id="2b009-192">Prerequisites:</span></span>
- <span data-ttu-id="2b009-193">De pc moet internettoegang hebben en internet delen via Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="2b009-193">PC must have internet access and support Internet sharing over Wi-Fi</span></span>

#### <a name="install-and-configure-wireshark"></a><span data-ttu-id="2b009-194">Wireshark installeren en configureren</span><span class="sxs-lookup"><span data-stu-id="2b009-194">Install and Configure Wireshark</span></span>
1. <span data-ttu-id="2b009-195">Op uw pc - [Wireshark installeren](https://www.wireshark.org/#download)</span><span class="sxs-lookup"><span data-stu-id="2b009-195">On your PC - install [Wireshark](https://www.wireshark.org/#download)</span></span> 
1. <span data-ttu-id="2b009-196">Op uw pc: schakel Mobiele hotspot in om uw internetverbinding via Wi-Fi te delen.</span><span class="sxs-lookup"><span data-stu-id="2b009-196">On your PC - enable Mobile hotspot to share your Internet connection from Wi-Fi.</span></span>
1. <span data-ttu-id="2b009-197">Op uw pc: start Wireshark en leg verkeer vast vanuit de interface voor mobiele hotspots.</span><span class="sxs-lookup"><span data-stu-id="2b009-197">On your PC - start Wireshark and capture traffic from the Mobile hotspot interface.</span></span> 
1. <span data-ttu-id="2b009-198">Op uw HoloLens 2 wijzigt u het Wi-Fi netwerk in de mobiele hotspot van de pc.</span><span class="sxs-lookup"><span data-stu-id="2b009-198">On your HoloLens 2 – change its Wi-Fi network to the PC’s Mobile hotspot.</span></span> <span data-ttu-id="2b009-199">HoloLens 2 IP-verkeer wordt in Wireshark weer geven.</span><span class="sxs-lookup"><span data-stu-id="2b009-199">HoloLens 2 IP traffic will show up in Wireshark.</span></span>

#### <a name="analyze-wireshark-logs"></a><span data-ttu-id="2b009-200">Wireshark-logboeken analyseren</span><span class="sxs-lookup"><span data-stu-id="2b009-200">Analyze Wireshark logs</span></span>
<span data-ttu-id="2b009-201">Wireshark-filters kunnen helpen bij het filteren van de pakketten met interesses.</span><span class="sxs-lookup"><span data-stu-id="2b009-201">Wireshark filters can help filtering out the packets of interests.</span></span> 

<span data-ttu-id="2b009-202">Bekijk de oorspronkelijke [blog](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/diagnose-hololens-2-network-issues-with-fiddler-and-wireshark/ba-p/2322458).</span><span class="sxs-lookup"><span data-stu-id="2b009-202">Check out the original [blog](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/diagnose-hololens-2-network-issues-with-fiddler-and-wireshark/ba-p/2322458).</span></span>

[<span data-ttu-id="2b009-203">Terug naar lijst</span><span class="sxs-lookup"><span data-stu-id="2b009-203">Back to list</span></span>](#list)

## <a name="cant-sign-in-to-a-previously-setup-hololens-device"></a><span data-ttu-id="2b009-204">Kan niet aanmelden bij een eerder ingesteld apparaat HoloLens apparaat</span><span class="sxs-lookup"><span data-stu-id="2b009-204">Can't sign in to a previously setup HoloLens device</span></span>

<span data-ttu-id="2b009-205">Als uw apparaat eerder is ingesteld voor iemand anders, voor een client of voor een voormalige werknemer, en u niet het [](/intune/remote-actions/devices-wipe) wachtwoord hebt om het apparaat te ontgrendelen, kunt u Intune gebruiken om het apparaat op afstand te wissen.</span><span class="sxs-lookup"><span data-stu-id="2b009-205">If your device was previously set up for someone else, either for a client or for a former employee, and you don't have their password to unlock the device, you can use Intune to remotely [wipe](/intune/remote-actions/devices-wipe) the device.</span></span> <span data-ttu-id="2b009-206">Het apparaat flasht zichzelf vervolgens opnieuw.</span><span class="sxs-lookup"><span data-stu-id="2b009-206">The device then re-flashes itself.</span></span>  
> [!IMPORTANT]
> <span data-ttu-id="2b009-207">Wanneer u het apparaat wist, zorg er dan voor dat Inschrijvingstoestand en gebruikersaccount **behouden** uitgeschakeld blijven.</span><span class="sxs-lookup"><span data-stu-id="2b009-207">When you wipe the device, make sure to leave **Retain enrollment state and user account** unchecked.</span></span>

[<span data-ttu-id="2b009-208">Terug naar lijst</span><span class="sxs-lookup"><span data-stu-id="2b009-208">Back to list</span></span>](#list)

## <a name="cant-login-after-updating-to-windows-holographic-21h1"></a><span data-ttu-id="2b009-209">Kan niet aanmelden na het bijwerken naar Windows Holographic 21H1</span><span class="sxs-lookup"><span data-stu-id="2b009-209">Can't login after updating to Windows Holographic 21H1</span></span>

### <a name="symptoms"></a><span data-ttu-id="2b009-210">Symptomen</span><span class="sxs-lookup"><span data-stu-id="2b009-210">Symptoms</span></span>
- <span data-ttu-id="2b009-211">Het gebruik van een pincode voor aanmelding mislukt nadat u de juiste pincode hebt invoeren.</span><span class="sxs-lookup"><span data-stu-id="2b009-211">Using PIN to logon will fail after entering the correct PIN.</span></span>
- <span data-ttu-id="2b009-212">Het gebruik van de web-aanmeldingsmethode mislukt nadat u zich hebt aanmelden op de webpagina.</span><span class="sxs-lookup"><span data-stu-id="2b009-212">Using the web logon method will fail after successfully signing in on the web page.</span></span>
- <span data-ttu-id="2b009-213">Het apparaat wordt niet vermeld als 'Azure AD-toegevoegd' in [Azure Portal](https://portal.azure.com/) -> Azure Active Directory -> Devices.</span><span class="sxs-lookup"><span data-stu-id="2b009-213">The device is not listed as “Azure AD joined” in [Azure portal](https://portal.azure.com/) -> Azure Active Directory -> Devices.</span></span>

### <a name="cause"></a><span data-ttu-id="2b009-214">Oorzaak</span><span class="sxs-lookup"><span data-stu-id="2b009-214">Cause</span></span>
<span data-ttu-id="2b009-215">Het beïnvloede apparaat is mogelijk verwijderd uit de Azure AD-tenant.</span><span class="sxs-lookup"><span data-stu-id="2b009-215">The impacted device may have been deleted from the Azure AD tenant.</span></span> <span data-ttu-id="2b009-216">Dit kan bijvoorbeeld gebeuren omdat:</span><span class="sxs-lookup"><span data-stu-id="2b009-216">For example, this may happen because:</span></span>

- <span data-ttu-id="2b009-217">Een beheerder of gebruiker heeft het apparaat verwijderd in de Azure Portal of met behulp van PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2b009-217">An administrator or user deleted the device in the Azure portal or using PowerShell.</span></span>
- <span data-ttu-id="2b009-218">Het apparaat is verwijderd uit de Azure AD-tenant vanwege inactiviteit.</span><span class="sxs-lookup"><span data-stu-id="2b009-218">The device was removed from the Azure AD tenant due to inactivity.</span></span> <span data-ttu-id="2b009-219">Voor een efficiënt beheerde omgeving raden we IT-beheerders doorgaans aan verouderde, inactieve apparaten uit hun [Azure AD-tenant te verwijderen.](/azure/active-directory/devices/manage-stale-devices)</span><span class="sxs-lookup"><span data-stu-id="2b009-219">For an efficiently managed environment, we typically recommend IT admins to [remove stale, inactive devices from their Azure AD tenant](/azure/active-directory/devices/manage-stale-devices).</span></span>

<span data-ttu-id="2b009-220">Wanneer een beïnvloed apparaat opnieuw contact probeert te maken met de Azure AD-tenant nadat het is verwijderd, kan het apparaat niet worden geverifieerd bij Azure AD.</span><span class="sxs-lookup"><span data-stu-id="2b009-220">When an impacted device attempts to contact the Azure AD tenant again after it has been deleted it will fail to authenticate with Azure AD.</span></span> <span data-ttu-id="2b009-221">Dit effect is vaak onzichtbaar voor de gebruiker van het apparaat, omdat aanmelding in de cache via een pincode de gebruiker blijft toestaan zich aan te geven.</span><span class="sxs-lookup"><span data-stu-id="2b009-221">This effect is often invisible to the user of the device, as cached logon via PIN will continue to allow the user to logon.</span></span>

### <a name="mitigation"></a><span data-ttu-id="2b009-222">Oplossing</span><span class="sxs-lookup"><span data-stu-id="2b009-222">Mitigation</span></span>
<span data-ttu-id="2b009-223">Er is momenteel geen manier om een verwijderd apparaat HoloLens toevoegen aan Azure AD.</span><span class="sxs-lookup"><span data-stu-id="2b009-223">There is currently no way to add a deleted HoloLens device back into Azure AD.</span></span> <span data-ttu-id="2b009-224">Betrokken apparaten moeten clean-reflashed worden door de instructies te volgen voor [het reflashen van hun apparaat.](hololens-recovery.md#clean-reflash-the-device)</span><span class="sxs-lookup"><span data-stu-id="2b009-224">Affected devices will need to be clean-reflashed by following the instructions on [reflashing their device](hololens-recovery.md#clean-reflash-the-device).</span></span>

[<span data-ttu-id="2b009-225">Terug naar lijst</span><span class="sxs-lookup"><span data-stu-id="2b009-225">Back to list</span></span>](#list)

## <a name="autopilot-troubleshooting"></a><span data-ttu-id="2b009-226">Problemen met Autopilot oplossen</span><span class="sxs-lookup"><span data-stu-id="2b009-226">Autopilot Troubleshooting</span></span>

<span data-ttu-id="2b009-227">De volgende artikelen kunnen een nuttige resource zijn voor meer informatie en het oplossen van Autopilot-problemen. Houd er echter rekening mee dat deze artikelen zijn gebaseerd op Windows 10 Desktop en dat niet alle informatie van toepassing is op HoloLens:</span><span class="sxs-lookup"><span data-stu-id="2b009-227">The following articles may be a useful resource for you to learn more information and troubleshoot Autopilot Issues, however please be aware that these articles are based on Windows 10 Desktop and not all information may apply to HoloLens:</span></span>

- [<span data-ttu-id="2b009-228">Windows Autopilot - bekende problemen</span><span class="sxs-lookup"><span data-stu-id="2b009-228">Windows Autopilot - known issues</span></span>](/mem/autopilot/known-issues)
- [<span data-ttu-id="2b009-229">Problemen met inschrijving van Windows-apparaten in Microsoft Intune oplossen</span><span class="sxs-lookup"><span data-stu-id="2b009-229">Troubleshoot Windows device enrollment problems in Microsoft Intune</span></span>](/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [<span data-ttu-id="2b009-230">Windows Autopilot - Beleidsconflicten</span><span class="sxs-lookup"><span data-stu-id="2b009-230">Windows Autopilot - Policy Conflicts</span></span>](/mem/autopilot/policy-conflicts)

[<span data-ttu-id="2b009-231">Terug naar lijst</span><span class="sxs-lookup"><span data-stu-id="2b009-231">Back to list</span></span>](#list)

## <a name="managed-hololens-devices-faqs"></a><span data-ttu-id="2b009-232">Veelgestelde HoloLens beheerde apparaten</span><span class="sxs-lookup"><span data-stu-id="2b009-232">Managed HoloLens Devices FAQs</span></span>

### <a name="can-i-use-system-center-configuration-manager-sccm-to-manage-hololens-devices"></a><span data-ttu-id="2b009-233">Kan ik System Center Configuration Manager (SCCM) gebruiken om uw HoloLens beheren?</span><span class="sxs-lookup"><span data-stu-id="2b009-233">Can I use System Center Configuration Manager (SCCM) to manage HoloLens devices?</span></span>

<span data-ttu-id="2b009-234">Nee.</span><span class="sxs-lookup"><span data-stu-id="2b009-234">No.</span></span> <span data-ttu-id="2b009-235">U moet een MDM-systeem gebruiken om uw apparaten HoloLens beheren.</span><span class="sxs-lookup"><span data-stu-id="2b009-235">You have to use an MDM system to manage HoloLens devices.</span></span>

### <a name="can-i-use-active-directory-domain-services-ad-ds-to-manage-hololens-user-accounts"></a><span data-ttu-id="2b009-236">Kan ik Active Directory Domain Services (AD DS) gebruiken voor het beheren HoloLens gebruikersaccounts?</span><span class="sxs-lookup"><span data-stu-id="2b009-236">Can I use Active Directory Domain Services (AD DS) to manage HoloLens user accounts?</span></span>

<span data-ttu-id="2b009-237">Nee.</span><span class="sxs-lookup"><span data-stu-id="2b009-237">No.</span></span> <span data-ttu-id="2b009-238">U moet Azure Active Directory (Azure AD) gebruiken om gebruikersaccounts voor HoloLens beheren.</span><span class="sxs-lookup"><span data-stu-id="2b009-238">You have to use Azure Active Directory (Azure AD) to manage user accounts for HoloLens devices.</span></span>

### <a name="is-hololens-capable-of-automated-data-capture-systems-adcs-auto-enrollment"></a><span data-ttu-id="2b009-239">Is HoloLens automatische inschrijving van Automated Data Capture Systems (ADCS) mogelijk?</span><span class="sxs-lookup"><span data-stu-id="2b009-239">Is HoloLens capable of Automated Data Capture Systems (ADCS) auto-enrollment?</span></span>

<span data-ttu-id="2b009-240">Nee.</span><span class="sxs-lookup"><span data-stu-id="2b009-240">No.</span></span>

### <a name="can-hololens-participate-in-integrated-windows-authentication"></a><span data-ttu-id="2b009-241">Kan HoloLens deelnemen aan geïntegreerde Windows-verificatie?</span><span class="sxs-lookup"><span data-stu-id="2b009-241">Can HoloLens participate in Integrated Windows Authentication?</span></span>

<span data-ttu-id="2b009-242">Nee.</span><span class="sxs-lookup"><span data-stu-id="2b009-242">No.</span></span>

### <a name="does-hololens-support-branding"></a><span data-ttu-id="2b009-243">Biedt HoloLens ondersteuning voor huisstijl?</span><span class="sxs-lookup"><span data-stu-id="2b009-243">Does HoloLens support branding?</span></span>

<span data-ttu-id="2b009-244">Nee.</span><span class="sxs-lookup"><span data-stu-id="2b009-244">No.</span></span> <span data-ttu-id="2b009-245">U kunt dit probleem echter oplossen met behulp van een van de volgende methoden:</span><span class="sxs-lookup"><span data-stu-id="2b009-245">However, you can work around this issue by using one of the following approaches:</span></span>

- <span data-ttu-id="2b009-246">Maak een aangepaste app en schakel vervolgens [kioskmodus in.](hololens-kiosk.md)</span><span class="sxs-lookup"><span data-stu-id="2b009-246">Create a custom app, and then [enable Kiosk mode](hololens-kiosk.md).</span></span> <span data-ttu-id="2b009-247">De aangepaste app kan een huisstijl hebben en kan andere apps starten (zoals Remote Assist).</span><span class="sxs-lookup"><span data-stu-id="2b009-247">The custom app can have branding, and can launch other apps (such as Remote Assist).</span></span>  
- <span data-ttu-id="2b009-248">Wijzig alle gebruikersprofielfoto's in Azure AD in uw bedrijfslogo.</span><span class="sxs-lookup"><span data-stu-id="2b009-248">Change all of the user profile pictures in Azure AD to your company logo.</span></span> <span data-ttu-id="2b009-249">Dit is echter mogelijk niet wenselijk voor alle scenario's.</span><span class="sxs-lookup"><span data-stu-id="2b009-249">However, this may not be desirable for all scenarios.</span></span>

### <a name="what-logging-capabilities-does-hololens-2-offer"></a><span data-ttu-id="2b009-250">Welke logboekregistratiemogelijkheden biedt HoloLens 2 bieden?</span><span class="sxs-lookup"><span data-stu-id="2b009-250">What logging capabilities does HoloLens 2 offer?</span></span>

<span data-ttu-id="2b009-251">Logboekregistratie is beperkt tot traceringen die kunnen worden vastgelegd in ontwikkel- of probleemoplossingsscenario's, of telemetrie die de apparaten naar Microsoft-servers verzenden.</span><span class="sxs-lookup"><span data-stu-id="2b009-251">Logging is limited to traces that can be captured in development or troubleshooting scenarios, or telemetry that the devices send to Microsoft servers.</span></span>

## <a name="questions-about-securing-hololens-devices"></a><span data-ttu-id="2b009-252">Vragen over het beveiligen HoloLens apparaten</span><span class="sxs-lookup"><span data-stu-id="2b009-252">Questions about securing HoloLens devices</span></span>

<span data-ttu-id="2b009-253">Zie [onze HoloLens 2 beveiligingsinformatie](security-overview.md).</span><span class="sxs-lookup"><span data-stu-id="2b009-253">See [our HoloLens 2 security information](security-overview.md).</span></span>
<span data-ttu-id="2b009-254">Raadpleeg HoloLens veelgestelde vragen voor meer informatie over apparaten uit [de eerste generatie.](hololens1-faq-security.yml)</span><span class="sxs-lookup"><span data-stu-id="2b009-254">For HoloLens 1st Gen devices please review [this FAQ](hololens1-faq-security.yml).</span></span>

[<span data-ttu-id="2b009-255">Terug naar lijst</span><span class="sxs-lookup"><span data-stu-id="2b009-255">Back to list</span></span>](#list)
