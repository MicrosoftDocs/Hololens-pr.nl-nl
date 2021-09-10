---
title: Intune en Bedrijfsportal
description: Meer informatie over het instellen, toewijzen en maken van een gebruikerservaring met Intune, het beheer van mobiele apparaten en de bedrijfsportal.
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
ms.openlocfilehash: b192732f5e7edffaa1d0ab081454e4034c416191
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427100"
---
# <a name="intune--company-portal"></a>Intune-& Bedrijfsportal

Met Mobile Device Management (MDM) kunt u uw eigen aangepaste apps via [Microsoft Endpoint Manager (Intune)](/intune/windows-holographic-for-business) gebruiken om deze rechtstreeks op uw HoloLens implementeren. Microsoft Intune is een cloudservice die is gericht op MDM (Mobile Device Management) en MAM (Mobile Application Management). Intune is opgenomen in de [EMS-suite (Enterprise Mobility en Security)](https://www.microsoft.com/microsoft-365/enterprise-mobility-security) van Microsoft, en biedt gebruikers de mogelijkheid om productief te zijn terwijl uw bedrijfsgegevens beschermd blijven. Lees Wat is Intune? voor meer informatie [over Intune.](/mem/intune/fundamentals/what-is-intune)

## <a name="setup"></a>Instellen

1. Upload app naar een Line-Of-Business-account of upload een aangepaste app naar uw Intune-tenant. Zie ook: [Enterprise app management](/windows/client-management/mdm/enterprise-app-management).

2. [Wijs uw app toe aan een groep](/mem/intune/apps/apps-deploy). Op basis van het toewijzingstype dat u kiest, kan de app automatisch worden geleverd of beschikbaar worden gesteld als u een selectie apps hebt.

> [!NOTE]
> Zorg er bij het bouwen van uw AppX-bundel voor dat u rekening houdt met de architectuur voor de apparaten waarop u implementeert. HoloLens 2 is ARM64 en HoloLens (1e generatie) is x86. U kunt beide opnemen in één appx-bundel als u van plan bent een omgeving met gemengde apparaten te hebben.

## <a name="assignment-types"></a>Toewijzingstypen

Als u wilt dat uw app na de inschrijving automatisch op het apparaat wordt geïnstalleerd, selecteert u **Vereist** voor die groep(en).
Als u uw app beschikbaar wilt maken voor downloaden naar apparaten die zijn ingeschreven via de bedrijfsportal, selecteert u **Beschikbaar voor ingeschreven apparaten.**

## <a name="end-user-experience"></a>De ervaring voor de eindgebruiker

Nadat u de configuratie voor Intune hebt ingesteld, kunt u eindgebruikers de geselecteerde apps laten ontvangen.

Volg deze stappen om uw app(s) automatisch op te halen:

1. Schrijf uw apparaat in bij uw tenant.
2. Zodra het apparaat is ingeschreven, ontvangt u de app op uw apparaat.
3. Als u uw app niet direct ziet, gaat u naar Instellingen Accounts **Werk-** of schoolaccountgegevens en scrolt u omlaag om informatie over de status van de  >    >    >   geïnstalleerde app weer te geven.

Apps openen via de Bedrijfsportal:

1. Open het **menu Start** en selecteer **Microsoft Store**.
2. Zoek naar **Bedrijfsportal** en download de app.
3. Meld u aan bij uw account.
4. Selecteer de app die u wilt ontvangen en download deze.

> [!Tip]
> Meer informatie over [het automatisch installeren van de Bedrijfsportal](/mem/intune/apps/company-portal-app) en het implementeren en beheren van apps in [Intune.](/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps)
