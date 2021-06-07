---
title: Fysieke ruimten in kaart brengen met HoloLens
description: HoloLens leert hoe een ruimte er in de tijd uitziet. Gebruikers kunnen dit proces mogelijk maken door de HoloLens op bepaalde manieren door de ruimte te verplaatsen.
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
ms.openlocfilehash: 7cedf2af90744477c33736087c85a43168167707
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379419"
---
# <a name="map-physical-spaces-with-hololens"></a>Fysieke ruimten in kaart brengen met HoloLens

HoloLens combineert hologrammen met uw fysieke wereld. Om dat te doen, moet HoloLens meer te weten komen over de fysieke wereld om u heen en onthouden waar u hologrammen in die ruimte plaatst.

Na een periode bouwt de HoloLens een ruimtelijke *kaart van* de omgeving die deze heeft gezien.  HoloLens werkt de kaart bij wanneer de omgeving verandert. Zolang u bent aangemeld en het apparaat is ingeschakeld, maakt HoloLens uw ruimtelijke kaarten en werkt het bij. Als u het apparaat vast houdt of draagt met de camera's die naar een ruimte wijzen, probeert de HoloLens het gebied toe te wijzen. Hoewel de HoloLens een ruimte op natuurlijke wijze leert in de tijd, zijn er manieren waarop u HoloLens kunt helpen uw ruimte sneller en efficiënter toe te wijzen.  

> [!NOTE]
> Als uw HoloLens uw ruimte niet kan in kaart brengen of geen kalibratie meer heeft, kan HoloLens in de beperkte modus worden gezet. In de modus Beperkt kunt u geen hologrammen in uw omgeving plaatsen.

In dit artikel wordt uitgelegd hoe HoloLens ruimten toewijst, hoe u de ruimtelijke toewijzing verbetert en hoe u de ruimtelijke gegevens beheert die door HoloLens worden verzameld.

## <a name="choosing-and-setting-up-and-your-space"></a>Kiezen en instellen en uw ruimte

Functies in uw omgeving kunnen het voor de HoloLens lastig maken om een ruimte te interpreteren. Lichte niveaus, materialen in de ruimte, de indeling van objecten en meer kunnen allemaal invloed hebben op de manier waarop HoloLens een gebied toekent.

HoloLens werkt het beste in bepaalde soorten omgevingen. Als u de beste ruimtelijke kaart wilt maken, kiest u een ruimte met voldoende licht en voldoende ruimte. Vermijd donkere ruimten en ruimten met een groot aantal donkere, doorzichtige of translucente ruimten (bijvoorbeeld spiegels of gaurige kleding).

HoloLens is geoptimaliseerd voor indoorgebruik. Ruimtelijke toewijzing werkt ook het beste wanneer Wi-Fi is ingeschakeld, hoewel deze niet met een netwerk hoeft te worden verbonden. HoloLens kan toegangspunten Wi-Fi, zelfs als deze niet is verbonden of geverifieerd. De HoloLens-functionaliteit verandert niet of de toegangspunten zijn verbonden met internet of alleen intranet/lokaal.

Gebruik HoloLens alleen op veilige locaties zonder trippingrisico's. [Meer informatie over veiligheid.](https://support.microsoft.com/help/4023454/safety-information)

## <a name="mapping-your-space"></a>Uw ruimte toewijzen

U kunt nu beginnen met het toewijzen van uw reserveonderdelen.  Wanneer HoloLens begint met het toewijzen van uw omgeving, ziet u een mesh-afbeelding die de ruimte verspreidt.  In Mixed Reality Startpagina kunt u de kaart activeren om weer te geven door op een kaartvlak te selecteren.

Hier volgen richtlijnen voor het bouwen van een geweldige ruimtelijke kaart.

### <a name="understand-the-scenarios-for-the-area"></a>De scenario's voor het gebied begrijpen

Het is belangrijk dat u de meeste tijd besteedt aan het gebruik van de HoloLens, zodat de kaart relevant en volledig is. Als een gebruikersscenario voor HoloLens bijvoorbeeld betrekking heeft op het verplaatsen van Punt A naar Punt B, loopt u dat pad twee tot drie keer en kijkt u in alle richtingen terwijl u zich verplaatst.  

### <a name="walk-slowly-around-the-space"></a>Langzaam door de ruimte lopen

Als u te snel door het gebied loopt, zal de HoloLens waarschijnlijk toewijzingsgebieden missen. Loop langzaam door de ruimte en stop elke 1,5 meter om rond uw omgeving te kijken.  

Soepele verplaatsingen helpen de HoloLens-kaart ook efficiënter toe te staan.

### <a name="look-in-all-directions"></a>In alle richtingen zoeken

Als u de ruimte in kaart brengt, krijgt de HoloLens meer gegevens over waar punten ten opzichte van elkaar zijn.  

Als u bijvoorbeeld niet op zoek bent, weet de HoloLens mogelijk niet waar het plafond in een ruimte is.  

Vergeet niet om op de grond te kijken terwijl u de ruimte toe kaartt.

### <a name="cover-key-areas-multiple-times"></a>Belangrijke gebieden meerdere keren behandelen

Als u meerdere keren door een gebied gaat, kunt u functies ophalen die u mogelijk hebt gemist tijdens de eerste rondleiding. Als u een ideale kaart wilt maken, doorkruist u een gebied twee tot drie keer.

Tijdens het herhalen van deze verplaatsingen kunt u, indien mogelijk, tijd besteden aan het lopen door een gebied in één richting, en vervolgens teruggaan naar de weg die u hebt gemaakt.

### <a name="take-your-time-mapping-the-area"></a>Neem de tijd om het gebied in kaart te brengen

Het kan tussen 15 en 20 minuten duren voordat de HoloLens volledig is toe te passen aan de omgeving. Als u een ruimte hebt waarin u van plan bent om regelmatig een HoloLens te gebruiken, kunnen problemen later worden voorkomen wanneer u die tijd van te voren neemt om de ruimte in kaart te brengen.  

## <a name="possible-errors-in-the-spatial-map"></a>Mogelijke fouten in de ruimtelijke kaart

Fouten in ruimtelijke toewijzingsgegevens kunnen in enkele categorieën worden onderverdeeld:

- *Gaten:* echte oppervlakten ontbreken in de ruimtelijke toewijzingsgegevens.
- *20:* Er bestaan surfaces in de ruimtelijke toewijzingsgegevens die niet bestaan in de echte wereld.
- *Wormgaten:* HoloLens 'verliest' een deel van de ruimtelijke kaart door te denken dat deze zich in een ander deel van de kaart bevindt dan het daadwerkelijk is.
- *Bias:* Surfaces in the spatial mapping data are perfect alignly alignly with real-world surfaces, either pushed in or pulled out.

Als u een van deze fouten ziet, gebruikt u [de FeedbackHub om](hololens-feedback.md) feedback te verzenden.

## <a name="security-and-storage-for-spatial-data"></a>Beveiliging en opslag voor ruimtelijke gegevens

Windows 10 update van versie 1803 voor Microsoft HoloLens en slaat toewijzingsgegevens op in een lokale database (op het apparaat).

HoloLens-gebruikers hebben geen rechtstreeks toegang tot de kaartdatabase, zelfs niet wanneer het apparaat is aangesloten op een pc of wanneer ze de Bestandenverkenner-app gebruiken. Wanneer BitLocker is ingeschakeld op HoloLens, worden de opgeslagen kaartgegevens ook versleuteld, samen met het hele volume.

### <a name="remove-map-data-and-known-spaces-from-hololens"></a>Kaartgegevens en bekende spaties verwijderen uit HoloLens

Er zijn twee opties voor het verwijderen van kaartgegevens in **Instellingen > System > Holograms:**

- Als u hologrammen in de buurt wilt verwijderen, **selecteert u Hologrammen in de buurt verwijderen.** Met deze opdracht worden de kaartgegevens en anker hologrammen voor de huidige ruimte geweerd. Als u het apparaat nog steeds in dezelfde ruimte gebruikt, wordt er een geheel nieuwe kaartsectie gemaakt en op het apparaat op het apparaat op te nemen ter vervanging van de verwijderde informatie.

   > [!NOTE]
   > 'Nearby' hologrammen zijn hologrammen die zijn verankerd in dezelfde kaartsectie in de huidige ruimte.

   U kunt deze optie bijvoorbeeld gebruiken om werkgerelateerde kaartgegevens te verwijderen zonder dat dit van invloed is op de thuisgerelateerde kaartgegevens.

- Als u alle hologrammen wilt verwijderen, **selecteert u Alle hologrammen verwijderen.** Met deze opdracht worden alle kaartgegevens gewed die op het apparaat zijn opgeslagen, evenals alle anker hologrammen. U moet alle hologrammen expliciet plaatsen. U kunt de eerder geplaatste hologrammen niet opnieuw ontdekken.

> [!NOTE]
> Nadat u in de buurt of alle hologrammen hebt verwijderd, begint HoloLens onmiddellijk met het scannen en toewijzen van de huidige ruimte.

### <a name="wi-fi-data-in-spatial-maps"></a>Wi-Fi in ruimtelijke kaarten

HoloLens slaat Wi-Fi kenmerken op om hologramlocaties en kaartsecties te correleren die zijn opgeslagen in de HoloLens-database van bekende ruimten. Informatie over Wi-Fi is niet toegankelijk voor gebruikers en wordt niet naar Microsoft verzonden met behulp van de cloud of telemetrie.

Zolang de Wi-Fi is ingeschakeld, correleert HoloLens kaartgegevens met Wi-Fi toegangspunten in de buurt. Er is geen verschil in gedrag of een netwerk is verbonden of alleen in de buurt is gedetecteerd. Als Wi-Fi is uitgeschakeld, zoekt HoloLens nog steeds naar de ruimte. HoloLens moet echter meer van de kaartgegevens in de spaces-database doorzoeken en heeft mogelijk meer tijd nodig om hologrammen te vinden. Zonder de Wi-Fi gegevens moet de HoloLens actieve scans vergelijken met alle hologramankers en kaartsecties die op het apparaat zijn opgeslagen om het juiste deel van de kaart te vinden.

## <a name="related-topics"></a>Verwante onderwerpen

- [Ontwerp van ruimtelijke toewijzing](https://docs.microsoft.com/windows/mixed-reality/spatial-mapping)
