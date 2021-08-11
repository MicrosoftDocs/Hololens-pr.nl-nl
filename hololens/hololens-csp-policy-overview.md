---
title: Overzicht van CSP's en apparaatbeheer configureren
description: Meer informatie over het configureren van CSP's, beleid en apparaatbeheer met mobile device management en inrichtingspakketten.
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
ms.openlocfilehash: ed28033f10f7a6d0e826775e95d040d0cac7f9e9c6266acd6975d3532f6d8067
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/05/2021
ms.locfileid: "115664254"
---
# <a name="configure-csps-and-device-management-overview"></a>Overzicht van CSP's en apparaatbeheer configureren

IT-beheerders kunnen beleidsinstellingen definiëren en implementeren op HoloLens 2. Welke configuratie-instellingen u gebruikt, verschilt op basis van het implementatiescenario en bedrijfsapparaten bieden IT het breedste beheerbereik. In Windows 10 CSP's (Configuration Service Providers) een interface voor het lezen, instellen, wijzigen of verwijderen van configuratie-instellingen op het apparaat. Deze instellingen worden aan registersleutels of bestanden toe te passen. Sommige configuratieserviceproviders ondersteunen de WAP-indeling, sommige bieden ondersteuning voor SyncML en sommige bieden ondersteuning voor beide.

Zie voor meer informatie Windows 10 Holographic CSP's voor [apparaatbeheer](/windows/client-management/mdm/configuration-service-provider-reference#hololens)de volledige lijst met CSP's die worden ondersteund in HoloLens apparaten.
IT-beheerders kunnen beleids-CSP's ook op apparaten beheren. Zie de volledige lijst met [beleids-CSP's](/windows/client-management/mdm/policy-csps-supported-by-hololens2)die worden ondersteund door HoloLens 2 .

## <a name="configuration-methods"></a>Configuratiemethoden

### <a name="configure-with-mdm"></a>Configureren met MDM

CSP's en beleidsregels kunnen eenvoudig worden beheerd op elk persoonlijk of zakelijk apparaat dat is ingeschreven in een MDM-systeem. Zodra een apparaat is ingeschreven bij uw MDM-oplossing, kunt u dat apparaat of een set apparaten beheren met behulp van apparaatconfiguraties. Meer informatie over het beheren [van uw HoloLens apparaten via MDM.](hololens-mdm-configure.md)

### <a name="configure-with-provisioning-packages"></a>Configureren met inrichtingspakketten

HoloLens 2 ondersteunt ook het instellen van een beperkte set CSP-configuraties voor HoloLens 2 apparaten via aangepaste inrichtingspakketten. Inrichtingspakketten worden doorgaans gebruikt voor niet door MDM beheerde apparaten en moeten handmatig worden toegepast op elk apparaat. Lees informatie over het bouwen [van aangepaste inrichtingspakketten voor HoloLens.](hololens-provisioning.md)

## <a name="configurations"></a>Configuraties

### <a name="common-device-restrictions"></a>Algemene apparaatbeperkingen

Sommige apparaatbeperkingen zijn net zo eenvoudig en schakelen een functionaliteit of verbinding met het apparaat uit. Lees meer over algemene [apparaatbeperkingen voor meer informatie.](hololens-common-device-restrictions.md)

### <a name="kiosk-modes"></a>Kioskmodi

Gebruik kioskmodus om te bepalen welke identiteiten standaard toegang hebben tot welke apps. Kiosken kunnen worden gebruikt voor een gebruikersinterface voor één of meerdere apps. Kioskconfiguraties variëren van één app voor iedereen die het apparaat gebruikt, tot verschillende apps voor verschillende groepen. De kioskmodus stopt niet dat 'toegestane apps' andere apps starten en was niet bedoeld voor ooit. Lees meer over [kioskmodi en hoe u deze kunt gebruiken.](hololens-kiosk.md)

### <a name="settings-page-visibility"></a>Instellingen Zichtbaarheid van pagina's

Gebruik Instellingen app-beleid om te bepalen welke identiteiten standaard toegang hebben tot instellingen. Met dit beleid kan Instellingen app zodanig worden geconfigureerd dat alleen de geselecteerde pagina's worden weergegeven of dat alle geselecteerde pagina's worden verborgen. [Meer informatie over het configureren van de beschikbare pagina's.](settings-uri-list.md)

Deze functie is momenteel alleen beschikbaar in [Windows Insider-builds.](hololens-insider.md) Zorg ervoor dat apparaten voor wie u deze functie wilt gebruiken, zich op build 19041.1349+ hebben.

### <a name="wdac"></a>WDAC

Gebruik WDAC-configuratie om te bepalen welke apps/processen zijn toegestaan/niet mogen worden gestart, ongeacht of het systeem zich in de kioskmodus of niet.
[Zie ons overzicht voor WDAC.](windows-defender-application-control-wdac.md)
