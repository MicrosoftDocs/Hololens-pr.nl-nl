---
title: De HoloLens 2
description: Meer informatie over het controleren van HoloLens buildnummer, het up-to-date houden van apparaatupdates, het deelnemen aan het Insiders-programma en het terugdraaien van updates.
keywords: how-to, update, roll back, HoloLens, check build, build number
ms.prod: hololens
ms.sitesec: library
author: qianw211
ms.author: v-beehanson
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/11/2021
audience: ITPro
ms.reviewer: ''
manager: sekerawa
appliesto:
- HoloLens 2
ms.openlocfilehash: 49036135ba13a93d2e8be97a7f3a95d50785c5c5
ms.sourcegitcommit: 19d1abb7589cebf14ba45e830f49224f7b4fcfe9
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/15/2021
ms.locfileid: "130034260"
---
# <a name="update-hololens-2"></a>De HoloLens 2

## <a name="overview"></a>Overzicht

We werken altijd aan nieuwe functies, foutfixes en beveiligingsupdates. U ontvangt een melding wanneer deze updates gereed zijn.

Op basis van uw voorkeur worden HoloLens systeemupdates automatisch gedownload en geïnstalleerd wanneer deze zijn aangesloten op stroom, zijn verbonden met internet en zelfs stand-by.

Om ervoor te HoloLens dat uw apparaat altijd wordt bijgewerkt, laat u het aangesloten op het bijgeleverde apparaat. U wilt ook dat uw HoloLens zijn verbonden met internet. Op deze manier worden systeemupdates automatisch gedownload en geïnstalleerd. 

Met Windows Update-service kunt u meerdere aspecten van het updateproces beheren, zoals welke apparaten op welk moment updates ontvangen. Dit besturingselement is handig omdat u updates kunt uitrollen naar een subset van HoloLens voor testen. Vervolgens kunt u updates voor de resterende updates uitrollen. U kunt ook verschillende updateschema's voor verschillende typen updates definiëren.

## <a name="types-of-updates"></a>Typen updates

Voor HoloLens kunt u automatisch twee typen updates beheren.

- Functie-updates: twee keer per jaar uitgebracht.
- Kwaliteitsupdates: inclusief essentiële beveiligingsupdates. Ze worden maandelijks vrijgegeven of indien nodig.

Gebruik  / **AllowAutoUpdate bijwerken om** het scannen, downloaden en installeren van updates te beheren. 

## <a name="scheduling-updates"></a>Updates plannen

U kunt ook een updateschema instellen. Dit kan op een bepaalde dag of elke dag op een bepaald tijdstip zijn. Bijvoorbeeld om 17:00 uur of buiten de werkuren.

Ten slotte nog enkele woorden over het plannen van uw updatestrategie. We ondersteunen uitstel van updates, zodat u kunt bepalen hoe lang u moet wachten nadat Microsoft een update heeft uitgebracht om die update op apparaten te installeren.

Soms probeert een bedrijf eerst alle nieuwe functies om er zeker van te zijn dat alles werkt en is het bedrijf bekend met de nieuwe updates, zodat het ondersteuningsteam wordt voorbereid. Zodra ze hebben bevestigd dat alles goed is, worden de updates voor het hele bedrijf uitrollen. Door subsets van uw apparaten te koppelen aan verschillende beleidsregels voor uitstel, ook wel updateringen genoemd, kunt u een strategie voor update-implementatie voor uw organisatie coördineren.

## <a name="hololens-update-tools"></a>HoloLens hulpprogramma's voor bijwerken

In deze sectie wordt u door de HoloLens voor:

- controleren op updates
- handmatig bijwerken HoloLens
- uw huidige besturingssysteemversie weergeven (buildnummer)
- terugrollen naar een oudere update

### <a name="check-for-updates-and-manually-update"></a>Controleren op updates en handmatig bijwerken

U kunt op elk gewenst moment controleren op updates in de instellingen.  Beschikbare updates bekijken en controleren op nieuwe updates:

1. Open de app **Instellingen**.
1. Navigeer **naar Update & Security** Windows  >  **Update**.
1. Selecteer **Controleren op updates**.

Als er een update beschikbaar is, wordt de nieuwe versie gedownload. Nadat het downloaden is voltooid, selecteert u de knop **Nu** opnieuw opstarten om de installatie te activeren. Als uw apparaat minder dan 40% is en niet is aangesloten, wordt de update niet opnieuw opgestart.

Terwijl uw HoloLens update installeert, worden er draaiende tandwielen en een voortgangsindicator weergegeven. Schakel uw HoloLens gedurende deze tijd niet uit. Deze wordt automatisch opnieuw opgestart zodra de installatie is voltooid.

HoloLens wordt één update tegelijk toegepast.  Als uw HoloLens meer dan één versie achter de meest recente versie ligt, moet u het updateproces mogelijk meerdere keren uitvoeren om deze volledig up-to-date te krijgen.

### <a name="check-your-operating-system-version-build-number"></a>Controleer de versie van uw besturingssysteem (buildnummer)

U kunt het systeemversienummer (buildnummer) controleren door Instellingen **en** **Systeem over te**  >  **selecteren.**

### <a name="go-back-to-a-previous-version"></a>Terug naar een eerdere versie

In sommige gevallen wilt u mogelijk teruggaan naar een eerdere versie van de HoloLens software. De aanbevolen stappen zijn:

1. Neem contact op met de ondersteuning om te zien of ze uw probleem kunnen oplossen.
    1. Zorg ervoor **dat Optionele** of **Volledige** telemetrie is ingeschakeld. Hierdoor kan uw fout beter worden ondernomen en kunnen technici gemakkelijker een diagnose stellen.
    1. In [Bestandsfeedback](hololens-feedback.md) moet u zo beschrijvend mogelijk zijn. Noteer de titel of gebruik de functie voor delen, zodat u uw fout kunt delen met ondersteuning.
    1. Neem contact [op met ondersteuning](https://aka.ms/hlsupport). Als uw probleem een probleem is dat moet worden opgelost door terug te keren naar een eerdere versie, kunnen ze u de FFU leveren om uw apparaat te laten knipperen.

1. Als dat niet werkt, kunt u uw [HoloLens 2 met de Advanced Recovery Companion](hololens-recovery.md#clean-reflash-the-device).

> [!NOTE]
> Als u terug gaat naar een eerdere versie, worden uw persoonlijke bestanden en instellingen verwijderd.

Als u de momenteel geïnstalleerde versie wilt blijven, kunt u updates ook [handmatig onderbreken.](hololens-updates.md#pause-updates-via-device) Dit geeft het technische team tijd om het probleem op te lossen.

## <a name="windows-insider-program-on-hololens"></a>Windows Insider-programma op HoloLens

Wilt u de nieuwste functies in HoloLens?  Als dat het zo is, voegt u de Windows Insider-programma; U krijgt toegang tot preview-builds van HoloLens software-updates voordat deze beschikbaar zijn voor het algemene publiek.

[Bekijk Windows Insider-preview voor Microsoft HoloLens.](hololens-insider.md)