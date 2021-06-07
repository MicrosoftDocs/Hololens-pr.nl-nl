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
ms.openlocfilehash: b86d88c7487043c6fcb057f03f353a57e44ef781
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379434"
---
# <a name="global-assigned-access--kiosk"></a>Globale toegewezen toegang – Kiosk

Deze functie configureert HoloLens 2 apparaat voor meerdere app-kioskmodus, die van toepassing is op systeemniveau, geen affiniteit heeft met een identiteit op het systeem en is van toepassing op iedereen die zich bij het apparaat meldt.

> [!NOTE]
> Deze functie is momenteel alleen beschikbaar in Windows Insider builds. Als u deze functie wilt uitproberen voordat deze algemeen beschikbaar is in HoloLens-releases, leest u meer over Windows Insider [builds.](hololens-insider.md)

## <a name="how-to-use-global-assigned-access-in-intune"></a>Hoe kan ik globale toegewezen toegang gebruiken in Intune?

> [!NOTE]
> Houd rekening met de gebieden die zijn gemarkeerd met '<!-'. Voor deze gebieden moet u wijzigingen aanbrengen op basis van uw voorkeuren.

1. Maak als volgt een aangepast OMA URI-apparaatconfiguratieprofiel en pas dit toe op de HoloLens-apparaatgroep:

    URI-waarde: ./Device/Vendor/MSFT/AssignedAccess/Configuration

    > [!div class="mx-imgBorder"]
    > ![OMA-URI voor globale toegewezen toegang in Intune](images/global-assigned-access-omauri.png)

2. Werk voor waarde de volgende inhoud bij en plak deze:

    :::code language="xml" source="samples/global-assigned-access.xml" highlight="12-13,23":::

## <a name="how-to-use-global-assigned-access-in-windows-configuration-designer"></a>Globale toegewezen toegang gebruiken in Windows Configuration Designer

1. Werk de HIERBOVEN genoemde XML-blob bij en sla deze op als XML-bestand. 

2. Volg de stappen in [Een inrichtingspakket gebruiken om](https://docs.microsoft.com/hololens/hololens-kiosk#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)een kiosk voor één app of meerdere apps in te stellen, met name de sectie Prov. package, step 2– Add the kiosk configuration XML file to a provisioning package' (pakket, stap 2: het XML-bestand voor de kioskconfiguratie toevoegen aan een inrichtingspakket) en verwijzen naar het XML-bestand dat in de vorige stap is opgeslagen.

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

Dit is een voorbeeld van een kiosk voor globale toegewezen toegang die wanneer een gebruiker zich meldt, een kiosk voor meerdere apps heeft met de instellingen-app, Feedback-hub en Microsoft Edge.

:::code language="xml" source="samples/kiosk-sample-global-assigned-access.xml":::

Dit voorbeeld is een algemeen toegewezen toegangskiosk waarmee de eigenaar van het apparaat wordt uitgesloten. Wanneer andere Azure AD-gebruikers zich bij hen kunnen aan- en uittekenen, hebben ze een kiosk voor meerdere apps met de instellingen-app, Feedback-hub en Microsoft Edge. Deze kiosk bevat ook een secundaire kioskconfiguratie voor een bezoekersaccount, die door iedereen kan worden aangemeld op het vergrendelingsscherm. Wanneer een gebruiker zich bij het bezoekersaccount meldt, heeft deze een kiosk voor meerdere apps die alleen de Feedback-hub app.

:::code language="xml" source="samples/kiosk-sample-global-assigned-access-visitor-exclude.xml":::
