---
title: 'Implementatiehandleiding : Zakelijk verbonden HoloLens 2 met Dynamics 365 Guides - Implementeren'
description: Meer informatie over het instellen van implementaties van HoloLens 2 apparaten via een bedrijfsnetwerk verbonden met Dynamics 365 Guides.
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
ms.openlocfilehash: 6407517bca9efd02fdaf45a78cba7a215ec05670
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/12/2021
ms.locfileid: "113637061"
---
# <a name="deploy---corporate-connected-guide"></a><span data-ttu-id="fdddf-104">Implementeren - Handleiding voor verbonden bedrijfsgegevens</span><span class="sxs-lookup"><span data-stu-id="fdddf-104">Deploy - Corporate Connected Guide</span></span>

<span data-ttu-id="fdddf-105">Een belangrijk onderdeel van elke implementatie is ervoor te zorgen dat uw implementatie goed is ingesteld voordat u deze zelf test om een soepele ervaring voor de eindgebruiker te garanderen.</span><span class="sxs-lookup"><span data-stu-id="fdddf-105">An important part of each deployment is ensuring that your deployment is properly set up before testing it yourself to ensure a smooth experience for the end user.</span></span>

<span data-ttu-id="fdddf-106">Omdat we het Wi-Fi-certificaat via MDM implementeren, moeten we in eerste instantie HoloLens instellen en apparaten inschrijven op een open Wi-Fi-netwerk of een netwerk waarvoor het certificaat niet vereist is.</span><span class="sxs-lookup"><span data-stu-id="fdddf-106">Because we are deploying the Wi-Fi certificate via MDM, we'll need to initially set up HoloLens and enroll devices on an open Wi-Fi network, or a network that doesn't require the certificate.</span></span> <span data-ttu-id="fdddf-107">Zodra de HoloLens OOBE is voltooid en ingeschreven, ontvangt het apparaat het netwerkcertificaat en de LOB die eerder zijn geconfigureerd en kunnen we controleren of beide zijn ontvangen door het apparaat.</span><span class="sxs-lookup"><span data-stu-id="fdddf-107">Once the HoloLens has finished OOBE and Enrolled, the device will receive the network certificate and LOB configured previously and we'll be able to validate both were received by the device.</span></span>

<span data-ttu-id="fdddf-108">Daarna kunt u bevestigen dat u zowel een testhandleiding kunt maken als gebruiken.</span><span class="sxs-lookup"><span data-stu-id="fdddf-108">Afterwards, you'll be able confirm you can both author and operate a test Guide.</span></span>

## <a name="enrollment-validation"></a><span data-ttu-id="fdddf-109">Validatie van inschrijving</span><span class="sxs-lookup"><span data-stu-id="fdddf-109">Enrollment Validation</span></span>

<span data-ttu-id="fdddf-110">Nu alles goed is geconfigureerd voor Azure AD- en MDM-inschrijving, moet de rest een uitlijning zijn.</span><span class="sxs-lookup"><span data-stu-id="fdddf-110">Now that everything is properly configured for Azure AD and MDM Enrollment, the rest should now be a snap.</span></span> <span data-ttu-id="fdddf-111">U hebt een Wi-Fi- en HoloLens-apparaat en een van de eerder geconfigureerde Azure AD-gebruikersaccounts nodig.</span><span class="sxs-lookup"><span data-stu-id="fdddf-111">You'll need a Wi-Fi connection and the HoloLens device, and one of the previously configured Azure AD user accounts.</span></span>

<span data-ttu-id="fdddf-112">Als uw apparaat momenteel niet de status fabrieksinstellingen heeft, is het nu een goed moment om het apparaat te [reflashen.](/hololens/hololens-recovery#clean-reflash-the-device)</span><span class="sxs-lookup"><span data-stu-id="fdddf-112">If your device isn't currently sitting in a factory settings state, now would be a good time to [reflash the device](/hololens/hololens-recovery#clean-reflash-the-device).</span></span>

1. <span data-ttu-id="fdddf-113">Zodra uw apparaat zich in OOBE heeft, moet u beginnen met communiceren en de prompts volgen.</span><span class="sxs-lookup"><span data-stu-id="fdddf-113">Once your device is in OOBE, you'll need to start interacting and following the prompts.</span></span>

2. <span data-ttu-id="fdddf-114">Verbinding maken verbinding maken met een Wi-Fi netwerk waarvoor geen certificaten nodig zijn om lid te worden van de Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="fdddf-114">Connect to an open Wi-Fi network that does not require certificates to join the Wi-Fi.</span></span> <span data-ttu-id="fdddf-115">Hierdoor kan het apparaat het certificaat downloaden dat na de eerste installatie op de Wi-Fi organisatie kan worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="fdddf-115">This will allow the device to download the certificate to be used on the organization's Wi-Fi after initial setup.</span></span>

3. <span data-ttu-id="fdddf-116">De kritieke vraag wordt wanneer u wordt gevraagd **of Wie eigenaar van deze HoloLens?**</span><span class="sxs-lookup"><span data-stu-id="fdddf-116">The critical prompt will be when you are asked **Who owns this HoloLens?**</span></span> <span data-ttu-id="fdddf-117">Selecteer **Mijn werk of school is eigenaar en** voer de referenties van uw Azure AD-account in.</span><span class="sxs-lookup"><span data-stu-id="fdddf-117">Select **My work or school owns it** and enter your Azure AD account credentials.</span></span>

4. <span data-ttu-id="fdddf-118">Wanneer de inschrijving is geslaagd, wordt u gevraagd een pincode in te stellen.</span><span class="sxs-lookup"><span data-stu-id="fdddf-118">When enrollment is successful, you'll be prompted to set up a PIN.</span></span> <span data-ttu-id="fdddf-119">Deze pincode is uniek voor dit apparaat voor deze gebruiker.</span><span class="sxs-lookup"><span data-stu-id="fdddf-119">This PIN is unique to this device for this user.</span></span> <span data-ttu-id="fdddf-120">U wordt ook gevraagd om Iris-scans, spraakgegevens en telemetrie-instellingen en tot slot kunt u leren hoe u het startmenu opent en OOBE voltooit.</span><span class="sxs-lookup"><span data-stu-id="fdddf-120">You will also be prompted for Iris scans, voice data, and telemetry settings and finally, you'll be able to learn how to open the start menu and complete OOBE.</span></span>

5. <span data-ttu-id="fdddf-121">Zodra u op de start Mixed Reality, opent u de Startmenu met behulp van de **beweging Start** die u zojuist hebt geleerd.</span><span class="sxs-lookup"><span data-stu-id="fdddf-121">Once you land in the Mixed Reality Home, open the Start menu using the **Start gesture** you just learned.</span></span>

6. <span data-ttu-id="fdddf-122">Selecteer de **Instellingen app** en selecteer **Systeem.**</span><span class="sxs-lookup"><span data-stu-id="fdddf-122">Select the **Settings** app and select **System**.</span></span> <span data-ttu-id="fdddf-123">Het eerste stukje informatie dat u ziet, is de Apparaatnaam, die voor uw HoloLens 2 HOLOLENS wordt, gevolgd door een &quot; &quot; tekenreeks van zes tekens.</span><span class="sxs-lookup"><span data-stu-id="fdddf-123">The first piece of information you'll see is your Device name, which for your HoloLens 2 device will be &quot;HOLOLENS-&quot; followed by a six character string.</span></span>

7. <span data-ttu-id="fdddf-124">Noteer deze naam.</span><span class="sxs-lookup"><span data-stu-id="fdddf-124">Take note of this name.</span></span>

    ![HoloLens 2 Instellingen scherm](./images/hololens2-settings-about.jpg)

8. <span data-ttu-id="fdddf-126">Controleer of uw apparaat is verbonden met Azure AD.</span><span class="sxs-lookup"><span data-stu-id="fdddf-126">Verify that your device is successfully joined to Azure AD.</span></span> <span data-ttu-id="fdddf-127">Er zijn twee manieren:</span><span class="sxs-lookup"><span data-stu-id="fdddf-127">There are two ways;</span></span>

    1.  <span data-ttu-id="fdddf-128">De Instellingen app.</span><span class="sxs-lookup"><span data-stu-id="fdddf-128">The Settings app.</span></span> <span data-ttu-id="fdddf-129">Selecteer **Instellingen** **Accounts Toegang tot** werk of  ->  **school.**</span><span class="sxs-lookup"><span data-stu-id="fdddf-129">From **Settings** select **Accounts** -> **Access work or school**.</span></span> <span data-ttu-id="fdddf-130">In dit scherm kunt u controleren of u bent ingeschreven door Verbonden met naamofAAD te zien&#39;&quot; Azure AD.</span><span class="sxs-lookup"><span data-stu-id="fdddf-130">From this screen, you can verify you are successfully enrolled by seeing &quot;Connected to nameofAAD&#39;s Azure AD.</span></span> <span data-ttu-id="fdddf-131">Verbonden door *yourusername@nameofAAD.onmicrosoft.com* .</span><span class="sxs-lookup"><span data-stu-id="fdddf-131">Connected by *yourusername@nameofAAD.onmicrosoft.com*.</span></span> <span data-ttu-id="fdddf-132">Hiermee wordt gecontroleerd of uw apparaat is verbonden met uw organisatie&#39;Azure AD.</span><span class="sxs-lookup"><span data-stu-id="fdddf-132">This will verify your device is joined to your organization&#39;s Azure AD.</span></span>

    1. <span data-ttu-id="fdddf-133">De [Azure Portal](https://portal.azure.com/#home).</span><span class="sxs-lookup"><span data-stu-id="fdddf-133">The [Azure portal](https://portal.azure.com/#home).</span></span> <span data-ttu-id="fdddf-134">Ga naar **Azure Active Directory**  ->  **Apparaten**  ->  **Alle apparaten** en zoek de apparaatnaam.</span><span class="sxs-lookup"><span data-stu-id="fdddf-134">Go to **Azure Active Directory** -> **Devices** -> **All devices**, and search the device name.</span></span> <span data-ttu-id="fdddf-135">Onder Jointype wordt deze als 'Azure AD-lid' laten zien.</span><span class="sxs-lookup"><span data-stu-id="fdddf-135">Under Join Type, it will show as being 'Azure AD Joined'.</span></span>
        <span data-ttu-id="fdddf-136">![Jointype controleren in Azure AD](./images/hololens2-devices-all-devices.png)</span><span class="sxs-lookup"><span data-stu-id="fdddf-136">![Verify Join Type in Azure AD](./images/hololens2-devices-all-devices.png)</span></span>

9. <span data-ttu-id="fdddf-137">Controleer of uw apparaat is ingeschreven bij MDM.</span><span class="sxs-lookup"><span data-stu-id="fdddf-137">Verify that your device is enrolled with MDM.</span></span> <span data-ttu-id="fdddf-138">Er zijn twee manieren:</span><span class="sxs-lookup"><span data-stu-id="fdddf-138">There are two ways;</span></span>

    1. <span data-ttu-id="fdddf-139">Selecteer **Instellingen**, **selecteer Accounts Toegang** tot werk of  ->  **school.**</span><span class="sxs-lookup"><span data-stu-id="fdddf-139">From **Settings**, select **Accounts** -> **Access work or school**.</span></span> <span data-ttu-id="fdddf-140">In dit scherm kunt u controleren of u bent ingeschreven door Verbonden met naamofAAD te zien&#39;&quot; Azure AD.</span><span class="sxs-lookup"><span data-stu-id="fdddf-140">From this screen, you can verify you are successfully enrolled by seeing &quot;Connected to nameofAAD&#39;s Azure AD.</span></span> <span data-ttu-id="fdddf-141">Verbonden door *yourusername@nameofAAD.onmicrosoft.com* .</span><span class="sxs-lookup"><span data-stu-id="fdddf-141">Connected by *yourusername@nameofAAD.onmicrosoft.com*.</span></span> <span data-ttu-id="fdddf-142">Selecteer vanuit dit Toegangsaccount voor werk of school de optie Verbonden &quot; met naamofAAD&#39;Azure AD.</span><span class="sxs-lookup"><span data-stu-id="fdddf-142">From this Access work or school account by selecting &quot;Connected to nameofAAD&#39;s Azure AD.</span></span> <span data-ttu-id="fdddf-143">Verbonden door yourusername@nameofAAD.onmicrosoft.com &quot; en selecteer de knop **Info.**</span><span class="sxs-lookup"><span data-stu-id="fdddf-143">Connected by yourusername@nameofAAD.onmicrosoft.com&quot; and select the **Info** button.</span></span>

    1. <span data-ttu-id="fdddf-144">[Microsoft Endpoint Manager-beheercentrum.](https://endpoint.microsoft.com/#home)</span><span class="sxs-lookup"><span data-stu-id="fdddf-144">[Microsoft Endpoint Manager Admin Center](https://endpoint.microsoft.com/#home).</span></span> <span data-ttu-id="fdddf-145">Meld u aan en selecteer **Apparaten** en **vervolgens Alle apparaten.**</span><span class="sxs-lookup"><span data-stu-id="fdddf-145">Log in and select  **Devices**  then  **All devices**.</span></span> <span data-ttu-id="fdddf-146">Hier kunt u de naam van HoloLens apparaat&#39;zoeken.</span><span class="sxs-lookup"><span data-stu-id="fdddf-146">From here, you can search your HoloLens device&#39;s name.</span></span> <span data-ttu-id="fdddf-147">Als het goed is, kunt u uw HoloLens in Intune.</span><span class="sxs-lookup"><span data-stu-id="fdddf-147">You should be able to see your HoloLens listed on Intune.</span></span>

        ![Beheerd door Intune verifiëren in Azure AD](./images/hololens2-devices-all-devices2.png)


## <a name="wi-fi-certificate-validation"></a><span data-ttu-id="fdddf-149">Wi-Fi certificaatvalidatie</span><span class="sxs-lookup"><span data-stu-id="fdddf-149">Wi-Fi certificate validation</span></span>

<span data-ttu-id="fdddf-150">Op dit moment moet het apparaat het Wi-Fi ontvangen.</span><span class="sxs-lookup"><span data-stu-id="fdddf-150">By now, the device should have received the Wi-Fi certificate.</span></span> <span data-ttu-id="fdddf-151">De eenvoudigste validatie die u kunt uitvoeren, is proberen verbinding te maken met Wi-Fi verbinding waarvoor&#39;het certificaat hebt ontvangen.</span><span class="sxs-lookup"><span data-stu-id="fdddf-151">The simplest validation you can do is attempt to connect to the Wi-Fi connection for which you&#39;ve received the certificate.</span></span> <span data-ttu-id="fdddf-152">Open de  Instellingen app, navigeer naar **Network &amp; Internet**  ->  **Wi-Fi** en selecteer de Wi-Fi-verbinding.</span><span class="sxs-lookup"><span data-stu-id="fdddf-152">Open up the **Settings** app and navigate to **Network &amp; Internet** -> **Wi-Fi** and select the Wi-fi connection.</span></span> <span data-ttu-id="fdddf-153">Nadat u verbinding hebt gemaakt, opent u Microsoft Edge app en bevestigt u dat u naar een website kunt navigeren.</span><span class="sxs-lookup"><span data-stu-id="fdddf-153">Once connected, open up the Microsoft Edge app and confirm you can navigate to a website.</span></span>

<span data-ttu-id="fdddf-154">Als u wilt bevestigen dat u het certificaat op het apparaat hebt ontvangen, kunt u [Certificaatbeheer gebruiken.](/hololens/certificate-manager)</span><span class="sxs-lookup"><span data-stu-id="fdddf-154">To confirm that you have received the certificate on the device, you can use the [Certificate Manager](/hololens/certificate-manager).</span></span>

## <a name="validate-lob-app-install"></a><span data-ttu-id="fdddf-155">Installatie van LOB-app valideren</span><span class="sxs-lookup"><span data-stu-id="fdddf-155">Validate LOB app install</span></span>

<span data-ttu-id="fdddf-156">Als u de voortgang van de installatie van een beheerde app wilt bekijken, controleert u of de app is geïnstalleerd of Instellingen.</span><span class="sxs-lookup"><span data-stu-id="fdddf-156">To see a managed app's install progress, you either see if the app is installed or check Settings.</span></span> <span data-ttu-id="fdddf-157">Door een LOB-app te configureren als een vereiste installatie voor onze groep, wordt de app, nadat de HoloLens is ingeschreven bij een gebruiker in de toegewezen groep, automatisch gedownload naar de HoloLens.</span><span class="sxs-lookup"><span data-stu-id="fdddf-157">By configuring a LOB app as a required installation for our group, after enrolling the HoloLens with a user in the assigned group, the app will automatically download to the HoloLens.</span></span>

<span data-ttu-id="fdddf-158">Open het Startmenu en selecteer **Alle apps**.</span><span class="sxs-lookup"><span data-stu-id="fdddf-158">Open the Start menu and select **All apps**.</span></span> <span data-ttu-id="fdddf-159">Afhankelijk van het aantal apps dat u hebt, moet u mogelijk de knoppen **Voor** pagina omhoog of Omlaag **gebruiken.**</span><span class="sxs-lookup"><span data-stu-id="fdddf-159">Depending on the number of apps you have, you may need to use the **page up** or **page down** buttons.</span></span>

<span data-ttu-id="fdddf-160">Als u de installatie van de app op het apparaat wilt valideren, kunt u dit doen via **Instellingen** Accounts Toegang tot werk of  ->    ->  **school.** Selecteer het account en vervolgens de knop **Info** en schuif omlaag om verschillende configuraties en apps te zien die vanuit MDM op het apparaat zijn toegepast.</span><span class="sxs-lookup"><span data-stu-id="fdddf-160">To validate the installation of the app on device, you can do so via **Settings** -> **Accounts** -> **Access work or school**; select the account then the **Info** button, and scroll down to see different configurations and apps applied to the device from MDM.</span></span>

<span data-ttu-id="fdddf-161">Als u de installatie vanuit Intune wilt valideren, navigeert u naar de pagina [](https://endpoint.microsoft.com/#home)  ->  **Apps** -> Alle apps TheNameOfYourApp Device install status page (Apps -> Alle **apps:** de installatiestatuspagina van het  -> *apparaatNaamVanUwApp-apparaat).*  ->  </span><span class="sxs-lookup"><span data-stu-id="fdddf-161">To validate the install from Intune, navigate to the [MEM portal](https://endpoint.microsoft.com/#home) -> **Apps** -> All **apps** ->*TheNameOfYourApp* -> **Device install status** page.</span></span>

<span data-ttu-id="fdddf-162">Meer informatie: [Intune-app-implementatie voor HoloLens](/hololens/app-deploy-intune)</span><span class="sxs-lookup"><span data-stu-id="fdddf-162">See more: [Intune App Deployment for HoloLens](/hololens/app-deploy-intune)</span></span>

## <a name="validate-dynamics-365-guides"></a><span data-ttu-id="fdddf-163">De Dynamics 365 Guides</span><span class="sxs-lookup"><span data-stu-id="fdddf-163">Validate Dynamics 365 Guides</span></span>

<span data-ttu-id="fdddf-164">Er zijn modi voor de app Guides HoloLens, schrijven en gebruiken.</span><span class="sxs-lookup"><span data-stu-id="fdddf-164">There are modes for the Guides app on HoloLens, authoring and operating.</span></span> <span data-ttu-id="fdddf-165">U moet het maken van een handleiding voltooien voordat u deze kunt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="fdddf-165">You'll need to finish authoring a guide before operating it.</span></span>

### <a name="authoring-the-guide"></a><span data-ttu-id="fdddf-166">De handleiding schrijven</span><span class="sxs-lookup"><span data-stu-id="fdddf-166">Authoring the Guide</span></span>

<span data-ttu-id="fdddf-167">We hoeven niet veel te doen voor deze snelle validatie.</span><span class="sxs-lookup"><span data-stu-id="fdddf-167">We don't need to do much for this quick validation.</span></span> <span data-ttu-id="fdddf-168">Selecteer gewoon de handleiding die u hebt voorbereid op uw pc.</span><span class="sxs-lookup"><span data-stu-id="fdddf-168">Simply select the guide you prepared on your PC.</span></span> <span data-ttu-id="fdddf-169">U moet de handleiding [ankeren voor](/dynamics365/mixed-reality/guides/hololens-app-anchor)een snelle validatie. U kunt een holografische anker gebruiken.</span><span class="sxs-lookup"><span data-stu-id="fdddf-169">You'll need to [anchor the guide](/dynamics365/mixed-reality/guides/hololens-app-anchor), for a quick validation you can use a holographic anchor.</span></span> <span data-ttu-id="fdddf-170">Daarna moet u [uw stappen en modellen plaatsen.](/dynamics365/mixed-reality/guides/hololens-app-orientation)</span><span class="sxs-lookup"><span data-stu-id="fdddf-170">Afterwards, you should [place your steps and models](/dynamics365/mixed-reality/guides/hololens-app-orientation).</span></span>

>[!NOTE]
> <span data-ttu-id="fdddf-171">U hebt de **ontwerprol nodig om** u aan te melden bij de pc en auteur op de HoloLens.</span><span class="sxs-lookup"><span data-stu-id="fdddf-171">You will need the **Authoring** role to login to the PC and author on the HoloLens.</span></span> <span data-ttu-id="fdddf-172">De rol Operator is alleen-lezen en heeft geen toegang tot de pc-app.</span><span class="sxs-lookup"><span data-stu-id="fdddf-172">The Operator role is read-only and has no access to the PC app.</span></span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/poE7s7_zWDE" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="operating-the-guide"></a><span data-ttu-id="fdddf-173">De handleiding gebruiken</span><span class="sxs-lookup"><span data-stu-id="fdddf-173">Operating the Guide</span></span>

<span data-ttu-id="fdddf-174">Zodra uw hologrammen zijn uitgevoerd, kunt u de werking van uw handleiding testen.</span><span class="sxs-lookup"><span data-stu-id="fdddf-174">Once your holograms are in place, you can test out operating your guide.</span></span> 
- <span data-ttu-id="fdddf-175">Operatormodus **selecteren**</span><span class="sxs-lookup"><span data-stu-id="fdddf-175">Select **Operator mode**</span></span>
- <span data-ttu-id="fdddf-176">Klik door de stappen van uw handleiding.</span><span class="sxs-lookup"><span data-stu-id="fdddf-176">Click through the steps of your guide.</span></span>

<span data-ttu-id="fdddf-177">Raadpleeg de volgende bronnen voor uitgebreidere richtlijnen voor het werken met een handleiding:</span><span class="sxs-lookup"><span data-stu-id="fdddf-177">For more in-depth guidance on how to operate a guide, check out these resources:</span></span>

[<span data-ttu-id="fdddf-178">Overzicht van het gebruik van een handleiding in Dynamics 365 Guides</span><span class="sxs-lookup"><span data-stu-id="fdddf-178">Overview of operating a guide in Dynamics 365 Guides</span></span>](/dynamics365/mixed-reality/guides/operator-overview)

[<span data-ttu-id="fdddf-179">Ga aan de haal met de kaart Stap als operator in Dynamics 365 Guides</span><span class="sxs-lookup"><span data-stu-id="fdddf-179">Get oriented with the Step card as an operator in Dynamics 365 Guides</span></span>](/dynamics365/mixed-reality/guides/operator-step-card-orientation)

<iframe width="560" height="315" src="https://www.youtube.com/embed/9s41BKGHVL8" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="next-step"></a><span data-ttu-id="fdddf-180">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="fdddf-180">Next step</span></span> 
> [!div class="nextstepaction"]
> [<span data-ttu-id="fdddf-181">Zakelijke verbonden implementatie - Onderhouden</span><span class="sxs-lookup"><span data-stu-id="fdddf-181">Corporate connected deployment - Maintain</span></span>](hololens2-corp-connected-maintain.md)
