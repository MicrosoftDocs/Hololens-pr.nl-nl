---
title: Uw HoloLens delen met meerdere personen
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
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032910"
---
# <a name="share-your-hololens-with-multiple-people"></a>Uw HoloLens delen met meerdere personen

## <a name="overview"></a>Overzicht
Bedrijven investeren vaak in veel gedeelde HoloLens apparaten. Hoe u HoloLens is flexibel over de hele wereld, afhankelijk van uw afzonderlijke vereisten. Hier is een voorbeeld van een aantal ervaringen voor meerdere gebruikers: 

- Apparaten waarvoor kosten in rekening worden gebracht en waarvoor Dynamics 365 Guides zijn ingeschakeld, en waarmee uw werknemers de Instellingen-app kunnen openen om wijzigingen aan te brengen in de Wi-Fi die nodig zijn, maar het beleid voor zichtbaarheid van Page Instellingen is ingeschakeld om het aantal pagina's te beperken dat beschikbaar is in de Instellingen-app.
- Apparaten die zijn Remote Assist en uw Line-Of-Business-app die worden verhuurd aan andere bedrijven. Deze apparaten hebben kiosken die alleen uw app en Remote Assist. WDAC wordt gebruikt om te zorgen dat de Instellingen-app niet Microsoft Edge start. Opgenomen in de verhuur is een USB-C-accupakket om de apparaten volledig op te laden voor meerdere ploegen.
- Al uw apparaten zijn ingesteld voor Autopilot en downloaden al uw bedrijfsapps. U hebt een aantal verschillende Kiosk-profielen ingesteld voor verschillende Azure AD-groepen. Elke gebruiker meldt zich aan bij HoloLens FIDO2-sleutels en meldt zich aan bij zijn eigen Azure AD-account en krijgt een op maat gemaakte ervaring te zien.



## <a name="share-with-multiple-people-each-using-their-own-account"></a>Delen met meerdere personen, elk met hun eigen account

**Vereiste:** op HoloLens apparaat moet Windows 10 versie 1803 of hoger worden uitgevoerd.  HoloLens (eerste generatie) moet ook worden bijgewerkt naar [Windows Holographic for Business](hololens-upgrade-enterprise.md).

Wanneer ze hun eigen Azure AD Azure Active Directory accounts gebruiken, kunnen meerdere gebruikers elk hun eigen gebruikersinstellingen en gebruikersgegevens op het apparaat bewaren.

Als u ervoor wilt zorgen dat meerdere personen hun eigen accounts op uw HoloLens, volgt u deze stappen om deze te configureren:

1. Zorg ervoor dat op het apparaat Windows 10 versie 1803 of hoger wordt uitgevoerd.
   > [!IMPORTANT]
   > Als u een HoloLens (1e generatie) gebruikt, moet u het [apparaat upgraden naar Windows Holographic for Business.](hololens1-upgrade-enterprise.md)
1. Wanneer u het apparaat in stelt, selecteert u Mijn werk of **school is** eigenaar en meldt u zich aan met een Azure AD-account.
1. Nadat u de installatie hebt voltooien, moet u ervoor zorgen dat de accountinstellingen (**Instellingen**  >  **Accounts**) **Andere gebruikers bevat.**

Als u HoloLens, volgt elke gebruiker deze stappen:

1. Als een andere gebruiker het apparaat heeft gebruikt, kiest u een van de volgende opties:
   - Druk eenmaal op de aan/uit-knop om naar de stand-by te gaan en druk vervolgens nogmaals op de aan/uit-knop om terug te keren naar het vergrendelingsscherm
   - HoloLens 2 gebruikers kunnen de tegel Gebruiker selecteren in de Startmenu de huidige gebruiker af te melden.

1. Gebruik de referenties van uw Azure AD-account om u aan te melden bij het apparaat.  
    Als het de eerste keer is dat u het [](hololens-calibration.md) apparaat gebruikt, moet HoloLens naar uw eigen ogen kalibreren.

Als u een lijst met de apparaatgebruikers wilt zien of als u een gebruiker van het apparaat wilt verwijderen, gaat u **naar Instellingen**  >  **Accounts**  >  **Andere gebruikers.**

## <a name="share-with-multiple-people-all-using-the-same-account"></a>Delen met meerdere personen, allemaal met hetzelfde account

Meerdere gebruikers kunnen ook een HoloLens delen terwijl ze één gebruikersaccount gebruiken.

**Wanneer HoloLens 2** nieuwe gebruiker het apparaat de eerste keer op het hoofd plaatst (terwijl hetzelfde account blijft aangemeld), wordt de nieuwe gebruiker gevraagd om de weergave-ervaring snel te kalibreren en aan te persoonlijke voorkeur. Het apparaat kan de kalibratiegegevens opslaan zodat het apparaat in de toekomst automatisch de kwaliteit en het comfort van de kijkervaring van elke gebruiker kan optimaliseren. De gebruikers hoeven het apparaat niet opnieuw te kalibreren.

**Op HoloLens (eerste generatie)** moeten gebruikers die een account delen, vragen om opnieuw te worden gecalibreerd in de Instellingen app.  Lees meer over [kalibratie](hololens-calibration.md).