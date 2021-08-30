---
title: Introductie van de nieuwe Instellingen app
description: Meer informatie over de nieuwe Instellingen app
author: joyjaz
ms.author: v-jjaswinski
keywords: HoloLens, instellingen, app- kiezen, volume
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisle
ms.openlocfilehash: bcde697b5887573826a3a1a61e8c3707b4d0337a
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189661"
---
# <a name="new-settings-app"></a>Nieuwe Instellingen app

Met [Windows Holographic, versie 21H1,](hololens-release-notes.md#windows-holographic-version-21h1)introduceren we een nieuwe versie van de Instellingen app. De nieuwe Instellingen-app bevat nieuwe functies en uitgebreide instellingen voor HoloLens 2 in de volgende gebieden: Geluid, De slaapstand van Power &, Network & Internet, Apps, Accounts, Toegankelijkheid en meer.

> [!NOTE]
> Omdat de nieuwe Instellingen-app verschilt van de verouderde Instellingen-app, worden alle Instellingen die u eerder in uw omgeving hebt geplaatst, verwijderd bij het bijwerken.

![Startpagina Instellingen nieuwe app.](images/new-settings-app.png)

**Nieuwe functies en instellingen**
- Instellingen zoeken: zoek naar instellingen op de startpagina van Instellingen met trefwoorden of de naam van de instelling.
- Kalibratie van > [systeemkleur](hololens2-display.md#how-to-use-display-color-calibration)
    - Selecteer een alternatief kleurprofiel voor uw HoloLens 2 weergave.
- System > Sound:
  - Audioapparaten voor invoer en uitvoer: kies onafhankelijk uw invoer- en uitvoerapparaten (bijvoorbeeld luisteren naar audio via Bluetooth-hoofdtelefoon of gebruik een USB-C-microfoon voor audio-invoer).
    > [!NOTE]
    > Bluetooth microfoons worden niet ondersteund door HoloLens 2.
  - App-volume: pas het volume van elke app onafhankelijk aan. Zie [volumebeheer per app.](holographic-home.md#per-app-volume-control)
- Systeem> Slaapstand &: kies wanneer het apparaat na een periode van inactiviteit in de slaapstand moet gaan.
- Systeem> batterij: schakel de batterijbesparing modus handmatig in of stel een drempelwaarde voor de accu in op batterijbesparing modus automatisch wordt ingeschakeld.
- Apparaten > USB: u kunt USB-verbindingen standaard uitschakelen.
- Netwerkverbinding & internet:
  - USB-C Ethernet-adapters worden nu weergegeven in Network & Internet.
  - Instellingen voor USB-C Ethernet-adapter zijn nu beschikbaar, met inbegrip van het IP-adres.
  - U kunt nu de vliegtuigmodus inschakelen op HoloLens 2.
- Apps: u kunt de standaardapps die worden gebruikt voor bestands- en koppelingstypen opnieuw instellen. Zie Standaard [app- kiezen voor meer informatie.](holographic-home.md#default-app-picker)
- Accounts > andere gebruikers: apparaateigenaren kunnen gebruikers toevoegen, standaardgebruikers upgraden naar apparaateigenaren, apparaateigenaren downgraden naar standaardgebruikers en gebruikers verwijderen.
- Toegankelijkheid: wijzig de tekstgrootte en enkele visuele effecten.

**Bekende problemen**
- Eerder geplaatste Instellingen worden verwijderd (zie opmerking hierboven).
- U kunt de naam van uw apparaat niet meer wijzigen met de Instellingen app. IT-beheerders kunnen de naam van apparaten wijzigen met behulp van de [sjabloon Windows Autopilot](hololens2-autopilot.md) voor HoloLens 2 apparaatnaam of het knooppunt MDM [DevDetail CSP](/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/DNSComputerName.
- Op de Ethernet-pagina wordt te allen tijde een virtueel Ethernet-apparaat (UsbNcm) weergegeven.
- Accugebruik voor de nieuwe Microsoft Edge mogelijk niet nauwkeurig, vanwege de aard van een Win32-desktoptoepassing die wordt ondersteund door een UWP-adapterlaag (er wordt binnenkort geen oplossing verwacht).

