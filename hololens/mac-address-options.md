---
title: Enterprise Enrollment of HoloLens Devices in MAC address restricted Wi-Fi Environment
description: MAC-adres voor netwerk op HoloLens 2 apparaten
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: mata
ms.topic: article
ms.localizationpriority: high
ms.date: 10/01/2020
ms.reviewer: v-evmill
audience: ITPro
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: a577eace62040e2d48de5d3e4cc99ef108bd006c
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379387"
---
# <a name="enterprise-enrollment-of-hololens-devices-in-mac-address-restricted-wi-fi-environment"></a><span data-ttu-id="545e8-103">Enterprise Enrollment of HoloLens Devices in MAC address restricted Wi-Fi Environment</span><span class="sxs-lookup"><span data-stu-id="545e8-103">Enterprise Enrollment of HoloLens Devices in MAC address restricted Wi-Fi Environment</span></span>

<span data-ttu-id="545e8-104">In dit document wordt een veelvoorkomende scenario beschreven dat we hebben geïdentificeerd in klantomgevingen waar de Wi-Fi wordt beperkt door MAC-adressen of certificaten zijn vereist voor draadloze netwerken.</span><span class="sxs-lookup"><span data-stu-id="545e8-104">This document will describe a common scenario we have identified within customer environments where the Wi-Fi is restricted by MAC addresses, or certificates are required to join Wireless networks.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="545e8-105">Voorbeeldscenario</span><span class="sxs-lookup"><span data-stu-id="545e8-105">Example Scenario</span></span>

<span data-ttu-id="545e8-106">Veel klanten in beveiligde omgevingen hebben beperkingen voor hun draadloze of bekabelde netwerken waardoor alleen goedgekeurde apparaten (op basis van MAC-adressen) verbinding kunnen maken.</span><span class="sxs-lookup"><span data-stu-id="545e8-106">Many customers in secure environments have restrictions on their Wireless or wired networks that will only allow approved devices (based on MAC Addresses) to connect successfully.</span></span> <span data-ttu-id="545e8-107">Dit kan worden afgedwongen via mac-adresfiltering op een draadloos toegangspunt of via een DHCP-server.</span><span class="sxs-lookup"><span data-stu-id="545e8-107">This may be enforced through MAC Address filtering on a Wireless Access Point or through a DHCP server.</span></span> <span data-ttu-id="545e8-108">Bovendien sommige draadloze netwerken kunnen worden beveiligd met PEAP, waarvoor een certificaat moet worden toegepast op het apparaat vóór de authenticatie op het draadloze netwerk.</span><span class="sxs-lookup"><span data-stu-id="545e8-108">Additionally, some Wireless networks can be protected with PEAP, which requires that a certificate be applied to the device prior to authenticating on the Wireless network.</span></span>

<span data-ttu-id="545e8-109">In dit scenario kunnen twee belangrijke vereisten vertragingen tot gevolg hebben of handmatig ingrijpen vereisen bij het samenvoegen van HoloLens-apparaten met het netwerk:</span><span class="sxs-lookup"><span data-stu-id="545e8-109">In this scenario, two key requirements may introduce delays or require manual intervention when joining HoloLens devices to the network:</span></span>

- <span data-ttu-id="545e8-110">Het draadloze PEAP-certificaat moet worden toegepast op het apparaat voordat het apparaat kan worden aangesloten op het draadloze netwerk.</span><span class="sxs-lookup"><span data-stu-id="545e8-110">The Wireless PEAP certificate must be applied to the device prior to the device successfully joining the wireless network.</span></span>
- <span data-ttu-id="545e8-111">Het MAC-adres van de HoloLensWi-Fi adapter moet worden geregistreerd.</span><span class="sxs-lookup"><span data-stu-id="545e8-111">The MAC Address of the HoloLens Wi-Fi adaptor must be registered.</span></span>

<span data-ttu-id="545e8-112">De belangrijkste uitdagingen met de bovenstaande vereisten zijn:</span><span class="sxs-lookup"><span data-stu-id="545e8-112">The core challenges with the requirements above are:</span></span>

1. <span data-ttu-id="545e8-113">Het MAC-adres kan momenteel alleen worden geïdentificeerd in de app Instellingen op het apparaat of in Intune na een geslaagde inschrijving.</span><span class="sxs-lookup"><span data-stu-id="545e8-113">The MAC Address can currently only be identified from the Settings app on the device, or from Intune after a successful enrollment.</span></span>

2. <span data-ttu-id="545e8-114">Zonder het MAC-adres kan het apparaat geen lid worden Wi-Fi netwerk om de inschrijving te starten.</span><span class="sxs-lookup"><span data-stu-id="545e8-114">Without the MAC address, the device cannot join the Wi-Fi Network to begin enrollment.</span></span>

3. <span data-ttu-id="545e8-115">Handmatige tijdelijke oplossingen voor deze uitdagingen vereisen dat een technicus met het apparaat communiceert.</span><span class="sxs-lookup"><span data-stu-id="545e8-115">Manual workarounds to these challenges require a technician to interact with the device.</span></span>

## <a name="solutions"></a><span data-ttu-id="545e8-116">Oplossingen</span><span class="sxs-lookup"><span data-stu-id="545e8-116">Solutions</span></span>

<span data-ttu-id="545e8-117">Er zijn veel manieren om deze situatie te verbeteren, afhankelijk van de infrastructuur die beschikbaar is in de omgeving.</span><span class="sxs-lookup"><span data-stu-id="545e8-117">There are many ways to improve this situation, depending on the infrastructure available within the environment.</span></span>

| <span data-ttu-id="545e8-118">Oplossing</span><span class="sxs-lookup"><span data-stu-id="545e8-118">Solution</span></span> | <span data-ttu-id="545e8-119">Voordelen</span><span class="sxs-lookup"><span data-stu-id="545e8-119">Benefits</span></span> | <span data-ttu-id="545e8-120">Vereisten</span><span class="sxs-lookup"><span data-stu-id="545e8-120">Requirements</span></span> |
| --- | --- | --- |
| <span data-ttu-id="545e8-121">Inrichtingspakket met Ethernet-adapter</span><span class="sxs-lookup"><span data-stu-id="545e8-121">Provisioning Package with Ethernet Adaptor</span></span> | <span data-ttu-id="545e8-122">Verbetert de OOBE-ervaring en maakt een snellere techniciervaring mogelijk.</span><span class="sxs-lookup"><span data-stu-id="545e8-122">Improves OOBE experience and allows for a quicker technician experience.</span></span> | <span data-ttu-id="545e8-123">HoloLens-compatibele USB-C Hub + Ethernet-adapter en technicus moeten nog steeds communiceren met het apparaat voor MAC Capture en OOBE-finalisatie</span><span class="sxs-lookup"><span data-stu-id="545e8-123">HoloLens compatible USB-C Hub + Ethernet adaptor, and technician will still need to interact with the device for MAC capture and OOBE finalization</span></span> |
| <span data-ttu-id="545e8-124">Autopilot met Intune-registratie via Ethernet</span><span class="sxs-lookup"><span data-stu-id="545e8-124">Autopilot with Intune Registration over Ethernet</span></span> | <span data-ttu-id="545e8-125">Dit is een verbinding in één stap en de registratie van het apparaat bij de klantomgeving.</span><span class="sxs-lookup"><span data-stu-id="545e8-125">This is a single-step connection and registration of the device to the customer environment.</span></span> <span data-ttu-id="545e8-126">MAC-opname kan worden voltooid zonder interactie met het apparaat</span><span class="sxs-lookup"><span data-stu-id="545e8-126">MAC capture can be completed without needing to interact with the device</span></span> | <span data-ttu-id="545e8-127">Intune ingeschakeld voor de AAD-tenant van de klant en een Met HoloLens compatibele USB-C Ethernet-adapter</span><span class="sxs-lookup"><span data-stu-id="545e8-127">Intune enabled for the customer AAD tenant and a HoloLens compatible USB-C Ethernet adaptor</span></span> |
| <span data-ttu-id="545e8-128">Automatische rapportage van MAC-adressen</span><span class="sxs-lookup"><span data-stu-id="545e8-128">Automated reporting of MAC Addresses</span></span> | <span data-ttu-id="545e8-129">Wanneer apparaten zijn geregistreerd bij de Intune-tenant, kan een script het MAC-adres rapporteren aan de technicus.</span><span class="sxs-lookup"><span data-stu-id="545e8-129">When devices are registered with the Intune tenant, a script can report the MAC address to the technician.</span></span> | <span data-ttu-id="545e8-130">Intune PowerShell-cmdlets</span><span class="sxs-lookup"><span data-stu-id="545e8-130">Intune PowerShell cmdlets</span></span> |

## <a name="provisioning-package-with-ethernet-adaptor"></a><span data-ttu-id="545e8-131">Inrichtingspakket met Ethernet-adapter</span><span class="sxs-lookup"><span data-stu-id="545e8-131">Provisioning Package with Ethernet Adaptor</span></span>

> [!NOTE] 
> <span data-ttu-id="545e8-132">Als het bekabelde netwerk ook onderhevig is aan MAC-beperkingen, moet ook het MAC-adres van de USB-C Hub + Ethernet-adapter vooraf worden goedgekeurd.</span><span class="sxs-lookup"><span data-stu-id="545e8-132">If the wired network is also subject to MAC restrictions, then the MAC address of the USB-C Hub + Ethernet adaptor will also need to be pre-approved.</span></span> <span data-ttu-id="545e8-133">Zorg ervoor dat u deze adapter gebruikt, omdat hiermee toegang tot het netwerk vanaf andere apparaten wordt toegestaan.</span><span class="sxs-lookup"><span data-stu-id="545e8-133">Care should be taken with this adapter as it will allow access to the network from other devices.</span></span>

### <a name="requirements"></a><span data-ttu-id="545e8-134">Vereisten</span><span class="sxs-lookup"><span data-stu-id="545e8-134">Requirements</span></span>

- <span data-ttu-id="545e8-135">Bekabelde netwerkpoort met toegang tot het klantnetwerk</span><span class="sxs-lookup"><span data-stu-id="545e8-135">Wired network port with access to the customer network</span></span>
- <span data-ttu-id="545e8-136">HoloLens-compatibele USB-C Hub met Ethernet-adapter: elke adapter waarvoor geen extra stuurprogramma's of toepassingen zijn geïnstalleerd, moet geschikt zijn.</span><span class="sxs-lookup"><span data-stu-id="545e8-136">HoloLens Compatible USB-C Hub with Ethernet adaptor — Any adapter that doesn't require any additional drivers or application installs should be suitable.</span></span>
- <span data-ttu-id="545e8-137">Inrichtingspakket met:</span><span class="sxs-lookup"><span data-stu-id="545e8-137">Provisioning Package containing:</span></span>
  - <span data-ttu-id="545e8-138">Informatie over draadloze netwerken en certificaat</span><span class="sxs-lookup"><span data-stu-id="545e8-138">Containing Wireless Network information and Certificate</span></span>
  - <span data-ttu-id="545e8-139">Optioneel met inschrijvingsgegevens voor De Azure AD van de organisatie</span><span class="sxs-lookup"><span data-stu-id="545e8-139">Optionally containing enrollment information for the Organization's Azure AD</span></span>
  - <span data-ttu-id="545e8-140">Met alle andere vereiste inrichtingsinstellingen</span><span class="sxs-lookup"><span data-stu-id="545e8-140">Containing any other required provisioning settings</span></span>

### <a name="process"></a><span data-ttu-id="545e8-141">Proces</span><span class="sxs-lookup"><span data-stu-id="545e8-141">Process</span></span>

<span data-ttu-id="545e8-142">Het proces kan variëren, afhankelijk van het softwareniveau van het apparaat.</span><span class="sxs-lookup"><span data-stu-id="545e8-142">The Process may vary depending on the software level of the device.</span></span> <span data-ttu-id="545e8-143">Als het apparaat de update [van mei 2004 heeft,](hololens-release-notes.md#windows-holographic-version-2004)volgt u de onderstaande stappen.</span><span class="sxs-lookup"><span data-stu-id="545e8-143">If the device has the [May 2004 update](hololens-release-notes.md#windows-holographic-version-2004), follow the steps below.</span></span>

1. <span data-ttu-id="545e8-144">Plaats het inrichtingspakket in de hoofdmap van een USB-stick en sluit het aan op de hub.</span><span class="sxs-lookup"><span data-stu-id="545e8-144">Place the provisioning package onto the root of a USB stick, and plug into the Hub.</span></span>
2. <span data-ttu-id="545e8-145">Sluit de Ethernet-kabel aan op de Hub + Ethernet-adapter.</span><span class="sxs-lookup"><span data-stu-id="545e8-145">Connect Ethernet cable to the Hub + Ethernet adapter.</span></span>
3. <span data-ttu-id="545e8-146">USB-C Hub verbinden met HoloLens-apparaat.</span><span class="sxs-lookup"><span data-stu-id="545e8-146">Connect USB-C Hub to HoloLens device.</span></span>
4. <span data-ttu-id="545e8-147">Schakel de HoloLens in en zet het apparaat op.</span><span class="sxs-lookup"><span data-stu-id="545e8-147">Turn on the HoloLens and put on the device.</span></span>
5. <span data-ttu-id="545e8-148">Druk op **de knop Volume omlaag en Aan/uit om** het inrichtingspakket toe te passen.</span><span class="sxs-lookup"><span data-stu-id="545e8-148">Press the **Volume Down and Power button** to apply the Provisioning Package.</span></span>
6. <span data-ttu-id="545e8-149">De technicus kan nu OOBE volgen en als dit is voltooid, opent u de app Instellingen om het MAC-adres van het apparaat op te halen.</span><span class="sxs-lookup"><span data-stu-id="545e8-149">The technician can now follow OOBE, and when complete, open the Settings App to retrieve the MAC Address of the device.</span></span>

<span data-ttu-id="545e8-150">Als het apparaat een build van het besturingssysteem heeft vóór de update van mei [2004,](hololens-release-notes.md#windows-holographic-version-2004)volgt u de onderstaande stappen.</span><span class="sxs-lookup"><span data-stu-id="545e8-150">If the device has an OS build before the [May 2004 update](hololens-release-notes.md#windows-holographic-version-2004), follow the steps below.</span></span>

1. <span data-ttu-id="545e8-151">Schakel de HoloLens in en sluit het apparaat aan op een pc.</span><span class="sxs-lookup"><span data-stu-id="545e8-151">Turn on the HoloLens and plug the device into a PC.</span></span>
2. <span data-ttu-id="545e8-152">Het apparaat moet op de pc worden weer geven als een bestandsopslagapparaat.</span><span class="sxs-lookup"><span data-stu-id="545e8-152">The device should show up on the PC as a file storage device.</span></span>
3. <span data-ttu-id="545e8-153">Het inrichtingspakket naar het apparaat kopiëren</span><span class="sxs-lookup"><span data-stu-id="545e8-153">Copy the Provisioning Package to the Device</span></span>
4. <span data-ttu-id="545e8-154">Sluit de Ethernet-kabel aan op de hub.</span><span class="sxs-lookup"><span data-stu-id="545e8-154">Connect Ethernet cable to the hub.</span></span>
5. <span data-ttu-id="545e8-155">USB-C Hub verbinden met HoloLens-apparaat.</span><span class="sxs-lookup"><span data-stu-id="545e8-155">Connect USB-C Hub to HoloLens device.</span></span>
6. <span data-ttu-id="545e8-156">De HoloLens in</span><span class="sxs-lookup"><span data-stu-id="545e8-156">Put on the HoloLens</span></span>
7. <span data-ttu-id="545e8-157">Druk op **de knop Volume omlaag en Aan/uit** om het inrichtingspakket toe te passen.</span><span class="sxs-lookup"><span data-stu-id="545e8-157">Press the **Volume Down and Power** button to apply the Provisioning Package.</span></span>
8. <span data-ttu-id="545e8-158">De technicus kan nu OOBE volgen en als dit is voltooid, opent u de app Instellingen om het MAC-adres van het apparaat op te halen.</span><span class="sxs-lookup"><span data-stu-id="545e8-158">The technician can now follow OOBE, and when complete, open the Settings App to retrieve the MAC Address of the device.</span></span>

### <a name="benefits"></a><span data-ttu-id="545e8-159">Voordelen</span><span class="sxs-lookup"><span data-stu-id="545e8-159">Benefits</span></span>

<span data-ttu-id="545e8-160">Hierdoor kan het apparaat met één toets het juiste inrichtingspakket toepassen en het MAC-adres van het apparaat verzamelen.</span><span class="sxs-lookup"><span data-stu-id="545e8-160">This will allow a "Single touch" of the device, to apply the correct provisioning package and gather the MAC address of the device.</span></span> [<span data-ttu-id="545e8-161">Inrichtingspakketten kunnen worden gemaakt volgens de richtlijnen hier.</span><span class="sxs-lookup"><span data-stu-id="545e8-161">Provisioning packages can be created following the guidance here.</span></span>](https://docs.microsoft.com/hololens/hololens-provisioning)

## <a name="autopilot-with-intune-enrollment"></a><span data-ttu-id="545e8-162">Autopilot met Intune-inschrijving</span><span class="sxs-lookup"><span data-stu-id="545e8-162">Autopilot with Intune Enrollment</span></span>

### <a name="requirements"></a><span data-ttu-id="545e8-163">Vereisten</span><span class="sxs-lookup"><span data-stu-id="545e8-163">Requirements</span></span>

- <span data-ttu-id="545e8-164">Bekabelde netwerkpoort met toegang tot het klantnetwerk</span><span class="sxs-lookup"><span data-stu-id="545e8-164">Wired network port with access to the customer network</span></span>
- <span data-ttu-id="545e8-165">HoloLens-apparaten met Windows Holographic 2004</span><span class="sxs-lookup"><span data-stu-id="545e8-165">HoloLens devices running Windows Holographic 2004</span></span>
- <span data-ttu-id="545e8-166">HoloLens-compatibele USB-C Ethernet-adapter</span><span class="sxs-lookup"><span data-stu-id="545e8-166">HoloLens Compatible USB-C Ethernet adapter</span></span>
- <span data-ttu-id="545e8-167">Intune instellen en inschakelen voor de tenant van de klant</span><span class="sxs-lookup"><span data-stu-id="545e8-167">Intune set up and enabled for the customer Tenant</span></span>
- <span data-ttu-id="545e8-168">Apparaat geregistreerd voor Autopilot en geïmporteerd in de tenant van de klant</span><span class="sxs-lookup"><span data-stu-id="545e8-168">Device registered for Autopilot and imported into the Customer Tenant</span></span>
- <span data-ttu-id="545e8-169">Intune-beleidsregels die zijn gedefinieerd voor het apparaat:</span><span class="sxs-lookup"><span data-stu-id="545e8-169">Intune Policies defined for the device:</span></span>
   - <span data-ttu-id="545e8-170">Informatie over draadloze netwerken en certificaat</span><span class="sxs-lookup"><span data-stu-id="545e8-170">Containing Wireless Network information and Certificate</span></span>
   - <span data-ttu-id="545e8-171">Met alle andere vereiste inrichtingsinstellingen</span><span class="sxs-lookup"><span data-stu-id="545e8-171">Containing any other required provisioning settings</span></span>

<span data-ttu-id="545e8-172">Hierdoor kan een klant met geavanceerde netwerkvereisten de apparaten inschrijven in een hands-off, schaalbare benadering</span><span class="sxs-lookup"><span data-stu-id="545e8-172">This will allow a customer with advanced networking requirements to enroll the devices in a hands-off, scalable approach</span></span>

<span data-ttu-id="545e8-173">Er zijn aanvullende vereisten nodig, zoals hieronder wordt beschreven:</span><span class="sxs-lookup"><span data-stu-id="545e8-173">Additional pre-requisites will be needed as below:</span></span>
1. <span data-ttu-id="545e8-174">[Schakel de tenant in voor de Autopilot-preview.](https://docs.microsoft.com/hololens/hololens2-autopilot)</span><span class="sxs-lookup"><span data-stu-id="545e8-174">[Enable the Tenant for the Autopilot preview](https://docs.microsoft.com/hololens/hololens2-autopilot).</span></span>
1. <span data-ttu-id="545e8-175">Maak het HoloLens-beleid ter vervanging van het inrichtingspakket in Intune.</span><span class="sxs-lookup"><span data-stu-id="545e8-175">Create the HoloLens policies to replace the Provisioning Package within Intune.</span></span>
1. <span data-ttu-id="545e8-176">Maak het HoloLens Intune-beleid.</span><span class="sxs-lookup"><span data-stu-id="545e8-176">Create the HoloLens Intune Policies.</span></span>
1. <span data-ttu-id="545e8-177">Wijs de apparaten toe aan de juiste groep.</span><span class="sxs-lookup"><span data-stu-id="545e8-177">Assign the devices to the correct group.</span></span>

### <a name="process"></a><span data-ttu-id="545e8-178">Proces</span><span class="sxs-lookup"><span data-stu-id="545e8-178">Process</span></span>

1. <span data-ttu-id="545e8-179">Sluit de ethernetkabel aan op de adapter en sluit de adapter aan op de USB-C-poort op HoloLens 2 apparaat.</span><span class="sxs-lookup"><span data-stu-id="545e8-179">Connect the ethernet cable to the adapter and plug the adapter into the USB-C port on the HoloLens 2 device.</span></span>

2. <span data-ttu-id="545e8-180">Schakel de HoloLens in.</span><span class="sxs-lookup"><span data-stu-id="545e8-180">Turn on the HoloLens.</span></span>

3. <span data-ttu-id="545e8-181">Het apparaat moet automatisch verbinding maken met internet tijdens OOBE via de Ethernet-adapter.</span><span class="sxs-lookup"><span data-stu-id="545e8-181">The device should automatically connect to the internet during OOBE via the Ethernet adaptor.</span></span> <span data-ttu-id="545e8-182">De Autopilot-configuratie moet worden gedetecteerd en automatisch worden geregistreerd bij Azure AD en Intune.</span><span class="sxs-lookup"><span data-stu-id="545e8-182">It should detect the Autopilot configuration and automatically register with Azure AD and Intune.</span></span>

4. <span data-ttu-id="545e8-183">Op het apparaat worden de vereiste Wi-Fi certificaten en andere configuratie toegepast, indien nodig via Intune.</span><span class="sxs-lookup"><span data-stu-id="545e8-183">The Device will apply the required Wi-Fi Certificates and other configuration as needed via Intune.</span></span>

5. <span data-ttu-id="545e8-184">Wanneer dit is voltooid, kan de technicus de Intune-portal (Endpoint Manager) laden en inzoomen op de pagina met apparaateigenschappen op **Start -> Devices -> DeviceName -> Hardware.**</span><span class="sxs-lookup"><span data-stu-id="545e8-184">When complete, the technician can load the Intune (Endpoint Manager) Portal and drill into the device properties page at **Home -> Devices -> DeviceName -> Hardware**.</span></span>

6. <span data-ttu-id="545e8-185">Het Wi-Fi MAC-adres wordt weergegeven in de Intune-portal.</span><span class="sxs-lookup"><span data-stu-id="545e8-185">The Wi-Fi MAC address will be visible within the Intune Portal.</span></span>

   ![MAC-adres via Intune](images/mac-address-intune.jpg)

7. <span data-ttu-id="545e8-187">De technicus voegt dit MAC-adres toe als een toegestaan apparaat.</span><span class="sxs-lookup"><span data-stu-id="545e8-187">The technician will add this MAC address as an allowed device.</span></span>

### <a name="benefits"></a><span data-ttu-id="545e8-188">Voordelen</span><span class="sxs-lookup"><span data-stu-id="545e8-188">Benefits</span></span>

<span data-ttu-id="545e8-189">Hierdoor is een 'kop-op-kop'-implementatie mogelijk voor de technicus, omdat het apparaat vanaf de doos kan worden ingeschreven bij Azure AD en Intune zonder dat de technicus het apparaat moet dragen of handmatig met de HoloLens-omgeving moet werken.</span><span class="sxs-lookup"><span data-stu-id="545e8-189">This will allow a "Heads off" deployment experience for the Technician, with the device being able to go from the box to enrolled in Azure AD and Intune without the technician having to wear the device or manually interact with the HoloLens environment.</span></span>

## <a name="reporting-of-mac-addresses-to-the-technician"></a><span data-ttu-id="545e8-190">Rapportage van MAC-adressen aan de technicus</span><span class="sxs-lookup"><span data-stu-id="545e8-190">Reporting of MAC addresses to the Technician</span></span>

### <a name="requirements"></a><span data-ttu-id="545e8-191">Vereisten</span><span class="sxs-lookup"><span data-stu-id="545e8-191">Requirements</span></span>

- <span data-ttu-id="545e8-192">Autorisatie van 'Intune Graph PowerShell' voor de tenant van de klant</span><span class="sxs-lookup"><span data-stu-id="545e8-192">Authorization of the "Intune Graph PowerShell" against the customer Tenant</span></span>
- <span data-ttu-id="545e8-193">Installatie van De Intune Graph PowerShell op de computer van de technici.</span><span class="sxs-lookup"><span data-stu-id="545e8-193">Installation of the Intune Graph PowerShell on the technicians machine.</span></span>
- [https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0)
- <span data-ttu-id="545e8-194">Leestoegang tot de elementen Beheerde apparaten van Intune.</span><span class="sxs-lookup"><span data-stu-id="545e8-194">Read access to the "Managed Devices" elements of Intune.</span></span> <span data-ttu-id="545e8-195">(Helpdesk-operator of hoger, of een aangepaste rol)</span><span class="sxs-lookup"><span data-stu-id="545e8-195">(Help Desk Operator or above, or a custom role)</span></span>

<span data-ttu-id="545e8-196">Er is momenteel geen eenvoudige manier om een automatiseringsopdracht te activeren op basis van de inschrijving van een nieuw apparaat in Intune.</span><span class="sxs-lookup"><span data-stu-id="545e8-196">At present, there is no "simple" way to trigger an automation command based on the enrollment of a new device within Intune.</span></span> <span data-ttu-id="545e8-197">Daarom biedt deze opdracht de technicus een eenvoudige manier om het MAC-adres op te halen zonder dat hij zich hoeft aan te melden bij de portal en het handmatig op te halen.</span><span class="sxs-lookup"><span data-stu-id="545e8-197">Therefore, this command will provide the technician a simple way to retrieve the MAC address without needing to log onto the portal and manually retrieve it.</span></span>

```powershell
Import-Module Microsoft.Graph.Intune

Connect-MSGraph

Get-IntuneManagedDevice -Filter "model eq 'Hololens 2'" | where {$_.enrolledDateTime -gt (get-date).AddDays(-30)}  | select deviceName, wiFiMacAddress 
```

<span data-ttu-id="545e8-198">Hiermee worden de naam en het MAC-adres van alle HoloLens-apparaten die in de afgelopen 30 dagen zijn geregistreerd, teruggeschreven.</span><span class="sxs-lookup"><span data-stu-id="545e8-198">This will return the name and MAC address of any HoloLens devices that have been enrolled in the last 30 days.</span></span>

![MAC-adres via PowerShell](images/mac-address-powershell.jpg)

### <a name="process"></a><span data-ttu-id="545e8-200">Proces</span><span class="sxs-lookup"><span data-stu-id="545e8-200">Process</span></span>

<span data-ttu-id="545e8-201">Nadat de Intune-inschrijving is voltooid, zou de monteur het bovenstaande script uitvoeren om het MAC-adres op te halen.</span><span class="sxs-lookup"><span data-stu-id="545e8-201">After the Intune enrollment has completed, the Technician would run the above script to retrieve the MAC address.</span></span>
