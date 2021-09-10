---
title: Een HoloLens (eerste generatie) instellen
description: Meer informatie over het instellen van uw HoloLens (1e generatie) voor de eerste keer via Wi-Fi-netwerk met een Microsoft-account (MSA) of Azure Active Directory-account (AAD).
ms.assetid: 0136188e-1305-43be-906e-151d70292e87
ms.prod: hololens
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.date: 8/12/2019
manager: jarrettr
ms.localizationpriority: medium
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 06b7142be471d0db3f45812654288a33425abd60
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427756"
---
# <a name="set-up-your-hololens-1st-gen"></a>Uw HoloLens (eerste generatie) instellen

De eerste keer dat u uw apparaat HoloLens, wordt u begeleid bij het maken van een apparaat, het instellen van uw apparaat en het aanmelden.  In dit artikel worden de HoloLens (eerste generatie) eerste start- en installatie-ervaring beschreven.

In de volgende sectie leert u hoe u kunt werken met HoloLens en communiceren met hologrammen. Zie Aan de slag met HoloLens [(1e generatie) om verder te](hololens1-basic-usage.md)gaan met dat artikel.

## <a name="before-you-start"></a>Voordat u begint

Voordat u aan de slag gaat, moet u ervoor zorgen dat het volgende beschikbaar is:

**Een Wi-Fi verbinding**. U moet uw netwerk verbinden HoloLens een Wi-Fi netwerk om dit in te stellen. De eerste keer dat u verbinding maakt, hebt u een open of met een wachtwoord beveiligd netwerk nodig waarvoor u niet hoeft te navigeren naar een website of certificaten hoeft te gebruiken om verbinding te maken. [Meer informatie over de websites die HoloLens gebruikt.](hololens-offline.md)

**Een Microsoft-account of een werkaccount.** U moet ook een Microsoft-account gebruiken (of een werkaccount, als uw organisatie eigenaar is van het apparaat) om u aan te melden bij HoloLens. Als u nog geen Microsoft-account hebt, gaat u naar [account.microsoft.com](https://account.microsoft.com) en stelt u er gratis een in.

**Een veilige, goed belichte ruimte zonder trippingsgevaren.** [Informatie over status en veiligheid.](https://go.microsoft.com/fwlink/p/?LinkId=746661)

**De optionele comfortaccessoires** die bij uw HoloLens, om u te helpen de meest geschikte keuze te krijgen. [Meer informatie over passendheid en comfort.](https://support.microsoft.com/help/12632/hololens-fit-your-hololens)

> [!NOTE]
>  
> - De eerste keer dat u uw HoloLens gebruikt, [is Cortana](hololens-cortana.md) al aan en klaar om u te begeleiden (hoewel ze pas op uw vragen kan reageren nadat u uw apparaat hebt ingesteld). U kunt de Cortana op elk moment uitschakelen in Cortana instellingen van uw apparaat.
> - Als u wilt overschakelen naar de Chinese of Japanse versie van HoloLens, moet u de build voor de taal downloaden op een pc en deze vervolgens installeren op uw HoloLens. Zie Gelokaliseerde versies van HoloLens [(1e generatie)](hololens1-install-localized.md)installeren voor meer informatie.

## <a name="start-your-hololens-and-set-up-windows"></a>Uw Hololens starten en de Windows

De eerste keer dat u uw HoloLens, is uw eerste taak het instellen van Windows Holographic op uw apparaat.

1. Verbinding maken verbinding maken met internet (HoloLens begeleidt u bij het selecteren van Wi-Fi netwerk).

1. Meld u aan bij uw gebruikersaccount. Kies tussen **Mijn werk of school is eigenaar en** ik ben er de eigenaar **van.**
    - Wanneer u Mijn werk of school is eigenaar **kiest,** meldt u zich aan met een Azure AD-account. Als uw organisatie gebruikmaakt Azure AD Premium automatische MDM-inschrijving heeft geconfigureerd, HoloLens automatisch ingeschreven bij MDM. Als uw organisatie geen gebruik maakt van Azure AD Premium, is automatische MDM-inschrijving niet beschikbaar, dus moet u deze handmatig HoloLens [registreren bij apparaatbeheer.](hololens-enroll-mdm.md#different-ways-to-enroll) Als u zich de eerste keer wilt aanmelden bij uw apparaat met een werk- of schoolaccount, volgt u deze stappen:
        1. Voer de accountgegevens van uw organisatie in.
        1. Accepteer de privacyverklaring.
        1. Meld u aan met uw Azure AD-referenties. Dit kan worden omgeleid naar de aanmeldingspagina van uw organisatie.
        1. Ga door met het instellen van het apparaat.
    - Wanneer u I **own it kiest,** kunt u zich aanmelden met behulp van een Microsoft-account. Nadat de installatie is voltooid, kunt u deze handmatig inschrijven [HoloLens apparaatbeheer.](hololens-enroll-mdm.md#different-ways-to-enroll)
        1. Voer uw Microsoft-account in.
        1. Voer uw wachtwoord in. Als uw Microsoft-account verificatie [in twee stappen (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/)vereist, voltooit u het verificatieproces.

1. Het apparaat stelt uw tijdzone in op basis van informatie die wordt ontvangen van het Wi-Fi netwerk.

## <a name="calibration"></a>Kalibratie

Nadat Cortana zichzelf heeft introduceert, is de volgende installatiestap kalibreren. Voor de beste HoloLens ervaring moet u het kalibratieproces tijdens de installatie voltooien.

HoloLens (eerste generatie) gebruikt de afstand tussen uw pupillen (IPD of [interpupillary distance)](https://en.wikipedia.org/wiki/Interpupillary_distance)om hologrammen duidelijk en eenvoudig te gebruiken. Als de IPD niet juist is, kunnen hologrammen instabiel of op een onjuiste afstand lijken te zijn.

Tijdens de kalibratie HoloLens u gevraagd om uw vinger uit te lijnen met een reeks van zes doelen per oog. HoloLens dit proces gebruikt om de juiste IP-adres voor uw ogen in te stellen. Als de kalibratie moet worden bijgewerkt of aangepast voor een nieuwe gebruiker, kan de nieuwe gebruiker de kalibratie-app buiten de installatie uitvoeren.

![Scherm voor uitlijning van IPD-vinger bij de tweede stap.](./images/ipd-finger-alignment-300px.jpg)

*Scherm voor uitlijning van IPD-vinger bij tweede stap*

Gefeliciteerd De installatie is voltooid en u kunt beginnen met het HoloLens.

## <a name="next-steps"></a>Volgende stappen

> [!div class="nextstepaction"]
> [Aan de slag HoloLens (eerste generatie)](hololens1-basic-usage.md)
