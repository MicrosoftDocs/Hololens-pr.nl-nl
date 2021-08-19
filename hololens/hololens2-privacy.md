---
title: HoloLens 2 Privacy en gegevensbescherming
description: Privacydocumentatie
keywords: HoloLens, AVG, privacy, PII, gegevensbescherming
author: golish
ms.author: marcingo
ms.reviewer: sekerawa, evmiller
ms.date: 02/05/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 74f74645a3fc1282f48cb7ce0f6f722979c91b04
ms.sourcegitcommit: 548550f309010fa95f674a7ff688166a31cf1963
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/18/2021
ms.locfileid: "122336735"
---
# <a name="hololens-2-privacy-and-data-protection"></a>HoloLens 2 Privacy en gegevensbescherming

Een van de belangrijkste elementen van de AVG is 'gegevensbescherming met opzet'. Dit concept geldt met name voor mobiele apparaten, zoals de HoloLens 2, vanwege hun draagbaarheid, onbeperkte internetverbinding en open communicatiekanalen. Hierdoor is de beveiliging van [](/hololens/security-architecture) de HoloLens 2 opnieuw ontworpen om geavanceerde, innovatieve beveiliging en privacybescherming, end-to-end te bieden, waarbij zowel Microsoft's benadering van [privacy](https://privacy.microsoft.com/)als AVG-regelgeving is gebruikt.

 >[!NOTE]
> Dit document is niet van toepassing op HoloLens (eerste generatie).

## <a name="privacy-overview"></a>Privacyoverzicht

HoloLens 2 is een op zichzelf staande Windows computer met Windows Holographic, die apps en oplossingen in een mixed reality omgeving. Het kan worden gebruikt als een beveiligd offline apparaat of worden geïmplementeerd als een [beheerd apparaat](/mem/intune/fundamentals/windows-holographic-for-business) binnen uw organisatie. Zie de volgende koppelingen om te begrijpen hoe de HoloLens 2 en Microsoft uw gegevens gebruiken en beveiligen:

1. [Privacyverklaring van Microsoft - HoloLens](https://privacy.microsoft.com/privacystatement) - vouw de sectie Enterprise en **developer** uit in het navigatiemenu aan de linkerkant en selecteer Software en apparaten voor ondernemingen **en ontwikkelaars.** Ga naar de **HoloLens** sectie.
2. [Windows 10 en uw onlineservices](https://privacy.microsoft.com/windows10privacy)
3. [Windows 10 & privacyhandleiding voor privacy](/windows/privacy/windows-10-and-privacy-compliance)
4. [Privacy en persoonlijke gegevens in Intune](/mem/intune/protect/privacy-personal-data)

## <a name="network-security"></a>Netwerkbeveiliging
Na de HoloLens 2 [algemene](/hololens/common-scenarios) [implementatiescenario's](/azure/compliance/) worden uw gegevens beveiligd door de eersteklas naleving van Azure, samen met de integratie van wettelijke/regelgevingsstandaarden. Als u nog geen tijd hebt met Azure AD en Dynamics 365 Remote Assist, kunt u verwijzen naar de controlelijst voor gereedheid van Azure en [Dynamics 365](/compliance/regulatory/gdpr-arc-azure-dynamics)voor de AVG.

Bovendien biedt Windows Defender Firewall essentiële functionaliteit om de connectiviteit van apparaten te beveiligen. Met HoloLens 2 is de firewall altijd ingeschakeld en zijn er geen manieren om deze programmatisch of via de gebruikersinterface uit te schakelen. Wanneer de HoloLens 2 wordt geïmplementeerd als een beheerd apparaat met behulp van [Intune,](/mem/intune/protect/device-compliance-get-started)is er meer nalevingsfunctionaliteit beschikbaar met integratie voor [Eindpunt](/mem/intune/protect/advanced-threat-protection) met Microsoft Intune als mobile threat defense-oplossing.

Meer informatie over de HoloLens 2 [beveiliging en architectuur](/hololens/security-architecture).

## <a name="os-security"></a>Beveiliging van besturingssysteem
Updates worden automatisch uitgevoerd (standaard), zodat uw HoloLens 2 altijd up-to-date is met de nieuwste versie van Windows Holographic en alle geïnstalleerde apps. Zie de volgende informatie voor meer informatie over hoe ons besturingssysteem veilig is ontworpen:

1. [Scheiding en isolatie van staten](/hololens/security-state-separation-isolation)
1. [Besturingssysteem met beheerdersrechten](/hololens/security-adminless-os)
1. [Wachtwoordgebruik beperken](/hololens/security-limiting-password-use)

## <a name="physical-security"></a>Fysieke beveiliging
HoloLens 2 beschikt over flashgeheugen dat wordt beveiligd met [BitLocker-versleuteling.](/hololens/security-encryption-data-protection) Uw apparaat en de lokale gegevens kunnen offline worden geflitst met Advanced [Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8#activetab=pivot:overviewtab) of op afstand worden gewist via MDM als het is geïmplementeerd als een beheerd apparaat.

## <a name="data-protection"></a>Gegevensbeveiliging
Windows updates worden automatisch uitgevoerd (standaard) en [Azure-integratie](/hololens/security-encryption-data-protection#Azure-integration) beschermt gegevens die tussen zichzelf en de cloud reizen.

Wanneer u HoloLens 2 clients implementeert, zorgt [Dynamics 365 Remote Assist](/hololens/hololens2-deployment-guide) ervoor dat uw gevoelige bedrijfsgegevens en -resources zowel afzonderlijk als veilig zijn.

Het delen van diagnostische gegevens met Microsoft kan handmatig worden geconfigureerd door MDM of door de gebruiker tijdens OOBE. Er zijn twee opties: optionele diagnostische gegevens en Vereiste diagnostische gegevens. Als uw oorspronkelijke diagnostische instelling op een later tijdstip moet worden gewijzigd voor het oplossen van problemen, kan deze door de gebruiker worden gewijzigd in **Instellingen -> Privacy -> Diagnostics & Feedback of** de IT-beheerder (MDM) als het een beheerd apparaat is. Meer informatie over [diagnostische gegevens, feedback en privacy in Windows 10](https://support.microsoft.com/windows/diagnostics-feedback-and-privacy-in-windows-10-28808a2b-a31b-dd73-dcd3-4559a5199319).

> [!Important]
> Diagnostische logboeken van apparaten bevatten persoonsgegevens, zoals over welke processen of toepassingen de gebruiker tijdens normale bewerkingen start. Wanneer meerdere gebruikers een HoloLens-apparaat delen (bijvoorbeeld wanneer gebruikers zich aanmelden bij hetzelfde apparaat met behulp van verschillende Microsoft Azure Active Directory-accounts (Azure AD) ), kunnen de diagnostische logboeken PII-gegevens bevatten die van toepassing zijn op meerdere gebruikers.

Er zijn [verschillende verzamelingsmethoden en beleidsregels voor gegevensretentie voor](/hololens/hololens-diagnostic-logs) het verzamelen van diagnostische gegevens van de HoloLens 2.  Zie Microsoft [Privacy statement - Diagnostics -](https://privacy.microsoft.com/privacystatement) expand Windows in het linkernavigatiemenu en selecteer Diagnostics voor meer informatie over hoe Microsoft diagnostische gegevens **verzamelt** en **gebruikt.** Ga naar de **sectie Diagnostische** gegevens.
