---
title: Infrastructuurrichtlijnen voor HoloLens
description: Meer informatie over de infrastructuurrichtlijnen HoloLens apparaten, waaronder draadloze netwerkondersteuning, hulp op afstand en beheer van mobiele apparaten.
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
ms.topic: article
ms.localizationpriority: high
ms.date: 1/23/2020
ms.reviewer: ''
audience: ITPro
manager: bradke
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: e3f87c524ce0f8af05ec8c92877d46facd962fb4
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639281"
---
# <a name="configure-your-network-for-hololens"></a><span data-ttu-id="42573-103">Uw netwerk configureren voor HoloLens</span><span class="sxs-lookup"><span data-stu-id="42573-103">Configure Your Network for HoloLens</span></span>

<span data-ttu-id="42573-104">Voor dit gedeelte van het document zijn de volgende personen vereist:</span><span class="sxs-lookup"><span data-stu-id="42573-104">This portion of the document will require the following people:</span></span>

1. <span data-ttu-id="42573-105">Netwerkbeheerder met machtigingen om wijzigingen aan te brengen in de proxy/firewall</span><span class="sxs-lookup"><span data-stu-id="42573-105">Network Admin with permissions to make changes to the proxy/firewall</span></span>
2. <span data-ttu-id="42573-106">Azure Active Directory Admin</span><span class="sxs-lookup"><span data-stu-id="42573-106">Azure Active Directory Admin</span></span>
3. <span data-ttu-id="42573-107">Mobile Apparaatbeheer Admin</span><span class="sxs-lookup"><span data-stu-id="42573-107">Mobile Device Manager Admin</span></span>

## <a name="infrastructure-requirements"></a><span data-ttu-id="42573-108">Infrastructuurvereisten</span><span class="sxs-lookup"><span data-stu-id="42573-108">Infrastructure Requirements</span></span>

<span data-ttu-id="42573-109">HoloLens is in de kern een Windows mobiel apparaat dat is geïntegreerd met Azure.</span><span class="sxs-lookup"><span data-stu-id="42573-109">HoloLens is, at its core, a Windows mobile device integrated with Azure.</span></span>  <span data-ttu-id="42573-110">Het werkt het beste in commerciële omgevingen met draadloze netwerkbeschikbaarheid (Wi-Fi) en toegang tot Microsoft-services.</span><span class="sxs-lookup"><span data-stu-id="42573-110">It works best in commercial environments with wireless network availability (wi-fi) and access to Microsoft services.</span></span>

<span data-ttu-id="42573-111">Essentiële cloudservices zijn onder andere:</span><span class="sxs-lookup"><span data-stu-id="42573-111">Critical cloud services include:</span></span>

- <span data-ttu-id="42573-112">Azure active directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="42573-112">Azure active directory (Azure AD)</span></span>
- <span data-ttu-id="42573-113">Windows Bijwerken (WU)</span><span class="sxs-lookup"><span data-stu-id="42573-113">Windows Update (WU)</span></span>

<span data-ttu-id="42573-114">Commerciële klanten hebben een enterprise mobility management-infrastructuur (EMM) of MDM-infrastructuur (Mobile Device Management) nodig om apparaten op schaal HoloLens beheren.</span><span class="sxs-lookup"><span data-stu-id="42573-114">Commercial customers will need enterprise mobility management (EMM) or mobile device management (MDM) infrastructure to manage HoloLens devices at scale.</span></span>  <span data-ttu-id="42573-115">In deze handleiding [wordt Microsoft Intune](https://www.microsoft.com/enterprise-mobility-security/microsoft-intune) voorbeeld gebruikt, maar elke provider met volledige ondersteuning voor Microsoft Policy kan ondersteuning bieden HoloLens.</span><span class="sxs-lookup"><span data-stu-id="42573-115">This guide uses [Microsoft Intune](https://www.microsoft.com/enterprise-mobility-security/microsoft-intune) as an example, though any provider with full support for Microsoft Policy can support HoloLens.</span></span>  <span data-ttu-id="42573-116">Vraag uw provider voor het beheer van mobiele apparaten of deze ondersteuning HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="42573-116">Ask your mobile device management provider if they support HoloLens 2.</span></span>

<span data-ttu-id="42573-117">HoloLens biedt ondersteuning voor een beperkte set niet-verbonden cloudervaringen.</span><span class="sxs-lookup"><span data-stu-id="42573-117">HoloLens does support a limited set of cloud disconnected experiences.</span></span>

### <a name="wireless-network-eap-support"></a><span data-ttu-id="42573-118">EAP-ondersteuning voor draadloze netwerken</span><span class="sxs-lookup"><span data-stu-id="42573-118">Wireless network EAP support</span></span>

- <span data-ttu-id="42573-119">PEAP-MS-CHAPv2</span><span class="sxs-lookup"><span data-stu-id="42573-119">PEAP-MS-CHAPv2</span></span>
- <span data-ttu-id="42573-120">PEAP-TLS</span><span class="sxs-lookup"><span data-stu-id="42573-120">PEAP-TLS</span></span>
- <span data-ttu-id="42573-121">TLS</span><span class="sxs-lookup"><span data-stu-id="42573-121">TLS</span></span>
- <span data-ttu-id="42573-122">TTLS-CHAP</span><span class="sxs-lookup"><span data-stu-id="42573-122">TTLS-CHAP</span></span>
- <span data-ttu-id="42573-123">TTLS-CHAPv2</span><span class="sxs-lookup"><span data-stu-id="42573-123">TTLS-CHAPv2</span></span>
- <span data-ttu-id="42573-124">TTLS-MS-CHAPv2</span><span class="sxs-lookup"><span data-stu-id="42573-124">TTLS-MS-CHAPv2</span></span>
- <span data-ttu-id="42573-125">TTLS-PAP</span><span class="sxs-lookup"><span data-stu-id="42573-125">TTLS-PAP</span></span>
- <span data-ttu-id="42573-126">TTLS-TLS</span><span class="sxs-lookup"><span data-stu-id="42573-126">TTLS-TLS</span></span>

### <a name="hololens-specific-network-requirements"></a><span data-ttu-id="42573-127">HoloLens Specifieke netwerkvereisten</span><span class="sxs-lookup"><span data-stu-id="42573-127">HoloLens Specific Network Requirements</span></span>

<span data-ttu-id="42573-128">Zorg ervoor dat [deze lijst met](hololens-offline.md) eindpunten is toegestaan op uw netwerkfirewall.</span><span class="sxs-lookup"><span data-stu-id="42573-128">Make sure that [this list](hololens-offline.md) of endpoints are allowed on your network firewall.</span></span> <span data-ttu-id="42573-129">Hierdoor kunnen HoloLens goed werken.</span><span class="sxs-lookup"><span data-stu-id="42573-129">This will enable HoloLens to function properly.</span></span>

### <a name="remote-assist-specific-network-requirements"></a><span data-ttu-id="42573-130">Remote Assist netwerkvereisten</span><span class="sxs-lookup"><span data-stu-id="42573-130">Remote Assist Specific Network Requirements</span></span>

1. <span data-ttu-id="42573-131">De aanbevolen bandbreedte voor optimale prestaties van Remote Assist is 1,5 Mbps.</span><span class="sxs-lookup"><span data-stu-id="42573-131">The recommended bandwidth for optimal performance of Remote Assist is 1.5Mbps.</span></span> <span data-ttu-id="42573-132">Zie de [gedetailleerde netwerkvereisten voor](/MicrosoftTeams/prepare-network) meer informatie.</span><span class="sxs-lookup"><span data-stu-id="42573-132">See the [detailed network requirements](/MicrosoftTeams/prepare-network) for additional information.</span></span>
<span data-ttu-id="42573-133">**(Als u geen netwerksnelheid van ten minste 1,5 Mbps hebt, werkt Remote Assist nog steeds. De kwaliteit kan echter wel onder het werk gaan).**</span><span class="sxs-lookup"><span data-stu-id="42573-133">**(Please note, if you don't network have network speeds of at least 1.5Mbps, Remote Assist will still work. However, quality may suffer).**</span></span>
1. <span data-ttu-id="42573-134">Zorg ervoor dat deze poorten en URL's zijn toegestaan op uw netwerkfirewall om ervoor te zorgen dat Microsoft Teams werken.</span><span class="sxs-lookup"><span data-stu-id="42573-134">Make sure that these ports and URLs are allowed on your network firewall to enable Microsoft Teams to function.</span></span> <span data-ttu-id="42573-135">Blijf up-to-date met [de meest recente lijst met poorten](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams).</span><span class="sxs-lookup"><span data-stu-id="42573-135">Stay up to date with the [latest list of ports](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams).</span></span>

- <span data-ttu-id="42573-136">Meer informatie over de specifieke [netwerkvereisten voor Remote Assist](/dynamics365/mixed-reality/remote-assist/requirements#network-requirements).</span><span class="sxs-lookup"><span data-stu-id="42573-136">Learn more about the specific [Network Requirements for Remote Assist](/dynamics365/mixed-reality/remote-assist/requirements#network-requirements).</span></span> 
- <span data-ttu-id="42573-137">Meer informatie over het [voorbereiden van het netwerk van uw](/MicrosoftTeams/prepare-network) organisatie op Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="42573-137">Learn more about how to [prepare your organization's network for Microsoft Teams](/MicrosoftTeams/prepare-network)</span></span>

### <a name="guides-specific-network-requirements"></a><span data-ttu-id="42573-138">Handleidingen Specifieke netwerkvereisten</span><span class="sxs-lookup"><span data-stu-id="42573-138">Guides Specific Network Requirements</span></span>

<span data-ttu-id="42573-139">Handleidingen vereisen alleen netwerktoegang om de app te downloaden en te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="42573-139">Guides only require network access to download and use the app.</span></span>

## <a name="azure-active-directory-guidance"></a><span data-ttu-id="42573-140">Azure Active Directory Begeleiding</span><span class="sxs-lookup"><span data-stu-id="42573-140">Azure Active Directory Guidance</span></span>

> [!NOTE]
> <span data-ttu-id="42573-141">Deze stap is alleen nodig als uw bedrijf van plan is om de HoloLens.</span><span class="sxs-lookup"><span data-stu-id="42573-141">This step is only necessary if your company plans on managing the HoloLens.</span></span>

1. <span data-ttu-id="42573-142">Zorg ervoor dat u een Azure AD-licentie hebt.</span><span class="sxs-lookup"><span data-stu-id="42573-142">Ensure that you have an Azure AD License.</span></span>
<span data-ttu-id="42573-143">Raadpleeg [HoloLens licentievereisten](hololens-licenses-requirements.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="42573-143">Please [HoloLens Licenses Requirements](hololens-licenses-requirements.md) for additional information.</span></span>

1. <span data-ttu-id="42573-144">Als u van plan bent automatische inschrijving te gebruiken, moet u [Azure AD-inschrijving configureren.](/intune/deploy-use/.set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment)</span><span class="sxs-lookup"><span data-stu-id="42573-144">If you plan on using Auto Enrollment, you will have to [Configure Azure AD enrollment.](/intune/deploy-use/.set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment)</span></span>

1. <span data-ttu-id="42573-145">Zorg ervoor dat de gebruikers van uw bedrijf zich in Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="42573-145">Ensure that your company's users are in Azure Active Directory (Azure AD).</span></span>
<span data-ttu-id="42573-146">Zie de volgende [instructies voor](/azure/active-directory/fundamentals/add-users-azure-active-directory) het toevoegen van gebruikers.</span><span class="sxs-lookup"><span data-stu-id="42573-146">See the following [instructions](/azure/active-directory/fundamentals/add-users-azure-active-directory) for adding users.</span></span>

1. <span data-ttu-id="42573-147">We raden aan dat gebruikers die vergelijkbare licenties nodig hebben, aan dezelfde groep worden toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="42573-147">We suggest that users who need similar licenses are added to the same group.</span></span>
    1. [<span data-ttu-id="42573-148">Een groep maken</span><span class="sxs-lookup"><span data-stu-id="42573-148">Create a Group</span></span>](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    1. [<span data-ttu-id="42573-149">Gebruikers toevoegen aan groepen</span><span class="sxs-lookup"><span data-stu-id="42573-149">Add users to groups</span></span>](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal)

1. <span data-ttu-id="42573-150">Zorg ervoor dat aan de gebruikers van uw bedrijf (of een groep gebruikers) de benodigde licenties zijn toegewezen.</span><span class="sxs-lookup"><span data-stu-id="42573-150">Ensure that your company's users (or group of users) are assigned the necessary licenses.</span></span>
<span data-ttu-id="42573-151">Als u licenties moet toewijzen, volgt u [deze instructies.](/azure/active-directory/fundamentals/license-users-groups)</span><span class="sxs-lookup"><span data-stu-id="42573-151">If you need to assign licenses, follow these [directions](/azure/active-directory/fundamentals/license-users-groups).</span></span>

1. <span data-ttu-id="42573-152">Doe deze stap alleen als van gebruikers wordt verwacht dat ze hun HoloLens/mobiele apparaat bij u inschrijven (er zijn drie opties) Deze stappen zorgen ervoor dat de gebruikers van uw bedrijf (of een groep gebruikers) apparaten kunnen toevoegen.</span><span class="sxs-lookup"><span data-stu-id="42573-152">Only do this step if users are expected to enroll their HoloLens/Mobile device into you (There are three options) These steps ensure that your company's users (or a group of users) can add devices.</span></span>
    1. <span data-ttu-id="42573-153">**Optie 1:** Geef alle gebruikers toestemming om apparaten aan Azure AD toe te sluiten.</span><span class="sxs-lookup"><span data-stu-id="42573-153">**Option 1:** Give all users permission to join devices to Azure AD.</span></span>
<span data-ttu-id="42573-154">**Meld u als Azure Portal aan bij de Azure Portal**  >  **Azure Active Directory**  >  **Apparaten**  >  **Apparaat Instellingen**  >
 **Stel Gebruikers mogen apparaten aan Azure AD deelnemen in op *Alle***</span><span class="sxs-lookup"><span data-stu-id="42573-154">**Sign in to the Azure portal as an administrator** > **Azure Active Directory** > **Devices** > **Device Settings** >
**Set Users may join devices to Azure AD to *All***</span></span>

    1. <span data-ttu-id="42573-155">**Optie 2:** Geselecteerde gebruikers/groepen toestemming geven om apparaten toe te laten bij Azure AD Meld u als beheerder aan bij de **Azure Portal** als beheerder Azure Active Directory Apparaten Apparaat  >    >    >  **Instellingen Gebruikers**  >
 \*\*\*\* 
 ![ mogen apparaten aan Azure AD deelnemen aan Geselecteerde afbeelding waarin Configuratie van apparaten die zijn samengevoegd met Azure AD wordt weer gegeven](images/azure-ad-image.png)</span><span class="sxs-lookup"><span data-stu-id="42573-155">**Option 2:** Give selected users/groups permission to join devices to Azure AD **Sign in to the Azure portal as an administrator** > **Azure Active Directory** > **Devices** > **Device Settings** >
\*\*Set Users may join devices to Azure AD to \*Selected\*\*\*
![Image that shows Configuration of Azure AD Joined Devices](images/azure-ad-image.png)</span></span>

    1. <span data-ttu-id="42573-156">**Optie 3:** U kunt blokkeren dat alle gebruikers hun apparaten toevoegen aan het domein.</span><span class="sxs-lookup"><span data-stu-id="42573-156">**Option 3:** You can block all users from joining their devices to the domain.</span></span> <span data-ttu-id="42573-157">Dit betekent dat alle apparaten handmatig moeten worden ingeschreven.</span><span class="sxs-lookup"><span data-stu-id="42573-157">This means that all devices will need to be manually enrolled.</span></span>

## <a name="mobile-device-manager-guidance"></a><span data-ttu-id="42573-158">Richtlijnen Apparaatbeheer mobiele apparaten</span><span class="sxs-lookup"><span data-stu-id="42573-158">Mobile Device Manager Guidance</span></span>

### <a name="ongoing-device-management"></a><span data-ttu-id="42573-159">Doorlopend apparaatbeheer</span><span class="sxs-lookup"><span data-stu-id="42573-159">Ongoing device management</span></span>

> [!NOTE]
> <span data-ttu-id="42573-160">Deze stap is alleen nodig als uw bedrijf van plan is om de HoloLens.</span><span class="sxs-lookup"><span data-stu-id="42573-160">This step is only necessary if your company plans to manage the HoloLens.</span></span>

<span data-ttu-id="42573-161">Doorlopend apparaatbeheer is afhankelijk van uw infrastructuur voor het beheer van mobiele apparaten.</span><span class="sxs-lookup"><span data-stu-id="42573-161">Ongoing device management will depend on your mobile device management infrastructure.</span></span>  <span data-ttu-id="42573-162">De meeste hebben dezelfde algemene functionaliteit, maar de gebruikersinterface kan sterk verschillen.</span><span class="sxs-lookup"><span data-stu-id="42573-162">Most have the same general functionality but the user interface may vary widely.</span></span>

1. <span data-ttu-id="42573-163">[Met CSP's (Configuration Service Providers)](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) kunt u beheerinstellingen maken en implementeren voor de apparaten in uw netwerk.</span><span class="sxs-lookup"><span data-stu-id="42573-163">[CSPs (Configuration Service Providers)](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) lets you to create and deploy management settings for the devices on your network.</span></span> <span data-ttu-id="42573-164">Zie de [lijst met HoloLens CSP's](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) voor naslag.</span><span class="sxs-lookup"><span data-stu-id="42573-164">See the [list of HoloLens CSPs](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) for reference.</span></span>

1. <span data-ttu-id="42573-165">[Nalevingsbeleid](/intune/device-compliance-get-started) zijn regels en instellingen waar apparaten aan moeten voldoen om compatibel te zijn in uw bedrijfsinfrastructuur.</span><span class="sxs-lookup"><span data-stu-id="42573-165">[Compliance policies](/intune/device-compliance-get-started) are rules and settings that devices must meet to be compliant in your corporate infrastructure.</span></span> <span data-ttu-id="42573-166">Gebruik dit beleid met voorwaardelijke toegang om de toegang tot bedrijfsbronnen te blokkeren voor apparaten die niet compatibel zijn.</span><span class="sxs-lookup"><span data-stu-id="42573-166">Use these policies with Conditional Access to block access to company resources for devices that are non-compliant.</span></span> <span data-ttu-id="42573-167">U kunt bijvoorbeeld een beleid maken waarvoor Bitlocker moet zijn ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="42573-167">For example, you can create a policy that requires Bitlocker be enabled.</span></span>

1. <span data-ttu-id="42573-168">[Nalevingsbeleid maken.](/intune/protect/compliance-policy-create-windows)</span><span class="sxs-lookup"><span data-stu-id="42573-168">[Create Compliance Policy](/intune/protect/compliance-policy-create-windows).</span></span>

1. <span data-ttu-id="42573-169">Met voorwaardelijke toegang kunnen mobiele apparaten en mobiele toepassingen geen toegang krijgen tot bedrijfsbronnen.</span><span class="sxs-lookup"><span data-stu-id="42573-169">Conditional Access allows/denies mobile devices and mobile applications from accessing company resources.</span></span> <span data-ttu-id="42573-170">Twee documenten die u mogelijk nuttig vindt, zijn [Plan your CA Deployment (CA-implementatie plannen)](/azure/active-directory/conditional-access/plan-conditional-access) en Best Practices [(Best practices).](/azure/active-directory/conditional-access/best-practices)</span><span class="sxs-lookup"><span data-stu-id="42573-170">Two documents you may find helpful are [Plan your CA Deployment](/azure/active-directory/conditional-access/plan-conditional-access) and [Best Practices](/azure/active-directory/conditional-access/best-practices).</span></span>

1. <span data-ttu-id="42573-171">[In dit artikel](/intune/fundamentals/windows-holographic-for-business) worden de beheerhulpprogramma's van Intune voor HoloLens.</span><span class="sxs-lookup"><span data-stu-id="42573-171">[This article](/intune/fundamentals/windows-holographic-for-business) talks about Intune's management tools for HoloLens.</span></span>

1. [<span data-ttu-id="42573-172">Een apparaatprofiel maken</span><span class="sxs-lookup"><span data-stu-id="42573-172">Create a device profile</span></span>](/intune/configuration/device-profile-create)

### <a name="manage-updates"></a><span data-ttu-id="42573-173">Updates beheren</span><span class="sxs-lookup"><span data-stu-id="42573-173">Manage updates</span></span>

<span data-ttu-id="42573-174">Intune bevat een functie met de naam Updateringen voor Windows 10-apparaten, waaronder HoloLens 2 en HoloLens v1 (met Holographic for Business).</span><span class="sxs-lookup"><span data-stu-id="42573-174">Intune includes a feature called Update rings for Windows 10 devices, including HoloLens 2 and HoloLens v1 (with Holographic for Business).</span></span> <span data-ttu-id="42573-175">Updateringen bevatten een groep instellingen die bepalen hoe en wanneer updates worden geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="42573-175">Update rings include a group of settings that determine how and when updates are installed.</span></span>

<span data-ttu-id="42573-176">U kunt bijvoorbeeld een onderhoudsvenster maken om updates te installeren of instellen dat opnieuw moet worden opgestart nadat updates zijn geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="42573-176">For example, you can create a maintenance window to install updates, or choose to restart after updates are installed.</span></span>  <span data-ttu-id="42573-177">U kunt er ook voor kiezen om updates voor onbepaalde tijd te onderbreken totdat u klaar bent om bij te werken.</span><span class="sxs-lookup"><span data-stu-id="42573-177">You can also choose to pause updates indefinitely until you're ready to update.</span></span>

<span data-ttu-id="42573-178">Meer informatie over [het configureren van updateringen met Intune](/intune/windows-update-for-business-configure).</span><span class="sxs-lookup"><span data-stu-id="42573-178">Read more about [configuring update rings with Intune](/intune/windows-update-for-business-configure).</span></span>

### <a name="application-management"></a><span data-ttu-id="42573-179">Toepassingsbeheer</span><span class="sxs-lookup"><span data-stu-id="42573-179">Application management</span></span>

<span data-ttu-id="42573-180">Beheer HoloLens toepassingen via:</span><span class="sxs-lookup"><span data-stu-id="42573-180">Manage HoloLens applications through:</span></span>

1. <span data-ttu-id="42573-181">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="42573-181">Microsoft Store</span></span>  
  <span data-ttu-id="42573-182">De Microsoft Store is de beste manier om toepassingen te distribueren en te gebruiken op HoloLens.</span><span class="sxs-lookup"><span data-stu-id="42573-182">The Microsoft Store is the best way to distribute and consume applications on HoloLens.</span></span>  <span data-ttu-id="42573-183">Er is al een groot aantal kerntoepassingen HoloLens beschikbaar in de store of u kunt [uw eigen publiceren.](/windows/uwp/publish/)</span><span class="sxs-lookup"><span data-stu-id="42573-183">There is a great set of core HoloLens applications already available in the store or you can [publish your own](/windows/uwp/publish/).</span></span>  
  <span data-ttu-id="42573-184">Alle toepassingen in de store zijn openbaar beschikbaar voor iedereen, maar als dit niet acceptabel is, checkt u de Microsoft Store voor Bedrijven.</span><span class="sxs-lookup"><span data-stu-id="42573-184">All applications in the store are available publicly to everyone, but if it isn't acceptable, checkout the Microsoft Store for Business.</span></span>  

1. [<span data-ttu-id="42573-185">Microsoft Store voor Bedrijven</span><span class="sxs-lookup"><span data-stu-id="42573-185">Microsoft Store for Business</span></span>](/microsoft-store/)  
  <span data-ttu-id="42573-186">Microsoft Store voor Bedrijven en Education is een aangepaste winkel voor uw bedrijfsomgeving.</span><span class="sxs-lookup"><span data-stu-id="42573-186">Microsoft Store for Business and Education is a custom store for your corporate environment.</span></span>  <span data-ttu-id="42573-187">Hiermee kunt u de Microsoft Store ingebouwde Windows 10 en HoloLens apps voor uw organisatie zoeken, verkrijgen, distribueren en beheren.</span><span class="sxs-lookup"><span data-stu-id="42573-187">It lets you use the Microsoft Store built into Windows 10 and HoloLens to find, acquire, distribute, and manage apps for your organization.</span></span>  <span data-ttu-id="42573-188">U kunt hiermee ook apps implementeren die specifiek zijn voor uw commerciële omgeving, maar niet voor de hele wereld.</span><span class="sxs-lookup"><span data-stu-id="42573-188">It also lets you deploy apps that are specific to your commercial environment but not to the world.</span></span>

1. <span data-ttu-id="42573-189">Implementatie en beheer van toepassingen via Intune of een andere beheeroplossing voor mobiele apparaten</span><span class="sxs-lookup"><span data-stu-id="42573-189">Application deployment and management via Intune or another mobile device management solution</span></span>  
  <span data-ttu-id="42573-190">De meeste oplossingen voor het beheer van mobiele apparaten, waaronder Intune, bieden een manier om Line-Of-Business-toepassingen rechtstreeks te implementeren op een set ingeschreven apparaten.</span><span class="sxs-lookup"><span data-stu-id="42573-190">Most mobile device management solutions, including Intune, provide a way to deploy line of business applications directly to a set of enrolled devices.</span></span>  <span data-ttu-id="42573-191">Zie dit artikel voor installatie [van de Intune-app.](/intune/apps-deploy)</span><span class="sxs-lookup"><span data-stu-id="42573-191">See this article for [Intune app install](/intune/apps-deploy).</span></span>

1. <span data-ttu-id="42573-192">_niet aanbevolen_ Apparaatportal</span><span class="sxs-lookup"><span data-stu-id="42573-192">_not recommended_ Device Portal</span></span>  
  <span data-ttu-id="42573-193">Toepassingen kunnen ook rechtstreeks op een HoloLens met behulp van de Windows Apparaatportal.</span><span class="sxs-lookup"><span data-stu-id="42573-193">Applications can also be installed on HoloLens directly using the Windows Device Portal.</span></span>  <span data-ttu-id="42573-194">Dit wordt niet aanbevolen omdat de ontwikkelaarsmodus moet worden ingeschakeld voor het gebruik van de apparaatportal.</span><span class="sxs-lookup"><span data-stu-id="42573-194">This isn't recommended since Developer Mode has to be enabled to use the device portal.</span></span>

<span data-ttu-id="42573-195">Lees meer over [het installeren van apps op HoloLens](hololens-install-apps.md).</span><span class="sxs-lookup"><span data-stu-id="42573-195">Read more about [installing apps on HoloLens](hololens-install-apps.md).</span></span>

### <a name="certificates"></a><span data-ttu-id="42573-196">Certificaten</span><span class="sxs-lookup"><span data-stu-id="42573-196">Certificates</span></span>

<span data-ttu-id="42573-197">U kunt certificaten distribueren via uw MDM-provider.</span><span class="sxs-lookup"><span data-stu-id="42573-197">You can distribute certificates through your MDM provider.</span></span> <span data-ttu-id="42573-198">Als uw bedrijf certificaten vereist, ondersteunt Intune PKCS, PFX en SCEP.</span><span class="sxs-lookup"><span data-stu-id="42573-198">If your company requires certificates, Intune supports PKCS, PFX, and SCEP.</span></span> <span data-ttu-id="42573-199">Het is belangrijk om te begrijpen welk certificaat het meest voor uw bedrijf is.</span><span class="sxs-lookup"><span data-stu-id="42573-199">It is important to understand which certificate is right for your company.</span></span> <span data-ttu-id="42573-200">Raadpleeg de documentatie [over certificaatconfiguraties](/intune/protect/certificates-configure) om te bepalen welk certificaat het beste voor u is.</span><span class="sxs-lookup"><span data-stu-id="42573-200">Please visit the [certificate configurations](/intune/protect/certificates-configure) documentation to determine which cert is best for you.</span></span> <span data-ttu-id="42573-201">Als u van plan bent certificaten te gebruiken voor HoloLens verificatie, is PFX of SCEP mogelijk de juiste voor u.</span><span class="sxs-lookup"><span data-stu-id="42573-201">If you plan to use certificates for HoloLens Authentication, PFX or SCEP may be right for you.</span></span>

<span data-ttu-id="42573-202">Zie de volgende stappen voor het gebruik van [SCEP.](/intune/protect/certificates-profile-scep)</span><span class="sxs-lookup"><span data-stu-id="42573-202">See the following steps for using [SCEP](/intune/protect/certificates-profile-scep).</span></span>

### <a name="how-to-upgrade-to-holographics-for-business-commercial-suite"></a><span data-ttu-id="42573-203">Upgraden naar Holographics for Business Commercial Suite</span><span class="sxs-lookup"><span data-stu-id="42573-203">How to Upgrade to Holographics for Business Commercial Suite</span></span>

> [!NOTE]
> <span data-ttu-id="42573-204">Windows Holographics for Business (commerciële suite) is alleen bedoeld voor apparaten HoloLens eerste generatie.</span><span class="sxs-lookup"><span data-stu-id="42573-204">Windows Holographics for Business (commercial suite) is only intended for HoloLens 1st gen devices.</span></span> <span data-ttu-id="42573-205">Het profiel wordt niet toegepast op HoloLens 2 apparaten.</span><span class="sxs-lookup"><span data-stu-id="42573-205">The profile will not be applied to HoloLens 2 devices.</span></span>

<span data-ttu-id="42573-206">U vindt een routebeschrijving voor het upgraden naar de commerciële suite in de [documentatie voor de holographic-upgrade.](/intune/configuration/holographic-upgrade)</span><span class="sxs-lookup"><span data-stu-id="42573-206">You can find directions for upgrading to the commercial suite in the [holographic upgrade](/intune/configuration/holographic-upgrade) documentation.</span></span>

### <a name="how-to-configure-kiosk-mode-using-microsoft-intune"></a><span data-ttu-id="42573-207">Kioskmodus configureren met Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="42573-207">How to Configure Kiosk Mode Using Microsoft Intune</span></span>

1. <span data-ttu-id="42573-208">Synchroniseer Microsoft Store naar Intune (zie de volgende [instructies).](/intune/apps/windows-store-for-business)</span><span class="sxs-lookup"><span data-stu-id="42573-208">Sync Microsoft Store to Intune (See the following [instructions](/intune/apps/windows-store-for-business)).</span></span>

1. <span data-ttu-id="42573-209">Uw app-instellingen controleren</span><span class="sxs-lookup"><span data-stu-id="42573-209">Check your app settings</span></span>
    1. <span data-ttu-id="42573-210">Meld u aan bij Microsoft Store Business-account</span><span class="sxs-lookup"><span data-stu-id="42573-210">Log into your Microsoft Store Business account</span></span>
    1. <span data-ttu-id="42573-211">**> producten en services beheren > apps en software-> Selecteer de app die u wilt synchroniseren > Beschikbaarheid van de privéopslag > Selecteer 'Iedereen' of 'Specifieke groepen'**</span><span class="sxs-lookup"><span data-stu-id="42573-211">**Manage > Products and Services > Apps and Software > Select the app you want to sync > Private Store Availability > Select "Everyone" or "Specific Groups"**</span></span>
        >[!NOTE]
        ><span data-ttu-id="42573-212">Als u de gezochte app niet ziet, moet u de app 'downloaden' door in de Store te zoeken naar uw app.</span><span class="sxs-lookup"><span data-stu-id="42573-212">If you don't see the app you want, you will have to "get" the app by searching the store for your app.</span></span> <span data-ttu-id="42573-213">Klik op de balk Zoeken in de rechterbovenhoek > typ de naam van de app > klik op de app om **> 'Get' te selecteren.**</span><span class="sxs-lookup"><span data-stu-id="42573-213">**Click the "Search" bar in the upper right-hand corner > type in the name of the app > click on the app > select "Get"**.</span></span>
    1. <span data-ttu-id="42573-214">Als u uw apps niet ziet in **Intune > Client Apps > Apps,** moet u uw apps mogelijk [opnieuw](/intune/apps/windows-store-for-business#synchronize-apps) synchroniseren.</span><span class="sxs-lookup"><span data-stu-id="42573-214">If you do not see your apps in **Intune > Client Apps > Apps** , you may have to [sync your apps](/intune/apps/windows-store-for-business#synchronize-apps) again.</span></span>

1. [<span data-ttu-id="42573-215">Een apparaatprofiel maken voor de kioskmodus</span><span class="sxs-lookup"><span data-stu-id="42573-215">Create a device profile for Kiosk mode</span></span>](/intune/configuration/kiosk-settings#create-the-profile)

> [!NOTE]
> <span data-ttu-id="42573-216">U kunt verschillende gebruikers configureren voor verschillende kioskmoduservaringen door 'Azure AD' te gebruiken als aanmeldingstype gebruiker.</span><span class="sxs-lookup"><span data-stu-id="42573-216">You can configure different users to have different Kiosk Mode experiences by using "Azure AD" as the "User logon type".</span></span> <span data-ttu-id="42573-217">Deze optie is echter alleen beschikbaar in de kioskmodus voor meerdere apps.</span><span class="sxs-lookup"><span data-stu-id="42573-217">However, this option is only available in Multi-App kiosk mode.</span></span> <span data-ttu-id="42573-218">De kioskmodus voor meerdere apps werkt met slechts één app en met meerdere apps.</span><span class="sxs-lookup"><span data-stu-id="42573-218">Multi-App kiosk mode will work with only one app as well as multiple apps.</span></span>

![Afbeelding van de configuratie van de kioskmodus in Intune](images/aad-kioskmode.png)

<span data-ttu-id="42573-220">Raadpleeg de documentatie van uw provider voor instructies voor andere MDM-services.</span><span class="sxs-lookup"><span data-stu-id="42573-220">For other MDM services, check your provider's documentation for instructions.</span></span> <span data-ttu-id="42573-221">Raadpleeg de instructies [HoloLens kiosk als](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) u een aangepaste instelling en volledige XML-configuratie moet gebruiken om een kiosk in uw MDM-service in te stellen.</span><span class="sxs-lookup"><span data-stu-id="42573-221">Refer to the [HoloLens kiosk](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) instructions if you need to use a custom setting and full XML configuration to set up a kiosk in your MDM service.</span></span>

## <a name="certificates-and-authentication"></a><span data-ttu-id="42573-222">Certificaten en verificatie</span><span class="sxs-lookup"><span data-stu-id="42573-222">Certificates and Authentication</span></span>

<span data-ttu-id="42573-223">Certificaten kunnen worden geïmplementeerd via uw MDM (zie Certificaten in de [sectie MDM).](hololens-commercial-infrastructure.md#mobile-device-manager-guidance)</span><span class="sxs-lookup"><span data-stu-id="42573-223">Certificates can be deployed via you MDM (see "certificates" in the [MDM Section](hololens-commercial-infrastructure.md#mobile-device-manager-guidance)).</span></span> <span data-ttu-id="42573-224">Certificaten kunnen ook worden geïmplementeerd op de HoloLens via pakket inrichten.</span><span class="sxs-lookup"><span data-stu-id="42573-224">Certificates can also be deployed to the HoloLens through package provisioning.</span></span> <span data-ttu-id="42573-225">Zie HoloLens [Inrichting voor](hololens-provisioning.md) meer informatie.</span><span class="sxs-lookup"><span data-stu-id="42573-225">Please see [HoloLens Provisioning](hololens-provisioning.md) for additional information.</span></span>

### <a name="additional-intune-quick-links"></a><span data-ttu-id="42573-226">Aanvullende Snelkoppelingen voor Intune</span><span class="sxs-lookup"><span data-stu-id="42573-226">Additional Intune Quick Links</span></span>

1. <span data-ttu-id="42573-227">[Profielen maken:](/intune/configuration/device-profile-create) Met profielen kunt u instellingen toevoegen en configureren die naar de apparaten in uw organisatie worden pushen.</span><span class="sxs-lookup"><span data-stu-id="42573-227">[Create Profiles:](/intune/configuration/device-profile-create) Profiles allow you to add and configure settings that will be pushed to the devices in your organization.</span></span>

