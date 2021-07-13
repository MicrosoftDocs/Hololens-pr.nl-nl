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
ms.openlocfilehash: 26fd2def8ce1fa8f960ab930e209c74fb37e2e0a
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639757"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a><span data-ttu-id="79b71-104">Implementatiehandleiding – Cloud verbonden HoloLens 2 met Remote Assist – Overzicht</span><span class="sxs-lookup"><span data-stu-id="79b71-104">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist – Overview</span></span>

<span data-ttu-id="79b71-105">Deze handleiding helpt IT-professionals bij het plannen en implementeren van Microsoft HoloLens 2 apparaten met Remote Assist in hun organisatie.</span><span class="sxs-lookup"><span data-stu-id="79b71-105">This guide will help IT professionals plan for and deploy Microsoft HoloLens 2 devices with Remote Assist to their organization.</span></span> <span data-ttu-id="79b71-106">Dit dient als een model voor proof-of-concept-implementaties in uw organisatie in HoloLens 2 gebruiksgevallen.</span><span class="sxs-lookup"><span data-stu-id="79b71-106">This will serve as a model for proof-of-concept deployments to your organization across various HoloLens 2 use cases.</span></span> <span data-ttu-id="79b71-107">De installatie is vergelijkbaar met [Scenario A: Implementeren naar apparaten die verbinding maken met de cloud.](common-scenarios.md#scenario-a)</span><span class="sxs-lookup"><span data-stu-id="79b71-107">The setup is similar to [Scenario A: Deploy to cloud connect devices](common-scenarios.md#scenario-a).</span></span> 

<span data-ttu-id="79b71-108">Tijdens de handleiding wordt be kwijt hoe u uw apparaten kunt registreren bij uw apparaatbeheer, licenties kunt toepassen wanneer dat nodig is en hoe u valideert dat uw eindgebruikers direct Remote Assist kunnen gebruiken bij het instellen van het apparaat.</span><span class="sxs-lookup"><span data-stu-id="79b71-108">During the guide, we will cover how to enroll your devices into your device management, apply licenses as needed, and validate that your end users are able to immediately use Remote Assist upon device setup.</span></span> <span data-ttu-id="79b71-109">Hiervoor gaan we in op de belangrijke onderdelen van de infrastructuur die nodig zijn om te worden ingesteld en uitgevoerd: implementatie op schaal bereiken met HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="79b71-109">To do this, we will go over the important pieces of infrastructure needed to get set up and running – achieving deployment at scale with HoloLens 2.</span></span> <span data-ttu-id="79b71-110">Er worden geen andere apparaatbeperkingen of configuraties toegepast in deze handleiding, maar we raden u aan deze opties na het afronden te verkennen.</span><span class="sxs-lookup"><span data-stu-id="79b71-110">No other device restrictions or configurations will be applied in this guide, however, we encourage you to explore those options after finishing.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="79b71-111">Vereisten</span><span class="sxs-lookup"><span data-stu-id="79b71-111">Prerequisites</span></span>

<span data-ttu-id="79b71-112">De volgende infrastructuur moet zijn geïmplementeerd om de HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="79b71-112">The following infrastructure should be in place in order to deploy the HoloLens 2.</span></span> <span data-ttu-id="79b71-113">Zo niet, dan is het instellen van Azure en Intune opgenomen in deze handleiding:</span><span class="sxs-lookup"><span data-stu-id="79b71-113">If not, setting up Azure and Intune is included in this guide:</span></span>

<span data-ttu-id="79b71-114">Dit is een installatie die vergelijkbaar is met [scenario A:](/hololens/common-scenarios#scenario-a)Implementeren op apparaten die verbinding maken met de cloud. Dit is een goede optie voor veel Proof of Concept-implementaties, waaronder:</span><span class="sxs-lookup"><span data-stu-id="79b71-114">This is a setup similar to [Scenario A: Deploy to cloud connect devices](/hololens/common-scenarios#scenario-a), which is a good option for many Proof of Concept deployments, which will include:</span></span>

- <span data-ttu-id="79b71-115">Wi-Fi netwerken zijn doorgaans volledig open voor internet en cloudservices</span><span class="sxs-lookup"><span data-stu-id="79b71-115">Wi-Fi networks are typically fully open to the Internet and Cloud services</span></span>
- <span data-ttu-id="79b71-116">Azure AD Join with MDM Auto Enrollment — MDM-managed (Intune)</span><span class="sxs-lookup"><span data-stu-id="79b71-116">Azure AD Join with MDM Auto Enrollment—MDM-managed (Intune)</span></span>
- <span data-ttu-id="79b71-117">Gebruikers melden zich aan met hun eigen bedrijfsaccount (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="79b71-117">Users sign in with their own corporate account (Azure AD)</span></span>
    - <span data-ttu-id="79b71-118">Eén of meerdere gebruikers per apparaat worden ondersteund.</span><span class="sxs-lookup"><span data-stu-id="79b71-118">Single or multiple users per device are supported.</span></span>

:::image type="content" alt-text="Scenario met verbonden cloud" source="./images/deployment-guides-revised-scenario-a.png" lightbox="./images/deployment-guides-revised-scenario-a.png":::


## <a name="learn-about-remote-assist"></a><span data-ttu-id="79b71-120">Meer informatie over Remote Assist</span><span class="sxs-lookup"><span data-stu-id="79b71-120">Learn about Remote Assist</span></span>

<span data-ttu-id="79b71-121">Remote Assist biedt samenwerking voor onderhoud en reparatie, externe inspectie, evenals kennis delen en trainen.</span><span class="sxs-lookup"><span data-stu-id="79b71-121">Remote Assist allows for collaborative maintenance and repair, remote inspection, as well as knowledge sharing and training.</span></span> <span data-ttu-id="79b71-122">Door mensen in verschillende rollen en locaties met elkaar te verbinden, kan een technicus die gebruikmaakt van Remote Assist verbinding maken met een externe medewerker op Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="79b71-122">By connecting people in different roles and locations, a technician who uses Remote Assist can connect with a remote collaborator on Microsoft Teams.</span></span> <span data-ttu-id="79b71-123">Ze kunnen video's, schermopnamen en aantekeningen combineren om problemen in realtime op te lossen, zelfs wanneer ze zich niet op dezelfde locatie bevinden.</span><span class="sxs-lookup"><span data-stu-id="79b71-123">They can combine video, screenshots, and annotations to solve problems in real time even when they aren't in the same location.</span></span> <span data-ttu-id="79b71-124">Externe samenwerkers kunnen referentieafbeeldingen, schema's en andere nuttige informatie invoegen over de fysieke ruimte van de technicus, zodat ze kunnen verwijzen naar de schematische gegevens tijdens het werken met hun werk aan HoloLens.</span><span class="sxs-lookup"><span data-stu-id="79b71-124">Remote collaborators can insert reference images, schematics, and other helpful information the technician's physical space so they can refer to the schematic while working heads-up and hands-free on HoloLens.</span></span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="remote-assist-licensing-and-requirements"></a><span data-ttu-id="79b71-125">Remote Assist licentieverlening en vereisten</span><span class="sxs-lookup"><span data-stu-id="79b71-125">Remote Assist Licensing and Requirements</span></span>

- <span data-ttu-id="79b71-126">Azure AD-account (vereist voor het kopen van het abonnement en het toewijzen van licenties)</span><span class="sxs-lookup"><span data-stu-id="79b71-126">Azure AD account (required for purchasing the subscription and assigning licenses)</span></span>
- <span data-ttu-id="79b71-127">[Remote Assist abonnement](/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (of [Remote Assist proefversie](/dynamics365/mixed-reality/remote-assist/try-remote-assist))</span><span class="sxs-lookup"><span data-stu-id="79b71-127">[Remote Assist subscription](/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (or [Remote Assist Trial](/dynamics365/mixed-reality/remote-assist/try-remote-assist))</span></span>
    
#### <a name="dynamics-365-remote-assist-user"></a><span data-ttu-id="79b71-128">Dynamics 365 Remote Assist gebruiker</span><span class="sxs-lookup"><span data-stu-id="79b71-128">Dynamics 365 Remote Assist user</span></span>

- <span data-ttu-id="79b71-129">Remote Assist licentie</span><span class="sxs-lookup"><span data-stu-id="79b71-129">Remote Assist license</span></span>
- <span data-ttu-id="79b71-130">Netwerkverbinding</span><span class="sxs-lookup"><span data-stu-id="79b71-130">Network Connectivity</span></span>

#### <a name="microsoft-teams-user"></a><span data-ttu-id="79b71-131">Microsoft Teams gebruiker</span><span class="sxs-lookup"><span data-stu-id="79b71-131">Microsoft Teams user</span></span>

- <span data-ttu-id="79b71-132">Microsoft Teams of [Teams Freemium](https://products.office.com/microsoft-teams/free).</span><span class="sxs-lookup"><span data-stu-id="79b71-132">Microsoft Teams or [Teams Freemium](https://products.office.com/microsoft-teams/free).</span></span>
- <span data-ttu-id="79b71-133">Netwerkverbinding</span><span class="sxs-lookup"><span data-stu-id="79b71-133">Network connectivity</span></span>

<span data-ttu-id="79b71-134">Als u van plan bent dit scenario voor verschillende [tenants te implementeren,](/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)hebt u mogelijk een licentie voor informatiebarrières nodig.</span><span class="sxs-lookup"><span data-stu-id="79b71-134">If you plan on implementing this [cross-tenant scenario](/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants), you may need an Information Barriers license.</span></span> <span data-ttu-id="79b71-135">Zie Vendors and customers use full Dynamics 365 Remote Assist capabilities (Leveranciers en klanten gebruiken volledige mogelijkheden voor [Dynamics 365 Remote Assist informatiebarrièrelicentie).](/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation)</span><span class="sxs-lookup"><span data-stu-id="79b71-135">To determine if an Information Barrier License is required, see [Vendors and customers use full Dynamics 365 Remote Assist capabilities](/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation).</span></span>

## <a name="in-this-guide-you-will"></a><span data-ttu-id="79b71-136">In deze handleiding gaat u het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="79b71-136">In this guide you will:</span></span>

<span data-ttu-id="79b71-137">Voorbereiden:</span><span class="sxs-lookup"><span data-stu-id="79b71-137">Prepare:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="79b71-138">Meer informatie over de essentiële infrastructuur voor HoloLens 2 apparaten.</span><span class="sxs-lookup"><span data-stu-id="79b71-138">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [<span data-ttu-id="79b71-139">Lees meer over Azure AD en stel er een in als&#39;niet hebt.</span><span class="sxs-lookup"><span data-stu-id="79b71-139">Learn more about Azure AD and set up one if you don&#39;t have it.</span></span>](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [<span data-ttu-id="79b71-140">Meer informatie over identiteitsbeheer en het instellen van Azure AD-accounts.</span><span class="sxs-lookup"><span data-stu-id="79b71-140">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-cloud-connected-prepare.md#identity-management)
> - [<span data-ttu-id="79b71-141">Meer informatie over MDM en instellen met Intune als&#39;er nog geen hebt.</span><span class="sxs-lookup"><span data-stu-id="79b71-141">Learn more about MDM, and set up with Intune if you don&#39;t already have one ready.</span></span>](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [<span data-ttu-id="79b71-142">Meer informatie over de netwerkvereisten van Remote Assist.</span><span class="sxs-lookup"><span data-stu-id="79b71-142">Learn about the networking requirements of Remote Assist.</span></span>](hololens2-cloud-connected-prepare.md#network)
> - [<span data-ttu-id="79b71-143">Optioneel: VPN om verbinding te maken met organisatiebronnen</span><span class="sxs-lookup"><span data-stu-id="79b71-143">Optionally: VPN to connect to organizational resources</span></span>](hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

<span data-ttu-id="79b71-144">Configureren:</span><span class="sxs-lookup"><span data-stu-id="79b71-144">Configure:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="79b71-145">Gebruikers en groepen maken.</span><span class="sxs-lookup"><span data-stu-id="79b71-145">How to create Users and Groups.</span></span>](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [<span data-ttu-id="79b71-146">Automatische inschrijving instellen in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="79b71-146">How to set up Auto-enrollment within Azure AD.</span></span>](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [<span data-ttu-id="79b71-147">Uw toepassingslicenties toewijzen.</span><span class="sxs-lookup"><span data-stu-id="79b71-147">How to assign your Application licenses.</span></span>](hololens2-cloud-connected-configure.md#application-licenses)

<span data-ttu-id="79b71-148">Implementatie:</span><span class="sxs-lookup"><span data-stu-id="79b71-148">Deploy:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="79b71-149">Stel uw HoloLens 2 en valideer de inschrijving.</span><span class="sxs-lookup"><span data-stu-id="79b71-149">Set up your HoloLens 2 and validate enrollment.</span></span>](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [<span data-ttu-id="79b71-150">Controleer of u een aanroep Remote Assist maken.</span><span class="sxs-lookup"><span data-stu-id="79b71-150">Validate you can make a Remote Assist call.</span></span>](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

<span data-ttu-id="79b71-151">Handhaven:</span><span class="sxs-lookup"><span data-stu-id="79b71-151">Maintain:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="79b71-152">Informatie over het bijwerken Remote Assist de Microsoft Store app.</span><span class="sxs-lookup"><span data-stu-id="79b71-152">How to update Remote Assist using the Microsoft Store app.</span></span>](hololens2-cloud-connected-maintain.md#updates)
> - [<span data-ttu-id="79b71-153">Een ondersteuningsplan maken.</span><span class="sxs-lookup"><span data-stu-id="79b71-153">Making a support plan.</span></span>](hololens2-cloud-connected-maintain.md#support-plan)
> - [<span data-ttu-id="79b71-154">Ontwikkelplan.</span><span class="sxs-lookup"><span data-stu-id="79b71-154">Development plan.</span></span>](hololens2-cloud-connected-maintain.md#development-plan)

## <a name="next-step"></a><span data-ttu-id="79b71-155">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="79b71-155">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="79b71-156">Cloudgeconnecteerde implementatie - Voorbereiden</span><span class="sxs-lookup"><span data-stu-id="79b71-156">Cloud connected deployment - Prepare</span></span>](hololens2-cloud-connected-prepare.md)

