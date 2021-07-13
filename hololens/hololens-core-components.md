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
# <a name="planning-hololens-2-deployment-in-a-commercial-environment"></a><span data-ttu-id="6ea74-103">Implementatie HoloLens 2 in een commerciële omgeving plannen</span><span class="sxs-lookup"><span data-stu-id="6ea74-103">Planning HoloLens 2 deployment in a commercial environment</span></span>

## <a name="overview"></a><span data-ttu-id="6ea74-104">Overzicht</span><span class="sxs-lookup"><span data-stu-id="6ea74-104">Overview</span></span>

> [!NOTE]
> <span data-ttu-id="6ea74-105">Dit overzicht is bedoeld om IT-professionals inzicht te geven in overwegingen voor het implementeren en beheren Microsoft HoloLens 2 apparaten binnen een organisatie.</span><span class="sxs-lookup"><span data-stu-id="6ea74-105">This overview is intended to help IT professionals understand considerations for deploying and managing Microsoft HoloLens 2 devices within an organization.</span></span> <span data-ttu-id="6ea74-106">Zie Get your HoloLens 2 ready to use to get started (Uw apparaat voorbereiden om aan de slag [te gaan) voor](hololens2-setup.md) eindgebruikers van apparaten.</span><span class="sxs-lookup"><span data-stu-id="6ea74-106">For device end users, see [Get your HoloLens 2 ready to use](hololens2-setup.md) to get started.</span></span>

<span data-ttu-id="6ea74-107">HoloLens 2 wordt uitgevoerd op Windows 10 Holographic waarmee organisaties robuuste, flexibele, ingebouwde technologieën voor het beheer van mobiele apparaten en apps kunnen gebruiken.</span><span class="sxs-lookup"><span data-stu-id="6ea74-107">HoloLens 2 runs on Windows 10 Holographic which provides organizations with robust, flexible, built-in mobile device and app management technologies.</span></span> <span data-ttu-id="6ea74-108">Windows 10 Holographic biedt ondersteuning voor end-to-end levenscyclusbeheer van apparaten, om bedrijven controle te geven over hun apparaten, gegevens en apps.</span><span class="sxs-lookup"><span data-stu-id="6ea74-108">Windows 10 Holographic supports end-to-end device lifecycle management to give companies control over their devices, data, and apps.</span></span> <span data-ttu-id="6ea74-109">De HoloLens 2 kunnen eenvoudig worden opgenomen in standaard levenscyclusprocedures, van apparaatinschrijving, configuratie en toepassingsbeheer tot onderhoud en pensioen met behulp van een uitgebreide beheeroplossing voor mobiele apparaten.</span><span class="sxs-lookup"><span data-stu-id="6ea74-109">The HoloLens 2 can easily be incorporated into standard lifecycle practices, from device enrollment, configuration, and application management to maintenance and retirement using a comprehensive mobile device management solution.</span></span>

<span data-ttu-id="6ea74-110">De volgende stappen en video kunnen u helpen bij het doorlopen van HoloLens 2 ingebruikname binnen uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="6ea74-110">The following steps and video can help guide you through the process of HoloLens 2 adoption within your organization.</span></span>

| &nbsp; | &nbsp; |
|--|--|
| ![Stap 1](images/1green.png)| <br/> <span data-ttu-id="6ea74-112">**[Algemene implementatiescenario's:](hololens-requirements.md)** inzicht in implementatiescenario's en verken de belangrijkste onderdelen die nodig zijn om HoloLens 2 implementeren.</span><span class="sxs-lookup"><span data-stu-id="6ea74-112">**[Common Deployment Scenarios](hololens-requirements.md)**: Understand deployment scenarios and explore the core components needed to deploy HoloLens 2 devices.</span></span> |
| ![Stap 2](images/2green.png)| <br/> <span data-ttu-id="6ea74-114">**[Voorbereiden:](#prepare)** vertrouwd raken met de infrastructuur essentials die nodig zijn voor HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="6ea74-114">**[Prepare](#prepare)**: Become familiar with the infrastructure essentials needed for HoloLens 2.</span></span> |
| ![Stap 3](images/3green.png) | <br/> <span data-ttu-id="6ea74-116">**[Configureren:](#configure)** meer informatie over het configureren van uw essentiële onderdelen voor een cloudimplementatie.</span><span class="sxs-lookup"><span data-stu-id="6ea74-116">**[Configure](#configure)**: Learn how to configure your essential components for a cloud-based deployment.</span></span> |
| ![Stap 4](images/4green.png) | <br/> <span data-ttu-id="6ea74-118">**[Implementeren:](#deploy)** ontdek hoe u uw apparaten implementeert en uw toepassingen veilig en efficiënt distribueert.</span><span class="sxs-lookup"><span data-stu-id="6ea74-118">**[Deploy](#deploy)**: Discover how to deploy your devices and distribute your applications securely and efficiently.</span></span> |
| ![Stap 5](images/5green.png) | <br/> <span data-ttu-id="6ea74-120">**[Onderhouden:](#maintain)** ontdek wat er nodig is om de status van uw apparaten HoloLens 2 te onderhouden en naleving van het bedrijfsbeleid te garanderen.</span><span class="sxs-lookup"><span data-stu-id="6ea74-120">**[Maintain](#maintain)**: Find out what's needed to properly maintain the state of your HoloLens 2 devices and ensure compliance with corporate policy.</span></span> |

<br/>

> [!VIDEO https://channel9.msdn.com/Shows/IT-Ops-Talk/HoloLens-2-Deployment-Overview/player]

## <a name="prepare"></a><span data-ttu-id="6ea74-121">Voorbereiden</span><span class="sxs-lookup"><span data-stu-id="6ea74-121">Prepare</span></span>

<span data-ttu-id="6ea74-122">Meer informatie over essentiële infrastructuurservices die nodig zijn om de volledige set HoloLens 2 ondersteunen.</span><span class="sxs-lookup"><span data-stu-id="6ea74-122">Learn about essential infrastructure services required to support the full set of HoloLens 2 capabilities.</span></span>

| <span data-ttu-id="6ea74-123">Onderdeel</span><span class="sxs-lookup"><span data-stu-id="6ea74-123">Component</span></span> | <span data-ttu-id="6ea74-124">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="6ea74-124">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="6ea74-125">Azure AD</span><span class="sxs-lookup"><span data-stu-id="6ea74-125">Azure AD</span></span>](hololens-identity.md) | <span data-ttu-id="6ea74-126">Biedt identiteits- en toegangsbeheer voor de HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="6ea74-126">Provides identity and access management for the HoloLens 2</span></span>  |
| [<span data-ttu-id="6ea74-127">Beheer van mobiele apparaten</span><span class="sxs-lookup"><span data-stu-id="6ea74-127">Mobile Device Management</span></span>](hololens-mdm-configure.md)| <span data-ttu-id="6ea74-128">Beheert HoloLens 2 apparaten die zijn verbonden met uw tenant</span><span class="sxs-lookup"><span data-stu-id="6ea74-128">Manages HoloLens 2 devices connected to your tenant</span></span>  |
| [<span data-ttu-id="6ea74-129">Wi-Fi-netwerk</span><span class="sxs-lookup"><span data-stu-id="6ea74-129">Wi-Fi Network</span></span>](hololens-commercial-infrastructure.md)| <span data-ttu-id="6ea74-130">Wi-Fi beschikbaar is en apparaten kunnen worden verbonden met internet</span><span class="sxs-lookup"><span data-stu-id="6ea74-130">Wi-Fi is available and devices can be connected to the Internet</span></span>  |

## <a name="configure"></a><span data-ttu-id="6ea74-131">Configureren</span><span class="sxs-lookup"><span data-stu-id="6ea74-131">Configure</span></span>

<span data-ttu-id="6ea74-132">Gebruik Intune en Autopilot als low-touch-oplossingen voor het registreren en configureren HoloLens 2 de Azure AD-tenant en MDM van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="6ea74-132">Use Intune and Autopilot as low-touch solutions for enrolling and configuring HoloLens 2 to your organization’s Azure AD tenant and MDM.</span></span>

| <span data-ttu-id="6ea74-133">Onderdeel</span><span class="sxs-lookup"><span data-stu-id="6ea74-133">Component</span></span> | <span data-ttu-id="6ea74-134">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="6ea74-134">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="6ea74-135">Automatische inschrijving</span><span class="sxs-lookup"><span data-stu-id="6ea74-135">Auto Enrollment</span></span>](hololens-enroll-mdm.md#auto-enrollment-in-mdm) | <span data-ttu-id="6ea74-136">Na de eerste aanmelding registreren apparaten zich automatisch bij Azure AD en registreren ze zich bij MDM</span><span class="sxs-lookup"><span data-stu-id="6ea74-136">After initial login, devices automatically register with Azure AD and enroll into MDM</span></span>  |
| [<span data-ttu-id="6ea74-137">Toepassingslicenties</span><span class="sxs-lookup"><span data-stu-id="6ea74-137">Application Licenses</span></span>](hololens2-cloud-connected-configure.md#application-licenses)| <span data-ttu-id="6ea74-138">Kan worden toegepast op gebruikers, gebruikersgroepen of apparaatgroepen</span><span class="sxs-lookup"><span data-stu-id="6ea74-138">Can be applied to either users, user groups, or device groups</span></span>  |
| [<span data-ttu-id="6ea74-139">Azure-gebruikers en -groepen</span><span class="sxs-lookup"><span data-stu-id="6ea74-139">Azure Users and Groups</span></span>](hololens2-cloud-connected-configure.md#azure-users-and-groups) | <span data-ttu-id="6ea74-140">Helpt bij het toewijzen van configuraties en licenties voor de HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="6ea74-140">Helps assign configurations and licenses for the HoloLens 2</span></span>  |

## <a name="deploy"></a><span data-ttu-id="6ea74-141">Implementeren</span><span class="sxs-lookup"><span data-stu-id="6ea74-141">Deploy</span></span>

<span data-ttu-id="6ea74-142">Distribueer uw HoloLens 2 apparaten en valideer de configuratie.</span><span class="sxs-lookup"><span data-stu-id="6ea74-142">Distribute your HoloLens 2 devices and validate their configuration.</span></span> 

| <span data-ttu-id="6ea74-143">Onderdeel</span><span class="sxs-lookup"><span data-stu-id="6ea74-143">Component</span></span> | <span data-ttu-id="6ea74-144">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="6ea74-144">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="6ea74-145">Validatie van inschrijving</span><span class="sxs-lookup"><span data-stu-id="6ea74-145">Enrollment Validation</span></span>](hololens2-corp-connected-deploy.md#enrollment-validation) | <span data-ttu-id="6ea74-146">Controleer of het apparaat is samengevoegd met Azure AD vanuit Instellingen of de Azure-portal</span><span class="sxs-lookup"><span data-stu-id="6ea74-146">Validate the device has Azure AD Joined from Settings or the Azure Portal</span></span> |
| [<span data-ttu-id="6ea74-147">Certificaatvalidatie</span><span class="sxs-lookup"><span data-stu-id="6ea74-147">Certificate Validation</span></span>](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation) | <span data-ttu-id="6ea74-148">Controleer de instellingen en controleer of ze correct zijn gedistribueerd</span><span class="sxs-lookup"><span data-stu-id="6ea74-148">Check settings and validate they have been distributed correctly</span></span> |
| [<span data-ttu-id="6ea74-149">App-installaties valideren</span><span class="sxs-lookup"><span data-stu-id="6ea74-149">Validate app installs</span></span>](hololens2-corp-connected-deploy.md#validate-lob-app-install) | <span data-ttu-id="6ea74-150">Controleer of de app aanwezig is en aan uw HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="6ea74-150">Confirm the app is present and working on your HoloLens 2</span></span> |

## <a name="maintain"></a><span data-ttu-id="6ea74-151">Onderhouden</span><span class="sxs-lookup"><span data-stu-id="6ea74-151">Maintain</span></span>

<span data-ttu-id="6ea74-152">Gebruik Windows Update voor Bedrijven samen met uw MDM-systeem of de Microsoft Store om uw HoloLens 2 apps bij te werken.</span><span class="sxs-lookup"><span data-stu-id="6ea74-152">Use Windows Update for Business along with your MDM system or the Microsoft Store to keep your fleet of HoloLens 2 and apps updated.</span></span>

| <span data-ttu-id="6ea74-153">Onderdeel</span><span class="sxs-lookup"><span data-stu-id="6ea74-153">Component</span></span> | <span data-ttu-id="6ea74-154">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="6ea74-154">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="6ea74-155">Werk HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="6ea74-155">Update HoloLens 2</span></span>](hololens-updates.md) | <span data-ttu-id="6ea74-156">Configureer updates naar behoefte via Windows Updates voor Bedrijven</span><span class="sxs-lookup"><span data-stu-id="6ea74-156">Configure updates as needed through Windows Updates for Business</span></span> |
| [<span data-ttu-id="6ea74-157">Apps bijwerken</span><span class="sxs-lookup"><span data-stu-id="6ea74-157">Update apps</span></span>](app-deploy-overview.md) | <span data-ttu-id="6ea74-158">Configureren via uw MDM-systeem of de Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="6ea74-158">Configure through your MDM system or the Microsoft Store</span></span>
