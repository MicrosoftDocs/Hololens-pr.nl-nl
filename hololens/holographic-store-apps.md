---
title: Toepassingen zoeken, installeren en verwijderen
description: De Microsoft Store is uw bron voor apps en games die werken met HoloLens.  Meer informatie over het zoeken, installeren en verwijderen van holografische apps.
ms.assetid: cbe9aa3a-884f-4a92-bf54-8d4917bc3435
ms.reviewer: v-miegge
ms.date: 10/27/2020
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
ms.openlocfilehash: bbbc60decb74942bd7930afb04297f78df33028a
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635854"
---
# <a name="find-install-and-uninstall-applications-from-the-microsoft-store"></a><span data-ttu-id="ec6eb-105">Toepassingen zoeken, installeren en verwijderen uit de Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="ec6eb-105">Find, install, and uninstall applications from the Microsoft Store</span></span>

<span data-ttu-id="ec6eb-106">De Microsoft Store is uw go-to-bron voor apps en games die werken met HoloLens.</span><span class="sxs-lookup"><span data-stu-id="ec6eb-106">The Microsoft Store is your go-to source for apps and games that work with HoloLens.</span></span> <span data-ttu-id="ec6eb-107">Wanneer u naar de Store op uw HoloLens, worden alle apps die u ziet, op de app uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="ec6eb-107">When you go to the Store on your HoloLens, any apps you see there will run on it.</span></span>

<span data-ttu-id="ec6eb-108">Apps op HoloLens een 2D-weergave of een holografische weergave.</span><span class="sxs-lookup"><span data-stu-id="ec6eb-108">Apps on HoloLens use either 2D view or holographic view.</span></span> <span data-ttu-id="ec6eb-109">Apps die gebruikmaken van een 2D-weergave, zien eruit als vensters en kunnen overal om u heen worden geplaatst.</span><span class="sxs-lookup"><span data-stu-id="ec6eb-109">Apps that use 2D view look like windows and can be positioned all around you.</span></span> <span data-ttu-id="ec6eb-110">Apps die gebruikmaken van een holografische weergave, omringen u en worden de enige app die u ziet.</span><span class="sxs-lookup"><span data-stu-id="ec6eb-110">Apps that use holographic view surround you and become the only app you see.</span></span>

<span data-ttu-id="ec6eb-111">HoloLens biedt ondersteuning voor veel bestaande toepassingen van de Microsoft Store en nieuwe apps die specifiek zijn gebouwd voor HoloLens.</span><span class="sxs-lookup"><span data-stu-id="ec6eb-111">HoloLens supports many existing applications from the Microsoft Store, and new apps built specifically for HoloLens.</span></span>  <span data-ttu-id="ec6eb-112">Dit artikel is gericht op holografische toepassingen van de Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="ec6eb-112">This article focuses on holographic applications from the Microsoft Store.</span></span>

<span data-ttu-id="ec6eb-113">Lees Aangepaste holographic-toepassingen voor meer informatie over het installeren en uitvoeren [van aangepaste apps.](holographic-custom-apps.md)</span><span class="sxs-lookup"><span data-stu-id="ec6eb-113">To learn more about installing and running custom apps, read [Custom holographic applications](holographic-custom-apps.md).</span></span>

## <a name="find-apps"></a><span data-ttu-id="ec6eb-114">Apps zoeken</span><span class="sxs-lookup"><span data-stu-id="ec6eb-114">Find apps</span></span>

<span data-ttu-id="ec6eb-115">Open de Microsoft Store in **het** menu Start.</span><span class="sxs-lookup"><span data-stu-id="ec6eb-115">Open the Microsoft Store from the **Start** menu.</span></span> <span data-ttu-id="ec6eb-116">Blader vervolgens naar apps en games.</span><span class="sxs-lookup"><span data-stu-id="ec6eb-116">Then browse for apps and games.</span></span> <span data-ttu-id="ec6eb-117">U kunt [spraakopdrachten](hololens-cortana.md) gebruiken om te zoeken door 'Zoeken' te zeggen. Zodra het zoekvenster wordt geopend, wordt 'Beginnen met dicteren' weergegeven en wanneer u hier om wordt gevraagd, begint u met het zeggen van uw zoektermen.</span><span class="sxs-lookup"><span data-stu-id="ec6eb-117">You can use [voice commands](hololens-cortana.md) to search by saying "Search", once the search window opens say "Start dictating" and then when prompted begin saying your search terms.</span></span>

> [!NOTE]
> <span data-ttu-id="ec6eb-118">De systeemvereisten voor HoloLens zijn gebaseerd op de architectuur van de app-build.</span><span class="sxs-lookup"><span data-stu-id="ec6eb-118">The System Requirements for HoloLens devices are based on the architecture of the app build.</span></span> <span data-ttu-id="ec6eb-119">Als een app-build voor HoloLens (eerste generatie) niet is bijgewerkt met naar een nieuwere UWP in de store om het ARM-architectuurpakket op te nemen, is het niet beschikbaar voor HoloLens 2-apparaten.</span><span class="sxs-lookup"><span data-stu-id="ec6eb-119">If an app build for HoloLens (1st gen) has not been updated with to a newer UWP in the store to include the ARM architecture package, then it will not be available for HoloLens 2 devices.</span></span> <span data-ttu-id="ec6eb-120">En als een HoloLens 2-app niet het x86-architectuurpakket bevat, is deze niet beschikbaar voor HoloLens (1e generatie).</span><span class="sxs-lookup"><span data-stu-id="ec6eb-120">Likewise, if a HoloLens 2 app does not include the x86 architecture package, it will not be available for HoloLens (1st gen) devices.</span></span> <span data-ttu-id="ec6eb-121">HoloLens van apparaten:</span><span class="sxs-lookup"><span data-stu-id="ec6eb-121">HoloLens device architectures:</span></span>
> - <span data-ttu-id="ec6eb-122">x86 = HoloLens (1e generatie)</span><span class="sxs-lookup"><span data-stu-id="ec6eb-122">x86 = HoloLens (1st gen)</span></span>
> - <span data-ttu-id="ec6eb-123">ARM = HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="ec6eb-123">ARM = HoloLens 2</span></span>

> [!NOTE]
> <span data-ttu-id="ec6eb-124">Op 12 januari 2021 bereiken de volgende apps Einde van ondersteuning op HoloLens apparaten.</span><span class="sxs-lookup"><span data-stu-id="ec6eb-124">On January 12, 2021 the following apps will reach End of Support on HoloLens devices.</span></span> <span data-ttu-id="ec6eb-125">We raden u aan de volgende koppeling op uw apparaat te gebruiken om de webversie van de app te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="ec6eb-125">We encourage you to use the following link on your device to use the web version of the app.</span></span>

| <span data-ttu-id="ec6eb-126">App</span><span class="sxs-lookup"><span data-stu-id="ec6eb-126">App</span></span>        | <span data-ttu-id="ec6eb-127">Koppeling</span><span class="sxs-lookup"><span data-stu-id="ec6eb-127">Link</span></span>                                          |
|------------|-----------------------------------------------|
| <span data-ttu-id="ec6eb-128">Excel mobiel</span><span class="sxs-lookup"><span data-stu-id="ec6eb-128">Excel mobile</span></span>      | https://office.live.com/start/Excel.aspx      |
| <span data-ttu-id="ec6eb-129">Word Mobile</span><span class="sxs-lookup"><span data-stu-id="ec6eb-129">Word mobile</span></span>       | https://office.live.com/start/Word.aspx       |
| <span data-ttu-id="ec6eb-130">PowerPoint mobiel</span><span class="sxs-lookup"><span data-stu-id="ec6eb-130">PowerPoint mobile</span></span> | https://office.live.com/start/PowerPoint.aspx |

## <a name="install-apps"></a><span data-ttu-id="ec6eb-131">Apps installeren</span><span class="sxs-lookup"><span data-stu-id="ec6eb-131">Install apps</span></span>

<span data-ttu-id="ec6eb-132">Als u apps wilt downloaden, moet u zijn aangemeld met een Microsoft-account.</span><span class="sxs-lookup"><span data-stu-id="ec6eb-132">To download apps, you'll need to be signed in with a Microsoft account.</span></span> <span data-ttu-id="ec6eb-133">Sommige apps zijn gratis en kunnen direct worden gedownload.</span><span class="sxs-lookup"><span data-stu-id="ec6eb-133">Some apps are free and can be downloaded right away.</span></span> <span data-ttu-id="ec6eb-134">Voor apps waarvoor een aankoop is vereist, moet u zijn aangemeld bij de Store met uw Microsoft-account een geldige betalingswijze hebben.</span><span class="sxs-lookup"><span data-stu-id="ec6eb-134">For apps that require a purchase, you must be signed in to the Store with your Microsoft account and have a valid payment method.</span></span>

> [!NOTE]
> <span data-ttu-id="ec6eb-135">Het account dat u gebruikt Microsoft Store hoeft niet hetzelfde te zijn als het account bij wie u bent aangemeld.</span><span class="sxs-lookup"><span data-stu-id="ec6eb-135">The account you use on Microsoft Store does not have to be the same as the account you are signed in with.</span></span> <span data-ttu-id="ec6eb-136">Als u een werk- of schoolaccount op uw HoloLens moet u zich mogelijk aanmelden met uw persoonlijke account in de Store-app om een aankoop te doen.</span><span class="sxs-lookup"><span data-stu-id="ec6eb-136">If you are using a Work or School account on your HoloLens then you may need to sign in with your personal account in the Store App to make a purchase.</span></span>

> [!TIP]
> <span data-ttu-id="ec6eb-137">Als u een betalingswijze wilt instellen, gaat u [naar account.microsoft.com](https://account.microsoft.com/) selecteert u **Betalingswijze**& betalingsopties Betalingsopties  >    >  **toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="ec6eb-137">To set up a payment method, go to [account.microsoft.com](https://account.microsoft.com/) and select **Payment & billing** > **Payment options** > **Add a payment option**.</span></span>

1. <span data-ttu-id="ec6eb-138">Als u het [ **menu Start** wilt openen,](holographic-home.md)voert u een [startbewegingen](/hololens/hololens2-basic-usage#start-gesture) of [een bloeibewegingen](hololens1-basic-usage.md) uit op HoloLens (1e generatie).</span><span class="sxs-lookup"><span data-stu-id="ec6eb-138">To open the [**Start** menu](holographic-home.md), perform a [Start gesture](/hololens/hololens2-basic-usage#start-gesture) or [bloom](hololens1-basic-usage.md) gesture on HoloLens (1st gen).</span></span>

1. <span data-ttu-id="ec6eb-139">Selecteer de Microsoft Store app.</span><span class="sxs-lookup"><span data-stu-id="ec6eb-139">Select the Microsoft Store app.</span></span> <span data-ttu-id="ec6eb-140">Nadat de Store-app is geopend:</span><span class="sxs-lookup"><span data-stu-id="ec6eb-140">After the Store app opens:</span></span>
   1. <span data-ttu-id="ec6eb-141">Gebruik de zoekbalk om te zoeken naar toepassingen.</span><span class="sxs-lookup"><span data-stu-id="ec6eb-141">Use the search bar to look for applications.</span></span> 
   1. <span data-ttu-id="ec6eb-142">Selecteer essentiële apps of apps die specifiek zijn gemaakt HoloLens uit een van de gecureerde categorieën.</span><span class="sxs-lookup"><span data-stu-id="ec6eb-142">Select essential apps or apps made specifically for HoloLens from one of the curated categories.</span></span>
   1. <span data-ttu-id="ec6eb-143">Selecteer rechtsboven in de Store-app de knop **'...'** en selecteer vervolgens **Mijn** bibliotheek om eerder gekochte apps weer te geven.</span><span class="sxs-lookup"><span data-stu-id="ec6eb-143">On the top right of the Store app, select the **"..."** button and then select **My Library** to view any previously purchased apps.</span></span>

1. <span data-ttu-id="ec6eb-144">Selecteer **Downloaden** of **installeren** op de pagina van de toepassing (mogelijk is een aankoop vereist).</span><span class="sxs-lookup"><span data-stu-id="ec6eb-144">Select **Get** or **Install** on the application's page (a purchase may be required).</span></span>

## <a name="update-apps"></a><span data-ttu-id="ec6eb-145">Apps bijwerken</span><span class="sxs-lookup"><span data-stu-id="ec6eb-145">Update Apps</span></span>

<span data-ttu-id="ec6eb-146">Als u een app wilt bijwerken die u hebt geïnstalleerd vanuit Microsoft Store, kunt u de app bijwerken vanuit de Microsoft Store app.</span><span class="sxs-lookup"><span data-stu-id="ec6eb-146">To update an app you installed from the Microsoft Store, you can update the app from the Microsoft Store app.</span></span> <span data-ttu-id="ec6eb-147">Voor apps die voor de Microsoft Store voor Bedrijven zijn geïnstalleerd, kunt u deze apps ook bijwerken vanuit de Microsoft Store voor Bedrijven.</span><span class="sxs-lookup"><span data-stu-id="ec6eb-147">For apps installed for the Microsoft Store for Business, you can also update those apps from the Microsoft Store for Business.</span></span> 

1. <span data-ttu-id="ec6eb-148">Als u het [ **menu Start** wilt openen,](holographic-home.md)voert u een [startbewegingen](/hololens/hololens2-basic-usage#start-gesture) of [een bloeibewegingen](hololens1-basic-usage.md) uit op HoloLens (1e generatie).</span><span class="sxs-lookup"><span data-stu-id="ec6eb-148">To open the [**Start** menu](holographic-home.md), perform a [Start gesture](/hololens/hololens2-basic-usage#start-gesture) or [bloom](hololens1-basic-usage.md) gesture on HoloLens (1st gen).</span></span>

1. <span data-ttu-id="ec6eb-149">Selecteer de Store-app.</span><span class="sxs-lookup"><span data-stu-id="ec6eb-149">Select the Store app.</span></span>

1. <span data-ttu-id="ec6eb-150">Kijk rechtsboven in de Store-app.</span><span class="sxs-lookup"><span data-stu-id="ec6eb-150">Look to the top right of the Store app.</span></span> 

1. <span data-ttu-id="ec6eb-151">Selecteer de **knop '...'** of 'Meer weergeven'.</span><span class="sxs-lookup"><span data-stu-id="ec6eb-151">Select the **"..."** or “See more” button.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ec6eb-152">![Microsoft Store app-schermopname.](images/store-update-1.png)</span><span class="sxs-lookup"><span data-stu-id="ec6eb-152">![Microsoft Store app screenshot.](images/store-update-1.png)</span></span>

1. <span data-ttu-id="ec6eb-153">Selecteer **Downloads en updates.**</span><span class="sxs-lookup"><span data-stu-id="ec6eb-153">Select **Downloads and updates**.</span></span>
    1. <span data-ttu-id="ec6eb-154">Als uw apparaat eerder updates heeft geïdentificeerd, is er mogelijk een pijl-omlaag en een getal dat staat voor updates die in behandeling zijn.</span><span class="sxs-lookup"><span data-stu-id="ec6eb-154">If your device has previously identified updates, there may be a down arrow and a number that represents pending updates.</span></span>

1. <span data-ttu-id="ec6eb-155">Selecteer **Updates downloaden.**</span><span class="sxs-lookup"><span data-stu-id="ec6eb-155">Select **Get updates**.</span></span> <span data-ttu-id="ec6eb-156">Uw apparaat zoekt nu naar updates en stelt deze in op downloaden en installeren.</span><span class="sxs-lookup"><span data-stu-id="ec6eb-156">Your device will now search for updates and set them to download and install.</span></span> 
 
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ec6eb-157">![Microsoft Store app-schermopname van het ontvangen van updates.](images/store-update-2.png.jpg)</span><span class="sxs-lookup"><span data-stu-id="ec6eb-157">![Microsoft Store app screenshot of getting updates..](images/store-update-2.png.jpg)</span></span>

> [!NOTE]
> <span data-ttu-id="ec6eb-158">Als de apps op uw apparaat door uw organisatie zijn gedistribueerd, kunnen ze worden bijgewerkt via dezelfde commerciële app-beheermethoden.</span><span class="sxs-lookup"><span data-stu-id="ec6eb-158">If the apps on your device were distributed by your organization they can be updated through the same commercial app management methods.</span></span> <span data-ttu-id="ec6eb-159">Als dit van toepassing is op uw situatie, leest u meer via ons overzicht van de implementatie [van commerciële apps.](app-deploy-overview.md)</span><span class="sxs-lookup"><span data-stu-id="ec6eb-159">If this applies to your situation, read more via our [overview of commercial app deployment.](app-deploy-overview.md)</span></span>
>
> <span data-ttu-id="ec6eb-160">Als u een aangepaste app wilt bijwerken die sideloaden of geïmplementeerd is, moet u dezelfde methode gebruiken met de bijgewerkte versie van uw app.</span><span class="sxs-lookup"><span data-stu-id="ec6eb-160">If you would like to update a custom app that has been sideloaded or deployed, you will need to use the same method with the updated version of your app.</span></span> <span data-ttu-id="ec6eb-161">Lees Aangepaste holographic-toepassingen voor meer informatie over het installeren en uitvoeren [van aangepaste apps.](holographic-custom-apps.md)</span><span class="sxs-lookup"><span data-stu-id="ec6eb-161">To learn more about installing and running custom apps, read [custom holographic applications](holographic-custom-apps.md).</span></span>

## <a name="uninstall-apps"></a><span data-ttu-id="ec6eb-162">Apps verwijderen</span><span class="sxs-lookup"><span data-stu-id="ec6eb-162">Uninstall apps</span></span>

<span data-ttu-id="ec6eb-163">Er zijn drie manieren om toepassingen te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="ec6eb-163">There are three ways to uninstall applications.</span></span> <span data-ttu-id="ec6eb-164">U kunt toepassingen verwijderen via de Microsoft Store, Startmenu of Instellingen.</span><span class="sxs-lookup"><span data-stu-id="ec6eb-164">You can uninstall applications through the Microsoft Store, Start menu or from Settings.</span></span> 

> [!WARNING]
> <span data-ttu-id="ec6eb-165">U kunt een systeem-app of de Microsoft Store verwijderen.</span><span class="sxs-lookup"><span data-stu-id="ec6eb-165">You can not uninstall a system app or the Microsoft Store itself.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ec6eb-166">Als uw HoloLens 2 meerdere gebruikers heeft, moet u zijn aangemeld als de gebruiker die de app heeft geïnstalleerd om deze te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="ec6eb-166">If your HoloLens 2 has multiple users, you must be logged in as the user who installed the app to uninstall it.</span></span> 

### <a name="uninstall-from-the-microsoft-store"></a><span data-ttu-id="ec6eb-167">Verwijderen van de Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="ec6eb-167">Uninstall from the Microsoft Store</span></span>

<span data-ttu-id="ec6eb-168">Open de Microsoft Store in het menu **Start** en blader naar de toepassing die u wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="ec6eb-168">Open the Microsoft Store from the **Start** menu, and then browse for the application you want to uninstall.</span></span>  <span data-ttu-id="ec6eb-169">Op de pagina Store heeft elke geïnstalleerde toepassing een **knop Verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="ec6eb-169">On the Store page, each installed application has an **Uninstall** button.</span></span>

### <a name="uninstall-from-the-start-menu"></a><span data-ttu-id="ec6eb-170">Verwijderen van de Startmenu</span><span class="sxs-lookup"><span data-stu-id="ec6eb-170">Uninstall from the Start menu</span></span>

<span data-ttu-id="ec6eb-171">Blader in **het** menu Start of in **Alle apps** lijst naar de app.</span><span class="sxs-lookup"><span data-stu-id="ec6eb-171">On the **Start** menu or in the **All apps** list, browse to the app.</span></span> <span data-ttu-id="ec6eb-172">Selecteer en houd in de wacht totdat het menu wordt weergegeven. Selecteer **vervolgens Verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="ec6eb-172">Select and hold until the menu appears, then select **Uninstall**.</span></span>

### <a name="uninstall-from-settings"></a><span data-ttu-id="ec6eb-173">Verwijderen uit Instellingen</span><span class="sxs-lookup"><span data-stu-id="ec6eb-173">Uninstall from Settings</span></span>
<span data-ttu-id="ec6eb-174">Selecteer in **het** menu Start **de optie Instellingen -> Apps.**</span><span class="sxs-lookup"><span data-stu-id="ec6eb-174">On the **Start** menu, select **Settings -> Apps.**</span></span> <span data-ttu-id="ec6eb-175">Zoek de app in de lijst, selecteer deze en klik vervolgens **op Verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="ec6eb-175">Find the app from the list, select it and then click **Uninstall**.</span></span>

<span data-ttu-id="ec6eb-176">Als u een app niet kunt verwijderen, kunt u [feedback verzenden](/hololens/hololens-feedback) met behulp van de Feedback-hub.</span><span class="sxs-lookup"><span data-stu-id="ec6eb-176">If you are unable to uninstall an app, please file [feedback](/hololens/hololens-feedback) using the Feedback Hub.</span></span>
