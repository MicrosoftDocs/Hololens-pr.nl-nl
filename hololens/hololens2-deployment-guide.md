---
title: Implementatiehandleiding voor externe clients
description: Implementatiehandleiding voor HoloLens 2 voor externe clients (met Hulp op afstand als voorbeeld)
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
ms.topic: article
ms.localizationpriority: medium
ms.date: 1/12/2021
ms.custom: ''
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: acf4b5d730b9a7eee2dedfad2bb3f866931d7455
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/12/2021
ms.locfileid: "113636942"
---
# <a name="deploying-hololens-2-to-external-clients-with-remote-assist"></a>Implementatie van HoloLens 2 naar externe clients met Remote Assist

Deze handleiding helpt IT-professionals bij het implementeren van Microsoft HoloLens 2 apparaten in hun organisatie:

1. Cloud-HoloLens 2 apparaten
1. Apparaten HoloLens 2 externe clients te verstrekken voor gebruik
1. Apparaten met leningen beveiligen

Deze handleiding biedt algemene aanbevelingen HoloLens 2 implementatie [die](#general-deployment-recommendations-and-instructions) van toepassing zijn op de [](#common-concerns) meeste HoloLens 2-implementatiescenario's en veelvoorkomende problemen die klanten hebben bij het implementeren Remote Assist voor extern gebruik.

## <a name="scenario-description"></a>Scenariobeschrijving

Voor het doel van dit document wil het bedrijf Contoso een HoloLens 2-apparaat verzenden naar de fabriek van een externe client voor kortetermijn- of langetermijngebruik. Wanneer de client hulp nodig heeft bij het onderhouden van machines, meldt de client zich aan bij het HoloLens 2-apparaat met de referenties van het bedrijf Contoso en gebruikt Remote Assist om contact op te nemen met de experts van het Contoso-bedrijf.

Meer informatie over Remote Assist [hier.](/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist)

### <a name="requirements-for-this-scenario"></a>Vereisten voor dit scenario

1. [Azure AD](/azure/active-directory/fundamentals/active-directory-whatis)
1. Mobiele Apparaatbeheer- zoals [Intune](/mem/intune/fundamentals/free-trial-sign-up)
1. Remote Assist licentie
    1. [Kopen Remote Assist](/dynamics365/mixed-reality/remote-assist/buy-remote-assist)
    1. [Proefversie Remote Assist](/dynamics365/mixed-reality/remote-assist/try-remote-assist)

## <a name="common-concerns"></a>Veelvoorkomende problemen

- [Ervoor zorgen dat externe clients niet de mogelijkheid hebben om met elkaar te communiceren](#how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another)
- [Ervoor zorgen dat clients geen toegang hebben tot bedrijfsbronnen](#how-to-ensure-that-clients-do-not-have-access-to-company-resources)
- [Apps beperken](#how-to-restrict-apps)
- [Wachtwoorden beheren](#how-to-manage-passwords)
- [Ervoor zorgen dat clients geen toegang hebben tot de chatgeschiedenis](#how-to-ensure-that-clients-do-not-have-access-to-chat-history)

### <a name="how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another"></a>Ervoor zorgen dat externe clients niet de mogelijkheid hebben om met elkaar te communiceren

Omdat Remote Assist HoloLens aanroepen HoloLens niet worden ondersteund, kunnen clients met elkaar zoeken, maar niet met elkaar communiceren. Om verder te beperken met wie [](/microsoft-365/compliance/information-barriers) clients kunnen zoeken en bellen, kunnen gegevensbarrières beperken met wie een client kan communiceren. Een andere optie die u kunt overwegen, is het gebruik [van Scoped Directory Search](/MicrosoftTeams/teams-scoped-directory-search)

 > [!NOTE]
> Omdat een aanmelding is ingeschakeld, is het belangrijk om de browser uit te schakelen met [**WDAC**](/hololens/windows-defender-application-control-wdac). Als een externe client de browser opent en gebruikmaakt van de webversie van Teams, heeft de client toegang tot de aanroep-/chatgeschiedenis.

### <a name="how-to-ensure-that-clients-do-not-have-access-to-company-resources"></a>Ervoor zorgen dat clients geen toegang hebben tot bedrijfsbronnen

Er zijn twee opties die u kunt overwegen.

De eerste optie is een benadering met meerdere lagen:

1. Wijs alleen licenties toe die de gebruiker nodig heeft. Als u geen OneDrive, Outlook, SharePoint, Yammer enzovoort aan de gebruiker toewijst, heeft hij/zij geen toegang tot deze resources. De enige licenties die gebruikers nodig hebben, zijn Remote Assist, Intune en AAD-licenties om te beginnen.
1. Blokkeer apps (zoals e-mail) die u niet wilt gebruiken voor clients (zie Apps [beperken).](#how-to-restrict-apps)
1. Deel GEEN gebruikersnamen en geen wachtwoord met clients. Als u zich wilt aanmelden HoloLens 2, hebt u een e-mail en een numerieke pincode nodig.

De tweede optie is het maken van een afzonderlijke tenant die clients host (zie afbeelding 1.1).

**Afbeelding 1.1**

![Afbeelding van service-tenant](./images/hololens-service-tenant-image.png)

### <a name="how-to-restrict-apps"></a>Apps beperken

[Kioskmodus](/hololens/hololens-kiosk) en/of [WDAC (Windows Defender Application Control)](/hololens/windows-defender-application-control-wdac) zijn opties voor het beperken van toepassingen.

### <a name="how-to-manage-passwords"></a>Wachtwoorden beheren

1. Wachtwoordverloopdatum verwijderen. Dit vergroot echter de kans dat een account wordt aangetast. Aanbeveling voor NIST-wachtwoorden is om wachtwoorden elke 30-90 dagen te wijzigen.
1. Breid de wachtwoordverlooptijd voor HoloLens 2 apparaten uit tot meer dan 90 dagen.
1. De apparaten moeten worden geretourneerd naar Contoso om de wachtwoorden te wijzigen. Dit kan echter problemen veroorzaken als de apparaten naar verwachting meer dan 90 dagen in de fabriek van de client zijn.  
1. Voor apparaten die naar meerdere clients worden verzonden, stelt u wachtwoorden opnieuw in voordat u het apparaat naar clients stuurt.

### <a name="how-to-ensure-that-clients-do-not-have-access-to-chat-history"></a>Ervoor zorgen dat clients geen toegang hebben tot de chatgeschiedenis

Remote Assist wordt de chatgeschiedenis na elke sessie geweken. De chatgeschiedenis is echter beschikbaar voor de Microsoft Teams gebruiker.

> [!NOTE]
> Omdat een aanmelding is ingeschakeld, is het belangrijk om de browser uit te schakelen met [**WDAC**](/hololens/windows-defender-application-control-wdac). Als een externe client de browser opent en gebruikmaakt van de webversie van Teams, heeft de client toegang tot de aanroep-/chatgeschiedenis.

## <a name="general-deployment-recommendations-and-instructions"></a>Algemene implementatie Aanbevelingen en instructies

Het volgende wordt aanbevolen voor HoloLens 2 implementatiestappen:

1. Gebruik de [nieuwste HoloLens versie van het besturingssysteem](https://aka.ms/hololens2download) als uw basislijn-build.
1. Licenties op basis van gebruikers of apparaten toewijzen:
    1. Licenties op basis van gebruikers en apparaten volgen beide de volgende stappen:
        1. [Maak een groep in AAD en voeg leden toe](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members) voor HoloLens/RA-gebruikers.
        1. [Wijs licenties op basis van apparaten](/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) of gebruikers toe aan deze groep.
        1. (Optioneel) U kunt zich richten op groepen voor MDM-beleid.

1. Apparaten moeten AAD-lid zijn van uw tenant, [automatisch worden ingeschreven](/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm)en geconfigureerd via Auto [Pilot.](/hololens/hololens2-autopilot)
    1. Houd er rekening mee dat de eerste gebruiker op het apparaat de eigenaar van het apparaat is.
    1. Als het apparaat is verbonden met AAD, wordt de gebruiker die de join heeft uitgevoerd, eigenaar van het apparaat.
    1. Zie Apparaateigenaar [voor meer informatie.](/hololens/security-adminless-os#device-owner)
1. [De tenant vergrendelt](/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot) het apparaat zodat het alleen kan worden samengevoegd met uw tenant.
    1. **Aanvullende koppeling:** [CSP voor tenantvergrendeling.](/windows/client-management/mdm/tenantlockdown-csp)
1. Configureer kiosk met behulp van globale toegewezen toegang tot [hier](/hololens/hololens-global-assigned-access-kiosk).
1. U kunt het beste de volgende (optionele) mogelijkheden uitschakelen:
    1. De mogelijkheid om het apparaat hier in de ontwikkelaarsmodus [te zetten.](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock)
    1. Mogelijkheid om verbinding te maken met HoloLens pc om de datum te [kopiëren, USB uitschakelen.](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)
       > [!NOTE]
        > Als u USB niet wilt uitschakelen, maar de mogelijkheid wilt om een inrichtingspakket op het apparaat toe te passen via USB, volgt u de instructies die hier worden [**weergegeven.**](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)

1. Gebruik [WDAC om](/hololens/windows-defender-application-control-wdac) apps toe te staan of te blokkeren op HoloLens 2 apparaat.
1. Werk Remote Assist bij naar de nieuwste versie als onderdeel van de installatie. Er zijn twee opties om dit te doen:
    1. U kunt dit doen door naar Windows **Microsoft Store --> Remote Assist --> en App bijwerken te gaan.**
    1. [ApplicationManagement/AllowAppStoreAutoUpdate](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowappstoreautoupdate) , waarmee automatische app-updates zijn toegestaan, is standaard ingeschakeld. Houd het apparaat aangesloten om updates te ontvangen.
1. [Schakel alle instellingenpagina's uit,](/hololens/settings-uri-list) met uitzondering van de netwerkinstellingen, zodat gebruikers verbinding kunnen maken met gastnetwerken op clientsites.
1. [Updates HoloLens beheren](/hololens/hololens-updates)
    1. Optie om [updates van het besturingssysteem](/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings) te bepalen of vrij te laten stromen.
1. [Algemene apparaatbeperkingen.](/hololens/hololens-common-device-restrictions)
