---
title: HoloLens 2 problemen met weergaven oplossen
description: Verwachtingen voor HoloLens 2 weergegeven. Richtlijnen voor het configureren van weergaven voor de beste afbeeldingskwaliteit.
author: BrandonBray
ms.author: branbray
ms.date: 8/13/2020
ms.topic: article
keywords: weergave, kalibratie, comfort, visuals, kwaliteit, ipd
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
appliesto:
- HoloLens 2
ms.openlocfilehash: 96bacd79d559bc0adcd42665c4a8b4af856b58b0
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923615"
---
# <a name="hololens-2-display-troubleshooting"></a>HoloLens 2 problemen met weergaven oplossen

## <a name="overview"></a>Overzicht
De HoloLens 2 is een combinatie van waveguides en lichte projectors. Gebruikers kijken door de waveguides( de lenzen in het visor) bij het dragen van de headset. De lichte projectors bevinden zich in de behuizing boven de brow. HoloLens 2 maakt gebruik van laserlicht om de weergave te belichten.

## <a name="troubleshooting"></a>Problemen oplossen

Volg de volgende stappen om de hoogste visuele kwaliteit van hologrammen in weergaven te garanderen:

* **Vergroot de helderheid van de weergave.** Hologrammen zien er het beste uit wanneer de weergave op het helderste niveau is. Wanneer u de HoloLens draagt, staan de helderheidsknoppen aan de linkerkant van het visor in de buurt van uw masker.
* **Breng de visor dichter bij uw ogen.** Draai de visor omlaag naar de dichtstbijzijnde positie voor uw ogen.
* **Shift visor omlaag.** Beweeg hetrow-pad naar beneden, wat ertoe leidt dat het visor dichter bij uw neus omlaag beweegt.
* **[Voer oogcontacten uit.](hololens-calibration.md#calibrating-your-hololens-2)** De weergave maakt gebruik van uw interpupillary distance (IPD) en oogcontact om afbeeldingen op de weergave te optimaliseren. Als u geen oogcontacten maakt, kan de kwaliteit van de afbeelding slechter worden. Als u oogsentatie wilt uitvoeren, gaat u naar **Instellingen**  >  **Systeem voor**  >  **kalibratie** Run  >  **eye-kalibratie.**
* **Voer de weergavekleur uit.** Op [Windows Holographic, versie 21H1](hololens-release-notes.md#windows-holographic-version-21h1) en  meer, kunt u een alternatief kleurprofiel selecteren voor uw HoloLens 2 weergave. Hierdoor kunnen kleuren nauwkeuriger worden weergegeven, met name bij lagere helderheidsniveaus. Kleurenweergave vindt u in de app **Instellingen** op de pagina Systeem > **Kalibratie.**

    > [!NOTE]
    > Omdat deze instelling een nieuw kleurprofiel op uw weergavefirmware op slaat, is het een instelling per apparaat (en niet uniek voor elk gebruikersaccount).

### <a name="how-to-use-display-color-calibration"></a>Weergavekleuren gebruiken
1. Start de **app Instellingen** en navigeer naar System **> Navigate.**
1. Selecteer **onder Kleurenbratie weergeven** de knop **Weergavekleur afstemmen** uitvoeren.
1. De ervaring voor het kalibreren van de weergavekleur wordt gelanceerd en u wordt aansporen om ervoor te zorgen dat uw visor de juiste positie heeft.
1. Nadat u de instructiedialoogvensters hebt doorgenomen, wordt uw weergave automatisch lichter gekleurd tot 30% helderheid.
    > [!TIP]
    > Als u problemen hebt met het zien van de lichter gekleurde scène in uw omgeving, kunt u het helderheidsniveau van de HoloLens 2 handmatig aanpassen met behulp van de helderheidsknoppen aan de linkerkant van het apparaat.
1. Selecteer knoppen 1-6 om elk kleurprofiel direct uit te proberen en zoek een profiel dat het beste bij uw ogen past (dit betekent meestal het profiel waarmee de scène het meest neutraal wordt weergegeven, met het grijstintenpatroon en de skin-uiterlijk zoals verwacht.)

    ![Kleurenscène voor kalibratie weergeven](images/color-cal-ui.png)
    
6. Wanneer u tevreden bent met het geselecteerde profiel, selecteert u de knop **& afsluiten**
1. Als u liever geen wijzigingen aan te brengen, selecteert u de knop **& annuleren** om uw wijzigingen terug te keren

> [!TIP]
> Hier vindt u enkele handige tips om rekening mee te houden bij het gebruik van de instelling voor het kalibratie van de weergavekleur:
> - U kunt weergavekleuren opnieuw uitvoeren vanuit Instellingen wanneer u wilt
> - Als iemand op het apparaat de instelling eerder heeft gebruikt om kleurprofielen te wijzigen, wordt de datum/tijd van de meest recente wijziging weergegeven op de pagina Instellingen
> - Wanneer u de weergavekleur opnieuw uitwerkt, wordt het kleurenprofiel dat eerder is opgeslagen gemarkeerd en wordt Profiel 0 niet weergegeven (profiel 0 vertegenwoordigt het oorspronkelijke kleurprofiel van de weergave)
> - Als u wilt terugkeren naar het oorspronkelijke kleurenprofiel van de weergave, kunt u dit doen op de pagina Instellingen (zie Het [kleurprofiel opnieuw instellen)](#how-to-reset-color-profile)

### <a name="how-to-reset-color-profile"></a>Kleurenprofiel opnieuw instellen

Als u ontevreden bent over het aangepaste kleurprofiel dat is opgeslagen op uw HoloLens 2, kunt u het oorspronkelijke kleurprofiel van het apparaat herstellen:
1. Start de **app Instellingen** en navigeer naar System **> Navigate.**
1. Selecteer **onder Kleurenbratie weergeven** de knop **Standaardkleurprofiel opnieuw** instellen.
1. Wanneer het dialoogvenster wordt geopend, selecteert u **Opnieuw** opstarten als u klaar bent om de HoloLens 2 en de wijzigingen toe te passen.

### <a name="top-display-color-calibration-known-issues"></a>Bekende problemen met de kleur van de bovenste weergavekleur

- Op de pagina Instellingen is de statusreeks die u vertelt wanneer het kleurprofiel voor het laatst is gewijzigd, verouderd totdat u die pagina met instellingen opnieuw laadt 
    - **Tijdelijke oplossing:** selecteer een andere pagina Instellingen en selecteer vervolgens opnieuw de pagina Kalibratie.
- Als uw HoloLens 2 gaat in de slaapstand tijdens het uitvoeren van weergavekleuren, wordt deze later hervat in de Mixed Reality Startpagina en wordt uw helderheidsniveau van de weergave nog steeds lichter gekleurd.
- Mogelijk moet u de helderheidsknoppen aan de linkerkant van uw apparaat een paar keer omhoog/omlaag drukken voordat ze werken zoals verwacht.
- Lokalisatie is niet voor alle markten voltooid

## <a name="faq"></a>Veelgestelde vragen

### <a name="what-are-the-patterns-that-occasionally-flash-in-the-bottom-corners-of-the-display"></a>Wat zijn de patronen die af en toe in de onderste hoeken van de weergave knipperen?

Af en toe worden HoloLens 2 in de linkeronder- en rechterhoek van de weergave verschillende patronen weergegeven. Voorbeelden worden hieronder weergegeven (GIF-animaties). Dit patroon maakt deel uit van de normale werking van HoloLens 2 apparaat om de weergave te kalibreren voor een optimale ervaring.

![Biphase-patroon](./images/DAT-Biphase-Fiducial.gif) ![GEO-patroon](./images/DAT-GEO-Fiducial.gif)

### <a name="why-am-i-unable-to-take-an-accurate-photograph-of-my-hololens-2-display"></a>Waarom kan ik geen nauwkeurige foto van mijn HoloLens 2 maken?

De HoloLens 2 is ontworpen om door het menselijk oog te worden bekeken. Het apparaat heeft een actief systeem voor kleurcorrectie dat zich aanpast aan de ogen van een gebruiker. Vergeleken met het menselijk oog zien camera's omgevingen anders en hieronder zijn enkele factoren die van invloed kunnen zijn op inconsistenties tussen wat een camera vast legt en wat een gebruiker ziet.

* **Oogpositie.** De HoloLens 2 is specifiek ontworpen voor de oogpositie van de gebruiker. De HoloLens 2 maakt gebruik van technologie voor het bijhouden van de ogen om zich aan te passen aan de oogpositie van de gebruiker. Een camera die door een paar millimeters verkeerd is geseed, kan leiden tot afbeeldingsverstoring. Nauwkeurige positiebepaling met een camera is moeilijk en moet overeenkomen met de exacte locatie en oogvermindering waarvoor het apparaat kleurcorrecties moet uitvoeren.
* **Oogbewegingen.** De weergave past zich aan de beweging van het oog van een gebruiker aan om de kleuren aan te passen. Wat er op de weergave wordt weergegeven, kan verschillen, afhankelijk van of de gebruiker naar het midden, de rand of de hoek van het scherm kijkt. Eén afbeeldingsopname kan in het beste beste alleen laten zien hoe de weergave eruitziet voor de as die overeenkomt met een oogcontactrichting.
* **Binotaalweergave.** De HoloLens 2 is ontworpen om met beide ogen te worden weergegeven. Het brein past zich aan het zien van twee afbeeldingen aan en combineert ze met elkaar. Afbeeldingen van slechts één weergave negeren de informatie van de andere weergave.
* **Tijd van camerablootstelling.** De blootstellingstijd van de camera moet exact een veelvoud van 1/120e van een seconde zijn. De HoloLens-weergaveframesnelheid is 120 Hz. Vanwege de manier waarop de HoloLens 2 afbeeldingen tekent, is het vastleggen van één frame ook niet voldoende om overeen te komen met de visuele ervaring van een mens. Tegelijkertijd projecteert het systeem de afbeelding opnieuw op de weergave om hologrammen te stabiliseren, zelfs micromovementen. Voor het vastleggen van meerdere frames terwijl de HoloLens niet wordt verplaatst, is meestal een laboratoriuminstallatie vereist.
* **De grootte van het camera-aperture.** De grootte van de camera moet ten minste 3 mm zijn om een nauwkeurige afbeelding vast te leggen. Mobiele telefooncamera's met kleine openingen integreren licht van een kleiner gebied dan het menselijke oog. Het apparaat past kleurcorrectie toe voor patronen die worden waargenomen door grotere openingen. Bij kleine openingen zijn uniformiteitspatronen steeds beter en blijven ze zichtbaar ondanks kleurcorrecties die door het systeem worden toegepast.
* **Camera-ingangsdekomer.** De ingang van de camera moet minimaal 3 mm in dediameter zijn om een nauwkeurige afbeelding vast te leggen. Anders legt de camera enkele patronen met een hoge frequentie vast die niet zichtbaar zijn voor het oog. De positie van de insluitingsleerling moet zich zowel vóór de camera bevinden als worden geplaatst bij de afstand tot de verlichting van de ogen om te voorkomen dat er afwijkingen en andere variaties op de vastgelegde afbeelding worden introduceren.
* **Camerapositie.** Camera's die voldoen aan de vereisten om de HoloLens 2-weergave weer te geven, zijn groter en het is moeilijk om de camera dicht genoeg bij de HoloLens 2 te plaatsen om de kleur van de afbeelding te bekijken. Als de camera op de verkeerde plaats staat, kan de kleurcorrectie een negatieve invloed hebben op het vastleggen van HoloLens 2 weergave.
* **Correctie van afbeeldingen.** Typische digitale camera's en smartphonecamera's passen een toonreproductiecurve (TRC) toe die het contrast en de kleur verbetert om een beter resultaat te bieden. Wanneer deze wordt toegepast op HoloLens 2 weergave, versterkt deze tooncurve niet-uniformiteiten.

Het is echter nog steeds mogelijk dat gespecialiseerde industriële camera's representatieve afbeeldingen van de HoloLens 2 vastleggen. Helaas kunnen smartphone-, consumenten- en professionele camera's geen afbeeldingen vastleggen die overeenkomen met wat een gebruiker in de HoloLens 2.

### <a name="what-does-eye-calibration-do-to-display-image-quality"></a>Wat doet oog kalibratie om de kwaliteit van de afbeelding weer te geven?

De HoloLens 2 actieve kleur corrigeert afbeeldingen op basis van de positie van de ogen van de gebruiker. [Ooginteractie](hololens-calibration.md) biedt twee belangrijke invoer: (1) de interpupillary afstand (IPD) van de gebruiker en (2) de richting waar elk oog naar kijkt. Zonder oogbewegingen krijgt het systeem standaard een nominale oogpositie zonder oogbewegingen. Het verschil tussen actieve kleurcorrectie en geen correctie is afhankelijk van de heid van de gebruiker zelf. Gebruikers met dezelfde IPD als de standaardinstelling van het systeem zien bijvoorbeeld minder kleurcorrectieverbeteringen. Hoewel gebruikers die een veel smallere of bredere IP-adres hebben dan de standaardinstelling van het systeem, zien meer wijzigingen in de weergaveafbeelding.

Let op: een nieuwe functie in [Windows Holographic versie 20H2](hololens-release-notes.md#windows-holographic-version-20h2) begint automatisch met het detecteren [van de oogpositie.](hololens-calibration.md#auto-eye-position-support) 

### <a name="what-are-the-display-differences-between-hololens-1st-gen-and-hololens-2"></a>Wat zijn de weergaveverschillen tussen HoloLens (eerste generatie) en HoloLens 2?

Een van de belangrijkste aanvragen die klanten Microsoft hebben gegeven na het ervaren van HoloLens 1 was (1) het verhogen van het gezichtsveld en (2) de helderheid verhogen. Dankzij technologieontwikkelingen kon Microsoft waveguides produceren die het gebied van het gezichtsveld verdubbelden en lichte projectors produceren met een weergave die maximaal drie keer zo groot is. De hardware stelt de basislijn in voor een groot aantal afwegingen voor de kwaliteit van de weergaveafbeelding: (1) veldweergave, (2) helderheid en (3) kleur uniformiteit. Voortdurende vooruitgang in de technologie maakt verbeteringen op alle gebieden mogelijk zonder dat dit ten koste gaat van een ander gebied. In de tussentijd stelt de bestaande technologie de limieten in die beschikbaar zijn voor deze afwegingen.

### <a name="what-improvements-are-coming-that-will-improve-hololens-2-image-quality"></a>Welke verbeteringen komen er aan die de kwaliteit van HoloLens 2 verbeteren?

Hoewel er veel onderzoeken worden gedaan om de kwaliteit van de afbeelding te verbeteren, worden de volgende gebieden verwacht in toekomstige updates:

* **Automatische oogpositie.** Met deze functie kunnen de procedures voor het kalibratieproces van het oog op de achtergrond worden uitgevoerd. Gebruikers hoeven geen oogcorrectie meer uit te voeren om actieve kleurcorrectie te laten werken. In plaats daarvan werkt het gewoon.
* **Verbeteringen in kleurbratie.** Deze update is gericht op kleurwaarden van donkere kleuren (bijvoorbeeld donkergrijs). Op dit moment krijgen de dimmerkleuren een rode kleur. Dit probleem doet zich ook voor wanneer het hele scherm grijs wordt weergegeven: het hele scherm haalt rode kleuren op. Dit probleem is het gevolg van te veel activiteit in het rode kleurkanaal voor deze donkere kleuren. We hebben de curven van de laserkrommen bij deze dimmerkleuren gekenmerkt en werken aan een procedure voor het kalibratieproces van de gebruiker. Het resultaat is meer kleurnauwkeurigheid in het helderheids spectrum. Het uiterlijk van witte achtergronden wordt niet gewijzigd bij volledige helderheid. We blijven het gebruik van ontwerppatronen in de donkere modus in apps adviseren.
* **Leesmodus.** Het is mogelijk voor app-ontwikkelaars om een afweging te maken tussen het weergaveveld om een hogere angular resolutie te bereiken. App-ontwikkelaars kunnen de projectiematrix overschrijven zodat inhoud wordt weergegeven op de tekenresolutie van de weergave. Deze functie resulteert in een vermindering van het veld van 30% en een overeenkomstige toename van de angular-resolutie. Er wordt gewerkt om deze mogelijkheid te introduceren in [de Mixed Reality Toolkit](https://github.com/Microsoft/MixedRealityToolkit-Unity). Indien beschikbaar, werkt de leesmodus op elk HoloLens 2 besturingssysteem. Deze is niet afhankelijk van een update van het besturingssysteem.

Updates van het besturingssysteem worden automatisch geleverd. U kunt ook vroege versies van softwareverbetering testen via het insider preview-programma.

### <a name="what-guidance-is-available-for-developers-to-apply-dark-mode-design-principles"></a>Welke richtlijnen zijn beschikbaar voor ontwikkelaars om ontwerpprincipes voor donkere modus toe te passen?

Gebruikers hebben de beste ervaring bij het vermijden van witte achtergronden. Donkere modus is een ontwerpprincipe dat door apps wordt gebruikt om een zwarte of donkergekleurde achtergrond te gebruiken. De systeeminstellingen worden standaard ingesteld op de donkere modus en kunnen worden aangepast door naar **Systeemkleur**  >  **van instellingen te**  >  **gaan.**

Ontwikkelaars wordt aangeraden de richtlijnen voor het ontwerp van de donkere modus te volgen:

* [Ontwerprichtlijnen voor ontwikkelaars voor HoloLens worden weergegeven](https://docs.microsoft.com/windows/mixed-reality/designing-content-for-holographic-display#design-guidelines)
* [Aanbevolen tekengrootten](https://docs.microsoft.com/windows/mixed-reality/typography#recommended-font-size)

Wanneer een hologram een witte achtergrond vereist, moet u de grootte van het hologram kleiner houden dan het volledige weergaveveld van de weergave. Met deze grootte kunnen gebruikers het hologram in het midden van de weergave zetten.

### <a name="how-do-you-clean-a-hololens-2-display"></a>Hoe schoont u een HoloLens 2 op?

Gebruik een microfiber om het visor te wissen. Als u de visor wilt opsnulken, gebruikt u 70% isopropyllak om een mond licht te maken en vervolgens het visor te wissen. Lees de volledige richtlijnen in de [veelgestelde HoloLens 2 over het opruimen van .](hololens2-maintenance.md)
