---
title: Overzicht van CSP's en apparaatbeheer configureren
description: Meer informatie over het configureren van CSP's, beleid en apparaatbeheer met Mobile Device Management en inrichtingspakketten.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 09/16/2020
ms.reviewer: lavinds
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: b312f9d20c9a75c5e4c1906c4ec55f42fda977f6
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428046"
---
# <a name="configure-csps-and-device-management-overview"></a>Overzicht van CSP's en apparaatbeheer configureren

IT-beheerders kunnen beleidsinstellingen definiëren en implementeren op HoloLens 2. Welke configuratie-instellingen u gebruikt, is afhankelijk van het implementatiescenario en bedrijfsapparaten bieden IT het breedste beheerbereik. In Windows 10 zijn CSP's (Configuration Service Providers) een interface voor het lezen, instellen, wijzigen of verwijderen van configuratie-instellingen op het apparaat. Deze instellingen worden aan registersleutels of bestanden toe te passen. Sommige configuratieserviceproviders ondersteunen de WAP-indeling, sommige bieden ondersteuning voor SyncML en sommige ondersteunen beide.

Zie de volledige lijst met CSP'Windows 10 Holographic ondersteund [in HoloLens-apparaten voor meer](/windows/client-management/mdm/configuration-service-provider-reference#hololens)informatie over CSP HoloLens s voor apparaatbeheer.
IT-beheerders kunnen ook beleids-CSP's op apparaten beheren. Zie de volledige lijst met beleids-CSP's die worden ondersteund [door HoloLens 2.](/windows/client-management/mdm/policy-csps-supported-by-hololens2)

## <a name="configuration-methods"></a>Configuratiemethoden

### <a name="configure-with-mdm"></a>Configureren met MDM

CSP's en beleidsregels kunnen eenvoudig worden beheerd op elk persoonlijk of zakelijk apparaat dat is ingeschreven in een MDM-systeem. Zodra een apparaat is ingeschreven bij uw MDM-oplossing, kunt u dat apparaat of een set apparaten beheren met behulp van apparaatconfiguraties. Meer informatie over het beheren [van uw HoloLens apparaten via MDM.](hololens-mdm-configure.md)

### <a name="configure-with-provisioning-packages"></a>Configureren met inrichtingspakketten

HoloLens 2 ondersteunt ook het instellen van een beperkte set CSP-configuraties voor HoloLens 2 apparaten via aangepaste inrichtingspakketten. Inrichtingspakketten worden doorgaans gebruikt voor niet door MDM beheerde apparaten en moeten handmatig op elk apparaat worden toegepast. Lees meer informatie over het bouwen [van aangepaste inrichtingspakketten voor HoloLens.](hololens-provisioning.md)

## <a name="configurations"></a>Configuraties

### <a name="common-device-restrictions"></a>Algemene apparaatbeperkingen

Sommige apparaatbeperkingen zijn zo eenvoudig en schakelen een functionaliteit of verbinding met het apparaat uit. Lees meer over algemene [apparaatbeperkingen voor meer informatie.](hololens-common-device-restrictions.md)

### <a name="kiosk-modes"></a>Kioskmodi

Gebruik kioskmodus om te bepalen welke identiteiten standaard toegang hebben tot welke apps. Kiosken kunnen worden gebruikt voor een gebruikersinterface voor één of meerdere apps. Kioskconfiguraties variëren van één app voor iedereen die het apparaat gebruikt, tot verschillende apps voor verschillende groepen. De kioskmodus zorgt er niet voor dat 'toegestane apps' andere apps starten en was nooit bedoeld. Lees meer over [kioskmodi en hoe u deze kunt gebruiken.](hololens-kiosk.md)

### <a name="settings-page-visibility"></a>Instellingen Zichtbaarheid van pagina's

Gebruik Instellingen app-beleid om te bepalen welke identiteiten standaard toegang hebben tot instellingen. Met dit beleid kan de Instellingen-app zodanig worden geconfigureerd dat alleen de geselecteerde pagina's worden weergegeven of dat alle geselecteerde pagina's worden verborgen. [Meer informatie over het configureren van de pagina's die beschikbaar zijn.](settings-uri-list.md)

Deze functie is momenteel alleen beschikbaar in [Windows Insider-builds.](hololens-insider.md) Zorg ervoor dat apparaten voor wie u deze functie wilt gebruiken, zich op build 19041.1349+ hebben.

### <a name="wdac"></a>WDAC

Gebruik WDAC-configuratie om te bepalen welke apps/processen zijn toegestaan/niet mogen worden gestart, ongeacht of het systeem zich in de kioskmodus of niet.
[Zie ons overzicht voor WDAC.](windows-defender-application-control-wdac.md)
