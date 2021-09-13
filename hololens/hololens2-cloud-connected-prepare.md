---
title: 'Implementatiehandleiding : Cloudgeconnecteerde HoloLens 2 implementatie op schaal met Remote Assist - Voorbereiden'
description: Meer informatie over het voorbereiden van de registratie van HoloLens via een cloudnetwerk met behulp van Azure Active Directory en identiteitsbeheer.
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
ms.openlocfilehash: 21fffdc24f8682bc44779e1cebe8cd6eacb59619
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032729"
---
# <a name="prepare---cloud-connected-guide"></a>Voorbereiden - Handleiding voor verbonden cloud

Aan het einde van dit artikel hebt u Azure AD en MDM ingesteld en krijgt u meer informatie over het gebruik van Azure AD-accounts en netwerkvereisten. In deze sectie van de handleiding kunt u en uw organisatie zich voorbereiden op het implementeren van HoloLens 2 in de cloud en het gebruik van Dynamics 365 Remote Assist. Het gaat over het belang van elk onderdeel van uw infrastructuur en biedt koppelingen naar handleidingen om u te helpen deze onderdelen zo nodig in te stellen.

## <a name="infrastructure-essentials"></a>Infrastructure Essentials

Voor zowel persoonlijke als zakelijke implementatiescenario's is een MDM-systeem de essentiële infrastructuur die vereist is voor het implementeren en beheren Windows 10 Holographic apparaten. Een Azure AD Premium-abonnement wordt aanbevolen als id-provider en is vereist voor de ondersteuning van bepaalde mogelijkheden.

### <a name="azure-active-directory"></a>Azure Active Directory

Azure AD is een cloudgebaseerde adreslijstservice die identiteits- en toegangsbeheer biedt. Organisaties die gebruikmaken van Microsoft Office 365 of Intune, maken al gebruik van Azure AD, dat drie edities heeft: Free, Premium P1 en Premium P2 (zie [Azure Active Directory editions](https://azure.microsoft.com/documentation/articles/active-directory-editions).) Alle edities ondersteunen Azure AD-apparaatregistratie, maar Premium P1 is vereist voor het inschakelen van automatische MDM-inschrijving. Deze zullen we later in deze handleiding gebruiken.

> [!IMPORTANT]
> Het is essentieel om over een Azure Active Directory te HoloLens apparaten geen ondersteuning bieden voor on-premises AD-join. Als u&#39;nog geen tenant Azure Active Directory ingesteld, gaat u naar Een nieuwe [tenant maken in Azure Active Directory](/azure/active-directory/fundamentals/active-directory-access-create-new-tenant).

## <a name="identity-management"></a>Identiteitsbeheer

Werknemers kunnen slechts één account gebruiken om een apparaat te initialiseren, zodat het&#39;is dat uw organisatie bepaalt welk account het eerst wordt ingeschakeld. Het gekozen account bepaalt wie het apparaat beheert en beïnvloedt uw beheermogelijkheden.

In deze handleiding hebben we [](/hololens/hololens-identity) ervoor gekozen dat we voor de gebruikte identiteit Azure AD-accounts of Azure Active Directory gebruiken. Er zijn verschillende voordelen voor Azure AD-accounts die we willen gebruiken, zoals:

- Werknemers gebruiken hun Azure AD-account om het apparaat te registreren bij Azure AD en registreren het automatisch bij de organisatie&#39;s MDM-oplossing (Azure AD + MDM- vereist Azure AD Premium).
- Azure AD-accounts bieden [ondersteuning voor een enkele aanmelding.](/azure/active-directory/manage-apps/what-is-single-sign-on) Wanneer een gebruiker zich Remote Assist, wordt de identiteit van de aangemelde Azure AD-gebruiker herkend en wordt de gebruiker aangemeld bij de app voor een gestroomlijnde ervaring.
- Azure AD-accounts hebben aanvullende [verificatieopties](/hololens/hololens-identity) via [Windows Hello for Business](/windows/security/identity-protection/hello-for-business/hello-identity-verification). Naast iris-aanmelding kunnen gebruikers zich aanmelden vanaf een ander apparaat of FIDO-beveiligingssleutels gebruiken.

### <a name="mobile-device-management"></a>Beheer van mobiele apparaten

Microsoft [Intune,](/mem/intune/fundamentals/what-is-intune)onderdeel van de Enterprise Mobility + Security, is een cloudgebaseerd MDM-systeem dat apparaten beheert die zijn verbonden met uw tenant. Net als Office 365 gebruikt Intune Azure AD voor identiteitsbeheer, zodat werknemers dezelfde referenties gebruiken om apparaten in te schrijven bij Intune die ze gebruiken om zich aan te melden bij Office 365. Intune ondersteunt ook apparaten met andere besturingssystemen, zoals iOS en Android, om een volledige MDM-oplossing te bieden. In deze handleiding richten we ons&#39;het gebruik van Intune voor het op schaal inschakelen van een cloudimplementatie met HoloLens 2.

> [!IMPORTANT]
> Het is essentieel om Mobile Device Management te hebben. Als u deze&#39;nog niet hebt ingesteld, volgt u deze handleiding en [gaat u aan de slag met Intune](/mem/intune/fundamentals/free-trial-sign-up).

> [!NOTE]
> Meerdere MDM-systemen ondersteunen Windows 10 en bieden de meeste ondersteuning voor implementatiescenario's voor persoonlijke en zakelijke apparaten. MDM-providers die ondersteuning Windows 10 Holographic zijn onder andere: AirWatch, MobileIron en andere. De meeste toonaangevende MDM-leveranciers ondersteunen al integratie met Azure AD. U vindt de MDM-leveranciers die Azure AD ondersteunen in [Azure Marketplace](https://azure.microsoft.com/marketplace/).

## <a name="network"></a>Netwerk

In deze installatie verwachten we dat HoloLens 2 verbinding maken met internet vanaf elk beschikbaar open Wi-Fi netwerk. Omdat een gebruiker de netwerkverbinding mogelijk moet wijzigen op basis van de locatie, moet hij leren hoe hij of zij HoloLens [verbinden met Wi-Fi.](/hololens/hololens-network)

Er Dynamics 365 Remote Assist diverse netwerkomstandigheden, waaronder bandbreedte, latentie, jitter en pakketverlies, die van invloed kunnen zijn op uw ervaring met videobellen. Hoewel audio- en videoaanroepen mogelijk zijn in omgevingen met een lagere bandbreedte, kan het zijn dat functies afnemen. Wanneer u Dynamics 365 Remote Assist op HoloLens, zijn hier de netwerkvereisten om rekening mee te houden:

**Minimaal:** 1,5 Mbps omhoog/omlaag is vereist voor peer-to-peer video-oproepen van HD-kwaliteit met een resolutie van HD 1080p met 30 mbps.

**Optimaal:** Voor peer-to-peer video-oproepen van HD-kwaliteit met een resolutie van HD 1080p moet 4-5 Mbps omhoog/omlaag worden verwacht.

Meer informatie:

- [Netwerkvereisten](/dynamics365/mixed-reality/remote-assist/requirements#network-requirements)
- [Aanbevelingen voor netwerkoptimalisatie](/dynamics365/mixed-reality/remote-assist/requirements#dynamics-365-remote-assist-hololens)

### <a name="optional-connect-your-hololens-to-vpn"></a>Optioneel: Verbinding maken uw HoloLens naar VPN

De apparaten die in deze handleiding worden verbonden, gaan verbinding maken met het netwerk via en het externe cloudnetwerk. Het kan zijn dat u voor toegang tot bedrijfsbronnen&#39;uw apparaten via VPN moet verbinden. Er zijn verschillende manieren om uw apparaten te verbinden met VPN, waarbij de eindgebruiker verbinding kan maken via de gebruikersinterface van het apparaat, of de apparaten kunnen worden beheerd en het VPN-profiel kunnen ontvangen van een PPKG of MDM. Het instellen van VPN wordt&#39;niet behandeld in dit artikel. Als u meer wilt weten over de verschillende VPN-protocollen of manieren om VPN te beheren&#39;, gaat u naar deze handleidingen voor informatie over [HoloLens en VPN.](/hololens/hololens-network#vpn)

## <a name="next-step"></a>Volgende stap

> [!div class="nextstepaction"]
> [Cloudgeconnecteerde implementatie - Configureren](hololens2-cloud-connected-configure.md)
