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
ms.openlocfilehash: 2cb497d850ff7ba2de66f69e8ec53e6dd36b773cc13d01b038def8d539e3b0c1
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/05/2021
ms.locfileid: "115665213"
---
# <a name="provisioning-package"></a>Inrichtingspakket

Inrichtingspakketten kunnen worden gebruikt om apparaten voor te bereiden en te configureren in een omgeving zonder toegang tot eindpuntbeheer. Ze kunnen ook worden geïmplementeerd op een apparaat, ongeacht de identiteit van de gebruiker, de inschrijvingsstatus, tijdens de Out-of-Box Experience (OOBE) of door een inrichtingspakket toe te passen tijdens de [installatie](/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup).

## <a name="provisioning-packages-considerations"></a>Overwegingen bij inrichtingspakketten:

* Niet-openbare apps
* Alleen USB-side-load
* Geen automatische update (handmatige updates via PPKG's vereist)

Apps die zijn geïnstalleerd via een inrichtingspakket, moeten zijn ondertekend met een certificaat in het lokale computeropslag. Inrichtingspakketten kunnen alleen certificaten installeren op het apparaat (lokale computer) en daarom kunnen een app en certificaat worden geïnstalleerd via hetzelfde inrichtingspakket. Als u uw certificaat van MDM implementeert of installeert via [Certificaatbeheer,](certificate-manager.md)moet u het certificaat implementeren in de store van de lokale computer om apps te ondertekenen die op deze manier zijn geïnstalleerd.

Voor meer informatie over de basisbeginselen van het maken van een inrichtingspakket HoloLens apparaten, gaat u [HoloLens Inrichting.](/hololens/hololens-provisioning) Als u een app wilt implementeren, moet u beginnen met geavanceerde inrichting.

> [!NOTE]
> HoloLens (eerste generatie) biedt beperkte ondersteuning voor het installeren van apps **(UniversalAppInstall)** met behulp van een inrichtingspakket. HoloLens apparaten (eerste generatie) bieden alleen ondersteuning voor het installeren van een app via PPKG tijdens OOBE en alleen met installatie van gebruikerscontext.

## <a name="setup"></a>Instellen

Binnen [Windows Configuration Designer de](https://www.microsoft.com/store/productId/9NBLGGH4TX22) volgende vier stappen uit.

1. Stel ApplicationManagement/AllowAllTrustedApps in op Ja. Zie: [ApplicationManagement/AllowAllTrustedApps.](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps)

2. **Navigeer naar UniversalAppInstall**  >  **UserContextAppLicense** voer **packageFamilyName in.** Zie [UniversalAppInstall.](/windows/configuration/wcd/wcd-universalappinstall) Zie ook: [UserContextAppLicense](/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).

   U kunt deze Apparaatportal op een apparaat waar u uw app al op hebt geïnstalleerd. Ga naar de pagina Apps en bekijk de regel PackageRelativeID, met alle informatie vóór de '!' Is uw **PackageFamilyName.**

3. Vervolgens ziet u dat u een nieuwe sectie hebt, **ApplicationFile**. Gebruik dit gebied om uw appx-bundel te uploaden.

4. Afhankelijk van of u uw app hebt aangeschaft of uw eigen LOB-app hebt gebouwd, moet u het licentiebestand of beveiligingscertificaat uploaden.

    - Voor licentiebestand: navigeer **naar UniversalAppInstall**  >  **UserContextAppLicence,** blader naar de locatie van uw licentie en upload deze.
    - Voor het beveiligingsbestand gaat u naar **Certificaten en** selecteert u het certificaat dat u naast uw APPX-bundel wilt installeren.

Zorg ervoor dat u uw project op een veilige locatie op slaan. Exporteert het vervolgens als **een inrichtingspakket.**   

Zie ook: [Uw inrichtingspakket toepassen op HoloLens.](/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup)
