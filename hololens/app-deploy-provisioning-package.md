---
title: Inrichtingspakket
description: Meer informatie over app-verpakking, inrichting, implementatie en implementatie van bedrijfsapps voor HoloLens-apparaten.
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
ms.openlocfilehash: 9c73b03e6a8dca6baf6c58fed091df96994c3780
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/19/2021
ms.locfileid: "111377849"
---
# <a name="provisioning-package"></a>Inrichtingspakket

Inrichtingspakketten kunnen worden gebruikt voor het voorbereiden en configureren van apparaten in een omgeving zonder toegang tot eindpuntbeheer. Ze kunnen ook worden geïmplementeerd op een apparaat, ongeacht de identiteit van de gebruiker, de inschrijvingsstatus, tijdens de Out of Box Experience (OOBE) of door een inrichtingspakket toe te passen tijdens de [installatie](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup).

## <a name="provisioning-packages-considerations"></a>Overwegingen voor inrichtingspakketten:

* Niet-openbare apps
* Alleen USB-side-load
* Geen automatische update (handmatige updates via PPKG's vereist)

Apps die zijn geïnstalleerd via een inrichtingspakket, moeten zijn ondertekend met een certificaat in de store van de lokale computer. Met inrichtingspakketten kunnen alleen certificaten worden geïnstalleerd in het apparaatopslag (lokale computer). Daarom kunnen een app en certificaat worden geïnstalleerd via hetzelfde inrichtingspakket. Als u uw certificaat implementeert vanuit MDM of installeert via [Certificaatbeheer,](certificate-manager.md)moet u het certificaat implementeren in de store van de lokale computer om apps te ondertekenen die op deze manier zijn geïnstalleerd.

Ga naar HoloLens Provisioning voor meer informatie over de basisbeginselen van het maken van een [inrichtingspakket voor HoloLens-apparaten.](https://docs.microsoft.com/hololens/hololens-provisioning) Als u een app wilt implementeren, moet u beginnen met geavanceerde inrichting.

> [!NOTE]
> HoloLens (eerste generatie) biedt beperkte ondersteuning voor het installeren van apps **(UniversalAppInstall)** met behulp van een inrichtingspakket. HoloLens-apparaten (eerste generatie) bieden alleen ondersteuning voor het installeren van een app via PPKG alleen tijdens OOBE en alleen met installatie van gebruikerscontext.

## <a name="setup"></a>Instellen

In [Windows Configuration Designer moet u](https://www.microsoft.com/store/productId/9NBLGGH4TX22) de volgende vier stappen volgen.

1. Stel ApplicationManagement/AllowAllTrustedApps in op Ja. Zie: [ApplicationManagement/AllowAllTrustedApps.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps)

2. **Navigeer naar UniversalAppInstall**  >  **UserContextAppLicense** voer **packageFamilyName in.** Zie [UniversalAppInstall.](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall) Zie ook: [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).

   U kunt deze Apparaatportal op een apparaat waar u uw app al op hebt geïnstalleerd. Ga naar de pagina Apps en bekijk de regel PackageRelativeID, met alle informatie vóór de '!' Is uw **PackageFamilyName.**

3. Vervolgens ziet u dat u een nieuwe sectie hebt, **ApplicationFile.** Gebruik dit gebied om uw appx-bundel te uploaden.

4. Afhankelijk van of u uw app hebt aangeschaft of uw eigen LOB-app hebt gebouwd, moet u het licentiebestand of beveiligingscertificaat uploaden.

    - Voor licentiebestand: navigeer **naar UniversalAppInstall**  >  **UserContextAppLicence,** blader naar de locatie van uw licentie en upload deze.
    - Voor het beveiligingsbestand gaat u naar **Certificaten en** selecteert u het certificaat dat u naast uw APPX-bundel wilt installeren.

Sla uw project op een veilige locatie op. Exporteert het vervolgens als **een inrichtingspakket**.   

Zie ook: [Uw inrichtingspakket toepassen op HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).
