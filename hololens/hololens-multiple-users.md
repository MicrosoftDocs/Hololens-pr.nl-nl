---
title: Uw HoloLens delen met meerdere personen
description: U kunt configureren HoloLens worden gedeeld door meerdere Azure Active Directory-accounts of door meerdere gebruikers die één account gebruiken.
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
ms.openlocfilehash: 821ef2d17531226177e508b1428af82012c16406e9fbce3ed1a5617c767adfe8
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/05/2021
ms.locfileid: "115663069"
---
# <a name="share-your-hololens-with-multiple-people"></a>Uw HoloLens delen met meerdere personen

Het is gebruikelijk om één apparaat HoloLens veel mensen te delen of om veel mensen een set apparaten HoloLens laten delen.  In dit artikel worden de verschillende manieren beschreven waarop u een apparaat kunt delen.

## <a name="share-with-multiple-people-each-using-their-own-account"></a>Delen met meerdere personen, elk met hun eigen account

**Vereiste:** op HoloLens apparaat moet Windows 10 versie 1803 of hoger worden uitgevoerd.  HoloLens (eerste generatie) moet ook worden geüpgraded [naar Windows Holographic for Business](hololens-upgrade-enterprise.md).

Wanneer ze hun eigen azure Azure Active Directory accounts (Azure AD) gebruiken, kunnen meerdere gebruikers elk hun eigen gebruikersinstellingen en gebruikersgegevens op het apparaat behouden.

Volg deze stappen om deze te configureren om ervoor te zorgen dat meerdere personen hun eigen accounts op uw HoloLens gebruiken:

1. Zorg ervoor dat op het apparaat Windows 10 versie 1803 of hoger wordt uitgevoerd.
   > [!IMPORTANT]
   > Als u een apparaat met HoloLens (1e generatie) gebruikt, moet u het [apparaat upgraden naar Windows Holographic for Business](hololens1-upgrade-enterprise.md).
1. Wanneer u het apparaat in stelt, selecteert u **Mijn werk** of school is eigenaar en meldt u zich aan met een Azure AD-account.
1. Nadat u klaar bent met de installatie, moet u ervoor zorgen dat de accountinstellingen **(Instellingen**  >  **Accounts)** **andere gebruikers bevat.**

Als u HoloLens, volgt elke gebruiker deze stappen:

1. Als een andere gebruiker het apparaat heeft gebruikt, doet u het volgende:
   - Druk eenmaal op de aan/uit-knop om naar stand-by te gaan en druk vervolgens nogmaals op de aan/uit-knop om terug te keren naar het vergrendelingsscherm
   - HoloLens 2 gebruikers kunnen de tegel Gebruiker selecteren in de Startmenu de huidige gebruiker af te melden.

1. Gebruik de referenties van uw Azure AD-account om u aan te melden bij het apparaat.  
    Als dit de eerste keer is dat u [](hololens-calibration.md) het apparaat gebruikt, moet HoloLens aan uw eigen ogen kalibreren.

Als u een lijst met de apparaatgebruikers wilt bekijken of een gebruiker van het apparaat wilt verwijderen, gaat u **naar Instellingen**  >  **Accounts**  >  **Andere gebruikers.**

## <a name="share-with-multiple-people-all-using-the-same-account"></a>Delen met meerdere personen, allemaal met hetzelfde account

Meerdere gebruikers kunnen ook een HoloLens delen met behulp van één gebruikersaccount.

**Op HoloLens 2** wordt de nieuwe gebruiker gevraagd om snel te kalibreren en de weergave te personaliseren wanneer een nieuwe gebruiker het apparaat voor het eerst op zijn hoofd plaatst (terwijl hetzelfde account blijft aangemeld). Het apparaat kan de kalibratiegegevens opslaan, zodat het apparaat in de toekomst automatisch de kwaliteit en het comfort van de weergave-ervaring van elke gebruiker kan optimaliseren. De gebruikers hoeven het apparaat niet opnieuw te kalibreren.

**Op HoloLens (eerste generatie)** moeten gebruikers die een account delen, vragen om opnieuw te worden gecalibreerd in de Instellingen app.  Lees meer over [kalibratie](hololens-calibration.md).
