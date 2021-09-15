---
title: Diagnostische gegevens verzamelen en gebruiken van HoloLens apparaten
description: Meer informatie over het verzamelen, gebruiken en bewaren van diagnostische gegevens van HoloLens apparaten.
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
ms.openlocfilehash: 2cbf3005293f4fde91b22f3ff87edc6041e53336
ms.sourcegitcommit: 16897df83c309acecf04e2bcfea310891cb6681b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/15/2021
ms.locfileid: "127817273"
---
# <a name="collect-and-use-diagnostic-information-from-hololens-devices"></a>Diagnostische gegevens verzamelen en gebruiken van HoloLens apparaten

HoloLens gebruikers en beheerders kunnen kiezen uit vier verschillende methoden voor het verzamelen van diagnostische gegevens van HoloLens:

- Feedback-hub app
- DiagnosticLog-CSP
- Instellingen app
- Offlinediagnose

> [!IMPORTANT]  
> Diagnostische logboeken van apparaten bevatten persoonlijk identificeerbare informatie (PII), zoals over welke processen of toepassingen de gebruiker start tijdens typische bewerkingen. Wanneer meerdere gebruikers een HoloLens-apparaat delen (bijvoorbeeld wanneer gebruikers zich op hetzelfde apparaat aanmelden met behulp van verschillende Microsoft Azure Active Directory-accounts (Azure AD), kunnen de diagnostische logboeken PII-gegevens bevatten die van toepassing zijn op meerdere gebruikers. Zie Privacyverklaring van [Microsoft voor meer informatie.](https://privacy.microsoft.com/privacystatement)

In de volgende tabel worden verschillende verzamelingsmethoden vergeleken. De namen van de methoden zijn gekoppeld aan gedetailleerdere informatie in de secties na de tabel.

|Methode |Vereisten |Gegevenslocaties |Gegevenstoegang en -gebruik |Gegevensretentie |
| --- | --- | --- | --- | --- |
|[Feedback-hub](#feedback-hub) |Netwerk- en internetverbinding<br /><br />Feedback-hub app<br /><br />Machtiging voor het uploaden van bestanden naar de Microsoft-cloud |Microsoft Cloud<br /><br />HoloLens (optioneel) |De gebruiker vraagt om hulp, gaat akkoord met de gebruiksvoorwaarden en uploadt de gegevens<br /><br />Microsoft-medewerkers bekijken de gegevens, overeenkomstig de gebruiksvoorwaarden |Gegevens in de cloud worden bewaard voor de periode die is gedefinieerd door NGP (Next Generation Privacy). Vervolgens worden de gegevens automatisch verwijderd.<br /><br />Gegevens op het apparaat kunnen op elk moment  worden verwijderd door een gebruiker met de machtiging Apparaateigenaar **of** Beheerder. |
|[Instellingen Probleemoplosser](#settings-troubleshooter) |Instellingen app |HoloLens-apparaat<br /><br />Verbonden computer (optioneel) |De gebruiker slaat de gegevens op en alleen de gebruiker heeft toegang tot de gegevens (tenzij de gebruiker de gegevens specifiek deelt met een andere gebruiker). |De gegevens worden bewaard op het apparaat totdat de gebruiker deze verwijdert.* |
|[DiagnosticLog-CSP](#diagnosticlog-csp) |Netwerkverbinding<br /><br />MDM-omgeving die ondersteuning biedt voor de DiagnosticLog-CSP |Beheerder configureert opslaglocaties |In de beheerde omgeving geeft de gebruiker impliciet toestemming voor beheerderstoegang tot de gegevens.<br /><br />De beheerder configureert toegangsrollen en -machtigingen. | Gegevens worden bewaard in de cloudopslag en de beheerder configureert het bewaarbeleid. |
|[Offlinediagnose](#offline-diagnostics) |Apparaatconfiguratie:<ul><li>Ingeschakeld en verbonden met computer</li><li>Aan/uit- en volumeknoppen werken</li></ul> |HoloLens-apparaat<br /><br />Verbonden computer |De gebruiker slaat de gegevens op en alleen de gebruiker heeft toegang tot de gegevens (tenzij de gebruiker de gegevens specifiek deelt met een andere gebruiker). |De gegevens worden bewaard op het apparaat totdat de gebruiker deze verwijdert. |

* De eindgebruiker is verantwoordelijk voor het op verantwoorde wijze delen van de logboeken met iemand anders. Deze bestanden zijn voornamelijk nuttig bij het contact opnemen met de klantenservice en ondersteuning.  

## <a name="feedback-hub"></a>Feedback-hub

Een HoloLens kan de Microsoft Feedback-hub desktop-app gebruiken om diagnostische gegevens naar de Microsoft-ondersteuning. Zie Feedback geven voor meer informatie en [volledige instructies.](hololens-feedback.md)  

> [!NOTE]  
> **Commerciële of zakelijke gebruikers:** Als u de Feedback-hub-app gebruikt om een probleem te melden dat betrekking heeft op MDM, inrichting of een ander aspect van apparaatbeheer, wijzigt u de categorie van de app in de categorie Enterprise **Management**  >  **Device.**

>[!IMPORTANT]
> Als u de best mogelijke gegevens wilt bieden voor het oplossen van problemen, raden we u ten zeerste aan de telemetrie van uw apparaat in te stellen op **Optioneel.** U kunt deze waarde instellen tijdens de OUT-of-Box-Experience  (OOBE) of met behulp van de Instellingen app. Als u dit wilt doen met behulp Instellingen, selecteert u **> Instellingen > Privacy > App Diagnostics > Op**.

### <a name="prerequisites"></a>Vereisten

- Het apparaat is verbonden met een netwerk.
- De Feedback-hub-app is beschikbaar op de desktopcomputer van de gebruiker en de gebruiker kan bestanden uploaden naar de Microsoft Cloud.

### <a name="data-locations-access-and-retention"></a>Gegevenslocaties, toegang en retentie

Door akkoord te gaan met de gebruiksvoorwaarden van de Feedback-hub, geeft de gebruiker expliciet toestemming voor de opslag en het gebruik van de gegevens (zoals gedefinieerd in die overeenkomst).

De Feedback-hub biedt twee locaties voor de gebruiker om diagnostische gegevens op te slaan:

- **De Microsoft Cloud.** Gegevens die de gebruiker uploadt met behulp van de Feedback-hub-app worden opgeslagen voor het aantal dagen dat consistent is met de NGP-vereisten (Next Generation Privacy). Microsoft-medewerkers kunnen gedurende deze periode een viewer gebruiken die compatibel is met NGP om toegang te krijgen tot de informatie.

   > [!NOTE]  
   > Deze vereisten zijn van toepassing op gegevens in Feedback-hub categorieën.

- **Het HoloLens apparaat**. Tijdens het indienen van een rapport in Feedback-hub, kan de gebruiker Een lokale kopie van diagnostische gegevens en bijlagen opslaan selecteren die zijn gemaakt bij **het geven van feedback.** Als de gebruiker deze optie selecteert, slaat Feedback-hub een kopie van de diagnostische gegevens op het HoloLens op. Deze informatie blijft toegankelijk voor de gebruiker (of iedereen die dat account gebruikt om zich aan te melden bij HoloLens). Als u deze informatie wilt verwijderen, moet een gebruiker de machtiging **Apparaateigenaar** **of** Beheerder hebben op het apparaat. Een gebruiker met de juiste machtigingen kan zich aanmelden bij de Feedback-hub, Instellingen Diagnostische logboeken weergeven selecteren en de  >  informatie verwijderen.

## <a name="settings-troubleshooter"></a>Instellingen Probleemoplosser

Een HoloLens kan de app **Instellingen** op het apparaat gebruiken om problemen op te lossen en diagnostische gegevens te verzamelen. Voer hiervoor de volgende stappen uit:

1. Open de Instellingen app en selecteer **de pagina &**  >  **Beveiligingsproblemen** bijwerken.
1. Selecteer het juiste gebied en selecteer **Starten.**
1. Reproduceer het probleem.
1. Nadat u het probleem hebt gereproduceerd, gaat u Instellingen selecteert u **Stoppen.**

Een gebruiker kan ook het gedrag van  Terugvaldiagnose configureren vanuit de Instellingen app. Ga naar **de pagina Privacy -> probleemoplossing** om deze instelling te configureren.
> [!NOTE]
> Als er MDM-beleid is geconfigureerd voor het apparaat, kan de gebruiker dat gedrag niet overschrijven.

### <a name="os-update-troubleshooter"></a>Probleemoplosser voor besturingssysteemupdates
Op builds [Windows Holographic, versie 21H1](hololens-release-notes.md#windows-holographic-version-21h1) en meer:
- Naast de vorige probleemoplossers in de Instellingen-app, is er een nieuwe probleemoplosser toegevoegd met de toevoeging van de nieuwe Instellingen-app voor updates van het besturingssysteem. **Navigeer naar Instellingen -> Update & Security -> Troubleshoot -> Windows Update** en selecteer **Start.** Hiermee kunt u traceringen verzamelen tijdens het reproduceren van uw probleem met updates van het besturingssysteem, zodat u beter kunt helpen bij het oplossen van problemen met uw IT of ondersteuning.

### <a name="prerequisites"></a>Vereisten

- De **Instellingen-app** is geïnstalleerd op het apparaat en is beschikbaar voor de gebruiker.

### <a name="data-locations-access-and-retention"></a>Gegevenslocaties, toegang en retentie

Omdat de gebruiker de gegevensverzameling start, geeft de gebruiker impliciet toestemming voor de opslag van de diagnostische gegevens. Alleen de gebruiker, of iemand met wie de gebruiker de gegevens deelt, heeft toegang tot de gegevens.

De diagnostische gegevens worden op het apparaat opgeslagen. Als het apparaat is verbonden met de computer van de gebruiker, bevindt de informatie zich ook op de computer in het volgende bestand:

> Dit interne \\ \<*HoloLens device name*> \\ pc Storage \\ documenten \\ trace \<*ddmmyyhhmmss*> .etl

> [!NOTE]  
> In dit bestandspad en de naam vertegenwoordigt de naam van het HoloLens apparaat en vertegenwoordigt de datum en tijd \<*HoloLens device name*> waarop het bestand is \<*ddmmyyhhmmss*> gemaakt.

De diagnostische gegevens blijven op deze locaties totdat de gebruiker deze verwijdert.

### <a name="view-diagnostic-report"></a>Diagnostisch rapport weergeven

Als u de MDM Diagnostics op HoloLens 2 wilt weergeven, selecteert u uw Wi-Fi-pictogram en navigeert u vervolgens naar Instellingen Accounts Access work **or** school en selecteert  ->    >   u **Export your management logs**. HoloLens verzendt de logboekbestanden naar uw account en geeft hun locatie weer op uw desktopcomputer.

## <a name="diagnosticlog-csp"></a>DiagnosticLog-CSP

In een MDM-omgeving (Mobile Device Management) kan de IT-beheerder de [CSP (DiagnosticLog](/windows/client-management/mdm/diagnosticlog-csp) Configuration Service Provider) gebruiken om diagnostische instellingen te configureren op ingeschreven HoloLens apparaten. De IT-beheerder kan deze instellingen configureren voor het verzamelen van logboeken van ingeschreven apparaten.

Meer informatie:
- [Diagnostische gegevens verzamelen van een Windows apparaat](/mem/intune/remote-actions/collect-diagnostics)
- [Openbare preview-versie van Intune - Windows 10 diagnostische gegevens van apparaten](https://techcommunity.microsoft.com/t5/intune-customer-success/intune-public-preview-windows-10-device-diagnostics/ba-p/2179712#:~:text=This%20first%20release%20of%20device%20diagnostics%20utilizes%20the,taking%20about%205%20minutes%20from%20start%20to%20finish.)

### <a name="prerequisites"></a>Vereisten

- Het apparaat is verbonden met een netwerk.
- Het apparaat is ingeschreven in een MDM-omgeving die ondersteuning biedt voor de DiagnosticLog-CSP.

### <a name="data-locations-access-and-retention"></a>Gegevenslocaties, toegang en retentie

Omdat het apparaat deel uitmaakt van de beheerde omgeving, geeft de gebruiker impliciet toestemming voor beheerderstoegang tot diagnostische gegevens.

De IT-beheerder gebruikt de DiagnosticLog-CSP om het beleid voor gegevensopslag, -retentie en -toegang te configureren, inclusief de beleidsregels die van toepassing zijn op het volgende:

- De cloudinfrastructuur die de diagnostische gegevens opgeslagen.
- De bewaarperiode voor de diagnostische gegevens.
- Machtigingen die de toegang tot de diagnostische gegevens bepalen.

## <a name="offline-diagnostics"></a>Offlinediagnose
In situaties waarin het apparaat geen diagnostische gegevens kan verzamelen via Feedback-hub of de probleemoplosser Instellingen, kunt u diagnostische gegevens handmatig verzamelen. Een scenario waarin dit nodig is, is wanneer het apparaat geen verbinding kan maken met Wi-Fi of wanneer u geen toegang hebt tot andere methoden die hierboven worden vermeld. De diagnostische gegevens verzamelen crashdumps en logboeken van het apparaat die een Ondersteuningstechnicus van Microsoft helpen bij het isoleren van problemen.

Dit werkt wanneer het apparaat wordt weergegeven in Verkenner nadat het via een USB-kabel is verbonden met een pc.

> [!NOTE]
> Het genereren en beheren van offline diagnostische gegevens wordt anders beheerd, afhankelijk van de versie van uw besturingssysteem. Voorheen werd dit beheerd door de telemetrie-instelling, maar dit wordt nu rechtstreeks beheerd via MDM-beleid. Als deze instelling of het MDM-beleid is uitgeschakeld, kunnen er geen diagnostische logboeken worden verzameld met behulp van dit mechanisme.

Gedrag [vóór Windows Holographic, versie 20H2:](hololens-release-notes.md#windows-holographic-version-20h2)
 - Offlinediagnose is alleen ingeschakeld wanneer de gebruiker oobe of de beleidswaarde [System\AllowTelemetry](/windows/client-management/mdm/policy-csp-system#system-allowtelemetry) doormaakt, is ingesteld op Volledig (Basic is de standaardwaarde op HoloLens). 
- Als u Offlinediagnose wilt uitschakelen, gaat **u Instellingen App > Privacy-pagina** en **selecteert u Basic** in **Diagnostische gegevens.** Op builds waarbij offlinediagnose afhankelijk is van de instelling van telemetrie, heeft dit alleen invloed op het al dan niet verzamelen van logboeken. Het heeft geen invloed op welke bestanden worden verzameld.
- Als het apparaat is vergrendeld, worden de logboeken niet weergegeven.

Op builds [Windows Holographic, versie 20H2](hololens-release-notes.md#windows-holographic-version-20h2) en hoger:
- Wanneer Terugvaldiagnose is ingeschakeld, wordt beheerd door een specifiek MDM-beleid met de bijbehorende instelling [MixedReality/FallbackDiagnostics](/windows/client-management/mdm/policy-csp-mixedreality#mixedreality-fallbackdiagnostics)
- Als het apparaat is vergrendeld, worden de logboeken niet weergegeven.

Bekijk deze video voor meer informatie.

> [!VIDEO https://channel9.msdn.com/Shows/Docs-Mixed-Reality/Gathering-Diagnostic-Files-on-HoloLens2/player]

Volg deze stappen voor het verzamelen van diagnostische gegevens:

1.  Verbinding maken het apparaat met een USB-kabel op uw pc.

2.  Navigeer in Verkenner op uw pc naar **'Deze pc \<hololens-device> \Interne Storage'**.

3.  Als de **map Storage** niet wordt weergeven, wacht het apparaat tot een gebruiker zich heeft aanmelden. U kunt het apparaat aanmelden of de stroomcyclus van het apparaat ingedrukt houden door de aan/uit-knop 10 seconden ingedrukt te houden.

4.  Druk op de knoppen **Power + Volume Down** en laat deze onmiddellijk los.

5.  Wacht een minuut totdat het apparaat de ZIP-archieven heeft voorbereid. (Een tijdelijk bestand met de naam HololensDiagnostics.temp kan zichtbaar worden terwijl het apparaat de ZIP-archieven genereert. U hoeft dat bestand niet te openen of op te slaan. Wanneer het proces is voltooien, wordt dit vervangen door de ZIP-archieven.)

6.  Vernieuw verkenner en navigeer naar de map **'\Documents'.**

7.  Kopieer de ZIP-bestanden voor diagnostische gegevens en deel deze met het ondersteuningsteam van Microsoft.

    > [!NOTE]
    > Sommige diagnostische ZIP-bestanden kunnen PII bevatten.
