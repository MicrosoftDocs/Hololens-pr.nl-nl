---
title: HoloLens 2 Platformmodus verplaatsen
description: Gebruik van HoloLens op bewegende platforms
keywords: platformen verplaatsen, dynamische beweging, hololens, platformmodus voor verplaatsen
author: evmill
ms.author: v-evmill
ms.reviewer: yabahman
ms.date: 8/10/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: high
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 9c37baa6fb63e9b049378799515ef107ed0ea7a8
ms.sourcegitcommit: 7b666c63a0367032a4a3f366b7f9029b2613e345
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/18/2021
ms.locfileid: "122401163"
---
# <a name="moving-platform-mode-on-low-dynamic-motion-moving-platforms"></a>Platformmodus verplaatsen op platformen met weinig dynamische beweging

In **Insider-build 20348.1411** is bètaondersteuning toegevoegd voor het bijhouden van laag dynamische bewegingsplatforms op HoloLens 2. Nadat u de build hebt geïnstalleerd en de Moving Platform-modus hebt inschakelen, kunt u uw HoloLens 2 gebruiken in eerder ontoegankelijke omgevingen, zoals grote schip en grote 12-30-2018. Op dit moment is de functie gericht op het inschakelen van deze specifieke platformen voor verplaatsen. Hoewel niets u verhindert om de functie in andere omgevingen te gebruiken, is de functie gericht op het toevoegen van ondersteuning voor deze omgevingen.

> [!NOTE]
> Deze functie is momenteel alleen beschikbaar [via Windows Insiders](hololens-insider.md).

In dit artikel wordt het volgende beschreven:

1. [Waarom een platform verplaatsen nodig is](#why-moving-platform-mode-is-necessary)
1. [Platformmodus verplaatsen inschakelen](#enabling-moving-platform-mode)

## <a name="why-moving-platform-mode-is-necessary"></a>Waarom de platformmodus moet worden verplaatst

HoloLens moet uw hoofdpositie kunnen volgen met [6](https://en.wikipedia.org/wiki/Six_degrees_of_freedom) vrijheidsgraden (X, Y, Z translation and roll, pitch, yaw rotation) om stabiele hologrammen weer te geven. Om dit te doen, HoloLens twee vergelijkbare gegevens uit twee afzonderlijke bronnen bij:

1. Zichtbare lichte camera's: deze houden de omgeving bij, bijvoorbeeld de fysieke ruimte waarin u de HoloLens
1. Inertial Measurement Unit (IMU), die bestaat uit een versnellingsmeter, eenscope en een snelheidsmeter die uw hoofd beweging en richting ten opzichte van de aarde bij houdt

Informatie uit deze twee bronnen wordt samengesteld om uw hoofdpositie bij te houden met een lage latentie en hoog genoeg frequentie om vloeiende hologrammen weer te geven.

Deze benadering is echter afhankelijk van een kritieke veronderstelling; de omgeving (bij te houden door de camera's) blijft stationair ten opzichte van de aarde (waarop de IMU metingen kan doen). Als dat niet het geval is, zoals op een boot in het water, kunnen de gegevens van beide bronnen met elkaar conflicteren en ervoor zorgen dat de tracker verloren gaat. Dit conflict produceert onjuiste positiegegevens en resulteert in my hologrammen of zelfs traceringsverlies.

Dit probleem wordt opgelost door de platformmodus te verplaatsen. Wanneer u De platformmodus verplaatsen inschakelen, is dat een hint voor onze tracker dat we niet altijd op onze sensorinvoer kunnen vertrouwen om volledig met elkaar in overeenstemming te zijn. In plaats daarvan moeten we meer vertrouwen op het bijhouden van visuele elementen en het snel identificeren van onlogische inertiële bewegingsgegevens en deze overeenkomstig filteren voordat we&#39;IMU-invoer kunnen gebruiken.

## <a name="supported-environments-and-known-limitations"></a>Ondersteunde omgevingen en bekende beperkingen

Hoewel de moving platformmodus is ontwikkeld om op intelligente wijze gevallen van inertiale en visuele gegevensconflicten af te handelen, is het momenteel beperkt tot grote, dynamische bewegingssituaties. Dit betekent dat er zeker beperkingen en niet-ondersteunde scenario's zijn.

### <a name="known-limitations"></a>Bekende beperkingen

- De enige ondersteunde omgevingen voor de MPM (Moving Platform Mode) zijn grote, dynamische beweging. Met andere woorden, veel veelvoorkomende omgevingen/situaties worden nog niet ondersteund vanwege de hoge frequentie van de beweging en hoge versnellingsniveaus en [de snelheid.](https://en.wikipedia.org/wiki/Jerk_(physics))  Bijvoorbeeld: vlakken, traint, auto's, fietsen, fietsen, kleine bootjes, lifts, enzovoort.
- Hologrammen kan een beetje wiebelen wanneer MPM is ingeschakeld, met name wanneer er te veel water is.
- Niets voorkomt dat gebruikers MPM proberen te gebruiken in niet-ondersteunde omgevingen, maar gebruikers kunnen ongewenste neveneffecten ervaren als het apparaat het bijhouden in de niet-ondersteunde ruimte kan behouden. Met MPM kunnen gebruikers bijvoorbeeld vinden dat het&#39;mogelijk is om in een lift te gebruiken tijdens het wijzigen van verdiepingen, terwijl dat voorheen onmogelijk was. Hoewel MPM het bijhouden van het apparaat toestaat, wordt het kaartbeheer momenteel niet verwerkt. Gebruikers zullen dus merken dat veranderende verdiepingen in een lift ertoe leiden dat het apparaat de bovenste en onderste verdiepingen in de war brengt en de kwaliteit van de kaart negatief beïnvloedt.

## <a name="prerequisites"></a>Vereisten

Voor bèta-ondersteuning voor de platformmodus zijn slechts enkele vereisten vereist:

1. Installeer build 20348.1411 of nieuwer door de nieuwste [Insiders-build via ARC](hololens-insider.md#ffu-download-and-flash-directions) te flashen of door uw apparaat in te schrijven en bij [te werken.](hololens-insider.md#start-receiving-insider-builds)
   - Opmerking: deze build is momenteel alleen beschikbaar op [Insider Dev Channel.](hololens-insider.md#start-receiving-insider-builds)
2. Ontwikkelaarsmodus [en -Apparaatportal](/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)

## <a name="enabling-moving-platform-mode"></a>Platformmodus verplaatsen inschakelen

Als u de modus Platform verplaatsen wilt inschakelen, [moet u eerst Apparaatportal.](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)

1. Selecteer de **systeem-overeenkomst** in het menu aan de linkerkant
2. Selecteer de **pagina Platform verplaatsen en** schakel het selectievakje Platform **verplaatsen** in

   ![Eerste afbeelding](.\images\moving-platform-1x.png)
 
     ![Tweede afbeelding](.\images\moving-platform-2x.png)

3. Wanneer u wordt gevraagd om een waarschuwing, selecteert u **OK**

   ![Derde afbeelding](.\images\moving-platform-3x.png)

4. Start uw apparaat opnieuw op. U kunt dit doen via het menu Apparaatportal **Power** in de rechterbovenboven of door de volgende spraakopdracht uit te voeren Het apparaat opnieuw opstarten en Ja &quot; &quot; &quot; &quot; selecteren.

   ![Vierde afbeelding](.\images\moving-platform-4x.png)

Als u de optie Platform verplaatsen niet ziet in Apparaatportal, betekent dit waarschijnlijk dat u nog niet de juiste build hebt. Zie de [sectie Vereisten.](#prerequisites)
