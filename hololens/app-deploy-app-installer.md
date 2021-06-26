---
title: Apps side loaden en apps installeren via HoloLens 2 App-installatieprogramma
description: Meer informatie over het installeren en oplossen van problemen met apps met het app-installatieprogramma, het laden aan de zijkant en het installeren van apps via de gebruikersinterface.
keywords: app-beheer, app, hololens, app-installatieprogramma
author: evmill
ms.author: v-evmill
ms.reviewer: qizho
ms.date: 11/10/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: d8be5c2ed7fba38b6710aba9c122557a36073a79
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924125"
---
# <a name="install-apps-on-hololens-2-via-app-installer"></a><span data-ttu-id="7de19-104">Apps installeren op HoloLens 2 via App-installatieprogramma</span><span class="sxs-lookup"><span data-stu-id="7de19-104">Install Apps on HoloLens 2 via App Installer</span></span>

> [!NOTE]
> <span data-ttu-id="7de19-105">Deze functie is beschikbaar gesteld in [Windows Holographic, versie 20H2 – update van december 2020.](hololens-release-notes.md)</span><span class="sxs-lookup"><span data-stu-id="7de19-105">This feature was made available in [Windows Holographic, version 20H2 – December 2020 Update](hololens-release-notes.md).</span></span> <span data-ttu-id="7de19-106">Zorg ervoor dat uw apparaat is [bijgewerkt](hololens-update-hololens.md) om deze functie te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="7de19-106">Ensure your device is [updated](hololens-update-hololens.md) to use this feature.</span></span>

<span data-ttu-id="7de19-107">We hebben **een nieuwe mogelijkheid (App-installatieprogramma)** toegevoegd waarmee u toepassingen naadloos kunt installeren op uw HoloLens 2 apparaten.</span><span class="sxs-lookup"><span data-stu-id="7de19-107">We have **added a new capability (App Installer) to allow you to install applications more seamlessly** on your HoloLens 2 devices.</span></span> <span data-ttu-id="7de19-108">De functie is **standaard ingeschakeld voor niet-beherende apparaten.**</span><span class="sxs-lookup"><span data-stu-id="7de19-108">The feature will be **on by default for unmanaged devices**.</span></span> <span data-ttu-id="7de19-109">Om onderbrekingen voor ondernemingen te voorkomen, is het app-installatieprogramma op dit moment niet beschikbaar **voor** beheerde apparaten.</span><span class="sxs-lookup"><span data-stu-id="7de19-109">To prevent disruption to enterprises, app installer will be **not be available for managed devices** at this time.</span></span>  

<span data-ttu-id="7de19-110">Een apparaat wordt beschouwd als 'beheerd' als **een** van de volgende waar is:</span><span class="sxs-lookup"><span data-stu-id="7de19-110">A device is considered “managed” if **any** of the following are true:</span></span>

- <span data-ttu-id="7de19-111">MDM [ingeschreven](hololens-enroll-mdm.md)</span><span class="sxs-lookup"><span data-stu-id="7de19-111">MDM [Enrolled](hololens-enroll-mdm.md)</span></span>
- <span data-ttu-id="7de19-112">Geconfigureerd met [inrichtingspakket](hololens-provisioning.md)</span><span class="sxs-lookup"><span data-stu-id="7de19-112">Configured with [provisioning package](hololens-provisioning.md)</span></span>
- <span data-ttu-id="7de19-113">[Gebruikersidentiteit](hololens-identity.md) is Azure AD</span><span class="sxs-lookup"><span data-stu-id="7de19-113">User [Identity](hololens-identity.md) is Azure AD</span></span>

<span data-ttu-id="7de19-114">U kunt nu Apps installeren zonder dat u de ontwikkelaarsmodus hoeft in te schakelen of Apparaatportal.</span><span class="sxs-lookup"><span data-stu-id="7de19-114">You are now able to install Apps without needing to enable Developer Mode or using Device Portal.</span></span>  <span data-ttu-id="7de19-115">Download (via USB of via Microsoft Edge) de Appx-bundel naar uw apparaat en navigeer naar de Appx-bundel in de Bestandenverkenner om te worden gevraagd de installatie te beginnen.</span><span class="sxs-lookup"><span data-stu-id="7de19-115">Download (over USB or through Microsoft Edge) the Appx Bundle to your device and navigate to the Appx Bundle in the File Explorer to be prompted to kick off the installation.</span></span>  <span data-ttu-id="7de19-116">U kunt ook [een installatie starten vanaf een webpagina](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).</span><span class="sxs-lookup"><span data-stu-id="7de19-116">Alternatively, [initiate an install from a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).</span></span>  <span data-ttu-id="7de19-117">Net als apps die u installeert vanuit de Microsoft Store of sideloaden met behulp van de [](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) LOB App-implementatiefunctie van MDM, moeten apps digitaal worden ondertekend met het hulpprogramma voor ondertekenen en moet het certificaat dat wordt gebruikt om te ondertekenen, worden vertrouwd door het HoloLens-apparaat voordat de app kan worden geïmplementeerd. [](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations)</span><span class="sxs-lookup"><span data-stu-id="7de19-117">Just like apps you install from the Microsoft Store or sideload using MDM’s LOB App deployment capability, apps need to be digitally signed with the [Sign Tool](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) and the [certificate used to sign must be trusted](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) by the HoloLens device before the app can be deployed.</span></span>

## <a name="requirements"></a><span data-ttu-id="7de19-118">Vereisten</span><span class="sxs-lookup"><span data-stu-id="7de19-118">Requirements</span></span>

### <a name="for-your-devices"></a><span data-ttu-id="7de19-119">Voor uw apparaten:</span><span class="sxs-lookup"><span data-stu-id="7de19-119">For your devices:</span></span>

<span data-ttu-id="7de19-120">Deze functie is momenteel beschikbaar in Windows Holographic 20H2-builds voor HoloLens 2 apparaten.</span><span class="sxs-lookup"><span data-stu-id="7de19-120">This feature is currently available in Windows Holographic 20H2 builds for HoloLens 2 devices.</span></span> <span data-ttu-id="7de19-121">Zorg ervoor dat alle apparaten die deze methode gebruiken, [worden bijgewerkt.](hololens-update-hololens.md)</span><span class="sxs-lookup"><span data-stu-id="7de19-121">Ensure any devices using this method are [updated](hololens-update-hololens.md).</span></span>

### <a name="for-your-apps"></a><span data-ttu-id="7de19-122">Voor uw apps:</span><span class="sxs-lookup"><span data-stu-id="7de19-122">For your apps:</span></span>

<span data-ttu-id="7de19-123">De oplossingsconfiguratie van uw  app moet Master of **Release** zijn, omdat App-installatieprogramma afhankelijkheden uit de store gebruikt.</span><span class="sxs-lookup"><span data-stu-id="7de19-123">Your app’s Solution Configuration must be either **Master** or **Release** as the App Installer will use dependencies from the store.</span></span> <span data-ttu-id="7de19-124">Zie meer over het [maken van app-pakketten.](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs)</span><span class="sxs-lookup"><span data-stu-id="7de19-124">See more about [creating app packages](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).</span></span>

<span data-ttu-id="7de19-125">Apps die via deze methode worden geïnstalleerd, moeten digitaal worden ondertekend.</span><span class="sxs-lookup"><span data-stu-id="7de19-125">Apps that are installed via this method must be digitally signed.</span></span> <span data-ttu-id="7de19-126">U moet een certificaat gebruiken om de app te ondertekenen.</span><span class="sxs-lookup"><span data-stu-id="7de19-126">You'll need to use a certificate to sign the app.</span></span> <span data-ttu-id="7de19-127">U kunt een certificaat verkrijgen uit de lijst met vertrouwde [MS-CA's.](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)In dat geval hoeft u geen extra actie te ondernemen.</span><span class="sxs-lookup"><span data-stu-id="7de19-127">You can either get a certificate from the [MS Trusted CA List](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT), in which case you won't need to take any extra action.</span></span> <span data-ttu-id="7de19-128">U kunt ook uw eigen certificaat ondertekenen, maar dat certificaat moet naar het apparaat worden pushen.</span><span class="sxs-lookup"><span data-stu-id="7de19-128">Or you can sign your own certificate however that certificate will need to be pushed onto the device.</span></span>

- <span data-ttu-id="7de19-129">Apps ondertekenen met [het hulpprogramma Sign.](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span><span class="sxs-lookup"><span data-stu-id="7de19-129">How to sign apps [using the Sign Tool.](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span></span>

<span data-ttu-id="7de19-130">**Certificaatopties:**</span><span class="sxs-lookup"><span data-stu-id="7de19-130">**Certificate options:**</span></span>

- [<span data-ttu-id="7de19-131">Lijst met vertrouwde MS-CA's</span><span class="sxs-lookup"><span data-stu-id="7de19-131">MS Trusted CA List</span></span>](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

<span data-ttu-id="7de19-132">**Kies een certificaatimplementatiemethode.**</span><span class="sxs-lookup"><span data-stu-id="7de19-132">**Pick a certificate deployment method.**</span></span>

- <span data-ttu-id="7de19-133">[Inrichtingspakketten kunnen](hololens-provisioning.md) worden toegepast op lokale apparaten.</span><span class="sxs-lookup"><span data-stu-id="7de19-133">[Provisioning Packages](hololens-provisioning.md) can be applied to local devices.</span></span>
- <span data-ttu-id="7de19-134">MDM kan worden gebruikt om [certificaten toe te passen met apparaatconfiguraties.](https://docs.microsoft.com/mem/intune/protect/certificates-configure)</span><span class="sxs-lookup"><span data-stu-id="7de19-134">MDM can be used to [apply certificates with device configurations](https://docs.microsoft.com/mem/intune/protect/certificates-configure).</span></span>
- <span data-ttu-id="7de19-135">Gebruik de op het [apparaat Certificate Manager.](certificate-manager.md)</span><span class="sxs-lookup"><span data-stu-id="7de19-135">Use the on device [Certificate Manager](certificate-manager.md).</span></span>

## <a name="installation-method"></a><span data-ttu-id="7de19-136">Installatiemethode</span><span class="sxs-lookup"><span data-stu-id="7de19-136">Installation method</span></span>

1. <span data-ttu-id="7de19-137">Controleer of uw apparaat niet wordt beschouwd als beheerd.</span><span class="sxs-lookup"><span data-stu-id="7de19-137">Check that your device is not considered managed.</span></span>
1. <span data-ttu-id="7de19-138">Controleer of uw HoloLens 2 is ingeschakeld en of u bent aangemeld.</span><span class="sxs-lookup"><span data-stu-id="7de19-138">Check that your HoloLens 2 device is powered on and you are signed in.</span></span>
1. <span data-ttu-id="7de19-139">Navigeer op uw pc naar uw aangepaste app en kopieer yourapp.appxbundle naar yourdevicename\Internal Storage\Downloads.</span><span class="sxs-lookup"><span data-stu-id="7de19-139">On your PC navigate to your custom app, and copy yourapp.appxbundle to yourdevicename\Internal Storage\Downloads.</span></span>
    <span data-ttu-id="7de19-140">Nadat u klaar bent met het kopiëren van het bestand, kunt u de verbinding met uw apparaat verbreken en de installatie later voltooien.</span><span class="sxs-lookup"><span data-stu-id="7de19-140">After you finish copying your file, you may disconnect your device and finish the install later.</span></span>
1. <span data-ttu-id="7de19-141">Open HoloLens 2 startmenu op uw **apparaat,** selecteer Alle apps **start** de **Verkenner-app.**</span><span class="sxs-lookup"><span data-stu-id="7de19-141">From your HoloLens 2 device Open the **Start Menu**, select **All apps** and launch the **File Explorer** app.</span></span>
1. <span data-ttu-id="7de19-142">Navigeer naar de map Downloads.</span><span class="sxs-lookup"><span data-stu-id="7de19-142">Navigate to the Downloads folder.</span></span> <span data-ttu-id="7de19-143">Mogelijk moet u eerst Dit apparaat  selecteren in het linkerpaneel van de app en vervolgens naar Downloads navigeren.</span><span class="sxs-lookup"><span data-stu-id="7de19-143">You may need to on the left panel of the app select **This device** first, then navigate to Downloads.</span></span>
1. <span data-ttu-id="7de19-144">Selecteer het bestand yourapp.appxbundle.</span><span class="sxs-lookup"><span data-stu-id="7de19-144">Select the yourapp.appxbundle file.</span></span>
1. <span data-ttu-id="7de19-145">De App-installatieprogramma wordt start.</span><span class="sxs-lookup"><span data-stu-id="7de19-145">The App Installer will launch.</span></span> <span data-ttu-id="7de19-146">Selecteer de **knop Installeren** om uw app te installeren.</span><span class="sxs-lookup"><span data-stu-id="7de19-146">Select the **Install** button to install your app.</span></span>

<span data-ttu-id="7de19-147">De geïnstalleerde app wordt automatisch start na voltooiing van de installatie.</span><span class="sxs-lookup"><span data-stu-id="7de19-147">The installed app will automatically launch upon the completion of installing.</span></span>

![MRTK-voorbeelden installeren via App-installatieprogramma](images/hololens-app-installer-picture.jpg)

### <a name="troubleshooting-installs"></a><span data-ttu-id="7de19-149">Problemen met installaties oplossen</span><span class="sxs-lookup"><span data-stu-id="7de19-149">Troubleshooting Installs</span></span>

<span data-ttu-id="7de19-150">Als de installatie van uw app is mislukt, controleert u het volgende om het probleem op te lossen:</span><span class="sxs-lookup"><span data-stu-id="7de19-150">If your app failed to install,  check the following to troubleshoot:</span></span>

- <span data-ttu-id="7de19-151">Uw app is een master- of release-build.</span><span class="sxs-lookup"><span data-stu-id="7de19-151">Your app is either a Master or Release build.</span></span>
- <span data-ttu-id="7de19-152">Uw apparaat wordt bijgewerkt naar een build waarop deze functie beschikbaar is.</span><span class="sxs-lookup"><span data-stu-id="7de19-152">Your device is updated to a build on which this feature is available.</span></span>
- <span data-ttu-id="7de19-153">U bent [verbonden met internet.](hololens-network.md)</span><span class="sxs-lookup"><span data-stu-id="7de19-153">You are [connected to the internet](hololens-network.md).</span></span>
- <span data-ttu-id="7de19-154">Uw [eindpunten voor de Microsoft Store](hololens-offline.md) juist zijn geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="7de19-154">Your [endpoints for the Microsoft Store](hololens-offline.md) are correctly configured.</span></span>  

## <a name="web-installer"></a><span data-ttu-id="7de19-155">Web-installatieprogramma</span><span class="sxs-lookup"><span data-stu-id="7de19-155">Web Installer</span></span>

<span data-ttu-id="7de19-156">Gebruikers kunnen een app rechtstreeks vanaf een webserver installeren.</span><span class="sxs-lookup"><span data-stu-id="7de19-156">Users can install an app directly from a web server.</span></span> <span data-ttu-id="7de19-157">Deze stroom maakt gebruik van de App-installatieprogramma gecombineerd met een distributiemethode voor eenvoudig downloaden en installeren.</span><span class="sxs-lookup"><span data-stu-id="7de19-157">This flow takes use of the App Installer combined with an easy download and install distribution method.</span></span>

### <a name="how-to-set-up-web-install"></a><span data-ttu-id="7de19-158">Web-installatie instellen:</span><span class="sxs-lookup"><span data-stu-id="7de19-158">How to set up web install:</span></span>

1. <span data-ttu-id="7de19-159">Zorg ervoor dat uw app juist is geconfigureerd voor installatie.</span><span class="sxs-lookup"><span data-stu-id="7de19-159">Ensure your app is correctly configured to install.</span></span>
1. <span data-ttu-id="7de19-160">Volg deze [stappen om installatie vanaf een webpagina in teschakelen.](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage)</span><span class="sxs-lookup"><span data-stu-id="7de19-160">Follow these [steps to enable install from a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).</span></span>

### <a name="end-user-experience"></a><span data-ttu-id="7de19-161">Eindgebruikerservaring:</span><span class="sxs-lookup"><span data-stu-id="7de19-161">End user experience:</span></span>

1. <span data-ttu-id="7de19-162">De gebruiker ontvangt en installeert het certificaat op het apparaat met behulp van een methode die hierboven is gekozen.</span><span class="sxs-lookup"><span data-stu-id="7de19-162">User receives and installs certificate to the device using a method previously chosen above.</span></span>
1. <span data-ttu-id="7de19-163">De gebruiker bezoekt de URL die in de bovenstaande stap is gemaakt.</span><span class="sxs-lookup"><span data-stu-id="7de19-163">User visits the URL created from the step above.</span></span>

<span data-ttu-id="7de19-164">De app wordt nu op het apparaat geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="7de19-164">The app will now install to the device.</span></span> <span data-ttu-id="7de19-165">Als u de app wilt zoeken, opent **u Startmenu** selecteert u de **knop Alle apps** app te zoeken.</span><span class="sxs-lookup"><span data-stu-id="7de19-165">To find the app, open the **Start menu** and select the **All apps** button to find your app.</span></span>

- <span data-ttu-id="7de19-166">Ga naar Problemen met het app-installatieprogramma oplossen voor meer hulp bij het oplossen van problemen met de installatiemethode [voor het app-installatieprogramma.](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues)</span><span class="sxs-lookup"><span data-stu-id="7de19-166">For more help with troubleshooting the app installer installation method visit [troubleshoot app installer issues](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues).</span></span>

> [!NOTE]
> <span data-ttu-id="7de19-167">De gebruikersinterface tijdens het updateproces wordt niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="7de19-167">UI during the update process is not supported.</span></span> <span data-ttu-id="7de19-168">De optie ShowPrompt op deze [pagina en](https://docs.microsoft.com/windows/msix/app-installer/update-settings) de bijbehorende opties worden dus niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="7de19-168">So the ShowPrompt option on [this page](https://docs.microsoft.com/windows/msix/app-installer/update-settings) and related options are not supported.</span></span>

## <a name="sample-apps"></a><span data-ttu-id="7de19-169">Voorbeeld-apps</span><span class="sxs-lookup"><span data-stu-id="7de19-169">Sample Apps</span></span>

<span data-ttu-id="7de19-170">Probeer de App-installatieprogramma met een van onze beschikbare voorbeeld-apps.</span><span class="sxs-lookup"><span data-stu-id="7de19-170">Try out the App Installer with one of our available sample apps.</span></span> 
> [!div class="nextstepaction"]
> [<span data-ttu-id="7de19-171">Voorbeeld-apps</span><span class="sxs-lookup"><span data-stu-id="7de19-171">Sample apps</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/features-and-samples?tabs=unity#sample-apps)
