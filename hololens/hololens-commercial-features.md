---
title: Commerciële functies
description: Meer informatie over de Microsoft HoloLens Commercial Suite functies die het voor bedrijven eenvoudiger maken om HoloLens-apparaten te beheren.
author: scooley
ms.author: scooley
ms.date: 08/26/2019
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
audience: ITPro
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
keywords: HoloLens, commercieel, functies, mdm, beheer van mobiele apparaten, kioskmodus
ms.openlocfilehash: 3682a2633477d68f61dba8a674846857947a3d15
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/25/2021
ms.locfileid: "111379353"
---
# <a name="commercial-features"></a>Commerciële functies

HoloLens bevat functies die het voor bedrijven eenvoudiger maken om HoloLens-apparaten te beheren.

Op HoloLens 2 apparaat zijn commerciële functies beschikbaar.

HoloLens (1e generatie) heeft twee licentieopties: de licentie voor ontwikkelaars en een commerciële licentie. Als u de commerciële mogelijkheden van HoloLens wilt ontgrendelen, upgradet u van de ontwikkelaarslicentie naar een commerciële licentie. Als u de Microsoft HoloLens Commercial Suite wilt kopen, neem dan contact op met uw Microsoft-account manager.

>[!VIDEO https://www.youtube.com/embed/tNd0e2CiAkE]

## <a name="key-commercial-features"></a>Belangrijkste commerciële functies

- **Kioskmodus.** U kunt HoloLens gebruiken in de demo of presentatie-ervaring met behulp van de kioskmodus om te beperken welke apps kunnen worden uitgevoerd.

  ![Met behulp van de kioskmodus wordt HoloLens rechtstreeks in de app van uw keuze gelanceerd.](images/201608-kioskmode-400px.png)

- **Mobile Device Management (MDM) voor HoloLens.** Uw IT-afdeling kan meerdere HoloLens-apparaten tegelijk beheren met behulp van oplossingen zoals Microsoft Intune. U kunt instellingen beheren, apps selecteren die u wilt installeren en beveiligingsconfiguraties instellen die zijn afgestemd op de behoeften van uw organisatie.

  ![Mobile Device Management op HoloLens biedt apparaatbeheer op bedrijf niveau op meerdere apparaten.](images/201608-enterprisemanagement-400px.png)

- **Windows Update voor Bedrijven.** Windows Update voor Bedrijven biedt beheerde updates van besturingssystemen voor apparaten en ondersteuning voor het langetermijnservicekanaal.
- **Gegevensbeveiliging.** BitLocker-gegevensversleuteling is ingeschakeld op HoloLens om hetzelfde beveiligingsniveau te bieden als elk ander Windows-apparaat.
- **Toegang via het werk.** Iedereen in uw organisatie kan op afstand verbinding maken met het bedrijfsnetwerk via VPN (Virtual Private Network) op een HoloLens. HoloLens heeft ook toegang tot Wi-Fi netwerken waarvoor referenties zijn vereist.
- **Microsoft Store voor Bedrijven.** Uw IT-afdeling kan ook een persoonlijke winkel voor ondernemingen instellen, die alleen de apps van uw bedrijf bevat voor uw specifieke HoloLens-gebruik. Distribueren van uw bedrijfssoftware veilig naar de geselecteerde groep zakelijke gebruikers.

## <a name="feature-comparison-between-editions"></a>Functievergelijking tussen edities

|Functies |HoloLens (1e generatie) Development Edition |HoloLens (1e generatie) Commercial Suite |HoloLens 2 |
|---|:---:|:---:|:---:|
|Apparaatversleuteling (BitLocker) | |✔️ |✔️ |
|Virtueel particulier netwerk (VPN) | |✔️ |✔️ |
|[Kioskmodus](hololens-kiosk.md) | |✔️ |✔️ |
|**Beheer en implementatie** | | | |
|het beheren van mobiele apparaten | |✔️ |✔️ |
|Mogelijkheid om uitschrijving te blokkeren | |✔️ |✔️ |
|Bedrijfstoegang op basis van Wi-Fi certificaat | |✔️ |✔️ |
|Microsoft Store (consument) |Consument |Filteren met behulp van MDM |Filteren met behulp van MDM |
|[Business Store-portal](https://docs.microsoft.com/microsoft-store/working-with-line-of-business-apps) | |✔️ |✔️ |
|**Beveiliging en identiteit** | | | |
|Aanmelden met behulp van Azure Active Directory (Azure AD)-account |✔️ |✔️ |✔️ |
|Aanmelden met een Microsoft-account (MSA) |✔️ |✔️ |✔️ |
|Referenties van de volgende generatie met pincode ontgrendelen |✔️ |✔️ |✔️ |
|[Beveiligd opstarten](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot) |✔️ |✔️ |✔️ |
|**Onderhoud en ondersteuning** | | | |
|Automatische systeemupdates wanneer ze binnenkomen |✔️ |✔️ |✔️ |
|[Windows Update voor Bedrijven](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) | |✔️ |✔️ |
|Long-Term Servicing Channel (LTSC) | |✔️ |✔️ |

## <a name="enabling-commercial-features"></a>Commerciële functies inschakelen

De IT-beheerder van uw organisatie kan commerciële functies instellen, zoals Microsoft Store voor Bedrijven, kioskmodus en Wi-Fi toegang. De [Microsoft HoloLens](index.yml) bevat stapsgewijs instructies voor het registreren van apparaten en het installeren van apps vanuit Microsoft Store voor Bedrijven.

## <a name="see-also"></a>Zie ook

- [Microsoft HoloLens](index.yml)
- [Kioskmodus](hololens-kiosk.md)
- [CSP's die worden ondersteund op HoloLens-apparaten](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices)
- [Microsoft Store For Business- en Line-Of-Business-toepassingen](https://blogs.technet.microsoft.com/sbucci/2016/04/13/windows-store-for-business-and-line-of-business-applications/)
- [Werken met Line-Of-Business-apps](/microsoft-store/working-with-line-of-business-apps)
