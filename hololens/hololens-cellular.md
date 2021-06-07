---
title: Verbinding maken met mobiel en 5G
description: Verbinding maken met mobiele netwerken vanaf uw HoloLens-mixed reality apparaten.
ms.assetid: f1aaadce-8762-41f8-bfeb-3b6067a2ec78
ms.prod: hololens
ms.sitesec: library
author: jbienzms
ms.author: jbienz
ms.topic: article
ms.localizationpriority: high
ms.date: 02/24/2021
manager: evmill
appliesto:
- HoloLens 2
ms.openlocfilehash: 8318d011d6a593c1036b6bcf6f7973870b0dc294
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/25/2021
ms.locfileid: "111379359"
---
# <a name="connect-to-cellular-and-5g"></a><span data-ttu-id="dafc1-103">Verbinding maken met mobiel en 5G</span><span class="sxs-lookup"><span data-stu-id="dafc1-103">Connect to Cellular and 5G</span></span>

<span data-ttu-id="dafc1-104">HoloLens 2 ondersteunt twee methoden om verbinding te maken met mobiele en 5G-netwerken:</span><span class="sxs-lookup"><span data-stu-id="dafc1-104">HoloLens 2 supports two methods for connecting to cellular and 5G networks:</span></span>

- <span data-ttu-id="dafc1-105">Een ad-hoc Wi-Fi-netwerk dat wordt geleverd door het mobiele apparaat, meestal aangeduid als een 'Hotspot'</span><span class="sxs-lookup"><span data-stu-id="dafc1-105">An ad hoc WiFi network provided by the cellular device, commonly referred to as a "Hotspot"</span></span>
- <span data-ttu-id="dafc1-106">Beperkte ondersteuning voor USB-C-tethered apparaten</span><span class="sxs-lookup"><span data-stu-id="dafc1-106">Limited support for USB-C tethered devices</span></span>

## <a name="hotspot-wifi"></a><span data-ttu-id="dafc1-107">Hotspot (Wi-Fi)</span><span class="sxs-lookup"><span data-stu-id="dafc1-107">Hotspot (WiFi)</span></span>

<span data-ttu-id="dafc1-108">Aan de meeste mobiele connectiviteitsbehoeften kan een hotspot worden voldaan.</span><span class="sxs-lookup"><span data-stu-id="dafc1-108">Most cellular connectivity needs can be met with a hotspot.</span></span> <span data-ttu-id="dafc1-109">HoloLens 2 Wi-Fi ondersteunt 802.11ac, dat de bandbreedte- en latentievereisten kan bieden die nodig zijn voor de meest voorkomende gebruiksgevallen.</span><span class="sxs-lookup"><span data-stu-id="dafc1-109">HoloLens 2 WiFi supports 802.11ac, which can provide the bandwidth and latency requirements necessary for most common use cases.</span></span> <span data-ttu-id="dafc1-110">Wi-Fi is ook kabelloos en biedt compatibiliteit met het grootste aantal mobiele apparaten.</span><span class="sxs-lookup"><span data-stu-id="dafc1-110">WiFi is also cable-free and offers compatibility with the largest number of cellular devices.</span></span>

### <a name="connecting-to-a-hotspot"></a><span data-ttu-id="dafc1-111">Verbinding maken met een hotspot</span><span class="sxs-lookup"><span data-stu-id="dafc1-111">Connecting to a Hotspot</span></span>

1. <span data-ttu-id="dafc1-112">Raadpleeg de handleiding van uw apparaat over het inschakelen van de hotspotmodus.</span><span class="sxs-lookup"><span data-stu-id="dafc1-112">Consult your device's manual on how to enable its hotspot mode.</span></span>
1. <span data-ttu-id="dafc1-113">Schakel de hotspotmodus in door een naam voor het netwerk en een bekend wachtwoord op te geven.</span><span class="sxs-lookup"><span data-stu-id="dafc1-113">Enable hotspot mode, supplying a name for the network as well as a known password.</span></span>
1. <span data-ttu-id="dafc1-114">Zoek HoloLens 2 netwerkinstellingen het Wi-Fi-netwerk dat u in stap 2 hebt gemaakt en voeg het toe.</span><span class="sxs-lookup"><span data-stu-id="dafc1-114">In HoloLens 2 Network settings, locate the WiFi network created in step 2 and join it.</span></span>

## <a name="usb-c-tethering"></a><span data-ttu-id="dafc1-115">USB-C-tethering</span><span class="sxs-lookup"><span data-stu-id="dafc1-115">USB-C Tethering</span></span>

<span data-ttu-id="dafc1-116">USB-C-tethering kan een lagere latentie bieden voor geavanceerde werkbelastingen die dit nodig hebben.</span><span class="sxs-lookup"><span data-stu-id="dafc1-116">USB-C tethering can provide lower latency for advanced workloads that need it.</span></span> <span data-ttu-id="dafc1-117">[Azure Remote Rendering](https://azure.microsoft.com/services/remote-rendering)kan bijvoorbeeld profiteren van tethering.</span><span class="sxs-lookup"><span data-stu-id="dafc1-117">[Azure Remote Rendering](https://azure.microsoft.com/services/remote-rendering), for example, can benefit from tethering.</span></span> <span data-ttu-id="dafc1-118">Houd er rekening mee dat voor tethering een kabel tussen het mobiele apparaat en HoloLens is vereist en dat tethering wordt ondersteund door een beperkt aantal apparaten.</span><span class="sxs-lookup"><span data-stu-id="dafc1-118">Note that tethering requires a cable between the cellular device and HoloLens, and tethering is supported by a limited number of devices.</span></span>

### <a name="usb-c-compatibility"></a><span data-ttu-id="dafc1-119">COMPATIBILITEIT MET USB-C</span><span class="sxs-lookup"><span data-stu-id="dafc1-119">USB-C compatibility</span></span>

<span data-ttu-id="dafc1-120">Een beperkt aantal apparaten die zichzelf als ethernetadapter presenteren, kan worden gebruikt met Windows Holographic versie 2004 en hoger.</span><span class="sxs-lookup"><span data-stu-id="dafc1-120">A limited number of devices that present themselves as an ethernet adaptor can be used with Windows Holographic version 2004 and later.</span></span>

<span data-ttu-id="dafc1-121">Apparaten die zichzelf niet als een ethernetadapter presenteren, moeten het algemene Microsoft [RNDIS-stuurprogramma](https://docs.microsoft.com/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) ondersteunen.</span><span class="sxs-lookup"><span data-stu-id="dafc1-121">Devices that do not present themselves as an ethernet adapter must support the generic Microsoft [RNDIS](https://docs.microsoft.com/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) driver.</span></span> <span data-ttu-id="dafc1-122">Maar slechts een beperkt aantal van deze apparaten is compatibel met HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="dafc1-122">But, only a limited number of those devices are compatible with HoloLens 2.</span></span> <span data-ttu-id="dafc1-123">Raadpleeg de fabrikant van uw apparaat voor meer informatie over of het ondersteuning biedt voor het algemene Microsoft RNDIS-stuurprogramma.</span><span class="sxs-lookup"><span data-stu-id="dafc1-123">Please consult your device's manufacturer for details on whether it supports the generic Microsoft RNDIS driver.</span></span>

<span data-ttu-id="dafc1-124">Apparaten die niet compatibel zijn met RNDIS of waarvoor een stuurprogramma of toepassing moet worden geïnstalleerd, worden niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="dafc1-124">Devices that are not RNDIS compatible, or require a driver or application to be installed, are not supported.</span></span>

<span data-ttu-id="dafc1-125">Hoewel Microsoft geen lijst met compatibele apparaten bijhoudt, is er een communitydiscussie over het onderwerp [hier.](https://aka.ms/HLCommunityCell)</span><span class="sxs-lookup"><span data-stu-id="dafc1-125">While Microsoft does not maintain a list of compatible devices, there is a community discussion on the topic [here](https://aka.ms/HLCommunityCell).</span></span>

### <a name="connecting-to-a-tethered-device"></a><span data-ttu-id="dafc1-126">Verbinding maken met een tethered apparaat</span><span class="sxs-lookup"><span data-stu-id="dafc1-126">Connecting to a tethered device</span></span>

1. <span data-ttu-id="dafc1-127">Raadpleeg de handleiding van uw apparaat over het inschakelen van gegevensdeling via USB.</span><span class="sxs-lookup"><span data-stu-id="dafc1-127">Consult your device's manual on how to enable data sharing over USB.</span></span> <span data-ttu-id="dafc1-128">Deze instelling wordt vaak aangeduid als 'USB-tethering', 'Gegevens delen' of 'USB-modem'.</span><span class="sxs-lookup"><span data-stu-id="dafc1-128">This setting is often referred to as "USB Tethering", "Data Sharing" or "USB Modem".</span></span>
1. <span data-ttu-id="dafc1-129">Gegevens delen via USB inschakelen.</span><span class="sxs-lookup"><span data-stu-id="dafc1-129">Enable data sharing over USB.</span></span>
1. <span data-ttu-id="dafc1-130">Verbind uw apparaat met de Usb-C-poort van HoloLens.</span><span class="sxs-lookup"><span data-stu-id="dafc1-130">Connect your device to the HoloLens USB-C port.</span></span>
1. <span data-ttu-id="dafc1-131">In HoloLens 2 Netwerkinstellingen wordt het apparaat automatisch weergegeven als een Ethernet-verbinding.</span><span class="sxs-lookup"><span data-stu-id="dafc1-131">In HoloLens 2 Network settings, the device will automatically appear as an Ethernet connection.</span></span>
