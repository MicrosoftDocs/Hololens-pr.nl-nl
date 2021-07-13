---
title: Opnieuw opstarten, opnieuw instellen of herstellen HoloLens 1
ms.reviewer: Keep up to date on the basic and advanced instructions for rebooting or resetting your HoloLens mixed reality device.
description: Het gebruik van Windows Device Recovery Tool om een afbeelding te flashen naar HoloLens 1st Gen.
keywords: how-to, reboot, reset, recover, hard reset, soft reset, power cycle, HoloLens, shut down, wdrt, windows device recovery tool
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.date: 06/01/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: medium
manager: yannisle
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 4840535030cc81f222cb25357474f1c751426e91
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635225"
---
# <a name="restart-reset-or-recover-hololens-1st-gen"></a><span data-ttu-id="b5fb0-104">Opnieuw opstarten, opnieuw instellen of HoloLens herstellen (1st Gen)</span><span class="sxs-lookup"><span data-stu-id="b5fb0-104">Restart, reset, or recover HoloLens (1st Gen)</span></span>

<span data-ttu-id="b5fb0-105">Als u problemen ondervindt met uw HoloLens, kunt u proberen het apparaat opnieuw op te starten of opnieuw in te stellen of zelfs een reflash op het apparaat uit te voeren met behulp van apparaatherstel.</span><span class="sxs-lookup"><span data-stu-id="b5fb0-105">If you're experiencing problems with your HoloLens, you may want to try a restart or reset, or even reflash the device by using device recovery.</span></span> <span data-ttu-id="b5fb0-106">Dit artikel begeleidt u door de aanbevolen herstelstappen in de volgorde.</span><span class="sxs-lookup"><span data-stu-id="b5fb0-106">This article guides you through the recommended recovery steps in order.</span></span>

<span data-ttu-id="b5fb0-107">Als u een herstelproces wilt HoloLens 2, zie [Een](hololens-recovery.md)HoloLens 2 herstellen, aangezien dat proces anders is.</span><span class="sxs-lookup"><span data-stu-id="b5fb0-107">If you're looking to recover a HoloLens 2, see [Recovering a HoloLens 2](hololens-recovery.md), as that process differs.</span></span>

> [!NOTE]
> <span data-ttu-id="b5fb0-108">Dit artikel richt zich op de HoloLens en software.</span><span class="sxs-lookup"><span data-stu-id="b5fb0-108">This article focuses on the HoloLens device and software.</span></span> <span data-ttu-id="b5fb0-109">Als uw hologrammen er niet goed uitzien, bekijkt u HoloLens **[omgevingsoverwegingen](hololens-environment-considerations.md)** voor informatie over factoren die de kwaliteit van hologrammen verbeteren.</span><span class="sxs-lookup"><span data-stu-id="b5fb0-109">If your holograms don't look right, see **[HoloLens environment considerations](hololens-environment-considerations.md)** for information about factors that improve hologram quality.</span></span>

## <a name="restart"></a><span data-ttu-id="b5fb0-110">Opnieuw starten</span><span class="sxs-lookup"><span data-stu-id="b5fb0-110">Restart</span></span>

### <a name="do-a-safe-restart-by-using-cortana"></a><span data-ttu-id="b5fb0-111">Veilig opnieuw opstarten met behulp van Cortana</span><span class="sxs-lookup"><span data-stu-id="b5fb0-111">Do a safe restart by using Cortana</span></span>

<span data-ttu-id="b5fb0-112">De veiligste manier om de HoloLens opnieuw op te starten, is door Cortana te gebruiken. Dit is meestal het eerste wat u moet proberen wanneer u een probleem met HoloLens.</span><span class="sxs-lookup"><span data-stu-id="b5fb0-112">The safest way to restart the HoloLens is by using Cortana, which is generally the first thing to try when you experience an issue with HoloLens.</span></span>

> [!NOTE] 
> <span data-ttu-id="b5fb0-113">Cortana is niet op alle apparaten beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="b5fb0-113">Cortana is not available on all devices.</span></span>
> - <span data-ttu-id="b5fb0-114">Cortana is beschikbaar op alle HoloLens (1st Gen)-apparaten.</span><span class="sxs-lookup"><span data-stu-id="b5fb0-114">Cortana is available on all HoloLens (1st Gen) devices.</span></span> 
> - <span data-ttu-id="b5fb0-115">Cortana is beschikbaar op HoloLens 2-apparaten op builds vóór de Windows Holograpic-update van versie 2004.</span><span class="sxs-lookup"><span data-stu-id="b5fb0-115">Cortana is available on HoloLens 2 devices on builds prior to the Windows Holograpic, Version 2004 update.</span></span>

1. <span data-ttu-id="b5fb0-116">Schakel uw HoloLens.</span><span class="sxs-lookup"><span data-stu-id="b5fb0-116">Turn on your HoloLens.</span></span>
1. <span data-ttu-id="b5fb0-117">Zorg ervoor dat een gebruiker is aangemeld en dat het apparaat niet wacht op een wachtwoord om het te ontgrendelen.</span><span class="sxs-lookup"><span data-stu-id="b5fb0-117">Make sure that a user is logged in and the device isn't waiting for a password to unlock it.</span></span>
2. <span data-ttu-id="b5fb0-118">Zeg 'Hey Cortana, reboot' of 'Hey Cortana, restart'.</span><span class="sxs-lookup"><span data-stu-id="b5fb0-118">Say "Hey Cortana, reboot" or "Hey Cortana, restart."</span></span>
3. <span data-ttu-id="b5fb0-119">Cortana reageert en u wordt gevraagd om dit te bevestigen.</span><span class="sxs-lookup"><span data-stu-id="b5fb0-119">Cortana will respond and prompt you to confirm.</span></span> <span data-ttu-id="b5fb0-120">Wacht tot er na de vraag een geluid wordt afspelen en zeg vervolgens Ja.</span><span class="sxs-lookup"><span data-stu-id="b5fb0-120">Wait for a sound to play after the question, and then say "Yes."</span></span> <span data-ttu-id="b5fb0-121">Het apparaat wordt opnieuw opgestart.</span><span class="sxs-lookup"><span data-stu-id="b5fb0-121">The device will restart.</span></span>

### <a name="use-the-power-button-to-do-a-safe-restart"></a><span data-ttu-id="b5fb0-122">De aan/uit-knop gebruiken om veilig opnieuw op te starten</span><span class="sxs-lookup"><span data-stu-id="b5fb0-122">Use the power button to do a safe restart</span></span>

<span data-ttu-id="b5fb0-123">Als u het apparaat nog steeds niet opnieuw kunt opstarten, probeert u het opnieuw op te starten met behulp van de **aan/uit-knop:**</span><span class="sxs-lookup"><span data-stu-id="b5fb0-123">If you still can't restart your device, try to restart it by using the **power** button:</span></span>

1. <span data-ttu-id="b5fb0-124">Houd de **aan/uit-knop** vijf seconden ingedrukt.</span><span class="sxs-lookup"><span data-stu-id="b5fb0-124">Press and hold the **power** button for 5 seconds.</span></span> <span data-ttu-id="b5fb0-125">Na 1 seconde gaan alle vijf led's uit en schakelen ze één voor één van rechts naar links uit.</span><span class="sxs-lookup"><span data-stu-id="b5fb0-125">After 1 second, all five LEDs will illuminate and then slowly turn off one by one from right to left.</span></span> <span data-ttu-id="b5fb0-126">Na 5 seconden zijn alle LED's uitgeschakeld, wat aangeeft dat het afsluiten is geslaagd.</span><span class="sxs-lookup"><span data-stu-id="b5fb0-126">After 5 seconds, all LEDs will be off, indicating successful shutdown.</span></span>
      
   > [!IMPORTANT]
   > <span data-ttu-id="b5fb0-127">Stop met het indrukken van de knop direct nadat alle LED's zijn uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="b5fb0-127">Stop pressing the button immediately after all the LEDs have turned off.</span></span>
1. <span data-ttu-id="b5fb0-128">Wacht 1 minuut totdat het afsluiten is voltooid.</span><span class="sxs-lookup"><span data-stu-id="b5fb0-128">Wait 1 minute for the shutdown to complete.</span></span> <span data-ttu-id="b5fb0-129">Het afsluiten wordt mogelijk nog uitgevoerd, zelfs nadat de weergaven zijn uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="b5fb0-129">The shutdown may still be in progress even after the displays are turned off.</span></span>
2. <span data-ttu-id="b5fb0-130">Schakel het apparaat opnieuw in door 1 seconde op de **aan/uit-knop** te drukken en ingedrukt te houden.</span><span class="sxs-lookup"><span data-stu-id="b5fb0-130">Turn on the device again by pressing and holding the **power** button for 1 second.</span></span>

### <a name="do-a-safe-restart-by-using-windows-device-portal"></a><span data-ttu-id="b5fb0-131">Veilig opnieuw opstarten met behulp van Windows Apparaatportal</span><span class="sxs-lookup"><span data-stu-id="b5fb0-131">Do a safe restart by using Windows Device Portal</span></span>

> [!NOTE]
> <span data-ttu-id="b5fb0-132">Voor dit proces moet HoloLens worden geconfigureerd als een apparaat voor ontwikkelaars.</span><span class="sxs-lookup"><span data-stu-id="b5fb0-132">For this process, HoloLens has to be configured as a developer device.</span></span> <span data-ttu-id="b5fb0-133">Meer informatie op [Windows Apparaatportal](/windows/mixed-reality/using-the-windows-device-portal).</span><span class="sxs-lookup"><span data-stu-id="b5fb0-133">Learn more at [Windows Device Portal](/windows/mixed-reality/using-the-windows-device-portal).</span></span>

<span data-ttu-id="b5fb0-134">Als de vorige procedure niet werkt, probeert u het apparaat opnieuw op te starten met behulp van [Windows Apparaatportal](/windows/mixed-reality/using-the-windows-device-portal).</span><span class="sxs-lookup"><span data-stu-id="b5fb0-134">If the previous procedure didn't work, try to restart the device by using [Windows Device Portal](/windows/mixed-reality/using-the-windows-device-portal).</span></span> <span data-ttu-id="b5fb0-135">Zoek in de rechterbovenhoek de optie om het apparaat opnieuw op te starten of af te sluiten.</span><span class="sxs-lookup"><span data-stu-id="b5fb0-135">In the upper-right corner, find the option to restart or shut down the device.</span></span>

### <a name="do-an-unsafe-forced-restart"></a><span data-ttu-id="b5fb0-136">Een onveilig geforceerd opnieuw opstarten</span><span class="sxs-lookup"><span data-stu-id="b5fb0-136">Do an unsafe forced restart</span></span>

<span data-ttu-id="b5fb0-137">Als de vorige methoden uw apparaat niet opnieuw HoloLens, forceer dan opnieuw opstarten.</span><span class="sxs-lookup"><span data-stu-id="b5fb0-137">If the previous methods didn't restart your HoloLens, force a restart.</span></span> <span data-ttu-id="b5fb0-138">Deze methode is gelijk aan het verwijderen en opnieuw installeren van de batterij.</span><span class="sxs-lookup"><span data-stu-id="b5fb0-138">This method is equivalent to removing and reinstalling the battery.</span></span> <span data-ttu-id="b5fb0-139">Dit is gevaarlijk omdat uw apparaat hierdoor beschadigd kan raken.</span><span class="sxs-lookup"><span data-stu-id="b5fb0-139">It's dangerous because it might leave your device in a corrupted state.</span></span> <span data-ttu-id="b5fb0-140">Als dat gebeurt, moet u uw HoloLens.</span><span class="sxs-lookup"><span data-stu-id="b5fb0-140">If that happens, you'll have to flash your HoloLens.</span></span>  

> [!WARNING]
> <span data-ttu-id="b5fb0-141">Dit is een mogelijk schadelijke methode en mag alleen worden gebruikt als de eerder genoemde methoden niet werken.</span><span class="sxs-lookup"><span data-stu-id="b5fb0-141">This is a potentially harmful method and should only be used if the previously cited methods didn't work.</span></span>

1. <span data-ttu-id="b5fb0-142">Houd de **aan/uit-knop** ten minste 10 seconden ingedrukt.</span><span class="sxs-lookup"><span data-stu-id="b5fb0-142">Press and hold the **power** button for at least 10 seconds.</span></span>
   - <span data-ttu-id="b5fb0-143">Het is geen probleem om de knop langer dan 10 seconden ingedrukt te houden.</span><span class="sxs-lookup"><span data-stu-id="b5fb0-143">It's okay to hold the button for longer than 10 seconds.</span></span>
   - <span data-ttu-id="b5fb0-144">Het is veilig om led-activiteiten te negeren.</span><span class="sxs-lookup"><span data-stu-id="b5fb0-144">It's safe to ignore any LED activity.</span></span>
1. <span data-ttu-id="b5fb0-145">Laat de knop los en wacht 2-3 seconden.</span><span class="sxs-lookup"><span data-stu-id="b5fb0-145">Release the button and wait for 2-3 seconds.</span></span>
1. <span data-ttu-id="b5fb0-146">Houd de **aan/uit-knop** 1 seconde ingedrukt.</span><span class="sxs-lookup"><span data-stu-id="b5fb0-146">Press and hold the **power** button for 1  second.</span></span>
1. <span data-ttu-id="b5fb0-147">Als u nog steeds  problemen hebt, drukt u 4 seconden op de aan/uit-knop totdat alle batterijindicatoren verdwijnen en het scherm geen hologrammen meer we weergeven.</span><span class="sxs-lookup"><span data-stu-id="b5fb0-147">If you still have problems, press the **power** button for 4 seconds, until all the battery indicators fade out and the screen stops displaying holograms.</span></span> <span data-ttu-id="b5fb0-148">Wacht 1 minuut en druk vervolgens nogmaals op **de aan/uit-knop** om het apparaat in te zetten.</span><span class="sxs-lookup"><span data-stu-id="b5fb0-148">Wait 1 minute, and then press the **power** button again to turn on the device.</span></span>

## <a name="go-back-to-a-previous-version---hololens-1st-gen"></a><span data-ttu-id="b5fb0-149">Terug naar een eerdere versie - HoloLens (1e generatie)</span><span class="sxs-lookup"><span data-stu-id="b5fb0-149">Go back to a previous version - HoloLens (1st Gen)</span></span>

<span data-ttu-id="b5fb0-150">In sommige gevallen wilt u mogelijk teruggaan naar een eerdere versie van de HoloLens software.</span><span class="sxs-lookup"><span data-stu-id="b5fb0-150">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="b5fb0-151">U kunt dit doen door het hulpprogramma Windows device recovery te gebruiken om uw HoloLens te herstellen naar de eerdere versie.</span><span class="sxs-lookup"><span data-stu-id="b5fb0-151">You can do this by using the Windows Device Recovery Tool to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="b5fb0-152">Als u terug gaat naar een eerdere versie, worden uw persoonlijke bestanden en instellingen verwijderd.</span><span class="sxs-lookup"><span data-stu-id="b5fb0-152">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="b5fb0-153">Als u wilt teruggaan naar een eerdere versie van HoloLens 1, volgt u deze stappen:</span><span class="sxs-lookup"><span data-stu-id="b5fb0-153">To go back to a previous version of HoloLens 1, follow these steps:</span></span>

1. <span data-ttu-id="b5fb0-154">Zorg ervoor dat u geen telefoons of apparaten hebt Windows zijn aangesloten op uw pc.</span><span class="sxs-lookup"><span data-stu-id="b5fb0-154">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
1. <span data-ttu-id="b5fb0-155">Download op uw pc de [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span><span class="sxs-lookup"><span data-stu-id="b5fb0-155">On your PC, download the [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span></span>
1. <span data-ttu-id="b5fb0-156">Download het [herstelpakket HoloLens Jubileumupdate.](https://aka.ms/hololensrecovery)</span><span class="sxs-lookup"><span data-stu-id="b5fb0-156">Download the [HoloLens Anniversary Update recovery package](https://aka.ms/hololensrecovery).</span></span>
1. <span data-ttu-id="b5fb0-157">Wanneer het downloaden is voltooien, opent u   >  **Bestandenverkenner Downloads.**</span><span class="sxs-lookup"><span data-stu-id="b5fb0-157">When the downloads finish, open **File explorer** > **Downloads**.</span></span> <span data-ttu-id="b5fb0-158">Klik met de rechtermuisknop op de ingepakte map die u zojuist hebt gedownload en selecteer **Alles** uitpakken  >  **om** het uit tepakken.</span><span class="sxs-lookup"><span data-stu-id="b5fb0-158">Right-click the zipped folder you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="b5fb0-159">Verbinding maken uw HoloLens op uw pc met behulp van de micro-USB-kabel bij de kabel.</span><span class="sxs-lookup"><span data-stu-id="b5fb0-159">Connect your HoloLens to your PC using the micro-USB cable that it came with.</span></span> <span data-ttu-id="b5fb0-160">(Zelfs als u andere kabels hebt gebruikt om uw HoloLens, werkt deze het beste.)</span><span class="sxs-lookup"><span data-stu-id="b5fb0-160">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="b5fb0-161">De WDRT detecteert automatisch uw HoloLens.</span><span class="sxs-lookup"><span data-stu-id="b5fb0-161">The WDRT will automatically detect your HoloLens.</span></span> <span data-ttu-id="b5fb0-162">Selecteer de **Microsoft HoloLens** tegel.</span><span class="sxs-lookup"><span data-stu-id="b5fb0-162">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="b5fb0-163">Selecteer in het volgende scherm Handmatige **pakketselectie** en kies het installatiebestand in de map die u in stap 4 hebt uitgepakt.</span><span class="sxs-lookup"><span data-stu-id="b5fb0-163">On the next screen, select **Manual package selection** and choose the installation file contained in the folder you unzipped in step 4.</span></span> <span data-ttu-id="b5fb0-164">(Zoek naar een bestand met de extensie .ffu.)</span><span class="sxs-lookup"><span data-stu-id="b5fb0-164">(Look for a file with the .ffu extension.)</span></span>
1. <span data-ttu-id="b5fb0-165">Selecteer **Software installeren** en volg de instructies.</span><span class="sxs-lookup"><span data-stu-id="b5fb0-165">Select **Install software**, and follow the instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="b5fb0-166">Als de WDRT uw apparaat niet HoloLens, start u de pc opnieuw op.</span><span class="sxs-lookup"><span data-stu-id="b5fb0-166">If the WDRT doesn't detect your HoloLens, try restarting your PC.</span></span> <span data-ttu-id="b5fb0-167">Als dat niet werkt, selecteert u Mijn apparaat is niet **gedetecteerd,** selecteert **Microsoft HoloLens** en volgt u de instructies.</span><span class="sxs-lookup"><span data-stu-id="b5fb0-167">If that doesn't work, select **My device was not detected**, select **Microsoft HoloLens**, and then follow the instructions.</span></span>

## <a name="reset-to-factory-settings"></a><span data-ttu-id="b5fb0-168">Fabrieksinstellingen herstellen</span><span class="sxs-lookup"><span data-stu-id="b5fb0-168">Reset to factory settings</span></span>

> [!NOTE]
> <span data-ttu-id="b5fb0-169">De accu moet ten minste 40 procent worden opstart.</span><span class="sxs-lookup"><span data-stu-id="b5fb0-169">The battery needs at least a 40-percent charge to reset.</span></span>

<span data-ttu-id="b5fb0-170">Als uw HoloLens nog steeds een probleem heeft, kunt u deze opnieuw instellen in de fabrieksstaat.</span><span class="sxs-lookup"><span data-stu-id="b5fb0-170">If your HoloLens still has a problem, try resetting it to factory state.</span></span> <span data-ttu-id="b5fb0-171">Met deze stap behoudt u de versie van Windows Holographic-software die erop is geïnstalleerd en retourneert al het andere naar de fabrieksinstellingen.</span><span class="sxs-lookup"><span data-stu-id="b5fb0-171">This step keeps the version of the Windows Holographic software that's installed on it and returns everything else to factory settings.</span></span>

>[!WARNING]
> <span data-ttu-id="b5fb0-172">Als u uw apparaat opnieuw in stelt, worden al uw persoonlijke gegevens, apps en instellingen gewist, inclusief informatie over het opnieuw instellen van TPM.</span><span class="sxs-lookup"><span data-stu-id="b5fb0-172">If you reset your device, all your personal data, apps, and settings will be erased, including TPM reset information.</span></span> <span data-ttu-id="b5fb0-173">Bij het opnieuw instellen wordt alleen de meest recente geïnstalleerde versie van Windows Holographic geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="b5fb0-173">Resetting will only install the latest installed version of Windows Holographic.</span></span> <span data-ttu-id="b5fb0-174">U moet alle initialisatiestappen opnieuw doen (kalibreren, verbinding maken met Wi-Fi, een gebruikersaccount maken, apps downloaden, etc.).</span><span class="sxs-lookup"><span data-stu-id="b5fb0-174">You'll have to redo all the initialization steps (calibrate, connect to Wi-Fi, create a user account, download apps, and so on).</span></span>

1. <span data-ttu-id="b5fb0-175">Open de Instellingen app en selecteer vervolgens **Herstel**  >  **bijwerken.**</span><span class="sxs-lookup"><span data-stu-id="b5fb0-175">Open the Settings app, and then select **Update** > **Recovery**.</span></span>
1. <span data-ttu-id="b5fb0-176">Selecteer de **optie Apparaat opnieuw** instellen en lees het bevestigingsbericht.</span><span class="sxs-lookup"><span data-stu-id="b5fb0-176">Select the **Reset device** option and read the confirmation message.</span></span>
1. <span data-ttu-id="b5fb0-177">Bevestig het opnieuw instellen.</span><span class="sxs-lookup"><span data-stu-id="b5fb0-177">Confirm the reset.</span></span> <span data-ttu-id="b5fb0-178">Het apparaat wordt opnieuw opgestart en er wordt een set draaiende tandwielen en een voortgangsbalk weergegeven.</span><span class="sxs-lookup"><span data-stu-id="b5fb0-178">The device will restart and display a set of spinning gears and a progress bar.</span></span>
1. <span data-ttu-id="b5fb0-179">Wacht ongeveer 30 minuten tot dit proces is voltooid.</span><span class="sxs-lookup"><span data-stu-id="b5fb0-179">Wait about 30 minutes for this process to complete.</span></span> <span data-ttu-id="b5fb0-180">Wanneer dit is gebeurd, wordt het apparaat opnieuw opgestart in de out-of-the-box-ervaring.</span><span class="sxs-lookup"><span data-stu-id="b5fb0-180">When it's done, the device will restart into the "out-of-the-box" experience.</span></span>

## <a name="reinstall-the-operating-system"></a><span data-ttu-id="b5fb0-181">Het besturingssysteem opnieuw installeren</span><span class="sxs-lookup"><span data-stu-id="b5fb0-181">Reinstall the operating system</span></span>

<span data-ttu-id="b5fb0-182">Als het apparaat nog steeds een probleem heeft na het opnieuw opstarten en opnieuw instellen, kunt u een herstelprogramma op uw computer gebruiken om het besturingssysteem en de firmware opnieuw te HoloLens installeren.</span><span class="sxs-lookup"><span data-stu-id="b5fb0-182">If the device is still having a problem after restart and reset, you can use a recovery tool on your computer to reinstall the HoloLens operating system and firmware.</span></span>  

<span data-ttu-id="b5fb0-183">De gegevens die HoloLens nodig hebben voor het opnieuw instellen, worden verpakt in een volledige flashupdate (FFU), die vergelijkbaar is met een .iso-, WIM- of VHD-bestand.</span><span class="sxs-lookup"><span data-stu-id="b5fb0-183">The data that HoloLens needs for the reset is packaged in a Full Flash Update (FFU), which is similar to an .iso, .wim, or .vhd file.</span></span> [<span data-ttu-id="b5fb0-184">Meer informatie over bestandsindelingen voor FFU-afbeeldingen.</span><span class="sxs-lookup"><span data-stu-id="b5fb0-184">Learn about FFU image file formats.</span></span>](/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

<span data-ttu-id="b5fb0-185">U kunt een nieuw besturingssysteem installeren op uw HoloLens (1e generatie) met behulp van Windows Device Recovery Tool.</span><span class="sxs-lookup"><span data-stu-id="b5fb0-185">You can install a new operating system on your HoloLens (1st gen) by using the Windows Device Recovery Tool.</span></span> <span data-ttu-id="b5fb0-186">Voordat u dat hulpprogramma gebruikt, moet u zien of het probleem wordt opgelost door uw HoloLens opnieuw in te stellen.</span><span class="sxs-lookup"><span data-stu-id="b5fb0-186">Before you use that tool, see if restarting or resetting your HoloLens fixes the problem.</span></span>

<span data-ttu-id="b5fb0-187">Het herstelproces kan even duren.</span><span class="sxs-lookup"><span data-stu-id="b5fb0-187">The recovery process may take a while.</span></span> <span data-ttu-id="b5fb0-188">Wanneer dit is gebeurd, wordt de nieuwste versie van Windows Holographic-software geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="b5fb0-188">When it's done, the latest version of the Windows Holographic software will be installed.</span></span>

<span data-ttu-id="b5fb0-189">Als u het hulpprogramma wilt gebruiken, hebt u een computer Windows 10 of hoger met ten minste 4 GB vrije opslagruimte.</span><span class="sxs-lookup"><span data-stu-id="b5fb0-189">To use the tool, you need a computer running Windows 10 or later with at least 4 GB of free storage space.</span></span> <span data-ttu-id="b5fb0-190">U kunt dit hulpprogramma niet uitvoeren op een virtuele machine.</span><span class="sxs-lookup"><span data-stu-id="b5fb0-190">You can't run this tool on a virtual machine.</span></span>

### <a name="recover-your-hololens"></a><span data-ttu-id="b5fb0-191">Uw HoloLens</span><span class="sxs-lookup"><span data-stu-id="b5fb0-191">Recover your HoloLens</span></span>

1. <span data-ttu-id="b5fb0-192">Download en installeer de [Windows Device Recovery Tool](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) op uw computer.</span><span class="sxs-lookup"><span data-stu-id="b5fb0-192">Download and install the [Windows Device Recovery Tool](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) on your computer.</span></span>
1. <span data-ttu-id="b5fb0-193">Verbinding maken de HoloLens (1e generatie) op uw computer met behulp van de Micro USB-kabel die bij uw HoloLens.</span><span class="sxs-lookup"><span data-stu-id="b5fb0-193">Connect the HoloLens (1st gen) to your computer by using the Micro USB cable that came with your HoloLens.</span></span>
1. <span data-ttu-id="b5fb0-194">Open de Windows Device Recovery Tool en volg de instructies.</span><span class="sxs-lookup"><span data-stu-id="b5fb0-194">Open the Windows Device Recovery Tool and follow the instructions.</span></span>

<span data-ttu-id="b5fb0-195">Als de HoloLens (eerste generatie) niet automatisch wordt gedetecteerd, selecteert u Mijn **apparaat is niet gedetecteerd.**</span><span class="sxs-lookup"><span data-stu-id="b5fb0-195">If the HoloLens (1st gen) isn't automatically detected, select **My device was not detected**.</span></span> <span data-ttu-id="b5fb0-196">Volg vervolgens de instructies om het apparaat in de herstelmodus te zetten.</span><span class="sxs-lookup"><span data-stu-id="b5fb0-196">Then follow the instructions to put the device into recovery mode.</span></span>

### <a name="manual-flashing-mode"></a><span data-ttu-id="b5fb0-197">Handmatige flashmodus</span><span class="sxs-lookup"><span data-stu-id="b5fb0-197">Manual flashing mode</span></span>

<span data-ttu-id="b5fb0-198">Als uw apparaat niet wordt gedetecteerd, volgt u deze stappen om het in de flashmodus te zetten:</span><span class="sxs-lookup"><span data-stu-id="b5fb0-198">If your device isn't detected, follow these steps to put it into flashing mode:</span></span>

1. <span data-ttu-id="b5fb0-199">Ontkoppel het apparaat van een voedingsbron.</span><span class="sxs-lookup"><span data-stu-id="b5fb0-199">Unplug the device from any power source.</span></span>
1. <span data-ttu-id="b5fb0-200">Als het apparaat is aan, houdt u de **aan/uit-knop ingedrukt** totdat het volledig wordt uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="b5fb0-200">If the device is on, hold down the **power** button until it completely turns off.</span></span>
2. <span data-ttu-id="b5fb0-201">Houd de **volumeknop ingedrukt** en tik kort op **de aan/uit-knop.**</span><span class="sxs-lookup"><span data-stu-id="b5fb0-201">Hold the **volume up** button, and briefly tap the **power** button.</span></span> <span data-ttu-id="b5fb0-202">Het apparaat moet starten en alleen de middelste LED weergeven.</span><span class="sxs-lookup"><span data-stu-id="b5fb0-202">The device should start and display only the middle LED.</span></span>
3. <span data-ttu-id="b5fb0-203">Sluit het apparaat aan op uw pc.</span><span class="sxs-lookup"><span data-stu-id="b5fb0-203">Plug the device into your PC.</span></span>
4. <span data-ttu-id="b5fb0-204">Open de Windows Device Recovery Tool.</span><span class="sxs-lookup"><span data-stu-id="b5fb0-204">Open the Windows Device Recovery Tool.</span></span>
5. <span data-ttu-id="b5fb0-205">Selecteer **Mijn apparaat is niet gedetecteerd** en selecteer **HoloLens.**</span><span class="sxs-lookup"><span data-stu-id="b5fb0-205">Select **My device was not detected** and then **HoloLens**.</span></span> 
6. <span data-ttu-id="b5fb0-206">Volg de instructies om uw apparaat te herstellen.</span><span class="sxs-lookup"><span data-stu-id="b5fb0-206">Follow the instructions to recover your device.</span></span>
