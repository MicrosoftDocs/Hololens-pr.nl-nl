---
title: Windows Defender Application Control - WDAC
description: Overzicht van wat Windows Defender Application Control is en hoe u dit kunt gebruiken om HoloLens-apparaten mixed reality beheren.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/26/2020
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 23c9a274387424e8f084a4729ee621e130820716
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/19/2021
ms.locfileid: "111377848"
---
# <a name="windows-defender-application-control---wdac"></a>Windows Defender Application Control - WDAC

Met WDAC kan een IT-beheerder zijn apparaten configureren om het starten van apps op apparaten te blokkeren. Dit verschilt van de apparaatbeperkingsmethoden, zoals de kioskmodus, waarbij de gebruiker een gebruikersinterface krijgt te zien die de apps op het apparaat verbergt, maar nog steeds kan worden gestart. Terwijl WDAC is geïmplementeerd, zijn de apps nog steeds zichtbaar in de lijst Alle apps, maar WDAC voorkomt dat deze apps en processen kunnen worden gestart door de gebruiker van het apparaat.

Aan een apparaat kan meer dan één WDAC-beleid worden toegewezen. Als er meerdere WDAC-beleidsregels zijn ingesteld op een systeem, worden de meest beperkende beleidsregels van kracht. 

> [!NOTE]
> Wanneer eindgebruikers een app proberen te starten die is geblokkeerd door WDAC, ontvangen ze op HoloLens geen melding dat ze die app niet kunnen starten.

Hier volgt een handleiding voor gebruikers voor informatie over het gebruik van WDAC en Windows PowerShell voor het toestaan of blokkeren van apps op [HoloLens 2-apparaten met Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).

Wanneer gebruikers zoeken naar apps die zijn geïnstalleerd op hun Windows 10 pc met behulp van de eerste voorbeeldstap, moeten ze mogelijk enkele pogingen doen om de resultaten te beperken.

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

Als u de volledige naam van het pakket niet weet, moet u mogelijk 'Get-AppxPackage -name YourBestGuess' een paar keer uitvoeren om het te \* \* vinden. Als u de naam hebt, voer dan '$package 1 = Get-AppxPackage -name Actual.PackageName' uit

Als u bijvoorbeeld het volgende Microsoft Edge meer dan één resultaat retourneren, maar uit die lijst kunt u zien dat de volledige naam die u nodig hebt Microsoft.MicrosoftEdge is.

```powershell
Get-AppxPackage -name *edge*
``` 

## <a name="package-family-names-for-apps-on-hololens"></a>Familienamen van pakketten voor apps op HoloLens

In de bovenstaande handleiding kunt u handmatig de newPolicy.xml en regels toevoegen voor toepassingen die alleen zijn geïnstalleerd op HoloLens met de familienamen van pakketten. Soms zijn er apps die u kunt gebruiken en die zich niet op uw desktopcomputer die u aan het beleid wilt toevoegen.

Hier is een lijst met veelgebruikte en In-Box voor HoloLens 2 apparaten.

| App-naam                   | Naam pakketfamilie                                |
|----------------------------|----------------------------------------------------|
| 3D-viewer                  | Microsoft.Microsoft3DViewer_8wekyb3d8bbwe          |
| App-installatieprogramma              | Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</sup>         |
| Kalender                   | microsoft.windowscommunicationsapps_8wekyb3d8bbwe  |
| Camera                     | HoloCamera_cw5n1h2txyewy                           |
| Cortana                    | Microsoft.549981C3F5F10_8wekyb3d8bbwe              |
| Dynamics 365-handleidingen        | Microsoft.Dynamics365.Guides_8wekyb3d8bbwe         |
| Dynamics 365 Remote Assist | Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe      |
| Feedback-hub               | Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe         |
| Verkenner              | c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy |
| Mail                       | microsoft.windowscommunicationsapps_8wekyb3d8bbwe  |
| Microsoft Store            | Microsoft.WindowsStore_8wekyb3d8bbwe               |
| Films & TV                | Microsoft.ZuneVideo_8wekyb3d8bbwe                  |
| OneDrive                   | microsoft.microsoftskydrive_8wekyb3d8bbwe          |
| Foto's                     | Microsoft.Windows.Photos_8wekyb3d8bbwe             |
| Instellingen                   | HolographicSystemSettings_cw5n1h2txyewy            |
| Tips                       | Microsoft.HoloLensTips_8wekyb3d8bbwe               |

- 1: als u App-installatieprogramma blokkeert, wordt alleen de App-installatieprogramma-app geblokkeerd en niet apps die zijn geïnstalleerd vanuit andere bronnen, zoals de Microsoft Store of van uw MDM-oplossing.

### <a name="how-to-find-a-package-family-name"></a>Een pakketfamilienaam zoeken

Als een app niet in deze lijst staat, kan een gebruiker Apparaatportal gebruiken, verbonden met een HoloLens 2 die de app heeft geïnstalleerd, om de PackageRelativeID te bepalen en van hieruit de PackageFamilyName op te halen.

1. Installeer de app op uw HoloLens 2 apparaat. 
1. Open Instellingen -> Updates &-> Voor ontwikkelaars en schakel de **ontwikkelaarsmodus** en vervolgens **Apparaatportal in.** 
    1. Lees hier meer informatie over de installatie [en het gebruik van de apparaatportal.](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)
1. Zodra Apparaatportal is verbonden, gaat u naar **Weergaven en** vervolgens **naar Apps.** 
1. Gebruik in het deelvenster Geïnstalleerde apps de vervolgkeuze selecteren om de geïnstalleerde app te selecteren. 
1. Zoek de PackageRelativeID. 
1. Kopieer app-tekens vóór de . Deze tekens zijn uw PackageFamilyName.


