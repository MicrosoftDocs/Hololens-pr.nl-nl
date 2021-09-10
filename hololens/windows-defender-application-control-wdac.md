---
title: Windows Defender Toepassingsbeheer (WDAC)
description: Overzicht van wat Windows Defender Application Control is en hoe u dit kunt gebruiken om uw HoloLens mixed reality beheren.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/3/2021
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: b5c3b55273346f330580b07e5294e7e8e65ea12d
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427895"
---
# <a name="windows-defender-application-control---wdac"></a>Windows Defender Toepassingsbeheer - WDAC

## <a name="overview"></a>Overzicht

Met WDAC kunt u een HoloLens het starten van apps te blokkeren. Het verschilt van de kioskmodus, waarbij de gebruikersinterface de apps verbergt, maar ze nog steeds kunnen worden gestart. Met WDAC kunt u de apps zien, maar ze kunnen niet worden gestart.

> [!NOTE]
> Wanneer eindgebruikers proberen een app te starten die is geblokkeerd door WDAC op HoloLens, krijgen ze geen melding dat ze de app niet kunnen starten.

Aan een apparaat kan meer dan één WDAC-beleid worden toegewezen. Als er meerdere WDAC-beleidsregels zijn ingesteld op een systeem, worden de meeste beperkende beleidsregels van kracht. 

Hier volgt een handleiding voor gebruikers om te leren hoe ze [WDAC](/mem/intune/configuration/custom-profile-hololens)en Windows PowerShell gebruiken om apps toe te staan of te blokkeren op HoloLens 2-apparaten met Microsoft Intune .

Wanneer gebruikers zoeken naar apps die op hun Windows 10 pc zijn geïnstalleerd met behulp van de eerste voorbeeldstap, moeten ze mogelijk enkele pogingen doen om de resultaten te beperken.

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

Als u de volledige naam van het pakket niet weet, moet u mogelijk een paar keer 'Get-AppxPackage -name YourBestGuess' uitvoeren om het te \* \* vinden. Voer vervolgens '$package 1 = Get-AppxPackage -name Actual.PackageName' uit als u de naam hebt

Als u bijvoorbeeld de volgende code voor een Microsoft Edge meer dan één resultaat retourneren, maar uit die lijst kunt u zien dat de volledige naam die u nodig hebt Microsoft.MicrosoftEdge is.

```powershell
Get-AppxPackage -name *edge*
``` 

## <a name="package-family-names-for-apps-on-hololens"></a>Familienamen van pakketten voor apps op HoloLens

In de bovenstaande handleiding kunt u handmatig de newPolicy.xml bewerken en regels toevoegen voor toepassingen die alleen zijn geïnstalleerd op HoloLens met de familienamen van pakketten. Soms zijn er apps die u kunt gebruiken die zich niet op uw desktop-pc die u wilt toevoegen aan het beleid.

Hier is een lijst met veelgebruikte en In-Box voor HoloLens 2 apparaten.

| App-naam                   | Naam pakketfamilie                                |
|----------------------------|----------------------------------------------------|
| 3D-viewer                  | Microsoft.Microsoft3DViewer_8wekyb3d8bbwe          |
| App-installatieprogramma              | Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</sup>         |
| Kalender                   | microsoft.windowscommunicationsapps_8wekyb3d8bbwe  |
| Camera                     | HoloCamera_cw5n1h2txyewy                           |
| Cortana                    | Microsoft.549981C3F5F10_8wekyb3d8bbwe              |
| Dynamics 365 Guides        | Microsoft.Dynamics365.Guides_8wekyb3d8bbwe         |
| Dynamics 365 Remote Assist | Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe      |
| Feedback-hub               | Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe         |
| Verkenner              | c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy |
| Mail                       | microsoft.windowscommunicationsapps_8wekyb3d8bbwe  |
| Microsoft Store            | Microsoft.WindowsStore_8wekyb3d8bbwe               |
| Films & TV                | Microsoft.ZuneVideo_8wekyb3d8bbwe                  |
| OneDrive                   | microsoft.microsoftskydrive_8wekyb3d8bbwe          |
| Foto's                     | Microsoft. Windows. Photos_8wekyb3d8bbwe             |
| Instellingen                   | HolographicSystemSettings_cw5n1h2txyewy            |
| Tips                       | Microsoft.HoloLensTips_8wekyb3d8bbwe               |

- 1: het blokkeren App-installatieprogramma blokkeert alleen de App-installatieprogramma-app en niet apps die zijn geïnstalleerd vanuit andere bronnen, zoals de Microsoft Store of van uw MDM-oplossing.

### <a name="how-to-find-a-package-family-name"></a>Een pakketfamilienaam vinden

Als een app niet in deze lijst staat, kan een gebruiker Apparaatportal gebruiken, verbonden met een HoloLens 2 die de app heeft geïnstalleerd en geblokkeerd, om de PackageRelativeID te bepalen en vervolgens PackageFamilyName op te halen.

1. Installeer de app op uw HoloLens 2 apparaat. 
1. Open Instellingen -> Updates & Security -> For developers en schakel de **ontwikkelaarsmodus** en vervolgens **Apparaatportal in.** 
    1. Meer informatie over instructies voor meer informatie over [het instellen en gebruiken van de apparaatportal is hier te vinden.](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)
1. Zodra Apparaatportal is verbonden, gaat u naar **Weergaven en** vervolgens **naar Apps.** 
1. Gebruik in het deelvenster Geïnstalleerde apps de vervolgkeuzekeuze om de geïnstalleerde app te selecteren. 
1. Zoek de PackageRelativeID. 
1. Kopieer app-tekens vóór `!` de . Deze tekens zijn uw PackageFamilyName.

