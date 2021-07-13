---
title: Statusscheiding en isolatie
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
ms.openlocfilehash: 0487ea49c706c753f4dfca7da7daa499d1715e9f
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639791"
---
# <a name="state-separation-and-isolation"></a>Statusscheiding en isolatie

Statusscheiding en isolatie beschermen kritieke delen van het Hololens 2-besturingssysteem tegen veranderingen, zoals de onderdelen die nodig zijn om het besturingssysteem in een vertrouwde status op te starten. Met isolatietechnologie worden niet-vertrouwde apps verplaatst naar een geïsoleerde sandbox-omgeving om ervoor te zorgen dat ze geen invloed hebben op de systeembeveiliging.

## <a name="state-separation"></a>Statusscheiding

Statusscheiding op HoloLens 2 verbetert de beveiliging en servicebaarheid (bijwerken) aanzienlijk en helpt bij het beveiligen van uw toepassingsgegevens.  Statusscheiding werkt als volgt:
  * Het basisbesturingssysteem wordt opgeslagen in het kernbesturingssysteemvolume (vertrouwd of geverifieerd Microsoft-besturingssysteem bij het bijwerken van het besturingssysteem).
  * De delen van het besturingssysteem die tijdens run time kunnen worden gewijzigd (zoals downloadbare stuurprogramma's en configuraties), gebruiken verdere statusscheiding om de gegevens te partitioneren en op te slaan op veilige, afzonderlijke opslaglocaties.
  * Aan elke veilige opslaglocatie zijn verschillende beveiligingsbeleidsregels gekoppeld, wat verschillende beveiligingsvoordelen biedt, zoals beschreven in de volgende sectie.

## <a name="state-separation-benefits"></a>Voordelen van statusscheiding

  * Beveiliging: De statusscheiding die wordt aanbevolen in HoloLens 2 verbetert de platformintegriteit, de bescherming tegen schadelijke software en de beveiliging van gebruikersgegevens aanzienlijk. Door het onafhandelbare deel van het besturingssysteem te scheiden en het besturingssysteem alleen-lezen of integriteit te beschermen, maakt statusscheiding het voor malware zeer moeilijk om te behouden bij een koude herstart. 
  * Updates: Met HoloLens 2 worden updates eenvoudig en betrouwbaar zodra het kernbesturingssysteem niet meer kan worden gemodifi zonder dat het is gescheiden van de rest van de gegevens op het apparaat.  Bovendien vormt statusscheiding de essentiële basis voor aanzienlijk snellere updates, waardoor het besturingssysteem in één stap (atomische eenheid) kan worden vervangen.
  * Apparaat opnieuw instellen: HoloLens 2 opnieuw instellen worden door de gebruiker gegenereerde gegevens en app-gegevens van gebruikers geweken op het apparaat, inclusief interne en externe opslaglocaties. Het behoudt de huidige besturingssysteem-apps en beveiligingskritieke apps, en de huidige door Microsoft en OEM aangepaste apps (vooraf geïnstalleerd). Deze vooraf geïnstalleerde apps kunnen op het apparaat worden gerehydrateerd nadat het opnieuw instellen is voltooid

### <a name="state-separation-states"></a>Statussen van scheiding van staten

Statusscheiding zorgt ervoor dat het besturingssysteem alleen kan worden gewijzigd door vertrouwde microsoft-apparaatonderdelen en dat alleen de status van hoge waarde behouden mag blijven tijdens het opnieuw opstarten; andere systeemtoestand bestaat alleen voor de duur van de opstartsessie en wordt verwijderd na het opnieuw opstarten. Als de status snel wordt gescheiden, keert het apparaat terug naar de fabriekstoestand. Windows Holographic for Business kunnen worden onderverdeeld in deze afzonderlijke categorieën:
  * Kernbesturingssysteem – Onaangepast
  * Besturingssysteemgegevens – Wijzigbare status 
  * Gebruikersgegevens – Wijzigbare status

Elk van deze HoloLens 2 operationele staten wordt beschreven in de volgende sectie.

#### <a name="core-operating-system"></a>Basisbesturingssysteem

Een onveranderbare status bestaat uit uitvoerbare bestanden en gegevens die onveranderbaar zijn en alleen door Microsoft kunnen worden gewijzigd tijdens de installatie van updates. Tijdens een dergelijke update van het basisbesturingssysteem wordt een nieuwe installatie afbeelding met de meest recente gewenste operationele status ingeschakeld.
De onverharde status wordt gemarkeerd als alleen-lezen (of is anderszins integriteit beveiligd), waardoor persistentie van malware met verhoogde bevoegdheden wordt voorkomen. De volgende uitvoerbare bestanden en gegevens zijn beveiligd met de status Onveranderbaar:
  * Windows Stuurprogramma's voor Holographic InBox
  * Binaire besturingssysteem-bestanden
  * Windows postvak IN
  * Statische Windows Holographic-instellingen die zijn opgeslagen in Windows Register Hive (HKLM)
    * Voorbeeld: HKLM slaat de configuratiegegevens op voor de apps die op een computer zijn geïnstalleerd. Het slaat ook informatie op voor het detecteren van hardware en de bijbehorende stuurprogramma's.
Door deze te beveiligen in de onveranderbare (integriteit en alleen-lezen beveiligde) status, zorgen we ervoor dat het basisbesturingssysteem altijd wordt op start in een vertrouwde status. Wanneer een apparaat opnieuw wordt ingesteld, kunnen we er bovendien voor zorgen dat het apparaat alleen wordt opstart in de onderdelen in deze onveranderbare sectie. 

#### <a name="operating-system-data"></a>Besturingssysteemgegevens 

Het is belangrijk te weten dat uitvoerbare bestanden en gegevens die tijdens runtime kunnen worden gewijzigd (en die niet essentieel zijn voor de functie van het besturingssysteem), kunnen worden verwijderd en opnieuw kunnen worden gemaakt wanneer de gegevens beschadigd of aangetast zijn. Een wijzigingstoestand met hoge waarde is functioneel vereist voor persistentheid door het besturingssysteem, of moet behouden blijven tijdens het afsluiten van het besturingssysteem en/of bij opnieuw opstarten door ondersteunde Windows-besturingssysteem- en apparaatscenario's. Voorbeelden van een veranderlijke status met hoge waarde zijn:
  * Door de IT-beheerder geconfigureerde algemene apparaatinstellingen, zoals het uitschakelen van de locatie voor alle gebruikers.
  * Wi-Fi-netwerkverbinding heeft toegang tot door het apparaat onthouden netwerken en gekoppelde verbindingswachtwoorden.
  * Crashdumps, inclusief instellingen en logboeken.
  * Stuurprogramma's die op aanvraag zijn gedownload voor nieuw ontdekte apparaten.
Een wijzigingstoestand met hoge waarde op HoloLens 2 bevindt zich op de locatie van de gegevensbeveiliging van het besturingssysteem, als een opgeslagen bestand op schijf of in een persistente register-hive.

#### <a name="user-data"></a>Gebruikersgegevens

De laatste statuscategorie vertegenwoordigt gebruikersgegevens die worden geproduceerd of persistent zijn gemaakt door UWP-toepassingen of het besturingssysteem. Alle bekende gebruikersmappen, zoals Downloads, Documenten, Video's, gebruikersprofielen en HKEY_CURRENT_USER hive, worden ook op deze locatie opgeslagen. Deze gegevens kunnen niet worden geëxtraheerd zonder de juiste referenties; Zie Versleuteling en gegevensbescherming voor meer informatie over hoe uw [gegevens worden beveiligd.](security-encryption-data-protection.md)

##  <a name="isolation"></a>Isolatie

Om dit evenwicht te bereiken, HoloLens 2 een kernbesturingssysteem dat wordt gebruikt voor primaire functies, zoals opstarten, hardwarebeheer, aanmelden, enzovoort. Er zijn slechts twee sets toepassingen die worden uitgevoerd op het basisbesturingssysteem: vooraf geïnstalleerde toepassingen en UWP-apps.

## <a name="code-signing"></a>Ondertekening van programmacode

Met digitaal ondertekeningscode kunt u substantieren dat uitvoerbare bestanden en scripts niet zijn gewijzigd omdat ze zijn ondertekend door een vertrouwde bron, waardoor authenticiteit en integriteit mogelijk zijn. De instanties die HoloLens 2 vertrouwensrelatie standaard gebruiken, zijn Microsoft en Microsoft Store. IT-beheerders kunnen nieuwe certificaten toevoegen aan het apparaat via de CSP's [ClientCertificateInstall](/windows/client-management/mdm/clientcertificateinstall-csp) en [RootCATrustedCertificates.](/windows/client-management/mdm/rootcacertificates-csp) Ze kunnen ook het [beleid AllowAllTrustedApps](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps) gebruiken om aanvullende sideloaded of [Line-Of-Business-apps te vertrouwen.](/intune/apps/lob-apps-windows) Certificaten bevinden zich in het certificaatopslag van de lokale computer die is opgeslagen in HKLM/Root als u "Apparaat" of in HKCU gebruikt als "Gebruiker".

## <a name="defender-protections"></a>Defender-beveiligingen
HoloLens 2 gebruikt Microsoft-services om gebruikers een geavanceerd beveiligingsniveau te bieden:

* [Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) wordt automatisch ingeschakeld op Windows Holographic door het besturingssysteem en beschermt tegen phishing en malware, evenals het downloaden van mogelijk schadelijke bestanden, op Edge. Het kan niet worden uitgeschakeld door de gebruiker, maar kan worden uitgeschakeld via beleid.

* [Defender Firewall](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security) blokkeert niet-geautoriseerd netwerkverkeer van en naar uw apparaat. Deze is standaard ingeschakeld en kan niet door de klant worden geconfigureerd via lokale acties of beleid. 

* [Windows Defender Application Control:](/windows/security/threat-protection/windows-defender-application-control/wdac-and-applocker-overview)HoloLens 2 biedt ondersteuning voor WDAC, waarmee de IT-beheerder beleid voor toepassingsbeheer naar het apparaat kan pushen. Meer informatie vindt u in [WDAC gebruiken op HoloLens 2 apparaten met MSFT Intune.](/mem/intune/configuration/custom-profile-hololens) 

IT-beheerders kunnen smartscreen-gedrag beheren [via AllowSmartScreen](/windows/client-management/mdm/policy-csp-browser#browser-allowsmartscreen) en browsergedrag via [dit beleid.](/windows/client-management/mdm/policy-csps-supported-by-hololens2) 

