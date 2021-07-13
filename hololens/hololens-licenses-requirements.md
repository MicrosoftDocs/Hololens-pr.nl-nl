---
title: Licentievereisten
description: Blijf op de hoogte van alle licentievereisten en richtlijnen die u nodig hebt voor het beheer van mobiele apparaten, HoloLens en Remote Assist.
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
ms.openlocfilehash: d0d8aa648df7901dec8636942e43aa549e626d7e
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635888"
---
# <a name="license-requirements"></a>Licentievereisten

## <a name="hololens-2-device-managed"></a>HoloLens 2 Apparaat (beheerd)

[Azure AD-account](https://docs.microsoft.com/azure/active-directory/)

> [!IMPORTANT]
> Active Directory (AD) kan niet worden gebruikt voor het beheren van HoloLens apparaten.

[Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) of een andere MDM.
- [Windows Autopilot voor HoloLens 2](hololens2-autopilot.md)vereenvoudigt de inrichtingservaring voor zowel IT-beheerders als eindgebruikers. IT-beheerders kunnen vooraf HoloLens 2 configureren en bij de eerste keer opstarten worden apparaten geïmplementeerd in een bedrijfsconfig status zonder tussenkomst van de eindgebruiker. 

  > [!NOTE]
  > Windows Autopilot vereist [dat Azure P1](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) en [Automatische](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment) inschrijving eerst worden geconfigureerd voor de Autopilot-stroom met weinig aanraking en apparaatimplementatie. 

### <a name="business-use-case"></a>Bedrijfsgebruikscase: 

- [Implementatiescenario A:](hololens-requirements.md#scenario-a-deploy-to-cloud-connected-devices) proof-of-concept of testimplementatie.

- [Implementatiescenario B:](hololens-requirements.md#scenario-b-deploy-inside-your-organizations-network) implementatie op schaal.

## <a name="hololens-2-device-only-non-managed"></a>HoloLens 2 Alleen apparaat (niet-beheerd)

Wanneer u een Microsoft-account (MSA) of een lokaal account gebruikt, zijn er geen extra licenties vereist voor deze accounts.

[Lokaal account](https://docs.microsoft.com/windows/security/identity-protection/access-control/local-accounts)

- Dit account moet [van tevoren worden ingericht](hololens-provisioning.md#provisioning-package-hololens-wizard) met Windows Configuration Designer (WCD).

[Microsoft-account (MSA)](https://docs.microsoft.com/windows/security/identity-protection/access-control/microsoft-accounts)

> [!WARNING]
> Meerdere gebruikers worden niet ondersteund voor een apparaat dat een van deze accounts gebruikt.

### <a name="business-use-case"></a>Bedrijfsgebruikscase: 

- [Implementatiescenario C:](hololens-requirements.md#scenario-c-deploy-in-secure-offline-environment) offline of beveiligde implementatie.
 
## <a name="dynamics-365-licensing-and-requirements"></a>Licenties en vereisten voor Dynamics 365

### <a name="dynamics-365-remote-assist"></a>Dynamics 365 Remote Assist 

#### <a name="admin"></a>Beheerder

- Azure AD-account (vereist voor het kopen van het abonnement en het toewijzen van licenties)
- [Remote Assist abonnement](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (of [Remote Assist proefversie](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist))
    
#### <a name="dynamics-365-remote-assist-user"></a>Dynamics 365 Remote Assist gebruiker

- Azure AD-account

- Remote Assist licentie 

  > [!NOTE]
  > Microsoft Teams is gebundeld met Remote Assist

- Netwerkverbinding

#### <a name="microsoft-teams-user"></a>Microsoft Teams gebruiker

- Azure AD-account

- Microsoft Teams of [Teams Freemium](https://products.office.com/microsoft-teams/free).

- Netwerkverbinding

Als u van plan bent dit scenario voor [verschillende tenants te implementeren,](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)hebt u mogelijk een licentie voor informatiebarrières nodig. Zie [dit artikel om](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) te bepalen of een licentie voor een gegevensbarrière is vereist.

### <a name="dynamics-365-guides"></a>Dynamics 365 Guides 

#### <a name="admin"></a>Beheerder

- Azure AD-account (vereist voor het kopen van het abonnement en het toewijzen van licenties)
- Abonnement op Dynamics 365 [Guides of gratis proefversie](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-one)

#### <a name="guides-author"></a>Auteur van handleidingen

1. Azure AD-account
1. [Dynamics 365 Guides licentie](/dynamics365/mixed-reality/guides/requirements)
1. Dynamics 365 Guides toepassing geïnstalleerd op een pc of HoloLens
1. [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (gebruikt om het analytics-dashboard weer te geven)
1. Rol van auteur (voor het maken van handleidingen)
1. Netwerkverbinding

#### <a name="guides-user"></a>Gebruikershandleidingen

1. Azure AD-account
1. [Dynamics 365 Guides licentie](/dynamics365/mixed-reality/guides/requirements)
1. Dynamics 365 Guides-app geïnstalleerd op een HoloLens
1. Operatorrol (voor het testen of gebruiken van handleidingen)
1. Netwerkverbinding
