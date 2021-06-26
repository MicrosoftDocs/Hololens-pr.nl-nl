---
title: HoloLens 1 opnieuw opstarten, opnieuw instellen of herstellen
ms.reviewer: Keep up to date on the basic and advanced instructions for rebooting or resetting your HoloLens mixed reality device.
description: Windows Device Recovery Tool gebruiken om een afbeelding te flashen naar HoloLens 1e Gen.
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
ms.openlocfilehash: 5963be84a5fbb186c77965d9bbf112713fea8242
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923513"
---
# <a name="restart-reset-or-recover-hololens-1st-gen"></a>HoloLens (1st Gen) opnieuw opstarten, opnieuw instellen of herstellen

Als u problemen ondervindt met uw HoloLens, kunt u proberen het apparaat opnieuw op te starten of opnieuw in te stellen, of het apparaat zelfs opnieuw instellen met behulp van apparaatherstel. In dit artikel worden de aanbevolen herstelstappen in de volgorde van de stappen beschreven.

Als u een herstel van een HoloLens 2, zie [Een](hololens-recovery.md)HoloLens 2 herstellen, aangezien dat proces verschilt.

> [!NOTE]
> Dit artikel is gericht op het HoloLens-apparaat en de software. Als uw hologrammen er niet goed uitzien, bekijkt u Overwegingen voor **[de HoloLens-omgeving](hololens-environment-considerations.md)** voor informatie over factoren die de kwaliteit van hologrammen verbeteren.

## <a name="restart"></a>Opnieuw starten

### <a name="do-a-safe-restart-by-using-cortana"></a>Veilig opnieuw opstarten met Cortana

De veiligste manier om de HoloLens opnieuw op te starten, is met behulp van Cortana. Dit is doorgaans het eerste wat u moet proberen wanneer u een probleem met HoloLens ervaart.

> [!NOTE] 
> Cortana is niet op alle apparaten beschikbaar.
> - Cortana is beschikbaar op alle HoloLens-apparaten (1st Gen). 
> - Cortana is beschikbaar op HoloLens 2 op builds vóór de Windows Holograpic-update van versie 2004.

1. Schakel uw HoloLens in.
1. Zorg ervoor dat een gebruiker is aangemeld en dat het apparaat niet wacht op een wachtwoord om het te ontgrendelen.
2. Zeg 'Hey Cortana, opnieuw opstarten' of 'Hey Cortana, opnieuw opstarten'.
3. Cortana reageert en vraagt u om te bevestigen. Wacht tot er na de vraag een geluid wordt afspelen en zeg vervolgens Ja. Het apparaat wordt opnieuw opgestart.

### <a name="use-the-power-button-to-do-a-safe-restart"></a>De aan/uit-knop gebruiken om veilig opnieuw op te starten

Als u het apparaat nog steeds niet opnieuw kunt opstarten, probeert u het opnieuw op te starten met behulp van de **aan/uit-knop:**

1. Houd de **aan/uit-knop** vijf seconden ingedrukt. Na 1 seconde zullen alle vijf de LED's zich uitsijen en vervolgens één voor één uitschakelen van rechts naar links. Na 5 seconden zijn alle LED's uitgeschakeld, wat aangeeft dat het afsluiten is geslaagd.
      
   > [!IMPORTANT]
   > Stop met het indrukken van de knop direct nadat alle LED's zijn uitgeschakeld.
1. Wacht 1 minuut totdat het afsluiten is voltooid. Het afsluiten wordt mogelijk nog uitgevoerd, zelfs nadat de weergaven zijn uitgeschakeld.
2. Schakel het apparaat opnieuw in  door op de aan/uit-knop te drukken en deze 1 seconde ingedrukt te houden.

### <a name="do-a-safe-restart-by-using-windows-device-portal"></a>Veilig opnieuw opstarten met behulp van Windows Apparaatportal

> [!NOTE]
> Voor dit proces moet HoloLens worden geconfigureerd als een apparaat voor ontwikkelaars. Meer informatie op [Windows Apparaatportal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).

Als de vorige procedure niet werkt, probeert u het apparaat opnieuw op te starten met behulp [van Windows Apparaatportal.](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) Zoek in de rechterbovenhoek de optie om het apparaat opnieuw op te starten of af te sluiten.

### <a name="do-an-unsafe-forced-restart"></a>Onveilig geforceerd opnieuw opstarten

Als uw HoloLens niet opnieuw is opgestart met de vorige methoden, forceer dan opnieuw opstarten. Deze methode is gelijk aan het verwijderen en opnieuw installeren van de accu. Dit is gevaarlijk omdat uw apparaat hierdoor beschadigd kan raken. Als dat gebeurt, moet u uw HoloLens laten knipperen.  

> [!WARNING]
> Dit is een mogelijk schadelijke methode en mag alleen worden gebruikt als de eerder genoemde methoden niet werken.

1. Houd de **aan/uit-knop** ten minste 10 seconden ingedrukt.
   - Het is geen probleem om de knop langer dan 10 seconden ingedrukt te houden.
   - Het is veilig om LED-activiteiten te negeren.
1. Laat de knop los en wacht 2-3 seconden.
1. Houd de **aan/uit-knop** 1 seconde ingedrukt.
1. Als u nog steeds  problemen hebt, drukt u 4 seconden op de aan/uit-knop totdat alle batterijindicatoren verdwijnen en het scherm geen hologrammen meer we weergeven. Wacht 1 minuut en druk vervolgens opnieuw op **de aan/uit-knop** om het apparaat in te zetten.

## <a name="go-back-to-a-previous-version---hololens-1st-gen"></a>Terug naar een eerdere versie - HoloLens (1e Gen)

In sommige gevallen wilt u mogelijk teruggaan naar een eerdere versie van de HoloLens-software. U kunt dit doen door het Hulpprogramma voor herstel van Windows-apparaten te gebruiken om uw HoloLens opnieuw in te stellen op de eerdere versie.

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

## <a name="reset-to-factory-settings"></a>Fabrieksinstellingen herstellen

> [!NOTE]
> De accu moet ten minste 40 procent worden belast om opnieuw in te stellen.

Als uw HoloLens nog steeds een probleem heeft, kunt u deze opnieuw instellen op de fabrieksstaat. Deze stap behoudt de versie van de Windows Holographic-software die erop is geïnstalleerd en retourneert de rest naar de fabrieksinstellingen.

>[!WARNING]
> Als u uw apparaat opnieuw in stelt, worden al uw persoonlijke gegevens, apps en instellingen gewist, inclusief informatie over het opnieuw instellen van TPM. Bij het opnieuw instellen wordt alleen de meest recente geïnstalleerde versie van Windows Holographic geïnstalleerd. U moet alle initialisatiestappen opnieuw doen (kalibreren, verbinding maken met Wi-Fi, een gebruikersaccount maken, apps downloaden, etc.).

1. Open de app Instellingen en selecteer vervolgens **Herstel**  >  **bijwerken.**
1. Selecteer de **optie Apparaat opnieuw** instellen en lees het bevestigingsbericht.
1. Bevestig het opnieuw instellen. Het apparaat wordt opnieuw opgestart en er wordt een set draaiende tandwielen en een voortgangsbalk weergegeven.
1. Wacht ongeveer 30 minuten totdat dit proces is voltooid. Wanneer dit is gebeurd, wordt het apparaat opnieuw opgestart in de out-of-the-box-ervaring.

## <a name="reinstall-the-operating-system"></a>Het besturingssysteem opnieuw installeren

Als het apparaat nog steeds een probleem heeft na het opnieuw opstarten en opnieuw instellen, kunt u een herstelprogramma op uw computer gebruiken om het HoloLens-besturingssysteem en de firmware opnieuw te installeren.  

De gegevens die HoloLens nodig heeft voor het opnieuw instellen, worden verpakt in een volledige Flash Update (FFU), die vergelijkbaar is met een .iso-, WIM- of .vhd-bestand. [Meer informatie over bestandsindelingen voor FFU-afbeeldingen.](https://docs.microsoft.com/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

U kunt een nieuw besturingssysteem installeren op uw HoloLens (1e generatie) met behulp van de Windows Device Recovery Tool. Voordat u dat hulpprogramma gebruikt, moet u zien of het probleem wordt opgelost door uw HoloLens opnieuw te starten of opnieuw in te stellen.

Het herstelproces kan even duren. Wanneer dit is gebeurd, wordt de nieuwste versie van de Windows Holographic-software geïnstalleerd.

Als u het hulpprogramma wilt gebruiken, hebt u een computer Windows 10 of hoger met ten minste 4 GB vrije opslagruimte. U kunt dit hulpprogramma niet uitvoeren op een virtuele machine.

### <a name="recover-your-hololens"></a>Uw HoloLens herstellen

1. Download en installeer het [Hulpprogramma voor herstel van Windows-apparaten](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) op uw computer.
1. Sluit de HoloLens (1e generatie) aan op uw computer met behulp van de Micro USB-kabel die bij uw HoloLens is meegeleverd.
1. Open het Hulpprogramma voor herstel van Windows-apparaten en volg de instructies.

Als de HoloLens (1e generatie) niet automatisch wordt gedetecteerd, selecteert u **Mijn apparaat is niet gedetecteerd.** Volg vervolgens de instructies om het apparaat in de herstelmodus te zetten.

### <a name="manual-flashing-mode"></a>Handmatige knippermodus

Als uw apparaat niet wordt gedetecteerd, volgt u deze stappen om het in de knippermodus te zetten:

1. Ontkoppel het apparaat van een voedingsbron.
1. Als het apparaat is aan staat, houdt u de **aan/uit-knop** ingedrukt totdat het volledig wordt uitgeschakeld.
2. Houd de **volumeknop ingedrukt** en tik kort op **de aan/uit-knop.** Het apparaat moet starten en alleen de middelste LED weergeven.
3. Sluit het apparaat aan op uw pc.
4. Open het Hulpprogramma voor apparaatherstel van Windows.
5. Selecteer **Mijn apparaat is niet gedetecteerd** en selecteer vervolgens **HoloLens**. 
6. Volg de instructies om uw apparaat te herstellen.
