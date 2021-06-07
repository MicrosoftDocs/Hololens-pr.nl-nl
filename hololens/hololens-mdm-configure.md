---
title: De Microsoft-Endpoint Manager Intune gebruiken om HoloLens-apparaten te beheren
description: Meer informatie over het gebruik van MDM voor het configureren van CSP, beleid en het beheren van HoloLens mixed reality apparaten op schaal met Behulp van Intune.
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
ms.openlocfilehash: ce288afdcb112c17ffde75078d641f3637a8448c
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/19/2021
ms.locfileid: "111377884"
---
# <a name="using-microsofts-endpoint-manager-intune-to-manage-hololens-devices"></a>De Microsoft-Endpoint Manager Intune gebruiken om HoloLens-apparaten te beheren

Er zijn talloze verschillende instellingen die u via MDM kunt beheren. Het gebruik van Intune-apparaten kan worden gegroepeerd en configuraties kunnen worden geïmplementeerd voor die groepen gebruikers of apparaten. Apps kunnen ook worden geïmplementeerd en beheerd, apparaten instellen om verbinding te maken met uw netwerk, en updates configureren die moeten worden uitgevoerd op het gewenste moment en op de benodigde updatering. 

## <a name="how-to-manage-via-intune"></a>Beheren via Intune

### <a name="device-categories-and-groups"></a>Apparaatcategorieën en -groepen
Met Intune kunt u apparaatcategorieën maken om apparaten automatisch toe te voegen aan groepen op basis van categorieën die u maakt, zoals Engineering, Medische afdeling, Ontwikkelaars, en meer. Het idee is om het beheer van uw apparaten met Windows Holographic for Business te vereenvoudigen.
Meer informatie: [Apparaten categoriseren in groepen](https://docs.microsoft.com/mem/intune/enrollment/device-group-mapping)

### <a name="device-configuration-profiles"></a>Apparaatconfiguratieprofielen
Intune omvat instellingen en functies die u op verschillende apparaten binnen uw organisatie kunt in- of uitschakelen. Deze instellingen en functies worden beheerd met behulp van profielen. U kunt bijvoorbeeld een profiel maken waarmee Cortana wordt ingeschakeld, of een profiel dat Microsoft Defender Smart Screen gebruikt op uw apparaten met Windows Holographic for Business.
U kunt OMA-URI in uw profielen gebruiken om een aantal instellingen aan te passen, apparaatbeperkingen in te stellen en een virtueel particulier netwerk (VPN) en Wi-Fi te configureren.
[Ga aan de slag met configuratieprofielen](https://docs.microsoft.com/mem/intune/configuration/device-profiles)en [profieloverzicht.](https://docs.microsoft.com/mem/intune/configuration/device-profile-create)

## <a name="examples-of-what-can-be-managed-and-configured"></a>Voorbeelden van wat kan worden beheerd en geconfigureerd

Het gebruik van MDM voor het beheren van apparaten biedt een breed scala aan items die kunnen worden geselecteerd. 

### <a name="wi-fi"></a>Wi-Fi
[Wi-Fi-instellingen](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-configure) wijst instellingen voor draadloze netwerken toe aan gebruikers en apparaten. Wanneer u een Wi-Fi toewijst, krijgen gebruikers toegang tot uw Wi-Fi zonder dat ze dit zelf moeten configureren.
Meer informatie over [het configureren van uw netwerk voor HoloLens](hololens-commercial-infrastructure.md)

### <a name="certificates"></a>Certificaten
Certificaten helpen de beveiliging te verbeteren door accountverificatie, Wi-Fi, VPN-versleuteling en SSL-versleuteling van webinhoud. Hoewel beheerders certificaten op apparaten handmatig kunnen beheren via inrichtingspakketten, is het een best practice om uw MDM-systeem te gebruiken voor het beheren van deze certificaten gedurende de hele levenscyclus, van inschrijving tot verlenging en intrekking. Uw MDM-systeem kan deze certificaten automatisch implementeren in de certificaatopslag van de apparaten nadat u het apparaat hebt ingeschreven (zolang het MDM-systeem ondersteuning biedt voor de Simple Certificate Enrollment Protocol (SCEP) of Public Key Cryptography Standards #12 (PKCS #12)). MDM kan ook geregistreerde clientcertificaten opvragen en verwijderen of een nieuwe inschrijvingsaanvraag activeren voordat het huidige certificaat is verlopen. 

### <a name="proxy"></a>Proxy
De meeste bedrijfs intranetnetwerken maken gebruik van een proxy voor het beheren van intern verkeer. Met HoloLens 2 kunt u een proxyserver configureren voor ethernet- en Wi-Fi verbindingen. Deze instellingen zijn niet van toepassing op VPN-verbindingen. Zie NetworkProxy CSP Windows 10 meer informatie over [proxy-instellingen voor Windows 10.](https://docs.microsoft.com/windows/client-management/mdm/networkproxy-csp)

### <a name="vpn"></a>VPN
Organisaties gebruiken vaak een VPN om de toegang tot apps en resources op het intranet van hun bedrijf te beheren. HoloLens 2 biedt ondersteuning voor SSL VPN-verbindingen, waarvoor een downloadbare invoegvoeg-app van de Microsoft Store vereist is en die specifiek is voor de VPN-leverancier van uw keuze. 
- Lees meer over [VPN op HoloLens](hololens-network.md#vpn).
- Zie de [VPNv2 CSP](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp)voor meer informatie over VPN-profielen.

### <a name="deploy-and-manage-apps"></a>Apps implementeren en beheren
Met Intune kunt u apps toevoegen aan uw apparaten met Windows Holographic for Business. Met een MDM-oplossing kunnen IT-besluitvormers en -beheerders hun in-house line-of-business-apps privé installeren (pushen) of apps aanschaffen via de Store voor een groep gebruikers. Apps kunnen op verschillende manieren worden geïmplementeerd. Voorbeelden hiervan zijn:
-   [Intune en Bedrijfsportal]( app-deploy-intune.md)
-   [Microsoft Store voor Bedrijven]( app-deploy-store-business.md)

Meer informatie over app-beheer via Intune.
-   [Apps toevoegen aan Intune](https://docs.microsoft.com/mem/intune/apps/apps-add)
-   [Microsoft Store-apps toevoegen](https://docs.microsoft.com/mem/intune/apps/store-apps-windows)
-   [Apps toevoegen die u maakt](https://docs.microsoft.com/mem/intune/apps/lob-apps-windows)
- [Apps aan groepen toewijzen](https://docs.microsoft.com/mem/intune/apps/apps-deploy)

### <a name="software-updates"></a>Software-updates
Intune heeft de functie update-ringen voor Windows 10-apparaten. Deze update-ringen bevatten een groep instellingen waarmee u bepaalt hoe updates worden geïnstalleerd. U kunt bijvoorbeeld een onderhoudsvenster maken om updates te installeren of instellen dat opnieuw moet worden opgestart nadat updates zijn geïnstalleerd. De update-ring kan worden toegepast op meerdere apparaten met Windows Holographic for Business.
Lees meer over [HoloLens-updates beheren en](hololens-updates.md) [Software-updates beheren via Intune.](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)

### <a name="configure-kiosk-mode"></a>Kioskmodus configureren
Met behulp van de gedeelde of gastfuncties van de pc die beschikbaar zijn in Intune kunt u Windows Holographic for Business-apparaten in de kioskmodus uitvoeren. Deze apparaten kunnen één app (één app in de kioskmodus) of meerdere apps uitvoeren (meerdere apps in de kioskmodus). Kioskmodus is een gebruikersinterface waarmee u kunt bepalen welke identiteiten standaard toegang hebben tot welke apps.
Meer informatie over [het instellen van HoloLens als kiosk]( hololens-kiosk.md)

