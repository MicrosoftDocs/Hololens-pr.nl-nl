---
title: Registratie van HoloLens in MDM
description: Meer informatie over het inschrijven HoloLens in Mobile Device Management (MDM) voor eenvoudiger beheer van meerdere apparaten.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 2a9b3fca-8370-44ec-8b57-fb98b8d317b0
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/15/2021
ms.reviewer: ''
manager: ranjibb
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 9f466abe45a1a9ad676f8dd6a94244473c084be7
ms.sourcegitcommit: 38b5e4d92da6fc5d6a6a2ef875644d6db2cce822
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/22/2021
ms.locfileid: "130202876"
---
# <a name="enroll-hololens-in-mdm"></a>Registratie van HoloLens in MDM

U kunt meerdere apparaten Microsoft HoloLens tegelijkertijd beheren met behulp van oplossingen zoals [Microsoft Intune](/intune/windows-holographic-for-business). U kunt instellingen beheren, apps selecteren om beveiligingsconfiguraties te installeren en instellen die zijn afgestemd op de behoefte van uw organisatie. Zie Apparaten met [Windows Holographic](/intune/windows-holographic-for-business)beheren met Microsoft Intune, de configuratieserviceproviders [(CSP's)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens)die worden ondersteund in Windows Holographic en de beleidsregels die door [Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).

> [!NOTE]
> Mobile Device Management (MDM), met inbegrip van de functies vpn, Bitlocker en kioskmodus, is alleen beschikbaar wanneer u een upgrade naar [Windows Holographic for Business.](hololens1-upgrade-enterprise.md)

## <a name="requirements"></a>Vereisten

 Uw organisatie moet Mobile Device Management (MDM) hebben ingesteld om de apparaten HoloLens beheren. Uw MDM-provider kan een Microsoft Intune een externe provider zijn die gebruikmaakt van Microsoft MDM-API's.

## <a name="different-ways-to-enroll"></a>Verschillende manieren om in te schrijven

Afhankelijk van het type identiteit [dat is gekozen](hololens-identity.md) tijdens OOBE of na het aanmelden, zijn er verschillende registratiemethoden.

- Als Identiteit Azure AD is, klikt u tijdens OOBE of Instellingen **de** knop App Access Work Verbinding maken  ->  **school.**  ->  
    - Voor Azure AD [vindt automatische MDM-inschrijving](hololens-enroll-mdm.md#auto-enrollment-in-mdm) alleen plaats als Azure AD is geconfigureerd met inschrijvings-URL's.

- Als de identiteit Azure AD is en het apparaat vooraf is geregistreerd bij de Intune MDM-server met een specifiek configuratieprofiel dat is toegewezen, vinden Azure AD-Join en automatische [MDM-inschrijving](hololens-enroll-mdm.md#auto-enrollment-in-mdm) plaats tijdens OOBE.
    - Ook wel [autopilot-stroom beschikbaar](hololens2-autopilot.md) in [builds van 19041.1103+](hololens-release-notes.md#windows-holographic-version-2004).


- Als Identiteit MSA is, gebruikt u Instellingen **knop Toegang** tot werk of  ->  **school**  ->  **Verbinding maken** app.
    - Ook wel werkaccountstroom (AWA) toevoegen genoemd.
- Als Identiteit lokale gebruiker is, kunt u Instellingen **de koppeling Werk-** of schoolinschrijving voor app-toegang alleen inschrijven  ->    ->  **bij apparaatbeheer.**
    - Ook wel pure MDM-inschrijvingsstroom genoemd.

Zodra het apparaat is ingeschreven bij uw MDM-server, geeft Instellingen app aan dat het apparaat is ingeschreven bij apparaatbeheer.

## <a name="auto-enrollment-in-mdm"></a>Automatische inschrijving in MDM

Als uw organisatie een [Azure Premium-abonnement](https://azure.microsoft.com/overview/)heeft, gebruik maakt van Azure Active Directory (Azure AD) en een MDM-oplossing die een Azure AD-token accepteert voor verificatie (momenteel alleen ondersteund in Microsoft Intune en AirWatch), kan uw IT-beheerder Azure AD zo configureren dat MDM-inschrijving automatisch wordt toegestaan nadat de gebruiker zich heeft aanmelden bij azure AD Account. [Meer informatie over het configureren van Azure AD-inschrijving en](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment) [Azure Active Directory-integratie met MDM](/windows/client-management/mdm/azure-active-directory-integration-with-mdm) voor gedetailleerde achtergrondinformatie.

Wanneer automatische inschrijving is ingeschakeld, is er geen extra handmatige inschrijving nodig. Wanneer de gebruiker zich met een Azure AD-account heeft aangemeld, wordt het apparaat ingeschreven bij MDM nadat de eerste run-ervaring is uitgevoerd.

Wanneer een apparaat lid is van Azure AD, kan dit van invloed zijn op wie de eigenaar [van het apparaat heeft beschouwd.](security-adminless-os.md#device-owner)

## <a name="unenroll-hololens-from-intune"></a>Registratie van HoloLens bij Intune

Afhankelijk van de inschrijvingsmethode is het uitschrijving van uw apparaat mogelijk niet beschikbaar.

Als uw apparaat is ingeschreven met een Azure AD-account of Autopilot, kan het niet worden uitgeschreven bij Intune. Als u de aaneenvoeging HoloLens Azure AD wilt verwijderen of opnieuw wilt aanvoegen in een andere Azure AD-tenant, moet u het apparaat [opnieuw instellen/reflashen.](hololens-recovery.md#restart-the-device)

Als uw apparaat is ingeschreven vanuit een MSA-account dat een werkaccount heeft toegevoegd of van een lokaal account dat alleen is ingeschreven bij apparaatbeheer, kunt u de registratie van het apparaat in de uitschrijving van het apparaat in- of verwijderen. Open het Startmenu en selecteer vervolgens Instellingen de knop **Verbinding** verbreken met werk- of  ->  **schoolaccount** van  ->    ->  **App Access.**

## <a name="enrollment-troubleshooting"></a>Problemen met inschrijving oplossen

### <a name="ensure-device-is-successfully-connected-to-internet-before-attempting-enrollment-post-oobe"></a>Zorg ervoor dat het apparaat is verbonden met internet voordat het apparaat wordt ingeschreven na OOBE

Nadat de gebruiker zich heeft aangemeld, zorgt u voor een internetverbinding door te bladeren naar een website op het apparaat die is gericht op internet.

### <a name="ensure-that-azure-active-directory-aad-join-is-not-disabled-in-your-aad-tenant"></a>Zorg ervoor dat Azure Active Directory (AAD) join niet is uitgeschakeld in uw AAD tenant

Raadpleeg [Uw apparaatinstellingen configureren voor](/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) informatie over de beschikbare opties in Azure Portal.

### <a name="ensure-valid-license-is-assigned-to-the-user"></a>Controleren of er een geldige licentie is toegewezen aan de gebruiker

Raadpleeg [Troubleshoot Windows device enrollment problems in Microsoft Intune](/troubleshoot/mem/intune/troubleshoot-windows-enrollment-errors) (Problemen met apparaatinschrijving [](/troubleshoot/mem/intune/troubleshoot-windows-enrollment-errors#check-device-type-restrictions) oplossen in Microsoft Intune) met name in de volgende secties, dat wil zeggen Beperkingen voor apparaattype controleren en Een geldige licentie toewijzen aan [de gebruiker.](/troubleshoot/mem/intune/troubleshoot-windows-enrollment-errors#assign-a-valid-license-to-the-user)

### <a name="ensure-that-mdm-enrollment-isnt-blocked-for-windows-devices"></a>Zorg ervoor dat MDM-inschrijving niet is geblokkeerd voor Windows apparaten

Als u de inschrijving wilt laten slagen, moet u ervoor zorgen dat uw HoloLens kunnen worden ingeschreven. Aangezien HoloLens wordt beschouwd als een Windows apparaat, hoeven er geen inschrijvingsbeperkingen te zijn die uw implementatie kunnen blokkeren. [Bekijk deze lijst met beperkingen](/mem/intune/enrollment/enrollment-restrictions-set) en zorg ervoor dat u uw apparaten kunt registreren.
