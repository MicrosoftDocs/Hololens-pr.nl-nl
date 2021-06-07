---
title: Releasenotities voor HoloLens 1 (gen)
description: Meer informatie over updates in elke nieuwe HoloLens-release.
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
ms.sourcegitcommit: 35e180e09e3938c25e4cac8e99885d7e57fa4dad
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/20/2021
ms.locfileid: "111377760"
---
# <a name="hololens-1st-gen-release-notes"></a>Releasenotities voor HoloLens 1 (gen)

## <a name="hololens-1st-gen-long-term-servicing"></a>Langetermijnservice van HoloLens (1e generatie)
HoloLens (1e generatie) is lts-status (Long Term Servicing). Toekomstige updates richten zich op problemen en beveiligingsfixes, terwijl de functiepariteit met de Windows 10 Holographic versie 1809 voor HoloLens (1e generatie) behouden blijft.

Voor ontwikkelaars betekent dit dat HoloLens-apps (eerste generatie) de OpenXR-API niet ondersteunen.  Deze headsets blijven ondersteund in Unity 2019 LTS met de WinRT API-back-end voor de volledige levenscyclus van Unity 2019 LTS tot halverwege 2022.

### <a name="windows-10-holographic-version-1809"></a>Windows 10 Holographic versie 1809

> **Van toepassing op:** HoloLens (1e generatie)

| Functie | Details |
|---|---|
| **Menu Snelle acties** | Wanneer u zich in een app besturingssysteem besturingssysteem gebruikt, wordt met de actie Bloom nu een menu Snelle acties geopend, waarmee u snel toegang hebt tot veelgebruikte systeemfuncties zonder de app te verlaten. <br> Zie [HoloLens instellen in kioskmodus](hololens-kiosk.md) voor informatie over het menu Snelle acties in de kioskmodus.<br><br> |
| **Video-opname stoppen vanuit het menu Start of snelle acties** | Als u video-opname start vanuit Startmenu menu of het menu Snelle acties, kunt u de opname vanaf dezelfde plaats stoppen. (Vergeet niet dat u dit altijd kunt doen met spraakopdrachten.) |
| **Project naar een Miracast-apparaat** | Projecter uw HoloLens-inhoud naar een surfaceapparaat of tv/monitor in de buurt als u een Microsoft Display-adapter gebruikt.  Selecteer **op Start** de optie **Verbinding** maken en selecteer vervolgens het apparaat dat u wilt projecten. **Opmerking:** U kunt HoloLens implementeren om Miracast-projectie te gebruiken zonder de ontwikkelaarsmodus in te schakelen. |
| **Nieuwe meldingen** | Bekijk en reageer op pop-upmeldingen op HoloLens, net zoals u dat op een pc doet. Staren om te reageren op of te laten weggaan (of als u een in immersieve ervaring hebt, gebruikt u de bloembewegingen). |
| **HoloLens-overlays**<br>(bestands kiezen, toetsenbord, dialoogvensters, enzovoort) | U ziet nu overlays, zoals het toetsenbord, dialoogvensters, bestands kiezen, enzovoort bij het gebruik van in immersieve apps. |
| **Visuele feedback overlay UI voor volumewijziging** | Wanneer u de knoppen volume omhoog/omlaag op uw HoloLens gebruikt, ziet u een visuele weergave van het volumeniveau. |
| **Nieuwe gebruikersinterface voor het opstarten van apparaten** | Er is een laadindicator toegevoegd tijdens het opstartproces om visuele feedback te geven dat het systeem laadt. Start het apparaat opnieuw op om de nieuwe laadindicator weer te geven. Deze staat tussen het bericht 'Hallo' en het Windows-opstartlogo. |
| **Delen in de buurt** | Daarnaast kunt u windows in de buurt delen, zodat u een opname kunt delen met een windows-apparaat in de buurt. Wanneer u een foto of video op HoloLens vast legt (of de knop Delen gebruikt vanuit een app zoals Microsoft Edge), selecteert u een Windows-apparaat in de buurt om mee te delen. |
| **Delen vanuit Microsoft Edge** | De knop Delen is nu beschikbaar in Microsoft Edge op HoloLens. Selecteer Microsoft Edge in **het dialoogvenster Delen.** Gebruik de HoloLens-share- picker om webinhoud te delen. |

#### <a name="for-international-customers"></a>Voor internationale klanten

| Functie | Details |
| --- | --- |
| Gelokaliseerde Chinese en Japanse builds | Gebruik HoloLens met gelokaliseerde gebruikersinterface voor vereenvoudigd Chinees of Japans, inclusief gelokaliseerde Pinyin-toetsenbord-, dicteer- en spraakopdrachten.<br>[Meer informatie over het installeren van de Chinese en Japanse versies van HoloLens.](hololens1-install-localized.md) |
| Spraaksynthese (TTS) | De functie voor spraaksynthese ondersteunt nu Chinees, Japans en Engels. |

#### <a name="for-administrators"></a>Voor beheerders

| Functie |  Details  |
|---|----|
| [Inrichting na installatie inschakelen](hololens-provisioning.md) | U kunt nu op elk moment een runtime-inrichtingspakket toepassen met behulp van **Instellingen.** |
| Toegewezen toegang met Azure AD-groepen | U kunt nu Azure AD-groepen gebruiken voor de configuratie van door Windows toegewezen toegang om een kioskconfiguratie voor één of meerdere apps in te stellen. |
| Profielsschakelaar voor aanmelden via pincode van aanmeldingsscherm | Aanmelding via pincode is nu beschikbaar voor **Andere gebruiker.** |
| Aanmelden met web-Referentieprovider wachtwoord | U kunt nu de optie Globe-aanmelding selecteren om web-aanmelding met uw wachtwoord te starten. Selecteer in het aanmeldingsscherm **Aanmeldingsopties** en selecteer de optie Wereldbol om de web-aanmelding te starten. Voer indien nodig uw gebruikersnaam in en vervolgens uw wachtwoord. <br>**Opmerking:** U kunt ervoor kiezen om alle opties voor pincodes/smartcards over te nemen wanneer u hier om wordt gevraagd tijdens het aanmelden bij het web. |
| Hardwaregegevens van apparaten lezen via MDM, zodat apparaten kunnen worden gevolgd op serienummer | IT-beheerders kunnen HoloLens zien en volgen op serienummer van het apparaat in hun MDM-console. Raadpleeg de MDM-documentatie voor de beschikbaarheid van functies en instructies. |
| HoloLens-apparaatnaam instellen via MDM (naam wijzigen) | IT-beheerders kunnen HoloLens-apparaten in hun MDM-console bekijken en de naam ervan wijzigen. Raadpleeg de MDM-documentatie voor de beschikbaarheid van functies en instructies. |

### <a name="windows-10-version-1803-for-microsoft-hololens"></a>Windows 10 versie 1803 voor Microsoft HoloLens

> **Van toepassing op:** HoloLens (1e generatie)

Windows 10 versie 1803 is de eerste functie-update voor Windows Holographic for Business sinds de release in Windows 10 versie 1607. Deze update introduceert de volgende wijzigingen:

- Voorheen kon u alleen controleren of de upgradelicentie voor Commercial Suite was toegepast op uw HoloLens-apparaat door te controleren of VPN een beschikbare optie was op het apparaat. Instellingensysteem   >  **wordt** nu  weergegeven Windows Holographic for Business de upgradelicentie is toegepast. [Meer informatie over het ontgrendelen Windows Holographic for Business functies](hololens1-upgrade-enterprise.md).

- U kunt het buildnummer van het besturingssysteem weergeven in apparaateigenschappen in de Bestandenverkenner-app en in [de Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq).
- Het inrichten van een HoloLens-apparaat is nu eenvoudiger met de nieuwe wizard **HoloLens-apparaten** inrichten in het hulpprogramma Windows Configuration Designer. In de wizard kunt u de installatie-ervaring en netwerkverbindingen configureren, de ontwikkelaarsmodus instellen en bulksgewijze Azure AD-tokens verkrijgen. [Meer informatie over het gebruik van de eenvoudige inrichtingswizard voor HoloLens](hololens-provisioning.md#provisioning-package-hololens-wizard).

- Wanneer u een lokaal account in een inrichtingspakket maakt, verloopt het wachtwoord niet langer om de 42 dagen.

- U kunt [HoloLens configureren als kiosk voor één app](hololens-kiosk.md)of voor meerdere apps. Met de kioskmodus voor meerdere apps kunt u een HoloLens instellen om alleen de apps uit te voeren die u opgeeft, en voorkomt u dat gebruikers wijzigingen aanbrengen.

- Media Transfer Protocol (MTP) is ingeschakeld, zodat u het HoloLens-apparaat via USB kunt verbinden met een pc en bestanden tussen HoloLens en de pc kunt overdragen. U kunt de verkenner-app ook gebruiken om bestanden te verplaatsen en te verwijderen vanuit HoloLens.

- Eerder moest u, nadat u zich bij het apparaat hebt aangemeld met een Azure Active Directory-account (Azure AD), werktoegang toevoegen **in** Instellingen om toegang te krijgen tot bedrijfsresources.  Nu meldt u zich aan met een Azure AD-account en vindt de inschrijving automatisch plaats.

- Voordat u zich aanmelden, kunt u het netwerkpictogram onder het wachtwoordveld kiezen om een ander netwerk Wi-Fi verbinding te maken. U kunt ook verbinding maken met een gastnetwerk, zoals in een hotel, conferentiecentrum of bedrijf.

- U kunt [HoloLens nu eenvoudig delen met meerdere personen met behulp](hololens-multiple-users.md) van Azure AD-accounts.

- Wanneer het instellen of aanmelden mislukt, kiest u de nieuwe optie **Gegevens verzamelen** om diagnostische logboeken op te halen voor probleemoplossing.

- Afzonderlijke gebruikers kunnen hun zakelijke e-mail synchroniseren zonder hun apparaat te registreren bij Mobile Device Management (MDM). U kunt het apparaat gebruiken met een Microsoft-account, de Mail-app downloaden en installeren en rechtstreeks een e-mailaccount toevoegen.

- U kunt de MDM-synchronisatiestatus voor een apparaat controleren in  >  **InstellingenAccounts**  >  **Toegang tot werk- of**  >  **schoolgegevens.** In de **sectie Apparaatsynchronisatiestatus** kunt u een synchronisatie starten, gebieden bekijken die worden beheerd door MDM en een geavanceerd diagnostisch rapport maken en exporteren.
