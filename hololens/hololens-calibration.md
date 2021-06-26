---
title: De kwaliteit en het comfort van de visual verbeteren
description: Meer informatie over het kalibreren van uw interpupillary distance (IPD) om de kwaliteit van uw visuals op HoloLens-apparaten te verbeteren.
author: Teresa-Motiv
ms.author: xerxesb
ms.date: 9/13/2019
ms.topic: article
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
keywords: kalibratie, comfort, visuals, kwaliteit, ipd, HoloLens, Windows Mixed Reality, VR-headsets
ms.openlocfilehash: 62d83aa5c6032d15b26fbc7938859bdaf74151f4
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924142"
---
# <a name="improve-visual-quality-and-comfort"></a>De kwaliteit en het comfort van de visual verbeteren

HoloLens 2 HoloLens (1e generatie) werken beide beter wanneer ze naar uw unieke ogen worden ge kalibreerd.

Hoewel beide apparaten moeten kalibreren voor de beste hologramweergave-ervaring, gebruiken ze verschillende kalibratietechnologieën en -technieken.  Ga naar [HoloLens 2 kalibratie](#calibrating-your-hololens-2) [of HoloLens-kalibratie (1e generatie).](#calibrating-your-hololens-1st-gen)

## <a name="calibrating-your-hololens-2"></a>Uw HoloLens 2

HoloLens 2 maakt gebruik van technologie voor het bijhouden van ogen om uw ervaring met het zien en communiceren met de virtuele omgeving te verbeteren. Door de HoloLens 2 zorgt u ervoor dat uw ogen (en de ogen van anderen die het apparaat gebruiken) nauwkeurig kunnen worden gevolgd. Het helpt ook bij het comfort van gebruikers, de uitlijning van hologrammen en het bijhouden van de hand. Na kalibratie worden hologrammen correct weergegeven, zelfs wanneer de visor op uw hoofd verschuift.

HoloLens 2 gebruiker wordt gevraagd het apparaat te kalibreren onder de volgende omstandigheden:

- De gebruiker gebruikt het apparaat voor het eerst
- De gebruiker heeft zich eerder voor het kalibratieproces uit gekozen
- Het kalibratieproces is niet geslaagd de laatste keer dat de gebruiker het apparaat heeft gebruikt
- De gebruiker heeft zijn kalibratieprofielen verwijderd
- Het apparaat wordt uitgeschakeld en weer aan gezet en een van de bovenstaande omstandigheden is van toepassing 


![Kalibratieprompt voor het aanpassen van de ogen.](./images/07-et-adjust-for-your-eyes.png)

Tijdens dit proces bekijkt u een set doelen (gems). Het is prima als u tijdens de kalibratie knippert, maar probeer gericht te blijven op de gems in plaats van andere objecten in de ruimte.  Door u te richten op de gems, kan HoloLens meer te weten komen over uw oogpositie om uw holografische wereld weer te geven.

![Prompt voor kalibratie dat de gebruiker het hoofd stil moet houden en punten met zijn ogen moet volgen.](./images/07-et-hold-head-still.png)

![Prompt voor kalibratie met gem-voorbeeld.](./images/08-et-gems.png)

![Prompt voor kalibratie aanpassen.](./images/09-et-adjusting.png)

Als de kalibratie is geslaagd, ziet u een successcherm.  Zo niet, lees dan meer over [het diagnosticeren van kalibratiefouten.](hololens2-display.md#troubleshooting)

![Prompt voor kalibratie geslaagd.](./images/10-et-success.png)

### <a name="calibration-when-sharing-a-device-or-session"></a>Kalibratie bij het delen van een apparaat of sessie

Meerdere gebruikers kunnen een HoloLens 2 delen, zonder dat elke persoon het apparaat hoeft in te stellen. Wanneer een nieuwe gebruiker het apparaat voor het eerst op zijn hoofd plaatst, HoloLens 2 de gebruiker automatisch gevraagd om visuals te kalibreren. Wanneer een gebruiker met eerder ge kalibreerd visuele elementen het apparaat op het hoofd plaatst, wordt het scherm naadloos aangepast voor kwaliteit en een vertrouwd weergave-ervaring.  

### <a name="manually-starting-the-calibration-process"></a>Handmatig het kalibratieproces starten

1. Gebruik de beweging Start om het menu [ **Start te** openen.](hololens2-basic-usage.md#start-gesture)
1. Als de app Instellingen niet is vastgemaakt aan **Start,** selecteert **u Alle apps.**
1. Selecteer **Instellingen** en selecteer vervolgens **Systeem**  >  **kalibratie**  >  **oog kalibratie**  >  **Run eye kalibratie**.

   ![De app Instellingen, met de optie Run eye kalibratie](./images/C-Settings.Calibration.png)

### <a name="auto-eye-position-support"></a>Ondersteuning voor automatische oogpositie

In HoloLens 2 zorgen oogposities voor nauwkeurige positiebepaling van hologrammen, een goede weergave-ervaring en een verbeterde kwaliteit van de weergave. Oogposities worden intern berekend als onderdeel van de berekening voor het bijhouden van de ogen. Dit vereist echter dat elke gebruiker de kalibratie van oogtracking doormaakt, zelfs wanneer voor de ervaring mogelijk geen ooginvoer nodig is.

**Automatische oogpositie (AEP)** maakt deze scenario's mogelijk met een interactieloze manier om oogposities voor de gebruiker te berekenen. Automatische oogpositie werkt automatisch op de achtergrond vanaf het moment dat de gebruiker het apparaat in gebruik neemt. Als de gebruiker geen voorafgaande kalibratie voor het bijhouden van de ogen heeft, geeft Automatische oogpositie de oogposities van de gebruiker aan het weergavesysteem na een verwerkingstijd van 20 tot 30 seconden. De gebruikersgegevens blijven niet op het apparaat behouden en dit proces wordt herhaald als de gebruiker opstart en het apparaat weer in gebruik neemt of als het apparaat opnieuw wordt opgestart of uit de slaapstand wordt halen.

Er zijn enkele wijzigingen in het systeemgedrag met de functie Automatische oogpositie wanneer een niet-gecalibreerde gebruiker het apparaat in gebruik neemt. In deze context verwijst een niet-gecalibreerde gebruiker naar iemand die het kalibratieproces voor het bijhouden van de ogen op het apparaat nog niet eerder heeft doorlopen.

| Actieve toepassing | Voorafgaand gedrag | Gedrag van Windows Holographic, versie 20H2 Update |
|:-------------------|:-----------------|:-----------------------------------|
| Niet-staren ingeschakelde app of Holographic Shell |Dialoogvenster voor het bijhouden van kalibratieprompts voor de ogen wordt weergegeven. | Er wordt geen prompt weergegeven. |
| Staren ingeschakelde app | Dialoogvenster voor het bijhouden van kalibratieprompts voor de ogen wordt weergegeven. | De prompt voor het traceren van de kalibratie wordt alleen weergegeven wanneer de toepassing oogcontactstroom gebruikt. |

Als de gebruiker overstapt van een toepassing zonder staren naar een toepassing die toegang heeft tot de staringsgegevens, wordt de kalibratieprompt weergegeven. 

Al het andere systeemgedrag is vergelijkbaar met wanneer de huidige gebruiker geen actieve kalibratie van oogtracking heeft. De eenhandige startbewegingen worden bijvoorbeeld niet ingeschakeld. De Out-Of-Box-Experience wordt niet gewijzigd voor de eerste installatie.

Voor ervaringen waarvoor oogcontactgegevens of nauwkeurige positie van hologrammen zijn vereist, raden we niet-gecalibreerde gebruikers aan om kalibratie van de oogtracking uit te voeren. De app is toegankelijk via de prompt voor het traceren van de ogen of door de app Instellingen te starten vanuit het menu Start en vervolgens **Systeem > Kalibratie >** Oog> uit te voeren.

#### <a name="deferred-calibration-prompt"></a>Uitgestelde kalibratieprompt

Met Automatische oogpositie wordt het dialoogvenster Kalibratieprompt voor oog bijhouden uitgesteld totdat een toepassing oogcontactgegevens aanvraagt. Dit zorgt ervoor dat de gebruiker niet wordt gevraagd om te kijken wanneer er geen staring nodig is voor de actieve toepassing. Als voor de toepassing wel staringsgegevens nodig zijn en de huidige gebruiker niet is ge kalibreerd, krijgt de gebruiker een kalibratieprompt te zien. Dit gedrag kan worden gebruikt om de prompt voor het traceren van de ogen weer te geven op een geschikt tijdstip voor de ervaring. Deze methode wordt aanbevolen om de volgende redenen

1.  Het dialoogvenster Prompt voor kalibratie van oog tracering biedt de gebruiker details over waarom oogtracking nodig is.
2.  Biedt de gebruiker een manier om te weigeren om zijn ogen te kalibreren.

Als de gebruiker ervoor kiest om de kalibratie van oogvolgendheid te starten, moet de focus terugkeren naar de oorspronkelijke toepassing nadat de kalibratie is voltooid. 

### <a name="calibration-data-and-security"></a>Kalibratiegegevens en beveiliging

Kalibratiegegevens worden lokaal op het apparaat opgeslagen en zijn niet gekoppeld aan accountgegevens. Er is geen record van wie het apparaat heeft gebruikt zonder kalibratie. Dit betekent dat nieuwe gebruikers wordt gevraagd visuals te kalibreren wanneer ze het apparaat voor het eerst gebruiken, en gebruikers die zich eerder hebben af-van-kalibratie of als de kalibratie is mislukt.

Op het apparaat kunnen maximaal 50 kalibratieprofielen lokaal worden opgeslagen. Nadat dit nummer is bereikt, verwijdert het apparaat automatisch het oudste ongebruikte profiel.

Kalibratiegegevens kunnen altijd van het apparaat worden verwijderd in  >  **Instellingen Privacy**  >  **Oogtracker.**  

### <a name="disable-calibration"></a>Kalibrering uitschakelen

U kunt de kalibratieprompt ook uitschakelen door de volgende stappen uit te voeren:

1. Selecteer **Instellingen Systeem**  >  **kalibratie.**  >  
1. Schakel Wanneer een nieuwe persoon deze HoloLens gebruikt uit, vraagt u automatisch om **oogabratie uit te voeren.**

> [!IMPORTANT]
> Deze instelling kan een negatieve invloed hebben op de kwaliteit en het comfort van hologramweergaven.  Wanneer u deze instelling uit schakelen, werken functies die afhankelijk zijn van het bijhouden van de ogen (zoals het scrollen van tekst) niet meer in in immersieve toepassingen.

### <a name="hololens-2-eye-tracking-technology"></a>HoloLens 2-trackingtechnologie

Het apparaat maakt gebruik van de technologie voor het bijhouden van de ogen om de kwaliteit van de weergave te verbeteren en ervoor te zorgen dat alle hologrammen nauwkeurig en gemakkelijk in 3D kunnen worden weergegeven. Omdat de ogen worden gebruikt als oriëntatiepunten, kan het apparaat zichzelf aanpassen voor elke gebruiker en de visuals afstemmen wanneer de headset iets verschuift tijdens het gebruik.  Alle aanpassingen worden op het eerste uur doorgevoerd zonder handmatig af te stemmen.
> [!NOTE]
> Het instellen van de IP-adress is niet van toepassing op Hololens 2, omdat oogposities worden berekend door het systeem.

HoloLens-toepassingen gebruiken oogtracking om bij te houden waar u in realtime naar op zoek bent. Dit is de belangrijkste mogelijkheid die ontwikkelaars kunnen gebruiken om een geheel nieuw niveau van context, menselijke kennis en interacties binnen de Holographic-ervaring mogelijk te maken. Ontwikkelaars hoeven niets te doen om deze mogelijkheid te gebruiken.

## <a name="calibrating-your-hololens-1st-gen"></a>Uw HoloLens (eerste generatie) kalibreren

HoloLens (1e generatie) past de hologramweergave aan op basis van uw [interpupillary distance](https://en.wikipedia.org/wiki/Interpupillary_distance) (IPD). Als de IPD niet nauwkeurig is, kunnen hologrammen instabiel of op een onjuiste afstand lijken. U kunt de kwaliteit van uw visuals verbeteren door het apparaat te kalibreren naar uw interpupillary distance (IPD).

Wanneer u uw HoloLens-apparaat (1e generatie) in stelt, wordt u gevraagd om uw visuals te kalibreren nadat Cortana zichzelf heeft introduceert. Het is raadzaam om de kalibratiestap tijdens deze installatiefase te voltooien. U kunt dit echter overslaan door te wachten totdat Cortana u vraagt en vervolgens 'Overslaan' zegt.

Tijdens het kalibratieproces vraagt HoloLens u om uw vinger uit te lijnen met een reeks van zes doelen per oog. HoloLens gebruikt dit proces om de IP-adress correct in te stellen voor uw ogen.

![Scherm voor uitlijning van IPD-vinger bij de tweede stap](./images/ipd-finger-alignment-300px.jpg)

### <a name="manually-start-the-calibration-process"></a>Handmatig het kalibratieproces starten

Als u de kalibratie moet bijwerken of als een nieuwe gebruiker deze moet aanpassen, kunt u de Kalibratie-app op elk moment handmatig uitvoeren. De kalibratie-app wordt standaard geïnstalleerd. U kunt deze openen met behulp van het menu **Start** of de app Instellingen.

Volg deze stappen **om het** menu Start te gebruiken om de kalibratie-app uit te voeren:

1. Gebruik de [bloembewegingen](hololens1-basic-usage.md) om het menu **Start te** openen.
1. Als u alle apps wilt weergeven, selecteert **+** u .
1. Selecteer **Kalibratie**.

![Toegang tot de kalibratie-app vanuit de shell](./images/calibration-shell.png)

![De kalibratie-app die wordt weergegeven als een livekubus nadat deze is gestart](./images/calibration-livecube-200px.png)

Volg deze stappen om de app Instellingen te gebruiken om de kalibratie-app uit te voeren:

1. Gebruik de [bloembewegingen](hololens1-basic-usage.md) om het menu **Start te** openen.
1. Als **Instellingen** niet is vastgemaakt aan **Start,** selecteert u om **+** alle apps weer te geven.
1. Selecteer **Instellingen**.
1. Selecteer   >  **Systeemprogramma's**  >  **Kalibratie openen.**

![De kalibratie-app starten vanuit de instellingen-app](./images/calibration-settings-500px.jpg)

## <a name="immersive-headsets"></a>Immersive headsets

Sommige immersive headsets bieden de mogelijkheid om de IPD-instelling aan te passen. Als u de IP-adres voor uw headset wilt wijzigen, opent u de app Instellingen en selecteert u **Mixed reality**  >  **Headset display** en verplaatst u vervolgens het schuifregelaar. U ziet de wijzigingen in realtime in uw headset. Als u uw IP-adres kent, kunt u deze ook rechtstreeks invoeren bij een bezoek aan de optometrist.

U kunt deze instelling ook op uw pc aanpassen door Instellingen  >  **Mixed Reality** Headset weer te  >  **geven.**

Als uw headset geen ondersteuning biedt voor IPD-aanpassing, wordt deze instelling uitgeschakeld.
