---
title: Opnieuw opstarten, opnieuw instellen of HoloLens
ms.reviewer: Follow along with our basic and advanced instructions for rebooting or resetting your HoloLens 2 device.
description: Advanced Recovery Companion gebruiken om een afbeelding te flashen voor HoloLens 2.
keywords: how-to, reboot, reset, recover, hard reset, soft reset, power cycle, HoloLens, shut down, arc, advanced recovery companion
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.date: 08/30/2021
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: high
manager: jarrettr
appliesto:
- HoloLens 2
ms.openlocfilehash: e9aad32891bb093cbce18671b76549788b19afcb
ms.sourcegitcommit: c4fe077e9e19a3b0a9fad8defa4b51547c5ae3c8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/31/2021
ms.locfileid: "123261920"
---
# <a name="restart-reset-or-recover-hololens-2"></a>Opnieuw opstarten, opnieuw instellen of HoloLens 2

>[!IMPORTANT]
> Voordat u een probleemoplossingsprocedure start, moet u ervoor zorgen dat uw apparaat, indien mogelijk, wordt op geladen tot **20 tot 40** procent van de accucapaciteit. De [accuindicatorlichten onder](hololens2-setup.md#lights-that-indicate-the-battery-level) de aan/uit-knop zijn een snelle manier om de accucapaciteit te controleren zonder u aan te melden bij het apparaat.

Gebruik de [kabel en de USB Type-C-kabel](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) die bij de HoloLens 2 omdat dit de beste manier is om uw apparaat op te laden. De goederen leveren 18 W aan stroom (9V bij 2A). Door gebruik te maken van de meegeleverde HoloLens 2 de accu in minder dan 65 minuten vol wanneer het apparaat stand-by is. Als deze accessoires niet beschikbaar zijn, moet u ervoor zorgen dat de beschikbare thee ten minste 15W aan stroom kan ondersteunen.

> [!NOTE]
> Vermijd indien mogelijk het gebruik van een pc om het apparaat via USB op te laden, wat traag is.

Als het apparaat correct is opgestart en actief is, zijn er drie manieren om het laadniveau van de accu te controleren:

- In het hoofdmenu van de HoloLens gebruikersinterface van het apparaat.
- Bekijk de LED dicht bij de aan/uit-knop (voor een kosten van 40 procent ziet u ten minste twee solide LED's).
    - Wanneer het apparaat wordt op laden, wordt de accu-indicator licht om het huidige laadniveau aan te geven.  Het laatste licht vervaagt in en uit om aan te geven dat de kosten actief zijn.
    - Wanneer uw HoloLens is aan, geeft de batterijindicator het accuniveau in vijf stappen weer.
    - Wanneer slechts een van de vijf lampen is aan, is het accuniveau lager dan 20 procent.
    - Als het accuniveau kritiek laag is en u het apparaat probeert in te zetten, gaat er kort één lampje uit en gaat u uit.
- Open verkenner op uw host-pc **en** zoek naar uw HoloLens 2 aan de linkerkant onder **Deze pc.** Klik met de rechtermuisknop op het apparaat en selecteer **Eigenschappen.** In een dialoogvenster wordt het acculadingsniveau weergegeven.

   ![Een scherm HoloLens 2 eigenschappen toont het niveau van de batterijwijziging.](images/ResetRecovery2.png)

Als het apparaat niet kan worden opgestart naar het opstartmenu, noteer dan de LED-weergave en apparaatinsemulatie op de host-pc. Volg vervolgens de gids [voor probleemoplossing.](hololens-troubleshooting.md) Als de status van het apparaat niet overeen komt met een van de statussen die worden vermeld in de gids voor probleemoplossing, voert u de [procedure](hololens-recovery.md#hard-reset-procedure) voor het opnieuw instellen uit met het apparaat dat is verbonden met de voeding en niet met uw host-pc. Wacht ten minste één uur totdat het apparaat wordt op belast.

## <a name="reset-the-device"></a>Het apparaat opnieuw instellen

Onder bepaalde omstandigheden moet u het apparaat mogelijk handmatig opnieuw instellen zonder de gebruikersinterface van de software te gebruiken.

### <a name="standard-procedure"></a>Standaardprocedure

1. Koppel de Type-C-kabel los om het apparaat los te koppelen van de voeding of de host-pc.

2. Houd de **aan/uit-knop** 15 seconden ingedrukt. Alle LED's moeten uit zijn.

3. Wacht 2-3 seconden en druk vervolgens kort op de **aan/uit-knop.** De LED's dicht bij de aan/uit-knop worden aan het licht licht en het apparaat wordt opstart.

4. Verbinding maken apparaat naar de host-pc en open Apparaatbeheer. (Voor Windows 10 drukt u op **de Windows** toets en vervolgens op de **X-toets** en selecteert **u Apparaatbeheer**.) Zorg ervoor dat het apparaat op de juiste wijze wordt Microsoft HoloLens *zoals* wordt weergegeven in de volgende afbeelding:

   ![HoloLens 2 MicrosoftOloLensRecovery-devive manager.](images/MicrosoftHoloLens_DeviceManager.png)

### <a name="hard-reset-procedure"></a>Procedure voor hard opnieuw instellen

Als de standaardprocedure voor opnieuw instellen niet werkt, gebruikt u de procedure voor hard opnieuw instellen:

1. Koppel de Type-C-kabel los om het apparaat los te koppelen van de voeding of de host-pc.

1. Houd de **aan/uit-knoppen** op het volume  +   15 seconden in de wacht. Het apparaat wordt automatisch opnieuw opgestart.

1. Verbinding maken apparaat naar de host-pc.

1. Open Apparaatbeheer (voor Windows 10 drukt u op **Windows** toets en vervolgens op de **X-toets** en **selecteert u Apparaatbeheer**). Zorg ervoor dat het apparaat op de juiste wijze wordt Microsoft HoloLens *zoals* wordt weergegeven in de volgende afbeelding:

   ![HoloLens 2 MicrosoftOloLensRecovery-apparaat maanger 2.](images/MicrosoftHoloLens_DeviceManager.png)

## <a name="clean-reflash-the-device"></a>Schone reflash op het apparaat

In uitzonderlijke situaties moet u de HoloLens 2. Houd er rekening mee dat clean-reflash naar verwachting geen invloed heeft op de volgende problemen:

- [Kleur uniformiteit weergeven](hololens2-display.md)
- Opstarten met geluid, maar geen weergave-uitvoer
- [1-3-5-LED-patroon](hololens2-setup.md#lights-to-indicate-problems)
- [Oververhitting](hololens-environment-considerations.md#temperature-and-regulatory-information) 
- Crashes van het besturingssysteem (die verschillen van crashes van toepassingen)

Er zijn twee manieren om het apparaat te gebruiken. Voor beide moet u eerst [Advanced Recovery Companion installeren vanuit de Windows Store.](https://www.microsoft.com/store/productId/9P74Z35SFRS8)

>[!WARNING]
>Als u een reflash op uw apparaat gebruikt, worden al uw persoonlijke gegevens, apps en instellingen gewist, inclusief informatie over het opnieuw instellen van TPM.

Advanced Recovery Companion is standaard ingesteld om de meest recente build van de functiere release te downloaden; Zie voor meer informatie over de nieuwste functieversie [HoloLens 2 opmerkingen bij de release.](hololens-release-notes.md) Als u het meest recente HoloLens 2 Full Flash Update (FFU) wilt downloaden om uw apparaat te reflashen via Advanced Recovery Companion, downloadt u de meest recente maandelijkse HoloLens 2 afbeelding: [https://aka.ms/hololens2download](https://aka.ms/hololens2download) . Deze versie is de meest recente algemeen beschikbare build.

Voordat u de reflash-procedure start, moet u ervoor zorgen dat de app is geïnstalleerd en wordt uitgevoerd op uw Windows 10 pc en klaar is om het apparaat te detecteren. Zorg er ook voor dat uw HoloLens minimaal 40% in rekening wordt gebracht.

![HoloLens 2 scherm met een schone reflash.](images/ARC1.png)

### <a name="normal-procedure"></a>Normale procedure

1. Terwijl het HoloLens apparaat wordt uitgevoerd, verbindt u het met de Windows 10 pc waarop u eerder de Advanced Recovery Companion-app hebt geopend.

   Het apparaat wordt automatisch gedetecteerd en de gebruikersinterface van de Geavanceerde herstel companion-app start het updateproces:

   ![HoloLens 2 eerste scherm voor het opsnlitsen van de reflash.](images/ARC2.png)

1. Selecteer het HoloLens 2 in de gebruikersinterface van de Geavanceerde herstel companion-app en volg de instructies om de reflash te voltooien.

### <a name="manual-procedure"></a>Handmatige procedure

Mogelijk moet u het apparaat in de herstelmodus zetten als:

- De HoloLens 2 niet goed starten
- Advanced Recovery Companion kan het apparaat niet detecteren
- U weet het wachtwoord/de pincode niet meer voor een apparaat dat slechts één gebruiker heeft

1. Koppel de Type-C-kabel los om het apparaat los te koppelen van de voeding of de host-pc.

2. Houd de **aan/uit-knop** 15 seconden ingedrukt. Alle LED's moeten worden uitgeschakeld.

3. Druk terwijl u **op de volumeknop omhoog** drukt op de **aan/uit-knop** om het apparaat te starten. Wacht 15 seconden en laat het **volume vervolgens los.** Alleen de middelste LED van de vijf LED's wordt licht licht.

4. Verbinding maken het apparaat naar de host-pc en open Apparaatbeheer. (Druk Windows 10 op **Windows** toets en vervolgens op **de X-toets** en selecteer **Apparaatbeheer**.) Zorg ervoor dat het apparaat op de juiste manier Microsoft HoloLens zoals wordt weergegeven in de volgende afbeelding:

   ![HoloLens 2 MicrosoftOloLensRecovery.](images/MicrosoftHoloLensRecovery.png)

   Het apparaat wordt automatisch gedetecteerd en de gebruikersinterface van de Geavanceerde herstel companion-app start het updateproces:

   ![HoloLens 2 het scherm schone reflash.](images/ARC2.png)

6. Selecteer het HoloLens 2 in de gebruikersinterface van de Advanced Recovery Companion-app en volg de instructies om de reflash te voltooien.

## <a name="troubleshoot-advanced-recovery-companion"></a>Problemen met geavanceerde herstel-companion oplossen

1. Zorg ervoor dat er voor uw apparaat 40% of meer in rekening wordt gebracht voordat u een flash-poging doet.

1. Controleer of uw apparaat is ontgrendeld.

1. Controleer of uw apparaat rechtstreeks op de host-pc is aangesloten, niet op een hub.

1. Als uw apparaat niet wordt weergegeven als een HoloLens/HoloLens Recovery-apparaat onder Universal Serial Bus Drivers, controleert u het volgende:
    1. **Poorten**, als een Qualcomm HS-USB-apparaat
    1. **Andere apparaten**, als QUSB_BULK apparaat: op uw host-pc ontbreken de benodigde stuurprogramma's om uw apparaat te HoloLens. Klik met de rechtermuisknop en selecteer Stuurprogramma bijwerken en zoek online naar stuurprogramma's of schakel [Optionele updates in uw](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/improving-the-update-discoverability-experience/ba-p/1585674)Windows Instellingen bijwerken in. Nadat het stuurprogramma is gedownload, moet ARC het kunnen detecteren.

1. Als ARC uw apparaat niet detecteert, controleert u of u verbinding kunt maken met uw apparaat via Verkenner op uw pc. Als dat niet mogelijk is,

    1. Het is mogelijk dat uw apparaat USB-beleidsregels heeft die die verbinding uitschakelen. Probeer in dat opzicht [handmatige knippermodus](hololens-recovery.md#manual-procedure)uit.
    2. Als er geen beleidsregels zijn, probeert u een andere USB-kabel.

1. Controleer of op uw apparaat geen [1-3-5-LED-patroon wordt weergegeven.](hololens2-setup.md#lights-to-indicate-problems)

## <a name="download-arc-without-using-the-app-store"></a>ARC downloaden zonder de App Store te gebruiken

Als de IT-omgeving het gebruik van de Windows Store-app voorkomt of de toegang tot de winkel beperkt, kan de IT-beheerder deze app beschikbaar maken via een 'offline' implementatiepad.

 >[!NOTE]
 > - IT-beheerders kunnen deze app ook distribueren via System Center Configuration Manager (SCCM) of Intune.
 > - Deze handleiding is gericht op Advanced Recovery Companion, maar het proces kan ook worden gebruikt voor andere offline-apps.

Volg deze stappen om het implementatiepad in te stellen:

1. Ga naar de [Microsoft Store voor Bedrijven](https://businessstore.microsoft.com) en meld u aan met een Azure Active Directory identiteit.

1. Ga naar **Beheren – Instellingen**. Schakel **Offline-apps tonen in** onder **Winkelervaring.**

1. Ga naar **de winkel voor mijn groep en** zoek naar Advanced Recovery [**_Companion_**](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).

1. Wijzig het **licentietype** in **_offline_*_, en selecteer _* Beheren.**

1. Selecteer **onder Het pakket downloaden voor offlinegebruik** de tweede blauwe knop **Downloaden.** Zorg ervoor dat de bestandsextensie *.appxbundle is.*

    - Als de desktop-pc in dit stadium internettoegang heeft, dubbelklikt u op het pakket om de app te installeren.

    - Als de doel-pc geen internetverbinding heeft, volgt u deze stappen:
       1. Selecteer de niet-gecodeerde licentie en selecteer vervolgens **Licentie genereren.**
       2. Selecteer **onder Vereiste frameworks** de optie **Downloaden.**
       3. Gebruik DISM om het pakket toe te passen met de afhankelijkheid en licentie. Voer vanaf een opdrachtprompt van de beheerder de volgende opdracht uit:

          ```console
          C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
          ```
          > [!NOTE]
          > Het versienummer in dit codevoorbeeld komt mogelijk niet overeen met de momenteel beschikbare versie. Mogelijk hebt u ook een andere downloadlocatie gekozen dan in het voorbeeld. Wijzig de opdracht naar behoefte.

> [!TIP]
> Wanneer u van plan bent Advanced Recovery Companion te gebruiken om een FFU offline te installeren, kan het handig zijn om uw flash-installatie afbeelding te downloaden. [**Download de huidige afbeelding voor HoloLens 2**](https://aka.ms/hololens2download).

Andere resources:

- [Offline-apps distribueren](/microsoft-store/distribute-offline-apps) 
- [Service-opdrachtregelopties voor DISM-app-pakket (.appx of .appxbundle)](/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options)
