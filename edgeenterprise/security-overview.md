---
title: Panoramica della sicurezza di Microsoft Edge
ms.author: srugh
author: srugh
manager: seanlyn
ms.date: 04/29/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Panoramica della distribuzione della sicurezza di Microsoft Edge
ms.openlocfilehash: f22f2dcbace00cd535d201950c2af488c708525b
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980306"
---
# <span data-ttu-id="a095f-103">Panoramica della sicurezza di Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="a095f-103">Overview of Microsoft Edge security</span></span>
  
<span data-ttu-id="a095f-104">Gli amministratori IT aziendali si trovano costantemente di fronte a una miriade di problemi di sicurezza esistenti ed emergenti, proteggendo nel contempo la rete aziendale e i dispositivi da attacchi dannosi e impedendo l'accesso non autorizzato e le perdite di dati aziendali.</span><span class="sxs-lookup"><span data-stu-id="a095f-104">IT admins in the enterprise are constantly facing a myriad of existing and emerging security challenges while protecting the corporate network and devices from malicious attacks and preventing unauthorized access and leaks of corporate data.</span></span> <span data-ttu-id="a095f-105">Microsoft Edge offre diverse funzionalità univoche create in modo nativo che consentono di risolvere queste problematiche.</span><span class="sxs-lookup"><span data-stu-id="a095f-105">Microsoft Edge provides several natively built, unique capabilities that help address these challenges.</span></span>

> [!NOTE]
> <span data-ttu-id="a095f-106">Questo articolo si applica a Microsoft Edge, versione 77 o successiva.</span><span class="sxs-lookup"><span data-stu-id="a095f-106">This article applies to Microsoft Edge version 77 or later.</span></span>

## <span data-ttu-id="a095f-107">Accesso condizionale</span><span class="sxs-lookup"><span data-stu-id="a095f-107">Conditional Access</span></span>

<span data-ttu-id="a095f-108">Un aspetto fondamentale della sicurezza del cloud è il controllo delle identità e dell'accesso in relazione alla gestione delle risorse cloud.</span><span class="sxs-lookup"><span data-stu-id="a095f-108">A key aspect of cloud security is identity and access when it comes to managing your cloud resources.</span></span> <span data-ttu-id="a095f-109">In un ambiente orientato alla mobilità e al cloud, gli utenti possono accedere alle risorse dell'organizzazione usando un'ampia gamma di dispositivi e app praticamente ovunque.</span><span class="sxs-lookup"><span data-stu-id="a095f-109">In a mobile-first, cloud-first world, users can access your organization's resources using a variety of devices and apps from anywhere.</span></span> <span data-ttu-id="a095f-110">Di conseguenza, concentrarsi solo su chi può accedere a una risorsa non è sufficiente.</span><span class="sxs-lookup"><span data-stu-id="a095f-110">As a result of this, just focusing on who can access a resource is not sufficient.</span></span> <span data-ttu-id="a095f-111">Devi anche esaminare la modalità di accesso a una risorsa.</span><span class="sxs-lookup"><span data-stu-id="a095f-111">You also need to factor in how a resource is accessed.</span></span> <span data-ttu-id="a095f-112">L'accesso condizionale di Azure Active Directory (Azure AD) consente di bilanciare la sicurezza e la produttività.</span><span class="sxs-lookup"><span data-stu-id="a095f-112">Azure Active Directory (Azure AD) Conditional Access helps you master the balance between security and productivity.</span></span>

### <span data-ttu-id="a095f-113">Accesso alle risorse protette con accesso condizionale in Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="a095f-113">Accessing Conditional Access protected resources in Microsoft Edge</span></span>

<span data-ttu-id="a095f-114">Microsoft Edge supporta in modo nativo l'accesso condizionale di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="a095f-114">Microsoft Edge natively supports Azure AD Conditional Access.</span></span> <span data-ttu-id="a095f-115">Non è necessario installare un'estensione separata.</span><span class="sxs-lookup"><span data-stu-id="a095f-115">There's no need to install a separate extension.</span></span> <span data-ttu-id="a095f-116">Quando si accede a un profilo Microsoft Edge con le credenziali Azure AD aziendali, Microsoft Edge consente di accedere in modo semplice alle risorse cloud aziendali protette con l'accesso condizionale.</span><span class="sxs-lookup"><span data-stu-id="a095f-116">When you're signed into a Microsoft Edge profile with enterprise Azure AD credentials, Microsoft Edge allows seamless access to enterprise cloud resources protected using Conditional Access.</span></span>

<span data-ttu-id="a095f-117">In un dispositivo conforme, l'identità che accede alla risorsa deve corrispondere all'identità del profilo.</span><span class="sxs-lookup"><span data-stu-id="a095f-117">On a compliant device, the identity accessing the resource should match the identity on the profile.</span></span>  <span data-ttu-id="a095f-118">In caso contrario, viene visualizzato un messaggio come quello nella schermata successiva.</span><span class="sxs-lookup"><span data-stu-id="a095f-118">If it doesn't, you'll see a message like the one in the next screenshot.</span></span> <span data-ttu-id="a095f-119">Nella schermata di esempio, "testadmin@evostsoneboxtest.com" è l'account di accesso necessario per accedere alla risorsa.</span><span class="sxs-lookup"><span data-stu-id="a095f-119">In the screenshot example, "testadmin@evostsoneboxtest.com" is the sign-in account needed to access the resource.</span></span>

![Messaggio di accesso condizionale nel browser](./media/edge-security/microsoft-edge-security-conditional-access.png)

<span data-ttu-id="a095f-121">Per continuare, devi passare al profilo richiesto (se ne hai uno) o creare un profilo con identità corrispondente.</span><span class="sxs-lookup"><span data-stu-id="a095f-121">To continue, you have to switch to the required profile (if you have one) or create a profile with matching identity.</span></span>

<span data-ttu-id="a095f-122">Per accedere e usare il tuo profilo, fai clic sull'immagine dell'account nell'angolo superiore destro del browser.</span><span class="sxs-lookup"><span data-stu-id="a095f-122">To sign in and work with your profile, click the account picture in the top right corner of the browser.</span></span> <span data-ttu-id="a095f-123">Puoi usare il menu a discesa per:</span><span class="sxs-lookup"><span data-stu-id="a095f-123">You can use the dropdown menu to:</span></span>

- <span data-ttu-id="a095f-124">Selezionare un altro profilo</span><span class="sxs-lookup"><span data-stu-id="a095f-124">Select another profile.</span></span> <span data-ttu-id="a095f-125">Fare clic sul nome del profilo.</span><span class="sxs-lookup"><span data-stu-id="a095f-125">Click the profile name.</span></span>
- <span data-ttu-id="a095f-126">Creare un profilo.</span><span class="sxs-lookup"><span data-stu-id="a095f-126">Create a profile.</span></span> <span data-ttu-id="a095f-127">Fai clic su **Aggiungi un profilo**.</span><span class="sxs-lookup"><span data-stu-id="a095f-127">Click **Add a profile**.</span></span>
- <span data-ttu-id="a095f-128">Gestire i tuoi profili.</span><span class="sxs-lookup"><span data-stu-id="a095f-128">Manage your profiles.</span></span> <span data-ttu-id="a095f-129">Fai clic su **Gestisci impostazioni del profilo**.</span><span class="sxs-lookup"><span data-stu-id="a095f-129">Click **Manage profile settings**.</span></span>

<span data-ttu-id="a095f-130">Questo supporto è disponibile in tutte le piattaforme, incluse tutte le versioni supportate di Windows e macOS.</span><span class="sxs-lookup"><span data-stu-id="a095f-130">This support is available across all platforms, including all supported versions of Windows and macOS.</span></span>

### <span data-ttu-id="a095f-131">Come distribuire l'accesso condizionale in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="a095f-131">How to deploy Conditional Access in Azure Active Directory</span></span>

<span data-ttu-id="a095f-132">L'articolo [Distribuire l'accesso condizionale](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) fornisce una guida dettagliata per distribuire l'accesso condizionale in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a095f-132">[Deploy Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) provides a detailed guide to help deploy Conditional Access in Azure Active Directory.</span></span>

## <span data-ttu-id="a095f-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a095f-133">See also</span></span>

- [<span data-ttu-id="a095f-134">Pagina di destinazione di Microsoft Edge in modalità Enterprise</span><span class="sxs-lookup"><span data-stu-id="a095f-134">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="a095f-135">Video: sicurezza, compatibilità e gestibilità</span><span class="sxs-lookup"><span data-stu-id="a095f-135">Video: Security, compatibility, and manageability</span></span>](/microsoft-edge-video-security-compatibility-manageability.md)
