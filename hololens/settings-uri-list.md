---
title: Zichtbaarheid Instellingen pagina's
description: Blijf op de hoogte van onze lijst met ondersteunde URI's voor PageVisibilityList en guide op HoloLens mixed reality apparaten.
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
ms.openlocfilehash: d2747da37ae198f7a2c051593da3ffd4cb4476dfaa7a3078a7749fa1fc912ba2
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/05/2021
ms.locfileid: "115665621"
---
# <a name="page-settings-visibility"></a>Zichtbaarheid Instellingen pagina's

Een van de beheerbare functies voor HoloLens-apparaten is het gebruik van het [Instellingen/PageVisibilityList-beleid](/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) om de pagina's te beperken die worden weergegeven in de Instellingen app. PageVisibilityList is een beleid waarmee IT-beheerders kunnen voorkomen dat specifieke pagina's in de System Instellingen-app zichtbaar of toegankelijk zijn, of om dit te doen voor alle pagina's behalve de pagina's die zijn opgegeven.

> [!NOTE]
> Deze functie is alleen beschikbaar in [Windows Holographic versie 20H2](hololens-release-notes.md#windows-holographic-version-20h2) of hoger voor HoloLens 2 apparaten. Zorg ervoor dat de apparaten voor wie u deze wilt gebruiken, zijn bijgewerkt.


## <a name="examples"></a>Voorbeelden
Pagina's worden aangeduid met een verkorte versie van de gepubliceerde URI's. Dit is de URI min het voorvoegsel 'ms-settings:'.

In het volgende voorbeeld ziet u een beleid waarmee alleen toegang kan worden toegestaan tot de pagina's about en Bluetooth, die respectievelijk URI 'network-wifi' en 'bluetooth' hebben:
- `showonly:network-wifi;network-proxy;bluetooth`

In het volgende voorbeeld ziet u een beleid dat de pagina Voor het opnieuw instellen van het besturingssysteem verbergt:
- `hide:reset`


## <a name="deploying-this-policy-via-intune"></a>Dit beleid implementeren via Intune

Dit zijn de configuratiewaarden die worden opgegeven voor Intune:

- **Naam:** Een door de beheerder gewenste weergavenaam voor het profiel.
- **OMA-URI:** De volledig gekwalificeerde URI van de instellingspagina, inclusief het [bereik](/windows/client-management/mdm/policy-configuration-service-provider). In deze voorbeelden op deze pagina wordt het bereik `./Device` gebruikt.
- **Waarde:** Een tekenreekswaarde die aangeeft of alleen de *opgegeven* pagina's moeten worden verborgen of weergegeven. Mogelijke waarden zijn `hide:<pagename>` en `showonly:<pagename>` . 
 
U kunt meerdere pagina's specificeren door ze te scheiden met een puntkomma. Hieronder vindt u een lijst met algemene pagina's.

1. Maak een **aangepast beleid.**
1. Bij het instellen van **de OMA-URI** voert u de URI met volledig bereik in. Bijvoorbeeld: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**
1. Kies bij het selecteren van de gegevens kiezen: **Tekenreeks**
1. Gebruik de **bovenstaande richtlijnen wanneer** u Waarde opgeeft. Bijvoorbeeld: **`showonly:network-wifi;network-proxy;bluetooth`** of **`hide:reset`** 
> [!IMPORTANT]
> Zorg ervoor dat u de aangepaste apparaatconfiguratie toewijst aan een groep waarin het apparaat is bedoeld. Als deze stap niet wordt uitgevoerd, wordt het beleid gep pusht, maar niet toegepast.

Zie [HoloLens MDM-configuratie](hololens-mdm-configure.md) voor meer informatie over Intune-groepen en apparaatconfiguraties.


## <a name="deploying-this-policy-via-a-provisioning-package"></a>Dit beleid implementeren via een inrichtingspakket

Dit zijn de configuratiewaarden die worden opgegeven in Windows Configuration Designer:

**Waarde:** Een tekenreekswaarde die aangeeft of alleen de *opgegeven* pagina's moeten worden verborgen of weergegeven. Mogelijke waarden zijn `hide:<pagename>` en `showonly:<pagename>` . U kunt meerdere pagina's specificeren door ze te scheiden met een puntkomma. Hieronder vindt u een lijst met algemene pagina's.


1. Tijdens het maken van uw pakket in Windows Configuration Designer naar **Beleidsregels > Instellingen > PageVisibilityList**
1. Voer de tekenreeks in: **`showonly:network-wifi;network-proxy;bluetooth`**
1. Exporteert u uw inrichtingspakket.
1. Pas het pakket toe op uw apparaat.
Ga naar de pagina HoloLens inrichting voor meer informatie over het maken en toepassen [van een inrichtingspakket.](hololens-provisioning.md)


Ongeacht de gekozen methode moet uw apparaat nu de wijzigingen ontvangen en krijgen gebruikers de volgende Instellingen app.

![Schermopname van actieve uren die worden gewijzigd in de Instellingen app](images/hololens-page-visibility-list.jpg)

Als u de pagina'Instellingen-app wilt configureren om uw eigen selectie pagina's weer te geven of te verbergen, bekijkt u de Instellingen URI's die beschikbaar zijn op HoloLens.

## <a name="settings-uris"></a>Instellingen Uris

HoloLens apparaten en Windows 10 apparaten hebben een andere selectie pagina's in de Instellingen app. Op deze pagina vindt u alleen de instellingen die op deze pagina HoloLens.

### <a name="accounts"></a>Accounts
| Pagina Instellingen           | URI                                            |
|-------------------------|------------------------------------------------|
| Werk- of schoolaccount openen | `workplace`                         |
| Iris-inschrijving       | `signinoptions-launchirisenrollment` |
| Aanmeldingsopties         | ` signinoptions `                   |

### <a name="apps"></a>Apps
| Pagina Instellingen | URI                          |
|---------------|------------------------------|
| Apps & functies <sup>2</sup>     | `appsfeatures` <br> |
| Apps & functies > Geavanceerde opties <sup>2</sup>     | `appsfeatures-app` <br> |
| Apps & functies > Offline Kaarten <sup>2</sup>     | `maps-maps` <br> |
| Apps & functies > Offline Kaarten > Download maps <sup>2</sup>     | `maps-downloadmaps` <br> |

### <a name="devices"></a>Apparaten
| Pagina Instellingen | URI                          |
|---------------|------------------------------|
| Bluetooth     | `bluetooth` <br> `connecteddevices` |
| Muis <sup>2</sup>      | `mouse` <br>  |
| USB <sup>2</sup>      | `usb` <br>  |

### <a name="privacy"></a>Privacy
| Pagina Instellingen            | URI                                             |
|--------------------------|-------------------------------------------------|
| Accountgegevens             | `privacy-accountinfo`              |
| App Diagnostics        | `privacy-appdiagnostics`              |
| Achtergrond-apps        | `privacy-backgroundapps`              |
| Kalender                 | `privacy-calendar`                    |
| Oproepgeschiedenis             | `privacy-callhistory`                 |
| Camera                   | `privacy-webcam`                      |
| Contactpersonen                 | `privacy-contacts`                    |
| Feedback over diagnostische & | `privacy-feedback`                    |
| Documenten                | `privacy-documents`                   |
| E-mail                    | `privacy-email`                       |
| Bestandssysteem              | `privacy-broadfilesystemaccess`       |
| Algemeen <sup>2</sup>             | `privacy-general`       |
| Ink-& te typen <sup>2</sup>             | `privacy-speechtyping`       |
| Locatie                 | `privacy-location`                    |
| Berichten                | `privacy-messaging`                   |
| Microfoon               | `privacy-microphone`                  |
| Beweging <sup>2</sup>               | `privacy-motion`                  |
| Meldingen            | `privacy-notifications`               |
| Andere apparaten            | `privacy-customdevices`               |
| Afbeeldingen                 | `privacy-pictures`                    |
| Radios                   | `privacy-radios`                      |
| Schermopname van randen <sup>2</sup>             | `privacy-graphicsCaptureWithoutBorder`       |
| Schermopnamen en apps <sup>2</sup>             | `privacy-graphicsCaptureProgrammatic`       |
| Spraak                   | `privacy-speech`                      |
| Taken                    | `privacy-tasks`                       |
| Gebruikersverloop           | `privacy-backgroundspatialperception` |
| Video's                   | `privacy-videos`                      |
| Spraakactivering       | `privacy-voiceactivation`             |

### <a name="network--internet"></a>Netwerk en internet
| Pagina Instellingen | URI                              |
|---------------|----------------------------------|
| Vliegtuigmodus <sup>2</sup> | `network-airplanemode`        |
| Proxy | `network-proxy`        |
| VPN   | `network-vpn`          |
| Wi-Fi  | `network-wifi`<br>`network-wifisettings`<br>`network-status`<br>`wifi-provisioning`    |



### <a name="system"></a>Systeem
| Pagina Instellingen      | URI                                |
|--------------------|------------------------------------|
| Accu <sup>2</sup>           | `batterysaver`<br>|
| Accu <sup>2</sup>           | `batterysaver-settings`<br>|
| Kleuren             | `colors`<br>`personalization-colors` |
| Hologrammen <sup>2</sup>  |  `holograms`  |
| <sup>Kalibratie 2</sup> |  `calibration` |
| Meldingen & acties  | `notifications`          |
| Gedeelde ervaringen | `crossdevice` 
| Geluid <sup>2</sup>           | `sound`<br>|
| Geluidsvolume > app-volume en apparaatvoorkeur <sup>2</sup>           | `apps-volume`<br>|
| Geluidsapparaten > geluidsapparaten beheren <sup>2</sup>           | `sound-devices`<br>|
| Storage            | `storagesense`           |
| Storage > Sense 2 Storage <sup>configureren</sup>           | `storagepolicies`<br>|

### <a name="time--language"></a>Time & Language
| Pagina Instellingen | URI                                           |
|---------------|-----------------------------------------------|
| Datum & tijd <sup>2</sup> | `dateandtime`                  |
| Toetsenbord <sup>2</sup> | `keyboard`                  |
| Taal <sup>2</sup> | `language`                  |
| Taal <sup>2</sup> | `regionlanguage-languageoptions`                  |
| Taal      | `regionlanguage`<br>`regionlanguage-adddisplaylanguage`<br>`regionlanguage-setdisplaylanguage` |
| Region        | `regionformatting`                  |

### <a name="update--security"></a>Beveiliging & bijwerken
| Pagina Instellingen                         | URI                                       |
|---------------------------------------|-------------------------------------------|
| Geavanceerde opties                    | `windowsupdate-options`         |
| Herstel & opnieuw <sup>instellen 2</sup>      | `reset`         |
| Windows Insider-programma               | `windowsinsider` <br>`windowsinsider-optin`          |
| Windows Update                        | `windowsupdate`<br> `windowsupdate-activehours`  <br> `windowsupdate-history` <br> `windowsupdate-optionalupdates` <br><sup>1</sup>`windowsupdate-options`<br><sup>1</sup>`windowsupdate-restartoptions` |
| Windows Update: controleert op updates | `windowsupdate-action`          |


- <sup>1:</sup> voor versies vóór Windows Holographic, versie 21H1, gaan de volgende  twee URI's niet daadwerkelijk naar de pagina's Geavanceerde opties of **Opties;** Ze blokkeren of tonen alleen de hoofdpagina Windows Update.
  -  windowsupdate-options
  -  windowsupdate-restartoptions

- <sup>2</sup> : beschikbaar in Windows Holographic 21H1 of hoger.


Ga voor een volledige lijst met Windows 10 Instellingen-URI's naar de [documentatie voor startinstellingen.](/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference)
