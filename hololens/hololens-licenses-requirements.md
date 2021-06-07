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
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 2f7af532d2172dcaa6514ee11dbb0d6ab5631929
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379433"
---
# <a name="license-requirements"></a>Licentievereisten

## <a name="mobile-device-management-mdm-licenses-guidance"></a>Richtlijnen voor MDM-licenties (Mobile Device Management)

Als u van plan bent uw HoloLens-apparaten te beheren, hebt u Azure AD en een MDM nodig. Active Director (AD) kan niet worden gebruikt voor het beheren van HoloLens-apparaten.
Als u van plan bent een andere MDM dan Intune te gebruiken, [is een Azure Active Directory licenties](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) vereist.
Als u van plan bent Om Intune als MDM te gebruiken, leest u de lijst met [suites](https://docs.microsoft.com/intune/fundamentals/licenses) met Intune-licenties. **Houd er rekening mee dat Azure AD is opgenomen in het merendeel van deze suites.**

## <a name="identify-the-licenses-needed-for-your-scenario-and-products"></a>De licenties identificeren die nodig zijn voor uw scenario en producten

### <a name="hololens-1st-gen-licenses-requirements"></a>Licentievereisten voor HoloLens (eerste generatie)

Mogelijk moet u uw HoloLens-apparaat (1e generatie) upgraden naar Windows Holographic for Business. (Zie [Commerciële functies van HoloLens om](holoLens-commercial-features.md#feature-comparison-between-editions) te bepalen of u een upgrade moet uitvoeren.

 In dat laatste moet u het volgende doen:

- Een HOLOLens Enterprise-licentie-XML-bestand verkrijgen
- Pas het XML-bestand toe op de HoloLens. U kunt dit doen via een [inrichtingspakket](hololens-provisioning.md) of via uw [mobiele Apparaatbeheer](https://docs.microsoft.com/intune/configuration/holographic-upgrade)

### <a name="remote-assist-license-requirements"></a>Remote Assist licentievereisten

Zorg ervoor dat u over de vereiste licentie en het vereiste apparaat hebt. Raadpleeg de documentatie [over vereisten.](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements)

1. [Remote Assist licentie](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist)
    1. Of probeer een [Remote Assist proefversie](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)
1. [Teams Freemium/Teams](https://products.office.com/microsoft-teams/free)
1. [Azure Active Directory (Azure AD)-licentie](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)

Als u van plan bent dit scenario voor verschillende **[tenants te implementeren,](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)** hebt u mogelijk een licentie voor informatiebarrières nodig. Raadpleeg dit [artikel om](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) te bepalen of een licentie voor een gegevensbarrière is vereist.

### <a name="guides-license-requirements"></a>Licentievereisten voor gidsen

Bekijk de [bijgewerkte licentie- en apparaatvereisten.](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements)

1. [Azure Active Directory (Azure AD)-licentie](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
1. [Power BI](https://powerbi.microsoft.com/desktop/)
1. [Gidsen](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup)
