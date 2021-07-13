---
title: Implementatiehandleiding - Cloudgeconnecteerde HoloLens 2 implementatie op schaal met Remote Assist - Implementeren
description: Meer informatie over het valideren van inschrijving en Remote Assist voor HoloLens via een met de cloud verbonden netwerk.
keywords: HoloLens, beheer, verbonden met de cloud, Remote Assist, AAD, Azure AD, MDM, Mobile Device Management
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: b0597806d58d7bf16fe6f6c766af3f9662fca7e6
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635174"
---
# <a name="deploy---cloud-connected-guide"></a>Implementeren - Handleiding voor verbonden cloud

Nu u alles hebt geconfigureerd, moet u klaar zijn om apparaten te distribueren. Dit is echter het moment waarop u de installatie voor het eerst moet valideren. Eerst moeten het proces voor Azure AD Join en MDM-inschrijving worden gevalideerd, gevolgd door te controleren of er een Remote Assist kan worden geplaatst.

## <a name="enrollment-validation"></a>Validatie van inschrijving

Nu alles goed is geconfigureerd voor Azure AD- en MDM-inschrijving, moet de rest een uitlijning zijn. U&#39;een Wi-Fi- en HoloLens-apparaat, evenals een van de eerder geconfigureerde AAD-gebruikersaccounts nodig.

Als uw apparaat momenteel&#39;de status fabrieksinstellingen heeft, is het nu een goed moment om een reflash op het [apparaat uit te halen.](/hololens/hololens-recovery#clean-reflash-the-device)

1. Zodra uw apparaat zich in OOBE&#39;, moet u de aanwijzingen gaan gebruiken en volgen. 
1. De kritieke vraag wordt wanneer u wordt gevraagd **of Wie eigenaar van deze HoloLens?** Selecteer **Mijn werk of school is eigenaar en** voer de referenties van uw Azure AD-account in.
1. Wanneer de inschrijving is geslaagd,&#39;gevraagd om een pincode in te stellen. Deze pincode is uniek voor dit apparaat voor deze gebruiker. U wordt ook gevraagd naar Iris-scans, spraakgegevens en telemetrie-instellingen en tot slot kunt&#39;leren hoe u het startmenu opent en OOBE voltooit.
1. Zodra u in de Mixed Reality start, opent u de Startmenu met behulp van de **gebaar Start** die u zojuist hebt geleerd.
1. Selecteer de **Instellingen app** en selecteer **Systeem.** Het eerste stukje informatie dat u&#39;ziet, is uw Apparaatnaam, die voor uw HoloLens 2-apparaat HOLOLENS is, gevolgd door een &quot; &quot; tekenreeks van zes tekens.
1. Noteer deze naam.

![HoloLens 2 Instellingen : over](./images/hololens2-settings-about.jpg)

7. U kunt controleren of uw apparaat is ingeschreven bij Azure AD in de Instellingen app. Selecteer **Instellingen** **Accounts Toegang** tot werk of  ->  **school.** In dit scherm kunt u controleren of u bent ingeschreven door Verbonden met &quot; _naamvanAAD_ te zien&#39;Azure AD. Verbonden door _yourusername_ @ _nameofAAD_.onmicrosoft.com &quot; .


Om te controleren of het apparaat lid is van Azure AD, kunnen we de Azure Active Directory controleren in de [Azure Portal](https://portal.azure.com/#home)Azure Active Directory Devices All devices en de naam van  ->    ->    ->  het apparaat doorzoeken. U&#39;zien dat het apparaat deel uitmaakt van de Azure Active Directory.


![Azure Active Directory - Apparaat](./images/aad-enrollment.png)

Vervolgens moet&#39;zich aanmelden bij het [Microsoft Endpoint Manager-beheercentrum.](https://endpoint.microsoft.com/#home) Meld u aan en selecteer **Apparaten** en **vervolgens Alle apparaten.** Hier kunt u de naam van HoloLens apparaat&#39;zoeken. Als het goed is, ziet u uw HoloLens in Intune.

![Intune - Apparaat](./images/endpoint-all-devices-enrolled.png)

## <a name="remote-assist-call-validation"></a>Remote Assist aanroepvalidatie

Nadat u&#39;hebt gecontroleerd of uw apparaat is ingeschreven bij zowel uw AAD als MDM,&#39;het tijd om een test-Remote Assist plaatsen. Voor deze validatie&#39;u het HoloLens-apparaat en een Windows 10-pc, evenals een tweede Azure AD-gebruikersaccount voor de pc.

Bij deze validatiestap wordt ervan uitgenomen dat u de laatste validatiestap eerder hebt voltooid en dat uw apparaat is ingeschreven en dat uw Azure AD-gebruiker zich op het apparaat heeft geregistreerd.


1. Als u nog geen Microsoft Teams op uw pc hebt geïnstalleerd, kunt u [deze Teams downloaden.](https://www.microsoft.com/microsoft-365/microsoft-teams/download-app)
2. Meld u Teams met het tweede Azure AD-gebruikersaccount dan het account dat momenteel is aangemeld bij uw HoloLens. Zodra u bent aangemeld op uw pc, bent u klaar om de aanroep te ontvangen.
3. Ontgrendel uw HoloLens en meld u aan.
4. Als u de Remote Assist app wilt starten, opent u **het menu Start** en **selecteert u Remote Assist**. Remote Assist is niet alleen gebundeld als postvak IN-app, maar ook vastgemaakt aan HoloLens 2&#39;menu Start van de app. In een gebeurtenis ziet&#39;deze niet is vastgemaakt aan de Startmenu open vervolgens de Alle apps **om** ernaar te zoeken.
5. Zodra Remote Assist wordt gestart, moet de gebruiker van het apparaat worden identificeren via [eenmalige aanmelding](/azure/active-directory/manage-apps/what-is-single-sign-on) en zich aanmelden bij de app.
6. Selecteer in de app Zoeken **en** zoek naar de tweede gebruiker op de pc. Selecteer de gebruiker om de aanroep te starten.
7. Beantwoord de oproep vanaf uw pc.

Gefeliciteerd, u&#39;verbinding hebt en u op afstand hulp nodig hebt. Zorg ervoor dat u specifieke functies voor hulp op afstand probeert, zoals het volgende:

- [Aantekeningen aantekeningen](/dynamics365/mixed-reality/remote-assist/add-annotations-hololens)
- [Een bestand delen en weergeven in mixed reality](/dynamics365/mixed-reality/remote-assist/display-save-files)
- [Hulp krijgen in een andere HoloLens app](/dynamics365/mixed-reality/remote-assist/get-help-hololens-app-hololens)

## <a name="next-step"></a>Volgende stap

> [!div class="nextstepaction"]
> [Cloudgeconnecteerde implementatie - Onderhouden](hololens2-cloud-connected-maintain.md)