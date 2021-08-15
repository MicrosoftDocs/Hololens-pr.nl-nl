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
ms.date: 04/01/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: df0cb555c8445ef4d8f8165996a33e0f8c1a38653b45514594f893e3c761f65a
ms.sourcegitcommit: 9615ed824bdf3f1747ec346da6136704d8eed015
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/11/2021
ms.locfileid: "120364282"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Insider-preview voor Microsoft HoloLens

Welkom bij de nieuwste Insider Preview-builds voor HoloLens. Het is eenvoudig om aan [de slag te gaan](hololens-insider.md#start-receiving-insider-builds) en waardevolle feedback te geven voor onze volgende belangrijke update van het besturingssysteem voor HoloLens.

## <a name="windows-insider-release-notes"></a>Windows Opmerkingen bij de release van Insider

We zijn blij dat we weer nieuwe functies kunnen Windows Insiders. Nieuwe builds worden naar de dev- en bètakanalen gerouteert voor de nieuwste updates. We blijven deze pagina bijwerken wanneer we meer functies en updates toevoegen aan onze Windows Insider-builds. Word enthousiast en bereid u voor om deze updates in uw realiteit te combineren.

| Functie                 | Beschrijving                | Gebruiker of scenario | Build geïntroduceerd |
|-------------------------|----------------------------|--------------|------------------|
| [CSP-wijzigingen voor rapportagegegevens HoloLens details](#csp-changes-for-reporting-hololens-details) | Nieuwe CSP's voor om query's uit te voeren op gegevens | IT-beheerders    | 20348.1403                 |
| [Beleid voor automatisch aanmelden beheerd door CSP](#auto-login-policy-controlled-by-csp) | Wordt gebruikt om automatisch aan te melden bij een account | IT-beheerders | 20348.1405 |
| [Ondersteuning van PFX-bestanden voor Certificaatbeheer](#pfx-file-support-for-certificate-manager) | PFX-certificaten toevoegen via Instellingen UI | Eindgebruiker | 20348.1405 |
| [Geavanceerd diagnostisch rapport weergeven in Instellingen op HoloLens](#view-advanced-diagnostic-report-in-settings-on-hololens) | Diagnostische MDM-logboeken op het apparaat weergeven | Problemen oplossen | 20348.1405 |
| [Offline diagnostische meldingen](#offline-diagnostics-notifications) | Feedback geven over het verzamelen van logboeken | Problemen oplossen | 20348.1405 |
| [Alleen persoonlijke Store-apps gebruiken voor Microsoft Store](#use-only-private-store-apps-for-microsoft-store) | De Store-app configureren om alleen apps van de organisatie weer te geven | IT-beheerder | 20348.1408 |
| [Verbeteringen aan logboekverzameling met lage opslag](#low-storage-log-collection-improvements) | Verbeteringen in scenario's voor logboekverzameling tijdens situaties met weinig opslag. | IT-beheerder | 20348.1412 |
| [Platformmodus verplaatsen](#moving-platform-mode) | Introduceert de bètaversie van de moving platformmodus, die, wanneer deze is geconfigureerd, het gebruik van HoloLens 2 mogelijk maakt op grote zeepaden die te maken hebben met weinig dynamische beweging. | Alles | 20348.1411 |
| [Oplossingen en verbeteringen](#fixes-and-improvements) | Oplossingen en verbeteringen voor HoloLens. | Alles | 20348.1411 |

### <a name="csp-changes-for-reporting-hololens-details"></a>CSP-wijzigingen voor rapportagegegevens HoloLens details

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

Dit nieuwe beleid AutoLogonUser bepaalt of een gebruiker automatisch wordt aangemeld. Sommige klanten willen apparaten instellen die zijn gekoppeld aan een identiteit, maar geen aanmeldingservaring willen. Imagine apparaat ophalen en direct hulp op afstand gebruiken. Of hebben een voordeel van het snel distribueren van HoloLens apparaten en hun eindgebruikers in staat stellen zich sneller aan te melden.

Wanneer het beleid is ingesteld op een niet-lege waarde, wordt het e-mailadres van de gebruiker voor automatische aanmelding opgegeven. De opgegeven gebruiker moet zich ten minste één keer bij het apparaat laten aanmelding inschakelen.

De OMA-URI van nieuwe `./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser` beleidsreekswaarde

- De gebruiker met hetzelfde e-mailadres heeft automatische aanmelding ingeschakeld.

Op een apparaat waarop dit beleid is geconfigureerd, moet de gebruiker die is opgegeven in het beleid ten minste één keer worden aanmelding. Als het apparaat na de eerste aanmelding opnieuw wordt opgestart, wordt de opgegeven gebruiker automatisch aangemeld. Er wordt slechts één gebruiker voor automatische aanmelding ondersteund. Zodra deze is ingeschakeld, kan de automatisch aangemelde gebruiker zich niet meer handmatig afmelden. Als u zich als een andere gebruiker wilt laten aanmeldingen, moet het beleid eerst worden uitgeschakeld.

> [!NOTE]
> - Voor sommige gebeurtenissen, zoals belangrijke updates van het besturingssysteem, moet de opgegeven gebruiker zich mogelijk opnieuw bij het apparaat laten aanmeldingen om automatisch aanmeldingsgedrag te hervatten. 
> - Automatische aanmelding wordt alleen ondersteund voor MSA- en AAD-gebruikers.

### <a name="pfx-file-support-for-certificate-manager"></a>Ondersteuning van PFX-bestanden voor Certificaatbeheer

Geïntroduceerd in Windows Insider-build 20348.1405. Er is nu ondersteuning toegevoegd aan [Certificaatbeheer om PFX-certificaten](certificate-manager.md) te gebruiken. Wanneer gebruikers naar **Instellingen** Update & Security Certificates gaan en Een certificaat installeren selecteren, ondersteunt de gebruikersinterface nu het  >    >  PFX-certificaatbestand. 
Gebruikers kunnen een PFX-certificaat met een persoonlijke sleutel importeren in een gebruikers- of machineopslag.

### <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a>Geavanceerd diagnostisch rapport weergeven in Instellingen op HoloLens

Voor beheerde apparaten bij het oplossen van problemen is het bevestigen dat een verwachte beleidsconfiguratie wordt toegepast een belangrijke stap. Voorheen moest dit voor deze nieuwe functie buiten het apparaat worden uitgevoerd via MDM of in de buurt van het apparaat na het exporteren van diagnostische MDM-logboeken die zijn verzameld via  ->  **Instellingen-accounts** Toegang tot werk of  >  **school,** en selecteert u **Uw beheerlogboeken** exporteren en weergeven op een pc in de buurt.

De MDM-diagnostische gegevens kunnen nu worden weergegeven op het apparaat met behulp van de Edge-browser. Als u het diagnostischE MDM-rapport eenvoudiger wilt weergeven, gaat u naar de pagina Werk- of schoolrapport openen en **selecteert u Geavanceerd diagnostisch rapport weergeven.** Hiermee wordt het rapport gegenereerd en geopend in een nieuw Edge-venster.

![Geavanceerde diagnostische gegevens weergeven in Instellingen app.](./images/view-advanced-diagnostic-report.jpg)

### <a name="offline-diagnostics-notifications"></a>Offline diagnostische meldingen

Dit is een update voor een bestaande functie met de [naam Offlinediagnose.](hololens-diagnostic-logs.md#offline-diagnostics) Voorheen was er geen duidelijke indicator voor gebruikers dat ze de diagnostische verzameling hadden geactiveerd of dat deze was voltooid.
Nu toegevoegd aan Windows Insider-builds, zijn er twee soorten feedback voor offlinediagnose. De eerste zijn pop-upmeldingen die worden weergegeven voor zowel wanneer de verzameling wordt gestart als voltooid. Deze worden weergegeven wanneer de gebruiker is aangemeld en visuals heeft.

![Pop-up voor het verzamelen van logboeken.](./images/logcollection1.jpg)

![Pop-up wanneer het verzamelen van logboeken is voltooid.](./images/logcollection2.jpg)
 
Omdat gebruikers vaak offlinediagnose gebruiken als mechanisme voor het verzamelen van terugvallogboeken wanneer ze geen toegang hebben tot een weergave, zich niet kunnen aanmelden of zich nog steeds in OOBE kunnen aanmelden, wordt er ook een audio-cue afgespeeld wanneer logboeken worden verzameld. Dit geluid wordt afgespeeld naast de pop-upmelding.

Deze nieuwe functie wordt ingeschakeld wanneer uw apparaat wordt bijgewerkt en hoeft niet te worden ingeschakeld of beheerd. In elk geval dat deze nieuwe feedback niet kan worden weergegeven of gehoord, wordt offlinediagnose nog steeds gegenereerd.

We hopen dat het met deze nieuwere toevoeging van feedback gemakkelijker is om diagnostische gegevens te verzamelen en sneller in staat te zijn om uw problemen op te lossen.

### <a name="use-only-private-store-apps-for-microsoft-store"></a>Alleen persoonlijke Store-apps gebruiken voor Microsoft Store

Het beleid RequirePrivateStoreOnly is ingeschakeld voor HoloLens. Met dit beleid kan Microsoft Store-app zodanig worden geconfigureerd dat alleen de persoonlijke opslag wordt weer te geven die voor uw organisatie is geconfigureerd. Beperk de toegang tot alleen de apps die u beschikbaar hebt gemaakt.

Meer informatie over [ApplicationManagement/RequirePrivateStoreOnly](http://windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly)

### <a name="low-storage-log-collection-improvements"></a>Verbeteringen aan logboekverzameling met lage opslag

In scenario's waarin een apparaat weinig schijfruimte lijkt te hebben wanneer diagnostische logboeken worden verzameld, wordt er een extra rapport met de **StorageDiagnostics.zip** gemaakt. De drempelwaarde voor lage opslag wordt automatisch bepaald door de Windows [opslag te bepalen.](https://support.microsoft.com/office/use-onedrive-and-storage-sense-in-windows-10-to-manage-disk-space-de5faa9a-6108-4be1-87a6-d90688d08a48)

### <a name="moving-platform-mode"></a>Platformmodus verplaatsen

Vanaf **Insider build 20348.1411** hebben we bètaondersteuning toegevoegd voor het bijhouden van laag dynamische bewegingsplatforms op HoloLens 2. Nadat u de build hebt geïnstalleerd en de Moving Platform-modus hebt inschakelen, kunt u uw HoloLens 2 gebruiken in eerder ontoegankelijke omgevingen, zoals grote schip en grote 12-30-2018. Op dit moment is de functie gericht op het inschakelen van deze specifieke platformen voor verplaatsen. Hoewel niets u verhindert om de functie in andere omgevingen te gebruiken, is de functie gericht op het toevoegen van ondersteuning voor deze omgevingen.

Ga naar de platformpagina voor verplaatsen voor meer informatie over wat wordt ondersteund en hoe u deze nieuwe functie [kunt inschakelen.](hololens2-moving-platform.md)

### <a name="fixes-and-improvements"></a>Oplossingen en verbeteringen

- Er is een bekend probleem opgelost voor Apparaatportal er geen prompt [was om vergrendelde bestanden te downloaden.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)
- Er is [een bekend probleem opgelost voor Apparaatportal met time-outs voor](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out) het uploaden en downloaden van bestanden.
- Behandelt problemen met het rapporteren van nalevingseigenschappen van HoloLens apparaten; Opnieuw opstarten kan vereist zijn om de juiste rapportage te kunnen starten op Insider-builds.  
- Een TOEGEWEZEN [toegangs-API](/uwp/api/windows.system.userprofile.assignedaccesssettings?view=winrt-20348) ingeschakeld, zodat apps nu kunnen bepalen of een HoloLens wordt uitgevoerd in een kioskmodus voor de gebruiker die is aangemeld bij de HoloLens.
- De in-box-versie van Remote Assist bijgewerkt die is geïnstalleerd op nieuwe flashes.

## <a name="start-receiving-insider-builds"></a>Beginnen met het ontvangen van Insider-builds

> [!NOTE]
> Als u het apparaat niet recent hebt bijgewerkt, start u het apparaat opnieuw op om de status bij te werken en de nieuwste build op te halen.
> - De spraakopdracht 'Apparaat opnieuw opstarten' werkt goed. 
> - U kunt ook de knop Opnieuw opstarten kiezen in Instellingen/Windows Insider-programma.
>
> Er is een fout in de back-end die u mogelijk hebt aangetroffen, zodat u weer op schema komt.

Ga op HoloLens 2 apparaat naar **Instellingen**  >  **Update & Security**  >  **Windows Insider-programma** en selecteer **Aan de slag.** Koppel het account dat u hebt gebruikt om u te registreren als Windows Insider.

Windows insider gaat nu over op Kanalen. De **Snelle** ring wordt het **Dev-kanaal,** de langzame **ring** wordt de **bèta-kanaal** en de **Release Preview-ring** wordt het **Release Preview-kanaal.** Deze toewijzing ziet er als volgende uit:

![Windows Uitleg van Insider Channels](images/WindowsInsiderChannels.png)

Zie [Introducing Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) (Introductie Windows Insider Channels) op Windows Blogs.
Selecteer vervolgens **Actieve ontwikkeling van Windows**, kies of u het **Dev-kanaal** wilt ontvangen of bèta-kanaal **builds** en bekijk de programmavoorwaarden.
Selecteer **Bevestigen > Nu opnieuw opstarten om** te voltooien. Nadat het apparaat opnieuw is opgestart, gaat u naar **Instellingen > Update & Security > Controleren** op updates om de nieuwste build te downloaden.

### <a name="update-error-0x80070490-work-around"></a>Updatefout 0x80070490 work-around

Als er een updatefout wordt 0x80070490 bij het bijwerken op het kanaal Dev of Beta, probeert u de volgende kortetermijnversie. Dit omvat het verplaatsen van uw insider-kanaal, het ophalen van de update en vervolgens het terug verplaatsen van uw Insider-kanaal.

#### <a name="stage-one---release-preview"></a>Fase 1 - preview-versie

1.  Instellingen, Update & Security en selecteer Windows Insider-programma **Release Preview Channel.**

2.  Instellingen, Update & Security, Windows Update, Check **for updates**. Na de update gaat u verder met Fase 2.

#### <a name="stage-two---dev-channel"></a>Fase 2 - Dev-kanaal

1. Instellingen, Update & Security en selecteer Windows Insider-programma **Dev Channel.**

2. Instellingen, Update & Security, Windows Update, Check **for updates**.

## <a name="ffu-download-and-flash-directions"></a>FFU-download- en flashbeschrijvingen

Als u wilt testen met een met een vlucht ondertekende ffu, moet u eerst uw apparaat ontgrendelen voordat de met de vlucht ondertekende ffu wordt geflitst.

1. Op pc:
    1. Download ffu naar uw pc vanaf [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .
    
    1. Installeer ARC (Advanced Recovery Companion) vanuit de Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .
    
1. Op HoloLens- Ontgrendelen met vlucht: **open** Instellingen Update & Security Windows Insider-programma registreer u en start  >    >   het apparaat opnieuw op.

1. Flash-FFU: u kunt nu de met de vlucht ondertekende FFU flashen met behulp van ARC.

### <a name="provide-feedback-and-report-issues"></a>Feedback geven en problemen rapporteren

Gebruik de [Feedback-hub-app op](hololens-feedback.md) uw HoloLens feedback te geven en problemen te melden. Het Feedback-hub zorgt ervoor dat alle benodigde diagnostische gegevens worden opgenomen om onze technici te helpen snel fouten op te sporen en het probleem op te lossen.  Problemen met de Chinese en Japanse versie van HoloLens moeten op dezelfde manier worden gerapporteerd.

> [!NOTE]
> Zorg ervoor dat u de prompt accepteert waarin wordt gevraagd of u Feedback-hub documenten wilt openen (selecteer **Ja** wanneer u hier om wordt gevraagd).

## <a name="note-for-developers"></a>Opmerking voor ontwikkelaars

U bent welkom en aangemoedigd om uw toepassingen te ontwikkelen met insider-builds van HoloLens.  Bekijk de documentatie [HoloLens ontwikkelaars om](https://developer.microsoft.com/windows/mixed-reality/development) aan de slag te gaan. Deze instructies werken met Insider-builds van HoloLens.  U kunt dezelfde builds van Unity en Visual Studio die u al gebruikt voor HoloLens ontwikkeling.

## <a name="stop-receiving-insider-builds"></a>Ontvangst van Insider-builds stoppen

Als u geen Insider-builds van Windows Holographic meer wilt ontvangen, kunt u zich uitloggen wanneer uw [](hololens-recovery.md) HoloLens een productie-build wordt uitgevoerd. U kunt uw apparaat ook herstellen met behulp van advanced recovery Companion om uw apparaat te herstellen naar een niet-Insider-versie van Windows Holographic.

> [!CAUTION]
> Er is een bekend probleem waarbij gebruikers die de registratie van Insider Preview-builds ongedaan maken nadat ze handmatig een nieuwe preview-build hebben geïnstalleerd, een blauw scherm krijgen. Daarna moeten ze hun apparaat handmatig herstellen. Bekijk meer over dit bekende probleem voor meer informatie over of dit al dan niet [wordt beïnvloed.](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)

Controleren of uw HoloLens een productie-build wordt uitgevoerd:

1. Ga naar **Instellingen > System > About** en zoek het buildnummer.

1. [Zie de releasenotities voor productie-buildnummers.](hololens-release-notes.md)

Als u zich wilt af melden voor Insider-builds:

1. Ga op HoloLens met een productie-build naar Instellingen > **Update & Security > Windows Insider-programma** en selecteer **Stop Insider builds.**

1. Volg de instructies om uw apparaat uit te kiezen.
