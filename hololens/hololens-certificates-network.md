---
title: Certificaten en netwerkprofielen voorbereiden voor HoloLens 2
description: Meer informatie over het configureren, gebruiken, implementeren en oplossen van problemen met certificaten voor HoloLens 2 mixed reality netwerkapparaten.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: aboeger
ms.topic: article
ms.localizationpriority: high
ms.date: 9/15/2020
ms.reviewer: v-evmill
audience: ITPro
manager: sekerawa
appliesto:
- HoloLens 2
ms.openlocfilehash: cf9e14ffbda01bb1fd9e788385f7b85884d1dc8c
ms.sourcegitcommit: 73a1555fb8b84f3d20c480282c648d8d800a6c98
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/26/2021
ms.locfileid: "130351614"
---
# <a name="prepare-certificates-and-network-profiles-for-hololens-2"></a>Certificaten en netwerkprofielen voorbereiden voor HoloLens 2

Verificatie op basis van certificaten is een algemene vereiste voor klanten die HoloLens 2. Mogelijk hebt u certificaten nodig voor toegang tot Wi-Fi, om verbinding te maken met VPN-oplossingen of om toegang te krijgen tot interne resources in uw organisatie.

Omdat HoloLens 2-apparaten doorgaans worden samengevoegd met Azure Active Directory (Azure AD) en worden beheerd door Intune of een andere MDM-provider, moet u dergelijke certificaten implementeren met behulp van een Simple Certificate Enrollment Protocol(SCEP) of PKCS-certificaatinfrastructuur (Public Key Cryptography Standard) die is geïntegreerd met uw MDM-oplossing. 

>[!NOTE]
> Als u geen MDM-provider hebt, kunt u nog steeds certificaten implementeren via een inrichtingspakket [in](hololens-provisioning.md#create-the-provisioning-package) [Windows Configuration Designer of](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?rtc=1&activetab=pivot:regionofsystemrequirementstab) via Certificate [Manager](certificate-manager.md) door naar Instellingen > Update & Security > Certificate Manager te **gaan.**

## <a name="certificate-requirements"></a>Certificaatvereisten
Basiscertificaten zijn vereist voor het implementeren van certificaten via een SCEP- of PKCS-infrastructuur. Voor andere toepassingen en services in uw organisatie moeten mogelijk ook basiscertificaten op uw HoloLens 2 geïmplementeerd. 

## <a name="wi-fi-connectivity-requirements"></a>Wi-Fi connectiviteitsvereisten
Als u wilt toestaan dat een apparaat automatisch wordt voorzien van de vereiste Wi-Fi-configuratie voor uw bedrijfsnetwerk, hebt u een Wi-Fi configuratieprofiel nodig. U kunt Intune of een andere MDM-provider configureren om deze profielen op uw apparaten te implementeren. Als uw netwerkbeveiliging vereist dat apparaten deel uitmaken van het lokale domein, moet u mogelijk ook uw Wi-Fi-netwerkinfrastructuur evalueren om ervoor te zorgen dat deze compatibel is met HoloLens 2-apparaten (HoloLens 2-apparaten zijn alleen lid van Azure AD).

## <a name="deploy-certificate-infrastructure"></a>Certificaatinfrastructuur implementeren
Als er nog geen SCEP- of PKCS-infrastructuur bestaat, moet u er een voorbereiden. Ter ondersteuning van het gebruik van SCEP- of PKCS-certificaten voor verificatie vereist Intune het gebruik van een [certificaatconnector.](/mem/intune/protect/certificate-connectors)

> [!NOTE]
> Wanneer u SCEP gebruikt met een Microsoft-CA, moet u ook de Registratieservice voor netwerkapparaten [(NDES) configureren](/mem/intune/protect/certificates-scep-configure#set-up-ndes)

Zie Een certificaatprofiel configureren [voor uw apparaten in Microsoft Intune.](/intune/certificates-configure)

## <a name="deploy-certificates-and-wi-fivpn-profile"></a>Certificaten en Wi-Fi-/VPN-profiel implementeren
Volg deze stappen om certificaten en profielen te implementeren:

1.  Maak een profiel voor elk van de basiscertificaten en tussenliggende certificaten (zie [Vertrouwde certificaatprofielen maken](/intune/protect/certificates-configure#create-trusted-certificate-profiles).) Elk van deze profielen moet een beschrijving hebben met een vervaldatum in DD/MM/YYYY-indeling. **Certificaatprofielen zonder een vervaldatum worden niet geïmplementeerd.**

2.  Maak een profiel voor elke SCEP- of PKCS-certificaten (zie Een SCEP-certificaatprofiel maken of Een [PKCS-certificaatprofiel](/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)maken) Elk van deze profielen moet een beschrijving hebben met een vervaldatum in DD/MM/YYYY-indeling. **Certificaatprofielen zonder een vervaldatum worden niet geïmplementeerd.**

    > [!NOTE]
    > Omdat de HoloLens 2 wordt beschouwd als een gedeeld apparaat, meerdere gebruikers per apparaat, wordt het aanbevolen om waar mogelijk apparaatcertificaten te implementeren in plaats van gebruikerscertificaten voor Wi-Fi verificatie

3.  Maak een profiel voor elk bedrijfsnetwerk Wi-Fi netwerk (zie [Wi-Fi-instellingen voor Windows 10 en latere apparaten).](/intune/wi-fi-settings-windows) 

    > [!NOTE]
    > Het wordt aanbevolen om het Wi-Fi [waar](/mem/intune/configuration/device-profile-assign) mogelijk toe te Wi-Fi aan Apparaatgroepen in plaats van Gebruikersgroepen. 

    > [!TIP]
    > U kunt ook een werkprofiel Wi-Fi exporteren vanaf een Windows 10 pc in uw bedrijfsnetwerk. Met deze export wordt een XML-bestand met alle huidige instellingen gemaakt. Importeer dit bestand vervolgens in Intune en gebruik het als het Wi-Fi profiel voor uw HoloLens 2 apparaten. Zie [Export and import Wi-Fi settings for Windows devices (Instellingen](/mem/intune/configuration/wi-fi-settings-import-windows-8-1) voor Windows exporteren en importeren).

4.  Maak een profiel voor elke zakelijke VPN (zie instellingen voor Windows 10 en Windows Holographic-apparaat om VPN-verbindingen toe te voegen met [Behulp van Intune).](/intune/vpn-settings-windows-10)

## <a name="troubleshooting"></a>Problemen oplossen

### <a name="issue---unable-to-connect-with-network-using-certificate-based-authentication"></a>Probleem: kan geen verbinding maken met het netwerk met behulp van verificatie op basis van certificaten ###

**Symptomen**

Het apparaat kan geen netwerkverbinding tot stand brengen met verificatie op basis van certificaten.

**Stappen voor probleemoplossing**

1. Als u wilt valideren dat een certificaat correct is geïmplementeerd, gebruikt u [Certificaatbeheer](certificate-manager.md) op het apparaat om te controleren of uw certificaat aanwezig is.  

    >[!WARNING]
    > Hoewel u door MDM geïmplementeerde certificaten kunt weergeven in Certificate Manager, kunt u ze niet verwijderen in Certificate Manager. U moet ze verwijderen via MDM.

2. Alleen voor Intune geldt dat als Simple Certificate Enrollment Protocol (SCEP) wordt gebruikt voor het implementeren van certificaten, ervoor zorgen dat de URL van de Registratieservice voor netwerkapparaten-server (NDES) bereikbaar is vanaf het apparaat. [Raadpleeg SCEP-certificaten in Intune](/mem/intune/protect/certificates-profile-scep) voor informatie over de installatie. Als CNAME wordt gebruikt in plaats van een volledig gekwalificeerd domein voor de NDES-server, zorgt u ervoor dat deze correct wordt opgelost door die URL in een webbrowser op het apparaat te typen.
