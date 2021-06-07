---
title: HoloLens opnieuw opstarten, opnieuw instellen of herstellen
ms.reviewer: Follow along with our basic and advanced instructions for rebooting or resetting your HoloLens 2 device.
description: Advanced Recovery Companion gebruiken om een afbeelding te HoloLens 2.
keywords: how-to, reboot, reset, recover, hard reset, soft reset, power cycle, HoloLens, shut down, arc, advanced recovery companion
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.date: 04/27/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: high
manager: jarrettr
appliesto:
- HoloLens 2
ms.openlocfilehash: afd782df1c68e8441b14823e0d961317914140e3
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/25/2021
ms.locfileid: "111379423"
---
# <a name="restart-reset-or-recover-hololens-2"></a><span data-ttu-id="e41c1-104">Opnieuw opstarten, opnieuw instellen of HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="e41c1-104">Restart, reset, or recover HoloLens 2</span></span>

## <a name="charge-the-device"></a><span data-ttu-id="e41c1-105">Het apparaat in rekening brengen</span><span class="sxs-lookup"><span data-stu-id="e41c1-105">Charge the device</span></span>

>[!IMPORTANT]
> <span data-ttu-id="e41c1-106">Voordat u een probleemoplossingsprocedure start, moet u ervoor zorgen dat uw apparaat, indien mogelijk, wordt op geladen tot **20 tot 40** procent van de accucapaciteit.</span><span class="sxs-lookup"><span data-stu-id="e41c1-106">Before you start any troubleshooting procedure, make sure that your device is charged to **20 to 40 percent** of battery capacity, if possible.</span></span> <span data-ttu-id="e41c1-107">De [accuindicatorlichten onder](hololens2-setup.md#lights-that-indicate-the-battery-level) de aan/uit-knop zijn een snelle manier om de accucapaciteit te controleren zonder u aan te melden bij het apparaat.</span><span class="sxs-lookup"><span data-stu-id="e41c1-107">The [battery indicator lights](hololens2-setup.md#lights-that-indicate-the-battery-level) located under the power button are a quick way to verify the battery capacity without logging into the device.</span></span>

<span data-ttu-id="e41c1-108">Gebruik de [kabel en de USB Type-C-kabel](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) die bij de HoloLens 2 omdat dit de beste manier is om uw apparaat op te laden.</span><span class="sxs-lookup"><span data-stu-id="e41c1-108">Use the [charger and the USB Type-C cable](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) that came with the HoloLens 2 as that is the best way to charge your device.</span></span> <span data-ttu-id="e41c1-109">De goederen leveren 18 W aan stroom (9V bij 2A).</span><span class="sxs-lookup"><span data-stu-id="e41c1-109">The charger supplies 18W of power (9V at 2A).</span></span> <span data-ttu-id="e41c1-110">Door gebruik te maken van de meegeleverde HoloLens 2 de accu in minder dan 65 minuten vol wanneer het apparaat stand-by is.</span><span class="sxs-lookup"><span data-stu-id="e41c1-110">Using the wall charger supplied, HoloLens 2 devices can charge the battery to full in less than 65 minutes when the device is in standby.</span></span> <span data-ttu-id="e41c1-111">Als deze accessoires niet beschikbaar zijn, moet u ervoor zorgen dat de beschikbare thee ten minste 15W aan stroom kan ondersteunen.</span><span class="sxs-lookup"><span data-stu-id="e41c1-111">If those accessories aren't available, make sure the charger that's available can support at least 15W of power.</span></span>

> [!NOTE]
> <span data-ttu-id="e41c1-112">Vermijd indien mogelijk het gebruik van een pc om het apparaat via USB op te laden, wat traag is.</span><span class="sxs-lookup"><span data-stu-id="e41c1-112">If possible, avoid using a PC to charge the device over USB, which is slow.</span></span>

<span data-ttu-id="e41c1-113">Als het apparaat correct is opgestart en wordt uitgevoerd, zijn er drie manieren om het laadniveau van de accu te controleren:</span><span class="sxs-lookup"><span data-stu-id="e41c1-113">If the device is correctly booted and running, there are three ways to check the battery charge level:</span></span>

- <span data-ttu-id="e41c1-114">Vanuit het hoofdmenu van de gebruikersinterface van het HoloLens-apparaat.</span><span class="sxs-lookup"><span data-stu-id="e41c1-114">From the main menu of the HoloLens device UI.</span></span>
- <span data-ttu-id="e41c1-115">Bekijk de LED dicht bij de aan/uit-knop (voor een kosten van 40 procent ziet u ten minste twee solide LED's).</span><span class="sxs-lookup"><span data-stu-id="e41c1-115">View the LED close to the power button (for a 40-percent charge, you should see at least two solid LEDs).</span></span>
    - <span data-ttu-id="e41c1-116">Wanneer het apparaat wordt op laden, wordt de accu-indicator licht om het huidige laadniveau aan te geven.</span><span class="sxs-lookup"><span data-stu-id="e41c1-116">When the device is charging, the battery indicator lights up to indicate the current level of charge.</span></span>  <span data-ttu-id="e41c1-117">Het laatste licht vervaagt in en uit om aan te geven dat de kosten actief zijn.</span><span class="sxs-lookup"><span data-stu-id="e41c1-117">The last light will fade in and out to indicate active charging.</span></span>
    - <span data-ttu-id="e41c1-118">Wanneer uw HoloLens is aan, geeft de batterijindicator het accuniveau in vijf stappen weer.</span><span class="sxs-lookup"><span data-stu-id="e41c1-118">When your HoloLens is on, the battery indicator displays the battery level in five increments.</span></span>
    - <span data-ttu-id="e41c1-119">Wanneer slechts een van de vijf lampen is aan, is het accuniveau lager dan 20 procent.</span><span class="sxs-lookup"><span data-stu-id="e41c1-119">When only one of the five lights is on, the battery level is below 20 percent.</span></span>
    - <span data-ttu-id="e41c1-120">Als het accuniveau kritiek laag is en u het apparaat probeert in te zetten, gaat er kort één lampje uit en gaat u uit.</span><span class="sxs-lookup"><span data-stu-id="e41c1-120">If the battery level is critically low and you try to turn on the device, one light will blink briefly, then go out.</span></span>
- <span data-ttu-id="e41c1-121">Open verkenner op uw host-pc **en** zoek uw HoloLens 2 aan de linkerkant onder **Deze pc.**</span><span class="sxs-lookup"><span data-stu-id="e41c1-121">On your host PC, open **File Explorer** and look for your HoloLens 2 device on left side under **This PC**.</span></span> <span data-ttu-id="e41c1-122">Klik met de rechtermuisknop op het apparaat en selecteer **Eigenschappen.**</span><span class="sxs-lookup"><span data-stu-id="e41c1-122">Right-click the device, and select **Properties**.</span></span> <span data-ttu-id="e41c1-123">In een dialoogvenster wordt het acculadingsniveau weergegeven.</span><span class="sxs-lookup"><span data-stu-id="e41c1-123">A dialog box will show the battery charge level.</span></span>

   ![Een scherm HoloLens 2 eigenschappen toont het niveau van de batterijwijziging](images/ResetRecovery2.png)

<span data-ttu-id="e41c1-125">Als het apparaat niet kan worden opgestart naar het opstartmenu, noteer dan de LED-weergave en apparaatinsemulatie op de host-pc.</span><span class="sxs-lookup"><span data-stu-id="e41c1-125">If the device can't boot to the startup menu, note the LED appearance and device enumeration on the host PC.</span></span> <span data-ttu-id="e41c1-126">Volg vervolgens de gids [voor probleemoplossing.](hololens-troubleshooting.md)</span><span class="sxs-lookup"><span data-stu-id="e41c1-126">Then follow the [troubleshooting guide](hololens-troubleshooting.md).</span></span> <span data-ttu-id="e41c1-127">Als de status van het apparaat niet overeen komt met een van de statussen die worden vermeld in de gids voor probleemoplossing, voert u de [procedure](hololens-recovery.md#hard-reset-procedure) voor het opnieuw instellen uit met het apparaat dat is verbonden met de voeding en niet met uw host-pc.</span><span class="sxs-lookup"><span data-stu-id="e41c1-127">If the state of the device doesn't match any of the states listed in the troubleshooting guide, perform the [hard reset procedure](hololens-recovery.md#hard-reset-procedure) with the device connected to the power supply, not to your host PC.</span></span> <span data-ttu-id="e41c1-128">Wacht ten minste één uur totdat het apparaat wordt op belast.</span><span class="sxs-lookup"><span data-stu-id="e41c1-128">Wait at least one hour for the device to charge.</span></span>

## <a name="reset-the-device"></a><span data-ttu-id="e41c1-129">Het apparaat opnieuw instellen</span><span class="sxs-lookup"><span data-stu-id="e41c1-129">Reset the device</span></span>

<span data-ttu-id="e41c1-130">Onder bepaalde omstandigheden moet u het apparaat mogelijk handmatig opnieuw instellen zonder de gebruikersinterface van de software te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="e41c1-130">Under certain circumstances, you may have to manually reset the device without using the software UI.</span></span>

### <a name="standard-procedure"></a><span data-ttu-id="e41c1-131">Standaardprocedure</span><span class="sxs-lookup"><span data-stu-id="e41c1-131">Standard procedure</span></span>

1. <span data-ttu-id="e41c1-132">Koppel de Type-C-kabel los om het apparaat los te koppelen van de voeding of de host-pc.</span><span class="sxs-lookup"><span data-stu-id="e41c1-132">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="e41c1-133">Houd de **aan/uit-knop** 15 seconden ingedrukt.</span><span class="sxs-lookup"><span data-stu-id="e41c1-133">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="e41c1-134">Alle LED's moeten uit zijn.</span><span class="sxs-lookup"><span data-stu-id="e41c1-134">All LEDs should be off.</span></span>

3. <span data-ttu-id="e41c1-135">Wacht 2-3 seconden en druk vervolgens kort op de **aan/uit-knop.**</span><span class="sxs-lookup"><span data-stu-id="e41c1-135">Wait 2-3 seconds, and then short-press the **power** button.</span></span> <span data-ttu-id="e41c1-136">De LED's dicht bij de aan/uit-knop worden aan het licht licht en het apparaat wordt opstart.</span><span class="sxs-lookup"><span data-stu-id="e41c1-136">The LEDs close to the power button will light up, and the device will begin to start up.</span></span>

4. <span data-ttu-id="e41c1-137">Verbind het apparaat met de host-pc en open Apparaatbeheer.</span><span class="sxs-lookup"><span data-stu-id="e41c1-137">Connect the device to the host PC, and then open Device Manager.</span></span> <span data-ttu-id="e41c1-138">(Voor Windows 10 drukt u op **de Windows-toets** en vervolgens op **de X-toets** en selecteert **u Apparaatbeheer**.) Zorg ervoor dat het apparaat op de juiste manier Microsoft HoloLens *zoals* wordt weergegeven in de volgende afbeelding:</span><span class="sxs-lookup"><span data-stu-id="e41c1-138">(For Windows 10, press the **Windows** key and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![HoloLens 2 Microsoft HolooLensRecovery-devive manager](images/MicrosoftHoloLens_DeviceManager.png)

### <a name="hard-reset-procedure"></a><span data-ttu-id="e41c1-140">Procedure voor hard opnieuw instellen</span><span class="sxs-lookup"><span data-stu-id="e41c1-140">Hard-reset procedure</span></span>

<span data-ttu-id="e41c1-141">Als de standaardprocedure voor opnieuw instellen niet werkt, gebruikt u de procedure voor hard opnieuw instellen:</span><span class="sxs-lookup"><span data-stu-id="e41c1-141">If the standard reset procedure didn't work, use the hard-reset procedure:</span></span>

1. <span data-ttu-id="e41c1-142">Koppel de Type-C-kabel los om het apparaat los te koppelen van de voeding of de host-pc.</span><span class="sxs-lookup"><span data-stu-id="e41c1-142">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="e41c1-143">Houd de **aan/uit-knoppen** op het volume  +   15 seconden in de wacht.</span><span class="sxs-lookup"><span data-stu-id="e41c1-143">Hold down the **volume down** + **power** buttons for 15 seconds.</span></span> <span data-ttu-id="e41c1-144">Het apparaat wordt automatisch opnieuw opgestart.</span><span class="sxs-lookup"><span data-stu-id="e41c1-144">The device will automatically restart.</span></span>

4. <span data-ttu-id="e41c1-145">Verbind het apparaat met de host-pc.</span><span class="sxs-lookup"><span data-stu-id="e41c1-145">Connect the device to the host PC.</span></span>

5. <span data-ttu-id="e41c1-146">Open Apparaatbeheer (voor Windows 10 **op de Windows-toets** en vervolgens op de **X-toets** en selecteer **Apparaatbeheer**).</span><span class="sxs-lookup"><span data-stu-id="e41c1-146">Open Device Manager (for Windows 10 press the **Windows** key and then the **X** key, and then select **Device Manager**).</span></span> <span data-ttu-id="e41c1-147">Zorg ervoor dat het apparaat op de juiste manier Microsoft HoloLens *zoals* wordt weergegeven in de volgende afbeelding:</span><span class="sxs-lookup"><span data-stu-id="e41c1-147">Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![HoloLens 2 Microsoft HolooLensRecovery device maanger 2](images/MicrosoftHoloLens_DeviceManager.png)

## <a name="clean-reflash-the-device"></a><span data-ttu-id="e41c1-149">Schone reflash op het apparaat</span><span class="sxs-lookup"><span data-stu-id="e41c1-149">Clean-reflash the device</span></span>

<span data-ttu-id="e41c1-150">In uitzonderlijke situaties moet u de HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="e41c1-150">In extraordinary situations, you may have to "clean-flash" the HoloLens 2.</span></span> <span data-ttu-id="e41c1-151">Houd er rekening mee dat clean-reflash naar verwachting geen invloed heeft op de volgende problemen:</span><span class="sxs-lookup"><span data-stu-id="e41c1-151">Please note that clean-reflash isn’t expected to affect the following issues:</span></span>
- [<span data-ttu-id="e41c1-152">Kleur uniformiteit weergeven</span><span class="sxs-lookup"><span data-stu-id="e41c1-152">Display color uniformity</span></span>](hololens2-display.md)
- <span data-ttu-id="e41c1-153">Opstarten met geluid, maar geen weergave-uitvoer</span><span class="sxs-lookup"><span data-stu-id="e41c1-153">Booting with sound but no display output</span></span>
- [<span data-ttu-id="e41c1-154">1-3-5-LED-patroon</span><span class="sxs-lookup"><span data-stu-id="e41c1-154">1-3-5-LED pattern</span></span>](hololens2-setup.md#lights-to-indicate-problems)
- [<span data-ttu-id="e41c1-155">Oververhitting</span><span class="sxs-lookup"><span data-stu-id="e41c1-155">Overheating</span></span>](hololens-environment-considerations.md#temperature-and-regulatory-information) 
- <span data-ttu-id="e41c1-156">Crashes van het besturingssysteem (die verschillen van crashes van toepassingen)</span><span class="sxs-lookup"><span data-stu-id="e41c1-156">OS crashes (which are distinct from application crashes)</span></span>

<span data-ttu-id="e41c1-157">Er zijn twee manieren om het apparaat te reflashen.</span><span class="sxs-lookup"><span data-stu-id="e41c1-157">There are two ways to reflash the device.</span></span> <span data-ttu-id="e41c1-158">Voor beide moet u eerst [Advanced Recovery Companion installeren vanuit de Windows Store.](https://www.microsoft.com/store/productId/9P74Z35SFRS8)</span><span class="sxs-lookup"><span data-stu-id="e41c1-158">For both, you must first [install Advanced Recovery Companion from the Windows Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span>

>[!WARNING]
><span data-ttu-id="e41c1-159">Als u een reflash op uw apparaat gebruikt, worden al uw persoonlijke gegevens, apps en instellingen gewist, inclusief informatie over het opnieuw instellen van TPM.</span><span class="sxs-lookup"><span data-stu-id="e41c1-159">If you reflash your device, all your personal data, apps, and settings will be erased, including TPM-reset information.</span></span>

<span data-ttu-id="e41c1-160">Advanced Recovery Companion is standaard ingesteld om de meest recente build van de functiere release te downloaden. Lees hier onze [release-opmerkingen](hololens-release-notes.md#) voor meer informatie over de nieuwste functiere release.</span><span class="sxs-lookup"><span data-stu-id="e41c1-160">By default, Advanced Recovery Companion is set to download the most recent feature release build, check here to read our [Release notes](hololens-release-notes.md#) to learn about the latest feature release.</span></span> <span data-ttu-id="e41c1-161">Als u het meest recente HoloLens 2 FFU-pakket (Full Flash Update) wilt downloaden om uw apparaat te reflashen via Advanced Recovery Companion, klikt u hier om de meest recente maandelijkse HoloLens 2 [downloaden.](https://aka.ms/hololens2download)</span><span class="sxs-lookup"><span data-stu-id="e41c1-161">To get the latest HoloLens 2 Full Flash Update (FFU) package to reflash your device via Advanced Recovery Companion, [click here to download the latest monthly HoloLens 2 image](https://aka.ms/hololens2download).</span></span> <span data-ttu-id="e41c1-162">Deze versie is de meest recente algemeen beschikbare build.</span><span class="sxs-lookup"><span data-stu-id="e41c1-162">This version is the latest generally available build.</span></span>

<span data-ttu-id="e41c1-163">Voordat u de reflash-procedure start, moet u ervoor zorgen dat de app is geïnstalleerd en wordt uitgevoerd op uw Windows 10 pc en klaar is om het apparaat te detecteren.</span><span class="sxs-lookup"><span data-stu-id="e41c1-163">Before you start the reflash procedure, make sure the app is installed and running on your Windows 10 PC and ready to detect the device.</span></span> <span data-ttu-id="e41c1-164">Zorg er ook voor dat uw HoloLens minimaal 40% in rekening wordt gebracht.</span><span class="sxs-lookup"><span data-stu-id="e41c1-164">Also ensure that your HoloLens is charged to a minimum of 40%.</span></span>

![HoloLens 2 scherm met schone reflash](images/ARC1.png)

### <a name="normal-procedure"></a><span data-ttu-id="e41c1-166">Normale procedure</span><span class="sxs-lookup"><span data-stu-id="e41c1-166">Normal procedure</span></span>

1. <span data-ttu-id="e41c1-167">Terwijl het HoloLens-apparaat wordt uitgevoerd, verbindt u het met de Windows 10 pc waarop u eerder de Advanced Recovery Companion-app hebt geopend.</span><span class="sxs-lookup"><span data-stu-id="e41c1-167">While the HoloLens device is running, connect it to the Windows 10 PC where you previously opened the Advanced Recovery Companion app.</span></span>
 
   <span data-ttu-id="e41c1-168">Het apparaat wordt automatisch gedetecteerd en de gebruikersinterface van de Geavanceerde herstel companion-app start het updateproces:</span><span class="sxs-lookup"><span data-stu-id="e41c1-168">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![HoloLens 2 eerste scherm nieuwe reflash maken](images/ARC2.png)

3. <span data-ttu-id="e41c1-170">Selecteer het HoloLens 2 in de gebruikersinterface van de Geavanceerde herstel companion-app en volg de instructies om de reflash te voltooien.</span><span class="sxs-lookup"><span data-stu-id="e41c1-170">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and follow the instructions to complete the reflash.</span></span>

### <a name="manual-procedure"></a><span data-ttu-id="e41c1-171">Handmatige procedure</span><span class="sxs-lookup"><span data-stu-id="e41c1-171">Manual procedure</span></span>

<span data-ttu-id="e41c1-172">Als de HoloLens 2 niet correct wordt start of als Advanced Recovery Companion het apparaat niet kan detecteren, moet u het apparaat mogelijk in de herstelmodus zetten:</span><span class="sxs-lookup"><span data-stu-id="e41c1-172">If the HoloLens 2 doesn't start correctly or if Advanced Recovery Companion cannot detect the device, you may need to put the device into recovery mode:</span></span>

1. <span data-ttu-id="e41c1-173">Koppel de Type-C-kabel los om het apparaat los te koppelen van de voeding of de host-pc.</span><span class="sxs-lookup"><span data-stu-id="e41c1-173">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="e41c1-174">Houd de **aan/uit-knop** 15 seconden ingedrukt.</span><span class="sxs-lookup"><span data-stu-id="e41c1-174">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="e41c1-175">Alle LED's moeten worden uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="e41c1-175">All LEDs should turn off.</span></span>

3. <span data-ttu-id="e41c1-176">Druk terwijl u **op de volumeknop omhoog** drukt op de **aan/uit-knop** om het apparaat te starten.</span><span class="sxs-lookup"><span data-stu-id="e41c1-176">While pressing the **volume up** button, press and release the **power** button to start the device.</span></span> <span data-ttu-id="e41c1-177">Wacht 15 seconden en laat het **volume vervolgens los.**</span><span class="sxs-lookup"><span data-stu-id="e41c1-177">Wait 15 seconds, and then release the **volume up** button.</span></span> <span data-ttu-id="e41c1-178">Alleen de middelste LED van de vijf LED's wordt licht licht.</span><span class="sxs-lookup"><span data-stu-id="e41c1-178">Only the middle LED of the five LEDs will light up.</span></span>

4. <span data-ttu-id="e41c1-179">Verbind het apparaat met de host-pc en open Apparaatbeheer.</span><span class="sxs-lookup"><span data-stu-id="e41c1-179">Connect the device to the host PC, and open Device Manager.</span></span> <span data-ttu-id="e41c1-180">(Voor Windows 10 op **de Windows-toets** en vervolgens op **de X-toets** en selecteer vervolgens **Apparaatbeheer**.) Zorg ervoor dat het apparaat op de juiste manier Microsoft HoloLens zoals wordt weergegeven in de volgende afbeelding:</span><span class="sxs-lookup"><span data-stu-id="e41c1-180">(For Windows 10 press the **Windows** key, and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as Microsoft HoloLens as shown in the following image:</span></span>

   ![HoloLens 2 Microsoft HolooLensRecovery](images/MicrosoftHoloLensRecovery.png)

   <span data-ttu-id="e41c1-182">Het apparaat wordt automatisch gedetecteerd en de gebruikersinterface van de Geavanceerde herstel companion-app start het updateproces:</span><span class="sxs-lookup"><span data-stu-id="e41c1-182">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![HoloLens 2 reflash-scherm maken](images/ARC2.png)

6. <span data-ttu-id="e41c1-184">Selecteer het HoloLens 2 in de gebruikersinterface van de Geavanceerde herstel companion-app en volg de instructies om de reflash te voltooien.</span><span class="sxs-lookup"><span data-stu-id="e41c1-184">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and then follow the instructions to complete the reflash.</span></span>

## <a name="troubleshoot-advanced-recovery-companion"></a><span data-ttu-id="e41c1-185">Problemen met geavanceerde herstel-companion oplossen</span><span class="sxs-lookup"><span data-stu-id="e41c1-185">Troubleshoot Advanced Recovery Companion</span></span>

1. <span data-ttu-id="e41c1-186">Zorg ervoor dat er voor uw apparaat 40% of meer in rekening wordt gebracht voordat u een flash-poging doet.</span><span class="sxs-lookup"><span data-stu-id="e41c1-186">Ensure your device is charged to 40% or more before attempting to flash.</span></span>

2. <span data-ttu-id="e41c1-187">Controleer of uw apparaat is ontgrendeld.</span><span class="sxs-lookup"><span data-stu-id="e41c1-187">Check that your device is unlocked.</span></span>

3. <span data-ttu-id="e41c1-188">Als ARC uw apparaat niet detecteert, controleert u of u verbinding kunt maken met uw apparaat via Verkenner op uw pc.</span><span class="sxs-lookup"><span data-stu-id="e41c1-188">If ARC does not detect your device, ensure that you can connect to your device via File Explorer on your PC.</span></span> <span data-ttu-id="e41c1-189">Als dat niet mogelijk is,</span><span class="sxs-lookup"><span data-stu-id="e41c1-189">If you cannot;</span></span>

    1.  <span data-ttu-id="e41c1-190">Het is mogelijk dat uw apparaat USB-beleidsregels heeft die die verbinding uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="e41c1-190">It is possible that your device may have USB policies that disable that connection.</span></span> <span data-ttu-id="e41c1-191">Probeer in dat opzicht [handmatige knippermodus](hololens-recovery.md#manual-procedure)uit.</span><span class="sxs-lookup"><span data-stu-id="e41c1-191">If so, try [Manual Flashing mode](hololens-recovery.md#manual-procedure).</span></span>
    2.  <span data-ttu-id="e41c1-192">Als er geen beleidsregels zijn, probeert u een andere USB-kabel.</span><span class="sxs-lookup"><span data-stu-id="e41c1-192">If there are no policies, try a different USB cable.</span></span>

1. <span data-ttu-id="e41c1-193">Controleer of op uw apparaat geen [1-3-5-LED-patroon wordt weergegeven.](hololens2-setup.md#lights-to-indicate-problems)</span><span class="sxs-lookup"><span data-stu-id="e41c1-193">Check that your device doesn't display a [1-3-5-LED pattern](hololens2-setup.md#lights-to-indicate-problems).</span></span>

## <a name="download-arc-without-using-the-app-store"></a><span data-ttu-id="e41c1-194">ARC downloaden zonder de App Store te gebruiken</span><span class="sxs-lookup"><span data-stu-id="e41c1-194">Download ARC without using the app store</span></span>

<span data-ttu-id="e41c1-195">Als de IT-omgeving het gebruik van de Windows Store-app voorkomt of de toegang tot de winkel beperkt, kan de IT-beheerder deze app beschikbaar maken via een 'offline' implementatiepad.</span><span class="sxs-lookup"><span data-stu-id="e41c1-195">If the IT environment prevents the use of the Windows Store app or limits access to the retail store, the IT administrator can make this app available through an "offline" deployment path.</span></span>

 >[!NOTE]
 > - <span data-ttu-id="e41c1-196">IT-beheerders kunnen deze app ook distribueren via System Center Configuration Manager (SCCM) of Intune.</span><span class="sxs-lookup"><span data-stu-id="e41c1-196">IT administrators can also distribute this app through System Center Configuration Manager (SCCM) or Intune.</span></span>
 > - <span data-ttu-id="e41c1-197">Deze handleiding is gericht op Advanced Recovery Companion, maar het proces kan ook worden gebruikt voor andere offline-apps.</span><span class="sxs-lookup"><span data-stu-id="e41c1-197">This guide focuses on Advanced Recovery Companion, but the process can also be used for other "offline" apps.</span></span>

<span data-ttu-id="e41c1-198">Volg deze stappen om het implementatiepad in te stellen:</span><span class="sxs-lookup"><span data-stu-id="e41c1-198">Follow these steps to enable the deployment path:</span></span>

1. <span data-ttu-id="e41c1-199">Ga naar de [Microsoft Store voor Bedrijven](https://businessstore.microsoft.com) en meld u aan met een Azure Active Directory identiteit.</span><span class="sxs-lookup"><span data-stu-id="e41c1-199">Go to the [Microsoft Store for Business](https://businessstore.microsoft.com) and sign in using an Azure Active Directory identity.</span></span>

1. <span data-ttu-id="e41c1-200">Ga naar **Beheren – Instellingen**.</span><span class="sxs-lookup"><span data-stu-id="e41c1-200">Go to **Manage – Settings**.</span></span> <span data-ttu-id="e41c1-201">Schakel **Offline-apps tonen in** onder **Winkelervaring.**</span><span class="sxs-lookup"><span data-stu-id="e41c1-201">Turn on **Show offline apps** under **Shopping experience**.</span></span>

1. <span data-ttu-id="e41c1-202">Ga naar **de winkel voor mijn groep en** zoek naar Advanced Recovery [**_Companion_**](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).</span><span class="sxs-lookup"><span data-stu-id="e41c1-202">Go to **shop for my group**, and search for [**_Advanced Recovery Companion_**](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).</span></span>

1. <span data-ttu-id="e41c1-203">Wijzig het **licentietype** in **_offline_*_, en selecteer _\* Beheren.*\*</span><span class="sxs-lookup"><span data-stu-id="e41c1-203">Change the **License Type** to \**_offline_*_, and select _\* Manage\*\*.</span></span>

1. <span data-ttu-id="e41c1-204">Selecteer **onder Het pakket downloaden voor offlinegebruik** de tweede blauwe knop **Downloaden.**</span><span class="sxs-lookup"><span data-stu-id="e41c1-204">Under **Download the package for offline use**, select the second blue **Download** button.</span></span> <span data-ttu-id="e41c1-205">Zorg ervoor dat de bestandsextensie *.appxbundle is.*</span><span class="sxs-lookup"><span data-stu-id="e41c1-205">Make sure that the file extension is *.appxbundle*.</span></span>

    - <span data-ttu-id="e41c1-206">Als de desktop-pc in dit stadium internettoegang heeft, dubbelklikt u op het pakket om de app te installeren.</span><span class="sxs-lookup"><span data-stu-id="e41c1-206">At this stage, if the Desktop PC has internet access, double-click the package to install the app.</span></span>

    - <span data-ttu-id="e41c1-207">Als de doel-pc geen internetverbinding heeft, volgt u deze stappen:</span><span class="sxs-lookup"><span data-stu-id="e41c1-207">If the destination PC has no internet connectivity, follow these steps:</span></span>
       1. <span data-ttu-id="e41c1-208">Selecteer de niet-gecodeerde licentie en selecteer vervolgens **Licentie genereren.**</span><span class="sxs-lookup"><span data-stu-id="e41c1-208">Select the unencoded license, and then select **Generate license**.</span></span>
       2. <span data-ttu-id="e41c1-209">Selecteer **onder Vereiste frameworks** de optie **Downloaden.**</span><span class="sxs-lookup"><span data-stu-id="e41c1-209">Under **Required Frameworks**, select **Download**.</span></span>
       3. <span data-ttu-id="e41c1-210">Gebruik DISM om het pakket toe te passen met de afhankelijkheid en licentie.</span><span class="sxs-lookup"><span data-stu-id="e41c1-210">Use DISM to apply the package with the dependency and license.</span></span> <span data-ttu-id="e41c1-211">Voer vanaf een opdrachtprompt van de beheerder de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="e41c1-211">From an administrator command prompt, run the following command:</span></span>

          ```console
          C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
          ```
          > [!NOTE]
          > <span data-ttu-id="e41c1-212">Het versienummer in dit codevoorbeeld komt mogelijk niet overeen met de momenteel beschikbare versie.</span><span class="sxs-lookup"><span data-stu-id="e41c1-212">The version number in this code example may not match the currently available version.</span></span> <span data-ttu-id="e41c1-213">Mogelijk hebt u ook een andere downloadlocatie gekozen dan in het voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="e41c1-213">You may have also chosen a different download location than in the example.</span></span> <span data-ttu-id="e41c1-214">Wijzig de opdracht naar behoefte.</span><span class="sxs-lookup"><span data-stu-id="e41c1-214">Make any changes to the command as needed.</span></span>

> [!TIP]
> <span data-ttu-id="e41c1-215">Wanneer u van plan bent Advanced Recovery Companion te gebruiken om een FFU offline te installeren, kan het handig zijn om uw flash-installatie afbeelding te downloaden.</span><span class="sxs-lookup"><span data-stu-id="e41c1-215">When you plan to use Advanced Recovery Companion to install an FFU offline, it may be useful to download your flash image.</span></span> <span data-ttu-id="e41c1-216">[**Download de huidige afbeelding voor HoloLens 2**](https://aka.ms/hololens2download).</span><span class="sxs-lookup"><span data-stu-id="e41c1-216">[**Download the current image for HoloLens 2**](https://aka.ms/hololens2download).</span></span>


<span data-ttu-id="e41c1-217">Andere resources:</span><span class="sxs-lookup"><span data-stu-id="e41c1-217">Other resources:</span></span>
- [<span data-ttu-id="e41c1-218">Offline-apps distribueren</span><span class="sxs-lookup"><span data-stu-id="e41c1-218">Distribute offline apps</span></span>](/microsoft-store/distribute-offline-apps) 
- [<span data-ttu-id="e41c1-219">Service-opdrachtregelopties voor DISM-app-pakket (.appx of .appxbundle)</span><span class="sxs-lookup"><span data-stu-id="e41c1-219">DISM app package (.appx or .appxbundle) servicing command-line options</span></span>](/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options)
