---
title: 'Implementatiehandleiding: zakelijk verbonden HoloLens 2 met Dynamics 365 Guides - Voorbereiden'
description: Meer informatie over het voorbereiden van de registratie van HoloLens 2 apparaten via een bedrijfsnetwerk dat is verbonden met Dynamics 365 Guides.
keywords: HoloLens, beheer, zakelijk verbonden, Dynamics 365 Guides, AAD, Azure AD, MDM, Mobile Device Management
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 5d8fc2eb0a8dafaae0e1b222b7451877975cf90b
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032686"
---
# <a name="prepare---corporate-connected-guide"></a>Voorbereiden - Corporate Connected Guide
## <a name="infrastructure-essentials"></a>Infrastructure Essentials
Voor zowel persoonlijke als zakelijke implementatiescenario's is een MDM-systeem (Mobile Device Management) de essentiële infrastructuur die vereist is voor het implementeren en beheren van Windows 10-apparaten, met name de HoloLens 2. Een [Azure AD Premium wordt](/azure/active-directory/fundamentals/active-directory-get-started-premium) aanbevolen als een id-provider en is vereist **voor** de ondersteuning van bepaalde mogelijkheden.

> [!NOTE]
> Hoewel de HoloLens 2 wordt geïmplementeerd en beheerd als een mobiel apparaat, wordt het meestal gebruikt als een gedeeld apparaat tussen veel gebruikers.

## <a name="azure-active-directory"></a>Azure Active Directory
Azure AD is een cloudgebaseerde adreslijstservice die identiteits- en toegangsbeheer biedt. Organisaties die gebruikmaken van Microsoft Office 365 of Intune, maken al gebruik van Azure AD, dat drie edities heeft: Free, Premium P1 en Premium P2 (zie [Azure Active Directory editions).](https://azure.microsoft.com/documentation/articles/active-directory-editions) Alle edities ondersteunen Azure AD-apparaatregistratie, maar Premium P1 is vereist voor het inschakelen van automatische inschrijving bij MDM, die we later in deze handleiding gaan gebruiken.
> [!Important]
> Het is essentieel om een Azure AD te hebben omdat HoloLens geen ondersteuning bieden voor on-premises AD-join. Als u nog geen Azure AD hebt ingesteld, volgt u de instructies om aan de slag te gaan en Een nieuwe [tenant maken in Azure Active Directory](/azure/active-directory/fundamentals/active-directory-access-create-new-tenant).

## <a name="identity-management"></a>Identiteitsbeheer
In deze handleiding zijn [Azure AD-accounts](/hololens/hololens-identity) de identiteit die wordt gebruikt. Azure AD-accounts hebben verschillende voordelen, zoals:

- Werknemers gebruiken hun Azure AD-account om het apparaat te registreren bij Azure AD en kunnen het automatisch inschrijven bij de MDM-oplossing van de organisatie (Azure AD+ MDM- vereist een [Azure AD Premium-abonnement).](/azure/active-directory/fundamentals/active-directory-get-started-premium)
- Azure AD-accounts hebben extra [verificatieopties](/hololens/hololens-identity) via [Windows Hello for Business.](/windows/security/identity-protection/hello-for-business/hello-identity-verification) Naast het aanmelden bij Iris kunnen gebruikers zich aanmelden vanaf een ander apparaat of gebruikmaken van FIDO-beveiligingssleutels.

> [!WARNING] 
> Werknemers kunnen slechts één account gebruiken om een apparaat te initialiseren. Het is dus belangrijk dat uw organisatie bepaalt welk **account eerst wordt ingeschakeld.** Het gekozen account bepaalt wie het apparaat beheert en beïnvloedt uw beheermogelijkheden.

## <a name="mobile-device-management"></a>Beheer van mobiele apparaten
Microsoft Intune, onderdeel van Enterprise Mobility + Security, is een cloudgebaseerd MDM-systeem dat apparaten beheert die zijn verbonden met uw tenant. Net Office 365 gebruikt Intune Azure AD voor identiteitsbeheer, zodat werknemers dezelfde referenties gebruiken om apparaten in te schrijven bij Intune die ze gebruiken om zich aan te melden bij Office 365. Intune ondersteunt ook apparaten met andere besturingssystemen, zoals iOS en Android, om een volledige MDM-oplossing te bieden. In deze handleiding richten we ons op het gebruik van Intune voor het inschakelen van een implementatie in uw interne netwerk met HoloLens 2.
> [!Important] 
> Het is essentieel om Mobile Device Management te hebben. Als u deze nog niet hebt ingesteld, volgt u deze handleiding en gaat u aan de slag met Intune.

> [!Important]
> Als u Gidsen wilt gebruiken, is een Azure AD-account vereist.

> [!Note] 
> Meerdere MDM-systemen ondersteunen Windows 10 en bieden de meeste ondersteuning voor implementatiescenario's voor persoonlijke en zakelijke apparaten. MDM-providers die ondersteuning Windows 10 Holographic zijn onder andere: AirWatch, MobileIron en andere. De meeste toonaangevende MDM-leveranciers ondersteunen al integratie met Azure AD. U vindt de meest recente lijst met MDM-leveranciers die ondersteuning bieden voor Azure AD in [Azure Marketplace](https://azuremarketplace.microsoft.com/marketplace/apps/category/azure-active-directory-apps).

## <a name="network-access"></a>Netwerktoegang 
Dynamics 365 Guides is een cloudtoepassing. Als uw netwerkbeheerder een goedgekeurde lijst heeft, moet deze mogelijk IP-adressen en/of eindpunten toevoegen die nodig zijn om verbinding te maken met de Dynamics 365-servers. [Meer informatie over het deblokkeren van IP-adressen en URL's.](/power-platform/admin/online-requirements#ip-addresses-and-urls)

## <a name="certificates"></a>Certificaten
Certificaten helpen de beveiliging te verbeteren door accountverificatie, Wi-Fi, VPN-versleuteling en SSL-versleuteling van webinhoud. Hoewel beheerders certificaten op apparaten handmatig kunnen beheren via inrichtingspakketten, is het een best practice om uw MDM-systeem te gebruiken voor het beheren van deze certificaten gedurende de hele levenscyclus, van inschrijving tot verlenging en intrekking. 

Uw MDM-systeem kan deze certificaten automatisch implementeren in de certificaatopslag van de apparaten nadat u ze hebt ingeschreven (zolang uw MDM-systeem ondersteuning biedt voor **de Simple Certificate Enrollment Protocol (SCEP)** of **Public Key Cryptography Standards #12 (PKCS #12)**). [Meer informatie over certificaattypen en -profielen die u gebruikt met Microsoft Intune.](/mem/intune/protect/certificates-configure) MDM kan ook geregistreerde clientcertificaten opvragen en verwijderen of een nieuwe inschrijvingsaanvraag activeren voordat het huidige certificaat is verlopen.

Als uw MDM-systemen al zijn geconfigureerd voor certificaten, verwijzen wij u naar Certificaten en [netwerkprofielen](/hololens/hololens-certificates-network) voorbereiden voor HoloLens 2 om te beginnen met het implementeren van certificaten en profielen voor uw HoloLens 2 apparaten.

## <a name="scep"></a>SCEP

De volgende services zijn vereist voor SCEP-implementatie, met uitzondering van de Web toepassingsproxy Server.

- [Certificeringsinstantie](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj125375(v=ws.11))
- [NDES-serverfunctie](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831498(v=ws.11))
- [Microsoft Intune-connector](/mem/intune/protect/certificates-scep-configure#install-the-microsoft-intune-connector)

U moet uw NDES-URL ook extern publiceren naar uw bedrijfsnetwerk met behulp van [de Azure AD-toepassingsproxy of webtoegangsproxy.](/azure/active-directory/manage-apps/application-proxy-add-on-premises-application) U kunt ook een andere omgekeerde proxy naar keuze gebruiken.

![SCEP-gegevensstroom.](./images/hololens2-scep-info-flow.png)

Als uw netwerk nog geen ondersteuning biedt voor SCEP of als u niet zeker weet of uw netwerk juist is ingesteld voor SCEP met Intune, verwijst u naar Infrastructuur configureren om SCEP met [Intune te ondersteunen.](/mem/intune/protect/certificates-scep-configure)

Als uw infrastructuur scEP al ondersteunt, [](/mem/configmgr/protect/deploy-use/create-certificate-profiles) moet u een profiel maken voor elk SCEP-certificaat dat door HoloLens 2 wordt gebruikt. [](/mem/intune/protect/certificates-profile-scep) Als u problemen hebt met SCEP, gebruikt u Problemen met het gebruik van [SCEP-certificaatprofielen](/troubleshoot/mem/intune/troubleshoot-scep-certificate-profiles)oplossen om certificaten in te Microsoft Intune.

## <a name="pkcs"></a>PKCS
Intune ondersteunt ook het gebruik van pkcs-certificaten (private en public key pair). Referentie [Gebruik persoonlijke en openbare-sleutelcertificaten in Microsoft Intune](/mem/intune/protect/certificates-pfx-configure) voor meer informatie.

## <a name="proxy"></a>Proxy
De meeste bedrijfs intranetnetwerken maken gebruik van een proxy voor het beheren van extern verkeer. Met HoloLens 2 kunt u een proxyserver configureren voor ethernet-, Wi-Fi- en VPN-verbindingen.

Er zijn enkele verschillende typen proxy's en manieren om proxy te configureren. In deze handleiding kiezen we voor **Wi-Fi-proxy, instellen via PAC-URL** en geïmplementeerd via MDM . Dit heeft de voordelen van automatisch worden geïmplementeerd via MDM, de mogelijkheid om het PAC-bestand bij te werken in plaats van een server:poortconfiguratie te gebruiken en ten slotte Wi-Fi-proxy te gebruiken om de proxy zo te configureren dat deze alleen van toepassing is op één Wi-Fi-verbinding, zodat de apparaten nog steeds kunnen worden gebruikt als ze op een andere locatie zijn verbonden.

Zie Create a Windows 10 Wi-Fi profile for devices in Microsoft Intune - Azure (Een Wi-Fi maken voor apparaten in azure) voor meer informatie over proxyinstellingen [voor Microsoft Intune.](/mem/intune/configuration/wi-fi-settings-configure)

## <a name="line-of-business-apps"></a>Line-Of-Business-apps 
Hoewel verschillende apps kunnen worden geïnstalleerd via de Microsoft Store, hebt u waarschijnlijk uw eigen aangepaste app die u specifiek hebt gemaakt voor gebruik in mixed reality. Deze aangepaste apps die voor uw bedrijf in uw organisatie worden gedistribueerd, worden LOB-apps (Line-Of-Business) genoemd.
  
Er zijn meerdere manieren om toepassingen te implementeren op HoloLens 2 apparaten. Apps kunnen rechtstreeks worden geïmplementeerd via MDM, de Microsoft Store voor Bedrijven (MSfB) of sideloaden via een inrichtingspakket. In deze handleiding implementeren we apps via MDM, door gebruik te maken van de vereiste app-installatie. Hierdoor kunnen uw LOB-apps automatisch worden gedownload naar uw HoloLens apparaten zodra ze zijn ingeschreven.

Voor degenen die geen eigen LOB hebben, bieden we een voorbeeld-app om deze implementatiestroom te testen. Deze app wordt de [mrtk-voorbeelden-app](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App) en is al vooraf gebouwd en verpakt om te testen op het testen van het concept.

Meer informatie over app-implementatie vindt u in [App Management: Overzicht.](/hololens/app-deploy-overview)

> [!NOTE]
> HoloLens 2 ondersteunt alleen het uitvoeren van UWP ARM64-apps.

## <a name="guides-playbook"></a>Playbook voor handleidingen
Gidsen maken gebruik van een Microsoft Dataverse-omgeving als gegevensstore voor uw gidsen-apps. Het is belangrijk om een beter beeld te krijgen van de manier waarop uw Dataverse-omgeving communiceert met uw gidsen-apps en uw tenant. In deze handleiding gaan we niet in op het beheren van uw gegevensverse, maar raadpleeg De basisconcepten voor het implementeren van [Dynamics 365 Guides - Dynamics 365 Mixed Reality](/dynamics365/mixed-reality/guides/admin-deployment-playbook).

## <a name="next-step"></a>Volgende stap 
> [!div class="nextstepaction"]
> [Zakelijke verbonden implementatie - Configureren](hololens2-corp-connected-configure.md)