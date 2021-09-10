---
title: Versleuteling en gegevensbeveiliging
description: Meer informatie over versleuteling en gegevensbeveiliging op HoloLens 2 apparaten, waaronder BitLocker en Azure-integratie.
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: beveiliging, hololens, versleuteling, gegevensbeveiliging, BitLocker-apparaat, BitLocker, bitlocker, bitlocker-versleuteling, Azure-integratie,
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: e156fc21bfd1541dd8718a7349e7ba82b45576be
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428918"
---
# <a name="encryption-and-data-protection"></a>Versleuteling en gegevensbeveiliging

Versleuteling en gegevensbeveiliging bebeveiligen gegevens wanneer het apparaat verloren of gestolen is en voorkomt dat niet-geautoriseerde toepassingen toegang hebben tot gevoelige informatie.

## <a name="bitlocker-device-encryption"></a>BitLocker-apparaatversleuteling

BitLocker is een functie voor volledige versleuteling voor integriteitsbeveiliging van ro-media (alleen-lezen) en privacybeveiliging van beschrijfbare media.  Sinds de start is het een effectief beschermingsscherm tegen onbevoegde toegang tot de gegevens tijdens offline-aanvallen. HoloLens 2 bitlocker Apparaatversleuteling (BDE) standaard in om gegevens te beveiligen tegen onbevoegde fysieke toegang tot het apparaat. Microsoft blijft voortdurend investeren en deze technologie verbeteren en blijft zich ontwikkelen om te voldoen aan de behoeften van de toekomst.

BDE is een functie voor gegevensbeveiliging die gebruik maakt van AES-XTS-256-versleuteling op alle volumes in de status-gescheiden indeling van het apparaat. BDE biedt versleuteling op apparaatniveau in een indeling met statussen gescheiden. BitLocker Apparaatversleuteling automatisch ingeschakeld op het besturingssysteem en vaste gegevensvolumes en kan niet worden uitgeschakeld, zelfs niet door IT-beheerders, zodat het apparaat altijd wordt beveiligd.

BDE-versleutelingssleutels worden vervolgens gebruikt voor het transparant ontsleutelen van binaire bestanden en de gegevens die nodig zijn om het apparaat op te starten. Als het besturingssysteemvolume wordt ontgrendeld en een systeem wordt opgestart, worden andere volumes toegankelijk via een volumespecifieke versie van de automatische ontgrendelingsbeveiliging. Er zijn geen andere beveiligingen beschikbaar om de privacy van gebruikers te behouden en het station kan alleen worden ontgrendeld op hetzelfde apparaat. Ro-afdwinging (Alleen-lezen) op vereiste volumes wordt onmiddellijk toegepast en afgedwongen, vanaf de eerste keer opstarten. De Bitlocker-herstelsleutel is niet nodig in de HoloLens 2 levenscyclus.

## <a name="azure-integration"></a>Azure-integratie 

HoloLens 2 stelt klanten in staat om hun apparaten te integreren met Azure-services. Communicatie tussen HoloLens 2-apparaten en Azure maakt gebruik van het TLS-protocol (Transport Layer Security) om gegevens te beveiligen die tussen zichzelf en cloudservices onderweg zijn en die sterke verificatie, privacy van berichten en integriteit bieden. Alle Azure-services ondersteunen volledig TLS 1.2 en services waarbij klanten alleen TLS 1.2 gebruiken, accepteren alleen TLS 1.2-verkeer. De versleutelingsstandaarden van Azure voor gegevens die onderweg zijn, worden beschreven in [Overzicht van Azure-versleuteling.](/azure/security/fundamentals/encryption-overview) Ga naar de Documentatie van Azure voor meer informatie over [best practices voor azure-gegevensbeveiliging en -versleuteling.](/azure/security/fundamentals/data-encryption-best-practices) 

OneDrive, een voorbeeld van cloudintegratie met HoloLens 2, heeft een functie voor automatisch uploaden, waarbij uw bestanden en documenten automatisch kunnen worden geüpload naar de cloud wanneer ze zijn verbonden met internet. Het onderbreken van automatische synchronisatie van bestanden kan niet worden uitgeschakeld via beleid, maar kan rechtstreeks worden geconfigureerd via de UX. 
