---
title: Algemene apparaatbeperkingen
description: Blijf op de hoogte van algemene apparaatbeperkingen en instellingen voor de HoloLens-mixed reality apparaat.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/13/2020
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: e9c44466da375611f8864eae1b6e6ceea3ef9b09
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/19/2021
ms.locfileid: "111377768"
---
# <a name="common-device-restrictions"></a>Algemene apparaatbeperkingen 

Deze handleiding helpt IT-professionals inzicht te krijgen in de meestgebruikte beheeropties die beschikbaar zijn voor Windows 10 Holographic besturingssysteem in de onderneming. Raadpleeg de documentatie van uw MDM-systeem voor meer informatie over hoe dit beleid wordt ingeschakeld door uw MDM-leverancier. Niet alle MDM-systemen ondersteunen elke instelling die in deze handleiding wordt beschreven. Sommige bieden ondersteuning voor aangepast beleid via OMA-URI XML-bestanden. Zie [Microsoft Intune ondersteuning voor aangepast beleid.](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10) Naamconventen kunnen ook per MDM-leverancier verschillen.

## <a name="prevent-changing-of-settings"></a>Wijzigen van instellingen voorkomen
Werknemers mogen doorgaans bepaalde persoonlijke apparaatinstellingen wijzigen die u mogelijk wilt vergrendelen op bedrijfsapparaten. Werknemers kunnen bepaalde instellingen van de HoloLens interactief aanpassen via de gebruikersinterface voor instellingen. Met MDM kunt u beperken wat gebruikers mogen wijzigen. Hieronder vindt u een lijst met veelgebruikte MDM-instellingen die Windows 10 Holographic voor het configureren van instellingenbeperkingen:
-   [VPN toestaan:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) Hiermee kan de gebruiker de VPN-instellingen wijzigen
-   [Handmatige Wi-Fi-configuratie toestaan:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration) Hiermee kunnen gebruikers verbinding Wi-Fi maken buiten netwerken die zijn ingericht met MDM
-   [Handmatige registratie van MDM toestaan](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-experience#experience-allowmanualmdmunenrollment) Of gebruikers het werkplekaccount mogen verwijderen (dat wil zeggen, de registratie van het apparaat bij het MDM-systeem wordt verwijderd)

Toegevoegd in [Windows Holographic, versie 20H2](hololens-release-notes.md#windows-holographic-version-20h2) voor HoloLens 2 apparaten:
- [Inrichtingspakket toevoegen toestaan:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage) Schakel in of gebruikers nieuwe inrichtingspakketten kunnen toevoegen door nieuwe waarden te overschrijven.
- [Inrichtingspakket verwijderen toestaan:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) Schakel in of gebruikers inrichtingspakketten kunnen verwijderen, zodat ze eerder vergrendelde instellingen kunnen in- of uitschakelen.

Meer informatie over beleidsopties vindt u in de door HoloLens ondersteunde [beleids-CSP's](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2)

## <a name="hardware-restrictions"></a>Hardwarebeperkingen
Windows 10 Holographic gebruiken geavanceerde technologie die populaire hardwarefuncties bevat, zoals camera's, microfoons, sprekers, USB-interfaces, Bluetooth-interfaces en Wi-Fi. U kunt hardwarebeperkingen gebruiken om de beschikbaarheid van deze functies te bepalen.
Hieronder vindt u een lijst met veelgebruikte MDM-instellingen die Windows 10 Holographic voor het configureren van hardwarebeperkingen:

> [!NOTE]
> Sommige van deze hardwarebeperkingen zijn van invloed op de connectiviteit en helpen bij de beveiliging van gegevens.

-   [Wi-Fi toestaan:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) Of gebruikers het Wi-Fi-radioprogramma op hun apparaten kunnen inschakelen en gebruiken.
-   [USB-verbinding toestaan:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) Of de USB-verbinding is ingeschakeld (heeft geen invloed op het laden van USB.)
-   [Bluetooth toestaan:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) Of gebruikers het Bluetooth-radioprogramma op hun apparaten kunnen inschakelen en gebruiken.
-   [Camera beperken:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccesscamera) Hiermee geeft u op of Windows-apps toegang hebben tot de camera.
-   [Microfoons beperken:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccessmicrophone) Hiermee geeft u op of Windows-apps toegang hebben tot de microfoon.

Toegevoegd in [Windows Holographic, versie 20H2](hololens-release-notes.md#windows-holographic-version-20h2) voor HoloLens 2 apparaten. 
- [DisplayOffTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery) Stel de hoeveelheid tijd in totdat de weergave wordt uitgeschakeld en door het scherm uit te schakelen, wordt het apparaat vergrendeld. 
- [DisplayOffTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin) Stel de hoeveelheid tijd in totdat de weergave wordt uitgeschakeld en door het scherm uit te schakelen, wordt het apparaat vergrendeld. 
