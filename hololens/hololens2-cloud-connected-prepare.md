---
title: 'Implementatiehandleiding : Cloudgeconnecteerde HoloLens 2 implementatie op schaal met Remote Assist - Voorbereiden'
description: Meer informatie over het voorbereiden van de inschrijving van HoloLens-apparaten via een verbonden cloudnetwerk met behulp van Azure Active Directory en identiteitsbeheer.
keywords: HoloLens, beheer, cloud verbonden, Remote Assist, AAD, Azure AD, MDM, Mobile Device Management
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 21132ed5d1e84d92a877747ac9a4c090b177ca08
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924567"
---
# <a name="prepare---cloud-connected-guide"></a>Voorbereiden - Handleiding voor verbonden cloud

Aan het einde van dit artikel hebt u Azure AD, MDM ingesteld en meer inzicht in het gebruik van Azure AD-accounts en netwerkvereisten. Deze sectie van de handleiding helpt u en uw organisatie bij het voorbereiden van de implementatie HoloLens 2 in de cloud en het gebruik van Dynamics 365 Remote Assist. Het gaat over het belang van elk onderdeel van uw infrastructuur en biedt koppelingen naar handleidingen om u te helpen deze onderdelen zo nodig in te stellen.

## <a name="infrastructure-essentials"></a>Infrastructure Essentials

Voor zowel persoonlijke als zakelijke implementatiescenario's is een MDM-systeem de essentiële infrastructuur die vereist is voor het implementeren en beheren Windows 10 Holographic apparaten. Een Azure AD Premium-abonnement wordt aanbevolen als id-provider en is vereist voor de ondersteuning van bepaalde mogelijkheden.

### <a name="azure-active-directory"></a>Azure Active Directory

Azure AD is een cloudgebaseerde adreslijstservice die identiteits- en toegangsbeheer biedt. Organisaties die gebruikmaken van Microsoft Office 365 of Intune maken al gebruik van Azure AD, dat drie edities heeft: Free, Premium P1 en Premium P2 (zie [Azure Active Directory editions](https://azure.microsoft.com/documentation/articles/active-directory-editions).) Alle edities ondersteunen Azure AD-apparaatregistratie, maar Premium P1 is vereist voor het inschakelen van automatische MDM-inschrijving, die we later in deze handleiding gaan gebruiken.

> [!IMPORTANT]
> Het is essentieel om een Azure Active Directory omdat HoloLens-apparaten geen ondersteuning bieden voor on-premises AD-join. Als u&#39;nog geen tenant Azure Active Directory ingesteld, gaat u naar Een nieuwe [tenant maken in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-access-create-new-tenant).

## <a name="identity-management"></a>Identiteitsbeheer

Werknemers kunnen slechts één account gebruiken om een apparaat te initialiseren, zodat het&#39;is dat uw organisatie bepaalt welk account het eerst wordt ingeschakeld. Het gekozen account bepaalt wie het apparaat beheert en beïnvloedt uw beheermogelijkheden.

In deze handleiding hebben we [](https://docs.microsoft.com/hololens/hololens-identity) ervoor gekozen dat we voor de gebruikte identiteit Azure AD-accounts of Azure Active Directory gebruiken. Er zijn verschillende voordelen voor Azure AD-accounts die we willen gebruiken, zoals:

- Werknemers gebruiken hun Azure AD-account om het apparaat te registreren in Azure AD en registreren het automatisch bij de organisatie&#39;s MDM-oplossing (Azure AD + MDM- vereist Azure AD Premium).
- Azure AD-accounts bieden [ondersteuning voor een enkele aanmelding.](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on) Wanneer een gebruiker zich Remote Assist, wordt de identiteit van de aangemelde Azure AD-gebruiker herkend en wordt de gebruiker aangemeld bij de app voor een gestroomlijnde ervaring.
- Azure AD-accounts hebben extra [verificatieopties](https://docs.microsoft.com/hololens/hololens-identity) via [Windows Hello voor Bedrijven](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification). Naast iris-aanmelding kunnen gebruikers zich aanmelden vanaf een ander apparaat of FIDO-beveiligingssleutels gebruiken.

### <a name="mobile-device-management"></a>Beheer van mobiele apparaten

Microsoft [Intune,](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)onderdeel van de Enterprise Mobility + Security, is een cloudgebaseerd MDM-systeem dat apparaten beheert die zijn verbonden met uw tenant. Net als Office 365 maakt Intune gebruik van Azure AD voor identiteitsbeheer, zodat werknemers dezelfde referenties gebruiken om apparaten in Tetune in te schrijven die ze gebruiken om zich aan te melden bij Office 365. Intune ondersteunt ook apparaten met andere besturingssystemen, zoals iOS en Android, om een volledige MDM-oplossing te bieden. In deze handleiding richten we ons&#39;het gebruik van Intune voor het op schaal inschakelen van een cloudimplementatie met HoloLens 2.

> [!IMPORTANT]
> Het is essentieel om Mobile Device Management te hebben. Als u deze&#39;nog niet hebt ingesteld, volgt u deze handleiding en [gaat u aan de slag met Intune](https://docs.microsoft.com/mem/intune/fundamentals/free-trial-sign-up).

> [!NOTE]
> Meerdere MDM-systemen ondersteunen Windows 10 en bieden de meeste ondersteuning voor implementatiescenario's voor persoonlijke en zakelijke apparaten. MDM-providers die ondersteuning Windows 10 Holographic zijn onder andere: AirWatch, MobileIron en andere. De meeste toonaangevende MDM-leveranciers ondersteunen al integratie met Azure AD. U vindt de MDM-leveranciers die Azure AD ondersteunen in [Azure Marketplace.](https://azure.microsoft.com/marketplace/)

## <a name="network"></a>Netwerk

In deze installatie verwachten we dat HoloLens 2 verbinding maken met internet vanaf elke beschikbare open Wi-Fi netwerk. Omdat een gebruiker de netwerkverbinding kan wijzigen op basis van de locatie, moet hij leren hoe hij [HoloLens-apparaten verbindt met Wi-Fi.](https://docs.microsoft.com/hololens/hololens-network)

Er Dynamics 365 Remote Assist diverse netwerkomstandigheden, waaronder bandbreedte, latentie, jitter en pakketverlies, die van invloed kunnen zijn op uw ervaring met videobellen. Hoewel audio- en videoaanroepen mogelijk zijn in omgevingen met een lagere bandbreedte, kan het zijn dat functies afnemen. Wanneer u Dynamics 365 Remote Assist hololens gebruikt, zijn dit de netwerkvereisten om rekening mee te houden:

**Minimaal:** 1,5 Mbps omhoog/omlaag is vereist voor peer-to-peer video-oproepen van HD-kwaliteit met een resolutie van HD 1080p met 30 mbps.

**Optimaal:** Voor peer-to-peer video-oproepen van HD-kwaliteit met een resolutie van HD 1080p moet 4-5 Mbps omhoog/omlaag worden verwacht.

Meer informatie:

- [Netwerkvereisten](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#network-requirements)
- [Aanbevelingen voor netwerkoptimalisatie](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#dynamics-365-remote-assist-hololens)

### <a name="optional-connect-your-hololens-to-vpn"></a>Optioneel: Uw HoloLens verbinden met VPN

De apparaten die in deze handleiding worden verbonden, gaan verbinding maken met het netwerk via en het externe cloudnetwerk. Het kan zijn dat u voor toegang tot bedrijfsbronnen&#39;uw apparaten via VPN moet verbinden. Er zijn verschillende manieren om uw apparaten te verbinden met VPN, waarbij de eindgebruiker verbinding kan maken via de gebruikersinterface van het apparaat, of de apparaten kunnen worden beheerd en het VPN-profiel kunnen ontvangen van een PPKG of MDM. Het instellen van VPN&#39;niet behandeld in dit artikel&#39;, dus als u meer wilt weten over de verschillende VPN-protocollen of manieren om VPN te beheren, gaat u naar deze handleidingen voor informatie over [HoloLens](https://docs.microsoft.com/hololens/hololens-network#vpn) en VPN.

## <a name="next-step"></a>Volgende stap

> [!div class="nextstepaction"]
> [Cloudgeconnecteerde implementatie - Configureren](hololens2-cloud-connected-configure.md)
