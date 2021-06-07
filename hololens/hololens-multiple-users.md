---
title: Uw HoloLens delen met meerdere personen
description: U kunt HoloLens configureren om te worden gedeeld door meerdere Azure Active Directory-accounts of door meerdere gebruikers die één account gebruiken.
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 09/16/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 39de72bb704ff500b0262f2268d003a08d520eb2
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/19/2021
ms.locfileid: "111377883"
---
# <a name="share-your-hololens-with-multiple-people"></a>Uw HoloLens delen met meerdere personen

Het is gebruikelijk om één HoloLens te delen met veel mensen of om veel mensen een set HoloLens-apparaten te laten delen.  In dit artikel worden de verschillende manieren beschreven waarop u een apparaat kunt delen.

## <a name="share-with-multiple-people-each-using-their-own-account"></a>Delen met meerdere personen, elk met hun eigen account

**Vereiste:** op het HoloLens-apparaat moet Windows 10 versie 1803 of hoger worden uitgevoerd.  HoloLens (1e generatie) moet ook worden bijgewerkt naar [Windows Holographic for Business.](hololens-upgrade-enterprise.md)

Wanneer ze hun eigen Azure AD Azure Active Directory accounts gebruiken, kunnen meerdere gebruikers elk hun eigen gebruikersinstellingen en gebruikersgegevens op het apparaat bewaren.

Volg deze stappen om deze te configureren om ervoor te zorgen dat meerdere personen hun eigen accounts op uw HoloLens kunnen gebruiken:

1. Zorg ervoor dat op het apparaat Windows 10 versie 1803 of hoger wordt uitgevoerd.
   > [!IMPORTANT]
   > Als u een HoloLens-apparaat (1e generatie) gebruikt, moet u het [apparaat upgraden naar Windows Holographic for Business](hololens1-upgrade-enterprise.md).
1. Wanneer u het apparaat in stelt, selecteert u Mijn werk of **school is** eigenaar en meldt u zich aan met een Azure AD-account.
1. Nadat u de installatie hebt voltooien,moet u ervoor zorgen dat de accountinstellingen  >  **(Instellingenaccounts)** **Andere gebruikers bevat.**

Als u HoloLens wilt gebruiken, volgt elke gebruiker deze stappen:

1. Als een andere gebruiker het apparaat heeft gebruikt, doet u het volgende:
   - Druk eenmaal op de aan/uit-knop om naar de stand-by te gaan en druk vervolgens nogmaals op de aan/uit-knop om terug te keren naar het vergrendelingsscherm
   - HoloLens 2 gebruikers kunnen de tegel Gebruiker selecteren in de Startmenu de huidige gebruiker af te melden.

1. Gebruik de referenties van uw Azure AD-account om u aan te melden bij het apparaat.  
    Als dit de eerste keer is dat u [](hololens-calibration.md) het apparaat gebruikt, moet u HoloLens naar uw eigen ogen kalibreren.

Als u een lijst met de apparaatgebruikers wilt zien of als u een gebruiker van het apparaat wilt verwijderen, gaat u naar  >  **InstellingenAccounts**  >  **Andere gebruikers.**

## <a name="share-with-multiple-people-all-using-the-same-account"></a>Delen met meerdere personen, allemaal met hetzelfde account

Meerdere gebruikers kunnen ook een HoloLens-apparaat delen terwijl ze één gebruikersaccount gebruiken.

**Wanneer HoloLens 2** nieuwe gebruiker het apparaat de eerste keer op het hoofd plaatst (terwijl hetzelfde account blijft aangemeld), wordt de nieuwe gebruiker gevraagd om de weergave-ervaring snel te kalibreren en aan te persoonlijke voorkeur. Het apparaat kan de kalibratiegegevens opslaan zodat het apparaat in de toekomst automatisch de kwaliteit en het comfort van de kijkervaring van elke gebruiker kan optimaliseren. De gebruikers hoeven het apparaat niet opnieuw te kalibreren.

**Op HoloLens (1e generatie)** moeten gebruikers die een account delen, vragen om opnieuw te worden gecalibreerd in de app Instellingen.  Lees meer over [kalibratie](hololens-calibration.md).
