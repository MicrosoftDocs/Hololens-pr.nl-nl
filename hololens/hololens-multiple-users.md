---
title: Uw gegevens HoloLens met meerdere personen
description: U kunt configureren HoloLens worden gedeeld door meerdere Azure Active Directory-accounts of door meerdere gebruikers die één account gebruiken.
ms.prod: hololens
ms.sitesec: library
author: qianw211
ms.author: v-qianwen
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/3/2021
ms.reviewer: ''
manager: sekerawa
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: e3acd2665e93e44bce2c5dad467c825dc768bfed
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427476"
---
# <a name="share-your-hololens-with-multiple-people"></a>Uw gegevens HoloLens met meerdere personen

## <a name="overview"></a>Overzicht
Bedrijven investeren vaak in veel gedeelde HoloLens apparaten. Hoe u HoloLens is flexibel over de hele wereld, afhankelijk van uw afzonderlijke vereisten. Hier is een voorbeeld van een aantal ervaringen voor meerdere gebruikers: 

- Apparaten waarvoor kosten in rekening worden gebracht en waarvoor Dynamics 365 Guides zijn ingeschakeld en waarmee uw werknemers de Instellingen-app kunnen openen om wijzigingen aan te brengen in de benodigde Wi-Fi, maar het beleid voor zichtbaarheid van Pagina Instellingen is ingeschakeld om het aantal pagina's dat beschikbaar is in de Instellingen-app te beperken.
- Apparaten die voor Remote Assist zijn en uw Line-Of-Business-app die worden verhuurd aan andere bedrijven. Deze apparaten hebben kiosken die alleen uw app en Remote Assist. WDAC wordt gebruikt om ervoor te zorgen dat de Instellingen-app Microsoft Edge start. Opgenomen in de verhuur is een USB-C-accupakket om de apparaten volledig op te laden via meerdere ploegendiensten.
- Al uw apparaten zijn ingesteld voor Autopilot en downloaden al uw bedrijfsapps. U hebt een aantal verschillende Kiosk-profielen ingesteld, gericht op verschillende Azure AD-groepen. Elke gebruiker meldt zich aan bij HoloLens FIDO2-sleutels en meldt zich aan bij zijn eigen Azure AD-account en krijgt een op maat gemaakte ervaring te zien.



## <a name="share-with-multiple-people-each-using-their-own-account"></a>Delen met meerdere personen, elk met een eigen account

**Vereiste:** op HoloLens apparaat moet Windows 10 versie 1803 of hoger worden uitgevoerd.  HoloLens (eerste generatie) moet ook worden geüpgraded [naar Windows Holographic for Business](hololens-upgrade-enterprise.md).

Wanneer ze hun eigen azure Azure Active Directory accounts (Azure AD) gebruiken, kunnen meerdere gebruikers elk hun eigen gebruikersinstellingen en gebruikersgegevens op het apparaat bewaren.

Volg deze stappen om deze te configureren om ervoor te zorgen dat meerdere personen hun eigen accounts op uw HoloLens gebruiken:

1. Zorg ervoor dat op het apparaat Windows 10 versie 1803 of hoger wordt uitgevoerd.
   > [!IMPORTANT]
   > Als u een apparaat met HoloLens (1e generatie) gebruikt, moet u het [apparaat upgraden naar Windows Holographic for Business](hololens1-upgrade-enterprise.md).
1. Wanneer u het apparaat in stelt, selecteert u **Mijn werk** of school is eigenaar en meldt u zich aan met een Azure AD-account.
1. Nadat u klaar bent met de installatie, moet u ervoor zorgen dat de accountinstellingen **(Instellingen**  >  **Accounts)** **andere gebruikers bevat.**

Als u HoloLens, volgt elke gebruiker deze stappen:

1. Als een andere gebruiker het apparaat heeft gebruikt, kiest u een van de volgende opties:
   - Druk eenmaal op de aan/uit-knop om naar stand-by te gaan en druk vervolgens nogmaals op de aan/uit-knop om terug te keren naar het vergrendelingsscherm
   - HoloLens 2 gebruikers kunnen de tegel Gebruiker selecteren in de Startmenu de huidige gebruiker af te melden.

1. Gebruik de referenties van uw Azure AD-account om u aan te melden bij het apparaat.  
    Als het de eerste keer is dat u het [](hololens-calibration.md) apparaat gebruikt, moet u het HoloLens uw eigen ogen kalibreren.

Als u een lijst met de apparaatgebruikers wilt zien of als u een gebruiker van het apparaat wilt verwijderen, gaat u **naar Instellingen**  >  **Accounts**  >  **Andere gebruikers.**

## <a name="share-with-multiple-people-all-using-the-same-account"></a>Delen met meerdere personen, allemaal met hetzelfde account

Meerdere gebruikers kunnen ook een HoloLens delen met behulp van één gebruikersaccount.

**Op HoloLens 2** wordt de nieuwe gebruiker gevraagd om snel te kalibreren en de weergave te personaliseren wanneer een nieuwe gebruiker het apparaat voor het eerst op zijn hoofd plaatst (terwijl hetzelfde account blijft aangemeld). Het apparaat kan de kalibratiegegevens opslaan, zodat het apparaat in de toekomst automatisch de kwaliteit en het comfort van de weergave-ervaring van elke gebruiker kan optimaliseren. De gebruikers hoeven het apparaat niet opnieuw te kalibreren.

**Op HoloLens (eerste generatie)** moeten gebruikers die een account delen, vragen om opnieuw te worden gecalibreerd in de Instellingen app.  Lees meer over [kalibratie](hololens-calibration.md).