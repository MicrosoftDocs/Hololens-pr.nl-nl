---
title: Inrichtingspakket
description: Meer informatie over app-verpakking, inrichting, implementatie en implementatie van bedrijfsapps voor HoloLens apparaten.
keywords: app, app-implementatie, implementatie van bedrijfsapps, inrichting
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: d071f4326a35a9ea61e2069618da7107bb808f04
ms.sourcegitcommit: f480d3cc8d549fa356e05df6ce15e9517f5b978a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/08/2021
ms.locfileid: "123610986"
---
# <a name="provisioning-package"></a>Inrichtingspakket

Inrichtingspakketten kunnen worden gebruikt voor het voorbereiden en configureren van apparaten in een omgeving zonder toegang tot eindpuntbeheer. Ze kunnen ook worden geïmplementeerd op een apparaat, ongeacht de identiteit van de gebruiker, de inschrijvingsstatus, tijdens de Out-of-Box Experience (OOBE) of door een inrichtingspakket toe te passen tijdens de [installatie](/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup).

## <a name="provisioning-packages-considerations"></a>Overwegingen bij inrichtingspakketten

* Niet-openbare apps
* Alleen USB-side-load
* Geen automatische update (vereist handmatige updates via PPKG's)

Apps die zijn geïnstalleerd via een inrichtingspakket, moeten zijn ondertekend met een certificaat in het lokale computeropslag. Met inrichtingspakketten kunnen alleen certificaten worden geïnstalleerd op het apparaatopslag (lokale computer). Daarom kunnen een app en een certificaat worden geïnstalleerd via hetzelfde inrichtingspakket. Als u uw certificaat van MDM implementeert of installeert via [Certificaatbeheer,](certificate-manager.md)moet u het certificaat implementeren in de store van de lokale computer om apps te ondertekenen die op deze manier zijn geïnstalleerd.

Als u de basisbeginselen van het maken van een inrichtingspakket voor HoloLens apparaten wilt leren, gaat u [HoloLens Inrichting.](/hololens/hololens-provisioning) Als u een app wilt implementeren, moet u beginnen met geavanceerde inrichting.

> [!NOTE]
> HoloLens (eerste generatie) biedt beperkte ondersteuning voor het installeren van apps **(UniversalAppInstall)** met behulp van een inrichtingspakket. HoloLens apparaten (eerste generatie) bieden alleen ondersteuning voor het installeren van een app via PPKG tijdens OOBE en alleen met installatie van gebruikerscontext.

## <a name="setup"></a>Instellen

In [Windows Configuration Designer volgt](https://www.microsoft.com/store/productId/9NBLGGH4TX22) u de volgende vier stappen.

1. Stel ApplicationManagement/AllowAllTrustedApps in op Ja. Zie: [ApplicationManagement/AllowAllTrustedApps.](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps)

2. **Navigeer naar UniversalAppInstall**  >  **UserContextApp** en voer **packageFamilyName in.** Zie [UniversalAppInstall.](/windows/configuration/wcd/wcd-universalappinstall)

   U kunt deze Apparaatportal op een apparaat waar u uw app al op hebt geïnstalleerd. Ga naar de pagina Apps en bekijk de regel PackageRelativeID, met alle informatie vóór de '!' Is uw **PackageFamilyName.**

3. Vervolgens ziet u dat u een nieuwe sectie hebt, **ApplicationFile**. Gebruik dit gebied om uw appx-bundel te uploaden.

4. Afhankelijk van of u uw app hebt aangeschaft of uw eigen LOB-app hebt gebouwd, moet u het licentiebestand of beveiligingscertificaat uploaden.

    - Voor licentiebestand: navigeer **naar UniversalAppInstall**  >  **UserContextAppLicence** en voer uw licentieproduct-id in. Er wordt een <b>nieuwe sectie LicenseProductID:</b><i>yourlicenseproductid</i> gemaakt, selecteer deze nieuwe sectie en blader naar de locatie van uw licentie en upload deze.
        - Zie [UserContextAppLicense](/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).
    - Voor het beveiligingsbestand gaat u naar **Certificaten en** selecteert u het certificaat dat u naast uw APPX-bundel wilt installeren.

Zorg ervoor dat u uw project op een veilige locatie op slaan. Exporteert het vervolgens als **een inrichtingspakket.**   

Zie ook: [Uw inrichtingspakket toepassen op HoloLens](/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).
