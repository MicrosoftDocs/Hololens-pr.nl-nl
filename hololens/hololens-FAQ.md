---
title: Veelgestelde vragen over HoloLens en hologrammen
description: Hebt u een korte vraag over het HoloLens of interactie met hologrammen?  Dit artikel bevat een snel antwoord en meer resources.
keywords: hololens, veelgestelde vragen, bekend probleem, help
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
ms.date: 02/27/2020
ms.reviewer: ''
ms.custom:
- CI 114606
- CSSTroubleshooting
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ae44ae1d9a2e088a1ef746f4e929e8fae73880bf
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428380"
---
# <a name="holograms-and-interactions-troubleshooting"></a>Hologrammen en interacties oplossen

In dit artikel worden problemen opgelost met het plaatsen van hologrammen, het werken met ruimten en het rapporteren van problemen met hologrammen.

Zorg er altijd voor dat u problemen hebt:
- Probeer [deze opnieuw op te starten](hololens-restart-recover.md) om te zien of de problemen daarmee worden opgelost.
- Voordat u problemen gaat oplossen, moet u HoloLens kosten in [rekening worden gebracht](hololens2-charging.md) (minimaal een uur in rekening gebracht). 


Gebruik de feedback-app om ons informatie over het probleem te sturen. U vindt de feedback-app in het [ **menu** Start.](holographic-home.md) 

Zie Aanpassen aanpassen voor tips over het HoloLens van [uw telefoon.](hololens2-setup.md#adjust-fit)

<a id="list"></a>
- [Er kunnen geen nieuwe spaties worden gemaakt](#new-spaces-cant-be-created)
- [Spaties kunnen niet worden geïdentificeerd of geladen](#spaces-cant-be-identified-or-loaded)
- [Hoe kan ik alle spaties verwijderen?](#how-do-i-delete-all-spaces)
- [Hologrammen er niet goed uitzien of zich verplaatsen](#holograms-dont-look-right-or-are-moving-around)
- [Bericht 'Uw ruimte zoeken'](#finding-your-space-message)
- [Verwachte hologrammen worden niet weergegeven in mijn ruimte](#expected-holograms-arent-showing-in-my-space)
- [Kan geen hologrammen plaatsen of eerder geplaatste hologrammen zien](#cant-place-holograms-or-see-previously-placed-holograms)
- [Hologrammen verdwijnen of zijn ingepakt in andere hologrammen of objecten](#holograms-disappear-or-are-encased-in-other-holograms-or-objects)
- [Hologrammen worden weergegeven aan de andere kant van een wand](#holograms-are-appearing-on-the-other-side-of-a-wall)
- [Nadat een hologram op een wand is geplaatst, lijkt het te zweven](#after-placing-a-hologram-on-a-wall-it-seems-to-float)
- [Apps worden te dicht bij elkaar weergegeven nadat ze zijn verplaatst](#apps-appear-too-close-after-moving-them)
- [Problemen melden met instabiele of inexacte hologrammen](#reporting-issues-with-unstable-or-inexact-holograms)

## <a name="new-spaces-cant-be-created"></a>Er kunnen geen nieuwe spaties worden gemaakt

Het meest waarschijnlijke probleem is dat u weinig opslagruimte hebt. [U kunt schijfruimte vrij maken](hololens-troubleshooting.md#low-disk-space-error) en het vervolgens opnieuw proberen.

[Terug naar lijst](#list)

## <a name="spaces-cant-be-identified-or-loaded"></a>Spaties kunnen niet worden geïdentificeerd of geladen

Als uw HoloLens de ruimte waarin u zich in zich hebt niet automatisch kan identificeren en laden, controleert u de volgende factoren:

- Zorg ervoor dat u bent verbonden met Wi-Fi
- Zorg ervoor dat er voldoende licht in de ruimte is
- Zorg ervoor dat er geen belangrijke wijzigingen zijn aangebracht in de omgeving.

U kunt een ruimte ook handmatig laden of uw ruimten beheren door naar Instellingen  >  **Systeemruimten te**  >  **gaan.**

[Terug naar lijst](#list)

## <a name="how-do-i-delete-all-spaces"></a>Hoe kan ik alle spaties verwijderen?

*Binnenkort*

[Terug naar lijst](#list)

## <a name="holograms-dont-look-right-or-are-moving-around"></a>Hologrammen niet goed uitzien of zich verplaatsen

Als uw hologrammen er niet goed uitzien (ze zijn bijvoorbeeld jittery of shaky, of als er zwarte patches op staan), probeert u een van deze oplossingen:

- [Schoon uw apparaat-visor op](hololens1-hardware.md#care-and-cleaning) en zorg ervoor dat de sensoren niet worden geblokkeerd.
- Zorg ervoor dat u zich in een goed belichte ruimte hebt die niet veel directe steno heeft.
- Probeer rond te lopen en naar uw omgeving te kijken, zodat HoloLens vollediger kunt scannen.
- Als u veel hologrammen hebt geplaatst, kunt u proberen een aantal te verwijderen.

Als u nog steeds problemen hebt, probeert u de app Kalibratie uit te proberen. Deze app kalibreert uw HoloLens om ervoor te zorgen dat uw hologrammen er op hun best uitzien. Ga hiervoor naar Instellingen  >  **System**  >  **Utilities**. Selecteer **onder Kalibratie** de **optie Kalibratie openen.**

[Terug naar lijst](#list)

## <a name="finding-your-space-message"></a>Bericht 'Uw ruimte zoeken'

Wanneer HoloLens een ruimte leert of laadt, ziet u mogelijk een kort bericht met de tekst 'Uw ruimte zoeken'. Als dit bericht langer dan een paar seconden wordt weergegeven, ziet u een ander bericht onder de Startmenu met de tekst 'Nog steeds op zoek naar uw ruimte'.

Deze berichten betekenen dat HoloLens problemen heeft met het toewijzen van uw ruimte. Als dit gebeurt, kunt u apps openen, maar u kunt geen hologrammen in uw omgeving plaatsen.

Als u deze berichten vaak ziet, probeert u een of meer van de volgende oplossingen:

- Zorg ervoor dat u zich in een goed belichte ruimte hebt die niet veel directe steno heeft.
- Zorg ervoor dat uw apparaat visor schoon is. [Meer informatie over het ops schonen van uw visor](hololens1-hardware.md#care-and-cleaning).
- Zorg ervoor dat u een sterk Wi-Fi hebt. Als u een nieuwe omgeving met geen Wi-Fi of een zwak Wi-Fi signaal, HoloLens u uw ruimte niet vinden. Controleer uw Wi-Fi verbinding door naar Instellingen  >  **&amp; Wi-Fi-netwerkinternet**  >  **te gaan.**
- Probeer langzamer te bewegen.

[Terug naar lijst](#list)

## <a name="expected-holograms-arent-showing-in-my-space"></a>Verwachte hologrammen worden niet weergegeven in mijn ruimte

Als u de hologrammen die u hebt geplaatst niet ziet of als u een aantal ziet dat u niet verwacht, probeer dan een of meer van de volgende oplossingen:

- Schakel enkele lampen in. HoloLens werkt het beste in een goed belichte ruimte.
- Verwijder hologrammen die u niet nodig hebt door naar Instellingen  >  **System**  >  **Hologrammen**  >  **Remove nearby holograms te gaan.** U kunt indien nodig ook **Alle hologrammen verwijderen selecteren.**

  > [!NOTE]
  > Als de indeling of belichting in uw ruimte aanzienlijk verandert, kan het zijn dat uw apparaat problemen heeft bij het identificeren van uw ruimte en het weergeven van uw hologrammen.

[Terug naar lijst](#list)

## <a name="cant-place-holograms-or-see-previously-placed-holograms"></a>Kan geen hologrammen plaatsen of eerder geplaatste hologrammen zien

Als HoloLens ruimte niet kan in kaart brengen of laden, wordt de beperkte modus gebruikt en kunt u geen hologrammen plaatsen of hologrammen zien die u hebt geplaatst. U kunt het volgende proberen:

- Zorg ervoor dat uw omgeving voldoende licht heeft, zodat HoloLens ruimte kan zien en in kaart kan brengen.
- Sta tussen één en drie meter van waar u het hologram wilt plaatsen.
- Plaats geen hologrammen op zwarte of reflectieve oppervlakken.
- Zorg ervoor dat u bent verbonden met een Wi-Fi netwerk. Als u niet bent verbonden met Wi-Fi, HoloLens een bekende ruimte niet identificeren en laden.
- Rond de ruimten zodat HoloLens omgeving opnieuw kunt scannen. Als u wilt zien wat er al is gescand, tikt u in de lucht om de mesh-afbeelding van de toewijzing weer te brengen.
- Als u een nieuwe ruimte wilt maken, maakt u verbinding met Wi-Fi en start u de HoloLens.
- Als u wilt zien of de juiste ruimte actief is of als u handmatig een spatie wilt laden, gaat u **naar Instellingen**  >  **Systeemruimten.**  >  
- Als de juiste ruimte is geladen en u nog steeds problemen hebt, is de ruimte mogelijk beschadigd. U kunt dit probleem oplossen door de spatie te selecteren en vervolgens **Verwijderen te selecteren.** Nadat u de ruimte hebt verwijderd, HoloLens u uw omgeving toewijsen en een nieuwe ruimte maken.

[Terug naar lijst](#list)

## <a name="holograms-disappear-or-are-encased-in-other-holograms-or-objects"></a>Hologrammen verdwijnen of zijn ingepakt in andere hologrammen of objecten

Als u te dicht bij een hologram komt, verdwijnt het tijdelijk om het hologram te herstellen. U gaat &mdash; er gewoon vandoor. Als u meerdere hologrammen dicht bij elkaar hebt geplaatst, kunnen sommige ook verdwijnen. Probeer er een paar te verwijderen.

Hologrammen kunnen ook worden geblokkeerd of ingepakt door andere hologrammen of door objecten zoals muren. Als dit het geval is, probeert u een van de volgende oplossingen:

- Als het hologram is ingepakt in een ander hologram, verplaatst u het ingepakte hologram naar een andere locatie. Als u dit wilt doen, **selecteert u Aanpassen,** tikt u op en houdt u deze vast om deze te positionen.
- Als het hologram is ingekapseld op een wand, selecteert u Aanpassen **en** loopt u naar het wand totdat het hologram wordt weergegeven. Tik en houd het hologram naar voren en uit de wand.
- Als u het hologram niet kunt verplaatsen met behulp van gebaren, gebruikt u uw stem om het te verwijderen. Staren naar het hologram en vervolgens 'Verwijderen' zeggen. Open vervolgens het hologram opnieuw en plaats het op een nieuwe locatie.

[Terug naar lijst](#list)

## <a name="holograms-are-appearing-on-the-other-side-of-a-wall"></a>Hologrammen worden weergegeven aan de andere kant van een wand

Als u zich heel dicht bij een wand of als HoloLens het wand nog niet heeft gescand, ziet u hologrammen in de volgende ruimte. Als u de wand wilt scannen, staat u tussen een en drie meter van het prikgetal en kijkt u er naar.

Een zwart of reflectief object (bijvoorbeeld een zwarte bank of een koelkast) in de buurt van de wand kan problemen veroorzaken wanneer HoloLens de wand scant. Als er een dergelijk object is, scant u de andere kant van het wand.

[Terug naar lijst](#list)

## <a name="after-placing-a-hologram-on-a-wall-it-seems-to-float"></a>Nadat een hologram op een wand is geplaatst, lijkt het te zweven

Een hologram dat u op een wand zet, lijkt meestal een inch of zo verwijderd van de wand. Probeer een of meer van de volgende oplossingen als deze verder weg lijkt te zijn:

- Wanneer u een hologram op een wand zet, moet u tussen één en drie meter van de wand staan en recht op de wand staan.
- Tik in de lucht op het wand om de mesh-afbeelding van de toewijzing weer te laten zien. Zorg ervoor dat de mesh is uitgelijnd met het wand. Als dat niet het beste is, verwijdert u het hologram, scant u de wand opnieuw en probeert u het opnieuw.
- Als het probleem zich blijft voordoen, voer dan de App Kalibratie uit. U vindt deze in **Instellingen**  >  **System**  >  **Utilities**.

[Terug naar lijst](#list)

## <a name="apps-appear-too-close-after-moving-them"></a>Apps worden te dicht bij elkaar weergegeven nadat ze zijn verplaatst

Probeer rond te lopen en te kijken naar het gebied waar u de app plaatst, zodat HoloLens het gebied vanuit verschillende hoeken scant. [Het opsporen van uw apparaat-visor](hololens1-hardware.md#care-and-cleaning) kan ook helpen.

[Terug naar lijst](#list)

## <a name="reporting-issues-with-unstable-or-inexact-holograms"></a>Problemen melden met instabiele of inexacte hologrammen
 
1. Neem een video en [een Vastleggen in mixed reality van](holographic-photos-and-videos.md#capture-a-mixed-reality-video) het probleem op. Deze video kan later worden geüpload via Feedback-hub als een bijgevoegd bestand.  
1. Schakel volledige telemetrie in via de **Instellingen-app** -> **Privacy**  ->  **Diagnostics**  & feedback en controleer onder Optionele diagnostische gegevens of de schakelknop is ingesteld op **Aan**
1. Haal de nieuwste hologramschaal- en stabiliteitsfixes op door bij te werken naar de nieuwste [Windows Holographic OS, (20H2 of hoger).](hololens-release-notes.md#windows-holographic-version-20h2) Voer na het bijwerken het volgende uit:
    1. Verwijder alle Hologrammen via **Instellingen** app -> **System** Hologrammen -> en selecteer  ->   vervolgens **Alle hologrammen** verwijderen en begin met een nieuwe kaart.
    1. Maak een nieuwe kaart van uw ruimte door de ruimte HoloLens en rond uw kamer te lopen en alle gebieden en oppervlak in de ruimte te bekijken. Doe dit 2-3 minuten.
    1. Voer IPD-kalibratie uit. Ga naar **Instellingen**  >  **System**  >  **Utilities**. Selecteer **onder Kalibratie** de **optie Kalibratie openen.**
    1. Test het scenario opnieuw en kijk of het scenario nog steeds wordt uitgevoerd.
1. Als het probleem niet wordt opgelost door bij te werken, kunt u een [Feedback-hub indienen.](hololens-feedback.md) Nadat u feedback hebt ingevuld, kunt u de knop **Delen** gebruiken om een eenvoudig te delen koppeling te maken die kan worden verzonden wanneer u contact op met de ondersteuning op te nemen.

[Terug naar lijst](#list)