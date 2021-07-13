---
title: Functies voor Windows Holographic for Business ontgrendelen
description: Wanneer u een upgrade naar Windows Holographic for Business, HoloLens extra functies die zijn ontworpen voor bedrijven.
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/16/2019
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: b5ae9b0d6859c0f916b5b906e2e9ec54cad6cbd9
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635191"
---
# <a name="unlock-windows-holographic-for-business-features"></a><span data-ttu-id="bd1dc-103">Functies voor Windows Holographic for Business ontgrendelen</span><span class="sxs-lookup"><span data-stu-id="bd1dc-103">Unlock Windows Holographic for Business features</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bd1dc-104">Deze pagina is alleen van toepassing op HoloLens eerste generatie.</span><span class="sxs-lookup"><span data-stu-id="bd1dc-104">This page only applies to HoloLens 1st Gen.</span></span>

<span data-ttu-id="bd1dc-105">Microsoft HoloLens is beschikbaar in de *Development Edition*, die wordt uitgevoerd Windows Holographic (een editie van Windows 10 die is ontworpen voor HoloLens) en in de [Commercial Suite](hololens-commercial-features.md), die extra functies biedt die zijn ontworpen voor bedrijven.</span><span class="sxs-lookup"><span data-stu-id="bd1dc-105">Microsoft HoloLens is available in the *Development Edition*, which runs Windows Holographic (an edition of Windows 10 that is designed for HoloLens), and in the [Commercial Suite](hololens-commercial-features.md), which provides extra features designed for business.</span></span>

<span data-ttu-id="bd1dc-106">Wanneer u de Commercial Suite aanschaft, ontvangt u een licentie die wordt Windows Holographic naar Windows Holographic for Business.</span><span class="sxs-lookup"><span data-stu-id="bd1dc-106">When you purchase the Commercial Suite, you receive a license that upgrades Windows Holographic to Windows Holographic for Business.</span></span> <span data-ttu-id="bd1dc-107">U kunt deze licentie toepassen op het apparaat met behulp van de [MDM-provider (Mobile Device Management)](#edition-upgrade-by-using-mdm) van de organisatie of met [een inrichtingspakket.](#edition-upgrade-by-using-a-provisioning-package)</span><span class="sxs-lookup"><span data-stu-id="bd1dc-107">You can apply this license to the device either by using the organization's [mobile device management (MDM) provider](#edition-upgrade-by-using-mdm) or a [provisioning package](#edition-upgrade-by-using-a-provisioning-package).</span></span>

> [!TIP]
> <span data-ttu-id="bd1dc-108">In Windows 10 versie 1803 kunt u controleren of de HoloLens is bijgewerkt naar de zakelijke editie door Instellingen  >  **selecteren.**</span><span class="sxs-lookup"><span data-stu-id="bd1dc-108">In Windows 10, version 1803, you can check that the HoloLens has been upgraded to the business edition by selecting **Settings** > **System**.</span></span>

## <a name="edition-upgrade-by-using-mdm"></a><span data-ttu-id="bd1dc-109">Editie-upgrade met behulp van MDM</span><span class="sxs-lookup"><span data-stu-id="bd1dc-109">Edition upgrade by using MDM</span></span>

<span data-ttu-id="bd1dc-110">De bedrijfslicentie kan worden toegepast door elke MDM-provider die ondersteuning biedt voor [de CSP (WindowsLicensing Configuration Service Provider).](https://msdn.microsoft.com/library/windows/hardware/dn904983.aspx)</span><span class="sxs-lookup"><span data-stu-id="bd1dc-110">The enterprise license can be applied by any MDM provider that supports the [WindowsLicensing configuration service provider (CSP)](https://msdn.microsoft.com/library/windows/hardware/dn904983.aspx).</span></span> <span data-ttu-id="bd1dc-111">De nieuwste versie van de Microsoft MDM-API biedt ondersteuning voor WindowsLicensing CSP.</span><span class="sxs-lookup"><span data-stu-id="bd1dc-111">The latest version of the Microsoft MDM API will support WindowsLicensing CSP.</span></span>

<span data-ttu-id="bd1dc-112">Zie Upgrade devices [running Windows Holographic](/intune/holographic-upgrade)to Windows Holographic for Business (Apparaten met Windows Holographic upgraden naar Windows Holographic for Business) voor stapsgewijs instructies voor het upgraden van HoloLens met behulp van Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="bd1dc-112">For step-by-step instructions for upgrading HoloLens by using Microsoft Intune, see [Upgrade devices running Windows Holographic to Windows Holographic for Business](/intune/holographic-upgrade).</span></span>

 <span data-ttu-id="bd1dc-113">Bij andere MDM-providers kunnen de specifieke stappen voor het instellen en implementeren van het beleid variëren.</span><span class="sxs-lookup"><span data-stu-id="bd1dc-113">On other MDM providers, the specific steps for setting up and deploying the policy might vary.</span></span>

## <a name="edition-upgrade-by-using-a-provisioning-package"></a><span data-ttu-id="bd1dc-114">Editie-upgrade met behulp van een inrichtingspakket</span><span class="sxs-lookup"><span data-stu-id="bd1dc-114">Edition upgrade by using a provisioning package</span></span>

<span data-ttu-id="bd1dc-115">Inrichtingspakketten zijn bestanden die zijn gemaakt door het hulpprogramma Windows Configuration Designer waarmee een opgegeven configuratie op een apparaat wordt toegepast.</span><span class="sxs-lookup"><span data-stu-id="bd1dc-115">Provisioning packages are files created by the Windows Configuration Designer tool that apply a specified configuration to a device.</span></span>

### <a name="create-a-provisioning-package-that-upgrades-the-windows-holographic-edition"></a><span data-ttu-id="bd1dc-116">Een inrichtingspakket maken dat de Windows Holographic-editie upgradet</span><span class="sxs-lookup"><span data-stu-id="bd1dc-116">Create a provisioning package that upgrades the Windows Holographic edition</span></span>

1. [<span data-ttu-id="bd1dc-117">Maak een inrichtingspakket voor HoloLens.</span><span class="sxs-lookup"><span data-stu-id="bd1dc-117">Create a provisioning package for HoloLens.</span></span>](hololens-provisioning.md)
1. <span data-ttu-id="bd1dc-118">Ga naar **Runtime-instellingen**  >  **EditionUpgrade** en selecteer **EditionUpgradeWithLicense.**</span><span class="sxs-lookup"><span data-stu-id="bd1dc-118">Go to **Runtime settings** > **EditionUpgrade**, and select **EditionUpgradeWithLicense**.</span></span>

    ![Editie upgraden met licentie-instelling geselecteerd](images/icd1.png)

1. <span data-ttu-id="bd1dc-120">Zoek het XML-licentiebestand dat is opgegeven toen u de Commercial Suite hebt gekocht.</span><span class="sxs-lookup"><span data-stu-id="bd1dc-120">Find the XML license file that was provided when you purchased the Commercial Suite.</span></span>

    > [!NOTE]
    > <span data-ttu-id="bd1dc-121">U kunt aanvullende [instellingen configureren in het inrichtingspakket](hololens-provisioning.md).</span><span class="sxs-lookup"><span data-stu-id="bd1dc-121">You can configure [additional settings in the provisioning package](hololens-provisioning.md).</span></span>

1. <span data-ttu-id="bd1dc-122">In het menu **Bestand** selecteert u **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="bd1dc-122">On the **File** menu, select **Save**.</span></span> 

1. <span data-ttu-id="bd1dc-123">Lees de waarschuwing dat projectbestanden gevoelige informatie kunnen bevatten en klik op **OK.**</span><span class="sxs-lookup"><span data-stu-id="bd1dc-123">Read the warning that project files may contain sensitive information and click **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="bd1dc-124">Wanneer u een inrichtingspakket bouwt, kunt u gevoelige informatie opnemen in de projectbestanden en het inrichtingspakketbestand (.ppkg).</span><span class="sxs-lookup"><span data-stu-id="bd1dc-124">When you build a provisioning package, you may include sensitive information in the project files and provisioning package (.ppkg) file.</span></span> <span data-ttu-id="bd1dc-125">Hoewel u de mogelijkheid hebt om het PPKG-bestand te versleutelen, worden projectbestanden niet versleuteld.</span><span class="sxs-lookup"><span data-stu-id="bd1dc-125">Although you have the option to encrypt the .ppkg file, project files are not encrypted.</span></span> <span data-ttu-id="bd1dc-126">Sla de projectbestanden op een veilige locatie op en verwijder de projectbestanden wanneer ze niet meer nodig zijn.</span><span class="sxs-lookup"><span data-stu-id="bd1dc-126">You should store the project files in a secure location and delete the project files when no longer needed.</span></span>

1. <span data-ttu-id="bd1dc-127">Selecteer in **het** menu Exporteren de optie **Inrichtingspakket.**</span><span class="sxs-lookup"><span data-stu-id="bd1dc-127">On the **Export** menu, select **Provisioning package**.</span></span>

1. <span data-ttu-id="bd1dc-128">Wijzig **Eigenaar** in **IT-beheerder,** waarmee de prioriteit van dit inrichtingspakket hoger is dan die van andere bronnen die op dit apparaat worden toegepast en selecteer **vervolgens Volgende.**</span><span class="sxs-lookup"><span data-stu-id="bd1dc-128">Change **Owner** to **IT Admin**, which sets the precedence of this provisioning package to be higher than others applied to this device from different sources, and then select **Next**.</span></span>

1. <span data-ttu-id="bd1dc-129">Stel een waarde in voor **Pakketversie**.</span><span class="sxs-lookup"><span data-stu-id="bd1dc-129">Set a value for **Package Version**.</span></span>

    > [!TIP]
    > <span data-ttu-id="bd1dc-130">U kunt wijzigingen aanbrengen in bestaande pakketten en het versienummer wijzigen om eerder toegepaste pakketten bij te werken.</span><span class="sxs-lookup"><span data-stu-id="bd1dc-130">You can make changes to existing packages and change the version number to update previously applied packages.</span></span>

1. <span data-ttu-id="bd1dc-131">Selecteer **volgende bij Beveiligingsdetails voor het inrichtingspakket** **selecteren.**</span><span class="sxs-lookup"><span data-stu-id="bd1dc-131">On **Select security details for the provisioning package**, select **Next**.</span></span>

1. <span data-ttu-id="bd1dc-132">Selecteer **Volgende** om de uitvoerlocatie op te geven waar u het inrichtingspakket naartoe wilt laten gaan zodra het is gebouwd.</span><span class="sxs-lookup"><span data-stu-id="bd1dc-132">Select **Next** to specify the output location where you want the provisioning package to go once it's built.</span></span> <span data-ttu-id="bd1dc-133">Standaard gebruikt Windows ICD de projectmap als uitvoerlocatie.</span><span class="sxs-lookup"><span data-stu-id="bd1dc-133">By default, Windows ICD uses the project folder as the output location.</span></span>

    <span data-ttu-id="bd1dc-134">U kunt eventueel Bladeren selecteren **om de** standaarduitvoerlocatie te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="bd1dc-134">Optionally, you can select **Browse** to change the default output location.</span></span>

1. <span data-ttu-id="bd1dc-135">Selecteer **Next**.</span><span class="sxs-lookup"><span data-stu-id="bd1dc-135">Select **Next**.</span></span>

1. <span data-ttu-id="bd1dc-136">Selecteer **Bouwen om** te beginnen met het bouwen van het pakket.</span><span class="sxs-lookup"><span data-stu-id="bd1dc-136">Select **Build** to start building the package.</span></span> <span data-ttu-id="bd1dc-137">Op de buildpagina worden de projectgegevens weergegeven en de voortgangsbalk geeft de buildstatus aan.</span><span class="sxs-lookup"><span data-stu-id="bd1dc-137">The build page displays the project information, and the progress bar indicates the build status.</span></span>

1. <span data-ttu-id="bd1dc-138">Wanneer de build is voltooid, selecteert u **Voltooien.**</span><span class="sxs-lookup"><span data-stu-id="bd1dc-138">When the build completes, select **Finish**.</span></span>

### <a name="apply-the-provisioning-package-to-hololens"></a><span data-ttu-id="bd1dc-139">Pas het inrichtingspakket toe op HoloLens</span><span class="sxs-lookup"><span data-stu-id="bd1dc-139">Apply the provisioning package to HoloLens</span></span>

1. <span data-ttu-id="bd1dc-140">Sluit het apparaat met behulp van de USB-kabel aan op een pc.</span><span class="sxs-lookup"><span data-stu-id="bd1dc-140">Using the USB cable, connect the device to a PC.</span></span> <span data-ttu-id="bd1dc-141">Start het apparaat, maar ga  niet verder dan de pagina voor passend maken van de eerste installatie -ervaring (de eerste pagina met het blauwe vak).</span><span class="sxs-lookup"><span data-stu-id="bd1dc-141">Start the device, but do not continue past the **fit** page of the initial setup experience (the first page with the blue box).</span></span> <span data-ttu-id="bd1dc-142">Op de pc wordt HoloLens weergegeven als een apparaat in Verkenner.</span><span class="sxs-lookup"><span data-stu-id="bd1dc-142">On the PC, HoloLens shows up as a device in File Explorer.</span></span>

    > [!NOTE]
    > <span data-ttu-id="bd1dc-143">Als op het HoloLens-apparaat Windows 10 versie 1607 of eerder wordt uitgevoerd, opent u Verkenner door  kort op **de knoppen Volume** down en Aan/uit te drukken op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="bd1dc-143">If the HoloLens device is running Windows 10, version 1607 or earlier, open File Explorer by briefly pressing and releasing the **Volume Down** and **Power** buttons simultaneously on the device.</span></span>

1. <span data-ttu-id="bd1dc-144">Sleep in Verkenner het inrichtingspakket (.ppkg) naar de apparaatopslag en zet het neer.</span><span class="sxs-lookup"><span data-stu-id="bd1dc-144">In File Explorer, drag and drop the provisioning package (.ppkg) onto the device storage.</span></span>

1. <span data-ttu-id="bd1dc-145">Terwijl HoloLens nog steeds op  de pagina passend is, drukt  u even op **volume** omlaag en drukt u tegelijkertijd op De knoppen Volume omlaag en Aan/uit.</span><span class="sxs-lookup"><span data-stu-id="bd1dc-145">While HoloLens is still on the **fit** page, briefly press and release the **Volume Down** and **Power** buttons simultaneously again.</span></span>

1. <span data-ttu-id="bd1dc-146">HoloLens wordt u gevraagd of u het pakket vertrouwt en wilt toepassen.</span><span class="sxs-lookup"><span data-stu-id="bd1dc-146">HoloLens asks you if you trust the package and would like to apply it.</span></span> <span data-ttu-id="bd1dc-147">Bevestig dat u het pakket vertrouwt.</span><span class="sxs-lookup"><span data-stu-id="bd1dc-147">Confirm that you trust the package.</span></span>

1. <span data-ttu-id="bd1dc-148">U ziet of het pakket al dan niet is toegepast.</span><span class="sxs-lookup"><span data-stu-id="bd1dc-148">You will see whether the package was applied successfully or not.</span></span> <span data-ttu-id="bd1dc-149">Als het niet is toegepast, kunt u het pakket herstellen en het opnieuw proberen.</span><span class="sxs-lookup"><span data-stu-id="bd1dc-149">If it was not applied successfully, you can fix your package and try again.</span></span> <span data-ttu-id="bd1dc-150">Als dit lukt, gaat u verder met het instellen van het apparaat.</span><span class="sxs-lookup"><span data-stu-id="bd1dc-150">If successful, proceed with device setup.</span></span>
