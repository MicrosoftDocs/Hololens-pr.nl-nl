---
title: Accu en laden
description: Uw HoloLens laden en externe batterijpakketten gebruiken.
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
ms.openlocfilehash: 15ecc698a515987857f556fed97d74f861cd6b20
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/25/2021
ms.locfileid: "111379496"
---
# <a name="battery-and-charging"></a>Accu en laden

Deze pagina biedt details over het laden van HoloLens 2 en het gebruik van externe accupakketten.

## <a name="included-charger"></a>Included Charger

De in de HoloLens 2 biedt maximaal 9V @ 2A (18W). Indien mogelijk wordt het ten zeerste aanbevolen om kosten in rekening te brengen met behulp van de inbegrepen auto.  

## <a name="specifications"></a>Specificaties

HoloLens 2 kunnen worden op basis van [USB-voedingen](https://www.usb.org/usb-charger-pd) tot 27 Watt. Als de bron ten minste 10 Watt kan leveren, kan de HoloLens-gebruiktijd worden uitgebreid (mogelijk voor onbepaalde tijd voor sommige workloads). 

> [!NOTE]
> Als u een USB-A-naar-USB-C-laadkabel gebruikt, worden de kosten beperkt tot 7,5 watt. De gebruiktijd wordt nog steeds verlengd, maar niet zo lang als het gebruik van USB-C naar C.

Wanneer HoloLens zich in de stand-bymodus bevindt, is 18 Watt voldoende om de maximale laadsnelheid voor de interne accu te bereiken. Wanneer HoloLens in gebruik is, kan het tarief worden verlaagd omdat HoloLens prioriteit geeft aan de werking boven de kosten.

> [!IMPORTANT]
> Het is raadzaam om HoloLens 2 minimaal 5V/1,5A in rekening te gebracht. Er mag geen gebruik worden gemaakt van 5V/1.5A-producten die niet ten minste 5V/1.5A kunnen leveren. 

## <a name="external-battery-packs"></a>Externe batterijpakketten

Accupakketten die voldoen aan de bovenstaande specificaties, kunnen worden gebruikt met HoloLens 2. Houd er echter rekening mee dat sommige USB-C-accupakketten voeding hebben en stroom leveren via dezelfde USB-C-poort. Het is belangrijk dat deze batterijpakketten [TRY implementeren. SRC om](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20) ervoor te zorgen dat ze HoloLens in rekening brengen in plaats van er kosten voor in rekening te brengen. 

## <a name="managing-heat"></a>Warmte beheren

Net als bij elk apparaat genereert het laden van HoloLens warmte. Hoe sneller de lading, hoe meer warmte wordt gegenereerd. Bovendien genereert het starten van een lading op een lager accuniveau meer warmte dan het starten van een lading wanneer de accu grotendeels vol is. Klanten die HoloLens gedurende langere tijd in een warme omgeving moeten gebruiken, kunnen de volgende technieken gebruiken:

- U kunt verbinding maken met HoloLens 2 externe voedingsbron, zelfs wanneer de interne accu volledig is op geladen.
- Wanneer een externe batterij is verwijderd, blijft HoloLens werken op de interne accu.    
- Als de warmte na de bovenstaande stappen nog steeds een probleem is, kunt u overwegen een batterij of accupakket te gebruiken dat de laadsnelheid beperkt tot 1,5A. Houd er rekening mee dat deze optie niet zo veel operationele tijd biedt omdat de interne accu nog steeds langzaam wordt leeggekoppeld.

## <a name="troubleshooting"></a>Problemen oplossen


### <a name="hololens-charges-external-battery"></a>Externe batterij van HoloLens-kosten
Als HoloLens 2 een externe accu laadt in plaats van door deze te worden geladen, geeft dit aan dat TRY niet door de accu wordt [geïmplementeerd. SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20). Overschakelen naar een nieuwer accupakket is de aanbevolen manier om dit probleem op te lossen, maar u kunt ook proberen om over te schakelen naar een USB-A-naar-USB-C-kabel. Houd er rekening mee dat dit de laadsnelheid beperkt tot 7,5 watt.
