---
title: HoloLens beveiligingsarchitectuur
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
ms.openlocfilehash: fd6409f5087ef7d6e7ab90d6ef8dcb83e1c490746803ad869ef075dace24bae7
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/05/2021
ms.locfileid: "115665519"
---
# <a name="security-overview-and-architecture"></a>Beveiligingsoverzicht en -architectuur

De HoloLens 2-beveiligingsarchitectuur is vanaf de grond ontworpen en ontworpen om vrij te zijn van verouderde beveiligingsproblemen, terwijl er tegelijkertijd een geminimaliseerd aanvalsoppervlak ontstaat. Deze nieuwe, innovatieve architectuur biedt veilige opslaglocaties en geavanceerde beveiligingselementen, met mechanismen waarmee besturingssystemen kunnen worden afgeschermd tegen mogelijke bedreigingen en beveiligingsproblemen.

HoloLens 2 hardware, software, netwerken en services om end-to-end-beveiliging te bieden en tegelijkertijd de gebruiker een optimale ervaring te bieden. Met HoloLens 2 wordt een groot deel van de beveiligingsfuncties nu automatisch ingeschakeld, waardoor het minimaliseren van de inspanning die nodig is om het besturingssysteem correct in te stellen en te configureren.

Windows HoloLens 2 en besturingssysteemarchitectuur biedt deze innovatieve beveiligingsfuncties:

  * **Statusscheiding** en isolatie: deze nieuwe architectuur beschermt kritieke delen van het HoloLens 2-besturingssysteem tegen veranderingen, zoals de onderdelen die nodig zijn om het basisbesturingssysteem op te starten in een vertrouwde status. Isolatietechnologie wordt gebruikt om niet-vertrouwde apps in een sandboxgebied tegen te gaan, zodat ze geen invloed hebben op de systeembeveiliging. Het hele besturingssysteem is gesegmenteerd in beveiligde secties, met elke sectie afgeschermd door een combinatie van verschillende beveiligingstechnologieën.
  
  * **Gegevensbeveiliging:** als het apparaat van een gebruiker verloren of gestolen is, voorkomt HoloLens 2 dat niet-geautoriseerde toepassingen gevoelige informatie kunnen lezen door gebruik te maken van BitLocker-versleuteling van gegevens. 
  
  * **Besturingssysteem zonder** wachtwoord: oudere, op wachtwoorden gebaseerde besturingssystemen kunnen per ongeluk gebruikers blootstellen aan phishing-bedreigingen en waren vaak verantwoordelijk voor aangetaste accounts. Windows Holographic for Business voorkomt het gebruik van wachtwoorden voor MSA- en Azure AD-aanmelding en versterkt de beveiliging van gebruikersidentiteiten met Windows Hello™ en FIDO2-aanmelding. 
  
    > [!NOTE]
    > Als u FIDO2-ondersteuning wilt hebben, moet het apparaat build 19041 of hoger hebben. 

  * **Netwerkbeveiliging:** HoloLens 2 biedt de gebruiker verbeterde netwerkbeveiliging via verbeterde protocollen en standaardinstellingen.
