---
title: De kwaliteit en het comfort van visuele elementen verbeteren
description: Meer informatie over het kalibreren van uw interpup aanvullende afstand (IPD) om de kwaliteit van uw visuals op HoloLens verbeteren.
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
ms.openlocfilehash: b3d917c71ac7441aeaf8dcbc25748ee07b9fbfa3
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189202"
---
# <a name="improve-visual-quality-and-comfort"></a>De kwaliteit en het comfort van visuele elementen verbeteren

HoloLens 2 en HoloLens (eerste generatie) werken beide beter wanneer ze naar uw unieke ogen worden ge kalibreerd.

Hoewel beide apparaten moeten kalibreren voor de beste hologramweergave, gebruiken ze verschillende technologieën en technieken voor kalibratie.  Ga naar [HoloLens 2 kalibratie](#calibrating-your-hololens-2) [of HoloLens (1e generatie) kalibratie](#calibrating-your-hololens-1st-gen).

## <a name="calibrating-your-hololens-2"></a>Uw HoloLens 2

HoloLens 2 maakt gebruik van technologie voor het bijhouden van de gaten om uw ervaring met de virtuele omgeving te verbeteren en te gebruiken. Door de HoloLens 2 zorgt u ervoor dat uw ogen (en de ogen van anderen die het apparaat gebruiken) nauwkeurig kunnen worden gevolgd. Het helpt ook bij het comfort van gebruikers, de uitlijning van hologrammen en het bijhouden van de hand. Na de kalibratie worden hologrammen correct weergegeven, zelfs wanneer het visor op uw hoofd verschuift.

HoloLens 2 gebruiker wordt gevraagd het apparaat te kalibreren onder de volgende omstandigheden:

- De gebruiker gebruikt het apparaat voor het eerst
- De gebruiker heeft zich eerder voor het kalibratieproces gekozen
- Het kalibratieproces is niet geslaagd de laatste keer dat de gebruiker het apparaat heeft gebruikt
- De gebruiker heeft zijn of haar kalibratieprofielen verwijderd
- Het apparaat wordt uitgeschakeld en wordt weer aan gezet en een van de bovenstaande omstandigheden is van toepassing 


![Prompt voor het aanpassen van de ogen.](./images/07-et-adjust-for-your-eyes.png)

Tijdens dit proces bekijkt u een set doelen (gems). Het is prima als u tijdens de kalibratie knippert, maar probeer gericht te blijven op de gems in plaats van andere objecten in de ruimte.  Door u te concentreren op de gems HoloLens meer te weten te komen over uw oogpositie om uw holografische wereld weer te geven.

![Prompt om de gebruiker te vertellen om het hoofd stil te houden en punten met hun ogen te volgen.](./images/07-et-hold-head-still.png)

![Prompt voor kalibratie met gem-voorbeeld.](./images/08-et-gems.png)

![Prompt voor het aanpassen van de kalibratie.](./images/09-et-adjusting.png)

Als de kalibratie is geslaagd, ziet u een successcherm.  Zo niet, dan kunt u meer lezen [over het diagnosticeren van fouten in de fouten](hololens2-display.md#troubleshooting)bij het analyseren van fouten.

![Prompt voor het slagen van de kalibratie.](./images/10-et-success.png)

### <a name="calibration-when-sharing-a-device-or-session"></a>Kalibratie bij het delen van een apparaat of sessie

Meerdere gebruikers kunnen een HoloLens 2 delen, zonder dat elke persoon het apparaat hoeft in te stellen. Wanneer een nieuwe gebruiker het apparaat voor het eerst op zijn hoofd plaatst, HoloLens 2 de gebruiker automatisch gevraagd visuals te kalibreren. Wanneer een gebruiker die eerder ge kalibreerde visuals heeft, het apparaat op de kop zet, wordt het scherm naadloos aangepast voor kwaliteit en een vertrouwd weergave-ervaring.  

### <a name="manually-starting-the-calibration-process"></a>Handmatig het kalibratieproces starten

1. Gebruik de beginbewegingen om de [**Startmenu.**](hololens2-basic-usage.md#start-gesture)
1. Als de Instellingen app niet is vastgemaakt aan **Start,** selecteert **u Alle apps.**
1. Selecteer **Instellingen** en selecteer vervolgens **Systeembrabrativiteit**  >    >  **Oogcontacten** uitvoeren op het  >  **oog.**

   ![De Instellingen app, met de optie Ooguitbreeding uitvoeren.](./images/C-Settings.Calibration.png)

### <a name="auto-eye-position-support"></a>Ondersteuning voor automatische oogpositie

In HoloLens 2 zorgen oogposities voor nauwkeurige positie van hologrammen, een gebruikservaring voor de weergave en verbeterde weergavekwaliteit. Oogposities worden intern berekend als onderdeel van de berekening voor het bijhouden van de ogen. Dit vereist echter dat elke gebruiker de kalibratie van oogtracking doormaakt, zelfs wanneer voor de ervaring mogelijk geen ooginvoer nodig is.

**Auto Eye Position (AEP)** maakt deze scenario's mogelijk met een interactieloze manier om oogposities voor de gebruiker te berekenen. Automatische oogpositie werkt automatisch op de achtergrond vanaf het moment dat de gebruiker het apparaat in gebruik neemt. Als de gebruiker geen voorafgaande kalibratie voor oogtracking heeft, geeft Automatische oogpositie de oogposities van de gebruiker aan het weergavesysteem na een verwerkingstijd van 20 tot 30 seconden. De gebruikersgegevens blijven niet behouden op het apparaat en dit proces wordt herhaald als de gebruiker opstart en het apparaat weer in- of uit de slaapstand zet.

Er zijn enkele wijzigingen in het systeemgedrag met de functie Automatische oogpositie wanneer een niet-gecalibreerde gebruiker het apparaat in gebruik neemt. In deze context verwijst een niet-gecalibreerde gebruiker naar iemand die het proces voor het traceren van de ogen op het apparaat niet eerder heeft doorlopen.

| Actieve toepassing | Eerder gedrag | Gedrag van Windows Holographic, versie 20H2 Update |
|:-------------------|:-----------------|:-----------------------------------|
| Niet-staren-app of Holographic Shell |Het dialoogvenster prompt voor het traceren van de ogen wordt weergegeven. | Er wordt geen prompt weergegeven. |
| Staren-app | Het dialoogvenster prompt voor het traceren van de ogen wordt weergegeven. | Prompt voor het traceren van de ogen wordt alleen weergegeven wanneer de toepassing toegang heeft tot de oogstream. |

Als de gebruiker overstapt van een toepassing zonder staren naar een toepassing die toegang heeft tot de staringsgegevens, wordt de prompt voor de kalibratie weergegeven. 

Al het andere systeemgedrag is vergelijkbaar met wanneer de huidige gebruiker geen actieve kalibratie van oogtracking heeft. Het eenhandige startgebaar wordt bijvoorbeeld niet ingeschakeld. De Out-Of-Box-Experience wordt niet gewijzigd voor de eerste installatie.

Voor ervaringen waarvoor oogcontactgegevens of nauwkeurige positie van hologrammen zijn vereist, raden we niet-gecalibreerde gebruikers aan om de kalibratie van oogtracking uit te voeren. De app is toegankelijk via de prompt voor het traceren van de oogtracking of door de Instellingen-app te starten vanuit het menu Start en vervolgens **Systeem >-kalibratie > oogcontacten te** selecteren > Oogregistratie uitvoeren.

#### <a name="deferred-calibration-prompt"></a>Uitgestelde vragen om uitstel

Met Automatische oogpositie wordt het dialoogvenster Oogvolgende kalibratieprompt uitgesteld totdat een toepassing oogcontactgegevens aanvraagt. Dit zorgt ervoor dat de gebruiker niet wordt gevraagd om te staren wanneer er geen staring nodig is voor de actieve toepassing. Als voor de toepassing staringsgegevens zijn vereist en de huidige gebruiker niet is ge kalibreerd, krijgt de gebruiker een prompt te zien. Dit gedrag kan worden gebruikt om de prompt voor het traceren van de ogen weer te geven op een geschikt tijdstip voor de ervaring. Deze methode wordt aanbevolen om de volgende redenen

1.  In het dialoogvenster Prompt voor het bijhouden van de oogvolgvolgendheden krijgt de gebruiker informatie over waarom oogtracking nodig is.
2.  Biedt de gebruiker een manier om te weigeren om zijn ogen te kalibreren.

Als de gebruiker ervoor kiest om de eye tracking-kalibratie te starten, moet de focus terugkeren naar de oorspronkelijke toepassing nadat de kalibratie is voltooid. 

### <a name="calibration-data-and-security"></a>Gegevens en beveiliging kalibreren

Kalibratie-informatie wordt lokaal op het apparaat opgeslagen en is niet gekoppeld aan accountgegevens. Er is geen record van wie het apparaat zonder kalibratie heeft gebruikt. Dit betekent dat nieuwe gebruikers wordt gevraagd visuals te kalibreren wanneer ze het apparaat voor het eerst gebruiken, en dat gebruikers die zich eerder hebben voorgekoteerd voor kalibratie of als de kalibratie is mislukt.

Op het apparaat kunnen maximaal 50 kalibratieprofielen lokaal worden opgeslagen. Nadat dit nummer is bereikt, verwijdert het apparaat automatisch het oudste ongebruikte profiel.

Kalibratie-informatie kan altijd worden verwijderd van het apparaat in **Instellingen**  >  **Privacy**  >  **Eye Tracker**.  

### <a name="disable-calibration"></a>Kalibrering uitschakelen

U kunt de prompt voor het terugprompt ook uitschakelen door de volgende stappen uit te voeren:

1. Selecteer **Instellingen**  >  **Systeem kalibratie**  >  .
1. Schakel Uit Wanneer een nieuwe persoon deze HoloLens gebruikt, automatisch om te vragen **om oogcontacten uit te voeren.**

   > [!IMPORTANT]
   > Deze instelling kan een negatieve invloed hebben op de kwaliteit en het comfort van hologrammen.  Wanneer u deze instelling uit schakelen, werken functies die afhankelijk zijn van het bijhouden van de ogen (zoals het scrollen van tekst) niet meer in in immersieve toepassingen.

> [!NOTE]
> De Instellingen is verwijderd vanaf Windows Holographic, versie 20H2 met het begin van [automatische oogpositieondersteuning.](hololens-release-notes.md#auto-eye-position-support) De prompt voor kalibratie wordt alleen automatisch weergegeven als een niet-gecalibreerde gebruiker een app met ingeschakelde oogtracking gebruikt.

### <a name="hololens-2-eye-tracking-technology"></a>HoloLens 2 technologie voor het bijhouden van uw oog

Het apparaat maakt gebruik van de technologie voor het bijhouden van de ogen om de kwaliteit van de weergave te verbeteren en ervoor te zorgen dat alle hologrammen nauwkeurig en vertrouwd zijn om in 3D weer te geven. Omdat het de ogen als oriëntatiepunten gebruikt, kan het apparaat zichzelf aanpassen voor elke gebruiker en de visuals afstemmen wanneer de headset iets verschuift tijdens het gebruik.  Alle aanpassingen worden op het eerste uur doorgevoerd zonder handmatige afstemming.
> [!NOTE]
> Het instellen van de IPD is niet van toepassing op Hololens 2, omdat oogposities worden berekend door het systeem.

HoloLens toepassingen gebruiken oogtracking om bij te houden waar u in realtime naar op zoek bent. Dit is de belangrijkste mogelijkheid die ontwikkelaars kunnen gebruiken om een geheel nieuw niveau van context, menselijk begrip en interacties mogelijk te maken binnen de Holographic-ervaring. Ontwikkelaars hoeven niets te doen om deze mogelijkheid te kunnen gebruiken.

## <a name="calibrating-your-hololens-1st-gen"></a>Uw HoloLens (eerste generatie)

HoloLens (1e generatie) past de hologramweergave aan op basis van uw [interpupillaire afstand](https://en.wikipedia.org/wiki/Interpupillary_distance) (IPD). Als de IPD niet nauwkeurig is, kunnen hologrammen instabiel of op een onjuiste afstand lijken. U kunt de kwaliteit van uw visuals verbeteren door het apparaat te kalibreren naar uw interpupillary distance (IPD).

Wanneer u uw apparaat HoloLens (eerste generatie) in te stellen, wordt u gevraagd om uw visuals te kalibreren nadat Cortana zichzelf introduceert. Het is raadzaam dat u de stap voor het kalibratieproces voltooit tijdens deze installatiefase. U kunt dit echter overslaan door te wachten totdat Cortana u wordt gevraagd en vervolgens 'Overslaan' te zeggen.

Tijdens het kalibratieproces wordt HoloLens gevraagd om uw vinger uit te lijnen met een reeks van zes doelen per oog. HoloLens dit proces gebruikt om het IP-adres correct in te stellen voor uw ogen.

![Scherm voor uitlijning van IPD-vinger bij de tweede stap.](./images/ipd-finger-alignment-300px.jpg)

### <a name="manually-start-the-calibration-process"></a>Handmatig het kalibratieproces starten

Als u de kalibratie moet bijwerken of als een nieuwe gebruiker deze moet aanpassen, kunt u de Kalibratie-app op elk moment handmatig uitvoeren. De kalibratie-app wordt standaard geïnstalleerd. U kunt deze openen met behulp van het menu **Start** of de Instellingen app.

Volg deze stappen **om het** menu Start te gebruiken om de Kalibratie-app uit te voeren:

1. Gebruik de [bloembewegingen](hololens1-basic-usage.md) om het menu **Start te** openen.
1. Als u alle apps wilt weergeven, selecteert **+** u .
1. Selecteer **Kalibratie**.

   ![Toegang tot de kalibratie-app vanuit de shell.](./images/calibration-shell.png)

   ![De kalibratie-app die wordt weergegeven als een livekubus nadat deze is gestart.](./images/calibration-livecube-200px.png)

Als u de app Instellingen gebruiken om de kalibratie-app uit te voeren, volgt u deze stappen:

1. Gebruik de [bloembewegingen](hololens1-basic-usage.md) om het menu **Start te** openen.
1. Als **Instellingen** niet is vastgemaakt aan **Start,** selecteert u om **+** alle apps weer te geven.
1. Selecteer **Instellingen**.
1. Selecteer   >  **Systeemprogramma's**  >  **Kalibratie openen.**

   ![De kalibratie-app starten vanuit de instellingen-app.](./images/calibration-settings-500px.jpg)

## <a name="immersive-headsets"></a>Immersive headsets

Sommige immersive headsets bieden de mogelijkheid om de IPD-instelling aan te passen. Als u de IP-adres voor uw headset wilt wijzigen, opent u de app Instellingen en selecteert u **Mixed Reality** Headset display en verplaatst u vervolgens het  >  schuifregelaar. U ziet de wijzigingen in realtime in uw headset. Als u uw IP-adres kent, kunt u deze ook rechtstreeks invoeren tijdens een bezoek aan de optometator.

U kunt deze instelling ook aanpassen op uw pc door Instellingen  >  **Mixed Reality** Headset weer te  >  **geven.**

Als uw headset geen ondersteuning biedt voor IPD-aanpassing, wordt deze instelling uitgeschakeld.
