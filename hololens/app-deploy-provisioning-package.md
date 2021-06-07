---
title: Inrichtingspakket
description: Meer informatie over app-verpakking, inrichting, implementatie en implementatie van bedrijfsapps voor HoloLens-apparaten.
keywords: app, app-implementatie, implementatie van bedrijfsapps, inrichting
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 9c73b03e6a8dca6baf6c58fed091df96994c3780
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/19/2021
ms.locfileid: "111377849"
---
# <a name="provisioning-package"></a><span data-ttu-id="5e51c-104">Inrichtingspakket</span><span class="sxs-lookup"><span data-stu-id="5e51c-104">Provisioning Package</span></span>

<span data-ttu-id="5e51c-105">Inrichtingspakketten kunnen worden gebruikt voor het voorbereiden en configureren van apparaten in een omgeving zonder toegang tot eindpuntbeheer.</span><span class="sxs-lookup"><span data-stu-id="5e51c-105">Provisioning packages can be used to prepare and configure devices in an environment without access to endpoint management.</span></span> <span data-ttu-id="5e51c-106">Ze kunnen ook worden geïmplementeerd op een apparaat, ongeacht de identiteit van de gebruiker, de inschrijvingsstatus, tijdens de Out of Box Experience (OOBE) of door een inrichtingspakket toe te passen tijdens de [installatie](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup).</span><span class="sxs-lookup"><span data-stu-id="5e51c-106">They can also be deployed to a device regardless of identity of the user, enrollment status, during the Out of Box Experience (OOBE), or by [applying a provisioning package during setup](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup).</span></span>

## <a name="provisioning-packages-considerations"></a><span data-ttu-id="5e51c-107">Overwegingen voor inrichtingspakketten:</span><span class="sxs-lookup"><span data-stu-id="5e51c-107">Provisioning Packages considerations:</span></span>

* <span data-ttu-id="5e51c-108">Niet-openbare apps</span><span class="sxs-lookup"><span data-stu-id="5e51c-108">Non-Public apps</span></span>
* <span data-ttu-id="5e51c-109">Alleen USB-side-load</span><span class="sxs-lookup"><span data-stu-id="5e51c-109">USB side-load only</span></span>
* <span data-ttu-id="5e51c-110">Geen automatische update (handmatige updates via PPKG's vereist)</span><span class="sxs-lookup"><span data-stu-id="5e51c-110">No auto update (requires manual updates via PPKGs)</span></span>

<span data-ttu-id="5e51c-111">Apps die zijn geïnstalleerd via een inrichtingspakket, moeten zijn ondertekend met een certificaat in de store van de lokale computer.</span><span class="sxs-lookup"><span data-stu-id="5e51c-111">Apps installed via a provisioning package must be signed by a certificate in the local machine store.</span></span> <span data-ttu-id="5e51c-112">Met inrichtingspakketten kunnen alleen certificaten worden geïnstalleerd in het apparaatopslag (lokale computer). Daarom kunnen een app en certificaat worden geïnstalleerd via hetzelfde inrichtingspakket.</span><span class="sxs-lookup"><span data-stu-id="5e51c-112">Provisioning packages can only install certificates to the device (local machine) store, therefore an app and certificate may be installed via the same provisioning package.</span></span> <span data-ttu-id="5e51c-113">Als u uw certificaat implementeert vanuit MDM of installeert via [Certificaatbeheer,](certificate-manager.md)moet u het certificaat implementeren in de store van de lokale computer om apps te ondertekenen die op deze manier zijn geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="5e51c-113">If you are deploying your certificate from MDM or installing via the [Certificate Manager](certificate-manager.md), make sure to deploy the certificate to the local machine store to sign apps installed this way.</span></span>

<span data-ttu-id="5e51c-114">Ga naar HoloLens Provisioning voor meer informatie over de basisbeginselen van het maken van een [inrichtingspakket voor HoloLens-apparaten.](https://docs.microsoft.com/hololens/hololens-provisioning)</span><span class="sxs-lookup"><span data-stu-id="5e51c-114">To learn the basics of creating a Provisioning Package for HoloLens devices, visit [HoloLens Provisioning](https://docs.microsoft.com/hololens/hololens-provisioning).</span></span> <span data-ttu-id="5e51c-115">Als u een app wilt implementeren, moet u beginnen met geavanceerde inrichting.</span><span class="sxs-lookup"><span data-stu-id="5e51c-115">To deploy an app, you must start with advanced provisioning.</span></span>

> [!NOTE]
> <span data-ttu-id="5e51c-116">HoloLens (eerste generatie) biedt beperkte ondersteuning voor het installeren van apps **(UniversalAppInstall)** met behulp van een inrichtingspakket.</span><span class="sxs-lookup"><span data-stu-id="5e51c-116">HoloLens (1st gen) has limited support installing apps (**UniversalAppInstall**) by using a provisioning package.</span></span> <span data-ttu-id="5e51c-117">HoloLens-apparaten (eerste generatie) bieden alleen ondersteuning voor het installeren van een app via PPKG alleen tijdens OOBE en alleen met installatie van gebruikerscontext.</span><span class="sxs-lookup"><span data-stu-id="5e51c-117">HoloLens (1st gen) devices only support installing an app via PPKG only during OOBE and only with user context installs.</span></span>

## <a name="setup"></a><span data-ttu-id="5e51c-118">Instellen</span><span class="sxs-lookup"><span data-stu-id="5e51c-118">Setup</span></span>

<span data-ttu-id="5e51c-119">In [Windows Configuration Designer moet u](https://www.microsoft.com/store/productId/9NBLGGH4TX22) de volgende vier stappen volgen.</span><span class="sxs-lookup"><span data-stu-id="5e51c-119">Within [Windows Configuration Designer](https://www.microsoft.com/store/productId/9NBLGGH4TX22) take following four steps.</span></span>

1. <span data-ttu-id="5e51c-120">Stel ApplicationManagement/AllowAllTrustedApps in op Ja.</span><span class="sxs-lookup"><span data-stu-id="5e51c-120">Set ApplicationManagement/AllowAllTrustedApps To “Yes”.</span></span> <span data-ttu-id="5e51c-121">Zie: [ApplicationManagement/AllowAllTrustedApps.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps)</span><span class="sxs-lookup"><span data-stu-id="5e51c-121">See: [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).</span></span>

2. <span data-ttu-id="5e51c-122">**Navigeer naar UniversalAppInstall**  >  **UserContextAppLicense** voer **packageFamilyName in.**</span><span class="sxs-lookup"><span data-stu-id="5e51c-122">Navigate to **UniversalAppInstall** > **UserContextAppLicense** enter the **PackageFamilyName**.</span></span> <span data-ttu-id="5e51c-123">Zie [UniversalAppInstall.](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall)</span><span class="sxs-lookup"><span data-stu-id="5e51c-123">See [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall).</span></span> <span data-ttu-id="5e51c-124">Zie ook: [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).</span><span class="sxs-lookup"><span data-stu-id="5e51c-124">See also: [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).</span></span>

   <span data-ttu-id="5e51c-125">U kunt deze Apparaatportal op een apparaat waar u uw app al op hebt geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="5e51c-125">You can use Device Portal on a device you have already installed your app to.</span></span> <span data-ttu-id="5e51c-126">Ga naar de pagina Apps en bekijk de regel PackageRelativeID, met alle informatie vóór de '!' Is uw **PackageFamilyName.**</span><span class="sxs-lookup"><span data-stu-id="5e51c-126">Visit the Apps page, and look at the PackageRelativeID line, all the information before the "!" Is your **PackageFamilyName**.</span></span>

3. <span data-ttu-id="5e51c-127">Vervolgens ziet u dat u een nieuwe sectie hebt, **ApplicationFile.**</span><span class="sxs-lookup"><span data-stu-id="5e51c-127">You will then see that you have a new section, **ApplicationFile**.</span></span> <span data-ttu-id="5e51c-128">Gebruik dit gebied om uw appx-bundel te uploaden.</span><span class="sxs-lookup"><span data-stu-id="5e51c-128">Use this area to upload your appx bundle.</span></span>

4. <span data-ttu-id="5e51c-129">Afhankelijk van of u uw app hebt aangeschaft of uw eigen LOB-app hebt gebouwd, moet u het licentiebestand of beveiligingscertificaat uploaden.</span><span class="sxs-lookup"><span data-stu-id="5e51c-129">Depending on if you have purchased your app or built your own LOB app, you will need to upload the license file or security certificate.</span></span>

    - <span data-ttu-id="5e51c-130">Voor licentiebestand: navigeer **naar UniversalAppInstall**  >  **UserContextAppLicence,** blader naar de locatie van uw licentie en upload deze.</span><span class="sxs-lookup"><span data-stu-id="5e51c-130">For license file: navigate to **UniversalAppInstall** > **UserContextAppLicence** and browse to the location of your license and upload it.</span></span>
    - <span data-ttu-id="5e51c-131">Voor het beveiligingsbestand gaat u naar **Certificaten en** selecteert u het certificaat dat u naast uw APPX-bundel wilt installeren.</span><span class="sxs-lookup"><span data-stu-id="5e51c-131">For the security file, navigate to **Certificates** and select your certificate to install alongside your .appx bundle.</span></span>

<span data-ttu-id="5e51c-132">Sla uw project op een veilige locatie op.</span><span class="sxs-lookup"><span data-stu-id="5e51c-132">Make sure to save your project to a secure location.</span></span> <span data-ttu-id="5e51c-133">Exporteert het vervolgens als **een inrichtingspakket**. </span><span class="sxs-lookup"><span data-stu-id="5e51c-133">Then **Export** it as a **Provisioning Package**.</span></span>  

<span data-ttu-id="5e51c-134">Zie ook: [Uw inrichtingspakket toepassen op HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).</span><span class="sxs-lookup"><span data-stu-id="5e51c-134">See also: [Apply your provisioning package to HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).</span></span>
