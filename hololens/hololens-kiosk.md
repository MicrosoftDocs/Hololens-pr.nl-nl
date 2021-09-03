---
title: Een HoloLens als kiosk instellen
description: Meer informatie over het instellen en gebruiken van een kioskconfiguratie voor het vergrendelen van de apps op HoloLens apparaten.
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 8/24/2021
ms.custom:
- CI 115262
- CI 111456
- CSSTroubleshooting
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: e856ac74e959743e8d05ea6acf583700a6450373
ms.sourcegitcommit: 37611ac0a4efaf69816a734e16b763c810655f1a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/02/2021
ms.locfileid: "123411341"
---
# <a name="set-up-hololens-as-a-kiosk"></a>Een HoloLens als kiosk instellen

## <a name="what-is-kiosk-mode"></a>Wat is kioskmodus?

Kioskmodus is een functie waarmee u kunt bepalen welke toepassingen worden weergegeven in het menu Start wanneer een gebruiker zich bij de HoloLens. Er zijn twee ondersteunde scenario's:

1. **Kioskmodus voor één app:** er wordt geen menu Start weergegeven en er wordt automatisch één app gestart wanneer de gebruiker zich meldt. <br> *In het voorbeeld wordt* gebruikt: een apparaat dat alleen wordt uitgevoerd Dynamics 365 Guides app.
2. **Kioskmodus voor meerdere** apps: Startmenu alleen de toepassingen die zijn opgegeven in de kioskconfiguratie wanneer een gebruiker zich aan meldt. U kunt ervoor kiezen om een app automatisch te starten, indien gewenst. <br> *In het voorbeeld wordt* gebruikt: een apparaat dat alleen de Store-app, Feedback-hub en Instellingen app in het menu Start we weergeven.

    <img alt="Multi app kiosk example" src=".\images\multi-app-kiosk.jpg" width="411" height="500" />

## <a name="description-of-kiosk-mode-experience-when-a-user-signs-in"></a>Beschrijving van de kioskmoduservaring wanneer een gebruiker zich meldt

De volgende tabel bevat de functiemogelijkheden in de verschillende kioskmodi.

| &nbsp; |Startmenu |Menu Snelle acties |Camera en video |Miracast |Cortana |Ingebouwde spraakopdrachten |
| --- | --- | --- | --- | --- | --- | --- |
|Kiosk voor één app |Uitgeschakeld |Uitgeschakeld |Uitgeschakeld |Uitgeschakeld   |Uitgeschakeld |Ingeschakeld* |
|Kiosk voor meerdere apps |Ingeschakeld |Ingeschakeld*  |Beschikbaar*  |Beschikbaar* |Beschikbaar*   |Ingeschakeld*  |

\*Zie AUMID's voor apps voor meer informatie over het inschakelen van uitgeschakelde functies of hoe spraakopdrachten werken met uitgeschakelde functies Cortana HoloLens [AUMID's voor apps.](hololens-kiosk-reference.md#hololens-application-user-model-ids-aumids)

## <a name="key-general-considerations-before-configuring-kiosk-mode"></a>Belangrijke algemene overwegingen voordat u de kioskmodus configureert

1. Bepalen welk type gebruikersaccount zich aanmeldt bij HoloLens in uw omgeving: HoloLens ondersteunt Azure Active Directory(AAD)-accounts, Microsoft-accounts (MSA) en lokale accounts. Daarnaast worden tijdelijk gemaakte accounts met de naam gasten/bezoekers ook ondersteund (alleen voor apparaten die lid zijn van AAD). Meer informatie in [Manage user identity and sign-in for HoloLens](hololens-identity.md).
2. De doelen van de kioskmodus bepalen: of het nu gaat om iedereen, één gebruiker, bepaalde gebruikers of gebruikers die lid zijn van een of meer AAD-groepen, enzovoort.
3. Bepaal voor de kioskmodus voor meerdere apps welke toepassingen moeten worden weergegeven in het menu Start. Voor elke toepassing is de [AUMID (Application User Model ID)](hololens-kiosk-reference.md#hololens-application-user-model-ids-aumids) nodig.
4. Bepalen of de kioskmodus wordt toegepast op HoloLens runtime-inrichtingspakketten of MDM-server (Mobile Device Management).

## <a name="security-considerations"></a>Beveiligingsoverwegingen

De kioskmodus moet niet worden beschouwd als een beveiligingsmethode, maar als een manier om de opstartervaring bij het aanmelden van gebruikers te bepalen. U kunt de kioskmodus combineren met de onderstaande opties als er specifieke beveiligingsgerelateerde behoeften zijn:

- Wanneer Instellingen app zo is geconfigureerd dat deze wordt weergegeven in de kioskmodus en u wilt bepalen welke pagina's worden weergegeven in Instellingen-app, raadpleegt u [Pagina Instellingen zichtbaarheid](settings-uri-list.md)
- Als u de toegang tot bepaalde hardwaremogelijkheden wilt beheren, bijvoorbeeld camera, Bluetooth, enzovoort voor bepaalde apps, enzovoort, raadpleegt u Beleid [in Beleids-CSP](/windows/client-management/mdm/policies-in-policy-csp-supported-by-hololens2)dat wordt ondersteund door HoloLens 2 - Windows Client Management. U kunt onze [Algemene apparaatbeperkingen voor ideeën](hololens-common-device-restrictions.md) bekijken.
- De kioskmodus blokkeert niet dat een app (geconfigureerd als onderdeel van de kioskervaring) andere apps kan starten. Als u het starten van bepaalde apps/processen op HoloLens volledig wilt blokkeren, raadpleegt u Use Windows Defender Application Control on HoloLens 2 devices in Microsoft Intune - Azure (Windows Defender Application Control gebruiken op [HoloLens 2-apparaten in Microsoft Intune - Azure](/mem/intune/configuration/custom-profile-hololens)

## <a name="key-technical-considerations-for-kiosk-mode-for-hololens"></a>Belangrijke technische overwegingen voor de kioskmodus voor HoloLens

Is alleen van toepassing als u runtime-inrichtingspakketten wilt gebruiken of zelf kioskconfiguraties wilt maken. De configuratie van de kioskmodus maakt gebruik van een hiërarchische structuur op basis van XML:

- Een toegewezen toegangsprofiel definieert welke toepassingen worden weergegeven in het menu Start in de kioskmodus. U kunt meerdere profielen in dezelfde XML-structuur definiëren waarnaar later kan worden verwezen.
- Een configuratie voor toegewezen toegang verwijst naar een profiel en doelgebruiker(en) van dat profiel, bijvoorbeeld een specifieke gebruiker, een AAD-groep of -bezoekers, enzovoort. U kunt meerdere configuraties in dezelfde XML-structuur definiëren, afhankelijk van de complexiteit van uw gebruiksscenario's (zie de sectie ondersteunde scenario's hieronder).
- Raadpleeg [AssignedAccess CSP voor meer informatie.](/windows/client-management/mdm/assignedaccess-csp)

## <a name="supported-scenarios-for-kiosk-mode-based-on-identity-type"></a>Ondersteunde scenario's voor kioskmodus op basis van identiteitstype

Zie [referentiekoppelingen](hololens-kiosk-reference.md#kiosk-xml-code-samples) voor voorbeelden op basis van uw scenario en werk zo nodig bij voordat u kopieert.

> [!NOTE]
> Gebruik ALLEEN XML als u de gebruikersinterface van Intune niet gebruikt om een kioskconfiguratie te maken.

### <a name="for-users-who-sign-in-as-either-local-account-or-msa"></a>Voor gebruikers die zich aanmelden als lokaal account of MSA

| **Gewenste kioskervaring** | **Aanbevolen kioskconfiguratie** | **Manieren om te configureren**  | **Opmerkingen** |
| --- | --- | --- | --- |
| Elke gebruiker die zich meldt, krijgt een kioskervaring. | [Een profiel voor globale toegewezen toegang voor meerdere apps configureren](hololens-kiosk-reference.md#multiple-app-global-assigned-access-profile) | • [Microsoft Intune sjabloon maken](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Runtime-inrichting - Meerdere apps](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | Globale toegewezen toegang vereist [20H2 en nieuwere builds](hololens-release-notes.md#windows-holographic-version-20h2) |
| Een specifieke gebruiker die zich meldt, krijgt een kioskervaring.  | [Configureer een of meer aan apps toegewezen toegangsprofiel (indien vereist) om de naam van een specifieke gebruiker op te geven.](hololens-kiosk-reference.md#multiple-app-assigned-access-profile-for-a-local-account-or-aad-user-account) | [Zie de ondersteunde opties hieronder.](#steps-in-configuring-kiosk-mode-for-hololens) | Voor de kioskmodus voor één app wordt alleen een lokaal gebruikersaccount of MSA-account ondersteund op HoloLens. <br> Voor de kioskmodus voor meerdere apps wordt alleen een MSA-account of AAD-account ondersteund op HoloLens. |

### <a name="for-users-who-sign-in-as-aad-account"></a>Voor gebruikers die zich aanmelden als AAD-account

| **Gewenste kioskervaring** | **Aanbevolen kioskconfiguratie** | **Manieren om te configureren** | **Opmerkingen** |
| --- | --- | --- | --- |
| Elke gebruiker die zich meldt, krijgt een kioskervaring. | [Een profiel voor globale toegewezen toegang voor meerdere apps configureren](hololens-kiosk-reference.md#multiple-app-global-assigned-access-profile) | • [Microsoft Intune sjabloon maken](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Runtime-inrichting - Meerdere apps](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | Globale toegewezen toegang vereist [20H2 en nieuwere builds](hololens-release-notes.md#windows-holographic-version-20h2) |
| Elke gebruiker die zich meldt, krijgt een kioskervaring, behalve bepaalde gebruikers. | Configureer een profiel voor globale toegewezen toegang voor meerdere apps door bepaalde gebruikers uit te [sluiten (die apparaateigenaars moeten zijn).](hololens-kiosk-reference.md#multiple-app-global-assigned-access-profile-excluding-device-owners) | • [Microsoft Intune sjabloon maken](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Runtime-inrichting - Meerdere apps](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | Globale toegewezen toegang vereist [20H2 en nieuwere builds](hololens-release-notes.md#windows-holographic-version-20h2) |
| Elke AAD-gebruiker krijgt een afzonderlijke kioskervaring die specifiek is voor die gebruiker. | [Configureer de configuratie van toegewezen toegang voor elke gebruiker die de naam van het AAD-account opgeeft.](hololens-kiosk-reference.md#multiple-app-assigned-access-profiles-for-two-aad-users-or-more) | • [Microsoft Intune sjabloon maken](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Runtime-inrichting - Meerdere apps](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | &nbsp; |
| Gebruikers in verschillende AAD-groepen gebruiken de kioskmodus die alleen voor hun groep is. | [Configureer de configuratie van toegewezen toegang voor elke gewenste AAD-groep.](hololens-kiosk-reference.md#multiple-app-assigned-access-profile-for-two-aad-groups-or-more) | • [Microsoft Intune sjabloon maken](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Runtime-inrichting - Meerdere apps](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | • Wanneer een gebruiker zich meldt en HoloLens is verbonden met internet en die gebruiker lid blijkt te zijn van de AAD-groep waarvoor de kioskconfiguratie bestaat, krijgt de gebruiker de kiosk voor die AAD-groep te zien. <br> • Als er geen internet beschikbaar is wanneer gebruikers zich aanmelden, krijgt de gebruiker te maken [met HoloLens foutmodus.](#issue---no-apps-are-shown-in-start-menu-in-kiosk-mode) <br> • Als de internetbeschikbaarheid niet wordt gegarandeerd wanneer gebruikers zich kunnen inloggen en een kiosk op basis van een AAD-groep moet worden gebruikt, kunt u [AADGroupMembershipCacheValidityInDayspolicy gebruiken.](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk) <br> • Voor optimale ervaring met AAD-groepen tijdens het aanmelden wordt aanbevolen [om AADGroupMembershipCacheValidityInDayspolicy te gebruiken](/hololens/hololens-release-notes#cache-azure-ad-group-membership-for-offline-kiosk) |
| Gebruikers die een kioskervaring moeten HoloLens voor tijdelijke doeleinden, krijgen een kioskervaring. | [Configuratie van toegewezen toegang voor bezoekers configureren](hololens-kiosk-reference.md#multiple-app-assigned-access-profile-for-visitors) | • [Microsoft Intune aangepaste sjabloon maken](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Runtime inrichten - Één app](hololens-kiosk.md?tabs=ppkgsak#steps-in-configuring-kiosk-mode-for-hololens) | • Er wordt automatisch een tijdelijk gebruikersaccount gemaakt door HoloLens bij het aanmelden en wordt verwijderd wanneer een tijdelijke gebruiker zich aftekent. <br> • Overweeg het [inschakelen van beleid voor automatische aanmelding van bezoekers.](#how-can-visitor-accounts-automatically-logon-to-kiosk-experience) |

## <a name="steps-in-configuring-kiosk-mode-for-hololens"></a>Stappen voor het configureren van de kioskmodus voor HoloLens

Kioskconfiguraties kunnen op de volgende manieren worden gemaakt en toegepast:

1. Met de gebruikersinterface van de MDM-server, bijvoorbeeld de kiosksjablonen van Intune of aangepaste OMA-URI-configuraties, die vervolgens extern worden toegepast op HoloLens.
2. Met runtime-inrichtingspakketten, die vervolgens rechtstreeks worden toegepast op HoloLens.

Hier volgen de volgende manieren om te configureren. Selecteer het tabblad dat overeenkomt met het proces dat u wilt gebruiken.

1. [Microsoft Intune kiosksjabloon voor één app maken](hololens-kiosk.md?tabs=uisak#steps-in-configuring-kiosk-mode-for-hololens)
2. [Microsoft Intune kiosksjabloon voor meerdere apps](hololens-kiosk.md?tabs=uimak#steps-in-configuring-kiosk-mode-for-hololens)
1. [Microsoft Intune sjabloon maken](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens)
1. [Runtime inrichten - Meerdere apps](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens)
1. [Runtime inrichten - Één app](hololens-kiosk.md?tabs=ppkgsak#steps-in-configuring-kiosk-mode-for-hololens)

[!INCLUDE[](includes/kiosk-configure-steps.md)]

## <a name="frequently-asked-questions"></a>Veelgestelde vragen

### <a name="how-can-visitor-accounts-automatically-logon-to-kiosk-experience"></a>Hoe kunnen bezoekersaccounts zich automatisch bij de kioskervaring laten aanmeldingen?

Op builds [Windows Holographic, versie 21H1](hololens-release-notes.md#windows-holographic-version-21h1) en meer:

- AAD- en niet-ADD-configuraties bieden beide ondersteuning voor bezoekersaccounts die automatisch worden ingeschakeld voor kioskmodi.

[!INCLUDE[](includes/kiosk-autologin.md)]

### <a name="is-kiosk-experience-supported-on-hololens-1st-gen"></a>Wordt kioskervaring ondersteund op HoloLens (1e generatie)?

De kioskmodus is alleen beschikbaar als het apparaat Windows Holographic for Business. Alle HoloLens 2 worden met Windows Holographic for Business en er zijn geen andere edities. Op HoloLens 2 apparaat kan de kioskmodus uit de doos worden uitgevoerd.

HoloLens apparaten (1e generatie) moeten worden bijgewerkt, zowel wat betreft de build van het besturingssysteem als de editie van het besturingssysteem. Hier vindt u meer informatie over het bijwerken van een HoloLens (1e generatie) naar [Windows Holographic for Business](hololens1-upgrade-enterprise.md) edition. Als u een HoloLens -apparaat (1e generatie) wilt bijwerken voor het gebruik van de kioskmodus, moet u er eerst voor zorgen dat op het apparaat Windows 10, versie 1803 of een latere versie wordt uitgevoerd. Als u het hulpprogramma Windows Device Recovery hebt gebruikt om uw HoloLens-apparaat (1e generatie) te herstellen naar de standaard build, of als u de meest recente updates hebt geïnstalleerd, is uw apparaat klaar om te worden geconfigureerd.

### <a name="how-to-use-device-portal-to-configure-kiosk-in-non-production-environments"></a>De apparaatportal gebruiken om kiosken te configureren in niet-productieomgevingen

Stel het HoloLens [apparaat in om de Windows Apparaatportal.](/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) De Apparaatportal is een webserver op uw HoloLens verbinding kunt maken vanuit een webbrowser op uw pc.

 > [!CAUTION]
 > Wanneer u de ontwikkelaarsmodus HoloLens het gebruik van de Apparaatportal, moet u de ontwikkelaarsmodus op het apparaat inschakelen. Met de ontwikkelaarsmodus op een apparaat met Windows Holographic for Business kunt u apps side-loaden. Deze instelling brengt echter het risico met zich mee dat een gebruiker apps kan installeren die niet zijn gecertificeerd door de Microsoft Store. Beheerders kunnen de mogelijkheid om de ontwikkelaarsmodus in te schakelen blokkeren met behulp van de instelling **ApplicationManagement/AllowDeveloper Unlock** in de [beleids-CSP](/windows/client-management/mdm/policy-configuration-service-provider). [Meer informatie over de ontwikkelaarsmodus.](/windows/uwp/get-started/enable-your-device-for-development#developer-mode)

De kioskmodus kan worden ingesteld via de REST API van Apparaatportal door een POST naar /api/holographic/kioskmode/settings uit te voeren met één vereiste querytekenreeksparameter ('kioskModeEnabled' met de waarde 'true' of 'false') en één optionele parameter ('startupApp' met de waarde van een pakketnaam). Houd er rekening mee dat Apparaatportal alleen bedoeld is voor ontwikkelaars en niet mag worden ingeschakeld op niet-ontwikkelaarsapparaten. De REST API is onderhevig aan wijzigingen in toekomstige updates/releases.

## <a name="troubleshooting"></a>Problemen oplossen

### <a name="issue---no-apps-are-shown-in-start-menu-in-kiosk-mode"></a>Probleem: er worden geen apps weergegeven in het menu Start in de kioskmodus

**Symptomen**

Wanneer er fouten optreden bij het toepassen van de kioskmodus, wordt het volgende gedrag weergegeven:

- Vóór Windows Holographic worden in versie 20H2 - HoloLens alle toepassingen in de Startmenu.
- Windows Holographic, versie 20H2: als een apparaat een kioskconfiguratie heeft. Dit is een combinatie van zowel globale toegewezen toegang als door een AAD-groepslid toegewezen toegang. Als het bepalen van het AAD-groepslidmaatschap mislukt, ziet de gebruiker niets in het menu Start.

    ![Afbeelding van de kioskmodus die er nu uitziet wanneer deze mislukt.](images/hololens-kiosk-failure-behavior.png )

- Vanaf Windows [Holographic, versie 21H1,](hololens-release-notes.md#windows-holographic-version-21h1)zoekt de kioskmodus naar Algemene toegewezen toegang voordat een leeg startmenu wordt weergegeven. De kioskervaring wordt terugvallen op een algemene kioskconfiguratie (indien aanwezig) als er fouten optreden tijdens de kioskmodus van de AAD-groep.

**Stappen voor probleemoplossing**

- Controleer of AUMID van de app correct is opgegeven en of deze geen versies bevat. Raadpleeg HoloLens [AUMID's voor](hololens-kiosk-reference.md#hololens-application-user-model-ids-aumids) Postvak IN-apps voor voorbeelden.
- Zorg ervoor dat de toepassing voor die gebruiker op het apparaat is geïnstalleerd.
- Als de kioskconfiguratie is gebaseerd op AAD-groepen, moet u ervoor zorgen dat er een internetverbinding aanwezig is wanneer de AAD-gebruiker zich meldt. Configureer [desgewenst het beleid MixedReality/AADGroupMembershipCacheValidityInDays,](/windows/client-management/mdm/policy-csp-mixedreality#mixedreality-aadgroupmembershipcachevalidityindays) zodat dit ook zonder internet kan werken.

### <a name="issue---building-a-package-with-kiosk-mode-failed"></a>Probleem: het bouwen van een pakket met de kioskmodus is mislukt

**Symptomen**

Er wordt een dialoogvenster zoals hieronder weergegeven.

<kbd>
    <img alt="Kiosk failure to build" src="./images/kiosk-steps/kiosk-ppkg-failure.png"/>
</kbd>

**Stappen voor probleemoplossing**

1. Klik op de hyperkoppeling die wordt weergegeven zoals in het bovenstaande dialoogvenster.
1. Open ICD.log in een teksteditor en de inhoud moet de fout aangeven.

> [!NOTE]
> Als u meerdere pogingen hebt gedaan, controleert u de tijdstempels in het logboek. Hiermee kunt u alleen de huidige problemen controleren.

### <a name="issue--provisioning-package-built-successfully-but-failed-to-apply"></a>Probleem: het inrichtingspakket is gebouwd, maar is niet toegepast.

**Symptomen**

Fout wordt weergegeven bij het toepassen van het inrichtingspakket op Hololens

**Stappen voor probleemoplossing**

1. Blader naar de map Windows Configuration Designer-project voor runtime-inrichtingspakket bestaat.
1. Open ICD.log en zorg ervoor dat het logboek geen fouten bevat tijdens het bouwen van het inrichtingspakket. Sommige fouten worden niet weergegeven tijdens het bouwen, maar worden nog steeds vastgelegd in ICD.log

### <a name="issue--multiple-app-assigned-access-to-aad-group-does-not-work"></a>Probleem: meerdere app-toegewezen toegang tot AAD-groep werkt niet

**Symptomen**

Bij het aanmelden van AAD-gebruikers gaat het apparaat niet in de kioskmodus

**Stappen voor probleemoplossing**

- Controleer in configuratie-XML voor toegewezen toegang of de GUID van de AAD-groep waarvan de aangemelde gebruiker lid is, wordt gebruikt en niet de GUID van de AAD-gebruiker.
- Controleer of in de Intune-portal de AAD-gebruiker inderdaad wordt weergegeven als lid van de beoogde AAD-groep.
