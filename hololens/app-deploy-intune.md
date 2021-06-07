---
title: Intune en Bedrijfsportal
description: Meer informatie over het instellen, toewijzen en maken van een gebruikerservaring met Intune, mobile device management en de bedrijfsportal.
keywords: intune, app-beheer, app, bedrijfsportal, portal, hololens
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: f91f97b6cddf678b20d0bdb3f381e01809b10f3f
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/19/2021
ms.locfileid: "111377920"
---
# <a name="intune--company-portal"></a>Intune-& Bedrijfsportal

Met Mobile Device Management (MDM) kunt u uw eigen aangepaste apps via [Microsoft Endpoint Manager (Intune)](https://docs.microsoft.com/intune/windows-holographic-for-business) gebruiken om deze rechtstreeks op uw HoloLens-apparaten te implementeren. Microsoft Intune is een cloudservice die is gericht op MDM (Mobile Device Management) en MAM (Mobile Application Management). Intune is opgenomen in de [EMS-suite (Enterprise Mobility en Security)](https://www.microsoft.com/microsoft-365/enterprise-mobility-security) van Microsoft, en biedt gebruikers de mogelijkheid om productief te zijn terwijl uw bedrijfsgegevens beschermd blijven. Lees Wat is Intune? voor meer informatie [over Intune.](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)

## <a name="setup"></a>Instellen

1. Upload een app naar een Line-Of-Business of upload een aangepaste app naar uw Intune-tenant. Zie ook: [Enterprise app management](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management).

2. [Wijs uw app toe aan een groep](https://docs.microsoft.com/mem/intune/apps/apps-deploy). Op basis van het toewijzingstype dat u kiest, kan de app automatisch worden geleverd of kan deze eenvoudig worden teruggehaald als u een selectie apps hebt.

> [!NOTE]
> Zorg er bij het bouwen van uw appx-bundel voor dat u rekening houdt met de architectuur voor de apparaten waarop u implementeert. HoloLens 2 is ARM64 en HoloLens (1e Gen) is x86. U kunt beide opnemen in één appx-bundel als u van plan bent een omgeving met gemengde apparaten te hebben.

## <a name="assignment-types"></a>Toewijzingstypen

Als u wilt dat uw app na de inschrijving automatisch op het apparaat wordt geïnstalleerd, moet u **Vereist** selecteren voor die groep(en).
Als u uw app beschikbaar wilt maken voor downloaden naar apparaten die zijn ingeschreven via de bedrijfsportal, selecteert u **Beschikbaar voor ingeschreven apparaten.**

## <a name="end-user-experience"></a>De ervaring voor de eindgebruiker

Nadat u de configuratie voor Intune hebt ingesteld, kunt u eindgebruikers de geselecteerde apps laten ontvangen.

Volg deze stappen om uw app(s) automatisch op te halen:

1. Schrijf uw apparaat in bij uw tenant.
2. Zodra de inschrijving van uw apparaat is voltooid, ontvangt u de app op uw apparaat.
3. Als u uw app niet direct ziet, gaat u naar  >  **InstellingenAccounts** Werk- of  >  **schoolaccountGegevens** en schuif omlaag om informatie over de status van  >   de geïnstalleerde app weer te geven.

Apps openen via de volgende Bedrijfsportal:

1. Open het **menu Start** en selecteer **Microsoft Store**.
2. Zoek naar **Bedrijfsportal** en download de app.
3. Meld u aan bij uw account.
4. Selecteer de app die u wilt ontvangen en download deze.

> [!Tip]
> Meer informatie over [het automatisch installeren van de Bedrijfsportal](https://docs.microsoft.com/mem/intune/apps/company-portal-app) en het implementeren en beheren van apps in [Intune.](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps)
