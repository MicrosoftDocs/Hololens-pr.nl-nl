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
# <a name="connect-hololens-to-a-network"></a>HoloLens verbinden met een netwerk

Als u de meeste dingen op uw HoloLens wilt doen, moet u zijn verbonden met een netwerk. HoloLens bevat een 2x2 Wi-Fi-radio die geschikt is voor 802.11ac en is vergelijkbaar met het verbinden van een Windows 10 Desktop- of Mobile-apparaat met een Wi-Fi-netwerk. Deze handleiding helpt u bij het volgende:

- Verbinding maken met een netwerk via Wi-Fi of alleen HoloLens 2, Wi-Fi Direct of Ethernet via USB-C
- Uitschakelen en opnieuw inschakelen Wi-Fi

Lees meer over het [offline gebruik van HoloLens.](hololens-offline.md)

## <a name="connecting-for-the-first-time"></a>Voor de eerste keer verbinding maken

De eerste keer dat u uw HoloLens gebruikt, wordt u begeleid bij het maken van verbinding met Wi-Fi netwerk. Als u tijdens de installatie problemen hebt met het maken van verbinding met Wi-Fi, moet u ervoor zorgen dat uw netwerk een open, met wachtwoorden beveiligd netwerk of een captive portal-netwerk is. Controleer ook of u voor het netwerk geen certificaat hoeft te gebruiken om verbinding te maken. Na de installatie kunt u verbinding maken met andere typen Wi-Fi netwerken.

Op HoloLens 2 apparaten kan een gebruiker ook een [USB-C-naar-Ethernet-adapter](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) gebruiken om rechtstreeks verbinding te maken met Wi-Fi om te helpen bij het instellen van het apparaat. Zodra het apparaat is ingesteld, kan een gebruiker de adapter blijven gebruiken of het apparaat loskoppelen van de adapter en verbinding maken [met Wi-Fi](hololens-network.md#connecting-to-wi-fi-after-setup)na het instellen. 

## <a name="connecting-to-wi-fi-after-setup"></a>Verbinding maken met Wi-Fi na de installatie

1. Maak de beweging **Start vooraf en** selecteer **Instellingen.** De app Instellingen wordt automatisch voor u geplaatst.
1. Selecteer **Network & Internet**  >  **Wi-Fi**. Controleer of Wi-Fi is ingeschakeld. Als u uw netwerk niet ziet, schuift u omlaag in de lijst.
1. Selecteer een netwerk en selecteer vervolgens **Verbinding maken.**
1. Als u wordt gevraagd om een netwerkwachtwoord typt u dit en selecteert u **volgende.**

![Instellingen voor HoloLens-Wi-Fi](./images/hololens-2-wifi-settings.jpg)

Als u wilt controleren of u bent verbonden met Wi-Fi netwerk, controleert u de status Wi-Fi in het menu **Start:**

1. Open het **menu** Start.
1. Kijk linksboven in het menu **Start** naar de Wi-Fi status. De status van Wi-Fi en de SSID van het verbonden netwerk wordt weergegeven.

> [!TIP]
> Als Wi-Fi niet beschikbaar is, kunt u ook verbinding [maken met mobiele en 5G-netwerken.](hololens-cellular.md)

> [!IMPORTANT]
> Gebruikers kunnen het Wi-Fi-roaminggedrag van de HoloLens 2 niet afstemmen. De enige manier om de Wi-Fi-lijst te **vernieuwen, is door** de Wi-Fi uit en Aan te zetten. Dit voorkomt veel problemen, zoals wanneer een apparaat 'vastloopt' aan een AP wanneer het buiten het bereik valt.

## <a name="connect-hololens-to-enterprise-wi-fi-network"></a>HoloLens verbinden met Enterprise Wi-Fi Network

Enterprise Wi-Fi-profielen maken gebruik van Extensible Authentication Protocol (EAP) om verbinding Wi-Fi verifiëren. Het HoloLens Enterprise Wi-Fi-profiel kan worden geconfigureerd via MDM of een inrichtingspakket dat is gemaakt door [Windows Configuration Designer.](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages)

Raadpleeg Microsoft Intune [Intune](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) voor configuratie-instructies voor meer informatie over het beheerde apparaat.

Als u een Wi-Fi-inrichtingspakket in WCD wilt maken, is een vooraf geconfigureerd Wi-Fi-.xml vereist. Hier is een voorbeeld van Wi-Fi voor WPA2-Enterprise met EAP-TLS-verificatie:

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


Het CA-basiscertificaat van de server en het clientcertificaat moeten mogelijk worden ingericht op het apparaat, afhankelijk van het EAP-type.

Aanvullende bronnen:

- WLANv1Profile Schema: [[MS-GPWL]: Draadloos LAN-profiel v1 Schema | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)
- EAP-TLS-schema: [[MS-GPWL]: Microsoft EAP TLS-schema | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)

Raadpleeg onze [pagina Voor probleemoplossing](hololens2-enterprise-troubleshooting.md#) als u problemen hebt met het maken van verbinding met uw Wi-Fi.

## <a name="configure-network-proxy"></a>Netwerkproxy configureren

In deze sectie wordt de netwerkproxy voor UwP-apps (HoloLens OS) en Universeel Windows-platform (UWP) met behulp van Windows HTTP-stack besturingssystemen. Toepassingen die geen Windows HTTP-stack gebruiken, hebben mogelijk hun eigen proxyconfiguratie en -verwerking. 

### <a name="proxy-configurations"></a>Proxyconfiguraties 

- Pac-script (Proxy Auto-Config) : een [PAC-bestand](https://developer.mozilla.org/en-US/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_PAC_file) (opent een niet-Microsoft-site) bevat de JavaScript-functie FindProxyForURL(url, host). 
- Statische proxy: in de vorm van Server:Poort.  
- Web Proxy Auto-Discovery Protocol (WPAD): geef de URL van het proxyconfiguratiebestand op via DHCP of DNS. 

### <a name="proxy-provisioning-methods"></a>Proxy-inrichtingsmethoden 
Er zijn drie manieren om proxies in terichten:

 

1.  **Gebruikersinterface van instellingen:** 
    1. Proxy per gebruiker (20H2 of eerder):
        1. Open het Startmenu selecteer Instellingen.
        2. Selecteer Network & Internet en vervolgens Proxy in het menu links.
        3. Schuif omlaag naar Handmatige proxy-installatie en stel Een proxyserver gebruiken in op Aan.
        4. Voer het IP-adres van de proxyserver in.
        5. Voer het poortnummer in.
        6. Klik op Opslaan.
      1. Wi-Fi-proxy (21H1 of hoger):
          1. Open de Startmenu en ga naar Wi-Fi pagina Eigenschappen van uw netwerk.
          1. Schuif omlaag naar Proxy
          1. Wijzigen in Handmatige installatie
          1. Voer het IP-adres van de proxyserver in.
          1. Voer het poortnummer in.
          1. Klik op Toepassen.
        
 2. **MDM** 
     1. Intune: gebruik deze stappen [om een](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) proxy in Intune te configureren. U moet naar de onderkant van de sectie schuiven.
     1. Andere MDM-oplossingen van derden: gebruik een [WiFi CSP.](https://docs.microsoft.com/windows/client-management/mdm/wifi-csp)

3. **PPKG** 
    1. Windows Configuration Designer openen
    1. Klik op Geavanceerde inrichting, voer de naam in voor het nieuwe Project en klik op Volgende.
    1. Selecteer Windows Holographic (HoloLens 2) en klik op Volgende.
    1. Importeer uw PPKG (optioneel) en klik op Voltooien.
    1. Vouw Runtime settings -> Connectivity Profiles -> WLAN -> WLAN Proxy uit.
    1. Voer de SSID van uw Wi-Fi netwerk in en klik op Toevoegen.
    1. Selecteer uw Wi-Fi netwerk in het linkervenster en voer de gewenste aanpassingen in. De ingeschakelde aanpassingen worden vet weergegeven in het menu links.
    1. Klik op Opslaan en afsluiten.
    1. [Pas](hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup) het inrichtingspakket toe op de HoloLens.

[CSP's](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) staan achter veel van de beheertaken en het beleid voor Windows 10, zowel in Microsoft Intune als bij niet-Microsoft MDM-serviceproviders. U kunt Windows [Configuration Designer ook gebruiken om](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-install-icd) een [inrichtingspakket te maken](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages) en dit toe te passen op de HoloLens 2.
De meest waarschijnlijke CSP's die worden toegepast op uw HoloLens 2 zijn:

- [Wi-Fi CSP:](https://docs.microsoft.com/windows/client-management/mdm/wifi-csp)proxy per profiel Wi-Fi proxy 

[Andere CSP's die worden ondersteund op HoloLens-apparaten](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)





## <a name="vpn"></a>VPN
Een VPN-verbinding kan helpen een veiligere verbinding en toegang tot het netwerk en internet van uw bedrijf te bieden. HoloLens 2 ondersteunt de ingebouwde VPN-client en Universeel Windows-platform VPN-in plug-in (UWP). 

Ondersteunde ingebouwde VPN-protocollen:
- IKEv2
- L2TP
- PPTP

Als certificaat wordt gebruikt voor verificatie voor de ingebouwde VPN-client, moet het vereiste clientcertificaat worden toegevoegd aan het certificaatopslag van de gebruiker. Als u wilt weten of een VPN-in plug-in van derden HoloLens 2 ondersteunt, gaat u naar Store om de VPN-app te zoeken en te controleren of HoloLens wordt vermeld als een ondersteund apparaat. Op de pagina Systeemvereiste ondersteunt de app arm- of ARM64-architectuur. HoloLens ondersteunt alleen Universeel Windows-platform voor VPN van derden.

 VPN kan worden beheerd door MDM via [Settings/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn)en worden ingesteld via [Vpnv2-csp-beleid.](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp)

Meer informatie over [het configureren van VPN met](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) deze [handleidingen.](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide)  

### <a name="vpn-via-ui"></a>VPN via de gebruikersinterface

VPN is niet standaard ingeschakeld, maar kan handmatig worden ingeschakeld door de **app** Instellingen te openen en naar Network & **Internet -> VPN te navigeren.**
1. Selecteer een VPN-provider.
1. Maak een verbindingsnaam. 
1. Voer uw servernaam of -adres in.
1. Selecteer het VPN-type.
1. Selecteer het type aanmeldingsgegevens. 
1. Voeg desgewenst een gebruikersnaam en wachtwoord toe.
1. Pas de VPN-instellingen toe. 

![Vpn-instellingen voor HoloLens](./images/vpn-settings-ui.jpg)

### <a name="vpn-set-via-provisioning-package"></a>VPN ingesteld via inrichtingspakket

> [!TIP] 
> In onze Windows Holographic, versie 20H2, hebben we een proxyconfiguratieprobleem opgelost voor de VPN-verbinding. Overweeg apparaten te upgraden naar deze build als u van plan bent deze stroom te gebruiken.

1. Start Windows Configuration Designer.
1. Klik **op HoloLens-apparaten inrichten** en selecteer vervolgens doelapparaat en **Volgende.**
1. Voer de pakketnaam en het pad in.
1. Klik **op Overschakelen naar geavanceerde editor.**
1. Open **Runtime-instellingen**  ->  **ConnectivityProfiles**  ->  **VPN**  ->  **VPNSettings**.
1. VPNProfileName configureren
1. Selecteer ProfileType: **Native** of **Third Party.**
    1. Voor Systeemeigen profiel selecteert **u SysteemeigenProtocolType** en configureert u vervolgens de server, het routeringsbeleid, het verificatietype en andere instellingen.
    1. Configureer voor het profiel 'Externe partij' de server-URL, de familienaam van de VPN-in plug-in-app-pakket (slechts drie vooraf gedefinieerde) en aangepaste configuraties.
1. Exporteert u uw pakket.
1. Verbind uw HoloLens en kopieer het PPKG-bestand naar het apparaat. 
1. Pas op HoloLens de VPN .ppkg toe door de Startmenu te openen en Instellingen Accounttoegang tot werk of school te selecteren Inrichtingspakket toevoegen of verwijderen -> Selecteer uw  ->    ->    ->   VPN-pakket.


### <a name="setting-up-vpn-via-intune"></a>VPN instellen via Intune
Volg de Intune-documenten om aan de slag te gaan. Wanneer u deze stappen volgt, moet u rekening houden met de ingebouwde VPN-protocollen die door HoloLens-apparaten worden ondersteund. 

[Maak VPN-profielen om verbinding te maken met VPN-servers in Intune.](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-configure)

[Windows 10 en Windows Holographic-apparaatinstellingen om VPN-verbindingen toe te voegen met behulp van Intune.](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-windows-10)

Wanneer u klaar bent, moet u [het profiel toewijzen.](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign)

### <a name="vpn-via-3rd-party-mdm-solutions"></a>VPN via MDM-oplossingen van derden
Voorbeeld van een VPN-verbinding van derden:
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

Native IKEv2 VPN-voorbeeld:
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
## <a name="disabling-wi-fi-on-hololens-1st-gen"></a>Uitschakelen Wi-Fi HoloLens (1e generatie)

### <a name="using-the-settings-app-on-hololens"></a>De app Instellingen op HoloLens gebruiken

1. Open het **menu** Start.
1. Selecteer de app **Instellingen** **op Start** of in de lijst **Alle apps** rechts van het **menu** Start. De  app Instellingen wordt automatisch voor u geplaatst.
1. Selecteer **Netwerk & Internet.**
1. Selecteer de Wi-Fi schuifregelaar om deze naar de **uit-positie te** verplaatsen. Hiermee worden de RF-onderdelen van het Wi-Fi uitgeschakeld en worden alle Wi-Fi op HoloLens uitgeschakeld.

    > [!WARNING]
    > Wanneer het Wi-Fi is uitgeschakeld, kan HoloLens uw ruimten niet automatisch [laden.](hololens-spaces.md)

1. Verplaats de schuifregelaar naar de **positie Aan om** het Wi-Fi in te schakelen en de Wi-Fi op Microsoft HoloLens. De geselecteerde Wi-Fi radiotoestand (**Aan** of **Uit)** blijft behouden tijdens het opnieuw opstarten.

## <a name="identifying-the-ip-address-of-your-hololens-on-the-wi-fi-network"></a>Het IP-adres van uw HoloLens in het Wi-Fi identificeren

### <a name="by-using-the-settings-app"></a>Met behulp van de app Instellingen

1. Open het **menu** Start.
1. Selecteer de app **Instellingen** **op Start** of in de lijst **Alle apps** rechts van het **menu** Start. De  app Instellingen wordt automatisch voor u geplaatst.
1. Selecteer **Netwerk & Internet.**
1. Schuif omlaag naar onder de lijst met beschikbare Wi-Fi netwerken en selecteer **Hardware-eigenschappen.**

    ![Hardware-eigenschappen in Wi-Fi instellingen](./images/wifi-hololens-hwdetails.jpg)

   Het IP-adres wordt weergegeven naast **IPv4-adres**.

### <a name="by-using-voice-commands"></a>Met behulp van spraakopdrachten

Afhankelijk van de build van uw apparaten kunt u ingebouwde spraakopdrachten of Cortana gebruiken om uw IP-adres weer te geven. Op builds na [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) spreekt u "Wat is mijn IP-adres?" en worden weergegeven. Voor eerdere builds of HoloLens (eerste generatie) zegt u "Hey Cortana, Wat is mijn IP-adres?" en Cortana worden weergegeven en uw IP-adres gelezen.

### <a name="by-using-windows-device-portal"></a>Met behulp van Windows Apparaatportal

1. Open de apparaatportal in een webbrowser op [uw pc.](/windows/mixed-reality/using-the-windows-device-portal.md#networking)
1. Navigeer naar **de sectie** Netwerken.  
   In deze sectie worden uw IP-adres en andere netwerkgegevens weergegeven. Met deze methode kunt u het IP-adres kopiëren en plakken op uw ontwikkel-pc.

## <a name="change-ip-address-to-static-address"></a>IP-adres wijzigen in statisch adres
### <a name="by-using-settings"></a>Met behulp van Instellingen
 
1. Open het **menu** Start.
1. Selecteer de app **Instellingen** **op Start** of in de lijst **Alle apps** rechts van het **menu** Start. De  app Instellingen wordt automatisch voor u geplaatst.
1. Selecteer **Netwerk & Internet.**
1. Schuif omlaag naar onder de lijst met beschikbare Wi-Fi netwerken en selecteer **Hardware-eigenschappen.**
1. Wijzig in **het venster IP-instellingen** bewerken het eerste veld in **Handmatig.**
1. Voer de gewenste IP-configuratie in de overige velden in en klik vervolgens op **Opslaan.**

### <a name="by-using-windows-device-portal"></a>Met behulp van Windows Apparaatportal

1. Open de apparaatportal in een webbrowser op [uw pc.](/windows/mixed-reality/using-the-windows-device-portal.md#networking)
1. Navigeer naar **de sectie** Netwerken.
1. Selecteer de **knop IPv4-configuratie.**
1. Selecteer **Het volgende IP-adres gebruiken en** voer de gewenste TCP/IP-configuratie in.
1. Selecteer **De volgende DNS-serveradressen gebruiken** en voer zo nodig de voorkeurs- en alternatieve DNS-serveradressen in.
1. Klik op **Opslaan**. 
