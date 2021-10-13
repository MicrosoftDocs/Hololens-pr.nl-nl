---
title: HoloLens 2 Platformmodus verplaatsen
description: Gebruik van HoloLens op bewegende platforms
keywords: platformen verplaatsen, dynamische beweging, hololens, platformmodus voor verplaatsen
author: evmill
ms.author: v-evmill
ms.reviewer: yabahman
ms.date: 10/12/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: high
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 7c636cd97e31c74d4976e71ec3f41ac5afe5bdcc
ms.sourcegitcommit: 9574db58592b7302bd2386bdf7fda3f6721de818
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/13/2021
ms.locfileid: "129924424"
---
# <a name="moving-platform-mode-on-low-dynamic-motion-moving-platforms"></a>Platformmodus verplaatsen op platformen met weinig dynamische beweging

In [Windows Holographic, versie 21H2,](hololens-release-notes.md#windows-holographic-version-21h2) is bètaondersteuning toegevoegd voor het bijhouden van laag dynamische bewegingsplatforms op HoloLens 2. Nadat u de build hebt geïnstalleerd en de Moving Platform-modus hebt inschakelen, kunt u uw HoloLens 2 gebruiken in eerder ontoegankelijke omgevingen, zoals grote zee- en grote zeeplatforms. Op dit moment is de functie gericht op het inschakelen van deze specifieke platformen voor verplaatsen. Hoewel niets u verhindert om de functie in andere omgevingen te gebruiken, is de functie gericht op het toevoegen van ondersteuning voor deze omgevingen.

![Voorbeeld van een verplaatst platform.](./images/mpm-compare.gif)

In dit artikel wordt het volgende beschreven:

1. [Waarom een platform verplaatsen nodig is](#why-moving-platform-mode-is-necessary)
1. [Platformmodus verplaatsen inschakelen](#enabling-moving-platform-mode)

## <a name="why-moving-platform-mode-is-necessary"></a>Waarom de platformmodus moet worden verplaatst

HoloLens moet uw hoofdpositie kunnen volgen met [6](https://en.wikipedia.org/wiki/Six_degrees_of_freedom) vrijheidsgraden (X, Y, Z, translation and roll, pitch, yaw rotation) om stabiele hologrammen weer te geven. Om dit te doen, HoloLens twee vergelijkbare gegevens uit twee afzonderlijke bronnen bij:

1. **Zichtbare lichte camera's.** Deze camera's volgen de omgeving, bijvoorbeeld de fysieke ruimte waarin u de HoloLens
1. **Inertial Measurement Unit (IMU).** De IMU bestaat uit een versnellingsmeter, eenscope en een teller die uw hoofd beweging en richting ten opzichte van de aarde bij houdt

Informatie uit deze twee bronnen wordt samengesteld om uw hoofdpositie bij te houden met een lage latentie en hoog genoeg frequentie om vloeiende hologrammen weer te geven.

Deze benadering is echter afhankelijk van een kritieke veronderstelling; de omgeving (bij te houden door de camera's) blijft stationair ten opzichte van de aarde (waarop de IMU metingen kan doen). Als dat niet het geval is, zoals op een boot in het water, kunnen de gegevens van beide bronnen met elkaar conflicteren en ervoor zorgen dat de tracker verloren gaat. Dit conflict produceert onjuiste positiegegevens en resulteert in my hologrammen of zelfs traceringsverlies.

Dit probleem wordt opgelost door de platformmodus te verplaatsen. Wanneer u De platformmodus verplaatsen inschakelen, is dat een hint voor onze tracker dat we niet altijd op onze sensorinvoer kunnen vertrouwen om volledig met elkaar in overeenstemming te zijn. In plaats daarvan moeten we meer vertrouwen op het bijhouden van visuele elementen en snel onlogische inertiële bewegingsgegevens identificeren en deze overeenkomstig filteren voordat we de IMU-invoer kunnen gebruiken.

## <a name="supported-environments-and-known-limitations"></a>Ondersteunde omgevingen en bekende beperkingen

Hoewel de moving platformmodus is ontwikkeld om op intelligente wijze gevallen van inertiale en visuele gegevensconflicten af te handelen, is het momenteel beperkt tot grote, dynamische bewegingssituaties. Dit betekent dat er zeker beperkingen en niet-ondersteunde scenario's zijn.

### <a name="known-limitations"></a>Bekende beperkingen

- De enige ondersteunde omgevingen voor MPM (Moving Platform Mode) zijn grote, dynamische beweging. Met andere woorden, veel veelvoorkomende omgevingen/situaties worden nog niet ondersteund vanwege de hoge frequentie van de beweging en hoge versnellingsniveaus en [de .](https://en.wikipedia.org/wiki/Jerk_(physics))  Bijvoorbeeld: vlakken, traint, auto's, fietsen, fietsen, kleine bootjes, lifts, enzovoort.
- Hologrammen kan een beetje snipperen wanneer MPM is ingeschakeld, met name wanneer er te veel water is.
- Niets voorkomt dat gebruikers MPM proberen te gebruiken in niet-ondersteunde omgevingen, maar gebruikers kunnen ongewenste neveneffecten ervaren als het apparaat het bijhouden in de niet-ondersteunde ruimte kan behouden. Met MPM kunnen gebruikers bijvoorbeeld vinden dat het mogelijk is om in een lift te gebruiken terwijl ze van verdieping wisselen, terwijl dat voorheen onmogelijk was. Hoewel MPM het bijhouden van het apparaat toestaat, wordt het kaartbeheer momenteel niet verwerkt. Gebruikers zullen merken dat het wijzigen van de verdiepingen in een lift ertoe zal leiden dat het apparaat de bovenste en onderste verdiepingen in de war brengt en de kwaliteit van de kaart negatief beïnvloedt.

## <a name="prerequisites"></a>Vereisten

Voor bèta-ondersteuning voor de platformmodus zijn slechts enkele vereisten vereist:

1. Installeer [Windows Holographic, versie 21H2](hololens-release-notes.md#windows-holographic-version-21h2) of nieuwer door de nieuwste build bij te werken of te [flashen](https://aka.ms/hololens2download) [via ARC](hololens-recovery.md#clean-reflash-the-device).

2. Ontwikkelmodus [en -Apparaatportal](/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)

## <a name="enabling-moving-platform-mode"></a>Platformmodus verplaatsen inschakelen

Als u de modus Platform verplaatsen wilt inschakelen, [moet u eerst Apparaatportal.](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)

1. Selecteer de **systeem-overeenkomst** in het menu aan de linkerkant

   ![Eerste afbeelding.](.\images\mpm-01.png)

2. Selecteer de **pagina Platform verplaatsen en** schakel het selectievakje Platform **verplaatsen** in

    ![Tweede afbeelding.](.\images\mpm-02.png)

3. Wanneer u wordt gevraagd om een waarschuwing, selecteert u **OK**

   ![Derde afbeelding.](.\images\mpm-03.png)

4. Start uw apparaat opnieuw op. U kunt dit doen via het menu Apparaatportal **Power** in de rechterbovenboven of door de volgende spraakopdracht uit te voeren Het apparaat opnieuw opstarten en Ja &quot; &quot; &quot; &quot; selecteren.

   ![Vierde afbeelding.](.\images\mpm-04.png)

Als u de optie Platform verplaatsen niet ziet in Apparaatportal, betekent dit waarschijnlijk dat u nog niet de juiste build hebt. Zie de [sectie Vereisten.](#prerequisites)

## <a name="reporting-issues"></a>Problemen met rapportage

Zoals eerder vermeld, is deze functie een bètafunctie die alleen beschikbaar is in de ontwikkelaarsmodus, wat betekent dat u mogelijk problemen krijgt. Als dat gebeurt, kunnen we het product onderzoeken en verbeteren:

1. Meld het probleem via [Feedback-hub](hololens-feedback.md) onder de **categorie Hologramn nauwkeurigheid, stabiliteit en** betrouwbaarheid en neem het volgende op:
    1. Een beschrijving van het probleem, inclusief het verwachte gedrag en ervaren gedrag
    1. Een Mixed Reality [video-opname](holographic-photos-and-videos.md#capture-a-mixed-reality-video) van het probleem
2.  Open een ondersteuningscase op en deel de Feedback-hub-URL, zodat we contact kunnen opvragen voor het geval [https://aka.ms/hlsupport](https://aka.ms/hlsupport) we vervolgvragen hebben