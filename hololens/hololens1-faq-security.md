---
title: Veelgestelde vragen over beveiliging
description: Blijf op de hoogte van veelgestelde beveiligingsvragen en antwoorden over HoloLens mixed reality apparaten.
ms.assetid: bd55ecd1-697a-4b09-8274-48d1499fcb0b
author: pawinfie
ms.author: pawinfie
ms.date: 02/19/2020
keywords: hololens, Windows Mixed Reality, beveiliging
ms.prod: hololens
ms.sitesec: library
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
ms.custom:
- CI 111456
- CSSTroubleshooting
manager: bradke
ms.openlocfilehash: 371c901acbf23feecfe98e72569caeaf63e2198f
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/19/2021
ms.locfileid: "111377969"
---
# <a name="frequently-asked-hololens-1st-gen-security-questions"></a>Veelgestelde vragen over de beveiliging van HoloLens (eerste generatie)

1. **Welk niveau van gegevensbeveiliging biedt HoloLens 1?**
    1. Zie [HoloLens (1e generatie) BitLocker-versleuteling](hololens1-encryption.md)
1. **Welk type draadloze verbinding wordt gebruikt?**
    1. 802.11ac en Bluetooth 4.1 LE
1. **Welk type architectuur is opgenomen?  Bijvoorbeeld: punt-naar-punt, mesh of iets anders?**
    1. Wi-Fi kunnen worden gebruikt in de infrastructuurmodus om te communiceren met andere draadloze toegangspunten.
    1. Bluetooth kan worden gebruikt om peer-to-peer tussen meerdere HoloLens te praten als de toepassing van de klant dit ondersteunt of met andere Bluetooth-apparaten.
1. **Wat is FCC-id?**
    1. C3K1688
1. **Op welk frequentiebereik en welke kanalen werkt het apparaat en is het configureerbaar?**
    1. Wi-Fi: het frequentiebereik kan niet door de gebruiker worden geconfigureerd en is afhankelijk van het land van gebruik. In de Vs Wi-Fi zowel kanalen van 2,4 GHz (1-11) als 5 GHz (36-64, 100-165) gebruikt.
    1. Bluetooth: Bluetooth maakt gebruik van het standaardbereik van 2,4-2,48 GHz.
1. **Kan het apparaat specifieke frequenties toestaan of blokkeren?**
    1. Dit kan niet worden bestuurd door de gebruiker/het apparaat.
1. **Wat is het energieniveau voor zowel verzenden als ontvangen? Is het aanpasbaar? Wat is het bereik van de bewerking?**
    1. Onze standaarden voor het testen van uitstoot vindt u [hier.](https://fccid.io/C3K1688) Het bereik van de bewerking is sterk afhankelijk van het toegangspunt en de omgeving, maar is ongeveer gelijk aan andere telefoons, tablets of pc's van hoge kwaliteit.
1. **Wat is de taakcyclus/levensduur voor normale werking?**
    1. 2-3 uur actief gebruik en maximaal twee weken stand-bytijd
    1. Levensduur van accu is niet beschikbaar.
1. **Wat is het gedrag voor verzenden en ontvangen wanneer een hulpprogramma niet binnen bereik is?**
    1. HoloLens-verzenden/ontvangen volgt het standaard Wi-Fi-/Bluetooth-patroon. Aan de rand van het bereik ziet u waarschijnlijk dat de invoer niet meer goed is, totdat de verbinding volledig is verbroken, maar nadat u weer binnen het bereik bent, zou de invoer snel opnieuw verbinding moeten maken.
1. **Wat is implementatiedichtheid per vierkante meter?**
    1. Dit is afhankelijk van uw netwerkinfrastructuur.
1. **Kan het apparaat de infrastructuur als client gebruiken?**
    1. Ja
1. **Welk protocol wordt gebruikt?**
    1. HoloLens gebruikt geen eigen protocollen
1. **Updatefrequentie van het besturingssysteem: wat is de frequentie van updates van het besturingssysteem voor de HL?  Is er een vast schema?  Brengt Microsoft beveiligingspatches uit, zoals nodig, enzovoort.**
    1. Microsoft biedt updates van het besturingssysteem aan HoloLens op exact dezelfde manier als voor Windows 10. Normaal gesproken zijn er twee belangrijke updates per jaar, één in het voorjaar, één in de lente. Omdat HoloLens een Windows-apparaat is, is het updateconcept hetzelfde als bij elk ander Windows-apparaat. Microsoft brengt zo nodig beveiligingspatches uit en volgt hetzelfde concept als op elk ander Windows-apparaat.
1. **Besturingssysteemverharding: welke opties zijn er om het besturingssysteem te harden?  Kunnen we overbodige apps of services verwijderen of afsluiten?**
    1. HoloLens gedraagt zich als een smartphone. Het is vergelijkbaar met andere moderne Windows-apparaten. HoloLens kan worden beheerd door Microsoft Intune of andere moderne oplossingen voor apparaatbeheer, zoals MobileIron, Airwatch of Soti. Er zijn beleidsregels die u in deze beheersystemen kunt instellen om beveiligingsbeleid op het apparaat te plaatsen en om het apparaat te harden. Indien nodig kunt u ook overbodige toepassingen verwijderen.
1. **Hoe worden softwaretoepassingen beheerd en bijgewerkt? Welk besturingselement hebben we om te definiëren welke apps worden geladen en welk app-updateproces voor apps die in de Microsoft Store wonen?**
    1. HoloLens haalt alleen softwaretoepassingen op via de Windows Store. Alleen Appx-toepassingspakketten kunnen worden geïnstalleerd, die zijn ontwikkeld voor het gebruik van HoloLens. U kunt dit zien in de Microsoft Store met een klein logo naast de toepassing die het HoloLens-apparaat toont. Alle besturingselementen die u over het beheer van Store-toepassingen hebt, zijn ook van toepassing op HoloLens. U kunt het concept van de officiële winkel of de store voor bedrijven gebruiken. Apps kunnen aan de zijkant worden geladen (handmatig proces voor het laden van een app op een Windows-apparaat) of kunnen worden beheerd via een MDM, zodat apps automatisch uit de Store worden gehaald wanneer dat nodig is.
1. **Wat is de frequentie van updates voor apps in de Store voor HoloLens?**
    1. Aangezien we hetzelfde concept van de Microsoft Store apps van hier volgen en er apps vandaan halen, wordt de updatecyclus bepaald door de ontwikkelaar van de toepassing. Alle beheeropties die u hebt om het updatemechanisme in de store te beheren, zijn ook van toepassing op HoloLens.
1. **Is er een beveiligde opstartmogelijkheid voor de HoloLens?**
    1. Ja
1. **Is er een mogelijkheid om randapparatuurondersteuning van het apparaat uit te schakelen of los te koppelen?**
    1. Ja
1. **Is er een mogelijkheid om het gebruik van poorten op het apparaat te controleren of uit te schakelen?**
    1. De HoloLens bevat slechts twee poorten (één voor draadloze apparaten en één voor laden of verbinding maken met pc's). Er is geen mogelijkheid om de poort uit te schakelen vanwege functionaliteit en herstelredenen.
1. **Antivirus, eindpuntdetectie, IPS, lijst met toegestane apps: elke mogelijkheid om antivirusprogramma's, eindpuntdetectie, IPS, lijst met toegestane app-besturingselementen, enzovoort uit te voeren.**
    1. Windows Holographic for Business (commerciële suite) biedt ondersteuning voor Windows Defender Smart Screen. Als een antivirusbedrijf de app zou maken en publiceren naar de Universeel Windows-platform, kan deze worden gedownload op HoloLens. Op dit moment hebben geen bedrijven dit gedaan voor HoloLens.
    1. Apps toestaan is mogelijk met behulp van de Microsoft Enterprise Store, waar u alleen kunt kiezen welke specifieke apps kunnen worden gedownload. Via MDM kunt u ook vergrendelen welke specifieke apps kunnen worden uitgevoerd of zelfs op het apparaat kunnen worden gezien.
1. **Kunnen we het apparaat in quarantaine plaatsen vanaf het prod-netwerk totdat we het apparaat bijwerken als het voor langere tijd offline is geweest?  Bijvoorbeeld: het apparaat zit al een periode (zes maanden) in een lade die niet is ingeschakeld en heeft geen updates, patches, enzovoort ontvangen.  Wanneer wordt geprobeerd het netwerk te gebruiken, kunnen we het markeren en zeggen dat u moet bijwerken op een ander netwerk voordat u de klachten krijgt om lid te worden van het netwerk.**
    1. Dit is iets dat kan worden beheerd op infrastructuurniveau door een MDM- of een on-prem-server. Het apparaat kan worden gemarkeerd als niet-compatibel als het niet voldoet aan een opgegeven updateversie.
1. **Bevat Microsoft achterdeuren of toegang tot services waarmee Microsoft verbinding kan maken met het apparaat voor schermdeling of externe ondersteuning?**
    1. Nee
1. **Wanneer er een PKI-certificaat wordt gegenereerd voor vertrouwde communicatie, willen we dat het certificaat wordt gegenereerd op het apparaat, zodat we weten dat het alleen op dat apparaat staat, uniek is voor dat apparaat en niet kan worden geëxporteerd of gebruikt om het apparaat te imiteren. Is dit waar voor HoloLens? Zo niet, is er dan een mogelijke beperking?**
    1. CSR voor SCEP wordt gegenereerd op het apparaat zelf. Intune en de on-premises SCEP-connector helpen de aanvragen zelf te beveiligen door een uitdagingsreeks toe te voegen en te verifiëren die naar de client wordt verzonden.
    1. Omdat HoloLens (1e Gen en 2e Generatie) een TPM-module hebben, worden deze certificaten opgeslagen in de TPM-module en kunnen ze niet worden geëxtraheerd. Zelfs als deze kan worden geëxtraheerd, kunnen de tekenreeksen van de uitdaging niet worden geverifieerd op een ander apparaat, waardoor de certificaten/sleutels onbruikbaar worden op verschillende apparaten.
