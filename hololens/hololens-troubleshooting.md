---
title: Problemen oplossen
description: Blijf op de hoogte van de meest voorkomende oplossingen voor Problemen met HoloLens-apparaten en technieken voor probleemoplossing.
author: mattzmsft
ms.author: mazeller
ms.date: 12/02/2019
ms.prod: hololens
ms.topic: article
audience: HoloLens
ms.localizationpriority: medium
manager: jarrettr
ms.custom:
- CI 111456
- CSSTroubleshooting
keywords: problemen, bug, probleem, oplossen, oplossen, hulp, ondersteuning, HoloLens
ms.openlocfilehash: 1039af533b5039eb4eef6599c7cbb480955b0661
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/25/2021
ms.locfileid: "111377875"
---
# <a name="troubleshoot-common-issues"></a>Algemene problemen

In dit artikel wordt beschreven hoe u verschillende veelvoorkomende problemen met HoloLens kunt oplossen.

## <a name="my-hololens-is-unresponsive-or-wont-start"></a>Mijn HoloLens reageert niet of start niet

Als uw HoloLens niet start:

- Als de LED's naast de aan/uit-knop niet worden licht of slechts één LED kort knippert, moet u uw [HoloLens mogelijk laden.](hololens-recovery.md#charge-the-device)
- Als de LED's worden weergegeven wanneer u op de aan/uit-knop drukt, maar er niets wordt weergegeven, moet u het apparaat hard [opnieuw instellen.](hololens-recovery.md#hard-reset-procedure)

Als uw HoloLens bevroren of niet meer reageert:

- Schakel uw HoloLens uit door op de aan/uit-knop te drukken totdat alle vijf de LED's zichzelf uitschakelen of 15 seconden lang als de LED's niet reageren. Als u uw HoloLens wilt starten, drukt u opnieuw op de aan/uit-knop.

Als deze stappen niet werken, [](hololens-recovery.md) kunt u proberen uw HoloLens 2 of [HoloLens-apparaat (1e generatie) te herstellen.](hololens1-recovery.md)

## <a name="holograms-dont-look-good"></a>Hologrammen zien er niet goed uit

Als uw hologrammen instabiel of jumpy zijn of er niet goed uitzien, probeert u het volgende:

- De visor en sensorbalk van uw apparaat aan de voorzijde van uw HoloLens opsporen.
- Het licht in uw ruimte vergroten.
- Loop rond en kijk naar uw omgeving, zodat HoloLens ze vollediger kan scannen.
- Uw HoloLens voor uw ogen laten eren. Ga naar **Instellingen**  >    >  **Systeemprogramma's.** Selecteer **onder Kalibratie** de **optie Kalibratie openen.**
 
### <a name="reporting-issues-where-holograms-are-unstable-or-dont-look-right"></a>Problemen melden waarbij hologrammen instabiel zijn of er niet goed uitzien
 
1. Neem een video en [een Vastleggen in mixed reality van](holographic-photos-and-videos.md#capture-a-mixed-reality-video) het probleem op. Deze video kan later worden geüpload via Feedback-hub als een bijgevoegd bestand.  
1. Schakel volledige telemetrie in via de **app** Instellingen -> **Privacy**  ->  **Diagnostics & feedback**  en controleer onder Optionele diagnostische gegevens of de schakelknop is ingesteld op **Aan**
1. Haal de nieuwste hologramschaal- en stabiliteitsfixes op door bij te werken naar het nieuwste [Windows Holographic-besturingssysteem (20H2 of hoger).](hololens-release-notes.md#windows-holographic-version-20h2) Voer na het bijwerken het volgende uit:
    1. Verwijder alle hologrammen **via** de app Instellingen -> **System**  ->  **Holograms** -> selecteer vervolgens **Alle hologrammen** verwijderen en begin met een nieuwe kaart.
    1. Maak een nieuwe kaart van uw ruimte door de HoloLens te dragen en door uw kamer te lopen en alle gebieden en vlakken in de ruimte te bekijken. Doe dit 2-3 minuten.
    1. Voer IPD-kalibratie uit. Ga naar **Instellingen**  >    >  **Systeemprogramma's.** Selecteer **onder Kalibratie** de **optie Kalibratie openen.**
    1. Test het scenario opnieuw en kijk of het scenario nog steeds wordt uitgevoerd.
1. Als het probleem niet wordt opgelost door bij te werken, kunt u een [Feedback-hub indienen.](hololens-feedback.md) Nadat u feedback hebt ingevuld, kunt u de knop **Delen** gebruiken om een eenvoudig te delen koppeling te maken die kan worden verzonden wanneer u contact op met de ondersteuning op neem.

## <a name="hololens-doesnt-respond-to-hand-input"></a>HoloLens reageert niet op handinvoer

Om ervoor te zorgen dat HoloLens uw handen kan zien, moet u ze in het bewegingsframe houden.  De Mixed Reality Start geeft feedback waarmee u kunt zien wanneer uw handen worden bijgespoord.  De feedback is anders voor verschillende versies van HoloLens:
- Op HoloLens (1e generatie) verandert de muisaanwijzer van een punt in een ring
- Op HoloLens 2 wordt een cursor met de muisaanwijzer weergegeven wanneer uw hand zich dicht bij een slate en een hand ray wordt weergegeven wanneer de slates verder weg zijn

Veel in immersieve apps volgen invoerpatronen die vergelijkbaar zijn met Mixed Reality Start.  Meer informatie over het gebruik van handinvoer [op HoloLens (1e generatie)](hololens1-basic-usage.md#use-hololens-with-your-hands) en [HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame).

Als u een handje draagt, moet u er rekening mee houden dat sommige soorten handjes niet werken bij het bijhouden van de hand.  Een veelvoorkomende voorbeeld is zwarte rubberen pakken, die de neiging hebben om licht te nemen en niet worden opgepikt door de dieptecamera.  Als uw werk bestaat uit een blauwe of grijze kleur, raden we u aan om een lichtere kleur te gebruiken, zoals blauw of grijs.  Een ander voorbeeld zijn grote baggy gloves, die de vorm van uw hand doorgaans verborgen houden. We raden u aan om voor de beste resultaten zo goed mogelijk vorm te geven.

Als uw visor vingerafdrukken of smudges heeft, gebruikt u de microfiberschoonmaak die bij de HoloLens werd gebruikt om uw visorgemiddelde op te schonen.

## <a name="hololens-doesnt-respond-to-my-voice-commands"></a>HoloLens reageert niet op mijn spraakopdrachten

Als Cortana niet reageert op uw spraakopdrachten, moet u ervoor zorgen dat Cortana is ingeschakeld. Selecteer in Alle apps de lijst **Cortana**  >  **Menu**  >  **Notebook**  >  **Settings om** wijzigingen aan te brengen. Zie Uw stem gebruiken met [HoloLens](hololens-cortana.md)voor meer informatie over wat u kunt zeggen.

## <a name="i-cant-place-holograms-or-see-holograms-that-i-previously-placed"></a>Ik kan geen hologrammen plaatsen of hologrammen zien die ik eerder heb geplaatst

Als HoloLens uw ruimte niet kan in kaart brengen of laden, wordt de beperkte modus gebruikt en kunt u geen hologrammen plaatsen of hologrammen zien die u hebt geplaatst. U kunt het volgende proberen:

- Zorg ervoor dat uw omgeving voldoende licht heeft, zodat HoloLens de ruimte kan zien en in kaart kan brengen.
- Zorg ervoor dat u bent verbonden met een Wi-Fi netwerk. Als u niet bent verbonden met Wi-Fi, kan HoloLens geen bekende ruimte identificeren en laden.
- Als u een nieuwe ruimte wilt maken, maakt u verbinding met Wi-Fi en start u de HoloLens opnieuw op.
- Als u wilt zien of de juiste ruimte actief is of als u handmatig een spatie wilt laden, gaat u naar  >  **Instellingen Systeemruimten.**  >  
- Als de juiste ruimte is geladen en u nog steeds problemen hebt, is de ruimte mogelijk beschadigd. U kunt dit probleem oplossen door de spatie te selecteren en vervolgens **Verwijderen te selecteren.** Nadat u de ruimte hebt verwijderd, begint HoloLens met het in kaart brengen van uw omgeving en het maken van een nieuwe ruimte.

## <a name="my-hololens-cant-tell-what-space-im-in"></a>Mijn HoloLens kan niet zien in welke ruimte ik me

Als uw HoloLens de ruimte waarin u zich in zich hebt niet automatisch kan identificeren en laden, controleert u de volgende factoren:

- Zorg ervoor dat u bent verbonden met Wi-Fi
- Zorg ervoor dat er voldoende licht in de ruimte is
- Zorg ervoor dat er geen belangrijke wijzigingen zijn aangebracht in de omgeving.

U kunt een ruimte ook handmatig laden of uw ruimten beheren door naar **Instellingen**  >  **Systeemruimten te**  >  **gaan.**

## <a name="im-getting-a-low-disk-space-error"></a>Ik krijg de fout 'weinig schijfruimte'

U moet opslagruimte vrij maken door een of meer van de volgende dingen te doen:

- Verwijder enkele ongebruikte spaties. Ga naar **Instellingen**  >  **Systeemruimten,** selecteer een spatie die u niet meer nodig hebt  >  en selecteer **vervolgens Verwijderen.**
- Verwijder enkele hologrammen die u hebt geplaatst.
- Verwijder enkele afbeeldingen en video's uit de app Foto's.
- Verwijder enkele apps van uw HoloLens. Tik in **Alle apps** lijst op de app die u wilt verwijderen en houd deze in de wacht. Selecteer **vervolgens Verwijderen.**

## <a name="my-hololens-cant-create-a-new-space"></a>Mijn HoloLens kan geen nieuwe ruimte maken

Het meest waarschijnlijke probleem is dat u weinig opslagruimte hebt. Probeer een van de [vorige tips uit om](#im-getting-a-low-disk-space-error) wat schijfruimte vrij te maken.

## <a name="the-hololens-emulator-isnt-working"></a>De HoloLens-emulator werkt niet

Informatie over de HoloLens-emulator vindt u in onze documentatie voor ontwikkelaars.  Lees meer over het [oplossen van problemen met de HoloLens-emulator](https://docs.microsoft.com/windows/mixed-reality/using-the-hololens-emulator#troubleshooting).
