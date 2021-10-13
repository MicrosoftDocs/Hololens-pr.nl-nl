---
title: Insider-preview voor Microsoft HoloLens
description: Leer hoe u aan de slag gaat met Insider-builds en waardevolle feedback kunt geven voor onze volgende belangrijke update van het besturingssysteem voor HoloLens.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 10/12/2021
ms.reviewer: ''
manager: ranjibb
appliesto:
- HoloLens 2
ms.openlocfilehash: 080eb5949bc80d1ce922d57f099c375668f5633f
ms.sourcegitcommit: 9574db58592b7302bd2386bdf7fda3f6721de818
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/13/2021
ms.locfileid: "129924363"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Insider-preview voor Microsoft HoloLens

Welkom bij de nieuwste Insider Preview-builds voor HoloLens. Het is eenvoudig om aan [de slag te gaan](hololens-insider.md#start-receiving-insider-builds) en waardevolle feedback te geven voor onze volgende belangrijke update van het besturingssysteem voor HoloLens.

## <a name="windows-insider-release-notes"></a>Windows Opmerkingen bij de release van Insider

We zijn blij dat al onze recente Insider-functies openbaar zijn geworden. Als u hier meer over wilt lezen, raadpleegt u de pagina [met opmerkingen bij de release](hololens-release-notes.md)

## <a name="start-receiving-insider-builds"></a>Beginnen met het ontvangen van Insider-builds

> [!NOTE]
> Als u het apparaat niet recent hebt bijgewerkt, start u het apparaat opnieuw op om de status bij te werken en de nieuwste build op te halen.
>
> - De spraakopdracht 'Apparaat opnieuw opstarten' werkt goed.
> - U kunt ook de knop Opnieuw opstarten kiezen in Instellingen/Windows Insider-programma.
>
> Er is een fout in de back-end die u mogelijk hebt aangetroffen, zodat u weer op schema komt.

Ga op HoloLens 2 apparaat naar **Instellingen**  >  **Update & Security**  >  **Windows Insider-programma** en selecteer **Aan de slag.** Koppel het account dat u hebt gebruikt om u te registreren als Windows Insider.

> [!NOTE]
> Als u uw apparaat wilt inschrijven bij Insider-builds, moet u optionele telemetrie inschakelen. Als u dit nog niet hebt gedaan, opent u de Instellingen-app en selecteert u **Privacy** Diagnostics & feedback en selecteert u vervolgens  ->   **Optionele diagnostische gegevens.**

Windows insider gaat nu over op Kanalen. De **snelle** ring wordt het **Dev-kanaal,** de langzame **ring** wordt de **bèta-kanaal** en de **Release Preview-ring** wordt het **Release Preview-kanaal.** Deze toewijzing ziet er als volgende uit:

![Windows Uitleg van Insider Channels.](images/WindowsInsiderChannels.png)

Zie [Introducing Windows Insider Channels (Introductie Windows Insider Channels)](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) op Windows Blogs.
Selecteer vervolgens **Actieve ontwikkeling van Windows**, kies of u het **Dev-kanaal** wilt ontvangen of bèta-kanaal **builds** en bekijk de programmavoorwaarden.
Selecteer **Bevestigen > Nu opnieuw opstarten om** te voltooien. Nadat het apparaat opnieuw is opgestart, gaat u naar **Instellingen > Update & Security > Controleren** op updates om de nieuwste build op te halen.

### <a name="update-error-0x80070490-work-around"></a>Updatefout 0x80070490 work-around

Als er een updatefout wordt 0x80070490 bij het bijwerken op het kanaal Dev of Beta, probeert u de volgende korte-termijn-work-around. Dit omvat het verplaatsen van uw insider-kanaal, het ophalen van de update en vervolgens het terug verplaatsen van uw Insider-kanaal.

#### <a name="stage-one---release-preview"></a>Fase 1 - preview-versie

1. Instellingen, Update & Security en selecteer Windows Insider-programma Release **Preview Channel.**

2. Instellingen, & bijwerken, Windows Bijwerken, Controleren op **updates.** Na de update gaat u verder met Fase 2.

#### <a name="stage-two---dev-channel"></a>Fase 2 - Dev-kanaal

1. Instellingen, Update & Security en selecteer Windows Insider-programma **Dev Channel.**

2. Instellingen, & bijwerken, Windows Bijwerken, Controleren op **updates.**

## <a name="ffu-download-and-flash-directions"></a>FFU-download- en flashbeschrijvingen

Als u wilt testen met een met een vlucht ondertekende ffu, moet u eerst uw apparaat ontgrendelen voordat de met de vlucht ondertekende ffu wordt geflitst.

1. Op pc:
    1. Download ffu naar uw pc vanaf [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .

    1. Installeer ARC (Advanced Recovery Companion) vanuit de Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .

1. On HoloLens - Flight Unlock: open **Instellingen** Update & Security Windows Insider-programma registreer het apparaat  >    >   en start het opnieuw op.

1. Flash-FFU: u kunt nu de met de vlucht ondertekende FFU flashen met behulp van ARC.

### <a name="provide-feedback-and-report-issues"></a>Feedback geven en problemen rapporteren

Gebruik de [Feedback-hub-app op](hololens-feedback.md) uw HoloLens feedback te geven en problemen te melden. Het Feedback-hub zorgt ervoor dat alle benodigde diagnostische gegevens worden opgenomen om onze technici te helpen snel fouten op te sporen en het probleem op te lossen.  Problemen met de Chinese en Japanse versie van HoloLens moeten op dezelfde manier worden gerapporteerd.

> [!NOTE]
> Zorg ervoor dat u de prompt accepteert waarin wordt gevraagd of u Feedback-hub documenten wilt openen (selecteer **Ja** wanneer u hier om wordt gevraagd).

## <a name="note-for-developers"></a>Opmerking voor ontwikkelaars

U bent welkom en aangemoedigd om uw toepassingen te ontwikkelen met insider-builds van HoloLens.  Bekijk de documentatie [HoloLens ontwikkelaars om](https://developer.microsoft.com/windows/mixed-reality/development) aan de slag te gaan. Deze instructies werken met Insider-builds van HoloLens.  U kunt dezelfde builds van Unity en Visual Studio die u al gebruikt voor HoloLens ontwikkeling.

## <a name="stop-receiving-insider-builds"></a>Ontvangst van Insider-builds stoppen

Als u geen Insider-builds van Windows Holographic meer wilt ontvangen, kunt u zich uitloggen wanneer uw [](hololens-recovery.md) HoloLens een productie-build wordt uitgevoerd. U kunt uw apparaat ook herstellen met behulp van advanced recovery companion om uw apparaat te herstellen naar een niet-Insider-versie van Windows Holographic.

> [!CAUTION]
> Er is een bekend probleem waarbij gebruikers die de registratie van Insider Preview-builds ongedaan maken nadat ze handmatig een nieuwe preview-build hebben geïnstalleerd, een blauw scherm krijgen. Daarna moeten ze hun apparaat handmatig herstellen. Bekijk meer over dit bekende probleem voor meer informatie over of u hier al dan niet [mee te maken zou krijgen.](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)

Controleren of uw HoloLens een productie-build wordt uitgevoerd:

1. Ga naar **Instellingen > System > About** en zoek het buildnummer.

1. [Zie de releasenotities voor productie-buildnummers.](hololens-release-notes.md)

Als u zich wilt af melden voor Insider-builds:

1. Ga op HoloLens met een productie-build naar Update **& Instellingen > Security > Windows Insider-programma** en selecteer Stop Insider **builds.**

1. Volg de instructies om uw apparaat uit te kiezen.
