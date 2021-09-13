---
title: Implementatiehandleiding - Zakelijk verbonden HoloLens 2 met Dynamics 365 Guides - Configureren
description: Meer informatie over het instellen van configuraties voor het implementeren HoloLens 2 apparaten via een bedrijfsnetwerk verbonden met Dynamics 365 Guides.
keywords: HoloLens, beheer, zakelijk verbonden, Dynamics 365 Guides, AAD, Azure AD, MDM, Mobile Device Management
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
ms.openlocfilehash: 9457acd2f53d0d3127d6c68d620b660f6e09866d
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032726"
---
# <a name="configure---corporate-connected-guide"></a>Configureren - Corporate Connected Guide

## <a name="azure-users-and-groups"></a>Azure-gebruikers en -groepen

Azure en Intune voor die extensie gebruiken gebruikers en groepen om configuraties en licenties toe te wijzen. Omwille van het valideren van deze implementatiestroom en de mogelijkheid om te controleren of u een handleiding kunt schrijven en gebruiken, hebt&#39;een gebruikersaccount nodig.

We kunnen één gebruikersgroep maken die specifiek is voor het toewijzen van licenties.

Als u geen&#39;hebt tot twee Azure AD-accounts in een gebruikersgroep, kunt u deze gebruiken; hier zijn de snelstartgidsen voor:

- [Een gebruiker maken](/mem/intune/fundamentals/quickstart-create-user)
- [Een groep maken](/mem/intune/fundamentals/quickstart-create-group)
- [Gebruikers toevoegen aan een groep](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) : gemaakte gebruikers toevoegen om een groep te maken
- [Azure AD configureren zodat een gebruikersgroep apparaten kan deelnemen:](/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) zorg ervoor dat de nieuwe gebruikersgroep toestemming heeft om apparaten in te schrijven bij Azure AD

## <a name="auto-enrollment-on-hololens-2"></a>Automatische inschrijving op HoloLens 2

Voor een soepele en naadloze ervaring is het instellen van Azure Active Directory Join (AADJ) en automatische inschrijving bij Intune voor HoloLens 2-apparaten de beste manier. Hierdoor kunnen gebruikers hun aanmeldingsreferenties voor de organisatie invoeren tijdens OOBE en automatisch registreren bij Azure AD en het apparaat registreren bij MDM.

Met behulp [Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home)kunt u services selecteren en door een paar pagina's navigeren totdat u Een Premium selecteren. Mogelijk ziet u dat er Azure Active Directory Premium 1 en 2 is. Voor Automatische inschrijving is P1 voldoende. We kunnen Intune selecteren, het gebruikersbereik voor automatische inschrijving selecteren en de groep selecteren die eerder is gemaakt.

Lees de handleiding over het inschakelen van automatische inschrijving voor [Intune](/mem/intune/enrollment/quickstart-setup-auto-enrollment)voor meer informatie en stappen.

## <a name="corporate-wi-fi-connectivity"></a>Connectiviteit Wi-Fi bedrijfsnetwerk

Voor Wi-Fi bedrijfsverbindingen is doorgaans verificatie op basis van certificaten vereist voor klanten die HoloLens 2. U moet dergelijke certificaten implementeren met behulp van een Simple Certificate Enrollment Protocol-certificaatinfrastructuur (SCEP) of PKCS-certificaatinfrastructuur (Public Key Cryptography Standard) die is geïntegreerd met uw MDM-oplossing. Het gebruik van Intune Wi-Fi profielen, certificaten en proxy-instellingen zorgt voor een naadloze ervaring voor eindgebruikers.
 
### <a name="deploy-certificates-and-wi-fi-profiles"></a>Certificaten en Wi-Fi implementeren

Als u certificaten en profielen wilt implementeren via Microsoft Endpoint Manager, volgt u deze stappen:

1. Maak een profiel voor elk van de basiscertificaten en tussenliggende certificaten (zie [Vertrouwde certificaatprofielen maken).](/intune/protect/certificates-configure#create-trusted-certificate-profiles) Elk van deze profielen moet een beschrijving hebben met een vervaldatum in DD/MM/YYYY-indeling.

    > [!CAUTION]
    > **Certificaatprofielen zonder een vervaldatum worden niet geïmplementeerd.**

2. Maak een profiel voor elke SCEP- of PKCS-certificaten (zie Een SCEP-certificaatprofiel maken of Een [PKCS-certificaatprofiel](/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)maken ) Elk van deze profielen moet een beschrijving hebben met een vervaldatum in DD/MM/YYYY-indeling.

    > [!CAUTION]
    > **Certificaatprofielen zonder een vervaldatum worden niet geïmplementeerd.**

    > [!Note]
    > Omdat de HoloLens 2 wordt beschouwd als een gedeeld apparaat, dat wil zeggen meerdere gebruikers per apparaat, wordt het aanbevolen waar mogelijk apparaatcertificaten te implementeren in plaats van gebruikerscertificaten voor Wi-Fi verificatie.

3. Maak een profiel voor uw bedrijfsnetwerk Wi-Fi (zie [Wi-Fi-instellingen voor](/intune/wi-fi-settings-windows)Windows 10 en latere apparaten). Binnen uw Wi-Fi kunt u de proxyinstellingen binnen uw organisatie gebruiken.

    Uw opties zijn:
    - **Geen**: Er zijn geen proxyinstellingen geconfigureerd.
    - **Handmatig configureren:** voer het **IP-adres van de proxyserver en** het **poortnummer in.**
    - **Automatisch configureren**: Voer de URL in die naar een proxyscript voor automatische configuratie (PAC) verwijst. Voer bijvoorbeeld *http://proxy.contoso.com/proxy.pac* in.

    Zie [PAC-bestand (Proxy Auto-Configuration)](https://developer.mozilla.org/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_(PAC)_file) (hiermee opent u een niet-Microsoft-site) voor meer informatie over PAC-bestanden.
 
    > [!Note]
    > Het wordt aanbevolen om het Wi-Fi waar mogelijk toe te laten aan Apparaatgroepen in plaats van Gebruikersgroepen.
     
    > [!Tip]
    > U kunt ook een werkprofiel Wi-Fi exporteren vanaf een Windows 10 pc in uw bedrijfsnetwerk. Met deze export maakt u een XML-bestand met alle huidige instellingen. Importeer dit bestand vervolgens in Intune en gebruik het als het Wi-Fi profiel voor uw HoloLens 2 apparaten. Zie [Wi-Fi-instellingen voor Windows-apparaten exporteren en importeren](/mem/intune/configuration/wi-fi-settings-import-windows-8-1).

1.  [Wijs](/mem/intune/configuration/device-profile-assign) de apparaatprofielen toe aan HoloLens apparaatgroep.

2.  [Controleer](/mem/intune/configuration/device-profile-monitor) de apparaatprofielen in Intune.

Als er problemen zijn met Wi-Fi profielen, verwijzen wij u naar [Problemen Wi-Fi apparaatconfiguratieprofielen in Intune oplossen.](/troubleshoot/mem/intune/troubleshoot-wi-fi-profiles)

## <a name="troubleshooting-external-internet-access-when-corp-connected"></a>Problemen met externe internettoegang oplossen wanneer Corp verbonden is
Wanneer services proberen geen proxy te gebruiken, kunnen ze proberen verbinding te maken via de firewall. U kunt een lijst met specifieke eindpunten aan uw firewallregels toevoegen om deze problemen op te lossen.

Als u bent geblokkeerd op firewallpoorten, moet u enkele algemene eindpunten [inschakelen](/hololens/hololens-offline) voor HoloLens.

U kunt ook de gidsen specifieke poorten inschakelen: url's die toegankelijk zijn voor internet die vereist zijn [voor connectiviteit met Microsoft Dynamics CRM Online.](https://support.microsoft.com/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami)

## <a name="app-deployment"></a>App-implementatie

Het implementeren van een LOB-app via MDM is een methode die eenvoudig schaalbaar is en automatisch op uw apparaten kan worden geïmplementeerd bij inschrijving in een gemaakte groep.

Als u nog steeds apps ontwikkelt of nog geen apps hebt, kunt u een voorbeeld-app van de MRTK-voorbeeldenhub gebruiken. Deze voorbeeld-app is klaar voor gebruik en vereist niet het gebruik van Unity of Visual Studio. [Download de mrtk-voorbeeld-app](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App).

Als u liever uw eigen app gebruikt of geïnteresseerd bent in app-ontwikkeling voor Mixed Reality, kunt u onze documentatie voor [Mixed Reality-ontwikkelaars bekijken.](/windows/mixed-reality/design/design)

> [!NOTE]
> De systeemvereisten voor HoloLens zijn gebaseerd op de architectuur van de app-build. HoloLens 2 gebruiken ARM-architectuur. Wanneer u uw apps in Visual Studio, moet u ervoor zorgen dat u de juiste architectuur voor het apparaat hebt geselecteerd en eventuele benodigde afhankelijkheden hebt op te nemen.

> [!IMPORTANT]
> Bij het implementeren van LOB-apps is het belangrijk dat u ook het certificaat uploadt naar Intune en dit toewijst aan dezelfde groep die is bedoeld om de app te gebruiken, anders wordt het certificaat niet goed geïnstalleerd.

### <a name="upload-and-assign-the-app"></a>Upload app installeren en toewijzen

1. Navigeer naar [het MEM-beheercentrum.](https://endpoint.microsoft.com/#home)

2. Selecteer **Apps**  ->  **Alle apps** en selecteer de **knop +** Toevoegen.

3. Selecteer onder Overige de optie **Line-Of-Business-app.** Klik **op selecteren.**

4. Selecteer het app-pakketbestand. Dit is uw APPXBUNDLE-bestand of in ons geval is de app _MRTK Examples Hub \_ 2.4.2.0 \_ arm \_ Master.appxbundle._

5. U krijgt een melding over ontbrekende afhankelijkheden. In dit geval moeten we _Microsoft.VCLibs.ARM.14.00.appx uploaden._ Zoek hier naar onder **Een bestand selecteren.**

6. Selecteer OK.

7. In het volgende scherm worden de vereiste velden automatisch ingevuld. Selecteer **Next**.

8. Voeg onder Vereist de eerder gemaakte groep toe om deze app vereist te maken voor de groep. Hierdoor wordt de app automatisch gedownload naar ingeschreven apparaten in de groep. Selecteer **Next**.

9. Selecteer **Maken**.

Meer informatie: [Apps toewijzen aan groepen in Microsoft Intune](/mem/intune/apps/apps-deploy#assign-an-app)

## <a name="setup-guides-application-licenses-dataverse-and-authoring"></a>Installatiehandleidingen: Toepassingslicenties, gegevensverse en ontwerp

Als u deze Dynamics 365 Guides, moet u enige voorbereidingen treffen. Er zijn drie gebieden waarop we ons moeten voorbereiden: gebruikers, dataverse en de handleidingen zelf.

### <a name="users-and-application-licenses"></a>Gebruikers- en toepassingslicenties

Iemand die Handleidingen kan gebruiken, moet een Azure AD-account gebruiken dat we eerder in deze handleiding hebben ingesteld.

U moet ook een Dynamics 365 Guides toewijzen aan de gebruiker die u hebt gemaakt. U doet dit vanuit de [Microsoft 365-beheercentrum](https://admin.microsoft.com/AdminPortal/Home). Wijs ook de licentie toe aan uw primaire Azure-account.

Volg [deze korte handleiding](/dynamics365/mixed-reality/guides/setup-step-one#assign-the-dynamics-365-guides-license-to-user-accounts) met afbeeldingen voor stapsgewijs instructies voor het toepassen van toepassingslicenties.

### <a name="set-up-the-dataverse"></a>De Dataverse instellen

Als u een [productieomgeving wilt instellen,](/dynamics365/mixed-reality/guides/setup-step-two#set-up-a-production-environment-for-purchased-licenses-only) moet u aan twee vereisten voldoen. U moet [**de rol**](/power-platform/admin/database-security)  Systeembeheerder hebben en u moet een [**Power Apps-licentie**](/power-platform/admin/signup-question-and-answer) (of een [**Dynamics 365 Guides-licentie**](/dynamics365/mixed-reality/guides/setup-step-one) met een Power Apps hebben). Als u deze handleiding volgt die u hebt gemaakt, voldoet u aan de rolvereisten voor systeembeheerder. In de vorige stap hebben we ook een licentie voor gidsen toegewezen.

In deze handleiding voor het [maken van een Microsoft Dataverse-omgeving:](/dynamics365/mixed-reality/guides/setup-step-two)

1. Begin met het gebruik van [Power Platform-beheercentrum](https://admin.powerplatform.microsoft.com/environments) en het maken van een nieuwe omgeving.
2. Wanneer u de **nieuwe omgeving maakt** voor het **type** dat u&#39;selecteert u **Productie**.
3. Is het belangrijk dat u een database voor **deze omgeving maken in-/uitschakelen?**  op **Ja.**
4. Stel in  **het dialoogvenster Database**  toevoegen de optie  **Dynamics 365-apps inschakelen**  in op  **Ja.**

U kunt het beste de maximale bestandsgrootte van items in uw dataverse verhogen. Door de maximale bestandsgrootte te vergroten, kunt u grotere 3D-modellen of videobestanden uploaden die u later in uw handleidingen gaat gebruiken. Volg een korte handleiding om [de maximale grootte van het uploadbestand te wijzigen.](/dynamics365/mixed-reality/guides/setup-step-two#change-the-maximum-upload-file-size)

Ten laatste moet u de oplossing installeren [en configureren.](/dynamics365/mixed-reality/guides/setup-step-two#install-and-configure-the-solution) Selecteer in [Power Platform-beheercentrum](https://admin.powerplatform.microsoft.com/environments)de optie **Resources** \& gt;  **Dynamics 365-apps,** selecteer **Dynamics 365 Guides** in de lijst en selecteer **vervolgens Installeren.**  

U moet [een beveiligingsrol Guides toevoegen](/dynamics365/mixed-reality/guides/assign-role) voordat u de apps kunt gebruiken.

### <a name="create-a-test-guide-on-your-pc-via-authoring"></a>Een testhandleiding op uw pc maken via Ontwerp

Wanneer u Handleidingen maakt, begint u altijd op uw pc. De stappen maken, modellen selecteren en de handleiding ankeren. Dit wordt gevolgd door het plaatsen van inhoud voor uw gids later in de ontwerpmodus op uw HoloLens apparaat. Voor deze handleiding raden we u aan een korte testhandleiding te maken met minimale stappen en modellen.

Als u meer wilt weten over het maken van handleidingen, begint u hier met het [ontwerpoverzicht](/dynamics365/mixed-reality/guides/authoring-overview). Bekijk deze korte video voor een snel overzicht.

<iframe width="560" height="315" src="https://www.youtube.com/embed/EC24dMlAy90" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="optional-kiosk-mode"></a>Optioneel: Kioskmodus

De kioskmodus is een modus waarmee een IT-beheerder de gebruikersinterface van het menu Start kan configureren om slechts één app of een selectie apps weer te geven. Een kiosk kan ook worden toegepast op specifieke gebruikers, groepen of op apparaatniveau; en in sommige gevallen moet u bepaalde gebruikers uitsluiten van de kiosk, zodat ze nog steeds toegang hebben tot het normale menu Start.

De kioskmodus heeft veel verschillende variabelen, zowel in het bereik als in configuraties die kunnen worden ingesteld, evenals methoden voor het implementeren van de kiosk op de HoloLens. Vanwege al deze variabelen wordt de kioskmodus voor deze handleiding optioneel gelaten en komt deze niet meer terug.  Als u van mening bent dat u de beschikbare apps wilt beperken tot gebruikers of meer wilt weten, kunt u hier lezen hoe u HoloLens [als kiosk kunt instellen.](/hololens/hololens-kiosk)

## <a name="optional-wdac"></a>Optioneel: WDAC

Met WDAC kan een IT-beheerder zijn apparaten configureren om het starten van apps op apparaten te blokkeren. Dit verschilt van de apparaatbeperkingsmethoden, zoals de kioskmodus, waarbij de gebruiker een gebruikersinterface krijgt te zien die de apps op het apparaat verbergt, maar die nog steeds kan worden gestart. Terwijl WDAC is geïmplementeerd, zijn de apps nog steeds zichtbaar in de lijst Alle apps, maar WDAC voorkomt dat deze apps en processen kunnen worden gestart door de gebruiker van het apparaat.

Voor meer informatie verwijzen we [naar WDAC](/mem/intune/configuration/custom-profile-hololens)en Windows PowerShell apps toestaan of blokkeren op HoloLens 2 apparaten met Microsoft Intune.

[Windows Defender Toepassingsbeheer - WDAC](/hololens/windows-defender-application-control-wdac)

## <a name="next-step"></a>Volgende stap 
> [!div class="nextstepaction"]
> [Zakelijke verbonden implementatie - Implementeren](hololens2-corp-connected-deploy.md)