---
title: HoloLens-updates beheren
description: Meer informatie over hoe uw beheerders Mobile Device Management kunnen gebruiken om updates voor HoloLens-apparaten te beheren.
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
audience: ITPro
ms.topic: article
ms.localizationpriority: high
ms.date: 10/13/2020
ms.reviewer: jarrettr
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.custom:
- CI 116337
- CI 115825
- CI 111456
- CSSTroubleshooting
ms.openlocfilehash: 6c9d1551b2a3348a6ff9962180c2d5552eb100f1
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/25/2021
ms.locfileid: "111379417"
---
# <a name="manage-hololens-updates"></a>HoloLens-updates beheren

HoloLens gebruikt Windows Update op dezelfde manier als andere Windows 10 apparaten. Wanneer een update beschikbaar is, wordt deze automatisch gedownload en geïnstalleerd de volgende keer dat uw apparaat op het netnet werkt en is verbonden met internet. In dit artikel wordt beschreven hoe u updates beheert in een onderneming of een andere beheerde omgeving. Zie HoloLens bijwerken voor meer informatie over het beheren van updates voor afzonderlijke [HoloLens-apparaten.](hololens-update-hololens.md)

## <a name="manage-updates-automatically"></a>Updates automatisch beheren

### <a name="managing-updates-by-using-windows-update-for-business"></a>Updates beheren met behulp van Windows Update voor Bedrijven

Windows Holographic for Business kunt [de](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) Windows Update voor Bedrijven gebruiken om updates te beheren. Alle HoloLens 2 kunnen gebruikmaken van Windows Holographic for Business. Zorg ervoor dat ze Windows Holographic for Business build 10.0.18362.1042 of een latere build. Als u HoloLens-apparaten (1e generatie) hebt, moet u ze upgraden naar [Windows Holographic for Business](hololens1-upgrade-enterprise.md) om hun updates te beheren.

Windows Update voor Bedrijven HoloLens-apparaten rechtstreeks met de Windows Update service. Met behulp Windows Update voor Bedrijven kunt u meerdere aspecten van het updateproces beheren, dat wil zeggen, welke apparaten op welk &mdash; moment updates ontvangen. U kunt bijvoorbeeld updates naar een subset van apparaten uitrollen om te testen en vervolgens later updates voor de resterende apparaten uitrollen. U kunt ook verschillende updateschema's voor verschillende typen updates definiëren.

> [!NOTE]  
> Voor HoloLens-apparaten kunt u automatisch functie-updates beheren (twee keer per jaar uitgebracht) en kwaliteitsupdates (maandelijks of indien nodig uitgebracht, inclusief essentiële beveiligingsupdates). Zie Typen updates die worden beheerd door Windows Update voor Bedrijven voor [meer informatie over updatetypen.](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb#types-of-updates-managed-by-windows-update-for-business)

U kunt uw Windows Update voor Bedrijven voor HoloLens configureren met behulp van beleidsregels in een MDM-oplossing (Mobile Device Management), zoals Microsoft Intune.

### <a name="managing-windows-update-for-business-by-using-microsoft-intune"></a>Beheer Windows Update voor Bedrijven met behulp van Microsoft Intune

Zie Manage Windows 10 software updates in Intune (Software-updates beheren [in Intune)](https://docs.microsoft.com/intune/protect/windows-update-for-business-configure)Windows Update voor Bedrijven gedetailleerde informatie over het gebruik van Intune om Windows Update voor Bedrijven configureren. Zie Intune updatebeheerfuncties die HoloLens ondersteunt voor meer informatie over de specifieke [Intune-functionaliteit die HoloLens ondersteunt.](#intune-update-management-functions-that-hololens-supports)

> [!IMPORTANT]  
> Intune biedt twee beleidstypen voor het beheren van updates: *Windows 10 updatering* en *Windows 10 functie-update.* Het Windows 10 voor het bijwerken van functies is momenteel in openbare preview en wordt niet ondersteund voor HoloLens.
>  
> U kunt een Windows 10 voor het beheren van HoloLens 2 bijwerken.

### <a name="configure-update-policies-for-hololens-2-or-hololens-1st-gen"></a>Updatebeleid configureren voor HoloLens 2 of HoloLens (1e generatie)

In deze sectie worden de beleidsregels beschreven die u kunt gebruiken voor het beheren van updates voor HoloLens 2 of HoloLens (1e generatie). Zie Update-implementaties plannen en configureren voor HoloLens 2 voor meer informatie over de functionaliteit die beschikbaar [is voor HoloLens 2.](#plan-and-configure-update-rollouts-for-hololens-2)

[Beleids-CSP: Met Bijwerken](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update) worden de beleidsregels voor het configureren van Windows Update voor Bedrijven.

> [!NOTE]  
> Zie Beleids-CSP's die worden ondersteund door HoloLens-apparaten voor een lijst met specifieke beleidsconfiguratieserviceproviders [(CSP's)](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#policy-csps-supported-by-hololens-devices)die worden ondersteund door specifieke edities van HoloLens.

#### <a name="configure-automatic-checks-for-updates"></a>Automatische controles voor updates configureren

U kunt het beleid **Update/AllowAutoUpdate gebruiken** om het gedrag van automatische updates te beheren, zoals het scannen, downloaden en installeren van updates. Zie [Update/AllowAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowautoupdate)voor meer informatie over de beschikbare instellingen voor dit beleid.

> [!NOTE]  
> In Microsoft Intune kunt u automatisch **updategedrag gebruiken om** dit beleid te wijzigen. Zie Manage [Windows 10 software updates in Intune (Software-updates beheren in Intune) voor meer informatie.](https://docs.microsoft.com/intune/windows-update-for-business-configure)

#### <a name="configure-an-update-schedule"></a>Een updateschema configureren

Gebruik de volgende beleidsregels om te configureren hoe en wanneer updates worden toegepast:

- [Update/ScheduledInstallDay](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduledinstallday)  
  - Waarden: **0**–**7** (0 = elke dag, 1 = zondag, 7 = zaterdag)
  - Standaardwaarde: **0** (elke dag)
- [Update/ScheduledInstallTime](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduledinstalltime)
  - Waarden: 0-23 (0 = middernacht, 23 = 21 PM)
  - Standaardwaarde: 15:00 uur

#### <a name="configure-active-hours"></a>Actieve uren configureren
Vanaf Windows Holographic kan een IT-beheerder versie [20H2](hololens-release-notes.md#windows-holographic-version-20h2) het bereik voor actieve uren voor HoloLens 2 opgeven.

Actieve uren bepalen de periode waarin u verwacht dat het apparaat in gebruik is. Automatisch opnieuw opstarten na een update wordt uitgevoerd buiten de actieve uren. Het opgegeven bereik wordt geteld vanaf de begintijd van de actieve uren. U kunt MDM gebruiken, zoals beschreven in [Actieve uren configureren met MDM.](https://docs.microsoft.com/windows/deployment/update/waas-restart#configuring-active-hours-with-mdm) MDM maakt gebruik van de instellingen Update/ActiveHoursStart en Update/ActiveHoursEnd en Update/ActiveHoursMaxRange in de beleids-CSP om de actieve uren te configureren.

-   [Update/ActiveHoursEnd:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend) met deze waarde stelt u de eindtijd in. De begintijd is maximaal 12 uur.
    -   Ondersteunde waarden zijn 0-23, waarbij 0 12:00 uur, 1 is 1:00 uur, enzovoort.
    -   De standaardwaarde is 17 (17:00 uur).
-   [Update/ActiveHoursMaxRange:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange) met deze waarde stelt u het maximum aantal actieve uren in vanaf de begintijd.
    -   Ondersteunde waarden zijn 8-18.
    -   De standaardwaarde is 18 (uur).
-   [Update/ActiveHoursStart:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart) met deze waarde stelt u de begintijd in. De eindtijd is maximaal 12 uur.
    -   Ondersteunde waarden zijn 0-23, waarbij 0 12:00 uur, 1 is 1:00 uur, enzovoort.
    -   De standaardwaarde is 8 (8:00 uur).

#### <a name="for-devices-that-run-windows-10-version-1607-only"></a>Alleen voor apparaten Windows 10 versie 1607

U kunt de volgende updatebeleidsregels gebruiken om apparaten te configureren voor het ontvangen van updates van Windows Server Update Service (WSUS) in plaats van Windows Update:

- [Update/AllowUpdateService](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowupdateservice)
- [Update/RequireUpdateApproval](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-requireupdateapproval)
- [Update/UpdateServiceUrl](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-updateserviceurl)

### <a name="plan-and-configure-update-rollouts-for-hololens-2"></a>Update-implementaties plannen en configureren voor HoloLens 2

HoloLens 2 ondersteunt meer functies voor updateautomatisering dan HoloLens (eerste generatie). Dit geldt met name als u een Microsoft Intune voor het beheren van Windows Update voor Bedrijven beleid. Deze functies maken het eenvoudiger voor u om update-implementaties in uw organisatie te plannen en te implementeren.

#### <a name="plan-the-update-strategy"></a>De updatestrategie plannen

Windows Updates voor Bedrijven ondersteunt uitstelbeleid. Nadat Microsoft een update heeft uitgebracht, kunt u een uitstelbeleid gebruiken om te bepalen hoe lang moet worden gewacht voordat deze update op apparaten wordt geïnstalleerd. Door subsets van uw apparaten (ook wel *updateringen* genoemd) te koppelen aan verschillende uitstelbeleidsregels, kunt u een strategie voor update-implementatie voor uw organisatie coördineren.

Denk bijvoorbeeld aan een organisatie die 1000 apparaten heeft en de apparaten in vijf golven moet bijwerken. De organisatie kan vijf updateringen maken, zoals wordt weergegeven in de volgende tabel.

|Groep |Aantal apparaten |Uitstel (dagen) |
| ---| :---: | :---: |
|Grp 1 (IT-personeel) |5 |0 |
|Grp 2 (early adopters) |50 |60 |
|Grp 3 (hoofd 1) |250 |120 |
|Grp 4 (hoofd 2) |300 |150 |
|Grp 5 (hoofd 3) |395 |180 |

Hier is te zien hoe de implementatie in de tijd verloopt voor de hele organisatie.

![Tijdlijn voor het implementeren van updates](./images/hololens-updates-timeline.png)

#### <a name="configure-an-update-deferral-policy"></a>Een beleid voor uitstel van updates configureren

Een uitstelbeleid geeft het aantal dagen aan tussen de datum waarop een update beschikbaar komt en de datum waarop de update wordt aangeboden aan een apparaat.

U kunt verschillende uitstelen configureren voor functie-updates en kwaliteitsupdates. De volgende tabel bevat de specifieke beleidsregels voor elk type en de maximale uitstel voor elk type.

|Categorie |Beleid |Maximum uitstellen |
| --- | --- | --- |
|Onderdelenupdates |DeferFeatureUpdatesPeriodInDays |365 dagen |
|Kwaliteitsupdates |DeferQualityUpdatesPeriodInDays |30 dagen |

#### <a name="pause-updates-via-device"></a>Updates onderbreken via apparaat

Als een gebruiker geen toegang heeft tot MDM, kan deze persoon updates maximaal 35 dagen handmatig onderbreken op een HoloLens 2-apparaat op build [Windows Holographic, versie 2004](hololens-release-notes.md#windows-holographic-version-2004) of hoger. Gebruikers kunnen deze instelling bereiken door te navigeren naar Instellingen **-> Update & Security -> Advanced options** schuif omlaag naar **Updates** onderbreken en selecteer de datum tot de datum waarop ze updates zullen onderbreken. Zodra een gebruiker de onderbrekingslimiet heeft bereikt, moet het apparaat nieuwe updates ontvangen, omdat deze opnieuw kunnen worden onderbroken. 

Vanaf [Windows Holographic, versie 20H2,](hololens-release-notes.md#windows-holographic-version-20h2)kan deze functie updates onderbreken worden beheerd voor HoloLens 2 apparaten. 
- [Update/SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess).
    - 0 (standaardinstelling) - Ingeschakeld
    - 1 : uitgeschakeld

#### <a name="intune-update-management-functions-that-hololens-supports"></a>Intune-functies voor updatebeheer die HoloLens ondersteunt

U kunt de volgende Intune-updatebeheerfuncties gebruiken om updates voor HoloLens te beheren.

- **Maken** en **toewijzen:** met deze functies voegt u een Windows 10-updatering toe aan de lijst met updateringen. Zie Updateringen maken en toewijzen [voor meer informatie.](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings)

- **Onderbreken:** als u een probleem ondervindt bij het implementeren van een functie- of kwaliteitsupdate, kunt u de update 35 dagen onderbreken (vanaf een opgegeven datum). Deze onderbreking voorkomt dat andere apparaten de update installeren totdat u het probleem oplost of verhelpt. Als u een functie-update onder pauzeert, worden kwaliteitsupdates nog steeds aangeboden aan apparaten om ervoor te zorgen dat ze veilig blijven. Wanneer een updatetype is onderbroken, wordt op het deelvenster Overzicht van deze ring weergegeven hoeveel dagen nog resteren voordat het updatetype wordt hervat. Nadat de opgegeven tijd is verstreken, verloopt de pauze automatisch en wordt het updateproces hervat.

  Terwijl de updatering is onderbroken, kunt u een van de volgende opties selecteren:

  - **Uitbreiden:** de onderbrekingsperiode voor een updatetype met 35 dagen verlengen.
  - **Hervatten:** updates voor die ring herstellen naar actieve bewerking. U kunt de updatering indien nodig opnieuw onderbreken.

  > [!NOTE]  
  > De **verwijderbewerking** voor updateringen wordt niet ondersteund voor HoloLens 2 apparaten.

### <a name="delivery-optimization-preview"></a>Delivery Optimization Preview

[Windows Holographic versie 21H1](hololens-release-notes.md#windows-holographic-version-21h1) heeft een vroege preview ingeschakeld voor delivery optimization-instellingen om het bandbreedteverbruik voor downloads van meerdere HoloLens-apparaten te verminderen. Een volledige beschrijving van deze functionaliteit en de aanbevolen netwerkconfiguratie is hier beschikbaar: Delivery Optimization [voor Windows 10 updates.](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization)

De volgende instellingen zijn ingeschakeld als onderdeel van het beheeroppervlak en [kunnen worden geconfigureerd vanuit Intune:](https://docs.microsoft.com/mem/intune/configuration/delivery-optimization-settings)

- [DOCacheHost](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehost)
- [DOCacheHostSource](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehostsource)
- [DODelayCacheServerFallbackBackground](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackbackground)
- [DODelayCacheServerFallbackForeground](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackforeground)
- [DODownloadMode](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodownloadmode)
- [DOMaxBackgroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxbackgrounddownloadbandwidth)
- [DOMaxForegroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxforegrounddownloadbandwidth)
- [DOPercentageMaxBackgroundBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxbackgroundbandwidth)
- [DOPercentageMaxForegroundBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxforegroundbandwidth)
- [DOSetHoursToLimitForegroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitforegrounddownloadbandwidth)
- [DOSetHoursToLimitBackgroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitbackgrounddownloadbandwidth)

Enkele waarschuwingen over deze preview-aanbieding:

- HoloLens-ondersteuning is in deze preview beperkt tot updates van het besturingssysteem.
- Windows Holographic for Business ondersteunt alleen HTTP-downloadmodi en downloads van een [Microsoft Verbonden cache-eindpunt;](https://docs.microsoft.com/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache) Peer-to-peer downloadmodi en groepstoewijzingen worden momenteel niet ondersteund voor HoloLens-apparaten.
- HoloLens biedt geen ondersteuning voor implementatie of delivery optimization voor Windows Server Update Services eindpunten.
- Voor het oplossen van problemen zijn diagnostische gegevens op de Verbonden cache-server of het verzamelen van een trace op HoloLens op HoloLens vereist via  >  **InstellingenUpdate & Security**  >   **Troubleshooting**  >   **Windows Update**.

## <a name="manually-check-for-updates"></a>Handmatig controleren op updates

Hoewel HoloLens periodiek controleert op systeemupdates, zijn er mogelijk omstandigheden waarin u handmatig wilt controleren.

Als u handmatig wilt controleren op updates, gaat **u** naar  >  **InstellingenUpdate &**  >  **Beveiligingscontrole op updates.** Als de app Instellingen aangeeft dat uw apparaat up-to-date is, hebt u alle updates die momenteel beschikbaar zijn.

## <a name="manually-roll-back-an-update"></a>Een update handmatig terugdraaien

In sommige gevallen wilt u mogelijk terugkeren naar een eerdere versie van de HoloLens-software. Het proces hiervoor is afhankelijk van het feit of u HoloLens 2 HoloLens (1e generatie) gebruikt.

### <a name="revert-to-a-previous-version-hololens-2"></a>Terugkeren naar een vorige versie (HoloLens 2)

U kunt updates terugdraaien en terugkeren naar een eerdere versie van HoloLens 2 met behulp van advanced [Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) om uw HoloLens opnieuw in te stellen naar de eerdere versie.

> [!NOTE]
> Als u een eerdere versie gebruikt, worden uw persoonlijke bestanden en instellingen verwijderd.

Als u wilt terugkeren naar een eerdere versie van HoloLens 2, volgt u deze stappen:

1. Zorg ervoor dat er geen telefoons of Windows-apparaten op uw computer zijn aangesloten.
1. Download advanced Recovery [Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) op uw computer van de Microsoft Store.
1. Download de [meest recente HoloLens 2 release](https://aka.ms/hololens2download).
1. Nadat deze downloads zijn gedownload, opent u Bestandenverkenner Downloads, klikt u met de rechtermuisknop op de gecomprimeerde map (.zip) die u zojuist hebt gedownload en selecteert u alles uitpakken om het bestand uit te  >     >   vouwen.
1. Gebruik een USB-A-naar-USB-C-kabel om uw HoloLens-apparaat te verbinden met uw computer. Zelfs als u andere kabels hebt gebruikt om uw HoloLens aan te sluiten, werkt dit type kabel het beste.
1. De Companion voor geavanceerd herstel detecteert automatisch uw HoloLens-apparaat. Selecteer de **Microsoft HoloLens** tegel.
1. Selecteer in het volgende scherm **Handmatige pakketselectie** en open vervolgens de map die u eerder hebt uit vouwd.
1. Selecteer het installatiebestand (.ffu).
1. Selecteer **Software installeren** en volg de instructies.

### <a name="revert-to-a-previous-version-hololens-1st-gen"></a>Terugkeren naar een eerdere versie (HoloLens (1e generatie))

U kunt updates terugdraaien en terugkeren naar een eerdere versie van HoloLens (1e generatie) met behulp van de [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379) om uw HoloLens opnieuw in te stellen naar de eerdere versie.

> [!NOTE]
> Als u een eerdere versie van HoloLens gebruikt, worden uw persoonlijke bestanden en instellingen verwijderd.

Als u wilt terugkeren naar een eerdere versie van HoloLens (1e generatie), volgt u deze stappen:

1. Zorg ervoor dat er geen telefoons of Windows-apparaten op uw computer zijn aangesloten.
1. Download de Windows [Device Recovery Tool (WDRT) op uw](https://support.microsoft.com/help/12379)computer.
1. Download het [holoLens Jubileumupdate-herstelpakket](https://aka.ms/hololensrecovery).
1. Nadat de downloads zijn gedownload, opent u  >  **Verkenner Downloads,** klikt u met de rechtermuisknop op de gecomprimeerde map (.zip) die u zojuist hebt gedownload en selecteert u alles uitpakken om het bestand uit te  >   vouwen.
1. Gebruik de micro-USB-kabel die samen met uw HoloLens-apparaat is meegeleverd om uw HoloLens-apparaat te verbinden met uw computer. Zelfs als u andere kabels hebt gebruikt om uw HoloLens-apparaat te verbinden, werkt deze het beste.
1. Het WDRT detecteert automatisch uw HoloLens-apparaat. Selecteer de **Microsoft HoloLens** tegel.
1. Selecteer in het volgende scherm **Handmatige pakketselectie** en open vervolgens de map die u eerder hebt uit vouwd.
1. Selecteer het installatiebestand (.ffu).
1. Selecteer **Software installeren** en volg de instructies.

**Als WDRT uw apparaat niet detecteert**

Als WDRT uw HoloLens-apparaat niet detecteert, start u de computer opnieuw op. Als dat niet werkt, selecteert u Mijn apparaat is niet **gedetecteerd,** selecteert **Microsoft HoloLens** en volgt u de instructies.

## <a name="related-articles"></a>Verwante artikelen:

- [HoloLens 2 opmerkingen bij de release](https://docs.microsoft.com/hololens/hololens-release-notes)
- [Wat is Windows Update voor Bedrijven?](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb)
- [Apparaten toewijzen aan onderhoudskanalen voor Windows 10 updates](https://docs.microsoft.com/windows/deployment/update/waas-servicing-channels-windows-10-updates)
- [Windows 10-software-updates beheren in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)
