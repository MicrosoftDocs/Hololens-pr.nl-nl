---
title: 'Implementatiehandleiding : cloudgeconnecteerde HoloLens 2 implementatie op schaal met Remote Assist - Configureren'
description: Meer informatie over het instellen van configuraties voor het HoloLens apparaten via een cloudnetwerk op schaal met Remote Assist.
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
ms.openlocfilehash: eb96f1cdc799551297c0373268e8cc8f35c6bd06
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635140"
---
# <a name="configure---cloud-connected-guide"></a><span data-ttu-id="b4edb-104">Configureren - Handleiding voor verbonden cloud</span><span class="sxs-lookup"><span data-stu-id="b4edb-104">Configure - Cloud connected Guide</span></span>

<span data-ttu-id="b4edb-105">In deze sectie van de handleiding&#39;het instellen van automatische inschrijving voor uw tenant en het toepassen van licenties voor zowel Intune als Remote Assist.</span><span class="sxs-lookup"><span data-stu-id="b4edb-105">In this section of the guide, we&#39;ll go over how to set up Auto Enrollment for your tenant, and how to apply licenses for both Intune and Remote Assist.</span></span>

## <a name="azure-users-and-groups"></a><span data-ttu-id="b4edb-106">Azure-gebruikers en -groepen</span><span class="sxs-lookup"><span data-stu-id="b4edb-106">Azure Users and Groups</span></span>

<span data-ttu-id="b4edb-107">Azure en Intune met deze extensie gebruiken gebruikers en groepen om configuraties en licenties toe te wijzen.</span><span class="sxs-lookup"><span data-stu-id="b4edb-107">Azure, and Intune by that extension, uses users and groups to help assign configurations and licenses.</span></span> <span data-ttu-id="b4edb-108">Omwille van het valideren van deze implementatiestroom en het kunnen maken van een Remote Assist-aanroep van de ene gebruiker naar de andere, hebt&#39;twee gebruikersaccounts nodig.</span><span class="sxs-lookup"><span data-stu-id="b4edb-108">For the sake of validating this deployment flow and being able to make a Remote Assist call from one user to another you&#39;ll need two user accounts.</span></span>

<span data-ttu-id="b4edb-109">We kunnen één gebruikersgroep maken om licenties toe te wijzen.</span><span class="sxs-lookup"><span data-stu-id="b4edb-109">We can make a single user group for the purpose of assigning licenses.</span></span> <span data-ttu-id="b4edb-110">We kunnen beide gebruikers aan dezelfde groep deelnemen en een licentie voor Intune en Remote Assist aan die groep.</span><span class="sxs-lookup"><span data-stu-id="b4edb-110">We can join both users to the same group and apply a license for Intune and Remote Assist to that group.</span></span>

<span data-ttu-id="b4edb-111">Als u geen&#39;hebt tot twee Azure AD-accounts in een gebruikersgroep, kunt u deze gebruiken; hier zijn de snelstartgidsen voor:</span><span class="sxs-lookup"><span data-stu-id="b4edb-111">If you don&#39;t already have access to two Azure AD accounts in a user group you can use; here are the quick start guides for:</span></span>

- [<span data-ttu-id="b4edb-112">Een gebruiker maken</span><span class="sxs-lookup"><span data-stu-id="b4edb-112">How to create a user</span></span>](/mem/intune/fundamentals/quickstart-create-user)
- [<span data-ttu-id="b4edb-113">Een groep maken</span><span class="sxs-lookup"><span data-stu-id="b4edb-113">How to create a group</span></span>](/mem/intune/fundamentals/quickstart-create-group)
- <span data-ttu-id="b4edb-114">[Gebruikers toevoegen aan een groep](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) : gemaakte gebruikers toevoegen om een groep te maken</span><span class="sxs-lookup"><span data-stu-id="b4edb-114">[Add users to a group](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – Add created users to create group</span></span>
- <span data-ttu-id="b4edb-115">[Azure AD configureren zodat een gebruikersgroep apparaten kan deelnemen:](/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) zorg ervoor dat de nieuwe gebruikersgroep toestemming heeft om apparaten in te schrijven bij Azure AD</span><span class="sxs-lookup"><span data-stu-id="b4edb-115">[Configure Azure AD to allow a User Group to join devices](/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) – Ensure new user group has permission to enroll devices to Azure AD</span></span>

## <a name="auto-enrollment-on-hololens-2"></a><span data-ttu-id="b4edb-116">Automatische inschrijving op HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="b4edb-116">Auto Enrollment on HoloLens 2</span></span>

<span data-ttu-id="b4edb-117">Voor een soepele en naadloze ervaring is het instellen van Azure Active Directory Join (AADJ) en automatische inschrijving bij Intune voor HoloLens 2-apparaten de beste manier.</span><span class="sxs-lookup"><span data-stu-id="b4edb-117">In order to have a smooth and seamless experience, setting up Azure Active Directory Join (AADJ) and Auto Enrollment to Intune for HoloLens 2 devices is the way to go.</span></span> <span data-ttu-id="b4edb-118">Hierdoor kunnen gebruikers hun aanmeldingsreferenties van hun organisatie invoeren tijdens OOBE en automatisch registreren bij Azure AD en het apparaat registreren bij MDM.</span><span class="sxs-lookup"><span data-stu-id="b4edb-118">This will allow users to input their organization log-in credentials during OOBE and automatically register with Azure AD and enroll the device into MDM.</span></span>

<span data-ttu-id="b4edb-119">Met behulp [Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home)kunt u services selecteren en door een paar pagina's navigeren totdat u Een gratis proefversie Premium selecteren.</span><span class="sxs-lookup"><span data-stu-id="b4edb-119">By using [Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home), we can select services and navigate a few pages until we can select Get a Premium trial.</span></span> <span data-ttu-id="b4edb-120">Mogelijk ziet u dat er Azure Active Directory Premium 1 en 2 is, voor Automatische inschrijving P1 voldoende is.</span><span class="sxs-lookup"><span data-stu-id="b4edb-120">You may notice there is Azure Active Directory Premium 1 and 2, for Automatic Enrollment P1 is sufficient.</span></span> <span data-ttu-id="b4edb-121">We kunnen Intune selecteren, het gebruikersbereik voor automatische inschrijving selecteren en de groep selecteren die eerder is gemaakt.</span><span class="sxs-lookup"><span data-stu-id="b4edb-121">We can select Intune and select the user scope for automatic enrollment, and select the group that was previously created.</span></span>

<span data-ttu-id="b4edb-122">Lees de handleiding over het inschakelen van automatische inschrijving voor [Intune](/mem/intune/enrollment/quickstart-setup-auto-enrollment)voor meer informatie en stappen.</span><span class="sxs-lookup"><span data-stu-id="b4edb-122">For full details and steps read the guide on [how to enable auto enrollment for Intune](/mem/intune/enrollment/quickstart-setup-auto-enrollment).</span></span>

## <a name="application-licenses"></a><span data-ttu-id="b4edb-123">Toepassingslicenties</span><span class="sxs-lookup"><span data-stu-id="b4edb-123">Application Licenses</span></span>

<span data-ttu-id="b4edb-124">Met een toepassingslicentie kan een gebruiker door het bedrijf gekochte apps installeren of upgraden van een gratis proefversie naar de volledige versie van een app.</span><span class="sxs-lookup"><span data-stu-id="b4edb-124">An application license allows a user to either install company purchased Apps or upgrade from a free trial to the full version of an app.</span></span> <span data-ttu-id="b4edb-125">Toepassingslicenties kunnen worden toegepast op gebruikers, gebruikersgroepen of apparaatgroepen.</span><span class="sxs-lookup"><span data-stu-id="b4edb-125">Application licenses can be applied to either users, user groups, or device groups.</span></span> <span data-ttu-id="b4edb-126">U&#39;licenties Remote Assist gebruikers in uw organisatie nodig hebben om deze te Remote Assist.</span><span class="sxs-lookup"><span data-stu-id="b4edb-126">You&#39;ll need Remote Assist licenses for users in your organization to use Remote Assist.</span></span> <span data-ttu-id="b4edb-127">Voor deze handleiding wijzen we de Remote Assist toe aan de gebruikersgroep die we hierboven hebben gemaakt in [Azure Users and Groups](hololens2-cloud-connected-configure.md#azure-users-and-groups).</span><span class="sxs-lookup"><span data-stu-id="b4edb-127">For the purpose of this guide we'll assign Remote Assist licenses to the user group we created above in [Azure Users and Groups](hololens2-cloud-connected-configure.md#azure-users-and-groups).</span></span>

<span data-ttu-id="b4edb-128">De vereisten voor licenties kunnen verschillen, afhankelijk van of de gebruiker de Remote Assist-aanroep maakt vanaf een apparaat of een externe samenwerker van Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b4edb-128">The requirements for licenses can be different depending on if the user will be making the Remote Assist call from a device or will be a remote collaborator from Microsoft Teams.</span></span> <span data-ttu-id="b4edb-129">Standaard zijn de Remote Assist en Teams selectievakjes gemarkeerd.</span><span class="sxs-lookup"><span data-stu-id="b4edb-129">By default the Remote Assist and Teams check boxes are both marked.</span></span> <span data-ttu-id="b4edb-130">Voor deze handleiding raden we u aan de standaardvakken ingeschakeld te laten.</span><span class="sxs-lookup"><span data-stu-id="b4edb-130">For the purposes of this guide, we suggest leaving the default boxes checked.</span></span>

1. <span data-ttu-id="b4edb-131">Meer informatie over de verschillende [licentie- en productvereisten per rol](/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role).</span><span class="sxs-lookup"><span data-stu-id="b4edb-131">Learn more about the different [Licensing and product requirements per role](/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role).</span></span> <span data-ttu-id="b4edb-132">Er zijn een aantal verschillende typen Remote Assist licenties, dus zorg ervoor dat u de juiste licenties voor uw behoeften hebt.</span><span class="sxs-lookup"><span data-stu-id="b4edb-132">There are a few different types of Remote Assist licenses so be sure to get the correct ones for your needs.</span></span>
2. <span data-ttu-id="b4edb-133">U&#39;de licentie [verkrijgen.](/dynamics365/mixed-reality/remote-assist/buy-remote-assist)</span><span class="sxs-lookup"><span data-stu-id="b4edb-133">You&#39;ll need to [acquire the license](/dynamics365/mixed-reality/remote-assist/buy-remote-assist).</span></span>
3. <span data-ttu-id="b4edb-134">[Pas uw licenties toe](/dynamics365/mixed-reality/remote-assist/deploy-remote-assist) op de groep.</span><span class="sxs-lookup"><span data-stu-id="b4edb-134">[Apply your licenses](/dynamics365/mixed-reality/remote-assist/deploy-remote-assist) to the group.</span></span>

## <a name="next-step"></a><span data-ttu-id="b4edb-135">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="b4edb-135">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="b4edb-136">Cloudgeconnecteerde implementatie - Implementeren</span><span class="sxs-lookup"><span data-stu-id="b4edb-136">Cloud connected deployment - Deploy</span></span>](hololens2-cloud-connected-deploy.md)