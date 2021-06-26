---
title: De HoloLens 2
description: Meer informatie over het controleren van uw HoloLens-buildnummer, het up-to-date houden van apparaatupdates, het deelnemen aan het Insiders-programma en het terugdraaien van updates.
keywords: how-to, update, roll back, HoloLens, check build, build number
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/27/2019
audience: ITPro
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens 2
ms.openlocfilehash: a27eb1d5eb32a6654f60aac98090cba1aab529d3
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924108"
---
# <a name="update-hololens-2"></a><span data-ttu-id="fe107-104">De HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="fe107-104">Update HoloLens 2</span></span>

<span data-ttu-id="fe107-105">HoloLens gebruikt Windows Update, net als andere Windows 10 apparaten.</span><span class="sxs-lookup"><span data-stu-id="fe107-105">HoloLens uses Windows Update, just like other Windows 10 devices.</span></span> <span data-ttu-id="fe107-106">Uw HoloLens downloadt en installeert automatisch systeemupdates wanneer deze is aangesloten op stroom en is verbonden met internet, zelfs wanneer deze stand-by is.</span><span class="sxs-lookup"><span data-stu-id="fe107-106">Your HoloLens will automatically download and install system updates whenever it is plugged-in to power and connected to the Internet, even when it is in standby.</span></span>

<span data-ttu-id="fe107-107">In dit artikel worden HoloLens-hulpprogramma's voor het volgende beschreven:</span><span class="sxs-lookup"><span data-stu-id="fe107-107">This article will walk through HoloLens tools for:</span></span>

- <span data-ttu-id="fe107-108">uw huidige besturingssysteemversie weergeven (buildnummer)</span><span class="sxs-lookup"><span data-stu-id="fe107-108">viewing your current operating system version (build number)</span></span>
- <span data-ttu-id="fe107-109">controleren op updates</span><span class="sxs-lookup"><span data-stu-id="fe107-109">checking for updates</span></span>
- <span data-ttu-id="fe107-110">HoloLens handmatig bijwerken</span><span class="sxs-lookup"><span data-stu-id="fe107-110">manually updating HoloLens</span></span>
- <span data-ttu-id="fe107-111">terugrollen naar een oudere update</span><span class="sxs-lookup"><span data-stu-id="fe107-111">rolling back to an older update</span></span>

## <a name="check-your-operating-system-version-build-number"></a><span data-ttu-id="fe107-112">Controleer de versie van uw besturingssysteem (buildnummer)</span><span class="sxs-lookup"><span data-stu-id="fe107-112">Check your operating system version (build number)</span></span>

<span data-ttu-id="fe107-113">U kunt het systeemversienummer (buildnummer) controleren door de app Instellingen te openen en **Systeem over te**  >  **selecteren.**</span><span class="sxs-lookup"><span data-stu-id="fe107-113">You can verify the system version number, (build number) by opening the Settings app and selecting **System** > **About**.</span></span>

## <a name="check-for-updates-and-manually-update"></a><span data-ttu-id="fe107-114">Controleren op updates en handmatig bijwerken</span><span class="sxs-lookup"><span data-stu-id="fe107-114">Check for updates and manually update</span></span>

<span data-ttu-id="fe107-115">U kunt op elk moment in de instellingen controleren op updates.</span><span class="sxs-lookup"><span data-stu-id="fe107-115">You can check for updates any time in settings.</span></span>  <span data-ttu-id="fe107-116">Beschikbare updates bekijken en controleren op nieuwe updates:</span><span class="sxs-lookup"><span data-stu-id="fe107-116">To see available updates and check for new updates:</span></span>

1. <span data-ttu-id="fe107-117">Open de app **Instellingen**.</span><span class="sxs-lookup"><span data-stu-id="fe107-117">Open the **Settings** app.</span></span>
1. <span data-ttu-id="fe107-118">Navigeer **naar Update & Security**  >  **Windows Update**.</span><span class="sxs-lookup"><span data-stu-id="fe107-118">Navigate to **Update & Security** > **Windows Update**.</span></span>
1. <span data-ttu-id="fe107-119">Selecteer **Controleren op updates**.</span><span class="sxs-lookup"><span data-stu-id="fe107-119">Select **Check for updates**.</span></span>

<span data-ttu-id="fe107-120">Als er een update beschikbaar is, wordt de nieuwe versie gedownload.</span><span class="sxs-lookup"><span data-stu-id="fe107-120">If an update is available, it will start downloading the new version.</span></span> <span data-ttu-id="fe107-121">Nadat het downloaden is voltooid, selecteert u de knop **Nu** opnieuw opstarten om de installatie te activeren.</span><span class="sxs-lookup"><span data-stu-id="fe107-121">After the download is complete, select the **Restart Now** button to trigger the installation.</span></span> <span data-ttu-id="fe107-122">Als uw apparaat minder dan 40% is en niet is aangesloten, wordt de update niet opnieuw opgestart.</span><span class="sxs-lookup"><span data-stu-id="fe107-122">If your device is below 40% and not plugged in, restarting will not start installing the update.</span></span>

<span data-ttu-id="fe107-123">Terwijl uw HoloLens de update installeert, worden er draaiende tandwielen en een voortgangsindicator weergegeven.</span><span class="sxs-lookup"><span data-stu-id="fe107-123">While your HoloLens is installing the update, it will display spinning gears and a progress indicator.</span></span> <span data-ttu-id="fe107-124">Schakel uw HoloLens gedurende deze periode niet uit.</span><span class="sxs-lookup"><span data-stu-id="fe107-124">Do not turn off your HoloLens during this time.</span></span> <span data-ttu-id="fe107-125">Deze wordt automatisch opnieuw opgestart zodra de installatie is voltooid.</span><span class="sxs-lookup"><span data-stu-id="fe107-125">It will restart automatically once it has completed the installation.</span></span>

<span data-ttu-id="fe107-126">HoloLens past één update per keer toe.</span><span class="sxs-lookup"><span data-stu-id="fe107-126">HoloLens applies one update at a time.</span></span>  <span data-ttu-id="fe107-127">Als uw HoloLens meer dan één versie achter de meest recente versie ligt, moet u het updateproces mogelijk meerdere keren doorlopen om deze volledig up-to-date te krijgen.</span><span class="sxs-lookup"><span data-stu-id="fe107-127">If your HoloLens is more than one version behind the latest you may need to run through the update process multiple times to get it fully up to date.</span></span>

## <a name="go-back-to-a-previous-version"></a><span data-ttu-id="fe107-128">Terug naar een eerdere versie</span><span class="sxs-lookup"><span data-stu-id="fe107-128">Go back to a previous version</span></span>

<span data-ttu-id="fe107-129">In sommige gevallen wilt u misschien teruggaan naar een eerdere versie van de HoloLens-software.</span><span class="sxs-lookup"><span data-stu-id="fe107-129">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="fe107-130">De aanbevolen stappen zijn:</span><span class="sxs-lookup"><span data-stu-id="fe107-130">The recommended steps are:</span></span>

1. <span data-ttu-id="fe107-131">Neem contact op met ondersteuning om te zien of ze uw probleem kunnen oplossen.</span><span class="sxs-lookup"><span data-stu-id="fe107-131">Contact Support to see if they can fix your issue.</span></span>
    1. <span data-ttu-id="fe107-132">Zorg ervoor **dat Optionele** of **Volledige** telemetrie is ingeschakeld. Hierdoor kan uw fout beter worden ondernomen en kunnen technici gemakkelijker een diagnose stellen.</span><span class="sxs-lookup"><span data-stu-id="fe107-132">Ensure that **Optional** or **Full** telemetry is enabled -  this makes your bug more actionable and easier for engineers to diagnose.</span></span>
    1. <span data-ttu-id="fe107-133">[Bestandsfeedback](hololens-feedback.md) is zo beschrijvend mogelijk.</span><span class="sxs-lookup"><span data-stu-id="fe107-133">[File Feedback](hololens-feedback.md) being as descriptive as possible.</span></span> <span data-ttu-id="fe107-134">Noteer de titel of gebruik de functie voor delen, zodat u uw fout kunt delen met ondersteuning.</span><span class="sxs-lookup"><span data-stu-id="fe107-134">Take note of the title or use the share feature so you can share your bug with Support.</span></span>
    1. <span data-ttu-id="fe107-135">Neem contact [op met ondersteuning](https://aka.ms/hlsupport).</span><span class="sxs-lookup"><span data-stu-id="fe107-135">Contact [Support](https://aka.ms/hlsupport).</span></span> <span data-ttu-id="fe107-136">Als uw probleem een probleem is dat moet worden opgelost door terug te keren naar een eerdere versie, kunnen ze u de FFU geven om uw apparaat te laten knipperen.</span><span class="sxs-lookup"><span data-stu-id="fe107-136">If your issue is one that needs to be solved by returning to a previous version, they can supply you the FFU to flash your device.</span></span>

1. <span data-ttu-id="fe107-137">Als dat niet werkt, stelt u uw gegevens opnieuw in of [HoloLens 2 de Advanced Recovery Companion](hololens-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="fe107-137">If that does not work, then [reset or reflash your HoloLens 2 with the Advanced Recovery Companion](hololens-recovery.md).</span></span>
    1. <span data-ttu-id="fe107-138">Download advanced Recovery [Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) op uw pc van de Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="fe107-138">On your PC, download the [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) from the Microsoft Store.</span></span>
    1. <span data-ttu-id="fe107-139">Zorg ervoor dat er geen telefoons of Windows-apparaten op uw pc zijn aangesloten.</span><span class="sxs-lookup"><span data-stu-id="fe107-139">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
    1. <span data-ttu-id="fe107-140">Kies naar welke versie u wilt flashen:</span><span class="sxs-lookup"><span data-stu-id="fe107-140">Choose which version you want to flash to:</span></span>
        1. <span data-ttu-id="fe107-141">U kunt de meest [recente versie HoloLens 2 downloaden.](https://aka.ms/hololens2download)</span><span class="sxs-lookup"><span data-stu-id="fe107-141">You can download the [most recent HoloLens 2 release](https://aka.ms/hololens2download).</span></span>
        1. <span data-ttu-id="fe107-142">U kunt de standaard build gebruiken die ARC-hosts gebruikt.</span><span class="sxs-lookup"><span data-stu-id="fe107-142">You can use the default build that ARC hosts.</span></span> <span data-ttu-id="fe107-143">(Als u deze optie kiest, slaat u de volgende stap over.)</span><span class="sxs-lookup"><span data-stu-id="fe107-143">(If you choose this option skip the next step.)</span></span>
        1. <span data-ttu-id="fe107-144">U kunt een buildondersteuning gebruiken die u hebt geleverd.</span><span class="sxs-lookup"><span data-stu-id="fe107-144">You can use a build Support provided you with.</span></span>
    1. <span data-ttu-id="fe107-145">Wanneer u deze downloads hebt voltooid, opent u **Bestandenverkenner**  >  **Downloads.**</span><span class="sxs-lookup"><span data-stu-id="fe107-145">When you have finished these downloads, open **File Explorer** > **Downloads**.</span></span> <span data-ttu-id="fe107-146">Klik met de rechtermuisknop op de ingepakte map die u zojuist hebt gedownload en selecteer **Alles** uitpakken  >  **om** deze uit tepakken.</span><span class="sxs-lookup"><span data-stu-id="fe107-146">Right-click the zipped folder that you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
    1. <span data-ttu-id="fe107-147">Sluit uw HoloLens aan op uw pc met behulp van een USB-A-naar-USB-C-kabel.</span><span class="sxs-lookup"><span data-stu-id="fe107-147">Connect your HoloLens to your PC using a USB-A to USB-C cable.</span></span> <span data-ttu-id="fe107-148">(Zelfs als u andere kabels hebt gebruikt om uw HoloLens aan te sluiten, werkt deze het beste.)</span><span class="sxs-lookup"><span data-stu-id="fe107-148">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
    1. <span data-ttu-id="fe107-149">De Companion voor geavanceerd herstel detecteert automatisch uw HoloLens.</span><span class="sxs-lookup"><span data-stu-id="fe107-149">The Advanced Recovery Companion automatically detects your HoloLens.</span></span> <span data-ttu-id="fe107-150">Selecteer de **Microsoft HoloLens** tegel.</span><span class="sxs-lookup"><span data-stu-id="fe107-150">Select the **Microsoft HoloLens** tile.</span></span>
    1. <span data-ttu-id="fe107-151">Selecteer in het volgende scherm **Handmatige pakketselectie** en selecteer vervolgens het installatiebestand in de map die u in stap 4 hebt uitgepakt.</span><span class="sxs-lookup"><span data-stu-id="fe107-151">On the next screen, select **Manual package selection** and then select the installation file contained in the folder that you unzipped in step 4.</span></span> <span data-ttu-id="fe107-152">(Zoek naar een bestand met de extensie .ffu.)</span><span class="sxs-lookup"><span data-stu-id="fe107-152">(Look for a file with the .ffu extension.)</span></span>
    1. <span data-ttu-id="fe107-153">Selecteer **Software installeren** en volg de instructies.</span><span class="sxs-lookup"><span data-stu-id="fe107-153">Select **Install software**, and follow the instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="fe107-154">Als u terug gaat naar een eerdere versie, worden uw persoonlijke bestanden en instellingen verwijderd.</span><span class="sxs-lookup"><span data-stu-id="fe107-154">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="fe107-155">Als u de momenteel geïnstalleerde versie wilt blijven, kunt u updates ook [handmatig onderbreken.](hololens-updates.md#pause-updates-via-device)</span><span class="sxs-lookup"><span data-stu-id="fe107-155">Additionally, if you would like to stay on your currently installed release, you can also manually [pause updates](hololens-updates.md#pause-updates-via-device).</span></span> <span data-ttu-id="fe107-156">Dit geeft het technische team tijd om het probleem op te lossen.</span><span class="sxs-lookup"><span data-stu-id="fe107-156">This will give the Engineering Team time to fix the issue.</span></span>

## <a name="windows-insider-program-on-hololens"></a><span data-ttu-id="fe107-157">Windows Insider-programma hololens</span><span class="sxs-lookup"><span data-stu-id="fe107-157">Windows Insider Program on HoloLens</span></span>

<span data-ttu-id="fe107-158">Wilt u de nieuwste functies in HoloLens zien?</span><span class="sxs-lookup"><span data-stu-id="fe107-158">Want to see the latest features in HoloLens?</span></span>  <span data-ttu-id="fe107-159">Als dat het zo is, voegt u Windows Insider-programma; U krijgt toegang tot preview-versies van HoloLens-software-updates voordat deze beschikbaar zijn voor het algemene publiek.</span><span class="sxs-lookup"><span data-stu-id="fe107-159">If so, join the Windows Insider Program; you'll get access to preview builds of HoloLens software updates before they're available to the general public.</span></span>

<span data-ttu-id="fe107-160">[Bekijk Windows Insider preview voor Microsoft HoloLens](hololens-insider.md).</span><span class="sxs-lookup"><span data-stu-id="fe107-160">[Get Windows Insider preview for Microsoft HoloLens](hololens-insider.md).</span></span>
