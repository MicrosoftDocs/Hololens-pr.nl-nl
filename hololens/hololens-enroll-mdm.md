---
title: Registratie van HoloLens in MDM
description: Meer informatie over het registreren HoloLens in Mobile Device Management (MDM) voor eenvoudiger beheer van meerdere apparaten.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 2a9b3fca-8370-44ec-8b57-fb98b8d317b0
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/06/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 6c279664fa6051fab2f5e2e8f61e70b55704ae7c
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640403"
---
# <a name="enroll-hololens-in-mdm"></a><span data-ttu-id="8ab7f-103">Registratie van HoloLens in MDM</span><span class="sxs-lookup"><span data-stu-id="8ab7f-103">Enroll HoloLens in MDM</span></span>

<span data-ttu-id="8ab7f-104">U kunt meerdere apparaten Microsoft HoloLens tegelijkertijd beheren met behulp van oplossingen zoals [Microsoft Intune](/intune/windows-holographic-for-business).</span><span class="sxs-lookup"><span data-stu-id="8ab7f-104">You can manage multiple Microsoft HoloLens devices simultaneously using solutions like [Microsoft Intune](/intune/windows-holographic-for-business).</span></span> <span data-ttu-id="8ab7f-105">U kunt instellingen beheren, apps selecteren om beveiligingsconfiguraties te installeren en instellen die zijn afgestemd op de behoefte van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="8ab7f-105">You will be able to manage settings, select apps to install and set security configurations tailored to your organization's need.</span></span> <span data-ttu-id="8ab7f-106">Zie Apparaten met [Windows Holographic](/intune/windows-holographic-for-business)beheren met Microsoft Intune, de configuratieserviceproviders [(CSP's)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens)die worden ondersteund in Windows Holographic en de beleidsregels die worden ondersteund [door Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).</span><span class="sxs-lookup"><span data-stu-id="8ab7f-106">See [Manage devices running Windows Holographic with Microsoft Intune](/intune/windows-holographic-for-business), the [configuration service providers (CSPs) that are supported in Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens), and the [policies supported by Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).</span></span>

> [!NOTE]
> <span data-ttu-id="8ab7f-107">Mobile Device Management (MDM), met inbegrip van de functies vpn, Bitlocker en kioskmodus, is alleen beschikbaar wanneer u een upgrade naar [Windows Holographic for Business.](hololens1-upgrade-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="8ab7f-107">Mobile device management (MDM), including the VPN, Bitlocker, and kiosk mode features, is only available when you [upgrade to Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="8ab7f-108">Vereisten</span><span class="sxs-lookup"><span data-stu-id="8ab7f-108">Requirements</span></span>

 <span data-ttu-id="8ab7f-109">Uw organisatie moet Mobile Device Management (MDM) hebben ingesteld om de apparaten HoloLens beheren.</span><span class="sxs-lookup"><span data-stu-id="8ab7f-109">Your organization will need to have Mobile Device Management (MDM) set up in order to manage HoloLens devices.</span></span> <span data-ttu-id="8ab7f-110">Uw MDM-provider kan een Microsoft Intune een externe provider zijn die gebruikmaakt van Microsoft MDM-API's.</span><span class="sxs-lookup"><span data-stu-id="8ab7f-110">Your MDM provider can be Microsoft Intune or a 3rd party provider that uses Microsoft MDM APIs.</span></span>
 
## <a name="different-ways-to-enroll"></a><span data-ttu-id="8ab7f-111">Verschillende manieren om in te schrijven</span><span class="sxs-lookup"><span data-stu-id="8ab7f-111">Different ways to enroll</span></span>

<span data-ttu-id="8ab7f-112">Afhankelijk van het type identiteit [dat is gekozen](hololens-identity.md) tijdens OOBE of na het aanmelden, zijn er verschillende registratiemethoden.</span><span class="sxs-lookup"><span data-stu-id="8ab7f-112">Depending on the type of [identity](hololens-identity.md) chosen either during OOBE or post sign-in, there are different methods of enrollment.</span></span>

- <span data-ttu-id="8ab7f-113">Als Identiteit Azure AD is, klikt u tijdens OOBE of Instellingen **de** knop App Access Work Verbinding maken  ->  **school.**  ->  </span><span class="sxs-lookup"><span data-stu-id="8ab7f-113">If Identity is Azure AD, then either during OOBE or **Settings App** -> **Access Work or School** -> **Connect** button.</span></span>
    - <span data-ttu-id="8ab7f-114">Voor Azure AD [vindt automatische MDM-inschrijving](hololens-enroll-mdm.md#auto-enrollment-in-mdm) alleen plaats als Azure AD is geconfigureerd met inschrijvings-URL's.</span><span class="sxs-lookup"><span data-stu-id="8ab7f-114">For Azure AD, [automatic MDM enrollment](hololens-enroll-mdm.md#auto-enrollment-in-mdm) only occurs if Azure AD has been configured with enrollment URLs.</span></span>
     
- <span data-ttu-id="8ab7f-115">Als de identiteit Azure AD is en het apparaat vooraf is geregistreerd bij de Intune MDM-server met een specifiek configuratieprofiel dat is toegewezen, vinden Azure AD-Join en automatische [MDM-inschrijving](hololens-enroll-mdm.md#auto-enrollment-in-mdm) plaats tijdens OOBE.</span><span class="sxs-lookup"><span data-stu-id="8ab7f-115">If Identity is Azure AD and device has been pre-registered with Intune MDM server with specific configuration profile assigned to it, then Azure AD-Join and [automatic MDM enrollment](hololens-enroll-mdm.md#auto-enrollment-in-mdm) will occur during OOBE.</span></span>
    - <span data-ttu-id="8ab7f-116">Ook wel [autopilot-stroom beschikbaar](hololens2-autopilot.md) in [builds van 19041.1103+](hololens-release-notes.md#windows-holographic-version-2004).</span><span class="sxs-lookup"><span data-stu-id="8ab7f-116">Also called [Autopilot flow](hololens2-autopilot.md) Available in [19041.1103+ builds](hololens-release-notes.md#windows-holographic-version-2004).</span></span>
    

- <span data-ttu-id="8ab7f-117">Als Identiteit MSA is, gebruikt u Instellingen **knop Toegang** tot werk of  ->  **school**  ->  **Verbinding maken** app.</span><span class="sxs-lookup"><span data-stu-id="8ab7f-117">If Identity is MSA, then using **Settings App** -> **Access Work or School** -> **Connect** button.</span></span>
    - <span data-ttu-id="8ab7f-118">Ook wel werkaccountstroom (AWA) toevoegen genoemd.</span><span class="sxs-lookup"><span data-stu-id="8ab7f-118">Also called Add Work Account (AWA) flow.</span></span>
- <span data-ttu-id="8ab7f-119">Als Identiteit lokale gebruiker is, gebruikt u Instellingen **de koppeling Werk-** of schoolinschrijving voor app-toegang alleen  ->    ->  **in apparaatbeheer.**</span><span class="sxs-lookup"><span data-stu-id="8ab7f-119">If Identity is Local User, then using **Settings App** -> **Access Work or School** -> **Enroll only in device management** link.</span></span>
    - <span data-ttu-id="8ab7f-120">Ook wel pure MDM-inschrijvingsstroom genoemd.</span><span class="sxs-lookup"><span data-stu-id="8ab7f-120">Also called pure MDM enrollment flow.</span></span>

<span data-ttu-id="8ab7f-121">Zodra het apparaat is ingeschreven bij uw MDM-server, geeft Instellingen app aan dat het apparaat is ingeschreven bij apparaatbeheer.</span><span class="sxs-lookup"><span data-stu-id="8ab7f-121">Once the device is enrolled with your MDM server, the Settings app will now reflect that the device is enrolled in device management.</span></span>

## <a name="auto-enrollment-in-mdm"></a><span data-ttu-id="8ab7f-122">Automatische inschrijving in MDM</span><span class="sxs-lookup"><span data-stu-id="8ab7f-122">Auto-enrollment in MDM</span></span>

<span data-ttu-id="8ab7f-123">Als uw organisatie een [Azure Premium-abonnement](https://azure.microsoft.com/overview/)heeft, gebruik maakt van Azure Active Directory (Azure AD) en een MDM-oplossing die een Azure AD-token accepteert voor verificatie (momenteel alleen ondersteund in Microsoft Intune en AirWatch), kan uw IT-beheerder Azure AD configureren om automatisch MDM-inschrijving toe te staan nadat de gebruiker zich heeft aanmelden met zijn Azure AD-account.</span><span class="sxs-lookup"><span data-stu-id="8ab7f-123">If your organization has an [Azure Premium subscription](https://azure.microsoft.com/overview/), is using Azure Active Directory (Azure AD) and an MDM solution that accepts an Azure AD token for authentication (currently, only supported in Microsoft Intune and AirWatch), your IT admin can configure Azure AD to automatically allow MDM enrollment after the user signs in with their Azure AD account.</span></span> [<span data-ttu-id="8ab7f-124">Meer informatie over het configureren van Azure AD-inschrijving.</span><span class="sxs-lookup"><span data-stu-id="8ab7f-124">Learn how to configure Azure AD enrollment.</span></span>](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

<span data-ttu-id="8ab7f-125">Wanneer automatische inschrijving is ingeschakeld, is er geen extra handmatige inschrijving nodig.</span><span class="sxs-lookup"><span data-stu-id="8ab7f-125">When auto-enrollment is enabled, no extra manual enrollment is needed.</span></span> <span data-ttu-id="8ab7f-126">Wanneer de gebruiker zich met een Azure AD-account heeft aangemeld, wordt het apparaat ingeschreven bij MDM nadat de eerste run-ervaring is uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="8ab7f-126">When the user signs in with an Azure AD account, the device is enrolled in MDM after completing the first-run experience.</span></span>

<span data-ttu-id="8ab7f-127">Wanneer een apparaat lid is van Azure AD, kan dit van invloed zijn op wie de eigenaar [van het apparaat heeft beschouwd.](security-adminless-os.md#device-owner)</span><span class="sxs-lookup"><span data-stu-id="8ab7f-127">When a device is Azure AD Joined it may affect who considered the [device owner](security-adminless-os.md#device-owner).</span></span>

## <a name="unenroll-hololens-from-intune"></a><span data-ttu-id="8ab7f-128">Registratie van HoloLens bij Intune</span><span class="sxs-lookup"><span data-stu-id="8ab7f-128">Unenroll HoloLens from Intune</span></span>

<span data-ttu-id="8ab7f-129">Afhankelijk van de inschrijvingsmethode is het uitschrijving van uw apparaat mogelijk niet beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="8ab7f-129">Depending on the enrollment method, unenrolling your device may not be available.</span></span>

<span data-ttu-id="8ab7f-130">Als uw apparaat is ingeschreven met een Azure AD-account of Autopilot, kan het niet worden uitgeschreven bij Intune.</span><span class="sxs-lookup"><span data-stu-id="8ab7f-130">If your device was enrolled with an Azure AD account or Autopilot, it cannot be unenrolled from Intune.</span></span> <span data-ttu-id="8ab7f-131">Als u de aaneenvoeging wilt HoloLens Azure AD of opnieuw wilt worden lid van een andere Azure AD-tenant, moet u het apparaat opnieuw [instellen/reflashen.](hololens-recovery.md#reset-the-device)</span><span class="sxs-lookup"><span data-stu-id="8ab7f-131">If you wish to unjoin HoloLens from Azure AD or rejoin it to a different to Azure AD tenant, you must [reset/reflash](hololens-recovery.md#reset-the-device) the device.</span></span>

<span data-ttu-id="8ab7f-132">Als uw apparaat is ingeschreven vanuit een MSA-account dat een werkaccount heeft toegevoegd of van een lokaal account dat alleen is ingeschreven bij apparaatbeheer, kunt u de registratie van het apparaat in de uitschrijving van het apparaat in- of verwijderen.</span><span class="sxs-lookup"><span data-stu-id="8ab7f-132">If your device was enrolled from a MSA account that added a work account or from a Local account that enrolled only in device management, then you may unenroll the device.</span></span> <span data-ttu-id="8ab7f-133">Open de Startmenu selecteer vervolgens Instellingen de knop **Verbinding** verbreken met werk- of  ->    ->  *schoolaccount* van App  ->  **Access.**</span><span class="sxs-lookup"><span data-stu-id="8ab7f-133">Open the Start menu and then select **Settings App** -> **Access Work or School** -> *YourAccount* -> **Disconnect** button.</span></span>