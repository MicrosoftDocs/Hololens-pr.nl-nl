---
ms.openlocfilehash: d96a769b40daba0948f8f3c71a88513576c531b5
ms.sourcegitcommit: 6ce962ede986ebfab21d1665722694eaee13c280
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/25/2021
ms.locfileid: "122859207"
---
# <a name="non-aad-configuration"></a>[Niet-AAD-configuratie](#tab/nonaadlogon)

#### <a name="non-aad-configuration"></a>Niet-AAD-configuratie

1. Maak een inrichtingspakket dat:
    1. Hiermee configureert u Runtime-instellingen/AssignedAccess om bezoekersaccounts toe te staan.
    1. Optioneel wordt het apparaat ingeschreven bij MDM (Runtime-instellingen/Werkplek/Registraties), zodat het later kan worden beheerd.
    1. Maak geen lokaal account
2. [Pas het inrichtingspakket toe.](../hololens-provisioning.md)

# <a name="aad-configuration"></a>[AAD-configuratie](#tab/aadlogon)

#### <a name="aad-configuration"></a>AAD-configuratie

AAD-apparaten die zijn geconfigureerd voor de kioskmodus, kunnen zich aanmelden bij een Bezoekers-account met één tik op de knop op het aanmeldingsscherm. Nadat het apparaat is aangemeld bij het bezoekersaccount, wordt het apparaat pas opnieuw gevraagd om zich aan te melden als de bezoekers expliciet is aangemeld bij het startmenu of het apparaat opnieuw is opgestart.

Automatische aanmelding van bezoekers kan worden beheerd via aangepast [OMA-URI-beleid:](/mem/intune/configuration/custom-settings-windows-10)

- URI-waarde: ./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon

| Beleid | Description | Configuraties |
| --------------------------- | ------------- | -------------------- |
| MixedReality/BezoekersAutoLogon | Hiermee kan een bezoekers zich automatisch bij een kiosk laten aanmeldingen. | 1 (Ja), 0 (Nee, standaardinstelling.) |