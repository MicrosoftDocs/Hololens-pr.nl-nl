---
title: Overzicht - App-beheer
description: Ga aan de slag met een overzicht mixed reality app-beheer met Mobile Device Management, Microsoft Store voor Bedrijven en inrichtingspakketten.
keywords: HoloLens, gebruiker, account, app, toepassingsbeheer,
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 019700c7e35f31c234c9fe69870cae54b3364b631253c37a17d8eaa0fe3053bd
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/05/2021
ms.locfileid: "115665230"
---
# <a name="app-management-overview"></a>App-beheer: Overzicht

U kunt apps implementeren op vier verschillende paden: **Mobile Device Management (MDM),** **Microsoft Store voor Bedrijven**, **Microsoft Store** of door ze te installeren via **Inrichten.**

## <a name="mobile-device-management-mdm"></a>het beheren van mobiele apparaten

Met een MDM-oplossing kunnen IT-besluitvormers en -beheerders hun in-house line-of-business-apps privé installeren (pushen) of apps aanschaffen via de Store voor een groep gebruikers. HoloLens apparaten werken het beste met Microsoft Endpoint Manager (Intune) voor [toepassingsbeheer.](app-deploy-intune.md) Intune biedt gebruikers ook meer controle over door IT beheerde apps via de Bedrijfsportal downloadbare ervaring.

> [!NOTE]
> De volgende instructies zijn voor gebruikers die hun toepassingen willen beheren met Intune. Microsoft raadt het gebruik van Intune aan voor toepassings- en apparaatbeheer.

Mobile Device Management (MDM) is van toepassing op:

* MDM geïmplementeerd + Bedrijfsportal
* Line-Of-Business-apps (niet-openbaar)
* Handmatige installatie van beschikbare toepassingen via Bedrijfsportal
* Admin push through MDM policy (Push van beheerder via MDM-beleid)
* Automatisch bijwerken via MDM

## <a name="microsoft-store-for-business"></a>Microsoft Store voor Bedrijven

De [Microsoft Store voor Bedrijven](app-deploy-store-business.md) it-besluitvormers en -beheerders in bedrijven om gratis en betaalde apps te zoeken, te verkrijgen, te beheren en te distribueren. IT-beheerders kunnen Microsoft Store apps en privé-Line-Of-Business-apps in één inventaris beheren, en zo nodig licenties toewijzen en opnieuw gebruiken. Ga naar Vereisten voor het gebruik van de Microsoft Store voor Bedrijven voor [meer Microsoft Store voor Bedrijven.](/microsoft-store/prerequisites-microsoft-store-for-business)

De Microsoft Store voor Bedrijven is van toepassing op:

* Openbare apps of Line-Of-Business-apps
* Automatische installatie van vereiste toepassingen via MDM-koppeling
* Gebruiker downloadt apps handmatig
* Automatisch bijwerken

## <a name="microsoft-store-apps"></a>Microsoft Store-apps

De Microsoft Store biedt IT-besluitvormers en -beheerders in bedrijven om openbare apps te zoeken, te verkrijgen, te beheren en te distribueren.

Deze Microsoft Store is van toepassing op:

* Alleen openbare apps
* Gebruiker downloadt apps handmatig
* Automatisch bijwerken als er verbinding is met internet

Ga naar [Holographic Store-apps voor meer informatie.](/hololens/holographic-store-apps)

## <a name="install-via-provisioning-packages"></a>Installeren via inrichtingspakketten

[Met inrichtingspakketten](app-deploy-provisioning-package.md) kunt u aangepaste of Line-Of-Business-apps installeren, zodat IT-professionals en beheerders snel apps op een lokaal apparaat(en) via USB kunnen installeren. Deze installatie kan worden uitgevoerd zonder internetverbinding en voor elk identiteitstype.

Installeren via inrichtingspakketten is van toepassing op:

* Line-Of-Business/zelf ontwikkelde (niet-openbare) apps
* Openbare apps (als offline installatieprogramma beschikbaar is)
* Alleen USB-side-loading
* Geen automatische update (vereist handmatige updates via Inrichtingspakket)

## <a name="install-apps-on-hololens-2-via-app-installer"></a>Apps installeren op HoloLens 2 via App-installatieprogramma

Met de [App-installatieprogramma](app-deploy-app-installer.md) kunnen gebruikers een eenvoudige ervaring hebben voor het installeren van apps op lokale apparaten of het delen van een app met iemand anders die niet bekend is met andere installatiemethoden voor apps op HoloLens. Dit kan worden gedaan zonder dat u de ontwikkelaarsmodus hoeft in te schakelen of Apparaatportal. Dit is een eenvoudige methode voor het distribueren van een volledig gebouwde app. Ongeacht of u uw app gewoon wilt demo's geven aan een andere gebruiker met een HoloLens of als u uw app wilt implementeren, werkt deze methode eenvoudig.

Installeren via App-installatieprogramma is van toepassing op:

* Line-Of-Business/zelf ontwikkelde (niet-openbare) apps
* Alleen side-load
* Vereist geen ontwikkelaarsmodus of apparaatportal
* Eenvoudig voor eindgebruikers om te installeren
