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
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428190"
---
# <a name="admin-less-operating-system"></a>Besturingssysteem met beheerdersrechten

HoloLens 2 minimaliseert de surface area voor escalatie van bevoegdheden door ondersteuning voor de groep Administrators uit te uitschakelen en alle CODE van uwP-toepassingen van derden te beperken tot alleen uitvoeren als standaardgebruikers in de AppContainer-sandbox. Aan deze code wordt alleen toegang verleend tot de resources die worden beveiligd door mogelijkheden die expliciet in de toepassing worden manifesteerd voor een gebruiker die geen niveau heeft, naast de resources die toegankelijk zijn voor alle AppContainers.
Deze toepassingsmogelijkheden blijven het classificatiemodel met drie lagen hebben:
  * Algemeen
  * Beperkt
  * Windows

Windows kunnen ook gebruikmaken van de AppContainer-sandbox via Systeem-UWP's. Zie UWP-documentatie voor meer informatie over Universal Windows Platform [(UWP).](/windows/uwp/) Daarnaast maken Windows-onderdelen met een grotere beperking van bevoegdheden (zoals browserinhoudspagina's of parsers) gebruik van de LPAC-sandbox (Less Privileged AppContainer), waardoor de toegang tot de set resources die toegankelijk is voor alle AppContainers wordt afgesneden.

## <a name="device-owner"></a>Eigenaar van het apparaat

Ten slotte is het uitvoeren van specifieke apparaatbrede bewerkingen, zoals het samenvoegen van het apparaat met een tenant of gebruikersbeheer, alleen toegestaan voor 'apparaateigenaren'. Deze groep wordt door gebruikers op het apparaat ingevuld via een van de volgende stappen:
  * De eerste gebruiker op het apparaat wordt altijd aangewezen als Eigenaar. 
> [!IMPORTANT]
>Voor Azure AD-gebruikers is de uitzondering op deze regel dat als het apparaat is samengevoegd met Azure AD via Autopilot of bulksgewijs Azure AD-inschrijving, dat gebruikmaakt van een niet-echte gebruiker. In dit geval wordt de eerste AAD-gebruiker die zich bij het apparaat heeft aanmelden mogelijk niet automatisch eigenaar van het apparaat, tenzij aan die gebruiker de rol 'globale beheerder' of 'apparaatbeheerder' is toegewezen in Azure Portal. Zie de opmerking hieronder voor meer informatie.  

  * Wanneer een gebruiker wordt gepromoveerd als eigenaar van de Instellingen UX door een andere eigenaar op het apparaat.
  * Als de eigenaar van het apparaat niet meer beschikbaar is (het bedrijf verlaat) en het apparaat lid is van Azure AD, kan de tenantbeheerder de eigenaar van het apparaat wijzigen in een nieuwe gebruiker in Azure Portal. Globale beheerders en apparaatbeheerders van een Azure AD-tenant worden impliciet aangemeld als eigenaren op het apparaat zonder dat een van de vorige stappen is vereist.  

 IT-beheerders kunnen beheren tot welke apps toegang kunnen krijgen via [privacybeleid.](/windows/client-management/mdm/policy-csp-privacy) 

> [!NOTE]
> Zie de documentatie 'Lokale beheerder toewijzen' (maar lees [](/azure/active-directory/devices/assign-local-admin) 'lokale beheerder' als 'apparaateigenaar' omdat de beheerder niet bestaat op HoloLens) voor meer informatie over wie eigenaar van het apparaat wordt gemaakt op een apparaat dat is HoloLens).