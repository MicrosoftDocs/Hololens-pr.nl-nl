---
title: Bekende problemen voor HoloLens
description: Blijf op de hoogte van onze lijst met bekende problemen en tijdelijke oplossingen die van invloed kunnen zijn op HoloLens-klanten en -ontwikkelaars die Unity en de Windows Apparaatportal.
keywords: probleem oplossen, bekend probleem, help
author: mattzmsft
ms.author: mazeller
ms.date: 11/30/2020
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
HoloLens and holograms: Frequently asked questions
manager: jarrettr
ms.prod: hololens
appliesto:
- HoloLens (1st Gen)
- HoloLens 2
ms.openlocfilehash: bc1d399a07a6a0622c953178cad7be1b8a018fdb
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/25/2021
ms.locfileid: "111377886"
---
# <a name="known-issues-for-hololens"></a>Bekende problemen voor HoloLens

Hier is de huidige lijst met bekende problemen voor HoloLens-apparaten. Controleer hier eerst of u vreemd gedrag ziet. Deze lijst wordt bijgewerkt wanneer nieuwe problemen worden ontdekt of gerapporteerd, of wanneer problemen worden opgelost in toekomstige HoloLens-software-updates.

>[!NOTE]
> - Als u een probleem ontdekt dat niet blokkeert, meldt u dit op uw HoloLens-apparaat via [Feedback-hub](hololens-feedback.md).
> - Als het probleem u blokkeert, dient u niet alleen feedback in, maar kunt u [ook een ondersteuningsaanvraag indienen.](https://aka.ms/hlsupport)

- [Bekende problemen voor alle HoloLens-generaties](#known-issues-for-all-hololens-generations)
- [Bekende problemen voor HoloLens 2 apparaten](#known-issues-for-hololens-2-devices)
- [Bekende problemen voor HoloLens (1st Gen)](#known-issues-for-hololens-1st-gen)
- [Bekende problemen voor HoloLens-emulator](#known-issues-for-hololens-emulator)

## <a name="known-issues-for-all-hololens-generations"></a>Bekende problemen voor alle HoloLens-generaties

### <a name="unity"></a>Unity

- Zie [Install the tools](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) for the most-to-date version of Unity recommended for HoloLens development (De hulpprogramma's installeren voor de meest recente versie van Unity die wordt aanbevolen voor HoloLens-ontwikkeling).
- Bekende problemen met de Unity HoloLens Technical Preview worden beschreven in de [HoloLens Unity-forums.](https://forum.unity3d.com/threads/known-issues.394627/)

### <a name="windows-device-portal"></a>Windows Apparaatportal

- De functie Live Preview in Mixed Reality capture kan enkele seconden latentie vertonen.

- Op de pagina Virtuele invoer zijn de besturingselementen Beweging en Scroll onder de sectie Virtuele gebaren niet functioneel. Het gebruik ervan heeft geen effect. Het virtuele toetsenbord op de virtuele invoerpagina werkt correct.

- Nadat u de ontwikkelaarsmodus hebt ingeschakeld in Instellingen, kan het enkele seconden duren voordat de schakelknop is ingeschakeld Apparaatportal ingeschakeld.

### <a name="onedrive-camera-upload"></a>OneDrive-camera uploaden

De OneDrive-app voor HoloLens biedt geen ondersteuning voor het automatisch uploaden van camera's voor werk- of schoolaccounts.

Oplossingen:

- Indien geschikt voor uw bedrijf, wordt automatisch uploaden van camera's ondersteund op Microsoft-accounts van consumenten. U kunt zich naast uw werk- Microsoft-account schoolaccount aanmelden bij uw account (de OneDrive-app ondersteunt dubbele aanmelding). Vanuit uw Microsoft-account in OneDrive kunt u automatisch uploaden van camera's op de achtergrond inschakelen.

- Als u een consumentenaccount niet veilig kunt Microsoft-account om uw foto's automatisch te uploaden, kunt u foto's handmatig uploaden naar uw werk- of schoolaccount vanuit de OneDrive-app. Zorg ervoor dat u bent aangemeld bij uw werk- of schoolaccount in de OneDrive-app om dit te doen. Selecteer de **+** knop en kies **Uploaden.** Zoek de foto's of video's die u wilt uploaden door te navigeren naar **Afbeeldingen > Camera Roll**. Selecteer de foto's of video's die u wilt uploaden en selecteer vervolgens de **knop** Openen.

## <a name="known-issues-for-hololens-2-devices"></a>Bekende problemen voor HoloLens 2 apparaten

### <a name="device-using-auto-login-asks-for-log-in"></a>Apparaat met automatische aanmelding vraagt om aanmelden

Een HoloLens 2 kan worden geconfigureerd om automatisch aan te melden **via** Instellingen  ->  **Accounts**  ->  **Aanmeldingsopties** ->  en onder Vereist de waarde instellen op **Nooit.** Sommige gebruikers moeten zich mogelijk opnieuw aanmelden bij het apparaat wanneer ze een apparaat bijwerken met een aanzienlijk grote update, zoals een functie-update.

Voorbeeld van wanneer dit kan gebeuren:

- Een apparaat bijwerken van Windows Holographic, versie 2004 (build 19041.xxxx) naar Windows Holographic, versie 21H1 (build 20346.xxxx)
- Een apparaat bijwerken voor een grote update op dezelfde grote build, bijvoorbeeld Windows Holographic, versie 2004 naar Windows Holographic, versie 20H2
- Een apparaat bijwerken van een fabrieksafbeelding naar de nieuwste afbeelding

Dit mag niet gebeuren tijdens:

- Apparaten met een maandelijkse onderhoudsupdate

Methoden om te werken:

- Aanmeldingsmethoden zoals pincode, wachtwoord, iris, webverificatie of FIDO2-sleutels.
- Als de pincode van het apparaat niet kan worden onthouden en andere verificatiemethoden niet beschikbaar zijn, kan een gebruiker de modus [voor handmatige reflashing gebruiken.](hololens-recovery.md#manual-procedure)

### <a name="microsoft-edge-fails-to-launch"></a>Microsoft Edge kan niet worden starten

> [!NOTE]
> Dit probleem is oorspronkelijk gemaakt met de verzendversie van Microsoft Edge in gedachten. Dit probleem kan worden opgelost in de [nieuwe Microsoft Edge](hololens-new-edge.md). Als dat niet het is, kunt u feedback geven.

Een aantal klanten heeft een probleem gerapporteerd waarbij Microsoft Edge kan worden gelanceerd. Voor deze klanten blijft het probleem bestaan via opnieuw opstarten en wordt het niet opgelost met Windows- of toepassingsupdates. Als u dit probleem ondervindt en u hebt bevestigd dat [Windows up-to-date is,](hololens-updates.md#manually-check-for-updates)kunt u een fout in de [Feedback-hub-app](hololens-feedback.md) indienen met de volgende categorie en subcategorie: Installeren en bijwerken van > Downloaden, installeren en configureren Windows Update.

Er zijn geen tijdelijke oplossingen bekend, omdat we tot nu toe de hoofdoorzaak van het probleem niet hebben kunnen vinden. Het indienen van een bug via Feedback-hub helpt ons onderzoek.

### <a name="keyboard-does-not-switch-to-special-characters"></a>Toetsenbord schakelt niet over naar speciale tekens

Er is een probleem tijdens OOBE, waarbij wanneer de gebruiker een werk- of schoolaccount heeft gekozen en zijn of haar wachtwoord invoeren, wordt geprobeerd om over te schakelen naar de speciale tekens op het toetsenbord door op de knop &123 te tikken, niet gewijzigd in speciale tekens.

Work-arounds:
-   Sluit het toetsenbord en open het opnieuw door op het tekstveld te tikken.
-   Voer ten onrechte uw wachtwoord in. Wanneer het toetsenbord de volgende keer opnieuw wordt gelanceerd, werkt het naar verwachting.
- Webverificatie, sluit het toetsenbord en selecteer **Aanmelden vanaf een ander apparaat.**
-   Als een gebruiker alleen getallen intoetst en deze in de wacht houdt om een uit uitgebreid menu te openen.
-   Met behulp van een USB-toetsenbord.

Dit heeft geen invloed op:
- Gebruikers die ervoor kiezen om een persoonlijk account te gebruiken.

### <a name="blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-an-insider-build"></a>Het blauwe scherm wordt weergegeven nadat de registratie van insider-previews is uitgehaald op een apparaatslash met een Insider-build

Dit is een probleem dat van invloed is op gebruikers die een Insider-preview-build hebben gemaakt, hun HoloLens 2 hebben geslashed met een nieuwe insider preview-build en vervolgens zijn uitgeschreven bij het Insider-programma.

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

    1. Plaats de [HoloLens 2 handmatig in](https://review.docs.microsoft.com/hololens/hololens-recovery?branch=master#hololens-2) de flashmodus door volledig uit te schakelen terwijl u geen verbinding maakt. Tik vervolgens terwijl u volume omhoog houdt op de aan/uit-knop.
    
    1. Maak verbinding met de pc en open Advanced Recovery Companion.
    
    1. Flash de HoloLens 2 naar de standaard-build.

## <a name="known-issues-for-hololens-1st-gen"></a>Bekende problemen voor HoloLens (1st Gen)

### <a name="unable-to-connect-and-deploy-to-hololens-through-visual-studio"></a>Kan geen verbinding maken en implementeren op HoloLens via Visual Studio

> [!NOTE]
> Laatste update: 8-08 -17:11 - Visual Studio heeft VS 2019 versie 16.2 uitgebracht, met een oplossing voor dit probleem. We raden u aan om bij te werken naar deze nieuwste versie om te voorkomen dat deze fout zich voordeed.

Visual Studio VS 2019 versie 16.2 is uitgebracht, waaronder een oplossing voor dit probleem. We raden u aan om bij te werken naar deze nieuwste versie om te voorkomen dat deze fout zich voordeed.

Hoofdoorzaak van probleem: gebruikers die Visual Studio 2015 of vroege versies van Visual Studio 2017 hebben gebruikt voor het implementeren en opsporen van fouten in toepassingen op hun HoloLens en vervolgens de nieuwste versies van Visual Studio 2017 of Visual Studio 2019 met dezelfde HoloLens hebben gebruikt, worden beïnvloed. De nieuwere versies van Visual Studio een nieuwe versie van een onderdeel implementeren, maar bestanden van de oudere versie worden overgelaten op het apparaat, waardoor de nieuwere versie mislukt.  Dit veroorzaakt het volgende foutbericht: DEP0100: Zorg ervoor dat de ontwikkelaarsmodus voor het doelapparaat is ingeschakeld. Kan geen ontwikkelaarslicentie verkrijgen op \<ip\> vanwege fout 80004005.

#### <a name="workaround"></a>Tijdelijke oplossing

Ons team werkt momenteel aan een oplossing. In de tussentijd kunt u de volgende stappen gebruiken om het probleem op te lossen en de implementatie en debugging te deblokkeren:  

1. Open Visual Studio.

1. Selecteer **Bestand** > **Nieuw** > **Project**.

1. Selecteer **Visual C#**  >  **Windows Desktop** Console App  >  **(.NET Framework)**.

1. Geef het project een naam (zoals HoloLensDeploymentFix) en zorg ervoor dat het Framework is ingesteld op ten minste .NET Framework 4.5 en selecteer **ok.**

1. Klik met de rechtermuisknop **op het** knooppunt Verwijzingen in Solution Explorer voeg  de volgende verwijzingen toe (selecteer de sectie Bladeren en selecteer **Bladeren**):

    ```console
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Deploy.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Connectivity.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\SirepInterop.dll
    ```

    > [!NOTE]
    > Als u 10.0.18362.0 niet hebt geïnstalleerd, gebruikt u de meest recente versie die u hebt. 

1. Klik met de rechtermuisknop op het project in Solution Explorer selecteer **Bestaand**  >  **item toevoegen.**

1. Blader naar C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86 en wijzig het filter in Alle bestanden **( \* . \* )**.

1. Selecteer zowel SirepClient.dll als SshClient.dll en Selecteer **Toevoegen.**

1. Zoek en selecteer beide bestanden in Solution Explorer (deze moeten onderaan de lijst met bestanden staan)  en wijzig Kopiëren naar uitvoermap **in** het venster Eigenschappen in **Altijd kopiëren.**

1. Voeg bovenaan het bestand het volgende toe aan de bestaande lijst met `using` -instructies:

    ```console
    using Microsoft.Tools.Deploy;
    using System.Net;
    ```

1. Voeg binnen `static void Main(...)` de volgende code toe:

    ```PowerShell
    RemoteDeployClient client = RemoteDeployClient.CreateRemoteDeployClient();
    client.Connect(new ConnectionOptions()
    {
        Credentials = new NetworkCredential("DevToolsUser", string.Empty),
        IPAddress = IPAddress.Parse(args[0])
    });
    client.RemoteDevice.DeleteFile(@"C:\Data\Users\DefaultAccount\AppData\Local\DevelopmentFiles\VSRemoteTools\x86\CoreCLR\mscorlib.ni.dll");
    ```

1. Selecteer **Bouwen** > **Oplossing bouwen**.

1. Open een opdrachtpromptvenster en cd naar de map die het gecompileerde .exe-bestand bevat (bijvoorbeeld C:\MyProjects\HoloLensDeploymentFix\bin\Debug).

1. Voer het uitvoerbare bestand uit en geef het IP-adres van het apparaat op als een opdrachtregelargument. (Als u verbinding hebt via USB, kunt u 127.0.0.1 gebruiken, anders gebruikt u het ip-adres van Wi-Fi apparaat.)  Bijvoorbeeld HoloLensDeploymentFix 127.0.0.1.

1. Nadat het hulpprogramma is afgesloten zonder berichten (dit duurt slechts enkele seconden), kunt u nu implementeren en fouten opsporen vanuit Visual Studio 2017 of hoger.  Verder gebruik van het hulpprogramma is niet nodig.

We zullen verdere updates leveren zodra deze beschikbaar komen.

### <a name="issues-launching-the-microsoft-store-and-apps-on-hololens"></a>Problemen met het starten Microsoft Store apps op HoloLens

> [!NOTE]
> Laatste update: 4/2 @ 10:00 uur - Probleem opgelost.

U kunt problemen ervaren bij het starten van de Microsoft Store apps op HoloLens. We hebben vastgesteld dat het probleem optreedt wanneer updates van achtergrond-apps een nieuwere versie van frameworkpakketten in specifieke reeksen implementeren terwijl een of meer van hun afhankelijke apps nog steeds worden uitgevoerd. In dit geval heeft een automatische app-update een nieuwe versie van het systeemeigen .NET Framework geleverd (versie 10.0.25531 tot 10.0.27413) waardoor de apps die worden uitgevoerd, niet correct zijn bijgewerkt voor alle apps die de vorige versie van het framework gebruiken.  De stroom voor frameworkupdates is als volgt:

1. Het nieuwe frameworkpakket wordt gedownload uit de Store en geïnstalleerd.

1. Alle apps het oudere framework worden bijgewerkt om de nieuwere versie te gebruiken.

Als stap 2 vóór voltooiing wordt onderbroken, kunnen apps waarvoor het nieuwere framework niet is geregistreerd, niet worden starten vanuit het menu Start.  We denken dat elke app op HoloLens door dit probleem kan worden beïnvloed.

Sommige gebruikers hebben gemeld dat het probleem voor hen wordt opgelost door apps te sluiten en andere apps te starten, zoals Feedback-hub, 3D-viewer of Foto's. Dit werkt echter niet 100% van de tijd.

De hoofdoorzaak is dat dit probleem niet de update zelf heeft veroorzaakt, maar een bug in het besturingssysteem die ertoe heeft geleid dat de systeemeigen .NET frameworkupdate onjuist is verwerkt. We zijn blij te kunnen aankondigen dat we een oplossing hebben geïdentificeerd en een update hebben uitgebracht (besturingssysteemversie 17763.380) met de oplossing.  

Ga als volgende te werk om te zien of uw apparaat de update kan gebruiken:

1. Ga naar de app Instellingen en open **Update & Security**.

1. Selecteer **Controleren op updates.**

1. Als update naar 17763.380 beschikbaar is, werkt u bij naar deze build om de oplossing voor de app-fout vast te stellen.

1. Bij het bijwerken naar deze versie van het besturingssysteem moeten de apps werken zoals verwacht.

Daarnaast hebben we, net als bij elke HoloLens OS-release, de FFU-afbeelding geplaatst in [het Microsoft Downloadcentrum.](https://aka.ms/hololensdownload/10.0.17763.380)

Als u de update niet wilt gebruiken, is er vanaf 3/29 een nieuwe versie van de Microsoft Store UWP-app uitgebracht. Nadat u de bijgewerkte versie van de Store hebt:

1. Open de Store en controleer of deze wordt geladen.
1. Gebruik de bloembewegingen om het menu te openen.
1. Probeer eerder verbroken apps te openen.
1. Als de app nog steeds niet kan worden gestart, tikt en houdt u het pictogram van de defecte app vast en selecteert u Verwijderen.
1. Installeer deze apps opnieuw vanuit de Store.

Als het apparaat nog steeds geen apps kan laden, kunt u een versie van systeemeigen .NET Framework en Runtime sideloaden via het downloadcentrum door de volgende stappen uit te voeren:

1. Download dit [ZIP-bestand](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) via het Microsoft Downloadcentrum. Als u het uit een bestand optelt, worden er twee bestanden geproduceerd.  Microsoft .NET.Native.Runtime.1.7.appx en Microsoft .NET.Native.Framework.1.7.appx.

1. Controleer of uw apparaat is ontgrendeld.  Als u dat nog niet eerder hebt gedaan, zie [dan Using the Windows Apparaatportal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) (De Windows Apparaatportal voor instructies.

1. Vervolgens wilt u naar de Windows Apparaatportal. Het wordt aanbevolen dit via USB te doen. Dit doet u door in uw http://127.0.0.1:10080 browser te typen.

1. Nadat u de Windows Apparaatportal, moet u de twee bestanden die u hebt gedownload aan de zijkant laden. Als u dit wilt doen, gaat u naar de linkerzijbalk totdat u bij de **sectie Apps** bent en selecteert u **Apps.**

1. Vervolgens ziet u een scherm dat vergelijkbaar is met het onderstaande.  Ga naar de sectie App  installeren en blader naar de plek waar u deze twee APPX-bestanden hebt uitgepakt. U kunt slechts één voor één doen, dus nadat u de eerste hebt geselecteerd, klikt u op 'Ga' onder de sectie Implementeren. Doe dit vervolgens voor het tweede APPX-bestand.

   ![Windows Apparaatportal app installeren Side-Loaded installeren](images/20190322-DevicePortal.png)
   
1. Op dit punt zijn we van mening dat uw toepassingen opnieuw moeten werken en dat u ook naar de Store kunt gaan.

1. In sommige gevallen moet de extra stap voor het starten van de app 3D-viewer de betreffende apps worden uitgevoerd. 

We waarderen uw geduld omdat we het proces hebben doorlopen om dit probleem op te lossen en we kijken ernaar uit om samen met onze community een succesvolle Mixed Reality creëren.

### <a name="device-update"></a>Apparaat bijwerken

- 30 seconden na een nieuwe update kan de shell één keer verdwijnen. Voer de bloembewegingen **uit** om uw sessie te hervatten.

### <a name="visual-studio"></a>Visual Studio

- Zie [De hulpprogramma's](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) installeren voor de meest recente versie van Visual Studio die wordt aanbevolen voor HoloLens-ontwikkeling.

- Wanneer u een app implementeert vanuit Visual Studio naar uw HoloLens, ziet u mogelijk de volgende fout: De aangevraagde bewerking kan niet worden uitgevoerd op een bestand met een door de gebruiker toegesneden **sectie geopend. (Uitzondering van HRESULT: 0x800704C8)**. Als dit gebeurt, probeert u het opnieuw en slaagt uw implementatie over het algemeen.

### <a name="api"></a>API

- Als de toepassing het [focuspunt](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) achter de gebruiker of de normale op camera.forward in stelt, worden hologrammen niet weergegeven in Vastleggen in mixed reality of video's. Totdat deze fout in Windows is opgelost, moeten toepassingen, als ze het [focuspunt](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) actief instellen, ervoor zorgen dat het vlak normaal is ingesteld tegenovergestelde camera-forward (bijvoorbeeld normal = -camera.forward).

### <a name="xbox-wireless-controller"></a>Xbox Wireless Controller

- Xbox Wireless Controller S moet worden bijgewerkt voordat deze kan worden gebruikt met HoloLens. Zorg ervoor dat u [up-to-date bent](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) voordat u uw controller gaat koppelen aan een HoloLens.

- Als u uw HoloLens opnieuw opstart terwijl de Xbox Wireless Controller is verbonden, maakt de controller niet automatisch opnieuw verbinding met HoloLens. Het lampje van de knop Gids knippert langzaam totdat de controller na 3 minuten wordt uitgeschakeld. Als u de controller onmiddellijk opnieuw wilt verbinden, schakelt u de controller uit door de knop Gids ingedrukt te houden totdat het licht wordt uitgeschakeld. Wanneer u de controller weer in bedrijf neemt, wordt er opnieuw verbinding gemaakt met HoloLens.

- Als uw HoloLens stand-by komt terwijl de Xbox Wireless Controller is verbonden, wordt de HoloLens door invoer op de controller ontwaald. U kunt dit voorkomen door uw controller uit te schakelen wanneer u klaar bent met het gebruik ervan.

## <a name="known-issues-for-hololens-emulator"></a>Bekende problemen voor HoloLens-emulator

- Niet alle apps in de Microsoft Store zijn compatibel met de emulator. Zo kunnen Young Conker en Fragmenten niet worden afspelen op de emulator.
- U kunt de pc-webcam niet gebruiken in de emulator.
- De functie Live Preview van de Windows Apparaatportal werkt niet met de emulator. U kunt nog steeds Mixed Reality video's en afbeeldingen vastleggen.
