---
title: Implementatiehandleiding - Bedrijfsgeconnecteerde HoloLens 2 dynamics 365-handleidingen - Configureren
description: Meer informatie over het instellen van configuraties voor het implementeren van HoloLens 2 via een bedrijfsnetwerk verbonden met Dynamics 365-handleidingen.
keywords: HoloLens, beheer, verbonden met het bedrijf, Dynamics 365 Guides, AAD, Azure AD, MDM, Mobile Device Management
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
ms.openlocfilehash: 939efc28a0c3255cc9a38af3cd8dd9aa8fc2ac98
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/19/2021
ms.locfileid: "111377771"
---
# <a name="configure---corporate-connected-guide"></a>Configureren - Handleiding voor verbonden bedrijfsgegevens

## <a name="azure-users-and-groups"></a>Azure-gebruikers en -groepen

Azure, en Intune door die extensie, maakt gebruik van gebruikers en groepen om configuraties en licenties toe te wijzen. Om deze implementatiestroom te valideren en te kunnen controleren of u een handleiding kunt maken en gebruiken, hebt&#39;een gebruikersaccount nodig.

We kunnen één gebruikersgroep specifiek maken voor het toewijzen van licenties.

Als u geen&#39;hebt tot twee Azure AD-accounts in een gebruikersgroep, kunt u deze gebruiken; hier zijn de snelstartgidsen voor:

- [Een gebruiker maken](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-user)
- [Een groep maken](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-group)
- [Gebruikers toevoegen aan een groep:](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) gemaakte gebruikers toevoegen om een groep te maken
- [Azure AD configureren zodat een gebruikersgroep apparaten kan deelnemen:](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) zorg ervoor dat de nieuwe gebruikersgroep toestemming heeft om apparaten in te schrijven bij Azure AD

## <a name="auto-enrollment-on-hololens-2"></a>Automatische inschrijving op HoloLens 2

Voor een soepele en naadloze ervaring kunt u Azure Active Directory Join (AADJ) en automatische inschrijving bij Intune instellen voor HoloLens 2-apparaten. Hierdoor kunnen gebruikers hun aanmeldingsreferenties voor de organisatie invoeren tijdens OOBE, zich automatisch registreren bij Azure AD en het apparaat registreren bij MDM.

Met behulp [van Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home)kunnen we services selecteren en door een paar pagina's navigeren totdat we Een Premium-proefversie krijgen kunnen selecteren. U merkt misschien dat er Azure Active Directory Premium 1 en 2 is: voor Automatische inschrijving is P1 voldoende. We kunnen Intune selecteren, het gebruikersbereik voor automatische inschrijving selecteren en de groep selecteren die eerder is gemaakt.

Lees de handleiding over het inschakelen van automatische inschrijving [voor Intune](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment)voor meer informatie en stappen.

## <a name="corporate-wi-fi-connectivity"></a>Connectiviteit Wi-Fi bedrijfsnetwerk

Voor Wi-Fi bedrijfsverbindingen is doorgaans verificatie op basis van certificaten vereist voor klanten die gebruikmaken van HoloLens 2. U moet dergelijke certificaten implementeren met behulp van een Simple Certificate Enrollment Protocol-certificaatinfrastructuur (SCEP) of PKCS-certificaatinfrastructuur (Public Key Cryptography Standard) die is geïntegreerd met uw MDM-oplossing. Als u Intune gebruikt om Wi-Fi, certificaten en proxy-instellingen te implementeren, ontstaat er een naadloze ervaring voor eindgebruikers.
 
### <a name="deploy-certificates-and-wi-fi-profiles"></a>Certificaten en Wi-Fi implementeren

Volg deze stappen om certificaten en profielen via Microsoft Endpoint Manager implementeren:

1. Maak een profiel voor elk van de basis- en tussencertificaten (zie [Vertrouwde certificaatprofielen maken).](https://docs.microsoft.com/intune/protect/certificates-configure#create-trusted-certificate-profiles) Elk van deze profielen moet een beschrijving hebben die een vervaldatum in DD/MM/YYYY-indeling bevat. 

    > [!CAUTION]
    > **Certificaatprofielen zonder een vervaldatum worden niet geïmplementeerd.**

2.  Maak een profiel voor elke SCEP- of PKCS-certificaten (zie Een SCEP-certificaatprofiel maken of Een [PKCS-certificaatprofiel](https://docs.microsoft.com/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)maken) Elk van deze profielen moet een beschrijving hebben met een vervaldatum in DD/MM/YYYY-indeling. 

    > [!CAUTION]
    > **Certificaatprofielen zonder een vervaldatum worden niet geïmplementeerd.**

    > [!Note]
    > Omdat de HoloLens 2 wordt beschouwd als een gedeeld apparaat, dat wil zeggen meerdere gebruikers per apparaat, wordt het aanbevolen om waar mogelijk Apparaatcertificaten te implementeren in plaats van gebruikerscertificaten voor Wi-Fi-verificatie.

3.  Maak een profiel voor uw zakelijke Wi-Fi netwerk (zie [Wi-Fi-instellingen voor Windows 10 en latere apparaten).](https://docs.microsoft.com/intune/wi-fi-settings-windows) Binnen uw Wi-Fi kunt u de proxyinstellingen binnen uw organisatie gebruiken.
 
    Uw opties zijn:
    - **Geen**: Er zijn geen proxyinstellingen geconfigureerd.
    - **Handmatig configureren:** voer het **IP-adres van de proxyserver en** het **poortnummer in.**
    - **Automatisch configureren**: Voer de URL in die naar een proxyscript voor automatische configuratie (PAC) verwijst. Voer bijvoorbeeld *http://proxy.contoso.com/proxy.pac* in.

    Zie [PAC-bestand (Proxy Auto-Configuration)](https://developer.mozilla.org/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_(PAC)_file) (hiermee opent u een niet-Microsoft-site) voor meer informatie over PAC-bestanden.
 
    > [!Note]
    > Het wordt aanbevolen om het Wi-Fi waar mogelijk toe te Wi-Fi aan Apparaatgroepen in plaats van Gebruikersgroepen.
     
    > [!Tip]
    > U kunt ook een werkprofiel Wi-Fi exporteren vanaf een Windows 10 pc in uw bedrijfsnetwerk. Met deze export maakt u een XML-bestand met alle huidige instellingen. Importeer dit bestand vervolgens in Intune en gebruik het als het Wi-Fi profiel voor uw HoloLens 2 apparaten. Zie [Wi-Fi-instellingen voor Windows-apparaten exporteren en importeren](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-import-windows-8-1).

1.  [Wijs](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign) de apparaatprofielen toe aan de HoloLens-apparaatgroep.

2.  [Controleer](https://docs.microsoft.com/mem/intune/configuration/device-profile-monitor) de apparaatprofielen in Intune.

Als er problemen zijn met Wi-Fi profielen, verwijzen wij u naar Problemen met [Wi-Fi-apparaatconfiguratieprofielen in Intune oplossen.](https://docs.microsoft.com/troubleshoot/mem/intune/troubleshoot-wi-fi-profiles)

## <a name="troubleshooting-external-internet-access-when-corp-connected"></a>Problemen met externe internettoegang oplossen wanneer Corp verbonden is
Wanneer services proberen geen proxy te gebruiken, kunnen ze proberen verbinding te maken via de firewall. U kunt een lijst met specifieke eindpunten toevoegen aan uw firewallregels om deze problemen op te lossen.

Als u bent geblokkeerd bij firewallpoorten, moet u enkele algemene eindpunten [voor](https://docs.microsoft.com/hololens/hololens-offline) HoloLens inschakelen.

U kunt ook de gidsen specifieke poorten inschakelen: [via internet toegankelijke URL's die vereist zijn voor connectiviteit met Microsoft Dynamics CRM Online.](https://support.microsoft.com/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami)

## <a name="app-deployment"></a>App-implementatie

Het implementeren van een LOB-app via MDM is een methode die eenvoudig schaalbaar is en automatisch op uw apparaten kan worden geïmplementeerd bij inschrijving in een gemaakte groep.

Als u nog steeds apps ontwikkelt of nog geen apps hebt, kunt u een voorbeeld-app van de MRTK-voorbeeldhub gebruiken. Deze voorbeeld-app is klaar voor gebruik en vereist niet het gebruik van Unity of Visual Studio. [Download de mrtk-voorbeeld-app](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App).

Als u liever uw eigen app gebruikt of geïnteresseerd bent in app-ontwikkeling voor Mixed Reality, kunt u onze documentatie voor ontwikkelaars [Mixed Reality lezen.](https://docs.microsoft.com/windows/mixed-reality/design/design)

> [!NOTE]
> De systeemvereisten voor HoloLens-apparaten zijn gebaseerd op de architectuur van de app-build. HoloLens 2 gebruiken ARM-architectuur. Wanneer u uw apps in Visual Studio, moet u ervoor zorgen dat u de juiste architectuur voor het apparaat hebt geselecteerd en eventuele benodigde afhankelijkheden hebt op te nemen.

> [!IMPORTANT]
> Bij het implementeren van LOB-apps is het belangrijk dat u ook het certificaat uploadt naar Intune en dit toewijst aan dezelfde groep die is bedoeld om de app te gebruiken, anders wordt het certificaat niet goed geïnstalleerd.

### <a name="upload-and-assign-the-app"></a>De app uploaden en toewijzen

1. Navigeer naar [het MEM-beheercentrum.](https://endpoint.microsoft.com/#home)

2. Selecteer **Apps**  ->  **Alle apps** en selecteer de **knop +** Toevoegen.

3. Selecteer onder Overige de optie **Line-Of-Business-app.** Klik **op selecteren.**

4. Selecteer het app-pakketbestand. Dit is uw APPXBUNDLE-bestand of in ons geval is de app _MRTK Examples Hub \_ 2.4.2.0 \_ arm \_ Master.appxbundle._

5. U krijgt een melding over ontbrekende afhankelijkheden. In dit geval moeten we _Microsoft.VCLibs.ARM.14.00.appx uploaden._ Zoek het bestand onder **Een bestand selecteren.**

6. Selecteer OK.

7. In het volgende scherm worden de vereiste velden automatisch ingevuld. Selecteer **Next**.

8. Voeg onder Vereist de eerder gemaakte groep toe om deze app vereist te maken voor de groep. Hierdoor wordt de app automatisch gedownload naar ingeschreven apparaten in de groep. Selecteer **Next**.

9. Selecteer **Maken**.

Meer informatie: [Apps toewijzen aan groepen in Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/apps-deploy#assign-an-app)

## <a name="setup-guides-application-licenses-dataverse-and-authoring"></a>Installatiehandleidingen: toepassingslicenties, gegevensverse en ontwerp

Als u Dynamics 365 Guides wilt gebruiken, moet u wat voorbereidingen treffen. Er zijn drie gebieden waarop we ons moeten voorbereiden; gebruikers, gegevensverse en de handleidingen zelf.

### <a name="users-and-application-licenses"></a>Gebruikers en toepassingslicenties

Iemand die Gebruikshandleidingen wil gebruiken, moet een Azure AD-account gebruiken dat we eerder in deze handleiding hebben ingesteld.

U moet ook een Dynamics 365 Guides-licentie toewijzen aan de gebruiker die u hebt gemaakt. U doet dit vanuit de [Microsoft 365-beheercentrum](https://admin.microsoft.com/AdminPortal/Home). Wijs ook de licentie toe aan uw primaire Azure-account.

Volg [deze korte handleiding](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-one#assign-the-dynamics-365-guides-license-to-user-accounts) met afbeeldingen voor stapsgewijs instructies voor het toepassen van toepassingslicenties.

### <a name="set-up-the-dataverse"></a>Dataverse instellen

Als u een [productieomgeving wilt instellen,](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two#set-up-a-production-environment-for-purchased-licenses-only) moet u aan twee vereisten voldoen. U moet [**de rol**](https://docs.microsoft.com/power-platform/admin/database-security)  Systeembeheerder hebben en u moet een Power Apps-licentie [**(of**](https://docs.microsoft.com/power-platform/admin/signup-question-and-answer) een [**Dynamics 365 Guides-licentie**](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-one) met een Power Apps licentie). Als u de Azure AD hebt gemaakt door deze handleiding te volgen, voldoet u aan de rolvereisten voor systeembeheerder. In de vorige stap hebben we ook een gidsenlicentie toegewezen.

In deze handleiding voor het [maken van een Microsoft Dataverse-omgeving:](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two)

1. Begin met de [Power Platform-beheercentrum](https://admin.powerplatform.microsoft.com/environments) en maak een nieuwe omgeving.
2. Wanneer u de **nieuwe omgeving maakt** voor het **type** dat u&#39;selecteert u **Productie**.
3. Is het belangrijk dat u De database **voor deze omgeving maken in-/uitschakelen?**  optie op **Ja.**
4. Stel in  **het dialoogvenster Database**  toevoegen de optie  **Dynamics 365-apps inschakelen**  in op  **Ja.**

U kunt het beste de maximale bestandsgrootte van items in uw gegevensverse verhogen. Door de maximale bestandsgrootte te vergroten, kunt u grotere 3D-modellen of videobestanden uploaden die u later in uw handleidingen gaat gebruiken. Volg een korte handleiding om [de maximale grootte van het uploadbestand te wijzigen.](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two#change-the-maximum-upload-file-size)

Ten laatste moet u de [oplossing installeren en configureren.](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two#install-and-configure-the-solution) Selecteer in [Power Platform-beheercentrum](https://admin.powerplatform.microsoft.com/environments)de optie **Resources** \& gt;  **Dynamics 365-apps,** **selecteer Dynamics 365-handleidingen** in de lijst en selecteer **vervolgens Installeren.**  

U moet [een beveiligingsrol Gidsen toevoegen](https://docs.microsoft.com/dynamics365/mixed-reality/guides/assign-role) voordat u de apps kunt gebruiken.

### <a name="create-a-test-guide-on-your-pc-via-authoring"></a>Een testhandleiding maken op uw pc via Authoring

Wanneer u Handleidingen maakt, begint u altijd op uw pc. Het maken van de stappen, het selecteren van modellen en het verankeren van de handleiding. Dit wordt gevolgd door het plaatsen van inhoud voor uw handleiding later in de ontwerpmodus op uw HoloLens-apparaat. Voor deze handleiding raden we u aan een korte testhandleiding te maken met minimale stappen en modellen.

Als u meer wilt weten over het maken van handleidingen, begint u hier met het [ontwerpoverzicht](https://docs.microsoft.com/dynamics365/mixed-reality/guides/authoring-overview). Bekijk deze korte video voor een snel overzicht.

<iframe width="560" height="315" src="https://www.youtube.com/embed/EC24dMlAy90" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="optional-kiosk-mode"></a>Optioneel: Kioskmodus

De kioskmodus is een modus waarmee een IT-beheerder de gebruikersinterface van het menu Start kan configureren om slechts één app of een selectie apps weer te geven. Een kiosk kan ook worden toegepast op specifieke gebruikers, groepen of op apparaatniveau; en in sommige gevallen moet u bepaalde gebruikers uitsluiten van de kiosk, zodat ze nog steeds toegang hebben tot het normale menu Start.

De kioskmodus heeft veel verschillende variabelen, zowel in bereik als in configuraties die kunnen worden ingesteld, evenals methoden voor het implementeren van de kiosk op de HoloLens. Vanwege al deze variabelen wordt de kioskmodus voor deze handleiding optioneel gelaten en komt deze niet meer terug.  Als u denkt dat u een bedrijf nodig hebt om beschikbare apps te beperken tot gebruikers of als u meer wilt weten, kunt u leren hoe u [HoloLens](https://docs.microsoft.com/hololens/hololens-kiosk)kunt instellen als kiosk.

## <a name="optional-wdac"></a>Optioneel: WDAC

Met WDAC kan een IT-beheerder zijn apparaten configureren om het starten van apps op apparaten te blokkeren. Dit verschilt van de apparaatbeperkingsmethoden, zoals de kioskmodus, waarbij de gebruiker een gebruikersinterface krijgt te zien die de apps op het apparaat verbergt, maar die nog steeds kan worden gestart. Terwijl WDAC is geïmplementeerd, zijn de apps nog steeds zichtbaar in de lijst Alle apps, maar WDAC voorkomt dat deze apps en processen kunnen worden gestart door de gebruiker van het apparaat.

Voor meer informatie verwijzen we [naar WDAC](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)en Windows PowerShell apps toestaan of blokkeren op HoloLens 2 apparaten met Microsoft Intune.

[Windows Defender Application Control - WDAC](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)

## <a name="next-step"></a>Volgende stap 
> [!div class="nextstepaction"]
> [Zakelijke verbonden implementatie - Implementeren](hololens2-corp-connected-deploy.md)