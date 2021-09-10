---
title: Integriteit en runtime-attestation met hardwareback-overig
description: Integriteit en runtime-attestation met hardwareback-overig
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.prod: hololens
ms.topic: article
keywords: beveiliging, hololens, integriteit van hardware,runtime attestation, UEFI, UEFI beveiligd opstarten, beveiligd opstarten, TPM, beveiliging tegen bedreigingen, Windows Anti-Persistentie Assurance, code-integriteit, codebeveiliging,
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 037f9325555244314518c81d7814bf983c345af6
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/10/2021
ms.locfileid: "124429010"
---
# <a name="hardware-backed-integrity-and-runtime-attestation"></a>Hardware-backed integriteit en runtime attestation

Hardware-ondersteuning integriteit en runtime attestation beschermt tegen bedreigingen die afkomstig zijn vóór het begin van een besturingssysteem, tijdens runtime, wanneer het apparaat hardware gebruikt, en externe Attestation-services om ervoor te zorgen dat integriteit behouden blijft tijdens het opstarten en tijdens de duur van de runtime.

## <a name="uefi-secure-boot"></a>Beveiligd opstarten met UEFI

HoloLens 2 unified Extensible Firmware Interface (UEFI) wordt beveiligd opstarten altijd afgedwongen en UEFI wordt alleen Windows Holographic for Business.
Beveiligd opstarten zorgt ervoor dat de volledige opstartketen wordt gecontroleerd op integriteit en dat Windows altijd wordt opgestart met het juiste beveiligingsbeleid dat erop is toegepast. Meer informatie over [Beveiligd opstarten.](/windows-hardware/design/device-experiences/oem-secure-boot)

## <a name="tpm"></a>TPM

De Trusted Platform Module (TPM) is een gespecialiseerde chip op een eindpuntapparaat. HoloLens 2 gebruikt een TPM 2.0, die hardware-afgedwongen sleutelisolatie biedt. Meer informatie over [de grondbeginselen van TPM.](/windows/security/information-protection/tpm/tpm-fundamentals)

## <a name="persistence-access-threat-protection"></a>Beveiliging tegen persistentietoegang tegen bedreigingen

Het doel van de meeste cyberaanvallen is om permanente toegang tot een apparaat te behouden. Voor cybercriminaliteit zorgt het onderhoud van deze persistentie ervoor dat een gecompromitteerd Windows-apparaat lid kan worden van een botnet, toegang kan verkopen aan het apparaat of andere schadelijke gebruikers, of om herhaalde gegevensdiefstal mogelijk te maken. In de wereld van gerichte aanvallen is persistentie essentieel voor een geslaagde cyberaanval, op een apparaat of (vaker) een heel netwerk.  

Gerichte aanvallen worden in feite beschouwd als 'geavanceerde permanente bedreigingen', vanwege de strategische noodzaak om toegang te houden tot een doelapparaat of netwerk. Daarom beschouwt Windows Holographic for Business bescherming tegen persistentie absoluut cruciaal en wordt gebruikgemaakt van anti-persistentietechnologie om een goede beveiligingsbeaam van klanten te maken.

### <a name="secure-boot"></a>Beveiligd opstarten

HoloLens 2 UEFI (Unified Extensible Firmware Interface) wordt beveiligd opstarten afgedwongen op alle statussen van het basisbesturingssysteem. UEFI start alleen vertrouwde Microsoft-platformen op, die ervoor zorgen dat de volledige opstartketen wordt gecontroleerd op integriteit en dat Windows altijd wordt opgestart met het juiste beveiligingsbeleid dat erop is toegepast. HoloLens 2 beveiligd opstarten niet worden uitgeschakeld en kan ook geen opstart loaders van derden worden toegestaan.

> [!Tip]
> Meer informatie over [beveiligd opstarten.](/windows-hardware/design/device-experiences/oem-secure-boot)

### <a name="windows-anti-persistence-assurance"></a>Windows Anti-persistentiegarantie

HoloLens 2 anti-persistentie garandeert de gebruikers dat zelfs in de zeldzame situatie dat er ooit een runtimecompromittie van het systeem zou plaatsvinden, zoals een externe exploit, een dergelijke gebeurtenis zou worden opgelost met alle schadelijke code die uit het systeem is verwijderd door het apparaat uit te schakelen. Om de anti-persistentie verder te versterken, HoloLens 2 krachtige integriteitsbeveiliging toegevoegd en zijn alleen-lezenbeveiligingen van kracht.

Persistentie van besturingssysteemgegevens in de vorm van gegevens is nog steeds mogelijk, tenzij de gebruiker pbr (push-button reset) uitvoert van het apparaat waarmee alle veranderlijke partities worden gewist. Hoewel persistentie voor onveranderbare partities veel moeilijker wordt gemaakt, moet de gebruiker de HoloLens 2 PBR gebruiken om mogelijke persistentie van onveranderlijke onderdelen te verwijderen.

## <a name="code-integrity-protection"></a>Beveiliging van code-integriteit

Code-integriteit (CI) is een belangrijke beveiligings-eigenschap van een modern besturingssysteem. Het afdwingen van CI maakt goede beveiligingsbeslissingen mogelijk, omdat het garandeert dat de herkomst van code transparant is voor zowel de gebruiker als het besturingssysteem. Volledige code-integriteit moet het ondertekenen van eerdere binaire afbeeldingen uitbreiden en runtime afdwingen, zoals controlestroomintegriteit en dynamische codebeperkingen. CI is essentieel voor het voorkomen van meerdere soorten aanvallen, waaronder sociaal ontwikkelde malware, zoals ransomware, aanvallen met externe code-uitvoering en verschillende andere aanvalsklassen.
