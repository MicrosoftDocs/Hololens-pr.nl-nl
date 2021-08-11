---
title: Een HoloLens kiosk instellen
description: Meer informatie over het instellen en gebruiken van een kioskconfiguratie voor het vergrendelen van de apps op HoloLens apparaten.
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/27/2020
ms.custom:
- CI 115262
- CI 111456
- CSSTroubleshooting
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: e7f1efa99cc16b1003bd7063817451013ed2ec2661dbdf02edcd89c7984d0980
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/05/2021
ms.locfileid: "115663991"
---
# <a name="set-up-hololens-as-a-kiosk"></a>Een HoloLens kiosk instellen

U kunt een HoloLens om te functioneren als een apparaat voor vaste doeleinden, ook wel *een kiosk* genoemd, door het apparaat zo te configureren dat het in de kioskmodus wordt uitgevoerd. De kioskmodus beperkt de toepassingen (of gebruikers) die beschikbaar zijn op het apparaat. De kioskmodus is een handige functie die u kunt gebruiken om een HoloLens-apparaat te besteden aan zakelijke apps of om het HoloLens gebruiken in een app-demo.

Dit artikel bevat informatie over aspecten van kioskconfiguratie die specifiek zijn voor HoloLens apparaten. Zie Configure kiosks and digital signs on Windows desktop editions (Kiosken en digitale borden configureren op Windows [desktopversies)](/windows/configuration/kiosk-methods)voor algemene informatie over de verschillende Windows-gebaseerde kiosken en hoe u deze configureert.  

> [!IMPORTANT]  
> De kioskmodus bepaalt welke apps beschikbaar zijn wanneer een gebruiker zich bij het apparaat aan meldt. De kioskmodus is echter geen beveiligingsmethode. Een 'toegestane' app wordt niet gestopt bij het openen van een andere app die niet is toegestaan. Als u wilt voorkomen dat apps of processen worden geopend, gebruikt [u Windows Defender Application Control (WDAC) CSP](/windows/client-management/mdm/applicationcontrol-csp) om het juiste beleid te maken.
>
> Meer informatie over de Microsoft-services om gebruikers een geavanceerd beveiligingsniveau te bieden dat HoloLens 2 gebruikt, leest u meer over Statusscheiding en isolatie [- Defender-beveiligingen.](security-state-separation-isolation.md#defender-protections) U kunt ook leren hoe u WDAC en Windows PowerShell kunt gebruiken om apps toe te staan of te blokkeren [op HoloLens 2-apparaten met Microsoft Intune](/mem/intune/configuration/custom-profile-hololens).

U kunt de kioskmodus gebruiken in een configuratie voor één app of voor meerdere apps. U kunt een van de drie processen gebruiken om de kioskconfiguratie in te stellen en te implementeren.

> [!IMPORTANT]  
> Als u de configuratie voor meerdere apps verwijdert, worden de gebruikersvergrendelingsprofielen verwijderd die door de functie voor toegewezen toegang zijn gemaakt. Niet alle beleidswijzigingen worden echter terugdraaid. Als u dit beleid wilt herstellen, moet u het apparaat opnieuw instellen op de fabrieksinstellingen.

## <a name="plan-the-kiosk-deployment"></a>De kioskimplementatie plannen

Bij het plannen van uw kiosk moet u de volgende vragen kunnen beantwoorden. Hier vindt u enkele beslissingen die u moet overwegen tijdens het lezen van deze pagina en enkele overwegingen voor deze vragen.
1. **Wie gebruikt uw kiosk en welk [type account(s)](hololens-identity.md) gebruiken ze?** Dit is een beslissing die u waarschijnlijk al hebt genomen en niet moet worden aangepast omwille van uw Kiosk, maar is van invloed op de manier waarop de kiosk later wordt toegewezen.
1. **Moet u verschillende kiosken per gebruiker/groep hebben of moet een Kiosk niet zijn ingeschakeld voor sommige?** Zo ja, dan kunt u de kiosk maken via XML. 
1. **Hoeveel apps worden er in uw kiosk?** Als u meer dan één app hebt, hebt u een kiosk voor meerdere apps nodig. 
1. **Welke app(s) vindt u in uw kiosk?** Gebruik onze lijst met AUMID's hieronder om alle In-Box-apps naast uw eigen apps toe te voegen.
1. **Hoe wilt u uw kiosk implementeren?** Als u een apparaat in MDM inschrijft, raden we u aan MDM te gebruiken om uw kiosk te implementeren. Als u MDM niet gebruikt, is implementatie met Inrichtingspakket beschikbaar.  

### <a name="kiosk-mode-requirements"></a>Vereisten voor kioskmodus

U kunt elk apparaat HoloLens 2 om de kioskmodus te gebruiken.

> [!IMPORTANT]
> De kioskmodus is alleen beschikbaar als het apparaat een Windows Holographic for Business. Alle HoloLens 2 worden met Windows Holographic for Business en er zijn geen andere edities. Op HoloLens 2 apparaten kan de kioskmodus uit de doos worden uitgevoerd.
>
> HoloLens apparaten (1e generatie) moeten worden bijgewerkt, zowel wat betreft de build van het besturingssysteem als de editie van het besturingssysteem. Hier vindt u meer informatie over het bijwerken van een HoloLens (1e generatie) naar [Windows Holographic for Business](hololens1-upgrade-enterprise.md) editie. Als u een HoloLens -apparaat (1e generatie) wilt bijwerken voor het gebruik van de kioskmodus, moet u er eerst voor zorgen dat op het apparaat Windows 10, versie 1803 of een latere versie wordt uitgevoerd. Als u het hulpprogramma Windows Device Recovery hebt gebruikt om uw HoloLens-apparaat (1e generatie) te herstellen naar de standaard build, of als u de meest recente updates hebt geïnstalleerd, is uw apparaat gereed om te worden geconfigureerd.

> [!IMPORTANT]  
> Als u apparaten wilt beveiligen die worden uitgevoerd in de kioskmodus, kunt u beleidsregels voor apparaatbeheer toevoegen die functies zoals USB-connectiviteit uitschakelen. Controleer daarnaast de instellingen voor de updatering om ervoor te zorgen dat automatische updates niet worden uitgevoerd tijdens de werkuren.

### <a name="decide-between-a-single-app-kiosk-or-a-multi-app-kiosk"></a>Kiezen tussen een kiosk voor één app of een kiosk voor meerdere apps

Een kiosk voor één app start de opgegeven app wanneer de gebruiker zich bij het apparaat meldt. De Startmenu is uitgeschakeld, net als Cortana. Een HoloLens 2 reageert niet op het [startgebaar.](hololens2-basic-usage.md#start-gesture) Een HoloLens (1e generatie) reageert niet op de [bloembewegingen.](hololens1-basic-usage.md) Omdat slechts één app kan worden uitgevoerd, kan de gebruiker geen andere apps plaatsen.

Een kiosk voor meerdere apps geeft de Startmenu wanneer de gebruiker zich bij het apparaat aan meldt. De kioskconfiguratie bepaalt welke apps beschikbaar zijn op Startmenu. U kunt een kiosk voor meerdere apps gebruiken om gebruikers een eenvoudig te begrijpen ervaring te bieden door alleen de dingen te presenteren die ze moeten gebruiken en de dingen die ze niet hoeven te gebruiken, te verwijderen.

De volgende tabel bevat de functiemogelijkheden in de verschillende kioskmodi.

| &nbsp; |Startmenu |Menu Snelle acties |Camera en video |Miracast |Cortana |Ingebouwde spraakopdrachten |
| --- | --- | --- | --- | --- | --- | --- | 
|Kiosk voor één app |Uitgeschakeld |Uitgeschakeld |Uitgeschakeld |Uitgeschakeld   |Uitgeschakeld |Ingeschakeld<sup>1</sup> |
|Kiosk voor meerdere apps |Ingeschakeld |Ingeschakeld<sup>2</sup> |Beschikbaar<sup>2</sup> |Beschikbaar<sup>2</sup> |Beschikbaar<sup>2, 3</sup>  |Ingeschakeld<sup>1</sup> |

> <sup>1</sup> Spraakopdrachten die betrekking hebben op uitgeschakelde functies werken niet.  
> <sup>2</sup> Zie [Kiosk-apps](#plan-kiosk-apps)selecteren voor meer informatie over het configureren van deze functies.  
> <sup>3</sup> Zelfs Cortana is uitgeschakeld, worden de ingebouwde spraakopdrachten ingeschakeld.

De volgende tabel bevat de functies voor gebruikersondersteuning van de verschillende kioskmodi.

| &nbsp; |Ondersteunde gebruikerstypen | Automatisch aanmelden | Meerdere toegangsniveaus |
| --- | --- | --- | --- |
|Kiosk voor één app | Microsoft-account (MSA) in Azure Active Directory (Azure AD) of lokaal account |Ja |Nee |
|Kiosk voor meerdere apps |Azure AD-account |Nee |Ja |

Zie de volgende tabel voor voorbeelden van het gebruik van deze mogelijkheden.

|Gebruik een kiosk voor één app voor: |Gebruik een kiosk voor meerdere apps voor: |
| --- | --- |
|Een apparaat met alleen een Dynamics 365-handleiding voor nieuwe werknemers. |Een apparaat met zowel gidsen als hulp op afstand voor een groot aantal werknemers. |
|Een apparaat met alleen een aangepaste app. |Een apparaat dat voor de meeste gebruikers als kiosk fungeert (met alleen een aangepaste app), maar fungeert als een standaardapparaat voor een specifieke groep gebruikers. |

### <a name="plan-kiosk-apps"></a>Kiosk-apps plannen

Zie Richtlijnen voor het kiezen van een app voor toegewezen toegang (kioskmodus) voor algemene informatie over het kiezen [van kiosk-apps.](/windows/configuration/guidelines-for-assigned-access-app)

Als u de Windows Apparaatportal om een kiosk voor één app te configureren, selecteert u de app tijdens het installatieproces.  

Als u een MDM-systeem (Mobile Device Management) of een inrichtingspakket gebruikt om de kioskmodus te configureren, gebruikt u [de CSP (AssignedAccess Configuration Service Provider)](/windows/client-management/mdm/assignedaccess-csp) om toepassingen op te geven. De CSP gebruikt [AUMID's (Application User Model IDs) om](/windows/configuration/find-the-application-user-model-id-of-an-installed-app) toepassingen te identificeren. De volgende tabel bevat de AUMID's van sommige in-box-toepassingen die u in een kiosk voor meerdere apps kunt gebruiken.

> [!IMPORTANT]
> De kioskmodus bepaalt welke apps beschikbaar zijn wanneer een gebruiker zich bij het apparaat aan meldt. De kioskmodus is echter geen beveiligingsmethode. Het stopt niet dat een 'toegestane' app een andere app opent die niet is toegestaan. Omdat we dit gedrag niet beperken, kunnen apps nog steeds worden gestart vanuit Edge, Verkenner en de Microsoft Store apps. Als er specifieke apps zijn die u niet wilt openen vanuit een kiosk, gebruikt u [Windows Defender Application Control (WDAC) CSP](/windows/client-management/mdm/applicationcontrol-csp) om het juiste beleid te maken. 
> 
> Bovendien kan de Mixed Reality Start niet worden ingesteld als een kiosk-app.

<a id="aumids"></a>

|App-naam |AUMID |
| --- | --- |
|3D-viewer |Microsoft.Microsoft3DViewer \_ 8wekyb3d8bbwe \! Microsoft.Microsoft3DViewer |
|Kalender |microsoft.windowscommunicationsapps \_ 8wekyb3d8bbwe \! microsoft.windowslive.calendar |
|Camera<sup>1, 2</sup> |HoloCamera \_ cw5n1h2txyewy \! HoloCamera |
|Cortana<sup>3</sup> |Microsoft.549981C3F5F10 \_ 8wekyb3d8bbwe \! App |
|Apparaat kiezen op HoloLens (1e generatie) |HoloDevicesFlow \_ cw5n1h2txyewy \! HoloDevicesFlow |
|Apparaat kiezen op HoloLens 2 |Microsoft. Windows. DevicesFlowHost \_ cw5n1h2txyewy \! Microsoft.Windows. DevicesFlowHost |
|Dynamics 365 Guides |Microsoft.Dynamics365.Guides \_ 8wekyb3d8bbwe \! MicrosoftGuides |
|Dynamics 365 Remote Assist |Microsoft.MicrosoftRemoteAssist \_ 8wekyb3d8bbwe \! Microsoft.RemoteAssist |
|Feedback &nbsp; Hub |Microsoft.WindowsFeedbackHub \_ 8wekyb3d8bbwe \! App |
|Verkenner |c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy! App |
|Mail |microsoft.windowscommunicationsapps_8wekyb3d8bbwe!microsoft.windowslive.mail |
|Oude Microsoft Edge |Microsoft.MicrosoftEdge_8wekyb3d8bbwe! MicrosoftEdge |
|Nieuwe Microsoft Edge |Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe! MSEDGE |
|Microsoft Store |Microsoft.WindowsStore_8wekyb3d8bbwe! App |
|Miracast<sup>4</sup> |&nbsp; |
|Films & TV |Microsoft.ZuneVideo \_ 8wekyb3d8bbwe \! Microsoft.ZuneVideo |
|OneDrive |microsoft.microsoftskydrive \_ 8wekyb3d8bbwe \! App |
|Foto's |Microsoft. Windows. \_Foto's 8wekyb3d8bbwe \! App |
|Oude Instellingen |HolographicSystemSettings_cw5n1h2txyewy! App |
|Nieuwe Instellingen |BAEAEF15-9ILE-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy! App |
|Tips |Microsoft.HoloLensTips \_ 8wekyb3d8bbwe \! HoloLensTips |

> <sup>1</sup> Als u foto- of video-opname wilt inschakelen, moet u de camera-app inschakelen als kiosk-app.  
> <sup>2</sup> Wanneer u de camera-app inschakelen, moet u rekening houden met de volgende voorwaarden:
> - Het menu Snelle acties bevat de knoppen Foto en Video.  
> - U moet ook een app inschakelen (zoals Foto's, Mail of OneDrive) die kan communiceren met afbeeldingen of deze kan ophalen.  
>  
> <sup>3</sup> Zelfs als u een Cortana kiosk-app inschakelen, worden ingebouwde spraakopdrachten ingeschakeld. Opdrachten die zijn gerelateerd aan uitgeschakelde functies hebben echter geen effect.  
> <sup>4</sup> U kunt de Miracast inschakelen. Als u Miracast een kiosk-app wilt inschakelen, moet u de camera-app en de app Apparaat kiezen inschakelen.

### <a name="plan-kiosk-profiles-for-users-or-groups"></a>Kioskprofielen voor gebruikers of groepen plannen

Wanneer u het XML-bestand maakt of de gebruikersinterface van Intune gebruikt om een kiosk in te stellen, moet u overwegen wie de kioskgebruiker wordt. Een kioskconfiguratie kan worden beperkt tot een afzonderlijk account of Azure AD-groepen. 

Kiosken zijn doorgaans ingeschakeld voor een gebruiker of gebruikersgroep. Als u echter van plan bent om uw eigen XML-kiosk te schrijven, kunt u globale toegewezen toegang overwegen, waarbij de kiosk wordt toegepast op apparaatniveau, ongeacht de identiteit. Lees meer over kiosken voor globale toegewezen toegang als dit u [aanbeedt.](hololens-global-assigned-access-kiosk.md)

#### <a name="if-you-are-creating-an-xml-file"></a>Als u een XML-bestand maakt:
-   U maakt meerdere Kiosk-profielen en wijst deze toe aan verschillende gebruikers/groepen. Zoals een kiosk voor uw Azure AD-groep die veel apps heeft en een bezoekers die een kiosk met meerdere apps heeft met een enkele app.
-   Uw kioskconfiguratie wordt een **profiel-id genoemd** en heeft een GUID.
-   U wijst dat profiel toe in de sectie configuraties door het gebruikerstype op te geven en dezelfde GUID te gebruiken voor **de DefaultProfile-id.**
- Een XML-bestand kan worden gemaakt, maar nog steeds worden toegepast op een apparaat via MDM door een aangepast OMA URI-apparaatconfiguratieprofiel te maken en dit toe te passen op de HoloLens-apparaatgroep met behulp van de URI-waarde: ./Device/Vendor/MSFT/AssignedAccess/Configuration

#### <a name="if-you-are-creating-a-kiosk-in-intune"></a>Als u een kiosk maakt in Intune.
-   Elk apparaat ontvangt mogelijk slechts één Kiosk-profiel, anders veroorzaakt dit een conflict en worden er helemaal geen Kiosk-configuraties ontvangen. 
    -   Andere soorten profielen en beleidsregels, zoals apparaatbeperkingen die niet zijn gerelateerd aan het kioskconfiguratieprofiel, zijn niet in strijd met het kioskconfiguratieprofiel.
-   De Kiosk wordt ingeschakeld voor alle gebruikers die deel uitmaken van het aanmeldingstype Gebruiker. Dit wordt ingesteld met een gebruiker of Azure AD-groep. 
-   Nadat de kioskconfiguratie is ingesteld en het aanmeldingstype Gebruiker **(gebruikers** die zich kunnen aanmelden bij de kiosk) en de apps zijn geselecteerd, moet apparaatconfiguratie nog steeds worden toegewezen aan een groep. De toegewezen groep(en) bepaalt welke apparaten de configuratie van het Kiosk-apparaat ontvangen, maar heeft geen interactie met als de kiosk al dan niet is ingeschakeld. 
    - Zie Gebruikers- en apparaatprofielen toewijzen in Microsoft Intune voor een volledige bespreking van de effecten van het [toewijzen van configuratieprofielen in Intune.](/intune/configuration/device-profile-assign)

### <a name="select-a-deployment-method"></a>Een implementatiemethode selecteren

U kunt een van de volgende methoden selecteren om kioskconfiguraties te implementeren:

- [Microsoft Intune of andere MDM-service (Mobile Device Management)](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)

- [Inrichtingspakket](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)

- [Windows Apparaatportal](#use-the-windows-device-portal-to-set-up-a-single-app-kiosk)

   > [!NOTE]  
   > Omdat deze methode vereist dat de ontwikkelaarsmodus is ingeschakeld op het apparaat, wordt u aangeraden deze alleen te gebruiken voor demonstraties.

De volgende tabel bevat de mogelijkheden en voordelen van elk van de implementatiemethoden.

| &nbsp; |Implementeren met behulp van Windows Apparaatportal |Implementeren met behulp van een inrichtingspakket |Implementeren met behulp van MDM |
| --------------------------- | ------------- | -------------------- | ---- |
|Kiosken voor één app implementeren   | Ja           | Ja                  | Ja  |
|Kiosken voor meerdere apps implementeren    | Nee            | Ja                  | Ja  |
|Alleen implementeren op lokale apparaten | Ja           | Ja                  | Nee   |
|Implementeren met behulp van de ontwikkelaarsmodus |Vereist       | Niet vereist            | Niet vereist   |
|Implementeren met behulp Azure Active Directory (Azure AD)  | Niet vereist            | Niet vereist                   | Vereist  |
|Automatisch implementeren      | Nee            | Nee                   | Ja  |
|Implementatiesnelheid            | Snel       | Snel                 | Langzaam |
|Op schaal implementeren | Niet aanbevolen    | Aanbevolen        | Aanbevolen |

## <a name="use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk"></a>Gebruik Microsoft Intune of andere MDM om een kiosk voor één app of voor meerdere apps in te stellen

Volg deze stappen om de kioskmodus Microsoft Intune of een ander MDM-systeem in te stellen.

1. [Bereid de inschrijving van de apparaten voor.](#mdmenroll)
1. [Maak een kioskconfiguratieprofiel.](#mdmprofile)
1. Configureer de kiosk.
   - [Configureer de instellingen voor een kiosk voor één app.](#mdmconfigsingle)
   - [Configureer de instellingen voor een kiosk voor meerdere apps.](#mdmconfigmulti)
1. [Wijs het kioskconfiguratieprofiel toe aan een groep](#mdmassign).
1. Implementeer de apparaten.
   - [Implementeer een kiosk voor één app.](#mdmsingledeploy)
   - [Implementeer een kiosk voor meerdere apps.](#mdmmultideploy)

### <a name="mdm-step-1-ndash-prepare-to-enroll-the-devices"></a><a id="mdmenroll"></a>MDM, stap 1 &ndash; Voorbereiden om de apparaten in te schrijven

U kunt uw MDM-systeem configureren om apparaten automatisch HoloLens registreren wanneer de gebruiker zich voor het eerst aan meldt of gebruikers apparaten handmatig laten registreren. De apparaten moeten ook worden samengevoegd met uw Azure AD-domein en worden toegewezen aan de juiste groepen.

Zie Registratie HoloLens van apparaten in [MDM](hololens-enroll-mdm.md) en Intune-registratiemethoden voor Windows apparaten voor meer informatie over het inschrijven [van de apparaten.](/mem/intune/enrollment/windows-enrollment-methods)

### <a name="mdm-step-2-ndash-create-a-kiosk-configuration-profile"></a><a id="mdmprofile"></a>MDM, stap 2 &ndash; Een kioskconfiguratieprofiel maken

1. Open [Azure Portal](https://portal.azure.com/) en meld u aan bij uw Intune-beheerder account.
1. Selecteer **Microsoft Intune**  >  **Apparaatconfiguratie - Profielen** Profiel  >  **maken.**
1. Voer een profielnaam in.
1. Selecteer **Platform**  >  **Windows 10 hoger** en selecteer vervolgens **Profieltype**  > **Apparaatbeperkingen.**
1. Selecteer   >  **Kiosk configureren** en selecteer vervolgens een van de volgende opties:
   - Als u een kiosk voor één app wilt maken, selecteert u **Kioskmodus**  >  **Kiosk voor één app.**
   - Als u een kiosk voor meerdere apps wilt maken, selecteert **u Kioskmodus**  >  **Kiosk voor meerdere apps.**
1. Als u de kiosk wilt configureren, selecteert u **Toevoegen.**

De volgende stappen verschillen, afhankelijk van het type kiosk dat u wilt. Selecteer een van de volgende opties voor meer informatie:  

- [Kiosk voor één app](#mdmconfigsingle)
- [Kiosk voor meerdere apps](#mdmconfigmulti)

Zie instellingen voor Windows 10 en Windows Holographic for Business om uit te voeren als een toegewezen kiosk met Behulp van Intune voor meer informatie over het maken van een [kioskconfiguratieprofiel.](/intune/configuration/kiosk-settings)

### <a name="mdm-step-3-single-app-ndash--configure-the-settings-for-a-single-app-kiosk"></a><a id="mdmconfigsingle"></a>MDM, stap 3 (één app) De instellingen voor een &ndash;  kiosk voor één app configureren

Deze sectie bevat een overzicht van de instellingen die een kiosk voor één app vereist. Zie de volgende artikelen voor meer informatie:

- Zie Kioskmodus configureren met behulp van Microsoft Intune voor meer informatie over het configureren van een [kioskconfiguratieprofiel in Intune.](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune)
- Zie Kiosken voor apps met één volledig scherm voor meer informatie over de beschikbare instellingen voor kiosken voor [één app](/intune/configuration/kiosk-settings-holographic#single-full-screen-app-kiosks) in Intune
- Raadpleeg de documentatie van uw provider voor instructies voor andere MDM-services. Als u een aangepaste XML-configuratie moet gebruiken om een kiosk in uw MDM-service in te stellen, maakt u een XML-bestand dat [de kioskconfiguratie definieert.](#ppkioskconfig)

1. Selecteer **Aanmeldingstype** Gebruiker Lokaal gebruikersaccount en voer vervolgens de gebruikersnaam in van het lokale  >  (apparaat)account of het Microsoft-account (MSA) dat zich kan aanmelden bij de kiosk.
   > [!NOTE]  
   > Gebruikersaccounttypen met het kenmerk **AutoLogon** worden niet ondersteund in Windows Holographic for Business.
1. Selecteer **Toepassingstype**  >  **Store-app** en selecteer vervolgens een app in de lijst.

De volgende stap is het [toewijzen van](#mdmassign) het profiel aan een groep.

### <a name="mdm-step-3-multi-app-ndash-configure-the-settings-for-a-multi-app-kiosk"></a><a id="mdmconfigmulti"></a>MDM, stap 3 (meerdere apps) &ndash; De instellingen voor een kiosk voor meerdere apps configureren

Deze sectie bevat een overzicht van de instellingen die een kiosk voor meerdere apps vereist. Raadpleeg de volgende artikelen voor meer informatie:

- Zie Kioskmodus configureren met behulp van Microsoft Intune voor meer informatie over het configureren van een [kioskconfiguratieprofiel in Intune.](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune)
- Zie Kiosken voor meerdere apps voor meer informatie over de beschikbare instellingen voor kiosken voor [meerdere apps](/mem/intune/configuration/kiosk-settings-holographic#multi-app-kiosks) in Intune
- Raadpleeg de documentatie van uw provider voor instructies voor andere MDM-services. Als u een aangepaste XML-configuratie moet gebruiken om een kiosk in uw MDM-service in te stellen, maakt u een XML-bestand dat [de kioskconfiguratie definieert.](#ppkioskconfig) Als u een XML-bestand gebruikt, moet u de indeling [Start opnemen.](#start-layout-for-hololens)  
- U kunt eventueel een aangepaste indeling voor de start gebruiken met Intune of andere MDM-services. Zie Indelingsbestand starten voor [MDM (Intune en andere)](#start-layout-file-for-mdm-intune-and-others)voor meer informatie.

1. Selecteer **Doel-Windows 10 in S-modusapparaten**  >  **Nee.**  
>[!NOTE]  
> De S-modus wordt niet ondersteund in Windows Holographic for Business.

1. Selecteer **Aanmeldingstype Gebruiker**  >  **Azure AD-gebruiker** of -groep of Aanmeldingstype gebruiker HoloLens bezoekers en voeg vervolgens een of meer gebruikersgroepen of   >  accounts toe.  

   Alleen gebruikers die deel uitmaken van de groepen of accounts die u in **Aanmeldingstype** gebruiker opgeeft, kunnen de kioskervaring gebruiken.

1. Selecteer een of meer apps met behulp van de volgende opties:
   - Als u een geüploade Line-Of-Business-app wilt toevoegen, selecteert u **Store-app toevoegen** en selecteert u vervolgens de want-app.
   - Als u een app wilt toevoegen door de AUMID op te geven, selecteert u **Toevoegen op AUMID** en voert u vervolgens de AUMID van de app in. [Bekijk de lijst met beschikbare AUMID's](#aumids)

De volgende stap is het [toewijzen van](#mdmassign) het profiel aan een groep.

### <a name="mdm-step-4-ndash-assign-the-kiosk-configuration-profile-to-a-group"></a><a id="mdmassign"></a>MDM, stap 4 &ndash; Het kioskconfiguratieprofiel toewijzen aan een groep

Gebruik de **pagina Toewijzingen van** het kioskconfiguratieprofiel om in te stellen waar u de kioskconfiguratie wilt implementeren. In het eenvoudigste geval wijst u het kioskconfiguratieprofiel toe aan een groep die het HoloLens apparaat bevat wanneer het apparaat wordt ingeschreven bij MDM.

### <a name="mdm-step-5-single-app-ndash-deploy-a-single-app-kiosk"></a><a id="mdmsingledeploy"></a>MDM, stap 5 (één app) &ndash; Een kiosk voor één app implementeren

Wanneer u een MDM-systeem gebruikt, kunt u het apparaat tijdens OOBE inschrijven bij MDM. Nadat OOBE is klaar, kunt u zich eenvoudig aanmelden bij het apparaat.

Volg deze stappen tijdens OOBE:

1. Meld u aan met het account dat u hebt opgegeven in het kioskconfiguratieprofiel.
1. Het apparaat inschrijven. Zorg ervoor dat het apparaat is toegevoegd aan de groep waar het kioskconfiguratieprofiel aan is toegewezen.
1. Wacht tot OOBE is uitgevoerd, totdat de Store-app is gedownload en geïnstalleerd en totdat er beleidsregels worden toegepast. Start het apparaat vervolgens opnieuw op.

De volgende keer dat u zich bij het apparaat aan melden, wordt de kiosk-app automatisch start.

Als u de kioskconfiguratie op dit moment niet ziet, controleert [u de toewijzingsstatus](/intune/configuration/device-profile-monitor).

### <a name="mdm-step-5-multi-app-ndash-deploy-a-multi-app-kiosk"></a><a id="mdmmultideploy"></a>MDM, stap 5 (meerdere apps) &ndash; Een kiosk voor meerdere apps implementeren

Wanneer u een MDM-systeem gebruikt, kunt u het apparaat aan uw Azure AD-tenant deelnemen en het apparaat tijdens OOBE registreren bij MDM. Geef, indien van toepassing, de inschrijvingsgegevens op aan de gebruikers, zodat deze beschikbaar zijn tijdens het OOBE-proces.

> [!NOTE]  
> Als u het kioskconfiguratieprofiel hebt toegewezen aan een groep met gebruikers, moet u ervoor zorgen dat een van deze gebruikersaccounts het eerste account is om u aan te melden bij het apparaat.

Volg deze stappen tijdens OOBE:

1. Meld u aan met het account dat bij de groep **Aanmeldingstype Gebruiker** hoort.
1. Het apparaat inschrijven.
1. Wacht tot alle apps die deel uitmaken van het kioskconfiguratieprofiel zijn gedownload en geïnstalleerd. Wacht ook tot beleid is toegepast.  
1. Nadat OOBE is klaar, kunt u extra apps installeren vanuit de Microsoft Store of door sideloaden. [Vereiste apps](/mem/intune/apps/apps-deploy#assign-an-app) voor de groep waar het apparaat bij hoort, moeten automatisch worden geïnstalleerd.
1. Nadat de installatie is voltooien, start u het apparaat opnieuw op.

De volgende keer dat u zich bij het apparaat aan melden met een account van het **aanmeldingstype** Gebruiker, wordt de kiosk-app automatisch starten.

Als u de kioskconfiguratie op dit moment niet ziet, controleert [u de toewijzingsstatus](/intune/configuration/device-profile-monitor).

## <a name="use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk"></a>Een inrichtingspakket gebruiken om een kiosk voor één app of voor meerdere apps in te stellen

Volg deze stappen om de kioskmodus in te stellen met behulp van een inrichtingspakket.

1. [Maak een XML-bestand dat de kioskconfiguratie definieert.](#ppkioskconfig), met inbegrip van de [indeling Start.](#start-layout-for-hololens)
2. [Voeg het XML-bestand toe aan een inrichtingspakket.](#ppconfigadd)
3. [Pas het inrichtingspakket toe op HoloLens.](#ppapply)

### <a name="provisioning-package-step-1-ndash-create-a-kiosk-configuration-xml-file"></a><a id="ppkioskconfig"></a>Inrichtingspakket, stap 1 &ndash; Een XML-bestand voor de kioskconfiguratie maken

Volg [de algemene instructies voor het maken van een XML-bestand voor de kioskconfiguratie Windows bureaublad,](/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file)met uitzondering van het volgende:

- Neem geen klassieke Windows (Win32) op. HoloLens biedt geen ondersteuning voor deze toepassingen.
- Gebruik de [tijdelijke aanduiding XML-indeling voor](#start-layout-for-hololens) HoloLens.
- Optioneel: Gasttoegang toevoegen aan de kioskconfiguratie

#### <a name="optional-add-guest-access-to-the-kiosk-configuration"></a><a id="ppkioskguest"></a>Optioneel: Gasttoegang toevoegen aan de kioskconfiguratie

In de [ **sectie Configuraties van** het XML-bestand](/windows/configuration/lock-down-windows-10-to-specific-apps#configs)kunt u een speciale groep met de naam **Bezoekers** configureren zodat gasten de kiosk kunnen gebruiken. Wanneer de kiosk is geconfigureerd  voor ondersteuning van de speciale bezoekersgroep, wordt de optie **'Gast'** toegevoegd aan de aanmeldingspagina. Het **gastaccount** vereist geen wachtwoord en alle gegevens die aan het account zijn gekoppeld, worden verwijderd wanneer het account zich aftekent.

Als u het **gastaccount wilt inschakelen,** voegt u het volgende codefragment toe aan de XML van uw kioskconfiguratie:

```xml
<Configs>
  <Config>  
    <SpecialGroup Name="Visitor" />  
    <DefaultProfile Id="enter a profile ID"/>  
  </Config>  
</Configs>  
```
#### <a name="enable-visitor-autologon"></a>Bezoekersautologon inschakelen

Op builds [Windows Holographic, versie 21H1](hololens-release-notes.md#windows-holographic-version-21h1) en meer:
- AAD- en niet-ADD-configuraties bieden beide ondersteuning voor bezoekersaccounts die automatisch worden ingeschakeld voor kioskmodi.

##### <a name="non-aad-configuration"></a>Niet-AAD-configuratie

1. Maak een inrichtingspakket dat:
    1. Hiermee configureert u Runtime-instellingen/AssignedAccess om bezoekersaccounts toe te staan.
    1. Optioneel wordt het apparaat ingeschreven bij MDM (Runtime-instellingen/Werkplek/Registraties), zodat het later kan worden beheerd.
    1. Maak geen lokaal account
2. [Pas het inrichtingspakket toe.](hololens-provisioning.md)

##### <a name="aad-configuration"></a>AAD-configuratie

AAD-apparaten die zijn geconfigureerd voor de kioskmodus, kunnen zich aanmelden bij een bezoekersaccount met één tik op de knop op het aanmeldingsscherm. Nadat het apparaat is aangemeld bij het bezoekersaccount, wordt het apparaat pas opnieuw gevraagd om zich aan te melden als de bezoekers expliciet is aangemeld bij het menu Start of het apparaat opnieuw wordt opgestart.

Automatische aanmelding van bezoekers kan worden beheerd via aangepast [OMA-URI-beleid:](/mem/intune/configuration/custom-settings-windows-10)

- URI-waarde: ./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon


| Beleid |Description |Configuraties 
| --------------------------- | ------------- | -------------------- |
| MixedReality/BezoekersAutoLogon | Hiermee kan een bezoekers zich automatisch bij een kiosk laten aanmeldingen. | 1 (Ja), 0 (Nee, standaardinstelling.) |

#### <a name="placeholder-start-layout-for-hololens"></a><a id="start-layout-for-hololens"></a>Tijdelijke aanduiding Startindeling voor HoloLens

Als u een [inrichtingspakket gebruikt om](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) een kiosk voor meerdere apps te configureren, is voor de procedure een indeling Start vereist. Het aanpassen van de beginindeling wordt niet ondersteund in Windows Holographic for Business. Daarom moet u een tijdelijke aanduiding Startindeling gebruiken.

> [!NOTE]  
> Omdat een kiosk met één app de kiosk-app start wanneer een gebruiker zich aan meldt, gebruikt deze geen Startmenu en hoeft deze geen startindeling te hebben.

> [!NOTE]  
> Als u [MDM gebruikt om](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) een kiosk voor meerdere apps in te stellen, kunt u eventueel een indeling Start gebruiken. Zie Tijdelijke aanduiding Indelingsbestand voor start voor [MDM (Intune en andere) voor meer informatie.](#start-layout-file-for-mdm-intune-and-others)

Voeg voor de indeling Start de volgende **sectie StartLayout toe** aan het XML-bestand voor kioskinrichting:

```xml
<!-- This section is required for parity with Desktop Assigned Access. It is not currently used on HoloLens -->
            <StartLayout>
                <![CDATA[<LayoutModificationTemplate xmlns:defaultlayout="http://schemas.microsoft.com/Start/2014/FullDefaultLayout" xmlns:start="http://schemas.microsoft.com/Start/2014/StartLayout" Version="1" xmlns="http://schemas.microsoft.com/Start/2014/LayoutModification">
                      <LayoutOptions StartTileGroupCellWidth="6" />
                      <DefaultLayoutOverride>
                        <StartLayoutCollection>
                          <defaultlayout:StartLayout GroupCellWidth="6">
                            <start:Group Name="">
                              <start:Tile Size="2x2" Column="0" Row="0" AppUserModelID="placeholderpackagename_kzf8qxf38zg5c!App" />
                            </start:Group>
                          </defaultlayout:StartLayout>
                        </StartLayoutCollection>
                      </DefaultLayoutOverride>
                    </LayoutModificationTemplate>
                ]]>
            </StartLayout>
            <!-- This section is required for parity with Desktop Assigned Access. It is not currently used on HoloLens -->
```

#### <a name="placeholder-start-layout-file-for-mdm-intune-and-others"></a><a id="start-layout-file-for-mdm-intune-and-others"></a>Tijdelijke aanduiding Indelingsbestand voor start voor MDM (Intune en andere)

Sla het volgende voorbeeld op als een XML-bestand. U kunt dit bestand gebruiken wanneer u de kiosk voor meerdere apps in Microsoft Intune configureert (of in een andere MDM-service die een kioskprofiel biedt).

> [!NOTE]
> Als u een aangepaste instelling en een volledige XML-configuratie moet gebruiken om een kiosk in uw MDM-service in te stellen, gebruikt u de instructies voor de indeling Start voor [een inrichtingspakket.](#start-layout-for-hololens)

```xml
<LayoutModificationTemplate
    xmlns="http://schemas.microsoft.com/Start/2014/LayoutModification"
    xmlns:defaultlayout="http://schemas.microsoft.com/Start/2014/FullDefaultLayout"
    xmlns:start="http://schemas.microsoft.com/Start/2014/StartLayout"
    Version="1">
  <RequiredStartGroupsCollection>
    <RequiredStartGroups>
      <AppendGroup Name="">
        <start:Tile Size="2x2" Column="0" Row="0" AppUserModelID="placeholderpackagename_kzf8qxf38zg5c!App" />
      </AppendGroup>
    </RequiredStartGroups>
  </RequiredStartGroupsCollection>
 </LayoutModificationTemplate>
```

### <a name="prov-package-step-2-ndash-add-the-kiosk-configuration-xml-file-to-a-provisioning-package"></a><a id="ppconfigadd"></a>Prov. pakket, stap 2 &ndash; Het XML-bestand voor de kioskconfiguratie toevoegen aan een inrichtingspakket

1. Open [Windows Configuration Designer.](https://www.microsoft.com/store/apps/9nblggh4tx22)
1. Selecteer **Geavanceerde inrichting,** voer een naam in voor uw project en selecteer **vervolgens Volgende.**
1. Selecteer **Windows 10 Holographic** en selecteer **vervolgens Volgende.**
1. Selecteer **Finish**. De werkruimte voor uw pakket wordt geopend.
1. Selecteer **Runtime-instellingen**  >  **ToegewezenAccess**  >  **MultiAppAssignedAccessSettings.**
1. Selecteer in het middelste deelvenster Bladeren **om het** XML-bestand voor de kioskconfiguratie te zoeken en te selecteren dat u hebt gemaakt.

   ![Schermopname van het veld MultiAppAssignedAccessSettings in Windows Configuration Designer](./images/multiappassignedaccesssettings.png)

1. **Optioneel**. (Als u het inrichtingspakket na de eerste installatie van het apparaat wilt toepassen en er al een gebruiker met beheerdersrechten beschikbaar is op het kioskapparaat, slaat u deze stap over.) Selecteer **Runtime-instellingen** &gt;  &gt; **AccountsGebruikers** en maak vervolgens een gebruikersaccount. Geef een gebruikersnaam en wachtwoord op en selecteer **vervolgens UserGroup**  >  **Administrators.**  
  
     Met dit account kunt u de inrichtingsstatus en logboeken bekijken.  
1. **Optioneel**. (Als u al een niet-beheerdersaccount op het kioskapparaat hebt, kunt u deze stap overslaan.) Selecteer **Runtime-instellingen** &gt;  &gt; **AccountsGebruikers** en maak vervolgens een lokaal gebruikersaccount. Zorg ervoor dat de gebruikersnaam hetzelfde is als voor het account dat u opgeeft in de configuratie-XML. Selecteer **UserGroup**  >  **Standard Users.**
1. Selecteer **Bestand**  >  **Opslaan.**
1. Selecteer   >  **Inrichtingspakket exporteren** en selecteer vervolgens **Eigenaar**  >  **IT-beheerder.** Hiermee stelt u de prioriteit van dit inrichtingspakket hoger in dan de inrichtingspakketten die vanuit andere bronnen op dit apparaat worden toegepast.
1. Selecteer **Next**.
1. Selecteer op **de pagina Inrichtingspakketbeveiliging** een beveiligingsoptie.
   > [!IMPORTANT]  
   > Als u Pakket **ondertekenen inschakelen selecteert,** moet u ook een geldig certificaat selecteren om het pakket te ondertekenen. Hiervoor selecteert u **Bladeren en** selecteert u het certificaat dat u wilt gebruiken om het pakket te ondertekenen.
   
   > [!CAUTION]  
   > Selecteer **pakketversleuteling niet inschakelen.** Op HoloLens apparaten zorgt deze instelling ervoor dat de inrichting mislukt.
1. Selecteer **Next**.
1. Geef de uitvoerlocatie op waar het inrichtingspakket naartoe moet wanneer het wordt gebouwd. Standaard gebruikt Windows Configuration Designer de projectmap als uitvoerlocatie. Als u de uitvoerlocatie wilt wijzigen, selecteert u **Bladeren.** Wanneer u klaar bent, selecteert u **Volgende.**
1. Selecteer **Bouwen om** te beginnen met het bouwen van het pakket. Het bouwen van het inrichtingspakket duurt niet lang. Op de buildpagina worden de projectgegevens weergegeven en de voortgangsbalk geeft de buildstatus aan.

### <a name="provisioning-package-step-3-ndash-apply-the-provisioning-package-to-hololens"></a><a id="ppapply"></a>Inrichtingspakket, stap 3 &ndash; Het inrichtingspakket toepassen op HoloLens

In het artikel HoloLens configureren met behulp van een inrichtingspakket vindt u gedetailleerde instructies voor het toepassen van het inrichtingspakket onder de volgende omstandigheden:

- U kunt in eerste [instantie een inrichtingspakket toepassen op HoloLens tijdens de installatie.](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)

- U kunt ook [een inrichtingspakket toepassen op HoloLens na de installatie.](hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup)

## <a name="use-the-windows-device-portal-to-set-up-a-single-app-kiosk"></a>Gebruik de Windows Apparaatportal om een kiosk voor één app in te stellen

Als u de kioskmodus wilt instellen met behulp van Windows Apparaatportal, volgt u deze stappen.

1. [Stel het HoloLens apparaat in om de Windows Apparaatportal.](https://developer.microsoft.com/windows/mixed-reality/using_the_windows_device_portal#setting_up_hololens_to_use_windows_device_portal) De Apparaatportal is een webserver op uw HoloLens verbinding kunt maken vanuit een webbrowser op uw pc.

    > [!CAUTION]
    > Wanneer u de HoloLens voor het gebruik van de Apparaatportal, moet u de ontwikkelaarsmodus op het apparaat inschakelen. Met de ontwikkelaarsmodus op een apparaat met Windows Holographic for Business kunt u apps side-loaden. Deze instelling brengt echter het risico met zich mee dat een gebruiker apps kan installeren die niet zijn gecertificeerd door de Microsoft Store. Beheerders kunnen de mogelijkheid om de ontwikkelaarsmodus in te schakelen blokkeren met behulp van de instelling **ApplicationManagement/AllowDeveloper Unlock** in de [beleids-CSP](/windows/client-management/mdm/policy-configuration-service-provider). [Meer informatie over de ontwikkelaarsmodus.](/windows/uwp/get-started/enable-your-device-for-development#developer-mode)
    
1. Maak op een computer verbinding met HoloLens via [Wi-Fi](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_wi-fi) of [USB.](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_usb)

1. Voer een van de volgende handelingen uit:
   - Als u voor het eerst verbinding maakt met Windows Apparaatportal, maakt u [een gebruikersnaam en wachtwoord](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#creating_a_username_and_password)
   - Voer de gebruikersnaam en het wachtwoord in die u eerder hebt ingesteld.

    > [!TIP]
    > Als er een certificaatfout in de browser wordt weergegeven, volgt u [deze stappen voor probleemoplossing.](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#security_certificate)

1. Selecteer in Windows Apparaatportal de **optie Kioskmodus.**

1. Selecteer **Kioskmodus inschakelen,** selecteer een app die moet worden uitgevoerd wanneer het apparaat wordt gestart en selecteer **vervolgens Opslaan.**

    ![Kioskmodus](images/kiosk.png)
1. Start HoloLens. Als de pagina Apparaatportal geopend, kunt u  bovenaan de pagina Opnieuw opstarten selecteren.

> [!NOTE]
> De kioskmodus kan worden ingesteld via de REST API van Apparaatportal door een POST naar /api/holographic/kioskmode/settings uit te voeren met één vereiste querytekenreeksparameter ('kioskModeEnabled' met de waarde 'true' of 'false') en één optionele parameter ('startupApp' met de waarde van een pakketnaam). Houd er rekening mee dat Apparaatportal alleen bedoeld is voor ontwikkelaars en niet mag worden ingeschakeld op niet-ontwikkelaarsapparaten. De REST API is onderhevig aan wijzigingen in toekomstige updates/releases.

## <a name="more-information"></a>Meer informatie

### <a name="watch-how-to-configure-a-kiosk-by-using-a-provisioning-package"></a>Bekijk hoe u een kiosk configureert met behulp van een inrichtingspakket.  

> [!VIDEO https://www.microsoft.com/videoplayer/embed/fa125d0f-77e4-4f64-b03e-d634a4926884?autoplay=false]

### <a name="global-assigned-access--kiosk-mode"></a>Globale toegewezen toegang – kioskmodus
- Minder identiteitsbeheer voor Kiosk door de nieuwe kioskmethode in te schakelen waarmee de kioskmodus op systeemniveau wordt toegepast.

Met deze nieuwe functie kan een IT-beheerder een HoloLens 2-apparaat configureren voor meerdere app-kioskmodussen die van toepassing is op systeemniveau, geen affiniteit heeft met een identiteit op het systeem en van toepassing is op iedereen die zich bij het apparaat meldt. Zie de [HoloLens kiosk voor wereldwijde toegewezen toegang](hololens-global-assigned-access-kiosk.md) voor meer informatie over deze nieuwe functie.

### <a name="automatic-launch-of-an-application-in-multiple-app-kiosk-mode"></a>Automatisch starten van een toepassing in de kioskmodus voor meerdere apps 
- Gerichte ervaring met het automatisch starten van apps, waardoor de gebruikersinterface en app-selecties die zijn gekozen voor kioskmodus nog verder worden vergroten.

Is alleen van toepassing op de kioskmodus voor meerdere apps en er kan slechts één app worden aangewezen voor automatisch starten met behulp van het gemarkeerde kenmerk hieronder in de configuratie toegewezen toegang. 

De toepassing wordt automatisch gestart wanneer de gebruiker zich meldt. 

```xml
<AllowedApps>                     
      <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
</AllowedApps>
```


### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>Wijzigingen in het gedrag van de kioskmodus voor het afhandelen van fouten
Wanneer er fouten optreden bij het toepassen van de kioskmodus, wordt het volgende gedrag weergegeven:

- Vóór Windows Holographic worden in versie 20H2 - HoloLens alle toepassingen in de Startmenu.
- Windows Holographic, versie 20H2: als een apparaat een kioskconfiguratie heeft die een combinatie is van zowel globale toegewezen toegang als aan AAD-groepslid toegewezen toegang, ziet de gebruiker niets als het bepalen van het AAD-groepslidmaatschap mislukt.

![Afbeelding van de kioskmodus die er nu uitziet wanneer deze mislukt.](images/hololens-kiosk-failure-behavior.png )


- Vanaf Windows [Holographic, versie 21H1,](hololens-release-notes.md#windows-holographic-version-21h1)zoekt de kioskmodus naar Algemene toegewezen toegang voordat een leeg startmenu wordt weergegeven. De kioskervaring wordt terugvallen op een algemene kioskconfiguratie (indien aanwezig) in het geval van fouten tijdens de kioskmodus van de AAD-groep.

### <a name="cache-azure-ad-group-membership-for-offline-kiosk"></a>Azure AD-groepslidmaatschap cachen voor offline kiosk

- Veiligere kioskmodus door het elimineren van beschikbare apps in kioskmodusfouten.
- Ingeschakelde offline kiosken kunnen maximaal 60 dagen worden gebruikt met Azure AD-groepen.

Met dit beleid bepaalt u hoe lang de Cache voor Azure AD-groepslidmaatschap mag worden gebruikt voor configuraties met toegewezen toegang die zijn gericht op Azure AD-groepen voor aangemelde gebruikers. Zodra deze beleidswaarde is ingesteld op waarde groter dan 0, wordt de cache anders niet gebruikt.  

Naam: AADGroupMembershipCacheValidityInDays URI-waarde: ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

Min. - 0 dagen  
Maximaal - 60 dagen 

Stappen om dit beleid correct te gebruiken: 
1. Maak een apparaatconfiguratieprofiel voor kiosken die zijn gericht op Azure AD-groepen en wijs dit toe HoloLens apparaten. 
1. Maak een aangepaste op OMA URI gebaseerde apparaatconfiguratie die deze beleidswaarde in stelt op het gewenste aantal dagen (> 0) en wijs deze toe aan HoloLens apparaat(en). 
    1. De URI-waarde moet in het tekstvak OMA-URI worden ingevoerd als ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays
    1. De waarde kan tussen min. /max. zijn toegestaan.
1. Schrijf HoloLens apparaten in en controleer of beide configuraties op het apparaat worden toegepast. 
1. Laat Azure AD-gebruiker 1 zich aanmelden wanneer internet beschikbaar is. Zodra de gebruiker zich heeft aanmelden en het Azure AD-groepslidmaatschap is bevestigd, wordt de cache gemaakt. 
1. Azure AD-gebruiker 1 kan nu HoloLens offline halen en gebruiken voor de kioskmodus zolang de beleidswaarde X dagen toestaat. 
1. Stap 4 en 5 kunnen worden herhaald voor elke andere Azure AD-gebruiker N. Het belangrijkste punt is dat elke Azure AD-gebruiker zich moet aanmelden bij het apparaat via internet, zodat ten minste één keer kan worden vastgesteld dat hij of zij lid is van de Azure AD-groep waarop de Kiosk-configuratie is gericht. 
 
> [!NOTE]
> Tot stap 4 voor een Azure AD-gebruiker wordt uitgevoerd, t ervaart deze foutgedrag dat wordt vermeld in omgevingen met een verbroken verbinding. 


## <a name="xml-kiosk-code-samples-for-hololens"></a>Xml Kiosk-codevoorbeelden voor HoloLens

### <a name="multiple-app-kiosk-mode-targeting-an-azure-ad-group"></a>De kioskmodus voor meerdere apps die is gericht op een Azure AD-groep. 
Deze kiosk implementeert een kiosk die voor gebruikers in de Azure AD-groep een kiosk heeft ingeschakeld die de drie apps bevat: Instellingen, Remote Assist en Feedback-hub. Als u dit voorbeeld wilt wijzigen om direct te worden gebruikt, moet u de hieronder gemarkeerde GUID wijzigen in een eigen Azure AD-groep. 


:::code language="xml" source="samples/kiosk-sample-multi-aad-group.xml" highlight="20":::


### <a name="multiple-app-kiosk-mode-targeting-azure-ad-account"></a>Kioskmodus voor meerdere apps gericht op Azure AD-account.
Deze kiosk implementeert een kiosk voor één gebruiker. Er wordt een kiosk ingeschakeld met de drie apps: Instellingen, Remote Assist en Feedback-hub. Als u dit voorbeeld wilt wijzigen om direct te worden gebruikt, moet u het hieronder gemarkeerde account wijzigen in een eigen Azure AD-account. 


:::code language="xml" source="samples/kiosk-sample-multi-aad-account.xml" highlight="20":::

