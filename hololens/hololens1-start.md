---
title: HoloLens (eerste generatie) instellen
description: Meer informatie over het instellen van uw HoloLens (1e generatie) voor de eerste keer via een Wi-Fi-netwerk met een Microsoft-account (MSA) of een Azure Active Directory-account (AAD).
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
ms.openlocfilehash: f0ec62e55f15fda6d5a8304ea2bb77039d644b9e
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/19/2021
ms.locfileid: "111377838"
---
# <a name="set-up-your-hololens-1st-gen"></a>Uw HoloLens (eerste generatie) instellen

De eerste keer dat u uw HoloLens in zet, wordt u begeleid bij het gebruik van uw apparaat, het instellen van uw apparaat en het aanmelden.  In dit artikel wordt de eerste start- en installatieervaring van HoloLens (eerste generatie) beschreven.

In de volgende sectie leert u hoe u met HoloLens werkt en hoe u met hologrammen communiceert. Zie Aan de slag met [HoloLens (eerste generatie)](hololens1-basic-usage.md)om verder te gaan met dat artikel.

## <a name="before-you-start"></a>Voordat u begint

Voordat u aan de slag gaat, moet u ervoor zorgen dat het volgende beschikbaar is:

**Een Wi-Fi verbinding**. U moet uw HoloLens verbinden met een Wi-Fi netwerk om dit in te stellen. De eerste keer dat u verbinding maakt, hebt u een open of met een wachtwoord beveiligd netwerk nodig waarvoor u niet naar een website hoeft te navigeren of certificaten hoeft te gebruiken om verbinding te maken. [Meer informatie over de websites die HoloLens gebruikt.](hololens-offline.md)

**Een Microsoft-account of een werkaccount.** U moet ook een Microsoft-account gebruiken (of een werkaccount als uw organisatie eigenaar is van het apparaat) om u aan te melden bij HoloLens. Als u nog geen Microsoft-account, gaat u naar [account.microsoft.com](https://account.microsoft.com) en stelt u er gratis een in.

**Een veilige, goed belichte ruimte zonder tripping-risico's.** [Informatie over status en veiligheid.](https://go.microsoft.com/fwlink/p/?LinkId=746661)

**De optionele comfortaccessoires** die bij uw HoloLens worden gebruikt, zodat u de meest geschikte versie kunt krijgen. [Meer informatie over passend en comfort.](https://support.microsoft.com/help/12632/hololens-fit-your-hololens)

> [!NOTE]
>  
> - De eerste keer dat u uw HoloLens gebruikt, is [Cortana](hololens-cortana.md) al ingeschakeld en klaar om u te begeleiden (hoewel ze pas op uw vragen kan reageren nadat u uw apparaat hebt ingesteld). U kunt Cortana op elk moment uitschakelen in de instellingen van Cortana.
> - Als u wilt overschakelen naar de Chinese of Japanse versie van HoloLens, moet u de build voor de taal downloaden op een pc en deze vervolgens installeren op uw HoloLens. Zie Gelokaliseerde versies van [HoloLens (1e generatie)](hololens1-install-localized.md)installeren voor meer informatie.

## <a name="start-your-hololens-and-set-up-windows"></a>Uw Hololens starten en Windows instellen

De eerste keer dat u uw HoloLens start, is uw eerste taak om Windows Holographic in te stellen op uw apparaat.

1. Verbinding maken met internet (HoloLens helpt u bij het selecteren van Wi-Fi netwerk).

1. Meld u aan bij uw gebruikersaccount. Kies tussen **Mijn werk of school is eigenaar en** ik ben er eigenaar **van.**
    - Wanneer u Mijn **werk of school is eigenaar kiest,** meldt u zich aan met een Azure AD-account. Als uw organisatie gebruikmaakt Azure AD Premium en automatische MDM-inschrijving heeft geconfigureerd, wordt HoloLens automatisch ingeschreven bij MDM. Als uw organisatie geen Azure AD Premium, is automatische MDM-inschrijving niet beschikbaar. Daarom moet u HoloLens handmatig inschrijven [bij apparaatbeheer.](hololens-enroll-mdm.md#different-ways-to-enroll) Als u zich de eerste keer wilt aanmelden bij uw apparaat met een werk- of schoolaccount, volgt u deze stappen:
        1. Voer de accountgegevens van uw organisatie in.
        1. Accepteer de privacyverklaring.
        1. Meld u aan met uw Azure AD-referenties. Dit kan worden omgeleid naar de aanmeldingspagina van uw organisatie.
        1. Ga door met het instellen van het apparaat.
    - Wanneer u I **own it kiest,** kunt u zich aanmelden met behulp van een Microsoft-account. Nadat de installatie is voltooid, kunt u [HoloLens handmatig inschrijven bij apparaatbeheer.](hololens-enroll-mdm.md#different-ways-to-enroll)
        1. Voer uw Microsoft-account in.
        1. Voer uw wachtwoord in. Als uw Microsoft-account verificatie in twee [stappen (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/)vereist, voltooit u het verificatieproces.

1. Het apparaat stelt uw tijdzone in op basis van informatie die wordt ontvangen van het Wi-Fi netwerk.

## <a name="calibration"></a>Kalibratie

Nadat Cortana zichzelf heeft introduceert, is de volgende installatiestap kalibreren. Voor de beste HoloLens-ervaring moet u het kalibratieproces tijdens de installatie voltooien.

HoloLens (1e generatie) gebruikt de afstand tussen uw leerlingen (IPD of [interpupillale](https://en.wikipedia.org/wiki/Interpupillary_distance)afstand) om hologrammen duidelijk te maken en gemakkelijk te gebruiken. Als het IP-adres niet juist is, kunnen hologrammen instabiel of op een onjuiste afstand lijken te zijn.

Tijdens de kalibratie vraagt HoloLens u om uw vinger uit te lijnen met een reeks van zes doelen per oog. HoloLens gebruikt dit proces om de juiste IP-adres voor uw ogen in te stellen. Als de kalibratie moet worden bijgewerkt of aangepast voor een nieuwe gebruiker, kan de nieuwe gebruiker de kalibratie-app buiten de installatie uitvoeren.

![Scherm voor uitlijning van IPD-vinger bij de tweede stap](./images/ipd-finger-alignment-300px.jpg)

*Scherm voor uitlijning van IPD-vinger bij de tweede stap*

Gefeliciteerd De installatie is voltooid en u kunt HoloLens gaan gebruiken.

## <a name="next-steps"></a>Volgende stappen

> [!div class="nextstepaction"]
> [Aan de slag met HoloLens (eerste generatie)](hololens1-basic-usage.md)
