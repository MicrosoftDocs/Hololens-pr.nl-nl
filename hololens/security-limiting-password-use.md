---
title: Wachtwoordgebruik beperken
description: wachtwoordgebruik beperken voor HoloLens
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: security, hololens, limiting password use, password, hololens password, sign-in, sign in, windows hello, hello, windows account manager, FIDO2 sign in, FIDO 2, WE PASSWORDTHN, local account, hololens security
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 074fffc8350dd6deb876a19320397674bcac3e46
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639298"
---
# <a name="limiting-password-use"></a>Wachtwoordgebruik beperken

De meeste computersystemen maken tegenwoordig gebruik van gebruikersreferenties als basis voor beveiliging, waardoor ze afhankelijk zijn van herbruikbare, door de gebruiker gemaakte wachtwoorden. Dit heeft ertoe geleid dat wachtwoorden ook de meest voorkomende oorzaak worden van inbreuk op accounts en inbreuk op gegevens. Als voorbeeld hiervan kunnen wachtwoorden worden onderschept bij verzending of gestolen van een server (door phishing- of wachtwoordaanvallen) en kunnen ze worden aangetast om toegang te krijgen tot een gebruikersaccount.

Om de beveiliging en accountbeveiliging te verbeteren, biedt HoloLens 2 de mogelijkheid om sterke, hardwarematige referenties zonder wachtwoord (inclusief Windows Hello) in te stellen voor het aanmelden van apparaten en naadloze toegang te bieden tot de Microsoft Cloud.

## <a name="signing-in-from-another-device"></a>Aanmelden vanaf een ander apparaat

HoloLens 2 biedt aanmeldingsopties voor externe apparaten voor Azure Active Directory-werkaccounts tijdens de eerste installatie van het apparaat en het aanmelden van gebruikers om de noodzaak tot het typen van complexe wachtwoorden te verminderen en de noodzaak van wachtwoorden als referenties te minimaliseren. Gebruikers en organisaties die smartcards gebruiken om te verifiëren, hebben moeite met het gebruik van deze referenties op apparaten zoals HoloLens 2, en vaak ontwikkelen organisaties gecompliceerde systemen en kostbare processen om het probleem op te lossen. Om dit probleem op te lossen, biedt Azure AD twee opties voor aanmelden met een wachtwoord HoloLens 2.

De eerste verificatiemethode is afhankelijk van nieuwe mogelijkheden in de Microsoft Authenticator-app om verificatie op basis van sleutels te bieden waarmee gebruikersreferenties kunnen worden gekoppeld aan een apparaat. Zodra de beheerder de tenant heeft ingeschakeld, krijgen gebruikers tijdens het instellen van het HoloLens een bericht te zien waarin staat dat ze op een getal in hun app moeten tikken. Vervolgens moeten ze overeenkomen met het nummer in hun authenticator-app, goedkeuren kiezen, hun pincode of biometrische gegevens verstrekken en volledige verificatie voor hun HoloLens instellen om door te gaan. Dit wordt uitgebreid beschreven in [aanmelden zonder wachtwoord.](/azure/active-directory/authentication/howto-authentication-passwordless-phone)

De tweede is een apparaatcodestroom die intuïtief is voor gebruikers en waarvoor geen extra infrastructuur nodig is.  Dit externe aanmeldingsgedrag is afhankelijk van een ander vertrouwd apparaat dat het voorkeursverificatiemechanisme van de organisatie ondersteunt en wanneer dit is voltooid, worden tokens terug gegeven aan de HoloLens om de aanmelding of het instellen van het apparaat te voltooien. De stappen in deze stroom zijn:

  1. Een gebruiker die de initiële apparaatinstallatie of aanmeldingsstromen op OOBE doormaakt, krijgt een koppeling 'Aanmelden vanaf een ander apparaat' te zien en tikt er op. Hiermee wordt een externe aanmeldingssessie gestart.
  1. De gebruiker krijgt vervolgens een polling-pagina te zien die een korte URI () bevat die naar het eindpunt voor apparaatverificatie van de [https://microsoft.com/devicelogin](https://microsoft.com/devicelogin) Azure AD Secure Token Service (STS) wijst. De gebruiker krijgt ook een een time-code te zien die veilig wordt gegenereerd in de cloud en een maximale levensduur van 15 minuten heeft. Naast het genereren van code maakt Azure AD ook een versleutelde sessie bij het initiëren van de externe aanmeldingsaanvraag in de vorige stap. Samen worden de URI en code gebruikt om de externe aanmeldingsaanvraag goed te keuren.
  1. De gebruiker navigeert vervolgens vanaf een ander apparaat naar de URI en wordt gevraagd de code in te voeren die wordt weergegeven op het HoloLens 2 apparaat.
  1. Zodra de gebruiker de code invoert, wordt in Azure AD STS een pagina weergegeven die het HoloLens 2-apparaat van de gebruiker aangeeft dat de aanvraag voor externe aanmelding heeft geactiveerd en het genereren van de code heeft aangevraagd. De gebruiker wordt vervolgens gevraagd om bevestiging om phishing-aanvallen te voorkomen.
  1. Als de gebruiker ervoor kiest om door te gaan met aanmelden bij de weergegeven 'toepassing', wordt de gebruiker door Azure AD STS om zijn of haar referenties gevraagd. Bij een geslaagde verificatie werkt Azure AD STS de externe sessie in de cache bij als goedgekeurd, samen met een autorisatiecode.
  1. Ten slotte ontvangt de pollingpagina op het HoloLens 2-apparaat van de gebruiker een 'Geautoriseerd' antwoord van Azure AD en wordt de gebruikerscode en de bijbehorende opgeslagen autorisatiecode gevalideerd en worden OAuth-tokens gegenereerd zoals aangevraagd om de installatie van het apparaat te voltooien. Het gemaakte verificatie-token is 1 uur geldig en het vernieuwings token heeft een levensduur van 90 dagen.

De codegeneratie- en versleutelingsalgoritmen die in deze stroom worden gebruikt, zijn beide FIPS-compatibel. HoloLens 2 gebruiken de TPM om apparaatsleutels te beveiligen en tokens te versleutelen die zijn gegenereerd na gebruikersverificatie met behulp van met hardware beveiligde sleutels. Meer informatie over beveiliging van tokens op HoloLens 2 wordt gedeeld in [Wat is een Primary Refresh Token (PRT)](/azure/active-directory/devices/concept-primary-refresh-token).

## <a name="device-sign-in-with-windows-hello"></a>Apparaat aanmelden met Windows Hello

[Windows Hello](/windows/security/identity-protection/hello-for-business/hello-identity-verification) biedt opties zonder wachtwoord die rechtstreeks in het besturingssysteem zijn ingebouwd, zodat gebruikers zich met Iris of pincode kunnen aanmelden bij het apparaat. Pincode is altijd beschikbaar als referentie en is vereist voor het instellen van het apparaat, terwijl Iris optioneel is en kan worden overgeslagen. Gebruikers kunnen zich aanmelden bij HoloLens apparaten met hun persoonlijke Microsoft-account of Azure Active Directory zonder een [wachtwoord in te voeren.  ](/azure/active-directory/authentication/concept-authentication-passwordless) Opties zoals deze bieden gebruikers snelle, beveiligde toegang tot hun volledige Windows ervaring, apps, gegevens, websites en services. De strategie van Microsoft voor wachtwoordloze ervaringen wordt hier beschreven.

Wanneer een Windows Hello wordt gemaakt, brengt deze een vertrouwde relatie tot stand met een id-provider en maakt het een asymmetrisch sleutelpaar voor verificatie. Een Windows Hello -beweging (zoals iris of pincode) biedt entropie voor het ontsleutelen van een persoonlijke sleutel die wordt gebruikt door de Trusted Platform Module(TPM)-chip van het apparaat. Deze persoonlijke sleutel wordt vervolgens gebruikt voor het ondertekenen van aanvragen die worden verzonden naar een verificatieserver. Na een geslaagde verificatie krijgt de gebruiker toegang tot zijn e-mail, foto's en andere accountinstellingen.

Zie de volgende infographic voor meer informatie:

  ![Windows Hello Aanmelden](images/security-hello-sign-in.png)
  
In de bovenstaande afbeelding staat nonce voor 'number once' en is het een willekeurig of semi-willekeurig gegenereerd getal. Zodra de Windows Hello biometrische gegevens of pincode is ingesteld, wordt het apparaat waarop het is ingericht nooit meer gebruikt. Zelfs als de pincode van de Windows Hello wordt gestolen, bijvoorbeeld via een phishing-aanval, is het onbruikbaar zonder het fysieke [apparaat van de gebruiker.](/windows/security/identity-protection/hello-for-business/hello-why-pin-is-better-than-password)

Voor extra beveiliging worden Windows Hello-referenties beveiligd door de Trusted Platform Module (TPM) om de referenties bestand te maken tegen manipulatie en worden ze aangevuld met bescherming tegen meerdere onjuiste vermeldingen en bescherming tegen schadelijke software om blootstelling te voorkomen. Lees dit overzicht van SSO-methoden voor meer informatie over Single Sign-On [(SSO).](/azure/active-directory/manage-apps/what-is-single-sign-on)

Irisverificatie valt terug op de pincode. Als u een nieuwe pincode (een sterke ver authenticator) op het apparaat wilt instellen, moet de gebruiker onlangs Meervoudige verificatie [(MFA)](/azure/active-directory/authentication/concept-mfa-howitworks) hebben doorlopen om het proces te voltooien.

## <a name="single-sign-on-with-web-account-manager"></a>Een aanmelding met webaccountbeheer

Met eenmalige aanmelding (SSO) kunnen gebruikers die geen wachtwoord hebben zich aanmelden bij het apparaat, met behulp van het persoonlijke account van de gebruiker of het werk- of schoolaccount. De gebruiker wordt automatisch geautoriseerd met SSO voor alle geïntegreerde apps en services via de [webaccountbeheer API's.](/uwp/api/Windows.Security.Authentication.Web.Provider?view=winrt-19041&preserve-view=true)

Zodra een identiteit via één toepassing is toegevoegd, kan deze, met toestemming van de gebruiker, beschikbaar worden voor alle apps en services met behulp van integratie op systeemniveau. Dit vermindert de belasting voor het aanmelden van apps aanzienlijk en biedt gebruikers een naadloze identiteitservaring.

Ga voor meer informatie over het implementeren webaccountbeheer API's naar [Webaccountbeheer API's](/windows/uwp/security/web-account-manager)implementeren.

  ![beveiligings-API](images/security-api-img.png)
  
Voor app-suites met gespecialiseerde verificatievereisten is het framework webaccountbeheer (WAM) uit te werken naar aangepaste id-providers. Gebruikers kunnen de aangepaste id-provider, verpakt als een UWP-app (Universal Windows Platform) downloaden van de Microsoft Store, om eenmalige aanmelding in teschakelen voor andere apps die zijn geïntegreerd met die id-provider.

Zie Custom WAM Identity Provider API reference (Referentie voor aangepaste [WAM Identity Provider-API's)](/uwp/api/Windows.Security.Authentication.Web.Provider?view=winrt-19041&preserve-view=true)voor meer informatie over het implementeren van aangepaste WAM-id-providers.

## <a name="windows-hello-and-fido2-sign-in-with-webauthn"></a>Windows Hello en FIDO2-aanmelding met WebAuthn

HoloLens 2 kunnen gebruikersreferenties (zoals Windows Hello- of FIDO2-beveiligingssleutels) gebruiken om zich veilig aan te melden op internet via Microsoft Edge en websites die WebAuthn ondersteunen. Met FIDO2 kunnen gebruikersreferenties profiteren van op standaarden gebaseerde apparaten om te verifiëren bij onlineservices.

> [!Note]
> De [Specificaties van WebAuthn](https://www.w3.org/TR/webauthn/) en FIDO2 [CTAP2](https://fidoalliance.org/specs/fido-v2.0-ps-20190130/fido-client-to-authenticator-protocol-v2.0-ps-20190130.html) worden geïmplementeerd in services. De ondertekende metagegevens die zijn opgegeven door WebAuthn en FIDO2 bieden informatie , zoals of de gebruiker aanwezig was, en verifieert de verificatie via de lokale beweging.

Net als Windows Hello wanneer de gebruiker een FIDO2-referentie maakt en registreert, genereert het apparaat (HoloLens 2 of de FIDO2-beveiligingssleutel) een persoonlijke en openbare sleutel op het apparaat. De persoonlijke sleutel wordt veilig op het apparaat opgeslagen en kan alleen worden gebruikt nadat deze is ontgrendeld met behulp van een lokale beweging, zoals een biometrische of pincode. Wanneer de persoonlijke sleutel wordt opgeslagen, wordt de openbare sleutel verzonden naar het Microsoft-account-systeem in de cloud en geregistreerd bij het bijbehorende gebruikersaccount.

Na aanmelding met een MSA- en Azure AD-account verzendt het systeem een gegenereerd getal of gegevensvariabele naar het HoloLens 2 of FIDO2-apparaat. De HoloLens 2 of het apparaat gebruikt de persoonlijke sleutel om de identificatie te ondertekenen. De ondertekende identificatie en metagegevens worden teruggestuurd naar het Microsoft-account systeem en geverifieerd met behulp van de openbare sleutel.

Windows Hello en FIDO2-apparaten implementeren referenties op basis van het HoloLens-apparaat, met name de ingebouwde Trusted Platform Module beveiligde enclave. De TPM-enclave slaat de persoonlijke sleutel op en vereist een biometrische sleutel of pincode om deze te ontgrendelen. Op dezelfde manier is een FIDO2-beveiligingssleutel een klein extern apparaat met een ingebouwde beveiligde enclave waarin de persoonlijke sleutel wordt op basis van een biometrische of pincode vereist om deze te ontgrendelen.

Beide opties bieden tweefactorauthenticatie in één stap, waarbij zowel een geregistreerd apparaat als een biometrische of pincode nodig zijn om u aan te melden. Zie de afbeelding en het proces van de FIDO2-beveiligingssleutel voor meer informatie.

### <a name="strong-authentication-with-fido2-security-key"></a>Sterke verificatie met FIDO2-beveiligingssleutel

  ![FIDO img](images/security-fido2-whfb-smaller.png)

1. De gebruiker sluit de FIDO2-beveiligingssleutel aan HoloLens 2
1. Windows detecteert een FIDO2-beveiligingssleutel
1. HoloLens verzendt een auth-aanvraag
1. Azure AD stuurt nonce terug
1. De gebruiker voltooit het ontgrendelen van persoonlijke sleutelopslag in de beveiligde enclave van de beveiligingssleutel
1. FiDO2-beveiligingssleutel ondertekent niet met persoonlijke sleutel
1. PrT-tokenaanvraag met ondertekende nonce wordt verzonden naar Azure AD
1. Azure AD controleert de FIDO-sleutel
1. Azure AD retourneert PRT en TGT om toegang tot resources mogelijk te maken

MSA en Azure AD zijn een van de eerste relying partijen die verificatie zonder wachtwoord ondersteunen door WebAuthn te implementeren.

Ga voor meer informatie over het gebruik van WebAuthn met toepassingen en/of SDK's naar [WebAuthn-API's](/windows/security/identity-protection/hello-for-business/webauthnapis)voor verificatie zonder wachtwoord op Windows 10 .

HoloLens 2 ondersteunt FIDO2-beveiligingsapparaten die zijn geïmplementeerd voor specificatie en voldoen aan de vereisten die worden vermeld in Azure Active Directory-aanmelding zonder wachtwoord: [FIDO2-beveiligingssleutels](/azure/active-directory/authentication/concept-authentication-passwordless#fido2-security-keys) moeten worden ondersteund.

## <a name="local-accounts"></a>Lokale accounts

Er kan één lokaal account worden geconfigureerd voor implementaties in de offlinemodus. Lokale accounts zijn niet standaard ingeschakeld en moeten worden geconfigureerd tijdens het inrichten van apparaten. Ze moeten zich aanmelden met een wachtwoord en ze bieden geen ondersteuning voor alternatieve verificatiemethoden (zoals [Windows Hello for Business](/windows/security/identity-protection/hello-for-business/hello-overview) of [Windows Hello).](/windows-hardware/design/device-experiences/windows-hello)

Meer informatie over HoloLens gebruikersaccounts vindt u [op HoloLens Identity.](hololens-identity.md)

IT-beheerders passen aan of de gebruiker een MSA-account mag gebruiken voor niet-e-mailgerelateerde verbindingsverificatie en -services via [AllowMicrosoftAccountConnection.](/windows/client-management/mdm/policy-csp-accounts#accounts-allowmicrosoftaccountconnection) Zie Apparaatvergrendeling voor beleidsregels voor wachtwoordconfiguratie, id-beleid en beleid voor [vergrendelingsscherm.](/windows/client-management/mdm/policy-csp-devicelock)
