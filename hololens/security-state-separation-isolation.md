---
title: Scheiding en isolatie van staten
description: Meer informatie over statusscheiding, isolatie, ondertekening van programmacode en Defender-toepassingen op HoloLens 2 mixed reality apparaat.
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: security, hololens, State separation, State separation and isolation, hololens 2, hololens2 security, security overview, security architecture, architecture, hololens 2 architecture
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 60d6d7c0e281395957ce9158144a5f3d60927682
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379458"
---
# <a name="state-separation-and-isolation"></a>Scheiding en isolatie van staten

Statusscheiding en isolatie beschermt kritieke delen van het Hololens 2-besturingssysteem tegen veranderingen, zoals de onderdelen die nodig zijn om het besturingssysteem in een vertrouwde status op te starten. Met isolatietechnologie worden niet-vertrouwde apps verplaatst naar een geïsoleerde sandbox-omgeving om ervoor te zorgen dat ze geen invloed hebben op de systeembeveiliging.

## <a name="state-separation"></a>Statusscheiding

Statusscheiding op HoloLens 2 verbetert de beveiliging en servicebaarheid (bijwerken) aanzienlijk en helpt uw toepassingsgegevens te beschermen.  Statusscheiding werkt als volgt:
  * Het basisbesturingssysteem wordt opgeslagen in het kernbesturingssysteemvolume (vertrouwd of geverifieerd Microsoft-besturingssysteem dat het besturingssysteem bij werkt).
  * De delen van het besturingssysteem die tijdens run time kunnen worden gewijzigd (zoals downloadbare stuurprogramma's en configuraties), gebruiken een verdere scheiding van de status om de gegevens te partitioneren en om deze op te slaan op veilige, afzonderlijke opslaglocaties.
  * Aan elke veilige opslaglocatie zijn verschillende beveiligingsbeleidsregels gekoppeld, wat verschillende beveiligingsvoordelen biedt, zoals beschreven in de volgende sectie.

## <a name="state-separation-benefits"></a>Voordelen van scheiding van staten

  * Beveiliging: De scheiding van statussen in HoloLens 2 verbetert de platformintegriteit, bescherming tegen schadelijke software en beveiliging van gebruikersgegevens aanzienlijk. Door het onaangepast deel van het besturingssysteem te scheiden en het besturingssysteem alleen-lezen of integriteit te beschermen, maakt statusscheiding het voor malware zeer moeilijk om persistent te maken bij een koude herstart. 
  * Updates: wanneer HoloLens 2 basisbesturingssysteem niet meer kan worden gemodifified en op een schone manier is gescheiden van de rest van de gegevens op het apparaat, worden updates eenvoudig en betrouwbaar.  Bovendien vormt staatscheiding de essentiële basis voor aanzienlijk snellere updates, waardoor het besturingssysteem in één stap (atomische eenheid) kan worden vervangen.
  * Apparaat opnieuw instellen: HoloLens 2 opnieuw instellen worden door de gebruiker gegenereerde gegevens en app-gegevens van gebruikers geweken op het apparaat, inclusief interne en externe opslaglocaties. Het behoudt de huidige besturingssysteem-apps en beveiligingskritieke apps, en de huidige door Microsoft en OEM aangepaste apps (vooraf geïnstalleerd). Deze vooraf geïnstalleerde apps kunnen op het apparaat worden gerehydrateerd nadat het opnieuw instellen is voltooid

### <a name="state-separation-states"></a>Statusscheidingstoestanden

Statusscheiding zorgt ervoor dat het besturingssysteem alleen kan worden gewijzigd door vertrouwde microsoft-apparaatonderdelen en dat alleen de status met een hoge waarde behouden mag blijven bij opnieuw opstarten; andere systeemtoestand bestaat alleen voor de duur van de opstartsessie en wordt verwijderd na het opnieuw opstarten. Als de status is gescheiden, keert het apparaat snel terug naar de fabrieksinstellingen. Windows Holographic for Business kunnen worden onderverdeeld in deze afzonderlijke categorieën:
  * Basisbesturingssysteem : niet-verhandelbare status
  * Besturingssysteemgegevens – Wijzigbare status 
  * Gebruikersgegevens – Wijzigbare status

Elk van deze HoloLens 2 operationele staten wordt beschreven in de volgende sectie.

#### <a name="core-operating-system"></a>Basisbesturingssysteem

Een onveranderbare status bestaat uit uitvoerbare bestanden en gegevens die onveranderbaar zijn en alleen door Microsoft kunnen worden gewijzigd tijdens de installatie van updates. Tijdens een dergelijke update van het basisbesturingssysteem wordt een nieuwe installatie afbeelding met de meest recente gewenste operationele status ingeschakeld.
De onverharde status wordt gemarkeerd als alleen-lezen (of is anderszins integriteit beveiligd), waardoor persistentie van malware met verhoogde bevoegdheden wordt voorkomen. De volgende uitvoerbare bestanden en gegevens worden beveiligd met de status Onveranderbaar:
  * Stuurprogramma's voor Postvak IN van Windows Holographic
  * Binaire besturingssysteem-bestanden
  * Windows Postvak IN-stuurprogramma's
  * Statische Windows Holographic-instellingen die zijn opgeslagen in Windows Registry Hive (HKLM)
    * Voorbeeld: HKLM slaat de configuratiegegevens op voor de apps die op een computer zijn geïnstalleerd. Het slaat ook informatie op voor het detecteren van hardware en de bijbehorende stuurprogramma's.
Door deze te beveiligen in de onveranderbare (integriteit en alleen-lezen beveiligde) status, zorgen we ervoor dat het basisbesturingssysteem altijd in een vertrouwde status wordt opgebootsd. Wanneer een apparaat opnieuw wordt ingesteld, kunnen we er bovendien voor zorgen dat het apparaat alleen wordt opstart in de onderdelen in deze onveranderbare sectie. 

#### <a name="operating-system-data"></a>Besturingssysteemgegevens 

Het is belangrijk te weten dat uitvoerbare bestanden en gegevens die tijdens runtime kunnen worden gewijzigd (en niet essentieel zijn voor de functie van het besturingssysteem), kunnen worden verwijderd en opnieuw kunnen worden gemaakt wanneer de gegevens beschadigd of aangetast zijn. Een wijzigingswaarde van hoge waarde is functioneel vereist om door het besturingssysteem te behouden, of naar verwachting te blijven bestaan tijdens het afsluiten van het besturingssysteem en/of bij opnieuw opstarten door ondersteunde scenario's voor Windows-besturingssystemen en apparaten. Voorbeelden van een veranderlijke status met hoge waarde zijn:
  * Door de IT-beheerder geconfigureerde algemene apparaatinstellingen, zoals het uitschakelen van de locatie voor alle gebruikers.
  * Wi-Fi-netwerkverbinding heeft toegang tot door het apparaat onthouden netwerken en gekoppelde verbindingswachtwoorden.
  * Crashdumps, waaronder instellingen en logboeken.
  * Stuurprogramma's die op aanvraag zijn gedownload voor nieuw ontdekte apparaten.
Een status met hoge waarde wijzigen op HoloLens 2 bevindt zich op het besturingssysteem Gegevensbeveiligingslocatie, hetzij als een opgeslagen bestand op schijf of in een persistent register hive.

#### <a name="user-data"></a>Gebruikersgegevens

De laatste statuscategorie vertegenwoordigt gebruikersgegevens die worden geproduceerd of persistent gemaakt door UWP-toepassingen of het besturingssysteem. Alle bekende gebruikersmappen, zoals Downloads, Documenten, Video's, gebruikersprofielen en HKEY_CURRENT_USER hive, worden ook op deze locatie opgeslagen. Deze gegevens kunnen niet worden geëxtraheerd zonder de juiste referenties; Zie Encryption and Data Protection (Versleuteling en gegevensbescherming) voor meer informatie over hoe [uw gegevens worden beveiligd.](security-encryption-data-protection.md)

##  <a name="isolation"></a>Isolatie

Om dit evenwicht te bereiken, HoloLens 2 een kernbesturingssysteem dat wordt gebruikt voor primaire functies zoals opstarten, hardwarebeheer, aanmelden, enzovoort. Er zijn slechts twee sets toepassingen die worden uitgevoerd op het basisbesturingssysteem: vooraf geïnstalleerde toepassingen en UWP-apps.

## <a name="code-signing"></a>Ondertekening van programmacode

Met digitaal ondertekeningscode is substantiatie mogelijk dat uitvoerbare bestanden en scripts niet zijn gewijzigd omdat ze zijn ondertekend door een vertrouwde bron, waardoor echtheid en integriteit mogelijk zijn. De instanties die HoloLens 2 vertrouwensrelatie zijn, zijn Microsoft en Microsoft Store. IT-beheerders kunnen nieuwe certificaten toevoegen aan het apparaat via de CSP's [ClientCertificateInstall](https://docs.microsoft.com/windows/client-management/mdm/clientcertificateinstall-csp) en [RootCATrustedCertificates.](https://docs.microsoft.com/windows/client-management/mdm/rootcacertificates-csp) Ze kunnen ook het [beleid AllowAllTrustedApps gebruiken](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps) om aanvullende sideloaded of [Line-Of-Business-apps te vertrouwen.](https://docs.microsoft.com/intune/apps/lob-apps-windows) Certificaten bevinden zich in het certificaatopslag van de lokale computer die is opgeslagen in HKLM/Root als u "Apparaat" of in HKCU gebruikt als "Gebruiker".

## <a name="defender-protections"></a>Defender-beveiligingen
HoloLens 2 gebruikt Microsoft-services om gebruikers een geavanceerd beveiligingsniveau te bieden:

* [Defender SmartScreen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) wordt automatisch ingeschakeld op Windows Holographic door het besturingssysteem en beschermt tegen phishing en malware, evenals het downloaden van mogelijk schadelijke bestanden, op Edge. Het kan niet worden uitgeschakeld door de gebruiker, maar kan worden uitgeschakeld via beleid.

* [Defender Firewall blokkeert](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security) het niet-geautoriseerde netwerkverkeer van en naar uw apparaat. Deze is standaard ingeschakeld en kan niet worden geconfigureerd door de klant via lokale acties of beleid. 

* [Windows Defender Toepassingsbeheer:](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/wdac-and-applocker-overview)HoloLens 2 ondersteunt WDAC waarmee de IT-beheerder toepassingsbeheerbeleid naar het apparaat kan pushen. Meer informatie vindt u in [WDAC gebruiken op HoloLens 2 apparaten met MSFT Intune.](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens) 

IT-beheerders kunnen smartscreen-gedrag beheren [via AllowSmartScreen](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-allowsmartscreen) en browsergedrag via [dit beleid.](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2) 

