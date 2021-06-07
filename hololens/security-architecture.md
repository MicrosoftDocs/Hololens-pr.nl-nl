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
# <a name="security-overview-and-architecture"></a><span data-ttu-id="45e1b-104">Beveiligingsoverzicht en -architectuur</span><span class="sxs-lookup"><span data-stu-id="45e1b-104">Security overview and architecture</span></span>

<span data-ttu-id="45e1b-105">De HoloLens 2-beveiligingsarchitectuur is vanaf de basis ontworpen en ontworpen om geen oudere beveiligingsproblemen te veroorzaken, terwijl er tegelijkertijd een geminimaliseerd aanvalsoppervlak ontstaat.</span><span class="sxs-lookup"><span data-stu-id="45e1b-105">The HoloLens 2 security architecture was designed and engineered from the ground up to be free from legacy security issues, while creating a minimized attack surface.</span></span> <span data-ttu-id="45e1b-106">Deze nieuwe, innovatieve architectuur biedt veilige opslaglocaties en geavanceerde beveiligingselementen, met mechanismen waarmee besturingssystemen kunnen worden afgeschermd tegen mogelijke bedreigingen en beveiligingsproblemen.</span><span class="sxs-lookup"><span data-stu-id="45e1b-106">This new, innovative architecture offers secure storage locations and advanced security elements, with mechanisms capable of shielding operating systems from potential threats and vulnerabilities.</span></span>

<span data-ttu-id="45e1b-107">HoloLens 2 combineert hardware, software, netwerken en services voor end-to-end-beveiliging en biedt de gebruiker een optimale ervaring.</span><span class="sxs-lookup"><span data-stu-id="45e1b-107">HoloLens 2 combines hardware, software, networking, and services to deliver end-to-end security, while providing the user with an optimal experience.</span></span> <span data-ttu-id="45e1b-108">Met HoloLens 2 is een groot deel van de beveiligingsfuncties nu automatisch ingeschakeld, waardoor het zo min mogelijk is om het besturingssysteem correct in te stellen en te configureren.</span><span class="sxs-lookup"><span data-stu-id="45e1b-108">With HoloLens 2, a large majority of security features are now turned on automatically, minimizing the effort required to correctly set up and configure the operating system.</span></span>

<span data-ttu-id="45e1b-109">Windows HoloLens 2 en besturingssysteemarchitectuur biedt deze innovatieve beveiligingsfuncties:</span><span class="sxs-lookup"><span data-stu-id="45e1b-109">Windows HoloLens 2 and operating system architecture offers these innovative security features:</span></span>

  * <span data-ttu-id="45e1b-110">**Statusscheiding** en isolatie: deze nieuwe architectuur beschermt kritieke delen van het HoloLens 2-besturingssysteem tegen veranderingen, zoals de onderdelen die nodig zijn om het basisbesturingssysteem in een vertrouwde status op te starten.</span><span class="sxs-lookup"><span data-stu-id="45e1b-110">**State separation and isolation**:  This new architecture protects critical portions of the HoloLens 2 operating system from change - such as those required for the core operating system to boot into a trusted state.</span></span> <span data-ttu-id="45e1b-111">Isolatietechnologie wordt gebruikt om niet-vertrouwde apps in een sandboxgebied tegen te gaan, om ervoor te zorgen dat ze geen invloed hebben op de systeembeveiliging.</span><span class="sxs-lookup"><span data-stu-id="45e1b-111">Isolation technology is used to confine untrusted apps in a sandbox area, ensuring that they cannot impact the system security.</span></span> <span data-ttu-id="45e1b-112">Het hele besturingssysteem is gesegmenteerd in beveiligde secties, met elke sectie afgeschermd door een combinatie van verschillende beveiligingstechnologieën.</span><span class="sxs-lookup"><span data-stu-id="45e1b-112">The entire operating system is segmented into secure sections, with each section shielded by a combination of different security technologies.</span></span>
  
  * <span data-ttu-id="45e1b-113">**Gegevensbeveiliging:** als het apparaat van een gebruiker verloren raakt of wordt gestolen, voorkomt HoloLens 2 dat niet-geautoriseerde toepassingen gevoelige informatie kunnen lezen door gebruik te maken van BitLocker-versleuteling van gegevens.</span><span class="sxs-lookup"><span data-stu-id="45e1b-113">**Data Protection**: If a user’s device is lost or stolen, HoloLens 2 prevents unauthorized applications from reading sensitive information by relying on BitLocker encryption of data.</span></span> 
  
  * <span data-ttu-id="45e1b-114">**Besturingssysteem zonder** wachtwoord: oudere besturingssystemen op basis van wachtwoorden kunnen per ongeluk gebruikers blootstellen aan phishing-bedreigingen en zijn vaak verantwoordelijk voor aangetaste accounts.</span><span class="sxs-lookup"><span data-stu-id="45e1b-114">**Password-less operating system**:  Older, password-based operating systems could inadvertently expose users to phishing threats and were often responsible for compromised accounts.</span></span> <span data-ttu-id="45e1b-115">Windows Holographic for Business het gebruik van wachtwoorden voor MSA- en Azure AD-aanmelding wordt voorkomen en wordt de beveiliging van gebruikersidentiteiten versterkt met Windows Hello™- en FIDO2-aanmelding.</span><span class="sxs-lookup"><span data-stu-id="45e1b-115">Windows Holographic for Business eliminates the use of passwords for MSA and Azure AD sign-in and strengthens user-identity protection with Windows Hello™ and FIDO2 sign-in.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="45e1b-116">Als u FIDO2-ondersteuning wilt hebben, moet het apparaat op build 19041 of hoger staan.</span><span class="sxs-lookup"><span data-stu-id="45e1b-116">To have FIDO2 support, the device must be on Build 19041 or higher.</span></span> 

  * <span data-ttu-id="45e1b-117">**Netwerkbeveiliging:** HoloLens 2 biedt de gebruiker verbeterde netwerkbeveiliging via verbeterde protocollen en standaardinstellingen.</span><span class="sxs-lookup"><span data-stu-id="45e1b-117">**Network security**: HoloLens 2 offers the user increased network security via improved protocols and default settings.</span></span>
