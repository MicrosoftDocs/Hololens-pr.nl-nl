---
title: Beveiliging van besturingssysteem met beheerdersrechten
description: Meer informatie over besturingssystemen met beheerdersrechten, apparaateigenaren en beveiliging op HoloLens-mixed reality apparaten.
ms.prod: hololens
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: security, hololens, adminless, admin-less, operating system, admin-less operating system, admin os, admin-less os, hololens 2, hololens2 security,
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 972bbc689505d42993cf47d82351ceeb79a0606b
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379397"
---
# <a name="admin-less-operating-system"></a>Besturingssysteem met beheerdersrechten

HoloLens 2 minimaliseert de surface area voor escalatie van bevoegdheden door ondersteuning voor de groep Administrators uit te uitschakelen en alle UWP-toepassingscode van derden te beperken zodat deze alleen wordt uitgevoerd als standaardgebruikers in de AppContainer-sandbox. Aan deze code wordt alleen toegang verleend tot de resources die worden beveiligd door mogelijkheden die expliciet worden manifesteerd in de toepassing voor een niet-geleveerde gebruiker, naast de resources die toegankelijk zijn voor alle AppContainers.
Deze toepassingsmogelijkheden hebben nog steeds het classificatiemodel met drie lagen:
  * Algemeen
  * Beperkt
  * Windows

Windows-onderdelen kunnen ook gebruikmaken van de AppContainer-sandbox via Systeem-UWP's. Zie UWP-documentatie voor Universeel Windows-platform [(UWP).](https://docs.microsoft.com/windows/uwp/) Daarnaast maken Windows-onderdelen met een grotere beperking van bevoegdheden (zoals browserinhoudspagina's of parsers) gebruik van de LPAC-sandbox (Less Privileged AppContainer), waardoor de toegang tot de set resources die toegankelijk is voor alle AppContainers wordt verlaagd.

## <a name="device-owner"></a>Eigenaar van het apparaat

Ten slotte is het uitvoeren van specifieke apparaatbrede bewerkingen, zoals het samenvoegen van het apparaat aan een tenant of gebruikersbeheer, alleen toegestaan voor 'apparaateigenaren'. Deze groep wordt ingevuld door gebruikers op het apparaat via een van de volgende stappen:
  * De eerste gebruiker op het apparaat wordt altijd aangewezen als eigenaar. 
> [!IMPORTANT]
>Voor Azure AD-gebruikers is de uitzondering op deze regel dat als het apparaat is samengevoegd met Azure AD via Autopilot of bulksgewijs Azure AD-inschrijving, die gebruikmaakt van een niet-echte gebruiker. In dit geval wordt de eerste AAD-gebruiker die zich bij het apparaat heeft aanmelden mogelijk niet automatisch eigenaar van het apparaat, tenzij aan die gebruiker de rol 'globale beheerder' of 'apparaatbeheerder' is toegewezen in Azure Portal. Zie de opmerking hieronder voor meer informatie.  

  * Wanneer een gebruiker door een andere eigenaar op het apparaat wordt gepromoveerd als eigenaar van de UX-instellingen.
  * Als de eigenaar van het apparaat niet meer beschikbaar is (het bedrijf verlaat) en het apparaat lid is van Azure AD, kan de tenantbeheerder de eigenaar van het apparaat wijzigen in een nieuwe gebruiker in Azure Portal. Globale beheerders en apparaatbeheerders van een Azure AD-tenant worden impliciet aangemeld als eigenaren op het apparaat zonder dat een van de vorige stappen is vereist.  

 IT-beheerders kunnen beheren tot welke apps toegang hebben via [privacybeleid.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy) 

> [!NOTE]
> Zie de documentatie 'Lokale beheerder toewijzen' [(maar](https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin) lees 'lokale beheerder' als 'apparaateigenaar' omdat de beheerder niet bestaat op HoloLens) voor meer informatie over wie eigenaar van een apparaat wordt gemaakt op een apparaat dat is verbonden met Azure AD.