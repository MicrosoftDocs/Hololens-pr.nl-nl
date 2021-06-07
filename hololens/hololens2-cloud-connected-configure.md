---
title: 'Implementatiehandleiding : Cloudgeconnecteerde HoloLens 2 implementatie op schaal met Remote Assist - Configureren'
description: Meer informatie over het instellen van configuraties voor het op schaal inschrijven van HoloLens-apparaten via een cloudnetwerk met Remote Assist.
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
ms.openlocfilehash: 00cc3f9df1fefafc9c4c084ff642364ae3ccb85c
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/19/2021
ms.locfileid: "111377837"
---
# <a name="configure---cloud-connected-guide"></a>Configureren - Handleiding voor verbonden cloud

In deze sectie van de handleiding&#39;het instellen van automatische inschrijving voor uw tenant en het toepassen van licenties voor zowel Intune als Remote Assist.

## <a name="azure-users-and-groups"></a>Azure-gebruikers en -groepen

Azure, en Intune door die extensie, maakt gebruik van gebruikers en groepen om configuraties en licenties toe te wijzen. Om deze implementatiestroom te valideren en een Remote Assist aanroep van de ene gebruiker naar de andere te kunnen&#39;hebt u twee gebruikersaccounts nodig.

We kunnen één gebruikersgroep maken voor het toewijzen van licenties. We kunnen beide gebruikers aan dezelfde groep deelnemen en een licentie voor Intune en Remote Assist op die groep.

Als u geen&#39;hebt tot twee Azure AD-accounts in een gebruikersgroep, kunt u deze gebruiken; hier zijn de snelstartgidsen voor:

- [Een gebruiker maken](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-user)
- [Een groep maken](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-group)
- [Gebruikers toevoegen aan een groep:](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) gemaakte gebruikers toevoegen om een groep te maken
- [Azure AD configureren zodat een gebruikersgroep apparaten kan deelnemen:](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) zorg ervoor dat de nieuwe gebruikersgroep toestemming heeft om apparaten in te schrijven bij Azure AD

## <a name="auto-enrollment-on-hololens-2"></a>Automatische inschrijving op HoloLens 2

Voor een soepele en naadloze ervaring kunt u Azure Active Directory Join (AADJ) en automatische inschrijving bij Intune instellen voor HoloLens 2-apparaten. Hierdoor kunnen gebruikers hun aanmeldingsreferenties voor de organisatie invoeren tijdens OOBE, zich automatisch registreren bij Azure AD en het apparaat registreren bij MDM.

Met behulp [van Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home)kunnen we services selecteren en door een paar pagina's navigeren totdat we Een Premium-proefversie krijgen kunnen selecteren. Mogelijk ziet u dat er Azure Active Directory Premium 1 en 2 is, voor Automatische inschrijving P1 voldoende is. We kunnen Intune selecteren, het gebruikersbereik voor automatische inschrijving selecteren en de groep selecteren die eerder is gemaakt.

Lees de handleiding over het inschakelen van automatische inschrijving [voor Intune](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment)voor meer informatie en stappen.

## <a name="application-licenses"></a>Toepassingslicenties

Met een toepassingslicentie kan een gebruiker door het bedrijf gekochte apps installeren of upgraden van een gratis proefversie naar de volledige versie van een app. Toepassingslicenties kunnen worden toegepast op gebruikers, gebruikersgroepen of apparaatgroepen. U&#39;licenties Remote Assist gebruikers in uw organisatie nodig hebben om deze te Remote Assist. Voor deze handleiding wijzen we Remote Assist toe aan de gebruikersgroep die we hierboven hebben gemaakt in [Azure Users and Groups](hololens2-cloud-connected-configure.md#azure-users-and-groups).

De vereisten voor licenties kunnen verschillen, afhankelijk van of de gebruiker de Remote Assist-aanroep maakt vanaf een apparaat of een externe samenwerker van Microsoft Teams is. Standaard zijn de Remote Assist teams gemarkeerd. Voor deze handleiding raden we u aan de standaardvakken ingeschakeld te laten.

1. Meer informatie over de verschillende [licentie- en productvereisten per rol](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role). Er zijn een aantal verschillende typen Remote Assist licenties, dus zorg ervoor dat u de juiste licenties voor uw behoeften hebt.
2. U&#39;de licentie [verkrijgen.](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist)
3. [Pas uw licenties toe](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/deploy-remote-assist) op de groep.

## <a name="next-step"></a>Volgende stap

> [!div class="nextstepaction"]
> [Cloudgeconnecteerde implementatie - Implementeren](hololens2-cloud-connected-deploy.md)