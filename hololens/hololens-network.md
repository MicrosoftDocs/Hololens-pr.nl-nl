---
title: HoloLens verbinden met een netwerk
description: Meer informatie over het instellen en verbinden met internet met HoloLens en het identificeren van het IP-adres van het apparaat.
ms.assetid: 0895606e-96c0-491e-8b1c-52e56b00365d
author: mattzmsft
ms.author: mazeller
keywords: HoloLens, Wi-Fi, draadloos, internet, ip, IP-adres
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
ms.openlocfilehash: 8564fb0483226a16722ada345de325577cda77d6
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923598"
---
# <a name="connect-hololens-to-a-network"></a><span data-ttu-id="b78c2-104">HoloLens verbinden met een netwerk</span><span class="sxs-lookup"><span data-stu-id="b78c2-104">Connect HoloLens to a network</span></span>

<span data-ttu-id="b78c2-105">Als u de meeste dingen op uw HoloLens wilt doen, moet u zijn verbonden met een netwerk.</span><span class="sxs-lookup"><span data-stu-id="b78c2-105">To do most things on your HoloLens, you have to be connected to a network.</span></span> <span data-ttu-id="b78c2-106">HoloLens bevat een 2x2 Wi-Fi-radio die geschikt is voor 802.11ac en is vergelijkbaar met het verbinden van een Windows 10 Desktop- of Mobile-apparaat met een Wi-Fi-netwerk.</span><span class="sxs-lookup"><span data-stu-id="b78c2-106">HoloLens contains a 802.11ac-capable, 2x2 Wi-Fi radio and connecting it to a network is similar to connecting a Windows 10 Desktop or Mobile device to a Wi-Fi network.</span></span> <span data-ttu-id="b78c2-107">Deze handleiding helpt u bij het volgende:</span><span class="sxs-lookup"><span data-stu-id="b78c2-107">This guide will help you:</span></span>

- <span data-ttu-id="b78c2-108">Verbinding maken met een netwerk via Wi-Fi of alleen HoloLens 2, Wi-Fi Direct of Ethernet via USB-C</span><span class="sxs-lookup"><span data-stu-id="b78c2-108">Connect to a network using Wi-Fi, or for HoloLens 2 only, Wi-Fi Direct or Ethernet over USB-C</span></span>
- <span data-ttu-id="b78c2-109">Uitschakelen en opnieuw inschakelen Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="b78c2-109">Disable and re-enable Wi-Fi</span></span>

<span data-ttu-id="b78c2-110">Lees meer over het [offline gebruik van HoloLens.](hololens-offline.md)</span><span class="sxs-lookup"><span data-stu-id="b78c2-110">Read more about [using HoloLens offline](hololens-offline.md).</span></span>

## <a name="connecting-for-the-first-time"></a><span data-ttu-id="b78c2-111">Voor de eerste keer verbinding maken</span><span class="sxs-lookup"><span data-stu-id="b78c2-111">Connecting for the first time</span></span>

<span data-ttu-id="b78c2-112">De eerste keer dat u uw HoloLens gebruikt, wordt u begeleid bij het maken van verbinding met Wi-Fi netwerk.</span><span class="sxs-lookup"><span data-stu-id="b78c2-112">The first time you use your HoloLens, you'll be guided through connecting to a Wi-Fi network.</span></span> <span data-ttu-id="b78c2-113">Als u tijdens de installatie problemen hebt met het maken van verbinding met Wi-Fi, moet u ervoor zorgen dat uw netwerk een open, met wachtwoorden beveiligd netwerk of een captive portal-netwerk is.</span><span class="sxs-lookup"><span data-stu-id="b78c2-113">If you have trouble connecting to Wi-Fi during setup, make sure that your network is either an open, password-protected network or a captive portal network.</span></span> <span data-ttu-id="b78c2-114">Controleer ook of u voor het netwerk geen certificaat hoeft te gebruiken om verbinding te maken.</span><span class="sxs-lookup"><span data-stu-id="b78c2-114">Also, confirm that the network doesn't require you to use a certificate to connect.</span></span> <span data-ttu-id="b78c2-115">Na de installatie kunt u verbinding maken met andere typen Wi-Fi netwerken.</span><span class="sxs-lookup"><span data-stu-id="b78c2-115">After setup, you can connect to other types of Wi-Fi networks.</span></span>

<span data-ttu-id="b78c2-116">Op HoloLens 2 apparaten kan een gebruiker ook een [USB-C-naar-Ethernet-adapter](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) gebruiken om rechtstreeks verbinding te maken met Wi-Fi om te helpen bij het instellen van het apparaat.</span><span class="sxs-lookup"><span data-stu-id="b78c2-116">On HoloLens 2 devices, a user may also [use a USB-C to Ethernet adapter](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) to connect directly to Wi-Fi to help assist in setting up the device.</span></span> <span data-ttu-id="b78c2-117">Zodra het apparaat is ingesteld, kan een gebruiker de adapter blijven gebruiken of het apparaat loskoppelen van de adapter en verbinding maken [met Wi-Fi](hololens-network.md#connecting-to-wi-fi-after-setup)na het instellen.</span><span class="sxs-lookup"><span data-stu-id="b78c2-117">Once the device has been set up a user may continue to use the adapter or they may disconnect the device from the adapter and [connect to wi-fi after set up](hololens-network.md#connecting-to-wi-fi-after-setup).</span></span> 

## <a name="connecting-to-wi-fi-after-setup"></a><span data-ttu-id="b78c2-118">Verbinding maken met Wi-Fi na de installatie</span><span class="sxs-lookup"><span data-stu-id="b78c2-118">Connecting to Wi-Fi after setup</span></span>

1. <span data-ttu-id="b78c2-119">Maak de beweging **Start vooraf en** selecteer **Instellingen.**</span><span class="sxs-lookup"><span data-stu-id="b78c2-119">Preform the **Start gesture** and select **Settings**.</span></span> <span data-ttu-id="b78c2-120">De app Instellingen wordt automatisch voor u geplaatst.</span><span class="sxs-lookup"><span data-stu-id="b78c2-120">The Settings app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="b78c2-121">Selecteer **Network & Internet**  >  **Wi-Fi**.</span><span class="sxs-lookup"><span data-stu-id="b78c2-121">Select **Network & Internet** > **Wi-Fi**.</span></span> <span data-ttu-id="b78c2-122">Controleer of Wi-Fi is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="b78c2-122">Make sure Wi-Fi is turned on.</span></span> <span data-ttu-id="b78c2-123">Als u uw netwerk niet ziet, schuift u omlaag in de lijst.</span><span class="sxs-lookup"><span data-stu-id="b78c2-123">If you don't see your network, scroll down the list.</span></span>
1. <span data-ttu-id="b78c2-124">Selecteer een netwerk en selecteer vervolgens **Verbinding maken.**</span><span class="sxs-lookup"><span data-stu-id="b78c2-124">Select a network, then select **Connect**.</span></span>
1. <span data-ttu-id="b78c2-125">Als u wordt gevraagd om een netwerkwachtwoord typt u dit en selecteert u **volgende.**</span><span class="sxs-lookup"><span data-stu-id="b78c2-125">If you are prompted for a network password type it and then select **Next**.</span></span>

![Instellingen voor HoloLens-Wi-Fi](./images/hololens-2-wifi-settings.jpg)

<span data-ttu-id="b78c2-127">Als u wilt controleren of u bent verbonden met Wi-Fi netwerk, controleert u de status Wi-Fi in het menu **Start:**</span><span class="sxs-lookup"><span data-stu-id="b78c2-127">To confirm you are connected to a Wi-Fi network, check the Wi-Fi status in the **Start** menu:</span></span>

1. <span data-ttu-id="b78c2-128">Open het **menu** Start.</span><span class="sxs-lookup"><span data-stu-id="b78c2-128">Open the **Start** menu.</span></span>
1. <span data-ttu-id="b78c2-129">Kijk linksboven in het menu **Start** naar de Wi-Fi status.</span><span class="sxs-lookup"><span data-stu-id="b78c2-129">Look at the top left of the **Start** menu for Wi-Fi status.</span></span> <span data-ttu-id="b78c2-130">De status van Wi-Fi en de SSID van het verbonden netwerk wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="b78c2-130">The state of Wi-Fi and the SSID of the connected network will be shown.</span></span>

> [!TIP]
> <span data-ttu-id="b78c2-131">Als Wi-Fi niet beschikbaar is, kunt u ook verbinding [maken met mobiele en 5G-netwerken.](hololens-cellular.md)</span><span class="sxs-lookup"><span data-stu-id="b78c2-131">If Wi-Fi is not available, you can also [connect to Cellular and 5G networks](hololens-cellular.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b78c2-132">Gebruikers kunnen het Wi-Fi-roaminggedrag van de HoloLens 2 niet afstemmen. De enige manier om de Wi-Fi-lijst te **vernieuwen, is door** de Wi-Fi uit en Aan te zetten.</span><span class="sxs-lookup"><span data-stu-id="b78c2-132">By design, users cannot fine tune the Wi-Fi roaming behavior of the HoloLens 2 - **the only way to refresh the Wi-Fi list is to toggle the Wi-Fi Off and On**.</span></span> <span data-ttu-id="b78c2-133">Dit voorkomt veel problemen, zoals wanneer een apparaat 'vastloopt' aan een AP wanneer het buiten het bereik valt.</span><span class="sxs-lookup"><span data-stu-id="b78c2-133">This prevents many issues, like where a device can remain "stuck" to an AP once it is out of range.</span></span>

## <a name="connect-hololens-to-enterprise-wi-fi-network"></a><span data-ttu-id="b78c2-134">HoloLens verbinden met Enterprise Wi-Fi Network</span><span class="sxs-lookup"><span data-stu-id="b78c2-134">Connect HoloLens to Enterprise Wi-Fi Network</span></span>

<span data-ttu-id="b78c2-135">Enterprise Wi-Fi-profielen maken gebruik van Extensible Authentication Protocol (EAP) om verbinding Wi-Fi verifiëren.</span><span class="sxs-lookup"><span data-stu-id="b78c2-135">Enterprise Wi-Fi profiles use Extensible Authentication Protocol (EAP) to authenticate Wi-Fi connections.</span></span> <span data-ttu-id="b78c2-136">Het HoloLens Enterprise Wi-Fi-profiel kan worden geconfigureerd via MDM of een inrichtingspakket dat is gemaakt door [Windows Configuration Designer.](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages)</span><span class="sxs-lookup"><span data-stu-id="b78c2-136">HoloLens Enterprise Wi-Fi profile can be configured through MDM or provisioning package created by [Windows Configuration Designer](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages).</span></span>

<span data-ttu-id="b78c2-137">Raadpleeg Microsoft Intune [Intune](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) voor configuratie-instructies voor meer informatie over het beheerde apparaat.</span><span class="sxs-lookup"><span data-stu-id="b78c2-137">For Microsoft Intune managed device, refer to [Intune](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) for configuration instructions.</span></span>

<span data-ttu-id="b78c2-138">Als u een Wi-Fi-inrichtingspakket in WCD wilt maken, is een vooraf geconfigureerd Wi-Fi-.xml vereist.</span><span class="sxs-lookup"><span data-stu-id="b78c2-138">To create a Wi-Fi provisioning package in WCD, a pre-configured Wi-Fi profile .xml file is required.</span></span> <span data-ttu-id="b78c2-139">Hier is een voorbeeld van Wi-Fi voor WPA2-Enterprise met EAP-TLS-verificatie:</span><span class="sxs-lookup"><span data-stu-id="b78c2-139">Here is a sample Wi-Fi profile for WPA2-Enterprise with EAP-TLS authentication:</span></span>

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


<span data-ttu-id="b78c2-140">Het CA-basiscertificaat van de server en het clientcertificaat moeten mogelijk worden ingericht op het apparaat, afhankelijk van het EAP-type.</span><span class="sxs-lookup"><span data-stu-id="b78c2-140">Server root CA certificate and client certificate may need to be provisioned on the device depending on the EAP type.</span></span>

<span data-ttu-id="b78c2-141">Aanvullende bronnen:</span><span class="sxs-lookup"><span data-stu-id="b78c2-141">Additional resources:</span></span>

- <span data-ttu-id="b78c2-142">WLANv1Profile Schema: [[MS-GPWL]: Draadloos LAN-profiel v1 Schema | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)</span><span class="sxs-lookup"><span data-stu-id="b78c2-142">WLANv1Profile Schema: [[MS-GPWL]: Wireless LAN Profile v1 Schema | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)</span></span>
- <span data-ttu-id="b78c2-143">EAP-TLS-schema: [[MS-GPWL]: Microsoft EAP TLS-schema | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)</span><span class="sxs-lookup"><span data-stu-id="b78c2-143">EAP-TLS Schema: [[MS-GPWL]: Microsoft EAP TLS Schema | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)</span></span>

<span data-ttu-id="b78c2-144">Raadpleeg onze [pagina Voor probleemoplossing](hololens2-enterprise-troubleshooting.md#) als u problemen hebt met het maken van verbinding met uw Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="b78c2-144">Check our [Troubleshooting](hololens2-enterprise-troubleshooting.md#) page if you are having problems connecting to your Wi-Fi.</span></span>

## <a name="configure-network-proxy"></a><span data-ttu-id="b78c2-145">Netwerkproxy configureren</span><span class="sxs-lookup"><span data-stu-id="b78c2-145">Configure Network Proxy</span></span>

<span data-ttu-id="b78c2-146">In deze sectie wordt de netwerkproxy voor UwP-apps (HoloLens OS) en Universeel Windows-platform (UWP) met behulp van Windows HTTP-stack besturingssystemen.</span><span class="sxs-lookup"><span data-stu-id="b78c2-146">This section covers network proxy for HoloLens OS and Universal Windows Platform (UWP) Apps using Windows HTTP stack.</span></span> <span data-ttu-id="b78c2-147">Toepassingen die geen Windows HTTP-stack gebruiken, hebben mogelijk hun eigen proxyconfiguratie en -verwerking.</span><span class="sxs-lookup"><span data-stu-id="b78c2-147">Applications using non-Windows HTTP stack may have their own proxy configuration and handling.</span></span> 

### <a name="proxy-configurations"></a><span data-ttu-id="b78c2-148">Proxyconfiguraties</span><span class="sxs-lookup"><span data-stu-id="b78c2-148">Proxy Configurations</span></span> 

- <span data-ttu-id="b78c2-149">Pac-script (Proxy Auto-Config) : een [PAC-bestand](https://developer.mozilla.org/en-US/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_PAC_file) (opent een niet-Microsoft-site) bevat de JavaScript-functie FindProxyForURL(url, host).</span><span class="sxs-lookup"><span data-stu-id="b78c2-149">Proxy Auto-Config (PAC) script: a [PAC file](https://developer.mozilla.org/en-US/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_PAC_file) (opens a non-Microsoft site) contains a JavaScript function FindProxyForURL(url, host).</span></span> 
- <span data-ttu-id="b78c2-150">Statische proxy: in de vorm van Server:Poort.</span><span class="sxs-lookup"><span data-stu-id="b78c2-150">Static Proxy: in the form of Server:Port.</span></span>  
- <span data-ttu-id="b78c2-151">Web Proxy Auto-Discovery Protocol (WPAD): geef de URL van het proxyconfiguratiebestand op via DHCP of DNS.</span><span class="sxs-lookup"><span data-stu-id="b78c2-151">Web Proxy Auto-Discovery Protocol (WPAD): provide URL of proxy configuration file through DHCP or DNS.</span></span> 

### <a name="proxy-provisioning-methods"></a><span data-ttu-id="b78c2-152">Proxy-inrichtingsmethoden</span><span class="sxs-lookup"><span data-stu-id="b78c2-152">Proxy Provisioning Methods</span></span> 
<span data-ttu-id="b78c2-153">Er zijn drie manieren om proxies in terichten:</span><span class="sxs-lookup"><span data-stu-id="b78c2-153">There are three ways to provision proxies:</span></span>

 

1.  <span data-ttu-id="b78c2-154">**Gebruikersinterface van instellingen:**</span><span class="sxs-lookup"><span data-stu-id="b78c2-154">**Settings UI:**</span></span> 
    1. <span data-ttu-id="b78c2-155">Proxy per gebruiker (20H2 of eerder):</span><span class="sxs-lookup"><span data-stu-id="b78c2-155">Per-user proxy (20H2 or earlier):</span></span>
        1. <span data-ttu-id="b78c2-156">Open het Startmenu selecteer Instellingen.</span><span class="sxs-lookup"><span data-stu-id="b78c2-156">Open the Start menu and select Settings.</span></span>
        2. <span data-ttu-id="b78c2-157">Selecteer Network & Internet en vervolgens Proxy in het menu links.</span><span class="sxs-lookup"><span data-stu-id="b78c2-157">Select Network & Internet and then Proxy on the left menu.</span></span>
        3. <span data-ttu-id="b78c2-158">Schuif omlaag naar Handmatige proxy-installatie en stel Een proxyserver gebruiken in op Aan.</span><span class="sxs-lookup"><span data-stu-id="b78c2-158">Scroll down to Manual proxy setup and toggle Use a proxy server to On.</span></span>
        4. <span data-ttu-id="b78c2-159">Voer het IP-adres van de proxyserver in.</span><span class="sxs-lookup"><span data-stu-id="b78c2-159">Enter the IP address of the proxy server.</span></span>
        5. <span data-ttu-id="b78c2-160">Voer het poortnummer in.</span><span class="sxs-lookup"><span data-stu-id="b78c2-160">Enter the port number.</span></span>
        6. <span data-ttu-id="b78c2-161">Klik op Opslaan.</span><span class="sxs-lookup"><span data-stu-id="b78c2-161">Click Save.</span></span>
      1. <span data-ttu-id="b78c2-162">Wi-Fi-proxy (21H1 of hoger):</span><span class="sxs-lookup"><span data-stu-id="b78c2-162">WiFi proxy (21H1 or higher):</span></span>
          1. <span data-ttu-id="b78c2-163">Open de Startmenu en ga naar Wi-Fi pagina Eigenschappen van uw netwerk.</span><span class="sxs-lookup"><span data-stu-id="b78c2-163">Open the Start menu and go to your Wi-Fi Network’s Properties page.</span></span>
          1. <span data-ttu-id="b78c2-164">Schuif omlaag naar Proxy</span><span class="sxs-lookup"><span data-stu-id="b78c2-164">Scroll down to Proxy</span></span>
          1. <span data-ttu-id="b78c2-165">Wijzigen in Handmatige installatie</span><span class="sxs-lookup"><span data-stu-id="b78c2-165">Change to Manual Setup</span></span>
          1. <span data-ttu-id="b78c2-166">Voer het IP-adres van de proxyserver in.</span><span class="sxs-lookup"><span data-stu-id="b78c2-166">Enter the IP address of the proxy server.</span></span>
          1. <span data-ttu-id="b78c2-167">Voer het poortnummer in.</span><span class="sxs-lookup"><span data-stu-id="b78c2-167">Enter the port number.</span></span>
          1. <span data-ttu-id="b78c2-168">Klik op Toepassen.</span><span class="sxs-lookup"><span data-stu-id="b78c2-168">Click Apply.</span></span>
        
 2. <span data-ttu-id="b78c2-169">**MDM**</span><span class="sxs-lookup"><span data-stu-id="b78c2-169">**MDM**</span></span> 
     1. <span data-ttu-id="b78c2-170">Intune: gebruik deze stappen [om een](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) proxy in Intune te configureren.</span><span class="sxs-lookup"><span data-stu-id="b78c2-170">Intune - Use these [steps](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) to configure proxy in Intune.</span></span> <span data-ttu-id="b78c2-171">U moet naar de onderkant van de sectie schuiven.</span><span class="sxs-lookup"><span data-stu-id="b78c2-171">You will need to scroll to the bottom of the section.</span></span>
     1. <span data-ttu-id="b78c2-172">Andere MDM-oplossingen van derden: gebruik een [WiFi CSP.](https://docs.microsoft.com/windows/client-management/mdm/wifi-csp)</span><span class="sxs-lookup"><span data-stu-id="b78c2-172">Other 3rd party MDM solutions - Use a [WiFi CSP](https://docs.microsoft.com/windows/client-management/mdm/wifi-csp).</span></span>

3. <span data-ttu-id="b78c2-173">**PPKG**</span><span class="sxs-lookup"><span data-stu-id="b78c2-173">**PPKG**</span></span> 
    1. <span data-ttu-id="b78c2-174">Windows Configuration Designer openen</span><span class="sxs-lookup"><span data-stu-id="b78c2-174">Open Windows Configuration Designer</span></span>
    1. <span data-ttu-id="b78c2-175">Klik op Geavanceerde inrichting, voer de naam in voor het nieuwe Project en klik op Volgende.</span><span class="sxs-lookup"><span data-stu-id="b78c2-175">Click on Advanced Provisioning, enter the name for your new Project and click Next.</span></span>
    1. <span data-ttu-id="b78c2-176">Selecteer Windows Holographic (HoloLens 2) en klik op Volgende.</span><span class="sxs-lookup"><span data-stu-id="b78c2-176">Select Windows Holographic (HoloLens 2) and click Next.</span></span>
    1. <span data-ttu-id="b78c2-177">Importeer uw PPKG (optioneel) en klik op Voltooien.</span><span class="sxs-lookup"><span data-stu-id="b78c2-177">Import your PPKG (optional) and click Finish.</span></span>
    1. <span data-ttu-id="b78c2-178">Vouw Runtime settings -> Connectivity Profiles -> WLAN -> WLAN Proxy uit.</span><span class="sxs-lookup"><span data-stu-id="b78c2-178">Expand Runtime Settings -> Connectivity Profiles -> WLAN -> WLAN Proxy.</span></span>
    1. <span data-ttu-id="b78c2-179">Voer de SSID van uw Wi-Fi netwerk in en klik op Toevoegen.</span><span class="sxs-lookup"><span data-stu-id="b78c2-179">Enter the SSID of your Wi-Fi network and click Add.</span></span>
    1. <span data-ttu-id="b78c2-180">Selecteer uw Wi-Fi netwerk in het linkervenster en voer de gewenste aanpassingen in.</span><span class="sxs-lookup"><span data-stu-id="b78c2-180">Select your Wi-Fi network in the left window and enter your desired customizations.</span></span> <span data-ttu-id="b78c2-181">De ingeschakelde aanpassingen worden vet weergegeven in het menu links.</span><span class="sxs-lookup"><span data-stu-id="b78c2-181">The enabled customizations will show in bold on the left menu.</span></span>
    1. <span data-ttu-id="b78c2-182">Klik op Opslaan en afsluiten.</span><span class="sxs-lookup"><span data-stu-id="b78c2-182">Click Save and Exit.</span></span>
    1. <span data-ttu-id="b78c2-183">[Pas](hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup) het inrichtingspakket toe op de HoloLens.</span><span class="sxs-lookup"><span data-stu-id="b78c2-183">[Apply](hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup) the provisioning package to the HoloLens.</span></span>

<span data-ttu-id="b78c2-184">[CSP's](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) staan achter veel van de beheertaken en het beleid voor Windows 10, zowel in Microsoft Intune als bij niet-Microsoft MDM-serviceproviders.</span><span class="sxs-lookup"><span data-stu-id="b78c2-184">[CSPs](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) are behind many of the management tasks and policies for Windows 10, both in Microsoft Intune and in non-Microsoft MDM service providers.</span></span> <span data-ttu-id="b78c2-185">U kunt Windows [Configuration Designer ook gebruiken om](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-install-icd) een [inrichtingspakket te maken](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages) en dit toe te passen op de HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="b78c2-185">You can also use [Windows Configuration Designer](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-install-icd) to create a [provisioning package](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages) and apply it to the HoloLens 2.</span></span>
<span data-ttu-id="b78c2-186">De meest waarschijnlijke CSP's die worden toegepast op uw HoloLens 2 zijn:</span><span class="sxs-lookup"><span data-stu-id="b78c2-186">The most likely CSPs that will be applied to your HoloLens 2 are:</span></span>

- <span data-ttu-id="b78c2-187">[Wi-Fi CSP:](https://docs.microsoft.com/windows/client-management/mdm/wifi-csp)proxy per profiel Wi-Fi proxy</span><span class="sxs-lookup"><span data-stu-id="b78c2-187">[WiFi CSP](https://docs.microsoft.com/windows/client-management/mdm/wifi-csp): per-profile Wi-Fi proxy</span></span> 

[<span data-ttu-id="b78c2-188">Andere CSP's die worden ondersteund op HoloLens-apparaten</span><span class="sxs-lookup"><span data-stu-id="b78c2-188">Other CSPs supported in HoloLens devices</span></span>](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)





## <a name="vpn"></a><span data-ttu-id="b78c2-189">VPN</span><span class="sxs-lookup"><span data-stu-id="b78c2-189">VPN</span></span>
<span data-ttu-id="b78c2-190">Een VPN-verbinding kan helpen een veiligere verbinding en toegang tot het netwerk en internet van uw bedrijf te bieden.</span><span class="sxs-lookup"><span data-stu-id="b78c2-190">A VPN connection can help provide a more secure connection and access to your company's network and the Internet.</span></span> <span data-ttu-id="b78c2-191">HoloLens 2 ondersteunt de ingebouwde VPN-client en Universeel Windows-platform VPN-in plug-in (UWP).</span><span class="sxs-lookup"><span data-stu-id="b78c2-191">HoloLens 2 supports built-in VPN client and Universal Windows Platform (UWP) VPN plug-in.</span></span> 

<span data-ttu-id="b78c2-192">Ondersteunde ingebouwde VPN-protocollen:</span><span class="sxs-lookup"><span data-stu-id="b78c2-192">Supported Built-in VPN protocols:</span></span>
- <span data-ttu-id="b78c2-193">IKEv2</span><span class="sxs-lookup"><span data-stu-id="b78c2-193">IKEv2</span></span>
- <span data-ttu-id="b78c2-194">L2TP</span><span class="sxs-lookup"><span data-stu-id="b78c2-194">L2TP</span></span>
- <span data-ttu-id="b78c2-195">PPTP</span><span class="sxs-lookup"><span data-stu-id="b78c2-195">PPTP</span></span>

<span data-ttu-id="b78c2-196">Als certificaat wordt gebruikt voor verificatie voor de ingebouwde VPN-client, moet het vereiste clientcertificaat worden toegevoegd aan het certificaatopslag van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="b78c2-196">If certificate is used for authentication for built-in VPN client, the required client certificate needs to be added to user certificate store.</span></span> <span data-ttu-id="b78c2-197">Als u wilt weten of een VPN-in plug-in van derden HoloLens 2 ondersteunt, gaat u naar Store om de VPN-app te zoeken en te controleren of HoloLens wordt vermeld als een ondersteund apparaat. Op de pagina Systeemvereiste ondersteunt de app arm- of ARM64-architectuur.</span><span class="sxs-lookup"><span data-stu-id="b78c2-197">To find if a 3rd party VPN plug-in supports HoloLens 2, go to Store to locate VPN app and check if HoloLens is listed as a supported device and in the System Requirement page the app supports ARM or ARM64 architecture.</span></span> <span data-ttu-id="b78c2-198">HoloLens ondersteunt alleen Universeel Windows-platform voor VPN van derden.</span><span class="sxs-lookup"><span data-stu-id="b78c2-198">HoloLens only supports Universal Windows Platform applications for 3rd party VPN.</span></span>

 <span data-ttu-id="b78c2-199">VPN kan worden beheerd door MDM via [Settings/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn)en worden ingesteld via [Vpnv2-csp-beleid.](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp)</span><span class="sxs-lookup"><span data-stu-id="b78c2-199">VPN can be managed by MDM via [Settings/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn), and set via  [Vpnv2-csp policy](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp).</span></span>

<span data-ttu-id="b78c2-200">Meer informatie over [het configureren van VPN met](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) deze [handleidingen.](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide)</span><span class="sxs-lookup"><span data-stu-id="b78c2-200">Learn more about [how to configure VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) with [these guides](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide).</span></span>  

### <a name="vpn-via-ui"></a><span data-ttu-id="b78c2-201">VPN via de gebruikersinterface</span><span class="sxs-lookup"><span data-stu-id="b78c2-201">VPN via UI</span></span>

<span data-ttu-id="b78c2-202">VPN is niet standaard ingeschakeld, maar kan handmatig worden ingeschakeld door de **app** Instellingen te openen en naar Network & **Internet -> VPN te navigeren.**</span><span class="sxs-lookup"><span data-stu-id="b78c2-202">VPN is not enabled by default but can be enabled manually by opening **Settings** app and navigating to  **Network & Internet -> VPN**.</span></span>
1. <span data-ttu-id="b78c2-203">Selecteer een VPN-provider.</span><span class="sxs-lookup"><span data-stu-id="b78c2-203">Select a VPN provider.</span></span>
1. <span data-ttu-id="b78c2-204">Maak een verbindingsnaam.</span><span class="sxs-lookup"><span data-stu-id="b78c2-204">Create a connection name.</span></span> 
1. <span data-ttu-id="b78c2-205">Voer uw servernaam of -adres in.</span><span class="sxs-lookup"><span data-stu-id="b78c2-205">Enter your server name or address.</span></span>
1. <span data-ttu-id="b78c2-206">Selecteer het VPN-type.</span><span class="sxs-lookup"><span data-stu-id="b78c2-206">Select the VPN type.</span></span>
1. <span data-ttu-id="b78c2-207">Selecteer het type aanmeldingsgegevens.</span><span class="sxs-lookup"><span data-stu-id="b78c2-207">Select type of sign-in info.</span></span> 
1. <span data-ttu-id="b78c2-208">Voeg desgewenst een gebruikersnaam en wachtwoord toe.</span><span class="sxs-lookup"><span data-stu-id="b78c2-208">Optionally add user name and password.</span></span>
1. <span data-ttu-id="b78c2-209">Pas de VPN-instellingen toe.</span><span class="sxs-lookup"><span data-stu-id="b78c2-209">Apply the VPN settings.</span></span> 

![Vpn-instellingen voor HoloLens](./images/vpn-settings-ui.jpg)

### <a name="vpn-set-via-provisioning-package"></a><span data-ttu-id="b78c2-211">VPN ingesteld via inrichtingspakket</span><span class="sxs-lookup"><span data-stu-id="b78c2-211">VPN set via Provisioning Package</span></span>

> [!TIP] 
> <span data-ttu-id="b78c2-212">In onze Windows Holographic, versie 20H2, hebben we een proxyconfiguratieprobleem opgelost voor de VPN-verbinding.</span><span class="sxs-lookup"><span data-stu-id="b78c2-212">In our Windows Holographic, version 20H2 we fixed a proxy configuration issue for VPN connection.</span></span> <span data-ttu-id="b78c2-213">Overweeg apparaten te upgraden naar deze build als u van plan bent deze stroom te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="b78c2-213">Please consider upgrading devices to this build if you intend to use this flow.</span></span>

1. <span data-ttu-id="b78c2-214">Start Windows Configuration Designer.</span><span class="sxs-lookup"><span data-stu-id="b78c2-214">Launch Windows Configuration Designer.</span></span>
1. <span data-ttu-id="b78c2-215">Klik **op HoloLens-apparaten inrichten** en selecteer vervolgens doelapparaat en **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="b78c2-215">Click **Provision HoloLens devices**, then select target device and **Next**.</span></span>
1. <span data-ttu-id="b78c2-216">Voer de pakketnaam en het pad in.</span><span class="sxs-lookup"><span data-stu-id="b78c2-216">Enter package name and path.</span></span>
1. <span data-ttu-id="b78c2-217">Klik **op Overschakelen naar geavanceerde editor.**</span><span class="sxs-lookup"><span data-stu-id="b78c2-217">Click **Switch to advanced editor**.</span></span>
1. <span data-ttu-id="b78c2-218">Open **Runtime-instellingen**  ->  **ConnectivityProfiles**  ->  **VPN**  ->  **VPNSettings**.</span><span class="sxs-lookup"><span data-stu-id="b78c2-218">Open **Runtime settings** -> **ConnectivityProfiles** -> **VPN** -> **VPNSettings**.</span></span>
1. <span data-ttu-id="b78c2-219">VPNProfileName configureren</span><span class="sxs-lookup"><span data-stu-id="b78c2-219">Configure VPNProfileName</span></span>
1. <span data-ttu-id="b78c2-220">Selecteer ProfileType: **Native** of **Third Party.**</span><span class="sxs-lookup"><span data-stu-id="b78c2-220">Select ProfileType: **Native** or **Third Party**.</span></span>
    1. <span data-ttu-id="b78c2-221">Voor Systeemeigen profiel selecteert **u SysteemeigenProtocolType** en configureert u vervolgens de server, het routeringsbeleid, het verificatietype en andere instellingen.</span><span class="sxs-lookup"><span data-stu-id="b78c2-221">For Native profile, select **NativeProtocolType**, then configure server, routing policy, authentication type and other settings.</span></span>
    1. <span data-ttu-id="b78c2-222">Configureer voor het profiel 'Externe partij' de server-URL, de familienaam van de VPN-in plug-in-app-pakket (slechts drie vooraf gedefinieerde) en aangepaste configuraties.</span><span class="sxs-lookup"><span data-stu-id="b78c2-222">For "Third Party" profile, configure server URL, VPN plug-in App package family name (only 3 predefined) and custom configurations.</span></span>
1. <span data-ttu-id="b78c2-223">Exporteert u uw pakket.</span><span class="sxs-lookup"><span data-stu-id="b78c2-223">Export your package.</span></span>
1. <span data-ttu-id="b78c2-224">Verbind uw HoloLens en kopieer het PPKG-bestand naar het apparaat.</span><span class="sxs-lookup"><span data-stu-id="b78c2-224">Connect your HoloLens and copy the .ppkg file to the device.</span></span> 
1. <span data-ttu-id="b78c2-225">Pas op HoloLens de VPN .ppkg toe door de Startmenu te openen en Instellingen Accounttoegang tot werk of school te selecteren Inrichtingspakket toevoegen of verwijderen -> Selecteer uw  ->    ->    ->   VPN-pakket.</span><span class="sxs-lookup"><span data-stu-id="b78c2-225">On HoloLens, apply the VPN .ppkg by opening the Start menu and selecting **Settings** -> **Account** -> **Access work or school** -> **Add or remove provisioning package** -> Select your VPN package.</span></span>


### <a name="setting-up-vpn-via-intune"></a><span data-ttu-id="b78c2-226">VPN instellen via Intune</span><span class="sxs-lookup"><span data-stu-id="b78c2-226">Setting up VPN via Intune</span></span>
<span data-ttu-id="b78c2-227">Volg de Intune-documenten om aan de slag te gaan.</span><span class="sxs-lookup"><span data-stu-id="b78c2-227">Just follow the Intune documents to get started.</span></span> <span data-ttu-id="b78c2-228">Wanneer u deze stappen volgt, moet u rekening houden met de ingebouwde VPN-protocollen die door HoloLens-apparaten worden ondersteund.</span><span class="sxs-lookup"><span data-stu-id="b78c2-228">When following these steps please keep in mind the built-in VPN protocols that HoloLens devices support.</span></span> 

<span data-ttu-id="b78c2-229">[Maak VPN-profielen om verbinding te maken met VPN-servers in Intune.](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-configure)</span><span class="sxs-lookup"><span data-stu-id="b78c2-229">[Create VPN profiles to connect to VPN servers in Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-configure).</span></span>

<span data-ttu-id="b78c2-230">[Windows 10 en Windows Holographic-apparaatinstellingen om VPN-verbindingen toe te voegen met behulp van Intune.](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-windows-10)</span><span class="sxs-lookup"><span data-stu-id="b78c2-230">[Windows 10 and Windows Holographic device settings to add VPN connections using Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-windows-10).</span></span>

<span data-ttu-id="b78c2-231">Wanneer u klaar bent, moet u [het profiel toewijzen.](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign)</span><span class="sxs-lookup"><span data-stu-id="b78c2-231">When done please remember to [assign the profile](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign).</span></span>

### <a name="vpn-via-3rd-party-mdm-solutions"></a><span data-ttu-id="b78c2-232">VPN via MDM-oplossingen van derden</span><span class="sxs-lookup"><span data-stu-id="b78c2-232">VPN via 3rd party MDM solutions</span></span>
<span data-ttu-id="b78c2-233">Voorbeeld van een VPN-verbinding van derden:</span><span class="sxs-lookup"><span data-stu-id="b78c2-233">3rd party VPN connection example:</span></span>
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

<span data-ttu-id="b78c2-234">Native IKEv2 VPN-voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="b78c2-234">Native IKEv2 VPN example:</span></span>
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
## <a name="disabling-wi-fi-on-hololens-1st-gen"></a><span data-ttu-id="b78c2-235">Uitschakelen Wi-Fi HoloLens (1e generatie)</span><span class="sxs-lookup"><span data-stu-id="b78c2-235">Disabling Wi-Fi on HoloLens (1st gen)</span></span>

### <a name="using-the-settings-app-on-hololens"></a><span data-ttu-id="b78c2-236">De app Instellingen op HoloLens gebruiken</span><span class="sxs-lookup"><span data-stu-id="b78c2-236">Using the Settings app on HoloLens</span></span>

1. <span data-ttu-id="b78c2-237">Open het **menu** Start.</span><span class="sxs-lookup"><span data-stu-id="b78c2-237">Open the **Start** menu.</span></span>
1. <span data-ttu-id="b78c2-238">Selecteer de app **Instellingen** **op Start** of in de lijst **Alle apps** rechts van het **menu** Start.</span><span class="sxs-lookup"><span data-stu-id="b78c2-238">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="b78c2-239">De  app Instellingen wordt automatisch voor u geplaatst.</span><span class="sxs-lookup"><span data-stu-id="b78c2-239">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="b78c2-240">Selecteer **Netwerk & Internet.**</span><span class="sxs-lookup"><span data-stu-id="b78c2-240">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="b78c2-241">Selecteer de Wi-Fi schuifregelaar om deze naar de **uit-positie te** verplaatsen.</span><span class="sxs-lookup"><span data-stu-id="b78c2-241">Select the Wi-Fi slider switch to move it to the **Off** position.</span></span> <span data-ttu-id="b78c2-242">Hiermee worden de RF-onderdelen van het Wi-Fi uitgeschakeld en worden alle Wi-Fi op HoloLens uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="b78c2-242">This will turn off the RF components of the Wi-Fi radio and disable all Wi-Fi functionality on HoloLens.</span></span>

    > [!WARNING]
    > <span data-ttu-id="b78c2-243">Wanneer het Wi-Fi is uitgeschakeld, kan HoloLens uw ruimten niet automatisch [laden.](hololens-spaces.md)</span><span class="sxs-lookup"><span data-stu-id="b78c2-243">When the Wi-Fi radio is disabled, HoloLens will not be able to automatically load your [spaces](hololens-spaces.md).</span></span>

1. <span data-ttu-id="b78c2-244">Verplaats de schuifregelaar naar de **positie Aan om** het Wi-Fi in te schakelen en de Wi-Fi op Microsoft HoloLens.</span><span class="sxs-lookup"><span data-stu-id="b78c2-244">Move the slider switch to the **On** position to turn on the Wi-Fi radio and restore Wi-Fi functionality on Microsoft HoloLens.</span></span> <span data-ttu-id="b78c2-245">De geselecteerde Wi-Fi radiotoestand (**Aan** of **Uit)** blijft behouden tijdens het opnieuw opstarten.</span><span class="sxs-lookup"><span data-stu-id="b78c2-245">The selected Wi-Fi radio state (**On** or **Off**) will persist across reboots.</span></span>

## <a name="identifying-the-ip-address-of-your-hololens-on-the-wi-fi-network"></a><span data-ttu-id="b78c2-246">Het IP-adres van uw HoloLens in het Wi-Fi identificeren</span><span class="sxs-lookup"><span data-stu-id="b78c2-246">Identifying the IP Address of your HoloLens on the Wi-Fi network</span></span>

### <a name="by-using-the-settings-app"></a><span data-ttu-id="b78c2-247">Met behulp van de app Instellingen</span><span class="sxs-lookup"><span data-stu-id="b78c2-247">By using the Settings app</span></span>

1. <span data-ttu-id="b78c2-248">Open het **menu** Start.</span><span class="sxs-lookup"><span data-stu-id="b78c2-248">Open the **Start** menu.</span></span>
1. <span data-ttu-id="b78c2-249">Selecteer de app **Instellingen** **op Start** of in de lijst **Alle apps** rechts van het **menu** Start.</span><span class="sxs-lookup"><span data-stu-id="b78c2-249">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="b78c2-250">De  app Instellingen wordt automatisch voor u geplaatst.</span><span class="sxs-lookup"><span data-stu-id="b78c2-250">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="b78c2-251">Selecteer **Netwerk & Internet.**</span><span class="sxs-lookup"><span data-stu-id="b78c2-251">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="b78c2-252">Schuif omlaag naar onder de lijst met beschikbare Wi-Fi netwerken en selecteer **Hardware-eigenschappen.**</span><span class="sxs-lookup"><span data-stu-id="b78c2-252">Scroll down to beneath the list of available Wi-Fi networks and select **Hardware properties**.</span></span>

    ![Hardware-eigenschappen in Wi-Fi instellingen](./images/wifi-hololens-hwdetails.jpg)

   <span data-ttu-id="b78c2-254">Het IP-adres wordt weergegeven naast **IPv4-adres**.</span><span class="sxs-lookup"><span data-stu-id="b78c2-254">The IP address appears next to **IPv4 address**.</span></span>

### <a name="by-using-voice-commands"></a><span data-ttu-id="b78c2-255">Met behulp van spraakopdrachten</span><span class="sxs-lookup"><span data-stu-id="b78c2-255">By using voice commands</span></span>

<span data-ttu-id="b78c2-256">Afhankelijk van de build van uw apparaten kunt u ingebouwde spraakopdrachten of Cortana gebruiken om uw IP-adres weer te geven.</span><span class="sxs-lookup"><span data-stu-id="b78c2-256">Depending on your devices build you can either use built in voice commands or Cortana to display your IP address.</span></span> <span data-ttu-id="b78c2-257">Op builds na [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) spreekt u "Wat is mijn IP-adres?"</span><span class="sxs-lookup"><span data-stu-id="b78c2-257">On builds after [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) speak "What's my IP address?"</span></span> <span data-ttu-id="b78c2-258">en worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="b78c2-258">and it will be displayed.</span></span> <span data-ttu-id="b78c2-259">Voor eerdere builds of HoloLens (eerste generatie) zegt u "Hey Cortana, Wat is mijn IP-adres?"</span><span class="sxs-lookup"><span data-stu-id="b78c2-259">For earlier builds or HoloLens (1st gen) say "Hey Cortana, What's my IP address?"</span></span> <span data-ttu-id="b78c2-260">en Cortana worden weergegeven en uw IP-adres gelezen.</span><span class="sxs-lookup"><span data-stu-id="b78c2-260">and Cortana will display and read out your IP address.</span></span>

### <a name="by-using-windows-device-portal"></a><span data-ttu-id="b78c2-261">Met behulp van Windows Apparaatportal</span><span class="sxs-lookup"><span data-stu-id="b78c2-261">By using Windows Device Portal</span></span>

1. <span data-ttu-id="b78c2-262">Open de apparaatportal in een webbrowser op [uw pc.](/windows/mixed-reality/using-the-windows-device-portal.md#networking)</span><span class="sxs-lookup"><span data-stu-id="b78c2-262">In a web browser on your PC, open the [device portal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span></span>
1. <span data-ttu-id="b78c2-263">Navigeer naar **de sectie** Netwerken.</span><span class="sxs-lookup"><span data-stu-id="b78c2-263">Navigate to the **Networking** section.</span></span>  
   <span data-ttu-id="b78c2-264">In deze sectie worden uw IP-adres en andere netwerkgegevens weergegeven.</span><span class="sxs-lookup"><span data-stu-id="b78c2-264">This section displays your IP address and other network information.</span></span> <span data-ttu-id="b78c2-265">Met deze methode kunt u het IP-adres kopiëren en plakken op uw ontwikkel-pc.</span><span class="sxs-lookup"><span data-stu-id="b78c2-265">By using this method, you can copy and paste of the IP address on your development PC.</span></span>

## <a name="change-ip-address-to-static-address"></a><span data-ttu-id="b78c2-266">IP-adres wijzigen in statisch adres</span><span class="sxs-lookup"><span data-stu-id="b78c2-266">Change IP Address to static address</span></span>
### <a name="by-using-settings"></a><span data-ttu-id="b78c2-267">Met behulp van Instellingen</span><span class="sxs-lookup"><span data-stu-id="b78c2-267">By using Settings</span></span>
 
1. <span data-ttu-id="b78c2-268">Open het **menu** Start.</span><span class="sxs-lookup"><span data-stu-id="b78c2-268">Open the **Start** menu.</span></span>
1. <span data-ttu-id="b78c2-269">Selecteer de app **Instellingen** **op Start** of in de lijst **Alle apps** rechts van het **menu** Start.</span><span class="sxs-lookup"><span data-stu-id="b78c2-269">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="b78c2-270">De  app Instellingen wordt automatisch voor u geplaatst.</span><span class="sxs-lookup"><span data-stu-id="b78c2-270">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="b78c2-271">Selecteer **Netwerk & Internet.**</span><span class="sxs-lookup"><span data-stu-id="b78c2-271">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="b78c2-272">Schuif omlaag naar onder de lijst met beschikbare Wi-Fi netwerken en selecteer **Hardware-eigenschappen.**</span><span class="sxs-lookup"><span data-stu-id="b78c2-272">Scroll down to beneath the list of available Wi-Fi networks and select **Hardware properties**.</span></span>
1. <span data-ttu-id="b78c2-273">Wijzig in **het venster IP-instellingen** bewerken het eerste veld in **Handmatig.**</span><span class="sxs-lookup"><span data-stu-id="b78c2-273">In the **Edit IP settings** window, change the first field to **Manual**.</span></span>
1. <span data-ttu-id="b78c2-274">Voer de gewenste IP-configuratie in de overige velden in en klik vervolgens op **Opslaan.**</span><span class="sxs-lookup"><span data-stu-id="b78c2-274">Input the desired IP configuration in the remaining fields and then click **Save**.</span></span>

### <a name="by-using-windows-device-portal"></a><span data-ttu-id="b78c2-275">Met behulp van Windows Apparaatportal</span><span class="sxs-lookup"><span data-stu-id="b78c2-275">By using Windows Device Portal</span></span>

1. <span data-ttu-id="b78c2-276">Open de apparaatportal in een webbrowser op [uw pc.](/windows/mixed-reality/using-the-windows-device-portal.md#networking)</span><span class="sxs-lookup"><span data-stu-id="b78c2-276">In a web browser on your PC, open the [device portal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span></span>
1. <span data-ttu-id="b78c2-277">Navigeer naar **de sectie** Netwerken.</span><span class="sxs-lookup"><span data-stu-id="b78c2-277">Navigate to the **Networking** section.</span></span>
1. <span data-ttu-id="b78c2-278">Selecteer de **knop IPv4-configuratie.**</span><span class="sxs-lookup"><span data-stu-id="b78c2-278">Select the **IPv4 Configuration** button.</span></span>
1. <span data-ttu-id="b78c2-279">Selecteer **Het volgende IP-adres gebruiken en** voer de gewenste TCP/IP-configuratie in.</span><span class="sxs-lookup"><span data-stu-id="b78c2-279">Select **Use the following IP address** and input the desired TCP/IP configuration.</span></span>
1. <span data-ttu-id="b78c2-280">Selecteer **De volgende DNS-serveradressen gebruiken** en voer zo nodig de voorkeurs- en alternatieve DNS-serveradressen in.</span><span class="sxs-lookup"><span data-stu-id="b78c2-280">Select **Use the following DNS server addresses** and enter the Preferred and Alternate DNS server addresses, if needed.</span></span>
1. <span data-ttu-id="b78c2-281">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="b78c2-281">Click **Save**.</span></span> 
