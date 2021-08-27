---
title: HoloLens 2 Platformmodus verplaatsen
description: Informatie over het gebruik HoloLens op bewegende platforms
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
ms.openlocfilehash: cd46e162971ea709d865b2ac998cc7a517d231ec
ms.sourcegitcommit: 18f6c00a57a6b4608dadcec418d1970455d8ee3a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/26/2021
ms.locfileid: "122989194"
---
# <a name="moving-platform-mode-on-low-dynamic-motion-moving-platforms"></a>Platformmodus verplaatsen op bewegende platforms met weinig dynamische beweging

In **Insider-build 20348.1411** is bètaondersteuning toegevoegd voor het bijhouden van bewegingsplatformen met weinig dynamische beweging op HoloLens 2. Nadat u de build hebt geïnstalleerd en de moving platformmodus hebt inschakelen, kunt u uw HoloLens 2 gebruiken in eerder ontoegankelijke omgevingen, zoals grote verzend- en grote waterbouw. Op dit moment is de functie gericht op het inschakelen van deze specifieke platformen voor verplaatsen. Hoewel niets voorkomt dat u de functie in andere omgevingen probeert te gebruiken, is de functie gericht op het toevoegen van ondersteuning voor deze omgevingen.

> [!NOTE]
> Deze functie is momenteel alleen beschikbaar [via Windows Insiders](hololens-insider.md).

![Voorbeeld van een platform verplaatsen.](./images/mpm-compare.gif)

In dit artikel wordt het volgende beschreven:

1. [Waarom Een platform verplaatsen nodig is](#why-moving-platform-mode-is-necessary)
1. [Platformmodus verplaatsen inschakelen](#enabling-moving-platform-mode)

## <a name="why-moving-platform-mode-is-necessary"></a>Waarom de platformmodus moet worden verplaatst

HoloLens moet uw hoofdpositie kunnen volgen met [6](https://en.wikipedia.org/wiki/Six_degrees_of_freedom) vrijheidsgraden (X, Y, Z, translation and roll, pitch, yaw rotation) om stabiele hologrammen weer te geven. Om dit te doen, HoloLens twee vergelijkbare gegevens uit twee afzonderlijke bronnen bij:

1. Zichtbare lichte camera's: deze houden de omgeving bij, bijvoorbeeld de fysieke ruimte waarin u de HoloLens
1. Inertial Measurement Unit (IMU), die bestaat uit een versnellingsmeter, eenscope en een snelheidsmeter die uw hoofd beweging en oriëntatie ten opzichte van de aarde bij houdt

Informatie uit deze twee bronnen wordt samengesteld om uw hoofdpositie bij te houden met een lage latentie en hoog genoeg frequentie om vloeiende hologrammen weer te geven.

Deze benadering is echter afhankelijk van een kritieke veronderstelling; de omgeving (bij te houden door de camera's) blijft stationair ten opzichte van de aarde (waarop de IMU metingen kan doen). Wanneer dat niet het geval is, zoals op een boot in het water, kunnen de gegevens van beide bronnen met elkaar conflicteren en ervoor zorgen dat de tracker verloren gaat. Dit conflict produceert onjuiste positiegegevens en resulteert in my hologrammen of zelfs traceringsverlies.

Dit probleem wordt opgelost door de platformmodus te verplaatsen. Wanneer u De platformmodus verplaatsen inschakelen, is dat een hint voor onze tracker dat we niet altijd op onze sensorinvoer kunnen vertrouwen om volledig met elkaar in overeenstemming te zijn. In plaats daarvan moeten we meer vertrouwen op het bijhouden van visuele elementen en het snel identificeren van onlogische inertiële bewegingsgegevens en deze dienovereenkomstig filteren voordat we de IMU-invoer kunnen gebruiken.

## <a name="supported-environments-and-known-limitations"></a>Ondersteunde omgevingen en bekende beperkingen

Hoewel de moving platformmodus is ontwikkeld om op intelligente wijze gevallen van een conflict met inertiële en visuele gegevens af te handelen, is deze momenteel beperkt tot grote, dynamische beweging. Dit betekent dat er zeker beperkingen en niet-ondersteunde scenario's zijn.

### <a name="known-limitations"></a>Bekende beperkingen

- De enige ondersteunde omgevingen voor MPM (Moving Platform Mode) zijn grote, dynamische bewegingssensoren. Met andere woorden, veel veelvoorkomende omgevingen/situaties worden nog niet ondersteund vanwege de hoge frequentie en hoge versnellingsniveaus [en de hoge snelheid.](https://en.wikipedia.org/wiki/Jerk_(physics))  Bijvoorbeeld: vlakken, traint, auto's, fietsen, fietsen, kleine bootjes, lifts, enzovoort.
- Hologrammen kan iets gehaabeld zijn wanneer MPM is ingeschakeld, met name wanneer het op water is.
- Niets voorkomt dat gebruikers MPM proberen te gebruiken in niet-ondersteunde omgevingen, maar gebruikers kunnen ongewenste neveneffecten ervaren als het apparaat het bijhouden in de niet-ondersteunde ruimte kan bijhouden. Met MPM kunnen gebruikers bijvoorbeeld vinden dat het mogelijk is om in een lift te gebruiken tijdens het wijzigen van verdiepingen, terwijl dat voorheen onmogelijk was. Hoewel MPM het bijhouden van het apparaat toestaat, is het op dit moment niet mogelijk om kaartbeheer te beheren. Gebruikers zullen merken dat het wijzigen van de verdiepingen in een lift ertoe zal leiden dat het apparaat de bovenste en onderste verdiepingen in de war brengt en de kwaliteit van de kaart negatief beïnvloedt.

## <a name="prerequisites"></a>Vereisten

Voor bèta-ondersteuning voor de Platformmodus verplaatsen zijn slechts enkele vereisten vereist:

1. Installeer build 20348.1411 of nieuwer door de nieuwste [Insiders-build via ARC](hololens-insider.md#ffu-download-and-flash-directions) te flashen of door uw apparaat in te schrijven en bij [te werken.](hololens-insider.md#start-receiving-insider-builds)

   > [!NOTE]
   > Deze build is momenteel alleen beschikbaar op [het Insider Dev Channel](hololens-insider.md#start-receiving-insider-builds).

2. Ontwikkelaarsmodus [en -Apparaatportal](/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)

## <a name="enabling-moving-platform-mode"></a>Platformmodus verplaatsen inschakelen

Als u de modus Platform verplaatsen wilt inschakelen, [moet u eerst Apparaatportal.](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)

1. Selecteer  de systeem-accordion in het menu aan de linkerkant

   ![Eerste afbeelding](.\images\moving-platform-1w.png)

2. Selecteer de **pagina Platformmodus verplaatsen** en schakel het selectievakje **Platform verplaatsen** in

    ![Tweede afbeelding](.\images\moving-platform-2z.png)

3. Wanneer u wordt gevraagd om een waarschuwing, selecteert u **OK**

   ![Derde afbeelding](.\images\moving-platform-3w.png)

4. Start uw apparaat opnieuw op. Dit kan via het Apparaatportal **Power-menu** rechtsboven of door de volgende spraakopdracht Het apparaat opnieuw opstarten te geven en Ja te &quot; &quot; &quot; &quot; selecteren.

   ![Vierde afbeelding](.\images\moving-platform-4z.png)

Als u de optie Platform verplaatsen niet ziet in Apparaatportal, betekent dit waarschijnlijk dat u nog niet de juiste build hebt. Zie de [sectie Vereisten.](#prerequisites)

## <a name="reporting-issues"></a>Problemen met rapportage

Zoals hierboven vermeld, is deze functie een bètafunctie die alleen beschikbaar is in de ontwikkelaarsmodus, wat betekent dat u mogelijk problemen krijgt. Als dat gebeurt, zodat we het product kunnen onderzoeken en verbeteren, kunt u

1. Meld het probleem via [Feedback-hub](hololens-feedback.md) onder de **categorie Hologram nauwkeurigheid, stabiliteit en** betrouwbaarheid en neem het volgende op:
    1. Een beschrijving van het probleem, inclusief het verwachte gedrag en ervaren gedrag
    1. Een Mixed Reality [video van](holographic-photos-and-videos.md#capture-a-mixed-reality-video) het probleem
2.  Open een ondersteuningscase op en deel de Feedback-hub-URL, zodat we contact kunnen opvragen voor het geval [https://aka.ms/hlsupport](https://aka.ms/hlsupport) we vervolgvragen hebben