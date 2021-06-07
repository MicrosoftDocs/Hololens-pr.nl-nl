---
title: Insider-preview voor Microsoft HoloLens
description: Leer hoe u aan de slag kunt gaan met Insider-builds en waardevolle feedback kunt geven voor onze volgende belangrijke update van het besturingssysteem voor HoloLens.
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 04/01/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 8545b5f23dc81c194b68ea8b40feb83e525dfdf7
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/25/2021
ms.locfileid: "111377895"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Insider-preview voor Microsoft HoloLens

Welkom bij de nieuwste Insider Preview-builds voor HoloLens. Het is eenvoudig om aan de slag [te gaan](hololens-insider.md#start-receiving-insider-builds) en waardevolle feedback te geven voor onze volgende belangrijke update van het besturingssysteem voor HoloLens.

## <a name="windows-insider-release-notes"></a>Windows Insider opmerkingen bij de release

We zijn blij dat we weer nieuwe functies aan Windows Insiders kunnen toevoegen. Nieuwe builds worden naar de dev- en bètakanalen gerouteert voor de nieuwste updates. We blijven deze pagina bijwerken wanneer we meer functies en updates toevoegen aan onze Windows Insider builds. Word enthousiast en bereid u voor om deze updates in uw realiteit te combineren. 

### <a name="onedrive-for-work-or-school-camera-roll-upload"></a>OneDrive voor werk of school Camera Roll uploaden

*Geïntroduceerd in build 20346.1402*

We hebben een nieuwe functie toegevoegd aan de app HoloLens 2 Settings, waarmee klanten automatisch mixed reality foto's en video's van de map Afbeeldingen > Camera Roll kunnen uploaden naar de bijbehorende map OneDrive voor werk of school. Met deze functie wordt een functie-hiaat in de [OneDrive-app](holographic-photos-and-videos.md#share-your-mixed-reality-photos-and-videos) op HoloLens 2 vereend, die alleen ondersteuning biedt voor het automatisch uploaden van camera's naar de persoonlijke Microsoft-account van een klant (en niet naar het werk- of schoolaccount van de klant).

**Uitleg**

- Ga **naar Instellingen > Systeem > Mixed reality-camera** 'Camera uploaden' in teschakelen.
- Als u deze  functie instelt op De positie Aan, worden alle mixed reality foto's of video's die op uw apparaat zijn vastgelegd, automatisch in de wachtrij geplaatst om te worden geüpload naar de map Afbeeldingen > Camera Roll van uw OneDrive voor werk- of schoolaccount.
    >[!NOTE]
    >Foto's en video's  die zijn vastgelegd voordat u deze functie inschakelen, worden niet in de wachtrij geplaatst voor uploaden en moeten nog steeds handmatig worden geüpload.
- In een statusbericht op de pagina Instellingen wordt het aantal bestanden weergegeven dat in behandeling is voor uploaden (of 'OneDrive is up-to-date' wanneer alle bestanden in behandeling zijn geüpload).
- Als u zich zorgen maakt over bandbreedte of de upload om een of andere reden wilt 'onderbreken', kunt u de functie overschakelen naar **de positie Uit.** Het tijdelijk uitschakelen van de functie zorgt ervoor dat de uploadwachtrij blijft toenemen wanneer u nieuwe bestanden toevoegt aan de map Camera Roll, maar bestanden worden pas geüpload wanneer u de functie opnieuw inschakelen.
- Nieuwste bestanden worden eerst geüpload (laatste in, eerste uit).
- Als uw OneDrive-account problemen heeft (bijvoorbeeld nadat  uw wachtwoord is gewijzigd), wordt de knop Nu herstellen weergegeven op de pagina Instellingen.
- Er is geen maximale bestandsgrootte, maar houd er rekening mee dat het uploaden van grote bestanden langer duurt (met name als uw uploadbandbreedte beperkt is). Als u het uploaden 'pauzeert' of uit zet terwijl een groot bestand wordt geüpload, wordt het uploaden onmiddellijk geannuleerd. Het uploaden wordt opnieuw gestart wanneer u de functie opnieuw inschakelen. U verliest geen bestanden, maar de gedeeltelijke upload wordt verwijderd.

**Bekende problemen en waarschuwingen**

- Deze instelling heeft geen ingebouwde beperking op basis van het huidige bandbreedtegebruik. Als u de bandbreedte voor een ander scenario wilt maximaliseren, moet u de instelling handmatig uitschakelen. Het uploaden wordt onderbroken, maar de functie blijft nieuw toegevoegde bestanden controleren op Camera Roll. Schakel uploaden opnieuw in wanneer u klaar bent om door te gaan.
- Deze functie moet zijn ingeschakeld voor elk gebruikersaccount op het apparaat en kan alleen actief bestanden uploaden voor de gebruiker die momenteel is aangemeld bij het apparaat.
- Als u foto's of video's maakt tijdens het in realtime bekijken van het aantal uploads op de pagina Instellingen, moet u er rekening mee houden dat het aantal in behandeling zijnde bestanden mogelijk niet verandert totdat het uploaden van het huidige bestand is voltooid.
- Het uploaden wordt onderbroken als uw apparaat in de slaapstand valt of wordt uitgeschakeld. Om ervoor te zorgen dat de uploads in behandeling zijn voltooid, gebruikt u het apparaat actief totdat op de pagina Instellingen de tekst OneDrive is up-to-date staat of past u de slaapstandinstellingen van **uw Power & aan.**

## <a name="start-receiving-insider-builds"></a>Beginnen met het ontvangen van Insider-builds
> [!NOTE]
> Als u het apparaat niet recent hebt bijgewerkt, start u het apparaat opnieuw op om de status bij te werken en de nieuwste build op te halen.
> - De spraakopdracht 'Apparaat opnieuw opstarten' werkt goed. 
> - U kunt ook de knop Opnieuw opstarten kiezen in Instellingen/Windows Insider-programma.
>
> Er is een fout in de back-end die u mogelijk hebt aangetroffen, zodat u weer op schema komt.

Ga op HoloLens 2 apparaat **naar**  >  **InstellingenUpdate & beveiligingsbeleid**  >  **Windows Insider-programma** selecteer **Aan de slag.** Koppel het account dat u hebt gebruikt om u te registreren als Windows Insider.
Windows Insider wordt nu verplaatst naar Kanalen. De **Fast-ring** wordt het **Dev-kanaal,** de langzame **ring** wordt de **bèta-kanaal** en de **Release Preview-ring** wordt het **Release Preview-kanaal.** Hier ziet u hoe die toewijzing eruit ziet: Windows Insider Uitleg van kanalen Zie Introductie ![ ](images/WindowsInsiderChannels.png) Windows Insider [kanalen](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) in Windows-blogs voor meer informatie.
Selecteer vervolgens **Actieve ontwikkeling van Windows,** kies of u het **Dev-kanaal** wilt ontvangen of bèta-kanaal **builds** en bekijk de programmavoorwaarden.
Selecteer **Bevestigen > Nu opnieuw opstarten om** te voltooien. Nadat het apparaat opnieuw is opgestart, gaat u naar Instellingen **> Update & Security > Controleren** op updates om de meest recente build op te halen.
### <a name="update-error-0x80070490-work-around"></a>Updatefout 0x80070490 work-around
Als er een updatefout wordt 0x80070490 bij het bijwerken op het kanaal Dev of Beta, kunt u de volgende korte-termijnversie proberen. Dit omvat het verplaatsen van uw insider-kanaal, het ophalen van de update en vervolgens het terug verplaatsen van uw Insider-kanaal.
#### <a name="stage-one---release-preview"></a>Fase 1 - preview-versie
1.  Instellingen, Update & Beveiliging, Windows Insider-programma selecteer **Release Preview-kanaal.**
2.  Instellingen, & bijwerken, Windows Update, **Controleren op updates.** Na de update gaat u verder met Fase 2.
#### <a name="stage-two---dev-channel"></a>Fase 2 - Dev-kanaal
1. Instellingen, Update & Security en selecteer Windows Insider-programma **Dev Channel.**
2. Instellingen, & bijwerken, Windows Update, **Controleren op updates.**
## <a name="ffu-download-and-flash-directions"></a>FFU-download- en flashbeschrijvingen
Als u wilt testen met een met een vlucht ondertekende ffu, moet u eerst uw apparaat ontgrendelen voordat de met de vlucht ondertekende ffu wordt geflitst.
1. Op pc:
    1. Download ffu naar uw pc vanaf [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .
    
    1. Installeer ARC (Advanced Recovery Companion) vanuit de Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .
    
1. Op HoloLens - Ontgrendelen met vlucht: **Open** Instellingen  >  **Bijwerken & Beveiligingsbeleid**  >  **Windows Insider-programma** u zich vervolgens aan te melden en het apparaat opnieuw op te starten.
1. Flash-FFU: u kunt nu de met de vlucht ondertekende FFU flashen met behulp van ARC.
### <a name="provide-feedback-and-report-issues"></a>Feedback geven en problemen rapporteren
Gebruik de [app Feedback-hub uw](hololens-feedback.md) HoloLens om feedback te geven en problemen te melden. Het Feedback-hub zorgt ervoor dat alle benodigde diagnostische gegevens worden opgenomen om onze technici te helpen snel fouten op te sporen en het probleem op te lossen.  Problemen met de Chinese en Japanse versie van HoloLens moeten op dezelfde manier worden gerapporteerd.
> [!NOTE]
> Zorg ervoor dat u de prompt accepteert waarin wordt gevraagd of u Feedback-hub documenten wilt openen (selecteer **Ja** wanneer u hier om wordt gevraagd).
## <a name="note-for-developers"></a>Opmerking voor ontwikkelaars
U wordt aangeraden uw toepassingen te ontwikkelen met insider-builds van HoloLens.  Bekijk de [Documentatie voor HoloLens-ontwikkelaars om](https://developer.microsoft.com/windows/mixed-reality/development) aan de slag te gaan. Dezelfde instructies werken met Insider-builds van HoloLens.  U kunt dezelfde builds van Unity en Visual Studio die u al gebruikt voor HoloLens-ontwikkeling.
## <a name="stop-receiving-insider-builds"></a>Ontvangst van Insider-builds stoppen
Als u geen Insider-builds van Windows Holographic meer wilt ontvangen, kunt u zich uitloggen [](hololens-recovery.md) wanneer op uw HoloLens een productie-build wordt uitgevoerd, of u kunt uw apparaat herstellen met behulp van advanced recovery companion om uw apparaat te herstellen naar een niet-Insider-versie van Windows Holographic.
> [!CAUTION]
> Er is een bekend probleem waarbij gebruikers die de registratie van Insider Preview-builds ongedaan maken nadat ze handmatig een nieuwe preview-build hebben geïnstalleerd, een blauw scherm krijgen. Daarna moeten ze hun apparaat handmatig herstellen. Bekijk meer over dit bekende probleem voor meer informatie over of u hier al dan niet [mee te maken zou krijgen.](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build)
Controleren of op uw HoloLens een productie-build wordt uitgevoerd:
1. Ga naar **Instellingen > Systeem > Over** en zoek het buildnummer.
1. [Zie de releasenotities voor productie-buildnummers.](hololens-release-notes.md)
U kunt als volgende kiezen voor Insider-builds:
1. Ga op een HoloLens met een productie-build naar Instellingen **> Update & Security > Windows Insider-programma** en selecteer Stop Insider **builds.**
1. Volg de instructies om uw apparaat uit te kiezen.
