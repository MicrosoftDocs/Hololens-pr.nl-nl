---
title: Zichtbaarheid van pagina-instellingen
description: Blijf op de hoogte van onze lijst met ondersteunde URI's voor PageVisibilityList en Guide on HoloLens mixed reality apparaten.
author: evmill
ms.author: v-evmill
ms.date: 10/13/2020
ms.topic: article
keywords: hololens, hololens 2, toegewezen toegang, kiosk, instellingenpagina
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: widuff
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: b5779ffa1de1700b4fcd17fc17b8ae3a82a45c22
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/25/2021
ms.locfileid: "111379413"
---
# <a name="page-settings-visibility"></a>Zichtbaarheid van pagina-instellingen

Een van de beheerbare functies voor HoloLens-apparaten is het gebruik van het beleid [Instellingen/PaginaVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) om de pagina's in de app Instellingen te beperken. PageVisibilityList is een beleid waarmee IT-beheerders kunnen voorkomen dat specifieke pagina's in de app Systeeminstellingen zichtbaar of toegankelijk zijn, of om dit te doen voor alle pagina's behalve de pagina's die zijn opgegeven.

> [!NOTE]
> Deze functie is alleen beschikbaar in [Windows Holographic, versie 20H2](hololens-release-notes.md#windows-holographic-version-20h2) of hoger voor HoloLens 2 apparaten. Zorg ervoor dat de apparaten voor wie u deze wilt gebruiken, zijn bijgewerkt.

In het volgende voorbeeld ziet u een beleid dat alleen toegang toestaat tot de pagina's about en Bluetooth, die respectievelijk URI 'ms-settings:network-wifi' en 'ms-settings:bluetooth' hebben:
- `showonly:network-wifi;network-proxy;bluetooth`

Dit instellen via een inrichtingspakket:

1. Navigeer tijdens het maken van uw pakket in Windows Configuration Designer **naar Beleidsregels > instellingen > PageVisibilityList**
1. Voer de tekenreeks in: **`showonly:network-wifi;network-proxy;bluetooth`**
1. Exporteert u uw inrichtingspakket.
1. Pas het pakket toe op uw apparaat.
Ga naar deze pagina voor meer informatie over het maken en toepassen van een [inrichtingspakket.](hololens-provisioning.md)

U kunt dit doen via Intune met oma-URI:

1. Maak een **aangepast beleid.**
1. Gebruik de tekenreeks bij het instellen van de OMA-URI: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**
1. Kies bij het selecteren van de gegevens kiezen: **Tekenreeks**
1. Wanneer u de waarde typt, gebruikt u: **`showonly:network-wifi;network-proxy;bluetooth`**
1. Zorg ervoor dat u de aangepaste apparaatconfiguratie toewijst aan een groep waarin het apparaat is bedoeld.

Zie [HoloLens MDM-configuratie](hololens-mdm-configure.md) voor meer informatie over Intune-groepen en apparaatconfiguraties.

Ongeacht de gekozen methode moet uw apparaat nu de wijzigingen ontvangen en krijgen gebruikers de volgende instellingen-app te zien.

![Schermopname van actieve uren die worden gewijzigd in de app Instellingen](images/hololens-page-visibility-list.jpg)

Als u de app-pagina's Instellingen wilt configureren om uw eigen selectie pagina's weer te geven of te verbergen, bekijkt u de instellingen-URI's die beschikbaar zijn op HoloLens.

## <a name="settings-uris"></a>Instellingen-URI's

HoloLens-apparaten Windows 10 apparaten hebben een andere selectie pagina's in de app Instellingen. Op deze pagina vindt u alleen de instellingen die aanwezig zijn op HoloLens.

### <a name="accounts"></a>Accounts
| Pagina Instellingen           | URI                                            |
|-------------------------|------------------------------------------------|
| Werk- of schoolaccount openen | `ms-settings:workplace`                         |
| Iris-inschrijving       | `ms-settings:signinoptions-launchirisenrollment` |
| Aanmeldingsopties         | ` ms-settings:signinoptions `                   |

### <a name="apps"></a>Apps
| Pagina Instellingen | URI                          |
|---------------|------------------------------|
| Apps & functies<sup>2</sup>     | `ms-settings:appsfeatures` <br> |
| Apps & functies > Geavanceerde opties <sup>2</sup>     | `ms-settings::appsfeatures-app` <br> |
| Apps & functies > Offline Maps <sup>2</sup>     | `ms-settings:maps-maps` <br> |
| Apps & functies > Offline maps > Download maps <sup>2</sup>     | `ms-settings:maps-downloadmaps` <br> |

### <a name="devices"></a>Apparaten
| Pagina Instellingen | URI                          |
|---------------|------------------------------|
| Bluetooth     | `ms-settings:bluetooth` <br> `ms-settings:connecteddevices` |
| Muis <sup>2</sup>      | `ms-settings:mouse` <br>  |
| USB <sup>2</sup>      | `ms-settings:usb` <br>  |

### <a name="privacy"></a>Privacy
| Pagina Instellingen            | URI                                             |
|--------------------------|-------------------------------------------------|
| Accountgegevens             | `ms-settings:privacy-accountinfo`              |
| App Diagnostics        | `ms-settings:privacy-appdiagnostics`              |
| Achtergrond-apps        | `ms-settings:privacy-backgroundapps`              |
| Kalender                 | `ms-settings:privacy-calendar`                    |
| Oproepgeschiedenis             | `ms-settings:privacy-callhistory`                 |
| Camera                   | `ms-settings:privacy-webcam`                      |
| Contactpersonen                 | `ms-settings:privacy-contacts`                    |
| Feedback over diagnostische & | `ms-settings:privacy-feedback`                    |
| Documenten                | `ms-settings:privacy-documents`                   |
| E-mail                    | `ms-settings:privacy-email`                       |
| Bestandssysteem              | `ms-settings:privacy-broadfilesystemaccess`       |
| Algemeen <sup>2</sup>             | `ms-settings:privacy-general`       |
| Ink-& te typen <sup>2</sup>             | `ms-settings:privacy-speechtyping`       |
| Locatie                 | `ms-settings:privacy-location`                    |
| Berichten                | `ms-settings:privacy-messaging`                   |
| Microfoon               | `ms-settings:privacy-microphone`                  |
| Beweging <sup>2</sup>               | `ms-settings:privacy-motion`                  |
| Meldingen            | `ms-settings:privacy-notifications`               |
| Andere apparaten            | `ms-settings:privacy-customdevices`               |
| Afbeeldingen                 | `ms-settings:privacy-pictures`                    |
| Radios                   | `ms-settings:privacy-radios`                      |
| Schermopname van randen <sup>2</sup>             | `ms-settings:privacy-graphicsCaptureWithoutBorder`       |
| Schermopnamen en apps <sup>2</sup>             | `ms-settings:privacy-graphicsCaptureProgrammatic`       |
| Spraak                   | `ms-settings:privacy-speech`                      |
| Taken                    | `ms-settings:privacy-tasks`                       |
| Gebruikersverloop           | `ms-settings:privacy-backgroundspatialperception` |
| Video's                   | `ms-settings:privacy-videos`                      |
| Spraakactivering       | `ms-settings:privacy-voiceactivation`             |

### <a name="network--internet"></a>Netwerk en internet
| Pagina Instellingen | URI                              |
|---------------|----------------------------------|
| Vliegtuigmodus <sup>2</sup> | `ms-settings:network-airplanemode`        |
| Proxy | `ms-settings:network-proxy`        |
| VPN   | `ms-settings:network-vpn`          |
| Wi-Fi  | `ms-settings:network-wifi`<br>`ms-settings:network-wifisettings`<br>`ms-settings:network-status`<br>`ms-settings:wifi-provisioning`    |



### <a name="system"></a>Systeem
| Pagina Instellingen      | URI                                |
|--------------------|------------------------------------|
| Accu <sup>2</sup>           | `ms-settings:batterysaver`<br>|
| Accu <sup>2</sup>           | `ms-settings:batterysaver-settings`<br>|
| Kleuren             | `ms-settings:colors`<br>`ms-settings:personalization-colors` |
| Hologrammen <sup>2</sup>  |  `ms-settings:holograms`  |
| <sup>Kalibratie 2</sup> |  `ms-settings:calibration` |
| Meldingen & acties  | `ms-settings:notifications`          |
| Gedeelde ervaringen | `ms-settings:crossdevice` 
| Geluid <sup>2</sup>           | `ms-settings:sound`<br>|
| Geluidsvolume > app-volume en apparaatvoorkeur <sup>2</sup>           | `ms-settings:apps-volume`<br>|
| Geluidsapparaten > beheren <sup>2</sup>           | `ms-settings:sound-devices`<br>|
| Storage            | `ms-settings:storagesense`           |
| Storage > Configue Opslaginzicht <sup>2</sup>           | `ms-settings:storagepolicies`<br>|

### <a name="time--language"></a>Time & Language
| Pagina Instellingen | URI                                           |
|---------------|-----------------------------------------------|
| Datum & tijd <sup>2</sup> | `ms-settings:dateandtime`                  |
| Toetsenbord <sup>2</sup> | `ms-settings:keyboard`                  |
| Taal <sup>2</sup> | `ms-settings:language`                  |
| Taal <sup>2</sup> | `ms-settings:regionlanguage-languageoptions`                  |
| Taal      | `ms-settings:regionlanguage`<br>`ms-settings:regionlanguage-adddisplaylanguage`<br>`ms-settings:regionlanguage-setdisplaylanguage` |
| Region        | `ms-settings:regionformatting`                  |

### <a name="update--security"></a>Beveiliging & bijwerken
| Pagina Instellingen                         | URI                                       |
|---------------------------------------|-------------------------------------------|
| Geavanceerde opties                    | `ms-settings:windowsupdate-options`         |
| Herstel & opnieuw <sup>instellen 2</sup>      | `ms-settings:reset`         |
| Windows Insider-programma               | `ms-settings:windowsinsider` <br>`ms-settings:windowsinsider-optin`          |
| Windows Update                        | `ms-settings:windowsupdate`<br> `ms-settings:windowsupdate-activehours`  <br> `ms-settings:windowsupdate-history` <br> `ms-settings:windowsupdate-optionalupdates` <br><sup>1</sup>`ms-settings:windowsupdate-options`<br><sup>1</sup>`ms-settings:windowsupdate-restartoptions` |
| Windows Update: controleert op updates | `ms-settings:windowsupdate-action`          |


>  <sup>1</sup> Voor versies vóór Windows Holographic, versie 21H1, gaan de  volgende twee URI's niet daadwerkelijk naar de pagina's Geavanceerde opties **of** Opties; Ze blokkeren of tonen alleen de hoofdpagina Windows Update pagina.
> - ms-settings:windowsupdate-options
> - ms-settings:windowsupdate-restartoptions
 
> <sup>2:</sup> beschikbaar in Windows Holographic 21H1 of hoger.


Ga voor een volledige lijst met Windows 10 Instellingen-URI's naar de [documentatie voor startinstellingen.](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference)
