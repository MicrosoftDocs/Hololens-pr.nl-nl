---
title: Certificaatbeheerder
description: Meer informatie over het handmatig installeren, beheren en verwijderen van certificaten op HoloLens 2 mixed reality apparaten.
author: evmill
ms.author: v-evmill
manager: yannisle
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/13/2020
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: f9dcf98cbd200ac54cd786648fdfe286bff1aa00
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/25/2021
ms.locfileid: "111377804"
---
# <a name="certificate-manager"></a>Certificaatbeheerder

- Verbeterde hulpprogramma's voor controle, diagnose en validatie voor apparaatbeveiliging en -naleving via de nieuwe Certificaatbeheerder. Met deze mogelijkheid kunt u uw certificaten op schaal implementeren, oplossen en valideren in commerciële omgevingen.

In Windows Holographic, versie 20H2, voegen we certificaatbeheer toe aan de app HoloLens 2 Instellingen. Ga naar **Instellingen > Beveiliging & bijwerken > certificaten.** Deze functie biedt een eenvoudige en gebruiksvriendelijke manier om certificaten op uw apparaat weer te geven, te installeren en te verwijderen. Met de nieuwe Certificate Manager hebben beheerders en gebruikers nu verbeterde hulpprogramma's voor controle, diagnose en validatie om ervoor te zorgen dat apparaten veilig en compatibel blijven. 

-   **Controle:** Mogelijkheid om te valideren dat een certificaat correct is geïmplementeerd of om te bevestigen dat het op de juiste wijze is verwijderd. 
-   **Diagnose:** Wanneer er problemen optreden, bespaart het valideren of de juiste certificaten op het apparaat bestaan tijd en helpt het bij het oplossen van problemen. 
-   **Validatie:** Controleren of een certificaat het beoogde doel heeft en functioneel is, kan aanzienlijke tijd besparen, met name in commerciële omgevingen voordat certificaten op grotere schaal worden geïmplementeerd.

Als u snel een specifiek certificaat in de lijst wilt vinden, zijn er opties om te sorteren op naam, winkel of vervaldatum. Gebruikers kunnen ook rechtstreeks naar een certificaat zoeken. Als u afzonderlijke certificaateigenschappen wilt weergeven, selecteert u het certificaat en klikt u op **Info.** 

Certificaatinstallatie ondersteunt momenteel CER- en CRT-bestanden. Apparaateigenaren kunnen certificaten installeren op de lokale computer en de huidige gebruiker;  alle andere gebruikers kunnen alleen installeren in Huidige gebruiker. Gebruikers kunnen alleen certificaten verwijderen die rechtstreeks vanuit de gebruikersinterface Instellingen zijn geïnstalleerd. Als een certificaat op een andere manier is geïnstalleerd, moet het ook door hetzelfde mechanisme worden verwijderd.

## <a name="to-install-a-certificate"></a>Een certificaat installeren: 

1.  Verbind uw HoloLens 2 met een pc.
1.  Plaats het certificaatbestand dat u wilt installeren op een locatie op HoloLens 2.
1.  **Navigeer naar Instellingen App > Update & Security > Certificates** en selecteer Install a certificate.
1.  Klik **op Bestand importeren** en navigeer naar de locatie waar u het certificaat hebt opgeslagen.
1.  Selecteer **Winkellocatie.**
1.  Selecteer **Certificaatopslag.**
1.  Klik op **Installeren**.

Het certificaat moet nu op het apparaat zijn geïnstalleerd.

## <a name="to-remove-a-certificate"></a>Een certificaat verwijderen: 
>[!WARNING]
> Hoewel u door MDM geïmplementeerde certificaten kunt weergeven in Certificate Manager, kunt u ze niet verwijderen in Certificate Manager. U moet ze verwijderen via MDM.
1. **Navigeer naar Instellingen-app > Bijwerken en beveiliging > certificaten.**
1. Zoek het certificaat op naam in het zoekvak.
1. Selecteer het certificaat.
1. Klik op **Verwijderen**
1. Selecteer **Ja wanneer** u om bevestiging wordt gevraagd.



![Certificaatviewer in de app Instellingen onder Certificaten](images/certificate-viewer-device.jpg)

![Afbeelding waarin wordt getoond hoe u de gebruikersinterface van het certificaat gebruikt om een certificaat te installeren in Instellingen.](images/certificate-device-install.jpg)
