---
title: Gelokaliseerde versies van de HoloLens
description: Meer informatie over het installeren van de gelokaliseerde versies van HoloLens (eerste generatie), waaronder Chinese en Japanse versies.
ms.prod: hololens
ms.mktglfcycl: manage
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
ms.openlocfilehash: 74eb003aafd23218b90988abe113d35f1fc3035a
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032801"
---
# <a name="install-localized-versions-of-hololens-1st-gen"></a>Gelokaliseerde versies van HoloLens (1e generatie) installeren

Als u wilt overschakelen naar de Chinese of Japanse versie van HoloLens, moet u de Windows Device Recovery Tool (WDRT) gebruiken om de build voor de taal te downloaden op een pc en deze vervolgens op uw HoloLens.

> [!IMPORTANT]
> Als u WDRT gebruikt om de Chinese of Japanse builds van HoloLens verwijdert u bestaande gegevens, zoals persoonlijke bestanden en instellingen, uit uw HoloLens. 

1. Download en installeer de Windows [Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379)op uw pc.
1. Download het pakket voor de taal die u op uw pc wilt: [Vereenvoudigd Chinees](https://aka.ms/hololensdownload-ch) of [Japans.](https://aka.ms/hololensdownload-jp)
1. Wanneer het downloaden is voltooien, selecteert **u**  >  **Bestandenverkenner Downloads.** Klik met de rechtermuisknop op de ingepakte map die u zojuist hebt gedownload en selecteer **Alles** uitpakken om het uit  >   tepakken.
1. Verbinding maken uw HoloLens naar uw pc met behulp van de micro-USB-kabel die wordt meegeleverd. (Zelfs als u andere kabels hebt gebruikt om uw HoloLens, werkt deze het beste.)
1. Nadat het hulpprogramma uw apparaat automatisch detecteert HoloLens selecteert u de Microsoft HoloLens tegel.
1. Selecteer in het **** volgende scherm Handmatige pakketselectie en selecteer het installatiebestand dat zich bevindt in de map die u in stap   4 hebt uitgepakt. (Zoek naar een bestand met de extensie ".ffu".) 
1. Selecteer **Software installeren** en volg de instructies. 
1. Nadat de build is geïnstalleerd, HoloLens de installatie automatisch gestart. Plaats het apparaat en volg de instructies voor het instellen. 

Wanneer u klaar bent met de installatie, gaat u naar **Instellingen** Update & Security Windows Insider-programma en controleert u of u bent geconfigureerd voor het ontvangen van de nieuwste  >    >  preview-builds. Net als bij de Engelse preview-builds houdt de Windows Insider-programma de Chinese en Japanse versies van HoloLens bijgewerkt met de nieuwste preview-builds.

> [!NOTE]
>  
> - U kunt de app Instellingen gebruiken om de systeemtaal te wijzigen tussen Engels, Japans en Chinees. Het flashen van een nieuwe build is de enige ondersteunde manier om de taal van het apparaatsysteem te wijzigen.
> - Hoewel u het scherm pinyin toetsenbord vereenvoudigd Chinees of Japans tekst invoeren kunt, met behulp van een Bluetooth hardware toetsenbord vereenvoudigd Chinees of Japans tekst wordt op dit moment niet ondersteund.  Op Chinese of Japanse HoloLens kunt u echter een Bluetooth-toetsenbord gebruiken om in het Engels te typen (als u een hardwaretoetsenbord in het Engels wilt typen, drukt u op de ~ toets).
