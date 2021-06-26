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
ms.openlocfilehash: a44247b4afea747e4b75c974fcae344380909989
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923530"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a><span data-ttu-id="65018-104">Implementatiehandleiding - Cloud verbonden HoloLens 2 met Remote Assist – Overzicht</span><span class="sxs-lookup"><span data-stu-id="65018-104">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist – Overview</span></span>

<span data-ttu-id="65018-105">Deze handleiding helpt IT-professionals bij het plannen en implementeren van Microsoft HoloLens 2 apparaten met Remote Assist in hun organisatie.</span><span class="sxs-lookup"><span data-stu-id="65018-105">This guide will help IT professionals plan for and deploy Microsoft HoloLens 2 devices with Remote Assist to their organization.</span></span> <span data-ttu-id="65018-106">Dit dient als een model voor proof-of-concept-implementaties in uw organisatie in HoloLens 2 gebruiksgevallen.</span><span class="sxs-lookup"><span data-stu-id="65018-106">This will serve as a model for proof-of-concept deployments to your organization across a variety of HoloLens 2 use cases.</span></span> <span data-ttu-id="65018-107">De installatie is vergelijkbaar met [Scenario A: Implementeren naar apparaten die verbinding maken met de cloud.](https://docs.microsoft.com/hololens/common-scenarios#scenario-a)</span><span class="sxs-lookup"><span data-stu-id="65018-107">The setup is similar to [Scenario A: Deploy to cloud connect devices](https://docs.microsoft.com/hololens/common-scenarios#scenario-a).</span></span> 

<span data-ttu-id="65018-108">Tijdens de handleiding wordt be kwijt hoe u uw apparaten kunt registreren bij uw apparaatbeheer, licenties kunt toepassen als dat nodig is en hoe u kunt valideren dat uw eindgebruikers direct gebruik kunnen maken van Remote Assist bij de installatie van het apparaat.</span><span class="sxs-lookup"><span data-stu-id="65018-108">During the guide, we will cover how to enroll your devices into your device management, apply licenses as needed, and validate that your end users are able to immediately use Remote Assist upon device setup.</span></span> <span data-ttu-id="65018-109">Hiervoor gaan we in op de belangrijke onderdelen van de infrastructuur die nodig zijn om te kunnen werken: implementatie op schaal bereiken met HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="65018-109">To do this, we will go over the important pieces of infrastructure needed to get set up and running – achieving deployment at scale with HoloLens 2.</span></span> <span data-ttu-id="65018-110">Er worden geen andere apparaatbeperkingen of configuraties toegepast in deze handleiding, maar we raden u aan deze opties na het afronden te verkennen.</span><span class="sxs-lookup"><span data-stu-id="65018-110">No other device restrictions or configurations will be applied in this guide, however, we encourage you to explore those options after finishing.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="65018-111">Vereisten</span><span class="sxs-lookup"><span data-stu-id="65018-111">Prerequisites</span></span>

<span data-ttu-id="65018-112">De volgende infrastructuur moet zijn geïmplementeerd om de HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="65018-112">The following infrastructure should be in place in order to deploy the HoloLens 2.</span></span> <span data-ttu-id="65018-113">Zo niet, dan is het instellen van Azure en Intune opgenomen in deze handleiding:</span><span class="sxs-lookup"><span data-stu-id="65018-113">If not, setting up Azure and Intune is included in this guide:</span></span>

- <span data-ttu-id="65018-114">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="65018-114">Wi-Fi</span></span>
    - <span data-ttu-id="65018-115">Netwerken zijn doorgaans geopend voor internet en cloudservices</span><span class="sxs-lookup"><span data-stu-id="65018-115">Networks are typically open to the Internet and Cloud services</span></span>
- <span data-ttu-id="65018-116">Azure Active Directory (Azure AD) Deelnemen met automatische MDM-inschrijving[(Azure AD P1-abonnement vereist)](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)</span><span class="sxs-lookup"><span data-stu-id="65018-116">Azure Active Directory (Azure AD) Join with MDM Auto Enrollment ([Azure AD P1 subscription](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) needed)</span></span>
- <span data-ttu-id="65018-117">MDM (Intune) Beheerd</span><span class="sxs-lookup"><span data-stu-id="65018-117">MDM (Intune) Managed</span></span>
    - <span data-ttu-id="65018-118">Een of meer toepassingen worden geïmplementeerd via MDM.</span><span class="sxs-lookup"><span data-stu-id="65018-118">One or more applications are deployed via MDM.</span></span>
- <span data-ttu-id="65018-119">Gebruikers melden zich aan met hun eigen bedrijfsaccount (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="65018-119">Users sign in with their own corporate account (Azure AD)</span></span>
    - <span data-ttu-id="65018-120">Eén of meerdere gebruikers per apparaat worden ondersteund.</span><span class="sxs-lookup"><span data-stu-id="65018-120">Single or multiple users per device is supported.</span></span>

:::image type="content" alt-text="Scenario voor verbonden cloud" source="./images/deployment-guides-revised-scenario-a.png" lightbox="./images/deployment-guides-revised-scenario-a.png":::


## <a name="learn-about-remote-assist"></a><span data-ttu-id="65018-122">Meer informatie over Remote Assist</span><span class="sxs-lookup"><span data-stu-id="65018-122">Learn about Remote Assist</span></span>

<span data-ttu-id="65018-123">Remote Assist kunt samenwerkend onderhoud en herstel, externe inspectie, evenals kennis delen en trainen.</span><span class="sxs-lookup"><span data-stu-id="65018-123">Remote Assist allows for collaborative maintenance and repair, remote inspection, as well as knowledge sharing and training.</span></span> <span data-ttu-id="65018-124">Door verbinding te maken met personen met verschillende rollen en locaties kan een technicus Remote Assist verbinding maken met een externe medewerker in Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="65018-124">By connecting people in different roles and locations a technician using Remote Assist can connect with a remote collaborator on Microsoft Teams.</span></span> <span data-ttu-id="65018-125">Ze kunnen video's, schermopnamen en aantekeningen combineren om problemen in realtime op te lossen, zelfs wanneer&#39;zich niet op dezelfde locatie bevinden.</span><span class="sxs-lookup"><span data-stu-id="65018-125">They can combine video, screenshots, and annotations to solve problems in real time even when they aren&#39;t in the same location.</span></span> <span data-ttu-id="65018-126">Externe samenwerkers kunnen referentieafbeeldingen, schema's en andere nuttige informatie invoegen die de technicus&#39;de fysieke ruimte, zodat ze kunnen verwijzen naar het schema tijdens het werken zonder kop en zonder problemen met HoloLens.</span><span class="sxs-lookup"><span data-stu-id="65018-126">Remote collaborators can insert reference images, schematics, and other helpful information the technician&#39;s physical space so they can refer to the schematic while working heads-up and hands-free on HoloLens.</span></span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="remote-assist-licensing-and-requirements"></a><span data-ttu-id="65018-127">Remote Assist licentieverlening en vereisten</span><span class="sxs-lookup"><span data-stu-id="65018-127">Remote Assist Licensing and Requirements</span></span>

- <span data-ttu-id="65018-128">Azure AD-account (vereist voor het kopen van het abonnement en het toewijzen van licenties)</span><span class="sxs-lookup"><span data-stu-id="65018-128">Azure AD account (required for purchasing the subscription and assigning licenses)</span></span>
- <span data-ttu-id="65018-129">[Remote Assist abonnement](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (of [Remote Assist proefversie](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist))</span><span class="sxs-lookup"><span data-stu-id="65018-129">[Remote Assist subscription](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (or [Remote Assist Trial](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist))</span></span>
    
#### <a name="dynamics-365-remote-assist-user"></a><span data-ttu-id="65018-130">Dynamics 365 Remote Assist gebruiker</span><span class="sxs-lookup"><span data-stu-id="65018-130">Dynamics 365 Remote Assist user</span></span>

- <span data-ttu-id="65018-131">Remote Assist licentie</span><span class="sxs-lookup"><span data-stu-id="65018-131">Remote Assist license</span></span>
- <span data-ttu-id="65018-132">Netwerkverbinding</span><span class="sxs-lookup"><span data-stu-id="65018-132">Network Connectivity</span></span>

#### <a name="microsoft-teams-user"></a><span data-ttu-id="65018-133">Microsoft Teams-gebruiker</span><span class="sxs-lookup"><span data-stu-id="65018-133">Microsoft Teams user</span></span>

- <span data-ttu-id="65018-134">Microsoft Teams of [Teams Freemium](https://products.office.com/microsoft-teams/free).</span><span class="sxs-lookup"><span data-stu-id="65018-134">Microsoft Teams or [Teams Freemium](https://products.office.com/microsoft-teams/free).</span></span>
- <span data-ttu-id="65018-135">Netwerkverbinding</span><span class="sxs-lookup"><span data-stu-id="65018-135">Network connectivity</span></span>

<span data-ttu-id="65018-136">Als u van plan bent dit scenario voor [verschillende tenants te implementeren,](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)hebt u mogelijk een licentie voor informatiebarrières nodig.</span><span class="sxs-lookup"><span data-stu-id="65018-136">If you plan on implementing this [cross-tenant scenario](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants), you may need an Information Barriers license.</span></span> <span data-ttu-id="65018-137">Zie [dit artikel om](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) te bepalen of een licentie voor een gegevensbarrière is vereist.</span><span class="sxs-lookup"><span data-stu-id="65018-137">See [this article](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) to determine if an Information Barrier License is required.</span></span>

## <a name="in-this-guide-you-will"></a><span data-ttu-id="65018-138">In deze handleiding gaat u het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="65018-138">In this guide you will:</span></span>

<span data-ttu-id="65018-139">Voorbereiden:</span><span class="sxs-lookup"><span data-stu-id="65018-139">Prepare:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="65018-140">Meer informatie over de essentiële infrastructuur voor HoloLens 2 apparaten.</span><span class="sxs-lookup"><span data-stu-id="65018-140">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [<span data-ttu-id="65018-141">Lees meer over Azure AD en stel er een in als&#39;niet hebt.</span><span class="sxs-lookup"><span data-stu-id="65018-141">Learn more about Azure AD and set up one if you don&#39;t have it.</span></span>](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [<span data-ttu-id="65018-142">Meer informatie over identiteitsbeheer en het instellen van Azure AD-accounts.</span><span class="sxs-lookup"><span data-stu-id="65018-142">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-cloud-connected-prepare.md#identity-management)
> - [<span data-ttu-id="65018-143">Meer informatie over MDM en instellen met Intune als&#39;er nog geen hebt.</span><span class="sxs-lookup"><span data-stu-id="65018-143">Learn more about MDM, and set up with Intune if you don&#39;t already have one ready.</span></span>](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [<span data-ttu-id="65018-144">Meer informatie over de netwerkvereisten van Remote Assist.</span><span class="sxs-lookup"><span data-stu-id="65018-144">Learn about the networking requirements of Remote Assist.</span></span>](hololens2-cloud-connected-prepare.md#network)
> - [<span data-ttu-id="65018-145">Optioneel: VPN om verbinding te maken met organisatiebronnen</span><span class="sxs-lookup"><span data-stu-id="65018-145">Optionally: VPN to connect to organizational resources</span></span>](hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

<span data-ttu-id="65018-146">Configureren:</span><span class="sxs-lookup"><span data-stu-id="65018-146">Configure:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="65018-147">Gebruikers en groepen maken.</span><span class="sxs-lookup"><span data-stu-id="65018-147">How to create Users and Groups.</span></span>](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [<span data-ttu-id="65018-148">Automatische inschrijving instellen in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="65018-148">How to set up Auto-enrollment within Azure AD.</span></span>](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [<span data-ttu-id="65018-149">Uw toepassingslicenties toewijzen.</span><span class="sxs-lookup"><span data-stu-id="65018-149">How to assign your Application licenses.</span></span>](hololens2-cloud-connected-configure.md#application-licenses)

<span data-ttu-id="65018-150">Implementatie:</span><span class="sxs-lookup"><span data-stu-id="65018-150">Deploy:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="65018-151">Stel uw HoloLens 2 en valideer de inschrijving.</span><span class="sxs-lookup"><span data-stu-id="65018-151">Set up your HoloLens 2 and validate enrollment.</span></span>](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [<span data-ttu-id="65018-152">Controleer of u een aanroep Remote Assist maken.</span><span class="sxs-lookup"><span data-stu-id="65018-152">Validate you can make a Remote Assist call.</span></span>](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

<span data-ttu-id="65018-153">Handhaven:</span><span class="sxs-lookup"><span data-stu-id="65018-153">Maintain:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="65018-154">Informatie over het bijwerken Remote Assist de Microsoft Store app.</span><span class="sxs-lookup"><span data-stu-id="65018-154">How to update Remote Assist using the Microsoft Store app.</span></span>](hololens2-cloud-connected-maintain.md#updates)
> - [<span data-ttu-id="65018-155">Een ondersteuningsplan maken.</span><span class="sxs-lookup"><span data-stu-id="65018-155">Making a support plan.</span></span>](hololens2-cloud-connected-maintain.md#support-plan)
> - [<span data-ttu-id="65018-156">Ontwikkelplan.</span><span class="sxs-lookup"><span data-stu-id="65018-156">Development plan.</span></span>](hololens2-cloud-connected-maintain.md#development-plan)

## <a name="next-step"></a><span data-ttu-id="65018-157">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="65018-157">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="65018-158">Cloudgeconnecteerde implementatie - Voorbereiden</span><span class="sxs-lookup"><span data-stu-id="65018-158">Cloud connected deployment - Prepare</span></span>](hololens2-cloud-connected-prepare.md)

