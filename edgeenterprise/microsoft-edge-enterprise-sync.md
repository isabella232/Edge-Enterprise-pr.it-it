---
title: Sincronizzazione di Microsoft Edge in modalità Enterprise
ms.author: scottbo
author: dan-wesley
manager: silvanam
ms.date: 09/30/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Sincronizzazione di Microsoft Edge in modalità Enterprise
ms.openlocfilehash: d5868fb496c036d750925bb5ae6dfa3de0293fd2
ms.sourcegitcommit: 8a4479a1b034c3c13ea03ee3a2374a1af332cb38
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/30/2020
ms.locfileid: "11091948"
---
# <span data-ttu-id="608c7-103">Sincronizzazione di Microsoft Edge in modalità Enterprise</span><span class="sxs-lookup"><span data-stu-id="608c7-103">Microsoft Edge Enterprise Sync</span></span>

<span data-ttu-id="608c7-104">Questo articolo spiega come usare Microsoft Edge per sincronizzare preferiti, password e altri dati del browser in tutti i dispositivi connessi.</span><span class="sxs-lookup"><span data-stu-id="608c7-104">This article explains how to use Microsoft Edge to sync your favorites, passwords, and other browser data across all your signed-in devices.</span></span>

> [!NOTE]
> <span data-ttu-id="608c7-105">Questo articolo si applica a Microsoft Edge versione 77 o successiva.</span><span class="sxs-lookup"><span data-stu-id="608c7-105">This article applies to Microsoft Edge version 77 or later.</span></span>

## <span data-ttu-id="608c7-106">Panoramica</span><span class="sxs-lookup"><span data-stu-id="608c7-106">Overview</span></span>

<span data-ttu-id="608c7-107">La sincronizzazione di Microsoft Edge consente agli utenti di accedere ai dati di esplorazione in tutti i dispositivi connessi.</span><span class="sxs-lookup"><span data-stu-id="608c7-107">Microsoft Edge sync enables users to access their browsing data across all their signed-in devices.</span></span> <span data-ttu-id="608c7-108">I dati supportati dalla sincronizzazione sono:</span><span class="sxs-lookup"><span data-stu-id="608c7-108">The data supported by sync includes:</span></span>

- <span data-ttu-id="608c7-109">Preferiti</span><span class="sxs-lookup"><span data-stu-id="608c7-109">Favorites</span></span>
- <span data-ttu-id="608c7-110">Password</span><span class="sxs-lookup"><span data-stu-id="608c7-110">Passwords</span></span>
- <span data-ttu-id="608c7-111">Indirizzi e altro (riempimento di moduli)</span><span class="sxs-lookup"><span data-stu-id="608c7-111">Addresses and more (form-fill)</span></span>
- <span data-ttu-id="608c7-112">Raccolte</span><span class="sxs-lookup"><span data-stu-id="608c7-112">Collections</span></span>
- <span data-ttu-id="608c7-113">Impostazioni</span><span class="sxs-lookup"><span data-stu-id="608c7-113">Settings</span></span>

<span data-ttu-id="608c7-114">La funzionalità di sincronizzazione è abilitata tramite il consenso dell'utente e gli utenti possono attivare o disattivare la sincronizzazione per ognuno dei tipi di dati elencati in precedenza.</span><span class="sxs-lookup"><span data-stu-id="608c7-114">Sync functionality is enabled via user consent and users can turn sync on or off for each of the data types listed above.</span></span>

> [!NOTE]
> <span data-ttu-id="608c7-115">Per supportare la funzionalità di sincronizzazione vengono caricati altri dati di configurazione e connettività del dispositivo (ad esempio il nome dispositivo, la marca e il modello).</span><span class="sxs-lookup"><span data-stu-id="608c7-115">Additional device connectivity and configuration data (such as device name, make and model) is uploaded to support sync functionality.</span></span>

## <span data-ttu-id="608c7-116">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="608c7-116">Prerequisites</span></span>

<span data-ttu-id="608c7-117">La sincronizzazione di Microsoft Edge per gli account di Azure Active Directory (Azure AD) è disponibile per gli abbonamenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="608c7-117">Microsoft Edge sync for Azure Active Directory (Azure AD) accounts is available for any of the following subscriptions:</span></span>

- <span data-ttu-id="608c7-118">Azure AD Premium (P1 e P2)</span><span class="sxs-lookup"><span data-stu-id="608c7-118">Azure AD Premium (P1 and P2)</span></span>
- <span data-ttu-id="608c7-119">M365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="608c7-119">M365 Business Premium</span></span>
- <span data-ttu-id="608c7-120">Office 365 E3 e superiore</span><span class="sxs-lookup"><span data-stu-id="608c7-120">Office 365 E3 and above</span></span>
- <span data-ttu-id="608c7-121">Azure Information Protection (AIP) (P1& P2)</span><span class="sxs-lookup"><span data-stu-id="608c7-121">Azure Information Protection (AIP) (P1& P2)</span></span>
- <span data-ttu-id="608c7-122">Tutti gli abbonamenti EDU (Microsoft Apps per studenti o istituti di istruzione, Exchange Online per studenti o istituti di istruzione, Office 365 A1 o versione successiva, Microsoft 365 A1 o superiore o Azure Information Protection P1 o P2 per studenti o istituti di istruzione)</span><span class="sxs-lookup"><span data-stu-id="608c7-122">All EDU subscriptions (Microsoft Apps for Students or Faculty, Exchange Online for Students or Faculty, O365 A1 or above, M365 A1 or above, or Azure Information Protection P1 or P2 for Students or Faculty)</span></span>

## <span data-ttu-id="608c7-123">Configurazione di Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="608c7-123">Configuring Microsoft Edge sync</span></span>

<span data-ttu-id="608c7-124">Le opzioni di configurazioni per la sincronizzazione di Microsoft Edge sono disponibili tramite il servizio di Azure Information Protection (AIP).</span><span class="sxs-lookup"><span data-stu-id="608c7-124">Configuration options for Microsoft Edge sync are available through the Azure Information Protection (AIP) service.</span></span> <span data-ttu-id="608c7-125">Quando AIP è abilitato per un tenant, tutti gli utenti possono sincronizzare i dati di Microsoft Edge, indipendentemente dalle licenze.</span><span class="sxs-lookup"><span data-stu-id="608c7-125">When AIP is enabled for a tenant, all users can sync Microsoft Edge data, regardless of licensing.</span></span> <span data-ttu-id="608c7-126">[Qui](https://docs.microsoft.com/azure/information-protection/activate-office365) è possibile trovare istruzioni su come abilitare il servizio AIP.</span><span class="sxs-lookup"><span data-stu-id="608c7-126">Instructions on how to enable AIP can be found [here](https://docs.microsoft.com/azure/information-protection/activate-office365).</span></span>

<span data-ttu-id="608c7-127">Per limitare la sincronizzazione a determinati gruppi di utenti, è possibile abilitare i [criteri di controllo di onboarding AIP](https://docs.microsoft.com/powershell/module/aipservice/set-aipserviceonboardingcontrolpolicy?view=azureipps)  per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="608c7-127">To restrict sync to certain set of users, you can enable the [AIP onboarding control policy](https://docs.microsoft.com/powershell/module/aipservice/set-aipserviceonboardingcontrolpolicy?view=azureipps) for those users.</span></span> <span data-ttu-id="608c7-128">Se la sincronizzazione non è ancora disponibile dopo avere eseguito l'onboarding di tutti gli utenti necessari, assicurarsi che IPCv3Service sia abilitato usando il cmdlet [Get-AIPServiceIPCv3](https://docs.microsoft.com/powershell/module/aipservice/get-aipserviceipcv3?view=azureipps) PowerShell.</span><span class="sxs-lookup"><span data-stu-id="608c7-128">If sync is still not available after ensuring that all necessary users are onboarded, ensure that the IPCv3Service is enabled using the [Get-AIPServiceIPCv3](https://docs.microsoft.com/powershell/module/aipservice/get-aipserviceipcv3?view=azureipps)  PowerShell cmdlet.</span></span>

> [!CAUTION]
> <span data-ttu-id="608c7-129">L'attivazione di Azure Information Protection consentirà inoltre ad altre applicazioni, come Microsoft Word o Microsoft Outlook, di proteggere il contenuto con AIP.</span><span class="sxs-lookup"><span data-stu-id="608c7-129">Activating Azure Information Protection will also allow other applications, such as Microsoft Word or Microsoft Outlook, to protect content with AIP.</span></span> <span data-ttu-id="608c7-130">I criteri di controllo onboarding usati per limitare la sincronizzazione Edge impediranno anche ad altre applicazioni di proteggere il contenuto tramite AIP.</span><span class="sxs-lookup"><span data-stu-id="608c7-130">In addition, any onboarding control policy used to restrict Edge sync will also restrict other applications from protecting content using AIP.</span></span>

## <span data-ttu-id="608c7-131">Microsoft Edge ed Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="608c7-131">Microsoft Edge and Enterprise State Roaming</span></span>

<span data-ttu-id="608c7-132">Il nuovo Microsoft Edge è un'applicazione multipiattaforma con un ambito esteso per la sincronizzazione dei dati degli utenti in tutti i dispositivi e non fa più parte di Azure AD Enterprise State Roaming.</span><span class="sxs-lookup"><span data-stu-id="608c7-132">The new Microsoft Edge is a cross-platform application with an expanded scope for syncing user data across all their devices and is no longer a part of Azure AD Enterprise State Roaming.</span></span> <span data-ttu-id="608c7-133">Tuttavia, il nuovo Microsoft Edge conserva le caratteristiche della protezione dei dati di ESR, ad esempio la possibilità di portare la propria chiave.</span><span class="sxs-lookup"><span data-stu-id="608c7-133">However, the new Microsoft Edge will fulfill the data protection promises of ESR, such as the ability to bring your own key.</span></span> <span data-ttu-id="608c7-134">Per ulteriori informazioni, vedi [Microsoft Edge e Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md).</span><span class="sxs-lookup"><span data-stu-id="608c7-134">For more information, see [Microsoft Edge and Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md).</span></span>

## <span data-ttu-id="608c7-135">Criteri di gruppo per la sincronizzazione</span><span class="sxs-lookup"><span data-stu-id="608c7-135">Sync group policies</span></span>

<span data-ttu-id="608c7-136">I criteri di gruppo seguenti influiscono sulla sincronizzazione di Microsoft Edge:</span><span class="sxs-lookup"><span data-stu-id="608c7-136">The following group policies impact Microsoft Edge sync:</span></span>

- <span data-ttu-id="608c7-137">[SyncDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#syncdisabled): disabilita completamente la sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="608c7-137">[SyncDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#syncdisabled): Disables sync completely.</span></span>
- <span data-ttu-id="608c7-138">[SavingBrowserHistoryDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#savingbrowserhistorydisabled): disabilita il salvataggio della cronologia esplorazioni e della sincronizzazione. Questo criterio disabilitata anche la sincronizzazione delle schede aperte.</span><span class="sxs-lookup"><span data-stu-id="608c7-138">[SavingBrowserHistoryDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#savingbrowserhistorydisabled): Disables saving browsing history and sync. This policy also disables open-tabs sync.</span></span>
- <span data-ttu-id="608c7-139">[SyncTypesListDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#synctypeslistdisabled): configurare l'elenco dei tipi esclusi dalla sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="608c7-139">[SyncTypesListDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#synctypeslistdisabled): Configure the list of types that are excluded from synchronization.</span></span>
- <span data-ttu-id="608c7-140">[RoamingProfileSupportEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#roamingprofilesupportenabled): consente ai profili di Active Directory (AD) di usare lo spazio di archiviazione locale.</span><span class="sxs-lookup"><span data-stu-id="608c7-140">[RoamingProfileSupportEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#roamingprofilesupportenabled): Allow Active Directory (AD) profiles to use on-premises storage.</span></span> <span data-ttu-id="608c7-141">Per altre informazioni, vedere [Sincronizzazione locale per gli utenti di Active Directory (AD)](https://docs.microsoft.com/DeployEdge/microsoft-edge-on-premises-sync).</span><span class="sxs-lookup"><span data-stu-id="608c7-141">For more information, see [On-premises sync for Active Directory (AD) users](https://docs.microsoft.com/DeployEdge/microsoft-edge-on-premises-sync).</span></span>
- <span data-ttu-id="608c7-142">[ForceSync]( https://docs.microsoft.com/deployedge/microsoft-edge-policies#forcesync): attiva la sincronizzazione per impostazione predefinita e non è necessario il consenso da parte dell’utente per la sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="608c7-142">[ForceSync]( https://docs.microsoft.com/deployedge/microsoft-edge-policies#forcesync): Turn sync on by default and do not require user consent to sync.</span></span>  

## <span data-ttu-id="608c7-143">Domande frequenti</span><span class="sxs-lookup"><span data-stu-id="608c7-143">Frequently Asked Questions</span></span>

### <span data-ttu-id="608c7-144">SICUREZZA e CONFORMITÀ SERVER/DATI</span><span class="sxs-lookup"><span data-stu-id="608c7-144">SECURITY and SERVER/DATA COMPLIANCE</span></span>

#### <span data-ttu-id="608c7-145">I dati sincronizzati sono crittografati?</span><span class="sxs-lookup"><span data-stu-id="608c7-145">Is the synced data encrypted?</span></span> 

<span data-ttu-id="608c7-146">I dati sono crittografati in Transport con TLS 1.2 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="608c7-146">The data is encrypted in transport using TLS 1.2 or greater.</span></span> <span data-ttu-id="608c7-147">La maggior parte dei tipi di dati viene ulteriormente crittografata nel servizio Microsoft tramite AES256.</span><span class="sxs-lookup"><span data-stu-id="608c7-147">Most data types are additionally encrypted at rest in Microsoft's service using AES256.</span></span> 

#### <span data-ttu-id="608c7-148">Dove vengono archiviati i dati sincronizzati di Microsoft Edge?</span><span class="sxs-lookup"><span data-stu-id="608c7-148">Where is Microsoft Edge sync data stored?</span></span>

<span data-ttu-id="608c7-149">I dati sincronizzati per gli account Azure AD sono archiviati in server protetti in base all'ID tenant.</span><span class="sxs-lookup"><span data-stu-id="608c7-149">Synced data for Azure AD accounts is stored in secure servers according to the tenant ID.</span></span> <span data-ttu-id="608c7-150">Ad esempio, i dati per un tenant registrato negli Stati Uniti sono archiviati in server geografici specifici per l'area geografica e usano la stessa soluzione di archiviazione delle applicazioni di Office.</span><span class="sxs-lookup"><span data-stu-id="608c7-150">For example, the data for a tenant that is registered in the United States is stored in servers geo-located for that region and uses the same storage solution as Office applications.</span></span>

#### <span data-ttu-id="608c7-151">Oltre alla sincronizzazione con Microsoft Edge, i dati lasciano mai il cloud di Microsoft?</span><span class="sxs-lookup"><span data-stu-id="608c7-151">Does the data ever leave Microsoft's cloud, aside from syncing to Microsoft Edge?</span></span>

<span data-ttu-id="608c7-152">No.</span><span class="sxs-lookup"><span data-stu-id="608c7-152">No.</span></span>

#### <span data-ttu-id="608c7-153">Gli amministratori del tenant possono usare le chiavi personali?</span><span class="sxs-lookup"><span data-stu-id="608c7-153">Can tenant admins bring their own key?</span></span>

<span data-ttu-id="608c7-154">Sì, tramite [Azure Information Protection](https://azure.microsoft.com/services/information-protection/).</span><span class="sxs-lookup"><span data-stu-id="608c7-154">Yes, through [Azure Information Protection](https://azure.microsoft.com/services/information-protection/).</span></span>

#### <span data-ttu-id="608c7-155">Quali sono le condizioni dell'utilizzo del servizio che interessano la sincronizzazione aziendale?</span><span class="sxs-lookup"><span data-stu-id="608c7-155">What terms of service does enterprise sync fall under?</span></span>

<span data-ttu-id="608c7-156">Le condizioni dell'utilizzo del servizio sono le stesse dell'abbonamento a Azure AD.</span><span class="sxs-lookup"><span data-stu-id="608c7-156">The terms of service are the same terms as your Azure AD subscription.</span></span> <span data-ttu-id="608c7-157">Tutte le condizioni dell'utilizzo del servizio di Azure AD rientrano nelle [Condizioni dei servizi online](https://www.microsoft.com/licensing/product-licensing/products) di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="608c7-157">All the Azure AD terms of service ultimately fall under Microsoft's [Online Service Terms](https://www.microsoft.com/licensing/product-licensing/products).</span></span>

#### <span data-ttu-id="608c7-158">Microsoft Edge supporta la conformità del Government Community Cloud (GCC) High?</span><span class="sxs-lookup"><span data-stu-id="608c7-158">Does Microsoft Edge support Government Community Cloud (GCC) High compliance?</span></span>

<span data-ttu-id="608c7-159">Al momento no.</span><span class="sxs-lookup"><span data-stu-id="608c7-159">Not today.</span></span> <span data-ttu-id="608c7-160">GCC High è di livello D, mentre Microsoft Edge supporta fino al livello C.</span><span class="sxs-lookup"><span data-stu-id="608c7-160">GCC High is Tier D, while Microsoft Edge supports up to Tier C.</span></span>

### <span data-ttu-id="608c7-161">APPLICAZIONE DELLA SINCRONIZZAZIONE</span><span class="sxs-lookup"><span data-stu-id="608c7-161">APPLYING SYNC</span></span>

#### <span data-ttu-id="608c7-162">Cosa accade per i clienti aziendali e di istituti di istruzione che decidono di rimanere con Microsoft Edge Legacy?</span><span class="sxs-lookup"><span data-stu-id="608c7-162">What happens with enterprise and educational customers who decide to stay with Microsoft Edge Legacy?</span></span>

<span data-ttu-id="608c7-163">La versione corrente del browser Microsoft Edge continuerà a partecipare all'offerta ESR.</span><span class="sxs-lookup"><span data-stu-id="608c7-163">The current version of Microsoft Edge browser will continue to participate in the ESR offering.</span></span>

#### <span data-ttu-id="608c7-164">Perché è necessario un abbonamento Premium ad Azure AD per la sincronizzazione?</span><span class="sxs-lookup"><span data-stu-id="608c7-164">Why do I need a premium Azure AD subscription to sync?</span></span>

<span data-ttu-id="608c7-165">La sincronizzazione aziendale dipende da Azure Information Protection, che non è disponibile in tutti i livelli di Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="608c7-165">Enterprise sync depends on Azure Information Protection, which is not available in all Azure AD tiers.</span></span>

#### <span data-ttu-id="608c7-166">La sincronizzazione di Microsoft Edge si basa sul servizio Enterprise State Roaming?</span><span class="sxs-lookup"><span data-stu-id="608c7-166">Is Microsoft Edge sync based on Enterprise State Roaming?</span></span>

<span data-ttu-id="608c7-167">No.</span><span class="sxs-lookup"><span data-stu-id="608c7-167">No.</span></span> <span data-ttu-id="608c7-168">ESR può essere usato per abilitare la sincronizzazione, tuttavia la sincronizzazione di Microsoft Edge non fa parte del servizio ESR.</span><span class="sxs-lookup"><span data-stu-id="608c7-168">ESR can be used to enable sync, but Microsoft Edge sync is not a part of ESR.</span></span> <span data-ttu-id="608c7-169">Per ulteriori informazioni, vedere [Sincronizzazione di Microsoft Edge](microsoft-edge-enterprise-sync.md) e [Microsoft Edge e Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md).</span><span class="sxs-lookup"><span data-stu-id="608c7-169">For more information, see [Microsoft Edge Sync](microsoft-edge-enterprise-sync.md) and [Microsoft Edge and Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md).</span></span>

#### <span data-ttu-id="608c7-170">Microsoft Edge supporterà mai la sincronizzazione tra Microsoft Edge e Internet Explorer?</span><span class="sxs-lookup"><span data-stu-id="608c7-170">Will Microsoft Edge ever support syncing between Microsoft Edge and IE?</span></span>

<span data-ttu-id="608c7-171">Non è previsto il supporto di questa sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="608c7-171">There are no plans to support this syncing.</span></span> <span data-ttu-id="608c7-172">Se è ancora necessario Internet Explorer nel proprio ambiente per supportare le app legacy, prendere in considerazione la [nuova modalità di IE](https://docs.microsoft.com/deployedge/edge-ie-mode).</span><span class="sxs-lookup"><span data-stu-id="608c7-172">If you still need IE in your environment to support legacy apps, consider our [new IE mode](https://docs.microsoft.com/deployedge/edge-ie-mode).</span></span>

#### <span data-ttu-id="608c7-173">Il nuovo browser Microsoft Edge verrà sincronizzato con la Versione legacy di Microsoft Edge?</span><span class="sxs-lookup"><span data-stu-id="608c7-173">Will the new Microsoft Edge browser sync with Microsoft Edge Legacy?</span></span>

<span data-ttu-id="608c7-174">No, non viene sincronizzato.</span><span class="sxs-lookup"><span data-stu-id="608c7-174">No, it won't.</span></span> <span data-ttu-id="608c7-175">Riteniamo che la connessione di questi due ecosistemi consente compromessi nell'affidabilità della sincronizzazione nel nuovo Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="608c7-175">We believe connecting these two ecosystems will lead to compromises in the reliability of sync in the new Microsoft Edge.</span></span> <span data-ttu-id="608c7-176">Garantiamo la migrazione dei dati esistenti al nuovo Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="608c7-176">We will ensure that existing data is migrated to the new Microsoft Edge.</span></span> <span data-ttu-id="608c7-177">Gli utenti saranno anche in grado di importare i dati dal browser che desiderano.</span><span class="sxs-lookup"><span data-stu-id="608c7-177">Users will also be able to import data from browser of their choice.</span></span> <span data-ttu-id="608c7-178">Questo significa anche che il nuovo browser Microsoft Edge non avrà un modo per eseguire la sincronizzazione con Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="608c7-178">This also means that new Microsoft Edge browser won't have a way to sync with IE.</span></span>

### <span data-ttu-id="608c7-179">GESTIONE DELLA SINCRONIZZAZIONE</span><span class="sxs-lookup"><span data-stu-id="608c7-179">MANAGING SYNC</span></span>

#### <span data-ttu-id="608c7-180">È possibile impedire agli utenti di eseguire la sincronizzazione con un tenant personale?</span><span class="sxs-lookup"><span data-stu-id="608c7-180">Is it possible to stop my users from syncing with a personal tenant?</span></span>

<span data-ttu-id="608c7-181">Non direttamente, ma è possibile determinare quali profili possono accedere a Microsoft Edge usando i criteri [RestrictSigninToPattern](https://docs.microsoft.com/deployedge/microsoft-edge-policies#restrictsignintopattern).</span><span class="sxs-lookup"><span data-stu-id="608c7-181">Not directly, but you can determine which profiles can sign on to Microsoft Edge using the [RestrictSigninToPattern](https://docs.microsoft.com/deployedge/microsoft-edge-policies#restrictsignintopattern) policy.</span></span>

## <span data-ttu-id="608c7-182">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="608c7-182">See also</span></span>

- [<span data-ttu-id="608c7-183">Pagina di destinazione di Microsoft Edge in modalità Enterprise</span><span class="sxs-lookup"><span data-stu-id="608c7-183">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="608c7-184">Microsoft Edge ed Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="608c7-184">Microsoft Edge and Enterprise State Roaming</span></span>](microsoft-edge-enterprise-state-roaming.md)
