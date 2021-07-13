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
ms.openlocfilehash: ccccdcc7d3188919d02eb5855131137415c12d16
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639825"
---
# <a name="common-deployment-scenarios"></a>Algemene implementatiescenario's

## <a name="overview"></a>Overzicht

Deze pagina biedt een overzicht van de architectuur op hoog niveau voor drie veelvoorkomende scenario's bij het implementeren en beheren Microsoft HoloLens 2 apparaten binnen de onderneming.

Vaak wordt de manier waarop u uw apparaten beheert en toegang krijgt tot de resources van uw organisatie grotendeels bepaald door factoren die al zijn gebruikt. Op basis van uw bestaande infrastructuur nodigt u uit om de algemene apparaatbeheerstijl (MDM) in de volgende scenario's te bekijken en vervolgens [Planning HoloLens 2 deployments in a commercial environment (Implementaties](hololens-core-components.md) plannen in een commerciële omgeving) te lezen om te bepalen welk scenario overeenkomt met uw behoeften. Er zijn ook drie bijbehorende handleidingen beschikbaar voor gebruik tijdens uw implementatie.


 1. [Implementatiehandleiding voor cloud verbonden omgevingen](hololens2-cloud-connected-overview.md)
     1. [Implementatiehandleiding voor cloud verbonden omgevingen (externe clients)](hololens2-deployment-guide.md)
 1. [Implementatiehandleiding voor bedrijfsnetwerk](hololens2-corp-connected-overview.md)
 1. [Implementatiehandleiding voor offline beveiligde omgeving](hololens-common-scenarios-offline-secure.md)

## <a name="scenario-a-deploy-to-cloud-connected-devices"></a>Scenario A: Implementeren naar met de cloud verbonden apparaten

Dit scenario is vergelijkbaar met het implementeren van beheerde mobiele apparaten binnen een bedrijf. HoloLens 2 wordt geïmplementeerd voor gebruik voornamelijk in omgevingen buiten een bedrijfsnetwerk. Bedrijfsresources worden niet gebruikt of kunnen worden beperkt via VPN. 
 * Algemene basisconfiguraties
   * Wi-Fi netwerken zijn doorgaans volledig open voor internet en cloudservices.
   * Azure AD Join with Mobile Device Management (MDM) Auto Enrollment --MDM (Intune) Managed
   * Gebruikers melden zich aan met hun eigen bedrijfsaccount (Azure AD)
     * Ondersteunde één of meerdere gebruikers per apparaat
   * Verschillende niveaus van apparaatvergrendelingsconfiguraties worden toegepast op basis van specifieke gebruiksgevallen, van Volledig geopend tot Kiosk voor één app.
   * Een of meer toepassingen worden geïmplementeerd via MDM

* Veelvoorkomende uitdagingen
   * Bepalen welke MDM-configuraties moeten worden toegepast op de HoloLens 2 op basis van scenariovereisten.

[![Scenario een diagram ](images/deployment-guides-revised-scenario-a.png)](images/deployment-guides-revised-scenario-a.png#lightbox)

De bijbehorende handleiding Verbonden met de cloud bevat informatie over het inschrijven van HoloLens 2 bij uw apparaatbeheer, het toepassen van licenties wanneer dat nodig is en het valideren dat uw eindgebruikers de Remote Assist onmiddellijk kunnen gebruiken bij het instellen van het apparaat. Gebruik de handleiding Externe clients om apparaten te implementeren op een externe site voor extern gebruik op de korte of lange termijn.

> [!div class="nextstepaction"]
> [Implementatiehandleiding voor cloud verbonden omgevingen](hololens2-cloud-connected-overview.md)

> [!div class="nextstepaction"]
> [Implementatiehandleiding voor cloud verbonden omgevingen (externe clients)](hololens2-deployment-guide.md)

## <a name="scenario-b-deploy-inside-your-organizations-network"></a>Scenario B: Implementeren binnen het netwerk van uw organisatie

Dit scenario is identiek aan een klassieke implementatie voor de meeste Windows 10 pc's. HoloLens 2 is geïmplementeerd voor gebruik voornamelijk op het bedrijfsnetwerk met toegang tot interne bedrijfsresources. Internet- en cloudservices zijn mogelijk beperkt. 

 * Algemene basisconfiguraties
   * Wi-Fi is een intern bedrijfsnetwerk met toegang tot interne resources en beperkte toegang tot internet of cloudservices.
   * Azure AD Join met automatische MDM-inschrijving
   * MDM (Intune) Beheerd
   * Gebruikers melden zich aan met hun eigen bedrijfsaccount (Azure AD)
     * Ondersteunde één of meerdere gebruikers per apparaat
   * Verschillende niveaus van apparaatvergrendelingsconfiguraties worden toegepast op basis van specifieke gebruiksgevallen, van Volledig geopend tot Kiosk voor één app.
   * Een of meer toepassingen worden geïmplementeerd via MDM

 * Veelvoorkomende uitdagingen
   * HoloLens 2 biedt geen ondersteuning voor on-premises AD-join of SCCM. Alleen Azure AD-join met MDM. Veel bedrijven implementeren momenteel nog steeds Windows 10-pc's in dit scenario als on-premises AD-apparaten die worden beheerd door System Center Configuration Manager (SCCM) en hebben mogelijk niet de infrastructuur geïmplementeerd/geconfigureerd voor het beheren van interne Windows 10-apparaten via cloudgebaseerde MDM-oplossingen.
   * Omdat HoloLens 2 een eerste cloudapparaat is, is het sterk afhankelijk van internet- en cloudservices voor gebruikersverificatie, updates van het besturingssysteem, MDM-beheer, en meer. Wanneer u verbinding maakt met een bedrijfsnetwerk, moeten de proxy-/firewallregels waarschijnlijk worden aangepast om toegang mogelijk te maken voor HoloLens 2 en de toepassingen die erop worden uitgevoerd.
   * Voor Wi-Fi bedrijfsconnectiviteit zijn doorgaans certificaten vereist om het apparaat of de gebruiker bij het netwerk te verifiëren. De vereiste infrastructuur of instellingen voor het implementeren van certificaten op Windows 10 apparaten via MDM kan lastig zijn om te configureren.

[![Diagram van scenario B1 ](images/deployment-guides-revised-scenario-b-01-1.png)](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)

[![Diagram van scenario B2 ](images/deployment-guides-revised-scenario-b-02-1.png)](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)

De bijbehorende handleiding Bedrijfsnetwerk geeft instructies voor het inschrijven van HoloLens 2 bij uw bestaande apparaatbeheer, het toepassen van licenties naar behoefte en het valideren dat uw eindgebruikers een Dynamics 365-handleiding kunnen gebruiken en aangepaste Line-Of-Business-apps kunnen gebruiken nadat het apparaat is ingesteld.

> [!div class="nextstepaction"]
> [Implementatiehandleiding voor bedrijfsnetwerk](hololens2-corp-connected-overview.md)

## <a name="scenario-c-deploy-in-secure-offline-environment"></a>Scenario C: Implementeren in een beveiligde offline omgeving

Dit is een typische implementatie voor zeer veilige of vertrouwelijke locaties. HoloLens 2 is geïmplementeerd voor gebruik voornamelijk offline zonder netwerk- of internettoegang. 
 * Algemene basisconfiguraties
   * Wi-Fi connectiviteit is uitgeschakeld. Ethernet via USB kan indien nodig worden ingeschakeld voor LAN-connectiviteit.
   * Niet beheerd.
   * Lokaal gebruikersaccount voor het aanmelden bij het apparaat.
     * HoloLens 2 ondersteunt slechts één lokaal account.
   * Verschillende niveaus van vergrendelingsconfiguraties voor apparaten worden toegepast via Inrichtingspakketten op basis van specifieke gebruiksgevallen. Deze configuraties zijn doorgaans beperkt vanwege de vereisten voor een veilige omgeving.
   * Een of meer toepassingen worden geïmplementeerd via Inrichtingspakket

 * Veelvoorkomende uitdagingen
   * Er is een beperkte set configuraties beschikbaar via Inrichtingspakketten
   * Cloudservices kunnen niet worden gebruikt, waardoor de mogelijkheden van HoloLens 2 beperkt.
   * Hogere administratieve overhead omdat deze apparaten handmatig moeten worden ingesteld, geconfigureerd en bijgewerkt.

[![Offline beveiligd diagram 1 ](images/deployment-guides-revised-scenario-c-01.png)](images/deployment-guides-revised-scenario-c-01.png#lightbox)

De bijbehorende offline beveiligde handleiding bevat instructies voor het toepassen van een voorbeeld van een inrichtingspakket dat een HoloLens 2 vergrendelt voor gebruik in beveiligde omgevingen.

> [!div class="nextstepaction"]
> [Implementatiehandleiding voor offline beveiligde omgeving](hololens-common-scenarios-offline-secure.md)


