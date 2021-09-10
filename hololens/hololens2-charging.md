---
title: HoloLens 2 Accu en laden
description: Het laden van uw HoloLens en het gebruik van externe accupakketten.
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
ms.openlocfilehash: b4692468942da88877370864eda2ce173cc499af
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427281"
---
# <a name="hololens-2-battery-and-charging"></a>HoloLens 2 Accu en laden

Deze pagina biedt details over het laden van HoloLens 2 en het gebruik van externe accupakketten.

## <a name="charging-the-device"></a>Het apparaat laden

Gebruik de [kabel en de USB Type-C-kabel](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) die bij de HoloLens 2 omdat dit de beste manier is om uw apparaat op te laden. De ton die is HoloLens 2 biedt maximaal 9V @ 2A (18W). Samen met de meegeleverde wandapparatuur kunnen HoloLens 2 de accu in minder dan 65 minuten vol laden wanneer het apparaat stand-by is. Als deze accessoires niet beschikbaar zijn, moet u ervoor zorgen dat de beschikbare thee ten minste 15W aan stroom kan ondersteunen.

> [!NOTE]
> Vermijd indien mogelijk het gebruik van een pc om het apparaat via USB op te laden, wat traag is.

## <a name="checking-the-battery-charge-level"></a>Het laadniveau van de accu controleren
Als het apparaat correct is opgestart en actief is, zijn er drie manieren om het laadniveau van de accu te controleren:

- In het hoofdmenu van de HoloLens gebruikersinterface van het apparaat.
- Bekijk de LED dicht bij de aan/uit-knop (voor een kosten van 40 procent ziet u ten minste twee solide LED's).
    - Wanneer het apparaat wordt op laden, wordt de accu-indicator licht om het huidige laadniveau aan te geven.  Het laatste licht vervaagt in en uit om aan te geven dat de kosten actief zijn.
    - Wanneer uw HoloLens is aan, geeft de batterijindicator het accuniveau in vijf stappen weer.
    - Wanneer slechts een van de vijf lampen is aan, is het accuniveau lager dan 20 procent.
    - Als het accuniveau kritiek laag is en u het apparaat probeert in te zetten, gaat er kort één lampje uit en gaat u uit.
- Open verkenner op uw host-pc **en** zoek uw apparaat HoloLens 2 aan de linkerkant onder **Deze pc.** Klik met de rechtermuisknop op het apparaat en selecteer **Eigenschappen.** In een dialoogvenster wordt het acculadingsniveau weergegeven.

   ![Een scherm HoloLens 2 eigenschappen toont het niveau van de batterijwijziging.](images/ResetRecovery2.png)

## <a name="alternative-charging-specifications"></a>Alternatieve kostenspecificaties

HoloLens 2 kunnen worden op basis van [USB-voedingen](https://www.usb.org/usb-charger-pd) tot 27 Watt. Als de bron ten minste 10 Watt kan leveren, kan de HoloLens worden uitgebreid (mogelijk voor onbepaalde tijd voor sommige werkbelastingen). 

> [!NOTE]
> Als u een USB-A-naar-USB-C-laadkabel gebruikt, worden de kosten beperkt tot 7,5 watt. De gebruiktijd wordt nog steeds verlengd, maar niet zo lang als het gebruik van USB-C naar C.

Wanneer HoloLens stand-bymodus is, is 18 Watt voldoende om de maximale laadsnelheid voor de interne accu te bereiken. Wanneer HoloLens in gebruik is, kan het tarief worden verlaagd omdat HoloLens prioriteit geeft aan de werking boven de kosten.

> [!IMPORTANT]
> Het is raadzaam om HoloLens 2 minimaal 5V/1,5A in rekening te worden gebracht. Moet niet worden gebruikt als u niet ten minste 5V/1.5A kunt leveren. 

### <a name="external-battery-packs"></a>Externe batterijpakketten

Accupakketten die voldoen aan de bovenstaande specificaties, kunnen worden gebruikt met HoloLens 2. Houd er echter rekening mee dat sommige USB-C-accupakketten voeding hebben en stroom leveren via dezelfde USB-C-poort. Het is belangrijk dat deze batterijpakketten [TRY implementeren. SRC om](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20) ervoor te zorgen dat ze HoloLens in plaats van er kosten van in rekening te brengen. 

### <a name="managing-heat"></a>Warmte beheren

Net als bij elk apparaat genereert HoloLens warmte. Hoe sneller de lading, hoe meer warmte wordt gegenereerd. Bovendien genereert het starten van een lading op een lager accuniveau meer warmte dan het starten van een lading wanneer de accu grotendeels vol is. Klanten die gedurende langere tijd HoloLens in warme omgevingen moeten werken, kunnen de volgende technieken gebruiken:

- U kunt verbinding maken met HoloLens 2 externe voedingsbron, zelfs wanneer de interne accu volledig is op geladen.
- Wanneer een externe batterij is verwijderd, HoloLens blijven werken op de interne accu.    
- Als de warmte na de bovenstaande stappen nog steeds een probleem is, kunt u overwegen een batterij of accupakket te gebruiken dat de laadsnelheid beperkt tot 1,5A. Houd er rekening mee dat deze optie niet zo veel operationele tijd biedt omdat de interne batterij nog steeds langzaam wordt leeggekoppeld.

## <a name="troubleshooting"></a>Problemen oplossen


### <a name="hololens-charges-external-battery"></a>HoloLens Externe batterij laden
Als HoloLens 2 een externe accu laadt in plaats van dat deze wordt op geladen, geeft dit aan dat TRY niet door de accu wordt [geïmplementeerd. SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20). Overschakelen naar een nieuwer accupakket is de aanbevolen manier om dit probleem op te lossen, maar u kunt ook proberen om over te schakelen naar een USB-A-naar-USB-C-kabel. Houd er rekening mee dat dit de laadsnelheid beperkt tot 7,5 watt.
