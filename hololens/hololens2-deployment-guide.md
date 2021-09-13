---
title: Cloud verbonden HoloLens 2 naar externe clients implementeren
description: Implementatiehandleiding voor HoloLens 2 voor externe clients (met Hulp op afstand als voorbeeld)
ms.prod: hololens
ms.sitesec: library
author: qianw211
ms.author: v-qianwen
ms.topic: article
ms.localizationpriority: medium
ms.date: 8/6/2021
ms.custom: ''
ms.reviewer: ''
manager: sekerawa
appliesto:
- HoloLens 2
ms.openlocfilehash: d5cd9c380e0d276f0a8aa9efac14cf44885446e5
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032681"
---
# <a name="deploy-cloud-connected-hololens-2-to-external-clients"></a>Cloud verbonden HoloLens 2 naar externe clients implementeren

Deze handleiding is een aanvulling op de [Cloud Connected Deployment Guide](hololens2-cloud-connected-overview.md). Het wordt gebruikt in situaties waarin uw organisatie apparaten HoloLens 2 verzenden naar de faciliteit van een externe client voor kortetermijn- of langetermijngebruik. De externe client zal zich aanmelden bij het HoloLens 2 apparaat met behulp van de referenties van uw organisatie, en gebruikt Remote Assist [om](/dynamics365/mixed-reality/remote-assist/ra-overview) contact op te nemen met uw experts. Deze handleiding bevat algemene [aanbevelingen HoloLens 2](#general-deployment-recommendations) implementatie die van toepassing zijn op de [](#common-external-client-deployment-concerns) meeste externe HoloLens 2-implementatiescenario's en veelvoorkomende problemen die klanten hebben bij het implementeren van Remote Assist voor extern gebruik. 

## <a name="prerequisites"></a>Vereisten

De volgende infrastructuur moet zijn geïmplementeerd volgens de [Cloud Connected Deployment Guide](hololens2-cloud-connected-overview.md) om de HoloLens 2 implementeren.

- Azure AD Join with MDM Auto Enrollment — MDM-managed (Intune)
- Gebruikers melden zich aan met hun eigen bedrijfsaccount (Azure AD)
    - Eén of meerdere gebruikers per apparaat worden ondersteund.

### <a name="remote-assist-licensing-and-requirements"></a>Remote Assist en vereisten

- Azure AD-account (vereist voor het kopen van het abonnement en het toewijzen van licenties)
- [Remote Assist abonnement](/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (of [Remote Assist proefversie](/dynamics365/mixed-reality/remote-assist/try-remote-assist))

Zie [Meer informatie over Remote Assist](/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist).

### <a name="dynamics-365-remote-assist-user"></a>Dynamics 365 Remote Assist gebruiker

- Remote Assist licentie
- Netwerkverbinding

### <a name="microsoft-teams-user"></a>Microsoft Teams gebruiker

- Microsoft Teams of [Teams Freemium](https://products.office.com/microsoft-teams/free)
- Netwerkverbinding

## <a name="general-deployment-recommendations"></a>Algemene aanbevelingen voor implementatie

U wordt aangeraden de volgende stappen uit te voeren voor HoloLens 2 externe implementatie:

1. Gebruik de [meest recente HoloLens versie van het besturingssysteem](https://aka.ms/hololens2download) als uw basislijn-build.
1. Wijs licenties op basis van gebruikers of apparaten toe door de onderstaande stappen te volgen:
    1. [Maak een groep in AAD en voeg leden toe](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members) voor HoloLens/RA-gebruikers.
    1. [Wijs licenties op basis van apparaten](/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) of gebruikers toe aan deze groep.
    1. (Optioneel) Doelgroepen voor [MDM-beleid (Mobile Device](hololens-enroll-mdm.md) Management).

1. Voeg AAD-apparaten toe aan uw tenant, [schrijf ze](/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm)automatisch in en configureer ze via [Autopilot.](/hololens/hololens2-autopilot) Zie apparaateigenaar voor [meer informatie.](/hololens/security-adminless-os#device-owner)
    1. De eerste gebruiker op het apparaat is de eigenaar van het apparaat.
    1. Als het apparaat is verbonden met AAD, wordt de gebruiker die de join heeft uitgevoerd, eigenaar van het apparaat gemaakt.
    
1. [Vergrendel het](/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot) apparaat met tenant zodat het alleen kan worden samengevoegd door uw tenant.
    1. Zie ook [CSP voor tenantvergrendeling.](/windows/client-management/mdm/tenantlockdown-csp)

1. [Configureer de kioskmodus met behulp van globale toegewezen toegang.](/hololens/hololens-global-assigned-access-kiosk)

1. Schakel de volgende (optionele) mogelijkheden uit:
    1. De mogelijkheid om het apparaat hier in de ontwikkelaarsmodus [te zetten.](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock)
    1. Mogelijkheid om verbinding te maken met HoloLens pc om de datum te [kopiëren, USB uitschakelen.](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)
       > [!NOTE]
        > Als u USB niet wilt uitschakelen, maar de mogelijkheid wilt om een inrichtingspakket toe te passen op het apparaat via USB, volgt u de instructies voor het toestaan van installatie van het [inrichtingspakket.](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)

1. Gebruik [Windows Defender Application Control (WDAC) om](/hololens/windows-defender-application-control-wdac) apps toe te staan of te blokkeren op HoloLens 2 apparaat.
1. Werk Remote Assist bij naar de nieuwste versie als onderdeel van de installatie. Houd rekening met de volgende twee opties:
    1. Ga naar Windows **Microsoft Store --> Remote Assist --> en App bijwerken.**
    1. [ApplicationManagement/AllowAppStoreAutoUpdate,](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowappstoreautoupdate) waarmee automatische app-updates zijn toegestaan, is standaard ingeschakeld. Houd het apparaat aangesloten om updates te ontvangen.
1. [Schakel alle instellingenpagina's uit,](/hololens/settings-uri-list) met uitzondering van de netwerkinstellingen, zodat gebruikers verbinding kunnen maken met gastnetwerken op clientsites.
1. [Updates HoloLens beheren](/hololens/hololens-updates)
    1. Optie om [updates van het besturingssysteem](/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings) te bepalen of vrij te laten stromen.
1. Stel [algemene apparaatbeperkingen in.](/hololens/hololens-common-device-restrictions)

Uw externe clients zijn nu klaar om hun eigen HoloLens 2.

## <a name="common-external-client-deployment-concerns"></a>Veelvoorkomende problemen met de implementatie van externe client

- [Ervoor zorgen dat clients niet met elkaar kunnen communiceren](#ensure-that-external-clients-cant-communicate-with-one-another)
- [Ervoor zorgen dat clients geen toegang hebben tot bedrijfsbronnen](#ensure-that-clients-wont-have-access-to-company-resources)
- [Apps verbergen of beperken](#hidden-or-restricted-apps)
- [Wachtwoorden voor uw clients beheren](#password-management-for-your-clients) 
- [Ervoor zorgen dat clients geen toegang hebben tot de chatgeschiedenis](#ensure-that-clients-wont-have-access-to-chat-history)

### <a name="ensure-that-external-clients-cant-communicate-with-one-another"></a>Zorg ervoor dat externe clients niet met elkaar kunnen communiceren

Remote Assist HoloLens voor HoloLens worden niet ondersteund. Clients kunnen zoeken naar, maar niet met elkaar communiceren. [Informatiebarrières in Microsoft 365](/microsoft-365/compliance/information-barriers) kunnen verder beperken met wie een client kan zoeken en aanroepen. Een andere optie is het gebruik [van Microsoft Teams adreslijst zoeken](/MicrosoftTeams/teams-scoped-directory-search)binnen bereik.

 > [!NOTE]
> Omdat een aanmelding is ingeschakeld, is het belangrijk om de browser uit te schakelen met Windows Defender [Application Control (WDAC).](/hololens/windows-defender-application-control-wdac) Als een externe client de browser opent en gebruikmaakt van de webversie van Teams, heeft de client toegang tot uw chatgeschiedenis.

### <a name="ensure-that-clients-wont-have-access-to-company-resources"></a>Zorg ervoor dat clients geen toegang hebben tot bedrijfsbronnen

Er zijn twee opties die u kunt overwegen.

De eerste optie is een benadering met meerdere lagen:

1. Wijs alleen licenties toe die de gebruiker nodig heeft. Als u geen OneDrive, Outlook, SharePoint, Yammer, enzovoort toewijst, heeft de gebruiker geen toegang tot deze resources. De enige licenties die gebruikers nodig hebben, zijn Remote Assist, Intune en AAD-licenties om te beginnen.
1. Blokkeer apps (zoals e-mail) die u niet wilt gebruiken voor clients (Zie [Apps zijn verborgen of beperkt).](#apps are hidden or restricted)
1. Deel geen gebruikersnamen of wachtwoorden met clients. Als u zich wilt aanmelden HoloLens 2, hebt u een e-mail en een numerieke pincode nodig.

De tweede optie is het maken van een afzonderlijke tenant die clients host (zie afbeelding 1.1).

**Afbeelding 1.1**

![Afbeelding van service-tenant.](./images/hololens-service-tenant-image.png)

### <a name="hidden-or-restricted-apps"></a>Verborgen of beperkte apps

[Kioskmodus](/hololens/hololens-kiosk) en/of [Windows Defender Application Control (WDAC)](/hololens/windows-efender-application-control-wdac) zijn opties voor het verbergen en/of beperken van toepassingen.

### <a name="password-management-for-your-clients"></a>Wachtwoordbeheer voor uw clients

1. Wachtwoordverloopdatum verwijderen. Deze optie kan echter de kans vergroten dat een account wordt gecompromitteerd. Aanbeveling voor NIST-wachtwoorden is om wachtwoorden elke 30-90 dagen te wijzigen.
1. Breid de wachtwoordverlooptijd voor HoloLens 2 apparaten uit tot meer dan 90 dagen.
1. De apparaten moeten worden teruggestuurd naar uw organisatie om de wachtwoorden te wijzigen. Deze optie kan echter problemen veroorzaken als de apparaten naar verwachting meer dan 90 dagen in de fabriek van de client zijn.  
1. Voor apparaten die naar meerdere clients worden verzonden, stelt u wachtwoorden opnieuw in voordat u het apparaat naar clients stuurt.

### <a name="ensure-that-clients-wont-have-access-to-chat-history"></a>Zorg ervoor dat clients geen toegang hebben tot de chatgeschiedenis

Remote Assist wordt de chatgeschiedenis na elke sessie geweken. De chatgeschiedenis is echter beschikbaar voor Microsoft Teams gebruikers.

> [!NOTE]
> Omdat een aanmelding is ingeschakeld, is het belangrijk om de browser uit te schakelen met Windows Defender [Application Control (WDAC).](/hololens/windows-defender-application-control-wdac)  Als een externe client de browser opent en gebruikmaakt van de webversie van Teams, heeft de client toegang tot de aanroep-/chatgeschiedenis.
