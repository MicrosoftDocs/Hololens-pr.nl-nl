---
title: Beveiliging van besturingssysteem met beheerdersrechten
description: Meer informatie over besturingssystemen die geen beheerder zijn, apparaateigenaren en beveiliging op HoloLens mixed reality apparaten.
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
ms.openlocfilehash: ed2d5134a6bc5952063f7dc5dc5d0e31db972b08
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639400"
---
# <a name="admin-less-operating-system"></a>Besturingssysteem met beheerdersrechten

HoloLens 2 minimaliseert de surface area voor escalatie van bevoegdheden door ondersteuning voor de groep Administrators uit te uitschakelen en alle UWP-toepassingscode van derden te beperken tot alleen uitvoeren als standaardgebruikers in de AppContainer-sandbox. Aan deze code wordt alleen toegang verleend tot de resources die zijn beveiligd door mogelijkheden die expliciet in de toepassing worden manifesteerd voor een niet-opleving gebruiker, naast resources die toegankelijk zijn voor alle AppContainers.
Deze toepassingsmogelijkheden blijven het classificatiemodel met drie lagen hebben:
  * Algemeen
  * Beperkt
  * Windows

Windows-onderdelen kunnen ook gebruikmaken van de AppContainer-sandbox via Systeem-UWP's. Zie uwP-documentatie voor meer Windows Universal Windows Platform [(UWP).](/windows/uwp/) Daarnaast maken Windows-onderdelen met een grotere beperking van bevoegdheden (zoals browserinhoudspagina's of parsers) gebruik van de LPAC-sandbox (Less Privileged AppContainer), waardoor de toegang tot de set resources die toegankelijk is voor alle AppContainers wordt afgesloten.

## <a name="device-owner"></a>Eigenaar van het apparaat

Ten slotte is het uitvoeren van specifieke apparaatbrede bewerkingen, zoals het samenvoegen van het apparaat aan een tenant of gebruikersbeheer, alleen toegestaan voor 'apparaateigenaren'. Deze groep wordt door gebruikers op het apparaat ingevuld via een van de volgende stappen:
  * De eerste gebruiker op het apparaat wordt altijd aangewezen als Eigenaar. 
> [!IMPORTANT]
>Voor Azure AD-gebruikers is de uitzondering op deze regel dat als het apparaat is samengevoegd met Azure AD via Autopilot of bulksgewijs Azure AD-inschrijving, dat gebruikmaakt van een niet-echte gebruiker. In dit geval wordt de eerste AAD-gebruiker die zich bij het apparaat heeft aanmelden mogelijk niet automatisch eigenaar van het apparaat, tenzij aan die gebruiker de rol 'globale beheerder' of 'apparaatbeheerder' is toegewezen in Azure Portal. Zie de opmerking hieronder voor meer informatie.  

  * Wanneer een gebruiker wordt gepromoveerd als eigenaar van de Instellingen UX door een andere eigenaar op het apparaat.
  * Als de eigenaar van het apparaat niet meer beschikbaar is (het bedrijf verlaat) en het apparaat lid is van Azure AD, kan de tenantbeheerder de eigenaar van het apparaat wijzigen in een nieuwe gebruiker in Azure Portal. Globale beheerders en apparaatbeheerders van een Azure AD-tenant worden impliciet aangemeld als eigenaren op het apparaat zonder dat een van de vorige stappen is vereist.  

 IT-beheerders kunnen beheren tot welke apps toegang kunnen krijgen via [privacybeleid.](/windows/client-management/mdm/policy-csp-privacy) 

> [!NOTE]
> Zie de documentatie 'Lokale beheerder toewijzen' (maar lees [](/azure/active-directory/devices/assign-local-admin) 'lokale beheerder' als 'apparaateigenaar' omdat de beheerder niet bestaat op HoloLens) voor meer informatie over wie eigenaar van een apparaat wordt gemaakt op een apparaat dat is HoloLens).