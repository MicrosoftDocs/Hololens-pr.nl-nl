---
title: 'Implementatiehandleiding : Zakelijk verbonden HoloLens 2 met Dynamics 365 Guides - Onderhouden'
description: Meer informatie over het onderhouden HoloLens 2 apparaten via een bedrijfsnetwerk verbonden met Dynamics 365 Guides.
keywords: HoloLens, beheer, zakelijk verbonden, Dynamics 365 Guides, AAD, Azure AD, MDM, Mobile Device Management
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 0176e816f167499574607bc16c8fbd6bde757daf
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427425"
---
# <a name="maintain---corporate-connected-guide"></a>Onderhouden - Handleiding voor verbonden bedrijfsgegevens

## <a name="update-hololens"></a>Werk HoloLens

Microsoft heeft Windows Update voor Bedrijven ontworpen om IT-beheerders aanvullende Windows Op updates gerichte beheermogelijkheden te bieden, zoals de mogelijkheid om updates te implementeren op groepen apparaten en om onderhoudsvensters te definiëren voor het installeren van updates.

Een populaire methode voor het beheren van updates is het uitstellen van functies van 30 dagen. Hierdoor kunnen beheerders nieuwe functies bijwerken en previews bekijken, kennis opdoen en uw ondersteuningsdesk informeren over nieuwe wijzigingen.

Leer hoe u [HoloLens beheert,](/hololens/hololens-updates)inclusief geplande dagen, geplande tijd en het instellen van actieve uren op het apparaat, zodat deze buiten werkuren worden bijgewerkt.

## <a name="how-to-update-dynamics-365-guides-and-other-store-apps"></a>Gegevens bijwerken Dynamics 365 Guides (en andere Store-apps)

Dynamics 365 Guides is een In-Box-app en kan worden bijgewerkt via de Microsoft Store app. Alle apps die via de Microsoft Store worden gedownload, kunnen handmatig worden bijgewerkt via [Microsoft Store](/hololens/holographic-store-apps#update-apps) app zelf.

## <a name="how-to-update-lob-apps"></a>LOB-apps bijwerken

LOB-apps kunnen op dezelfde manier worden bijgewerkt als ze zijn toegevoegd aan Intune. Apps kunnen worden bijgewerkt in Intune door de nieuwe app met een hoger versienummer te uploaden naar de bestaande app-configuratie. Wanneer het apparaat wordt gesynchroniseerd met Intune, ziet u dat er een nieuwere app-versie is en dat de nieuwere app wordt gedownload en de oude app wordt vervangen.

1. Als u de nieuwere app wilt uploaden, gaat u naar de [MEM-portal](https://endpoint.microsoft.com/#home)  ->  **Apps** -> Alle **apps**  ->  *TheNameOfYourApp*  ->  **Properties.**
2. Selecteer bewerken naast **App-gegevens.**
3. Selecteer uw bestand &quot; voor de waarde bestand selecteren die moet worden &quot; bijgewerkt.
4. Gebruik hier het contextmenu om de bestandenverkenner te openen en de nieuwere versie van de LOB-app te uploaden. Zorg ervoor dat afhankelijkheden zo nodig zijn op te nemen.

Meer informatie: [Intune-app-implementatie voor HoloLens](/hololens/app-deploy-intune)

## <a name="development-plan"></a>Ontwikkelingsplan

Nu uw apparaat is ingeschreven, bent u voorbereid om meer LOB-apps op uw apparaten te implementeren. Voor de duur van deze handleiding gebruiken we een voorbeeld-app, maar het is waarschijnlijker dat u aangepaste apps wilt gebruiken die zijn gebouwd voor de behoeften van uw organisatie.

Als u al een LOB-app hebt, kunt u uw [app implementeren via MDM.](/hololens/app-deploy-intune) Als u liever een andere methode gebruikt, bekijkt u het overzicht van de toepassingsimplementatie voor HoloLens 2 [voor](/hololens/app-deploy-overview) meer methoden voor het implementeren van uw LOB-app op uw apparaten.

Als u nog uw eigen LOB-app moet maken of nog bezig bent met het maken, bekijkt u onze mixed reality-ontwikkelings docs om te beginnen met het ontwerpen en maken van [prototypen](/windows/mixed-reality/design/design) of om de belangrijkste concepten te leren om aan de slag te gaan [met mixed reality-ontwikkeling.](/windows/mixed-reality/discover/get-started-with-mr)

## <a name="support-plan"></a>Ondersteuningsplan

Een ondersteuningsplan is uitstekend om te hebben. Het is handig om iemand of een groep te laten trainen voor het oplossen van problemen met het inschrijvingsproces op HoloLens-apparaten en voor algemeen gebruik van het HoloLens-apparaat binnen uw organisatie. Om uw gebruikers in staat te stellen hun problemen sneller op te lossen, raden we u aan uw escalatieproces op een vergelijkbare manier te verwerken als in deze volgorde:

1. Uw ondersteuningsdesk.
2. Uw HoloLens Expert-team
3. [HoloLens Docs](/hololens/)  /  [HoloLens Docs voor probleemoplossing](/hololens/hololens-troubleshooting)
4. [Contact opnemen met ondersteuning](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="device-management"></a>Apparaatbeheer

In deze handleiding is het instellen van Mobile Device Management (MDM) besproken en gebruikt om enkele apparaatconfiguraties in te stellen en instellingen toe te passen om toegang toe te staan in termen van Wi-Fi certificaten en proxy. MDM kan echter ook worden gebruikt om apparaatbeperkingen toe te passen via CSP's en beleidsregels.

In veel gevallen kunnen apparaten verbindingsbeperkingen hebben, zoals Bluetooth, VPN, USB of zelfs het uitschakelen van de toegang tot de camera of microfoon. Als u een van deze interesses hebt, raden we u aan onze algemene pagina met [apparaatbeperkingen te lezen.](/hololens/hololens-common-device-restrictions)

Er zijn andere complexere apparaatbeperkingen die u kunt gebruiken. Zoals:

- Beperk de pagina's die kunnen worden weergegeven in de Instellingen-app met behulp van [InstellingenPaginaVisibility,](/hololens/settings-uri-list)zodat gebruikers alleen toegang hebben tot de instellingen die ze moeten aanpassen, zoals het wijzigen van hun Wi-Fi verbinding.
- Gebruik [kioskmodus om](/hololens/hololens-kiosk) de gebruikersinterface te beperken die wordt weergegeven aan gebruikers op een apparaat. U kunt Kiosken instellen om één app of meerdere apps weer te geven met een aangepaste startpagina. Kiosken kunnen ook verschillende ervaringen presenteren aan verschillende gebruikers.
- [Windows Application Control (WDAC) om](/hololens/windows-defender-application-control-wdac) te zorgen dat specifieke apps of processen niet volledig worden starten.

Als u meer wilt weten over aanvullende methoden voor apparaatbeheer of apparaatbeperkingen, gaat u naar de volgende stap en leest u het [Overzicht van apparaatbeheer.](/hololens/hololens-csp-policy-overview)





