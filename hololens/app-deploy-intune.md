---
title: Intune en Bedrijfsportal
description: Meer informatie over het instellen, toewijzen en maken van een gebruikerservaring met Intune, mobile device management en de bedrijfsportal.
keywords: intune, app-beheer, app, bedrijfsportal, portal, hololens
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: b192732f5e7edffaa1d0ab081454e4034c416191
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635497"
---
# <a name="intune--company-portal"></a><span data-ttu-id="f0292-104">Intune-& Bedrijfsportal</span><span class="sxs-lookup"><span data-stu-id="f0292-104">Intune & Company Portal</span></span>

<span data-ttu-id="f0292-105">Met Mobile Device Management (MDM) kunt u uw eigen aangepaste apps via [Microsoft Endpoint Manager (Intune)](/intune/windows-holographic-for-business) gebruiken om deze rechtstreeks op uw HoloLens implementeren.</span><span class="sxs-lookup"><span data-stu-id="f0292-105">With Mobile Device Management (MDM), you can use your own custom apps through [Microsoft Endpoint Manager (Intune)](/intune/windows-holographic-for-business) to deploy it directly to your HoloLens devices.</span></span> <span data-ttu-id="f0292-106">Microsoft Intune is een cloudservice die is gericht op MDM (Mobile Device Management) en MAM (Mobile Application Management).</span><span class="sxs-lookup"><span data-stu-id="f0292-106">Microsoft Intune is a cloud-based service that focuses on mobile device management (MDM) and mobile application management (MAM).</span></span> <span data-ttu-id="f0292-107">Intune is opgenomen in de [EMS-suite (Enterprise Mobility en Security)](https://www.microsoft.com/microsoft-365/enterprise-mobility-security) van Microsoft, en biedt gebruikers de mogelijkheid om productief te zijn terwijl uw bedrijfsgegevens beschermd blijven.</span><span class="sxs-lookup"><span data-stu-id="f0292-107">Intune is included in Microsoft's [Enterprise Mobility + Security (EMS) suite](https://www.microsoft.com/microsoft-365/enterprise-mobility-security), and enables users to be productive while keeping your organization data protected.</span></span> <span data-ttu-id="f0292-108">Lees Wat is Intune? voor meer informatie [over Intune.](/mem/intune/fundamentals/what-is-intune)</span><span class="sxs-lookup"><span data-stu-id="f0292-108">To learn more about Intune, read [What is Intune](/mem/intune/fundamentals/what-is-intune).</span></span>

## <a name="setup"></a><span data-ttu-id="f0292-109">Instellen</span><span class="sxs-lookup"><span data-stu-id="f0292-109">Setup</span></span>

1. <span data-ttu-id="f0292-110">Upload app naar een Line-Of-Business-bedrijf of upload een aangepaste app naar uw Intune-tenant.</span><span class="sxs-lookup"><span data-stu-id="f0292-110">Upload an app to a Line of Business, or upload a custom app to your Intune tenant.</span></span> <span data-ttu-id="f0292-111">Zie ook: [Enterprise app management](/windows/client-management/mdm/enterprise-app-management).</span><span class="sxs-lookup"><span data-stu-id="f0292-111">See also: [Enterprise app management](/windows/client-management/mdm/enterprise-app-management).</span></span>

2. <span data-ttu-id="f0292-112">[Wijs uw app toe aan een groep](/mem/intune/apps/apps-deploy).</span><span class="sxs-lookup"><span data-stu-id="f0292-112">[Assign your app to a group](/mem/intune/apps/apps-deploy).</span></span> <span data-ttu-id="f0292-113">Op basis van het toewijzingstype dat u kiest, kan de app automatisch worden geleverd of kan deze eenvoudig worden teruggehaald als u een selectie apps hebt.</span><span class="sxs-lookup"><span data-stu-id="f0292-113">Based on the assignment type you choose, the app can be delivered automatically or available to be readily pulled down if you have a selection of apps.</span></span>

> [!NOTE]
> <span data-ttu-id="f0292-114">Zorg er bij het bouwen van uw appx-bundel voor dat u rekening houdt met de architectuur voor de apparaten waarop u implementeert.</span><span class="sxs-lookup"><span data-stu-id="f0292-114">When building your appx bundle make sure to account for including the architecture for the device(s) that you are deploying to.</span></span> <span data-ttu-id="f0292-115">HoloLens 2 is ARM64 en HoloLens (1e generatie) is x86.</span><span class="sxs-lookup"><span data-stu-id="f0292-115">HoloLens 2 is ARM64, and HoloLens (1st Gen) is x86.</span></span> <span data-ttu-id="f0292-116">U kunt beide opnemen in één appx-bundel als u van plan bent een omgeving met gemengde apparaten te hebben.</span><span class="sxs-lookup"><span data-stu-id="f0292-116">You may include both in a single appx bundle if you plan on having a mixed devices environment.</span></span>

## <a name="assignment-types"></a><span data-ttu-id="f0292-117">Toewijzingstypen</span><span class="sxs-lookup"><span data-stu-id="f0292-117">Assignment types</span></span>

<span data-ttu-id="f0292-118">Als u wilt dat uw app na de inschrijving automatisch op het apparaat wordt geïnstalleerd, moet u **Vereist** selecteren voor die groep(en).</span><span class="sxs-lookup"><span data-stu-id="f0292-118">To have your app to be automatically installed on the device after enrollment, you should select **Required** for that group(s).</span></span>
<span data-ttu-id="f0292-119">Als u uw app beschikbaar wilt maken voor downloaden naar apparaten die zijn ingeschreven via de bedrijfsportal, selecteert u **Beschikbaar voor ingeschreven apparaten.**</span><span class="sxs-lookup"><span data-stu-id="f0292-119">To make your app available for download to devices enrolled through the company portal, select **Available for enrolled devices**.</span></span>

## <a name="end-user-experience"></a><span data-ttu-id="f0292-120">De ervaring voor de eindgebruiker</span><span class="sxs-lookup"><span data-stu-id="f0292-120">End-User Experience</span></span>

<span data-ttu-id="f0292-121">Nadat u de configuratie voor Intune hebt ingesteld, kunt u eindgebruikers de geselecteerde apps laten ontvangen.</span><span class="sxs-lookup"><span data-stu-id="f0292-121">After you have set up configuration on Intune, you are ready for end users to receive your selected apps.</span></span>

<span data-ttu-id="f0292-122">Volg deze stappen om uw app(s) automatisch op te halen:</span><span class="sxs-lookup"><span data-stu-id="f0292-122">Follow these steps to automatically get your app(s):</span></span>

1. <span data-ttu-id="f0292-123">Schrijf uw apparaat in bij uw tenant.</span><span class="sxs-lookup"><span data-stu-id="f0292-123">Enroll your device with your tenant.</span></span>
2. <span data-ttu-id="f0292-124">Zodra de inschrijving van uw apparaat is voltooid, ontvangt u de app op uw apparaat.</span><span class="sxs-lookup"><span data-stu-id="f0292-124">Once your device has completed enrollment, you should receive the app on your device.</span></span>
3. <span data-ttu-id="f0292-125">Als u uw app niet direct ziet, gaat u naar Instellingen Accounts **Werk-** of schoolaccountgegevens en schuift u omlaag om informatie over de status van de  >    >    >   geïnstalleerde app weer te geven.</span><span class="sxs-lookup"><span data-stu-id="f0292-125">If you are not seeing you app immediately, go to **Settings** > **Accounts** > **Work or School** > *your account* Info, and scroll down to see information on installed app status.</span></span>

<span data-ttu-id="f0292-126">Apps openen via de Bedrijfsportal:</span><span class="sxs-lookup"><span data-stu-id="f0292-126">How to get to apps through the Company Portal:</span></span>

1. <span data-ttu-id="f0292-127">Open het **menu Start** en selecteer **Microsoft Store**.</span><span class="sxs-lookup"><span data-stu-id="f0292-127">Open the **Start Menu** and select **Microsoft Store**.</span></span>
2. <span data-ttu-id="f0292-128">Zoek naar **Bedrijfsportal** en download de app.</span><span class="sxs-lookup"><span data-stu-id="f0292-128">Search for **Company Portal** and download the app.</span></span>
3. <span data-ttu-id="f0292-129">Meld u aan bij uw account.</span><span class="sxs-lookup"><span data-stu-id="f0292-129">Sign into your account.</span></span>
4. <span data-ttu-id="f0292-130">Selecteer de app die u wilt ontvangen en download deze.</span><span class="sxs-lookup"><span data-stu-id="f0292-130">Select the app you wish to receive and download it.</span></span>

> [!Tip]
> <span data-ttu-id="f0292-131">Meer informatie over [het automatisch installeren van de Bedrijfsportal](/mem/intune/apps/company-portal-app) en het implementeren en beheren van apps in [Intune.](/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps)</span><span class="sxs-lookup"><span data-stu-id="f0292-131">Learn more about [auto-installing the Company Portal](/mem/intune/apps/company-portal-app) and [deploying and managing apps in Intune](/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps).</span></span>
