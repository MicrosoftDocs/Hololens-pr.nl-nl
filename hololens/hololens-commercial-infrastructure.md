---
title: Infrastructuurrichtlijnen voor HoloLens
description: Meer informatie over de infrastructuurrichtlijnen voor HoloLens-apparaten, waaronder draadloze netwerkondersteuning, hulp op afstand en beheer van mobiele apparaten.
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
ms.topic: article
ms.localizationpriority: high
ms.date: 1/23/2020
ms.reviewer: ''
audience: ITPro
manager: bradke
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 4eb55bec56e53de9195ac87e0491eefd91992f3d
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379357"
---
# <a name="configure-your-network-for-hololens"></a>Uw netwerk configureren voor HoloLens

Voor dit gedeelte van het document zijn de volgende personen vereist:

1. Netwerkbeheerder met machtigingen om wijzigingen aan te brengen in de proxy/firewall
2. Azure Active Directory beheerder
3. Mobile Apparaatbeheer Admin

## <a name="infrastructure-requirements"></a>Vereisten voor de infrastructuur

HoloLens is in de kern een mobiel Windows-apparaat dat is geïntegreerd met Azure.  Het werkt het beste in commerciële omgevingen met draadloze netwerkbeschikbaarheid (Wi-Fi) en toegang tot Microsoft-services.

Essentiële cloudservices zijn onder andere:

- Azure active directory (Azure AD)
- Windows Update (WU)

Commerciële klanten hebben enterprise mobility management (EMM) of MDM-infrastructuur (Mobile Device Management) nodig om HoloLens-apparaten op schaal te beheren.  In deze handleiding [Microsoft Intune](https://www.microsoft.com/enterprise-mobility-security/microsoft-intune) voorbeeld gebruikt, maar elke provider met volledige ondersteuning voor Microsoft Policy kan HoloLens ondersteunen.  Vraag uw provider voor het beheer van mobiele apparaten of deze ondersteuning HoloLens 2.

HoloLens biedt ondersteuning voor een beperkte set niet-verbonden ervaringen in de cloud.

### <a name="wireless-network-eap-support"></a>EAP-ondersteuning voor draadloze netwerken

- PEAP-MS-CHAPv2
- PEAP-TLS
- TLS
- TTLS-CHAP
- TTLS-CHAPv2
- TTLS-MS-CHAPv2
- TTLS-PAP
- TTLS-TLS

### <a name="hololens-specific-network-requirements"></a>Specifieke netwerkvereisten voor HoloLens

Zorg ervoor dat [deze lijst met](hololens-offline.md) eindpunten is toegestaan op uw netwerkfirewall. Hierdoor kan HoloLens goed werken.

### <a name="remote-assist-specific-network-requirements"></a>Remote Assist specifieke netwerkvereisten

1. De aanbevolen bandbreedte voor optimale prestaties van Remote Assist is 1,5 Mbps. Zie de [gedetailleerde netwerkvereisten](https://docs.microsoft.com/MicrosoftTeams/prepare-network) voor meer informatie.
**(Houd er rekening mee dat als u geen netwerksnelheid van ten minste 1,5 Mbps hebt, Remote Assist nog steeds werken. Kwaliteit kan echter wel leiden tot een slechte kwaliteit).**
1. Zorg ervoor dat deze poorten en URL's zijn toegestaan op uw netwerkfirewall, zodat Microsoft Teams kan functioneren. Blijf up-to-date met [de meest recente lijst met poorten](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams).

- Meer informatie over de specifieke [netwerkvereisten voor Remote Assist.](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#network-requirements) 
- Meer informatie over het voorbereiden [van het netwerk van uw organisatie voor Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/prepare-network)

### <a name="guides-specific-network-requirements"></a>Specifieke netwerkvereisten voor gidsen

Handleidingen vereisen alleen netwerktoegang om de app te downloaden en te gebruiken.

## <a name="azure-active-directory-guidance"></a>Azure Active Directory richtlijnen

> [!NOTE]
> Deze stap is alleen nodig als uw bedrijf van plan is de HoloLens te beheren.

1. Zorg ervoor dat u een Azure AD-licentie hebt.
Please [HoloLens Licenses Requirements (Vereisten voor HoloLens-licenties)](hololens-licenses-requirements.md) voor meer informatie.

1. Als u van plan bent automatische inschrijving te gebruiken, moet u [Azure AD-inschrijving configureren.](https://docs.microsoft.com/intune/deploy-use/.set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment)

1. Zorg ervoor dat de gebruikers van uw bedrijf zich in Azure Active Directory (Azure AD).
Zie de volgende instructies [voor het](https://docs.microsoft.com/azure/active-directory/fundamentals/add-users-azure-active-directory) toevoegen van gebruikers.

1. We raden u aan dat gebruikers die vergelijkbare licenties nodig hebben, worden toegevoegd aan dezelfde groep.
    1. [Een groep maken](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    1. [Gebruikers toevoegen aan groepen](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal)

1. Zorg ervoor dat aan de gebruikers (of groep gebruikers) van uw bedrijf de benodigde licenties zijn toegewezen.
Als u licenties moet toewijzen, volgt u [deze instructies.](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups)

1. Doe deze stap alleen als van gebruikers wordt verwacht dat ze hun HoloLens/Mobile-apparaat bij u inschrijven (er zijn drie opties) Met deze stappen zorgt u ervoor dat de gebruikers van uw bedrijf (of een groep gebruikers) apparaten kunnen toevoegen.
    1. **Optie 1:** Geef alle gebruikers toestemming om apparaten toe tevoegen aan Azure AD.
**Meld u als beheerder Azure Portal aan bij de Azure Portal**  >  **Azure Active Directory**  >  **Apparaten**  >  **Apparaatinstellingen**  >
 **Stel Gebruikers mogen apparaten aan Azure AD deelnemen in op *Alle***

    1. **Optie 2:** Geselecteerde gebruikers/groepen toestemming geven om apparaten toe te sluiten bij Azure AD Meld u als beheerder aan bij de **Azure Portal** als beheerder Azure Active Directory Apparaten Apparaatinstellingen Instellen Gebruikers kunnen apparaten aan  >    >    >    >
 **Azure AD** 
 ![ deelnemen aan de geselecteerde afbeelding met de configuratie van apparaten die zijn samengevoegd met Azure AD](images/azure-ad-image.png)

    1. **Optie 3:** U kunt blokkeren dat alle gebruikers hun apparaten toevoegen aan het domein. Dit betekent dat alle apparaten handmatig moeten worden ingeschreven.

## <a name="mobile-device-manager-guidance"></a>Richtlijnen Apparaatbeheer mobiele apparaten

### <a name="ongoing-device-management"></a>Doorlopend apparaatbeheer

> [!NOTE]
> Deze stap is alleen nodig als uw bedrijf van plan is de HoloLens te beheren.

Doorlopend apparaatbeheer is afhankelijk van uw infrastructuur voor het beheer van mobiele apparaten.  De meeste hebben dezelfde algemene functionaliteit, maar de gebruikersinterface kan sterk variëren.

1. [Met CSP's (Configuration Service Providers)](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) kunt u beheerinstellingen maken en implementeren voor de apparaten in uw netwerk. Zie de [lijst met HoloLens CSP's voor](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) naslag.

1. [Nalevingsbeleid](https://docs.microsoft.com/intune/device-compliance-get-started) zijn regels en instellingen waar apparaten aan moeten voldoen om compatibel te zijn in uw bedrijfsinfrastructuur. Gebruik dit beleid met voorwaardelijke toegang om de toegang tot bedrijfsbronnen te blokkeren voor apparaten die niet compatibel zijn. U kunt bijvoorbeeld een beleid maken waarvoor Bitlocker moet zijn ingeschakeld.

1. [Nalevingsbeleid maken.](https://docs.microsoft.com/intune/protect/compliance-policy-create-windows)

1. Met voorwaardelijke toegang kunnen mobiele apparaten en mobiele toepassingen geen toegang krijgen tot bedrijfsbronnen. Twee documenten die u mogelijk nuttig vindt, zijn [Plan your CA Deployment](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) en Best [Practices](https://docs.microsoft.com/azure/active-directory/conditional-access/best-practices).

1. [In dit artikel](https://docs.microsoft.com/intune/fundamentals/windows-holographic-for-business) wordt gesproken over de beheerhulpprogramma's van Intune voor HoloLens.

1. [Een apparaatprofiel maken](https://docs.microsoft.com/intune/configuration/device-profile-create)

### <a name="manage-updates"></a>Updates beheren

Intune bevat een functie met de naam Updateringen Windows 10 apparaten, waaronder HoloLens 2 en HoloLens v1 (met Holographic for Business). Updateringen bevatten een groep instellingen die bepalen hoe en wanneer updates worden geïnstalleerd.

U kunt bijvoorbeeld een onderhoudsvenster maken om updates te installeren of instellen dat opnieuw moet worden opgestart nadat updates zijn geïnstalleerd.  U kunt er ook voor kiezen om updates voor onbepaalde tijd te onderbreken totdat u klaar bent om bij te werken.

Lees meer over [het configureren van updateringen met Intune](https://docs.microsoft.com/intune/windows-update-for-business-configure).

### <a name="application-management"></a>Toepassingsbeheer

HoloLens-toepassingen beheren via:

1. Microsoft Store  
  De Microsoft Store is de beste manier om toepassingen op HoloLens te distribueren en te gebruiken.  Er is al een geweldige set HoloLens-kerntoepassingen beschikbaar in de Store of u kunt [uw eigen publiceren.](https://docs.microsoft.com/windows/uwp/publish/)  
  Alle toepassingen in de store zijn openbaar beschikbaar voor iedereen, maar als dit niet acceptabel is, bekijkt u de Microsoft Store voor Bedrijven.  

1. [Microsoft Store voor Bedrijven](https://docs.microsoft.com/microsoft-store/)  
  Microsoft Store voor Bedrijven en Education is een aangepast winkel voor uw bedrijfsomgeving.  Hiermee kunt u de Microsoft Store ingebouwde Windows 10 en HoloLens gebruiken om apps voor uw organisatie te zoeken, verkrijgen, distribueren en beheren.  U kunt hiermee ook apps implementeren die specifiek zijn voor uw commerciële omgeving, maar niet voor de hele wereld.

1. Implementatie en beheer van toepassingen via Intune of een andere beheeroplossing voor mobiele apparaten  
  De meeste oplossingen voor het beheer van mobiele apparaten, waaronder Intune, bieden een manier om Line-Of-Business-toepassingen rechtstreeks te implementeren op een set geregistreerde apparaten.  Zie dit artikel voor de [installatie van de Intune-app.](https://docs.microsoft.com/intune/apps-deploy)

1. _niet aanbevolen_ Apparaatportal  
  Toepassingen kunnen ook rechtstreeks op HoloLens worden geïnstalleerd met behulp van de Windows Apparaatportal.  Dit wordt niet aanbevolen omdat de ontwikkelaarsmodus moet worden ingeschakeld voor het gebruik van de apparaatportal.

Lees meer over [het installeren van apps op HoloLens](https://docs.microsoft.com/hololens/hololens-install-apps).

### <a name="certificates"></a>Certificaten

U kunt certificaten distribueren via uw MDM-provider. Als uw bedrijf certificaten vereist, ondersteunt Intune PKCS, PFX en SCEP. Het is belangrijk om te begrijpen welk certificaat het juiste is voor uw bedrijf. Raadpleeg de documentatie [over certificaatconfiguraties](https://docs.microsoft.com/intune/protect/certificates-configure) om te bepalen welk certificaat het meest voor u is. Als u certificaten voor HoloLens-verificatie wilt gebruiken, is PFX of SCEP mogelijk de juiste voor u.

Zie de volgende stappen voor het gebruik van [SCEP.](https://docs.microsoft.com/intune/protect/certificates-profile-scep)

### <a name="how-to-upgrade-to-holographics-for-business-commercial-suite"></a>Upgraden naar Holographics for Business Commercial Suite

> [!NOTE]
> Windows Holographics for Business (commerciële suite) is alleen bedoeld voor apparaten van de eerste generatie van HoloLens. Het profiel wordt niet toegepast op HoloLens 2 apparaten.

U vindt een routebeschrijving voor het upgraden naar de commerciële suite in de [documentatie voor de holographic-upgrade.](https://docs.microsoft.com/intune/configuration/holographic-upgrade)

### <a name="how-to-configure-kiosk-mode-using-microsoft-intune"></a>Kioskmodus configureren met Microsoft Intune

1. Synchroniseer Microsoft Store naar Intune (zie de volgende [instructies).](https://docs.microsoft.com/intune/apps/windows-store-for-business)

1. Uw app-instellingen controleren
    1. Meld u aan bij Microsoft Store Business-account
    1. **> producten en services beheren > apps en software-> Selecteer de app die u wilt synchroniseren > Beschikbaarheid van de privéopslag > Selecteer 'Iedereen' of 'Specifieke groepen'**
        >[!NOTE]
        >Als u de gezochte app niet ziet, moet u de app 'downloaden' door in de Store te zoeken naar uw app. Klik op de balk Zoeken in de rechterbovenhoek > typ de naam van de app > klik op de app om **> 'Get' te selecteren.**
    1. Als u uw apps niet ziet in **Intune > Client Apps > Apps,** moet u uw apps mogelijk [opnieuw](https://docs.microsoft.com/intune/apps/windows-store-for-business#synchronize-apps) synchroniseren.

1. [Een apparaatprofiel maken voor de kioskmodus](https://docs.microsoft.com/intune/configuration/kiosk-settings#create-the-profile)

> [!NOTE]
> U kunt verschillende gebruikers configureren voor verschillende kioskmoduservaringen door 'Azure AD' te gebruiken als aanmeldingstype gebruiker. Deze optie is echter alleen beschikbaar in de kioskmodus voor meerdere apps. De kioskmodus voor meerdere apps werkt met slechts één app en met meerdere apps.

![Afbeelding van de configuratie van de kioskmodus in Intune](images/aad-kioskmode.png)

Raadpleeg de documentatie van uw provider voor instructies voor andere MDM-services. Raadpleeg de [HoloLens-kioskinstructies](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) als u een aangepaste instelling en een volledige XML-configuratie moet gebruiken om een kiosk in te stellen in uw MDM-service.

## <a name="certificates-and-authentication"></a>Certificaten en verificatie

Certificaten kunnen worden geïmplementeerd via uw MDM (zie Certificaten in de [sectie MDM).](hololens-commercial-infrastructure.md#mobile-device-manager-guidance) Certificaten kunnen ook worden geïmplementeerd in de HoloLens via het inrichten van pakketten. Zie [HoloLens-inrichting](hololens-provisioning.md) voor meer informatie.

### <a name="additional-intune-quick-links"></a>Aanvullende Snelkoppelingen voor Intune

1. [Profielen maken:](https://docs.microsoft.com/intune/configuration/device-profile-create) Met profielen kunt u instellingen toevoegen en configureren die naar de apparaten in uw organisatie worden pushen.

