---
title: Diagnosticare e risolvere i problemi di sincronizzazione di Microsoft Edge
ms.author: scottbo
author: dan-wesley
manager: silvanam
ms.date: 03/08/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Linee guida e strumenti che un amministratore di Microsoft Edge può usare per risolvere i problemi comuni di sincronizzazione aziendale
ms.openlocfilehash: 49fb0c5fc555e4f7ad4c728477387e931a5fbb5f
ms.sourcegitcommit: f363ceb6c42054fabc95ce8d7bca3c52d80e6a9f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "11447160"
---
# <a name="diagnose-and-fix-microsoft-edge-sync-issues"></a><span data-ttu-id="64dad-103">Diagnosticare e risolvere i problemi di sincronizzazione di Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="64dad-103">Diagnose and fix Microsoft Edge sync issues</span></span>

<span data-ttu-id="64dad-104">Questo articolo fornisce indicazioni per la risoluzione dei problemi di sincronizzazione più comuni in un ambiente Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="64dad-104">This article provides troubleshooting guidance for the most commonly encountered sync issues in an Azure Active Directory (Azure AD) environment.</span></span> <span data-ttu-id="64dad-105">Include anche gli strumenti consigliati per raccogliere i log necessari per la risoluzione di un problema di sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="64dad-105">It also includes the recommended tools for gathering the logs needed for troubleshooting a sync issue.</span></span>

<span data-ttu-id="64dad-106">Se un utente riscontra un problema durante la sincronizzazione dei dati del browser tra i dispositivi, può provare a [reimpostare la sincronizzazione.](edge-learnmore-reset-data-in-cloud.md) Se non funziona, gli amministratori o il personale di supporto possono usare le indicazioni seguenti per risolvere un problema di sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="64dad-106">If a user is experiencing an issue syncing browser data across their devices they can try [resetting sync](edge-learnmore-reset-data-in-cloud.md). If this doesn't work, admins or support staff can use the following guidance to fix a sync issue.</span></span>

> [!NOTE]
> <span data-ttu-id="64dad-107">Si applica a Microsoft Edge versione 77 o successiva, se non diversamente specificato.</span><span class="sxs-lookup"><span data-stu-id="64dad-107">Applies to Microsoft Edge version 77 or later unless otherwise noted.</span></span>

## <a name="identity-issues-versus-sync-issues"></a><span data-ttu-id="64dad-108">Problemi di identità e problemi di sincronizzazione</span><span class="sxs-lookup"><span data-stu-id="64dad-108">Identity issues versus sync issues</span></span>

<span data-ttu-id="64dad-109">Prima di iniziare, è importante comprendere la differenza tra problemi di identità e problemi di sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="64dad-109">Before you begin it's important to understand the difference between identity issues and sync issues.</span></span> <span data-ttu-id="64dad-110">Uno dei casi di utilizzo più diffusi per gestire l'identità degli utenti nel browser è supportare la sincronizzazione. Per questo motivo, i problemi di identità vengono spesso confusi con i problemi di sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="64dad-110">A popular use case for maintaining user identity in the browser is to support sync. For this reason, identity issues are frequently confused with sync issues.</span></span> <span data-ttu-id="64dad-111">Comprendere la differenza tra i problemi di identità e sincronizzazione prima di avviare la risoluzione dei problemi di sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="64dad-111">Understand the difference between identity and sync issue before you start troubleshooting sync.</span></span>

<span data-ttu-id="64dad-112">Prima di considerare un problema di sincronizzazione, verificare se l'utente ha eseguito l'accesso al browser con un account valido.</span><span class="sxs-lookup"><span data-stu-id="64dad-112">Before you treat an issue as a sync issue, check to see if the user is signed into the browser with a valid account.</span></span>

<span data-ttu-id="64dad-113">Nella schermata successiva viene illustrato un esempio di errore di identità.</span><span class="sxs-lookup"><span data-stu-id="64dad-113">The next screenshot shows an example of an identity error.</span></span> <span data-ttu-id="64dad-114">L'errore è "**errore token ultimo, EDGE_AUTH_ERROR: 3, 54, 3ea**", disponibile in *Edge://Sync-internals* in **Credenziali**:</span><span class="sxs-lookup"><span data-stu-id="64dad-114">The error is "**Last Token Error, EDGE_AUTH_ERROR: 3, 54, 3ea**", which is found in *edge://sync-internals* under **Credentials**:</span></span>

:::image type="content" source="media/microsoft-edge-enterprise-sync-configure-and-troubleshoot/sync-identity-issue.png" alt-text="Errore ultimo token EDGE_AUTH_ERROR: 3, 54, 3ea":::

## <a name="common-sync-issues"></a><span data-ttu-id="64dad-116">Problemi comuni di sincronizzazione</span><span class="sxs-lookup"><span data-stu-id="64dad-116">Common sync issues</span></span>

### <a name="issue-cant-access-m365-or-azure-information-protection-subscription"></a><span data-ttu-id="64dad-117">Problema: Non è possibile accedere all'abbonamento M365 o Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="64dad-117">Issue: Can't access M365 or Azure Information Protection subscription</span></span>

<span data-ttu-id="64dad-118">Se hai un precedente abbonamento M365 o Azure Information Protection (AIP) che abbia scaduto e sia stato sostituito con un nuovo abbonamento?</span><span class="sxs-lookup"><span data-stu-id="64dad-118">Do you have a previous M365 or Azure Information Protection (AIP) subscription that expired and then replaced with a new subscription?</span></span> <span data-ttu-id="64dad-119">In questo caso, l'ID tenant è cambiato e i dati del servizio devono essere reimpostati.</span><span class="sxs-lookup"><span data-stu-id="64dad-119">If so, then the tenant ID has changed and the service data needs to be reset.</span></span> <span data-ttu-id="64dad-120">Vedi le istruzioni per reimpostare i dati nel problema dell'**errore di Cryptographer riscontrato**.</span><span class="sxs-lookup"><span data-stu-id="64dad-120">See the instructions for resetting data in the **Cryptographer error encountered** issue.</span></span>

### <a name="issue-sync-is-not-available-for-this-account"></a><span data-ttu-id="64dad-121">Problema: "La sincronizzazione non è disponibile per questo account".</span><span class="sxs-lookup"><span data-stu-id="64dad-121">Issue: “Sync is not available for this account.”</span></span>

<span data-ttu-id="64dad-122">Se si verifica questo errore per un account di Azure Active Directory o se DISABLED_BY_ADMIN viene visualizzato in *edge://sync-internals*, seguire i passaggi della procedura successiva in sequenza fino a risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="64dad-122">If this error is encountered for an Azure Active Directory account, or if DISABLED_BY_ADMIN appears in *edge://sync-internals*, follow the steps in the next procedure sequentially until the problem is fixed.</span></span>

> [!NOTE]
> <span data-ttu-id="64dad-123">Poiché l'origine di questo errore è in genere una modifica della configurazione in un tenant di Azure Active Directory, questa procedura di risoluzione dei problemi può essere eseguita solo da un amministratore del tenant e non dagli utenti finali.</span><span class="sxs-lookup"><span data-stu-id="64dad-123">Because the source of this error is usually requires a configuration change in an Azure Active Directory tenant, these troubleshooting steps can only performed by a tenant admin and not by end users.</span></span>

1. <span data-ttu-id="64dad-124">Verifica che il tenant aziendale abbia un abbonamento M365 supportato.</span><span class="sxs-lookup"><span data-stu-id="64dad-124">Verify that the enterprise tenant has a supported M365 subscription.</span></span> <span data-ttu-id="64dad-125">L'elenco corrente dei tipi di abbonamento [disponibile qui](/azure/information-protection/activate-office365).</span><span class="sxs-lookup"><span data-stu-id="64dad-125">The current list of available subscription types is [provided here](/azure/information-protection/activate-office365).</span></span> <span data-ttu-id="64dad-126">Se il tenant non ha un abbonamento supportato, può acquistare Azure Information Protection separatamente oppure eseguire l'aggiornamento a uno degli abbonamenti supportati.</span><span class="sxs-lookup"><span data-stu-id="64dad-126">If the tenant doesn't have a supported subscription, they can either purchase Azure Information Protection separately, or upgrade to one of the supported subscriptions.</span></span>
2. <span data-ttu-id="64dad-127">Se è disponibile un abbonamento supportato, verifica che nel tenant sia disponibile Azure Information Protection (AIP).</span><span class="sxs-lookup"><span data-stu-id="64dad-127">If a supported subscription is available, verify that the tenant has Azure Information Protection (AIP) available.</span></span> <span data-ttu-id="64dad-128">Le istruzioni per controllare lo stato di AIP e, se necessario, attivare AIP sono disponibili [qui](/azure/information-protection/activate-office365).</span><span class="sxs-lookup"><span data-stu-id="64dad-128">The instructions for checking the AIP status and, if necessary, activating AIP are [here](/azure/information-protection/activate-office365).</span></span>
3. <span data-ttu-id="64dad-129">Se il passaggio 2 indica che AIP è attivo ma la sincronizzazione non funziona comunque, attiva Enterprise State Roaming (ESR).</span><span class="sxs-lookup"><span data-stu-id="64dad-129">If step 2 shows that AIP is active but sync still doesn't work, turn on Enterprise State Roaming (ESR).</span></span> <span data-ttu-id="64dad-130">Le istruzioni per l'abilitazione di ESR sono riportate [qui](/azure/active-directory/devices/enterprise-state-roaming-enable).</span><span class="sxs-lookup"><span data-stu-id="64dad-130">The instructions for enabling ESR are [here](/azure/active-directory/devices/enterprise-state-roaming-enable).</span></span> <span data-ttu-id="64dad-131">Tieni presente che ESR non deve rimanere in funzione.</span><span class="sxs-lookup"><span data-stu-id="64dad-131">Note that ESR does not need to stay on.</span></span> <span data-ttu-id="64dad-132">Puoi disattivare ESR se questo passaggio consente di risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="64dad-132">You can turn off ESR if this step fixes the issue.</span></span>
4. <span data-ttu-id="64dad-133">Verifica che l'ambito di Azure Information Protection non sia in base a un criterio di onboarding.</span><span class="sxs-lookup"><span data-stu-id="64dad-133">Confirm that Azure Information Protection is not scoped via an onboarding policy.</span></span> <span data-ttu-id="64dad-134">Puoi utilizzare l'applet di PowerShell [Get-AadrmOnboardingControlPolicy](/powershell/module/aadrm/get-aadrmonboardingcontrolpolicy?view=azureipps) per verificare se l'ambito è abilitato.</span><span class="sxs-lookup"><span data-stu-id="64dad-134">You can use the [Get-AadrmOnboardingControlPolicy](/powershell/module/aadrm/get-aadrmonboardingcontrolpolicy?view=azureipps) PowerShell applet to see if scoping is enabled.</span></span> <span data-ttu-id="64dad-135">I due esempi seguenti mostrano una configurazione senza ambito e una configurazione che ha come ambito un gruppo di sicurezza specifico.</span><span class="sxs-lookup"><span data-stu-id="64dad-135">The next two examples show an unscoped configuration and a configuration scoped to a specific security group.</span></span>

   ```powershell
    PS C:\Work\scripts\PowerShell> Get-AadrmOnboardingControlPolicy
 
    UseRmsUserLicense SecurityGroupObjectId                Scope
    ----------------- ---------------------                -----
                False 
   ```

   ```powershell

    PS C:\Work\scripts\PowerShell> Get-AadrmOnboardingControlPolicy
 
    UseRmsUserLicense SecurityGroupObjectId                Scope
    ----------------- ---------------------                -----
                False f1488a05-8196-40a6-9483-524948b90282   All
   ```

   <span data-ttu-id="64dad-136">Se l'ambito è abilitato, l'utente interessato deve essere aggiunto al gruppo di sicurezza per l'ambito oppure l'ambito deve essere rimosso.</span><span class="sxs-lookup"><span data-stu-id="64dad-136">If scoping is enabled, the affected user should either be added to the security group for the scope, or the scope should be removed.</span></span> <span data-ttu-id="64dad-137">Nell'esempio seguente l'ambito del processo di onboarding è AIP nel gruppo di sicurezza indicato e l'ambito deve essere rimosso con l'applet PowerShell[Set-AadrmOnboardingControlPolicy](/powershell/module/aadrm/set-aadrmonboardingcontrolpolicy?view=azureipps).</span><span class="sxs-lookup"><span data-stu-id="64dad-137">In the example below, onboarding has scoped AIP to the indicated security group and the scoping should be removed with the [Set-AadrmOnboardingControlPolicy](/powershell/module/aadrm/set-aadrmonboardingcontrolpolicy?view=azureipps) PowerShell applet.</span></span>

5. <span data-ttu-id="64dad-138">Verifica che IPCv3Service sia attivato nel tenant.</span><span class="sxs-lookup"><span data-stu-id="64dad-138">Confirm that the IPCv3Service is turned on in the tenant.</span></span> <span data-ttu-id="64dad-139">L’applet di Powersell[Get-AadrmConfiguration](/powershell/module/aadrm/get-aadrmconfiguration?view=azureipps) mostra lo stato del servizio.</span><span class="sxs-lookup"><span data-stu-id="64dad-139">The [Get-AadrmConfiguration](/powershell/module/aadrm/get-aadrmconfiguration?view=azureipps)  PowerShell applet shows the status of the service.</span></span>

   :::image type="content" source="media/microsoft-edge-enterprise-sync-configure-and-troubleshoot/sync-scoped-cfg-example.png" alt-text="Verificare se IPCv3Service è abilitato.":::

6. <span data-ttu-id="64dad-141">Se il problema persiste, contattare il [supporto Microsoft Edge](https://www.microsoftedgeinsider.com/support).</span><span class="sxs-lookup"><span data-stu-id="64dad-141">If the issue isn't fixed, contact [Microsoft Edge support](https://www.microsoftedgeinsider.com/support).</span></span>

### <a name="issue-stuck-at-setting-up-sync-or-couldnt-connect-to-the-sync-server-retrying"></a><span data-ttu-id="64dad-142">Problema: Bloccato a “Configurazione della sincronizzazione in corso...” o "Non è possibile connettersi al server di sincronizzazione”.</span><span class="sxs-lookup"><span data-stu-id="64dad-142">Issue: Stuck at "Setting up sync..." or “Couldn’t connect to the sync server.</span></span> <span data-ttu-id="64dad-143">Riprova</span><span class="sxs-lookup"><span data-stu-id="64dad-143">Retrying…”</span></span>

1. <span data-ttu-id="64dad-144">Disconnettersi e quindi accedere nuovamente.</span><span class="sxs-lookup"><span data-stu-id="64dad-144">Try to sign out and then sign in.</span></span>
2. <span data-ttu-id="64dad-145">Passa a *edge://sync-internals*.</span><span class="sxs-lookup"><span data-stu-id="64dad-145">Go to *edge://sync-internals*.</span></span> <span data-ttu-id="64dad-146">Se nella sezione "**Digita info**" è presente l'errore seguente, passa al problema seguente problema **errore di Cryptographer rilevato**.</span><span class="sxs-lookup"><span data-stu-id="64dad-146">If under the "**Type info**" section the following error is present, then  skip to the following issue, **Cryptographer error encountered**.</span></span>

   `"Error:GenerateCryptoErrorsForTypes@../../components/sync/driver/data_type_manager_impl.cc:42, cryptographer error was encountered"`

3. <span data-ttu-id="64dad-147">Provare a effettuare il ping all'endpoint del server.</span><span class="sxs-lookup"><span data-stu-id="64dad-147">Try pinging the server endpoint.</span></span> <span data-ttu-id="64dad-148">L'endpoint server per un client è disponibile in *edge://sync-internals*.</span><span class="sxs-lookup"><span data-stu-id="64dad-148">The server endpoint for a client is available in *edge://sync-internals*.</span></span> <span data-ttu-id="64dad-149">Lo screenshot successivo mostra le informazioni sull'endpoint in **Informazioni dell’ambiente**.</span><span class="sxs-lookup"><span data-stu-id="64dad-149">The next screenshot shows endpoint information under **Environment Info**.</span></span>

   :::image type="content" source="media/microsoft-edge-enterprise-sync-configure-and-troubleshoot/sync-endpoint-info.png" alt-text="Informazioni sull'endpoint":::

4. <span data-ttu-id="64dad-151">Se l'endpoint del server è vuoto o se non è possibile effettuare il ping al server e nell'ambiente è presente un firewall, verificare che gli endpoint del servizio necessari siano disponibili per il computer client.</span><span class="sxs-lookup"><span data-stu-id="64dad-151">If the server endpoint is empty, or if server cannot be pinged and a firewall is present in the environment, confirm that the necessary service endpoints are available to the client computer.</span></span>

   - <span data-ttu-id="64dad-152">Endpoint del servizio di sincronizzazione Microsoft Edge:</span><span class="sxs-lookup"><span data-stu-id="64dad-152">Microsoft Edge sync service endpoints:</span></span>
     - [https://edge-enterprise.activity.windows.com](https://edge-enterprise.activity.windows.com)
     - [https://edge.activity.windows.com](https://edge.activity.windows.com)
    - <span data-ttu-id="64dad-153">Endpoint di Azure Information Protection:</span><span class="sxs-lookup"><span data-stu-id="64dad-153">Azure Information Protection endpoints:</span></span>
      - <span data-ttu-id="64dad-154">[https://api.aadrm.com](https://api.aadrm.com) (per la maggior parte dei tenant)</span><span class="sxs-lookup"><span data-stu-id="64dad-154">[https://api.aadrm.com](https://api.aadrm.com) (for most tenants)</span></span>
      - <span data-ttu-id="64dad-155">[https://api.aadrm.de](https://api.aadrm.de) (per i tenant in Germania)</span><span class="sxs-lookup"><span data-stu-id="64dad-155">[https://api.aadrm.de](https://api.aadrm.de) (for tenants in Germany)</span></span>
      - <span data-ttu-id="64dad-156">[https://api.aadrm.cn](https://api.aadrm.cn) (per i tenant in Cina)</span><span class="sxs-lookup"><span data-stu-id="64dad-156">[https://api.aadrm.cn](https://api.aadrm.cn) (for tenants in China)</span></span>
   - <span data-ttu-id="64dad-157">[Endpoint del servizio di notifica di Windows](/windows/uwp/design/shell/tiles-and-notifications/firewall-allowlist-config).</span><span class="sxs-lookup"><span data-stu-id="64dad-157">[Windows Notification Service endpoints](/windows/uwp/design/shell/tiles-and-notifications/firewall-allowlist-config).</span></span>

5. <span data-ttu-id="64dad-158">Se il problema persiste, contatta il [supporto di Microsoft Edge](https://www.microsoftedgeinsider.com/support).</span><span class="sxs-lookup"><span data-stu-id="64dad-158">If the issue still isn't fixed, contact [Microsoft Edge support](https://www.microsoftedgeinsider.com/support).</span></span>

### <a name="issue-cryptographer-error-encountered"></a><span data-ttu-id="64dad-159">Problema: Errore di Cryptographer rilevato</span><span class="sxs-lookup"><span data-stu-id="64dad-159">Issue: Cryptographer error encountered</span></span>

<span data-ttu-id="64dad-160">Questo errore è visibile in **Digita informazione** in *edge://sync-internals* e può significare che i dati sul lato del servizio dell'utente devono essere reimpostati.</span><span class="sxs-lookup"><span data-stu-id="64dad-160">This error is visible under **Type info** in *edge://sync-internals* and may mean that the user's service side data needs to be reset.</span></span> <span data-ttu-id="64dad-161">L'esempio seguente mostra un messaggio di errore di crittografia:</span><span class="sxs-lookup"><span data-stu-id="64dad-161">The following example shows a cryptography error message:</span></span>
<br><span data-ttu-id="64dad-162">"Errore: GenerateCryptoErrorsForTypes@.. /.. /Components/Sync/driver/data_type_manager_impl. cc: 42, si è verificato un errore di crittografia".</span><span class="sxs-lookup"><span data-stu-id="64dad-162">"Error:GenerateCryptoErrorsForTypes@../../components/sync/driver/data_type_manager_impl.cc:42, cryptographer error was encountered".</span></span>

1. <span data-ttu-id="64dad-163">Riavvia Microsoft Edge e passa alla *edge://sync-internals* e controlla la sezione "**Stato della chiave dell'account AAD**"</span><span class="sxs-lookup"><span data-stu-id="64dad-163">Restart Microsoft Edge and navigate to *edge://sync-internals* and check the “**AAD Account Key Status**” section</span></span>
   - <span data-ttu-id="64dad-164">"Success" in "Last MIP Result": l'errore del crittografo indica che i dati del server potrebbero essere stati crittografati con una chiave persa.</span><span class="sxs-lookup"><span data-stu-id="64dad-164">"Success" in "Last MIP Result": the cryptographer error means server data might be encrypted with a lost key.</span></span> <span data-ttu-id="64dad-165">La reimpostazione dei dati è necessaria per riprendere la sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="64dad-165">Data reset is needed to resume sync.</span></span>
   - <span data-ttu-id="64dad-166">"Nessuna autorizzazione" in "Ultimo risultato MIP": la causa potrebbe essere una modifica di Azure AD o una modifica all’abbonamento del tenant.</span><span class="sxs-lookup"><span data-stu-id="64dad-166">"No permissions" in "Last MIP Result": It is possibly caused by an Azure AD change or tenant subscription changes.</span></span> <span data-ttu-id="64dad-167">La reimpostazione dei dati è necessaria per riprendere la sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="64dad-167">Data reset is needed to resume sync.</span></span>
   - <span data-ttu-id="64dad-168">Altri errori possono significare problemi di configurazione del server.</span><span class="sxs-lookup"><span data-stu-id="64dad-168">Other errors may mean server configuration issues.</span></span>
2. <span data-ttu-id="64dad-169">Se è necessaria la reimpostazione dei dati, vedi i [Dati di Microsoft Edge nel cloud](edge-learnmore-reset-data-in-cloud.md).</span><span class="sxs-lookup"><span data-stu-id="64dad-169">If data reset is needed, see [Reset Microsoft Edge data in the cloud](edge-learnmore-reset-data-in-cloud.md).</span></span>

### <a name="issue-sync-has-been-turned-off-by-your-administrator"></a><span data-ttu-id="64dad-170">Problema: "La sincronizzazione è stata disattivata dall'amministratore".</span><span class="sxs-lookup"><span data-stu-id="64dad-170">Issue: “Sync has been turned off by your administrator.”</span></span>

<span data-ttu-id="64dad-171">Assicurarsi che non sia impostato il [criterio SyncDisabled](./microsoft-edge-policies.md#syncdisabled).</span><span class="sxs-lookup"><span data-stu-id="64dad-171">Make sure that the [SyncDisabled policy](./microsoft-edge-policies.md#syncdisabled)  is not set.</span></span>

## <a name="see-also"></a><span data-ttu-id="64dad-172">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="64dad-172">See also</span></span>

- [<span data-ttu-id="64dad-173">Sincronizzazione di Microsoft Edge in modalità Enterprise</span><span class="sxs-lookup"><span data-stu-id="64dad-173">Microsoft Edge Enterprise Sync</span></span>](microsoft-edge-enterprise-sync.md)
- [<span data-ttu-id="64dad-174">Microsoft Edge ed Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="64dad-174">Microsoft Edge and Enterprise State Roaming</span></span>](microsoft-edge-enterprise-state-roaming.md)
- [<span data-ttu-id="64dad-175">Pagina di destinazione di Microsoft Edge in modalità Enterprise</span><span class="sxs-lookup"><span data-stu-id="64dad-175">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)