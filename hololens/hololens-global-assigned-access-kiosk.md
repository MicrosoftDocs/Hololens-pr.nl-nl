---
title: Globale toegewezen toegang
description: Ga aan de slag met onze handleiding voor het gebruik van OMA-URI voor globale kiosken voor toegewezen toegang met Intune en Windows Configuration Designer.
author: evmill
ms.author: v-evmill
ms.date: 9/21/2020
ms.topic: article
keywords: hololens, hololens 2, toegewezen toegang, kiosk
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: lavinds
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: d36192e7f65f7fe2ccc7ff8699484a19b3d5d3a7ccab0167d2dbdcaf64bb5880
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/05/2021
ms.locfileid: "115664036"
---
# <a name="global-assigned-access--kiosk"></a>Globale toegewezen toegang – Kiosk

Deze functie configureert HoloLens 2 apparaat voor de kioskmodus voor meerdere apps, die van toepassing is op systeemniveau, heeft geen affiniteit met een identiteit op het systeem en is van toepassing op iedereen die zich bij het apparaat meldt.

> [!NOTE]
> Deze functie is momenteel alleen beschikbaar in Windows Insider-builds. Als u deze functie wilt uitproberen voordat deze algemeen beschikbaar is in HoloLens releases, leest u meer over Windows [Insider-builds.](hololens-insider.md)

## <a name="how-to-use-global-assigned-access-in-intune"></a>Hoe kan ik globale toegewezen toegang gebruiken in Intune?

> [!NOTE]
> Houd rekening met de gebieden die zijn gemarkeerd met '<!-'. Voor deze gebieden moet u wijzigingen aanbrengen op basis van uw voorkeuren.

1. Maak als volgt een aangepast OMA URI-apparaatconfiguratieprofiel en pas dit toe op HoloLens apparaatgroep:

    URI-waarde: ./Device/Vendor/MSFT/AssignedAccess/Configuration

    > [!div class="mx-imgBorder"]
    > ![OMA-URI voor globale toegewezen toegang in Intune](images/global-assigned-access-omauri.png)

2. Werk voor waarde de volgende inhoud bij en plak deze:

    :::code language="xml" source="samples/global-assigned-access.xml" highlight="12-13,23":::

## <a name="how-to-use-global-assigned-access-in-windows-configuration-designer"></a>Globale toegewezen toegang gebruiken in Windows Configuration Designer?

1. Werk de HIERBOVEN genoemde XML-blob bij en sla deze op als XML-bestand. 

2. Volg de stappen in [Use a provisioning package to set up a single-app or multi-app kiosk](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)(Een inrichtingspakket gebruiken om een kiosk voor één app of meerdere apps in te stellen) in het bijzonder de sectie "Prov. package, step 2– Add the kiosk configuration XML file to a provisioning package' (pakket, stap 2: het XML-bestand voor de kioskconfiguratie toevoegen aan een inrichtingspakket) en verwijzen naar het XML-bestand dat in de vorige stap is opgeslagen.

## <a name="can-i-create-a-configuration-where-global-applies-to-everyone-and-separate-configuration-applies-to-1-azure-ad-account-or-azure-ad-group"></a>Kan ik een configuratie maken waarbij globaal van toepassing is op iedereen en afzonderlijke configuratie van toepassing is op 1 Azure AD-account of Azure AD-groep? 

Ja, raadpleeg de voorbeeld-XML-blob hieronder. Het profiel Voor globale toegewezen toegang wordt toegepast op HoloLens wanneer er geen specifiek profiel voor de aangemelde gebruiker wordt gevonden. Dit is dus de standaardconfiguratie voor de kioskmodus voor aangemelde gebruikers.
Hier volgt een voorbeeld van een XML-blob die moet worden gebruikt:

> [!NOTE]
> Houd rekening met de gemarkeerde gebieden die zijn gemarkeerd met `<!-` . Voor deze gebieden moet u wijzigingen aanbrengen op basis van uw voorkeuren.

 :::code language="xml" source="samples/exclude-one-aad-user-or-group.xml" highlight="8,11,17":::

## <a name="excluding-deviceowners-from-global-assigned-access-profile"></a>DeviceOwners uitsluiten van algemeen toegewezen toegangsprofiel

Met deze functie kan een[](security-adminless-os.md)gebruiker die wordt beschouwd als 'Apparaateigenaar' op HoloLens worden uitgesloten van globale toegewezen toegang. Als u wilt profiteren van deze functie, moet u in de XML-blob voor de kioskconfiguratie voor meerdere apps ervoor zorgen dat er gemarkeerde regels worden toegevoegd:

 :::code language="xml" source="samples/exclude-device-owners-from-global.xml" highlight="6,16-18":::

## <a name="additional-global-assigned-access-examples"></a>Aanvullende voorbeelden van globale toegewezen toegang

Dit is een voorbeeld van een kiosk voor globale toegewezen toegang die wanneer een gebruiker zich aan meldt, een kiosk voor meerdere apps heeft met de Instellingen App, Feedback-hub en Microsoft Edge.

:::code language="xml" source="samples/kiosk-sample-global-assigned-access.xml":::

Dit voorbeeld is een kiosk voor globale toegewezen toegang die de eigenaar van het apparaat uitsluit, wanneer andere Azure AD-gebruikers zich kunnen aan- en uittekenen, een kiosk voor meerdere apps hebben met de Instellingen-app, Feedback-hub en Microsoft Edge. Deze kiosk bevat ook een secundaire kioskconfiguratie voor een bezoekersaccount, die door iedereen kan worden aangemeld op het vergrendelingsscherm. Wanneer een gebruiker zich bij het bezoekersaccount meldt, heeft deze een kiosk voor meerdere apps die alleen de Feedback-hub app.

:::code language="xml" source="samples/kiosk-sample-global-assigned-access-visitor-exclude.xml":::
