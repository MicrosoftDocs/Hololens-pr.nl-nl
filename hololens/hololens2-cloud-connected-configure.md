---
title: 'Implementatiehandleiding : cloudgeconnecteerde HoloLens 2 implementatie op schaal met Remote Assist - Configureren'
description: Meer informatie over het instellen van configuraties voor het op schaal HoloLens registreren van apparaten via een cloudnetwerk met Remote Assist.
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
ms.openlocfilehash: eb96f1cdc799551297c0373268e8cc8f35c6bd06
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032745"
---
# <a name="configure---cloud-connected-guide"></a>Configureren - Handleiding voor verbonden cloud

In deze sectie van de handleiding wordt&#39;het instellen van automatische inschrijving voor uw tenant en het toepassen van licenties voor zowel Intune als Remote Assist.

## <a name="azure-users-and-groups"></a>Azure-gebruikers en -groepen

Azure en Intune voor die extensie gebruiken gebruikers en groepen om configuraties en licenties toe te wijzen. Om deze implementatiestroom te valideren en een Remote Assist aanroep van de ene gebruiker naar de andere te kunnen maken, hebt&#39;twee gebruikersaccounts nodig.

We kunnen één gebruikersgroep maken voor het toewijzen van licenties. We kunnen beide gebruikers aan dezelfde groep deelnemen en een licentie voor Intune en Remote Assist op die groep.

Als u geen&#39;hebt tot twee Azure AD-accounts in een gebruikersgroep die u kunt gebruiken; hier zijn de snelstartgidsen voor:

- [Een gebruiker maken](/mem/intune/fundamentals/quickstart-create-user)
- [Een groep maken](/mem/intune/fundamentals/quickstart-create-group)
- [Gebruikers toevoegen aan een groep](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) : gemaakte gebruikers toevoegen om een groep te maken
- [Azure AD configureren zodat een gebruikersgroep apparaten kan deelnemen:](/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) zorg ervoor dat de nieuwe gebruikersgroep toestemming heeft om apparaten in te schrijven bij Azure AD

## <a name="auto-enrollment-on-hololens-2"></a>Automatische inschrijving op HoloLens 2

Voor een soepele en naadloze ervaring is het instellen van Azure Active Directory Join (AADJ) en automatische inschrijving bij Intune voor HoloLens 2-apparaten de beste manier. Hierdoor kunnen gebruikers hun aanmeldingsreferenties van hun organisatie invoeren tijdens OOBE en automatisch registreren bij Azure AD en het apparaat registreren bij MDM.

Met behulp [Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home)kunt u services selecteren en door een paar pagina's navigeren totdat u Een Premium selecteren. Mogelijk ziet u dat er Azure Active Directory Premium 1 en 2 is, voor Automatische inschrijving P1 voldoende is. We kunnen Intune selecteren, het gebruikersbereik voor automatische inschrijving selecteren en de groep selecteren die eerder is gemaakt.

Lees de handleiding over het inschakelen van automatische inschrijving voor [Intune](/mem/intune/enrollment/quickstart-setup-auto-enrollment)voor meer informatie en stappen.

## <a name="application-licenses"></a>Toepassingslicenties

Met een toepassingslicentie kan een gebruiker door het bedrijf gekochte apps installeren of upgraden van een gratis proefversie naar de volledige versie van een app. Toepassingslicenties kunnen worden toegepast op gebruikers, gebruikersgroepen of apparaatgroepen. U&#39;licenties Remote Assist gebruikers in uw organisatie nodig hebben om deze te Remote Assist. Voor deze handleiding wijzen we de Remote Assist toe aan de gebruikersgroep die we hierboven hebben gemaakt in [Azure Users and Groups](hololens2-cloud-connected-configure.md#azure-users-and-groups).

De vereisten voor licenties kunnen verschillen, afhankelijk van of de gebruiker de Remote Assist-aanroep maakt vanaf een apparaat of een externe samenwerker van Microsoft Teams. Standaard zijn de Remote Assist Teams selectievakjes gemarkeerd. Voor deze handleiding raden we u aan de standaardvakken ingeschakeld te laten.

1. Meer informatie over de verschillende [licentie- en productvereisten per rol](/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role). Er zijn enkele verschillende typen Remote Assist licenties, dus zorg ervoor dat u de juiste licenties voor uw behoeften hebt.
2. U&#39;de [licentie verkrijgen.](/dynamics365/mixed-reality/remote-assist/buy-remote-assist)
3. [Pas uw licenties toe](/dynamics365/mixed-reality/remote-assist/deploy-remote-assist) op de groep.

## <a name="next-step"></a>Volgende stap

> [!div class="nextstepaction"]
> [Cloudgeconnecteerde implementatie - Implementeren](hololens2-cloud-connected-deploy.md)