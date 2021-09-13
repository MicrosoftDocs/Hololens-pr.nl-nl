---
title: HoloLens opmerkingen bij de release van eerste (gen)
description: Meer informatie over updates in elke nieuwe HoloLens release.
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
- HoloLens 1
ms.openlocfilehash: 0fb6c9ed1cd8d3ecc23975052eed54512a465bfb
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032785"
---
# <a name="hololens-1st-gen-release-notes"></a>HoloLens opmerkingen bij de release van eerste (gen)

## <a name="hololens-1st-gen-long-term-servicing"></a>HoloLens (1e generatie) Long Term Servicing
HoloLens (eerste generatie) is de lts-status (Long Term Servicing) ingegaan. Toekomstige updates zijn gericht op problemen en beveiligingsfixes, terwijl de functiepariteit behouden blijft met de Windows 10 Holographic versie 1809 voor HoloLens (1e generatie).

Voor ontwikkelaars betekent dit dat HoloLens (1e generatie) geen ondersteuning biedt voor de OpenXR-API.  Deze headsets blijven ondersteund in Unity 2019 LTS met de WinRT API-back-end voor de volledige levenscyclus van Unity 2019 LTS tot halverwege 2022.

### <a name="windows-10-holographic-version-1809"></a>Windows 10 Holographic versie 1809

> **Van toepassing op:** HoloLens (eerste generatie)

| Functie | Details |
|---|---|
| **Menu Snelle acties** | Wanneer u zich in een app besturingssysteem besturingssysteem gebruikt, wordt er nu met de gebaar Van de bloem een menu Snelle acties geopend, waarmee u snel toegang hebt tot veelgebruikte systeemfuncties zonder dat u de app moet verlaten. <br> Zie [HoloLens in kioskmodus instellen](hololens-kiosk.md) voor informatie over het menu Snelle acties in de kioskmodus.<br><br> |
| **Video-opname stoppen via het menu Start of snelle acties** | Als u video-opname start vanuit Startmenu menu of het menu Snelle acties, kunt u de opname vanaf dezelfde plaats stoppen. (Vergeet niet dat u dit altijd kunt doen met spraakopdrachten.) |
| **Project naar een Miracast apparaat met ingeschakelde functie** | Project inhoud HoloLens een Surface-apparaat of tv/monitor in de buurt als u een Microsoft Display-adapter gebruikt.  Selecteer **op** Start **de Verbinding maken** selecteer vervolgens het apparaat dat u wilt projecten. **Opmerking:** U kunt een HoloLens voor het gebruik van Miracast projectie zonder de ontwikkelaarsmodus in te schakelen. |
| **Nieuwe meldingen** | Pop-upweergaven van meldingen op HoloLens, net als op een pc. Staren om op ze te reageren of ze te laten weggaan (of als u een in immersieve ervaring hebt, gebruikt u het bloemgebaar). |
| **HoloLens overlays**<br>(bestands picker, toetsenbord, dialoogvensters, enzovoort) | U ziet nu overlays, zoals het toetsenbord, dialoogvensters, bestands kiezen, enzovoort bij het gebruik van in immersive apps. |
| **Visuele feedback overlay-gebruikersinterface voor volumewijziging** | Wanneer u de knoppen volume omhoog/omlaag op uw HoloLens ziet u een visuele weergave van het volumeniveau. |
| **Nieuwe gebruikersinterface voor het opstarten van apparaten** | Er is een laadindicator toegevoegd tijdens het opstartproces om visuele feedback te geven dat het systeem wordt geladen. Start het apparaat opnieuw op om de nieuwe laadindicator weer te geven. Deze staat tussen het bericht 'Hallo' en het Windows opstartlogo. |
| **Delen in de buurt** | Toevoeging van de Windows delen in de buurt, zodat u een opname kunt delen met een Windows apparaat. Wanneer u een foto of video op een HoloLens vast legt (of de knop Delen gebruikt vanuit een app zoals Microsoft Edge), selecteert u een apparaat in de buurt Windows wilt delen. |
| **Delen vanuit Microsoft Edge** | De knop Delen is nu beschikbaar in Microsoft Edge vensters op HoloLens. Selecteer Microsoft Edge in het **dialoogvenster Delen.** Gebruik de HoloLens delen om webinhoud te delen. |

#### <a name="for-international-customers"></a>Voor internationale klanten

| Functie | Details |
| --- | --- |
| Gelokaliseerde Chinese en Japanse builds | Gebruik HoloLens gelokaliseerde gebruikersinterface voor vereenvoudigd Chinees of Japans, inclusief gelokaliseerde Pinyin-toetsenbord-, dicteer- en spraakopdrachten.<br>[Meer informatie over het installeren van de Chinese en Japanse versies van HoloLens.](hololens1-install-localized.md) |
| Spraaksynthese (TTS) | De functie voor spraaksynthese ondersteunt nu Chinees, Japans en Engels. |

#### <a name="for-administrators"></a>Voor beheerders

| Functie |  Details  |
|---|----|
| [Inrichten na installatie inschakelen](hololens-provisioning.md) | U kunt nu op elk moment een runtime-inrichtingspakket toepassen met behulp **van Instellingen**. |
| Toegewezen toegang met Azure AD-groepen | U kunt nu Azure AD-groepen gebruiken voor de configuratie van Windows toegewezen toegang om een kioskconfiguratie voor één of meerdere apps in te stellen. |
| Schakel van het aanmeldingsscherm naar het profiel voor het aanmelden via een pincode | Aanmelden via pincode is nu beschikbaar voor **Andere gebruiker.** |
| Aanmelden met web-Referentieprovider wachtwoord | U kunt nu de aanmeldingsoptie Globe selecteren om de web-aanmelding te starten met uw wachtwoord. Selecteer in het aanmeldingsscherm **Aanmeldingsopties** en selecteer de optie Wereldbol om de web-aanmelding te starten. Voer indien nodig uw gebruikersnaam in en vervolgens uw wachtwoord. <br>**Opmerking:** U kunt ervoor kiezen om alle pincode-/smartcardopties over te laten wanneer u hier om wordt gevraagd tijdens het aanmelden bij het web. |
| Hardwaregegevens van apparaten lezen via MDM, zodat apparaten kunnen worden gevolgd op serienummer | IT-beheerders kunnen de HoloLens apparaatserienummer in hun MDM-console bekijken en bijhouden. Raadpleeg de MDM-documentatie voor de beschikbaarheid van functies en instructies. |
| Apparaatnaam HoloLens via MDM (naam wijzigen) | IT-beheerders kunnen hun apparaten in HoloLens MDM-console bekijken en de naam ervan wijzigen. Raadpleeg de MDM-documentatie voor de beschikbaarheid van functies en instructies. |

### <a name="windows-10-version-1803-for-microsoft-hololens"></a>Windows 10 versie 1803 voor Microsoft HoloLens

> **Van toepassing op:** HoloLens (eerste generatie)

Windows 10 versie 1803 is de eerste functie-update voor Windows Holographic for Business sinds de release in Windows 10 versie 1607. Deze update introduceert de volgende wijzigingen:

- Voorheen kon u alleen controleren of de upgradelicentie voor Commercial Suite was toegepast op uw HoloLens-apparaat door te controleren of VPN een beschikbare optie was op het apparaat. Nu wordt **Instellingen**  >  **systeem** weergegeven nadat **Windows Holographic for Business** upgradelicentie is toegepast. [Meer informatie over het ontgrendelen Windows Holographic for Business functies](hololens1-upgrade-enterprise.md).

- U kunt het buildnummer van het besturingssysteem weergeven in apparaateigenschappen in de Verkenner-app en in [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq).
- Het inrichten van HoloLens apparaat is nu eenvoudiger met de nieuwe wizard **HoloLens-apparaten** inrichten in Windows Configuration Designer-hulpprogramma. In de wizard kunt u de installatie-ervaring en netwerkverbindingen configureren, de ontwikkelaarsmodus instellen en bulksgewijze Azure AD-tokens verkrijgen. [Meer informatie over het gebruik van de eenvoudige inrichtingswizard voor HoloLens.](hololens-provisioning.md#provisioning-package-hololens-wizard)

- Wanneer u een lokaal account in een inrichtingspakket maakt, verloopt het wachtwoord niet langer om de 42 dagen.

- U kunt deze HoloLens als kiosk voor één app of [voor meerdere apps.](hololens-kiosk.md) Met de kioskmodus voor meerdere apps kunt u een HoloLens om alleen de door u opgegeven apps uit te voeren en voorkomt u dat gebruikers wijzigingen aanbrengen.

- Media Transfer Protocol (MTP) is ingeschakeld, zodat u het HoloLens-apparaat via USB kunt verbinden met een pc en bestanden tussen HoloLens en de pc kunt overdragen. U kunt de verkenner-app ook gebruiken om bestanden te verplaatsen en te verwijderen vanuit HoloLens.

- Eerder moest u, nadat u zich bij het apparaat hebt aangemeld met een Azure Active Directory-account (Azure AD), werktoegang toevoegen **in** **Instellingen** om toegang te krijgen tot bedrijfsresources. U meldt zich nu aan met een Azure AD-account en de inschrijving vindt automatisch plaats.

- Voordat u zich aanmelden, kunt u het netwerkpictogram onder het wachtwoordveld kiezen om een ander netwerk Wi-Fi verbinding te maken. U kunt ook verbinding maken met een gastnetwerk, zoals in een hotel, conferentiecentrum of bedrijf.

- U kunt nu eenvoudig [een HoloLens met meerdere personen met behulp](hololens-multiple-users.md) van Azure AD-accounts.

- Wanneer de installatie of aanmelding mislukt, kiest u de nieuwe optie **Gegevens verzamelen** om diagnostische logboeken op te halen voor probleemoplossing.

- Afzonderlijke gebruikers kunnen hun zakelijke e-mail synchroniseren zonder hun apparaat in te schrijven bij Mobile Device Management (MDM). U kunt het apparaat gebruiken met een Microsoft-account, de Mail-app downloaden en installeren en rechtstreeks een e-mailaccount toevoegen.

- U kunt de MDM-synchronisatiestatus voor een apparaat controleren in **Instellingen**  >  **Accounts**  >  **Access Work or School**  >  **Info**. In de **sectie Apparaatsynchronisatiestatus** kunt u een synchronisatie starten, gebieden bekijken die worden beheerd door MDM en een geavanceerd diagnostisch rapport maken en exporteren.
