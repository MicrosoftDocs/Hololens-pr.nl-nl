---
title: Uw HoloLens 2
description: Leer hoe u uw HoloLens 2 voor de eerste keer via Wi-Fi-netwerk in te stellen met een Microsoft-account (MSA) of Azure Active Directory (AAD)-account.
ms.assetid: 507305f4-e85a-47c5-a055-a3400ae8a10e
ms.date: 6/09/2021
keywords: hololens
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 2
ms.openlocfilehash: 0d087037e94bcaed2cd79d9cff77ed3039919a09
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923714"
---
# <a name="set-up-your-hololens-2"></a>Uw HoloLens 2

De eerste keer dat u uw HoloLens in zet, wordt u begeleid bij het instellen van uw apparaat, het aanmelden met een gebruikersaccount en het naar uw ogen eren van de HoloLens.  In deze sectie wordt de HoloLens 2 de eerste installatie beloopt.

In de volgende sectie leert u hoe u met HoloLens werkt en hoe u met hologrammen communiceert. Als u verder wilt gaan met dat artikel, gaat [u naar HoloLens 2](hololens2-basic-usage.md).

## <a name="before-you-start"></a>Voordat u begint

Voordat u aan de slag gaat, moet u ervoor zorgen dat het volgende beschikbaar is:

**Een netwerkverbinding.** U moet uw HoloLens verbinden met een netwerk om dit in te stellen. Met HoloLens 2 kunt u verbinding maken met Wi-Fi of met behulp van ethernet (u hebt een USB-C-naar-Ethernet-adapter nodig). De eerste keer dat u verbinding maakt, hebt u een open of met een wachtwoord beveiligd netwerk nodig waarvoor u niet hoeft te navigeren naar een website of certificaten hoeft te gebruiken om verbinding te maken. [Meer informatie over de websites die HoloLens gebruikt.](hololens-offline.md)

**Een Microsoft-account**. U moet zich ook aanmelden bij HoloLens met een Microsoft-account (of met uw werkaccount, als uw organisatie eigenaar is van het apparaat). Als u nog geen Microsoft-account hebt, gaat u [naar account.microsoft.com](https://account.microsoft.com) en stelt u er gratis een in.

**Een veilige, goed belichte ruimte zonder trippingsgevaren.** [Informatie over status en veiligheid.](https://go.microsoft.com/fwlink/p/?LinkId=746661)

**De optionele comfortaccessoires** die bij uw HoloLens zijn verkrijgbaar, zodat u de meest geschikte keuze krijgt. [Meer informatie over aanpassen en comfort.](hololens2-setup.md#adjust-fit)

## <a name="set-up-windows"></a>Windows installeren

De eerste keer dat u uw HoloLens 2, is het instellen van Windows Holographic.  Wanneer u uw HoloLens start, hoort u muziek en ziet u een Windows-logo.

![Eerste scherm tijdens de eerste keer opstarten](images/01-magic-moment.png)

HoloLens 2 doorloop de volgende stappen:

1. Selecteer uw taal.

    ![Taal selecteren](images/04-language.png)

1. Kies uw regio.

    ![Regio selecteren](images/05-region.png)

1. Kalibreer HoloLens naar uw ogen.  Als u ervoor kiest om kalibratie over te slaan, wordt u de volgende keer dat u zich aanmeldt gevraagd. 

    1. Eerst past u uw visor aan.
    
        ![Scherm voor selectie van kalibratie](images/06-et-corners.png)

    2. Als u wilt kalibreren, bekijkt u een set doelen (gems genoemd). Het is prima als u tijdens de kalibratie knippert of uw ogen sluit, maar probeer niet naar andere objecten in de ruimte of fysieke ruimte te staren. HoloLens gebruikt dit proces om meer te weten te komen over de positie van uw oog, zodat uw holografische wereld beter kan worden weergegeven. 

        ![Voor uw ogen aanpassen](images/07-adjust-eyes.png)

        Na kalibratie worden hologrammen correct weergegeven, zelfs wanneer de visor op uw hoofd verschuift. Kalibratiegegevens worden lokaal op het apparaat opgeslagen en zijn niet gekoppeld aan accountgegevens. Zie Kalibratiegegevens en beveiliging [voor meer informatie.](hololens-calibration.md#calibration-data-and-security)

        ![Kalibratie is voltooid](images/calibration-complete.png)

1. Verbinding maken met internet (selecteer Wi-Fi of uw ethernetverbinding).

     HoloLens stelt uw tijdzone automatisch in op basis van gegevens die zijn verkregen van Wi-Fi netwerk. Nadat de installatie is klaar, kunt u de tijdzone wijzigen met behulp van de app Instellingen.

    ![Verbinding maken met Wi-Fi](images/11-network.png)

    > [!NOTE] 
    > Als u verder bent dan de Wi-Fi-stap en later moet overschakelen naar een ander netwerk  terwijl u nog in de installatie bent, kunt u tegelijkertijd op de knoppen **Volume** omlaag en Aan/uit drukken om terug te keren naar deze stap als u een versie van het besturingssysteem van oktober 2019 of hoger gebruikt. Voor eerdere versies moet u [](hololens-recovery.md) het apparaat mogelijk opnieuw instellen of opnieuw opstarten op een locatie waar het Wi-Fi-netwerk niet beschikbaar is om te voorkomen dat het automatisch verbinding maakt.
    > 
    > Houd er ook rekening mee dat er tijdens het instellen van HoloLens een time-out voor referenties van twee minuten is. De gebruikersnaam/het wachtwoord moet binnen twee minuten worden ingevoerd, anders wordt het veld gebruikersnaam automatisch geweerd.

1. HoloLens 2 zoekt en past een Autopilot-profiel toe als er een bestaat. Er is geen actie nodig op dit scherm.
 
    ![Zoeken in Autopilot-profielen](images/autopilot-profile-search.png) 

1. Klik **op Accepteren** in het licentiescherm.

    ![Windows-licentieovereenkomst](images/windows-license-agreement.png)

1. Meld u aan bij uw gebruikersaccount. U kiest tussen **Mijn werk** of school is eigenaar en ik ben **eigenaar.**

    - Wanneer u Mijn **werk of school is eigenaar kiest,** meldt u zich aan met een Azure AD-account. Als uw organisatie gebruikmaakt Azure AD Premium automatische MDM-inschrijving heeft geconfigureerd, wordt HoloLens automatisch ingeschreven bij MDM. Als uw organisatie geen gebruik maakt Azure AD Premium, is automatische MDM-inschrijving niet beschikbaar. In dat geval moet u HoloLens handmatig inschrijven [bij apparaatbeheer.](hololens-enroll-mdm.md#different-ways-to-enroll)

        1. Voer de gegevens van uw organisatieaccount in.
        1. Accepteer de privacyverklaring en de gebruikslicentieovereenkomst.
        1. Meld u aan met uw Azure AD-referenties. Dit kan worden omgeleid naar de aanmeldingspagina van uw organisatie.
        1. Ga door met het instellen van het apparaat.

    - Wanneer u I **own it kiest,** kunt u zich aanmelden met een Microsoft-account. Nadat de installatie is voltooid, kunt u [HoloLens handmatig inschrijven bij apparaatbeheer.](hololens-enroll-mdm.md#different-ways-to-enroll)

        1. Voer uw Microsoft-account in.
        2. Voer uw wachtwoord in. Als uw Microsoft-account verificatie [in twee stappen (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/)vereist, voltooit u het verificatieproces.

    ![Gebruiker instellen](images/13-device-owner.png)

1. Stel Iris-aanmelding in door Volgende **te selecteren.** U doormaakt een vergelijkbare ervaring als de kalibratie van het oog. Selecteer **Voltooid** wanneer de scan is voltooid. U kunt ook Overslaan selecteren **om** deze stap over te slaan.
    
    ![Iris-instelling ](images/setup-iris.png) ![ Voltooiing van de Iris-installatie](images/iris-setup-complete.png) 
     
  
1. U gaat een pincode instellen om u aan te melden bij het apparaat. Deze pincode is apparaatsyte specifiek. 

    ![Installatie Windows Hello](images/setup-windows-hello.png)

    ![Pincode Windows Hello instellen](images/windows-hello-pin.png)

    ![Windows Hello setup is geslaagd](images/windows-hello-successful.png) 
    
1. Selecteer of u spraak wilt inschakelen op HoloLens 2.

    ![Cortana inschakelen](images/22-do-more-with-voice.png)

1. Selecteer of u de locatie op de HoloLens 2.
    
    ![Locatieservices inschakelen](images/setup-location-services.png)

1. Selecteer uw telemetrieniveau. Schakel desgewenst Optionele telemetrie in. Deze informatie helpt het technische team van HoloLens echt.

     ![Telemetrieniveau](images/24-telemetry.png)

1. Meer informatie over het gebruik van het begingebaar op HoloLens 2.

     ![Meer informatie over het gebruik van het beginbewegingen, afbeelding 1](images/26-01-startmenu-learning.png)

     ![Meer informatie over het gebruik van het beginbewegingen, afbeelding 2](images/26-02-startmenu-learning.png)

Gefeliciteerd  De installatie is voltooid en u kunt HoloLens gaan gebruiken.

## <a name="next-steps"></a>Volgende stappen

1. Ga direct aan de slag met Mixed Reality en navigeer naar Windows 10 op uw HoloLens. Bekijk de **tips-app** voor praktische zelfstudies voor handinteracties. Gebruik de startbewegingen om naar Start te gaan of zeg 'Ga naar start' en selecteer Tips.

1. Klik hieronder om door te gaan met het lezen van HoloLens 2.

> [!div class="nextstepaction"]
> [Kennismaken met HoloLens 2](hololens2-basic-usage.md)
