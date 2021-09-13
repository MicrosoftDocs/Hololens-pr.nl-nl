---
title: Bestanden zoeken en opslaan op HoloLens
description: Informatie over het gebruik van Verkenner op HoloLens om bestanden op uw apparaat te openen, weer te geven mixed reality beheren.
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
ms.openlocfilehash: 18dc962b869dafaea9ff9c605eef51fcbb35bfb2
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032552"
---
# <a name="find-open-and-save-files-on-hololens"></a>Bestanden zoeken, openen en opslaan op HoloLens

Bestanden die u op uw HoloLens, inclusief foto's en video's, worden rechtstreeks op uw HoloLens opgeslagen. U kunt ze op dezelfde manier weergeven en beheren als bestanden op Windows 10:

- De verkenner-app gebruiken voor toegang tot lokale mappen.
- Binnen de opslag van een app.
- In een speciale map (zoals de video- of muziekbibliotheek).
- Het gebruik van een opslagservice die een app en een bestands picker bevat (zoals OneDrive).
- Het gebruik van een desktopcomputer die is HoloLens met behulp van een USB-kabel, met behulp van MTP (Media Transfer Protocol) ondersteuning.

## <a name="view-files-on-hololens-using-file-explorer"></a>Bestanden op een HoloLens verkenner

> Is van toepassing op alle HoloLens 2-apparaten en HoloLens (eerste generatie) vanaf [de update van Windows 10 april 2018 (RS4) voor HoloLens](/windows/mixed-reality/release-notes-april-2018).

Gebruik Verkenner op HoloLens om bestanden op uw apparaat weer te geven en te beheren, waaronder 3D-objecten, documenten en afbeeldingen. Ga naar **Start**   >  **Alle apps**   >  **Bestandenverkenner om** aan de slag te gaan.

> [!TIP]
> Als er geen bestanden worden vermeld in Verkenner, selecteert u **Dit apparaat** in het linkerbovendeelvenster.

Als u geen bestanden ziet in Verkenner, is het filter Recent mogelijk actief (klokpictogram is gemarkeerd in het linkerdeelvenster). Als u dit wilt oplossen, **selecteert** u het documentpictogram Dit apparaat in het linkerdeelvenster (onder het klokpictogram) of opent u het menu en selecteert **u Dit apparaat.**

## <a name="find-and-view-your-photos-and-videos"></a>Uw foto's en video's zoeken en bekijken

[Met Mixed Reality Capture](holographic-photos-and-videos.md) kunt u foto mixed reality en video's maken op HoloLens.  Deze foto's en video's worden opgeslagen in de map Camera Roll van het apparaat.

U kunt foto's en video's die zijn gemaakt met HoloLens openen door:

- toegang tot de camera roll rechtstreeks via de [Foto's app](holographic-photos-and-videos.md).
- foto's en video's uploaden naar cloudopslag door uw foto's en video's te synchroniseren met OneDrive.
- met behulp Vastleggen in mixed reality pagina van de [Windows Apparaatportal](/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture).

### <a name="photos-app"></a>App Foto's

De Foto's app is een van de standaardapps in het menu **Start** en is ingebouwd met HoloLens. Meer informatie over het [gebruik van de Foto's-app om inhoud weer te geven.](holographic-photos-and-videos.md)

U kunt de app ook installeren [OneDrive van](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) de Microsoft Store om foto's te synchroniseren met andere apparaten.

### <a name="onedrive-app"></a>OneDrive app

[OneDrive](https://onedrive.live.com/) kunt u uw foto's en video's openen, beheren en delen met elk apparaat en met elke gebruiker. Als u toegang wilt krijgen tot de foto's en video HoloLens s die zijn vastgelegd op uw OneDrive, downloadt u de [app](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) Microsoft Store uw HoloLens. Nadat u de app hebt gedownload, opent OneDrive app en selecteert **Instellingen** Camera uploaden en selecteert u  >   **Camera uploaden.**

### <a name="connect-to-a-pc"></a>Verbinding maken naar een pc

Als op uw HoloLens de [update van Windows 10 april 2018 of](/windows/mixed-reality/release-notes-april-2018) hoger wordt uitgevoerd, kunt u uw HoloLens verbinden met een Windows 10-pc met behulp van een USB-kabel om foto's en video's op het apparaat te bekijken met behulp van MTP (mediaoverdrachtprotocol). U moet ervoor zorgen dat het apparaat is ontgrendeld om door bestanden te bladeren als u een pincode of wachtwoord hebt ingesteld op uw apparaat.  

Als u de Windows Apparaatportal [hebt](/windows/mixed-reality/using-the-windows-device-portal)ingeschakeld, kunt u deze gebruiken om te bladeren, op te halen en de foto's en video's te beheren die op uw apparaat zijn opgeslagen.

## <a name="access-files-within-an-app"></a>Toegang tot bestanden in een app

Als een toepassing bestanden op uw apparaat opgeslagen, kunt u die toepassing gebruiken om er toegang toe te krijgen.

### <a name="requesting-files-from-another-app"></a>Bestanden aanvragen bij een andere app

Een toepassing kan een aanvraag indienen om een bestand op te slaan of een bestand te openen vanuit een andere app met behulp van [bestands pickers](/windows/mixed-reality/app-model#file-pickers).

### <a name="known-folders"></a>Bekende mappen

HoloLens ondersteunt een aantal bekende [mappen die](/windows/mixed-reality/app-model#known-folders) apps kunnen aanvragen om toegang te krijgen.

## <a name="view-hololens-files-on-your-pc"></a>Uw HoloLens op uw pc weergeven

Net als bij andere mobiele apparaten maakt u HoloLens verbinding met uw desktopcomputer met behulp van MTP (Media Transfer Protocol) en opent u Verkenner op de pc voor toegang tot uw HoloLens-bibliotheken voor eenvoudige overdracht.

Uw bestanden HoloLens in Verkenner op uw pc weergeven:

1. Meld u aan bij HoloLens sluit deze vervolgens aan op de pc met behulp van de USB-kabel die bij de HoloLens.

1. Selecteer **Apparaat openen om bestanden weer te geven met Verkenner** of open Verkenner op de pc en navigeer naar het apparaat.

Als u informatie over uw HoloLens, klikt u met de rechtermuisknop op de apparaatnaam in Verkenner op uw pc en selecteert u **vervolgens Eigenschappen.**

> [!NOTE]
> HoloLens (eerste generatie) biedt geen ondersteuning voor het maken van verbinding met externe harde schijven of SD-kaarten.

## <a name="sync-to-the-cloud"></a>Synchroniseren met de cloud

Als u foto's en andere bestanden van uw HoloLens wilt synchroniseren met de cloud, installeert en stelt u OneDrive in HoloLens. Als u OneDrive wilt, zoekt u deze in de Microsoft Store op uw HoloLens.

HoloLens maakt geen back-up van app-bestanden en -gegevens, dus is het een goed idee om uw belangrijke zaken op te slaan in OneDrive. Op die manier wordt er een back-up van uw gegevens als u uw apparaat opnieuw instuurt of een app verwijdert.
