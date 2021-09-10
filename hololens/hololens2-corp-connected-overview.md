---
title: 'Implementatiehandleiding : zakelijk verbonden HoloLens 2 met Dynamics 365 Guides - Overzicht'
description: Meer informatie over het inschrijven HoloLens 2 apparaten met Dynamics 365 Guides via een verbonden bedrijfsnetwerk.
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
ms.openlocfilehash: 541c1080d7f5fe9491d6cb11179ea98b160f687c
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428116"
---
# <a name="deployment-guide---corporate-connected-hololens-2-with-dynamics-365-guides---overview"></a>Implementatiehandleiding - Corporate Connected HoloLens 2 met Dynamics 365 Guides - Overzicht

Deze handleiding helpt IT-professionals bij het plannen en implementeren van Microsoft HoloLens 2 apparaten met Dynamics 365 Guides (guides) in hun organisatie. Deze handleiding is zeer goed voor zowel luchtvaart- als productie-implementaties en is vergelijkbaar met [scenario B: Implementeren in](/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) de netwerkhandleiding van uw organisatie. Nadat u uw proof-of-concept hebt getest, gebruikt u deze handleiding om verder te gaan met het integreren van HoloLens in uw organisatie.

In deze handleiding wordt beland hoe u uw apparaten kunt registreren bij uw bestaande apparaatbeheer, licenties kunt toepassen als dat nodig is, en hoe u kunt valideren dat uw eindgebruikers een Dynamics 365-handleiding kunnen gebruiken en aangepaste Line-Of-Business-apps kunnen gebruiken nadat het apparaat is ingesteld. 

## <a name="prerequisites"></a>Vereisten

De volgende infrastructuur moet al zijn gebruikt:
- Wi-Fi
    - Intern bedrijfsnetwerk met toegang tot interne resources en beperkte toegang tot internet of cloudservices
    - Verificatie op basis van apparaatcertificaten.
- Azure Active Directory (Azure AD) Deelnemen met automatische MDM-inschrijving[(Azure AD P1-abonnement vereist)](/azure/active-directory/fundamentals/active-directory-whatis)
- MDM (Intune) Beheerd
    - Een of meer toepassingen worden geïmplementeerd via MDM.
- Netwerk 
    - Certificaten (SCEP of PKCS)
    - Proxyconfiguratie
- Gebruikers melden zich aan met hun eigen bedrijfsaccount (Azure AD)
    - Eén of meerdere gebruikers per apparaat worden ondersteund.
- Verschillende niveaus van vergrendelingsconfiguraties voor apparaten die worden toegepast op basis van specifieke gebruiksgevallen, van Volledig geopend tot Kiosk voor één app.

## <a name="guides-licensing-and-requirements"></a>[Handleidingen licentieverlening en vereisten](/dynamics365/mixed-reality/guides/requirements#licensing-and-product-requirements)

- Azure AD-account
- Dynamics 365 Guides pc en HoloLens
- Dynamics 365 Guides abonnement
    - Microsoft Dataverse (inbegrepen)
    - Power Apps (inbegrepen)
- Power BI Desktop
- Netwerkverbinding

[![Corp verbonden netwerkdiagram, fase 1. ](./images/deployment-guides-revised-scenario-b-01-1.png)](./images/deployment-guides-revised-scenario-b-01-1.png#lightbox)

[![Corp verbonden netwerkdiagram, fase 2. ](./images/deployment-guides-revised-scenario-b-02-1.png)](./images/deployment-guides-revised-scenario-b-02-1.png#lightbox)

## <a name="in-this-guide-you-will"></a>In deze handleiding gaat u het volgende doen:
### <a name="prepare"></a>Voorbereiden
> [!div class="checklist"]
>- [Meer informatie over de essentiële infrastructuur voor HoloLens 2 apparaten.](hololens2-corp-connected-prepare.md#infrastructure-essentials)
>- [Meer informatie over Azure AD en er een instellen als u deze nog niet hebt.](hololens2-corp-connected-prepare.md#azure-active-directory)
>- [Meer informatie over identiteitsbeheer en het instellen van Azure AD-accounts.](hololens2-corp-connected-prepare.md#identity-management)
>- [Meer informatie over MDM en instellen met Intune als u er nog geen hebt.](hololens2-corp-connected-prepare.md#mobile-device-management)
>- [Vertrouwd raken met Wi-Fi op basis van certificaten.](hololens2-corp-connected-prepare.md#certificates)
>- [Vertrouwd raken met Proxy.](hololens2-corp-connected-prepare.md#proxy)
>- [Meer informatie over hoe u Line-Of-Business-apps kunt gebruiken.](hololens2-corp-connected-prepare.md#line-of-business-apps)
>- [Meer informatie over de manier waarop u handleidingen voor uw organisatie kunt gebruiken.](hololens2-corp-connected-prepare.md#guides-playbook)
### <a name="configure"></a>Configureren
> [!div class="checklist"]
>- [Gebruikers en groepen maken.](hololens2-corp-connected-configure.md#azure-users-and-groups)
>- [Automatische inschrijving instellen.](hololens2-corp-connected-configure.md#auto-enrollment-on-hololens-2)
>- [How to set up Wi-Fi certificates and profiles for Corporate Wi-Fi Connectivity.](hololens2-corp-connected-configure.md#corporate-wi-fi-connectivity)
>- [Upload LOB-app-pakketten (Line-of-Business) toewijzen.](hololens2-corp-connected-configure.md#app-deployment)
>- [Stel Dynamics 365 Guides.](hololens2-corp-connected-configure.md#setup-guides-application-licenses-dataverse-and-authoring)
>- [Kioskmodus configureren (optioneel).](hololens2-corp-connected-configure.md#optional-kiosk-mode)
>- [WDAC configureren (optioneel).](hololens2-corp-connected-configure.md#optional-wdac)
### <a name="deploy"></a>Implementeren
> [!div class="checklist"]
>-  [Valideer de inschrijving via apparaat en MDM.](hololens2-corp-connected-deploy.md#enrollment-validation)
>-  [Valideer Wi-Fi certificaten.](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation)
>-  [Valideer de installatie van LOB-apps.](hololens2-corp-connected-deploy.md#validate-lob-app-install)
>-  [Valideer handleidingen via ontwerp en gebruik.](hololens2-corp-connected-deploy.md#validate-dynamics-365-guides)
### <a name="maintain"></a>Onderhouden
> [!div class="checklist"]
>- [Werk HoloLens 2.](hololens2-corp-connected-maintain.md#update-hololens)
>- [Handleidingen bijwerken (Store-apps).](hololens2-corp-connected-maintain.md#how-to-update-dynamics-365-guides-and-other-store-apps)
>- [LOB-apps bijwerken.](hololens2-corp-connected-maintain.md#how-to-update-lob-apps) 
>- [Ontwikkelplan.](hololens2-corp-connected-maintain.md#development-plan) 
>- [Een ondersteuningsplan maken.](hololens2-corp-connected-maintain.md#support-plan)
>- [Opties voor apparaatbeheer.](hololens2-corp-connected-maintain.md#device-management)

## <a name="next-step"></a>Volgende stap 
> [!div class="nextstepaction"]
> [Zakelijke verbonden implementatie - Voorbereiden](hololens2-corp-connected-prepare.md)
