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
# <a name="troubleshooting-implementation-and-managed-devices"></a>Problemen met implementatie en beheerde apparaten oplossen 

In dit artikel wordt beschreven hoe u verschillende problemen kunt oplossen of vragen kunt beantwoorden met betrekking tot de implementatie en het beheer van HoloLens 2.

>[!IMPORTANT]
> Voordat u een probleemoplossingsprocedure start, moet u ervoor zorgen dat uw apparaat, indien mogelijk, wordt geladen op **20 tot 40** procent van de accucapaciteit. De [accuindicatorlichten onder](hololens2-setup.md#lights-that-indicate-the-battery-level) de aan/uit-knop zijn een snelle manier om de accucapaciteit te controleren zonder u aan te melden bij het apparaat.


<a id="list"></a>
- [Problemen met EAP oplossen](#eap-troubleshooting)
- [Problemen met Wi-Fi oplossen](#wi-fi-troubleshooting)
- [Problemen met het netwerk oplossen](#network-troubleshooting)
- [Kan niet aanmelden bij een eerder ingesteld HoloLens-apparaat](#cant-sign-in-to-a-previously-setup-hololens-device)
- [Kan niet aanmelden na het bijwerken naar Windows Holographic 21H1](#cant-login-after-updating-to-windows-holographic-21h1)
- [Problemen met Autopilot oplossen](#autopilot-troubleshooting)
- [Veelgestelde vragen over beheerde HoloLens-apparaten](#managed-hololens-devices-faqs)

## <a name="eap-troubleshooting"></a>Problemen met EAP oplossen
1. Controleer of Wi-Fi profiel de juiste instellingen heeft:
    - EAP-type is correct geconfigureerd, algemene EAP-typen: EAP-TLS (13), EAP-TTLS (21) en PEAP (25).
    - Wi-Fi SSID-naam juist is en overeenkomt met HEX-tekenreeks.
    - Voor EAP-TLS bevat TrustedRootCA de SHA-1-hash van het vertrouwde basis-CA-certificaat van de server. Op Windows-pc 'certutil.exe -dump cert_file_name'-opdracht wordt de SHA-1-hash-tekenreeks van een certificaat weer gegeven.
2. Verzamel netwerkpakketopname op de logboeken van het toegangspunt, de controller of de AAA-server om erachter te komen waar de EAP-sessie mislukt.
    - Als de EAP-identiteit die wordt geleverd door HoloLens niet wordt verwacht, controleert u of de identiteit correct is ingericht via Wi-Fi-profiel of clientcertificaat.
    - Als de server het HoloLens-clientcertificaat weigert, controleert u of het vereiste clientcertificaat is ingericht op het apparaat.
    - Als HoloLens het servercertificaat weigert, controleert u of het basis-CA-certificaat voor de server is ingericht op HoloLens.
3. Als het ondernemingsprofiel is ingericht via Wi-Fi inrichtingspakket, kunt u overwegen het inrichtingspakket toe te passen op een Windows 10 pc. Als dit ook mislukt op Windows 10 pc, volgt u de probleemoplossingsgids voor Windows-client 802.1X-verificatie.
4. Stuur ons feedback via Feedback-hub.

[Terug naar lijst](#list)

## <a name="wi-fi-troubleshooting"></a>Wi-Fi oplossen

Hier zijn enkele dingen die u kunt proberen als u uw HoloLens niet kunt verbinden met Wi-Fi netwerk:

1. Zorg ervoor dat Wi-Fi is ingeschakeld. Als u dit wilt controleren, gebruikt u de beweging Starten en selecteert u vervolgens Instellingen > Netwerk & Internet > Wi-Fi. Als Wi-Fi is aan, probeert u deze uit te schakelen en vervolgens weer aan.
2. Ga dichter bij de router of het toegangspunt zitten.
3. Start uw Wi-Fi en start HoloLens opnieuw. Probeer opnieuw verbinding te maken.
4. Als geen van deze dingen werkt, controleert u of uw router de meest recente firmware gebruikt. U vindt deze informatie op de website van de fabrikant.

Wanneer u zich op het apparaat bij een bedrijfs- of organisatieaccount aankeert, kan het ook MDM-beleid (Mobile Device Management) toepassen als het beleid is geconfigureerd door uw IT-beheerder.

## <a name="network-troubleshooting"></a>Problemen met het netwerk oplossen
Als netwerkproblemen een obstakel vormen voor het succesvol implementeren en gebruiken van HoloLens 2 in uw organisatie, leert u hoe u met twee bekende hulpprogramma's voor netwerkdiagnose, Fiddler en Wireshark, problemen kunt scannen, diagnosticeren en identificeren. Bekijk dit [blog voor](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/diagnose-hololens-2-network-issues-with-fiddler-and-wireshark/ba-p/2322458) meer informatie.

[Terug naar lijst](#list)

## <a name="cant-sign-in-to-a-previously-setup-hololens-device"></a>Kan niet aanmelden bij een eerder ingesteld HoloLens-apparaat

Als uw apparaat eerder is ingesteld voor iemand anders, voor een client of voor een voormalige werknemer, en u geen wachtwoord [](https://docs.microsoft.com/intune/remote-actions/devices-wipe) hebt om het apparaat te ontgrendelen, kunt u Intune gebruiken om het apparaat op afstand te wissen. Het apparaat wordt vervolgens opnieuw geflitst.  
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
- Het apparaat is verwijderd uit de Azure AD-tenant vanwege inactiviteit. Voor een efficiënt beheerde omgeving raden we IT-beheerders doorgaans aan verouderde, inactieve apparaten uit hun [Azure AD-tenant te verwijderen.](https://docs.microsoft.com/azure/active-directory/devices/manage-stale-devices)

Wanneer een beïnvloed apparaat opnieuw contact probeert op te nemen met de Azure AD-tenant nadat het is verwijderd, mislukt de verificatie bij Azure AD. Dit effect is vaak onzichtbaar voor de gebruiker van het apparaat, omdat aanmelding in de cache via een pincode de gebruiker blijft toestaan zich aan te geven.

### <a name="mitigation"></a>Oplossing
Er is momenteel geen manier om een verwijderd HoloLens-apparaat weer toe te voegen aan Azure AD. Betrokken apparaten moeten clean reflashed worden door de instructies te volgen voor [het reflashen van hun apparaat.](hololens-recovery.md#clean-reflash-the-device)

## <a name="autopilot-troubleshooting"></a>Problemen met Autopilot oplossen

De volgende artikelen kunnen een nuttige informatiebron zijn voor meer informatie en het oplossen van Autopilot-problemen. Houd er echter rekening mee dat deze artikelen zijn gebaseerd op Windows 10 Desktop en dat niet alle informatie van toepassing is op HoloLens:

- [Windows Autopilot- bekende problemen](https://docs.microsoft.com/mem/autopilot/known-issues)
- [Problemen met inschrijving van Windows-apparaten in Microsoft Intune oplossen](https://docs.microsoft.com/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [Windows Autopilot - Beleidsconflicten](https://docs.microsoft.com/mem/autopilot/policy-conflicts)

## <a name="managed-hololens-devices-faqs"></a>Veelgestelde vragen over beheerde HoloLens-apparaten

### <a name="can-i-use-system-center-configuration-manager-sccm-to-manage-hololens-devices"></a>Kan ik System Center Configuration Manager (SCCM) gebruiken om HoloLens-apparaten te beheren?

Nee. U moet een MDM-systeem gebruiken om HoloLens-apparaten te beheren.

### <a name="can-i-use-active-directory-domain-services-ad-ds-to-manage-hololens-user-accounts"></a>Kan ik Active Directory Domain Services (AD DS) gebruiken om HoloLens-gebruikersaccounts te beheren?

Nee. U moet een Azure Active Directory (Azure AD) gebruiken om gebruikersaccounts voor HoloLens-apparaten te beheren.

### <a name="is-hololens-capable-of-automated-data-capture-systems-adcs-auto-enrollment"></a>Is HoloLens geschikt voor automatische ADCS-inschrijving (Automated Data Capture Systems)?

Nee.

### <a name="can-hololens-participate-in-integrated-windows-authentication"></a>Kan HoloLens deelnemen aan Geïntegreerde Windows-verificatie?

Nee.

### <a name="does-hololens-support-branding"></a>Ondersteunt HoloLens de huisstijl?

Nee. U kunt dit probleem echter op een van de volgende manieren oplossen:

- Maak een aangepaste app en schakel vervolgens [kioskmodus in.](hololens-kiosk.md) De aangepaste app kan een huisstijl hebben en kan andere apps starten (zoals Remote Assist).  
- Wijzig alle gebruikersprofielfoto's in Azure AD in uw bedrijfslogo. Dit is echter mogelijk niet wenselijk voor alle scenario's.

### <a name="what-logging-capabilities-does-hololens-2-offer"></a>Welke logboekregistratiemogelijkheden biedt HoloLens 2 bieden?

Logboekregistratie is beperkt tot traceringen die kunnen worden vastgelegd in ontwikkel- of probleemoplossingsscenario's, of telemetrie die de apparaten naar Microsoft-servers verzenden.

## <a name="questions-about-securing-hololens-devices"></a>Vragen over het beveiligen van HoloLens-apparaten

Zie [onze HoloLens 2 beveiligingsgegevens](security-overview.md).
Raadpleeg deze veelgestelde vragen voor HoloLens 1st [Gen-apparaten.](hololens1-faq-security.md)

[Terug naar lijst](#list)
