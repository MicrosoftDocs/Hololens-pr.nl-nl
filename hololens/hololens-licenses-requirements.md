---
title: Licentievereisten
description: Blijf op de hoogte van alle licentievereisten en richtlijnen die u nodig hebt voor het beheer van mobiele apparaten, HoloLens en Remote Assist.
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
audience: HoloLens
ms.topic: article
ms.localizationpriority: high
ms.date: 1/23/2020
ms.reviewer: ''
manager: bradke
appliesto:
- HoloLens 2
ms.openlocfilehash: d0d8aa648df7901dec8636942e43aa549e626d7e
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635888"
---
# <a name="license-requirements"></a><span data-ttu-id="4f8de-103">Licentievereisten</span><span class="sxs-lookup"><span data-stu-id="4f8de-103">License requirements</span></span>

## <a name="hololens-2-device-managed"></a><span data-ttu-id="4f8de-104">HoloLens 2 Apparaat (beheerd)</span><span class="sxs-lookup"><span data-stu-id="4f8de-104">HoloLens 2 Device (managed)</span></span>

[<span data-ttu-id="4f8de-105">Azure AD-account</span><span class="sxs-lookup"><span data-stu-id="4f8de-105">Azure AD Account</span></span>](https://docs.microsoft.com/azure/active-directory/)

> [!IMPORTANT]
> <span data-ttu-id="4f8de-106">Active Directory (AD) kan niet worden gebruikt voor het beheren van HoloLens apparaten.</span><span class="sxs-lookup"><span data-stu-id="4f8de-106">Active Directory (AD) cannot be used to manage HoloLens devices.</span></span>

<span data-ttu-id="4f8de-107">[Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) of een andere MDM.</span><span class="sxs-lookup"><span data-stu-id="4f8de-107">[Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) or another MDM.</span></span>
- <span data-ttu-id="4f8de-108">[Windows Autopilot voor HoloLens 2](hololens2-autopilot.md)vereenvoudigt de inrichtingservaring voor zowel IT-beheerders als eindgebruikers.</span><span class="sxs-lookup"><span data-stu-id="4f8de-108">[Windows Autopilot for HoloLens 2](hololens2-autopilot.md)- simplifies the provisioning experience for both IT admins and end users.</span></span> <span data-ttu-id="4f8de-109">IT-beheerders kunnen vooraf HoloLens 2 configureren en bij de eerste keer opstarten worden apparaten geïmplementeerd in een bedrijfsconfig status zonder tussenkomst van de eindgebruiker.</span><span class="sxs-lookup"><span data-stu-id="4f8de-109">IT admins can preconfigure HoloLens 2 policies, and upon first boot, devices will be deployed in business-ready state with zero end-user interaction.</span></span> 

  > [!NOTE]
  > <span data-ttu-id="4f8de-110">Windows Autopilot vereist [dat Azure P1](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) en [Automatische](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment) inschrijving eerst worden geconfigureerd voor de Autopilot-stroom met weinig aanraking en apparaatimplementatie.</span><span class="sxs-lookup"><span data-stu-id="4f8de-110">Windows Autopilot requires [Azure P1](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) and [Auto-enrollment](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment) to be configured first for the low-touch Autopilot flow and device deployment.</span></span> 

### <a name="business-use-case"></a><span data-ttu-id="4f8de-111">Bedrijfsgebruikscase:</span><span class="sxs-lookup"><span data-stu-id="4f8de-111">Business Use Case:</span></span> 

- <span data-ttu-id="4f8de-112">[Implementatiescenario A:](hololens-requirements.md#scenario-a-deploy-to-cloud-connected-devices) proof-of-concept of testimplementatie.</span><span class="sxs-lookup"><span data-stu-id="4f8de-112">[Deployment Scenario A](hololens-requirements.md#scenario-a-deploy-to-cloud-connected-devices) - proof-of-concept or pilot deployment.</span></span>

- <span data-ttu-id="4f8de-113">[Implementatiescenario B:](hololens-requirements.md#scenario-b-deploy-inside-your-organizations-network) implementatie op schaal.</span><span class="sxs-lookup"><span data-stu-id="4f8de-113">[Deployment Scenario B](hololens-requirements.md#scenario-b-deploy-inside-your-organizations-network) - deployment at scale.</span></span>

## <a name="hololens-2-device-only-non-managed"></a><span data-ttu-id="4f8de-114">HoloLens 2 Alleen apparaat (niet-beheerd)</span><span class="sxs-lookup"><span data-stu-id="4f8de-114">HoloLens 2 Device-only (non-managed)</span></span>

<span data-ttu-id="4f8de-115">Wanneer u een Microsoft-account (MSA) of een lokaal account gebruikt, zijn er geen extra licenties vereist voor deze accounts.</span><span class="sxs-lookup"><span data-stu-id="4f8de-115">When using either a Microsoft Account (MSA) or Local account no additional licenses are required for these accounts.</span></span>

[<span data-ttu-id="4f8de-116">Lokaal account</span><span class="sxs-lookup"><span data-stu-id="4f8de-116">Local Account</span></span>](https://docs.microsoft.com/windows/security/identity-protection/access-control/local-accounts)

- <span data-ttu-id="4f8de-117">Dit account moet [van tevoren worden ingericht](hololens-provisioning.md#provisioning-package-hololens-wizard) met Windows Configuration Designer (WCD).</span><span class="sxs-lookup"><span data-stu-id="4f8de-117">This account must be [provisioned](hololens-provisioning.md#provisioning-package-hololens-wizard) ahead of time with Windows Configuration Designer (WCD).</span></span>

[<span data-ttu-id="4f8de-118">Microsoft-account (MSA)</span><span class="sxs-lookup"><span data-stu-id="4f8de-118">Microsoft Account (MSA)</span></span>](https://docs.microsoft.com/windows/security/identity-protection/access-control/microsoft-accounts)

> [!WARNING]
> <span data-ttu-id="4f8de-119">Meerdere gebruikers worden niet ondersteund voor een apparaat dat een van deze accounts gebruikt.</span><span class="sxs-lookup"><span data-stu-id="4f8de-119">Multiple users are not supported for a device using either of these accounts.</span></span>

### <a name="business-use-case"></a><span data-ttu-id="4f8de-120">Bedrijfsgebruikscase:</span><span class="sxs-lookup"><span data-stu-id="4f8de-120">Business Use Case:</span></span> 

- <span data-ttu-id="4f8de-121">[Implementatiescenario C:](hololens-requirements.md#scenario-c-deploy-in-secure-offline-environment) offline of beveiligde implementatie.</span><span class="sxs-lookup"><span data-stu-id="4f8de-121">[Deployment Scenario C](hololens-requirements.md#scenario-c-deploy-in-secure-offline-environment) - offline or secure deployment.</span></span>
 
## <a name="dynamics-365-licensing-and-requirements"></a><span data-ttu-id="4f8de-122">Licenties en vereisten voor Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="4f8de-122">Dynamics 365 Licensing and Requirements</span></span>

### <a name="dynamics-365-remote-assist"></a><span data-ttu-id="4f8de-123">Dynamics 365 Remote Assist</span><span class="sxs-lookup"><span data-stu-id="4f8de-123">Dynamics 365 Remote Assist</span></span> 

#### <a name="admin"></a><span data-ttu-id="4f8de-124">Beheerder</span><span class="sxs-lookup"><span data-stu-id="4f8de-124">Admin</span></span>

- <span data-ttu-id="4f8de-125">Azure AD-account (vereist voor het kopen van het abonnement en het toewijzen van licenties)</span><span class="sxs-lookup"><span data-stu-id="4f8de-125">Azure AD account (required for purchasing the subscription and assigning licenses)</span></span>
- <span data-ttu-id="4f8de-126">[Remote Assist abonnement](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (of [Remote Assist proefversie](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist))</span><span class="sxs-lookup"><span data-stu-id="4f8de-126">[Remote Assist subscription](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (or [Remote Assist Trial](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist))</span></span>
    
#### <a name="dynamics-365-remote-assist-user"></a><span data-ttu-id="4f8de-127">Dynamics 365 Remote Assist gebruiker</span><span class="sxs-lookup"><span data-stu-id="4f8de-127">Dynamics 365 Remote Assist user</span></span>

- <span data-ttu-id="4f8de-128">Azure AD-account</span><span class="sxs-lookup"><span data-stu-id="4f8de-128">Azure AD account</span></span>

- <span data-ttu-id="4f8de-129">Remote Assist licentie</span><span class="sxs-lookup"><span data-stu-id="4f8de-129">Remote Assist license</span></span> 

  > [!NOTE]
  > <span data-ttu-id="4f8de-130">Microsoft Teams is gebundeld met Remote Assist</span><span class="sxs-lookup"><span data-stu-id="4f8de-130">Microsoft Teams is bundled with Remote Assist</span></span>

- <span data-ttu-id="4f8de-131">Netwerkverbinding</span><span class="sxs-lookup"><span data-stu-id="4f8de-131">Network Connectivity</span></span>

#### <a name="microsoft-teams-user"></a><span data-ttu-id="4f8de-132">Microsoft Teams gebruiker</span><span class="sxs-lookup"><span data-stu-id="4f8de-132">Microsoft Teams user</span></span>

- <span data-ttu-id="4f8de-133">Azure AD-account</span><span class="sxs-lookup"><span data-stu-id="4f8de-133">Azure AD account</span></span>

- <span data-ttu-id="4f8de-134">Microsoft Teams of [Teams Freemium](https://products.office.com/microsoft-teams/free).</span><span class="sxs-lookup"><span data-stu-id="4f8de-134">Microsoft Teams or [Teams Freemium](https://products.office.com/microsoft-teams/free).</span></span>

- <span data-ttu-id="4f8de-135">Netwerkverbinding</span><span class="sxs-lookup"><span data-stu-id="4f8de-135">Network connectivity</span></span>

<span data-ttu-id="4f8de-136">Als u van plan bent dit scenario voor [verschillende tenants te implementeren,](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)hebt u mogelijk een licentie voor informatiebarrières nodig.</span><span class="sxs-lookup"><span data-stu-id="4f8de-136">If you plan on implementing this [cross-tenant scenario](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants), you may need an Information Barriers license.</span></span> <span data-ttu-id="4f8de-137">Zie [dit artikel om](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) te bepalen of een licentie voor een gegevensbarrière is vereist.</span><span class="sxs-lookup"><span data-stu-id="4f8de-137">See [this article](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) to determine if an Information Barrier License is required.</span></span>

### <a name="dynamics-365-guides"></a><span data-ttu-id="4f8de-138">Dynamics 365 Guides</span><span class="sxs-lookup"><span data-stu-id="4f8de-138">Dynamics 365 Guides</span></span> 

#### <a name="admin"></a><span data-ttu-id="4f8de-139">Beheerder</span><span class="sxs-lookup"><span data-stu-id="4f8de-139">Admin</span></span>

- <span data-ttu-id="4f8de-140">Azure AD-account (vereist voor het kopen van het abonnement en het toewijzen van licenties)</span><span class="sxs-lookup"><span data-stu-id="4f8de-140">Azure AD account (required for purchasing the subscription and assigning licenses)</span></span>
- <span data-ttu-id="4f8de-141">Abonnement op Dynamics 365 [Guides of gratis proefversie](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-one)</span><span class="sxs-lookup"><span data-stu-id="4f8de-141">Dynamics 365 [Guides subscription or free trial](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-one)</span></span>

#### <a name="guides-author"></a><span data-ttu-id="4f8de-142">Auteur van handleidingen</span><span class="sxs-lookup"><span data-stu-id="4f8de-142">Guides Author</span></span>

1. <span data-ttu-id="4f8de-143">Azure AD-account</span><span class="sxs-lookup"><span data-stu-id="4f8de-143">Azure AD account</span></span>
1. [<span data-ttu-id="4f8de-144">Dynamics 365 Guides licentie</span><span class="sxs-lookup"><span data-stu-id="4f8de-144">Dynamics 365 Guides license</span></span>](/dynamics365/mixed-reality/guides/requirements)
1. <span data-ttu-id="4f8de-145">Dynamics 365 Guides toepassing geïnstalleerd op een pc of HoloLens</span><span class="sxs-lookup"><span data-stu-id="4f8de-145">Dynamics 365 Guides application installed on a PC or HoloLens</span></span>
1. <span data-ttu-id="4f8de-146">[Power BI Desktop](https://powerbi.microsoft.com/desktop/) (gebruikt om het analytics-dashboard weer te geven)</span><span class="sxs-lookup"><span data-stu-id="4f8de-146">[Power BI Desktop](https://powerbi.microsoft.com/desktop/) (used to view the Analytics dashboard)</span></span>
1. <span data-ttu-id="4f8de-147">Rol van auteur (voor het maken van handleidingen)</span><span class="sxs-lookup"><span data-stu-id="4f8de-147">Author role (for creating guides)</span></span>
1. <span data-ttu-id="4f8de-148">Netwerkverbinding</span><span class="sxs-lookup"><span data-stu-id="4f8de-148">Network Connectivity</span></span>

#### <a name="guides-user"></a><span data-ttu-id="4f8de-149">Gebruikershandleidingen</span><span class="sxs-lookup"><span data-stu-id="4f8de-149">Guides User</span></span>

1. <span data-ttu-id="4f8de-150">Azure AD-account</span><span class="sxs-lookup"><span data-stu-id="4f8de-150">Azure AD account</span></span>
1. [<span data-ttu-id="4f8de-151">Dynamics 365 Guides licentie</span><span class="sxs-lookup"><span data-stu-id="4f8de-151">Dynamics 365 Guides license</span></span>](/dynamics365/mixed-reality/guides/requirements)
1. <span data-ttu-id="4f8de-152">Dynamics 365 Guides-app geïnstalleerd op een HoloLens</span><span class="sxs-lookup"><span data-stu-id="4f8de-152">Dynamics 365 Guides app installed on a HoloLens</span></span>
1. <span data-ttu-id="4f8de-153">Operatorrol (voor het testen of gebruiken van handleidingen)</span><span class="sxs-lookup"><span data-stu-id="4f8de-153">Operator role (for testing or using guides)</span></span>
1. <span data-ttu-id="4f8de-154">Netwerkverbinding</span><span class="sxs-lookup"><span data-stu-id="4f8de-154">Network Connectivity</span></span>
