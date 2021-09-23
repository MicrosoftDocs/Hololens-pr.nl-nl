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
ms.date: 09/14/2021
ms.reviewer: ''
manager: ranjibb
appliesto:
- HoloLens 2
ms.openlocfilehash: 22d635fd3fc32b8aedc36bcb19d900128cdcb718
ms.sourcegitcommit: ab86b31357004726d8a28ebae76123728adc8e59
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/23/2021
ms.locfileid: "128306162"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Insider-preview voor Microsoft HoloLens

Welkom bij de nieuwste Insider Preview-builds voor HoloLens. Het is eenvoudig om aan de [slag te gaan](hololens-insider.md#start-receiving-insider-builds) en waardevolle feedback te geven voor onze volgende belangrijke update van het besturingssysteem voor HoloLens.

## <a name="windows-insider-release-notes"></a>Windows Opmerkingen bij de release van Insider

We zijn blij om nieuwe functies opnieuw te kunnen Windows Insiders. Voor nieuwe builds worden de dev- en bètakanalen gebruikt voor de nieuwste updates. We blijven deze pagina bijwerken wanneer we meer functies en updates toevoegen aan onze Windows Insider-builds. Word enthousiast en bereid u voor om deze updates in uw realiteit te combineren.

Dit gaat over de verbeterde probleemoplossing en apparaatrapporten, een aantal opgeloste fouten in de kioskmodus en de certificaatviewer, het uitgebreide beheerbaarheidsoppervlak en de verbeterde betrouwbaarheid van updates. Een nieuwe functie van deze functie-update die binnenkort HoloLens is onze modus Voor platform verplaatsen. Bekijk alle nieuwe geweldige functies voor HoloLens 2.

| Functie                 | Beschrijving                | Gebruiker of scenario | Build geïntroduceerd |
|-------------------------|----------------------------|--------------|------------------|
| [Platformmodus verplaatsen](#moving-platform-mode) | Introduceert de bètaversie van de Moving Platform-modus, die, wanneer geconfigureerd, het gebruik van HoloLens 2 op grote 2019-2018 mogelijk maakt met weinig dynamische beweging. | Alles | 20348.1411 |
| [PfX-bestandsondersteuning voor Certificaatbeheer](#pfx-file-support-for-certificate-manager) | PFX-certificaten toevoegen via Instellingen UI | Eindgebruiker | 20348.1405 |
| [Geavanceerd diagnostisch rapport weergeven in Instellingen op HoloLens](#view-advanced-diagnostic-report-in-settings-on-hololens) | Diagnostische MDM-logboeken weergeven op apparaat | Problemen oplossen | 20348.1405 |
| [Offline diagnostische meldingen](#offline-diagnostics-notifications) | Feedback over het verzamelen van logboeken | Problemen oplossen | 20348.1405 |
| [Verbeteringen in het verzamelen van logboeken met weinig opslag](#low-storage-log-collection-improvements) | Verbeteringen in scenario's voor logboekverzameling tijdens situaties met weinig opslag. | Problemen oplossen | 20348.1412 |
| [CSP-wijzigingen voor rapportage HoloLens details](#csp-changes-for-reporting-hololens-details) | Nieuwe CSP's voor om gegevens op te vragen | IT-beheerders    | 20348.1403                 |
| [Beleid voor automatisch aanmelden beheerd door CSP](#auto-login-policy-controlled-by-csp) | Wordt gebruikt om automatisch aan te melden bij een account | IT-beheerders | 20348.1405 |
| [Verbeterde detectie van opnieuw opstarten van updates en meldingen](#improved-update-restart-detection-and-notifications) | Nieuw ingeschakeld beleid en UX voor updates. | IT-beheerders | 20348.1405 |
| [Slim opnieuw proberen voor app-updates](#smart-retry-for-app-updates) | Hiermee kunnen IT-beheerders geplande nieuwe proberen om apps bij te werken. | IT-beheerders | 20348.1405 |
| [Alleen persoonlijke Store-apps gebruiken voor Microsoft Store](#use-only-private-store-apps-for-microsoft-store) | De Store-app configureren om alleen apps van de organisatie weer te geven | IT-beheerder | 20348.1408 |
| [WDAC- en LOB-apps gebruiken](#use-wdac-and-lob-apps) | Hiermee kunnen IT-beheerders hun eigen apps gebruiken en nog steeds WDAC gebruiken om andere apps te blokkeren. | IT-beheerders | 20348.1405 |
| [Oplossingen en verbeteringen](#fixes-and-improvements) | Oplossingen en verbeteringen voor HoloLens. | Alles | 20348.1411 |

### <a name="it-admin-insider-feature-checklist"></a>Controlelijst voor Insider-functies van IT-beheerder

✔️ als u één Azure AD-account wilt instellen om automatisch aan te melden, configureert u [deze nieuwe CSP.](#auto-login-policy-controlled-by-csp) <br>
✔️ als u wilt configureren dat uw apps automatisch proberen bij te werken nadat het bijwerken is mislukt, stelt u deze nieuwe CSP in [voor slim opnieuw proberen.](#smart-retry-for-app-updates) <br>
✔️ Als u meer controle wilt over updates van het besturingssysteem, bekijkt u deze nieuw [ingeschakelde updatebeleidsregels.](#improved-update-restart-detection-and-notifications) <br>
✔️ Als u de apps van uw organisatie beschikbaar wilt maken in de store van uw bedrijf via de Microsoft Store, maar alleen toegang wilt toestaan tot de apps van uw organisatie en niet de volledige [store,](#use-only-private-store-apps-for-microsoft-store)stelt u dit beleid in. <br>
✔️ als u de beschikbare opslagruimte, SSID of BSSID van uw HoloLens-apparaten wilt weten, raadpleegt u deze [rapportage-CSP's.](#csp-changes-for-reporting-hololens-details) <br>
✔️ Als u WDAC wilt gebruiken om het starten van apps of processen te blokkeren, maar ook uw eigen line-of-iness-apps wilt gebruiken, kunt u nu LOB toestaan in uw [WDAC-beleid.](#use-wdac-and-lob-apps)

### <a name="moving-platform-mode"></a>Platformmodus verplaatsen

Vanaf **Insider-build 20348.1411** is bètaondersteuning toegevoegd voor het bijhouden van bewegingsplatforms met weinig dynamische beweging op HoloLens 2. Nadat u de build hebt geïnstalleerd en de Moving Platform-modus hebt inschakelen, kunt u uw HoloLens 2 gebruiken in eerder ontoegankelijke omgevingen, zoals grote zee- en grote zee- en containeromgevingen. Op dit moment is de functie gericht op het inschakelen van deze specifieke platformen voor verplaatsen. Hoewel niets voorkomt dat u de functie in andere omgevingen probeert te gebruiken, is de functie gericht op het toevoegen van ondersteuning voor deze omgevingen.

Ga naar de pagina voor het verplaatsen van platformen voor meer informatie over wat wordt ondersteund en hoe u deze nieuwe functie [kunt inschakelen.](hololens2-moving-platform.md)

#### <a name="overview-to-try-out-moving-platform-mode"></a>Overzicht van het uitproberen van de platformmodus verplaatsen

1. [Schakel de ontwikkelaarsmodus en de apparaatportal in.](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)
1. [Schakel de platformmodus verplaatsen in via De apparaatportal.](hololens2-moving-platform.md#enabling-moving-platform-mode)
1. Ga met uw apparaat naar uw grote bewegende platform en kijk hoe stabiel hologrammen zijn.

### <a name="pfx-file-support-for-certificate-manager"></a>PfX-bestandsondersteuning voor Certificaatbeheer

Geïntroduceerd in Windows Insider-build 20348.1405. We hebben nu ondersteuning toegevoegd aan [Certificaatbeheer om PFX-certificaten](certificate-manager.md) te gebruiken. Wanneer gebruikers naar **Instellingen** Update & Security Certificates gaan en Een certificaat installeren selecteren, ondersteunt de gebruikersinterface nu het  >    >  PFX-certificaatbestand. 
Gebruikers kunnen een PFX-certificaat met een persoonlijke sleutel importeren in een gebruikers- of machineopslag.

#### <a name="overview-to-try-out-pfx-files-in-certificate-manager"></a>Overzicht van het uitproberen van PFX-bestanden in Certificate Manager

1. Bereid uw PFX-bestand voor.
1. Kopieer het bestand naar uw apparaat via een USB-C-kabel.
1. Open de Instellingen app, navigeer naar [Certificaatbeheer](certificate-manager.md) en pas het certificaat toe.

### <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a>Geavanceerd diagnostisch rapport weergeven in Instellingen op HoloLens

Voor beheerde apparaten bij het oplossen van problemen is het bevestigen dat een verwachte beleidsconfiguratie wordt toegepast een belangrijke stap. Voorheen moest voor deze nieuwe functie het weergeven van deze informatie op het apparaat worden uitgevoerd via MDM of in de buurt van het apparaat na het exporteren van diagnostische MDM-logboeken die zijn verzameld via Instellingen Accounts Toegang tot werk **of**  ->    >  **school,** en selecteert u **Uw** beheerlogboeken exporteren en weergeven op een pc in de buurt.

De MDM-diagnose kan nu worden weergegeven op het apparaat met behulp van de Edge-browser. Als u het diagnostischE MDM-rapport eenvoudiger wilt weergeven, gaat u naar de pagina Werk- of schoolrapport openen en **selecteert u Geavanceerd diagnostisch rapport weergeven.** Hiermee wordt het rapport gegenereerd en geopend in een nieuw Edge-venster.

![Bekijk het geavanceerde diagnostische rapport in Instellingen app.](./images/view-advanced-diagnostic-report.jpg)

#### <a name="overview-to-try-out-the-advanced-diagnostic-report"></a>Overzicht voor het uitproberen van het geavanceerde diagnostische rapport

1. Open de app Instellingen.
1. Navigeer naar de pagina Accounts en klik op de nieuwe koppeling **Uw beheerlogboeken exporteren.**
1. Bekijk geavanceerde informatie over de configuraties van uw apparaat.

### <a name="offline-diagnostics-notifications"></a>Offline diagnostische meldingen

Dit is een update voor een bestaande functie met de [naam Offlinediagnose.](hololens-diagnostic-logs.md#offline-diagnostics) Voorheen was er geen duidelijke indicator voor gebruikers dat ze de diagnostische verzameling hadden geactiveerd of dat deze was voltooid.
Nu toegevoegd aan Windows Insider-builds, zijn er twee soorten feedback over offlinediagnose. De eerste zijn pop-upmeldingen die worden weergegeven voor zowel wanneer de verzameling wordt gestart als voltooid. Deze worden weergegeven wanneer de gebruiker is aangemeld en visuals heeft.

![Pop-up voor het verzamelen van logboeken.](./images/logcollection1.jpg)

![Pop-up wanneer het verzamelen van logboeken is voltooid.](./images/logcollection2.jpg)

Omdat gebruikers vaak offlinediagnose gebruiken als mechanisme voor het verzamelen van terugvallogboeken wanneer ze geen toegang hebben tot een weergave, zich niet kunnen aanmelden of zich nog steeds in OOBE kunnen aanmelden, wordt er ook een audio-cue afgespeeld wanneer logboeken worden verzameld. Dit geluid wordt afgespeeld naast de pop-upmelding.

Deze nieuwe functie wordt ingeschakeld wanneer uw apparaat wordt bijgewerkt en hoeft niet te worden ingeschakeld of beheerd. In elk geval dat deze nieuwe feedback niet kan worden weergegeven of gehoord, wordt offlinediagnose nog steeds gegenereerd.

We hopen dat het met deze nieuwere toevoeging van feedback gemakkelijker is om diagnostische gegevens te verzamelen en sneller in staat te zijn om uw problemen op te lossen.

#### <a name="overview-to-try-out-the-diagnostics-notifications"></a>Overzicht om de diagnostische meldingen uit te proberen

1. Ontgrendel uw apparaat en draag het.
1. Druk op de **combinatie van de** knop **Aan/uit** en volume omlaag om [offlinediagnose te verzamelen.](hololens-diagnostic-logs.md#offline-diagnostics)
1. Bekijk de pop-upmeldingen en horen audio aanwijzingen voor wanneer uw apparaat wordt gestart en klaar is met het verzamelen van logboeken.

### <a name="low-storage-log-collection-improvements"></a>Verbeteringen in de verzameling met logboeken met weinig opslag

In scenario's waarin een apparaat weinig schijfruimte lijkt te hebben wanneer diagnostische logboeken worden verzameld, wordt **er een** extra rapport met deStorageDiagnostics.zipgemaakt. De drempelwaarde voor lage opslag wordt automatisch bepaald door de Windows [opslag te bepalen.](https://support.microsoft.com/office/use-onedrive-and-storage-sense-in-windows-10-to-manage-disk-space-de5faa9a-6108-4be1-87a6-d90688d08a48)

#### <a name="overview-to-try-out-the-low-storage-improvements"></a>Overzicht van het uitproberen van de verbeteringen in de lage opslag

1. Vul de opslagruimte van uw apparaat in.
1. Druk op de **combinatie van de** knop **Aan/uit** en volume omlaag om [offlinediagnose te verzamelen.](hololens-diagnostic-logs.md#offline-diagnostics)
1. U ziet dat er een nieuw bestand in de verzameling logboeken is opgeslagen in de map Documenten van uw HoloLens.

### <a name="csp-changes-for-reporting-hololens-details"></a>CSP-wijzigingen voor rapportage HoloLens details

- Geïntroduceerd in Windows Insider-build, 20348.1403

De volgende CSP's zijn bijgewerkt met nieuwe manieren om informatie van uw HoloLens rapporteren.

#### <a name="devdetail-csp---free-storage"></a>DevDetail CSP - Gratis Storage

DevDetail CSP rapporteert nu ook vrije opslagruimte op HoloLens apparaat. Dit moet ongeveer overeenkomen met de waarde die wordt weergegeven op Instellingen pagina van Storage app. Hieronder vindt u het specifieke knooppunt met deze informatie.

- ./DevDetail/Ext/Microsoft/FreeStorage (alleen GET-bewerking)

#### <a name="devicestatus-csp---ssid-and-bssid"></a>DeviceStatus CSP - SSID en BSSID

DeviceStatus CSP rapporteert nu ook SSID en BSSID van Wi-Fi netwerk waarmee HoloLens actief is verbonden. Hieronder vindt u de specifieke knooppunten die deze informatie bevatten.

- ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac-adres van Wi-Fi adapter*/SSID
- ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac-adres van Wi-Fi adapter*/BSSID

Voorbeeld van syncml-blob (voor MDM-leveranciers) om een query uit te voeren voor NetworkIdentifiers

```xml
<SyncML>
<SyncBody>
    <Get>
        <CmdID>$CmdID$</CmdID>
        <Item>
            <Target>
            <LocURI>
                ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers?list=StructData
            </LocURI>
            </Target>
        </Item>
    </Get>
    <Final/>
</SyncBody>
</SyncML>
```

### <a name="auto-login-policy-controlled-by-csp"></a>Beleid voor automatisch aanmelden beheerd door CSP

Met dit nieuwe beleid AutoLogonUser bepaalt u of een gebruiker automatisch wordt aangemeld. Sommige klanten willen apparaten instellen die zijn gekoppeld aan een identiteit, maar geen aanmeldingservaring willen. Imagine apparaat ophalen en direct hulp op afstand gebruiken. Of hebben een voordeel van het snel distribueren van HoloLens apparaten en hun eindgebruikers in staat stellen zich sneller aan te melden.

Wanneer het beleid is ingesteld op een niet-lege waarde, wordt het e-mailadres van de gebruiker voor automatische aanmelding opgegeven. De opgegeven gebruiker moet zich ten minste één keer bij het apparaat laten aanmelding inschakelen.

De OMA-URI van nieuwe `./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser` beleidsreekswaarde

- De gebruiker met hetzelfde e-mailadres heeft automatische aanmelding ingeschakeld.

Op een apparaat waarop dit beleid is geconfigureerd, moet de gebruiker die is opgegeven in het beleid ten minste één keer worden aanmelding. Als het apparaat na de eerste aanmelding opnieuw wordt opgestart, wordt de opgegeven gebruiker automatisch aangemeld. Er wordt slechts één gebruiker voor automatische aanmelding ondersteund. Zodra deze is ingeschakeld, kan de automatisch aangemelde gebruiker zich niet meer handmatig afmelden. Als u zich als een andere gebruiker wilt laten aanmeldingen, moet het beleid eerst worden uitgeschakeld.

> [!NOTE]
>
> - Voor sommige gebeurtenissen, zoals belangrijke updates van het besturingssysteem, moet de opgegeven gebruiker zich mogelijk opnieuw bij het apparaat laten aanmeldingen om automatisch aanmeldingsgedrag te hervatten.
> - Automatische aanmelding wordt alleen ondersteund voor MSA- en AAD-gebruikers.

#### <a name="overview-to-try-auto-logon-csp"></a>Overzicht van het proberen van CSP voor automatische aanmelding

1. Configureer de nieuwe CSP voor een gewenste gebruiker [met behulp van een aangepast beleid:](/mem/intune/configuration/custom-settings-windows-10)`./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser`
1. Pas de CSP toe op het apparaat via [het inrichtingspakket](hololens-provisioning.md) of [MDM.](hololens-mdm-configure.md)
1. Meld u aan bij het opgegeven account.
1. Start het apparaat opnieuw op en kijk of de gebruiker automatisch is aangemeld.

### <a name="improved-update-restart-detection-and-notifications"></a>Verbeterde detectie en meldingen voor opnieuw opstarten van updates

Tussen actieve uren en het beleid voor de installatietijd is het mogelijk om te voorkomen dat HoloLens apparaten opnieuw worden opgestart wanneer ze in gebruik zijn. Het zou echter ook de acceptatie van updates vertragen als er geen herstart wordt uitgevoerd om de installatie van een vereiste update te voltooien. We hebben nu beleidsregels toegevoegd waarmee IT deadlines en vereiste herstarts kan afdwingen en ervoor te zorgen dat de installatie van een update tijdig is voltooid. Gebruikers kunnen een melding ontvangen voordat het opnieuw opstarten wordt gestart en ze kunnen het opnieuw opstarten vertragen in overeenstemming met het IT-beleid.

De volgende updatebeleidsregels zijn toegevoegd:

- [Update/AutoRestartNotificationSchedule](/windows/client-management/mdm/policy-csp-update#update-autorestartnotificationschedule)
- [Update/AutoRestartRequiredNotificationDismissal](/windows/client-management/mdm/policy-csp-update#update-autorestartrequirednotificationdismissal)
- [Update/ConfigureDeadlineForFeatureUpdates](/windows/client-management/mdm/policy-csp-update#update-configuredeadlineforfeatureupdates)
- [Update/ConfigureDeadlineForQualityUpdates](/windows/client-management/mdm/policy-csp-update#update-configuredeadlineforqualityupdates)
- [Update/ConfigureDeadlineGracePeriod](/windows/client-management/mdm/policy-csp-update#update-configuredeadlinegraceperiod)
- [Update/ConfigureDeadlineNoAutoReboot](/windows/client-management/mdm/policy-csp-update#update-configuredeadlinenoautoreboot)
- [Update/ScheduleImminentRestartWarning](/windows/client-management/mdm/policy-csp-update#update-scheduleimminentrestartwarning)
- [Update/ScheduleRestartWarning](/windows/client-management/mdm/policy-csp-update#update-schedulerestartwarning)
- [Update/UpdateNotificationLevel](/windows/client-management/mdm/policy-csp-update#update-updatenotificationlevel)

#### <a name="overview-to-try-new-update-notifications"></a>Overzicht om nieuwe updatemeldingen uit te proberen

1. Configureer een van de nieuwe update-CSP's via [inrichtingspakket](hololens-provisioning.md) of [MDM](hololens-mdm-configure.md) (zie de bovenstaande koppelingslijst en kies er een).
1. Gebruik het apparaat op de geplande tijd.
1. U ziet dat de gebruiker op de hoogte wordt gesteld van de update en dat het apparaat opnieuw moet worden \* opgestart.

\* Uw resultaten kunnen variëren op basis van het gebruikte updatebeleid.

### <a name="smart-retry-for-app-updates"></a>Slim opnieuw proberen voor app-updates

Nu ingeschakeld voor HoloLens is een nieuw beleid waarmee IT-beheerders een terugkerende of eenmalige datum kunnen instellen om apps opnieuw op te starten waarvan de update is mislukt omdat de app in gebruik is, waardoor de update kan worden toegepast. Deze kunnen worden ingesteld op basis van een aantal verschillende triggers, zoals een gepland tijdstip of aanmelding. Zie [ApplicationManagement/ScheduleForceRestartForUpdateFailures](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-scheduleforcerestartforupdatefailures)voor meer informatie over het gebruik van dit beleid.

#### <a name="overview-to-try-smart-retry-for-app-updates"></a>Overzicht van het uitproberen van Slimme nieuwe poging voor app-updates

1. Configureer de nieuwe functie voor slim opnieuw proberen.
1. Meld u aan bij een online omgeving op een apparaat dat uw app nog niet heeft ontvangen en correct is geconfigureerd voor .
1. Zorg ervoor dat het apparaat de app niet kan downloaden door deze uit te schakelen of de verbinding te verbreken.
1. Laat uw apparaat ingeschakeld en verbonden zijn met internet tijdens het geactiveerde tijdstip om het downloaden opnieuw uit te proberen.

### <a name="use-only-private-store-apps-for-microsoft-store"></a>Alleen persoonlijke Store-apps gebruiken voor Microsoft Store

Het beleid RequirePrivateStoreOnly is ingeschakeld voor HoloLens. Met dit beleid kan de Microsoft Store-app zodanig worden geconfigureerd dat alleen de persoonlijke opslag wordt weer geven die voor uw organisatie is geconfigureerd via [Microsoft Store voor Bedrijven](/microsoft-store/microsoft-store-for-business-overview). Beperk de toegang tot alleen de apps die u beschikbaar hebt gemaakt.

Meer informatie over [ApplicationManagement/RequirePrivateStoreOnly](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly).

#### <a name="overview-to-try-only-private-store-apps"></a>Overzicht om alleen persoonlijke Store-apps te proberen

1. Configureer het nieuwe beleid voor uw apparaten via [MDM.](hololens-mdm-configure.md)
1. Meld u aan bij een apparaat met het beleid.
1. Open de Microsoft Store app en u ziet dat u alleen de apps van uw organisatie kunt zien.

### <a name="use-wdac-and-lob-apps"></a>WDAC- en LOB-apps gebruiken

U kunt nu WDAC gebruiken om te blokkeren dat apps of processen worden gelanceerd en uw eigen line-of-iness-apps blijven gebruiken. u kunt ze nu toestaan in uw WDAC-beleid. Als u dit beleid gebruikt, moet u een extra regel code uitvoeren in PowerShell bij het maken van uw WDAC-beleid. [Bekijk de stappen hier.](/mem/intune/configuration/custom-profile-hololens)

#### <a name="overview-to-try-your-own-apps-while-using-wdac-to-block-others"></a>Overzicht om uw eigen apps uit te proberen terwijl u WDAC gebruikt om anderen te blokkeren

1. Verzamel de AUMID's van uw LOB-app en de apps die u wilt blokkeren.
1. [Maak een nieuw WDAC-beleid door](/mem/intune/configuration/custom-profile-hololens) de nieuwe stappen te volgen.
1. [Implementeer het beleid met behulp van MDM](hololens-mdm-configure.md) op uw apparaat.
1. Meld u aan bij het apparaat en kijk of u uw app kunt starten en anderen kunt blokkeren.

### <a name="fixes-and-improvements"></a>Oplossingen en verbeteringen

- Er is [een bekend probleem opgelost voor Apparaatportal waarbij er geen prompt was om vergrendelde bestanden te downloaden.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)
- Er is een [bekend probleem opgelost voor Apparaatportal met time-outs](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)voor het uploaden en downloaden van bestanden.
- Behandelt problemen met het rapporteren van nalevingseigenschappen van HoloLens apparaten; Mogelijk moet u opnieuw opstarten om de juiste rapportage te kunnen starten op Insider-builds.  
- Een TOEGEWEZEN [toegangs-API](/uwp/api/windows.system.userprofile.assignedaccesssettings?view=winrt-20348&preserve-view=true) ingeschakeld zodat apps nu kunnen bepalen of een HoloLens wordt uitgevoerd in een kioskmodus voor de gebruiker die is aangemeld bij de HoloLens.
- De in-box-versie van de Remote Assist is geïnstalleerd op nieuwe flashes.
- Verwerking van Gamepad voor 2D-apps is uitgeschakeld in Insider-builds. Door deze te verwijderen, kunnen apps nu rechtstreeks gebruikmaken van de Gamepad-API's en hebben ze toegang tot de volledige set besturingselementen en kunnen ze doen wat ze willen. Ontwikkelaars moeten de Gamepad-API's gebruiken om Gamepad-invoer te gebruiken. Hier is een voorbeeld voor [Gamepad-klasse (Windows. Gaming.Input) - Windows UWP-toepassingen](/uwp/api/windows.gaming.input.gamepad?view=winrt-20348&preserve-view=true).
- Er is een probleem opgelost waarbij OOBE na de eerste aanmelding van gebruikers werd beëindigd in scenario's waarin op AAD-groepen gebaseerde kioskconfiguraties werden gebruikt.
- Er is een probleem opgelost met het weergeven van updatemeldingen en dialoogvensterprompts om het apparaat opnieuw op te starten.

## <a name="start-receiving-insider-builds"></a>Beginnen met het ontvangen van Insider-builds

> [!NOTE]
> Als u het apparaat niet recent hebt bijgewerkt, start u het apparaat opnieuw op om de status bij te werken en de nieuwste build op te halen.
>
> - De spraakopdracht 'Apparaat opnieuw opstarten' werkt goed.
> - U kunt ook de knop Opnieuw opstarten kiezen in Instellingen/Windows Insider-programma.
>
> Er is een fout in de back-end die u mogelijk hebt aangetroffen, zodat u weer op schema komt.

Ga op HoloLens 2 apparaat naar **Instellingen**  >  **Update & Security**  >  **Windows Insider-programma** en selecteer Aan **de slag.** Koppel het account dat u hebt gebruikt om u te registreren als Windows Insider.

> [!NOTE]
> Als u uw apparaat wilt inschrijven bij Insider-builds, moet u optionele telemetrie inschakelen. Als u dit nog niet hebt gedaan, opent u de Instellingen-app en selecteert u  ->  **Privacydiagnose & feedback** en selecteert u vervolgens **Optionele diagnostische gegevens.**

Windows insider gaat nu over op Kanalen. De **Fast-ring** wordt **het Dev-kanaal,** de langzame **ring** wordt de **bèta-kanaal** en de **Release Preview-ring** wordt het **Release Preview-kanaal.** Deze toewijzing ziet er als volgende uit:

![Windows Uitleg van Insider Channels.](images/WindowsInsiderChannels.png)

Zie [Introducing Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) (Introductie Windows Insider Channels) op Windows Blogs.
Selecteer vervolgens **Actieve ontwikkeling van Windows**, kies of u het **Dev-kanaal** wilt ontvangen of bèta-kanaal **builds** en bekijk de programmavoorwaarden.
Selecteer **Bevestigen > Nu opnieuw opstarten om** te voltooien. Nadat het apparaat opnieuw is opgestart, gaat u naar **Instellingen > Update & Security > Controleren** op updates om de nieuwste build te downloaden.

### <a name="update-error-0x80070490-work-around"></a>Updatefout 0x80070490 work-around

Als er een updatefout wordt 0x80070490 bij het bijwerken op het kanaal Dev of Beta, probeert u de volgende korte-termijn-work-around. Dit omvat het verplaatsen van uw insider-kanaal, het ophalen van de update en vervolgens het terug verplaatsen van uw Insider-kanaal.

#### <a name="stage-one---release-preview"></a>Fase 1 - preview-versie

1. Instellingen, Update & Security en selecteer Windows Insider-programma **Release Preview Channel.**

2. Instellingen, & bijwerken, Windows Bijwerken, Controleren op **updates.** Na de update gaat u verder met Fase 2.

#### <a name="stage-two---dev-channel"></a>Fase 2 - Dev-kanaal

1. Instellingen, Update & Security en selecteer Windows Insider-programma **Dev Channel.**

2. Instellingen, & bijwerken, Windows Bijwerken, Controleren op **updates.**

## <a name="ffu-download-and-flash-directions"></a>FFU-download- en flashbeschrijvingen

Als u wilt testen met een met een vlucht ondertekende ffu, moet u eerst uw apparaat ontgrendelen voordat de met de vlucht ondertekende ffu wordt geflitst.

1. Op pc:
    1. Download ffu naar uw pc vanaf [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .

    1. Installeer ARC (Advanced Recovery Companion) vanuit de Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .

1. Op HoloLens: Ontgrendelen met vlucht: **open** Instellingen Update & Security Windows Insider-programma registreer u vervolgens en start  >    >   het apparaat opnieuw op.

1. Flash-FFU: u kunt nu de met de vlucht ondertekende FFU flashen met behulp van ARC.

### <a name="provide-feedback-and-report-issues"></a>Feedback geven en problemen rapporteren

Gebruik de [Feedback-hub-app op](hololens-feedback.md) uw HoloLens feedback te geven en problemen te melden. Het Feedback-hub zorgt ervoor dat alle benodigde diagnostische gegevens worden opgenomen om onze technici te helpen snel fouten op te sporen en het probleem op te lossen.  Problemen met de Chinese en Japanse versie van HoloLens moeten op dezelfde manier worden gerapporteerd.

> [!NOTE]
> Zorg ervoor dat u de prompt accepteert waarin wordt gevraagd of u Feedback-hub documenten wilt openen (selecteer **Ja** wanneer u hier om wordt gevraagd).

## <a name="note-for-developers"></a>Opmerking voor ontwikkelaars

U bent welkom en aangemoedigd om uw toepassingen te ontwikkelen met insider-builds van HoloLens.  Bekijk de documentatie [HoloLens ontwikkelaars om](https://developer.microsoft.com/windows/mixed-reality/development) aan de slag te gaan. Dezelfde instructies werken met Insider-builds van HoloLens.  U kunt dezelfde builds van Unity en Visual Studio die u al gebruikt voor HoloLens ontwikkeling.

## <a name="stop-receiving-insider-builds"></a>Ontvangst van Insider-builds stoppen

Als u geen Insider-builds van Windows Holographic meer wilt ontvangen, kunt u zich uitloggen wanneer uw [](hololens-recovery.md) HoloLens een productie-build wordt uitgevoerd. U kunt uw apparaat ook herstellen met behulp van advanced recovery companion om uw apparaat te herstellen naar een niet-Insider-versie van Windows Holographic.

> [!CAUTION]
> Er is een bekend probleem waarbij gebruikers die de registratie van Insider Preview-builds ongedaan maken nadat ze handmatig een nieuwe preview-build hebben geïnstalleerd, een blauw scherm krijgen. Daarna moeten ze hun apparaat handmatig herstellen. Bekijk meer over dit bekende probleem voor meer informatie over of u hier al dan niet [mee te maken zou krijgen.](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)

Controleren of op uw HoloLens een productie-build wordt uitgevoerd:

1. Ga naar **Instellingen > System > About** en zoek het buildnummer.

1. [Zie de releasenotities voor productie-buildnummers.](hololens-release-notes.md)

Als u zich wilt af melden voor Insider-builds:

1. Ga op HoloLens met een productie-build naar Instellingen > **Update & Security > Windows Insider-programma** en selecteer Stop Insider **builds.**

1. Volg de instructies om uw apparaat uit te kiezen.
