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
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/13/2021
ms.locfileid: "126035960"
---
# <a name="troubleshooting-implementation-and-managed-devices"></a>Problemen met implementatie en beheerde apparaten oplossen 

In dit artikel wordt beschreven hoe u verschillende problemen kunt oplossen of vragen kunt beantwoorden met betrekking tot de implementatie en het beheer van HoloLens 2.

>[!IMPORTANT]
> Voordat u een probleemoplossingsprocedure start, moet u ervoor zorgen dat uw apparaat, indien mogelijk, wordt geladen op **20 tot 40** procent van de accucapaciteit. De [accuindicatorlichten onder](hololens2-setup.md#lights-that-indicate-the-battery-level) de aan/uit-knop zijn een snelle manier om de accucapaciteit te controleren zonder u aan te melden bij het apparaat.


<a id="list"></a>
- [Problemen met EAP oplossen](#eap-troubleshooting)
- [Problemen met Wi-Fi oplossen](#wi-fi-troubleshooting)
- [Problemen met het netwerk oplossen](#network-troubleshooting)
- [Kan niet aanmelden bij een eerder ingesteld HoloLens apparaat](#cant-sign-in-to-a-previously-setup-hololens-device)
- [Kan niet aanmelden na het bijwerken naar Windows Holographic 21H1](#cant-login-after-updating-to-windows-holographic-21h1)
- [Problemen met Autopilot oplossen](#autopilot-troubleshooting)
- [Veelgestelde HoloLens beheerde apparaten](#managed-hololens-devices-faqs)

## <a name="eap-troubleshooting"></a>Problemen met EAP oplossen
1. Controleer of Wi-Fi profiel de juiste instellingen heeft:
    - EAP-type is correct geconfigureerd, algemene EAP-typen: EAP-TLS (13), EAP-TTLS (21) en PEAP (25).
    - Wi-Fi SSID-naam is juist en komt overeen met HEX-tekenreeks.
    - Voor EAP-TLS bevat TrustedRootCA de SHA-1-hash van het vertrouwde basis-CA-certificaat van de server. Op Windows pc 'certutil.exe -dump cert_file_name'-opdracht wordt de SHA-1-hash-tekenreeks van een certificaat weer gegeven.
2. Verzamel netwerkpakketopname op de logboeken van het toegangspunt, de controller of de AAA-server om erachter te komen waar de EAP-sessie mislukt.
    - Als de EAP-identiteit die wordt geleverd door HoloLens niet wordt verwacht, controleert u of de identiteit correct is ingericht via Wi-Fi profiel of clientcertificaat.
    - Als de server het HoloLens clientcertificaat weigert, controleert u of het vereiste clientcertificaat is ingericht op het apparaat.
    - Als HoloLens servercertificaat weigert, controleert u of het basis-CA-certificaat van de server is ingericht op HoloLens.
3. Als het ondernemingsprofiel is ingericht via Wi-Fi inrichtingspakket, kunt u overwegen het inrichtingspakket toe te passen op een Windows 10 pc. Als dit ook mislukt op Windows 10 pc, volgt u de gids voor het oplossen van problemen Windows client 802.1X-verificatie.
4. Stuur ons feedback via Feedback-hub.

[Terug naar lijst](#list)

## <a name="wi-fi-troubleshooting"></a>Wi-Fi oplossen

Hier zijn enkele dingen die u kunt proberen als u uw HoloLens niet kunt verbinden met Wi-Fi netwerk:

1. Zorg ervoor dat Wi-Fi is ingeschakeld. Als u dit wilt controleren, gebruikt u de beweging Starten en selecteert u Instellingen > Network & Internet > Wi-Fi. Als Wi-Fi is aan, probeert u deze uit te schakelen en vervolgens weer aan.
2. Ga dichter bij de router of het toegangspunt zitten.
3. Start uw Wi-Fi router opnieuw op en start HoloLens. Probeer opnieuw verbinding te maken.
4. Als geen van deze dingen werkt, controleert u of uw router de meest recente firmware gebruikt. U vindt deze informatie op de website van de fabrikant.

Wanneer u zich op het apparaat bij een bedrijfs- of organisatieaccount aankeert, kan het ook MDM-beleid (Mobile Device Management) toepassen als het beleid is geconfigureerd door uw IT-beheerder.

[Terug naar lijst](#list)

## <a name="network-troubleshooting"></a>Problemen met het netwerk oplossen
Als netwerkproblemen een obstakel vormen voor het succesvol implementeren en gebruiken van HoloLens 2 in uw organisatie, configureert u Fiddler en/of Wireshark om HTTP/HTTPS-verkeer vast te leggen en te analyseren. 

### <a name="configure-fiddler-to-capture-http-traffic"></a>Fiddler configureren om HTTP-verkeer vast te leggen
Fiddler is een webdebuggingsproxy en wordt gebruikt om HTTP(S)-problemen op te lossen. Het legt elke HTTP-aanvraag vast die de computer maakt en registreert alles wat ermee is gekoppeld. Het blootleggen van verificatieproblemen voor uw HTTPS-apps zorgt voor een betere productiviteit en efficiëntie voor HoloLens 2 gebruiksgevallen. 

#### <a name="prerequisites"></a>Vereisten
 
- HoloLens 2 apparaten en uw pc moeten zich in hetzelfde netwerk
- Noteer het IP-adres van uw pc

#### <a name="install-and-configure-fiddler"></a>Fiddler installeren en configureren

1. Op uw pc: [installeer en](https://docs.telerik.com/fiddler-everywhere/get-started/installation-procedure) start Fiddler.  
1. Op uw pc: configureer Fiddler zodat externe computers verbinding kunnen maken.
    1. Ga naar Fiddler Instellingen -> Connections
    1. Let op de luisterpoort voor Fiddler (de standaardwaarde is 8866)
    1. Controleer Externe computers toestaan verbinding te maken
    1. Klik op Opslaan
3. Configureer fiddler HoloLens 2 proxyserver 1 op uw<sup>HoloLens 2:</sup>
    1. Open het Startmenu en selecteer Instellingen
    1. Selecteer Network & Internet en vervolgens Proxy in het menu links
    1. Schuif omlaag naar Handmatige proxy-installatie en stel Een proxyserver gebruiken in op Aan
    1. Voer het IP-adres in van de pc waarop Fiddler is geïnstalleerd
    1. Voer het poortnummer in dat u hierboven vermeldt (de standaardwaarde is 8866)
    1. Klik op Opslaan

<sup>1</sup> Voor builds 20279.1006+ (Insiders en de volgende release) gebruikt u de volgende stappen om de proxy te configureren:
1. Open de Startmenu en ga naar de Wi-Fi van uw netwerk 
1. Schuif omlaag naar Proxy
1. Wijzigen in Handmatige installatie
1. Voer het IP-adres in van de pc waarop Fiddler is geïnstalleerd
1. Voer het hierboven genoteerde poortnummer in. (de standaardwaarde is 8866)
1. Klik op Toepassen
    
#### <a name="decrypt-https-traffic-from-hololens-2"></a>HTTPS-verkeer ontsleutelen van HoloLens 2

1. Exporteert u het Fiddler-certificaat op uw pc.
    1. Ga naar Fiddler Instellingen -> HTTPS en vouw Geavanceerde Instellingen
    2. Klik op Fiddler-certificaat exporteren. Het wordt op uw bureaublad op slaan
    3. Verplaats het certificaat naar de map Downloads op uw HoloLens 2

2.  Importeer HoloLens 2 Fiddler-certificaat op uw HoloLens 2.
    1. Ga naar Instellingen -> Update and Security -> Certificates
    2. Klik op Certificaat installeren, blader naar de map Downloads en selecteer het Fiddler-certificaat
    3. Winkellocatie wijzigen in Lokale computer
    4. Certificaatopslag wijzigen in root
    5. Selecteer Installeren
    6. Controleer of het certificaat wordt weergegeven in de lijst met certificaten. Als dat niet het beste is, herhaalt u de bovenstaande stappen

#### <a name="inspect-https-sessions"></a>HTTP(S)-sessies inspecteren

Op uw pc geeft Fiddler de live HTTP(S)-sessies van de HoloLens 2 van de gebruiker weer. In het deelvenster Inspectors in Fiddler kunnen HTTP(S)-aanvragen/-antwoorden in verschillende weergaven worden weergegeven. In de weergave Onbewerkt ziet u bijvoorbeeld de onbewerkte aanvraag of het antwoord in tekst zonder tekst. 

### <a name="configure-wireshark-to-capture-network-traffic"></a>Wireshark configureren om netwerkverkeer vast te leggen
Wireshark is een netwerkprotocolanalyse en wordt gebruikt om TCP/UDP-verkeer van en naar uw HoloLens 2 inspecteren. Zo kunt u eenvoudig bepalen welk verkeer uw netwerk doorkruist naar uw HoloLens 2, hoeveel ervan, hoe vaak, hoeveel latentie er is tussen bepaalde hops, enzovoort.

#### <a name="prerequisites"></a>Vereisten:
- De pc moet internettoegang hebben en internet delen via Wi-Fi

#### <a name="install-and-configure-wireshark"></a>Wireshark installeren en configureren
1. Op uw pc - [Wireshark installeren](https://www.wireshark.org/#download) 
1. Op uw pc: schakel Mobiele hotspot in om uw internetverbinding via Wi-Fi te delen.
1. Op uw pc: start Wireshark en leg verkeer vast vanuit de interface voor mobiele hotspots. 
1. Op uw HoloLens 2 wijzigt u het Wi-Fi netwerk in de mobiele hotspot van de pc. HoloLens 2 IP-verkeer wordt in Wireshark weer geven.

#### <a name="analyze-wireshark-logs"></a>Wireshark-logboeken analyseren
Wireshark-filters kunnen helpen bij het filteren van de pakketten met interesses. 

Bekijk de oorspronkelijke [blog](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/diagnose-hololens-2-network-issues-with-fiddler-and-wireshark/ba-p/2322458).

[Terug naar lijst](#list)

## <a name="cant-sign-in-to-a-previously-setup-hololens-device"></a>Kan niet aanmelden bij een eerder ingesteld apparaat HoloLens apparaat

Als uw apparaat eerder is ingesteld voor iemand anders, voor een client of voor een voormalige werknemer, en u niet het [](/intune/remote-actions/devices-wipe) wachtwoord hebt om het apparaat te ontgrendelen, kunt u Intune gebruiken om het apparaat op afstand te wissen. Het apparaat flasht zichzelf vervolgens opnieuw.  
> [!IMPORTANT]
> Wanneer u het apparaat wist, zorg er dan voor dat Inschrijvingstoestand en gebruikersaccount **behouden** uitgeschakeld blijven.

[Terug naar lijst](#list)

## <a name="cant-login-after-updating-to-windows-holographic-21h1"></a>Kan niet aanmelden na het bijwerken naar Windows Holographic 21H1

### <a name="symptoms"></a>Symptomen
- Het gebruik van een pincode voor aanmelding mislukt nadat u de juiste pincode hebt invoeren.
- Het gebruik van de web-aanmeldingsmethode mislukt nadat u zich hebt aanmelden op de webpagina.
- Het apparaat wordt niet vermeld als 'Azure AD-toegevoegd' in [Azure Portal](https://portal.azure.com/) -> Azure Active Directory -> Devices.

### <a name="cause"></a>Oorzaak
Het beïnvloede apparaat is mogelijk verwijderd uit de Azure AD-tenant. Dit kan bijvoorbeeld gebeuren omdat:

- Een beheerder of gebruiker heeft het apparaat verwijderd in de Azure Portal of met behulp van PowerShell.
- Het apparaat is verwijderd uit de Azure AD-tenant vanwege inactiviteit. Voor een efficiënt beheerde omgeving raden we IT-beheerders doorgaans aan verouderde, inactieve apparaten uit hun [Azure AD-tenant te verwijderen.](/azure/active-directory/devices/manage-stale-devices)

Wanneer een beïnvloed apparaat opnieuw contact probeert te maken met de Azure AD-tenant nadat het is verwijderd, kan het apparaat niet worden geverifieerd bij Azure AD. Dit effect is vaak onzichtbaar voor de gebruiker van het apparaat, omdat aanmelding in de cache via een pincode de gebruiker blijft toestaan zich aan te geven.

### <a name="mitigation"></a>Oplossing
Er is momenteel geen manier om een verwijderd apparaat HoloLens toevoegen aan Azure AD. Betrokken apparaten moeten clean-reflashed worden door de instructies te volgen voor [het reflashen van hun apparaat.](hololens-recovery.md#clean-reflash-the-device)

[Terug naar lijst](#list)

## <a name="autopilot-troubleshooting"></a>Problemen met Autopilot oplossen

De volgende artikelen kunnen een handige resource zijn voor meer informatie en het oplossen van Autopilot-problemen. Houd er echter rekening mee dat deze artikelen zijn gebaseerd op Windows 10 Desktop en dat niet alle informatie van toepassing is op HoloLens:

- [Windows Autopilot - bekende problemen](/mem/autopilot/known-issues)
- [Problemen met inschrijving van Windows-apparaten in Microsoft Intune oplossen](/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [Windows Autopilot - Beleidsconflicten](/mem/autopilot/policy-conflicts)

[Terug naar lijst](#list)

## <a name="managed-hololens-devices-faqs"></a>Veelgestelde HoloLens managed HoloLens Devices

### <a name="can-i-use-system-center-configuration-manager-sccm-to-manage-hololens-devices"></a>Kan ik System Center Configuration Manager (SCCM) gebruiken om uw HoloLens beheren?

Nee. U moet een MDM-systeem gebruiken om uw apparaten HoloLens beheren.

### <a name="can-i-use-active-directory-domain-services-ad-ds-to-manage-hololens-user-accounts"></a>Kan ik Active Directory Domain Services (AD DS) gebruiken voor het beheren HoloLens gebruikersaccounts?

Nee. U moet een Azure Active Directory (Azure AD) gebruiken om gebruikersaccounts voor HoloLens beheren.

### <a name="is-hololens-capable-of-automated-data-capture-systems-adcs-auto-enrollment"></a>Is HoloLens automatische inschrijving van Automated Data Capture Systems (ADCS) mogelijk?

Nee.

### <a name="can-hololens-participate-in-integrated-windows-authentication"></a>Kan HoloLens deelnemen aan geïntegreerde Windows-verificatie?

Nee.

### <a name="does-hololens-support-branding"></a>Biedt HoloLens ondersteuning voor huisstijl?

Nee. U kunt dit probleem echter oplossen met behulp van een van de volgende methoden:

- Maak een aangepaste app en schakel vervolgens [kioskmodus in.](hololens-kiosk.md) De aangepaste app kan een huisstijl hebben en kan andere apps starten (zoals Remote Assist).  
- Wijzig alle gebruikersprofielfoto's in Azure AD in uw bedrijfslogo. Dit is echter mogelijk niet wenselijk voor alle scenario's.

### <a name="what-logging-capabilities-does-hololens-2-offer"></a>Welke logboekregistratiemogelijkheden biedt HoloLens 2 bieden?

Logboekregistratie is beperkt tot traceringen die kunnen worden vastgelegd in ontwikkel- of probleemoplossingsscenario's, of telemetrie die de apparaten naar Microsoft-servers verzenden.

## <a name="questions-about-securing-hololens-devices"></a>Vragen over het beveiligen HoloLens apparaten

Zie [onze HoloLens 2 beveiligingsinformatie](security-overview.md).
Raadpleeg HoloLens veelgestelde vragen voor meer informatie over apparaten uit [de eerste generatie.](hololens1-faq-security.yml)

[Terug naar lijst](#list)
