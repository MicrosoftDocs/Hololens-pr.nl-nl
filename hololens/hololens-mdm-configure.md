---
title: De microsoft-Endpoint Manager Intune gebruiken voor het beheren van HoloLens apparaten
description: Meer informatie over het gebruik van MDM voor het configureren van CSP, beleid en het op schaal HoloLens mixed reality beheren van apparaten met Behulp van Intune.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/9/2020
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 5485a4b2558a11a6c0545ec8b3405c120cff287c
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427972"
---
# <a name="using-microsofts-endpoint-manager-intune-to-manage-hololens-devices"></a>De microsoft-Endpoint Manager Intune gebruiken voor het beheren van HoloLens apparaten

Er zijn talloze verschillende instellingen die u kunt beheren via MDM. Het gebruik van Intune-apparaten kan worden gegroepeerd en configuraties kunnen worden geïmplementeerd voor deze groepen gebruikers of apparaten. Apps kunnen ook worden geïmplementeerd en beheerd, apparaten instellen om verbinding te maken met uw netwerk, en updates configureren om te worden uitgevoerd op het gewenste moment en op de benodigde updatering. 

## <a name="how-to-manage-via-intune"></a>Beheren via Intune

### <a name="device-categories-and-groups"></a>Apparaatcategorieën en -groepen
Met Intune kunt u apparaatcategorieën maken om apparaten automatisch toe te voegen aan groepen op basis van categorieën die u maakt, zoals Engineering, Medische afdeling, Ontwikkelaars, en meer. Het idee is om het beheer van uw apparaten met Windows Holographic for Business te vereenvoudigen.
Meer informatie: [Apparaten categoriseren in groepen](/mem/intune/enrollment/device-group-mapping)

### <a name="device-configuration-profiles"></a>Apparaatconfiguratieprofielen
Intune omvat instellingen en functies die u op verschillende apparaten binnen uw organisatie kunt in- of uitschakelen. Deze instellingen en functies worden beheerd met behulp van profielen. U kunt bijvoorbeeld een profiel maken waarmee Cortana wordt ingeschakeld, of een profiel dat Microsoft Defender Smart Screen gebruikt op uw apparaten met Windows Holographic for Business.
U kunt OMA-URI in uw profielen gebruiken om een aantal instellingen aan te passen, apparaatbeperkingen in te stellen en een virtueel particulier netwerk (VPN) en Wi-Fi te configureren.
[Ga aan de slag met configuratieprofielen](/mem/intune/configuration/device-profiles)en [profieloverzicht.](/mem/intune/configuration/device-profile-create)

## <a name="examples-of-what-can-be-managed-and-configured"></a>Voorbeelden van wat kan worden beheerd en geconfigureerd

Het gebruik van MDM voor het beheren van apparaten biedt een breed scala aan items die kunnen worden geselecteerd. 

### <a name="wi-fi"></a>Wi-Fi
[Wi-Fi-instellingen](/mem/intune/configuration/wi-fi-settings-configure) wijst instellingen voor draadloze netwerken toe aan gebruikers en apparaten. Wanneer u een Wi-Fi toewijst, krijgen gebruikers toegang tot uw zakelijke Wi-Fi zonder dat ze dit zelf moeten configureren.
Meer informatie over [het configureren van uw netwerk voor HoloLens](hololens-commercial-infrastructure.md)

### <a name="certificates"></a>Certificaten
Certificaten helpen de beveiliging te verbeteren door accountverificatie, Wi-Fi, VPN-versleuteling en SSL-versleuteling van webinhoud. Hoewel beheerders certificaten op apparaten handmatig kunnen beheren via inrichtingspakketten, is het een best practice om uw MDM-systeem te gebruiken voor het beheren van deze certificaten gedurende de hele levenscyclus, van inschrijving tot verlenging en intrekking. Uw MDM-systeem kan deze certificaten automatisch implementeren in de certificaatopslag van de apparaten nadat u het apparaat hebt ingeschreven (zolang het MDM-systeem ondersteuning biedt voor Simple Certificate Enrollment Protocol (SCEP) of Public Key Cryptography Standards #12 (PKCS #12)). MDM kan ook geregistreerde clientcertificaten opvragen en verwijderen of een nieuwe inschrijvingsaanvraag activeren voordat het huidige certificaat is verlopen. 

### <a name="proxy"></a>Proxy
De meeste intranetnetwerken van het bedrijf maken gebruik van een proxy voor het beheren van intern verkeer. Met HoloLens 2 kunt u een proxyserver configureren voor ethernet- en Wi-Fi verbindingen. Deze instellingen zijn niet van toepassing op VPN-verbindingen. Zie NetworkProxy CSP Windows 10 meer informatie over [proxy-instellingen voor Windows 10.](/windows/client-management/mdm/networkproxy-csp)

### <a name="vpn"></a>VPN
Organisaties gebruiken vaak een VPN om de toegang tot apps en resources op het intranet van hun bedrijf te beheren. HoloLens 2 biedt ondersteuning voor SSL VPN-verbindingen, waarvoor een downloadbare invoegvoeg-app van de Microsoft Store is vereist en die specifiek zijn voor de VPN-leverancier van uw keuze. 
- Lees meer over [VPN op HoloLens](hololens-network.md#vpn).
- Zie de [VPNv2 CSP](/windows/client-management/mdm/vpnv2-csp)voor meer informatie over VPN-profielen.

### <a name="deploy-and-manage-apps"></a>Apps implementeren en beheren
Met Intune kunt u apps toevoegen aan uw apparaten met Windows Holographic for Business. Met een MDM-oplossing kunnen IT-besluitvormers en -beheerders privé hun in-house line-of-business-apps automatisch installeren (pushen) of apps aanschaffen via de Store voor een groep gebruikers. Apps kunnen op verschillende manieren worden geïmplementeerd. Voorbeelden hiervan zijn:
-   [Intune en Bedrijfsportal]( app-deploy-intune.md)
-   [Microsoft Store voor Bedrijven]( app-deploy-store-business.md)

Meer informatie over app-beheer via Intune.
-   [Apps toevoegen aan Intune](/mem/intune/apps/apps-add)
-   [Microsoft Store-apps toevoegen](/mem/intune/apps/store-apps-windows)
-   [Apps toevoegen die u maakt](/mem/intune/apps/lob-apps-windows)
- [Apps aan groepen toewijzen](/mem/intune/apps/apps-deploy)

### <a name="software-updates"></a>Software-updates
Intune heeft de functie update-ringen voor Windows 10-apparaten. Deze update-ringen bevatten een groep instellingen waarmee u bepaalt hoe updates worden geïnstalleerd. U kunt bijvoorbeeld een onderhoudsvenster maken om updates te installeren of instellen dat opnieuw moet worden opgestart nadat updates zijn geïnstalleerd. De update-ring kan worden toegepast op meerdere apparaten met Windows Holographic for Business.
Meer informatie over het beheren [van HoloLens en](hololens-updates.md) het beheren van [software-updates via Intune.](/mem/intune/protect/windows-update-for-business-configure)

### <a name="configure-kiosk-mode"></a>Kioskmodus configureren
Met behulp van de gedeelde of gastfuncties van de pc die beschikbaar zijn in Intune kunt u Windows Holographic for Business-apparaten in de kioskmodus uitvoeren. Deze apparaten kunnen één app (één app in de kioskmodus) of meerdere apps uitvoeren (meerdere apps in de kioskmodus). Kioskmodus is een gebruikersinterface waarmee u kunt bepalen tot welke identiteiten apps standaard toegang hebben.
Meer informatie over [het instellen HoloLens als kiosk]( hololens-kiosk.md)

