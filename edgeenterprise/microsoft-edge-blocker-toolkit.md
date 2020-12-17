---
title: Blocker Toolkit per disabilitare la distribuzione automatica di Microsoft Edge
ms.author: kvice
author: dan-wesley
manager: srugh
ms.date: 12/16/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Blocker Toolkit per disabilitare la distribuzione automatica di Microsoft Edge
ms.openlocfilehash: 9fb97d2dfec4822f8ce76dc3e37b85118c6572ad
ms.sourcegitcommit: 606282995b466a968bab40c16005a6653323c763
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/16/2020
ms.locfileid: "11229617"
---
# <span data-ttu-id="88c57-103">Blocker Toolkit per disabilitare la distribuzione automatica di Microsoft Edge (basata su Chromium)</span><span class="sxs-lookup"><span data-stu-id="88c57-103">Blocker Toolkit to disable automatic delivery of Microsoft Edge (Chromium-based)</span></span>

<span data-ttu-id="88c57-104">In questo articolo viene descritto Blocker Toolkit per disabilitare la distribuzione e l'installazione automatica di Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="88c57-104">This article describes the Blocker Toolkit for disabling automatic delivery and installation of Microsoft Edge.</span></span>

<span data-ttu-id="88c57-105">Gli aggiornamenti seguenti sono stati apportati a questo articolo:</span><span class="sxs-lookup"><span data-stu-id="88c57-105">The following updates have been made to this article:</span></span>

- <span data-ttu-id="88c57-106">**09/01/2020** con ulteriori informazioni sui dispositivi che potrebbero richiedere l'uso di Blocker Toolkit</span><span class="sxs-lookup"><span data-stu-id="88c57-106">**01/09/2020** with more information about devices that might require you to use the Blocker Toolkit</span></span>
- <span data-ttu-id="88c57-107">**28/02/2020** per rimuovere "MDM Managed" dai criteri dei dispositivi da escludere da questo aggiornamento automatico</span><span class="sxs-lookup"><span data-stu-id="88c57-107">**2/28/2020** to remove "MDM managed" from the criteria of devices to be excluded from this automatic update</span></span>
- <span data-ttu-id="88c57-108">**30/06/2020** per garantire che tutti i dispositivi connessi a Windows Update possano ricevere questo aggiornamento (effettivo a partire dal 30/07/2020)</span><span class="sxs-lookup"><span data-stu-id="88c57-108">**6/30/2020** to reflect that all Windows Update connected devices are in scope to receive this update (effective no sooner than 7/30/2020)</span></span>
- <span data-ttu-id="88c57-109">**10/12/2020** per spiegare le situazioni pre 20H2 in cui le impostazioni di Blocker Toolkit verranno ignorate</span><span class="sxs-lookup"><span data-stu-id="88c57-109">**12/10/2020** to explain pre 20H2 situations in which the Blocker Toolkit settings will be ignored</span></span>

> [!NOTE]
> <span data-ttu-id="88c57-110">Questo articolo si applica al canale stabile di Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="88c57-110">This applies to Microsoft Edge Stable channel.</span></span>

## <span data-ttu-id="88c57-111">Panoramica</span><span class="sxs-lookup"><span data-stu-id="88c57-111">Overview</span></span>

<span data-ttu-id="88c57-112">Per consentire ai clienti di restare sempre protetti e aggiornati, Microsoft distribuirà Microsoft Edge (basato su Chromium) a tutti i dispositivi connessi a Windows Update con la versione 1803 di Windows 10 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="88c57-112">To help our customers become more secure and up-to-date, Microsoft will distribute Microsoft Edge (Chromium-based) to all Windows Update-connected devices running Windows 10 version 1803 and newer.</span></span> <span data-ttu-id="88c57-113">Questo processo verrà avviato dopo il 15 gennaio 2020 e ulteriori informazioni saranno disponibili a partire da tale data.</span><span class="sxs-lookup"><span data-stu-id="88c57-113">This process will start after January 15, 2020 and more information will be available on that date.</span></span>

<span data-ttu-id="88c57-114">Blocker Toolkit è progettato per le organizzazioni che desiderano bloccare la distribuzione automatica di Microsoft Edge (basato su Chromium) nei dispositivi connessi a Windows Update con la versione 1803 di Windows 10 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="88c57-114">The Blocker Toolkit is intended for organizations that would like to block automatic delivery of Microsoft Edge (Chromium-based) to Windows Updated-connected devices running Windows 10 version 1803 and newer.</span></span> <span data-ttu-id="88c57-115">I dispositivi Windows Server Update Services (WSUS) o Windows Update per le aziende gestiti verranno esclusi da questo aggiornamento automatico di Windows, ma potrebbero ricevere il nuovo Microsoft Edge (basato su Chromium) tramite la propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="88c57-115">Devices that are Windows Server Update Services (WSUS) or Windows Update for Business (WUfB) managed will be excluded from this automatic Windows Update, but may receive the new Microsoft Edge (Chromium-based) through their organization.</span></span>

**<span data-ttu-id="88c57-116">È importante notare che:</span><span class="sxs-lookup"><span data-stu-id="88c57-116">It's important to note that:</span></span>**

- <span data-ttu-id="88c57-117">Blocker Toolkit non impedisce agli utenti di installare manualmente Microsoft Edge (basato su Chromium) tramite download da Internet o supporti esterni.</span><span class="sxs-lookup"><span data-stu-id="88c57-117">The Blocker Toolkit will not prevent users from manually installing Microsoft Edge (Chromium-based) from Internet download, or from external media.</span></span>
- <span data-ttu-id="88c57-118">Le organizzazioni con gli aggiornamenti gestiti tramite Windows Update per le aziende (WUfB) non riceveranno automaticamente questo aggiornamento e non devono distribuire Blocker Toolkit.</span><span class="sxs-lookup"><span data-stu-id="88c57-118">Organizations with updates managed through Windows Update for Business (WUfB) will not automatically receive this update and do not need to deploy the blocker toolkit.</span></span>
- <span data-ttu-id="88c57-119">Le organizzazioni con ambienti gestiti con una soluzione per la gestione degli aggiornamenti come Windows Server Update Services (WSUS) o System Center Configuration Manager (SCCM) non devono distribuire Blocker Toolkit.</span><span class="sxs-lookup"><span data-stu-id="88c57-119">Organizations with environments managed with an update management solution such as Windows Server Update Services (WSUS) or System Center Configuration Manager (SCCM) do not have to deploy the Blocker Toolkit.</span></span> <span data-ttu-id="88c57-120">Possono usare questi prodotti per gestire in modo completo la distribuzione degli aggiornamenti rilasciati tramite Windows Update e Microsoft Update, incluso l'[aggiornamento in WSUS per il nuovo Microsoft Edge](https://support.microsoft.com/help/4584642/update-in-wsus-for-the-new-microsoft-edge), all'interno del loro ambiente.</span><span class="sxs-lookup"><span data-stu-id="88c57-120">They can use those products to fully manage deployment of updates released through Windows Update and Microsoft Update, including the [Update in WSUS for the new Microsoft Edge](https://support.microsoft.com/help/4584642/update-in-wsus-for-the-new-microsoft-edge), within their environment.</span></span>
- <span data-ttu-id="88c57-121">Questo aggiornamento è un aggiornamento indipendente (non incluso nell'aggiornamento cumulativo mensile) per offrire ai clienti aziendali la flessibilità e il massimo controllo sulla distribuzione di questo aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="88c57-121">This update is a stand-alone update (not part of the monthly cumulative update) to give Enterprise customers flexibility and maximum control over deploying this update.</span></span>
- <span data-ttu-id="88c57-122">Il nuovo Microsoft Edge (basato su Chromium) è incluso nell'aggiornamento delle funzionalità di Windows 10, versione 20H2 nella seconda metà di 2020.</span><span class="sxs-lookup"><span data-stu-id="88c57-122">The new Microsoft Edge (Chromium-based) is included as part of the Windows 10, version 20H2 feature update in the second half of 2020.</span></span> <span data-ttu-id="88c57-123">Il toolkit Blocker non influisce sui comportamenti e sulla distribuzione della versione 20H2.</span><span class="sxs-lookup"><span data-stu-id="88c57-123">The Blocker toolkit does not impact 20H2 behaviors or deployment.</span></span> <span data-ttu-id="88c57-124">Vedere ulteriori informazioni sulla versione 20H2 di Windows 10 [qui](https://blogs.windows.com/windowsexperience/2020/06/16/whats-next-for-windows-10-updates/).</span><span class="sxs-lookup"><span data-stu-id="88c57-124">See more information about Windows 10, version 20H2 [here](https://blogs.windows.com/windowsexperience/2020/06/16/whats-next-for-windows-10-updates/).</span></span>

<span data-ttu-id="88c57-125">Puoi scaricare il file eseguibile di Blocker Toolkit all'indirizzo [https://msedgeblockertoolkit.blob.core.windows.net/blockertoolkit/MicrosoftEdgeChromiumBlockerToolkit.exe](https://msedgeblockertoolkit.blob.core.windows.net/blockertoolkit/MicrosoftEdgeChromiumBlockerToolkit.exe).</span><span class="sxs-lookup"><span data-stu-id="88c57-125">You can download the Blocker Toolkit executable file from [https://msedgeblockertoolkit.blob.core.windows.net/blockertoolkit/MicrosoftEdgeChromiumBlockerToolkit.exe](https://msedgeblockertoolkit.blob.core.windows.net/blockertoolkit/MicrosoftEdgeChromiumBlockerToolkit.exe).</span></span>

### <span data-ttu-id="88c57-126">Componenti del toolkit</span><span class="sxs-lookup"><span data-stu-id="88c57-126">Toolkit components</span></span>

<span data-ttu-id="88c57-127">Il toolkit contiene i seguenti componenti:</span><span class="sxs-lookup"><span data-stu-id="88c57-127">This toolkit contains the following components:</span></span>

- <span data-ttu-id="88c57-128">Script di blocco eseguibile (.CMD)</span><span class="sxs-lookup"><span data-stu-id="88c57-128">Executable blocker script (.CMD)</span></span>
- <span data-ttu-id="88c57-129">Modello amministrativo Criteri di gruppo (.ADMX e .ADML)</span><span class="sxs-lookup"><span data-stu-id="88c57-129">Group Policy Administrative Template (.ADMX and .ADML)</span></span>

### <span data-ttu-id="88c57-130">Sistemi operativi supportati</span><span class="sxs-lookup"><span data-stu-id="88c57-130">Supported Operating Systems</span></span>

<span data-ttu-id="88c57-131">Windows 10, versione 1803 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="88c57-131">Windows 10 version 1803 and newer.</span></span>

## <span data-ttu-id="88c57-132">Script di blocco</span><span class="sxs-lookup"><span data-stu-id="88c57-132">Blocker script</span></span>

<span data-ttu-id="88c57-133">Lo script crea una chiave del Registro di sistema e imposta il valore associato per bloccare o sbloccare (a seconda dell'opzione della riga di comando utilizzata) la distribuzione automatica di Microsoft Edge (basato su Chromium) nel computer locale o in un computer di destinazione remoto.</span><span class="sxs-lookup"><span data-stu-id="88c57-133">The script creates a registry key and sets the associated value to block or unblock (depending on the command-line option used) automatic delivery of Microsoft Edge (Chromium-based) on either the local machine or a remote target machine.</span></span>

**<span data-ttu-id="88c57-134">Chiave del Registro di sistema:</span><span class="sxs-lookup"><span data-stu-id="88c57-134">Registry key:</span></span>** `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\EdgeUpdate`<br>
**<span data-ttu-id="88c57-135">Nome del valore della chiave:</span><span class="sxs-lookup"><span data-stu-id="88c57-135">Key value name:</span></span>** `DoNotUpdateToEdgeWithChromium`

| <span data-ttu-id="88c57-136">Valore</span><span class="sxs-lookup"><span data-stu-id="88c57-136">Value</span></span>                | <span data-ttu-id="88c57-137">Risultato</span><span class="sxs-lookup"><span data-stu-id="88c57-137">Result</span></span>                         |
|----------------------|--------------------------------|
| *<span data-ttu-id="88c57-138">La chiave non è definita</span><span class="sxs-lookup"><span data-stu-id="88c57-138">Key is not defined</span></span>* | <span data-ttu-id="88c57-139">La distribuzione *non* è bloccata.</span><span class="sxs-lookup"><span data-stu-id="88c57-139">Distribution is *not* blocked.</span></span> |
| <span data-ttu-id="88c57-140">0</span><span class="sxs-lookup"><span data-stu-id="88c57-140">0</span></span>                    | <span data-ttu-id="88c57-141">La distribuzione *non* è bloccata.</span><span class="sxs-lookup"><span data-stu-id="88c57-141">Distribution is *not* blocked.</span></span> |
| <span data-ttu-id="88c57-142">1</span><span class="sxs-lookup"><span data-stu-id="88c57-142">1</span></span>                    | <span data-ttu-id="88c57-143">La distribuzione è bloccata.</span><span class="sxs-lookup"><span data-stu-id="88c57-143">Distribution is blocked.</span></span>       |

<span data-ttu-id="88c57-144">Lo script ha la seguente sintassi della riga di comando:</span><span class="sxs-lookup"><span data-stu-id="88c57-144">The script has the following command-line syntax:</span></span><br>
`EdgeChromium_Blocker.cmd [<machine name>] [/B] [/U] [/H]`

### <span data-ttu-id="88c57-145">Nome computer</span><span class="sxs-lookup"><span data-stu-id="88c57-145">Machine name</span></span>

<span data-ttu-id="88c57-146">Il parametro `<machine name>` è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="88c57-146">The `<machine name>` parameter is optional.</span></span> <span data-ttu-id="88c57-147">Se non viene specificato, l'azione viene eseguita nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="88c57-147">If not specified, the action is performed on the local machine.</span></span> <span data-ttu-id="88c57-148">In caso contrario, l'accesso al computer remoto avviene tramite le funzionalità del Registro di sistema remoto del comando `REG`.</span><span class="sxs-lookup"><span data-stu-id="88c57-148">Otherwise, the remote machine is accessed through the remote registry capabilities of the `REG` command.</span></span> <span data-ttu-id="88c57-149">Se non è possibile accedere al Registro di sistema remoto a causa di autorizzazioni di sicurezza o non è possibile trovare il computer remoto, viene restituito un messaggio di errore dal comando `REG`.</span><span class="sxs-lookup"><span data-stu-id="88c57-149">If the remote registry can't be accessed due to security permissions or the remote machine can't be found, an error message is returned from the `REG` command.</span></span>

### <span data-ttu-id="88c57-150">Opzioni</span><span class="sxs-lookup"><span data-stu-id="88c57-150">Switches</span></span>

<span data-ttu-id="88c57-151">Le opzioni usate dallo script si escludono a vicenda e viene attivata solo la prima opzione valida di un determinato comando.</span><span class="sxs-lookup"><span data-stu-id="88c57-151">Switches used by the script are mutually exclusive and only the first valid switch from a given command is acted on.</span></span> <span data-ttu-id="88c57-152">Lo script può essere eseguito più volte nello stesso computer.</span><span class="sxs-lookup"><span data-stu-id="88c57-152">The script can be run multiple times on the same machine.</span></span>

| <span data-ttu-id="88c57-153">Opzione</span><span class="sxs-lookup"><span data-stu-id="88c57-153">Switch</span></span>       | <span data-ttu-id="88c57-154">Descrizione</span><span class="sxs-lookup"><span data-stu-id="88c57-154">Description</span></span>                              |
|--------------|------------------------------------------|
| `/B`         | <span data-ttu-id="88c57-155">La distribuzione è bloccata</span><span class="sxs-lookup"><span data-stu-id="88c57-155">Blocks distribution</span></span>                      |
| `/U`         | <span data-ttu-id="88c57-156">La distribuzione è sbloccata</span><span class="sxs-lookup"><span data-stu-id="88c57-156">Unblocks distribution</span></span>                    |
| `/H` <span data-ttu-id="88c57-157">o</span><span class="sxs-lookup"><span data-stu-id="88c57-157">or</span></span> `/?` | <span data-ttu-id="88c57-158">Viene visualizzata la seguente guida di riepilogo:</span><span class="sxs-lookup"><span data-stu-id="88c57-158">Displays the following summary help:</span></span><br>`This tool can be used to remotely block or unblock the delivery of Microsoft Edge (Chromium-based) through Automatic Updates.`<br> `Usage:`<br>`EdgeChromium_Blocker.cmd [<machine name>] [/B][/U][/H]`<br>`B = Block Microsoft Edge (Chromium-based) deployment`<br>`U = Allow Microsoft Edge (Chromium-based) deployment`<br>`H = Help`<br>`Examples:`<br>`EdgeChromium_Blocker.cmd mymachine /B (blocks delivery on machine "mymachine")`<br>`EdgeChromium_Blocker.cmd /U (unblocks delivery on the local machine)`<br> |

## <span data-ttu-id="88c57-159">Modello amministrativo Criteri di gruppo (file .ADMX e .ADML)</span><span class="sxs-lookup"><span data-stu-id="88c57-159">Group Policy Administrative Template (.ADMX and .ADML files)</span></span>

<span data-ttu-id="88c57-160">Il modello amministrativo Criteri di gruppo (file .ADMX e .ADML) consente agli amministratori di importare le nuove impostazioni di Criteri di gruppo per bloccare o sbloccare la distribuzione automatica di Microsoft Edge (basato su Chromium) nell'ambiente Criteri di gruppo e usare Criteri di gruppo per eseguire l'azione in modo centralizzato nei sistemi dell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="88c57-160">The Group Policy Administrative Template (.ADMX  and .ADML files) allows administrators to import the new Group Policy settings to block or unblock automatic delivery of Microsoft Edge (Chromium-based) into their Group Policy environment, and use Group Policy to centrally execute the action across systems in their environment.</span></span>

<span data-ttu-id="88c57-161">Per gli utenti che eseguono Windows 10 RS3 Enterprise/EDU e RS4 e versioni successive, i criteri sono nel percorso seguente:</span><span class="sxs-lookup"><span data-stu-id="88c57-161">Users running Windows 10 RS3 Enterprise/EDU and RS4 and newer, will see the policy under the following path:</span></span>

```
/Computer Configuration  
  /Administrative Templates
    /Classic Administrative Templates
      /Windows Components
        /Windows Update  
          /Microsoft Edge (Chromium-based) Blockers  
```

<span data-ttu-id="88c57-162">Questa impostazione è disponibile solo come impostazione per computer, non è disponibile un'impostazione per utente.</span><span class="sxs-lookup"><span data-stu-id="88c57-162">This setting is available only as a Computer setting; there is no Per-User setting.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="88c57-163">Questa impostazione del Registro di sistema non è archiviata in una chiave dei criteri e viene considerata una *preferenza*.</span><span class="sxs-lookup"><span data-stu-id="88c57-163">This registry setting isn't stored in a policies key and is considered a *preference*.</span></span> <span data-ttu-id="88c57-164">Pertanto, se l'oggetto Criteri di gruppo che implementa l'impostazione viene rimosso o se il criterio è impostato su **Non configurato**, l'impostazione rimane inalterata.</span><span class="sxs-lookup"><span data-stu-id="88c57-164">Therefore, if the Group Policy Object that implements the setting is ever removed or the policy is set to **Not Configured**, the setting will remain.</span></span> <span data-ttu-id="88c57-165">Per sbloccare la distribuzione di Microsoft Edge (basata su Chromium) tramite Criteri di gruppo, imposta i criteri su **Disabilitato**.</span><span class="sxs-lookup"><span data-stu-id="88c57-165">To unblock distribution of Microsoft Edge (Chromium-based) by using Group Policy, set the policy to **Disabled**.</span></span>

## <span data-ttu-id="88c57-166">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="88c57-166">See also</span></span>

- [<span data-ttu-id="88c57-167">Pagina di destinazione di Microsoft Edge in modalità Enterprise</span><span class="sxs-lookup"><span data-stu-id="88c57-167">Microsoft Edge Enterprise landing page</span></span>](https://www.microsoftedgeinsider.com/enterprise)
- [<span data-ttu-id="88c57-168">Aggiornamenti di Windows per supportare Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="88c57-168">Windows updates to support Microsoft Edge</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-sysupdate-windows-updates)
- [<span data-ttu-id="88c57-169">Come accedere alla versione precedente di Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="88c57-169">How to access the old version of Microsoft Edge</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-sysupdate-access-old-edge)
