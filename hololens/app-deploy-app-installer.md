---
title: Apps side loaden en apps installeren via HoloLens 2 App-installatieprogramma
description: Meer informatie over het installeren en oplossen van problemen met apps met het app-installatieprogramma en het side loaden en installeren van apps via de gebruikersinterface.
keywords: app-beheer, app, hololens, app-installatieprogramma
author: evmill
ms.author: v-evmill
ms.reviewer: qizho
ms.date: 11/10/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 0b0de9039ce4d0c1eeab968b0f7c2f5eee8cdc34739391b6022b409325955350
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/05/2021
ms.locfileid: "115665264"
---
# <a name="install-apps-on-hololens-2-via-app-installer"></a>Apps installeren op HoloLens 2 via App-installatieprogramma

> [!NOTE]
> Deze functie is beschikbaar gemaakt in [Windows Holographic, versie 20H2 – Update van december 2020.](hololens-release-notes.md) Zorg ervoor dat uw apparaat is [bijgewerkt](hololens-update-hololens.md) om deze functie te gebruiken.

We hebben **een nieuwe mogelijkheid (App-installatieprogramma)** toegevoegd waarmee u toepassingen naadloos kunt installeren op uw HoloLens 2 apparaten. De functie is **standaard ingeschakeld voor niet-beherende apparaten.** Om onderbrekingen voor ondernemingen te voorkomen, is het app-installatieprogramma op dit moment niet beschikbaar **voor** beheerde apparaten.  

Een apparaat wordt beschouwd als 'beheerd' als **een** van de volgende waar is:

- MDM [ingeschreven](hololens-enroll-mdm.md)
- Geconfigureerd met [inrichtingspakket](hololens-provisioning.md)
- [Gebruikersidentiteit](hololens-identity.md) is Azure AD

U kunt nu apps installeren zonder dat u de ontwikkelaarsmodus hoeft in te schakelen of de Apparaatportal.  Download (via USB of via Microsoft Edge) de Appx-bundel naar uw apparaat en navigeer naar de Appx-bundel in de Verkenner om te worden gevraagd de installatie te beginnen.  U kunt ook [een installatie starten vanaf een webpagina](/windows/msix/app-installer/installing-windows10-apps-web). Net als apps die u installeert via de Microsoft Store of sideloaden met behulp van de [](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) lob-app-implementatiefunctie van MDM, moeten apps digitaal worden ondertekend met het hulpprogramma voor ondertekenen en moet het certificaat dat wordt gebruikt om te ondertekenen worden vertrouwd door het HoloLens-apparaat voordat de app kan worden geïmplementeerd. [](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations)

## <a name="requirements"></a>Vereisten

### <a name="for-your-devices"></a>Voor uw apparaten:

Deze functie is momenteel beschikbaar in Windows Holographic 20H2-builds voor HoloLens 2 apparaten. Zorg ervoor dat alle apparaten die deze methode gebruiken, [worden bijgewerkt.](hololens-update-hololens.md)

### <a name="for-your-apps"></a>Voor uw apps:

De oplossingsconfiguratie van uw app moet **Master** of **Release** zijn, omdat de App-installatieprogramma afhankelijkheden van de store gebruikt. Meer informatie over het [maken van app-pakketten.](/windows/msix/app-installer/create-appinstallerfile-vs)

Apps die via deze methode worden geïnstalleerd, moeten digitaal zijn ondertekend. U moet een certificaat gebruiken om de app te ondertekenen. U kunt een certificaat verkrijgen uit de lijst met vertrouwde [MS-CA's.](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)In dat geval hoeft u geen extra actie te ondernemen. U kunt ook uw eigen certificaat ondertekenen, maar dat certificaat moet naar het apparaat worden pushen.

- Apps ondertekenen met [het hulpprogramma Sign.](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)

**Certificaatopties:**

- [Lijst met vertrouwde MS-CA's](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

**Kies een implementatiemethode voor certificaten.**

- [Inrichtingspakketten kunnen](hololens-provisioning.md) worden toegepast op lokale apparaten.
- MDM kan worden gebruikt voor het [toepassen van certificaten met apparaatconfiguraties.](/mem/intune/protect/certificates-configure)
- Gebruik de op het [apparaat Certificate Manager](certificate-manager.md).

## <a name="installation-method"></a>Installatiemethode

1. Controleer of uw apparaat niet wordt beschouwd als beheerd.
1. Controleer of uw HoloLens 2 is ingeschakeld en of u bent aangemeld.
1. Navigeer op uw pc naar uw aangepaste app en kopieer yourapp.appxbundle naar yourdevicename\Internal Storage\Downloads.
    Nadat u klaar bent met het kopiëren van het bestand, kunt u de verbinding met uw apparaat verbreken en de installatie later voltooien.
1. Open op HoloLens 2 apparaat Het **menu Start openen,** selecteer Alle apps **start** de **bestandenverkenner-app.**
1. Navigeer naar de map Downloads. Mogelijk moet u in het linkerpaneel van de app eerst **Dit apparaat** selecteren en vervolgens naar Downloads navigeren.
1. Selecteer het bestand yourapp.appxbundle.
1. De App-installatieprogramma wordt start. Selecteer de **knop Installeren** om uw app te installeren.

De geïnstalleerde app wordt automatisch start na voltooiing van de installatie.

![MRTK-voorbeelden installeren via App-installatieprogramma](images/hololens-app-installer-picture.jpg)

### <a name="troubleshooting-installs"></a>Problemen met installaties oplossen

Als de installatie van uw app is mislukt, controleert u het volgende om het probleem op te lossen:

- Uw app is een master- of release-build.
- Uw apparaat wordt bijgewerkt naar een build waarop deze functie beschikbaar is.
- U bent [verbonden met internet.](hololens-network.md)
- Uw [eindpunten voor de Microsoft Store](hololens-offline.md) juist geconfigureerd.  

## <a name="web-installer"></a>Web Installer

Gebruikers kunnen een app rechtstreeks vanaf een webserver installeren. Deze stroom maakt gebruik van de App-installatieprogramma gecombineerd met een distributiemethode voor eenvoudig downloaden en installeren.

### <a name="how-to-set-up-web-install"></a>Web-installatie instellen:

1. Zorg ervoor dat uw app juist is geconfigureerd voor installatie.
1. Volg deze [stappen om installatie vanaf een webpagina in teschakelen.](/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage)

### <a name="end-user-experience"></a>Eindgebruikerservaring:

1. De gebruiker ontvangt en installeert het certificaat op het apparaat met behulp van een eerder gekozen methode.
1. De gebruiker bezoekt de URL die in de bovenstaande stap is gemaakt.

De app wordt nu op het apparaat geïnstalleerd. Als u de app wilt zoeken, opent u **Startmenu** selecteert u de **knop Alle apps** app te zoeken.

- Ga voor meer hulp bij het oplossen van problemen met de installatiemethode voor het app-installatieprogramma naar [Problemen met app-installatieprogramma's oplossen.](/windows/msix/app-installer/troubleshoot-appinstaller-issues)

> [!NOTE]
> De gebruikersinterface tijdens het updateproces wordt niet ondersteund. De optie ShowPrompt op deze [pagina en](/windows/msix/app-installer/update-settings) de bijbehorende opties worden dus niet ondersteund.

## <a name="sample-apps"></a>Voorbeeld-apps

Probeer de App-installatieprogramma met een van onze beschikbare voorbeeld-apps. 
> [!div class="nextstepaction"]
> [Voorbeeld-apps](/windows/mixed-reality/develop/features-and-samples)
