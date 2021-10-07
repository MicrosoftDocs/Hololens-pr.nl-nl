---
title: Uw HoloLens delen met meerdere personen
description: U kunt configureren HoloLens worden gedeeld door meerdere Azure Active Directory-accounts of door meerdere gebruikers die één account gebruiken.
ms.prod: hololens
ms.sitesec: library
author: qianw211
ms.author: v-qianwen
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/23/2021
ms.reviewer: anisgup
manager: sean-kerawala
appliesto:
- HoloLens 2
ms.openlocfilehash: bbb955edaa500187ea921538291bb1c7bda05422
ms.sourcegitcommit: be1393d24a98381e37bd1f56183c1f381f87cbd4
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/06/2021
ms.locfileid: "129600726"
---
# <a name="share-your-hololens-with-multiple-people"></a>Uw HoloLens delen met meerdere personen

## <a name="overview"></a>Overzicht

Bedrijven investeren vaak in veel gedeelde HoloLens apparaten. Hoe u HoloLens is flexibel over de hele wereld, afhankelijk van uw afzonderlijke vereisten. Hier is een voorbeeld van een aantal ervaringen voor meerdere gebruikers:

- Er wordt een HoloLens 2 apparaten ingesteld via Windows Autopilot voor HoloLens 2, met een consistente portfolio van bedrijfstoepassingen op elk apparaat. U hebt een aantal verschillende Kiosk-profielen ingesteld voor verschillende Azure AD-groepen. Elke gebruiker meldt zich aan bij HoloLens FIDO2-sleutels en meldt zich aan bij zijn eigen Azure AD-account en krijgt een op maat gemaakte ervaring te zien.
- Een onafhankelijke softwareleverancier (ISV) huurt HoloLens 2 Devices met D365 Remote Assist en hun LOB-toepassing (Line-Of-Business) naar het bedrijf van een klant. Deze apparaten zijn geconfigureerd voor kiosken die alleen hun LOB-app en -Remote Assist bevatten en worden gedeeld met meerdere eindgebruikers. WDAC wordt gebruikt om te zorgen dat de Instellingen-app niet Microsoft Edge wordt starten. Opgenomen in de verhuur is een USB-C-accupakket om de apparaten volledig op te laden voor meerdere ploegen.
- Een eindgebruiker bij een onderneming probeert Bluetooth op het apparaat aan te passen zodat deze verbinding kan maken met een nieuw apparaat, maar het beleid Pagina Instellingen zichtbaarheid is ingeschakeld om te voorkomen dat de pagina Apparaten wordt weergegeven. Ze hebben naar behoefte nog steeds toegang tot andere pagina's, zoals Wi-Fi zodat ze Remote Assist kunnen gebruiken op meerdere locaties met dezelfde HoloLens.

## <a name="best-practices"></a>Aanbevolen procedures

Wanneer u van plan bent uw apparaten te delen, zijn er verschillende overwegingen om uw apparaatomgeving te optimaliseren op basis van uw bedrijfsbehoeften.

- [Identiteit en authenticatie](#identity-and-authentication)
- [Apparaatbeheer](#device-management)
- [Geavanceerd apparaatbeheer - Kiosk en WDAC](#advanced-device-management---kiosk-and-wdac)
- [Fysiek beheer](#physical-management)

### <a name="identity-and-authentication"></a>[Identiteit en authenticatie](hololens-identity.md)

Als u van plan bent meerdere accounts op een apparaat te hebben, hebt u Azure AD-accounts met alle verificatiemodi. Deze verificatiemethoden worden gebaseerd op Windows Hello [,](/windows-hardware/design/device-experiences/windows-hello)met inbegrip van Iris- en FIDO2-sleutels.

- FIDO 2-beveiligingssleutels zijn uitstekend als u meerdere apparaten, veel gebruikers of voortdurend nieuwe apparaten gebruikt.
- Als u tien of minder gebruikers hebt, is Iris een snelle oplossing voor het aanmelden van gebruikers die zich eerder bij hetzelfde apparaat hebben aangemeld.

### <a name="device-management"></a>[Apparaatbeheer](hololens-csp-policy-overview.md)

Als apparaten worden gedeeld tussen gebruikers, wilt u waarschijnlijk apparaatbeperkingen gebruiken. Met apparaatbeheer kunt u een aantal beleidsregels instellen om uw gebruikers in staat te stellen het apparaat te gebruiken, updates te beheren of te beperken wat het apparaat kan doen. Het is raadzaam om onze algemene [apparaatbeperkingen te bekijken](hololens-common-device-restrictions.md)en te kijken of deze aanbevelingen geschikt lijken te zijn voor uw organisatie. Zodra u weet welk beleid u wilt gebruiken, kunt u deze toepassen via [de MDM-pakketten (Endpoint Manager](hololens-mdm-configure.md) van Microsoft).

### <a name="advanced-device-management---kiosk-and-wdac"></a>Geavanceerd apparaatbeheer - [Kiosk](hololens-kiosk.md) en [WDAC](windows-defender-application-control-wdac.md)

In sommige gevallen wilt u mogelijk beperken welke toepassingen toegankelijk zijn voor de eindgebruikers. U kunt beperken welke apps gebruikers krijgen te zien in het menu Start met behulp [van kioskmodus.](hololens-kiosk.md) Kiosk kan worden geconfigureerd om verschillende startmenu's weer te geven op basis van gebruikers, Azure-groepen of speciale gebruikerstypen; dergelijke bezoekers of exclusief apparaateigenaren. U kunt meerdere apps of slechts één app kiezen. Een kiosk voor meerdere apps stopt de ene app niet om een andere app te starten, dus als de Store of een andere app beschikbaar is, kunnen gebruikers nog steeds een andere app starten.

Mogelijk wilt u ook het starten van apps of services volledig stoppen met behulp van [Windows Defender Application Control (WDAC)](windows-defender-application-control-wdac.md) om apps te beperken. WDAC verschilt van Kiosk, omdat de gebruikersinterface van HoloLens niet wordt gewijzigd, maar in plaats daarvan geen geblokkeerde app mag worden starten.

[Pagina Instellingen Zichtbaarheid](settings-uri-list.md) is een andere manier om beperkingen toe te voegen aan een apparaat. In het geval dat u gebruikers toegang moet verlenen tot sommige pagina's in de Instellingen-app, maar niet alle pagina's en zichtbaarheid kunt u Instellingen gebruiken om de toegang te beperken. Dit is bijvoorbeeld handig als uw gebruikers de Wi-Fi moeten wijzigen, maar u niet wilt dat ze toegang hebben tot de pagina Accounts.

### <a name="physical-management"></a>Fysiek beheer

Bij het delen van het apparaat tussen meerdere gebruikers zijn er enkele fysieke overwegingen.

- Zorg ervoor dat apparaten kosten in rekening worden brengen tussen ploegen.
- Als een apparaat vereist is voor een shift en meerdere ploegen moet duren, kunt u overwegen om aan het begin van een shift een externe accu te gebruiken terwijl het apparaat nog steeds aanzienlijke lading heeft volgens de beherende heat [directions](hololens2-charging.md#managing-heat).
- Wanneer apparaten worden opgeslagen, blijven ze aangesloten en verbonden met een netwerk. Dit is de beste manier om updates van het besturingssysteem en de app te garanderen.
- Denk na over hoe u van plan [bent om het apparaat tussen](hololens2-maintenance.md) gebruikers op te schonen.
- Voor een apparaat met één gedeelde gebruiker als u een gedeelde pincode/wachtwoord voor één gebruiker gebruikt, moet u de pincode/het wachtwoord niet aan de zijkant van het apparaat zetten.
- Gebruik verschillende pincodes/wachtwoorden voor meerdere apparaten met één gedeelde gebruiker.

## <a name="share-with-multiple-people-each-using-their-own-account"></a>Delen met meerdere personen, elk met hun eigen account

Afzonderlijke Azure Active Directory (Azure AD)-accounts zijn de voorkeurs- en veiligste identiteitsgebruikscase voor HoloLens 2 gebruikers. Wanneer u hun eigen Azure AD-accounts gebruikt, kunnen meerdere gebruikers elk hun eigen gebruikersinstellingen en gebruikersgegevens op het apparaat behouden. Er kan slechts één gebruiker tegelijk worden aangemeld. Wanneer een gebruiker zich meldt, HoloLens de vorige gebruiker af.

Als u ervoor wilt zorgen dat meerdere personen hun eigen accounts op uw HoloLens, volgt u deze stappen om deze te configureren:

1. Wanneer u [het apparaat in stelt,](hololens2-start.md)selecteert u **Mijn werk** of school is eigenaar ervan en meldt u zich aan met behulp van een Azure AD-account.
1. Nadat u de installatie hebt voltooien, moet u ervoor zorgen dat de accountinstellingen (Instellingen > Accounts) **Andere gebruikers bevatten.**

> [!NOTE]
> Als uw apparaat niet is ingesteld met een Azure AD-account, moet het opnieuw worden ingesteld of een [reflash worden gebruikt](hololens-recovery.md) en correct worden ingesteld.

Als u HoloLens, volgt elke gebruiker deze stappen:

1. Als een andere gebruiker het apparaat heeft gebruikt, kiest u een van de volgende opties:
   - Druk eenmaal op de aan/uit-knop om naar de stand-by te gaan en druk vervolgens nogmaals op de aan/uit-knop om terug te keren naar het vergrendelingsscherm
   - Selecteer de tegel Gebruiker in **het Startmenu** of meld u af in het **Power-menu om** de huidige gebruiker af te melden.

1. Gebruik de referenties van uw Azure AD-account om u aan te melden bij het apparaat.  
    - Als dit de eerste keer is dat u het [](hololens-calibration.md) apparaat hebt gebruikt, wordt u gevraagd om de HoloLens naar uw eigen ogen te kalibreren.
    - Als u het apparaat eerder hebt gebruikt:
        - [Windows Holographic versie 20H2, build 19041.1128](hololens-release-notes.md#windows-holographic-version-20h2) of hoger, wordt de weergave naadloos aangepast voor kwaliteit en een vertrouwd weergave-ervaring.
        - Voor eerdere builds is handmatige kalibratie nodig om u aan te passen aan uw ogen.

> [!TIP]
> Als een gebruiker nog niet is aangemeld bij een apparaat, probeert u een van deze twee methoden voor een snellere aanmelding:
>
> - **FIDO** 2-beveiligingssleutel: uw FIDO2-beveiligingssleutel wordt automatisch herkend en de gebruiker hoeft geen gebruikersreferenties in te typen of MFA te gebruiken. Dit is de snelste methode om u aan te melden op een nieuw apparaat.
> - **Webverificatie:** wanneer u zich bij een nieuw  apparaat aanmelden, kunt u de koppeling Aanmelden vanaf een ander apparaat selecteren. Hiermee wordt een code van 9 tekens gegenereerd die u op [aka.ms/devicelogin](https://login.microsoftonline.com/common/oauth2/deviceauth) kunt gebruiken om u aan te melden als de gebruiker op het apparaat, of typt u uw gebruikersnaam en wachtwoord met een toetsenbord voor uw gemak.

Als u een lijst met de apparaatgebruikers wilt zien of als u een gebruiker van het apparaat wilt verwijderen, gaat u **naar Instellingen**  >  **Accounts**  >  **Andere gebruikers.**

## <a name="share-with-multiple-people-all-using-the-same-account"></a>Delen met meerdere personen, allemaal met hetzelfde account

Meerdere gebruikers kunnen ook een HoloLens delen terwijl ze één gebruikersaccount gebruiken. Hoewel het voor gebruikers HoloLens voorkeur is om zich met hun afzonderlijke identiteiten (Azure AD-accounts) aan te melden bij het apparaat, is dit in sommige organisaties geen optie.

Er zijn twee methoden voor gedeelde apparaten beschikbaar:

- **Meerdere eindgebruikers die één apparaat** delen: een HoloLens apparaat wordt toegewezen aan een aangewezen ruimte waar werknemers het apparaat kunnen gebruiken. Voorbeelden hiervan zijn een schone ruimte of een suite met kamers.

- **Meerdere eindgebruikers die meerdere apparaten delen:** HoloLens apparaten zich in een gedeelde opslagruimte waar werknemers elk apparaat kunnen gebruiken. Voorbeelden hiervan zijn een olieplatform of een autodealer/auto-dealer.

Wanneer een nieuwe gebruiker het apparaat voor het eerst in gebruik neemt terwijl hetzelfde account blijft aangemeld, wordt de gebruiker gevraagd om de weergave-ervaring snel te kalibreren en te personaliseren. Op het apparaat worden de kalibratiegegevens opgeslagen om de kwaliteit en het comfort van de weergave van elke gebruiker automatisch te optimaliseren. Gebruikers hoeven het apparaat niet opnieuw te kalibreren.
