---
title: Algemene implementatiescenario's
description: Meer informatie over het implementeren en beheren van HoloLens in bedrijfsomgevingen, waaronder infrastructuur, Azure Active Directory en beheer van mobiele apparaten.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: bgener
ms.author: bogenera
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/04/2020
appliesto:
- HoloLens 2
ms.openlocfilehash: 529dde590c30d4a51fa8ae61e9d37d22170dc271
ms.sourcegitcommit: 5130823947caffd2a444e9d8fb15cd24cbb6414c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/24/2021
ms.locfileid: "114659060"
---
# <a name="common-deployment-scenarios"></a>Algemene implementatiescenario's

## <a name="overview"></a>Overzicht

Het kan lastig zijn om te weten hoe u een nieuw apparaat implementeert wanneer u het de eerste keer probeert. Hier delen we verschillende manieren voor het implementeren en beheren van Microsoft HoloLens twee apparaten binnen de organisatie.

U wilt oplossingen die op schaal worden geïmplementeerd. We willen u graag helpen. Laten we eerst eens kijken naar de stappen voor het implementeren van apparaten, dus hologrammen, om waarde te bereiken voor uw doel-mixed reality-scenario, of u nu D365 Remote Assist, Guides of een Azure mixed reality-toepassing met service ingeschakeld die u hebt gemaakt.

Mogelijk bent u een zakelijke beslisser, IT-professional of een innovatieteam dat op zoek is naar HoloLens binnen uw organisatie. Tijdens het bouwen van een proof-of-concept tot een geschaalde implementatie, zijn onze implementatiehandleidingen zinvol HoloLens binnen uw IT-infrastructuur, ongeacht hoe groot of klein. De volgende implementatiescenario's komen het meest voor:

| Scenario |Gebruik | Belangrijkste punten |
|---------|---------|---------|
| [Scenario A: Met de cloud verbonden apparaten](hololens2-cloud-connected-overview.md) | Wanneer u de implementatie voor het eerst start, kunt u klein beginnen en één apparaat implementeren dat is verbonden met de cloud om het basisproces te zien. | Apparaten worden verbonden met cloudservices en openbaar internet. Dit is het meest geschikt voor gebruiksgevallen van klanten, veldservices en proof-of-concept.|
| [Scenario B: Netwerk van de organisatie](hololens2-corp-connected-overview.md) | Wanneer u op schaal in productie implementeert, moet u mogelijk integreren met het netwerk van uw eigen organisatie. | Apparaten worden verbonden met een 'zakelijk' Wi-Fi-netwerk. Dit is het meest geschikt voor interne gebruikers of voor gebruik binnen de bedrijfsomgeving.|
| [Scenario C: Offline beveiligde omgeving](hololens-common-scenarios-offline-secure.md) | Voor sommige bedrijfskritieke processen of bepaalde bedrijfsbeleidsregels kan het gebruik van offlineomgevingen worden vereist. | Apparaten worden verbonden met een zeer beperkend netwerk of zijn uitsluitend offlineapparaten. Dit is het meest geschikt voor uiterst veilige omgevingen of internetverbindingsbeperkingen in externe gebieden. |

## <a name="scenario-a-deploy-to-cloud-connected-devices"></a>Scenario A: Implementeren op met de cloud verbonden apparaten

Dit scenario is vergelijkbaar met het implementeren van beheerde mobiele apparaten binnen een bedrijf. HoloLens 2 wordt geïmplementeerd voor gebruik voornamelijk in omgevingen buiten een bedrijfsnetwerk. Bedrijfsresources worden niet gebruikt of kunnen worden beperkt via VPN.

[![Scenario Een diagram](images/deployment-guides-revised-scenario-a.png)](images/deployment-guides-revised-scenario-a.png#lightbox)

### <a name="when-to-use"></a>Wanneer gebruikt u dit?

Overweeg dit implementatiemodel voor:

* Proof-of-concept- en fieldservices implementeren
* Implementatie [Remote Assist](hololens2-options-remote-assist.md)

### <a name="basic-common-configurations"></a>Algemene basisconfiguraties

* Wi-Fi netwerken zijn doorgaans volledig open voor internet en cloudservices
* Azure AD Join with Mobile Device Management (MDM) Auto Enrollment --MDM (Intune) Managed
* Gebruikers melden zich aan met hun eigen bedrijfsaccount (Azure AD)
  * Eén of meerdere gebruikers per ondersteund apparaat
* Verschillende niveaus van vergrendelingsconfiguraties voor apparaten worden toegepast op basis van specifieke gebruiksgevallen, van Volledig geopend tot Kiosk voor één app.
* Een of meer toepassingen worden geïmplementeerd via MDM

### <a name="common-challenges"></a>Veelvoorkomende uitdagingen

* Bepalen welke MDM-configuraties moeten worden toegepast op de HoloLens 2 op basis van scenariovereisten

De bijbehorende handleiding Cloud Connected bevat informatie over het inschrijven van HoloLens 2 bij uw apparaatbeheer, het toepassen van licenties naar behoefte en het valideren dat uw eindgebruikers de Remote Assist onmiddellijk kunnen gebruiken bij de installatie van het apparaat.

> [!div class="nextstepaction"]
> [Cloud Connected-implementatiehandleiding](hololens2-cloud-connected-overview.md)

Gebruik de handleiding Externe clients om apparaten te implementeren op een externe site voor extern gebruik op korte of lange termijn.

> [!div class="nextstepaction"]
> [Implementatiehandleiding voor cloud verbonden (externe clients)](hololens2-deployment-guide.md)

## <a name="scenario-b-deploy-inside-your-organizations-network"></a>Scenario B: Implementeren binnen het netwerk van uw organisatie

Dit scenario is identiek aan een klassieke implementatie voor de meeste Windows 10 pc's. HoloLens 2 is geïmplementeerd voor gebruik in het bedrijfsnetwerk met toegang tot interne bedrijfsresources. Internet- en cloudservices zijn mogelijk beperkt. 

[![Diagram van scenario B1](images/deployment-guides-revised-scenario-b-01-1.png)](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)

[![Scenario B2-diagram](images/deployment-guides-revised-scenario-b-02-1.png)](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)

### <a name="when-to-use"></a>Wanneer gebruikt u dit?

Overweeg dit implementatiemodel voor:

* Interne gebruikers
* Implementeren op schaal (pilot en productie) binnen de bedrijfsomgeving

### <a name="basic-common-configurations"></a>Algemene basisconfiguraties

* Wi-Fi netwerk is een intern bedrijfsnetwerk met toegang tot interne resources en beperkte toegang tot internet of cloudservices.
* Azure AD Join met automatische MDM-inschrijving
* MDM (Intune) Beheerd
* Gebruikers melden zich aan met hun eigen bedrijfsaccount (Azure AD)
  * Eén of meerdere gebruikers per ondersteund apparaat
* Verschillende niveaus van vergrendelingsconfiguraties voor apparaten worden toegepast op basis van specifieke gebruiksgevallen, van Volledig geopend tot Kiosk voor één app.
* Een of meer toepassingen worden geïmplementeerd via MDM

### <a name="common-challenges"></a>Veelvoorkomende uitdagingen

* HoloLens 2 biedt geen ondersteuning voor on-premises AD-join of System Center Configuration Manager (SCCM). Alleen Azure AD-join met MDM. Veel bedrijven implementeren momenteel nog steeds Windows 10-pc's in dit scenario als on-premises AD-apparaten die worden beheerd door SCCM en hebben mogelijk niet de infrastructuur geïmplementeerd/geconfigureerd voor het beheren van interne Windows 10-apparaten via MDM-oplossingen in de cloud.
* Omdat HoloLens 2 een eerste cloudapparaat is, is het sterk afhankelijk van internet- en cloudservices voor gebruikersverificatie, updates van het besturingssysteem, MDM-beheer, en meer. Wanneer u verbinding maakt met een bedrijfsnetwerk, moeten proxy-/firewallregels waarschijnlijk worden aangepast om toegang mogelijk te maken voor HoloLens 2 en de toepassingen die erop worden uitgevoerd.
* Voor Wi-Fi bedrijfsconnectiviteit zijn doorgaans certificaten vereist om het apparaat of de gebruiker bij het netwerk te verifiëren. De vereiste infrastructuur of instellingen voor het implementeren van certificaten Windows 10 apparaten via MDM kan lastig zijn om te configureren.

De bijbehorende handleiding Verbonden met het bedrijf geeft informatie over het inschrijven van HoloLens 2 bij uw bestaande apparaatbeheer, het toepassen van licenties naar behoefte en het valideren dat uw eindgebruikers een Dynamics 365-handleiding kunnen gebruiken en aangepaste Line-Of-Business-apps kunnen gebruiken nadat het apparaat is ingesteld.

> [!div class="nextstepaction"]
> [Implementatiehandleiding voor Verbonden bedrijfsnetwerk](hololens2-corp-connected-overview.md)

## <a name="scenario-c-deploy-in-secure-offline-environment"></a>Scenario C: Implementeren in een beveiligde offline omgeving

Dit is een typische implementatie voor zeer veilige of vertrouwelijke locaties. HoloLens 2 is geïmplementeerd voor gebruik voornamelijk offline zonder netwerk- of internettoegang.

[![Offline beveiligd diagram 1](images/deployment-guides-revised-scenario-c-01.png)](images/deployment-guides-revised-scenario-c-01.png#lightbox)

### <a name="when-to-use"></a>Wanneer gebruikt u dit?

Overweeg dit implementatiemodel voor:

* Uiterst veilige omgevingen waarin gegevens in eigen ruimte moeten worden bewaard
* Ervaringen waar het publiek de apparaten gaat gebruiken
* Probleem met internetverbinding in het externe gebied

### <a name="basic-common-configurations"></a>Algemene basisconfiguraties

* Wi-Fi connectiviteit is uitgeschakeld. Indien nodig kan Ethernet via USB worden ingeschakeld voor LAN-connectiviteit
* Niet beheerd
* Lokaal gebruikersaccount voor apparaat aanmelden
  * HoloLens 2 ondersteunt slechts één lokaal account
* Verschillende niveaus van vergrendelingsconfiguraties voor apparaten worden toegepast via Inrichtingspakketten op basis van specifieke gebruiksgevallen. Deze configuraties zijn doorgaans beperkt vanwege vereisten voor beveiligde omgevingen
* Een of meer toepassingen worden geïmplementeerd via Inrichtingspakket

### <a name="common-challenges"></a>Veelvoorkomende uitdagingen

* Er is een beperkte set configuraties beschikbaar via inrichtingspakketten
* Cloudservices kunnen niet worden gebruikt, waardoor de mogelijkheden van HoloLens 2 beperkt.
* Hogere administratieve overhead omdat deze apparaten handmatig moeten worden ingesteld, geconfigureerd en bijgewerkt.

De bijbehorende offline beveiligde handleiding bevat instructies voor het toepassen van een voorbeeld van een inrichtingspakket dat een HoloLens 2 voor gebruik in beveiligde omgevingen.

> [!div class="nextstepaction"]
> [Implementatiehandleiding voor offline beveiligde omgeving](hololens-common-scenarios-offline-secure.md)
