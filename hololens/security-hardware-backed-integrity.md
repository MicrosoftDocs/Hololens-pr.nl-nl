---
title: Integriteit en runtime-attestation met hardwareback-overig
description: Integriteit en runtime-attestation met hardwareback-overig
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.prod: hololens
ms.topic: article
keywords: beveiliging, hololens, hardware-ondersteuning integriteit, runtime attestation, UEFI, UEFI beveiligd opstarten, beveiligd opstarten, TPM, beveiliging tegen bedreigingen, Windows Anti-Persistence Assurance, code-integriteit, codebeveiliging,
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 0a89fa5e61e560f629444efd2728f6dd41db60d3
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379414"
---
# <a name="hardware-backed-integrity-and-runtime-attestation"></a>Hardware-back-integriteit en runtime attestation

Hardware-back-integriteit en runtime attestation beschermen tegen bedreigingen die afkomstig zijn vóór het begin van een besturingssysteem, tijdens runtime, wanneer het apparaat hardware gebruikt, en externe Attestation-services om ervoor te zorgen dat de integriteit behouden blijft tijdens het opstarten en tijdens de duur van de runtime.

## <a name="uefi-secure-boot"></a>Beveiligd opstarten met UEFI

HoloLens 2 UEFI (Unified Extensible Firmware Interface) Beveiligd opstarten altijd afdwingen en UEFI wordt alleen Windows Holographic for Business.
Beveiligd opstarten zorgt ervoor dat de volledige opstartketen wordt gecontroleerd op integriteit en dat Windows altijd wordt opgestart met het juiste beveiligingsbeleid dat erop is toegepast. Meer informatie over [Beveiligd opstarten.](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot)

## <a name="tpm"></a>TPM

De Trusted Platform Module (TPM) is een gespecialiseerde chip op een eindpuntapparaat. HoloLens 2 maakt gebruik van TPM 2.0, dat hardware-afgedwongen sleutelisolatie biedt. Meer informatie over [de grondbeginselen van TPM.](https://docs.microsoft.com/windows/security/information-protection/tpm/tpm-fundamentals)

## <a name="persistence-access-threat-protection"></a>Bedreigingsbeveiliging voor persistentietoegang

Het doel van de meeste cyberaanvallen is om permanente toegang tot een apparaat te behouden. Voor cybercriminaliteit kan een gecompromitteerd Windows-apparaat bij een botnet blijven, toegang tot het apparaat of andere schadelijke gebruikers verkopen of herhaalde gegevensdiefstal inschakelen. In de wereld van gerichte aanvallen is persistentie essentieel voor een geslaagde cyberaanval: op een apparaat of (vaker) een heel netwerk.  

Gerichte aanvallen worden in feite beschouwd als 'geavanceerde permanente bedreigingen', vanwege hun strategische noodzaak om toegang te houden tot een doelapparaat of netwerk. Daarom beschouwt Windows Holographic for Business bescherming tegen persistentie absoluut cruciaal en wordt gebruikgemaakt van anti-persistentietechnologie om een goede beveiligingsbeaam van klanten te maken.

### <a name="secure-boot"></a>Beveiligd opstarten

HoloLens 2 UEFI (Unified Extensible Firmware Interface) wordt beveiligd opstarten afgedwongen op alle basisbesturingssysteemtoestanden. UEFI start alleen vertrouwde Microsoft-platforms op, wat ervoor zorgt dat de volledige opstartketen wordt gecontroleerd op integriteit en dat Windows altijd wordt opgestart met het juiste beveiligingsbeleid dat erop is toegepast. HoloLens 2 beveiligd opstarten wordt niet uitgeschakeld en staat geen opstartbelastingen van derden toe.

> [!Tip]
> Meer informatie over [Beveiligd opstarten.](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot)

### <a name="windows-anti-persistence-assurance"></a>Windows Anti-Persistence Assurance

HoloLens 2 anti-persistentie garandeert de gebruikers dat zelfs in de zeldzame situatie dat er ooit een runtimecompromitting van het systeem zou plaatsvinden, zoals een externe exploit, een dergelijke gebeurtenis zou worden vereenvoudigd met alle schadelijke code die uit het systeem is verwijderd door het apparaat uit te schakelen. Om de anti-persistentie verder te versterken, HoloLens 2 krachtige integriteitsbeveiliging toegevoegd en is er alleen-lezenbeveiliging toegevoegd.

Persistentie van besturingssysteemgegevens in de vorm van gegevens is nog steeds mogelijk, tenzij de gebruiker push-button reset (PBR) uitvoert van het apparaat dat alle veranderlijke partities wist. Hoewel persistentie voor onveranderbare partities veel moeilijker wordt gemaakt, moet de gebruiker de HoloLens 2 PBR gebruiken om mogelijke persistentie van bedreigingen van veranderlijke onderdelen te verwijderen.

## <a name="code-integrity-protection"></a>Beveiliging van code-integriteit

Code-integriteit (CI) is een belangrijke beveiligings-eigenschap van een modern besturingssysteem. Het afdwingen van CI maakt goede beveiligingsbeslissingen mogelijk, omdat het garandeert dat de herkomst van code transparant is voor zowel de gebruiker als het besturingssysteem. Volledige code-integriteit moet eerdere binaire ondertekening van afbeeldingen uitbreiden en runtime-afdwinging bevatten, zoals controlestroomintegriteit en dynamische codebeperkingen. CI is essentieel voor het voorkomen van meerdere soorten aanvallen, waaronder sociaal ontwikkelde malware, zoals ransomware, aanvallen met externe code-uitvoering en verschillende andere aanvalsklassen.
