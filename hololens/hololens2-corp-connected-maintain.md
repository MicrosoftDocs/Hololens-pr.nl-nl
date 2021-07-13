---
title: 'Implementatiehandleiding : Zakelijk verbonden HoloLens 2 met Dynamics 365 Guides - Onderhouden'
description: Meer informatie over het onderhouden HoloLens 2 apparaten via een bedrijfsnetwerk verbonden met Dynamics 365 Guides.
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
ms.openlocfilehash: 0176e816f167499574607bc16c8fbd6bde757daf
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/12/2021
ms.locfileid: "113636993"
---
# <a name="maintain---corporate-connected-guide"></a><span data-ttu-id="97f0f-104">Onderhouden - Handleiding voor verbonden bedrijfsgegevens</span><span class="sxs-lookup"><span data-stu-id="97f0f-104">Maintain - Corporate Connected Guide</span></span>

## <a name="update-hololens"></a><span data-ttu-id="97f0f-105">Werk HoloLens</span><span class="sxs-lookup"><span data-stu-id="97f0f-105">Update HoloLens</span></span>

<span data-ttu-id="97f0f-106">Microsoft heeft Windows Update voor Bedrijven ontworpen om IT-beheerders aanvullende Windows op updates gerichte beheermogelijkheden te bieden, zoals de mogelijkheid om updates te implementeren op groepen apparaten en om onderhoudsvensters te definiëren voor het installeren van updates.</span><span class="sxs-lookup"><span data-stu-id="97f0f-106">Microsoft designed Windows Update for Business to provide IT administrators with additional Windows Update-centric management capabilities, such as the ability to deploy updates to groups of devices and to define maintenance windows for installing updates.</span></span>

<span data-ttu-id="97f0f-107">Een populaire methode voor het beheren van updates is het uitstellen van functies van 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="97f0f-107">One popular method of managing updates is to do a feature deferral of 30 days.</span></span> <span data-ttu-id="97f0f-108">Hierdoor kunnen beheerders nieuwe functies bijwerken en previews bekijken, kennis opdoen en de ondersteuningsdesk informeren over nieuwe wijzigingen.</span><span class="sxs-lookup"><span data-stu-id="97f0f-108">This allows Admins to update and preview new features, gaining first hand knowledge and informing your support desk of any new changes.</span></span>

<span data-ttu-id="97f0f-109">Leer hoe u [HoloLens beheert,](/hololens/hololens-updates)inclusief geplande dagen, geplande tijd en het instellen van actieve uren op het apparaat, zodat deze buiten werkuren worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="97f0f-109">Learn how to [manage HoloLens updates](/hololens/hololens-updates), including scheduled days, scheduled time, and setting active hours on the device, so it will update outside of working hours.</span></span>

## <a name="how-to-update-dynamics-365-guides-and-other-store-apps"></a><span data-ttu-id="97f0f-110">Apps bijwerken Dynamics 365 Guides (en andere Store-apps)</span><span class="sxs-lookup"><span data-stu-id="97f0f-110">How to update Dynamics 365 Guides (and other store apps)</span></span>

<span data-ttu-id="97f0f-111">Dynamics 365 Guides is een In-Box-app en kan worden bijgewerkt via de Microsoft Store app.</span><span class="sxs-lookup"><span data-stu-id="97f0f-111">Dynamics 365 Guides is an In-Box app, and can be updated through the Microsoft Store app.</span></span> <span data-ttu-id="97f0f-112">Alle apps die via de Microsoft Store worden gedownload, kunnen handmatig worden bijgewerkt via [Microsoft Store](/hololens/holographic-store-apps#update-apps) app zelf.</span><span class="sxs-lookup"><span data-stu-id="97f0f-112">For all apps that are downloaded through the Microsoft Store, they can be [updated through the Microsoft Store](/hololens/holographic-store-apps#update-apps) app itself manually.</span></span>

## <a name="how-to-update-lob-apps"></a><span data-ttu-id="97f0f-113">LOB-apps bijwerken</span><span class="sxs-lookup"><span data-stu-id="97f0f-113">How to update LOB apps</span></span>

<span data-ttu-id="97f0f-114">LOB-apps kunnen op dezelfde manier worden bijgewerkt als ze zijn toegevoegd aan Intune.</span><span class="sxs-lookup"><span data-stu-id="97f0f-114">LOB apps can be updated in the same way they were added to Intune.</span></span> <span data-ttu-id="97f0f-115">Apps kunnen worden bijgewerkt in Intune door de nieuwe app met een hoger versienummer te uploaden naar de bestaande app-configuratie.</span><span class="sxs-lookup"><span data-stu-id="97f0f-115">Apps can be updated in Intune by uploading the new app with a higher version number to the existing App configuration.</span></span> <span data-ttu-id="97f0f-116">Wanneer het apparaat wordt gesynchroniseerd met Intune, ziet u dat er een nieuwere app-versie is en dat de nieuwere app wordt gedownload en de oude app wordt vervangen.</span><span class="sxs-lookup"><span data-stu-id="97f0f-116">When the device syncs to Intune, it will observe that there is a newer app version and the newer app will be downloaded and replace the old app.</span></span>

1. <span data-ttu-id="97f0f-117">Als u de nieuwere app wilt uploaden, gaat u naar de [MEM-portal](https://endpoint.microsoft.com/#home)  ->  **Apps** -> Alle **apps**  ->  *TheNameOfYourApp*  ->  **Properties.**</span><span class="sxs-lookup"><span data-stu-id="97f0f-117">To upload the newer app, navigate to the [MEM portal](https://endpoint.microsoft.com/#home) -> **Apps** -> All **apps** -> *TheNameOfYourApp* -> **Properties.**</span></span>
2. <span data-ttu-id="97f0f-118">Selecteer bewerken naast **App-gegevens.**</span><span class="sxs-lookup"><span data-stu-id="97f0f-118">Next to App information, select **Edit.**</span></span>
3. <span data-ttu-id="97f0f-119">Selecteer uw bestand &quot; voor de waarde bestand selecteren die moet worden &quot; bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="97f0f-119">For the value of &quot;Select file to update&quot;, select your file.</span></span>
4. <span data-ttu-id="97f0f-120">Gebruik hier het contextmenu om de verkenner te openen en de nieuwere versie van de LOB-app te uploaden.</span><span class="sxs-lookup"><span data-stu-id="97f0f-120">From here, use the context menu to open your file explorer and upload the newer version of the LOB app.</span></span> <span data-ttu-id="97f0f-121">Zorg ervoor dat afhankelijkheden zo nodig zijn op te nemen.</span><span class="sxs-lookup"><span data-stu-id="97f0f-121">Ensure to include dependencies as needed.</span></span>

<span data-ttu-id="97f0f-122">Meer informatie: [Intune-app-implementatie voor HoloLens](/hololens/app-deploy-intune)</span><span class="sxs-lookup"><span data-stu-id="97f0f-122">See more: [Intune App Deployment for HoloLens](/hololens/app-deploy-intune)</span></span>

## <a name="development-plan"></a><span data-ttu-id="97f0f-123">Ontwikkelingsplan</span><span class="sxs-lookup"><span data-stu-id="97f0f-123">Development Plan</span></span>

<span data-ttu-id="97f0f-124">Nu uw apparaat is ingeschreven, bent u voorbereid om meer LOB-apps op uw apparaten te implementeren.</span><span class="sxs-lookup"><span data-stu-id="97f0f-124">With your device successfully enrolled, you are now prepared to deploy more LOB apps to your devices.</span></span> <span data-ttu-id="97f0f-125">Voor de duur van deze handleiding gebruiken we een voorbeeld-app, maar het is waarschijnlijker dat u aangepaste apps wilt gebruiken die zijn gebouwd voor de behoeften van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="97f0f-125">For the duration of this Guide, we're using a sample app, but it's more likely that you will want to use custom apps built for your organization's needs.</span></span>

<span data-ttu-id="97f0f-126">Als u al een LOB-app hebt, kunt u uw [app implementeren via MDM.](/hololens/app-deploy-intune)</span><span class="sxs-lookup"><span data-stu-id="97f0f-126">If you already have a LOB app, then you're ready to [deploy your app through MDM](/hololens/app-deploy-intune).</span></span> <span data-ttu-id="97f0f-127">Als u liever een andere methode [](/hololens/app-deploy-overview) gebruikt, bekijkt u het overzicht van de toepassingsimplementatie voor HoloLens 2 voor meer methoden voor het implementeren van uw LOB-app op uw apparaten.</span><span class="sxs-lookup"><span data-stu-id="97f0f-127">If you'd prefer a different method, then review the [application deployment overview for HoloLens 2](/hololens/app-deploy-overview) to learn more methods of deploying your LOB app to your devices.</span></span>

<span data-ttu-id="97f0f-128">Als u nog uw eigen LOB-app moet maken of nog bezig bent met het maken, bekijkt u onze mixed reality-ontwikkelings docs om te beginnen met het ontwerpen en maken van [prototypen](/windows/mixed-reality/design/design) of om de belangrijkste concepten te leren om aan de slag te gaan [met mixed reality ontwikkeling.](/windows/mixed-reality/discover/get-started-with-mr)</span><span class="sxs-lookup"><span data-stu-id="97f0f-128">If you've yet to create your own LOB app or are still in the process of creation, then review our mixed reality development docs to [start designing and prototyping](/windows/mixed-reality/design/design) or learn the core concepts to [get started with mixed reality development.](/windows/mixed-reality/discover/get-started-with-mr)</span></span>

## <a name="support-plan"></a><span data-ttu-id="97f0f-129">Ondersteuningsplan</span><span class="sxs-lookup"><span data-stu-id="97f0f-129">Support Plan</span></span>

<span data-ttu-id="97f0f-130">Een ondersteuningsplan is uitstekend om te hebben.</span><span class="sxs-lookup"><span data-stu-id="97f0f-130">A support plan is an excellent thing to have in place.</span></span> <span data-ttu-id="97f0f-131">Het is handig om iemand, of een groep, te laten trainen voor het oplossen van problemen met het inschrijvingsproces op HoloLens-apparaten en voor algemeen gebruik van het HoloLens-apparaat binnen uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="97f0f-131">Having someone, or a group, trained up on troubleshooting the enrollment process on HoloLens devices and also general use of the HoloLens device within your organization is useful.</span></span> <span data-ttu-id="97f0f-132">Om uw gebruikers in staat te stellen hun problemen sneller op te lossen, raden we u aan uw escalatieproces op een vergelijkbare manier te laten verlopen als in deze volgorde:</span><span class="sxs-lookup"><span data-stu-id="97f0f-132">In order to allow your users to have the faster resolution of their issues, we suggest that your escalation process is handled in a similar manner to this order:</span></span>

1. <span data-ttu-id="97f0f-133">Uw ondersteuningsdesk.</span><span class="sxs-lookup"><span data-stu-id="97f0f-133">Your Support desk.</span></span>
2. <span data-ttu-id="97f0f-134">Uw HoloLens Expert-team</span><span class="sxs-lookup"><span data-stu-id="97f0f-134">Your HoloLens Expert team</span></span>
3. <span data-ttu-id="97f0f-135">[HoloLens Docs](/hololens/)  /  [HoloLens docs voor probleemoplossing](/hololens/hololens-troubleshooting)</span><span class="sxs-lookup"><span data-stu-id="97f0f-135">[HoloLens Docs](/hololens/) / [HoloLens Troubleshooting Docs](/hololens/hololens-troubleshooting)</span></span>
4. [<span data-ttu-id="97f0f-136">Contact opnemen met ondersteuning</span><span class="sxs-lookup"><span data-stu-id="97f0f-136">Contact Support</span></span>](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="device-management"></a><span data-ttu-id="97f0f-137">Apparaatbeheer</span><span class="sxs-lookup"><span data-stu-id="97f0f-137">Device Management</span></span>

<span data-ttu-id="97f0f-138">In deze handleiding is het instellen van Mobile Device Management (MDM) besproken en gebruikt om enkele apparaatconfiguraties in te stellen en instellingen toe te passen om toegang toe te staan in termen van Wi-Fi certificaten en proxy.</span><span class="sxs-lookup"><span data-stu-id="97f0f-138">This guide talked about setting up Mobile Device Management (MDM) and used it to set up some device configurations and apply settings to allow access in terms of Wi-Fi certificates and proxy.</span></span> <span data-ttu-id="97f0f-139">MDM kan echter ook worden gebruikt om apparaatbeperkingen toe te passen via CSP's en beleidsregels.</span><span class="sxs-lookup"><span data-stu-id="97f0f-139">However, MDM can also be used to apply device restrictions via CSPs and Policies.</span></span>

<span data-ttu-id="97f0f-140">In veel gevallen kunnen apparaten verbindingsbeperkingen hebben, zoals Bluetooth, VPN, USB of zelfs het uitschakelen van de toegang tot de camera of microfoon.</span><span class="sxs-lookup"><span data-stu-id="97f0f-140">In many cases, devices can have connectivity restrictions, such as Bluetooth, VPN, USB or even turning off access to the camera or microphone.</span></span> <span data-ttu-id="97f0f-141">Als u een van deze interesses hebt, raden we u aan onze algemene pagina met [apparaatbeperkingen te lezen.](/hololens/hololens-common-device-restrictions)</span><span class="sxs-lookup"><span data-stu-id="97f0f-141">If any of these interests you, then we encourage you to read our [common device restrictions page](/hololens/hololens-common-device-restrictions).</span></span>

<span data-ttu-id="97f0f-142">Er zijn andere complexere apparaatbeperkingen die u kunt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="97f0f-142">There are other more complex device restrictions you can use.</span></span> <span data-ttu-id="97f0f-143">Zoals:</span><span class="sxs-lookup"><span data-stu-id="97f0f-143">Such as:</span></span>

- <span data-ttu-id="97f0f-144">Beperk de pagina's die kunnen worden weergegeven in de Instellingen-app met behulp van [InstellingenPaginaVisibility,](/hololens/settings-uri-list)zodat gebruikers alleen toegang hebben tot de instellingen die ze moeten aanpassen, zoals het wijzigen van hun Wi-Fi verbinding.</span><span class="sxs-lookup"><span data-stu-id="97f0f-144">Limiting the pages that can be viewed in the Settings app by using [SettingsPageVisibility](/hololens/settings-uri-list), allowing users to only access the settings they need to adjust, such as changing their Wi-Fi connection.</span></span>
- <span data-ttu-id="97f0f-145">Gebruik [kioskmodus om](/hololens/hololens-kiosk) de gebruikersinterface te beperken die wordt weergegeven aan gebruikers op een apparaat.</span><span class="sxs-lookup"><span data-stu-id="97f0f-145">Use [Kiosk mode](/hololens/hololens-kiosk) to limit the UI presented to users on a device.</span></span> <span data-ttu-id="97f0f-146">U kunt Kiosken instellen om één app of meerdere apps weer te geven met een aangepaste startpagina.</span><span class="sxs-lookup"><span data-stu-id="97f0f-146">You can set Kiosks to show a single app, or multiple apps with a custom start page.</span></span> <span data-ttu-id="97f0f-147">Kiosken kunnen ook verschillende ervaringen presenteren aan verschillende gebruikers.</span><span class="sxs-lookup"><span data-stu-id="97f0f-147">Kiosks can also present different experiences to different users.</span></span>
- <span data-ttu-id="97f0f-148">[Windows Application Control (WDAC) om](/hololens/windows-defender-application-control-wdac) te zorgen dat specifieke apps of processen niet volledig worden starten.</span><span class="sxs-lookup"><span data-stu-id="97f0f-148">[Windows Application Control (WDAC)](/hololens/windows-defender-application-control-wdac) to keep specific apps or processes from launching entirely.</span></span>

<span data-ttu-id="97f0f-149">Als u meer wilt weten over aanvullende methoden voor apparaatbeheer of apparaatbeperkingen, gaat u naar de volgende stap en leest u het [Overzicht van apparaatbeheer.](/hololens/hololens-csp-policy-overview)</span><span class="sxs-lookup"><span data-stu-id="97f0f-149">If you'd like to learn about additional methods of device management or device restrictions, then take the next step and read our [Device Management Overview](/hololens/hololens-csp-policy-overview).</span></span>





