---
title: HoloLens 2 naleving en AVG
description: AVG-documentatie
keywords: HoloLens, AVG, privacy, PII
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: skerewala, evmiller
ms.date: 02/05/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 8b795513d83c9d23f70b8dd8365e703d1fc43a51
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/19/2021
ms.locfileid: "111377957"
---
# <a name="hololens-2-privacy-statement"></a>HoloLens 2 privacyverklaring

Een van de belangrijkste elementen van de AVG is 'gegevensbescherming met opzet'. Dit concept geldt met name voor mobiele apparaten, zoals de HoloLens 2, vanwege hun draagbaarheid, onbeperkte internetverbinding en open communicatiekanalen. Hierdoor is de beveiliging van [](https://docs.microsoft.com/hololens/security-architecture) de HoloLens 2 opnieuw ontworpen om geavanceerde, innovatieve beveiliging en privacybescherming te bieden, end-to-end, waarin zowel Microsoft's benadering van [privacy](https://privacy.microsoft.com/)als AVG-regelgeving is gebruikt.

 >[!NOTE]
> Dit document is niet van toepassing op HoloLens (eerste generatie).

## <a name="privacy-overview"></a>Privacyoverzicht

HoloLens 2 is een zelfstandige Windows-computer met Windows Holographic waarmee apps en oplossingen worden uitgevoerd in een mixed reality omgeving. Het kan worden gebruikt als een beveiligd offline apparaat of worden geïmplementeerd als een [beheerd apparaat](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business) binnen uw organisatie. Zie de volgende koppelingen om te begrijpen hoe de HoloLens 2 en Microsoft uw gegevens gebruiken en beveiligen:
1. [Privacyverklaring van Microsoft- HoloLens:](https://privacy.microsoft.com/privacystatement) vouw de sectie Enterprise en **ontwikkelaar** uit in het navigatiemenu aan de linkerkant en selecteer Enterprise- en **ontwikkelaarssoftware en -apparaten.** Ga naar de **sectie HoloLens.**
2.  [Windows 10 en uw onlineservices](https://privacy.microsoft.com/windows10privacy)
3.  [Windows 10 & privacyhandleiding voor privacy](https://docs.microsoft.com/windows/privacy/windows-10-and-privacy-compliance)
4.  [Privacy en persoonlijke gegevens in Intune](https://docs.microsoft.com/mem/intune/protect/privacy-personal-data)

## <a name="network-security"></a>Netwerkbeveiliging
Na de HoloLens 2 [algemene](https://docs.microsoft.com/hololens/common-scenarios) [implementatiescenario's](https://docs.microsoft.com/azure/compliance/) worden uw gegevens beveiligd door de naleving van Azure van wereldklasse, samen met de integratie van wettelijke/regelgevingsstandaarden. Als u nog geen tijd hebt met Azure AD en Dynamics 365 Remote Assist, kunt u verwijzen naar de controlelijst voor aansprakelijkheid van Azure en [Dynamics 365](https://docs.microsoft.com/compliance/regulatory/gdpr-arc-azure-dynamics)voor de AVG.

Bovendien biedt Windows Defender Firewall essentiële functionaliteit om de connectiviteit van apparaten te beveiligen. Met HoloLens 2 is de firewall altijd ingeschakeld en zijn er geen manieren om deze programmatisch of via de gebruikersinterface uit te schakelen. Wanneer de HoloLens 2 wordt geïmplementeerd als een beheerd apparaat met behulp van [Intune,](https://docs.microsoft.com/mem/intune/protect/device-compliance-get-started)is er meer nalevingsfunctionaliteit beschikbaar met integratie voor [Endpoint met Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection) als mobile threat defense-oplossing. 

Meer informatie over de HoloLens 2 [beveiliging en architectuur](https://docs.microsoft.com/hololens/security-architecture).

## <a name="os-security"></a>Beveiliging van besturingssysteem
Updates worden automatisch uitgevoerd (standaard), zodat uw HoloLens 2 altijd up-to-date is met de nieuwste versie van Windows Holographic en alle geïnstalleerde apps. Zie de volgende informatie voor meer informatie over hoe ons besturingssysteem veilig is ontworpen:
1. [Scheiding en isolatie van staten](https://docs.microsoft.com/hololens/security-state-separation-isolation)
1. [Besturingssysteem met beheerdersrechten](https://docs.microsoft.com/hololens/security-adminless-os)
1. [Wachtwoordgebruik beperken](https://docs.microsoft.com/hololens/security-limiting-password-use)

## <a name="physical-security"></a>Fysieke beveiliging
HoloLens 2 beschikt over flashgeheugen dat wordt beveiligd met [BitLocker-versleuteling.](https://docs.microsoft.com/hololens/security-encryption-data-protection) Uw apparaat en de lokale gegevens kunnen offline worden geflitst met Advanced [Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8#activetab=pivot:overviewtab) of op afstand worden gewist via MDM als het is geïmplementeerd als een beheerd apparaat.

## <a name="data-protection"></a>Gegevensbeveiliging
Windows-updates worden automatisch uitgevoerd (standaard) en [Azure-integratie](https://docs.microsoft.com/hololens/security-encryption-data-protection#Azure-integration) beschermt gegevens die tussen zichzelf en de cloud reizen. 

Bij het implementeren HoloLens 2 naar externe clients zorgt [Dynamics 365 Remote Assist](https://docs.microsoft.com/hololens/hololens2-deployment-guide) ervoor dat uw gevoelige bedrijfsgegevens en -resources zowel afzonderlijk als veilig zijn. 

Het delen van diagnostische gegevens met Microsoft kan handmatig worden geconfigureerd door MDM of door de gebruiker tijdens OOBE. Er zijn twee opties: Optionele diagnostische gegevens en Vereiste diagnostische gegevens. Als uw oorspronkelijke diagnostische instelling op een later tijdstip moet worden gewijzigd voor het oplossen van problemen, kan deze door de gebruiker worden gewijzigd in Instellingen **-> Privacy -> Diagnostics & Feedback of** de IT-beheerder (MDM) als een beheerd apparaat is. Meer informatie over [diagnostische gegevens, feedback en privacy in Windows 10.](https://support.microsoft.com/windows/diagnostics-feedback-and-privacy-in-windows-10-28808a2b-a31b-dd73-dcd3-4559a5199319)

> [!Important]
> Diagnostische logboeken van apparaten bevatten persoonsgegevens, zoals over welke processen of toepassingen de gebruiker tijdens normale bewerkingen start. Wanneer meerdere gebruikers een HoloLens-apparaat delen (bijvoorbeeld wanneer gebruikers zich aanmelden bij hetzelfde apparaat met behulp van verschillende Microsoft Azure Active Directory-accounts (Azure AD), kunnen de diagnostische logboeken PII-gegevens bevatten die van toepassing zijn op meerdere gebruikers.

 

Er zijn [verschillende verzamelingsmethoden en beleidsregels voor gegevensretentie](https://docs.microsoft.com/hololens/hololens-diagnostic-logs) voor het verzamelen van diagnostische gegevens uit de HoloLens 2.  Zie Microsoft [Privacy statement - Diagnostics -](https://privacy.microsoft.com/privacystatement) expand **Windows** in het linkernavigatiemenu en selecteer Diagnostics voor meer informatie over hoe Microsoft diagnostische gegevens verzamelt en **gebruikt.** Ga naar de **sectie Diagnostische** gegevens.
