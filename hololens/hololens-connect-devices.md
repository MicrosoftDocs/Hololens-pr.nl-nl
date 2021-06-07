---
title: Verbinding maken met Bluetooth- en USB-C-apparaten
description: Maak verbinding met Bluetooth- en USB-C-apparaten en -accessoires vanaf uw HoloLens-mixed reality apparaten.
ms.assetid: 01af0848-3b36-4c13-b797-f38ad3977e30
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.localizationpriority: high
ms.date: 03/11/2020
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ffae65a6e1c096242ae7a28c488896c65df1c62d
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/25/2021
ms.locfileid: "111379443"
---
# <a name="connect-to-bluetooth-and-usb-c-devices"></a><span data-ttu-id="ce502-103">Verbinding maken met Bluetooth- en USB-C-apparaten</span><span class="sxs-lookup"><span data-stu-id="ce502-103">Connect to Bluetooth and USB-C devices</span></span>

## <a name="pair-bluetooth-devices"></a><span data-ttu-id="ce502-104">Bluetooth-apparaten koppelen</span><span class="sxs-lookup"><span data-stu-id="ce502-104">Pair Bluetooth devices</span></span>

<span data-ttu-id="ce502-105">HoloLens 2 ondersteunt de volgende klassen Bluetooth-apparaten:</span><span class="sxs-lookup"><span data-stu-id="ce502-105">HoloLens 2 supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="ce502-106">[VERBORGEN:](https://docs.microsoft.com/windows-hardware/drivers/hid/)</span><span class="sxs-lookup"><span data-stu-id="ce502-106">[HID](https://docs.microsoft.com/windows-hardware/drivers/hid/):</span></span>
    - <span data-ttu-id="ce502-107">Muis</span><span class="sxs-lookup"><span data-stu-id="ce502-107">Mouse</span></span>
    - <span data-ttu-id="ce502-108">Toetsenbord</span><span class="sxs-lookup"><span data-stu-id="ce502-108">Keyboard</span></span>
- <span data-ttu-id="ce502-109">Audio-uitvoerapparaten (A2DP)</span><span class="sxs-lookup"><span data-stu-id="ce502-109">Audio output (A2DP) devices</span></span>

<span data-ttu-id="ce502-110">HoloLens 2 ondersteunt de volgende Bluetooth-API's:</span><span class="sxs-lookup"><span data-stu-id="ce502-110">HoloLens 2 supports the following Bluetooth APIs:</span></span>
- <span data-ttu-id="ce502-111">[GATT-server](https://docs.microsoft.com/windows/uwp/devices-sensors/gatt-server) en [-client](https://docs.microsoft.com/windows/uwp/devices-sensors/gatt-client)</span><span class="sxs-lookup"><span data-stu-id="ce502-111">GATT [Server](https://docs.microsoft.com/windows/uwp/devices-sensors/gatt-server) and [Client](https://docs.microsoft.com/windows/uwp/devices-sensors/gatt-client)</span></span>
- [<span data-ttu-id="ce502-112">Rfcomm</span><span class="sxs-lookup"><span data-stu-id="ce502-112">RFCOMM</span></span>](https://docs.microsoft.com/windows/uwp/devices-sensors/send-or-receive-files-with-rfcomm)
>[!IMPORTANT]
> <span data-ttu-id="ce502-113">Mogelijk moet u bijbehorende companion-apps installeren vanuit Microsoft Store om de APPARATEN VAN HET PROGRAMMA en de GATT daadwerkelijk te kunnen gebruiken.</span><span class="sxs-lookup"><span data-stu-id="ce502-113">You may have to install corresponding companion apps from Microsoft Store to actually use the HID and GATT devices.</span></span>

<span data-ttu-id="ce502-114">HoloLens (1e generatie) ondersteunt de volgende klassen Bluetooth-apparaten:</span><span class="sxs-lookup"><span data-stu-id="ce502-114">HoloLens (1st gen) supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="ce502-115">Muis</span><span class="sxs-lookup"><span data-stu-id="ce502-115">Mouse</span></span>
- <span data-ttu-id="ce502-116">Toetsenbord</span><span class="sxs-lookup"><span data-stu-id="ce502-116">Keyboard</span></span>
- [<span data-ttu-id="ce502-117">Klik op HoloLens (1e generatie)</span><span class="sxs-lookup"><span data-stu-id="ce502-117">HoloLens (1st gen) clicker</span></span>](https://docs.microsoft.com/hololens/hololens1-clicker)

> [!NOTE]
> <span data-ttu-id="ce502-118">Andere soorten Bluetooth-apparaten, zoals sprekers, headsets, smartphones en gamepads, kunnen worden vermeld als beschikbaar in HoloLens-instellingen.</span><span class="sxs-lookup"><span data-stu-id="ce502-118">Other types of Bluetooth devices, such as speakers, headsets, smartphones, and game pads, may be listed as available in HoloLens settings.</span></span> <span data-ttu-id="ce502-119">Deze apparaten worden echter niet ondersteund op HoloLens (eerste generatie).</span><span class="sxs-lookup"><span data-stu-id="ce502-119">However, these devices aren't supported on HoloLens (1st gen).</span></span> <span data-ttu-id="ce502-120">Zie [HoloLens Settings lists devices as available (HoloLens-instellingen)](hololens-FAQ.md#hololens-settings-lists-devices-as-available-but-the-devices-dont-work)als beschikbaar, maar de apparaten werken niet.</span><span class="sxs-lookup"><span data-stu-id="ce502-120">For more information, see [HoloLens Settings lists devices as available, but the devices don't work](hololens-FAQ.md#hololens-settings-lists-devices-as-available-but-the-devices-dont-work).</span></span>

### <a name="pair-a-bluetooth-keyboard-or-mouse"></a><span data-ttu-id="ce502-121">Een Bluetooth-toetsenbord of -muis koppelen</span><span class="sxs-lookup"><span data-stu-id="ce502-121">Pair a Bluetooth keyboard or mouse</span></span>

1. <span data-ttu-id="ce502-122">Schakel uw toetsenbord of muis in en maak het detecteerbaar.</span><span class="sxs-lookup"><span data-stu-id="ce502-122">Turn on your keyboard or mouse, and make it discoverable.</span></span> <span data-ttu-id="ce502-123">Als u wilt weten hoe u het apparaat detecteerbaar maakt, gaat u naar informatie over het apparaat (of de documentatie) of gaat u naar de website van de fabrikant.</span><span class="sxs-lookup"><span data-stu-id="ce502-123">To learn how to make the device discoverable, look for information on the device (or its documentation) or visit the manufacturer's website.</span></span>

1. <span data-ttu-id="ce502-124">Gebruik de bloembewegingen (HoloLens (1e generatie)) of het beginbewegingen (HoloLens 2) om naar **Start** te gaan en selecteer vervolgens **Instellingen**.</span><span class="sxs-lookup"><span data-stu-id="ce502-124">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings**.</span></span>

1. <span data-ttu-id="ce502-125">Selecteer **Apparaten** en zorg ervoor dat Bluetooth is aan.</span><span class="sxs-lookup"><span data-stu-id="ce502-125">Select **Devices**, and make sure that Bluetooth is on.</span></span>  

1. <span data-ttu-id="ce502-126">Wanneer u de apparaatnaam ziet, selecteert **u Koppelen** en volgt u de instructies.</span><span class="sxs-lookup"><span data-stu-id="ce502-126">When you see the device name, select **Pair**, and then follow the instructions.</span></span>

## <a name="disable-bluetooth"></a><span data-ttu-id="ce502-127">Bluetooth uitschakelen</span><span class="sxs-lookup"><span data-stu-id="ce502-127">Disable Bluetooth</span></span>

<span data-ttu-id="ce502-128">Met deze procedure worden de RF-onderdelen van het Bluetooth-radioprogramma uitgeschakeld en wordt alle Bluetooth-functionaliteit op de Microsoft HoloLens.</span><span class="sxs-lookup"><span data-stu-id="ce502-128">This procedure turns off the RF components of the Bluetooth radio and disables all Bluetooth functionality on Microsoft HoloLens.</span></span>

1. <span data-ttu-id="ce502-129">Gebruik de bloembewegingen (HoloLens (1e generatie)) of de beginbewegingen (HoloLens 2) om naar **Start** te gaan en selecteer vervolgens  >  **Instellingen Apparaten.**</span><span class="sxs-lookup"><span data-stu-id="ce502-129">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings** > **Devices**.</span></span>

1. <span data-ttu-id="ce502-130">Verplaats de schuifregelaar voor **Bluetooth naar** de **uit-positie.**</span><span class="sxs-lookup"><span data-stu-id="ce502-130">Move the slider switch for **Bluetooth** to the **Off** position.</span></span>

## <a name="hololens-2-connect-usb-c-devices"></a><span data-ttu-id="ce502-131">HoloLens 2: USB-C-apparaten verbinden</span><span class="sxs-lookup"><span data-stu-id="ce502-131">HoloLens 2: Connect USB-C devices</span></span>

<span data-ttu-id="ce502-132">HoloLens 2 ondersteunt de volgende klassen USB-C-apparaten:</span><span class="sxs-lookup"><span data-stu-id="ce502-132">HoloLens 2 supports the following classes of USB-C devices:</span></span>

- <span data-ttu-id="ce502-133">Apparaten voor massaopslag (zoals vingerafdrukstations)</span><span class="sxs-lookup"><span data-stu-id="ce502-133">Mass storage devices (such as thumb drives)</span></span>
- <span data-ttu-id="ce502-134">Ethernet-adapters (inclusief ethernet en laadtijd)</span><span class="sxs-lookup"><span data-stu-id="ce502-134">Ethernet adapters (including ethernet plus charging)</span></span>
- <span data-ttu-id="ce502-135">Digitale USB-C-naar-3,5mm-audioadapters</span><span class="sxs-lookup"><span data-stu-id="ce502-135">USB-C-to-3.5mm digital audio adapters</span></span>
- <span data-ttu-id="ce502-136">Digitale USB-C-audio-headsets (inclusief headsetadapters plus laden)</span><span class="sxs-lookup"><span data-stu-id="ce502-136">USB-C digital audio headsets (including headset adapters plus charging)</span></span>
- <span data-ttu-id="ce502-137">Externe USB-C-microfoons[(Windows Holographic, versie 21H1](hololens-release-notes.md#windows-holographic-version-21h1) en hoger)</span><span class="sxs-lookup"><span data-stu-id="ce502-137">USB-C External Microphones ([Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) and higher)</span></span>
- <span data-ttu-id="ce502-138">Bekabelde muis</span><span class="sxs-lookup"><span data-stu-id="ce502-138">Wired mouse</span></span>
- <span data-ttu-id="ce502-139">Bekabeld toetsenbord</span><span class="sxs-lookup"><span data-stu-id="ce502-139">Wired keyboard</span></span>
- <span data-ttu-id="ce502-140">Combinatie van PD-hubs (USB A plus PD-kosten)</span><span class="sxs-lookup"><span data-stu-id="ce502-140">Combination PD hubs (USB A plus PD charging)</span></span>


> [!NOTE]
> <span data-ttu-id="ce502-141">Als reactie op feedback van klanten hebben we beperkte ondersteuning ingeschakeld voor mobiele connectiviteit die rechtstreeks aan de HoloLens is verbonden via USB-C.</span><span class="sxs-lookup"><span data-stu-id="ce502-141">In response to customer feedback, we have enabled limited support for cellular connectivity tethered directly to the HoloLens via USB-C.</span></span> <span data-ttu-id="ce502-142">Zie [Verbinding maken met mobiel en 5G](hololens-cellular.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="ce502-142">See [Connect to Cellular and 5G](hololens-cellular.md) for more information.</span></span>

### <a name="usb-c-external-microphone-support"></a><span data-ttu-id="ce502-143">Ondersteuning voor externe USB-C-microfoon</span><span class="sxs-lookup"><span data-stu-id="ce502-143">USB-C External Microphone Support</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ce502-144">Als u een **USB-microfoon aansluit, wordt deze niet automatisch ingesteld als invoerapparaat.**</span><span class="sxs-lookup"><span data-stu-id="ce502-144">Plugging in **a USB mic will not automatically set it as the input device**.</span></span> <span data-ttu-id="ce502-145">Bij het aansluiten van een set USB-C-headsets zien gebruikers dat de audio van de microfoon automatisch wordt omgeleid naar de laptop, maar het HoloLens-besturingssysteem geeft prioriteit aan de interne microfoon array boven elk ander invoerapparaat.</span><span class="sxs-lookup"><span data-stu-id="ce502-145">When plugging in a set of USB-C headphones, users will observe that the headphone's audio will automatically be redirected to the headphones, but the HoloLens OS prioritizes the internal microphone array above any other input device.</span></span> <span data-ttu-id="ce502-146">**Volg de onderstaande stappen om een USB-C-microfoon te gebruiken.**</span><span class="sxs-lookup"><span data-stu-id="ce502-146">**In order to use a USB-C microphone follow the steps below.**</span></span>

> [!NOTE]
> <span data-ttu-id="ce502-147">Externe microfoons kunnen niet worden gebruikt in builds vóór [Windows Holographic, versie 21H1](hololens-release-notes.md#windows-holographic-version-21h1) en hoger.</span><span class="sxs-lookup"><span data-stu-id="ce502-147">External microphones cannot be used in builds prior to [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) and higher.</span></span> 

<span data-ttu-id="ce502-148">Gebruikers kunnen externe usb-C-microfoons selecteren met behulp van het **instellingenpaneel** Geluid.</span><span class="sxs-lookup"><span data-stu-id="ce502-148">Users can select USB-C connected external microphones using the **Sound** settings panel.</span></span> <span data-ttu-id="ce502-149">USB-C-microfoons kunnen worden gebruikt voor het aanroepen, opnemen, enzovoort.</span><span class="sxs-lookup"><span data-stu-id="ce502-149">USB-C microphones can be used for calling, recording, etc.</span></span>

<span data-ttu-id="ce502-150">Open de **app Instellingen** en selecteer   >  **Systeemgeluid.**</span><span class="sxs-lookup"><span data-stu-id="ce502-150">Open the **Settings** app and select **System** > **Sound**.</span></span>

![Geluidsinstellingen](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> <span data-ttu-id="ce502-152">Als u externe microfoons wilt **gebruiken Remote Assist,** moeten gebruikers op de hyperlink Geluidsapparaten beheren klikken.</span><span class="sxs-lookup"><span data-stu-id="ce502-152">To use external microphones with **Remote Assist**, users will need to click the “Manage sound devices” hyperlink.</span></span>
>
> <span data-ttu-id="ce502-153">Gebruik vervolgens de vervolgkeuzeset om de externe microfoon in te stellen als **Standaardmicrofoon** of **Standaardcommunicatie.**</span><span class="sxs-lookup"><span data-stu-id="ce502-153">Then use the drop-down to set the external microphone as either **Default** or **Communications Default.**</span></span> <span data-ttu-id="ce502-154">Als **u Standaard** kiest, wordt de externe microfoon overal gebruikt.</span><span class="sxs-lookup"><span data-stu-id="ce502-154">Choosing **Default** means that the external microphone will be used everywhere.</span></span>
>
> <span data-ttu-id="ce502-155">Als **u Standaardcommunicatie** kiest, wordt de externe microfoon gebruikt in Remote Assist en andere communicatie-apps, maar kan de HoloLens-microfoon nog steeds worden gebruikt voor andere taken.</span><span class="sxs-lookup"><span data-stu-id="ce502-155">Choosing **Communications Default** means that the external microphone will be used in Remote Assist and other communications apps, but the HoloLens mic array may still be used for other tasks.</span></span>

![Geluidsapparaten beheren](images/usbc-mic-2.png)

<br>

![Standaardmicrofoon instellen](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a><span data-ttu-id="ce502-158">Hoe zit het met ondersteuning voor Bluetooth-microfoons?</span><span class="sxs-lookup"><span data-stu-id="ce502-158">What about Bluetooth microphone support?</span></span>

<span data-ttu-id="ce502-159">Helaas worden Bluetooth-microfoons momenteel nog niet ondersteund op HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="ce502-159">Unfortunately, Bluetooth microphones are still not currently supported on HoloLens 2.</span></span>

#### <a name="troubleshooting-usb-c-microphones"></a><span data-ttu-id="ce502-160">Problemen met USB-C-microfoons oplossen</span><span class="sxs-lookup"><span data-stu-id="ce502-160">Troubleshooting USB-C microphones</span></span>

<span data-ttu-id="ce502-161">Let erop dat sommige USB-C-microfoons zich onjuist melden als zowel een microfoon *als* een spreker.</span><span class="sxs-lookup"><span data-stu-id="ce502-161">Be aware that some USB-C microphones incorrectly report themselves as both a microphone *and* a speaker.</span></span> <span data-ttu-id="ce502-162">Dit is een probleem met de microfoon en niet met HoloLens.</span><span class="sxs-lookup"><span data-stu-id="ce502-162">This is a problem with the microphone and not with HoloLens.</span></span> <span data-ttu-id="ce502-163">Wanneer u een van deze microfoons op HoloLens aangesloten, gaat het geluid mogelijk verloren.</span><span class="sxs-lookup"><span data-stu-id="ce502-163">When plugging one of these microphones into HoloLens, sound may be lost.</span></span> <span data-ttu-id="ce502-164">Gelukkig is er een eenvoudige oplossing.</span><span class="sxs-lookup"><span data-stu-id="ce502-164">Fortunately there is a simple fix.</span></span>  

<span data-ttu-id="ce502-165">Stel **in**  ->    ->  **Systeemgeluid van** instellingen expliciet de ingebouwde sprekers **(Analog Feature Audio Driver)** in als **het standaardapparaat.**</span><span class="sxs-lookup"><span data-stu-id="ce502-165">In **Settings** -> **System** -> **Sound**, explicitly set the built-in speakers **(Analog Feature Audio Driver)** as the **Default device**.</span></span> <span data-ttu-id="ce502-166">HoloLens moet deze instelling onthouden, zelfs als de microfoon wordt verwijderd en later opnieuw wordt verbonden.</span><span class="sxs-lookup"><span data-stu-id="ce502-166">HoloLens should remember this setting even if the microphone is removed and reconnected later.</span></span>

![Problemen met USB-C-microfoons oplossen](images/usbc-mic-4.png)
### <a name="usb-c-hubs"></a><span data-ttu-id="ce502-168">USB-C Hubs</span><span class="sxs-lookup"><span data-stu-id="ce502-168">USB-C Hubs</span></span>

<span data-ttu-id="ce502-169">Sommige gebruikers moeten mogelijk meerdere apparaten tegelijk verbinden.</span><span class="sxs-lookup"><span data-stu-id="ce502-169">Some users may need to connect multiple devices at once.</span></span> <span data-ttu-id="ce502-170">Voor gebruikers die een [USB-C-microfoon](#usb-c-external-microphone-support) en een ander aangesloten apparaat willen gebruiken, kunnen USB-C-hubs aan de behoeften van de klant worden gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="ce502-170">For users who would like to use a [USB-C microphone](#usb-c-external-microphone-support) along with another connected device, USB-C hubs may fit the customer's need.</span></span> <span data-ttu-id="ce502-171">Microsoft heeft deze apparaten niet getest en we kunnen ook geen specifieke merken aanbevelen.</span><span class="sxs-lookup"><span data-stu-id="ce502-171">Microsoft has not tested these devices, nor can we recommend any specific brands.</span></span>

<span data-ttu-id="ce502-172">**Vereisten voor USB-C-hub en verbonden apparaten:**</span><span class="sxs-lookup"><span data-stu-id="ce502-172">**Requirements for USB-C hub and connected devices:**</span></span>

- <span data-ttu-id="ce502-173">Voor verbonden apparaten mag geen stuurprogramma zijn geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="ce502-173">Connected devices must not require a driver to be installed.</span></span>
- <span data-ttu-id="ce502-174">Het totale vermogen van alle verbonden apparaten moet lager zijn dan 4,5 Watt.</span><span class="sxs-lookup"><span data-stu-id="ce502-174">The total power draw of all connected devices must be below 4.5 Watts.</span></span>

## <a name="connect-to-miracast"></a><span data-ttu-id="ce502-175">Verbinding maken met Miracast</span><span class="sxs-lookup"><span data-stu-id="ce502-175">Connect to Miracast</span></span>

<span data-ttu-id="ce502-176">Volg deze stappen om Miracast te gebruiken:</span><span class="sxs-lookup"><span data-stu-id="ce502-176">To use Miracast, follow these steps:</span></span>

1. <span data-ttu-id="ce502-177">Voer een van de volgende handelingen uit:</span><span class="sxs-lookup"><span data-stu-id="ce502-177">Do one of the following:</span></span>  

   - <span data-ttu-id="ce502-178">Open het **menu Start** en selecteer het **pictogram** Weergeven.</span><span class="sxs-lookup"><span data-stu-id="ce502-178">Open the **Start** menu, and select the **Display** icon.</span></span>
   - <span data-ttu-id="ce502-179">Zeg 'Verbinding maken' terwijl u naar het **menu Start kijkt.**</span><span class="sxs-lookup"><span data-stu-id="ce502-179">Say "Connect" while you gaze at the **Start** menu.</span></span>  

1. <span data-ttu-id="ce502-180">Selecteer een beschikbaar apparaat in de lijst met apparaten die wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="ce502-180">On the list of devices that appears, select an available device.</span></span>

1. <span data-ttu-id="ce502-181">Voltooi de koppeling om te beginnen met projecteren.</span><span class="sxs-lookup"><span data-stu-id="ce502-181">Complete the pairing to begin projecting.</span></span>
