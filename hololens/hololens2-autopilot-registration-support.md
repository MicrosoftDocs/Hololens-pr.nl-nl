---
title: Windows Autopilot registratieondersteuning voor HoloLens 2
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
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/25/2021
ms.locfileid: "111379497"
---
# <a name="hololens-2-registration-support-for-autopilot"></a>HoloLens 2 registratieondersteuning voor Autopilot

Klanten en Microsoft Cloud Solution Providers (CSP's) kunnen zich nu registreren HoloLens 2 apparaten door rechtstreeks aanvragen te verzenden naar Microsoft-ondersteuning. Deze pagina bevat een overzicht van de vereisten voor de volgende ondersteunde Autopilot-registratiescenario's:

- **HoloLens 2 Autopilot-registratie voor apparaten.** Verstuurt een aanvraag voor het registreren HoloLens 2 apparaten in Windows Autopilot.
- **HoloLens 2-hashaanvraag voor apparaathardware in.** Verstuurt een aanvraag naar Microsoft-ondersteuning om u hardwarehashes te bieden die klanten of CSP's kunnen gebruiken om apparaten zelf te registreren via Microsoft Intune of microsoft Partner Center.
- **HoloLens 2 Autopilot-registratie van het apparaat.** Hiermee wordt een aanvraag ingediend om apparaten uit Windows Autopilot verwijderen, die doorgaans worden gebruikt in scenario's met het einde van de levensduur van apparaten.

In de volgende tabel vindt u informatie over de gegevens die u moet verzamelen *voordat* u registratieaanvragen indient bij Microsoft-ondersteuning.

| Vereiste informatie | Beschrijving | Autopilot-registratie  | Hardware-hashaanvraag | Autopilot-registratie |
------------|-------------------------------|--------------------------------------------------|------------------------------|--------------------------------|
|  Azure Active Directory tenant-id    |    Uw Azure Active Directory tenant-id is een guid (Globally Unique Identifier) die anders is dan de naam of het domein van uw organisatie.    Meld u aan bij Azure Portal om uw tenant-id [te vinden.](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)    |     ✔️                         |                              |                         ✔️                        |
|  Azure Active Directory Domain Name    |   Uw domeinnaam op het hoogste niveau; Bijvoorbeeld: contoso.com.    |     ✔️                         |                              |                         ✔️                        |
|  Bewijs van eigendom    |   Controleer het eigendomsbewijs door de oorspronkelijke factuur van de verkoop of factuur in PDF-indeling te uploaden. Schermopnamen worden niet geaccepteerd. De factuur voor verkoop of factuur moet het volgende bevatten: Serienummers van apparaten. Bedrijfsnaam.     |     ✔️                         |              ✔️                |                         ✔️                        |
|  Serienummers van apparaten    |   Upload een Excel-bestand in CSV-indeling met elk serienummer van een apparaat op een nieuwe regel.     |     ✔️                         |              ✔️                |                         ✔️                        |

## <a name="submit-support-requests"></a>Ondersteuningsaanvragen indienen

> [!div class="nextstepaction"]
> [Ondersteuning voor Autopilot-registratie indienen voor HoloLens 2](https://prod.support.services.microsoft.com/supportrequestform/0d8bf192-cab7-6d39-143d-5a17840b9f5f)
