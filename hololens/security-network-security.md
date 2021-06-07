---
title: Netwerkbeveiliging
description: netwerkbeveiliging
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: beveiliging, hololens, netwerk, netwerkbeveiliging
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: f1e5304408a9a9543eb0703ad7321725484eef01
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379391"
---
# <a name="network-security"></a><span data-ttu-id="592cd-104">Netwerkbeveiliging</span><span class="sxs-lookup"><span data-stu-id="592cd-104">Network security</span></span>

## <a name="network-protocols"></a><span data-ttu-id="592cd-105">Netwerkprotocollen</span><span class="sxs-lookup"><span data-stu-id="592cd-105">Network protocols</span></span>

<span data-ttu-id="592cd-106">Het verouderde NetBIOS (Network Basic Input/Output System) werd in het verleden veel gebruikt in LAN-scenario's, vaak voor het leveren van naamom oplossing voor een computer en gedeelde mappen.</span><span class="sxs-lookup"><span data-stu-id="592cd-106">The outdated NetBIOS (Network Basic Input/Output System) was widely used in the past in LAN scenarios – often for providing name resolution to a computer and shared folders.</span></span> <span data-ttu-id="592cd-107">Maar na een periode blijkt NetBIOS vatbaar te zijn voor meerdere aanvallen en is de relevantie ervan afgenomen ten opzichte van andere veiligere protocollen.</span><span class="sxs-lookup"><span data-stu-id="592cd-107">But over time, NetBIOS proved to be susceptible to multiple attacks, and its relevance decreased in favor of other more secure protocols.</span></span> <span data-ttu-id="592cd-108">Als u dit beveiligingsprobleem wilt verwijderen, HoloLens 2 netBIOS-gerelateerde code uit het besturingssysteem verwijderd.</span><span class="sxs-lookup"><span data-stu-id="592cd-108">To remove this vulnerability issue, HoloLens 2 has eliminated the NetBIOS-related code from the operating system.</span></span>

<span data-ttu-id="592cd-109">TLS-protocollen (Transport Layer Security) zijn voortdurend in ontwikkeling.</span><span class="sxs-lookup"><span data-stu-id="592cd-109">TLS (Transport Layer Security) protocols are constantly evolving.</span></span> <span data-ttu-id="592cd-110">Om de verschillende beveiligingsactiviteiten die op dit gebied zijn ontdekt bij te houden, heeft de computerbranche zijn overgeplaatst naar nieuwere en effectievere versies.</span><span class="sxs-lookup"><span data-stu-id="592cd-110">To keep up with the various security exploits that have been uncovered in this area, the computing industry has graduated to newer and more effective versions.</span></span> <span data-ttu-id="592cd-111">Vanwege de tijd die nodig is voor alle serverimplementaties om de nieuwe TLS-protocolversies te gebruiken, kan er een terugvalmechanisme worden geïmplementeerd waarmee de client en servers op verschillende standaardprotocolversies nog steeds kunnen communiceren tijdens de periode.</span><span class="sxs-lookup"><span data-stu-id="592cd-111">Due to the time required for all server deployments to adopt the new TLS protocol versions, a fallback mechanism can be implemented that permits the client and servers on different default protocol versions to still be able to communicate during the transition period.</span></span>

## <a name="secure-connectivity"></a><span data-ttu-id="592cd-112">Beveiligde connectiviteit</span><span class="sxs-lookup"><span data-stu-id="592cd-112">Secure connectivity</span></span> 

<span data-ttu-id="592cd-113">De Windows Defender Firewall biedt essentiële functionaliteit om de connectiviteit van apparaten te beveiligen.</span><span class="sxs-lookup"><span data-stu-id="592cd-113">The Windows Defender Firewall delivers critical functionality to secure device connectivity.</span></span> <span data-ttu-id="592cd-114">Met HoloLens 2 is de firewall altijd ingeschakeld en zijn er geen manieren om deze programmatisch of via de gebruikersinterface uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="592cd-114">With HoloLens 2, the firewall is always enabled and there are no ways to disable it programmatically or through the UI.</span></span>

<span data-ttu-id="592cd-115">De privacy van externe toegang en verbindingen voor mobiele clients kan worden gegarandeerd via het [UWP VPN-internetverbindingsplatform.](https://docs.microsoft.com/uwp/api/Windows.Networking.Vpn?view=winrt-19041)</span><span class="sxs-lookup"><span data-stu-id="592cd-115">Remote access and connection privacy for mobile clients can be assured through the [UWP VPN plug-in platform](https://docs.microsoft.com/uwp/api/Windows.Networking.Vpn?view=winrt-19041).</span></span> <span data-ttu-id="592cd-116">Externe VPN-providers kunnen hun eigen in plug-ins maken met behulp van WinRT-API's die worden uitgevoerd in de AppContainer-sandbox, waardoor de complexiteit en problemen die vaak worden geassocieerd met het schrijven van stuurprogramma's op systeemniveau, worden voorkomen.</span><span class="sxs-lookup"><span data-stu-id="592cd-116">Third-party VPN providers can create their own plug-ins using WinRT APIs which will run within the AppContainer sandbox, eliminating the complexity and issues often associated with writing system-level drivers.</span></span>
