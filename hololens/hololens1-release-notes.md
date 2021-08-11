---
title: HoloLens opmerkingen bij de release van de eerste (gen)
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
ms.openlocfilehash: e332794baf20fbab8278a138ceeafb651c6fa2a06f3f41a66038e544f7a6e46b
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/05/2021
ms.locfileid: "115661831"
---
# <a name="hololens-1st-gen-release-notes"></a>HoloLens opmerkingen bij de release van de eerste (gen)

## <a name="hololens-1st-gen-long-term-servicing"></a>HoloLens (1e generatie) Long Term Servicing
HoloLens (1e generatie) is lts-status (Long Term Servicing). Toekomstige updates richten zich op problemen en beveiligingsfixes, terwijl de functiepariteit met de Windows 10 Holographic versie 1809 voor HoloLens (1e generatie) behouden blijft.

Voor ontwikkelaars betekent dit dat HoloLens apps (eerste generatie) de OpenXR-API niet ondersteunen.  Deze headsets blijven ondersteund in Unity 2019 LTS met de WinRT API-back-end voor de volledige levenscyclus van Unity 2019 LTS tot halverwege 2022.

### <a name="windows-10-holographic-version-1809"></a>Windows 10 Holographic versie 1809

> **Van toepassing op:** HoloLens (eerste generatie)

| Functie | Details |
|---|---|
| **Menu Snelle acties** | Wanneer u zich in een app besturingssysteem besturingssysteem gebruikt, wordt met de actie Bloom nu een menu Snelle acties geopend, waarmee u snel toegang hebt tot veelgebruikte systeemfuncties zonder de app te verlaten. <br> Zie [HoloLens in kioskmodus instellen](hololens-kiosk.md) voor informatie over het menu Snelle acties in de kioskmodus.<br><br> |
| **Video-opname stoppen vanuit het menu Start of snelle acties** | Als u video-opname start vanuit Startmenu menu of het menu Snelle acties, kunt u de opname vanaf dezelfde plaats stoppen. (Vergeet niet dat u dit altijd kunt doen met spraakopdrachten.) |
| **Project naar een Miracast apparaat met ingeschakelde functie** | Project uw HoloLens naar een surfaceapparaat of tv/monitor in de buurt als u een Microsoft Display-adapter gebruikt.  Selecteer **bij** Start **Verbinding maken** en selecteer vervolgens het apparaat dat u wilt projecten. **Opmerking:** U kunt een HoloLens voor het gebruik van Miracast projectie zonder de ontwikkelaarsmodus in te schakelen. |
| **Nieuwe meldingen** | Bekijk en reageer op pop-upmeldingen op HoloLens, net als op een pc. Staren om te reageren op of ze te laten weggaan (of als u een in immersieve ervaring hebt, gebruikt u de bloembewegingen). |
| **HoloLens overlays**<br>(bestands kiezen, toetsenbord, dialoogvensters, enzovoort) | U ziet nu overlays, zoals het toetsenbord, dialoogvensters, bestands kiezen, enzovoort bij het gebruik van in immersieve apps. |
| **Visuele feedback overlay UI voor volumewijziging** | Wanneer u de knoppen volume omhoog/omlaag op uw HoloLens ziet u een visuele weergave van het volumeniveau. |
| **Nieuwe gebruikersinterface voor het opstarten van apparaten** | Er is een laadindicator toegevoegd tijdens het opstartproces om visuele feedback te geven dat het systeem laadt. Start het apparaat opnieuw op om de nieuwe laadindicator weer te geven. Deze staat tussen het bericht 'Hallo' en het Windows opstartlogo. |
| **Delen in de buurt** | Toevoeging van de Windows delen in de buurt, zodat u een opname kunt delen met een Windows apparaat. Wanneer u een foto of video op HoloLens vast legt (of de knop Delen gebruikt vanuit een app zoals Microsoft Edge), selecteert u een apparaat in de buurt Windows wilt delen. |
| **Delen vanuit Microsoft Edge** | De knop Delen is nu beschikbaar in Microsoft Edge vensters op HoloLens. Selecteer Microsoft Edge in **het dialoogvenster Delen.** Gebruik de HoloLens om webinhoud te delen. |

#### <a name="for-international-customers"></a>Voor internationale klanten

| Functie | Details |
| --- | --- |
| Gelokaliseerde Chinese en Japanse builds | Gebruik HoloLens gelokaliseerde gebruikersinterface voor vereenvoudigd Chinees of Japans, waaronder gelokaliseerde Pinyin-toetsenbord-, dicteer- en spraakopdrachten.<br>[Meer informatie over het installeren van de Chinese en Japanse versies van HoloLens.](hololens1-install-localized.md) |
| Spraaksynthese (TTS) | De functie voor spraaksynthese ondersteunt nu Chinees, Japans en Engels. |

#### <a name="for-administrators"></a>Voor beheerders

| Functie |  Details  |
|---|----|
| [Inrichting na installatie inschakelen](hololens-provisioning.md) | U kunt nu op elk moment een runtime-inrichtingspakket toepassen met behulp **van Instellingen**. |
| Toegewezen toegang met Azure AD-groepen | U kunt nu Azure AD-groepen gebruiken voor de configuratie van Windows toegewezen toegang om een kioskconfiguratie voor één of meerdere apps in te stellen. |
| Profielsschakelaar voor aanmelden via pincode van aanmeldingsscherm | Aanmelding via pincode is nu beschikbaar voor **Andere gebruiker.** |
| Aanmelden met web-Referentieprovider wachtwoord | U kunt nu de optie Globe-aanmelding selecteren om web-aanmelding met uw wachtwoord te starten. Selecteer in het aanmeldingsscherm **Aanmeldingsopties** en selecteer de optie Wereldbol om de web-aanmelding te starten. Voer indien nodig uw gebruikersnaam in en vervolgens uw wachtwoord. <br>**Opmerking:** U kunt ervoor kiezen om alle opties voor pincodes/smartcards over te nemen wanneer u hier om wordt gevraagd tijdens het aanmelden bij het web. |
| Hardwaregegevens van apparaten lezen via MDM, zodat apparaten kunnen worden gevolgd op serienummer | IT-beheerders kunnen de HoloLens apparaatserienummer in hun MDM-console bekijken en bijhouden. Raadpleeg de MDM-documentatie voor de beschikbaarheid van functies en instructies. |
| Apparaatnaam HoloLens via MDM (naam wijzigen) | IT-beheerders kunnen de naam van HoloLens zien en wijzigen in hun MDM-console. Raadpleeg de MDM-documentatie voor de beschikbaarheid van functies en instructies. |

### <a name="windows-10-version-1803-for-microsoft-hololens"></a>Windows 10 versie 1803 voor Microsoft HoloLens

> **Van toepassing op:** HoloLens (eerste generatie)

Windows 10 versie 1803 is de eerste functie-update voor Windows Holographic for Business sinds de release in Windows 10 versie 1607. Deze update introduceert de volgende wijzigingen:

- Voorheen kon u alleen controleren of de upgradelicentie voor Commercial Suite was toegepast op uw HoloLens-apparaat door te controleren of VPN een beschikbare optie was op het apparaat. Nu wordt **Instellingen**  >  **systeem** weergegeven nadat **Windows Holographic for Business** upgradelicentie is toegepast. [Meer informatie over het ontgrendelen Windows Holographic for Business functies](hololens1-upgrade-enterprise.md).

- U kunt het buildnummer van het besturingssysteem weergeven in apparaateigenschappen in de Bestandenverkenner-app en in [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq).
- Het inrichten van HoloLens apparaat is nu eenvoudiger met de nieuwe **wizard** Apparaten HoloLens inrichten in het hulpprogramma Windows Configuration Designer. In de wizard kunt u de installatie-ervaring en netwerkverbindingen configureren, de ontwikkelaarsmodus instellen en bulksgewijze Azure AD-tokens verkrijgen. [Meer informatie over het gebruik van de eenvoudige inrichtingswizard voor HoloLens](hololens-provisioning.md#provisioning-package-hololens-wizard).

- Wanneer u een lokaal account in een inrichtingspakket maakt, verloopt het wachtwoord niet langer om de 42 dagen.

- U kunt deze HoloLens als kiosk voor één app of [voor meerdere apps.](hololens-kiosk.md) Met de kioskmodus voor meerdere apps kunt u een HoloLens om alleen de apps uit te voeren die u opgeeft, en voorkomt u dat gebruikers wijzigingen aanbrengen.

- Media Transfer Protocol (MTP) is ingeschakeld, zodat u het HoloLens-apparaat via USB kunt verbinden met een pc en bestanden tussen HoloLens en de pc kunt overdragen. U kunt ook de bestandenverkenner-app gebruiken om bestanden te verplaatsen en te verwijderen vanuit HoloLens.

- Eerder moest u, nadat u zich bij het apparaat hebt aangemeld met een Azure Active Directory-account (Azure AD), werktoegang toevoegen **in** **Instellingen** om toegang te krijgen tot bedrijfsresources. Nu meldt u zich aan met een Azure AD-account en vindt de inschrijving automatisch plaats.

- Voordat u zich aanmelden, kunt u het netwerkpictogram onder het wachtwoordveld kiezen om een ander netwerk Wi-Fi verbinding te maken. U kunt ook verbinding maken met een gastnetwerk, zoals in een hotel, conferentiecentrum of bedrijf.

- U kunt nu eenvoudig [een HoloLens met meerdere personen met behulp](hololens-multiple-users.md) van Azure AD-accounts.

- Wanneer het instellen of aanmelden mislukt, kiest u de nieuwe optie **Gegevens verzamelen** om diagnostische logboeken op te halen voor probleemoplossing.

- Afzonderlijke gebruikers kunnen hun zakelijke e-mail synchroniseren zonder hun apparaat in te schrijven bij Mobile Device Management (MDM). U kunt het apparaat gebruiken met een Microsoft-account, de Mail-app downloaden en installeren en rechtstreeks een e-mailaccount toevoegen.

- U kunt de MDM-synchronisatiestatus voor een apparaat controleren in **Instellingen**  >  **Accounts**  >  **Access Work or School**  >  **Info**. In de **sectie Apparaatsynchronisatiestatus** kunt u een synchronisatie starten, gebieden bekijken die worden beheerd door MDM en een geavanceerd diagnostisch rapport maken en exporteren.
