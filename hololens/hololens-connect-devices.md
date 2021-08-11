---
title: Verbinding maken voor Bluetooth USB-C-apparaten
description: Maak verbinding met uw Bluetooth USB-C-apparaten en -accessoires van uw HoloLens mixed reality apparaten.
ms.assetid: 01af0848-3b36-4c13-b797-f38ad3977e30
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.localizationpriority: high
ms.date: 03/11/2020
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 1e478e366b8ad70243f6fffc47cd62e847af837637a992ebb60fc80bf6774186
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/05/2021
ms.locfileid: "115664306"
---
# <a name="connect-to-bluetooth-and-usb-c-devices"></a>Verbinding maken voor Bluetooth USB-C-apparaten

## <a name="pair-bluetooth-devices"></a>Apparaten Bluetooth koppelen

HoloLens 2 ondersteunt de volgende klassen van Bluetooth apparaten:

- [HADOE:](/windows-hardware/drivers/hid/)
    - Muis
    - Toetsenbord
- Audio-uitvoerapparaten (A2DP)

HoloLens 2 ondersteunt de volgende Bluetooth API's:
- [GATT-server](/windows/uwp/devices-sensors/gatt-server) en [-client](/windows/uwp/devices-sensors/gatt-client)
- [Rfcomm](/windows/uwp/devices-sensors/send-or-receive-files-with-rfcomm)
>[!IMPORTANT]
> Mogelijk moet u bijbehorende companion-apps installeren van Microsoft Store om daadwerkelijk gebruik te kunnen maken van de APPARATEN VAN HET PROGRAMMA en de GATT.

HoloLens (eerste generatie) ondersteunt de volgende klassen van Bluetooth apparaten:

- Muis
- Toetsenbord
- [HoloLens (eerste generatie) clicker](hololens1-clicker.md)

> [!NOTE]
> Andere typen Bluetooth apparaten, zoals sprekers, headsets, smartphones en gamepads, kunnen worden vermeld als beschikbaar in HoloLens instellingen. Deze apparaten worden echter niet ondersteund op HoloLens (eerste generatie). Zie HoloLens Instellingen [apparaten als beschikbaar,](hololens-troubleshooting.md#devices-listed-as-available-in-settings-dont-work)maar de apparaten werken niet voor meer informatie.

### <a name="pair-a-bluetooth-keyboard-or-mouse"></a>Een toetsenbord of muis Bluetooth koppelen

1. Schakel uw toetsenbord of muis in en maak het detecteerbaar. Als u wilt weten hoe u het apparaat detecteerbaar kunt maken, gaat u naar informatie op het apparaat (of de documentatie) of gaat u naar de website van de fabrikant.

1. Gebruik het bloembewegingen (HoloLens (eerste generatie)) of het beginbewegingen (HoloLens 2) om naar **Start** te gaan en selecteer vervolgens **Instellingen**.

1. Selecteer **Apparaten** en zorg ervoor dat Bluetooth is.  

1. Wanneer u de apparaatnaam ziet, selecteert **u Koppelen** en volgt u de instructies.

## <a name="disable-bluetooth"></a>Schakel Bluetooth

Met deze procedure worden de RF-onderdelen van het Bluetooth uitgeschakeld en worden alle Bluetooth uitgeschakeld op Microsoft HoloLens.

1. Gebruik de bloembewegingen (HoloLens (eerste generatie)) of het beginbewegingen (HoloLens 2) om naar **Start** te gaan en selecteer vervolgens **Instellingen**  >  **Apparaten.**

1. Verplaats de schuifregelaar voor **Bluetooth** naar de **positie Uit.**

## <a name="hololens-2-connect-usb-c-devices"></a>HoloLens 2: Verbinding maken USB-C-apparaten

HoloLens 2 ondersteunt de volgende klassen USB-C-apparaten:

- Apparaten voor massaopslag (zoals vingerafdrukstations)
- Ethernet-adapters (inclusief ethernet plus laadsnelheid)
- Digitale USB-C-naar-3.5mm-audioadapters
- Digitale USB-C-audio-headsets (inclusief headsetadapters plus laden)
- Externe USB-C-microfoons[(Windows Holographic, versie 21H1](hololens-release-notes.md#windows-holographic-version-21h1) en hoger)
- Bekabelde muis
- Bekabeld toetsenbord
- Combinatie van PD-hubs (USB A plus PD-laadtijd)


> [!NOTE]
> In reactie op feedback van klanten hebben we beperkte ondersteuning ingeschakeld voor mobiele connectiviteit die rechtstreeks naar de HoloLens via USB-C. Zie [Verbinding maken mobiele verbinding en 5G voor](hololens-cellular.md) meer informatie.

### <a name="usb-c-external-microphone-support"></a>Ondersteuning voor externe USB-C-microfoon

> [!IMPORTANT]
> Als u een **USB-microfoon aansluit, wordt deze niet automatisch ingesteld als invoerapparaat.** Bij het aansluiten van een set USB-C-hoofdtelefoon zien gebruikers dat de audio van de hoofdtelefoon automatisch wordt omgeleid naar de hoofdtelefoon, maar het besturingssysteem van de HoloLens geeft prioriteit aan de interne microfoon array boven elk ander invoerapparaat. **Volg de onderstaande stappen om een USB-C-microfoon te gebruiken.**

> [!NOTE]
> Externe microfoons kunnen niet worden gebruikt in builds vóór [Windows Holographic, versie 21H1](hololens-release-notes.md#windows-holographic-version-21h1) en hoger. 

Gebruikers kunnen externe usb-C-microfoons selecteren met behulp van het **instellingenpaneel** Geluid. USB-C-microfoons kunnen worden gebruikt voor het aanroepen, opnemen, enzovoort.

Open de **Instellingen app** en selecteer   >  **Systeemgeluid.**

![Geluid Instellingen](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> Als u externe microfoons wilt **gebruiken Remote Assist,** moeten gebruikers op de hyperlink 'Geluidsapparaten beheren' klikken.
>
> Gebruik vervolgens de vervolgkeuzeset om de externe microfoon in te stellen als **Standaardmicrofoon** of **Communicatie standaard.** Als **u Standaard** kiest, wordt de externe microfoon overal gebruikt.
>
> Als **u Standaardcommunicatie** kiest, betekent dit dat de externe microfoon wordt gebruikt in Remote Assist en andere communicatie-apps, maar de HoloLens mic-matrix kan nog steeds worden gebruikt voor andere taken.

![Geluidsapparaten beheren](images/usbc-mic-2.png)

<br>

![Standaardmicrofoon instellen](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a>Hoe zit het Bluetooth microfoonondersteuning?

Helaas worden Bluetooth microfoons nog steeds niet ondersteund op HoloLens 2.

### <a name="usb-c-hubs"></a>USB-C Hubs

Sommige gebruikers moeten mogelijk meerdere apparaten tegelijk verbinden. Voor gebruikers die een [USB-C-microfoon](#usb-c-external-microphone-support) samen met een ander aangesloten apparaat willen gebruiken, kunnen USB-C-hubs aan de behoeften van de klant worden gekoppeld. Microsoft heeft deze apparaten niet getest en we kunnen ook geen specifieke merken aanbevelen.

**Vereisten voor USB-C-hub en verbonden apparaten:**

- Voor verbonden apparaten mag geen stuurprogramma zijn geïnstalleerd.
- Het totale vermogen van alle verbonden apparaten moet lager zijn dan 4,5 Watt.

## <a name="connect-to-miracast"></a>Verbinding maken naar Miracast

Als u Miracast, volgt u deze stappen:

1. Voer een van de volgende handelingen uit:  

   - Open het **menu Start** en selecteer het **pictogram** Weergeven.
   - Zeg 'Verbinding maken' terwijl u naar het **menu Start kijkt.**  

1. Selecteer een beschikbaar apparaat in de lijst met apparaten die wordt weergegeven.

1. Voltooi de koppeling om te beginnen met projecteren.
