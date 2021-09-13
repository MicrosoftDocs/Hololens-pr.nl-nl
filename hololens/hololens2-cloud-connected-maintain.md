---
title: 'Implementatiehandleiding : Cloudgeconnecteerde HoloLens 2 implementatie op schaal met Remote Assist - Onderhouden'
description: Blijf op de hoogte met onze tips voor het onderhouden en ondersteunen van HoloLens via een met de cloud verbonden netwerk.
keywords: HoloLens, beheer, cloud verbonden, Remote Assist, AAD, Azure AD, MDM, Mobile Device Management
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 941de296d59713c098718b16431fa793bd1b60e6
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032737"
---
# <a name="maintain---cloud-connected-guide"></a>Onderhouden - Handleiding voor verbonden cloud

## <a name="updates"></a>Updates

Microsoft heeft Windows Update voor Bedrijven ontworpen om IT-beheerders aanvullende Windows Op updates gerichte beheermogelijkheden te bieden, zoals de mogelijkheid om updates te implementeren op groepen apparaten en om onderhoudsvensters te definiëren voor het installeren van updates.

Meer informatie over het [HoloLens van updates,](/hololens/hololens-updates) waaronder geplande dagen, geplande tijd en het instellen van actieve uren op het apparaat, zodat het buiten werkuren wordt bijgewerkt.

Remote Assist is een In-Box-app en kan worden bijgewerkt via de Microsoft Store app. Voor alle apps die worden gedownload via de Microsoft Store kunnen ze handmatig worden bijgewerkt [via Microsoft Store](/hololens/holographic-store-apps#update-apps) app zelf.

## <a name="support-plan"></a>Ondersteuningsplan

Een ondersteuningsplan is uitstekend om te hebben. Het is handig om iemand of een groep te laten trainen voor het oplossen van problemen met het inschrijvingsproces op HoloLens-apparaten en voor algemeen gebruik van het HoloLens-apparaat binnen uw organisatie. Om uw gebruikers in staat te stellen hun problemen sneller op te lossen, raden we u aan uw escalatieproces op een vergelijkbare manier te verwerken als in deze volgorde:

1. Uw ondersteuningsdesk.
2. Uw HoloLens Expert-team
3. [HoloLens Docs](/hololens/)  /  [HoloLens Docs voor probleemoplossing](/hololens/hololens-troubleshooting)
4. [Contact opnemen met ondersteuning](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="development-plan"></a>Ontwikkelingsplan

Nu uw apparaat is ingeschreven, bent u klaar om LOB-apps (Line-Of-Business) op uw apparaten te implementeren. Dit zijn aangepaste apps die zijn gebouwd voor uw organisatie&#39;de behoeften van uw organisatie.

Als u al een Line-Of-Business-app hebt, kunt&#39;[app implementeren via MDM.](/hololens/app-deploy-intune) Als u&#39;liever een andere methode gebruikt, bekijkt u het overzicht van de implementatie van toepassingen voor [HoloLens 2](/hololens/app-deploy-overview) voor meer methoden voor het implementeren van uw LOB-app op uw apparaten.

Als u&#39;uw eigen LOB-app wilt maken of nog bezig bent met het maken, bekijkt u onze mixed reality-ontwikkel docs om te beginnen met het ontwerpen en [prototypen](/windows/mixed-reality/design/design) of om de belangrijkste concepten te leren om aan de slag te gaan met [mixed reality-ontwikkeling.](/windows/mixed-reality/discover/get-started-with-mr)

## <a name="device-management"></a>Apparaatbeheer 

Hoewel in deze handleiding werd gesproken over het instellen van Mobile Device Management (MDM), werd het niet gebruikt om apparaatbeperkingen of beleidsregels toe te passen op apparaten. Apparaatbeheer kan worden gebruikt om toegang toe te staan door certificaten te pushen of de toegang te beperken met verschillende apparaatbeperkingen. 

In veel gevallen kunnen apparaten verbindingsbeperkingen hebben, zoals Bluetooth, VPN, USB of zelfs het uitschakelen van de toegang tot de camera of microfoon. Als u een van deze interesses hebt, raden we u aan onze algemene pagina met [apparaatbeperkingen te lezen.](hololens-common-device-restrictions.md)

Er zijn andere complexere apparaatbeperkingen die u kunt gebruiken. Zoals:

- Beperk de pagina's die kunnen worden weergegeven in de Instellingen-app met behulp van [InstellingenPaginaVisibility,](settings-uri-list.md)zodat gebruikers alleen toegang hebben tot de instellingen die ze moeten aanpassen, zoals het wijzigen van hun Wi-Fi-verbinding.
- Gebruik [kioskmodus om](hololens-kiosk.md) de gebruikersinterface te beperken die wordt weergegeven aan gebruikers op een apparaat. U kunt Kiosken instellen om één app of meerdere apps weer te geven met een aangepaste startpagina. Kiosken kunnen ook verschillende ervaringen presenteren aan verschillende gebruikers.  
- [Windows Application Control (WDAC) om](windows-defender-application-control-wdac.md) te zorgen dat specifieke apps of processen niet volledig worden starten.

Als u meer informatie wilt over meer verschillende methoden voor apparaatbeheer of apparaatbeperkingen, gaat u naar de volgende stap en leest u het Overzicht van apparaatbeheer.

## <a name="next-step"></a>Volgende stap

> [!div class="nextstepaction"]
> [Lees het overzicht van CSP's en apparaatbeheer](hololens-csp-policy-overview.md)