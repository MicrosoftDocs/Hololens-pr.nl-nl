---
title: HoloLens bijwerken
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
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ef1721c60aca82d20e60636cbf4301de81c0177c
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/19/2021
ms.locfileid: "111377874"
---
# <a name="update-hololens"></a>HoloLens bijwerken

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

Als er een update beschikbaar is, wordt de nieuwe versie gedownload. Nadat het downloaden is voltooid, selecteert u de knop **Nu** opnieuw opstarten om de installatie te activeren. Als uw apparaat lager is dan 40% en niet is aangesloten, wordt de update niet opnieuw opgestart.

Terwijl uw HoloLens de update installeert, worden er draaiende tandwielen en een voortgangsindicator weergegeven. Schakel uw HoloLens gedurende deze periode niet uit. Deze wordt automatisch opnieuw opgestart zodra de installatie is voltooid.

HoloLens past één update per keer toe.  Als uw HoloLens meer dan één versie achter de meest recente versie ligt, moet u het updateproces mogelijk meerdere keren doorlopen om deze volledig up-to-date te krijgen.

## <a name="go-back-to-a-previous-version---hololens-2"></a>Terug naar een eerdere versie - HoloLens 2

In sommige gevallen wilt u misschien teruggaan naar een eerdere versie van de HoloLens-software. U kunt dit doen door advanced Recovery Companion te gebruiken om uw HoloLens opnieuw in te stellen op de eerdere versie.

> [!NOTE]
> Als u terug gaat naar een eerdere versie, worden uw persoonlijke bestanden en instellingen verwijderd.

Als u wilt teruggaan naar een eerdere versie van HoloLens 2, volgt u deze stappen:

1. Zorg ervoor dat er geen telefoons of Windows-apparaten op uw pc zijn aangesloten.
1. Download advanced Recovery [Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) op uw pc van de Microsoft Store.
1. Download de [meest recente HoloLens 2 release](https://aka.ms/hololens2download).
1. Wanneer u klaar bent met downloaden, opent u **Bestandenverkenner**  >  **Downloads.** Klik met de rechtermuisknop op de ingepakte map die u zojuist hebt gedownload en selecteer **Alles uitpakken**  >  **om** deze uit tepakken.
1. Sluit uw HoloLens aan op uw pc met behulp van een USB-A-naar-USB-C-kabel. (Zelfs als u andere kabels hebt gebruikt om uw HoloLens aan te sluiten, werkt deze het beste.)
1. De Companion voor geavanceerd herstel detecteert automatisch uw HoloLens. Selecteer de **Microsoft HoloLens** tegel.
1. Selecteer in het volgende scherm **Handmatige pakketselectie** en selecteer vervolgens het installatiebestand in de map die u in stap 4 hebt uitgepakt. (Zoek naar een bestand met de extensie .ffu.)
1. Selecteer **Software installeren** en volg de instructies.

## <a name="go-back-to-a-previous-version---hololens-1st-gen"></a>Terug naar een eerdere versie - HoloLens (1e generatie)

In sommige gevallen wilt u misschien teruggaan naar een eerdere versie van de HoloLens-software. U kunt dit doen door het Hulpprogramma voor herstel van Windows-apparaten te gebruiken om uw HoloLens opnieuw in te stellen op de eerdere versie.

> [!NOTE]
> Als u terug gaat naar een eerdere versie, worden uw persoonlijke bestanden en instellingen verwijderd.

Als u wilt teruggaan naar een eerdere versie van HoloLens 1, volgt u deze stappen:

1. Zorg ervoor dat er geen telefoons of Windows-apparaten op uw pc zijn aangesloten.
1. Download windows Device [Recovery Tool (WDRT)](https://support.microsoft.com/help/12379)op uw pc.
1. Download het [herstelpakket voor HoloLens Jubileumupdate.](https://aka.ms/hololensrecovery)
1. Wanneer de downloads zijn gedownload, opent u   >  **Bestandenverkenner Downloads.** Klik met de rechtermuisknop op de ingepakte map die u zojuist hebt gedownload en selecteer **Alles** uitpakken  >  **om** deze uit tepakken.
1. Sluit uw HoloLens aan op uw pc met behulp van de micro-USB-kabel die bij deze kabel is meegeleverd. (Zelfs als u andere kabels hebt gebruikt om uw HoloLens aan te sluiten, werkt deze het beste.)
1. De WDRT detecteert automatisch uw HoloLens. Selecteer de **Microsoft HoloLens** tegel.
1. Selecteer in het volgende scherm **Handmatige pakketselectie** en kies het installatiebestand in de map die u in stap 4 hebt uitgepakt. (Zoek naar een bestand met de extensie .ffu.)
1. Selecteer **Software installeren** en volg de instructies.

> [!NOTE]
> Als de WDRT uw HoloLens niet detecteert, start u de pc opnieuw op. Als dat niet werkt, selecteert u Mijn apparaat is niet **gedetecteerd,** selecteert u **Microsoft HoloLens** en volgt u de instructies.

## <a name="windows-insider-program-on-hololens"></a>Windows Insider-programma hololens

Wilt u de nieuwste functies in HoloLens zien?  Als dat het zo is, voegt u Windows Insider-programma; U krijgt toegang tot preview-versies van HoloLens-software-updates voordat deze beschikbaar zijn voor het algemene publiek.

[Bekijk Windows Insider preview voor Microsoft HoloLens](hololens-insider.md).
