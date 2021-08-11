---
title: Functies Windows Holographic for Business ontgrendelen
description: Wanneer u een upgrade naar Windows Holographic for Business, HoloLens extra functies die zijn ontworpen voor bedrijven.
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/16/2019
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 7cf35a10a5f18dc0ccca876230b1677c6eca54ad116f0b2045fc1b269ac6c4b0
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/05/2021
ms.locfileid: "115661885"
---
# <a name="unlock-windows-holographic-for-business-features"></a>Functies Windows Holographic for Business ontgrendelen

> [!IMPORTANT]
> Deze pagina is alleen van toepassing HoloLens eerste generatie.

Microsoft HoloLens is beschikbaar in de *Development Edition*, die wordt uitgevoerd Windows Holographic (een editie van Windows 10 die is ontworpen voor HoloLens) en in de [Commercial Suite](hololens-commercial-features.md), die extra functies biedt die zijn ontworpen voor bedrijven.

Wanneer u de Commercial Suite aanschaft, ontvangt u een licentie die wordt Windows Holographic naar Windows Holographic for Business. U kunt deze licentie toepassen op het apparaat met behulp van de [MDM-provider (Mobile Device Management)](#edition-upgrade-by-using-mdm) van de organisatie of een [inrichtingspakket.](#edition-upgrade-by-using-a-provisioning-package)

> [!TIP]
> In Windows 10 versie 1803 kunt u controleren of de HoloLens is bijgewerkt naar de bedrijfseditie door **Instellingen**  >  **Selecteren.**

## <a name="edition-upgrade-by-using-mdm"></a>Editie-upgrade met behulp van MDM

De enterprise-licentie kan worden toegepast door elke MDM-provider die ondersteuning biedt voor [de CSP (WindowsLicensing Configuration Service Provider).](https://msdn.microsoft.com/library/windows/hardware/dn904983.aspx) De nieuwste versie van de Microsoft MDM-API biedt ondersteuning voor Windows CSP voorlicensing.

Zie Upgrade devices [running Windows Holographic](/intune/holographic-upgrade)to Windows Holographic for Business (Apparaten Windows Holographic upgraden naar Windows Holographic for Business) voor stapsgewijse instructies voor het upgraden van HoloLens met behulp van Microsoft Intune.

 Bij andere MDM-providers kunnen de specifieke stappen voor het instellen en implementeren van het beleid variëren.

## <a name="edition-upgrade-by-using-a-provisioning-package"></a>Editie-upgrade met behulp van een inrichtingspakket

Inrichtingspakketten zijn bestanden die zijn gemaakt door het hulpprogramma Windows Configuration Designer waarmee een opgegeven configuratie op een apparaat wordt toegepast.

### <a name="create-a-provisioning-package-that-upgrades-the-windows-holographic-edition"></a>Een inrichtingspakket maken dat een upgrade voor de Windows Holographic-editie

1. [Maak een inrichtingspakket voor HoloLens.](hololens-provisioning.md)
1. Ga naar **Runtime-instellingen**  >  **EditionUpgrade** en selecteer **EditionUpgradeWithLicense.**

    ![Editie upgraden met licentie-instelling geselecteerd](images/icd1.png)

1. Zoek het XML-licentiebestand dat is opgegeven toen u de Commercial Suite hebt gekocht.

    > [!NOTE]
    > U kunt aanvullende [instellingen configureren in het inrichtingspakket](hololens-provisioning.md).

1. In het menu **Bestand** selecteert u **Opslaan**. 

1. Lees de waarschuwing dat projectbestanden gevoelige informatie kunnen bevatten en klik op **OK.**

    > [!IMPORTANT]
    > Wanneer u een inrichtingspakket bouwt, kunt u gevoelige informatie opnemen in de projectbestanden en het inrichtingspakketbestand (.ppkg). Hoewel u de mogelijkheid hebt om het PPKG-bestand te versleutelen, worden projectbestanden niet versleuteld. Sla de projectbestanden op een veilige locatie op en verwijder de projectbestanden wanneer ze niet meer nodig zijn.

1. Selecteer in **het** menu Exporteren de optie **Inrichtingspakket.**

1. Wijzig **Eigenaar** in **IT-beheerder**, waarmee de prioriteit van dit inrichtingspakket hoger is dan die van andere bronnen die op dit apparaat worden toegepast en selecteer **vervolgens Volgende.**

1. Stel een waarde in voor **Pakketversie**.

    > [!TIP]
    > U kunt wijzigingen aanbrengen in bestaande pakketten en het versienummer wijzigen om eerder toegepaste pakketten bij te werken.

1. Selecteer **volgende in Beveiligingsdetails selecteren voor** het **inrichtingspakket.**

1. Selecteer **Volgende** om de uitvoerlocatie op te geven waar u het inrichtingspakket naartoe wilt laten gaan zodra het is gebouwd. Standaard gebruikt Windows ICD de projectmap als uitvoerlocatie.

    U kunt eventueel Bladeren selecteren **om de** standaarduitvoerlocatie te wijzigen.

1. Selecteer **Next**.

1. Selecteer **Bouwen om** te beginnen met het bouwen van het pakket. Op de buildpagina worden de projectgegevens weergegeven en de voortgangsbalk geeft de buildstatus aan.

1. Wanneer de build is voltooid, selecteert u **Voltooien.**

### <a name="apply-the-provisioning-package-to-hololens"></a>Pas het inrichtingspakket toe op HoloLens

1. Sluit het apparaat met behulp van de USB-kabel aan op een pc. Start het apparaat, maar ga  niet verder dan de pagina passend van de eerste installatie -ervaring (de eerste pagina met het blauwe vak). Op de pc worden HoloLens weergegeven als een apparaat in Verkenner.

    > [!NOTE]
    > Als op het HoloLens-apparaat Windows 10 versie 1607 of eerder wordt uitgevoerd, opent u Verkenner door  kort op **de knoppen Volume** down en Aan/uit op het apparaat te drukken en vrij te geven.

1. Sleep in Verkenner het inrichtingspakket (.ppkg) naar de apparaatopslag.

1. Terwijl HoloLens nog steeds op  de pagina passend is, drukt u even op **volume** omlaag en laat u de aan/uit-knoppen  tegelijkertijd weer los.

1. HoloLens wordt u gevraagd of u het pakket vertrouwt en dit wilt toepassen. Bevestig dat u het pakket vertrouwt.

1. U ziet of het pakket al dan niet is toegepast. Als het niet is toegepast, kunt u het pakket herstellen en het opnieuw proberen. Als dit lukt, gaat u verder met het instellen van het apparaat.
