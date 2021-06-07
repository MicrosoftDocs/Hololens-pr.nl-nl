---
title: 'Implementatiehandleiding : Cloudgeconnecteerde HoloLens 2 implementatie op schaal met Remote Assist - Implementeren'
description: Meer informatie over het valideren van inschrijving en Remote Assist voor HoloLens-apparaten via een met de cloud verbonden netwerk.
keywords: HoloLens, beheer, cloud verbonden, Remote Assist, AAD, Azure AD, MDM, Mobile Device Management
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
ms.openlocfilehash: 4183bde30673f5147683e16b4d625f73b063c529
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/19/2021
ms.locfileid: "111377933"
---
# <a name="deploy---cloud-connected-guide"></a>Implementeren - Handleiding voor verbonden cloud

Nu u alles hebt geconfigureerd, moet u klaar zijn om apparaten te distribueren. Dit is echter het moment waarop u de installatie voor het eerst moet valideren. Eerst moet het proces van Azure AD Join en MDM-inschrijving worden gevalideerd, gevolgd door te controleren of een Remote Assist kan worden geplaatst.

## <a name="enrollment-validation"></a>Validatie van inschrijving

Nu alles goed is geconfigureerd voor Azure AD- en MDM-inschrijving, moet de rest een uitlijning zijn. U&#39;een Wi-Fi verbinding en het HoloLens-apparaat nodig, evenals een van de eerder geconfigureerde AAD-gebruikersaccounts.

Als uw apparaat momenteel&#39;de status fabrieksinstellingen heeft, is dit een goed moment om het apparaat te [gebruiken.](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device)

1. Zodra uw apparaat zich in OOBE&#39;, moet u beginnen met communiceren en de aanwijzingen volgen. 
1. De kritieke vraag wordt wanneer u wordt gevraagd **wie de eigenaar is van deze HoloLens?** Selecteer **Mijn werk of school is eigenaar en** voer de referenties van uw Azure AD-account in.
1. Wanneer de inschrijving is geslaagd,&#39;gevraagd om een pincode in te stellen. Deze pincode is uniek voor dit apparaat voor deze gebruiker. U wordt ook gevraagd om irisscans, spraakgegevens en telemetrie-instellingen en tot slot kunt&#39;leren hoe u het startmenu opent en OOBE voltooit.
1. Zodra u in het Mixed Reality start opent u de Startmenu met behulp van de **gebaar Starten** die u zojuist hebt geleerd.
1. Selecteer de app **Instellingen** en selecteer **Systeem.** Het eerste stukje informatie dat u&#39;ziet, is de Apparaatnaam, die voor uw HoloLens 2-apparaat HOLOLENS is, gevolgd door een &quot; &quot; tekenreeks van zes tekens.
1. Noteer deze naam.

![HoloLens 2-instellingen - Over](./images/hololens2-settings-about.jpg)

7. U kunt controleren of uw apparaat is ingeschreven bij Azure AD in de app Instellingen. Selecteer **bij Instellingen** de optie **Accounts** Toegang tot werk  ->  **of school.** In dit scherm kunt u controleren of u bent ingeschreven door Verbonden met &quot; _naamvanAAD_ te zien&#39;Azure AD. Verbonden door _yourusername_ @ _nameofAAD_.onmicrosoft.com &quot; .


Om te controleren of Azure AD is verbonden met het apparaat, kunnen we de Azure Active Directory controleren in de [Azure Portal](https://portal.azure.com/#home)Azure Active Directory Devices All devices en zoeken we de  ->    ->    ->  naam van het apparaat. U&#39;zien dat het apparaat deel uitmaakt van de Azure Active Directory.


![Azure Active Directory - Apparaat](./images/aad-enrollment.png)

Vervolgens moet&#39;zich aanmelden bij het [Microsoft Endpoint Manager-beheercentrum.](https://endpoint.microsoft.com/#home) Meld u aan en selecteer **Apparaten** en **vervolgens Alle apparaten.** Hier kunt u op uw HoloLens-apparaat&#39;naam. U zou uw HoloLens moeten kunnen zien in Intune.

![Intune - Apparaat](./images/endpoint-all-devices-enrolled.png)

## <a name="remote-assist-call-validation"></a>Remote Assist-aanroepvalidatie

Nadat u&#39;hebt gecontroleerd of uw apparaat is ingeschreven bij zowel uw AAD als MDM,&#39;het tijd om een test-aanroep Remote Assist plaatsen. Voor deze validatie&#39;u het HoloLens-apparaat en een Windows 10-pc, evenals een tweede Azure AD-gebruikersaccount voor de pc.

Bij deze validatiestap wordt ervan uitgenomen dat u de laatste validatiestap eerder hebt voltooid en dat uw apparaat is geregistreerd en dat uw Azure AD-gebruiker zich op het apparaat heeft geregistreerd.


1. Als u Microsoft Teams nog niet op uw pc hebt geïnstalleerd, kunt u [Teams hier downloaden.](https://www.microsoft.com/microsoft-365/microsoft-teams/download-app)
2. Meld u aan bij Teams met het tweede Azure AD-gebruikersaccount dan het account dat momenteel is aangemeld bij uw HoloLens. Zodra u bent aangemeld bij uw pc, bent u klaar om de aanroep te ontvangen.
3. Ontgrendel uw HoloLens en meld u aan.
4. Als u de Remote Assist app wilt starten, opent u **het menu Start** en **selecteert u Remote Assist**. Remote Assist is niet alleen gebundeld als postvak in-app, maar ook vastgemaakt aan HoloLens 2&#39;menu start van de app. In een gebeurtenis die u niet&#39;vastgemaakt aan de Startmenu, opent u vervolgens de Alle apps **om** ernaar te zoeken.
5. Zodra Remote Assist wordt gestart, moet deze de gebruiker van het apparaat identificeren via [eenmalige aanmelding](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on) en zich aanmelden bij de app.
6. Selecteer in de app Zoeken **en** zoek naar de tweede gebruiker op de pc. Selecteer de gebruiker om de aanroep te starten.
7. Beantwoord de oproep vanaf uw pc.

Gefeliciteerd, u&#39;verbinding hebt en op afstand hulp nodig hebt. Zorg ervoor dat u specifieke functies voor hulp op afstand probeert, zoals het gebruik van:

- [Aantekeningen aan het intikken](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/add-annotations-hololens)
- [Een bestand delen en weergeven in mixed reality](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/display-save-files)
- [Hulp krijgen in een andere HoloLens-app](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/get-help-hololens-app-hololens)

## <a name="next-step"></a>Volgende stap

> [!div class="nextstepaction"]
> [Cloudgeconnecteerde implementatie - Onderhouden](hololens2-cloud-connected-maintain.md)