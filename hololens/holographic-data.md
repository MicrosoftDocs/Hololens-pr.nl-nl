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
ms.openlocfilehash: ad210c9d31d8d7c226345618b6dfabf8457ee2398882935920d7b3217259a644
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/05/2021
ms.locfileid: "115664873"
---
# <a name="find-open-and-save-files-on-hololens"></a>Bestanden zoeken, openen en opslaan op HoloLens

Bestanden die u op uw HoloLens, inclusief foto's en video's, worden rechtstreeks op uw HoloLens opgeslagen. Bekijk en beheer ze op dezelfde manier als u bestanden op uw Windows 10:

- De app Bestandenverkenner gebruiken voor toegang tot lokale mappen.
- Binnen de opslag van een app.
- In een speciale map (zoals de video- of muziekbibliotheek).
- Het gebruik van een opslagservice met een app en een bestandsverlener (zoals OneDrive).
- Een desktopcomputer gebruiken die is verbonden met uw HoloLens met behulp van een USB-kabel, met behulp van MTP -ondersteuning (Media Transfer Protocol).

## <a name="view-files-on-hololens-using-file-explorer"></a>Bestanden op een HoloLens met behulp van Verkenner

> Is van toepassing op alle HoloLens 2-apparaten en HoloLens (eerste generatie) vanaf de update van Windows 10 april [2018 (RS4) voor HoloLens](/windows/mixed-reality/release-notes-april-2018).

Gebruik Verkenner op HoloLens om bestanden op uw apparaat weer te geven en te beheren, waaronder 3D-objecten, documenten en afbeeldingen. Ga naar **Start**   >  **Alle apps**   >  **Verkenner om** aan de slag te gaan.

> [!TIP]
> Als er geen bestanden worden vermeld in Verkenner, selecteert u **Dit apparaat** in het linkerbovendeelvenster.

Als u geen bestanden ziet in Verkenner, is het filter Recent mogelijk actief (klokpictogram is gemarkeerd in het linkerdeelvenster). Als u dit wilt oplossen, selecteert u **het** documentpictogram Dit apparaat in het linkerdeelvenster (onder het klokpictogram) of opent u het menu en selecteert **u Dit apparaat.**

## <a name="find-and-view-your-photos-and-videos"></a>Uw foto's en video's zoeken en bekijken

[Met Mixed Reality Capture](holographic-photos-and-videos.md) kunt u mixed reality foto's en video's op HoloLens.  Deze foto's en video's worden opgeslagen in de map Camera Roll van het apparaat.

U kunt foto's en video's bekijken die zijn gemaakt met HoloLens door:

- toegang tot de Camera Roll rechtstreeks via de [Foto's app](holographic-photos-and-videos.md).
- foto's en video's uploaden naar cloudopslag door uw foto's en video's te synchroniseren met OneDrive.
- met behulp Vastleggen in mixed reality pagina van de [Windows Apparaatportal](/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture).

### <a name="photos-app"></a>App Foto's

De Foto's-app is een van de standaard-apps in het menu **Start** en is ingebouwd met HoloLens. Meer informatie over het [gebruik van de Foto's-app om inhoud weer te geven.](holographic-photos-and-videos.md)

U kunt ook de app [OneDrive van](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) de Microsoft Store om foto's te synchroniseren met andere apparaten.

### <a name="onedrive-app"></a>OneDrive app

[OneDrive](https://onedrive.live.com/) kunt u uw foto's en video's openen, beheren en delen met elk apparaat en met elke gebruiker. Als u toegang wilt krijgen tot de foto HoloLens en video's die op uw HoloLens zijn vastgelegd, downloadt u de [OneDrive-app](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) via de Microsoft Store op uw HoloLens. Nadat u de app hebt gedownload, opent OneDrive app en selecteert u Instellingen Camera uploaden en zet  >  u Camera **uploaden in.**

### <a name="connect-to-a-pc"></a>Verbinding maken naar een pc

Als op uw HoloLens de [update van Windows 10 april 2018 of](/windows/mixed-reality/release-notes-april-2018) hoger wordt uitgevoerd, kunt u uw HoloLens verbinden met een Windows 10-pc met behulp van een USB-kabel om door foto's en video's op het apparaat te bladeren met behulp van MTP (mediaoverdrachtprotocol). U moet ervoor zorgen dat het apparaat is ontgrendeld om door bestanden te bladeren als u een pincode of wachtwoord op uw apparaat hebt ingesteld.  

Als u de Windows Apparaatportal hebt [ingeschakeld,](/windows/mixed-reality/using-the-windows-device-portal)kunt u deze gebruiken om de foto's en video's die op uw apparaat zijn opgeslagen te bladeren, op te halen en te beheren.

## <a name="access-files-within-an-app"></a>Toegang tot bestanden in een app

Als een toepassing bestanden op uw apparaat opgeslagen, kunt u die toepassing gebruiken om er toegang toe te krijgen.

### <a name="requesting-files-from-another-app"></a>Bestanden aanvragen bij een andere app

Een toepassing kan een aanvraag indienen om een bestand op te slaan of een bestand te openen vanuit een andere app met behulp van [bestands pickers](/windows/mixed-reality/app-model#file-pickers).

### <a name="known-folders"></a>Bekende mappen

HoloLens ondersteunt een aantal bekende [mappen die](/windows/mixed-reality/app-model#known-folders) apps kunnen aanvragen om toegang te krijgen.

## <a name="view-hololens-files-on-your-pc"></a>Bestanden HoloLens uw pc weergeven

Net als bij andere mobiele apparaten maakt u HoloLens verbinding met uw desktopcomputer met behulp van MTP (Media Transfer Protocol) en opent u Verkenner op de pc voor toegang tot uw HoloLens-bibliotheken voor eenvoudige overdracht.

Als u uw bestanden HoloLens in Verkenner op uw pc:

1. Meld u aan bij HoloLens sluit deze vervolgens aan op de pc met behulp van de USB-kabel die bij de HoloLens.

1. Selecteer **Apparaat openen om bestanden weer te geven met Verkenner** of open Verkenner op de pc en navigeer naar het apparaat.

Als u informatie over uw HoloLens, klikt u met de rechtermuisknop op de apparaatnaam in Verkenner op uw pc en selecteert u **vervolgens Eigenschappen.**

> [!NOTE]
> HoloLens (eerste generatie) biedt geen ondersteuning voor het maken van verbinding met externe harde schijven of SD-kaarten.

## <a name="sync-to-the-cloud"></a>Synchroniseren met de cloud

Als u foto's en andere bestanden van uw HoloLens wilt synchroniseren met de cloud, installeert en stelt u de OneDrive in HoloLens. Als u OneDrive wilt, zoekt u deze in de Microsoft Store op uw HoloLens.

HoloLens maakt geen back-up van app-bestanden en -gegevens, dus is het een goed idee om uw belangrijke zaken op te slaan in OneDrive. Op die manier wordt er een back-up van uw gegevens als u uw apparaat opnieuw instuurt of een app verwijdert.
