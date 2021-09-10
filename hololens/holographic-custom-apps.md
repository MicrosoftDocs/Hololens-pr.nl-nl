---
title: Aangepaste apps voor HoloLens beheren (eerste generatie)
description: Meer informatie over het installeren, verwijderen en side loaden van aangepaste holographic-apps op HoloLens apparaten met behulp van de Apparaatportal en Visual Studio.
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 12/10/2020
manager: v-miegge
keywords: hololens, sideload, side load, side-load, store, uwp, app, install
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.topic: article
ms.localizationpriority: medium
ms.custom:
- CI 111456
- CSSTroubleshooting
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: b6769c36f821ee3619ac9b62efd637ac561192bb
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428520"
---
# <a name="manage-custom-apps-for-hololens-1st-gen"></a>Aangepaste apps voor HoloLens beheren (eerste generatie)

HoloLens biedt ondersteuning voor veel bestaande toepassingen van Microsoft Store, evenals nieuwe apps die specifiek zijn gebouwd voor HoloLens. Dit artikel is gericht op aangepaste holografische toepassingen.  

Zie Apps beheren met de Store voor meer informatie over [Store-apps.](holographic-store-apps.md)

> [!IMPORTANT]
> De volgende informatie is gemaakt voor de HoloLens (1e generatie), op dat moment ook wel de HoloLens Developer Edition genoemd. Het sideloaden van apps via de apparaatportal en het installeren van apps via Visual Studio waren toen gebruikelijk. Voor bedrijfsimplementaties raden we niet aan om de ontwikkelaarsmodus in te schakelen, die door beide methoden wordt gebruikt. Als u geïnteresseerd bent in een implementatiemethode voor beveiligde apps, raadpleegt u [appbeheer: overzicht.](app-deploy-overview.md)
>
> Als u op zoek bent naar een van beide ontwikkelaarsmethodes voor app-installatie voor HoloLens 2 apparaten, raadpleegt u:
>
> - [Apparaatportal: Een app installeren](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
> - [Apps Visual Studio implementeren en fouten opsporen](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

## <a name="install-custom-apps"></a>Aangepaste apps installeren

U kunt uw eigen toepassingen op HoloLens installeren met behulp van de Apparaatportal of door de apps te implementeren vanuit Visual Studio.

### <a name="installing-an-application-package-with-the-device-portal"></a>Een toepassingspakket installeren met de Apparaatportal

1. Stel een verbinding tot [stand Apparaatportal](/windows/mixed-reality/using-the-windows-device-portal) de doelverbinding met HoloLens.

1. Navigeer in het linkernavigatievenster naar de **pagina Apps.**

1. Blader **onder App-pakket** naar het APPX-bestand dat aan uw toepassing is gekoppeld.

   > [!IMPORTANT]
   > Zorg ervoor dat u verwijst naar alle bijbehorende afhankelijkheids- en certificaatbestanden.

1. Selecteer **Go.**

   > [!div class="mx-imgBorder"]
   > ![Installeer het app-formulier in Windows Apparaatportal op Microsoft HoloLens.](images/deviceportal-appmanager.jpg)

### <a name="deploying-from-microsoft-visual-studio-2015"></a>Implementeren vanuit Microsoft Visual Studio 2015

1. Open de oplossing Visual Studio app (.sln-bestand).

1. Open eigenschappen van **het** project.

1. Selecteer de volgende buildconfiguratie: **Master/x86/Remote Machine.**

1. Wanneer u Externe **machine selecteert:**
   - Zorg ervoor dat het adres naar het Wi-Fi IP-adres van uw HoloLens.
   - Stel verificatie in **op Universal (Unencrypted Protocol).**
   
1. Bouw uw oplossing.

1. Als u de app wilt implementeren vanaf uw ontwikkel-pc naar HoloLens, selecteert u **Externe machine.** Als u al een bestaande build op de HoloLens, selecteert u **Ja** om deze nieuwere versie te installeren.  

   ![Implementatie van externe machines voor apps Microsoft HoloLens in Visual Studio.](images/vs2015-remotedeployment.jpg)  
   
1. De toepassing wordt geïnstalleerd en automatisch op uw HoloLens.

Nadat u een app hebt geïnstalleerd, vindt  u deze in de Alle apps **(Start**  >  **Alle apps).**
