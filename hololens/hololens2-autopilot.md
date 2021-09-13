---
title: Windows Autopilot voor HoloLens 2
description: Meer informatie over het instellen, configureren en oplossen van problemen met Autopilot op HoloLens 2 apparaten.
author: qianw211
ms.author: v-qianwen
ms.date: 9/8/2021
ms.prod: hololens
ms.topic: article
ms.custom:
- CI 116283
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: high
keywords: Automatische piloot
manager: sekerawa
ms.openlocfilehash: c71716778ebd536d3aecd2a34c9929c8b2f76d98
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/13/2021
ms.locfileid: "126035973"
---
# <a name="windows-autopilot-for-hololens-2"></a>Windows Autopilot voor HoloLens 2

## <a name="overview"></a>Overzicht

Als u op schaal wilt implementeren, raden we u aan om aan de slag te Windows Autopilot. Het wordt beschouwd als 'low touch' omdat het het instellen van HoloLens voor zowel IT- als eindgebruikers aanzienlijk vereenvoudigt. 

Op hoog niveau maakt een IT-beheerder doorgaans de configuraties die gereed zijn voor het bedrijf en registreert HoloLens 2 op MDM-portals. Wanneer HoloLens 2-apparaten opstarten met out-of-box experience (OOBE) en verbinding maken met internet, worden bedrijfsconfiguraties voor geregistreerde HoloLens 2-apparaten automatisch gedownload en toegepast om het apparaat bedrijfsklaar te maken zonder tussenkomst van de gebruiker.

Zie overzicht van autopilot-Windows voor [meer | Microsoft Docs](/mem/autopilot/windows-autopilot) artikel.

## <a name="supported-autopilot-scenario-on-hololens-2"></a>Ondersteund Autopilot-scenario op HoloLens 2

> [!NOTE]
> Autopilot-configuratie voor HoloLens in Microsoft Endpoint Manager wordt overstappen van **openbare preview** naar **algemene beschikbaarheid.** Alle tenants kunnen Autopilot instellen in het MEM-beheercentrum.

Vanaf Windows Holographic-versie 2004 biedt HoloLens 2 ondersteuning voor Windows Autopilot [Self-Deploying Mode](/mem/autopilot/self-deploying) met Microsoft Intune (MDM's van derden worden niet ondersteund). Deze configuratie vermindert de overhead voor voorraadbeheer, de kosten van praktijkinleiding voor het voorbereiden van apparaten en ondersteuningsgesprekken van werknemers tijdens de installatie. Meer informatie in de [Windows Autopilot-documentatie.](/mem/autopilot/windows-autopilot)

Net als bij Surface-apparaten wordt het aanbevolen dat klanten samenwerken met hun Microsoft [Cloud Solution Provider](https://partner.microsoft.com/cloud-solution-provider) (reseller of distributor) om apparaten te registreren bij de Autopilot-service via Partner Center.

Wanneer een gebruiker het zelf-implementerende Autopilot-proces start, voltooit Autopilot de volgende stappen:

1. Voeg het apparaat toe aan Azure Active Directory (Azure AD). Autopilot voor HoloLens geen ondersteuning voor Active Directory-join of Hybrid Azure AD Join.

1. Gebruik Azure AD om het apparaat in te schrijven bij Microsoft Endpoint Manager (of een andere MDM-service).

1. Download en pas op apparaten gerichte beleidsregels, certificaten, netwerkprofielen en toepassingen toe.

1. Het aanmeldingsscherm presenteren aan de gebruiker.

## <a name="configuring-autopilot-for-hololens-2"></a>Autopilot configureren voor HoloLens 2

Volg de onderstaande stappen om uw omgeving in te stellen:

1. [Bekijk de vereisten voor Windows Autopilot voor HoloLens 2.](#1-review-requirements-for-windows-autopilot-for-hololens-2)

1. [Automatische MDM-inschrijving inschakelen](#2-enable-automatic-mdm-enrollment)

1. (Alleen voor Intune) [Zorg ervoor dat MDM-inschrijving niet wordt geblokkeerd voor Windows apparaten.](/mem/intune/enrollment/enrollment-restrictions-set)

1. [Apparaten registreren in Windows Autopilot.](#4-register-devices-in-windows-autopilot)

1. [Maak een apparaatgroep.](#5-create-a-device-group)

1. [Maak een Autopilot-profiel en wijs het toe aan de apparaatgroep.](#6-create-autopilot-profile-and-assign-it-to-the-device-group)

1. [Maak een esp-configuratie (Enrollment Status Page) en wijs deze toe aan de apparaatgroep.](#7-create-enrollment-status-page-esp-configuration-and-assign-it-to-the-device-group)

1. [Controleer de profielstatus van de HoloLens apparaten.](#8-verify-the-profile-status-of-the-hololens-devices)

### <a name="1-review-requirements-for-windows-autopilot-for-hololens-2"></a>1. Controleer de vereisten voor Windows Autopilot voor HoloLens 2

#### <a name="review-the-following-sections-of-the-windows-autopilot-requirements-article"></a>Lees de volgende secties van het artikel Windows Autopilot-vereisten:

- [Netwerkvereisten](/mem/autopilot/networking-requirements)  
- [Licentievereisten](/mem/autopilot/licensing-requirements)  
- [Configuratievereisten](/mem/autopilot/configuration-requirements)

**Lees de sectie [Vereisten](/windows/deployment/windows-autopilot/self-deploying#requirements)van het artikel Windows autopilot-Self-Deploying modus.** Uw omgeving moet voldoen aan deze vereisten en de standaardvereisten Windows Autopilot. U hoeft de secties 'Stap voor stap' en 'Validatie' van het artikel niet door te nemen. De procedures verder in dit artikel bieden bijbehorende stappen die specifiek zijn voor HoloLens.

Zorg ervoor dat de apparaten niet al lid zijn van Azure AD en niet zijn ingeschreven bij Intune (of een ander MDM-systeem). Het zelf-implementerende Autopilot-proces voltooit deze stappen. Als u er zeker van wilt zijn dat  alle apparaatgerelateerde informatie wordt opgeschoond, controleert u de pagina's Apparaten in zowel Azure AD- als Intune-portals. Convert all targeted devices to Autopilot'-functie wordt momenteel niet ondersteund HoloLens doelapparaten. 

#### <a name="review-hololens-os-requirements"></a>Bekijk HoloLens vereisten voor het besturingssysteem:

Als u de buildversie op uw apparaat of reflash naar het nieuwste besturingssysteem wilt bevestigen, gebruikt u [de Arc (Advanced Recovery Companion)](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=2&activetab=pivot:overviewtab) en onze instructies voor [de reflash van het apparaat.](hololens-recovery.md) Op apparaten die tot eind september 2020 worden geleverd, Windows Holographic-versie 1903 vooraf geïnstalleerd. Neem contact op met uw wederverkoper om ervoor te zorgen dat autopilot-apparaten naar u worden verzonden.

 Minimumversie van het besturingssysteem | Ondersteunde functie | Opmerkingen 
 ------ | ------ | ------  
 [Windows Holographic versie 2004](hololens-release-notes.md#windows-holographic-version-2004) (build 19041.1103) of hoger | 1. Zelf-implementerend scenario van Autopilot op HoloLens 2. | Het downloaden van Autopilot-profielen wordt alleen ondersteund via Ethernet. Zorg ervoor HoloLens is verbonden met ethernet met behulp van een USB-C-naar-Ethernet-adapter **voordat u deze instroomt.**  Als u van plan bent een Autopilot-implementatie uit te voeren voor veel HoloLens apparaten, raden we u aan de infrastructuur van de adapter te plannen. USB-hubs worden niet aanbevolen, omdat er vaak stuurprogramma's van derden moeten worden geïnstalleerd die niet worden ondersteund op HoloLens.
 [Windows Holographic versie 20H2](hololens-release-notes.md#windows-holographic-version-20h2) (build 19041.1128) of hoger | 1. Autopilot-profiel downloaden via Wi-Fi. <br> 2. [Tenantvergrendeling CSP en Autopilot om](#tenant-lockdown-csp-and-autopilot) apparaten te vergrendelen met een door Autopilot opgegeven tenant. | U kunt desgewenst nog steeds ethernetadapters gebruiken. Voor apparaten die zijn verbonden via Wi-Fi, moet de gebruiker alleen het volgende doen: <ul> <li> Ga door de scène van de samenmingbird. </li> <li> Kies de taal en de taal. </li> <li> Voer oog-kalibratie uit. </li> <li> Verbinding maken met het gewenste Wifi-netwerk. </li> </ul>

### <a name="2-enable-automatic-mdm-enrollment"></a>2. Automatische MDM-inschrijving inschakelen:

Als u wilt dat Autopilot slaagt, moet u Automatische MDM-inschrijving inschakelen in uw Azure Portal. Hierdoor kan het apparaat zonder gebruiker worden ingeschreven.

Bekijk de volgende korte handleiding voor het inschakelen van [automatische MDM-inschrijving](/windows/client-management/mdm/azure-ad-and-microsoft-intune-automatic-mdm-enrollment-in-the-new-portal) of de [snelstartgids](/mem/intune/enrollment/quickstart-setup-auto-enrollment) voor automatische inschrijving voor nog meer informatie over het instellen.

### <a name="3-ensure-that-mdm-enrollment-isnt-blocked-for-windows-devices"></a>3. Zorg ervoor dat MDM-inschrijving niet wordt geblokkeerd voor Windows apparaten.

Als u wilt dat Autopilot slaagt, moet u ervoor zorgen dat uw HoloLens kunnen worden ingeschreven. Aangezien HoloLens wordt beschouwd als een Windows apparaat, hoeven er geen inschrijvingsbeperkingen te zijn die uw implementatie kunnen blokkeren. [Bekijk deze lijst met beperkingen](/mem/intune/enrollment/enrollment-restrictions-set) en zorg ervoor dat u uw apparaten kunt registreren.

### <a name="4-register-devices-in-windows-autopilot"></a>4. Apparaten registreren in Windows Autopilot

Uw apparaten moeten worden geregistreerd in Windows Autopilot voordat u deze voor de eerste keer instelt. 

Er zijn drie primaire manieren om apparaten HoloLens registreren:

 - **Resellers kunnen apparaten registreren in de Partner Center wanneer u een order plaatsen.**

   > [!NOTE]  
   > Dit is het aanbevolen pad voor het toevoegen van apparaten aan de Autopilot-service. [Meer informatie](/mem/autopilot/partner-registration).  

 - **U kunt [rechtstreeks een ondersteuningsaanvraag](hololens2-autopilot-registration-support.md) indienen bij Microsoft.**
 - **Haal de hardware-hash (ook wel bekend als de hardware-id)** op en registreer het apparaat handmatig in het MEM-beheercentrum.

#### <a name="obtain-hardware-hash"></a>Hardware-hash verkrijgen

U kunt de hardwarehash ophalen van het apparaat. Het apparaat registreert de hardware-hash in een CSV-bestand tijdens het OOBE-proces, of later wanneer een apparaateigenaar het verzamelen van diagnostische logboeken start (beschreven in de volgende procedure). Normaal gesproken is de eigenaar van het apparaat de eerste gebruiker die zich bij het apparaat heeft aanmelden.

> [!WARNING]
> Als u in builds vóór 20H2 OOBE hebt doorgegaan en de telemetrie is ingesteld op Vereist, kunt u de hardware-hash voor Autopilot niet verzamelen via deze methode. Als u uw hardwarehash via deze methode wilt verzamelen, stelt u de telemetrieoptie in op Volledig via de Instellingen-app en selecteert u Privacy -> Diagnostics.

1. Start het HoloLens 2 apparaat.

1. Druk op het apparaat  tegelijkertijd op de knoppen In-/uit- en volume-omlaag en laat ze vervolgens los.  Het apparaat verzamelt diagnostische logboeken en de hardware-hash en slaat deze op in een set .zip bestanden.

1. Voor volledige details en een instructievideo voor het uitvoeren van deze lees lezen over [Offline diagnostics](hololens-diagnostic-logs.md#offline-diagnostics).

1. Gebruik een USB-C-kabel om het apparaat te verbinden met een computer.

1. Open Verkenner op de computer. Open **Deze pc interne Storage \\ \<*HoloLens device name*> \\ \\ documenten** en zoek het AutopilotDiagnostics.zip bestand.  

> [!NOTE]  
> Het .zip is mogelijk niet onmiddellijk beschikbaar. Als het bestand nog niet gereed is, ziet u mogelijk het bestand HoloLensDiagnostics.temp in de map Documents. Vernieuw het venster om de lijst met bestanden bij te werken.
    
1. Extraheren van de inhoud van AutopilotDiagnostics.zip bestand.

1. Zoek in de uitgepakte bestanden het CSV-bestand met het voorvoegsel 'DeviceHash' van de bestandsnaam. Kopieer dat bestand naar een station op de computer waar u het later kunt openen.  

> [!IMPORTANT]  
> De gegevens in het CSV-bestand moeten de volgende header- en regelindeling gebruiken:
> ```
> Device Serial Number,Windows Product ID,Hardware Hash,Group Tag,Assigned User <serialNumber>,<ProductID>,<hardwareHash>,<optionalGroupTag>,<optionalAssignedUser>
>```

#### <a name="register-device-through-mem"></a>Apparaat registreren via MEM

1. Selecteer [Microsoft Endpoint Manager](https://endpoint.microsoft.com)het beheercentrum de optie Apparaten  >    >  **Windows Windows inschrijving** en selecteer   >   vervolgens Apparaten importeren onder Windows Autopilot Deployment Programma .

1. Selecteer **onder Windows Autopilot-apparaten** toevoegen het CSV-bestand DeviceHash, selecteer **Openen** en selecteer **vervolgens Importeren.**  

   > [!div class="mx-imgBorder"]
   > ![Gebruik de opdracht Importeren om de hardware-hash te importeren.](./images/hololens-ap-hash-import.png)

1. Nadat het importeren is voltooien, **selecteert u Apparaten**  >  **Windows**  >  **Windows enrollment**  >  **Devices**  >  **Sync.** Het proces kan enkele minuten duren, afhankelijk van het aantal apparaten dat wordt gesynchroniseerd. Als u het geregistreerde apparaat wilt zien, selecteert u **Vernieuwen.**  

   > [!div class="mx-imgBorder"]
   > ![Gebruik de opdrachten Synchroniseren en Vernieuwen om de apparatenlijst weer te geven.](./images/hololens-ap-devices-sync.png)  

### <a name="5-create-a-device-group"></a>5. Een apparaatgroep maken

1. Selecteer [Microsoft Endpoint Manager nieuwe groep in](https://endpoint.microsoft.com)het   >  **beheercentrum.**

1. Bij **Groepstype** selecteert **u Beveiliging** en voert u vervolgens een groepsnaam en beschrijving in.

1. Bij **Lidmaatschapstype** selecteert u **Toegewezen** of **Dynamisch apparaat.**

1. Voer een van de volgende handelingen uit:  

   - Als u in **de vorige** stap Toegewezen als **lidmaatschapstype** hebt geselecteerd, selecteert u **Leden** en voegt u vervolgens Autopilot-apparaten toe aan de groep. Autopilot-apparaten die nog niet zijn ingeschreven, worden vermeld met het serienummer van het apparaat als apparaatnaam.
   - Als u in  **de vorige** stap Dynamische apparaten hebt geselecteerd als lidmaatschapstype, selecteert u Leden van dynamisch apparaat en voert u in Geavanceerde regel code **in** die er als volgt uit ziet:
     - Als u een groep wilt maken met al uw Autopilot-apparaten, typt u: `(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`
     - Het veld groepstag van Intune wordt toe te staan aan het **kenmerk OrderID** op Azure AD-apparaten. Als u een groep wilt maken met al uw Autopilot-apparaten met een specifieke groepstag (de OrderID van het Azure AD-apparaat), typt u: `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881")`
     - Als u een groep wilt maken met al uw Autopilot-apparaten met een specifieke inkooporder-id, typt u: `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")`

     > [!NOTE]  
     > Deze regels zijn gericht op kenmerken die uniek zijn voor Autopilot-apparaten.
1. Selecteer **Opslaan** en selecteer vervolgens **Maken.**

### <a name="6-create-autopilot-profile-and-assign-it-to-the-device-group"></a>6. Een Autopilot-profiel maken en dit toewijzen aan de apparaatgroep

1. Selecteer [Microsoft Endpoint Manager](https://endpoint.microsoft.com)het beheercentrum de optie Apparaten Windows Windows en Windows  >    >    >  **Autopilot-implementatieprofielen**  >    >  Profiel maken HoloLens.
   ![De vervolgkeuzepagina Profiel maken bevat een HoloLens item.](./images/hololens-ap-enrollment-profiles.png)

1. Voer een profielnaam en -beschrijving in en selecteer **Volgende.**  
   Als het goed is, ziet u een **lijst met HoloLens.** Als deze optie niet aanwezig is, gebruikt u een van de [feedbackopties](hololens2-autopilot.md#feedback-and-support-for-autopilot) om contact met ons op te nemen.

   > [!div class="mx-imgBorder"]
   > ![Voeg een profielnaam en -beschrijving toe.](./images/hololens-ap-profile-name.png)

1. Op de **pagina Out-Of-Box Experience (OOBE)** zijn de meeste instellingen vooraf geconfigureerd om OOBE voor deze evaluatie te stroomlijnen. U kunt desgewenst de volgende instellingen configureren:  

   - **Taal (regio)**: Selecteer de taal voor OOBE. U wordt aangeraden een taal te selecteren in de lijst met [ondersteunde talen voor HoloLens 2.](hololens2-language-support.md)
   - **Toetsenbord automatisch configureren:** selecteer Ja om ervoor te zorgen dat het toetsenbord overeenkomt met de geselecteerde **taal.**
   - Sjabloon voor apparaatnaam **toepassen:** als u de apparaatnaam automatisch wilt instellen tijdens OOBE, selecteert u Ja en voert u vervolgens de sjabloonzin en tijdelijke aanduidingen **in** Bij Een naam invoeren voert u bijvoorbeeld een voorvoegsel en een tijdelijke aanduiding in voor een willekeurig getal van vier  `%RAND:4%` &mdash; cijfers.
     > [!NOTE]  
     > Als u een apparaatnaamsjabloon gebruikt, start het OOBE-proces het apparaat één keer opnieuw op nadat de apparaatnaam is toegepast en voordat het apparaat aan Azure AD wordt toevoegen. Door deze herstart wordt de nieuwe naam van kracht.  

   > [!div class="mx-imgBorder"]
   > ![OOBE-instellingen configureren.](./images/hololens-ap-profile-oobe.png)

1. Nadat u de instellingen hebt geconfigureerd, selecteert u **Volgende.**
1. Voeg op **de pagina Bereiktags** desgewenst de bereiktags toe die u wilt toepassen op dit profiel. Zie [Use role-based access control and scope tags for distributed IT](/mem/intune/fundamentals/scope-tags.md) (Op rollen gebaseerd toegangsbeheer en bereiktags gebruiken voor gedistribueerde IT) voor meer informatie over bereiktags. Selecteer **Volgende** als u klaar bent.
1. Selecteer op **de pagina Toewijzingen** de **optie Geselecteerde groepen** voor Toewijzen **aan**.
1. Selecteer **onder GESELECTEERDE GROEPEN** de optie + Groepen selecteren om op te **nemen.**
1. Selecteer in **de lijst Groepen selecteren** die moeten worden opgenomen de apparaatgroep die u hebt gemaakt voor de Autopilot-HoloLens en selecteer vervolgens **Volgende.**  
  
   Als u groepen wilt uitsluiten, selecteert u **Groepen selecteren die moeten worden uitgesloten** en selecteert u de groepen die u wilt uitsluiten.

   > [!div class="mx-imgBorder"]
   > ![Een apparaatgroep toewijzen aan het profiel.](./images/hololens-ap-profile-assign-devicegroup.png)

1. Controleer de **instellingen op de** pagina Beoordelen en maken en selecteer vervolgens Maken **om** het profiel te maken.  

   > [!div class="mx-imgBorder"]
   > ![Beoordelen en maken.](./images/hololens-ap-profile-summ.png)

### <a name="7-create-enrollment-status-page-esp-configuration-and-assign-it-to-the-device-group"></a>7. Configuratie van inschrijvingsstatuspagina (ESP) maken en deze toewijzen aan de apparaatgroep

Op de pagina Status van de inschrijving (ESP) wordt de status weergegeven van het volledige apparaatconfiguratieproces dat wordt uitgevoerd wanneer een door MDM beheerde gebruiker zich voor de eerste keer bij een apparaat aan meldt. Zorg ervoor dat uw ESP-configuratie op het volgende lijkt en controleer of de toewijzingen juist zijn.  

> [!div class="mx-imgBorder"]
> ![ESP-configuratie.](./images/hololens-ap-profile-settings.png)

Raadpleeg de pagina Status van de inschrijving instellen - Microsoft Intune | voor meer informatie [over ESP Microsoft Intune | Microsoft Docs](/mem/intune/enrollment/windows-enrollment-status)

### <a name="8-verify-the-profile-status-of-the-hololens-devices"></a>8. Controleer de profielstatus van de HoloLens apparaten

1. Selecteer Microsoft Endpoint Manager het beheercentrum **de** optie  >  **Apparaten Windows**  >  **Windows-inschrijvingsapparaten.**  >  

1. Controleer of de HoloLens apparaten worden weergegeven en of hun profielstatus **Toegewezen is.**  

   > [!NOTE]  
   > Het kan enkele minuten duren voordat het profiel is toegewezen aan het apparaat.  

   > [!div class="mx-imgBorder"]
   > ![Apparaat- en profieltoewijzingen.](./images/hololens-ap-devices-assignments.png)

## <a name="windows-autopilot-for-hololens-2-user-experience"></a>Windows Autopilot voor HoloLens 2 gebruikerservaring

Zodra de bovenstaande instructies zijn voltooid, HoloLens 2 gebruikers de volgende ervaring door om hun apparaten in HoloLens inrichten:  

1. Voor de Autopilot-ervaring is internettoegang vereist. Gebruik een van de volgende opties om internettoegang te bieden:

    - Verbinding maken apparaat in een Wi-Fi-netwerk in OOBE en laat het vervolgens autopilot-ervaring automatisch detecteren. Dit is de enige keer dat u met OOBE moet communiceren totdat de Autopilot-ervaring is voltooid. Standaard wacht HoloLens 2 10 seconden om Autopilot te detecteren na het detecteren van internet. Als er binnen tien seconden geen Autopilot-profiel wordt gedetecteerd, presenteert OOBE de EULA. Als u dit scenario tegenkomt, start u het apparaat opnieuw op, zodat er een andere poging kan worden gedaan om Autopilot te detecteren. Houd er ook rekening mee dat OOBE alleen voor onbepaalde tijd op Autopilot kan wachten als het TenantLockdown-beleid is ingesteld op het apparaat.

    - Verbinding maken uw apparaat met Ethernet met behulp van USB-C naar Ethernet-adapters voor bekabelde internetverbinding en HoloLens 2 Autopilot-ervaring automatisch voltooien.

    - Verbinding maken apparaat met USB-C-naar-Wi-Fi-adapters voor draadloze internetverbinding en HoloLens 2 autopilot-ervaring automatisch voltooien.

        > [!IMPORTANT]  
       > Apparaten die gebruikmaken van Wi-Fi-netwerken in OOBE voor Autopilot, moeten zich op [Windows Holographic, versie 20H2.](hololens-release-notes.md#windows-holographic-version-20h2)
       >
       > Voor apparaten die gebruikmaken van ethernetadapters moet u het apparaat verbinden met het netwerk voordat out-of-the-Box-Experience (OOBE) wordt gestart. Het apparaat bepaalt op het eerste OOBE-scherm of het wordt ingericht als een Autopilot-apparaat. Als het apparaat geen verbinding kan maken met het netwerk of als u ervoor kiest het apparaat niet in terichten als Een Autopilot-apparaat, kunt u het apparaat niet op een later tijdstip wijzigen in Autopilot-inrichting. In plaats daarvan moet u deze procedure opnieuw starten om het apparaat in terichten als een Autopilot-apparaat.

1. Het apparaat moet OOBE automatisch starten. Communiceer niet met OOBE.

    > [!IMPORTANT]
    > Communiceer niet met OOBE en druk niet op de aan/uit-knop om het systeem stand-by/uit te sluiten terwijl Autopilot wordt uitgevoerd. Dit kan ertoe leiden dat de Autopilot-stroom niet is voltooid.

   U HoloLens 2 netwerkconnectiviteit detecteren en oobe automatisch laten voltooien. Het apparaat kan opnieuw worden opgestart tijdens OOBE. De OOBE-schermen moeten er als volgt uit zien.

   ![OOBE, stap 1. ](./images/autopilot-welcome.jpg)
    ![ OOBE- stap 2. ](./images/autopilot-step-complete.jpg)
    ![ OOBE- stap 3.](./images/autopilot-device-setup.jpg)

1. Aan het einde van OOBE kunt u zich aanmelden bij het apparaat met behulp van uw gebruikersnaam en wachtwoord.

   <br/><img src="./images/other-user.jpg" alt="Other user" width="450" height="700" />

## <a name="tenant-lockdown-csp-and-autopilot"></a>CSP en Autopilot voor vergrendelen van tenants

HoloLens 2 ondersteunen TenantLockdown CSP vanaf Windows Holographic versie 20H2. Deze CSP houdt apparaten op de tenant van de organisatie door ze te vergrendelen voor die tenant, zelfs door het apparaat opnieuw in te stellen of een reflash uit te voeren.

[TenantLockdown](/windows/client-management/mdm/tenantlockdown-csp) Met CSP HoloLens 2 alleen met Autopilot gekoppeld aan MDM-inschrijving. Zodra het knooppunt RequireNetworkInOOBE van tenantLockdown CSP is ingesteld op waar of onwaar (in eerste instantie ingesteld) op HoloLens 2, blijft die waarde op het apparaat staan ondanks reflashing, updates van het besturingssysteem, enzovoort.

Zodra het knooppunt RequireNetworkInOOBE van tenantLockdown-CSP's is ingesteld op true op HoloLens 2, wacht OOBE voor onbepaalde tijd tot het Autopilot-profiel is gedownload en toegepast, na de netwerkverbinding.

Zodra het knooppunt RequireNetworkInOOBE van tenantLockdown-CSP's is ingesteld op true op HoloLens 2, zijn de volgende bewerkingen niet toegestaan in OOBE:

- Lokale gebruiker maken met runtime-inrichting 
- Azure AD Join-bewerking uitvoeren via runtime-inrichting 
- Selecteren wie eigenaar is van het apparaat in OOBE-ervaring 

#### <a name="how-to-set-this-using-intune"></a>Hoe kan ik dit instellen met Intune? 
1. Maak een aangepast OMA URI-apparaatconfiguratieprofiel en geef true op voor het knooppunt RequireNetworkInOOBE, zoals hieronder wordt weergegeven.
Oma-URI-waarde moet ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE zijn

   > [!div class="mx-imgBorder"]
   > ![Vergrendelingsvergrendeling instellen via OMA-URI.](images/hololens-tenant-lockdown.png)

1. Maak een groep en wijs het apparaatconfiguratieprofiel toe aan die apparaatgroep.

1. Maak het HoloLens 2 apparaatlid van de groep die u in de vorige stap hebt gemaakt en synchronisatie activeren.  

Controleer in de Intune-portal of de apparaatconfiguratie is toegepast. Zodra deze apparaatconfiguratie is toegepast op HoloLens 2 apparaat, zijn de effecten van TenantLockdown actief.

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a>Hoe kan ik RequireNetworkInOOBE van TenantLockdown op een HoloLens 2 in Intune?

1. Verwijder de HoloLens 2 uit de apparaatgroep waaraan de hierboven gemaakte apparaatconfiguratie eerder is toegewezen.

1. Maak een aangepast op OMA URI gebaseerd apparaatconfiguratieprofiel en geef false op voor RequireNetworkInOOBE, zoals hieronder wordt weergegeven.
Oma-URI-waarde moet ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE zijn

   > [!div class="mx-imgBorder"]
   > ![Schermopname van de instelling RequireNetworkInOOBE op false via OMA URI in Intune.](images/hololens-tenant-lockdown-false.png)

1. Maak een groep en wijs het apparaatconfiguratieprofiel toe aan die apparaatgroep. 

1. Maak het HoloLens 2 apparaatlid van de groep die u in de vorige stap hebt gemaakt en synchronisatie activeren.

Controleer in de Intune-portal of de apparaatconfiguratie is toegepast. Zodra deze apparaatconfiguratie is toegepast op HoloLens 2 apparaat, zijn de effecten van TenantLockdown inactief.

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a>Wat zou er gebeuren tijdens OOBE als het Autopilot-profiel niet is toegewezen aan een HoloLens nadat TenantLockdown is ingesteld op true? 
OOBE wacht voor onbepaalde tijd tot het Autopilot-profiel is gedownload en het volgende dialoogvenster wordt weergegeven. Als u de gevolgen van TenantLockdown wilt verwijderen, moet het apparaat eerst worden geregistreerd bij de oorspronkelijke tenant met behulp van Autopilot en moet RequireNetworkInOOBE niet zijn ingesteld zoals beschreven in de vorige stap, voordat de beperkingen die door TenantLockdown CSP zijn geïntroduceerd, worden verwijderd.

![In de apparaatweergave voor wanneer beleid wordt afgedwongen op het apparaat.](images/hololens-autopilot-lockdown.png)

## <a name="known-issues--limitations"></a>Bekende problemen & beperkingen

- We onderzoeken een probleem waarbij de installatie van een toepassing op basis van apparaatcontext die is geconfigureerd in MEM, niet van toepassing is op HoloLens. [Meer informatie over het installeren van apparaatcontext en gebruikerscontext.](/mem/intune/apps/apps-windows-10-app-deploy#install-apps-on-windows-10-devices)
- Tijdens het instellen van Autopilot via Wi-Fi is er mogelijk een exemplaar waarin het Autopilot-profiel niet wordt gedownload wanneer er voor het eerst een internetverbinding tot stand is gebracht. In dit geval wordt de Gebruikslicentieovereenkomst (EULA) weergegeven en heeft de gebruiker de mogelijkheid om door te gaan met de niet-Autopilot-installatie. Als u het apparaat opnieuw wilt instellen met Autopilot, zet u het apparaat in de slaapstand en wordt het vervolgens ingeschakeld of start u het apparaat opnieuw op en laat u het opnieuw proberen.

### <a name="troubleshooting"></a>Problemen oplossen

De volgende artikelen kunnen een nuttige informatiebron voor u zijn voor meer informatie en het oplossen van Autopilot-problemen. Deze artikelen zijn echter gebaseerd op Windows 10 Desktop en niet alle informatie is mogelijk van toepassing op HoloLens:

- [Windows Autopilot: bekende problemen](/mem/autopilot/known-issues)
- [Problemen met inschrijving van Windows-apparaten in Microsoft Intune oplossen](/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [Windows Autopilot - Beleidsconflicten](/mem/autopilot/policy-conflicts)

## <a name="feedback-and-support-for-autopilot"></a>Feedback en ondersteuning voor Autopilot

Gebruik een van de volgende methoden om feedback te geven of problemen te melden:

- Neem contact op met uw wederverkoper of distributeur voor ondersteuning bij apparaatregistratie.
- Voor algemene ondersteuningsvragen over Windows Autopilot of voor problemen zoals profieltoewijzingen, het maken van groepen of besturingselementen in de MEM-portal, kunt u contact opnemen [met Microsoft Endpoint Manager ondersteuning](/mem/get-support)  
- Als uw apparaat is geregistreerd bij de Autopilot-service en het profiel is toegewezen in de MEM-portal, neem dan contact op met HoloLens ondersteuning [(zie](/hololens/) de kaart Ondersteuning). Open een ondersteuningsticket en voeg, indien van toepassing, schermopnamen en logboeken toe door [offline](hololens-diagnostic-logs.md#offline-diagnostics) diagnostische logboeken vast te leggen tijdens de OOBE (Out-Of-Box-Experience).
- Als u een probleem vanaf het apparaat wilt melden, gebruikt u de Feedback-hub-app op uw HoloLens. Selecteer in Feedback-hub de categorie **Enterprise Management**  >  **Device.**
- Als u algemene feedback wilt geven over Autopilot voor HoloLens, kunt u deze enquête [indienen](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR7vUmjNI0XhCp1T72ODD84xUMEM3TVJPOURBRkNVWkYwM0RWWEhJNVdJSi4u&wdLOR=cEF1F57F6-AD9B-4CCE-B919-AB5AE320A993)

## <a name="delete-autopilot-devices"></a>Autopilot-apparaten verwijderen

Mogelijk wilt u geen apparaat meer gebruiken voor Autopilot of uw apparaten registreren bij een andere tenant. Als u dit wilt doen, leest u [hoe u Autopilot-apparaten kunt verwijderen.](/mem/autopilot/add-devices#delete-autopilot-devices)