---
title: Domande frequenti sulla sincronizzazione aziendale di Microsoft Edge
ms.author: collw
author: dan-wesley
manager: silvanam
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Domande frequenti sulla sincronizzazione aziendale di Microsoft Edge.
ms.openlocfilehash: a13e1f02f6e871004d45f81159d5cf0a3397b6ad
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2021
ms.locfileid: "11643142"
---
# <a name="microsoft-edge-enterprise-sync-faq"></a><span data-ttu-id="fcd0d-103">Domande frequenti sulla sincronizzazione aziendale di Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="fcd0d-103">Microsoft Edge enterprise sync FAQ</span></span>

<span data-ttu-id="fcd0d-104">Questo articolo risponde alle domande frequenti sulla sincronizzazione aziendale per Microsoft Edge versione 77 o successiva.</span><span class="sxs-lookup"><span data-stu-id="fcd0d-104">This article answers frequently asked questions about enterprise sync for Microsoft Edge version 77 or later.</span></span>

## <a name="security-and-serverdata-compliance"></a><span data-ttu-id="fcd0d-105">Sicurezza e conformità di server e dati</span><span class="sxs-lookup"><span data-stu-id="fcd0d-105">Security and Server/Data Compliance</span></span>

### <a name="is-the-synced-data-encrypted"></a><span data-ttu-id="fcd0d-106">I dati sincronizzati sono crittografati?</span><span class="sxs-lookup"><span data-stu-id="fcd0d-106">Is the synced data encrypted?</span></span>

<span data-ttu-id="fcd0d-107">I dati vengono crittografati durante la trasmissione con TLS 1.2 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="fcd0d-107">The data is encrypted in transport using TLS 1.2 or greater.</span></span> <span data-ttu-id="fcd0d-108">Inoltre, tutti tipi di dati inattivi vengono crittografati nel servizio Microsoft usando AES128.</span><span class="sxs-lookup"><span data-stu-id="fcd0d-108">All data types are additionally encrypted at rest in Microsoft's service using AES128.</span></span> <span data-ttu-id="fcd0d-109">Tutti i tipi di dati, ad eccezione di quelli usati per la sincronizzazione delle schede aperte e della cronologia, vengono inoltre crittografati prima di lasciare il dispositivo dell'utente con chiavi gestite tramite le norme di [Azure Information Protection](./microsoft-edge-policies.md#restrictsignintopattern).</span><span class="sxs-lookup"><span data-stu-id="fcd0d-109">All data types except those used for open tab and history sync are additionally encrypted before leaving the user’s device with keys managed via the [Azure Information Protection](./microsoft-edge-policies.md#restrictsignintopattern) policy.</span></span>

### <a name="why-dont-open-tab-and-history-data-have-more-client-side-encryption"></a><span data-ttu-id="fcd0d-110">Perché per i dati delle schede aperte e della cronologia non viene applicata crittografia del lato del client?</span><span class="sxs-lookup"><span data-stu-id="fcd0d-110">Why don’t open tab and history data have more client-side encryption?</span></span>

<span data-ttu-id="fcd0d-111">Per ridurre l'utilizzo delle risorse nei dispositivi degli utenti finali, i dati della cronologia vengono generati sul lato server in base ai dati di roaming delle schede aperte.</span><span class="sxs-lookup"><span data-stu-id="fcd0d-111">To reduce resource utilization on end-user devices, history data is generated server-side based on open tab roaming data.</span></span> <span data-ttu-id="fcd0d-112">Questo processo non sarebbe possibile con la crittografia lato client di questi dati.</span><span class="sxs-lookup"><span data-stu-id="fcd0d-112">This process would not be possible with client-side encryption of this data.</span></span> <span data-ttu-id="fcd0d-113">Per disabilitare la sincronizzazione delle schede aperte e della cronologia, applicare i criteri [SavingBrowserHistoryDisabled](./microsoft-edge-policies.md#savingbrowserhistorydisabled) o [SyncTypesListDisabled](./microsoft-edge-policies.md#synctypeslistdisabled).</span><span class="sxs-lookup"><span data-stu-id="fcd0d-113">To disable open tab and history sync, apply the [SavingBrowserHistoryDisabled](./microsoft-edge-policies.md#savingbrowserhistorydisabled) or [SyncTypesListDisabled](./microsoft-edge-policies.md#synctypeslistdisabled) policies.</span></span>

### <a name="can-tenant-admins-bring-their-own-key"></a><span data-ttu-id="fcd0d-114">Gli amministratori del tenant possono usare le chiavi personali?</span><span class="sxs-lookup"><span data-stu-id="fcd0d-114">Can tenant admins bring their own key?</span></span>

<span data-ttu-id="fcd0d-115">Sì, tramite  [Azure Information Protection](https://azure.microsoft.com/services/information-protection/).</span><span class="sxs-lookup"><span data-stu-id="fcd0d-115">Yes, through [Azure Information Protection](https://azure.microsoft.com/services/information-protection/).</span></span>

### <a name="where-is-microsoft-edge-sync-data-stored"></a><span data-ttu-id="fcd0d-116">Dove vengono archiviati i dati di sincronizzazione di Microsoft Edge?</span><span class="sxs-lookup"><span data-stu-id="fcd0d-116">Where is Microsoft Edge sync data stored?</span></span>

<span data-ttu-id="fcd0d-117">I dati sincronizzati per gli account Azure AD sono archiviati in server protetti in base all'ID tenant.</span><span class="sxs-lookup"><span data-stu-id="fcd0d-117">Synced data for Azure AD accounts is stored in secure servers according to the tenant ID.</span></span> <span data-ttu-id="fcd0d-118">Ad esempio, i dati per un tenant registrato negli Stati Uniti sono archiviati in server geografici specifici per l'area geografica e usano la stessa soluzione di archiviazione delle applicazioni di Office.</span><span class="sxs-lookup"><span data-stu-id="fcd0d-118">For example, the data for a tenant that is registered in the United States is stored in servers geo-located for that region and uses the same storage solution as Office applications.</span></span>

### <a name="does-the-data-ever-leave-microsofts-cloud-aside-from-syncing-to-microsoft-edge"></a><span data-ttu-id="fcd0d-119">Oltre alla sincronizzazione con Microsoft Edge, i dati lasciano mai il cloud di Microsoft?</span><span class="sxs-lookup"><span data-stu-id="fcd0d-119">Does the data ever leave Microsoft's cloud, aside from syncing to Microsoft Edge?</span></span>

<span data-ttu-id="fcd0d-120">No.</span><span class="sxs-lookup"><span data-stu-id="fcd0d-120">No.</span></span>

### <a name="what-terms-of-service-does-enterprise-sync-fall-under"></a><span data-ttu-id="fcd0d-121">Quali sono le condizioni d'uso che interessano la sincronizzazione aziendale?</span><span class="sxs-lookup"><span data-stu-id="fcd0d-121">What terms of service does enterprise sync fall under?</span></span>

<span data-ttu-id="fcd0d-122">Le condizioni d'uso del servizio di sincronizzazione di Microsoft Edge rientrano nella licenza software Microsoft, visualizzabile in Microsoft Edge in *edge://terms*.</span><span class="sxs-lookup"><span data-stu-id="fcd0d-122">Terms of service for Microsoft Edge sync falls under the Microsoft software license viewable in Microsoft Edge at *edge://terms*.</span></span> <span data-ttu-id="fcd0d-123">Le condizioni d'uso e la sottoscrizione di Azure AD rientrano nelle [Condizioni per l'utilizzo dei servizi online ](https://www.microsoft.com/licensing/product-licensing/products)di Microsoft".</span><span class="sxs-lookup"><span data-stu-id="fcd0d-123">Your Azure AD subscription and terms of service ultimately fall under Microsoft's [Online Service Terms](https://www.microsoft.com/licensing/product-licensing/products).</span></span>

### <a name="does-microsoft-edge-support-government-community-cloud-gcc-high-compliance"></a><span data-ttu-id="fcd0d-124">Microsoft Edge supporta la conformità del Government Community Cloud (GCC) High?</span><span class="sxs-lookup"><span data-stu-id="fcd0d-124">Does Microsoft Edge support Government Community Cloud (GCC) High compliance?</span></span>

<span data-ttu-id="fcd0d-125">Al momento no.</span><span class="sxs-lookup"><span data-stu-id="fcd0d-125">Not today.</span></span> <span data-ttu-id="fcd0d-126">Per i clienti nel cloud GCC High, la sincronizzazione di Microsoft Edge è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="fcd0d-126">For customers in the GCC High cloud, Microsoft Edge sync is disabled.</span></span>

## <a name="applying-sync"></a><span data-ttu-id="fcd0d-127">Applicazione della sincronizzazione</span><span class="sxs-lookup"><span data-stu-id="fcd0d-127">Applying Sync</span></span>

### <a name="why-isnt-microsoft-edge-sync-supported-in-all-m365-subscriptions"></a><span data-ttu-id="fcd0d-128">Perché la sincronizzazione di Microsoft Edge non è supportata in tutti gli abbonamenti a Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="fcd0d-128">Why isn’t Microsoft Edge sync supported in all M365 subscriptions?</span></span>

<span data-ttu-id="fcd0d-129">La sincronizzazione aziendale dipende dalla [Azure Information Protection](https://azure.microsoft.com/services/information-protection/), che non è disponibile in tutti gli abbonamenti a M365.</span><span class="sxs-lookup"><span data-stu-id="fcd0d-129">Enterprise sync depends on [Azure Information Protection](https://azure.microsoft.com/services/information-protection/), which is not available in all M365 subscriptions.</span></span>

### <a name="is-microsoft-edge-sync-based-on-enterprise-state-roaming"></a><span data-ttu-id="fcd0d-130">La sincronizzazione di Microsoft Edge si basa sul servizio Enterprise State Roaming?</span><span class="sxs-lookup"><span data-stu-id="fcd0d-130">Is Microsoft Edge sync based on Enterprise State Roaming?</span></span>

<span data-ttu-id="fcd0d-131">No.</span><span class="sxs-lookup"><span data-stu-id="fcd0d-131">No.</span></span> <span data-ttu-id="fcd0d-132">ESR può essere usato per abilitare la sincronizzazione, tuttavia la sincronizzazione di Microsoft Edge non fa parte del servizio ESR.</span><span class="sxs-lookup"><span data-stu-id="fcd0d-132">ESR can be used to enable sync, but Microsoft Edge sync is not a part of ESR.</span></span> <span data-ttu-id="fcd0d-133">Per ulteriori informazioni, vedere [Sincronizzazione di Microsoft Edge](/DeployEdge/microsoft-edge-enterprise-sync) e [Microsoft Edge e Enterprise State Roaming](/DeployEdge/microsoft-edge-enterprise-state-roaming).</span><span class="sxs-lookup"><span data-stu-id="fcd0d-133">For more information, see [Microsoft Edge Sync](/DeployEdge/microsoft-edge-enterprise-sync) and [Microsoft Edge and Enterprise State Roaming](/DeployEdge/microsoft-edge-enterprise-state-roaming).</span></span>

### <a name="will-microsoft-edge-ever-support-syncing-between-microsoft-edge-and-ie"></a><span data-ttu-id="fcd0d-134">Microsoft Edge supporterà mai la sincronizzazione tra Microsoft Edge e Internet Explorer?</span><span class="sxs-lookup"><span data-stu-id="fcd0d-134">Will Microsoft Edge ever support syncing between Microsoft Edge and IE?</span></span>

<span data-ttu-id="fcd0d-135">Non è previsto il supporto di questa sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="fcd0d-135">There are no plans to support this syncing.</span></span> <span data-ttu-id="fcd0d-136">Se è ancora necessario Internet Explorer nel proprio ambiente per supportare le app legacy, considerare la [nuova modalità Internet Explorer](./edge-ie-mode.md).</span><span class="sxs-lookup"><span data-stu-id="fcd0d-136">If you still need IE in your environment to support legacy apps, consider our [new IE mode](./edge-ie-mode.md).</span></span>

### <a name="will-microsoft-edge-sync-with-microsoft-edge-legacy"></a><span data-ttu-id="fcd0d-137">Microsoft Edge verrà sincronizzato con la versione legacy di Microsoft Edge?</span><span class="sxs-lookup"><span data-stu-id="fcd0d-137">Will Microsoft Edge sync with Microsoft Edge Legacy?</span></span>

<span data-ttu-id="fcd0d-138">No.</span><span class="sxs-lookup"><span data-stu-id="fcd0d-138">No, it won't.</span></span> <span data-ttu-id="fcd0d-139">Crediamo che connettere questi due ecosistemi possa compromettere l'affidabilità della sincronizzazione in Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="fcd0d-139">We believe connecting these two ecosystems will lead to compromises in the reliability of sync in the Microsoft Edge.</span></span> <span data-ttu-id="fcd0d-140">Garantiamo la migrazione dei dati esistenti in Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="fcd0d-140">We will ensure that existing data is migrated to the Microsoft Edge.</span></span> <span data-ttu-id="fcd0d-141">Gli utenti potranno anche importare dati dal browser a loro scelta, il che significa anche che Microsoft Edge non sarà in grado di eseguire la sincronizzazione con Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="fcd0d-141">Users will also be able to import data from browser of their choice, which also means that Microsoft Edge won't have a way to sync with IE.</span></span>

## <a name="managing-sync"></a><span data-ttu-id="fcd0d-142">Gestione della sincronizzazione</span><span class="sxs-lookup"><span data-stu-id="fcd0d-142">Managing Sync</span></span>

### <a name="is-it-possible-to-stop-my-users-from-syncing-with-a-personal-tenant"></a><span data-ttu-id="fcd0d-143">È possibile impedire agli utenti di eseguire la sincronizzazione con un tenant personale?</span><span class="sxs-lookup"><span data-stu-id="fcd0d-143">Is it possible to stop my users from syncing with a personal tenant?</span></span>

<span data-ttu-id="fcd0d-144">Non direttamente, ma è possibile determinare quali profili possono accedere a Microsoft Edge usando i criteri [RestrictSigninToPattern](./microsoft-edge-policies.md#restrictsignintopattern).</span><span class="sxs-lookup"><span data-stu-id="fcd0d-144">Not directly, but you can determine which profiles can sign on to Microsoft Edge using the [RestrictSigninToPattern](./microsoft-edge-policies.md#restrictsignintopattern) policy.</span></span>

## <a name="see-also"></a><span data-ttu-id="fcd0d-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fcd0d-145">See also</span></span>

- [<span data-ttu-id="fcd0d-146">Sincronizzazione di Microsoft Edge in modalità Enterprise</span><span class="sxs-lookup"><span data-stu-id="fcd0d-146">Microsoft Edge Enterprise Sync</span></span>](microsoft-edge-enterprise-sync.md)
- [<span data-ttu-id="fcd0d-147">Microsoft Edge ed Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="fcd0d-147">Microsoft Edge and Enterprise State Roaming</span></span>](microsoft-edge-enterprise-state-roaming.md)
- [<span data-ttu-id="fcd0d-148">Pagina di destinazione di Microsoft Edge in modalità Enterprise</span><span class="sxs-lookup"><span data-stu-id="fcd0d-148">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)