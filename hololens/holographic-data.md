---
title: Bestanden zoeken en opslaan op HoloLens
description: Meer informatie over het gebruik van Verkenner op HoloLens om bestanden op uw apparaat te openen, weer te geven mixed reality beheren.
keywords: how-to, file picker, files, photos, videos, pictures, OneDrive, storage, file explorer, hololens
ms.assetid: 77d2e357-f65f-43c8-b62f-6cd9bf37070a
author: mattzmsft
ms.author: mazeller
manager: v-miegge
ms.reviewer: jarrettrenshaw
ms.date: 12/30/2019
ms.prod: hololens
ms.sitesec: library
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 2d979b2cffd20589ddef7f11db5c7206eaea23cb
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/19/2021
ms.locfileid: "111377789"
---
# <a name="find-open-and-save-files-on-hololens"></a><span data-ttu-id="a387f-104">Bestanden zoeken, openen en opslaan op HoloLens</span><span class="sxs-lookup"><span data-stu-id="a387f-104">Find, open, and save files on HoloLens</span></span>

<span data-ttu-id="a387f-105">Bestanden die u op HoloLens maakt, inclusief foto's en video's, worden rechtstreeks opgeslagen op uw HoloLens-apparaat.</span><span class="sxs-lookup"><span data-stu-id="a387f-105">Files you create on HoloLens, including photos and videos, are saved directly to your HoloLens device.</span></span> <span data-ttu-id="a387f-106">U kunt ze op dezelfde manier weergeven en beheren als bestanden op Windows 10:</span><span class="sxs-lookup"><span data-stu-id="a387f-106">View and manage them in the same way you would manage files on Windows 10:</span></span>

- <span data-ttu-id="a387f-107">De verkenner-app gebruiken voor toegang tot lokale mappen.</span><span class="sxs-lookup"><span data-stu-id="a387f-107">Using the File Explorer app to access local folders.</span></span>
- <span data-ttu-id="a387f-108">Binnen de opslag van een app.</span><span class="sxs-lookup"><span data-stu-id="a387f-108">Within an app's storage.</span></span>
- <span data-ttu-id="a387f-109">In een speciale map (zoals de video- of muziekbibliotheek).</span><span class="sxs-lookup"><span data-stu-id="a387f-109">In a special folder (such as the video or music library).</span></span>
- <span data-ttu-id="a387f-110">Het gebruik van een opslagservice die een app en een bestands picker (zoals OneDrive) bevat.</span><span class="sxs-lookup"><span data-stu-id="a387f-110">Using a storage service that includes an app and file picker (such as OneDrive).</span></span>
- <span data-ttu-id="a387f-111">Het gebruik van een desktopcomputer die is verbonden met uw HoloLens via een USB-kabel, met behulp van MTP-ondersteuning (Media Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="a387f-111">Using a desktop PC connected to your HoloLens by using a USB cable, using MTP (Media Transfer Protocol) support.</span></span>

## <a name="view-files-on-hololens-using-file-explorer"></a><span data-ttu-id="a387f-112">Bestanden op HoloLens weergeven met verkenner</span><span class="sxs-lookup"><span data-stu-id="a387f-112">View files on HoloLens using File Explorer</span></span>

> <span data-ttu-id="a387f-113">Is van toepassing op HoloLens 2 apparaten en HoloLens (1e generatie) vanaf de [Update voor Windows 10, april 2018 (RS4) voor HoloLens.](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018)</span><span class="sxs-lookup"><span data-stu-id="a387f-113">Applies to all HoloLens 2 devices and HoloLens (1st gen) as of the [Windows 10 April 2018 Update (RS4) for HoloLens](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018).</span></span>

<span data-ttu-id="a387f-114">Gebruik Verkenner op HoloLens om bestanden op uw apparaat weer te geven en te beheren, waaronder 3D-objecten, documenten en afbeeldingen.</span><span class="sxs-lookup"><span data-stu-id="a387f-114">Use File Explorer on HoloLens to view and manage files on your device, including 3D objects, documents, and pictures.</span></span> <span data-ttu-id="a387f-115">Ga naar **Start**   >  **Alle apps**   >  **Bestandenverkenner om** aan de slag te gaan.</span><span class="sxs-lookup"><span data-stu-id="a387f-115">Go to **Start**  > **All apps**  > **File Explorer** to get started.</span></span>

> [!TIP]
> <span data-ttu-id="a387f-116">Als er geen bestanden worden vermeld in Verkenner, selecteert u **Dit apparaat** in het linkerbovendeelvenster.</span><span class="sxs-lookup"><span data-stu-id="a387f-116">If there are no files listed in File Explorer, select **This Device** in the top left pane.</span></span>

<span data-ttu-id="a387f-117">Als u geen bestanden ziet in Verkenner, is het filter Recent mogelijk actief (klokpictogram is gemarkeerd in het linkerdeelvenster).</span><span class="sxs-lookup"><span data-stu-id="a387f-117">If you don’t see any files in File Explorer, the "Recent" filter may be active (clock icon is highlighted in left pane).</span></span> <span data-ttu-id="a387f-118">Als u dit wilt oplossen, **selecteert** u het documentpictogram Dit apparaat in het linkerdeelvenster (onder het klokpictogram) of opent u het menu en selecteert **u Dit apparaat.**</span><span class="sxs-lookup"><span data-stu-id="a387f-118">To fix this, select the **This Device** document icon in the left pane (beneath the clock icon), or open the menu and select **This Device**.</span></span>

## <a name="find-and-view-your-photos-and-videos"></a><span data-ttu-id="a387f-119">Uw foto's en video's zoeken en bekijken</span><span class="sxs-lookup"><span data-stu-id="a387f-119">Find and view your photos and videos</span></span>

<span data-ttu-id="a387f-120">[Met Mixed Reality Capture](holographic-photos-and-videos.md) kunt u mixed reality foto's en video's maken op HoloLens.</span><span class="sxs-lookup"><span data-stu-id="a387f-120">[Mixed reality capture](holographic-photos-and-videos.md) lets you take mixed reality photos and videos on HoloLens.</span></span>  <span data-ttu-id="a387f-121">Deze foto's en video's worden opgeslagen in de map Camera Roll van het apparaat.</span><span class="sxs-lookup"><span data-stu-id="a387f-121">These photos and videos are saved to the device's Camera Roll folder.</span></span>

<span data-ttu-id="a387f-122">U hebt toegang tot foto's en video's die zijn gemaakt met HoloLens door:</span><span class="sxs-lookup"><span data-stu-id="a387f-122">You can access photos and videos taken with HoloLens by:</span></span>

- <span data-ttu-id="a387f-123">de camera-roll rechtstreeks via de [app Photos te openen.](holographic-photos-and-videos.md)</span><span class="sxs-lookup"><span data-stu-id="a387f-123">accessing the Camera Roll directly through the [Photos app](holographic-photos-and-videos.md).</span></span>
- <span data-ttu-id="a387f-124">foto's en video's uploaden naar cloudopslag door uw foto's en video's te synchroniseren met OneDrive.</span><span class="sxs-lookup"><span data-stu-id="a387f-124">uploading photos and videos to cloud storage by syncing your photos and videos to OneDrive.</span></span>
- <span data-ttu-id="a387f-125">met behulp Vastleggen in mixed reality pagina van de [Windows Apparaatportal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture).</span><span class="sxs-lookup"><span data-stu-id="a387f-125">using the Mixed Reality Capture page of the [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture).</span></span>

### <a name="photos-app"></a><span data-ttu-id="a387f-126">App Foto's</span><span class="sxs-lookup"><span data-stu-id="a387f-126">Photos app</span></span>

<span data-ttu-id="a387f-127">De app Photos is een van de standaard-apps in het menu **Start** en is ingebouwd in HoloLens.</span><span class="sxs-lookup"><span data-stu-id="a387f-127">The Photos app is one of the default apps on the **Start** menu, and comes built-in with HoloLens.</span></span> <span data-ttu-id="a387f-128">Meer informatie over het [gebruik van de app Foto's om inhoud weer te geven.](holographic-photos-and-videos.md)</span><span class="sxs-lookup"><span data-stu-id="a387f-128">Learn more about [using the Photos app to view content](holographic-photos-and-videos.md).</span></span>

<span data-ttu-id="a387f-129">U kunt de [OneDrive-app](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) ook installeren vanuit de Microsoft Store om foto's te synchroniseren met andere apparaten.</span><span class="sxs-lookup"><span data-stu-id="a387f-129">You can also install the [OneDrive app](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) from the Microsoft Store to sync photos to other devices.</span></span>

### <a name="onedrive-app"></a><span data-ttu-id="a387f-130">OneDrive-app</span><span class="sxs-lookup"><span data-stu-id="a387f-130">OneDrive app</span></span>

<span data-ttu-id="a387f-131">[Met OneDrive](https://onedrive.live.com/) kunt u uw foto's en video's openen, beheren en delen met elk apparaat en met elke gebruiker.</span><span class="sxs-lookup"><span data-stu-id="a387f-131">[OneDrive](https://onedrive.live.com/) lets you access, manage, and share your photos and videos with any device and with any user.</span></span> <span data-ttu-id="a387f-132">Als u toegang wilt krijgen tot de foto's en video's die zijn vastgelegd op HoloLens, downloadt u de [OneDrive-app](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) vanuit Microsoft Store HoloLens.</span><span class="sxs-lookup"><span data-stu-id="a387f-132">To access the photos and videos captured on HoloLens, download the [OneDrive app](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) from the Microsoft Store on your HoloLens.</span></span> <span data-ttu-id="a387f-133">Nadat u de OneDrive-app hebt gedownload, selecteert u **Instellingen**  >  **Camera uploaden** en zet u **Camera-upload in.**</span><span class="sxs-lookup"><span data-stu-id="a387f-133">Once downloaded, open the OneDrive app and select **Settings** > **Camera upload**, and turn on **Camera upload**.</span></span>

### <a name="connect-to-a-pc"></a><span data-ttu-id="a387f-134">Verbinding maken met een pc</span><span class="sxs-lookup"><span data-stu-id="a387f-134">Connect to a PC</span></span>

<span data-ttu-id="a387f-135">Als op uw HoloLens de [update van Windows 10 april 2018 of](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) hoger wordt uitgevoerd, kunt u uw HoloLens verbinden met een Windows 10-pc met behulp van een USB-kabel om door foto's en video's op het apparaat te bladeren met behulp van MTP (mediaoverdrachtprotocol).</span><span class="sxs-lookup"><span data-stu-id="a387f-135">If your HoloLens is running the [Windows 10 April 2018 update](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) or later, you can connect your HoloLens to a Windows 10 PC by using a USB cable to browse photos and videos on the device by using MTP (media transfer protocol).</span></span> <span data-ttu-id="a387f-136">U moet ervoor zorgen dat het apparaat is ontgrendeld om door bestanden te bladeren als u een pincode of wachtwoord hebt ingesteld op uw apparaat.</span><span class="sxs-lookup"><span data-stu-id="a387f-136">You'll need to make sure the device is unlocked to browse files if you have a PIN or password set up on your device.</span></span>  

<span data-ttu-id="a387f-137">Als u de Windows Apparaatportal hebt [ingeschakeld,](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)kunt u deze gebruiken om de foto's en video's die op uw apparaat zijn opgeslagen te bladeren, op te halen en te beheren.</span><span class="sxs-lookup"><span data-stu-id="a387f-137">If you have enabled the [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal), you can use it to browse, retrieve, and manage the photos and videos stored on your device.</span></span>

## <a name="access-files-within-an-app"></a><span data-ttu-id="a387f-138">Toegang tot bestanden in een app</span><span class="sxs-lookup"><span data-stu-id="a387f-138">Access files within an app</span></span>

<span data-ttu-id="a387f-139">Als een toepassing bestanden op uw apparaat opgeslagen, kunt u die toepassing gebruiken om er toegang toe te krijgen.</span><span class="sxs-lookup"><span data-stu-id="a387f-139">If an application saves files on your device, you can use that application to access them.</span></span>

### <a name="requesting-files-from-another-app"></a><span data-ttu-id="a387f-140">Bestanden aanvragen bij een andere app</span><span class="sxs-lookup"><span data-stu-id="a387f-140">Requesting files from another app</span></span>

<span data-ttu-id="a387f-141">Een toepassing kan een aanvraag indienen om een bestand op te slaan of een bestand te openen vanuit een andere app met behulp van [bestands pickers](https://docs.microsoft.com/windows/mixed-reality/app-model#file-pickers).</span><span class="sxs-lookup"><span data-stu-id="a387f-141">An application can request to save a file or open a file from another app by using [file pickers](https://docs.microsoft.com/windows/mixed-reality/app-model#file-pickers).</span></span>

### <a name="known-folders"></a><span data-ttu-id="a387f-142">Bekende mappen</span><span class="sxs-lookup"><span data-stu-id="a387f-142">Known folders</span></span>

<span data-ttu-id="a387f-143">HoloLens ondersteunt een aantal bekende [mappen die](https://docs.microsoft.com/windows/mixed-reality/app-model#known-folders) apps kunnen aanvragen om toegang te krijgen.</span><span class="sxs-lookup"><span data-stu-id="a387f-143">HoloLens supports a number of [known folders](https://docs.microsoft.com/windows/mixed-reality/app-model#known-folders) that apps can request permission to access.</span></span>

## <a name="view-hololens-files-on-your-pc"></a><span data-ttu-id="a387f-144">HoloLens-bestanden weergeven op uw pc</span><span class="sxs-lookup"><span data-stu-id="a387f-144">View HoloLens files on your PC</span></span>

<span data-ttu-id="a387f-145">Net als bij andere mobiele apparaten verbindt u HoloLens met uw desktop-pc met behulp van MTP (Media Transfer Protocol) en opent u Verkenner op de pc voor toegang tot uw HoloLens-bibliotheken voor eenvoudige overdracht.</span><span class="sxs-lookup"><span data-stu-id="a387f-145">Similar to other mobile devices, connect HoloLens to your desktop PC using MTP (Media Transfer Protocol) and open File Explorer on the PC to access your HoloLens libraries for easy transfer.</span></span>

<span data-ttu-id="a387f-146">Uw HoloLens-bestanden weergeven in Verkenner op uw pc:</span><span class="sxs-lookup"><span data-stu-id="a387f-146">To see your HoloLens files in File Explorer on your PC:</span></span>

1. <span data-ttu-id="a387f-147">Meld u aan bij HoloLens en sluit deze vervolgens aan op de pc met behulp van de USB-kabel die bij de HoloLens is meegeleverd.</span><span class="sxs-lookup"><span data-stu-id="a387f-147">Sign in to HoloLens, then plug it into the PC using the USB cable that came with the HoloLens.</span></span>

1. <span data-ttu-id="a387f-148">Selecteer **Apparaat openen om bestanden weer te geven met Verkenner** of open Verkenner op de pc en navigeer naar het apparaat.</span><span class="sxs-lookup"><span data-stu-id="a387f-148">Select **Open Device to view files with File Explorer**, or open File Explorer on the PC and navigate to the device.</span></span>

<span data-ttu-id="a387f-149">Als u informatie over uw HoloLens wilt bekijken, klikt u met de rechtermuisknop op de naam van het apparaat in Verkenner op uw pc en selecteert u **vervolgens Eigenschappen.**</span><span class="sxs-lookup"><span data-stu-id="a387f-149">To see info about your HoloLens, right-click the device name in File Explorer on your PC, then select **Properties**.</span></span>

> [!NOTE]
> <span data-ttu-id="a387f-150">HoloLens (1e generatie) biedt geen ondersteuning voor het maken van verbinding met externe harde schijven of SD-kaarten.</span><span class="sxs-lookup"><span data-stu-id="a387f-150">HoloLens (1st gen) does not support connecting to external hard drives or SD cards.</span></span>

## <a name="sync-to-the-cloud"></a><span data-ttu-id="a387f-151">Synchroniseren met de cloud</span><span class="sxs-lookup"><span data-stu-id="a387f-151">Sync to the cloud</span></span>

<span data-ttu-id="a387f-152">Als u foto's en andere bestanden van uw HoloLens wilt synchroniseren met de cloud, installeert en stelt u OneDrive in HoloLens in.</span><span class="sxs-lookup"><span data-stu-id="a387f-152">To sync photos and other files from your HoloLens to the cloud, install and set up OneDrive on HoloLens.</span></span> <span data-ttu-id="a387f-153">Als u OneDrive wilt krijgen, zoekt u deze in de Microsoft Store hololens.</span><span class="sxs-lookup"><span data-stu-id="a387f-153">To get OneDrive, search for it in the Microsoft Store on your HoloLens.</span></span>

<span data-ttu-id="a387f-154">HoloLens maakt geen back-up van app-bestanden en -gegevens, dus is het een goed idee om uw belangrijke zaken op te slaan in OneDrive.</span><span class="sxs-lookup"><span data-stu-id="a387f-154">HoloLens doesn't back up app files and data, so it's a good idea to save your important stuff to OneDrive.</span></span> <span data-ttu-id="a387f-155">Op die manier wordt er een back-up van uw gegevens als u uw apparaat opnieuw instuurt of een app verwijdert.</span><span class="sxs-lookup"><span data-stu-id="a387f-155">That way, if you reset your device or uninstall an app, your info will be backed up.</span></span>
