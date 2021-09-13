---
title: Windows Ondersteuning voor Autopilot-registratie voor HoloLens 2
description: Meer informatie over het krijgen van registratieondersteuning voor Autopilot op HoloLens 2 apparaten.
author: joyjaz
ms.author: v-jjaswinski
ms.date: 5/20/2021
ms.prod: hololens
ms.topic: article
ms.custom:
- CI 116283
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: high
keywords: Automatische piloot
manager: ylempidakis
ms.openlocfilehash: cdd2ab68905d5cc82b1c5ccc50640112e857f2f4
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/13/2021
ms.locfileid: "126036159"
---
# <a name="hololens-2-registration-support-for-autopilot"></a>HoloLens 2 Registratieondersteuning voor Autopilot

Klanten en Microsoft Cloud Solution Providers (CSP's) kunnen nu HoloLens 2 registreren door rechtstreeks aanvragen naar de Microsoft-ondersteuning. Op deze pagina worden de vereisten beschreven voor de volgende ondersteunde Autopilot-registratiescenario's:

- **HoloLens 2 Autopilot-apparaatregistratie.** Verstuurt een aanvraag om apparaten HoloLens 2 registreren bij Windows Autopilot.
- **HoloLens 2 hardware-hashaanvraag voor het apparaat.** Verstuurt een aanvraag naar Microsoft-ondersteuning om u hardwarehashes te bieden die klanten of CSP's kunnen gebruiken om apparaten zelf te registreren via Microsoft Intune of microsoft Partner Center.
- **HoloLens 2 Device Autopilot-deregistration .** Hiermee wordt een aanvraag ingediend om apparaten te verwijderen Windows Autopilot, meestal gebruikt in scenario's met het einde van de levensduur van apparaten.

In de volgende tabel vindt u informatie over de informatie die u moet verzamelen *voordat* u registratieaanvragen naar Microsoft-ondersteuning.

| Vereiste informatie | Description | Autopilot-registratie  | Hardware-hashaanvraag | Autopilot-registratie |
------------|-------------------------------|--------------------------------------------------|------------------------------|--------------------------------|
|  Azure Active Directory Tenant-id    |    Uw Azure Active Directory tenant-id is een guid (globally unique identifier) die anders is dan de naam of het domein van uw organisatie.    Meld u aan bij Azure Portal om uw tenant-id [te vinden.](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)    |     ✔️                         |                              |                         ✔️                        |
|  Azure Active Directory Domeinnaam    |   Uw domeinnaam op het hoogste niveau; bijvoorbeeld contoso.com.    |     ✔️                         |                              |                         ✔️                        |
|  Bewijs van eigendom    |   Controleer het eigendomsbewijs door de oorspronkelijke factuur van de verkoop of factuur in PDF-indeling te uploaden. Schermopnamen worden niet geaccepteerd. De factuur voor verkoop of factuur moet het volgende bevatten: Serienummers van apparaten. Bedrijfsnaam.     |     ✔️                         |              ✔️                |                         ✔️                        |
|  Serienummers van apparaten    |   Upload Excel bestand in CSV-indeling met elk serienummer van elk apparaat in een nieuwe regel.     |     ✔️                         |              ✔️                |                         ✔️                        |

## <a name="submit-support-requests"></a>Ondersteuningsaanvragen indienen

> [!div class="nextstepaction"]
> [Ondersteuning voor Autopilot-registratie indienen voor HoloLens 2](https://prod.support.services.microsoft.com/supportrequestform/0d8bf192-cab7-6d39-143d-5a17840b9f5f)
