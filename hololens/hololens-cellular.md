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
ms.openlocfilehash: 6f7da0263e8637486f0151fd2b9da55da8feccc1
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/13/2021
ms.locfileid: "126035906"
---
# <a name="connect-to-cellular-and-5g"></a>Verbinding maken naar mobiel en 5G

HoloLens 2 ondersteunt twee methoden om verbinding te maken met mobiele netwerken en 5G-netwerken:

- Een ad-hoc Wi-Fi-netwerk dat wordt geleverd door het mobiele apparaat, meestal aangeduid als een 'Hotspot'
- Beperkte ondersteuning voor USB-C-tethered apparaten

## <a name="hotspot-wifi"></a>Hotspot (Wi-Fi)

Aan de meeste mobiele connectiviteitsbehoeften kan een hotspot worden voldaan. HoloLens 2 Wi-Fi ondersteunt 802.11ac, dat de bandbreedte- en latentievereisten kan bieden die nodig zijn voor de meest voorkomende gebruiksgevallen. Wi-Fi is ook kabelloos en biedt compatibiliteit met het grootste aantal mobiele apparaten.

### <a name="connecting-to-a-hotspot"></a>Verbinding maken met een hotspot

1. Raadpleeg de handleiding van uw apparaat over het inschakelen van de hotspotmodus.
1. Schakel de hotspotmodus in door een naam voor het netwerk en een bekend wachtwoord op te geven.
1. Zoek HoloLens 2 netwerkinstellingen het Wi-Fi-netwerk dat u in stap 2 hebt gemaakt en voeg het toe.

## <a name="usb-c-tethering"></a>USB-C-tethering

USB-C-tethering kan een lagere latentie bieden voor geavanceerde werkbelastingen die dit nodig hebben. [Azure Remote Rendering](https://azure.microsoft.com/services/remote-rendering)kan bijvoorbeeld profiteren van tethering. Houd er rekening mee dat voor tethering een kabel tussen het mobiele apparaat en HoloLens vereist is en dat tethering wordt ondersteund door een beperkt aantal apparaten.

### <a name="usb-c-compatibility"></a>COMPATIBILITEIT MET USB-C

Een beperkt aantal apparaten die zich als ethernetadapter presenteren, kan worden gebruikt met Windows Holographic-versie 2004 en hoger.

Apparaten die zichzelf niet als een ethernetadapter presenteren, moeten het algemene Microsoft [RNDIS-stuurprogramma](/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) ondersteunen. Maar slechts een beperkt aantal van deze apparaten is compatibel met HoloLens 2. Raadpleeg de fabrikant van uw apparaat voor meer informatie over of het ondersteuning biedt voor het algemene Microsoft RNDIS-stuurprogramma.

Apparaten die niet compatibel zijn met RNDIS of waarvoor een stuurprogramma of toepassing moet worden geïnstalleerd, worden niet ondersteund.

Hoewel Microsoft geen lijst met compatibele apparaten bijhoudt, is er een communitydiscussie over het onderwerp [hier.](https://aka.ms/HLCommunityCell)

### <a name="connecting-to-a-tethered-device"></a>Verbinding maken met een tethered apparaat

1. Raadpleeg de handleiding van uw apparaat over het inschakelen van gegevensdeling via USB. Deze instelling wordt vaak aangeduid als 'USB-tethering', 'Gegevens delen' of 'USB-modem'.
1. Gegevens delen via USB inschakelen.
1. Verbinding maken apparaat naar de HoloLens USB-C-poort.
1. In HoloLens 2 netwerkinstellingen wordt het apparaat automatisch weergegeven als een Ethernet-verbinding.
