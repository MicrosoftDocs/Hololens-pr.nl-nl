---
title: 'Implementatiehandleiding : zakelijk verbonden HoloLens 2 met Dynamics 365 Guides - Implementeren'
description: Meer informatie over het instellen van implementaties van HoloLens 2 apparaten via een bedrijfsnetwerk verbonden met Dynamics 365 Guides.
keywords: HoloLens, beheer, verbonden bedrijf, Dynamics 365 Guides, AAD, Azure AD, MDM, Mobile Device Management
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 7df2b00b2d87be7b9ad4a5d84c83251ec0ebec4d
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032721"
---
# <a name="deploy---corporate-connected-guide"></a>Implementeren - Corporate Connected Guide

Een belangrijk onderdeel van elke implementatie is ervoor te zorgen dat uw implementatie goed is ingesteld voordat u deze zelf test om een soepele ervaring voor de eindgebruiker te garanderen.

Omdat we het Wi-Fi-certificaat via MDM implementeren, moeten we in eerste instantie HoloLens instellen en apparaten inschrijven in een open Wi-Fi-netwerk of een netwerk waarvoor het certificaat niet vereist is. Zodra de HoloLens OOBE heeft voltooid en ingeschreven, ontvangt het apparaat het netwerkcertificaat en de LOB die eerder zijn geconfigureerd en kunnen we controleren of beide zijn ontvangen door het apparaat.

Daarna kunt u bevestigen dat u zowel een testhandleiding kunt maken als gebruiken.

## <a name="enrollment-validation"></a>Validatie van inschrijving

Nu alles goed is geconfigureerd voor Azure AD- en MDM-inschrijving, is de rest nu een module. U hebt een Wi-Fi- en HoloLens apparaat en een van de eerder geconfigureerde Azure AD-gebruikersaccounts nodig.

Als uw apparaat momenteel niet de status fabrieksinstellingen heeft, is dit een goed moment om het apparaat opnieuw [te gebruiken.](/hololens/hololens-recovery#clean-reflash-the-device)

1. Zodra uw apparaat zich in OOBE heeft, moet u beginnen met de interactie en de aanwijzingen volgen.

2. Verbinding maken verbinding maken met een Wi-Fi netwerk waarvoor geen certificaten nodig zijn om lid te worden van de Wi-Fi. Hierdoor kan het apparaat het certificaat downloaden dat na de eerste installatie op de Wi-Fi organisatie wordt gebruikt.

3. De kritieke vraag wordt wanneer u wordt gevraagd **of Wie eigenaar van deze HoloLens?** Selecteer **Mijn werk of school is eigenaar en** voer de referenties van uw Azure AD-account in.

4. Wanneer de inschrijving is geslaagd, wordt u gevraagd een pincode in te stellen. Deze pincode is uniek voor dit apparaat voor deze gebruiker. U wordt ook gevraagd naar Iris-scans, spraakgegevens en telemetrie-instellingen en tot slot kunt u leren hoe u het startmenu opent en OOBE voltooit.

5. Zodra u op de start Mixed Reality, opent u de Startmenu met behulp van de **gebaar Start** die u zojuist hebt geleerd.

6. Selecteer de **Instellingen app** en selecteer **Systeem.** Het eerste stukje informatie dat u ziet, is de apparaatnaam, die voor uw HoloLens 2 hololens is, gevolgd door &quot; &quot; een tekenreeks van zes tekens.

7. Noteer deze naam.

    ![HoloLens 2 Instellingen scherm.](./images/hololens2-settings-about.jpg)

8. Controleer of uw apparaat is verbonden met Azure AD. Er zijn twee manieren:

    1.  De Instellingen app. Selecteer **Instellingen** Accounts **Toegang tot** werk of  ->  **school.** In dit scherm kunt u controleren of u bent ingeschreven. Zie Verbonden met &quot; naamvanAAD&#39;Azure AD. Verbonden door *yourusername@nameofAAD.onmicrosoft.com* . Hiermee wordt gecontroleerd of uw apparaat is verbonden met uw organisatie&#39;Azure AD.

    1. De [Azure Portal](https://portal.azure.com/#home). Ga naar **Azure Active Directory**  ->  **Apparaten**  ->  **Alle apparaten** en zoek de naam van het apparaat. Onder Jointype wordt deze als 'Azure AD-lid' weer geven.
        ![Controleer het jointype in Azure AD.](./images/hololens2-devices-all-devices.png)

9. Controleer of uw apparaat is ingeschreven bij MDM. Er zijn twee manieren:

    1. Selecteer **Instellingen** accounts **Toegang tot** werk  ->  **of school.** In dit scherm kunt u controleren of u bent ingeschreven. Zie Verbonden met &quot; naamvanAAD&#39;Azure AD. Verbonden door *yourusername@nameofAAD.onmicrosoft.com* . Selecteer vanuit dit Toegangsaccount voor werk of school de optie Verbonden met &quot; naamofAAD&#39;Azure AD. Verbonden door yourusername@nameofAAD.onmicrosoft.com &quot; en selecteer de knop **Info.**

    1. [Microsoft Endpoint Manager-beheercentrum.](https://endpoint.microsoft.com/#home) Meld u aan en selecteer **Apparaten** en **vervolgens Alle apparaten.** Hier kunt u de naam van HoloLens apparaat&#39;zoeken. Als het goed is, kunt u uw HoloLens in Intune zien.

        ![Controleer of beheerd door Intune in Azure AD.](./images/hololens2-devices-all-devices2.png)


## <a name="wi-fi-certificate-validation"></a>Wi-Fi certificaatvalidatie

Op dit moment moet het apparaat het Wi-Fi ontvangen. De eenvoudigste validatie die u kunt uitvoeren, is proberen verbinding te maken met Wi-Fi verbinding waarvoor u&#39;certificaat hebt ontvangen. Open de  Instellingen app, navigeer naar **Network &amp; Internet**  ->  **Wi-Fi** en selecteer de Wi-Fi-verbinding. Nadat u verbinding hebt gemaakt, opent u Microsoft Edge app en bevestigt u dat u naar een website kunt navigeren.

Als u wilt bevestigen dat u het certificaat op het apparaat hebt ontvangen, kunt u [certificaatbeheer gebruiken.](/hololens/certificate-manager)

## <a name="validate-lob-app-install"></a>Installatie van LOB-app valideren

Als u de voortgang van de installatie van een beheerde app wilt bekijken, controleert u of de app is geïnstalleerd of Instellingen. Door een LOB-app te configureren als een vereiste installatie voor onze groep, wordt de app, nadat de HoloLens is ingeschreven bij een gebruiker in de toegewezen groep, automatisch gedownload naar de HoloLens.

Open het Startmenu en selecteer **Alle apps**. Afhankelijk van het aantal apps dat u hebt, moet u mogelijk de knoppen Pagina **omhoog** of Omlaag **gebruiken.**

Als u de installatie van de app op het apparaat wilt valideren, kunt u dit doen via Instellingen-accounts Toegang tot werk of school. Selecteer het account en vervolgens de knop Info en schuif omlaag om verschillende configuraties en apps te zien die op het apparaat zijn toegepast vanuit  ->    ->  MDM. 

Als u de installatie vanuit Intune wilt valideren, gaat u naar de pagina Apps -> Alle apps van de [MEM-portal](https://endpoint.microsoft.com/#home)  ->     -> *TheNameOfYourApp*  ->  **Device install status.**

Meer informatie: [Intune-app-implementatie voor HoloLens](/hololens/app-deploy-intune)

## <a name="validate-dynamics-365-guides"></a>Valideren Dynamics 365 Guides

Er zijn modi voor de app Guides HoloLens, schrijven en gebruiken. U moet het schrijven van een handleiding voltooien voordat u deze kunt gebruiken.

### <a name="authoring-the-guide"></a>De handleiding schrijven

We hoeven niet veel te doen voor deze snelle validatie. Selecteer gewoon de handleiding die u hebt voorbereid op uw pc. U moet de handleiding [ankeren voor](/dynamics365/mixed-reality/guides/hololens-app-anchor)een snelle validatie die u kunt gebruiken voor een holografische anker. Daarna moet u [uw stappen en modellen plaatsen.](/dynamics365/mixed-reality/guides/hololens-app-orientation)

>[!NOTE]
> U hebt de **ontwerprol nodig om** u aan te melden bij de pc en auteur op de HoloLens. De rol Operator is alleen-lezen en heeft geen toegang tot de pc-app.

<iframe width="560" height="315" src="https://www.youtube.com/embed/poE7s7_zWDE" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="operating-the-guide"></a>De handleiding gebruiken

Zodra uw hologrammen zijn uitgevoerd, kunt u de handleiding testen. 
- Operatormodus **selecteren**
- Klik door de stappen van uw handleiding.

Raadpleeg de volgende bronnen voor uitgebreidere richtlijnen voor het werken met een handleiding:

[Overzicht van het gebruik van een handleiding in Dynamics 365 Guides](/dynamics365/mixed-reality/guides/operator-overview)

[Ga georiënteerd te werk met de kaart Stap als een operator in Dynamics 365 Guides](/dynamics365/mixed-reality/guides/operator-step-card-orientation)

<iframe width="560" height="315" src="https://www.youtube.com/embed/9s41BKGHVL8" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="next-step"></a>Volgende stap 
> [!div class="nextstepaction"]
> [Zakelijke verbonden implementatie - Onderhouden](hololens2-corp-connected-maintain.md)
