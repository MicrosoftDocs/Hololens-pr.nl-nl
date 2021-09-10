---
title: HoloLens omgevingsoverwegingen
description: Krijg de best mogelijke ervaring met HoloLens wanneer u het apparaat optimaliseert voor uw ogen en omgeving.
author: dorreneb
ms.author: dobrown
manager: jarrettr
ms.date: 8/29/2019
ms.prod: hololens
ms.topic: article
audience: ITPro
ms.localizationpriority: high
keywords: holographic frame, field of view, fov, kalibratie, spaties, omgeving, HoloLens, mixed reality, mixed reality headsets
ms.openlocfilehash: 6976527d759e768fa5da72f96395a8b7b390cefd
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427848"
---
# <a name="hololens-environment-considerations"></a>HoloLens omgevingsoverwegingen

HoloLens combineert het holografische met de 'echte' wereld en plaatst hologrammen in uw omgeving. Een holografische app-venster 'hangt' aan de wand, een holografische man draait op de tabletop, de oren van uw onbewuste vriend zitten op het hoofd van uw onbewuste vriend. Wanneer u een immersive game of app gebruikt, wordt de holografische wereld verspreid om uw omgeving te vullen, maar u kunt de ruimte nog steeds zien en verplaatsen.

De hologrammen die u plaats, blijven waar u ze hebt op hun plaats, zelfs als u uw apparaat uit zet.

## <a name="setting-up-an-environment"></a>Een omgeving instellen

HoloLens weten hoe u stabiele en nauwkeurige hologrammen kunt plaatsen door *gebruikers* in een ruimte bij te houden. Zonder de juiste tracering begrijpt het apparaat niet de omgeving of de gebruiker in het apparaat. Hologrammen kunnen op de verkeerde plaatsen worden weergegeven, niet elke keer op dezelfde plek worden weergegeven of helemaal niet worden weergegeven. De gegevens die worden gebruikt om gebruikers bij te houden, worden weergegeven in de *ruimtelijke kaart*.  

De prestaties van tracering worden sterk beïnvloed door de omgeving waarin de gebruiker zich in de omgeving zich voordeed. Het afstemmen van een omgeving om stabiele en consistente tracering te stimuleren, is een kunst in plaats van een wetenschap. Veel verschillende omgevingsfactoren worden samengevoegd om tracering mogelijk te maken, maar als Mixed Reality-ontwikkelaar zijn er verschillende factoren waarmee u rekening kunt houden om ruimte voor betere tracering af te stemmen.

### <a name="lighting"></a>Belichting

Windows Mixed Reality gebruikt visueel licht om de locatie van de gebruiker bij te houden. Wanneer een omgeving te licht is, kunnen de camera's verzadigd raken en wordt er niets gezien. Als de omgeving te donker is, kunnen de camera's niet voldoende informatie ophalen en wordt er niets gezien. De belichting moet even zijn en voldoende licht zijn dat een mens zonder moeite kan zien, maar niet zo licht dat het licht erg is om naar te kijken.  

Gebieden met lichtpunten in een algemeen donker gebied zijn ook problematisch, omdat de camera zich moet aanpassen bij het in- en uitsturen van lichte ruimten. Dit kan ertoe leiden dat het apparaat 'verloren gaat' en denkt dat de wijziging in het licht gelijk is aan een wijziging in de locatie. Stabiele lichtniveaus in een gebied leiden tot betere tracering.  

Elke verlichting in de buitenruimte kan ook leiden tot instabiliteit in de tracker, omdat de zon in de tijd aanzienlijk kan variëren. Zo kan het bijhouden in dezelfde ruimte in de zomer versus de winter aanzienlijk verschillende resultaten opleveren, omdat het tweedehands licht buiten op verschillende tijdstippen van het jaar hoger kan zijn.  

Als u eenmeter hebt, is een stabiele 500-1000 meter een goede plek om te beginnen.  

#### <a name="types-of-lighting"></a>Soorten belichting

Verschillende soorten licht in een ruimte kunnen ook van invloed zijn op het bijhouden. Licht pulseer met de elektriciteit van de wisselstroom die er doorheen loopt: als de AC-frequentie 50 Hz is, wordt de lichte pulses op 50 Hz gebruikt. Voor een mens is dit niet opgemerkt. De 30-camera van HoloLens echter ziet deze wijzigingen: sommige frames zullen goed worden gebruikt, sommige zullen slecht worden aanlicht en sommige worden oververlicht wanneer de camera probeert te compenseren voor lichte pulses.  

In de Verenigde Staten is de standaard voor de elektriciteitsfrequentie 60 Hz, dus de gloeilamp pulses worden gebruikt met de framesnelheid van HoloLens: 60 Hz-pulses die zijn afgestemd op de 30 FPS-framesnelheid van HoloLens. Veel landen hebben echter een AC-frequentiestandaard van 50 Hz, wat betekent dat sommige HoloLens frames worden genomen tijdens de pulses en andere niet. Het is met name bekend dat de belichting in Europa problemen veroorzaakt.  

Er zijn enkele dingen die u kunt proberen op te lossen. Temperatuur-, gloeilamp- en opwarmcycli zijn veelvoorkomende oorzaken van het afwisselen en vervangen van planten. Het kan ook helpen om de huidige trekkingen te vereenspanken en ervoor te zorgen dat de huidige trekkingen constant zijn.  

### <a name="items-in-a-space"></a>Items in een ruimte

HoloLens maakt gebruik van unieke omgevings oriëntatiepunten, ook wel *functies* genoemd, om zichzelf in een ruimte te lokaliseren.  

Een apparaat kan bijna nooit bijhouden in een gebied met slechte functies, omdat het apparaat niet kan weten waar het zich in de ruimte van het apparaat voor doet. Het toevoegen van functies aan de muren van een ruimte is meestal een goede manier om het bijhouden te verbeteren. Posters, symbolen die zijn vastgetapt aan een wand, planten, unieke objecten of andere vergelijkbare items helpen allemaal. Een rommelige bureau is een goed voorbeeld van een omgeving die leidt tot een goede tracering. Er zijn veel verschillende functies in één gebied.  

Gebruik daarnaast unieke functies in dezelfde ruimte. Dezelfde poster die meerdere keren wordt herhaald op een wand, veroorzaakt bijvoorbeeld verwarring bij het apparaat, omdat de HoloLens niet weet naar welke van de terugkerende posters het gaat. Een veelgebruikte manier om unieke functies toe te voegen, is het gebruik van regels maskeringstape om unieke, niet-terugkerende patronen te maken langs de muren en de vloer van een ruimte.  

Een goede vraag om uzelf te stellen is: als u slechts een klein deel van de scène hebt gezien, kunt u zich dan op unieke manier in de ruimte vinden? Zo niet, dan heeft het apparaat waarschijnlijk ook problemen met het bijhouden van de gegevens.

#### <a name="wormholes"></a>Wormholes

Als u twee gebieden of regio's hebt die er hetzelfde uitzien, denkt de tracker misschien dat ze hetzelfde zijn. Dit leidt tot een apparaat dat zichzelf laat denken dat het ergens anders is. We noemen dit soort terugkerende gebieden *wormgaten.*  

Om wormgaten te voorkomen, probeert u identieke gebieden in dezelfde ruimte te voorkomen. Identieke gebieden kunnen soms fabrieksstations, vensters op een gebouw, serverrekken of werkstations zijn. Door gebieden te labelen of unieke functies toe te voegen aan elk gebied dat er ongeveer uit ziet, kunnen wormgaten worden beperkt.

### <a name="movement-in-a-space"></a>Verplaatsing in een ruimte

Als uw omgeving voortdurend verschuift en verandert, heeft het apparaat geen stabiele functies om op te zoeken.  

Hoe meer bewegende objecten zich in een ruimte, met inbegrip van personen, hoe gemakkelijker het is om tracering te verliezen. Het verplaatsen van transportbandjes, items in verschillende bouwsystemen en veel mensen in een ruimte is bekend dat ze traceringsproblemen veroorzaken.

De HoloLens kunnen zich snel aanpassen aan deze wijzigingen, maar alleen wanneer dat gebied duidelijk zichtbaar is voor het apparaat. Gebieden die niet zo vaak worden gezien, kunnen achterlopen op de realiteit, wat fouten in de ruimtelijke kaart kan veroorzaken. Een gebruiker scant bijvoorbeeld een vriend en draait zich vervolgens om terwijl de vriend de ruimte verlaat. Een 'ghost'-weergave van de vriend blijft bestaan in de ruimtelijke toewijzingsgegevens totdat de gebruiker de nu lege ruimte opnieuw scant.

### <a name="proximity-of-the-user-to-items-in-the-space"></a>Nabijheid van de gebruiker bij items in de ruimte

Op dezelfde manier als de manier waarop mensen zich niet goed kunnen concentreren op objecten dicht bij de ogen, HoloLens problemen wanneer objecten zich dicht bij de camera's ervan. Als een object te dicht bij beide camera's te zien is of als een object één camera blokkeert, heeft het apparaat veel meer problemen met het bijhouden van het object.  

De camera's kunnen niet dichter dan 15 cm van een object zien.

### <a name="surfaces-in-a-space"></a>Surfaces in a space

Sterk reflectieve oppervlakten zien er waarschijnlijk anders uit, afhankelijk van de hoek, wat van invloed is op het bijhouden. U kunt een geheel nieuwe auto zien: wanneer u er omheen beweegt, reflecteert het licht en ziet u verschillende objecten in het oppervlak terwijl u zich verplaatst. Voor de tracker vertegenwoordigen de verschillende objecten die in het oppervlak worden weergegeven een veranderende omgeving en verliest het apparaat de tracering.

Minder objecten zijn gemakkelijker te vinden.

### <a name="wi-fi-fingerprint-considerations"></a>Wi-Fi vingerafdruk overwegen

Zolang de Wi-Fi is ingeschakeld, worden kaartgegevens gecorreleerd met een Wi-Fi vingerafdruk, zelfs wanneer ze niet zijn verbonden met een daadwerkelijk Wi-Fi-netwerk/-router. Zonder Wi-Fi informatie zijn de ruimte en hologrammen mogelijk iets langzamer te herkennen. Als de Wi-Fi aanzienlijk veranderen, kan het apparaat denken dat het zich in een andere ruimte in de weg zit.

Netwerkidentificatie (zoals SSID of MAC-adres) wordt niet naar Microsoft verzonden en alle Wi-Fi worden lokaal op de HoloLens.

## <a name="mapping-new-spaces"></a>Nieuwe ruimten toewijzen

Wanneer u een nieuwe ruimte opslaat (of een bestaande laadt), ziet u een mesh-afbeelding die over de ruimte verspreidt. Dit betekent dat uw apparaat uw omgeving toewijst. Hoewel een HoloLens in de tijd een ruimte leert, zijn er tips en trucs voor het in kaart brengen van ruimten.

## <a name="environment-management"></a>Omgevingsbeheer

Er zijn twee instellingen waarmee gebruikers hologrammen kunnen 'ops schonen' en ervoor kunnen zorgen dat HoloLens ruimte 'vergeet'. Ze bestaan in **Hologrammen omgevingen** in de instellingen-app. De tweede instelling wordt ook weergegeven onder **Privacy** in de instellingen-app.  

1. **Verwijder hologrammen in de buurt.** Wanneer u deze instelling selecteert, HoloLens alle anker hologrammen en alle opgeslagen kaartgegevens voor de 'huidige ruimte' waar het apparaat zich bevindt, gewist. Er wordt een nieuwe kaartsectie gemaakt en opgeslagen in de database voor die locatie zodra hologrammen opnieuw in dezelfde ruimte zijn geplaatst.

1. **Verwijder alle hologrammen.** Als u deze instelling selecteert, HoloLens alle kaartgegevens en anker hologrammen in de volledige databases van ruimten gewist. Er worden geen hologrammen opnieuw ontdekt en hologrammen moeten opnieuw worden geplaatst om mapsecties in de database op te slaan.

## <a name="hologram-quality"></a>Hologramkwaliteit

Hologrammen kunnen in uw omgeving worden geplaatst, hoog, laag en overal om u heen, maar u ziet ze via een [holografische kader](/windows/mixed-reality/holographic-frame) dat zich voor uw ogen bevindt. Als u de beste weergave wilt krijgen, moet u uw apparaat aanpassen zodat u het hele frame kunt zien. En wees gerust om uw omgeving te verkennen.

Om uw [hologrammen](/windows/mixed-reality/hologram) er helder, helder en stabiel uit te laten zien, moet HoloLens alleen voor u worden ge kalibreerd. Wanneer u uw HoloLens, wordt u door dit proces geleid. Als hologrammen er later niet goed uitzien of als u talloze fouten ziet, kunt u aanpassingen aanbrengen.

Als u problemen hebt met het toewijzen van spaties, kunt u proberen om hologrammen in de buurt te verwijderen en de ruimte opnieuw toe te staan.

### <a name="calibration"></a>Kalibratie

Als uw hologrammen er jittery of arcch uitzien, of als u problemen hebt bij het plaatsen van hologrammen, is het eerste wat u moet proberen de [kalibratie-app](hololens-calibration.md). Deze app kan ook helpen als u last hebt van problemen tijdens het gebruik van HoloLens.

Ga naar Instellingen Systeemprogramma's om **naar de**  >  **kalibratie-app**  >  **te gaan.** Selecteer **Kalibratie openen** en volg de instructies.

Als iemand anders uw apparaat gaat gebruiken HoloLens, moet hij eerst de Kalibratie-app uitvoeren, zodat het apparaat voor hem of haar juist is ingesteld.

## <a name="temperature-and-regulatory-information"></a>Informatie over temperatuur en regelgeving

[HoloLens Informatie over regelgeving:](https://support.microsoft.com/en-us/help/13761/hololens-regulatory-information)bevat informatie over temperatuurbereik, verwijdering, radio- en tv-interferentie, en meer.

Zie details voor 'HoloLens' in [Materialen](https://www.microsoft.com/legal/compliance/materials-substances) en > REACH Article 33 Disclosure on Environmental Compliance (PDF).

Hier volgen enkele richtlijnen voor het gebruik van uw apparaat:

1. Sla het apparaat een uur op in een omgeving binnen het temperatuurbereik (stand-by of uit) voordat u het apparaat gebruikt.
1. Gebruik het apparaat in een omgeving binnen het temperatuurbereik.
1. Gebruik het apparaat binnen.
1. Apparaat in de schaduw gebruiken; zelfs binnen vermijdt u directe sing door vensters of skylights.
1. Als u de bovenstaande richtlijnen volgt, maar onverwachte problemen ervaart, volgt u de onderstaande stappen voor het verzenden van [feedback.](hololens-feedback.md) 
    1. Zorg **ervoor dat** Volledige of **Optionele** telemetrie is ingeschakeld op uw apparaat. Als dat niet het zo is, kunt u deze inschakelen. 
    >[!CAUTION]
    > Telemetrie is niet met terugwerkende kracht voor thermische gebeurtenissen. De telemetriegegevens moeten tijdens het gebruik worden ingeschakeld, anders worden de vereiste gegevens niet vastgelegd.
    
    2. Reproduceer het probleem met de koeling.
    3. Neem de datum en tijd op waarop de fout is opgetreden.
    4. Feedback [verzenden.](hololens-feedback.md)

## <a name="see-also"></a>Zie ook

- [Ontwerp van ruimtelijke toewijzing](/windows/mixed-reality/spatial-mapping)
- [Hologrammen](/windows/mixed-reality/hologram)
