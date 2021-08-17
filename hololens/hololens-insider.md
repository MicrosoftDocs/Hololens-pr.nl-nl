---
title: Insider-preview voor Microsoft HoloLens
description: Leer hoe u aan de slag gaat met Insider-builds en waardevolle feedback kunt geven voor onze volgende belangrijke update van het besturingssysteem voor HoloLens.
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 08/19/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 3ccb9d0f7175a358262c39c76d364aee464c5469
ms.sourcegitcommit: e2a3e85882b7c594d73d08fbd7ae85856d22f8c5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/16/2021
ms.locfileid: "122213907"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Insider-preview voor Microsoft HoloLens

Welkom bij de nieuwste Insider Preview-builds voor HoloLens. Het is eenvoudig om aan de [slag te gaan](hololens-insider.md#start-receiving-insider-builds) en waardevolle feedback te geven voor onze volgende belangrijke update van het besturingssysteem voor HoloLens.

## <a name="windows-insider-release-notes"></a>Windows Opmerkingen bij de release van Insider

We zijn blij om nieuwe functies opnieuw te kunnen Windows Insiders. Voor nieuwe builds worden de dev- en bètakanalen gebruikt voor de nieuwste updates. We blijven deze pagina bijwerken wanneer we meer functies en updates toevoegen aan onze Windows Insider-builds. Word enthousiast en bereid u voor om deze updates in uw realiteit te combineren.

| Functie                 | Beschrijving                | Gebruiker of scenario | Build geïntroduceerd |
|-------------------------|----------------------------|--------------|------------------|
| [CSP-wijzigingen voor rapportage HoloLens details](#csp-changes-for-reporting-hololens-details) | Nieuwe CSP's voor om gegevens op te vragen | IT-beheerders    | 20348.1403                 |
| [Beleid voor automatisch aanmelden beheerd door CSP](#auto-login-policy-controlled-by-csp) | Wordt gebruikt om automatisch aan te melden bij een account | IT-beheerders | 20348.1405 |
| [Verbeterde detectie van opnieuw opstarten van updates en meldingen](#improved-update-restart-detection-and-notifications) | Nieuw ingeschakelde politie en UX voor updates. | IT-beheerders | 20348.1405 |
| [PfX-bestandsondersteuning voor Certificaatbeheer](#pfx-file-support-for-certificate-manager) | PFX-certificaten toevoegen via Instellingen UI | Eindgebruiker | 20348.1405 |
| [Slim opnieuw proberen voor app-updates](#smart-retry-for-app-updates) | Hiermee kunnen IT-beheerders geplande nieuwe proberen om apps bij te werken. | IT-beheerders | 20348.1405 |
| [Geavanceerd diagnostisch rapport weergeven in Instellingen op HoloLens](#view-advanced-diagnostic-report-in-settings-on-hololens) | Diagnostische MDM-logboeken weergeven op apparaat | Problemen oplossen | 20348.1405 |
| [Offline diagnostische meldingen](#offline-diagnostics-notifications) | Feedback over het verzamelen van logboeken | Problemen oplossen | 20348.1405 |
| [Alleen persoonlijke Store-apps gebruiken voor Microsoft Store](#use-only-private-store-apps-for-microsoft-store) | De Store-app configureren om alleen apps van de organisatie weer te geven | IT-beheerder | 20348.1408 |
| [Verbeteringen in het verzamelen van logboeken met weinig opslag](#low-storage-log-collection-improvements) | Verbeteringen in scenario's voor logboekverzameling tijdens situaties met weinig opslag. | IT-beheerder | 20348.1412 |
| [Platformmodus verplaatsen](#moving-platform-mode) | Introduceert de bètaversie van de Moving Platform-modus, die, wanneer geconfigureerd, het gebruik van HoloLens 2 op grote auto's met een lage dynamische beweging mogelijk maakt. | Alles | 20348.1411 |
| [Oplossingen en verbeteringen](#fixes-and-improvements) | Oplossingen en verbeteringen voor HoloLens. | Alles | 20348.1411 |

### <a name="csp-changes-for-reporting-hololens-details"></a>CSP-wijzigingen voor rapportage HoloLens details

- Geïntroduceerd in Windows Insider-build, 20348.1403

De volgende CSP's zijn bijgewerkt met nieuwe manieren om informatie van uw HoloLens rapporteren.

#### <a name="devdetail-csp---free-storage"></a>DevDetail CSP - Gratis Storage

DevDetail CSP rapporteert nu ook vrije opslagruimte op HoloLens apparaat. Dit moet ongeveer overeenkomen met de waarde die wordt weergegeven op Instellingen pagina van Storage app. Hieronder volgt het specifieke knooppunt met deze informatie.

- ./DevDetail/Ext/Microsoft/FreeStorage (alleen GET-bewerking)

#### <a name="devicestatus-csp---ssid-and-bssid"></a>DeviceStatus CSP - SSID en BSSID

DeviceStatus CSP rapporteert nu ook SSID en BSSID van Wi-Fi netwerk waarmee HoloLens actief is verbonden. Hieronder vindt u de specifieke knooppunten die deze informatie bevatten.

- ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/mac address *of Wi-Fi adapter*/SSID
- ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/mac address *of Wi-Fi adapter*/BSSID

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

Dit nieuwe beleid AutoLogonUser bepaalt of een gebruiker automatisch wordt aangemeld. Sommige klanten willen apparaten instellen die zijn gekoppeld aan een identiteit, maar geen aanmeldingservaring willen. Imagine apparaat ophalen en direct hulp op afstand gebruiken. Of u hebt het voordeel dat u snel uw apparaten HoloLens distribueert en hun eindgebruikers in staat stelt om de aanmelding te versnellen.

Wanneer het beleid is ingesteld op een niet-lege waarde, wordt het e-mailadres van de gebruiker voor automatische aanmelding opgegeven. De opgegeven gebruiker moet zich ten minste één keer bij het apparaat laten aanmelding inschakelen.

De OMA-URI van nieuwe `./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser` beleidsreekswaarde

- De gebruiker met hetzelfde e-mailadres heeft automatische aanmelding ingeschakeld.

Op een apparaat waarop dit beleid is geconfigureerd, moet de gebruiker die is opgegeven in het beleid ten minste één keer worden aanmelding. Na het opnieuw opstarten van het apparaat na de eerste aanmelding wordt de opgegeven gebruiker automatisch aangemeld. Er wordt slechts één gebruiker voor automatische aanmelding ondersteund. Zodra deze functie is ingeschakeld, kan de automatisch aangemelde gebruiker zich niet meer handmatig afmelden. Als u zich als een andere gebruiker wilt laten aanmeldingen, moet het beleid eerst worden uitgeschakeld.

> [!NOTE]
>
> - Voor sommige gebeurtenissen, zoals belangrijke updates van het besturingssysteem, moet de opgegeven gebruiker zich mogelijk opnieuw bij het apparaat laten aanmeldingen om automatisch aanmeldingsgedrag te hervatten.
> - Automatische aanmelding wordt alleen ondersteund voor MSA- en AAD-gebruikers.

### <a name="improved-update-restart-detection-and-notifications"></a>Verbeterde detectie van opnieuw opstarten van updates en meldingen

Tussen actieve uren en het beleid voor de installatietijd is het mogelijk om te voorkomen dat apparaten HoloLens opnieuw worden opgestart wanneer ze in gebruik zijn. Het zou echter ook de acceptatie van updates vertragen als opnieuw wordt opgestart om de installatie van een vereiste update te voltooien. We hebben nu beleidsregels toegevoegd om IT deadlines en vereiste herstarts te laten afdwingen en ervoor te zorgen dat de installatie van een update tijdig wordt voltooid. Gebruikers kunnen een melding ontvangen voordat het opnieuw opstarten wordt gestart en ze kunnen het opnieuw opstarten vertragen in overeenstemming met het IT-beleid.

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

### <a name="pfx-file-support-for-certificate-manager"></a>PfX-bestandsondersteuning voor Certificaatbeheer

Geïntroduceerd in Windows Insider build 20348.1405. We hebben nu ondersteuning toegevoegd aan [Certificaatbeheer om PFX-certificaten](certificate-manager.md) te gebruiken. Wanneer gebruikers naar **Instellingen** Update & Security Certificates gaan en Een certificaat installeren selecteren, ondersteunt de gebruikersinterface nu het  >    >  PFX-certificaatbestand. 
Gebruikers kunnen een PFX-certificaat met een persoonlijke sleutel importeren in een gebruikers- of machineopslag.

### <a name="smart-retry-for-app-updates"></a>Slim opnieuw proberen voor app-updates

Nu ingeschakeld voor HoloLens is een nieuw beleid waarmee IT-beheerders een terugkerende of eenmalige datum kunnen instellen om apps opnieuw op te starten waarvan de update is mislukt omdat de app in gebruik is, zodat de update kan worden toegepast. Deze kunnen worden ingesteld op basis van een aantal verschillende triggers, zoals een gepland tijdstip of aanmelding. Zie [ApplicationManagement/ScheduleForceRestartForUpdateFailures](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-scheduleforcerestartforupdatefailures)voor meer informatie over het gebruik van dit beleid.

### <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a>Geavanceerd diagnostisch rapport weergeven in Instellingen op HoloLens

Voor beheerde apparaten bij het oplossen van problemen is het bevestigen dat een verwachte beleidsconfiguratie wordt toegepast een belangrijke stap. Voorheen moest dit voor deze nieuwe functie via MDM of in de buurt van het apparaat worden gedaan na het exporteren van diagnostische MDM-logboeken die zijn verzameld via  ->  **Instellingen-accounts** Toegang tot werk of  >  **school,** en selecteert u **Uw** beheerlogboeken exporteren en weergeven op een pc in de buurt.

De MDM-diagnose kan nu worden weergegeven op het apparaat met behulp van de Edge-browser. Als u het diagnostischE MDM-rapport eenvoudiger wilt weergeven, gaat u naar de pagina Werk- of schoolrapport openen en **selecteert u Geavanceerd diagnostisch rapport weergeven.** Hiermee wordt het rapport gegenereerd en geopend in een nieuw Edge-venster.

![Bekijk het geavanceerde diagnostische rapport in Instellingen app.](./images/view-advanced-diagnostic-report.jpg)

### <a name="offline-diagnostics-notifications"></a>Offline diagnostische meldingen

Dit is een update voor een bestaande functie met de [naam Offline Diagnostics](hololens-diagnostic-logs.md#offline-diagnostics). Voorheen was er geen duidelijke indicator voor gebruikers dat ze het verzamelen van diagnostische gegevens hadden geactiveerd of dat deze was voltooid.
Nu toegevoegd aan Windows Insider-builds, zijn er twee soorten feedback over offlinediagnose. De eerste is pop-upmeldingen die worden weergegeven voor zowel wanneer de verzameling wordt gestart als voltooid. Deze worden weergegeven wanneer de gebruiker is aangemeld en visuals heeft.

![Pop-up voor het verzamelen van logboeken.](./images/logcollection1.jpg)

![Pop-up wanneer het verzamelen van logboeken is voltooid.](./images/logcollection2.jpg)

Omdat gebruikers vaak offlinediagnose gebruiken als mechanisme voor het verzamelen van terugvallogboeken voor wanneer ze geen toegang hebben tot een weergave, zich niet kunnen aanmelden of zich nog steeds in OOBE aanmelden, wordt er ook een audio-cue afgespeeld wanneer logboeken worden verzameld. Dit geluid wordt afgespeeld naast de pop-upmelding.

Deze nieuwe functie wordt ingeschakeld wanneer uw apparaat wordt bijgewerkt en hoeft niet te worden ingeschakeld of beheerd. In elk geval dat deze nieuwe feedback niet kan worden weergegeven of gehoord, wordt offlinediagnose nog steeds gegenereerd.

We hopen dat het met deze nieuwere toevoeging van feedback gemakkelijker is om diagnostische gegevens te verzamelen en sneller in staat zijn om uw problemen op te lossen.

### <a name="use-only-private-store-apps-for-microsoft-store"></a>Alleen persoonlijke Store-apps gebruiken voor Microsoft Store

Het beleid RequirePrivateStoreOnly is ingeschakeld voor HoloLens. Met dit beleid kan Microsoft Store-app zodanig worden geconfigureerd dat alleen de persoonlijke opslag wordt weer geven die voor uw organisatie is geconfigureerd. De toegang beperken tot alleen de apps die u beschikbaar hebt gemaakt.

Meer informatie over [ApplicationManagement/RequirePrivateStoreOnly](http://windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly)

### <a name="low-storage-log-collection-improvements"></a>Verbeteringen in het verzamelen van logboeken met weinig opslag

In scenario's waarin een apparaat weinig schijfruimte lijkt te hebben wanneer diagnostische logboeken worden verzameld, wordt een extra rapport met de **StorageDiagnostics.zip** gemaakt. De drempelwaarde voor lage opslag wordt automatisch bepaald door de Windows [opslag.](https://support.microsoft.com/office/use-onedrive-and-storage-sense-in-windows-10-to-manage-disk-space-de5faa9a-6108-4be1-87a6-d90688d08a48)

### <a name="moving-platform-mode"></a>Platformmodus verplaatsen

Vanaf **Insider-build 20348.1411** is bètaondersteuning toegevoegd voor het bijhouden van bewegingsplatformen met weinig dynamische beweging op HoloLens 2. Nadat u de build hebt geïnstalleerd en de moving platformmodus hebt inschakelen, kunt u uw HoloLens 2 gebruiken in eerder ontoegankelijke omgevingen, zoals grote vrachten en grote zeebaars. Op dit moment is de functie gericht op het inschakelen van deze specifieke platformen voor verplaatsen. Hoewel niets voorkomt dat u de functie in andere omgevingen probeert te gebruiken, is de functie gericht op het toevoegen van ondersteuning voor deze omgevingen.

Ga naar de pagina voor het verplaatsen van platformen voor meer informatie over wat wordt ondersteund en hoe u deze nieuwe functie [kunt inschakelen.](hololens2-moving-platform.md)

### <a name="fixes-and-improvements"></a>Oplossingen en verbeteringen

- Er is een bekend probleem opgelost Apparaatportal er geen prompt [was om vergrendelde bestanden te downloaden.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)
- Er is [een bekend probleem opgelost Apparaatportal problemen met time-outs voor](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out) het uploaden en downloaden van bestanden.
- Behandelt problemen met het rapporteren van nalevingseigenschappen van HoloLens apparaten; Opnieuw opstarten kan vereist zijn om de juiste rapportage te kunnen triggeren op Insider-builds.  
- Er is een [API voor](/uwp/api/windows.system.userprofile.assignedaccesssettings?view=winrt-20348) toegewezen toegang ingeschakeld, zodat apps nu kunnen bepalen of een HoloLens wordt uitgevoerd in de kioskmodus voor de gebruiker die is aangemeld bij de HoloLens.
- De in-box-versie van de Remote Assist is geïnstalleerd op nieuwe flashes.

## <a name="start-receiving-insider-builds"></a>Beginnen met het ontvangen van Insider-builds

> [!NOTE]
> Als u het apparaat niet recent hebt bijgewerkt, start u het apparaat opnieuw op om de status bij te werken en de nieuwste build op te halen.
>
> - De spraakopdracht 'Apparaat opnieuw opstarten' werkt goed.
> - U kunt ook de knop Opnieuw opstarten kiezen in Instellingen/Windows Insider-programma.
>
> Er is een fout in de back-end die u mogelijk hebt aangetroffen, zodat u weer op schema komt.

Ga op HoloLens 2 apparaat naar **Instellingen**  >  **Update & Security**  >  **Windows Insider-programma** en selecteer **Aan de slag.** Koppel het account dat u hebt gebruikt om u te registreren als Windows Insider.

Windows insider wordt verplaatst naar Kanalen. De **Fast-ring** wordt **het Dev-kanaal,** de langzame **ring** wordt de **bèta-kanaal** en de **Release Preview-ring** wordt het **Release Preview-kanaal.** Deze toewijzing ziet er als volgende uit:

![Windows Uitleg insider-kanalen](images/WindowsInsiderChannels.png)

Zie [Introducing Windows Insider Channels (Introductie Windows Insider-kanalen)](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) op Windows Blogs.
Selecteer vervolgens **Actieve ontwikkeling van Windows**, kies of u **Dev Channel-** of **bèta-kanaal-builds** wilt ontvangen en bekijk de programmavoorwaarden.
Selecteer **Bevestigen > Nu opnieuw opstarten om** te voltooien. Nadat het apparaat opnieuw is opgestart, gaat u naar **Instellingen > Update & Security > Controleren** op updates om de meest recente build op te halen.

### <a name="update-error-0x80070490-work-around"></a>Updatefout 0x80070490 work-around

Als er een updatefout 0x80070490 tijdens het bijwerken op het kanaal Dev of Beta, kunt u de volgende kortetermijnwerkfase proberen. Het omvat het verplaatsen van uw insider-kanaal, het ophalen van de update en vervolgens het terug verplaatsen van uw Insider-kanaal.

#### <a name="stage-one---release-preview"></a>Fase 1 - releasevoorbeeld

1. Instellingen, Update & Security en Windows Insider-programma **Release Preview Channel.**

2. Instellingen, & bijwerken, Windows Bijwerken, Controleren op **updates.** Na de update gaat u verder met Fase 2.

#### <a name="stage-two---dev-channel"></a>Fase 2 - Dev Channel

1. Instellingen, Update & Security en Windows Insider-programma **Dev Channel.**

2. Instellingen, & bijwerken, Windows Bijwerken, Controleren op **updates.**

## <a name="ffu-download-and-flash-directions"></a>FFU-download- en flashbeschrijvingen

Als u wilt testen met een ffu die is ondertekend met een vlucht, moet u eerst uw apparaat ontgrendelen voordat de ffu met een ondertekende vlucht wordt geflitst.

1. Op pc:
    1. Download ffu naar uw pc vanaf [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .

    1. Installeer ARC (Advanced Recovery Companion) vanuit de Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .

1. On HoloLens- Flight Unlock: Open **Instellingen** Update & Security Windows Insider-programma registreer het apparaat  >    >   en start het opnieuw op.

1. Flash-FFU: u kunt nu de met vlucht ondertekende FFU flashen met behulp van ARC.

### <a name="provide-feedback-and-report-issues"></a>Feedback geven en problemen melden

Gebruik de [Feedback-hub-app op](hololens-feedback.md) uw HoloLens feedback te geven en problemen te melden. Door Feedback-hub zorgt u ervoor dat alle benodigde diagnostische gegevens worden opgenomen om onze technici te helpen het probleem snel op te sporen en op te lossen.  Problemen met de Chinese en Japanse versie van HoloLens moeten op dezelfde manier worden gerapporteerd.

> [!NOTE]
> Zorg ervoor dat u de prompt accepteert waarin u wordt gevraagd of u Feedback-hub documenten wilt openen (selecteer **Ja** wanneer u hier om wordt gevraagd).

## <a name="note-for-developers"></a>Opmerking voor ontwikkelaars

U bent welkom en aangemoedigd om uw toepassingen te ontwikkelen met insider-builds van HoloLens.  Bekijk de documentatie [HoloLens ontwikkelaars om aan](https://developer.microsoft.com/windows/mixed-reality/development) de slag te gaan. Dezelfde instructies werken met Insider-builds van HoloLens.  U kunt dezelfde builds van Unity en Visual Studio die u al gebruikt voor HoloLens ontwikkeling.

## <a name="stop-receiving-insider-builds"></a>Geen Insider-builds meer ontvangen

Als u geen Insider-builds van Windows Holographic meer wilt ontvangen, kunt u zich uitloggen wanneer uw [](hololens-recovery.md) HoloLens een productie-build wordt uitgevoerd, of u kunt uw apparaat herstellen met behulp van advanced recovery companion om uw apparaat te herstellen naar een niet-Insider-versie van Windows Holographic.

> [!CAUTION]
> Er is een bekend probleem waarbij gebruikers die de registratie van Insider Preview-builds ongedaan maken nadat ze handmatig een nieuwe preview-build hebben geïnstalleerd, een blauw scherm krijgen. Daarna moeten ze hun apparaat handmatig herstellen. Bekijk meer over dit bekende probleem voor meer informatie over of u hier al dan niet [mee te maken zou krijgen.](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)

Controleren of uw HoloLens een productie-build wordt uitgevoerd:

1. Ga naar **Instellingen > System > About** en zoek het buildnummer.

1. [Zie de releasenotities voor productie-buildnummers.](hololens-release-notes.md)

Als u zich wilt af melden voor Insider-builds:

1. Ga op HoloLens met een productie-build naar Instellingen > **Update & Security > Windows Insider-programma** en selecteer Stop Insider **builds.**

1. Volg de instructies om uw apparaat uit te kiezen.
