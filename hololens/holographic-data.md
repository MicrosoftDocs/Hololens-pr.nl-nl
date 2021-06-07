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
# <a name="find-open-and-save-files-on-hololens"></a>Bestanden zoeken, openen en opslaan op HoloLens

Bestanden die u op HoloLens maakt, inclusief foto's en video's, worden rechtstreeks opgeslagen op uw HoloLens-apparaat. U kunt ze op dezelfde manier weergeven en beheren als bestanden op Windows 10:

- De verkenner-app gebruiken voor toegang tot lokale mappen.
- Binnen de opslag van een app.
- In een speciale map (zoals de video- of muziekbibliotheek).
- Het gebruik van een opslagservice die een app en een bestands picker (zoals OneDrive) bevat.
- Het gebruik van een desktopcomputer die is verbonden met uw HoloLens via een USB-kabel, met behulp van MTP-ondersteuning (Media Transfer Protocol).

## <a name="view-files-on-hololens-using-file-explorer"></a>Bestanden op HoloLens weergeven met verkenner

> Is van toepassing op HoloLens 2 apparaten en HoloLens (1e generatie) vanaf de [Update voor Windows 10, april 2018 (RS4) voor HoloLens.](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018)

Gebruik Verkenner op HoloLens om bestanden op uw apparaat weer te geven en te beheren, waaronder 3D-objecten, documenten en afbeeldingen. Ga naar **Start**   >  **Alle apps**   >  **Bestandenverkenner om** aan de slag te gaan.

> [!TIP]
> Als er geen bestanden worden vermeld in Verkenner, selecteert u **Dit apparaat** in het linkerbovendeelvenster.

Als u geen bestanden ziet in Verkenner, is het filter Recent mogelijk actief (klokpictogram is gemarkeerd in het linkerdeelvenster). Als u dit wilt oplossen, **selecteert** u het documentpictogram Dit apparaat in het linkerdeelvenster (onder het klokpictogram) of opent u het menu en selecteert **u Dit apparaat.**

## <a name="find-and-view-your-photos-and-videos"></a>Uw foto's en video's zoeken en bekijken

[Met Mixed Reality Capture](holographic-photos-and-videos.md) kunt u mixed reality foto's en video's maken op HoloLens.  Deze foto's en video's worden opgeslagen in de map Camera Roll van het apparaat.

U hebt toegang tot foto's en video's die zijn gemaakt met HoloLens door:

- de camera-roll rechtstreeks via de [app Photos te openen.](holographic-photos-and-videos.md)
- foto's en video's uploaden naar cloudopslag door uw foto's en video's te synchroniseren met OneDrive.
- met behulp Vastleggen in mixed reality pagina van de [Windows Apparaatportal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture).

### <a name="photos-app"></a>App Foto's

De app Photos is een van de standaard-apps in het menu **Start** en is ingebouwd in HoloLens. Meer informatie over het [gebruik van de app Foto's om inhoud weer te geven.](holographic-photos-and-videos.md)

U kunt de [OneDrive-app](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) ook installeren vanuit de Microsoft Store om foto's te synchroniseren met andere apparaten.

### <a name="onedrive-app"></a>OneDrive-app

[Met OneDrive](https://onedrive.live.com/) kunt u uw foto's en video's openen, beheren en delen met elk apparaat en met elke gebruiker. Als u toegang wilt krijgen tot de foto's en video's die zijn vastgelegd op HoloLens, downloadt u de [OneDrive-app](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) vanuit Microsoft Store HoloLens. Nadat u de OneDrive-app hebt gedownload, selecteert u **Instellingen**  >  **Camera uploaden** en zet u **Camera-upload in.**

### <a name="connect-to-a-pc"></a>Verbinding maken met een pc

Als op uw HoloLens de [update van Windows 10 april 2018 of](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) hoger wordt uitgevoerd, kunt u uw HoloLens verbinden met een Windows 10-pc met behulp van een USB-kabel om door foto's en video's op het apparaat te bladeren met behulp van MTP (mediaoverdrachtprotocol). U moet ervoor zorgen dat het apparaat is ontgrendeld om door bestanden te bladeren als u een pincode of wachtwoord hebt ingesteld op uw apparaat.  

Als u de Windows Apparaatportal hebt [ingeschakeld,](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)kunt u deze gebruiken om de foto's en video's die op uw apparaat zijn opgeslagen te bladeren, op te halen en te beheren.

## <a name="access-files-within-an-app"></a>Toegang tot bestanden in een app

Als een toepassing bestanden op uw apparaat opgeslagen, kunt u die toepassing gebruiken om er toegang toe te krijgen.

### <a name="requesting-files-from-another-app"></a>Bestanden aanvragen bij een andere app

Een toepassing kan een aanvraag indienen om een bestand op te slaan of een bestand te openen vanuit een andere app met behulp van [bestands pickers](https://docs.microsoft.com/windows/mixed-reality/app-model#file-pickers).

### <a name="known-folders"></a>Bekende mappen

HoloLens ondersteunt een aantal bekende [mappen die](https://docs.microsoft.com/windows/mixed-reality/app-model#known-folders) apps kunnen aanvragen om toegang te krijgen.

## <a name="view-hololens-files-on-your-pc"></a>HoloLens-bestanden weergeven op uw pc

Net als bij andere mobiele apparaten verbindt u HoloLens met uw desktop-pc met behulp van MTP (Media Transfer Protocol) en opent u Verkenner op de pc voor toegang tot uw HoloLens-bibliotheken voor eenvoudige overdracht.

Uw HoloLens-bestanden weergeven in Verkenner op uw pc:

1. Meld u aan bij HoloLens en sluit deze vervolgens aan op de pc met behulp van de USB-kabel die bij de HoloLens is meegeleverd.

1. Selecteer **Apparaat openen om bestanden weer te geven met Verkenner** of open Verkenner op de pc en navigeer naar het apparaat.

Als u informatie over uw HoloLens wilt bekijken, klikt u met de rechtermuisknop op de naam van het apparaat in Verkenner op uw pc en selecteert u **vervolgens Eigenschappen.**

> [!NOTE]
> HoloLens (1e generatie) biedt geen ondersteuning voor het maken van verbinding met externe harde schijven of SD-kaarten.

## <a name="sync-to-the-cloud"></a>Synchroniseren met de cloud

Als u foto's en andere bestanden van uw HoloLens wilt synchroniseren met de cloud, installeert en stelt u OneDrive in HoloLens in. Als u OneDrive wilt krijgen, zoekt u deze in de Microsoft Store hololens.

HoloLens maakt geen back-up van app-bestanden en -gegevens, dus is het een goed idee om uw belangrijke zaken op te slaan in OneDrive. Op die manier wordt er een back-up van uw gegevens als u uw apparaat opnieuw instuurt of een app verwijdert.
