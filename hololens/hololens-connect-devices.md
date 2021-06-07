---
title: Verbinding maken met Bluetooth- en USB-C-apparaten
description: Maak verbinding met Bluetooth- en USB-C-apparaten en -accessoires vanaf uw HoloLens-mixed reality apparaten.
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
ms.openlocfilehash: ffae65a6e1c096242ae7a28c488896c65df1c62d
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/25/2021
ms.locfileid: "111379443"
---
# <a name="connect-to-bluetooth-and-usb-c-devices"></a>Verbinding maken met Bluetooth- en USB-C-apparaten

## <a name="pair-bluetooth-devices"></a>Bluetooth-apparaten koppelen

HoloLens 2 ondersteunt de volgende klassen Bluetooth-apparaten:

- [VERBORGEN:](https://docs.microsoft.com/windows-hardware/drivers/hid/)
    - Muis
    - Toetsenbord
- Audio-uitvoerapparaten (A2DP)

HoloLens 2 ondersteunt de volgende Bluetooth-API's:
- [GATT-server](https://docs.microsoft.com/windows/uwp/devices-sensors/gatt-server) en [-client](https://docs.microsoft.com/windows/uwp/devices-sensors/gatt-client)
- [Rfcomm](https://docs.microsoft.com/windows/uwp/devices-sensors/send-or-receive-files-with-rfcomm)
>[!IMPORTANT]
> Mogelijk moet u bijbehorende companion-apps installeren vanuit Microsoft Store om de APPARATEN VAN HET PROGRAMMA en de GATT daadwerkelijk te kunnen gebruiken.

HoloLens (1e generatie) ondersteunt de volgende klassen Bluetooth-apparaten:

- Muis
- Toetsenbord
- [Klik op HoloLens (1e generatie)](https://docs.microsoft.com/hololens/hololens1-clicker)

> [!NOTE]
> Andere soorten Bluetooth-apparaten, zoals sprekers, headsets, smartphones en gamepads, kunnen worden vermeld als beschikbaar in HoloLens-instellingen. Deze apparaten worden echter niet ondersteund op HoloLens (eerste generatie). Zie [HoloLens Settings lists devices as available (HoloLens-instellingen)](hololens-FAQ.md#hololens-settings-lists-devices-as-available-but-the-devices-dont-work)als beschikbaar, maar de apparaten werken niet.

### <a name="pair-a-bluetooth-keyboard-or-mouse"></a>Een Bluetooth-toetsenbord of -muis koppelen

1. Schakel uw toetsenbord of muis in en maak het detecteerbaar. Als u wilt weten hoe u het apparaat detecteerbaar maakt, gaat u naar informatie over het apparaat (of de documentatie) of gaat u naar de website van de fabrikant.

1. Gebruik de bloembewegingen (HoloLens (1e generatie)) of het beginbewegingen (HoloLens 2) om naar **Start** te gaan en selecteer vervolgens **Instellingen**.

1. Selecteer **Apparaten** en zorg ervoor dat Bluetooth is aan.  

1. Wanneer u de apparaatnaam ziet, selecteert **u Koppelen** en volgt u de instructies.

## <a name="disable-bluetooth"></a>Bluetooth uitschakelen

Met deze procedure worden de RF-onderdelen van het Bluetooth-radioprogramma uitgeschakeld en wordt alle Bluetooth-functionaliteit op de Microsoft HoloLens.

1. Gebruik de bloembewegingen (HoloLens (1e generatie)) of de beginbewegingen (HoloLens 2) om naar **Start** te gaan en selecteer vervolgens  >  **Instellingen Apparaten.**

1. Verplaats de schuifregelaar voor **Bluetooth naar** de **uit-positie.**

## <a name="hololens-2-connect-usb-c-devices"></a>HoloLens 2: USB-C-apparaten verbinden

HoloLens 2 ondersteunt de volgende klassen USB-C-apparaten:

- Apparaten voor massaopslag (zoals vingerafdrukstations)
- Ethernet-adapters (inclusief ethernet en laadtijd)
- Digitale USB-C-naar-3,5mm-audioadapters
- Digitale USB-C-audio-headsets (inclusief headsetadapters plus laden)
- Externe USB-C-microfoons[(Windows Holographic, versie 21H1](hololens-release-notes.md#windows-holographic-version-21h1) en hoger)
- Bekabelde muis
- Bekabeld toetsenbord
- Combinatie van PD-hubs (USB A plus PD-kosten)


> [!NOTE]
> Als reactie op feedback van klanten hebben we beperkte ondersteuning ingeschakeld voor mobiele connectiviteit die rechtstreeks aan de HoloLens is verbonden via USB-C. Zie [Verbinding maken met mobiel en 5G](hololens-cellular.md) voor meer informatie.

### <a name="usb-c-external-microphone-support"></a>Ondersteuning voor externe USB-C-microfoon

> [!IMPORTANT]
> Als u een **USB-microfoon aansluit, wordt deze niet automatisch ingesteld als invoerapparaat.** Bij het aansluiten van een set USB-C-headsets zien gebruikers dat de audio van de microfoon automatisch wordt omgeleid naar de laptop, maar het HoloLens-besturingssysteem geeft prioriteit aan de interne microfoon array boven elk ander invoerapparaat. **Volg de onderstaande stappen om een USB-C-microfoon te gebruiken.**

> [!NOTE]
> Externe microfoons kunnen niet worden gebruikt in builds vóór [Windows Holographic, versie 21H1](hololens-release-notes.md#windows-holographic-version-21h1) en hoger. 

Gebruikers kunnen externe usb-C-microfoons selecteren met behulp van het **instellingenpaneel** Geluid. USB-C-microfoons kunnen worden gebruikt voor het aanroepen, opnemen, enzovoort.

Open de **app Instellingen** en selecteer   >  **Systeemgeluid.**

![Geluidsinstellingen](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> Als u externe microfoons wilt **gebruiken Remote Assist,** moeten gebruikers op de hyperlink Geluidsapparaten beheren klikken.
>
> Gebruik vervolgens de vervolgkeuzeset om de externe microfoon in te stellen als **Standaardmicrofoon** of **Standaardcommunicatie.** Als **u Standaard** kiest, wordt de externe microfoon overal gebruikt.
>
> Als **u Standaardcommunicatie** kiest, wordt de externe microfoon gebruikt in Remote Assist en andere communicatie-apps, maar kan de HoloLens-microfoon nog steeds worden gebruikt voor andere taken.

![Geluidsapparaten beheren](images/usbc-mic-2.png)

<br>

![Standaardmicrofoon instellen](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a>Hoe zit het met ondersteuning voor Bluetooth-microfoons?

Helaas worden Bluetooth-microfoons momenteel nog niet ondersteund op HoloLens 2.

#### <a name="troubleshooting-usb-c-microphones"></a>Problemen met USB-C-microfoons oplossen

Let erop dat sommige USB-C-microfoons zich onjuist melden als zowel een microfoon *als* een spreker. Dit is een probleem met de microfoon en niet met HoloLens. Wanneer u een van deze microfoons op HoloLens aangesloten, gaat het geluid mogelijk verloren. Gelukkig is er een eenvoudige oplossing.  

Stel **in**  ->    ->  **Systeemgeluid van** instellingen expliciet de ingebouwde sprekers **(Analog Feature Audio Driver)** in als **het standaardapparaat.** HoloLens moet deze instelling onthouden, zelfs als de microfoon wordt verwijderd en later opnieuw wordt verbonden.

![Problemen met USB-C-microfoons oplossen](images/usbc-mic-4.png)
### <a name="usb-c-hubs"></a>USB-C Hubs

Sommige gebruikers moeten mogelijk meerdere apparaten tegelijk verbinden. Voor gebruikers die een [USB-C-microfoon](#usb-c-external-microphone-support) en een ander aangesloten apparaat willen gebruiken, kunnen USB-C-hubs aan de behoeften van de klant worden gekoppeld. Microsoft heeft deze apparaten niet getest en we kunnen ook geen specifieke merken aanbevelen.

**Vereisten voor USB-C-hub en verbonden apparaten:**

- Voor verbonden apparaten mag geen stuurprogramma zijn geïnstalleerd.
- Het totale vermogen van alle verbonden apparaten moet lager zijn dan 4,5 Watt.

## <a name="connect-to-miracast"></a>Verbinding maken met Miracast

Volg deze stappen om Miracast te gebruiken:

1. Voer een van de volgende handelingen uit:  

   - Open het **menu Start** en selecteer het **pictogram** Weergeven.
   - Zeg 'Verbinding maken' terwijl u naar het **menu Start kijkt.**  

1. Selecteer een beschikbaar apparaat in de lijst met apparaten die wordt weergegeven.

1. Voltooi de koppeling om te beginnen met projecteren.
