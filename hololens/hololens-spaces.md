---
title: Fysieke ruimten met een HoloLens
description: HoloLens leert hoe een ruimte er na een periode uitziet. Gebruikers kunnen dit proces vergemakkelijken door de HoloLens op bepaalde manieren door de ruimte te verplaatsen.
ms.assetid: bd55ecd1-697a-4b09-8274-48d1499fcb0b
author: dorreneb
ms.author: dobrown
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.date: 09/16/2019
keywords: hololens, Windows Mixed Reality, ontwerp, ruimtelijke toewijzing, HoloLens, oppervlakterep, mesh, head tracking, toewijzing
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 1 (1st gen)
- HoloLens 2
ms.openlocfilehash: b8bda049f0ef4610dcf0ca6fe81d89dd5a316e3e
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427025"
---
# <a name="map-physical-spaces-with-hololens"></a>Fysieke ruimten met een HoloLens

HoloLens hologrammen combineren met uw fysieke wereld. Om dat te doen, HoloLens meer te weten komen over de fysieke wereld om u heen en moet u onthouden waar u hologrammen in die ruimte kunt plaatsen.

Na een periode bouwt HoloLens een ruimtelijke *kaart van* de omgeving die deze heeft gezien.  HoloLens werkt de kaart bij wanneer de omgeving verandert. Zolang u bent aangemeld en het apparaat is ingeschakeld, maakt HoloLens en werkt u uw ruimtelijke kaarten bij. Als u het apparaat vast houdt of draagt met de camera's die naar een ruimte wijzen, probeert de HoloLens het gebied toe te wijzen. Hoewel de HoloLens een ruimte op natuurlijke wijze leert in de tijd, zijn er manieren waarop u uw ruimte HoloLens sneller en efficiënter kunt in kaart brengen.  

> [!NOTE]
> Als uw HoloLens uw ruimte niet kan in kaart brengen of geen kalibratie meer heeft, HoloLens u de beperkte modus in. In de beperkte modus kunt u geen hologrammen in uw omgeving plaatsen.

In dit artikel wordt uitgelegd HoloLens ruimtetoewijzing kunt toewijzen, hoe u de ruimtelijke toewijzing kunt verbeteren en hoe u de ruimtelijke gegevens beheert die HoloLens verzamelt.

## <a name="choosing-and-setting-up-and-your-space"></a>Kiezen en instellen en uw ruimte

Functies in uw omgeving kunnen het moeilijk maken voor de HoloLens een ruimte te interpreteren. Lichtniveaus, materialen in de ruimte, de lay-out van objecten en meer kunnen allemaal invloed hebben op hoe HoloLens een gebied toe te passen.

HoloLens werkt het beste in bepaalde soorten omgevingen. Als u de beste ruimtelijke kaart wilt maken, kiest u een ruimte met voldoende licht en voldoende ruimte. Vermijd donkere ruimten en ruimten met veel donkere, doorzichtige of translucente oppervlakken (bijvoorbeeld spiegels of gaezige luchten).

HoloLens is geoptimaliseerd voor indoorgebruik. Ruimtelijke toewijzing werkt ook het beste Wi-Fi is ingeschakeld, hoewel deze niet verbonden hoeft te zijn met een netwerk. HoloLens kunt toegangspunten Wi-Fi verkrijgen, zelfs als deze niet is verbonden of geverifieerd. HoloLens-functionaliteit verandert niet of de toegangspunten zijn verbonden met internet of alleen intranet/lokaal.

Gebruik alleen HoloLens veilige plaatsen zonder trippingrisico's. [Meer informatie over veiligheid.](https://support.microsoft.com/help/4023454/safety-information)

## <a name="mapping-your-space"></a>Uw ruimte toewijzen

U kunt nu beginnen met het toewijzen van uw reserveonderdelen.  Wanneer HoloLens begint met het toewijzen van uw omgeving, ziet u een mesh-afbeelding verspreid over de ruimte.  In Mixed Reality Startpagina kunt u de kaart activeren om weer te geven door te selecteren op een kaartoppervlak.

Hier volgen richtlijnen voor het bouwen van een geweldige ruimtelijke kaart.

### <a name="understand-the-scenarios-for-the-area"></a>Inzicht in de scenario's voor het gebied

Het is belangrijk om de meeste tijd te besteden aan het gebruik van de HoloLens, zodat de kaart relevant en volledig is. Als een gebruikersscenario voor HoloLens bijvoorbeeld moet worden verplaatst van punt A naar punt B, loopt u dat pad twee tot drie keer en kijkt u in alle richtingen terwijl u zich verplaatst.  

### <a name="walk-slowly-around-the-space"></a>Langzaam door de ruimte lopen

Als u te snel door het gebied loopt, is de kans groot dat de HoloLens toewijzingsgebieden mist. Loop langzaam door de ruimte en stop elke 5-8 meter om rond te kijken naar uw omgeving.  

Soepele verplaatsingen helpen de HoloLens efficiënter toe te staan.

### <a name="look-in-all-directions"></a>In alle richtingen zoeken

Als u de ruimte in kaart brengt, krijgt HoloLens meer gegevens over waar punten ten opzichte van elkaar zijn.  

Als u bijvoorbeeld niet op zoek bent, weet de HoloLens mogelijk niet waar het plafond in een ruimte is.  

Vergeet niet om op de vloer te kijken wanneer u de ruimte toe kaartt.

### <a name="cover-key-areas-multiple-times"></a>Belangrijke gebieden meerdere keren behandelen

Als u meerdere keren door een gebied gaat, kunt u functies ophalen die u mogelijk hebt gemist tijdens de eerste rondleiding. Als u een ideale kaart wilt maken, doorkruist u een gebied twee tot drie keer.

Terwijl u deze verplaatsingen herhaalt, kunt u, indien mogelijk, in één richting door een gebied lopen. Keer u vervolgens om en kom terug op de plek waar u bent gekomen.

### <a name="take-your-time-mapping-the-area"></a>Neem de tijd om het gebied toe tewijzing

Het kan 15 tot 20 minuten duren voordat de HoloLens volledig is toe te passen en zich aan de omgeving ervan aan te passen. Als u een ruimte hebt waarin u van plan bent om regelmatig een HoloLens te gebruiken, kunnen problemen later worden voorkomen door die tijd van te voren toe te geven aan de ruimte.  

## <a name="possible-errors-in-the-spatial-map"></a>Mogelijke fouten in de ruimtelijke kaart

Fouten in ruimtelijke toewijzingsgegevens kunnen worden onderverdeeld in een aantal categorieën:

- *Gaten:* echte oppervlakten ontbreken in de ruimtelijke toewijzingsgegevens.
- *5:* Er bestaan surfaces in de ruimtelijke toewijzingsgegevens die niet bestaan in de echte wereld.
- *Wormgaten:* HoloLens 'verliest' een deel van de ruimtelijke kaart door te denken dat deze zich in een ander deel van de kaart bevindt dan het daadwerkelijk is.
- *Bias:* Surfaces in the spatial mapping data are perfect aligned with real-world surfaces, either pushed in or pulled out.

Als u een van deze fouten ziet, gebruikt u [de FeedbackHub om](hololens-feedback.md) feedback te verzenden.

## <a name="security-and-storage-for-spatial-data"></a>Beveiliging en opslag voor ruimtelijke gegevens

Windows 10 update van versie 1803 voor Microsoft HoloLens en slaat toewijzingsgegevens op in een lokale database (op het apparaat).

HoloLens kunnen gebruikers niet rechtstreeks toegang krijgen tot de kaartdatabase, zelfs niet wanneer het apparaat op een pc is aangesloten of wanneer de Verkenner-app wordt gebruikt. Wanneer BitLocker is ingeschakeld op HoloLens, worden de opgeslagen kaartgegevens ook versleuteld samen met het hele volume.

### <a name="remove-map-data-and-known-spaces-from-hololens"></a>Verwijder kaartgegevens en bekende spaties uit HoloLens

Er zijn twee opties voor het verwijderen van kaartgegevens in **Instellingen > System > Hologrammen:**

- Als u hologrammen in de buurt wilt verwijderen, **selecteert u Hologrammen in de buurt verwijderen.** Met deze opdracht worden de kaartgegevens en ankerde hologrammen voor de huidige ruimte geweken. Als u het apparaat in dezelfde ruimte blijft gebruiken, wordt er een geheel nieuwe kaartsectie gemaakt en op het apparaat op te nemen ter vervanging van de verwijderde informatie.

   > [!NOTE]
   > 'In de buurt' hologrammen zijn hologrammen die zijn verankerd in dezelfde kaartsectie in de huidige ruimte.

   U kunt deze optie bijvoorbeeld gebruiken om werkgerelateerde kaartgegevens te verwijderen zonder dat dit van invloed is op kaartgegevens die betrekking hebben op het thuisgebruik.

- Als u alle hologrammen wilt verwijderen, **selecteert u Alle hologrammen verwijderen.** Met deze opdracht worden alle kaartgegevens gewed die op het apparaat zijn opgeslagen, evenals alle anker-hologrammen. U moet hologrammen expliciet plaatsen. U kunt de eerder geplaatste hologrammen niet opnieuw ontdekken.

> [!NOTE]
> Nadat u in de buurt of alle hologrammen hebt verwijderd, HoloLens de huidige ruimte scannen en toewijzen.

### <a name="wi-fi-data-in-spatial-maps"></a>Wi-Fi in ruimtelijke kaarten

HoloLens slaat Wi-Fi kenmerken op om hologramlocaties en kaartsecties te correleren die zijn opgeslagen in de HoloLens database van bekende ruimten. Informatie over Wi-Fi is niet toegankelijk voor gebruikers en wordt niet naar Microsoft verzonden met behulp van de cloud of telemetrie.

Zolang de Wi-Fi is ingeschakeld, correleert HoloLens kaartgegevens met Wi-Fi toegangspunten in de buurt. Er is geen verschil in gedrag of een netwerk is verbonden of alleen in de buurt is gedetecteerd. Als Wi-Fi is uitgeschakeld, HoloLens nog steeds in de ruimte gezocht. De HoloLens echter meer van de kaartgegevens in de database met spaties zoeken en mogelijk meer tijd nodig om hologrammen te vinden. Zonder de Wi-Fi-informatie moet de HoloLens actieve scans vergelijken met alle hologramankers en kaartsecties die op het apparaat zijn opgeslagen om het juiste deel van de kaart te vinden.

## <a name="related-topics"></a>Verwante onderwerpen

- [Ontwerp van ruimtelijke toewijzing](/windows/mixed-reality/spatial-mapping)
