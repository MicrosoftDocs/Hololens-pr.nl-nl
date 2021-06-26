---
title: De HoloLens 2
description: Meer informatie over het controleren van uw HoloLens-buildnummer, het up-to-date houden van apparaatupdates, het deelnemen aan het Insiders-programma en het terugdraaien van updates.
keywords: how-to, update, roll back, HoloLens, check build, build number
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/27/2019
audience: ITPro
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens 2
ms.openlocfilehash: a27eb1d5eb32a6654f60aac98090cba1aab529d3
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924108"
---
# <a name="update-hololens-2"></a>De HoloLens 2

HoloLens gebruikt Windows Update, net als andere Windows 10 apparaten. Uw HoloLens downloadt en installeert automatisch systeemupdates wanneer deze is aangesloten op stroom en is verbonden met internet, zelfs wanneer deze stand-by is.

In dit artikel worden HoloLens-hulpprogramma's voor het volgende beschreven:

- uw huidige besturingssysteemversie weergeven (buildnummer)
- controleren op updates
- HoloLens handmatig bijwerken
- terugrollen naar een oudere update

## <a name="check-your-operating-system-version-build-number"></a>Controleer de versie van uw besturingssysteem (buildnummer)

U kunt het systeemversienummer (buildnummer) controleren door de app Instellingen te openen en **Systeem over te**  >  **selecteren.**

## <a name="check-for-updates-and-manually-update"></a>Controleren op updates en handmatig bijwerken

U kunt op elk moment in de instellingen controleren op updates.  Beschikbare updates bekijken en controleren op nieuwe updates:

1. Open de app **Instellingen**.
1. Navigeer **naar Update & Security**  >  **Windows Update**.
1. Selecteer **Controleren op updates**.

Als er een update beschikbaar is, wordt de nieuwe versie gedownload. Nadat het downloaden is voltooid, selecteert u de knop **Nu** opnieuw opstarten om de installatie te activeren. Als uw apparaat minder dan 40% is en niet is aangesloten, wordt de update niet opnieuw opgestart.

Terwijl uw HoloLens de update installeert, worden er draaiende tandwielen en een voortgangsindicator weergegeven. Schakel uw HoloLens gedurende deze periode niet uit. Deze wordt automatisch opnieuw opgestart zodra de installatie is voltooid.

HoloLens past één update per keer toe.  Als uw HoloLens meer dan één versie achter de meest recente versie ligt, moet u het updateproces mogelijk meerdere keren doorlopen om deze volledig up-to-date te krijgen.

## <a name="go-back-to-a-previous-version"></a>Terug naar een eerdere versie

In sommige gevallen wilt u misschien teruggaan naar een eerdere versie van de HoloLens-software. De aanbevolen stappen zijn:

1. Neem contact op met ondersteuning om te zien of ze uw probleem kunnen oplossen.
    1. Zorg ervoor **dat Optionele** of **Volledige** telemetrie is ingeschakeld. Hierdoor kan uw fout beter worden ondernomen en kunnen technici gemakkelijker een diagnose stellen.
    1. [Bestandsfeedback](hololens-feedback.md) is zo beschrijvend mogelijk. Noteer de titel of gebruik de functie voor delen, zodat u uw fout kunt delen met ondersteuning.
    1. Neem contact [op met ondersteuning](https://aka.ms/hlsupport). Als uw probleem een probleem is dat moet worden opgelost door terug te keren naar een eerdere versie, kunnen ze u de FFU geven om uw apparaat te laten knipperen.

1. Als dat niet werkt, stelt u uw gegevens opnieuw in of [HoloLens 2 de Advanced Recovery Companion](hololens-recovery.md).
    1. Download advanced Recovery [Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) op uw pc van de Microsoft Store.
    1. Zorg ervoor dat er geen telefoons of Windows-apparaten op uw pc zijn aangesloten.
    1. Kies naar welke versie u wilt flashen:
        1. U kunt de meest [recente versie HoloLens 2 downloaden.](https://aka.ms/hololens2download)
        1. U kunt de standaard build gebruiken die ARC-hosts gebruikt. (Als u deze optie kiest, slaat u de volgende stap over.)
        1. U kunt een buildondersteuning gebruiken die u hebt geleverd.
    1. Wanneer u deze downloads hebt voltooid, opent u **Bestandenverkenner**  >  **Downloads.** Klik met de rechtermuisknop op de ingepakte map die u zojuist hebt gedownload en selecteer **Alles** uitpakken  >  **om** deze uit tepakken.
    1. Sluit uw HoloLens aan op uw pc met behulp van een USB-A-naar-USB-C-kabel. (Zelfs als u andere kabels hebt gebruikt om uw HoloLens aan te sluiten, werkt deze het beste.)
    1. De Companion voor geavanceerd herstel detecteert automatisch uw HoloLens. Selecteer de **Microsoft HoloLens** tegel.
    1. Selecteer in het volgende scherm **Handmatige pakketselectie** en selecteer vervolgens het installatiebestand in de map die u in stap 4 hebt uitgepakt. (Zoek naar een bestand met de extensie .ffu.)
    1. Selecteer **Software installeren** en volg de instructies.

> [!NOTE]
> Als u terug gaat naar een eerdere versie, worden uw persoonlijke bestanden en instellingen verwijderd.

Als u de momenteel geïnstalleerde versie wilt blijven, kunt u updates ook [handmatig onderbreken.](hololens-updates.md#pause-updates-via-device) Dit geeft het technische team tijd om het probleem op te lossen.

## <a name="windows-insider-program-on-hololens"></a>Windows Insider-programma hololens

Wilt u de nieuwste functies in HoloLens zien?  Als dat het zo is, voegt u Windows Insider-programma; U krijgt toegang tot preview-versies van HoloLens-software-updates voordat deze beschikbaar zijn voor het algemene publiek.

[Bekijk Windows Insider preview voor Microsoft HoloLens](hololens-insider.md).
