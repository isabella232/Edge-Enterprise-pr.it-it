---
title: Microsoft Edge e Accesso condizionale
ms.author: srugh
author: srugh
manager: seanlyn
ms.date: 10/02/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge e Accesso condizionale
ms.openlocfilehash: a81d39c15f418dab6565ee7acc45de17f66e3828
ms.sourcegitcommit: 3478cfcf2b03944213a7c7c61f05490bc37aa7c4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/03/2020
ms.locfileid: "11094775"
---
# <span data-ttu-id="56a07-103">Microsoft Edge e Accesso condizionale</span><span class="sxs-lookup"><span data-stu-id="56a07-103">Microsoft Edge and Conditional Access</span></span>
  
<span data-ttu-id="56a07-104">Questo articolo descrive in che modo Microsoft Edge supporta l'accesso condizionale e come accedere alle risorse protette dall'accesso condizionale.</span><span class="sxs-lookup"><span data-stu-id="56a07-104">This article describes how Microsoft Edge supports Conditional Access, and how to access resources protected by Conditional Access.</span></span>

> [!NOTE]
> <span data-ttu-id="56a07-105">Questo articolo si applica a Microsoft Edge versione 77 o successiva.</span><span class="sxs-lookup"><span data-stu-id="56a07-105">This article applies to Microsoft Edge version 77 or later.</span></span>

<span data-ttu-id="56a07-106">Un aspetto fondamentale della sicurezza del cloud è il controllo delle identità e dell'accesso in relazione alla gestione delle risorse cloud.</span><span class="sxs-lookup"><span data-stu-id="56a07-106">A key aspect of cloud security is identity and access when it comes to managing your cloud resources.</span></span> <span data-ttu-id="56a07-107">In un ambiente orientato alla mobilità e al cloud, gli utenti possono accedere alle risorse dell'organizzazione usando un'ampia gamma di dispositivi e app praticamente ovunque.</span><span class="sxs-lookup"><span data-stu-id="56a07-107">In a mobile-first, cloud-first world, users can access your organization's resources using a variety of devices and apps from anywhere.</span></span> <span data-ttu-id="56a07-108">Di conseguenza, concentrarsi solo su chi può accedere a una risorsa non è sufficiente.</span><span class="sxs-lookup"><span data-stu-id="56a07-108">As a result of this, just focusing on who can access a resource is not sufficient.</span></span> <span data-ttu-id="56a07-109">Devi anche esaminare la modalità di accesso a una risorsa.</span><span class="sxs-lookup"><span data-stu-id="56a07-109">You also need to factor in how a resource is accessed.</span></span> <span data-ttu-id="56a07-110">L'accesso condizionale di Azure Active Directory (Azure AD) consente di bilanciare la sicurezza e la produttività.</span><span class="sxs-lookup"><span data-stu-id="56a07-110">Azure Active Directory (Azure AD) Conditional Access helps you master the balance between security and productivity.</span></span>

## <span data-ttu-id="56a07-111">Accesso alle risorse protette con accesso condizionale in Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="56a07-111">Accessing Conditional Access protected resources in Microsoft Edge</span></span>

<span data-ttu-id="56a07-112">Microsoft Edge supporta in modo nativo l'accesso condizionale di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="56a07-112">Microsoft Edge natively supports Azure AD Conditional Access.</span></span> <span data-ttu-id="56a07-113">Non è necessario installare un'estensione separata.</span><span class="sxs-lookup"><span data-stu-id="56a07-113">There's no need to install a separate extension.</span></span> <span data-ttu-id="56a07-114">Quando si accede a un profilo Microsoft Edge con le credenziali Azure AD aziendali, Microsoft Edge consente di accedere in modo semplice alle risorse cloud aziendali protette con l'accesso condizionale.</span><span class="sxs-lookup"><span data-stu-id="56a07-114">When you're signed into a Microsoft Edge profile with enterprise Azure AD credentials, Microsoft Edge allows seamless access to enterprise cloud resources protected using Conditional Access.</span></span>

<span data-ttu-id="56a07-115">In un dispositivo conforme, l'identità che accede alla risorsa deve corrispondere all'identità del profilo.</span><span class="sxs-lookup"><span data-stu-id="56a07-115">On a compliant device, the identity accessing the resource should match the identity on the profile.</span></span>  <span data-ttu-id="56a07-116">In caso contrario, viene visualizzato un messaggio come quello nella schermata successiva.</span><span class="sxs-lookup"><span data-stu-id="56a07-116">If it doesn't, you'll see a message like the one in the next screenshot.</span></span> <span data-ttu-id="56a07-117">Nella schermata di esempio, "testadmin@evostsoneboxtest.com" è l'account di accesso necessario per accedere alla risorsa.</span><span class="sxs-lookup"><span data-stu-id="56a07-117">In the screenshot example, "testadmin@evostsoneboxtest.com" is the sign-in account needed to access the resource.</span></span>

![Messaggio di accesso condizionale nel browser](./media/edge-security/microsoft-edge-security-conditional-access.png)

<span data-ttu-id="56a07-119">Per continuare, devi passare al profilo richiesto (se ne hai uno) o creare un profilo con identità corrispondente.</span><span class="sxs-lookup"><span data-stu-id="56a07-119">To continue, you have to switch to the required profile (if you have one) or create a profile with matching identity.</span></span>

<span data-ttu-id="56a07-120">Per accedere e usare il tuo profilo, fai clic sull'immagine dell'account nell'angolo superiore destro del browser.</span><span class="sxs-lookup"><span data-stu-id="56a07-120">To sign in and work with your profile, click the account picture in the top right corner of the browser.</span></span> <span data-ttu-id="56a07-121">Puoi usare il menu a discesa per:</span><span class="sxs-lookup"><span data-stu-id="56a07-121">You can use the dropdown menu to:</span></span>

- <span data-ttu-id="56a07-122">Selezionare un altro profilo</span><span class="sxs-lookup"><span data-stu-id="56a07-122">Select another profile.</span></span> <span data-ttu-id="56a07-123">Fare clic sul nome del profilo.</span><span class="sxs-lookup"><span data-stu-id="56a07-123">Click the profile name.</span></span>
- <span data-ttu-id="56a07-124">Creare un profilo.</span><span class="sxs-lookup"><span data-stu-id="56a07-124">Create a profile.</span></span> <span data-ttu-id="56a07-125">Fai clic su **Aggiungi un profilo**.</span><span class="sxs-lookup"><span data-stu-id="56a07-125">Click **Add a profile**.</span></span>
- <span data-ttu-id="56a07-126">Gestire i tuoi profili.</span><span class="sxs-lookup"><span data-stu-id="56a07-126">Manage your profiles.</span></span> <span data-ttu-id="56a07-127">Fai clic su **Gestisci impostazioni del profilo**.</span><span class="sxs-lookup"><span data-stu-id="56a07-127">Click **Manage profile settings**.</span></span>

<span data-ttu-id="56a07-128">Questo supporto è disponibile in tutte le piattaforme, incluse tutte le versioni supportate di Windows e macOS.</span><span class="sxs-lookup"><span data-stu-id="56a07-128">This support is available across all platforms, including all supported versions of Windows and macOS.</span></span>

### <span data-ttu-id="56a07-129">Come distribuire l'accesso condizionale in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="56a07-129">How to deploy Conditional Access in Azure Active Directory</span></span>

<span data-ttu-id="56a07-130">L'articolo [Distribuire l'accesso condizionale](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) fornisce una guida dettagliata per distribuire l'accesso condizionale in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="56a07-130">[Deploy Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) provides a detailed guide to help deploy Conditional Access in Azure Active Directory.</span></span>

## <span data-ttu-id="56a07-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="56a07-131">See also</span></span>

- [<span data-ttu-id="56a07-132">Pagina di destinazione di Microsoft Edge in modalità Enterprise</span><span class="sxs-lookup"><span data-stu-id="56a07-132">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="56a07-133">Video: sicurezza, compatibilità e gestibilità</span><span class="sxs-lookup"><span data-stu-id="56a07-133">Video: Security, compatibility, and manageability</span></span>](/microsoft-edge-video-security-compatibility-manageability.md)
