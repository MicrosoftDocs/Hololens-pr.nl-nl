---
title: HoloLens BitLocker-versleuteling
description: Meer informatie over het inschakelen van BitLocker-apparaatversleuteling om bestanden te beveiligen die zijn opgeslagen op uw HoloLens-mixed reality apparaten.
ms.prod: hololens
ms.mktglfcycl: manage
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 01/26/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 2929cbea826e0cc92a72550c7874995506b94257
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/25/2021
ms.locfileid: "111377763"
---
# <a name="hololens-1st-gen-bitlocker-encryption"></a>HoloLens (1e generatie) BitLocker-versleuteling

HoloLens (eerste generatie) en HoloLens 2 ondersteunen apparaatversleuteling met bitLocker, maar BitLocker is altijd ingeschakeld op HoloLens 2.

In dit artikel vindt u hulp bij het inschakelen en beheren van BitLocker op HoloLens (eerste generatie).

Op HoloLens (1e generatie) kunt u BitLocker-apparaatversleuteling handmatig inschakelen of met behulp van Mobile Device Management (MDM). Volg deze instructies om [BitLocker-apparaatversleuteling in teschakelen](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption) om bestanden en informatie te beveiligen die zijn opgeslagen op de HoloLens. Apparaatversleuteling helpt uw gegevens te beveiligen met behulp van de AES-CBC 128-versleutelingsmethode, die gelijk is aan [EncryptionMethodByDriveType-methode 3](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp#encryptionmethodbydrivetype) in de BitLocker-configuratieserviceprovider (CSP). Medewerkers met de juiste versleutelingssleutel (zoals een wachtwoord) kunnen deze ontsleutelen of gegevensherstel uitvoeren.

## <a name="enable-device-encryption-using-mdm"></a>Apparaatversleuteling inschakelen met MDM

U kunt uw MDM-provider (Mobile Device Management) gebruiken om een beleid toe te passen dat apparaatversleuteling vereist. Het beleid dat moet worden gebruikt, is de instelling [Security/RequireDeviceEncryption](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-requiredeviceencryption) in de beleids-CSP.

[Zie de instructies voor het inschakelen van apparaatversleuteling met Microsoft Intune.](https://docs.microsoft.com/intune/compliance-policy-create-windows#windows-holographic-for-business)

Zie de documentatie van uw MDM-provider voor instructies voor andere MDM-hulpprogramma's. Als uw MDM-provider aangepaste URI vereist voor apparaatversleuteling, gebruikt u de volgende configuratie:

- **Naam:** een naam naar keuze
- **Beschrijving:** optioneel
- **OMA-URI:**`./Vendor/MSFT/Policy/Config/Security/RequireDeviceEncryption`
- **Gegevenstype:** geheel getal
- **Waarde**: `1`

## <a name="enable-device-encryption-using-a-provisioning-package"></a>Apparaatversleuteling inschakelen met behulp van een inrichtingspakket

Inrichtingspakketten zijn bestanden die zijn gemaakt door het hulpprogramma Windows Configuration Designer waarmee een opgegeven configuratie op een apparaat wordt toegepast. 

### <a name="create-a-provisioning-package-that-upgrades-the-windows-holographic-edition-and-enables-encryption"></a>Een inrichtingspakket maken waarmee de Windows Holographic-editie wordt geupgraded en versleuteling wordt mogelijk gemaakt

1. [Maak een inrichtingspakket voor HoloLens.](hololens-provisioning.md)
1. Ga naar **Runtime settings**  >  **Policies**  >  **Security** en selecteer **RequireDeviceEncryption.**

    ![Instelling apparaatversleuteling vereisen die is geconfigureerd op Ja](images/device-encryption.png)

1. Zoek het XML-licentiebestand dat is opgegeven toen u de Commercial Suite hebt gekocht.

1. Blader naar en selecteer het XML-licentiebestand dat is opgegeven bij de aankoop van de Commerciële suite.
    > [!NOTE]
    > U kunt aanvullende [instellingen configureren in het inrichtingspakket](hololens-provisioning.md).

1. Klik in het menu **Bestand** op **Opslaan**. 

1. Lees de waarschuwing waarin wordt uitgelegd dat projectbestanden gevoelige informatie kunnen bevatten en klik op **OK.**

    > [!IMPORTANT]
    > Wanneer u een inrichtingspakket bouwt, kunt u gevoelige informatie opnemen in de projectbestanden en het inrichtingspakketbestand (.ppkg). Hoewel u de mogelijkheid hebt om het PPKG-bestand te versleutelen, worden projectbestanden niet versleuteld. Sla de projectbestanden op een veilige locatie op en verwijder de projectbestanden wanneer ze niet meer nodig zijn.

1. Klik in **het** menu Exporteren op **Inrichtingspakket.**
1. Wijzig **Eigenaar** in **IT-beheerder,** waarmee de prioriteit van dit inrichtingspakket hoger wordt ingesteld dan de inrichtingspakketten die vanuit andere bronnen op dit apparaat zijn toegepast en selecteer **vervolgens Volgende.**
1. Stel een waarde in voor **Pakketversie**.

    > [!TIP]
    > U kunt wijzigingen aanbrengen in bestaande pakketten en het versienummer wijzigen om eerder toegepaste pakketten bij te werken.

1. Klik in **Beveiligingsdetails selecteren voor het inrichtingspakket** op **Volgende.**
1. Klik **op** Volgende om de uitvoerlocatie op te geven waar u het inrichtingspakket naartoe wilt laten gaan zodra het is gebouwd. Windows ICD gebruikt standaard de projectmap als uitvoerlocatie.

    U kunt desgewenst op Bladeren klikken om de standaarduitvoerlocatie te wijzigen.

1. Klik op **Volgende**.
1. Klik **op Bouwen** om te beginnen met het bouwen van het pakket. De projectgegevens worden weergegeven op de buildpagina en de voortgangsbalk geeft de buildstatus aan.
1. Wanneer de build is voltooid, klikt u op **Voltooien.**

### <a name="apply-the-provisioning-package-to-hololens"></a>Het inrichtingspakket toepassen op HoloLens

1. Sluit het apparaat via USB aan op een pc en  start het apparaat, maar ga niet verder dan de pagina voor passend maken van de eerste installatie (de eerste pagina met het blauwe vak).
1. Druk kort op de knoppen **Volume down en** **Aan/uit.**
1. HoloLens wordt weergegeven als een apparaat in Verkenner op de pc.
1. Sleep in Verkenner het inrichtingspakket (.ppkg) naar de apparaatopslag en zet het neer.
1. Druk kort op de knoppen **Volume down en** **Aan/uit** terwijl u op de pagina aanpassen **staat.**
1. Het apparaat vraagt u of u het pakket vertrouwt en het wilt toepassen. Bevestig dat u het pakket vertrouwt.
1. U ziet of het pakket al dan niet is toegepast. Als dit is mislukt, kunt u het pakket herstellen en het opnieuw proberen. Als dit is gelukt, gaat u verder met het instellen van het apparaat.

> [!NOTE]
> Als het apparaat vóór augustus 2016 is gekocht, moet u zich aanmelden bij het apparaat met een Microsoft-account, de meest recente update van het besturingssysteem downloaden en vervolgens het besturingssysteem opnieuw instellen om het inrichtingspakket toe te passen.

## <a name="verify-device-encryption"></a>Apparaatversleuteling controleren

Versleuteling wordt stil op HoloLens. De versleutelingsstatus van het apparaat controleren:

- Ga op HoloLens naar  >  **Instellingensysteem**  >  **over**. **BitLocker** is **ingeschakeld als** het apparaat is versleuteld. 

    ![Over het scherm met BitLocker ingeschakeld](images/about-encryption.png)
