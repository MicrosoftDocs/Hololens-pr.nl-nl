---
title: Problemen met HoloLens-apparaten oplossen
description: Blijf op de hoogte van de meest voorkomende oplossingen voor HoloLens-apparaatproblemen en probleemoplossingstechnieken.
author: mattzmsft
ms.author: mazeller
ms.date: 12/02/2019
ms.prod: hololens
ms.topic: article
audience: HoloLens
ms.localizationpriority: medium
manager: jarrettr
ms.custom:
- CI 111456
- CSSTroubleshooting
keywords: problemen, bug, probleemoplossing, oplossing, hulp, ondersteuning, HoloLens, emulator
ms.openlocfilehash: b69dddf04ac31b69f0b2f8759d095806189f33ab
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924618"
---
# <a name="device-troubleshooting"></a>Problemen met apparaten oplossen

In dit artikel wordt beschreven hoe u een aantal veelvoorkomende HoloLens-problemen kunt oplossen.

>[!IMPORTANT]
> Voordat u een probleemoplossingsprocedure start, moet u ervoor zorgen dat uw apparaat, indien mogelijk, wordt geladen op **20 tot 40** procent van de accucapaciteit. De [accuindicatorlichten onder](hololens2-setup.md#lights-that-indicate-the-battery-level) de aan/uit-knop zijn een snelle manier om de accucapaciteit te controleren zonder u aan te melden bij het apparaat.

<a id="list"></a>

**Bekende problemen**
- [Remote Assist video na 20 minuten vast](#remote-assist-video-freezes-after-20-minutes)
- [Auto-login vraagt om aanmelden](#auto-login-asks-for-log-in)
- [Microsoft Edge kan niet worden starten](#microsoft-edge-fails-to-launch)
- [Toetsenbord schakelt niet over naar speciale tekens](#keyboard-doesnt-switch-to-special-characters)
- [Er wordt geen fout weergegeven bij het downloaden van vergrendelde bestanden](#downloading-locked-files-doesnt-error)
- [Apparaatportal-out voor uploaden/downloaden van bestanden](#device-portal-file-uploaddownload-times-out)
- [Blauw scherm na uitschrijving van Insider Preview op een apparaat dat is geflitst met een Insider-build](#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)
- [OneDrive uploadt afbeeldingen niet automatisch](#onedrive-doesnt-automatically-upload-pictures)

**Algemeen**
- [HoloLens reageert niet of start niet](#hololens-is-unresponsive-or-wont-start)
- [Fout : Weinig schijfruimte](#low-disk-space-error)
- [Kalibrering mislukt](#calibration-fails)
- [Kan niet aanmelden omdat mijn HoloLens eerder is ingesteld voor iemand anders](#cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else)
- [Unity werkt niet](#unity-isnt-working)
- [Windows Apparaatportal werkt niet goed](#windows-device-portal-isnt-working-correctly)
- [De HoloLens Emulator werkt niet](#the-hololens-emulator-isnt-working)

**Invoer**
- [Spraakopdrachten werken niet](#voice-commands-arent-working)
- [Handinvoer werkt niet](#hand-input-isnt-working)

**Connectiviteit**
- [Kan geen verbinding maken met Wi-Fi](#cant-connect-to-wi-fi)

**Externe apparaten** 
- [Bluetooth-apparaten worden niet gekoppeld](#bluetooth-devices-arent-pairing)
- [USB-C-microfoon werkt niet](#usb-c-microphone-isnt-working)
- [Apparaten die worden vermeld als beschikbaar in Instellingen werken niet](#devices-listed-as-available-in-settings-dont-work)

## <a name="remote-assist-video-freezes-after-20-minutes"></a>Remote Assist video na 20 minuten vast

> [!NOTE]
> Vanwege de ernst van dit bekende probleem is de beschikbaarheid van Windows Holographic, versie 21H1, momenteel onderbroken. Als u uw apparaten nog steeds wilt bijwerken naar 21h1, raadpleegt u de instructies in onze releaseop opmerkingen [boven aan de pagina.](hololens-release-notes.md)

In de nieuwste versie van [Windows Holographic, versie 21H1,](hololens-release-notes.md#windows-holographic-version-21h1)hebben sommige gebruikers van Remote Assist te maken gehad met video's die gedurende meer dan 20 minuten vastvijfden tijdens oproepen. Dit is een **bekend probleem.**

### <a name="workarounds"></a>Tijdelijke oplossingen

#### <a name="restart-in-between-calls"></a>Opnieuw opstarten tussen aanroepen

Als uw aanroepen langer duren dan 20 minuten en u dit probleem ondervindt, kunt u uw apparaat opnieuw opstarten. Als u het apparaat opnieuw opstart Remote Assist aanroepen, wordt uw apparaat vernieuwd en weer in een goede staat gezet.

Als u een apparaat snel opnieuw wilt opstarten in Windows Holographic, opent u versie [21H1](hololens-release-notes.md#windows-holographic-version-21h1) het menu Start en selecteert u het gebruikerspictogram. Selecteer vervolgens **Opnieuw opstarten.**

#### <a name="revert-to-an-older-build"></a>Terugkeren naar een oudere build

Sommige klanten hebben ontdekt dat ze dit probleem niet meer ervaren wanneer ze terugkeren naar een eerdere versie van het besturingssysteem. Als u hebt ontdekt dat dit probleem zich voor uw apparaten voordeed, probeert u deze stappen:


Oplossingen:

- Indien geschikt voor uw bedrijf, wordt automatisch uploaden van camera's ondersteund op Microsoft-accounts van consumenten. U kunt zich naast uw werk- Microsoft-account schoolaccount aanmelden bij uw account (de OneDrive-app ondersteunt dubbele aanmelding). Vanuit uw Microsoft-account in OneDrive kunt u automatisch uploaden van camera's op de achtergrond inschakelen.

- Als u een consumentenaccount niet veilig kunt Microsoft-account om uw foto's automatisch te uploaden, kunt u foto's handmatig uploaden naar uw werk- of schoolaccount vanuit de OneDrive-app. Zorg ervoor dat u bent aangemeld bij uw werk- of schoolaccount in de OneDrive-app om dit te doen. Selecteer de **+** knop en kies **Uploaden.** Zoek de foto's of video's die u wilt uploaden door te navigeren naar **Afbeeldingen > Camera Roll**. Selecteer de foto's of video's die u wilt uploaden en selecteer vervolgens de **knop** Openen.


1. [Download de build voor Windows Holographic, versie 20H2 – update van mei 2021](https://aka.ms/hololens2download/10.0.19041.1146)
1. Volg de instructies [om terug te keren naar een eerdere versie van het besturingssysteem](hololens-update-hololens.md#go-back-to-a-previous-version)
1. [Besturingssysteemupdates op het apparaat](hololens-updates.md#pause-updates-via-device) handmatig onderbreken of voor veel apparaten wordt [uitstel via MDM gebruikt.](hololens-updates.md#configure-an-update-deferral-policy)

[Terug naar lijst](#list)

## <a name="auto-login-asks-for-log-in"></a>Auto-login vraagt om aanmelden

Een HoloLens 2 kan worden geconfigureerd om automatisch aan te melden **via** Instellingen  ->  **Accounts**  ->  **Aanmeldingsopties** ->  en onder Vereist de waarde instellen op **Nooit.** Sommige gebruikers moeten zich mogelijk opnieuw aanmelden bij het apparaat wanneer ze een apparaat bijwerken met een aanzienlijk grote update, zoals een functie-update. Dit is een **bekend probleem.**

Voorbeeld van wanneer dit kan gebeuren:

- Een apparaat bijwerken van Windows Holographic, versie 2004 (build 19041.xxxx) naar Windows Holographic, versie 21H1 (build 20346.xxxx)
- Een apparaat bijwerken voor een grote update op dezelfde grote build, bijvoorbeeld Windows Holographic, versie 2004 naar Windows Holographic, versie 20H2
- Een apparaat bijwerken van een fabrieksafbeelding naar de nieuwste afbeelding

Dit mag niet gebeuren tijdens:

- Apparaten met een maandelijkse onderhoudsupdate

Methoden om te werken:

- Aanmeldingsmethoden zoals pincode, wachtwoord, iris, webverificatie of FIDO2-sleutels.
- Als de pincode van het apparaat niet kan worden onthouden en andere verificatiemethoden niet beschikbaar zijn, kan een gebruiker de modus [voor handmatige reflashing gebruiken.](hololens-recovery.md#manual-procedure)

[Terug naar lijst](#list)

## <a name="microsoft-edge-fails-to-launch"></a>Microsoft Edge kan niet worden starten

> [!NOTE]
> Dit probleem is oorspronkelijk gemaakt met de verzendversie van Microsoft Edge in gedachten. Dit probleem kan worden opgelost in de [nieuwe Microsoft Edge](hololens-new-edge.md). Als dat niet het is, kunt u feedback geven.

Een aantal klanten heeft een probleem gerapporteerd waarbij Microsoft Edge kan worden gelanceerd. Voor deze klanten blijft het probleem bestaan via opnieuw opstarten en wordt het niet opgelost met Windows- of toepassingsupdates. Als u dit probleem ondervindt en u hebt bevestigd dat [Windows up-to-date is,](hololens-updates.md#manually-check-for-updates)kunt u een fout in de [Feedback-hub-app](hololens-feedback.md) indienen met de volgende categorie en subcategorie: Installeren en bijwerken van > Downloaden, installeren en configureren Windows Update.

Er zijn geen tijdelijke oplossingen bekend, omdat we tot nu toe de hoofdoorzaak van het probleem niet hebben kunnen vinden. Het indienen van een bug via Feedback-hub helpt ons onderzoek. Dit is een **bekend probleem.**

[Terug naar lijst](#list)

## <a name="keyboard-doesnt-switch-to-special-characters"></a>Toetsenbord schakelt niet over naar speciale tekens

Er is een probleem tijdens OOBE, waarbij wanneer de gebruiker een werk- of schoolaccount heeft gekozen en zijn of haar wachtwoord invoeren, wordt geprobeerd om over te schakelen naar de speciale tekens op het toetsenbord door op de knop &123 te tikken, niet gewijzigd in speciale tekens. Dit is een **bekend probleem.**

Work-arounds:
-   Sluit het toetsenbord en open het opnieuw door op het tekstveld te tikken.
-   Voer ten onrechte uw wachtwoord in. Wanneer het toetsenbord de volgende keer opnieuw wordt gelanceerd, werkt het naar verwachting.
- Webverificatie, sluit het toetsenbord en selecteer **Aanmelden vanaf een ander apparaat.**
-   Als een gebruiker alleen getallen intoetst en deze in de wacht houdt om een uit uitgebreid menu te openen.
-   Met behulp van een USB-toetsenbord.

Dit heeft geen invloed op:
- Gebruikers die ervoor kiezen om een persoonlijk account te gebruiken.

[Terug naar lijst](#list)


## <a name="downloading-locked-files-doesnt-error"></a>Er wordt geen fout opgetreden bij het downloaden van vergrendelde bestanden
> ! OPMERKING Dit is een **bekend probleem dat** is opgelost in Windows Insider build, versie 20348.1403.


In eerdere builds van Windows Holographic, bij het downloaden van een vergrendeld bestand, zou het resultaat een HTTP-foutpagina zijn. In windows Holographic, versie 21H1-update, bij het downloaden van een vergrendeld bestand, gebeurt er niets. Het bestand wordt niet gedownload en er is geen fout. 

[Terug naar lijst](#list)

## <a name="device-portal-file-uploaddownload-times-out"></a>Apparaatportal-out voor uploaden/downloaden van bestanden
> ! OPMERKING Dit is een **bekend probleem dat** is opgelost in Windows Insider build, versie 20348.1403. Als u de SSL-verbinding eerder hebt uitgeschakeld als onderdeel van de tijdelijke oplossing, raden we u ten zeerste aan deze opnieuw in te stellen.


Sommige klanten hebben ontdekt dat de bewerking vast kan hangen wanneer ze bestanden proberen te uploaden of te downloaden en er vervolgens een time-out is of dat deze bewerking nooit is voltooid. Dit staat los van het bekende probleem['bestand vergrendeld'.](#downloading-locked-files-doesnt-error) Dit is van invloed op Windows Holographic, versies 2004, 20H2 en 21H1 in-market builds. Het probleem is veroorzaakt door een fout in de Apparaatportal van bepaalde aanvragen en wordt het meest consistent getroffen bij het gebruik van https. Dit is de standaardinstelling. 

### <a name="workaround"></a>Tijdelijke oplossing

Deze tijdelijke oplossing, die ook van toepassing is op Wi-Fi en UsbNcm, is om de optie 'vereist' onder 'SSL-verbinding' uit te schakelen. Ga om dit te doen naar Apparaatportal, **Systeem** en selecteer de **pagina Voorkeuren.** Zoek in **de sectie Apparaatbeveiliging** de **optie SSL-verbinding** en schakel vereist **uit.**

De gebruiker moet vervolgens naar http:// gaan, niet https:// (IP-adres) en functies zoals het uploaden en downloaden van bestanden werken.

[Terug naar lijst](#list)

## <a name="blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build"></a>Blauw scherm na uitschrijving van Insider Preview op een apparaat dat is geflitst met een Insider-build

Dit is een probleem dat van invloed is op gebruikers die een Insider-preview-build hebben gemaakt, hun HoloLens 2 hebben geslashed met een nieuwe insider preview-build en vervolgens zijn uitgeschreven bij het Insider-programma. Dit is een **bekend probleem.**

Dit heeft geen invloed op:
- Gebruikers die niet zijn ingeschreven bij Windows Insider 
- Insiders:
    - Als een apparaat is ingeschreven sinds Insider-builds versie 18362.x waren
    - Als er een Insider-build uit 19041.x is ondertekend en ingeschreven blijft in het Insider-programma

Work-around: 
- Vermijd het probleem 
    - Flash een niet-insider-build. Een van de regelmatige maandelijkse updates.
    - Blijf op Insider Preview
- Reflash op het apparaat

    1. Plaats de [HoloLens 2 handmatig in](hololens-recovery.md) de flashmodus door volledig uit te schakelen terwijl u geen verbinding maakt. Tik vervolgens terwijl u volume omhoog houdt op de aan/uit-knop.
    
    1. Maak verbinding met de pc en open Advanced Recovery Companion.
    
    1. Flash de HoloLens 2 naar de standaard-build.

[Terug naar lijst](#list)

## <a name="onedrive-doesnt-automatically-upload-pictures"></a>OneDrive uploadt afbeeldingen niet automatisch

De OneDrive-app voor HoloLens biedt geen ondersteuning voor het automatisch uploaden van camera's voor werk- of schoolaccounts. Dit is een **bekend probleem.**

Oplossingen:

- Indien geschikt voor uw bedrijf, wordt automatisch uploaden van camera's ondersteund op Microsoft-accounts van consumenten. U kunt zich naast uw werk- Microsoft-account schoolaccount aanmelden bij uw account (de OneDrive-app ondersteunt dubbele aanmelding). Vanuit uw Microsoft-account in OneDrive kunt u automatisch uploaden van camera's op de achtergrond inschakelen.

- Als u een consumentenaccount niet veilig kunt Microsoft-account om uw foto's automatisch te uploaden, kunt u foto's handmatig uploaden naar uw werk- of schoolaccount vanuit de OneDrive-app. Zorg ervoor dat u bent aangemeld bij uw werk- of schoolaccount in de OneDrive-app om dit te doen. Selecteer de **+** knop en kies **Uploaden.** Zoek de foto's of video's die u wilt uploaden door te navigeren naar **Afbeeldingen > Camera Roll**. Selecteer de foto's of video's die u wilt uploaden en selecteer vervolgens de **knop** Openen.

[Terug naar lijst](#list)

## <a name="hololens-is-unresponsive-or-wont-start"></a>HoloLens reageert niet of start niet

Als uw HoloLens niet start:

- Als de LED's naast de aan/uit-knop niet licht worden of slechts één LED kort knippert, moet u uw [HoloLens mogelijk laden.](hololens2-charging.md#charging-the-device)
- Als de LED's worden weergegeven wanneer u op de aan/uit-knop drukt, maar er niets wordt weergegeven, moet u het apparaat hard [opnieuw instellen.](hololens-recovery.md#hard-reset-procedure)

Als uw HoloLens bevroren of niet meer reageert:

- Schakel uw HoloLens uit door op de aan/uit-knop te drukken totdat alle vijf de LED's zichzelf uitschakelen of 15 seconden lang als de LED's niet reageren. Als u uw HoloLens wilt starten, drukt u opnieuw op de aan/uit-knop.

Als deze stappen niet werken, [](hololens-recovery.md) kunt u proberen uw HoloLens 2 of [HoloLens-apparaat (1e generatie) te herstellen.](hololens1-recovery.md)

[Terug naar lijst](#list)

## <a name="low-disk-space-error"></a>Fout : Weinig schijfruimte

U moet wat opslagruimte vrij maken door een of meer van de volgende stappen uit te gaan:

- Verwijder enkele niet-gebruikte ruimten. Ga naar **Instellingen**  >  **Systeemruimten,** selecteer een spatie die u niet meer nodig hebt  >  en selecteer **vervolgens Verwijderen.**
- Verwijder enkele hologrammen die u hebt geplaatst.
- Verwijder enkele afbeeldingen en video's uit de app Foto's.
- Verwijder enkele apps van uw HoloLens. Tik in **Alle apps** lijst op de app die u wilt verwijderen en houd deze in de wacht. Selecteer **vervolgens Verwijderen.**

[Terug naar lijst](#list)

## <a name="calibration-fails"></a>Kalibratie mislukt

Kalibratie zou voor de meeste mensen moeten werken, maar er zijn gevallen waarin de kalibratie mislukt.
  
Enkele mogelijke redenen voor kalibratiefout zijn:

- Afgeleid raken en de kalibratiedoelen niet volgen
- Vervuilde of be scratchde visor of apparaat visor niet goed geplaatst
- Vervuilde of be scratched bril
- Bepaalde soorten contactlenzen en bril (gekleurde contactlenzen, sommige metrische contactlenzen, IR-blokkerende bril, een bril met hoge bril, zonnebrillen of iets dergelijks)
- Meer uitgesproken haaruitbreidingen en een aantal eyelash-extensies
- Frames met haar of een dicht bril als ze blokkeren dat het apparaat uw ogen kan zien
- Bepaalde ogen, oogomstandigheden of oogoperaties, zoals smalle ogen, lange oogslashen, amblyopie, nystagmus, sommige gevallen van LASIK of andere oogpieken

Als kalibratie mislukt, probeert u het volgende:

- De visor van uw apparaat opsporing
- Uw bril ops cleaning
- De visor van uw apparaat zo dicht mogelijk bij uw ogen pushen
- Objecten in uw visor uit de weg verplaatsen (zoals haar)
- Een licht in uw ruimte in- of uitschakelen

Als u alle richtlijnen hebt gevolgd en kalibratie nog steeds mislukt, kunt u de kalibratieprompt uitschakelen in Instellingen. Laat het ons ook weten door feedback in te dienen [Feedback-hub.](hololens-feedback.md)

Zie ook gerelateerde informatie voor het oplossen [van problemen met de kleur of helderheid van afbeeldingen.](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)

Het instellen van IPD is niet van toepassing op HoloLens 2, omdat oogposities worden berekend door het systeem. 

[Terug naar lijst](#list)

## <a name="cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else"></a>Kan niet aanmelden omdat mijn HoloLens eerder is ingesteld voor iemand anders

U kunt [het apparaat in de **flashmodus zetten en** Advanced Recovery Companion](hololens-recovery.md#clean-reflash-the-device) gebruiken om het apparaat te herstellen.

[Terug naar lijst](#list)


## <a name="unity-isnt-working"></a>Unity werkt niet

- Zie [Install the tools](/windows/mixed-reality/install-the-tools) for the most-to-date version of Unity recommended for HoloLens development (De hulpprogramma's installeren voor de meest recente versie van Unity die wordt aanbevolen voor HoloLens-ontwikkeling).
- Bekende problemen met de Unity HoloLens Technical Preview worden beschreven in de [HoloLens Unity-forums.](https://forum.unity3d.com/threads/known-issues.394627/)

[Terug naar lijst](#list)

## <a name="windows-device-portal-isnt-working-correctly"></a>Windows Apparaatportal werkt niet goed

- De functie Live Preview in Mixed Reality capture kan enkele seconden latentie vertonen.

- Op de pagina Virtuele invoer zijn de besturingselementen Beweging en Scroll onder de sectie Virtuele gebaren niet functioneel. Het gebruik ervan heeft geen effect. Het virtuele toetsenbord op de virtuele invoerpagina werkt correct.

- Nadat u de ontwikkelaarsmodus hebt ingeschakeld in Instellingen, kan het enkele seconden duren voordat de schakelknop is ingeschakeld Apparaatportal ingeschakeld.

[Terug naar lijst](#list)

## <a name="emulator"></a>Emulator
### <a name="the-hololens-emulator-isnt-working"></a>De HoloLens Emulator werkt niet

Informatie over de HoloLens-emulator vindt u in onze documentatie voor ontwikkelaars.  Lees meer over het [oplossen van problemen met de HoloLens-emulator](/windows/mixed-reality/using-the-hololens-emulator#troubleshooting).


- Niet alle apps in de Microsoft Store zijn compatibel met de emulator. Zo kunnen Young Conker en Fragmenten niet worden afspelen op de emulator.
- U kunt de pc-webcam niet gebruiken in de emulator.
- De functie Live Preview van de Windows Apparaatportal werkt niet met de emulator. U kunt nog steeds Mixed Reality video's en afbeeldingen vastleggen.

[Terug naar lijst](#list)

## <a name="i-cannot-find-or-use-the-keyboard-to-type-in-the-hololens-2-emulator"></a>Ik kan het toetsenbord niet vinden of gebruiken om de emulator HoloLens 2 typen

*Binnenkort*

[Terug naar lijst](#list)

## <a name="voice-commands-arent-working"></a>Spraakopdrachten werken niet

Als Cortana niet reageert op uw spraakopdrachten, moet u ervoor zorgen dat Cortana is ingeschakeld. Selecteer in Alle apps de lijst **Cortana**  >  **Menu**  >  **Notebook**  >  **Settings om** wijzigingen aan te brengen. Zie Uw stem gebruiken met [HoloLens](hololens-cortana.md)voor meer informatie over wat u kunt zeggen.

Op HoloLens (1e generatie) kan ingebouwde spraakherkenning niet worden geconfigureerd. Deze is altijd ingeschakeld. Op HoloLens 2 kunt u kiezen of u zowel spraakherkenning als Cortana wilt in- of uitschakelen tijdens de installatie van het apparaat.

Als uw HoloLens 2 reageert op uw stem, moet u ervoor zorgen dat Spraakherkenning is ingeschakeld. Ga naar **Start**  >  **Settings**  >  **Privacy**  >  **Speech en** schakel **Spraakherkenning in.**

[Terug naar lijst](#list)

## <a name="hand-input-isnt-working"></a>Handinvoer werkt niet

Om ervoor te zorgen dat HoloLens uw handen kan zien, moet u ze in het bewegingsframe houden.  De Mixed Reality Start geeft feedback waarmee u kunt zien wanneer uw handen worden bijgespoord.  De feedback is anders voor verschillende versies van HoloLens:
- Op HoloLens (1e generatie) verandert de muisaanwijzer van een punt in een ring
- Op HoloLens 2 wordt een cursor met de muisaanwijzer weergegeven wanneer uw hand zich dicht bij een slate en een hand ray wordt weergegeven wanneer de slates verder weg zijn

Veel in immersieve apps volgen invoerpatronen die vergelijkbaar zijn met Mixed Reality Start.  Meer informatie over het gebruik van handinvoer [op HoloLens (eerste generatie)](hololens1-basic-usage.md#use-hololens-with-your-hands) en [HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame).

Als u een handje draagt, moet u er rekening mee houden dat sommige soorten handjes niet werken bij het bijhouden van de hand.  Een veelvoorkomende voorbeeld is zwarte rubberen pakken, die de neiging hebben om licht te nemen en niet worden opgepikt door de dieptecamera.  Als uw werk bestaat uit een blauwe of grijze kleur, raden we u aan om een lichtere kleur te gebruiken, zoals blauw of grijs.  Een ander voorbeeld zijn grote baggy gloves, die de vorm van uw hand doorgaans verborgen houden. We raden u aan om voor de beste resultaten zo goed mogelijk vorm te geven.

Als uw visor vingerafdrukken of smudges heeft, gebruikt u de microfiberschoonmaak die bij de HoloLens werd gebruikt om uw visorgemiddelde op te schonen.

[Terug naar lijst](#list)

## <a name="cant-connect-to-wi-fi"></a>Kan geen verbinding maken met Wi-Fi

Hier zijn enkele dingen die u kunt proberen als u uw HoloLens niet kunt verbinden met Wi-Fi netwerk:

- Zorg ervoor dat Wi-Fi is ingeschakeld. Als u dit wilt controleren, gebruikt u de beweging Starten en selecteert u vervolgens  >  **Instellingen Netwerk &amp; Internet**  >  **Wi-Fi.** Als Wi-Fi is, probeert u deze uit te schakelen en vervolgens weer aan.
- Ga dichter bij de router of het toegangspunt zitten.
- Start uw Wi-Fi router opnieuw en start [HoloLens opnieuw.](hololens-recovery.md) Probeer opnieuw verbinding te maken.
- Als geen van deze dingen werkt, controleert u of uw router de meest recente firmware gebruikt. U vindt deze informatie op de website van de fabrikant.

[Terug naar lijst](#list)
## <a name="bluetooth-devices-arent-pairing"></a>Bluetooth-apparaten worden niet gekoppeld

Als u problemen hebt met het [koppelen van een Bluetooth-apparaat,](hololens-connect-devices.md)probeert u het volgende:

- Ga naar  >  **InstellingenApparaten** en zorg ervoor dat Bluetooth is ingeschakeld. Als dat het zo is, kunt u deze uitschakelen en weer in- en uitschakelen.
- Zorg ervoor dat uw Bluetooth-apparaat volledig is geladen of nieuwe accu's heeft.
- Als u nog steeds geen verbinding kunt maken, start [u de HoloLens opnieuw](hololens-recovery.md)op.

[Terug naar lijst](#list)

## <a name="usb-c-microphone-isnt-working"></a>USB-C-microfoon werkt niet
Let erop dat sommige USB-C-microfoons zich onjuist melden als zowel een microfoon *als* een spreker. Dit is een probleem met de microfoon en niet met HoloLens. Wanneer u een van deze microfoons op HoloLens aangesloten, gaat het geluid mogelijk verloren. Gelukkig is er een eenvoudige oplossing.  

Stel **in**  ->    ->  **Systeemgeluid van** instellingen expliciet de ingebouwde sprekers **(Analog Feature Audio Driver)** in als **het standaardapparaat.** HoloLens moet deze instelling onthouden, zelfs als de microfoon wordt verwijderd en later opnieuw wordt verbonden.

![Problemen met USB-C-microfoons oplossen](images/usbc-mic-4.png)

## <a name="devices-listed-as-available-in-settings-dont-work"></a>Apparaten die worden vermeld als beschikbaar in Instellingen werken niet

HoloLens (eerste generatie) biedt geen ondersteuning voor Bluetooth-audioprofielen. Bluetooth-audioapparaten, zoals sprekers en headsets, worden mogelijk als beschikbaar weergegeven in HoloLens-instellingen, maar worden niet ondersteund.

HoloLens 2 ondersteunt het Bluetooth A2DP-audioprofiel voor stereo afspelen. Het Bluetooth Hands Free-profiel waarmee microfoonopname van een Bluetooth-randapparaat kan worden gemaakt, wordt niet ondersteund op HoloLens 2.

Als u problemen hebt met het gebruik van een Bluetooth-apparaat, moet u ervoor zorgen dat het een ondersteund apparaat is. Ondersteunde apparaten zijn onder andere:

- Engelstalige QWERTY Bluetooth-toetsenborden (u kunt deze overal gebruiken waar u het holografische toetsenbord gebruikt).
- Bluetooth mice.
- De [HoloLens-klik op](hololens1-clicker.md).

U kunt andere Bluetooth- EN GATT-apparaten koppelen aan uw HoloLens. Mogelijk moet u echter bijbehorende companion-apps installeren vanuit Microsoft Store om de apparaten daadwerkelijk te kunnen gebruiken.

[Terug naar lijst](#list)
