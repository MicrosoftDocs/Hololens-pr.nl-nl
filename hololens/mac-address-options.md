---
title: Enterprise Enrollment of HoloLens Devices in MAC address restricted Wi-Fi Environment
description: MAC-adres voor netwerk op HoloLens 2 apparaten
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: mata
ms.topic: article
ms.localizationpriority: high
ms.date: 10/01/2020
ms.reviewer: v-evmill
audience: ITPro
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 1be1a8aa021c2a588b120fc9fa148b6c5dafd2840bbefa0d8ea9701751834521
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/05/2021
ms.locfileid: "115665578"
---
# <a name="enterprise-enrollment-of-hololens-devices-in-mac-address-restricted-wi-fi-environment"></a>Enterprise Enrollment of HoloLens Devices in MAC address restricted Wi-Fi Environment

In dit document wordt een veelvoorkomende scenario beschreven dat we hebben geïdentificeerd in klantomgevingen waar de Wi-Fi wordt beperkt door MAC-adressen of certificaten zijn vereist voor draadloze netwerken.

## <a name="example-scenario"></a>Voorbeeldscenario

Veel klanten in beveiligde omgevingen hebben beperkingen voor hun draadloze of bekabelde netwerken waardoor alleen goedgekeurde apparaten (op basis van MAC-adressen) verbinding kunnen maken. Dit kan worden afgedwongen via mac-adresfiltering op een draadloos toegangspunt of via een DHCP-server. Bovendien sommige draadloze netwerken kunnen worden beveiligd met PEAP, waarvoor een certificaat moet worden toegepast op het apparaat vóór de authenticatie op het draadloze netwerk.

In dit scenario kunnen twee belangrijke vereisten vertragingen tot gevolg hebben of handmatige interventie vereisen bij het HoloLens apparaten aan het netwerk:

- Het draadloze PEAP-certificaat moet worden toegepast op het apparaat voordat het apparaat kan worden aangesloten op het draadloze netwerk.
- Het MAC-adres van de HoloLens Wi-Fi adapter moet worden geregistreerd.

De belangrijkste uitdagingen met de bovenstaande vereisten zijn:

1. Het MAC-adres kan momenteel alleen worden geïdentificeerd vanuit de Instellingen-app op het apparaat of vanuit Intune na een geslaagde inschrijving.

2. Zonder het MAC-adres kan het apparaat geen lid worden Wi-Fi netwerk om de inschrijving te starten.

3. Handmatige tijdelijke oplossingen voor deze uitdagingen vereisen dat een technicus met het apparaat communiceert.

## <a name="solutions"></a>Oplossingen

Er zijn veel manieren om deze situatie te verbeteren, afhankelijk van de infrastructuur die beschikbaar is in de omgeving.

| Oplossing | Voordelen | Vereisten |
| --- | --- | --- |
| Inrichtingspakket met Ethernet-adapter | Verbetert de OOBE-ervaring en maakt een snellere techniciervaring mogelijk. | HoloLens compatibele USB-C Hub + Ethernet-adapter, en de technicus moet nog steeds communiceren met het apparaat voor MAC Capture en OOBE-finalisatie |
| Autopilot met Intune-registratie via Ethernet | Dit is een verbinding in één stap en de registratie van het apparaat bij de klantomgeving. MAC-opname kan worden voltooid zonder interactie met het apparaat | Intune ingeschakeld voor de AAD-tenant van de klant en een HoloLens compatibele USB-C Ethernet-adapter |
| Automatische rapportage van MAC-adressen | Wanneer apparaten zijn geregistreerd bij de Intune-tenant, kan een script het MAC-adres rapporteren aan de technicus. | Intune PowerShell-cmdlets |

## <a name="provisioning-package-with-ethernet-adaptor"></a>Inrichtingspakket met Ethernet-adapter

> [!NOTE] 
> Als het bekabelde netwerk ook onderhevig is aan MAC-beperkingen, moet ook het MAC-adres van de USB-C Hub + Ethernet-adapter vooraf worden goedgekeurd. Zorg ervoor dat u deze adapter gebruikt, omdat hiermee toegang tot het netwerk wordt toegestaan vanaf andere apparaten.

### <a name="requirements"></a>Vereisten

- Bekabelde netwerkpoort met toegang tot het klantnetwerk
- HoloLens Compatibele USB-C Hub met Ethernet-adapter: elke adapter waarvoor geen extra stuurprogramma's of toepassings installeren nodig is, moet geschikt zijn.
- Inrichtingspakket met:
  - Informatie over draadloze netwerken en certificaat
  - Optioneel met inschrijvingsgegevens voor De Azure AD van de organisatie
  - Met alle andere vereiste inrichtingsinstellingen

### <a name="process"></a>Proces

Het proces kan variëren, afhankelijk van het softwareniveau van het apparaat. Als het apparaat de update [van mei 2004 heeft,](hololens-release-notes.md#windows-holographic-version-2004)volgt u de onderstaande stappen.

1. Plaats het inrichtingspakket in de hoofdmap van een USB-stick en sluit het aan op de hub.
2. Verbinding maken Ethernetkabel naar de Hub + Ethernet-adapter.
3. Verbinding maken USB-C Hub naar HoloLens apparaat.
4. Schakel de HoloLens in en zet het apparaat op.
5. Druk op **de knop Volume omlaag en Aan/uit om** het inrichtingspakket toe te passen.
6. De technicus kan oobe nu volgen en na het voltooien de Instellingen-app openen om het MAC-adres van het apparaat op te halen.

Als het apparaat een build van het besturingssysteem heeft vóór de update van mei [2004,](hololens-release-notes.md#windows-holographic-version-2004)volgt u de onderstaande stappen.

1. Schakel de HoloLens en sluit het apparaat aan op een pc.
2. Het apparaat moet op de pc worden weer geven als een bestandsopslagapparaat.
3. Het inrichtingspakket naar het apparaat kopiëren
4. Verbinding maken Ethernetkabel naar de hub.
5. Verbinding maken USB-C Hub naar HoloLens apparaat.
6. Plaats de HoloLens
7. Druk op **de knop Volume omlaag en Aan/uit** om het inrichtingspakket toe te passen.
8. De technicus kan oobe nu volgen en na het voltooien de Instellingen-app openen om het MAC-adres van het apparaat op te halen.

### <a name="benefits"></a>Voordelen

Hierdoor kan het apparaat met één toets het juiste inrichtingspakket toepassen en het MAC-adres van het apparaat verzamelen. [Inrichtingspakketten kunnen worden gemaakt volgens de richtlijnen hier.](hololens-provisioning.md)

## <a name="autopilot-with-intune-enrollment"></a>Autopilot met Intune-inschrijving

### <a name="requirements"></a>Vereisten

- Bekabelde netwerkpoort met toegang tot het klantnetwerk
- HoloLens apparaten met Windows Holographic 2004
- HoloLens Compatibele USB-C Ethernet-adapter
- Intune instellen en inschakelen voor de tenant van de klant
- Apparaat geregistreerd voor Autopilot en geïmporteerd in de tenant van de klant
- Intune-beleidsregels die zijn gedefinieerd voor het apparaat:
   - Informatie over draadloze netwerken en certificaat
   - Met alle andere vereiste inrichtingsinstellingen

Hierdoor kan een klant met geavanceerde netwerkvereisten de apparaten inschrijven in een hands-off, schaalbare benadering

Er zijn aanvullende vereisten nodig, zoals hieronder wordt beschreven:
1. [Schakel de tenant in voor de Autopilot-preview.](hololens2-autopilot.md)
1. Maak de HoloLens om het inrichtingspakket in Intune te vervangen.
1. Maak de HoloLens Intune-beleid.
1. Wijs de apparaten toe aan de juiste groep.

### <a name="process"></a>Proces

1. Verbinding maken ethernetkabel naar de adapter en sluit de adapter aan op de USB-C-poort op HoloLens 2 apparaat.

2. Schakel de HoloLens.

3. Het apparaat moet automatisch verbinding maken met internet tijdens OOBE via de Ethernet-adapter. De Autopilot-configuratie moet worden gedetecteerd en automatisch worden geregistreerd bij Azure AD en Intune.

4. Op het apparaat worden de vereiste Wi-Fi certificaten en andere configuratie toegepast, indien nodig via Intune.

5. Als u klaar bent, kan de technicus de Intune-portal (Endpoint Manager) laden en inzoomen op de pagina apparaateigenschappen op **Start ->-apparaten -> DeviceName -> Hardware.**

6. Het Wi-Fi MAC-adres wordt weergegeven in de Intune-portal.

   ![MAC-adres via Intune](images/mac-address-intune.jpg)

7. De technicus voegt dit MAC-adres toe als een toegestaan apparaat.

### <a name="benefits"></a>Voordelen

Hierdoor is een 'Kop-op-kop'-implementatie mogelijk voor de technicus, omdat het apparaat vanaf de doos kan worden ingeschreven bij Azure AD en Intune zonder dat de technicus het apparaat moet dragen of handmatig met de HoloLens-omgeving moet werken.

## <a name="reporting-of-mac-addresses-to-the-technician"></a>Rapportage van MAC-adressen aan de technicus

### <a name="requirements"></a>Vereisten

- Autorisatie van 'Intune Graph PowerShell' voor de tenant van de klant
- Installatie van de Intune Graph PowerShell op de technicimachine.
- [https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0)
- Leestoegang tot de elementen Beheerde apparaten van Intune. (Helpdesk-operator of hoger, of een aangepaste rol)

Er is momenteel geen eenvoudige manier om een automatiseringsopdracht te activeren op basis van de inschrijving van een nieuw apparaat in Intune. Daarom biedt deze opdracht de technicus een eenvoudige manier om het MAC-adres op te halen zonder dat hij zich hoeft aan te melden bij de portal en het handmatig op te halen.

```powershell
Import-Module Microsoft.Graph.Intune

Connect-MSGraph

Get-IntuneManagedDevice -Filter "model eq 'Hololens 2'" | where {$_.enrolledDateTime -gt (get-date).AddDays(-30)}  | select deviceName, wiFiMacAddress 
```

Hiermee worden de naam en het MAC-adres van alle HoloLens die in de afgelopen 30 dagen zijn geregistreerd.

![MAC-adres via PowerShell](images/mac-address-powershell.jpg)

### <a name="process"></a>Proces

Nadat de Intune-inschrijving is voltooid, zou de technicus het bovenstaande script uitvoeren om het MAC-adres op te halen.
