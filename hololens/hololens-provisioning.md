---
title: Een HoloLens configureren met behulp van een inrichtingspakket (HoloLens)
description: Windows inrichten kunnen IT-beheerders eenvoudig apparaten van eindgebruikers configureren zonder afbeeldingen te maken.
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.custom:
- CI 115190
- CSSTroubleshooting
ms.localizationpriority: medium
ms.date: 10/13/2020
ms.reviewer: Teresa-Motiv
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 9474774b47858003cc11363a5f325f589b0732ab
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/30/2021
ms.locfileid: "123188998"
---
# <a name="configure-hololens-by-using-a-provisioning-package"></a>Een HoloLens configureren met behulp van een inrichtingspakket

[Windows inrichten kunnen](/windows/configuration/provisioning-packages/provisioning-packages) IT-beheerders eenvoudig apparaten van eindgebruikers configureren zonder imaging te maken. Windows Configuration Designer is een hulpprogramma voor het configureren van installatieprogramma's en runtime-instellingen die vervolgens worden ingebouwd in inrichtingspakketten.

Enkele van de HoloLens die u in een inrichtingspakket kunt toepassen, zijn onder andere:

- Upgraden naar [Windows Holographic for Business](hololens1-upgrade-enterprise.md)
- Een lokaal account instellen
- Een verbinding Wi-Fi instellen
- Certificaten toepassen op het apparaat
- Ontwikkelaarsmodus inschakelen
- Configureer de kioskmodus door onze gedetailleerde [instructies te volgen.](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens)

## <a name="provisioning-package-hololens-wizard"></a>Wizard Inrichtingspakket HoloLens inrichten

Met HoloLens wizard kunt u de volgende instellingen configureren in een inrichtingspakket:

- Upgraden naar de Enterprise-editie

    > [!NOTE]
    > Dit mag alleen worden gebruikt voor apparaten HoloLens eerste generatie. Instellingen in een inrichtingspakket worden alleen toegepast als het inrichtingspakket een editie-upgradelicentie voor Windows Holographic for Business bevat of als het apparaat al is geüpgraded naar [Windows Holographic for Business](hololens1-upgrade-enterprise.md).

- De HoloLens first experience (OOBE) configureren
- Het netwerk Wi-Fi configureren
- Schrijf het apparaat in Azure Active Directory of maak een lokaal account
- Certificaten toevoegen
- Ontwikkelaarsmodus inschakelen
- Configureer de kioskmodus door gedetailleerde [instructies te volgen.](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens)

> [!WARNING]
> U moet Windows Configuration Designer uitvoeren op Windows 10 om Azure Active Directory te configureren met behulp van een van de wizards.

Inrichtingspakketten kunnen beheerinstructies en beleidsregels, aangepaste netwerkverbindingen en beleidsregels bevatten, en meer.

> [!TIP]
> Gebruik de bureaubladwizard om een pakket met de algemene instellingen te maken en schakel vervolgens over naar de geavanceerde editor om andere instellingen, apps, beleidsregels, enzovoort toe te voegen.

## <a name="steps-for-creating-provisioning-packages"></a>Stappen voor het maken van inrichtingspakketten

1. **Optie 1:** [Microsoft Store](https://www.microsoft.com/store/apps/9nblggh4tx22). Dit omvat HoloLens 2 mogelijkheden.
2. **Optie 2:** [uit Windows Assessment and Deployment Kit (ADK) voor Windows 10.](https://developer.microsoft.com/windows/hardware/windows-assessment-deployment-kit) Als u Windows Configuration Designer installeert vanuit de Windows ADK, selecteert u **Configuration Designer** in het dialoogvenster Selecteer de functies die u **wilt** installeren. Deze optie omvat geen HoloLens 2 mogelijkheden.

> [!NOTE]
> Als u weet dat u een offline pc gebruikt die toegang nodig heeft tot Windows Configuration Designer, volgt u de instructies [offline app install(hololens-recovery.md#downloading-arc-without-using-the-app-store) voor Advanced Recovery Companion. Maak Windows Configuration Designer uw selectie. 

### <a name="2-create-the-provisioning-package"></a>2. Het inrichtingspakket maken

Gebruik het Windows Configuration Designer om een inrichtingspakket te maken.

1. Open Windows Configuration Designer (standaard %windir%\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86\ICD.exe).

2. Selecteer **Apparaten HoloLens inrichten.**

   ![IcD-startopties.](images/icd-create-options-1703.png)

3. Noem uw project en selecteer **Voltooien.**

4. Lees de instructies op de pagina **Aan de slag** en selecteer **Volgende.** De pagina's voor het inrichten van het bureaublad helpen u bij de volgende stappen.
  
> [!IMPORTANT]
> Wanneer u een inrichtingspakket bouwt, kunt u gevoelige informatie opnemen in de projectbestanden en in het inrichtingspakketbestand (.ppkg). Hoewel u de mogelijkheid hebt om het PPKG-bestand te versleutelen, worden projectbestanden niet versleuteld. U moet de projectbestanden opslaan op een veilige locatie en de projectbestanden verwijderen wanneer ze niet meer nodig zijn.

### <a name="configure-settings"></a>Instellingen configureren

<table>
<tr><td style="width:45%" valign="top"><a id="one"></a><img src="images/one.png" alt="step one"/><img src="images/set-up-device.png" alt="set up device"/></br></br>Blader naar en selecteer het licentiebestand van de onderneming om de editie van HoloLens upgraden.</br></br>U kunt ook Ja of <strong>Nee in-</strong> of <strong>uitschakelen om</strong> delen van de eerste ervaring te verbergen.</br></br>Als u het apparaat wilt instellen zonder dat u verbinding hoeft te maken met een Wi-Fi netwerk, zet Wi-Fi <strong>overslaan op</strong> <strong>Aan.</strong></br></br>Selecteer een regio en tijdzone waarin het apparaat wordt gebruikt. </td><td><img src="images/set-up-device-details.png" alt="Select enterprise licence file and configure OOBE"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="two"></a><img src="images/two.png" alt="step two"/>  <img src="images/set-up-network.png" alt="set up network"/></br></br>In deze sectie kunt u de details van het Wi-Fi draadloze netwerk dat het apparaat automatisch verbinding moet maken. Selecteer hiervoor Aan, voer de SSID, het netwerktype (<strong>Open</strong> of <strong>WPA2-Personal)</strong>in en (als <strong>WPA2-Personal</strong>) het wachtwoord voor het draadloze netwerk. <strong></strong></td><td><img src="images/set-up-network-details-desktop.png" alt="Enter network SSID and type"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="three"></a><img src="images/three.png" alt="step three"/>  <img src="images/account-management.png" alt="account management"/></br></br>U kunt het apparaat registreren bij Azure Active Directory of een lokaal account op het apparaat maken</br></br>Voordat u een configuratiewizard Windows Configureren om bulksgewijs Azure AD-inschrijving te configureren, stelt u <a href="/azure/active-directory/active-directory-azureadjoin-setup" data-raw-source="[set up Azure AD join in your organization](/azure/active-directory/active-directory-azureadjoin-setup)">Azure AD Join in uw organisatie in.</a> Het <strong>maximum aantal apparaten per gebruiker</strong> in uw Azure AD-tenant bepaalt hoe vaak het bulk-token dat u in de wizard krijgt, kan worden gebruikt. Als u het apparaat wilt registreren bij Azure AD, selecteert u die optie en voert u een gebruiksvriendelijke naam in voor het bulk-token dat u met de wizard krijgt. Stel een vervaldatum in voor het token (maximum is 30 dagen na de datum waarop u het token krijgt). Selecteer <strong>Get bulk token</strong>. Voer in <strong>het venster&#39;</strong> u aangemeld krijgen een account in dat machtigingen heeft om een apparaat aan Azure AD te toevoegen en voer vervolgens het wachtwoord in. Selecteer <strong>Accepteren om</strong> de Windows Configuration Designer de benodigde machtigingen te geven. </br></br>Als u een lokaal account wilt maken, selecteert u die optie en voert u een gebruikersnaam en wachtwoord in. </br></br><strong>Belangrijk:</strong> <br />(Alleen Windows 10 versie 1607) Als u een lokaal account in het inrichtingspakket maakt, moet u het wachtwoord elke 42 <strong>dagen</strong> wijzigen met de Instellingen app. Als het wachtwoord in die periode niet is gewijzigd, is het account mogelijk vergrendeld en kan het niet worden aanmelden.  </td><td><img src="images/account-management-details.png" alt="join  Azure AD or create a local  account"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="four"></a><img src="images/four.png" alt="step four"/> <img src="images/add-certificates.png" alt="add certificates"/></br></br>Als u het apparaat wilt inrichten met een certificaat, klikt <strong>u op Een certificaat toevoegen.</strong> Voer een naam in voor het certificaat, blader naar en selecteer het certificaat dat moet worden gebruikt.</td><td><img src="images/add-certificates-details.png" alt="add a certificate"/></td></tr> 
<tr><td style="width:45%" valign="top"><a id="five"></a><img src="images/five.png" alt="step five"/> <img src="images/developer-setup.png" alt="Developer Setup"/></br></br>Schakel <strong>Ja</strong> of <strong>Nee in om</strong> de ontwikkelaarsmodus in te schakelen op HoloLens. <a href="/windows/uwp/get-started/enable-your-device-for-development#developer-mode" data-raw-source="[Learn more about Developer Mode.](/windows/uwp/get-started/enable-your-device-for-development#developer-mode)">Meer informatie over de ontwikkelaarsmodus.</a></td><td><img src="images/developer-setup-details.png" alt="Enable Developer Mode"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="six"></a><img src="images/six.png" alt="step six"/> <img src="images/finish.png" alt="finished"/></br></br>Stel geen wachtwoord in om uw inrichtingspakket te beveiligen. Als het inrichtingspakket wordt beveiligd met een wachtwoord, mislukt het inrichten HoloLens apparaat.</td><td><img src="images/finish-details.png" alt="Protect your package"/></td></tr>
</table>

Selecteer **Maken** als u klaar bent. Dit duurt slechts enkele seconden. Wanneer het pakket is gebouwd, wordt de locatie waar het pakket is opgeslagen weergegeven als een hyperlink onder aan de pagina.

### <a name="3-create-a-provisioning-package-for-hololens-by-using-advanced-provisioning"></a>3. Een inrichtingspakket voor HoloLens maken met behulp van geavanceerde inrichting

> [!NOTE]
> Een inrichtingspakket dat u **maakt** in Geavanceerde inrichting hoeft geen editie-upgradelicentie op te nemen om Windows Holographic for Business succesvol toe te passen op een HoloLens (eerste generatie). [Zie meer over Windows Holographic for Business voor HoloLens (1e generatie)](hololens1-upgrade-enterprise.md).

1. Selecteer op Windows startpagina van Configuration Designer de optie **Geavanceerde inrichting.**
2. Geef in **het venster Projectdetails** invoeren een naam op voor uw project en de locatie voor uw project. Voer desgewenst een korte beschrijving in om uw project te beschrijven.

3. Selecteer **Next**.

4. Selecteer in **het venster Kiezen welke** instellingen u wilt weergeven en configureren **Windows 10 Holographic** en selecteer **vervolgens Volgende.**

5. Selecteer **Finish**.

6. Vouw **Runtime-instellingen uit** en pas het pakket aan met behulp van een van de instellingen die [verder in dit artikel worden beschreven.](#what-you-can-configure)

    > [!IMPORTANT]
    > (Alleen Windows 10 versie 1607) Als u een lokaal account in het inrichtingspakket maakt, moet u het wachtwoord elke 42 **dagen** wijzigen met de Instellingen app. Als het wachtwoord in die periode niet is gewijzigd, is het account mogelijk vergrendeld en kan het niet worden aanmelden. Als het gebruikersaccount is vergrendeld, moet u [een volledig apparaatherstel uitvoeren.](https://developer.microsoft.com/windows/mixed-reality/reset_or_recover_your_hololens#perform_a_full_device_recovery)

7. Selecteer **Bestand**  >  **Opslaan.**

8. Lees de waarschuwing dat projectbestanden gevoelige informatie kunnen bevatten en selecteer **OK.**

    > [!IMPORTANT]
    > Wanneer u een inrichtingspakket bouwt, kunt u gevoelige informatie opnemen in de projectbestanden en in het inrichtingspakketbestand (.ppkg). Hoewel u de mogelijkheid hebt om het PPKG-bestand te versleutelen, worden projectbestanden niet versleuteld. U moet de projectbestanden opslaan op een veilige locatie en de projectbestanden verwijderen wanneer ze niet meer nodig zijn.

9. Selecteer   >  **Inrichtingspakket exporteren.**

10. Wijzig **Eigenaar** in **IT-beheerder.** Hiermee stelt u de prioriteit van dit inrichtingspakket hoger in dan de inrichtingspakketten die vanuit andere bronnen op dit apparaat worden toegepast. Selecteer **Next**.

11. Stel een waarde in voor **Pakketversie**.

    > [!TIP]
    > U kunt wijzigingen aanbrengen in bestaande pakketten en het versienummer wijzigen om eerder toegepaste pakketten bij te werken.

12. Selecteer in **Beveiligingsdetails selecteren voor het inrichtingspakket** de optie **Volgende.**

    > [!WARNING]
    > Als u het inrichtingspakket versleutelt, mislukt het inrichten HoloLens apparaat.  

13. Selecteer **Volgende** om de uitvoerlocatie op te geven waar u het inrichtingspakket naartoe wilt laten gaan zodra het is gebouwd. Standaard gebruikt Windows Configuration Designer de projectmap als uitvoerlocatie.

    U kunt eventueel Bladeren selecteren **om de** standaarduitvoerlocatie te wijzigen.

14. Selecteer **Next**.

15. Selecteer **Bouwen om** te beginnen met het bouwen van het pakket. De projectgegevens worden weergegeven op de buildpagina en de voortgangsbalk geeft de buildstatus aan.

16. Wanneer de build is voltooid, selecteert u **Voltooien.**

<span id="apply" />

## <a name="apply-a-provisioning-package-to-hololens-during-setup"></a>Een inrichtingspakket toepassen op HoloLens tijdens de installatie

HoloLens 2 apparaten op Windows Holographic, versie 2004 of build [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) of hoger, kunnen een USB-station gebruiken om een inrichtingspakket toe te passen. Kopieer gewoon het PPKG-bestand naar de hoofdmap van het USB-station. Inrichtingspakketten worden alleen toegepast als ze zich in de hoofdmap van het USB-station. Meerdere aanwezige inrichtingspakketten worden opeenvolgend toegepast.

HoloLens 2 apparaten op [Windows Holographic-versie 20H2](hololens-release-notes.md#windows-holographic-version-20h2) of hoger hebben nieuwere functies om dit proces te stroomlijnen en vereenvoudigen, waardoor het automatisch wordt. Raadpleeg de volgende secties:

- [Inrichting via USB automatisch starten](hololens-provisioning.md#auto-launch-provisioning-from-usb)
- [Inrichtingspakketten automatisch bevestigen in OOBE](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe)
- [Automatisch inrichten zonder gebruik van de gebruikersinterface](hololens-provisioning.md#automatic-provisioning-without-using-ui)

1. Gebruik de USB-kabel om het apparaat te verbinden met een pc (of USB-station voor HoloLens 2 zoals hierboven wordt vermeld) en start het apparaat vervolgens. Ga niet verder na de **pagina Eerste interactiemoment** van OOBE.
    - Op HoloLens (eerste generatie) bevat deze pagina een blauw vak.
    - Op HoloLens 2 pagina staat de kuntmingbird.

2. Druk kort op de knoppen **Volume down en** **Aan/uit** en laat deze tegelijkertijd los.

3. HoloLens wordt weergegeven als een apparaat in Verkenner op de pc.

4. Sleep in Verkenner het inrichtingspakket (.ppkg) naar de apparaatopslag.

5. Druk kort op de knoppen **Volume down** en **Aan/uit** terwijl u op de pagina Eerste **interactiemoment** van OOBE staat.

6. Het apparaat vraagt u of u het pakket vertrouwt en het wilt toepassen. Bevestig dat u het pakket vertrouwt.

7. U ziet of het pakket al dan niet is toegepast. Als dit is mislukt, kunt u het pakket herstellen en het opnieuw proberen. Als dit is gelukt, gaat u verder met OOBE.

> [!NOTE]
> Als het apparaat vóór augustus 2016 is gekocht, moet u zich aanmelden bij het apparaat met behulp van een Microsoft-account, de meest recente update van het besturingssysteem downloaden en vervolgens het besturingssysteem opnieuw instellen om het inrichtingspakket toe te passen.

### <a name="auto-launch-provisioning-from-usb"></a>Inrichting via USB automatisch starten

- Geautomatiseerde processen die minder gebruikersinteractie mogelijk maken wanneer USB-stations met inrichtingspakketten worden gebruikt tijdens OOBE.

Vóór deze release moesten gebruikers het inrichtingsscherm handmatig starten tijdens OOBE om in te delen met behulp van een combinatie van knoppen. Gebruikers kunnen nu de combinatie van knoppen overslaan met behulp van een inrichtingspakket op een USB-opslagstation.

1. Sluit het USB-station aan met het inrichtingspakket tijdens het eerste interactiemoment van OOBE
1. Wanneer het apparaat gereed is om te worden ingericht, wordt de prompt automatisch geopend met de inrichtingspagina.

Opmerking: Als een USB-station blijft aangesloten terwijl het apparaat wordt opgestart, zal OOBE een bestaand USB-opslagapparaat opsnoemen, evenals extra apparaten die op het net worden aangesloten.

Lees meer over [het toepassen van inrichtingspakketten tijdens OOBE.](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)

### <a name="auto-confirm-provisioning-packages-in-oobe"></a>Inrichtingspakketten automatisch bevestigen in OOBE
- Geautomatiseerd proces dat minder gebruikersinteractie mogelijk maakt. Wanneer de pagina Inrichtingspakket wordt weergegeven, worden alle vermelde pakketten automatisch toegepast.

Wanneer het hoofdscherm voor inrichting wordt weergegeven, telt OOBE 10 seconden af voordat automatisch alle inrichtingspakketten worden toegepast. Gebruikers kunnen binnen deze tien seconden nog steeds bevestigen of annuleren nadat ze de verwachte pakketten hebben gecontroleerd.

### <a name="automatic-provisioning-without-using-ui"></a>Automatische inrichting zonder gebruik van de gebruikersinterface
- Gecombineerde automatische processen voor minder apparaatinteracties voor inrichting. 

Door het automatisch starten van het inrichten van USB-apparaten en de automatische bevestiging van inrichtingspakketten te combineren, kan een gebruiker automatisch HoloLens 2-apparaten inrichten zonder de gebruikersinterface van het apparaat te gebruiken of zelfs het apparaat te laten inrichten. U kunt hetzelfde USB-station en inrichtingspakket blijven gebruiken voor meerdere apparaten. Dit is handig voor het implementeren van meerdere apparaten tegelijk in hetzelfde gebied. 

1. [Maak een inrichtingspakket met](hololens-provisioning.md) [Windows Configuration Designer.](https://www.microsoft.com/store/productId/9NBLGGH4TX22) 
1. Kopieer het pakket naar een USB-opslagstation.
1. [Flash uw HoloLens 2](hololens-insider.md#ffu-download-and-flash-directions) [naar 19041.1361 of nieuwer.](https://aka.ms/hololens2previewdownload) 
1. Wanneer [Advanced Recovery Companion](https://www.microsoft.com/store/productId/9P74Z35SFRS8) klaar is met het flashen van uw apparaat, moet u de USB-C-kabel loskoppelen. 
1. Sluit uw USB-station aan op het apparaat.
1. Wanneer het HoloLens 2 oobe opstart, detecteert het automatisch het inrichtingspakket op het USB-station en start het de inrichtingspagina.
1. Na 10 seconden wordt het inrichtingspakket automatisch toegepast op het apparaat. 

Uw apparaat is nu geconfigureerd en het scherm Inrichten is geslaagd wordt weergegeven.

## <a name="applyremove-a-provisioning-package-to-hololens-after-setup"></a>Een inrichtingspakket toepassen/verwijderen HoloLens na de installatie

> [!NOTE]
> Deze stappen zijn van toepassing op alle HoloLens 2- en HoloLens-apparaten (eerste generatie) op Windows Holographic, versie 1809 en hoger.

Volg deze stappen op uw pc:
1. Maak een inrichtingspakket zoals beschreven in [Create a provisioning package for HoloLens using the HoloLens wizard](hololens-provisioning.md).
2. Verbinding maken het HoloLens een pc met behulp van een USB-kabel. HoloLens wordt weergegeven als een apparaat in Verkenner op de pc.
3. Sleep het inrichtingspakket naar de map Documenten op de HoloLens.

Volg op HoloLens volgende stappen:
1. Ga naar **Instellingen** > **Accounts** > **Toegang tot werk of school**. 
2. Selecteer **in Instellingen** een **inrichtingspakket** toevoegen of verwijderen.
3. Selecteer op de volgende pagina Een **pakket toevoegen om** de bestandsverlener te starten en selecteer uw inrichtingspakket. Als de map leeg is, selecteert u **Dit apparaat en** selecteert u **Documenten.**

Nadat het pakket is toegepast, wordt het weergegeven in de lijst **geïnstalleerde pakketten**. Als u de pakketdetails wilt weergeven of het pakket van het apparaat wilt verwijderen, selecteert u het vermelde pakket.

## <a name="what-you-can-configure"></a>Instellingen die u kunt configureren

Inrichtingspakketten maken gebruik van configuratieserviceproviders (CSP's). Zie Inleiding tot configuratieserviceproviders [(CSP's) voor IT-professionals](/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers)als u niet bekend bent met CSP's.

Wanneer Windows Configuration Designer een **inrichtingspakket** voor Windows Holographic maakt, zijn de instellingen in Beschikbare aanpassingen gebaseerd op CSP's die worden ondersteund [in Windows Holographic.](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) In de volgende tabel worden de instellingen beschreven die u mogelijk wilt configureren voor HoloLens.

![Algemene runtime-instellingen voor HoloLens.](images/icd-settings.png)

| Instelling | Beschrijving |
| --- | --- |
| **Certificaten** | Implementeer een certificaat in HoloLens.  |
| **ConnectivityProfiles** | Implementeer Wi-Fi profiel voor HoloLens.   |
| **EditionUpgrade** | [Upgrade naar Windows Holographic for Business.](hololens1-upgrade-enterprise.md)  |
| **Beleidsregels** | Hiermee kunt u de ontwikkelaarsmodus in de HoloLens. [Beleid dat wordt ondersteund door Windows Holographic for Business](/windows/client-management/mdm/policy-configuration-service-provider#hololenspolicies) |

## <a name="app-install-via-provisioning-package"></a>App installeren via inrichtingspakket

Apps kunnen worden geïnstalleerd via inrichtingspakketten op HoloLens 2 apparaten. Hierdoor is een eenvoudig te gebruiken pakket mogelijk dat u kunt gebruiken om uw apps te distribueren. Lees de volledige instructies voor [het implementeren van apps via Inrichtingspakketten.](app-deploy-provisioning-package.md)  

> [!NOTE]
> HoloLens (eerste generatie) biedt beperkte ondersteuning voor het installeren van apps **(UniversalAppInstall)** met behulp van een inrichtingspakket. HoloLens apparaten (eerste generatie) bieden alleen ondersteuning voor het installeren van een app via PPKG alleen tijdens OOBE en alleen met installatie van gebruikerscontext.
