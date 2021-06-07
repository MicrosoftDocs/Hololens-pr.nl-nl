---
title: Diagnostische gegevens van HoloLens-apparaten verzamelen en gebruiken
description: Informatie over het verzamelen, gebruiken en bewaren van diagnostische gegevens van HoloLens-apparaten.
author: Teresa-Motiv
ms.author: v-tea
ms.date: 10/15/2020
ms.prod: hololens
ms.mktglfcycl: manage
ms.sitesec: library
ms.topic: article
ms.custom:
- CI 115131
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: medium
keywords: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: c1d5205d4faa4384600c489167c9581de8e4b62c
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/25/2021
ms.locfileid: "111377919"
---
# <a name="collect-and-use-diagnostic-information-from-hololens-devices"></a>Diagnostische gegevens van HoloLens-apparaten verzamelen en gebruiken

HoloLens-gebruikers en -beheerders kunnen kiezen uit vier verschillende methoden om diagnostische gegevens van HoloLens te verzamelen:

- Feedback-hub app
- DiagnosticLog-CSP
- App Instellingen
- Offlinediagnose

> [!IMPORTANT]  
> Diagnostische logboeken van apparaten bevatten persoonsgegevens, zoals over welke processen of toepassingen de gebruiker tijdens normale bewerkingen start. Wanneer meerdere gebruikers een HoloLens-apparaat delen (bijvoorbeeld wanneer gebruikers zich aanmelden bij hetzelfde apparaat met behulp van verschillende Microsoft Azure Active Directory-accounts (Azure AD), kunnen de diagnostische logboeken PII-gegevens bevatten die van toepassing zijn op meerdere gebruikers. Zie Privacyverklaring van [Microsoft voor meer informatie.](https://privacy.microsoft.com/privacystatement)

In de volgende tabel worden verschillende verzamelingsmethoden vergeleken. De methodenamen zijn gekoppeld aan gedetailleerdere informatie in de secties die volgen op de tabel.

|Methode |Vereisten |Gegevenslocaties |Gegevenstoegang en -gebruik |Gegevensretentie |
| --- | --- | --- | --- | --- |
|[Feedback-hub](#feedback-hub) |Netwerk- en internetverbinding<br /><br />Feedback-hub app<br /><br />Machtiging voor het uploaden van bestanden naar de Microsoft-cloud |Microsoft Cloud<br /><br />HoloLens-apparaat (optioneel) |Gebruiker vraagt hulp, gaat akkoord met de gebruiksvoorwaarden en uploadt de gegevens<br /><br />Microsoft-medewerkers bekijken de gegevens, overeenkomstig de gebruiksvoorwaarden |Gegevens in de cloud worden bewaard voor de periode die is gedefinieerd door NGP (Next Generation Privacy). Vervolgens worden de gegevens automatisch verwijderd.<br /><br />Gegevens op het apparaat kunnen op elk moment  worden verwijderd door een gebruiker met de machtiging Apparaateigenaar **of** Beheerder. |
|[Probleemoplosser voor instellingen](#settings-troubleshooter) |App Instellingen |HoloLens-apparaat<br /><br />Verbonden computer (optioneel) |De gebruiker slaat de gegevens op en alleen de gebruiker heeft toegang tot de gegevens (tenzij de gebruiker de gegevens specifiek deelt met een andere gebruiker). |De gegevens worden bewaard op het apparaat totdat de gebruiker deze verwijdert.* |
|[DiagnosticLog-CSP](#diagnosticlog-csp) |Netwerkverbinding<br /><br />MDM-omgeving die ondersteuning biedt voor de DiagnosticLog-CSP |Beheerder configureert opslaglocaties |In de beheerde omgeving geeft de gebruiker impliciet beheerderstoegang tot de gegevens.<br /><br />De beheerder configureert toegangsrollen en -machtigingen. | Gegevens worden bewaard in de cloudopslag en de beheerder configureert het bewaarbeleid. |
|[Offlinediagnose](#offline-diagnostics) |Apparaatconfiguratie:<ul><li>Ingeschakeld en verbonden met computer</li><li>Aan/ en volumeknoppen werken</li></ul> |HoloLens-apparaat<br /><br />Verbonden computer |De gebruiker slaat de gegevens op en alleen de gebruiker heeft toegang tot de gegevens (tenzij de gebruiker de gegevens specifiek deelt met een andere gebruiker). |De gegevens worden bewaard op het apparaat totdat de gebruiker deze verwijdert. |

* De eindgebruiker is verantwoordelijk voor het op verantwoorde wijze delen van de logboeken met iemand anders. Deze bestanden zijn voornamelijk nuttig bij het contact opnemen met de klantenservice en ondersteuning.  

## <a name="feedback-hub"></a>Feedback-hub

Een HoloLens-gebruiker kan de Microsoft Feedback-hub desktop-app gebruiken om diagnostische gegevens naar de Microsoft-ondersteuning. Zie Feedback geven voor meer informatie en [volledige instructies.](hololens-feedback.md)  

> [!NOTE]  
> **Commerciële of zakelijke gebruikers:** Als u de Feedback-hub-app gebruikt om een probleem te melden dat betrekking heeft op MDM, inrichting of een ander aspect van apparaatbeheer, wijzigt u de app-categorie in De categorie  >  **Bedrijfsbeheerapparaat.**

>[!IMPORTANT]
> Als u de best mogelijke gegevens wilt bieden voor het oplossen van problemen, raden we u ten zeerste aan de telemetrie van uw apparaat in te stellen op **Optioneel.** U kunt deze waarde instellen tijdens de OOBE (Out-of-Box-Experience) of met behulp van **de** app Instellingen. Als u dit wilt doen met behulp van Instellingen, selecteert u **> Instellingen > Privacy > App Diagnostics > Op**.
### <a name="prerequisites"></a>Vereisten

- Het apparaat is verbonden met een netwerk.
- De Feedback-hub-app is beschikbaar op de desktopcomputer van de gebruiker en de gebruiker kan bestanden uploaden naar de Microsoft-cloud.

### <a name="data-locations-access-and-retention"></a>Gegevenslocaties, toegang en retentie

Door akkoord te gaan met de gebruiksvoorwaarden van de Feedback-hub, geeft de gebruiker expliciet toestemming voor de opslag en het gebruik van de gegevens (zoals gedefinieerd in die overeenkomst).

De Feedback-hub biedt de gebruiker twee locaties voor het opslaan van diagnostische gegevens:

- **De Microsoft Cloud.** Gegevens die de gebruiker uploadt met behulp van de Feedback-hub-app, worden opgeslagen voor het aantal dagen dat consistent is met de NGP-vereisten (Next Generation Privacy). Microsoft-medewerkers kunnen een NGP-compatibele viewer gebruiken voor toegang tot de informatie gedurende deze periode.

   > [!NOTE]  
   > Deze vereisten zijn van toepassing op gegevens in Feedback-hub categorieën.

- **Het HoloLens-apparaat**. Tijdens het indienen van een rapport in Feedback-hub, kan de gebruiker Een lokale kopie van diagnostische gegevens en bijlagen opslaan selecteren die zijn gemaakt bij **het geven van feedback.** Als de gebruiker deze optie selecteert, slaat Feedback-hub een kopie van de diagnostische gegevens op het HoloLens-apparaat op. Deze informatie blijft toegankelijk voor de gebruiker (of iedereen die dat account gebruikt om zich aan te melden bij HoloLens). Als u deze informatie wilt verwijderen, moet een gebruiker de machtiging **Apparaateigenaar** of **Beheerder** hebben op het apparaat. Een gebruiker met de juiste machtigingen kan zich aanmelden bij de Feedback-hub, instellingen Diagnostische logboeken weergeven selecteren en  >  de informatie verwijderen.

## <a name="settings-troubleshooter"></a>Probleemoplosser voor instellingen

Een HoloLens-gebruiker kan de app **Instellingen op** het apparaat gebruiken om problemen op te lossen en diagnostische gegevens te verzamelen. Voer hiervoor de volgende stappen uit:

1. Open de app Instellingen en selecteer **Update & pagina**  >  **Beveiligingsproblemen** oplossen.
1. Selecteer het juiste gebied en selecteer **Starten.**
1. Reproduceer het probleem.
1. Nadat u het probleem hebt gereproduceerd, gaat u terug naar Instellingen en selecteert u **vervolgens Stoppen.**

Een gebruiker kan ook het gedrag van Terugvaldiagnose configureren vanuit **de** app Instellingen. **Navigeer naar de > Privacy om** deze instelling te configureren.
> [!NOTE]
> Als er MDM-beleid is geconfigureerd voor het apparaat, kan de gebruiker dat gedrag niet overschrijven.

### <a name="os-update-troubleshooter"></a>Probleemoplosser voor besturingssysteemupdates
Op builds [van Windows Holographic, versie 21H1 ](hololens-release-notes.md#windows-holographic-version-21h1) en meer:
- Naast de vorige probleemoplossers in de app Instellingen is er een nieuwe probleemoplosser toegevoegd met de toevoeging van de nieuwe app Instellingen voor updates van het besturingssysteem. **Navigeer naar Instellingen -> Update & Security -> Troubleshoot -> Windows Update** en selecteer **Start.** Hiermee kunt u traceringen verzamelen tijdens het reproduceren van uw probleem met updates van het besturingssysteem, zodat u beter kunt helpen bij het oplossen van problemen met uw IT of ondersteuning.
### <a name="prerequisites"></a>Vereisten

- De **app** Instellingen is geïnstalleerd op het apparaat en is beschikbaar voor de gebruiker.

### <a name="data-locations-access-and-retention"></a>Gegevenslocaties, toegang en retentie

Omdat de gebruiker de gegevensverzameling start, geeft de gebruiker impliciet toestemming voor de opslag van de diagnostische gegevens. Alleen de gebruiker, of iemand met wie de gebruiker de gegevens deelt, heeft toegang tot de gegevens.

De diagnostische gegevens worden opgeslagen op het apparaat. Als het apparaat is verbonden met de computer van de gebruiker, bevindt de informatie zich ook op de computer in het volgende bestand:

> Deze pc \\ \<*HoloLens device name*> \\ interne opslag documenten \\ trace \\ \<*ddmmyyhhmmss*> .etl

> [!NOTE]  
> In dit bestandspad en de naam vertegenwoordigt de naam van het HoloLens-apparaat en de datum en tijd \<*HoloLens device name*> waarop het bestand is \<*ddmmyyhhmmss*> gemaakt.

De diagnostische gegevens blijven op deze locaties totdat de gebruiker deze verwijdert.

## <a name="diagnosticlog-csp"></a>DiagnosticLog-CSP

In een MDM-omgeving (Mobile Device Management) kan de IT-beheerder de DiagnosticLog-configuratieserviceprovider [(CSP)](https://docs.microsoft.com/windows/client-management/mdm/diagnosticlog-csp) gebruiken om diagnostische instellingen te configureren op ingeschreven HoloLens-apparaten. De IT-beheerder kan deze instellingen configureren voor het verzamelen van logboeken van ingeschreven apparaten.

Meer informatie:
- [Diagnostische gegevens verzamelen van een Windows-apparaat](https://docs.microsoft.com/mem/intune/remote-actions/collect-diagnostics)
- [Openbare preview-versie van Intune - Windows 10 diagnostische gegevens van apparaten](https://techcommunity.microsoft.com/t5/intune-customer-success/intune-public-preview-windows-10-device-diagnostics/ba-p/2179712#:~:text=This%20first%20release%20of%20device%20diagnostics%20utilizes%20the,taking%20about%205%20minutes%20from%20start%20to%20finish.)

### <a name="prerequisites"></a>Vereisten

- Het apparaat is verbonden met een netwerk.
- Het apparaat is ingeschreven in een MDM-omgeving die ondersteuning biedt voor de DiagnosticLog-CSP.

### <a name="data-locations-access-and-retention"></a>Gegevenslocaties, toegang en retentie

Omdat het apparaat deel uitmaakt van de beheerde omgeving, geeft de gebruiker impliciet toestemming voor beheerderstoegang tot diagnostische gegevens.

De IT-beheerder gebruikt de DiagnosticLog-CSP om het beleid voor gegevensopslag, -retentie en -toegang te configureren, met inbegrip van de beleidsregels die van toepassing zijn op het volgende:

- De cloudinfrastructuur die de diagnostische gegevens opgeslagen.
- De bewaarperiode voor de diagnostische gegevens.
- Machtigingen die de toegang tot de diagnostische gegevens bepalen.

## <a name="offline-diagnostics"></a>Offlinediagnose
In situaties waarin het apparaat geen diagnostische gegevens kan verzamelen via Feedback-hub of de probleemoplosser voor instellingen, kunt u diagnostische gegevens handmatig verzamelen. Een scenario waarin dit nodig is, is wanneer het apparaat geen verbinding kan maken met Wi-Fi of wanneer u geen toegang hebt tot andere hierboven genoemde methoden. De diagnostische gegevens verzamelen crashdumps en logboeken van het apparaat die een Ondersteuningstechnicus van Microsoft helpen bij het isoleren van problemen.

Dit werkt wanneer het apparaat wordt weergegeven in Verkenner nadat het via een USB-kabel is verbonden met een pc.

> [!NOTE]
> Het genereren en beheren van offlinediagnose wordt anders beheerd, afhankelijk van de versie van uw besturingssysteem. Voorheen werd dit beheerd door de telemetrie-instelling, maar wordt nu rechtstreeks beheerd via MDM-beleid. Als deze is uitgeschakeld via een instellings- of MDM-beleid, kunnen diagnostische logboeken niet worden verzameld met behulp van dit mechanisme.

Gedrag vóór [Windows Holographic, versie 20H2:](hololens-release-notes.md#windows-holographic-version-20h2)
 - Offlinediagnose is alleen ingeschakeld wanneer de gebruiker oobe of de beleidswaarde [System\AllowTelemetry](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry) doormaakt, is ingesteld op Volledig (Basic is de standaardwaarde op HoloLens). 
- Als u Offlinediagnose wilt uitschakelen, gaat u naar De > **Privacy** en selecteert u **Basis** in **Diagnostische gegevens.** Op builds waarbij offlinediagnose afhankelijk is van de telemetrie-instelling, heeft dit alleen invloed op het al dan niet verzamelen van logboeken. Het heeft geen invloed op welke bestanden worden verzameld.
- Als het apparaat is vergrendeld, worden er geen logboeken weergegeven.

Op builds [van Windows Holographic, versie 20H2](hololens-release-notes.md#windows-holographic-version-20h2) en hoger:
- Wanneer Terugvaldiagnose is ingeschakeld, wordt beheerd door een specifiek MDM-beleid met de bijbehorende instelling [MixedReality/FallbackDiagnostics](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-mixedreality#mixedreality-fallbackdiagnostics)
- Als het apparaat is vergrendeld, worden er geen logboeken weergegeven.

Bekijk deze video voor meer informatie.

> [!VIDEO https://channel9.msdn.com/Shows/Docs-Mixed-Reality/Gathering-Diagnostic-Files-on-HoloLens2/player]

Volg deze stappen om diagnostische gegevens te verzamelen:
1.  Sluit het apparaat met een USB-kabel aan op uw pc.
2.  Navigeer in Verkenner op uw pc naar **'Deze pc \<hololens-device> \Interne opslag'.**
3.  Als de **map Interne** opslag niet wordt weergeven, wacht het apparaat tot een gebruiker zich heeft aanmelden. U kunt het apparaat aanmelden of het apparaat aan-/uit-zetten door de AAN/uit-knop tien seconden ingedrukt te houden.
4.  Druk op de knoppen **Power + Volume Down** en laat deze direct los.
5.  Wacht een minuut totdat het apparaat de ZIP-archieven heeft voorbereid. (Een tijdelijk bestand met de naam HololensDiagnostics.temp kan zichtbaar worden terwijl het apparaat de ZIP-archieven genereert. U kunt dit bestand niet openen of opslaan. Wanneer het proces is voltooien, wordt het vervangen door de ZIP-archieven.)
6.  Vernieuw Verkenner en navigeer naar de map **\Documents.**
7.  Kopieer de ZIP-bestanden voor diagnostische gegevens en deel deze met het ondersteuningsteam van Microsoft.

> [!NOTE]
> Sommige diagnostische ZIP-bestanden kunnen PII bevatten.
