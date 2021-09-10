---
title: Licentievereisten
description: Blijf op de hoogte van alle licentievereisten en richtlijnen die u nodig hebt voor mobile device management, HoloLens en Remote Assist.
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
audience: HoloLens
ms.topic: article
ms.localizationpriority: high
ms.date: 1/23/2020
ms.reviewer: ''
manager: bradke
appliesto:
- HoloLens 2
ms.openlocfilehash: 6224cd5e07794d9fca3c0a406e787d1a3fd88b43
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428018"
---
# <a name="license-requirements"></a>Licentievereisten

## <a name="overview"></a>Overzicht
Deze pagina biedt een overzicht op hoog niveau van de licenties en accounts die nodig zijn voor het implementeren van zowel beheerde als HoloLens 2 apparaten in uw organisatie. Het bevat ook informatie over licentieverlening voor Dynamics 365 [Remote Assist](#dynamics-365-remote-assist) en [Guides.](#dynamics-365-guides)

## <a name="hololens-2-license-and-account-requirements"></a>HoloLens 2 licentie- en accountvereisten

 
|       &nbsp;      | Beheerde HoloLens | Niet-HoloLens |
|-------------------|-----------------|---------------------|
| **Bedrijfsgebruikscase** | | |
| [Implementeren naar met de cloud verbonden apparaten - proof of concept/pilot-implementatie](hololens-requirements.md#scenario-a-deploy-to-cloud-connected-devices)  | ✔️| |
| [Implementeren binnen het netwerk van uw organisatie - implementatie op schaal](hololens-requirements.md#scenario-b-deploy-inside-your-organizations-network) | ✔️| |
| [Implementeren in een beveiligde offlineomgeving](hololens-requirements.md#scenario-c-deploy-in-secure-offline-environment) | | ✔️ |
| **Licenties** | | |
| Azure Active Directory | ✔️ | |
| MDM (Intune<sup>1</sup> of <sup>2</sup>) | ✔️  | |
| **Accounts** |  | |
| Azure AD-beheerdersaccount | ✔️ |  |
| Azure AD-gebruikersaccount | ✔️ | |
| [Microsoft-account (MSA)](/windows/security/identity-protection/access-control/microsoft-accounts)| | ✔️ |
| [Lokaal account](/windows/security/identity-protection/access-control/local-accounts)<sup>3</sup> | | ✔️ |
- <sup>1</sup> [Automatische inschrijving tijdens de](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment) eerste installatie van het apparaat, waarmee apparaten worden geregistreerd en Azure Active Directory en het apparaat kan worden beheerd met Intune.
- <sup>2</sup> [Windows Autopilot voor HoloLens 2](hololens2-autopilot.md) vereenvoudigt de inrichtingservaring voor zowel IT-beheerders als eindgebruikers. IT-beheerders kunnen vooraf HoloLens 2 configureren en bij de eerste keer opstarten worden apparaten geïmplementeerd in een bedrijfsklaar status zonder tussenkomst van de eindgebruiker.
- <sup>3</sup> Dit account moet [van tevoren worden ingericht](hololens-provisioning.md#provisioning-package-hololens-wizard) met Windows Configuration Designer (WCD).

> [!IMPORTANT]
> Active Directory (AD) kan niet worden gebruikt voor het beheren van HoloLens apparaten.
 
> [!WARNING]
> Meerdere gebruikers worden niet ondersteund voor een apparaat met een MSA- of lokaal account.

## <a name="dynamics-365-licensing-and-requirements"></a>Licenties en vereisten voor Dynamics 365

### <a name="dynamics-365-remote-assist"></a>Dynamics 365 Remote Assist 

#### <a name="admin"></a>Beheerder

- Azure AD-account (vereist voor het kopen van het abonnement en het toewijzen van licenties)
- [Remote Assist (of](/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) Remote Assist [Proefversie](/dynamics365/mixed-reality/remote-assist/try-remote-assist))
    
#### <a name="dynamics-365-remote-assist-user"></a>Dynamics 365 Remote Assist gebruiker

- Azure AD-account

- Remote Assist licentie 

  > [!NOTE]
  > Microsoft Teams is gebundeld met Remote Assist

- Netwerkverbinding

#### <a name="microsoft-teams-user"></a>Microsoft Teams gebruiker

- Azure AD-account

- Microsoft Teams [of Teams Freemium](https://products.office.com/microsoft-teams/free)

- Netwerkverbinding

Als u van plan bent dit scenario voor verschillende [tenants te implementeren,](/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)hebt u mogelijk een licentie voor informatiebarrières nodig. Zie [dit artikel om](/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) te bepalen of een licentie voor een informatiebarrière is vereist.

### <a name="dynamics-365-guides"></a>Dynamics 365 Guides 

#### <a name="admin"></a>Beheerder

1. Azure AD-account (vereist voor het kopen van het abonnement en het toewijzen van licenties)
2. Abonnement op Dynamics 365 [Guides of gratis proefversie](/dynamics365/mixed-reality/guides/setup-step-one)

#### <a name="guides-author"></a>Auteur van handleidingen

1. Azure AD-account
1. [Dynamics 365 Guides licentie](/dynamics365/mixed-reality/guides/requirements)
1. Dynamics 365 Guides geïnstalleerd op een pc of HoloLens
1. [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (gebruikt om het analytics-dashboard weer te geven)
1. Rol van auteur (voor het maken van handleidingen)
1. Netwerkverbinding

#### <a name="guides-user"></a>Gebruikershandleidingen

1. Azure AD-account
1. [Dynamics 365 Guides licentie](/dynamics365/mixed-reality/guides/requirements)
1. Dynamics 365 Guides-app geïnstalleerd op een HoloLens
1. Operatorrol (voor het testen of gebruiken van handleidingen)
1. Netwerkverbinding
