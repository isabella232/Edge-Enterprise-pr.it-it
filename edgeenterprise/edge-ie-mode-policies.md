---
title: Configurare i criteri della modalità IE
ms.author: cjacks
author: cjacks
manager: saudm
ms.date: 03/25/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Configurare i criteri della modalità IE
ms.openlocfilehash: 2d2ded3a3fb338bdf2d815d681b52249007945ac
ms.sourcegitcommit: 4edbe2fc2fc9a013e6a0245aba485fcc5905539b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2020
ms.locfileid: "10980170"
---
# <span data-ttu-id="dc96a-103">Configurare i criteri della modalità IE</span><span class="sxs-lookup"><span data-stu-id="dc96a-103">Configure IE mode policies</span></span>

<span data-ttu-id="dc96a-104">Questo articolo spiega come configurare i criteri della modalità IE.</span><span class="sxs-lookup"><span data-stu-id="dc96a-104">This article explains how to configure IE mode policies.</span></span>

> [!NOTE]
> <span data-ttu-id="dc96a-105">Questo articolo si applica ai canali Microsoft Edge **Stable**, **Beta** e **Dev**, versione 77 o successiva.</span><span class="sxs-lookup"><span data-stu-id="dc96a-105">This article applies to Microsoft Edge **Stable**, **Beta** and **Dev** Channels, version 77 or later.</span></span>

<span data-ttu-id="dc96a-106">La configurazione della modalità IE richiede tre passaggi:</span><span class="sxs-lookup"><span data-stu-id="dc96a-106">Configuring IE mode requires three steps:</span></span>

1. [<span data-ttu-id="dc96a-107">Configurare l'integrazione Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="dc96a-107">Configure Internet Explorer integration</span></span>](#configure-internet-explorer-integration)
2. [<span data-ttu-id="dc96a-108">Reindirizzare i siti da Microsoft Edge alla modalità IE</span><span class="sxs-lookup"><span data-stu-id="dc96a-108">Redirect sites from Microsoft Edge to IE mode</span></span>](#redirect-sites-from-microsoft-edge-to-ie-mode)
3. <span data-ttu-id="dc96a-109">[Reindirizzare i siti da IE a Microsoft Edge](#redirect-sites-from-ie-to-microsoft-edge) (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="dc96a-109">(Optional) [Redirect sites from IE to Microsoft Edge](#redirect-sites-from-ie-to-microsoft-edge)</span></span>

> [!NOTE]
> <span data-ttu-id="dc96a-110">I criteri per abilitare la modalità Internet Explorer possono essere configurati con Intune.</span><span class="sxs-lookup"><span data-stu-id="dc96a-110">Policies to enable IE mode can be configured through Intune.</span></span> <span data-ttu-id="dc96a-111">Per altre informazioni, vedere [Aggiungere Microsoft Edge a Microsoft Intune](https://docs.microsoft.com/intune/apps/apps-windows-edge?toc=https://docs.microsoft.com/DeployEdge/toc.json&bc=https://docs.microsoft.com/DeployEdge/breadcrumb/toc.json) e [Configurare i criteri Microsoft Edge con Microsoft Intune](https://docs.microsoft.com/DeployEdge/configure-edge-with-intune).</span><span class="sxs-lookup"><span data-stu-id="dc96a-111">For more information, see [Add Microsoft Edge to Microsoft Intune](https://docs.microsoft.com/intune/apps/apps-windows-edge?toc=https://docs.microsoft.com/DeployEdge/toc.json&bc=https://docs.microsoft.com/DeployEdge/breadcrumb/toc.json) and [Configure Microsoft Edge policies with Microsoft Intune](https://docs.microsoft.com/DeployEdge/configure-edge-with-intune).</span></span>

## <span data-ttu-id="dc96a-112">Configurare l'integrazione Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="dc96a-112">Configure Internet Explorer integration</span></span>

<span data-ttu-id="dc96a-113">È possibile configurare Internet Explorer in modo che venga aperto direttamente all'interno di Microsoft Edge (modalità IE).</span><span class="sxs-lookup"><span data-stu-id="dc96a-113">You can configure Internet Explorer to open directly within Microsoft Edge (IE mode).</span></span> <span data-ttu-id="dc96a-114">È anche possibile configurare Internet Explorer in modo che venga aperto con una finestra autonoma di Internet Explorer 11.</span><span class="sxs-lookup"><span data-stu-id="dc96a-114">You can also configure Internet Explorer to open with a standalone Internet Explorer 11 window.</span></span> <span data-ttu-id="dc96a-115">La maggior parte degli utenti preferisce l'opzione che consente di aprire i siti direttamente all'interno di Microsoft Edge in modalità IE.</span><span class="sxs-lookup"><span data-stu-id="dc96a-115">Most users prefer when sites open directly within Microsoft Edge in IE mode.</span></span>

### <span data-ttu-id="dc96a-116">Abilitare l'integrazione Internet Explorer con Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="dc96a-116">Enable Internet Explorer integration using Group Policy</span></span>

1. <span data-ttu-id="dc96a-117">Scarica e usa il [modello di criteri di Microsoft Edge](https://www.microsoft.com/en-us/edge/business/download) più recente.</span><span class="sxs-lookup"><span data-stu-id="dc96a-117">Download and use the latest [Microsoft Edge Policy Template](https://www.microsoft.com/en-us/edge/business/download).</span></span>
2. <span data-ttu-id="dc96a-118">Apri Editor Criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="dc96a-118">Open Group Policy Editor.</span></span>
3. <span data-ttu-id="dc96a-119">Fai clic su **Configurazione computer** > **Modelli amministrativi** > **Microsoft Edge**.</span><span class="sxs-lookup"><span data-stu-id="dc96a-119">Click **Computer Configuration** > **Administrative Templates** > **Microsoft Edge**.</span></span>
4. <span data-ttu-id="dc96a-120">Fai doppio clic su **Configura integrazione Internet Explorer**.</span><span class="sxs-lookup"><span data-stu-id="dc96a-120">Double-click **Configure Internet Explorer integration**.</span></span>
5. <span data-ttu-id="dc96a-121">Seleziona **Attivata**.</span><span class="sxs-lookup"><span data-stu-id="dc96a-121">Select **Enabled**.</span></span>
6. <span data-ttu-id="dc96a-122">In **Opzioni** impostare il valore del menu a discesa su</span><span class="sxs-lookup"><span data-stu-id="dc96a-122">Under **Options**, set the dropdown value to</span></span> 
   -  <span data-ttu-id="dc96a-123">**Modalità Internet Explorer** se si vuole che i siti vengano aperti in modalità IE su Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="dc96a-123">**Internet Explorer mode** if you want sites to open in IE mode on Microsoft Edge</span></span>
   -  <span data-ttu-id="dc96a-124">**Internet Explorer 11** se si vuole che i siti vengano aperti in una finestra di Internet Explorer 11 autonoma</span><span class="sxs-lookup"><span data-stu-id="dc96a-124">**Internet Explorer 11** if you want sites to open in a standalone Internet Explorer 11 window</span></span>
   -  <span data-ttu-id="dc96a-125">**Nessuno** se si desidera impedire agli utenti di configurare la modalità Internet Explorer tramite edge://flags o la riga di comando</span><span class="sxs-lookup"><span data-stu-id="dc96a-125">**None** if you want to stop users from configuring Internet Explorer mode via edge://flags or through the command line</span></span>

   > [!NOTE]
   > <span data-ttu-id="dc96a-126">Se si impostano i criteri su **Disabilitato** la modalità Internet Explorer è disabilitata in base ai criteri, ma può essere impostata tramite edge://flags o le opzioni della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="dc96a-126">Setting the policy to **Disabled** implies IE mode is disabled by policy, but can be set through edge://flags or command line options.</span></span>
7. <span data-ttu-id="dc96a-127">Fai clic su **OK** o su **Applica** per salvare questa impostazione.</span><span class="sxs-lookup"><span data-stu-id="dc96a-127">Click **OK** or **Apply** to save this policy setting.</span></span>

## <span data-ttu-id="dc96a-128">Reindirizzare i siti da Microsoft Edge alla modalità IE</span><span class="sxs-lookup"><span data-stu-id="dc96a-128">Redirect sites from Microsoft Edge to IE mode</span></span>

<span data-ttu-id="dc96a-129">Sono disponibili due opzioni per identificare i siti che devono essere aperti in modalità IE:</span><span class="sxs-lookup"><span data-stu-id="dc96a-129">There are two options for identifying which sites should open in IE mode:</span></span>

- <span data-ttu-id="dc96a-130">(Consigliato) [Configurare i siti nell'elenco di siti in modalità Enterprise](#configure-sites-on-the-enterprise-site-list)</span><span class="sxs-lookup"><span data-stu-id="dc96a-130">(Recommended) [Configure sites on the Enterprise Site list](#configure-sites-on-the-enterprise-site-list)</span></span>
- [<span data-ttu-id="dc96a-131">Configurare tutti i siti Intranet</span><span class="sxs-lookup"><span data-stu-id="dc96a-131">Configure all Intranet sites</span></span>](#configure-all-intranet-sites)

### <span data-ttu-id="dc96a-132">Configurare i siti nell'elenco di siti in modalità Enterprise</span><span class="sxs-lookup"><span data-stu-id="dc96a-132">Configure sites on the Enterprise Site list</span></span>

<span data-ttu-id="dc96a-133">Puoi usare i seguenti criteri di gruppo per configurare siti specifici da aprire in modalità Internet Explorer:</span><span class="sxs-lookup"><span data-stu-id="dc96a-133">You can use the following group policies to configure specific sites to open in IE mode:</span></span>

- <span data-ttu-id="dc96a-134">[Usa elenco siti Web di Internet Explorer modalità Enterprise](#configure-using-the-use-the-enterprise-mode-ie-website-list-policy) (Internet Explorer)</span><span class="sxs-lookup"><span data-stu-id="dc96a-134">[Use the Enterprise Mode IE website list](#configure-using-the-use-the-enterprise-mode-ie-website-list-policy) (Internet Explorer)</span></span>
- <span data-ttu-id="dc96a-135">[Configura elenco siti modalità Enterprise](#configure-using-the-configure-the-enterprise-mode-site-list-policy) (Microsoft Edge, versione 78 o successiva)</span><span class="sxs-lookup"><span data-stu-id="dc96a-135">[Configure the Enterprise Mode Site List](#configure-using-the-configure-the-enterprise-mode-site-list-policy) (Microsoft Edge, version 78 or later)</span></span><br/><span data-ttu-id="dc96a-136">Questi criteri consentono di creare un elenco di siti in modalità Enterprise separati per Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="dc96a-136">This policy lets you create a separate Enterprise Mode Site list for Microsoft Edge.</span></span> <span data-ttu-id="dc96a-137">L'abilitazione di questo criterio sovrascrive le impostazioni nel criterio "Usa elenco siti Web di Internet Explorer modalità Enterprise", purché "Configura integrazione Internet Explorer" sia abilitato.</span><span class="sxs-lookup"><span data-stu-id="dc96a-137">Enabling this policy overrides the settings in the "Use the Enterprise Mode IE website list" policy, if "Configure Internet Explorer integration" is enabled.</span></span> <span data-ttu-id="dc96a-138">La disabilitazione o la configurazione di questo criterio non influisce sul comportamento predefinito del criterio "Configura integrazione Internet Explorer".</span><span class="sxs-lookup"><span data-stu-id="dc96a-138">Disabling or not configuring this policy doesn't affect the default behavior of the "Configure Internet Explorer integration" policy.</span></span>
    > [!NOTE]
    > <span data-ttu-id="dc96a-139">Non è obbligatorio configurare il criterio di Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="dc96a-139">It is not mandatory to configure the Microsoft Edge policy.</span></span> <span data-ttu-id="dc96a-140">Molte organizzazioni usano questo criterio come override per indirizzare l'elenco di siti corrente a tutti gli utenti con il criterio di IE e per inoltrare più facilmente una versione aggiornata agli utenti pilota con il criterio di Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="dc96a-140">Many organizations use this as an override, allowing them to target the current Site List at all users with the IE policy, and more easily target an updated version to pilot uses with the Microsoft Edge policy.</span></span>

<span data-ttu-id="dc96a-141">Per altre informazioni sull'elenco di siti per la modalità Enterprise, vedi:</span><span class="sxs-lookup"><span data-stu-id="dc96a-141">For more information about Enterprise Mode Site lists, see:</span></span>

- [<span data-ttu-id="dc96a-142">Usare Enterprise Mode Site List Manager</span><span class="sxs-lookup"><span data-stu-id="dc96a-142">Use the Enterprise Mode Site List Manager</span></span>](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/use-the-enterprise-mode-site-list-manager)
- <span data-ttu-id="dc96a-143">[Aggiungere più siti all'elenco dei siti per la modalità Enterprise tramite un file ed Enterprise Mode Site List Manager (schema v.2)](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/add-multiple-sites-to-enterprise-mode-site-list-using-the-version-2-schema-and-enterprise-mode-tool).</span><span class="sxs-lookup"><span data-stu-id="dc96a-143">[Add multiple sites to the Enterprise Mode site list using a file and the Enterprise Mode Site List Manager (schema v.2)](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/add-multiple-sites-to-enterprise-mode-site-list-using-the-version-2-schema-and-enterprise-mode-tool).</span></span>

### <span data-ttu-id="dc96a-144">Configurare tramite il criterio Usa elenco siti Web di Internet Explorer modalità Enterprise</span><span class="sxs-lookup"><span data-stu-id="dc96a-144">Configure using the Use the Enterprise Mode IE website list policy</span></span>

<span data-ttu-id="dc96a-145">La modalità IE può usare il criterio esistente configurando l'elenco di siti in modalità Enterprise per Internet Explorer, che consente di creare e gestire un unico elenco.</span><span class="sxs-lookup"><span data-stu-id="dc96a-145">IE mode can use the existing policy configuring the Enterprise Site List for Internet Explorer, allowing you to create and maintain a single list.</span></span>

1. <span data-ttu-id="dc96a-146">Creare o usare nuovamente un file XML dell'elenco di siti</span><span class="sxs-lookup"><span data-stu-id="dc96a-146">Create or reuse a Site List XML</span></span>
    1. <span data-ttu-id="dc96a-147">Tutti i siti che contengono l'elemento _\<open-in\>IE11\</open-in\>_ ora si apriranno in modalità di Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="dc96a-147">All sites that have the element _\<open-in\>IE11\</open-in\>_ will now open in IE mode.</span></span>
2. <span data-ttu-id="dc96a-148">Apri Editor Criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="dc96a-148">Open Group Policy Editor.</span></span>
3. <span data-ttu-id="dc96a-149">Fai clic su **Configurazione computer** > **Modelli amministrativi** > **Componenti di Windows** > **Internet Explorer**.</span><span class="sxs-lookup"><span data-stu-id="dc96a-149">Click **Computer Configuration** > **Administrative Templates** > **Windows Components** > **Internet Explorer**.</span></span>
4. <span data-ttu-id="dc96a-150">Fai doppio clic su **Usa elenco siti Web di Internet Explorer modalità Enterprise**.</span><span class="sxs-lookup"><span data-stu-id="dc96a-150">Double-click **Use the Enterprise Mode IE website list**.</span></span>
5. <span data-ttu-id="dc96a-151">Seleziona **Attivata**.</span><span class="sxs-lookup"><span data-stu-id="dc96a-151">Select **Enabled**.</span></span>
6. <span data-ttu-id="dc96a-152">In **Opzioni**, digita il percorso dell'elenco di siti Web.</span><span class="sxs-lookup"><span data-stu-id="dc96a-152">Under **Options**, type the location of website list.</span></span> <span data-ttu-id="dc96a-153">Puoi usare uno dei percorsi seguenti:</span><span class="sxs-lookup"><span data-stu-id="dc96a-153">You can use one of the following locations:</span></span>
    - <span data-ttu-id="dc96a-154">Percorso HTTPS: **https**:**//iemode/sites.xml** (scelta consigliata)</span><span class="sxs-lookup"><span data-stu-id="dc96a-154">(Recommended) HTTPS location: **https**:**//iemode/sites.xml**</span></span>
    - <span data-ttu-id="dc96a-155">File di rete locale: **\\\network\shares\sites.xml**</span><span class="sxs-lookup"><span data-stu-id="dc96a-155">Local network file: **\\\network\shares\sites.xml**</span></span>
    - <span data-ttu-id="dc96a-156">File locale: **file:///c:/Users/\<user\>/Documents/sites.xml**</span><span class="sxs-lookup"><span data-stu-id="dc96a-156">Local file: **file:///c:/Users/\<user\>/Documents/sites.xml**</span></span>
7. <span data-ttu-id="dc96a-157">Fai clic su **OK** o su **Applica** per salvare queste impostazioni.</span><span class="sxs-lookup"><span data-stu-id="dc96a-157">Click **OK** or **Apply** to save these settings.</span></span>

### <span data-ttu-id="dc96a-158">Configurare tramite il criterio Configura elenco siti modalità Enterprise</span><span class="sxs-lookup"><span data-stu-id="dc96a-158">Configure using the Configure the Enterprise Mode Site List policy</span></span>

<span data-ttu-id="dc96a-159">È anche possibile configurare la modalità IE con un criterio separato per Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="dc96a-159">You can also configure IE mode with a separate policy for Microsoft Edge.</span></span> <span data-ttu-id="dc96a-160">Questo criterio aggiuntivo consente di eseguire l'override dell'elenco di siti IE.</span><span class="sxs-lookup"><span data-stu-id="dc96a-160">This additional policy allows you to override the IE site list.</span></span> <span data-ttu-id="dc96a-161">Ad esempio, alcune organizzazioni indirizzano l'elenco di siti di produzione a tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="dc96a-161">For example, some organizations will target the production site list to all users.</span></span> <span data-ttu-id="dc96a-162">È quindi possibile distribuire l'elenco di siti pilota a un piccolo gruppo di utenti con questo criterio.</span><span class="sxs-lookup"><span data-stu-id="dc96a-162">You can then deploy the pilot site list to a small group of users using this policy.</span></span>

1. <span data-ttu-id="dc96a-163">Creare o usare nuovamente un file XML dell'elenco di siti</span><span class="sxs-lookup"><span data-stu-id="dc96a-163">Create or reuse a Site List XML</span></span>
    1. <span data-ttu-id="dc96a-164">Tutti i siti che contengono l'elemento _\<open-in\>IE11\</open-in\>_ ora si apriranno in modalità di Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="dc96a-164">All sites that have the element _\<open-in\>IE11\</open-in\>_ will now open in IE mode.</span></span>
2. <span data-ttu-id="dc96a-165">Apri Editor Criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="dc96a-165">Open Group Policy Editor.</span></span>
3. <span data-ttu-id="dc96a-166">Fai clic su **Configurazione computer** > **Modelli amministrativi** > **Microsoft Edge**.</span><span class="sxs-lookup"><span data-stu-id="dc96a-166">Click **Computer Configuration** > **Administrative Templates** > **Microsoft Edge**.</span></span>
4. <span data-ttu-id="dc96a-167">Fai doppio clic su **Configura elenco siti modalità Enterprise**.</span><span class="sxs-lookup"><span data-stu-id="dc96a-167">Double-click **Configure the Enterprise Mode Site List**.</span></span>
5. <span data-ttu-id="dc96a-168">Seleziona **Attivata**.</span><span class="sxs-lookup"><span data-stu-id="dc96a-168">Select **Enabled**.</span></span>
6. <span data-ttu-id="dc96a-169">In **Opzioni**, digita il percorso dell'elenco di siti Web.</span><span class="sxs-lookup"><span data-stu-id="dc96a-169">Under **Options**, type the location of website list.</span></span> <span data-ttu-id="dc96a-170">Puoi usare uno dei percorsi seguenti:</span><span class="sxs-lookup"><span data-stu-id="dc96a-170">You can use one of the following locations:</span></span>
    - <span data-ttu-id="dc96a-171">Percorso HTTPS: **https**:**//iemode/sites.xml** (scelta consigliata)</span><span class="sxs-lookup"><span data-stu-id="dc96a-171">(Recommended) HTTPS location: **https**:**//iemode/sites.xml**</span></span> <!--Trying to keep this from being an active link in MD -->
    - <span data-ttu-id="dc96a-172">File di rete locale: **\\\network\shares\sites.xml**</span><span class="sxs-lookup"><span data-stu-id="dc96a-172">Local network file: **\\\network\shares\sites.xml**</span></span>
    - <span data-ttu-id="dc96a-173">File locale: **file:///c:/Users/\<user\>/Documents/sites.xml**</span><span class="sxs-lookup"><span data-stu-id="dc96a-173">Local file: **file:///c:/Users/\<user\>/Documents/sites.xml**</span></span>
7. <span data-ttu-id="dc96a-174">Fai clic su **OK** o su **Applica** per salvare queste impostazioni.</span><span class="sxs-lookup"><span data-stu-id="dc96a-174">Click **OK** or **Apply** to save these settings.</span></span>

### <span data-ttu-id="dc96a-175">Configurare tutti i siti Intranet</span><span class="sxs-lookup"><span data-stu-id="dc96a-175">Configure all intranet sites</span></span>

<span data-ttu-id="dc96a-176">La modalità IE può essere configurata come tutti i siti nella zona dell'area Intranet locale.</span><span class="sxs-lookup"><span data-stu-id="dc96a-176">IE mode can be configured as for all sites in the Local Intranet zone.</span></span> <span data-ttu-id="dc96a-177">È possibile rimuovere singoli siti dalla modalità IE con un elenco di siti in modalità Enterprise.</span><span class="sxs-lookup"><span data-stu-id="dc96a-177">You can remove individual sites from IE mode using an Enterprise Mode Site List.</span></span>

>[!NOTE]
>
> <span data-ttu-id="dc96a-178">L'area Intranet locale contiene siti aggiunti esplicitamente, ma è anche possibile assegnare i siti a questa area usando l'euristica.</span><span class="sxs-lookup"><span data-stu-id="dc96a-178">The Local Intranet zone contains explicitly added sites, but also assigns sites to this zone using heuristics.</span></span> <span data-ttu-id="dc96a-179">Possono essere inclusi nomi host senza punto (ad esempio, **https**:**//payroll**) e i siti che lo script di configurazione del proxy configura per ignorare il proxy.</span><span class="sxs-lookup"><span data-stu-id="dc96a-179">This can include dotless host names (e.g. **https**:**//payroll**) and sites that the proxy configuration script configures to bypass the proxy.</span></span> <span data-ttu-id="dc96a-180">Se una parte esterna controlla il DNS o il proxy, potrebbe forzare i siti Web in modalità IE.</span><span class="sxs-lookup"><span data-stu-id="dc96a-180">If an external party controls DNS or proxy, they could potentially force websites into IE mode.</span></span>

1. <span data-ttu-id="dc96a-181">Aprire l'Editor Criteri di gruppo locali.</span><span class="sxs-lookup"><span data-stu-id="dc96a-181">Open Local Group Policy Editor.</span></span>
2. <span data-ttu-id="dc96a-182">Fai clic su **Configurazione computer** > **Modelli amministrativi** > **Microsoft Edge**.</span><span class="sxs-lookup"><span data-stu-id="dc96a-182">Click **Computer Configuration** > **Administrative Templates** > **Microsoft Edge**.</span></span>
3. <span data-ttu-id="dc96a-183">Fai doppio clic su **Invia tutti i siti Intranet a Internet Explorer**.</span><span class="sxs-lookup"><span data-stu-id="dc96a-183">Double-click **Send all intranet sites to Internet Explorer**.</span></span>
4. <span data-ttu-id="dc96a-184">Seleziona **Abilitato** e quindi fai clic su **OK** o su **Applica** per salvare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="dc96a-184">Select **Enabled**, and then click **OK** or **Apply** to save the policy settings.</span></span>

## <span data-ttu-id="dc96a-185">Reindirizzare i siti da IE a Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="dc96a-185">Redirect sites from IE to Microsoft Edge</span></span>

<span data-ttu-id="dc96a-186">È possibile impedire agli utenti di usare Internet Explorer per i siti che non lo richiedono.</span><span class="sxs-lookup"><span data-stu-id="dc96a-186">You can prevent your users from using Internet Explorer for sites that don't need it.</span></span> <span data-ttu-id="dc96a-187">Internet Explorer può reindirizzare automaticamente i siti a Microsoft Edge se non si trovano nell'elenco di siti.</span><span class="sxs-lookup"><span data-stu-id="dc96a-187">Internet Explorer can automatically redirect sites to Microsoft Edge if they aren't on your site list.</span></span>

1. <span data-ttu-id="dc96a-188">Apri Editor Criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="dc96a-188">Open Group Policy Editor.</span></span>
2. <span data-ttu-id="dc96a-189">Fare clic su **Configurazione computer** > **Strumenti di amministrazione** > **Componenti di Windows** > **Internet Explorer**.</span><span class="sxs-lookup"><span data-stu-id="dc96a-189">Click **Computer Configuration** > **Administrative Tools** > **Windows Components** > **Internet Explorer**.</span></span>
3. <span data-ttu-id="dc96a-190">Fare doppio clic su **Invia a Microsoft Edge tutti i siti non inclusi nell'elenco siti modalità Enterprise**.</span><span class="sxs-lookup"><span data-stu-id="dc96a-190">Double-click **Send all sites not included in the Enterprise Mode Site List to Microsoft Edge.**</span></span>
4. <span data-ttu-id="dc96a-191">Selezionare **Attivato**.</span><span class="sxs-lookup"><span data-stu-id="dc96a-191">Select **Enabled**</span></span>
5. <span data-ttu-id="dc96a-192">Fai clic su **OK** o su **Applica** per salvare queste impostazioni.</span><span class="sxs-lookup"><span data-stu-id="dc96a-192">Click **OK** or **Apply** to save these settings.</span></span>
6. <span data-ttu-id="dc96a-193">Fare doppio clic su **Configura quale canale di Microsoft Edge usare per aprire i siti reindirizzati**.</span><span class="sxs-lookup"><span data-stu-id="dc96a-193">Double-click **Configure which channel of Microsoft Edge to use for opening redirected sites**.</span></span>
7. <span data-ttu-id="dc96a-194">Seleziona **Attivata**.</span><span class="sxs-lookup"><span data-stu-id="dc96a-194">Select **Enabled**.</span></span>
8. <span data-ttu-id="dc96a-195">In **Opzioni**, selezionare le prime tre scelte per il canale da usare: Internet Explorer reindirizzerà alla scelta con la classificazione più alta che l'utente ha installato sul dispositivo:</span><span class="sxs-lookup"><span data-stu-id="dc96a-195">Under **Options**, select your top three choices for the channel to use - Internet Explorer will redirect to the highest ranked choice that the user has installed on that device:</span></span>
   - <span data-ttu-id="dc96a-196">Canale stabile Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="dc96a-196">Microsoft Edge Stable</span></span>
   - <span data-ttu-id="dc96a-197">Canale Microsoft Edge Beta versione 77 o successiva</span><span class="sxs-lookup"><span data-stu-id="dc96a-197">Microsoft Edge Beta version 77 or later</span></span>
   - <span data-ttu-id="dc96a-198">Canale Microsoft Edge Dev versione 77 o successiva</span><span class="sxs-lookup"><span data-stu-id="dc96a-198">Microsoft Edge Dev version 77 or later</span></span>
   - <span data-ttu-id="dc96a-199">Canale Microsoft Edge Canary versione 77 o successiva</span><span class="sxs-lookup"><span data-stu-id="dc96a-199">Microsoft Edge Canary version 77 or later</span></span>
   - <span data-ttu-id="dc96a-200">Microsoft Edge versione 45 o precedente</span><span class="sxs-lookup"><span data-stu-id="dc96a-200">Microsoft Edge version 45 or earlier</span></span>
9. <span data-ttu-id="dc96a-201">Fai clic su **OK** o su **Applica** per salvare queste impostazioni.</span><span class="sxs-lookup"><span data-stu-id="dc96a-201">Click **OK** or **Apply** to save these settings.</span></span>

## <span data-ttu-id="dc96a-202">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dc96a-202">See also</span></span>

- [<span data-ttu-id="dc96a-203">Pagina di destinazione di Microsoft Edge in modalità Enterprise</span><span class="sxs-lookup"><span data-stu-id="dc96a-203">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="dc96a-204">Informazioni sulla modalità IE</span><span class="sxs-lookup"><span data-stu-id="dc96a-204">About IE mode</span></span>](https://docs.microsoft.com/deployedge/edge-ie-mode)
- [<span data-ttu-id="dc96a-205">Informazioni aggiuntive sulla modalità Enterprise</span><span class="sxs-lookup"><span data-stu-id="dc96a-205">Additional Enterprise Mode information</span></span>](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/enterprise-mode-overview-for-ie11)