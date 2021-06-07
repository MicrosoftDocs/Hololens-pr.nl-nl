---
title: Overzicht van cloud verbonden HoloLens 2 met Remote Assist
description: Meer informatie over het inschrijven HoloLens 2 apparaten via een met de cloud verbonden netwerk met behulp van Dynamics 365 Remote Assist.
keywords: HoloLens, beheer, verbonden met de cloud, Remote Assist, AAD, Azure AD, MDM, Mobile Device Management
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 43fbcc3a841f6c3f15006f285188e55d22f10599
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/25/2021
ms.locfileid: "111377773"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a>Implementatiehandleiding - Cloud verbonden HoloLens 2 met Remote Assist – Overzicht

Deze handleiding helpt IT-professionals bij het plannen en implementeren van Microsoft HoloLens 2-apparaten in hun organisatie met als doel deze apparaten in de cloud te verbinden met uw organisatie met Dynamics 365 Remote Assist gereed voor gebruik. Houd er rekening mee dat dit zal fungeren als een model voor proof-of-concept-implementaties in uw organisatie voor verschillende HoloLens 2 gebruiksgevallen.

In deze handleiding wordt be kwijt hoe u uw apparaten kunt registreren bij uw apparaatbeheer, licenties kunt toepassen wanneer dat nodig is en hoe u kunt valideren dat uw eindgebruikers de apparaten direct kunnen Remote Assist bij de installatie van het apparaat. Hiervoor gaan we in op de belangrijke onderdelen van de infrastructuur die nodig zijn om in te stellen en te werken: implementatie op schaal bereiken met HoloLens 2.

[![Scenario voor verbonden cloud ](./images/deployment-guides-revised-scenario-a.png)](./images/deployment-guides-revised-scenario-a.png#lightbox)
## <a name="in-this-guide"></a>In deze handleiding

Deze handleiding heeft als specifiek doel het instellen van Remote Assist uw organisatie op uw HoloLens-apparaten. We behandelen de benodigde behoeften om dat doel te bereiken. Om de focus op dit doel te houden, worden bepaalde voorbereidingen en configuraties vooraf geselecteerd om deze implementatie te optimaliseren of om de benodigde items voor de configuratie te verminderen. U wordt op de hoogte gesteld van deze keuzes en u kunt uw implementatie aanpassen op basis van de behoeften van uw bedrijf.

Dit is een set die vergelijkbaar is met [Scenario A:](https://docs.microsoft.com/hololens/common-scenarios#scenario-a)Implementeren op apparaten die zijn verbonden met de cloud. Dit is een goede optie voor veel Proof of Concept-implementaties, waaronder:

- Wi-Fi netwerken zijn doorgaans volledig open voor internet- en cloudservices
- Azure AD Join met MDM Auto Enrollment -- MDM (Intune) Managed
- Gebruikers melden zich aan met hun eigen bedrijfsaccount (Azure AD)
  - Eén of meerdere gebruikers per ondersteund apparaat
- Verschillende niveaus van vergrendelingsconfiguraties voor apparaten worden toegepast op basis van specifieke gebruiksgevallen, van Volledig geopend tot Kiosk voor één app



Er worden geen andere apparaatbeperkingen of configuraties toegepast in deze handleiding, maar we raden u aan deze opties na het afronden te verkennen.

## <a name="learn-about-remote-assist"></a>Meer informatie over Remote Assist

Remote Assist kunt samenwerkend onderhoud en herstel, externe inspectie, evenals kennis delen en trainen. Door verbinding te maken met personen met verschillende rollen en locaties kan een technicus Remote Assist verbinding maken met een externe medewerker in Microsoft Teams. Ze kunnen video's, schermopnamen en aantekeningen combineren om problemen in realtime op te lossen, zelfs wanneer&#39;zich niet op dezelfde locatie bevinden. Externe samenwerkers kunnen referentieafbeeldingen, schema's en andere nuttige informatie invoegen die de technicus&#39;de fysieke ruimte, zodat ze kunnen verwijzen naar het schema tijdens het werken zonder kop en zonder problemen met HoloLens.

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="in-this-guide-you-will"></a>In deze handleiding gaat u het volgende doen:

Voorbereiden:

> [!div class="checklist"]
> - [Meer informatie over de essentiële infrastructuur voor HoloLens 2 apparaten.](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [Lees meer over Azure AD en stel er een in als&#39;niet hebt.](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [Meer informatie over identiteitsbeheer en het instellen van Azure AD-accounts.](hololens2-cloud-connected-prepare.md#identity-management)
> - [Meer informatie over MDM en instellen met Intune als&#39;er nog geen hebt.](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [Meer informatie over de netwerkvereisten van Remote Assist.](hololens2-cloud-connected-prepare.md#network)
> - [Optioneel: VPN om verbinding te maken met organisatiebronnen](/hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

Configureren:

> [!div class="checklist"]
> - [Gebruikers en groepen maken.](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [Automatische inschrijving instellen in Azure AD.](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [Uw toepassingslicenties toewijzen.](hololens2-cloud-connected-configure.md#application-licenses)

Implementatie:

> [!div class="checklist"]
> - [Stel uw HoloLens 2 en valideer de inschrijving.](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [Controleer of u een aanroep Remote Assist maken.](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

Handhaven:

> [!div class="checklist"]
> - [Informatie over het bijwerken Remote Assist de Microsoft Store app.](hololens2-cloud-connected-maintain.md#updates)
> - [Een ondersteuningsplan maken.](hololens2-cloud-connected-maintain.md#support-plan)
> - [Ontwikkelplan.](hololens2-cloud-connected-maintain.md#development-plan)

## <a name="next-step"></a>Volgende stap

> [!div class="nextstepaction"]
> [Cloudgeconnecteerde implementatie - Voorbereiden](hololens2-cloud-connected-prepare.md)

