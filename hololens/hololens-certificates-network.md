---
title: Certificaten en netwerkprofielen voorbereiden voor HoloLens 2
description: Meer informatie over het configureren, gebruiken, implementeren en oplossen van problemen met certificaten voor netwerken op HoloLens 2 mixed reality apparaten.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: aboeger
ms.topic: article
ms.localizationpriority: high
ms.date: 9/15/2020
ms.reviewer: v-evmill
audience: ITPro
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 62eedd0c05bb23f11a4e17a97b4ab5441a2931cf
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639264"
---
# <a name="prepare-certificates-and-network-profiles-for-hololens-2"></a>Certificaten en netwerkprofielen voorbereiden voor HoloLens 2

Verificatie op basis van certificaten is een algemene vereiste voor klanten die HoloLens 2. Mogelijk hebt u certificaten nodig voor toegang tot Wi-Fi, om verbinding te maken met VPN-oplossingen of om toegang te krijgen tot interne resources in uw organisatie.

Omdat HoloLens 2-apparaten doorgaans worden samengevoegd met Azure Active Directory (Azure AD) en worden beheerd door Intune of een andere MDM-provider, moet u dergelijke certificaten implementeren met behulp van een SIMPLE CERTIFICATE ENROLLMENT PROTOCOL-certificaatinfrastructuur (SCEP) of PKCS-certificaatinfrastructuur (Public Key Cryptography Standard) die is geïntegreerd met uw MDM-oplossing. 

>[!NOTE]
> Als u geen MDM-provider hebt, kunt u nog steeds certificaten implementeren via een inrichtingspakket [in](hololens-provisioning.md#steps-for-creating-provisioning-packages) [Windows Configuration Designer of](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?rtc=1&activetab=pivot:regionofsystemrequirementstab) via Certificate [Manager](certificate-manager.md) door naar Instellingen > Update & Security > Certificate Manager te **gaan.**

## <a name="certificate-requirements"></a>Certificaatvereisten
Basiscertificaten zijn vereist voor het implementeren van certificaten via een SCEP- of PKCS-infrastructuur. Voor andere toepassingen en services in uw organisatie moeten mogelijk ook basiscertificaten op uw HoloLens 2 geïmplementeerd. 

## <a name="wi-fi-connectivity-requirements"></a>Wi-Fi connectiviteitsvereisten
Als u wilt toestaan dat een apparaat automatisch wordt voorzien van de vereiste Wi-Fi-configuratie voor uw bedrijfsnetwerk, hebt u een Wi-Fi configuratieprofiel nodig. U kunt Intune of een andere MDM-provider configureren om deze profielen op uw apparaten te implementeren. Als uw netwerkbeveiliging vereist dat apparaten deel uitmaken van het lokale domein, moet u mogelijk ook uw Wi-Fi-netwerkinfrastructuur evalueren om ervoor te zorgen dat deze compatibel is met HoloLens 2-apparaten (HoloLens 2-apparaten zijn alleen lid van Azure AD).

## <a name="deploy-certificate-infrastructure"></a>Certificaatinfrastructuur implementeren
Als er nog geen SCEP- of PKCS-infrastructuur bestaat, moet u er een voorbereiden. Ter ondersteuning van het gebruik van SCEP- of PKCS-certificaten voor verificatie, vereist Intune het gebruik van een [certificaatconnector](/mem/intune/protect/certificate-connectors).

> [!NOTE]
> Wanneer u SCEP gebruikt met een Microsoft-CA, moet u ook de Registratieservice voor netwerkapparaten [(NDES) configureren](/mem/intune/protect/certificates-scep-configure#set-up-ndes)

Zie Een certificaatprofiel configureren voor uw apparaten in de [Microsoft Intune.](/intune/certificates-configure)

## <a name="deploy-certificates-and-wi-fivpn-profile"></a>Certificaten en Wi-Fi-/VPN-profiel implementeren
Volg deze stappen om certificaten en profielen te implementeren:
1.  Maak een profiel voor elk van de basiscertificaten en tussenliggende certificaten (zie [Vertrouwde certificaatprofielen maken.)](/intune/protect/certificates-configure#create-trusted-certificate-profiles) Elk van deze profielen moet een beschrijving hebben met een vervaldatum in DD/MM/YYY-indeling. **Certificaatprofielen zonder een vervaldatum worden niet geïmplementeerd.**
1.  Maak een profiel voor elke SCEP- of PKCS-certificaten (zie Een SCEP-certificaatprofiel maken of Een [PKCS-certificaatprofiel](/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)maken) Elk van deze profielen moet een beschrijving hebben met een vervaldatum in DD/MM/YYYY-indeling. **Certificaatprofielen zonder een vervaldatum worden niet geïmplementeerd.**

    > [!NOTE]
    > Omdat de HoloLens 2 wordt beschouwd als een gedeeld apparaat, meerdere gebruikers per apparaat, wordt het aanbevolen waar mogelijk apparaatcertificaten te implementeren in plaats van gebruikerscertificaten voor Wi-Fi verificatie

3.  Maak een profiel voor elk bedrijfsnetwerk Wi-Fi netwerk (zie [Wi-Fi-instellingen voor](/intune/wi-fi-settings-windows)Windows 10 en latere apparaten). 
    > [!NOTE]
    > Het wordt aanbevolen om het Wi-Fi waar mogelijk toe [te](/mem/intune/configuration/device-profile-assign) Wi-Fi aan Apparaatgroepen in plaats van gebruikersgroepen. 

    > [!TIP]
    > U kunt ook een werkprofiel Wi-Fi exporteren vanaf een Windows 10 pc in uw bedrijfsnetwerk. Met deze export maakt u een XML-bestand met alle huidige instellingen. Importeer dit bestand vervolgens in Intune en gebruik het als het Wi-Fi profiel voor uw HoloLens 2 apparaten. Zie [Export and import Wi-Fi settings for Windows devices (Instellingen voor](/mem/intune/configuration/wi-fi-settings-import-windows-8-1) Windows exporteren en importeren).

4.  Maak een profiel voor elke zakelijke VPN (zie Windows 10 en Windows Holographic-apparaatinstellingen om VPN-verbindingen toe te [voegen met Behulp van Intune).](/intune/vpn-settings-windows-10)

## <a name="troubleshooting-certificates"></a>Problemen met certificaten oplossen

Als u wilt valideren dat een certificaat correct is geïmplementeerd, gebruikt u [Certificaatbeheer](certificate-manager.md) op het apparaat om te controleren of uw certificaat aanwezig is.  

>[!WARNING]
> Hoewel u door MDM geïmplementeerde certificaten kunt weergeven in Certificate Manager, kunt u ze niet verwijderen in Certificate Manager. U moet ze verwijderen via MDM.


