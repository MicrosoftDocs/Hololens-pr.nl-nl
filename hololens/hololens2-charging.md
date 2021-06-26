---
title: HoloLens 2 batterij en laden
description: Uw HoloLens laden en externe accupakketten gebruiken.
ms.assetid: E0AB903E-454E-46F6-AB25-4DFA0A475B0C
ms.prod: hololens
ms.sitesec: library
author: jbienzms
ms.author: jbienz
ms.topic: article
ms.localizationpriority: high
ms.date: 05/14/2021
manager: evmill
appliesto:
- HoloLens 2
ms.openlocfilehash: acbc3e52240f420d384fa372684966d7220d53c6
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923581"
---
# <a name="hololens-2-battery-and-charging"></a>HoloLens 2 batterij en laden

Deze pagina bevat details over het laden van HoloLens 2 en het gebruik van externe accupakketten.

## <a name="charging-the-device"></a>Het apparaat laden

Gebruik de [kabel en de USB Type-C-kabel](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) die bij de HoloLens 2 omdat dit de beste manier is om uw apparaat op te laden. De met de HoloLens 2 voorziet in maximaal 9V @ 2A (18W). Samen met de meegeleverde wandgevel kunnen HoloLens 2 de accu in minder dan 65 minuten vol laden wanneer het apparaat stand-by is. Als deze accessoires niet beschikbaar zijn, moet u ervoor zorgen dat de beschikbare accessoires ten minste 15W aan stroom kunnen ondersteunen.

> [!NOTE]
> Vermijd indien mogelijk het gebruik van een pc om het apparaat op te laden via USB, wat traag is.

## <a name="checking-the-battery-charge-level"></a>Het laadniveau van de accu controleren
Als het apparaat correct is opgestart en wordt uitgevoerd, zijn er drie manieren om het laadniveau van de accu te controleren:

- In het hoofdmenu van de gebruikersinterface van het HoloLens-apparaat.
- Bekijk de LED dicht bij de aan/uit-knop (voor een kosten van 40 procent ziet u ten minste twee solide LED's).
    - Wanneer het apparaat wordt op laden, wordt de accu-indicator licht om het huidige laadniveau aan te geven.  Het laatste licht vervaagt in en uit om actieve laadtijd aan te geven.
    - Wanneer uw HoloLens is aan, geeft de batterijindicator het accuniveau in vijf stappen weer.
    - Wanneer slechts een van de vijf lampen is aan, is het accuniveau lager dan 20 procent.
    - Als het accuniveau kritiek laag is en u het apparaat probeert in te zetten, gaat er kort één lampje knipperen en gaat u uit.
- Open verkenner op de host-pc **en** zoek uw HoloLens 2 aan de linkerkant onder **Deze pc.** Klik met de rechtermuisknop op het apparaat en selecteer **Eigenschappen.** In een dialoogvenster wordt het acculadingsniveau weergegeven.

   ![Een scherm HoloLens 2 eigenschappen toont het wijzigingsniveau van de accu](images/ResetRecovery2.png)

## <a name="alternative-charging-specifications"></a>Alternatieve specificaties voor kosten

HoloLens 2 kunnen worden in rekening gebracht door [USB-energiebronnen](https://www.usb.org/usb-charger-pd) tot 27 Watt. Als de bron ten minste 10 Watt kan leveren, kan de HoloLens-gebruiktijd worden verlengd (mogelijk voor onbepaalde tijd voor sommige workloads). 

> [!NOTE]
> Als u een USB-A-naar-USB-C-laadkabel gebruikt, worden de kosten beperkt tot 7,5 Watt. De gebruiktijd wordt nog steeds verlengd, maar niet zo lang als het gebruik van USB-C naar C.

Wanneer HoloLens zich in de stand-bymodus bevindt, is 18 Watt voldoende om de maximale laadsnelheid voor de interne accu te bereiken. Wanneer HoloLens in gebruik is, kan het tarief worden verlaagd omdat HoloLens prioriteit geeft aan het gebruik boven de kosten.

> [!IMPORTANT]
> Het is raadzaam dat HoloLens 2 minimaal 5V/1,5A in rekening wordt gebracht. Er mogen geen 5V/1.5A-producten worden gebruikt die niet ten minste 5V/1.5A kunnen leveren. 

### <a name="external-battery-packs"></a>Externe batterijpakketten

Accupakketten die voldoen aan de bovenstaande specificaties kunnen worden gebruikt met HoloLens 2. Houd er echter rekening mee dat sommige USB-C-accupakketten worden gebruikt en stroom leveren via dezelfde USB-C-poort. Het is belangrijk dat deze accupakketten [TRY implementeren. SRC om](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20) ervoor te zorgen dat ze HoloLens in rekening brengen in plaats van er kosten van in rekening te brengen. 

### <a name="managing-heat"></a>Heat beheren

Net als bij elk apparaat genereert het laden van HoloLens warmte. Hoe sneller de lading, hoe meer warmte wordt gegenereerd. Als u een lading op een lager accuniveau start, wordt er ook meer warmte gegenereerd dan wanneer de accu bijna vol is. Klanten die HoloLens gedurende langere tijd in een warme omgeving moeten gebruiken, kunnen de volgende technieken gebruiken:

- U kunt verbinding maken met HoloLens 2 externe voedingsbron, zelfs wanneer de interne accu volledig is geladen.
- Wanneer een externe batterij wordt verwijderd, blijft HoloLens werken op de interne accu.    
- Als de warmte na de bovenstaande stappen nog steeds een probleem is, kunt u overwegen om een accupakket te gebruiken dat het laden beperkt tot 1,5A. Houd er rekening mee dat deze optie niet zo veel gebruiksduur biedt omdat de interne accu nog steeds langzaam wordt leeggekoppeld.

## <a name="troubleshooting"></a>Problemen oplossen


### <a name="hololens-charges-external-battery"></a>Externe batterij voor HoloLens-kosten
Als HoloLens 2 externe accu laadt in plaats van dat deze wordt geladen, geeft dit aan dat TRY niet door de accu wordt [geïmplementeerd. SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20). Overschakelen naar een nieuwer accupakket is de aanbevolen manier om dit probleem op te lossen, maar u kunt ook proberen om over te schakelen naar een USB-A-naar-USB-C-kabel. Houd er rekening mee dat dit de laadsnelheid beperkt tot 7,5 watt.
