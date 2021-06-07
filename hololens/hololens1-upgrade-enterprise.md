---
title: Functies Windows Holographic for Business ontgrendelen
description: Wanneer u een upgrade naar Windows Holographic for Business, biedt HoloLens extra functies die zijn ontworpen voor bedrijven.
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
ms.openlocfilehash: 8d42c935e698f156aed894e4fa5012c9f04d8d49
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/19/2021
ms.locfileid: "111377867"
---
# <a name="unlock-windows-holographic-for-business-features"></a>Functies Windows Holographic for Business ontgrendelen

> [!IMPORTANT]
> Deze pagina is alleen van toepassing op HoloLens 1st Gen.

Microsoft HoloLens is beschikbaar in de *Development Edition*, met Windows Holographic (een editie van Windows 10 die is ontworpen voor HoloLens) en in de [Commercial Suite,](hololens-commercial-features.md)die extra functies biedt die zijn ontworpen voor bedrijven.

Wanneer u de Commercial Suite aanschaft, ontvangt u een licentie voor het upgraden van Windows Holographic naar Windows Holographic for Business. U kunt deze licentie toepassen op het apparaat met behulp van de [MDM-provider (Mobile Device Management)](#edition-upgrade-by-using-mdm) van de organisatie of een [inrichtingspakket.](#edition-upgrade-by-using-a-provisioning-package)

> [!TIP]
> In Windows 10 versie 1803 kunt u controleren of de HoloLens is bijgewerkt naar de zakelijke editie door  >  **Instellingensysteem te selecteren.**

## <a name="edition-upgrade-by-using-mdm"></a>Editie-upgrade met behulp van MDM

De enterprise-licentie kan worden toegepast door elke MDM-provider die ondersteuning biedt voor [de CSP (WindowsLicensing Configuration Service Provider).](https://msdn.microsoft.com/library/windows/hardware/dn904983.aspx) De nieuwste versie van de Microsoft MDM-API biedt ondersteuning voor Windows CSP voorlicensing.

Zie Upgrade devices [running Windows Holographic to Windows Holographic for Business](https://docs.microsoft.com/intune/holographic-upgrade)(Apparaten met Windows Holographic upgraden naar Windows Holographic for Business) voor stapsgewijle instructies voor het upgraden van HoloLens met behulp van Microsoft Intune.

 Bij andere MDM-providers kunnen de specifieke stappen voor het instellen en implementeren van het beleid variëren.

## <a name="edition-upgrade-by-using-a-provisioning-package"></a>Editie-upgrade met behulp van een inrichtingspakket

Inrichtingspakketten zijn bestanden die zijn gemaakt door het hulpprogramma Windows Configuration Designer waarmee een opgegeven configuratie op een apparaat wordt toegepast.

### <a name="create-a-provisioning-package-that-upgrades-the-windows-holographic-edition"></a>Een inrichtingspakket maken dat een upgrade voor de Windows Holographic-editie heeft

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

1. Selecteer **Volgende** om de uitvoerlocatie op te geven waar u het inrichtingspakket naartoe wilt laten gaan zodra het is gebouwd. Windows ICD gebruikt standaard de projectmap als uitvoerlocatie.

    U kunt eventueel Bladeren selecteren **om de** standaarduitvoerlocatie te wijzigen.

1. Selecteer **Next**.

1. Selecteer **Bouwen om** te beginnen met het bouwen van het pakket. Op de buildpagina worden de projectgegevens weergegeven en de voortgangsbalk geeft de buildstatus aan.

1. Wanneer de build is voltooid, selecteert u **Voltooien.**

### <a name="apply-the-provisioning-package-to-hololens"></a>Het inrichtingspakket toepassen op HoloLens

1. Sluit het apparaat met behulp van de USB-kabel aan op een pc. Start het apparaat, maar ga  niet verder dan de pagina die past bij de eerste installatie (de eerste pagina met het blauwe vak). Op de pc wordt HoloLens weergegeven als een apparaat in Verkenner.

    > [!NOTE]
    > Als op het HoloLens-apparaat Windows 10 versie 1607 of eerder wordt uitgevoerd, opent u Verkenner door kort op **de knoppen Volume** down en Aan/uit op het apparaat te drukken en vrij te geven. 

1. Sleep in Verkenner het inrichtingspakket (.ppkg) naar de apparaatopslag.

1. Terwijl HoloLens nog  steeds op de pagina passend is, drukt u even op **volume** omlaag en laat u de aan/uit-knoppen  tegelijkertijd weer los.

1. HoloLens vraagt u of u het pakket vertrouwt en dit wilt toepassen. Bevestig dat u het pakket vertrouwt.

1. U ziet of het pakket al dan niet is toegepast. Als het niet is toegepast, kunt u het pakket herstellen en het opnieuw proberen. Als dit lukt, gaat u verder met het instellen van het apparaat.
