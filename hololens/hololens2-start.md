---
title: Uw HoloLens 2
description: Meer informatie over het instellen van uw HoloLens 2 voor de eerste keer via Wi-Fi-netwerk met een Microsoft-account (MSA) of een Azure Active Directory -account (AAD).
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
ms.openlocfilehash: a5c0e28eff9bb71135309ec5e484fc5b88f02d08
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/12/2021
ms.locfileid: "113636572"
---
# <a name="set-up-your-hololens-2"></a>Uw HoloLens 2

De eerste keer dat u uw HoloLens in zet, wordt u begeleid bij het instellen van uw apparaat, het aanmelden met een gebruikersaccount en het HoloLens uw ogen.  In deze sectie wordt de HoloLens 2 eerste installatie-ervaring.

In de volgende sectie leert u hoe u kunt werken met HoloLens en communiceren met hologrammen. Als u verder wilt gaan met dat artikel, gaat [u naar HoloLens 2](hololens2-basic-usage.md).

## <a name="before-you-start"></a>Voordat u begint

Voordat u aan de slag gaat, moet u ervoor zorgen dat het volgende beschikbaar is:

**Een netwerkverbinding.** U moet uw netwerkverbinding HoloLens met een netwerk om dit in te stellen. Met HoloLens 2 kunt u verbinding maken met Wi-Fi of met behulp van ethernet (u hebt een USB-C-naar-Ethernet-adapter nodig). De eerste keer dat u verbinding maakt, hebt u een open of met een wachtwoord beveiligd netwerk nodig waarvoor u niet naar een website hoeft te navigeren of certificaten hoeft te gebruiken om verbinding te maken. [Meer informatie over de websites die HoloLens gebruikt.](hololens-offline.md)

**Een Microsoft-account**. U moet zich ook aanmelden bij HoloLens met een Microsoft-account (of met uw werkaccount, als uw organisatie eigenaar is van het apparaat). Als u nog geen Microsoft-account, gaat u naar [account.microsoft.com](https://account.microsoft.com) en stelt u er gratis een in.

**Een veilige, goed belichte ruimte zonder tripping-risico's.** [Informatie over status en veiligheid.](https://go.microsoft.com/fwlink/p/?LinkId=746661)

**De optionele comfortaccessoires** die bij uw HoloLens, om u te helpen de meest geschikte keuze te maken. [Meer informatie over passend en comfort.](hololens2-setup.md#adjust-fit)

## <a name="set-up-windows"></a>Windows installeren

De eerste keer dat u uw HoloLens 2 start, is uw eerste taak het instellen van Windows Holographic.  Wanneer u uw HoloLens, hoort u muziek en ziet u een Windows logo.

![Eerste scherm tijdens de eerste keer opstarten](images/01-magic-moment.png)

U ziet dat er een vogeltje rondvriest.

![Toerduifje](images/hummingbird-1.png)

Volg deze met uw hand.

![Demingbird-100000000000000](images/hummingbird-2.png)

HoloLens 2 doorloop de volgende stappen:

1. Selecteer uw taal.

    ![Taal selecteren](images/04-language.png)

1. Kies uw regio.

    ![Regio selecteren](images/05-region.png)

1. Kalibreer HoloLens uw ogen.  Als u ervoor kiest om de kalibratie over te slaan, wordt u de volgende keer dat u zich aanmeldt gevraagd. 

    1. Eerst past u uw visor aan.
    
        ![Scherm voor selectie van kalibratie](images/06-et-corners.png)

    2. Als u wilt kalibreren, bekijkt u een set doelen (gems genoemd). Het is prima als u tijdens de kalibratie knippert of uw ogen sluit, maar probeer niet te staren naar andere objecten in de ruimte of fysieke ruimte. HoloLens dit proces gebruikt om meer te weten te komen over uw oogpositie, zodat uw holografische wereld beter kan worden weergegeven. 

        ![Aanpassen voor uw ogen](images/07-adjust-eyes.png)

        Na de kalibratie worden hologrammen correct weergegeven, zelfs wanneer het visor op uw hoofd verschuift. Kalibratie-informatie wordt lokaal op het apparaat opgeslagen en is niet gekoppeld aan accountgegevens. Zie Gegevens en beveiliging [voor meer informatie.](hololens-calibration.md#calibration-data-and-security)

        ![De kalibratie is voltooid](images/calibration-complete.png)

1. Verbinding maken verbinding maken met internet (selecteer Wi-Fi of uw ethernetverbinding).

     HoloLens wordt uw tijdzone automatisch op basis van gegevens die zijn verkregen van het Wi-Fi netwerk. Nadat de installatie is voltooien, kunt u de tijdzone wijzigen met behulp van de Instellingen app.

    ![Verbinding maken met Wi-Fi](images/11-network.png)

    > [!NOTE] 
    > Als u verder bent dan de Wi-Fi-stap en u later moet overschakelen naar een ander  netwerk terwijl u nog in de installatie bent, kunt u tegelijkertijd op de knoppen **Volume** omlaag en Aan/uit drukken om terug te keren naar deze stap als u een versie van het besturingssysteem van oktober 2019 of hoger gebruikt. Voor eerdere versies moet u [](hololens-recovery.md) het apparaat mogelijk opnieuw instellen of opnieuw opstarten op een locatie waar het Wi-Fi-netwerk niet beschikbaar is om te voorkomen dat het automatisch verbinding maakt.
    > 
    > Houd er ook rekening mee HoloLens tijdens het instellen van de referenties een time-out van twee minuten is. De gebruikersnaam en het wachtwoord moeten binnen twee minuten worden ingevoerd, anders wordt het veld gebruikersnaam automatisch geweerd.

1. HoloLens 2 zoekt en past een Autopilot-profiel toe als er een bestaat. Er is geen actie nodig op dit scherm.
 
    ![Zoeken in Autopilot-profielen](images/autopilot-profile-search.png) 

1. Klik **op Accepteren** in het licentiescherm.

    ![Windows-licentieovereenkomst](images/windows-license-agreement.png)

1. Meld u aan bij uw gebruikersaccount. U kiest tussen Mijn werk of **school is eigenaar en** ik ben **eigenaar.**

    ![Gebruiker instellen](images/13-device-owner.png)
    - Wanneer u Mijn **werk of school is eigenaar van** het account kiest, meldt u zich aan met een Azure AD-account. Als uw organisatie gebruikmaakt Azure AD Premium en automatische MDM-inschrijving heeft geconfigureerd, HoloLens automatisch ingeschreven bij MDM. Als uw organisatie geen gebruik maakt Azure AD Premium, is automatische MDM-inschrijving niet beschikbaar. In dat geval moet u de inschrijving [handmatig HoloLens in apparaatbeheer.](hololens-enroll-mdm.md#different-ways-to-enroll)

        1. Voer de accountgegevens van uw organisatie in.
        1. Accepteer de privacyverklaring en de gebruikslicentieovereenkomst.
        1. Meld u aan met uw Azure AD-referenties. Dit kan worden omgeleid naar de aanmeldingspagina van uw organisatie.
        1. Ga door met het instellen van het apparaat.

    - Wanneer u I **own it kiest,** kunt u zich aanmelden met een Microsoft-account. Nadat de installatie is voltooid, kunt u deze handmatig HoloLens [in apparaatbeheer.](hololens-enroll-mdm.md#different-ways-to-enroll)

        1. Voer uw Microsoft-account in.
        2. Voer uw wachtwoord in. Als uw Microsoft-account verificatie in twee [stappen (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/)vereist, voltooit u het verificatieproces.

        
1. Stel Iris-aanmelding in door Volgende **te selecteren.** U krijgt een vergelijkbare ervaring als bij het oogcontact. Selecteer **Voltooid wanneer** de scan is voltooid. U kunt ook Overslaan selecteren **om** deze stap over te slaan.
    
    ![Iris setup ](images/setup-iris.png) ![ Iris setup completion (Iris-instelling voltooien)](images/iris-setup-complete.png) 
     
  
1. U gaat een pincode instellen om u aan te melden bij het apparaat. Deze pincode is apparaatsyte specifiek. 

    ![Installatie Windows Hello](images/setup-windows-hello.png)

    ![Een Windows Hello instellen](images/windows-hello-pin.png)

    ![Windows Hello Installatie is geslaagd](images/windows-hello-successful.png) 
    
1. Selecteer of u spraak wilt inschakelen op HoloLens 2.

    ![Cortana](images/22-do-more-with-voice.png)

1. Selecteer of u de locatie op de HoloLens 2.
    
    ![Locatieservices inschakelen](images/setup-location-services.png)

1. Selecteer uw telemetrieniveau. Schakel desgewenst Optionele telemetrie in. Deze informatie helpt het technische team HoloLens te helpen.

     ![Telemetrieniveau](images/24-telemetry.png)

1. Meer informatie over het gebruik van het begingebaar op HoloLens 2.

     ![Meer informatie over het gebruik van het begingebaar, afbeelding 1](images/26-01-startmenu-learning.png)

     ![Meer informatie over het gebruik van het begingebaar, afbeelding 2](images/26-02-startmenu-learning.png)

Gefeliciteerd  De installatie is voltooid en u kunt de HoloLens.

## <a name="next-steps"></a>Volgende stappen

1. Ga direct aan de slag met Mixed Reality en navigeer naar Windows 10 op uw HoloLens. Bekijk de **Tips-app** voor praktijkzelfstudies voor handinteracties. Gebruik het startgebaar om naar Start te gaan of 'Ga naar start' te zeggen en selecteer Tips.

1. Klik hieronder om door te gaan met het lezen van HoloLens 2.

> [!div class="nextstepaction"]
> [Kennismaken met HoloLens 2](hololens2-basic-usage.md)
