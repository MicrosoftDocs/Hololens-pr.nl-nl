---
title: De kwaliteit en het comfort van visuele elementen verbeteren
description: Meer informatie over het kalibreren van uw interpup aanvullende afstand (IPD) om de kwaliteit van uw visuals op HoloLens-apparaten te verbeteren.
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
keywords: kalibratie, comfort, visuals, kwaliteit, ipd, HoloLens, Windows Mixed Reality, VR headsets
ms.openlocfilehash: e975e2ccd978d4ec6b5331af0ae566af116711c5
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379363"
---
# <a name="improve-visual-quality-and-comfort"></a>De kwaliteit en het comfort van visuele elementen verbeteren

HoloLens 2 en HoloLens (1e generatie) werken beide beter wanneer ze naar uw unieke ogen worden ge kalibreerd.

Hoewel beide apparaten moeten kalibreren voor de beste hologramweergave, gebruiken ze verschillende technologieën en technieken voor kalibratie.  Ga naar [HoloLens 2 kalibratie](#calibrating-your-hololens-2) [of HoloLens-kalibratie (1e generatie).](#calibrating-your-hololens-1st-gen)

## <a name="calibrating-your-hololens-2"></a>Uw HoloLens 2

HoloLens 2 maakt gebruik van technologie voor het bijhouden van de gaten om uw ervaring met de virtuele omgeving te verbeteren en te gebruiken. Door de HoloLens 2 zorgt u ervoor dat uw ogen (en de ogen van anderen die het apparaat gebruiken) nauwkeurig kunnen worden gevolgd. Het helpt ook bij het comfort van gebruikers, de uitlijning van hologrammen en het bijhouden van de hand. Na de kalibratie worden hologrammen correct weergegeven, zelfs wanneer het visor op uw hoofd verschuift.

HoloLens 2 wordt een gebruiker gevraagd het apparaat te kalibreren onder de volgende omstandigheden:

- De gebruiker gebruikt het apparaat voor het eerst
- De gebruiker heeft zich eerder voor het kalibratieproces gekozen
- Het kalibratieproces is niet geslaagd de laatste keer dat de gebruiker het apparaat heeft gebruikt
- De gebruiker heeft zijn of haar profielen voor kalibratie verwijderd
- Het apparaat wordt uitgeschakeld en wordt weer aan gezet en een van de bovenstaande omstandigheden is van toepassing 


![Prompt voor het aanpassen van de ogen.](./images/07-et-adjust-for-your-eyes.png)

Tijdens dit proces bekijkt u een set doelen (gems). Het is prima als u tijdens de kalibratie knippert, maar probeer gericht te blijven op de gems in plaats van op andere objecten in de ruimte.  Door u te concentreren op de gems, kan HoloLens meer te weten komen over uw oogpositie om uw holografische wereld weer te geven.

![Prompt om de gebruiker te vragen om het hoofd stil te houden en punten met zijn ogen te volgen.](./images/07-et-hold-head-still.png)

![Prompt voor kalibratie met gem-voorbeeld.](./images/08-et-gems.png)

![Prompt voor het aanpassen van de kalibratie.](./images/09-et-adjusting.png)

Als de kalibratie is geslaagd, ziet u een successcherm.  Zo niet, dan kunt u meer lezen [over het diagnosticeren van fouten in de fouten](#troubleshooting-hololens-2-calibration)bij het analyseren van fouten.

![Prompt voor kalibratie geslaagd.](./images/10-et-success.png)

### <a name="calibration-when-sharing-a-device-or-session"></a>Kalibratie bij het delen van een apparaat of sessie

Meerdere gebruikers kunnen een apparaat HoloLens 2 delen, zonder dat elke persoon het apparaat hoeft in te stellen. Wanneer een nieuwe gebruiker het apparaat voor het eerst op zijn hoofd plaatst, HoloLens 2 de gebruiker automatisch gevraagd visuals te kalibreren. Wanneer een gebruiker die eerder ge kalibreerde visuals heeft, het apparaat op de kop zet, wordt het scherm naadloos aangepast voor kwaliteit en een gebruiksvriendelijke weergave.  

### <a name="manually-starting-the-calibration-process"></a>Handmatig het kalibratieproces starten

1. Gebruik de beweging Start om het menu [ **Start te** openen.](hololens2-basic-usage.md#start-gesture)
1. Als de app Instellingen niet is vastgemaakt aan **Start,** selecteert **u Alle apps.**
1. Selecteer **Instellingen** en selecteer vervolgens **Systeemorbratie**  >    >  **oogcontactEn**  >  **uitvoeren op oogen.**

   ![De app Instellingen, met de optie Ooguitbreeding uitvoeren](./images/C-Settings.Calibration.png)

### <a name="auto-eye-position-support"></a>Ondersteuning voor automatische oogpositie

In HoloLens 2 zorgen oogposities voor nauwkeurige positie van hologrammen, een gebruikservaring voor de weergave en verbeterde weergavekwaliteit. Oogposities worden intern berekend als onderdeel van de berekening van oogtracking. Dit vereist echter dat elke gebruiker de kalibratie van oogtracking doormaakt, zelfs wanneer voor de ervaring mogelijk geen ooginvoer nodig is.

**Auto Eye Position (AEP)** maakt deze scenario's mogelijk met een interactieloze manier om oogposities voor de gebruiker te berekenen. Automatische oogpositie werkt automatisch op de achtergrond vanaf het moment dat de gebruiker het apparaat in gebruik neemt. Als de gebruiker geen voorafgaande kalibratie voor het bijhouden van de oog heeft, geeft Automatische oogpositie de oogposities van de gebruiker aan het weergavesysteem na een verwerkingstijd van 20 tot 30 seconden. De gebruikersgegevens blijven niet op het apparaat behouden en dit proces wordt herhaald als de gebruiker opstart en het apparaat weer in- of uit de slaapstand zet.

Er zijn enkele wijzigingen in het systeemgedrag met de functie Automatische oogpositie wanneer een niet-gecalibreerde gebruiker het apparaat in gebruik neemt. In deze context verwijst een niet-gecalibreerde gebruiker naar iemand die het proces voor het traceren van de ogen op het apparaat niet eerder heeft doorlopen.

| Actieve toepassing | Eerder gedrag | Gedrag van Windows Holographic, versie 20H2 Update |
|:-------------------|:-----------------|:-----------------------------------|
| App zonder staren of Holographic Shell |Het dialoogvenster prompt voor het traceren van de ogen wordt weergegeven. | Er wordt geen prompt weergegeven. |
| Staren-app | Het dialoogvenster prompt voor het traceren van de ogen wordt weergegeven. | De prompt voor het bijhouden van de kalibratie wordt alleen weergegeven wanneer de toepassing toegang heeft tot de oogstream. |

Als de gebruiker overstapt van een toepassing zonder staren naar een toepassing die toegang heeft tot de staringsgegevens, wordt de prompt voor de kalibratie weergegeven. 

Al het andere systeemgedrag is vergelijkbaar met wanneer de huidige gebruiker geen actieve kalibratie van oogtracking heeft. Het eenhandige startgebaar wordt bijvoorbeeld niet ingeschakeld. De Out-Of-Box-Experience wordt niet gewijzigd voor de eerste installatie.

Voor ervaringen waarvoor oogcontactgegevens of nauwkeurige positie van hologrammen nodig zijn, raden we niet-gecalibreerde gebruikers aan om de kalibratie van oogtracking uit te voeren. U kunt de app openen via de prompt voor het traceren van de ogen of door de app Instellingen te starten vanuit het menu Start en vervolgens **Systeem > Kalibratie >** Ooginding > Run eye te selecteren.

#### <a name="deferred-calibration-prompt"></a>Uitgestelde vragen om uitstel

Met Automatische oogpositie wordt het dialoogvenster Oogvolgende kalibratieprompt uitgesteld totdat een toepassing oogcontactgegevens aanvraagt. Dit zorgt ervoor dat de gebruiker niet wordt gevraagd om te staren wanneer er geen staring nodig is voor de actieve toepassing. Als voor de toepassing wel staringsgegevens nodig zijn en de huidige gebruiker niet is ge kalibreerd, krijgt de gebruiker een prompt te zien. Dit gedrag kan worden gebruikt om de prompt voor het traceren van de ogen weer te geven op een geschikt tijdstip voor de ervaring. Deze methode wordt aanbevolen om de volgende redenen

1.  In het dialoogvenster Prompt voor het traceren van het oog krijgt de gebruiker informatie over waarom oogtracking nodig is.
2.  Biedt de gebruiker een manier om te weigeren om zijn ogen te kalibreren.

Als de gebruiker ervoor kiest om de eye tracking-kalibratie te starten, moet de focus terugkeren naar de oorspronkelijke toepassing nadat de kalibratie is voltooid. 

### <a name="troubleshooting-hololens-2-calibration"></a>Problemen met HoloLens 2 oplossen

Kalibratie zou voor de meeste mensen moeten werken, maar er zijn gevallen waarin de kalibratie mislukt.
  
Enkele mogelijke redenen voor het mislukken van de kalibratie zijn:

- Afgeleid raken en de kalibratiedoelen niet volgen
- Vervuilde of gekrast apparaat visor of apparaat visor niet goed geplaatst
- Vervuilde of gekraste bril
- Bepaalde soorten contactlenzen en bril (gekleurde contactlenzen, sommige tor-contactlenzen, blokkerende IR-bril, een bril met hoge bril, zonnebrillen of iets dergelijks)
- Meer uitgesprokenen en een aantal eyelash-extensies
- Frames met een haar of een dicht bril als ze blokkeren dat het apparaat uw ogen niet meer ziet
- Bepaalde oogbuien, oogomstandigheden of oogoperaties, zoals smalle ogen, lange oogslashen, amblyopie, nystagmus, sommige gevallen van LASIK of andere oogpieken

Als de kalibratie mislukt, probeert u het volgende:

- Uw apparaat-visor opsporing
- Uw bril opsnuurt
- Uw apparaat-visor zo dicht mogelijk bij uw ogen pushen
- Objecten in uw visor uit de weg verplaatsen (zoals haar)
- Een licht in uw kamer in- of uitschakelen

Als u alle richtlijnen hebt gevolgd en de kalibratie nog steeds mislukt, kunt u de prompt voor de kalibratie uitschakelen in Instellingen. Laat het ons ook weten door feedback in te dienen [Feedback-hub.](hololens-feedback.md)

Zie ook gerelateerde informatie over het oplossen van problemen [met de kleur of helderheid van afbeeldingen.](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)

Het instellen van IPD is niet van toepassing op HoloLens 2, omdat oogposities worden berekend door het systeem. 

### <a name="calibration-data-and-security"></a>Kalibratiegegevens en beveiliging

Kalibratiegegevens worden lokaal op het apparaat opgeslagen en zijn niet gekoppeld aan accountgegevens. Er is geen record van wie het apparaat zonder kalibratie heeft gebruikt. Dit betekent dat nieuwe gebruikers wordt gevraagd visuals te kalibreren wanneer ze het apparaat voor het eerst gebruiken, en dat gebruikers die zich eerder hebben voorgekoteerd voor kalibratie of als de kalibratie is mislukt.

Op het apparaat kunnen maximaal 50 kalibratieprofielen lokaal worden opgeslagen. Nadat dit aantal is bereikt, verwijdert het apparaat automatisch het oudste ongebruikte profiel.

Kalibratie-informatie kan altijd van het apparaat worden verwijderd in  >  **Instellingen Privacy**  >  **Oogtracker**.  

### <a name="disable-calibration"></a>Kalibrering uitschakelen

U kunt de prompt ook uitschakelen door de volgende stappen uit te voeren:

1. Selecteer **Instellingen Systeem**  >  **kalibratie.**  >  
1. Schakel Uit Wanneer een nieuwe persoon deze HoloLens gebruikt, automatisch om te vragen **om oogbrabratie uit te voeren.**

> [!IMPORTANT]
> Deze instelling kan een negatieve invloed hebben op de kwaliteit en het comfort van hologrammen.  Wanneer u deze instelling uit schakelen, werken functies die afhankelijk zijn van het bijhouden van de ogen (zoals het scrollen van tekst) niet meer in in immersieve toepassingen.

### <a name="hololens-2-eye-tracking-technology"></a>HoloLens 2 technologie voor het bijhouden van uw oog

Het apparaat maakt gebruik van de technologie voor het bijhouden van de ogen om de kwaliteit van de weergave te verbeteren en ervoor te zorgen dat alle hologrammen nauwkeurig en vertrouwd zijn om in 3D weer te geven. Omdat de ogen worden gebruikt als oriëntatiepunten, kan het apparaat zichzelf aanpassen voor elke gebruiker en de visuals afstemmen wanneer de headset iets verschuift tijdens het gebruik.  Alle aanpassingen worden op het eerste uur doorgevoerd zonder handmatige afstemming.
> [!NOTE]
> Het instellen van de IPD is niet van toepassing op Hololens 2, omdat oogposities worden berekend door het systeem.

HoloLens-toepassingen gebruiken oogtracking om bij te houden waar u in realtime naar op zoek bent. Dit is de belangrijkste mogelijkheid die ontwikkelaars kunnen gebruiken om een geheel nieuw niveau van context, menselijk begrip en interacties mogelijk te maken binnen de Holographic-ervaring. Ontwikkelaars hoeven niets te doen om deze mogelijkheid te kunnen gebruiken.

## <a name="calibrating-your-hololens-1st-gen"></a>Uw HoloLens (1e generatie) kalibreren

HoloLens (1e generatie) past de hologramweergave aan op basis van uw [interpupillale afstand](https://en.wikipedia.org/wiki/Interpupillary_distance) (IPD). Als de IPD niet nauwkeurig is, kunnen hologrammen instabiel of op een onjuiste afstand lijken. U kunt de kwaliteit van uw visuals verbeteren door het apparaat te kalibreren naar uw interpupillary distance (IPD).

Wanneer u uw HoloLens-apparaat (1e generatie) in stelt, wordt u gevraagd om uw visuals te kalibreren nadat Cortana zichzelf heeft introduceert. Het is raadzaam dat u de stap voor het kalibratieproces voltooit tijdens deze installatiefase. U kunt dit echter overslaan door te wachten totdat Cortana u vraagt en vervolgens 'Overslaan' zegt.

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
