---
title: Implementatie HoloLens 2 in een commerciële omgeving plannen
description: Meer informatie over de belangrijkste behoeften voor het implementeren en beheren van HoloLens in bedrijfsomgevingen, waaronder infrastructuur, Azure Active Directory en Mobile Device Management.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: joyjaz
ms.author: v-jjaswinski
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 05/21/2021
appliesto:
- HoloLens 2
ms.openlocfilehash: 43162389eae82bc09135c62acd40d71048d14db1
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639077"
---
# <a name="planning-hololens-2-deployment-in-a-commercial-environment"></a>Implementatie HoloLens 2 in een commerciële omgeving plannen

## <a name="overview"></a>Overzicht

> [!NOTE]
> Dit overzicht is bedoeld om IT-professionals inzicht te geven in overwegingen voor het implementeren en beheren Microsoft HoloLens 2 apparaten binnen een organisatie. Zie Get your HoloLens 2 ready to use to get started (Uw apparaat voorbereiden om aan de slag [te gaan) voor](hololens2-setup.md) eindgebruikers van apparaten.

HoloLens 2 wordt uitgevoerd op Windows 10 Holographic waarmee organisaties robuuste, flexibele, ingebouwde technologieën voor het beheer van mobiele apparaten en apps kunnen gebruiken. Windows 10 Holographic biedt ondersteuning voor end-to-end levenscyclusbeheer van apparaten, om bedrijven controle te geven over hun apparaten, gegevens en apps. De HoloLens 2 kunnen eenvoudig worden opgenomen in standaard levenscyclusprocedures, van apparaatinschrijving, configuratie en toepassingsbeheer tot onderhoud en pensioen met behulp van een uitgebreide beheeroplossing voor mobiele apparaten.

De volgende stappen en video kunnen u helpen bij het doorlopen van HoloLens 2 ingebruikname binnen uw organisatie.

| &nbsp; | &nbsp; |
|--|--|
| ![Stap 1](images/1green.png)| <br/> **[Algemene implementatiescenario's:](hololens-requirements.md)** inzicht in implementatiescenario's en verken de belangrijkste onderdelen die nodig zijn om HoloLens 2 implementeren. |
| ![Stap 2](images/2green.png)| <br/> **[Voorbereiden:](#prepare)** vertrouwd raken met de infrastructuur essentials die nodig zijn voor HoloLens 2. |
| ![Stap 3](images/3green.png) | <br/> **[Configureren:](#configure)** meer informatie over het configureren van uw essentiële onderdelen voor een cloudimplementatie. |
| ![Stap 4](images/4green.png) | <br/> **[Implementeren:](#deploy)** ontdek hoe u uw apparaten implementeert en uw toepassingen veilig en efficiënt distribueert. |
| ![Stap 5](images/5green.png) | <br/> **[Onderhouden:](#maintain)** ontdek wat er nodig is om de status van uw apparaten HoloLens 2 te onderhouden en naleving van het bedrijfsbeleid te garanderen. |

<br/>

> [!VIDEO https://channel9.msdn.com/Shows/IT-Ops-Talk/HoloLens-2-Deployment-Overview/player]

## <a name="prepare"></a>Voorbereiden

Meer informatie over essentiële infrastructuurservices die nodig zijn om de volledige set HoloLens 2 ondersteunen.

| Onderdeel | Beschrijving |
|-----------|------------|
| [Azure AD](hololens-identity.md) | Biedt identiteits- en toegangsbeheer voor de HoloLens 2  |
| [Beheer van mobiele apparaten](hololens-mdm-configure.md)| Beheert HoloLens 2 apparaten die zijn verbonden met uw tenant  |
| [Wi-Fi-netwerk](hololens-commercial-infrastructure.md)| Wi-Fi beschikbaar is en apparaten kunnen worden verbonden met internet  |

## <a name="configure"></a>Configureren

Gebruik Intune en Autopilot als low-touch-oplossingen voor het registreren en configureren HoloLens 2 de Azure AD-tenant en MDM van uw organisatie.

| Onderdeel | Beschrijving |
|-----------|------------|
| [Automatische inschrijving](hololens-enroll-mdm.md#auto-enrollment-in-mdm) | Na de eerste aanmelding registreren apparaten zich automatisch bij Azure AD en registreren ze zich bij MDM  |
| [Toepassingslicenties](hololens2-cloud-connected-configure.md#application-licenses)| Kan worden toegepast op gebruikers, gebruikersgroepen of apparaatgroepen  |
| [Azure-gebruikers en -groepen](hololens2-cloud-connected-configure.md#azure-users-and-groups) | Helpt bij het toewijzen van configuraties en licenties voor de HoloLens 2  |

## <a name="deploy"></a>Implementeren

Distribueer uw HoloLens 2 apparaten en valideer de configuratie. 

| Onderdeel | Beschrijving |
|-----------|------------|
| [Validatie van inschrijving](hololens2-corp-connected-deploy.md#enrollment-validation) | Controleer of het apparaat is samengevoegd met Azure AD vanuit Instellingen of de Azure-portal |
| [Certificaatvalidatie](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation) | Controleer de instellingen en controleer of ze correct zijn gedistribueerd |
| [App-installaties valideren](hololens2-corp-connected-deploy.md#validate-lob-app-install) | Controleer of de app aanwezig is en aan uw HoloLens 2 |

## <a name="maintain"></a>Onderhouden

Gebruik Windows Update voor Bedrijven samen met uw MDM-systeem of de Microsoft Store om uw HoloLens 2 apps bij te werken.

| Onderdeel | Beschrijving |
|-----------|------------|
| [Werk HoloLens 2](hololens-updates.md) | Configureer updates naar behoefte via Windows Updates voor Bedrijven |
| [Apps bijwerken](app-deploy-overview.md) | Configureren via uw MDM-systeem of de Microsoft Store
