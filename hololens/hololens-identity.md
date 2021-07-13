---
title: Gebruikersidentiteit en aanmelding beheren voor HoloLens
description: Meer informatie over het beheren van gebruikersidentiteit, ondersteuning voor meerdere gebruikers, beveiliging, ondernemingsverificatie en aanmelden voor HoloLens apparaten.
keywords: HoloLens, gebruiker, account, AAD, Azure AD, adfs, microsoft-account, msa, referenties, verwijzing
ms.assetid: 728cfff2-81ce-4eb8-9aaa-0a3c3304660e
author: scooley
ms.author: scooley
ms.date: 10/6/2020
ms.prod: hololens
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 4d959d99b65085aea2a776725abdb36e27b43b81
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640386"
---
# <a name="manage-user-identity-and-sign-in-for-hololens"></a>Gebruikersidentiteit en aanmelding beheren voor HoloLens

> [!NOTE]
> Dit artikel is een technische naslag voor IT-professionals en technische professionals. Als u op zoek bent naar HoloLens instellen, leest u '[Uw HoloLens (eerste generatie) instellen'](hololens1-start.md)of['Uw](hololens2-start.md)HoloLens 2 instellen'.

Net als Windows apparaten werkt HoloLens altijd in een gebruikerscontext. Er is altijd een gebruikersidentiteit. HoloLens wordt identiteit bijna op dezelfde manier behandeld als andere Windows 10 apparaten. Dit artikel is een diepgaande naslag voor identiteiten op HoloLens en richt zich op de verschillen HoloLens andere Windows 10 apparaten.

HoloLens ondersteunt verschillende soorten gebruikersidentiteiten. U kunt een of meer gebruikersaccounts gebruiken om u aan te melden. Hier is een overzicht van de identiteitstypen en verificatieopties op HoloLens:

| Identiteitstype | Accounts per apparaat | Verificatieopties |
| --- | --- | --- |
| [Azure Active Directory](/azure/active-directory/)<sup>1</sup>  | 64 | <ul><li>Azure-webreferentieprovider</li><li>Azure Authenticator-app</li><li>Biometrische gegevens (Iris) &ndash; HoloLens 2<sup>slechts 2</sup> </li><li>Pincode &ndash; optioneel voor HoloLens (eerste generatie), vereist voor HoloLens 2</li><li>Wachtwoord</li></ul> |
| [Microsoft-account (MSA)](/windows/security/identity-protection/access-control/microsoft-accounts) | 1 | <ul><li>Biometrische gegevens (Iris) &ndash; HoloLens 2 alleen</li><li>Pincode &ndash; optioneel voor HoloLens (eerste generatie), vereist voor HoloLens 2</li><li>Wachtwoord</li></ul> |
| [Lokaal account](/windows/security/identity-protection/access-control/local-accounts) | 1 | Wachtwoord |

Cloud-verbonden accounts (Azure AD en MSA) bieden meer functies omdat ze Azure-services kunnen gebruiken.  
> [!IMPORTANT]
> 1: Azure AD Premium is niet vereist om u aan te melden bij het apparaat. Dit is echter vereist voor andere functies van een cloudimplementatie met weinig aanraking, zoals automatische inschrijving en Autopilot.

> [!NOTE]
> 2- Hoewel een HoloLens 2 maximaal 64 Azure AD-accounts kan ondersteunen, kunnen slechts 10 van deze accounts worden ingeschreven bij Iris-verificatie. Dit is afgestemd op andere [biometrische verificatieopties voor Windows Hello voor Bedrijven.](/windows/security/identity-protection/hello-for-business/hello-faq#how-many-users-can-enroll-for-windows-hello-for-business-on-a-single-windows-10-computer)

## <a name="setting-up-users"></a>Gebruikers instellen

De meest voorkomende manier om een nieuwe gebruiker in te stellen is tijdens HoloLens out-of-box experience (OOBE). Tijdens de installatie HoloLens een gebruiker gevraagd zich aan te melden met het account dat hij of zij op het apparaat wil gebruiken. Dit account kan een consumentenaccount Microsoft-account een enterprise-account dat is geconfigureerd in Azure. Zie Uw HoloLens [(eerste generatie) of](hololens1-start.md) [HoloLens 2.](hololens2-start.md)

Net Windows op andere apparaten, maakt het aanmelden tijdens de installatie een gebruikersprofiel op het apparaat. Het gebruikersprofiel slaat apps en gegevens op. Hetzelfde account biedt ook een aanmelding voor apps, zoals Edge of de Microsoft Store, met behulp van de Windows Account Manager-API's.  

Als u een bedrijfs- of organisatieaccount gebruikt om u aan te melden bij HoloLens, HoloLens ingeschreven bij de IT-infrastructuur van de organisatie. Met deze inschrijving kan uw IT-beheerder Mobile Device Management (MDM) configureren voor het verzenden van groepsbeleid naar uw HoloLens.

Standaard moet u zich, net Windows 10 andere apparaten, opnieuw aanmelden wanneer HoloLens stand-by wordt opgestart of hervat. U kunt de Instellingen-app gebruiken om dit gedrag te wijzigen, of het gedrag kan worden bepaald door groepsbeleid.

### <a name="linked-accounts"></a>Gekoppelde accounts

Net als in de desktopversie van Windows, kunt u aanvullende webaccountreferenties koppelen aan uw HoloLens account. Deze koppeling maakt het gemakkelijker om toegang te krijgen tot resources in of binnen apps (zoals de Store) of om de toegang tot persoonlijke en werkbronnen te combineren. Nadat u een account hebt verbonden met het apparaat, kunt u toestemming geven om het apparaat te gebruiken voor apps, zodat u zich niet bij elke app afzonderlijk hoeft aan te melden.

Bij het koppelen van accounts worden de gebruikersgegevens die op het apparaat zijn gemaakt, zoals afbeeldingen of downloads, niet gescheiden.  

### <a name="setting-up-multi-user-support-azure-ad-only"></a>Ondersteuning voor meerdere gebruikers instellen (alleen Azure AD)

HoloLens ondersteunt meerdere gebruikers uit dezelfde Azure AD-tenant. Als u deze functie wilt gebruiken, moet u een account gebruiken dat bij uw organisatie hoort om het apparaat in te stellen. Andere gebruikers van dezelfde tenant kunnen zich vervolgens aanmelden bij het apparaat vanaf het aanmeldingsscherm of door op de tegel Gebruiker in het startvenster te tikken. Er kan slechts één gebruiker tegelijk worden aangemeld. Wanneer een gebruiker zich meldt, HoloLens de vorige gebruiker af. De eerste gebruiker op het apparaat wordt beschouwd als de eigenaar van het apparaat, behalve in het geval van Azure AD Join, meer informatie [over apparaateigenaren.](security-adminless-os.md#device-owner)

Alle gebruikers kunnen de apps gebruiken die op het apparaat zijn geïnstalleerd. Elke gebruiker heeft echter zijn eigen app-gegevens en voorkeuren. Als u een app van het apparaat verwijdert, wordt deze voor alle gebruikers verwijderd.  

Apparaten die zijn ingesteld met Azure AD-accounts, kunnen zich niet aanmelden bij het apparaat met een Microsoft-account. Alle volgende accounts die worden gebruikt, moeten Azure AD-accounts zijn van dezelfde tenant als het apparaat. U kunt zich [nog steeds aanmelden met een Microsoft-account bij apps](hololens-identity.md#setting-up-multi-user-support-azure-ad-only) die dit ondersteunen (zoals de Microsoft Store). Als u het gebruik van Azure AD-accounts wilt wijzigen in Microsoft-accounts voor aanmelding bij het apparaat, moet [u het apparaat opnieuw gebruiken.](hololens-recovery.md#clean-reflash-the-device)

> [!NOTE]
> **HoloLens (eerste generatie)** begon meerdere Azure AD-gebruikers te ondersteunen in de [update van Windows 10 april 2018](/windows/mixed-reality/release-notes-april-2018) als onderdeel van [Windows Holographic for Business](hololens-upgrade-enterprise.md).

### <a name="multiple-users-listed-on-sign-in-screen"></a>Meerdere gebruikers die worden vermeld op het aanmeldingsscherm

Voorheen werd in het scherm Aanmelden alleen de meest recent aangemelde gebruiker weergegeven, evenals het toegangspunt 'Andere gebruiker'. We hebben feedback van klanten ontvangen dat dit niet voldoende is als meerdere gebruikers zich hebben aangemeld bij het apparaat. Ze moesten nog steeds hun gebruikersnaam opnieuw typen, enzovoort.

Geïntroduceerd in [Windows Holographic, versie 21H1,](hololens-release-notes.md#windows-holographic-version-21h1)wanneer u Andere gebruiker selecteert rechts van het invoerveld Pincode, worden op het aanmeldingsscherm meerdere gebruikers weergegeven met een eerdere aanmelding bij het apparaat.  Hierdoor kunnen gebruikers hun gebruikersprofiel selecteren en zich vervolgens aanmelden met hun Windows Hello referenties. Een nieuwe gebruiker kan ook worden toegevoegd aan het apparaat vanaf deze pagina Andere gebruikers via de **knop Account** toevoegen.

In het menu Andere gebruikers wordt op de knop Andere gebruikers de laatste gebruiker weergegeven die is aangemeld bij het apparaat. Selecteer deze knop om terug te keren naar het aanmeldingsscherm voor deze gebruiker.

![Standaard aanmeldingsscherm](./images/multiusers1.jpg)

<br>

![Aanmeldingsscherm voor andere gebruikers](./images/multiusers2.jpg)

## <a name="removing-users"></a>Gebruikers verwijderen

U kunt een gebruiker van het apparaat verwijderen door naar Instellingen  >  **Accounts**  >  **Other people te gaan.** Met deze actie wordt ook ruimte vrij gemaakt door alle app-gegevens van die gebruiker van het apparaat te verwijderen.  

## <a name="using-single-sign-on-within-an-app"></a>Een aanmelding gebruiken in een app

Als app-ontwikkelaar kunt u profiteren van gekoppelde identiteiten op HoloLens met behulp van de [API's van Windows Account Manager,](/uwp/api/Windows.Security.Authentication.Web.Core)net als op andere Windows-apparaten. Sommige codevoorbeelden voor deze API's zijn beschikbaar op GitHub: [Voorbeeld van webaccountbeheer.](https://go.microsoft.com/fwlink/p/?LinkId=620621)

Accountonderbreken die kunnen optreden, zoals het aanvragen van toestemming van de gebruiker voor accountgegevens, verificatie in twee factoren, enzovoort, moeten worden afgehandeld wanneer de app een verificatie-token aanvraagt.

Als uw app een specifiek accounttype vereist dat nog niet eerder is gekoppeld, kan uw app het systeem vragen om de gebruiker te vragen om er een toe te voegen. Met deze aanvraag wordt het deelvenster met accountinstellingen als modaal onderliggende taak van uw app ingesteld. Voor 2D-apps wordt dit venster rechtstreeks over het midden van uw app weergegeven. Voor Unity-apps wordt de gebruiker met deze aanvraag kort uit uw holografische app haalt om het onderliggende venster weer te geven. Zie [WebAccountCommand Class](/uwp/api/Windows.UI.ApplicationSettings.WebAccountCommand)voor meer informatie over het aanpassen van de opdrachten en acties in dit deelvenster.

## <a name="enterprise-and-other-authentication"></a>Ondernemingsverificatie en andere verificatie

Als uw app gebruikmaakt van andere typen verificatie, zoals NTLM, Basic of Kerberos, kunt u [de gebruikersinterface](/uwp/api/Windows.Security.Credentials.UI) van Windows Credential gebruiken om de referenties van de gebruiker te verzamelen, te verwerken en op te slaan. De gebruikerservaring voor het verzamelen van deze referenties is vergelijkbaar met andere cloudgestuurde accountonderbreken en wordt weergegeven als een onderliggende app boven op uw 2D-app of onderbreekt kort een Unity-app om de gebruikersinterface weer te geven.

## <a name="deprecated-apis"></a>Afgeschafte API's

Een manier waarop ontwikkelen voor HoloLens verschilt van ontwikkelen voor Desktop is dat de [OnlineIDAuthenticator-API](/uwp/api/Windows.Security.Authentication.OnlineId.OnlineIdAuthenticator) niet volledig wordt ondersteund. Hoewel de API een token retourneert als het primaire account een goede status heeft, geven interrupts zoals in dit artikel geen gebruikersinterface weer voor de gebruiker en wordt het account niet correct geverifieerd.

## <a name="frequently-asked-questions"></a>Veelgestelde vragen

### <a name="is-windows-hello-for-business-supported-on-hololens-1st-gen"></a>Wordt Windows Hello for Business ondersteund op HoloLens (eerste generatie)?

Windows Hello for Business (die ondersteuning biedt voor het gebruik van een pincode om u aan te melden) wordt ondersteund voor HoloLens (1e generatie). Als u Windows Hello voor Bedrijven wilt toestaan om u aan te melden bij HoloLens:

1. Het HoloLens moet worden [beheerd door MDM.](hololens-enroll-mdm.md)
1. U moet Windows Hello voor Bedrijven inschakelen voor het apparaat. ([Zie de instructies voor Microsoft Intune.](/intune/windows-hello))
1. Op HoloLens kan de gebruiker vervolgens de  >  **Instellingen-aanmeldingsopties** Pincode toevoegen gebruiken  >   om een pincode in te stellen.

> [!NOTE]
> Gebruikers die zich aanmelden met behulp van een Microsoft-account kunnen ook een pincode **instellen** in Instellingen opties voor aanmelden  >    >  **Pincode toevoegen.** Deze pincode is gekoppeld [aan Windows Hello,](https://support.microsoft.com/help/17215/windows-10-what-is-hello)in plaats [Windows Hello voor Bedrijven.](/windows/security/identity-protection/hello-for-business/hello-overview)

### <a name="how-is-iris-biometric-authentication-implemented-on-hololens-2"></a>Hoe wordt biometrische irisverificatie geïmplementeerd op HoloLens 2?

HoloLens 2 ondersteunt Iris-verificatie. Iris is gebaseerd op Windows Hello technologie en wordt ondersteund voor gebruik door zowel Azure Active Directory als Microsoft-accounts. Iris wordt op dezelfde manier geïmplementeerd als andere Windows Hello technologieën en bereikt biometriebeveiliging FAR van 1/100.000.

Zie de [biometrische vereisten en specificaties voor Windows Hello](/windows-hardware/design/device-experiences/windows-hello-biometric-requirements) voor meer informatie. Meer informatie over [Windows Hello](/windows-hardware/design/device-experiences/windows-hello) en [Windows Hello for Business](/windows/security/identity-protection/hello-for-business/hello-identity-verification). 

### <a name="how-does-the-type-of-account-affect-sign-in-behavior"></a>Wat is de invloed van het type account op het aanmeldingsgedrag?

Als u beleidsregels voor aanmelden toe passen, wordt het beleid altijd in acht genomen. Als er geen beleid voor aanmelden is toegepast, zijn dit de standaardgedragsinstellingen voor elk accounttype:

- **Azure AD:** vraagt standaard om verificatie en kan worden geconfigureerd **door Instellingen** om niet langer om verificatie te vragen.
- **Microsoft-account:** vergrendelingsgedrag is anders bij automatisch ontgrendelen, maar aanmeldingsverificatie is nog steeds vereist bij opnieuw opstarten.
- **Lokaal account:** vraagt altijd om verificatie in de vorm van een wachtwoord, niet configureerbaar in **Instellingen**

> [!NOTE]
> Timers voor inactiviteit worden momenteel niet ondersteund, wat betekent dat het **beleid AllowIdleReturnWithoutPassword** alleen wordt in acht genomen wanneer het apparaat naar StandBy gaat.

## <a name="additional-resources"></a>Aanvullende bronnen

Lees veel meer over beveiliging en verificatie van gebruikersidentiteiten in Windows 10 [documentatie over beveiliging en identiteit van gebruikers.](/windows/security/identity-protection/)

Meer informatie over het instellen van een hybride identiteitsinfrastructuur door de [Azure Hybrid Identity-documentatie](/azure/active-directory/hybrid/).
