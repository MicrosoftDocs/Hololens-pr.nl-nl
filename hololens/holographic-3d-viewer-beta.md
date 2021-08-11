---
title: 3D-viewer Beta gebruiken op HoloLens (1e generatie)
description: Beschrijft de typen bestanden en functies die 3D-viewer Beta op HoloLens (1e generatie) ondersteunt, en hoe u de app kunt gebruiken en problemen met de app kunt oplossen.
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.localizationpriority: high
ms.date: 10/30/2019
ms.reviewer: scooley
audience: ITPro
manager: jarrettr
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: d25a87bd210535e36e18f165b5461141c40aa292a07c560018ba7c0cbf76f6ba
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/05/2021
ms.locfileid: "115664924"
---
# <a name="using-3d-viewer-beta-on-hololens-1st-gen"></a>3D-viewer Beta gebruiken op HoloLens (1e generatie)

3D-viewer Beta kunt u 3D-modellen weergeven op HoloLens (1e generatie). U kunt ondersteunde  FBX-bestanden openen en weergeven vanuit Microsoft Edge, OneDrive en andere apps.

>[!NOTE]
>Dit artikel is van toepassing op de in immersive Unity **3D-viewer Beta-app,** die .fbx-bestanden ondersteunt en alleen beschikbaar is op HoloLens (1e generatie). De vooraf geïnstalleerde **3D-viewer-app** op HoloLens 2 ondersteunt het openen van aangepaste .D-modellen in de Mixed Reality Startpagina (zie Overzicht assetvereisten [voor](/windows/mixed-reality/creating-3d-models-for-use-in-the-windows-mixed-reality-home#asset-requirements-overview) meer informatie.

>[!IMPORTANT]
>Hoewel 3D-viewer Beta beschikbaar kan blijven in de Microsoft Store voor HoloLens (eerste generatie), is deze niet langer in actieve ontwikkeling en wordt deze niet meer ondersteund.

Als u problemen hebt met het openen van een 3D-model in 3D-viewer Beta, of als bepaalde functies van uw 3D-model niet worden ondersteund, bekijkt u de [onderstaande ondersteunde](#supported-content-specifications) inhoudsspecificaties.

Zie [Optimizeing 3D models for 3D-viewer Beta (3D-modellen](#optimizing-3d-models-for-3d-viewer-beta) optimaliseren voor bètaversie) als u 3D-modellen wilt bouwen of optimaliseren voor gebruik met 3D-viewer Beta.

Er zijn twee manieren om een 3D-model te openen op HoloLens. Zie [FBX-bestanden weergeven op HoloLens](#viewing-fbx-files-on-hololens) voor meer informatie.

Zie Probleemoplossing hieronder als u problemen hebt nadat u deze onderwerpen [hebt](#troubleshooting) gelezen.

## <a name="supported-content-specifications"></a>Ondersteunde inhoudsspecificaties

### <a name="file-format"></a>Bestandsindeling

- FBX-indeling
- Maximale FBX-release 2015.1.0

### <a name="file-size"></a>Bestandsgrootte

- Minimaal 5 kB
- Maximaal 500 MB

### <a name="geometry"></a>Geometrie

- Alleen veelhoekige modellen. Geen onderverdelingsoppervlakken of NUBS
- Rechtshandig coördinaatsysteem
- Shear in transformatie matrices wordt niet ondersteund

### <a name="textures"></a>Patronen

- Patroonkaarten moeten worden ingesloten in het FBX-bestand
- Ondersteunde afbeeldingsindelingen
  - JPEG- en PNG-afbeeldingen
  - BMP-afbeeldingen (24-bits RGB true-color)
  - TGA-afbeeldingen (24-bits RGB en 32-bits RGBIR true-color)
- Maximale patroonresolutie van 2048x2048
- Maximaal één diffuuskaart, één normale kaart en één reflectiekubuskaart per mesh
- Alfakanaal in diffuus patroon zorgt ervoor dat pixels worden verwijderd als ze lager zijn dan 50%

### <a name="animation"></a>Animatie

- Animatie van schalen/draaien/vertalen van afzonderlijke objecten
- De animatie van Den Haagal (gesereerd) met skinning
  - Maximaal 4 invloeden per hoekpunt

### <a name="materials"></a>Materialen

- De materialen Voor en Phong worden ondersteund, met aanpasbare parameters
- Ondersteunde materiaaleigenschappen voor
  - Hoofdtextuur (RGB + Alpha-test)
  - Diffuuskleur (RGB)
  - Omgevingskleur (RGB)
- Ondersteunde materiaaleigenschappen voor Phong
  - Hoofdtextuur (RGB + Alpha-test)
  - Diffuuskleur (RGB)
  - Omgevingskleur (RGB)
  - Specificatiekleur (RGB)
  - Gereedheid
  - Reflectiviteit
- Aangepaste materialen worden niet ondersteund
- Maximaal één materiaal per mesh
- Maximaal één materiaallaag
- Maximaal 8 materialen per bestand

### <a name="file-and-model-limitations"></a>Beperkingen voor bestanden en modellen

Er zijn harde limieten voor de grootte van bestanden, evenals het aantal modellen, vertices en meshes dat tegelijkertijd kan worden geopend in 3D-viewer Beta:

- Maximale bestandsgrootte van 500 MB per model
- Vertices: 600.000 gecombineerd op alle open modellen
- Meshes: 1600 gecombineerd voor alle open modellen
- Maximaal 40 modellen tegelijk geopend

## <a name="optimizing-3d-models-for-3d-viewer-beta"></a>3D-modellen optimaliseren voor 3D-viewer Beta

### <a name="special-considerations"></a>Speciale overwegingen

- Vermijd zwarte materialen of zwarte gebieden in patroonkaarten. Hologrammen zijn gemaakt van licht, waardoor HoloLens zwart (de afwezigheid van licht) als transparant wordt weergegeven.
- Voordat u vanuit uw hulpprogramma voor het maken naar FBX exporteert, moet u ervoor zorgen dat alle geometrie zichtbaar en ontgrendeld is en dat er geen lagen met geometrie zijn uitgeschakeld of gesjabloond. Zichtbaarheid wordt niet in acht genomen.
- Vermijd zeer grote vertaal offsets tussen knooppunten (bijvoorbeeld 100.000 eenheden). Dit kan ertoe leiden dat het model jitter tijdens het verplaatst/geschaald/geruleerd wordt.

### <a name="performance-optimization"></a>Optimalisatie van prestaties

Houd rekening met de prestaties tijdens het maken van inhoud en valideer in de 3D-viewer Beta-app op HoloLens tijdens het ontwerpproces voor de beste resultaten. 3D-viewer Beta geeft inhoud in realtime weer en de prestaties zijn onderhevig aan HoloLens hardwaremogelijkheden.  

Er zijn veel variabelen in een 3D-model die van invloed kunnen zijn op de prestaties. 3D-viewer Beta geeft een waarschuwing over de belasting weer als er meer dan 150.000 vertices of meer dan 400 meshes zijn. Animaties kunnen invloed hebben op de prestaties van andere open modellen. Er zijn ook harde limieten voor het totale aantal modellen, vertices en meshes dat tegelijkertijd kan worden geopend in 3D-viewer Beta (zie Beperkingen voor bestanden en [modellen).](#file-and-model-limitations)  

Als het 3D-model niet goed wordt uitgevoerd vanwege de complexiteit van het model, kunt u het volgende overwegen:

- Het aantal veelhoeken verminderen
- Het aantal basisen in een animatie verminderen
- Zelf-occlusie voorkomen

Dubbelzijdige rendering wordt ondersteund in 3D-viewer Beta, hoewel deze standaard is uitgeschakeld om prestatieredenen. Dit kan worden ingeschakeld via de **knop Dubbelzijd** op de **pagina Details.** Voor de beste prestaties hoeft u geen dubbelzijdige rendering in uw inhoud te gebruiken.

### <a name="validating-your-3d-model"></a>Uw 3D-model valideren

Valideer uw model door het te openen in 3D-viewer Beta op HoloLens. Selecteer de **knop Details** om de kenmerken en waarschuwingen van niet-ondersteunde inhoud van uw model weer te geven (indien aanwezig).

### <a name="rendering-3d-models-with-true-to-life-dimensions"></a>3D-modellen weergeven met echte dimensies

Standaard geeft 3D-viewer Beta 3D-modellen weer met een goede grootte en positie ten opzichte van de gebruiker. Als het echter belangrijk is om een 3D-model met echte metingen weer te geven (bijvoorbeeld bij het evalueren van modellen in een ruimte), kan de maker van de inhoud een vlag instellen in de metagegevens van het bestand om te voorkomen dat de toepassing en de gebruiker het formaat van dat model kunnen veranderen.

Als u het schalen van het model wilt voorkomen, voegt u een aangepast Booleaanse kenmerk toe aan een object in de scène met de naam Microsoft_DisableScale stelt u dit in op true. 3D-viewer Beta respecteert vervolgens de FbxSystemUnit-informatie in het FBX-bestand. Schalen in 3D-viewer Beta is 1 meter per FBX-eenheid.

## <a name="viewing-fbx-files-on-hololens"></a>FBX-bestanden weergeven op HoloLens

### <a name="open-an-fbx-file-from-microsoft-edge"></a>Open een FBX-bestand vanuit Microsoft Edge

FBX-bestanden kunnen rechtstreeks vanaf een website worden geopend met behulp Microsoft Edge op HoloLens.

1. Navigeer Microsoft Edge naar de webpagina met het FBX-bestand dat u wilt weergeven.
1. Selecteer het bestand om het te downloaden.
1. Wanneer het downloaden is voltooid, selecteert u de knop **Openen** in Microsoft Edge om het bestand te openen in 3D-viewer Beta.

Het gedownloade bestand kan later worden geopend en opnieuw worden geopend met behulp van Downloads in Microsoft Edge. Als u een 3D-model wilt opslaan en de toegang wilt waarborgen, downloadt u het bestand op uw pc en sla u het op in uw OneDrive-account. Het bestand kan vervolgens worden geopend vanuit de OneDrive app op HoloLens.

> [!NOTE]
> Sommige websites met downloadbare FBX-modellen bieden deze in gecomprimeerde ZIP-indeling. 3D-viewer Beta kan geen ZIP-bestanden rechtstreeks openen. Gebruik in plaats daarvan uw pc om het FBX-bestand uit te extraheren en op te slaan in OneDrive account. Het bestand kan vervolgens worden geopend vanuit de OneDrive app op HoloLens.

### <a name="open-an-fbx-file-from-onedrive"></a>Open een FBX-bestand vanuit OneDrive

FBX-bestanden kunnen worden geopend vanuit OneDrive met behulp van de OneDrive-app op HoloLens. Zorg ervoor dat u een OneDrive hebt geïnstalleerd met behulp van Microsoft Store-app op HoloLens en dat u het FBX-bestand al hebt geüpload naar OneDrive op uw pc.

Eenmaal in OneDrive kunnen FBX-bestanden op twee manieren worden geopend op HoloLens met 3D-viewer Beta:

- Start OneDrive op HoloLens selecteer het FBX-bestand om het te openen in 3D-viewer Beta.
- Start 3D-viewer Beta, tik in de lucht om de werkbalk weer te geven en selecteer **Bestand openen.** OneDrive start, zodat u een FBX-bestand kunt selecteren.

## <a name="troubleshooting"></a>Problemen oplossen

### <a name="i-see-a-warning-when-i-open-a-3d-model"></a>Ik zie een waarschuwing wanneer ik een 3D-model open

U ziet een waarschuwing als u probeert een 3D-model te openen dat functies bevat die niet worden ondersteund door 3D-viewer Beta, of als het model te complex is en de prestaties mogelijk worden beïnvloed. 3D-viewer Beta wordt het 3D-model nog steeds geladen, maar de prestaties of visuele betrouwbaarheid kunnen worden aangetast.

Zie Supported [content specifications (Ondersteunde inhoudsspecificaties)](#supported-content-specifications) [en Optimizing 3D models for 3D-viewer Beta (3D-modellen](#optimizing-3d-models-for-3d-viewer-beta)optimaliseren voor 3D-viewer Beta).

### <a name="i-see-a-warning-and-the-3d-model-doesnt-load"></a>Ik zie een waarschuwing en het 3D-model wordt niet geladen

Er wordt een foutbericht weergegeven wanneer 3D-viewer Beta een 3D-model niet kan laden vanwege complexiteit of bestandsgrootte, of als het FBX-bestand beschadigd of ongeldig is. Er wordt ook een foutbericht weergegeven als u de limiet hebt bereikt voor het totale aantal modellen, vertices of meshes dat tegelijkertijd kan worden geopend.  

Zie Ondersteunde [inhoudsspecificaties en Bestands-](#supported-content-specifications) en [modelbeperkingen voor meer informatie.](#file-and-model-limitations)

### <a name="my-3d-model-loads-but-does-not-appear-as-expected"></a>Mijn 3D-model wordt geladen, maar wordt niet weergegeven zoals verwacht

Als uw 3D-model er niet uit ziet zoals verwacht in 3D-viewer Beta, tikt u in de lucht om de werkbalk weer te geven en selecteert u **details.** Aspecten van het bestand die niet worden ondersteund door 3D-viewer Beta worden gemarkeerd als waarschuwingen.

Het meest voorkomende probleem dat u mogelijk ziet, zijn ontbrekende texturen, waarschijnlijk omdat ze niet zijn ingesloten in het FBX-bestand. In dit geval wordt het model wit weergegeven. Dit probleem kan worden opgelost in het aanmaakproces door te exporteren van uw hulpprogramma voor het maken naar FBX met de optie voor insluittexturen geselecteerd.

Zie Supported [content specifications (Ondersteunde inhoudsspecificaties)](#supported-content-specifications) [en Optimizing 3D models for 3D-viewer Beta (3D-modellen](#optimizing-3d-models-for-3d-viewer-beta)optimaliseren voor 3D-viewer Beta).

### <a name="i-experience-performance-drops-while-viewing-my-3d-model"></a>Ik ervaart prestatiedalingen tijdens het weergeven van mijn 3D-model

De prestaties bij het laden en weergeven van een 3D-model kunnen worden beïnvloed door de complexiteit van het model, het aantal modellen dat gelijktijdig wordt geopend of het aantal modellen met actieve animaties.

Zie [Optimizing 3D models for 3D-viewer Beta](#optimizing-3d-models-for-3d-viewer-beta) and File and model limitations (3D-modellen optimaliseren voor bèta- en bestands- en [modelbeperkingen) voor meer informatie.](#file-and-model-limitations)

### <a name="when-i-open-an-fbx-file-on-hololens-it-doesnt-open-in-3d-viewer-beta"></a>Wanneer ik een FBX-bestand op HoloLens open, wordt het niet geopend in 3D-viewer bètaversie

3D-viewer Beta wordt automatisch gekoppeld aan de bestandsextensie .fbx wanneer deze wordt geïnstalleerd.

Als u probeert een FBX-bestand te openen en een dialoogvenster ziet waarin u naar Microsoft Store wordt doorverweken, hebt u momenteel geen app die is gekoppeld aan de bestandsextensie .fbx op HoloLens.

Controleer of 3D-viewer Beta is geïnstalleerd. Als deze niet is geïnstalleerd, downloadt u Microsoft Store op HoloLens.

Als 3D-viewer Beta al is geïnstalleerd, start u 3D-viewer Beta en probeert u het bestand opnieuw te openen. Als het probleem zich blijft voordoen, verwijdert en installeert u 3D-viewer Beta. Hiermee koppelt u de bestandsextensie .fbx opnieuw aan 3D-viewer Beta.

Als u probeert een FBX-bestand te openen, wordt er een andere app dan 3D-viewer Beta geopend. Deze app is waarschijnlijk geïnstalleerd na 3D-viewer Beta en heeft de associatie met de bestandsextensie .fbx overgenomen. Als u liever 3D-viewer Beta wilt gekoppeld aan de bestandsextensie .fbx, verwijdert en installeert u 3D-viewer Beta.

### <a name="the-open-file-button-in-3d-viewer-beta-doesnt-launch-an-app"></a>Met de knop Bestand openen in 3D-viewer Beta wordt geen app geopend

Met **de knop Bestand** openen wordt de app geopend die is gekoppeld aan de functie voor het kiezen van bestanden op HoloLens. Als OneDrive is geïnstalleerd, wordt de knop **Bestand** openen OneDrive. Als er momenteel echter geen app is gekoppeld aan de functie voor het kiezen van bestanden die is geïnstalleerd op HoloLens, wordt u omgeleid naar Microsoft Store.

Als met **de knop** Bestand openen een andere app dan OneDrive wordt geopend, is die app waarschijnlijk geïnstalleerd na OneDrive en heeft deze de associatie met de functie voor het kiezen van bestanden overgenomen. Als u liever OneDrive starten bij  het selecteren van de knop Bestand openen in 3D-viewer Beta, verwijdert en installeert u OneDrive.

Als de **knop** Bestand openen niet actief is, is het mogelijk dat u de limiet hebt bereikt voor het aantal modellen dat in één keer kan worden geopend in 3D-viewer Beta. Als er 40 modellen zijn geopend in 3D-viewer Beta, moet u er een aantal sluiten voordat u extra modellen kunt openen.

## <a name="additional-resources"></a>Aanvullende bronnen

- [Ondersteuningsforums:](http://forums.hololens.com/categories/3d-viewer-beta) alleen voor archiveringsdoeleinden. Dit forum is niet meer actief.
- [Mededelingen van derden](https://www.microsoft.com/{lang-locale}/legal/products)
