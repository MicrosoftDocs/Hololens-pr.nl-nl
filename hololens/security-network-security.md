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
# <a name="network-security"></a>Netwerkbeveiliging

## <a name="network-protocols"></a>Netwerkprotocollen

Het verouderde NetBIOS (Network Basic Input/Output System) werd in het verleden veel gebruikt in LAN-scenario's, vaak voor het leveren van naamom oplossing voor een computer en gedeelde mappen. Maar na een periode blijkt NetBIOS vatbaar te zijn voor meerdere aanvallen en is de relevantie ervan afgenomen ten opzichte van andere veiligere protocollen. Als u dit beveiligingsprobleem wilt verwijderen, HoloLens 2 netBIOS-gerelateerde code uit het besturingssysteem verwijderd.

TLS-protocollen (Transport Layer Security) zijn voortdurend in ontwikkeling. Om de verschillende beveiligingsactiviteiten die op dit gebied zijn ontdekt bij te houden, heeft de computerbranche zijn overgeplaatst naar nieuwere en effectievere versies. Vanwege de tijd die nodig is voor alle serverimplementaties om de nieuwe TLS-protocolversies te gebruiken, kan er een terugvalmechanisme worden geïmplementeerd waarmee de client en servers op verschillende standaardprotocolversies nog steeds kunnen communiceren tijdens de periode.

## <a name="secure-connectivity"></a>Beveiligde connectiviteit 

De Windows Defender Firewall biedt essentiële functionaliteit om de connectiviteit van apparaten te beveiligen. Met HoloLens 2 is de firewall altijd ingeschakeld en zijn er geen manieren om deze programmatisch of via de gebruikersinterface uit te schakelen.

De privacy van externe toegang en verbindingen voor mobiele clients kan worden gegarandeerd via het [UWP VPN-internetverbindingsplatform.](https://docs.microsoft.com/uwp/api/Windows.Networking.Vpn?view=winrt-19041) Externe VPN-providers kunnen hun eigen in plug-ins maken met behulp van WinRT-API's die worden uitgevoerd in de AppContainer-sandbox, waardoor de complexiteit en problemen die vaak worden geassocieerd met het schrijven van stuurprogramma's op systeemniveau, worden voorkomen.
