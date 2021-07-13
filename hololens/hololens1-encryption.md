---
title: HoloLens BitLocker-versleuteling
description: Meer informatie over het inschakelen van BitLocker-apparaatversleuteling om bestanden te beveiligen die zijn opgeslagen op HoloLens mixed reality apparaten.
ms.prod: hololens
ms.mktglfcycl: manage
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 01/26/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 37efab3ef3d68a9641320e144619008612f6efa2
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635242"
---
# <a name="hololens-1st-gen-bitlocker-encryption"></a><span data-ttu-id="fcaf6-103">HoloLens (1e generatie) BitLocker-versleuteling</span><span class="sxs-lookup"><span data-stu-id="fcaf6-103">HoloLens (1st Gen) BitLocker Encryption</span></span>

<span data-ttu-id="fcaf6-104">HoloLens (eerste generatie) en HoloLens 2 ondersteunen apparaatversleuteling met BitLocker, maar BitLocker is altijd ingeschakeld op HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="fcaf6-104">HoloLens (1st gen) and HoloLens 2 both support device encryption using BitLocker, however, BitLocker is always enabled on HoloLens 2.</span></span>

<span data-ttu-id="fcaf6-105">In dit artikel vindt u hulp bij het inschakelen en beheren van BitLocker op HoloLens (1e generatie).</span><span class="sxs-lookup"><span data-stu-id="fcaf6-105">This article will help you enable and manage BitLocker on HoloLens (1st gen).</span></span>

<span data-ttu-id="fcaf6-106">Op HoloLens (eerste generatie) kunt u BitLocker-apparaatversleuteling handmatig inschakelen of MDM (Mobile Device Management) gebruiken.</span><span class="sxs-lookup"><span data-stu-id="fcaf6-106">On HoloLens (1st gen) you can enable BitLocker device encryption manually or using mobile device management (MDM).</span></span> <span data-ttu-id="fcaf6-107">Volg deze instructies om [BitLocker-apparaatversleuteling in te](/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption) HoloLens.</span><span class="sxs-lookup"><span data-stu-id="fcaf6-107">Follow these instructions to enable [BitLocker device encryption](/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption) to protect files and information stored on the HoloLens.</span></span> <span data-ttu-id="fcaf6-108">Apparaatversleuteling helpt uw gegevens te beveiligen met behulp van de AES-CBC 128-versleutelingsmethode, die gelijk is aan [EncryptionMethodByDriveType-methode 3](/windows/client-management/mdm/bitlocker-csp#encryptionmethodbydrivetype) in de BitLocker-configuratieserviceprovider (CSP).</span><span class="sxs-lookup"><span data-stu-id="fcaf6-108">Device encryption helps protect your data using the AES-CBC 128 encryption method, which is equivalent to [EncryptionMethodByDriveType method 3](/windows/client-management/mdm/bitlocker-csp#encryptionmethodbydrivetype) in the BitLocker configuration service provider (CSP).</span></span> <span data-ttu-id="fcaf6-109">Medewerkers met de juiste versleutelingssleutel (zoals een wachtwoord) kunnen deze ontsleutelen of gegevensherstel uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="fcaf6-109">Personnel who have the correct encryption key (such as a password) can decrypt it or perform a data recovery.</span></span>

## <a name="enable-device-encryption-using-mdm"></a><span data-ttu-id="fcaf6-110">Apparaatversleuteling inschakelen met MDM</span><span class="sxs-lookup"><span data-stu-id="fcaf6-110">Enable device encryption using MDM</span></span>

<span data-ttu-id="fcaf6-111">U kunt uw MDM-provider (Mobile Device Management) gebruiken om een beleid toe te passen dat apparaatversleuteling vereist.</span><span class="sxs-lookup"><span data-stu-id="fcaf6-111">You can use your Mobile Device Management (MDM) provider to apply a policy that requires device encryption.</span></span> <span data-ttu-id="fcaf6-112">Het beleid dat moet worden gebruikt, is de instelling [Security/RequireDeviceEncryption](/windows/client-management/mdm/policy-csp-security#security-requiredeviceencryption) in de beleids-CSP.</span><span class="sxs-lookup"><span data-stu-id="fcaf6-112">The policy to use is the [Security/RequireDeviceEncryption setting](/windows/client-management/mdm/policy-csp-security#security-requiredeviceencryption) in the Policy CSP.</span></span>

[<span data-ttu-id="fcaf6-113">Zie de instructies voor het inschakelen van apparaatversleuteling met Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="fcaf6-113">See instructions for enabling device encryption using Microsoft Intune.</span></span>](/intune/compliance-policy-create-windows#windows-holographic-for-business)

<span data-ttu-id="fcaf6-114">Zie de documentatie van uw MDM-provider voor instructies voor andere MDM-hulpprogramma's.</span><span class="sxs-lookup"><span data-stu-id="fcaf6-114">For other MDM tools, see your MDM provider's documentation for instructions.</span></span> <span data-ttu-id="fcaf6-115">Als uw MDM-provider aangepaste URI vereist voor apparaatversleuteling, gebruikt u de volgende configuratie:</span><span class="sxs-lookup"><span data-stu-id="fcaf6-115">If your MDM provider requires custom URI for device encryption, use the following configuration:</span></span>

- <span data-ttu-id="fcaf6-116">**Naam:** een naam naar keuze</span><span class="sxs-lookup"><span data-stu-id="fcaf6-116">**Name**: a name of your choice</span></span>
- <span data-ttu-id="fcaf6-117">**Beschrijving:** optioneel</span><span class="sxs-lookup"><span data-stu-id="fcaf6-117">**Description**: optional</span></span>
- <span data-ttu-id="fcaf6-118">**OMA-URI:**`./Vendor/MSFT/Policy/Config/Security/RequireDeviceEncryption`</span><span class="sxs-lookup"><span data-stu-id="fcaf6-118">**OMA-URI**: `./Vendor/MSFT/Policy/Config/Security/RequireDeviceEncryption`</span></span>
- <span data-ttu-id="fcaf6-119">**Gegevenstype:** geheel getal</span><span class="sxs-lookup"><span data-stu-id="fcaf6-119">**Data type**: integer</span></span>
- <span data-ttu-id="fcaf6-120">**Waarde**: `1`</span><span class="sxs-lookup"><span data-stu-id="fcaf6-120">**Value**: `1`</span></span>

## <a name="enable-device-encryption-using-a-provisioning-package"></a><span data-ttu-id="fcaf6-121">Apparaatversleuteling inschakelen met behulp van een inrichtingspakket</span><span class="sxs-lookup"><span data-stu-id="fcaf6-121">Enable device encryption using a provisioning package</span></span>

<span data-ttu-id="fcaf6-122">Inrichtingspakketten zijn bestanden die zijn gemaakt door het hulpprogramma Windows Configuration Designer waarmee een opgegeven configuratie op een apparaat wordt toegepast.</span><span class="sxs-lookup"><span data-stu-id="fcaf6-122">Provisioning packages are files created by the Windows Configuration Designer tool that apply a specified configuration to a device.</span></span> 

### <a name="create-a-provisioning-package-that-upgrades-the-windows-holographic-edition-and-enables-encryption"></a><span data-ttu-id="fcaf6-123">Een inrichtingspakket maken waarmee de Windows Holographic-editie wordt geupgraded en versleuteling wordt mogelijk gemaakt</span><span class="sxs-lookup"><span data-stu-id="fcaf6-123">Create a provisioning package that upgrades the Windows Holographic edition and enables encryption</span></span>

1. [<span data-ttu-id="fcaf6-124">Maak een inrichtingspakket voor HoloLens.</span><span class="sxs-lookup"><span data-stu-id="fcaf6-124">Create a provisioning package for HoloLens.</span></span>](hololens-provisioning.md)
1. <span data-ttu-id="fcaf6-125">Ga naar **Runtime settings**  >  **Policies**  >  **Security** en selecteer **RequireDeviceEncryption.**</span><span class="sxs-lookup"><span data-stu-id="fcaf6-125">Go to **Runtime settings** > **Policies** > **Security**, and select **RequireDeviceEncryption**.</span></span>

    ![Instelling apparaatversleuteling vereisen die is geconfigureerd op Ja](images/device-encryption.png)

1. <span data-ttu-id="fcaf6-127">Zoek het XML-licentiebestand dat is opgegeven toen u de Commercial Suite hebt gekocht.</span><span class="sxs-lookup"><span data-stu-id="fcaf6-127">Find the XML license file that was provided when you purchased the Commercial Suite.</span></span>

1. <span data-ttu-id="fcaf6-128">Blader naar en selecteer het XML-licentiebestand dat is opgegeven bij de aankoop van de Commerciële suite.</span><span class="sxs-lookup"><span data-stu-id="fcaf6-128">Browse to and select the XML license file that was provided when you purchased the Commercial Suite.</span></span>
    > [!NOTE]
    > <span data-ttu-id="fcaf6-129">U kunt aanvullende [instellingen configureren in het inrichtingspakket](hololens-provisioning.md).</span><span class="sxs-lookup"><span data-stu-id="fcaf6-129">You can configure [additional settings in the provisioning package](hololens-provisioning.md).</span></span>

1. <span data-ttu-id="fcaf6-130">Klik in het menu **Bestand** op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="fcaf6-130">On the **File** menu, click **Save**.</span></span> 

1. <span data-ttu-id="fcaf6-131">Lees de waarschuwing waarin wordt uitgelegd dat projectbestanden gevoelige informatie kunnen bevatten en klik op **OK.**</span><span class="sxs-lookup"><span data-stu-id="fcaf6-131">Read the warning explaining that project files may contain sensitive information and click **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="fcaf6-132">Wanneer u een inrichtingspakket bouwt, kunt u gevoelige informatie opnemen in de projectbestanden en het inrichtingspakketbestand (.ppkg).</span><span class="sxs-lookup"><span data-stu-id="fcaf6-132">When you build a provisioning package, you may include sensitive information in the project files and provisioning package (.ppkg) file.</span></span> <span data-ttu-id="fcaf6-133">Hoewel u de mogelijkheid hebt om het PPKG-bestand te versleutelen, worden projectbestanden niet versleuteld.</span><span class="sxs-lookup"><span data-stu-id="fcaf6-133">Although you have the option to encrypt the .ppkg file, project files are not encrypted.</span></span> <span data-ttu-id="fcaf6-134">Sla de projectbestanden op een veilige locatie op en verwijder de projectbestanden wanneer ze niet meer nodig zijn.</span><span class="sxs-lookup"><span data-stu-id="fcaf6-134">You should store the project files in a secure location and delete the project files when no longer needed.</span></span>

1. <span data-ttu-id="fcaf6-135">Klik in **het** menu Exporteren op **Inrichtingspakket.**</span><span class="sxs-lookup"><span data-stu-id="fcaf6-135">On the **Export** menu, click **Provisioning package**.</span></span>
1. <span data-ttu-id="fcaf6-136">Wijzig **Eigenaar** in **IT-beheerder,** waarmee de prioriteit van dit inrichtingspakket hoger wordt ingesteld dan de inrichtingspakketten die vanuit andere bronnen op dit apparaat zijn toegepast en selecteer **vervolgens Volgende.**</span><span class="sxs-lookup"><span data-stu-id="fcaf6-136">Change **Owner** to **IT Admin**, which will set the precedence of this provisioning package higher than provisioning packages applied to this device from other sources, and then select **Next**.</span></span>
1. <span data-ttu-id="fcaf6-137">Stel een waarde in voor **Pakketversie**.</span><span class="sxs-lookup"><span data-stu-id="fcaf6-137">Set a value for **Package Version**.</span></span>

    > [!TIP]
    > <span data-ttu-id="fcaf6-138">U kunt wijzigingen aanbrengen in bestaande pakketten en het versienummer wijzigen om eerder toegepaste pakketten bij te werken.</span><span class="sxs-lookup"><span data-stu-id="fcaf6-138">You can make changes to existing packages and change the version number to update previously applied packages.</span></span>

1. <span data-ttu-id="fcaf6-139">Klik in **Beveiligingsdetails selecteren voor het inrichtingspakket** op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="fcaf6-139">On the **Select security details for the provisioning package**, click **Next**.</span></span>
1. <span data-ttu-id="fcaf6-140">Klik **op** Volgende om de uitvoerlocatie op te geven waar u het inrichtingspakket naartoe wilt laten gaan zodra het is gebouwd.</span><span class="sxs-lookup"><span data-stu-id="fcaf6-140">Click **Next** to specify the output location where you want the provisioning package to go once it's built.</span></span> <span data-ttu-id="fcaf6-141">Standaard gebruikt Windows ICD de projectmap als uitvoerlocatie.</span><span class="sxs-lookup"><span data-stu-id="fcaf6-141">By default, Windows ICD uses the project folder as the output location.</span></span>

    <span data-ttu-id="fcaf6-142">U kunt desgewenst op Bladeren klikken om de standaarduitvoerlocatie te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="fcaf6-142">Optionally, you can click Browse to change the default output location.</span></span>

1. <span data-ttu-id="fcaf6-143">Klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="fcaf6-143">Click **Next**.</span></span>
1. <span data-ttu-id="fcaf6-144">Klik **op Bouwen** om te beginnen met het bouwen van het pakket.</span><span class="sxs-lookup"><span data-stu-id="fcaf6-144">Click **Build** to start building the package.</span></span> <span data-ttu-id="fcaf6-145">De projectgegevens worden weergegeven op de buildpagina en de voortgangsbalk geeft de buildstatus aan.</span><span class="sxs-lookup"><span data-stu-id="fcaf6-145">The project information is displayed in the build page and the progress bar indicates the build status.</span></span>
1. <span data-ttu-id="fcaf6-146">Wanneer de build is voltooid, klikt u op **Voltooien.**</span><span class="sxs-lookup"><span data-stu-id="fcaf6-146">When the build completes, click **Finish**.</span></span>

### <a name="apply-the-provisioning-package-to-hololens"></a><span data-ttu-id="fcaf6-147">Pas het inrichtingspakket toe op HoloLens</span><span class="sxs-lookup"><span data-stu-id="fcaf6-147">Apply the provisioning package to HoloLens</span></span>

1. <span data-ttu-id="fcaf6-148">Verbinding maken apparaat via USB naar een pc en start het apparaat  op, maar ga niet verder dan de pagina voor passend maken van de eerste installatie (de eerste pagina met het blauwe vak).</span><span class="sxs-lookup"><span data-stu-id="fcaf6-148">Connect the device via USB to a PC and start the device, but do not continue past the **fit** page of the initial setup experience (the first page with the blue box).</span></span>
1. <span data-ttu-id="fcaf6-149">Druk kort op de knoppen **Volume down en** **Aan/uit.**</span><span class="sxs-lookup"><span data-stu-id="fcaf6-149">Briefly press and release the **Volume Down** and **Power** buttons simultaneously.</span></span>
1. <span data-ttu-id="fcaf6-150">HoloLens wordt weergegeven als een apparaat in Verkenner op de pc.</span><span class="sxs-lookup"><span data-stu-id="fcaf6-150">HoloLens will show up as a device in File Explorer on the PC.</span></span>
1. <span data-ttu-id="fcaf6-151">Sleep in Verkenner het inrichtingspakket (.ppkg) naar de apparaatopslag en zet het neer.</span><span class="sxs-lookup"><span data-stu-id="fcaf6-151">In File Explorer, drag and drop the provisioning package (.ppkg) onto the device storage.</span></span>
1. <span data-ttu-id="fcaf6-152">Druk kort op de knoppen **Volume down en** **Aan/uit** terwijl u op de pagina aanpassen **staat.**</span><span class="sxs-lookup"><span data-stu-id="fcaf6-152">Briefly press and release the **Volume Down** and **Power** buttons simultaneously again while on the **fit** page.</span></span>
1. <span data-ttu-id="fcaf6-153">Het apparaat vraagt u of u het pakket vertrouwt en het wilt toepassen.</span><span class="sxs-lookup"><span data-stu-id="fcaf6-153">The device will ask you if you trust the package and would like to apply it.</span></span> <span data-ttu-id="fcaf6-154">Bevestig dat u het pakket vertrouwt.</span><span class="sxs-lookup"><span data-stu-id="fcaf6-154">Confirm that you trust the package.</span></span>
1. <span data-ttu-id="fcaf6-155">U ziet of het pakket al dan niet is toegepast.</span><span class="sxs-lookup"><span data-stu-id="fcaf6-155">You will see whether the package was applied successfully or not.</span></span> <span data-ttu-id="fcaf6-156">Als dit is mislukt, kunt u het pakket herstellen en het opnieuw proberen.</span><span class="sxs-lookup"><span data-stu-id="fcaf6-156">If it failed, you can fix your package and try again.</span></span> <span data-ttu-id="fcaf6-157">Als dit is gelukt, gaat u verder met het instellen van het apparaat.</span><span class="sxs-lookup"><span data-stu-id="fcaf6-157">If it succeeded, proceed with device setup.</span></span>

> [!NOTE]
> <span data-ttu-id="fcaf6-158">Als het apparaat vóór augustus 2016 is gekocht, moet u zich aanmelden bij het apparaat met een Microsoft-account, de meest recente update van het besturingssysteem downloaden en vervolgens het besturingssysteem opnieuw instellen om het inrichtingspakket toe te passen.</span><span class="sxs-lookup"><span data-stu-id="fcaf6-158">If the device was purchased before August 2016, you will need to sign into the device with a Microsoft account, get the latest OS update, and then reset the OS in order to apply the provisioning package.</span></span>

## <a name="verify-device-encryption"></a><span data-ttu-id="fcaf6-159">Apparaatversleuteling controleren</span><span class="sxs-lookup"><span data-stu-id="fcaf6-159">Verify device encryption</span></span>

<span data-ttu-id="fcaf6-160">Versleuteling wordt op de HoloLens.</span><span class="sxs-lookup"><span data-stu-id="fcaf6-160">Encryption is silent on HoloLens.</span></span> <span data-ttu-id="fcaf6-161">De versleutelingsstatus van het apparaat controleren:</span><span class="sxs-lookup"><span data-stu-id="fcaf6-161">To verify the device encryption status:</span></span>

- <span data-ttu-id="fcaf6-162">Ga HoloLens naar **Instellingen**  >  **Systeem**  >  **over**.</span><span class="sxs-lookup"><span data-stu-id="fcaf6-162">On HoloLens, go to **Settings** > **System** > **About**.</span></span> <span data-ttu-id="fcaf6-163">**BitLocker** is **ingeschakeld als** het apparaat is versleuteld.</span><span class="sxs-lookup"><span data-stu-id="fcaf6-163">**BitLocker** is **enabled** if the device is encrypted.</span></span> 

    ![Over het scherm met BitLocker ingeschakeld](images/about-encryption.png)
