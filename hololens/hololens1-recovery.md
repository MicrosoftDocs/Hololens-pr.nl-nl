---
title: Opnieuw opstarten, opnieuw instellen of herstellen HoloLens 1
ms.reviewer: Keep up to date on the basic and advanced instructions for rebooting or resetting your HoloLens mixed reality device.
description: Het gebruik van Windows Device Recovery Tool om een afbeelding te flashen naar HoloLens 1st Gen.
keywords: how-to, reboot, reset, recover, hard reset, soft reset, power cycle, HoloLens, shut down, wdrt, windows device recovery tool
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.date: 06/01/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: medium
manager: yannisle
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 4840535030cc81f222cb25357474f1c751426e91
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032793"
---
# <a name="restart-reset-or-recover-hololens-1st-gen"></a>Opnieuw opstarten, opnieuw instellen of HoloLens herstellen (1e generatie)

Als u problemen ondervindt met uw HoloLens, kunt u proberen opnieuw op te starten of opnieuw in te stellen, of het apparaat zelfs opnieuw instellen met behulp van apparaatherstel. Dit artikel begeleidt u door de aanbevolen herstelstappen in de volgorde.

Als u een herstelproces wilt HoloLens 2, zie [Een](hololens-recovery.md)HoloLens 2 herstellen, aangezien dat proces anders is.

> [!NOTE]
> Dit artikel richt zich op de HoloLens en software. Als uw hologrammen er niet goed uitzien, bekijkt u HoloLens **[omgevingsoverwegingen](hololens-environment-considerations.md)** voor informatie over factoren die de kwaliteit van hologrammen verbeteren.

## <a name="restart"></a>Opnieuw starten

### <a name="do-a-safe-restart-by-using-cortana"></a>Veilig opnieuw opstarten met behulp van Cortana

De veiligste manier om de HoloLens opnieuw op te starten, is door Cortana te gebruiken. Dit is meestal het eerste wat u moet proberen wanneer u een probleem met HoloLens.

> [!NOTE] 
> Cortana is niet op alle apparaten beschikbaar.
> - Cortana is beschikbaar op alle HoloLens (1st Gen)-apparaten. 
> - Cortana is beschikbaar op HoloLens 2-apparaten op builds vóór de Windows Holograpic-update van versie 2004.

1. Schakel uw HoloLens.
1. Zorg ervoor dat een gebruiker is aangemeld en dat het apparaat niet wacht op een wachtwoord om het te ontgrendelen.
2. Zeg 'Hey Cortana, reboot' of 'Hey Cortana, restart'.
3. Cortana antwoordt en u wordt gevraagd om te bevestigen. Wacht tot er na de vraag een geluid wordt afspelen en zeg vervolgens Ja. Het apparaat wordt opnieuw opgestart.

### <a name="use-the-power-button-to-do-a-safe-restart"></a>De aan/uit-knop gebruiken om veilig opnieuw op te starten

Als u het apparaat nog steeds niet opnieuw kunt opstarten, probeert u het opnieuw op te starten met behulp van de **aan/uit-knop:**

1. Houd de **aan/uit-knop** vijf seconden ingedrukt. Na 1 seconde gaan alle vijf led's uit en schakelen ze één voor één van rechts naar links uit. Na 5 seconden zijn alle LED's uitgeschakeld, wat aangeeft dat het afsluiten is geslaagd.
      
   > [!IMPORTANT]
   > Stop met het indrukken van de knop direct nadat alle LED's zijn uitgeschakeld.
1. Wacht 1 minuut totdat het afsluiten is voltooid. Het afsluiten wordt mogelijk nog uitgevoerd, zelfs nadat de weergaven zijn uitgeschakeld.
2. Schakel het apparaat opnieuw in door 1 seconde op de **aan/uit-knop** te drukken en ingedrukt te houden.

### <a name="do-a-safe-restart-by-using-windows-device-portal"></a>Veilig opnieuw opstarten met behulp van Windows Apparaatportal

> [!NOTE]
> Voor dit proces moet HoloLens worden geconfigureerd als een apparaat voor ontwikkelaars. Meer informatie op [Windows Apparaatportal](/windows/mixed-reality/using-the-windows-device-portal).

Als de vorige procedure niet werkt, probeert u het apparaat opnieuw op te starten met behulp [van Windows Apparaatportal](/windows/mixed-reality/using-the-windows-device-portal). Zoek in de rechterbovenhoek de optie om het apparaat opnieuw op te starten of af te sluiten.

### <a name="do-an-unsafe-forced-restart"></a>Onveilig geforceerd opnieuw opstarten

Als de vorige methoden uw apparaat niet opnieuw hebben HoloLens, forceer dan opnieuw opstarten. Deze methode is gelijk aan het verwijderen en opnieuw installeren van de batterij. Dit is gevaarlijk omdat uw apparaat hierdoor beschadigd kan raken. Als dat gebeurt, moet u uw HoloLens.  

> [!WARNING]
> Dit is een mogelijk schadelijke methode en mag alleen worden gebruikt als de eerder genoemde methoden niet werken.

1. Houd de **aan/uit-knop** ten minste tien seconden ingedrukt.
   - Het is geen probleem om de knop langer dan 10 seconden ingedrukt te houden.
   - Het is veilig om led-activiteiten te negeren.
1. Laat de knop los en wacht 2-3 seconden.
1. Houd de **aan/uit-knop** 1 seconde ingedrukt.
1. Als u nog steeds  problemen hebt, drukt u 4 seconden op de aan/uit-knop totdat alle batterijindicatoren verdwijnen en het scherm geen hologrammen meer we weergeven. Wacht 1 minuut en druk vervolgens nogmaals op **de aan/uit-knop** om het apparaat in te zetten.

## <a name="go-back-to-a-previous-version---hololens-1st-gen"></a>Terug naar een eerdere versie - HoloLens (1e generatie)

In sommige gevallen wilt u mogelijk teruggaan naar een eerdere versie van de HoloLens software. U kunt dit doen met behulp van Windows Device Recovery Tool om uw apparaat opnieuw in HoloLens naar de eerdere versie.

> [!NOTE]
> Als u terug gaat naar een eerdere versie, worden uw persoonlijke bestanden en instellingen verwijderd.

Als u wilt teruggaan naar een eerdere versie van HoloLens 1, volgt u deze stappen:

1. Zorg ervoor dat u geen telefoons of apparaten hebt Windows zijn aangesloten op uw pc.
1. Download op uw pc de [Windows Device Recovery Tool (WDRT).](https://support.microsoft.com/help/12379)
1. Download het [herstelpakket HoloLens Jubileumupdate.](https://aka.ms/hololensrecovery)
1. Wanneer het downloaden is voltooien, opent u   >  **Bestandenverkenner Downloads.** Klik met de rechtermuisknop op de ingepakte map die u zojuist hebt gedownload en selecteer **Alles** uitpakken  >  **om** het uit tepakken.
1. Verbinding maken uw HoloLens op uw pc met behulp van de micro-USB-kabel bij de kabel. (Zelfs als u andere kabels hebt gebruikt om uw HoloLens, werkt deze het beste.)
1. De WDRT detecteert automatisch uw HoloLens. Selecteer de **Microsoft HoloLens** tegel.
1. Selecteer in het volgende scherm Handmatige **pakketselectie** en kies het installatiebestand in de map die u in stap 4 hebt uitgepakt. (Zoek naar een bestand met de extensie .ffu.)
1. Selecteer **Software installeren** en volg de instructies.

> [!NOTE]
> Als de WDRT uw apparaat niet HoloLens, start u de pc opnieuw op. Als dat niet werkt, selecteert u Mijn apparaat is niet **gedetecteerd,** selecteert **Microsoft HoloLens** en volgt u de instructies.

## <a name="reset-to-factory-settings"></a>Fabrieksinstellingen herstellen

> [!NOTE]
> De accu moet ten minste 40 procent worden belast om opnieuw in te stellen.

Als uw HoloLens nog steeds een probleem heeft, kunt u deze opnieuw instellen in de fabrieksstaat. Deze stap behoudt de versie van de Windows Holographic-software die erop is geïnstalleerd en retourneert de rest naar de fabrieksinstellingen.

>[!WARNING]
> Als u uw apparaat opnieuw in stelt, worden al uw persoonlijke gegevens, apps en instellingen gewist, inclusief informatie over het opnieuw instellen van TPM. Bij het opnieuw instellen wordt alleen de meest recente geïnstalleerde versie van Windows Holographic geïnstalleerd. U moet alle initialisatiestappen opnieuw doen (kalibreren, verbinding maken met Wi-Fi, een gebruikersaccount maken, apps downloaden, etc.).

1. Open de Instellingen app en selecteer vervolgens **Herstel**  >  **bijwerken.**
1. Selecteer de **optie Apparaat opnieuw** instellen en lees het bevestigingsbericht.
1. Bevestig het opnieuw instellen. Het apparaat wordt opnieuw opgestart en er wordt een set draaiende tandwielen en een voortgangsbalk weergegeven.
1. Wacht ongeveer 30 minuten tot dit proces is voltooid. Wanneer dit is gebeurd, wordt het apparaat opnieuw opgestart in de out-of-the-box-ervaring.

## <a name="reinstall-the-operating-system"></a>Het besturingssysteem opnieuw installeren

Als het apparaat nog steeds een probleem heeft na het opnieuw opstarten en opnieuw instellen, kunt u een herstelprogramma op uw computer gebruiken om het HoloLens besturingssysteem en firmware opnieuw te installeren.  

De gegevens die HoloLens nodig hebben voor het opnieuw instellen, worden verpakt in een volledige flashupdate (FFU), die vergelijkbaar is met een .iso-, WIM- of VHD-bestand. [Meer informatie over bestandsindelingen voor FFU-afbeeldingen.](/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

U kunt een nieuw besturingssysteem installeren op uw HoloLens (eerste generatie) met behulp van Windows Device Recovery Tool. Voordat u dat hulpprogramma gebruikt, moet u zien of het probleem wordt opgelost door uw HoloLens opnieuw in te stellen.

Het herstelproces kan even duren. Wanneer dit is gebeurd, wordt de nieuwste versie van Windows Holographic-software geïnstalleerd.

Als u het hulpprogramma wilt gebruiken, hebt u een computer Windows 10 of hoger met ten minste 4 GB vrije opslagruimte. U kunt dit hulpprogramma niet uitvoeren op een virtuele machine.

### <a name="recover-your-hololens"></a>Uw HoloLens

1. Download en installeer de [Windows Device Recovery Tool](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) op uw computer.
1. Verbinding maken de HoloLens (1e generatie) op uw computer met behulp van de Micro USB-kabel die bij uw HoloLens.
1. Open de Windows Device Recovery Tool en volg de instructies.

Als de HoloLens (eerste generatie) niet automatisch wordt gedetecteerd, selecteert u Mijn **apparaat is niet gedetecteerd.** Volg vervolgens de instructies om het apparaat in de herstelmodus te zetten.

### <a name="manual-flashing-mode"></a>Handmatige flashmodus

Als uw apparaat niet wordt gedetecteerd, volgt u deze stappen om het in de flashmodus te zetten:

1. Ontkoppel het apparaat van een voedingsbron.
1. Als het apparaat is aan, houdt u de **aan/uit-knop ingedrukt** totdat het volledig wordt uitgeschakeld.
2. Houd de **volumeknop ingedrukt** en tik kort op **de aan/uit-knop.** Het apparaat moet starten en alleen de middelste LED weergeven.
3. Sluit het apparaat aan op uw pc.
4. Open de Windows Device Recovery Tool.
5. Selecteer **Mijn apparaat is niet gedetecteerd** en selecteer **HoloLens.** 
6. Volg de instructies om uw apparaat te herstellen.
