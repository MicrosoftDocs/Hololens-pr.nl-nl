---
title: Introductie van de nieuwe Instellingen app
description: Meer informatie over de nieuwe Instellingen app
author: joyjaz
ms.author: v-jjaswinski
keywords: HoloLens, instellingen, app- picker, volume
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisle
ms.openlocfilehash: e6da84c180ef596b63b6d41229bd094354ab1221
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640165"
---
# <a name="new-settings-app"></a>Nieuwe Instellingen app

Met [Windows Holographic, versie 21H1,](hololens-release-notes.md#windows-holographic-version-21h1)introduceren we een nieuwe versie van de Instellingen app. De nieuwe Instellingen-app bevat nieuwe functies en uitgebreide instellingen voor HoloLens 2 in de volgende gebieden: Geluid, De slaapstand van Power &, Network & Internet, Apps, Accounts, Toegankelijkheid en meer.

> [!NOTE]
> Omdat de nieuwe Instellingen-app verschilt van de verouderde Instellingen-app, worden alle Instellingen-vensters die u eerder in uw omgeving hebt geplaatst, verwijderd bij het bijwerken.

![Startpagina Instellingen nieuwe app](images/new-settings-app.png)

**Nieuwe functies en instellingen**
- Instellingen zoeken: zoek naar instellingen van de Instellingen startpagina met trefwoorden of de naam van de instelling.
- Kalibratie van > [systeemkleur](hololens2-display.md#how-to-use-display-color-calibration)
    - Selecteer een alternatief kleurprofiel voor uw HoloLens 2 weergave.
- System > Sound:
  - Audioapparaten voor invoer en uitvoer: kies onafhankelijk uw invoer- en uitvoerapparaten (bijvoorbeeld luisteren naar audio via Bluetooth-hoofdtelefoon of gebruik een USB-C-microfoon voor audio-invoer).
    > [!NOTE]
    > Bluetooth microfoons worden niet ondersteund door HoloLens 2.
  - App-volume: pas het volume van elke app onafhankelijk aan. Zie [volumebeheer per app.](holographic-home.md#per-app-volume-control)
- Systeem> Slaapstand &: kies wanneer het apparaat na een periode van inactiviteit in de slaapstand moet gaan.
- Systeem> batterij: schakel handmatig de batterijbesparing in of stel een drempelwaarde voor de accu in op welk punt batterijbesparing modus automatisch wordt ingeschakeld.
- Apparaten > USB: u kunt USB-verbindingen standaard uitschakelen.
- Netwerkverbinding & internet:
  - USB-C Ethernet-adapters worden nu weergegeven in Network & Internet.
  - Instellingen voor USB-C Ethernet-adapter zijn nu beschikbaar, met inbegrip van het IP-adres.
  - U kunt nu de vliegtuigmodus inschakelen op HoloLens 2.
- Apps: u kunt de standaardapps die worden gebruikt voor bestands- en koppelingstypen opnieuw instellen. Zie Standaard [app- kiezen voor meer informatie.](holographic-home.md#default-app-picker)
- Accounts > andere gebruikers: apparaateigenaren kunnen gebruikers toevoegen, standaardgebruikers upgraden naar apparaateigenaren, apparaateigenaren downgraden naar standaardgebruikers en gebruikers verwijderen.
- Toegankelijkheid: de grootte van de tekst en enkele visuele effecten wijzigen.

**Bekende problemen**
- Eerder geplaatste Instellingen worden verwijderd (zie opmerking hierboven).
- U kunt de naam van uw apparaat niet meer wijzigen met de Instellingen app. IT-beheerders kunnen de naam van apparaten wijzigen met behulp van de [sjabloon Windows Autopilot](hololens2-autopilot.md) voor HoloLens 2-apparaatnaam of het knooppunt MDM [DevDetail CSP](/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/DNSComputerName.
- Op de Ethernet-pagina wordt te allen tijde een virtueel Ethernet-apparaat (UsbNcm) weergegeven.
- Accugebruik voor de nieuwe Microsoft Edge mogelijk niet nauwkeurig, vanwege de aard van een Win32-desktoptoepassing die wordt ondersteund door een UWP-adapterlaag (naar verwachting zal dit niet snel worden opgelost).

