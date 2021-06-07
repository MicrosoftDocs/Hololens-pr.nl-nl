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
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a><span data-ttu-id="5ced8-104">Implementatiehandleiding - Cloud verbonden HoloLens 2 met Remote Assist – Overzicht</span><span class="sxs-lookup"><span data-stu-id="5ced8-104">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist – Overview</span></span>

<span data-ttu-id="5ced8-105">Deze handleiding helpt IT-professionals bij het plannen en implementeren van Microsoft HoloLens 2-apparaten in hun organisatie met als doel deze apparaten in de cloud te verbinden met uw organisatie met Dynamics 365 Remote Assist gereed voor gebruik.</span><span class="sxs-lookup"><span data-stu-id="5ced8-105">This guide helps IT professionals plan for and deploy Microsoft HoloLens 2 devices to their organization with the overall goal of having those devices cloud connected to your organization with Dynamics 365 Remote Assist ready to use.</span></span> <span data-ttu-id="5ced8-106">Houd er rekening mee dat dit zal fungeren als een model voor proof-of-concept-implementaties in uw organisatie voor verschillende HoloLens 2 gebruiksgevallen.</span><span class="sxs-lookup"><span data-stu-id="5ced8-106">Keep in mind, this will serve as a model for proof-of-concept deployments to your organization across a variety of HoloLens 2 use cases.</span></span>

<span data-ttu-id="5ced8-107">In deze handleiding wordt be kwijt hoe u uw apparaten kunt registreren bij uw apparaatbeheer, licenties kunt toepassen wanneer dat nodig is en hoe u kunt valideren dat uw eindgebruikers de apparaten direct kunnen Remote Assist bij de installatie van het apparaat.</span><span class="sxs-lookup"><span data-stu-id="5ced8-107">During the guide we will cover how to enroll your devices into your device management, apply licenses as needed, and validate that your end users are able to immediately use Remote Assist upon device setup.</span></span> <span data-ttu-id="5ced8-108">Hiervoor gaan we in op de belangrijke onderdelen van de infrastructuur die nodig zijn om in te stellen en te werken: implementatie op schaal bereiken met HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="5ced8-108">To do this we will go over the important pieces of infrastructure needed to get set up and running – achieving deployment at scale with HoloLens 2.</span></span>

<span data-ttu-id="5ced8-109">[![Scenario voor verbonden cloud ](./images/deployment-guides-revised-scenario-a.png)](./images/deployment-guides-revised-scenario-a.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="5ced8-109">[ ![Cloud connected scenario](./images/deployment-guides-revised-scenario-a.png) ](./images/deployment-guides-revised-scenario-a.png#lightbox)</span></span>
## <a name="in-this-guide"></a><span data-ttu-id="5ced8-110">In deze handleiding</span><span class="sxs-lookup"><span data-stu-id="5ced8-110">In this Guide</span></span>

<span data-ttu-id="5ced8-111">Deze handleiding heeft als specifiek doel het instellen van Remote Assist uw organisatie op uw HoloLens-apparaten.</span><span class="sxs-lookup"><span data-stu-id="5ced8-111">This guide has the specific goal of setting up Remote Assist within your organization on your HoloLens devices.</span></span> <span data-ttu-id="5ced8-112">We behandelen de benodigde behoeften om dat doel te bereiken.</span><span class="sxs-lookup"><span data-stu-id="5ced8-112">We will cover the necessities needed to achieve that goal.</span></span> <span data-ttu-id="5ced8-113">Om de focus op dit doel te houden, worden bepaalde voorbereidingen en configuraties vooraf geselecteerd om deze implementatie te optimaliseren of om de benodigde items voor de configuratie te verminderen.</span><span class="sxs-lookup"><span data-stu-id="5ced8-113">In order to maintain focus on this goal certain preparation and configurations will be pre-selected in order to optimize for this deployment or to reduce the items needed to configure.</span></span> <span data-ttu-id="5ced8-114">U wordt op de hoogte gesteld van deze keuzes en u kunt uw implementatie aanpassen op basis van de behoeften van uw bedrijf.</span><span class="sxs-lookup"><span data-stu-id="5ced8-114">You will be informed of these choices, and can customize your deployment based on your business needs.</span></span>

<span data-ttu-id="5ced8-115">Dit is een set die vergelijkbaar is met [Scenario A:](https://docs.microsoft.com/hololens/common-scenarios#scenario-a)Implementeren op apparaten die zijn verbonden met de cloud. Dit is een goede optie voor veel Proof of Concept-implementaties, waaronder:</span><span class="sxs-lookup"><span data-stu-id="5ced8-115">This is a set up similar to [Scenario A: Deploy to cloud connect devices](https://docs.microsoft.com/hololens/common-scenarios#scenario-a), which is a good option for many Proof of Concept deployments, which will include:</span></span>

- <span data-ttu-id="5ced8-116">Wi-Fi netwerken zijn doorgaans volledig open voor internet- en cloudservices</span><span class="sxs-lookup"><span data-stu-id="5ced8-116">Wi-Fi networks are typically fully open to the Internet and Cloud services</span></span>
- <span data-ttu-id="5ced8-117">Azure AD Join met MDM Auto Enrollment -- MDM (Intune) Managed</span><span class="sxs-lookup"><span data-stu-id="5ced8-117">Azure AD Join with MDM Auto Enrollment -- MDM (Intune) Managed</span></span>
- <span data-ttu-id="5ced8-118">Gebruikers melden zich aan met hun eigen bedrijfsaccount (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="5ced8-118">Users sign in with their own corporate account (Azure AD)</span></span>
  - <span data-ttu-id="5ced8-119">Eén of meerdere gebruikers per ondersteund apparaat</span><span class="sxs-lookup"><span data-stu-id="5ced8-119">Single or multiple users per device supported</span></span>
- <span data-ttu-id="5ced8-120">Verschillende niveaus van vergrendelingsconfiguraties voor apparaten worden toegepast op basis van specifieke gebruiksgevallen, van Volledig geopend tot Kiosk voor één app</span><span class="sxs-lookup"><span data-stu-id="5ced8-120">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk</span></span>



<span data-ttu-id="5ced8-121">Er worden geen andere apparaatbeperkingen of configuraties toegepast in deze handleiding, maar we raden u aan deze opties na het afronden te verkennen.</span><span class="sxs-lookup"><span data-stu-id="5ced8-121">No other device restrictions or configurations will be applied in this guide, however we encourage you to explore those options after finishing.</span></span>

## <a name="learn-about-remote-assist"></a><span data-ttu-id="5ced8-122">Meer informatie over Remote Assist</span><span class="sxs-lookup"><span data-stu-id="5ced8-122">Learn about Remote Assist</span></span>

<span data-ttu-id="5ced8-123">Remote Assist kunt samenwerkend onderhoud en herstel, externe inspectie, evenals kennis delen en trainen.</span><span class="sxs-lookup"><span data-stu-id="5ced8-123">Remote Assist allows for collaborative maintenance and repair, remote inspection, as well as knowledge sharing and training.</span></span> <span data-ttu-id="5ced8-124">Door verbinding te maken met personen met verschillende rollen en locaties kan een technicus Remote Assist verbinding maken met een externe medewerker in Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="5ced8-124">By connecting people in different roles and locations a technician using Remote Assist can connect with a remote collaborator on Microsoft Teams.</span></span> <span data-ttu-id="5ced8-125">Ze kunnen video's, schermopnamen en aantekeningen combineren om problemen in realtime op te lossen, zelfs wanneer&#39;zich niet op dezelfde locatie bevinden.</span><span class="sxs-lookup"><span data-stu-id="5ced8-125">They can combine video, screenshots, and annotations to solve problems in real time even when they aren&#39;t in the same location.</span></span> <span data-ttu-id="5ced8-126">Externe samenwerkers kunnen referentieafbeeldingen, schema's en andere nuttige informatie invoegen die de technicus&#39;de fysieke ruimte, zodat ze kunnen verwijzen naar het schema tijdens het werken zonder kop en zonder problemen met HoloLens.</span><span class="sxs-lookup"><span data-stu-id="5ced8-126">Remote collaborators can insert reference images, schematics, and other helpful information the technician&#39;s physical space so they can refer to the schematic while working heads-up and hands-free on HoloLens.</span></span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="in-this-guide-you-will"></a><span data-ttu-id="5ced8-127">In deze handleiding gaat u het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="5ced8-127">In this guide you will:</span></span>

<span data-ttu-id="5ced8-128">Voorbereiden:</span><span class="sxs-lookup"><span data-stu-id="5ced8-128">Prepare:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="5ced8-129">Meer informatie over de essentiële infrastructuur voor HoloLens 2 apparaten.</span><span class="sxs-lookup"><span data-stu-id="5ced8-129">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [<span data-ttu-id="5ced8-130">Lees meer over Azure AD en stel er een in als&#39;niet hebt.</span><span class="sxs-lookup"><span data-stu-id="5ced8-130">Learn more about Azure AD and set up one if you don&#39;t have it.</span></span>](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [<span data-ttu-id="5ced8-131">Meer informatie over identiteitsbeheer en het instellen van Azure AD-accounts.</span><span class="sxs-lookup"><span data-stu-id="5ced8-131">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-cloud-connected-prepare.md#identity-management)
> - [<span data-ttu-id="5ced8-132">Meer informatie over MDM en instellen met Intune als&#39;er nog geen hebt.</span><span class="sxs-lookup"><span data-stu-id="5ced8-132">Learn more about MDM, and set up with Intune if you don&#39;t already have one ready.</span></span>](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [<span data-ttu-id="5ced8-133">Meer informatie over de netwerkvereisten van Remote Assist.</span><span class="sxs-lookup"><span data-stu-id="5ced8-133">Learn about the networking requirements of Remote Assist.</span></span>](hololens2-cloud-connected-prepare.md#network)
> - [<span data-ttu-id="5ced8-134">Optioneel: VPN om verbinding te maken met organisatiebronnen</span><span class="sxs-lookup"><span data-stu-id="5ced8-134">Optionally: VPN to connect to organizational resources</span></span>](/hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

<span data-ttu-id="5ced8-135">Configureren:</span><span class="sxs-lookup"><span data-stu-id="5ced8-135">Configure:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="5ced8-136">Gebruikers en groepen maken.</span><span class="sxs-lookup"><span data-stu-id="5ced8-136">How to create Users and Groups.</span></span>](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [<span data-ttu-id="5ced8-137">Automatische inschrijving instellen in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="5ced8-137">How to set up Auto-enrollment within Azure AD.</span></span>](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [<span data-ttu-id="5ced8-138">Uw toepassingslicenties toewijzen.</span><span class="sxs-lookup"><span data-stu-id="5ced8-138">How to assign your Application licenses.</span></span>](hololens2-cloud-connected-configure.md#application-licenses)

<span data-ttu-id="5ced8-139">Implementatie:</span><span class="sxs-lookup"><span data-stu-id="5ced8-139">Deploy:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="5ced8-140">Stel uw HoloLens 2 en valideer de inschrijving.</span><span class="sxs-lookup"><span data-stu-id="5ced8-140">Set up your HoloLens 2 and validate enrollment.</span></span>](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [<span data-ttu-id="5ced8-141">Controleer of u een aanroep Remote Assist maken.</span><span class="sxs-lookup"><span data-stu-id="5ced8-141">Validate you can make a Remote Assist call.</span></span>](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

<span data-ttu-id="5ced8-142">Handhaven:</span><span class="sxs-lookup"><span data-stu-id="5ced8-142">Maintain:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="5ced8-143">Informatie over het bijwerken Remote Assist de Microsoft Store app.</span><span class="sxs-lookup"><span data-stu-id="5ced8-143">How to update Remote Assist using the Microsoft Store app.</span></span>](hololens2-cloud-connected-maintain.md#updates)
> - [<span data-ttu-id="5ced8-144">Een ondersteuningsplan maken.</span><span class="sxs-lookup"><span data-stu-id="5ced8-144">Making a support plan.</span></span>](hololens2-cloud-connected-maintain.md#support-plan)
> - [<span data-ttu-id="5ced8-145">Ontwikkelplan.</span><span class="sxs-lookup"><span data-stu-id="5ced8-145">Development plan.</span></span>](hololens2-cloud-connected-maintain.md#development-plan)

## <a name="next-step"></a><span data-ttu-id="5ced8-146">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="5ced8-146">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="5ced8-147">Cloudgeconnecteerde implementatie - Voorbereiden</span><span class="sxs-lookup"><span data-stu-id="5ced8-147">Cloud connected deployment - Prepare</span></span>](hololens2-cloud-connected-prepare.md)

