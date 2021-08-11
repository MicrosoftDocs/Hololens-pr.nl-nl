---
title: Verbinding maken naar mobiel en 5G
description: Verbinding maken met mobiele netwerken vanaf uw HoloLens mixed reality apparaten.
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
ms.openlocfilehash: 0a31ff0af0af5b60fc0a44ef8fc5a85b5b50e766201d5441d508fd23dd0369e4
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/05/2021
ms.locfileid: "115664482"
---
# <a name="connect-to-cellular-and-5g"></a>Verbinding maken naar mobiel en 5G

HoloLens 2 ondersteunt twee methoden om verbinding te maken met mobiele en 5G-netwerken:

- Een ad-hoc Wi-Fi-netwerk dat wordt geleverd door het mobiele apparaat, vaak aangeduid als een 'Hotspot'
- Beperkte ondersteuning voor USB-C-tethered apparaten

## <a name="hotspot-wifi"></a>Hotspot (Wi-Fi)

De meeste mobiele connectiviteitsbehoeften kunnen worden bereikt met een hotspot. HoloLens 2 WiFi ondersteunt 802.11ac, dat de bandbreedte- en latentievereisten kan bieden die nodig zijn voor de meest voorkomende gebruiksgevallen. Wi-Fi is ook kabelloos en biedt compatibiliteit met het grootste aantal mobiele apparaten.

### <a name="connecting-to-a-hotspot"></a>Verbinding maken met een hotspot

1. Raadpleeg de handleiding van uw apparaat over het inschakelen van de hotspotmodus.
1. Schakel de hotspotmodus in, met een naam voor het netwerk en een bekend wachtwoord.
1. Zoek HoloLens 2 netwerkinstellingen het Wi-Fi-netwerk dat u in stap 2 hebt gemaakt en voeg het toe.

## <a name="usb-c-tethering"></a>USB-C-tethering

USB-C-tethering kan een lagere latentie bieden voor geavanceerde werkbelastingen die dit nodig hebben. [Azure Remote Rendering](https://azure.microsoft.com/services/remote-rendering)kan bijvoorbeeld profiteren van tethering. Houd er rekening mee dat voor tethering een kabel tussen het mobiele apparaat en HoloLens vereist en dat tethering wordt ondersteund door een beperkt aantal apparaten.

### <a name="usb-c-compatibility"></a>COMPATIBILITEIT MET USB-C

Een beperkt aantal apparaten die zichzelf als ethernetadapter presenteren, kan worden gebruikt met Windows Holographic-versie 2004 en hoger.

Apparaten die zichzelf niet als een ethernetadapter presenteren, moeten het algemene Microsoft [RNDIS-stuurprogramma](/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) ondersteunen. Maar slechts een beperkt aantal van deze apparaten is compatibel met HoloLens 2. Raadpleeg de fabrikant van uw apparaat voor meer informatie over of het ondersteuning biedt voor het algemene Microsoft RNDIS-stuurprogramma.

Apparaten die niet compatibel zijn met RNDIS of waarvoor een stuurprogramma of toepassing moet worden geïnstalleerd, worden niet ondersteund.

Hoewel Microsoft geen lijst met compatibele apparaten bijhoudt, is er een communitydiscussie over het onderwerp [hier](https://aka.ms/HLCommunityCell).

### <a name="connecting-to-a-tethered-device"></a>Verbinding maken met een tethered apparaat

1. Raadpleeg de handleiding van uw apparaat over het inschakelen van gegevensdeling via USB. Deze instelling wordt vaak aangeduid als 'USB-tethering', 'Gegevens delen' of 'USB-modem'.
1. Gegevens delen via USB inschakelen.
1. Verbinding maken apparaat naar de HoloLens USB-C-poort.
1. In HoloLens 2 Netwerkinstellingen wordt het apparaat automatisch weergegeven als een Ethernet-verbinding.
