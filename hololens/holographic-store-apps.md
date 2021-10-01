---
title: Toepassingen zoeken, installeren en verwijderen
description: De Microsoft Store is uw bron voor apps en games die werken met HoloLens.  Meer informatie over het zoeken, installeren en verwijderen van holografische apps.
ms.assetid: cbe9aa3a-884f-4a92-bf54-8d4917bc3435
ms.reviewer: v-miegge
ms.date: 9/7/2021
manager: jarrettr
keywords: hololens, store, uwp, app, installeren
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: f7d4ddf41f02b083000c1e57f5140c38527826d7
ms.sourcegitcommit: b9cd7ed5edb98249c609b547b90587863ea1cb9e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/01/2021
ms.locfileid: "129364417"
---
# <a name="find-install-and-uninstall-applications-from-the-microsoft-store"></a>Toepassingen zoeken, installeren en verwijderen uit de Microsoft Store

De Microsoft Store is uw go-to-bron voor apps en games die werken met HoloLens. Wanneer u naar de Store op uw HoloLens, worden alle apps die u ziet, op de app uitgevoerd.

Apps op HoloLens een 2D-weergave of een holografische weergave. Apps die gebruikmaken van een 2D-weergave, zien eruit als vensters en kunnen overal om u heen worden geplaatst. Apps die gebruikmaken van een holografische weergave, omringen u en worden de enige app die u ziet.

HoloLens biedt ondersteuning voor veel bestaande toepassingen van de Microsoft Store en nieuwe apps die specifiek zijn gebouwd voor HoloLens.  Dit artikel is gericht op holografische toepassingen van de Microsoft Store.

Lees Aangepaste holographic-toepassingen voor meer informatie over het installeren en uitvoeren [van aangepaste apps.](holographic-custom-apps.md)

## <a name="find-apps"></a>Apps zoeken

Open de Microsoft Store in **het** menu Start. Blader vervolgens naar apps en games. U kunt [spraakopdrachten](hololens-cortana.md) gebruiken om te zoeken door 'Zoeken' te zeggen. Zodra het zoekvenster wordt geopend, wordt 'Beginnen met dicteren' weergegeven en wanneer u hier om wordt gevraagd, begint u met het zeggen van uw zoektermen.

> [!NOTE]
> De systeemvereisten voor HoloLens zijn gebaseerd op de architectuur van de app-build. Als een app-build voor HoloLens (1e generatie) niet is bijgewerkt met naar een nieuwere UWP in de Store om het ARM-architectuurpakket op te nemen, is het niet beschikbaar voor HoloLens 2-apparaten. En als een HoloLens 2-app niet het x86-architectuurpakket bevat, is deze niet beschikbaar voor HoloLens (1e generatie). HoloLens van apparaten:
>
> - x86 = HoloLens (1e generatie)
> - ARM = HoloLens 2

> [!NOTE]
> Op 12 januari 2021 bereiken de volgende apps Einde van ondersteuning op HoloLens apparaten. We raden u aan de volgende koppeling op uw apparaat te gebruiken om de webversie van de app te gebruiken.

| App        | Koppeling                                          |
|------------|-----------------------------------------------|
| Excel mobiel      | [https://office.live.com/start/Excel.aspx](https://office.live.com/start/Excel.aspx)      |
| Word Mobile       | [https://office.live.com/start/Word.aspx](https://office.live.com/start/Word.aspx)       |
| PowerPoint mobiel | [https://office.live.com/start/PowerPoint.aspx](https://office.live.com/start/PowerPoint.aspx) |

> [!NOTE]
> De OneDrive-app wordt momenteel niet ondersteund voor Azure AD-accounts op HoloLens. U wordt aangeraden de app Microsoft OneDrive PWA downloaden. [Volg deze stappen om de app te downloaden.]

## <a name="install-apps"></a>Apps installeren

Als u apps wilt downloaden, moet u zijn aangemeld met een Microsoft-account. Sommige apps zijn gratis en kunnen direct worden gedownload. Voor apps waarvoor een aankoop is vereist, moet u zijn aangemeld bij de Store met uw Microsoft-account een geldige betalingswijze hebben.

> [!NOTE]
> Het account dat u gebruikt op Microsoft Store hoeft niet hetzelfde te zijn als het account bij wie u bent aangemeld. Als u een werk- of schoolaccount op uw HoloLens, moet u zich mogelijk aanmelden met uw persoonlijke account in de Store-app om een aankoop te doen.

> [!TIP]
> Als u een betalingswijze wilt instellen, gaat u [naar account.microsoft.com](https://account.microsoft.com/) selecteert u **Betalingsopties &** betalingswijze Betalingsopties  >    >  **toevoegen.**

1. Als u het [ **menu Start** wilt openen,](holographic-home.md)voert u een [startbewegingen](/hololens/hololens2-basic-usage#start-gesture) of [een](hololens1-basic-usage.md) bloeibewegingen uit op HoloLens (1e generatie).

1. Selecteer de Microsoft Store app. Nadat de Store-app is geopend:
   1. Gebruik de zoekbalk om te zoeken naar toepassingen.
   1. Selecteer essentiële apps of apps die specifiek zijn gemaakt HoloLens uit een van de gecureerde categorieën.
   1. Selecteer rechtsboven in de Store-app de knop **'...'** en selecteer vervolgens **Mijn** bibliotheek om eerder gekochte apps weer te geven.

1. Selecteer **Downloaden** of **installeren** op de pagina van de toepassing (mogelijk is een aankoop vereist).

### <a name="install-microsoft-onedrive-pwa-app"></a>Een Microsoft OneDrive PWA installeren

Vereisten: de gebruiker heeft het apparaat HoloLens 2 aan zijn werkten tenant.

1. Open het menu Start en start de Edge-browser.

    ![Startmenu](images/office-pwa-1.jpg)

1. Ga op HoloLens naar [https://onedrive.live.com/about/signin](https://onedrive.live.com/about/signin) en voer de referenties van uw werkaccount in

    ![Aanmelden via het werk](images/office-pwa-2.jpg)

1. Nadat u zich hebt aangemeld bij uw OneDrive-webportal, wacht u 30 tot 60 seconden totdat de downloadknop PWA wordt weergeven

    ![PWA knop installeren](images/office-pwa-3.jpg)

1. Selecteer de knop PWA downloaden en installeer de app

    ![Installatieprompt](images/office-pwa-4.jpg)

1. Sluit de Edge-browser en selecteer Startmenu de knop Alle **apps** en start OneDrive PWA app met het **Microsoft OneDrive**

    ![Alle apps beide apps worden weergegeven.](images/office-pwa-5.jpg)

    > [!NOTE]
    > De 'Microsoft OneDrive' is de PWA app, waarbij 'OneDrive' de oudere UWP is.

1. Vervolgens kunt u uw OneDrive zien.

    ![OneDrive PWA](images/office-pwa-6.jpg)

Zie ook: [Automatische uploads inschakelen naar OneDrive voor bedrijven](hololens-release-notes.md#onedrive-for-work-or-school-camera-roll-upload)

## <a name="update-apps"></a>Apps bijwerken

### <a name="manual-updates"></a>Handmatige updates

Als u een app wilt bijwerken die u hebt geïnstalleerd vanuit Microsoft Store, kunt u de app bijwerken vanuit de Microsoft Store app. Voor apps die voor de Microsoft Store voor Bedrijven zijn geïnstalleerd, kunt u deze apps ook bijwerken vanuit de Microsoft Store voor Bedrijven.

1. Als u het [ **menu Start** wilt openen,](holographic-home.md)voert u een [startbewegingen](/hololens/hololens2-basic-usage#start-gesture) of [een](hololens1-basic-usage.md) bloeibewegingen uit op HoloLens (1e generatie).

1. Selecteer de Store-app.

1. Kijk rechtsboven in de Store-app.

1. Selecteer de **knop '...'** of 'Meer weergeven'.

   > [!div class="mx-imgBorder"]
   > ![Microsoft Store app-schermopname.](images/store-update-1.png)

1. Selecteer **Downloads en updates.**
    1. Als uw apparaat eerder updates heeft geïdentificeerd, is er mogelijk een pijl-omlaag en een getal dat staat voor updates die in behandeling zijn.

1. Selecteer **Updates downloaden.** Uw apparaat zoekt nu naar updates en stelt deze in op downloaden en installeren.

   > [!div class="mx-imgBorder"]
   > ![Microsoft Store app-schermopname van het downloaden van updates..](images/store-update-2.png.jpg)

> [!NOTE]
> Als de apps op uw apparaat door uw organisatie zijn gedistribueerd, kunnen ze worden bijgewerkt via dezelfde commerciële app-beheermethoden. Als dit van toepassing is op uw situatie, leest u meer via ons overzicht van de implementatie [van commerciële apps.](app-deploy-overview.md)
>
> Als u een aangepaste app wilt bijwerken die sideloaden of geïmplementeerd is, moet u dezelfde methode gebruiken met de bijgewerkte versie van uw app. Lees Aangepaste holographic-toepassingen voor meer informatie over het installeren en uitvoeren [van aangepaste apps.](holographic-custom-apps.md)

### <a name="automatic-app-updates"></a>Automatische app-updates

Automatische updates zijn van toepassing op Microsoft Store of Microsoft Store voor Bedrijven apps en kunnen alleen automatisch worden bijgewerkt als ze rechtstreeks vanuit de Store zijn geïnstalleerd. Indien geïnstalleerd vanuit Intune, kan IT updates van MDM naar beneden pushen door te synchroniseren met de Microsoft Store voor Bedrijven voor de meest recente beschikbare versie voor de app.

> [!NOTE]
> Voor apps die afkomstig zijn van de Microsoft Store voor Bedrijven, moet u zijn aangemeld bij de Store en worden geverifieerd met dezelfde tenant die is gekoppeld aan de Microsoft Store voor Bedrijven-catalogus die op het apparaat wordt gebruikt.

#### <a name="how-automatic-updates-work"></a>Hoe automatische updates werken

Automatische app-updates worden gepland om dagelijks (ongeveer elke 24 uur) te worden uitgevoerd, afhankelijk van de netwerkbeschikbaarheid. Houd uw apparaat actief of aangesloten op de wisselstroom om updates te ontvangen. Zelfs als app-updates worden gedownload tijdens actief dagelijks gebruik, worden ze alleen toegepast wanneer de app die moet worden bijgewerkt niet meer in gebruik is.

> [!TIP]
> Laad uw apparaat indien mogelijk 's nachts terwijl het is verbonden met het bedrijfsnetwerk. Als updates 's nachts kunnen worden gedownload en geïnstalleerd, zullen ze het actieve apparaatgebruik minder onderbreken.

#### <a name="how-it-administrators-can-control-automatic-updates"></a>Hoe IT-beheerders automatische updates kunnen controleren

IT-beheerders kunnen automatische app-updates controleren via het [beleid ApplicationManagement/AllowAppStoreAutoUpdate.](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowappstoreautoupdate) Met dit beleid kunnen ze automatische app-updates volledig in- of uitschakelen, maar wordt er geen controle over wanneer er updates plaatsvinden.

Vanaf [21H2](hololens-release-notes.md#windows-holographic-version-21h1)kunnen IT-beheerders ook het [beleid ScheduleForceRestartForUpdateFailures](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-scheduleforcerestartforupdatefailures) gebruiken om te bepalen wanneer apps die in gebruik waren, maar niet konden worden bijgewerkt bij eerdere pogingen, geforceereerd opnieuw moeten worden opgestart.

## <a name="uninstall-apps"></a>Apps verwijderen

Er zijn drie manieren om toepassingen te verwijderen. U kunt toepassingen verwijderen via de Microsoft Store, Startmenu of Instellingen.

> [!WARNING]
> U kunt een systeem-app of de Microsoft Store verwijderen.

> [!IMPORTANT]
> Als uw HoloLens 2 meerdere gebruikers heeft, moet u zijn aangemeld als de gebruiker die de app heeft geïnstalleerd om deze te verwijderen.

### <a name="uninstall-from-the-microsoft-store"></a>Verwijderen van de Microsoft Store

Open de Microsoft Store in het menu **Start** en blader naar de toepassing die u wilt verwijderen.  Op de pagina Store heeft elke geïnstalleerde toepassing een **knop Verwijderen.**

### <a name="uninstall-from-the-start-menu"></a>Verwijderen van de Startmenu

Blader in **het** menu Start of in **Alle apps** lijst naar de app. Selecteer en houd in de wacht totdat het menu wordt weergegeven. Selecteer **vervolgens Verwijderen.**

### <a name="uninstall-from-settings"></a>Verwijderen van Instellingen

Selecteer in **het** menu Start de **optie Instellingen > Apps.** Zoek de app in de lijst, selecteer deze en klik vervolgens **op Verwijderen.**

Als u een app niet kunt verwijderen, kunt u [feedback geven](/hololens/hololens-feedback) via de Feedback-hub.
