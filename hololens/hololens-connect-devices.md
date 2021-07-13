---
title: Verbinding maken voor Bluetooth USB-C-apparaten
description: Maak verbinding met uw Bluetooth USB-C-apparaten en -accessoires van uw HoloLens mixed reality apparaten.
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
ms.openlocfilehash: 5fed56d7a0beeda0a0d96eddc63aaee872f3e52d
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639094"
---
# <a name="connect-to-bluetooth-and-usb-c-devices"></a><span data-ttu-id="f25f2-103">Verbinding maken voor Bluetooth USB-C-apparaten</span><span class="sxs-lookup"><span data-stu-id="f25f2-103">Connect to Bluetooth and USB-C devices</span></span>

## <a name="pair-bluetooth-devices"></a><span data-ttu-id="f25f2-104">Apparaten Bluetooth koppelen</span><span class="sxs-lookup"><span data-stu-id="f25f2-104">Pair Bluetooth devices</span></span>

<span data-ttu-id="f25f2-105">HoloLens 2 ondersteunt de volgende klassen van Bluetooth apparaten:</span><span class="sxs-lookup"><span data-stu-id="f25f2-105">HoloLens 2 supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="f25f2-106">[HADOEEN:](/windows-hardware/drivers/hid/)</span><span class="sxs-lookup"><span data-stu-id="f25f2-106">[HID](/windows-hardware/drivers/hid/):</span></span>
    - <span data-ttu-id="f25f2-107">Muis</span><span class="sxs-lookup"><span data-stu-id="f25f2-107">Mouse</span></span>
    - <span data-ttu-id="f25f2-108">Toetsenbord</span><span class="sxs-lookup"><span data-stu-id="f25f2-108">Keyboard</span></span>
- <span data-ttu-id="f25f2-109">Audio-uitvoerapparaten (A2DP)</span><span class="sxs-lookup"><span data-stu-id="f25f2-109">Audio output (A2DP) devices</span></span>

<span data-ttu-id="f25f2-110">HoloLens 2 ondersteunt de volgende Bluetooth API's:</span><span class="sxs-lookup"><span data-stu-id="f25f2-110">HoloLens 2 supports the following Bluetooth APIs:</span></span>
- <span data-ttu-id="f25f2-111">[GATT-server](/windows/uwp/devices-sensors/gatt-server) en [-client](/windows/uwp/devices-sensors/gatt-client)</span><span class="sxs-lookup"><span data-stu-id="f25f2-111">GATT [Server](/windows/uwp/devices-sensors/gatt-server) and [Client](/windows/uwp/devices-sensors/gatt-client)</span></span>
- [<span data-ttu-id="f25f2-112">Rfcomm</span><span class="sxs-lookup"><span data-stu-id="f25f2-112">RFCOMM</span></span>](/windows/uwp/devices-sensors/send-or-receive-files-with-rfcomm)
>[!IMPORTANT]
> <span data-ttu-id="f25f2-113">Mogelijk moet u bijbehorende companion-apps installeren vanuit Microsoft Store om daadwerkelijk gebruik te kunnen maken van de APPARATEN VAN HET PROGRAMMA en de GATT.</span><span class="sxs-lookup"><span data-stu-id="f25f2-113">You may have to install corresponding companion apps from Microsoft Store to actually use the HID and GATT devices.</span></span>

<span data-ttu-id="f25f2-114">HoloLens (eerste generatie) ondersteunt de volgende klassen van Bluetooth apparaten:</span><span class="sxs-lookup"><span data-stu-id="f25f2-114">HoloLens (1st gen) supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="f25f2-115">Muis</span><span class="sxs-lookup"><span data-stu-id="f25f2-115">Mouse</span></span>
- <span data-ttu-id="f25f2-116">Toetsenbord</span><span class="sxs-lookup"><span data-stu-id="f25f2-116">Keyboard</span></span>
- [<span data-ttu-id="f25f2-117">HoloLens (eerste generatie) clicker</span><span class="sxs-lookup"><span data-stu-id="f25f2-117">HoloLens (1st gen) clicker</span></span>](hololens1-clicker.md)

> [!NOTE]
> <span data-ttu-id="f25f2-118">Andere typen Bluetooth apparaten, zoals sprekers, headsets, smartphones en gamepads, kunnen worden vermeld als beschikbaar in HoloLens instellingen.</span><span class="sxs-lookup"><span data-stu-id="f25f2-118">Other types of Bluetooth devices, such as speakers, headsets, smartphones, and game pads, may be listed as available in HoloLens settings.</span></span> <span data-ttu-id="f25f2-119">Deze apparaten worden echter niet ondersteund op HoloLens (eerste generatie).</span><span class="sxs-lookup"><span data-stu-id="f25f2-119">However, these devices aren't supported on HoloLens (1st gen).</span></span> <span data-ttu-id="f25f2-120">Zie HoloLens Instellingen [apparaten als beschikbaar,](hololens-troubleshooting.md#devices-listed-as-available-in-settings-dont-work)maar de apparaten werken niet voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="f25f2-120">For more information, see [HoloLens Settings lists devices as available, but the devices don't work](hololens-troubleshooting.md#devices-listed-as-available-in-settings-dont-work).</span></span>

### <a name="pair-a-bluetooth-keyboard-or-mouse"></a><span data-ttu-id="f25f2-121">Een toetsenbord of muis Bluetooth koppelen</span><span class="sxs-lookup"><span data-stu-id="f25f2-121">Pair a Bluetooth keyboard or mouse</span></span>

1. <span data-ttu-id="f25f2-122">Schakel uw toetsenbord of muis in en maak het detecteerbaar.</span><span class="sxs-lookup"><span data-stu-id="f25f2-122">Turn on your keyboard or mouse, and make it discoverable.</span></span> <span data-ttu-id="f25f2-123">Als u wilt weten hoe u het apparaat detecteerbaar kunt maken, gaat u naar informatie op het apparaat (of de documentatie) of gaat u naar de website van de fabrikant.</span><span class="sxs-lookup"><span data-stu-id="f25f2-123">To learn how to make the device discoverable, look for information on the device (or its documentation) or visit the manufacturer's website.</span></span>

1. <span data-ttu-id="f25f2-124">Gebruik het bloembewegingen (HoloLens (eerste generatie)) of het beginbewegingen (HoloLens 2) om naar **Start** te gaan en selecteer vervolgens **Instellingen**.</span><span class="sxs-lookup"><span data-stu-id="f25f2-124">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings**.</span></span>

1. <span data-ttu-id="f25f2-125">Selecteer **Apparaten** en zorg ervoor dat Bluetooth is.</span><span class="sxs-lookup"><span data-stu-id="f25f2-125">Select **Devices**, and make sure that Bluetooth is on.</span></span>  

1. <span data-ttu-id="f25f2-126">Wanneer u de apparaatnaam ziet, selecteert **u Koppelen** en volgt u de instructies.</span><span class="sxs-lookup"><span data-stu-id="f25f2-126">When you see the device name, select **Pair**, and then follow the instructions.</span></span>

## <a name="disable-bluetooth"></a><span data-ttu-id="f25f2-127">Schakel Bluetooth</span><span class="sxs-lookup"><span data-stu-id="f25f2-127">Disable Bluetooth</span></span>

<span data-ttu-id="f25f2-128">Met deze procedure worden de RF-onderdelen van de Bluetooth uitgeschakeld en worden alle Bluetooth uitgeschakeld op Microsoft HoloLens.</span><span class="sxs-lookup"><span data-stu-id="f25f2-128">This procedure turns off the RF components of the Bluetooth radio and disables all Bluetooth functionality on Microsoft HoloLens.</span></span>

1. <span data-ttu-id="f25f2-129">Gebruik de bloembewegingen (HoloLens (eerste generatie)) of het beginbewegingen (HoloLens 2) om naar **Start** te gaan en selecteer vervolgens **Instellingen**  >  **Apparaten.**</span><span class="sxs-lookup"><span data-stu-id="f25f2-129">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings** > **Devices**.</span></span>

1. <span data-ttu-id="f25f2-130">Verplaats de schuifregelaar voor **Bluetooth** naar de **positie Uit.**</span><span class="sxs-lookup"><span data-stu-id="f25f2-130">Move the slider switch for **Bluetooth** to the **Off** position.</span></span>

## <a name="hololens-2-connect-usb-c-devices"></a><span data-ttu-id="f25f2-131">HoloLens 2: Verbinding maken USB-C-apparaten</span><span class="sxs-lookup"><span data-stu-id="f25f2-131">HoloLens 2: Connect USB-C devices</span></span>

<span data-ttu-id="f25f2-132">HoloLens 2 ondersteunt de volgende klassen USB-C-apparaten:</span><span class="sxs-lookup"><span data-stu-id="f25f2-132">HoloLens 2 supports the following classes of USB-C devices:</span></span>

- <span data-ttu-id="f25f2-133">Apparaten voor massaopslag (zoals vingerafdrukstations)</span><span class="sxs-lookup"><span data-stu-id="f25f2-133">Mass storage devices (such as thumb drives)</span></span>
- <span data-ttu-id="f25f2-134">Ethernet-adapters (inclusief ethernet plus laadsnelheid)</span><span class="sxs-lookup"><span data-stu-id="f25f2-134">Ethernet adapters (including ethernet plus charging)</span></span>
- <span data-ttu-id="f25f2-135">Digitale USB-C-naar-3.5mm-audioadapters</span><span class="sxs-lookup"><span data-stu-id="f25f2-135">USB-C-to-3.5mm digital audio adapters</span></span>
- <span data-ttu-id="f25f2-136">Digitale USB-C-audio-headsets (inclusief headsetadapters plus laden)</span><span class="sxs-lookup"><span data-stu-id="f25f2-136">USB-C digital audio headsets (including headset adapters plus charging)</span></span>
- <span data-ttu-id="f25f2-137">Externe USB-C-microfoons[(Windows Holographic, versie 21H1](hololens-release-notes.md#windows-holographic-version-21h1) en hoger)</span><span class="sxs-lookup"><span data-stu-id="f25f2-137">USB-C External Microphones ([Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) and higher)</span></span>
- <span data-ttu-id="f25f2-138">Bekabelde muis</span><span class="sxs-lookup"><span data-stu-id="f25f2-138">Wired mouse</span></span>
- <span data-ttu-id="f25f2-139">Bekabeld toetsenbord</span><span class="sxs-lookup"><span data-stu-id="f25f2-139">Wired keyboard</span></span>
- <span data-ttu-id="f25f2-140">Combinatie van PD-hubs (USB A plus PD-laadtijd)</span><span class="sxs-lookup"><span data-stu-id="f25f2-140">Combination PD hubs (USB A plus PD charging)</span></span>


> [!NOTE]
> <span data-ttu-id="f25f2-141">In reactie op feedback van klanten hebben we beperkte ondersteuning ingeschakeld voor mobiele connectiviteit die rechtstreeks naar de HoloLens via USB-C.</span><span class="sxs-lookup"><span data-stu-id="f25f2-141">In response to customer feedback, we have enabled limited support for cellular connectivity tethered directly to the HoloLens via USB-C.</span></span> <span data-ttu-id="f25f2-142">Zie [Verbinding maken mobiele verbinding en 5G voor](hololens-cellular.md) meer informatie.</span><span class="sxs-lookup"><span data-stu-id="f25f2-142">See [Connect to Cellular and 5G](hololens-cellular.md) for more information.</span></span>

### <a name="usb-c-external-microphone-support"></a><span data-ttu-id="f25f2-143">Ondersteuning voor externe USB-C-microfoon</span><span class="sxs-lookup"><span data-stu-id="f25f2-143">USB-C External Microphone Support</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f25f2-144">Als u een **USB-microfoon aansluit, wordt deze niet automatisch ingesteld als invoerapparaat.**</span><span class="sxs-lookup"><span data-stu-id="f25f2-144">Plugging in **a USB mic will not automatically set it as the input device**.</span></span> <span data-ttu-id="f25f2-145">Bij het aansluiten van een set USB-C-hoofdtelefoon zien gebruikers dat de audio van de hoofdtelefoon automatisch wordt omgeleid naar de hoofdtelefoon, maar het HoloLens-besturingssysteem geeft prioriteit aan de interne microfoon array boven elk ander invoerapparaat.</span><span class="sxs-lookup"><span data-stu-id="f25f2-145">When plugging in a set of USB-C headphones, users will observe that the headphone's audio will automatically be redirected to the headphones, but the HoloLens OS prioritizes the internal microphone array above any other input device.</span></span> <span data-ttu-id="f25f2-146">**Volg de onderstaande stappen om een USB-C-microfoon te gebruiken.**</span><span class="sxs-lookup"><span data-stu-id="f25f2-146">**In order to use a USB-C microphone follow the steps below.**</span></span>

> [!NOTE]
> <span data-ttu-id="f25f2-147">Externe microfoons kunnen niet worden gebruikt in builds vóór [Windows Holographic, versie 21H1](hololens-release-notes.md#windows-holographic-version-21h1) en hoger.</span><span class="sxs-lookup"><span data-stu-id="f25f2-147">External microphones cannot be used in builds prior to [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) and higher.</span></span> 

<span data-ttu-id="f25f2-148">Gebruikers kunnen externe usb-C-microfoons selecteren met behulp van het **instellingenpaneel** Geluid.</span><span class="sxs-lookup"><span data-stu-id="f25f2-148">Users can select USB-C connected external microphones using the **Sound** settings panel.</span></span> <span data-ttu-id="f25f2-149">USB-C-microfoons kunnen worden gebruikt voor het aanroepen, opnemen, enzovoort.</span><span class="sxs-lookup"><span data-stu-id="f25f2-149">USB-C microphones can be used for calling, recording, etc.</span></span>

<span data-ttu-id="f25f2-150">Open de **Instellingen app** en selecteer   >  **Systeemgeluid.**</span><span class="sxs-lookup"><span data-stu-id="f25f2-150">Open the **Settings** app and select **System** > **Sound**.</span></span>

![Geluid Instellingen](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> <span data-ttu-id="f25f2-152">Als u externe microfoons wilt **gebruiken Remote Assist,** moeten gebruikers op de hyperlink 'Geluidsapparaten beheren' klikken.</span><span class="sxs-lookup"><span data-stu-id="f25f2-152">To use external microphones with **Remote Assist**, users will need to click the “Manage sound devices” hyperlink.</span></span>
>
> <span data-ttu-id="f25f2-153">Gebruik vervolgens de vervolgkeuzeset om de externe microfoon in te stellen als **Standaardmicrofoon** of **Communicatie standaard.**</span><span class="sxs-lookup"><span data-stu-id="f25f2-153">Then use the drop-down to set the external microphone as either **Default** or **Communications Default.**</span></span> <span data-ttu-id="f25f2-154">Als **u Standaard** kiest, wordt de externe microfoon overal gebruikt.</span><span class="sxs-lookup"><span data-stu-id="f25f2-154">Choosing **Default** means that the external microphone will be used everywhere.</span></span>
>
> <span data-ttu-id="f25f2-155">Als **u Standaardcommunicatie** kiest, betekent dit dat de externe microfoon wordt gebruikt in Remote Assist en andere communicatie-apps, maar de HoloLens mic-matrix kan nog steeds worden gebruikt voor andere taken.</span><span class="sxs-lookup"><span data-stu-id="f25f2-155">Choosing **Communications Default** means that the external microphone will be used in Remote Assist and other communications apps, but the HoloLens mic array may still be used for other tasks.</span></span>

![Geluidsapparaten beheren](images/usbc-mic-2.png)

<br>

![Standaardmicrofoon instellen](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a><span data-ttu-id="f25f2-158">Hoe zit het Bluetooth microfoonondersteuning?</span><span class="sxs-lookup"><span data-stu-id="f25f2-158">What about Bluetooth microphone support?</span></span>

<span data-ttu-id="f25f2-159">Helaas worden Bluetooth microfoons nog steeds niet ondersteund op HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="f25f2-159">Unfortunately, Bluetooth microphones are still not currently supported on HoloLens 2.</span></span>

### <a name="usb-c-hubs"></a><span data-ttu-id="f25f2-160">USB-C Hubs</span><span class="sxs-lookup"><span data-stu-id="f25f2-160">USB-C Hubs</span></span>

<span data-ttu-id="f25f2-161">Sommige gebruikers moeten mogelijk meerdere apparaten tegelijk verbinden.</span><span class="sxs-lookup"><span data-stu-id="f25f2-161">Some users may need to connect multiple devices at once.</span></span> <span data-ttu-id="f25f2-162">Voor gebruikers die een [USB-C-microfoon](#usb-c-external-microphone-support) samen met een ander aangesloten apparaat willen gebruiken, kunnen USB-C-hubs aan de behoeften van de klant worden gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="f25f2-162">For users who would like to use a [USB-C microphone](#usb-c-external-microphone-support) along with another connected device, USB-C hubs may fit the customer's need.</span></span> <span data-ttu-id="f25f2-163">Microsoft heeft deze apparaten niet getest en we kunnen ook geen specifieke merken aanbevelen.</span><span class="sxs-lookup"><span data-stu-id="f25f2-163">Microsoft has not tested these devices, nor can we recommend any specific brands.</span></span>

<span data-ttu-id="f25f2-164">**Vereisten voor USB-C-hub en verbonden apparaten:**</span><span class="sxs-lookup"><span data-stu-id="f25f2-164">**Requirements for USB-C hub and connected devices:**</span></span>

- <span data-ttu-id="f25f2-165">Voor verbonden apparaten mag geen stuurprogramma zijn geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="f25f2-165">Connected devices must not require a driver to be installed.</span></span>
- <span data-ttu-id="f25f2-166">Het totale vermogen van alle verbonden apparaten moet lager zijn dan 4,5 Watt.</span><span class="sxs-lookup"><span data-stu-id="f25f2-166">The total power draw of all connected devices must be below 4.5 Watts.</span></span>

## <a name="connect-to-miracast"></a><span data-ttu-id="f25f2-167">Verbinding maken naar Miracast</span><span class="sxs-lookup"><span data-stu-id="f25f2-167">Connect to Miracast</span></span>

<span data-ttu-id="f25f2-168">Als u Miracast, volgt u deze stappen:</span><span class="sxs-lookup"><span data-stu-id="f25f2-168">To use Miracast, follow these steps:</span></span>

1. <span data-ttu-id="f25f2-169">Voer een van de volgende handelingen uit:</span><span class="sxs-lookup"><span data-stu-id="f25f2-169">Do one of the following:</span></span>  

   - <span data-ttu-id="f25f2-170">Open het **menu Start** en selecteer het **pictogram** Weergeven.</span><span class="sxs-lookup"><span data-stu-id="f25f2-170">Open the **Start** menu, and select the **Display** icon.</span></span>
   - <span data-ttu-id="f25f2-171">Zeg 'Verbinding maken' terwijl u naar het **menu Start kijkt.**</span><span class="sxs-lookup"><span data-stu-id="f25f2-171">Say "Connect" while you gaze at the **Start** menu.</span></span>  

1. <span data-ttu-id="f25f2-172">Selecteer een beschikbaar apparaat in de lijst met apparaten die wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="f25f2-172">On the list of devices that appears, select an available device.</span></span>

1. <span data-ttu-id="f25f2-173">Voltooi de koppeling om te beginnen met projecteren.</span><span class="sxs-lookup"><span data-stu-id="f25f2-173">Complete the pairing to begin projecting.</span></span>
