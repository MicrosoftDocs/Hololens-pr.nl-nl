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
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 2f7af532d2172dcaa6514ee11dbb0d6ab5631929
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379433"
---
# <a name="license-requirements"></a><span data-ttu-id="4cb6b-103">Licentievereisten</span><span class="sxs-lookup"><span data-stu-id="4cb6b-103">License requirements</span></span>

## <a name="mobile-device-management-mdm-licenses-guidance"></a><span data-ttu-id="4cb6b-104">Richtlijnen voor MDM-licenties (Mobile Device Management)</span><span class="sxs-lookup"><span data-stu-id="4cb6b-104">Mobile Device Management (MDM) Licenses Guidance</span></span>

<span data-ttu-id="4cb6b-105">Als u van plan bent uw HoloLens-apparaten te beheren, hebt u Azure AD en een MDM nodig.</span><span class="sxs-lookup"><span data-stu-id="4cb6b-105">If you plan on managing your HoloLens devices, you will need Azure AD and an MDM.</span></span> <span data-ttu-id="4cb6b-106">Active Director (AD) kan niet worden gebruikt voor het beheren van HoloLens-apparaten.</span><span class="sxs-lookup"><span data-stu-id="4cb6b-106">Active Director (AD) cannot be used to manage HoloLens devices.</span></span>
<span data-ttu-id="4cb6b-107">Als u van plan bent een andere MDM dan Intune te gebruiken, [is een Azure Active Directory licenties](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) vereist.</span><span class="sxs-lookup"><span data-stu-id="4cb6b-107">If you plan on using an MDM other than Intune, an [Azure Active Directory Licenses](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) is required.</span></span>
<span data-ttu-id="4cb6b-108">Als u van plan bent Om Intune als MDM te gebruiken, leest u de lijst met [suites](https://docs.microsoft.com/intune/fundamentals/licenses) met Intune-licenties.</span><span class="sxs-lookup"><span data-stu-id="4cb6b-108">If you plan on using Intune as your MDM, read up on the [list of suites](https://docs.microsoft.com/intune/fundamentals/licenses) that include Intune licenses.</span></span> <span data-ttu-id="4cb6b-109">**Houd er rekening mee dat Azure AD is opgenomen in het merendeel van deze suites.**</span><span class="sxs-lookup"><span data-stu-id="4cb6b-109">**Please note that Azure AD is included in the majority of these suites.**</span></span>

## <a name="identify-the-licenses-needed-for-your-scenario-and-products"></a><span data-ttu-id="4cb6b-110">De licenties identificeren die nodig zijn voor uw scenario en producten</span><span class="sxs-lookup"><span data-stu-id="4cb6b-110">Identify the licenses needed for your scenario and products</span></span>

### <a name="hololens-1st-gen-licenses-requirements"></a><span data-ttu-id="4cb6b-111">Licentievereisten voor HoloLens (eerste generatie)</span><span class="sxs-lookup"><span data-stu-id="4cb6b-111">HoloLens (1st gen) Licenses Requirements</span></span>

<span data-ttu-id="4cb6b-112">Mogelijk moet u uw HoloLens-apparaat (1e generatie) upgraden naar Windows Holographic for Business.</span><span class="sxs-lookup"><span data-stu-id="4cb6b-112">You may need to upgrade your HoloLens (1st gen) device to Windows Holographic for Business.</span></span> <span data-ttu-id="4cb6b-113">(Zie [Commerciële functies van HoloLens om](holoLens-commercial-features.md#feature-comparison-between-editions) te bepalen of u een upgrade moet uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="4cb6b-113">(See [HoloLens commercial features](holoLens-commercial-features.md#feature-comparison-between-editions) to determine if you need to upgrade).</span></span>

 <span data-ttu-id="4cb6b-114">In dat laatste moet u het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="4cb6b-114">If so, you will need to do the following:</span></span>

- <span data-ttu-id="4cb6b-115">Een HOLOLens Enterprise-licentie-XML-bestand verkrijgen</span><span class="sxs-lookup"><span data-stu-id="4cb6b-115">Acquire a HoloLens Enterprise license XML file</span></span>
- <span data-ttu-id="4cb6b-116">Pas het XML-bestand toe op de HoloLens.</span><span class="sxs-lookup"><span data-stu-id="4cb6b-116">Apply the XML file to the HoloLens.</span></span> <span data-ttu-id="4cb6b-117">U kunt dit doen via een [inrichtingspakket](hololens-provisioning.md) of via uw [mobiele Apparaatbeheer](https://docs.microsoft.com/intune/configuration/holographic-upgrade)</span><span class="sxs-lookup"><span data-stu-id="4cb6b-117">You can do this through a [Provisioning package](hololens-provisioning.md) or through your [Mobile Device Manager](https://docs.microsoft.com/intune/configuration/holographic-upgrade)</span></span>

### <a name="remote-assist-license-requirements"></a><span data-ttu-id="4cb6b-118">Remote Assist licentievereisten</span><span class="sxs-lookup"><span data-stu-id="4cb6b-118">Remote Assist License Requirements</span></span>

<span data-ttu-id="4cb6b-119">Zorg ervoor dat u over de vereiste licentie en het vereiste apparaat hebt. Raadpleeg de documentatie [over vereisten.](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements)</span><span class="sxs-lookup"><span data-stu-id="4cb6b-119">Make sure you have the required licensing and device, which you can check in the [requirements](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements) documentation.</span></span>

1. [<span data-ttu-id="4cb6b-120">Remote Assist licentie</span><span class="sxs-lookup"><span data-stu-id="4cb6b-120">Remote Assist License</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist)
    1. <span data-ttu-id="4cb6b-121">Of probeer een [Remote Assist proefversie](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)</span><span class="sxs-lookup"><span data-stu-id="4cb6b-121">Or try a [Remote Assist trial](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)</span></span>
1. [<span data-ttu-id="4cb6b-122">Teams Freemium/Teams</span><span class="sxs-lookup"><span data-stu-id="4cb6b-122">Teams Freemium/Teams</span></span>](https://products.office.com/microsoft-teams/free)
1. [<span data-ttu-id="4cb6b-123">Azure Active Directory (Azure AD)-licentie</span><span class="sxs-lookup"><span data-stu-id="4cb6b-123">Azure Active Directory (Azure AD) License</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)

<span data-ttu-id="4cb6b-124">Als u van plan bent dit scenario voor verschillende **[tenants te implementeren,](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)** hebt u mogelijk een licentie voor informatiebarrières nodig.</span><span class="sxs-lookup"><span data-stu-id="4cb6b-124">If you plan on implementing **[this cross-tenant scenario](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)**, you may need an Information Barriers license.</span></span> <span data-ttu-id="4cb6b-125">Raadpleeg dit [artikel om](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) te bepalen of een licentie voor een gegevensbarrière is vereist.</span><span class="sxs-lookup"><span data-stu-id="4cb6b-125">Please see [this article](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) to determine if an Information Barrier License is required.</span></span>

### <a name="guides-license-requirements"></a><span data-ttu-id="4cb6b-126">Licentievereisten voor gidsen</span><span class="sxs-lookup"><span data-stu-id="4cb6b-126">Guides License Requirements</span></span>

<span data-ttu-id="4cb6b-127">Bekijk de [bijgewerkte licentie- en apparaatvereisten.](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements)</span><span class="sxs-lookup"><span data-stu-id="4cb6b-127">Check out the [updated licensing and device requirements](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements).</span></span>

1. [<span data-ttu-id="4cb6b-128">Azure Active Directory (Azure AD)-licentie</span><span class="sxs-lookup"><span data-stu-id="4cb6b-128">Azure Active Directory (Azure AD) License</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
1. [<span data-ttu-id="4cb6b-129">Power BI</span><span class="sxs-lookup"><span data-stu-id="4cb6b-129">Power BI</span></span>](https://powerbi.microsoft.com/desktop/)
1. [<span data-ttu-id="4cb6b-130">Gidsen</span><span class="sxs-lookup"><span data-stu-id="4cb6b-130">Guides</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup)
