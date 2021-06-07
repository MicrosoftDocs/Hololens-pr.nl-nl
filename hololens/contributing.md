---
title: Bijdragende instructies
description: Meer informatie over hoe u een bijdrage kunt leveren aan de HoloLens-documenten op docs.microsoft.com platform met Behulp van Markdown met een GitHub-smaak.
author: hferrone
ms.author: mattwoj
ms.date: 01/04/2021
ms.topic: article
ms.prod: hololens
ms.openlocfilehash: dd205ab1fe399d6612be982136c80733a5eb087e
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/19/2021
ms.locfileid: "111377797"
---
# <a name="contributing-to-the-hololens-documentation"></a><span data-ttu-id="06933-103">Bijdragen aan de HoloLens-documentatie</span><span class="sxs-lookup"><span data-stu-id="06933-103">Contributing to the HoloLens documentation</span></span>

<span data-ttu-id="06933-104">Welkom bij de [HoloLens-documentatie!](https://github.com/MicrosoftDocs/Hololens)</span><span class="sxs-lookup"><span data-stu-id="06933-104">Welcome to the [HoloLens documentation](https://github.com/MicrosoftDocs/Hololens)!</span></span> <span data-ttu-id="06933-105">Alle artikelen die u in deze repo maakt of **bewerkt, zijn zichtbaar voor het publiek.**</span><span class="sxs-lookup"><span data-stu-id="06933-105">Any articles you create or edit in this repo **will be visible to the public.**</span></span> 

<span data-ttu-id="06933-106">HoloLens-documenten worden weergegeven op docs.microsoft.com platform, dat gebruikmaakt van Markdown met een GitHub-versie met Markdig-functies.</span><span class="sxs-lookup"><span data-stu-id="06933-106">HoloLens docs are displayed on the docs.microsoft.com platform, which uses GitHub-flavored Markdown with Markdig features.</span></span> <span data-ttu-id="06933-107">De inhoud die u in deze repo bewerkt, wordt opgemaakt in niet-geformatteerde pagina's die worden weergegeven op https://docs.microsoft.com/hololens .</span><span class="sxs-lookup"><span data-stu-id="06933-107">The content you edit in this repo gets formatted into stylized pages that show up at https://docs.microsoft.com/hololens.</span></span> 

<span data-ttu-id="06933-108">Deze pagina bevat de basisstappen en richtlijnen voor bijdragen en koppelingen naar de basisbeginselen van Markdown.</span><span class="sxs-lookup"><span data-stu-id="06933-108">This page covers the basic steps and guidelines for contributing and links to Markdown basics.</span></span> <span data-ttu-id="06933-109">Bedankt voor uw bijdrage!</span><span class="sxs-lookup"><span data-stu-id="06933-109">Thanks for your contribution!</span></span>

## <a name="available-repos"></a><span data-ttu-id="06933-110">Beschikbare repos</span><span class="sxs-lookup"><span data-stu-id="06933-110">Available repos</span></span>

| <span data-ttu-id="06933-111">Naam van opslagplaats</span><span class="sxs-lookup"><span data-stu-id="06933-111">Repository name</span></span> | <span data-ttu-id="06933-112">URL</span><span class="sxs-lookup"><span data-stu-id="06933-112">URL</span></span> |
| --- | --- |
| <span data-ttu-id="06933-113">HoloLens</span><span class="sxs-lookup"><span data-stu-id="06933-113">HoloLens</span></span> | [<span data-ttu-id="06933-114">MicrosoftDocs/HoloLens</span><span class="sxs-lookup"><span data-stu-id="06933-114">MicrosoftDocs/HoloLens</span></span>](https://github.com/MicrosoftDocs/Hololens) |
| <span data-ttu-id="06933-115">Mixed Reality</span><span class="sxs-lookup"><span data-stu-id="06933-115">Mixed Reality</span></span> | [<span data-ttu-id="06933-116">MicrosoftDocs/mixed-reality</span><span class="sxs-lookup"><span data-stu-id="06933-116">MicrosoftDocs/mixed-reality</span></span>](https://docs.microsoft.com/windows/mixed-reality) |
| <span data-ttu-id="06933-117">Gids voor vr-fans</span><span class="sxs-lookup"><span data-stu-id="06933-117">VR Enthusiasts Guide</span></span> | [<span data-ttu-id="06933-118">MicrosoftDocs/mixed-reality/fanshandleiding</span><span class="sxs-lookup"><span data-stu-id="06933-118">MicrosoftDocs/mixed-reality/enthusiast-guide</span></span>](https://github.com/MicrosoftDocs/mixed-reality/tree/docs/enthusiast-guide) |

## <a name="before-you-start"></a><span data-ttu-id="06933-119">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="06933-119">Before you start</span></span>

<span data-ttu-id="06933-120">Als u er nog geen hebt, moet u een [GitHub-account maken.](https://github.com/join)</span><span class="sxs-lookup"><span data-stu-id="06933-120">If you don't already have one, you'll need to [create a GitHub account](https://github.com/join).</span></span>

>[!NOTE]
><span data-ttu-id="06933-121">Als u een Microsoft-medewerker bent, koppelt u uw GitHub-account aan uw Microsoft-alias in de [Microsoft Open Source-portal.](https://repos.opensource.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="06933-121">If you're a Microsoft employee, link your GitHub account to your Microsoft alias on the [Microsoft Open Source portal](https://repos.opensource.microsoft.com/).</span></span> <span data-ttu-id="06933-122">Word lid **van de organisaties Microsoft** en **MicrosoftDocs.**</span><span class="sxs-lookup"><span data-stu-id="06933-122">Join the **"Microsoft"** and **"MicrosoftDocs"** organizations.</span></span>

<span data-ttu-id="06933-123">Bij het instellen van uw GitHub-account raden we ook deze voorzorgsmaatregelen aan:</span><span class="sxs-lookup"><span data-stu-id="06933-123">When setting up your GitHub account, we also recommend these security precautions:</span></span>
- <span data-ttu-id="06933-124">Maak een [sterk wachtwoord voor uw GitHub-account.](https://github.com/settings/admin)</span><span class="sxs-lookup"><span data-stu-id="06933-124">Create a [strong password for your GitHub account](https://github.com/settings/admin).</span></span>
- <span data-ttu-id="06933-125">Schakel [twee-factor authentication in.](https://github.com/settings/two_factor_authentication/configure)</span><span class="sxs-lookup"><span data-stu-id="06933-125">Enable [two-factor authentication](https://github.com/settings/two_factor_authentication/configure).</span></span>
- <span data-ttu-id="06933-126">Sla uw [herstelcodes](https://github.com/settings/auth/recovery-codes) op een veilige plaats op.</span><span class="sxs-lookup"><span data-stu-id="06933-126">Save your [recovery codes](https://github.com/settings/auth/recovery-codes) in a safe place.</span></span>
- <span data-ttu-id="06933-127">Werk uw [openbare profielinstellingen bij.](https://github.com/settings/profile)</span><span class="sxs-lookup"><span data-stu-id="06933-127">Update your [public profile settings](https://github.com/settings/profile).</span></span>
   - <span data-ttu-id="06933-128">Stel uw naam in en overweeg uw openbare *e-mailadres in te* stellen op *Mijn e-mailadres niet tonen.*</span><span class="sxs-lookup"><span data-stu-id="06933-128">Set your name, and consider setting your *Public email* to *Don't show my email address*.</span></span>
   - <span data-ttu-id="06933-129">U wordt aangeraden een profielafbeelding te uploaden, omdat er een miniatuur wordt weergegeven op docs-pagina's waar u een bijdrage aan levert.</span><span class="sxs-lookup"><span data-stu-id="06933-129">We recommend you upload a profile picture because a thumbnail is shown on docs pages you contribute to.</span></span>
- <span data-ttu-id="06933-130">Als u van plan bent om de opdrachtregel te gebruiken, kunt u [Git-Aanmeldingsgegevensbeheer instellen voor Windows.](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest)</span><span class="sxs-lookup"><span data-stu-id="06933-130">If you plan to use the command line, consider setting up [Git Credential Manager for Windows](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest).</span></span> <span data-ttu-id="06933-131">Op die manier hoeft u uw wachtwoord niet telkens in te voeren wanneer u een bijdrage levert.</span><span class="sxs-lookup"><span data-stu-id="06933-131">That way, you won't have to enter your password every time you make a contribution.</span></span>

<span data-ttu-id="06933-132">Het publicatiesysteem is gekoppeld aan GitHub, dus deze stappen zijn belangrijk.</span><span class="sxs-lookup"><span data-stu-id="06933-132">The publishing system is tied to GitHub, so these steps are important.</span></span> <span data-ttu-id="06933-133">U wordt vermeld als auteur of inzender voor elk artikel met behulp van uw GitHub-alias.</span><span class="sxs-lookup"><span data-stu-id="06933-133">You'll be listed as either author or contributor to each article using your GitHub alias.</span></span>

## <a name="editing-an-existing-article"></a><span data-ttu-id="06933-134">Een bestaand artikel bewerken</span><span class="sxs-lookup"><span data-stu-id="06933-134">Editing an existing article</span></span>

<span data-ttu-id="06933-135">Gebruik de volgende werkstroom om een bestaand *artikel via* GitHub in een webbrowser bij te werken:</span><span class="sxs-lookup"><span data-stu-id="06933-135">Use the following workflow to make updates to *an existing article* via GitHub in a web browser:</span></span>

1. <span data-ttu-id="06933-136">Navigeer naar het artikel dat u wilt bewerken in de map mixed-reality-docs.</span><span class="sxs-lookup"><span data-stu-id="06933-136">Navigate to the article you wish to edit in the "mixed-reality-docs" folder.</span></span>

2. <span data-ttu-id="06933-137">Selecteer rechtsboven de knop Bewerken (potloodpictogram), waarmee automatisch een vertakking voor eenmalig gebruik van de master-vertakking wordt gevorkd.</span><span class="sxs-lookup"><span data-stu-id="06933-137">Select the edit button (pencil icon) in the top right, which will automatically fork a disposable branch off the 'master' branch.</span></span>

   ![Bewerk een artikel.](images/editpage.png)
   
3. <span data-ttu-id="06933-139">Bewerk de inhoud van het artikel volgens de [basisprincipes van Markdown.](#markdown-basics)</span><span class="sxs-lookup"><span data-stu-id="06933-139">Edit the content of the article according to the ["Markdown basics"](#markdown-basics).</span></span>

4. <span data-ttu-id="06933-140">Metagegevens boven aan elk artikel bijwerken:</span><span class="sxs-lookup"><span data-stu-id="06933-140">Update metadata at the top of each article:</span></span>

   * <span data-ttu-id="06933-141">**titel:** paginatitel die wordt weergegeven op het browsertabblad wanneer het artikel wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="06933-141">**title**: Page title that appears in the browser tab when the article is being viewed.</span></span> <span data-ttu-id="06933-142">Paginatitels worden gebruikt voor ZOEKMACHINE- en indexering, dus wijzig de titel niet tenzij dit nodig is (hoewel dit minder kritiek is voordat de documentatie openbaar wordt).</span><span class="sxs-lookup"><span data-stu-id="06933-142">Page titles are used for SEO and indexing, so don't change the title unless necessary (though this is less critical before documentation goes public).</span></span>
   * <span data-ttu-id="06933-143">**beschrijving:** schrijf een korte beschrijving van de inhoud van het artikel, waardoor SEO en detectie worden versterkt.</span><span class="sxs-lookup"><span data-stu-id="06933-143">**description**: Write a brief description of the article's content, which boosts SEO and discovery.</span></span>
   * <span data-ttu-id="06933-144">**auteur:** als u de primaire eigenaar van de pagina bent, voegt u hier uw GitHub-alias toe.</span><span class="sxs-lookup"><span data-stu-id="06933-144">**author**: If you're the primary owner of the page, add your GitHub alias here.</span></span>
   * <span data-ttu-id="06933-145">**ms.author:** als u de primaire eigenaar van de pagina bent, voegt u hier uw Microsoft-alias toe (u hebt niet alleen de @microsoft.com alias nodig).</span><span class="sxs-lookup"><span data-stu-id="06933-145">**ms.author**: If you're the primary owner of the page, add your Microsoft alias here (you don't need @microsoft.com, just the alias).</span></span>
   * <span data-ttu-id="06933-146">**ms.date:** werk de datum bij als u belangrijke inhoud aan de pagina toevoegt, maar niet voor oplossingen zoals verduidelijking, opmaak, grammatica of spelling.</span><span class="sxs-lookup"><span data-stu-id="06933-146">**ms.date**: Update the date if you're adding major content to the page, but not for fixes like clarification, formatting, grammar, or spelling.</span></span>
   * <span data-ttu-id="06933-147">**trefwoorden: Trefwoorden** helpen bij zoekmachineoptimalisatie.</span><span class="sxs-lookup"><span data-stu-id="06933-147">**keywords**: Keywords aid in SEO (search engine optimization).</span></span> <span data-ttu-id="06933-148">Voeg trefwoorden toe, gescheiden door een komma en een spatie, die specifiek zijn voor uw artikel, maar geen leestekens na het laatste trefwoord in de lijst.</span><span class="sxs-lookup"><span data-stu-id="06933-148">Add keywords, separated by a comma and a space, that are specific to your article, but no punctuation after the last keyword in your list.</span></span> <span data-ttu-id="06933-149">U hoeft geen algemene trefwoorden toe te voegen die van toepassing zijn op alle artikelen, omdat deze elders worden beheerd.</span><span class="sxs-lookup"><span data-stu-id="06933-149">You don't need to add global keywords that apply to all articles, as those are managed elsewhere.</span></span> 
   
5. <span data-ttu-id="06933-150">Wanneer u klaar bent met het bewerken van uw artikel, schuift u omlaag en **selecteert u Bestandswijziging voorstellen.**</span><span class="sxs-lookup"><span data-stu-id="06933-150">When you've completed your article edits, scroll down and select **Propose file change**.</span></span>

6. <span data-ttu-id="06933-151">Selecteer op de volgende pagina **Pull-aanvraag maken om** de automatisch gemaakte vertakking samen te voegen in master.</span><span class="sxs-lookup"><span data-stu-id="06933-151">On the next page, select **Create pull request** to merge your automatically created branch into 'master.'</span></span>

7. <span data-ttu-id="06933-152">Herhaal de bovenstaande stappen voor het volgende artikel dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="06933-152">Repeat the steps above for the next article you want to edit.</span></span>

## <a name="renaming-or-deleting-an-existing-article"></a><span data-ttu-id="06933-153">De naam van een bestaand artikel wijzigen of verwijderen</span><span class="sxs-lookup"><span data-stu-id="06933-153">Renaming or deleting an existing article</span></span>

<span data-ttu-id="06933-154">Als de naam van een bestaand artikel wordt gewijzigd of verwijderd, moet u een omleiding toevoegen.</span><span class="sxs-lookup"><span data-stu-id="06933-154">If your change will rename or delete an existing article, be sure to add a redirect.</span></span> <span data-ttu-id="06933-155">Op die manier komt iedereen met een koppeling naar het bestaande artikel nog steeds op de juiste plaats terecht.</span><span class="sxs-lookup"><span data-stu-id="06933-155">That way, anyone with a link to the existing article will still end up in the right place.</span></span> <span data-ttu-id="06933-156">Omleidingen worden beheerd door de .openpublishing.redirection.jsin het bestand in de hoofdmap van de repo.</span><span class="sxs-lookup"><span data-stu-id="06933-156">Redirects are managed by the .openpublishing.redirection.json file in the root of the repo.</span></span>

<span data-ttu-id="06933-157">Als u een omleiding wilt toevoegen .openpublishing.redirection.jsaan, voegt u een vermelding toe aan de `redirections` matrix:</span><span class="sxs-lookup"><span data-stu-id="06933-157">To add a redirect to .openpublishing.redirection.json, add an entry to the `redirections` array:</span></span>

```json
{
    "redirections": [
        {
            "source_path": "hololens/old-article.md",
            "redirect_url": "new-article#section-about-old-topic",
            "redirect_document_id": false
        },
```

- <span data-ttu-id="06933-158">De `source_path` is het relatieve pad naar de opslagplaats naar het oude artikel dat u verwijdert.</span><span class="sxs-lookup"><span data-stu-id="06933-158">The `source_path` is the relative repository path to the old article that you're removing.</span></span> <span data-ttu-id="06933-159">Zorg ervoor dat het pad begint met `mixed-reality-docs` en eindigt met `.md` .</span><span class="sxs-lookup"><span data-stu-id="06933-159">Be sure the path starts with `mixed-reality-docs` and ends with `.md`.</span></span>

- <span data-ttu-id="06933-160">De `redirect_url` is de relatieve openbare URL van het oude artikel naar het nieuwe artikel.</span><span class="sxs-lookup"><span data-stu-id="06933-160">The `redirect_url` is the relative public URL from the old article to the new article.</span></span> <span data-ttu-id="06933-161">Zorg ervoor dat deze URL **geen** of bevat, omdat deze verwijst naar de openbare `mixed-reality-docs` URL en niet naar het pad naar de `.md` opslagplaats.</span><span class="sxs-lookup"><span data-stu-id="06933-161">Be sure that this URL **doesn't** contain `mixed-reality-docs` or `.md`, as it refers to the public URL and not the repository path.</span></span> <span data-ttu-id="06933-162">Het is toegestaan om een koppeling te maken naar een sectie in het nieuwe artikel met `#section` behulp van .</span><span class="sxs-lookup"><span data-stu-id="06933-162">Linking to a section within the new article using `#section` is allowed.</span></span> <span data-ttu-id="06933-163">U kunt hier indien nodig ook een absoluut pad naar een andere site gebruiken.</span><span class="sxs-lookup"><span data-stu-id="06933-163">You can also use an absolute path to another site here, if necessary.</span></span>

- <span data-ttu-id="06933-164">`redirect_document_id` geeft aan of u de document-id uit het vorige bestand wilt behouden.</span><span class="sxs-lookup"><span data-stu-id="06933-164">`redirect_document_id` indicates whether you would like to keep the document ID from the previous file.</span></span> <span data-ttu-id="06933-165">De standaardwaarde is `false`.</span><span class="sxs-lookup"><span data-stu-id="06933-165">The default is `false`.</span></span> <span data-ttu-id="06933-166">Gebruik `true` als u de kenmerkwaarde uit het `ms.documentid` omgeleide artikel wilt behouden.</span><span class="sxs-lookup"><span data-stu-id="06933-166">Use `true` if you want to preserve the `ms.documentid` attribute value from the redirected article.</span></span> <span data-ttu-id="06933-167">Als u de document-id behoudt, worden gegevens, zoals paginaweergaven en rangschikkingen, overgebracht naar het doelartikel.</span><span class="sxs-lookup"><span data-stu-id="06933-167">If you preserve the document ID, data, such as page views and rankings, will be transferred to the target article.</span></span> <span data-ttu-id="06933-168">Doe dit als de omleiding voornamelijk een naam heeft en geen aanwijzer is naar een ander artikel dat alleen betrekking heeft op een deel van dezelfde inhoud.</span><span class="sxs-lookup"><span data-stu-id="06933-168">Do this if the redirect is primarily a rename, and not a pointer to different article that only covers some of the same content.</span></span>

<span data-ttu-id="06933-169">Als u een omleiding toevoegt, moet u ook het oude bestand verwijderen.</span><span class="sxs-lookup"><span data-stu-id="06933-169">If you add a redirect, be sure to delete the old file as well.</span></span>

## <a name="creating-a-new-article"></a><span data-ttu-id="06933-170">Een nieuw artikel maken</span><span class="sxs-lookup"><span data-stu-id="06933-170">Creating a new article</span></span>

<span data-ttu-id="06933-171">Gebruik de volgende werkstroom om *nieuwe artikelen* te maken in de opslagplaats voor documentatie via GitHub in een webbrowser:</span><span class="sxs-lookup"><span data-stu-id="06933-171">Use the following workflow to *create new articles* in the documentation repo via GitHub in a web browser:</span></span>

1. <span data-ttu-id="06933-172">Maak een fork van de mastervertakking MicrosoftDocs/mixed-reality (met behulp van de **knop Fork** in de rechterbovenpositie).</span><span class="sxs-lookup"><span data-stu-id="06933-172">Create a fork off the MicrosoftDocs/mixed-reality 'master' branch (using the **Fork** button in the top right).</span></span>

   ![Fork de master branch.](images/forkbranch.png)
   
2. <span data-ttu-id="06933-174">Selecteer in de map mixed-reality-docs de optie **Nieuw bestand maken** in de rechterbovenmap.</span><span class="sxs-lookup"><span data-stu-id="06933-174">In the "mixed-reality-docs" folder, select **Create new file** in the top right.</span></span>

3. <span data-ttu-id="06933-175">Maak een paginanaam voor het artikel (gebruik afbreekstreepje in plaats van spaties en gebruik geen leestekens of apostroofs) en plaats '.md'</span><span class="sxs-lookup"><span data-stu-id="06933-175">Create a page name for the article (use hyphens instead of spaces and don't use punctuation or apostrophes) and append ".md"</span></span>

   ![Noem uw nieuwe pagina.](images/newpagetitle.png)
   
   >[!IMPORTANT]
   ><span data-ttu-id="06933-177">Zorg ervoor dat u het nieuwe artikel maakt vanuit de map mixed-reality-docs.</span><span class="sxs-lookup"><span data-stu-id="06933-177">Make sure you create the new article from within the "mixed-reality-docs" folder.</span></span> <span data-ttu-id="06933-178">U kunt dit bevestigen door te controleren op '/mixed-reality-docs/' in de nieuwe bestandsnaamregel.</span><span class="sxs-lookup"><span data-stu-id="06933-178">You can confirm this by checking for "/mixed-reality-docs/" in the new file name line.</span></span>

4. <span data-ttu-id="06933-179">Voeg bovenaan de nieuwe pagina het volgende metagegevensblok toe:</span><span class="sxs-lookup"><span data-stu-id="06933-179">At the top of your new page, add the following metadata block:</span></span>

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

5. <span data-ttu-id="06933-180">Vul de relevante metagegevensvelden in volgens de instructies in de [bovenstaande sectie](#editing-an-existing-article).</span><span class="sxs-lookup"><span data-stu-id="06933-180">Fill in the relevant metadata fields per the instructions in the [section above](#editing-an-existing-article).</span></span>

6. <span data-ttu-id="06933-181">Schrijf artikelinhoud met de [basisbeginselen van Markdown.](#markdown-basics)</span><span class="sxs-lookup"><span data-stu-id="06933-181">Write article content using [Markdown basics](#markdown-basics).</span></span>

7. <span data-ttu-id="06933-182">Voeg onderaan `## See also` het artikel een sectie toe met koppelingen naar andere relevante artikelen.</span><span class="sxs-lookup"><span data-stu-id="06933-182">Add a `## See also` section at the bottom of the article with links to other relevant articles.</span></span>

8. <span data-ttu-id="06933-183">Wanneer u klaar bent, **selecteert u Nieuw bestand commit .**</span><span class="sxs-lookup"><span data-stu-id="06933-183">When finished, select **Commit new file**.</span></span>

9. <span data-ttu-id="06933-184">Selecteer **Nieuwe pull-aanvraag** en voeg de mastervertakking van uw fork samen in MicrosoftDocs/mixed-reality master (zorg ervoor dat de pijl de juiste kant op wijst).</span><span class="sxs-lookup"><span data-stu-id="06933-184">Select **New pull request** and merge your fork's 'master' branch into MicrosoftDocs/mixed-reality 'master' (make sure the arrow is pointing the correct way).</span></span>

   ![Een pull-aanvraag maken van uw fork in MicrosoftDocs/mixed-reality](images/pr-to-master.png)

## <a name="markdown-basics"></a><span data-ttu-id="06933-186">Basisbeginselen van markdown</span><span class="sxs-lookup"><span data-stu-id="06933-186">Markdown basics</span></span>

<span data-ttu-id="06933-187">De volgende bronnen helpen u bij het bewerken van documentatie met behulp van de Markdown-taal:</span><span class="sxs-lookup"><span data-stu-id="06933-187">The following resources will help you learn how to edit documentation using the Markdown language:</span></span>

- [<span data-ttu-id="06933-188">Basisbeginselen van markdown</span><span class="sxs-lookup"><span data-stu-id="06933-188">Markdown basics</span></span>](https://help.github.com/articles/basic-writing-and-formatting-syntax/)
- [<span data-ttu-id="06933-189">Aanvullende bronnen voor het schrijven van Markdown voor docs.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="06933-189">Additional resources for writing Markdown for docs.microsoft.com</span></span>](https://docs.microsoft.com/contribute/how-to-write-use-markdown)

### <a name="adding-tables"></a><span data-ttu-id="06933-190">Tabellen toevoegen</span><span class="sxs-lookup"><span data-stu-id="06933-190">Adding tables</span></span>

<span data-ttu-id="06933-191">Vanwege de manier waarop docs.microsoft.com, hebben ze geen randen of aangepaste stijlen, zelfs niet als u inline CSS gebruikt.</span><span class="sxs-lookup"><span data-stu-id="06933-191">Because of the way docs.microsoft.com styles tables, they won’t have borders or custom styles, even if you try inline CSS.</span></span> <span data-ttu-id="06933-192">Het lijkt korte tijd te werken, maar uiteindelijk zal het platform de stijl uit de tabel stripen.</span><span class="sxs-lookup"><span data-stu-id="06933-192">It will appear to work for a short period of time, but eventually the platform will strip the styling out of the table.</span></span> <span data-ttu-id="06933-193">Plan dus vooruit en houd uw tabellen eenvoudig.</span><span class="sxs-lookup"><span data-stu-id="06933-193">So plan ahead and keep your tables simple.</span></span> <span data-ttu-id="06933-194">[Hier is een site die Markdown-tabellen eenvoudig maakt.](https://www.tablesgenerator.com/markdown_tables)</span><span class="sxs-lookup"><span data-stu-id="06933-194">[Here’s a site that makes Markdown tables easy](https://www.tablesgenerator.com/markdown_tables).</span></span>

<span data-ttu-id="06933-195">Met [de Docs Markdown-extensie voor Visual Studio Code](https://docs.microsoft.com/teamblog/docs-extension) kunt u ook eenvoudig tabelgeneraties uitvoeren als u Visual Studio Code [(zie hieronder)](#using-visual-studio-code) gebruikt om de documentatie te bewerken.</span><span class="sxs-lookup"><span data-stu-id="06933-195">The [Docs Markdown Extension for Visual Studio Code](https://docs.microsoft.com/teamblog/docs-extension) also makes table generation easy if you're using [Visual Studio Code (see below)](#using-visual-studio-code) to edit the documentation.</span></span>

### <a name="adding-images"></a><span data-ttu-id="06933-196">Afbeeldingen toevoegen</span><span class="sxs-lookup"><span data-stu-id="06933-196">Adding images</span></span>

<span data-ttu-id="06933-197">U moet uw afbeeldingen uploaden naar de map mixed-reality-docs/images in de repo en er vervolgens naar verwijzen in het artikel.</span><span class="sxs-lookup"><span data-stu-id="06933-197">You’ll need to upload your images to the "mixed-reality-docs/images" folder in the repo, and then reference them appropriately in the article.</span></span> <span data-ttu-id="06933-198">Afbeeldingen worden automatisch op volledige grootte weer geven, wat betekent dat grote afbeeldingen de volledige breedte van het artikel vullen.</span><span class="sxs-lookup"><span data-stu-id="06933-198">Images will automatically show up at full-size, which means large images will fill the entire width of the article.</span></span> <span data-ttu-id="06933-199">We raden u aan de afbeelding vooraf te izingen voordat u ze uploadt.</span><span class="sxs-lookup"><span data-stu-id="06933-199">We recommend pre-sizing your images before uploading them.</span></span> <span data-ttu-id="06933-200">De aanbevolen breedte ligt tussen 600 en 700 pixels, maar u moet de grootte omhoog of omlaag aanpassen als het een compacte schermopname of een fractie van een schermopname is.</span><span class="sxs-lookup"><span data-stu-id="06933-200">The recommended width is between 600 and 700 pixels, though you should size up or down if it’s a dense screenshot or a fraction of a screenshot, respectively.</span></span>

>[!IMPORTANT]
><span data-ttu-id="06933-201">U kunt alleen afbeeldingen uploaden naar uw gevorkte repo voordat u deze samenvoegt.</span><span class="sxs-lookup"><span data-stu-id="06933-201">You can only upload images to your forked repo before merging.</span></span> <span data-ttu-id="06933-202">Dus als u van plan bent om afbeeldingen toe te voegen aan een artikel, moet u [Visual Studio Code](#using-visual-studio-code) gebruiken om de afbeeldingen eerst toe te voegen aan de map 'afbeeldingen' van uw fork of om ervoor te zorgen dat u het volgende hebt gedaan in een webbrowser:</span><span class="sxs-lookup"><span data-stu-id="06933-202">So, if you plan on adding images to an article, you'll need to [use Visual Studio Code](#using-visual-studio-code) to add the images to your fork's "images" folder first or make sure you've done the following in a web browser:</span></span>
>
>1. <span data-ttu-id="06933-203">De MicrosoftDocs-/mixed reality-repo is gevorkt.</span><span class="sxs-lookup"><span data-stu-id="06933-203">Forked the MicrosoftDocs/mixed-reality repo.</span></span>
>2. <span data-ttu-id="06933-204">U hebt het artikel in uw fork bewerkt.</span><span class="sxs-lookup"><span data-stu-id="06933-204">Edited the article in your fork.</span></span>
>3. <span data-ttu-id="06933-205">U hebt de afbeeldingen waar u in uw artikel naar verwijst, geüpload naar de map mixed-reality-docs/images in uw fork.</span><span class="sxs-lookup"><span data-stu-id="06933-205">Uploaded the images you're referencing in your article to the "mixed-reality-docs/images" folder in your fork.</span></span>
>4. <span data-ttu-id="06933-206">U hebt een **pull-aanvraag** gemaakt om uw fork samen te voegen in de mastervertakking MicrosoftDocs/mixed-reality.</span><span class="sxs-lookup"><span data-stu-id="06933-206">Created a **pull request** to merge your fork into the MicrosoftDocs/mixed-reality 'master' branch.</span></span>
>
><span data-ttu-id="06933-207">Volg de instructies voor het maken van een nieuw artikel voor meer informatie over het instellen van uw eigen [gevorkte repo.](#creating-a-new-article)</span><span class="sxs-lookup"><span data-stu-id="06933-207">To learn how to set up your own forked repo, follow the instructions for [creating a new article](#creating-a-new-article).</span></span>

## <a name="previewing-your-work"></a><span data-ttu-id="06933-208">Een voorbeeld van uw werk bekijken</span><span class="sxs-lookup"><span data-stu-id="06933-208">Previewing your work</span></span>

<span data-ttu-id="06933-209">Tijdens het bewerken in GitHub via een webbrowser, kunt u bovenaan de pagina het tabblad **Preview** selecteren om een voorbeeld van uw werk te bekijken voordat u uw werk gaat uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="06933-209">While editing in GitHub via a web browser, you can select the **Preview** tab near the top of the page to preview your work before committing.</span></span> 

>[!NOTE]
><span data-ttu-id="06933-210">Een voorbeeld van uw wijzigingen op review.docs.microsoft.com is alleen beschikbaar voor Microsoft-medewerkers</span><span class="sxs-lookup"><span data-stu-id="06933-210">Previewing your changes on review.docs.microsoft.com is only available to Microsoft employees</span></span>

<span data-ttu-id="06933-211">Microsoft-medewerkers: zodra uw bijdragen zijn samengevoegd in de master-vertakking, kunt u de inhoud controleren voordat deze openbaar wordt op https://review.docs.microsoft.com/hololens?branch=master .</span><span class="sxs-lookup"><span data-stu-id="06933-211">Microsoft employees: once your contributions have been merged into the 'master' branch, you can review the content before it goes public at https://review.docs.microsoft.com/hololens?branch=master.</span></span> <span data-ttu-id="06933-212">Zoek uw artikel met behulp van de inhoudsopgave in de linkerkolom.</span><span class="sxs-lookup"><span data-stu-id="06933-212">Find your article using the table of contents in the left column.</span></span>

## <a name="editing-in-the-browser-vs-editing-with-a-desktop-client"></a><span data-ttu-id="06933-213">Bewerken in de browser versus bewerken met een desktopclient</span><span class="sxs-lookup"><span data-stu-id="06933-213">Editing in the browser vs. editing with a desktop client</span></span>

<span data-ttu-id="06933-214">Bewerken in de browser is de eenvoudigste manier om snelle wijzigingen aan te brengen, maar er zijn enkele nadelen:</span><span class="sxs-lookup"><span data-stu-id="06933-214">Editing in the browser is the easiest way to make quick changes, however, there are a few disadvantages:</span></span>

- <span data-ttu-id="06933-215">U krijgt geen spellingcontrole.</span><span class="sxs-lookup"><span data-stu-id="06933-215">You don't get spell-check.</span></span>
- <span data-ttu-id="06933-216">U krijgt geen slimme koppeling naar andere artikelen (u moet de bestandsnaam van het artikel handmatig typen).</span><span class="sxs-lookup"><span data-stu-id="06933-216">You don't get any smart-linking to other articles (you have to manually type the article's filename).</span></span>
- <span data-ttu-id="06933-217">Het uploaden en verwijzen naar afbeeldingen kan een probleem zijn.</span><span class="sxs-lookup"><span data-stu-id="06933-217">It can be a hassle to upload and reference images.</span></span>

<span data-ttu-id="06933-218">Als u deze problemen liever niet wilt oplossen, gebruikt u een desktopclient zoals [Visual Studio Code](https://code.visualstudio.com/) met een aantal nuttige extensies bij [het](#useful-extensions) bijdragen.</span><span class="sxs-lookup"><span data-stu-id="06933-218">If you'd rather not deal with these issues, use a desktop client like [Visual Studio Code](https://code.visualstudio.com/) with a couple [helpful extensions](#useful-extensions) when contributing.</span></span>

## <a name="using-visual-studio-code"></a><span data-ttu-id="06933-219">Visual Studio Code gebruiken</span><span class="sxs-lookup"><span data-stu-id="06933-219">Using Visual Studio Code</span></span>

<span data-ttu-id="06933-220">Om de bovenstaande redenen [kunt](#editing-in-the-browser-vs-editing-with-a-desktop-client)u de voorkeur geven aan het gebruik van een desktopclient om documentatie te bewerken in plaats van een webbrowser.</span><span class="sxs-lookup"><span data-stu-id="06933-220">For the reasons listed [above](#editing-in-the-browser-vs-editing-with-a-desktop-client), you may prefer using a desktop client to edit documentation instead of a web browser.</span></span> <span data-ttu-id="06933-221">We raden u aan [om Visual Studio Code te gebruiken.](https://code.visualstudio.com/)</span><span class="sxs-lookup"><span data-stu-id="06933-221">We recommend using [Visual Studio Code](https://code.visualstudio.com/).</span></span>

### <a name="setup"></a><span data-ttu-id="06933-222">Instellen</span><span class="sxs-lookup"><span data-stu-id="06933-222">Setup</span></span>

<span data-ttu-id="06933-223">Volg deze stappen om Visual Studio Code te configureren om met deze repo te werken:</span><span class="sxs-lookup"><span data-stu-id="06933-223">Follow these steps to configure Visual Studio Code to work with this repo:</span></span>

1. <span data-ttu-id="06933-224">In een webbrowser:</span><span class="sxs-lookup"><span data-stu-id="06933-224">In a web browser:</span></span>
    1. <span data-ttu-id="06933-225">Installeer [Git voor uw pc.](https://git-scm.com/downloads)</span><span class="sxs-lookup"><span data-stu-id="06933-225">Install [Git for your PC](https://git-scm.com/downloads).</span></span>
    2. <span data-ttu-id="06933-226">Installeer [Visual Studio Code](https://code.visualstudio.com/).</span><span class="sxs-lookup"><span data-stu-id="06933-226">Install [Visual Studio Code](https://code.visualstudio.com/).</span></span>
    3. <span data-ttu-id="06933-227">[Fork MicrosoftDocs/mixed-reality](#creating-a-new-article) als u dat nog niet hebt gedaan.</span><span class="sxs-lookup"><span data-stu-id="06933-227">[Fork MicrosoftDocs/mixed-reality](#creating-a-new-article) if you haven't already.</span></span>
    4. <span data-ttu-id="06933-228">Selecteer in uw fork Klonen of **downloaden en** kopieer de URL.</span><span class="sxs-lookup"><span data-stu-id="06933-228">In your fork, select **Clone or download** and copy the URL.</span></span>
2. <span data-ttu-id="06933-229">Maak een lokale kloon van uw fork in Visual Studio Code:</span><span class="sxs-lookup"><span data-stu-id="06933-229">Create a local clone of your fork in Visual Studio Code:</span></span>
    1. <span data-ttu-id="06933-230">Selecteer **opdrachtpalet** in het menu **Weergave.**</span><span class="sxs-lookup"><span data-stu-id="06933-230">From the **View** menu, select **Command Palette**.</span></span>
    2. <span data-ttu-id="06933-231">Typ 'Git: Clone'.</span><span class="sxs-lookup"><span data-stu-id="06933-231">Type "Git: Clone."</span></span>
    3. <span data-ttu-id="06933-232">Plak de URL die u hebt gekopieerd.</span><span class="sxs-lookup"><span data-stu-id="06933-232">Paste the URL you copied.</span></span>
    4. <span data-ttu-id="06933-233">Kies waar u de kloon wilt opslaan op uw pc.</span><span class="sxs-lookup"><span data-stu-id="06933-233">Choose where to save the clone on your PC.</span></span>
    5. <span data-ttu-id="06933-234">Selecteer In de pop-up de optie **Repo** openen.</span><span class="sxs-lookup"><span data-stu-id="06933-234">Select **Open repo** in the pop-up.</span></span>

### <a name="editing-documentation"></a><span data-ttu-id="06933-235">Documentatie bewerken</span><span class="sxs-lookup"><span data-stu-id="06933-235">Editing documentation</span></span>

<span data-ttu-id="06933-236">Gebruik de volgende werkstroom om wijzigingen aan te brengen in de documentatie met Visual Studio Code:</span><span class="sxs-lookup"><span data-stu-id="06933-236">Use the following workflow to make changes to the documentation with Visual Studio Code:</span></span>

>[!NOTE]
><span data-ttu-id="06933-237">Alle richtlijnen voor het [bewerken](#editing-an-existing-article) en [maken](#creating-a-new-article) van artikelen, en de basisbeginselen van het bewerken van [Markdown,](#markdown-basics)van hierboven, zijn ook van toepassing wanneer u Visual Studio Code gebruikt.</span><span class="sxs-lookup"><span data-stu-id="06933-237">All the guidance for [editing](#editing-an-existing-article) and [creating](#creating-a-new-article) articles, and the [basics of editing Markdown](#markdown-basics), from above applies when using Visual Studio Code as well.</span></span>

1. <span data-ttu-id="06933-238">Zorg ervoor dat de gekloonde fork is bijgewerkt met de officiële repo.</span><span class="sxs-lookup"><span data-stu-id="06933-238">Make sure your cloned fork is up to date with the official repo.</span></span>

   1. <span data-ttu-id="06933-239">Maak in een webbrowser een pull-aanvraag om recente wijzigingen van andere inzenders in MicrosoftDocs/mixed-reality master te synchroniseren met uw fork (zorg ervoor dat de pijl de juiste kant op wijst).</span><span class="sxs-lookup"><span data-stu-id="06933-239">In a web browser, create a pull request to sync recent changes from other contributors in MicrosoftDocs/mixed-reality 'master' to your fork (make sure the arrow is pointing the right way).</span></span>
      
      ![Wijzigingen van MicrosoftDocs/mixed-reality synchroniseren met uw fork](images/sync-repos.png)
      
   2. <span data-ttu-id="06933-241">Selecteer in Visual Studio Code de knop Synchroniseren om uw zojuist bijgewerkte fork te synchroniseren met de lokale kloon.</span><span class="sxs-lookup"><span data-stu-id="06933-241">In Visual Studio Code, select the sync button to sync your freshly updated fork to the local clone.</span></span>
      
      ![Klik op de afbeelding van de synchronisatieknop](images/sync-clone.png)
      
2. <span data-ttu-id="06933-243">Maak of bewerk artikelen in uw gekloonde repo met behulp Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="06933-243">Create or edit articles in your cloned repo using Visual Studio Code.</span></span>

   1. <span data-ttu-id="06933-244">Bewerk een of meer artikelen (voeg indien nodig afbeeldingen toe aan de map afbeeldingen).</span><span class="sxs-lookup"><span data-stu-id="06933-244">Edit one or more articles (add images to “images” folder if necessary).</span></span>
   
   2. <span data-ttu-id="06933-245">**Sla de** wijzigingen op in **Explorer**.</span><span class="sxs-lookup"><span data-stu-id="06933-245">**Save** changes in **Explorer**.</span></span>
      
      ![Kies Alles opslaan in Explorer](images/explorer-save.png)
      
   3. <span data-ttu-id="06933-247">**Alle wijzigingen** in **Broncodebeheer (schrijf** het commit-bericht wanneer hier om wordt gevraagd) door.</span><span class="sxs-lookup"><span data-stu-id="06933-247">**Commit all** changes in **Source Control** (write commit message when prompted).</span></span>
   
      ![Kies Alles doorbesturingselementen in Broncodebeheer](images/source-control-commit.png)
      
   4. <span data-ttu-id="06933-249">Selecteer de **synchronisatieknop** om uw wijzigingen terug te synchroniseren naar de oorsprong (uw fork op GitHub).</span><span class="sxs-lookup"><span data-stu-id="06933-249">Select the **sync** button to sync your changes back to origin (your fork on GitHub).</span></span>
      
      ![Klik op de knop Synchroniseren](images/sync-back.png)
      
3. <span data-ttu-id="06933-251">Maak in een webbrowser een pull-aanvraag om nieuwe wijzigingen in uw fork terug te synchroniseren met MicrosoftDocs/mixed-reality master (zorg ervoor dat de pijl de juiste kant op wijst).</span><span class="sxs-lookup"><span data-stu-id="06933-251">In a web browser, create a pull request to sync new changes in your fork back to MicrosoftDocs/mixed-reality 'master' (make sure the arrow is pointing the correct way).</span></span>

   ![Een pull-aanvraag maken van uw fork in MicrosoftDocs/mixed-reality](images/pr-to-master.png)

### <a name="useful-extensions"></a><span data-ttu-id="06933-253">Nuttige extensies</span><span class="sxs-lookup"><span data-stu-id="06933-253">Useful extensions</span></span>

<span data-ttu-id="06933-254">De volgende Visual Studio code-extensies zijn nuttig bij het bewerken van documentatie:</span><span class="sxs-lookup"><span data-stu-id="06933-254">The following Visual Studio Code extensions are useful when editing documentation:</span></span>

- <span data-ttu-id="06933-255">[Docs Markdown-extensie voor Visual Studio Code:](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) gebruik **Alt+M** om een menu met ontwerpopties voor documenten weer te geven, zoals:</span><span class="sxs-lookup"><span data-stu-id="06933-255">[Docs Markdown Extension for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) - Use **Alt+M** to bring up a menu of docs authoring options like:</span></span>
   - <span data-ttu-id="06933-256">Zoek en verwijs naar afbeeldingen die u hebt geüpload.</span><span class="sxs-lookup"><span data-stu-id="06933-256">Search and reference images you've uploaded.</span></span>
   - <span data-ttu-id="06933-257">Voeg opmaak toe, zoals lijsten, tabellen en docs-specifieke aanroepen, zoals `>[!NOTE]` .</span><span class="sxs-lookup"><span data-stu-id="06933-257">Add formatting like lists, tables, and docs-specific call-outs like `>[!NOTE]`.</span></span>
   - <span data-ttu-id="06933-258">Interne koppelingen en bladwijzers zoeken en hier naar verwijzen (koppelingen naar specifieke secties binnen een pagina).</span><span class="sxs-lookup"><span data-stu-id="06933-258">Search and reference internal links and bookmarks (links to specific sections within a page).</span></span>
   - <span data-ttu-id="06933-259">Opmaakfouten zijn gemarkeerd (beweeg de muisaanwijzer over de fout voor meer informatie).</span><span class="sxs-lookup"><span data-stu-id="06933-259">Formatting errors are highlighted (hover your mouse over the error to learn more).</span></span>
- <span data-ttu-id="06933-260">[Code Spell Checker:](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) verkeerd gespelde woorden worden onderstreept; klik met de rechtermuisknop op een verkeerd gespeld woord om het te wijzigen of op te slaan in de woordenlijst.</span><span class="sxs-lookup"><span data-stu-id="06933-260">[Code Spell Checker](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) - misspelled words will be underlined; right-click on a misspelled word to change it or save it to the dictionary.</span></span>
