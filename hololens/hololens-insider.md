---
title: Insider-preview voor Microsoft HoloLens
description: Leer hoe u aan de slag kunt gaan met Insider-builds en waardevolle feedback kunt geven voor onze volgende belangrijke update van het besturingssysteem voor HoloLens.
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
ms.openlocfilehash: a4949ab68121cb772fdb8a62411ed70868a6ccb6
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924363"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Insider-preview voor Microsoft HoloLens

Welkom bij de nieuwste Insider Preview-builds voor HoloLens. Het is eenvoudig om aan de slag [te gaan](hololens-insider.md#start-receiving-insider-builds) en waardevolle feedback te geven voor onze volgende belangrijke update van het besturingssysteem voor HoloLens.

## <a name="windows-insider-release-notes"></a>Windows Insider opmerkingen bij de release

We zijn blij dat we weer nieuwe functies aan Windows Insiders kunnen toevoegen. Nieuwe builds worden naar de dev- en bètakanalen gerouteert voor de nieuwste updates. We blijven deze pagina bijwerken wanneer we meer functies en updates toevoegen aan onze Windows Insider builds. Word enthousiast en bereid u voor om deze updates in uw realiteit te combineren. 

### <a name="csp-changes-on-hololens"></a>CSP-wijzigingen in HoloLens
 
- Geïntroduceerd in Windows Insider build, 20348.1403

#### <a name="devdetail-csp"></a>DevDetail CSP

DevDetail CSP rapporteert nu ook vrije opslagruimte op een HoloLens-apparaat. Dit moet ongeveer overeenkomen met de waarde die wordt weergegeven op de pagina Opslag van de app Instellingen. Hieronder vindt u het specifieke knooppunt met deze informatie.

- ./DevDetail/Ext/Microsoft/FreeStorage (alleen GET-bewerking)

#### <a name="devicestatus-csp"></a>DeviceStatus CSP

DeviceStatus CSP rapporteert nu ook SSID en BSSID van het Wifi-netwerk waarmee HoloLens actief is verbonden. Hieronder vindt u de specifieke knooppunten die deze informatie bevatten.

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

### <a name="fixes-and-improvements"></a>Oplossingen en verbeteringen:

- Er is een bekend probleem opgelost voor Apparaatportal er geen prompt [was om vergrendelde bestanden te downloaden.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)
- Er is [een bekend probleem opgelost voor Apparaatportal met time-outs voor](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out) het uploaden en downloaden van bestanden.

## <a name="start-receiving-insider-builds"></a>Beginnen met het ontvangen van Insider-builds
> [!NOTE]
> Als u het apparaat niet recent hebt bijgewerkt, start u het apparaat opnieuw op om de status bij te werken en de nieuwste build op te halen.
> - De spraakopdracht 'Apparaat opnieuw opstarten' werkt goed. 
> - U kunt ook de knop Opnieuw opstarten kiezen in Instellingen/Windows Insider-programma.
>
> Er is een fout in de back-end die u mogelijk hebt aangetroffen, zodat u weer op schema komt.

Ga op HoloLens 2 apparaat **naar**  >  **InstellingenUpdate & beveiligingsbeleid**  >  **Windows Insider-programma** selecteer **Aan de slag.** Koppel het account dat u hebt gebruikt om u te registreren als Windows Insider.
Windows Insider wordt nu verplaatst naar Kanalen. De **Fast-ring** wordt het **Dev-kanaal,** de langzame **ring** wordt de **bèta-kanaal** en de **Release Preview-ring** wordt het **Release Preview-kanaal.** Hier ziet u hoe die toewijzing eruit ziet: Windows Insider Uitleg van kanalen Zie Introductie ![ ](images/WindowsInsiderChannels.png) Windows Insider [kanalen](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) in Windows-blogs voor meer informatie.
Selecteer vervolgens **Actieve ontwikkeling van Windows,** kies of u het **Dev-kanaal** wilt ontvangen of bèta-kanaal **builds** en bekijk de programmavoorwaarden.
Selecteer **Bevestigen > Nu opnieuw opstarten om** te voltooien. Nadat het apparaat opnieuw is opgestart, gaat u naar Instellingen **> Update & Security > Controleren** op updates om de meest recente build op te halen.
### <a name="update-error-0x80070490-work-around"></a>Updatefout 0x80070490 work-around
Als er een updatefout wordt 0x80070490 bij het bijwerken op het kanaal Dev of Beta, probeert u de volgende kortetermijnversie. Dit omvat het verplaatsen van uw insider-kanaal, het ophalen van de update en vervolgens het terug verplaatsen van uw Insider-kanaal.
#### <a name="stage-one---release-preview"></a>Fase 1 - preview-versie
1.  Instellingen, Update & Beveiliging, Windows Insider-programma selecteer **Release Preview-kanaal.**
2.  Instellingen, & bijwerken, Windows Update, **Controleren op updates.** Na de update gaat u verder met Fase 2.
#### <a name="stage-two---dev-channel"></a>Fase 2 - Dev-kanaal
1. Instellingen, Update & Security en selecteer Windows Insider-programma **Dev Channel.**
2. Instellingen, & bijwerken, Windows Update, **Controleren op updates.**
## <a name="ffu-download-and-flash-directions"></a>FFU-download- en flashbeschrijvingen
Als u wilt testen met een met een vlucht ondertekende ffu, moet u eerst uw apparaat ontgrendelen voordat de met de vlucht ondertekende ffu wordt geflitst.
1. Op pc:
    1. Download ffu naar uw pc vanaf [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .
    
    1. Installeer ARC (Advanced Recovery Companion) vanuit de Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .
    
1. Op HoloLens - Ontgrendelen met vlucht: **Open** Instellingen  >  **Bijwerken & Beveiligingsbeleid**  >  **Windows Insider-programma** u zich vervolgens aan te melden en het apparaat opnieuw op te starten.
1. Flash-FFU: u kunt nu de met de vlucht ondertekende FFU flashen met behulp van ARC.
### <a name="provide-feedback-and-report-issues"></a>Feedback geven en problemen rapporteren
Gebruik de [app Feedback-hub uw](hololens-feedback.md) HoloLens om feedback te geven en problemen te melden. Het Feedback-hub zorgt ervoor dat alle benodigde diagnostische gegevens worden opgenomen om onze technici te helpen snel fouten op te sporen en het probleem op te lossen.  Problemen met de Chinese en Japanse versie van HoloLens moeten op dezelfde manier worden gerapporteerd.
> [!NOTE]
> Zorg ervoor dat u de prompt accepteert waarin wordt gevraagd of u Feedback-hub documenten wilt openen (selecteer **Ja** wanneer u hier om wordt gevraagd).
## <a name="note-for-developers"></a>Opmerking voor ontwikkelaars
U bent welkom en aangemoedigd om uw toepassingen te ontwikkelen met behulp van Insider-builds van HoloLens.  Bekijk de [Documentatie voor HoloLens-ontwikkelaars om](https://developer.microsoft.com/windows/mixed-reality/development) aan de slag te gaan. Dezelfde instructies werken met Insider-builds van HoloLens.  U kunt dezelfde builds van Unity en Visual Studio die u al gebruikt voor HoloLens-ontwikkeling.
## <a name="stop-receiving-insider-builds"></a>Ontvangst van Insider-builds stoppen
Als u geen Insider-builds van Windows Holographic meer wilt ontvangen, kunt u zich uitloggen [](hololens-recovery.md) wanneer op uw HoloLens een productie-build wordt uitgevoerd, of u kunt uw apparaat herstellen met behulp van advanced recovery companion om uw apparaat te herstellen naar een niet-Insider-versie van Windows Holographic.
> [!CAUTION]
> Er is een bekend probleem waarbij gebruikers die de registratie van Insider Preview-builds ongedaan maken nadat ze handmatig een nieuwe preview-build hebben geïnstalleerd, een blauw scherm krijgen. Daarna moeten ze hun apparaat handmatig herstellen. Bekijk meer over dit bekende probleem voor meer informatie over of u hier al dan niet [mee te maken zou krijgen.](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)
Controleren of op uw HoloLens een productie-build wordt uitgevoerd:
1. Ga naar **Instellingen > Systeem > Over** en zoek het buildnummer.
1. [Zie de releasenotities voor productie-buildnummers.](hololens-release-notes.md)
Als u zich wilt af melden voor Insider-builds:
1. Ga op een HoloLens met een productie-build naar Instellingen **> Update & Security > Windows Insider-programma** en selecteer Stop Insider **builds.**
1. Volg de instructies om uw apparaat uit te kiezen.
