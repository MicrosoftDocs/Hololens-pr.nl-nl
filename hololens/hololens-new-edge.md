---
title: Introductie van de nieuwe Microsoft Edge
description: Meer informatie over de nieuwe Edge-app
author: joyjaz
ms.author: v-jjaswinski
keywords: HoloLens, edge, internet, browser
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisle
ms.openlocfilehash: 41978c626328903cf480a3315d56841f187bc123
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640182"
---
# <a name="introducing-the-new-microsoft-edge"></a>Introductie van de nieuwe Microsoft Edge

![Animatie van verouderd Microsoft Edge logo naar nieuw Microsoft Edge logo](images/new-edge.gif)

De nieuwe Microsoft Edge [maakt](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) gebruik van het Chromium open source project om betere compatibiliteit voor klanten en minder fragmentatie van het web voor webontwikkelaars te creëren.

Met [Windows Holographic, versie 21H1,](hololens-release-notes.md#windows-holographic-version-21h1)is de nieuwe Microsoft Edge voor het eerst beschikbaar HoloLens 2 klanten! Deel feedback en fouten met ons team via de functie **Feedback** verzenden in de nieuwe Microsoft Edge of via [Feedback-hub](hololens-feedback.md).

> [!IMPORTANT]
> Deze nieuwe Microsoft Edge vervangt automatisch verouderde Microsoft Edge, die niet meer [wordt ondersteund](https://blogs.windows.com/msedgedev/2021/03/09/microsoft-edge-legacy-end-of-support/) in nieuwe releases.

![Schermopname van Microsoft Edge nieuwe versie](images/new-edge-ui.png)

## <a name="launching-the-new-microsoft-edge"></a>De nieuwe Microsoft Edge

Het nieuwe Microsoft Edge ![pictogram Microsoft Edge nieuwe Microsoft Edge](images/new_edge_logo.png) (vertegenwoordigd door een blauw en groen pictogram) wordt vastgemaakt aan de Startmenu en wordt automatisch geactiveerd wanneer u een webkoppeling activeert.

> [!NOTE]
> Wanneer u de nieuwe Microsoft Edge voor HoloLens 2 start, worden uw instellingen en gegevens geïmporteerd uit verouderde Microsoft Edge.

## <a name="configuring-policy-settings-for-the-new-microsoft-edge"></a>Beleidsinstellingen configureren voor de nieuwe Microsoft Edge

De nieuwe Microsoft Edge biedt IT-beheerders een veel bredere set browserbeleidsregels op HoloLens 2 dan voorheen beschikbaar waren met verouderde Microsoft Edge.

Hier vindt u nuttige informatiebronnen voor meer informatie over het beheren van beleidsinstellingen voor de nieuwe Microsoft Edge:

- [Beleidsinstellingen Microsoft Edge configureren met Microsoft Intune](/deployedge/configure-edge-with-intune)
- [Microsoft Edge (oudere versie) voor Microsoft Edge toewijzen van beleid](/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [Google Chrome voor het Microsoft Edge van beleid](/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- Volledige [Microsoft Edge Enterprise-documentatie](/deployedge/)

> [!IMPORTANT]
> Vanwege het grote aantal browserbeleidsregels dat door de nieuwe Microsoft Edge wordt ondersteund, kan ons team niet garanderen dat elk nieuw beleid werkt op HoloLens 2. We hebben echter getest en bevestigd dat het nieuwe Microsoft Edge-equivalent van elk verouderd Microsoft Edge-beleid dat eerder werd ondersteund op HoloLens 2 werken zoals verwacht. Zie Microsoft Edge (oudere versie) voor [Microsoft Edge-toewijzing](/deployedge/microsoft-edge-policy-map-legacy-to-newedge) van beleid om de nieuwe Microsoft Edge-equivalent te vinden van elk verouderd Microsoft Edge-browserbeleid dat u gebruikte met HoloLens 2.
>
> Er zijn ten minste twee nieuwe Microsoft Edge beleidsregels die niet *werken* met HoloLens 2:
> - EnterpriseModeSiteList
> - EnterpriseSiteListServiceURL

## <a name="what-to-expect-from-the-new-microsoft-edge-on-hololens-2"></a>Wat u kunt verwachten van de nieuwe Microsoft Edge op HoloLens 2

Omdat de nieuwe Microsoft Edge een native Win32-app is met een nieuwe UWP-adapterlaag zodat deze kan worden uitgevoerd op uwP-apparaten zoals HoloLens 2, zijn sommige functies mogelijk niet onmiddellijk beschikbaar. We ondersteunen in de komende maanden nieuwe scenario's en functies, dus controleer deze ruimte op actuele informatie.

**Scenario's en functies werken naar verwachting:**
- Eerste ervaring, aanmelden bij profiel en synchroniseren
- Websites moeten worden weergegeven en gedragen zoals verwacht
- De meeste browserfunctionaliteit (favorieten, geschiedenis, enzovoort) werkt zoals verwacht
- Donkere modus
- Web-apps op het apparaat installeren
- Extensies installeren (laat het ons weten als u extensies gebruikt die niet goed werken op HoloLens 2)
- Een PDF weergeven en markeren
- Ruimtelijk geluid vanuit één browservenster
- Automatisch en handmatig bijwerken van de browser
- Een PDF opslaan in het menu Afdrukken (met behulp van de optie Opslaan in PDF)
- WebXR en 360 Viewer-extensie
- Inhoud herstellen naar het juiste venster wanneer u door meerdere vensters in uw omgeving bladert

**Scenario's en functies werken naar verwachting niet:**
- Ruimtelijk geluid van meerdere vensters met gelijktijdige audiostreams
- "Zie het, zeg het"
- Afdrukken

**Meest bekende problemen met de browser:**
- De preview van de vergrootglas op het holografische toetsenbord is uitgeschakeld voor de nieuwe Microsoft Edge. We hopen deze functie in een toekomstige update opnieuw in te kunnen stellen zodra de functie goed werkt.
- Audio kan worden afspelen vanuit het verkeerde browservenster als u een ander browservenster hebt geopend en actief hebt. U kunt dit probleem oplossen door het andere actieve venster te sluiten dat geen audio mag afspelen.
- Wanneer u audio afspelen vanuit een browservenster in de modus Volg mij, blijft de audio afspelen als u de modus Volg mij uit schakelen. U kunt dit probleem oplossen door het afspelen van audio te stoppen voordat u de modus Volg mij uitsluit of door het venster te sluiten met de X-knop.
- Interactie met actieve Microsoft Edge kan ertoe leiden dat andere 2D-app-vensters onverwacht inactief worden. U kunt deze vensters opnieuw activeren door er opnieuw mee te werken.

## <a name="microsoft-edge-insider-channels"></a>Microsoft Edge Insider-kanalen

Het Microsoft Edge team maakt drie preview-kanalen beschikbaar voor de Edge Insider-community: Beta, Dev en Canary. Als u een preview-kanaal installeert, wordt de uitgebrachte versie van Microsoft Edge niet verwijderd op uw HoloLens 2 en kunt u er meer dan één tegelijk installeren. 

Ga naar [de Microsoft Edge Insider voor](https://www.microsoftedgeinsider.com) meer informatie over de Edge Insider-community. Ga naar de Edge [Insider-downloadpagina](https://www.microsoftedgeinsider.com/download)voor meer informatie over de verschillende Edge Insider-kanalen en om aan de slag te gaan.

Er zijn een aantal methoden beschikbaar voor het installeren van Microsoft Edge Insider-kanalen om HoloLens 2:

**Directe installatie op apparaat (momenteel alleen beschikbaar voor niet-beherende apparaten)**
  1. Ga op HoloLens 2 pagina naar de [Edge Insider-downloadpagina.](https://www.microsoftedgeinsider.com/download)
  1. Selecteer de **knop Downloaden HoloLens 2** voor het Edge Insider-kanaal dat u wilt installeren.
  1. Start het gedownloade MSIX-bestand vanuit de Edge-downloadwachtrij of vanuit de map Downloads van uw apparaat (met behulp van Verkenner).
  1. [Het installatieprogramma](app-deploy-app-installer.md) voor de app wordt start.
  1. Selecteer de **knop** Installeren.
  1. Nadat de installatie is geslaagd, vindt u Microsoft Edge Beta, Dev of Canary  als een afzonderlijke vermelding in de Alle apps lijst van de Startmenu.

**Installeren via pc met Windows Apparaatportal (hiervoor moet [de](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) ontwikkelaarsmodus zijn ingeschakeld op HoloLens 2)**
  1. Ga op uw pc naar de [Edge Insider-downloadpagina.](https://www.microsoftedgeinsider.com/download)
  1. Selecteer de **vervolgkeuzepijl** naast de knop 'Downloaden voor Windows 10' voor het Edge Insider-kanaal dat u wilt installeren.
  1. Selecteer **HoloLens 2** in de vervolgkeuzelijst.
  1. Sla het MSIX-bestand op in de map Downloads van uw pc (of een andere map die u gemakkelijk kunt vinden).
  1. Gebruik [Windows Apparaatportal](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) op uw pc om het gedownloade MSIX-bestand te installeren op HoloLens 2.
  1. Nadat de installatie is geslaagd, vindt u Microsoft Edge Beta, Dev of Canary  als een afzonderlijke vermelding in de Alle apps lijst van de Startmenu.

## <a name="using-wdac-to-block-new-microsoft-edge"></a>WDAC gebruiken om nieuwe Microsoft Edge

IT-beheerders die hun [WDAC-beleid](windows-defender-application-control-wdac.md) willen bijwerken om de nieuwe Microsoft Edge-app te blokkeren, moeten het volgende toevoegen aan uw beleid.

``` <Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" /> ```

## <a name="managing-endpoints-for-the-new-microsoft-edge"></a>Eindpunten voor de nieuwe Microsoft Edge

Sommige omgevingen hebben mogelijk netwerkbeperkingen om rekening mee te houden als overweging. Schakel deze Microsoft-eindpunten in om een soepele ervaring met de nieuwe [Edge te garanderen.](/deployedge/microsoft-edge-security-endpoints)

Lees meer over de momenteel beschikbare [eindpunten voor HoloLens](hololens-offline.md).

## <a name="install-web-apps"></a>Web-apps installeren
 > [!Note]
> Vanaf Windows [Holographic, versie 21H1,](hololens-release-notes.md#windows-holographic-version-21h1)wordt de Office web-app niet meer vooraf geïnstalleerd. 

U kunt de nieuwe Edge gebruiken om web-apps naast de Microsoft Store installeren. U kunt de web-app bijvoorbeeld Microsoft Office om bestanden weer te geven en te bewerken die worden gehost op SharePoint of OneDrive. Als u de Office web-app wilt installeren, gaat u naar en selecteert u de knop App beschikbaar of Office https://www.office.com installeren in de adresbalk.   Selecteer **Installeren om** te bevestigen.
> [!IMPORTANT]
> Office web-app-functionaliteit is alleen beschikbaar wanneer uw HoloLens 2 een actieve internetverbinding heeft.

## <a name="webxr-and-360-viewer"></a>WebXR en 360 Viewer


De nieuwe Microsoft Edge biedt ondersteuning voor WebXR, de nieuwe standaard voor het maken van in immersieve webervaringen (waarbij WebVR wordt vervangen). Veel ingebouwde webervaringen zijn ontworpen met VR in gedachten (ze vervangen uw weergaveveld door een virtuele omgeving), maar deze ervaringen worden ook ondersteund door HoloLens 2. De WebXR-standaard biedt ook uitgebreide en mixed reality ingebouwde webervaringen die gebruikmaken van uw fysieke omgeving. Naarmate ontwikkelaars meer tijd besteden aan WebXR, verwachten we dat er nieuwe uitgebreide en mixed reality-ervaringen zullen worden HoloLens 2 klanten kunnen uitproberen.

De 360 Viewer-extensie is gebouwd op WebXR en wordt automatisch geïnstalleerd naast de nieuwe Microsoft Edge op HoloLens 2. Met deze webextensie kunt u zich in een video van 360 graden verdiepen. YouTube biedt de grootste selectie van 360 video's. Daarom raden we u aan om daar te beginnen.

### <a name="how-to-use-webxr"></a>WebXR gebruiken

1. Navigeer naar een website met WebXR-ondersteuning.
1. Selecteer de **knop VR invoeren** op de website. De locatie en visuele weergave van deze knop kunnen per website verschillen, maar kunnen er ongeveer als de volgende uitzien:

    ![Voorbeeld van een VR-knop invoeren](images/75px-enter-vr.png)

1. De eerste keer dat u een WebXR-ervaring op een specifiek domein probeert te starten, vraagt de browser om toestemming om een in immersieve weergave in te voeren. Selecteer **Toestaan.**
1. Gebruik [HoloLens 2 om de ervaring](hololens2-basic-usage.md#the-hand-tracking-frame) te manipuleren.
1. Als de ervaring geen  knop Afsluiten heeft, gebruikt u de beweging [Start om](hololens2-basic-usage.md#start-gesture) terug te keren.

**Aanbevolen WebXR-voorbeelden**
- 360 Viewer (zie de volgende sectie)
- [XR-](https://www.xrdinosaurs.com/)
- [Barista Express](https://constructarca.de/game/barista-express/)
- [WebXR-Paint](https://threejs.org/examples/webxr_vr_paint.html)

### <a name="how-to-use-360-viewer"></a>360 Viewer gebruiken

1. Navigeer naar een video van 360 graden op YouTube.
1. Selecteer in het videoframe de knop mixed reality headset:

    ![Knop om 360 Viewer te activeren](images/enter-360-viewer.jpg)

1. De eerste keer dat u 360 Viewer op een specifiek domein probeert te starten, wordt in de browser om toestemming gevraagd om een in immersieve weergave in te voeren. selecteer **Toestaan**.
1. [Tik in de lucht](hololens2-basic-usage.md#select-using-air-tap) om de afspeelbesturingselementen weer te brengen. Gebruik [handfoto's](hololens2-basic-usage.md#select-using-air-tap) en tikken in de lucht om af te spelen/onderbreken, vooruit/terug te gaan, bijschriften in/uit te schakelen of de ervaring te stoppen (waardoor de in immersieve weergave wordt afgesloten). De afspeelbesturingselementen verdwijnen na een paar seconden inactiviteit.

### <a name="top-webxr-and-360-viewer-known-issues"></a>Meest bekende problemen met WebXR en 360 Viewer
- Afhankelijk van de complexiteit van de WebXR-ervaring, kan de framerate worden verwijderd of gesutterd.
- Ondersteuning voor verwoorde handjes in WebXR is niet standaard ingeschakeld. Ontwikkelaars kunnen ondersteuning inschakelen via edge://flags door 'WebXR Hand Input' in te stellen.
- 360 video's van andere websites dan YouTube werken mogelijk niet zoals verwacht.

### <a name="providing-feedback-on-webxr-and-360-viewer"></a>Feedback geven over WebXR en 360 Viewer

Deel feedback en fouten met ons team via de functie **Feedback** verzenden in de nieuwe Microsoft Edge.
