---
title: HoloLens naslaginformatie over kiosken
description: Informatie en voorbeelden voor kiosken op HoloLens apparaten.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 8/24/2021
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 9f8cfd0013ac5b8cf85a334cbb89c458440820d9
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032565"
---
# <a name="hololens-kiosk-reference-information"></a>HoloLens Naslaginformatie over kiosken

Deze pagina bevat nuttige informatie voor het instellen van HoloLens kioskmodus van uw apparaat. Deze verwijzingen bevatten AUMID's voor Postvak IN-apps en het zoeken naar uw eigen apps, en verschillende XML-voorbeelden voor de kioskmodus, die slechts een paar bewerkingen zijn verwijderd van het gereed zijn voor gebruik voor verschillende scenario's. Lees de pagina Een kiosk instellen voor meer informatie over [het instellen van een kiosk.](hololens-kiosk.md)

## <a name="hololens-application-user-model-ids-aumids"></a>HoloLens Model-ID's van toepassingsgebruikers (AUMID's)  

Zie Richtlijnen voor het kiezen van een app voor toegewezen toegang [(kioskmodus)](/windows/configuration/guidelines-for-assigned-access-app)voor algemene informatie over het kiezen van kiosk-apps.

Als u een MDM-systeem (Mobile Device Management) of een inrichtingspakket gebruikt om de kioskmodus te configureren, gebruikt u [de CSP (AssignedAccess Configuration Service Provider)](/windows/client-management/mdm/assignedaccess-csp) om toepassingen op te geven. De CSP gebruikt [AUMID's (Application User Model IDs) om](/windows/configuration/find-the-application-user-model-id-of-an-installed-app) toepassingen te identificeren. De volgende tabel bevat de AUMID's van sommige in-box-toepassingen die u in een kiosk voor meerdere apps kunt gebruiken.

<a id="aumids"></a>

|App-naam |AUMID |
| --- | --- |
|3D-viewer |Microsoft.Microsoft3DViewer \_ 8wekyb3d8bbwe \! Microsoft.Microsoft3DViewer |
|Kalender |microsoft.windowscommunicationsapps \_ 8wekyb3d8bbwe \! microsoft.windowslive.calendar |
|Camera<sup>1, 2</sup> |HoloCamera \_ cw5n1h2txyewy \! HoloCamera |
|Cortana<sup>3</sup> |Microsoft.549981C3F5F10 \_ 8wekyb3d8bbwe \! App |
|Apparaat kiezen op HoloLens (eerste generatie) |HoloDevicesFlow \_ cw5n1h2txyewy \! HoloDevicesFlow |
|Apparaat kiezen op HoloLens 2 |Microsoft. Windows. DevicesFlowHost \_ cw5n1h2txyewy \! Microsoft.Windows. DevicesFlowHost |
|Dynamics 365 Guides |Microsoft.Dynamics365.Guides \_ 8wekyb3d8bbwe \! MicrosoftGuides |
|Dynamics 365 Remote Assist |Microsoft.MicrosoftRemoteAssist \_ 8wekyb3d8bbwe \! Microsoft.RemoteAssist |
|Feedback &nbsp; Hub |Microsoft.WindowsFeedbackHub \_ 8wekyb3d8bbwe \! App |
|Verkenner |c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy! App |
|Mail |microsoft.windowscommunicationsapps_8wekyb3d8bbwe!microsoft.windowslive.mail |
|Oude Microsoft Edge |Microsoft.MicrosoftEdge_8wekyb3d8bbwe! MicrosoftEdge |
|Nieuwe Microsoft Edge |Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe! MSEDGE |
|Microsoft Store |Microsoft.WindowsStore_8wekyb3d8bbwe! App |
|Miracast<sup>4</sup> | &nbsp; |
|Films & TV |Microsoft.ZuneVideo \_ 8wekyb3d8bbwe \! Microsoft.ZuneVideo |
|OneDrive |microsoft.microsoftskydrive \_ 8wekyb3d8bbwe \! App |
|Foto's |Microsoft. Windows. \_Foto's 8wekyb3d8bbwe \! App |
|Oude Instellingen |HolographicSystemSettings_cw5n1h2txyewy! App |
|Nieuwe Instellingen |BAEAEF15-9ILE-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy! App |
|Tips |Microsoft.HoloLensTips \_ 8wekyb3d8bbwe \! HoloLensTips |

> <sup>1</sup> Als u foto- of video-opname wilt inschakelen, moet u de camera-app inschakelen als kiosk-app.  
> <sup>2</sup> Wanneer u de camera-app inschakelen, moet u rekening houden met de volgende voorwaarden:
> - Het menu Snelle acties bevat de knoppen Foto en Video.
> - U moet ook een app inschakelen (zoals Foto's, Mail of OneDrive) die kan communiceren met afbeeldingen of deze kan ophalen.  
>  
> <sup>3</sup> Zelfs als u een Cortana kiosk-app inschakelen, worden ingebouwde spraakopdrachten ingeschakeld. Opdrachten die zijn gerelateerd aan uitgeschakelde functies hebben echter geen effect.  
> <sup>4</sup> U kunt de Miracast inschakelen. Als u de Miracast als kiosk-app wilt inschakelen, moet u de app Camera en de app Apparaat kiezen inschakelen.

Bovendien kan de Mixed Reality Start niet worden ingesteld als een kiosk-app.

Ga terug naar [Ondersteunde scenario's voor de kioskmodus op basis van het identiteitstype](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

## <a name="kiosk-xml-code-samples"></a>Voorbeelden van XML-code voor kiosken

1. [Meerdere app-profiel voor algemeen toegewezen toegang](#multiple-app-global-assigned-access-profile)
1. [Meerdere app-profiel voor algemeen toegewezen toegang, met uitzondering van apparaateigenaren](#multiple-app-global-assigned-access-profile-excluding-device-owners)
1. [Meerdere apps toegewezen toegangsprofiel voor een lokaal account of AAD-gebruikersaccount](#multiple-app-assigned-access-profile-for-a-local-account-or-aad-user-account)
1. [Meerdere app-toegewezen toegangsprofielen voor twee AAD-gebruikers of meer](#multiple-app-assigned-access-profiles-for-two-aad-users-or-more)
1. [Meerdere app-toegewezen toegangsprofiel voor één AAD-groep](#multiple-app-assigned-access-profile-for-one-aad-group)
1. [Meerdere app-toegewezen toegangsprofiel voor twee AAD-groepen of meer](#multiple-app-assigned-access-profile-for-two-aad-groups-or-more)
1. [Aan meerdere apps toegewezen toegangsprofiel voor één AAD-account en één AAD-groep](#multiple-app-assigned-access-profile-for-one-aad-account-and-one-aad-group)
1. [Aan meerdere apps toegewezen toegangsprofiel voor bezoekers](#multiple-app-assigned-access-profile-for-visitors)

> [!NOTE]
> Vervang TODO-acties volgens uw vereisten.

### <a name="multiple-app-global-assigned-access-profile"></a>Meerdere app-profiel voor algemeen toegewezen toegang

:::code language="xml" source="samples/kiosk-sample-global-multiapp-for-everyone.xml" highlight="18-20":::

[Terug naar lijst](#kiosk-xml-code-samples) <br>
Ga terug naar [Ondersteunde scenario's voor de kioskmodus op basis van het identiteitstype](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-global-assigned-access-profile-excluding-device-owners"></a>Meerdere app-profiel voor algemeen toegewezen toegang, met uitzondering van apparaateigenaren

:::code language="xml" source="samples/kiosk-sample-global-multiapp-for-everyone-excluding-device-owners.xml" highlight="18-20":::

[Terug naar lijst](#kiosk-xml-code-samples) <br>
Ga terug naar [Ondersteunde scenario's voor de kioskmodus op basis van het identiteitstype](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profile-for-a-local-account-or-aad-user-account"></a>Meerdere apps toegewezen toegangsprofiel voor een lokaal account of AAD-gebruikersaccount

:::code language="xml" source="samples/kiosk-sample-multi-app-local-or-aad-user.xml" highlight="18-20,51,55":::

[Terug naar lijst](#kiosk-xml-code-samples) <br>
Ga terug naar [Ondersteunde scenario's voor de kioskmodus op basis van het identiteitstype](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profiles-for-two-aad-users-or-more"></a>Meerdere app-toegewezen toegangsprofielen voor twee AAD-gebruikers of meer

:::code language="xml" source="samples/kiosk-sample-multi-app-two-aad-users-or-more.xml" highlight="22-24,52,53,80,88":::

[Terug naar lijst](#kiosk-xml-code-samples) <br>
Ga terug naar [Ondersteunde scenario's voor de kioskmodus op basis van het identiteitstype](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profile-for-one-aad-group"></a>Meerdere app-toegewezen toegangsprofiel voor één AAD-groep

:::code language="xml" source="samples/kiosk-sample-multi-app-one-aad-group.xml" highlight="28":::

[Terug naar lijst](#kiosk-xml-code-samples) <br>
Ga terug naar [Ondersteunde scenario's voor de kioskmodus op basis van het identiteitstype](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profile-for-two-aad-groups-or-more"></a>Meerdere app-toegewezen toegangsprofiel voor twee AAD-groepen of meer

:::code language="xml" source="samples/kiosk-sample-multi-app-two-aad-groups-or-more.xml" highlight="22-24,52,53,83,94":::

[Terug naar lijst](#kiosk-xml-code-samples) <br>
Ga terug naar [Ondersteunde scenario's voor de kioskmodus op basis van het identiteitstype](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profile-for-one-aad-account-and-one-aad-group"></a>Aan meerdere apps toegewezen toegangsprofiel voor één AAD-account en één AAD-groep

:::code language="xml" source="samples/kiosk-sample-multi-app-for-aad-user-and-aad-group.xml" highlight="22-24,52,53,80,91":::

[Terug naar lijst](#kiosk-xml-code-samples) <br>
Ga terug naar [Ondersteunde scenario's voor de kioskmodus op basis van het identiteitstype](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profile-for-visitors"></a>Aan meerdere apps toegewezen toegangsprofiel voor bezoekers

:::code language="xml" source="samples/kiosk-sample-multi-app-visitor-user.xml" highlight="18-20":::

[Terug naar lijst](#kiosk-xml-code-samples) <br>
Ga terug naar [Ondersteunde scenario's voor de kioskmodus op basis van het identiteitstype](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)
