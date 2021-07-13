---
title: Overzicht van cloud verbonden HoloLens 2 met Remote Assist
description: Meer informatie over het inschrijven van HoloLens 2 via een cloudnetwerk met behulp van Dynamics 365 Remote Assist.
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
ms.openlocfilehash: 86d36275d5cf1296ca3e9fec90684a188a29f3f0
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635123"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a>Implementatiehandleiding : Cloud verbonden HoloLens 2 met Remote Assist – Overzicht

Deze handleiding helpt IT-professionals bij het plannen en implementeren van Microsoft HoloLens 2 apparaten met Remote Assist in hun organisatie. Dit dient als een model voor proof-of-concept-implementaties in uw organisatie in HoloLens 2 gebruiksgevallen. De installatie is vergelijkbaar met [Scenario A: Implementeren naar apparaten die verbinding maken met de cloud.](https://docs.microsoft.com/hololens/common-scenarios#scenario-a) 

Tijdens de handleiding wordt be kwijt hoe u uw apparaten kunt registreren bij uw apparaatbeheer, licenties kunt toepassen als dat nodig is en hoe u kunt valideren dat uw eindgebruikers direct gebruik kunnen maken van Remote Assist bij de installatie van het apparaat. Hiervoor gaan we in op de belangrijke onderdelen van de infrastructuur die nodig zijn om alles in te stellen en te laten werken: implementatie op schaal bereiken met HoloLens 2. Er worden geen andere apparaatbeperkingen of configuraties toegepast in deze handleiding, maar we raden u aan deze opties na het afronden te verkennen.

## <a name="prerequisites"></a>Vereisten

De volgende infrastructuur moet zijn geïmplementeerd om de HoloLens 2. Zo niet, dan is het instellen van Azure en Intune opgenomen in deze handleiding:

Dit is een set die vergelijkbaar is met [Scenario A:](/hololens/common-scenarios#scenario-a)Implementeren op apparaten die zijn verbonden met de cloud. Dit is een goede optie voor veel Proof of Concept-implementaties, waaronder:

- Wi-Fi netwerken zijn doorgaans volledig open voor internet- en cloudservices
- Azure AD Join met MDM Auto Enrollment -- MDM (Intune) Managed
- Gebruikers melden zich aan met hun eigen bedrijfsaccount (Azure AD)
    - Eén of meerdere gebruikers per apparaat worden ondersteund.

:::image type="content" alt-text="Scenario voor verbonden cloud" source="./images/deployment-guides-revised-scenario-a.png" lightbox="./images/deployment-guides-revised-scenario-a.png":::


## <a name="learn-about-remote-assist"></a>Meer informatie over Remote Assist

Remote Assist kunt samenwerkend onderhoud en herstel, externe inspectie, evenals kennis delen en trainen. Door verbinding te maken met personen met verschillende rollen en locaties kan een monteur Remote Assist verbinding maken met een externe medewerker op Microsoft Teams. Ze kunnen video's, schermopnamen en aantekeningen combineren om problemen in realtime op te lossen, zelfs wanneer&#39;zich niet op dezelfde locatie bevinden. Externe samenwerkers kunnen referentieafbeeldingen, schema's en andere nuttige informatie invoegen die de technicus&#39;de fysieke ruimte, zodat ze naar het schema kunnen verwijzen tijdens het werken met de HoloLens.

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="remote-assist-licensing-and-requirements"></a>Remote Assist licentieverlening en vereisten

- Azure AD-account (vereist voor het kopen van het abonnement en het toewijzen van licenties)
- [Remote Assist abonnement](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (of [Remote Assist proefversie](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist))
    
#### <a name="dynamics-365-remote-assist-user"></a>Dynamics 365 Remote Assist gebruiker

- Remote Assist licentie
- Netwerkverbinding

#### <a name="microsoft-teams-user"></a>Microsoft Teams gebruiker

- Microsoft Teams of [Teams Freemium](https://products.office.com/microsoft-teams/free).
- Netwerkverbinding

Als u van plan bent dit scenario voor [verschillende tenants te implementeren,](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)hebt u mogelijk een licentie voor informatiebarrières nodig. Zie [dit artikel om](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) te bepalen of een licentie voor een gegevensbarrière is vereist.

## <a name="in-this-guide-you-will"></a>In deze handleiding gaat u het volgende doen:

Voorbereiden:

> [!div class="checklist"]
> - [Meer informatie over de essentiële infrastructuur voor HoloLens 2 apparaten.](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [Lees meer over Azure AD en stel er een in als&#39;niet hebt.](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [Meer informatie over identiteitsbeheer en het instellen van Azure AD-accounts.](hololens2-cloud-connected-prepare.md#identity-management)
> - [Meer informatie over MDM en instellen met Intune als&#39;er nog geen hebt.](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [Meer informatie over de netwerkvereisten van Remote Assist.](hololens2-cloud-connected-prepare.md#network)
> - [Optioneel: VPN om verbinding te maken met organisatiebronnen](hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

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

