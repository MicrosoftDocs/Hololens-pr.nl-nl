---
title: 'Implementatiehandleiding : cloudgeconnecteerde HoloLens 2 implementatie op schaal met Remote Assist - Onderhouden'
description: Blijf op de hoogte met onze tips voor het onderhouden en ondersteunen van HoloLens-apparaten via een met de cloud verbonden netwerk.
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
ms.openlocfilehash: bc34c4e41c5a6cee8f3f9a0a97407ee38d419bbc
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/19/2021
ms.locfileid: "111377931"
---
# <a name="maintain---cloud-connected-guide"></a><span data-ttu-id="76d5c-104">Onderhouden - Handleiding voor verbonden cloud</span><span class="sxs-lookup"><span data-stu-id="76d5c-104">Maintain - Cloud connected Guide</span></span>

## <a name="updates"></a><span data-ttu-id="76d5c-105">Updates</span><span class="sxs-lookup"><span data-stu-id="76d5c-105">Updates</span></span>

<span data-ttu-id="76d5c-106">Microsoft heeft Windows Update voor Bedrijven ontworpen om IT-beheerders aanvullende Windows Update-gerichte beheermogelijkheden te bieden, zoals de mogelijkheid om updates te implementeren op groepen apparaten en om onderhoudsvensters te definiëren voor het installeren van updates.</span><span class="sxs-lookup"><span data-stu-id="76d5c-106">Microsoft designed Windows Update for Business to provide IT administrators with additional Windows Update-centric management capabilities, such as the ability to deploy updates to groups of devices and to define maintenance windows for installing updates.</span></span>

<span data-ttu-id="76d5c-107">Meer informatie over het [beheren van HoloLens-updates,](https://docs.microsoft.com/hololens/hololens-updates) waaronder geplande dagen, geplande tijd en het instellen van actieve uren op het apparaat, zodat deze buiten werkuren worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="76d5c-107">Learn how to [manage HoloLens updates](https://docs.microsoft.com/hololens/hololens-updates) including scheduled days, scheduled time, and setting active hours on the device so it will update outside of working hours.</span></span>

<span data-ttu-id="76d5c-108">Remote Assist is een In-Box app en kan worden bijgewerkt via de Microsoft Store app.</span><span class="sxs-lookup"><span data-stu-id="76d5c-108">Remote Assist is an In-Box app, and can be update through the Microsoft Store app.</span></span> <span data-ttu-id="76d5c-109">Voor alle apps die worden gedownload via de Microsoft Store kunnen ze handmatig worden bijgewerkt [via Microsoft Store](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) app zelf.</span><span class="sxs-lookup"><span data-stu-id="76d5c-109">For all apps that are downloaded through the Microsoft Store they can be [updated through the Microsoft Store](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) app itself manually.</span></span>

## <a name="support-plan"></a><span data-ttu-id="76d5c-110">Ondersteuningsplan</span><span class="sxs-lookup"><span data-stu-id="76d5c-110">Support Plan</span></span>

<span data-ttu-id="76d5c-111">Een ondersteuningsplan is uitstekend om te hebben.</span><span class="sxs-lookup"><span data-stu-id="76d5c-111">A support plan is an excellent thing to have in place.</span></span> <span data-ttu-id="76d5c-112">Het is handig om iemand of een groep te laten trainen voor het oplossen van problemen met het inschrijvingsproces op HoloLens-apparaten en algemeen gebruik van het HoloLens-apparaat binnen uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="76d5c-112">Having someone, or a group trained up on troubleshooting the enrollment process on HoloLens devices and also general use of the HoloLens device within your organization is useful.</span></span> <span data-ttu-id="76d5c-113">Om uw gebruikers in staat te stellen hun problemen sneller op te lossen, raden we u aan om uw escalatieproces op een vergelijkbare manier te verwerken als in deze volgorde:</span><span class="sxs-lookup"><span data-stu-id="76d5c-113">In order to allow your users to have the faster resolution of their issues, we suggest that your escalation process is handled in a similar manner to this order:</span></span>

1. <span data-ttu-id="76d5c-114">Uw ondersteuningsdesk.</span><span class="sxs-lookup"><span data-stu-id="76d5c-114">Your Support desk.</span></span>
2. <span data-ttu-id="76d5c-115">Uw HoloLens Expert-team</span><span class="sxs-lookup"><span data-stu-id="76d5c-115">Your HoloLens Expert team</span></span>
3. <span data-ttu-id="76d5c-116">[HoloLens Docs](https://docs.microsoft.com/hololens/)  /  [Documentatie voor het oplossen van problemen met HoloLens](https://docs.microsoft.com/hololens/hololens-troubleshooting)</span><span class="sxs-lookup"><span data-stu-id="76d5c-116">[HoloLens Docs](https://docs.microsoft.com/hololens/) / [HoloLens Troubleshooting Docs](https://docs.microsoft.com/hololens/hololens-troubleshooting)</span></span>
4. [<span data-ttu-id="76d5c-117">Contact opnemen met ondersteuning</span><span class="sxs-lookup"><span data-stu-id="76d5c-117">Contact Support</span></span>](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="development-plan"></a><span data-ttu-id="76d5c-118">Ontwikkelingsplan</span><span class="sxs-lookup"><span data-stu-id="76d5c-118">Development Plan</span></span>

<span data-ttu-id="76d5c-119">Nu uw apparaat is ingeschreven, bent u voorbereid op het implementeren van Lob-apps (Line-Of-Business) op uw apparaten.</span><span class="sxs-lookup"><span data-stu-id="76d5c-119">With your device successfully enrolled you are now prepared to deploy Line of Business apps (LOB apps) to your devices.</span></span> <span data-ttu-id="76d5c-120">Dit zijn aangepaste apps die zijn gebouwd voor uw organisatie&#39;behoeften.</span><span class="sxs-lookup"><span data-stu-id="76d5c-120">These are custom apps built for your organization&#39;s needs.</span></span>

<span data-ttu-id="76d5c-121">Als u al een Line-Of-Business-app hebt, kunt&#39;[app implementeren via MDM.](https://docs.microsoft.com/hololens/app-deploy-intune)</span><span class="sxs-lookup"><span data-stu-id="76d5c-121">If you already have a line of business app then you&#39;re ready to [deploy your app through MDM](https://docs.microsoft.com/hololens/app-deploy-intune).</span></span> <span data-ttu-id="76d5c-122">Als u&#39;liever een andere methode gebruikt, bekijkt u het overzicht van de toepassingsimplementatie voor [HoloLens 2](https://docs.microsoft.com/hololens/app-deploy-overview) meer methoden voor het implementeren van uw LOB-app op uw apparaten.</span><span class="sxs-lookup"><span data-stu-id="76d5c-122">If you&#39;d prefer a different method then review the [application deployment overview for HoloLens 2](https://docs.microsoft.com/hololens/app-deploy-overview) to learn more methods of deploying your LOB app to your devices.</span></span>

<span data-ttu-id="76d5c-123">Als u nog&#39;LOB-app wilt maken of nog steeds bezig bent met het maken, bekijkt u onze mixed reality-ontwikkelings docs om te beginnen met het ontwerpen en [prototypen](https://docs.microsoft.com/windows/mixed-reality/design/design) of om de belangrijkste concepten te leren om aan de slag te gaan met [mixed reality-ontwikkeling.](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)</span><span class="sxs-lookup"><span data-stu-id="76d5c-123">If you&#39;ve yet to create your own LOB app or are still in the process of creation then review our mixed reality development docs to [start designing and prototyping](https://docs.microsoft.com/windows/mixed-reality/design/design) or learn the core concepts to [get started with mixed reality development.](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)</span></span>

## <a name="device-management"></a><span data-ttu-id="76d5c-124">Apparaatbeheer</span><span class="sxs-lookup"><span data-stu-id="76d5c-124">Device Management</span></span> 

<span data-ttu-id="76d5c-125">Hoewel in deze handleiding wordt gesproken over het instellen van Mobile Device Management (MDM), werd het niet gebruikt om apparaatbeperkingen toe te passen of werd er beleid toegepast op apparaten.</span><span class="sxs-lookup"><span data-stu-id="76d5c-125">While this guide talked about setting up Mobile Device Management (MDM) it wasn't employed to apply device restrictions or policies were applied to devices.</span></span> <span data-ttu-id="76d5c-126">Apparaatbeheer kan worden gebruikt om toegang toe te staan door certificaten te pushen of de toegang te beperken met verschillende apparaatbeperkingen.</span><span class="sxs-lookup"><span data-stu-id="76d5c-126">Device management can be used to both to allow access by pushing certificates, or restrict access with a variety of device restrictions.</span></span> 

<span data-ttu-id="76d5c-127">In veel gevallen kunnen apparaten verbindingsbeperkingen hebben, zoals Bluetooth, VPN, USB of zelfs het uitschakelen van de toegang tot de camera of microfoon.</span><span class="sxs-lookup"><span data-stu-id="76d5c-127">In many cases devices can have connectivity restrictions such as Bluetooth, VPN, USB or even turning off access to the camera or microphone.</span></span> <span data-ttu-id="76d5c-128">Als u een van deze interesses hebt, raden we u aan onze algemene pagina met [apparaatbeperkingen te lezen.](hololens-common-device-restrictions.md)</span><span class="sxs-lookup"><span data-stu-id="76d5c-128">If any of these interests you then we encourage you to read our [common device restrictions page](hololens-common-device-restrictions.md).</span></span>

<span data-ttu-id="76d5c-129">Er zijn andere complexere apparaatbeperkingen die u kunt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="76d5c-129">There are other more complex device restrictions you can use.</span></span> <span data-ttu-id="76d5c-130">Zoals:</span><span class="sxs-lookup"><span data-stu-id="76d5c-130">Such as:</span></span>

- <span data-ttu-id="76d5c-131">Beperk de pagina's die kunnen worden weergegeven in de app Instellingen met behulp van [InstellingenPaginaVisibility,](settings-uri-list.md)zodat gebruikers alleen toegang hebben tot de instellingen die ze moeten aanpassen, zoals het wijzigen van hun Wi-Fi verbinding.</span><span class="sxs-lookup"><span data-stu-id="76d5c-131">Limiting the pages that can be viewed in the Settings app by using [SettingsPageVisibility](settings-uri-list.md), allowing users to only access the settings they need to adjust such as changing their Wi-Fi connection.</span></span>
- <span data-ttu-id="76d5c-132">Gebruik [de kioskmodus](hololens-kiosk.md) om de gebruikersinterface te beperken die wordt weergegeven aan gebruikers op een apparaat.</span><span class="sxs-lookup"><span data-stu-id="76d5c-132">Use [Kiosk mode](hololens-kiosk.md) to limit the UI presented to users on a device.</span></span> <span data-ttu-id="76d5c-133">U kunt Kiosken instellen op het tonen van één app of meerdere apps met een aangepaste startpagina.</span><span class="sxs-lookup"><span data-stu-id="76d5c-133">You can set Kiosks to show a single app, or multiple apps with a custom start page.</span></span> <span data-ttu-id="76d5c-134">Kiosken kunnen ook verschillende ervaringen bieden aan verschillende gebruikers.</span><span class="sxs-lookup"><span data-stu-id="76d5c-134">Kiosks can also present different experiences to different users.</span></span>  
- <span data-ttu-id="76d5c-135">[Windows Application Control (WDAC) om](windows-defender-application-control-wdac.md) te zorgen dat specifieke apps of processen niet volledig worden starten.</span><span class="sxs-lookup"><span data-stu-id="76d5c-135">[Windows Application Control (WDAC)](windows-defender-application-control-wdac.md) to keep specific apps or processes from launching entirely.</span></span>

<span data-ttu-id="76d5c-136">Als u meer informatie wilt over meer verschillende methoden voor apparaatbeheer of apparaatbeperkingen, gaat u naar de volgende stap en leest u het Overzicht van apparaatbeheer.</span><span class="sxs-lookup"><span data-stu-id="76d5c-136">If you'd like to learn about more different methods of device management or device restrictions, then take the next step and read our Device Management Overview.</span></span>

## <a name="next-step"></a><span data-ttu-id="76d5c-137">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="76d5c-137">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="76d5c-138">Lees het overzicht van CSP's en apparaatbeheer</span><span class="sxs-lookup"><span data-stu-id="76d5c-138">Read the CSPs and Device Management Overview</span></span>](hololens-csp-policy-overview.md)