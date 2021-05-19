---
title: Documentazione sui criteri di Microsoft Edge Update
ms.author: stmoody
author: brianalt-msft
manager: tahills
ms.date: 10/07/2020
audience: ITPro
ms.topic: reference
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
ms.custom: ''
description: Documentazione per tutti i criteri supportati da Microsoft Edge Update
ms.openlocfilehash: feb7859f062ae39e2bbfe08d8e478386defb85cf
ms.sourcegitcommit: 4e6188ade942ca6fd599a4ce1c8e0d90d3d03399
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/09/2020
ms.locfileid: "11105570"
---
# <span data-ttu-id="1efcf-103">Microsoft Edge - Criteri di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="1efcf-103">Microsoft Edge - Update policies</span></span>
<span data-ttu-id="1efcf-104">La versione più recente di Microsoft Edge include i seguenti criteri che puoi usare per controllare come e quando Microsoft Edge viene aggiornato.</span><span class="sxs-lookup"><span data-stu-id="1efcf-104">The latest version of Microsoft Edge includes the following policies that you can use to control how and when Microsoft Edge is updated.</span></span>

<span data-ttu-id="1efcf-105">Per informazioni su altri criteri disponibili in Microsoft Edge, vedi [Riferimento ai criteri del browser Microsoft Edge](microsoft-edge-policies.md)</span><span class="sxs-lookup"><span data-stu-id="1efcf-105">For information about other policies available in Microsoft Edge, check out [Microsoft Edge browser policy reference](microsoft-edge-policies.md)</span></span>
> [!NOTE]
> <span data-ttu-id="1efcf-106">Questo articolo si applica a Microsoft Edge versione 77 o successiva.</span><span class="sxs-lookup"><span data-stu-id="1efcf-106">This article applies to Microsoft Edge version 77 or later.</span></span>
## <span data-ttu-id="1efcf-107">Criteri disponibili</span><span class="sxs-lookup"><span data-stu-id="1efcf-107">Available policies</span></span>
<span data-ttu-id="1efcf-108">In queste tabelle sono elencati tutti i criteri di gruppo correlati agli aggiornamenti disponibili in questa versione di Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="1efcf-108">These tables lists all of the update-related group policies available in this release of Microsoft Edge.</span></span> <span data-ttu-id="1efcf-109">Usa i collegamenti nella tabella per ottenere altri dettagli su criteri specifici.</span><span class="sxs-lookup"><span data-stu-id="1efcf-109">Use the links in the table to get more details about specific policies.</span></span>

|||
|-|-|
|[<span data-ttu-id="1efcf-110">Applicazioni</span><span class="sxs-lookup"><span data-stu-id="1efcf-110">Applications</span></span>](#applications)|[<span data-ttu-id="1efcf-111">Preferenze</span><span class="sxs-lookup"><span data-stu-id="1efcf-111">Preferences</span></span>](#preferences)|
|[<span data-ttu-id="1efcf-112">Server proxy</span><span class="sxs-lookup"><span data-stu-id="1efcf-112">Proxy Server</span></span>](#proxy-server)|[<span data-ttu-id="1efcf-113">Microsoft Edge WebView</span><span class="sxs-lookup"><span data-stu-id="1efcf-113">Microsoft Edge WebView</span></span>](#microsoft-edge-webview)|

### [<span data-ttu-id="1efcf-114">Applicazioni</span><span class="sxs-lookup"><span data-stu-id="1efcf-114">Applications</span></span>](#applications-policies)
|<span data-ttu-id="1efcf-115">Nome criterio</span><span class="sxs-lookup"><span data-stu-id="1efcf-115">Policy Name</span></span>|<span data-ttu-id="1efcf-116">Didascalia</span><span class="sxs-lookup"><span data-stu-id="1efcf-116">Caption</span></span>|
|-|-|
|[<span data-ttu-id="1efcf-117">InstallDefault</span><span class="sxs-lookup"><span data-stu-id="1efcf-117">InstallDefault</span></span>](#installdefault)|<span data-ttu-id="1efcf-118">Consenti installazione predefinita</span><span class="sxs-lookup"><span data-stu-id="1efcf-118">Allow installation default</span></span>|
|[<span data-ttu-id="1efcf-119">UpdateDefault</span><span class="sxs-lookup"><span data-stu-id="1efcf-119">UpdateDefault</span></span>](#updatedefault)|<span data-ttu-id="1efcf-120">Sostituzione dei criteri di aggiornamento predefinita</span><span class="sxs-lookup"><span data-stu-id="1efcf-120">Update policy override default</span></span>|
|[<span data-ttu-id="1efcf-121">Install</span><span class="sxs-lookup"><span data-stu-id="1efcf-121">Install</span></span>](#install)|<span data-ttu-id="1efcf-122">Consenti installazione (per canale)</span><span class="sxs-lookup"><span data-stu-id="1efcf-122">Allow installation (per channel)</span></span>|
|[<span data-ttu-id="1efcf-123">Update</span><span class="sxs-lookup"><span data-stu-id="1efcf-123">Update</span></span>](#update)|<span data-ttu-id="1efcf-124">Sostituzione dei criteri di aggiornamento (per canale)</span><span class="sxs-lookup"><span data-stu-id="1efcf-124">Update policy override (per channel)</span></span>|
|[<span data-ttu-id="1efcf-125">Allowsxs</span><span class="sxs-lookup"><span data-stu-id="1efcf-125">Allowsxs</span></span>](#allowsxs)|<span data-ttu-id="1efcf-126">Consenti esperienza browser Microsoft Edge affiancata</span><span class="sxs-lookup"><span data-stu-id="1efcf-126">Allow Microsoft Edge Side by Side browser experience</span></span>|
|[<span data-ttu-id="1efcf-127">CreateDesktopShortcutDefault</span><span class="sxs-lookup"><span data-stu-id="1efcf-127">CreateDesktopShortcutDefault</span></span>](#createdesktopshortcutdefault)|<span data-ttu-id="1efcf-128">Impedisce la creazione di un collegamento sul desktop a seguito dell'installazione predefinita</span><span class="sxs-lookup"><span data-stu-id="1efcf-128">Prevent Desktop Shortcut creation upon install default</span></span>|
|[<span data-ttu-id="1efcf-129">CreateDesktopShortcut</span><span class="sxs-lookup"><span data-stu-id="1efcf-129">CreateDesktopShortcut</span></span>](#createdesktopshortcut)|<span data-ttu-id="1efcf-130">Impedisce la creazione di un collegamento sul desktop a seguito dell'installazione (per canale)</span><span class="sxs-lookup"><span data-stu-id="1efcf-130">Prevent Desktop Shortcut creation upon install (per channel)</span></span>|
|[<span data-ttu-id="1efcf-131">RollbackToTargetVersion</span><span class="sxs-lookup"><span data-stu-id="1efcf-131">RollbackToTargetVersion</span></span>](#rollbacktotargetversion)|<span data-ttu-id="1efcf-132">Eseguire il ripristino dello stato precedente della versione di destinazione (per canale)</span><span class="sxs-lookup"><span data-stu-id="1efcf-132">Rollback to Target version (per channel)</span></span>|
|[<span data-ttu-id="1efcf-133">TargetVersionPrefix</span><span class="sxs-lookup"><span data-stu-id="1efcf-133">TargetVersionPrefix</span></span>](#targetversionprefix)|<span data-ttu-id="1efcf-134">Sostituzione della versione di destinazione (in base al canale)</span><span class="sxs-lookup"><span data-stu-id="1efcf-134">Target version override (per channel)</span></span>|

### [<span data-ttu-id="1efcf-135">Preferenze</span><span class="sxs-lookup"><span data-stu-id="1efcf-135">Preferences</span></span>](#preferences-policies)
|<span data-ttu-id="1efcf-136">Nome criterio</span><span class="sxs-lookup"><span data-stu-id="1efcf-136">Policy Name</span></span>|<span data-ttu-id="1efcf-137">Didascalia</span><span class="sxs-lookup"><span data-stu-id="1efcf-137">Caption</span></span>|
|-|-|
|[<span data-ttu-id="1efcf-138">AutoUpdateCheckPeriodMinutes</span><span class="sxs-lookup"><span data-stu-id="1efcf-138">AutoUpdateCheckPeriodMinutes</span></span>](#autoupdatecheckperiodminutes)|<span data-ttu-id="1efcf-139">Sostituzione del periodo di controllo dell'aggiornamento automatico</span><span class="sxs-lookup"><span data-stu-id="1efcf-139">Auto-update check period override</span></span>|
|[<span data-ttu-id="1efcf-140">UpdatesSuppressed</span><span class="sxs-lookup"><span data-stu-id="1efcf-140">UpdatesSuppressed</span></span>](#updatessuppressed)|<span data-ttu-id="1efcf-141">Periodo di tempo in ogni giorno per eliminare il controllo dell'aggiornamento automatico</span><span class="sxs-lookup"><span data-stu-id="1efcf-141">Time period in each day to suppress auto-update check</span></span>|

### [<span data-ttu-id="1efcf-142">Server proxy</span><span class="sxs-lookup"><span data-stu-id="1efcf-142">Proxy Server</span></span>](#proxy-server-policies)
|<span data-ttu-id="1efcf-143">Nome criterio</span><span class="sxs-lookup"><span data-stu-id="1efcf-143">Policy Name</span></span>|<span data-ttu-id="1efcf-144">Didascalia</span><span class="sxs-lookup"><span data-stu-id="1efcf-144">Caption</span></span>|
|-|-|
|[<span data-ttu-id="1efcf-145">ProxyMode</span><span class="sxs-lookup"><span data-stu-id="1efcf-145">ProxyMode</span></span>](#proxymode)|<span data-ttu-id="1efcf-146">Scegliere come specificare le impostazioni del server proxy</span><span class="sxs-lookup"><span data-stu-id="1efcf-146">Choose how to specify proxy server settings</span></span>|
|[<span data-ttu-id="1efcf-147">ProxyPacUrl</span><span class="sxs-lookup"><span data-stu-id="1efcf-147">ProxyPacUrl</span></span>](#proxypacurl)|<span data-ttu-id="1efcf-148">URL di un file PAC del proxy</span><span class="sxs-lookup"><span data-stu-id="1efcf-148">URL to a proxy .pac file</span></span>|
|[<span data-ttu-id="1efcf-149">ProxyServer</span><span class="sxs-lookup"><span data-stu-id="1efcf-149">ProxyServer</span></span>](#proxyserver)|<span data-ttu-id="1efcf-150">Indirizzo o URL del server proxy</span><span class="sxs-lookup"><span data-stu-id="1efcf-150">Address or URL of proxy server</span></span>|

### [<span data-ttu-id="1efcf-151">Microsoft Edge WebView</span><span class="sxs-lookup"><span data-stu-id="1efcf-151">Microsoft Edge WebView</span></span>](#microsoft-edge-webview-policies)
|<span data-ttu-id="1efcf-152">Nome criterio</span><span class="sxs-lookup"><span data-stu-id="1efcf-152">Policy Name</span></span>|<span data-ttu-id="1efcf-153">Didascalia</span><span class="sxs-lookup"><span data-stu-id="1efcf-153">Caption</span></span>|
|-|-|
|[<span data-ttu-id="1efcf-154">Installazione</span><span class="sxs-lookup"><span data-stu-id="1efcf-154">Install</span></span>](#install-webview)|<span data-ttu-id="1efcf-155">Consenti installazione</span><span class="sxs-lookup"><span data-stu-id="1efcf-155">Allow installation</span></span>|
|[<span data-ttu-id="1efcf-156">Aggiornamenti</span><span class="sxs-lookup"><span data-stu-id="1efcf-156">Update</span></span>](#update-webview)|<span data-ttu-id="1efcf-157">Sostituzione dei criteri di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="1efcf-157">Update policy override</span></span>|

## <span data-ttu-id="1efcf-158">Criteri delle applicazioni</span><span class="sxs-lookup"><span data-stu-id="1efcf-158">Applications policies</span></span>

[<span data-ttu-id="1efcf-159">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="1efcf-159">Back to top</span></span>](#microsoft-edge---update-policies)
### <span data-ttu-id="1efcf-160">InstallDefault</span><span class="sxs-lookup"><span data-stu-id="1efcf-160">InstallDefault</span></span>
#### <span data-ttu-id="1efcf-161">Consenti installazione predefinita</span><span class="sxs-lookup"><span data-stu-id="1efcf-161">Allow installation default</span></span>
><span data-ttu-id="1efcf-162">Microsoft Edge Update 1.2.145.5 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="1efcf-162">Microsoft Edge Update 1.2.145.5 and later</span></span>

#### <span data-ttu-id="1efcf-163">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1efcf-163">Description</span></span>
<span data-ttu-id="1efcf-164">È possibile specificare il comportamento predefinito di tutti i canali per consentire o bloccare Microsoft Edge nei dispositivi collegati al dominio.</span><span class="sxs-lookup"><span data-stu-id="1efcf-164">You can specify the default behavior of all channels to allow or block Microsoft Edge on domain-joined devices.</span></span>

<span data-ttu-id="1efcf-165">È possibile sostituire il criterio per i singoli canali abilitando il criterio "[Consenti installazione](#install)" per i canali specifici.</span><span class="sxs-lookup"><span data-stu-id="1efcf-165">You can override this policy for individual channels by enabling the '[Allow installation](#install)' policy for specific channels.</span></span>

<span data-ttu-id="1efcf-166">Disabilitando questo criterio, l'installazione di Microsoft Edge verrà bloccata.</span><span class="sxs-lookup"><span data-stu-id="1efcf-166">If you disable this policy, the installation of Microsoft Edge is blocked.</span></span> <span data-ttu-id="1efcf-167">Questo riguarda solo l'installazione del software Microsoft Edge quando il criterio "[Consenti l'installazione](#install)" è impostato su Non configurato.</span><span class="sxs-lookup"><span data-stu-id="1efcf-167">This only affects the installation of Microsoft Edge software when the '[Allow installation](#install)' policy is set to Not Configured.</span></span>

<span data-ttu-id="1efcf-168">Questo criterio non impedisce l'esecuzione di Microsoft Edge Update, né impedisce l'installazione del software Microsoft Edge attraverso altri metodi.</span><span class="sxs-lookup"><span data-stu-id="1efcf-168">This policy doesn't prevent Microsoft Edge Update from running or prevent users from installing Microsoft Edge software using other methods.</span></span>

<span data-ttu-id="1efcf-169">Questo criterio è disponibile solo nelle istanze di Windows che fanno parte di un dominio Microsoft® Active Directory®.</span><span class="sxs-lookup"><span data-stu-id="1efcf-169">This policy is available only on Windows instances that are joined to a Microsoft® Active Directory® domain.</span></span>
#### <span data-ttu-id="1efcf-170">Informazioni e impostazioni di Windows</span><span class="sxs-lookup"><span data-stu-id="1efcf-170">Windows information and settings</span></span>
##### <span data-ttu-id="1efcf-171">Info su Criteri di gruppo (ADMX)</span><span class="sxs-lookup"><span data-stu-id="1efcf-171">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="1efcf-172">Nome univoco Criteri di gruppo: InstallDefault</span><span class="sxs-lookup"><span data-stu-id="1efcf-172">GP unique name: InstallDefault</span></span>
- <span data-ttu-id="1efcf-173">Nome Criteri di gruppo: Consenti installazione predefinita</span><span class="sxs-lookup"><span data-stu-id="1efcf-173">GP name: Allow installation default</span></span>
- <span data-ttu-id="1efcf-174">Percorso Criteri di gruppo: Modelli amministrativi/Microsoft Edge Update/Applicazioni</span><span class="sxs-lookup"><span data-stu-id="1efcf-174">GP path: Administrative Templates/Microsoft Edge Update/Applications</span></span>
- <span data-ttu-id="1efcf-175">Nome file ADMX Criteri di gruppo: msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="1efcf-175">GP ADMX file name: msedgeupdate.admx</span></span>
##### <span data-ttu-id="1efcf-176">Impostazioni del Registro di sistema di Windows</span><span class="sxs-lookup"><span data-stu-id="1efcf-176">Windows Registry Settings</span></span>
- <span data-ttu-id="1efcf-177">Percorso: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="1efcf-177">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="1efcf-178">Nome valore: InstallDefault</span><span class="sxs-lookup"><span data-stu-id="1efcf-178">Value Name: InstallDefault</span></span>
- <span data-ttu-id="1efcf-179">Tipo valore: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="1efcf-179">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="1efcf-180">Valore di esempio</span><span class="sxs-lookup"><span data-stu-id="1efcf-180">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="1efcf-181">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="1efcf-181">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="1efcf-182">UpdateDefault</span><span class="sxs-lookup"><span data-stu-id="1efcf-182">UpdateDefault</span></span>
#### <span data-ttu-id="1efcf-183">Sostituzione dei criteri di aggiornamento predefinita</span><span class="sxs-lookup"><span data-stu-id="1efcf-183">Update policy override default</span></span>
><span data-ttu-id="1efcf-184">Microsoft Edge Update 1.2.145.5 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="1efcf-184">Microsoft Edge Update 1.2.145.5 and later</span></span>

#### <span data-ttu-id="1efcf-185">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1efcf-185">Description</span></span>
<span data-ttu-id="1efcf-186">Consente di specificare il comportamento predefinito per tutti i canali in relazione al modo in cui Microsoft Edge Update gestisce gli aggiornamenti disponibili per Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="1efcf-186">Lets you specify the default behavior for all channels concerning the way Microsoft Edge Update handles available updates for Microsoft Edge.</span></span> <span data-ttu-id="1efcf-187">Può essere sostituito per singoli canali specificando il criterio "[Sostituzione dei criteri di aggiornamento](#update)" per i canali specifici.</span><span class="sxs-lookup"><span data-stu-id="1efcf-187">Can be overridden for individual channels by specifying the '[Update policy override](#update)' policy for those specific channels.</span></span>

  <span data-ttu-id="1efcf-188">Se abiliti questo criterio, Microsoft Edge Update gestisce gli aggiornamenti Microsoft Edge in base alla configurazione delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1efcf-188">If you enable this policy, Microsoft Edge Update handles Microsoft Edge updates according to how you configure the following options:</span></span>
   - <span data-ttu-id="1efcf-189">Consenti sempre gli aggiornamenti: gli aggiornamenti vengono sempre applicati quando vengono rilevati, in seguito a un controllo periodico o manuale.</span><span class="sxs-lookup"><span data-stu-id="1efcf-189">Always allow updates: Updates are always applied when found, either by periodic update check or by a manual update check.</span></span>
   - <span data-ttu-id="1efcf-190">Solo aggiornamenti automatici: gli aggiornamenti vengono applicati solo quando vengono rilevati in seguito al controllo periodico.</span><span class="sxs-lookup"><span data-stu-id="1efcf-190">Automatic silent updates only: Updates are applied only when they're found by the periodic update check.</span></span>
   - <span data-ttu-id="1efcf-191">Solo aggiornamenti manuali: gli aggiornamenti vengono applicati solo quando gli utenti eseguono un controllo manuale.</span><span class="sxs-lookup"><span data-stu-id="1efcf-191">Manual updates only: Updates are applied only when the user runs a manual update check.</span></span>
   - <span data-ttu-id="1efcf-192">Aggiornamenti disabilitati: gli aggiornamenti non vengono mai applicati.</span><span class="sxs-lookup"><span data-stu-id="1efcf-192">Updates disabled: Updates are never applied.</span></span>

  <span data-ttu-id="1efcf-193">Se selezioni gli aggiornamenti manuali, verifica di controllare periodicamente la disponibilità degli aggiornamenti tramite il meccanismo di aggiornamento manuale dell'app, se disponibile.</span><span class="sxs-lookup"><span data-stu-id="1efcf-193">If you select manual updates, make sure you periodically check for updates by using the app's manual update mechanism, if available.</span></span> <span data-ttu-id="1efcf-194">Se disabiliti gli aggiornamenti, verificane periodicamente la disponibilità e distribuiscili agli utenti.</span><span class="sxs-lookup"><span data-stu-id="1efcf-194">If you disable updates, periodically check for updates, and distribute them to users.</span></span>

  <span data-ttu-id="1efcf-195">Se non abiliti né configuri questo criterio, Microsoft Edge Update gestisce gli aggiornamenti disponibili, come indicato dal criterio "[Sostituzione dei criteri di aggiornamento](#update)".</span><span class="sxs-lookup"><span data-stu-id="1efcf-195">If you don't enable and configure this policy, Microsoft Edge Update handles available updates as specified by the '[Update policy override](#update)' policy.</span></span>

  <span data-ttu-id="1efcf-196">Questo criterio è disponibile solo nelle istanze di Windows che fanno parte di un dominio Microsoft® Active Directory®.</span><span class="sxs-lookup"><span data-stu-id="1efcf-196">This policy is available only on Windows instances that are joined to a Microsoft® Active Directory® domain.</span></span>
#### <span data-ttu-id="1efcf-197">Informazioni e impostazioni di Windows</span><span class="sxs-lookup"><span data-stu-id="1efcf-197">Windows information and settings</span></span>
##### <span data-ttu-id="1efcf-198">Info su Criteri di gruppo (ADMX)</span><span class="sxs-lookup"><span data-stu-id="1efcf-198">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="1efcf-199">Nome univoco Criteri di gruppo: UpdateDefault</span><span class="sxs-lookup"><span data-stu-id="1efcf-199">GP unique name: UpdateDefault</span></span>
- <span data-ttu-id="1efcf-200">Nome Criteri di gruppo: Sostituzione dei criteri di aggiornamento predefinita</span><span class="sxs-lookup"><span data-stu-id="1efcf-200">GP name: Update policy override default</span></span>
- <span data-ttu-id="1efcf-201">Percorso Criteri di gruppo: Modelli amministrativi/Microsoft Edge Update/Applicazioni</span><span class="sxs-lookup"><span data-stu-id="1efcf-201">GP path: Administrative Templates/Microsoft Edge Update/Applications</span></span>
- <span data-ttu-id="1efcf-202">Nome file ADMX Criteri di gruppo: msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="1efcf-202">GP ADMX file name: msedgeupdate.admx</span></span>
##### <span data-ttu-id="1efcf-203">Impostazioni del Registro di sistema di Windows</span><span class="sxs-lookup"><span data-stu-id="1efcf-203">Windows Registry Settings</span></span>
- <span data-ttu-id="1efcf-204">Percorso: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="1efcf-204">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="1efcf-205">Nome valore: UpdateDefault</span><span class="sxs-lookup"><span data-stu-id="1efcf-205">Value Name: UpdateDefault</span></span>
- <span data-ttu-id="1efcf-206">Tipo valore: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="1efcf-206">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="1efcf-207">Valore di esempio</span><span class="sxs-lookup"><span data-stu-id="1efcf-207">Example value:</span></span>
```
0x00000003
```
[<span data-ttu-id="1efcf-208">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="1efcf-208">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="1efcf-209">Install</span><span class="sxs-lookup"><span data-stu-id="1efcf-209">Install</span></span>
#### <span data-ttu-id="1efcf-210">Consenti installazione</span><span class="sxs-lookup"><span data-stu-id="1efcf-210">Allow installation</span></span>
><span data-ttu-id="1efcf-211">Microsoft Edge Update 1.2.145.5 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="1efcf-211">Microsoft Edge Update 1.2.145.5 and later</span></span>

#### <span data-ttu-id="1efcf-212">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1efcf-212">Description</span></span>
<span data-ttu-id="1efcf-213">Specifica se è possibile installare un canale Microsoft Edge sui dispositivi collegati al dominio.</span><span class="sxs-lookup"><span data-stu-id="1efcf-213">Specifies whether a Microsoft Edge channel can be installed on domain-joined devices.</span></span>

  <span data-ttu-id="1efcf-214">Se abiliti questo criterio per un canale, Microsoft Edge non verrà bloccato dall'installazione.</span><span class="sxs-lookup"><span data-stu-id="1efcf-214">If you enable this policy for a channel, Microsoft Edge will not be blocked from installation.</span></span>

  <span data-ttu-id="1efcf-215">Se disabiliti questo criterio per un canale, Microsoft Edge verrà bloccato dall'installazione.</span><span class="sxs-lookup"><span data-stu-id="1efcf-215">If you disable this policy for a channel, Microsoft Edge will be blocked from installation.</span></span>

  <span data-ttu-id="1efcf-216">Se non configuri questo criterio per un canale, il criterio "[Consenti installazione predefinita](#installdefault)" determina se gli utenti possono installare il canale di Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="1efcf-216">If you don't configure this policy for a channel, the '[Allow installation default](#installdefault)' policy configuration determines whether users can install that channel of Microsoft Edge.</span></span>

  <span data-ttu-id="1efcf-217">Questo criterio è disponibile solo nelle istanze di Windows che fanno parte di un dominio Microsoft® Active Directory®.</span><span class="sxs-lookup"><span data-stu-id="1efcf-217">This policy is available only on Windows instances that are joined to a Microsoft® Active Directory® domain.</span></span>
#### <span data-ttu-id="1efcf-218">Informazioni e impostazioni di Windows</span><span class="sxs-lookup"><span data-stu-id="1efcf-218">Windows information and settings</span></span>
##### <span data-ttu-id="1efcf-219">Info su Criteri di gruppo (ADMX)</span><span class="sxs-lookup"><span data-stu-id="1efcf-219">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="1efcf-220">Nome univoco Criteri di gruppo: Install</span><span class="sxs-lookup"><span data-stu-id="1efcf-220">GP unique name: Install</span></span>
- <span data-ttu-id="1efcf-221">Nome Criteri di gruppo: Consenti installazione</span><span class="sxs-lookup"><span data-stu-id="1efcf-221">GP name: Allow installation</span></span>
- <span data-ttu-id="1efcf-222">Percorso Criteri di gruppo:</span><span class="sxs-lookup"><span data-stu-id="1efcf-222">GP path:</span></span> 
  - <span data-ttu-id="1efcf-223">Modelli amministrativi/Microsoft Edge Update/Applicazioni/Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="1efcf-223">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge</span></span>
  - <span data-ttu-id="1efcf-224">Modelli amministrativi/Microsoft Edge Update/Applicazioni/Microsoft Edge Beta</span><span class="sxs-lookup"><span data-stu-id="1efcf-224">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Beta</span></span>
  - <span data-ttu-id="1efcf-225">Modelli amministrativi/Microsoft Edge Update/Applicazioni/Microsoft Edge Canary</span><span class="sxs-lookup"><span data-stu-id="1efcf-225">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Canary</span></span>
  - <span data-ttu-id="1efcf-226">Modelli amministrativi/Microsoft Edge Update/Applicazioni/Microsoft Edge Dev</span><span class="sxs-lookup"><span data-stu-id="1efcf-226">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Dev</span></span>
- <span data-ttu-id="1efcf-227">Nome file ADMX Criteri di gruppo: msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="1efcf-227">GP ADMX file name: msedgeupdate.admx</span></span>
##### <span data-ttu-id="1efcf-228">Impostazioni del Registro di sistema di Windows</span><span class="sxs-lookup"><span data-stu-id="1efcf-228">Windows Registry Settings</span></span>
- <span data-ttu-id="1efcf-229">Percorso: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="1efcf-229">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="1efcf-230">Nome valore:</span><span class="sxs-lookup"><span data-stu-id="1efcf-230">Value Name:</span></span> 
  - <span data-ttu-id="1efcf-231">(Stabile): Install{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span><span class="sxs-lookup"><span data-stu-id="1efcf-231">(Stable): Install{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span></span>
  - <span data-ttu-id="1efcf-232">(Beta): Install{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span><span class="sxs-lookup"><span data-stu-id="1efcf-232">(Beta): Install{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span></span>
  - <span data-ttu-id="1efcf-233">(Canary): Install{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span><span class="sxs-lookup"><span data-stu-id="1efcf-233">(Canary): Install{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span></span>
  - <span data-ttu-id="1efcf-234">(Dev): Install{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span><span class="sxs-lookup"><span data-stu-id="1efcf-234">(Dev): Install{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span></span>
- <span data-ttu-id="1efcf-235">Tipo valore: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="1efcf-235">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="1efcf-236">Valore di esempio</span><span class="sxs-lookup"><span data-stu-id="1efcf-236">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="1efcf-237">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="1efcf-237">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="1efcf-238">Update</span><span class="sxs-lookup"><span data-stu-id="1efcf-238">Update</span></span>
#### <span data-ttu-id="1efcf-239">Sostituzione dei criteri di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="1efcf-239">Update policy override</span></span>
><span data-ttu-id="1efcf-240">Microsoft Edge Update 1.2.145.5 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="1efcf-240">Microsoft Edge Update 1.2.145.5 and later</span></span>

#### <span data-ttu-id="1efcf-241">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1efcf-241">Description</span></span>
<span data-ttu-id="1efcf-242">Specifica il modo in cui Microsoft Edge Update gestisce gli aggiornamenti disponibili da Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="1efcf-242">Specifies how Microsoft Edge Update handles available updates from Microsoft Edge.</span></span>

<span data-ttu-id="1efcf-243">Se abiliti questo criterio, Microsoft Edge Update gestisce gli aggiornamenti Microsoft Edge in base alla configurazione delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1efcf-243">If you enable this policy, Microsoft Edge Update handles Microsoft Edge updates according to how you configure the following options:</span></span>
  - <span data-ttu-id="1efcf-244">Consenti sempre gli aggiornamenti: gli aggiornamenti vengono sempre applicati quando vengono rilevati, in seguito a un controllo periodico o manuale.</span><span class="sxs-lookup"><span data-stu-id="1efcf-244">Always allow updates: Updates are always applied when found, either by periodic update check or by a manual update check.</span></span>
  - <span data-ttu-id="1efcf-245">Solo aggiornamenti automatici: gli aggiornamenti vengono applicati solo quando vengono rilevati in seguito al controllo periodico.</span><span class="sxs-lookup"><span data-stu-id="1efcf-245">Automatic silent updates only: Updates are applied only when they're found by the periodic update check.</span></span>
  - <span data-ttu-id="1efcf-246">Solo aggiornamenti manuali: gli aggiornamenti vengono applicati solo quando gli utenti eseguono un controllo manuale.</span><span class="sxs-lookup"><span data-stu-id="1efcf-246">Manual updates only: Updates are applied only when the user runs a manual update check.</span></span> <span data-ttu-id="1efcf-247">Non tutte le app forniscono un'interfaccia per questa opzione.</span><span class="sxs-lookup"><span data-stu-id="1efcf-247">(Not all apps provide an interface for this option.)</span></span>
  - <span data-ttu-id="1efcf-248">Aggiornamenti disabilitati: gli aggiornamenti non vengono mai applicati.</span><span class="sxs-lookup"><span data-stu-id="1efcf-248">Updates disabled: Updates are never applied.</span></span>

<span data-ttu-id="1efcf-249">Se selezioni gli aggiornamenti manuali, verifica di controllare periodicamente la disponibilità degli aggiornamenti tramite il meccanismo di aggiornamento manuale dell'app, se disponibile.</span><span class="sxs-lookup"><span data-stu-id="1efcf-249">If you select manual updates, make sure you periodically check for updates by using the app's manual update mechanism, if available.</span></span> <span data-ttu-id="1efcf-250">Se disabiliti gli aggiornamenti, verificane periodicamente la disponibilità e distribuiscili agli utenti.</span><span class="sxs-lookup"><span data-stu-id="1efcf-250">If you disable updates, periodically check for updates, and distribute them to users.</span></span>

<span data-ttu-id="1efcf-251">Se non abiliti né configuri questo criterio, Microsoft Edge Update gestisce gli aggiornamenti disponibili, come indicato dal criterio "[Sostituzione dei criteri di aggiornamento predefinita](#updatedefault)".</span><span class="sxs-lookup"><span data-stu-id="1efcf-251">If you don't enable and configure this policy, Microsoft Edge Update handles available updates as specified by the '[Update policy override default](#updatedefault)' policy.</span></span>

<span data-ttu-id="1efcf-252">Per altre informazioni, vedere [https://go.microsoft.com/fwlink/?linkid=2136406](https://go.microsoft.com/fwlink/?linkid=2136406).</span><span class="sxs-lookup"><span data-stu-id="1efcf-252">See [https://go.microsoft.com/fwlink/?linkid=2136406](https://go.microsoft.com/fwlink/?linkid=2136406) for more information.</span></span>

<span data-ttu-id="1efcf-253">Questo criterio è disponibile solo nelle istanze di Windows che fanno parte di un dominio Microsoft® Active Directory®.</span><span class="sxs-lookup"><span data-stu-id="1efcf-253">This policy is available only on Windows instances that are joined to a Microsoft® Active Directory® domain.</span></span>
#### <span data-ttu-id="1efcf-254">Informazioni e impostazioni di Windows</span><span class="sxs-lookup"><span data-stu-id="1efcf-254">Windows information and settings</span></span>
##### <span data-ttu-id="1efcf-255">Info su Criteri di gruppo (ADMX)</span><span class="sxs-lookup"><span data-stu-id="1efcf-255">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="1efcf-256">Nome univoco Criteri di gruppo: Update</span><span class="sxs-lookup"><span data-stu-id="1efcf-256">GP unique name: Update</span></span>
- <span data-ttu-id="1efcf-257">Nome Criteri di gruppo: Sostituzione dei criteri di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="1efcf-257">GP name: Update policy override</span></span>
- <span data-ttu-id="1efcf-258">Percorso Criteri di gruppo:</span><span class="sxs-lookup"><span data-stu-id="1efcf-258">GP path:</span></span> 
  - <span data-ttu-id="1efcf-259">Modelli amministrativi/Microsoft Edge Update/Applicazioni/Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="1efcf-259">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge</span></span>
  - <span data-ttu-id="1efcf-260">Modelli amministrativi/Microsoft Edge Update/Applicazioni/Microsoft Edge Beta</span><span class="sxs-lookup"><span data-stu-id="1efcf-260">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Beta</span></span>
  - <span data-ttu-id="1efcf-261">Modelli amministrativi/Microsoft Edge Update/Applicazioni/Microsoft Edge Canary</span><span class="sxs-lookup"><span data-stu-id="1efcf-261">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Canary</span></span>
  - <span data-ttu-id="1efcf-262">Modelli amministrativi/Microsoft Edge Update/Applicazioni/Microsoft Edge Dev</span><span class="sxs-lookup"><span data-stu-id="1efcf-262">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Dev</span></span>
- <span data-ttu-id="1efcf-263">Nome file ADMX Criteri di gruppo: msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="1efcf-263">GP ADMX file name: msedgeupdate.admx</span></span>
##### <span data-ttu-id="1efcf-264">Impostazioni del Registro di sistema di Windows</span><span class="sxs-lookup"><span data-stu-id="1efcf-264">Windows Registry Settings</span></span>
- <span data-ttu-id="1efcf-265">Percorso: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="1efcf-265">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="1efcf-266">Nome:</span><span class="sxs-lookup"><span data-stu-id="1efcf-266">Value Name:</span></span> 
  - <span data-ttu-id="1efcf-267">(Stabile): Update{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span><span class="sxs-lookup"><span data-stu-id="1efcf-267">(Stable): Update{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span></span>
  - <span data-ttu-id="1efcf-268">(Beta): Update{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span><span class="sxs-lookup"><span data-stu-id="1efcf-268">(Beta): Update{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span></span>
  - <span data-ttu-id="1efcf-269">(Canary): Update{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span><span class="sxs-lookup"><span data-stu-id="1efcf-269">(Canary): Update{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span></span>
  - <span data-ttu-id="1efcf-270">(Dev): Update{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span><span class="sxs-lookup"><span data-stu-id="1efcf-270">(Dev): Update{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span></span>
- <span data-ttu-id="1efcf-271">Tipo valore: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="1efcf-271">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="1efcf-272">Valore di esempio</span><span class="sxs-lookup"><span data-stu-id="1efcf-272">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="1efcf-273">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="1efcf-273">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="1efcf-274">Allowsxs</span><span class="sxs-lookup"><span data-stu-id="1efcf-274">Allowsxs</span></span>
#### <span data-ttu-id="1efcf-275">Consenti esperienza browser Microsoft Edge affiancata</span><span class="sxs-lookup"><span data-stu-id="1efcf-275">Allow Microsoft Edge Side by Side browser experience</span></span>
><span data-ttu-id="1efcf-276">Microsoft Edge Update 1.2.145.5 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="1efcf-276">Microsoft Edge Update 1.2.145.5 and later</span></span>

#### <span data-ttu-id="1efcf-277">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1efcf-277">Description</span></span>
<span data-ttu-id="1efcf-278">Questo criterio consente a un utente di eseguire Microsoft Edge (Edge HTML) e Microsoft Edge (basato su Chromium) in modalità affiancata.</span><span class="sxs-lookup"><span data-stu-id="1efcf-278">This policy lets a user run Microsoft Edge (Edge HTML) and Microsoft Edge (Chromium-based) side-by-side.</span></span>

<span data-ttu-id="1efcf-279">Se questo criterio è impostato su "Non configurato", Microsoft Edge (basato su Chromium) sostituirà Microsoft Edge (Edge HTML) dopo l'installazione del canale stabile di Microsoft Edge (basato su Chromium) e degli aggiornamenti della sicurezza di novembre 2019.</span><span class="sxs-lookup"><span data-stu-id="1efcf-279">If this policy is set to “Not configured”, Microsoft Edge (Chromium-based) will replace Microsoft Edge (Edge HTML) after the Microsoft Edge (Chromium-based) stable channel and the November 2019 security updates are installed.</span></span>  <span data-ttu-id="1efcf-280">Si tratta dello stesso comportamento correlato all'impostazione "Disabilitato".</span><span class="sxs-lookup"><span data-stu-id="1efcf-280">This is the same behavior as the “Disabled” setting.</span></span>

<span data-ttu-id="1efcf-281">L'impostazione "Disabilitato" blocca un'esperienza affiancata e Microsoft Edge (basato su Chromium) sostituirà Microsoft Edge (Edge HTML) dopo l'installazione del canale stabile di Microsoft Edge (basato su Chromium) e degli aggiornamenti della sicurezza di novembre 2019.</span><span class="sxs-lookup"><span data-stu-id="1efcf-281">The “Disabled” setting blocks a side-by-side experience and Microsoft Edge (Chromium-based) will replace Microsoft Edge (Edge HTML) after the Microsoft Edge (Chromium-based) stable channel and the November 2019 security updates are installed.</span></span>  <span data-ttu-id="1efcf-282">Si tratta dello stesso comportamento correlato all'impostazione "Non configurato".</span><span class="sxs-lookup"><span data-stu-id="1efcf-282">This is the same behavior as the “Not Configured” setting.</span></span>

<span data-ttu-id="1efcf-283">Quando l'impostazione di questo criterio è "Abilitato", è possibile eseguire in modalità affiancata Microsoft Edge (basato su Chromium) e Microsoft Edge (Edge HTML) dopo l'installazione di Microsoft Edge (basato su Chromium).</span><span class="sxs-lookup"><span data-stu-id="1efcf-283">When this policy is “Enabled”, Microsoft Edge (Chromium-based) and Microsoft Edge (Edge HTML) can run side-by-side after Microsoft Edge (Chromium-based) is installed.</span></span>

<span data-ttu-id="1efcf-284">Affinché questi criteri di gruppo abbiano effetto, è necessario configurarli prima dell'installazione automatica di Microsoft Edge (basato su Chromium) da Windows Update.</span><span class="sxs-lookup"><span data-stu-id="1efcf-284">For this group policy to take affect, it must be configured before the automatic install of Microsoft Edge (Chromium-based) by Windows Update.</span></span> <span data-ttu-id="1efcf-285">Nota: un utente può bloccare l'aggiornamento automatico di Microsoft Edge (basato su Chromium) usando Blocker Toolkit di Microsoft Edge (basato su Chromium).</span><span class="sxs-lookup"><span data-stu-id="1efcf-285">Note: A user can block the automatic update of Microsoft Edge (Chromium-based) by using the Microsoft Edge (Chromium-based) Blocker Toolkit.</span></span>
#### <span data-ttu-id="1efcf-286">Informazioni e impostazioni di Windows</span><span class="sxs-lookup"><span data-stu-id="1efcf-286">Windows information and settings</span></span>
##### <span data-ttu-id="1efcf-287">Info su Criteri di gruppo (ADMX)</span><span class="sxs-lookup"><span data-stu-id="1efcf-287">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="1efcf-288">Nome univoco Criteri di gruppo: Allowsxs</span><span class="sxs-lookup"><span data-stu-id="1efcf-288">GP unique name: Allowsxs</span></span>
- <span data-ttu-id="1efcf-289">Nome Criteri di gruppo: Consenti esperienza browser Microsoft Edge affiancata</span><span class="sxs-lookup"><span data-stu-id="1efcf-289">GP name: Allow Microsoft Edge Side by Side browser experience</span></span>
- <span data-ttu-id="1efcf-290">Percorso Criteri di gruppo: Modelli amministrativi/Microsoft Edge Update/Applicazioni</span><span class="sxs-lookup"><span data-stu-id="1efcf-290">GP path: Administrative Templates/Microsoft Edge Update/Applications</span></span>
- <span data-ttu-id="1efcf-291">Nome file ADMX Criteri di gruppo: msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="1efcf-291">GP ADMX file name: msedgeupdate.admx</span></span>
##### <span data-ttu-id="1efcf-292">Impostazioni del Registro di sistema di Windows</span><span class="sxs-lookup"><span data-stu-id="1efcf-292">Windows Registry Settings</span></span>
- <span data-ttu-id="1efcf-293">Percorso: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="1efcf-293">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="1efcf-294">Nome valore: Allowsxs</span><span class="sxs-lookup"><span data-stu-id="1efcf-294">Value Name: Allowsxs</span></span>
- <span data-ttu-id="1efcf-295">Tipo valore: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="1efcf-295">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="1efcf-296">Valore di esempio</span><span class="sxs-lookup"><span data-stu-id="1efcf-296">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="1efcf-297">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="1efcf-297">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="1efcf-298">CreateDesktopShortcutDefault</span><span class="sxs-lookup"><span data-stu-id="1efcf-298">CreateDesktopShortcutDefault</span></span>
#### <span data-ttu-id="1efcf-299">Impedisce la creazione di un collegamento sul desktop a seguito dell'installazione predefinita</span><span class="sxs-lookup"><span data-stu-id="1efcf-299">Prevent Desktop Shortcut creation upon install default</span></span>
><span data-ttu-id="1efcf-300">Microsoft Edge Update 1.3.128.0 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="1efcf-300">Microsoft Edge Update 1.3.128.0 and later</span></span>

#### <span data-ttu-id="1efcf-301">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1efcf-301">Description</span></span>
<span data-ttu-id="1efcf-302">Consente di specificare il comportamento predefinito per tutti i canali per la creazione di un collegamento sul desktop quando Microsoft Edge è installato.</span><span class="sxs-lookup"><span data-stu-id="1efcf-302">Lets you specify the default behavior for all channels for creating a desktop shortcut when Microsoft Edge is installed.</span></span>

  <span data-ttu-id="1efcf-303">Abilitando questo criterio, si creerà un collegamento sul desktop quando Microsoft Edge è installato.</span><span class="sxs-lookup"><span data-stu-id="1efcf-303">If you enable this policy a desktop shortcut is created when Microsoft Edge is installed.</span></span>
<span data-ttu-id="1efcf-304">Disabilitando questo criterio, non si creerà un collegamento sul desktop quando Microsoft Edge è installato.</span><span class="sxs-lookup"><span data-stu-id="1efcf-304">If you disable this policy, no desktop shortcut will be created when Microsoft Edge is installed.</span></span>
<span data-ttu-id="1efcf-305">Non configurando questo criterio, si creerà sul desktop un collegamento a Microsoft Edge durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="1efcf-305">If you don’t configure this policy a desktop shortcut to Microsoft Edge will be created during installation.</span></span>
<span data-ttu-id="1efcf-306">Nel caso in cui Microsoft Edge fosse già installato, il criterio non avrà effetto.</span><span class="sxs-lookup"><span data-stu-id="1efcf-306">If Microsoft Edge is already installed, this policy will have no effect.</span></span>
#### <span data-ttu-id="1efcf-307">Informazioni e impostazioni di Windows</span><span class="sxs-lookup"><span data-stu-id="1efcf-307">Windows information and settings</span></span>
##### <span data-ttu-id="1efcf-308">Info su Criteri di gruppo (ADMX)</span><span class="sxs-lookup"><span data-stu-id="1efcf-308">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="1efcf-309">Nome univoco Criteri di gruppo: CreateDesktopShortcutDefault</span><span class="sxs-lookup"><span data-stu-id="1efcf-309">GP unique name: CreateDesktopShortcutDefault</span></span>
- <span data-ttu-id="1efcf-310">Nome Criteri di gruppo: impedisce la creazione di un collegamento sul desktop a seguito dell'installazione predefinita</span><span class="sxs-lookup"><span data-stu-id="1efcf-310">GP name: Prevent Desktop Shortcut creation upon install default</span></span>
- <span data-ttu-id="1efcf-311">Percorso Criteri di gruppo: Modelli amministrativi/Microsoft Edge Update/Applicazioni</span><span class="sxs-lookup"><span data-stu-id="1efcf-311">GP path: Administrative Templates/Microsoft Edge Update/Applications</span></span>
- <span data-ttu-id="1efcf-312">Nome file ADMX Criteri di gruppo: msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="1efcf-312">GP ADMX file name: msedgeupdate.admx</span></span>
##### <span data-ttu-id="1efcf-313">Impostazioni del Registro di sistema di Windows</span><span class="sxs-lookup"><span data-stu-id="1efcf-313">Windows Registry Settings</span></span>
- <span data-ttu-id="1efcf-314">Percorso: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="1efcf-314">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="1efcf-315">Nome valore: CreateDesktopShortcutDefault</span><span class="sxs-lookup"><span data-stu-id="1efcf-315">Value Name: CreateDesktopShortcutDefault</span></span>
- <span data-ttu-id="1efcf-316">Tipo valore: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="1efcf-316">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="1efcf-317">Valore di esempio</span><span class="sxs-lookup"><span data-stu-id="1efcf-317">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="1efcf-318">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="1efcf-318">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="1efcf-319">CreateDesktopShortcut</span><span class="sxs-lookup"><span data-stu-id="1efcf-319">CreateDesktopShortcut</span></span>
#### <span data-ttu-id="1efcf-320">Impedisce la creazione di un collegamento sul desktop a seguito dell'installazione</span><span class="sxs-lookup"><span data-stu-id="1efcf-320">Prevent Desktop Shortcut creation upon install</span></span>
><span data-ttu-id="1efcf-321">Microsoft Edge Update 1.3.128.0 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="1efcf-321">Microsoft Edge Update 1.3.128.0 and later</span></span>

#### <span data-ttu-id="1efcf-322">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1efcf-322">Description</span></span>
<span data-ttu-id="1efcf-323">Abilitando questo criterio, si creerà un collegamento sul desktop quando Microsoft Edge è installato.</span><span class="sxs-lookup"><span data-stu-id="1efcf-323">If you enable this policy a desktop shortcut is created when Microsoft Edge is installed.</span></span>
<span data-ttu-id="1efcf-324">Disabilitando questo criterio, non si creerà un collegamento sul desktop quando Microsoft Edge è installato.</span><span class="sxs-lookup"><span data-stu-id="1efcf-324">If you disable this policy, no desktop shortcut will be created when Microsoft Edge is installed.</span></span>
<span data-ttu-id="1efcf-325">Non configurando questo criterio, si creerà sul desktop un collegamento a Microsoft Edge durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="1efcf-325">If you don’t configure this policy a desktop shortcut to Microsoft Edge will be created during installation.</span></span>
<span data-ttu-id="1efcf-326">Nel caso in cui Microsoft Edge fosse già installato, il criterio non avrà effetto.</span><span class="sxs-lookup"><span data-stu-id="1efcf-326">If Microsoft Edge is already installed, this policy will have no effect.</span></span>

  <span data-ttu-id="1efcf-327">Se questo criterio non viene configurato per un canale, la configurazione del criterio "[Impedisce la creazione di un collegamento sul desktop a seguito dell'installazione predefinita](#createdesktopshortcutdefault)" determina la creazione del collegamento quando Microsoft Edge viene installato.</span><span class="sxs-lookup"><span data-stu-id="1efcf-327">If you don't configure this policy for a channel, the '[Prevent Desktop Shortcut creation upon install default](#createdesktopshortcutdefault)' policy configuration determines shortcut creation when Microsoft Edge is installed.</span></span>
#### <span data-ttu-id="1efcf-328">Informazioni e impostazioni di Windows</span><span class="sxs-lookup"><span data-stu-id="1efcf-328">Windows information and settings</span></span>
##### <span data-ttu-id="1efcf-329">Info su Criteri di gruppo (ADMX)</span><span class="sxs-lookup"><span data-stu-id="1efcf-329">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="1efcf-330">Nome univoco Criteri di gruppo: CreateDesktopShortcut</span><span class="sxs-lookup"><span data-stu-id="1efcf-330">GP unique name: CreateDesktopShortcut</span></span>
- <span data-ttu-id="1efcf-331">Nome Criteri di gruppo: impedisce la creazione di un collegamento sul desktop dopo l'installazione</span><span class="sxs-lookup"><span data-stu-id="1efcf-331">GP name: Prevent Desktop Shortcut creation upon install</span></span>
- <span data-ttu-id="1efcf-332">Percorso Criteri di gruppo:</span><span class="sxs-lookup"><span data-stu-id="1efcf-332">GP path:</span></span> 
  - <span data-ttu-id="1efcf-333">Modelli amministrativi/Microsoft Edge Update/Applicazioni/Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="1efcf-333">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge</span></span>
  - <span data-ttu-id="1efcf-334">Modelli amministrativi/Microsoft Edge Update/Applicazioni/Microsoft Edge Beta</span><span class="sxs-lookup"><span data-stu-id="1efcf-334">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Beta</span></span>
  - <span data-ttu-id="1efcf-335">Modelli amministrativi/Microsoft Edge Update/Applicazioni/Microsoft Edge Canary</span><span class="sxs-lookup"><span data-stu-id="1efcf-335">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Canary</span></span>
  - <span data-ttu-id="1efcf-336">Modelli amministrativi/Microsoft Edge Update/Applicazioni/Microsoft Edge Dev</span><span class="sxs-lookup"><span data-stu-id="1efcf-336">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Dev</span></span>
- <span data-ttu-id="1efcf-337">Nome file ADMX Criteri di gruppo: msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="1efcf-337">GP ADMX file name: msedgeupdate.admx</span></span>
##### <span data-ttu-id="1efcf-338">Impostazioni del Registro di sistema di Windows</span><span class="sxs-lookup"><span data-stu-id="1efcf-338">Windows Registry Settings</span></span>
- <span data-ttu-id="1efcf-339">Percorso: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="1efcf-339">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="1efcf-340">Nome:</span><span class="sxs-lookup"><span data-stu-id="1efcf-340">Value Name:</span></span> 
  - <span data-ttu-id="1efcf-341">(Stable): CreateDesktopShortcut{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span><span class="sxs-lookup"><span data-stu-id="1efcf-341">(Stable): CreateDesktopShortcut{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span></span>
  - <span data-ttu-id="1efcf-342">(Beta): CreateDesktopShortcut{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span><span class="sxs-lookup"><span data-stu-id="1efcf-342">(Beta): CreateDesktopShortcut{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span></span>
  - <span data-ttu-id="1efcf-343">(Canary): CreateDesktopShortcut{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span><span class="sxs-lookup"><span data-stu-id="1efcf-343">(Canary): CreateDesktopShortcut{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span></span>
  - <span data-ttu-id="1efcf-344">(Dev): CreateDesktopShortcut{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span><span class="sxs-lookup"><span data-stu-id="1efcf-344">(Dev): CreateDesktopShortcut{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span></span>
- <span data-ttu-id="1efcf-345">Tipo valore: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="1efcf-345">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="1efcf-346">Valore di esempio</span><span class="sxs-lookup"><span data-stu-id="1efcf-346">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="1efcf-347">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="1efcf-347">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="1efcf-348">RollbackToTargetVersion</span><span class="sxs-lookup"><span data-stu-id="1efcf-348">RollbackToTargetVersion</span></span>
#### <span data-ttu-id="1efcf-349">Esegui il ripristino dello stato precedente della versione di destinazione</span><span class="sxs-lookup"><span data-stu-id="1efcf-349">Rollback to Target version</span></span>
><span data-ttu-id="1efcf-350">Microsoft Edge Update 1.3.133.3 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="1efcf-350">Microsoft Edge Update 1.3.133.3 and later</span></span>

#### <span data-ttu-id="1efcf-351">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1efcf-351">Description</span></span>
<span data-ttu-id="1efcf-352">Specifica che Microsoft Edge Update dovrebbe eseguire il ripristino dello stato precedente delle installazioni di Microsoft Edge alla versione indicata in "[Sostituzione della versione di destinazione](#targetversionprefix)".</span><span class="sxs-lookup"><span data-stu-id="1efcf-352">Specifies that Microsoft Edge Update should rollback installations of Microsoft Edge to the version indicated in '[Target version override](#targetversionprefix)'.</span></span>

<span data-ttu-id="1efcf-353">Questo criterio non ha alcun effetto, a meno che “[Sostituzione della versione di destinazione](#targetversionprefix)” sia impostato e “[Aggiorna criterio sostituzione](#update)” sia impostato su ATTIVO in uno dei seguenti stati (Consenti sempre gli aggiornamenti, Solo aggiornamenti automatici silenziosi, Solo aggiornamenti manuali).</span><span class="sxs-lookup"><span data-stu-id="1efcf-353">This policy has no effect unless '[Target version override](#targetversionprefix)' is set and '[Update policy override](#update)' is set to one of the ON states (Always allow updates, Automatic silent updates only, Manual updates only).</span></span>

<span data-ttu-id="1efcf-354">Se disabiliti questo criterio o non lo configuri, le installazioni con una versione superiore a quella specificata da "[Sostituzione della versione di destinazione](#targetversionprefix)" verranno lasciate così come sono.</span><span class="sxs-lookup"><span data-stu-id="1efcf-354">If you disable this policy or don't configure it, installs that have a version higher than that specified by '[Target version override](#targetversionprefix)' will be left as-is.</span></span>

<span data-ttu-id="1efcf-355">Se abiliti questi criteri, le installazioni che hanno una versione corrente superiore a quella specificata dall'override della”[Aggiorna criterio sostituzione](#targetversionprefix)" verranno declassate alla versione di destinazione.</span><span class="sxs-lookup"><span data-stu-id="1efcf-355">If you enable this policy, installs that have a current version higher than specified by the '[Target version override](#targetversionprefix)' will be downgraded to the target version.</span></span>

<span data-ttu-id="1efcf-356">È consigliabile installare l’ultima versione del browser Microsoft Edge per sfruttare la protezione degli aggiornamenti della sicurezza più recenti.</span><span class="sxs-lookup"><span data-stu-id="1efcf-356">We recommend that users install the latest version of the Microsoft Edge browser to ensure protection by the latest security updates.</span></span> <span data-ttu-id="1efcf-357">Il ripristino di una versione precedente può comportare rischi di esposizione a problemi di sicurezza noti.</span><span class="sxs-lookup"><span data-stu-id="1efcf-357">Rollback to an earlier version risks exposure to known security issues.</span></span> <span data-ttu-id="1efcf-358">Questo criterio deve essere usato come correzione temporanea per risolvere i problemi di aggiornamento del browser Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="1efcf-358">This policy is meant to be used as a temporary fix to address issues in a Microsoft Edge browser update.</span></span>

<span data-ttu-id="1efcf-359">Prima di ripristinare temporaneamente la versione precedente del browser, è inoltre consigliabile abilitare la sincronizzazione ([https://go.microsoft.com/fwlink/?linkid=2133032](https://go.microsoft.com/fwlink/?linkid=2133032)) per tutti gli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="1efcf-359">Before temporarily rolling back your browser version, we recommend that you turn on Sync ([https://go.microsoft.com/fwlink/?linkid=2133032](https://go.microsoft.com/fwlink/?linkid=2133032)) for all users in your organization.</span></span> <span data-ttu-id="1efcf-360">Se la sincronizzazione non viene abilitata, si rischia la perdita permanente dei dati di navigazione.</span><span class="sxs-lookup"><span data-stu-id="1efcf-360">If you don't turn on Sync, there is a risk of permanent browsing data loss.</span></span> <span data-ttu-id="1efcf-361">Usa questo criterio a tuo rischio.</span><span class="sxs-lookup"><span data-stu-id="1efcf-361">Use this policy at your own risk.</span></span>

<span data-ttu-id="1efcf-362">Nota: è possibile visualizzare tutte le versioni disponibili per il ripristino dello stato precedente qui [https://aka.ms/EdgeEnterprise](https://aka.ms/EdgeEnterprise).</span><span class="sxs-lookup"><span data-stu-id="1efcf-362">Note: All versions available for rollback can be viewed here [https://aka.ms/EdgeEnterprise](https://aka.ms/EdgeEnterprise).</span></span>

<span data-ttu-id="1efcf-363">Questo criteri viene applicato a Microsoft Edge versione 86 o successiva.</span><span class="sxs-lookup"><span data-stu-id="1efcf-363">This policy applies to Microsoft Edge version 86 or later.</span></span>

<span data-ttu-id="1efcf-364">Per altre informazioni, vedere [https://go.microsoft.com/fwlink/?linkid=2133918](https://go.microsoft.com/fwlink/?linkid=2133918).</span><span class="sxs-lookup"><span data-stu-id="1efcf-364">See [https://go.microsoft.com/fwlink/?linkid=2133918](https://go.microsoft.com/fwlink/?linkid=2133918) for more information.</span></span>

<span data-ttu-id="1efcf-365">Questo criterio è disponibile solo nelle istanze di Windows che fanno parte di un dominio Microsoft® Active Directory®.</span><span class="sxs-lookup"><span data-stu-id="1efcf-365">This policy is available only on Windows instances that are joined to a Microsoft® Active Directory® domain.</span></span>
#### <span data-ttu-id="1efcf-366">Informazioni e impostazioni di Windows</span><span class="sxs-lookup"><span data-stu-id="1efcf-366">Windows information and settings</span></span>
##### <span data-ttu-id="1efcf-367">Info su Criteri di gruppo (ADMX)</span><span class="sxs-lookup"><span data-stu-id="1efcf-367">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="1efcf-368">Nome univoco Criteri di gruppo: RollbackToTargetVersion</span><span class="sxs-lookup"><span data-stu-id="1efcf-368">GP unique name: RollbackToTargetVersion</span></span>
- <span data-ttu-id="1efcf-369">Nome Criteri di gruppo: ripristina versione di destinazione</span><span class="sxs-lookup"><span data-stu-id="1efcf-369">GP name: Rollback to Target version</span></span>
- <span data-ttu-id="1efcf-370">Percorso Criteri di gruppo:</span><span class="sxs-lookup"><span data-stu-id="1efcf-370">GP path:</span></span> 
  - <span data-ttu-id="1efcf-371">Modelli amministrativi/Microsoft Edge Update/Applicazioni/Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="1efcf-371">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge</span></span>
  - <span data-ttu-id="1efcf-372">Modelli amministrativi/Microsoft Edge Update/Applicazioni/Microsoft Edge Beta</span><span class="sxs-lookup"><span data-stu-id="1efcf-372">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Beta</span></span>
  - <span data-ttu-id="1efcf-373">Modelli amministrativi/Microsoft Edge Update/Applicazioni/Microsoft Edge Canary</span><span class="sxs-lookup"><span data-stu-id="1efcf-373">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Canary</span></span>
  - <span data-ttu-id="1efcf-374">Modelli amministrativi/Microsoft Edge Update/Applicazioni/Microsoft Edge Dev</span><span class="sxs-lookup"><span data-stu-id="1efcf-374">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Dev</span></span>
- <span data-ttu-id="1efcf-375">Nome file ADMX Criteri di gruppo: msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="1efcf-375">GP ADMX file name: msedgeupdate.admx</span></span>
##### <span data-ttu-id="1efcf-376">Impostazioni del Registro di sistema di Windows</span><span class="sxs-lookup"><span data-stu-id="1efcf-376">Windows Registry Settings</span></span>
- <span data-ttu-id="1efcf-377">Percorso: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="1efcf-377">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="1efcf-378">Nome:</span><span class="sxs-lookup"><span data-stu-id="1efcf-378">Value Name:</span></span> 
  - <span data-ttu-id="1efcf-379">(Stable): RollbackToTargetVersion{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span><span class="sxs-lookup"><span data-stu-id="1efcf-379">(Stable): RollbackToTargetVersion{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span></span>
  - <span data-ttu-id="1efcf-380">(Beta): RollbackToTargetVersion{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span><span class="sxs-lookup"><span data-stu-id="1efcf-380">(Beta): RollbackToTargetVersion{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span></span>
  - <span data-ttu-id="1efcf-381">(Canary): RollbackToTargetVersion{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span><span class="sxs-lookup"><span data-stu-id="1efcf-381">(Canary): RollbackToTargetVersion{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span></span>
  - <span data-ttu-id="1efcf-382">(Dev): RollbackToTargetVersion{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span><span class="sxs-lookup"><span data-stu-id="1efcf-382">(Dev): RollbackToTargetVersion{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span></span>
- <span data-ttu-id="1efcf-383">Tipo valore: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="1efcf-383">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="1efcf-384">Valore di esempio</span><span class="sxs-lookup"><span data-stu-id="1efcf-384">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="1efcf-385">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="1efcf-385">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="1efcf-386">TargetVersionPrefix</span><span class="sxs-lookup"><span data-stu-id="1efcf-386">TargetVersionPrefix</span></span>
#### <span data-ttu-id="1efcf-387">Sostituzione della versione di destinazione</span><span class="sxs-lookup"><span data-stu-id="1efcf-387">Target version override</span></span>
><span data-ttu-id="1efcf-388">Microsoft Edge Update 1.3.119.43 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="1efcf-388">Microsoft Edge Update 1.3.119.43 and later</span></span>

#### <span data-ttu-id="1efcf-389">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1efcf-389">Description</span></span>
<span data-ttu-id="1efcf-390">Abilitando questo criterio e l'aggiornamento automatico, Microsoft Edge verrà aggiornato alla versione specificata da questo valore criterio.</span><span class="sxs-lookup"><span data-stu-id="1efcf-390">When this policy is enabled, and auto-update is enabled, Microsoft Edge will be updated to the version specified by this policy value.</span></span>

<span data-ttu-id="1efcf-391">Il valore del criterio deve essere una specifica versione di Microsoft Edge, ad esempio: 83.0.499.12.</span><span class="sxs-lookup"><span data-stu-id="1efcf-391">The policy value must be a specific Microsoft Edge version, e.g. 83.0.499.12.</span></span>

<span data-ttu-id="1efcf-392">Se sul dispositivo è installata una versione più recente di Microsoft Edge del valore specificato, Edge manterrà la versione più recente e non eseguirà il downgrade alla versione specificata.</span><span class="sxs-lookup"><span data-stu-id="1efcf-392">If a device has newer version of Microsoft Edge than the value specified, Microsoft Edge will remain on the newer version and not downgrade to the specified version.</span></span>

<span data-ttu-id="1efcf-393">In caso la versione specificata non esista o non sia formattata correttamente, Microsoft Edge manterrà la versione attuale e non verrà aggiornato automaticamente alle versioni future.</span><span class="sxs-lookup"><span data-stu-id="1efcf-393">If the specified version does not exist, or is improperly formatted, then Microsoft Edge will remain on its current version and not update to future versions automatically.</span></span>

<span data-ttu-id="1efcf-394">Per altre informazioni, vedere [https://go.microsoft.com/fwlink/?linkid=2136707](https://go.microsoft.com/fwlink/?linkid=2136707).</span><span class="sxs-lookup"><span data-stu-id="1efcf-394">See [https://go.microsoft.com/fwlink/?linkid=2136707](https://go.microsoft.com/fwlink/?linkid=2136707) for more information.</span></span>

<span data-ttu-id="1efcf-395">Questo criterio è disponibile solo nelle istanze di Windows che fanno parte di un dominio Microsoft® Active Directory®.</span><span class="sxs-lookup"><span data-stu-id="1efcf-395">This policy is available only on Windows instances that are joined to a Microsoft® Active Directory® domain.</span></span>
#### <span data-ttu-id="1efcf-396">Informazioni e impostazioni di Windows</span><span class="sxs-lookup"><span data-stu-id="1efcf-396">Windows information and settings</span></span>
##### <span data-ttu-id="1efcf-397">Info su Criteri di gruppo (ADMX)</span><span class="sxs-lookup"><span data-stu-id="1efcf-397">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="1efcf-398">Nome univoco Criteri di gruppo: TargetVersionPrefix</span><span class="sxs-lookup"><span data-stu-id="1efcf-398">GP unique name: TargetVersionPrefix</span></span>
- <span data-ttu-id="1efcf-399">Nome Criteri di gruppo: Sostituzione della versione di destinazione</span><span class="sxs-lookup"><span data-stu-id="1efcf-399">GP name: Target version override</span></span>
- <span data-ttu-id="1efcf-400">Percorso Criteri di gruppo:</span><span class="sxs-lookup"><span data-stu-id="1efcf-400">GP path:</span></span> 
  - <span data-ttu-id="1efcf-401">Modelli amministrativi/Microsoft Edge Update/Applicazioni/Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="1efcf-401">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge</span></span>
  - <span data-ttu-id="1efcf-402">Modelli amministrativi/Microsoft Edge Update/Applicazioni/Microsoft Edge Beta</span><span class="sxs-lookup"><span data-stu-id="1efcf-402">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Beta</span></span>
  - <span data-ttu-id="1efcf-403">Modelli amministrativi/Microsoft Edge Update/Applicazioni/Microsoft Edge Canary</span><span class="sxs-lookup"><span data-stu-id="1efcf-403">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Canary</span></span>
  - <span data-ttu-id="1efcf-404">Modelli amministrativi/Microsoft Edge Update/Applicazioni/Microsoft Edge Dev</span><span class="sxs-lookup"><span data-stu-id="1efcf-404">Administrative Templates/Microsoft Edge Update/Applications/Microsoft Edge Dev</span></span>
- <span data-ttu-id="1efcf-405">Nome file ADMX Criteri di gruppo: msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="1efcf-405">GP ADMX file name: msedgeupdate.admx</span></span>
##### <span data-ttu-id="1efcf-406">Impostazioni del Registro di sistema di Windows</span><span class="sxs-lookup"><span data-stu-id="1efcf-406">Windows Registry Settings</span></span>
- <span data-ttu-id="1efcf-407">Percorso: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="1efcf-407">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="1efcf-408">Nome:</span><span class="sxs-lookup"><span data-stu-id="1efcf-408">Value Name:</span></span> 
  - <span data-ttu-id="1efcf-409">(Stable): TargetVersionPrefix{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span><span class="sxs-lookup"><span data-stu-id="1efcf-409">(Stable): TargetVersionPrefix{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}</span></span>
  - <span data-ttu-id="1efcf-410">(Beta): TargetVersionPrefix{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span><span class="sxs-lookup"><span data-stu-id="1efcf-410">(Beta): TargetVersionPrefix{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}</span></span>
  - <span data-ttu-id="1efcf-411">(Canary): TargetVersionPrefix{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span><span class="sxs-lookup"><span data-stu-id="1efcf-411">(Canary): TargetVersionPrefix{65C35B14-6C1D-4122-AC46-7148CC9D6497}</span></span>
  - <span data-ttu-id="1efcf-412">(Dev): TargetVersionPrefix{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span><span class="sxs-lookup"><span data-stu-id="1efcf-412">(Dev): TargetVersionPrefix{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}</span></span>
- <span data-ttu-id="1efcf-413">Tipo valore: REG_SZ</span><span class="sxs-lookup"><span data-stu-id="1efcf-413">Value Type: REG_SZ</span></span>
##### <span data-ttu-id="1efcf-414">Valore di esempio</span><span class="sxs-lookup"><span data-stu-id="1efcf-414">Example value:</span></span>
```
83.0.499.12
```
[<span data-ttu-id="1efcf-415">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="1efcf-415">Back to top</span></span>](#microsoft-edge---update-policies)


## <span data-ttu-id="1efcf-416">Criteri delle preferenze</span><span class="sxs-lookup"><span data-stu-id="1efcf-416">Preferences policies</span></span>

[<span data-ttu-id="1efcf-417">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="1efcf-417">Back to top</span></span>](#microsoft-edge---update-policies)
### <span data-ttu-id="1efcf-418">AutoUpdateCheckPeriodMinutes</span><span class="sxs-lookup"><span data-stu-id="1efcf-418">AutoUpdateCheckPeriodMinutes</span></span>
#### <span data-ttu-id="1efcf-419">Sostituzione del periodo di controllo dell'aggiornamento automatico</span><span class="sxs-lookup"><span data-stu-id="1efcf-419">Auto-update check period override</span></span>
><span data-ttu-id="1efcf-420">Microsoft Edge Update 1.2.145.5 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="1efcf-420">Microsoft Edge Update 1.2.145.5 and later</span></span>

#### <span data-ttu-id="1efcf-421">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1efcf-421">Description</span></span>
<span data-ttu-id="1efcf-422">Se abilitata, questo criterio consente di impostare un valore per il numero minimo di minuti che devono intercorrere tra i controlli dell'aggiornamento automatico.</span><span class="sxs-lookup"><span data-stu-id="1efcf-422">If enabled, this policy lets you set a value for the minimum number of minutes between automatic update checks.</span></span> <span data-ttu-id="1efcf-423">In caso contrario, per impostazione predefinita, l'aggiornamento automatico verifica la disponibilità degli aggiornamenti ogni 10 ore.</span><span class="sxs-lookup"><span data-stu-id="1efcf-423">Otherwise, by default, auto-update checks for updates every 10 hours.</span></span>

  <span data-ttu-id="1efcf-424">Se desideri disabilitare tutti i controlli dell'aggiornamento automatico, imposta il valore su 0 (scelta non consigliata).</span><span class="sxs-lookup"><span data-stu-id="1efcf-424">If you want to disable all auto-update checks, set the value to 0 (not recommended).</span></span>
#### <span data-ttu-id="1efcf-425">Informazioni e impostazioni di Windows</span><span class="sxs-lookup"><span data-stu-id="1efcf-425">Windows information and settings</span></span>
##### <span data-ttu-id="1efcf-426">Info su Criteri di gruppo (ADMX)</span><span class="sxs-lookup"><span data-stu-id="1efcf-426">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="1efcf-427">Nome univoco Criteri di gruppo: AutoUpdateCheckPeriodMinutes</span><span class="sxs-lookup"><span data-stu-id="1efcf-427">GP unique name: AutoUpdateCheckPeriodMinutes</span></span>
- <span data-ttu-id="1efcf-428">Nome Criteri di gruppo: Sostituzione del periodo di controllo dell'aggiornamento automatico</span><span class="sxs-lookup"><span data-stu-id="1efcf-428">GP name: Auto-update check period override</span></span>
- <span data-ttu-id="1efcf-429">Percorso Criteri di gruppo: Modelli amministrativi/Microsoft Edge Update/Preferenze</span><span class="sxs-lookup"><span data-stu-id="1efcf-429">GP path: Administrative Templates/Microsoft Edge Update/Preferences</span></span>
- <span data-ttu-id="1efcf-430">Nome file ADMX Criteri di gruppo: msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="1efcf-430">GP ADMX file name: msedgeupdate.admx</span></span>
##### <span data-ttu-id="1efcf-431">Impostazioni del Registro di sistema di Windows</span><span class="sxs-lookup"><span data-stu-id="1efcf-431">Windows Registry Settings</span></span>
- <span data-ttu-id="1efcf-432">Percorso: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="1efcf-432">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="1efcf-433">Nome valore: AutoUpdateCheckPeriodMinutes</span><span class="sxs-lookup"><span data-stu-id="1efcf-433">Value Name: AutoUpdateCheckPeriodMinutes</span></span>
- <span data-ttu-id="1efcf-434">Tipo valore: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="1efcf-434">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="1efcf-435">Valore di esempio</span><span class="sxs-lookup"><span data-stu-id="1efcf-435">Example value:</span></span>
```
0x00000578
```
[<span data-ttu-id="1efcf-436">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="1efcf-436">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="1efcf-437">UpdatesSuppressed</span><span class="sxs-lookup"><span data-stu-id="1efcf-437">UpdatesSuppressed</span></span>
#### <span data-ttu-id="1efcf-438">Periodo di tempo in ogni giorno per eliminare il controllo dell'aggiornamento automatico</span><span class="sxs-lookup"><span data-stu-id="1efcf-438">Time period in each day to suppress auto-update check</span></span>
><span data-ttu-id="1efcf-439">Microsoft Edge Update 1.3.33.5 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="1efcf-439">Microsoft Edge Update 1.3.33.5 and later</span></span>

#### <span data-ttu-id="1efcf-440">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1efcf-440">Description</span></span>
<span data-ttu-id="1efcf-441">Se abiliti questo criterio, i controlli degli aggiornamenti vengono soppressi ogni giorno a partire dall'ora e dal minuto specificati per un periodo stabilito (in minuti).</span><span class="sxs-lookup"><span data-stu-id="1efcf-441">If you enable this policy, update checks are suppressed each day starting at Hour:Minute for a period of Duration (in minutes).</span></span> <span data-ttu-id="1efcf-442">La durata non è influenzata dall'ora legale.</span><span class="sxs-lookup"><span data-stu-id="1efcf-442">Duration isn't affected by daylight saving time.</span></span> <span data-ttu-id="1efcf-443">Ad esempio, se l'ora di inizio è 22.00 e la durata è 480 minuti, gli aggiornamenti verranno soppressi per esattamente 8 ore, indipendentemente dal fatto che l'ora legale venga avviata o termini durante questo periodo.</span><span class="sxs-lookup"><span data-stu-id="1efcf-443">For example, if the start time is 22:00 and the duration is 480 minutes, updates will be suppressed for exactly 8 hours, regardless of whether daylight saving time starts or ends during this period.</span></span>

  <span data-ttu-id="1efcf-444">Se disabiliti o non configuri questo criterio, i controlli degli aggiornamenti non vengono soppressi durante alcun periodo specifico.</span><span class="sxs-lookup"><span data-stu-id="1efcf-444">If you disable or don't configure this policy, update checks aren't suppressed during any specific period.</span></span>
#### <span data-ttu-id="1efcf-445">Informazioni e impostazioni di Windows</span><span class="sxs-lookup"><span data-stu-id="1efcf-445">Windows information and settings</span></span>
##### <span data-ttu-id="1efcf-446">Info su Criteri di gruppo (ADMX)</span><span class="sxs-lookup"><span data-stu-id="1efcf-446">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="1efcf-447">Nome univoco Criteri di gruppo: UpdatesSuppressed</span><span class="sxs-lookup"><span data-stu-id="1efcf-447">GP unique name: UpdatesSuppressed</span></span>
- <span data-ttu-id="1efcf-448">Nome Criteri di gruppo: Periodo di tempo in ogni giorno per eliminare il controllo dell'aggiornamento automatico</span><span class="sxs-lookup"><span data-stu-id="1efcf-448">GP name: Time period in each day to suppress auto-update check</span></span>
  - <span data-ttu-id="1efcf-449">Opzioni { Hour, Minute, Duration }</span><span class="sxs-lookup"><span data-stu-id="1efcf-449">Options { Hour, Minute, Duration }</span></span>
- <span data-ttu-id="1efcf-450">Percorso Criteri di gruppo: Modelli amministrativi/Microsoft Edge Update/Preferenze</span><span class="sxs-lookup"><span data-stu-id="1efcf-450">GP path: Administrative Templates/Microsoft Edge Update/Preferences</span></span>
- <span data-ttu-id="1efcf-451">Nome file ADMX Criteri di gruppo: msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="1efcf-451">GP ADMX file name: msedgeupdate.admx</span></span>
##### <span data-ttu-id="1efcf-452">Impostazioni del Registro di sistema di Windows</span><span class="sxs-lookup"><span data-stu-id="1efcf-452">Windows Registry Settings</span></span>
- <span data-ttu-id="1efcf-453">Percorso: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="1efcf-453">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="1efcf-454">Nome:</span><span class="sxs-lookup"><span data-stu-id="1efcf-454">Value Name:</span></span> 
  - <span data-ttu-id="1efcf-455">UpdatesSuppressedDurationMin</span><span class="sxs-lookup"><span data-stu-id="1efcf-455">UpdatesSuppressedDurationMin</span></span>
  - <span data-ttu-id="1efcf-456">UpdatesSuppressedStartHour</span><span class="sxs-lookup"><span data-stu-id="1efcf-456">UpdatesSuppressedStartHour</span></span>
  - <span data-ttu-id="1efcf-457">UpdatesSuppressedStartMin</span><span class="sxs-lookup"><span data-stu-id="1efcf-457">UpdatesSuppressedStartMin</span></span>
- <span data-ttu-id="1efcf-458">Tipo valore: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="1efcf-458">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="1efcf-459">Valore di esempio</span><span class="sxs-lookup"><span data-stu-id="1efcf-459">Example value:</span></span>
```
duration   : 0x0000003c
start hour : 0x00000001
start min  : 0x00000002
```
[<span data-ttu-id="1efcf-460">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="1efcf-460">Back to top</span></span>](#microsoft-edge---update-policies)


## <span data-ttu-id="1efcf-461">Criteri server proxy</span><span class="sxs-lookup"><span data-stu-id="1efcf-461">Proxy Server policies</span></span>

[<span data-ttu-id="1efcf-462">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="1efcf-462">Back to top</span></span>](#microsoft-edge---update-policies)
### <span data-ttu-id="1efcf-463">ProxyMode</span><span class="sxs-lookup"><span data-stu-id="1efcf-463">ProxyMode</span></span>
#### <span data-ttu-id="1efcf-464">Scegliere come specificare le impostazioni del server proxy</span><span class="sxs-lookup"><span data-stu-id="1efcf-464">Choose how to specify proxy server settings</span></span>
><span data-ttu-id="1efcf-465">Microsoft Edge Update 1.3.21.81 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="1efcf-465">Microsoft Edge Update 1.3.21.81 and later</span></span>

#### <span data-ttu-id="1efcf-466">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1efcf-466">Description</span></span>
<span data-ttu-id="1efcf-467">Consente di specificare le impostazioni del server proxy usate da Microsoft Edge Update.</span><span class="sxs-lookup"><span data-stu-id="1efcf-467">Allows you to specify the proxy server settings that are used by Microsoft Edge Update.</span></span>

  <span data-ttu-id="1efcf-468">Se abiliti questo criterio, puoi scegliere una delle opzioni relative al server proxy seguenti:</span><span class="sxs-lookup"><span data-stu-id="1efcf-468">If you enable this policy, you can choose between the following proxy server options:</span></span>
   - <span data-ttu-id="1efcf-469">Se scegli di non usare mai un server proxy e ti connetti sempre direttamente, tutte le altre opzioni vengono ignorate.</span><span class="sxs-lookup"><span data-stu-id="1efcf-469">If you choose to never use a proxy server and always connect directly, all other options are ignored.</span></span>
   - <span data-ttu-id="1efcf-470">Se scegli di usare le impostazioni del proxy di sistema o di rilevare automaticamente il server proxy, tutte le altre opzioni vengono ignorate.</span><span class="sxs-lookup"><span data-stu-id="1efcf-470">If you choose to use system proxy settings or auto-detect the proxy server, all other options are ignored.</span></span>
   - <span data-ttu-id="1efcf-471">Se scegli la modalità proxy server fisso, puoi specificare altre opzioni nel criterio "[Indirizzo o URL del server proxy](#proxyserver)".</span><span class="sxs-lookup"><span data-stu-id="1efcf-471">If you choose fixed server proxy mode, you can specify further options in '[Address or URL of proxy server](#proxyserver)' policy.</span></span>
   - <span data-ttu-id="1efcf-472">Se scegli di usare uno script proxy PAC, devi specificare l'URL per lo script nel criterio "[URL di un file PAC del proxy](#proxypacurl)".</span><span class="sxs-lookup"><span data-stu-id="1efcf-472">If you choose to use a .pac proxy script, you must specify the URL for the script in '[URL to a proxy .pac file](#proxypacurl)' policy.</span></span>

  <span data-ttu-id="1efcf-473">Se abiliti questo criterio, gli utenti dell'organizzazione non possono modificare le impostazioni proxy in Microsoft Edge Update.</span><span class="sxs-lookup"><span data-stu-id="1efcf-473">If you enable this policy, users in your organization can't change the proxy settings in Microsoft Edge Update.</span></span>

  <span data-ttu-id="1efcf-474">Se disabiliti o non configuri questo criterio, non vengono configurate impostazioni del server proxy, ma gli utenti dell'organizzazione possono scegliere le proprie impostazioni proxy per Microsoft Edge Update.</span><span class="sxs-lookup"><span data-stu-id="1efcf-474">If you disable or don't configure this policy, no proxy server settings are configured, but users in your organization can choose their own proxy settings for Microsoft Edge Update.</span></span>
#### <span data-ttu-id="1efcf-475">Informazioni e impostazioni di Windows</span><span class="sxs-lookup"><span data-stu-id="1efcf-475">Windows information and settings</span></span>
##### <span data-ttu-id="1efcf-476">Info su Criteri di gruppo (ADMX)</span><span class="sxs-lookup"><span data-stu-id="1efcf-476">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="1efcf-477">Nome univoco Criteri di gruppo: ProxyMode</span><span class="sxs-lookup"><span data-stu-id="1efcf-477">GP unique name: ProxyMode</span></span>
- <span data-ttu-id="1efcf-478">Nome Criteri di gruppo: Scegliere come specificare le impostazioni del server proxy</span><span class="sxs-lookup"><span data-stu-id="1efcf-478">GP name: Choose how to specify proxy server settings</span></span>
- <span data-ttu-id="1efcf-479">Percorso Criteri di gruppo: Modelli amministrativi/Microsoft Edge Update/Server proxy</span><span class="sxs-lookup"><span data-stu-id="1efcf-479">GP path: Administrative Templates/Microsoft Edge Update/Proxy Server</span></span>
- <span data-ttu-id="1efcf-480">Nome file ADMX Criteri di gruppo: msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="1efcf-480">GP ADMX file name: msedgeupdate.admx</span></span>
##### <span data-ttu-id="1efcf-481">Impostazioni del Registro di sistema di Windows</span><span class="sxs-lookup"><span data-stu-id="1efcf-481">Windows Registry Settings</span></span>
- <span data-ttu-id="1efcf-482">Percorso: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="1efcf-482">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="1efcf-483">Nome valore: ProxyMode</span><span class="sxs-lookup"><span data-stu-id="1efcf-483">Value Name: ProxyMode</span></span>
- <span data-ttu-id="1efcf-484">Tipo valore: REG_SZ</span><span class="sxs-lookup"><span data-stu-id="1efcf-484">Value Type: REG_SZ</span></span>
##### <span data-ttu-id="1efcf-485">Valore di esempio</span><span class="sxs-lookup"><span data-stu-id="1efcf-485">Example value:</span></span>
```
fixed_servers
```
[<span data-ttu-id="1efcf-486">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="1efcf-486">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="1efcf-487">ProxyPacUrl</span><span class="sxs-lookup"><span data-stu-id="1efcf-487">ProxyPacUrl</span></span>
#### <span data-ttu-id="1efcf-488">URL di un file PAC del proxy</span><span class="sxs-lookup"><span data-stu-id="1efcf-488">URL to a proxy .pac file</span></span>
><span data-ttu-id="1efcf-489">Microsoft Edge Update 1.3.21.81 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="1efcf-489">Microsoft Edge Update 1.3.21.81 and later</span></span>

#### <span data-ttu-id="1efcf-490">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1efcf-490">Description</span></span>
<span data-ttu-id="1efcf-491">Consente di specificare un URL per un file di configurazione automatica del proxy (PAC).</span><span class="sxs-lookup"><span data-stu-id="1efcf-491">Allows you to specify a URL for a proxy auto-config (PAC) file.</span></span>

  <span data-ttu-id="1efcf-492">Se abiliti questo criterio, puoi specificare un URL per un file PAC per automatizzare il modo in cui Microsoft Edge Update seleziona il server proxy appropriato per il recupero di un particolare sito Web.</span><span class="sxs-lookup"><span data-stu-id="1efcf-492">If you enable this policy, you can specify a URL for a PAC file to automate how Microsoft Edge Update selects the appropriate proxy server for fetching a particular website.</span></span>

  <span data-ttu-id="1efcf-493">Questo criterio viene applicato solo se sono state specificate impostazioni proxy manuali nel criterio "[Scegliere come specificare le impostazioni del server proxy](#proxymode)".</span><span class="sxs-lookup"><span data-stu-id="1efcf-493">This policy is applied only if you have specified manual proxy settings in the '[Choose how to specify proxy server settings](#proxymode)' policy.</span></span>

  <span data-ttu-id="1efcf-494">Non configurare questo criterio se hai selezionato un'impostazione proxy diversa da quella manuale nel criterio "[Scegliere come specificare le impostazioni del server proxy](#proxymode)".</span><span class="sxs-lookup"><span data-stu-id="1efcf-494">Don't configure this policy if you have selected a proxy setting other than manual in the '[Choose how to specify proxy server settings](#proxymode)' policy.</span></span>
#### <span data-ttu-id="1efcf-495">Informazioni e impostazioni di Windows</span><span class="sxs-lookup"><span data-stu-id="1efcf-495">Windows information and settings</span></span>
##### <span data-ttu-id="1efcf-496">Info su Criteri di gruppo (ADMX)</span><span class="sxs-lookup"><span data-stu-id="1efcf-496">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="1efcf-497">Nome univoco Criteri di gruppo: ProxyPacUrl</span><span class="sxs-lookup"><span data-stu-id="1efcf-497">GP unique name: ProxyPacUrl</span></span>
- <span data-ttu-id="1efcf-498">Nome Criteri di Gruppo: URL di un file PAC del proxy</span><span class="sxs-lookup"><span data-stu-id="1efcf-498">GP name: URL to a proxy .pac file</span></span>
- <span data-ttu-id="1efcf-499">Percorso Criteri di gruppo: Modelli amministrativi/Microsoft Edge Update/Server proxy</span><span class="sxs-lookup"><span data-stu-id="1efcf-499">GP path: Administrative Templates/Microsoft Edge Update/Proxy Server</span></span>
- <span data-ttu-id="1efcf-500">Nome file ADMX Criteri di gruppo: msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="1efcf-500">GP ADMX file name: msedgeupdate.admx</span></span>
##### <span data-ttu-id="1efcf-501">Impostazioni del Registro di sistema di Windows</span><span class="sxs-lookup"><span data-stu-id="1efcf-501">Windows Registry Settings</span></span>
- <span data-ttu-id="1efcf-502">Percorso: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="1efcf-502">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="1efcf-503">Nome valore: ProxyPacUrl</span><span class="sxs-lookup"><span data-stu-id="1efcf-503">Value Name: ProxyPacUrl</span></span>
- <span data-ttu-id="1efcf-504">Tipo valore: REG_SZ</span><span class="sxs-lookup"><span data-stu-id="1efcf-504">Value Type: REG_SZ</span></span>
##### <span data-ttu-id="1efcf-505">Valore di esempio</span><span class="sxs-lookup"><span data-stu-id="1efcf-505">Example value:</span></span>
```
https://www.microsoft.com
```
[<span data-ttu-id="1efcf-506">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="1efcf-506">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="1efcf-507">ProxyServer</span><span class="sxs-lookup"><span data-stu-id="1efcf-507">ProxyServer</span></span>
#### <span data-ttu-id="1efcf-508">Indirizzo o URL del server proxy</span><span class="sxs-lookup"><span data-stu-id="1efcf-508">Address or URL of proxy server</span></span>
><span data-ttu-id="1efcf-509">Microsoft Edge Update 1.3.21.81 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="1efcf-509">Microsoft Edge Update 1.3.21.81 and later</span></span>

#### <span data-ttu-id="1efcf-510">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1efcf-510">Description</span></span>
<span data-ttu-id="1efcf-511">Consente di specificare l'URL del server proxy per l'uso da parte di Microsoft Edge Update.</span><span class="sxs-lookup"><span data-stu-id="1efcf-511">Allows you to specify the URL of the proxy server for Microsoft Edge Update to use.</span></span>

  <span data-ttu-id="1efcf-512">Se abiliti questo criterio, puoi impostare l'URL del server proxy usato da Microsoft Edge Update nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="1efcf-512">If you enable this policy, you can set the proxy server URL used by Microsoft Edge Update in your organization.</span></span>

  <span data-ttu-id="1efcf-513">Questo criterio viene applicato solo se sono state selezionate impostazioni proxy manuali nel criterio "[Scegliere come specificare le impostazioni del server proxy](#proxymode)".</span><span class="sxs-lookup"><span data-stu-id="1efcf-513">This policy is applied only if you have selected manual proxy settings in the '[Choose how to specify proxy server settings](#proxymode)' policy.</span></span>

  <span data-ttu-id="1efcf-514">Non configurare questo criterio se hai selezionato un'impostazione proxy diversa da quella manuale nel criterio "[Scegliere come specificare le impostazioni del server proxy](#proxymode)".</span><span class="sxs-lookup"><span data-stu-id="1efcf-514">Don't configure this policy if you have selected a proxy setting other than manual in the '[Choose how to specify proxy server settings](#proxymode)' policy.</span></span>
#### <span data-ttu-id="1efcf-515">Informazioni e impostazioni di Windows</span><span class="sxs-lookup"><span data-stu-id="1efcf-515">Windows information and settings</span></span>
##### <span data-ttu-id="1efcf-516">Info su Criteri di gruppo (ADMX)</span><span class="sxs-lookup"><span data-stu-id="1efcf-516">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="1efcf-517">Nome univoco Criteri di gruppo: ProxyServer</span><span class="sxs-lookup"><span data-stu-id="1efcf-517">GP unique name: ProxyServer</span></span>
- <span data-ttu-id="1efcf-518">Nome Criteri di gruppo: Indirizzo o URL del server proxy</span><span class="sxs-lookup"><span data-stu-id="1efcf-518">GP name: Address or URL of proxy server</span></span>
- <span data-ttu-id="1efcf-519">Percorso Criteri di gruppo: Modelli amministrativi/Microsoft Edge Update/Server proxy</span><span class="sxs-lookup"><span data-stu-id="1efcf-519">GP path: Administrative Templates/Microsoft Edge Update/Proxy Server</span></span>
- <span data-ttu-id="1efcf-520">Nome file ADMX Criteri di gruppo: msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="1efcf-520">GP ADMX file name: msedgeupdate.admx</span></span>
##### <span data-ttu-id="1efcf-521">Impostazioni del Registro di sistema di Windows</span><span class="sxs-lookup"><span data-stu-id="1efcf-521">Windows Registry Settings</span></span>
- <span data-ttu-id="1efcf-522">Percorso: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="1efcf-522">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="1efcf-523">Nome valore: ProxyServer</span><span class="sxs-lookup"><span data-stu-id="1efcf-523">Value Name: ProxyServer</span></span>
- <span data-ttu-id="1efcf-524">Tipo valore: REG_SZ</span><span class="sxs-lookup"><span data-stu-id="1efcf-524">Value Type: REG_SZ</span></span>
##### <span data-ttu-id="1efcf-525">Valore di esempio</span><span class="sxs-lookup"><span data-stu-id="1efcf-525">Example value:</span></span>
```
https://www.microsoft.com
```
[<span data-ttu-id="1efcf-526">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="1efcf-526">Back to top</span></span>](#microsoft-edge---update-policies)


## <span data-ttu-id="1efcf-527">Criteri di Microsoft Edge WebView</span><span class="sxs-lookup"><span data-stu-id="1efcf-527">Microsoft Edge WebView policies</span></span>

[<span data-ttu-id="1efcf-528">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="1efcf-528">Back to top</span></span>](#microsoft-edge---update-policies)
### <span data-ttu-id="1efcf-529">Installa (WebView)</span><span class="sxs-lookup"><span data-stu-id="1efcf-529">Install (WebView)</span></span>
#### <span data-ttu-id="1efcf-530">Consenti installazione</span><span class="sxs-lookup"><span data-stu-id="1efcf-530">Allow installation</span></span>
><span data-ttu-id="1efcf-531">Microsoft Edge Update 1.3.127.1 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="1efcf-531">Microsoft Edge Update 1.3.127.1 and later</span></span>

#### <span data-ttu-id="1efcf-532">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1efcf-532">Description</span></span>
<span data-ttu-id="1efcf-533">Consente di specificare se è possibile installare Microsoft Edge WebView tramite Microsoft Edge Update.</span><span class="sxs-lookup"><span data-stu-id="1efcf-533">Lets you specify whether Microsoft Edge WebView can be installed using Microsoft Edge Update.</span></span>

  - <span data-ttu-id="1efcf-534">Abilitando questo criterio, gli utenti possono installare Microsoft Edge WebView tramite Microsoft Edge Update.</span><span class="sxs-lookup"><span data-stu-id="1efcf-534">If you enable this policy, users can install Microsoft Edge WebView through Microsoft Edge Update.</span></span>
  - <span data-ttu-id="1efcf-535">Disabilitando questo criterio, gli utenti non possono installare Microsoft Edge WebView tramite Microsoft Edge Update.</span><span class="sxs-lookup"><span data-stu-id="1efcf-535">If you disable this policy, users cannot install Microsoft Edge WebView through Microsoft Edge Update.</span></span>
  - <span data-ttu-id="1efcf-536">Non configurando questo criterio, la configurazione del criterio "[Consenti installazione predefinita](#installdefault)" determina se gli utenti possono installare Microsoft Edge WebView tramite Microsoft Edge Update.</span><span class="sxs-lookup"><span data-stu-id="1efcf-536">If you don't configure this policy, the '[Allow installation default](#installdefault)' policy configuration determines whether users can install Microsoft Edge WebView through Microsoft Edge Update.</span></span>
#### <span data-ttu-id="1efcf-537">Informazioni e impostazioni di Windows</span><span class="sxs-lookup"><span data-stu-id="1efcf-537">Windows information and settings</span></span>
##### <span data-ttu-id="1efcf-538">Info su Criteri di gruppo (ADMX)</span><span class="sxs-lookup"><span data-stu-id="1efcf-538">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="1efcf-539">Nome univoco Criteri di gruppo: Install</span><span class="sxs-lookup"><span data-stu-id="1efcf-539">GP unique name: Install</span></span>
- <span data-ttu-id="1efcf-540">Nome Criteri di gruppo: Consenti installazione</span><span class="sxs-lookup"><span data-stu-id="1efcf-540">GP name: Allow installation</span></span>
- <span data-ttu-id="1efcf-541">Percorso Criteri di gruppo: Modelli amministrativi/Microsoft Edge Update/Microsoft Edge WebView</span><span class="sxs-lookup"><span data-stu-id="1efcf-541">GP path: Administrative Templates/Microsoft Edge Update/Microsoft Edge WebView</span></span>
- <span data-ttu-id="1efcf-542">Nome file ADMX Criteri di gruppo: msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="1efcf-542">GP ADMX file name: msedgeupdate.admx</span></span>
##### <span data-ttu-id="1efcf-543">Impostazioni del Registro di sistema di Windows</span><span class="sxs-lookup"><span data-stu-id="1efcf-543">Windows Registry Settings</span></span>
- <span data-ttu-id="1efcf-544">Percorso: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="1efcf-544">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="1efcf-545">Nome:</span><span class="sxs-lookup"><span data-stu-id="1efcf-545">Value Name:</span></span> 
  - <span data-ttu-id="1efcf-546">Install{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}</span><span class="sxs-lookup"><span data-stu-id="1efcf-546">Install{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}</span></span>
- <span data-ttu-id="1efcf-547">Tipo valore: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="1efcf-547">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="1efcf-548">Valore di esempio</span><span class="sxs-lookup"><span data-stu-id="1efcf-548">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="1efcf-549">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="1efcf-549">Back to top</span></span>](#microsoft-edge---update-policies)


### <span data-ttu-id="1efcf-550">Aggiornameto (WebView)</span><span class="sxs-lookup"><span data-stu-id="1efcf-550">Update (WebView)</span></span>
#### <span data-ttu-id="1efcf-551">Sostituzione dei criteri di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="1efcf-551">Update policy override</span></span>
><span data-ttu-id="1efcf-552">Microsoft Edge Update 1.3.127.1 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="1efcf-552">Microsoft Edge Update 1.3.127.1 and later</span></span>

#### <span data-ttu-id="1efcf-553">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1efcf-553">Description</span></span>
<span data-ttu-id="1efcf-554">Consente di specificare se abilitare gli aggiornamenti automatici per Microsoft Edge WebView.</span><span class="sxs-lookup"><span data-stu-id="1efcf-554">Lets you specify whether or not automatic updates are enabled for Microsoft Edge WebView.</span></span> <span data-ttu-id="1efcf-555">Microsoft Edge WebView è una componente usata dalle applicazioni per visualizzare il contenuto Web.</span><span class="sxs-lookup"><span data-stu-id="1efcf-555">Microsoft Edge WebView is a component used by applications to display web content.</span></span>
<span data-ttu-id="1efcf-556">Gli aggiornamenti automatici sono abilitati per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="1efcf-556">Automatic updates are enabled by default.</span></span> <span data-ttu-id="1efcf-557">Disabilitando gli aggiornamenti automatici per Microsoft Edge WebView potrebbero verificarsi problemi di compatibilità con le applicazioni che dipendono da questa componente.</span><span class="sxs-lookup"><span data-stu-id="1efcf-557">Disabling automatic updates for Microsoft Edge WebView might cause compatibility issues with applications that depend on this component.</span></span>

  <span data-ttu-id="1efcf-558">Abilitando questo criterio, Microsoft Edge Update gestisce gli aggiornamenti di Microsoft Edge WebView in base alla configurazione delle seguenti opzioni:</span><span class="sxs-lookup"><span data-stu-id="1efcf-558">If you enable this policy, Microsoft Edge Update handles Microsoft Edge WebView updates according to how you configure the following options:</span></span>
  - <span data-ttu-id="1efcf-559">Consenti sempre gli aggiornamenti: gli aggiornamenti vengono scaricati e applicati automaticamente</span><span class="sxs-lookup"><span data-stu-id="1efcf-559">Always allow updates: Updates are automatically downloaded and applied</span></span>
  - <span data-ttu-id="1efcf-560">Aggiornamenti disabilitati: gli aggiornamenti non vengono mai scaricati o applicati</span><span class="sxs-lookup"><span data-stu-id="1efcf-560">Updates disabled: Updates are never downloaded or applied</span></span>

  <span data-ttu-id="1efcf-561">Non abilitando questo criterio, gli aggiornamenti verranno scaricati e applicati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="1efcf-561">If you don't enable this policy, updates are automatically downloaded and applied.</span></span>
#### <span data-ttu-id="1efcf-562">Informazioni e impostazioni di Windows</span><span class="sxs-lookup"><span data-stu-id="1efcf-562">Windows information and settings</span></span>
##### <span data-ttu-id="1efcf-563">Info su Criteri di gruppo (ADMX)</span><span class="sxs-lookup"><span data-stu-id="1efcf-563">Group Policy (ADMX) info</span></span>
- <span data-ttu-id="1efcf-564">Nome univoco Criteri di gruppo: Update</span><span class="sxs-lookup"><span data-stu-id="1efcf-564">GP unique name: Update</span></span>
- <span data-ttu-id="1efcf-565">Nome Criteri di gruppo: Sostituzione dei criteri di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="1efcf-565">GP name: Update policy override</span></span>
- <span data-ttu-id="1efcf-566">Percorso Criteri di gruppo: Modelli amministrativi/Microsoft Edge Update/Microsoft Edge WebView</span><span class="sxs-lookup"><span data-stu-id="1efcf-566">GP path: Administrative Templates/Microsoft Edge Update/Microsoft Edge WebView</span></span>
- <span data-ttu-id="1efcf-567">Nome file ADMX Criteri di gruppo: msedgeupdate.admx</span><span class="sxs-lookup"><span data-stu-id="1efcf-567">GP ADMX file name: msedgeupdate.admx</span></span>
##### <span data-ttu-id="1efcf-568">Impostazioni del Registro di sistema di Windows</span><span class="sxs-lookup"><span data-stu-id="1efcf-568">Windows Registry Settings</span></span>
- <span data-ttu-id="1efcf-569">Percorso: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span><span class="sxs-lookup"><span data-stu-id="1efcf-569">Path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate</span></span>
- <span data-ttu-id="1efcf-570">Nome:</span><span class="sxs-lookup"><span data-stu-id="1efcf-570">Value Name:</span></span> 
  - <span data-ttu-id="1efcf-571">Update{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}</span><span class="sxs-lookup"><span data-stu-id="1efcf-571">Update{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}</span></span>
- <span data-ttu-id="1efcf-572">Tipo valore: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="1efcf-572">Value Type: REG_DWORD</span></span>
##### <span data-ttu-id="1efcf-573">Valore di esempio</span><span class="sxs-lookup"><span data-stu-id="1efcf-573">Example value:</span></span>
```
0x00000001
```
[<span data-ttu-id="1efcf-574">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="1efcf-574">Back to top</span></span>](#microsoft-edge---update-policies)


## <span data-ttu-id="1efcf-575">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1efcf-575">See also</span></span>
  - [<span data-ttu-id="1efcf-576">Configurazione di Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="1efcf-576">Configuring Microsoft Edge</span></span>](configure-microsoft-edge.md)
  - [<span data-ttu-id="1efcf-577">Pagina di destinazione di Microsoft Edge in modalità Enterprise</span><span class="sxs-lookup"><span data-stu-id="1efcf-577">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)