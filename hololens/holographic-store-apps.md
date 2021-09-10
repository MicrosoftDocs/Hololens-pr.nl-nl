---
title: Toepassingen zoeken, installeren en verwijderen
description: De Microsoft Store is uw bron voor apps en games die werken met HoloLens.  Meer informatie over het zoeken, installeren en verwijderen van holografische apps.
ms.assetid: cbe9aa3a-884f-4a92-bf54-8d4917bc3435
ms.reviewer: v-miegge
ms.date: 9/7/2021
manager: jarrettr
keywords: hololens, store, uwp, app, install
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 3442da500e7554d7f97db2178cbaceeecad143ac
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427621"
---
# <a name="find-install-and-uninstall-applications-from-the-microsoft-store"></a>Toepassingen zoeken, installeren en verwijderen uit de Microsoft Store

De Microsoft Store is uw go-to-bron voor apps en games die werken met HoloLens. Wanneer u naar de Store op uw HoloLens, worden alle apps die u ziet, op de app uitgevoerd.

Apps op HoloLens een 2D-weergave of een holografische weergave. Apps die gebruikmaken van een 2D-weergave, zien eruit als vensters en kunnen overal om u heen worden geplaatst. Apps die gebruikmaken van een holografische weergave, omringen u en worden de enige app die u ziet.

HoloLens ondersteunt veel bestaande toepassingen uit de Microsoft Store en nieuwe apps die speciaal zijn gebouwd voor HoloLens.  Dit artikel is gericht op holografische toepassingen van de Microsoft Store.

Lees Aangepaste holographic-toepassingen voor meer informatie over het installeren en uitvoeren [van aangepaste apps.](holographic-custom-apps.md)

## <a name="find-apps"></a>Apps zoeken

Open de Microsoft Store in het **menu** Start. Blader vervolgens naar apps en games. U kunt [spraakopdrachten](hololens-cortana.md) gebruiken om te zoeken door 'Zoeken' te zeggen. Zodra het zoekvenster wordt geopend, zegt u 'Beginnen met dicteren' en begint u vervolgens wanneer u wordt gevraagd met het zeggen van uw zoektermen.

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
> De OneDrive-app wordt momenteel niet ondersteund voor Azure AD-accounts op HoloLens. U kunt het beste de Microsoft OneDrive PWA downloaden. [Volg deze stappen om de app te downloaden.]

## <a name="install-apps"></a>Apps installeren

Als u apps wilt downloaden, moet u zijn aangemeld met een Microsoft-account. Sommige apps zijn gratis en kunnen direct worden gedownload. Voor apps waarvoor een aankoop is vereist, moet u zijn aangemeld bij de Store met uw Microsoft-account een geldige betalingswijze hebben.

> [!NOTE]
> Het account dat u gebruikt op Microsoft Store hoeft niet hetzelfde te zijn als het account waarin u bent aangemeld. Als u een werk- of schoolaccount op uw HoloLens moet u zich mogelijk aanmelden met uw persoonlijke account in de Store-app om een aankoop te doen.

> [!TIP]
> Als u een betalingswijze wilt instellen, gaat u [naar account.microsoft.com](https://account.microsoft.com/) selecteert u Betalingswijze & **betalingsopties** toevoegen  >    >  **Betalingsoptie toevoegen.**

1. Als u het [ **menu Start** wilt openen,](holographic-home.md)voert u een [startbewegingen](/hololens/hololens2-basic-usage#start-gesture) [of](hololens1-basic-usage.md) een bloembewegingen uit op HoloLens (1e generatie).

1. Selecteer de Microsoft Store app. Nadat de Store-app is geopend:
   1. Gebruik de zoekbalk om te zoeken naar toepassingen.
   1. Selecteer essentiële apps of apps die specifiek zijn gemaakt HoloLens uit een van de gecureerde categorieën.
   1. Selecteer rechtsboven in de Store-app de knop **'...'** en selecteer vervolgens **Mijn** bibliotheek om eerder gekochte apps weer te geven.

1. Selecteer **Downloaden** of **Installeren** op de pagina van de toepassing (mogelijk is een aankoop vereist).

### <a name="install-microsoft-onedrive-pwa-app"></a>Een Microsoft OneDrive PWA installeren

Vereisten: de gebruiker heeft het apparaat HoloLens 2 aan zijn werkten tenant.

1. Open het menu Start en start de Edge-browser.

    ![Startmenu](images/office-pwa-1.jpg)

1. Ga op HoloLens naar [https://onedrive.live.com/about/signin](https://onedrive.live.com/about/signin) en voer de referenties van uw werkaccount in

    ![Aanmelden via het werk](images/office-pwa-2.jpg)

1. Nadat u zich hebt aangemeld bij uw OneDrive-webportal, wacht u 30 tot 60 seconden totdat de downloadknop PWA wordt weergeven

    ![PWA installeren](images/office-pwa-3.jpg)

1. Selecteer de knop PWA downloaden en installeer de app

    ![Installatieprompt](images/office-pwa-4.jpg)

1. Sluit de Edge-browser en selecteer Startmenu de knop Alle **apps** en start OneDrive PWA app met het **label Microsoft OneDrive**

    ![Alle apps met beide apps.](images/office-pwa-5.jpg)

> [!NOTE]
> De 'Microsoft OneDrive' is de PWA app, waarbij 'OneDrive' de oudere UWP is.

1. Vervolgens kunt u uw OneDrive zien.

    ![OneDrive PWA](images/office-pwa-6.jpg)

Zie ook: [Automatische uploads naar OneDrive voor bedrijven inschakelen](hololens-release-notes.md#onedrive-for-work-or-school-camera-roll-upload)

## <a name="update-apps"></a>Apps bijwerken

Als u een app wilt bijwerken die u hebt geïnstalleerd Microsoft Store, kunt u de app bijwerken vanuit de Microsoft Store app. Voor apps die voor de Microsoft Store voor Bedrijven zijn geïnstalleerd, kunt u deze apps ook bijwerken vanuit de Microsoft Store voor Bedrijven.

1. Als u het [ **menu Start** wilt openen,](holographic-home.md)voert u een [startbewegingen](/hololens/hololens2-basic-usage#start-gesture) [of](hololens1-basic-usage.md) een bloembewegingen uit op HoloLens (1e generatie).

1. Selecteer de Store-app.

1. Kijk rechtsboven in de Store-app.

1. Selecteer de **knop '...'** of 'Meer weergeven'.

   > [!div class="mx-imgBorder"]
   > ![Microsoft Store app-schermopname.](images/store-update-1.png)

1. Selecteer **Downloads en updates.**
    1. Als uw apparaat eerder updates heeft geïdentificeerd, is er mogelijk een pijl-omlaag en een getal dat updates in behandeling vertegenwoordigt.

1. Selecteer **Updates downloaden.** Uw apparaat zoekt nu naar updates en stelt deze in op downloaden en installeren.

   > [!div class="mx-imgBorder"]
   > ![Microsoft Store app-schermopname van het ontvangen van updates.](images/store-update-2.png.jpg)

> [!NOTE]
> Als de apps op uw apparaat zijn gedistribueerd door uw organisatie, kunnen ze worden bijgewerkt via dezelfde commerciële app-beheermethoden. Als dit van toepassing is op uw situatie, kunt u meer lezen via ons overzicht van de implementatie [van commerciële apps.](app-deploy-overview.md)
>
> Als u een aangepaste app wilt bijwerken die is ge sideload of geïmplementeerd, moet u dezelfde methode gebruiken met de bijgewerkte versie van uw app. Lees aangepaste holographic-toepassingen voor meer informatie over het installeren en uitvoeren [van aangepaste apps.](holographic-custom-apps.md)

## <a name="uninstall-apps"></a>Apps verwijderen

Er zijn drie manieren om toepassingen te verwijderen. U kunt toepassingen verwijderen via de Microsoft Store, Startmenu of Instellingen.

> [!WARNING]
> U kunt een systeem-app of de Microsoft Store verwijderen.

> [!IMPORTANT]
> Als uw HoloLens 2 meerdere gebruikers heeft, moet u zijn aangemeld als de gebruiker die de app heeft geïnstalleerd om deze te verwijderen.

### <a name="uninstall-from-the-microsoft-store"></a>Verwijderen van de Microsoft Store

Open de Microsoft Store in het menu **Start** en blader naar de toepassing die u wilt verwijderen.  Op de pagina Store heeft elke geïnstalleerde toepassing de **knop Verwijderen.**

### <a name="uninstall-from-the-start-menu"></a>Verwijderen van de Startmenu

Blader in **het** menu Start of in **Alle apps** lijst naar de app. Selecteer en houd in de wacht totdat het menu wordt weergegeven. Selecteer **vervolgens Verwijderen.**

### <a name="uninstall-from-settings"></a>Verwijderen uit Instellingen

Selecteer in **het** menu Start de **optie Instellingen > Apps.** Zoek de app in de lijst, selecteer deze en klik vervolgens **op Verwijderen.**

Als u een app niet kunt verwijderen, kunt u [feedback geven](/hololens/hololens-feedback) via de Feedback-hub.
