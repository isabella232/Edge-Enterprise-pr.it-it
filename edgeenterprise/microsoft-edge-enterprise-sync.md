---
title: Sincronizzazione di Microsoft Edge in modalità Enterprise
ms.author: scottbo
author: dan-wesley
manager: silvanam
ms.date: 08/03/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Sincronizzazione di Microsoft Edge in modalità Enterprise
ms.openlocfilehash: a6d01356db478871a7c6b386bbb731b32dc4739a
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980277"
---
# <span data-ttu-id="19883-103">Sincronizzazione di Microsoft Edge in modalità Enterprise</span><span class="sxs-lookup"><span data-stu-id="19883-103">Microsoft Edge Enterprise Sync</span></span>

<span data-ttu-id="19883-104">Questo articolo spiega come usare Microsoft Edge per sincronizzare preferiti, password e altri dati del browser in tutti i dispositivi connessi.</span><span class="sxs-lookup"><span data-stu-id="19883-104">This article explains how to use Microsoft Edge to sync your favorites, passwords, and other browser data across all your signed-in devices.</span></span>

> [!NOTE]
> <span data-ttu-id="19883-105">Questo articolo si applica a Microsoft Edge versione 77 o successiva.</span><span class="sxs-lookup"><span data-stu-id="19883-105">This article applies to Microsoft Edge version 77 or later.</span></span>

## <span data-ttu-id="19883-106">Panoramica</span><span class="sxs-lookup"><span data-stu-id="19883-106">Overview</span></span>

<span data-ttu-id="19883-107">La sincronizzazione di Microsoft Edge consente agli utenti di accedere ai dati di esplorazione in tutti i dispositivi connessi.</span><span class="sxs-lookup"><span data-stu-id="19883-107">Microsoft Edge sync enables users to access their browsing data across all their signed-in devices.</span></span> <span data-ttu-id="19883-108">I dati supportati dalla sincronizzazione sono:</span><span class="sxs-lookup"><span data-stu-id="19883-108">The data supported by sync includes:</span></span>

- <span data-ttu-id="19883-109">Preferiti</span><span class="sxs-lookup"><span data-stu-id="19883-109">Favorites</span></span>
- <span data-ttu-id="19883-110">Password</span><span class="sxs-lookup"><span data-stu-id="19883-110">Passwords</span></span>
- <span data-ttu-id="19883-111">Indirizzi e altro (riempimento di moduli)</span><span class="sxs-lookup"><span data-stu-id="19883-111">Addresses and more (form-fill)</span></span>
- <span data-ttu-id="19883-112">Raccolte</span><span class="sxs-lookup"><span data-stu-id="19883-112">Collections</span></span>
- <span data-ttu-id="19883-113">Impostazioni</span><span class="sxs-lookup"><span data-stu-id="19883-113">Settings</span></span>

<span data-ttu-id="19883-114">La funzionalità di sincronizzazione è abilitata tramite il consenso dell'utente e gli utenti possono attivare o disattivare la sincronizzazione per ognuno dei tipi di dati elencati in precedenza.</span><span class="sxs-lookup"><span data-stu-id="19883-114">Sync functionality is enabled via user consent and users can turn sync on or off for each of the data types listed above.</span></span>

> [!NOTE]
> <span data-ttu-id="19883-115">Per supportare la funzionalità di sincronizzazione vengono caricati altri dati di configurazione e connettività del dispositivo (ad esempio il nome dispositivo, la marca e il modello).</span><span class="sxs-lookup"><span data-stu-id="19883-115">Additional device connectivity and configuration data (such as device name, make and model) is uploaded to support sync functionality.</span></span>

## <span data-ttu-id="19883-116">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="19883-116">Prerequisites</span></span>

<span data-ttu-id="19883-117">Attualmente la sincronizzazione di Microsoft Edge per gli account di Azure Active Directory (Azure AD) è disponibile per gli abbonamenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="19883-117">Currently Microsoft Edge sync for Azure Active Directory (Azure AD) accounts is available for the following subscriptions:</span></span>

- <span data-ttu-id="19883-118">Azure AD Premium (P1 e P2)</span><span class="sxs-lookup"><span data-stu-id="19883-118">Azure AD Premium (P1 and P2)</span></span>
- <span data-ttu-id="19883-119">M365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="19883-119">M365 Business Premium</span></span>
- <span data-ttu-id="19883-120">Office 365 E3 e superiore</span><span class="sxs-lookup"><span data-stu-id="19883-120">Office 365 E3 and above</span></span>
- <span data-ttu-id="19883-121">Azure Information Protection (AIP) (P1& P2)</span><span class="sxs-lookup"><span data-stu-id="19883-121">Azure Information Protection (AIP) (P1& P2)</span></span>
- <span data-ttu-id="19883-122">Tutte le sottoscrizioni EDU (O365 A1 o superiore, M365 A1 o superiore o Azure Information Protection P1 o P2 per studenti o docenti)</span><span class="sxs-lookup"><span data-stu-id="19883-122">All EDU subscriptions (O365 A1 or above, M365 A1 or above, or Azure Information Protection P1 or P2 for Students or Faculty)</span></span>

> [!NOTE]
> <span data-ttu-id="19883-123">La sincronizzazione ha una dipendenza dal servizio di protezione offerto da Azure Information Protection (AIP) per proteggere i dati di sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="19883-123">Sync has a dependency on the protection service offered by Azure Information Protection (AIP) to protect sync data.</span></span> <span data-ttu-id="19883-124">Questo servizio è attualmente disponibile per le sottoscrizioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="19883-124">This service is currently available to the preceding subscriptions.</span></span> <span data-ttu-id="19883-125">Per vedere l'elenco completo degli SKU con AIP, vedi [Prezzi per la protezione delle informazioni](https://azure.microsoft.com/pricing/details/information-protection/).</span><span class="sxs-lookup"><span data-stu-id="19883-125">To see the full list of SKUs with AIP, see [Information Protection Pricing](https://azure.microsoft.com/pricing/details/information-protection/).</span></span>

## <span data-ttu-id="19883-126">Opzioni di configurazioni per la sincronizzazione di Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="19883-126">Configuration options for Microsoft Edge sync</span></span>

<span data-ttu-id="19883-127">Per abilitare la sincronizzazione di Microsoft Edge, sono disponibili le opzioni di configurazione seguenti:</span><span class="sxs-lookup"><span data-stu-id="19883-127">The following configuration options are available for enabling Microsoft Edge sync:</span></span>

- <span data-ttu-id="19883-128">Azure Information Protection (AIP)</span><span class="sxs-lookup"><span data-stu-id="19883-128">Azure Information Protection (AIP)</span></span>
- <span data-ttu-id="19883-129">Azure AD Enterprise State Roaming (ESR)</span><span class="sxs-lookup"><span data-stu-id="19883-129">Azure AD Enterprise State Roaming (ESR)</span></span>

<span data-ttu-id="19883-130">Se sia AIP che ESR sono disabilitati, gli utenti riceveranno un messaggio di errore indicante che la sincronizzazione non è disponibile per i loro account.</span><span class="sxs-lookup"><span data-stu-id="19883-130">If both AIP and ESR are disabled, users will see an error message indicating that sync is not available for their account.</span></span>

### <span data-ttu-id="19883-131">Azure Information Protection (AIP)</span><span class="sxs-lookup"><span data-stu-id="19883-131">Azure Information Protection (AIP)</span></span>

<span data-ttu-id="19883-132">Se il servizio Azure Information Protection (AIP) è abilitato per un tenant, tutti gli utenti possono sincronizzare i dati di Microsoft Edge, indipendentemente dalle licenze.</span><span class="sxs-lookup"><span data-stu-id="19883-132">If the Azure Information Protection (AIP) service is enabled for a tenant, all users can sync Microsoft Edge data, regardless of licensing.</span></span> <span data-ttu-id="19883-133">[Qui](https://docs.microsoft.com/azure/information-protection/activate-office365) è possibile trovare istruzioni su come abilitare il servizio AIP.</span><span class="sxs-lookup"><span data-stu-id="19883-133">Instructions on how to enable AIP can be found [here](https://docs.microsoft.com/azure/information-protection/activate-office365).</span></span>

<span data-ttu-id="19883-134">Per limitare la sincronizzazione a determinati gruppi di utenti, è possibile abilitare i [criteri di controllo di onboarding AADRM](https://docs.microsoft.com/powershell/module/aadrm/set-aadrmonboardingcontrolpolicy?view=azureipps) per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="19883-134">To restrict sync to certain set of users, you can enable the [AADRM onboarding control policy](https://docs.microsoft.com/powershell/module/aadrm/set-aadrmonboardingcontrolpolicy?view=azureipps) for those users.</span></span> <span data-ttu-id="19883-135">Se la sincronizzazione non è ancora disponibile dopo avere eseguito l'onboarding di tutti gli utenti necessari, assicurarsi che IPCv3Service sia abilitato usando il cmdlet [Get-AIPServiceIPCv3](https://docs.microsoft.com/powershell/module/aipservice/Get-AipServiceIPCv3?view=azureipps) PowerShell.</span><span class="sxs-lookup"><span data-stu-id="19883-135">If sync is still not available after ensuring that all necessary users are onboarded, ensure that the IPCv3Service is enabled using the [Get-AIPServiceIPCv3](https://docs.microsoft.com/powershell/module/aipservice/Get-AipServiceIPCv3?view=azureipps) PowerShell cmdlet.</span></span>

> [!CAUTION]
> <span data-ttu-id="19883-136">L'attivazione di Azure Information Protection limiterà inoltre l'accesso per altre applicazioni che usano AIP, come Microsoft Word o Microsoft Outlook.</span><span class="sxs-lookup"><span data-stu-id="19883-136">Activating Azure Information Protection will also restrict access for other applications using AIP, such as Microsoft Word or Microsoft Outlook.</span></span>

### <span data-ttu-id="19883-137">Azure AD Enterprise State Roaming (ESR)</span><span class="sxs-lookup"><span data-stu-id="19883-137">Azure AD Enterprise State Roaming (ESR)</span></span>

<span data-ttu-id="19883-138">Se la funzionalità di Azure Active Directory [Enterprise State Roaming](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-overview) (ESR) è abilitata per un utente o un tenant, la funzionalità di sincronizzazione Microsoft Edge è disponibile indipendentemente dall'impostazione dei criteri di controllo di onboarding.</span><span class="sxs-lookup"><span data-stu-id="19883-138">If the Azure Active Directory [Enterprise State Roaming](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-overview) (ESR) feature is enabled for any user or tenant, they can use the Microsoft Edge sync feature regardless of the onboarding control policy setting.</span></span>

## <span data-ttu-id="19883-139">Microsoft Edge ed Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="19883-139">Microsoft Edge and Enterprise State Roaming</span></span>

<span data-ttu-id="19883-140">Il nuovo Microsoft Edge è un'applicazione multipiattaforma con un ambito esteso per la sincronizzazione dei dati degli utenti in tutti i dispositivi e non fa più parte di Azure AD Enterprise State Roaming.</span><span class="sxs-lookup"><span data-stu-id="19883-140">The new Microsoft Edge is a cross-platform application with an expanded scope for syncing user data across all their devices and is no longer a part of Azure AD Enterprise State Roaming.</span></span> <span data-ttu-id="19883-141">Tuttavia, il nuovo Microsoft Edge conserva le caratteristiche della protezione dei dati di ESR, ad esempio la possibilità di portare la propria chiave.</span><span class="sxs-lookup"><span data-stu-id="19883-141">However, the new Microsoft Edge will fulfill the data protection promises of ESR, such as the ability to bring your own key.</span></span> <span data-ttu-id="19883-142">Per ulteriori informazioni, vedi [Microsoft Edge e Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md).</span><span class="sxs-lookup"><span data-stu-id="19883-142">For more information, see [Microsoft Edge and Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md).</span></span>

## <span data-ttu-id="19883-143">Criteri di gruppo per la sincronizzazione</span><span class="sxs-lookup"><span data-stu-id="19883-143">Sync group policies</span></span>

<span data-ttu-id="19883-144">I criteri di gruppo seguenti influiscono sulla sincronizzazione di Microsoft Edge:</span><span class="sxs-lookup"><span data-stu-id="19883-144">The following group policies impact Microsoft Edge sync:</span></span>

- <span data-ttu-id="19883-145">[SyncDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#syncdisabled): disabilita completamente la sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="19883-145">[SyncDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#syncdisabled): Disables sync completely.</span></span>
- <span data-ttu-id="19883-146">[SavingBrowserHistoryDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#savingbrowserhistorydisabled): disabilita il salvataggio della cronologia esplorazioni e della sincronizzazione. Questo criterio disabilitata anche la sincronizzazione delle schede aperte.</span><span class="sxs-lookup"><span data-stu-id="19883-146">[SavingBrowserHistoryDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#savingbrowserhistorydisabled): Disables saving browsing history and sync. This policy also disables open-tabs sync.</span></span>
- <span data-ttu-id="19883-147">[SyncTypesListDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#synctypeslistdisabled): configurare l'elenco dei tipi esclusi dalla sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="19883-147">[SyncTypesListDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#synctypeslistdisabled): Configure the list of types that are excluded from synchronization.</span></span>

## <span data-ttu-id="19883-148">Domande frequenti</span><span class="sxs-lookup"><span data-stu-id="19883-148">Frequently Asked Questions</span></span>

### <span data-ttu-id="19883-149">SICUREZZA e CONFORMITÀ SERVER/DATI</span><span class="sxs-lookup"><span data-stu-id="19883-149">SECURITY and SERVER/DATA COMPLIANCE</span></span>

#### <span data-ttu-id="19883-150">I dati sincronizzati sono crittografati?</span><span class="sxs-lookup"><span data-stu-id="19883-150">Is the synced data encrypted?</span></span> 

<span data-ttu-id="19883-151">I dati vengono crittografati durante la trasmissione tramite TLS 1.2 o versione successiva, e successivamente in modo statico nel servizio Microsoft tramite AES256.</span><span class="sxs-lookup"><span data-stu-id="19883-151">The data is encrypted in transport using TLS 1.2 or greater, and additionally at rest in Microsoft's service using AES256.</span></span>

#### <span data-ttu-id="19883-152">Dove vengono archiviati i dati sincronizzati di Microsoft Edge?</span><span class="sxs-lookup"><span data-stu-id="19883-152">Where is Microsoft Edge sync data stored?</span></span>

<span data-ttu-id="19883-153">I dati sincronizzati per gli account Azure AD sono archiviati in server protetti in base all'ID tenant.</span><span class="sxs-lookup"><span data-stu-id="19883-153">Synced data for Azure AD accounts is stored in secure servers according to the tenant ID.</span></span> <span data-ttu-id="19883-154">Ad esempio, i dati per un tenant registrato negli Stati Uniti sono archiviati in server geografici specifici per l'area geografica e usano la stessa soluzione di archiviazione delle applicazioni di Office.</span><span class="sxs-lookup"><span data-stu-id="19883-154">For example, the data for a tenant that is registered in the United States is stored in servers geo-located for that region and uses the same storage solution as Office applications.</span></span>

#### <span data-ttu-id="19883-155">Oltre alla sincronizzazione con Microsoft Edge, i dati lasciano mai il cloud di Microsoft?</span><span class="sxs-lookup"><span data-stu-id="19883-155">Does the data ever leave Microsoft's cloud, aside from syncing to Microsoft Edge?</span></span>

<span data-ttu-id="19883-156">No.</span><span class="sxs-lookup"><span data-stu-id="19883-156">No.</span></span>

#### <span data-ttu-id="19883-157">Gli amministratori del tenant possono usare le chiavi personali?</span><span class="sxs-lookup"><span data-stu-id="19883-157">Can tenant admins bring their own key?</span></span>

<span data-ttu-id="19883-158">Sì, tramite [Azure Information Protection](https://azure.microsoft.com/services/information-protection/).</span><span class="sxs-lookup"><span data-stu-id="19883-158">Yes, through [Azure Information Protection](https://azure.microsoft.com/services/information-protection/).</span></span>

#### <span data-ttu-id="19883-159">Quali sono le condizioni dell'utilizzo del servizio che interessano la sincronizzazione aziendale?</span><span class="sxs-lookup"><span data-stu-id="19883-159">What terms of service does enterprise sync fall under?</span></span>

<span data-ttu-id="19883-160">Le condizioni dell'utilizzo del servizio sono le stesse dell'abbonamento a Azure AD.</span><span class="sxs-lookup"><span data-stu-id="19883-160">The terms of service are the same terms as your Azure AD subscription.</span></span> <span data-ttu-id="19883-161">Tutte le condizioni dell'utilizzo del servizio di Azure AD rientrano nelle [Condizioni dei servizi online](https://www.microsoft.com/licensing/product-licensing/products) di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="19883-161">All the Azure AD terms of service ultimately fall under Microsoft's [Online Service Terms](https://www.microsoft.com/licensing/product-licensing/products).</span></span>

#### <span data-ttu-id="19883-162">Microsoft Edge supporta la conformità del Government Community Cloud (GCC) High?</span><span class="sxs-lookup"><span data-stu-id="19883-162">Does Microsoft Edge support Government Community Cloud (GCC) High compliance?</span></span>

<span data-ttu-id="19883-163">Al momento no.</span><span class="sxs-lookup"><span data-stu-id="19883-163">Not today.</span></span> <span data-ttu-id="19883-164">GCC High è di livello D, mentre Microsoft Edge supporta fino al livello C.</span><span class="sxs-lookup"><span data-stu-id="19883-164">GCC High is Tier D, while Microsoft Edge supports up to Tier C.</span></span>

### <span data-ttu-id="19883-165">APPLICAZIONE DELLA SINCRONIZZAZIONE</span><span class="sxs-lookup"><span data-stu-id="19883-165">APPLYING SYNC</span></span>

#### <span data-ttu-id="19883-166">Cosa accade per i clienti aziendali e di istituti di istruzione che decidono di rimanere con Microsoft Edge Legacy?</span><span class="sxs-lookup"><span data-stu-id="19883-166">What happens with enterprise and educational customers who decide to stay with Microsoft Edge Legacy?</span></span>

<span data-ttu-id="19883-167">La versione corrente del browser Microsoft Edge continuerà a partecipare all'offerta ESR.</span><span class="sxs-lookup"><span data-stu-id="19883-167">The current version of Microsoft Edge browser will continue to participate in the ESR offering.</span></span>

#### <span data-ttu-id="19883-168">Perché è necessario un abbonamento Premium ad Azure AD per la sincronizzazione?</span><span class="sxs-lookup"><span data-stu-id="19883-168">Why do I need a premium Azure AD subscription to sync?</span></span>

<span data-ttu-id="19883-169">La sincronizzazione aziendale dipende da Azure Information Protection, che non è disponibile in tutti i livelli di Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="19883-169">Enterprise sync depends on Azure Information Protection, which is not available in all Azure AD tiers.</span></span>

#### <span data-ttu-id="19883-170">La sincronizzazione di Microsoft Edge si basa sul servizio Enterprise State Roaming?</span><span class="sxs-lookup"><span data-stu-id="19883-170">Is Microsoft Edge sync based on Enterprise State Roaming?</span></span>

<span data-ttu-id="19883-171">No.</span><span class="sxs-lookup"><span data-stu-id="19883-171">No.</span></span> <span data-ttu-id="19883-172">ESR può essere usato per abilitare la sincronizzazione, tuttavia la sincronizzazione di Microsoft Edge non fa parte del servizio ESR.</span><span class="sxs-lookup"><span data-stu-id="19883-172">ESR can be used to enable sync, but Microsoft Edge sync is not a part of ESR.</span></span> <span data-ttu-id="19883-173">Per ulteriori informazioni, vedere [Sincronizzazione di Microsoft Edge](microsoft-edge-enterprise-sync.md) e [Microsoft Edge e Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md).</span><span class="sxs-lookup"><span data-stu-id="19883-173">For more information, see [Microsoft Edge Sync](microsoft-edge-enterprise-sync.md) and [Microsoft Edge and Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md).</span></span>

#### <span data-ttu-id="19883-174">Microsoft Edge supporterà mai la sincronizzazione tra Microsoft Edge e Internet Explorer?</span><span class="sxs-lookup"><span data-stu-id="19883-174">Will Microsoft Edge ever support syncing between Microsoft Edge and IE?</span></span>

<span data-ttu-id="19883-175">Non è previsto il supporto di questa sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="19883-175">There are no plans to support this syncing.</span></span> <span data-ttu-id="19883-176">Se è ancora necessario Internet Explorer nel proprio ambiente per supportare le app legacy, prendere in considerazione la [nuova modalità di IE](https://docs.microsoft.com/deployedge/edge-ie-mode).</span><span class="sxs-lookup"><span data-stu-id="19883-176">If you still need IE in your environment to support legacy apps, consider our [new IE mode](https://docs.microsoft.com/deployedge/edge-ie-mode).</span></span>

#### <span data-ttu-id="19883-177">Il nuovo browser Microsoft Edge verrà sincronizzato con la Versione legacy di Microsoft Edge?</span><span class="sxs-lookup"><span data-stu-id="19883-177">Will the new Microsoft Edge browser sync with Microsoft Edge Legacy?</span></span>

<span data-ttu-id="19883-178">No, non viene sincronizzato.</span><span class="sxs-lookup"><span data-stu-id="19883-178">No, it won't.</span></span> <span data-ttu-id="19883-179">Riteniamo che la connessione di questi due ecosistemi consente compromessi nell'affidabilità della sincronizzazione nel nuovo Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="19883-179">We believe connecting these two ecosystems will lead to compromises in the reliability of sync in the new Microsoft Edge.</span></span> <span data-ttu-id="19883-180">Garantiamo la migrazione dei dati esistenti al nuovo Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="19883-180">We will ensure that existing data is migrated to the new Microsoft Edge.</span></span> <span data-ttu-id="19883-181">Gli utenti saranno anche in grado di importare i dati dal browser che desiderano.</span><span class="sxs-lookup"><span data-stu-id="19883-181">Users will also be able to import data from browser of their choice.</span></span> <span data-ttu-id="19883-182">Questo significa anche che il nuovo browser Microsoft Edge non avrà un modo per eseguire la sincronizzazione con Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="19883-182">This also means that new Microsoft Edge browser won't have a way to sync with IE.</span></span>

### <span data-ttu-id="19883-183">GESTIONE DELLA SINCRONIZZAZIONE</span><span class="sxs-lookup"><span data-stu-id="19883-183">MANAGING SYNC</span></span>

#### <span data-ttu-id="19883-184">È possibile impedire agli utenti di eseguire la sincronizzazione con un tenant personale?</span><span class="sxs-lookup"><span data-stu-id="19883-184">Is it possible to stop my users from syncing with a personal tenant?</span></span>

<span data-ttu-id="19883-185">Non direttamente, ma è possibile determinare quali profili possono accedere a Microsoft Edge usando i criteri [RestrictSigninToPattern](https://docs.microsoft.com/deployedge/microsoft-edge-policies#restrictsignintopattern).</span><span class="sxs-lookup"><span data-stu-id="19883-185">Not directly, but you can determine which profiles can sign on to Microsoft Edge using the [RestrictSigninToPattern](https://docs.microsoft.com/deployedge/microsoft-edge-policies#restrictsignintopattern) policy.</span></span>

## <span data-ttu-id="19883-186">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="19883-186">See also</span></span>

- [<span data-ttu-id="19883-187">Pagina di destinazione di Microsoft Edge in modalità Enterprise</span><span class="sxs-lookup"><span data-stu-id="19883-187">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="19883-188">Microsoft Edge ed Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="19883-188">Microsoft Edge and Enterprise State Roaming</span></span>](microsoft-edge-enterprise-state-roaming.md)
