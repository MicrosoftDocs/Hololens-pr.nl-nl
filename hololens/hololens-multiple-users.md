---
title: Uw HoloLens delen met meerdere personen
description: U kunt HoloLens configureren om te worden gedeeld door meerdere Azure Active Directory-accounts of door meerdere gebruikers die één account gebruiken.
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 09/16/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 39de72bb704ff500b0262f2268d003a08d520eb2
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/19/2021
ms.locfileid: "111377883"
---
# <a name="share-your-hololens-with-multiple-people"></a><span data-ttu-id="22cee-103">Uw HoloLens delen met meerdere personen</span><span class="sxs-lookup"><span data-stu-id="22cee-103">Share your HoloLens with multiple people</span></span>

<span data-ttu-id="22cee-104">Het is gebruikelijk om één HoloLens te delen met veel mensen of om veel mensen een set HoloLens-apparaten te laten delen.</span><span class="sxs-lookup"><span data-stu-id="22cee-104">It's common to share one HoloLens with many people or to have many people share a set of HoloLens devices.</span></span>  <span data-ttu-id="22cee-105">In dit artikel worden de verschillende manieren beschreven waarop u een apparaat kunt delen.</span><span class="sxs-lookup"><span data-stu-id="22cee-105">This article describes the different ways in which you can share a device.</span></span>

## <a name="share-with-multiple-people-each-using-their-own-account"></a><span data-ttu-id="22cee-106">Delen met meerdere personen, elk met hun eigen account</span><span class="sxs-lookup"><span data-stu-id="22cee-106">Share with multiple people, each using their own account</span></span>

<span data-ttu-id="22cee-107">**Vereiste:** op het HoloLens-apparaat moet Windows 10 versie 1803 of hoger worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="22cee-107">**Prerequisite**: The HoloLens device must be running Windows 10, version 1803 or later.</span></span>  <span data-ttu-id="22cee-108">HoloLens (1e generatie) moet ook worden bijgewerkt naar [Windows Holographic for Business.](hololens-upgrade-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="22cee-108">HoloLens (1st gen) also need to be [upgraded to Windows Holographic for Business](hololens-upgrade-enterprise.md).</span></span>

<span data-ttu-id="22cee-109">Wanneer ze hun eigen Azure AD Azure Active Directory accounts gebruiken, kunnen meerdere gebruikers elk hun eigen gebruikersinstellingen en gebruikersgegevens op het apparaat bewaren.</span><span class="sxs-lookup"><span data-stu-id="22cee-109">When they use their own Azure Active Directory (Azure AD) accounts, multiple users can each keep their own user settings and user data on the device.</span></span>

<span data-ttu-id="22cee-110">Volg deze stappen om deze te configureren om ervoor te zorgen dat meerdere personen hun eigen accounts op uw HoloLens kunnen gebruiken:</span><span class="sxs-lookup"><span data-stu-id="22cee-110">To make sure that multiple people can use their own accounts on your HoloLens, follow these steps to configure it:</span></span>

1. <span data-ttu-id="22cee-111">Zorg ervoor dat op het apparaat Windows 10 versie 1803 of hoger wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="22cee-111">Make sure the the device is running Windows 10, version 1803 or later.</span></span>
   > [!IMPORTANT]
   > <span data-ttu-id="22cee-112">Als u een HoloLens-apparaat (1e generatie) gebruikt, moet u het [apparaat upgraden naar Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="22cee-112">If you are using a HoloLens (1st gen) device, [upgrade the device to Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span></span>
1. <span data-ttu-id="22cee-113">Wanneer u het apparaat in stelt, selecteert u Mijn werk of **school is** eigenaar en meldt u zich aan met een Azure AD-account.</span><span class="sxs-lookup"><span data-stu-id="22cee-113">When you set up the device, select **My work or school owns it** and sign in by using an Azure AD account.</span></span>
1. <span data-ttu-id="22cee-114">Nadat u de installatie hebt voltooien,moet u ervoor zorgen dat de accountinstellingen  >  **(Instellingenaccounts)** **Andere gebruikers bevat.**</span><span class="sxs-lookup"><span data-stu-id="22cee-114">After you finish setup, make sure that the account settings (**Settings** > **Accounts**) includes **Other users**.</span></span>

<span data-ttu-id="22cee-115">Als u HoloLens wilt gebruiken, volgt elke gebruiker deze stappen:</span><span class="sxs-lookup"><span data-stu-id="22cee-115">To use HoloLens, each user follows these steps:</span></span>

1. <span data-ttu-id="22cee-116">Als een andere gebruiker het apparaat heeft gebruikt, doet u het volgende:</span><span class="sxs-lookup"><span data-stu-id="22cee-116">If another user has been using the device, do one of the following:</span></span>
   - <span data-ttu-id="22cee-117">Druk eenmaal op de aan/uit-knop om naar de stand-by te gaan en druk vervolgens nogmaals op de aan/uit-knop om terug te keren naar het vergrendelingsscherm</span><span class="sxs-lookup"><span data-stu-id="22cee-117">Press the power button once to go to standby, and then press the power button again to return to the lock screen</span></span>
   - <span data-ttu-id="22cee-118">HoloLens 2 gebruikers kunnen de tegel Gebruiker selecteren in de Startmenu de huidige gebruiker af te melden.</span><span class="sxs-lookup"><span data-stu-id="22cee-118">HoloLens 2 users may select the user tile from the Start menu to sign out the current user.</span></span>

1. <span data-ttu-id="22cee-119">Gebruik de referenties van uw Azure AD-account om u aan te melden bij het apparaat.</span><span class="sxs-lookup"><span data-stu-id="22cee-119">Use your Azure AD account credentials to sign in to the device.</span></span>  
    <span data-ttu-id="22cee-120">Als dit de eerste keer is dat u [](hololens-calibration.md) het apparaat gebruikt, moet u HoloLens naar uw eigen ogen kalibreren.</span><span class="sxs-lookup"><span data-stu-id="22cee-120">If this is the first time that you have used the device, you have to [calibrate](hololens-calibration.md) HoloLens to your own eyes.</span></span>

<span data-ttu-id="22cee-121">Als u een lijst met de apparaatgebruikers wilt zien of als u een gebruiker van het apparaat wilt verwijderen, gaat u naar  >  **InstellingenAccounts**  >  **Andere gebruikers.**</span><span class="sxs-lookup"><span data-stu-id="22cee-121">To see a list of the device users or to remove a user from the device, go to **Settings** > **Accounts** > **Other users**.</span></span>

## <a name="share-with-multiple-people-all-using-the-same-account"></a><span data-ttu-id="22cee-122">Delen met meerdere personen, allemaal met hetzelfde account</span><span class="sxs-lookup"><span data-stu-id="22cee-122">Share with multiple people, all using the same account</span></span>

<span data-ttu-id="22cee-123">Meerdere gebruikers kunnen ook een HoloLens-apparaat delen terwijl ze één gebruikersaccount gebruiken.</span><span class="sxs-lookup"><span data-stu-id="22cee-123">Multiple users can also share a HoloLens device while using a single user account.</span></span>

<span data-ttu-id="22cee-124">**Wanneer HoloLens 2** nieuwe gebruiker het apparaat de eerste keer op het hoofd plaatst (terwijl hetzelfde account blijft aangemeld), wordt de nieuwe gebruiker gevraagd om de weergave-ervaring snel te kalibreren en aan te persoonlijke voorkeur.</span><span class="sxs-lookup"><span data-stu-id="22cee-124">**On HoloLens 2**, when a new user puts the device on their head for the first time (while keeping the same account signed in), the device prompts the new user to quickly calibrate and personalize the viewing experience.</span></span> <span data-ttu-id="22cee-125">Het apparaat kan de kalibratiegegevens opslaan zodat het apparaat in de toekomst automatisch de kwaliteit en het comfort van de kijkervaring van elke gebruiker kan optimaliseren.</span><span class="sxs-lookup"><span data-stu-id="22cee-125">The device can store the calibration information so that in the future, the device can automatically optimize the quality and comfort of each user's viewing experience.</span></span> <span data-ttu-id="22cee-126">De gebruikers hoeven het apparaat niet opnieuw te kalibreren.</span><span class="sxs-lookup"><span data-stu-id="22cee-126">The users do not need to calibrate the device again.</span></span>

<span data-ttu-id="22cee-127">**Op HoloLens (1e generatie)** moeten gebruikers die een account delen, vragen om opnieuw te worden gecalibreerd in de app Instellingen.</span><span class="sxs-lookup"><span data-stu-id="22cee-127">**On HoloLens (1st gen)** users sharing an account will need to ask to recalibrate in the Settings app.</span></span>  <span data-ttu-id="22cee-128">Lees meer over [kalibratie](hololens-calibration.md).</span><span class="sxs-lookup"><span data-stu-id="22cee-128">Read more about [calibration](hololens-calibration.md).</span></span>
