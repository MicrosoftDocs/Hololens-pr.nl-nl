---
title: HoloLens 2 opmerkingen bij de release
description: Blijf op de hoogte van alle updates in elke nieuwe HoloLens 2 release.
author: scooley
ms.author: scooley
manager: laurawi
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/12/2021
ms.custom:
- CI 111456
- CSSTroubleshooting
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: 3f5e5f3e38c24805935fc69dfacd5eac93ddd017
ms.sourcegitcommit: 19d1abb7589cebf14ba45e830f49224f7b4fcfe9
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/15/2021
ms.locfileid: "130034277"
---
# <a name="hololens-2-release-notes"></a>HoloLens 2 opmerkingen bij de release

Om ervoor te zorgen dat u een productieve ervaring HoloLens uw apparaten, blijven we functies, fouten en beveiligingsupdates vrijgeven. Op deze pagina kunt u elke maand zien wat er nieuw is HoloLens nieuwe functies. Als u de meest recente HoloLens 2 update wilt downloaden, kunt u controleren op [updates](hololens-update-hololens.md#check-for-updates-and-manually-update) en handmatig bijwerken of de FFU (Full Flash Update) downloaden om uw apparaat te flashen [via Advanced Recovery Companion](hololens-recovery.md#clean-reflash-the-device). De [download](https://aka.ms/hololens2download) wordt up-to-date gehouden en biedt de meest recente algemeen beschikbare build.

> [!NOTE]
> De recente Windows 11 was gericht op de pc-versie van Windows. We hebben in oktober [2021](#windows-holographic-version-21h2)een belangrijke update voor het besturingssysteem HoloLens 2 uitgebracht en we werken aan nieuwe releases op basis van feedback van klanten.

## <a name="windows-holographic-version-21h2"></a>Windows Holographic, versie 21H2

- Build 20348.1432

Windows Holographic versie 21H2 is nu beschikbaar en biedt een groot aantal nieuwe functies voor HoloLens 2 en IT-professionals. Dit gaat over de verbeterde probleemoplossing en apparaatrapporten, enkele opgeloste fouten in de kioskmodus en de certificaatviewer, het uitgebreide beheerbaarheidsoppervlak en de verbeterde betrouwbaarheid van updates. Een nieuwe functie van deze functie-update die binnenkort beschikbaar HoloLens is onze platformmodus voor verplaatsen. Bekijk alle nieuwe geweldige functies voor HoloLens 2.

Deze meest recente versie is een maandelijkse update naar versie 21H1, maar deze keer nemen we nieuwe functies op. Hierdoor blijft het nummer van de grote build hetzelfde en geeft Windows Update een maandelijkse release naar versie 21H1 (build 20348) aan. HoloLens 2 instellingen worden nog steeds 21H1 weergegeven, ook al verwijzen we naar deze release als 21H2. Controleer of het versienummer 20348.1432 of hoger is om ervoor te zorgen dat u 21H2 hebt ontvangen. U kunt uw buildnummer bekijken in uw Instellingen > Scherm Over om te bevestigen dat u de nieuwste beschikbare build 20348.1432+ hebt.

Als u wilt bijwerken naar de nieuwste versie, opent u de Instellingen app, gaat u naar Update & Security en tikt u op Controleren op updates. Ga voor meer informatie over het beheren van HoloLens updates [naar HoloLens beheren.](hololens-updates.md)

| Functie                 | Beschrijving                | Gebruiker of scenario |
|-------------------------|----------------------------|--------------|
| [Platformmodus verplaatsen](#moving-platform-mode) | Introduceert de bètaversie van de moving platformmodus, die, wanneer deze is geconfigureerd, het gebruik van HoloLens 2 mogelijk maakt op grote zeepaden die te maken hebben met weinig dynamische beweging. | Alles |
| [Ondersteuning van PFX-bestanden voor Certificaatbeheer](#pfx-file-support-for-certificate-manager) | PFX-certificaten toevoegen via Instellingen UI | Eindgebruiker |
| [Geavanceerd diagnostisch rapport weergeven in Instellingen op HoloLens](#view-advanced-diagnostic-report-in-settings-on-hololens) | MDM-logboeken met diagnostische gegevens op het apparaat weergeven | Problemen oplossen |
| [Offline diagnostische meldingen](#offline-diagnostics-notifications) | Feedback geven over het verzamelen van logboeken | Problemen oplossen |
| [Verbeteringen in de verzameling met logboeken met weinig opslag](#low-storage-log-collection-improvements) | Verbeteringen in scenario's voor logboekverzameling tijdens situaties met weinig opslag. | Problemen oplossen |
| [CSP-wijzigingen voor rapportagegegevens HoloLens details](#csp-changes-for-reporting-hololens-details) | Nieuwe CSP's om query's uit te voeren op gegevens | IT-beheerders    |
| [Beleid voor automatisch aanmelden beheerd door CSP](#auto-login-policy-controlled-by-csp) | Wordt gebruikt om automatisch aan te melden bij een account | IT-beheerders |
| [Verbeterde detectie en meldingen voor opnieuw opstarten van updates](#improved-update-restart-detection-and-notifications) | Nieuw ingeschakeld beleid en UX voor updates. | IT-beheerders |
| [Slim opnieuw proberen voor app-updates](#smart-retry-for-app-updates) | Hiermee kunnen IT-beheerders geplande nieuwe proberen bij te werken apps. | IT-beheerders |
| [Alleen persoonlijke Store-apps gebruiken voor Microsoft Store](#use-only-private-store-apps-for-microsoft-store) | De Store-app configureren om alleen apps van de organisatie weer te geven | IT-beheerder |
| [WDAC- en LOB-apps gebruiken](#use-wdac-and-lob-apps) | Hiermee kunnen IT-beheerders hun eigen apps gebruiken en nog steeds WDAC gebruiken om andere apps te blokkeren. | IT-beheerders |
| [Oplossingen en verbeteringen](#fixes-and-improvements) | Oplossingen en verbeteringen voor HoloLens. | Alles |

### <a name="it-admin-feature-checklist"></a>Controlelijst voor IT-beheerfunctie

✔️ Als u één Azure AD-account wilt instellen om automatisch aan te melden, configureert u [deze nieuwe CSP.](#auto-login-policy-controlled-by-csp) <br>
✔️ als u uw apps zo wilt configureren dat deze automatisch proberen bij te werken nadat het bijwerken is mislukt, stelt u deze nieuwe CSP in [voor slim opnieuw proberen.](#smart-retry-for-app-updates) <br>
✔️ Als u meer controle wilt over updates van het besturingssysteem, bekijkt u deze zojuist [ingeschakelde updatebeleidsregels.](#improved-update-restart-detection-and-notifications) <br>
✔️ Als u de apps van uw organisatie beschikbaar wilt maken in de store van uw bedrijf via de Microsoft Store, maar alleen toegang wilt toestaan tot de apps van uw organisatie en niet de volledige Store, stelt u dit beleid [in.](#use-only-private-store-apps-for-microsoft-store) <br>
✔️ Als u de vrije opslagruimte, SSID of BSSID van uw HoloLens wilt weten, bekijkt u deze [rapportage-CSP's.](#csp-changes-for-reporting-hololens-details) <br>
✔️ Als u WDAC wilt gebruiken om het starten van apps of processen te blokkeren, maar ook uw eigen line-of-iness-apps wilt gebruiken, kunt u lob nu toestaan in uw [WDAC-beleid.](#use-wdac-and-lob-apps)

### <a name="moving-platform-mode"></a>Platformmodus verplaatsen

Vanaf Windows [Holographic, versie 21H2,](hololens-release-notes.md#windows-holographic-version-21h2) is bètaondersteuning toegevoegd voor het bijhouden van laag dynamische bewegingsplatforms op HoloLens 2. Nadat u de build hebt geïnstalleerd en de Moving Platform-modus hebt inschakelen, kunt u uw HoloLens 2 gebruiken in eerder ontoegankelijke omgevingen, zoals grote zee- en zeeplatforms. Op dit moment is de functie gericht op het inschakelen van deze specifieke platformen voor verplaatsen. Hoewel niets u verhindert om de functie in andere omgevingen te gebruiken, is de functie gericht op het toevoegen van ondersteuning voor deze omgevingen.

Ga naar de pagina voor het verplaatsen van platformen voor meer informatie over wat wordt ondersteund en hoe u deze nieuwe functie [kunt inschakelen.](hololens2-moving-platform.md)

#### <a name="overview-to-try-out-moving-platform-mode"></a>Overzicht van het uitproberen van de platformmodus voor verplaatsen

1. [Schakel de ontwikkelaarsmodus en de apparaatportal in.](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)
1. [Schakel de platformmodus verplaatsen in via De apparaatportal.](hololens2-moving-platform.md#enabling-moving-platform-mode)
1. Ga met uw apparaat naar uw grote bewegende platform en kijk hoe stabiel hologrammen zijn.

### <a name="pfx-file-support-for-certificate-manager"></a>Ondersteuning van PFX-bestanden voor Certificaatbeheer

Geïntroduceerd in Windows Insider-build 20348.1405. Er is nu ondersteuning toegevoegd aan [Certificaatbeheer om PFX-certificaten](certificate-manager.md) te gebruiken. Wanneer gebruikers naar het **Instellingen** Bijwerken & beveiligingscertificaten gaan en Een certificaat installeren selecteren, ondersteunt de gebruikersinterface nu  >    >  pfx-certificaatbestand. 
Gebruikers kunnen een PFX-certificaat met een persoonlijke sleutel importeren in een gebruikers- of machineopslag.

#### <a name="overview-to-try-out-pfx-files-in-certificate-manager"></a>Overzicht voor het uitproberen van PFX-bestanden in Certificate Manager

1. Bereid uw PFX-bestand voor.
1. Kopieer het bestand naar uw apparaat via een USB-C-kabel.
1. Open de Instellingen app, navigeer naar [Certificaatbeheer](certificate-manager.md) en pas het certificaat toe.

### <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a>Geavanceerd diagnostisch rapport weergeven in Instellingen op HoloLens

Voor beheerde apparaten bij het oplossen van problemen is het bevestigen dat een verwachte beleidsconfiguratie wordt toegepast een belangrijke stap. Voorheen moest dit voor deze nieuwe functie buiten het apparaat worden gedaan via MDM of in de buurt van het apparaat na het exporteren van diagnostische MDM-logboeken die zijn verzameld via  ->  **Instellingen-accounts** Toegang tot werk of  >  **school,** en selecteert u **Uw beheerlogboeken** exporteren en weergeven op een pc in de buurt.

De MDM-diagnostische gegevens kunnen nu worden weergegeven op het apparaat met behulp van de Edge-browser. Als u het diagnostischE MDM-rapport eenvoudiger wilt weergeven, gaat u naar de pagina Werk of school openen en **selecteert u Geavanceerd diagnostisch rapport weergeven.** Hiermee wordt het rapport gegenereerd en geopend in een nieuw Edge-venster.

![Bekijk het geavanceerde diagnostische rapport in Instellingen app.](./images/view-advanced-diagnostic-report.jpg)

#### <a name="overview-to-try-out-the-advanced-diagnostic-report"></a>Overzicht om het geavanceerde diagnostische rapport uit te proberen

1. Open de app Instellingen.
1. Navigeer naar de pagina Accounts en klik op de nieuwe koppeling **Uw beheerlogboeken exporteren.**
1. Bekijk geavanceerde informatie over de configuraties van uw apparaat.

### <a name="offline-diagnostics-notifications"></a>Offline diagnostische meldingen

Dit is een update voor een bestaande functie met de [naam Offlinediagnose.](hololens-diagnostic-logs.md#offline-diagnostics) Voorheen was er geen duidelijke indicator voor gebruikers dat ze de diagnostische verzameling hadden geactiveerd of dat deze was voltooid.
Nu toegevoegd in [Windows Holographic, versie 21H2,](hololens-release-notes.md#windows-holographic-version-21h2)zijn er twee vormen van feedback over offlinediagnose. De eerste zijn pop-upmeldingen die worden weergegeven voor zowel wanneer de verzameling wordt gestart als voltooid. Deze worden weergegeven wanneer de gebruiker is aangemeld en visuals heeft.

![Pop-up voor het verzamelen van logboeken.](./images/logcollection1.jpg)

![Pop-up wanneer het verzamelen van logboeken is voltooid.](./images/logcollection2.jpg)

Omdat gebruikers vaak offlinediagnose gebruiken als mechanisme voor het verzamelen van terugvallogboeken wanneer ze geen toegang hebben tot een weergave, zich niet kunnen aanmelden of zich nog steeds in OOBE kunnen aanmelden, wordt er ook een audio-cue afgespeeld wanneer logboeken worden verzameld. Dit geluid wordt afgespeeld naast de pop-upmelding.

Deze nieuwe functie wordt ingeschakeld wanneer uw apparaat wordt bijgewerkt en hoeft niet te worden ingeschakeld of beheerd. In elk geval dat deze nieuwe feedback niet kan worden weergegeven of gehoord, wordt offlinediagnose nog steeds gegenereerd.

We hopen dat het met deze nieuwere toevoeging van feedback gemakkelijker is om diagnostische gegevens te verzamelen en sneller in staat te zijn om uw problemen op te lossen.

Deze informatie kan later worden weergegeven op de pagina [met diagnostische logboeken.](hololens-diagnostic-logs.md#offline-diagnostics)

#### <a name="overview-to-try-out-the-diagnostics-notifications"></a>Overzicht om de diagnostische meldingen uit te proberen

1. Ontgrendel uw apparaat en draag het.
1. Druk op de **combinatie van de** knop **Aan/uit** en volume omlaag om [offlinediagnose te verzamelen.](hololens-diagnostic-logs.md#offline-diagnostics)
1. Bekijk de pop-upmeldingen en horen audio aanwijzingen voor wanneer uw apparaat wordt gestart en klaar is met het verzamelen van logboeken.

### <a name="low-storage-log-collection-improvements"></a>Verbeteringen in de verzameling met logboeken met weinig opslag

In scenario's waarin een apparaat weinig schijfruimte lijkt te hebben wanneer diagnostische logboeken worden verzameld, wordt **er een extra** rapport met deStorageDiagnostics.zipgemaakt. De drempelwaarde voor lage opslag wordt automatisch bepaald door de Windows [opslag te bepalen.](https://support.microsoft.com/office/use-onedrive-and-storage-sense-in-windows-10-to-manage-disk-space-de5faa9a-6108-4be1-87a6-d90688d08a48)

Deze informatie kan later worden weergegeven op de pagina [met diagnostische logboeken.](hololens-diagnostic-logs.md#offline-diagnostics)

#### <a name="overview-to-try-out-the-low-storage-improvements"></a>Overzicht van het uitproberen van de verbeteringen in de lage opslag

1. Vul de opslagruimte van uw apparaat in.
1. Druk op de **combinatie van de** knop **Aan/uit** en volume omlaag om [offlinediagnose te verzamelen.](hololens-diagnostic-logs.md#offline-diagnostics)
1. U ziet dat er een nieuw bestand in de verzameling logboeken is opgeslagen in de map Documenten van uw HoloLens.

### <a name="csp-changes-for-reporting-hololens-details"></a>CSP-wijzigingen voor rapportagegegevens HoloLens details

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

Wanneer het beleid is ingesteld op een niet-lege waarde, wordt het e-mailadres van de gebruiker voor automatische aanmelding opgegeven. De opgegeven gebruiker moet zich ten minste één keer aanmelden bij het apparaat om automatische aanmelding in te kunnenschakelen.

De OMA-URI van nieuwe `./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser` beleidsreekswaarde

- De gebruiker met hetzelfde e-mailadres heeft automatische aanmelding ingeschakeld.

Op een apparaat waarop dit beleid is geconfigureerd, moet de gebruiker die is opgegeven in het beleid zich ten minste één keer aanmelden. Als het apparaat na de eerste aanmelding opnieuw wordt opgestart, wordt de opgegeven gebruiker automatisch aangemeld. Er wordt slechts één gebruiker voor automatische aanmelding ondersteund. Zodra deze is ingeschakeld, kan de automatisch aangemelde gebruiker zich niet meer handmatig afmelden. Als u zich als een andere gebruiker wilt aanmelden, moet het beleid eerst worden uitgeschakeld.

> [!NOTE]
>
> - Voor sommige gebeurtenissen, zoals belangrijke updates van het besturingssysteem, moet de opgegeven gebruiker zich mogelijk opnieuw bij het apparaat laten aanmeldingen om automatisch aanmeldingsgedrag te hervatten.
> - Automatische aanmelding wordt alleen ondersteund voor MSA- en AAD gebruikers.

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

Deze informatie vindt u later in de [pagina App Deployment Store voor Bedrijven.](app-deploy-store-business.md)

#### <a name="overview-to-try-smart-retry-for-app-updates"></a>Overzicht van het uitproberen van Slimme nieuwe poging voor app-updates

1. Configureer de nieuwe functie voor slim opnieuw proberen.
1. Meld u aan bij een online omgeving op een apparaat dat uw app nog niet heeft ontvangen en correct is geconfigureerd voor .
1. Zorg ervoor dat het apparaat de app niet kan downloaden door deze uit te schakelen of de verbinding te verbreken.
1. Laat uw apparaat ingeschakeld en verbonden zijn met internet tijdens het geactiveerde tijdstip om het downloaden opnieuw uit te proberen.

### <a name="use-only-private-store-apps-for-microsoft-store"></a>Alleen persoonlijke Store-apps gebruiken voor Microsoft Store

Het beleid RequirePrivateStoreOnly is ingeschakeld voor HoloLens. Met dit beleid kan de Microsoft Store-app zodanig worden geconfigureerd dat alleen de persoonlijke opslag wordt weer te geven die voor uw organisatie is geconfigureerd [via Microsoft Store voor Bedrijven](/microsoft-store/microsoft-store-for-business-overview). Beperk de toegang tot alleen de apps die u beschikbaar hebt gemaakt.

Meer informatie over [ApplicationManagement/RequirePrivateStoreOnly](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly)

Deze informatie vindt u later in de [pagina App Deployment Store voor Bedrijven.](app-deploy-store-business.md)

#### <a name="overview-to-try-only-private-store-apps"></a>Overzicht om alleen persoonlijke Store-apps te proberen

1. Configureer het nieuwe beleid voor uw apparaten via [MDM.](hololens-mdm-configure.md)
1. Meld u aan bij een apparaat met het beleid.
1. Open de Microsoft Store app en u ziet dat u alleen de apps van uw organisatie kunt zien.

### <a name="use-wdac-and-lob-apps"></a>WDAC- en LOB-apps gebruiken

U kunt nu WDAC gebruiken om te blokkeren dat apps of processen worden gelanceerd en uw eigen line-of-iness-apps blijven gebruiken. u kunt ze nu toestaan in uw WDAC-beleid. Als u dit beleid gebruikt, moet u een extra regel code uitvoeren in PowerShell bij het maken van uw WDAC-beleid. [Bekijk hier de stappen.](/mem/intune/configuration/custom-profile-hololens)

#### <a name="overview-to-try-your-own-apps-while-using-wdac-to-block-others"></a>Overzicht om uw eigen apps uit te proberen terwijl u WDAC gebruikt om anderen te blokkeren

1. Verzamel de AUMID's van uw LOB-app en de apps die u wilt blokkeren.
1. [Maak een nieuw WDAC-beleid door](/mem/intune/configuration/custom-profile-hololens) de nieuwe stappen te volgen.
1. [Implementeer het beleid met behulp van MDM](hololens-mdm-configure.md) op uw apparaat.
1. Meld u aan bij het apparaat en kijk of u uw app kunt starten en anderen kunt blokkeren.

### <a name="fixes-and-improvements"></a>Oplossingen en verbeteringen

#### <a name="for-developers"></a>Voor ontwikkelaars

- Er is [een bekend probleem opgelost voor Apparaatportal waarbij er geen prompt was om vergrendelde bestanden te downloaden.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)
- Er is [een bekend probleem opgelost voor Apparaatportal met time-outs](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)voor het uploaden en downloaden van bestanden.
- Verwerking van Gamepad voor 2D-apps is uitgeschakeld in Insider-builds. Door deze te verwijderen, kunnen apps nu rechtstreeks gebruikmaken van de Gamepad-API's en hebben ze toegang tot de hele set besturingselementen en kunnen ze worden ontwikkeld om meer te doen. Ontwikkelaars moeten de Gamepad-API's gebruiken om Gamepad-invoer te gebruiken. Hier is een voorbeeld voor [Gamepad-klasse (Windows. Gaming.Input) - Windows UWP-toepassingen](/uwp/api/windows.gaming.input.gamepad?view=winrt-20348&preserve-view=true).
- Een TOEGEWEZEN [toegangs-API](/uwp/api/windows.system.userprofile.assignedaccesssettings?view=winrt-20348&preserve-view=true) ingeschakeld, zodat apps nu kunnen bepalen of een HoloLens wordt uitgevoerd in een kioskmodus voor de gebruiker die is aangemeld bij de HoloLens.

#### <a name="for-enterprise"></a>Voor Enterprise

- Behandelt problemen met het rapporteren van nalevingseigenschappen van HoloLens apparaten; Mogelijk moet u opnieuw opstarten om de juiste rapportage te kunnen starten op Insider-builds.  
- De in-box-versie van Remote Assist bijgewerkt die is geïnstalleerd op nieuwe flashes.
- Er is een probleem opgelost waarbij OOBE na de eerste aanmelding van gebruikers werd beëindigd in scenario's waarin AAD kioskconfiguraties op basis van groepen werden gebruikt.
- Er is een probleem opgelost met het weergeven van updatemeldingen en dialoogvensterprompts om het apparaat opnieuw op te starten.
- Er is een probleem opgelost waarbij na het opnieuw opstarten van het apparaat Xbox Controllers en andere Bluetooth LE-randapparatuur opnieuw moesten worden gekoppeld om verbinding te maken.
- Probleem met video-encoder opgelost dat een korte stop van uitgaande video tijdens een Remote Assist veroorzaakt. Wi-Fi wijzigingen in stuurprogramma's en firmware om problemen met 'Fragment en Forge' Wi-Fi verhelpen.
- Wi-Fi wijzigingen in stuurprogramma's en firmware om problemen met 'Fragment en Forge' Wi-Fi verhelpen.
- Wanneer u de MPM (Moving Platform Mode) gebruikt, wordt 'Omlaag' geschat door de gemiddelde ernst gedurende een korte periode. Deze waarde vervangt de werkelijke ernst bij het verplaatsen van platformmodus.
- Periodieke wobble in hologrammen opgelost in de 3DoF-modus of tijdens het verlies van tracering.
- Lost een probleem op dat van invloed is op updates voor de 21H1/21H2-release van oudere releases.

## <a name="windows-holographic-version-20h2---october-2021-update"></a>Windows Holographic, versie 20H2 - update van oktober 2021

- Build 19041.1168

Verbeteringen en oplossingen in de update:

- Deze maandelijkse kwaliteitsupdate bevat geen belangrijke wijzigingen. We raden u aan onze nieuwste build, Windows Holographic, versie 21H2, uit te proberen.

## <a name="windows-holographic-version-21h1---september-2021-update"></a>Windows Holographic, versie 21H1 - Update van september 2021

- Build 20348.1018

Verbeteringen en oplossingen in de update:

- Oplossingen voor het oplossen van problemen waarbij de systeemtijd onverwacht kan snel gaan.

## <a name="windows-holographic-version-20h2---september-2021-update"></a>Windows Holographic, versie 20H2 - Update van september 2021

- Build 19041.1165

Verbeteringen en oplossingen in de update:

- Oplossingen voor het oplossen van problemen waarbij de systeemtijd onverwacht kan snel gaan.

## <a name="windows-holographic-version-21h1---august-2021-update"></a>Windows Holographic, versie 21H1 - update van augustus 2021

- Build 20348.1014

Verbeteringen en oplossingen in de update:

- Er is een probleem opgelost waardoor Xbox-controllers niet konden werken in in immersieve toepassingen met controllerondersteuning.
- Verbeterde diagnostische gegevens voor mislukte apparaatupdates.

## <a name="windows-holographic-version-20h2---august-2021-update"></a>Windows Holographic, versie 20H2 - update van augustus 2021

- Build 19041.1161

Verbeteringen en oplossingen in de update:

- Deze maandelijkse kwaliteitsupdate bevat geen belangrijke wijzigingen. We raden u aan onze nieuwste build, Windows Holographic, versie 21H1, uit te proberen.

## <a name="windows-holographic-version-21h1---july-2021-update"></a>Windows Holographic, versie 21H1 - update van juli 2021

- Build 20348.1010

Verbeteringen en oplossingen in de update:

- Apparaatportal heeft verbeterde methoden om de klant op de hoogte te stellen wanneer er problemen zijn met het openen van vergrendelde bestanden in Verkenner.
- Het uploaden, downloaden, hernoemen en verwijderen van bestanden is nu opgelost wanneer u https gebruikt in alle ondersteunde browsers.
- Er is een probleem opgelost waarbij Wi-Fi proxy niet kan worden opgeslagen wanneer de gebruikersinterface voor Wi-Fi-eigenschappen wordt gestart vanuit **Instellingen > Network & Internet > Status > Properties.**
- Er is een probleem opgelost met het verwijderen van eSIM-certificaten tussen besturingssysteemupdates. Deze oplossing zorgt ervoor dat de eSIM-certificaten en gerelateerde onderdelen worden verwijderd bij het bijwerken naar de 21H1-release.
- Er is een probleem opgelost dat van invloed was op vooraf geïnstalleerde apps in het opnieuw instellen van het besturingssysteem.
- Laadprestaties van accu's zijn afgestemd op het verhogen van de runtime bij het laden met verhoogde CPU-belasting. Als bij het HoloLens 2 apparaten wordt gedetecteerd dat het apparaat heet wordt, wordt de interne batterij langzamer op belast om de warmte te verminderen. Het positieve effect is dat een apparaat minder waarschijnlijk wordt afgesloten vanwege thermische problemen, met als gevolg dat het apparaat langer wordt uitgevoerd. Als het apparaat 'cool' wordt uitgevoerd, wordt het tarief niet beïnvloed.

> [!IMPORTANT]
> Vanwege een nu opgelost bekend probleem in onze [21H1-build](hololens-troubleshooting.md#remote-assist-video-freezes-after-20-minutes)dat van invloed was op Remote Assist-gebruikers, hebben we het aanbieden van Windows Holographic- versie 21H1-updates tijdelijk onderbroken. We hadden ook de standaard ARC-build (Advanced Recovery Companion) gewijzigd in [Windows Holographic, versie 20H2 - update van juni 2021.](hololens-release-notes.md#windows-holographic-version-20h2--june-2021-update) De ARC-build wordt nu hervat voor de 21H1-build.

## <a name="windows-holographic-version-20h2--july-2021-update"></a>Windows Holographic, versie 20H2 – update van juli 2021

- Build 19041.1157

Verbeteringen en oplossingen in de update:

- Apparaatportal heeft verbeterde methoden om de klant op de hoogte te stellen wanneer er problemen zijn met het openen van vergrendelde bestanden in Verkenner.
- Het uploaden, downloaden, hernoemen en verwijderen van bestanden is nu opgelost wanneer u https gebruikt in alle ondersteunde browsers.

## <a name="windows-holographic-version-21h1---june-2021-update"></a>Windows Holographic, versie 21H1 - update van juni 2021

- Build 20348.1007

### <a name="onedrive-for-work-or-school-camera-roll-upload"></a>OneDrive voor werk of school Camera Roll uploaden

We hebben een nieuwe functie toegevoegd aan de HoloLens 2 Instellingen-app, waarmee klanten automatisch mixed reality foto's en video's uit de map Afbeeldingen > Camera Roll van het apparaat kunnen uploaden naar de bijbehorende map OneDrive voor werk of school. Met deze functie wordt een functie-hiaat in de [OneDrive-app](holographic-photos-and-videos.md#share-your-mixed-reality-photos-and-videos) op HoloLens 2 vereend, die alleen ondersteuning biedt voor het automatisch uploaden van camera's naar de persoonlijke Microsoft-account van een klant (en niet naar het werk- of schoolaccount).

**Uitleg**

- Ga **naar Instellingen > System > Mixed reality-camera** om 'Camera uploaden' in teschakelen.
- Als u deze  functie instelt op De positie Aan, worden alle mixed reality-foto's of video's die op uw apparaat zijn vastgelegd, automatisch in de wachtrij geplaatst om te worden geüpload naar de map Afbeeldingen > Camera Roll van uw OneDrive voor werk- of schoolaccount.
    >[!NOTE]
    >Foto's video's die zijn vastgelegd  voordat u deze functie inschakelen, worden niet in de wachtrij geplaatst voor uploaden en moeten nog steeds handmatig worden geüpload.
- Een statusbericht op de pagina Instellingen geeft het aantal bestanden weer dat in behandeling is voor uploaden (of 'OneDrive is up-to-date' wanneer alle bestanden in behandeling zijn geüpload).
- Als u zich zorgen maakt over bandbreedte of de upload om een of andere reden wilt 'onderbreken', kunt u de functie overschakelen naar **de positie Uit.** Het tijdelijk uitschakelen van de functie zorgt ervoor dat de uploadwachtrij blijft toenemen wanneer u nieuwe bestanden toevoegt aan de map Camera Roll, maar bestanden worden pas geüpload wanneer u de functie opnieuw inschakelen.
- Nieuwste bestanden worden eerst geüpload (laatste in, eerste uit).
- Als uw OneDrive-account problemen heeft (bijvoorbeeld nadat uw  wachtwoord is gewijzigd), wordt de knop Nu herstellen weergegeven op de Instellingen pagina.
- Er is geen maximale bestandsgrootte, maar houd er rekening mee dat het uploaden van grote bestanden langer duurt (met name als uw uploadbandbreedte beperkt is). Als u het uploaden 'pauzeert' of uit zet terwijl een groot bestand wordt geüpload, blijft de gedeeltelijke upload behouden. Als het uploaden binnen enkele uren na het onderbreken of uitschakelen opnieuw is ingeschakeld, wordt het uploaden voortgezet vanaf de plek waar het was gebleven. Als het uploaden na enkele uren echter opnieuw is ingeschakeld, wordt het uploaden van het grote bestand vanaf het begin opnieuw gestart.

**Bekende problemen en waarschuwingen**

- Deze instelling heeft geen ingebouwde beperking op basis van het huidige bandbreedtegebruik. Als u de bandbreedte voor een ander scenario wilt maximaliseren, moet u de instelling handmatig uitschakelen. Upload worden onderbroken, maar de functie blijft nieuw toegevoegde bestanden aan Camera Roll bewaken. Schakel uploaden opnieuw in wanneer u klaar bent om door te gaan.
- Deze functie moet zijn ingeschakeld voor elk gebruikersaccount op het apparaat en kan alleen actief bestanden uploaden voor de gebruiker die momenteel is aangemeld bij het apparaat.
- Als u foto's of video's maakt tijdens het in realtime bekijken van het aantal uploads op de pagina Instellingen, moet u er rekening mee houden dat het aantal in behandeling zijnde bestanden mogelijk niet verandert totdat het uploaden van het huidige bestand is voltooid.
- Upload wordt onderbroken als uw apparaat in de slaapstand valt of wordt uitgeschakeld. Om ervoor te zorgen dat de uploads in behandeling zijn voltooid, gebruikt u het apparaat actief totdat op de Instellingen-pagina de tekst 'OneDrive is up-to-date' wordt weergegeven of uw **Power &-slaapstandinstellingen.**

### <a name="added-support-for-some-telemetry-policies"></a>Ondersteuning toegevoegd voor bepaalde telemetriebeleidsregels

De volgende telemetriebeleidsregels worden nu ondersteund op de HoloLens 2:

- ConfigureTelemetryOptInSettingsUx
- DisableDeviceDelete
- AllowDeviceNameInDiagnosticData
- FeedbackHubAlwaysSaveDiagnosticsLocally

Zowel System\AllowTelemetry als System\ConfigureTelemetryOptInSettingsUx moeten samen worden gebruikt om volledige controle te hebben over de telemetrie en het gedrag in de Instellingen app.

Verbeteringen en oplossingen in de update:

- Herstelt belangrijke beschadiging van video's met Color-kalibratie.
- Lost een probleem op waarbij tekst kan worden afgekapt in het power-menu.
- Hiermee schakelt u ondersteuning in voor het beleid RequirePrivateStoreOnly.

## <a name="windows-holographic-version-20h2--june-2021-update"></a>Windows Holographic, versie 20H2 – update van juni 2021

- Build 19041.1154

### <a name="added-support-for-some-telemetry-policies"></a>Ondersteuning toegevoegd voor een aantal telemetriebeleidsregels

De volgende telemetriebeleidsregels worden nu ondersteund op HoloLens 2:

- ConfigureTelemetryOptInSettingsUx
- DisableDeviceDelete
- AllowDeviceNameInDiagnosticData
- FeedbackHubAlwaysSaveDiagnosticsLocally

Zowel System\AllowTelemetry als System\ConfigureTelemetryOptInSettingsUx moeten samen worden gebruikt om volledige controle te hebben over de telemetrie en het gedrag in de Instellingen app.

We raden u aan onze nieuwste build, Windows Holographic versie 21H1, uit te proberen.

## <a name="windows-holographic-version-1903---june-2021-update"></a>Windows Holographic, versie 1903 - update van juni 2021

- Build 18362.1116

Verbeteringen en oplossingen in de update:

- Deze maandelijkse kwaliteitsupdate bevat geen belangrijke wijzigingen. We raden u aan onze nieuwste build, Windows Holographic, versie 21H1, uit te proberen.

>[!IMPORTANT]
> Deze build wordt niet meer gebruikt.

## <a name="windows-holographic-version-21h1"></a>Windows Holographic, versie 21H1

- Build 20346.1002

Deze update bevat functies voor twee doelgroepen; functies die door iedereen op een apparaat kunnen worden gebruikt door de eindgebruiker en nieuwe opties voor apparaatbeheer die kunnen worden geconfigureerd door IT-beheerders. In de onderstaande tabel worden de functies opgegeven die relevant zijn voor elke doelgroep. Als u een IT-beheerder bent, raadpleegt u onze controlelijst voor [IT-beheerders - Bijwerken.](#it-admin---update-checklist)
>[!IMPORTANT]
>Als u wilt bijwerken naar deze build, HoloLens 2 op een of meer apparaten momenteel de update van februari 2021 (build 19041.1136) of nieuwer worden uitgevoerd. Als u deze functie-update niet beschikbaar ziet, moet u eerst uw apparaat bijwerken en het opnieuw proberen.

>[!NOTE]
>Momenteel ondersteunt Microsoft HoloLens 2 maandelijkse onderhoudsupdates (bug- en beveiligingsfixes) voor de volgende releases:
>
>- Windows Holographic, versie 20H2 (build 19041.1128+)
>- Windows Holographic, versie 2004 (build 19041.1103+)
>- Windows Holographic, versie 1903 (build 18362+)
>
> Met de introductie Windows Holographic-versie 21H1, worden er maandelijkse onderhoudsupdates voor Windows **Holographic-versie 1903.** Hierdoor kunnen we ons richten op recentere releases en waardevolle verbeteringen blijven leveren.

| Functienaam                                              | Korte beschrijving                                                                      | Doelgroep |
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|
| [Nieuwe Microsoft Edge](#introducing-the-new-microsoft-edge)  | De nieuwe, Chromium gebaseerde Microsoft Edge is nu beschikbaar voor HoloLens 2. | Eindgebruiker |
[WebXR en 360 Viewer](#webxr-and-360-viewer) | Probeer immersive web experiences en 360 video's af te spelen. | Eindgebruiker |
[Nieuwe Instellingen app](#new-settings-app) | De verouderde Instellingen-app wordt vervangen door een bijgewerkte versie met nieuwe functies en instellingen. | Eindgebruiker |
[Kalibratie van kleur weergeven](#display-color-calibration) | Selecteer een alternatief kleurprofiel voor uw HoloLens 2 weergave. | Eindgebruiker |
[Standaard app- kiezen](#default-app-picker) | Kies welke app moet worden gebruikt voor elk bestands- of koppelingstype. | Eindgebruiker |
[Volumebeheer per app](#per-app-volume-control) | Beheer het volume op app-niveau onafhankelijk van het systeemvolume. | Eindgebruiker |
[Web-apps installeren](#install-web-apps) | Installeer web-apps op HoloLens 2, zoals Microsoft Office, met de nieuwe Microsoft Edge browser. | Eindgebruiker |
[Veeg om te typen](#swipe-to-type) | Gebruik de punt van uw vinger om woorden op het holografische toetsenbord te 'swipen'. | Eindgebruiker |
[Aan/uit-menu vanaf het startmenu](#power-menu-from-start) | Start het startmenu opnieuw op en sluit het HoloLens af. | Eindgebruiker |
[Meerdere gebruikers die worden vermeld op het aanmeldingsscherm](#multiple-users-listed-on-sign-in-screen) | Meerdere gebruikersaccounts weergeven op het scherm Aanmelden. | Eindgebruiker |
[Ondersteuning voor externe USB-C-microfoon](#usb-c-external-microphone-support) | USB-C-microfoons gebruiken voor apps en/of Remote Assist. | Eindgebruiker |
[Automatische aanmelding van bezoekers voor kiosken](#visitor-auto-logon-for-kiosks) | Hiermee schakelt u in dat de automatische aanmelding bij bezoekersaccounts kan worden gebruikt voor kioskmodi. | IT-beheerder |
[Nieuwe AUMID's voor nieuwe apps in kioskmodus](#use-the-new-settings-and-edge-apps-in-kiosk-modes)  | AUMID's voor nieuwe Instellingen edge-apps. | IT-beheerder |
[Verbeterde fout bij het in de kioskmodus geven](#kiosk-mode-behavior-changes-for-handling-of-failures) | De kioskmodus zoekt naar Algemene toegewezen toegang voordat het menu Start leeg is. | IT-beheerder |
[Nieuwe InstellingenURI's voor Instellingen zichtbaarheid](#new-settings-uris-for-page-settings-visibility) | Meer dan 20 nieuwe SettingsURIs voor Instellingen/PageVisibilityList-beleid. | IT-beheerder |
[Terugvaldiagnose configureren](#configuring-fallback-diagnostics-via-settings-app) | Terugvaldiagnosegedrag instellen in Instellingen app. | IT-beheerder |
[Dingen delen met apparaten in de buurt](#share-things-with-nearby-devices) | Bestanden of URL's van een HoloLens naar een pc. | Alles |
[Nieuwe diagnostische traceringen van het besturingssysteem](#new-os-diagnostic-traces) | Nieuwe probleemoplosser in Instellingen voor updates van het besturingssysteem. | IT-beheerder |
[Delivery Optimization Preview](#delivery-optimization-preview) | Verminder het bandbreedteverbruik voor downloads vanaf meerdere HoloLens apparaten. | IT-beheerder |

Bekijk de gerelateerde opmerkingen bij de release:

- [Ga naar HoloLens Emulator archief](/windows/mixed-reality/hololens-emulator-archive)
- [Dynamics 365 Remote Assist](/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)
- [Dynamics 365 Guides](/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)

### <a name="introducing-the-new-microsoft-edge"></a>Introductie van de nieuwe Microsoft Edge

![Animatie van het verouderde Microsoft Edge logo naar het nieuwe Microsoft Edge logo.](images/new-edge.gif)

De nieuwe Microsoft Edge maakt gebruik van [het Chromium open source-project](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) voor betere compatibiliteit voor klanten en minder fragmentatie van het web voor webontwikkelaars.

> [!IMPORTANT]
> Deze nieuwe Microsoft Edge vervangt automatisch verouderde Microsoft Edge, die [niet meer wordt ondersteund](https://blogs.windows.com/msedgedev/2021/03/09/microsoft-edge-legacy-end-of-support/) in nieuwe releases.

![Schermopname Microsoft Edge nieuwe versie.](images/new-edge-ui.png)

#### <a name="launching-the-new-microsoft-edge"></a>De nieuwe Microsoft Edge

De nieuwe Microsoft Edge ![pictogram Microsoft Edge nieuwe versie.](images/new_edge_logo.png) (vertegenwoordigd door een blauw en groen pictogram) wordt vastgemaakt aan de Startmenu en wordt automatisch geactiveerd wanneer u een webkoppeling activeert.

> [!NOTE]
> Wanneer u de nieuwe Microsoft Edge op HoloLens 2 start, worden uw instellingen en gegevens geïmporteerd uit verouderde Microsoft Edge. Als u verouderde Microsoft Edge blijft gebruiken na het starten van de nieuwe Microsoft Edge, worden die nieuwe gegevens niet gesynchroniseerd van verouderde Microsoft Edge naar de nieuwe Microsoft Edge.

#### <a name="configuring-policy-settings-for-the-new-microsoft-edge"></a>Beleidsinstellingen configureren voor de nieuwe Microsoft Edge

De nieuwe Microsoft Edge biedt IT-beheerders een veel bredere set browserbeleidsregels op HoloLens 2 dan voorheen beschikbaar waren met verouderde Microsoft Edge.

Hier vindt u nuttige informatiebronnen voor meer informatie over het beheren van beleidsinstellingen voor de nieuwe Microsoft Edge:

- [Uw Microsoft Edge configureren met Microsoft Intune](/deployedge/configure-edge-with-intune)
- [Microsoft Edge (oudere versie) om Microsoft Edge te maken](/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [Google Chrome voor het Microsoft Edge van beleid](/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- Volledige [Microsoft Edge Enterprise-documentatie](/deployedge/)

> [!IMPORTANT]
> Vanwege het grote aantal browserbeleidsregels dat door de nieuwe Microsoft Edge wordt ondersteund, kan ons team niet garanderen dat elk nieuw beleid op deze HoloLens 2. We hebben echter getest en bevestigd dat de nieuwe Microsoft Edge equivalent is van elk verouderd Microsoft Edge-beleid dat eerder werd ondersteund op HoloLens 2 zoals verwacht. Zie Microsoft Edge (oudere versie) voor [Microsoft Edge-toewijzing](/deployedge/microsoft-edge-policy-map-legacy-to-newedge) van beleid om de nieuwe Microsoft Edge-equivalent te vinden van elk verouderd Microsoft Edge-browserbeleid dat u gebruikte met HoloLens 2.
>
> Er zijn ten minste twee nieuwe Microsoft Edge beleidsregels die niet *werken* met HoloLens 2:
>
> - EnterpriseModeSiteList
> - EnterpriseSiteListServiceURL

#### <a name="what-to-expect-from-the-new-microsoft-edge-on-hololens-2"></a>Wat u kunt verwachten van de nieuwe Microsoft Edge op HoloLens 2

Omdat de nieuwe Microsoft Edge een native Win32-app is met een nieuwe UWP-adapterlaag zodat deze kan worden uitgevoerd op UWP-apparaten zoals HoloLens 2, zijn sommige functies mogelijk niet onmiddellijk beschikbaar. In de komende maanden zullen we nieuwe scenario's en functies ondersteunen, dus controleer deze ruimte op actuele informatie.

**Scenario's en functies werken naar verwachting:**

- Eerste ervaring, aanmelden bij profiel en synchroniseren
- Websites moeten worden weergegeven en gedragen zoals verwacht
- De meeste browserfunctionaliteit (favorieten, geschiedenis, enzovoort) werkt zoals verwacht
- Donkere modus
- Web-apps installeren op het apparaat
- Extensies installeren (laat het ons weten als u extensies gebruikt die niet goed werken op HoloLens 2)
- Een PDF weergeven en markeren
- Ruimtelijk geluid vanuit één browservenster
- Automatisch en handmatig bijwerken van de browser
- Een PDF opslaan in het menu Afdrukken (met behulp van de optie Opslaan in PDF)
- WebXR en 360 Viewer-extensie
- Inhoud herstellen naar het juiste venster wanneer u door meerdere vensters bladert die in uw omgeving zijn geplaatst

**Scenario's en functies werken naar verwachting niet:**

- Ruimtelijk geluid van meerdere vensters met gelijktijdige audiostreams
- "See it, say it"
- Afdrukken

**Meest bekende problemen met de browser:**

- De preview-versie van de vergrootglas in het holografische toetsenbord is uitgeschakeld voor de nieuwe Microsoft Edge. We hopen deze functie in een toekomstige update opnieuw in te kunnen stellen zodra de functie correct werkt.
- Audio kan worden afspelen vanuit het verkeerde browservenster als u een ander browservenster hebt geopend en actief hebt. U kunt dit probleem oplossen door het andere actieve venster te sluiten dat geen audio mag afspelen.
- Wanneer u audio afspelen vanuit een browservenster in de modus Volg [me,](hololens2-basic-usage.md#follow-me-stop-following)blijft de audio afspelen als u de modus Volg mij uit schakelen. U kunt dit probleem oplossen door het afspelen van audio te stoppen voordat u de modus Volg mij uitsluit of door het venster te sluiten met de **X-knop.**
- Interactie met actieve Microsoft Edge kan ertoe leiden dat andere 2D-appvensters onverwacht inactief worden. U kunt deze vensters opnieuw activeren door er opnieuw mee te werken.

#### <a name="microsoft-edge-insider-channels"></a>Microsoft Edge Insider-kanalen

Het Microsoft Edge team maakt drie preview-kanalen beschikbaar voor de Edge Insider-community: Beta, Dev en Canary. Als u een preview-kanaal installeert, wordt de uitgebrachte versie van Microsoft Edge niet verwijderd op uw HoloLens 2 en kunt u er meer dan één tegelijk installeren.

Ga naar [de Microsoft Edge Insider voor](https://www.microsoftedgeinsider.com) meer informatie over de Edge Insider-community. Ga naar de edge [Insider-downloadpagina](https://www.microsoftedgeinsider.com/download)voor meer informatie over de verschillende Edge Insider-kanalen en om aan de slag te gaan.

Er zijn een aantal methoden beschikbaar voor het installeren van Microsoft Edge Insider-kanalen om HoloLens 2:

**Directe installatie op apparaat (momenteel alleen beschikbaar voor niet-mande apparaten)**

  1. Ga op HoloLens 2 naar de [edge Insider-downloadpagina.](https://www.microsoftedgeinsider.com/download)
  1. Selecteer de **knop Downloaden HoloLens 2** voor het Edge Insider-kanaal dat u wilt installeren.
  1. Start het gedownloade MSIX-bestand vanuit de Edge-downloadwachtrij of vanuit de map Downloads van uw apparaat (met behulp van Verkenner).
  1. [Het app-installatieprogramma](app-deploy-app-installer.md) wordt starten.
  1. Selecteer de **knop** Installeren.
  1. Nadat de installatie is geslaagd, vindt u Microsoft Edge Beta, Dev of Canary als een afzonderlijke vermelding in de **Alle apps** lijst van de Startmenu.

**Installeren via pc met Windows Apparaatportal (hiervoor moet [de](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) ontwikkelaarsmodus zijn ingeschakeld op HoloLens 2)**

  1. Ga op uw pc naar de [Edge Insider-downloadpagina.](https://www.microsoftedgeinsider.com/download)
  1. Selecteer de **vervolgkeuzepijl** naast de knop Downloaden voor Windows 10 voor het Edge Insider-kanaal dat u wilt installeren.
  1. Selecteer **HoloLens 2** in de vervolgkeuzelijst.
  1. Sla het MSIX-bestand op in de map Downloads van uw pc (of een andere map die u gemakkelijk kunt vinden).
  1. Gebruik [Windows Apparaatportal](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) op uw pc om het gedownloade MSIX-bestand te installeren op HoloLens 2.
  1. Nadat de installatie is geslaagd, vindt u Microsoft Edge Beta, Dev of Canary als een afzonderlijke vermelding in de **Alle apps** lijst van de Startmenu.

#### <a name="using-wdac-to-block-new-microsoft-edge"></a>WDAC gebruiken om nieuwe Microsoft Edge

IT-beheerders die hun [WDAC-beleid](windows-defender-application-control-wdac.md) willen bijwerken om de nieuwe Microsoft Edge-app te blokkeren, moeten het volgende toevoegen aan uw beleid.

``` <Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" /> ```

#### <a name="managing-endpoints-for-the-new-microsoft-edge"></a>Eindpunten voor de nieuwe Microsoft Edge

Sommige omgevingen hebben mogelijk netwerkbeperkingen om rekening mee te houden als overweging. Schakel deze Microsoft-eindpunten in om een soepele ervaring met de nieuwe [Edge te garanderen.](/deployedge/microsoft-edge-security-endpoints)

Lees meer over de momenteel beschikbare [eindpunten voor HoloLens](hololens-offline.md).

### <a name="install-web-apps"></a>Web-apps installeren

 > [!Note]
>Vanaf Windows [Holographic, versie 21H1,](hololens-release-notes.md#windows-holographic-version-21h1)wordt de Office web-app niet meer vooraf geïnstalleerd.

U kunt de nieuwe Edge gebruiken om web-apps te installeren naast Microsoft Store apps. U kunt bijvoorbeeld de web-app Microsoft Office om bestanden weer te geven en te bewerken die worden gehost op SharePoint of OneDrive. Als u de Office web-app wilt installeren, gaat u naar en selecteert u de knop App beschikbaar Office https://www.office.com installeren in de adresbalk.   Selecteer **Installeren om** te bevestigen.

> [!IMPORTANT]
> Office web-app-functionaliteit is alleen beschikbaar wanneer uw HoloLens 2 een actieve internetverbinding heeft.

### <a name="webxr-and-360-viewer"></a>WebXR en 360 Viewer

De nieuwe Microsoft Edge biedt ondersteuning voor WebXR, de nieuwe standaard voor het maken van in immersive web experiences (het vervangen van WebVR). Veel in immersieve webervaringen zijn ontworpen met VR in gedachten (ze vervangen uw weergaveveld door een virtuele omgeving), maar deze ervaringen worden ook ondersteund door HoloLens 2. De WebXR-standaard biedt ook uitgebreide en mixed reality ingebouwde webervaringen die gebruikmaken van uw fysieke omgeving. Omdat ontwikkelaars meer tijd besteden aan WebXR, verwachten we dat er nieuwe uitgebreide en mixed reality-ervaringen zullen binnenkomen die klanten HoloLens 2 kunnen proberen.

De 360 Viewer-extensie is gebaseerd op WebXR en wordt automatisch geïnstalleerd naast de nieuwe Microsoft Edge op HoloLens 2. Deze webextensie biedt u de mogelijkheid om uzelf te verdiepen in video's van 360 graden. YouTube biedt de grootste selectie van 360 video's. Daarom raden we u aan om daar te beginnen.

#### <a name="how-to-use-webxr"></a>WebXR gebruiken

1. Navigeer naar een website met WebXR-ondersteuning.
1. Selecteer de **knop VR** invoeren op de website. De locatie en visuele weergave van deze knop kunnen per website verschillen, maar kunnen er ongeveer als de volgende uitzien:

    ![Voer het voorbeeld van de VR-knop in.](images/75px-enter-vr.png)

1. De eerste keer dat u een WebXR-ervaring op een specifiek domein probeert te starten, vraagt de browser om toestemming om een in immersieve weergave in te voeren. Selecteer **Toestaan.**
1. Gebruik [HoloLens 2 om de](hololens2-basic-usage.md#the-hand-tracking-frame) ervaring te manipuleren.
1. Als de ervaring geen  knop Afsluiten heeft, gebruikt u de beweging [Start om](hololens2-basic-usage.md#start-gesture) terug te keren.

**Aanbevolen WebXR-voorbeelden**

- 360 Viewer (zie de volgende sectie)
- [XR-](https://www.xrdinosaurs.com/)
- [Barista Express](https://constructarca.de/game/barista-express/)
- [WebXR-Paint](https://threejs.org/examples/webxr_vr_paint.html)

#### <a name="how-to-use-360-viewer"></a>360 Viewer gebruiken

1. Navigeer naar een video van 360 graden op YouTube.
1. Selecteer in het videoframe de knop mixed reality headset:

    ![Knop om 360 Viewer te activeren.](images/enter-360-viewer.jpg)

1. De eerste keer dat u 360 Viewer op een specifiek domein probeert te starten, wordt in de browser om toestemming gevraagd om een in immersieve weergave in te voeren. selecteer **Toestaan**.
1. [Tik in de lucht](hololens2-basic-usage.md#select-using-air-tap) om de afspeelbesturingselementen weer te brengen. Gebruik [handfoto's](hololens2-basic-usage.md#select-using-air-tap) en tikken in de lucht om af te spelen/onderbreken, vooruit/terug te gaan, bijschriften in/uit te schakelen of de ervaring te stoppen (waardoor de in immersieve weergave wordt afgesloten). De afspeelbesturingselementen verdwijnen na een paar seconden inactiviteit.

#### <a name="top-webxr-and-360-viewer-known-issues"></a>Meest bekende problemen met WebXR en 360 Viewer

- Afhankelijk van de complexiteit van de WebXR-ervaring, kan de framerate worden verwijderd of gesutterd.
- Ondersteuning voor verwoorde handjes in WebXR is niet standaard ingeschakeld. Ontwikkelaars kunnen ondersteuning inschakelen via `edge://flags` door 'WebXR Hand Input' in te stellen.
- 360 video's van andere websites dan YouTube werken mogelijk niet zoals verwacht.

#### <a name="providing-feedback-on-webxr-and-360-viewer"></a>Feedback geven over WebXR en 360 Viewer

Deel feedback en fouten met ons team via de functie **Feedback** verzenden in de nieuwe Microsoft Edge.

### <a name="new-settings-app"></a>Nieuwe Instellingen app

In deze release introduceren we een nieuwe versie van de Instellingen app. De nieuwe Instellingen-app bevat nieuwe functies en uitgebreide instellingen voor HoloLens 2 in de volgende gebieden: Geluid, Power &-slaapstand, Network & Internet, Apps, Accounts, Toegankelijkheid en meer.

> [!NOTE]
> Omdat de nieuwe Instellingen-app verschilt van de verouderde Instellingen-app, worden alle Instellingen-vensters die u eerder in uw omgeving hebt geplaatst, verwijderd bij het bijwerken.

![Startpagina Instellingen nieuwe app.](images/new-settings-app.png)

**Nieuwe functies en instellingen**

- Instellingen zoeken: zoek naar instellingen op de startpagina Instellingen met trefwoorden of de naam van de instelling.
- System > Sound:
  - Audioapparaten voor invoer en uitvoer: kies onafhankelijk van elkaar uw invoer- en uitvoer audioapparaten (u kunt bijvoorbeeld luisteren naar audio via een Bluetooth-microfoon of een USB-C-microfoon gebruiken voor audio-invoer).
    > [!NOTE]
    > Bluetooth microfoons worden niet ondersteund door HoloLens 2.
  - App-volume: pas het volume van elke app onafhankelijk aan. Zie [volumebeheer per app.](#per-app-volume-control)
- Systeem> slaapstand & slaapstand: kies wanneer het apparaat na een periode van inactiviteit in de slaapstand moet gaan.
- Systeem > batterij: schakel de batterijbesparing modus handmatig in of stel een batterijdrempel in op welk punt batterijbesparing modus automatisch wordt ingeschakeld.
- Apparaten > USB: u kunt USB-verbindingen standaard uitschakelen.
- Netwerkverbinding & internet:
  - USB-C Ethernet-adapters worden nu weergegeven in & Internet.
  - Usb-C Ethernet-adapterinstellingen zijn nu beschikbaar, met inbegrip van het IP-adres.
  - U kunt nu de vliegtuigmodus inschakelen op HoloLens 2.
- Apps: u kunt de standaardapps die worden gebruikt voor bestands- en koppelingstypen opnieuw instellen. Zie Standaard [app- picker voor meer informatie.](#default-app-picker)
- Accounts > andere gebruikers: apparaateigenaren kunnen gebruikers toevoegen, standaardgebruikers upgraden naar apparaateigenaren, apparaateigenaren downgraden naar standaardgebruikers en gebruikers verwijderen.
- Toegankelijkheid: wijzig de tekstgrootte en enkele visuele effecten.

**Bekende problemen**

- Eerder geplaatste Instellingen worden verwijderd (zie opmerking hierboven).
- U kunt de naam van uw apparaat niet meer wijzigen met de Instellingen app. IT-beheerders kunnen de naam van apparaten wijzigen met behulp van de [sjabloon Windows Autopilot](hololens2-autopilot.md) voor HoloLens 2-apparaatnaam of het knooppunt MDM [DevDetail CSP](/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/DNSComputerName.
- Op de Ethernet-pagina wordt te allen tijde een virtueel Ethernet-apparaat (UsbNcm) weergegeven.
- Accugebruik voor de nieuwe Microsoft Edge mogelijk niet nauwkeurig, vanwege de aard van een Win32-desktoptoepassing die wordt ondersteund door een UWP-adapterlaag (er wordt binnenkort geen oplossing verwacht).

#### <a name="display-color-calibration"></a>Kleurenkleuren weergeven

Met deze nieuwe instelling kunt u een alternatief kleurprofiel voor uw HoloLens 2 selecteren. Hierdoor kunnen kleuren nauwkeuriger worden weergegeven, met name bij lagere helderheidsniveaus. Kleurenweergave vindt u in de Instellingen app op de pagina Systeem > kalibratie.

> [!NOTE]
> Omdat deze instelling een nieuw kleurprofiel op uw weergavefirmware opspart, is het een instelling per apparaat (en niet uniek voor elk gebruikersaccount).

##### <a name="how-to-use-display-color-calibration"></a>Weergavekleuren gebruiken

1. Start de **Instellingen app** en navigeer **naar System > Navigate.**
1. Selecteer **onder Kleurenbratie weergeven** de knop **Weergavekleur afstemmen** uitvoeren.
1. De ervaring voor het kalibratieproces van de weergavekleur wordt gelanceerd en u wordt aansporen om ervoor te zorgen dat uw visor de juiste positie heeft.
1. Nadat u de instructiedialoogvensters hebt doorgenomen, wordt uw weergave automatisch lichter gekleurd tot 30% helderheid.
    > [!TIP]
    > Als u problemen hebt met het zien van de lichter gekleurde scène in uw omgeving, kunt u het helderheidsniveau van de HoloLens 2 handmatig aanpassen met behulp van de helderheidsknoppen aan de linkerkant van het apparaat.
1. Selecteer knoppen 1-6 om elk kleurprofiel direct uit te proberen en zoek een profiel dat het beste bij uw ogen past (dit betekent meestal het profiel waarmee de scène het meest neutraal wordt weergegeven, met het grijstintenpatroon en een skin-uiterlijk zoals verwacht.)

    ![Weergave van kleurenscène voor kalibratie.](images/color-cal-ui.png)

1. Wanneer u tevreden bent met het geselecteerde profiel, selecteert u de knop **Opslaan & afsluiten**
1. Als u liever geen wijzigingen aan te brengen, selecteert u de knop **& annuleren** en worden uw wijzigingen teruggedraaid

> [!TIP]
> Hier vindt u enkele handige tips om rekening mee te houden bij het gebruik van de instelling voor het kalibratie van de weergavekleur:
>
> - U kunt de weergavekleuren opnieuw uitvoeren vanaf Instellingen wanneer u wilt
> - Als iemand op het apparaat de instelling eerder heeft gebruikt om kleurprofielen te wijzigen, wordt de datum/tijd van de meest recente wijziging weergegeven op de Instellingen pagina
> - Wanneer u de weergavekleur opnieuw uitwerkt, wordt het kleurenprofiel dat eerder is opgeslagen gemarkeerd en wordt Profiel 0 niet weergegeven (profiel 0 vertegenwoordigt het oorspronkelijke kleurprofiel van de weergave)
> - Als u wilt terugkeren naar het oorspronkelijke kleurenprofiel van de weergave, kunt u dit doen vanaf de pagina Instellingen (zie Kleurprofiel opnieuw [instellen)](#how-to-reset-color-profile)

##### <a name="how-to-reset-color-profile"></a>Kleurenprofiel opnieuw instellen

Als u ontevreden bent over het aangepaste kleurprofiel dat is opgeslagen op uw HoloLens 2, kunt u het oorspronkelijke kleurprofiel van het apparaat herstellen:

1. Start de **Instellingen app** en navigeer **naar System > Navigate.**
1. Selecteer **onder Kleurenvoorwaarde weergeven** de knop **Standaardkleurprofiel opnieuw** instellen.
1. Wanneer het dialoogvenster wordt geopend, selecteert u **Opnieuw** opstarten als u klaar bent om de HoloLens 2 en uw wijzigingen toe te passen.

#### <a name="top-display-color-calibration-known-issues"></a>Bekende problemen met de kleur van de bovenste weergavekleur

- Op de Instellingen pagina is de statusreeks die u vertelt wanneer het kleurprofiel voor het laatst is gewijzigd, verouderd totdat u die pagina van de Instellingen.
    - Tijdelijke oplossing: selecteer een andere Instellingen selecteer vervolgens opnieuw de pagina Kalibratie.

#### <a name="default-app-picker"></a>Standaard app- kiezen

Wanneer u een hyperlink activeert of een bestandstype opent met meer dan één geïnstalleerde app die dit ondersteunt, wordt er een nieuw venster geopend waarin u wordt gevraagd te selecteren welke geïnstalleerde app het bestands- of koppelingstype moet verwerken. In dit venster kunt u er ook voor kiezen om de geselecteerde app het bestand of koppelingstype Eenmaal of Altijd te laten verwerken.

Als u Altijd kiest, maar later wilt wijzigen welke app een bepaald bestands- of koppelingstype verwerkt, kunt u de opgeslagen standaardinstellingen opnieuw instellen in **Instellingen > Apps.** Schuif naar de onderkant van  de pagina en selecteer de knop Leeg onder Standaard-apps voor bestandstypen en/of Standaard-apps voor koppelingstypen. In tegenstelling tot de vergelijkbare instelling op desktop-pc's, kunt u de standaardinstellingen voor afzonderlijke bestandstype niet opnieuw instellen.

#### <a name="per-app-volume-control"></a>Volumebeheer per app

In deze Windows kunnen gebruikers het volumeniveau van elke app handmatig aanpassen. Hierdoor kunnen gebruikers zich beter richten op de apps die ze nodig hebben, of beter kunnen horen wanneer ze meerdere apps gebruiken. Bijvoorbeeld wanneer u het volume van de ene app moet in- of uitroepen terwijl u een andere persoon aanroept voor hulp op afstand in een andere app.

Als u het volume van een afzonderlijke app wilt instellen, gaat u **naar Instellingen** System Sound en selecteert u onder Geavanceerde geluidsopties de optie  >    >   **App-volume en apparaatvoorkeuren.**<br/><br/>

<img alt="App volume and device preferences." src="./images/volume-per-app.jpg" width="500" height="250" />

#### <a name="swipe-to-type"></a>Veeg om te typen

Sommige klanten vinden het sneller 'typen' op virtuele toetsenborden door de vorm te vegen van het woord dat ze willen typen. We bekijken deze functie voor het holografische toetsenbord. U kunt met één woord tegelijk vegen door de punt van uw vinger door te geven via het vlak van het holografische toetsenbord, de vorm van het woord te vegen en vervolgens de punt van uw vinger uit het vlak van het toetsenbord te halen. U kunt de volgende woorden swipen zonder op de spatiebalk te hoeven drukken door uw vinger tussen woorden van het toetsenbord te verwijderen. U weet dat de functie werkt als u een veegtrail ziet na de beweging van uw vinger op het toetsenbord.

Houd er rekening mee dat deze functie lastig te gebruiken en te beheersen kan zijn vanwege de aard van een holografische toetsenbord waar u geen bescherming tegen uw vinger hebt (in tegenstelling tot een mobiele telefoonweergave). 

### <a name="power-menu-from-start"></a>Aan/uit-menu vanaf het startmenu

Een nieuw menu waarmee de gebruiker zich kan af- en afsluiten en het apparaat opnieuw kan opstarten. Een indicator in de HoloLens Startscherm die laat zien wanneer een systeemupdate beschikbaar is.

#### <a name="how-to-use"></a>Gebruik

1. Open de HoloLens Startscherm met behulp van [de beweging Start](hololens2-basic-usage.md#start-gesture) of zeg 'Ga naar start'.

2. Let op het beletselteken (...) naast de afbeelding van het gebruikersprofiel:<br/><br/>

   <img alt="ser context dots, ..." src="./images/powertransition_icon_default_cropped.png" width="586" height="330" />

3. Selecteer de afbeelding van het gebruikersprofiel met behulp van uw handen of de spraakopdracht 'Power'.

4. Er wordt een menu weergegeven met opties voor Afloggen, Opnieuw opstarten of Afsluiten van het apparaat:<br/><br/>

   <img alt="User context menu" src="./images/powertransition_aad_options_cropped.png" width="586" height="330" />

5. Selecteer de menuopties om u af te melden, opnieuw op te starten of uw HoloLens. De optie Aanmelden is mogelijk niet beschikbaar als het apparaat is ingesteld voor één [Microsoft-account (MSA) of een lokaal account.](hololens-identity.md)

6. Sluit het menu door ergens anders aan te raken of de Startmenu met de beweging Starten.

#### <a name="update-indicator"></a>Indicator bijwerken

Wanneer een update beschikbaar is, wordt het beletselteken weergegeven om aan te geven dat de update opnieuw wordt geïnstalleerd. De menuopties worden ook gewijzigd om de aanwezigheid van de update weer te geven.<br/><br/>

<img alt="User context menu showing update" src="./images/powertransition_aad_options_update_cropped.png" width="470" height="313" />

### <a name="multiple-users-listed-on-sign-in-screen"></a>Meerdere gebruikers die worden vermeld op het aanmeldingsscherm

Voorheen werd in het scherm Aanmelden alleen de meest recent aangemelde gebruiker weergegeven, evenals het toegangspunt 'Andere gebruiker'. We hebben feedback van klanten ontvangen dat dit niet voldoende is als meerdere gebruikers zich bij het apparaat hebben aangemeld. Ze moesten nog steeds hun gebruikersnaam opnieuw typen, enzovoort.

Geïntroduceerd in deze Windows build,  wanneer u Andere gebruiker selecteert die zich rechts van het invoerveld voor de pincode bevindt, worden op het aanmeldingsscherm meerdere gebruikers weergegeven met een eerder aangemelde gebruiker bij het apparaat. Hierdoor kunnen gebruikers hun gebruikersprofiel selecteren en zich vervolgens aanmelden met hun Windows Hello referenties. Een nieuwe gebruiker kan ook worden toegevoegd aan het apparaat vanaf deze pagina Andere gebruikers via de **knop Account** toevoegen.

In het menu Andere gebruikers wordt op de knop Andere gebruikers de laatste gebruiker weergegeven die is aangemeld bij het apparaat. Selecteer deze knop om terug te keren naar het aanmeldingsscherm voor deze gebruiker.

![Standaard aanmeldingsscherm.](./images/multiusers1.jpg)

<br>

![Aanmeldingsscherm voor andere gebruikers.](./images/multiusers2.jpg)

### <a name="usb-c-external-microphone-support"></a>Ondersteuning voor externe USB-C-microfoon

> [!IMPORTANT]
> Als u een **USB-microfoon aansluit, wordt deze niet automatisch ingesteld als invoerapparaat.** Bij het aansluiten van een set USB-C-hoofdtelefoon zien gebruikers dat de audio van de hoofdtelefoon automatisch wordt omgeleid naar de hoofdtelefoon, maar het besturingssysteem van de HoloLens geeft prioriteit aan de interne microfoon array boven elk ander invoerapparaat. **Volg de onderstaande stappen om een USB-C-microfoon te gebruiken.**

Gebruikers kunnen externe usb-C-microfoons selecteren met behulp van het **instellingenpaneel** Geluid. USB-C-microfoons kunnen worden gebruikt voor het aanroepen, opnemen, enzovoort.

Open de **Instellingen app** en selecteer   >  **Systeemgeluid.**

![Geluid Instellingen.](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> Als u externe microfoons met **Remote Assist,** moeten gebruikers op de hyperlink 'Geluidsapparaten beheren' klikken.
>
> Gebruik vervolgens de vervolgkeuzeset om de externe microfoon in te stellen als **Standaardmicrofoon** of **Standaardcommunicatie.** Als **u Standaard** kiest, wordt de externe microfoon overal gebruikt.
>
> Als **u Standaardcommunicatie** kiest, betekent dit dat de externe microfoon wordt gebruikt in Remote Assist en andere communicatie-apps, maar de HoloLens mic-matrix kan nog steeds worden gebruikt voor andere taken.

![Geluidsapparaten beheren.](images/usbc-mic-2.png)

<br>

![Stel de standaardwaarde voor de microfoon in.](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a>Hoe zit het Bluetooth microfoonondersteuning?

Helaas Bluetooth microfoons nog steeds niet ondersteund op HoloLens 2.

#### <a name="troubleshooting-usb-c-microphones"></a>Problemen met USB-C-microfoons oplossen

Let erop dat sommige USB-C-microfoons zichzelf ten onrechte als microfoon en *spreker* melden. Dit is een probleem met de microfoon en niet met HoloLens. Wanneer u een van deze microfoons op het HoloLens, gaat het geluid mogelijk verloren. Gelukkig is er een eenvoudige oplossing.  

Stel **Instellingen** in het systeemgeluid expliciet  >    >  de ingebouwde sprekers **(audio-stuurprogramma** voor analoge functie) in als **het standaardapparaat**. HoloLens moet deze instelling onthouden, zelfs als de microfoon wordt verwijderd en later opnieuw wordt verbonden.

![Problemen met USB-C-microfoons oplossen.](images/usbc-mic-4.png)

### <a name="visitor-auto-logon-for-kiosks"></a>Automatische aanmelding van bezoekers voor kiosken

Met deze nieuwe functie kan de automatische aanmelding bij Bezoekersaccounts worden gebruikt voor kioskmodi.

Voor een niet-AAD configureren van een apparaat voor automatische aanmelding van bezoekers:

1. Maak een inrichtingspakket dat:
    1. Hiermee **configureert u Runtime-instellingen/AssignedAccess om** bezoekersaccounts toe te staan.
    1. Optioneel wordt het apparaat ingeschreven bij MDM **(Runtime-instellingen/Werkplek/Registraties),** zodat het later kan worden beheerd.
    1. Maak geen lokaal account
1. [Pas het inrichtingspakket toe.](hololens-provisioning.md)

Voor een AAD kunnen gebruikers tegenwoordig iets vergelijkbaars als dit bereiken zonder deze wijziging. AAD apparaten die zijn geconfigureerd voor de kioskmodus, kunnen zich aanmelden bij een Bezoekers-account met één knop tikken vanaf het aanmeldingsscherm. Nadat het apparaat is aangemeld bij het bezoekersaccount, wordt het apparaat pas opnieuw gevraagd om zich aan te melden als de bezoekers expliciet is aangemeld bij het menu Start of het apparaat opnieuw wordt opgestart.

Automatische aanmelding van bezoekers kan worden beheerd via aangepast [OMA-URI-beleid:](/mem/intune/configuration/custom-settings-windows-10)

- URI-waarde: ./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon

| Beleid  | Description   | Configuraties  |
|---|---|---|
| MixedReality/BezoekersAutoLogon  | Hiermee kan een bezoekers zich automatisch bij een kiosk laten aanmeldingen   | 1 (Ja), 0 (Nee, standaardinstelling.)  |

### <a name="use-the-new-settings-and-edge-apps-in-kiosk-modes"></a>De nieuwe apps Instellingen Edge in kioskmodi gebruiken

Bij het toevoegen van apps in [kiosken](hololens-kiosk.md)voegt een IT-beheerder de app vaak toe aan de kiosk, maar gebruikt deze de AUMID (App User Model ID). Omdat zowel de Instellingen-app als de Microsoft Edge-app worden beschouwd als nieuwe apps en anders dan de oudere apps, moeten kiosken die gebruikmaken van AUMID's voor deze apps worden bijgewerkt om de nieuwe AUMID te kunnen gebruiken.

Wanneer u een Kiosk wijzigt om de nieuwe apps op te nemen, raden we u aan de nieuwe AUMID toe te voegen en de oude te verlaten. Dit maakt een eenvoudige overgang mogelijk wanneer gebruikers het besturingssysteem bijwerken en geen nieuw beleid hoeven te ontvangen om de kiosk naar eigen goed gebruik te blijven gebruiken.

| App                    | AUMID                                                  |
|------------------------|--------------------------------------------------------|
| Oude Instellingen app       | HolographicSystemSettings_cw5n1h2txyewy! App            |
| Nieuwe Instellingen app       | BAEAEF15-9ILE-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy! App |
| Oude Microsoft Edge app | Microsoft.MicrosoftEdge_8wekyb3d8bbwe! MicrosoftEdge    |
| Nieuwe Microsoft Edge app | Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe! MSEDGE    |

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>Wijzigingen in het gedrag van de kioskmodus voor het afhandelen van fouten

Als een apparaat in oudere builds een kioskconfiguratie heeft, wat een combinatie is van zowel globale toegewezen toegang als aan AAD-groepslid toegewezen[](hololens-kiosk.md#issue---no-apps-are-shown-in-start-menu-in-kiosk-mode)toegang, ziet de gebruiker niets in het menu Start als het bepalen van het AAD-groepslidmaatschap is mislukt.

Vanaf deze Windows wordt de kioskervaring terugvallen op de algemene kioskconfiguratie (indien aanwezig) in het geval van fouten tijdens AAD kioskmodus.

### <a name="new-settings-uris-for-page-settings-visibility"></a>Nieuwe Instellingen voor zichtbaarheid van pagina-Instellingen

In [Windows Holographic, versie 20H2,](hololens-release-notes.md#windows-holographic-version-20h2) is het [beleid Instellingen/PageVisibilityList](/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) toegevoegd om de pagina's in de app Instellingen beperken. PageVisibilityList is een beleid waarmee IT-beheerders kunnen voorkomen dat specifieke pagina's in de System Instellingen-app zichtbaar of toegankelijk zijn, of om dit te doen voor alle pagina's behalve de pagina's die zijn opgegeven.

Als u Page [Instellingen Visibility](settings-uri-list.md)bezoekt, vindt u instructies voor het gebruik van deze CSP en de lijst met URI's die beschikbaar zijn in eerdere releases.

We gaan verder met de lijst met beschikbare Instellingen URI's die IT-beheerders kunnen beheren. Sommige van deze URI's zijn voor nieuw beschikbare gebieden binnen de nieuwe Instellingen app. Als u het beleid Instellingen/PageVisibilityList gebruikt, bekijkt u de volgende lijst en past u de toegestane of geblokkeerde pagina's zo nodig aan.

> [!NOTE]
> **Afgeschaft: ms-settings:network-proxy**
>
> Eén instellingenpagina is afgeschaft in deze nieuwere builds. De oude **pagina &**  >  **internetproxy** is niet meer beschikbaar als algemene instelling. De nieuwe proxyinstellingen per verbinding vindt u onder **Network & Internet**  >  **Wi-Fi** Properties of Network &  >   **Internet**  >  **Ethernet**  >  **Properties**.

<br>

| Pagina Instellingen                                        | URI                                              |
|------------------------------------------------------|--------------------------------------------------|
| Apps > Apps &-functies                               | `ms-settings:appsfeatures`                         |
| Apps > Apps & functies > Geavanceerde opties          | `ms-settings:appsfeatures-app`                     |
| Apps > Offline-kaarten                                  | `ms-settings:maps`                                 |
| Apps > Offline-kaarten > Download-kaarten                  | `ms-settings:maps-downloadmaps`                    |
| Apparaten > Muis                                      | `ms-settings:mouse`                                |
| Apparaten > USB                                        | `ms-settings:usb`                                  |
| Netwerkverbinding & internet > vliegtuigmodus                   | `ms-settings:network-airplanemode`                 |
| Privacy > Algemeen                                    | `ms-settings:privacy-general`                      |
| Privacy-> Ink-& te typen             | `ms-settings:privacy-speechtyping`                 |
| Privacy > Motion                                     | `ms-settings:privacy-motion`                       |
| Privacy-> Schermopnamegrenzen                         | `ms-settings:privacy-graphicsCaptureWithoutBorder` |
| Privacy > schermopnamen en apps                       | `ms-settings:privacy-graphicsCaptureProgrammatic`  |
| Systeem > batterij                                     | `ms-settings:batterysaver`                         |
| Systeem > batterij                                     | `ms-settings:batterysaver-settings`                |
| System > Sound                                       | `ms-settings:sound`                                |
| System > Sound > App-volume en apparaatvoorkeuren | `ms-settings:apps-volume`                          |
| System > Sound > Geluidsapparaten beheren              | `ms-settings:sound-devices`                        |
| System > Storage > Configure Storage Sense         | `ms-settings:storagepolicies`                      |
| Time & Language > Datum & tijd                        | `ms-settings:dateandtime`                          |
| Time & Language > Keyboard                           | `ms-settings:keyboard`                             |
| Time & Language > Language                           | `ms-settings:language`                             |
| Time & Language > Language                           | `ms-settings:regionlanguage-languageoptions`       |
| Beveiligingsbeleid & opnieuw > herstellen & bijwerken               | `ms-settings:reset`                                |

#### <a name="updated-uris"></a>Bijgewerkte URI's

Voorheen zouden de volgende twee URI's een gebruiker niet rechtstreeks naar de aangegeven pagina's laten gaan, maar alleen de hoofdupdatepagina blokkeren. De volgende items zijn bijgewerkt om naar de pagina's te gaan:

- `ms-settings:windowsupdate-options`
- `ms-settings:windowsupdate-restartoptions`

### <a name="configuring-fallback-diagnostics-via-settings-app"></a>Terugvaldiagnose configureren via Instellingen app

In Instellingen App kan een gebruiker nu het gedrag van [Fallback Diagnostics configureren.](hololens-diagnostic-logs.md) Ga in Instellingen app naar de **pagina**  >  **Privacyproblemen** oplossen om deze instelling te configureren.

> [!NOTE]
> Als er MDM-beleid is geconfigureerd voor het apparaat, kan de gebruiker dat gedrag niet overschrijven.  

### <a name="share-things-with-nearby-devices"></a>Dingen delen met apparaten in de buurt

Deel dingen met bijna Windows 10 apparaten, met inbegrip van zowel pc's als andere HoloLens 2 apparaten. U kunt het uitproberen in **Instellingen** System Shared Experiences om bestanden of URL's van een HoloLens naar  >    >   een pc te delen. Lees meer over het delen van dingen met apparaten in de buurt [in Windows 10.](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9)

Deze functie kan worden beheerd via [Connectivity/AllowConnectedDevices](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowconnecteddevices).

### <a name="new-os-diagnostic-traces"></a>Nieuwe diagnostische traceringen van het besturingssysteem

Naast de vorige probleemoplossers in de Instellingen-app, is er een nieuwe probleemoplosser toegevoegd met de toevoeging van de nieuwe Instellingen-app voor updates van het besturingssysteem. Navigeer **naar Instellingen**  >  **Update &amp; Security**  >  **Troubleshoot**  >  **Windows Update** en selecteer **Start.** Hiermee kunt u traceringen verzamelen tijdens het reproduceren van uw probleem met updates van het besturingssysteem, zodat u beter kunt helpen bij het oplossen van problemen met uw IT of ondersteuning.

### <a name="delivery-optimization-preview"></a>Delivery Optimization Preview

Met deze HoloLens update kunnen Windows Holographic for Business delivery optimization-instellingen gebruiken om het bandbreedteverbruik voor downloads van meerdere HoloLens beperken. Een volledige beschrijving van deze functionaliteit en de aanbevolen netwerkconfiguratie is hier beschikbaar: Delivery Optimization [voor Windows 10 updates.](/windows/deployment/update/waas-delivery-optimization)

De volgende instellingen zijn ingeschakeld als onderdeel van het beheeroppervlak en [kunnen worden geconfigureerd vanuit Intune:](/mem/intune/configuration/delivery-optimization-settings)

- [DOCacheHost](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehost)
- [DOCacheHostSource](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehostsource)
- [DODelayCacheServerFallbackBackground](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackbackground)
- [DODelayCacheServerFallbackForeground](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackforeground)
- [DODownloadMode](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodownloadmode)
- [DOMaxBackgroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxbackgrounddownloadbandwidth)
- [DOMaxForegroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxforegrounddownloadbandwidth)
- [DOPercentageMaxBackgroundBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxbackgroundbandwidth)
- [DOPercentageMaxForegroundBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxforegroundbandwidth)
- [DOSetHoursToLimitForegroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitforegrounddownloadbandwidth)
- [DOSetHoursToLimitBackgroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitbackgrounddownloadbandwidth)

Enkele waarschuwingen over deze preview-aanbieding:

- HoloLens ondersteuning is in deze preview beperkt tot alleen updates van het besturingssysteem.
- Windows Holographic for Business ondersteunt alleen HTTP-downloadmodi en downloads van een [Microsoft Verbonden cache-eindpunt;](/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache) Peer-to-peer downloadmodi en groepstoewijzingen worden momenteel niet ondersteund HoloLens apparaten.
- HoloLens biedt geen ondersteuning voor implementatie of delivery optimization voor Windows Server Update Services eindpunten.
- Voor het oplossen van problemen zijn diagnostische gegevens op de Verbonden cache-server of het verzamelen van een trace op HoloLens op HoloLens vereist via **Instellingen**  >  **Update & Security**  >   **Troubleshooting** Windows  >   **Update**.

### <a name="it-admin---update-checklist"></a>IT-beheerder - Controlelijst voor bijwerken

Deze controlelijst helpt u de nieuwe items te kennen die functies die worden toegevoegd in deze functie-update die van invloed kunnen zijn op uw huidige configuraties voor apparaatbeheer, of nieuwe functies die u mogelijk wilt gaan gebruiken.

#### <a name="updates-to-kiosk-mode"></a>Updates voor kioskmodus

✔️ nieuwe [**AUMID's voor nieuwe apps in kioskmodus**](#use-the-new-settings-and-edge-apps-in-kiosk-modes):

Als u voorheen de Instellingen- of Microsoft Edge-app in een kiosk gebruikte, hebben we deze apps vervangen door nieuwe apps die een andere app-id gebruiken. We raden u ten zeerste aan nieuwe [AUMID's](#use-the-new-settings-and-edge-apps-in-kiosk-modes) voor nieuwe apps in de kioskmodus hieronder te lezen. Zo zorgt u ervoor dat u de app Instellingen in uw kiosk blijft of dat u de nieuwe app Microsoft Edge opnemen. Deze wijzigingen kunnen nu worden uitgevoerd en op alle apparaten worden geïmplementeerd en zorgen voor een soepelere overgang bij de update.

✔️ [**Bezoekers automatische aanmelding voor kiosken:**](#visitor-auto-logon-for-kiosks)

Bezoekers kunnen nu automatisch worden aangemeld bij een kiosk. Dit gedrag is standaard ingeschakeld, maar kan worden beheerd en uitgeschakeld.

✔️ verbeterde [**fout bij het in de kioskmodus geven:**](#kiosk-mode-behavior-changes-for-handling-of-failures)

Als AAD groepslidmaatschap van de aangemelde AAD-gebruiker niet is vastgesteld, wordt globale kioskconfiguratie gebruikt voor het startmenu (indien aanwezig), anders wordt het menu Start leeg weergegeven. Hoewel het lege startmenu geen configuratie is die u rechtstreeks kunt instellen, kan deze nieuwe verwerking iets zijn om uw ondersteuningsafdeling op de hoogte te stellen van als u kiosken gebruikt, omdat dit van toepassing kan zijn op uw configuraties of u mogelijk nieuwe aanpassingen wilt aanbrengen in uw toegewezen toegangsconfiguraties.

#### <a name="updates-to-page-settings-visibility"></a>Updates voor Instellingen zichtbaarheid

✔️ Nieuwe [**Instellingen-URI's voor zichtbaarheid Instellingen pagina**](#new-settings-uris-for-page-settings-visibility)

Als u momenteel Page [Instellingen Visibility](settings-uri-list.md) gebruikt, wilt u mogelijk wijzigingen aanbrengen in uw bestaande URI's die u hebt toegestaan of geblokkeerd.

#### <a name="updates-for-your-wdac-policy"></a>Updates voor uw WDAC-beleid

✔️ als u eerder toegang Microsoft Edge via WDAC hebt geblokkeerd, moet u uw WDAC-beleid bijwerken. Controleer het volgende en gebruik de opgegeven voorbeeldcode.

#### <a name="enable-new-endpoints-for-edge"></a>Nieuwe eindpunten inschakelen voor Edge

✔️ als u een infrastructuur hebt die netwerk-eindpunten zoals proxy of firewall moet configureren, moet u deze nieuwe eindpunten inschakelen voor de nieuwe Microsoft Edge app.

#### <a name="newly-configurable-items"></a>Nieuw configureerbare items

✔️ [Terugvaldiagnose configureren:](#configuring-fallback-diagnostics-via-settings-app)u kunt configureren of en wie terugvaldiagnose mogen verzamelen.

✔️[Delen met apparaten in de buurt:](#share-things-with-nearby-devices)u kunt de nieuwe functie voor delen in de buurt uitschakelen.

✔️ [Beleidsinstellingen configureren voor](#configuring-policy-settings-for-the-new-microsoft-edge)de nieuwe Microsoft Edge: controleer de nieuwe configuraties die beschikbaar zijn voor Microsoft Edge.

#### <a name="new-diagnostic-tool"></a>Nieuw diagnostisch hulpprogramma

✔️[diagnostische traceringen van het besturingssysteem:](#new-os-diagnostic-traces)verzamel logboeken met betrekking tot updates van het besturingssysteem.

### <a name="improvements-and-fixes-in-the-update"></a>Verbeteringen en oplossingen in de update:

- [Offlinediagnose](hololens-diagnostic-logs.md#offline-diagnostics) bevat ook aanvullende apparaatgegevens voor het serienummer en de versie van het besturingssysteem.
- Oplossing voor een probleem met de implementatie van Line-Of-Business-toepassingen via runtime-inrichtingspakketten.
- Er is een probleem opgelost met de rapportage van de installatiestatus van line-of-business-toepassingen.
- Hiermee wordt een probleem opgelost met de persistentie van nieuwe app-pakketten bij het opnieuw instellen van apparaten.
- Lost een probleem op dat ertoe kan leiden dat onjuiste symbolen worden getypt in Edge voor Japanse klanten.
- Verbetert de tolerantie van updates van het besturingssysteem voor vooraf geïnstalleerde apps, zoals Edge.
- Behandelt een updatebetrouwbaarheid die van invloed is op de installatie van Microsoft Edge.

## <a name="windows-holographic-version-20h2--may-2021-update"></a>Windows Holographic, versie 20H2 – Update van mei 2021

- Build 19041.1146

Verbeteringen en oplossingen in de update:

- Deze maandelijkse kwaliteitsupdate bevat geen belangrijke wijzigingen. We raden u aan onze nieuwste build, Windows Holographic, versie 21H1, uit te proberen.

## <a name="windows-holographic-version-1903---may-2021-update"></a>Windows Holographic, versie 1903 - Update van mei 2021

- Build 18362.1110

Verbeteringen en oplossingen in de update:

- Deze maandelijkse kwaliteitsupdate bevat geen belangrijke wijzigingen. **Deze build ontvangt geen maandelijkse service-updates meer.** We raden u aan onze nieuwste build, Windows Holographic versie 21H1, uit te proberen.

## <a name="windows-holographic-version-20h2---april-2021-update"></a>Windows Holographic, versie 20H2 - update van april 2021

- Build 19041.1144

Verbeteringen en oplossingen in de update:

- Er is een probleem opgelost met de rapportage van de installatiestatus van line-of-business-toepassingen.

## <a name="windows-holographic-version-1903---april-2021-update"></a>Windows Holographic, versie 1903 - update van april 2021

- Build 18362.1108

Verbeteringen en oplossingen in de update:

- Lost een probleem op waarbij de Instellingen app vast loopt bij een poging om een wachtwoord voor een lokaal account te wijzigen.


## <a name="windows-holographic-version-20h2---march-2021-update"></a>Windows Holographic, versie 20H2 - update van maart 2021

- Build 19041.1140

Verbeteringen en oplossingen in de update:

- Klanten die AdvancedPhotoCapture of LowLagPhotoCapture gebruiken om foto's vast te leggen met HoloLens 2 kunnen nu de camerahouding ophalen tot drie seconden nadat de foto is vastgelegd.
- Oplossing voor een geheugenlek in Apparaatportal-service, heeft het probleem het verhoogde geheugengebruik veroorzaakt door de service waardoor het toewijzen van geheugen door andere toepassingen is mislukt.
- Er is een probleem opgelost waarbij gebruikers die zijn ingeschreven bij gefaseerd rollout zich niet kunnen aanmelden bij het apparaat.

## <a name="windows-holographic-version-1903---march-2021-update"></a>Windows Holographic, versie 1903 - update van maart 2021

- Build 18362.1102

Verbeteringen en oplossingen in de update:

- Oplossing voor een geheugenlek in Apparaatportal-service, heeft het probleem het verhoogde geheugengebruik veroorzaakt door de service waardoor het toewijzen van geheugen door andere toepassingen is mislukt.

## <a name="windows-holographic-version-20h2---february-2021-update"></a>Windows Holographic, versie 20H2 - update van februari 2021

- Build 19041.1136

Verbeteringen en oplossingen in de update:

- Er is een probleem opgelost met de initiële installatie van apparaten en het opslaan van app-updates.
- Lost een probleem op met betrekking tot upgrades en vluchten voor latere HoloLens releases.
- Ongebruikte vooraf geïnstalleerde certificaten verwijderd uit het eSIM-basisopslag van HoloLens apparaten.

## <a name="windows-holographic-version-1903---february-2021-update"></a>Windows Holographic, versie 1903 - Update van februari 2021

- Build 18362.1098

Deze maandelijkse kwaliteitsupdate bevat geen belangrijke wijzigingen. We raden u aan onze nieuwste builds voor Windows Holographic, versie 2004, uit te proberen.

## <a name="windows-holographic-version-20h2---january-2021-update"></a>Windows Holographic, versie 20H2 - update van januari 2021

- Build 19041.1134

Verbeteringen en oplossingen in de update:

- Verbeterde prestaties tijdens het opstarten, hervatten en schakelen tussen gebruikers wanneer er veel gebruikers op het apparaat zijn.
- Er is arm32-ondersteuning toegevoegd voor [de onderzoeksmodus](/windows/mixed-reality/develop/platform-capabilities-and-apis/research-mode).

## <a name="windows-holographic-version-1903---january-2021-update"></a>Windows Holographic, versie 1903 - update van januari 2021

- Build 18362.1091

Deze maandelijkse kwaliteitsupdate bevat geen belangrijke wijzigingen. We raden u aan onze nieuwste builds voor Windows Holographic, versie 2004, uit te proberen.

## <a name="windows-holographic-version-20h2--december-2020-update"></a>Windows Holographic, versie 20H2 – update van december 2020

- Build 19041.1131

### <a name="install-apps-on-hololens-2-via-app-installer"></a>Apps installeren op HoloLens 2 via App-installatieprogramma

Er wordt **een nieuwe mogelijkheid (App-installatieprogramma)** toegevoegd waarmee u toepassingen naadloos kunt installeren op uw HoloLens 2 apparaten. De functie is **standaard ingeschakeld voor niet-beherende apparaten.** Om onderbrekingen voor ondernemingen te voorkomen, is het app-installatieprogramma op dit moment niet beschikbaar **voor** beheerde apparaten.  

Een apparaat wordt beschouwd als 'beheerd' als **een** van de volgende waar is:

- MDM [ingeschreven](hololens-enroll-mdm.md)
- Geconfigureerd met [inrichtingspakket](hololens-provisioning.md)
- [Gebruikersidentiteit](hololens-identity.md) is Azure AD

U kunt nu Apps installeren zonder dat u de ontwikkelaarsmodus hoeft in te schakelen of de Apparaatportal.  Download (via USB of edge) de Appx-bundel naar uw apparaat en navigeer naar de Appx-bundel in de Bestandenverkenner om te worden gevraagd de installatie te beginnen.  U kunt ook [een installatie starten vanaf een webpagina](/windows/msix/app-installer/installing-windows10-apps-web).  Net als apps die u installeert vanuit de Microsoft Store of sideloaden met behulp van de [](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) LOB App-implementatiefunctie van MDM, moeten apps digitaal worden ondertekend met het hulpprogramma voor ondertekenen en moet het certificaat dat wordt gebruikt om te ondertekenen door het HoloLens-apparaat worden vertrouwd voordat de app kan worden geïmplementeerd. [](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations)

**Installatie-instructies voor de toepassing.**

1. Zorg ervoor dat uw apparaat niet wordt beschouwd als beheerd
1. Zorg ervoor dat HoloLens 2 apparaat is ingeschakeld en is verbonden met uw pc
1. Zorg ervoor dat u bent aangemeld bij het HoloLens 2 apparaat
1. Navigeer op uw pc naar uw aangepaste app en kopieer yourapp.appxbundle naar yourdevicename\Internal Storage\Downloads.   Nadat u klaar bent met het kopiëren van het bestand, kunt u de verbinding met uw apparaat verbreken
1. Selecteer op HoloLens 2 apparaat Het startmenu openen, selecteer Alle apps start de Verkenner-app.
1. Navigeer naar de map Downloads. Mogelijk moet u eerst Dit apparaat selecteren in het linkerpaneel van de app en vervolgens naar Downloads navigeren.
1. Selecteer het bestand yourapp.appxbundle.
1. De App-installatieprogramma wordt starten. Selecteer de knop Installeren om uw app te installeren.
De geïnstalleerde app wordt automatisch start na voltooiing van de installatie.

U vindt voorbeeld-apps op [Windows Universal Samples GitHub](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples) deze stroom te testen.

Lees meer over het volledige proces [voor het installeren van apps op HoloLens 2 met de App-installatieprogramma](app-deploy-app-installer.md).  

![MRTK-voorbeelden installeren via App-installatieprogramma.](images/hololens-app-installer-picture.jpg)

### <a name="improvements-and-fixes-in-the-update"></a>Verbeteringen en oplossingen in de update:

- Handtracking houdt nu het bijhouden bij in veel nieuwe gevallen waarbij de hand eerder verloren zou zijn gegaan.  In sommige van deze nieuwe gevallen blijft alleen de positie van de functie worden bijgewerkt op basis van de echte hand van de gebruiker, terwijl de andere positie wordt afgeleid op basis van een eerdere houding.  Deze wijziging helpt bij het verbeteren van de consistentie van het bijhouden van verplaatsingen, zoals slapping, throwing,ing en clapping.  Het helpt ook in gevallen waarin de hand zich dicht bij een oppervlak of een object houdt.  Wanneer handgewrichten worden afgeleid, wordt [de waarde per gezamenlijke](/uwp/api/windows.perception.people.jointposeaccuracy?view=winrt-19041&preserve-view=true) nauwkeurigheid ingesteld op 'Bij benadering' in plaats van 'Hoog'.
- Er is een probleem opgelost waarbij het opnieuw instellen van de pincode voor Azure AD-accounts de foutmelding 'Er is iets misgegaan' wordt weergegeven.
- Gebruikers moeten na het opstarten veel minder OOBE-crashes zien bij het starten van ET, Iris vanuit de instellingen-app, nieuwe gebruiker of pop-up voor meldingen.
- Gebruikers moeten de juiste tijdzone hebben die afkomstig is uit OOBE.

## <a name="windows-holographic-version-1903--december-2020-update"></a>Windows Holographic, versie 1903 – update van december 2020

- Build 18362.1088

Deze maandelijkse kwaliteitsupdate bevat geen belangrijke wijzigingen. We raden u aan onze nieuwste Windows Holographic, versie 20H2- december 2020-update en de nieuwe App-installatieprogramma-functie uit te proberen die in de build is toegevoegd.

## <a name="windows-holographic-version-20h2"></a>Windows Holographic, versie 20H2

- Build 19041.1128

Windows Holographic versie 20H2 is nu beschikbaar en biedt een groot aantal nieuwe functies voor HoloLens 2 en IT-professionals. Van automatisch plaatsen van ogen tot Certificaatbeheer in Instellingen, tot verbeterde functionaliteit voor de kioskmodus en nieuwe autopilot-installatiemogelijkheden. Deze nieuwe update stelt IT-teams in staat gedetailleerdere controle te krijgen over het configureren en beheren van HoloLens apparaten en biedt gebruikers nog meer naadloze holografische ervaringen.

Deze nieuwste versie is een maandelijkse update naar versie 2004, maar deze keer worden er nieuwe functies toegevoegd. Het nummer van de belangrijkste build blijft hetzelfde en Windows Update geeft een maandelijkse release aan van versie 2004 (build 19041). U kunt uw buildnummer bekijken in het scherm Instellingen > Over om te bevestigen dat u de nieuwste beschikbare build 19041.1128+ hebt. Als u wilt bijwerken naar de nieuwste versie, opent u de Instellingen app, gaat u naar Update & Security en tikt u op Controleren op updates. Ga voor meer informatie over het beheren van HoloLens updates naar [HoloLens beheren.](hololens-updates.md)

### <a name="whats-new-in-windows-holographic-version-20h2"></a>Wat is er nieuw in Windows Holographic, versie 20H2  

| Functie                                              | Beschrijving                                                                                                                                     |
|------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| [Ondersteuning voor automatische oogpositie](hololens-release-notes.md#auto-eye-position-support) | Berekent actief oogposities zonder dat gebruikers de kalibratie van Oogtracking moeten doorrekenen.   |
| [Certificaatbeheerder](hololens-release-notes.md#certificate-manager)   | Hiermee kunt u nieuwe eenvoudigere methoden voor het installeren en verwijderen van certificaten uit de Instellingen app.     |
| [Inrichting via USB automatisch starten](hololens-release-notes.md#auto-launch-provisioning-from-usb)                    | Inrichtingspakketten op USB-stations vragen automatisch om de inrichtingspagina in OOBE.                                                         |
| [Inrichtingspakketten automatisch bevestigen in OOBE](hololens-release-notes.md#auto-confirm-provisioning-packages-in-oobe)           | Inrichtingspakketten worden automatisch toegepast tijdens OOBE vanaf de inrichtingspagina.                                                         |
| [Automatische inrichting zonder gebruik van de gebruikersinterface](hololens-release-notes.md#automatic-provisioning-without-using-ui) | Het combineren van de inrichting voor automatisch starten en automatisch bevestigen. |
| [Autopilot gebruiken met Wi-Fi verbinding](hololens-release-notes.md#using-autopilot-with-wi-fi-connection) | Autopilot gebruiken vanaf apparaat Wi-Fi ethernetadapter niet nodig. |
| [Tenantlockdown-CSP en Autopilot](hololens-release-notes.md#tenantlockdown-csp-and-autopilot)                     | Nadat de tenant is ingeschreven en het beleid is toegepast, kan het apparaat alleen worden ingeschreven in die tenant wanneer het apparaat opnieuw wordt ingesteld of opnieuw wordt geflitst. |
| [Globale toegewezen toegang](hololens-release-notes.md#global-assigned-access--kiosk-mode)                               | Nieuwe configuratiemethode voor de kioskmodus voor meerdere apps waarmee de kiosk op systeemniveau wordt toegepast, waardoor deze van toepassing is op iedereen.                  |
| [Een app automatisch starten in een kiosk voor meerdere apps](hololens-release-notes.md#automatic-launch-of-an-application-in-multiple-app-kiosk-mode)                | Hiermee stelt u een toepassing in om automatisch te starten wanneer u zich aanmeldt bij een kioskmodus voor meerdere apps.                                                        |
| [Wijzigingen in het gedrag van de kioskmodus voor het afhandelen van fouten](hololens-release-notes.md#kiosk-mode-behavior-changes-for-handling-of-failures) | De fout in de kioskmodus heeft nu een beperkende terugval.                                                                                                |
| [HoloLens Beleid](hololens-release-notes.md#hololens-policies)                                    | Nieuw beleid voor HoloLens.     |
| [Azure AD-groepslidmaatschap cachen voor offline kiosk](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk)         | Met nieuw beleid kunnen gebruikers de cache voor groepslidmaatschap gebruiken om de kioskmodus offline te gebruiken voor een vast aantal dagen.                                        |
| [Nieuw apparaatbeperkingsbeleid voor HoloLens 2](hololens-release-notes.md#new-device-restriction-policies-for-hololens-2)       | Beleid voor apparaatbeheer dat nieuw is ingeschakeld voor HoloLens 2.                                                                                |
| [Nieuw energiebeleid voor HoloLens 2](hololens-release-notes.md#new-power-policies-for-hololens-2)       | Nieuw ondersteund beleid voor time-outinstellingen voor energie.  |
| [Updatebeleid](hololens-release-notes.md#newly-enabled-update-policies-for-hololens)        | Nieuw ingeschakeld beleid dat controle over updates mogelijk maakt.           |
| [Zichtbaarheid van Instellingen ingeschakelde HoloLens 2](hololens-release-notes.md#enabled-settings-page-visibility-for-hololens-2)      | Beleid om te kiezen welke pagina's worden weergegeven in Instellingen app.             |
| [Onderzoeksmodus](hololens-release-notes.md#research-mode) | De onderzoeksmodus gebruiken op HoloLens 2. |
| [Opnamelengte verhoogd](hololens-release-notes.md#recording-length-increased) | MRC-opnamen zijn niet langer dan 5 minuten. |
| [Verbeteringen en oplossingen in de update](hololens-release-notes.md#improvements-and-fixes-in-the-update)                 | Aanvullende oplossingen in de update.   |

### <a name="auto-eye-position-support"></a>Ondersteuning voor automatische oogpositie

In HoloLens 2 zorgen oogposities voor nauwkeurige positie van hologrammen, een goede weergave-ervaring en verbeterde weergavekwaliteit. Oogposities worden intern berekend als onderdeel van de berekening van de oogtracking. Dit vereist echter dat elke gebruiker de kalibratie van oogtracking doormaakt, zelfs wanneer voor de ervaring mogelijk geen ooginvoer nodig is.

**Auto Eye Position (AEP)** maakt deze scenario's mogelijk met een interactieloze manier om oogposities voor de gebruiker te berekenen. Automatische oogpositie werkt automatisch op de achtergrond vanaf het moment dat de gebruiker het apparaat aan zet. Als de gebruiker geen voorafgaande kalibratie voor oogtracking heeft, geeft Automatische oogpositie de oogposities van de gebruiker aan het weergavesysteem na een verwerkingstijd van 20 tot 30 seconden. De gebruikersgegevens blijven niet behouden op het apparaat. Daarom wordt dit proces herhaald als de gebruiker opstart en het apparaat weer in- of uit de slaapstand zet.

Er zijn enkele wijzigingen in het systeemgedrag met de functie Automatische oogpositie wanneer een niet-gecalibreerde gebruiker het apparaat in gebruik neemt. In deze context verwijst een niet-gecalibreerde gebruiker naar iemand die het proces voor het traceren van de ogen op het apparaat niet eerder heeft doorlopen.

| Actieve toepassing | Eerder gedrag | Gedrag van Windows Holographic, versie 20H2 Update |
|:-------------------|:-----------------|:-----------------------------------|
| App zonder staren of Holographic Shell |Het dialoogvenster prompt voor het traceren van de ogen wordt weergegeven. | Er wordt geen prompt weergegeven. |
| Staren-app | Het dialoogvenster prompt voor het traceren van de ogen wordt weergegeven. | De prompt voor het bijhouden van de kalibratie wordt alleen weergegeven wanneer de toepassing toegang heeft tot de oogstream. |

Als de gebruiker overstapt van een toepassing zonder staren naar een toepassing die toegang heeft tot de staringsgegevens, wordt de prompt voor de kalibratie weergegeven.

Al het andere systeemgedrag is vergelijkbaar met wanneer de huidige gebruiker geen actieve kalibratie van oogtracking heeft. De eenhandige beweging Starten wordt bijvoorbeeld niet ingeschakeld. De Out-Of-Box-Experience wordt niet gewijzigd voor de eerste installatie.

Voor ervaringen waarvoor oogcontactgegevens of zeer nauwkeurige positie van hologrammen nodig zijn, raden we niet-gecalibreerde gebruikers aan om de kalibratie van oogtracking uit te voeren. De app is toegankelijk via de prompt voor het traceren van de oogcontacten of door de Instellingen-app te starten vanuit het menu Start en vervolgens Systeem > Kalibratie > Ooginding te selecteren > Oog uit te **voeren.**

Deze informatie vindt u later met andere [kalibratiegegevens](hololens-calibration.md#auto-eye-position-support).

### <a name="certificate-manager"></a>Certificaatbeheerder

- Verbeterde hulpprogramma's voor controle, diagnose en validatie voor apparaatbeveiliging en -naleving via de nieuwe Certificaatbeheerder. Met deze mogelijkheid kunt u uw certificaten op schaal implementeren, oplossen en valideren in commerciële omgevingen.

In Windows Holographic-versie 20H2 voegen we certificaatbeheer toe aan de HoloLens 2 Instellingen app. Ga naar **Instellingen > Update & Security > Certificates**. Deze functie biedt een eenvoudige en gebruiksvriendelijke manier om certificaten op uw apparaat weer te geven, te installeren en te verwijderen. Met de nieuwe Certificate Manager hebben beheerders en gebruikers nu verbeterde hulpprogramma's voor controle, diagnose en validatie om ervoor te zorgen dat apparaten veilig en compatibel blijven.

- **Controle:** Mogelijkheid om te valideren dat een certificaat correct is geïmplementeerd of om te bevestigen dat het op de juiste wijze is verwijderd.
- **Diagnose:** Wanneer er problemen optreden, bespaart het valideren of de juiste certificaten op het apparaat aanwezig zijn tijd en helpt het bij het oplossen van problemen.
- **Validatie:** Controleren of een certificaat het beoogde doel heeft en functioneel is, kan aanzienlijke tijd besparen, met name in commerciële omgevingen voordat certificaten op grotere schaal worden geïmplementeerd.

Als u snel een specifiek certificaat in de lijst wilt vinden, zijn er opties om te sorteren op naam, winkel of vervaldatum. Gebruikers kunnen ook rechtstreeks naar een certificaat zoeken. Als u afzonderlijke certificaateigenschappen wilt weergeven, selecteert u het certificaat en klikt u op **Info.**

Certificaatinstallatie ondersteunt momenteel CER- en CRT-bestanden. Apparaateigenaren kunnen certificaten installeren op de lokale computer en de huidige gebruiker;  alle andere gebruikers kunnen alleen installeren in Huidige gebruiker. Gebruikers kunnen alleen certificaten verwijderen die rechtstreeks vanuit de gebruikersinterface Instellingen geïnstalleerd. Als een certificaat op een andere manier is geïnstalleerd, moet het ook door hetzelfde mechanisme worden verwijderd.

#### <a name="steps-to-install-a-certificate"></a>Stappen voor het installeren van een certificaat

1. Verbinding maken uw HoloLens 2 naar een pc.
1. Plaats het certificaatbestand dat u wilt installeren op een locatie op HoloLens 2.
1. **Navigeer naar Instellingen App > Update & Security > Certificates** en selecteer Install a certificate.
1. Klik **op Bestand importeren** en navigeer naar de locatie waar u het certificaat hebt opgeslagen.
1. Selecteer **Winkellocatie.**
1. Selecteer **Certificaatopslag.**
1. Klik op **Installeren**.

Het certificaat moet nu op het apparaat zijn geïnstalleerd.

#### <a name="steps-to-remove-a-certificate"></a>Stappen voor het verwijderen van een certificaat

1. Navigeer **naar Instellingen App > Update and Security > Certificates**.
1. Zoek het certificaat op naam in het zoekvak.
1. Selecteer het certificaat.
1. Klik op **Verwijderen**
1. Selecteer **Ja wanneer** u om bevestiging wordt gevraagd.

![Certificaatviewer in de Instellingen app.](images/certificate-viewer-device.jpg)

![Afbeelding waarin wordt getoond hoe u de gebruikersinterface van het certificaat gebruikt om een certificaat te installeren.](images/certificate-device-install.jpg)

Deze informatie vindt u later [op een nieuwe certificaatbeheerpagina.](certificate-manager.md)

### <a name="auto-launch-provisioning-from-usb"></a>Inrichting via USB automatisch starten

- Geautomatiseerde processen die minder gebruikersinteractie mogelijk maken wanneer USB-stations met inrichtingspakketten worden gebruikt tijdens OOBE.

Vóór deze release moesten gebruikers het inrichtingsscherm handmatig starten tijdens OOBE om in te delen met behulp van een combinatie van knoppen. Gebruikers kunnen nu de knopcombinatie overslaan met behulp van een inrichtingspakket op een USB-opslagstation.

1. Sluit het USB-station aan met het inrichtingspakket tijdens het eerste interactiemoment van OOBE
1. Wanneer het apparaat gereed is om te worden ingericht, wordt de prompt automatisch geopend met de inrichtingspagina.

Opmerking: Als een USB-station op het net aangesloten blijft terwijl het apparaat wordt opgestart, wordt met OOBE een bestaand USB-opslagapparaat opgesierd en worden er extra apparaten op aangesloten.

Voor meer informatie over het toepassen van inrichtingspakketten tijdens OOBE, gaat u naar HoloLens [inrichtingsdocumentatie.](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)

Meer informatie over [het automatisch starten van de](hololens-provisioning.md#auto-launch-provisioning-from-usb) inrichting via een USB vindt u in HoloLens inrichtingsdocumentatie.

### <a name="auto-confirm-provisioning-packages-in-oobe"></a>Inrichtingspakketten automatisch bevestigen in OOBE

- Geautomatiseerd proces dat minder gebruikersinteractie mogelijk maakt. Wanneer de pagina Inrichtingspakket wordt weergegeven, worden alle vermelde pakketten automatisch toegepast.

Wanneer het hoofdscherm voor inrichting wordt weergegeven, telt OOBE 10 seconden af voordat automatisch alle inrichtingspakketten worden toegepast. Gebruikers kunnen binnen [tien seconden na het](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe) controleren van de verwachte pakketten nog steeds bevestigen of annuleren.

### <a name="automatic-provisioning-without-using-ui"></a>Automatisch inrichten zonder gebruik van de gebruikersinterface

- Gecombineerde automatische processen voor minder apparaatinteracties voor inrichting.

Door het automatisch starten van het inrichten van USB-apparaten en de automatische bevestiging van inrichtingspakketten te combineren, kan een gebruiker automatisch HoloLens 2-apparaten inrichten zonder de gebruikersinterface van het apparaat te gebruiken of zelfs het apparaat te verkrichten. U kunt hetzelfde USB-station en inrichtingspakket blijven gebruiken voor meerdere apparaten. Dit is handig voor het implementeren van meerdere apparaten tegelijk in hetzelfde gebied.

1. [Maak een inrichtingspakket met](hololens-provisioning.md) [behulp Windows Configuration Designer](https://www.microsoft.com/store/productId/9NBLGGH4TX22).
1. Kopieer het pakket naar een USB-opslagstation.
1. [Flash uw HoloLens 2](hololens-insider.md#ffu-download-and-flash-directions) [naar 19041.1361 of nieuwer.](https://aka.ms/hololens2previewdownload)
1. Wanneer [Advanced Recovery Companion](https://www.microsoft.com/store/productId/9P74Z35SFRS8) klaar is met het flashen van uw apparaat, moet u de USB-C-kabel loskoppelen.
1. Sluit uw USB-station aan op het apparaat.
1. Wanneer het HoloLens 2 apparaat wordt opstart in OOBE, detecteert het automatisch het inrichtingspakket op het USB-station en start het de inrichtingspagina.
1. Na 10 seconden wordt het inrichtingspakket automatisch toegepast op het apparaat.

Uw apparaat is nu geconfigureerd en het [scherm Inrichting is geslaagd wordt weergegeven.](hololens-provisioning.md#automatic-provisioning-without-using-ui)

### <a name="using-autopilot-with-wi-fi-connection"></a>Autopilot gebruiken met Wi-Fi verbinding

- De noodzaak voor USB-C-adapters om de hardwarebehoeften te verminderen, is verwijderd door Autopilot in te stellen op Wi-Fi verbonden apparaten.

Als u nu tijdens OOBE verbinding HoloLens 2 met Wi-Fi, controleert OOBE op een Autopilot-profiel voor het apparaat. Als er een wordt gevonden, wordt deze gebruikt om de rest van de stroom voor AAD en inschrijving te voltooien. Met andere woorden, het gebruik van ethernet naar USB-C of Wi-Fi naar USB-C-adapter is geen vereiste meer, maar ze blijven werken als ze aan het begin van OOBE worden geleverd. Meer informatie over [Autopilot voor HoloLens 2 apparaten.](hololens2-autopilot.md)

### <a name="tenantlockdown-csp-and-autopilot"></a>Tenantlockdown-CSP en Autopilot

- Houdt apparaten in de tenant van de organisatie door ze te vergrendelen voor de tenant, zelfs door het apparaat opnieuw in te stellen of een reflash uit te voeren. Met verdere beveiliging door het maken van een account in niet toe te staan via inrichting.

HoloLens 2 ondersteunen nu TenantLockdown CSP vanaf [Windows Holographic versie 20H2.](hololens-release-notes.md#windows-holographic-version-20h2)

[TenantLockdown](/windows/client-management/mdm/tenantlockdown-csp) Met CSP HoloLens 2 gekoppeld aan MDM-inschrijving met behulp van alleen Autopilot. Zodra het CSP-knooppunt RequireNetworkInOOBE van TenantLockdown is ingesteld op waar of onwaar (in eerste instantie ingesteld) op HoloLens 2, blijft die waarde op het apparaat staan ondanks het opnieuw knipperen, updates van het besturingssysteem, enzovoort.

Zodra het knooppunt RequireNetworkInOOBE van tenantLockdown CSP's is ingesteld op true op HoloLens 2, wacht OOBE voor onbepaalde tijd totdat het Autopilot-profiel is gedownload en toegepast, na de netwerkverbinding.

Zodra het knooppunt RequireNetworkInOOBE van tenantLockdown CSP's is ingesteld op true op HoloLens 2, zijn de volgende bewerkingen niet toegestaan in OOBE:

- Lokale gebruiker maken met runtime-inrichting
- Azure AD-joinbewerking uitvoeren via runtime-inrichting
- Selecteren wie de eigenaar van het apparaat is in OOBE-ervaring

#### <a name="how-to-set-this-using-intune"></a>Hoe kunt u dit instellen met Intune?

1. Maak een aangepast OMA URI-apparaatconfiguratieprofiel en geef true op voor het knooppunt RequireNetworkInOOBE, zoals hieronder wordt weergegeven.
Oma-URI-waarde moet ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE zijn

   > [!div class="mx-imgBorder"]
   > ![Vergrendelingsvergrendeling instellen via OMA-URI.](images/hololens-tenant-lockdown.png)

1. Maak een groep en wijs het apparaatconfiguratieprofiel toe aan die apparaatgroep.

1. Maak het HoloLens 2 apparaatlid van de groep die u in de vorige stap hebt gemaakt en synchronisatie activeren.  

Controleer in de Intune-portal of de apparaatconfiguratie is toegepast. Zodra deze apparaatconfiguratie is toegepast op HoloLens 2 apparaat, zijn de effecten van TenantLockdown actief.

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a>RequireNetworkInOOBE van TenantLockdown in een HoloLens 2 in Intune?

1. Verwijder de HoloLens 2 de apparaatgroep waaraan de hierboven gemaakte apparaatconfiguratie eerder is toegewezen.

1. Maak een aangepast op OMA URI gebaseerd apparaatconfiguratieprofiel en geef false op voor RequireNetworkInOOBE, zoals hieronder wordt weergegeven.
Oma-URI-waarde moet ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE zijn

   > [!div class="mx-imgBorder"]
   > ![Schermopname van het instellen van RequireNetworkInOOBE op false via OMA URI in Intune.](images/hololens-tenant-lockdown-false.png)

1. Maak een groep en wijs het apparaatconfiguratieprofiel toe aan die apparaatgroep.

1. Maak het HoloLens 2 apparaatlid van de groep die u in de vorige stap hebt gemaakt en synchronisatie activeren.

Controleer in de Intune-portal of de apparaatconfiguratie is toegepast. Zodra deze apparaatconfiguratie is toegepast op HoloLens 2 apparaat, zijn de effecten van TenantLockdown inactief.

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a>Wat zou er gebeuren tijdens OOBE, als het Autopilot-profiel niet is toegewezen aan een HoloLens nadat TenantLockdown is ingesteld op true?

OOBE wacht voor onbepaalde tijd tot het Autopilot-profiel is gedownload en het volgende dialoogvenster wordt weergegeven. Als u de effecten van TenantLockdown wilt verwijderen, moet het apparaat eerst worden geregistreerd bij de oorspronkelijke tenant met behulp van Autopilot en requireNetworkInOOBE moet niet zijn ingesteld zoals beschreven in de vorige stap voordat de beperkingen die door TenantLockdown CSP zijn geïntroduceerd, worden verwijderd.

![In de apparaatweergave voor wanneer beleid wordt afgedwongen op het apparaat.](images/hololens-autopilot-lockdown.png)

Deze informatie vindt u nu samen met de rest van Autopilot onder [Tenantlockdown CSP en Autopilot.](hololens2-autopilot.md#tenant-lockdown-csp-and-autopilot)

### <a name="global-assigned-access--kiosk-mode"></a>Globale toegewezen toegang - kioskmodus

- Minder identiteitsbeheer voor Kiosk door de nieuwe kioskmethode in te schakelen waarmee de kioskmodus op systeemniveau wordt toegepast.

Met deze nieuwe functie kan een IT-beheerder een HoloLens 2-apparaat configureren voor de kioskmodus voor meerdere apps die van toepassing is op systeemniveau, geen affiniteit heeft met een identiteit in het systeem en van toepassing is op iedereen die zich bij het apparaat heeft meldt. Meer informatie over deze nieuwe functie wordt uitgebreid beschreven in [HoloLens kioskmodus](hololens-kiosk.md).

### <a name="automatic-launch-of-an-application-in-multiple-app-kiosk-mode"></a>Automatisch starten van een toepassing in de kioskmodus voor meerdere apps

- Gerichte ervaring met het automatisch starten van apps, waardoor de gebruikersinterface en app-selecties die zijn gekozen voor kioskmodus nog verder toenemen.

Is alleen van toepassing op de kioskmodus voor meerdere apps en er kan slechts één app worden aangewezen voor automatisch starten met behulp van het gemarkeerde kenmerk hieronder in de configuratie toegewezen toegang.

De toepassing wordt automatisch gestart wanneer de gebruiker zich meldt.

```xml
<AllowedApps>                     
    <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
```

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>Wijzigingen in het gedrag van de kioskmodus voor het afhandelen van fouten

- Veiligere kioskmodus door beschikbare apps in kioskmodusfouten te elimineren.

Eerder zijn er fouten bij het toepassen van de kioskmodus HoloLens gebruikt om alle toepassingen weer te geven in het menu Start. In Windows Holographic-versie 20H2 in het geval van fouten worden er geen apps weergegeven in het menu Start, zoals hieronder:

![Afbeelding van de kioskmodus die er nu uitziet wanneer deze mislukt.](images/hololens-kiosk-failure-behavior.png )

### <a name="hololens-policies"></a>HoloLens Beleid

- Opties voor apparaatbeheer die specifiek zijn HoloLens gemaakt voor het beheren van het apparaat.

Er mixed reality nieuwe beleidsregels voor HoloLens 2 gemaakt op Windows Holographic-versie 20H2. Nieuwe beheerbare instellingen zijn onder andere: helderheid instellen, volume instellen, audio-opname uitschakelen in mixed reality-opnamen, instellen wanneer diagnostische gegevens kunnen worden verzameld en AAD groepslidmaatschapcache.  

| Nieuw HoloLens beleid                                | Description                                                                               | Notities                                                                |
|----------------------------------------------------|-------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| MixedReality\BrightnessButtonDisabled              | Hiermee kunnen helderheidsknoppen worden uitgeschakeld, zodat de helderheid niet wordt gewijzigd door op de knop te drukken.       | 1 Ja, 0 Nee (standaard)                                                |
| MixedReality\VolumeButtonDisabled                  | Hiermee kunt u volumeknoppen worden uitgeschakeld, zodat het volume niet wordt gewijzigd door er op te drukken.               | 1 Ja, 0 Nee (standaard)                                                |
| MixedReality\MicrophoneDisabled                    | Hiermee schakelt u de microfoon uit, zodat er geen audio-opname mogelijk is op HoloLens 2.                      | 1 Ja, 0 Nee (standaard)                                                |
| MixedReality\FallbackDiagnostics                   | Hiermee bepaalt u het gedrag van wanneer diagnostische logboeken kunnen worden verzameld.                               | 0 Uitgeschakeld, 1 ingeschakeld voor apparaateigenaren, 2 ingeschakeld voor iedereen (standaard) |
| MixedReality\HeadTrackingMode                      | Gereserveerd voor toekomstig gebruik.                                                                  |                                                                      |
| MixedReality\AADGroupMembershipCacheValidityInDays | Hiermee bepaalt u hoeveel dagen azure AD-groepslidmaatschapcache wordt gebruikt voor kiosken die zijn gericht op Azure AD-groepen. | Zie hieronder.                                                           |

### <a name="cache-azure-ad-group-membership-for-offline-kiosk"></a>Azure AD-groepslidmaatschap cachen voor offline kiosk

- Ingeschakelde offline kiosken kunnen maximaal 60 dagen AAD groepen worden gebruikt.

Met dit beleid bepaalt u hoe lang azure AD-groepslidmaatschapcache mag worden gebruikt voor configuraties voor toegewezen toegang die zijn gericht op Azure AD-groepen voor aangemelde gebruikers. Zodra deze beleidswaarde is ingesteld op een waarde die groter is dan 0, wordt de cache anders niet gebruikt.  

Naam: AADGroupMembershipCacheValidityInDays URI-waarde: ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

Min. - 0 dagen  
Maximaal - 60 dagen

Stappen om dit beleid correct te gebruiken:

1. Maak een apparaatconfiguratieprofiel voor kiosken die zijn gericht op Azure AD-groepen en wijs dit toe HoloLens apparaten.
1. Maak een aangepaste op OMA URI gebaseerde apparaatconfiguratie die deze beleidswaarde in stelt op het gewenste aantal dagen (> 0) en wijs deze toe aan HoloLens apparaten.
    1. De URI-waarde moet in het tekstvak OMA-URI worden ingevoerd als ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays
    1. De waarde kan tussen min. /max. zijn toegestaan.
1. Schrijf HoloLens apparaten in en controleer of beide configuraties op het apparaat worden toegepast.
1. Laat Azure AD-gebruiker 1 zich aanmelden wanneer internet beschikbaar is. Zodra de gebruiker zich heeft aanmelden en het Azure AD-groepslidmaatschap is bevestigd, wordt de cache gemaakt.
1. Azure AD-gebruiker 1 kan nu HoloLens offline halen en gebruiken voor de kioskmodus, zolang de beleidswaarde het aantal dagen toestaat.
1. Stap 4 en 5 kunnen worden herhaald voor elke andere Azure AD-gebruiker N. Het belangrijkste punt is dat elke Azure AD-gebruiker zich moet aanmelden bij het apparaat via internet, zodat ten minste één keer kan worden vastgesteld dat hij of zij lid is van de Azure AD-groep waarop de Kiosk-configuratie is gericht.

> [!NOTE]
> Tot stap 4 voor een Azure AD-gebruiker wordt uitgevoerd, t ervaart deze foutgedrag dat wordt vermeld in 'niet-verbonden' omgevingen.

### <a name="new-device-restriction-policies-for-hololens-2"></a>Nieuw apparaatbeperkingsbeleid voor HoloLens 2

- Hiermee kunnen gebruikers specifieke beleidsregels voor apparaatbeheer beheren, zoals het blokkeren van het toevoegen of verwijderen van inrichtingspakketten.

Nieuw ingeschakeld beleid waarmee meer beheeropties voor apparaten HoloLens 2 ingeschakeld.

- [AllowAddProvisioningPackage](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)
- [AllowRemoveProvisioningPackage](/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage)
- [ConfigureTimeZone](/windows/client-management/mdm/policy-csp-timelanguagesettings#timelanguagesettings-configuretimezone)
- [RemoteLock](/windows/client-management/mdm/remotelock-csp)

Deze twee nieuwe beleidsregels voor AllowAddProvisioningPackage en AllowRemoveProvisioningPackage worden toegevoegd aan onze [Algemene apparaatbeperkingen.](hololens-common-device-restrictions.md)

> [!NOTE]
> Met betrekking tot [RemoteLock](/windows/client-management/mdm/remotelock-csp)ondersteunt HoloLens alleen de configuratie ./Vendor/MSFT/RemoteLock/Lock. De configuraties die te maken hebben met pincodes, zoals opnieuw instellen en herstellen, worden niet ondersteund.

### <a name="new-power-policies-for-hololens-2"></a>Nieuw energiebeleid voor HoloLens 2

- Meer opties voor wanneer HoloLens slaapstand of vergrendelingen via energiebeleid.

Met deze nieuw toegevoegde beleidsregels kunnen beheerders energie-staten beheren, zoals time-out voor inactieve gegevens. Klik op de koppeling voor dat beleid voor meer informatie over elk afzonderlijk beleid.

|     Koppeling beleidsdocumentatie                |     Notities                                                                                                                                       |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
|     [DisplayOffTimeoutOnBattery](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery)               |     Voorbeeldwaarde die moet worden gebruikt in Windows Configuration Designer, dat wil zeggen,`<enabled/><data   id="EnterVideoDCPowerDownTimeOut" value="100"/>`     |
|     [DisplayOffTimeoutPluggedIn](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin)               |     Voorbeeldwaarde die moet worden gebruikt in Windows Configuration Designer, dat wil zeggen,`<enabled/><data   id="EnterVideoACPowerDownTimeOut" value="100"/>`     |
|     [EnergySaverBatteryThresholdOnBattery](/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdonbattery)     |  Voorbeeldwaarde die moet worden gebruikt in Windows Configuration Designer, dat wil zeggen 100                                                                             |
|     [EnergySaverBatteryThresholdPluggedIn](/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdpluggedin)     |     Voorbeeldwaarde die moet worden gebruikt in Windows Configuration Designer, dat wil zeggen 100                                                                          |
|     [StandbyTimeoutOnBattery](/windows/client-management/mdm/policy-csp-power#power-standbytimeoutonbattery)                  |     Voorbeeldwaarde die moet worden gebruikt in Windows Configuration Designer, dat wil zeggen,`<enabled/><data   id="EnterDCStandbyTimeOut" value="100"/>`          |
|     [StandbyTimeoutPluggedIn](/windows/client-management/mdm/policy-csp-power#power-standbytimeoutpluggedin)                  |     Voorbeeldwaarde die moet worden gebruikt in Windows Configuration Designer, dat wil zeggen,`<enabled/><data   id="EnterACStandbyTimeOut" value="100"/>`           |

Deze twee nieuwe beleidsregels voor DisplayOffTimeoutOnBattery en DisplayOffTimeoutPluggedIn worden toegevoegd aan [onze Algemene apparaatbeperkingen.](hololens-common-device-restrictions.md)

> [!NOTE]
> Zorg ervoor dat HoloLens 2 waarden voor DisplayOffTimeoutOnBattery en StandbyTimeoutOnBattery als dezelfde waarde zijn ingesteld voor consistente ervaring met de HoloLens 2. Hetzelfde geldt voor DisplayOffTimeoutPluggedIn en StandbyTimeoutPluggedIn. Raadpleeg [Inactieve timers weergeven, slaapstand](/windows-hardware/design/device-experiences/display--sleep--and-hibernate-idle-timers) en sluimerstand voor meer informatie over moderne stand-by.

### <a name="newly-enabled-update-policies-for-hololens"></a>Nieuw ingeschakeld Updatebeleid voor HoloLens

- Meer opties voor wanneer updates worden geïnstalleerd of de knop Updates onderbreken uitschakelen om updates te garanderen.

Deze updatebeleidsregels zijn nu ingeschakeld op HoloLens 2 apparaten:

- [Update/ActiveHoursEnd](/windows/client-management/mdm/policy-csp-update#update-activehoursend)
- [Update/ActiveHoursMaxRange](/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
- [Update/ActiveHoursStart](/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
- [Update/SetDisablePauseUXAccess](/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

Volledige informatie over deze updatebeleidsregels en hoe u deze kunt gebruiken voor HoloLens apparaten, kunt u hier lezen in [HoloLens beheren.](hololens-updates.md)

### <a name="enabled-settings-page-visibility-for-hololens-2"></a>Zichtbaarheid van Instellingen pagina ingeschakeld voor HoloLens 2

- Meer gebruikersinterfacebesturingselementen in de Instellingen App, wat kan worden verward met een beperkte selectie pagina's.

We hebben nu een beleid ingeschakeld waarmee IT-beheerders kunnen voorkomen dat specifieke pagina's in de System Instellingen-app zichtbaar of toegankelijk zijn, of om dit te doen voor alle pagina's behalve de pagina's die zijn opgegeven. Als u wilt weten hoe u deze functie volledig kunt aanpassen, klikt u op de onderstaande koppeling.

- [PageVisibilityList](/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)

Als u wilt weten welke pagina-instellingen u kunt aanpassen op HoloLens 2, gaat u naar onze [pagina Instellingen URI's.](settings-uri-list.md)

![Schermopname van actieve uren die worden gewijzigd in de Instellingen app.](images/hololens-page-visibility-list.jpg)

### <a name="research-mode"></a>Onderzoeksmodus

In de onderzoeksmodus wordt HoloLens 2 een hulpprogramma voor computer vision-onderzoek. Vergeleken met vorige edities heeft de onderzoeksmodus voor HoloLens 2 de volgende voordelen:

- Naast sensoren die worden blootgesteld in HoloLens onderzoeksmodus (eerste generatie), bieden we nu IMU-sensortoegang, waaronder een versnellingsmeter, eenscope en een teller.
- HoloLens 2 biedt nieuwe mogelijkheden die samen met de onderzoeksmodus kunnen worden gebruikt. Met name toegang tot verwoorde API's voor handtracking en oogtracking die een uitgebreidere set experimenten kunnen leveren.

Onderzoekers hebben nu de mogelijkheid om de onderzoeksmodus in te schakelen op hun HoloLens om toegang te krijgen tot al deze extern gerichte onbewerkte sensorenstromen. Onderzoeksmodus voor HoloLens 2 biedt ook toegang tot de snelheidsmeter,scope en snelheidsmetermetingen. Ter bescherming van de privacy van gebruikers zijn onbewerkte cameraafbeeldingen voor het bijhouden van ogen niet beschikbaar via de onderzoeksmodus, maar de richting van de ogen is beschikbaar via bestaande API's.

Bekijk de documentatie [voor de onderzoeksmodus](/windows/mixed-reality/research-mode) voor meer technische details.

### <a name="recording-length-increased"></a>Opnamelengte verhoogd

Vanwege feedback van klanten hebben we de opnamelengte van de [mixed reality opnamen verhoogd.](holographic-photos-and-videos.md) Mixed Reality-opnamen worden niet langer standaard beperkt tot vijf minuten, maar berekenen in plaats daarvan de maximale opnamelengte op basis van de beschikbare schijfruimte. Het apparaat schat de maximale duur van de video-opname op basis van de beschikbare schijfruimte tot 80% van de totale schijfruimte.

> [!NOTE]
> De HoloLens standaardlengte voor video-opname (5 minuten) als een van de volgende opties wordt gebruikt:
>
> - De geschatte maximale opnameduur is kleiner dan de standaardduur van 5 minuten.
> - De beschikbare schijfruimte is minder dan 20% van de totale schijfruimte.

U vindt de volledige vereisten in onze documentatie over [holografische foto's en video's.](holographic-photos-and-videos.md#maximum-recording-length)

### <a name="improvements-and-fixes-in-the-windows-holographic-version-20h2-update"></a>Verbeteringen en oplossingen in Windows Holographic, versie 20H2-update:

- Meer schermen in OOBE zijn nu in donkere modus.
- Meer inhoud moet naar de meest recente privacyverklaring online wijzen.
- Er is een probleem opgelost waarbij gebruikers geen VPN-profielen konden inrichten via inrichtingspakketten.
- Probleem met proxyconfiguratie voor VPN-verbinding opgelost.
- Beleid bijgewerkt om de enumeratie van USB-functies via MDM voor NCM voor AllowUsbConnection uit te schakelen.
- Er is een probleem opgelost waardoor een [HoloLens-apparaat](hololens-kiosk.md)niet kon worden weergegeven in Verkenner via Media Transfer Protocol (MTP) wanneer het apparaat is ingesteld als kiosk voor één app. Houd er rekening mee dat MTP (en USB-verbinding in het algemeen) nog steeds kan worden uitgeschakeld met behulp van het [beleid AllowUSBConnection.](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)
- Er is een probleem opgelost waarbij pictogrammen in de Startmenu correct werden geschaald in de kioskmodus.
- Er is een probleem opgelost omdat http-caching de kioskmodus verstoort die is gericht op Azure AD-groepen.
- Er is een probleem opgelost waarbij gebruikers de knop Koppelen niet konden gebruiken nadat ze de ontwikkelaarsmodus hadden ingeschakeld met inrichtingspakketten, tenzij ze de ontwikkelaarsmodus hebben uitgeschakeld en opnieuw hebben ingeschakeld.

## <a name="windows-holographic-version-1903---november-2020-update"></a>Windows Holographic, versie 1903 - update van november 2020

- Build 18362.1085

Deze maandelijkse kwaliteitsupdate bevat geen belangrijke wijzigingen. We raden u aan onze nieuwste build van de functiere release uit te proberen Windows Holographic versie 20H2.

## <a name="windows-holographic-version-2004---october-2020-update"></a>Windows Holographic, versie 2004 - update van oktober 2020

- Build 19041.1124

Verbeteringen en oplossingen in de update:

- Er is een onnodige controle verwijderd die een runtimesysteemfout heeft veroorzaakt.

## <a name="windows-holographic-version-1903---october-2020-update"></a>Windows Holographic, versie 1903 - update van oktober 2020

- Build 18362.1081

Deze maandelijkse kwaliteitsupdate bevat geen belangrijke wijzigingen. We raden u aan onze nieuwste builds voor Windows Holographic versie 2004 uit te proberen.

## <a name="windows-holographic-version-2004---september-2020-update"></a>Windows Holographic, versie 2004 - update van september 2020

- Build 19041.1117

Verbeteringen en oplossingen in de update:

- Lost een probleem op waardoor Visual Studio een toepassing niet kan debuggen wanneer SupportsMultipleInstances="true" aanwezig is in de appxmanifest.
- Deze release bevat een NCSI-proxydetectiefix voor het oplossen van mislukte internetdetectie via een netwerkproxy. NCSI kan machineproxy en proxy per profiel gebruiken voor detectie van internetverbinding. Proxy per gebruiker wordt ondersteund door NCSI in een toekomstige versie.
- Op de Windows Mixed Reality apparaten is de vector van de voorwaartse richting parallel aan de grond wanneer het hoofd van de gebruiker zich in een neutrale positie in de toekomst kijkt. Eerdere versies van HoloLens 2 echter de vector uitgelijnd om in plaats daarvan perpensaal te zijn ten opzichte van de weergavepanelen, die een paar graden omlaag wordt gekanteld ten opzichte van de ideale richting. Nieuwere versies van HoloLens 2 hebben dit gecorrigeerd om semantische consistentie tussen formulierfactoren te garanderen.
- Verbeterde robuustheid van handtracking die leidt tot minder traceringsverlies in specifieke scenario's.
- Deze release bevat een oplossing voor het verbeteren van de kwaliteit van audiotijdstempels die mogelijk hebben bijgedragen aan problemen met het vastleggen van video's.

## <a name="windows-holographic-version-1903---september-2020-update"></a>Windows Holographic, versie 1903 - update van september 2020

- Build 18362.1079

Verbeteringen en oplossingen in de update:

- Op de Windows Mixed Reality apparaten is de vector van de voorwaartse richting parallel aan de grond wanneer het hoofd van de gebruiker zich in een neutrale positie in de toekomst kijkt. Eerdere versies van HoloLens 2 echter de vector uitgelijnd om in plaats daarvan perpensaal te zijn ten opzichte van de weergavepanelen, die een paar graden omlaag wordt gekanteld ten opzichte van de ideale richting. Nieuwere versies van HoloLens 2 hebben dit gecorrigeerd om semantische consistentie tussen formulierfactoren te garanderen.
- Verbeterde robuustheid van handtracking die leidt tot minder traceringsverlies in specifieke scenario's.

## <a name="windows-holographic-version-2004---august-2020-update"></a>Windows Holographic, versie 2004 - update van augustus 2020

- Build 19041.1113

Verbeteringen en oplossingen in de update:

- Instellingen app wordt de gebruiker niet langer gevolgd in Iris-registratie of eye tracking-kalibratie-ervaringen.
- Er is een fout opgelost waarbij het toepassen van een inrichtingspakket tijdens OOBE dat de naam van het apparaat wijzigt en andere acties uitvoert (zoals verbinding maken met een netwerk), de andere acties na het opnieuw opstarten van het apparaat niet kan uitvoeren vanwege de naams wijzigen.
- Het kleurenschema van de initiële apparaatinstallatiestromen is gewijzigd om de visuele kwaliteit te verbeteren.

## <a name="windows-holographic-version-1903---august-2020-update"></a>Windows Holographic, versie 1903 - update van augustus 2020

- Build 18362.1074

Deze maandelijkse kwaliteitsupdate bevat geen belangrijke wijzigingen. We raden u aan onze nieuwste builds voor Windows Holographic versie 2004 uit te proberen.

## <a name="windows-holographic-version-2004---july-2020-update"></a>Windows Holographic, versie 2004 - update van juli 2020

- Build 19041.1109

Verbeteringen en oplossingen in de update:

- Ontwikkelaars kunnen nu kiezen tussen het in- of uitschakelen van Apparaatportal een beveiligde verbinding vereisen.
- De betrouwbaarheid is verbeterd voor toepassingslanceringen na updates van het besturingssysteem.
- De standaard helderheid van postvak IN is gewijzigd in 100 procent.
- Er is een probleem opgelost met doorsturen via HTTPS voor de Windows Apparaatportal op HoloLens 2.

## <a name="windows-holographic-version-1903---july-2020-update"></a>Windows Holographic, versie 1903 - update van juli 2020

- Build 18362.1071

Verbeteringen en oplossingen in de update:

- Er is een probleem opgelost dat ertoe kan leiden dat hologrammen in Unity-toepassingen verdwijnen wanneer ze verliezen of weer worden bijgezet.
- Er is een probleem opgelost waardoor exclusieve HoloLens-apps op bepaalde apparaten terug naar de shell zijn gecrasht tijdens het gebruik van de HoloLens Emulator met hardwareversnelling.
- Er is een probleem opgelost met betrekking tot https-doorsturen voor de Windows Apparaatportal op HoloLens 2.

## <a name="windows-holographic-version-2004---june-2020-update"></a>Windows Holographic, versie 2004 - update van juni 2020

- Build 19041.1106

Verbeteringen en oplossingen in de update:

- Aangepaste MRC-recorders hebben nu nieuwe standaardwaarden voor bepaalde eigenschappen als ze niet zijn opgegeven.
  - In het *MRC-video-effect:*
    - PreferredOgramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (Immersive headset))
  - Op het *MRC-audio-effect:*
    - LoopbackGain (de huidige waarde 'App Audio Gain' op Vastleggen in mixed reality pagina in Windows Apparaatportal)
    - MicrophoneGain (de huidige waarde voor 'Mic Audio Gain' op Vastleggen in mixed reality pagina in Windows Apparaatportal)
- Er is een fout opgelost om de audiokwaliteit te verbeteren in mixed reality capture-scenario's. Deze oplossing moet met name audiofoutjes in de opname elimineren wanneer het menu **Start** wordt weergegeven.
- De stabiliteit van hologrammen in opgenomen video's is verbeterd.
- Er is een probleem opgelost waarbij mixed reality video niet kon opnemen nadat het apparaat meerdere dagen stand-by was.
- De HolographicSpace.UserPresence-API is doorgaans uitgeschakeld voor Unity-toepassingen. Dit gedrag voorkomt een probleem waardoor sommige apps zijn onderbroken toen de visor werd gespiegeld, zelfs als de instelling 'Uitvoeren op de achtergrond' was ingeschakeld. De API is nu ingeschakeld voor Unity-versies 2018.4.18 en hoger en 2019.3.4 en hoger.
- Wanneer u toegang Apparaatportal via een Wi-Fi verbinding, kan een webbrowser de toegang tot verhinderen vanwege een ongeldig certificaat. De browser rapporteert mogelijk een fout zoals 'ERR_SSL_PROTOCOL_ERROR', zelfs als het apparaatcertificaat eerder is vertrouwd. In dit geval kunt u niet verder met Apparaatportal, omdat er geen optie is om beveiligingswaarschuwingen te negeren. Met deze update is het probleem opgelost. Als het apparaatcertificaat eerder is gedownload en vertrouwd op een pc om browserbeveiligingswaarschuwingen te verwijderen en de SSL-fout optreedt, moet het nieuwe certificaat worden gedownload en vertrouwd om browserbeveiligingswaarschuwingen te kunnen aanpakken.
- De mogelijkheid ingeschakeld om een runtime-inrichtingspakket te maken waarmee een app kan worden geïnstalleerd met behulp van MSIX-pakketten.
- Er is een instelling toegevoegd **in Instellingen** System Hologrammen waarmee gebruikers automatisch alle hologrammen van Mixed Reality huis kunnen verwijderen wanneer het  >    >   apparaat wordt afgesloten.
- Er is een probleem opgelost waardoor HoloLens apps die hun pixelindeling wijzigen, zwart in de emulator HoloLens weergegeven.
- Er is een fout opgelost die een crash heeft veroorzaakt tijdens het aanmelden bij Iris.
- Er is een probleem opgelost met herhaalde store-downloads voor apps die al actueel zijn.
- Er is een fout opgelost om te voorkomen dat in immersive apps Microsoft Edge geopend.
- Er is een probleem opgelost met de lanceringen van de Foto's-app in eerste instantie wordt bijgewerkt na het bijwerken vanaf de release van 1903.
- Verbeterde prestaties en betrouwbaarheid.

## <a name="windows-holographic-version-1903---june-2020-update"></a>Windows Holographic, versie 1903 - update van juni 2020

- Build 18362.1064

Verbeteringen en oplossingen in de update:

- Aangepaste MRC-recorders hebben nieuwe standaardwaarden voor bepaalde eigenschappen als ze niet zijn opgegeven.
  - In het *MRC-video-effect:*
    - PreferredOgramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (Immersive headset))
  - Op het *MRC-audio-effect:*
    - LoopbackGain (de huidige waarde 'App Audio Gain' op Vastleggen in mixed reality pagina in Windows Apparaatportal)
    - MicrophoneGain (de huidige waarde voor 'Mic Audio Gain' op Vastleggen in mixed reality pagina in Windows Apparaatportal)
- De HolographicSpace.UserPresence-API is doorgaans uitgeschakeld voor Unity-toepassingen. Dit gedrag voorkomt een probleem waardoor sommige apps worden onderbroken wanneer de visor wordt gespiegeld, zelfs als de instelling voor het uitvoeren op de achtergrond is ingeschakeld. De API is nu ingeschakeld voor Unity-versies 2018.4.18 en hoger en 2019.3.4 en hoger.
- Er is een probleem opgelost waardoor HoloLens apps die hun pixelindeling wijzigen, zwart in de HoloLens Emulator.
- Er is een probleem opgelost met de lanceringen van de Foto's-app in eerste instantie wordt bijgewerkt na het bijwerken vanaf de release van 1903.

## <a name="windows-holographic-version-2004"></a>Windows Holographic, versie 2004

- Build - 19041.1103

De belangrijkste software-update van mei 2020 voor *HoloLens 2, Windows Holographic, versie 2004* bevat tal van interessante nieuwe mogelijkheden, zoals ondersteuning voor Windows Autopilot, de donkere modus van de app, USB Ethernet-ondersteuning voor 5G/LTE-hotspots en nog veel meer. Als u wilt bijwerken naar de nieuwste versie, opent u **de** Instellingen-app, gaat u naar Update & Security en selecteert u de knop   Controleren op  **** **updates.**   

|             Functie                              |          Beschrijving                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       Windows Autopilot                          |          Nieuwe apparaten vooraf configureren en naadloos instellen voor productie met behulp van Windows AutoPilot                 |
|       FIDO 2-ondersteuning                             |          Ondersteuning voor FIDO2-beveiligingssleutels om snelle en veilige verificatie voor gedeelde apparaten mogelijk te maken            |
|       Verbeterde inrichting                      |          Naadloos een inrichtingspakket van een USB-station toepassen op uw HoloLens                              |
|       Installatiestatus van toepassing                 |          Controleer de installatiestatus in de Instellingen-app voor apps naar uw HoloLens 2 via MDM               |
|       Configuratieserviceproviders (CSP's)   |          Nieuwe configuratieserviceproviders toegevoegd om de beheermogelijkheden te verbeteren                 |
|       ONDERSTEUNING voor USB 5G/LTE                       |          Uitgebreide USB Ethernet-mogelijkheid biedt ondersteuning voor 5G/LTE                                    |
|       Donkere app-modus                              |          Donkere app-modus beschikbaar voor apps die zowel donkere als lichte modi ondersteunen, waardoor de weergave-ervaring wordt verbeterd        |
|       Spraakopdrachten                             |          Ondersteuning voor aanvullende systeemstemopdrachten voor het HoloLens handsfree                           |
|       Verbeteringen in handtracking                 |          Met verbeteringen in handtracking worden knoppen en 2D-slate-interacties nauwkeuriger                        |
|       Kwaliteitsverbeteringen en oplossingen                 |          Verschillende verbeteringen in de systeemprestaties en -betrouwbaarheid op het platform                            |

### <a name="support-for-windows-autopilot"></a>Ondersteuning voor Windows Autopilot

Windows Met Autopilot voor HoloLens 2 kan het verkoopkanaal van het apparaat vooraf HoloLens bij uw Intune-tenant. Wanneer apparaten binnenkomen, zijn ze klaar om zelf te implementeren als gedeelde apparaten onder uw tenant. Als u wilt profiteren van zelf-implementatie, moet het apparaat verbinding maken met een netwerk tijdens het eerste scherm in de installatie met behulp van een USB-C-naar-Ethernet.

Nadat een gebruiker het zelf-implementerende Autopilot-proces heeft gestart, worden de volgende stappen voltooid:

1. Voeg het apparaat toe aan Azure Active Directory (Azure AD).
1. Gebruik Azure AD om het apparaat in te schrijven bij Microsoft Intune (of een andere MDM-service).
1. Download het beleid, de certificaten en de netwerkprofielen die op het apparaat zijn gericht.
1. Het apparaat inrichten.
1. Het aanmeldingsscherm presenteren aan de gebruiker.

Meer informatie in de [Windows Autopilot voor HoloLens 2 evaluatiehandleiding.](hololens2-autopilot.md)

*Neem contact op met uw accountmanager om nu deel te nemen aan de AutoPilot-preview. Apparaten die gereed zijn voor Autopilot worden binnenkort beschikbaar.*

### <a name="fido2-security-key-support"></a>Ondersteuning voor FIDO2-beveiligingssleutels

Sommige gebruikers delen een HoloLens apparaat met anderen in een werk- of schoolomgeving. Het is dus belangrijk dat gebruikers eenvoudig lange gebruikersnamen en wachtwoorden kunnen typen. Met Fast Identity Online (FIDO) kan iedereen in uw organisatie (Azure AD-tenant) zich naadloos aanmelden bij HoloLens zonder een gebruikersnaam of wachtwoord in te voeren.

FIDO2-beveiligingssleutels zijn een 'unphishable' op standaarden gebaseerde verificatiemethode zonder wachtwoord die in elke vormfactor kan worden gebruikt. FIDO is een open standaard voor verificatie zonder wachtwoord. Hiermee kunnen gebruikers en organisaties zich aanmelden bij hun resources zonder gebruikersnaam of wachtwoord. In plaats daarvan gebruiken ze een externe beveiligingssleutel of een platformsleutel die is ingebouwd in een apparaat.

Zie Aanmelden met een beveiligingssleutel [zonder wachtwoord inschakelen om aan de slag te gaan.](/azure/active-directory/authentication/howto-authentication-passwordless-security-key)

### <a name="improved-mdm-enrollment-via-provisioning-package"></a>Verbeterde MDM-inschrijving via inrichtingspakket

Met inrichtingspakketten kunt u HoloLens configureren via een configuratiebestand in plaats van via HoloLens out-of-box-ervaring. Voorheen moesten inrichtingspakketten naar het interne geheugen HoloLens gekopieerd. Ze kunnen zich nu op een USB-station, zodat ze gemakkelijker te hergebruiken op meerdere HoloLens apparaten en u apparaten parallel kunt inrichten. Inrichtingspakketten ondersteunen nu ook een veld om in te schrijven voor apparaatbeheer, zodat er na het inrichten geen handmatige installatie is.

Ga als volgende te werk om het uit te proberen:

1. Download de nieuwste versie van de Windows Configuration Designer vanuit de Windows store op uw pc.
1. Selecteer **Inrichten HoloLens Apparaten**  >  **Inrichten HoloLens 2 apparaten.**
1. Bouw uw configuratieprofiel. Kopieer vervolgens alle bestanden die zijn gemaakt naar een USB-C-opslagapparaat.
1. Sluit het USB-C-apparaat aan op een zojuist geflitst HoloLens. Druk vervolgens op de **aan/uit-knoppen** op het volume  +   om uw inrichtingspakket toe te passen.

### <a name="line-of-business-application-install-status"></a>Installatiestatus van Line-Of-Business-toepassing

De implementatie en het beheer van MDM-apps voor Line-Of-Business-apps is essentieel voor HoloLens. Beheerders en gebruikers moeten de installatiestatus van de app bekijken voor controle en diagnose. In deze release hebben we meer informatie toegevoegd in **Instellingen**  >  **Accounts** Access work or  >  **school (Toegang**  >    >  tot werk of school) Klik op uw account Info .

### <a name="additional-csps-and-policies"></a>Aanvullende CSP's en beleidsregels

Een [configuratieserviceprovider (CSP)](/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN) is een interface voor het lezen, instellen, wijzigen of verwijderen van configuratie-instellingen op een apparaat. In deze release voegen we ondersteuning toe voor meer beleid om de controle te vergroten die beheerders hebben over geïmplementeerde HoloLens apparaten. Zie [NetworkQoSPolicy CSP](/windows/client-management/mdm/networkqospolicy-csp)HoloLens de lijst met CSP's die worden ondersteund door HoloLens.

Nieuw in deze release:

**Policy-CSP** 

Met de serviceprovider Beleidsconfiguratie kan de onderneming beleidsregels configureren op Windows apparaten. In deze release hebben we nieuwe beleidsregels toegevoegd voor HoloLens, die hier worden vermeld. Zie Beleids-CSP's die worden [ondersteund door HoloLens 2 voor meer HoloLens 2.](/windows/client-management/mdm/policies-supported-by-hololens2)  

- LetAppsAccessCamera_ForceAllowTheseApps  
- LetAppsAccessCamera_ForceDenyTheseApps  
- LetAppsAccessCamera_UserInControlOfTheseApps
- LetAppsAccessGazeInput
- LetAppsAccessGazeInput_ForceAllowTheseApps
- LetAppsAccessGazeInput_ForceDenyTheseApps
- LetAppsAccessGazeInput_UserInControlOfTheseApps
- LetAppsAccessMicrophone_ForceAllowTheseApps
- LetAppsAccessMicrophone_ForceDenyTheseApps
- LetAppsAccessMicrophone_UserInControlOfTheseApps
- AllowWiFi

**NetworkQoSPolicy CSP**

De NetworkQoSPolicy-configuratieserviceprovider maakt QoS-beleid (Quality of Service) voor netwerken. Een QoS-beleid voert een set acties uit op netwerkverkeer op basis van een set overeenkomende voorwaarden. Zie [NetworkQoSPolicy CSP voor meer informatie.](/windows/client-management/mdm/networkqospolicy-csp)

### <a name="expanded-usb-ethernet-support-for-5glte-tethered-devices"></a>Uitgebreide USB Ethernet-ondersteuning voor 5G/LTE-tethered apparaten

Er is ondersteuning toegevoegd voor het inschakelen van bepaalde mobiele breedbandapparaten, zoals 5G/LTE-telefoons en Wi-Fi-hotspots, wanneer ze via USB aan de HoloLens 2 zijn aangesloten. Deze apparaten worden nu weergegeven in **netwerkinstellingen als** een andere Ethernet-verbinding. (Mobiele breedbandapparaten waarvoor een extern stuurprogramma is vereist, worden niet ondersteund.) Deze functionaliteit maakt verbindingen met hoge bandbreedte mogelijk wanneer Wi-Fi beschikbaar is en Wi-Fi tethering niet goed genoeg presteert. Zie Voor meer informatie over ondersteunde USB-apparaten [Verbinding maken voor Bluetooth en USB-C-apparaten.](hololens-connect-devices.md)  

### <a name="hand-tracking-improvements"></a>Verbeteringen in handtracking

Deze release bevat verschillende verbeteringen voor het bijhouden van de hand:

- **Wijzende houdingstabiliteit:** Het systeem weerstaat nu het gebruik van de wijsvinger wanneer deze wordt occludeerd door de man. Deze wijziging verbetert de nauwkeurigheid wanneer u knoppen, type, schuifinhoud en meer pusht. 
- **Minder onbedoelde tikken in de lucht:** We hebben de detectie van het tikken in de lucht verbeterd. Er zijn nu minder onbedoelde activeringen in verschillende veelvoorkomende scenario's, zoals wanneer u uw handen aan uw zijden laat vallen.
- **Betrouwbaarheid van gebruikersschakelaar:** Het systeem is nu sneller en betrouwbaarder in het bijwerken van de handgrootte wanneer u een apparaat deelt.
- **Minder hand steelt:** We hebben de verwerking van gevallen verbeterd waarbij er meer dan twee handen in beeld zijn van de sensoren. Als meerdere personen dicht bij elkaar werken, is de kans nu veel kleiner dat de bij te houden hand van de gebruiker naar de hand van iemand anders in de scène gaat.
- **Systeembetrouwbaarheid:** Er is een probleem opgelost waardoor het bijhouden van de hand niet meer werkt wanneer het apparaat wordt belast.

### <a name="dark-mode"></a>Donkere modus

Veel Windows ondersteunen nu zowel donkere als lichte modi. HoloLens 2 kunnen de standaardmodus kiezen voor apps die beide ondersteunen. Na de update is de standaard-app-modus 'donker', maar u kunt deze instelling eenvoudig wijzigen: Navigeer **naar Instellingen**  >  **Systeemkleuren** Kies uw  >    >  **standaard-app-modus.**

Deze 'in-box'-apps ondersteunen de donkere modus:

- Instellingen
- Microsoft Store
- Mail
- Kalender
- Verkenner
- Feedback-hub
- OneDrive
- Foto's
- 3D-viewer
- Films & TV

![Donkere modus windows tegel.](images/DarkMode.jpg)

### <a name="system-voice-commands"></a>Systeemsytemeopdrachten

U kunt nu spraakopdrachten gebruiken met elke app op het apparaat. Zie Use your voice to operate HoloLens [(Uw stem gebruiken om te werken met HoloLens.](hololens-cortana.md) Zie ook [Ondersteunde talen voor HoloLens 2.](hololens2-language-support.md)  

### <a name="cortana-updates"></a>Cortana updates

De bijgewerkte app is geïntegreerd met Microsoft 365 om meer gedaan te krijgen op uw apparaten (momenteel alleen US-English beschikbaar). Op HoloLens 2 biedt Cortana geen ondersteuning meer voor bepaalde apparaatspecifieke opdrachten, zoals het aanpassen van het volume of opnieuw opstarten. Deze opties worden nu ondersteund door de nieuwe systeemstemopdrachten. Meer informatie over de nieuwe Cortana-app in onze [blog](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/).

### <a name="quality-improvements-and-fixes"></a>Kwaliteitsverbeteringen en oplossingen

Verbeteringen en oplossingen ook in de update:  

- Er is een actief weergave-kalibratiesysteem geïntroduceerd. Deze functie verbetert de stabiliteit en uitlijning van hologrammen. Ze blijven nu op hun plaats wanneer u uw hoofd van links naar rechts verplaatst.
- Er is een fout opgelost waarbij Wi-Fi streaming HoloLens periodiek werd onderbroken. Als een toepassing aangeeft dat streaming met lage latentie nodig is, implementeert u de oplossing door de [functie SetSocketMediaStreamingMode aan te roepen.](/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode)
- Er is een apparaat vast komen te hangen dat zich tijdens het streamen in de onderzoeksmodus voordeed.
- Er is een fout opgelost waarbij in sommige gevallen de juiste gebruiker niet op het aanmeldingsscherm zou worden weergegeven bij het hervatten van een sessie.
- Er is een probleem opgelost waarbij gebruikers MDM-logboeken niet konden exporteren via **Instellingen.**
- Er is een probleem opgelost waarbij de nauwkeurigheid van het bijhouden van de ogen direct na de out-of-box-installatie mogelijk lager is dan verwacht.
- Er is een probleem opgelost waarbij het subsysteem voor oogtracking onder bepaalde omstandigheden geen kalibratie kon initialiseren of uitvoeren.
- Er is een probleem opgelost waarbij de ooginterbrabratie zou worden gevraagd naar een gebruiker die al is ge kalibreerd.
- Er is een probleem opgelost waarbij een stuurprogramma zou crashen tijdens het maken van een oog.
- Er is een probleem opgelost waarbij herhaalde aan/uit-knop-drukken een systeem-time-out van 60 seconden en een shell-crash kon veroorzaken.
- Verbeterde stabiliteit voor dieptebuffers.
- Er is **een knop** Delen toegevoegd aan Feedback-hub zodat gebruikers gemakkelijker feedback kunnen delen.
- Er is een fout opgelost waarbij RoboRaid WAN niet juist is geïnstalleerd.

### <a name="known-issues"></a>Bekende problemen

- Een probleem met de systeemtaal zh-CN voorkomt dat spraakopdrachten een mixed reality het IP-adres van het apparaat vastleggen of weergeven.
- Voor een probleem moet u de app Cortana starten nadat het apparaat is geactiveerd om spraakactivering "Hey Cortana" te gebruiken. Als u van een 18362-build hebt bijgewerkt, ziet u mogelijk ook een tweede app-tegel voor de vorige versie van de Cortana-app die niet meer werkt in **Start.**

## <a name="windows-holographic-version-1903---may-2020-update"></a>Windows Holographic, versie 1903 - Update van mei 2020

- Build 18362.1061

Deze maandelijkse kwaliteitsupdate bevat geen belangrijke wijzigingen omdat het team aan de Windows Holographic-versie 2004 May Update werkte, zoals eerder beschreven.

## <a name="windows-holographic-version-1903---april-2020-update"></a>Windows Holographic, versie 1903 - Update van april 2020

- Build 18362.1059

**Donkere modus voor ondersteunde apps**

Veel Windows bieden ondersteuning voor zowel de donkere als de lichte modus. HoloLens 2 kunnen klanten nu de standaardmodus kiezen voor apps die ondersteuning bieden voor beide kleurenschema's. Op basis van feedback van klanten stellen we de standaard-app-modus in op 'donker', maar u kunt deze instelling eenvoudig op elk moment wijzigen: Navigeer naar **Instellingen > System > Colors** om te zoeken naar 'Kies uw **standaard-app-modus'.**

Deze 'in-box'-apps ondersteunen de donkere modus:

- Instellingen
- Microsoft Store
- Mail
- Kalender
- Verkenner
- Feedback-hub
- OneDrive
- Foto's
- 3D-viewer
- Films & TV

**Verbeteringen en oplossingen ook in de update:**

- Ervoor gezorgd dat shell-overlays zijn opgenomen in mixed reality captures.
- Onwerkelijke ontwikkelaars kunnen nu de pagina 3D-weergave in Apparaatportal om hun toepassingen te testen en fouten op te sporen.
- Verbeterde hologramstabiliteit in mixed reality vastleggen wanneer het *holographicDepthReprojectionMethod DepthReprojection-algoritme* wordt gebruikt.
- De fout 'WinRT IStreamSocketListener API Class not registered' in 32-bits ARM-apps is opgelost.

## <a name="windows-holographic-version-1903---march-2020-update"></a>Windows Holographic, versie 1903 - Update van maart 2020

- Build 18362.1056

Verbeteringen en oplossingen in de update:

- Verbeterde hologramstabiliteit in mixed reality vastleggen wanneer het *HolographicDepthReprojectionMethod AutoPlanar-algoritme* wordt gebruikt.
- Ervoor gezorgd dat het coördinaatsysteem dat is gekoppeld aan een diepte-MF-voorbeeld consistent is met openbare documentatie.
- Verbeterde productiviteit voor ontwikkelaars door klanten in staat te stellen grote hoeveelheden tekst via de apparaatportal te plakken.

## <a name="windows-holographic-version-1903---february-2020-update"></a>Windows Holographic, versie 1903 - Update van februari 2020

- Build 18362.1053

Verbeteringen en oplossingen in de update:

- De HolographicSpace.UserPresence-API voor Unity-toepassingen is tijdelijk uitgeschakeld. Deze wijziging voorkomt een probleem waardoor sommige apps werden onderbroken toen het visor werd gespiegeld, zelfs als de instelling 'Uitvoeren op de achtergrond' was ingeschakeld.
- Er is een willekeurige HUP-crash opgelost die werd veroorzaakt door het bijhouden van de hand, waarbij de gebruiker zag dat de gebruikersinterface na enkele seconden opnieuw werd vastgezet in de shell.
- Verbeterde handtracking, zodat wanneer u met uw wijsvinger gaat werken, het bovenste deel van die vinger minder snel onverwacht gaat curlen.
- Verbeterde betrouwbaarheid van headtracking, ruimtelijke toewijzing en andere runtimes.

## <a name="windows-holographic-version-1903---january-2020-update"></a>Windows Holographic, versie 1903 - Update van januari 2020

- Build 18362.1043

Verbeteringen en oplossingen in de update:

- Verbeterde stabiliteit voor exclusieve apps bij het werken met HoloLens 2 emulator.

## <a name="windows-holographic-version-1903---december-2019-update"></a>Windows Holographic, versie 1903 - Update van december 2019

- Build 18362.1042

Verbeteringen en oplossingen in de update:

- Er zijn oplossingen geïntroduceerd voor het reproduceren van de laatste fase (LSR). Verbeterde visuele weergave van hologrammen om stabieler en helder te worden weergegeven door nauwkeuriger rekening te houden met hun diepte. Dit symptoom is na deze update beter zichtbaar als apps de diepte van hologrammen niet correct instellen.
- De stabiliteit van exclusieve apps en navigatie tussen exclusieve apps zijn hersteld.
- Er is een probleem opgelost waarbij mixed reality video niet kon opnemen nadat het apparaat enkele dagen stand-by was.
- Verbeterde hologram-stabiliteit.

## <a name="windows-holographic-version-1903---november-2019-update"></a>Windows Holographic, versie 1903 - Update van november 2019

- Build 18362.1039

Verbeteringen en oplossingen in de update:

- De functionaliteit van **Spraakopdrachten** selecteren tijdens de eerste installatie voor en-CA en en-AU is opgelost.
- Verbeterde visuele kwaliteit van objecten die ver weg zijn geplaatst in de meest recente versies van Unity Mixed Reality Toolkit (MRTK).
- Problemen opgelost met holografische toepassingen die vast komen te zitten in een onderbroken status bij het opstarten totdat de Startmenu geopend en vervolgens gesloten.
- Oplossingen en verbeteringen voor openXR-runtime-conformiteit voor HoloLens 2 en de emulator.
