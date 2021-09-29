---
ms.openlocfilehash: 3d6b36124cd50dcc9f420227cb7787f0d787c013
ms.sourcegitcommit: c73cdefbdb4411f6a187cc38bb2570dadeb156bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/28/2021
ms.locfileid: "129221023"
---
# <a name="microsoft-intune-single-app-kiosk-template"></a>[Microsoft Intune kiosksjabloon voor één app maken](#tab/uisak)

### <a name="microsoft-intune-single-app-kiosk-template"></a>Microsoft Intune kiosksjabloon voor één app maken

1. Een configuratieprofiel maken <br>
<kbd>
    <img alt="Create a configuration profile" src="../images/kiosk-steps/kiosk-template-sa-1.png"/>
</kbd>

<br>

2. Kiosksjabloon kiezen <br>
<kbd>
    <img alt="Create a kiosk profile" src="../images/kiosk-steps/kiosk-template-sa-2.png" width="415" height="530" />
</kbd>

<br>

3. Kies of u één of meerdere app-kiosken wilt gebruiken en kies ook een soort gebruikerstargeting voor de kioskmodus <br>
<kbd>
    <img alt="Select single app kiosk mode" src="../images/kiosk-steps/kiosk-template-sa-3.png"/>
</kbd>

<br>

4. Kies de app die u wilt uitvoeren in de kioskmodus <br>
<kbd>
    <img alt="Choose the app" src="../images/kiosk-steps/kiosk-template-sa-4.png"/>
</kbd>

<br>

5. Laat de overige opties zoals ze zijn <br>
<kbd>
    <img alt="Leave options" src="../images/kiosk-steps/kiosk-template-sa-5.png"/>
</kbd>

<br>

6. Kies aan welke groepen/apparaten of gebruikers dit configuratieprofiel moet worden toegewezen <br> 
<kbd>
    <img alt="Choose how to assign" src="../images/kiosk-steps/kiosk-template-sa-6.png"/>
</kbd>

7. Controleren en maken om configuratieprofiel op te slaan
8. Voer MDM-synchronisatie uit vanaf het apparaat of in Intune om configuratie toe te passen op het apparaat. Apparaten synchroniseren vanuit [Intune](/mem/intune/remote-actions/device-sync#sync-a-device) of op een apparaat via **Instellingen -> Accounts -> Work or school ->** selecteer het verbonden account **-> Info -> Sync**
9. Meld u aan als de doelgebruiker om kiosk te ervaren.

# <a name="microsoft-intune-multi-app-kiosk-template"></a>[Microsoft Intune kiosksjabloon voor meerdere apps maken](#tab/uimak)

### <a name="microsoft-intune-multi-app-kiosk-template"></a>Microsoft Intune kiosksjabloon voor meerdere apps maken

1. Een configuratieprofiel maken <br>
<kbd>
    <img alt="Create a configuration profile" src="../images/kiosk-steps/kiosk-template-sa-1.png"/>
</kbd>

<br>

2. Kiosksjabloon kiezen <br>
<kbd>
    <img alt="Create a kiosk profile" src="../images/kiosk-steps/kiosk-template-sa-2.png" width="415" height="530" />
</kbd>

<br>

3. Kies of u één of meerdere app-kiosken wilt gebruiken en kies ook een soort gebruikerstargeting voor de kioskmodus <br>
<kbd>
    <img alt="Select single app kiosk mode" src="../images/kiosk-steps/kiosk-template-mak-3.png"/>
</kbd>

<br>

4. Kies de app(s) die u wilt uitvoeren in de kioskmodus <br>
<kbd>
    <img alt="Choose the app(s)" src="../images/kiosk-steps/kiosk-template-mak-4.png"/>
</kbd>

<br>

5. Laat de overige opties zoals ze zijn <br>
<kbd>
    <img alt="Leave options" src="../images/kiosk-steps/kiosk-template-sa-5.png"/>
</kbd>

<br>

6. Kies aan welke groepen/apparaten of gebruikers dit configuratieprofiel moet worden toegewezen <br> 
<kbd>
    <img alt="Choose how to assign" src="../images/kiosk-steps/kiosk-template-sa-6.png"/>
</kbd>

<br>

7. Controleren en maken om configuratieprofiel op te slaan
8. Voer MDM-synchronisatie uit vanaf het apparaat of in Intune om configuratie toe te passen op het apparaat. Apparaten synchroniseren vanuit [Intune](/mem/intune/remote-actions/device-sync#sync-a-device) of op een apparaat via **Instellingen -> Accounts -> Work or school ->** selecteer het verbonden account **-> Info -> Sync**
9. Meld u aan als de doelgebruiker om kiosk te ervaren.

# <a name="microsoft-intune-custom-template"></a>[Microsoft Intune sjabloon maken](#tab/intunecustom)

### <a name="microsoft-intune-custom-template"></a>Microsoft Intune sjabloon maken

1. Maak een XML-configuratie voor de gewenste kioskervaring. Bekijk [hier voorbeelden](../hololens-kiosk-reference.md#kiosk-xml-code-samples) om te beginnen.

1. Een aangepast configuratieprofiel maken <br>
<kbd>
    <img alt="Create a custom configuration profile" src="../images/kiosk-steps/kiosk-custom-1.png"/>
</kbd>

<br>

3. Geef de naam van het aangepaste configuratieprofiel op en klik op Toevoegen in de sectie Configuratie-instellingen om OMA-URI-instellingen toe te voegen. <br>
<kbd>
    <img alt="Name and add" src="../images/kiosk-steps/kiosk-custom-2.png"/>
</kbd>

<br>

4. Geef de naam van oma-URI-instellingen op.

    1. Voer in het tekstvak OMA-URI **./Device/Vendor/MSFT/AssignedAccess/Configuration in**
    1. Kies Gegevenstype als **Tekenreeks.**
    1. Kopieer in het tekstvak waarde het XML-bestand voor de configuratie van toegewezen toegang (zie referentiekoppelingen voor voorbeelden op basis van uw scenario en werk zo nodig bij voordat u kopieert en plakt).
    1. Selecteer de knop Opslaan om de instelling en configuratie op te slaan.

    <kbd>
        <img alt="Specify OMA-URI settings" src="../images/kiosk-steps/kiosk-custom-3.png"/>
    </kbd>

<br>

5. Kies aan welke groepen/apparaten of gebruikers dit configuratieprofiel moet worden toegewezen. <br>
<kbd>
    <img alt="Choose how to assign" src="../images/kiosk-steps/kiosk-custom-4.png"/>
</kbd>

<br>

6. Controleer en maak om het configuratieprofiel op te slaan.
1. Voer MDM-synchronisatie uit vanaf het apparaat of in Intune om configuratie toe te passen op het apparaat. Apparaten synchroniseren vanuit [Intune](/mem/intune/remote-actions/device-sync#sync-a-device) of op een apparaat via **Instellingen -> Accounts -> Work or school ->** selecteer het verbonden account **-> Info -> Sync**
1. Meld u aan als de doelgebruiker om kiosk te ervaren.

# <a name="runtime-provisioning---multi-app"></a>[Runtime inrichten - Meerdere apps](#tab/ppkgmak)

### <a name="runtime-provisioning---multi-app"></a>Runtime inrichten - Meerdere apps

1. Maak een XML-configuratie voor de gewenste kioskervaring. Bekijk [hier voorbeelden](../hololens-kiosk-reference.md#kiosk-xml-code-samples) om te beginnen.

1. Open [Windows Configuration Designer.](https://www.microsoft.com/store/apps/9nblggh4tx22)

1. Selecteer op de startpagina **De apparaten HoloLens inrichten.** <br>
<kbd>
    <img alt="Selecting provision HoloLens" src="../images/kiosk-steps/kiosk-provision-1.png"/>
</kbd>

<br>

4. Selecteer **HoloLens 2 apparaten inrichten en** selecteer vervolgens Volgende. <br>
<kbd>
    <img alt="Select HoloLens 2" src="../images/kiosk-steps/kiosk-provision-2.png"/>
</kbd>

<br>

5. Noem uw project. Schrijf eventueel een beschrijving. Selecteer **Voltooien om** door te gaan.

6. Selecteer linksonder in het scherm Overschakelen naar **geavanceerde editor.** Bevestig de overstap naar de geavanceerde editor door Ja te **selecteren.** <br>

    <kbd>
        <img alt="Switch to advanced editor" src="../images/kiosk-steps/kiosk-provision-2.png"/>
    </kbd>

<br>

7. Vouw aan de linkerkant Runtime-instellingen en ToegewezenAccess uit en selecteer **MultiAppAssignedAccess.** <br>

    <kbd>
        <img alt="select MultiAppAssignedAccess" src="../images/kiosk-steps/kiosk-provision-3.png"/>
    </kbd>

<br>

8. Selecteer de knop **Bladeren...** om de bestandenverkenner te openen. En selecteer het geconfigureerde XML-bestand van de kiosk.

9. Selecteer **Exporteren** en vervolgens **Inrichtingspakket.**

    <kbd>
        <img alt="Export package" src="../images/kiosk-steps/kiosk-provision-4.png"/>
    </kbd>

<br>

10. Wijzig het type eigenaar in **IT-beheerder**. <br>

    <kbd>
        <img alt="Exporting as IT Admin" src="../images/kiosk-steps/kiosk-provision-5.png"/>
    </kbd>

<br>

11. Selecteer drie keer **Volgende**. Selecteer vervolgens **Build.**

12. Nadat het inrichtingspakket is gebouwd, opent u de map Uitvoerlocatie. Het PPKG-bestand is uw inrichtingspakket. Optionele stap: Sla uw project op.

13. U kunt nu uw inrichtingspakket toepassen. U kunt een [inrichtingspakket](../hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup) toepassen op HoloLens tijdens de installatie of een inrichtingspakket toepassen op HoloLens [na de installatie.](../hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup)

14. Meld u aan als de doelgebruiker om kiosk te ervaren.

# <a name="runtime-provisioning---single-app"></a>[Runtime inrichten - Enkele app](#tab/ppkgsak)

### <a name="runtime-provisioning---single-app"></a>Runtime inrichten - Enkele app

1. Open [Windows Configuration Designer.](https://www.microsoft.com/store/apps/9nblggh4tx22)

1. Selecteer op de startpagina **De apparaten HoloLens inrichten.** <br>

    <kbd>
        <img alt="Selecting provision HoloLens" src="../images/kiosk-steps/kiosk-provision-1.png"/>
    </kbd>

<br>

3. Selecteer **HoloLens 2 apparaten inrichten en** selecteer vervolgens Volgende. <br>

    <kbd>
        <img alt="Select HoloLens 2" src="../images/kiosk-steps/kiosk-provision-2.png"/>
    </kbd>

<br>

4. Noem uw project. Schrijf eventueel een beschrijving. Selecteer **Voltooien om** door te gaan.

5. Selecteer linksonder in het scherm Overschakelen naar **geavanceerde editor.** Bevestig de overstap naar de geavanceerde editor door Ja te **selecteren.** <br>

    <kbd>
        <img alt="Switch to advanced editor" src="../images/kiosk-steps/kiosk-provision-2.png"/>
    </kbd>

<br>

6. Vouw aan de linkerkant Runtime-instellingen uit, ToegewezenAccess en selecteer **ToegewezenAccessInstellingen.** <br>

    <kbd>
        <img alt="Navigate to assigned access settings" src="../images/kiosk-steps/kiosk-provision-sak-1.png"/>
    </kbd>

<br>

7. Definieer uw kiosk in het tekstvak. Met het volgende maakt u bijvoorbeeld een kiosk voor één app voor een lokaal account met de naam LocalAccount, dat de instellingen-app is.
```{"Account":"LocalAccount","AUMID":"BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy!App"}```

8. Selecteer **Exporteren** en vervolgens **Inrichtingspakket.** <br>

    <kbd>
        <img alt="Export package" src="../images/kiosk-steps/kiosk-provision-4.png"/>
    </kbd>

<br>

9. Wijzig het type eigenaar in **IT-beheerder**. <br>

    <kbd>
        <img alt="Exporting as IT Admin" src="../images/kiosk-steps/kiosk-provision-5.png"/>
    </kbd>

<br>

10. Selecteer drie keer **Volgende**. Selecteer vervolgens **Build.**

11. Nadat het inrichtingspakket is gebouwd, opent u de map Uitvoerlocatie. Het PPKG-bestand is uw inrichtingspakket. Optionele stap: Sla uw project op.

12. U kunt nu uw inrichtingspakket toepassen. U kunt een [inrichtingspakket](../hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup) toepassen op HoloLens tijdens de installatie of een inrichtingspakket toepassen op HoloLens [na de installatie.](../hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup)