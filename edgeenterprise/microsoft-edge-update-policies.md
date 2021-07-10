---
title: Documentazione sui criteri di Microsoft Edge Update
ms.author: stmoody
author: dan-wesley
manager: tahills
ms.date: 06/29/2021
audience: ITPro
ms.topic: reference
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.custom: ''
description: Documentazione per tutti i criteri supportati da Microsoft Edge Update
ms.openlocfilehash: a9808981acad544042c6e0ccb59ff755a670c848
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2021
ms.locfileid: "11642322"
---
# <a name="microsoft-edge---update-policies"></a><span data-ttu-id="2a2a2-103">Microsoft Edge - Criteri di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="2a2a2-103">Microsoft Edge - Update policies</span></span>

<span data-ttu-id="2a2a2-104">La versione più recente di Microsoft Edge include i seguenti criteri che puoi usare per controllare come e quando Microsoft Edge viene aggiornato.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-104">The latest version of Microsoft Edge includes the following policies that you can use to control how and when Microsoft Edge is updated.</span></span>

<span data-ttu-id="2a2a2-105">Per informazioni su altri criteri disponibili in Microsoft Edge, vedi [Riferimento ai criteri del browser Microsoft Edge](microsoft-edge-policies.md)</span><span class="sxs-lookup"><span data-stu-id="2a2a2-105">For information about other policies available in Microsoft Edge, check out [Microsoft Edge browser policy reference](microsoft-edge-policies.md)</span></span>
> [!NOTE]
> <span data-ttu-id="2a2a2-106">Questo articolo si applica a Microsoft Edge versione 77 o successiva.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-106">This article applies to Microsoft Edge version 77 or later.</span></span>
## <a name="available-policies"></a><span data-ttu-id="2a2a2-107">Criteri disponibili</span><span class="sxs-lookup"><span data-stu-id="2a2a2-107">Available policies</span></span>
<span data-ttu-id="2a2a2-108">In queste tabelle sono elencati tutti i criteri di gruppo correlati agli aggiornamenti disponibili in questa versione di Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-108">These tables lists all of the update-related group policies available in this release of Microsoft Edge.</span></span> <span data-ttu-id="2a2a2-109">Usare i collegamenti nella tabella per ottenere altri dettagli su criteri specifici.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-109">Use the links in the table to get more details about specific policies.</span></span>

<span data-ttu-id="2a2a2-110">|&nbsp;|&nbsp;| |**-**| -| | **[Applicazioni](#applications)** | [Preferenze](#preferences)| | **[Server proxy](#proxy-server)** | [Microsoft Edge WebView](#microsoft-edge-webview)|</span><span class="sxs-lookup"><span data-stu-id="2a2a2-110">|&nbsp;|&nbsp;| |**-**|-| |**[Applications](#applications)**|[Preferences](#preferences)| |**[Proxy Server](#proxy-server)**|[Microsoft Edge WebView](#microsoft-edge-webview)|</span></span>
### [<a name="applications"></a><span data-ttu-id="2a2a2-111">Applicazioni</span><span class="sxs-lookup"><span data-stu-id="2a2a2-111">Applications</span></span>](#applications-policies)
|<span data-ttu-id="2a2a2-112">Nome criterio</span><span class="sxs-lookup"><span data-stu-id="2a2a2-112">Policy Name</span></span>|<span data-ttu-id="2a2a2-113">Didascalia</span><span class="sxs-lookup"><span data-stu-id="2a2a2-113">Caption</span></span>|
|-|-|
|[<span data-ttu-id="2a2a2-114">InstallDefault</span><span class="sxs-lookup"><span data-stu-id="2a2a2-114">InstallDefault</span></span>](#installdefault)|<span data-ttu-id="2a2a2-115">Consenti installazione predefinita</span><span class="sxs-lookup"><span data-stu-id="2a2a2-115">Allow installation default</span></span>|
|[<span data-ttu-id="2a2a2-116">UpdateDefault</span><span class="sxs-lookup"><span data-stu-id="2a2a2-116">UpdateDefault</span></span>](#updatedefault)|<span data-ttu-id="2a2a2-117">Sostituzione dei criteri di aggiornamento predefinita</span><span class="sxs-lookup"><span data-stu-id="2a2a2-117">Update policy override default</span></span>|
|[<span data-ttu-id="2a2a2-118">Install</span><span class="sxs-lookup"><span data-stu-id="2a2a2-118">Install</span></span>](#install)|<span data-ttu-id="2a2a2-119">Consenti installazione (per canale)</span><span class="sxs-lookup"><span data-stu-id="2a2a2-119">Allow installation (per channel)</span></span>|
|[<span data-ttu-id="2a2a2-120">Update</span><span class="sxs-lookup"><span data-stu-id="2a2a2-120">Update</span></span>](#update)|<span data-ttu-id="2a2a2-121">Sostituzione dei criteri di aggiornamento (per canale)</span><span class="sxs-lookup"><span data-stu-id="2a2a2-121">Update policy override (per channel)</span></span>|
|[<span data-ttu-id="2a2a2-122">Allowsxs</span><span class="sxs-lookup"><span data-stu-id="2a2a2-122">Allowsxs</span></span>](#allowsxs)|<span data-ttu-id="2a2a2-123">Consenti esperienza browser Microsoft Edge affiancata</span><span class="sxs-lookup"><span data-stu-id="2a2a2-123">Allow Microsoft Edge Side by Side browser experience</span></span>|
|[<span data-ttu-id="2a2a2-124">CreateDesktopShortcutDefault</span><span class="sxs-lookup"><span data-stu-id="2a2a2-124">CreateDesktopShortcutDefault</span></span>](#createdesktopshortcutdefault)|<span data-ttu-id="2a2a2-125">Impedisce la creazione di un collegamento sul desktop a seguito dell'installazione predefinita</span><span class="sxs-lookup"><span data-stu-id="2a2a2-125">Prevent Desktop Shortcut creation upon install default</span></span>|
|[<span data-ttu-id="2a2a2-126">CreateDesktopShortcut</span><span class="sxs-lookup"><span data-stu-id="2a2a2-126">CreateDesktopShortcut</span></span>](#createdesktopshortcut)|<span data-ttu-id="2a2a2-127">Impedisce la creazione di un collegamento sul desktop a seguito dell'installazione (per canale)</span><span class="sxs-lookup"><span data-stu-id="2a2a2-127">Prevent Desktop Shortcut creation upon install (per channel)</span></span>|
|[<span data-ttu-id="2a2a2-128">RollbackToTargetVersion</span><span class="sxs-lookup"><span data-stu-id="2a2a2-128">RollbackToTargetVersion</span></span>](#rollbacktotargetversion)|<span data-ttu-id="2a2a2-129">Eseguire il ripristino dello stato precedente della versione di destinazione (per canale)</span><span class="sxs-lookup"><span data-stu-id="2a2a2-129">Rollback to Target version (per channel)</span></span>|
|[<span data-ttu-id="2a2a2-130">TargetVersionPrefix</span><span class="sxs-lookup"><span data-stu-id="2a2a2-130">TargetVersionPrefix</span></span>](#targetversionprefix)|<span data-ttu-id="2a2a2-131">Sostituzione della versione di destinazione (in base al canale)</span><span class="sxs-lookup"><span data-stu-id="2a2a2-131">Target version override (per channel)</span></span>|

### [<a name="preferences"></a><span data-ttu-id="2a2a2-132">Preferenze</span><span class="sxs-lookup"><span data-stu-id="2a2a2-132">Preferences</span></span>](#preferences-policies)
|<span data-ttu-id="2a2a2-133">Nome criterio</span><span class="sxs-lookup"><span data-stu-id="2a2a2-133">Policy Name</span></span>|<span data-ttu-id="2a2a2-134">Didascalia</span><span class="sxs-lookup"><span data-stu-id="2a2a2-134">Caption</span></span>|
|-|-|
|[<span data-ttu-id="2a2a2-135">AutoUpdateCheckPeriodMinutes</span><span class="sxs-lookup"><span data-stu-id="2a2a2-135">AutoUpdateCheckPeriodMinutes</span></span>](#autoupdatecheckperiodminutes)|<span data-ttu-id="2a2a2-136">Sostituzione del periodo di controllo dell'aggiornamento automatico</span><span class="sxs-lookup"><span data-stu-id="2a2a2-136">Auto-update check period override</span></span>|
|[<span data-ttu-id="2a2a2-137">UpdatesSuppressed</span><span class="sxs-lookup"><span data-stu-id="2a2a2-137">UpdatesSuppressed</span></span>](#updatessuppressed)|<span data-ttu-id="2a2a2-138">Periodo di tempo in ogni giorno per eliminare il controllo dell'aggiornamento automatico</span><span class="sxs-lookup"><span data-stu-id="2a2a2-138">Time period in each day to suppress auto-update check</span></span>|

### [<a name="proxy-server"></a><span data-ttu-id="2a2a2-139">Server proxy</span><span class="sxs-lookup"><span data-stu-id="2a2a2-139">Proxy Server</span></span>](#proxy-server-policies)
|<span data-ttu-id="2a2a2-140">Nome criterio</span><span class="sxs-lookup"><span data-stu-id="2a2a2-140">Policy Name</span></span>|<span data-ttu-id="2a2a2-141">Didascalia</span><span class="sxs-lookup"><span data-stu-id="2a2a2-141">Caption</span></span>|
|-|-|
|[<span data-ttu-id="2a2a2-142">ProxyMode</span><span class="sxs-lookup"><span data-stu-id="2a2a2-142">ProxyMode</span></span>](#proxymode)|<span data-ttu-id="2a2a2-143">Scegliere come specificare le impostazioni del server proxy</span><span class="sxs-lookup"><span data-stu-id="2a2a2-143">Choose how to specify proxy server settings</span></span>|
|[<span data-ttu-id="2a2a2-144">ProxyPacUrl</span><span class="sxs-lookup"><span data-stu-id="2a2a2-144">ProxyPacUrl</span></span>](#proxypacurl)|<span data-ttu-id="2a2a2-145">URL di un file PAC del proxy</span><span class="sxs-lookup"><span data-stu-id="2a2a2-145">URL to a proxy .pac file</span></span>|
|[<span data-ttu-id="2a2a2-146">ProxyServer</span><span class="sxs-lookup"><span data-stu-id="2a2a2-146">ProxyServer</span></span>](#proxyserver)|<span data-ttu-id="2a2a2-147">Indirizzo o URL del server proxy</span><span class="sxs-lookup"><span data-stu-id="2a2a2-147">Address or URL of proxy server</span></span>|

### [<a name="microsoft-edge-webview"></a><span data-ttu-id="2a2a2-148">Microsoft Edge WebView</span><span class="sxs-lookup"><span data-stu-id="2a2a2-148">Microsoft Edge WebView</span></span>](#microsoft-edge-webview-policies)
|<span data-ttu-id="2a2a2-149">Nome criterio</span><span class="sxs-lookup"><span data-stu-id="2a2a2-149">Policy Name</span></span>|<span data-ttu-id="2a2a2-150">Didascalia</span><span class="sxs-lookup"><span data-stu-id="2a2a2-150">Caption</span></span>|
|-|-|
|[<span data-ttu-id="2a2a2-151">Installazione</span><span class="sxs-lookup"><span data-stu-id="2a2a2-151">Install</span></span>](#install-webview)|<span data-ttu-id="2a2a2-152">Consenti installazione</span><span class="sxs-lookup"><span data-stu-id="2a2a2-152">Allow installation</span></span>|
|[<span data-ttu-id="2a2a2-153">Aggiornamenti</span><span class="sxs-lookup"><span data-stu-id="2a2a2-153">Update</span></span>](#update-webview)|<span data-ttu-id="2a2a2-154">Sostituzione dei criteri di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="2a2a2-154">Update policy override</span></span>|

## <a name="applications-policies"></a><span data-ttu-id="2a2a2-155">Criteri delle applicazioni</span><span class="sxs-lookup"><span data-stu-id="2a2a2-155">Applications policies</span></span>

[<span data-ttu-id="2a2a2-156">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="2a2a2-156">Back to top</span></span>](#microsoft-edge---update-policies)
### <a name="installdefault"></a><span data-ttu-id="2a2a2-157">InstallDefault</span><span class="sxs-lookup"><span data-stu-id="2a2a2-157">InstallDefault</span></span>
#### <a name="allow-installation-default"></a><span data-ttu-id="2a2a2-158">Consenti installazione predefinita</span><span class="sxs-lookup"><span data-stu-id="2a2a2-158">Allow installation default</span></span>
><span data-ttu-id="2a2a2-159">Microsoft Edge Update 1.2.145.5 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="2a2a2-159">Microsoft Edge Update 1.2.145.5 and later</span></span>

#### <a name="description"></a><span data-ttu-id="2a2a2-160">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2a2a2-160">Description</span></span>
<span data-ttu-id="2a2a2-161">È possibile specificare il comportamento predefinito di tutti i canali per consentire o bloccare Microsoft Edge nei dispositivi collegati al dominio.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-161">You can specify the default behavior of all channels to allow or block Microsoft Edge on domain-joined devices.</span></span>

<span data-ttu-id="2a2a2-162">È possibile sostituire il criterio per i singoli canali abilitando il criterio "[Consenti installazione](#install)" per i canali specifici.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-162">You can override this policy for individual channels by enabling the '[Allow installation](#install)' policy for specific channels.</span></span>

<span data-ttu-id="2a2a2-163">Disabilitando questo criterio, l'installazione di Microsoft Edge verrà bloccata.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-163">If you disable this policy, the installation of Microsoft Edge is blocked.</span></span> <span data-ttu-id="2a2a2-164">Questo riguarda solo l'installazione del software Microsoft Edge quando il criterio "[Consenti l'installazione](#install)" è impostato su Non configurato.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-164">This only affects the installation of Microsoft Edge software when the '[Allow installation](#install)' policy is set to Not Configured.</span></span>

<span data-ttu-id="2a2a2-165">Questo criterio non impedisce l'esecuzione di Microsoft Edge Update, né impedisce l'installazione del software Microsoft Edge attraverso altri metodi.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-165">This policy doesn't prevent Microsoft Edge Update from running or prevent users from installing Microsoft Edge software using other methods.</span></span>

<span data-ttu-id="2a2a2-166">Questo criterio è disponibile solo nelle istanze di Windows che fanno parte di un dominio Microsoft® Active Directory®.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-166">This policy is available only on Windows instances that are joined to a Microsoft® Active Directory® domain.</span></span>
#### <a name="windows-information-and-settings"></a><span data-ttu-id="2a2a2-167">Informazioni e impostazioni di Windows</span><span class="sxs-lookup"><span data-stu-id="2a2a2-167">Windows information and settings</span></span>
##### <a name="group-policy-admx-info"></a><span data-ttu-id="2a2a2-168">Info su Criteri di gruppo (ADMX)</span><span class="sxs-lookup"><span data-stu-id="2a2a2-168">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="2a2a2-169">Nome univoco Criteri di gruppo: InstallDefault</span><span class="sxs-lookup"><span data-stu-id="2a2a2-169">GP unique name: InstallDefault</span></span>
- <span data-ttu-id="2a2a2-170">Nome Criteri di gruppo: Consenti installazione predefinita</span><span class="sxs-lookup"><span data-stu-id="2a2a2-170">GP name: Allow installation default</span></span>
- <span data-ttu-id="2a2a2-171">Percorso Criteri di gruppo: Modelli amministrativi/Microsoft Edge Update/Applicazioni</span><span class="sxs-lookup"><span data-stu-id="2a2a2-171">GP path: Administrative Templates/Microsoft Edge Update/Applications</span></span>
- <span data-ttu-id="2a2a2-172">Nome file ADMX Criteri di gruppo: msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="2a2a2-172">GP ADMX file name: msedgeupdate.admx</span></span>
##### <a name="windows-registry-settings"></a><span data-ttu-id="2a2a2-173">Impostazioni del Registro di sistema di Windows</span><span class="sxs-lookup"><span data-stu-id="2a2a2-173">Windows Registry Settings</span></span>
- <span data-ttu-id="2a2a2-174">Percorso: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="2a2a2-174">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="2a2a2-175">Nome valore: InstallDefault</span><span class="sxs-lookup"><span data-stu-id="2a2a2-175">Value Name: InstallDefault</span></span>
- <span data-ttu-id="2a2a2-176">Tipo valore: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="2a2a2-176">Value Type: REG_DWORD</span></span>
##### <a name="example-value"></a><span data-ttu-id="2a2a2-177">Valore di esempio</span><span class="sxs-lookup"><span data-stu-id="2a2a2-177">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="2a2a2-178">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="2a2a2-178">Back to top</span></span>](#microsoft-edge---update-policies)


### <a name="updatedefault"></a><span data-ttu-id="2a2a2-179">UpdateDefault</span><span class="sxs-lookup"><span data-stu-id="2a2a2-179">UpdateDefault</span></span>
#### <a name="update-policy-override-default"></a><span data-ttu-id="2a2a2-180">Sostituzione dei criteri di aggiornamento predefinita</span><span class="sxs-lookup"><span data-stu-id="2a2a2-180">Update policy override default</span></span>
><span data-ttu-id="2a2a2-181">Microsoft Edge Update 1.2.145.5 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="2a2a2-181">Microsoft Edge Update 1.2.145.5 and later</span></span>

#### <a name="description"></a><span data-ttu-id="2a2a2-182">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2a2a2-182">Description</span></span>
<span data-ttu-id="2a2a2-183">Consente di specificare il comportamento predefinito per tutti i canali in relazione al modo in cui Microsoft Edge Update gestisce gli aggiornamenti disponibili per Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-183">Lets you specify the default behavior for all channels concerning the way Microsoft Edge Update handles available updates for Microsoft Edge.</span></span> <span data-ttu-id="2a2a2-184">Può essere sostituito per singoli canali specificando il criterio "[Sostituzione dei criteri di aggiornamento](#update)" per i canali specifici.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-184">Can be overridden for individual channels by specifying the '[Update policy override](#update)' policy for those specific channels.</span></span>

  <span data-ttu-id="2a2a2-185">Se abiliti questo criterio, Microsoft Edge Update gestisce gli aggiornamenti Microsoft Edge in base alla configurazione delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2a2a2-185">If you enable this policy, Microsoft Edge Update handles Microsoft Edge updates according to how you configure the following options:</span></span>
   - <span data-ttu-id="2a2a2-186">Consenti sempre gli aggiornamenti: gli aggiornamenti vengono sempre applicati quando vengono rilevati, in seguito a un controllo periodico o manuale.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-186">Always allow updates: Updates are always applied when found, either by periodic update check or by a manual update check.</span></span>
   - <span data-ttu-id="2a2a2-187">Solo aggiornamenti automatici: gli aggiornamenti vengono applicati solo quando vengono rilevati in seguito al controllo periodico.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-187">Automatic silent updates only: Updates are applied only when they're found by the periodic update check.</span></span>
   - <span data-ttu-id="2a2a2-188">Solo aggiornamenti manuali: gli aggiornamenti vengono applicati solo quando gli utenti eseguono un controllo manuale.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-188">Manual updates only: Updates are applied only when the user runs a manual update check.</span></span>
   - <span data-ttu-id="2a2a2-189">Aggiornamenti disabilitati: gli aggiornamenti non vengono mai applicati.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-189">Updates disabled: Updates are never applied.</span></span>

  <span data-ttu-id="2a2a2-190">Se selezioni gli aggiornamenti manuali, verifica di controllare periodicamente la disponibilità degli aggiornamenti tramite il meccanismo di aggiornamento manuale dell'app, se disponibile.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-190">If you select manual updates, make sure you periodically check for updates by using the app's manual update mechanism, if available.</span></span> <span data-ttu-id="2a2a2-191">Se disabiliti gli aggiornamenti, verificane periodicamente la disponibilità e distribuiscili agli utenti.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-191">If you disable updates, periodically check for updates, and distribute them to users.</span></span>

  <span data-ttu-id="2a2a2-192">Se non abiliti né configuri questo criterio, Microsoft Edge Update gestisce gli aggiornamenti disponibili, come indicato dal criterio "[Sostituzione dei criteri di aggiornamento](#update)".</span><span class="sxs-lookup"><span data-stu-id="2a2a2-192">If you don't enable and configure this policy, Microsoft Edge Update handles available updates as specified by the '[Update policy override](#update)' policy.</span></span>

  <span data-ttu-id="2a2a2-193">Questo criterio è disponibile solo nelle istanze di Windows che fanno parte di un dominio Microsoft® Active Directory®.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-193">This policy is available only on Windows instances that are joined to a Microsoft® Active Directory® domain.</span></span>
#### <a name="windows-information-and-settings"></a><span data-ttu-id="2a2a2-194">Informazioni e impostazioni di Windows</span><span class="sxs-lookup"><span data-stu-id="2a2a2-194">Windows information and settings</span></span>
##### <a name="group-policy-admx-info"></a><span data-ttu-id="2a2a2-195">Info su Criteri di gruppo (ADMX)</span><span class="sxs-lookup"><span data-stu-id="2a2a2-195">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="2a2a2-196">Nome univoco Criteri di gruppo: UpdateDefault</span><span class="sxs-lookup"><span data-stu-id="2a2a2-196">GP unique name: UpdateDefault</span></span>
- <span data-ttu-id="2a2a2-197">Nome Criteri di gruppo: Sostituzione dei criteri di aggiornamento predefinita</span><span class="sxs-lookup"><span data-stu-id="2a2a2-197">GP name: Update policy override default</span></span>
- <span data-ttu-id="2a2a2-198">Percorso Criteri di gruppo: Modelli amministrativi/Microsoft Edge Update/Applicazioni</span><span class="sxs-lookup"><span data-stu-id="2a2a2-198">GP path: Administrative Templates/Microsoft Edge Update/Applications</span></span>
- <span data-ttu-id="2a2a2-199">Nome file ADMX Criteri di gruppo: msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="2a2a2-199">GP ADMX file name: msedgeupdate.admx</span></span>
##### <a name="windows-registry-settings"></a><span data-ttu-id="2a2a2-200">Impostazioni del Registro di sistema di Windows</span><span class="sxs-lookup"><span data-stu-id="2a2a2-200">Windows Registry Settings</span></span>
- <span data-ttu-id="2a2a2-201">Percorso: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="2a2a2-201">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="2a2a2-202">Nome valore: UpdateDefault</span><span class="sxs-lookup"><span data-stu-id="2a2a2-202">Value Name: UpdateDefault</span></span>
- <span data-ttu-id="2a2a2-203">Tipo valore: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="2a2a2-203">Value Type: REG_DWORD</span></span>
##### <a name="example-value"></a><span data-ttu-id="2a2a2-204">Valore di esempio</span><span class="sxs-lookup"><span data-stu-id="2a2a2-204">Example value:</span></span>
```
0x00000003
```
[<span data-ttu-id="2a2a2-205">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="2a2a2-205">Back to top</span></span>](#microsoft-edge---update-policies)


### <a name="install"></a><span data-ttu-id="2a2a2-206">Install</span><span class="sxs-lookup"><span data-stu-id="2a2a2-206">Install</span></span>
#### <a name="allow-installation"></a><span data-ttu-id="2a2a2-207">Consenti installazione</span><span class="sxs-lookup"><span data-stu-id="2a2a2-207">Allow installation</span></span>
><span data-ttu-id="2a2a2-208">Microsoft Edge Update 1.2.145.5 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="2a2a2-208">Microsoft Edge Update 1.2.145.5 and later</span></span>

#### <a name="description"></a><span data-ttu-id="2a2a2-209">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2a2a2-209">Description</span></span>
<span data-ttu-id="2a2a2-210">Specifica se è possibile installare un canale Microsoft Edge sui dispositivi collegati al dominio.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-210">Specifies whether a Microsoft Edge channel can be installed on domain-joined devices.</span></span>

  <span data-ttu-id="2a2a2-211">Se abiliti questo criterio per un canale, Microsoft Edge non verrà bloccato dall'installazione.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-211">If you enable this policy for a channel, Microsoft Edge will not be blocked from installation.</span></span>

  <span data-ttu-id="2a2a2-212">Se disabiliti questo criterio per un canale, Microsoft Edge verrà bloccato dall'installazione.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-212">If you disable this policy for a channel, Microsoft Edge will be blocked from installation.</span></span>

  <span data-ttu-id="2a2a2-213">Se non configuri questo criterio per un canale, il criterio "[Consenti installazione predefinita](#installdefault)" determina se gli utenti possono installare il canale di Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-213">If you don't configure this policy for a channel, the '[Allow installation default](#installdefault)' policy configuration determines whether users can install that channel of Microsoft Edge.</span></span>

  <span data-ttu-id="2a2a2-214">Questo criterio è disponibile solo nelle istanze di Windows che fanno parte di un dominio Microsoft® Active Directory®.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-214">This policy is available only on Windows instances that are joined to a Microsoft® Active Directory® domain.</span></span>
#### <a name="windows-information-and-settings"></a><span data-ttu-id="2a2a2-215">Informazioni e impostazioni di Windows</span><span class="sxs-lookup"><span data-stu-id="2a2a2-215">Windows information and settings</span></span>
##### <a name="group-policy-admx-info"></a><span data-ttu-id="2a2a2-216">Info su Criteri di gruppo (ADMX)</span><span class="sxs-lookup"><span data-stu-id="2a2a2-216">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="2a2a2-217">Nome univoco Criteri di gruppo: Install</span><span class="sxs-lookup"><span data-stu-id="2a2a2-217">GP unique name: Install</span></span>
- <span data-ttu-id="2a2a2-218">Nome Criteri di gruppo: Consenti installazione</span><span class="sxs-lookup"><span data-stu-id="2a2a2-218">GP name: Allow installation</span></span>
- <span data-ttu-id="2a2a2-219">Percorso Criteri di gruppo:</span><span class="sxs-lookup"><span data-stu-id="2a2a2-219">GP path:</span></span> 
  - <span data-ttu-id="2a2a2-220">Modelli amministrativi/Microsoft Edge Update/Applicazioni/Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="2a2a2-220">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge</span></span>
  - <span data-ttu-id="2a2a2-221">Modelli amministrativi/Microsoft Edge Update/Applicazioni/Microsoft Edge Beta</span><span class="sxs-lookup"><span data-stu-id="2a2a2-221">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Beta</span></span>
  - <span data-ttu-id="2a2a2-222">Modelli amministrativi/Microsoft Edge Update/Applicazioni/Microsoft Edge Canary</span><span class="sxs-lookup"><span data-stu-id="2a2a2-222">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Canary</span></span>
  - <span data-ttu-id="2a2a2-223">Modelli amministrativi/Microsoft Edge Update/Applicazioni/Microsoft Edge Dev</span><span class="sxs-lookup"><span data-stu-id="2a2a2-223">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Dev</span></span>
- <span data-ttu-id="2a2a2-224">Nome file ADMX Criteri di gruppo: msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="2a2a2-224">GP ADMX file name: msedgeupdate.admx</span></span>
##### <a name="windows-registry-settings"></a><span data-ttu-id="2a2a2-225">Impostazioni del Registro di sistema di Windows</span><span class="sxs-lookup"><span data-stu-id="2a2a2-225">Windows Registry Settings</span></span>
- <span data-ttu-id="2a2a2-226">Percorso: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="2a2a2-226">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="2a2a2-227">Nome valore:</span><span class="sxs-lookup"><span data-stu-id="2a2a2-227">Value Name:</span></span> 
  - <span data-ttu-id="2a2a2-228">(Stabile): Install{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span><span class="sxs-lookup"><span data-stu-id="2a2a2-228">(Stable): Install{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span></span>
  - <span data-ttu-id="2a2a2-229">(Beta): Install{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span><span class="sxs-lookup"><span data-stu-id="2a2a2-229">(Beta): Install{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span></span>
  - <span data-ttu-id="2a2a2-230">(Canary): Install{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span><span class="sxs-lookup"><span data-stu-id="2a2a2-230">(Canary): Install{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span></span>
  - <span data-ttu-id="2a2a2-231">(Dev): Install{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span><span class="sxs-lookup"><span data-stu-id="2a2a2-231">(Dev): Install{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span></span>
- <span data-ttu-id="2a2a2-232">Tipo valore: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="2a2a2-232">Value Type: REG_DWORD</span></span>
##### <a name="example-value"></a><span data-ttu-id="2a2a2-233">Valore di esempio</span><span class="sxs-lookup"><span data-stu-id="2a2a2-233">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="2a2a2-234">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="2a2a2-234">Back to top</span></span>](#microsoft-edge---update-policies)


### <a name="update"></a><span data-ttu-id="2a2a2-235">Update</span><span class="sxs-lookup"><span data-stu-id="2a2a2-235">Update</span></span>
#### <a name="update-policy-override"></a><span data-ttu-id="2a2a2-236">Sostituzione dei criteri di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="2a2a2-236">Update policy override</span></span>
><span data-ttu-id="2a2a2-237">Microsoft Edge Update 1.2.145.5 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="2a2a2-237">Microsoft Edge Update 1.2.145.5 and later</span></span>

#### <a name="description"></a><span data-ttu-id="2a2a2-238">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2a2a2-238">Description</span></span>
<span data-ttu-id="2a2a2-239">Specifica il modo in cui Microsoft Edge Update gestisce gli aggiornamenti disponibili da Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-239">Specifies how Microsoft Edge Update handles available updates from Microsoft Edge.</span></span>

<span data-ttu-id="2a2a2-240">Se abiliti questo criterio, Microsoft Edge Update gestisce gli aggiornamenti Microsoft Edge in base alla configurazione delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2a2a2-240">If you enable this policy, Microsoft Edge Update handles Microsoft Edge updates according to how you configure the following options:</span></span>
  - <span data-ttu-id="2a2a2-241">Consenti sempre gli aggiornamenti: gli aggiornamenti vengono sempre applicati quando vengono rilevati, in seguito a un controllo periodico o manuale.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-241">Always allow updates: Updates are always applied when found, either by periodic update check or by a manual update check.</span></span>
  - <span data-ttu-id="2a2a2-242">Solo aggiornamenti automatici: gli aggiornamenti vengono applicati solo quando vengono rilevati in seguito al controllo periodico.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-242">Automatic silent updates only: Updates are applied only when they're found by the periodic update check.</span></span>
  - <span data-ttu-id="2a2a2-243">Solo aggiornamenti manuali: gli aggiornamenti vengono applicati solo quando gli utenti eseguono un controllo manuale.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-243">Manual updates only: Updates are applied only when the user runs a manual update check.</span></span> <span data-ttu-id="2a2a2-244">Non tutte le app forniscono un'interfaccia per questa opzione.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-244">(Not all apps provide an interface for this option.)</span></span>
  - <span data-ttu-id="2a2a2-245">Aggiornamenti disabilitati: gli aggiornamenti non vengono mai applicati.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-245">Updates disabled: Updates are never applied.</span></span>

<span data-ttu-id="2a2a2-246">Se selezioni gli aggiornamenti manuali, verifica di controllare periodicamente la disponibilità degli aggiornamenti tramite il meccanismo di aggiornamento manuale dell'app, se disponibile.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-246">If you select manual updates, make sure you periodically check for updates by using the app's manual update mechanism, if available.</span></span> <span data-ttu-id="2a2a2-247">Se disabiliti gli aggiornamenti, verificane periodicamente la disponibilità e distribuiscili agli utenti.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-247">If you disable updates, periodically check for updates, and distribute them to users.</span></span>

<span data-ttu-id="2a2a2-248">Se non abiliti né configuri questo criterio, Microsoft Edge Update gestisce gli aggiornamenti disponibili, come indicato dal criterio "[Sostituzione dei criteri di aggiornamento predefinita](#updatedefault)".</span><span class="sxs-lookup"><span data-stu-id="2a2a2-248">If you don't enable and configure this policy, Microsoft Edge Update handles available updates as specified by the '[Update policy override default](#updatedefault)' policy.</span></span>

<span data-ttu-id="2a2a2-249">Per altre informazioni, vedere [https://go.microsoft.com/fwlink/?linkid=2136406](https://go.microsoft.com/fwlink/?linkid=2136406).</span><span class="sxs-lookup"><span data-stu-id="2a2a2-249">See [https://go.microsoft.com/fwlink/?linkid=2136406](https://go.microsoft.com/fwlink/?linkid=2136406) for more information.</span></span>

<span data-ttu-id="2a2a2-250">Questo criterio è disponibile solo nelle istanze di Windows che fanno parte di un dominio Microsoft® Active Directory®.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-250">This policy is available only on Windows instances that are joined to a Microsoft® Active Directory® domain.</span></span>
#### <a name="windows-information-and-settings"></a><span data-ttu-id="2a2a2-251">Informazioni e impostazioni di Windows</span><span class="sxs-lookup"><span data-stu-id="2a2a2-251">Windows information and settings</span></span>
##### <a name="group-policy-admx-info"></a><span data-ttu-id="2a2a2-252">Info su Criteri di gruppo (ADMX)</span><span class="sxs-lookup"><span data-stu-id="2a2a2-252">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="2a2a2-253">Nome univoco Criteri di gruppo: Update</span><span class="sxs-lookup"><span data-stu-id="2a2a2-253">GP unique name: Update</span></span>
- <span data-ttu-id="2a2a2-254">Nome Criteri di gruppo: Sostituzione dei criteri di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="2a2a2-254">GP name: Update policy override</span></span>
- <span data-ttu-id="2a2a2-255">Percorso Criteri di gruppo:</span><span class="sxs-lookup"><span data-stu-id="2a2a2-255">GP path:</span></span> 
  - <span data-ttu-id="2a2a2-256">Modelli amministrativi/Microsoft Edge Update/Applicazioni/Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="2a2a2-256">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge</span></span>
  - <span data-ttu-id="2a2a2-257">Modelli amministrativi/Microsoft Edge Update/Applicazioni/Microsoft Edge Beta</span><span class="sxs-lookup"><span data-stu-id="2a2a2-257">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Beta</span></span>
  - <span data-ttu-id="2a2a2-258">Modelli amministrativi/Microsoft Edge Update/Applicazioni/Microsoft Edge Canary</span><span class="sxs-lookup"><span data-stu-id="2a2a2-258">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Canary</span></span>
  - <span data-ttu-id="2a2a2-259">Modelli amministrativi/Microsoft Edge Update/Applicazioni/Microsoft Edge Dev</span><span class="sxs-lookup"><span data-stu-id="2a2a2-259">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Dev</span></span>
- <span data-ttu-id="2a2a2-260">Nome file ADMX Criteri di gruppo: msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="2a2a2-260">GP ADMX file name: msedgeupdate.admx</span></span>
##### <a name="windows-registry-settings"></a><span data-ttu-id="2a2a2-261">Impostazioni del Registro di sistema di Windows</span><span class="sxs-lookup"><span data-stu-id="2a2a2-261">Windows Registry Settings</span></span>
- <span data-ttu-id="2a2a2-262">Percorso: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="2a2a2-262">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="2a2a2-263">Nome:</span><span class="sxs-lookup"><span data-stu-id="2a2a2-263">Value Name:</span></span> 
  - <span data-ttu-id="2a2a2-264">(Stabile): Update{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span><span class="sxs-lookup"><span data-stu-id="2a2a2-264">(Stable): Update{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span></span>
  - <span data-ttu-id="2a2a2-265">(Beta): Update{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span><span class="sxs-lookup"><span data-stu-id="2a2a2-265">(Beta): Update{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span></span>
  - <span data-ttu-id="2a2a2-266">(Canary): Update{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span><span class="sxs-lookup"><span data-stu-id="2a2a2-266">(Canary): Update{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span></span>
  - <span data-ttu-id="2a2a2-267">(Dev): Update{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span><span class="sxs-lookup"><span data-stu-id="2a2a2-267">(Dev): Update{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span></span>
- <span data-ttu-id="2a2a2-268">Tipo valore: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="2a2a2-268">Value Type: REG_DWORD</span></span>
##### <a name="example-value"></a><span data-ttu-id="2a2a2-269">Valore di esempio</span><span class="sxs-lookup"><span data-stu-id="2a2a2-269">Example value:</span></span>
```
always allow updates 0x00000001
Automatic silent updates only 0x00000003
manual updates only 0x00000002
updates disabled 0x00000000
```
[<span data-ttu-id="2a2a2-270">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="2a2a2-270">Back to top</span></span>](#microsoft-edge---update-policies)


### <a name="allowsxs"></a><span data-ttu-id="2a2a2-271">Allowsxs</span><span class="sxs-lookup"><span data-stu-id="2a2a2-271">Allowsxs</span></span>
#### <a name="allow-microsoft-edge-side-by-side-browser-experience"></a><span data-ttu-id="2a2a2-272">Consenti esperienza browser Microsoft Edge affiancata</span><span class="sxs-lookup"><span data-stu-id="2a2a2-272">Allow Microsoft Edge Side by Side browser experience</span></span>
><span data-ttu-id="2a2a2-273">Microsoft Edge Update 1.2.145.5 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="2a2a2-273">Microsoft Edge Update 1.2.145.5 and later</span></span>

#### <a name="description"></a><span data-ttu-id="2a2a2-274">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2a2a2-274">Description</span></span>
<span data-ttu-id="2a2a2-275">Questo criterio consente a un utente di eseguire Microsoft Edge (Edge HTML) e Microsoft Edge (basato su Chromium) in modalità affiancata.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-275">This policy lets a user run Microsoft Edge (Edge HTML) and Microsoft Edge (Chromium-based) side-by-side.</span></span>

<span data-ttu-id="2a2a2-276">Se questo criterio è impostato su "Non configurato", Microsoft Edge (basato su Chromium) sostituirà Microsoft Edge (Edge HTML) dopo l'installazione del canale stabile di Microsoft Edge (basato su Chromium) e degli aggiornamenti della sicurezza di novembre 2019.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-276">If this policy is set to “Not configured”, Microsoft Edge (Chromium-based) will replace Microsoft Edge (Edge HTML) after the Microsoft Edge (Chromium-based) stable channel and the November 2019 security updates are installed.</span></span>  <span data-ttu-id="2a2a2-277">Si tratta dello stesso comportamento correlato all'impostazione "Disabilitato".</span><span class="sxs-lookup"><span data-stu-id="2a2a2-277">This is the same behavior as the “Disabled” setting.</span></span>

<span data-ttu-id="2a2a2-278">L'impostazione "Disabilitato" blocca un'esperienza affiancata e Microsoft Edge (basato su Chromium) sostituirà Microsoft Edge (Edge HTML) dopo l'installazione del canale stabile di Microsoft Edge (basato su Chromium) e degli aggiornamenti della sicurezza di novembre 2019.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-278">The “Disabled” setting blocks a side-by-side experience and Microsoft Edge (Chromium-based) will replace Microsoft Edge (Edge HTML) after the Microsoft Edge (Chromium-based) stable channel and the November 2019 security updates are installed.</span></span>  <span data-ttu-id="2a2a2-279">Si tratta dello stesso comportamento correlato all'impostazione "Non configurato".</span><span class="sxs-lookup"><span data-stu-id="2a2a2-279">This is the same behavior as the “Not Configured” setting.</span></span>

<span data-ttu-id="2a2a2-280">Quando l'impostazione di questo criterio è "Abilitato", è possibile eseguire in modalità affiancata Microsoft Edge (basato su Chromium) e Microsoft Edge (Edge HTML) dopo l'installazione di Microsoft Edge (basato su Chromium).</span><span class="sxs-lookup"><span data-stu-id="2a2a2-280">When this policy is “Enabled”, Microsoft Edge (Chromium-based) and Microsoft Edge (Edge HTML) can run side-by-side after Microsoft Edge (Chromium-based) is installed.</span></span>

<span data-ttu-id="2a2a2-281">Affinché questi criteri di gruppo abbiano effetto, è necessario configurarli prima dell'installazione automatica di Microsoft Edge (basato su Chromium) da Windows Update.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-281">For this group policy to take affect, it must be configured before the automatic install of Microsoft Edge (Chromium-based) by Windows Update.</span></span> <span data-ttu-id="2a2a2-282">Nota: un utente può bloccare l'aggiornamento automatico di Microsoft Edge (basato su Chromium) usando Blocker Toolkit di Microsoft Edge (basato su Chromium).</span><span class="sxs-lookup"><span data-stu-id="2a2a2-282">Note: A user can block the automatic update of Microsoft Edge (Chromium-based) by using the Microsoft Edge (Chromium-based) Blocker Toolkit.</span></span>
#### <a name="windows-information-and-settings"></a><span data-ttu-id="2a2a2-283">Informazioni e impostazioni di Windows</span><span class="sxs-lookup"><span data-stu-id="2a2a2-283">Windows information and settings</span></span>
##### <a name="group-policy-admx-info"></a><span data-ttu-id="2a2a2-284">Info su Criteri di gruppo (ADMX)</span><span class="sxs-lookup"><span data-stu-id="2a2a2-284">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="2a2a2-285">Nome univoco Criteri di gruppo: Allowsxs</span><span class="sxs-lookup"><span data-stu-id="2a2a2-285">GP unique name: Allowsxs</span></span>
- <span data-ttu-id="2a2a2-286">Nome Criteri di gruppo: Consenti esperienza browser Microsoft Edge affiancata</span><span class="sxs-lookup"><span data-stu-id="2a2a2-286">GP name: Allow Microsoft Edge Side by Side browser experience</span></span>
- <span data-ttu-id="2a2a2-287">Percorso Criteri di gruppo: Modelli amministrativi/Microsoft Edge Update/Applicazioni</span><span class="sxs-lookup"><span data-stu-id="2a2a2-287">GP path: Administrative Templates/Microsoft Edge Update/Applications</span></span>
- <span data-ttu-id="2a2a2-288">Nome file ADMX Criteri di gruppo: msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="2a2a2-288">GP ADMX file name: msedgeupdate.admx</span></span>
##### <a name="windows-registry-settings"></a><span data-ttu-id="2a2a2-289">Impostazioni del Registro di sistema di Windows</span><span class="sxs-lookup"><span data-stu-id="2a2a2-289">Windows Registry Settings</span></span>
- <span data-ttu-id="2a2a2-290">Percorso: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="2a2a2-290">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="2a2a2-291">Nome valore: Allowsxs</span><span class="sxs-lookup"><span data-stu-id="2a2a2-291">Value Name: Allowsxs</span></span>
- <span data-ttu-id="2a2a2-292">Tipo valore: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="2a2a2-292">Value Type: REG_DWORD</span></span>
##### <a name="example-value"></a><span data-ttu-id="2a2a2-293">Valore di esempio</span><span class="sxs-lookup"><span data-stu-id="2a2a2-293">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="2a2a2-294">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="2a2a2-294">Back to top</span></span>](#microsoft-edge---update-policies)


### <a name="createdesktopshortcutdefault"></a><span data-ttu-id="2a2a2-295">CreateDesktopShortcutDefault</span><span class="sxs-lookup"><span data-stu-id="2a2a2-295">CreateDesktopShortcutDefault</span></span>
#### <a name="prevent-desktop-shortcut-creation-upon-install-default"></a><span data-ttu-id="2a2a2-296">Impedisce la creazione di un collegamento sul desktop a seguito dell'installazione predefinita</span><span class="sxs-lookup"><span data-stu-id="2a2a2-296">Prevent Desktop Shortcut creation upon install default</span></span>
><span data-ttu-id="2a2a2-297">Microsoft Edge Update 1.3.128.0 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="2a2a2-297">Microsoft Edge Update 1.3.128.0 and later</span></span>

#### <a name="description"></a><span data-ttu-id="2a2a2-298">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2a2a2-298">Description</span></span>
<span data-ttu-id="2a2a2-299">Consente di specificare il comportamento predefinito per tutti i canali per la creazione di un collegamento sul desktop quando Microsoft Edge è installato.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-299">Lets you specify the default behavior for all channels for creating a desktop shortcut when Microsoft Edge is installed.</span></span>

  <span data-ttu-id="2a2a2-300">Abilitando questo criterio, si creerà un collegamento sul desktop quando Microsoft Edge è installato.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-300">If you enable this policy a desktop shortcut is created when Microsoft Edge is installed.</span></span>
<span data-ttu-id="2a2a2-301">Disabilitando questo criterio, non si creerà un collegamento sul desktop quando Microsoft Edge è installato.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-301">If you disable this policy, no desktop shortcut will be created when Microsoft Edge is installed.</span></span>
<span data-ttu-id="2a2a2-302">Non configurando questo criterio, si creerà sul desktop un collegamento a Microsoft Edge durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-302">If you don’t configure this policy a desktop shortcut to Microsoft Edge will be created during installation.</span></span>
<span data-ttu-id="2a2a2-303">Nel caso in cui Microsoft Edge fosse già installato, il criterio non avrà effetto.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-303">If Microsoft Edge is already installed, this policy will have no effect.</span></span>
#### <a name="windows-information-and-settings"></a><span data-ttu-id="2a2a2-304">Informazioni e impostazioni di Windows</span><span class="sxs-lookup"><span data-stu-id="2a2a2-304">Windows information and settings</span></span>
##### <a name="group-policy-admx-info"></a><span data-ttu-id="2a2a2-305">Info su Criteri di gruppo (ADMX)</span><span class="sxs-lookup"><span data-stu-id="2a2a2-305">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="2a2a2-306">Nome univoco Criteri di gruppo: CreateDesktopShortcutDefault</span><span class="sxs-lookup"><span data-stu-id="2a2a2-306">GP unique name: CreateDesktopShortcutDefault</span></span>
- <span data-ttu-id="2a2a2-307">Nome Criteri di gruppo: impedisce la creazione di un collegamento sul desktop a seguito dell'installazione predefinita</span><span class="sxs-lookup"><span data-stu-id="2a2a2-307">GP name: Prevent Desktop Shortcut creation upon install default</span></span>
- <span data-ttu-id="2a2a2-308">Percorso Criteri di gruppo: Modelli amministrativi/Microsoft Edge Update/Applicazioni</span><span class="sxs-lookup"><span data-stu-id="2a2a2-308">GP path: Administrative Templates/Microsoft Edge Update/Applications</span></span>
- <span data-ttu-id="2a2a2-309">Nome file ADMX Criteri di gruppo: msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="2a2a2-309">GP ADMX file name: msedgeupdate.admx</span></span>
##### <a name="windows-registry-settings"></a><span data-ttu-id="2a2a2-310">Impostazioni del Registro di sistema di Windows</span><span class="sxs-lookup"><span data-stu-id="2a2a2-310">Windows Registry Settings</span></span>
- <span data-ttu-id="2a2a2-311">Percorso: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="2a2a2-311">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="2a2a2-312">Nome valore: CreateDesktopShortcutDefault</span><span class="sxs-lookup"><span data-stu-id="2a2a2-312">Value Name: CreateDesktopShortcutDefault</span></span>
- <span data-ttu-id="2a2a2-313">Tipo valore: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="2a2a2-313">Value Type: REG_DWORD</span></span>
##### <a name="example-value"></a><span data-ttu-id="2a2a2-314">Valore di esempio</span><span class="sxs-lookup"><span data-stu-id="2a2a2-314">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="2a2a2-315">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="2a2a2-315">Back to top</span></span>](#microsoft-edge---update-policies)


### <a name="createdesktopshortcut"></a><span data-ttu-id="2a2a2-316">CreateDesktopShortcut</span><span class="sxs-lookup"><span data-stu-id="2a2a2-316">CreateDesktopShortcut</span></span>
#### <a name="prevent-desktop-shortcut-creation-upon-install"></a><span data-ttu-id="2a2a2-317">Impedisce la creazione di un collegamento sul desktop a seguito dell'installazione</span><span class="sxs-lookup"><span data-stu-id="2a2a2-317">Prevent Desktop Shortcut creation upon install</span></span>
><span data-ttu-id="2a2a2-318">Microsoft Edge Update 1.3.128.0 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="2a2a2-318">Microsoft Edge Update 1.3.128.0 and later</span></span>

#### <a name="description"></a><span data-ttu-id="2a2a2-319">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2a2a2-319">Description</span></span>
<span data-ttu-id="2a2a2-320">Abilitando questo criterio, si creerà un collegamento sul desktop quando Microsoft Edge è installato.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-320">If you enable this policy a desktop shortcut is created when Microsoft Edge is installed.</span></span>
<span data-ttu-id="2a2a2-321">Disabilitando questo criterio, non si creerà un collegamento sul desktop quando Microsoft Edge è installato.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-321">If you disable this policy, no desktop shortcut will be created when Microsoft Edge is installed.</span></span>
<span data-ttu-id="2a2a2-322">Non configurando questo criterio, si creerà sul desktop un collegamento a Microsoft Edge durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-322">If you don’t configure this policy a desktop shortcut to Microsoft Edge will be created during installation.</span></span>
<span data-ttu-id="2a2a2-323">Nel caso in cui Microsoft Edge fosse già installato, il criterio non avrà effetto.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-323">If Microsoft Edge is already installed, this policy will have no effect.</span></span>

  <span data-ttu-id="2a2a2-324">Se questo criterio non viene configurato per un canale, la configurazione del criterio "[Impedisce la creazione di un collegamento sul desktop a seguito dell'installazione predefinita](#createdesktopshortcutdefault)" determina la creazione del collegamento quando Microsoft Edge viene installato.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-324">If you don't configure this policy for a channel, the '[Prevent Desktop Shortcut creation upon install default](#createdesktopshortcutdefault)' policy configuration determines shortcut creation when Microsoft Edge is installed.</span></span>
#### <a name="windows-information-and-settings"></a><span data-ttu-id="2a2a2-325">Informazioni e impostazioni di Windows</span><span class="sxs-lookup"><span data-stu-id="2a2a2-325">Windows information and settings</span></span>
##### <a name="group-policy-admx-info"></a><span data-ttu-id="2a2a2-326">Info su Criteri di gruppo (ADMX)</span><span class="sxs-lookup"><span data-stu-id="2a2a2-326">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="2a2a2-327">Nome univoco Criteri di gruppo: CreateDesktopShortcut</span><span class="sxs-lookup"><span data-stu-id="2a2a2-327">GP unique name: CreateDesktopShortcut</span></span>
- <span data-ttu-id="2a2a2-328">Nome Criteri di gruppo: impedisce la creazione di un collegamento sul desktop dopo l'installazione</span><span class="sxs-lookup"><span data-stu-id="2a2a2-328">GP name: Prevent Desktop Shortcut creation upon install</span></span>
- <span data-ttu-id="2a2a2-329">Percorso Criteri di gruppo:</span><span class="sxs-lookup"><span data-stu-id="2a2a2-329">GP path:</span></span> 
  - <span data-ttu-id="2a2a2-330">Modelli amministrativi/Microsoft Edge Update/Applicazioni/Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="2a2a2-330">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge</span></span>
  - <span data-ttu-id="2a2a2-331">Modelli amministrativi/Microsoft Edge Update/Applicazioni/Microsoft Edge Beta</span><span class="sxs-lookup"><span data-stu-id="2a2a2-331">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Beta</span></span>
  - <span data-ttu-id="2a2a2-332">Modelli amministrativi/Microsoft Edge Update/Applicazioni/Microsoft Edge Canary</span><span class="sxs-lookup"><span data-stu-id="2a2a2-332">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Canary</span></span>
  - <span data-ttu-id="2a2a2-333">Modelli amministrativi/Microsoft Edge Update/Applicazioni/Microsoft Edge Dev</span><span class="sxs-lookup"><span data-stu-id="2a2a2-333">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Dev</span></span>
- <span data-ttu-id="2a2a2-334">Nome file ADMX Criteri di gruppo: msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="2a2a2-334">GP ADMX file name: msedgeupdate.admx</span></span>
##### <a name="windows-registry-settings"></a><span data-ttu-id="2a2a2-335">Impostazioni del Registro di sistema di Windows</span><span class="sxs-lookup"><span data-stu-id="2a2a2-335">Windows Registry Settings</span></span>
- <span data-ttu-id="2a2a2-336">Percorso: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="2a2a2-336">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="2a2a2-337">Nome:</span><span class="sxs-lookup"><span data-stu-id="2a2a2-337">Value Name:</span></span> 
  - <span data-ttu-id="2a2a2-338">(Stable): CreateDesktopShortcut{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span><span class="sxs-lookup"><span data-stu-id="2a2a2-338">(Stable): CreateDesktopShortcut{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span></span>
  - <span data-ttu-id="2a2a2-339">(Beta): CreateDesktopShortcut{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span><span class="sxs-lookup"><span data-stu-id="2a2a2-339">(Beta): CreateDesktopShortcut{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span></span>
  - <span data-ttu-id="2a2a2-340">(Canary): CreateDesktopShortcut{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span><span class="sxs-lookup"><span data-stu-id="2a2a2-340">(Canary): CreateDesktopShortcut{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span></span>
  - <span data-ttu-id="2a2a2-341">(Dev): CreateDesktopShortcut{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span><span class="sxs-lookup"><span data-stu-id="2a2a2-341">(Dev): CreateDesktopShortcut{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span></span>
- <span data-ttu-id="2a2a2-342">Tipo valore: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="2a2a2-342">Value Type: REG_DWORD</span></span>
##### <a name="example-value"></a><span data-ttu-id="2a2a2-343">Valore di esempio</span><span class="sxs-lookup"><span data-stu-id="2a2a2-343">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="2a2a2-344">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="2a2a2-344">Back to top</span></span>](#microsoft-edge---update-policies)


### <a name="rollbacktotargetversion"></a><span data-ttu-id="2a2a2-345">RollbackToTargetVersion</span><span class="sxs-lookup"><span data-stu-id="2a2a2-345">RollbackToTargetVersion</span></span>
#### <a name="rollback-to-target-version"></a><span data-ttu-id="2a2a2-346">Esegui il ripristino dello stato precedente della versione di destinazione</span><span class="sxs-lookup"><span data-stu-id="2a2a2-346">Rollback to Target version</span></span>
><span data-ttu-id="2a2a2-347">Microsoft Edge Update 1.3.133.3 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="2a2a2-347">Microsoft Edge Update 1.3.133.3 and later</span></span>

#### <a name="description"></a><span data-ttu-id="2a2a2-348">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2a2a2-348">Description</span></span>
<span data-ttu-id="2a2a2-349">Specifica che Microsoft Edge Update dovrebbe eseguire il ripristino dello stato precedente delle installazioni di Microsoft Edge alla versione indicata in "[Sostituzione della versione di destinazione](#targetversionprefix)".</span><span class="sxs-lookup"><span data-stu-id="2a2a2-349">Specifies that Microsoft Edge Update should rollback installations of Microsoft Edge to the version indicated in '[Target version override](#targetversionprefix)'.</span></span>

<span data-ttu-id="2a2a2-350">Questo criterio non ha alcun effetto, a meno che “[Sostituzione della versione di destinazione](#targetversionprefix)” sia impostato e “[Aggiorna criterio sostituzione](#update)” sia impostato su ATTIVO in uno dei seguenti stati (Consenti sempre gli aggiornamenti, Solo aggiornamenti automatici silenziosi, Solo aggiornamenti manuali).</span><span class="sxs-lookup"><span data-stu-id="2a2a2-350">This policy has no effect unless '[Target version override](#targetversionprefix)' is set and '[Update policy override](#update)' is set to one of the ON states (Always allow updates, Automatic silent updates only, Manual updates only).</span></span>

<span data-ttu-id="2a2a2-351">Se disabiliti questo criterio o non lo configuri, le installazioni con una versione superiore a quella specificata da "[Sostituzione della versione di destinazione](#targetversionprefix)" verranno lasciate così come sono.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-351">If you disable this policy or don't configure it, installs that have a version higher than that specified by '[Target version override](#targetversionprefix)' will be left as-is.</span></span>

<span data-ttu-id="2a2a2-352">Se abiliti questi criteri, le installazioni che hanno una versione corrente superiore a quella specificata dall'override della”[Aggiorna criterio sostituzione](#targetversionprefix)" verranno declassate alla versione di destinazione.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-352">If you enable this policy, installs that have a current version higher than specified by the '[Target version override](#targetversionprefix)' will be downgraded to the target version.</span></span>

<span data-ttu-id="2a2a2-353">È consigliabile installare l’ultima versione del browser Microsoft Edge per sfruttare la protezione degli aggiornamenti della sicurezza più recenti.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-353">We recommend that users install the latest version of the Microsoft Edge browser to ensure protection by the latest security updates.</span></span> <span data-ttu-id="2a2a2-354">Il ripristino di una versione precedente può comportare rischi di esposizione a problemi di sicurezza noti.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-354">Rollback to an earlier version risks exposure to known security issues.</span></span> <span data-ttu-id="2a2a2-355">Questo criterio deve essere usato come correzione temporanea per risolvere i problemi di aggiornamento del browser Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-355">This policy is meant to be used as a temporary fix to address issues in a Microsoft Edge browser update.</span></span>

<span data-ttu-id="2a2a2-356">Prima di ripristinare temporaneamente la versione precedente del browser, è inoltre consigliabile abilitare la sincronizzazione ([https://go.microsoft.com/fwlink/?linkid=2133032](https://go.microsoft.com/fwlink/?linkid=2133032)) per tutti gli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-356">Before temporarily rolling back your browser version, we recommend that you turn on Sync ([https://go.microsoft.com/fwlink/?linkid=2133032](https://go.microsoft.com/fwlink/?linkid=2133032)) for all users in your organization.</span></span> <span data-ttu-id="2a2a2-357">Se la sincronizzazione non viene abilitata, si rischia la perdita permanente dei dati di navigazione.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-357">If you don't turn on Sync, there is a risk of permanent browsing data loss.</span></span> <span data-ttu-id="2a2a2-358">Usa questo criterio a tuo rischio.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-358">Use this policy at your own risk.</span></span>

<span data-ttu-id="2a2a2-359">Nota: è possibile visualizzare tutte le versioni disponibili per il ripristino dello stato precedente qui [https://aka.ms/EdgeEnterprise](https://aka.ms/EdgeEnterprise).</span><span class="sxs-lookup"><span data-stu-id="2a2a2-359">Note: All versions available for rollback can be viewed here [https://aka.ms/EdgeEnterprise](https://aka.ms/EdgeEnterprise).</span></span>

<span data-ttu-id="2a2a2-360">Questo criteri viene applicato a Microsoft Edge versione 86 o successiva.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-360">This policy applies to Microsoft Edge version 86 or later.</span></span>

<span data-ttu-id="2a2a2-361">Per altre informazioni, vedere [https://go.microsoft.com/fwlink/?linkid=2133918](https://go.microsoft.com/fwlink/?linkid=2133918).</span><span class="sxs-lookup"><span data-stu-id="2a2a2-361">See [https://go.microsoft.com/fwlink/?linkid=2133918](https://go.microsoft.com/fwlink/?linkid=2133918) for more information.</span></span>

<span data-ttu-id="2a2a2-362">Questo criterio è disponibile solo nelle istanze di Windows che fanno parte di un dominio Microsoft® Active Directory®.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-362">This policy is available only on Windows instances that are joined to a Microsoft® Active Directory® domain.</span></span>
#### <a name="windows-information-and-settings"></a><span data-ttu-id="2a2a2-363">Informazioni e impostazioni di Windows</span><span class="sxs-lookup"><span data-stu-id="2a2a2-363">Windows information and settings</span></span>
##### <a name="group-policy-admx-info"></a><span data-ttu-id="2a2a2-364">Info su Criteri di gruppo (ADMX)</span><span class="sxs-lookup"><span data-stu-id="2a2a2-364">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="2a2a2-365">Nome univoco Criteri di gruppo: RollbackToTargetVersion</span><span class="sxs-lookup"><span data-stu-id="2a2a2-365">GP unique name: RollbackToTargetVersion</span></span>
- <span data-ttu-id="2a2a2-366">Nome Criteri di gruppo: ripristina versione di destinazione</span><span class="sxs-lookup"><span data-stu-id="2a2a2-366">GP name: Rollback to Target version</span></span>
- <span data-ttu-id="2a2a2-367">Percorso Criteri di gruppo:</span><span class="sxs-lookup"><span data-stu-id="2a2a2-367">GP path:</span></span> 
  - <span data-ttu-id="2a2a2-368">Modelli amministrativi/Microsoft Edge Update/Applicazioni/Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="2a2a2-368">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge</span></span>
  - <span data-ttu-id="2a2a2-369">Modelli amministrativi/Microsoft Edge Update/Applicazioni/Microsoft Edge Beta</span><span class="sxs-lookup"><span data-stu-id="2a2a2-369">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Beta</span></span>
  - <span data-ttu-id="2a2a2-370">Modelli amministrativi/Microsoft Edge Update/Applicazioni/Microsoft Edge Canary</span><span class="sxs-lookup"><span data-stu-id="2a2a2-370">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Canary</span></span>
  - <span data-ttu-id="2a2a2-371">Modelli amministrativi/Microsoft Edge Update/Applicazioni/Microsoft Edge Dev</span><span class="sxs-lookup"><span data-stu-id="2a2a2-371">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Dev</span></span>
- <span data-ttu-id="2a2a2-372">Nome file ADMX Criteri di gruppo: msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="2a2a2-372">GP ADMX file name: msedgeupdate.admx</span></span>
##### <a name="windows-registry-settings"></a><span data-ttu-id="2a2a2-373">Impostazioni del Registro di sistema di Windows</span><span class="sxs-lookup"><span data-stu-id="2a2a2-373">Windows Registry Settings</span></span>
- <span data-ttu-id="2a2a2-374">Percorso: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="2a2a2-374">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="2a2a2-375">Nome:</span><span class="sxs-lookup"><span data-stu-id="2a2a2-375">Value Name:</span></span> 
  - <span data-ttu-id="2a2a2-376">(Stable): RollbackToTargetVersion{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span><span class="sxs-lookup"><span data-stu-id="2a2a2-376">(Stable): RollbackToTargetVersion{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span></span>
  - <span data-ttu-id="2a2a2-377">(Beta): RollbackToTargetVersion{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span><span class="sxs-lookup"><span data-stu-id="2a2a2-377">(Beta): RollbackToTargetVersion{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span></span>
  - <span data-ttu-id="2a2a2-378">(Canary): RollbackToTargetVersion{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span><span class="sxs-lookup"><span data-stu-id="2a2a2-378">(Canary): RollbackToTargetVersion{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span></span>
  - <span data-ttu-id="2a2a2-379">(Dev): RollbackToTargetVersion{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span><span class="sxs-lookup"><span data-stu-id="2a2a2-379">(Dev): RollbackToTargetVersion{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span></span>
- <span data-ttu-id="2a2a2-380">Tipo valore: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="2a2a2-380">Value Type: REG_DWORD</span></span>
##### <a name="example-value"></a><span data-ttu-id="2a2a2-381">Valore di esempio</span><span class="sxs-lookup"><span data-stu-id="2a2a2-381">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="2a2a2-382">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="2a2a2-382">Back to top</span></span>](#microsoft-edge---update-policies)


### <a name="targetversionprefix"></a><span data-ttu-id="2a2a2-383">TargetVersionPrefix</span><span class="sxs-lookup"><span data-stu-id="2a2a2-383">TargetVersionPrefix</span></span>
#### <a name="target-version-override"></a><span data-ttu-id="2a2a2-384">Sostituzione della versione di destinazione</span><span class="sxs-lookup"><span data-stu-id="2a2a2-384">Target version override</span></span>
><span data-ttu-id="2a2a2-385">Microsoft Edge Update 1.3.119.43 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="2a2a2-385">Microsoft Edge Update 1.3.119.43 and later</span></span>

#### <a name="description"></a><span data-ttu-id="2a2a2-386">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2a2a2-386">Description</span></span>
<span data-ttu-id="2a2a2-387">Abilitando questo criterio e l'aggiornamento automatico, Microsoft Edge verrà aggiornato alla versione specificata da questo valore criterio.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-387">When this policy is enabled, and auto-update is enabled, Microsoft Edge will be updated to the version specified by this policy value.</span></span>

<span data-ttu-id="2a2a2-388">Il valore del criterio deve essere una specifica versione di Microsoft Edge, ad esempio: 83.0.499.12.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-388">The policy value must be a specific Microsoft Edge version, e.g. 83.0.499.12.</span></span>

<span data-ttu-id="2a2a2-389">Se sul dispositivo è installata una versione più recente di Microsoft Edge del valore specificato, Edge manterrà la versione più recente e non eseguirà il downgrade alla versione specificata.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-389">If a device has newer version of Microsoft Edge than the value specified, Microsoft Edge will remain on the newer version and not downgrade to the specified version.</span></span>

<span data-ttu-id="2a2a2-390">In caso la versione specificata non esista o non sia formattata correttamente, Microsoft Edge manterrà la versione attuale e non verrà aggiornato automaticamente alle versioni future.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-390">If the specified version does not exist, or is improperly formatted, then Microsoft Edge will remain on its current version and not update to future versions automatically.</span></span>

<span data-ttu-id="2a2a2-391">Per altre informazioni, vedere [https://go.microsoft.com/fwlink/?linkid=2136707](https://go.microsoft.com/fwlink/?linkid=2136707).</span><span class="sxs-lookup"><span data-stu-id="2a2a2-391">See [https://go.microsoft.com/fwlink/?linkid=2136707](https://go.microsoft.com/fwlink/?linkid=2136707) for more information.</span></span>

<span data-ttu-id="2a2a2-392">Questo criterio è disponibile solo nelle istanze di Windows che fanno parte di un dominio Microsoft® Active Directory®.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-392">This policy is available only on Windows instances that are joined to a Microsoft® Active Directory® domain.</span></span>
#### <a name="windows-information-and-settings"></a><span data-ttu-id="2a2a2-393">Informazioni e impostazioni di Windows</span><span class="sxs-lookup"><span data-stu-id="2a2a2-393">Windows information and settings</span></span>
##### <a name="group-policy-admx-info"></a><span data-ttu-id="2a2a2-394">Info su Criteri di gruppo (ADMX)</span><span class="sxs-lookup"><span data-stu-id="2a2a2-394">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="2a2a2-395">Nome univoco Criteri di gruppo: TargetVersionPrefix</span><span class="sxs-lookup"><span data-stu-id="2a2a2-395">GP unique name: TargetVersionPrefix</span></span>
- <span data-ttu-id="2a2a2-396">Nome Criteri di gruppo: Sostituzione della versione di destinazione</span><span class="sxs-lookup"><span data-stu-id="2a2a2-396">GP name: Target version override</span></span>
- <span data-ttu-id="2a2a2-397">Percorso Criteri di gruppo:</span><span class="sxs-lookup"><span data-stu-id="2a2a2-397">GP path:</span></span> 
  - <span data-ttu-id="2a2a2-398">Modelli amministrativi/Microsoft Edge Update/Applicazioni/Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="2a2a2-398">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge</span></span>
  - <span data-ttu-id="2a2a2-399">Modelli amministrativi/Microsoft Edge Update/Applicazioni/Microsoft Edge Beta</span><span class="sxs-lookup"><span data-stu-id="2a2a2-399">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Beta</span></span>
  - <span data-ttu-id="2a2a2-400">Modelli amministrativi/Microsoft Edge Update/Applicazioni/Microsoft Edge Canary</span><span class="sxs-lookup"><span data-stu-id="2a2a2-400">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Canary</span></span>
  - <span data-ttu-id="2a2a2-401">Modelli amministrativi/Microsoft Edge Update/Applicazioni/Microsoft Edge Dev</span><span class="sxs-lookup"><span data-stu-id="2a2a2-401">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Dev</span></span>
- <span data-ttu-id="2a2a2-402">Nome file ADMX Criteri di gruppo: msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="2a2a2-402">GP ADMX file name: msedgeupdate.admx</span></span>
##### <a name="windows-registry-settings"></a><span data-ttu-id="2a2a2-403">Impostazioni del Registro di sistema di Windows</span><span class="sxs-lookup"><span data-stu-id="2a2a2-403">Windows Registry Settings</span></span>
- <span data-ttu-id="2a2a2-404">Percorso: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="2a2a2-404">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="2a2a2-405">Nome:</span><span class="sxs-lookup"><span data-stu-id="2a2a2-405">Value Name:</span></span> 
  - <span data-ttu-id="2a2a2-406">(Stable): TargetVersionPrefix{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span><span class="sxs-lookup"><span data-stu-id="2a2a2-406">(Stable): TargetVersionPrefix{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span></span>
  - <span data-ttu-id="2a2a2-407">(Beta): TargetVersionPrefix{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span><span class="sxs-lookup"><span data-stu-id="2a2a2-407">(Beta): TargetVersionPrefix{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span></span>
  - <span data-ttu-id="2a2a2-408">(Canary): TargetVersionPrefix{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span><span class="sxs-lookup"><span data-stu-id="2a2a2-408">(Canary): TargetVersionPrefix{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span></span>
  - <span data-ttu-id="2a2a2-409">(Dev): TargetVersionPrefix{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span><span class="sxs-lookup"><span data-stu-id="2a2a2-409">(Dev): TargetVersionPrefix{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span></span>
- <span data-ttu-id="2a2a2-410">Tipo valore: REG_SZ</span><span class="sxs-lookup"><span data-stu-id="2a2a2-410">Value Type: REG_SZ</span></span>
##### <a name="example-value"></a><span data-ttu-id="2a2a2-411">Valore di esempio</span><span class="sxs-lookup"><span data-stu-id="2a2a2-411">Example value:</span></span>
```
83.0.499.12
```
[<span data-ttu-id="2a2a2-412">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="2a2a2-412">Back to top</span></span>](#microsoft-edge---update-policies)


## <a name="preferences-policies"></a><span data-ttu-id="2a2a2-413">Criteri delle preferenze</span><span class="sxs-lookup"><span data-stu-id="2a2a2-413">Preferences policies</span></span>

[<span data-ttu-id="2a2a2-414">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="2a2a2-414">Back to top</span></span>](#microsoft-edge---update-policies)
### <a name="autoupdatecheckperiodminutes"></a><span data-ttu-id="2a2a2-415">AutoUpdateCheckPeriodMinutes</span><span class="sxs-lookup"><span data-stu-id="2a2a2-415">AutoUpdateCheckPeriodMinutes</span></span>
#### <a name="auto-update-check-period-override"></a><span data-ttu-id="2a2a2-416">Sostituzione del periodo di controllo dell'aggiornamento automatico</span><span class="sxs-lookup"><span data-stu-id="2a2a2-416">Auto-update check period override</span></span>
><span data-ttu-id="2a2a2-417">Microsoft Edge Update 1.2.145.5 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="2a2a2-417">Microsoft Edge Update 1.2.145.5 and later</span></span>

#### <a name="description"></a><span data-ttu-id="2a2a2-418">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2a2a2-418">Description</span></span>
<span data-ttu-id="2a2a2-419">Se abilitata, questo criterio consente di impostare un valore per il numero minimo di minuti che devono intercorrere tra i controlli dell'aggiornamento automatico.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-419">If enabled, this policy lets you set a value for the minimum number of minutes between automatic update checks.</span></span> <span data-ttu-id="2a2a2-420">In caso contrario, per impostazione predefinita, l'aggiornamento automatico verifica la disponibilità degli aggiornamenti ogni 10 ore.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-420">Otherwise, by default, auto-update checks for updates every 10 hours.</span></span>

  <span data-ttu-id="2a2a2-421">Se desideri disabilitare tutti i controlli dell'aggiornamento automatico, imposta il valore su 0 (scelta non consigliata).</span><span class="sxs-lookup"><span data-stu-id="2a2a2-421">If you want to disable all auto-update checks, set the value to 0 (not recommended).</span></span>
#### <a name="windows-information-and-settings"></a><span data-ttu-id="2a2a2-422">Informazioni e impostazioni di Windows</span><span class="sxs-lookup"><span data-stu-id="2a2a2-422">Windows information and settings</span></span>
##### <a name="group-policy-admx-info"></a><span data-ttu-id="2a2a2-423">Info su Criteri di gruppo (ADMX)</span><span class="sxs-lookup"><span data-stu-id="2a2a2-423">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="2a2a2-424">Nome univoco Criteri di gruppo: AutoUpdateCheckPeriodMinutes</span><span class="sxs-lookup"><span data-stu-id="2a2a2-424">GP unique name: AutoUpdateCheckPeriodMinutes</span></span>
- <span data-ttu-id="2a2a2-425">Nome Criteri di gruppo: Sostituzione del periodo di controllo dell'aggiornamento automatico</span><span class="sxs-lookup"><span data-stu-id="2a2a2-425">GP name: Auto-update check period override</span></span>
- <span data-ttu-id="2a2a2-426">Percorso Criteri di gruppo: Modelli amministrativi/Microsoft Edge Update/Preferenze</span><span class="sxs-lookup"><span data-stu-id="2a2a2-426">GP path: Administrative Templates/Microsoft Edge Update/Preferences</span></span>
- <span data-ttu-id="2a2a2-427">Nome file ADMX Criteri di gruppo: msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="2a2a2-427">GP ADMX file name: msedgeupdate.admx</span></span>
##### <a name="windows-registry-settings"></a><span data-ttu-id="2a2a2-428">Impostazioni del Registro di sistema di Windows</span><span class="sxs-lookup"><span data-stu-id="2a2a2-428">Windows Registry Settings</span></span>
- <span data-ttu-id="2a2a2-429">Percorso: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="2a2a2-429">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="2a2a2-430">Nome valore: AutoUpdateCheckPeriodMinutes</span><span class="sxs-lookup"><span data-stu-id="2a2a2-430">Value Name: AutoUpdateCheckPeriodMinutes</span></span>
- <span data-ttu-id="2a2a2-431">Tipo valore: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="2a2a2-431">Value Type: REG_DWORD</span></span>
##### <a name="example-value"></a><span data-ttu-id="2a2a2-432">Valore di esempio</span><span class="sxs-lookup"><span data-stu-id="2a2a2-432">Example value:</span></span>
```
0x00000578
```
[<span data-ttu-id="2a2a2-433">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="2a2a2-433">Back to top</span></span>](#microsoft-edge---update-policies)


### <a name="updatessuppressed"></a><span data-ttu-id="2a2a2-434">UpdatesSuppressed</span><span class="sxs-lookup"><span data-stu-id="2a2a2-434">UpdatesSuppressed</span></span>
#### <a name="time-period-in-each-day-to-suppress-auto-update-check"></a><span data-ttu-id="2a2a2-435">Periodo di tempo in ogni giorno per eliminare il controllo dell'aggiornamento automatico</span><span class="sxs-lookup"><span data-stu-id="2a2a2-435">Time period in each day to suppress auto-update check</span></span>
><span data-ttu-id="2a2a2-436">Microsoft Edge Update 1.3.33.5 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="2a2a2-436">Microsoft Edge Update 1.3.33.5 and later</span></span>

#### <a name="description"></a><span data-ttu-id="2a2a2-437">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2a2a2-437">Description</span></span>
<span data-ttu-id="2a2a2-438">Se abiliti questo criterio, i controlli degli aggiornamenti vengono soppressi ogni giorno a partire dall'ora e dal minuto specificati per un periodo stabilito (in minuti).</span><span class="sxs-lookup"><span data-stu-id="2a2a2-438">If you enable this policy, update checks are suppressed each day starting at Hour:Minute for a period of Duration (in minutes).</span></span> <span data-ttu-id="2a2a2-439">La durata non è influenzata dall'ora legale.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-439">Duration isn't affected by daylight saving time.</span></span> <span data-ttu-id="2a2a2-440">Ad esempio, se l'ora di inizio è 22.00 e la durata è 480 minuti, gli aggiornamenti verranno soppressi per esattamente 8 ore, indipendentemente dal fatto che l'ora legale venga avviata o termini durante questo periodo.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-440">For example, if the start time is 22:00 and the duration is 480 minutes, updates will be suppressed for exactly 8 hours, regardless of whether daylight saving time starts or ends during this period.</span></span>

  <span data-ttu-id="2a2a2-441">Se disabiliti o non configuri questo criterio, i controlli degli aggiornamenti non vengono soppressi durante alcun periodo specifico.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-441">If you disable or don't configure this policy, update checks aren't suppressed during any specific period.</span></span>
#### <a name="windows-information-and-settings"></a><span data-ttu-id="2a2a2-442">Informazioni e impostazioni di Windows</span><span class="sxs-lookup"><span data-stu-id="2a2a2-442">Windows information and settings</span></span>
##### <a name="group-policy-admx-info"></a><span data-ttu-id="2a2a2-443">Info su Criteri di gruppo (ADMX)</span><span class="sxs-lookup"><span data-stu-id="2a2a2-443">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="2a2a2-444">Nome univoco Criteri di gruppo: UpdatesSuppressed</span><span class="sxs-lookup"><span data-stu-id="2a2a2-444">GP unique name: UpdatesSuppressed</span></span>
- <span data-ttu-id="2a2a2-445">Nome Criteri di gruppo: Periodo di tempo in ogni giorno per eliminare il controllo dell'aggiornamento automatico</span><span class="sxs-lookup"><span data-stu-id="2a2a2-445">GP name: Time period in each day to suppress auto-update check</span></span>
  - <span data-ttu-id="2a2a2-446">Opzioni { Hour, Minute, Duration }</span><span class="sxs-lookup"><span data-stu-id="2a2a2-446">Options { Hour, Minute, Duration }</span></span>
- <span data-ttu-id="2a2a2-447">Percorso Criteri di gruppo: Modelli amministrativi/Microsoft Edge Update/Preferenze</span><span class="sxs-lookup"><span data-stu-id="2a2a2-447">GP path: Administrative Templates/Microsoft Edge Update/Preferences</span></span>
- <span data-ttu-id="2a2a2-448">Nome file ADMX Criteri di gruppo: msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="2a2a2-448">GP ADMX file name: msedgeupdate.admx</span></span>
##### <a name="windows-registry-settings"></a><span data-ttu-id="2a2a2-449">Impostazioni del Registro di sistema di Windows</span><span class="sxs-lookup"><span data-stu-id="2a2a2-449">Windows Registry Settings</span></span>
- <span data-ttu-id="2a2a2-450">Percorso: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="2a2a2-450">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="2a2a2-451">Nome:</span><span class="sxs-lookup"><span data-stu-id="2a2a2-451">Value Name:</span></span> 
  - <span data-ttu-id="2a2a2-452">UpdatesSuppressedDurationMin</span><span class="sxs-lookup"><span data-stu-id="2a2a2-452">UpdatesSuppressedDurationMin</span></span>
  - <span data-ttu-id="2a2a2-453">UpdatesSuppressedStartHour</span><span class="sxs-lookup"><span data-stu-id="2a2a2-453">UpdatesSuppressedStartHour</span></span>
  - <span data-ttu-id="2a2a2-454">UpdatesSuppressedStartMin</span><span class="sxs-lookup"><span data-stu-id="2a2a2-454">UpdatesSuppressedStartMin</span></span>
- <span data-ttu-id="2a2a2-455">Tipo valore: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="2a2a2-455">Value Type: REG_DWORD</span></span>
##### <a name="example-value"></a><span data-ttu-id="2a2a2-456">Valore di esempio</span><span class="sxs-lookup"><span data-stu-id="2a2a2-456">Example value:</span></span>
```
duration   : 0x0000003c
start hour : 0x00000001
start min  : 0x00000002
```
[<span data-ttu-id="2a2a2-457">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="2a2a2-457">Back to top</span></span>](#microsoft-edge---update-policies)


## <a name="proxy-server-policies"></a><span data-ttu-id="2a2a2-458">Criteri server proxy</span><span class="sxs-lookup"><span data-stu-id="2a2a2-458">Proxy Server policies</span></span>

[<span data-ttu-id="2a2a2-459">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="2a2a2-459">Back to top</span></span>](#microsoft-edge---update-policies)
### <a name="proxymode"></a><span data-ttu-id="2a2a2-460">ProxyMode</span><span class="sxs-lookup"><span data-stu-id="2a2a2-460">ProxyMode</span></span>
#### <a name="choose-how-to-specify-proxy-server-settings"></a><span data-ttu-id="2a2a2-461">Scegliere come specificare le impostazioni del server proxy</span><span class="sxs-lookup"><span data-stu-id="2a2a2-461">Choose how to specify proxy server settings</span></span>
><span data-ttu-id="2a2a2-462">Microsoft Edge Update 1.3.21.81 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="2a2a2-462">Microsoft Edge Update 1.3.21.81 and later</span></span>

#### <a name="description"></a><span data-ttu-id="2a2a2-463">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2a2a2-463">Description</span></span>
<span data-ttu-id="2a2a2-464">Consente di specificare le impostazioni del server proxy usate da Microsoft Edge Update.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-464">Allows you to specify the proxy server settings that are used by Microsoft Edge Update.</span></span>

  <span data-ttu-id="2a2a2-465">Se abiliti questo criterio, puoi scegliere una delle opzioni relative al server proxy seguenti:</span><span class="sxs-lookup"><span data-stu-id="2a2a2-465">If you enable this policy, you can choose between the following proxy server options:</span></span>
   - <span data-ttu-id="2a2a2-466">Se scegli di non usare mai un server proxy e ti connetti sempre direttamente, tutte le altre opzioni vengono ignorate.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-466">If you choose to never use a proxy server and always connect directly, all other options are ignored.</span></span>
   - <span data-ttu-id="2a2a2-467">Se scegli di usare le impostazioni del proxy di sistema o di rilevare automaticamente il server proxy, tutte le altre opzioni vengono ignorate.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-467">If you choose to use system proxy settings or auto-detect the proxy server, all other options are ignored.</span></span>
   - <span data-ttu-id="2a2a2-468">Se scegli la modalità proxy server fisso, puoi specificare altre opzioni nel criterio "[Indirizzo o URL del server proxy](#proxyserver)".</span><span class="sxs-lookup"><span data-stu-id="2a2a2-468">If you choose fixed server proxy mode, you can specify further options in '[Address or URL of proxy server](#proxyserver)' policy.</span></span>
   - <span data-ttu-id="2a2a2-469">Se scegli di usare uno script proxy PAC, devi specificare l'URL per lo script nel criterio "[URL di un file PAC del proxy](#proxypacurl)".</span><span class="sxs-lookup"><span data-stu-id="2a2a2-469">If you choose to use a .pac proxy script, you must specify the URL for the script in '[URL to a proxy .pac file](#proxypacurl)' policy.</span></span>

  <span data-ttu-id="2a2a2-470">Se abiliti questo criterio, gli utenti dell'organizzazione non possono modificare le impostazioni proxy in Microsoft Edge Update.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-470">If you enable this policy, users in your organization can't change the proxy settings in Microsoft Edge Update.</span></span>

  <span data-ttu-id="2a2a2-471">Se disabiliti o non configuri questo criterio, non vengono configurate impostazioni del server proxy, ma gli utenti dell'organizzazione possono scegliere le proprie impostazioni proxy per Microsoft Edge Update.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-471">If you disable or don't configure this policy, no proxy server settings are configured, but users in your organization can choose their own proxy settings for Microsoft Edge Update.</span></span>
#### <a name="windows-information-and-settings"></a><span data-ttu-id="2a2a2-472">Informazioni e impostazioni di Windows</span><span class="sxs-lookup"><span data-stu-id="2a2a2-472">Windows information and settings</span></span>
##### <a name="group-policy-admx-info"></a><span data-ttu-id="2a2a2-473">Info su Criteri di gruppo (ADMX)</span><span class="sxs-lookup"><span data-stu-id="2a2a2-473">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="2a2a2-474">Nome univoco Criteri di gruppo: ProxyMode</span><span class="sxs-lookup"><span data-stu-id="2a2a2-474">GP unique name: ProxyMode</span></span>
- <span data-ttu-id="2a2a2-475">Nome Criteri di gruppo: Scegliere come specificare le impostazioni del server proxy</span><span class="sxs-lookup"><span data-stu-id="2a2a2-475">GP name: Choose how to specify proxy server settings</span></span>
- <span data-ttu-id="2a2a2-476">Percorso Criteri di gruppo: Modelli amministrativi/Microsoft Edge Update/Server proxy</span><span class="sxs-lookup"><span data-stu-id="2a2a2-476">GP path: Administrative Templates/Microsoft Edge Update/Proxy Server</span></span>
- <span data-ttu-id="2a2a2-477">Nome file ADMX Criteri di gruppo: msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="2a2a2-477">GP ADMX file name: msedgeupdate.admx</span></span>
##### <a name="windows-registry-settings"></a><span data-ttu-id="2a2a2-478">Impostazioni del Registro di sistema di Windows</span><span class="sxs-lookup"><span data-stu-id="2a2a2-478">Windows Registry Settings</span></span>
- <span data-ttu-id="2a2a2-479">Percorso: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="2a2a2-479">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="2a2a2-480">Nome valore: ProxyMode</span><span class="sxs-lookup"><span data-stu-id="2a2a2-480">Value Name: ProxyMode</span></span>
- <span data-ttu-id="2a2a2-481">Tipo valore: REG_SZ</span><span class="sxs-lookup"><span data-stu-id="2a2a2-481">Value Type: REG_SZ</span></span>
##### <a name="example-value"></a><span data-ttu-id="2a2a2-482">Valore di esempio</span><span class="sxs-lookup"><span data-stu-id="2a2a2-482">Example value:</span></span>
```
fixed_servers
```
[<span data-ttu-id="2a2a2-483">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="2a2a2-483">Back to top</span></span>](#microsoft-edge---update-policies)


### <a name="proxypacurl"></a><span data-ttu-id="2a2a2-484">ProxyPacUrl</span><span class="sxs-lookup"><span data-stu-id="2a2a2-484">ProxyPacUrl</span></span>
#### <a name="url-to-a-proxy-pac-file"></a><span data-ttu-id="2a2a2-485">URL di un file PAC del proxy</span><span class="sxs-lookup"><span data-stu-id="2a2a2-485">URL to a proxy .pac file</span></span>
><span data-ttu-id="2a2a2-486">Microsoft Edge Update 1.3.21.81 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="2a2a2-486">Microsoft Edge Update 1.3.21.81 and later</span></span>

#### <a name="description"></a><span data-ttu-id="2a2a2-487">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2a2a2-487">Description</span></span>
<span data-ttu-id="2a2a2-488">Consente di specificare un URL per un file di configurazione automatica del proxy (PAC).</span><span class="sxs-lookup"><span data-stu-id="2a2a2-488">Allows you to specify a URL for a proxy auto-config (PAC) file.</span></span>

  <span data-ttu-id="2a2a2-489">Se abiliti questo criterio, puoi specificare un URL per un file PAC per automatizzare il modo in cui Microsoft Edge Update seleziona il server proxy appropriato per il recupero di un particolare sito Web.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-489">If you enable this policy, you can specify a URL for a PAC file to automate how Microsoft Edge Update selects the appropriate proxy server for fetching a particular website.</span></span>

  <span data-ttu-id="2a2a2-490">Questo criterio viene applicato solo se sono state specificate impostazioni proxy manuali nel criterio "[Scegliere come specificare le impostazioni del server proxy](#proxymode)".</span><span class="sxs-lookup"><span data-stu-id="2a2a2-490">This policy is applied only if you have specified manual proxy settings in the '[Choose how to specify proxy server settings](#proxymode)' policy.</span></span>

  <span data-ttu-id="2a2a2-491">Non configurare questo criterio se hai selezionato un'impostazione proxy diversa da quella manuale nel criterio "[Scegliere come specificare le impostazioni del server proxy](#proxymode)".</span><span class="sxs-lookup"><span data-stu-id="2a2a2-491">Don't configure this policy if you have selected a proxy setting other than manual in the '[Choose how to specify proxy server settings](#proxymode)' policy.</span></span>
#### <a name="windows-information-and-settings"></a><span data-ttu-id="2a2a2-492">Informazioni e impostazioni di Windows</span><span class="sxs-lookup"><span data-stu-id="2a2a2-492">Windows information and settings</span></span>
##### <a name="group-policy-admx-info"></a><span data-ttu-id="2a2a2-493">Info su Criteri di gruppo (ADMX)</span><span class="sxs-lookup"><span data-stu-id="2a2a2-493">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="2a2a2-494">Nome univoco Criteri di gruppo: ProxyPacUrl</span><span class="sxs-lookup"><span data-stu-id="2a2a2-494">GP unique name: ProxyPacUrl</span></span>
- <span data-ttu-id="2a2a2-495">Nome Criteri di Gruppo: URL di un file PAC del proxy</span><span class="sxs-lookup"><span data-stu-id="2a2a2-495">GP name: URL to a proxy .pac file</span></span>
- <span data-ttu-id="2a2a2-496">Percorso Criteri di gruppo: Modelli amministrativi/Microsoft Edge Update/Server proxy</span><span class="sxs-lookup"><span data-stu-id="2a2a2-496">GP path: Administrative Templates/Microsoft Edge Update/Proxy Server</span></span>
- <span data-ttu-id="2a2a2-497">Nome file ADMX Criteri di gruppo: msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="2a2a2-497">GP ADMX file name: msedgeupdate.admx</span></span>
##### <a name="windows-registry-settings"></a><span data-ttu-id="2a2a2-498">Impostazioni del Registro di sistema di Windows</span><span class="sxs-lookup"><span data-stu-id="2a2a2-498">Windows Registry Settings</span></span>
- <span data-ttu-id="2a2a2-499">Percorso: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="2a2a2-499">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="2a2a2-500">Nome valore: ProxyPacUrl</span><span class="sxs-lookup"><span data-stu-id="2a2a2-500">Value Name: ProxyPacUrl</span></span>
- <span data-ttu-id="2a2a2-501">Tipo valore: REG_SZ</span><span class="sxs-lookup"><span data-stu-id="2a2a2-501">Value Type: REG_SZ</span></span>
##### <a name="example-value"></a><span data-ttu-id="2a2a2-502">Valore di esempio</span><span class="sxs-lookup"><span data-stu-id="2a2a2-502">Example value:</span></span>
```
https://www.microsoft.com
```
[<span data-ttu-id="2a2a2-503">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="2a2a2-503">Back to top</span></span>](#microsoft-edge---update-policies)


### <a name="proxyserver"></a><span data-ttu-id="2a2a2-504">ProxyServer</span><span class="sxs-lookup"><span data-stu-id="2a2a2-504">ProxyServer</span></span>
#### <a name="address-or-url-of-proxy-server"></a><span data-ttu-id="2a2a2-505">Indirizzo o URL del server proxy</span><span class="sxs-lookup"><span data-stu-id="2a2a2-505">Address or URL of proxy server</span></span>
><span data-ttu-id="2a2a2-506">Microsoft Edge Update 1.3.21.81 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="2a2a2-506">Microsoft Edge Update 1.3.21.81 and later</span></span>

#### <a name="description"></a><span data-ttu-id="2a2a2-507">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2a2a2-507">Description</span></span>
<span data-ttu-id="2a2a2-508">Consente di specificare l'URL del server proxy per l'uso da parte di Microsoft Edge Update.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-508">Allows you to specify the URL of the proxy server for Microsoft Edge Update to use.</span></span>

  <span data-ttu-id="2a2a2-509">Se abiliti questo criterio, puoi impostare l'URL del server proxy usato da Microsoft Edge Update nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-509">If you enable this policy, you can set the proxy server URL used by Microsoft Edge Update in your organization.</span></span>

  <span data-ttu-id="2a2a2-510">Questo criterio viene applicato solo se sono state selezionate impostazioni proxy manuali nel criterio "[Scegliere come specificare le impostazioni del server proxy](#proxymode)".</span><span class="sxs-lookup"><span data-stu-id="2a2a2-510">This policy is applied only if you have selected manual proxy settings in the '[Choose how to specify proxy server settings](#proxymode)' policy.</span></span>

  <span data-ttu-id="2a2a2-511">Non configurare questo criterio se hai selezionato un'impostazione proxy diversa da quella manuale nel criterio "[Scegliere come specificare le impostazioni del server proxy](#proxymode)".</span><span class="sxs-lookup"><span data-stu-id="2a2a2-511">Don't configure this policy if you have selected a proxy setting other than manual in the '[Choose how to specify proxy server settings](#proxymode)' policy.</span></span>
#### <a name="windows-information-and-settings"></a><span data-ttu-id="2a2a2-512">Informazioni e impostazioni di Windows</span><span class="sxs-lookup"><span data-stu-id="2a2a2-512">Windows information and settings</span></span>
##### <a name="group-policy-admx-info"></a><span data-ttu-id="2a2a2-513">Info su Criteri di gruppo (ADMX)</span><span class="sxs-lookup"><span data-stu-id="2a2a2-513">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="2a2a2-514">Nome univoco Criteri di gruppo: ProxyServer</span><span class="sxs-lookup"><span data-stu-id="2a2a2-514">GP unique name: ProxyServer</span></span>
- <span data-ttu-id="2a2a2-515">Nome Criteri di gruppo: Indirizzo o URL del server proxy</span><span class="sxs-lookup"><span data-stu-id="2a2a2-515">GP name: Address or URL of proxy server</span></span>
- <span data-ttu-id="2a2a2-516">Percorso Criteri di gruppo: Modelli amministrativi/Microsoft Edge Update/Server proxy</span><span class="sxs-lookup"><span data-stu-id="2a2a2-516">GP path: Administrative Templates/Microsoft Edge Update/Proxy Server</span></span>
- <span data-ttu-id="2a2a2-517">Nome file ADMX Criteri di gruppo: msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="2a2a2-517">GP ADMX file name: msedgeupdate.admx</span></span>
##### <a name="windows-registry-settings"></a><span data-ttu-id="2a2a2-518">Impostazioni del Registro di sistema di Windows</span><span class="sxs-lookup"><span data-stu-id="2a2a2-518">Windows Registry Settings</span></span>
- <span data-ttu-id="2a2a2-519">Percorso: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="2a2a2-519">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="2a2a2-520">Nome valore: ProxyServer</span><span class="sxs-lookup"><span data-stu-id="2a2a2-520">Value Name: ProxyServer</span></span>
- <span data-ttu-id="2a2a2-521">Tipo valore: REG_SZ</span><span class="sxs-lookup"><span data-stu-id="2a2a2-521">Value Type: REG_SZ</span></span>
##### <a name="example-value"></a><span data-ttu-id="2a2a2-522">Valore di esempio</span><span class="sxs-lookup"><span data-stu-id="2a2a2-522">Example value:</span></span>
```
https://www.microsoft.com
```
[<span data-ttu-id="2a2a2-523">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="2a2a2-523">Back to top</span></span>](#microsoft-edge---update-policies)


## <a name="microsoft-edge-webview-policies"></a><span data-ttu-id="2a2a2-524">Criteri di Microsoft Edge WebView</span><span class="sxs-lookup"><span data-stu-id="2a2a2-524">Microsoft Edge WebView policies</span></span>

[<span data-ttu-id="2a2a2-525">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="2a2a2-525">Back to top</span></span>](#microsoft-edge---update-policies)
### <a name="install-webview"></a><span data-ttu-id="2a2a2-526">Installa (WebView)</span><span class="sxs-lookup"><span data-stu-id="2a2a2-526">Install (WebView)</span></span>
#### <a name="allow-installation"></a><span data-ttu-id="2a2a2-527">Consenti installazione</span><span class="sxs-lookup"><span data-stu-id="2a2a2-527">Allow installation</span></span>
><span data-ttu-id="2a2a2-528">Microsoft Edge Update 1.3.127.1 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="2a2a2-528">Microsoft Edge Update 1.3.127.1 and later</span></span>

#### <a name="description"></a><span data-ttu-id="2a2a2-529">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2a2a2-529">Description</span></span>
<span data-ttu-id="2a2a2-530">Consente di specificare se è possibile installare Microsoft Edge WebView tramite Microsoft Edge Update.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-530">Lets you specify whether Microsoft Edge WebView can be installed using Microsoft Edge Update.</span></span>

  - <span data-ttu-id="2a2a2-531">Abilitando questo criterio, gli utenti possono installare Microsoft Edge WebView tramite Microsoft Edge Update.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-531">If you enable this policy, users can install Microsoft Edge WebView through Microsoft Edge Update.</span></span>
  - <span data-ttu-id="2a2a2-532">Disabilitando questo criterio, gli utenti non possono installare Microsoft Edge WebView tramite Microsoft Edge Update.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-532">If you disable this policy, users cannot install Microsoft Edge WebView through Microsoft Edge Update.</span></span>
  - <span data-ttu-id="2a2a2-533">Non configurando questo criterio, la configurazione del criterio "[Consenti installazione predefinita](#installdefault)" determina se gli utenti possono installare Microsoft Edge WebView tramite Microsoft Edge Update.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-533">If you don't configure this policy, the '[Allow installation default](#installdefault)' policy configuration determines whether users can install Microsoft Edge WebView through Microsoft Edge Update.</span></span>
#### <a name="windows-information-and-settings"></a><span data-ttu-id="2a2a2-534">Informazioni e impostazioni di Windows</span><span class="sxs-lookup"><span data-stu-id="2a2a2-534">Windows information and settings</span></span>
##### <a name="group-policy-admx-info"></a><span data-ttu-id="2a2a2-535">Info su Criteri di gruppo (ADMX)</span><span class="sxs-lookup"><span data-stu-id="2a2a2-535">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="2a2a2-536">Nome univoco Criteri di gruppo: Install</span><span class="sxs-lookup"><span data-stu-id="2a2a2-536">GP unique name: Install</span></span>
- <span data-ttu-id="2a2a2-537">Nome Criteri di gruppo: Consenti installazione</span><span class="sxs-lookup"><span data-stu-id="2a2a2-537">GP name: Allow installation</span></span>
- <span data-ttu-id="2a2a2-538">Percorso Criteri di gruppo: Modelli amministrativi/Microsoft Edge Update/Microsoft Edge WebView</span><span class="sxs-lookup"><span data-stu-id="2a2a2-538">GP path: Administrative Templates/Microsoft Edge Update/Microsoft Edge WebView</span></span>
- <span data-ttu-id="2a2a2-539">Nome file ADMX Criteri di gruppo: msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="2a2a2-539">GP ADMX file name: msedgeupdate.admx</span></span>
##### <a name="windows-registry-settings"></a><span data-ttu-id="2a2a2-540">Impostazioni del Registro di sistema di Windows</span><span class="sxs-lookup"><span data-stu-id="2a2a2-540">Windows Registry Settings</span></span>
- <span data-ttu-id="2a2a2-541">Percorso: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="2a2a2-541">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="2a2a2-542">Nome:</span><span class="sxs-lookup"><span data-stu-id="2a2a2-542">Value Name:</span></span> 
  - <span data-ttu-id="2a2a2-543">Install{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}</span><span class="sxs-lookup"><span data-stu-id="2a2a2-543">Install{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}</span></span>
- <span data-ttu-id="2a2a2-544">Tipo valore: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="2a2a2-544">Value Type: REG_DWORD</span></span>
##### <a name="example-value"></a><span data-ttu-id="2a2a2-545">Valore di esempio</span><span class="sxs-lookup"><span data-stu-id="2a2a2-545">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="2a2a2-546">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="2a2a2-546">Back to top</span></span>](#microsoft-edge---update-policies)


### <a name="update-webview"></a><span data-ttu-id="2a2a2-547">Aggiornameto (WebView)</span><span class="sxs-lookup"><span data-stu-id="2a2a2-547">Update (WebView)</span></span>
#### <a name="update-policy-override"></a><span data-ttu-id="2a2a2-548">Sostituzione dei criteri di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="2a2a2-548">Update policy override</span></span>
><span data-ttu-id="2a2a2-549">Microsoft Edge Update 1.3.127.1 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="2a2a2-549">Microsoft Edge Update 1.3.127.1 and later</span></span>

#### <a name="description"></a><span data-ttu-id="2a2a2-550">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2a2a2-550">Description</span></span>
<span data-ttu-id="2a2a2-551">Consente di specificare se abilitare gli aggiornamenti automatici per Microsoft Edge WebView.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-551">Lets you specify whether or not automatic updates are enabled for Microsoft Edge WebView.</span></span> <span data-ttu-id="2a2a2-552">Microsoft Edge WebView è una componente usata dalle applicazioni per visualizzare il contenuto Web.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-552">Microsoft Edge WebView is a component used by applications to display web content.</span></span>
<span data-ttu-id="2a2a2-553">Gli aggiornamenti automatici sono abilitati per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-553">Automatic updates are enabled by default.</span></span> <span data-ttu-id="2a2a2-554">Disabilitando gli aggiornamenti automatici per Microsoft Edge WebView potrebbero verificarsi problemi di compatibilità con le applicazioni che dipendono da questa componente.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-554">Disabling automatic updates for Microsoft Edge WebView might cause compatibility issues with applications that depend on this component.</span></span>

  <span data-ttu-id="2a2a2-555">Abilitando questo criterio, Microsoft Edge Update gestisce gli aggiornamenti di Microsoft Edge WebView in base alla configurazione delle seguenti opzioni:</span><span class="sxs-lookup"><span data-stu-id="2a2a2-555">If you enable this policy, Microsoft Edge Update handles Microsoft Edge WebView updates according to how you configure the following options:</span></span>
  - <span data-ttu-id="2a2a2-556">Consenti sempre gli aggiornamenti: gli aggiornamenti vengono scaricati e applicati automaticamente</span><span class="sxs-lookup"><span data-stu-id="2a2a2-556">Always allow updates: Updates are automatically downloaded and applied</span></span>
  - <span data-ttu-id="2a2a2-557">Aggiornamenti disabilitati: gli aggiornamenti non vengono mai scaricati o applicati</span><span class="sxs-lookup"><span data-stu-id="2a2a2-557">Updates disabled: Updates are never downloaded or applied</span></span>

  <span data-ttu-id="2a2a2-558">Non abilitando questo criterio, gli aggiornamenti verranno scaricati e applicati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="2a2a2-558">If you don't enable this policy, updates are automatically downloaded and applied.</span></span>
#### <a name="windows-information-and-settings"></a><span data-ttu-id="2a2a2-559">Informazioni e impostazioni di Windows</span><span class="sxs-lookup"><span data-stu-id="2a2a2-559">Windows information and settings</span></span>
##### <a name="group-policy-admx-info"></a><span data-ttu-id="2a2a2-560">Info su Criteri di gruppo (ADMX)</span><span class="sxs-lookup"><span data-stu-id="2a2a2-560">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="2a2a2-561">Nome univoco Criteri di gruppo: Update</span><span class="sxs-lookup"><span data-stu-id="2a2a2-561">GP unique name: Update</span></span>
- <span data-ttu-id="2a2a2-562">Nome Criteri di gruppo: Sostituzione dei criteri di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="2a2a2-562">GP name: Update policy override</span></span>
- <span data-ttu-id="2a2a2-563">Percorso Criteri di gruppo: Modelli amministrativi/Microsoft Edge Update/Microsoft Edge WebView</span><span class="sxs-lookup"><span data-stu-id="2a2a2-563">GP path: Administrative Templates/Microsoft Edge Update/Microsoft Edge WebView</span></span>
- <span data-ttu-id="2a2a2-564">Nome file ADMX Criteri di gruppo: msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="2a2a2-564">GP ADMX file name: msedgeupdate.admx</span></span>
##### <a name="windows-registry-settings"></a><span data-ttu-id="2a2a2-565">Impostazioni del Registro di sistema di Windows</span><span class="sxs-lookup"><span data-stu-id="2a2a2-565">Windows Registry Settings</span></span>
- <span data-ttu-id="2a2a2-566">Percorso: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="2a2a2-566">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="2a2a2-567">Nome:</span><span class="sxs-lookup"><span data-stu-id="2a2a2-567">Value Name:</span></span> 
  - <span data-ttu-id="2a2a2-568">Update{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}</span><span class="sxs-lookup"><span data-stu-id="2a2a2-568">Update{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}</span></span>
- <span data-ttu-id="2a2a2-569">Tipo valore: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="2a2a2-569">Value Type: REG_DWORD</span></span>
##### <a name="example-value"></a><span data-ttu-id="2a2a2-570">Valore di esempio</span><span class="sxs-lookup"><span data-stu-id="2a2a2-570">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="2a2a2-571">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="2a2a2-571">Back to top</span></span>](#microsoft-edge---update-policies)


## <a name="see-also"></a><span data-ttu-id="2a2a2-572">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="2a2a2-572">See also</span></span>
  - [<span data-ttu-id="2a2a2-573">Configurazione di Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="2a2a2-573">Configuring Microsoft Edge</span></span>](configure-microsoft-edge.md)
  - [<span data-ttu-id="2a2a2-574">Pagina di destinazione di Microsoft Edge in modalità Enterprise</span><span class="sxs-lookup"><span data-stu-id="2a2a2-574">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
