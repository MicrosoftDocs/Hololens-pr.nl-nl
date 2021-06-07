---
title: Certificaatbeheerder
description: Meer informatie over het handmatig installeren, beheren en verwijderen van certificaten op HoloLens 2 mixed reality apparaten.
author: evmill
ms.author: v-evmill
manager: yannisle
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/13/2020
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: f9dcf98cbd200ac54cd786648fdfe286bff1aa00
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/25/2021
ms.locfileid: "111377804"
---
# <a name="certificate-manager"></a><span data-ttu-id="39049-103">Certificaatbeheerder</span><span class="sxs-lookup"><span data-stu-id="39049-103">Certificate Manager</span></span>

- <span data-ttu-id="39049-104">Verbeterde hulpprogramma's voor controle, diagnose en validatie voor apparaatbeveiliging en -naleving via de nieuwe Certificaatbeheerder.</span><span class="sxs-lookup"><span data-stu-id="39049-104">Improved auditing, diagnosis, and validation tooling for device security and compliance through the new Certificate Manager.</span></span> <span data-ttu-id="39049-105">Met deze mogelijkheid kunt u uw certificaten op schaal implementeren, oplossen en valideren in commerciële omgevingen.</span><span class="sxs-lookup"><span data-stu-id="39049-105">This capability will enable you to deploy, troubleshoot, and validate your certificates at scale in commercial environments.</span></span>

<span data-ttu-id="39049-106">In Windows Holographic, versie 20H2, voegen we certificaatbeheer toe aan de app HoloLens 2 Instellingen.</span><span class="sxs-lookup"><span data-stu-id="39049-106">In Windows Holographic, version 20H2, we are adding a Certificate Manager in the HoloLens 2 Settings app.</span></span> <span data-ttu-id="39049-107">Ga naar **Instellingen > Beveiliging & bijwerken > certificaten.**</span><span class="sxs-lookup"><span data-stu-id="39049-107">Go to **Settings > Update & Security > Certificates**.</span></span> <span data-ttu-id="39049-108">Deze functie biedt een eenvoudige en gebruiksvriendelijke manier om certificaten op uw apparaat weer te geven, te installeren en te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="39049-108">This feature provides a simple and user-friendly way to view, install and remove certificates on your device.</span></span> <span data-ttu-id="39049-109">Met de nieuwe Certificate Manager hebben beheerders en gebruikers nu verbeterde hulpprogramma's voor controle, diagnose en validatie om ervoor te zorgen dat apparaten veilig en compatibel blijven.</span><span class="sxs-lookup"><span data-stu-id="39049-109">With the new Certificate Manager, admins and users now have improved auditing, diagnosis and validation tooling to ensure that devices remain secure and compliant.</span></span> 

-   <span data-ttu-id="39049-110">**Controle:** Mogelijkheid om te valideren dat een certificaat correct is geïmplementeerd of om te bevestigen dat het op de juiste wijze is verwijderd.</span><span class="sxs-lookup"><span data-stu-id="39049-110">**Auditing:** Ability to validate that a certificate is deployed correctly or to confirm that it was removed appropriately.</span></span> 
-   <span data-ttu-id="39049-111">**Diagnose:** Wanneer er problemen optreden, bespaart het valideren of de juiste certificaten op het apparaat bestaan tijd en helpt het bij het oplossen van problemen.</span><span class="sxs-lookup"><span data-stu-id="39049-111">**Diagnosis:** When issues arise, validating that the appropriate certificates exist on the device saves time and helps with troubleshooting.</span></span> 
-   <span data-ttu-id="39049-112">**Validatie:** Controleren of een certificaat het beoogde doel heeft en functioneel is, kan aanzienlijke tijd besparen, met name in commerciële omgevingen voordat certificaten op grotere schaal worden geïmplementeerd.</span><span class="sxs-lookup"><span data-stu-id="39049-112">**Validation:** Verifying that a certificate serves the intended purpose and is functional, can save significant time, particularly in commercial environments before deploying certificates at larger scale.</span></span>

<span data-ttu-id="39049-113">Als u snel een specifiek certificaat in de lijst wilt vinden, zijn er opties om te sorteren op naam, winkel of vervaldatum.</span><span class="sxs-lookup"><span data-stu-id="39049-113">To find a specific certificate in the list quickly, there are options to sort by name, store or expiration date.</span></span> <span data-ttu-id="39049-114">Gebruikers kunnen ook rechtstreeks naar een certificaat zoeken.</span><span class="sxs-lookup"><span data-stu-id="39049-114">Users may also directly search for a certificate.</span></span> <span data-ttu-id="39049-115">Als u afzonderlijke certificaateigenschappen wilt weergeven, selecteert u het certificaat en klikt u op **Info.**</span><span class="sxs-lookup"><span data-stu-id="39049-115">To view individual certificate properties, select the certificate and click on **Info**.</span></span> 

<span data-ttu-id="39049-116">Certificaatinstallatie ondersteunt momenteel CER- en CRT-bestanden.</span><span class="sxs-lookup"><span data-stu-id="39049-116">Certificate installation currently supports .cer and .crt files.</span></span> <span data-ttu-id="39049-117">Apparaateigenaren kunnen certificaten installeren op de lokale computer en de huidige gebruiker;  alle andere gebruikers kunnen alleen installeren in Huidige gebruiker.</span><span class="sxs-lookup"><span data-stu-id="39049-117">Device Owners can install certificates in Local Machine and Current User;  all other users can only install into Current User.</span></span> <span data-ttu-id="39049-118">Gebruikers kunnen alleen certificaten verwijderen die rechtstreeks vanuit de gebruikersinterface Instellingen zijn geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="39049-118">Users can only remove certificates installed directly from the Settings UI.</span></span> <span data-ttu-id="39049-119">Als een certificaat op een andere manier is geïnstalleerd, moet het ook door hetzelfde mechanisme worden verwijderd.</span><span class="sxs-lookup"><span data-stu-id="39049-119">If a certificate has been installed through other means, it must also be removed by the same mechanism.</span></span>

## <a name="to-install-a-certificate"></a><span data-ttu-id="39049-120">Een certificaat installeren:</span><span class="sxs-lookup"><span data-stu-id="39049-120">To install a certificate:</span></span> 

1.  <span data-ttu-id="39049-121">Verbind uw HoloLens 2 met een pc.</span><span class="sxs-lookup"><span data-stu-id="39049-121">Connect your HoloLens 2 to a PC.</span></span>
1.  <span data-ttu-id="39049-122">Plaats het certificaatbestand dat u wilt installeren op een locatie op HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="39049-122">Place the certificate file you want to install in a location on your HoloLens 2.</span></span>
1.  <span data-ttu-id="39049-123">**Navigeer naar Instellingen App > Update & Security > Certificates** en selecteer Install a certificate.</span><span class="sxs-lookup"><span data-stu-id="39049-123">Navigate to **Settings App > Update & Security > Certificates**, and select Install a certificate.</span></span>
1.  <span data-ttu-id="39049-124">Klik **op Bestand importeren** en navigeer naar de locatie waar u het certificaat hebt opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="39049-124">Click **Import File** and navigate to the location you saved the certificate.</span></span>
1.  <span data-ttu-id="39049-125">Selecteer **Winkellocatie.**</span><span class="sxs-lookup"><span data-stu-id="39049-125">Select **Store Location**.</span></span>
1.  <span data-ttu-id="39049-126">Selecteer **Certificaatopslag.**</span><span class="sxs-lookup"><span data-stu-id="39049-126">Select **Certificate Store**.</span></span>
1.  <span data-ttu-id="39049-127">Klik op **Installeren**.</span><span class="sxs-lookup"><span data-stu-id="39049-127">Click **Install**.</span></span>

<span data-ttu-id="39049-128">Het certificaat moet nu op het apparaat zijn geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="39049-128">The certificate should now be installed on the device.</span></span>

## <a name="to-remove-a-certificate"></a><span data-ttu-id="39049-129">Een certificaat verwijderen:</span><span class="sxs-lookup"><span data-stu-id="39049-129">To remove a certificate:</span></span> 
>[!WARNING]
> <span data-ttu-id="39049-130">Hoewel u door MDM geïmplementeerde certificaten kunt weergeven in Certificate Manager, kunt u ze niet verwijderen in Certificate Manager.</span><span class="sxs-lookup"><span data-stu-id="39049-130">Although you can view MDM-deployed certificates in Certificate Manager, you cannot uninstall them in Certificate Manager.</span></span> <span data-ttu-id="39049-131">U moet ze verwijderen via MDM.</span><span class="sxs-lookup"><span data-stu-id="39049-131">You must uninstall them through MDM.</span></span>
1. <span data-ttu-id="39049-132">**Navigeer naar Instellingen-app > Bijwerken en beveiliging > certificaten.**</span><span class="sxs-lookup"><span data-stu-id="39049-132">Navigate to **Settings App > Update and Security > Certificates**.</span></span>
1. <span data-ttu-id="39049-133">Zoek het certificaat op naam in het zoekvak.</span><span class="sxs-lookup"><span data-stu-id="39049-133">Search for the certificate by name in the search box.</span></span>
1. <span data-ttu-id="39049-134">Selecteer het certificaat.</span><span class="sxs-lookup"><span data-stu-id="39049-134">Select the certificate.</span></span>
1. <span data-ttu-id="39049-135">Klik op **Verwijderen**</span><span class="sxs-lookup"><span data-stu-id="39049-135">Click **Remove**</span></span>
1. <span data-ttu-id="39049-136">Selecteer **Ja wanneer** u om bevestiging wordt gevraagd.</span><span class="sxs-lookup"><span data-stu-id="39049-136">Select **Yes** when prompted for confirmation.</span></span>



![Certificaatviewer in de app Instellingen onder Certificaten](images/certificate-viewer-device.jpg)

![Afbeelding waarin wordt getoond hoe u de gebruikersinterface van het certificaat gebruikt om een certificaat te installeren in Instellingen.](images/certificate-device-install.jpg)
