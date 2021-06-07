---
title: Accu en laden
description: Uw HoloLens laden en externe batterijpakketten gebruiken.
ms.assetid: E0AB903E-454E-46F6-AB25-4DFA0A475B0C
ms.prod: hololens
ms.sitesec: library
author: jbienzms
ms.author: jbienz
ms.topic: article
ms.localizationpriority: high
ms.date: 05/14/2021
manager: evmill
appliesto:
- HoloLens 2
ms.openlocfilehash: 15ecc698a515987857f556fed97d74f861cd6b20
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/25/2021
ms.locfileid: "111379496"
---
# <a name="battery-and-charging"></a><span data-ttu-id="2d3f1-103">Accu en laden</span><span class="sxs-lookup"><span data-stu-id="2d3f1-103">Battery and Charging</span></span>

<span data-ttu-id="2d3f1-104">Deze pagina biedt details over het laden van HoloLens 2 en het gebruik van externe accupakketten.</span><span class="sxs-lookup"><span data-stu-id="2d3f1-104">This page offers details about charging HoloLens 2 and using external battery packs.</span></span>

## <a name="included-charger"></a><span data-ttu-id="2d3f1-105">Included Charger</span><span class="sxs-lookup"><span data-stu-id="2d3f1-105">Included Charger</span></span>

<span data-ttu-id="2d3f1-106">De in de HoloLens 2 biedt maximaal 9V @ 2A (18W).</span><span class="sxs-lookup"><span data-stu-id="2d3f1-106">The charger included with HoloLens 2 provides up to 9V @ 2A (18W).</span></span> <span data-ttu-id="2d3f1-107">Indien mogelijk wordt het ten zeerste aanbevolen om kosten in rekening te brengen met behulp van de inbegrepen auto.</span><span class="sxs-lookup"><span data-stu-id="2d3f1-107">When possible, it's highly recommended to charge using the included charger.</span></span>  

## <a name="specifications"></a><span data-ttu-id="2d3f1-108">Specificaties</span><span class="sxs-lookup"><span data-stu-id="2d3f1-108">Specifications</span></span>

<span data-ttu-id="2d3f1-109">HoloLens 2 kunnen worden op basis van [USB-voedingen](https://www.usb.org/usb-charger-pd) tot 27 Watt.</span><span class="sxs-lookup"><span data-stu-id="2d3f1-109">HoloLens 2 can be charged by [USB Power Delivery](https://www.usb.org/usb-charger-pd) sources up to 27 Watts.</span></span> <span data-ttu-id="2d3f1-110">Als de bron ten minste 10 Watt kan leveren, kan de HoloLens-gebruiktijd worden uitgebreid (mogelijk voor onbepaalde tijd voor sommige workloads).</span><span class="sxs-lookup"><span data-stu-id="2d3f1-110">If the source is able supply at least 10 Watts, HoloLens operating time can be extended (potentially indefinitely for some workloads).</span></span> 

> [!NOTE]
> <span data-ttu-id="2d3f1-111">Als u een USB-A-naar-USB-C-laadkabel gebruikt, worden de kosten beperkt tot 7,5 watt.</span><span class="sxs-lookup"><span data-stu-id="2d3f1-111">Using a USB-A to USB-C charging cable will limit the charge to 7.5 Watts.</span></span> <span data-ttu-id="2d3f1-112">De gebruiktijd wordt nog steeds verlengd, maar niet zo lang als het gebruik van USB-C naar C.</span><span class="sxs-lookup"><span data-stu-id="2d3f1-112">Operating time will still be extended, but not as long as using USB-C to C.</span></span>

<span data-ttu-id="2d3f1-113">Wanneer HoloLens zich in de stand-bymodus bevindt, is 18 Watt voldoende om de maximale laadsnelheid voor de interne accu te bereiken.</span><span class="sxs-lookup"><span data-stu-id="2d3f1-113">When HoloLens is in standby mode, 18 Watts is sufficient to reach the maximum charge rate for the internal battery.</span></span> <span data-ttu-id="2d3f1-114">Wanneer HoloLens in gebruik is, kan het tarief worden verlaagd omdat HoloLens prioriteit geeft aan de werking boven de kosten.</span><span class="sxs-lookup"><span data-stu-id="2d3f1-114">When HoloLens is in use, the charge rate may be reduced since HoloLens prioritizes operating over charging.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2d3f1-115">Het is raadzaam om HoloLens 2 minimaal 5V/1,5A in rekening te gebracht.</span><span class="sxs-lookup"><span data-stu-id="2d3f1-115">It's recommended that HoloLens 2 be charged at 5V/1.5A minimum.</span></span> <span data-ttu-id="2d3f1-116">Er mag geen gebruik worden gemaakt van 5V/1.5A-producten die niet ten minste 5V/1.5A kunnen leveren.</span><span class="sxs-lookup"><span data-stu-id="2d3f1-116">Chargers that can't supply at least 5V/1.5A should not be used.</span></span> 

## <a name="external-battery-packs"></a><span data-ttu-id="2d3f1-117">Externe batterijpakketten</span><span class="sxs-lookup"><span data-stu-id="2d3f1-117">External Battery Packs</span></span>

<span data-ttu-id="2d3f1-118">Accupakketten die voldoen aan de bovenstaande specificaties, kunnen worden gebruikt met HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="2d3f1-118">Battery packs that meet the specifications above can be used with HoloLens 2.</span></span> <span data-ttu-id="2d3f1-119">Houd er echter rekening mee dat sommige USB-C-accupakketten voeding hebben en stroom leveren via dezelfde USB-C-poort.</span><span class="sxs-lookup"><span data-stu-id="2d3f1-119">However, note that some USB-C battery packs recharge and provide power through the same USB-C port.</span></span> <span data-ttu-id="2d3f1-120">Het is belangrijk dat deze batterijpakketten [TRY implementeren. SRC om](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20) ervoor te zorgen dat ze HoloLens in rekening brengen in plaats van er kosten voor in rekening te brengen.</span><span class="sxs-lookup"><span data-stu-id="2d3f1-120">It's important that these battery packs implement [TRY.SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20) to ensure they charge HoloLens rather than charge from it.</span></span> 

## <a name="managing-heat"></a><span data-ttu-id="2d3f1-121">Warmte beheren</span><span class="sxs-lookup"><span data-stu-id="2d3f1-121">Managing Heat</span></span>

<span data-ttu-id="2d3f1-122">Net als bij elk apparaat genereert het laden van HoloLens warmte.</span><span class="sxs-lookup"><span data-stu-id="2d3f1-122">As with any device, charging HoloLens generates heat.</span></span> <span data-ttu-id="2d3f1-123">Hoe sneller de lading, hoe meer warmte wordt gegenereerd.</span><span class="sxs-lookup"><span data-stu-id="2d3f1-123">The more rapid the charge, the more heat is generated.</span></span> <span data-ttu-id="2d3f1-124">Bovendien genereert het starten van een lading op een lager accuniveau meer warmte dan het starten van een lading wanneer de accu grotendeels vol is.</span><span class="sxs-lookup"><span data-stu-id="2d3f1-124">Also, starting a charge at a lower battery level will generate more heat than starting a charge when the battery is mostly full.</span></span> <span data-ttu-id="2d3f1-125">Klanten die HoloLens gedurende langere tijd in een warme omgeving moeten gebruiken, kunnen de volgende technieken gebruiken:</span><span class="sxs-lookup"><span data-stu-id="2d3f1-125">Customers who need to operate HoloLens for extended periods of time in hot environments can use the following techniques:</span></span>

- <span data-ttu-id="2d3f1-126">U kunt verbinding maken met HoloLens 2 externe voedingsbron, zelfs wanneer de interne accu volledig is op geladen.</span><span class="sxs-lookup"><span data-stu-id="2d3f1-126">It's OK to connect HoloLens 2 to an external power source even when the internal battery is fully charged.</span></span>
- <span data-ttu-id="2d3f1-127">Wanneer een externe batterij is verwijderd, blijft HoloLens werken op de interne accu.</span><span class="sxs-lookup"><span data-stu-id="2d3f1-127">When an external battery is depleted, HoloLens will continue operating on its internal battery.</span></span>    
- <span data-ttu-id="2d3f1-128">Als de warmte na de bovenstaande stappen nog steeds een probleem is, kunt u overwegen een batterij of accupakket te gebruiken dat de laadsnelheid beperkt tot 1,5A.</span><span class="sxs-lookup"><span data-stu-id="2d3f1-128">If heat is still an issue after following steps above, consider using a charger or battery pack that limits charging to 1.5A.</span></span> <span data-ttu-id="2d3f1-129">Houd er rekening mee dat deze optie niet zo veel operationele tijd biedt omdat de interne accu nog steeds langzaam wordt leeggekoppeld.</span><span class="sxs-lookup"><span data-stu-id="2d3f1-129">Note that this option won't provide as much operating time since the internal battery will still slowly deplete.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="2d3f1-130">Problemen oplossen</span><span class="sxs-lookup"><span data-stu-id="2d3f1-130">Troubleshooting</span></span>


### <a name="hololens-charges-external-battery"></a><span data-ttu-id="2d3f1-131">Externe batterij van HoloLens-kosten</span><span class="sxs-lookup"><span data-stu-id="2d3f1-131">HoloLens Charges External Battery</span></span>
<span data-ttu-id="2d3f1-132">Als HoloLens 2 een externe accu laadt in plaats van door deze te worden geladen, geeft dit aan dat TRY niet door de accu wordt [geïmplementeerd. SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20).</span><span class="sxs-lookup"><span data-stu-id="2d3f1-132">If HoloLens 2 charges an external battery rather than being charged by it, this indicates that the battery doesn't implement [TRY.SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20).</span></span> <span data-ttu-id="2d3f1-133">Overschakelen naar een nieuwer accupakket is de aanbevolen manier om dit probleem op te lossen, maar u kunt ook proberen om over te schakelen naar een USB-A-naar-USB-C-kabel.</span><span class="sxs-lookup"><span data-stu-id="2d3f1-133">Switching to a newer battery pack is the recommended way to solve this issue, but alternatively you can try switching to a USB-A to USB-C cable.</span></span> <span data-ttu-id="2d3f1-134">Houd er rekening mee dat dit de laadsnelheid beperkt tot 7,5 watt.</span><span class="sxs-lookup"><span data-stu-id="2d3f1-134">Keep in mind this will limit the charging rate to 7.5 watts.</span></span>
