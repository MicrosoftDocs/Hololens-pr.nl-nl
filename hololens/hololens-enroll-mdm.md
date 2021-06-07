---
title: HoloLens inschrijven bij MDM
description: Meer informatie over het inschrijven van HoloLens bij Mobile Device Management (MDM) voor eenvoudiger beheer van meerdere apparaten.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 2a9b3fca-8370-44ec-8b57-fb98b8d317b0
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/06/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 624ebd17335820b1d2858f9d39cabb7032a83bfe
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/19/2021
ms.locfileid: "111377917"
---
# <a name="enroll-hololens-in-mdm"></a>HoloLens inschrijven bij MDM

U kunt meerdere apparaten Microsoft HoloLens beheren met behulp van oplossingen zoals [Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business). U kunt instellingen beheren, apps selecteren om beveiligingsconfiguraties te installeren en instellen die zijn afgestemd op de behoefte van uw organisatie. Zie [Apparaten met Windows Holographic](https://docs.microsoft.com/intune/windows-holographic-for-business)beheren met Microsoft Intune, de configuratieserviceproviders [(CSP's)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens)die worden ondersteund in Windows Holographic en het beleid dat wordt [ondersteund door Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).

> [!NOTE]
> Mobile Device Management (MDM), met inbegrip van de functies voor VPN, Bitlocker en kioskmodus, is alleen beschikbaar wanneer u een upgrade naar [Windows Holographic for Business.](hololens1-upgrade-enterprise.md)

## <a name="requirements"></a>Vereisten

 Uw organisatie moet Mobile Device Management (MDM) hebben ingesteld om HoloLens-apparaten te kunnen beheren. Uw MDM-provider kan een Microsoft Intune een externe provider zijn die gebruikmaakt van Microsoft MDM-API's.
 
## <a name="different-ways-to-enroll"></a>Verschillende manieren om in te schrijven

Afhankelijk van het type identiteit [dat](hololens-identity.md) is gekozen tijdens OOBE of na het aanmelden, zijn er verschillende registratiemethoden.

- Als Identiteit Azure AD is, klikt u op de knop OOBE of **Instellingen App** Access Work  ->  **of School**  ->  **Connect.**
    - Voor Azure AD [vindt automatische MDM-inschrijving](hololens-enroll-mdm.md#auto-enrollment-in-mdm) alleen plaats als Azure AD is geconfigureerd met inschrijvings-URL's.
     
- Als Identiteit Azure AD is en het apparaat vooraf is geregistreerd bij de Intune MDM-server met een specifiek configuratieprofiel dat is toegewezen, vinden Azure AD-Join en automatische [MDM-inschrijving](hololens-enroll-mdm.md#auto-enrollment-in-mdm) plaats tijdens OOBE.
    - Ook wel [autopilot-stroom genoemd,](hololens2-autopilot.md) beschikbaar in [19041.1103+ builds.](hololens-release-notes.md#windows-holographic-version-2004)
    

- Als Identiteit MSA is, gebruikt u de knop **Instellingen**  ->  **App-toegang Werk of School**  ->  **Verbinden.**
    - Ook wel werkaccount toevoegen (AWA)-stroom genoemd.
- Als Identiteit lokale gebruiker is, gebruikt u Instellingen   ->  **App-toegang Werk-** of  ->  **schoolinschrijving alleen in de koppeling Apparaatbeheer.**
    - Ook wel pure MDM-inschrijvingsstroom genoemd.

Zodra het apparaat is ingeschreven bij uw MDM-server, geeft de app Instellingen aan dat het apparaat is ingeschreven bij apparaatbeheer.

## <a name="auto-enrollment-in-mdm"></a>Automatische inschrijving in MDM

Als uw organisatie een [Azure Premium-abonnement](https://azure.microsoft.com/overview/)heeft, gebruik maakt van Azure Active Directory (Azure AD) en een MDM-oplossing die een Azure AD-token accepteert voor verificatie (momenteel alleen ondersteund in Microsoft Intune en AirWatch), kan uw IT-beheerder Azure AD configureren om automatisch MDM-inschrijving toe te staan nadat de gebruiker zich heeft aanmelden met zijn Azure AD-account. [Meer informatie over het configureren van Azure AD-inschrijving.](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

Wanneer automatische inschrijving is ingeschakeld, is er geen extra handmatige inschrijving nodig. Wanneer de gebruiker zich met een Azure AD-account heeft aangemeld, wordt het apparaat ingeschreven bij MDM nadat de first-run experience is uitgevoerd.

Wanneer een apparaat lid is van Azure AD, kan dit van invloed zijn op wie als de eigenaar [van het apparaat wordt beschouwd.](security-adminless-os.md#device-owner)

## <a name="unenroll-hololens-from-intune"></a>HoloLens uitschrijving bij Intune

Afhankelijk van de inschrijvingsmethode is het mogelijk dat de registratie van uw apparaat niet beschikbaar is.

Als uw apparaat is ingeschreven met een Azure AD-account of Autopilot, kan het niet worden uitgeschreven bij Intune. Als u HoloLens wilt losgevoegd van Azure AD of opnieuw wilt worden lid van een andere Azure AD-tenant, moet u het apparaat opnieuw [instellen/reflashen.](https://docs.microsoft.com/hololens/hololens-recovery#reset-the-device)

Als uw apparaat is ingeschreven via een MSA-account dat een werkaccount heeft toegevoegd of van een lokaal account dat alleen is ingeschreven bij apparaatbeheer, kunt u de registratie van het apparaat in de hand nemen. Open het Startmenu en selecteer vervolgens **Instellingen**  ->  **App-toegang Werk-** of  ->  *schoolaccount*  ->  **verbreken-knop.**