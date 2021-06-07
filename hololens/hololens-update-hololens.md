---
title: HoloLens bijwerken
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
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ef1721c60aca82d20e60636cbf4301de81c0177c
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/19/2021
ms.locfileid: "111377874"
---
# <a name="update-hololens"></a><span data-ttu-id="30cbe-104">HoloLens bijwerken</span><span class="sxs-lookup"><span data-stu-id="30cbe-104">Update HoloLens</span></span>

<span data-ttu-id="30cbe-105">HoloLens gebruikt Windows Update, net als andere Windows 10 apparaten.</span><span class="sxs-lookup"><span data-stu-id="30cbe-105">HoloLens uses Windows Update, just like other Windows 10 devices.</span></span> <span data-ttu-id="30cbe-106">Uw HoloLens downloadt en installeert automatisch systeemupdates wanneer deze is aangesloten op stroom en is verbonden met internet, zelfs wanneer deze stand-by is.</span><span class="sxs-lookup"><span data-stu-id="30cbe-106">Your HoloLens will automatically download and install system updates whenever it is plugged-in to power and connected to the Internet, even when it is in standby.</span></span>

<span data-ttu-id="30cbe-107">In dit artikel worden HoloLens-hulpprogramma's voor het volgende beschreven:</span><span class="sxs-lookup"><span data-stu-id="30cbe-107">This article will walk through HoloLens tools for:</span></span>

- <span data-ttu-id="30cbe-108">uw huidige besturingssysteemversie weergeven (buildnummer)</span><span class="sxs-lookup"><span data-stu-id="30cbe-108">viewing your current operating system version (build number)</span></span>
- <span data-ttu-id="30cbe-109">controleren op updates</span><span class="sxs-lookup"><span data-stu-id="30cbe-109">checking for updates</span></span>
- <span data-ttu-id="30cbe-110">HoloLens handmatig bijwerken</span><span class="sxs-lookup"><span data-stu-id="30cbe-110">manually updating HoloLens</span></span>
- <span data-ttu-id="30cbe-111">terugrollen naar een oudere update</span><span class="sxs-lookup"><span data-stu-id="30cbe-111">rolling back to an older update</span></span>

## <a name="check-your-operating-system-version-build-number"></a><span data-ttu-id="30cbe-112">Controleer de versie van uw besturingssysteem (buildnummer)</span><span class="sxs-lookup"><span data-stu-id="30cbe-112">Check your operating system version (build number)</span></span>

<span data-ttu-id="30cbe-113">U kunt het systeemversienummer (buildnummer) controleren door de app Instellingen te openen en **Systeem over te**  >  **selecteren.**</span><span class="sxs-lookup"><span data-stu-id="30cbe-113">You can verify the system version number, (build number) by opening the Settings app and selecting **System** > **About**.</span></span>

## <a name="check-for-updates-and-manually-update"></a><span data-ttu-id="30cbe-114">Controleren op updates en handmatig bijwerken</span><span class="sxs-lookup"><span data-stu-id="30cbe-114">Check for updates and manually update</span></span>

<span data-ttu-id="30cbe-115">U kunt op elk moment in de instellingen controleren op updates.</span><span class="sxs-lookup"><span data-stu-id="30cbe-115">You can check for updates any time in settings.</span></span>  <span data-ttu-id="30cbe-116">Beschikbare updates bekijken en controleren op nieuwe updates:</span><span class="sxs-lookup"><span data-stu-id="30cbe-116">To see available updates and check for new updates:</span></span>

1. <span data-ttu-id="30cbe-117">Open de app **Instellingen**.</span><span class="sxs-lookup"><span data-stu-id="30cbe-117">Open the **Settings** app.</span></span>
1. <span data-ttu-id="30cbe-118">Navigeer **naar Update & Security**  >  **Windows Update**.</span><span class="sxs-lookup"><span data-stu-id="30cbe-118">Navigate to **Update & Security** > **Windows Update**.</span></span>
1. <span data-ttu-id="30cbe-119">Selecteer **Controleren op updates**.</span><span class="sxs-lookup"><span data-stu-id="30cbe-119">Select **Check for updates**.</span></span>

<span data-ttu-id="30cbe-120">Als er een update beschikbaar is, wordt de nieuwe versie gedownload.</span><span class="sxs-lookup"><span data-stu-id="30cbe-120">If an update is available, it will start downloading the new version.</span></span> <span data-ttu-id="30cbe-121">Nadat het downloaden is voltooid, selecteert u de knop **Nu** opnieuw opstarten om de installatie te activeren.</span><span class="sxs-lookup"><span data-stu-id="30cbe-121">After the download is complete, select the **Restart Now** button to trigger the installation.</span></span> <span data-ttu-id="30cbe-122">Als uw apparaat lager is dan 40% en niet is aangesloten, wordt de update niet opnieuw opgestart.</span><span class="sxs-lookup"><span data-stu-id="30cbe-122">If your device is below 40% and not plugged in, restarting will not start installing the update.</span></span>

<span data-ttu-id="30cbe-123">Terwijl uw HoloLens de update installeert, worden er draaiende tandwielen en een voortgangsindicator weergegeven.</span><span class="sxs-lookup"><span data-stu-id="30cbe-123">While your HoloLens is installing the update, it will display spinning gears and a progress indicator.</span></span> <span data-ttu-id="30cbe-124">Schakel uw HoloLens gedurende deze periode niet uit.</span><span class="sxs-lookup"><span data-stu-id="30cbe-124">Do not turn off your HoloLens during this time.</span></span> <span data-ttu-id="30cbe-125">Deze wordt automatisch opnieuw opgestart zodra de installatie is voltooid.</span><span class="sxs-lookup"><span data-stu-id="30cbe-125">It will restart automatically once it has completed the installation.</span></span>

<span data-ttu-id="30cbe-126">HoloLens past één update per keer toe.</span><span class="sxs-lookup"><span data-stu-id="30cbe-126">HoloLens applies one update at a time.</span></span>  <span data-ttu-id="30cbe-127">Als uw HoloLens meer dan één versie achter de meest recente versie ligt, moet u het updateproces mogelijk meerdere keren doorlopen om deze volledig up-to-date te krijgen.</span><span class="sxs-lookup"><span data-stu-id="30cbe-127">If your HoloLens is more than one version behind the latest you may need to run through the update process multiple times to get it fully up to date.</span></span>

## <a name="go-back-to-a-previous-version---hololens-2"></a><span data-ttu-id="30cbe-128">Terug naar een eerdere versie - HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="30cbe-128">Go back to a previous version - HoloLens 2</span></span>

<span data-ttu-id="30cbe-129">In sommige gevallen wilt u misschien teruggaan naar een eerdere versie van de HoloLens-software.</span><span class="sxs-lookup"><span data-stu-id="30cbe-129">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="30cbe-130">U kunt dit doen door advanced Recovery Companion te gebruiken om uw HoloLens opnieuw in te stellen op de eerdere versie.</span><span class="sxs-lookup"><span data-stu-id="30cbe-130">You can do this by using the Advanced Recovery Companion to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="30cbe-131">Als u terug gaat naar een eerdere versie, worden uw persoonlijke bestanden en instellingen verwijderd.</span><span class="sxs-lookup"><span data-stu-id="30cbe-131">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="30cbe-132">Als u wilt teruggaan naar een eerdere versie van HoloLens 2, volgt u deze stappen:</span><span class="sxs-lookup"><span data-stu-id="30cbe-132">To go back to a previous version of HoloLens 2, follow these steps:</span></span>

1. <span data-ttu-id="30cbe-133">Zorg ervoor dat er geen telefoons of Windows-apparaten op uw pc zijn aangesloten.</span><span class="sxs-lookup"><span data-stu-id="30cbe-133">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
1. <span data-ttu-id="30cbe-134">Download advanced Recovery [Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) op uw pc van de Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="30cbe-134">On your PC, download the [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) from the Microsoft Store.</span></span>
1. <span data-ttu-id="30cbe-135">Download de [meest recente HoloLens 2 release](https://aka.ms/hololens2download).</span><span class="sxs-lookup"><span data-stu-id="30cbe-135">Download the [most recent HoloLens 2 release](https://aka.ms/hololens2download).</span></span>
1. <span data-ttu-id="30cbe-136">Wanneer u klaar bent met downloaden, opent u **Bestandenverkenner**  >  **Downloads.**</span><span class="sxs-lookup"><span data-stu-id="30cbe-136">When you have finished these downloads, open **File explorer** > **Downloads**.</span></span> <span data-ttu-id="30cbe-137">Klik met de rechtermuisknop op de ingepakte map die u zojuist hebt gedownload en selecteer **Alles uitpakken**  >  **om** deze uit tepakken.</span><span class="sxs-lookup"><span data-stu-id="30cbe-137">Right-click the zipped folder that you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="30cbe-138">Sluit uw HoloLens aan op uw pc met behulp van een USB-A-naar-USB-C-kabel.</span><span class="sxs-lookup"><span data-stu-id="30cbe-138">Connect your HoloLens to your PC using a USB-A to USB-C cable.</span></span> <span data-ttu-id="30cbe-139">(Zelfs als u andere kabels hebt gebruikt om uw HoloLens aan te sluiten, werkt deze het beste.)</span><span class="sxs-lookup"><span data-stu-id="30cbe-139">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="30cbe-140">De Companion voor geavanceerd herstel detecteert automatisch uw HoloLens.</span><span class="sxs-lookup"><span data-stu-id="30cbe-140">The Advanced Recovery Companion automatically detects your HoloLens.</span></span> <span data-ttu-id="30cbe-141">Selecteer de **Microsoft HoloLens** tegel.</span><span class="sxs-lookup"><span data-stu-id="30cbe-141">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="30cbe-142">Selecteer in het volgende scherm **Handmatige pakketselectie** en selecteer vervolgens het installatiebestand in de map die u in stap 4 hebt uitgepakt.</span><span class="sxs-lookup"><span data-stu-id="30cbe-142">On the next screen, select **Manual package selection** and then select the installation file contained in the folder that you unzipped in step 4.</span></span> <span data-ttu-id="30cbe-143">(Zoek naar een bestand met de extensie .ffu.)</span><span class="sxs-lookup"><span data-stu-id="30cbe-143">(Look for a file with the .ffu extension.)</span></span>
1. <span data-ttu-id="30cbe-144">Selecteer **Software installeren** en volg de instructies.</span><span class="sxs-lookup"><span data-stu-id="30cbe-144">Select **Install software**, and follow the instructions.</span></span>

## <a name="go-back-to-a-previous-version---hololens-1st-gen"></a><span data-ttu-id="30cbe-145">Terug naar een eerdere versie - HoloLens (1e generatie)</span><span class="sxs-lookup"><span data-stu-id="30cbe-145">Go back to a previous version - HoloLens (1st Gen)</span></span>

<span data-ttu-id="30cbe-146">In sommige gevallen wilt u misschien teruggaan naar een eerdere versie van de HoloLens-software.</span><span class="sxs-lookup"><span data-stu-id="30cbe-146">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="30cbe-147">U kunt dit doen door het Hulpprogramma voor herstel van Windows-apparaten te gebruiken om uw HoloLens opnieuw in te stellen op de eerdere versie.</span><span class="sxs-lookup"><span data-stu-id="30cbe-147">You can do this by using the Windows Device Recovery Tool to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="30cbe-148">Als u terug gaat naar een eerdere versie, worden uw persoonlijke bestanden en instellingen verwijderd.</span><span class="sxs-lookup"><span data-stu-id="30cbe-148">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="30cbe-149">Als u wilt teruggaan naar een eerdere versie van HoloLens 1, volgt u deze stappen:</span><span class="sxs-lookup"><span data-stu-id="30cbe-149">To go back to a previous version of HoloLens 1, follow these steps:</span></span>

1. <span data-ttu-id="30cbe-150">Zorg ervoor dat er geen telefoons of Windows-apparaten op uw pc zijn aangesloten.</span><span class="sxs-lookup"><span data-stu-id="30cbe-150">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
1. <span data-ttu-id="30cbe-151">Download windows Device [Recovery Tool (WDRT)](https://support.microsoft.com/help/12379)op uw pc.</span><span class="sxs-lookup"><span data-stu-id="30cbe-151">On your PC, download the [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span></span>
1. <span data-ttu-id="30cbe-152">Download het [herstelpakket voor HoloLens Jubileumupdate.](https://aka.ms/hololensrecovery)</span><span class="sxs-lookup"><span data-stu-id="30cbe-152">Download the [HoloLens Anniversary Update recovery package](https://aka.ms/hololensrecovery).</span></span>
1. <span data-ttu-id="30cbe-153">Wanneer de downloads zijn gedownload, opent u   >  **Bestandenverkenner Downloads.**</span><span class="sxs-lookup"><span data-stu-id="30cbe-153">When the downloads finish, open **File explorer** > **Downloads**.</span></span> <span data-ttu-id="30cbe-154">Klik met de rechtermuisknop op de ingepakte map die u zojuist hebt gedownload en selecteer **Alles** uitpakken  >  **om** deze uit tepakken.</span><span class="sxs-lookup"><span data-stu-id="30cbe-154">Right-click the zipped folder you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="30cbe-155">Sluit uw HoloLens aan op uw pc met behulp van de micro-USB-kabel die bij deze kabel is meegeleverd.</span><span class="sxs-lookup"><span data-stu-id="30cbe-155">Connect your HoloLens to your PC using the micro-USB cable that it came with.</span></span> <span data-ttu-id="30cbe-156">(Zelfs als u andere kabels hebt gebruikt om uw HoloLens aan te sluiten, werkt deze het beste.)</span><span class="sxs-lookup"><span data-stu-id="30cbe-156">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="30cbe-157">De WDRT detecteert automatisch uw HoloLens.</span><span class="sxs-lookup"><span data-stu-id="30cbe-157">The WDRT will automatically detect your HoloLens.</span></span> <span data-ttu-id="30cbe-158">Selecteer de **Microsoft HoloLens** tegel.</span><span class="sxs-lookup"><span data-stu-id="30cbe-158">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="30cbe-159">Selecteer in het volgende scherm **Handmatige pakketselectie** en kies het installatiebestand in de map die u in stap 4 hebt uitgepakt.</span><span class="sxs-lookup"><span data-stu-id="30cbe-159">On the next screen, select **Manual package selection** and choose the installation file contained in the folder you unzipped in step 4.</span></span> <span data-ttu-id="30cbe-160">(Zoek naar een bestand met de extensie .ffu.)</span><span class="sxs-lookup"><span data-stu-id="30cbe-160">(Look for a file with the .ffu extension.)</span></span>
1. <span data-ttu-id="30cbe-161">Selecteer **Software installeren** en volg de instructies.</span><span class="sxs-lookup"><span data-stu-id="30cbe-161">Select **Install software**, and follow the instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="30cbe-162">Als de WDRT uw HoloLens niet detecteert, start u de pc opnieuw op.</span><span class="sxs-lookup"><span data-stu-id="30cbe-162">If the WDRT doesn't detect your HoloLens, try restarting your PC.</span></span> <span data-ttu-id="30cbe-163">Als dat niet werkt, selecteert u Mijn apparaat is niet **gedetecteerd,** selecteert u **Microsoft HoloLens** en volgt u de instructies.</span><span class="sxs-lookup"><span data-stu-id="30cbe-163">If that doesn't work, select **My device was not detected**, select **Microsoft HoloLens**, and then follow the instructions.</span></span>

## <a name="windows-insider-program-on-hololens"></a><span data-ttu-id="30cbe-164">Windows Insider-programma hololens</span><span class="sxs-lookup"><span data-stu-id="30cbe-164">Windows Insider Program on HoloLens</span></span>

<span data-ttu-id="30cbe-165">Wilt u de nieuwste functies in HoloLens zien?</span><span class="sxs-lookup"><span data-stu-id="30cbe-165">Want to see the latest features in HoloLens?</span></span>  <span data-ttu-id="30cbe-166">Als dat het zo is, voegt u Windows Insider-programma; U krijgt toegang tot preview-versies van HoloLens-software-updates voordat deze beschikbaar zijn voor het algemene publiek.</span><span class="sxs-lookup"><span data-stu-id="30cbe-166">If so, join the Windows Insider Program; you'll get access to preview builds of HoloLens software updates before they're available to the general public.</span></span>

<span data-ttu-id="30cbe-167">[Bekijk Windows Insider preview voor Microsoft HoloLens](hololens-insider.md).</span><span class="sxs-lookup"><span data-stu-id="30cbe-167">[Get Windows Insider preview for Microsoft HoloLens](hololens-insider.md).</span></span>
