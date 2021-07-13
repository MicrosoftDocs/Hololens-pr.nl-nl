---
title: 'Implementatiehandleiding : Zakelijk verbonden HoloLens 2 met Dynamics 365 Guides - Overzicht'
description: Meer informatie over het inschrijven HoloLens 2 apparaten met Dynamics 365 Guides via een verbonden bedrijfsnetwerk.
keywords: HoloLens, beheer, zakelijk verbonden, Dynamics 365 Guides, AAD, Azure AD, MDM, Mobile Device Management
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: f2f7e1425a208e1f466d995f66118b7e68984242
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/12/2021
ms.locfileid: "113637010"
---
# <a name="deployment-guide---corporate-connected-hololens-2-with-dynamics-365-guides---overview"></a><span data-ttu-id="7a308-104">Implementatiehandleiding - Bedrijfsgeconnecteerde HoloLens 2 met Dynamics 365 Guides - Overzicht</span><span class="sxs-lookup"><span data-stu-id="7a308-104">Deployment Guide - Corporate Connected HoloLens 2 with Dynamics 365 Guides - Overview</span></span>

<span data-ttu-id="7a308-105">Deze handleiding helpt IT-professionals bij het plannen en implementeren van Microsoft HoloLens 2 apparaten met Dynamics 365 Guides (Guides) in hun organisatie.</span><span class="sxs-lookup"><span data-stu-id="7a308-105">This guide will help IT professionals plan for and deploy Microsoft HoloLens 2 devices with Dynamics 365 Guides (Guides) to their organization.</span></span> <span data-ttu-id="7a308-106">Deze handleiding is geweldig voor zowel gidsen als productie-implementaties en is vergelijkbaar met [scenario B: Implementeren binnen](/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) de netwerkhandleiding van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="7a308-106">This guide is great for pilots as well as production deployments and is similar to the [Scenario B: Deploy inside your organization's network](/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) guide.</span></span> <span data-ttu-id="7a308-107">Nadat u uw proof-of-concept hebt getest, gebruikt u deze handleiding om verder te gaan met het integreren HoloLens in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="7a308-107">After testing your proof-of-concept, use this guide to move forward with integrating HoloLens into your organization.</span></span>

<span data-ttu-id="7a308-108">In deze handleiding wordt begrensd hoe u uw apparaten kunt registreren bij uw bestaande apparaatbeheer, licenties kunt toepassen als dat nodig is, en hoe u valideert dat uw eindgebruikers een Dynamics 365-handleiding kunnen gebruiken, en hoe u aangepaste Line-Of-Business-apps kunt gebruiken nadat het apparaat is ingesteld.</span><span class="sxs-lookup"><span data-stu-id="7a308-108">In this guide, we will cover how to enroll your devices into your existing device management, apply licenses as needed, and validate that your end users are able to operate a Dynamics 365 Guide, as well as use custom line of business apps, after device set up.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="7a308-109">Vereisten</span><span class="sxs-lookup"><span data-stu-id="7a308-109">Prerequisites</span></span>

<span data-ttu-id="7a308-110">De volgende infrastructuur moet al zijn gebruikt:</span><span class="sxs-lookup"><span data-stu-id="7a308-110">The following infrastructure should already be in place:</span></span>
- <span data-ttu-id="7a308-111">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="7a308-111">Wi-Fi</span></span>
    - <span data-ttu-id="7a308-112">Intern bedrijfsnetwerk met toegang tot interne resources en beperkte toegang tot internet of cloudservices</span><span class="sxs-lookup"><span data-stu-id="7a308-112">Internal corporate network with access to internal resources and limited access to the internet or Cloud services</span></span>
    - <span data-ttu-id="7a308-113">Verificatie op basis van apparaatcertificaten.</span><span class="sxs-lookup"><span data-stu-id="7a308-113">Device-based certificate authentication.</span></span>
- <span data-ttu-id="7a308-114">Azure Active Directory (Azure AD) Deelnemen met automatische MDM-inschrijving[(Azure AD P1-abonnement](/azure/active-directory/fundamentals/active-directory-whatis) vereist)</span><span class="sxs-lookup"><span data-stu-id="7a308-114">Azure Active Directory (Azure AD) Join with MDM Auto Enrollment ([Azure AD P1 subscription](/azure/active-directory/fundamentals/active-directory-whatis) needed)</span></span>
- <span data-ttu-id="7a308-115">MDM (Intune) Beheerd</span><span class="sxs-lookup"><span data-stu-id="7a308-115">MDM (Intune) Managed</span></span>
    - <span data-ttu-id="7a308-116">Een of meer toepassingen worden geïmplementeerd via MDM.</span><span class="sxs-lookup"><span data-stu-id="7a308-116">One or more applications are deployed via MDM.</span></span>
- <span data-ttu-id="7a308-117">Netwerk</span><span class="sxs-lookup"><span data-stu-id="7a308-117">Network</span></span> 
    - <span data-ttu-id="7a308-118">Certificaten (SCEP of PKCS)</span><span class="sxs-lookup"><span data-stu-id="7a308-118">Certificates (SCEP or PKCS)</span></span>
    - <span data-ttu-id="7a308-119">Proxyconfiguratie</span><span class="sxs-lookup"><span data-stu-id="7a308-119">Proxy configuration</span></span>
- <span data-ttu-id="7a308-120">Gebruikers melden zich aan met hun eigen bedrijfsaccount (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="7a308-120">Users sign in with their own corporate account (Azure AD)</span></span>
    - <span data-ttu-id="7a308-121">Eén of meerdere gebruikers per apparaat wordt ondersteund.</span><span class="sxs-lookup"><span data-stu-id="7a308-121">Single or multiple users per device is supported.</span></span>
- <span data-ttu-id="7a308-122">Verschillende niveaus van vergrendelingsconfiguraties voor apparaten die worden toegepast op basis van specifieke gebruiksgevallen, van Volledig geopend tot Kiosk voor één app.</span><span class="sxs-lookup"><span data-stu-id="7a308-122">Varying levels of device lockdown configurations applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>

## <a name="guides-licensing-and-requirements"></a>[<span data-ttu-id="7a308-123">Handleidingen licentieverlening en vereisten</span><span class="sxs-lookup"><span data-stu-id="7a308-123">Guides Licensing and Requirements</span></span>](/dynamics365/mixed-reality/guides/requirements#licensing-and-product-requirements)

- <span data-ttu-id="7a308-124">Azure AD-account</span><span class="sxs-lookup"><span data-stu-id="7a308-124">Azure AD account</span></span>
- <span data-ttu-id="7a308-125">Dynamics 365 Guides-pc en HoloLens</span><span class="sxs-lookup"><span data-stu-id="7a308-125">Dynamics 365 Guides applications PC and HoloLens</span></span>
- <span data-ttu-id="7a308-126">Dynamics 365 Guides abonnement</span><span class="sxs-lookup"><span data-stu-id="7a308-126">Dynamics 365 Guides subscription</span></span>
    - <span data-ttu-id="7a308-127">Microsoft Dataverse (inbegrepen)</span><span class="sxs-lookup"><span data-stu-id="7a308-127">Microsoft Dataverse (included)</span></span>
    - <span data-ttu-id="7a308-128">Power Apps (inbegrepen)</span><span class="sxs-lookup"><span data-stu-id="7a308-128">Power Apps (included)</span></span>
- <span data-ttu-id="7a308-129">Power BI Desktop</span><span class="sxs-lookup"><span data-stu-id="7a308-129">Power BI Desktop</span></span>
- <span data-ttu-id="7a308-130">Netwerkverbinding</span><span class="sxs-lookup"><span data-stu-id="7a308-130">Network Connectivity</span></span>

<span data-ttu-id="7a308-131">[![Diagram van verbonden corp-netwerk, fase 1 ](./images/deployment-guides-revised-scenario-b-01-1.png)](./images/deployment-guides-revised-scenario-b-01-1.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="7a308-131">[ ![Corp connected network diagram, stage 1](./images/deployment-guides-revised-scenario-b-01-1.png) ](./images/deployment-guides-revised-scenario-b-01-1.png#lightbox)</span></span>

<span data-ttu-id="7a308-132">[![Diagram van met corp verbonden netwerk, fase 2 ](./images/deployment-guides-revised-scenario-b-02-1.png)](./images/deployment-guides-revised-scenario-b-02-1.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="7a308-132">[ ![Corp connected network diagram, stage 2](./images/deployment-guides-revised-scenario-b-02-1.png) ](./images/deployment-guides-revised-scenario-b-02-1.png#lightbox)</span></span>

## <a name="in-this-guide-you-will"></a><span data-ttu-id="7a308-133">In deze handleiding gaat u het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="7a308-133">In this guide you will:</span></span>
### <a name="prepare"></a><span data-ttu-id="7a308-134">Voorbereiden</span><span class="sxs-lookup"><span data-stu-id="7a308-134">Prepare</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="7a308-135">Meer informatie over de essentiële infrastructuur voor HoloLens 2 apparaten.</span><span class="sxs-lookup"><span data-stu-id="7a308-135">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-corp-connected-prepare.md#infrastructure-essentials)
>- [<span data-ttu-id="7a308-136">Lees meer over Azure AD en stel er een in als u deze nog niet hebt.</span><span class="sxs-lookup"><span data-stu-id="7a308-136">Learn more about Azure AD and set up one if you don't have it.</span></span>](hololens2-corp-connected-prepare.md#azure-active-directory)
>- [<span data-ttu-id="7a308-137">Meer informatie over identiteitsbeheer en het instellen van Azure AD-accounts.</span><span class="sxs-lookup"><span data-stu-id="7a308-137">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-corp-connected-prepare.md#identity-management)
>- [<span data-ttu-id="7a308-138">Meer informatie over MDM en instellen met Intune als u er nog geen hebt.</span><span class="sxs-lookup"><span data-stu-id="7a308-138">Learn more about MDM and set up with Intune if you don't already have one ready.</span></span>](hololens2-corp-connected-prepare.md#mobile-device-management)
>- [<span data-ttu-id="7a308-139">Vertrouwd raken met Wi-Fi op basis van certificaten.</span><span class="sxs-lookup"><span data-stu-id="7a308-139">Familiarize yourself with certificate-based Wi-Fi.</span></span>](hololens2-corp-connected-prepare.md#certificates)
>- [<span data-ttu-id="7a308-140">Vertrouwd raken met Proxy.</span><span class="sxs-lookup"><span data-stu-id="7a308-140">Familiarize yourself with Proxy.</span></span>](hololens2-corp-connected-prepare.md#proxy)
>- [<span data-ttu-id="7a308-141">Meer informatie over hoe u Line-Of-Business-apps kunt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="7a308-141">Understand how you can use Line of Business Apps.</span></span>](hololens2-corp-connected-prepare.md#line-of-business-apps)
>- [<span data-ttu-id="7a308-142">Meer informatie over de manier waarop u handleidingen voor uw organisatie kunt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="7a308-142">Learn more about the way you can use Guides for your organization.</span></span>](hololens2-corp-connected-prepare.md#guides-playbook)
### <a name="configure"></a><span data-ttu-id="7a308-143">Configureren</span><span class="sxs-lookup"><span data-stu-id="7a308-143">Configure</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="7a308-144">Gebruikers en groepen maken.</span><span class="sxs-lookup"><span data-stu-id="7a308-144">How to create users and groups.</span></span>](hololens2-corp-connected-configure.md#azure-users-and-groups)
>- [<span data-ttu-id="7a308-145">Automatische inschrijving instellen.</span><span class="sxs-lookup"><span data-stu-id="7a308-145">How to set up Auto Enrollment.</span></span>](hololens2-corp-connected-configure.md#auto-enrollment-on-hololens-2)
>- [<span data-ttu-id="7a308-146">How to set up Wi-Fi certificates and profiles for Corporate Wi-Fi Connectivity.</span><span class="sxs-lookup"><span data-stu-id="7a308-146">How to set up Wi-Fi certificates and profiles for Corporate Wi-Fi Connectivity.</span></span>](hololens2-corp-connected-configure.md#corporate-wi-fi-connectivity)
>- [<span data-ttu-id="7a308-147">Upload lob-app-pakketten (Line-Of-Business) toewijzen.</span><span class="sxs-lookup"><span data-stu-id="7a308-147">Upload and Assign Line of Business (LOB) App packages.</span></span>](hololens2-corp-connected-configure.md#app-deployment)
>- [<span data-ttu-id="7a308-148">Stel Dynamics 365 Guides.</span><span class="sxs-lookup"><span data-stu-id="7a308-148">Setup Dynamics 365 Guides.</span></span>](hololens2-corp-connected-configure.md#setup-guides-application-licenses-dataverse-and-authoring)
>- [<span data-ttu-id="7a308-149">Kioskmodus configureren (optioneel).</span><span class="sxs-lookup"><span data-stu-id="7a308-149">How to configure Kiosk Mode (optional).</span></span>](hololens2-corp-connected-configure.md#optional-kiosk-mode)
>- [<span data-ttu-id="7a308-150">WDAC configureren (optioneel).</span><span class="sxs-lookup"><span data-stu-id="7a308-150">How to configure WDAC (optional).</span></span>](hololens2-corp-connected-configure.md#optional-wdac)
### <a name="deploy"></a><span data-ttu-id="7a308-151">Implementeren</span><span class="sxs-lookup"><span data-stu-id="7a308-151">Deploy</span></span>
> [!div class="checklist"]
>-  [<span data-ttu-id="7a308-152">Valideer de inschrijving via apparaat en MDM.</span><span class="sxs-lookup"><span data-stu-id="7a308-152">Validate enrollment via device and MDM.</span></span>](hololens2-corp-connected-deploy.md#enrollment-validation)
>-  [<span data-ttu-id="7a308-153">Valideer Wi-Fi certificaten.</span><span class="sxs-lookup"><span data-stu-id="7a308-153">Validate Wi-Fi certificates.</span></span>](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation)
>-  [<span data-ttu-id="7a308-154">Valideer de installatie van LOB-apps.</span><span class="sxs-lookup"><span data-stu-id="7a308-154">Validate LOB app install.</span></span>](hololens2-corp-connected-deploy.md#validate-lob-app-install)
>-  [<span data-ttu-id="7a308-155">Valideer handleidingen via ontwerp en gebruik.</span><span class="sxs-lookup"><span data-stu-id="7a308-155">Validate Guides via authoring and operating.</span></span>](hololens2-corp-connected-deploy.md#validate-dynamics-365-guides)
### <a name="maintain"></a><span data-ttu-id="7a308-156">Onderhouden</span><span class="sxs-lookup"><span data-stu-id="7a308-156">Maintain</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="7a308-157">Werk HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="7a308-157">Update HoloLens 2.</span></span>](hololens2-corp-connected-maintain.md#update-hololens)
>- [<span data-ttu-id="7a308-158">Handleidingen bijwerken (Store-apps).</span><span class="sxs-lookup"><span data-stu-id="7a308-158">How to update Guides (store apps).</span></span>](hololens2-corp-connected-maintain.md#how-to-update-dynamics-365-guides-and-other-store-apps)
>- [<span data-ttu-id="7a308-159">LOB-apps bijwerken.</span><span class="sxs-lookup"><span data-stu-id="7a308-159">How to update LOB apps.</span></span>](hololens2-corp-connected-maintain.md#how-to-update-lob-apps) 
>- [<span data-ttu-id="7a308-160">Ontwikkelplan.</span><span class="sxs-lookup"><span data-stu-id="7a308-160">Development plan.</span></span>](hololens2-corp-connected-maintain.md#development-plan) 
>- [<span data-ttu-id="7a308-161">Een ondersteuningsplan maken.</span><span class="sxs-lookup"><span data-stu-id="7a308-161">Making a support plan.</span></span>](hololens2-corp-connected-maintain.md#support-plan)
>- [<span data-ttu-id="7a308-162">Opties voor apparaatbeheer.</span><span class="sxs-lookup"><span data-stu-id="7a308-162">Device management options.</span></span>](hololens2-corp-connected-maintain.md#device-management)

## <a name="next-step"></a><span data-ttu-id="7a308-163">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="7a308-163">Next step</span></span> 
> [!div class="nextstepaction"]
> [<span data-ttu-id="7a308-164">Zakelijke verbonden implementatie - Voorbereiden</span><span class="sxs-lookup"><span data-stu-id="7a308-164">Corporate connected deployment - Prepare</span></span>](hololens2-corp-connected-prepare.md)
