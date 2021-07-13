---
title: Globale toegewezen toegang
description: Ga aan de slag met onze handleiding voor het gebruik van OMA-URI voor globale kiosken voor toegewezen toegang met Intune en Windows Configuration Designer.
author: evmill
ms.author: v-evmill
ms.date: 9/21/2020
ms.topic: article
keywords: hololens, hololens 2, toegewezen toegang, kiosk
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: lavinds
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: d89c630da76060fe6c2a049e5fa162e88779bb99
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640420"
---
# <a name="global-assigned-access--kiosk"></a><span data-ttu-id="a5c34-104">Globale toegewezen toegang – Kiosk</span><span class="sxs-lookup"><span data-stu-id="a5c34-104">Global Assigned Access – Kiosk</span></span>

<span data-ttu-id="a5c34-105">Deze functie configureert HoloLens 2 apparaat voor de kioskmodus voor meerdere apps, die van toepassing is op systeemniveau, heeft geen affiniteit met een identiteit op het systeem en is van toepassing op iedereen die zich bij het apparaat meldt.</span><span class="sxs-lookup"><span data-stu-id="a5c34-105">This feature configures HoloLens 2 device for multiple app kiosk mode, which is applicable at system level, has no affinity with any identity on the system and applies to everyone who signs into the device.</span></span>

> [!NOTE]
> <span data-ttu-id="a5c34-106">Deze functie is momenteel alleen beschikbaar in Windows Insider-builds.</span><span class="sxs-lookup"><span data-stu-id="a5c34-106">This feature is currently only available in Windows Insider builds.</span></span> <span data-ttu-id="a5c34-107">Als u deze functie wilt uitproberen voordat deze algemeen beschikbaar is in HoloLens releases, leest u meer over Windows [Insider-builds.](hololens-insider.md)</span><span class="sxs-lookup"><span data-stu-id="a5c34-107">If you would like to try this feature before it is generally available in HoloLens releases please read more about [Windows Insider](hololens-insider.md) builds.</span></span>

## <a name="how-to-use-global-assigned-access-in-intune"></a><span data-ttu-id="a5c34-108">Hoe kan ik globale toegewezen toegang gebruiken in Intune?</span><span class="sxs-lookup"><span data-stu-id="a5c34-108">How to use Global Assigned Access in Intune?</span></span>

> [!NOTE]
> <span data-ttu-id="a5c34-109">Houd rekening met de gebieden die zijn gemarkeerd met '<!-'.</span><span class="sxs-lookup"><span data-stu-id="a5c34-109">Please be aware of the areas marked with "<!-".</span></span> <span data-ttu-id="a5c34-110">Voor deze gebieden moet u wijzigingen aanbrengen op basis van uw voorkeuren.</span><span class="sxs-lookup"><span data-stu-id="a5c34-110">These areas will require you to make modifications based on your preferences.</span></span>

1. <span data-ttu-id="a5c34-111">Maak als volgt een aangepast OMA URI-apparaatconfiguratieprofiel en pas dit toe op HoloLens apparaatgroep:</span><span class="sxs-lookup"><span data-stu-id="a5c34-111">Create a custom OMA URI device configuration profile as follows and apply it to HoloLens device group:</span></span>

    <span data-ttu-id="a5c34-112">URI-waarde: ./Device/Vendor/MSFT/AssignedAccess/Configuration</span><span class="sxs-lookup"><span data-stu-id="a5c34-112">URI value: ./Device/Vendor/MSFT/AssignedAccess/Configuration</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="a5c34-113">![OMA-URI voor globale toegewezen toegang in Intune](images/global-assigned-access-omauri.png)</span><span class="sxs-lookup"><span data-stu-id="a5c34-113">![Global Assigned Access OMA-URI in Intune](images/global-assigned-access-omauri.png)</span></span>

2. <span data-ttu-id="a5c34-114">Werk voor waarde de volgende inhoud bij en plak deze:</span><span class="sxs-lookup"><span data-stu-id="a5c34-114">For value, update and paste following content:</span></span>

    :::code language="xml" source="samples/global-assigned-access.xml" highlight="12-13,23":::

## <a name="how-to-use-global-assigned-access-in-windows-configuration-designer"></a><span data-ttu-id="a5c34-115">Globale toegewezen toegang gebruiken in Windows Configuration Designer?</span><span class="sxs-lookup"><span data-stu-id="a5c34-115">How to use Global Assigned Access in Windows Configuration Designer?</span></span>

1. <span data-ttu-id="a5c34-116">Werk de HIERBOVEN genoemde XML-blob bij en sla deze op als XML-bestand.</span><span class="sxs-lookup"><span data-stu-id="a5c34-116">Update and save XML blob mentioned above as XML file.</span></span> 

2. <span data-ttu-id="a5c34-117">Volg de stappen in [Een inrichtingspakket gebruiken om](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)een kiosk voor één app of meerdere apps in te stellen, met name de sectie Prov.</span><span class="sxs-lookup"><span data-stu-id="a5c34-117">Follow the steps in [Use a provisioning package to set up a single-app or multi-app kiosk](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk), specifically the section "Prov.</span></span> <span data-ttu-id="a5c34-118">package, step 2– Add the kiosk configuration XML file to a provisioning package' (pakket, stap 2: het XML-bestand voor de kioskconfiguratie toevoegen aan een inrichtingspakket) en verwijzen naar het XML-bestand dat in de vorige stap is opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="a5c34-118">package, step 2 – Add the kiosk configuration XML file to a provisioning package" and refer to the XML file that was saved in the previous step.</span></span>

## <a name="can-i-create-a-configuration-where-global-applies-to-everyone-and-separate-configuration-applies-to-1-azure-ad-account-or-azure-ad-group"></a><span data-ttu-id="a5c34-119">Kan ik een configuratie maken waarbij globaal van toepassing is op iedereen en afzonderlijke configuratie van toepassing is op 1 Azure AD-account of Azure AD-groep?</span><span class="sxs-lookup"><span data-stu-id="a5c34-119">Can I create a configuration where global applies to everyone and separate configuration applies to 1 Azure AD account or Azure AD group?</span></span> 

<span data-ttu-id="a5c34-120">Ja, raadpleeg de voorbeeld-XML-blob hieronder.</span><span class="sxs-lookup"><span data-stu-id="a5c34-120">Yes, refer to the example XML blob below.</span></span> <span data-ttu-id="a5c34-121">Het profiel Voor globale toegewezen toegang wordt toegepast op HoloLens wanneer er geen specifiek profiel voor de aangemelde gebruiker wordt gevonden. Dit is dus de standaardconfiguratie voor de kioskmodus voor de aangemelde gebruiker.</span><span class="sxs-lookup"><span data-stu-id="a5c34-121">Global Assigned Access profile is applied on HoloLens when a specific one for the signed in user is not found, so it is default kiosk mode configuration for signed-in user.</span></span>
<span data-ttu-id="a5c34-122">Hier volgt een voorbeeld van een XML-blob die moet worden gebruikt:</span><span class="sxs-lookup"><span data-stu-id="a5c34-122">Here is an example of XML blob to be used:</span></span>

> [!NOTE]
> <span data-ttu-id="a5c34-123">Houd rekening met de gemarkeerde gebieden die zijn gemarkeerd met `<!-` .</span><span class="sxs-lookup"><span data-stu-id="a5c34-123">Please be aware of the highlighted areas marked with `<!-`.</span></span> <span data-ttu-id="a5c34-124">Voor deze gebieden moet u wijzigingen aanbrengen op basis van uw voorkeuren.</span><span class="sxs-lookup"><span data-stu-id="a5c34-124">These areas will require you to make modifications based on your preferences.</span></span>

 :::code language="xml" source="samples/exclude-one-aad-user-or-group.xml" highlight="8,11,17":::

## <a name="excluding-deviceowners-from-global-assigned-access-profile"></a><span data-ttu-id="a5c34-125">DeviceOwners uitsluiten van algemeen toegewezen toegangsprofiel</span><span class="sxs-lookup"><span data-stu-id="a5c34-125">Excluding DeviceOwners from Global Assigned Access Profile</span></span>

<span data-ttu-id="a5c34-126">Met deze functie kan een[](security-adminless-os.md)gebruiker die wordt beschouwd als 'Apparaateigenaar' op HoloLens worden uitgesloten van globale toegewezen toegang.</span><span class="sxs-lookup"><span data-stu-id="a5c34-126">This feature allows a user who is considered “[Device owner](security-adminless-os.md)" on HoloLens to be excluded from Global Assigned Access.</span></span> <span data-ttu-id="a5c34-127">Als u wilt profiteren van deze functie, moet u in de XML-blob voor de kioskconfiguratie voor meerdere apps ervoor zorgen dat er gemarkeerde regels worden toegevoegd:</span><span class="sxs-lookup"><span data-stu-id="a5c34-127">In order to take advantage of this feature, in the XML blob for multiple-app kiosk configuration, ensure highlighted lines are added:</span></span>

 :::code language="xml" source="samples/exclude-device-owners-from-global.xml" highlight="6,16-18":::

## <a name="additional-global-assigned-access-examples"></a><span data-ttu-id="a5c34-128">Aanvullende voorbeelden van globale toegewezen toegang</span><span class="sxs-lookup"><span data-stu-id="a5c34-128">Additional Global Assigned Access Examples</span></span>

<span data-ttu-id="a5c34-129">Dit is een voorbeeld van een kiosk voor globale toegewezen toegang die wanneer een gebruiker zich aan meldt, een kiosk voor meerdere apps heeft met de Instellingen App, Feedback-hub en Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="a5c34-129">This is an example Global Assigned Access kiosk that when any user signs in they will have a multi-app kiosk with the Settings App, Feedback Hub, and Microsoft Edge.</span></span>

:::code language="xml" source="samples/kiosk-sample-global-assigned-access.xml":::

<span data-ttu-id="a5c34-130">Dit voorbeeld is een kiosk voor globale toegewezen toegang die de eigenaar van het apparaat uitsluit, wanneer andere Azure AD-gebruikers zich kunnen aan- en uittekenen, een kiosk voor meerdere apps hebben met de Instellingen-app, Feedback-hub en Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="a5c34-130">This example is a Global Assigned Access kiosk that excludes the device owner, when any other Azure AD user signs in they will have a multi-app kiosk with the Settings App, Feedback Hub, and Microsoft Edge.</span></span> <span data-ttu-id="a5c34-131">Deze kiosk bevat ook een secundaire kioskconfiguratie voor een bezoekersaccount, die door iedereen kan worden aangemeld op het vergrendelingsscherm.</span><span class="sxs-lookup"><span data-stu-id="a5c34-131">This kiosk also includes a secondary kiosk configuration for a Visitor account, which may be signed into by anyone on the lock screen.</span></span> <span data-ttu-id="a5c34-132">Wanneer een gebruiker zich bij het bezoekersaccount meldt, heeft deze een kiosk voor meerdere apps die alleen de Feedback-hub app.</span><span class="sxs-lookup"><span data-stu-id="a5c34-132">When a user signs into the Visitor account they will have a multi-app kiosk that only has the Feedback Hub app.</span></span>

:::code language="xml" source="samples/kiosk-sample-global-assigned-access-visitor-exclude.xml":::
