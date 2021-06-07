---
title: HoloLens verbinden met een netwerk
description: Meer informatie over het instellen en verbinden met internet met HoloLens en het identificeren van het IP-adres van het apparaat.
ms.assetid: 0895606e-96c0-491e-8b1c-52e56b00365d
author: mattzmsft
ms.author: mazeller
keywords: HoloLens, Wi-Fi, draadloos, internet, IP, IP-adres
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
ms.openlocfilehash: d68c75dcb2249a67f2e07c77cb1b69997eb0ae72
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/25/2021
ms.locfileid: "111379428"
---
# <a name="connect-hololens-to-a-network"></a><span data-ttu-id="ab21d-104">HoloLens verbinden met een netwerk</span><span class="sxs-lookup"><span data-stu-id="ab21d-104">Connect HoloLens to a network</span></span>

<span data-ttu-id="ab21d-105">Als u de meeste dingen op uw HoloLens wilt doen, moet u zijn verbonden met een netwerk.</span><span class="sxs-lookup"><span data-stu-id="ab21d-105">To do most things on your HoloLens, you have to be connected to a network.</span></span> <span data-ttu-id="ab21d-106">HoloLens bevat een 802.11ac-geschikt 2x2 Wi-Fi-radio en het verbinden ervan met een netwerk is vergelijkbaar met het verbinden van een Windows 10 Desktop- of Mobile-apparaat met een Wi-Fi-netwerk.</span><span class="sxs-lookup"><span data-stu-id="ab21d-106">HoloLens contains a 802.11ac-capable, 2x2 Wi-Fi radio and connecting it to a network is similar to connecting a Windows 10 Desktop or Mobile device to a Wi-Fi network.</span></span> <span data-ttu-id="ab21d-107">Deze handleiding helpt u bij het volgende:</span><span class="sxs-lookup"><span data-stu-id="ab21d-107">This guide will help you:</span></span>

- <span data-ttu-id="ab21d-108">Maak verbinding met een netwerk via Wi-Fi of HoloLens 2 alleen Wi-Fi Direct of Ethernet via USB-C</span><span class="sxs-lookup"><span data-stu-id="ab21d-108">Connect to a network using Wi-Fi, or for HoloLens 2 only, Wi-Fi Direct or Ethernet over USB-C</span></span>
- <span data-ttu-id="ab21d-109">Schakel de Wi-Fi en schakel deze opnieuw Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="ab21d-109">Disable and re-enable Wi-Fi</span></span>

<span data-ttu-id="ab21d-110">Lees meer over het [offline gebruik van HoloLens.](hololens-offline.md)</span><span class="sxs-lookup"><span data-stu-id="ab21d-110">Read more about [using HoloLens offline](hololens-offline.md).</span></span>

## <a name="connecting-for-the-first-time"></a><span data-ttu-id="ab21d-111">Voor de eerste keer verbinding maken</span><span class="sxs-lookup"><span data-stu-id="ab21d-111">Connecting for the first time</span></span>

<span data-ttu-id="ab21d-112">De eerste keer dat u uw HoloLens gebruikt, wordt u begeleid bij het maken van verbinding met Wi-Fi netwerk.</span><span class="sxs-lookup"><span data-stu-id="ab21d-112">The first time you use your HoloLens, you'll be guided through connecting to a Wi-Fi network.</span></span> <span data-ttu-id="ab21d-113">Als u tijdens de installatie problemen hebt met het maken van verbinding met Wi-Fi, moet u ervoor zorgen dat uw netwerk een open, met wachtwoorden beveiligd netwerk of een captive portal-netwerk is.</span><span class="sxs-lookup"><span data-stu-id="ab21d-113">If you have trouble connecting to Wi-Fi during setup, make sure that your network is either an open, password-protected network or a captive portal network.</span></span> <span data-ttu-id="ab21d-114">Controleer ook of u voor het netwerk geen certificaat hoeft te gebruiken om verbinding te maken.</span><span class="sxs-lookup"><span data-stu-id="ab21d-114">Also, confirm that the network doesn't require you to use a certificate to connect.</span></span> <span data-ttu-id="ab21d-115">Na de installatie kunt u verbinding maken met andere typen Wi-Fi netwerken.</span><span class="sxs-lookup"><span data-stu-id="ab21d-115">After setup, you can connect to other types of Wi-Fi networks.</span></span>

<span data-ttu-id="ab21d-116">Op HoloLens 2 apparaten kan een gebruiker ook een [USB-C-naar-Ethernet-adapter](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) gebruiken om rechtstreeks verbinding te maken met Wi-Fi om te helpen bij het instellen van het apparaat.</span><span class="sxs-lookup"><span data-stu-id="ab21d-116">On HoloLens 2 devices, a user may also [use a USB-C to Ethernet adapter](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) to connect directly to Wi-Fi to help assist in setting up the device.</span></span> <span data-ttu-id="ab21d-117">Zodra het apparaat is ingesteld, kan een gebruiker de adapter blijven gebruiken of het apparaat loskoppelen van de adapter en verbinding maken [met Wi-Fi](hololens-network.md#connecting-to-wi-fi-after-setup)na het instellen.</span><span class="sxs-lookup"><span data-stu-id="ab21d-117">Once the device has been set up a user may continue to use the adapter or they may disconnect the device from the adapter and [connect to wi-fi after set up](hololens-network.md#connecting-to-wi-fi-after-setup).</span></span> 

## <a name="connecting-to-wi-fi-after-setup"></a><span data-ttu-id="ab21d-118">Verbinding maken met Wi-Fi na de installatie</span><span class="sxs-lookup"><span data-stu-id="ab21d-118">Connecting to Wi-Fi after setup</span></span>

1. <span data-ttu-id="ab21d-119">Maak de beweging **Start vooraf en** selecteer **Instellingen.**</span><span class="sxs-lookup"><span data-stu-id="ab21d-119">Preform the **Start gesture** and select **Settings**.</span></span> <span data-ttu-id="ab21d-120">De app Instellingen wordt automatisch voor u geplaatst.</span><span class="sxs-lookup"><span data-stu-id="ab21d-120">The Settings app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="ab21d-121">Selecteer **Network & Internet**  >  **Wi-Fi.**</span><span class="sxs-lookup"><span data-stu-id="ab21d-121">Select **Network & Internet** > **Wi-Fi**.</span></span> <span data-ttu-id="ab21d-122">Controleer of Wi-Fi is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="ab21d-122">Make sure Wi-Fi is turned on.</span></span> <span data-ttu-id="ab21d-123">Als u uw netwerk niet ziet, schuift u omlaag in de lijst.</span><span class="sxs-lookup"><span data-stu-id="ab21d-123">If you don't see your network, scroll down the list.</span></span>
1. <span data-ttu-id="ab21d-124">Selecteer een netwerk en selecteer vervolgens **Verbinding maken.**</span><span class="sxs-lookup"><span data-stu-id="ab21d-124">Select a network, then select **Connect**.</span></span>
1. <span data-ttu-id="ab21d-125">Als u wordt gevraagd om een netwerkwachtwoord typt u dit en selecteert u **volgende.**</span><span class="sxs-lookup"><span data-stu-id="ab21d-125">If you are prompted for a network password type it and then select **Next**.</span></span>

![Instellingen voor HoloLens-Wi-Fi](./images/hololens-2-wifi-settings.jpg)

<span data-ttu-id="ab21d-127">Controleer de status van Wi-Fi netwerk in het menu Start om Wi-Fi te **controleren:**</span><span class="sxs-lookup"><span data-stu-id="ab21d-127">To confirm you are connected to a Wi-Fi network, check the Wi-Fi status in the **Start** menu:</span></span>

1. <span data-ttu-id="ab21d-128">Open het **menu** Start.</span><span class="sxs-lookup"><span data-stu-id="ab21d-128">Open the **Start** menu.</span></span>
1. <span data-ttu-id="ab21d-129">Bekijk linksboven in het menu **Start** de status Wi-Fi weergeven.</span><span class="sxs-lookup"><span data-stu-id="ab21d-129">Look at the top left of the **Start** menu for Wi-Fi status.</span></span> <span data-ttu-id="ab21d-130">De status van Wi-Fi en de SSID van het verbonden netwerk worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="ab21d-130">The state of Wi-Fi and the SSID of the connected network will be shown.</span></span>

> [!TIP]
> <span data-ttu-id="ab21d-131">Als Wi-Fi niet beschikbaar is, kunt u ook verbinding [maken met mobiele en 5G-netwerken.](https://docs.microsoft.com/hololens/hololens-cellular)</span><span class="sxs-lookup"><span data-stu-id="ab21d-131">If Wi-Fi is not available, you can also [connect to Cellular and 5G networks](https://docs.microsoft.com/hololens/hololens-cellular).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ab21d-132">Gebruikers kunnen het Wi-Fi-roaminggedrag van de HoloLens 2 niet afstemmen. De enige manier om de Wi-Fi-lijst te **vernieuwen, is door** de Wi-Fi Uit en Aan te zetten.</span><span class="sxs-lookup"><span data-stu-id="ab21d-132">By design, users cannot fine tune the Wi-Fi roaming behavior of the HoloLens 2 - **the only way to refresh the Wi-Fi list is to toggle the Wi-Fi Off and On**.</span></span> <span data-ttu-id="ab21d-133">Dit voorkomt veel problemen, zoals wanneer een apparaat 'vastloopt' aan een AP wanneer het buiten het bereik valt.</span><span class="sxs-lookup"><span data-stu-id="ab21d-133">This prevents many issues, like where a device can remain "stuck" to an AP once it is out of range.</span></span>

## <a name="troubleshooting-your-connection-to-wi-fi"></a><span data-ttu-id="ab21d-134">Problemen met uw verbinding met Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="ab21d-134">Troubleshooting your connection to Wi-Fi</span></span>

<span data-ttu-id="ab21d-135">Als u problemen hebt met het maken van verbinding met Wi-Fi, zie Ik kan geen verbinding [maken met Wi-Fi.](./hololens-faq.md#i-cant-connect-to-wi-fi)</span><span class="sxs-lookup"><span data-stu-id="ab21d-135">If you experience problems connecting to Wi-Fi, see [I can't connect to Wi-Fi](./hololens-faq.md#i-cant-connect-to-wi-fi).</span></span>

<span data-ttu-id="ab21d-136">Wanneer u zich op het apparaat bij een bedrijfs- of organisatieaccount aankeert, kan het ook MDM-beleid (Mobile Device Management) toepassen als het beleid is geconfigureerd door uw IT-beheerder.</span><span class="sxs-lookup"><span data-stu-id="ab21d-136">When you sign into an enterprise or organizational account on the device, it may also apply Mobile Device Management (MDM) policy, if the policy is configured by your IT administrator.</span></span>

## <a name="connect-hololens-to-enterprise-wi-fi-network"></a><span data-ttu-id="ab21d-137">HoloLens verbinden met Enterprise Wi-Fi Network</span><span class="sxs-lookup"><span data-stu-id="ab21d-137">Connect HoloLens to Enterprise Wi-Fi Network</span></span>

<span data-ttu-id="ab21d-138">Enterprise Wi-Fi-profielen gebruiken Extensible Authentication Protocol (EAP) om verbinding Wi-Fi verifiëren.</span><span class="sxs-lookup"><span data-stu-id="ab21d-138">Enterprise Wi-Fi profiles use Extensible Authentication Protocol (EAP) to authenticate Wi-Fi connections.</span></span> <span data-ttu-id="ab21d-139">HoloLens Enterprise Wi-Fi-profiel kan worden geconfigureerd via MDM of een inrichtingspakket dat is gemaakt [door Windows Configuration Designer.](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages)</span><span class="sxs-lookup"><span data-stu-id="ab21d-139">HoloLens Enterprise Wi-Fi profile can be configured through MDM or provisioning package created by [Windows Configuration Designer](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages).</span></span>

<span data-ttu-id="ab21d-140">Raadpleeg Microsoft Intune [Intune](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) voor configuratie-instructies voor meer informatie over het beheerde apparaat.</span><span class="sxs-lookup"><span data-stu-id="ab21d-140">For Microsoft Intune managed device, refer to [Intune](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) for configuration instructions.</span></span>

<span data-ttu-id="ab21d-141">Als u een Wi-Fi inrichtingspakket in WCD wilt maken, is een vooraf geconfigureerd Wi-Fi-.xml vereist.</span><span class="sxs-lookup"><span data-stu-id="ab21d-141">To create a Wi-Fi provisioning package in WCD, a pre-configured Wi-Fi profile .xml file is required.</span></span> <span data-ttu-id="ab21d-142">Hier is een voorbeeld van Wi-Fi voor WPA2-Enterprise EAP-TLS-verificatie:</span><span class="sxs-lookup"><span data-stu-id="ab21d-142">Here is a sample Wi-Fi profile for WPA2-Enterprise with EAP-TLS authentication:</span></span>

``` xml
<?xml version="1.0"?> 
<WLANProfile xmlns="http://www.microsoft.com/networking/WLAN/profile/v1"> 
    <name>SampleEapTlsProfile</name> 
    <SSIDConfig> 
        <SSID> 
            <hex>53616d706c65</hex> 
            <name>Sample</name> 
        </SSID> 
        <nonBroadcast>true</nonBroadcast> 
    </SSIDConfig> 
    <connectionType>ESS</connectionType> 
    <connectionMode>auto</connectionMode> 
    <autoSwitch>false</autoSwitch> 
    <MSM> 
        <security> 
            <authEncryption> 
                <authentication>WPA2</authentication> 
                <encryption>AES</encryption> 
                <useOneX>true</useOneX> 
                <FIPSMode xmlns="http://www.microsoft.com/networking/WLAN/profile/v2">false</FIPSMode> 
            </authEncryption> 
            <PMKCacheMode>disabled</PMKCacheMode> 
            <OneX xmlns="http://www.microsoft.com/networking/OneX/v1"> 
                <authMode>machine</authMode> 
                <EAPConfig> 
                    <EapHostConfig xmlns="http://www.microsoft.com/provisioning/EapHostConfig"> 
                        <EapMethod> 
                            <Type xmlns="http://www.microsoft.com/provisioning/EapCommon">13</Type> 
                            <VendorId xmlns="http://www.microsoft.com/provisioning/EapCommon">0</VendorId> 
                            <VendorType xmlns="http://www.microsoft.com/provisioning/EapCommon">0</VendorType> 
                            <AuthorId xmlns="http://www.microsoft.com/provisioning/EapCommon">0</AuthorId> 
                        </EapMethod> 
                        <Config xmlns="http://www.microsoft.com/provisioning/EapHostConfig"> 
                            <Eap xmlns="http://www.microsoft.com/provisioning/BaseEapConnectionPropertiesV1"> 
                                <Type>13</Type> 
                                <EapType xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV1"> 
                                    <CredentialsSource><CertificateStore><SimpleCertSelection>true</SimpleCertSelection> 
                                        </CertificateStore> 
                                    </CredentialsSource> 
                                    <ServerValidation> 
                                        <DisableUserPromptForServerValidation>false</DisableUserPromptForServerValidation> 
                                        <ServerNames></ServerNames> 
                                        <TrustedRootCA>00 01 02 03 04 05 06 07 08 09 0a 0b 0c 0d 0e 0f 10 11 12 13</TrustedRootCA> 
                                    </ServerValidation> 
                                    <DifferentUsername>false</DifferentUsername> 
                                    <PerformServerValidation xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">true</PerformServerValidation> 
                                    <AcceptServerName xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">false</AcceptServerName> 
                                </EapType> 
                            </Eap> 
                        </Config> 
                    </EapHostConfig> 
                </EAPConfig> 
            </OneX> 
        </security> 
    </MSM> 
</WLANProfile> 
```


<span data-ttu-id="ab21d-143">Het CA-basiscertificaat van de server en het clientcertificaat moeten mogelijk worden ingericht op het apparaat, afhankelijk van het EAP-type.</span><span class="sxs-lookup"><span data-stu-id="ab21d-143">Server root CA certificate and client certificate may need to be provisioned on the device depending on the EAP type.</span></span>

<span data-ttu-id="ab21d-144">Aanvullende bronnen:</span><span class="sxs-lookup"><span data-stu-id="ab21d-144">Additional resources:</span></span>

- <span data-ttu-id="ab21d-145">WLANv1Profile Schema: [[MS-GPWL]: Draadloos LAN-profiel v1 Schema | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)</span><span class="sxs-lookup"><span data-stu-id="ab21d-145">WLANv1Profile Schema: [[MS-GPWL]: Wireless LAN Profile v1 Schema | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)</span></span>
- <span data-ttu-id="ab21d-146">EAP-TLS-schema: [[MS-GPWL]: Microsoft EAP TLS-schema | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)</span><span class="sxs-lookup"><span data-stu-id="ab21d-146">EAP-TLS Schema: [[MS-GPWL]: Microsoft EAP TLS Schema | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)</span></span>

## <a name="eap-troubleshooting"></a><span data-ttu-id="ab21d-147">Problemen met EAP oplossen</span><span class="sxs-lookup"><span data-stu-id="ab21d-147">EAP Troubleshooting</span></span>
> [!TIP]
> <span data-ttu-id="ab21d-148">Het merendeel van de netwerkproblemen is het gevolg van een van de onderstaande drie instellingen die onjuist zijn in het Wi-FI-profiel.</span><span class="sxs-lookup"><span data-stu-id="ab21d-148">A majority of network issues are the result of one of the below 3 settings being incorrect in the Wi-FI profile.</span></span> 
1. <span data-ttu-id="ab21d-149">Controleer of Wi-Fi profiel de juiste instellingen heeft:</span><span class="sxs-lookup"><span data-stu-id="ab21d-149">Double check Wi-Fi profile has right settings:</span></span>
   1. <span data-ttu-id="ab21d-150">EAP-type is correct geconfigureerd, algemene EAP-typen: EAP-TLS (13), EAP-TTLS (21) en PEAP (25).</span><span class="sxs-lookup"><span data-stu-id="ab21d-150">EAP type is configured correctly, common EAP types: EAP-TLS (13), EAP-TTLS (21) and PEAP (25).</span></span>
   1. <span data-ttu-id="ab21d-151">Wi-Fi SSID-naam juist is en overeenkomt met HEX-tekenreeks.</span><span class="sxs-lookup"><span data-stu-id="ab21d-151">Wi-Fi SSID name is right and matches with HEX string.</span></span>
   1. <span data-ttu-id="ab21d-152">Voor EAP-TLS bevat TrustedRootCA de SHA-1-hash van de server&#39;het vertrouwde basis-CA-certificaat.</span><span class="sxs-lookup"><span data-stu-id="ab21d-152">For EAP-TLS, TrustedRootCA contains the SHA-1 hash of server&#39;s trusted root CA certificate.</span></span> <span data-ttu-id="ab21d-153">Op Windows-pc'certutil.exe -dump certificaat bestandsnaam opdracht wordt een certificaat&#39;&quot; \_ \_ &quot; sha-1 hash-tekenreeks.</span><span class="sxs-lookup"><span data-stu-id="ab21d-153">On Windows PC &quot;certutil.exe -dump cert\_file\_name&quot; command will show a certificate&#39;s SHA-1 hash string.</span></span>

2. <span data-ttu-id="ab21d-154">Verzamel netwerkpakketopname op de logboeken van het toegangspunt, de controller of de AAA-server om erachter te komen waar de EAP-sessie mislukt.</span><span class="sxs-lookup"><span data-stu-id="ab21d-154">Collect network packet capture on the Access Point or Controller or AAA server logs to find out where the EAP session fails.</span></span>
   1. <span data-ttu-id="ab21d-155">Als de EAP-identiteit die wordt geleverd door HoloLens niet wordt verwacht, controleert u of de identiteit correct is ingericht via Wi-Fi-profiel of clientcertificaat.</span><span class="sxs-lookup"><span data-stu-id="ab21d-155">If the EAP identity provided by HoloLens is not expected, check whether the identity has been correctly provisioned through Wi-Fi profile or client certificate.</span></span>
   1. <span data-ttu-id="ab21d-156">Als de server het HoloLens-clientcertificaat weigert, controleert u of het vereiste clientcertificaat is ingericht op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="ab21d-156">If server rejects HoloLens client certificate, check whether the required client certificate has been provisioned on the device.</span></span>
   1. <span data-ttu-id="ab21d-157">Als HoloLens het servercertificaat weigert, controleert u of het basis-CA-certificaat voor de server is ingericht op HoloLens.</span><span class="sxs-lookup"><span data-stu-id="ab21d-157">If HoloLens rejects server certificate, check if the server root CA certificate has been provisioned on HoloLens.</span></span>
1. <span data-ttu-id="ab21d-158">Als het ondernemingsprofiel is ingericht via Wi-Fi inrichtingspakket, kunt u overwegen het inrichtingspakket toe te passen op een Windows 10 pc.</span><span class="sxs-lookup"><span data-stu-id="ab21d-158">If the enterprise profile is provisioned through Wi-Fi provisioning package, consider applying the provisioning package on a Windows 10 PC.</span></span> <span data-ttu-id="ab21d-159">Als dit ook mislukt op Windows 10 pc, volgt u de probleemoplossingsgids voor [Windows-client 802.1X-verificatie.](https://docs.microsoft.com/windows/client-management/advanced-troubleshooting-802-authentication)</span><span class="sxs-lookup"><span data-stu-id="ab21d-159">If it also fails on Windows 10 PC, follow the [Windows client 802.1X authentication troubleshooting guide](https://docs.microsoft.com/windows/client-management/advanced-troubleshooting-802-authentication).</span></span>
1. <span data-ttu-id="ab21d-160">Stel uw telemetrie in op Volledig of Optioneel (afhankelijk van uw build) en stuur ons feedback via [Feedback-hub](https://docs.microsoft.com/hololens/hololens-feedback).</span><span class="sxs-lookup"><span data-stu-id="ab21d-160">Set your telemetry to Full or Optional (depending on your build) and then send us feedback through [Feedback Hub](https://docs.microsoft.com/hololens/hololens-feedback).</span></span>

### <a name="additional-resources"></a><span data-ttu-id="ab21d-161">Aanvullende bronnen:</span><span class="sxs-lookup"><span data-stu-id="ab21d-161">Additional resources:</span></span>
- [<span data-ttu-id="ab21d-162">Wi-Fi-instellingen exporteren vanuit een Windows-apparaat</span><span class="sxs-lookup"><span data-stu-id="ab21d-162">Export Wi-Fi settings from a Windows device</span></span>](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-import-windows-8-1#export-wi-fi-settings-from-a-windows-device)

## <a name="configure-network-proxy"></a><span data-ttu-id="ab21d-163">Netwerkproxy configureren</span><span class="sxs-lookup"><span data-stu-id="ab21d-163">Configure Network Proxy</span></span>

<span data-ttu-id="ab21d-164">In deze sectie wordt de netwerkproxy voor UwP-apps (HoloLens OS) en Universeel Windows-platform (UWP) met behulp van Windows HTTP-stack besturingssysteem en app-apps bestrijkt.</span><span class="sxs-lookup"><span data-stu-id="ab21d-164">This section covers network proxy for HoloLens OS and Universal Windows Platform (UWP) Apps using Windows HTTP stack.</span></span> <span data-ttu-id="ab21d-165">Toepassingen die gebruikmaken van http-stacks die niet van Windows zijn, hebben mogelijk hun eigen proxyconfiguratie en -verwerking.</span><span class="sxs-lookup"><span data-stu-id="ab21d-165">Applications using non-Windows HTTP stack may have their own proxy configuration and handling.</span></span> 

### <a name="proxy-configurations"></a><span data-ttu-id="ab21d-166">Proxyconfiguraties</span><span class="sxs-lookup"><span data-stu-id="ab21d-166">Proxy Configurations</span></span> 

- <span data-ttu-id="ab21d-167">Pac-script (Proxy Auto-Config) : een [PAC-bestand](https://developer.mozilla.org/en-US/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_PAC_file) (opent een niet-Microsoft-site) bevat de JavaScript-functie FindProxyForURL(url, host).</span><span class="sxs-lookup"><span data-stu-id="ab21d-167">Proxy Auto-Config (PAC) script: a [PAC file](https://developer.mozilla.org/en-US/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_PAC_file) (opens a non-Microsoft site) contains a JavaScript function FindProxyForURL(url, host).</span></span> 
- <span data-ttu-id="ab21d-168">Statische proxy: in de vorm van Server:Poort.</span><span class="sxs-lookup"><span data-stu-id="ab21d-168">Static Proxy: in the form of Server:Port.</span></span>  
- <span data-ttu-id="ab21d-169">Web Proxy Auto-Discovery Protocol (WPAD): geef de URL van het proxyconfiguratiebestand op via DHCP of DNS.</span><span class="sxs-lookup"><span data-stu-id="ab21d-169">Web Proxy Auto-Discovery Protocol (WPAD): provide URL of proxy configuration file through DHCP or DNS.</span></span> 

### <a name="proxy-provisioning-methods"></a><span data-ttu-id="ab21d-170">Proxy-inrichtingsmethoden</span><span class="sxs-lookup"><span data-stu-id="ab21d-170">Proxy Provisioning Methods</span></span> 
<span data-ttu-id="ab21d-171">Er zijn drie manieren om -proxies in te stellen:</span><span class="sxs-lookup"><span data-stu-id="ab21d-171">There are three ways to provision proxies:</span></span>

 

1.  <span data-ttu-id="ab21d-172">**Gebruikersinterface van instellingen:**</span><span class="sxs-lookup"><span data-stu-id="ab21d-172">**Settings UI:**</span></span> 
    1. <span data-ttu-id="ab21d-173">Proxy per gebruiker (20H2 of eerder):</span><span class="sxs-lookup"><span data-stu-id="ab21d-173">Per-user proxy (20H2 or earlier):</span></span>
        1. <span data-ttu-id="ab21d-174">Open het Startmenu en selecteer Instellingen.</span><span class="sxs-lookup"><span data-stu-id="ab21d-174">Open the Start menu and select Settings.</span></span>
        2. <span data-ttu-id="ab21d-175">Selecteer Network & Internet en vervolgens Proxy in het menu links.</span><span class="sxs-lookup"><span data-stu-id="ab21d-175">Select Network & Internet and then Proxy on the left menu.</span></span>
        3. <span data-ttu-id="ab21d-176">Schuif omlaag naar Handmatige proxy-installatie en stel Een proxyserver gebruiken in op Aan.</span><span class="sxs-lookup"><span data-stu-id="ab21d-176">Scroll down to Manual proxy setup and toggle Use a proxy server to On.</span></span>
        4. <span data-ttu-id="ab21d-177">Voer het IP-adres van de proxyserver in.</span><span class="sxs-lookup"><span data-stu-id="ab21d-177">Enter the IP address of the proxy server.</span></span>
        5. <span data-ttu-id="ab21d-178">Voer het poortnummer in.</span><span class="sxs-lookup"><span data-stu-id="ab21d-178">Enter the port number.</span></span>
        6. <span data-ttu-id="ab21d-179">Klik op Opslaan.</span><span class="sxs-lookup"><span data-stu-id="ab21d-179">Click Save.</span></span>
      1. <span data-ttu-id="ab21d-180">Wi-Fi-proxy (21H1 of hoger):</span><span class="sxs-lookup"><span data-stu-id="ab21d-180">WiFi proxy (21H1 or higher):</span></span>
          1. <span data-ttu-id="ab21d-181">Open de Startmenu en ga naar de Wi-Fi van uw netwerk.</span><span class="sxs-lookup"><span data-stu-id="ab21d-181">Open the Start menu and go to your Wi-Fi Network’s Properties page.</span></span>
          1. <span data-ttu-id="ab21d-182">Schuif omlaag naar Proxy</span><span class="sxs-lookup"><span data-stu-id="ab21d-182">Scroll down to Proxy</span></span>
          1. <span data-ttu-id="ab21d-183">Wijzigen in Handmatige installatie</span><span class="sxs-lookup"><span data-stu-id="ab21d-183">Change to Manual Setup</span></span>
          1. <span data-ttu-id="ab21d-184">Voer het IP-adres van de proxyserver in.</span><span class="sxs-lookup"><span data-stu-id="ab21d-184">Enter the IP address of the proxy server.</span></span>
          1. <span data-ttu-id="ab21d-185">Voer het poortnummer in.</span><span class="sxs-lookup"><span data-stu-id="ab21d-185">Enter the port number.</span></span>
          1. <span data-ttu-id="ab21d-186">Klik op Toepassen.</span><span class="sxs-lookup"><span data-stu-id="ab21d-186">Click Apply.</span></span>
        
 2. <span data-ttu-id="ab21d-187">**MDM**</span><span class="sxs-lookup"><span data-stu-id="ab21d-187">**MDM**</span></span> 
     1. <span data-ttu-id="ab21d-188">Intune: gebruik deze stappen [om een](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) proxy in Intune te configureren.</span><span class="sxs-lookup"><span data-stu-id="ab21d-188">Intune - Use these [steps](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) to configure proxy in Intune.</span></span> <span data-ttu-id="ab21d-189">U moet naar de onderkant van de sectie schuiven.</span><span class="sxs-lookup"><span data-stu-id="ab21d-189">You will need to scroll to the bottom of the section.</span></span>
     1. <span data-ttu-id="ab21d-190">Andere MDM-oplossingen van derden: gebruik een [Wi-Fi-CSP.](https://docs.microsoft.com/windows/client-management/mdm/wifi-csp)</span><span class="sxs-lookup"><span data-stu-id="ab21d-190">Other 3rd party MDM solutions - Use a [WiFi CSP](https://docs.microsoft.com/windows/client-management/mdm/wifi-csp).</span></span>

3. <span data-ttu-id="ab21d-191">**PPKG**</span><span class="sxs-lookup"><span data-stu-id="ab21d-191">**PPKG**</span></span> 
    1. <span data-ttu-id="ab21d-192">Windows Configuration Designer openen</span><span class="sxs-lookup"><span data-stu-id="ab21d-192">Open Windows Configuration Designer</span></span>
    1. <span data-ttu-id="ab21d-193">Klik op Geavanceerde inrichting, voer de naam in voor het nieuwe Project en klik op Volgende.</span><span class="sxs-lookup"><span data-stu-id="ab21d-193">Click on Advanced Provisioning, enter the name for your new Project and click Next.</span></span>
    1. <span data-ttu-id="ab21d-194">Selecteer Windows Holographic (HoloLens 2) en klik op Volgende.</span><span class="sxs-lookup"><span data-stu-id="ab21d-194">Select Windows Holographic (HoloLens 2) and click Next.</span></span>
    1. <span data-ttu-id="ab21d-195">Importeer uw PPKG (optioneel) en klik op Voltooien.</span><span class="sxs-lookup"><span data-stu-id="ab21d-195">Import your PPKG (optional) and click Finish.</span></span>
    1. <span data-ttu-id="ab21d-196">Vouw Runtime settings -> Connectivity Profiles -> WLAN -> WLAN Proxy uit.</span><span class="sxs-lookup"><span data-stu-id="ab21d-196">Expand Runtime Settings -> Connectivity Profiles -> WLAN -> WLAN Proxy.</span></span>
    1. <span data-ttu-id="ab21d-197">Voer de SSID van uw Wi-Fi netwerk in en klik op Toevoegen.</span><span class="sxs-lookup"><span data-stu-id="ab21d-197">Enter the SSID of your Wi-Fi network and click Add.</span></span>
    1. <span data-ttu-id="ab21d-198">Selecteer uw Wi-Fi netwerk in het linkervenster en voer de gewenste aanpassingen in.</span><span class="sxs-lookup"><span data-stu-id="ab21d-198">Select your Wi-Fi network in the left window and enter your desired customizations.</span></span> <span data-ttu-id="ab21d-199">De ingeschakelde aanpassingen worden vet weergegeven in het menu links.</span><span class="sxs-lookup"><span data-stu-id="ab21d-199">The enabled customizations will show in bold on the left menu.</span></span>
    1. <span data-ttu-id="ab21d-200">Klik op Opslaan en afsluiten.</span><span class="sxs-lookup"><span data-stu-id="ab21d-200">Click Save and Exit.</span></span>
    1. <span data-ttu-id="ab21d-201">[Pas](https://docs.microsoft.com/hololens/hololens-provisioning#applyremove-a-provisioning-package-to-hololens-after-setup) het inrichtingspakket toe op de HoloLens.</span><span class="sxs-lookup"><span data-stu-id="ab21d-201">[Apply](https://docs.microsoft.com/hololens/hololens-provisioning#applyremove-a-provisioning-package-to-hololens-after-setup) the provisioning package to the HoloLens.</span></span>

<span data-ttu-id="ab21d-202">[CSP's](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) staan achter veel van de beheertaken en het beleid voor Windows 10, zowel in Microsoft Intune als bij niet-Microsoft MDM-serviceproviders.</span><span class="sxs-lookup"><span data-stu-id="ab21d-202">[CSPs](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) are behind many of the management tasks and policies for Windows 10, both in Microsoft Intune and in non-Microsoft MDM service providers.</span></span> <span data-ttu-id="ab21d-203">U kunt Windows [Configuration Designer ook gebruiken om](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-install-icd) een [inrichtingspakket te maken](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages) en dit toe te passen op de HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="ab21d-203">You can also use [Windows Configuration Designer](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-install-icd) to create a [provisioning package](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages) and apply it to the HoloLens 2.</span></span>
<span data-ttu-id="ab21d-204">De meest waarschijnlijke CSP's die worden toegepast op uw HoloLens 2 zijn:</span><span class="sxs-lookup"><span data-stu-id="ab21d-204">The most likely CSPs that will be applied to your HoloLens 2 are:</span></span>

- <span data-ttu-id="ab21d-205">[Wi-Fi CSP:](https://docs.microsoft.com/windows/client-management/mdm/wifi-csp)proxy per profiel Wi-Fi proxy</span><span class="sxs-lookup"><span data-stu-id="ab21d-205">[WiFi CSP](https://docs.microsoft.com/windows/client-management/mdm/wifi-csp): per-profile Wi-Fi proxy</span></span> 

[<span data-ttu-id="ab21d-206">Andere CSP's die worden ondersteund op HoloLens-apparaten</span><span class="sxs-lookup"><span data-stu-id="ab21d-206">Other CSPs supported in HoloLens devices</span></span>](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)





## <a name="vpn"></a><span data-ttu-id="ab21d-207">VPN</span><span class="sxs-lookup"><span data-stu-id="ab21d-207">VPN</span></span>
<span data-ttu-id="ab21d-208">Een VPN-verbinding kan helpen een veiligere verbinding en toegang tot het netwerk en internet van uw bedrijf te bieden.</span><span class="sxs-lookup"><span data-stu-id="ab21d-208">A VPN connection can help provide a more secure connection and access to your company's network and the Internet.</span></span> <span data-ttu-id="ab21d-209">HoloLens 2 ondersteunt de ingebouwde VPN-client en Universeel Windows-platform VPN-in plug-in (UWP).</span><span class="sxs-lookup"><span data-stu-id="ab21d-209">HoloLens 2 supports built-in VPN client and Universal Windows Platform (UWP) VPN plug-in.</span></span> 

<span data-ttu-id="ab21d-210">Ondersteunde ingebouwde VPN-protocollen:</span><span class="sxs-lookup"><span data-stu-id="ab21d-210">Supported Built-in VPN protocols:</span></span>
- <span data-ttu-id="ab21d-211">IKEv2</span><span class="sxs-lookup"><span data-stu-id="ab21d-211">IKEv2</span></span>
- <span data-ttu-id="ab21d-212">L2TP</span><span class="sxs-lookup"><span data-stu-id="ab21d-212">L2TP</span></span>
- <span data-ttu-id="ab21d-213">PPTP</span><span class="sxs-lookup"><span data-stu-id="ab21d-213">PPTP</span></span>

<span data-ttu-id="ab21d-214">Als certificaat wordt gebruikt voor verificatie voor de ingebouwde VPN-client, moet het vereiste clientcertificaat worden toegevoegd aan het certificaatopslag van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="ab21d-214">If certificate is used for authentication for built-in VPN client, the required client certificate needs to be added to user certificate store.</span></span> <span data-ttu-id="ab21d-215">Als u wilt weten of een VPN-in plug-in van derden HoloLens 2 ondersteunt, gaat u naar Store om de VPN-app te zoeken en te controleren of HoloLens wordt vermeld als een ondersteund apparaat. Op de pagina Systeemvereiste ondersteunt de app arm- of ARM64-architectuur.</span><span class="sxs-lookup"><span data-stu-id="ab21d-215">To find if a 3rd party VPN plug-in supports HoloLens 2, go to Store to locate VPN app and check if HoloLens is listed as a supported device and in the System Requirement page the app supports ARM or ARM64 architecture.</span></span> <span data-ttu-id="ab21d-216">HoloLens ondersteunt alleen Universeel Windows-platform voor VPN van derden.</span><span class="sxs-lookup"><span data-stu-id="ab21d-216">HoloLens only supports Universal Windows Platform applications for 3rd party VPN.</span></span>

 <span data-ttu-id="ab21d-217">VPN kan worden beheerd door MDM via [Settings/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn)en worden ingesteld via [Vpnv2-csp-beleid.](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp)</span><span class="sxs-lookup"><span data-stu-id="ab21d-217">VPN can be managed by MDM via [Settings/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn), and set via  [Vpnv2-csp policy](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp).</span></span>

<span data-ttu-id="ab21d-218">Meer informatie over [het configureren van VPN met](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) deze [handleidingen.](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide)</span><span class="sxs-lookup"><span data-stu-id="ab21d-218">Learn more about [how to configure VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) with [these guides](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide).</span></span>  

### <a name="vpn-via-ui"></a><span data-ttu-id="ab21d-219">VPN via gebruikersinterface</span><span class="sxs-lookup"><span data-stu-id="ab21d-219">VPN via UI</span></span>

<span data-ttu-id="ab21d-220">VPN is niet standaard ingeschakeld, maar kan handmatig worden ingeschakeld door de **app** Instellingen te openen en naar Network & **Internet -> VPN te navigeren.**</span><span class="sxs-lookup"><span data-stu-id="ab21d-220">VPN is not enabled by default but can be enabled manually by opening **Settings** app and navigating to  **Network & Internet -> VPN**.</span></span>
1. <span data-ttu-id="ab21d-221">Selecteer een VPN-provider.</span><span class="sxs-lookup"><span data-stu-id="ab21d-221">Select a VPN provider.</span></span>
1. <span data-ttu-id="ab21d-222">Maak een verbindingsnaam.</span><span class="sxs-lookup"><span data-stu-id="ab21d-222">Create a connection name.</span></span> 
1. <span data-ttu-id="ab21d-223">Voer uw servernaam of -adres in.</span><span class="sxs-lookup"><span data-stu-id="ab21d-223">Enter your server name or address.</span></span>
1. <span data-ttu-id="ab21d-224">Selecteer het VPN-type.</span><span class="sxs-lookup"><span data-stu-id="ab21d-224">Select the VPN type.</span></span>
1. <span data-ttu-id="ab21d-225">Selecteer het type aanmeldingsgegevens.</span><span class="sxs-lookup"><span data-stu-id="ab21d-225">Select type of sign-in info.</span></span> 
1. <span data-ttu-id="ab21d-226">Voeg desgewenst een gebruikersnaam en wachtwoord toe.</span><span class="sxs-lookup"><span data-stu-id="ab21d-226">Optionally add user name and password.</span></span>
1. <span data-ttu-id="ab21d-227">Pas de VPN-instellingen toe.</span><span class="sxs-lookup"><span data-stu-id="ab21d-227">Apply the VPN settings.</span></span> 

![Vpn-instellingen voor HoloLens](./images/vpn-settings-ui.jpg)

### <a name="vpn-set-via-provisioning-package"></a><span data-ttu-id="ab21d-229">VPN ingesteld via inrichtingspakket</span><span class="sxs-lookup"><span data-stu-id="ab21d-229">VPN set via Provisioning Package</span></span>

> [!TIP] 
> <span data-ttu-id="ab21d-230">In onze Windows Holographic, versie 20H2, hebben we een proxyconfiguratieprobleem opgelost voor de VPN-verbinding.</span><span class="sxs-lookup"><span data-stu-id="ab21d-230">In our Windows Holographic, version 20H2 we fixed a proxy configuration issue for VPN connection.</span></span> <span data-ttu-id="ab21d-231">Overweeg apparaten te upgraden naar deze build als u van plan bent deze stroom te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="ab21d-231">Please consider upgrading devices to this build if you intend to use this flow.</span></span>

1. <span data-ttu-id="ab21d-232">Start Windows Configuration Designer.</span><span class="sxs-lookup"><span data-stu-id="ab21d-232">Launch Windows Configuration Designer.</span></span>
1. <span data-ttu-id="ab21d-233">Klik **op HoloLens-apparaten inrichten** en selecteer vervolgens doelapparaat en **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="ab21d-233">Click **Provision HoloLens devices**, then select target device and **Next**.</span></span>
1. <span data-ttu-id="ab21d-234">Voer de pakketnaam en het pad in.</span><span class="sxs-lookup"><span data-stu-id="ab21d-234">Enter package name and path.</span></span>
1. <span data-ttu-id="ab21d-235">Klik **op Overschakelen naar geavanceerde editor.**</span><span class="sxs-lookup"><span data-stu-id="ab21d-235">Click **Switch to advanced editor**.</span></span>
1. <span data-ttu-id="ab21d-236">Open **Runtime-instellingen**  ->  **ConnectivityProfiles**  ->  **VPN**  ->  **VPNSettings**.</span><span class="sxs-lookup"><span data-stu-id="ab21d-236">Open **Runtime settings** -> **ConnectivityProfiles** -> **VPN** -> **VPNSettings**.</span></span>
1. <span data-ttu-id="ab21d-237">VPNProfileName configureren</span><span class="sxs-lookup"><span data-stu-id="ab21d-237">Configure VPNProfileName</span></span>
1. <span data-ttu-id="ab21d-238">Selecteer ProfileType: **Native** of **Third Party.**</span><span class="sxs-lookup"><span data-stu-id="ab21d-238">Select ProfileType: **Native** or **Third Party**.</span></span>
    1. <span data-ttu-id="ab21d-239">Voor Systeemeigen profiel selecteert **u SysteemeigenProtocolType** en configureert u vervolgens de server, het routeringsbeleid, het verificatietype en andere instellingen.</span><span class="sxs-lookup"><span data-stu-id="ab21d-239">For Native profile, select **NativeProtocolType**, then configure server, routing policy, authentication type and other settings.</span></span>
    1. <span data-ttu-id="ab21d-240">Configureer voor het profiel 'Externe partij' de server-URL, de familienaam van de VPN-in plug-in-app-pakket (slechts 3 vooraf gedefinieerde) en aangepaste configuraties.</span><span class="sxs-lookup"><span data-stu-id="ab21d-240">For "Third Party" profile, configure server URL, VPN plug-in App package family name (only 3 predefined) and custom configurations.</span></span>
1. <span data-ttu-id="ab21d-241">Exporteert u uw pakket.</span><span class="sxs-lookup"><span data-stu-id="ab21d-241">Export your package.</span></span>
1. <span data-ttu-id="ab21d-242">Verbind uw HoloLens en kopieer het PPKG-bestand naar het apparaat.</span><span class="sxs-lookup"><span data-stu-id="ab21d-242">Connect your HoloLens and copy the .ppkg file to the device.</span></span> 
1. <span data-ttu-id="ab21d-243">Pas op HoloLens de VPN .ppkg toe door de Startmenu te openen en Instellingen Accounttoegang tot werk of school te selecteren Inrichtingspakket toevoegen of verwijderen -> Selecteer uw  ->    ->    ->   VPN-pakket.</span><span class="sxs-lookup"><span data-stu-id="ab21d-243">On HoloLens, apply the VPN .ppkg by opening the Start menu and selecting **Settings** -> **Account** -> **Access work or school** -> **Add or remove provisioning package** -> Select your VPN package.</span></span>


### <a name="setting-up-vpn-via-intune"></a><span data-ttu-id="ab21d-244">VPN instellen via Intune</span><span class="sxs-lookup"><span data-stu-id="ab21d-244">Setting up VPN via Intune</span></span>
<span data-ttu-id="ab21d-245">Volg de Intune-documenten om aan de slag te gaan.</span><span class="sxs-lookup"><span data-stu-id="ab21d-245">Just follow the Intune documents to get started.</span></span> <span data-ttu-id="ab21d-246">Wanneer u deze stappen volgt, moet u rekening houden met de ingebouwde VPN-protocollen die door HoloLens-apparaten worden ondersteund.</span><span class="sxs-lookup"><span data-stu-id="ab21d-246">When following these steps please keep in mind the built-in VPN protocols that HoloLens devices support.</span></span> 

<span data-ttu-id="ab21d-247">[Maak VPN-profielen om verbinding te maken met VPN-servers in Intune.](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-configure)</span><span class="sxs-lookup"><span data-stu-id="ab21d-247">[Create VPN profiles to connect to VPN servers in Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-configure).</span></span>

<span data-ttu-id="ab21d-248">[Windows 10 en Windows Holographic-apparaatinstellingen om VPN-verbindingen toe te voegen met behulp van Intune.](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-windows-10)</span><span class="sxs-lookup"><span data-stu-id="ab21d-248">[Windows 10 and Windows Holographic device settings to add VPN connections using Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-windows-10).</span></span>

<span data-ttu-id="ab21d-249">Wanneer u klaar bent, moet u [het profiel toewijzen.](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign)</span><span class="sxs-lookup"><span data-stu-id="ab21d-249">When done please remember to [assign the profile](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign).</span></span>

### <a name="vpn-via-3rd-party-mdm-solutions"></a><span data-ttu-id="ab21d-250">VPN via MDM-oplossingen van derden</span><span class="sxs-lookup"><span data-stu-id="ab21d-250">VPN via 3rd party MDM solutions</span></span>
<span data-ttu-id="ab21d-251">Voorbeeld van een VPN-verbinding van derden:</span><span class="sxs-lookup"><span data-stu-id="ab21d-251">3rd party VPN connection example:</span></span>
```xml
<!-- Configure VPN Server Name or Address (PhoneNumber=) [Comma Separated]-->
      <Add>
        <CmdID>10001</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/PluginProfile/ServerUrlList</LocURI>
          </Target>
          <Data>selfhost.corp.contoso.com</Data>
        </Item>
      </Add>

      <!-- Configure VPN Plugin AppX Package ID (ThirdPartyProfileInfo=) -->
      <Add>
        <CmdID>10002</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/PluginProfile/PluginPackageFamilyName</LocURI>
          </Target>
          <Data>TestVpnPluginApp-SL_8wekyb3d8bbwe</Data>
        </Item>
      </Add>

      <!-- Configure Microsoft's Custom XML (ThirdPartyProfileInfo=) -->
      <Add>
        <CmdID>10003</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/PluginProfile/CustomConfiguration</LocURI>
          </Target>          <Data><pluginschema><ipAddress>auto</ipAddress><port>443</port><networksettings><routes><includev4><route><address>172.10.10.0</address><prefix>24</prefix></route></includev4></routes><namespaces><namespace><space>.vpnbackend.com</space><dnsservers><server>172.10.10.11</server></dnsservers></namespace></namespaces></networksettings></pluginschema></Data>
        </Item>
      </Add>
```

<span data-ttu-id="ab21d-252">Native IKEv2 VPN-voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="ab21d-252">Native IKEv2 VPN example:</span></span>
```xml
      <Add>
        <CmdID>10001</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/Servers</LocURI>
          </Target>
          <Data>Selfhost.corp.contoso.com</Data>
        </Item>
      </Add>

      <Add>
        <CmdID>10002</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/RoutingPolicyType</LocURI>
          </Target>
          <Data>ForceTunnel</Data>
        </Item>
      </Add>

      <!-- Configure VPN Protocol Type (L2tp, Pptp, Ikev2) -->
      <Add>
        <CmdID>10003</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/NativeProtocolType</LocURI>
          </Target>
          <Data>Ikev2</Data>
        </Item>
      </Add>

      <!-- Configure VPN User Method (Mschapv2, Eap) -->
      <Add>
        <CmdID>10004</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/Authentication/UserMethod</LocURI>
          </Target>
          <Data>Eap</Data>
        </Item>
      </Add>

      <Add>
        <CmdID>10004</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/Authentication/Eap/Configuration</LocURI>
          </Target>
          <Data>EAP_configuration_xml_content</Data>
        </Item>
      </Add>
```
## <a name="disabling-wi-fi-on-hololens-1st-gen"></a><span data-ttu-id="ab21d-253">Wi-Fi uitschakelen op HoloLens (1e generatie)</span><span class="sxs-lookup"><span data-stu-id="ab21d-253">Disabling Wi-Fi on HoloLens (1st gen)</span></span>

### <a name="using-the-settings-app-on-hololens"></a><span data-ttu-id="ab21d-254">De app Instellingen op HoloLens gebruiken</span><span class="sxs-lookup"><span data-stu-id="ab21d-254">Using the Settings app on HoloLens</span></span>

1. <span data-ttu-id="ab21d-255">Open het **menu** Start.</span><span class="sxs-lookup"><span data-stu-id="ab21d-255">Open the **Start** menu.</span></span>
1. <span data-ttu-id="ab21d-256">Selecteer de app **Instellingen** op **Start** of in **de lijst Alle apps** rechts van het menu Start. </span><span class="sxs-lookup"><span data-stu-id="ab21d-256">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="ab21d-257">De **app** Instellingen wordt automatisch voor u geplaatst.</span><span class="sxs-lookup"><span data-stu-id="ab21d-257">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="ab21d-258">Selecteer **Netwerk & Internet.**</span><span class="sxs-lookup"><span data-stu-id="ab21d-258">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="ab21d-259">Selecteer de Wi-Fi schuifregelaar om deze naar de **uit-positie te** verplaatsen.</span><span class="sxs-lookup"><span data-stu-id="ab21d-259">Select the Wi-Fi slider switch to move it to the **Off** position.</span></span> <span data-ttu-id="ab21d-260">Hiermee worden de RF-onderdelen van de Wi-Fi uitgeschakeld en worden alle Wi-Fi op HoloLens uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="ab21d-260">This will turn off the RF components of the Wi-Fi radio and disable all Wi-Fi functionality on HoloLens.</span></span>

    > [!WARNING]
    > <span data-ttu-id="ab21d-261">Wanneer het Wi-Fi is uitgeschakeld, kan HoloLens uw ruimten niet automatisch [laden.](hololens-spaces.md)</span><span class="sxs-lookup"><span data-stu-id="ab21d-261">When the Wi-Fi radio is disabled, HoloLens will not be able to automatically load your [spaces](hololens-spaces.md).</span></span>

1. <span data-ttu-id="ab21d-262">Verplaats de schuifregelaar naar de **positie Aan om** het Wi-Fi in te schakelen en de Wi-Fi op Microsoft HoloLens.</span><span class="sxs-lookup"><span data-stu-id="ab21d-262">Move the slider switch to the **On** position to turn on the Wi-Fi radio and restore Wi-Fi functionality on Microsoft HoloLens.</span></span> <span data-ttu-id="ab21d-263">De geselecteerde Wi-Fi radiotoestand (**Aan** of **Uit)** blijft behouden tijdens het opnieuw opstarten.</span><span class="sxs-lookup"><span data-stu-id="ab21d-263">The selected Wi-Fi radio state (**On** or **Off**) will persist across reboots.</span></span>

## <a name="identifying-the-ip-address-of-your-hololens-on-the-wi-fi-network"></a><span data-ttu-id="ab21d-264">Het IP-adres van uw HoloLens in het Wi-Fi identificeren</span><span class="sxs-lookup"><span data-stu-id="ab21d-264">Identifying the IP Address of your HoloLens on the Wi-Fi network</span></span>

### <a name="by-using-the-settings-app"></a><span data-ttu-id="ab21d-265">Met behulp van de app Instellingen</span><span class="sxs-lookup"><span data-stu-id="ab21d-265">By using the Settings app</span></span>

1. <span data-ttu-id="ab21d-266">Open het **menu** Start.</span><span class="sxs-lookup"><span data-stu-id="ab21d-266">Open the **Start** menu.</span></span>
1. <span data-ttu-id="ab21d-267">Selecteer de app **Instellingen** op **Start** of in **de lijst Alle apps** rechts van het menu Start. </span><span class="sxs-lookup"><span data-stu-id="ab21d-267">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="ab21d-268">De **app** Instellingen wordt automatisch voor u geplaatst.</span><span class="sxs-lookup"><span data-stu-id="ab21d-268">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="ab21d-269">Selecteer **Netwerk & Internet.**</span><span class="sxs-lookup"><span data-stu-id="ab21d-269">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="ab21d-270">Schuif omlaag naar onder de lijst met beschikbare Wi-Fi netwerken en selecteer **Hardware-eigenschappen.**</span><span class="sxs-lookup"><span data-stu-id="ab21d-270">Scroll down to beneath the list of available Wi-Fi networks and select **Hardware properties**.</span></span>

    ![Hardware-eigenschappen in Wi-Fi instellingen](./images/wifi-hololens-hwdetails.jpg)

   <span data-ttu-id="ab21d-272">Het IP-adres wordt weergegeven naast **IPv4-adres**.</span><span class="sxs-lookup"><span data-stu-id="ab21d-272">The IP address appears next to **IPv4 address**.</span></span>

### <a name="by-using-voice-commands"></a><span data-ttu-id="ab21d-273">Met behulp van spraakopdrachten</span><span class="sxs-lookup"><span data-stu-id="ab21d-273">By using voice commands</span></span>

<span data-ttu-id="ab21d-274">Afhankelijk van de build van uw apparaten kunt u ingebouwde spraakopdrachten of Cortana gebruiken om uw IP-adres weer te geven.</span><span class="sxs-lookup"><span data-stu-id="ab21d-274">Depending on your devices build you can either use built in voice commands or Cortana to display your IP address.</span></span> <span data-ttu-id="ab21d-275">Op builds na [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) spreekt u "Wat is mijn IP-adres?"</span><span class="sxs-lookup"><span data-stu-id="ab21d-275">On builds after [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) speak "What's my IP address?"</span></span> <span data-ttu-id="ab21d-276">en worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="ab21d-276">and it will be displayed.</span></span> <span data-ttu-id="ab21d-277">Voor eerdere builds of HoloLens (eerste generatie) zegt u "Hey Cortana, Wat is mijn IP-adres?"</span><span class="sxs-lookup"><span data-stu-id="ab21d-277">For earlier builds or HoloLens (1st gen) say "Hey Cortana, What's my IP address?"</span></span> <span data-ttu-id="ab21d-278">en Cortana worden weergegeven en uw IP-adres gelezen.</span><span class="sxs-lookup"><span data-stu-id="ab21d-278">and Cortana will display and read out your IP address.</span></span>

### <a name="by-using-windows-device-portal"></a><span data-ttu-id="ab21d-279">Met behulp van Windows Apparaatportal</span><span class="sxs-lookup"><span data-stu-id="ab21d-279">By using Windows Device Portal</span></span>

1. <span data-ttu-id="ab21d-280">Open de apparaatportal in een webbrowser op [uw pc.](/windows/mixed-reality/using-the-windows-device-portal.md#networking)</span><span class="sxs-lookup"><span data-stu-id="ab21d-280">In a web browser on your PC, open the [device portal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span></span>
1. <span data-ttu-id="ab21d-281">Navigeer naar **de sectie** Netwerken.</span><span class="sxs-lookup"><span data-stu-id="ab21d-281">Navigate to the **Networking** section.</span></span>  
   <span data-ttu-id="ab21d-282">In deze sectie worden uw IP-adres en andere netwerkgegevens weergegeven.</span><span class="sxs-lookup"><span data-stu-id="ab21d-282">This section displays your IP address and other network information.</span></span> <span data-ttu-id="ab21d-283">Met deze methode kunt u het IP-adres kopiëren en plakken op uw ontwikkel-pc.</span><span class="sxs-lookup"><span data-stu-id="ab21d-283">By using this method, you can copy and paste of the IP address on your development PC.</span></span>

## <a name="change-ip-address-to-static-address"></a><span data-ttu-id="ab21d-284">IP-adres wijzigen in statisch adres</span><span class="sxs-lookup"><span data-stu-id="ab21d-284">Change IP Address to static address</span></span>
### <a name="by-using-settings"></a><span data-ttu-id="ab21d-285">Met behulp van Instellingen</span><span class="sxs-lookup"><span data-stu-id="ab21d-285">By using Settings</span></span>
 
1. <span data-ttu-id="ab21d-286">Open het **menu** Start.</span><span class="sxs-lookup"><span data-stu-id="ab21d-286">Open the **Start** menu.</span></span>
1. <span data-ttu-id="ab21d-287">Selecteer de app **Instellingen** op **Start** of in **de lijst Alle apps** rechts van het menu Start. </span><span class="sxs-lookup"><span data-stu-id="ab21d-287">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="ab21d-288">De **app** Instellingen wordt automatisch voor u geplaatst.</span><span class="sxs-lookup"><span data-stu-id="ab21d-288">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="ab21d-289">Selecteer **Netwerk & Internet.**</span><span class="sxs-lookup"><span data-stu-id="ab21d-289">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="ab21d-290">Schuif omlaag naar onder de lijst met beschikbare Wi-Fi netwerken en selecteer **Hardware-eigenschappen.**</span><span class="sxs-lookup"><span data-stu-id="ab21d-290">Scroll down to beneath the list of available Wi-Fi networks and select **Hardware properties**.</span></span>
1. <span data-ttu-id="ab21d-291">Wijzig in **het venster IP-instellingen** bewerken het eerste veld in **Handmatig.**</span><span class="sxs-lookup"><span data-stu-id="ab21d-291">In the **Edit IP settings** window, change the first field to **Manual**.</span></span>
1. <span data-ttu-id="ab21d-292">Voer de gewenste IP-configuratie in de overige velden in en klik vervolgens op **Opslaan.**</span><span class="sxs-lookup"><span data-stu-id="ab21d-292">Input the desired IP configuration in the remaining fields and then click **Save**.</span></span>

### <a name="by-using-windows-device-portal"></a><span data-ttu-id="ab21d-293">Met behulp van Windows Apparaatportal</span><span class="sxs-lookup"><span data-stu-id="ab21d-293">By using Windows Device Portal</span></span>

1. <span data-ttu-id="ab21d-294">Open de apparaatportal in een webbrowser op [uw pc.](/windows/mixed-reality/using-the-windows-device-portal.md#networking)</span><span class="sxs-lookup"><span data-stu-id="ab21d-294">In a web browser on your PC, open the [device portal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span></span>
1. <span data-ttu-id="ab21d-295">Navigeer naar **de sectie** Netwerken.</span><span class="sxs-lookup"><span data-stu-id="ab21d-295">Navigate to the **Networking** section.</span></span>
1. <span data-ttu-id="ab21d-296">Selecteer de **knop IPv4-configuratie.**</span><span class="sxs-lookup"><span data-stu-id="ab21d-296">Select the **IPv4 Configuration** button.</span></span>
1. <span data-ttu-id="ab21d-297">Selecteer **Het volgende IP-adres gebruiken en** voer de gewenste TCP/IP-configuratie in.</span><span class="sxs-lookup"><span data-stu-id="ab21d-297">Select **Use the following IP address** and input the desired TCP/IP configuration.</span></span>
1. <span data-ttu-id="ab21d-298">Selecteer **De volgende DNS-serveradressen gebruiken** en voer zo nodig de voorkeurs- en alternatieve DNS-serveradressen in.</span><span class="sxs-lookup"><span data-stu-id="ab21d-298">Select **Use the following DNS server addresses** and enter the Preferred and Alternate DNS server addresses, if needed.</span></span>
1. <span data-ttu-id="ab21d-299">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="ab21d-299">Click **Save**.</span></span> 