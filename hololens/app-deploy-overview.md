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
ms.openlocfilehash: ca87f34718319d489b69ba33ad24731628d87fac
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427632"
---
# <a name="app-management-overview"></a>App-beheer: Overzicht

U kunt apps implementeren op vier verschillende paden: **Mobile Device Management (MDM),** **Microsoft Store voor Bedrijven**, **Microsoft Store** of door ze te installeren via **Inrichting.**

## <a name="mobile-device-management-mdm"></a>het beheren van mobiele apparaten

Met een MDM-oplossing kunnen IT-besluitvormers en -beheerders privé hun in-house line-of-business-apps automatisch installeren (pushen) of apps aanschaffen via de Store voor een groep gebruikers. HoloLens apparaten werken het beste met Microsoft Endpoint Manager (Intune) voor [toepassingsbeheer.](app-deploy-intune.md) Intune biedt gebruikers ook een fijner beheer over it-beheerde apps via de Bedrijfsportal downloadbare ervaring.

> [!NOTE]
> De volgende instructies zijn voor gebruikers die hun toepassingen willen beheren met Intune. Microsoft raadt u aan Intune te gebruiken voor toepassings- en apparaatbeheer.

Mobile Device Management (MDM) is van toepassing op:

* MDM geïmplementeerd + Bedrijfsportal
* Line-Of-Business-apps (niet-openbaar)
* Handmatige installatie van beschikbare toepassingen via Bedrijfsportal
* Admin push through MDM policy (Push van beheerder via MDM-beleid)
* Automatisch bijwerken via MDM

## <a name="microsoft-store-for-business"></a>Microsoft Store voor Bedrijven

De [Microsoft Store voor Bedrijven](app-deploy-store-business.md) it-besluitvormers en -beheerders in bedrijven om gratis en betaalde apps te zoeken, te verkrijgen, te beheren en te distribueren. IT-beheerders kunnen Microsoft Store apps en persoonlijke Line-Of-Business-apps in één inventaris beheren, plus licenties toewijzen en opnieuw gebruiken als dat nodig is. Ga naar Vereisten voor het [gebruik van de](/microsoft-store/prerequisites-microsoft-store-for-business)Microsoft Store voor Bedrijven.

De Microsoft Store voor Bedrijven is van toepassing op:

* Openbare apps of Line-Of-Business-apps
* Automatische installatie van vereiste toepassingen via MDM-koppeling
* Gebruiker downloadt apps handmatig
* Automatisch bijwerken

## <a name="microsoft-store-apps"></a>Microsoft Store-apps

De Microsoft Store it-besluitvormers en -beheerders in bedrijven om openbare apps te zoeken, te verkrijgen, te beheren en te distribueren.

Deze Microsoft Store is van toepassing op:

* Alleen openbare apps
* Gebruiker downloadt apps handmatig
* Automatisch bijwerken als er verbinding is met internet

Ga naar [Holographic Store-apps voor meer informatie.](/hololens/holographic-store-apps)

## <a name="install-via-provisioning-packages"></a>Installeren via Inrichtingspakketten

[Met inrichtingspakketten](app-deploy-provisioning-package.md) kunt u aangepaste of Line-Of-Business-apps installeren, zodat IT-professionals en beheerders snel apps op een lokaal apparaat(en) via USB kunnen installeren. Deze installatie kan worden uitgevoerd zonder internetverbinding en voor elk identiteitstype.

Installeren via Inrichtingspakketten is van toepassing op:

* Line-Of-Business/zelf ontwikkelde (niet-openbare) apps
* Openbare apps (als het offline-installatieprogramma beschikbaar is)
* Alleen USB-side-loading
* Geen automatische update (handmatige updates via inrichtingspakket vereist)

## <a name="install-apps-on-hololens-2-via-app-installer"></a>Apps installeren op HoloLens 2 via App-installatieprogramma

Met de [App-installatieprogramma](app-deploy-app-installer.md) kunnen gebruikers een eenvoudige ervaring hebben voor het installeren van apps op lokale apparaten of het delen van een app met iemand anders die niet bekend is met andere installatiemethoden voor apps op HoloLens. Dit kan worden gedaan zonder dat u de ontwikkelaarsmodus hoeft in te schakelen of Apparaatportal. Dit is een eenvoudige methode voor het distribueren van een volledig gebouwde app. Ongeacht of u uw app gewoon wilt demo's geven aan een andere gebruiker met een HoloLens of als u uw app wilt implementeren, werkt deze methode eenvoudig.

Installeren via App-installatieprogramma is van toepassing op:

* Line-Of-Business/zelf ontwikkelde (niet-openbare) apps
* Alleen side-load
* Vereist geen ontwikkelaarsmodus of apparaatportal
* Eenvoudig voor eindgebruikers om te installeren
