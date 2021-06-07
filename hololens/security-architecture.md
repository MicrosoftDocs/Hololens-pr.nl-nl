---
title: HoloLens-beveiligingsarchitectuur
description: Beveiligingsarchitectuur
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: beveiliging, hololens, hololens 2, hololens2-beveiliging, beveiligingsoverzicht, beveiligingsarchitectuur, architectuur, hololens 2-architectuur
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: d8e68f73d05db397a7ee088382e82dfa762177b0
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379383"
---
# <a name="security-overview-and-architecture"></a>Beveiligingsoverzicht en -architectuur

De HoloLens 2-beveiligingsarchitectuur is vanaf de basis ontworpen en ontworpen om geen oudere beveiligingsproblemen te veroorzaken, terwijl er tegelijkertijd een geminimaliseerd aanvalsoppervlak ontstaat. Deze nieuwe, innovatieve architectuur biedt veilige opslaglocaties en geavanceerde beveiligingselementen, met mechanismen waarmee besturingssystemen kunnen worden afgeschermd tegen mogelijke bedreigingen en beveiligingsproblemen.

HoloLens 2 combineert hardware, software, netwerken en services voor end-to-end-beveiliging en biedt de gebruiker een optimale ervaring. Met HoloLens 2 is een groot deel van de beveiligingsfuncties nu automatisch ingeschakeld, waardoor het zo min mogelijk is om het besturingssysteem correct in te stellen en te configureren.

Windows HoloLens 2 en besturingssysteemarchitectuur biedt deze innovatieve beveiligingsfuncties:

  * **Statusscheiding** en isolatie: deze nieuwe architectuur beschermt kritieke delen van het HoloLens 2-besturingssysteem tegen veranderingen, zoals de onderdelen die nodig zijn om het basisbesturingssysteem in een vertrouwde status op te starten. Isolatietechnologie wordt gebruikt om niet-vertrouwde apps in een sandboxgebied tegen te gaan, om ervoor te zorgen dat ze geen invloed hebben op de systeembeveiliging. Het hele besturingssysteem is gesegmenteerd in beveiligde secties, met elke sectie afgeschermd door een combinatie van verschillende beveiligingstechnologieën.
  
  * **Gegevensbeveiliging:** als het apparaat van een gebruiker verloren raakt of wordt gestolen, voorkomt HoloLens 2 dat niet-geautoriseerde toepassingen gevoelige informatie kunnen lezen door gebruik te maken van BitLocker-versleuteling van gegevens. 
  
  * **Besturingssysteem zonder** wachtwoord: oudere besturingssystemen op basis van wachtwoorden kunnen per ongeluk gebruikers blootstellen aan phishing-bedreigingen en zijn vaak verantwoordelijk voor aangetaste accounts. Windows Holographic for Business het gebruik van wachtwoorden voor MSA- en Azure AD-aanmelding wordt voorkomen en wordt de beveiliging van gebruikersidentiteiten versterkt met Windows Hello™- en FIDO2-aanmelding. 
  
    > [!NOTE]
    > Als u FIDO2-ondersteuning wilt hebben, moet het apparaat op build 19041 of hoger staan. 

  * **Netwerkbeveiliging:** HoloLens 2 biedt de gebruiker verbeterde netwerkbeveiliging via verbeterde protocollen en standaardinstellingen.
