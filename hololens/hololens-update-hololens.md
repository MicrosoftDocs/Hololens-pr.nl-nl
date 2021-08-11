---
title: Werk HoloLens 2
description: Informatie over het controleren van HoloLens buildnummer, het up-to-date houden van apparaatupdates, het deelnemen aan het Insiders-programma en het terugdraaien van updates.
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
ms.openlocfilehash: 7e63fcab4c64f151684a634bb24d9fc31826f6805d52b23c5672add0b6269430
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/05/2021
ms.locfileid: "115662832"
---
# <a name="update-hololens-2"></a>Werk HoloLens 2

HoloLens maakt gebruik van Windows Update, net als andere Windows 10 apparaten. Uw HoloLens automatisch systeemupdates downloaden en installeren wanneer deze zijn aangesloten op stroom en zijn verbonden met internet, zelfs wanneer deze stand-by is.

In dit artikel worden de HoloLens beschreven voor:

- uw huidige besturingssysteemversie weergeven (buildnummer)
- controleren op updates
- handmatig bijwerken HoloLens
- terugrollen naar een oudere update

## <a name="check-your-operating-system-version-build-number"></a>Controleer de versie van uw besturingssysteem (buildnummer)

U kunt het systeemversienummer (buildnummer) controleren door de app Instellingen openen en **Systeem over te**  >  **selecteren.**

## <a name="check-for-updates-and-manually-update"></a>Controleren op updates en handmatig bijwerken

U kunt op elk moment controleren op updates in de instellingen.  Beschikbare updates bekijken en controleren op nieuwe updates:

1. Open de app **Instellingen**.
1. **Navigeer naar Update & Security** Windows  >  **Update**.
1. Selecteer **Controleren op updates**.

Als er een update beschikbaar is, wordt de nieuwe versie gedownload. Nadat het downloaden is voltooid, selecteert u de knop **Nu** opnieuw opstarten om de installatie te activeren. Als uw apparaat minder dan 40% is en niet is aangesloten, wordt de update niet opnieuw geïnstalleerd.

Terwijl uw HoloLens update installeert, worden er draaiende tandwielen en een voortgangsindicator weergegeven. Schakel uw HoloLens gedurende deze tijd niet uit. Deze wordt automatisch opnieuw opgestart zodra de installatie is voltooid.

HoloLens wordt één update tegelijk toegepast.  Als uw HoloLens meer dan één versie achter de meest recente versie ligt, moet u het updateproces mogelijk meerdere keren doorlopen om deze volledig up-to-date te krijgen.

## <a name="go-back-to-a-previous-version"></a>Terug naar een eerdere versie

In sommige gevallen wilt u misschien teruggaan naar een eerdere versie van de HoloLens software. De aanbevolen stappen zijn:

1. Neem contact op met de ondersteuning om te zien of ze uw probleem kunnen oplossen.
    1. Zorg ervoor **dat Optionele** **of Volledige** telemetrie is ingeschakeld. Dit maakt uw fout bruikbaarder en gemakkelijker te diagnosticeren voor technici.
    1. [Bestandsfeedback](hololens-feedback.md) is zo beschrijvend mogelijk. Noteer de titel of gebruik de sharefunctie, zodat u uw fout kunt delen met ondersteuning.
    1. Neem contact [op met ondersteuning](https://aka.ms/hlsupport). Als uw probleem een probleem is dat moet worden opgelost door terug te keren naar een eerdere versie, kunnen ze u de FFU geven om uw apparaat te laten knipperen.

1. Als dat niet werkt, stelt u de gegevens opnieuw in of haalt u een [reflash op HoloLens 2 met de Advanced Recovery Companion](hololens-recovery.md).
    1. Download advanced Recovery [Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) op uw pc van de Microsoft Store.
    1. Zorg ervoor dat u geen telefoons of apparaten hebt Windows zijn aangesloten op uw pc.
    1. Kies welke versie u wilt flashen:
        1. U kunt de meest [recente versie HoloLens 2 downloaden.](https://aka.ms/hololens2download)
        1. U kunt de standaard build gebruiken die ARC-hosts bevat. (Als u deze optie kiest, slaat u de volgende stap over.)
        1. U kunt een build-ondersteuning gebruiken die u hebt geleverd.
    1. Wanneer u deze downloads hebt voltooid, opent u **Bestandenverkenner**  >  **Downloads.** Klik met de rechtermuisknop op de ingepakte map die u zojuist hebt gedownload en selecteer **Alles** uitpakken om het uit  >   tepakken.
    1. Verbinding maken verbinding HoloLens uw pc met behulp van een USB-A-naar-USB-C-kabel. (Zelfs als u andere kabels hebt gebruikt om uw HoloLens, werkt deze het beste.)
    1. Advanced Recovery Companion detecteert automatisch uw HoloLens. Selecteer de **Microsoft HoloLens** tegel.
    1. Selecteer in het  volgende scherm Handmatige pakketselectie en selecteer vervolgens het installatiebestand in de map die u in stap 4 hebt uitgepakt. (Zoek naar een bestand met de extensie .ffu.)
    1. Selecteer **Software installeren** en volg de instructies.

> [!NOTE]
> Als u terug gaat naar een eerdere versie, worden uw persoonlijke bestanden en instellingen verwijderd.

Als u de momenteel geïnstalleerde versie wilt blijven, kunt u bovendien updates [handmatig onderbreken.](hololens-updates.md#pause-updates-via-device) Hierdoor krijgt het technische team de tijd om het probleem op te lossen.

## <a name="windows-insider-program-on-hololens"></a>Windows Insider-programma op HoloLens

Wilt u de nieuwste functies in HoloLens?  Als dit het is, voegt u de Windows Insider-programma; U krijgt toegang tot preview-versies van HoloLens software-updates voordat deze beschikbaar zijn voor het algemene publiek.

[Bekijk Windows Insider-preview voor Microsoft HoloLens.](hololens-insider.md)
