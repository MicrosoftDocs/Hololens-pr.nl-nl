---
title: Bijdragende instructies
description: Meer informatie over hoe u kunt bijdragen aan HoloLens documenten op het docs.microsoft.com platform met behulp GitHub Markdown met een smaak.
author: hferrone
ms.author: mattwoj
ms.date: 01/04/2021
ms.topic: article
ms.prod: hololens
ms.openlocfilehash: d511156d6940574deda7448a6f634c0004b8f053
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427163"
---
# <a name="contributing-to-the-hololens-documentation"></a>Bijdragen aan de HoloLens documentatie

Welkom bij de [HoloLens documentatie](https://github.com/MicrosoftDocs/Hololens)! Alle artikelen die u in deze repo maakt of **bewerkt, zijn zichtbaar voor het publiek.** 

HoloLens documenten worden weergegeven op het docs.microsoft.com-platform, dat gebruikmaakt van GitHub markdown met Markdig-functies. De inhoud die u in deze repo bewerkt, wordt opgemaakt in niet-geformatteerde pagina's die worden weergegeven op /hololens.

Deze pagina bevat de basisstappen en richtlijnen voor bijdragen en koppelingen naar de basisbeginselen van Markdown. Bedankt voor uw bijdrage!

## <a name="available-repos"></a>Beschikbare repos

| Naam van opslagplaats | URL |
| --- | --- |
| HoloLens | [MicrosoftDocs/HoloLens](https://github.com/MicrosoftDocs/Hololens) |
| Mixed Reality | [MicrosoftDocs/mixed-reality](/windows/mixed-reality) |
| Gids voor vr-fans | [MicrosoftDocs/mixed-reality/fanshandleiding](https://github.com/MicrosoftDocs/mixed-reality/tree/docs/enthusiast-guide) |

## <a name="before-you-start"></a>Voordat u begint

Als u nog geen account hebt, moet u een GitHub [maken.](https://github.com/join)

>[!NOTE]
>Als u een Microsoft-medewerker bent, koppelt u uw GitHub-account aan uw Microsoft-alias in de [Microsoft Open Source-portal.](https://repos.opensource.microsoft.com/) Word lid **van de organisaties Microsoft** en **MicrosoftDocs.**

Bij het instellen van GitHub account raden we ook deze voorzorgsmaatregelen aan:
- Maak een [sterk wachtwoord voor uw GitHub account](https://github.com/settings/admin).
- Schakel [twee-factor authentication in.](https://github.com/settings/two_factor_authentication/configure)
- Sla uw [herstelcodes](https://github.com/settings/auth/recovery-codes) op een veilige plaats op.
- Werk uw [openbare profielinstellingen bij.](https://github.com/settings/profile)
   - Stel uw naam in en overweeg uw openbare *e-mailadres in te* stellen op *Mijn e-mailadres niet tonen.*
   - U wordt aangeraden een profielafbeelding te uploaden, omdat er een miniatuur wordt weergegeven op docs-pagina's waar u een bijdrage aan levert.
- Als u van plan bent om de opdrachtregel te gebruiken, kunt u [Git-Aanmeldingsgegevensbeheer instellen voor Windows](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest). Op die manier hoeft u uw wachtwoord niet telkens in te voeren wanneer u een bijdrage levert.

Het publicatiesysteem is gekoppeld aan GitHub, dus deze stappen zijn belangrijk. U wordt vermeld als auteur of inzender voor elk artikel met behulp van uw GitHub alias.

## <a name="editing-an-existing-article"></a>Een bestaand artikel bewerken

Gebruik de volgende werkstroom om een bestaand artikel *via* een GitHub in een webbrowser bij te werken:

1. Navigeer naar het artikel dat u wilt bewerken in de map mixed-reality-docs.

2. Selecteer rechtsboven de knop Bewerken (potloodpictogram).

   ![Bewerk een artikel.](images/editpage.png)

   Hiermee wordt automatisch een vertakking voor eenmalig gebruik van de standaard vertakking gevorkd, _hoofd_.

   > [!NOTE]
   > Dit artikel bevat verwijzingen naar _master_, een term die Microsoft niet meer gebruikt. Zodra de term uit de software wordt verwijderd, verwijderen we deze uit dit artikel.
   
3. Bewerk de inhoud van het artikel volgens de basisbeginselen [van Markdown.](#markdown-basics)

4. Metagegevens boven aan elk artikel bijwerken:

   * **titel:** paginatitel die wordt weergegeven op het browsertabblad wanneer het artikel wordt weergegeven. Paginatitels worden gebruikt voor ZOEKMACHINE- en indexering, dus wijzig de titel niet tenzij dit nodig is (hoewel dit minder kritiek is voordat de documentatie openbaar wordt).
   * **beschrijving:** schrijf een korte beschrijving van de inhoud van het artikel, waardoor SEO en detectie worden versterkt.
   * **auteur:** als u de primaire eigenaar van de pagina bent, voegt u hier uw alias GitHub toe.
   * **ms.author:** als u de primaire eigenaar van de pagina bent, voegt u hier uw Microsoft-alias toe (u hebt niet alleen de @microsoft.com alias nodig).
   * **ms.date:** werk de datum bij als u belangrijke inhoud aan de pagina toevoegt, maar niet voor oplossingen zoals verduidelijking, opmaak, grammatica of spelling.
   * **trefwoorden: Trefwoorden** helpen bij zoekmachineoptimalisatie. Voeg trefwoorden toe, gescheiden door een komma en een spatie, die specifiek zijn voor uw artikel, maar geen leestekens na het laatste trefwoord in de lijst. U hoeft geen algemene trefwoorden toe te voegen die van toepassing zijn op alle artikelen, omdat deze elders worden beheerd. 
   
5. Wanneer u klaar bent met het bewerken van uw artikel, schuift u omlaag en **selecteert u Bestandswijziging voorstellen.**

6. Selecteer op de volgende pagina Pull-aanvraag **maken om** de automatisch gemaakte vertakking samen te voegen in de standaard branch, _master._

7. Herhaal de bovenstaande stappen voor het volgende artikel dat u wilt bewerken.

## <a name="renaming-or-deleting-an-existing-article"></a>De naam van een bestaand artikel wijzigen of verwijderen

Als de naam van een bestaand artikel wordt gewijzigd of verwijderd, moet u een omleiding toevoegen. Op die manier komt iedereen met een koppeling naar het bestaande artikel nog steeds op de juiste plaats terecht. Omleidingen worden beheerd door de .openpublishing.redirection.jsbestand in de hoofdmap van de repo.

Als u een omleiding wilt toevoegen .openpublishing.redirection.jsaan, voegt u een vermelding toe aan de `redirections` matrix:

```json
{
    "redirections": [
        {
            "source_path": "hololens/old-article.md",
            "redirect_url": "new-article#section-about-old-topic",
            "redirect_document_id": false
        },
```

- De `source_path` is het relatieve pad naar de opslagplaats naar het oude artikel dat u verwijdert. Zorg ervoor dat het pad begint met `mixed-reality-docs` en eindigt met `.md` .

- De `redirect_url` is de relatieve openbare URL van het oude artikel naar het nieuwe artikel. Zorg ervoor dat deze URL **niet** of bevat, omdat deze verwijst naar de openbare `mixed-reality-docs` URL en niet naar het pad naar de `.md` opslagplaats. Het is toegestaan om een koppeling te maken naar een sectie in het nieuwe artikel met `#section` behulp van . U kunt hier indien nodig ook een absoluut pad naar een andere site gebruiken.

- `redirect_document_id` geeft aan of u de document-id uit het vorige bestand wilt behouden. De standaardwaarde is `false`. Gebruik als u de kenmerkwaarde uit het omgeleide `true` `ms.documentid` artikel wilt behouden. Als u de document-id behoudt, worden gegevens, zoals paginaweergaven en rangschikkingen, overgebracht naar het doelartikel. Doe dit als de omleiding voornamelijk een naam heeft en geen aanwijzer is naar een ander artikel dat alleen betrekking heeft op een deel van dezelfde inhoud.

Als u een omleiding toevoegt, moet u ook het oude bestand verwijderen.

## <a name="creating-a-new-article"></a>Een nieuw artikel maken

Gebruik de volgende werkstroom om *nieuwe artikelen* te maken in de documentatie-repo via GitHub in een webbrowser:

1. Maak een fork van de standaardvertakking, _master_, van MicrosoftDocs/mixed-reality met behulp van de **knop Fork** in de rechterbovenpositie.

   ![Vertak de standaard branch, momenteel master genoemd.](images/forkbranch.png)

   > [!NOTE]
   > Dit artikel bevat verwijzingen naar _master_, een term die Microsoft niet meer gebruikt. Zodra de term uit de software wordt verwijderd, verwijderen we deze uit dit artikel.
   
2. Selecteer in de map mixed-reality-docs de optie **Nieuw bestand maken** in de rechterbovenmap.

3. Maak een paginanaam voor het artikel (gebruik afbreekstreepje in plaats van spaties en gebruik geen leestekens of apostroofs) en plaats '.md'

   ![Noem uw nieuwe pagina.](images/newpagetitle.png)
   
   >[!IMPORTANT]
   >Zorg ervoor dat u het nieuwe artikel maakt vanuit de map mixed-reality-docs. U kunt dit bevestigen door te controleren op '/mixed-reality-docs/' in de nieuwe bestandsnaamregel.

4. Voeg bovenaan de nieuwe pagina het volgende metagegevensblok toe:

   ```md
   ---
   title:
   description:
   author:
   ms.author:
   ms.date:
   ms.topic: article
   keywords:
   ---
   ```

5. Vul de relevante metagegevensvelden in zoals eerder beschreven in [Een bestaand artikel bewerken.](#editing-an-existing-article)

6. Schrijf artikelinhoud met behulp van [de basisbeginselen van Markdown.](#markdown-basics)

7. Voeg onderaan `## See also` het artikel een sectie toe met koppelingen naar andere relevante artikelen.

8. Wanneer u klaar bent, **selecteert u Nieuw bestand commit .**

9. Selecteer **Nieuwe pull-aanvraag** en voeg  de hoofdvertakking van uw fork samen in MicrosoftDocs/mixed-reality _master_ (zorg ervoor dat de pijl naar de juiste bestemming wijst).

   ![Maak een pull-aanvraag van uw fork in MicrosoftDocs/mixed-reality.](images/pr-to-master.png)

## <a name="markdown-basics"></a>Basisbeginselen van markdown

De volgende bronnen helpen u bij het bewerken van documentatie met behulp van de Markdown-taal:

- [Basisbeginselen van markdown](https://help.github.com/articles/basic-writing-and-formatting-syntax/)
- [Aanvullende bronnen voor het schrijven van Markdown voor docs.microsoft.com](/contribute/how-to-write-use-markdown)

### <a name="adding-tables"></a>Tabellen toevoegen

Vanwege de manier waarop docs.microsoft.com stijlen, hebben ze geen randen of aangepaste stijlen, zelfs niet als u inline CSS gebruikt. Het lijkt korte tijd te werken, maar uiteindelijk zal het platform de stijl uit de tabel stripen. Plan dus vooruit en houd uw tabellen eenvoudig. Hier is een site die Markdown-tabellen eenvoudig maakt: [Tables Generator]] ( https://www.tablesgenerator.com/markdown_tables) .

De [Docs Markdown-extensie voor Visual Studio Code](/teamblog/docs-extension) maakt het ook eenvoudig om tabel te genereren als u Visual Studio Code [(zie hieronder)](#using-visual-studio-code) gebruikt om de documentatie te bewerken.

### <a name="adding-images"></a>Afbeeldingen toevoegen

U moet uw afbeeldingen uploaden naar de map mixed-reality-docs/images in de repo en er vervolgens naar verwijzen in het artikel. Afbeeldingen worden automatisch op volledige grootte weer geven, wat betekent dat grote afbeeldingen de volledige breedte van het artikel vullen. We raden u aan de afbeelding vooraf in te delen voordat u ze uploadt. De aanbevolen breedte ligt tussen 600 en 700 pixels, maar u moet de grootte omhoog of omlaag aanpassen als het een compacte schermopname of een fractie van een schermopname is.

>[!IMPORTANT]
>U kunt alleen afbeeldingen uploaden naar uw gevorkte repo voordat u ze samenvoegt. Dus als u van plan bent om afbeeldingen toe te voegen aan een artikel, moet u [Visual Studio Code](#using-visual-studio-code) gebruiken om de afbeeldingen eerst toe te voegen aan de map 'afbeeldingen' van uw fork of om ervoor te zorgen dat u het volgende hebt gedaan in een webbrowser:
>
>1. De MicrosoftDocs-/mixed-reality-repo is gevorkt.
>2. U hebt het artikel in uw fork bewerkt.
>3. De afbeeldingen die u in uw artikel verwijst, hebben geüpload naar de map mixed-reality-docs/images in uw fork.
>4. U hebt een **pull-aanvraag gemaakt** om uw fork samen te voegen in de mastervertakking MicrosoftDocs/mixed-reality. 
>
>Volg de instructies voor het maken van een nieuw artikel voor meer informatie over het instellen van uw eigen [gevorkte repo.](#creating-a-new-article)

## <a name="previewing-your-work"></a>Een voorbeeld van uw werk bekijken

Tijdens het bewerken in GitHub webbrowser, kunt u het tabblad **Preview** bovenaan de pagina selecteren om een voorbeeld van uw werk te bekijken voordat u uw werk gaat uitvoeren. 

>[!NOTE]
>Een voorbeeld van uw wijzigingen review.docs.microsoft.com is alleen beschikbaar voor Microsoft-medewerkers

Microsoft-medewerkers: wanneer uw bijdragen zijn samengevoegd in de standaard branch, _hoofd_, kunt u de inhoud controleren voordat deze openbaar wordt op </hololens?branch=master>. Zoek uw artikel met behulp van de inhoudsopgave in de linkerkolom.

## <a name="editing-in-the-browser-vs-editing-with-a-desktop-client"></a>Bewerken in de browser versus bewerken met een desktopclient

Bewerken in de browser is de eenvoudigste manier om snelle wijzigingen aan te brengen, maar er zijn enkele nadelen:

- U krijgt geen spellingcontrole.
- U krijgt geen slimme koppeling naar andere artikelen (u moet handmatig de bestandsnaam van het artikel typen).
- Het uploaden en verwijzen naar afbeeldingen kan een probleem zijn.

Als u deze problemen liever niet wilt oplossen, gebruikt u een desktopclient zoals [Visual Studio Code](https://code.visualstudio.com/) met een aantal nuttige extensies [bij](#useful-extensions) het bijdragen.

## <a name="using-visual-studio-code"></a>Visual Studio Code gebruiken

Om de bovenstaande redenen [kunt](#editing-in-the-browser-vs-editing-with-a-desktop-client)u de voorkeur geven aan het gebruik van een desktopclient om documentatie te bewerken in plaats van een webbrowser. We raden u aan Visual Studio [code te gebruiken.](https://code.visualstudio.com/)

### <a name="setup"></a>Instellen

Volg deze stappen om uw Visual Studio code te configureren om met deze repo te werken:

1. In een webbrowser:
    1. Installeer [Git voor uw pc.](https://git-scm.com/downloads)
    2. Installeer [Visual Studio Code](https://code.visualstudio.com/).
    3. [Fork MicrosoftDocs/mixed-reality](#creating-a-new-article) als u dat nog niet hebt gedaan.
    4. Selecteer in uw fork Klonen of **downloaden en** kopieer de URL.
2. Maak een lokale kloon van uw fork in Visual Studio Code:
    1. Selecteer **opdrachtpalet** in het menu **Weergave.**
    2. Typ 'Git: Clone'.
    3. Plak de URL die u hebt gekopieerd.
    4. Kies waar u de kloon wilt opslaan op uw pc.
    5. Selecteer **Open repo** in het pop-uppop-up.

### <a name="editing-documentation"></a>Documentatie bewerken

Gebruik de volgende werkstroom om wijzigingen aan te brengen in de documentatie met Visual Studio Code:

>[!NOTE]
>Alle richtlijnen voor het [bewerken](#editing-an-existing-article) en [maken](#creating-a-new-article) van artikelen, en de basisbeginselen voor het bewerken van [Markdown,](#markdown-basics)van hierboven, zijn ook van toepassing wanneer u Visual Studio Code gebruikt.

1. Zorg ervoor dat uw gekloonde fork is bijgewerkt met de officiële repo.

   1. Maak in een webbrowser een pull-aanvraag om recente wijzigingen van andere inzenders in de standaardvertakking MicrosoftDocs/mixed-reality, _master,_ te synchroniseren met uw fork (zorg ervoor dat de pijl naar de juiste bestemming wijst).
      
      ![Synchroniseer wijzigingen van MicrosoftDocs/mixed-reality naar uw fork.](images/sync-repos.png)
      
   2. In Visual Studio Code selecteert u de synchronisatieknop om uw zojuist bijgewerkte fork te synchroniseren met de lokale kloon.
      
      ![Klik op de afbeelding van de knop Synchroniseren.](images/sync-clone.png)
      
2. Maak of bewerk artikelen in uw gekloonde repo met behulp Visual Studio Code.

   1. Bewerk een of meer artikelen (voeg indien nodig afbeeldingen toe aan de map afbeeldingen).
   
   2. **Sla de** wijzigingen op in **Explorer.**
      
      ![Kies Alles opslaan in Explorer](images/explorer-save.png)
      
   3. **Alle wijzigingen in** **Broncodebeheer (schrijf** het commit-bericht wanneer hier om wordt gevraagd) door.
   
      !['Alles commit' kiezen in Broncodebeheer](images/source-control-commit.png)
      
   4. Selecteer de **synchronisatieknop** om uw wijzigingen weer naar de oorsprong te synchroniseren (uw fork op GitHub).
      
      ![Klik op de knop Synchroniseren.](images/sync-back.png)
      
3. Maak in een webbrowser een pull-aanvraag om nieuwe wijzigingen in uw fork terug te synchroniseren met MicrosoftDocs/mixed-reality _master_ (zorg ervoor dat de pijl naar de juiste bestemming wijst).

   ![Maak een pull-aanvraag van uw fork in MicrosoftDocs/mixed-reality.](images/pr-to-master.png)

### <a name="useful-extensions"></a>Nuttige extensies

De volgende Visual Studio code-extensies zijn nuttig bij het bewerken van documentatie:

- [Docs Markdown-extensie voor Visual Studio Code:](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) gebruik **Alt+M om** een menu met ontwerpopties voor documenten weer te geven, zoals:
   - Zoek en verwijs naar afbeeldingen die u hebt geüpload.
   - Voeg opmaak toe, zoals lijsten, tabellen en docs-specifieke aanroepen, zoals `>[!NOTE]` .
   - Interne koppelingen en bladwijzers zoeken en hier naar verwijzen (koppelingen naar specifieke secties op een pagina).
   - Opmaakfouten worden gemarkeerd (beweeg de muisaanwijzer over de fout voor meer informatie).
- [Code Spell Checker:](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) verkeerd gespelde woorden worden onderstreept; klik met de rechtermuisknop op een verkeerd gespeld woord om het te wijzigen of op te slaan in de woordenlijst.
