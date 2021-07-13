---
title: Beveiliging van besturingssysteem met beheerdersrechten
description: Meer informatie over besturingssystemen die geen beheerder zijn, apparaateigenaren en beveiliging op HoloLens mixed reality apparaten.
ms.prod: hololens
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: security, hololens, adminless, admin-less, operating system, admin-less operating system, admin os, admin-less os, hololens 2, hololens2 security,
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ed2d5134a6bc5952063f7dc5dc5d0e31db972b08
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639400"
---
# <a name="admin-less-operating-system"></a><span data-ttu-id="2aced-104">Besturingssysteem met beheerdersrechten</span><span class="sxs-lookup"><span data-stu-id="2aced-104">Admin-less operating system</span></span>

<span data-ttu-id="2aced-105">HoloLens 2 minimaliseert de surface area voor escalatie van bevoegdheden door ondersteuning voor de groep Administrators uit te uitschakelen en alle UWP-toepassingscode van derden te beperken tot alleen uitvoeren als standaardgebruikers in de AppContainer-sandbox.</span><span class="sxs-lookup"><span data-stu-id="2aced-105">HoloLens 2 minimizes the surface area for privilege escalation by disabling support for the Administrators group and limiting all third-party UWP application code to only execute as standard users within the AppContainer sandbox.</span></span> <span data-ttu-id="2aced-106">Aan deze code wordt alleen toegang verleend tot de resources die zijn beveiligd door mogelijkheden die expliciet in de toepassing worden manifesteerd voor een niet-opleving gebruiker, naast resources die toegankelijk zijn voor alle AppContainers.</span><span class="sxs-lookup"><span data-stu-id="2aced-106">This code is only granted access to those resources protected by capabilities explicitly manifested in the application for an unelevated user in addition to resources accessible to all AppContainers.</span></span>
<span data-ttu-id="2aced-107">Deze toepassingsmogelijkheden blijven het classificatiemodel met drie lagen hebben:</span><span class="sxs-lookup"><span data-stu-id="2aced-107">These application capabilities continue to have the three-tiered classification model:</span></span>
  * <span data-ttu-id="2aced-108">Algemeen</span><span class="sxs-lookup"><span data-stu-id="2aced-108">General</span></span>
  * <span data-ttu-id="2aced-109">Beperkt</span><span class="sxs-lookup"><span data-stu-id="2aced-109">Restricted</span></span>
  * <span data-ttu-id="2aced-110">Windows</span><span class="sxs-lookup"><span data-stu-id="2aced-110">Windows</span></span>

<span data-ttu-id="2aced-111">Windows-onderdelen kunnen ook gebruikmaken van de AppContainer-sandbox via Systeem-UWP's.</span><span class="sxs-lookup"><span data-stu-id="2aced-111">Windows components can also leverage the AppContainer sandbox through System UWPs.</span></span> <span data-ttu-id="2aced-112">Zie uwP-documentatie voor meer Windows Universal Windows Platform [(UWP).](/windows/uwp/)</span><span class="sxs-lookup"><span data-stu-id="2aced-112">To learn more about Universal Windows Platform (UWP), see [UWP documentation](/windows/uwp/).</span></span> <span data-ttu-id="2aced-113">Daarnaast maken Windows-onderdelen met een grotere beperking van bevoegdheden (zoals browserinhoudspagina's of parsers) gebruik van de LPAC-sandbox (Less Privileged AppContainer), waardoor de toegang tot de set resources die toegankelijk is voor alle AppContainers wordt afgesloten.</span><span class="sxs-lookup"><span data-stu-id="2aced-113">Additionally, Windows components with greater privilege reduction needs (like browser content pages or parsers) use the Less Privileged AppContainer (LPAC) sandbox, which cuts off access to the set of resources accessible to all AppContainers.</span></span>

## <a name="device-owner"></a><span data-ttu-id="2aced-114">Eigenaar van het apparaat</span><span class="sxs-lookup"><span data-stu-id="2aced-114">Device owner</span></span>

<span data-ttu-id="2aced-115">Ten slotte is het uitvoeren van specifieke apparaatbrede bewerkingen, zoals het samenvoegen van het apparaat aan een tenant of gebruikersbeheer, alleen toegestaan voor 'apparaateigenaren'.</span><span class="sxs-lookup"><span data-stu-id="2aced-115">Finally, the execution of specific device-wide operations, such as joining the device to a tenant or user management, is only permitted for “device owners”.</span></span> <span data-ttu-id="2aced-116">Deze groep wordt door gebruikers op het apparaat ingevuld via een van de volgende stappen:</span><span class="sxs-lookup"><span data-stu-id="2aced-116">This group is populated by users on the device through one of the following steps:</span></span>
  * <span data-ttu-id="2aced-117">De eerste gebruiker op het apparaat wordt altijd aangewezen als Eigenaar.</span><span class="sxs-lookup"><span data-stu-id="2aced-117">The first user on the device is always designated an Owner.</span></span> 
> [!IMPORTANT]
><span data-ttu-id="2aced-118">Voor Azure AD-gebruikers is de uitzondering op deze regel dat als het apparaat is samengevoegd met Azure AD via Autopilot of bulksgewijs Azure AD-inschrijving, dat gebruikmaakt van een niet-echte gebruiker.</span><span class="sxs-lookup"><span data-stu-id="2aced-118">For Azure AD Users, the exception to this rule is that if the device is Azure AD joined via Autopilot or bulk Azure AD enrollment, which uses a non-real user.</span></span> <span data-ttu-id="2aced-119">In dit geval wordt de eerste AAD-gebruiker die zich bij het apparaat heeft aanmelden mogelijk niet automatisch eigenaar van het apparaat, tenzij aan die gebruiker de rol 'globale beheerder' of 'apparaatbeheerder' is toegewezen in Azure Portal.</span><span class="sxs-lookup"><span data-stu-id="2aced-119">In this case, the first AAD user to sign into the device may not be made device owner automatically unless that user has the "global administrator" or "device administrator" role assigned in Azure portal.</span></span> <span data-ttu-id="2aced-120">Zie de opmerking hieronder voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="2aced-120">For more information, see the note below.</span></span>  

  * <span data-ttu-id="2aced-121">Wanneer een gebruiker wordt gepromoveerd als eigenaar van de Instellingen UX door een andere eigenaar op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="2aced-121">When a user is promoted to be an Owner from the Settings UX by another Owner on the device.</span></span>
  * <span data-ttu-id="2aced-122">Als de eigenaar van het apparaat niet meer beschikbaar is (het bedrijf verlaat) en het apparaat lid is van Azure AD, kan de tenantbeheerder de eigenaar van het apparaat wijzigen in een nieuwe gebruiker in Azure Portal.</span><span class="sxs-lookup"><span data-stu-id="2aced-122">If the device owner is no longer available (leaves the company) and the device is Azure AD joined, the Tenant Admin can change the device owner to a new user in Azure portal.</span></span> <span data-ttu-id="2aced-123">Globale beheerders en apparaatbeheerders van een Azure AD-tenant worden impliciet aangemeld als eigenaren op het apparaat zonder dat een van de vorige stappen is vereist.</span><span class="sxs-lookup"><span data-stu-id="2aced-123">Global Administrators and Device Administrators of an Azure AD tenant are implicitly signed in as Owners on the device without requiring either of the previous steps.</span></span>  

 <span data-ttu-id="2aced-124">IT-beheerders kunnen beheren tot welke apps toegang kunnen krijgen via [privacybeleid.](/windows/client-management/mdm/policy-csp-privacy)</span><span class="sxs-lookup"><span data-stu-id="2aced-124">IT administrators can manage what apps can access through [Privacy](/windows/client-management/mdm/policy-csp-privacy) policies.</span></span> 

> [!NOTE]
> <span data-ttu-id="2aced-125">Zie de documentatie 'Lokale beheerder toewijzen' (maar lees [](/azure/active-directory/devices/assign-local-admin) 'lokale beheerder' als 'apparaateigenaar' omdat de beheerder niet bestaat op HoloLens) voor meer informatie over wie eigenaar van een apparaat wordt gemaakt op een apparaat dat is HoloLens).</span><span class="sxs-lookup"><span data-stu-id="2aced-125">To understand more about who is made a device owner on an Azure AD joined device, see [“Assign Local Admin” documentation](/azure/active-directory/devices/assign-local-admin) (but read ‘local admin’ as ‘device owner’ since admin does not exist on HoloLens).</span></span>