---
title: HoloLens instellen in een commerciële omgeving
description: Meer informatie over het implementeren en beheren van HoloLens in bedrijfsomgevingen, waaronder infrastructuur, Azure Active Directory en Mobile Device Management.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: scooley
ms.author: scooley
ms.reviewer: aboeger
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/04/2020
appliesto:
- HoloLens 2
ms.openlocfilehash: e6aebfca076294de34068cd075d954220d7f4686
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/25/2021
ms.locfileid: "111377876"
---
# <a name="hololens-2-enterprise-deployment-and-management"></a>HoloLens 2 enterprise-implementatie en -beheer

Dit overzicht is bedoeld om IT-professionals inzicht te geven in overwegingen voor het implementeren en beheren Microsoft HoloLens 2 apparaten binnen de onderneming.

HoloLens 2 wordt uitgevoerd op Windows 10 Holographic waarmee organisaties robuuste, flexibele, ingebouwde technologieën voor het beheer van mobiele apparaten en apps kunnen gebruiken. Windows 10 Holographic biedt ondersteuning voor end-to-end levenscyclusbeheer van apparaten, om bedrijven controle te geven over hun apparaten, gegevens en apps. De HoloLens 2 kunnen eenvoudig worden opgenomen in standaard levenscyclusprocedures, van apparaatinschrijving, configuratie en toepassingsbeheer tot onderhoud en pensioen met behulp van een uitgebreide oplossing voor het beheer van mobiele apparaten.

## <a name="prepare"></a>Voorbereiden

Terwijl u de implementatie van HoloLens 2 in uw bedrijfsomgeving voorbereidt, zijn er verschillende overwegingen die moeten worden gecontroleerd en begrepen wanneer u begint met het plannen van schaalimplementaties van HoloLens 2.

### <a name="infrastructure-essentials"></a>Infrastructure Essentials

Voor HoloLens 2 in een bedrijfsimplementatiescenario zijn er bepaalde essentiële infrastructuurservices vereist voor de ondersteuning van de volledige set mogelijkheden. HoloLens 2 is gebouwd met [Modern Mobile Device Management](https://www.microsoft.com/itshowcase/managing-windows-10-devices-with-microsoft-intune) in gedachten voor implementatie en beheer. Met Azure AD Join + MDM als de belangrijkste manier om dat te bereiken in een steeds groter wordend mobiel personeel. De onderstaande onderwerpen bieden een kort overzicht van elk infrastructuuronderdeel dat moet worden overwogen in uw implementatieplanning voor HoloLens 2.

### <a name="azure-active-directory"></a>Azure Active Directory
Azure AD is een cloudgebaseerde adreslijstservice die identiteits- en toegangsbeheer biedt. U kunt deze integreren met bestaande on-premises directories om een hybride identiteitsoplossing te maken. Organisaties die gebruikmaken van Microsoft Office 365 of Intune maken al gebruik van Azure AD, dat drie edities heeft: Free, Premium P1 en Premium P2 (zie [Azure Active Directory editions).](https://azure.microsoft.com/documentation/articles/active-directory-editions/) Alle edities ondersteunen Azure AD-apparaatregistratie, maar Premium P1 is vereist om automatische inschrijving van MDM in te kunnenschakelen. HoloLens 2 vereist Azure Active Directory Join om de meeste functies en functionaliteit op ondernemingsniveau mogelijk te maken.

> [!NOTE]
> On-premises Active Directory Join wordt niet ondersteund op HoloLens 2.

### <a name="mobile-device-management"></a>Beheer van mobiele apparaten
HoloLens 2 is speciaal ontworpen om te worden beheerd door MDM-systemen (Mobile Device Management) in een bedrijfsomgeving. Microsoft [Intune,](https://www.microsoft.com/microsoft-365/enterprise-mobility-security/microsoft-intune)onderdeel van de Enterprise Mobility + Security, is een cloud-gebaseerd MDM-systeem dat apparaten in de onderneming beheert. Net als Office 365 maakt Intune gebruik van Azure AD voor identiteitsbeheer, zodat werknemers dezelfde referenties gebruiken om apparaten in te schrijven bij Intune die ze gebruiken om zich aan te melden bij Office 365. Meerdere MDM-systemen ondersteunen Windows 10 en bieden de meeste ondersteuning voor implementatiescenario's voor persoonlijke en zakelijke apparaten. MDM-systemen kunnen ook toepassingsimplementaties en updates voor de HoloLens 2 beheren. Andere MDM-providers die ondersteuning HoloLens 2 zijn onder andere: AirWatch, MobileIron en andere. Alle MDM-systeemleveranciers hebben gelijke toegang tot Windows 10 CSP's (Device Management Configuration Service Providers), waardoor IT-organisaties de vrijheid hebben om te selecteren welk systeem het beste past bij hun beheervereisten, of dit nu Microsoft Intune of een MDM-product van derden is.

> [!NOTE]
> Traditionele on-premises pc-beheersystemen zoals System Center Configuration Manager worden niet ondersteund op HoloLens 2.

### <a name="windows-update-for-business"></a>Windows Update voor Bedrijven
Microsoft heeft Windows Update voor Bedrijven ontworpen om IT-beheerders aanvullende Windows Update-gerichte beheermogelijkheden te bieden, zoals de mogelijkheid om updates te implementeren op groepen apparaten en om onderhoudsvensters te definiëren voor het installeren van updates. Zie de [documentatie voor HoloLens-updates](https://docs.microsoft.com/hololens/hololens-updates) voor meer informatie over het beheren HoloLens 2 updates.

### <a name="certificates"></a>Certificaten
HoloLens 2 ondersteunt de implementatie van certificaten via MDM als uw omgeving certificaten voor Corp Wi-Fi netwerkverificatie of toegang tot andere bronnen vereist. Sommige MDM-infrastructuurconfiguraties zijn mogelijk vereist om certificaatimplementaties in te HoloLens 2. Lees meer over het [voorbereiden van certificaten en netwerkprofielen voor HoloLens 2.](https://docs.microsoft.com/hololens/hololens-certificates-network) Als u Intune gebruikt, bekijkt u de details van de [certificeringsconfiguratie.](https://docs.microsoft.com/mem/intune/protect/certificates-configure)

## <a name="configure"></a>Configureren

MDM-beheerders kunnen beleidsinstellingen definiëren en implementeren op elk bedrijfsapparaat dat is ingeschreven in een MDM-systeem. Welke configuratie-instellingen u gebruikt, is afhankelijk van het implementatiescenario. In Windows 10 CSP's (Configuration Service Providers) een interface voor het lezen, instellen, wijzigen of verwijderen van configuratie-instellingen op het apparaat. Deze instellingen worden aan registersleutels of bestanden toe te passen. Zie de volledige lijst met CSP'Windows 10 ondersteund [in HoloLens-apparaten](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)voor meer informatie over CSP's voor apparaatbeheer voor HoloLens 2.

HoloLens 2 ondersteunt ook het instellen van een beperkte set CSP-configuraties via aangepaste inrichtingspakketten. Inrichtingspakketten worden doorgaans gebruikt voor niet door MDM beheerde apparaten en moeten handmatig op elk apparaat worden toegepast. Zie de [holoLens-inrichtingsdocumentatie](https://docs.microsoft.com/hololens/hololens-provisioning) voor meer informatie over het bouwen van aangepaste inrichtingspakketten.

> [!NOTE]
> HoloLens 2 biedt [Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot)voor een eenvoudig en eenvoudig proces voor het beheren van Windows 10 bedrijfsapparaatconfiguraties.

### <a name="identity-management"></a>Identiteitsbeheer

Werknemers kunnen slechts één account gebruiken om een apparaat te initialiseren, zodat&#39;belangrijk is dat uw organisatie bepaalt welk account het eerst wordt ingeschakeld. Het gekozen account bepaalt wie het apparaat beheert en beïnvloedt uw beheermogelijkheden. HoloLens 2 ondersteunt drie accounttypen: lokaal gebruikersaccount, persoonlijk Microsoft-account en Azure Active Directory accounts. Het wordt ten zeerste aanbevolen om Azure Active Directory te gebruiken voor uw oplossing voor identiteitsbeheer van uw bedrijf, omdat deze de volledige mogelijkheden op uw HoloLens 2 mogelijk maakt. Bekijk [HoloLens-identiteit voor](https://docs.microsoft.com/hololens/hololens-identity) meer informatie over identiteiten voor HoloLens 2.

### <a name="network-and-connectivity"></a>Netwerk en connectiviteit

Aangezien HoloLens 2 een eerste cloudapparaat is, is netwerktoegang tot onlinebronnen vereist om volledige functionaliteit en mogelijkheden beschikbaar te stellen. Als u HoloLens 2 implementeert met verbinding met uw bedrijfs-intranetnetwerk, moet u mogelijk uw proxy-/firewallregels bijwerken om toegang tot HoloLens 2 cloudservices toe te staan. Bekijk voor meer informatie de lijst met algemene eindpunten voor het [HoloLens 2 besturingssysteem](https://docs.microsoft.com/hololens/hololens-offline). Toegang tot extra eindpunten kan vereist zijn om toepassingen of andere cloudservices op een HoloLens 2 uitvoeren.

Enkele veelvoorkomende HoloLens 2 die extra eindpunttoegang vereisen, zijn als volgt:

- [Intune](https://docs.microsoft.com/mem/intune/fundamentals/intune-endpoints)
- [D365-handleidingen](https://support.microsoft.com/en-us/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami)
- [D365 Remote Assist (O365 Teams-infrastructuur)](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

### <a name="certificate-deployment"></a>Certificaatimplementatie

Als certificaten vereist zijn voor toegang tot bedrijfsnetwerken Wi-Fi andere services binnen uw organisatie, ondersteunt HoloLens 2 implementatie van gebruikers- en apparaatcertificaten via MDM. Opmerking: voor uw MDM-oplossing is mogelijk aanvullende infrastructuurconfiguratie vereist om certificaten te implementeren op Windows 10 apparaten.

### <a name="security-review"></a>Beveiligingsbeoordeling

De meeste IT-afdelingen voor ondernemingen vereisen evaluatie en beoordeling van nieuwe apparaten die worden geïmplementeerd in een bedrijfsnetwerk. Als uw organisatie een beveiligingsbeoordeling van uw HoloLens 2, vindt u meer informatie om te helpen bij het [verkrijgen van beveiligingsgoedkeuringen.](https://docs.microsoft.com/hololens/security-overview)

### <a name="common-hololens-2-device-settings"></a>Algemene HoloLens 2 apparaatinstellingen

Wanneer u HoloLens 2 in een bedrijfsomgeving implementeert, zijn er een aantal algemene apparaatconfiguraties die in aanmerking kunnen worden genomen bij het plannen van uw implementatie van HoloLens 2. In deze lijst worden configuraties en instellingen belicht die heel gangbaar zijn en die niet bestaan uit een volledige lijst met beschikbare opties:

| Apparaatinstelling | Korte beschrijving.                                                                              |
|----------------|-------------------------------------------------------------------------------------------------|
| [Hardwarebeperkingen](hololens-requirements.md#hardware-restrictions)               | Hardwarebeperkingen verminderen de connectiviteit en helpen bij gegevensbeveiliging.                        |
| [Wi-Fi-profielen](hololens-requirements.md#wi-fi-profiles)               | Configureer Wi-Fi profielen zonder tussenkomst of interactie van de gebruiker.                              |
| [Certificaten](hololens-requirements.md#certificates-1)               | Geef account- en/of Wi-Fi verificatie, VPN-versleuteling en SSL-versleuteling van webinhoud op. |
| [Proxy](hololens-requirements.md#proxy)              | Intern verkeer beheren.                                                                        |
|  [VPN](hololens-requirements.md#vpn)              | Toegang tot apps en resources beheren op het intranet van hun bedrijf.                               |
| [Kioskmodus](hololens-requirements.md#kiosk-mode) | Beperkt de toepassingen die aan gebruikers worden aangeboden via de gebruikersinterface. |

#### <a name="hardware-restrictions"></a>Hardwarebeperkingen

HoloLens 2 maakt gebruik van geavanceerde technologie die populaire hardwarefuncties zoals camera's, microfoons, sprekers, USB-interfaces, Bluetooth-interfaces en Wi-Fi omvat. U kunt hardwarebeperkingen gebruiken om de beschikbaarheid van deze functies te bepalen.

Hieronder vindt u de meest gebruikte MDM-instellingen die HoloLens 2 voor het configureren van hardwarebeperkingen. Sommige van deze hardwarebeperkingen bieden connectiviteit en helpen bij gegevensbeveiliging.

- [**Wi-Fi toestaan:**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) Of gebruikers de Wi-Fi op hun apparaten kunnen inschakelen en gebruiken
- [**USB-verbinding toestaan:**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) Of de USB-verbinding is ingeschakeld (heeft&#39;invloed op USB-laden)
- [**Bluetooth toestaan:**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) Of gebruikers het Bluetooth-radio kunnen inschakelen en gebruiken op hun apparaten

Meer informatie over andere [algemene apparaatbeperkingen.](https://docs.microsoft.com/hololens/hololens-common-device-restrictions)

#### <a name="wi-fi-profiles"></a>Wi-Fi-profielen

De meeste bedrijfsnetwerken Wi-Fi vereisen certificaten en andere complexe informatie om gebruikerstoegang te beperken en te beveiligen. Deze geavanceerde Wi-Fi is moeilijk te configureren voor gewone gebruikers, maar MDM-systemen kunnen deze profielen volledig Wi-Fi zonder tussenkomst van de gebruiker. U kunt meerdere Wi-Fi maken in uw MDM-systeem.

Zie Wi-Fi-instellingen voor enterpriseWi-Fi profiel voor Windows 10 meer informatie over [de instellingen voor enterprise-profielen.](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile)

#### <a name="certificates"></a>Certificaten

Certificaten helpen de beveiliging te verbeteren door accountverificatie, Wi-Fi, VPN-versleuteling en SSL-versleuteling van webinhoud. Hoewel beheerders certificaten op apparaten handmatig kunnen beheren via inrichtingspakketten,&#39;een best practice om uw MDM-systeem te gebruiken voor het beheren van deze certificaten gedurende de hele levenscyclus, van inschrijving tot verlenging en intrekking. Uw MDM-systeem kan deze certificaten automatisch implementeren op de apparaten&#39;-certificaatopslag nadat u het apparaat hebt ingeschreven (zolang het MDM-systeem ondersteuning biedt voor de Simple Certificate Enrollment Protocol (SCEP) of Public Key Cryptography Standards #12 (PKCS #12)). MDM kan ook geregistreerde clientcertificaten opvragen en verwijderen of een nieuwe inschrijvingsaanvraag activeren voordat het huidige certificaat is verlopen.

Lees meer over het voorbereiden [van certificaten en netwerkprofielen voor HoloLens 2.](https://docs.microsoft.com/hololens/hololens-certificates-network)

#### <a name="proxy"></a>Proxy

De meeste bedrijfs intranetnetwerken maken gebruik van een proxy voor het beheren van intern verkeer. Met HoloLens 2 kunt u een proxyserver configureren voor ethernet- en Wi-Fi verbindingen. Deze instellingen zijn niet van toepassing op VPN-verbindingen.

Zie NetworkProxy CSP Windows 10 meer informatie over [proxy-instellingen voor Windows 10.](https://docs.microsoft.com/windows/client-management/mdm/networkproxy-csp)

#### <a name="vpn"></a>VPN

Organisaties gebruiken vaak een VPN om de toegang tot apps en resources op hun bedrijfsapps&#39;intranet te beheren. HoloLens 2 biedt ondersteuning voor SSL VPN-verbindingen, waarvoor een downloadbare invoegvoeg-app van de Microsoft Store vereist is en die specifiek is voor de VPN-leverancier van uw keuze.

Zie de [VPNv2 CSP](https://msdn.microsoft.com/library/windows/hardware/dn914776(v=vs.85).aspx) voor meer informatie over VPN-profielen

#### <a name="kiosk-mode"></a>Kioskmodus

U kunt een HoloLens 2 om te functioneren als een apparaat voor vaste doeleinden, ook wel een kiosk genoemd, door het apparaat zo te configureren dat het in de kioskmodus wordt uitgevoerd. De kioskmodus beperkt de toepassingen (of gebruikers) die beschikbaar zijn op het apparaat. De kioskmodus is een handige functie die u kunt gebruiken om een HoloLens 2-apparaat te besteden aan zakelijke apps of om het HoloLens 2-apparaat te gebruiken in een app-demo.

Zie [HoloLens](https://docs.microsoft.com/hololens/hololens-kiosk) instellen als kiosk voor meer HoloLens 2 over het configureren van een HoloLens 2 in de kioskmodus

## <a name="deploy"></a>Implementeren

### <a name="mdm-device-enrollment"></a>MDM-apparaatinschrijving

Voor bedrijfsimplementaties wordt [](https://docs.microsoft.com/hololens/hololens-enroll-mdm) aangeraden om apparaten alleen bij MDM in te schrijven als bedrijfsapparaten met Azure AD Join en automatische MDM-inschrijving (Azure AD+MDM). Hiervoor is Azure AD Premium automatische inschrijving bij verschillende MDM-providers, waaronder Intune, vereist.

Meer informatie over de zelf-implementerende inschrijvingsmethode [Autopilot](https://docs.microsoft.com/hololens/hololens2-autopilot).

### <a name="application-deployment"></a>Toepassingsimplementatie

Gebruikersproductiviteit op mobiele apparaten wordt vaak aangestuurd door apps.

Windows 10 kunt u apps ontwikkelen die naadloos werken op meerdere apparaten met behulp van de Universeel Windows-platform (UWP) voor Windows-apps.

Er zijn meerdere manieren om toepassingen te implementeren op HoloLens 2 apparaten. Apps kunnen rechtstreeks worden geïmplementeerd via MDM, de Microsoft Store voor Bedrijven of sideloaden via een inrichtingspakket. Raadpleeg de documentatie [voor app-implementatie](https://docs.microsoft.com/hololens/app-deploy-overview) voor meer informatie.

> [!NOTE]
> HoloLens 2 ondersteunt alleen het uitvoeren van UWP ARM64-apps.

## <a name="maintain"></a>Onderhouden

In IT-bedrijfsomgevingen moet de behoefte aan beveiliging en kostenbeheer worden afgewogen tegen de wens om gebruikers de nieuwste technologieën te bieden. Aangezien cyberaanvallen een alledaagse gebeurtenis zijn geworden, is het belangrijk om de status van uw apparaten Windows 10 onderhouden. IT moet configuratie-instellingen beheren, zodat deze niet meer voldoen aan de naleving, en afdwingen welke apparaten toegang hebben tot interne toepassingen. HoloLens 2 biedt de beheermogelijkheden voor mobiele bewerkingen die nodig zijn om ervoor te zorgen dat apparaten voldoen aan het bedrijfsbeleid.

### <a name="os-servicing-options"></a>Opties voor besturingssysteemservice

**Een gestroomlijnd updateproces**

Microsoft heeft de windows-producten engineering en de releasecyclus gestroomlijnd, zodat nieuwe functies, ervaringen en functionaliteit die door de markt worden gesereerd, sneller dan ooit tevoren kunnen worden geleverd. Microsoft is van plan om twee functie-updates per jaar te leveren (periode van 12 maanden). **Met functie-updates** wordt een Current Branch of CB tot stand gebracht en is er een bijbehorende versie beschikbaar.

Microsoft levert en installeert updates voor beveiliging en stabiliteit ook rechtstreeks op HoloLens 2 apparaten. Deze **kwaliteitsupdates,** uitgebracht onder Microsoft-beheer via Windows Update, zijn maandelijks beschikbaar. HoloLens 2 gebruikt onderdeelupdates en kwaliteitsupdates als onderdeel van hetzelfde standaardupdateproces.

Enterprise-klanten kunnen de update-ervaring en het proces op HoloLens 2's beheren met behulp van een MDM-systeem. In de meeste gevallen geldt beleid voor het beheren van het updateproces voor zowel functie- als kwaliteitsupdates. Meer informatie over het [configureren van MDM voor HoloLens-updates.](https://docs.microsoft.com/hololens/hololens-updates)

### <a name="managing-applications"></a>Toepassingen beheren

IT-beheerders kunnen bepalen welke apps mogen worden geïnstalleerd op de HoloLens 2 en hoe ze up-to-date moeten worden gehouden.

HoloLens 2 ondersteunt [Windows Defender Application Control (WDAC),](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)waarmee beheerders lijsten met apps van de Microsoft Store. Deze mogelijkheid is ook beschikbaar voor ingebouwde apps. De mogelijkheid om apps toe te staan of te weigeren, helpt ervoor te zorgen dat mensen hun apparaten voor hun beoogde doeleinden gebruiken. Het is echter niet altijd eenvoudig om een evenwicht te vinden tussen wat werknemers nodig hebben of vragen en beveiligingsproblemen. Voor het maken van lijsten met toegestane of niet-toegestane apps moet u ook rekening houden met het veranderende app-landschap in Microsoft Store.

Zie Application [Control CSP voor meer informatie.](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp)

### <a name="retire"></a>Buiten gebruik stellen

Het verwijderen van apparaten is de laatste fase van de levenscyclus van het apparaat. Het&#39;&#39;belangrijk dat apparaten die worden vervangen door nieuwere modellen veilig worden teruggetrokken, omdat u niet wilt dat bedrijfsgegevens op verwijderde apparaten blijven staan die de vertrouwelijkheid van uw gegevens in gevaar kunnen brengen. IT heeft ook een manier nodig om gebruikers te ondersteunen die verloren of gestolen apparaten moeten wissen.

HoloLens 2 ondersteunt drie methoden om het apparaat te wissen

**MDM Factory wissen:** Hiermee stelt u de HoloLens 2 terug naar de fabrieksafbeelding via een door de beheerder geïnitieerde MDM-opdracht. Wist alle opgeslagen gegevens op het apparaat.

**Apparaat opnieuw instellen vanuit Instellingen:** Eindgebruikers kunnen het apparaat handmatig opnieuw instellen HoloLens 2 in de app Instellingen op het apparaat. Wist alle opgeslagen gegevens op het apparaat.

**Geavanceerde companion herstel (ARC):** Vanaf een pc met het ARC-hulpprogramma kan een gebruiker of beheerder een apparaat HoloLens 2 via een USB-kabel met de pc is verbonden. Wist alle opgeslagen gegevens op het apparaat.

> [!div class="nextstepaction"]
> [Algemene implementatiescenario's](common-scenarios.md)
