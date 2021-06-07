---
title: "Algemene scenario's : offline beveiligde HoloLens 2"
description: Meer informatie over het instellen van een scenario voor offline beveiligde implementatie en app-implementatie met inrichting voor HoloLens-apparaten.
keywords: HoloLens, beheer, offline, offline beveiligd
ms.date: 9/25/2020
manager: yannisle
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
appliesto:
- HoloLens 2
ms.openlocfilehash: 8828444a69d7e5d46293340ff771f97eb5eb01e6
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/25/2021
ms.locfileid: "111377776"
---
# <a name="common-scenarios--offline-secure-hololens-2"></a>Algemene scenario's : offline beveiligde HoloLens 2

## <a name="overview"></a>Overzicht

Deze handleiding bevat richtlijnen voor het toepassen van een voorbeeld van een inrichtingspakket dat een HoloLens 2 vergrendelt voor gebruik in beveiligde omgevingen met de volgende beperkingen:

-   Wi-Fi uitschakelen.
-   Schakel BlueTooth uit.
-   Schakel Microfoons uit.
-   Hiermee voorkomt u dat inrichtingspakketten worden toegevoegd of verwijderd.
-   Geen enkele gebruiker kan een van de bovenstaande beperkte onderdelen inschakelen.

[![Scenario voor offline-beveiliging ](./images/deployment-guides-revised-scenario-c-01.png)](./images/deployment-guides-revised-scenario-c-01.png#lightbox)

## <a name="prepare"></a>Voorbereiden

Windows 10 pc installeren
1. [Download het meest recente HoloLens 2 besturingssysteembestand](https://aka.ms/hololens2download) rechtstreeks naar een pc. 
   1. Ondersteuning voor deze configuratie is opgenomen in build 19041.1117 en hoger.
1. Download/installeer het hulpprogramma Advanced Recovery Companion (ARC) [van de Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) op uw pc
1. Download/installeer het nieuwste [wcd-hulpprogramma (Windows Configuration Designer)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) van de Microsoft Store op uw pc.
1. [Download de OfflineSecureHL2_Sample map met de projectbestanden om](https://aka.ms/HoloLensDocs-SecureOfflineSample) de PPKG te bouwen.
1. Bereid uw offline [Line-Of-Business-toepassing voor op ppkg-implementatie.](app-deploy-provisioning-package.md) 


## <a name="configure"></a>Configureren

Een pakket voor beveiligde configuratie-inrichting bouwen

1. Start het WCD-hulpprogramma op uw pc.
1. Selecteer **Bestand -> Project openen.**
  1. Navigeer naar de locatie van de eerder OfflineSecureHL2_Sample map en selecteer: OfflineSecureHL2_Sample.icdproj.xml
1. Het project wordt geopend en u hebt nu een lijst met beschikbare aanpassingen:

   > [!div class="mx-imgBorder"]
   > ![Schermopname van het configuratiepakket dat is geopend in WCD](images/offline-secure-sample-wcd.png)

   Configuraties die zijn ingesteld in dit inrichtingspakket:
   
   |     Item                                                |     Instelling                       |     Beschrijving                                                                                                                    |
   |---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
   |     Accounts/gebruikers                                    |     Lokaal gebruikersnaam & wachtwoord    |     Voor deze offlineapparaten moeten één gebruikersnaam en wachtwoord worden ingesteld en gedeeld door alle gebruikers van het apparaat.          |
   |     First Experience / HoloLens / SkipCalibration       |     Waar                          |     Overslaan van kalibratie tijdens de eerste installatie van het apparaat alleen                                                                             |
   |     First Experience /HoloLens/SkipTraining          |     Waar                          |     Apparaattraining overslaan tijdens de eerste installatie van het apparaat                                                                              |
   |     Eerste ervaring / HoloLens / Wi-Fi                  |     Waar                          |     Slaat de Wi-Fi over tijdens de eerste configuratie van het apparaat                                                                                 |
   |     Beleid/Connectiviteit/AllowBluetooth                |     Nee                            |     Bluetooth uitschakelen                                                                                                             |
   |     Beleid/Ervaring/AllowCortana                    |     Nee                            |     Hiermee schakelt u Cortana uit (om mogelijke problemen te voorkomen omdat de microfoons zijn uitgeschakeld)                                          |
   |     Policies/MixedReality/MicrophoneDisabled            |     Ja                           |     Microfoon uitschakelen                                                                                                            |
   |     Policies/Privacy/LetAppsAccessLocation              |     Weigeren forcen                    |     Hiermee voorkomt u dat apps toegang proberen te krijgen tot locatiegegevens (om mogelijke problemen te voorkomen omdat het bijhouden van de locatie is uitgeschakeld)    |
   |     Policies/Privacy/LetAppsAccessMicrophone            |     Weigeren forcen                    |     Hiermee voorkomt u dat apps toegang proberen te krijgen tot microfoons (om mogelijke problemen te voorkomen omdat de microfoons zijn uitgeschakeld)           |
   |     Policies/Security/AllowAddProvisioningPackage       |     Nee                            |     Hiermee voorkomt u dat iemand inrichtingspakketten toevoegt die mogelijk proberen vergrendeld beleid te overschrijven.                         |
   |     Policies/Security/AllowRemoveProvisioningPackage    |     Nee                            |     Hiermee voorkomt u dat iemand dit vergrendelde inrichtingspakket kan verwijderen.                                                           |
   |     Policies/System/AllowLocation                       |     Nee                            |     Hiermee voorkomt u dat het apparaat locatiegegevens probeert bij te houden.                                                                        |
   |     Beleid/Wi-Fi/AllowWiFi                             |     Nee                            |     Schakelt Wi-Fi                                                                                                                 |

1. Selecteer onder Runtime-instellingen **de optie Accounts /Users/UserName: Holo/Password.**

   Noteer het wachtwoord en stel het indien gewenst opnieuw in.

1. Navigeer naar UniversalAppInstall/UserContextApp en configureer de [LOB-app](app-deploy-provisioning-package.md) die u op deze apparaten gaat implementeren.

   > [!div class="mx-imgBorder"]
   > ![Schermopname van waar u uw app toevoegt in WCD.](images/offline-secure-sample-wcd-usercontextapp2.png)

1. Als u klaar is, selecteert u de knop Exporteren en volgt u alle prompts totdat uw inrichtingspakket is gemaakt.

   > [!div class="mx-imgBorder"]
   > ![Schermopname van de knop Exporteren voor dit pakket in WCD.](images/offline-secure-sample-wcd-export.png)

## <a name="deploy"></a>Implementeren

1. Sluit de HL2 aan op uw Windows 10 pc via een USB-kabel.
1. Start het ARC-hulpprogramma en selecteer **HoloLens 2**

   ![HoloLens 2 eerste scherm nieuwe reflash maken](images/ARC2.png)

1. Selecteer in het volgende scherm **Handmatige pakketselectie.**

   ![HoloLens 2 ARC-infoscherm](images/arc_device_info.png)

1. Navigeer naar het eerder gedownloade FFU-bestand en selecteer **Openen.**
1. Selecteer op de pagina Waarschuwing **doorgaan.**

   ![HoloLens 2 ARC-waarschuwingsscherm](images/arc_warning.png)

1. Wacht tot het ARC-hulpprogramma de installatie van HoloLens 2 besturingssysteem heeft voltooid.
1. Nadat het apparaat de installatie heeft voltooid en opnieuw is opgeslagen, gaat u vanaf uw pc naar Verkenner en kopieert u het eerder opgeslagen PPKG-bestand naar de map van het apparaat.

   > [!div class="mx-imgBorder"]
   > ![PPKG-bestand op pc in het venster Bestandenverkenner.](images/offline-secure-file-explorer.png)

1. Druk in HoloLens 2 op de volgende knopcombinatie om het inrichtingspakket  uit te voeren: tik tegelijkertijd op **Volume** omlaag en aan/uit.
1. U wordt gevraagd het inrichtingspakket toe te passen. Selecteer **Bevestigen**
1. Zodra het inrichtingspakket is voltooid, selecteert u **OK**.
1. Vervolgens wordt u gevraagd u aan te melden bij het apparaat met het gedeelde lokale account en wachtwoord.

## <a name="maintain"></a>Onderhouden

Met deze configuratie wordt het aanbevolen om het bovenstaande proces opnieuw op te starten en het apparaat met het ARC-hulpprogramma te reflashen en een nieuwe PPKG toe te passen om eventuele updates aan te brengen in het besturingssysteem en/of de toepassing(en).
